---
title: 移至命令 | Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
caps.latest.revision: 18
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 123398be5bf8b4aece11e2624390507cec2252d0
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47488746"
---
# <a name="go-to-command"></a>移至命令
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[移至 命令](https://docs.microsoft.com/visualstudio/ide/reference/go-to-command)。  
  
  
將游標移至指定的程式行。  
  
## <a name="syntax"></a>語法  
  
```  
Edit.GoTo [linenumber]  
```  
  
## <a name="arguments"></a>引數  
 `linenumber`  
 選擇性。 整數，代表要移至的行號。  
  
## <a name="remarks"></a>備註  
 行編號是從一開始。 如果 `linenumber` 的值小於一，則會顯示第一行。 如果 `linenumber` 的值大於最後一行的行號，則會顯示最後一行。  
  
 如果未指定 `linenumber` 的值，則會顯示 [移至指定行] 對話方塊。  
  
 此命令的別名是 GoToLn。  
  
## <a name="example"></a>範例  
  
```  
>Edit.GoTo 125  
```  
  
## <a name="see-also"></a>另請參閱  
 [Visual Studio 命令](../../ide/reference/visual-studio-commands.md)   
 [命令視窗](../../ide/reference/command-window.md)   
 [尋找/命令方塊](../../ide/find-command-box.md)   
 [Visual Studio 命令別名](../../ide/reference/visual-studio-command-aliases.md)



