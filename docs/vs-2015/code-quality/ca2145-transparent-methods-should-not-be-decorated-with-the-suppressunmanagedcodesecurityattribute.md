---
title: CA2145： 透明方法不應該使用 SuppressUnmanagedCodeSecurityAttribute 裝飾 |Microsoft Docs
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
- CA2145
ms.assetid: 81970700-b438-4b3b-9239-16887e16f7b7
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 7dcb7d2596a03bc78eed7dc4c3a1455c91478b04
ms.sourcegitcommit: 568bb0b944d16cfe1af624879fa3d3594d020187
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/13/2018
ms.locfileid: "47588953"
---
# <a name="ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute"></a>CA2145：透明方法不可以使用 SuppressUnmanagedCodeSecurityAttribute 來裝飾
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[CA2145： 透明方法不可以使用 SuppressUnmanagedCodeSecurityAttribute 來裝飾](https://docs.microsoft.com/visualstudio/code-quality/ca2145-transparent-methods-should-not-be-decorated-with-the-suppressunmanagedcodesecurityattribute)。

|||
|-|-|
|TypeName|TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity|
|CheckId|CA2145|
|分類|Microsoft.Security|
|中斷變更|中斷|

## <a name="cause"></a>原因
 透明方法，這個方法標記為<xref:System.Security.SecuritySafeCriticalAttribute>方法或包含一種方法的類型以標記<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>屬性。

## <a name="rule-description"></a>規則描述
 方法使用裝飾<xref:System.Security.SuppressUnmanagedCodeSecurityAttribute>屬性有任何方法呼叫它時放置隱含的 LinkDemand。 這個 LinkDemand 會要求呼叫程式碼具備安全性關鍵。 標記使用 SuppressUnmanagedCodeSecurity 的方法<xref:System.Security.SecurityCriticalAttribute>屬性會讓這項需求更為明顯的方法呼叫者。

## <a name="how-to-fix-violations"></a>如何修正違規
 若要修正此規則的違規情形，標記方法，或輸入具有<xref:System.Security.SecurityCriticalAttribute>屬性。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 請勿隱藏此規則的警告。

### <a name="code"></a>程式碼
 [!code-csharp[FxCop.Security.CA2145.TransparentMethodsShouldNotUseSuppressUnmanagedCodeSecurity#1](../snippets/csharp/VS_Snippets_CodeAnalysis/fxcop.security.ca2145.transparentmethodsshouldnotusesuppressunmanagedcodesecurity/cs/ca2145.cs#1)]

### <a name="comments"></a>註解



