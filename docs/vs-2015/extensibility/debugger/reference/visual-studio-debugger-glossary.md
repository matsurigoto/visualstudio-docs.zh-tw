---
title: Visual Studio 偵錯工具字彙 |Microsoft Docs
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
- glossary [Debugging SDK]
- debugging [Debugging SDK], glossary
ms.assetid: 4a2cfaab-1fbd-4a23-bd00-9ac4cc50d7fd
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: da2b0d2c435cbfc0bca19977074a7b54e8de6315
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47490875"
---
# <a name="visual-studio-debugger-glossary"></a>Visual Studio 偵錯工具字彙
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

本主題的最新的版本可從[Visual Studio 偵錯工具字彙](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/visual-studio-debugger-glossary)。  
  
以下是中使用的詞彙[!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)]偵錯 sdk 》。  
  
## <a name="terms"></a>詞彙  
 繫結的中斷點  
 程式碼中設定中斷點的抽象概念。 沒有繫結的中斷點和中斷點中的指令碼資料流之間的一對一關聯性。 程式碼卸載時，繫結的中斷點可能會解除繫結。  
  
 因果關係  
 可讓您跨多個實體的執行緒、 處理序和機器，追蹤執行的邏輯執行緒，並在該執行緒的存留期間重建該邏輯的執行緒，在任何指定的時間點的呼叫堆疊。  
  
 程式碼內容  
 提供抽象的已知的偵錯引擎的程式碼中的位置。 適用於大部分的執行階段架構程式碼內容會是該應用程式的指令資料流中的位址。 對於非傳統任務為語言，在其中的程式碼可能無法表示的指示，程式碼內容都可以透過其他方式來表示。  
  
 程式碼路徑  
 表示程式碼，採用的分支，或函式呼叫中執行的點。 堆疊追蹤是基本上是清單的函式呼叫的程式碼路徑。  
  
 偵錯引擎 (DE)  
 允許偵錯執行階段架構的元件。 偵錯引擎和解譯器或作業系統一起工作，並提供偵錯的服務，例如執行控制、 中斷點、 和運算式評估。  
  
 文件內容  
 提供抽象的來源檔案的文件，已知的偵錯引擎中的位置。 對於大部分的語言，文件內容會是原始程式檔中的位置。 對於非傳統任務為語言，為其來源檔案可能不是文字，文件內容可能會以其他方式。 另請參閱*文件位置*。  
  
 文件位置  
 提供抽象的原始程式檔，已知在 IDE 中的位置。 對於大部分的語言，文件位置會是原始程式檔中的位置。 如需非傳統任務為語言，文件位置可能會表示以其他方式。 另請參閱*文件內容*。  
  
 錯誤的中斷點  
 描述在暫止中斷點錯誤抽象概念。 錯誤中斷點可能說明暫止的中斷點暫止的中斷點或防止繫結中的暫止的中斷點，程式碼位置的其他資訊相關聯的運算式的位置中的錯誤。  
  
 評估內容  
 運算式評估，提供程式設計內容的抽象概念。 一般而言，評估內容是一個範圍。 運算式內容中的評估運算式時，運算式的內容會提供符合其建立的時間範圍規則。 比方說，在堆疊框架中建立的運算式內容將提供的內容，來評估區域變數、 方法參數、 類別成員 （如果適用） 和全域變數。  
  
 攔截到例外狀況  
 即使沒有例外狀況處理機制是在目前的堆疊框架中的位置，會將偵錯引擎所攔截的例外狀況。  
  
 JustMyCode  
 偵錯只屬於使用者程式碼，並忽略所有的中繼程式碼，例如系統程式碼的概念，即使原始程式碼是適用於該系統程式碼。  
  
 暫止中斷點  
 提供抽象方法的中斷點之前、 期間和之後的程式碼會載入，而且虛擬化中斷點的方式。 暫止的中斷點：  
  
-   包含將中斷點繫結至一個或多個程式中的程式碼所需的所有資訊。  
  
-   可以繫結到一或多個程式中的多個程式碼位置。  
  
-   永遠不會繫結到程式碼。  
  
 每次程式碼會載入，在程式中的所有暫止中斷點會檢查以查看它們可以繫結。 暫止中斷點即為包含所有繫結的繫結的中斷點。  
  
 處理序  
 實體的 「 Win32 處理程序。 處理程序可以包含多個程式。 另請參閱*程式*。  
  
 程式  
 單一的命名空間，在特定的執行階段架構內執行。 另請參閱*程序*。  
  
 工作階段偵錯管理員 (SDM)  
 管理任何數目的任意數目的任意數目的機器上的多個處理程序中的程式進行偵錯的偵錯引擎。 在基本層級，SDM 是多工器的偵錯引擎。 此外，在 SDM 提供 IDE 偵錯工作階段的統一的檢視。  
  
 堆疊框架  
 表示在特定畫面格的計算的狀態和特定的層級的巢狀函式呼叫。  
  
 thread  
 在至少一個程式中執行的堆疊為基礎的指令執行通用的概念。  
  
 警告中斷點  
 描述在暫止中斷點的警告抽象概念。 警告中斷點描述為何暫止中斷點具有尚未繫結至程式碼位置的原因。 這可能是，程式碼未載入尚未暫止的中斷點，所描述的位置，或因其他原因。  
  
## <a name="see-also"></a>另請參閱  
 [Visual Studio 偵錯工具的擴充性](../../../extensibility/debugger/visual-studio-debugger-extensibility.md)
