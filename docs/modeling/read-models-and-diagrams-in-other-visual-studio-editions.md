---
title: 在其他 Visual Studio 版本中讀取模型和圖表
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- models, versions of Visual Studio
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.openlocfilehash: cfd6188bc4d48f26e85ae8778d75d2fa99ef0f25
ms.sourcegitcommit: ad5fb20f18b23eb8bd2568717f61edc6b7eee5e7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/01/2018
ms.locfileid: "47859675"
---
# <a name="read-models-and-diagrams-in-other-visual-studio-editions"></a>在其他 Visual Studio 版本中讀取模型和圖表
在不支援模型建立的 Visual Studio 版本中開啟模型時，會以唯讀模式開啟模型。 在此模式中，您可以變更圖表的版面配置，但是無法變更模型。

 若要查看哪些版本的 Visual Studio 支援模型建立，請參閱[architecture and modeling tools 的版本支援](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)。

## <a name="obtaining-access-to-a-model-and-diagrams"></a>取得模型和圖表的存取權
 若要讀取的相依性圖表，您必須先使用 Visual Studio 開啟模型專案中，，然後開啟 其內圖表。

 基於這個理由，如果您想要讀取相依性圖表中，您也必須在其中建立模型專案的存取權。 您可以藉由存取 從原始檔控制專案或取得專案檔的複本。

> [!NOTE]
>  這不適用於透過程式碼產生的 Code Map 和 .NET 類別圖。 這些圖表可以與模型專案分開檢視。

 若要讀取的相依性圖表，您需要的檔案的最小集如下所示：

-   兩個圖表檔，例如，想要讀取之圖表**MyDiagram.classdiagram 和 MyDiagram.classdiagram.layout**。

    > [!NOTE]
    >  如需相依性圖表中，您還要有檔案，稱為_MyDiagram_**。 layerdiagram.suppressions**。

-   模型專案檔 (**MyModel.modelproj**)

-   根模型檔 (**ModelDefinition\MyModel.uml**)

-   在圖表中所參考之任何套件的套件檔案 (**ModelDefinition\MyPackage.uml**)

## <a name="changes-that-you-can-make-in-read-only-mode"></a>您可以在唯讀模式中進行的變更
 如果您在不支援模型建立的 Visual Studio 版本中開啟模型和其圖表，則無法變更模型。 也就是說，您無法變更圖表或模型總管中所顯示的項目和關聯性。 不過，您可以對圖表的版面配置進行一些變更：

-   重新排列圖表上的圖形和連接器。

-   展開和摺疊圖形。

 您可以儲存這些變更。 如果您想要讓您變更其他使用者看到，您必須至少傳送更新過 **.layout**檔案。

## <a name="RelatedTopics"></a> 相關的主題

|標題|描述|
|-----------|-----------------|
|[相依性圖表︰參考](../modeling/layer-diagrams-reference.md)|分層圖會顯示現有或提議之架構的結構。 撰寫程式碼時，可以針對分層圖自動進行驗證。|

## <a name="see-also"></a>另請參閱

- [建立應用程式模型](../modeling/create-models-for-your-app.md)