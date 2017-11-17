---
title: "擴充工作清單 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "工作清單"
ms.assetid: 9d84c9c4-7796-4fa1-86f8-22d077b79f7e
caps.latest.revision: 17
caps.handback.revision: 17
manager: "douge"
---
# 擴充工作清單
[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] **工作清單**可讓使用者加入自訂程式設計工作、檢視連結至程式碼行的工作註解，以及建立和檢視工作訊息的自訂類別。  
  
 工作是透過名為 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> 的服務所處理，而服務實作 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList> 和 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList2>。 若要使用基本 \[工作清單\] 功能，您必須實作 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider> 來建立工作提供者。  
  
 向 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> 服務註冊您工作提供者的方式是呼叫 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RegisterTaskProvider%2A> 其會傳回必須用來唯一識別所有後續交易中之工作提供者的 Cookie 值。  
  
 每個工作提供者實作都負責維護內部工作清單。 工作提供者可以對 \[工作清單\] 呼叫 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList.RefreshTasks%2A> 以更新顯示的工作清單。 發生這種情況時：  
  
1.  這個服務會使用 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider.EnumTaskItems%2A> 方法來回呼至工作提供者。  
  
2.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider.EnumTaskItems%2A> 的工作提供者實作會傳回 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumTaskItems> 物件。  
  
3.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumTaskItems> 物件會逐一查看 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskItem> 物件集合。  
  
4.  接著，<xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList> 服務會更新 \[工作清單\] 顯示。  
  
 還有其他功能可用。<xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskProvider3> 介面可讓每個工作提供者提供專屬的一組自訂資料行。  
  
## 範例  
 下列程式碼範例會示範工作提供者的實作。  
  
