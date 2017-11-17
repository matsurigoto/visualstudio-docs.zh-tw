---
title: "ResourcesGenerator 工作 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- embedding resources into a .resources file [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild]
- ResourcesGenerator task [WPF MSBuild], parameters
ms.assetid: e782bbac-9ee6-472b-8171-3ee008c77b4e
caps.latest.revision: "6"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: aed4b108ad10272579ee5acd43128311003e9ea3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2017
---
# <a name="resourcesgenerator-task"></a>ResourcesGenerator 工作
<xref:Microsoft.Build.Tasks.Windows.ResourcesGenerator> 工作會將一或多種資源 (.jpg、.ico、.bmp、二進位格式的 [!INCLUDE[TLA2#tla_xaml](../msbuild/includes/tla2sharptla_xaml_md.md)] 以及其他副檔名類型) 內嵌到 .resources 檔案。  
  
## <a name="task-parameters"></a>工作參數  
  
|參數|描述|  
|---------------|-----------------|  
|`OutputPath`|必要的 **String** 參數。<br /><br /> 指定輸出目錄的路徑。 如果路徑不是絕對路徑，會將它視為相對於專案根目錄的路徑。|  
|`OutputResourcesFile`|必要的 **ITaskItem[]** 輸出參數。<br /><br /> 指定所產生 .resources 檔案的路徑和名稱。 如果路徑不是絕對路徑，會相對於專案根目錄產生 .resources 檔案。|  
|`ResourcesFiles`|必要的 **ITaskItem[]** 參數。<br /><br /> 指定要內嵌到所產生 .resources 檔案的一或多種資源。|  
  
## <a name="example"></a>範例  
 下列範例會產生使用單一 .bmp 資源的 .resources 檔案。 在相對於專案根目錄的目錄中產生 .bmp 資源。  
  
```xml  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.ResourcesGenerator"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="ResourcesGeneratorTask">  
    <ResourcesGenerator  
      ResourceFiles="Resource1.bmp"  
      OutputPath="myresources"  
      OutputResourcesFile="myresources\my.resources" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>另請參閱  
 [WPF MSBuild 參考](../msbuild/wpf-msbuild-reference.md)   
 [工作參考](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild 參考](../msbuild/msbuild-reference.md)   
 [工作參考](../msbuild/msbuild-task-reference.md)   
 [建置 WPF 應用程式 (WPF)](/dotnet/framework/wpf/app-development/building-a-wpf-application-wpf)