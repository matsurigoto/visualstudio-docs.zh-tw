---
title: 'How to: Programmatically Add Shapes to a Visio Document | Microsoft Docs'
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
- Visio [Office development in Visual Studio], adding Visio shapes
- shapes [Office development in Visual Studio], adding Visio shapes
ms.assetid: 29613237-88f5-41a7-9e13-cfa177f41221
caps.latest.revision: 17
author: kempb
ms.author: kempb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: 2adff4c408493c1a69a44207d9aad801ce8266fd
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="how-to-programmatically-add-shapes-to-a-visio-document"></a>How to: Programmatically Add Shapes to a Visio Document
  You can add shapes to a Microsoft Office Visio document by retrieving the masters from a stencil and dropping the shapes on the active page.  
  
 For more information, see the VBA reference documentation for the [Microsoft.Office.Interop.Visio.Documents.Add](http://msdn.microsoft.com/library/office/ff766868.aspx) method, [Microsoft.Office.Interop.Visio.Application.ActivePage](http://msdn.microsoft.com/library/office/ff765484.aspx) property, and [Microsoft.Office.Interop.Visio.Page.Drop](http://msdn.microsoft.com/library/office/ff765054.aspx) method.  
  
## <a name="adding-shapes-to-a-visio-document"></a>Adding Shapes to a Visio Document  
  
#### <a name="to-add-shapes-to-a-visio-document"></a>To add shapes to a Visio document  
  
-   With a document active, retrieve the masters from the Documents.Masters collection and drop the shapes on the active document. You can retrieve a master by using the index or master name.  
  
     The following code example creates a blank Visio document, and then opens it with the **Basic Shapes** stencil docked. The code then retrieves several shapes and drops them on the active page.  
  
     [!code-csharp[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/CSharp/trin_vstcorevisioautomationaddin/ThisAddIn.cs#13)]  [!code-vb[Trin_VstcoreVisioAutomationAddIn#13](../vsto/codesnippet/VisualBasic/trin_vstcorevisioautomationaddin/ThisAddIn.vb#13)]  
  
## <a name="see-also"></a>See Also  
 [Visio Solutions](../vsto/visio-solutions.md)   
 [Visio Object Model Overview](../vsto/visio-object-model-overview.md)   
 [Working with Visio Shapes](../vsto/working-with-visio-shapes.md)   
 [How to: Programmatically Copy and Paste Shapes in a Visio Document](../vsto/how-to-programmatically-copy-and-paste-shapes-in-a-visio-document.md)  
  
  