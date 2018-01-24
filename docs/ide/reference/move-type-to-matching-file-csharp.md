---
title: "將類型移到對應的檔案 - 重構 (C#) | Microsoft Docs"
ms.custom: 
ms.date: 11/16/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: dotnet
ms.openlocfilehash: 4b7b9b1ba52bed5d2bdf042db0149d799c489a7d
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2018
---
# <a name="move-a-type-to-a-matching-file-in-c"></a>使用 C# 將類型移到對應的檔案 #

**功能：**讓您將選取的類型移到具有相同名稱的個別檔案。

**時機：**您在相同檔案中有多個類別、結構、介面等，而想要加以分隔。

**原因：**將多個類型放在相同檔案中會很難尋找這些類型。  藉由將類型移到具有相同名稱的檔案，程式碼會變得較容易閱讀及瀏覽。

**做法：**

1. 醒目標示要移動的類型名稱，或將文字游標放在要移動的類型名稱內：

   ![醒目標示的程式碼](media/movetype-highlight-cs.png)

1. 接著，執行下列其中一項操作：
   * **鍵盤**
     * 按 **Ctrl+.** 以觸發 [快速動作與重構] 功能表，然後從 [預覽] 快顯視窗中選取 [將類型移到 *TypeName*.cs]，其中 *TypeName* 是您所選類型的名稱。
   * **滑鼠**
     * 在程式碼上按一下滑鼠右鍵，選取 [快速動作與重構] 功能表，然後從 [預覽] 快顯視窗中選取 [將類型移到 *TypeName*.cs]，其中 *TypeName* 是您所選類型的名稱。

   系統將會立即將類型移到您方案內具有該名稱的新檔案。

   ![內嵌結果](media/movetype-result-cs.png)

## <a name="see-also"></a>另請參閱

[重構](../refactoring-in-visual-studio.md)