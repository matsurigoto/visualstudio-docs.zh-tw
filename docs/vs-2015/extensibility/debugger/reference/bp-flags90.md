---
title: BP_FLAGS90 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BP_FLAGS90 enumeration
ms.assetid: 3e5a06c5-fb30-4b8a-b2d5-4a0570fc80bd
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c983356d3a808d523ddd8a5cb87912f0a2638d7f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47497543"
---
# <a name="bpflags90"></a>BP_FLAGS90
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[BP_FLAGS90](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-flags90)。  
  
列舉有效的值，選擇性旗標。 選擇性旗標可用來指定其他資訊，當您設定中斷點。 這個列舉型別會擴充[BP_FLAGS](../../../extensibility/debugger/reference/bp-flags.md)列舉型別。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE               = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION    = 0x0001,  
   BP90_FLAG_DONT_STOP          = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
typedef DWORD BP_FLAGS90;  
```  
  
```csharp  
public enum enum_BP_FLAGS90  
{  
   // VS 8.0 values  
   BP90_FLAG_NONE                = 0x0000,  
   BP90_FLAG_MAP_DOCPOSITION     = 0x0001,  
   BP90_FLAG_DONT_STOP           = 0x0002,  
  
   // Values added in VS 9.0  
   BP90_FLAG_TRACEPOINT_CONTINUE = 0x0004,  
};  
```  
  
#### <a name="parameters"></a>參數  
 BP90_FLAG_NONE  
 不指定任何中斷點旗標。  
  
 BP90_FLAG_MAP_DOCPOSITION  
 指定偵錯引擎 (DE) 應該使用的文件位置來對應中斷點。 這是僅適用於指令碼導向的原始程式檔等動態伺服器網頁 (ASP) 中設定中斷點。  
  
 BP90_FLAG_DONT_STOP  
 指定偵錯引擎中，應該處理中斷點，但，偵錯引擎最終應該不只如此;亦即[IDebugBreakpointEvent2](../../../extensibility/debugger/reference/idebugbreakpointevent2.md)應該不會傳送事件的物件。 這個旗標被設計用於主要與追蹤點。  
  
 BP90_FLAG_TRACEPOINT_CONTINUE  
 使用原生偵錯引擎來判斷是否應該清除逐步執行的狀態。 它會有所不同 BP90_FLAG_DONT_STOP，因為如果在追蹤點執行巨集 BP90_FLAG_DONT_STOP 未設定。  
  
## <a name="requirements"></a>需求  
 標頭： Msdbg90.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [列舉](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)

