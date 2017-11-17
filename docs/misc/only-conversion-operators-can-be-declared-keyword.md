---
title: "只有轉換運算子可以宣告為 &#39;&lt;關鍵字&gt;&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc33019"
  - "vbc33019"
helpviewer_keywords: 
  - "BC33019"
ms.assetid: 946266fe-a909-41b1-aad4-f85dc8050b88
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 只有轉換運算子可以宣告為 &#39;&lt;關鍵字&gt;&#39;
運算子不是轉換運算子時，[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement) 會指定 [Widening](/dotnet/visual-basic/language-reference/modifiers/widening) 或 [Narrowing](/dotnet/visual-basic/language-reference/modifiers/narrowing)。  
  
 每個運算子都必須宣告為 [Public](/dotnet/visual-basic/language-reference/modifiers/public) 和 [Shared](/dotnet/visual-basic/language-reference/modifiers/shared)。 不過，只能使用 [Widening](/dotnet/visual-basic/language-reference/modifiers/widening) 或 [Narrowing](/dotnet/visual-basic/language-reference/modifiers/narrowing) 來宣告轉換運算子，但不可同時使用兩者。  
  
 運算子定義可以選擇性地包含 [Overloads](/dotnet/visual-basic/language-reference/modifiers/overloads) 和 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows) 關鍵字。[Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement) 中不允許其他關鍵字。  
  
 **錯誤 ID︰**BC33019  
  
### 更正這個錯誤  
  
1.  請從運算子定義中移除 `Widening` 或 `Narrowing` 關鍵字。 這些不適用，因為將不會進行類型轉換。  
  
## 請參閱  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Type Conversions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/type-conversions)