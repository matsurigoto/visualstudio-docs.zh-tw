---
title: 步驟 7：將對話方塊元件新增至您的表單 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ea98c55e-6213-4893-ba7b-f19d7f119527
caps.latest.revision: 17
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 1b6f819495cd6787398fadf414bcfebb2c3eefec
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47496482"
---
# <a name="step-7-add-dialog-components-to-your-form"></a>步驟 7：將對話方塊元件加入至您的表單
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[步驟 7： 將對話方塊元件新增至您的表單](https://docs.microsoft.com/visualstudio/ide/step-7-add-dialog-components-to-your-form)。  
  
若要讓程式開啟圖片檔並選擇背景色彩，請在這個步驟中，將 **OpenFileDialog** 元件和 **ColorDialog** 元件新增至表單。  
  
 元件在某些方面就像控制項一樣。 您可以使用 [工具箱] 將元件新增至表單，並使用 [屬性] 視窗設定該元件的屬性。 但與控制項不同，將元件加入至表單並不會加入可讓使用者在表單上看見的項目。 相反地，只會提供可讓您透過程式碼來觸發的某些行為。 它是一個可開啟 [開啟檔案] 對話方塊的元件。  
  
 ![影片連結](../data-tools/media/playvideo.gif "PlayVideo")如需觀看本主題的影片版本，請參閱[教學課程 1：在 Visual Basic 中建立圖片檢視器 - 影片 3](http://go.microsoft.com/fwlink/?LinkId=205213) 或 [教學課程 1：在 C# 中建立圖片檢視器 - 影片 3](http://go.microsoft.com/fwlink/?LinkId=205202)。 這些影片使用舊版 Visual Studio，因此有一些功能表命令以及某些使用者介面項目會有些微差異。 不過，概念和程序在目前 Visual Studio 版本中的運作方式雷同。  
  
### <a name="to-add-dialog-components-to-your-form"></a>若要將對話方塊元件加入至您的表單  
  
1.  選擇 Windows Form 設計工具 (Form1.cs [設計] 或 Form1.vb [設計])，然後開啟 [工具箱] 中的 [對話方塊] 群組。  
  
    > [!NOTE]
    >  [工具箱] 中的 [對話方塊] 群組包含可開啟許多實用對話方塊的元件，您可用來開啟和儲存檔案、瀏覽資料夾及選擇字型和色彩。 您在本專案中會使用下列兩個對話方塊元件：**OpenFileDialog** 和 **ColorDialog**。  
  
2.  若要將名稱為 **openFileDialog1** 的元件新增至表單，請按兩下 **OpenFileDialog**。 若要將名稱為 **colorDialog1** 的元件新增至表單，請按兩下 [工具箱] 中的 **ColorDialog**。 (您在下一個教學課程步驟中會用到該元件)。您應該會看到 [Windows Form 設計工具] 底部 (在 [圖片檢視器] 表單下方) 的區域，您在其中加入的兩個對話方塊元件各有一個圖示，如下圖所示。  
  
     ![對話方塊元件](../ide/media/express-dialogsadded.png "Express_DialogsAdded")  
對話方塊元件  
  
3.  選擇 Windows Form 設計工具底部區域中的 **openFileDialog1** 圖示。 設定兩個屬性：  
  
    -   將 [篩選條件] 屬性設定為下列值 (您可以複製並貼上)：  
  
        ```  
        JPEG Files (*.jpg)|*.jpg|PNG Files (*.png)|*.png|BMP Files (*.bmp)|*.bmp|All files (*.*)|*.*  
        ```  
  
    -   將 [標題] 屬性設定為下列值：[選取圖片檔案]  
  
         [篩選條件] 屬性設定會指定要在 [選取圖片檔案] 對話方塊中顯示的檔案類型。  
  
    > [!NOTE]
    >  若要查看不同應用程式中的 [開啟檔案] 對話方塊範例，請開啟記事本或小畫家，並在功能表列上選擇 [檔案]、[開啟舊檔]。 請注意底部的 [檔案類型] 下拉式清單。 您剛才已使用 **OpenFileDialog** 元件的 [篩選條件] 屬性來設定此清單。 另外，請注意 [屬性] 視窗中的 [標題] 和 [篩選條件] 屬性都是粗體。 IDE 這樣做是為了讓您知道任何屬性已變更，而不再是預設值。  
  
### <a name="to-continue-or-review"></a>若要繼續或檢視  
  
-   若要移到下一個教學課程步驟，請參閱[步驟 8：為顯示圖片按鈕事件處理常式撰寫程式碼](../ide/step-8-write-code-for-the-show-a-picture-button-event-handler.md)。  
  
-   若要回到上一個教學課程步驟，請參閱[步驟 6：命名您的按鈕控制項](../ide/step-6-name-your-button-controls.md)。



