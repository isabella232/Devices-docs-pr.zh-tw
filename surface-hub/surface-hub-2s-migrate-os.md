---
title: 移轉到 Windows 10 專業版或 Surface Hub 2 企業版
description: 如何從位於 Surface Hub 2 的 Windows 10 團隊遷移到 Windows 10 專業版或 Windows 10 Enterprise。
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
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297636"
---
# <span data-ttu-id="115bb-104">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="115bb-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

- [<span data-ttu-id="115bb-105">文章版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="115bb-105">Article version history</span></span>](#version-history)

<span data-ttu-id="115bb-106">Surface Hub 2 與已安裝 Windows 10 的小組。</span><span class="sxs-lookup"><span data-stu-id="115bb-106">Surface Hub 2S comes with Windows 10 Team installed.</span></span> <span data-ttu-id="115bb-107">此自訂版本的 Windows 10 有利於在會議室環境中共同作業。</span><span class="sxs-lookup"><span data-stu-id="115bb-107">This customized edition of Windows 10 facilitates collaboration in meeting-room environments.</span></span> <span data-ttu-id="115bb-108">您現在可以改為執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。</span><span class="sxs-lookup"><span data-stu-id="115bb-108">You can now instead run Windows 10 Pro or Enterprise to use your Surface Hub 2S much like any other PC.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="115bb-109">此遷移程式需要您遵循本文所述的特定程式。</span><span class="sxs-lookup"><span data-stu-id="115bb-109">This migration process requires you to follow the specific procedure that's described in this article.</span></span> <span data-ttu-id="115bb-110">繼續之前，請先閱讀 [解決方案元件](#solution-components) 及 [遷移和安裝工作流程](#migration-and-installation-workflow-summary)。</span><span class="sxs-lookup"><span data-stu-id="115bb-110">Before you continue, read [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary).</span></span>

> [!NOTE]
> <span data-ttu-id="115bb-111">當您安裝 Windows 10 專業版或企業版時，您需要與現有的 Windows 10 小組授權不同的新授權。</span><span class="sxs-lookup"><span data-stu-id="115bb-111">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span>

<span data-ttu-id="115bb-112">使用不同的電腦和可下載的 *SURFACE UEFI 配置介面* 工具，從 Windows 10 團隊開始遷移。</span><span class="sxs-lookup"><span data-stu-id="115bb-112">Start the migration from Windows 10 Team by using a separate PC and the downloadable *Surface UEFI Configurator* tool.</span></span> <span data-ttu-id="115bb-113">此工具會建立一個套件，其中包含您套用至 Surface Hub 2 秒的新 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="115bb-113">The tool creates a package that contains a new UEFI setting that you apply to the Surface Hub 2S.</span></span>  

<span data-ttu-id="115bb-114">Surface UEFI 配置處理常式在 (SEMM) 中，成為 Surface Enterprise 管理模式的介面。</span><span class="sxs-lookup"><span data-stu-id="115bb-114">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="115bb-115">它可集中管理公司環境中的 Surface 裝置上的固件設定。</span><span class="sxs-lookup"><span data-stu-id="115bb-115">It enables centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="115bb-116">如需詳細資訊，請參閱 [Microsoft Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="115bb-116">For more information, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 
## <span data-ttu-id="115bb-117">解決方案元件</span><span class="sxs-lookup"><span data-stu-id="115bb-117">Solution components</span></span>

- <span data-ttu-id="115bb-118">執行 Windows 10 小組的 Surface Hub 2 秒裝置</span><span class="sxs-lookup"><span data-stu-id="115bb-118">Surface Hub 2S device running Windows 10 Team</span></span>
- <span data-ttu-id="115bb-119">運行 Windows 10 的個別裝置</span><span class="sxs-lookup"><span data-stu-id="115bb-119">Separate device running Windows 10</span></span>
- <span data-ttu-id="115bb-120">用於建立 SEMM 套件的 Surface UEFI 設定檔工具</span><span class="sxs-lookup"><span data-stu-id="115bb-120">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="115bb-121">Windows 10 專業版或企業版作業系統影像、版本1903或更新版本</span><span class="sxs-lookup"><span data-stu-id="115bb-121">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="115bb-122">兩個有 16 GB 儲存空間的 USB 磁片磁碟機，FAT32 格式</span><span class="sxs-lookup"><span data-stu-id="115bb-122">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="115bb-123">在 Surface Hub 2 中，Windows 10 專業版與企業版的驅動程式與固件，在 Microsoft Windows 安裝程式 (的 MSI) 檔案</span><span class="sxs-lookup"><span data-stu-id="115bb-123">The drivers and firmware for Windows 10 Pro and Enterprise in a Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="115bb-124">網際網路連線</span><span class="sxs-lookup"><span data-stu-id="115bb-124">Internet connection</span></span>
- <span data-ttu-id="115bb-125">影像處理方案 (選用) </span><span class="sxs-lookup"><span data-stu-id="115bb-125">Imaging solution (optional)</span></span>
 
## <span data-ttu-id="115bb-126">遷移和安裝工作流程摘要</span><span class="sxs-lookup"><span data-stu-id="115bb-126">Migration and installation workflow summary</span></span>

| <span data-ttu-id="115bb-127">步驟</span><span class="sxs-lookup"><span data-stu-id="115bb-127">Step</span></span>  | <span data-ttu-id="115bb-128">動作</span><span class="sxs-lookup"><span data-stu-id="115bb-128">Action</span></span>                                                                                                 | <span data-ttu-id="115bb-129">摘要</span><span class="sxs-lookup"><span data-stu-id="115bb-129">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="115bb-130">sr-1</span><span class="sxs-lookup"><span data-stu-id="115bb-130">1</span></span> | <span data-ttu-id="115bb-131">[驗證 Surface Hub 2 上的 UEFI 版本](#verify-the-uefi-version-on-surface-hub-2s)。</span><span class="sxs-lookup"><span data-stu-id="115bb-131">[Verify the UEFI version on the Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s).</span></span>                                  | <span data-ttu-id="115bb-132">UEFI 版本必須是 *694.2938.768.0* 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="115bb-132">The UEFI version must be version *694.2938.768.0* or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="115bb-133">pplx-2</span><span class="sxs-lookup"><span data-stu-id="115bb-133">2</span></span> | [<span data-ttu-id="115bb-134">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件。</span><span class="sxs-lookup"><span data-stu-id="115bb-134">Download Surface UEFI Configurator and the Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="115bb-135">在 [ **[表面工具](https://www.microsoft.com/download/details.aspx?id=46703)** ] 頁面上 </a> ，選取 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-135">On the **[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)** page</a>, select **Download**.</span></span> <span data-ttu-id="115bb-136">然後選取並下載 **SURFACE UEFI 設定檔 MSI**檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="115bb-136">Then select and download the **Surface UEFI Configurator MSI file**, and install it on a separate PC.</span></span> <span data-ttu-id="115bb-137">此外，請下載 [適用于 Surface Hub 2 MSI 檔案的 Windows 10 專業版與企業作業系統的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="115bb-137">Also download the [Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span></a> <span data-ttu-id="115bb-138">儲存此套件以供在步驟5使用。</span><span class="sxs-lookup"><span data-stu-id="115bb-138">Save this package for use in step 5.</span></span> |
| <span data-ttu-id="115bb-139">3</span><span class="sxs-lookup"><span data-stu-id="115bb-139">3</span></span> | [<span data-ttu-id="115bb-140">準備 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="115bb-140">Prepare the SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="115bb-141">準備運行 Surface UEFI 配置器所需的憑證，或使用您目前的憑證。</span><span class="sxs-lookup"><span data-stu-id="115bb-141">Prepare the certificate that's required to run Surface UEFI Configurator, or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="115bb-142">4</span><span class="sxs-lookup"><span data-stu-id="115bb-142">4</span></span> | [<span data-ttu-id="115bb-143">建立 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="115bb-143">Create a SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="115bb-144">啟動 Surface UEFI 設定檔以在 USB 磁片磁碟機上建立 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="115bb-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive.</span></span> <span data-ttu-id="115bb-145">這個套件將包含您需要在 Surface Hub 2 的設定檔。</span><span class="sxs-lookup"><span data-stu-id="115bb-145">This package will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="115bb-146">將這些 SEMM 套件檔案複製到您電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="115bb-146">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="115bb-147">500</span><span class="sxs-lookup"><span data-stu-id="115bb-147">5</span></span> | [<span data-ttu-id="115bb-148">使用 Windows 10 影像、SEMM 套件以及驅動程式和固件載入 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="115bb-148">Load a USB flash drive with Windows 10 image, the SEMM package, and drivers and firmware.</span></span>](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="115bb-149">建立包含 Windows 10 影像的 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="115bb-149">Create a USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="115bb-150">在這個範例中，磁片磁碟機名為 *BOOTME*。</span><span class="sxs-lookup"><span data-stu-id="115bb-150">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="115bb-151">在 Surface Hub 2 (的 Windows 10 專業版和 Enterprise OS 中新增驅動程式及固件，) 從步驟 2) 到 *BOOTME* 磁片的 SEMM (套件檔案。</span><span class="sxs-lookup"><span data-stu-id="115bb-151">Add the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (from step 2) and the SEMM package files (from step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="115bb-152">6</span><span class="sxs-lookup"><span data-stu-id="115bb-152">6</span></span> | [<span data-ttu-id="115bb-153">更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="115bb-153">Update the UEFI on the Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="115bb-154">使用 *BOOTME* 磁片磁碟機啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="115bb-154">Use the *BOOTME* drive to boot the Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="115bb-155">utf-7</span><span class="sxs-lookup"><span data-stu-id="115bb-155">7</span></span> | [<span data-ttu-id="115bb-156">安裝 Windows 10 專業版或企業版。</span><span class="sxs-lookup"><span data-stu-id="115bb-156">Install Windows 10 Pro or Enterprise.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="115bb-157">使用 *BOOTME* 磁片磁碟機來安裝 Windows 10 專業版或企業版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="115bb-157">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="115bb-158">型</span><span class="sxs-lookup"><span data-stu-id="115bb-158">8</span></span> | [<span data-ttu-id="115bb-159">安裝適用于 Windows 10 專業版與企業版的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="115bb-159">Install drivers and firmware for Windows 10 Pro and Enterprise.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="115bb-160">若要確保您的裝置擁有所有最新的更新和驅動程式，請 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 MSI 檔案上安裝 Windows 10 專業版和企業版 OS 的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="115bb-160">To ensure that your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="115bb-161">9</span><span class="sxs-lookup"><span data-stu-id="115bb-161">9</span></span> | [<span data-ttu-id="115bb-162">將 Surface Hub 秒設定為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="115bb-162">Configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="115bb-163">啟用建議的設定和應用程式，以將 Surface Hub 秒優化為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="115bb-163">Enable the recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="115bb-164">驗證 Surface Hub 2 上的 UEFI 版本</span><span class="sxs-lookup"><span data-stu-id="115bb-164">Verify the UEFI version on Surface Hub 2S</span></span>

<span data-ttu-id="115bb-165">在您將 Surface Hub 從 Windows 10 小組遷移至 Windows 10 桌上出版前，您需要 UEFI 版本 *694.2938.768.0* 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="115bb-165">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need UEFI version *694.2938.768.0* or later.</span></span>
 
**<span data-ttu-id="115bb-166">若要在您的系統上驗證 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="115bb-166">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="115bb-167">在 Surface Hub 2 的 [首頁] 頁面上，選取 [**開始**]，然後在 [**所有應用程式**]  >  **表面**) 開啟 [Surface app] (。</span><span class="sxs-lookup"><span data-stu-id="115bb-167">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="115bb-168">選取 **您的 surface** 以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="115bb-168">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="115bb-169">如果 UEFI 版本是 *694.2938.768.0* 或更新版本，如下列影像所示，您可以建立 SEMM 套件來啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="115bb-169">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![螢幕擷取畫面顯示 Surface app 中的 [您的 Surface] 頁面。](images/shm-fig1.png)
 
   - <span data-ttu-id="115bb-171">如果 UEFI 版本早于版本 *694.2938.768.0*，請使用下列其中一種方法來取得較新的版本</span><span class="sxs-lookup"><span data-stu-id="115bb-171">If the UEFI version is earlier than version *694.2938.768.0*, use one of the following methods to get a newer version</span></span>
   
#### <span data-ttu-id="115bb-172">透過 Windows Update 更新 UEFI</span><span class="sxs-lookup"><span data-stu-id="115bb-172">Update UEFI via Windows Update</span></span>

1. <span data-ttu-id="115bb-173">在 Surface Hub 2 秒，請以系統 **管理員**身分登入。</span><span class="sxs-lookup"><span data-stu-id="115bb-173">On your Surface Hub 2S, sign in as **Admin**.</span></span>

    >[!Note]
    > <span data-ttu-id="115bb-174">如果您不知道您的使用者名稱或系統管理員密碼，您必須重設裝置。</span><span class="sxs-lookup"><span data-stu-id="115bb-174">If you don't know your user name or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="115bb-175">如需詳細資訊，請參閱 [重設及恢復 Surface Hub 2 秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)。</span><span class="sxs-lookup"><span data-stu-id="115bb-175">For more information, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

1. <span data-ttu-id="115bb-176">移至 [**所有應用程式**]  >  **設定**[  >  **更新與安全性**]  >  **Windows update**，然後安裝所有更新。</span><span class="sxs-lookup"><span data-stu-id="115bb-176">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and install all updates.</span></span>
1. <span data-ttu-id="115bb-177">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="115bb-177">Restart the device.</span></span>
1. <span data-ttu-id="115bb-178">使用 Surface app 驗證 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="115bb-178">Verify the UEFI version by using the Surface app.</span></span> <span data-ttu-id="115bb-179">如果 UEFI 版本不是版本 *694.2938.768.0* 或更新版本，請重複這些步驟，或使用下列程式來取得最新的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="115bb-179">If the UEFI version isn't version *694.2938.768.0* or later, repeat these steps, or use the following procedure to get the latest UEFI version.</span></span>

#### <span data-ttu-id="115bb-180">透過裸機復原 (BMR) 影像來更新 UEFI</span><span class="sxs-lookup"><span data-stu-id="115bb-180">Update the UEFI via bare metal recovery (BMR) image</span></span>

1.  <span data-ttu-id="115bb-181">移至 [ [surface](https://support.microsoft.com/surfacerecoveryimage) 復原] 網站，然後選取 [ **Surface Hub 2 秒**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-181">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**.</span></span>
3.  <span data-ttu-id="115bb-182">輸入您的中樞序列值。</span><span class="sxs-lookup"><span data-stu-id="115bb-182">Enter your Hub serial number.</span></span> <span data-ttu-id="115bb-183">它位於中樞背面的電源連接旁邊。</span><span class="sxs-lookup"><span data-stu-id="115bb-183">It's located on the back of the Hub next to the power connection.</span></span>
4.  <span data-ttu-id="115bb-184">按照指示，透過安裝 Windows 10 Team 2020 更新，將影像下載到格式化的 USB 磁片磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="115bb-184">Follow the directions to download the image onto a formatted USB drive by installing the Windows 10 Team 2020 Update.</span></span>
5.  <span data-ttu-id="115bb-185">更新之後，裝置會在 (OOBE) 設定中輸入現成的體驗。</span><span class="sxs-lookup"><span data-stu-id="115bb-185">After the update, the device enters out-of-box-experience (OOBE) setup.</span></span> <span data-ttu-id="115bb-186">您不需要完成設定。</span><span class="sxs-lookup"><span data-stu-id="115bb-186">You don't need to complete setup.</span></span> <span data-ttu-id="115bb-187">UEFI 版本已更新。</span><span class="sxs-lookup"><span data-stu-id="115bb-187">The UEFI version is already updated.</span></span> <span data-ttu-id="115bb-188">請改為按住電源按鈕，直到螢幕關閉為止，再關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="115bb-188">Instead power down the device by holding the power button until the screen turns off.</span></span>

### <span data-ttu-id="115bb-189">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="115bb-189">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="115bb-190">在不同的電腦上，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="115bb-190">On a separate PC, follow these steps:</span></span>

1. <span data-ttu-id="115bb-191">在 [ <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> 表面工具] 頁面上 </a> ，選取 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-191">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>  
1. <span data-ttu-id="115bb-192">選取並下載 Surface UEFI 設定檔 MSI 檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="115bb-192">Select and download the Surface UEFI Configurator MSI file, and install it on a separate PC.</span></span> <span data-ttu-id="115bb-193">安裝 Windows 10 小組版時，Surface UEFI 組態工具無法在 Surface Hub 2 上執行。</span><span class="sxs-lookup"><span data-stu-id="115bb-193">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="115bb-194">下載 [Surface Hub 2 驅動程式和固件 Windows 安裝程式 MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案。</span><span class="sxs-lookup"><span data-stu-id="115bb-194">Download the [Surface Hub 2 drivers and firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="115bb-195">當您安裝新的作業系統時，您將會用到這個檔案。</span><span class="sxs-lookup"><span data-stu-id="115bb-195">You'll use this file when you install the new operating system.</span></span>

### <span data-ttu-id="115bb-196">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="115bb-196">Prepare the SEMM certificate</span></span>

<span data-ttu-id="115bb-197">如果您尚未使用 Surface UEFI 配置器，您必須準備證書。</span><span class="sxs-lookup"><span data-stu-id="115bb-197">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="115bb-198">這個憑證可確保在裝置註冊 SEMM 之後，您只能使用以核准憑證建立的套件來修改 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="115bb-198">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span>

<span data-ttu-id="115bb-199">您取得憑證的方式取決於貴組織的規模或複雜度。</span><span class="sxs-lookup"><span data-stu-id="115bb-199">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="115bb-200">企業組織通常會維持自己的基礎結構，以根據標準安全慣例產生證書。</span><span class="sxs-lookup"><span data-stu-id="115bb-200">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="115bb-201">中型企業及其他人通常選擇從合作夥伴提供者取得憑證。</span><span class="sxs-lookup"><span data-stu-id="115bb-201">Medium-sized businesses and others often choose to get certificates from partner providers.</span></span> <span data-ttu-id="115bb-202">對於不具備 IT 專業人員或缺乏專門 IT 安全小組的組織而言，建議使用此選項。</span><span class="sxs-lookup"><span data-stu-id="115bb-202">This option is recommended for organizations that don't have as much IT expertise or lack a dedicated IT security team.</span></span>

- <span data-ttu-id="115bb-203">或者，您也可以使用 PowerShell 腳本來產生自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="115bb-203">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="115bb-204">如需詳細資訊，請參閱 [企業管理模式證書需求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="115bb-204">For more information, see the [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="115bb-205">或者，您可以使用 PowerShell 建立您自己的憑證。</span><span class="sxs-lookup"><span data-stu-id="115bb-205">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="115bb-206">如需詳細資訊，請參閱 [新的 SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 檔。</span><span class="sxs-lookup"><span data-stu-id="115bb-206">For more information, see the [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) documentation.</span></span>

<span data-ttu-id="115bb-207">Surface UEFI 設定檔建立的 SEMM 套件必須以憑證加以保護。</span><span class="sxs-lookup"><span data-stu-id="115bb-207">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="115bb-208">憑證會驗證設定檔的簽名，然後才能套用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="115bb-208">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="115bb-209">如需詳細資訊，請參閱 [SEMM](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 檔。</span><span class="sxs-lookup"><span data-stu-id="115bb-209">For more information, see the [SEMM](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
### <span data-ttu-id="115bb-210">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="115bb-210">Create a SEMM package</span></span>

1. <span data-ttu-id="115bb-211">在另一部電腦上，安裝您先前下載的 Surface UEFI 組態工具。</span><span class="sxs-lookup"><span data-stu-id="115bb-211">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span>

1. <span data-ttu-id="115bb-212">開啟 Surface UEFI 配置器，然後選取 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-212">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![Surface UEFI 配置器開始畫面。](images/shm-fig2.png)
   
1. <span data-ttu-id="115bb-214">選取 [ **Surface 裝置**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-214">Select **Surface Devices**, and then select **Next**.</span></span>

   ![螢幕擷取畫面顯示已選取 [Surface 裝置] 選項。](images/shm-fig3.png)
  
1. <span data-ttu-id="115bb-216">選取 [設定 **套件**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-216">Select **Configuration Package**.</span></span>

   ![螢幕擷取畫面顯示已選取 [選取配置套件]。](images/shm-fig4.png)
  
1. <span data-ttu-id="115bb-218">選取 [ **憑證保護**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-218">Select **Certificate Protection**.</span></span>

   ![螢幕擷取畫面顯示如何選擇 [選取憑證保護]。](images/shm-fig5.png)

   <span data-ttu-id="115bb-220">系統會提示您新增憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="115bb-220">You'll be prompted to add your certificate .pfx file.</span></span>

   ![螢幕擷取畫面顯示在何處新增您的憑證檔案。](images/shm-fig6.png)
   
1. <span data-ttu-id="115bb-222">輸入您的憑證密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-222">Enter your certificate password, and then select **OK**.</span></span>

   ![螢幕擷取畫面顯示用於輸入並確認您的憑證密碼的欄位。](images/shm-fig7.png)

1. <span data-ttu-id="115bb-224">選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="115bb-224">Select **Password Protection** to add a password to the Surface UEFI.</span></span> <span data-ttu-id="115bb-225">每當您啟動至 UEFI 時，就會需要此密碼。</span><span class="sxs-lookup"><span data-stu-id="115bb-225">You'll need this password whenever you boot to the UEFI.</span></span> *<span data-ttu-id="115bb-226">我們強烈建議您設定要在 Surface Hub 的2秒使用的 UEFI 密碼。</span><span class="sxs-lookup"><span data-stu-id="115bb-226">We strongly recommend that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>*

   ![螢幕擷取畫面顯示在何處選取密碼保護。](images/shm-fig8.png)
   
1. <span data-ttu-id="115bb-228">設定 UEFI 密碼，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-228">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="115bb-229">將密碼儲存在可供管理 Surface Hub 之 IT 系統管理員存取的安全位置。</span><span class="sxs-lookup"><span data-stu-id="115bb-229">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> *<span data-ttu-id="115bb-230">如果此密碼遺失，就無法復原。</span><span class="sxs-lookup"><span data-stu-id="115bb-230">If this password is lost, it can't be recovered.</span></span>*

   ![螢幕擷取畫面顯示您設定 UEFI 密碼的位置。](images/shm-fig9.png)

1. <span data-ttu-id="115bb-232">選取 [ **Surface Hub 2 秒**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-232">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![螢幕擷取畫面顯示在何處選取 Surface Hub 2 到2。](images/shm-fig10.png)
   
1. <span data-ttu-id="115bb-234">再次選取 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="115bb-234">Select **Next** again.</span></span>

    ![螢幕擷取畫面顯示如何選取 [選擇哪些元件] 下的 [下一步]。](images/shm-fig10a.png)

1. <span data-ttu-id="115bb-236">若要允許安裝 Windows 10 專業版或企業版，請開啟 **EnableOsMigration**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-236">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![螢幕擷取畫面顯示如何選取 [啟用 O S] 遷移。](images/shm-fig11.png)
    
    ![螢幕擷取畫面顯示如何將啟用 OS 遷移的位置設定為 [開啟]。](images/shm-fig12.png)

### <span data-ttu-id="115bb-239">管理 SEMM 登記</span><span class="sxs-lookup"><span data-stu-id="115bb-239">Manage SEMM enrollment</span></span>

<span data-ttu-id="115bb-240">將裝置註冊至 SEMM 會影響您可以管理它的方式。</span><span class="sxs-lookup"><span data-stu-id="115bb-240">Enrolling a device into SEMM affects how you can manage it.</span></span> <span data-ttu-id="115bb-241">例如，在您套用 SEMM 套件之後，所有的 UEFI 設定都無法在裝置的 UEFI 功能表中 (鎖定) 。</span><span class="sxs-lookup"><span data-stu-id="115bb-241">For example, after you apply a SEMM package, all UEFI settings are unavailable (locked) in the device's UEFI menu.</span></span> <span data-ttu-id="115bb-242">其他設定（例如 **IPv6 FOR PXE 啟動** ）的預設值也無法使用。</span><span class="sxs-lookup"><span data-stu-id="115bb-242">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span>

<span data-ttu-id="115bb-243">若要在完成遷移後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="115bb-243">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="115bb-244">如果您套用另一個 SEMM 套件來變更 UEFI 設定，則在建立新的 SEMM 套件時，您必須使用原始證書。</span><span class="sxs-lookup"><span data-stu-id="115bb-244">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="115bb-245">使用 UEFI 組態工具工具，並將 **EnableOSMigration** *關閉* (*不在) 的原始* 遷移步驟中。</span><span class="sxs-lookup"><span data-stu-id="115bb-245">Use the UEFI Configurator tool and leave **EnableOSMigration** *off* (not *on* as in the original migration steps).</span></span>

#### <span data-ttu-id="115bb-246">如果您與合作夥伴合作</span><span class="sxs-lookup"><span data-stu-id="115bb-246">If you work with partners</span></span>

<span data-ttu-id="115bb-247">如果您的公司 outsources Surface Hub 2 遷移至 Windows 10 專業版或企業版，您可能會想要讓合作夥伴將 SEMM 憑證、SEMM 套件和 UEFI 密碼轉讓給您。</span><span class="sxs-lookup"><span data-stu-id="115bb-247">If your company outsources the Surface Hub 2 migration to Windows 10 Pro or Enterprise, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span> <span data-ttu-id="115bb-248">或者，在您遷移中心之後，您可以立即取消將其從 SEMM 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="115bb-248">Or, after you migrate the Hub, you can immediately unenroll it from SEMM.</span></span> <span data-ttu-id="115bb-249">此步驟可讓您對 UEFI 進行本機管理，並將裝置傳輸至另一方。</span><span class="sxs-lookup"><span data-stu-id="115bb-249">This step enables local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="115bb-250">但我們還是強烈建議您使用 UEFI 密碼，這可以在遷移之後進行設定。</span><span class="sxs-lookup"><span data-stu-id="115bb-250">But we still strongly recommend that you use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="115bb-251">若要深入瞭解，請參閱 [管理 SURFACE UEFI 設定](https://docs.microsoft.com/surface/manage-surface-uefi-settings)。</span><span class="sxs-lookup"><span data-stu-id="115bb-251">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <span data-ttu-id="115bb-252">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="115bb-252">To roll back to Windows 10 Team</span></span>

<span data-ttu-id="115bb-253">如果您選擇在進行遷移之後將裝置還原至 Windows 10 小組，請 [參閱本文稍後所述](#to-roll-back-to-windows-10-team)，我們建議您先取消從 SEMM 取消中樞。</span><span class="sxs-lookup"><span data-stu-id="115bb-253">If you choose to restore your device to Windows 10 Team after the migration [as described later in this article](#to-roll-back-to-windows-10-team), we recommend that you first unenroll Hub from SEMM.</span></span> <span data-ttu-id="115bb-254">若要深入瞭解，請參閱 [從 SEMM 取消註冊 Surface 裝置](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="115bb-254">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

#### <span data-ttu-id="115bb-255">將 SEMM 套件儲存至 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="115bb-255">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="115bb-256">將 USB 磁片磁碟機連線至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="115bb-256">Connect a USB drive to your PC.</span></span>
1. <span data-ttu-id="115bb-257">選擇 [ **中心2秒**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-257">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![螢幕擷取畫面顯示在何處選取中心2秒](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="115bb-259">在建立 SEMM 套件時，USB 磁片磁碟機上的所有現有資料都會被清除。</span><span class="sxs-lookup"><span data-stu-id="115bb-259">All existing data on the USB drive will be erased when the SEMM package is built.</span></span> <span data-ttu-id="115bb-260">在您建立 SEMM 套件之前，請先從 USB 磁片磁碟機移除任何您需要的檔案。</span><span class="sxs-lookup"><span data-stu-id="115bb-260">Before you build the SEMM package, remove any files that you need from the USB drive.</span></span>
   
1. <span data-ttu-id="115bb-261">選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-261">Select **Build**.</span></span>

   ![螢幕擷取畫面顯示要選取組建的位置。](images/shm-fig14.png)

1. <span data-ttu-id="115bb-263">捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-263">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="115bb-264">您的 SEMM 套件現已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="115bb-264">Your SEMM package is now ready.</span></span> <span data-ttu-id="115bb-265">它包含 SEMM 套件 *DfciUpdate. dfi* ，以及包含 SEMM *指紋*的文字檔，也就是憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="115bb-265">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM *thumbprint*, which is the last two characters of the certificate's thumbprint.</span></span>

   ![螢幕擷取畫面顯示要選取結束的位置。](images/shm-fig15.png)
   
4. <span data-ttu-id="115bb-267">儲存憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="115bb-267">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="115bb-268">當您在 Surface Hub 2 上套用套件時，您必須使用這些字元來啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="115bb-268">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="115bb-269">使用 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式和固件載入 USB 快閃磁碟機</span><span class="sxs-lookup"><span data-stu-id="115bb-269">Load a USB flash drive with a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="115bb-270">您可以使用下列其中一個選項，在版本 *1903* 或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：</span><span class="sxs-lookup"><span data-stu-id="115bb-270">You can install a Windows 10 Pro or Enterprise image (version *1903* or later) by using one of the following options:</span></span>

- <span data-ttu-id="115bb-271">您目前的影像解決方案。</span><span class="sxs-lookup"><span data-stu-id="115bb-271">Your current imaging solution.</span></span>

- <span data-ttu-id="115bb-272">[Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator)。</span><span class="sxs-lookup"><span data-stu-id="115bb-272">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator).</span></span> <span data-ttu-id="115bb-273">使用這個工具來建立可引導的 Windows 10 影像。</span><span class="sxs-lookup"><span data-stu-id="115bb-273">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="115bb-274">影像可以包含所有目前的 Windows 10 更新、Microsoft Office、其他 app，以及所需的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="115bb-274">The image can include all current Windows 10 updates, Microsoft Office, other apps, and the required drivers and firmware.</span></span>

- <span data-ttu-id="115bb-275">包含 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="115bb-275">A USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="115bb-276">然後在 Surface Hub 2 上安裝 [適用于 Windows 10 專業版與企業版的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974) 。</span><span class="sxs-lookup"><span data-stu-id="115bb-276">Then install [drivers and firmware for Windows 10 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) on Surface Hub 2.</span></span>
 
<span data-ttu-id="115bb-277">下列步驟說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後新增 SEMM 套件檔案，以及 Windows 10 專業版和企業作業系統在 Surface Hub 2 MSI 檔案中的驅動程式與固件。</span><span class="sxs-lookup"><span data-stu-id="115bb-277">The following steps show how to create a USB flash drive from installation media and then add the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="115bb-278">如果您使用其他部署方法，請移至 [Surface Hub 2 上的更新 UEFI，以啟用本文的作業系統遷移](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 一節。</span><span class="sxs-lookup"><span data-stu-id="115bb-278">If you use another deployment method, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="115bb-279">完成安裝之後，您需要適用于 Windows 10 專業版或 Windows 10 Enterprise 的有效授權，與現有的 Windows 10 小組授權不同。</span><span class="sxs-lookup"><span data-stu-id="115bb-279">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="115bb-280">若要建立 Windows 10 專業版安裝，請按照指示下載 [windows 10](https://www.microsoft.com/software-download/windows10)中的媒體建立工具。</span><span class="sxs-lookup"><span data-stu-id="115bb-280">To create a Windows 10 Pro installation, follow the instructions to download the media creation tool at [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span> <span data-ttu-id="115bb-281">若要下載 Windows 10 企業版，請移至 [Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="115bb-281">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

1. <span data-ttu-id="115bb-282">插入新的 USB 儲存空間磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="115bb-282">Insert a new USB storage drive.</span></span>
1. <span data-ttu-id="115bb-283">開啟 [媒體建立工具]，選取 [ **建立安裝媒體**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-283">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![螢幕擷取畫面顯示建立安裝媒體的選項。](images/shm-fig16.png)
   
3. <span data-ttu-id="115bb-285">選取 [語言]，然後選取 [ **Windows 10** ] 和 [ \*\*64 (x64) \*\*]。</span><span class="sxs-lookup"><span data-stu-id="115bb-285">Select a language, and then select **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="115bb-286">然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-286">Then select **Next**.</span></span>

   ![螢幕擷取畫面顯示您選取語言、O S 及架構類型的位置。](images/shm-fig17.png)
   
4. <span data-ttu-id="115bb-288">選取 [ **USB 快閃記憶體磁片磁碟機**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-288">Select **USB flash drive**, and then select **Next**.</span></span>

   ![螢幕擷取畫面顯示如何選取 [U S B] 快閃記憶體磁片磁碟機。](images/shm-fig18.png)
   
5. <span data-ttu-id="115bb-290">下載完成後，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-290">When the download finishes, select **Finish**.</span></span>

   ![顯示 U S B 磁片磁碟機已準備就緒且包含 [完成] 按鈕的畫面。](images/shm-fig19.png)
   
6. <span data-ttu-id="115bb-292">在 Surface Hub 2 上複製 SEMM 套件檔案和 Windows 10 專業版作業系統的驅動程式及固件， (MSI 檔案) 到包含您 Windows 10 影像 (*BOOTME*) 的 USB 快閃記憶體磁片磁碟機根目錄。</span><span class="sxs-lookup"><span data-stu-id="115bb-292">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="115bb-293">BOOTME USB 磁片磁碟機將包含：</span><span class="sxs-lookup"><span data-stu-id="115bb-293">The BOOTME USB drive will contain:</span></span>

    - <span data-ttu-id="115bb-294">您的 Windows 10 可引導影像。</span><span class="sxs-lookup"><span data-stu-id="115bb-294">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="115bb-295">複製到 USB 磁片磁碟機根目錄的 SEMM 套件檔案：</span><span class="sxs-lookup"><span data-stu-id="115bb-295">The SEMM package files, copied to the root of the USB drive:</span></span>
    
      - <span data-ttu-id="115bb-296">*DfciUpdate dfi*。</span><span class="sxs-lookup"><span data-stu-id="115bb-296">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="115bb-297">包含 SEMM 指紋的文字檔。</span><span class="sxs-lookup"><span data-stu-id="115bb-297">A text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="115bb-298"> (在這個範例中，檔案是 *SurfaceUEFI_2020Aug25_1058.txt*。 ) 自動產生的日期時間戳記會對應到您使用 Surface UEFI 設定檔建立檔案的日期。</span><span class="sxs-lookup"><span data-stu-id="115bb-298">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date-time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="115bb-299">Surface Hub 2 上的 Windows 10 專業版與 Enterprise OS 的驅動程式和固件 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="115bb-299">The drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="115bb-300">將此檔案複製到 USB 磁片磁碟機的根目錄。</span><span class="sxs-lookup"><span data-stu-id="115bb-300">Copy this file to the root of the USB drive.</span></span>

### <span data-ttu-id="115bb-301">更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移</span><span class="sxs-lookup"><span data-stu-id="115bb-301">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="115bb-302">將您的 BOOTME 磁片磁碟機插入 Surface Hub 2 的 USB-A 埠。</span><span class="sxs-lookup"><span data-stu-id="115bb-302">Insert your BOOTME drive into the USB-A port on the Surface Hub 2S.</span></span> <span data-ttu-id="115bb-303">如需其所需內容的清單，請參閱上一節。</span><span class="sxs-lookup"><span data-stu-id="115bb-303">For a list of its required contents, see the previous section.</span></span>

1. <span data-ttu-id="115bb-304">若要引導至 UEFI：</span><span class="sxs-lookup"><span data-stu-id="115bb-304">To boot into UEFI:</span></span>

   1. <span data-ttu-id="115bb-305">關閉) Surface Hub 2 的 (關閉。</span><span class="sxs-lookup"><span data-stu-id="115bb-305">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="115bb-306">按住 [ **音量 +**]，然後按下再放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="115bb-306">Press and hold **Volume +**, and then press and release the power button.</span></span> <span data-ttu-id="115bb-307">保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。</span><span class="sxs-lookup"><span data-stu-id="115bb-307">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![[繪圖] 會顯示 [音量] 和 [電源] 按鈕。](images/shm-fig20.png)
      
3. <span data-ttu-id="115bb-309">當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (建議) ）。</span><span class="sxs-lookup"><span data-stu-id="115bb-309">When the device restarts, enter the UEFI password that you created earlier, if applicable (recommended).</span></span>

   ![系統密碼] 畫面。](images/shm-fig22.png)
   
4. <span data-ttu-id="115bb-311">從 [UEFI] 功能表中，選取 [ **管理**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-311">From the UEFI menu, select **Management**.</span></span> <span data-ttu-id="115bb-312">然後選取 [  **從 USB 安裝**]。</span><span class="sxs-lookup"><span data-stu-id="115bb-312">Then select  **Install from USB**.</span></span>

   ![螢幕擷取畫面顯示要選取管理的位置，然後按一下 [從 U S B 安裝]。](images/shm-fig21.png)
   
5. <span data-ttu-id="115bb-314">選取 [ **立即重新開機**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="115bb-314">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="115bb-315">裝置會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="115bb-315">The device will restart.</span></span> <span data-ttu-id="115bb-316">它會在視窗中間顯示白色 Microsoft 標誌，然後關閉。</span><span class="sxs-lookup"><span data-stu-id="115bb-316">It will display a white Microsoft logo in the middle of the window and then shut down.</span></span>

   ![螢幕擷取畫面顯示一則訊息，提示您重新開機。](images/shm-fig25.png)
   
6. <span data-ttu-id="115bb-318">按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="115bb-318">Press and release the power button.</span></span> <span data-ttu-id="115bb-319">在出現的紅色對話方塊中，選擇 [啟用 Surface Enterprise 管理模式]。</span><span class="sxs-lookup"><span data-stu-id="115bb-319">In the red dialog box that appears, choose to activate Surface Enterprise Management Mode.</span></span>

7. <span data-ttu-id="115bb-320">輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。</span><span class="sxs-lookup"><span data-stu-id="115bb-320">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="115bb-321">然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="115bb-321">Then select **OK**.</span></span>

   ![螢幕擷取畫面顯示 [確認啟用] 對話方塊，您可以在此輸入雙字元憑證指紋及您的 UEFI 設定密碼。](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="115bb-323">在裝置上啟用 SEMM 之後，就會套用新的 UEFI 設定 **EnableOSMigration** 。</span><span class="sxs-lookup"><span data-stu-id="115bb-323">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="115bb-324">您不能再存取 Windows 10 小組。</span><span class="sxs-lookup"><span data-stu-id="115bb-324">You can no longer access Windows 10 Team.</span></span> <span data-ttu-id="115bb-325">相反地，您必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="115bb-325">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span>

   <span data-ttu-id="115bb-326">裝置會重新開機。</span><span class="sxs-lookup"><span data-stu-id="115bb-326">The device reboots.</span></span> <span data-ttu-id="115bb-327">它會在畫面中間顯示白色標誌，然後再次關閉。</span><span class="sxs-lookup"><span data-stu-id="115bb-327">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <span data-ttu-id="115bb-328">安裝 Windows 10 專業版或企業版</span><span class="sxs-lookup"><span data-stu-id="115bb-328">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="115bb-329">如果您的可引導 Windows 10 專業版或企業版磁碟機尚不在 Surface Hub 2 USB-A 埠中，請立即插入。</span><span class="sxs-lookup"><span data-stu-id="115bb-329">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="115bb-330">然後按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="115bb-330">Then press and release the power button.</span></span>

    <span data-ttu-id="115bb-331">裝置啟動時，您會在畫面中間看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="115bb-331">When the device starts, you'll see the white logo in the middle of the screen.</span></span> <span data-ttu-id="115bb-332">然後旋轉的圓圈會出現在白色標誌下方。</span><span class="sxs-lookup"><span data-stu-id="115bb-332">Then a spinning circle appears below the white logo.</span></span>

3. <span data-ttu-id="115bb-333">如果 Surface 裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置 (拔下電源線，然後再插回) 。</span><span class="sxs-lookup"><span data-stu-id="115bb-333">If the Surface device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="115bb-334">再次插入電源線之後，裝置會在幾秒後啟動。</span><span class="sxs-lookup"><span data-stu-id="115bb-334">After you plug in the power cord again, the device should boot after a few seconds.</span></span> <span data-ttu-id="115bb-335">然後，您會在畫面中間看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="115bb-335">Then you'll see the white logo in the middle of screen.</span></span>

    <span data-ttu-id="115bb-336">如果裝置沒有開啟，請按下並放開 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="115bb-336">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="115bb-337">在畫面中間看到標誌之後，按住 [音量] 按鈕，直到您看到白色標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="115bb-337">Immediately after you see the logo in the middle of the screen, press and hold the volume button until you see the spinning circle below the white logo.</span></span>
 
   ![[音量] 和 [電源] 按鈕的圖片。](images/shm-fig26.png)
   
4. <span data-ttu-id="115bb-339">當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或 Enterprise (版本1903或) 更新版本。</span><span class="sxs-lookup"><span data-stu-id="115bb-339">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="115bb-340">安裝 Surface Hub 2 驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="115bb-340">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="115bb-341">若要確保 Surface Hub 2 是最新版本，請安裝 [適用于 Windows 10 專業版與企業版的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="115bb-341">To ensure that your Surface Hub 2 is up to date, install [drivers and firmware for Windows 10 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="115bb-342">然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="115bb-342">Then reboot the device.</span></span> <span data-ttu-id="115bb-343">讓表面保持開啟一個小時，然後再次重新開機。</span><span class="sxs-lookup"><span data-stu-id="115bb-343">Keep the Surface turned on for an hour, and then reboot it again.</span></span> <span data-ttu-id="115bb-344">第二次重新開機時，系統不會提示您。</span><span class="sxs-lookup"><span data-stu-id="115bb-344">You won't be prompted for the second reboot.</span></span> <span data-ttu-id="115bb-345">這種暫停和額外的重新開機可確保固件已完全更新。</span><span class="sxs-lookup"><span data-stu-id="115bb-345">This pause and extra reboot ensures that the firmware has been fully updated.</span></span>
 
## <span data-ttu-id="115bb-346">設定建議的設定</span><span class="sxs-lookup"><span data-stu-id="115bb-346">Configure recommended settings</span></span>

<span data-ttu-id="115bb-347">若要將 Surface Hub 秒設定為個人生產力裝置，請參閱在 [Surface Hub 2 上設定 Windows 10 專業版或企業版](surface-hub-2-post-install.md)。</span><span class="sxs-lookup"><span data-stu-id="115bb-347">To configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="115bb-348">如果您無法成功將裝置遷移至 Windows 10 專業版或 Surface Hub 的 Enterprise，請依照本文所述的步驟，接觸 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="115bb-348">If you can't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2 by following the steps outlined in this article, contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="115bb-349">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="115bb-349">To roll back to Windows 10 Team</span></span>

<span data-ttu-id="115bb-350">如果您想要將裝置還原至 Windows 10 小組，請參閱 [重設及恢復 Surface Hub 2 秒](surface-hub-2s-recover-reset.md)。</span><span class="sxs-lookup"><span data-stu-id="115bb-350">If you want to restore your device to Windows 10 Team, see [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

> [!NOTE]
> <span data-ttu-id="115bb-351">在您回滾至 Windows 10 團隊之前，建議您先從 SEMM 取消對 Surface Hub 的註冊。</span><span class="sxs-lookup"><span data-stu-id="115bb-351">Before you roll back to Windows 10 Team, we recommended that you first unenroll the Surface Hub from SEMM.</span></span> <span data-ttu-id="115bb-352">若要深入瞭解，請參閱 [從 SEMM 取消註冊 Surface 裝置](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="115bb-352">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="115bb-353">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="115bb-353">Version history</span></span>

<span data-ttu-id="115bb-354">下表摘要列出本文所做的變更。</span><span class="sxs-lookup"><span data-stu-id="115bb-354">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="115bb-355">版本</span><span class="sxs-lookup"><span data-stu-id="115bb-355">Version</span></span> | <span data-ttu-id="115bb-356">日期</span><span class="sxs-lookup"><span data-stu-id="115bb-356">Date</span></span>               | <span data-ttu-id="115bb-357">說明</span><span class="sxs-lookup"><span data-stu-id="115bb-357">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="115bb-358">向量.</span><span class="sxs-lookup"><span data-stu-id="115bb-358">v.</span></span> <span data-ttu-id="115bb-359">1.4</span><span class="sxs-lookup"><span data-stu-id="115bb-359">1.4</span></span>  | <span data-ttu-id="115bb-360">2020年12月14日</span><span class="sxs-lookup"><span data-stu-id="115bb-360">December 14, 2020</span></span> | <span data-ttu-id="115bb-361">提供有關安裝 MSI 檔案（適用于 Surface Hub 2 的 Windows 10 專業版和 Enterprise OS）的 [詳細資訊](#install-surface-hub-2-drivers-and-firmware) ，說明您可能需要重新開機第二次，視系統的狀態而定。</span><span class="sxs-lookup"><span data-stu-id="115bb-361">Provides [further info](#install-surface-hub-2-drivers-and-firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2," advising that a second reboot may be necessary depending on the state of your system.</span></span>                                                          |
| <span data-ttu-id="115bb-362">向量.</span><span class="sxs-lookup"><span data-stu-id="115bb-362">v.</span></span> <span data-ttu-id="115bb-363">1.3</span><span class="sxs-lookup"><span data-stu-id="115bb-363">1.3</span></span>  | <span data-ttu-id="115bb-364">2020年12月3日</span><span class="sxs-lookup"><span data-stu-id="115bb-364">December 3, 2020</span></span> | <span data-ttu-id="115bb-365">更新了有關 [管理 SEMM 註冊](#manage-semm-enrollment)的指導方針。</span><span class="sxs-lookup"><span data-stu-id="115bb-365">Updated with guidance about [managing SEMM enrollment](#manage-semm-enrollment).</span></span>                                                       |
| <span data-ttu-id="115bb-366">向量.</span><span class="sxs-lookup"><span data-stu-id="115bb-366">v.</span></span> <span data-ttu-id="115bb-367">1.2</span><span class="sxs-lookup"><span data-stu-id="115bb-367">1.2</span></span>  | <span data-ttu-id="115bb-368">2020年9月29日</span><span class="sxs-lookup"><span data-stu-id="115bb-368">September 29, 2020</span></span> | <span data-ttu-id="115bb-369">針對可用性意見反應的各種更新。</span><span class="sxs-lookup"><span data-stu-id="115bb-369">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="115bb-370">向量.</span><span class="sxs-lookup"><span data-stu-id="115bb-370">v.</span></span> <span data-ttu-id="115bb-371">1.1</span><span class="sxs-lookup"><span data-stu-id="115bb-371">1.1</span></span>  | <span data-ttu-id="115bb-372">2020年9月15日</span><span class="sxs-lookup"><span data-stu-id="115bb-372">September 15, 2020</span></span> | <span data-ttu-id="115bb-373">在簡介中放置了說明安裝新作業系統的授權需求。</span><span class="sxs-lookup"><span data-stu-id="115bb-373">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="115bb-374">向量.</span><span class="sxs-lookup"><span data-stu-id="115bb-374">v.</span></span> <span data-ttu-id="115bb-375">1.0</span><span class="sxs-lookup"><span data-stu-id="115bb-375">1.0</span></span>  | <span data-ttu-id="115bb-376">2020年9月1日</span><span class="sxs-lookup"><span data-stu-id="115bb-376">September 1, 2020</span></span>  | <span data-ttu-id="115bb-377">新文章。</span><span class="sxs-lookup"><span data-stu-id="115bb-377">New article.</span></span>                                                                                           |
