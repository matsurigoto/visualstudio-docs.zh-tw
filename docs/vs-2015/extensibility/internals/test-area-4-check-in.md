---
title: 測試區域 4︰ 簽入 |Microsoft Docs
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
- source control [Visual Studio SDK], checking items in
- source control plug-ins, checking items in
ms.assetid: d0329fa8-7a8d-4d30-b67b-6f2a97b75a30
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 740ddbfbc24dacaa23200cac1632bf3cf4aef828
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47486454"
---
# <a name="test-area-4-check-in"></a>測試區域 4︰簽入
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[測試區域 4： 簽入](https://docs.microsoft.com/visualstudio/extensibility/internals/test-area-4-check-in)。  
  
此原始檔控制外掛程式的測試區域涵蓋版本存放區，以透過傳送更新的項目**簽入**命令。  
  
## <a name="command-menu-access"></a>命令功能表存取  
 下列[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]與測試案例中使用整合式的開發環境功能表路徑。  
  
##### <a name="check-in"></a>簽入：  
 **檔案**，**原始檔控制**，**簽入**。  
  
 **檔案**，**簽入**。  
  
 快顯功能表**簽入**。  
  
## <a name="common-expected-behavior"></a>常見的預期的行為  
  
-   專案和加入至方案或專案原始檔控制下的檔案會出現在**簽入** 對話方塊中，**暫止簽入**視窗。  
  
-   簽入之後, 加入的項目會出現在原始檔控制。  
  
-   在檢查之後, 已更新的項目是正確版本存放區中。  
  
## <a name="test-cases"></a>測試案例  
 以下是簽入測試區域的特定測試案例。  
  
### <a name="case-4a-modified-items"></a>案例 4a： 修改項目  
 描述如何使用作用中的檢查更新已修改的原始檔控制下的檔案。  
  
|動作|測試步驟|若要確認預期的結果|  
|------------|----------------|--------------------------------|  
|修改尚未簽出的文字檔案、 簽入僅限檔案 (**簽入**對話方塊)|1.文字檔中建立新的專案。<br />2.您可以將方案加入原始檔控制。<br />3.簽出和修改文字檔案。<br />4.透過 [另存新檔] 對話方塊檢查 (**檔案**，**原始檔控制**，**簽入**)。|常見的預期的行為。|  
|修改尚未簽出的文字檔案、 簽入僅限檔案 (**暫止簽入**視窗)|1.文字檔中建立新的專案。<br />2.您可以將方案加入原始檔控制。<br />3.簽出和修改文字檔案。<br />4.簽入，透過**暫止簽入**視窗。|常見的預期的行為。|  
  
### <a name="case-4b-adding-files"></a>案例 4b： 新增檔案  
 將檔案加入至專案或方案項目，但是專案或解決方案必須也變更。 因此父檔案也簽出，並且必須簽入，才能完成加入。  
  
|動作|測試步驟|若要確認預期的結果|  
|------------|----------------|--------------------------------|  
|加入文字檔案，並簽入所有檔案 (**簽入**對話方塊)|1.建立新的專案。<br />2.您可以將方案加入原始檔控制。<br />3.將文字檔加入至專案。<br />4.如果出現提示，請接受簽出專案。<br />5.選取中的解決方案**方案總管 中**。<br />6.從簽入**簽入** 對話方塊。|常見的預期的行為。|  
|加入文字檔案，並簽入所有檔案 (**暫止簽入**視窗)|1.建立新的專案。<br />2.您可以將方案加入原始檔控制。<br />3.將文字檔加入至專案。<br />4.如果出現提示，請接受簽出專案。<br />5.從方案簽入**暫止簽入**視窗。|常見的預期的行為|  
  
### <a name="case-4c-adding-projects"></a>案例 4c： 新增專案  
 當您可以將專案加入方案，方案必須也變更。 因此方案檔也已簽出，並且必須簽入，才能完成加入。  
  
|動作|測試步驟|若要確認預期的結果|  
|------------|----------------|--------------------------------|  
|將專案加入原始檔控制下的空白方案 (**簽入**對話方塊)|1.建立空白方案。<br />2.您可以將方案加入原始檔控制。<br />3.加入新的專案。<br />4.如果出現提示，請接受簽出的解決方案。<br />5.從簽入**簽入** 對話方塊。|常見的預期的行為。|  
|將專案加入原始檔控制下的空白方案 (**暫止簽入**視窗)|1.建立空白方案。<br />2.您可以將方案加入原始檔控制。<br />3.加入新的專案。<br />4.如果出現提示，請接受簽出的解決方案。<br />5.從方案簽入**暫止簽入**視窗。|常見的預期的行為。|  
  
## <a name="see-also"></a>另請參閱  
 [原始檔控制外掛程式測試指南](../../extensibility/internals/test-guide-for-source-control-plug-ins.md)
