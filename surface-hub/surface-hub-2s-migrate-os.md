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
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9878e64e414f4fe9ec3abfbd49adf233edc1da1d
ms.sourcegitcommit: 53d1eac8840fafbcd155798fce0d8c843f48dca3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/09/2021
ms.locfileid: "11255485"
---
# <span data-ttu-id="1af15-104">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="1af15-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

- [<span data-ttu-id="1af15-105">文章版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="1af15-105">Article version history</span></span>](#version-history)

<span data-ttu-id="1af15-106">Surface Hub 秒是預先預先安裝了 Windows 10 團隊。</span><span class="sxs-lookup"><span data-stu-id="1af15-106">Surface Hub 2S comes preinstalled with Windows 10 Team.</span></span> <span data-ttu-id="1af15-107">此自訂版本的 Windows 10 是設計來協助在會議室環境中共同作業。</span><span class="sxs-lookup"><span data-stu-id="1af15-107">This customized edition of Windows 10 is designed to facilitate collaboration in meeting room environments.</span></span> <span data-ttu-id="1af15-108">現在，您可以選擇執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。</span><span class="sxs-lookup"><span data-stu-id="1af15-108">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="1af15-109">與典型的升級或遷移不同，此程式必須遵循說明性程式，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="1af15-109">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described in this article.</span></span> <span data-ttu-id="1af15-110">繼續之前，請先查看 [解決方案元件](#solution-components) 與 [遷移及安裝工作流程](#migration-and-installation-workflow-summary) 。</span><span class="sxs-lookup"><span data-stu-id="1af15-110">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before you continue.</span></span>


> [!NOTE]
> <span data-ttu-id="1af15-111">當您安裝 Windows 10 專業版或企業版時，您需要與現有的 Windows 10 小組授權不同的新授權。</span><span class="sxs-lookup"><span data-stu-id="1af15-111">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="1af15-112">使用個別的電腦和可下載的工具 *SURFACE UEFI 配置*器，從 Windows 10 小組開始遷移。</span><span class="sxs-lookup"><span data-stu-id="1af15-112">Start the migration from Windows 10 Team by using a separate PC and the downloadable tool *Surface UEFI Configurator*.</span></span> <span data-ttu-id="1af15-113">使用此工具來建立包含您套用至 Surface Hub 2 秒的新 UEFI 設定的套件。</span><span class="sxs-lookup"><span data-stu-id="1af15-113">Use the tool  to create a package that contains a new UEFI setting that you apply to Surface Hub 2S.</span></span>  

<span data-ttu-id="1af15-114">Surface UEFI 配置處理常式在 (SEMM) 中，成為 Surface Enterprise 管理模式的介面。</span><span class="sxs-lookup"><span data-stu-id="1af15-114">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="1af15-115">它旨在協助集中管理公司環境中的 Surface 裝置上的固件設定。</span><span class="sxs-lookup"><span data-stu-id="1af15-115">It's designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="1af15-116">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> MICROSOFT SEMM 檔 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-116">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank">Microsoft SEMM documentation</a>.</span></span>
 

## <span data-ttu-id="1af15-117">解決方案元件</span><span class="sxs-lookup"><span data-stu-id="1af15-117">Solution components</span></span>

- <span data-ttu-id="1af15-118">執行 Windows 10 小組作業系統的 Surface Hub 2 秒裝置</span><span class="sxs-lookup"><span data-stu-id="1af15-118">Surface Hub 2S device running the Windows 10 Team operating system</span></span>
- <span data-ttu-id="1af15-119">運行 Windows 10 的個別裝置</span><span class="sxs-lookup"><span data-stu-id="1af15-119">Separate device running Windows 10</span></span>
- <span data-ttu-id="1af15-120">用於建立 SEMM 套件的 Surface UEFI 設定檔工具</span><span class="sxs-lookup"><span data-stu-id="1af15-120">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="1af15-121">Windows 10 專業版或企業版作業系統影像、版本1903或更新版本</span><span class="sxs-lookup"><span data-stu-id="1af15-121">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="1af15-122">兩個有 16 GB 儲存空間的 USB 磁片磁碟機，FAT32 格式</span><span class="sxs-lookup"><span data-stu-id="1af15-122">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="1af15-123">Windows 10 專業版和企業作業系統在 Surface Hub 2 上的驅動程式與固件，Microsoft Windows Installer (的 MSI) 檔案</span><span class="sxs-lookup"><span data-stu-id="1af15-123">The Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="1af15-124">網際網路連線</span><span class="sxs-lookup"><span data-stu-id="1af15-124">Internet connection</span></span>
- <span data-ttu-id="1af15-125">影像處理方案 (選用) </span><span class="sxs-lookup"><span data-stu-id="1af15-125">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="1af15-126">遷移和安裝工作流程摘要</span><span class="sxs-lookup"><span data-stu-id="1af15-126">Migration and installation workflow summary</span></span>

| <span data-ttu-id="1af15-127">步驟</span><span class="sxs-lookup"><span data-stu-id="1af15-127">Step</span></span>  | <span data-ttu-id="1af15-128">動作</span><span class="sxs-lookup"><span data-stu-id="1af15-128">Action</span></span>                                                                                                 | <span data-ttu-id="1af15-129">摘要</span><span class="sxs-lookup"><span data-stu-id="1af15-129">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1af15-130">sr-1</span><span class="sxs-lookup"><span data-stu-id="1af15-130">1</span></span> | [<span data-ttu-id="1af15-131">確認 Surface Hub 2 上的 UEFI 版本符合最低需求。</span><span class="sxs-lookup"><span data-stu-id="1af15-131">Verify that the UEFI version on Surface Hub 2S meets minimum requirements.</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="1af15-132">確定 UEFI 版本為694.2938.768.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-132">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="1af15-133">pplx-2</span><span class="sxs-lookup"><span data-stu-id="1af15-133">2</span></span> | [<span data-ttu-id="1af15-134">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件。</span><span class="sxs-lookup"><span data-stu-id="1af15-134">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="1af15-135">在 [ <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> **表面工具**] 頁面上 </a> ，選取 [**下載**]。</span><span class="sxs-lookup"><span data-stu-id="1af15-135">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank">**Surface Tools for IT** page</a>, select **Download**.</span></span> <span data-ttu-id="1af15-136">然後選取並下載 **SURFACE UEFI 配置器。MSI** 檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="1af15-136">Then select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="1af15-137">下載 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 適用于 Surface Hub 2 MSI 檔案的 Windows 10 專業版和企業版 OS 的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="1af15-137">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a> <span data-ttu-id="1af15-138">將它儲存在步驟5中以供使用。</span><span class="sxs-lookup"><span data-stu-id="1af15-138">Save it for use in step 5.</span></span> |
| <span data-ttu-id="1af15-139">3</span><span class="sxs-lookup"><span data-stu-id="1af15-139">3</span></span> | [<span data-ttu-id="1af15-140">準備 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="1af15-140">Prepare SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="1af15-141">準備運行 Surface UEFI 配置器所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="1af15-141">Prepare the certificate that's required to run Surface UEFI Configurator.</span></span> <span data-ttu-id="1af15-142">或使用您目前的憑證。</span><span class="sxs-lookup"><span data-stu-id="1af15-142">Or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="1af15-143">4</span><span class="sxs-lookup"><span data-stu-id="1af15-143">4</span></span> | [<span data-ttu-id="1af15-144">建立 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="1af15-144">Create SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="1af15-145">啟動 Surface UEFI 設定檔以在 USB 磁片磁碟機上建立 SEMM 套件，這將包含您需要在 Surface Hub 2 上套用的配置檔案。</span><span class="sxs-lookup"><span data-stu-id="1af15-145">Start Surface UEFI Configurator to create a SEMM package on a USB drive, which will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="1af15-146">將這些 SEMM 套件檔案複製到您電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="1af15-146">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="1af15-147">500</span><span class="sxs-lookup"><span data-stu-id="1af15-147">5</span></span> | [<span data-ttu-id="1af15-148">準備 USB 快閃記憶體磁片磁碟機，其中包含適用于 Surface Hub 2 的 windows 10 專業版與企業作業系統的 SEMM 套件、驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="1af15-148">Prepare USB flash drive that contains Windows 10 image, SEMM package, and drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="1af15-149">建立包含 Windows 10 影像的單一 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1af15-149">Create a single USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="1af15-150">在這個範例中，磁片磁碟機名為 *BOOTME*。</span><span class="sxs-lookup"><span data-stu-id="1af15-150">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="1af15-151">在 Surface Hub 2 (的 Windows 10 專業版與企業作業系統的驅動程式和固件，請 (步驟 2) 並 SEMM 套件檔案步驟 4) 移至 *BOOTME* 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1af15-151">Add your drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (step 2) and SEMM package files (step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="1af15-152">6</span><span class="sxs-lookup"><span data-stu-id="1af15-152">6</span></span> | [<span data-ttu-id="1af15-153">更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="1af15-153">Update UEFI on Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="1af15-154">使用 *BOOTME* 磁片磁碟機來啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="1af15-154">Use the *BOOTME* drive to boot Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="1af15-155">utf-7</span><span class="sxs-lookup"><span data-stu-id="1af15-155">7</span></span> | [<span data-ttu-id="1af15-156">安裝 Windows 10 專業版或企業版1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-156">Install Windows 10 Pro or Enterprise version 1903 or later.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="1af15-157">使用 *BOOTME* 磁片磁碟機來安裝 Windows 10 專業版或企業版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-157">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="1af15-158">型</span><span class="sxs-lookup"><span data-stu-id="1af15-158">8</span></span> | [<span data-ttu-id="1af15-159">安裝適用于 Surface Hub 2 的 Windows 10 專業版和企業版作業系統的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="1af15-159">Install drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="1af15-160">為了確保您的裝置擁有所有最新的更新和驅動程式，請 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 的 MSI 檔案上安裝 Windows 10 專業版和企業版 OS 的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="1af15-160">To ensure your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="1af15-161">9</span><span class="sxs-lookup"><span data-stu-id="1af15-161">9</span></span> | [<span data-ttu-id="1af15-162">將 Surface Hub 2 完整設定為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="1af15-162">Fully configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="1af15-163">啟用建議的設定和應用程式，以將 Surface Hub 秒優化為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="1af15-163">Enable recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="1af15-164">驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求</span><span class="sxs-lookup"><span data-stu-id="1af15-164">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="1af15-165">在您將 Surface Hub 從 Windows 10 小組遷移至 Windows 10 桌上出版前，您需要至少 *694.2938.768.0*的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-165">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need a UEFI version that's at least *694.2938.768.0*.</span></span>
 
**<span data-ttu-id="1af15-166">若要在您的系統上驗證 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="1af15-166">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="1af15-167">在 Surface Hub 2 的 [首頁] 頁面上，選取 [**開始**]，然後在 [**所有應用程式**]  >  **表面**) 開啟 [Surface app] (。</span><span class="sxs-lookup"><span data-stu-id="1af15-167">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="1af15-168">選取 **您的 surface** 以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-168">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="1af15-169">如果 UEFI 版本是 *694.2938.768.0* 或更新版本，如下列影像所示，您可以建立 SEMM 套件來啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="1af15-169">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![在 Surface app 中顯示您的 Surface 頁面的螢幕擷取畫面。](images/shm-fig1.png)
 
   - <span data-ttu-id="1af15-171">如果 UEFI 版本早于版本694.2938.768.0，您將需要安裝 Windows 10 Team 2020 更新裸機復原 (BMR) 影像或使用 Windows Update 來取得目前版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-171">If the UEFI version is earlier than version 694.2938.768.0, you will need to obtain a current version by either installing the Window 10 Team 2020 Update Bare Metal Recovery (BMR) image, or by using Windows Update.</span></span>
   
**<span data-ttu-id="1af15-172">若要透過 Windows Update 更新 UEFI：</span><span class="sxs-lookup"><span data-stu-id="1af15-172">To update UEFI via Windows Update:</span></span>**

1. <span data-ttu-id="1af15-173">在 Surface Hub 2 秒，請以系統 **管理員**身分登入。</span><span class="sxs-lookup"><span data-stu-id="1af15-173">On your Surface Hub 2S, sign in as **Admin**.</span></span> 

    >[!Note]
    > <span data-ttu-id="1af15-174">如果您不知道您的使用者名稱或系統管理員密碼，您必須重設裝置。</span><span class="sxs-lookup"><span data-stu-id="1af15-174">If you don't know your username or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="1af15-175">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank"> 重設及恢復 Surface Hub 2 秒。</span><span class="sxs-lookup"><span data-stu-id="1af15-175">For more information, see <a href="https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset" target="_blank">Reset and recovery for Surface Hub 2S.</span></span></a>

1. <span data-ttu-id="1af15-176">移至 [**所有應用程式**設定] 的 [  >  \*\*\*\*  >  **更新與安全性**]  >  **Windows update**，然後安裝所有更新。</span><span class="sxs-lookup"><span data-stu-id="1af15-176">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and then install all updates.</span></span> 

1. <span data-ttu-id="1af15-177">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="1af15-177">Restart the device.</span></span> 

1. <span data-ttu-id="1af15-178">使用 Surface app 驗證 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-178">Verify the UEFI version by using the Surface app.</span></span>

1. <span data-ttu-id="1af15-179">在此情況下，如果 UEFI 版本尚不是版本694.2938.768.0 或更新版本，您可以重複上述步驟，或安裝 Windows 10 Team 2020 更新裸機復原 (BMR) 影像，即可取得最新的 UEFI。</span><span class="sxs-lookup"><span data-stu-id="1af15-179">At this point, if the UEFI version is not yet version  694.2938.768.0 or later, you can either repeat the above steps, or you can get the latest UEFI by installing the Windows 10 Team 2020 Update Bare Metal Recovery (BMR) image.</span></span>

**<span data-ttu-id="1af15-180">若要透過裸機復原來更新 UEFI (BMR) 影像：</span><span class="sxs-lookup"><span data-stu-id="1af15-180">To update UEFI via Bare Metal Recovery (BMR) image:</span></span>**

1.  <span data-ttu-id="1af15-181">移至 [ [surface](https://support.microsoft.com/surfacerecoveryimage) 復原] 網站，然後選取 [ **Surface Hub 2 秒**]。</span><span class="sxs-lookup"><span data-stu-id="1af15-181">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**.</span></span>

3.  <span data-ttu-id="1af15-182">輸入您的中樞序列值， (位於中樞背面，位於 [電源連接]) 旁邊。</span><span class="sxs-lookup"><span data-stu-id="1af15-182">Enter your Hub Serial Number (located on the rear side of the Hub next to the power connection).</span></span>

4.  <span data-ttu-id="1af15-183">按照指示，透過安裝 Windows 10 Team 2020 更新，將影像下載到格式化的 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1af15-183">Follow the directions to download the image onto a formatted USB drive through installing the Windows 10 Team 2020 Update.</span></span>

5.  <span data-ttu-id="1af15-184">更新完成之後，裝置第一次進入 OOBE 時，您不需要完成 OOBE，就會更新 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-184">After the update has completed and the device enters the OOBE first time setup, you do not need to complete OOBE, the UEFI version will be updated.</span></span> <span data-ttu-id="1af15-185">請改為按住電源按鈕，直到螢幕關閉為止，再關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="1af15-185">Instead power down the device by holding the power button until the screen turns off.</span></span> 

### <span data-ttu-id="1af15-186">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="1af15-186">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="1af15-187">在不同的電腦上：</span><span class="sxs-lookup"><span data-stu-id="1af15-187">On a separate PC:</span></span>

1. <span data-ttu-id="1af15-188">在 [ <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> 表面工具] 頁面上 </a> ，選取 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="1af15-188">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>

1. <span data-ttu-id="1af15-189">選取並下載 Surface UEFI 設定檔 MSI 檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="1af15-189">Select and download the Surface UEFI Configurator MSI file and install it on a separate PC.</span></span> <span data-ttu-id="1af15-190">安裝 Windows 10 小組版時，Surface UEFI 組態工具無法在 Surface Hub 2 上執行。</span><span class="sxs-lookup"><span data-stu-id="1af15-190">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while the Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="1af15-191">下載 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Surface Hub 2 驅動程式和固件 Windows 安裝程式 MSI 檔案 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-191">Download the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Surface Hub 2 Drivers and Firmware Windows Installer MSI file</a>.</span></span> <span data-ttu-id="1af15-192">當您安裝新的作業系統時，您將會用到這個檔案。</span><span class="sxs-lookup"><span data-stu-id="1af15-192">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="1af15-193">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="1af15-193">Prepare the SEMM certificate</span></span>

<span data-ttu-id="1af15-194">如果您尚未使用 Surface UEFI 配置器，您必須準備證書。</span><span class="sxs-lookup"><span data-stu-id="1af15-194">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="1af15-195">這個憑證可確保在裝置註冊 SEMM 之後，您只能使用以核准憑證建立的套件來修改 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="1af15-195">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span> 

<span data-ttu-id="1af15-196">您取得憑證的方式取決於貴組織的規模或複雜度。</span><span class="sxs-lookup"><span data-stu-id="1af15-196">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="1af15-197">企業組織通常會維持自己的基礎結構，以根據標準安全慣例產生證書。</span><span class="sxs-lookup"><span data-stu-id="1af15-197">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="1af15-198">中型企業及其他人可能選擇從合作夥伴提供者取得憑證。</span><span class="sxs-lookup"><span data-stu-id="1af15-198">Medium-sized businesses and others might choose to get certificates from partner providers.</span></span> <span data-ttu-id="1af15-199">對於沒有足夠 IT 專業知識或專門 IT 安全小組的組織，建議使用此選項。</span><span class="sxs-lookup"><span data-stu-id="1af15-199">This option is recommended for organizations that don't have sufficient IT expertise or a dedicated IT security team.</span></span>

- <span data-ttu-id="1af15-200">或者，您也可以使用 PowerShell 腳本來產生自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="1af15-200">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="1af15-201">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank"> 企業管理模式證書需求 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-201">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements" target="_blank">Surface Enterprise Management Mode certificate requirements </a>.</span></span> <span data-ttu-id="1af15-202">或者，您可以使用 PowerShell 建立您自己的憑證。</span><span class="sxs-lookup"><span data-stu-id="1af15-202">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="1af15-203">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> 新的 SelfSignedCertificate </a> 檔。</span><span class="sxs-lookup"><span data-stu-id="1af15-203">For more information, see the <a href="https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate" target="_blank"> New-SelfSignedCertificate</a> documentation.</span></span>

<span data-ttu-id="1af15-204">Surface UEFI 設定檔建立的 SEMM 套件必須以憑證加以保護。</span><span class="sxs-lookup"><span data-stu-id="1af15-204">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="1af15-205">憑證會驗證設定檔的簽名，然後才能套用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="1af15-205">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="1af15-206">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM 檔 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-206">For more information, see the <a href="https://docs.microsoft.com/surface/surface-enterprise-management-mode" target="_blank"> SEMM documentation</a>.</span></span>
 
 
### <span data-ttu-id="1af15-207">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="1af15-207">Create a SEMM package</span></span>

1. <span data-ttu-id="1af15-208">在另一部電腦上，安裝您先前下載的 Surface UEFI 組態工具。</span><span class="sxs-lookup"><span data-stu-id="1af15-208">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span> 

2. <span data-ttu-id="1af15-209">開啟 Surface UEFI 配置器，然後選取 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="1af15-209">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![開啟 Surface UEFI 配置器。](images/shm-fig2.png)
   
3. <span data-ttu-id="1af15-211">選取 [ **Surface 裝置**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-211">Select **Surface Devices**, and then select **Next**.</span></span>

   ![選取 [Surface 裝置]。](images/shm-fig3.png)
  
4. <span data-ttu-id="1af15-213">選取 [設定 **套件**]。</span><span class="sxs-lookup"><span data-stu-id="1af15-213">Select **Configuration Package**.</span></span>

   ![選取 [設定套件]。](images/shm-fig4.png)
  
5. <span data-ttu-id="1af15-215">選取 [ **憑證保護**]。</span><span class="sxs-lookup"><span data-stu-id="1af15-215">Select **Certificate Protection**.</span></span>

   ![選取 [憑證保護]。](images/shm-fig5.png)

   <span data-ttu-id="1af15-217">系統會提示您新增憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="1af15-217">You're prompted to add your certificate .pfx file.</span></span>

   ![新增您的憑證。](images/shm-fig6.png)
   
7. <span data-ttu-id="1af15-219">輸入您的憑證密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-219">Enter your certificate password, and then select **OK**.</span></span>

   ![輸入您的憑證密碼，然後選取 [確定]。](images/shm-fig7.png)

8. <span data-ttu-id="1af15-221">選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="1af15-221">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="1af15-222">每當您引導至 UEFI 時，就會需要此密碼。</span><span class="sxs-lookup"><span data-stu-id="1af15-222">You'll need this password whenever you boot to UEFI.</span></span> <span data-ttu-id="1af15-223">我們 *強烈建議* 您設定要在 Surface Hub 的2秒使用的 UEFI 密碼。</span><span class="sxs-lookup"><span data-stu-id="1af15-223">We *strongly recommend* that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>

   ![選取 [密碼保護]。](images/shm-fig8.png)
   
9. <span data-ttu-id="1af15-225">設定 UEFI 密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-225">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="1af15-226">將密碼儲存在可供管理 Surface Hub 之 IT 系統管理員存取的安全位置。</span><span class="sxs-lookup"><span data-stu-id="1af15-226">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> <span data-ttu-id="1af15-227">如果密碼遺失，就無法復原。</span><span class="sxs-lookup"><span data-stu-id="1af15-227">If the password is lost, it can't be recovered.</span></span> 

   ![輸入您的 UEFI 密碼。](images/shm-fig9.png)

10. <span data-ttu-id="1af15-229">選取 [ **Surface Hub 2 秒**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-229">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![選取 [Surface Hub 2 秒]。](images/shm-fig10.png)
   
11. <span data-ttu-id="1af15-231">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-231">Select **Next**.</span></span>

    ![選取 \[下一步\]。](images/shm-fig10a.png)

12. <span data-ttu-id="1af15-233">若要允許安裝 Windows 10 專業版或企業版，請開啟 **EnableOsMigration**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-233">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![選取 [啟用 O S 遷移]。](images/shm-fig11.png)
    
    ![將 [啟用作業系統遷移] 設定為 [開啟]。](images/shm-fig12.png)

### <span data-ttu-id="1af15-236">管理 SEMM 登記</span><span class="sxs-lookup"><span data-stu-id="1af15-236">Managing SEMM enrollment</span></span>

<span data-ttu-id="1af15-237">將裝置註冊至 SEMM 會影響您管理裝置的後續方式。</span><span class="sxs-lookup"><span data-stu-id="1af15-237">Enrolling devices into SEMM affects how you can manage the device going forward.</span></span> <span data-ttu-id="1af15-238">例如，在您套用 SEMM 套件之後，在裝置的 UEFI 功能表中，所有 UEFI 設定都無法使用 (鎖定) 。</span><span class="sxs-lookup"><span data-stu-id="1af15-238">For example, after you apply a SEMM package, in the device's UEFI menu, all UEFI settings are unavailable (locked).</span></span> <span data-ttu-id="1af15-239">其他設定（例如 **IPv6 FOR PXE 啟動** ）的預設值也無法使用。</span><span class="sxs-lookup"><span data-stu-id="1af15-239">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span> 

<span data-ttu-id="1af15-240">若要在完成遷移後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="1af15-240">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="1af15-241">如果您套用另一個 SEMM 套件來變更 UEFI 設定，則在建立新的 SEMM 套件時，您必須使用原始證書。</span><span class="sxs-lookup"><span data-stu-id="1af15-241">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="1af15-242">使用 UEFI 組態工具工具，並將 **EnableOSMigration** 關閉 (不在開啟，如原始的遷移步驟) 所示。</span><span class="sxs-lookup"><span data-stu-id="1af15-242">Use the UEFI Configurator tool and leave **EnableOSMigration** off (not on, as shown in the original migration steps).</span></span>

#### <span data-ttu-id="1af15-243">與合作夥伴合作</span><span class="sxs-lookup"><span data-stu-id="1af15-243">Working with partners</span></span>

<span data-ttu-id="1af15-244">如果您的公司已將遷移移至 Windows 10 專業版或 Surface Hub 2 上的企業，您可能會想要讓合作夥伴將 SEMM 憑證、SEMM 套件和 UEFI 密碼轉讓給您。</span><span class="sxs-lookup"><span data-stu-id="1af15-244">If your company is outsourcing the migration to Windows 10 Pro or Enterprise on Surface Hub 2, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span>  <span data-ttu-id="1af15-245">或者，在您遷移中心之後，您可以立即取消從 SEMM 進行註冊，這將允許對 UEFI 進行本機管理，並將裝置傳輸至另一方。</span><span class="sxs-lookup"><span data-stu-id="1af15-245">Alternatively, after migrating the Hub, you can immediately un-enroll it from SEMM, which will allow local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="1af15-246">不過，仍強烈建議使用 UEFI 密碼（可在遷移之後進行設定）。</span><span class="sxs-lookup"><span data-stu-id="1af15-246">Nevertheless, it's still strongly recommended to use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="1af15-247">若要深入瞭解，請參閱 [管理 SURFACE UEFI 設定](https://docs.microsoft.com/surface/manage-surface-uefi-settings)。</span><span class="sxs-lookup"><span data-stu-id="1af15-247">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <span data-ttu-id="1af15-248">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="1af15-248">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="1af15-249">如果您在遷移之後選擇將裝置還原至 Windows 10 小組（ [如下所述](#roll-back-to-windows-10-team)），建議您首先取消從 SEMM 取消中樞。</span><span class="sxs-lookup"><span data-stu-id="1af15-249">If after migrating you choose to restore your device to Windows 10 Team, [as described below](#roll-back-to-windows-10-team), it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="1af15-250">若要深入瞭解，請參閱 [從 SEMM 取消註冊 Surface 裝置](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="1af15-250">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>


#### <span data-ttu-id="1af15-251">將 SEMM 套件儲存至 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="1af15-251">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="1af15-252">將 USB 磁片磁碟機連線至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="1af15-252">Connect a USB drive to your PC.</span></span> 

1. <span data-ttu-id="1af15-253">選擇 [ **中心2秒**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-253">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![選取 [USB]](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="1af15-255">在建立 SEMM 套件時，會清除 USB 磁片磁碟機上的所有現有資料。</span><span class="sxs-lookup"><span data-stu-id="1af15-255">All existing data on the USB drive is erased when the SEMM package is built.</span></span> <span data-ttu-id="1af15-256">在建立 SEMM 套件之前，請先從您要儲存的 USB 磁片磁碟機中移除任何檔案。</span><span class="sxs-lookup"><span data-stu-id="1af15-256">Before building the SEMM package, remove any files from the USB drive that you want to save.</span></span>
   
2. <span data-ttu-id="1af15-257">選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="1af15-257">Select **Build**.</span></span>

   ![選取 [建立]。](images/shm-fig14.png)

3. <span data-ttu-id="1af15-259">捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。</span><span class="sxs-lookup"><span data-stu-id="1af15-259">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="1af15-260">您的 SEMM 套件現已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="1af15-260">Your SEMM package is now ready.</span></span> <span data-ttu-id="1af15-261">它包含 SEMM 套件 *DfciUpdate dfi* 和文字檔，其中包含 SEMM 指紋 (憑證的指紋) 中的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="1af15-261">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM thumbprint (the last two characters of the certificate's thumbprint).</span></span>

   ![選取 [結束]。](images/shm-fig15.png)
   
4. <span data-ttu-id="1af15-263">儲存憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="1af15-263">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="1af15-264">當您在 Surface Hub 2 上套用套件時，您必須使用這些字元來啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="1af15-264">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="1af15-265">準備包含 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式與固件的 USB 快閃記憶體磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="1af15-265">Prepare a USB flash drive that contains a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="1af15-266">您可以使用下列其中一個選項，在版本1903或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：</span><span class="sxs-lookup"><span data-stu-id="1af15-266">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) by using one of the following options:</span></span>

- <span data-ttu-id="1af15-267">您目前的影像解決方案。</span><span class="sxs-lookup"><span data-stu-id="1af15-267">Your current imaging solution.</span></span>

- <a href="https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator" target="_blank"> <span data-ttu-id="1af15-268">Surface 部署加速器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-268">Surface Deployment Accelerator</a>.</span></span> <span data-ttu-id="1af15-269">使用這個工具來建立可引導的 Windows 10 影像。</span><span class="sxs-lookup"><span data-stu-id="1af15-269">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="1af15-270">影像可以包含所有目前的 Windows 10 更新、Office、您選擇的其他應用程式，以及所需的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="1af15-270">The image can include all current Windows 10 updates, Office, other apps that you choose, and the required drivers and firmware.</span></span> 

- <span data-ttu-id="1af15-271">包含 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1af15-271">USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="1af15-272">然後 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 上安裝 Windows 10 專業版和企業版作業系統的驅動程式和固件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-272">Then install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span>
 
<span data-ttu-id="1af15-273">下列程式說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後新增 SEMM 套件檔案，以及 Windows 10 專業版的驅動程式和固件（Surface Hub 2 MSI 檔案）。</span><span class="sxs-lookup"><span data-stu-id="1af15-273">The following procedure describes how to create a USB flash drive from installation media, and then add the SEMM package files and the Drivers and Firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="1af15-274">如果您使用的是其他部署方法，請前往 [Surface Hub 2 上的更新 UEFI，以啟用](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 本文中的 [作業系統遷移] 區段。</span><span class="sxs-lookup"><span data-stu-id="1af15-274">If you're using other deployment methods, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="1af15-275">完成安裝之後，您需要適用于 Windows 10 專業版或 Windows 10 Enterprise 的有效授權，與現有的 Windows 10 小組授權不同。</span><span class="sxs-lookup"><span data-stu-id="1af15-275">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="1af15-276">若要建立 Windows 10 專業版安裝，請在 [ <a href="https://www.microsoft.com/software-download/windows10" target="_blank"> 下載 windows 10] </a> 頁面上，依照指示下載媒體建立工具。</span><span class="sxs-lookup"><span data-stu-id="1af15-276">To create a Windows 10 Pro installation, on the<a href="https://www.microsoft.com/software-download/windows10" target="_blank"> Download Windows 10</a> page, follow the instructions to download the media creation tool.</span></span> <span data-ttu-id="1af15-277">若要下載 Windows 10 企業版，請移至 <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft 大量授權服務中心 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-277">To download Windows 10 Enterprise, go to the <a href="https://www.microsoft.com/licensing/servicecenter/default.aspx" target="_blank"> Microsoft Volume Licensing Service Center</a>.</span></span>

1. <span data-ttu-id="1af15-278">插入新的 USB 儲存空間磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1af15-278">Insert a new USB storage drive.</span></span> 

1. <span data-ttu-id="1af15-279">開啟 [媒體建立工具]，選取 [ **建立安裝媒體**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-279">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![建立安裝媒體。](images/shm-fig16.png)
   
1. <span data-ttu-id="1af15-281">選取 [語言]，然後選擇 [ **Windows 10** ] 和 [ \*\*64 位 (x64) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="1af15-281">Select a language, and then choose **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="1af15-282">然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-282">Then select **Next**.</span></span>

   ![選取 [語言]，然後選擇 [Windows 10] 和 [64 位]。](images/shm-fig17.png)
   
1. <span data-ttu-id="1af15-285">選取 [ **USB 快閃記憶體磁片磁碟機**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-285">Select **USB flash drive**, and then select **Next**.</span></span>

   ![選取 [U S B 快閃記憶體磁碟機]，然後選取 [下一步]。](images/shm-fig18.png)
   
1. <span data-ttu-id="1af15-287">下載完成後，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-287">When the download finishes, select **Finish**.</span></span>

   ![選取 [完成]。](images/shm-fig19.png)
   
1. <span data-ttu-id="1af15-289">在 Surface Hub 2 上複製 SEMM 套件檔案和 Windows 10 專業版作業系統的驅動程式及固件， (MSI 檔案) 到包含您 Windows 10 影像 (*BOOTME*) 的 USB 快閃記憶體磁片磁碟機根目錄。</span><span class="sxs-lookup"><span data-stu-id="1af15-289">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="1af15-290">BOOTME USB 磁片磁碟機包含：</span><span class="sxs-lookup"><span data-stu-id="1af15-290">The BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="1af15-291">您的 Windows 10 可引導影像。</span><span class="sxs-lookup"><span data-stu-id="1af15-291">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="1af15-292">SEMM 套件檔案 (複製到 USB 磁片磁碟機的根目錄) 。</span><span class="sxs-lookup"><span data-stu-id="1af15-292">SEMM package files (copied to the root of the USB drive).</span></span>
    
      - <span data-ttu-id="1af15-293">*DfciUpdate dfi*。</span><span class="sxs-lookup"><span data-stu-id="1af15-293">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="1af15-294">包含 SEMM 指紋的文字檔。</span><span class="sxs-lookup"><span data-stu-id="1af15-294">Text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="1af15-295"> (在這個範例中，檔案是 *SurfaceUEFI_2020Aug25_1058.txt*。 ) 自動產生的日期時間戳記會對應到您使用 Surface UEFI 設定檔建立檔案的日期。</span><span class="sxs-lookup"><span data-stu-id="1af15-295">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="1af15-296">Surface Hub 2 上的 Windows 10 專業版與企業作業系統的驅動程式和固件 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="1af15-296">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="1af15-297">將此檔案複製到 USB 磁片磁碟機的根目錄。</span><span class="sxs-lookup"><span data-stu-id="1af15-297">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="1af15-298">更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移</span><span class="sxs-lookup"><span data-stu-id="1af15-298">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="1af15-299">將您的 BOOTME 硬碟插入到 Surface Hub 2 的 USB-A 埠。</span><span class="sxs-lookup"><span data-stu-id="1af15-299">Insert your BOOTME drive into the USB-A port on Surface Hub 2S.</span></span> <span data-ttu-id="1af15-300">如需檔案的清單，請參閱上一節。</span><span class="sxs-lookup"><span data-stu-id="1af15-300">For a list of required files, see the previous section.</span></span>

2. <span data-ttu-id="1af15-301">若要引導至 UEFI：</span><span class="sxs-lookup"><span data-stu-id="1af15-301">To boot into UEFI:</span></span>

   1. <span data-ttu-id="1af15-302">關閉) Surface Hub 2 的 (關閉。</span><span class="sxs-lookup"><span data-stu-id="1af15-302">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="1af15-303">按住 [ **音量 +**]，然後按下再放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1af15-303">Press and hold **Volume +**, and then press and release the power button.</span></span>
   1. <span data-ttu-id="1af15-304">保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。</span><span class="sxs-lookup"><span data-stu-id="1af15-304">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![按住調高音量按鈕，直到 UEFI 功能表出現為止。](images/shm-fig20.png)
      
3. <span data-ttu-id="1af15-306">當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (強烈建議) ）。</span><span class="sxs-lookup"><span data-stu-id="1af15-306">When the device restarts, enter the UEFI password that you created earlier, if applicable (strongly recommended).</span></span>

   ![輸入 UEFI 密碼。](images/shm-fig22.png)
   
4. <span data-ttu-id="1af15-308">在 UEFI 功能表中，選取\*\*\*\*[  >  **從 USB 安裝**管理元件]。</span><span class="sxs-lookup"><span data-stu-id="1af15-308">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![選取 [管理] 並從 U S B 安裝。](images/shm-fig21.png)
   
5. <span data-ttu-id="1af15-310">選取 [ **立即重新開機**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="1af15-310">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="1af15-311">裝置會重新開機。</span><span class="sxs-lookup"><span data-stu-id="1af15-311">The device reboots.</span></span> <span data-ttu-id="1af15-312">它會在視窗中間顯示白色 Microsoft 標誌，然後關閉。</span><span class="sxs-lookup"><span data-stu-id="1af15-312">It displays a white Microsoft logo in the middle of the window and then shuts down.</span></span>

   ![選取 [立即重新開機]。](images/shm-fig25.png)
   
6. <span data-ttu-id="1af15-314">按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1af15-314">Press and release the power button.</span></span> <span data-ttu-id="1af15-315">在出現的紅色視窗中，啟動 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="1af15-315">In the red window that appears, activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="1af15-316">輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。</span><span class="sxs-lookup"><span data-stu-id="1af15-316">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="1af15-317">然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1af15-317">Then select **OK**.</span></span>

   ![輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="1af15-319">在裝置上啟用 SEMM 之後，就會套用新的 UEFI 設定 **EnableOSMigration** 。</span><span class="sxs-lookup"><span data-stu-id="1af15-319">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="1af15-320">您將無法再存取 Windows 10 小組。</span><span class="sxs-lookup"><span data-stu-id="1af15-320">You'll no longer be able to access Windows 10 Team.</span></span> <span data-ttu-id="1af15-321">相反地，您必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="1af15-321">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

   <span data-ttu-id="1af15-322">裝置會重新開機。</span><span class="sxs-lookup"><span data-stu-id="1af15-322">The device reboots.</span></span> <span data-ttu-id="1af15-323">它會在畫面中間顯示白色標誌，然後再次關閉。</span><span class="sxs-lookup"><span data-stu-id="1af15-323">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="1af15-324">安裝 Windows 10 專業版或企業版</span><span class="sxs-lookup"><span data-stu-id="1af15-324">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="1af15-325">如果您的可引導 Windows 10 專業版或企業版磁碟機尚不在 Surface Hub 2 USB-A 埠中，請立即插入。</span><span class="sxs-lookup"><span data-stu-id="1af15-325">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="1af15-326">然後按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1af15-326">Then press and release the power button.</span></span> 

    <span data-ttu-id="1af15-327">裝置啟動時，您會在畫面中間看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="1af15-327">When the device starts, you see the white logo in the middle of the screen.</span></span> <span data-ttu-id="1af15-328">接著，您會看到白色標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="1af15-328">Then you see a spinning circle below the white logo.</span></span>

3. <span data-ttu-id="1af15-329">如果裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置 (拔下電源線，然後再插回) 。</span><span class="sxs-lookup"><span data-stu-id="1af15-329">If the device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="1af15-330">再次插入電源線之後，裝置會在幾秒後啟動。</span><span class="sxs-lookup"><span data-stu-id="1af15-330">After you plug the power cord in again, the device should boot after a few seconds.</span></span> <span data-ttu-id="1af15-331">然後，您會在畫面中間看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="1af15-331">Then you'll see the white logo in the middle of screen.</span></span> 

    <span data-ttu-id="1af15-332">如果裝置沒有開啟，請按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="1af15-332">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="1af15-333">在畫面中間看到標誌之後，按住 **音量** 按鈕，直到您看到白色標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="1af15-333">Immediately after you see the logo in the middle of the screen, press and hold the **Volume -** button until you see the spinning circle below the white logo.</span></span>
 
   ![從 U S B 磁片磁碟機啟動至 Windows 10。](images/shm-fig26.png)
   
4. <span data-ttu-id="1af15-335">當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或 Enterprise (版本1903或) 更新版本。</span><span class="sxs-lookup"><span data-stu-id="1af15-335">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="1af15-336">安裝 Surface Hub 2 驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="1af15-336">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="1af15-337">為了確保您的裝置擁有所有最新的更新和驅動程式，請 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 ENTERPRISE OS 的驅動程式和固件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-337">To ensure your device has all the latest updates and drivers, install <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2</a>.</span></span> <span data-ttu-id="1af15-338">安裝驅動程式和固件 MSI 之後，請重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="1af15-338">After installation of the drivers and firmware MSI, reboot the device.</span></span> <span data-ttu-id="1af15-339">然後，在再次開啟 Hub 之後，請將電腦的電源持續一小時，然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="1af15-339">Then, after powering the Hub back on, keep the PC power on for an hour and reboot the device again.</span></span> <span data-ttu-id="1af15-340">第二次重新開機時，系統不會提示您。</span><span class="sxs-lookup"><span data-stu-id="1af15-340">You will not be prompted for the second reboot.</span></span> <span data-ttu-id="1af15-341">視電腦的狀態在遷移至 Windows 10 專業版或企業版前，您可能需要執行第二個步驟，以確保所有的固件都已更新。</span><span class="sxs-lookup"><span data-stu-id="1af15-341">Depending on the state of your machine prior to migrating to Windows 10 Pro or Enterprise, this second step may be needed to ensure all of the firmware has been updated.</span></span>
 
## <span data-ttu-id="1af15-342">設定建議的設定</span><span class="sxs-lookup"><span data-stu-id="1af15-342">Configure recommended settings</span></span>

<span data-ttu-id="1af15-343">若要將 Surface Hub 2 完整設定為個人生產力裝置，請參閱在 <a href="surface-hub-2-post-install.md" target="_blank"> Surface Hub 2 上設定 Windows 10 專業版或企業版 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-343">To fully configure Surface Hub 2S as a personal productivity device, see <a href="surface-hub-2-post-install.md" target="_blank">Configure Windows 10 Pro or Enterprise on Surface Hub 2</a>.</span></span>

> [!NOTE]
><span data-ttu-id="1af15-344">如果本文所述的步驟無法成功將您的裝置遷移至 Windows 10 專業版或 Surface Hub 2 的 Enterprise，請接觸 <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub 支援 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-344">If the steps outlined in this article don't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2, contact <a href="https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support" target="_blank"> Surface Hub Support</a>.</span></span>

## <span data-ttu-id="1af15-345">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="1af15-345">Roll back to Windows 10 Team</span></span>

<span data-ttu-id="1af15-346">如果您想要將裝置還原至 Windows 10 小組，請參閱 <a href="surface-hub-2s-recover-reset.md" target="_blank"> 重設及恢復 Surface Hub 2 秒 </a> 。</span><span class="sxs-lookup"><span data-stu-id="1af15-346">If you want to restore your device to Windows 10 Team, see <a href="surface-hub-2s-recover-reset.md" target="_blank"> Reset and recovery for Surface Hub 2S</a>.</span></span>

> [!NOTE]
> <span data-ttu-id="1af15-347">在回滾至 Windows 10 小組之前，建議您先取消從 SEMM 取消中樞。</span><span class="sxs-lookup"><span data-stu-id="1af15-347">Before rolling back to Windows 10 Team, it's recommended to first unenroll Hub from SEMM.</span></span> <span data-ttu-id="1af15-348">若要深入瞭解，請參閱 [從 SEMM 取消註冊 Surface 裝置](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="1af15-348">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="1af15-349">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="1af15-349">Version history</span></span>

<span data-ttu-id="1af15-350">下表摘要列出本文所做的變更。</span><span class="sxs-lookup"><span data-stu-id="1af15-350">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="1af15-351">版本</span><span class="sxs-lookup"><span data-stu-id="1af15-351">Version</span></span> | <span data-ttu-id="1af15-352">日期</span><span class="sxs-lookup"><span data-stu-id="1af15-352">Date</span></span>               | <span data-ttu-id="1af15-353">描述</span><span class="sxs-lookup"><span data-stu-id="1af15-353">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="1af15-354">向量.</span><span class="sxs-lookup"><span data-stu-id="1af15-354">v.</span></span> <span data-ttu-id="1af15-355">1.4</span><span class="sxs-lookup"><span data-stu-id="1af15-355">1.4</span></span>  | <span data-ttu-id="1af15-356">2020年12月14日</span><span class="sxs-lookup"><span data-stu-id="1af15-356">December 14, 2020</span></span> | <span data-ttu-id="1af15-357">提供有關安裝 MSI 檔案（適用于 Surface Hub 2 的 Windows 10 專業版和 Enterprise OS）的 [詳細資訊](#install-surface-hub-2-drivers-and-firmware) ，說明您可能需要重新開機第二次，視系統的狀態而定。</span><span class="sxs-lookup"><span data-stu-id="1af15-357">Provides [further info](#install-surface-hub-2-drivers-and-firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2," advising that a second reboot may be necessary depending on the state of your system.</span></span>                                                          |
| <span data-ttu-id="1af15-358">向量.</span><span class="sxs-lookup"><span data-stu-id="1af15-358">v.</span></span> <span data-ttu-id="1af15-359">1.3</span><span class="sxs-lookup"><span data-stu-id="1af15-359">1.3</span></span>  | <span data-ttu-id="1af15-360">2020年12月3日</span><span class="sxs-lookup"><span data-stu-id="1af15-360">December 3, 2020</span></span> | <span data-ttu-id="1af15-361">更新了有關 [管理 SEMM 註冊](#managing-semm-enrollment)的指導方針。</span><span class="sxs-lookup"><span data-stu-id="1af15-361">Updated with guidance about [managing SEMM enrollment](#managing-semm-enrollment).</span></span>                                                       |
| <span data-ttu-id="1af15-362">向量.</span><span class="sxs-lookup"><span data-stu-id="1af15-362">v.</span></span> <span data-ttu-id="1af15-363">1.2</span><span class="sxs-lookup"><span data-stu-id="1af15-363">1.2</span></span>  | <span data-ttu-id="1af15-364">2020年9月29日</span><span class="sxs-lookup"><span data-stu-id="1af15-364">September 29, 2020</span></span> | <span data-ttu-id="1af15-365">針對可用性意見反應的各種更新。</span><span class="sxs-lookup"><span data-stu-id="1af15-365">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="1af15-366">向量.</span><span class="sxs-lookup"><span data-stu-id="1af15-366">v.</span></span> <span data-ttu-id="1af15-367">1.1</span><span class="sxs-lookup"><span data-stu-id="1af15-367">1.1</span></span>  | <span data-ttu-id="1af15-368">2020年9月15日</span><span class="sxs-lookup"><span data-stu-id="1af15-368">September 15, 2020</span></span> | <span data-ttu-id="1af15-369">在簡介中放置了說明安裝新作業系統的授權需求。</span><span class="sxs-lookup"><span data-stu-id="1af15-369">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="1af15-370">向量.</span><span class="sxs-lookup"><span data-stu-id="1af15-370">v.</span></span> <span data-ttu-id="1af15-371">1.0</span><span class="sxs-lookup"><span data-stu-id="1af15-371">1.0</span></span>  | <span data-ttu-id="1af15-372">2020年9月1日</span><span class="sxs-lookup"><span data-stu-id="1af15-372">September 1, 2020</span></span>  | <span data-ttu-id="1af15-373">新文章。</span><span class="sxs-lookup"><span data-stu-id="1af15-373">New article.</span></span>                                                                                           |
