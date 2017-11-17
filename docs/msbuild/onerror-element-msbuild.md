---
title: "OnError 元素 (MSBuild) | Microsoft Docs"
ms.custom: 
ms.date: 03/13/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/developer/msbuild/2003#OnError
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- OnError Element [MSBuild]
- <OnError Element [MSBuild]
ms.assetid: 765767d3-ecb7-4cd9-ba1e-d9468964dddc
caps.latest.revision: "14"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: 1c0238bb7a525166f69a59b0af5d08db5286a5f8
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/31/2017
---
# <a name="onerror-element-msbuild"></a>OnError 項目 (MSBuild)
如果失敗工作的 `ContinueOnError` 屬性是 `false`，則會執行一或多個目標。  

 \<Project>  
 \<Target>  
 \<OnError>  

## <a name="syntax"></a>語法  

```  
<OnError ExecuteTargets="TargetName"  
    Condition="'String A'=='String B'" />  
```  

## <a name="attributes-and-elements"></a>屬性和項目  
 下列章節說明屬性、子項目和父項目。  

### <a name="attributes"></a>屬性  

|屬性|描述|  
|---------------|-----------------|  
|`Condition`|選擇性屬性。<br /><br /> 要評估的條件。 如需詳細資訊，請參閱[條件](../msbuild/msbuild-conditions.md)。|  
|`ExecuteTargets`|必要屬性。<br /><br /> 工作失敗時要執行的目標。 以分號分隔多個目標。 多個目標會以指定的順序執行。|  

### <a name="child-elements"></a>子項目  
 無。  

### <a name="parent-elements"></a>父項目  

|項目|說明|  
|-------------|-----------------|  
|[Target](../msbuild/target-element-msbuild.md)|[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 工作的容器元素。|  

## <a name="remarks"></a>備註  
 如果其中一個 `Target` 元素的工作失敗，且 `ContinueOnError` 屬性設為 `ErrorAndStop` (或 `false`)，[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 便會執行 `OnError` 元素。 工作失敗時，便會執行 `ExecuteTargets` 屬性指定的目標。 如果目標中有多個 `OnError` 元素，則工作失敗時會依序執行 `OnError` 元素。  

 如需 `ContinueOnError` 屬性的相關資訊，請參閱 [Task 項目 (MSBuild)](../msbuild/task-element-msbuild.md)。 如需目標的詳細資訊，請參閱[目標](../msbuild/msbuild-targets.md)。  

## <a name="example"></a>範例  
 下列程式碼會執行 `TaskOne` 和 `TaskTwo` 工作。 如果 `TaskOne` 失敗，[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 會評估 `OnError` 元素，並執行 `OtherTarget` 目標。  

```xml  
<Target Name="ThisTarget">  
    <TaskOne ContinueOnError="ErrorAndStop">  
    </TaskOne>  
    <TaskTwo>  
    </TaskTwo>  
    <OnError ExecuteTargets="OtherTarget" />  
</Target>  
```  

## <a name="see-also"></a>另請參閱  
 [專案檔案結構描述參考](../msbuild/msbuild-project-file-schema-reference.md)   
 [目標](../msbuild/msbuild-targets.md)