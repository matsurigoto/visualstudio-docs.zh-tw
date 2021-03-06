---
title: 舊版語言服務中的自動格式設定 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- language services, automatic formatting
ms.assetid: c210fc94-77bd-4694-b312-045087d8a549
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 46e5f30d01a3063a3683aa3cae4ae1da3e0aa141
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47496595"
---
# <a name="automatic-formatting-in-a-legacy-language-service"></a>舊版語言服務中的自動格式化
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[舊版語言服務中的自動格式化](https://docs.microsoft.com/visualstudio/extensibility/internals/automatic-formatting-in-a-legacy-language-service)。  
  
使用自動格式設定中，語言服務會自動插入程式碼的片段，當使用者開始輸入已知的程式碼建構。  
  
## <a name="automatic-formatting-behavior"></a>自動格式化行為  
 例如，當您輸入`if`、 語言服務會自動插入對稱的括號，或如果您按 ENTER 鍵時，語言服務會強制的插入點在新的一行上的適當縮排層級，取決於是否先前線條會開啟新的範圍。  
  
 使用語言服務的 rest 命令篩選條件可以用於自動格式化。 您也可以藉由呼叫白對稱的括號<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView.HighlightMatchingBrace%2A>。  
  
## <a name="see-also"></a>另請參閱  
 [開發舊版語言服務](../../extensibility/internals/developing-a-legacy-language-service.md)

