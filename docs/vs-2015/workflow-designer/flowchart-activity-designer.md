---
title: Flowchart 活動設計工具 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- System.Activities.Statements.Flowchart.UI
- System.Activities.Statements.FlowStep.UI
- System.Activities.Core.Presentation.FlowStart.UI
ms.assetid: d5af2276-5215-4138-880a-cf2b90bbf3a0
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: 1fb9c6493390b0f489b2afaf27dc0293748c70a6
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47492056"
---
# <a name="flowchart-activity-designer"></a>Flowchart 活動設計工具
<xref:System.Activities.Statements.Flowchart> 活動會用來建立工作流程，這些工作流程可定義及管理複雜的流程控制。 <xref:System.Activities.Statements.Flowchart> 可以利用程式碼或使用 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 製作。 這個主題提供 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 體驗的說明文件。 [!INCLUDE[wfd1](../includes/wfd1-md.md)] 工作流程活動設計工具可供開發人員以自然的方式製作工作流程。  
  
## <a name="the-flowchart-activity"></a>Flowchart 活動  
 <xref:System.Activities.Statements.Flowchart> 指定工作流程開始時會執行的唯一 <xref:System.Activities.Statements.Flowchart.StartNode%2A>，並且使用已連結 <xref:System.Activities.Statements.Flowchart.Nodes%2A> 的網路來建立任意迴圈，或是在任何特定時間將執行的流動轉向任何其他地方。  
  
### <a name="using-the-flowchart-activity-designer"></a>使用 Flowchart 活動設計工具  
 **流程圖**活動設計工具位於**流程圖**類別**工具箱**，即可存取的哪一個**工具箱**索引標籤上[!INCLUDE[wfd2](../includes/wfd2-md.md)](或者，選取**工具列**從**檢視**功能表或 CTRL + ALT + X。)  
  
 **流程圖**活動設計工具可以從拖曳**工具箱**，放入[!INCLUDE[wfd2](../includes/wfd2-md.md)]介面只要活動設計工具通常用來放置，做為根活動，或是當做子系另一個控制流程活動。 如果**流程圖**活動設計工具放到空白[!INCLUDE[wfd2](../includes/wfd2-md.md)]介面，它會建立<xref:System.Activities.Statements.Flowchart>活動，這預設會初始化執行 [啟動] 節點的展開檢視以綠色球形代表。 如果**流程圖**活動設計工具拖放至另一個控制流程活動，它會將本身的最小化的檢視，可按兩下進行擴充以呈現**流程圖**活動設計工具。 中的任何活動**工具箱**可以直接拖曳**流程圖**活動設計工具，包括其他控制流程活動。  
  
 將多種不同的活動設計工具拖曳到 [!INCLUDE[wfd2](../includes/wfd2-md.md)] 畫布上之後，設計工具代表的 <xref:System.Activities.Activity> 物件可以連結在一起，用來指定執行的順序。 若要建立來源活動與目的地活動之間的連結，請將滑鼠游標移至來源活動的設計工具上，設計工具的每一邊就會出現方形控點。 按一下方形控點，按住滑鼠按鈕，拖曳到目的地活動周圍的其中一個控點，亦即將滑鼠游標移至目的地活動上時同樣會出現的幾個控點之一。 放開滑鼠按鈕，這兩個活動之間就會建立連結，此連結會以箭號表示，從來源設計工具指向目的地設計工具。  
  
### <a name="flowchart-activity-properties"></a>Flowchart 活動屬性  
 下表顯示 <xref:System.Activities.Statements.Flowchart> 屬性，並且描述屬性在設計工具中的使用方式。 這些屬性可以在屬性方格中或在設計工具介面上編輯。  
  
|屬性名稱|必要項|使用方式|  
|-------------------|--------------|-----------|  
|<xref:System.Activities.Activity.DisplayName%2A>|False|指定活動設計工具在標頭中的顯示名稱。 預設值為 Flowchart。 值可以在中編輯**屬性**視窗或直接在活動設計工具標頭。<br /><br /> 雖然 <xref:System.Activities.Activity.DisplayName%2A> 並非絕對必要，但建議您盡量使用。|  
|<xref:System.Activities.Statements.Flowchart.Variables%2A>|False|設定至這個 <xref:System.Activities.Statements.Flowchart> 的範圍內，使其子活動都有共同狀態之變數的集合。|  
|<xref:System.Activities.Statements.Flowchart.StartNode%2A>|False|在 <xref:System.Activities.Statements.FlowNode> 開始時執行的 <xref:System.Activities.Statements.Flowchart>。|  
|<xref:System.Activities.Statements.Flowchart.Nodes%2A>|False|包含 <xref:System.Activities.Statements.FlowNode> 中 <xref:System.Activities.Statements.Flowchart> 物件的集合。|  
  
## <a name="see-also"></a>另請參閱  
 [流程圖](../workflow-designer/flowchart-activity-designers.md)   
 [FlowDecision](../workflow-designer/flowdecision-activity-designer.md)   
 [FlowSwitch\<T >](../workflow-designer/flowswitch-t-activity-designer.md)