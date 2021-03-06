---
title: VSIXLanguagePack 元素 （VSIX 語言套件結構描述） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 767f5c22-8b87-49ca-92aa-a7a3f026469f
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: cf8e55e38ecf16577482955c30ea95c5a5980087
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47491084"
---
# <a name="vsixlanguagepack-element-vsix-language-pack-schema"></a>VSIXLanguagePack 元素 （VSIX 語言套件結構描述）
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[VSIXLanguagePack 元素 （VSIX 語言套件結構描述）](https://docs.microsoft.com/visualstudio/extensibility/vsixlanguagepack-element-vsix-language-pack-schema)。  
  
必要。 VSIX 語言套件中提供的根項目。 VSIX 語言套件會提供 VSIX 封裝當地語系化的安裝資訊。  
  
## <a name="syntax"></a>語法  
  
```  
<VSIXLanguagePack>  
  <LocalizedName>...</LocalizedName>  
  <LocalizedDescription>...</LocalizedDescription>  
  <MoreInfoURL>...</MoreInfoURL>  
  <License>...</License>  
</VSIXLanguagePack>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|`xmlns`|VSIX 語言套件結構描述定義的 XML 命名空間。|  
  
## <a name="xmlns-attribute"></a>xmlns 屬性  
  
|值|描述|  
|-----------|-----------------|  
|`http://schemas.microsoft.com/developer/vsx-schema-lp/2010`|必要。 定義語言組件的結構描述檔案的位置。|  
  
### <a name="child-elements"></a>子元素  
  
|項目|描述|  
|-------------|-----------------|  
|[LocalizedName 元素](../extensibility/localizedname-element-vsix-language-pack-schema.md)|必要。 安裝延伸模組的當地語系化的名稱。|  
|[LocalizedDescription 元素](../extensibility/localizeddescription-element-vsix-language-pack-schema.md)|必要。 安裝延伸模組的當地語系化的描述。|  
|[MoreInfoURL 元素](../extensibility/moreinfourl-element-vsix-language-pack-schema.md)|選擇性。 有關擴充功能的當地語系化資訊的連結。|  
|[License 元素](../extensibility/license-element-vsix-language-pack-schema.md)|選擇性。 當地語系化版本的延伸模組的授權檔案的路徑。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|無||  
  
## <a name="element-information"></a>項目資訊  
  
|||  
|-|-|  
|命名空間|http://schemas.microsoft.com/developer/vsx-schema-lp/2010|  
|結構描述名稱|VSIX 語言套件結構描述|  
|驗證檔|VSIXLanguagePackSchema.xsd|  
|可以是空白|否|  
  
## <a name="see-also"></a>另請參閱  
 [VSX 語言套件結構描述參考](../extensibility/vsx-language-pack-schema-reference.md)   
 [將 VSIX 封裝當地語系化](../extensibility/localizing-vsix-packages.md)   
 [VSIX 延伸結構描述 1.0 參考](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)

