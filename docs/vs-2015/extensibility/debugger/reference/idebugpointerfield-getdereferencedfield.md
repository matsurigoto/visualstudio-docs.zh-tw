---
title: IDebugPointerField::GetDereferencedField |Microsoft Docs
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
- IDebugPointerField::GetDereferencedField
helpviewer_keywords:
- IDebugPointerField::GetDereferencedField method
ms.assetid: 8de988ab-cd79-4287-be72-3c900f2fe407
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 730f869613341b3733bff47a3bdcb066e987f9a5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47486955"
---
# <a name="idebugpointerfieldgetdereferencedfield"></a>IDebugPointerField::GetDereferencedField
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[IDebugPointerField::GetDereferencedField](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugpointerfield-getdereferencedfield)。  
  
這個方法會傳回這個指標物件所指向的物件型別。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT GetDereferencedField(  
   IDebugField** ppField  
);  
```  
  
```csharp  
int GetDereferencedField(  
   out IDebugField ppField  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ppField`  
 [out]傳回[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)描述的目標物件類型。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 例如，如果[IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)物件會指向整數[IDebugField](../../../extensibility/debugger/reference/idebugfield.md)這個方法所傳回的型別描述該整數類型。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)

