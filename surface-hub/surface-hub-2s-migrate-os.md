---
title: 移轉到 Windows 10 專業版或 Surface Hub 2 企業版
description: 本文將說明如何從 Surface Hub 2 上的 Windows 10 團隊遷移到 Windows 10 專業版或 Windows 10 Enterprise。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 713bd2e76f144b4dca7c0fad5c584b06ea12b0b5
ms.sourcegitcommit: 3ca1d1bc77452acca914d0af03e252ee260ebf1a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154140"
---
# <span data-ttu-id="27267-104">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="27267-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="27267-105">Surface Hub 秒是預先預先安裝了 Windows 10 團隊。</span><span class="sxs-lookup"><span data-stu-id="27267-105">Surface Hub 2S comes preinstalled with Windows 10 Team.</span></span> <span data-ttu-id="27267-106">此自訂版本的 Windows 10 是設計來協助在會議室環境中共同作業。</span><span class="sxs-lookup"><span data-stu-id="27267-106">This customized edition of Windows 10 is designed to facilitate collaboration in meeting room environments.</span></span> <span data-ttu-id="27267-107">現在，您可以選擇執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。</span><span class="sxs-lookup"><span data-stu-id="27267-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="27267-108">與典型的升級或遷移不同，此程式必須遵循說明性程式，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="27267-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described in this article.</span></span> <span data-ttu-id="27267-109">繼續之前，請先查看 [解決方案元件](#solution-components) 與 [遷移及安裝工作流程](#migration-and-installation-workflow-summary) 。</span><span class="sxs-lookup"><span data-stu-id="27267-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before you continue.</span></span>


> [!NOTE]
> <span data-ttu-id="27267-110">當您安裝 Windows 10 專業版或企業版時，您需要與現有的 Windows 10 小組授權不同的新授權。</span><span class="sxs-lookup"><span data-stu-id="27267-110">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="27267-111">使用個別的電腦和可下載的工具 *SURFACE UEFI 配置*器，從 Windows 10 小組開始遷移。</span><span class="sxs-lookup"><span data-stu-id="27267-111">Start the migration from Windows 10 Team by using a separate PC and the downloadable tool *Surface UEFI Configurator*.</span></span> <span data-ttu-id="27267-112">使用此工具來建立包含您套用至 Surface Hub 2 秒的新 UEFI 設定的套件。</span><span class="sxs-lookup"><span data-stu-id="27267-112">Use the tool  to create a package that contains a new UEFI setting that you apply to Surface Hub 2S.</span></span>  

<span data-ttu-id="27267-113">Surface UEFI 配置處理常式在 (SEMM) 中，成為 Surface Enterprise 管理模式的介面。</span><span class="sxs-lookup"><span data-stu-id="27267-113">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="27267-114">它旨在協助集中管理公司環境中的 Surface 裝置上的固件設定。</span><span class="sxs-lookup"><span data-stu-id="27267-114">It's designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="27267-115">如需詳細資訊，請參閱 [MICROSOFT SEMM 檔](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="27267-115">For more information, see the [Microsoft SEMM documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="27267-116">解決方案元件</span><span class="sxs-lookup"><span data-stu-id="27267-116">Solution components</span></span>

- <span data-ttu-id="27267-117">執行 Windows 10 小組作業系統的 Surface Hub 2 秒裝置</span><span class="sxs-lookup"><span data-stu-id="27267-117">Surface Hub 2S device running the Windows 10 Team operating system</span></span>
- <span data-ttu-id="27267-118">運行 Windows 10 的個別裝置</span><span class="sxs-lookup"><span data-stu-id="27267-118">Separate device running Windows 10</span></span>
- <span data-ttu-id="27267-119">用於建立 SEMM 套件的 Surface UEFI 設定檔工具</span><span class="sxs-lookup"><span data-stu-id="27267-119">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="27267-120">Windows 10 專業版或企業版作業系統影像、版本1903或更新版本</span><span class="sxs-lookup"><span data-stu-id="27267-120">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="27267-121">兩個有 16 GB 儲存空間的 USB 磁片磁碟機，FAT32 格式</span><span class="sxs-lookup"><span data-stu-id="27267-121">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="27267-122">Windows 10 專業版和企業作業系統在 Surface Hub 2 上的驅動程式與固件，Microsoft Windows Installer (的 MSI) 檔案</span><span class="sxs-lookup"><span data-stu-id="27267-122">The Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="27267-123">網際網路連線</span><span class="sxs-lookup"><span data-stu-id="27267-123">Internet connection</span></span>
- <span data-ttu-id="27267-124">影像處理方案 (選用) </span><span class="sxs-lookup"><span data-stu-id="27267-124">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="27267-125">遷移和安裝工作流程摘要</span><span class="sxs-lookup"><span data-stu-id="27267-125">Migration and installation workflow summary</span></span>

