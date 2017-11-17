---
title: "管理應用程式資源 (.NET) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- msvse_resedit.dlg.SetCustomTool
- msvse_settingsdesigner.err.formatvalue
- msvse_resedit.err.nameblank
- msvse_resedit.err.duplicatename
helpviewer_keywords:
- editors [Visual Studio], Resource Designer
- Resource Designer
- resources [Visual Studio], managing
- Resources page in Project Designer
- resources types, Resource Designer
- application resources [Visual Studio]
- Project Designer, Resources page
ms.assetid: f2582734-8ada-4baa-8a7c-e2ef943ddf7e
caps.latest.revision: 20
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Human Translation
ms.sourcegitcommit: 3d32d11a430227800cb3ed53831a9565eb6adeb3
ms.openlocfilehash: 5cb2e044f5c55881adade6d3022fc453360a2e9c
ms.contentlocale: zh-tw
ms.lasthandoff: 05/30/2017

---
# 管理應用程式資源 (.NET)
<a id="managing-application-resources-net" class="xliff"></a>
資源檔案是屬於應用程式的一部分，但不會經過編譯的檔案，例如圖示檔案或音訊檔案。 由於這些檔案不屬於編譯處理程序的一部分，您可以變更它們而無需重新編譯二進位檔。 如果您打算將應用程式當地語系化，您應該針對所有字串和其他在將應用程式當地語系化時需要變更的資源使用資源檔。  
  
 如需 .NET 桌面應用程式中資源的詳細資訊，請參閱[桌面應用程式中的資源](/dotnet/framework/resources/index)。 如需 C++ 桌面應用程式中的資源的詳細資訊，請參閱 [Working with Resource Files](/cpp/windows/working-with-resource-files)。  
  
 Windows 市集應用程式使用的資源模型與桌面應用程式不同。 如需 Windows 市集應用程式中的資源的相關資訊，請參閱 Windows 開發人員中心網站上的 [定義應用程式資源](https://msdn.microsoft.com/en-us/library/windows/apps/hh465228.aspx) 。  
  
## 使用資源
<a id="working-with-resources" class="xliff"></a>  
 在 managed 程式碼專案中，開啟 專案屬性 視窗 (以滑鼠右鍵按一下專案節點中的 **方案總管 中** ，然後選取 **屬性**, ，或類型 **專案屬性** 中 **快速啟動**  視窗中，或輸入 ALT + ENTER 在 **方案總管 中** 視窗)。 選取 **資源**  索引標籤。 您可以在專案尚未包含 .resx 檔案的情況下加入 .resx 檔案、加入和刪除不同種類的資源，以及修改現有的資源。  
  
 若要了解如何在 C++ 專案中使用資源，請參閱[如何：建立資源](/cpp/windows/how-to-create-a-resource)。