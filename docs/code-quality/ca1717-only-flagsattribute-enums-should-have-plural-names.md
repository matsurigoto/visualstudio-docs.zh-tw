---
title: "： 只有 FlagsAttribute 列舉 ca1717 應該使用複數名稱 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1717
- OnlyFlagsEnumsShouldHavePluralNames
helpviewer_keywords:
- OnlyFlagsEnumsShouldHavePluralNames
- CA1717
ms.assetid: a6855d8b-d78a-42c1-834e-61c31f5572ed
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 787b2f5c1a838bb6312fe5d08cd8328b07460243
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2017
---
# <a name="ca1717-only-flagsattribute-enums-should-have-plural-names"></a>CA1717：只有 FlagsAttribute 列舉應該使用複數名稱
|||  
|-|-|  
|TypeName|OnlyFlagsEnumsShouldHavePluralNames|  
|CheckId|CA1717|  
|分類|Microsoft.Naming|  
|中斷變更|中斷|  
  
## <a name="cause"></a>原因  
 外部可見的列舉型別的名稱結尾的複數單字和列舉型別不標記為<xref:System.FlagsAttribute?displayProperty=fullName>屬性。  
  
## <a name="rule-description"></a>規則描述  
 依照命名規範的要求列舉的複數名稱代表可以同時指定多個列舉值。 <xref:System.FlagsAttribute>告訴編譯器列舉型別應該視為位元欄位，可讓列舉型別上的位元運算。  
  
 如果只可以指定列舉的其中一個值，一次，列舉型別的名稱應該是單數單字。 例如，定義一周天數的列舉可能被適用於應用程式中您可以在此指定多天。 這個列舉型別應該具有<xref:System.FlagsAttribute>和天' 呼叫。 類似的列舉型別，可讓某一天指定沒有屬性，且可能 ' day '。  
  
 命名慣例提供共同的外觀文件庫目標通用語言執行平台。 這會減少需要學習新的軟體程式庫，而且會增加的程式庫由具備專業知識在開發 managed 程式碼開發的客戶信心的時間。  
  
## <a name="how-to-fix-violations"></a>如何修正違規  
 讓列舉型別的名稱單數單字，或新增<xref:System.FlagsAttribute>。  
  
## <a name="when-to-suppress-warnings"></a>隱藏警告的時機  
 它可以安全地名稱結尾的單數單字內如果隱藏此規則的警告。  
  
## <a name="related-rules"></a>相關的規則  
 [CA1714：旗標列舉應該使用複數名稱](../code-quality/ca1714-flags-enums-should-have-plural-names.md)  
  
 [CA1027：必須以 FlagsAttribute 標記列舉](../code-quality/ca1027-mark-enums-with-flagsattribute.md)  
  
 [CA2217：不要以 FlagsAttribute 標記列舉](../code-quality/ca2217-do-not-mark-enums-with-flagsattribute.md)  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.FlagsAttribute?displayProperty=fullName>   
 [列舉設計](/dotnet/standard/design-guidelines/enum)