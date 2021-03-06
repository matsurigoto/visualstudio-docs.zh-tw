---
title: BP_RESOLUTION_LOCATION |Microsoft Docs
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
- BP_RESOLUTION_LOCATION
helpviewer_keywords:
- BP_RESOLUTION_LOCATION structure
ms.assetid: 21dc5246-69c1-43e3-855c-9cd4e596c0e6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: af73894f85d60d5aaa99de6958168f3c09a68d45
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47487056"
---
# <a name="bpresolutionlocation"></a>BP_RESOLUTION_LOCATION
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[BP_RESOLUTION_LOCATION](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/bp-resolution-location)。  
  
指定的中斷點解析位置的結構。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
struct _BP_RESOLUTION_LOCATION {  
   BP_TYPE bpType;  
   union {  
      BP_RESOLUTION_CODE bpresCode;  
      BP_RESOLUTION_DATA bpresData;  
      int                unused;  
   } bpResLocation;  
} BP_RESOLUTION_LOCATION;  
```  
  
```csharp  
public struct BP_RESOLUTION_LOCATION {  
   public uint bpType;  
   public IntPtr unionmember1;  
   public IntPtr unionmember2;  
   public IntPtr unionmember3;  
   public uint   unionmember4;  
};  
```  
  
## <a name="members"></a>成員  
 `bpType`  
 值，以從[BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)列舉，指定如何解譯`bpResLocation`聯集或`unionmemberX`成員。  
  
 `bpResLocation.bpresCode`  
 [只有 c + +]包含[BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md)結構，如果`bpType`  =  `BPT_CODE`。  
  
 `bpResLocation.bpresData`  
 [只有 c + +]包含[BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)結構，如果`bpType`  =  `BPT_DATA`。  
  
 `bpResLocation.unused`  
 [只有 c + +]預留位置。  
  
 `unionmember1`  
 [僅限 C#]請參閱有關如何解譯的備註。  
  
 `unionmember2`  
 [僅限 C#]請參閱有關如何解譯的備註。  
  
 `unionmember3`  
 [僅限 C#]請參閱有關如何解譯的備註。  
  
 `unionmember4`  
 [僅限 C#]請參閱有關如何解譯的備註。  
  
## <a name="remarks"></a>備註  
 此結構是隸屬[BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)並[BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)結構。  
  
 [僅限 C#]`unionmemberX`成員會根據下表來解譯。 往下的左側資料行`bpType`來判斷每個值然後跨`unionmemberX`成員表示和封送處理`unionmemberX`據此。 請參閱的方式來解譯此結構在 C# 中的範例。  
  
|`bpLocationType`|`unionmember1`|`unionmember2`|`unionmember3`|`unionmember4`|  
|----------------------|--------------------|--------------------|--------------------|--------------------|  
|`BPT_CODE`|[IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)|-|-|-|  
|`BPT_DATA`|`string` （資料運算式）|`string` （函式名稱）|`string` （映像名稱）|`enum_BP_RES_DATA_FLAGS`|  
  
## <a name="example"></a>範例  
 此範例示範如何解譯`BP_RESOLUTION_LOCATION`C# 中的結構。  
  
```csharp  
using System;  
using System.Runtime.Interop.Services;  
using Microsoft.VisualStudio.Debugger.Interop;  
  
namespace MyPackage  
{  
    public class MyClass  
    {  
        public void Interpret(BP_RESOLUTION_LOCATION bprl)  
        {  
            if (bprl.bpType == (uint)enum_BP_TYPE.BPT_CODE)  
            {  
                 IDebugCodeContext2 pContext = (IDebugCodeContext2)Marshal.GetObjectForIUnknown(bp.unionmember1);  
            }  
            else if (bprl.bpType == (uint)enum_BP_TYPE.BPT_DATA)  
            {  
                 string dataExpression = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 string functionName = Marshal.PtrToStringBSTR(bp.unionmember2);  
                 string imageName = Marshal.PtrToStringBSTR(bp.unionmember3);  
                 enum_BP_RES_DATA_FLAGS numElements = (enum_BP_RES_DATA_FLAGS)bp.unionmember4;  
            }  
        }  
    }  
}  
```  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [結構和等位](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [BP_TYPE](../../../extensibility/debugger/reference/bp-type.md)   
 [BP_ERROR_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-error-resolution-info.md)   
 [BP_RESOLUTION_INFO](../../../extensibility/debugger/reference/bp-resolution-info.md)   
 [BP_RESOLUTION_CODE](../../../extensibility/debugger/reference/bp-resolution-code.md)   
 [BP_RESOLUTION_DATA](../../../extensibility/debugger/reference/bp-resolution-data.md)   
 [BP_RES_DATA_FLAGS](../../../extensibility/debugger/reference/bp-res-data-flags.md)

