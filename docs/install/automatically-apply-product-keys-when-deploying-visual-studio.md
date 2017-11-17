---
title: "在部署 Visual Studio 時自動套用產品金鑰 | Microsoft Docs"
ms.custom: 
ms.date: 08/14/2017
ms.reviewer: tims
ms.suite: 
ms.technology:
- vs-ide-install
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d79260be-6234-4fd3-89b5-a9756b4a93c1
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: f23906933add1f4706d8786b2950fb3b5d2e6781
ms.openlocfilehash: 1ebf97930f115795139c9e748df7e03523088a21
ms.contentlocale: zh-tw
ms.lasthandoff: 09/26/2017

---
# <a name="automatically-apply-product-keys-when-deploying-visual-studio"></a>在部署 Visual Studio 時自動套用產品金鑰
您能以程式設計方式套用您的產品金鑰，作為用來自動化部署 Visual Studio 的一部分指令碼。 您可以在 Visual Studio 安裝期間或完成安裝後，以程式設計方式在裝置上設定產品金鑰。

## <a name="apply-the-license-after-installation"></a>在安裝後套用授權
 您可以在目標電腦上以無訊息模式使用 `StorePID.exe` 公用程式，利用產品金鑰來啟用已安裝的 Visual Studio 版本。 `StorePID.exe` 是與 Visual Studio 2017 一起安裝的公用程式，其預設位置如下： <br> `C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE`

 使用 System Center 代理程式或提升權限的命令提示字元，以較高的權限執行 `StorePID.exe`。 之後，請使用產品金鑰和 Microsoft 產品代碼 (MPC)。

>[!IMPORTANT]
> 務必包含產品金鑰的破折號。

 ```
 StorePID.exe [product key including the dashes] [MPC]
 ```

 下列範例示範的命令列可套用 MPC 為 08860、產品金鑰為 `AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE` 並採用預設安裝位置的 Visual Studio 2017 Enterprise 授權：

 ```cmd
 "C:\Program Files (x86)\Microsoft Visual Studio\2017\Enterprise\Common7\IDE\StorePID.exe" AAAAA-BBBBB-CCCCC-DDDDDD-EEEEEE 08860
 ```

 下表列出每個 Visual Studio 版本的 MPC 代碼：

| Visual Studio 版本                | MPC   |
|--------------------------------------|-------|
| Visual Studio Enterprise 2017        | 08860 |
| Visual Studio Professional 2017      | 08862 |
| Visual Studio Test Professional 2017 | 08866 |

如果 `StorePID.exe` 成功套用產品金鑰，則會傳回值為 0 的 `%ERRORLEVEL%`。 如果發生錯誤，則會根據錯誤狀況傳回下列其中一個代碼：

| 錯誤                     | 程式碼 |
|---------------------------|------|
| `PID_ACTION_SUCCESS`      | 0    |
| `PID_ACTION_NOTINSTALLED` | 1    |
| `PID_ACTION_INVALID`      | 2    |
| `PID_ACTION_EXPIRED`      | 3    |
| `PID_ACTION_INUSE`        | 4    |
| `PID_ACTION_FAILURE`      | 5    |
| `PID_ACTION_NOUPGRADE`    | 6    |

## <a name="see-also"></a>另請參閱
 * [安裝 Visual Studio](../install/install-visual-studio.md)
 * [建立 Visual Studio 的離線安裝](../install/create-an-offline-installation-of-visual-studio.md)
