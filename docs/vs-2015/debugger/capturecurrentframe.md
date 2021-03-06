---
title: CaptureCurrentFrame |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4509311d-6fe2-4b65-9b4a-ff0522585d6a
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2fcb05d63370f8f40ab09f0978e0f49dbe7d6a3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47491871"
---
# <a name="capturecurrentframe"></a>CaptureCurrentFrame
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[CaptureCurrentFrame](https://docs.microsoft.com/visualstudio/debugger/graphics/capturecurrentframe)。  
  
擷取目前畫面的圖形記錄檔的其餘部分。  
  
## <a name="syntax"></a>語法  
  
```cpp  
void CaptureCurrentFrame();  
```  
  
## <a name="remarks"></a>備註  
 如果另一個擷取目前正在進行中，例如擷取所啟動的`BeginCapture`函式，該擷取會完成，且會記錄到圖形記錄檔，做為不同的框架。 立即之後，圖形診斷會開始擷取目前的框架，也會記錄為不同的畫面格的其餘部分。 目前的框架結束是由呼叫呈現標記。  
  
 若要擷取的畫面格，您必須準備您的應用程式，來擷取和記錄的圖形資訊 — 也就是您必須先呼叫[Init](../debugger/init.md)的執行個體透過`VsgDbg`類別在呼叫之前`CaptureCurrentFrame`。  
  
## <a name="see-also"></a>另請參閱  
 [Init](../debugger/init.md)   
 [BeginCapture](../debugger/begincapture.md)



