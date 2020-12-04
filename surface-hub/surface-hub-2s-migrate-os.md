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
ms.date: 12/03/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 01c5c8a5c6b9f7ed657829fe792fc9eecd1facb5
ms.sourcegitcommit: 5d02cca9ca8c0a252798c2fc0a89dbda81911c44
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/04/2020
ms.locfileid: "11195398"
---
# <span data-ttu-id="4b1f6-104">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="4b1f6-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="4b1f6-105">Surface Hub 秒是預先預先安裝了 Windows 10 團隊。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-105">Surface Hub 2S comes preinstalled with Windows 10 Team.</span></span> <span data-ttu-id="4b1f6-106">此自訂版本的 Windows 10 是設計來協助在會議室環境中共同作業。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-106">This customized edition of Windows 10 is designed to facilitate collaboration in meeting room environments.</span></span> <span data-ttu-id="4b1f6-107">現在，您可以選擇執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="4b1f6-108">與典型的升級或遷移不同，此程式必須遵循說明性程式，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described in this article.</span></span> <span data-ttu-id="4b1f6-109">繼續之前，請先查看 [解決方案元件](#solution-components) 與 [遷移及安裝工作流程](#migration-and-installation-workflow-summary) 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before you continue.</span></span>


> [!NOTE]
> <span data-ttu-id="4b1f6-110">當您安裝 Windows 10 專業版或企業版時，您需要與現有的 Windows 10 小組授權不同的新授權。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-110">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="4b1f6-111">使用個別的電腦和可下載的工具 *SURFACE UEFI 配置*器，從 Windows 10 小組開始遷移。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-111">Start the migration from Windows 10 Team by using a separate PC and the downloadable tool *Surface UEFI Configurator*.</span></span> <span data-ttu-id="4b1f6-112">使用此工具來建立包含您套用至 Surface Hub 2 秒的新 UEFI 設定的套件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-112">Use the tool  to create a package that contains a new UEFI setting that you apply to Surface Hub 2S.</span></span>  

<span data-ttu-id="4b1f6-113">Surface UEFI 配置處理常式在 (SEMM) 中，成為 Surface Enterprise 管理模式的介面。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-113">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="4b1f6-114">它旨在協助集中管理公司環境中的 Surface 裝置上的固件設定。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-114">It's designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="4b1f6-115">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> MICROSOFT SEMM 檔</span><span class="sxs-lookup"><span data-stu-id="4b1f6-115">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank">Microsoft SEMM documentation</span></span></a>
 

## <span data-ttu-id="4b1f6-116">解決方案元件</span><span class="sxs-lookup"><span data-stu-id="4b1f6-116">Solution components</span></span>

- <span data-ttu-id="4b1f6-117">執行 Windows 10 小組作業系統的 Surface Hub 2 秒裝置</span><span class="sxs-lookup"><span data-stu-id="4b1f6-117">Surface Hub 2S device running the Windows 10 Team operating system</span></span>
- <span data-ttu-id="4b1f6-118">運行 Windows 10 的個別裝置</span><span class="sxs-lookup"><span data-stu-id="4b1f6-118">Separate device running Windows 10</span></span>
- <span data-ttu-id="4b1f6-119">用於建立 SEMM 套件的 Surface UEFI 設定檔工具</span><span class="sxs-lookup"><span data-stu-id="4b1f6-119">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="4b1f6-120">Windows 10 專業版或企業版作業系統影像、版本1903或更新版本</span><span class="sxs-lookup"><span data-stu-id="4b1f6-120">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="4b1f6-121">兩個有 16 GB 儲存空間的 USB 磁片磁碟機，FAT32 格式</span><span class="sxs-lookup"><span data-stu-id="4b1f6-121">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="4b1f6-122">Windows 10 專業版和企業作業系統在 Surface Hub 2 上的驅動程式與固件，Microsoft Windows Installer (的 MSI) 檔案</span><span class="sxs-lookup"><span data-stu-id="4b1f6-122">The Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="4b1f6-123">網際網路連線</span><span class="sxs-lookup"><span data-stu-id="4b1f6-123">Internet connection</span></span>
- <span data-ttu-id="4b1f6-124">影像處理方案 (選用) </span><span class="sxs-lookup"><span data-stu-id="4b1f6-124">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="4b1f6-125">遷移和安裝工作流程摘要</span><span class="sxs-lookup"><span data-stu-id="4b1f6-125">Migration and installation workflow summary</span></span>

