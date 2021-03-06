---
title: 如何：收集 Windows 事件追蹤 (ETW) 資料 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.performance.property.events
helpviewer_keywords:
- event trace providers, performance tools
- profiling tools, event trace providers
- performance tools, enabling event trace providers
ms.assetid: aa2261fe-d5f5-49fc-a171-d18842e1dc7d
caps.latest.revision: 31
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9f3476a5aa27075f28d9d02f8ca7167cd3f7e64
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47498193"
---
# <a name="how-to-collect-event-tracing-for-windows-etw-data"></a>如何：收集 Windows 事件追蹤 (ETW) 資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[如何： 收集事件追蹤的 Windows (ETW) 資料](https://docs.microsoft.com/visualstudio/profiling/how-to-collect-event-tracing-for-windows-etw-data)。  
  
Windows 事件追蹤 (ETW) 是高效率的核心層級追蹤功能，可讓程式碼剖析工具記錄核心或應用程式定義的事件。 從事件提供者收集的資料，只能透過 /**Summary:ETW** option of the [VSPerfReport](../profiling/vsperfreport.md)命令列工具檢視。 您可使用此報告來判斷應用程式中發生效能問題的癥結。  
  
 **需求**  
  
-   [!INCLUDE[vsUltLong](../includes/vsultlong-md.md)], [!INCLUDE[vsPreLong](../includes/vsprelong-md.md)], [!INCLUDE[vsPro](../includes/vspro-md.md)]  
  
> [!NOTE]
>  Windows 8 和 Windows Server 2012 增強式安全性功能需要的重大變更，會以 Visual Studio 分析工具在這些平台收集資料的方式表現。 Windows 市集應用程式也需要新的資料收集技術。 請參閱 [Windows 8 和 Windows Server 2012 應用程式的效能工具](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。  
  
### <a name="to-enable-event-trace-providers"></a>啟用事件追蹤提供者  
  
1.  在 [效能總管] 中，以滑鼠右鍵按一下效能工作階段，然後按一下 [屬性] 。  
  
2.  在 [屬性頁] 中，按一下 [Windows 事件]  屬性。  
  
3.  在 [選取要從中收集資料的事件追蹤提供者] 清單中，選取要用來對應用程式進行程式碼剖析的事件提供者。  
  
## <a name="see-also"></a>另請參閱  
 [設定效能工作階段](../profiling/configuring-performance-sessions.md)



