---
title: 'Walkthrough: Adding Controls to a Worksheet at Run Time in VSTO add-in Project | Microsoft Docs'
ms.custom: 
ms.date: 02/02/2017
ms.prod: visual-studio-dev14
ms.reviewer: 
ms.suite: 
ms.technology:
- office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- add-ins [Office development in Visual Studio], adding controls
- controls [Office development in Visual Studio], adding to worksheets at run time
- application-level add-ins [Office development in Visual Studio], adding controls
- worksheets, adding controls at run time
ms.assetid: 4f68677a-4789-4564-b229-02e2d4031a5f
caps.latest.revision: 38
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: 05ef7ad5662fd9009f082abb01a111e152be4ab4
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="walkthrough-adding-controls-to-a-worksheet-at-run-time-in-vsto-add-in-project"></a>Walkthrough: Adding Controls to a Worksheet at Run Time in VSTO add-in Project
  You can add controls to any open worksheet by using an Excel VSTO Add-in. This walkthrough demonstrates how to use the Ribbon to enable users to add a <xref:Microsoft.Office.Tools.Excel.Controls.Button>, a <xref:Microsoft.Office.Tools.Excel.NamedRange>, and a <xref:Microsoft.Office.Tools.Excel.ListObject> to a worksheet. For information, see [Adding Controls to Office Documents at Run Time](../vsto/adding-controls-to-office-documents-at-run-time.md).  
  
 **Applies to:** The information in this topic applies to VSTO Add-in projects for Excel. For more information, see [Features Available by Office Application and Project Type](../vsto/features-available-by-office-application-and-project-type.md).  
  
 This walkthrough illustrates the following tasks:  
  
-   Providing a user interface (UI) to add controls to the worksheet.  
  
-   Adding controls to the worksheet.  
  
-   Removing controls from the worksheet.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Prerequisites  
 You need the following components to complete this walkthrough:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   Excel  
  
## <a name="creating-a-new-excel-vsto-add-in-project"></a>Creating a New Excel VSTO Add-in Project  
 Start by creating an Excel VSTO Add-in project.  
  
#### <a name="to-create-a-new-excel-vsto-add-in-project"></a>To create a new Excel VSTO Add-in project  
  
