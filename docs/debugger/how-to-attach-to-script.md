---
title: "如何：附加至指令碼 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
helpviewer_keywords: 
  - "處理序, 附加至指令碼"
  - "遠端偵錯, 附加至指令碼"
  - "指令碼偵錯, 附加至指令碼"
  - "指令碼, 附加至"
ms.assetid: 82013e9a-ef53-4fd2-b451-a6891cdc6307
caps.latest.revision: 23
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 23
---
# 如何：附加至指令碼
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

這個主題說明如何以手動方式將 Visual Studio 偵錯工具附加至指令碼檔以便進行偵錯。  
  
### 若要附加至執行中的處理序  
  
1.  在 \[**偵錯**\] 功能表上，選擇 \[**附加至處理序**\] \(如果沒有開啟的專案，請在 \[**工具**\] 功能表中選擇 \[**附加至處理序**\]\)。  
  
2.  請在 \[**附加至處理序**\] 對話方塊中查看 \[**可使用的處理序**\] 清單，並且尋找您要附加的指令碼處理程序。  您可經由查看 \[**型別**\] 欄識別指令碼處理程序。  
  
    1.  如果您要偵錯的處理序正執行於另一台電腦上，您必須先選取該遠端電腦。  如需詳細資訊，請參閱 [How to: Select a Remote Computer](http://msdn.microsoft.com/zh-tw/4332ba8e-2f0b-4f62-b96a-e762b9f3c3ba)。  
  
    2.  如果該處理序正在不同的使用者帳戶下執行，請選取 \[**顯示所有使用者的處理序**\] 核取方塊。  
  
    3.  如果您透過 \[**遠端桌面連線**\] 進行連接，請選取 \[**顯示所有工作階段中的處理序**\] 核取方塊。  
  
3.  按一下您要附加的處理序。  
  
4.  在 \[**附加至**\] 方塊中，您應該看見 \[**指令碼**\] 或 \[**自動：指令碼**\]。  如果看到其他項目，請遵照以下步驟：  
  
    1.  按一下 \[**選取**\]。  
  
    2.  在 \[**選取程式碼類型**\] 對話方塊中按一下 \[**偵錯這些程式碼類型**\]，然後選取 \[**指令碼**\]。  
  
    3.  按一下 \[**確定**\]。  
  
5.  按一下 \[**附加**\]。  
  
     此時，您可能會看到警告，指出 Internet Explorer 中已停用指令碼偵錯功能。  如果發生上述情形，請參閱[警告：已停用指令碼偵錯](../debugger/warning-script-debugging-disabled.md)。  
  
 \[**可使用的處理序**\] 清單會在您開啟 \[**處理序**\] 對話方塊時自動顯示。  當對話方塊開啟時，處理序可以在背景中啟動和停止。  所以，內容不一定是最新的。  您可以隨時按 \[**重新整理**\] 按鈕重新整理該清單，查看目前的處理序清單。  
  
 偵錯時，您可以附加至多個程式，但是無論在任何時間，偵錯工具一次只能有一個使用中程式。  您可在 \[偵錯位置\] 工具列中設定使用中程式。  如需詳細資訊，請參閱 [How to: Set the Current Process](http://msdn.microsoft.com/zh-tw/7e1d7fa5-0e40-44cf-8c41-d3dba31c969e)。  
  
 所有 \[**偵錯**\] 功能表的執行命令都會影響使用中的程式。  您可以在 \[處理序\] 對話方塊中斷任何偵錯中的程式。[使用中斷點](../debugger/using-breakpoints.md)  
  
> [!NOTE]
>  如果您嘗試附加至未受信任的使用者帳戶所擁有的處理序，會出現安全性警告對話方塊確認訊息。  如需詳細資訊，請參閱[安全性警告：附加至未受信任的使用者帳戶所擁有的處理序可能會造成危險。如果下面的資訊看起來有問題，或者您並不確定，請不要附加至此處理序](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md)。  
  
 在某些情況下，在終端機服務 \(遠端桌面\) 工作階段中進行偵錯時，\[可使用的處理序\] 清單並不會顯示所有可使用的處理序。  在 [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)] \(含\) 以後版本中，如果您是以受限制的使用者身分執行 Visual Studio，則 \[可使用的處理序\] 清單不會顯示在工作階段 0 中執行的處理序，因為工作階段 0 是用於服務以及其他包括 w3wp.exe 的伺服器處理序。  可藉由使用系統管理員帳戶來執行 Visual Studio，或是從伺服器主控台 \(而非終端機服務工作階段\) 執行 Visual Studio，來解決這個問題。  如果這些解決方法都沒有效，第三個方法就是在 Windows 命令列輸入 vsjitdebugger.exe \-p ProcessId 來附加至處理序。  您可以使用 tlist.exe 來判斷處理序 ID。  若要取得 tlist.exe，您可以從 [Windows 硬體開發人員中心](http://go.microsoft.com/fwlink/?linkid=1651)下載並安裝 Debugging Tools for Windows。  
  
## 請參閱  
 [用戶端指令碼偵錯](../debugger/client-side-script-debugging.md)   
 [附加至執行中處理序](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)   
 [安全性警告：附加至未受信任的使用者帳戶所擁有的處理序可能會造成危險。如果下面的資訊看起來有問題，或者您並不確定，請不要附加至此處理序](../debugger/security-warning-attaching-to-a-process-owned-by-an-untrusted-user-can-be-dangerous-if-the-following-information-looks-suspicious-or-you-are-unsure-do-not-attach-to-this-process.md)   
 [偵錯工具安全性](../debugger/debugger-security.md)