```vb#  
Class TaskProvider Implements ITaskProvider Implements IVsSolutionEvents Public Sub New(ByVal provider As IServiceProvider) _imageList.ImageSize = New Size(9, 16) _imageList.Images.AddStrip(Resources.priority) _imageList.TransparentColor = Color.FromArgb(0, 255, 0) _serviceProvider = provider Dim taskList As IVsTaskList = TryCast(_serviceProvider.GetService(GetType(SVsTaskList)), IVsTaskList) Dim hr As Integer = taskList.RegisterTaskProvider(Me, _cookie) Debug.Assert(hr = VSConstants.S_OK, "RegisterTaskProvider did not return S_OK.") Debug.Assert(_cookie <> 0, "RegisterTaskProvider did not return a nonzero cookie.") SetCommandHandlers() ListenForProjectUnload() End Sub #Region "ITaskProvider Members" Public Sub AddResult(ByVal result As IScanResult, ByVal projectFile As String) Dim fullPath As String = result.FilePath If Not Path.IsPathRooted(fullPath) Then fullPath = Utilities.AbsolutePathFromRelative(fullPath, Path.GetDirectoryName(projectFile)) End If If result.Scanned Then For Each hit As IScanHit In result.Results If hit.Warning IsNot Nothing AndAlso hit.Warning.Length > 0 Then ' See if we've warned about this term before; ' if so, don't warn again. If _termsWithDuplicateWarning.Find(Function(ByVal item As String) [String].Compare(item, hit.Term.Text, StringComparison.OrdinalIgnoreCase) = 0) Is Nothing Then _tasks.Add(New Task(hit.Term.Text, hit.Term.Severity, hit.Term.[Class], hit.Warning, "", "", _ -1, -1, "", "", Me, _serviceProvider)) _termsWithDuplicateWarning.Add(hit.Term.Text) End If End If _tasks.Add(New Task(hit.Term.Text, hit.Term.Severity, hit.Term.[Class], hit.Term.Comment, hit.Term.RecommendedTerm, fullPath, _ hit.Line, hit.Column, projectFile, hit.LineText, Me, _serviceProvider)) Next Else _tasks.Add(New Task("", 1, "", [String].Format(CultureInfo.CurrentUICulture, Resources.FileNotScannedError, fullPath), "", fullPath, _ -1, -1, projectFile, "", Me, _serviceProvider)) End If Refresh() End Sub Public Sub Clear() _tasks.Clear() Refresh() End Sub Public Sub SetAsActiveProvider() Dim taskList As IVsTaskList2 = TryCast(_serviceProvider.GetService(GetType(SVsTaskList)), IVsTaskList2) Dim ourGuid As Guid = _providerGuid Dim hr As Integer = taskList.SetActiveProvider(ourGuid) Debug.Assert(hr = VSConstants.S_OK, "SetActiveProvider did not return S_OK.") End Sub Public Sub ShowTaskList() Dim shell As IVsUIShell = TryCast(_serviceProvider.GetService(GetType(SVsUIShell)), IVsUIShell) Dim dummy As Object = Nothing Dim cmdSetGuid As Guid = VSConstants.GUID_VSStandardCommandSet97 Dim hr As Integer = shell.PostExecCommand(cmdSetGuid, CInt(VSConstants.VSStd97CmdID.TaskListWindow), 0, dummy) Debug.Assert(hr = VSConstants.S_OK, "SetActiveProvider did not return S_OK.") End Sub ''' <summary> ''' Returns an image index between 0 and 2 inclusive corresponding ''' to the specified severity. ''' </summary> Public Shared Function GetImageIndexForSeverity(ByVal severity As Integer) As Integer Return Math.Max(1, Math.Min(3, severity)) - 1 End Function Public ReadOnly Property IsShowingIgnoredInstances() As Boolean Get Return _showingIgnoredInstances End Get End Property #End Region #Region "IVsTaskProvider Members" Public Function EnumTaskItems(ByRef ppenum As IVsEnumTaskItems) As Integer ppenum = New TaskEnumerator(_tasks, IsShowingIgnoredInstances) Return VSConstants.S_OK End Function <DllImport("comctl32.dll")> _ Private Shared Function ImageList_Duplicate(ByVal original As IntPtr) As IntPtr End Function Public Function ImageList(ByRef phImageList As IntPtr) As Integer phImageList = ImageList_Duplicate(_imageList.Handle) Return VSConstants.S_OK End Function Public Function OnTaskListFinalRelease(ByVal pTaskList As IVsTaskList) As Integer If (_cookie <> 0) AndAlso (pTaskList IsNot Nothing) Then Dim hr As Integer = pTaskList.UnregisterTaskProvider(_cookie) Debug.Assert(hr = VSConstants.S_OK, "UnregisterTaskProvider did not return S_OK.") End If Return VSConstants.S_OK End Function Public Function ReRegistrationKey(ByRef pbstrKey As String) As Integer pbstrKey = "" Return VSConstants.E_NOTIMPL End Function Public Function SubcategoryList(ByVal cbstr As UInteger, ByVal rgbstr As String(), ByRef pcActual As UInteger) As Integer pcActual = 0 Return VSConstants.E_NOTIMPL End Function End Class  
```  
  
