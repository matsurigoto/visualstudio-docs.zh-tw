---
title: 錯誤： 偵錯不&#39;t，可能因為在系統上啟用核心偵錯 |Microsoft Docs
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
- vs.debug.error.kernel_dbg_enabled
dev_langs:
- FSharp
- VB
- CSharp
- C++
- VB
- CSharp
- C++
helpviewer_keywords:
- kernel debugger
ms.assetid: 630a7abd-3303-4aaa-888a-6de3de14bc01
caps.latest.revision: 26
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 95ee7bddb45fdcdadfdf9cce077b550509ab4c5d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47500645"
---
# <a name="error-debugging-isn39t-possible-because-a-kernel-debugger-is-enabled-on-the-system"></a>錯誤： 偵錯不&#39;t，可能因為在系統上啟用核心偵錯
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[錯誤： 偵錯不是&#39;t，可能因為在系統上啟用核心偵錯](https://docs.microsoft.com/visualstudio/debugger/error-debugging-isn-t-possible-because-a-kernel-debugger-is-enabled-on-the-system)。  
  
當您對 Managed 程式碼進行偵錯時，可能會收到下列錯誤訊息：  
  
```  
Debugging isn't possible because a kernel debugger is enabled on the system  
```  
  
 當您嘗試對 Managed 程式碼進行偵錯時，這個訊息就會出現：  
  
-   在以偵錯模式啟動的 [!INCLUDE[win7](../includes/win7-md.md)] 或 [!INCLUDE[wiprlhext](../includes/wiprlhext-md.md)] 系統上。  
  
-   使用 CLR 2.0、3.0 或 3.5 版的應用程式。  
  
## <a name="solution"></a>方案  
  
#### <a name="to-fix-this-problem"></a>若要修復這個問題  
  
-   將您的應用程式升級為使用 CLR 4.0 或 4.5 版  
  
     -或-  
  
-   停用核心偵錯而以 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 進行偵錯。  
  
     -或-  
  
-   使用核心偵錯工具進行偵錯，不要使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]。  
  
     -或-  
  
-   在核心偵錯工具中，停用使用者模式例外狀況。  
  
#### <a name="to-disable-kernel-debugging-in-the-current-session"></a>若要在目前工作階段中停用核心偵錯  
  
-   在命令提示中，輸入：  
  
    ```  
    Kdbgctrl.exe -d  
    ```  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-windows-vista-and-windows-7"></a>若要停用所有工作階段的核心偵錯 (Windows Vista 和 Windows 7)  
  
1.  在命令提示中，輸入：  
  
    ```  
    bcdedit /debug off   
    ```  
  
2.  重新啟動電腦。  
  
#### <a name="to-disable-kernel-debugging-for-all-sessions-other-windows-operating-systems"></a>若要停用所有工作階段的核心偵錯 (其他 Windows 作業系統)  
  
1.  您的系統磁碟機上尋找 boot.ini (通常是 c:\\)。 boot.ini 檔案可能為隱藏或唯讀狀態。 因此，您必須使用下列命令才能看見該檔案：  
  
    ```  
    dir /ASH  
    ```  
  
2.  使用 [記事本] 開啟 boot.ini 並移除下列選項：  
  
    ```  
    /debug  
    /debugport  
    /baudrate  
    ```  
  
3.  重新啟動電腦。  
  
#### <a name="to-debug-with-the-kernel-debugger"></a>若要使用核心偵錯工具進行偵錯  
  
1.  如果已經連結核心偵錯工具，您將看到一則訊息，詢問您是否要繼續進行偵錯。 按一下這個按鈕繼續進行。  
  
2.  您也可能會收到 `User break exception(Int 3).`。如果發生這種情況，請輸入下列核心偵錯工具命令繼續進行偵錯：  
  
     `gn`  
  
## <a name="see-also"></a>另請參閱  
 [偵錯工具安全性](../debugger/debugger-security.md)   
 [偵錯 Managed 程式碼](../debugger/debugging-managed-code.md)


