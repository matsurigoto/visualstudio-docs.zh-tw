---
title: "&#39;&lt;屬性名稱&gt;&#39; 的 &#39;&lt;關鍵字&gt;&#39; 存取子過時 (Visual Basic 警告) | Microsoft Docs"
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
  - "vbc40020"
  - "bc40020"
helpviewer_keywords: 
  - "BC40020"
ms.assetid: 005440f4-6e82-421c-b2ce-9c5139325bac
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;屬性名稱&gt;&#39; 的 &#39;&lt;關鍵字&gt;&#39; 存取子過時 (Visual Basic 警告)
已使用 <xref:System.ObsoleteAttribute> 屬性 \(attribute\) 和指示詞標示其對應程序之讀取或寫入屬性 \(property\) 的陳述式嘗試，會視為警告。  
  
 您可以將任何程式設計項目標記為不再使用，方法是對其套用 <xref:System.ObsoleteAttribute>。 如果您這麼做，則可以將屬性 \(attribute\) 的 <xref:System.ObsoleteAttribute.IsError%2A> 屬性 \(property\) 設定為 `True` 或 `False`。 如果您將它設定為 `True`，則編譯器會將使用這個項目的嘗試視為錯誤。 如果您將它設定為 `False`，或讓它預設為 `False`，則在嘗試使用該項目時，編譯器會發出警告。  
  
 根據預設，這個訊息是一個警告，因為 <xref:System.ObsoleteAttribute> 的 <xref:System.ObsoleteAttribute.IsError%2A> 屬性是 `False`。 如需隱藏警告或將警告視為錯誤的詳細資訊，請參閱[在 Visual Basic 中設定警告](../ide/configuring-warnings-in-visual-basic.md)。  
  
 **錯誤 ID︰**BC40020  
  
### 更正這個錯誤  
  
1.  請確定原始程式碼參考正確拼寫的屬性名稱。  
  
2.  請避免使用產生這則訊息的方式 \(讀取或寫入\) 來存取屬性。  
  
## 請參閱  
 [不在組建中：Visual Basic 中使用的屬性](http://msdn.microsoft.com/zh-tw/22231318-8a40-49af-9245-e0aab723563b)   
 [不在組建中：屬性的應用](http://msdn.microsoft.com/zh-tw/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [屬性程序](/dotnet/visual-basic/programming-guide/language-features/procedures/property-procedures)