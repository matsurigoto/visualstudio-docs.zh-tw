---
title: Item 函式 | Microsoft Docs
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
- msbuild, Item functions
ms.assetid: 5e6df3cc-2db8-4cbd-8fdd-3ffd03ac0876
caps.latest.revision: 32
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 58344d897630244f5f2c1e987f5f41971bfc720c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47485554"
---
# <a name="item-functions"></a>Item 函式
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[項目函式](https://docs.microsoft.com/visualstudio/msbuild/item-functions)。  
  
  
從 MSBuild 4.0 開始，工作和目標中的程式碼可以呼叫項目函式來取得專案中項目的相關資訊。 這些函式會簡化取得 Distinct() 項目的方式，速度比執行項目迴圈還快。  
  
## <a name="string-item-functions"></a>字串項目函式  
 您可以使用 .NET Framework 中的字串方法和屬性，來操作任何項目值。 針對 <xref:System.String> 方法，指定方法名稱。 針對 <xref:System.String> 屬性，在 "get_" 後面指定屬性名稱。  
  
 針對有多個字串的項目，字串方法或屬性是在每個字串上執行。  
  
 下列範例示範如何使用這些字串項目函式。  
  
```  
<ItemGroup>  
    <theItem Include="andromeda;tadpole;cartwheel" />  
</ItemGroup>  
  
<Target Name = "go">  
    <Message Text="IndexOf  @(theItem->IndexOf('r'))" />  
    <Message Text="Replace  @(theItem->Replace('tadpole', 'pinwheel'))" />  
    <Message Text="Length   @(theItem->get_Length())" />  
    <Message Text="Chars    @(theItem->get_Chars(2))" />  
</Target>  
  
  <!--  
  Output:  
    IndexOf  3;-1;2  
    Replace  andromeda;pinwheel;cartwheel  
    Length   9;7;9  
    Chars    d;d;r  
  -->  
```  
  
## <a name="intrinsic-item-functions"></a>內建項目函式  
 下表列出項目可用的內建函式。  
  
|功能|範例|描述|  
|--------------|-------------|-----------------|  
|`Count`|`@(MyItem->Count())`|傳回項目計數。|  
|`DirectoryName`|`@(MyItem->DirectoryName())`|傳回每個項目之 `Path.DirectoryName` 的對等項目。|  
|`Distinct`|`@(MyItem->Distinct())`|傳回具有相異 `Include` 值的項目。 會略過中繼資料。 比較不區分大小寫。|  
|`DistinctWithCase`|`@(MyItem->DistinctWithCase())`|傳回具有相異 `itemspec` 值的項目。 會略過中繼資料。 比較會區分大小寫。|  
|`Reverse`|`@(MyItem->Reverse())`|以反向順序傳回項目。|  
|`AnyHaveMetadataValue`|`@(MyItem->AnyHaveMetadataValue("MetadataName", "MetadataValue"))`|傳回 `boolean`，以指出任何項目是否具有指定的中繼資料名稱和值。 比較不區分大小寫。|  
|`ClearMetadata`|`@(MyItem->ClearMetadata())`|傳回已清除其中繼資料的項目。 只會保留 `itemspec`。|  
|`HasMetadata`|`@(MyItem->HasMetadataValue("MetadataName")`|傳回具有所指定中繼資料名稱的項目。 比較不區分大小寫。|  
|`Metadata`|`@(MyItem->Metadata("MetadataName"))`|傳回具有中繼資料名稱的中繼資料值。|  
|`WithMetadataValue`|`@(MyItem->WithMetadataValue("MetadataName", "MetadataValue")`|傳回具有所指定中繼資料名稱和值的項目。 比較不區分大小寫。|  
  
 下列範例示範如何使用內建項目函式。  
  
```  
<ItemGroup>  
    <TheItem Include="first">  
        <Plant>geranium</Plant>  
    </TheItem>  
    <TheItem Include="second">  
        <Plant>algae</Plant>  
    </TheItem>  
    <TheItem Include="third">  
        <Plant>geranium</Plant>  
    </TheItem>  
</ItemGroup>  
  
<Target Name="go">  
    <Message Text="MetaData:    @(TheItem->Metadata('Plant'))" />  
    <Message Text="HasMetadata: @(theItem->HasMetadata('Plant'))" />  
    <Message Text="WithMetadataValue: @(TheItem->WithMetadataValue('Plant', 'geranium'))" />  
    <Message Text=" " />  
    <Message Text="Count:   @(theItem->Count())" />  
    <Message Text="Reverse: @(theItem->Reverse())" />  
</Target>  
  
  <!--   
  Output:  
    MetaData:    geranium;algae;geranium  
    HasMetadata: first;second;third  
    WithMetadataValue: first;third  
  
    Count:   3  
    Reverse: third;second;first  
  -->  
```  
  
## <a name="see-also"></a>另請參閱  
 [項目](../msbuild/msbuild-items.md)


