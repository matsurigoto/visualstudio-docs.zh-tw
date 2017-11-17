---
title: "如何：管理編輯器模式 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- word wrap
- views, virtual space
- line numbers, displaying
- virtual space mode
- line numbers
- Code Editor, view and display options
- full screen mode
- Code Editor, modes
- views, splitting
- views, word wrapping
- fonts and size
- views, creating new windows
- views, line numbers
- views, changing mode
- views, outlining
ms.assetid: 1fb48027-d870-439f-8b72-4a0321390748
caps.latest.revision: 20
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 5ea9179ad37514ffad4876177b05150eecc22def
ms.openlocfilehash: 71566f11a069d266ded2aebe02bbf388cf00730e
ms.contentlocale: zh-tw
ms.lasthandoff: 05/24/2017

---
# <a name="how-to-manage-editor-modes"></a>如何：管理編輯器模式
您可以用各種不同的顯示模式顯示 Visual Studio 程式碼編輯器。  
  
> [!NOTE]
>  根據您目前使用的設定或版本，您所看到的對話方塊與功能表命令可能會與 [說明] 中描述的不同。 若要變更設定，請從 [ **工具** ] 功能表中選取 [ **匯入和匯出設定** ]。 如需詳細資訊，請參閱[將 Visual Studio IDE 個人化](../ide/personalizing-the-visual-studio-ide.md)。  
  
## <a name="enabling-full-screen-mode"></a>啟用全螢幕模式  
 您可以選擇隱藏所有工具視窗，並且只檢視文件視窗，方法是啟用 [全螢幕] 模式。  
  
#### <a name="to-enable-full-screen-mode"></a>啟用全螢幕模式  
  
-   按 ALT+SHIFT+ENTER 來進入或結束 [全螢幕] 模式。  
  
     -或-  
  
-   在 [命令] 視窗中發出命令 `View.Fullscreen`。  
  
## <a name="enabling-virtual-space-mode"></a>啟用虛擬空間模式  
 在 [虛擬空間] 模式中，會在每一行程式碼的結尾插入空格。 選取這個選項，可在程式碼旁邊一致的位置上放置註解。  
  
#### <a name="to-enable-virtual-space-mode"></a>啟用虛擬空間模式  
  
1.  選取 [工具] 功能表上的 [選項]。  
  
2.  展開 [文字編輯器] 資料夾，然後選擇 [所有語言] 全域設定此選項，或選擇特定語言的資料夾。 (例如，若只要在 Visual Basic 中開啟行號，請選擇 [基本]、[文字編輯器] 選項)。  
  
3.  選取 [一般] 選項，然後在 [設定] 下選取 [啟用虛擬空間]。  
  
    > [!NOTE]
    >  在 [資料行選取] 模式中會啟用 [虛擬空間]。 未啟用 [虛擬空間] 模式時，插入點會從一行結尾直接移到下一行的第一個字元。  
  
## <a name="see-also"></a>另請參閱  
 [自訂編輯器](../ide/customizing-the-editor.md)   
 [在 Visual Studio 中自訂視窗版面配置](../ide/customizing-window-layouts-in-visual-studio.md)   
 [選項對話方塊、環境、字型和色彩](../ide/reference/fonts-and-colors-environment-options-dialog-box.md)