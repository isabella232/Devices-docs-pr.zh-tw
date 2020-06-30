---
title: 建立 Surface Hub 2S 的佈建套件
description: 此頁面說明如何使用預配套件和其他工具來部署 Surface Hub 2。
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
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832186"
---
# <span data-ttu-id="a45ad-104">建立 Surface Hub 2S 的佈建套件</span><span class="sxs-lookup"><span data-stu-id="a45ad-104">Create provisioning packages for Surface Hub 2S</span></span>

<span data-ttu-id="a45ad-105">您可以使用 Windows 配置設計工具（WCD）建立預配套件，以自動化 Surface Hub 2 的部署程式。</span><span class="sxs-lookup"><span data-stu-id="a45ad-105">You can use Windows Configuration Designer (WCD) to create provisioning packages to automate the deployment process of Surface Hub 2S.</span></span> <span data-ttu-id="a45ad-106">使用預配套件來新增憑證、設定 proxy、設定裝置管理員和裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="a45ad-106">Use provisioning packages to add certificates, configure proxies, set up device administrators and device accounts.</span></span> <span data-ttu-id="a45ad-107">您也可以使用置備套件和設定檔，以單一的 USB 拇指磁片磁碟機來部署多個 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a45ad-107">You can also use provisioning packages along with a configuration file to deploy multiple Surface Hubs with a single USB thumb drive.</span></span>

### <span data-ttu-id="a45ad-108">安裝 Windows 設定設計工具</span><span class="sxs-lookup"><span data-stu-id="a45ad-108">Install Windows Configuration Designer</span></span>

