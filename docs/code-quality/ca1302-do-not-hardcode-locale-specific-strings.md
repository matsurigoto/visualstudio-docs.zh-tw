---
title: 'CA1302: Do not hardcode locale specific strings | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
helpviewer_keywords:
- DoNotHardcodeLocaleSpecificStrings
- CA1302
ms.assetid: 05ed134a-837d-43d7-bf97-906edeac44ce
caps.latest.revision: 17
author: stevehoag
ms.author: shoag
manager: wpickett
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: b723eade12eac5be6959710afc667452d05ac81a
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="ca1302-do-not-hardcode-locale-specific-strings"></a>CA1302: Do not hardcode locale specific strings
|||  
|-|-|  
|TypeName|DoNotHardcodeLocaleSpecificStrings|  
|CheckId|CA1302|  
|Category|Microsoft.Globalization|  
|Breaking Change|Non-breaking|  
  
## <a name="cause"></a>Cause  
 A method uses a string literal that represents part of the path of certain system folders.  
  
## <a name="rule-description"></a>Rule Description  
 The <xref:System.Environment.SpecialFolder?displayProperty=fullName> enumeration contains members that refer to special system folders. The locations of these folders can have different values on different operating systems, the user can change some of the locations, and the locations are localized. An example of a special folder is the System folder, which is "C:\WINDOWS\system32" on [!INCLUDE[winxp](../code-quality/includes/winxp_md.md)] but "C:\WINNT\system32" on [!INCLUDE[win2kfamily](../code-quality/includes/win2kfamily_md.md)]. The <xref:System.Environment.GetFolderPath%2A?displayProperty=fullName> method returns the locations that are associated with the <xref:System.Environment.SpecialFolder> enumeration. The locations that are returned by <xref:System.Environment.GetFolderPath%2A> are localized and appropriate for the currently running computer.  
  
 This rule tokenizes the folder paths that are retrieved by using the <xref:System.Environment.GetFolderPath%2A> method into separate directory levels. Each string literal is compared to the tokens. If a match is found, it is assumed that the method is building a string that refers to the system location that is associated with the token. For portability and localizability, use the <xref:System.Environment.GetFolderPath%2A> method to retrieve the locations of the special system folders instead of using string literals.  
  
## <a name="how-to-fix-violations"></a>How to Fix Violations  
 To fix a violation of this rule, retrieve the location by using the <xref:System.Environment.GetFolderPath%2A> method.  
  
## <a name="when-to-suppress-warnings"></a>When to Suppress Warnings  
 It is safe to suppress a warning from this rule if the string literal is not used to refer to one of the system locations that is associated with the <xref:System.Environment.SpecialFolder> enumeration.  
  
## <a name="example"></a>Example  
 The following example builds the path of the common application data folder, which generates three warnings from this rule. Next, the example retrieves the path by using the <xref:System.Environment.GetFolderPath%2A> method.  
  
 [!code-csharp[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/CSharp/ca1302-do-not-hardcode-locale-specific-strings_1.cs)] [!code-vb[FxCop.Globalization.HardcodedLocaleStrings#1](../code-quality/codesnippet/VisualBasic/ca1302-do-not-hardcode-locale-specific-strings_1.vb)]  
  
## <a name="related-rules"></a>Related Rules  
 [CA1303: Do not pass literals as localized parameters](../code-quality/ca1303-do-not-pass-literals-as-localized-parameters.md)