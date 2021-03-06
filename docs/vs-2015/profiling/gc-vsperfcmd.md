---
title: GC (VSPerfCmd) | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7c81e88b-a748-4cf5-a7a1-3429608e1b54
caps.latest.revision: 17
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d7e7323d679ac0cde2a1227c1c9ce4b7e3a380fd
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47498189"
---
# <a name="gc-vsperfcmd"></a>GC (VSPerfCmd)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[GC (VSPerfCmd)](https://docs.microsoft.com/visualstudio/profiling/gc-vsperfcmd)。  
  
**GC** 選項啟用 .NET Framework 記憶體配置和物件存留期資料的收集。 **GC** 選項只能與取樣分析方法搭配使用，並且只能與 **Launch** 選項搭配使用。  
  
 當您要使用 **GC** 選項時，不需要 VSPerfClrEnv **/sampleon** 命令。  
  
 如果未指定任何參數，或指定 **Allocation** 參數，則只會收集 .NET Framework 記憶體配置資料。 如果指定 **Lifetime** 參數，則會收集 .NET Framework 記憶體配置和 .NET Framework 物件存留期資料。  
  
## <a name="syntax"></a>語法  
  
```  
VSPerfCmd.exe /Launch:AppName /GC[:{Allocation|Lifetime}] [Options]  
```  
  
#### <a name="parameters"></a>參數  
 **配置**  
 預設值： 收集 .NET Framework 記憶體配置資料。  
  
 **存留期**  
 收集 .NET Framework 記憶體配置資料和 .NET Framework 物件存留期資料。  
  
## <a name="required-options"></a>必要選項  
 **GC** 選項只能與 **Launch** 選項搭配使用。  
  
 **Launch：** `AppName`  
 啟動指定的應用程式，並使用取樣方法開始程式碼剖析。  
  
## <a name="example"></a>範例  
 下列範例會啟動應用程式，並收集 .NET Framework 記憶體配置資料。  
  
```  
VSPerfCmd.exe /Launch:TestApp.exe /gc  
```  
  
## <a name="see-also"></a>另請參閱  
 [VSPerfCmd](../profiling/vsperfcmd.md)   
 [對獨立應用程式進行程式碼剖析](../profiling/command-line-profiling-of-stand-alone-applications.md)   
 [對 ASP.NET Web 應用程式進行程式碼剖析](../profiling/command-line-profiling-of-aspnet-web-applications.md)   
 [對服務進行程式碼剖析](../profiling/command-line-profiling-of-services.md)



