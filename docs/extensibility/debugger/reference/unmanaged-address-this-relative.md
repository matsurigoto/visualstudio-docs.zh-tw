---
title: UNMANAGED_ADDRESS_THIS_RELATIVE |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- UNMANAGED_ADDRESS_THIS_RELATIVE
helpviewer_keywords:
- UNMANAGED_ADDRESS_THIS_RELATIVE structure
ms.assetid: e6a91ace-2d47-4ff9-aefb-8d8b68eab0b2
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e0a488c06f009636f7905000529ac7803fb0d6de
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/16/2018
ms.locfileid: "31127079"
---
# <a name="unmanagedaddressthisrelative"></a>UNMANAGED_ADDRESS_THIS_RELATIVE
此結構表示的位址是相對於`this`指標 (`Me`在 Visual Basic 中)。  
  
## <a name="syntax"></a>語法  
  
```cpp  
typedef struct _tagUNMANAGED_THIS_RELATIVE {  
   DWORD dwOffset;  
   DWORD dwBitOffset;  
   DWORD dwBitLength;  
} UNMANAGED_ADDRESS_THIS_RELATIVE;  
```  
  
```csharp  
public struct UNMANAGED_THIS_RELATIVE {  
   public uint dwOffset;  
   public uint dwBitOffset;  
   public uint dwBitLength;  
}  
```  
  
## <a name="terms"></a>詞彙  
 dwOffset  
 自的基底的位置 （例如，開頭類別 vtable） 位移的位元組。  
  
 dwBitOffset  
 在基底的位置的位元位移 (永遠為 0 除非參考是位元欄位)。  
  
 dwBitLength  
 代表地址的位元數 (永遠為 0 除非參考是位元欄位)。  
  
## <a name="remarks"></a>備註  
 這個結構是中的等位的一部分[DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)結構時`dwKind`欄位`DEBUG_ADDRESS_UNION`結構設為`ADDRESS_KIND_UNMANAGED_THIS_RELATIVE`(介於[ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)列舉型別）。  
  
## <a name="requirements"></a>需求  
 標頭： sh.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [結構和等位](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)