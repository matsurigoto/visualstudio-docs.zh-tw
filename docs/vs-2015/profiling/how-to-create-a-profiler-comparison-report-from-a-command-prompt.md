---
title: 如何：從命令提示字元建立分析工具比較報表 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00548d16-eb5b-46f7-8a65-862f98a43831
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3cb31a79af25fbe66112efd6be0aacd9b3c3820d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47488614"
---
# <a name="how-to-create-a-profiler-comparison-report-from-a-command-prompt"></a>如何：從命令提示字元建立程式碼剖析工具比較報表
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[如何： 從命令提示字元建立 Profiler 比較報表](https://docs.microsoft.com/visualstudio/profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt)。  
  
您可以產生 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 分析工具報表，以比較兩個分析資料 (.VSP 或 .VSPS) 檔案的效能資料。 此報表顯示會顯示差異、 效能衰退和改進，到另一個程式碼剖析工作階段時發生。 報表中的值呈現與您所指定之第一個檔案的基準線的差異或變更。 這項差異的計算是透過判斷舊值 (即基準值) 與新分析中結果值之間的差異。 分析工具資料的比較可以根據程式碼中的函式、應用程式中的模組、程式行、指令指標 (IP) 及型別。  
  
 若要列出比較類別和欄位的識別碼，請鍵入下列命令列：  
  
 **VSPerfReport /querydifftables**  *VspFileName1* *VspFileName2*  
  
 使用下列語法來建立比較報表：  
  
 **VSPerfReport /diff**  `VspFileName1` *VspFileName2* [**/**`Options`]  
  
 您可以將下表中的選項新增至 **VSPerfReport /diff** 命令列。  
  
|選項|描述|  
|------------|-----------------|  
|**DiffThreshold:**[*值*]|如果低於這個百分比臨界值，則忽略差異。 此外，將不會顯示值低於此臨界值的新資料。|  
|**DiffTable:** *TableName*|使用此資料表來比較檔案。 預設會使用函式資料表。 指定 **VSPerfReport /querydifftables** 中所列的識別碼。|  
|**DiffColumn:** *ColumnName*|使用此資料行來比較值。 預設會使用專有樣本百分比資料行。 指定 **VSPerfReport /querydifftables** 中所列的識別碼。|


