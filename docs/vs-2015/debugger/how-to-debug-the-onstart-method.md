---
title: 如何： 偵錯 OnStart 方法 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- OnStart method
- debugging [Visual Studio], Windows services
- debugging managed code, OnStart method
- debugging Windows Services applications, OnStart method
- Windows Service applications, debugging
ms.assetid: b06b5d65-424b-490f-bf58-97583cd7006a
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c2528c99c0f607c3fc98cb8d10e15bfa0c2316f4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47487873"
---
# <a name="how-to-debug-the-onstart-method"></a>如何：偵錯 OnStart 方法
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[如何： 偵錯 OnStart 方法](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-the-onstart-method)。  
  
您可以藉由啟動服務並將偵錯工具附加到服務處理序，對 Windows 服務進行偵錯。 如需詳細資訊，請參閱[如何：偵錯 Windows 服務應用程式](http://msdn.microsoft.com/library/63ab0800-0f05-4f1e-88e6-94c73fd920a2)。 但是若要對 Windows 服務的 <xref:System.ServiceProcess.ServiceBase.OnStart%2A?displayProperty=fullName> 方法進行偵錯，您必須從方法內啟動偵錯工具。  
  
1.  在 <xref:System.Diagnostics.Debugger.Launch%2A> 方法的開頭加入對 `OnStart()`的呼叫。  
  
    ```csharp  
    protected override void OnStart(string[] args)  
    {  
        System.Diagnostics.Debugger.Launch();  
     }  
    ```  
  
2.  啟動服務 (您可以使用 `net start`，或在 [服務]  視窗中加以啟動)。  
  
     您應該會看到如下所示的對話方塊：  
  
     ![OnStartDebug](../debugger/media/onstartdebug.png "OnStartDebug")  
  
3.  選取  **是，偵錯\<服務名稱 >。**  
  
4.  在 [Just-In-Time 偵錯工具] 視窗中，選取您要用來偵錯的 Visual Studio 版本。  
  
     ![JustInTimeDebugger](../debugger/media/justintimedebugger.png "JustInTimeDebugger")  
  
5.  Visual Studio 的新執行個體隨即啟動，並在 `Debugger.Launch()` 方法停止執行。  
  
## <a name="see-also"></a>另請參閱  
 [偵錯工具安全性](../debugger/debugger-security.md)   
 [偵錯 Managed 程式碼](../debugger/debugging-managed-code.md)



