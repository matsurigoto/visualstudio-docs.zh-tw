---
title: 網路使用量 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45fa397d-d7a1-4c4c-9c97-ede6c21643bd
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e324f81d4f7580a25f0f2b5c1850c1343a85c6ac
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47491456"
---
# <a name="network-usage"></a>網路使用量
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[UWP 應用程式，在 Visual Studio 中分析網路使用量](https://docs.microsoft.com/visualstudio/profiling/network-usage)。  
  
Visual Studio 的 [網路] 診斷工具會收集使用 [Windows.Web.Http 應用程式開發介面](https://msdn.microsoft.com/library/windows/apps/windows.web.http.aspx)執行之網路作業的相關資料。 分析這份資料可協助您解決存取和驗證、不正確的快取使用，以及顯示和下載效能不佳等問題。  
  
 網路工具僅支援 Windows 通用平台應用程式。 目前不支援其他平台。  
  
> [!NOTE]
>  如需更多完整的網路工具描述，請參閱[介紹 Visual Studio 的網路工具](http://blogs.msdn.com/b/visualstudio/archive/2015/05/04/introducing-visual-studio-s-network-tool.aspx)。  
  
## <a name="collecting-network-tool-data"></a>收集網路工具資料  
 您應該針對 Visual Studio 電腦上開啟的 Visual Studio 專案執行 [網路] 工具。  
  
1.  在 Visual Studio 中開啟專案。  
  
2.  在功能表上，按一下 [偵錯/效能分析工具]。選擇 [網路]，然後選擇 [啟動]。  
  
3.  網路工具會開始收集您應用程式的 HTTP 流量。  
  
     執行應用程式時，在左窗格中的摘要檢視會自動顯示擷取的 HTTP 作業清單。 在摘要檢視上選取項目，來檢視在右窗格詳細資料面板中的詳細資訊。  
  
4.  選擇 [停止] 以關閉應用程式。  
  
 報表視窗看起來應該類似這樣：  
  
 ![[網路] 視窗](../profiling/media/network-fullwindow.png "NETWORK_FullWindow")  
  
## <a name="analyzing-data"></a>分析資料  
 無論您的應用程式正在執行，或甚至在關閉之後，透過選取任何顯示在摘要檢視上的網路作業，即可分析擷取的 HTTP 流量。  
  
 [網路] 摘要清單顯示執行應用程式時的每個網路作業資料。 選擇資料行標頭以排序清單，或選擇要顯示在 [內容類型] 篩選檢視中的內容類型。  
  
 選擇 [另存為 HAR] 以建立可供 Fiddler 等協力廠商工具使用的 JSON 檔案。  
  
 [網路] 詳細資料檢視在摘要檢視中顯示更多網路作業的相關資訊。  
  
 ![網路工具詳細資料窗格](../profiling/media/network-detailsviewpane.png "NETWORK_DetailsViewPane")  
  
|||  
|-|-|  
|**標頭**|事件的要求標頭資訊。|  
|**本文**|要求和回應承載資料。|  
|**參數**|查詢字串參數名稱和值。|  
|**Cookie**|回應和要求 Cookie 資料。|  
|**計時**|取得所選資源的各階段圖表。|  
  
 網路 [摘要] 列會顯示在任何給定的時間點、傳輸資料量、下載所花費時間，以及可見的錯誤數目 (4xx 或 5xx 回應的要求) 的網路作業數。  
  
### <a name="analysis-tips"></a>分析秘訣  
 此工具會反白顯示特定區域，有助您執行網路相關的分析：  
  
1.  完全來自快取的要求會在 [已接收] 資料行中顯示為 [(從快取)]。 這可協助判斷您是否有效率地使用快取來節省使用者頻寬，或您是否意外地快取回應且提供具過時資料的應用程式給使用者。  
  
2.  錯誤回應 (4xx 或 5xx) 會顯示在 [結果] 資料行中，並具有紅色狀態程式碼，同時也會在摘要列中反白顯示。 這樣可以在應用程式上許多潛在的要求之間輕易發現錯誤。  
  
3.  回應美化顯示按鈕 (在主體索引標籤內) 可協助您藉由增加內容可讀性來剖析 JSON、XML、HTML、CSS、JavaScript 和 TypeScript 的回應裝載。  
  
## <a name="see-also"></a>另請參閱  
 [執行但不偵錯程式碼剖析工具](http://msdn.microsoft.com/library/e97ce1a4-62d6-4b8e-a2f7-61576437ff01)   
 [Visual Studio 部落格： 介紹 Visual Studio 的網路偵測器](http://go.microsoft.com/fwlink/?LinkId=535022)   
 [Channel 9 影片︰ VS 診斷工具 - 新的網路分析工具 (英文)](http://channel9.msdn.com/Series/ConnectOn-Demand/206)



