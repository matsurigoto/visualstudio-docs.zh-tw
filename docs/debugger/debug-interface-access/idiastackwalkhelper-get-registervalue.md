---
title: IDiaStackWalkHelper::get_registerValue |Microsoft 文件
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::get_registerValue method
ms.assetid: 46ac5eee-73a3-44a1-8635-6c58ba193cb6
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6ccc491ec9e966b8d893b6d669aafc64ebc5c8cf
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/18/2018
ms.locfileid: "31462765"
---
# <a name="idiastackwalkhelpergetregistervalue"></a>IDiaStackWalkHelper::get_registerValue
擷取暫存器的值。  
  
## <a name="syntax"></a>語法  
  
```C++  
HRESULT get_registerValue (   
   DWORD      index,  
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>參數  
 `index`  
 [in]中的值[CV_HREG_e 列舉](../../debugger/debug-interface-access/cv-hreg-e.md)列舉指定的註冊以取得的值。  
  
 `pRetVal`  
 [out]傳回登錄的目前值。  
  
## <a name="return-value"></a>傳回值  
 如果成功，傳回`S_OK`; 否則傳回錯誤碼。  
  
## <a name="remarks"></a>備註  
 儘管大小`pRetVal`參數，實作應只哪些暫存器通常會保留儲存。 例如的 8 位元暫存器保留只最低 8 位元的指定值。 8 位元值，這個已擴充成 64 位元，從這個方法傳回時。  
  
## <a name="see-also"></a>另請參閱  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV_HREG_e 列舉](../../debugger/debug-interface-access/cv-hreg-e.md)