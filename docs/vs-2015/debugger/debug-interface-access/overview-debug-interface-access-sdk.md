---
title: 概觀 （偵錯介面存取 SDK） |Microsoft Docs
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user-defined types
- .dbg files
- modules
- interfaces [DIA SDK]
- DBG files
- procedures [DIA SDK]
- executable files
- COM objects, in DIA SDK
- compilands
- executable images
ms.assetid: 720b4479-a8bc-4fec-860e-80c1a0780405
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8de5b25b1ece8c4523ba222a97f1107d2275ba3a
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47489509"
---
# <a name="overview-debug-interface-access-sdk"></a>概觀 (偵錯介面存取 SDK)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[概觀 (偵錯介面存取 SDK)](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/overview-debug-interface-access-sdk)。  
  
使用 DIA SDK，來存取 Microsoft 偵錯資訊。 DIA SDK 提供 COM 為基礎的 API 集，就不需要重寫程式碼，每當 Microsoft 變更偵錯資訊格式。 DIA SDK 也可讓您從一組精選的舊版偵錯資訊，位於所產生的.pdb 和.dbg 檔案讀取[!INCLUDE[vcprvc](../../includes/vcprvc-md.md)]5.0 及更新版本的版本。  
  
 DIA SDK 中的每個介面，將不同的 COM 物件，表示除了其中指明。 額外的介面，因此其他物件，建立明確的查詢，透過這類[idiadatasource:: Opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)或是[idiasession:: Findchildren](../../debugger/debug-interface-access/idiasession-findchildren.md)，而不是藉由呼叫`QueryInterface`現有的介面指標。  
  
## <a name="see-also"></a>另請參閱  
 [Idiadatasource:: Opensession](../../debugger/debug-interface-access/idiadatasource-opensession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)



