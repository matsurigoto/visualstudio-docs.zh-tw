---
title: 操作說明：從命令列使用分析工具以檢測獨立的 .NET Framework 元件並收集計時資料 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b7dcc27b-45c6-4302-9552-6fa5b1e94b56
caps.latest.revision: 33
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9d9c7083b46b6f59d28c56724722b2ea591e971b
ms.sourcegitcommit: d705e015cb525bfa87a0b93e93376c3956ec2707
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/29/2018
ms.locfileid: "47588636"
---
# <a name="how-to-instrument-a-stand-alone-net-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line"></a>如何：從命令列使用程式碼剖析工具以檢測獨立的 .NET Framework 元件並收集計時資料
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[如何： 檢測獨立的.NET Framework 元件並收集計時資料，使用 Profiler 從命令列](https://docs.microsoft.com/visualstudio/profiling/how-to-instrument-a-stand-alone-dotnet-framework-component-and-collect-timing-data-with-the-profiler-from-the-command-line)。  
  
本主題描述如何使用 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具命令列工具來檢測 .NET Framework 元件，例如 .exe 或 .dll 檔案，並收集詳細的計時資料。  
  
> [!NOTE]
>  Windows 8 和 Windows Server 2012 增強式安全性功能需要的重大變更，會以 Visual Studio 分析工具在這些平台收集資料的方式表現。 Windows 市集應用程式也需要新的資料收集技術。 請參閱 [Windows 8 和 Windows Server 2012 應用程式的效能工具](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。  
>   
>  程式碼剖析工具的命令列工具位於 [!INCLUDE[vs_current_short](../includes/vs-current-short-md.md)] 安裝目錄的 \Team Tools\Performance Tools 子目錄中。 在 64 位元電腦上，64 位元和 32 位元版本的工具都可以使用。 若要使用程式碼剖析工具命令列工具，必須將工具路徑加入至命令提示字元視窗的 PATH 環境變數，或將它加入至命令本身。 如需詳細資訊，請參閱[指定命令列工具的路徑](../profiling/specifying-the-path-to-profiling-tools-command-line-tools.md)。  
>   
>  若要將階層互動資料加入至程式碼剖析回合中，則需要使用命令列程式碼剖析工具的特定程序。 請參閱[收集階層互動資料](../profiling/adding-tier-interaction-data-from-the-command-line.md)。  
  
 若要使用檢測方法從 .NET Framework 元件收集詳細的計時資料，可以使用 [VSInstr.exe](../profiling/vsinstr.md) 工具來產生已檢測版的元件，並使用 [VSPerfCLREnv.cmd](../profiling/vsperfclrenv.md) 工具來初始化程式碼剖析環境變數。 然後啟動分析工具。  
  
 執行已檢測的元件時，計時資料會自動收集到資料檔案。 程式碼剖析工作階段期間，您可以暫停和繼續資料收集。  
  
 若要結束程式碼剖析工作階段，必須關閉目標應用程式，並明確地關閉程式碼剖析工具。 在大部分情況下，建議您在工作階段結束時清除程式碼剖析環境變數。  
  
## <a name="starting-the-profiling-session"></a>啟動分析工作階段  
  
#### <a name="to-start-profiling-by-using-the-instrumentation-method"></a>使用檢測方法開始分析  
  
1.  開啟 [命令提示字元] 視窗。 如有必要，請將分析工具目錄新增至 PATH 環境變數。 安裝時不會新增路徑。  
  
2.  使用 [VSInstr] 工具產生已檢測版的目標應用程式。  
  
3.  初始化 .NET Framework 程式碼剖析環境變數。 類型：  
  
     **VSPerfClrEnv /traceon**  
  
4.  啟動分析工具。 類型：  
  
     **VSPerfCmd /start:trace /output:** `OutputFile` [`Options`]  
  
    -   [/start](../profiling/start.md)**:trace** 選項會初始化程式碼剖析工具。  
  
    -   [/output](../profiling/output.md)**:**`OutputFile` 選項必須搭配 **/start** 使用。 `OutputFile` 指定程式碼剖析資料 (.vsp) 檔案的名稱和位置。  
  
     您可以使用下列任一選項搭配 **/start:trace** 選項。  
  
    |選項|描述|  
    |------------|-----------------|  
    |[/user](../profiling/user-vsperfcmd.md) **:**[`Domain`**\\**]`UserName`|指定擁有程式碼剖析處理序之帳戶的網域和使用者名稱。 只有在以登入的使用者之外的使用者身分執行處理序時，才需要這個選項。 處理序擁有者會列在 [Windows 工作管理員] 的 [處理程序] 索引標籤上的 [使用者名稱] 欄。|  
    |[/crosssession](../profiling/crosssession.md)|在其他工作階段啟用處理序程式碼剖析。 如果 ASP.NET 應用程式在不同的工作階段中執行，則需要這個選項。 工作階段識別碼會列在 [Windows 工作管理員] 的 [處理程序] 索引標籤上的 [工作階段識別碼] 欄。 **/crosssession** 可縮寫成 **/CS**。|  
    |[/globaloff](../profiling/globalon-and-globaloff.md)|啟動分析工具，但暫停資料收集。 使用 [/globalon](../profiling/globalon-and-globaloff.md) 以繼續程式碼剖析。|  
    |[/counter](../profiling/counter.md) **:** `Config`|從 `Config` 中指定的處理器效能計數器收集資訊。 計數器資訊會新增至在每個程式碼剖析事件收集的資料。|  
    |[/wincounter](../profiling/wincounter.md) **:** `WinCounterPath`|指定程式碼剖析期間要收集的 Windows 效能計數器。|  
    |[/automark](../profiling/automark.md) **:** `Interval`|只能搭配 **/wincounter** 使用。 指定 Windows 效能計數器收集事件間隔的毫秒數。 預設值為 500 毫秒。|  
    |[/events](../profiling/events-vsperfcmd.md) **:** `Config`|指定程式碼剖析期間要收集的 Windows 事件追蹤 (ETW) 事件。 ETW 事件會收集至個別的 (.etl) 檔案。|  
  
5.  從命令提示字元視窗啟動目標應用程式。  
  
## <a name="controlling-data-collection"></a>控制資料收集  
 當目標應用程式執行時，您可以使用 **VSPerfCmd.exe** 選項開始和停止將資料寫入至程式碼剖析資料檔案，以控制資料收集。 控制資料收集可讓您收集特定程式執行 (例如啟動或關閉應用程式) 的資料。  
  
#### <a name="to-start-and-stop-data-collection"></a>開始和停止資料收集  
  
-   下列成對的選項會開始和停止資料收集。 請在個別的命令列上指定各個選項。 您可以多次開始和停止資料收集。  
  
    |選項|描述|  
    |------------|-----------------|  
    |[/globalon /globaloff](../profiling/globalon-and-globaloff.md)|開始 (**/globalon**) 或停止 (**/globaloff**) 所有處理序的資料收集。|  
    |[/processon](../profiling/processon-and-processoff.md) **:** `PID` [/processoff](../profiling/processon-and-processoff.md) **:** `PID`|開始 (**/processon**) 或停止 (**/processoff**) 處理序 ID (`PID`) 指定的處理序資料收集。|  
    |[/threadon](../profiling/threadon-and-threadoff.md) **:** `TID` [/threadoff](../profiling/threadon-and-threadoff.md) **:** `TID`|開始 (**/threadon**) 或停止 (**/threadoff**) 執行緒識別碼 (`TID`) 所指定執行緒的資料收集。|  
  
## <a name="ending-the-profiling-session"></a>結束程式碼剖析工作階段  
 若要結束分析工作階段，請關閉執行已檢測元件的應用程式。 呼叫 **VSPerfCmd** [/shutdown](../profiling/shutdown.md) 選項以關閉分析工具，並關閉分析資料檔案。 **VSPerfClrEnv /off** 命令會清除程式碼剖析環境變數。  
  
#### <a name="to-end-a-profiling-session"></a>結束程式碼剖析工作階段  
  
1.  關閉目標應用程式。  
  
2.  關閉分析工具。 類型：  
  
     **VSPerfCmd /shutdown**  
  
3.  (選擇性) 清除程式碼剖析環境變數。 類型：  
  
     **VSPerfClrEnv /off**  
  
## <a name="see-also"></a>另請參閱  
 [對獨立應用程式進行程式碼剖析](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [檢測方法資料檢視](../profiling/instrumentation-method-data-views.md)



