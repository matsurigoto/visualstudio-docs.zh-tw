---
title: IDebugProperty3::GetCustomViewerList |Microsoft Docs
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
- IDebugProperty3::GetCustomViewerList
helpviewer_keywords:
- IDebugProperty3::GetCustomViewerList
ms.assetid: 74490fd8-6f44-4618-beea-dab64961bb8a
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 490c94ca951fe8a4fb765675920a399569ab24f9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47490828"
---
# <a name="idebugproperty3getcustomviewerlist"></a>IDebugProperty3::GetCustomViewerList
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[IDebugProperty3::GetCustomViewerList](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproperty3-getcustomviewerlist)。  
  
取得與這個屬性相關聯的自訂檢視器的清單。  
  
## <a name="syntax"></a>語法  
  
```cpp  
HRESULT GetCustomViewerList(  
   ULONG                celtSkip,  
   ULONG                celtRequested,  
   DEBUG_CUSTOM_VIEWER* rgViewers,  
   ULONG*               pceltFetched  
);  
```  
  
```csharp  
int GetCustomViewerList(  
   uint                  celtSkip,  
   uint                  celtRequested,  
   DEBUG_CUSTOM_VIEWER[] rgViewers,  
   out uint              pceltFetched  
);  
```  
  
#### <a name="parameters"></a>參數  
 `celtSkip`  
 [in]略過的檢視器的數目。  
  
 `celtRequested`  
 [in]若要擷取的檢視器的數目 (也會指定的大小`rgViewers`陣列)。  
  
 `rgViewers`  
 [in、 out]陣列[DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)来填入結構。  
  
 `pceltFetched`  
 [out]傳回的檢視器的實際數目。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 若要支援類型視覺化檢視，這個方法會呼叫轉送[GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)方法。 如果運算式評估工具也支援自訂檢視器，這個屬性的類型，這個方法可以將適當的自訂檢視器附加至清單。  
  
 請參閱[類型視覺化檢視和自訂檢視器](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)如類型視覺化檢視和自訂檢視器之間的差異的詳細資訊。  
  
## <a name="example"></a>範例  
 下列範例示範如何實作這個方法，如**CProperty**公開 （expose） 的物件[IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)介面。  
  
```cpp#  
STDMETHODIMP CProperty::GetCustomViewerList(ULONG celtSkip, ULONG celtRequested, DEBUG_CUSTOM_VIEWER* prgViewers, ULONG* pceltFetched)  
{  
    if (NULL == prgViewers)  
    {  
        return E_POINTER;  
    }  
  
    if (GetVisualizerService())  
    {  
        return m_pIEEVisualizerService->GetCustomViewerList(celtSkip, celtRequested, prgViewers, pceltFetched);  
    }  
    else  
    {  
        return E_NOTIMPL;  
    }  
}  
```  
  
## <a name="see-also"></a>另請參閱  
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [DEBUG_CUSTOM_VIEWER](../../../extensibility/debugger/reference/debug-custom-viewer.md)   
 [GetCustomViewerList](../../../extensibility/debugger/reference/ieevisualizerservice-getcustomviewerlist.md)   
 [類型視覺化檢視和自訂檢視器](../../../extensibility/debugger/type-visualizer-and-custom-viewer.md)

