---
title: 偵錯原生程式碼 |Microsoft Docs
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
- vs.debug
dev_langs:
- FSharp
- VB
- CSharp
- C++
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
caps.latest.revision: 24
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9a4c8d5c19ea397f8fc23a962a045645740a1164
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47486096"
---
# <a name="debugging-native-code"></a>偵錯機器碼
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[偵錯原生程式碼](https://docs.microsoft.com/visualstudio/debugger/debugging-native-code)。  
  
本章節內容涵蓋原生應用程式一些常見的偵錯問題和技術。 本章節所涵蓋的技術屬高階技術。 使用 Visual Studio 偵錯工具的機制，請參閱 <<c0> [ 偵錯工具藍圖](../debugger/debugger-basics.md)。  
  
## <a name="in-this-section"></a>本節內容  
 [如何：偵錯最佳化程式碼](../debugger/how-to-debug-optimized-code.md)  
 提供偵錯最佳化程式碼的秘訣，特別說明您應該偵錯非最佳化版本程式的理由、偵錯和發行組態的預設最佳化設定，以及找出只出現在最佳化程式碼中之錯誤的秘訣 (係指在偵錯版組建組態中開啟最佳化)。  
  
 [DebugBreak 和 __debugbreak](../debugger/debugbreak-and-debugbreak.md)  
 說明 Win32 `DebugBreak` 函式，以及提供其在 Platform SDK 中參考主題的連結。 同時也說明 `__debugbreak` 內建函式。  
  
 [C/C++ 判斷提示](../debugger/c-cpp-assertions.md)  
 討論判斷提示陳述式、其作用方式、使用它們的優點 (攔截邏輯錯誤、檢查作業的結果和測試錯誤條件)、與 `_DEBUG` 的互動，以及 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 中所支援的判斷提示類型。  
  
 [如何：偵錯內嵌組譯程式碼](../debugger/how-to-debug-inline-assembly-code.md)  
 提供使用 [反組譯碼] 視窗來檢視組譯碼指示，以及使用 [暫存器視窗] 來檢視暫存器內容的簡短指示，並提供關於這些視窗的主題連結。  
  
 [MFC 偵錯技術](../debugger/mfc-debugging-techniques.md)  
 MFC 程式之偵錯技術的連結，包括：afxDebugBreak、TRACE 巨集、以 MFC 偵測記憶體流失、MFC 判斷提示和減少 MFC 偵錯組建的大小。  
  
 [CRT 偵錯技術](../debugger/crt-debugging-techniques.md)  
 C 執行階段程式庫之偵錯技術的連結，包括使用 CRT 偵錯程式庫、報告巨集、malloc 和 _malloc_dbg 的差異、撰寫偵錯攔截函式和 CRT 偵錯堆積。  
  
 [偵錯機器碼常見問題集](../debugger/debugging-native-code-faqs.md)  
 提供關於偵錯 Visual C++ 程式之常見問題集的解答。  
  
 [偵錯 COM 和 ActiveX](../debugger/com-and-activex-debugging.md)  
 提供偵錯 COM 和 ActiveX 應用程式的詳細資訊，包括您可以用來進行 COM 和 ActiveX 偵錯的工具。  
  
 [如何：偵錯原生 DLL](../debugger/how-to-debug-native-dlls.md)  
 說明如何從機器碼設定 DLL 的偵錯。  
  
 [如何：偵錯插入程式碼](../debugger/how-to-debug-injected-code.md)  
 提供使用屬性 (Attribute) 之程式碼的偵錯指引。 包含如何開啟來源附註、如何檢視插入程式碼，以及如何在目前的執行點上檢視反組譯碼程式碼的指示。  
  
 [逐步解說：偵錯平行應用程式](../debugger/walkthrough-debugging-a-parallel-application.md)  
 描述如何使用**平行工作**並**平行堆疊**工具視窗來偵錯平行應用程式。  
  
## <a name="related-sections"></a>相關章節  
 [Visual C++ 專案類型](../debugger/debugging-preparation-visual-cpp-project-types.md)  
 提供描述如何針對由 Visual C++ 專案範本所建立之原生專案類型進行偵錯的主題連結。  
  
 [Visual Studio 偵錯](../debugger/debugging-in-visual-studio.md)  
 提供偵錯相關文件的主要連結。 這些資訊包括：偵錯工具的新功能、設定和準備、中斷點、例外狀況處理、編輯後繼續、偵錯 Managed 程式碼、偵錯機器碼、偵錯 SQL，以及使用者介面的參考。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯工具安全性](../debugger/debugger-security.md)   
 [Visual Studio 偵錯](../debugger/debugging-in-visual-studio.md)


