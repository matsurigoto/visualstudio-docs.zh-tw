---
title: '&lt;摘要&gt;(JavaScript) |Microsoft Docs'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- summary JavaScript XML tag
- <summary> JavaScript XML tag
ms.assetid: 6540582d-bdb3-42ec-ad2f-c176783e6f9c
caps.latest.revision: 15
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: f6b4808112e746e30f0e40d4626f546c3f99b193
ms.sourcegitcommit: 71218ffc33da325cc1b886f69ff2ca50d44f5f33
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2018
ms.locfileid: "48879014"
---
# <a name="ltsummarygt-javascript"></a>&lt;摘要&gt;(JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

本主題的最新的版本可從[Visual Studio 2017 文件](/visualstudio/)。  
  
指定函式或方法的描述。  
  
## <a name="syntax"></a>語法  
  
```  
<summary locid="descriptionID">description  
</summary>  
```  
  
#### <a name="parameters"></a>參數  
 `locid`  
 選擇性。 如需函式或方法的當地語系化資訊識別項。 識別項是成員識別碼或其對應至`name`屬性 OpenAjax 中繼資料所定義的訊息組合中的值。 識別項型別取決於所指定的格式[ \<loc >](../ide/loc-javascript.md)項目。  
  
 `description`  
 選擇性。 函式或方法的描述。  
  
## <a name="remarks"></a>備註  
 用來標註函式，其中包含的項目[\<摘要 >](../ide/summary-javascript.md)， [ \<param >](../ide/param-javascript.md)，以及[\<傳回 >](../ide/returns-javascript.md)，必須放在任何陳述式之前的函式主體。  
  
## <a name="example"></a>範例  
 下列程式碼示範如何使用`<summary>`項目。  
  
```javascript  
function areaFunction(radiusParam)  
{  
    /// <summary>Determines the area of a circle when supplied a radius parameter.</summary>  
    /// <param name="radiusParam" type="Number">The radius of the circle.</param>  
    /// <returns type="Number">The area.</returns>  
    var areaVal;  
    areaVal = Math.PI * radiusParam * radiusParam;  
    return areaVal;  
}  
  
```  
  
## <a name="see-also"></a>另請參閱  
 [XML 文件註解](../ide/xml-documentation-comments-javascript.md)



