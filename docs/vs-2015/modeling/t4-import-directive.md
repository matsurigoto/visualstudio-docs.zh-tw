---
title: T4 匯入指示詞 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 713ca975-b9aa-4210-bf6d-b7660f5b193b
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 2b0b4332f9c156bc9690ef94f8670e963203b5a9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47489144"
---
# <a name="t4-import-directive"></a>T4 匯入指示詞
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[T4 匯入指示詞](https://docs.microsoft.com/visualstudio/modeling/t4-import-directive)。  
  
在 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] T4 文字範本的程式碼區塊中，`import` 指示詞可讓您不必提供完整名稱，即可參考另一個命名空間中的項目。 這個指示詞相當於 C# 中的 `using` 或 `imports` 中的 [!INCLUDE[vb_current_short](../includes/vb-current-short-md.md)]。  
  
 撰寫 T4 文字範本的一般概觀，請參閱 <<c0> [ 撰寫 T4 文字範本](../modeling/writing-a-t4-text-template.md)。  
  
## <a name="using-the-import-directive"></a>使用匯入指示詞  
  
```  
<#@ import namespace="namespace" #>  
```  
  
 在這個範例中，範本程式碼會省略 System.IO 成員的明確命名空間。  
  
```  
<#@ import namespace="System.IO" #>  
<#   
   string fileContent = File.ReadAllText("C:\x.txt"); // System.IO.File  
#>   
The file contains: <#=  fileContent #>  
```  
  
## <a name="standard-imports"></a>標準匯入  
 下列命名空間會自動匯入，因此您不需要為它撰寫 import 指示詞：  
  
-   `System`  
  
 此外，如果使用自訂指示詞，指示詞處理器可能會自動匯入一些組件。  
  
 例如，如果撰寫特定領域語言 (DSL)，就不需要為下列命名空間撰寫 import 指示詞：  
  
-   `Microsoft.VisualStudio.Modeling`  
  
-   DSL 的命名空間  
  
## <a name="see-also"></a>另請參閱  
 [T4 組件指示詞](../modeling/t4-assembly-directive.md)



