---
title: 'Walkthrough: Complex Data Binding in a Document-Level Project | Microsoft Docs'
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
- data [Office development in Visual Studio], binding data
- complex data [Office development in Visual Studio]
- multiple column data binding [Office development in Visual Studio]
- data binding [Office development in Visual Studio], multiple columns
ms.assetid: 32ffad3d-fba4-476a-99b8-ef440434f4e1
caps.latest.revision: 50
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: eabb6c71606a980cb0056bd844e93cde6c3a746e
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="walkthrough-complex-data-binding-in-a-document-level-project"></a>Walkthrough: Complex Data Binding in a Document-Level Project
  This walkthrough demonstrates the basics of complex data binding in a document-level project. You can bind multiple cells in a Microsoft Office Excel worksheet to fields in the Northwind SQL Server database.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 This walkthrough illustrates the following tasks:  
  
-   Adding a data source to your workbook project.  
  
-   Adding data-bound controls to a worksheet.  
  
-   Saving data changes back to the database.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>Prerequisites  
 You need the following components to complete this walkthrough:  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] or [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)].  
  
-   Access to a server with the Northwind SQL Server sample database.  
  
-   Permissions to read from and write to the SQL Server database.  
  
## <a name="creating-a-new-project"></a>Creating a New Project  
 The first step is to create an Excel workbook project.  
  
#### <a name="to-create-a-new-project"></a>To create a new project  
  
