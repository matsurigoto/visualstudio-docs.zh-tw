---
title: IDebugPortSupplier2::CanAddPort |Microsoft Docs
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
- IDebugPortSupplier2::CanAddPort
helpviewer_keywords:
- IDebugPortSupplier2::CanAddPort
ms.assetid: 41f69e0a-e82c-473d-8b7a-0c40fc5730fc
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1478841e6fdd48a6c956486153db7bf4e81435fa
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484997"
---
# <a name="idebugportsupplier2canaddport"></a>IDebugPortSupplier2::CanAddPort
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[IDebugPortSupplier2::CanAddPort](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportsupplier2-canaddport)。  
  
確認連接埠提供者可以新增新的連接埠。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT CanAddPort(   
   void   
);  
```  
  
```csharp  
int CanAddPort();  
```  
  
## <a name="return-value"></a>傳回值  
 如果可以加入連接埠，會傳回`S_OK`; 否則傳回`S_FALSE`，表示沒有連接埠可以新增到此連接埠提供者。  
  
## <a name="remarks"></a>備註  
 呼叫這個方法，然後再呼叫[下列](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)方法，因為第二個方法會建立連接埠，以及加入它，這可能耗時的作業。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [AddPort](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md)

