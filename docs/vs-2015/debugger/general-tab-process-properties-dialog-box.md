---
title: 一般索引標籤上，處理序屬性對話方塊 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Process properties for Windows NT
ms.assetid: 86f4d61d-a594-4aac-8960-c5279b4a10fd
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5043d5250c6ce26807379d6cef25077480dbc344
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47498579"
---
# <a name="general-tab-process-properties-dialog-box"></a>處理序屬性對話方塊、一般索引標籤
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[一般索引標籤、 處理序屬性對話方塊](https://docs.microsoft.com/visualstudio/debugger/general-tab-process-properties-dialog-box)。  
  
使用**一般**索引標籤，以深入了解特定的處理程序。 若要顯示[處理序屬性對話方塊](../debugger/process-properties-dialog-box.md)，焦點移至[處理序檢視](../debugger/processes-view.md)視窗。 在樹狀目錄中，選取任何處理序節點，然後選擇**屬性**從**檢視**功能表。  
  
 下列設定位於**一般** 索引標籤：  
  
|進入|描述|  
|-----------|-----------------|  
|**模組名稱**|模組的名稱。|  
|**處理序 ID**|此程序的唯一識別碼。 重複使用處理序識別碼，因此它們只會針對該程序的存留期識別處理程序。 當程式執行時，會建立處理程序物件類型。 處理序中的所有執行緒共用相同的位址空間，而且可以存取相同的資料。|  
|**優先權基底**|此程序目前的基礎優先權。 在處理序中的執行緒可以引發，並降低其自己的基礎優先權，相對於處理程序的基本優先順序。|  
|**執行緒**|目前使用此程序中的執行緒數目。|  
|**CPU 時間**|在此程序和其執行緒所花費的總 CPU 時間。 等於使用者時間加上特殊權限的時間。|  
|**使用者時間**|此程序的執行緒，所執行的程式碼在使用者模式下非閒置執行緒的累計耗用時間。 子系統，例如 「 視窗管理員 」 和圖形引擎一樣，應用程式會執行使用者模式中。|  
|**特殊權限的時間**|總耗用時間此程序具有執行在特權模式下非閒置執行緒中。 服務層、 高階主管常式和核心會在特殊權限模式下執行。 適用於大部分裝置以外的圖形介面卡和印表機的裝置驅動程式也會執行特殊權限的模式。 某些工作，Windows 會為您的應用程式可能會出現在其他子系統處理序，除了具有特殊權限的時間。|  
|**已耗用時間**|總耗用時間已執行此程序。|



