---
title: "遇到中斷點 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "偵錯 [偵錯 SDK]，請叫用中斷點"
  - "點擊的中斷點"
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 遇到中斷點
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

以下說明時，偵錯引擎 \(DE\) 叫用中斷點時執行或逐步執行的處理程序：  
  
## 疑難排解叫用中斷點  
  
1.  DE 傳送 [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 介面做為 **EVENT\_SYNC\_STOP**。  
  
2.  工作階段偵錯管理員 \(SDM\) 會呼叫 [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) 以取得已叫用中斷點。  
  
## 請參閱  
 [呼叫偵錯工具事件](../../extensibility/debugger/calling-debugger-events.md)