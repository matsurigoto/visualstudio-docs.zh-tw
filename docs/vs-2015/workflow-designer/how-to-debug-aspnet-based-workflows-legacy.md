---
title: 如何： 偵錯 ASP.NET 為基礎的工作流程 （舊版） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: .net-framework-4.6
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- ASP.NET, debugging workflows
- debugging workflows, ASP.NET workflows
- ASP.NET workflows, debugging
- debugging, ASP.NET workflows
ms.assetid: 79b21edc-9e7d-410d-af68-09c1598b9c30
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: erikre
ms.openlocfilehash: d30cb54ea035dfac63cf3ab4761c2c7cb5376314
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47492261"
---
# <a name="how-to-debug-aspnet-based-workflows-legacy"></a>HOW TO：ASP.NET 工作流程偵錯 (舊版)
本主題描述如何在舊版 [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] 中偵錯 [!INCLUDE[wf](../includes/wf-md.md)] 型 [!INCLUDE[netfx35_long](../includes/netfx35-long-md.md)] 應用程式，該應用程式是以 [!INCLUDE[vstecwinfx](../includes/vstecwinfx-md.md)] 或 [!INCLUDE[wfd1](../includes/wfd1-md.md)] 為目標。  
  
 您可以針對在 ASP.NET 中啟動的舊版工作流程，或是藉由附加至裝載工作流程的處理序而發行為 Web 服務的舊版工作流程進行偵錯。  
  
### <a name="to-debug-an-aspnet-based-workflow"></a>若要偵錯 ASP.NET 工作流程  
  
1.  啟用偵錯 ASP.NET 應用程式，藉由設定**偵錯 = true** web.config 檔案中。  
  
2.  將工作流程程式庫設為啟始專案，並在工作流程中設定中斷點。  
  
3.  在 工作流程專案屬性中輸入預設網頁的 URL**偵錯**選項**外部 URL 啟動瀏覽器**文字方塊。  
  
4.  選取  **připojit k procesu**上**偵錯**功能表。  
  
5.  選取要附加至處理序**可用的處理序**清單。  
  
     附加至裝載工作流程的 w3wp.exe、webdev.webserver 或 aspnet_wp 處理序。  
  
6.  按一下 **選取 **旁**附加至**文字方塊。  
  
     **選取程式碼類型** 對話方塊隨即出現。  
  
7.  選取 **偵錯這些程式碼類型**，然後選取**工作流程**。  
  
8.  按一下 [確定 **Deploying Office Solutions**]。  
  
9. 按一下 [附加] 。  
  
10. 在瀏覽器中開啟預設網頁，並啟動工作流程。  
  
## <a name="see-also"></a>另請參閱  
 [叫用 Visual Studio Debugger for Windows Workflow Foundation （舊版）](../workflow-designer/invoking-the-visual-studio-debugger-for-windows-workflow-foundation-legacy.md)   
 [如何： 在工作流程 （舊版） 中設定中斷點](../workflow-designer/how-to-set-breakpoints-in-workflows-legacy.md)   
 [偵錯舊版工作流程](../workflow-designer/debugging-legacy-workflows.md)