---
title: BP_LOCATION_DATA_STRING |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- BP_LOCATION_DATA_STRING
helpviewer_keywords:
- BP_LOCATION_DATA_STRING structure
ms.assetid: 445d6f3f-95b0-47ac-85e2-51b778240687
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: c53fa0f14cbea9dc65fbc1f8c99680785066379a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47499101"
---
# <a name="bplocationdatastring"></a>BP_LOCATION_DATA_STRING
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[BP_LOCATION_DATA_STRING](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-location-data-string)。  
  
用於設定資料中斷點的使用者可以輸入從整合式的開發環境 (IDE) 的字串為基礎。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
typedef struct _BP_LOCATION_DATA_STRING {   
   IDebugThread2* pThread;  
   BSTR           bstrContext;  
   BSTR           bstrDataExpr;  
   DWORD          dwNumElements;  
} BP_LOCATION_DATA_STRING;  
```  
  
## <a name="members"></a>成員  
 `pThread`  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)物件，表示中斷點發生的執行緒。  
  
 `bstrContext`  
 程式碼內的中斷點，通常是方法或函式的名稱為 呼叫堆疊上看到的內容。  
  
 `bstrDataExpr`  
 資料字串，使用者會進入設定中斷點。  
  
 `dwNumElements`  
 中斷點會發生的資料字串中的項目數目。  
  
## <a name="remarks"></a>備註  
 此結構是隸屬[BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)結構的聯集的一部分。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [結構和等位](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_LOCATION](../../../extensibility/debugger/reference/bp-location.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)

