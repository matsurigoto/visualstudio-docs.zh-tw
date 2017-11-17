---
title: "Task Base Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 6c3f6238-b9f0-4325-b8b0-de61090bd0a2
caps.latest.revision: 6
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 6
---
# Task Base Class
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

許多工作最終都繼承自 <xref:Microsoft.Build.Utilities.Task> 類別。  此類別會將多個參數加入至從其中衍生的工作。  這些參數已於本文件中列出。  
  
## 參數  
 下表說明此基底類別的參數。  
  
|參數|描述|  
|--------|--------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|選擇性 <xref:Microsoft.Build.Framework.IBuildEngine> 參數。<br /><br /> 指定可供工作使用的建置引擎介面。  建置引擎會自動設定這個參數，以允許工作回呼至它。|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|選擇性 <xref:Microsoft.Build.Framework.IBuildEngine2> 參數。<br /><br /> 指定可供工作使用的建置引擎介面。  建置引擎會自動設定這個參數，以允許工作回呼至它。<br /><br /> 這是很便利的屬性，如此一來，從此類別繼承的工作作者就不需要將值從 `IBuildEngine` 轉換為 `IBuildEngine2`。|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|選擇性 <xref:Microsoft.Build.Framework.IBuildEngine3> 參數。<br /><br /> 指定由主機提供的建置引擎介面。|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|選擇性 <xref:Microsoft.Build.Framework.ITaskHost> 參數。<br /><br /> 指定主物件執行個體 \(可以是 Null\)。  如果主 IDE 將主物件與這個特定工作關聯，則建置引擎會設定這個屬性。|  
|<xref:Microsoft.Build.Utilities.Task.Log%2A>|選擇性 <xref:Microsoft.Build.Utilities.TaskLoggingHelper> 唯讀參數。<br /><br /> 記錄 Helper 物件。|  
  
## 請參閱  
 [Task Reference](../msbuild/msbuild-task-reference.md)   
 [工作](../msbuild/msbuild-tasks.md)