1.  Create an Excel workbook project with the name **My Complex Data Binding**. In the wizard, select **Create a new document**.  
  
     For more information, see [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
     Visual Studio opens the new Excel workbook in the designer and adds the **My Complex Data Binding** project to **Solution Explorer**.  
  
## <a name="creating-the-data-source"></a>Creating the Data Source  
 Use the **Data Sources** window to add a typed dataset to your project.  
  
#### <a name="to-create-the-data-source"></a>To create the data source  
  
1.  If the **Data Sources** window is not visible, display it by, on the menu bar, choosing **View**, **Other Windows**, **Data Sources**.  
  
2.  Choose **Add New Data Source** to start the **Data Source Configuration Wizard**.  
  
3.  Select **Database** and then click **Next**.  
  
4.  Select a data connection to the Northwind sample SQL Server database, or add a new connection by using the **New Connection** button.  
  
5.  After a connection has been selected or created, click **Next**.  
  
6.  Clear the option to save the connection if it is selected, and then click **Next**.  
  
7.  Expand the **Tables** node in the **Database objects** window.  
  
8.  Select the check box next to the **Employees** table.  
  
9. Click **Finish**.  
  
 The wizard adds the **Employees** table to the **Data Sources** window. It also adds a typed dataset to your project that is visible in **Solution Explorer**.  
  
## <a name="adding-controls-to-the-worksheet"></a>Adding Controls to the Worksheet  
 A worksheet will display the **Employees** table when the workbook is opened. Users will be able to make changes to the data and then save those changes back to the database by clicking a button.  
  
 To bind the worksheet to the table automatically, you can add a <xref:Microsoft.Office.Tools.Excel.ListObject> control to the worksheet from the **Data Sources** window. To give the user the option to save changes, add a <xref:System.Windows.Forms.Button> control from the **Toolbox**.  
  
#### <a name="to-add-a-list-object"></a>To add a list object  
  
1.  Verify that the **My Complex Data Binding.xlsx** workbook is open in the Visual Studio designer, with **Sheet1** displayed.  
  
2.  Open the **Data Sources** window and select the **Employees** node.  
  
3.  Click the drop-down arrow that appears.  
  
4.  Select **ListObject** in the drop-down list.  
  
5.  Drag the **Employees** table to cell **A6**.  
  
     A <xref:Microsoft.Office.Tools.Excel.ListObject> control named `EmployeesListObject` is created in cell **A6**. At the same time, a <xref:System.Windows.Forms.BindingSource> named `EmployeesBindingSource`, a table adapter, and a <xref:System.Data.DataSet> instance are added to the project. The control is bound to the <xref:System.Windows.Forms.BindingSource>, which in turn is bound to the <xref:System.Data.DataSet> instance.  
  
#### <a name="to-add-a-button"></a>To add a button  
  
1.  From the **Common Controls** tab of the **Toolbox**, add a <xref:System.Windows.Forms.Button> control to cell **A4** of the worksheet.  
  
 The next step is to add text to the button when the worksheet opens.  
  
## <a name="initializing-the-control"></a>Initializing the Control  
 Add text to the button in the <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> event handler.  
  
#### <a name="to-initialize-the-control"></a>To initialize the control  
  
1.  In **Solution Explorer**, right-click **Sheet1.vb** or **Sheet1.cs**, and then click **View Code** on the shortcut menu.  
  
2.  Add the following code to the `Sheet1_Startup` method to set the text for the b`utton`.  
  
     [!code-csharp[Trin_VstcoreDataExcel#8](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#8)]  [!code-vb[Trin_VstcoreDataExcel#8](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet3.vb#8)]  
  
3.  For C# only, add an event handler for the <xref:System.Windows.Forms.Control.Click> event to the `Sheet1_Startup` method.  
  
     [!code-csharp[Trin_VstcoreDataExcel#9](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#9)]  
  
 Now add code to handle the <xref:System.Windows.Forms.Control.Click> event of the button.  
  
## <a name="saving-changes-to-the-database"></a>Saving Changes to the Database  
 Any changes have been made to the data exist only in the local dataset until they are explicitly saved back to the database.  
  
#### <a name="to-save-changes-to-the-database"></a>To save changes to the database  
  
1.  Add an event handler for the <xref:System.Windows.Forms.Control.Click> event of the b`utton`, and add the following code to commit all changes that have been made in the dataset back to the database.  
  
     [!code-csharp[Trin_VstcoreDataExcel#10](../vsto/codesnippet/CSharp/Trin_VstcoreDataExcelCS/Sheet3.cs#10)]  [!code-vb[Trin_VstcoreDataExcel#10](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataExcelVB/Sheet3.vb#10)]  
  
## <a name="testing-the-application"></a>Testing the Application  
 Now you can test your workbook to verify that the data appears as expected, and that you can manipulate the data in the list object.  
  
#### <a name="to-test-the-data-binding"></a>To test the data binding  
  
-   Press F5.  
  
     Verify that when the workbook opens, the list object is filled with data from the **Employees** table.  
  
#### <a name="to-modify-data"></a>To modify data  
  
1.  Click cell **B7**, which should contain the name **Davolio**.  
  
2.  Type the name **Anderson**, and then press ENTER.  
  
#### <a name="to-modify-a-column-header"></a>To modify a column header  
  
1.  Click the cell that contains the column header **LastName**.  
  
2.  Type **Last Name**, including a space between the two words, and then press ENTER.  
  
#### <a name="to-save-data"></a>To save data  
  
1.  Click **Save** on the worksheet.  
  
2.  Exit Excel. Click **No** when prompted to save the changes you made.  
  
3.  Press F5 to run the project again.  
  
     The list object is filled with data from the **Employees** table.  
  
4.  Notice that the name in cell **B7** is still **Anderson**, which is the data change that you made and saved back to the database. The column header **LastName** has changed back to its original form with no space, because the column header is not bound to the database and you did not save the changes you made to the worksheet.  
  
#### <a name="to-add-new-rows"></a>To add new rows  
  
1.  Select a cell inside the list object.  
  
     A new row appears at the bottom of the list, with an asterisk (**\***) in the first cell of the new row.  
  
2.  Add the following information in the empty row.  
  
    |EmployeeID|LastName|FirstName|Title|  
    |----------------|--------------|---------------|-----------|  
    |10|Ito|Shu|Sales Manager|  
  
#### <a name="to-delete-rows"></a>To delete rows  
  
-   Right-click the number 16 (row 16) on the far left side of the worksheet, and then click **Delete**.  
  
#### <a name="to-sort-the-rows-in-the-list"></a>To sort the rows in the List  
  
1.  Select a cell inside the list.  
  
     Arrow buttons appear in each column header.  
  
2.  Click the arrow button in the **Last Name** column header.  
  
3.  Click **Sort Ascending**.  
  
     The rows are sorted alphabetically by last names.  
  
#### <a name="to-filter-information"></a>To filter information  
  
1.  Select a cell inside the list.  
  
2.  Click the arrow button in the **Title** column header.  
  
3.  Click **Sales Representative**.  
  
     The list shows only those rows that have **Sales Representative** in the **Title** column.  
  
4.  Click the arrow button in the **Title** column header again.  
  
5.  Click **(All)**.  
  
     Filtering is removed and all the rows appear.  
  
## <a name="next-steps"></a>Next Steps  
 This walkthrough shows the basics of binding a table in a database to a list object. Here are some tasks that might come next:  
  
-   Cache the data so that it can be used offline. For more information, see [How to: Cache Data for Use Offline or on a Server](../vsto/how-to-cache-data-for-use-offline-or-on-a-server.md).  
  
-   Deploy the solution. For more information, see [Deploying an Office Solution](../vsto/deploying-an-office-solution.md).  
  
-   Create a master/detail relation between a field and a table. For more information, see [Walkthrough: Creating a Master Detail Relation Using a Cached Dataset](../vsto/walkthrough-creating-a-master-detail-relation-using-a-cached-dataset.md).  
  
## <a name="see-also"></a>See Also  
 [Binding Data to Controls in Office Solutions](../vsto/binding-data-to-controls-in-office-solutions.md)   
 [Data in Office Solutions](../vsto/data-in-office-solutions.md)   
 [Walkthrough: Simple Data Binding in a Document-Level Project](../vsto/walkthrough-simple-data-binding-in-a-document-level-project.md)  
  
  