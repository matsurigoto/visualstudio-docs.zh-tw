---
title: "IDebugApplication::FIsAutoJitDebugEnabled | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.FIsAutoJitDebugEnabled
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::FIsAutoJitDebugEnabled"
ms.assetid: 0551dd3b-e6eb-442a-8201-418f96fe62df
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::FIsAutoJitDebugEnabled
判斷 Just\-In\-Time \(JIT\) 偵錯工具是否登錄自動偵錯沉默寡言的主機。  
  
## 語法  
  
```  
BOOL FIsAutoJitDebugEnabled();  
```  
  
#### 參數  
 這個方法不採用參數。  
  
## 傳回值  
 如果方法成功，以及一個 JIT 偵錯工具會註冊自動偵錯沉默寡言的主機，則方法會傳回 `TRUE`。  否則，會傳回 `FALSE`。  
  
## 備註  
 這個方法會判斷某個 JIT 偵錯工具是否登錄自動偵錯沉默寡言的主機。  
  
## 請參閱  
 [IDebugApplication 介面](../../winscript/reference/idebugapplication-interface.md)