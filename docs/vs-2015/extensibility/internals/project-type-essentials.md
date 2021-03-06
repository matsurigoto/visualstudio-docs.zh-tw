---
title: 專案類型的基本資訊 |Microsoft Docs
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
- project types [Visual Studio SDK]
ms.assetid: 09991589-2300-430e-b6a4-7f2b95fe676f
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: dd2c0db72cce80f5345475dfd7e82b019b0ec22a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47496571"
---
# <a name="project-type-essentials"></a>專案類型的基本資訊
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[專案類型的基本資訊](https://docs.microsoft.com/visualstudio/extensibility/internals/project-type-essentials)。  
  
[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 包含語言的數種專案類型，例如[!INCLUDE[csprcs](../../includes/csprcs-md.md)]或[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 也可讓您建立您自己的專案類型。  
  
 如果您只想要新增自訂命令、 編輯器或工具視窗， [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]，您不必建立新的專案類型。 如需詳細資訊，請參閱下列主題：  
  
-   [命令、功能表及工具列](../../extensibility/internals/commands-menus-and-toolbars.md)  
  
-   [編輯器和語言服務擴充功能](../../extensibility/editor-and-language-service-extensions.md)  
  
-   [擴充和自訂工具視窗](../../extensibility/extending-and-customizing-tool-windows.md)  
  
 同樣地，如果您想要自訂所提供的行為[!INCLUDE[csprcs](../../includes/csprcs-md.md)]和[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]專案類型中，您可以使用專案子類型。 如需詳細資訊，請參閱 <<c0> [ 專案子類型](../../extensibility/internals/project-subtypes.md)。  
  
 您必須建立新的專案類型，會根據語言以外的專案[!INCLUDE[csprcs](../../includes/csprcs-md.md)]和[!INCLUDE[vbprvb](../../includes/vbprvb-md.md)]如果您想要支援的一或多個項目：  
  
-   組建  
  
-   部署  
  
-   多個組態  
  
-   原始檔控制  
  
-   偵錯  
  
-   在 [方案總管] 中的專案項目  
  
-   **開啟專案**或是**新的專案**對話方塊  
  
-   專案的巢狀結構  
  
-   如需詳細的專案類型功能的相關資訊，請參閱下列各項：  
  
-   專案類型是在 VSPackage 中實作的介面集合的物件[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]預期。 如果您使用 C# 來開發專案類型，Managed Package Framework 專案類別會為您實作必要的介面，並可讓您繼承該實作。 如需詳細資訊，請參閱 <<c0> [ 使用 Managed Package Framework 實作專案類型 (C#)](../../extensibility/internals/using-the-managed-package-framework-to-implement-a-project-type-csharp.md)。  
  
-   適用於 c + + 開發人員，HierUtil 文件庫中的類別會以類似的方式運作。 如需詳細資訊，請參閱 <<c0> [ 不在組建中： 使用 HierUtil7 專案類別以實作專案類型 （c + +）](http://msdn.microsoft.com/en-us/a5c16a09-94a2-46ef-87b5-35b815e2f346)。  
  
-   專案類型可支援典型的原始檔建置為.exe 或.dll 的組件的程式碼檔案以外的資料。 例如，[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]資料庫專案包含指令碼，並查詢儲存在磁碟上的檔案的參考，並將命令加入至**方案總管 中**執行指令碼和查詢資料庫，但專案不支援建置行為。 如需詳細資訊，請參閱 <<c0> [ 開啟和儲存專案項目](../../extensibility/internals/opening-and-saving-project-items.md)。  
  
-   若要使用的檔案沒有專案類型。 比方說，專案類型可以儲存在資料庫中的所有資料。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 可讓專案類型完全控制它們將專案和專案項目資料的保存。 如需詳細資訊，請參閱 <<c0> [ 專案類型的設計決策](../../extensibility/internals/project-type-design-decisions.md)。  
  
-   專案類型必須提供*project factory*，這是建立專案的執行個體的物件輸入每當[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]告訴開啟或建立該專案類型為基礎的專案。 如需詳細資訊，請參閱 <<c0> [ 建立專案執行個體所使用 Project Factory](../../extensibility/internals/creating-project-instances-by-using-project-factories.md)。  
  
-   專案類型必須提供專案和專案項目範本。 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 當使用者建立新的專案，並將新的項目新增至現有的專案，請使用範本。 如需詳細資訊，請參閱 <<c0> [ 加入專案和專案項目範本](../../extensibility/internals/adding-project-and-project-item-templates.md)。  
  
-   專案類型可支援多個組態，例如偵錯和發行。 使用者可以使用您提供的屬性頁來變更專案的不同的組態。 如需詳細資訊，請參閱 <<c0> [ 管理組態選項](../../extensibility/internals/managing-configuration-options.md)。  
  
## <a name="see-also"></a>另請參閱  
 [部署專案類型](../../extensibility/internals/deploying-project-types.md)

