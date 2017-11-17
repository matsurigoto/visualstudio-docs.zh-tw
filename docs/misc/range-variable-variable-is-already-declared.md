---
title: "範圍變數 &lt;變數&gt; 已宣告 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36600"
  - "bc36600"
helpviewer_keywords: 
  - "BC36600"
ms.assetid: d53da04d-cd36-44ec-8b23-48cd81231191
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 範圍變數 &lt;變數&gt; 已宣告
`Select` 子句中指定的範圍變數名稱，或 `Aggregate`、`Group By` 或 `Group Join` 子句的 `Into` 部分，會重複已經在查詢子句中指定之範圍變數的名稱。  
  
 **錯誤 ID︰**BC36600  
  
### 更正這個錯誤  
  
1.  請確定查詢子句中的所有範圍變數都有唯一的名稱。  
  
## 請參閱  
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [Aggregate Clause](/dotnet/visual-basic/language-reference/queries/aggregate-clause)   
 [Select Clause](/dotnet/visual-basic/language-reference/queries/select-clause)   
 [Group By 子句](/dotnet/visual-basic/language-reference/queries/group-by-clause)   
 [Group Join Clause](/dotnet/visual-basic/language-reference/queries/group-join-clause)