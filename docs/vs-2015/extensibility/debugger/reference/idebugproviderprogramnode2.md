---
title: IDebugProviderProgramNode2 |Microsoft Docs
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
- IDebugProviderProgramNode2
helpviewer_keywords:
- IDebugProviderProgramNode2
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b4b180ad9ceb0ccb44a04f4f06af3541d2244822
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47488448"
---
# <a name="idebugproviderprogramnode2"></a>IDebugProviderProgramNode2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[IDebugProviderProgramNode2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugproviderprogramnode2)。  
  
此介面中，封送處理程式相關的介面跨處理序界限。  
  
## <a name="syntax"></a>語法  
  
```  
IDebugProviderProgramNode2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>實作者的附註  
 偵錯引擎 (DE) 實作的相同物件上實作這個介面[IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)以支援跨處理序界限的封送處理的介面。  
  
## <a name="notes-for-callers"></a>呼叫端資訊  
 呼叫[QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3)上`IDebugProgramNode2`介面，以取得此介面。 如果無法取得此介面，DE 不支援封送處理的介面。  
  
## <a name="methods-in-vtable-order"></a>依照 Vtable 順序的方法  
 這個介面會實作下列方法：  
  
|方法|描述|  
|------------|-----------------|  
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|取得指定的介面，跨處理序界限。|  
  
## <a name="remarks"></a>備註  
 DE 執行不同的處理序空間中，從正在偵錯程式時，會實作這個介面： 例如，當 DE 執行 Visual Studio 處理序空間，而不是正在偵錯之程式的處理序空間中。  
  
## <a name="requirements"></a>需求  
 標頭： msdbg.h  
  
 命名空間： Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>另請參閱  
 [核心介面](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)

