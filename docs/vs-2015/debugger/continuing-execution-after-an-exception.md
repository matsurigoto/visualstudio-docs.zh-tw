---
title: 例外狀況之後繼續執行 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- managed exceptions, continuing execution after
- exceptions, continuing execution after
- debugger, exceptions
- managed code, exception handling
- exception handling, continuing execution after
- execution, continuing after an exception
- program execution
- threading [Visual Studio], continuing execution after exceptions
- Exceptions dialog box
- programs, executing
ms.assetid: 6fe97aac-2131-4615-bd92-d3afee741558
caps.latest.revision: 30
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a71d71622809dfaeea399355e490fe4e69b52b9f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47496527"
---
# <a name="continuing-execution-after-an-exception"></a>例外狀況之後繼續執行
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[繼續執行之後例外狀況](https://docs.microsoft.com/visualstudio/debugger/continuing-execution-after-an-exception)。  
  
當偵錯工具因為例外狀況而中斷執行時，對話方塊隨即出現。 若是 Visual Basic 或 C#，您會看到[例外狀況助理](http://msdn.microsoft.com/library/992892ac-9d52-44cc-bf09-b44bfc5befeb)對話方塊中，依預設。 C + +，您會看到較舊**例外狀況** 對話方塊。 如果您使用 Visual Basic 或 C#，但已停用**例外狀況助理**中**選項** 對話方塊中，您會看到**例外狀況** 對話方塊。  
  
 當**例外狀況助理**或是**例外狀況**對話方塊隨即出現，您可以嘗試修正造成例外狀況的問題。  
  
## <a name="managed-code"></a>Managed 程式碼  
 在 Managed 程式碼中，您可以在出現未處理的例外狀況之後，繼續在相同的執行緒中執行。 **例外狀況助理**回溯呼叫堆疊來擲回例外狀況的位置。  
  
## <a name="native-code"></a>機器碼  
 在原生 C/C++ 中，您擁有兩個選項：  
  
-   您可以按一下**中斷**並嘗試修正此問題。 當您處於中斷模式時，您可以回溯呼叫堆疊中的框架上按一下滑鼠右鍵**呼叫堆疊** 視窗，然後選取**回溯至此框架**快顯功能表。 當您繼續偵錯**例外狀況**對話方塊會再度出現如果您有尚未修正問題。 否則，請**例外狀況**不會再次顯示對話方塊。  
  
-   您可以按一下**繼續**繼續執行，但不會嘗試修正此問題。 **例外狀況**對話方塊隨即再度出現。  
  
## <a name="mixed-code"></a>混合程式碼  
 如果在偵錯原生和 Managed 混合的程式碼時發生未處理的例外狀況，作業系統條件約束會禁止回溯呼叫堆疊。 如果您嘗試使用捷徑功能表回溯呼叫堆疊，就會出現錯誤訊息，說明在混合程式碼偵錯期間，偵錯工具無法從未處理的例外狀況回溯。  
  
## <a name="see-also"></a>另請參閱  
 [使用偵錯工具管理例外狀況](../debugger/managing-exceptions-with-the-debugger.md)





