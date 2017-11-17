---
title: "如何︰ 附加至文件資料的檢視 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "編輯器 [Visual Studio SDK]，自訂-附加到文件資料的檢視"
ms.assetid: f92c0838-45be-42b8-9c55-713e9bb8df07
caps.latest.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 22
---
# 如何︰ 附加至文件資料的檢視
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

如果您有新的文件檢視，您可以將它附加至現有的文件資料物件。  
  
### 若要判斷是否可以將檢視附加至現有的文件資料物件  
  
1.  實作 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A>。  
  
2.  在您實作 `IVsEditorFactory::CreateEditorInstance`, ，呼叫 `QueryInterface` 上現有的文件資料物件時，IDE 會呼叫您 `CreateEditorInstance` 實作。  
  
     呼叫 `QueryInterface` 可讓您檢視現有的文件資料物件，指定在 `punkDocDataExisting` 參數。  
  
     確切的介面，您必須查詢，不過，取決於編輯器中開啟文件中，步驟 4 中所述。  
  
3.  如果找不到現有的文件資料物件上適當的介面，則傳回錯誤程式碼編輯器，指出文件資料物件您的編輯器與不相容。  
  
     在 IDE 的實作 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A>, ，訊息方塊通知您已在另一個編輯器中開啟文件，並詢問您是否要將它關閉。  
  
4.  如果您關閉這份文件時，Visual Studio 會呼叫編輯器 factory 的第二次。 在這個呼叫時， `DocDataExisting` 參數等於 NULL。 編輯器 factory 實作然後可以在您自己的編輯器中開啟文件資料物件。  
  
    > [!NOTE]
    >  若要判斷是否可以使用現有的文件資料物件，您也可以使用私用介面實作的知識將轉換為實際的指標 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] 私用實作的類別。 例如，所有標準編輯器實作 `IVsPersistFileFormat`, ，繼承自 <xref:Microsoft.VisualStudio.OLE.Interop.IPersist>。 因此，您可以呼叫 `QueryInterface` 的 <xref:Microsoft.VisualStudio.OLE.Interop.IPersist.GetClassID%2A>, ，與現有的文件的資料物件的類別識別碼是否符合您的實作類別識別碼，則您可以使用文件資料物件。  
  
## 穩固程式設計  
 當 Visual Studio 會呼叫您的實作 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory.CreateEditorInstance%2A> 方法，它會傳遞回指標至中現有的文件資料物件 `punkDocDataExisting` 參數，如果有的話。 檢查文件資料物件中傳回 `punkDocDataExisting` 來判斷是否適合您的編輯器，請注意，在本主題中的程序的步驟 4 中所述的文件資料物件。 如果適合，則編輯器 factory 應該提供第二個檢視資料中所述 [支援多個文件檢視](../extensibility/supporting-multiple-document-views.md)。 如果沒有，則它應該會顯示適當的錯誤訊息。  
  
## 請參閱  
 [支援多個文件檢視](../extensibility/supporting-multiple-document-views.md)   
 [文件資料，以及在自訂編輯器中的文件檢視](../extensibility/document-data-and-document-view-in-custom-editors.md)