| <span data-ttu-id="27267-126">步驟</span><span class="sxs-lookup"><span data-stu-id="27267-126">Step</span></span>  | <span data-ttu-id="27267-127">動作</span><span class="sxs-lookup"><span data-stu-id="27267-127">Action</span></span>                                                                                                 | <span data-ttu-id="27267-128">摘要</span><span class="sxs-lookup"><span data-stu-id="27267-128">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="27267-129">sr-1</span><span class="sxs-lookup"><span data-stu-id="27267-129">1</span></span> | [<span data-ttu-id="27267-130">確認 Surface Hub 2 上的 UEFI 版本符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="27267-130">Verify that the UEFI version on Surface Hub 2S meets minimum requirements.</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="27267-131">確定 UEFI 版本為694.2938.768.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="27267-131">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="27267-132">pplx-2</span><span class="sxs-lookup"><span data-stu-id="27267-132">2</span></span> | [<span data-ttu-id="27267-133">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件。</span><span class="sxs-lookup"><span data-stu-id="27267-133">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="27267-134">在 [ [**表面工具**](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面上，選取 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="27267-134">On the [**Surface Tools for IT**](https://www.microsoft.com/download/details.aspx?id=46703) page, select **Download**.</span></span> <span data-ttu-id="27267-135">然後選取並下載 **SURFACE UEFI 配置器。MSI** 檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="27267-135">Then select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="27267-136">下載 [適用于 Surface Hub 2 MSI 檔案的 Windows 10 專業版和企業版 OS 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="27267-136">Download the [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="27267-137">將它儲存在步驟5中以供使用。</span><span class="sxs-lookup"><span data-stu-id="27267-137">Save it for use in step 5.</span></span> |
| <span data-ttu-id="27267-138">3</span><span class="sxs-lookup"><span data-stu-id="27267-138">3</span></span> | [<span data-ttu-id="27267-139">準備 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="27267-139">Prepare SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="27267-140">準備運行 Surface UEFI 配置器所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="27267-140">Prepare the certificate that's required to run Surface UEFI Configurator.</span></span> <span data-ttu-id="27267-141">或使用您目前的憑證。</span><span class="sxs-lookup"><span data-stu-id="27267-141">Or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="27267-142">4</span><span class="sxs-lookup"><span data-stu-id="27267-142">4</span></span> | [<span data-ttu-id="27267-143">建立 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="27267-143">Create SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="27267-144">啟動 Surface UEFI 設定檔以在 USB 磁片磁碟機上建立 SEMM 套件，這將包含您需要在 Surface Hub 2 上套用的配置檔案。</span><span class="sxs-lookup"><span data-stu-id="27267-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="27267-145">將這些 SEMM 套件檔案複製到您電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="27267-145">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="27267-146">500</span><span class="sxs-lookup"><span data-stu-id="27267-146">5</span></span> | [<span data-ttu-id="27267-147">準備 USB 快閃記憶體磁片磁碟機，其中包含適用于 Surface Hub 2 的 windows 10 專業版與企業作業系統的 SEMM 套件、驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="27267-147">Prepare USB flash drive that contains Windows 10 image, SEMM package, and drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="27267-148">建立包含 Windows 10 影像的單一 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="27267-148">Create a single USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="27267-149">在這個範例中，磁片磁碟機名為 *BOOTME*。</span><span class="sxs-lookup"><span data-stu-id="27267-149">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="27267-150">在 Surface Hub 2 (的 Windows 10 專業版與企業作業系統的驅動程式和固件，請 (步驟 2) 並 SEMM 套件檔案步驟 4) 移至 *BOOTME* 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="27267-150">Add your drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (step 2) and SEMM package files (step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="27267-151">6</span><span class="sxs-lookup"><span data-stu-id="27267-151">6</span></span> | [<span data-ttu-id="27267-152">更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="27267-152">Update UEFI on Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="27267-153">使用 *BOOTME* 磁片磁碟機來啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="27267-153">Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="27267-154">utf-7</span><span class="sxs-lookup"><span data-stu-id="27267-154">7</span></span> | [<span data-ttu-id="27267-155">安裝 Windows 10 專業版或企業版1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="27267-155">Install Windows 10 Pro or Enterprise version 1903 or later.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="27267-156">使用 *BOOTME* 磁片磁碟機來安裝 Windows 10 專業版或企業版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="27267-156">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="27267-157">型</span><span class="sxs-lookup"><span data-stu-id="27267-157">8</span></span> | [<span data-ttu-id="27267-158">安裝適用于 Surface Hub 2 的 Windows 10 專業版和企業版作業系統的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="27267-158">Install drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="27267-159">為了確保您的裝置擁有所有最新的更新和驅動程式，請 [在 Surface Hub 2 的 MSI 檔案上安裝 Windows 10 專業版和企業版 OS 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="27267-159">To ensure your device has all the latest updates and drivers, install the [Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="27267-160">9</span><span class="sxs-lookup"><span data-stu-id="27267-160">9</span></span> | [<span data-ttu-id="27267-161">將 Surface Hub 2 完整設定為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="27267-161">Fully configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="27267-162">啟用建議的設定和應用程式，以將 Surface Hub 秒優化為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="27267-162">Enable recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="27267-163">驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求</span><span class="sxs-lookup"><span data-stu-id="27267-163">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="27267-164">在您將 Surface Hub 從 Windows 10 小組遷移至 Windows 10 桌上出版前，您需要至少 *694.2938.768.0*的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="27267-164">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need a UEFI version that's at least *694.2938.768.0*.</span></span>
 
<span data-ttu-id="27267-165">若要在您的系統上驗證 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="27267-165">To verify the UEFI version on your system:</span></span>

1. <span data-ttu-id="27267-166">在 Surface Hub 2 的 [首頁] 頁面上，選取 [**開始**]，然後在 [**所有應用程式**]  >  **表面**) 開啟 [Surface app] (。</span><span class="sxs-lookup"><span data-stu-id="27267-166">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="27267-167">選取 **您的 surface** 以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="27267-167">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="27267-168">如果 UEFI 版本是 *694.2938.768.0* 或更新版本，如下列影像所示，您可以建立 SEMM 套件來啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="27267-168">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![在 Surface app 中顯示您的 Surface 頁面的螢幕擷取畫面。](images/shm-fig1.png)
 
   - <span data-ttu-id="27267-170">如果 UEFI 版本早于 *694.2938.768.0*，請使用 Windows Update 取得目前的版本。</span><span class="sxs-lookup"><span data-stu-id="27267-170">If the UEFI version is earlier than *694.2938.768.0*, get a current version by using Windows Update.</span></span>

<span data-ttu-id="27267-171">若要使用 Windows Update 來更新 UEFI：</span><span class="sxs-lookup"><span data-stu-id="27267-171">To update the UEFI by using Windows Update:</span></span>

1. <span data-ttu-id="27267-172">在 Surface Hub 2 秒，請以系統 **管理員**身分登入。</span><span class="sxs-lookup"><span data-stu-id="27267-172">On your Surface Hub 2S, sign in as **Admin**.</span></span> 
    >[!Note]
    > <span data-ttu-id="27267-173">如果您不知道您的使用者名稱或系統管理員密碼，您必須重設裝置。</span><span class="sxs-lookup"><span data-stu-id="27267-173">If you don't know your username or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="27267-174">如需詳細資訊，請參閱 [重設及恢復 Surface Hub 2 秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)。</span><span class="sxs-lookup"><span data-stu-id="27267-174">For more information, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

1. <span data-ttu-id="27267-175">移至 [**所有應用程式**設定] 的 [  >  **Settings**  >  **更新與安全性**]  >  **Windows update**，然後安裝所有更新。</span><span class="sxs-lookup"><span data-stu-id="27267-175">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.</span></span> 
1. <span data-ttu-id="27267-176">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="27267-176">Restart the device.</span></span> 
1. <span data-ttu-id="27267-177">使用 Surface app 驗證 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="27267-177">Verify the UEFI version by using the Surface app.</span></span> 
2. <span data-ttu-id="27267-178">重複這些步驟，直到 UEFI 版本為 *694.2938.768.0* 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="27267-178">Repeat these steps until the UEFI version is *694.2938.768.0* or later.</span></span>
3. <span data-ttu-id="27267-179">如果您在多次嘗試後沒看到更新的 UEFI，請核取 [ **更新歷程記錄** ] 並尋找任何失敗的固件安裝實例。</span><span class="sxs-lookup"><span data-stu-id="27267-179">If you don't see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="27267-180">您可能需要重設裝置 (**設定**  >  **更新 & 安全**  >  **重設裝置**) 。</span><span class="sxs-lookup"><span data-stu-id="27267-180">You might need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="27267-181">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="27267-181">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="27267-182">在不同的電腦上：</span><span class="sxs-lookup"><span data-stu-id="27267-182">On a separate PC:</span></span>

1. <span data-ttu-id="27267-183">在 [ [表面工具] 頁面](https://www.microsoft.com/download/details.aspx?id=46703)上，選取 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="27267-183">On the [Surface Tools for IT page](https://www.microsoft.com/download/details.aspx?id=46703), select **Download**.</span></span>  
1. <span data-ttu-id="27267-184">選取並下載 Surface UEFI 設定檔 MSI 檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="27267-184">Select and download the Surface UEFI Configurator MSI file and install it on a separate PC.</span></span> <span data-ttu-id="27267-185">安裝 Windows 10 小組版時，Surface UEFI 組態工具無法在 Surface Hub 2 上執行。</span><span class="sxs-lookup"><span data-stu-id="27267-185">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while the Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="27267-186">下載 [Surface Hub 2 驅動程式和固件 Windows 安裝程式 MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案。</span><span class="sxs-lookup"><span data-stu-id="27267-186">Download the [Surface Hub 2 Drivers and Firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="27267-187">當您安裝新的作業系統時，您將會用到這個檔案。</span><span class="sxs-lookup"><span data-stu-id="27267-187">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="27267-188">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="27267-188">Prepare the SEMM certificate</span></span>

<span data-ttu-id="27267-189">如果您尚未使用 Surface UEFI 配置器，您必須準備證書。</span><span class="sxs-lookup"><span data-stu-id="27267-189">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="27267-190">這個憑證可確保在裝置註冊 SEMM 之後，您只能使用以核准憑證建立的套件來修改 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="27267-190">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span> 

<span data-ttu-id="27267-191">您取得憑證的方式取決於貴組織的規模或複雜度。</span><span class="sxs-lookup"><span data-stu-id="27267-191">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="27267-192">企業組織通常會維持自己的基礎結構，以根據標準安全慣例產生證書。</span><span class="sxs-lookup"><span data-stu-id="27267-192">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="27267-193">中型企業及其他人可能選擇從合作夥伴提供者取得憑證。</span><span class="sxs-lookup"><span data-stu-id="27267-193">Medium-sized businesses and others might choose to get certificates from partner providers.</span></span> <span data-ttu-id="27267-194">對於沒有足夠 IT 專業知識或專門 IT 安全小組的組織，建議使用此選項。</span><span class="sxs-lookup"><span data-stu-id="27267-194">This option is recommended for organizations that don't have sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="27267-195">或者，您也可以使用 PowerShell 腳本來產生自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="27267-195">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="27267-196">如需詳細資訊，請參閱 [企業管理模式證書需求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="27267-196">For more information, see the [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="27267-197">或者，您可以使用 PowerShell 建立您自己的憑證。</span><span class="sxs-lookup"><span data-stu-id="27267-197">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="27267-198">如需詳細資訊，請參閱 [新的 SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 檔。</span><span class="sxs-lookup"><span data-stu-id="27267-198">For more information, see the [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) documentation.</span></span>

<span data-ttu-id="27267-199">Surface UEFI 設定檔建立的 SEMM 套件必須以憑證加以保護。</span><span class="sxs-lookup"><span data-stu-id="27267-199">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="27267-200">憑證會驗證設定檔的簽名，然後才能套用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="27267-200">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="27267-201">如需詳細資訊，請參閱 [SEMM 檔](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="27267-201">For more information, see the [SEMM documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 
 
### <span data-ttu-id="27267-202">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="27267-202">Create a SEMM package</span></span>

1. <span data-ttu-id="27267-203">在另一部電腦上，安裝您先前下載的 Surface UEFI 組態工具。</span><span class="sxs-lookup"><span data-stu-id="27267-203">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span> 

2. <span data-ttu-id="27267-204">開啟 Surface UEFI 配置器，然後選取 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="27267-204">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![開啟 Surface UEFI 配置器。](images/shm-fig2.png)
   
3. <span data-ttu-id="27267-206">選取 [ **Surface 裝置**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27267-206">Select **Surface Devices**, and then select **Next**.</span></span>

   ![選取 [Surface 裝置]。](images/shm-fig3.png)
  
4. <span data-ttu-id="27267-208">選取 [設定 **套件**]。</span><span class="sxs-lookup"><span data-stu-id="27267-208">Select **Configuration Package**.</span></span>

   ![選取 [設定套件]。](images/shm-fig4.png)
  
5. <span data-ttu-id="27267-210">選取 [ **憑證保護**]。</span><span class="sxs-lookup"><span data-stu-id="27267-210">Select **Certificate Protection**.</span></span>

   ![選取 [憑證保護]。](images/shm-fig5.png)

   <span data-ttu-id="27267-212">系統會提示您新增憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="27267-212">You're prompted to add your certificate .pfx file.</span></span>

   ![新增您的憑證。](images/shm-fig6.png)
   
7. <span data-ttu-id="27267-214">輸入您的憑證密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27267-214">Enter your certificate password, and then select **OK**.</span></span>

   ![輸入您的憑證密碼，然後選取 [確定]。](images/shm-fig7.png)

8. <span data-ttu-id="27267-216">選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="27267-216">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="27267-217">每當您引導至 UEFI 時，就會需要此密碼。</span><span class="sxs-lookup"><span data-stu-id="27267-217">You'll need this password whenever you boot to UEFI.</span></span> <span data-ttu-id="27267-218">我們 *強烈建議* 您設定要在 Surface Hub 的2秒使用的 UEFI 密碼。</span><span class="sxs-lookup"><span data-stu-id="27267-218">We *strongly recommend* that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>

   ![選取 [密碼保護]。](images/shm-fig8.png)
   
9. <span data-ttu-id="27267-220">設定 UEFI 密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27267-220">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="27267-221">將密碼儲存在可供管理 Surface Hub 之 IT 系統管理員存取的安全位置。</span><span class="sxs-lookup"><span data-stu-id="27267-221">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> <span data-ttu-id="27267-222">如果密碼遺失，就無法復原。</span><span class="sxs-lookup"><span data-stu-id="27267-222">If the password is lost, it can't be recovered.</span></span> 

   ![輸入您的 UEFI 密碼。](images/shm-fig9.png)

10. <span data-ttu-id="27267-224">選取 [ **Surface Hub 2 秒**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27267-224">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![選取 [Surface Hub 2 秒]。](images/shm-fig10.png)
   
11. <span data-ttu-id="27267-226">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="27267-226">Select **Next**.</span></span>

    ![選取 \[下一步\]。](images/shm-fig10a.png)

12. <span data-ttu-id="27267-228">若要允許安裝 Windows 10 專業版或企業版，請開啟 **EnableOsMigration**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27267-228">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![選取 [啟用 O S 遷移]。](images/shm-fig11.png)
    
    ![將 [啟用作業系統遷移] 設定為 [開啟]。](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="27267-231">在您套用 SEMM 套件之後，請在裝置的 UEFI 功能表中，所有的 UEFI 設定都無法使用 (鎖定) 。</span><span class="sxs-lookup"><span data-stu-id="27267-231">After you apply a SEMM package, in the device's UEFI menu, all UEFI settings are unavailable (locked).</span></span> <span data-ttu-id="27267-232">其他設定（例如 **IPv6 FOR PXE 啟動** ）的預設值也無法使用。</span><span class="sxs-lookup"><span data-stu-id="27267-232">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span> 
>
><span data-ttu-id="27267-233">若要在完成遷移後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="27267-233">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="27267-234">如果您套用另一個 SEMM 套件來變更 UEFI 設定，則在建立新的 SEMM 套件時，您必須使用原始證書。</span><span class="sxs-lookup"><span data-stu-id="27267-234">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="27267-235">使用 UEFI 組態工具工具，並將 **EnableOSMigration** 關閉 (不在開啟，如原始的遷移步驟) 所示。</span><span class="sxs-lookup"><span data-stu-id="27267-235">Use the UEFI Configurator tool and leave **EnableOSMigration** off (not on, as shown in the original migration steps).</span></span>

#### <span data-ttu-id="27267-236">將 SEMM 套件儲存至 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="27267-236">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="27267-237">將 USB 磁片磁碟機連線至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="27267-237">Connect a USB drive to your PC.</span></span> 
1. <span data-ttu-id="27267-238">選擇 [ **中心2秒**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27267-238">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![選取 [USB]](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="27267-240">在建立 SEMM 套件時，會清除 USB 磁片磁碟機上的所有現有資料。</span><span class="sxs-lookup"><span data-stu-id="27267-240">All existing data on the USB drive is erased when the SEMM package is built.</span></span> <span data-ttu-id="27267-241">在建立 SEMM 套件之前，請先從您要儲存的 USB 磁片磁碟機中移除任何檔案。</span><span class="sxs-lookup"><span data-stu-id="27267-241">Before building the SEMM package, remove any files from the USB drive that you want to save.</span></span>
   
2. <span data-ttu-id="27267-242">選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="27267-242">Select **Build**.</span></span>

   ![選取 [建立]。](images/shm-fig14.png)

3. <span data-ttu-id="27267-244">捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。</span><span class="sxs-lookup"><span data-stu-id="27267-244">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="27267-245">您的 SEMM 套件現已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="27267-245">Your SEMM package is now ready.</span></span> <span data-ttu-id="27267-246">它包含 SEMM 套件 *DfciUpdate dfi* 和文字檔，其中包含 SEMM 指紋 (憑證的指紋) 中的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="27267-246">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM thumbprint (the last two characters of the certificate's thumbprint).</span></span>

   ![選取 [結束]。](images/shm-fig15.png)
   
4. <span data-ttu-id="27267-248">儲存憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="27267-248">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="27267-249">當您在 Surface Hub 2 上套用套件時，您必須使用這些字元來啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="27267-249">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="27267-250">準備包含 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式與固件的 USB 快閃記憶體磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="27267-250">Prepare a USB flash drive that contains a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="27267-251">您可以使用下列其中一個選項，在版本1903或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：</span><span class="sxs-lookup"><span data-stu-id="27267-251">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) by using one of the following options:</span></span>

- <span data-ttu-id="27267-252">您目前的影像解決方案。</span><span class="sxs-lookup"><span data-stu-id="27267-252">Your current imaging solution.</span></span>

- <span data-ttu-id="27267-253">[Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator)。</span><span class="sxs-lookup"><span data-stu-id="27267-253">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator).</span></span> <span data-ttu-id="27267-254">使用這個工具來建立可引導的 Windows 10 影像。</span><span class="sxs-lookup"><span data-stu-id="27267-254">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="27267-255">影像可以包含所有目前的 Windows 10 更新、Office、您選擇的其他應用程式，以及所需的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="27267-255">The image can include all current Windows 10 updates, Office, other apps that you choose, and the required drivers and firmware.</span></span> 

- <span data-ttu-id="27267-256">包含 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="27267-256">USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="27267-257">然後 [在 Surface Hub 2 上安裝 Windows 10 專業版和企業版作業系統的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="27267-257">Then install [drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
<span data-ttu-id="27267-258">下列程式說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後新增 SEMM 套件檔案，以及 Windows 10 專業版的驅動程式和固件（Surface Hub 2 MSI 檔案）。</span><span class="sxs-lookup"><span data-stu-id="27267-258">The following procedure describes how to create a USB flash drive from installation media, and then add the SEMM package files and the Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="27267-259">如果您使用的是其他部署方法，請前往 [Surface Hub 2 上的更新 UEFI，以啟用](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 本文中的 [作業系統遷移] 區段。</span><span class="sxs-lookup"><span data-stu-id="27267-259">If you're using other deployment methods, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="27267-260">完成安裝之後，您需要適用于 Windows 10 專業版或 Windows 10 Enterprise 的有效授權，與現有的 Windows 10 小組授權不同。</span><span class="sxs-lookup"><span data-stu-id="27267-260">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="27267-261">若要建立 Windows 10 專業版安裝，請在 [ [**下載 windows 10**](https://www.microsoft.com/software-download/windows10) ] 頁面上，依照指示下載媒體建立工具。</span><span class="sxs-lookup"><span data-stu-id="27267-261">To create a Windows 10 Pro installation, on the [**Download Windows 10**](https://www.microsoft.com/software-download/windows10) page, follow the instructions to download the media creation tool.</span></span> <span data-ttu-id="27267-262">若要下載 Windows 10 企業版，請移至 [Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="27267-262">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="27267-263">插入新的 USB 儲存空間磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="27267-263">Insert a new USB storage drive.</span></span> 
1. <span data-ttu-id="27267-264">開啟 [媒體建立工具]，選取 [ **建立安裝媒體**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27267-264">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![建立安裝媒體。](images/shm-fig16.png)
   
3. <span data-ttu-id="27267-266">選取 [語言]，然後選擇 [ **Windows 10** ] 和 [ \*\*64 位 (x64) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="27267-266">Select a language, and then choose **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="27267-267">然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27267-267">Then select **Next**.</span></span>

   ![選取 [語言]，然後選擇 [Windows 10] 和 [64 位]。](images/shm-fig17.png)
   
4. <span data-ttu-id="27267-270">選取 [ **USB 快閃記憶體磁片磁碟機**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="27267-270">Select **USB flash drive**, and then select **Next**.</span></span>

   ![選取 [U S B 快閃記憶體磁碟機]，然後選取 [下一步]。](images/shm-fig18.png)
   
5. <span data-ttu-id="27267-272">下載完成後，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="27267-272">When the download finishes, select **Finish**.</span></span>

   ![選取 [完成]。](images/shm-fig19.png)
   
6. <span data-ttu-id="27267-274">在 Surface Hub 2 上複製 SEMM 套件檔案和 Windows 10 專業版作業系統的驅動程式及固件， (MSI 檔案) 到包含您 Windows 10 影像 (*BOOTME*) 的 USB 快閃記憶體磁片磁碟機根目錄。</span><span class="sxs-lookup"><span data-stu-id="27267-274">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="27267-275">BOOTME USB 磁片磁碟機包含：</span><span class="sxs-lookup"><span data-stu-id="27267-275">The BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="27267-276">您的 Windows 10 可引導影像。</span><span class="sxs-lookup"><span data-stu-id="27267-276">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="27267-277">SEMM 套件檔案 (複製到 USB 磁片磁碟機的根目錄) 。</span><span class="sxs-lookup"><span data-stu-id="27267-277">SEMM package files (copied to the root of the USB drive).</span></span>
    
      - <span data-ttu-id="27267-278">*DfciUpdate dfi*。</span><span class="sxs-lookup"><span data-stu-id="27267-278">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="27267-279">包含 SEMM 指紋的文字檔。</span><span class="sxs-lookup"><span data-stu-id="27267-279">Text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="27267-280"> (在這個範例中，檔案是 *SurfaceUEFI_2020Aug25_1058.txt*。 ) 自動產生的日期時間戳記會對應到您使用 Surface UEFI 設定檔建立檔案的日期。</span><span class="sxs-lookup"><span data-stu-id="27267-280">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="27267-281">Surface Hub 2 上的 Windows 10 專業版與企業作業系統的驅動程式和固件 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="27267-281">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="27267-282">將此檔案複製到 USB 磁片磁碟機的根目錄。</span><span class="sxs-lookup"><span data-stu-id="27267-282">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="27267-283">更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移</span><span class="sxs-lookup"><span data-stu-id="27267-283">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="27267-284">將您的 BOOTME 硬碟插入到 Surface Hub 2 的 USB-A 埠。</span><span class="sxs-lookup"><span data-stu-id="27267-284">Insert your BOOTME drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="27267-285">如需檔案的清單，請參閱上一節。</span><span class="sxs-lookup"><span data-stu-id="27267-285">For a list of required files, see the previous section.</span></span>

2. <span data-ttu-id="27267-286">若要引導至 UEFI：</span><span class="sxs-lookup"><span data-stu-id="27267-286">To boot into UEFI:</span></span>

   1. <span data-ttu-id="27267-287">關閉) Surface Hub 2 的 (關閉。</span><span class="sxs-lookup"><span data-stu-id="27267-287">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="27267-288">按住 [ **音量 +**]，然後按下再放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="27267-288">Press and hold **Volume +**, and then press and release the power button.</span></span>
   1. <span data-ttu-id="27267-289">保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。</span><span class="sxs-lookup"><span data-stu-id="27267-289">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![按住調高音量按鈕，直到 UEFI 功能表出現為止。](images/shm-fig20.png)
      
3. <span data-ttu-id="27267-291">當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (強烈建議) ）。</span><span class="sxs-lookup"><span data-stu-id="27267-291">When the device restarts, enter the UEFI password that you created earlier, if applicable (strongly recommended).</span></span>

   ![輸入 UEFI 密碼。](images/shm-fig22.png)
   
4. <span data-ttu-id="27267-293">在 UEFI 功能表中，選取**Management**[  >  **從 USB 安裝**管理元件]。</span><span class="sxs-lookup"><span data-stu-id="27267-293">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![選取 [管理] 並從 U S B 安裝。](images/shm-fig21.png)
   
5. <span data-ttu-id="27267-295">選取 [ **立即重新開機**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="27267-295">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="27267-296">裝置會重新開機。</span><span class="sxs-lookup"><span data-stu-id="27267-296">The device reboots.</span></span> <span data-ttu-id="27267-297">它會在視窗中間顯示白色 Microsoft 標誌，然後關閉。</span><span class="sxs-lookup"><span data-stu-id="27267-297">It displays a white Microsoft logo in the middle of the window and then shuts down.</span></span>

   ![選取 [立即重新開機]。](images/shm-fig25.png)
   
6. <span data-ttu-id="27267-299">按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="27267-299">Press and release the power button.</span></span> <span data-ttu-id="27267-300">在出現的紅色視窗中，啟動 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="27267-300">In the red window that appears, activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="27267-301">輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。</span><span class="sxs-lookup"><span data-stu-id="27267-301">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="27267-302">然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="27267-302">Then select **OK**.</span></span>

   ![輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="27267-304">在裝置上啟用 SEMM 之後，就會套用新的 UEFI 設定 **EnableOSMigration** 。</span><span class="sxs-lookup"><span data-stu-id="27267-304">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="27267-305">您將無法再存取 Windows 10 小組。</span><span class="sxs-lookup"><span data-stu-id="27267-305">You'll no longer be able to access Windows 10 Team.</span></span> <span data-ttu-id="27267-306">相反地，您必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="27267-306">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

   <span data-ttu-id="27267-307">裝置會重新開機。</span><span class="sxs-lookup"><span data-stu-id="27267-307">The device reboots.</span></span> <span data-ttu-id="27267-308">它會在畫面中間顯示白色標誌，然後再次關閉。</span><span class="sxs-lookup"><span data-stu-id="27267-308">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="27267-309">安裝 Windows 10 專業版或企業版</span><span class="sxs-lookup"><span data-stu-id="27267-309">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="27267-310">如果您的可引導 Windows 10 專業版或企業版磁碟機尚不在 Surface Hub 2 USB-A 埠中，請立即插入。</span><span class="sxs-lookup"><span data-stu-id="27267-310">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="27267-311">然後按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="27267-311">Then press and release the power button.</span></span> 

    <span data-ttu-id="27267-312">裝置啟動時，您會在畫面中間看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="27267-312">When the device starts, you see the white logo in the middle of the screen.</span></span> <span data-ttu-id="27267-313">接著，您會看到白色標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="27267-313">Then you see a spinning circle below the white logo.</span></span>

3. <span data-ttu-id="27267-314">如果裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置 (拔下電源線，然後再插回) 。</span><span class="sxs-lookup"><span data-stu-id="27267-314">If the device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="27267-315">再次插入電源線之後，裝置會在幾秒後啟動。</span><span class="sxs-lookup"><span data-stu-id="27267-315">After you plug the power cord in again, the device should boot after a few seconds.</span></span> <span data-ttu-id="27267-316">然後，您會在畫面中間看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="27267-316">Then you'll see the white logo in the middle of screen.</span></span> 

    <span data-ttu-id="27267-317">如果裝置沒有開啟，請按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="27267-317">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="27267-318">在畫面中間看到標誌之後，按住 [音量] 按鈕，直到您看到白色標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="27267-318">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![從 U S B 磁片磁碟機啟動至 Windows 10。](images/shm-fig26.png)
   
4. <span data-ttu-id="27267-320">當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或 Enterprise (版本1903或) 更新版本。</span><span class="sxs-lookup"><span data-stu-id="27267-320">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="27267-321">安裝 Surface Hub 2 驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="27267-321">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="27267-322">為了確保您的裝置擁有所有最新的更新和驅動程式，請 [在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 ENTERPRISE OS 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="27267-322">To ensure your device has all the latest updates and drivers, install [drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
## <span data-ttu-id="27267-323">設定建議的設定</span><span class="sxs-lookup"><span data-stu-id="27267-323">Configure recommended settings</span></span>

<span data-ttu-id="27267-324">若要將 Surface Hub 2 完整設定為個人生產力裝置，請參閱在 [Surface Hub 2 上設定 Windows 10 專業版或企業版](surface-hub-2-post-install.md)。</span><span class="sxs-lookup"><span data-stu-id="27267-324">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="27267-325">如果本文所述的步驟無法成功將您的裝置遷移至 Windows 10 專業版或 Surface Hub 2 的 Enterprise，請接觸 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="27267-325">If the steps outlined in this article don't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2, contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="27267-326">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="27267-326">Roll back to Windows 10 Team</span></span>

<span data-ttu-id="27267-327">如果您想要將裝置還原至 Windows 10 小組，請參閱 [重設及恢復 Surface Hub 2 秒](surface-hub-2s-recover-reset.md)。</span><span class="sxs-lookup"><span data-stu-id="27267-327">If you want to restore your device to Windows 10 Team, see [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

## <span data-ttu-id="27267-328">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="27267-328">Version history</span></span>

<span data-ttu-id="27267-329">下表摘要列出本文所做的變更。</span><span class="sxs-lookup"><span data-stu-id="27267-329">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="27267-330">版本</span><span class="sxs-lookup"><span data-stu-id="27267-330">Version</span></span> | <span data-ttu-id="27267-331">日期</span><span class="sxs-lookup"><span data-stu-id="27267-331">Date</span></span>               | <span data-ttu-id="27267-332">描述</span><span class="sxs-lookup"><span data-stu-id="27267-332">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="27267-333">向量.</span><span class="sxs-lookup"><span data-stu-id="27267-333">v.</span></span> <span data-ttu-id="27267-334">1.2</span><span class="sxs-lookup"><span data-stu-id="27267-334">1.2</span></span>  | <span data-ttu-id="27267-335">2020年9月29日</span><span class="sxs-lookup"><span data-stu-id="27267-335">September 29, 2020</span></span> | <span data-ttu-id="27267-336">針對可用性意見反應的各種更新。</span><span class="sxs-lookup"><span data-stu-id="27267-336">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="27267-337">向量.</span><span class="sxs-lookup"><span data-stu-id="27267-337">v.</span></span> <span data-ttu-id="27267-338">1.1</span><span class="sxs-lookup"><span data-stu-id="27267-338">1.1</span></span>  | <span data-ttu-id="27267-339">2020年9月15日</span><span class="sxs-lookup"><span data-stu-id="27267-339">September 15, 2020</span></span> | <span data-ttu-id="27267-340">在簡介中放置了說明安裝新作業系統的授權需求。</span><span class="sxs-lookup"><span data-stu-id="27267-340">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="27267-341">向量.</span><span class="sxs-lookup"><span data-stu-id="27267-341">v.</span></span> <span data-ttu-id="27267-342">1.0</span><span class="sxs-lookup"><span data-stu-id="27267-342">1.0</span></span>  | <span data-ttu-id="27267-343">2020年9月1日</span><span class="sxs-lookup"><span data-stu-id="27267-343">September 1, 2020</span></span>  | <span data-ttu-id="27267-344">新文章。</span><span class="sxs-lookup"><span data-stu-id="27267-344">New article.</span></span>                                                                                           |
