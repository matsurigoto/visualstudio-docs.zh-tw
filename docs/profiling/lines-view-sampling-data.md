---
title: "程式行檢視 - 程式碼剖析工具：取樣資料 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "程式行檢視"
ms.assetid: 46497249-c797-42c5-a02c-3e4bb3b4ee60
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 程式行檢視 - 程式碼剖析工具：取樣資料
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

取樣資料的 \[程式行\] 檢視會針對在執行程式碼剖析期間收集樣本時執行的陳述式，列出效能資料。  
  
> [!NOTE]
>  Windows 8 和 Windows Server 2012 中的增強安全性功能，需要在 Visual Studio 分析工具收集這些平台資料的方式上進行重大變更。  Windows 市集應用程式也需要新的收集技術。  請參閱 [剖析 Windows 8 和 Windows Server 2012 應用程式](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)。  
  
 在任一原始程式檔中，任一陳述式在該原始程式檔中可以長達多行，而單獨一行程式行也可能包含一個以上的陳述式。  陳述式是由下列項目識別：  
  
-   包含此函式陳述式的原始程式檔。  
  
-   包含此陳述式的函式。  
  
-   此陳述式開始的原始程式碼行。  
  
-   此陳述式在原始程式檔中開始的字元。  
  
-   此陳述式在原始程式檔中結束的程式行位置。  
  
-   此陳述式在原始程式檔中結束的字元。  
  
 \[程式行名稱\] 資料行提供識別項資料的可排序串連。  
  
 根據定義，陳述式不會呼叫其他函式。  因此，只會列出專有值。  
  
|資料行|說明|  
|---------|--------|  
|**處理序 ID**|執行程式碼剖析期間的處理序 ID \(PID\)。|  
|**處理序名稱**|處理序的名稱。|  
|**模組名稱**|包含函式行的模組名稱。|  
|**模組路徑**|包含函式行的模組路徑。|  
|**原始程式檔**|包含函式行的原始程式檔。|  
|**函式名稱**|函式的名稱。|  
|**函式行號**|在原始程式檔中這個函式的開頭行號。|  
|**函式位址**|函式的開始位址。|  
|**原始程式碼開頭行**|收集這個樣本的原始程式檔中的起始行號。|  
|**原始程式碼結尾行**|收集這個樣本的原始程式檔中的結尾行號。|  
|**原始程式碼開頭字元**|收集這個樣本的原始程式檔行中，起始字元的位移。|  
|**原始程式碼結尾字元**|收集這個樣本的原始程式檔行中，結尾字元的位移。|  
|**程式行名稱**|使用下列語法之程式行的程式碼剖析工具產生的識別項：`Source File`**;\[**`Line Number Start`**,**`Character Start`**\]\-\>;\[**`Line Number End`,`Character End`**\]**|  
|**專有樣本**|當正在執行函式程式行時所收集的總樣本數。|  
|**專有樣本 %**|執行程式碼剖析期間，執行函式行時所收集的所有樣本的百分比。|  
  
## 請參閱  
 [程式行檢視 \- 取樣](../profiling/lines-view-dotnet-memory-sampling-data.md)