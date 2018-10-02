---
title: VSG_NODEFAULT_INSTANCE |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 19c95b0d-9a4d-441f-9ed7-3acb39e67521
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fad6992daf5e8175089ba8f24a4189ad1957ba7c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47486209"
---
# <a name="vsgnodefaultinstance"></a>VSG_NODEFAULT_INSTANCE
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[VSG_NODEFAULT_INSTANCE](https://docs.microsoft.com/visualstudio/debugger/graphics/vsg-nodefault-instance)。  
  
預設執行個體是否定義出現[VsgDbg 類別](../debugger/vsgdbg-class.md)類別，以提供的程式設計擷取介面 — 提供。  
  
## <a name="syntax"></a>語法  
  
```cpp  
#define VSG_NODEFAULT_INSTANCE  
```  
  
## <a name="value"></a>值  
 前置處理器符號會出現，或如果沒有決定的預設執行個體`VsgDbg`類別會提供。 如果已定義這個符號，則沒有預設的執行個體`VsgDbg`類別會提供; 否則預設執行個體是提供，並且初始化您的程式執行之前。  
  
 程式設計擷取介面會提供具有全域範圍內，透過指標`g_pVsgDbg`。  
  
```  
VsgDbg *g_pVsgDbg;  
```  
  
## <a name="remarks"></a>備註  
 預設執行個體通常就已足夠，但該 DLL 外部建立 D3D 裝置後，請使用程式設計擷取介面，於 DLL 內，您必須建立並管理您自己的執行個體`VsgDbg`類別。 如果您要管理您自己的介面，以程式設計擷取 API，如此一來，停用的預設執行個體定義`VSG_NODEFAULT_INSTANCE`以避免額外負荷。  
  
 如果預設執行個體未停用，它會自動初始化您的程式執行之前，即會自動終結，當您的程式結束時。 您不必在初始化或明確解除初始化這個執行個體。  
  
 若要停用的預設執行個體，您必須定義`VSG_NODEFAULT_INSTANCE`您加入之前`vsgcapture.h`在程式中。  
  
## <a name="example"></a>範例  
 此範例示範如何停用的預設執行個體：  
  
```  
// Define VSG_NODEFAULT_INSTANCE before including vsgcapture.h  
#define VSG_NODEFAULT_INSTANCE  
  
#include <vsgcapture.h>  
```


