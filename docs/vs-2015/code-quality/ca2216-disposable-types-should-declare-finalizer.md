---
title: CA2216： 可處置類型應該宣告完成項 |Microsoft Docs
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
- DisposableTypesShouldDeclareFinalizer
- CA2216
helpviewer_keywords:
- CA2216
- DisposableTypesShouldDeclareFinalizer
ms.assetid: 0cabcc5e-b526-452b-8c2a-0cbe3b93c0ef
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: d7e44ead74e7bcedefff69fefd2ebaf7a478faa3
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588420"
---
# <a name="ca2216-disposable-types-should-declare-finalizer"></a>CA2216：可處置類型應該宣告完成項
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[CA2216： 可處置類型應該宣告完成項](https://docs.microsoft.com/visualstudio/code-quality/ca2216-disposable-types-should-declare-finalizer)。

|||
|-|-|
|TypeName|DisposableTypesShouldDeclareFinalizer|
|CheckId|CA2216|
|分類|Microsoft.Usage|
|中斷變更|非中斷|

## <a name="cause"></a>原因
 型別可實作<xref:System.IDisposable?displayProperty=fullName>，且建議使用的 unmanaged 資源的欄位，不會實作完成項，如所述<xref:System.Object.Finalize%2A?displayProperty=fullName>。

## <a name="rule-description"></a>規則描述
 如果可處置型別包含下列類型的欄位，就會報告這項規則的違規情形：

-   <xref:System.IntPtr?displayProperty=fullName>

-   <xref:System.UIntPtr?displayProperty=fullName>

-   <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，實作完成項，會呼叫您<xref:System.IDisposable.Dispose%2A>方法。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 它可安全地隱藏此規則的警告，如果類型未實作<xref:System.IDisposable>用於釋放 unmanaged 的資源。

## <a name="example"></a>範例
 下列範例顯示違反此規則的型別。

 [!code-csharp[FxCop.Usage.DisposeNoFinalize#1](../snippets/csharp/VS_Snippets_CodeAnalysis/FxCop.Usage.DisposeNoFinalize/cs/FxCop.Usage.DisposeNoFinalize.cs#1)]

## <a name="related-rules"></a>相關的規則
 [CA2115：使用原生資源時必須呼叫 GC.KeepAlive](../code-quality/ca2115-call-gc-keepalive-when-using-native-resources.md)

 [CA1816：正確呼叫 GC.SuppressFinalize](../code-quality/ca1816-call-gc-suppressfinalize-correctly.md)

 [CA1049：具有原生資源的類型應該要可呼叫 Dispose 方法明確釋放資源](../code-quality/ca1049-types-that-own-native-resources-should-be-disposable.md)

## <a name="see-also"></a>另請參閱
 <xref:System.IDisposable?displayProperty=fullName> <xref:System.IntPtr?displayProperty=fullName>
 <xref:System.Runtime.InteropServices.HandleRef?displayProperty=fullName>
 <xref:System.UIntPtr?displayProperty=fullName>
 <xref:System.Object.Finalize%2A?displayProperty=fullName>
 [Dispose 模式](http://msdn.microsoft.com/library/31a6c13b-d6a2-492b-9a9f-e5238c983bcb)



