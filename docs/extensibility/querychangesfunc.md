---
title: "QUERYCHANGESFUNC |Microsoft 文件"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- QUERYCHANGESFUNC
helpviewer_keywords:
- QUERYCHANGESFUNC callback function
- QUERYCHANGESDATA structure
ms.assetid: 9d383e2c-eee1-4996-973a-0652d4c5951c
caps.latest.revision: 16
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 7b53174955e07f2ecfc58a32b7cd888443640511
ms.contentlocale: zh-tw
ms.lasthandoff: 09/26/2017

---
# <a name="querychangesfunc"></a>QUERYCHANGESFUNC
這是所使用的回呼函式[SccQueryChanges](../extensibility/sccquerychanges-function.md)操作列舉的檔案名稱的集合，並判斷每個檔案的狀態。  
  
 `SccQueryChanges`函式會指定一份檔案，以及一個指向`QUERYCHANGESFUNC`回呼。 原始檔控制外掛程式列舉指定的清單，並提供每個清單中的檔案狀態 （透過此回呼）。  
  
## <a name="signature"></a>簽章  
  
```cpp  
typedef BOOL (*QUERYCHANGESFUNC)(  
   LPVOID pvCallerData,  
   QUERYCHANGESDATA * pChangesData  
);  
```  
  
## <a name="parameters"></a>參數  
 pvCallerData  
 [in]`pvCallerData`參數傳遞至呼叫端 (IDE) [SccQueryChanges](../extensibility/sccquerychanges-function.md)。 原始檔控制外掛程式，應該進行內容的這個值不作任何假設。  
  
 pChangesData  
 [in]指標[QUERYCHANGESDATA 結構](#LinkQUERYCHANGESDATA)結構描述檔案的變更。  
  
## <a name="return-value"></a>傳回值  
 IDE 會傳回適當的錯誤程式碼：  
  
|值|說明|  
|-----------|-----------------|  
|SCC_OK|繼續處理。|  
|SCC_I_OPERATIONCANCELED|停止處理。|  
|SCC_E_xxx|任何適當的 SCC 錯誤，應該停止處理。|  
  
##  <a name="LinkQUERYCHANGESDATA"></a>QUERYCHANGESDATA 結構  
 傳入的每個檔案的結構類似下列所示：  
  
```cpp  
struct QUERYCHANGESDATA_A  
{  
    DWORD  dwSize;  
    LPCSTR lpFileName;  
    DWORD  dwChangeType;  
    LPCSTR lpLatestName;  
};  
  
typedef struct QUERYCHANGESDATA_A QUERYCHANGESDATA;  
  
struct QUERYCHANGESDATA_W  
{  
    DWORD   dwSize;  
    LPCWSTR lpFileName;  
    DWORD   dwChangeType;  
    LPCWSTR lpLatestName;  
};  
```  
  
 dwSize  
 此結構 （以位元組為單位） 的大小。  
  
 lpFileName  
 此項目的原始的檔案名稱。  
  
 dwChangeType  
 指出檔案的狀態碼：  
  
|程式碼|說明|  
|----------|-----------------|  
|`SCC_CHANGE_UNKNOWN`|無法分辨哪些變更。|  
|`SCC_CHANGE_UNCHANGED`|這個檔案的名稱並無任何變更。|  
|`SCC_CHANGE_DIFFERENT`|檔案使用不同的身分識別，但在資料庫中存在相同的名稱。|  
|`SCC_CHANGE_NONEXISTENT`|檔案不存在資料庫中或在本機。|  
|`SCC_CHANGE_DATABASE_DELETED`|從資料庫中刪除的檔案。|  
|`SCC_CHANGE_LOCAL_DELETED`|在本機刪除的檔案，但該檔案仍存在於資料庫中。 如果無法判別，傳回`SCC_CHANGE_DATABASE_ADDED`。|  
|`SCC_CHANGE_DATABASE_ADDED`|檔案加入至資料庫，但不在本機上。|  
|`SCC_CHANGE_LOCAL_ADDED`|檔案不存在資料庫中，且新的本機檔案。|  
|`SCC_CHANGE_RENAMED_TO`|檔案重新命名或移動資料庫做為`lpLatestName`。|  
|`SCC_CHANGE_RENAMED_FROM`|檔案重新命名或從資料庫中移動`lpLatestName`; 如果這是過於昂貴，若要追蹤，傳回不同的旗標，例如`SCC_CHANGE_DATABASE_ADDED`。|  
  
 lpLatestName  
 此項目目前的檔案名稱。  
  
## <a name="see-also"></a>另請參閱  
 [IDE 所實作的回呼函式](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)   
 [錯誤碼](../extensibility/error-codes.md)