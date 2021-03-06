---
title: CA2006： 使用 SafeHandle 封裝原生資源 |Microsoft Docs
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
- CA2006
- UseSafeHandleToEncapsulateNativeResources
helpviewer_keywords:
- UseSafeHandleToEncapsulateNativeResources
- CA2006
ms.assetid: a71950bd-bcc1-463d-b1f2-5233bc451456
caps.latest.revision: 19
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 08eed3577a8c225a69c5a3a8a9b4a1348656bd3f
ms.sourcegitcommit: 99d097d82ee4f9eff6f588e5ebb6b17d8f724b04
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2018
ms.locfileid: "47588315"
---
# <a name="ca2006-use-safehandle-to-encapsulate-native-resources"></a>CA2006：使用 SafeHandle 封裝原生資源
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[CA2006： 使用 SafeHandle 封裝原生資源](https://docs.microsoft.com/visualstudio/code-quality/ca2006-use-safehandle-to-encapsulate-native-resources)。

|||
|-|-|
|TypeName|UseSafeHandleToEncapsulateNativeResources|
|CheckId|CA2006|
|分類|Microsoft.Reliability|
|中斷變更|非重大|

## <a name="cause"></a>原因
 Managed 程式碼會使用<xref:System.IntPtr>存取原生資源。

## <a name="rule-description"></a>規則描述
 使用`IntPtr`managed 程式碼中可能表示有潛在的安全性和可靠性問題。 所有使用`IntPtr`必須檢視，以決定是否使用<xref:System.Runtime.InteropServices.SafeHandle>，或類似的技術，需要在該處。 如果發生問題，將`IntPtr`代表某些原生資源，例如記憶體、 檔案控制代碼或通訊端，managed 程式碼會被視為擁有。 如果 managed 程式碼擁有的資源，它也必須釋出，相關聯的原生資源，因為若要這樣做會造成資源流失。

 在此情況下，安全性或可靠性問題仍有如果允許多執行緒的存取`IntPtr`釋出資源所表示的方式`IntPtr`提供。 這些問題牽涉到回收`IntPtr`資源釋放時正在進行另一個執行緒上同時使用資源的值。 這會造成競爭情形，其中一個執行緒可以讀取或寫入錯誤的資源相關聯的資料。 例如，如果您的型別會儲存為作業系統控制代碼`IntPtr`，並可讓使用者呼叫這兩**關閉**和任何其他方法，會使用該控制代碼，同時並沒有某種類型的同步處理，您的程式碼已回收運用控制代碼發生問題。

 此控制代碼回收問題可能導致資料損毀和，通常有安全性弱點。 `SafeHandle` 和其同層級類別<xref:System.Runtime.InteropServices.CriticalHandle>提供機制來封裝資源的原生控制代碼，以便您可以避免這類執行緒的問題。 此外，您可以使用`SafeHandle`和其同層級類別`CriticalHandle`的其他執行緒的問題，比方說，仔細控制透過原生方法的呼叫中包含的原生控制代碼複本的 managed 物件的存留期。 在此情況下，您經常可以移除呼叫`GC.KeepAlive`。 當您使用會產生效能額外負荷所`SafeHandle`和程度， `CriticalHandle`，經常可以降低透過謹慎的設計。

## <a name="how-to-fix-violations"></a>如何修正違規
 轉換`IntPtr`使用量`SafeHandle`來安全地管理原生資源的存取權。 請參閱<xref:System.Runtime.InteropServices.SafeHandle>範例的參考主題。

## <a name="when-to-suppress-warnings"></a>隱藏警告的時機
 您不應該隱藏這個警告。

## <a name="see-also"></a>另請參閱
 <xref:System.IDisposable>



