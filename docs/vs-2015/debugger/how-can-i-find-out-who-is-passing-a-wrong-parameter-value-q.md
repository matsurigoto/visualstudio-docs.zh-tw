---
title: 如何發現誰傳錯參數值？ | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.parameters
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging [C++], parameters
- parameters [debugger]
- passing parameters, troubleshooting wrong values
- functions [debugger], detecting wrong parameter values
- parameter values, troubleshooting
ms.assetid: 1f1ae455-0e25-4e9d-b33f-53908f5bd6ce
caps.latest.revision: 22
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1d7ae67e7ba09a25277afc55ef92da47a8e770d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47487653"
---
# <a name="how-can-i-find-out-who-is-passing-a-wrong-parameter-value"></a>如何發現誰傳錯參數值？
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[可如何發現傳錯參數值？](https://docs.microsoft.com/visualstudio/debugger/how-can-i-find-out-who-is-passing-a-wrong-parameter-value-q)。  
  
問題說明  
 我的函式中傳入了一個錯誤的參數。 這個函式會從許多地方呼叫。 我該如何確定錯誤值是誰傳出的？  
  
## <a name="solution"></a>方案  
  
#### <a name="to-resolve-this-problem"></a>若要解決這個問題  
  
1.  在函式的開頭設定位置中斷點。  
  
2.  以滑鼠右鍵按一下中斷點，然後選取**條件**。  
  
3.  在 [**中斷點條件**] 對話方塊中，按一下**條件**核取方塊。 請參閱[進階中斷點](../debugger/using-breakpoints.md#BKMK_Specify_a_breakpoint_condition_using_a_code_expression)。  
  
4.  在文字方塊中輸入運算式，例如 `Var==3`；其中 `Var` 是含有錯誤值的參數名稱，而 `3` 則是傳入的錯誤值。  
  
5.  選取 [**為 True，否則**選項按鈕，然後按一下**確定**] 按鈕。  
  
6.  現在再次執行程式。 當 `Var` 參數的值是 `3` 時，中斷點會造成程式暫止在函式的開頭。  
  
7.  然後您可以使用 [呼叫堆疊] 視窗來找出呼叫函式並且巡覽原始程式碼。 如需詳細資訊，請參閱 <<c0> [ 如何： 使用 [呼叫堆疊] 視窗](../debugger/how-to-use-the-call-stack-window.md)。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯機器碼常見問題集](../debugger/debugging-native-code-faqs.md)   
 [中斷點](http://msdn.microsoft.com/en-us/fe4eedc1-71aa-4928-962f-0912c334d583)   
 [偵錯機器碼](../debugger/debugging-native-code.md)



