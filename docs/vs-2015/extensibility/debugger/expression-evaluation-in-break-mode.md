---
title: 在中斷模式中的運算式評估 |Microsoft Docs
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
- break mode, expression evaluation
- debugging [Debugging SDK], expression evaluation
- expression evaluation, break mode
ms.assetid: 34fe5b58-15d5-4387-a266-72120f90a4b6
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: a74119edfb390dab0a8ce0fddd96046ca80ad92d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47500421"
---
# <a name="expression-evaluation-in-break-mode"></a>中斷模式中的運算式評估
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[中斷模式中的運算式評估](https://docs.microsoft.com/visualstudio/extensibility/debugger/expression-evaluation-in-break-mode)。  
  
以下說明發生時偵錯工具處於中斷模式，以及必須進行運算式評估的程序。  
  
## <a name="expression-evaluation-process"></a>運算式評估程序  
 以下是評估運算式所需的基本步驟：  
  
1.  工作階段的偵錯管理員 (SDM) 會呼叫[IDebugStackFrame2::GetExpressionContext](../../extensibility/debugger/reference/idebugstackframe2-getexpressioncontext.md)若要取得運算式內容介面[IDebugExpressionContext2](../../extensibility/debugger/reference/idebugexpressioncontext2.md)。  
  
2.  然後呼叫 SDM [IDebugExpressionContext2::ParseText](../../extensibility/debugger/reference/idebugexpressioncontext2-parsetext.md)要剖析的字串。  
  
3.  如果 ParseText 不會傳回 s_ok 時，會傳回錯誤的原因。  
  
     -否則-  
  
     如果 ParseText 確實傳回 S_OK，SDM 然後呼叫[IDebugExpression2::EvaluateSync](../../extensibility/debugger/reference/idebugexpression2-evaluatesync.md)或是[IDebugExpression2::EvaluateAsync](../../extensibility/debugger/reference/idebugexpression2-evaluateasync.md)從剖析的運算式取得最終的值。  
  
    -   如果是使用`IDebugExpression2::EvaluateSync`，指定的回呼介面用來通訊的評估進行中的程序。 最終的值都會傳入[IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)介面。  
  
    -   如果是使用`IDebugExpression2::EvaluateAsync`，指定的回呼介面用來通訊的評估進行中的程序。 評估完成之後，會將傳送 EvaluateAsync [IDebugExpressionEvaluationCompleteEvent2](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2.md)透過回呼介面。 與此事件介面中，最終的值可以透過取得[GetResult](../../extensibility/debugger/reference/idebugexpressionevaluationcompleteevent2-getresult.md)。  
  
## <a name="see-also"></a>另請參閱  
 [呼叫偵錯工具事件](../../extensibility/debugger/calling-debugger-events.md)

