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
# <a name="create-provisioning-packages-for-surface-hub-2s"></a><span data-ttu-id="6f6a7-104">建立 Surface Hub 2S 的佈建套件</span><span class="sxs-lookup"><span data-stu-id="6f6a7-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="6f6a7-105">您可以在 WCD Windows配置設計工具 (建立) 套件，以自動化 2S Surface Hub部署。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate deployment of Surface Hub 2S.</span></span> <span data-ttu-id="6f6a7-106">使用部署套件來新增憑證、設定代理、設定裝置系統管理員和裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="6f6a7-107">您也可以使用部署套件和設定檔，以單一 USB 拇指磁碟機部署多個 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <a name="install-windows-configuration-designer"></a><span data-ttu-id="6f6a7-108">安裝 Windows 設定設計工具</span><span class="sxs-lookup"><span data-stu-id="6f6a7-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="6f6a7-109">從 Windows ADK Windows的 ADK (安裝) 組Windows 10。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="6f6a7-110">下載並安裝[適用于 Windows 10版本 1703 的 ADK。](https://go.microsoft.com/fwlink/p/?LinkId=845542)</span><span class="sxs-lookup"><span data-stu-id="6f6a7-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="6f6a7-111">如需詳細資訊，請參閱 [下載並安裝 Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <a name="add-certificates"></a><span data-ttu-id="6f6a7-112">新增憑證</span><span class="sxs-lookup"><span data-stu-id="6f6a7-112">Add certificates</span></span>

<span data-ttu-id="6f6a7-113">您可以將憑證頒發機構憑證Surface Hub 2S。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="6f6a7-114">若要將憑證新Surface Hub 2S，您需要以 .cer 格式將每個憑證的一份副本作為 X.509。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="6f6a7-115">您無法導入 .crt、.pfx 或其他容器格式。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="6f6a7-116">憑證必須輸入至Windows設計工具，並按階層排列：</span><span class="sxs-lookup"><span data-stu-id="6f6a7-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

> [!div class="mx-imgBorder"]
> ![新增憑證](images/sh2-wcd.png)

### <a name="configure-proxy-during-oobe"></a><span data-ttu-id="6f6a7-118">在 OOBE 期間設定 Proxy</span><span class="sxs-lookup"><span data-stu-id="6f6a7-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="6f6a7-119">在 Windows設定設計工具中，請前往設定 Proxy 設定選項卡，然後輸入適當的設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

> [!div class="mx-imgBorder"]
> ![設定 Proxy 設定](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="6f6a7-121">設定 Proxy 設定時，如果您\*\*\*\* 打算使用設定腳本或 Proxy 伺服器，請關閉自動偵測設定。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="6f6a7-122">您可以使用設定 *腳本或* Proxy 伺服器，而非兩者。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <a name="affiliate-surface-hub-2s-with-azure-active-directory"></a><span data-ttu-id="6f6a7-123">與 Surface Hub 2S 的Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f6a7-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="6f6a7-124">您可以使用Surface Hub套件Azure Active Directory 2S 與 Azure Active Directory 進行關聯：做為 Azure Active Directory 全域系統管理員，您可以使用大量權杖將大量 Windows 裝置加入 Azure Active Directory 和 Intune。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="6f6a7-125">若要建立大量權杖，請為它指定一個方便的名稱，設定到期日 (最多 30 天) 並使用您的系統管理員認證取得權杖，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f6a7-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

> [!div class="mx-imgBorder"]
> ![設定裝置系統管理員範例 1](images/sh2-token.png)

> [!div class="mx-imgBorder"]
> ![設定裝置系統管理員範例 2](images/sh2-token2.png)

> [!div class="mx-imgBorder"]
> ![設定裝置系統管理員範例 3](images/sh2-token3.png)


### <a name="provisioning-multiple-devices-csv-file"></a><span data-ttu-id="6f6a7-129">將多個裝置 (.csv檔案) </span><span class="sxs-lookup"><span data-stu-id="6f6a7-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="6f6a7-130">除了設定套件之外，您還可以使用Surface Hub設定檔，更輕鬆地設定您的裝置。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="6f6a7-131">一Surface Hub組設定檔包含裝置帳戶清單，以及無線投影的方便名稱。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="6f6a7-132">在第一次執行期間，您可以從設定檔選擇裝置帳戶和好用名稱。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <a name="to-create-a-surface-hub-configuration-file"></a><span data-ttu-id="6f6a7-133">若要建立Surface Hub組設定檔</span><span class="sxs-lookup"><span data-stu-id="6f6a7-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="6f6a7-134">使用 Microsoft Excel或另一個 CSV 編輯器，建立**名為：SurfaceHubConfiguration.csv**</span><span class="sxs-lookup"><span data-stu-id="6f6a7-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>

2. <span data-ttu-id="6f6a7-135">輸入此格式的裝置帳戶和好用名稱清單：</span><span class="sxs-lookup"><span data-stu-id="6f6a7-135">Enter a list of device accounts and friendly names in this format:</span></span>

    `<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>`

3. <span data-ttu-id="6f6a7-136">將檔案儲存到您複製 PPKG 檔案的 USB 拇指磁碟機根目錄。</span><span class="sxs-lookup"><span data-stu-id="6f6a7-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    > [!div class="mx-imgBorder"]
    > ![組設定檔範例](images/sh2-config-file.png)
