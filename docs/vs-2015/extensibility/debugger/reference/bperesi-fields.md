---
title: BPERESI_FIELDS |Microsoft Docs
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
- BPERESI_FIELDS
helpviewer_keywords:
- BPERESI_FIELDS enumeration
ms.assetid: dd7dd89c-1043-46a1-a929-099cc039c344
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8207271404811f3da3dd03782974abd9e67fb576
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47486837"
---
# <a name="bperesifields"></a>BPERESI_FIELDS
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[BPERESI_FIELDS](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bperesi-fields)。  
  
指定要擷取失敗的解決方式的中斷點相關的資訊。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
typedef DWORD BPERESI_FIELDS;  
```  
  
```csharp  
public enum enum_BPERESI_FIELDS {   
   PERESI_BPRESLOCATION = 0x0001,  
   BPERESI_PROGRAM      = 0x0002,  
   BPERESI_THREAD       = 0x0004,  
   BPERESI_MESSAGE      = 0x0008,  
   BPERESI_TYPE         = 0x0010,  
   BPERESI_ALLFIELDS    = 0xffffffff  
};  
```  
  
## <a name="members"></a>成員  
 PERESI_BPRESLOCATION  
 初始化/使用`bpResLocation`（中斷點解析位置） 欄位[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)結構。  
  
 BPERESI_PROGRAM  
 初始化/使用`pProgram`欄位`BP_ERROR_RESOLUTION_INFO`結構。  
  
 BPERESI_THREAD  
 初始化/使用`pThread`欄位`BP_ERROR_RESOLUTION_INFO`結構。  
  
 BPERESI_MESSAGE  
 初始化/使用`bstrMessage`欄位`BP_ERROR_RESOLUTION_INFO`結構。  
  
 BPERESI_TYPE  
 初始化/使用`dwType`（中斷點型別） 欄位`BP_ERROR_RESOLUTION_INFO`結構。  
  
 BPERESI_ALLFIELDS  
 初始化/使用的所有欄位`BP_ERROR_RESOLUTION_INFO`結構。  
  
## <a name="remarks"></a>備註  
 做為參數傳遞[GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)方法，以表示哪些欄位[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)結構會進行初始化。  
  
 這些值也可用來指示中的哪些欄位`BP_ERROR_RESOLUTION_INFO`結構會使用和有效時傳回該結構。  
  
 這些值可能會合併的位元`OR`。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [列舉型別](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [GetResolutionInfo](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2-getresolutioninfo.md)

