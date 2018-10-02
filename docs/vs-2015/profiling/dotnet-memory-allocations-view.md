---
title: .NET 記憶體配置檢視 | Microsoft Docs
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
- vs.performance.view.allocation
helpviewer_keywords:
- performance reports, allocation view
- Allocations view
- profiling tools, Allocation view
- profiling tools reports, Allocation view
ms.assetid: 01eb876e-c413-4516-977b-4f896929e8a6
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e53fe27148901bc4af78f9b607c0e3a70ba4b91
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47492419"
---
# <a name="net-memory-allocations-view"></a>.NET 記憶體配置檢視
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[.NET 記憶體配置檢視](https://docs.microsoft.com/visualstudio/profiling/dotnet-memory-allocations-view)。  
  
[配置] 檢視會列出在分析回合期間建立的類型。 每種類型都是呼叫樹狀圖的根節點，可顯示導致類型配置的函式執行路徑。  
  
 類型資料列中的資料會顯示分析回合中所建立類型的物件總數，以及針對該類型之物件所配置的位元組總數。 類型的內含和專有值一律會相同。  
  
-   內含值是針對呼叫樹狀圖中父函式所呼叫函式和其子函式執行個體中建立的物件。  
  
-   父函式呼叫函式直接建立的物件時，專有值適用於這類物件。 不包含子函式中所建立的物件。  
  
 函式的資料會顯示已建立的物件數目以及針對父類型的物件所配置的位元組數目。  
  
## <a name="highlighting-the-execution-hot-path"></a>反白顯示執行最忙碌路徑  
 您可以找到建立父類型大部分物件之呼叫樹狀圖的執行路徑。  
  
-   若要顯示最常使用的路徑，請以滑鼠右鍵按一下類型或函式，然後按一下 [展開最忙碌路徑]。  
  
|資料行|描述|  
|------------|-----------------|  
|**名稱**|已配置類型或函式的名稱。|  
|**處理序 ID**|分析執行的處理序 ID (PID)。|  
|**處理序名稱**|處理序的名稱。|  
|**模組名稱**|包含類型或函式的模組名稱。|  
|**模組路徑**|包含類型或函式的模組路徑。|  
|**原始程式檔**|包含類型或函式定義的原始程式檔。|  
|**函式行號**|原始程式檔中此類型定義或函式的開頭行號。|  
|**層級**|指出資料適用於類型還是函式。|  
|**內含配置**|-   針對函式，函式所建立父類型的物件總數。 此數目包含子函式中所建立的物件。<br />-   針對類型，為該類型建立的執行個體總數。|  
|**內含配置 %**|-   針對函式，分析回合中建立的所有物件中，屬於函式父類型之內含配置的百分比。<br />-   針對類型，分析回合中建立的物件總數中，屬於類型執行個體的百分比。|  
|**專有配置**|-   針對函式，函式直接在呼叫堆疊最上方執行時所建立的物件數目。 此數目未包含子函式中所建立的物件。<br />-   針對類型，為該類型建立的執行個體總數。|  
|**專有配置 %**|-   針對函式，分析回合中建立的所有物件中，屬於函式父類型之專有配置的百分比。<br />-   針對類型，分析回合中建立的物件總數中，屬於類型執行個體的百分比。|  
|**內含位元組**|-   針對函式，父類型之物件的函式所配置的記憶體位元組數目。 此數目包含其子函式所配置的記憶體。<br />-   針對類型，分析回合中針對類型執行個體所配置的位元組總數。|  
|**內含位元組 %**|-   針對函式，分析回合中配置的所有記憶體中，屬於函式父類型之內含配置的百分比。<br />-   針對類型，針對類型執行個體所配置的分析回合中配置的所有記憶體百分比。|  
|**專有位元組**|-   針對函式，父類型之物件的函式所配置的記憶體位元組數目。 此數目未包含其子函式所配置的記憶體。<br />-   針對類型，分析回合中針對類型執行個體所配置的位元組總數。|  
|**專有位元組 %**|-   針對函式，分析回合中配置的所有記憶體中，屬於函式父類型之專有配置的百分比。<br />-   針對類型，針對類型執行個體所配置的分析回合中配置的所有記憶體百分比。|


