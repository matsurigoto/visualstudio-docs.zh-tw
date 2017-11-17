---
title: "如何：以限制使用權限偵錯 ClickOnce 應用程式 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "偵錯 [Visual Studio], ClickOnce 應用程式"
  - "ClickOnce 部署, 偵錯"
  - "ClickOnce 應用程式, 偵錯"
ms.assetid: 6991ea91-5253-451b-923d-22273a3d38b1
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 10
---
# 如何：以限制使用權限偵錯 ClickOnce 應用程式
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

身為開發人員，您很可能正在以完全信任權限來執行開發電腦，因此在偵錯 ClickOnce 應用程式時，不會看到使用者以受限權限執行時可能看到的相同安全性例外狀況。  
  
 為了攔截這些例外狀況，您需要使用與終端使用者相同的權限來進行應用程式的偵錯。 權限受限制情況的偵錯可在 \[專案設計工具\] 的 \[安全性\] 頁面上啟用。  
  
 此外，當您開發可呼叫 Web 服務的應用程式時，這些 Web 服務通常位於開發電腦上。 部署之後，使用者會從不同的 URL 存取這些 Web 服務。 若要模擬偵錯期間的使用者體驗，您可以指定 URL，而偵錯工具會將 Web 服務視為是從該 URL 進行呼叫。  
  
### 啟用使用受限權限進行的偵錯  
  
1.  在方案總管中選取專案之後，按一下 \[專案\] 功能表中 \[屬性\]。  
  
2.  在 \[專案設計工具\] 中，按一下 \[安全性\] 索引標籤。  
  
3.  選取 \[啟用 ClickOnce 安全性設定\] 核取方塊，然後按一下 \[這是部分信任的應用程式\] 選項按鈕。  
  
4.  按一下 \[**進階**\] 按鈕。  
  
5.  選取 \[以選取的使用權限集合對此應用程式進行偵錯\] 核取方塊，然後按一下 \[確定\]。  
  
     當您偵錯應用程式時，任何嘗試存取不在權限集中的權限都會引發安全性例外狀況。  
  
### 指定 URL 以進行偵錯  
  
1.  在方案總管中選取專案之後，按一下 \[專案\] 功能表中 \[屬性\]。  
  
2.  在 \[專案設計工具\] 中，按一下 \[安全性\] 索引標籤。  
  
3.  選取 \[啟用 ClickOnce 安全性設定\] 核取方塊，然後按一下 \[這是部分信任的應用程式\] 選項按鈕。  
  
4.  按一下 \[**進階**\] 按鈕。  
  
5.  選取 \[以選取的使用權限集合對此應用程式進行偵錯\] 核取方塊，然後按一下 \[確定\]。  
  
6.  在 \[將下列 URL 視為此應用程式的下載位置來進行偵錯\] 文字方塊中，輸入 URL 或網路路徑。  
  
## 請參閱  
 [如何：設定 ClickOnce 應用程式的自訂使用權限](../deployment/how-to-set-custom-permissions-for-a-clickonce-application.md)   
 [保護 ClickOnce 應用程式](../deployment/securing-clickonce-applications.md)   
 [ClickOnce 應用程式的程式碼存取安全性](../deployment/code-access-security-for-clickonce-applications.md)   
 [保護 ClickOnce 應用程式](../deployment/securing-clickonce-applications.md)