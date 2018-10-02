---
title: 著色器設計工具節點 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f5192fbd-c78f-40a8-a4d4-443209610268
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f718faebef46308cf74847f75b3a05cd12386704
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47490636"
---
# <a name="shader-designer-nodes"></a>著色器設計工具節點
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[著色器設計工具節點](https://docs.microsoft.com/visualstudio/designers/shader-designer-nodes)。  
  
文件這節中的文章包含可用來建立圖形效果之各種著色器設計工具節點的資訊。  
  
## <a name="nodes-and-node-types"></a>節點和節點類型  
 著色器設計工具會以圖形呈現視覺效果。 這些圖形是透過節點所建置，而這些節點是特別選擇並以精確方式連線，來達到預期的效果。 每個節點都代表資訊片段或數學函式，而其間的連線代表資訊如何流經圖表來產生結果。 著色器設計工具提供六種不同的節點類型 (篩選、紋理節點、參數、常數、公用程式節點和數學節點) 以及數個屬於每種類型的個別節點。 本節的其他文章會詳述這些節點和節點類型；請參閱本文件結尾的連結。  
  
## <a name="node-structure"></a>節點結構  
 所有節點都是由通用項目組合所構成。 每個節點在其右側都至少有一個輸出終端機 (代表著色器輸出的最終色彩節點除外)。 代表計算或紋理取樣器的節點在其左側會有輸入終端機，但代表資訊的節點沒有任何輸入終端機。 輸出終端機會連線至輸入終端機，以將資訊從某個節點移至另一個節點。  
  
### <a name="promotion-of-inputs"></a>輸入的提升  
 因為著色器設計工具最終必須產生 HLSL 原始程式碼，以在遊戲或應用程式中使用效果，所以著色器設計工具節點受限於 HLSL 所使用的類型提升規則。 因為圖形硬體主要作用於浮點值，所以不同類型之間的類型提升 (例如，從 `int` 到 `float` 或從 `float` 到 `double`) 並不常見。 相反地，因為圖形硬體同時對多個資訊片段使用相同的作業，所以在較短的輸入數目加長以符合最長輸入大小時進行不同類型的提升。 加長方式取決於輸入類型和運算本身：  
  
-   **如果較小的類型是純量值，則：**  
  
     純量值會複寫至大小等於較大輸入的向量。 例如，不論運算為何，在最大運算輸入是三項目向量時，純量輸入 5.0 會變成向量 (5.0, 5.0, 5.0)。  
  
-   **如果較小的類型是向量，而且運算是乘法 (\*、/、% 等等)，則：**  
  
     向量的值會複製至大小等於較大輸入之向量的前置項目，而且尾端項目設為 1.0。 例如，向量輸入 (5.0, 5.0) 乘上四項目向量時，會變成向量 (5.0, 5.0, 1.0, 1.0)。 這會使用乘法單位 1.0 保留輸出的第三個和第四個項目。  
  
-   **如果較小的類型是向量，而且運算是加法 (+、- 等等)，則：**  
  
     向量的值會複製至大小等於較大輸入之向量的前置項目，而且尾端項目設為 0.0。 例如，向量輸入 (5.0, 5.0) 加上四項目向量時，會變成向量 (5.0, 5.0, 0.0, 0.0)。 這會使用加法單位 0.0 保留輸出的第三個和第四個項目。  
  
## <a name="related-topics"></a>相關主題  
  
|標題|描述|  
|-----------|-----------------|  
|[常數節點](../designers/constant-nodes.md)|描述您可用來代表著色器計算之常值和插補頂點狀態資訊的節點。 因為插入頂點狀態 (因此，每個像素都會不同)，所以每個像素著色器執行個體都會收到不同版本的常數。|  
|[參數節點](../designers/parameter-nodes.md)|所描述的節點可以用來代表著色器計算中的觀景窗位置、材質屬性、光源參數、時間以及其他應用程式狀態資訊。|  
|[紋理節點](../designers/texture-nodes.md)|所描述的節點可用來對各種紋理類型和幾何形狀取樣，並以一般方式產生或轉換紋理座標。|  
|[數學節點](../designers/math-nodes.md)|所描述的節點可用來執行代數、邏輯、三角，以及直接對應至 HLSL 指令的其他數學運算。|  
|[公用程式節點](../designers/utility-nodes.md)|所描述的節點可用來執行常見光源計算，以及未直接對應至 HLSL 指令的其他常見運算。|  
|[篩選節點](../designers/filter-nodes.md)|所描述的節點可用來執行紋理篩選和色彩篩選。|