```c#  
class TaskProvider : ITaskProvider, IVsSolutionEvents { public TaskProvider(IServiceProvider provider) { _imageList.ImageSize = new Size(9, 16); _imageList.Images.AddStrip(Resources.priority); _imageList.TransparentColor = Color.FromArgb(0, 255, 0); _serviceProvider = provider; IVsTaskList taskList = _serviceProvider.GetService(typeof(SVsTaskList)) as IVsTaskList; int hr = taskList.RegisterTaskProvider(this, out _cookie); Debug.Assert(hr == VSConstants.S_OK, "RegisterTaskProvider did not return S_OK."); Debug.Assert(_cookie != 0, "RegisterTaskProvider did not return a nonzero cookie."); SetCommandHandlers(); ListenForProjectUnload(); } #region ITaskProvider Members public void AddResult(IScanResult result, string projectFile) { string fullPath = result.FilePath; if (!Path.IsPathRooted(fullPath)) { fullPath = Utilities.AbsolutePathFromRelative(fullPath, Path.GetDirectoryName(projectFile)); } if (result.Scanned) { foreach (IScanHit hit in result.Results) { if (hit.Warning != null && hit.Warning.Length > 0) { // See if we've warned about this term before; // if so, don't warn again. if (null == _termsWithDuplicateWarning.Find( delegate(string item) { return String.Compare(item, hit.Term.Text, StringComparison.OrdinalIgnoreCase) == 0; })) { _tasks.Add(new Task(hit.Term.Text, hit.Term.Severity, hit.Term.Class, hit.Warning, "", "", -1, -1, "", "", this, _serviceProvider)); _termsWithDuplicateWarning.Add(hit.Term.Text); } } _tasks.Add(new Task(hit.Term.Text, hit.Term.Severity, hit.Term.Class, hit.Term.Comment, hit.Term.RecommendedTerm, fullPath, hit.Line, hit.Column, projectFile, hit.LineText, this, _serviceProvider)); } } else { _tasks.Add(new Task("", 1, "", String.Format(CultureInfo.CurrentUICulture, Resources.FileNotScannedError, fullPath), "", fullPath, -1, -1, projectFile, "", this, _serviceProvider)); } Refresh(); } public void Clear() { _tasks.Clear(); Refresh(); } public void SetAsActiveProvider() { IVsTaskList2 taskList = _serviceProvider.GetService(typeof(SVsTaskList)) as IVsTaskList2; Guid ourGuid = _providerGuid; int hr = taskList.SetActiveProvider(ref ourGuid); Debug.Assert(hr == VSConstants.S_OK, "SetActiveProvider did not return S_OK."); } public void ShowTaskList() { IVsUIShell shell = _serviceProvider.GetService(typeof(SVsUIShell)) as IVsUIShell; object dummy = null; Guid cmdSetGuid = VSConstants.GUID_VSStandardCommandSet97; int hr = shell.PostExecCommand(ref cmdSetGuid, (int)VSConstants.VSStd97CmdID.TaskListWindow, 0, ref dummy); Debug.Assert(hr == VSConstants.S_OK, "SetActiveProvider did not return S_OK."); } /// <summary> /// Returns an image index between 0 and 2 inclusive corresponding /// to the specified severity. /// </summary> public static int GetImageIndexForSeverity(int severity) { return Math.Max(1, Math.Min(3, severity)) - 1; } public bool IsShowingIgnoredInstances { get { return _showingIgnoredInstances; } } #endregion #region IVsTaskProvider Members public int EnumTaskItems(out IVsEnumTaskItems ppenum) { ppenum = new TaskEnumerator(_tasks, IsShowingIgnoredInstances); return VSConstants.S_OK; } [DllImport("comctl32.dll")] static extern IntPtr ImageList_Duplicate(IntPtr original); public int ImageList(out IntPtr phImageList) { phImageList = ImageList_Duplicate(_imageList.Handle); return VSConstants.S_OK; } public int OnTaskListFinalRelease(IVsTaskList pTaskList) { if ((_cookie != 0) && (null != pTaskList)) { int hr = pTaskList.UnregisterTaskProvider(_cookie); Debug.Assert(hr == VSConstants.S_OK, "UnregisterTaskProvider did not return S_OK."); } return VSConstants.S_OK; } public int ReRegistrationKey(out string pbstrKey) { pbstrKey = ""; return VSConstants.E_NOTIMPL; } public int SubcategoryList(uint cbstr, string[] rgbstr, out uint pcActual) { pcActual = 0; return VSConstants.E_NOTIMPL; } }  
```  
  
## 請參閱  
 [建立自訂工作清單檢視](/visual-cpp/misc/creating-custom-task-list-views)   
 [如何：建立工作清單的自訂分類](../misc/how-to-create-custom-categories-of-task-lists.md)