1.  In [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], create an Excel VSTO Add-in project with the name **ExcelDynamicControls**. For more information, see [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
2.  Add a reference to the **Microsoft.Office.Tools.Excel.v4.0.Utilities.dll** assembly. This reference is required to programmatically add a Windows Forms control to a worksheet later in this walkthrough.  
  
## <a name="providing-a-ui-to-add-controls-to-a-worksheet"></a>Providing a UI to Add Controls to a Worksheet  
 Add a custom tab to the Excel Ribbon. Users can select check boxes on the tab to add controls to a worksheet.  
  
#### <a name="to-provide-a-ui-to-add-controls-to-a-worksheet"></a>To provide a UI to add controls to a worksheet  
  
1.  On the **Project** menu, click **Add New Item**.  
  
2.  In the **Add New Item** dialog box, select **Ribbon (Visual Designer)**, and then click **Add**.  
  
     A file named **Ribbon1.cs** or **Ribbon1.vb** opens in the Ribbon Designer and displays a default tab and group.  
  
3.  From the **Office Ribbon Controls** tab of the **Toolbox**, drag a CheckBox control onto **group1**.  
  
4.  Click **CheckBox1** to select it.  
  
5.  In the **Properties** window, change the following properties.  
  
    |Property|Value|  
    |--------------|-----------|  
    |**Name**|**Button**|  
    |**Label**|**Button**|  
  
6.  Add a second check box to **group1**, and then change the following properties.  
  
    |Property|Value|  
    |--------------|-----------|  
    |**Name**|**NamedRange**|  
    |**Label**|**NamedRange**|  
  
7.  Add a third check box to **group1**, and then change the following properties.  
  
    |Property|Value|  
    |--------------|-----------|  
    |**Name**|**ListObject**|  
    |**Label**|**ListObject**|  
  
## <a name="adding-controls-to-the-worksheet"></a>Adding Controls to the Worksheet  
 Managed controls can only be added to host items, which act as containers. Because VSTO Add-in projects work with any open workbook, the VSTO Add-in converts the worksheet into a host item, or gets an existing host item, before adding the control. Add code to the click event handlers of each control to generate a <xref:Microsoft.Office.Tools.Excel.Worksheet> host item that is based on the open worksheet. Then, add a <xref:Microsoft.Office.Tools.Excel.Controls.Button>, a <xref:Microsoft.Office.Tools.Excel.NamedRange>, and a <xref:Microsoft.Office.Tools.Excel.ListObject> at the current selection in the worksheet.  
  
#### <a name="to-add-controls-to-a-worksheet"></a>To add controls to a worksheet  
  
1.  In the Ribbon Designer, double-click **Button**.  
  
     The <xref:Microsoft.Office.Tools.Ribbon.RibbonCheckBox.Click> event handler of the **Button** check box opens in the Code Editor.  
  
2.  Replace the `Button_Click` event handler with the following code.  
  
     This code uses the `GetVstoObject` method to get a host item that represents the first worksheet in the workbook, and then adds a <xref:Microsoft.Office.Tools.Excel.Controls.Button> control to the currently selected cell.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#2](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#2)]  [!code-vb[Trin_Excel_Dynamic_Controls#2](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#2)]  
  
3.  In **Solution Explorer**, select Ribbon1.cs or Ribbon1.vb.  
  
4.  On the **View** menu, click **Designer**.  
  
5.  In the Ribbon Designer, double-click **NamedRange**.  
  
6.  Replace the `NamedRange_Click` event handler with the following code.  
  
     This code uses the `GetVstoObject` method to get a host item that represents the first worksheet in the workbook, and then defines a <xref:Microsoft.Office.Tools.Excel.NamedRange> control for the currently selected cell or cells.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#3](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#3)]  [!code-vb[Trin_Excel_Dynamic_Controls#3](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#3)]  
  
7.  In the Ribbon Designer, double-click **ListObject**.  
  
8.  Replace the `ListObject_Click` event handler with the following code.  
  
     This code uses the `GetVstoObject` method to get a host item that represents the first worksheet in the workbook, and then defines a <xref:Microsoft.Office.Tools.Excel.ListObject> for the currently selected cell or cells.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#4](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#4)]  [!code-vb[Trin_Excel_Dynamic_Controls#4](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#4)]  
  
9. Add the following statements to the top of the Ribbon code file.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#1](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/Ribbon1.cs#1)]   [!code-vb[Trin_Excel_Dynamic_Controls#1](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/Ribbon1.vb#1)]  
  
## <a name="removing-controls-from-the-worksheet"></a>Removing Controls from the Worksheet  
 Controls are not persisted when the worksheet is saved and closed. You should programmatically remove all generated Windows Forms controls before the worksheet is saved, or only an outline of the control will appear when the workbook is opened again. Add code to the <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> event that removes Windows Forms controls from the controls collection of the generated host item. For more information, see [Persisting Dynamic Controls in Office Documents](../vsto/persisting-dynamic-controls-in-office-documents.md).  
  
#### <a name="to-remove-controls-from-the-worksheet"></a>To remove controls from the worksheet  
  
1.  In **Solution Explorer**, select ThisAddIn.cs or ThisAddIn.vb.  
  
2.  On the **View** menu, click **Code**.  
  
3.  Add the following method to the ThisAddIn class. This code gets the first worksheet in the workbook and then uses the `HasVstoObject` method to check whether the worksheet has a generated worksheet object. If the generated worksheet object has controls, the code gets that worksheet object and iterates through the control collection, removing the controls.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#6](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#6)]  [!code-vb[Trin_Excel_Dynamic_Controls#6](../vsto/codesnippet/VisualBasic/Trin_Excel_Dynamic_Controls/ThisAddIn.vb#6)]  
  
4.  In C#, you must create an event handler for the <xref:Microsoft.Office.Interop.Excel.AppEvents_Event.WorkbookBeforeSave> event. You can place this code in the `ThisAddIn_Startup` method. For more information about creating event handlers, see [How to: Create Event Handlers in Office Projects](../vsto/how-to-create-event-handlers-in-office-projects.md). Replace the `ThisAddIn_Startup` method with the following code.  
  
     [!code-csharp[Trin_Excel_Dynamic_Controls#5](../vsto/codesnippet/CSharp/Trin_Excel_Dynamic_Controls/ThisAddIn.cs#5)]  
  
## <a name="testing-the-solution"></a>Testing the Solution  
 Add controls to a worksheet by selecting them from a custom tab on the Ribbon. When you save the worksheet, these controls are removed.  
  
#### <a name="to-test-the-solution"></a>To test the solution.  
  
1.  Press F5 to run your project.  
  
2.  Select any cell in Sheet1.  
  
3.  Click the **Add-Ins** tab.  
  
4.  In the **group1** group, click **Button**.  
  
     A button appears in the selected cell.  
  
5.  Select a different cell in Sheet1.  
  
6.  In the **group1** group, click **NamedRange**.  
  
     A named range is defined for the selected cell.  
  
7.  Select a series of cells in Sheet1.  
  
8.  In the **group1** group, click **ListObject**.  
  
     A list object is added for the selected cells.  
  
9. Save the worksheet.  
  
     The controls that you added to Sheet1 no longer appear.  
  
## <a name="next-steps"></a>Next Steps  
 You can learn more about controls in Excel VSTO Add-in projects from this topic:  
  
-   To learn about how to save controls to a worksheet, see the Excel VSTO Add-in Dynamic Controls Sample at [Office Development Samples and Walkthroughs](../vsto/office-development-samples-and-walkthroughs.md).  
  
## <a name="see-also"></a>See Also  
 [Excel Solutions](../vsto/excel-solutions.md)   
 [Windows Forms Controls on Office Documents Overview](../vsto/windows-forms-controls-on-office-documents-overview.md)   
 [Controls on Office Documents](../vsto/controls-on-office-documents.md)   
 [NamedRange Control](../vsto/namedrange-control.md)   
 [ListObject Control](../vsto/listobject-control.md)  
  
  