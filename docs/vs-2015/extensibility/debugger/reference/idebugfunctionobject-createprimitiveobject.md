---
title: IDebugFunctionObject::CreatePrimitiveObject |Microsoft Docs
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
- IDebugFunctionObject::CreatePrimitiveObject
helpviewer_keywords:
- IDebugFunctionObject::CreatePrimitiveObject method
ms.assetid: 6e9dc8b6-b4e1-4abf-b6e0-e885910775bc
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 320930a86a58b51155b3f7400ea791135c321d95
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47498445"
---
# <a name="idebugfunctionobjectcreateprimitiveobject"></a>IDebugFunctionObject::CreatePrimitiveObject
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[IDebugFunctionObject::CreatePrimitiveObject](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugfunctionobject-createprimitiveobject)。  
  
建立基本資料物件，例如簡單的整數。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT CreatePrimitiveObject(   
   OBJECT_TYPE    ot,  
   IDebugObject** ppObject  
);  
```  
  
```csharp  
int CreatePrimitiveObject(  
   enum_OBJECT_TYPE ot,   
   out IDebugObject ppObject  
);  
```  
  
#### <a name="parameters"></a>參數  
 `ot`  
 [in]值，以從[OBJECT_TYPE](../../../extensibility/debugger/reference/object-type.md)列舉型別表示來建立基本的型別。  
  
 `ppObject`  
 [out]傳回[IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)代表新建立的物件。  
  
## <a name="return-value"></a>傳回值  
 如果成功，會傳回 S_OK;否則，傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 呼叫這個方法來建立物件，表示基本物件所表示的函式的參數[IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)介面。 例如，如果 「 myString(5)"的運算式字串，這個方法可用來建立物件，代表整數 5。  
  
## <a name="see-also"></a>另請參閱  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)

