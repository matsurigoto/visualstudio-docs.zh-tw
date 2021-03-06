---
title: Ca2242： 必須正確測試 NaN |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- TestForNaNCorrectly
- CA2242
helpviewer_keywords:
- CA2242
ms.assetid: e12dcffc-e255-4e1e-8fdf-3c6054d44abe
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: dcbfd5e5bd52be2919835cbe5bdfb06119f2a688
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588312"
---
# <a name="ca2242-test-for-nan-correctly"></a>CA2242：必須正確測試 NaN
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[ca2242 必須： 正確測試 NaN](https://docs.microsoft.com/visualstudio/code-quality/ca2242-test-for-nan-correctly)。

|||
|-|-|
|TypeName|TestForNaNCorrectly|
|CheckId|CA2242|
|分類|Microsoft.Usage|
|中斷變更|非中斷|

## <a name="cause"></a>原因
 運算式會測試值<xref:System.Single.NaN?displayProperty=fullName>或<xref:System.Double.NaN?displayProperty=fullName>。

## <a name="rule-description"></a>規則描述
 <xref:System.Double.NaN?displayProperty=fullName>這表示不是數字，則會產生未定義的算術運算時。 測試值是否相等的任何運算式並<xref:System.Double.NaN?displayProperty=fullName>一律會傳回`false`。 測試是否不相等的值之間的任何運算式並<xref:System.Double.NaN?displayProperty=fullName>一律會傳回`true`。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形並準確地判斷值是否代表<xref:System.Double.NaN?displayProperty=fullName>，使用<xref:System.Single.IsNaN%2A?displayProperty=fullName>或<xref:System.Double.IsNaN%2A?displayProperty=fullName>即可測試值。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告。

## <a name="example"></a>範例
 下列範例顯示不正確地測試值的兩個運算式<xref:System.Double.NaN?displayProperty=fullName>正確使用的運算式和<xref:System.Double.IsNaN%2A?displayProperty=fullName>即可測試值。

 [!code-csharp[FxCop.Usage.TestForNaN#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.TestForNaN/cs/FxCop.Usage.TestForNaN.cs#1)]
 [!code-vb[FxCop.Usage.TestForNaN#1](../snippets/visualbasic/VS_Snippets_CodeAnalysis/FxCop.Usage.TestForNaN/vb/FxCop.Usage.TestForNaN.vb#1)]



