---
title: "獨立應用程式的命令列分析 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- profillng tools,stand-alone applications
- profling stand-alone applications
ms.assetid: a47f2bf2-186d-4120-bb79-34e2f3a1ee42
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 212631838fa6c396fc6f1a5af5164538a156bcd0
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2017
---
# <a name="command-line-profiling-of-stand-alone-applications"></a>獨立應用程式的命令列分析
本節說明從命令列使用 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 分析工具收集獨立 (用戶端) 應用程式之效能資料的程序和選項。  
  
## <a name="common-tasks"></a>一般工作  
  
|工作|相關內容|  
|----------|---------------------|  
|**收集應用程式統計資料：**使用取樣方法收集效能統計資料。 取樣資料可用來分析 CPU 使用率的問題，以及了解應用程式的一般效能特性。|-   [使用取樣收集應用程式統計資料](../profiling/collecting-application-statistics-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**收集詳細計時資料：**使用檢測方法收集詳細的計時資訊。 檢測資料可用來分析 I/O 問題，並且適用於更細緻的應用程式案例分析。|-   [使用檢測收集詳細計時資料](../profiling/collecting-detailed-timing-data-for-a-stand-alone-application-by-using-the-profiler-command-line.md)|  
|**收集 .NET 記憶體資料︰**使用取樣或檢測收集 .NET 記憶體配置資料，顯示配置物件的大小和數目。 您也可以收集物件存留期資料，顯示每個記憶體回收層代中回收的物件大小和數目。|-   [收集 .NET Framework 記憶體資料](../profiling/collecting-dotnet-framework-memory-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**收集並行資料：**使用並行方法收集資源爭用資料和執行緒活動資料，顯示 CPU 使用率、執行緒爭用、執行緒移轉、同步處理延遲、重疊 I/O 區域 和其他系統事件。|-   [收集並行資料](../profiling/collecting-concurrency-data-for-stand-alone-applications-by-using-the-profiler-command-line.md)|  
|**加入階層互動資料︰**您可以新增應用程式對 Microsoft [!INCLUDE[ssNoVersion](../data-tools/includes/ssnoversion_md.md)] 資料庫之同步 ADO.NET 呼叫的相關效能資料。 若要將階層互動資料加入至程式碼剖析回合中，則需要使用命令列程式碼剖析工具的特定程序。|-   [收集階層互動資料](../profiling/adding-tier-interaction-data-from-the-command-line.md)|  
|**試試看︰**使用逐步程序利用取樣或檢測方法來分析範例用戶端應用程式。|-   [逐步解說：使用取樣進行命令列分析](../profiling/walkthrough-command-line-profiling-using-sampling.md)<br />-   [逐步解說：使用檢測進行命令列分析](../profiling/walkthrough-command-line-profiling-using-instrumentation.md)|  
  
## <a name="related-tasks"></a>相關工作  
  
|工作|相關內容|  
|----------|---------------------|  
|**分析 ASP.NET 應用程式**|-   [分析 ASP.NET Web 應用程式](../profiling/command-line-profiling-of-aspnet-web-applications.md)|  
|**分析服務**|-   [分析服務](../profiling/command-line-profiling-of-services.md)|