<span data-ttu-id="a45ad-109">從 windows 10 版 Windows 評估與部署套件（ADK）安裝 Windows 配置設計工具。</span><span class="sxs-lookup"><span data-stu-id="a45ad-109">Install Windows Configuration Designer from the Windows Assessment and Deployment Kit (ADK) for Windows 10.</span></span> <span data-ttu-id="a45ad-110">下載並安裝[適用于 Windows 10 版本1703的 ADK](https://go.microsoft.com/fwlink/p/?LinkId=845542)。</span><span class="sxs-lookup"><span data-stu-id="a45ad-110">Download and install the [ADK for Windows 10, version 1703](https://go.microsoft.com/fwlink/p/?LinkId=845542).</span></span> <span data-ttu-id="a45ad-111">如需詳細資訊，請參閱[下載並安裝 WINDOWS ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)。</span><span class="sxs-lookup"><span data-stu-id="a45ad-111">For more information, see [Download and install the Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install).</span></span>

### <span data-ttu-id="a45ad-112">新增憑證</span><span class="sxs-lookup"><span data-stu-id="a45ad-112">Add certificates</span></span>

<span data-ttu-id="a45ad-113">您可以將憑證授權單位憑證匯入到 Surface Hub 2 秒。</span><span class="sxs-lookup"><span data-stu-id="a45ad-113">You can import Certificate Authority certificates to Surface Hub 2S.</span></span>
<span data-ttu-id="a45ad-114">若要將憑證新增至 Surface Hub 2，您需要將每個憑證複本為 x.509 格式。</span><span class="sxs-lookup"><span data-stu-id="a45ad-114">To add certificates to Surface Hub 2S, you need a copy of each certificate as X.509 in .cer format.</span></span> <span data-ttu-id="a45ad-115">您無法匯入 .crt、.pfx 或其他容器格式。</span><span class="sxs-lookup"><span data-stu-id="a45ad-115">You cannot import .crt, .pfx or other container formats.</span></span> <span data-ttu-id="a45ad-116">必須將憑證匯入 Windows 配置設計工具，並依階層排列：</span><span class="sxs-lookup"><span data-stu-id="a45ad-116">Certificates must be imported into Windows Configuration Designer and arranged by hierarchy:</span></span>

 ![新增憑證](images/sh2-wcd.png)

### <span data-ttu-id="a45ad-118">在 OOBE 期間設定 proxy</span><span class="sxs-lookup"><span data-stu-id="a45ad-118">Configure proxy during OOBE</span></span>

<span data-ttu-id="a45ad-119">在 Windows [組態工具設計工具] 中，移至 [設定 proxy 設定] 索引標籤，然後輸入適當的設定，如下所示。</span><span class="sxs-lookup"><span data-stu-id="a45ad-119">In Windows Configuration Designer, go to the Configure proxy settings tab and enter the appropriate settings as shown below.</span></span>

 ![設定 Proxy 設定](images/sh2-proxy.png) 

> [!NOTE]
> <span data-ttu-id="a45ad-121">設定 [proxy 設定] 時，如果您想要使用安裝程式腳本或 proxy 伺服器，請關閉 [**自動偵測設定**]。</span><span class="sxs-lookup"><span data-stu-id="a45ad-121">When configuring proxy settings, turn off **Automatically detect settings** if you intend to use a setup script or a proxy server.</span></span> <span data-ttu-id="a45ad-122">您可以使用安裝程式腳本*或*proxy 伺服器，而不是兩者。</span><span class="sxs-lookup"><span data-stu-id="a45ad-122">You can use a setup script *or* a proxy server, not both.</span></span>

### <span data-ttu-id="a45ad-123">含 Azure Active Directory 的關聯 Surface Hub 中樞</span><span class="sxs-lookup"><span data-stu-id="a45ad-123">Affiliate Surface Hub 2S with Azure Active Directory</span></span>

<span data-ttu-id="a45ad-124">您可以使用置備套件，將 Surface Hub 2 與 Azure Active Directory 封裝在一起：如 Azure Active Directory 全域系統管理員，您可以使用大量的 Windows 裝置，將大量的新 Windows 裝置加入 Azure Active Directory 和 Intune，並使用大量的權杖。</span><span class="sxs-lookup"><span data-stu-id="a45ad-124">You can affiliate Surface Hub 2S with Azure Active Directory using a provisioning package: As an Azure Active Directory Global Administrator, you can join large numbers of new Windows devices to Azure Active Directory and Intune using a bulk token.</span></span>

<span data-ttu-id="a45ad-125">若要建立大量權杖，請為它指定一個易記的名稱、設定到期日（最多30天），並使用您的系統管理員認證來取得權杖，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a45ad-125">To create a bulk token, give it a friendly name, configure the expiration date (maximum of 30 days) and use your Admin credentials to acquire the token as shown below:</span></span>

 ![設定裝置管理員](images/sh2-token.png) <br><br>
 ![設定裝置管理員](images/sh2-token2.png) <br><br>
 ![設定裝置管理員](images/sh2-token3.png) <br><br>

### <span data-ttu-id="a45ad-129">預配多個裝置（.csv 檔案）</span><span class="sxs-lookup"><span data-stu-id="a45ad-129">Provisioning multiple devices (.csv file)</span></span>

<span data-ttu-id="a45ad-130">除了預配套件之外，您還可以使用 Surface Hub 設定檔，讓您更輕鬆地設定裝置。</span><span class="sxs-lookup"><span data-stu-id="a45ad-130">In addition to the provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="a45ad-131">Surface Hub 設定檔包含適用于無線投影的裝置帳戶和易記名稱清單。</span><span class="sxs-lookup"><span data-stu-id="a45ad-131">A Surface Hub configuration file contains a list of device accounts and friendly names for wireless projection.</span></span> <span data-ttu-id="a45ad-132">在第一次執行期間，您會看到從設定檔選擇裝置帳戶和易記名稱的選項。</span><span class="sxs-lookup"><span data-stu-id="a45ad-132">During first run, you get an option to choose a device account and friendly name from a configuration file.</span></span>

### <span data-ttu-id="a45ad-133">建立 Surface Hub 設定檔</span><span class="sxs-lookup"><span data-stu-id="a45ad-133">To create a Surface Hub configuration file</span></span>

1. <span data-ttu-id="a45ad-134">使用 Microsoft Excel 或其他 CSV 編輯器，建立名為： **SurfaceHubConfiguration.csv**的 CSV 檔案</span><span class="sxs-lookup"><span data-stu-id="a45ad-134">Using Microsoft Excel or another CSV editor, create a CSV file named: **SurfaceHubConfiguration.csv**</span></span>
2. <span data-ttu-id="a45ad-135">以這個格式輸入裝置帳戶和易記名稱的清單：</span><span class="sxs-lookup"><span data-stu-id="a45ad-135">Enter a list of device accounts and friendly names in this format:</span></span>

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. <span data-ttu-id="a45ad-136">將檔案儲存到您複製 PPKG 檔案的 USB 拇指磁片磁碟機根目錄。</span><span class="sxs-lookup"><span data-stu-id="a45ad-136">Save the file to the root of the USB thumb drive where you copied the PPKG file.</span></span>

    ![設定檔範例](images/sh2-config-file.png)
