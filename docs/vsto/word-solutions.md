---
title: "Word 方案"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "方案 [Visual Studio 中的 Office 程式開發]，Word"
  - "Office 專案 [Visual Studio 中的 Office 程式開發]，Word"
  - "應用程式層級增益集 [Visual Studio 中的 Office 程式開發]，Word"
  - "Word [Visual Studio 中的 Office 程式開發]"
  - "專案 [Visual Studio 中的 Office 程式開發]，Word"
  - "Word [Visual Studio 中的 Office 程式開發]，關於 Word 方案"
  - "Office 方案 [Visual Studio 中的 Office 程式開發]，Word"
  - "Word [Visual Studio 中的 Office 程式開發]，應用程式層級增益集"
  - "文件 [Visual Studio 中的 Office 程式開發]，Word"
  - "Visual Studio 中的 Office 程式開發，Word 方案"
  - "增益集 [Visual Studio 中的 Office 程式開發]，Word"
  - "Word [Visual Studio 中的 Office 程式開發]，文件層級自訂"
  - "使用者介面 [Visual Studio 中的 Office 程式開發]，Word"
  - "Office 文件 [Visual Studio 中的 Office 程式開發]，Word"
  - "文件層級自訂 [Visual Studio 中的 Office 程式開發]，Word"
