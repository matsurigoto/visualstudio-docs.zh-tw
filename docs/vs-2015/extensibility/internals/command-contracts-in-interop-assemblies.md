---
title: 命令 Interop 組件中的合約 |Microsoft Docs
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
- command handling with interop assemblies, command contracts
- interop assemblies, command contracts
ms.assetid: 57245708-f539-42dc-8963-2754a48f0189
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8a5e2a7abb298aa43aefbf3f04c048c5928bd555
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47487313"
---
# <a name="command-contracts-in-interop-assemblies"></a>Interop 組件中的命令合約
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[Interop 組件中的命令合約](https://docs.microsoft.com/visualstudio/extensibility/internals/command-contracts-in-interop-assemblies)。  
  
處理命令，透過的基本合約<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>介面是環境呼叫<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>方法以判斷是否支援該命令，如果支援，以判斷其狀態和文字。 接著，環境會呼叫<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>方法來執行命令。  
  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>方法會處理相同的所有命令。 其他的通訊，如有必要 （例如，使用下拉式清單中），由呼叫<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A>搭配適當參數的方法。 這些參數的解譯取決於指定的命令。  
  
 如果在命令目標的輸出參數中傳回值，呼叫端負責一律釋放已配置的任何資源。 這個參數是變數，因為清除 variant 釋放的資源。  
  
 在其中命令必須在階層架構視窗運作的情況下<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>必須使用介面。 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy>介面具有類似的合約，與類似的方法：<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.QueryStatusCommand%2A>和<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierarchy.ExecCommand%2A>。  
  
## <a name="see-also"></a>另請參閱  
 [Vspackage 如何新增使用者介面項目](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [在 Vspackage 中路由傳送命令](../../extensibility/internals/command-routing-in-vspackages.md)   
 [實作](../../extensibility/internals/command-implementation.md)

