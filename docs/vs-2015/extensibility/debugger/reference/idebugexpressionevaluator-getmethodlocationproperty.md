---
title: IDebugExpressionEvaluator::GetMethodLocationProperty |Microsoft Docs
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
- IDebugExpressionEvaluator::GetMethodLocationProperty
helpviewer_keywords:
- IDebugExpressionEvaluator::GetMethodLocationProperty method
ms.assetid: 52c42a2e-f144-476b-8bef-442464c8fe8e
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a11013ba2450685798796d0645486cf178950fc1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47500364"
---
# <a name="idebugexpressionevaluatorgetmethodlocationproperty"></a>IDebugExpressionEvaluator::GetMethodLocationProperty
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[IDebugExpressionEvaluator::GetMethodLocationProperty](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugexpressionevaluator-getmethodlocationproperty)。  
  
這個方法會將方法的位置和位移轉換成記憶體位址。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT GetMethodLocationProperty(   
   LPCOLESTR             upstrFullyQualifiedMethodPlusOffset,  
   IDebugSymbolProvider* pSymbolProvider,  
   IDebugAddress*        pAddress,  
   IDebugBinder*         pBinder,  
   IDebugProperty2**     ppProperty  
);  
```  
  
```csharp  
int GetMethodLocationProperty(  
   string               upstrFullyQualifiedMethodPlusOffset,   
   IDebugSymbolProvider pSymbolProvider,   
   IDebugAddress        pAddress,   
   IDebugBinder         pBinder,   
   out IDebugProperty2  ppProperty  
);  
```  
  
#### <a name="parameters"></a>參數  
 `upstrFullyQualifiedMethodPlusOffset`  
 [in]方法的位置和位移、 以字串表示。  
  
 `pSymbolProvider`  
 [in]符號提供者以表示[IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)物件。  
  
 `pAddress`  
 [in]在方法中，以表示地址[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)物件。  
  
 `pBinder`  
 [in]繫結器表示為[IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)物件。  
  
 `ppProperty`  
 [out]傳回[IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)代表的記憶體位址的介面。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 傳回的位址可用來設定中斷點，例如使用中。  
  
 儘管有此名稱`upstrFullyQualifiedMethodPlusOffset`，這個參數可以傳遞完整的方法名稱。 在此情況下，選取的方法是包圍`pAddress`。 此參數的解譯方式，是由運算式評估工具及它所支援的語言實作。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugSymbolProvider](../../../extensibility/debugger/reference/idebugsymbolprovider.md)   
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [IDebugExpressionEvaluator](../../../extensibility/debugger/reference/idebugexpressionevaluator.md)

