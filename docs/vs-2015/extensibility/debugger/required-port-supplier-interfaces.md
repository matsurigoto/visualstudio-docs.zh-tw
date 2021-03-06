---
title: 所需的連接埠供應商介面 |Microsoft Docs
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
- port suppliers, required interfaces
- debugging [Debugging SDK], port suppliers
ms.assetid: 0c2cdd40-9f6f-425e-b305-858f7734161e
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 960cd5668fe49ba50e79f036848948ec8e0bbfc2
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47488436"
---
# <a name="required-port-supplier-interfaces"></a>必要的連接埠提供者介面
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[需要的連接埠供應商介面](https://docs.microsoft.com/visualstudio/extensibility/debugger/required-port-supplier-interfaces)。  
  
連接埠提供者必須實作[IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)介面。[IDebugPortSupplier2](../../extensibility/debugger/reference/idebugportsupplier2.md)  
  
 由於連接埠提供者會提供連接埠，它也必須實作它們。 因此，它必須實作下列介面：  
  
-   [IDebugPort2](../../extensibility/debugger/reference/idebugport2.md)  
  
     描述該連接埠，並可以列舉所有的連接埠上執行的處理程序。  
  
-   [IDebugPortEx2](../../extensibility/debugger/reference/idebugportex2.md)  
  
     提供啟動和終止的連接埠上的處理序。  
  
-   [IDebugPortNotify2](../../extensibility/debugger/reference/idebugportnotify2.md)  
  
     提供一個機制，以通知它程式節點的建立和解構的這個連接埠的內容中執行的程式。 如需詳細資訊，請參閱 <<c0> [ 計劃節點](../../extensibility/debugger/program-nodes.md)。  
  
-   `IConnectionPointContainer`  
  
     提供的連接點[IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md)。  
  
## <a name="port-supplier-operation"></a>連接埠供應商的作業  
 [IDebugPortEvents2](../../extensibility/debugger/reference/idebugportevents2.md)接收會收到通知時處理序，然後建立並終結的連接埠上的程式。 連接埠，才能傳送[IDebugProcessCreateEvent2](../../extensibility/debugger/reference/idebugprocesscreateevent2.md)處理程序建立時並[IDebugProcessDestroyEvent2](../../extensibility/debugger/reference/idebugprocessdestroyevent2.md)處理程序時終結的連接埠。 連接埠也需要傳送[IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md)程式建立時並[IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)程式中的連接埠上執行的程序時損毀。  
  
 連接埠通常會傳送程式建立和終結事件以回應[AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md)並[RemoveProgramNode](../../extensibility/debugger/reference/idebugportnotify2-removeprogramnode.md)方法，分別。  
  
 因為連接埠可以啟動和終止處理序實體和邏輯的程式，也必須實作這些介面的偵錯引擎：  
  
-   [IDebugProcess2](../../extensibility/debugger/reference/idebugprocess2.md)  
  
     描述實體的程序。 至少必須實作下列方法：  
  
    -   [EnumPrograms](../../extensibility/debugger/reference/idebugprocess2-enumprograms.md)  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprocess2-getname.md)  
  
    -   [GetServer](../../extensibility/debugger/reference/idebugprocess2-getserver.md)  
  
    -   [GetPhysicalProcessId](../../extensibility/debugger/reference/idebugprocess2-getphysicalprocessid.md)  
  
    -   [GetProcessId](../../extensibility/debugger/reference/idebugprocess2-getprocessid.md)  
  
    -   [GetAttachedSessionName](../../extensibility/debugger/reference/idebugprocess2-getattachedsessionname.md)  
  
-   [IDebugProcessEx2](../../extensibility/debugger/reference/idebugprocessex2.md)  
  
     提供了 SDM attach 和 detach 本身的處理程序的方式。  
  
-   [IDebugProgram2](../../extensibility/debugger/reference/idebugprogram2.md)  
  
     描述邏輯的程式。 至少必須實作下列方法：  
  
    -   [GetName](../../extensibility/debugger/reference/idebugprogram2-getname.md)  
  
    -   [GetProcess](../../extensibility/debugger/reference/idebugprogram2-getprocess.md)  
  
    -   [GetProgramId](../../extensibility/debugger/reference/idebugprogram2-getprogramid.md)  
  
-   [IDebugProgramEx2](../../extensibility/debugger/reference/idebugprogramex2.md)  
  
     提供了 SDM 附加至這個程式的方式。  
  
## <a name="see-also"></a>另請參閱  
 [實作連接埠提供者](../../extensibility/debugger/implementing-a-port-supplier.md)

