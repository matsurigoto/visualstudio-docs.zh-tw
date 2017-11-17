---
title: 'CA1021: Avoid out parameters | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CA1021
- AvoidOutParameters
helpviewer_keywords:
- AvoidOutParameters
- CA1021
ms.assetid: 970f2304-842c-4fb7-9734-f3871da8d479
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
manager: wpickett
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: eb5c9550fd29b0e98bf63a7240737da4f13f3249
ms.openlocfilehash: c2d981d71613b94c7c1142d40fc0ef8e4a6d0a5c
ms.contentlocale: zh-tw
ms.lasthandoff: 08/30/2017

---
# <a name="ca1021-avoid-out-parameters"></a>CA1021: Avoid out parameters
|||  
|-|-|  
|TypeName|AvoidOutParameters|  
|CheckId|CA1021|  
|Category|Microsoft.Design|  
|Breaking Change|Breaking|  
  
## <a name="cause"></a>Cause  
 A public or protected method in a public type has an `out` parameter.  
  
## <a name="rule-description"></a>Rule Description  
 Passing types by reference (using `out` or `ref`) requires experience with pointers, understanding how value types and reference types differ, and handling methods with multiple return values. Also, the difference between `out` and `ref` parameters is not widely understood.  
  
 When a reference type is passed "by reference," the method intends to use the parameter to return a different instance of the object. Passing a reference type by reference is also known as using a double pointer, pointer to a pointer, or double indirection. By using the default calling convention, which is pass "by value," a parameter that takes a reference type already receives a pointer to the object. The pointer, not the object to which it points, is passed by value. Pass by value means that the method cannot change the pointer to have it point to a new instance of the reference type. However, it can change the contents of the object to which it points. For most applications this is sufficient and yields the desired behavior.  
  
 If a method must return a different instance, use the return value of the method to accomplish this. See the <xref:System.String?displayProperty=fullName> class for a variety of methods that operate on strings and return a new instance of a string. When this model is used, the caller must decide whether the original object is preserved.  
  
 Although return values are commonplace and heavily used, the correct application of `out` and `ref` parameters requires intermediate design and coding skills. Library architects who design for a general audience should not expect users to master working with `out` or `ref` parameters.  
  
## <a name="how-to-fix-violations"></a>How to Fix Violations  
 To fix a violation of this rule that is caused by a value type, have the method return the object as its return value. If the method must return multiple values, redesign it to return a single instance of an object that holds the values.  
  
 To fix a violation of this rule that is caused by a reference type, make sure that the desired behavior is to return a new instance of the reference. If it is, the method should use its return value to do this.  
  
## <a name="when-to-suppress-warnings"></a>When to Suppress Warnings  
 It is safe to suppress a warning from this rule. However, this design could cause usability issues.  
  
## <a name="example"></a>Example  
 The following library shows two implementations of a class that generates responses to the feedback of a user. The first implementation (`BadRefAndOut`) forces the library user to manage three return values. The second implementation (`RedesignedRefAndOut`) simplifies the user experience by returning an instance of a container class (`ReplyData`) that manages the data as a single unit.  
  
 [!code-csharp[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_1.cs)]  
  
## <a name="example"></a>Example  
 The following application illustrates the experience of the user. The call to the redesigned library (`UseTheSimplifiedClass` method) is more straightforward, and the information returned by the method is easily managed. The output from the two methods is identical.  
  
 [!code-csharp[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_2.cs)]  
  
## <a name="example"></a>Example  
 The following example library illustrates how `ref` parameters for reference types are used and shows a better way to implement this functionality.  
  
 [!code-csharp[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_3.cs)]  
  
## <a name="example"></a>Example  
 The following application calls each method in the library to demonstrate the behavior.  
  
 [!code-csharp[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_4.cs)]  
  
 This example produces the following output.  
  
 **Changing pointer - passed by value:**  
**12345**  
**12345**  
**Changing pointer - passed by reference:**  
**12345**  
**12345 ABCDE**  
**Passing by return value:**  
**12345 ABCDE**   
## <a name="try-pattern-methods"></a>Try pattern methods  
  
### <a name="description"></a>Description  
 Methods that implement the **Try\<Something>** pattern, such as <xref:System.Int32.TryParse%2A?displayProperty=fullName>, do not raise this violation. The following example shows a structure (value type) that implements the <xref:System.Int32.TryParse%2A?displayProperty=fullName> method.  
  
### <a name="code"></a>Code  
 [!code-csharp[FxCop.Design.TryPattern#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_5.cs)]  
  
## <a name="related-rules"></a>Related Rules  
 [CA1045: Do not pass types by reference](../code-quality/ca1045-do-not-pass-types-by-reference.md)