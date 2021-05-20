---
title: 建立 Surface Hub 2S 的佈建套件
description: 此頁面說明如何使用部署套件Surface Hub部署 2S。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 214a71a759358ae08eb0da7942ea190946deb327
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576863"
---
# <a name="create-provisioning-packages-for-surface-hub-2s"></a>建立 Surface Hub 2S 的佈建套件

您可以在 WCD Windows配置設計工具 (建立) 套件，以自動化 2S Surface Hub部署。 使用部署套件來新增憑證、設定代理、設定裝置系統管理員和裝置帳戶。 您也可以使用部署套件和設定檔，以單一 USB 拇指磁碟機部署多個 Surface Hub。

### <a name="install-windows-configuration-designer"></a>安裝 Windows 設定設計工具

從 Windows ADK Windows的 ADK (安裝) 組Windows 10。 下載並安裝[適用于 Windows 10版本 1703 的 ADK。](https://go.microsoft.com/fwlink/p/?LinkId=845542) 如需詳細資訊，請參閱 [下載並安裝 Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)。

### <a name="add-certificates"></a>新增憑證

您可以將憑證頒發機構憑證Surface Hub 2S。
若要將憑證新Surface Hub 2S，您需要以 .cer 格式將每個憑證的一份副本作為 X.509。 您無法導入 .crt、.pfx 或其他容器格式。 憑證必須輸入至Windows設計工具，並按階層排列：

> [!div class="mx-imgBorder"]
> ![新增憑證](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a>在 OOBE 期間設定 Proxy

在 Windows設定設計工具中，請前往設定 Proxy 設定選項卡，然後輸入適當的設定，如下所示。

> [!div class="mx-imgBorder"]
> ![設定 Proxy 設定](images/sh2-proxy.png) 

> [!NOTE]
> 設定 Proxy 設定時，如果您**** 打算使用設定腳本或 Proxy 伺服器，請關閉自動偵測設定。 您可以使用設定 *腳本或* Proxy 伺服器，而非兩者。

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a>與 Surface Hub 2S 的Azure Active Directory

您可以使用Surface Hub套件Azure Active Directory 2S 與 Azure Active Directory 進行關聯：做為 Azure Active Directory 全域系統管理員，您可以使用大量權杖將大量 Windows 裝置加入 Azure Active Directory 和 Intune。

若要建立大量權杖，請為它指定一個方便的名稱，設定到期日 (最多 30 天) 並使用您的系統管理員認證取得權杖，如下所示：

> [!div class="mx-imgBorder"]
> ![設定裝置系統管理員範例 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![設定裝置系統管理員範例 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![設定裝置系統管理員範例 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a>將多個裝置 (.csv檔案) 

除了設定套件之外，您還可以使用Surface Hub設定檔，更輕鬆地設定您的裝置。 一Surface Hub組設定檔包含裝置帳戶清單，以及無線投影的方便名稱。 在第一次執行期間，您可以從設定檔選擇裝置帳戶和好用名稱。

### <a name="to-create-a-surface-hub-configuration-file"></a>若要建立Surface Hub組設定檔

1. 使用 Microsoft Excel或另一個 CSV 編輯器，建立**名為：SurfaceHubConfiguration.csv**

2. 輸入此格式的裝置帳戶和好用名稱清單：

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. 將檔案儲存到您複製 PPKG 檔案的 USB 拇指磁碟機根目錄。

    > [!div class="mx-imgBorder"]
    > ![組設定檔範例](images/sh2-config-file.png)
