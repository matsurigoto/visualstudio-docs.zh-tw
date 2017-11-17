---
title: "程式碼度量問題疑難排解 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f2fdb995-4888-4246-85dc-7bacadd45968
caps.latest.revision: 4
author: erickson-doug
ms.author: douge
manager: douge
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
ms.sourcegitcommit: 5db97d19b1b823388a465bba15d057b30ff0b3ce
ms.openlocfilehash: 26dc2869ceb16e2c16a74ee52249777394fb666a
ms.contentlocale: zh-tw
ms.lasthandoff: 09/26/2017

---
# <a name="troubleshooting-code-metrics-issues"></a>程式碼度量問題疑難排解
收集程式碼度量時，可能遇到下列問題：  
  
-   [在 Visual Studio 2010 程式碼複雜度計算中的變更](#Changes_in_Visual_Studio_2010_code_complexity_calculations)  
  
##  <a name="Changes_in_Visual_Studio_2010_code_complexity_calculations"></a>在 Visual Studio 2010 程式碼複雜度計算中的變更  
 針對相同的函式的程式碼複雜性公制，計算中[!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]可以不同於舊版的導出的計量[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]針對下列情況：  
  
-   此函式包含一或多個 catch 區塊。 在舊版的[!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)]，catch 區塊不包含在計算中。 在[!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]，每個 catch 區塊的複雜度加入函式的複雜度。  
  
-   函式包含參數 (在 VB 中的 Select Case) 陳述式。 編譯器之間的差異[!INCLUDE[vs_dev10_long](../code-quality/includes/vs_dev10_long_md.md)]及更早版本可以產生包含中斷的情況下的某些 switch 陳述式不同 MSIL 的程式碼。  
  
## <a name="see-also"></a>另請參閱  
 [測量 Managed 程式碼的複雜度和維護性](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)