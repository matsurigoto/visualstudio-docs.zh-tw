---
title: 圖形事件呼叫堆疊 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.graphics.callstack
ms.assetid: 8a30168d-8b39-4de1-b094-c7356ba101a3
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d866e63ecffbed5cd5e9a9e477f99fbd8e8c3fc9
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47490486"
---
# <a name="graphics-event-call-stack"></a>圖形事件呼叫堆疊
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[圖形事件呼叫堆疊](https://docs.microsoft.com/visualstudio/debugger/graphics/graphics-event-call-stack)。  
  
Visual Studio 圖形分析器中的圖形事件呼叫堆疊可協助您對應有問題的圖形事件與您應用程式的原始程式碼之間的關聯性。  
  
 這是 [事件呼叫堆疊] 視窗：  
  
 ![呼叫堆疊 DrawIndexed 事件。](../debugger/media/gfx-diag-demo-graphics-event-call-stack-orientation.png "gfx_diag_demo_graphics_event_call_stack_orientation")  
  
## <a name="understanding-the-graphics-event-call-stack"></a>了解圖形事件呼叫堆疊  
 您可以使用 [事件呼叫堆疊] 來了解導致特定 Direct3D 事件的執行流程。 它和 Visual Studio 呼叫堆疊視窗很像，但它不會顯示執行中應用程式中作用中執行緒的目前呼叫堆疊，只會顯示所選取 Direct3D 事件發生時就已存在的呼叫堆疊。 在 [事件呼叫堆疊] 中，您可以跳到所選取 Direct3D 事件的呼叫位置，以檢查周圍的程式碼。  
  
 藉由使用 [事件呼叫堆疊] 來識別問題事件來源的程式碼路徑，您可以運用您的程式碼基底知識來推論問題的可能來源，或者您可以在應用程式的原始程式碼中加入中斷點，讓您可以使用傳統偵錯技術來檢查應用程式或事件參數的狀態如何導致事件行為失常。 這個檢查可以幫助您找出原始程式碼中，只顯示為呈現問題的原始程式碼。  
  
### <a name="graphics-event-call-stack-information"></a>圖形事件呼叫堆疊資訊  
 事件呼叫堆疊不支援畫面格前事件或使用者定義事件。 圖形事件呼叫堆疊會以資料表格式顯示。  
  
|Column|描述|  
|------------|-----------------|  
|**名稱**|特別用來識別含有呼叫位置之函式的符號。 當函式的偵錯符號可用時即會顯示；否則會顯示函式位移。|  
|**檔案**|含有呼叫位置之原始程式檔或程式庫檔案的檔案名稱。|  
|**位置**|呼叫位置的行號。|  
  
### <a name="links-to-graphics-objects"></a>圖形物件連結  
 若要了解所選取的圖形事件，您可能需要與其相關聯之 Direct3D 物件的相關資訊。 **圖形事件呼叫堆疊**視窗提供此資訊的連結。  
  
## <a name="see-also"></a>另請參閱  
 [逐步解說：因端點著色而遺漏的物件](../debugger/walkthrough-missing-objects-due-to-vertex-shading.md)



