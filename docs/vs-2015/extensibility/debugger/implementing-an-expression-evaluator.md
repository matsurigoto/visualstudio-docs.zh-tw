---
title: 實作運算式評估工具 |Microsoft Docs
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
- expression evaluators
- debugging [Debugging SDK], expression evaluators
ms.assetid: e9ada7be-845e-4baa-bf8f-e4890e7ba490
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d80688af9c574c522a1151c700d2ab117f4206d8
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47484966"
---
# <a name="implementing-an-expression-evaluator"></a>實作運算式評估工具
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[實作運算式評估工具](https://docs.microsoft.com/visualstudio/extensibility/debugger/implementing-an-expression-evaluator)。  
  
> [!IMPORTANT]
>  在 Visual Studio 2015 中，這種實作運算式評估工具已被取代。 如需實作 CLR 運算式評估工具的資訊，請參閱[CLR 運算式評估工具](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators)並[Managed 運算式評估工具範例](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample)。  
  
 評估運算式時錯綜複雜的偵錯引擎 (DE)、 符號提供者 (SP)、 繫結器物件與運算式評估工具 (EE) 本身之間。 這四個元件會透過介面會實作一個元件，並由另一個連接。  
  
 EE 會使用運算式從字串的形式在德國和剖析或加以評估。 EE 會實作下列介面，以供 DE:  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
 EE 呼叫繫結器提供的物件，由 DE，以取得此值的符號和物件。 EE 會取用 DE 所實作的下列介面：  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
-   [IDebugArrayObject](../../extensibility/debugger/reference/idebugarrayobject.md)  
  
-   [IDebugFunctionObject](../../extensibility/debugger/reference/idebugfunctionobject.md)  
  
-   [IDebugPointerObject](../../extensibility/debugger/reference/idebugpointerobject.md)  
  
-   [IDebugManagedObject](../../extensibility/debugger/reference/idebugmanagedobject.md)  
  
-   [IEnumDebugObjects](../../extensibility/debugger/reference/ienumdebugobjects.md)  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
 實作 EE [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)。 `IDebugProperty2` 提供機制，來描述運算式評估，例如本機變數、 基本類型或物件，則會顯示在適當的資訊中的 Visual studio 的結果**區域變數**， **監看式**，或**即時運算**視窗。  
  
 預存程序會提供給 EE DE 時它會要求資訊。 預存程序會實作介面描述位址和欄位，例如下列介面和其衍生項目：  
  
-   [IDebugSymbolProvider](../../extensibility/debugger/reference/idebugsymbolprovider.md)  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
 EE 會消耗所有的這些介面。  
  
## <a name="in-this-section"></a>本節內容  
 [運算式評估工具的實作策略](../../extensibility/debugger/expression-evaluator-implementation-strategy.md)  
 定義運算式評估工具 (EE) 的實作策略的三步驟程序。  
  
## <a name="see-also"></a>另請參閱  
 [撰寫 CLR 運算式評估工具](../../extensibility/debugger/writing-a-common-language-runtime-expression-evaluator.md)

