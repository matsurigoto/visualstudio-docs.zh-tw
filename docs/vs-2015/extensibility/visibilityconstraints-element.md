---
title: VisibilityConstraints 元素 |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VisibilityConstraints
helpviewer_keywords:
- VSCT XML schema elements, VisibilityConstraints
- VisibilityConstraints element (VSCT XML schema)
ms.assetid: d6dcd314-6fe4-4693-a189-91fa026c7b34
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 9fd6d6968984f0640dd73067c286a4259ade6745
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47498569"
---
# <a name="visibilityconstraints-element"></a>VisibilityConstraints 項目
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[VisibilityConstraints 元素](https://docs.microsoft.com/visualstudio/extensibility/visibilityconstraints-element)。  
  
VisibilityConstraints 元素會決定靜態群組的命令和工具列可見。 可見性會先受到[!INCLUDE[vsprvs](../includes/vsprvs-md.md)]沒有載入 VSPackage 的整合式的開發環境 (IDE)。  
  
## <a name="syntax"></a>語法  
  
```  
<VisibilityConstraints>  
  <VisibilityConstraint>... </VisibilityConstraint>  
  <VisibilityConstraint>... </VisibilityConstraint>  
</VisibilityConstraint>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|條件|選擇性。 請參閱[條件式屬性](../extensibility/vsct-xml-schema-conditional-attributes.md)。|  
  
### <a name="child-elements"></a>子元素  
  
|項目|描述|  
|-------------|-----------------|  
|[VisibilityItem 元素](../extensibility/visibilityitem-element.md)|決定命令和工具列的靜態可見。|  
|[VisibilityConstraints](../extensibility/visibilityconstraints-element.md)|決定靜態群組的命令和工具列可見。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[CommandTable 元素](../extensibility/commandtable-element.md)|定義代表 VSPackage 提供給 IDE 的命令 （例如，功能表項目、 功能表、 工具列和下拉式方塊） 的所有項目。|  
  
## <a name="example"></a>範例  
  
```  
<VisibilityConstraints>  
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"  
    context="guidNotViewSourceMode"/>  
</VisibilityConstraints>  
```  
  
## <a name="see-also"></a>另請參閱  
 [VisibilityItem 元素](../extensibility/visibilityitem-element.md)   
 [Visual Studio 命令表檔案 (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

