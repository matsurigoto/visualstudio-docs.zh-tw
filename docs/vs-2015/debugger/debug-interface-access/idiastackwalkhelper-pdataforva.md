---
title: IDiaStackWalkHelper::pdataForVA |Microsoft Docs
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
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6949fba8216bbc1747c9bd1f963a0f1c06bff4e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/22/2018
ms.locfileid: "47491345"
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

本主題的最新的版本可從[IDiaStackWalkHelper::pdataForVA](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiastackwalkhelper-pdataforva)。  
  
傳回虛擬位址相關聯的 PDATA 資料區塊。  
  
## <a name="syntax"></a>語法  
  
```cpp#  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>參數  
 `va`  
 [in]指定要取得之資料的虛擬位址。  
  
 `cbData`  
 [in]以位元組為單位來取得資料的大小。  
  
 `pcbData`  
 [out]傳回資料的實際大小，以位元組為單位所取得。  
  
 `pbData`  
 [in、 out]要求的資料會填入緩衝區。 不能是`NULL`。  
  
## <a name="return-value"></a>傳回值  
 如果成功，則傳回`S_OK`。 傳回`S_FALSE`如果沒有針對指定的位址沒有 PDATA。 反之則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 PDATA （名為".pdata 」 一節） 的編譯模組包含 例外狀況處理函式的相關資訊。  
  
 呼叫端知道多少資料是要讓呼叫端沒有問多少資料，則會出現不需要傳回。 因此，它是可接受的傳回錯誤，如果此方法的實作`pbData`參數是`NULL`。  
  
## <a name="see-also"></a>另請參閱  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)