| <span data-ttu-id="4b1f6-126">步驟</span><span class="sxs-lookup"><span data-stu-id="4b1f6-126">Step</span></span>  | <span data-ttu-id="4b1f6-127">動作</span><span class="sxs-lookup"><span data-stu-id="4b1f6-127">Action</span></span>                                                                                                 | <span data-ttu-id="4b1f6-128">摘要</span><span class="sxs-lookup"><span data-stu-id="4b1f6-128">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="4b1f6-129">sr-1</span><span class="sxs-lookup"><span data-stu-id="4b1f6-129">1</span></span> | [<span data-ttu-id="4b1f6-130">確認 Surface Hub 2 上的 UEFI 版本符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-130">Verify that the UEFI version on Surface Hub 2S meets minimum requirements.</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="4b1f6-131">確定 UEFI 版本為694.2938.768.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-131">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="4b1f6-132">pplx-2</span><span class="sxs-lookup"><span data-stu-id="4b1f6-132">2</span></span> | [<span data-ttu-id="4b1f6-133">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-133">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="4b1f6-134">在 [ <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **表面工具**] 頁面上 </a> ，選取 [**下載**]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-134">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">**Surface Tools for IT** page</a>, select **Download**.</span></span> <span data-ttu-id="4b1f6-135">然後選取並下載 **SURFACE UEFI 配置器。MSI** 檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-135">Then select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="4b1f6-136">下載 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 適用于 Surface Hub 2 MSI 檔案的 Windows 10 專業版和企業版 OS 的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-136">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a> <span data-ttu-id="4b1f6-137">將它儲存在步驟5中以供使用。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-137">Save it for use in step 5.</span></span> |
| <span data-ttu-id="4b1f6-138">3</span><span class="sxs-lookup"><span data-stu-id="4b1f6-138">3</span></span> | [<span data-ttu-id="4b1f6-139">準備 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-139">Prepare SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="4b1f6-140">準備運行 Surface UEFI 配置器所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-140">Prepare the certificate that's required to run Surface UEFI Configurator.</span></span> <span data-ttu-id="4b1f6-141">或使用您目前的憑證。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-141">Or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="4b1f6-142">4</span><span class="sxs-lookup"><span data-stu-id="4b1f6-142">4</span></span> | [<span data-ttu-id="4b1f6-143">建立 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-143">Create SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="4b1f6-144">啟動 Surface UEFI 設定檔以在 USB 磁片磁碟機上建立 SEMM 套件，這將包含您需要在 Surface Hub 2 上套用的配置檔案。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="4b1f6-145">將這些 SEMM 套件檔案複製到您電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-145">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="4b1f6-146">500</span><span class="sxs-lookup"><span data-stu-id="4b1f6-146">5</span></span> | [<span data-ttu-id="4b1f6-147">準備 USB 快閃記憶體磁片磁碟機，其中包含適用于 Surface Hub 2 的 windows 10 專業版與企業作業系統的 SEMM 套件、驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-147">Prepare USB flash drive that contains Windows 10 image, SEMM package, and drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="4b1f6-148">建立包含 Windows 10 影像的單一 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-148">Create a single USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="4b1f6-149">在這個範例中，磁片磁碟機名為 *BOOTME*。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-149">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="4b1f6-150">在 Surface Hub 2 (的 Windows 10 專業版與企業作業系統的驅動程式和固件，請 (步驟 2) 並 SEMM 套件檔案步驟 4) 移至 *BOOTME* 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-150">Add your drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (step 2) and SEMM package files (step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="4b1f6-151">6</span><span class="sxs-lookup"><span data-stu-id="4b1f6-151">6</span></span> | [<span data-ttu-id="4b1f6-152">更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-152">Update UEFI on Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="4b1f6-153">使用 *BOOTME* 磁片磁碟機來啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-153">Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="4b1f6-154">utf-7</span><span class="sxs-lookup"><span data-stu-id="4b1f6-154">7</span></span> | [<span data-ttu-id="4b1f6-155">安裝 Windows 10 專業版或企業版1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-155">Install Windows 10 Pro or Enterprise version 1903 or later.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="4b1f6-156">使用 *BOOTME* 磁片磁碟機來安裝 Windows 10 專業版或企業版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-156">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="4b1f6-157">型</span><span class="sxs-lookup"><span data-stu-id="4b1f6-157">8</span></span> | [<span data-ttu-id="4b1f6-158">安裝適用于 Surface Hub 2 的 Windows 10 專業版和企業版作業系統的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-158">Install drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="4b1f6-159">為了確保您的裝置擁有所有最新的更新和驅動程式，請 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 的 MSI 檔案上安裝 Windows 10 專業版和企業版 OS 的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-159">To ensure your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="4b1f6-160">9</span><span class="sxs-lookup"><span data-stu-id="4b1f6-160">9</span></span> | [<span data-ttu-id="4b1f6-161">將 Surface Hub 2 完整設定為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-161">Fully configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="4b1f6-162">啟用建議的設定和應用程式，以將 Surface Hub 秒優化為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-162">Enable recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="4b1f6-163">驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求</span><span class="sxs-lookup"><span data-stu-id="4b1f6-163">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="4b1f6-164">在您將 Surface Hub 從 Windows 10 小組遷移至 Windows 10 桌上出版前，您需要至少 *694.2938.768.0*的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-164">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need a UEFI version that's at least *694.2938.768.0*.</span></span>
 
**<span data-ttu-id="4b1f6-165">若要在您的系統上驗證 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="4b1f6-165">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="4b1f6-166">在 Surface Hub 2 的 [首頁] 頁面上，選取 [**開始**]，然後在 [**所有應用程式**]  >  **表面**) 開啟 [Surface app] (。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-166">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="4b1f6-167">選取 **您的 surface** 以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-167">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="4b1f6-168">如果 UEFI 版本是 *694.2938.768.0* 或更新版本，如下列影像所示，您可以建立 SEMM 套件來啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-168">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![在 Surface app 中顯示您的 Surface 頁面的螢幕擷取畫面。](images/shm-fig1.png)
 
   - <span data-ttu-id="4b1f6-170">如果 UEFI 版本早于版本694.2938.768.0，您將需要安裝 Windows 10 Team 2020 更新裸機復原 (BMR) 影像或使用 Windows Update 來取得目前版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-170">If the UEFI version is earlier than version 694.2938.768.0, you will need to obtain a current version by either installing the Window 10 Team 2020 Update Bare Metal Recovery (BMR) image, or by using Windows Update.</span></span>
   
**<span data-ttu-id="4b1f6-171">若要透過 Windows Update 更新 UEFI：</span><span class="sxs-lookup"><span data-stu-id="4b1f6-171">To update UEFI via Windows Update:</span></span>**

1. <span data-ttu-id="4b1f6-172">在 Surface Hub 2 秒，請以系統 **管理員**身分登入。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-172">On your Surface Hub 2S, sign in as **Admin**.</span></span> 
    >[!Note]
    > <span data-ttu-id="4b1f6-173">如果您不知道您的使用者名稱或系統管理員密碼，您必須重設裝置。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-173">If you don't know your username or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="4b1f6-174">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> 重設及恢復 Surface Hub 2 秒。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-174">For more information, see <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank">Reset and recovery for Surface Hub 2S.</span></span></a>

1. <span data-ttu-id="4b1f6-175">移至 [**所有應用程式**設定] 的 [  >  **Settings**  >  **更新與安全性**]  >  **Windows update**，然後安裝所有更新。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-175">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.</span></span> 
1. <span data-ttu-id="4b1f6-176">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-176">Restart the device.</span></span> 
1. <span data-ttu-id="4b1f6-177">使用 Surface app 驗證 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-177">Verify the UEFI version by using the Surface app.</span></span> 
1. <span data-ttu-id="4b1f6-178">在此情況下，如果 UEFI 版本尚不是版本694.2938.768.0 或更新版本，您可以重複上述步驟，或安裝 Windows 10 Team 2020 更新裸機復原 (BMR) 影像，即可取得最新的 UEFI。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-178">At this point, if the UEFI version is not yet version  694.2938.768.0 or later, you can either repeat the above steps, or you can get the latest UEFI by installing the Windows 10 Team 2020 Update Bare Metal Recovery (BMR) image.</span></span>

**<span data-ttu-id="4b1f6-179">若要透過裸機復原來更新 UEFI (BMR) 影像：</span><span class="sxs-lookup"><span data-stu-id="4b1f6-179">To update UEFI via Bare Metal Recovery (BMR) image:</span></span>**

1.  <span data-ttu-id="4b1f6-180">移至 [ [surface](https://support.microsoft.com/surfacerecoveryimage)復原] 網站，然後選取 [ **Surface Hub 2 秒**]</span><span class="sxs-lookup"><span data-stu-id="4b1f6-180">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**</span></span>
3.  <span data-ttu-id="4b1f6-181">輸入您的中樞序列值， (位於中樞背面，位於 [電源連接] 旁邊。 ) </span><span class="sxs-lookup"><span data-stu-id="4b1f6-181">Enter your Hub Serial Number (located on the rear side of the Hub next to the power connection.)</span></span>
4.  <span data-ttu-id="4b1f6-182">按照指示，透過安裝 Windows 10 Team 2020 更新，將影像下載到格式化的 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-182">Follow the directions to download the image onto a formatted USB drive through installing the Windows 10 Team 2020 Update.</span></span>
5.  <span data-ttu-id="4b1f6-183">更新完成之後，裝置第一次進入 OOBE 時，您不需要完成 OOBE，就會更新 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-183">After the update has completed and the device enters the OOBE first time setup, you do not need to complete OOBE, the UEFI version will be updated.</span></span> <span data-ttu-id="4b1f6-184">請改為按住電源按鈕，直到螢幕關閉為止，再關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-184">Instead power down the device by holding the power button until the screen turns off.</span></span> 

### <span data-ttu-id="4b1f6-185">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="4b1f6-185">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="4b1f6-186">在不同的電腦上：</span><span class="sxs-lookup"><span data-stu-id="4b1f6-186">On a separate PC:</span></span>

1. <span data-ttu-id="4b1f6-187">在 [ <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> 表面工具] 頁面上 </a> ，選取 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-187">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>  
1. <span data-ttu-id="4b1f6-188">選取並下載 Surface UEFI 設定檔 MSI 檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-188">Select and download the Surface UEFI Configurator MSI file and install it on a separate PC.</span></span> <span data-ttu-id="4b1f6-189">安裝 Windows 10 小組版時，Surface UEFI 組態工具無法在 Surface Hub 2 上執行。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-189">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while the Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="4b1f6-190">下載 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 驅動程式和固件 Windows 安裝程式 MSI 檔案 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-190">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Surface Hub 2 Drivers and Firmware Windows Installer MSI file</a>.</span></span> <span data-ttu-id="4b1f6-191">當您安裝新的作業系統時，您將會用到這個檔案。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-191">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="4b1f6-192">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="4b1f6-192">Prepare the SEMM certificate</span></span>

<span data-ttu-id="4b1f6-193">如果您尚未使用 Surface UEFI 配置器，您必須準備證書。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-193">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="4b1f6-194">這個憑證可確保在裝置註冊 SEMM 之後，您只能使用以核准憑證建立的套件來修改 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-194">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span> 

<span data-ttu-id="4b1f6-195">您取得憑證的方式取決於貴組織的規模或複雜度。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-195">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="4b1f6-196">企業組織通常會維持自己的基礎結構，以根據標準安全慣例產生證書。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-196">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="4b1f6-197">中型企業及其他人可能選擇從合作夥伴提供者取得憑證。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-197">Medium-sized businesses and others might choose to get certificates from partner providers.</span></span> <span data-ttu-id="4b1f6-198">對於沒有足夠 IT 專業知識或專門 IT 安全小組的組織，建議使用此選項。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-198">This option is recommended for organizations that don't have sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="4b1f6-199">或者，您也可以使用 PowerShell 腳本來產生自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-199">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="4b1f6-200">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> 企業管理模式證書需求 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-200">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank">Surface Enterprise Management Mode certificate requirements </a>.</span></span> <span data-ttu-id="4b1f6-201">或者，您可以使用 PowerShell 建立您自己的憑證。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-201">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="4b1f6-202">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> 新的 SelfSignedCertificate </a> 檔。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-202">For more information, see the <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate</a> documentation.</span></span>

<span data-ttu-id="4b1f6-203">Surface UEFI 設定檔建立的 SEMM 套件必須以憑證加以保護。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-203">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="4b1f6-204">憑證會驗證設定檔的簽名，然後才能套用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-204">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="4b1f6-205">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 檔 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-205">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM documentation</a>.</span></span>
 
 
### <span data-ttu-id="4b1f6-206">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="4b1f6-206">Create a SEMM package</span></span>

1. <span data-ttu-id="4b1f6-207">在另一部電腦上，安裝您先前下載的 Surface UEFI 組態工具。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-207">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span> 

2. <span data-ttu-id="4b1f6-208">開啟 Surface UEFI 配置器，然後選取 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-208">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![開啟 Surface UEFI 配置器。](images/shm-fig2.png)
   
3. <span data-ttu-id="4b1f6-210">選取 [ **Surface 裝置**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-210">Select **Surface Devices**, and then select **Next**.</span></span>

   ![選取 [Surface 裝置]。](images/shm-fig3.png)
  
4. <span data-ttu-id="4b1f6-212">選取 [設定 **套件**]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-212">Select **Configuration Package**.</span></span>

   ![選取 [設定套件]。](images/shm-fig4.png)
  
5. <span data-ttu-id="4b1f6-214">選取 [ **憑證保護**]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-214">Select **Certificate Protection**.</span></span>

   ![選取 [憑證保護]。](images/shm-fig5.png)

   <span data-ttu-id="4b1f6-216">系統會提示您新增憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-216">You're prompted to add your certificate .pfx file.</span></span>

   ![新增您的憑證。](images/shm-fig6.png)
   
7. <span data-ttu-id="4b1f6-218">輸入您的憑證密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-218">Enter your certificate password, and then select **OK**.</span></span>

   ![輸入您的憑證密碼，然後選取 [確定]。](images/shm-fig7.png)

8. <span data-ttu-id="4b1f6-220">選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-220">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="4b1f6-221">每當您引導至 UEFI 時，就會需要此密碼。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-221">You'll need this password whenever you boot to UEFI.</span></span> <span data-ttu-id="4b1f6-222">我們 *強烈建議* 您設定要在 Surface Hub 的2秒使用的 UEFI 密碼。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-222">We *strongly recommend* that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>

   ![選取 [密碼保護]。](images/shm-fig8.png)
   
9. <span data-ttu-id="4b1f6-224">設定 UEFI 密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-224">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4b1f6-225">將密碼儲存在可供管理 Surface Hub 之 IT 系統管理員存取的安全位置。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-225">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> <span data-ttu-id="4b1f6-226">如果密碼遺失，就無法復原。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-226">If the password is lost, it can't be recovered.</span></span> 

   ![輸入您的 UEFI 密碼。](images/shm-fig9.png)

10. <span data-ttu-id="4b1f6-228">選取 [ **Surface Hub 2 秒**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-228">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![選取 [Surface Hub 2 秒]。](images/shm-fig10.png)
   
11. <span data-ttu-id="4b1f6-230">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-230">Select **Next**.</span></span>

    ![選取 \[下一步\]。](images/shm-fig10a.png)

12. <span data-ttu-id="4b1f6-232">若要允許安裝 Windows 10 專業版或企業版，請開啟 **EnableOsMigration**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-232">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![選取 [啟用 O S 遷移]。](images/shm-fig11.png)
    
    ![將 [啟用作業系統遷移] 設定為 [開啟]。](images/shm-fig12.png)

### <span data-ttu-id="4b1f6-235">管理 SEMM 登記</span><span class="sxs-lookup"><span data-stu-id="4b1f6-235">Managing SEMM enrollment</span></span>

<span data-ttu-id="4b1f6-236">將裝置註冊至 SEMM 會影響您管理裝置的後續方式。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-236">Enrolling devices into SEMM affects how you can manage the device going forward.</span></span> <span data-ttu-id="4b1f6-237">例如，在您套用 SEMM 套件之後，在裝置的 UEFI 功能表中，所有 UEFI 設定都無法使用 (鎖定) 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-237">For example, after you apply a SEMM package, in the device's UEFI menu, all UEFI settings are unavailable (locked).</span></span> <span data-ttu-id="4b1f6-238">其他設定（例如 **IPv6 FOR PXE 啟動** ）的預設值也無法使用。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-238">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span> 

<span data-ttu-id="4b1f6-239">若要在完成遷移後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-239">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="4b1f6-240">如果您套用另一個 SEMM 套件來變更 UEFI 設定，則在建立新的 SEMM 套件時，您必須使用原始證書。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-240">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="4b1f6-241">使用 UEFI 組態工具工具，並將 **EnableOSMigration** 關閉 (不在開啟，如原始的遷移步驟) 所示。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-241">Use the UEFI Configurator tool and leave **EnableOSMigration** off (not on, as shown in the original migration steps).</span></span>

#### <span data-ttu-id="4b1f6-242">與合作夥伴合作</span><span class="sxs-lookup"><span data-stu-id="4b1f6-242">Working with partners</span></span>

<span data-ttu-id="4b1f6-243">如果您的公司已將遷移移至 Windows 10 專業版或 Surface Hub 2 上的企業，您可能會想要讓合作夥伴將 SEMM 憑證、SEMM 套件和 UEFI 密碼轉讓給您。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-243">If your company is outsourcing the migration to Windows 10 Pro or Enterprise on Surface Hub 2, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span>  <span data-ttu-id="4b1f6-244">或者，在您遷移中心之後，您可以立即取消從 SEMM 進行註冊，這將允許對 UEFI 進行本機管理，並將裝置傳輸至另一方。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-244">Alternatively, after migrating the Hub, you can immediately un-enroll it from SEMM, which will allow local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="4b1f6-245">不過，仍強烈建議使用 UEFI 密碼（可在遷移之後進行設定）。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-245">Nevertheless, it's still strongly recommended to use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="4b1f6-246">若要深入瞭解，請參閱 [管理 SURFACE UEFI 設定](https://docs.microsoft.com/surface/manage-surface-uefi-settings)。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-246">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <span data-ttu-id="4b1f6-247">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="4b1f6-247">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="4b1f6-248">如果您在遷移之後選擇將裝置還原至 Windows 10 小組（ [如下所述](#roll-back-to-windows-10-team)），建議您首先取消從 SEMM 取消中樞。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-248">If after migrating you choose to restore your device to Windows 10 Team, [as described below](#roll-back-to-windows-10-team), it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="4b1f6-249">若要深入瞭解，請參閱 [從 SEMM 取消註冊 Surface 裝置](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-249">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>


#### <span data-ttu-id="4b1f6-250">將 SEMM 套件儲存至 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="4b1f6-250">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="4b1f6-251">將 USB 磁片磁碟機連線至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-251">Connect a USB drive to your PC.</span></span> 
1. <span data-ttu-id="4b1f6-252">選擇 [ **中心2秒**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-252">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![選取 [USB]](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="4b1f6-254">在建立 SEMM 套件時，會清除 USB 磁片磁碟機上的所有現有資料。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-254">All existing data on the USB drive is erased when the SEMM package is built.</span></span> <span data-ttu-id="4b1f6-255">在建立 SEMM 套件之前，請先從您要儲存的 USB 磁片磁碟機中移除任何檔案。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-255">Before building the SEMM package, remove any files from the USB drive that you want to save.</span></span>
   
2. <span data-ttu-id="4b1f6-256">選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-256">Select **Build**.</span></span>

   ![選取 [建立]。](images/shm-fig14.png)

3. <span data-ttu-id="4b1f6-258">捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-258">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="4b1f6-259">您的 SEMM 套件現已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-259">Your SEMM package is now ready.</span></span> <span data-ttu-id="4b1f6-260">它包含 SEMM 套件 *DfciUpdate dfi* 和文字檔，其中包含 SEMM 指紋 (憑證的指紋) 中的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-260">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM thumbprint (the last two characters of the certificate's thumbprint).</span></span>

   ![選取 [結束]。](images/shm-fig15.png)
   
4. <span data-ttu-id="4b1f6-262">儲存憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-262">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="4b1f6-263">當您在 Surface Hub 2 上套用套件時，您必須使用這些字元來啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-263">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="4b1f6-264">準備包含 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式與固件的 USB 快閃記憶體磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="4b1f6-264">Prepare a USB flash drive that contains a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="4b1f6-265">您可以使用下列其中一個選項，在版本1903或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：</span><span class="sxs-lookup"><span data-stu-id="4b1f6-265">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) by using one of the following options:</span></span>

- <span data-ttu-id="4b1f6-266">您目前的影像解決方案。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-266">Your current imaging solution.</span></span>

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> <span data-ttu-id="4b1f6-267">Surface 部署加速器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-267">Surface Deployment Accelerator</a>.</span></span> <span data-ttu-id="4b1f6-268">使用這個工具來建立可引導的 Windows 10 影像。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-268">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="4b1f6-269">影像可以包含所有目前的 Windows 10 更新、Office、您選擇的其他應用程式，以及所需的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-269">The image can include all current Windows 10 updates, Office, other apps that you choose, and the required drivers and firmware.</span></span> 

- <span data-ttu-id="4b1f6-270">包含 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-270">USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="4b1f6-271">然後 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 上安裝 Windows 10 專業版和企業版作業系統的驅動程式和固件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-271">Then install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
<span data-ttu-id="4b1f6-272">下列程式說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後新增 SEMM 套件檔案，以及 Windows 10 專業版的驅動程式和固件（Surface Hub 2 MSI 檔案）。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-272">The following procedure describes how to create a USB flash drive from installation media, and then add the SEMM package files and the Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="4b1f6-273">如果您使用的是其他部署方法，請前往 [Surface Hub 2 上的更新 UEFI，以啟用](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 本文中的 [作業系統遷移] 區段。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-273">If you're using other deployment methods, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="4b1f6-274">完成安裝之後，您需要適用于 Windows 10 專業版或 Windows 10 Enterprise 的有效授權，與現有的 Windows 10 小組授權不同。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-274">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="4b1f6-275">若要建立 Windows 10 專業版安裝，請在 [ <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> 下載 windows 10] </a> 頁面上，依照指示下載媒體建立工具。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-275">To create a Windows 10 Pro installation, on the<a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Download Windows 10</a> page, follow the instructions to download the media creation tool.</span></span> <span data-ttu-id="4b1f6-276">若要下載 Windows 10 企業版，請移至 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft 大量授權服務中心 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-276">To download Windows 10 Enterprise, go to the <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft Volume Licensing Service Center</a>.</span></span>

2. <span data-ttu-id="4b1f6-277">插入新的 USB 儲存空間磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-277">Insert a new USB storage drive.</span></span> 
1. <span data-ttu-id="4b1f6-278">開啟 [媒體建立工具]，選取 [ **建立安裝媒體**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-278">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![建立安裝媒體。](images/shm-fig16.png)
   
3. <span data-ttu-id="4b1f6-280">選取 [語言]，然後選擇 [ **Windows 10** ] 和 [ \*\*64 位 (x64) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-280">Select a language, and then choose **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="4b1f6-281">然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-281">Then select **Next**.</span></span>

   ![選取 [語言]，然後選擇 [Windows 10] 和 [64 位]。](images/shm-fig17.png)
   
4. <span data-ttu-id="4b1f6-284">選取 [ **USB 快閃記憶體磁片磁碟機**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-284">Select **USB flash drive**, and then select **Next**.</span></span>

   ![選取 [U S B 快閃記憶體磁碟機]，然後選取 [下一步]。](images/shm-fig18.png)
   
5. <span data-ttu-id="4b1f6-286">下載完成後，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-286">When the download finishes, select **Finish**.</span></span>

   ![選取 [完成]。](images/shm-fig19.png)
   
6. <span data-ttu-id="4b1f6-288">在 Surface Hub 2 上複製 SEMM 套件檔案和 Windows 10 專業版作業系統的驅動程式及固件， (MSI 檔案) 到包含您 Windows 10 影像 (*BOOTME*) 的 USB 快閃記憶體磁片磁碟機根目錄。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-288">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="4b1f6-289">BOOTME USB 磁片磁碟機包含：</span><span class="sxs-lookup"><span data-stu-id="4b1f6-289">The BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="4b1f6-290">您的 Windows 10 可引導影像。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-290">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="4b1f6-291">SEMM 套件檔案 (複製到 USB 磁片磁碟機的根目錄) 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-291">SEMM package files (copied to the root of the USB drive).</span></span>
    
      - <span data-ttu-id="4b1f6-292">*DfciUpdate dfi*。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-292">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="4b1f6-293">包含 SEMM 指紋的文字檔。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-293">Text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="4b1f6-294"> (在這個範例中，檔案是 *SurfaceUEFI_2020Aug25_1058.txt*。 ) 自動產生的日期時間戳記會對應到您使用 Surface UEFI 設定檔建立檔案的日期。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-294">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="4b1f6-295">Surface Hub 2 上的 Windows 10 專業版與企業作業系統的驅動程式和固件 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-295">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="4b1f6-296">將此檔案複製到 USB 磁片磁碟機的根目錄。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-296">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="4b1f6-297">更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移</span><span class="sxs-lookup"><span data-stu-id="4b1f6-297">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="4b1f6-298">將您的 BOOTME 硬碟插入到 Surface Hub 2 的 USB-A 埠。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-298">Insert your BOOTME drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="4b1f6-299">如需檔案的清單，請參閱上一節。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-299">For a list of required files, see the previous section.</span></span>

2. <span data-ttu-id="4b1f6-300">若要引導至 UEFI：</span><span class="sxs-lookup"><span data-stu-id="4b1f6-300">To boot into UEFI:</span></span>

   1. <span data-ttu-id="4b1f6-301">關閉) Surface Hub 2 的 (關閉。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-301">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="4b1f6-302">按住 [ **音量 +**]，然後按下再放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-302">Press and hold **Volume +**, and then press and release the power button.</span></span>
   1. <span data-ttu-id="4b1f6-303">保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-303">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![按住調高音量按鈕，直到 UEFI 功能表出現為止。](images/shm-fig20.png)
      
3. <span data-ttu-id="4b1f6-305">當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (強烈建議) ）。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-305">When the device restarts, enter the UEFI password that you created earlier, if applicable (strongly recommended).</span></span>

   ![輸入 UEFI 密碼。](images/shm-fig22.png)
   
4. <span data-ttu-id="4b1f6-307">在 UEFI 功能表中，選取**Management**[  >  **從 USB 安裝**管理元件]。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-307">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![選取 [管理] 並從 U S B 安裝。](images/shm-fig21.png)
   
5. <span data-ttu-id="4b1f6-309">選取 [ **立即重新開機**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-309">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="4b1f6-310">裝置會重新開機。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-310">The device reboots.</span></span> <span data-ttu-id="4b1f6-311">它會在視窗中間顯示白色 Microsoft 標誌，然後關閉。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-311">It displays a white Microsoft logo in the middle of the window and then shuts down.</span></span>

   ![選取 [立即重新開機]。](images/shm-fig25.png)
   
6. <span data-ttu-id="4b1f6-313">按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-313">Press and release the power button.</span></span> <span data-ttu-id="4b1f6-314">在出現的紅色視窗中，啟動 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-314">In the red window that appears, activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="4b1f6-315">輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-315">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="4b1f6-316">然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-316">Then select **OK**.</span></span>

   ![輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="4b1f6-318">在裝置上啟用 SEMM 之後，就會套用新的 UEFI 設定 **EnableOSMigration** 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-318">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="4b1f6-319">您將無法再存取 Windows 10 小組。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-319">You'll no longer be able to access Windows 10 Team.</span></span> <span data-ttu-id="4b1f6-320">相反地，您必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-320">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

   <span data-ttu-id="4b1f6-321">裝置會重新開機。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-321">The device reboots.</span></span> <span data-ttu-id="4b1f6-322">它會在畫面中間顯示白色標誌，然後再次關閉。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-322">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="4b1f6-323">安裝 Windows 10 專業版或企業版</span><span class="sxs-lookup"><span data-stu-id="4b1f6-323">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="4b1f6-324">如果您的可引導 Windows 10 專業版或企業版磁碟機尚不在 Surface Hub 2 USB-A 埠中，請立即插入。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-324">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="4b1f6-325">然後按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-325">Then press and release the power button.</span></span> 

    <span data-ttu-id="4b1f6-326">裝置啟動時，您會在畫面中間看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-326">When the device starts, you see the white logo in the middle of the screen.</span></span> <span data-ttu-id="4b1f6-327">接著，您會看到白色標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-327">Then you see a spinning circle below the white logo.</span></span>

3. <span data-ttu-id="4b1f6-328">如果裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置 (拔下電源線，然後再插回) 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-328">If the device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="4b1f6-329">再次插入電源線之後，裝置會在幾秒後啟動。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-329">After you plug the power cord in again, the device should boot after a few seconds.</span></span> <span data-ttu-id="4b1f6-330">然後，您會在畫面中間看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-330">Then you'll see the white logo in the middle of screen.</span></span> 

    <span data-ttu-id="4b1f6-331">如果裝置沒有開啟，請按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-331">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="4b1f6-332">在畫面中間看到標誌之後，按住 [音量] 按鈕，直到您看到白色標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-332">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![從 U S B 磁片磁碟機啟動至 Windows 10。](images/shm-fig26.png)
   
4. <span data-ttu-id="4b1f6-334">當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或 Enterprise (版本1903或) 更新版本。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-334">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="4b1f6-335">安裝 Surface Hub 2 驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="4b1f6-335">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="4b1f6-336">為了確保您的裝置擁有所有最新的更新和驅動程式，請 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 ENTERPRISE OS 的驅動程式和固件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-336">To ensure your device has all the latest updates and drivers, install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
## <span data-ttu-id="4b1f6-337">設定建議的設定</span><span class="sxs-lookup"><span data-stu-id="4b1f6-337">Configure recommended settings</span></span>

<span data-ttu-id="4b1f6-338">若要將 Surface Hub 2 完整設定為個人生產力裝置，請參閱在 <a href="surface-hub-2-post-install.md" target="_blank"> Surface Hub 2 上設定 Windows 10 專業版或企業版 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-338">To fully configure Surface Hub 2S as a personal productivity device, see <a href="surface-hub-2-post-install.md" target="_blank">Configure Windows 10 Pro or Enterprise on Surface Hub 2</a>.</span></span>

> [!NOTE]
><span data-ttu-id="4b1f6-339">如果本文所述的步驟無法成功將您的裝置遷移至 Windows 10 專業版或 Surface Hub 2 的 Enterprise，請接觸 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub 支援 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-339">If the steps outlined in this article don't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2, contact <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub Support</a>.</span></span>

## <span data-ttu-id="4b1f6-340">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="4b1f6-340">Roll back to Windows 10 Team</span></span>

<span data-ttu-id="4b1f6-341">如果您想要將裝置還原至 Windows 10 小組，請參閱 <a href="surface-hub-2s-recover-reset.md" target="_blank"> 重設及恢復 Surface Hub 2 秒 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-341">If you want to restore your device to Windows 10 Team, see <a href="surface-hub-2s-recover-reset.md" target="_blank"> Reset and recovery for Surface Hub 2S</a>.</span></span>

> [!NOTE]
> <span data-ttu-id="4b1f6-342">在回滾至 Windows 10 小組之前，建議您先取消從 SEMM 取消中樞。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-342">Before rolling back to Windows 10 Team, it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="4b1f6-343">若要深入瞭解，請參閱 [從 SEMM 取消註冊 Surface 裝置](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-343">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="4b1f6-344">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="4b1f6-344">Version history</span></span>

<span data-ttu-id="4b1f6-345">下表摘要列出本文所做的變更。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-345">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="4b1f6-346">版本</span><span class="sxs-lookup"><span data-stu-id="4b1f6-346">Version</span></span> | <span data-ttu-id="4b1f6-347">日期</span><span class="sxs-lookup"><span data-stu-id="4b1f6-347">Date</span></span>               | <span data-ttu-id="4b1f6-348">描述</span><span class="sxs-lookup"><span data-stu-id="4b1f6-348">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="4b1f6-349">向量.</span><span class="sxs-lookup"><span data-stu-id="4b1f6-349">v.</span></span> <span data-ttu-id="4b1f6-350">1.3</span><span class="sxs-lookup"><span data-stu-id="4b1f6-350">1.3</span></span>  | <span data-ttu-id="4b1f6-351">2020年12月3日</span><span class="sxs-lookup"><span data-stu-id="4b1f6-351">December 3, 2020</span></span> | <span data-ttu-id="4b1f6-352">已更新有關管理 SEMM 登記的指導方針</span><span class="sxs-lookup"><span data-stu-id="4b1f6-352">Updated with guidance about managing SEMM enrollment</span></span>                                                        |
| <span data-ttu-id="4b1f6-353">向量.</span><span class="sxs-lookup"><span data-stu-id="4b1f6-353">v.</span></span> <span data-ttu-id="4b1f6-354">1.2</span><span class="sxs-lookup"><span data-stu-id="4b1f6-354">1.2</span></span>  | <span data-ttu-id="4b1f6-355">2020年9月29日</span><span class="sxs-lookup"><span data-stu-id="4b1f6-355">September 29, 2020</span></span> | <span data-ttu-id="4b1f6-356">針對可用性意見反應的各種更新。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-356">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="4b1f6-357">向量.</span><span class="sxs-lookup"><span data-stu-id="4b1f6-357">v.</span></span> <span data-ttu-id="4b1f6-358">1.1</span><span class="sxs-lookup"><span data-stu-id="4b1f6-358">1.1</span></span>  | <span data-ttu-id="4b1f6-359">2020年9月15日</span><span class="sxs-lookup"><span data-stu-id="4b1f6-359">September 15, 2020</span></span> | <span data-ttu-id="4b1f6-360">在簡介中放置了說明安裝新作業系統的授權需求。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-360">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="4b1f6-361">向量.</span><span class="sxs-lookup"><span data-stu-id="4b1f6-361">v.</span></span> <span data-ttu-id="4b1f6-362">1.0</span><span class="sxs-lookup"><span data-stu-id="4b1f6-362">1.0</span></span>  | <span data-ttu-id="4b1f6-363">2020年9月1日</span><span class="sxs-lookup"><span data-stu-id="4b1f6-363">September 1, 2020</span></span>  | <span data-ttu-id="4b1f6-364">新文章。</span><span class="sxs-lookup"><span data-stu-id="4b1f6-364">New article.</span></span>                                                                                           |
