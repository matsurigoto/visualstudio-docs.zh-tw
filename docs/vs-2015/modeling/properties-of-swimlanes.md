---
title: 泳道的屬性 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.dsltools.dsldesigner.swimlane
helpviewer_keywords:
- Domain-Specific Language, swimlane
ms.assetid: 47edbc2d-09e4-48ac-b4d1-5268a06a27e6
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: dd274d1de99ab4a9dac6dd6c045ef6d313fe9bb7
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47488387"
---
# <a name="properties-of-swimlanes"></a>泳道的屬性
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[屬性的泳道](https://docs.microsoft.com/visualstudio/modeling/properties-of-swimlanes)。  
  
您可以將泳道加入圖表。 區隔線會將圖表分成垂直或水平區域。 您可以定義其他要顯示在泳道的圖形。 如需詳細資訊，請參閱 <<c0> [ 如何定義特定領域語言](../modeling/how-to-define-a-domain-specific-language.md)。 如需如何使用這些屬性的詳細資訊，請參閱[自訂及擴充特定領域語言](../modeling/customizing-and-extending-a-domain-specific-language.md)。  
  
 泳道具有下表中所列的屬性。  
  
|屬性|描述|預設|  
|--------------|-----------------|-------------|  
|本文填滿色彩|為泳道本文填滿色彩。|白皮書|  
|標頭填滿色彩|為泳道標題填滿色彩。|暗灰色|  
|分隔符號色彩|分隔線的色彩。|LightGray|  
|分隔符號的線條樣式|分隔線的樣式 (`Solid`， `Dash`， `Dot`， `DashDot`， `DashDotDot`，或`Custom`)。|`Dash`|  
|分隔符號寬度|英吋為單位的分隔線的粗細。|0.03125|  
|文字色彩|使用此區隔線相關聯的文字裝飾項目的色彩。|黑色|  
|存取修飾詞|類別的存取層級 (`public`或`internal`)。|Public|  
|自訂屬性|用來將屬性加入至這個區隔線從產生的程式碼類別。|\<無 >|  
|產生雙衍生|如果`True`，將產生的基底類別和部分類別 （以支援透過覆寫自訂）。 如需詳細資訊，請參閱 <<c0> [ 覆寫及擴充產生的類別](../modeling/overriding-and-extending-the-generated-classes.md)。|False|  
|具有自訂建構函式|如果`True`，以原始碼提供自訂建構函式。 如需詳細資訊，請參閱 <<c0> [ 覆寫及擴充產生的類別](../modeling/overriding-and-extending-the-generated-classes.md)。|False|  
|繼承修飾詞|描述的繼承來源的程式碼類別產生的區隔線的類型 (`none`，`abstract`或`sealed`)。|無|  
|基底泳道|此泳道的基底類別。|(無)|  
|名稱|此泳道的名稱。|目前的名稱|  
|命名空間|此泳道附屬於命名空間。|目前的命名空間|  
|工具提示類型|工具提示的定義方式 (`fixed`， `variable`，或`none`)。 如果`fixed`，然後的值`Fixed Tooltip Text`屬性用; 如果`variable`，然後在自訂程式碼中定義工具提示。|\<無 >|  
|注意|此區隔線相關聯的非正式附註。|\<無 >|  
|對齊|水平或垂直對齊方式。|垂直|  
|初始的高度|此泳道，英吋為單位的初始高度。 僅適用於水平泳道。|0|  
|初始寬度|此泳道，英吋為單位的初始寬度。 僅適用於垂直泳道。|0|  
|公開 （expose) 的文字色彩|如果`True`，使用者可以設定區隔線的色彩在產生的設計工具中。 若要設定這種情況，以滑鼠右鍵按一下 「 泳道 」 圖形，然後按一下**加入已公開**。|False|  
|描述|用來產生的設計工具的文件。|\<無 >|  
|顯示名稱|將會顯示在產生的設計工具，來參考此區隔線類別名稱。|\<無 >|  
|固定的工具提示文字|用於固定工具提示文字。|\<無 >|  
|說明關鍵字|用來編製索引的此泳道的 F1 說明關鍵字。|\<無 >|  
  
## <a name="see-also"></a>另請參閱  
 [特定領域語言工具字彙](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



