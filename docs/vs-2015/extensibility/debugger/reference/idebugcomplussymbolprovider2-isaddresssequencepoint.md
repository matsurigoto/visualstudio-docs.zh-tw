---
title: IDebugComPlusSymbolProvider2::IsAddressSequencePoint |Microsoft Docs
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
- IDebugComPlusSymbolProvider2::IsAddressSequencePoint
- IsAddressSequencePoint
ms.assetid: 89b27c57-5295-428b-8229-a402500d8cd3
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 23b51caa70052a8d535287769924e84d386fa60b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47496766"
---
# <a name="idebugcomplussymbolprovider2isaddresssequencepoint"></a>IDebugComPlusSymbolProvider2::IsAddressSequencePoint
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[IDebugComPlusSymbolProvider2::IsAddressSequencePoint](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugcomplussymbolprovider2-isaddresssequencepoint)。  
  
判斷指定的偵錯位址為序列點。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT IsAddressSequencePoint(  
   IDebugAddress* pAddress  
);  
```  
  
```csharp  
int IsAddressSequencePoint(  
   IDebugAddress pAddress  
);  
```  
  
#### <a name="parameters"></a>參數  
 `pAddress`  
 [in]偵錯所表示的地址[IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md)介面。  
  
## <a name="return-value"></a>傳回值  
 如果偵錯位址都是序列點，會傳回`S_OK`; 否則傳回`S_FALSE`。  
  
## <a name="example"></a>範例  
 下列範例示範如何實作這個方法，如**CDebugSymbolProvider**公開 （expose） 的物件[IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)介面。  
  
```cpp#  
HRESULT CDebugSymbolProvider::IsAddressSequencePoint(  
    IDebugAddress* pAddress  
)  
{  
    HRESULT hr = S_OK;  
    CDEBUG_ADDRESS address;  
    CComPtr<CModule> pModule;  
  
    METHOD_ENTRY( CDebugSymbolProvider::LoadSymbol );  
  
    IfFalseGo( pAddress, E_INVALIDARG );  
  
    IfFailGo( pAddress->GetAddress( &address ) );  
  
    ASSERT(address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD);  
    IfFalseGo( address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD, S_FALSE );  
  
    IfFailGo( GetModule( address.GetModule(), &pModule) );  
  
    if (!pModule->IsSequencePoint( address.addr.addr.addrMethod.tokMethod,  
                                   address.addr.addr.addrMethod.dwVersion,  
                                   address.addr.addr.addrMethod.dwOffset ))  
    {  
  
        // S_FALSE indicates this is not a sequence point  
  
        hr = S_FALSE;  
    }  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::LoadSymbol, hr );  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)
