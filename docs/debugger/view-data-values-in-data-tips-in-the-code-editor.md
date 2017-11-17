---
title: "在程式碼編輯器的資料提示中檢視資料值 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "DataTips 工具"
  - "偵錯 [Visual Studio], DataTips"
ms.assetid: ffa7bd18-439b-4685-a9b3-c7884b5de41f
caps.latest.revision: 38
caps.handback.revision: 38
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 在程式碼編輯器的資料提示中檢視資料值
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

資料提示方塊提供方便的方法，讓您在偵錯期間檢視程式中的變數資訊。  資料提示方塊只能夠在中斷模式中運作，並且只能使用目前執行範圍內的變數。  
  
 在 [!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)] 中，DataTips 可以固定至原始程式檔中的特定位置，或是浮動在所有 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 視窗的上層。  
  
### 若要顯示資料提示方塊 \(僅限在中斷模式中\)  
  
1.  在來源視窗中，將滑鼠指標放在目前範圍中的任何變數。  
  
     資料提示方塊就會出現。  
  
    > [!NOTE]
    >  資料提示一律在暫停執行的內容中評估，而不是在游標停留的內容中評估。  如果您將游標停留在另一個函式的變數上，而該變數的名稱與目前內容中變數的名稱相同，則將另一個函式中的變數值當做目前內容中的變數值顯示。  
  
2.  當您移除滑鼠指標時，資料提示方塊就會消失。  若要固定 DataTip，讓它保持開啟，請按一下 \[**固定在來源**\] 圖示，或者  
  
    -   以滑鼠右鍵按一下變數，然後按一下 \[**固定在來源**\]。  
  
     當偵錯工作階段結束時，固定的資料提示方塊就會關閉。  
  
### 若要取消固定資料提示方塊並讓它浮動  
  
-   在固定的資料提示方塊中，按一下 \[**從來源取消固定**\] 圖示。  
  
     固定圖示會變更為已取消固定的位置。  資料提示方塊現在會浮動在任何開啟視窗的上方。  當偵錯工作階段結束時，浮動的資料提示方塊就會關閉。  
  
### 若要重新固定浮動的資料提示方塊  
  
-   按一下資料提示方塊中的固定圖示。  
  
     固定圖示會變更為已固定的位置。  如果資料提示方塊位在來源視窗外部，則會停用固定圖示，而且無法固定資料提示方塊。  
  
### 若要關閉資料提示方塊  
  
-   將滑鼠指標放在資料提示方塊上，然後按一下 \[**關閉**\] 圖示。  
  
### 若要關閉所有資料提示方塊  
  
-   按一下 \[**偵錯**\] 功能表上的 \[**清除所有 DataTips**\]。  
  
### 若要關閉特定檔案的所有資料提示方塊  
  
-   按一下 \[**偵錯**\] 功能表上的 \[**清除固定在 *File* 的所有 DataTips**\]。  
  
## 展開和編輯資訊  
 您可以使用資料提示方塊展開陣列、結構或物件，以便檢視其成員。  也可以從資料提示方塊編輯變數值。  
  
#### 若要展開變數以檢視項目  
  
-   在資料提示方塊中，將滑鼠指標放在變數名稱前面的 **\+** 號上。  
  
     變數就會展開並以樹狀目錄格式來顯示項目。  
  
     當變數展開時，您可以使用鍵盤上的方向鍵上下移動。  或者，您也可以使用滑鼠。  
  
#### 若要使用資料提示方塊編輯變數的值  
  
1.  按一下資料提示方塊中的值。  唯讀值會停用這項功能。  
  
2.  輸入新的值，然後按 ENTER 鍵。  
  
## 讓資料提示方塊變成透明  
 如果您想要看到資料提示方塊後方的程式碼，則可以暫時讓資料提示方塊變成透明。  此選項不適用於固定或浮動的 DataTips。  
  
#### 若要讓資料提示方塊變成透明  
  
-   在資料提示方塊中，按 CTRL 鍵。  
  
     只要您按住 CTRL 鍵，資料提示方塊就會維持透明。  
  
## 視覺化處理複雜資料型別  
 如果在資料提示方塊中變數名稱旁邊出現放大鏡圖示，該資料型別的變數可以使用一或多個[視覺化檢視](../debugger/create-custom-visualizers-of-data.md)。  您可以使用視覺化檢視，以更有意義的方式 \(通常是圖形\) 來顯示資訊。  
  
#### 若要使用視覺化檢視來檢視變數的內容  
  
-   按一下放大鏡圖示，以選取資料型別的預設視覺化檢視。  
  
     \-或\-  
  
     按一下視覺化檢視旁邊的快顯箭號，以從資料型別的適當視覺化檢視清單中進行選取。  
  
     視覺化檢視會顯示資訊。  
  
## 將資訊加入至監看式視窗  
 如果您想要繼續監看變數，可以從資料提示方塊將變數加入至 \[**監看式**\] 視窗。  
  
#### 若要將變數加入至監看式視窗  
  
-   以滑鼠右鍵按一下資料提示方塊，然後按一下 \[**加入監看式**\]。  
  
     變數便會加入至 \[**監看式**\] 視窗。  如果您使用的版本支援多個 \[**監看式**\] 視窗，則變數會加入至 \[**監看式 1**\]。  
  
## 匯入和匯出資料提示方塊  
 您可以將資料提示方塊匯出至 XML 檔，之後您就可以將這個檔案與同事共用，或是使用文字編輯器進行編輯。  
  
#### 若要匯出資料提示方塊  
  
1.  按一下 \[偵錯\] 功能表上的 \[**匯出 DataTips**\]。  
  
     \[**匯出 DataTips**\] 對話方塊隨即出現。  
  
2.  像平常處理其他檔案一樣，巡覽至您要儲存 XML 檔的位置，並在 \[**檔案名稱**\] 方塊中輸入檔案名稱，然後按一下 \[**確定**\]。  
  
#### 若要匯入資料提示方塊  
  
1.  按一下 \[偵錯\] 功能表上的 \[**匯入 DataTips**\]。  
  
     \[**匯入 DataTips**\] 對話方塊隨即出現。  
  
2.  使用這個對話方塊尋找您要開啟的 XML 檔，然後按一下 \[**確定**\]。  
  
## 請參閱  
 [在偵錯工具中檢視資料](../debugger/viewing-data-in-the-debugger.md)   
 [如何：使用快速監看式對話方塊](../Topic/How%20to:%20Use%20the%20QuickWatch%20Dialog%20Box.md)   
 [視覺化檢視](../debugger/create-custom-visualizers-of-data.md)   
 [如何：變更偵錯工具視窗的數值格式](../Topic/How%20to:%20Change%20the%20Numeric%20Format%20of%20Debugger%20Windows.md)