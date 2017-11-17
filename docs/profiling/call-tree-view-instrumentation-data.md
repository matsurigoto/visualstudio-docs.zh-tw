---
title: "呼叫樹狀圖檢視 - 檢測資料 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Call Tree view
ms.assetid: 306bd176-0ce9-4a10-89ca-20b043d37d4e
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97cf11522b921ce9ebf1bfb26b40f2cd5a96d55e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2017
---
# <a name="call-tree-view---instrumentation-data"></a>呼叫樹狀圖檢視 - 檢測資料
呼叫樹狀圖中的函式值，表示呼叫樹狀圖中父函式呼叫函式執行個體的時間。 百分比值的計算方式是比較在分析執行中函式執行個體的值與所有函式的總功能內含耗用 (Elapsed Inclusive) 時間。  
  
## <a name="general"></a>一般  
 一般資料行會識別檢視列中的函式。  
  
|Column|說明|  
|------------|-----------------|  
|**函式名稱**|函式的名稱。|  
|**函式位址**|函式的位址。|  
|**函式行號**|原始程式檔中這個函式的開頭行號。|  
|**呼叫次數**|呼叫此函式的總次數。|  
|**原始程式檔**|含有這個函式定義的原始程式檔。|  
|**模組名稱**|包含該函式的模組名稱。|  
|**模組路徑**|包含該函式的模組路徑。|  
|**處理序 ID**|分析執行的處理序 ID (PID)。|  
|**處理序名稱**|指派給處理序的名稱。|  
|**時間專有探查額外負荷**|檢測對這個函式造成的時間額外負荷。 已經從所有專有時間減去探查額外負荷。|  
|**時間內含探查額外負荷**|檢測對這個函式及其子函式所造成的時間額外負荷。 已經從所有內含時間減去探查額外負荷。|  
|**層級**|函式在呼叫樹狀圖中的深度。 只在[VSPerfReport](../profiling/vsperfreport.md) 命令列的報表中。|  
  
## <a name="elapsed-inclusive-values"></a>功能內含耗用值  
 功能內含耗用值表示呼叫樹狀圖中父函式所呼叫之函式執行個體在呼叫堆疊上的時間。 該時間包含函式呼叫子函式以及呼叫作業系統所花費的時間，例如內容切換和輸入/輸出作業。  
  
|Column|說明|  
|------------|-----------------|  
|**功能內含耗用 (Elapsed Inclusive) 時間**|在此內容中這個函式所有呼叫的總功能內含耗用 (Elapsed Inclusive) 時間。|  
|**功能內含耗用 (Elapsed Inclusive) 時間 %**|在分析執行的總功能內含耗用時間中，花費在此內容中此函式之總功能內含耗用時間的百分比。|  
|**平均功能內含耗用 (Elapsed Inclusive) 時間**|在此內容中呼叫此函式的平均功能內含耗用 (Elapsed Inclusive) 時間。|  
|**最大功能內含耗用 (Elapsed Inclusive) 時間**|在此內容中呼叫此函式的最大功能內含耗用 (Elapsed Inclusive) 時間。|  
|**最小功能內含耗用 (Elapsed Inclusive) 時間**|在此內容中呼叫此函式的最小功能內含耗用 (Elapsed Inclusive) 時間。|  
  
## <a name="elapsed-exclusive-values"></a>功能專屬耗用值  
 功能專屬耗用值表示呼叫樹狀圖中父函式所呼叫之函式執行個體在函式主體中執行程式碼的時間，也就是當函式位於呼叫堆疊的頂端時。 該時間包含呼叫作業系統所花費的時間，例如內容切換和輸入/輸出作業。 不過，該時間不包括函式呼叫子函式所花費的時間。  
  
|Column|描述|  
|------------|-----------------|  
|**功能專屬耗用 (Elapsed Exclusive) 時間**|在此內容中這個函式所有呼叫的總功能專屬耗用 (Elapsed Exclusive) 時間。|  
|**功能專屬耗用 (Elapsed Exclusive) 時間 %**|在分析執行的總功能專屬耗用時間中，花費在此內容中此函式之總功能專屬耗用時間的百分比。|  
|**平均功能專屬耗用 (Elapsed Exclusive) 時間**|在此內容中呼叫此函式的平均功能專屬耗用 (Elapsed Exclusive) 時間。|  
|**最大功能專屬耗用 (Elapsed Exclusive) 時間**|在此內容中呼叫此函式的最大功能專屬耗用 (Elapsed Exclusive) 時間。|  
|**最小功能專屬耗用 (Elapsed Exclusive) 時間**|在此內容中呼叫此函式的最小功能專屬耗用 (Elapsed Exclusive) 時間。|  
  
## <a name="application-inclusive-values"></a>應用程式內含值  
 應用程式內含值表示呼叫樹狀圖中父函式所呼叫之函式執行個體位於呼叫堆疊上的時間。 該時間不包含呼叫作業系統所花費的時間，例如內容切換和輸入/輸出作業，但包含函式呼叫子函式所花費的時間。  
  
|Column|說明|  
|------------|-----------------|  
|**應用程式內含 (Application Inclusive) 時間**|在此內容中這個函式所有呼叫的總應用程式內含 (Application Inclusive) 時間。|  
|**應用程式內含 (Application Inclusive) 時間 %**|在分析執行的總功能內含耗用時間中，花費在此內容中此函式之總應用程式內含時間的百分比。|  
|**平均應用程式內含 (Application Inclusive) 時間**|在此內容中呼叫此函式的平均應用程式內含 (Application Inclusive) 時間。|  
|**最大應用程式內含 (Application Inclusive) 時間**|在此內容中呼叫此函式的最大應用程式內含 (Application Inclusive) 時間。|  
|**最小應用程式內含 (Application Inclusive) 時間**|在此內容中呼叫此函式的最小應用程式內含 (Application Inclusive) 時間。|  
  
## <a name="application-exclusive-values"></a>應用程式專屬值  
 應用程式專屬值表示呼叫樹狀圖中父函式所呼叫之函式執行個體在函式主體中直接執行程式碼的時間，也就是當函式位於呼叫堆疊的頂端時。 該時間不包含呼叫作業系統所花費的時間，例如內容切換和輸入/輸出作業。 也不包括函式呼叫子函式所花費的時間。  
  
|Column|描述|  
|------------|-----------------|  
|**應用程式專屬 (Application Exclusive) 時間**|在此內容中這個函式所有呼叫的總應用程式專屬 (Application Exclusive) 時間。|  
|**應用程式專屬 (Application Exclusive) 時間 %**|在分析執行的總功能專屬耗用時間中，花費在此內容中此函式之總應用程式專屬時間的百分比。|  
|**平均應用程式專屬 (Application Exclusive) 時間**|在此內容中呼叫此函式的平均應用程式專屬 (Application Exclusive) 時間。|  
|**最大應用程式專屬 (Application Exclusive) 時間**|在此內容中呼叫此函式的最大應用程式專屬 (Application Exclusive) 時間。|  
|**最小應用程式專屬 (Application Exclusive) 時間**|在此內容中呼叫此函式的最小應用程式專屬 (Application Exclusive) 時間。|  
  
## <a name="see-also"></a>另請參閱  
 [如何：自訂報表檢視資料行](../profiling/how-to-customize-report-view-columns.md)   
 [呼叫樹狀圖檢視](../profiling/call-tree-view-sampling-data.md)   
 [呼叫樹狀圖檢視 - 檢測](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [呼叫樹狀圖檢視 - 取樣](../profiling/call-tree-view-dotnet-memory-sampling-data.md)