ms.assetid: ef339ad8-1897-4a44-b588-e6004d0b6d8b
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 31
---
# Word 方案
  Visual Studio 提供的專案範本，可用以建立 Microsoft Office Word 的文件層級自訂和 VSTO 增益集。 您可以使用這些解決方案自動化 Word、擴充 Word 功能和自訂 Word 使用者介面 \(UI\)。 如需文件層級自訂和 VSTO 增益集差異的詳細資訊，請參閱 [Office 方案開發概觀 &#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md)。  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 本主題提供下列資訊：  
  
-   [自動化 Word](#automating)。  
  
-   [開發 Word 的文件層級自訂](#doclevel)。  
  
-   [開發 Word 的 VSTO 增益集](#applevel)。  
  
-   [自訂 Word 的使用者介面](#UI)。  
  
##  <a name="automating"></a> 自動化 Word  
 Word 物件模型會公開您可用來自動化 Word 的許多類型。 例如，您可以程式設計方式建立資料表、格式化文件，以及設定範圍和段落中的文字。 如需詳細資訊，請參閱[Word 物件模型概觀](../vsto/word-object-model-overview.md)。  
  
 在 Visual Studio 中開發 Word 方案時，您也可以在解決方案中使用*「主項目」*\(host items\) 和*「主控制項」*\(host controls\)。 這些都是在 Word 物件模型中擴充某些常用物件的物件，例如 <xref:Microsoft.Office.Interop.Word.Document> 和 <xref:Microsoft.Office.Interop.Word.ContentControl> 物件。 這些擴充物件的行為與它們所根據的 Word 物件一樣，但是這些物件會在物件中加入額外的事件和資料繫結功能。 如需詳細資訊，請參閱[使用擴充物件自動化 Word](../vsto/automating-word-by-using-extended-objects.md)。  
  
##  <a name="doclevel"></a> 開發 Word 的文件層級自訂  
 Microsoft Office Word 文件層級自訂是由與特定文件相關聯的組件所組成。 組件通常是透過自訂 UI 及自動化 Word 來擴充文件。 不同於與 Word 本身相關聯的 VSTO 增益集，您在自訂中實作的功能只有在 Word 中開啟相關聯的文件時才能使用。  
  
 若要建立 Word 的文件層級自訂專案，請使用 Visual Studio \[新增專案\] 對話方塊中的 Word 文件或 Word 範本專案範本。 如需詳細資訊，請參閱[如何：在 Visual Studio 中建立 Office 專案](../vsto/how-to-create-office-projects-in-visual-studio.md)。  
  
 如需文件層級自訂運作方式的詳細資訊，請參閱[文件層級自訂的架構](../vsto/architecture-of-document-level-customizations.md)。  
  
### Word 自訂程式設計模型  
 當您建立 Word 文件層級專案時，Visual Studio 會產生名為 `ThisDocument` 的類別，這是解決方案的基礎。 這個類別代表與解決方案相關聯的文件，並提供撰寫程式碼的起點。  
  
 如需文件層級專案中可用之 `ThisDocument` 類別和其他功能的詳細資訊，請參閱[文件層級自訂程式設計](../vsto/programming-document-level-customizations.md)。  
  
##  <a name="applevel"></a> 開發 Word 的 VSTO 增益集  
 Microsoft Office Word 的 VSTO 增益集是由 Word 載入的組件所組成。 組件通常是透過自訂 UI 及自動化 Word 來擴充 Word。 不像與特定文件相關聯的文件層級自訂，任何文件都可以使用您在 VSTO 增益集中實作的功能。  
  
 若要建立 Word 的 VSTO 增益集專案，請使用 Visual Studio \[新增專案\] 對話方塊中的 Word 增益集專案範本。 如需詳細資訊，請參閱[如何：在 Visual Studio 中建立 Office 專案](../vsto/how-to-create-office-projects-in-visual-studio.md)。  
  
 如需 VSTO 增益集運作方式的一般資訊，請參閱 [VSTO 增益集的架構](../vsto/architecture-of-vsto-add-ins.md)。  
  
### Word 增益集程式設計模型  
 當您建立 Word VSTO 增益集專案時，Visual Studio 會產生名為 `ThisAddIn` 的類別，這是方案的基礎。 這個類別會提供撰寫程式碼的起點，還會向 VSTO 增益集公開 Word 物件模型。  
  
 如需 VSTO 增益集中可用之 `ThisAddIn` 類別和其他功能的詳細資訊，請參閱 [VSTO 增益集程式設計](../vsto/programming-vsto-add-ins.md)。  
  
##  <a name="UI"></a> 自訂 Word 的使用者介面  
 有幾種不同的方式可以自訂 Word 的使用者介面。 有些選項適用於所有專案類型，有些選項則僅限 VSTO 增益集或文件層級自訂使用。  
  
### 適用於所有專案類型的選項  
 下表列出的自訂選項，文件層級自訂和 VSTO 增益集皆可使用。  
  
|工作|如需詳細資訊|  
|--------|------------|  
|自訂功能區。|[功能區概觀](../vsto/ribbon-overview.md)|  
|在文件層級自訂的自訂文件，或任何開啟的 VSTO 增益集文件中，加入 Windows Form 控制項或擴充的 Word 控制項。|[如何：將 Windows Form 控制項加入至 Office 文件](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)<br /><br /> [如何：將內容控制項加入至 Word 文件](../vsto/how-to-add-content-controls-to-word-documents.md)<br /><br /> [如何：將書籤控制項加入至 Word 文件](../vsto/how-to-add-bookmark-controls-to-word-documents.md)|  
  
### 文件層級自訂的選項  
 下表列出的自訂選項僅限文件層級自訂使用。  
  
|工作|如需詳細資訊|  
|--------|------------|  
|在文件中加入執行窗格。|[執行窗格概觀](../vsto/actions-pane-overview.md)<br /><br /> [如何：將執行窗格加入至 Word 文件或 Excel 活頁簿](../vsto/how-to-add-an-actions-pane-to-word-documents-or-excel-workbooks.md)|  
|在文件介面中加入擴充的 XMLNode 和 XMLNodes 控制項。|[如何：將 XMLNode 控制項加入至 Word 文件](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)<br /><br /> [如何：將 XMLNodes 控制項加入至 Word 文件](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)|  
  
### VSTO 增益集的選項  
 下表列出的自訂選項僅限 VSTO 增益集使用。  
  
|工作|如需詳細資訊|  
|--------|------------|  
|建立自訂工作窗格。|[自訂工作窗格](../vsto/custom-task-panes.md)|  
  
### 相關主題  
  
|標題|描述|  
|--------|--------|  
|[Word 物件模型概觀](../vsto/word-object-model-overview.md)|提供 Word 物件模型所提供的主要類型的概觀。|  
|[使用擴充物件自動化 Word](../vsto/automating-word-by-using-extended-objects.md)|提供可以用在 Word 方案中之擴充物件 \(由 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 所提供\) 的相關資訊。|  
|[Office 文件上的 Windows Forms 控制項概觀](../vsto/windows-forms-controls-on-office-documents-overview.md)|描述如何在 Word 文件中加入 Windows Form 控制項。|  
|[逐步解說：建立 Word 的第一個文件層級自訂](../vsto/walkthrough-creating-your-first-document-level-customization-for-word.md)|示範如何建立 Word 的基本文件層級自訂。|  
|[逐步解說：為您的 Word 建立第一個 VSTO 增益集](../vsto/walkthrough-creating-your-first-vsto-add-in-for-word.md)|示範如何建立 Word 的基本 VSTO 增益集。|  
|[逐步解說：在執行階段於 VSTO 增益集中，將控制項加入文件](../vsto/walkthrough-adding-controls-to-a-document-at-run-time-in-a-vsto-add-in.md)|示範如何使用 VSTO 增益集，於執行階段在文件中加入 Windows Form 按鈕和 <xref:Microsoft.Office.Tools.Word.RichTextContentControl>。|  
|[Office 程式開發中的 Word 2010](http://go.microsoft.com/fwlink/?LinkId=199020)|提供有關開發 Word 解決方案 \(不限於使用 Visual Studio 的 Office 程式開發\) 之文章和參考文件的連結。|  
  
  