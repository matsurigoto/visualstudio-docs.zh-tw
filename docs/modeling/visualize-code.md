---
title: "視覺化程式碼 |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-devops-techdebt
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code, understanding
- code, visualizing
- code, exploring
ms.assetid: 0dd7d438-393a-4cd3-b417-9bf37379e1b0
caps.latest.revision: 47
author: alexhomer1
ms.author: ahomer
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
translationtype: Machine Translation
ms.sourcegitcommit: 3d07f82ea737449fee6dfa04a61e195654ba35fa
ms.openlocfilehash: aa7e0e7e9bbd4d4a3f8a1b2fa82f1ce7a6ba3e53
ms.lasthandoff: 02/22/2017

---
# <a name="visualize-code"></a>視覺化程式碼
您可以使用 Visual Studio 的視覺化和模型工具，以利了解現有的程式碼，並描述您的應用程式。 這可讓您以視覺化方式了解變更會如何影響程式碼，並幫助您評估因這些變更所導致的工作和風險。 例如：  
  
-   若要了解程式碼中的關聯性，請以視覺化方式對應這些關聯性。  
  
-   若要描述您的系統架構，並讓程式碼與設計保持一致，建立相依性圖表，並針對這些圖表驗證程式碼。  
  
-   若要描述類別結構，建立類別圖。  
  
 這些工具也可協助您更輕鬆地與專案相關人員通訊。 
  
 若要查看哪些版本的 Visual Studio 支援每項功能，請參閱[的架構和模型工具版本支援](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)  
  
## <a name="what-do-you-want-to-do"></a>請您指定選項。  
  
|||  
|-|-|  
|**了解程式碼和其關聯性︰**<br /><br /> 對應特定程式碼片段之間的關聯性。<br /><br /> 查看整個方案的程式碼中的關聯性概觀。<br /><br /> **注意**：在本版 Visual Studio 中，會以 *Code Map* 一詞取代 *「相依性圖形」*(Dependency Graph)。|-   [對應整個方案的相依性](../modeling/map-dependencies-across-your-solutions.md)<br />-   [使用 code map 偵錯應用程式](../modeling/use-code-maps-to-debug-your-applications.md)<br />-   [找出潛在的問題使用 code map 分析器](../modeling/find-potential-problems-using-code-map-analyzers.md)<br />-   [偵錯時對應呼叫堆疊上的方法](../debugger/map-methods-on-the-call-stack-while-debugging-in-visual-studio.md)|  
|**了解類別結構︰**<br /><br /> 從程式碼建立類別圖，將專案中的類別結構視覺化。|[如何：將類別圖表新增至專案 (類別設計工具)](../ide/how-to-add-class-diagrams-to-projects-class-designer.md)|  
|**描述高階系統設計，並針對這項設計驗證程式碼︰**<br /><br /> 藉由建立相依性圖表來描述高階系統設計和其預定的相依性。 針對此設計驗證程式碼，以確定程式碼中的相依性與設計保持一致。|-   [從您的程式碼建立相依性圖表](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [相依性圖表︰ 參考](../modeling/layer-diagrams-reference.md)<br />-   [相依性圖表︰ 方針](../modeling/layer-diagrams-guidelines.md)<br />-   [使用相依性圖表驗證程式碼](../modeling/validate-code-with-layer-diagrams.md)|  
  
## <a name="external-resources"></a>外部資源  
  
|**類別目錄**|**連結**|  
|------------------|---------------|  
|**論壇**|-   [Visual Studio Visualization i 模型工具](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio Visualization i Modeling SDK （DSL 工具）](http://go.microsoft.com/fwlink/?LinkId=184721)|  
|**部落格**|[Visual Studio ALM + Team Foundation Server 部落格](http://go.microsoft.com/fwlink/?LinkID=201340)|  
|**技術文件和日誌**|[MSDN 架構論壇](http://go.microsoft.com/fwlink/?LinkId=201343)|  
  
## <a name="see-also"></a>另請參閱  
 [案例︰ 變更您的設計使用視覺化和模型化](../modeling/scenario-change-your-design-using-visualization-and-modeling.md)   
 [分析和模型架構](../modeling/analyze-and-model-your-architecture.md)   
 [建立您的應用程式架構的模型](../modeling/model-your-app-s-architecture.md)   
 [在開發程序中使用模型](../modeling/use-models-in-your-development-process.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]
