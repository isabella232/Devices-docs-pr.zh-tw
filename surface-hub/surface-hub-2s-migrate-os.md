---
title: 移轉到 Windows 10 專業版或 Surface Hub 2 企業版
description: 如何從 2 Windows 10 團隊版 2 Surface Hub到 Windows 10 專業版 Windows 10 企業版。
keywords: Surface Hub桌面Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 5e2eaa88fe0e5677c78cb5a7d49802ed71d4b902
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576743"
---
# <a name="migrate-to-windows-10-pro-or-enterprise-on-surface-hub-2"></a><span data-ttu-id="81e56-104">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="81e56-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

- [<span data-ttu-id="81e56-105">文章版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="81e56-105">Article version history</span></span>](#version-history)

<span data-ttu-id="81e56-106">Surface Hub 2S 隨附Windows 10 團隊版安裝。</span><span class="sxs-lookup"><span data-stu-id="81e56-106">Surface Hub 2S comes with Windows 10 Team installed.</span></span> <span data-ttu-id="81e56-107">此自訂版本的 Windows 10可促進在會議室環境中共同合作。</span><span class="sxs-lookup"><span data-stu-id="81e56-107">This customized edition of Windows 10 facilitates collaboration in meeting-room environments.</span></span> <span data-ttu-id="81e56-108">您現在可以改為執行 Windows 10 專業版 或 Enterprise，以使用 Surface Hub 2S，就像任何其他電腦一樣。</span><span class="sxs-lookup"><span data-stu-id="81e56-108">You can now instead run Windows 10 Pro or Enterprise to use your Surface Hub 2S much like any other PC.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="81e56-109">此移移程式要求您遵循本文所述的特定程式。</span><span class="sxs-lookup"><span data-stu-id="81e56-109">This migration process requires you to follow the specific procedure that's described in this article.</span></span> <span data-ttu-id="81e56-110">在您繼續之前，請閱讀[解決方案元件及](#solution-components)[移移和安裝工作流程](#migration-and-installation-workflow-summary)。</span><span class="sxs-lookup"><span data-stu-id="81e56-110">Before you continue, read [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary).</span></span>

> [!NOTE]
> <span data-ttu-id="81e56-111">當您安裝Windows 10 專業版或Enterprise時，您需要與現有授權Windows 10 團隊版授權。</span><span class="sxs-lookup"><span data-stu-id="81e56-111">When you install Windows 10 Pro or Enterprise, you need a new licence that's separate from your existing Windows 10 Team license.</span></span>

<span data-ttu-id="81e56-112">使用個別電腦Windows 10 團隊版可下載*的 Surface UEFI Configurator*工具，從伺服器開始移移。</span><span class="sxs-lookup"><span data-stu-id="81e56-112">Start the migration from Windows 10 Team by using a separate PC and the downloadable *Surface UEFI Configurator* tool.</span></span> <span data-ttu-id="81e56-113">此工具會建立套件，其中包含套用至 2S Surface Hub UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="81e56-113">The tool creates a package that contains a new UEFI setting that you apply to the Surface Hub 2S.</span></span>  

<span data-ttu-id="81e56-114">Surface UEFI Configurator 在 SEMM Enterprise管理模式 (介面) 。</span><span class="sxs-lookup"><span data-stu-id="81e56-114">Surface UEFI Configurator works as an interface into Surface Enterprise Management Mode (SEMM).</span></span> <span data-ttu-id="81e56-115">它可在公司環境中集中管理 Surface 裝置上的固件設定。</span><span class="sxs-lookup"><span data-stu-id="81e56-115">It enables centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="81e56-116">詳細資訊，請參閱[Microsoft Surface Enterprise管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="81e56-116">For more information, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 
## <a name="solution-components"></a><span data-ttu-id="81e56-117">解決方案元件</span><span class="sxs-lookup"><span data-stu-id="81e56-117">Solution components</span></span>

- <span data-ttu-id="81e56-118">Surface Hub 2S 裝置Windows 10 團隊版</span><span class="sxs-lookup"><span data-stu-id="81e56-118">Surface Hub 2S device running Windows 10 Team</span></span>
- <span data-ttu-id="81e56-119">個別裝置Windows 10</span><span class="sxs-lookup"><span data-stu-id="81e56-119">Separate device running Windows 10</span></span>
- <span data-ttu-id="81e56-120">Surface UEFI Configurator 工具可建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="81e56-120">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="81e56-121">Windows 10 專業版或Enterprise OS 映射、版本 1903 或更新版本</span><span class="sxs-lookup"><span data-stu-id="81e56-121">Windows 10 Pro or Enterprise OS image, version 1903 or later</span></span>
- <span data-ttu-id="81e56-122">兩個儲存空間為 16 GB 的 USB 磁片磁碟機，採用 FAT32 格式</span><span class="sxs-lookup"><span data-stu-id="81e56-122">Two USB drives that have 16 GB of storage, FAT32 format</span></span>
- <span data-ttu-id="81e56-123">在 2 個 Microsoft Windows 10 專業版 Enterprise Windows安裝程式Surface Hub MSI (安裝程式) 驅動程式和) </span><span class="sxs-lookup"><span data-stu-id="81e56-123">The drivers and firmware for Windows 10 Pro and Enterprise in a Surface Hub 2 Microsoft Windows Installer (MSI) file</span></span>
- <span data-ttu-id="81e56-124">網際網路連線</span><span class="sxs-lookup"><span data-stu-id="81e56-124">Internet connection</span></span>
- <span data-ttu-id="81e56-125">影像解決方案 (選) </span><span class="sxs-lookup"><span data-stu-id="81e56-125">Imaging solution (optional)</span></span>
 
## <a name="migration-and-installation-workflow-summary"></a><span data-ttu-id="81e56-126">移移和安裝工作流程摘要</span><span class="sxs-lookup"><span data-stu-id="81e56-126">Migration and installation workflow summary</span></span>

| <span data-ttu-id="81e56-127">步驟</span><span class="sxs-lookup"><span data-stu-id="81e56-127">Step</span></span>  | <span data-ttu-id="81e56-128">動作</span><span class="sxs-lookup"><span data-stu-id="81e56-128">Action</span></span>                                                                                                 | <span data-ttu-id="81e56-129">摘要</span><span class="sxs-lookup"><span data-stu-id="81e56-129">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="81e56-130">1</span><span class="sxs-lookup"><span data-stu-id="81e56-130">1</span></span> | <span data-ttu-id="81e56-131">[驗證 2S 上的 UEFI Surface Hub版本](#verify-the-uefi-version-on-surface-hub-2s)。</span><span class="sxs-lookup"><span data-stu-id="81e56-131">[Verify the UEFI version on the Surface Hub 2S](#verify-the-uefi-version-on-surface-hub-2s).</span></span>                                  | <span data-ttu-id="81e56-132">UEFI 版本必須是版本 *694.2938.768.0* 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="81e56-132">The UEFI version must be version *694.2938.768.0* or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="81e56-133">2</span><span class="sxs-lookup"><span data-stu-id="81e56-133">2</span></span> | [<span data-ttu-id="81e56-134">下載 Surface UEFI 組Surface Hub 2 個驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="81e56-134">Download Surface UEFI Configurator and the Surface Hub 2 drivers and firmware.</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="81e56-135">在 IT**[版 Surface 工具頁面上](https://www.microsoft.com/download/details.aspx?id=46703)** </a> ，選取 下載\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="81e56-135">On the **[Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703)** page</a>, select **Download**.</span></span> <span data-ttu-id="81e56-136">然後選取並下載 **Surface UEFI Configurator MSI 檔案**，然後將它安裝在另一部電腦上安裝。</span><span class="sxs-lookup"><span data-stu-id="81e56-136">Then select and download the **Surface UEFI Configurator MSI file**, and install it on a separate PC.</span></span> <span data-ttu-id="81e56-137">此外，在[2 MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案上下載 Windows 10 專業版 和 Enterprise OS Surface Hub驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="81e56-137">Also download the [Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span></a> <span data-ttu-id="81e56-138">儲存此套件以用於步驟 5。</span><span class="sxs-lookup"><span data-stu-id="81e56-138">Save this package for use in step 5.</span></span> |
| <span data-ttu-id="81e56-139">3</span><span class="sxs-lookup"><span data-stu-id="81e56-139">3</span></span> | [<span data-ttu-id="81e56-140">準備 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="81e56-140">Prepare the SEMM certificate.</span></span>](#prepare-the-semm-certificate)                                                                          | <span data-ttu-id="81e56-141">準備執行 Surface UEFI Configurator 所需的憑證，或使用您目前的憑證。</span><span class="sxs-lookup"><span data-stu-id="81e56-141">Prepare the certificate that's required to run Surface UEFI Configurator, or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="81e56-142">4</span><span class="sxs-lookup"><span data-stu-id="81e56-142">4</span></span> | [<span data-ttu-id="81e56-143">建立 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="81e56-143">Create a SEMM package.</span></span>](#create-a-semm-package)                                                                               | <span data-ttu-id="81e56-144">啟動 Surface UEFI Configurator，在 USB 磁碟機上建立 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="81e56-144">Start Surface UEFI Configurator to create a SEMM package on a USB drive.</span></span> <span data-ttu-id="81e56-145">此套件會包含您需要套用至 2S Surface Hub的組Surface Hub檔案。</span><span class="sxs-lookup"><span data-stu-id="81e56-145">This package will contain the configuration files you need to apply on Surface Hub 2S.</span></span> <span data-ttu-id="81e56-146">將這些 SEMM 套件檔案複製到您 PC 上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="81e56-146">Copy these SEMM package files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="81e56-147">5</span><span class="sxs-lookup"><span data-stu-id="81e56-147">5</span></span> | [<span data-ttu-id="81e56-148">載入 USB 快閃Windows 10圖像、SEMM 套件、驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="81e56-148">Load a USB flash drive with Windows 10 image, the SEMM package, and drivers and firmware.</span></span>](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="81e56-149">建立包含影像的 USB Windows 10磁碟機。</span><span class="sxs-lookup"><span data-stu-id="81e56-149">Create a USB drive that contains a Windows 10 image.</span></span> <span data-ttu-id="81e56-150">在此範例中，該磁碟機名為 *BOOTME*。</span><span class="sxs-lookup"><span data-stu-id="81e56-150">In this example, the drive is named *BOOTME*.</span></span> <span data-ttu-id="81e56-151">從步驟 (2) 將 Surface Hub Windows 10 專業版 和 Enterprise OS 的驅動程式和 Enterprise 作業系統)  (從步驟 4) 新增到*BOOTME*磁碟機。</span><span class="sxs-lookup"><span data-stu-id="81e56-151">Add the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (from step 2) and the SEMM package files (from step 4) to the *BOOTME* drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="81e56-152">6</span><span class="sxs-lookup"><span data-stu-id="81e56-152">6</span></span> | [<span data-ttu-id="81e56-153">更新 2S 上的 UEFI Surface Hub啟用 OS 移移。</span><span class="sxs-lookup"><span data-stu-id="81e56-153">Update the UEFI on the Surface Hub 2S to enable OS migration.</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="81e56-154">使用*BOOTME*磁碟機將 Surface Hub 2S 引導至 UEFI 功能表並安裝 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="81e56-154">Use the *BOOTME* drive to boot the Surface Hub 2S to the UEFI menu and install the SEMM package.</span></span>|
| <span data-ttu-id="81e56-155">7</span><span class="sxs-lookup"><span data-stu-id="81e56-155">7</span></span> | [<span data-ttu-id="81e56-156">安裝Windows 10 專業版或Enterprise。</span><span class="sxs-lookup"><span data-stu-id="81e56-156">Install Windows 10 Pro or Enterprise.</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="81e56-157">使用*BOOTME*磁碟機Windows 10 專業版或Enterprise版本 1903 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="81e56-157">Use the *BOOTME* drive to install Windows 10 Pro or Enterprise version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="81e56-158">8</span><span class="sxs-lookup"><span data-stu-id="81e56-158">8</span></span> | [<span data-ttu-id="81e56-159">安裝適用于 Windows 10 專業版 和 Enterprise 的驅動程式和Enterprise。</span><span class="sxs-lookup"><span data-stu-id="81e56-159">Install drivers and firmware for Windows 10 Pro and Enterprise.</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="81e56-160">為了確保您的裝置擁有所有最新的更新和驅動程式，請于 Windows 10 專業版 2 MSI 檔案Enterprise安裝 Surface Hub 驅動程式 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 和固件。</span><span class="sxs-lookup"><span data-stu-id="81e56-160">To ensure that your device has all the latest updates and drivers, install the <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank">Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span></a>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="81e56-161">9</span><span class="sxs-lookup"><span data-stu-id="81e56-161">9</span></span> | [<span data-ttu-id="81e56-162">將 Surface Hub 2S 設定為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="81e56-162">Configure Surface Hub 2S as a personal productivity device.</span></span>](#configure-recommended-settings)                                        |  <span data-ttu-id="81e56-163">啟用建議的設定和應用程式，以將 2S Surface Hub個人生產力裝置優化。</span><span class="sxs-lookup"><span data-stu-id="81e56-163">Enable the recommended settings and applications to optimize Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a><span data-ttu-id="81e56-164">在 2S 上驗證 UEFI Surface Hub版本</span><span class="sxs-lookup"><span data-stu-id="81e56-164">Verify the UEFI version on Surface Hub 2S</span></span>

<span data-ttu-id="81e56-165">在您將 Surface Hub Windows 10 團隊版 Windows 10桌上出版之前，您需要 UEFI 版本*694.2938.768.0*或更新版本。</span><span class="sxs-lookup"><span data-stu-id="81e56-165">Before you migrate Surface Hub from Windows 10 Team to Windows 10 Desktop, you need UEFI version *694.2938.768.0* or later.</span></span>
 
**<span data-ttu-id="81e56-166">若要驗證您系統的 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="81e56-166">To verify the UEFI version on your system:</span></span>**

1. <span data-ttu-id="81e56-167">在 Surface Hub 2S 首頁上，選取開始 **，然後**開啟 Surface 應用程式 (所有**App**  >  **Surface**) 。</span><span class="sxs-lookup"><span data-stu-id="81e56-167">On the Surface Hub 2S home page, select **Start**, and then open the Surface app (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="81e56-168">選取**您的 Surface**以顯示有關 Surface Hub的資訊，包括裝置上的目前 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="81e56-168">Select **Your Surface** to display information about Surface Hub, including the current UEFI version on the device.</span></span> 
   - <span data-ttu-id="81e56-169">如果 UEFI 版本 *是 694.2938.768.0* 或更新版本，如下圖所示，您可以建立 SEMM 套件來啟用 OS 移移。</span><span class="sxs-lookup"><span data-stu-id="81e56-169">If the UEFI version is *694.2938.768.0* or later, as the following image shows, you can create the SEMM package to enable OS migration.</span></span>

       ![螢幕擷取畫面顯示 Surface 應用程式中的 「您的 Surface」頁面。](images/shm-fig1.png)
 
   - <span data-ttu-id="81e56-171">如果 UEFI 版本早于版本 *694.2938.768.0，* 請使用下列其中一種方法取得較新版本</span><span class="sxs-lookup"><span data-stu-id="81e56-171">If the UEFI version is earlier than version *694.2938.768.0*, use one of the following methods to get a newer version</span></span>
   
#### <a name="update-uefi-via-windows-update"></a><span data-ttu-id="81e56-172">透過更新更新 UEFI Windows UEFI</span><span class="sxs-lookup"><span data-stu-id="81e56-172">Update UEFI via Windows Update</span></span>

1. <span data-ttu-id="81e56-173">在 2S Surface Hub上，以系統管理員**的登錄。**</span><span class="sxs-lookup"><span data-stu-id="81e56-173">On your Surface Hub 2S, sign in as **Admin**.</span></span>

    >[!Note]
    > <span data-ttu-id="81e56-174">如果您不知道使用者名稱或系統管理員密碼，則需要重設裝置。</span><span class="sxs-lookup"><span data-stu-id="81e56-174">If you don't know your user name or admin password, you'll need to reset the device.</span></span> <span data-ttu-id="81e56-175">詳細資訊，請參閱[2S 的重設Surface Hub復原](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)。</span><span class="sxs-lookup"><span data-stu-id="81e56-175">For more information, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

1. <span data-ttu-id="81e56-176">請前往所有**應用程式**  >  **設定**  >  **更新**和安全性Windows  >  **更新**，並安裝所有更新。</span><span class="sxs-lookup"><span data-stu-id="81e56-176">Go to **All apps** > **Settings** > **Update and Security** > **Windows Update**, and install all updates.</span></span>
1. <span data-ttu-id="81e56-177">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="81e56-177">Restart the device.</span></span>
1. <span data-ttu-id="81e56-178">使用 Surface 應用程式驗證 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="81e56-178">Verify the UEFI version by using the Surface app.</span></span> <span data-ttu-id="81e56-179">如果 UEFI 版本不是版本 *694.2938.768.0* 或更新版本，請重複這些步驟，或使用下列程式取得最新的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="81e56-179">If the UEFI version isn't version *694.2938.768.0* or later, repeat these steps, or use the following procedure to get the latest UEFI version.</span></span>

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a><span data-ttu-id="81e56-180">透過裸露金屬修復更新 UEFI (BMR) 圖像</span><span class="sxs-lookup"><span data-stu-id="81e56-180">Update the UEFI via bare metal recovery (BMR) image</span></span>

1.  <span data-ttu-id="81e56-181">前往 Surface[修復網站，](https://support.microsoft.com/surfacerecoveryimage)然後選取**Surface Hub 2S**。</span><span class="sxs-lookup"><span data-stu-id="81e56-181">Go to the [Surface recovery site](https://support.microsoft.com/surfacerecoveryimage) and select **Surface Hub 2S**.</span></span>
3.  <span data-ttu-id="81e56-182">輸入您的中樞序號。</span><span class="sxs-lookup"><span data-stu-id="81e56-182">Enter your Hub serial number.</span></span> <span data-ttu-id="81e56-183">它位於電源連接旁的中樞背面。</span><span class="sxs-lookup"><span data-stu-id="81e56-183">It's located on the back of the Hub next to the power connection.</span></span>
4.  <span data-ttu-id="81e56-184">請遵循指示，安裝 2020 Update Windows 10 團隊版格式化的 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="81e56-184">Follow the directions to download the image onto a formatted USB drive by installing the Windows 10 Team 2020 Update.</span></span>
5.  <span data-ttu-id="81e56-185">更新之後，裝置會輸入 OOBE (即) 體驗。</span><span class="sxs-lookup"><span data-stu-id="81e56-185">After the update, the device enters out-of-box-experience (OOBE) setup.</span></span> <span data-ttu-id="81e56-186">您不需要完成設定。</span><span class="sxs-lookup"><span data-stu-id="81e56-186">You don't need to complete setup.</span></span> <span data-ttu-id="81e56-187">UEFI 版本已經更新。</span><span class="sxs-lookup"><span data-stu-id="81e56-187">The UEFI version is already updated.</span></span> <span data-ttu-id="81e56-188">而是按住電源按鈕，直到螢幕關閉，以關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="81e56-188">Instead power down the device by holding the power button until the screen turns off.</span></span>

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a><span data-ttu-id="81e56-189">下載 Surface UEFI 組Surface Hub 2 個驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="81e56-189">Download Surface UEFI Configurator and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="81e56-190">在個別的 PC 上，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="81e56-190">On a separate PC, follow these steps:</span></span>

1. <span data-ttu-id="81e56-191">在 IT <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> 版 Surface 工具頁面上 </a> ，選取 下載 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="81e56-191">On the <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> Surface Tools for IT page</a>, select **Download**.</span></span>  
1. <span data-ttu-id="81e56-192">選取並下載 Surface UEFI Configurator MSI 檔案，然後安裝在另一部電腦上安裝。</span><span class="sxs-lookup"><span data-stu-id="81e56-192">Select and download the Surface UEFI Configurator MSI file, and install it on a separate PC.</span></span> <span data-ttu-id="81e56-193">安裝 2S 版時，Surface UEFI Surface Hub工具Windows 10 團隊版執行。</span><span class="sxs-lookup"><span data-stu-id="81e56-193">The Surface UEFI Configurator tool can't be run on a Surface Hub 2S while Windows 10 Team edition is installed.</span></span>

1. <span data-ttu-id="81e56-194">下載安裝程式 MSI Surface Hub 2 個驅動程式[和Windows的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="81e56-194">Download the [Surface Hub 2 drivers and firmware Windows Installer MSI file](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="81e56-195">當您安裝新作業系統時，會使用此檔案。</span><span class="sxs-lookup"><span data-stu-id="81e56-195">You'll use this file when you install the new operating system.</span></span>

### <a name="prepare-the-semm-certificate"></a><span data-ttu-id="81e56-196">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="81e56-196">Prepare the SEMM certificate</span></span>

<span data-ttu-id="81e56-197">如果您之前尚未使用 Surface UEFI Configurator，則需要準備憑證。</span><span class="sxs-lookup"><span data-stu-id="81e56-197">If you haven't used Surface UEFI Configurator before, you need to prepare a certificate.</span></span> <span data-ttu-id="81e56-198">此憑證可確保在裝置註冊 SEMM 之後，您只能使用使用核准憑證所建立套件來修改 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="81e56-198">This certificate ensures that after a device is enrolled in SEMM, you can modify UEFI settings only by using packages that are created with the approved certificate.</span></span>

<span data-ttu-id="81e56-199">取得憑證的方式取決於貴組織的大小或複雜度：</span><span class="sxs-lookup"><span data-stu-id="81e56-199">How you get a certificate depends on the size or complexity of your organization:</span></span>

- <span data-ttu-id="81e56-200">Enterprise組織通常會維護自己的基礎結構，以根據標準安全性做法產生憑證。</span><span class="sxs-lookup"><span data-stu-id="81e56-200">Enterprise organizations typically maintain their own infrastructure to generate certificates according to standard security practices.</span></span>

- <span data-ttu-id="81e56-201">中型企業和其他企業通常會選擇從合作夥伴提供者取得憑證。</span><span class="sxs-lookup"><span data-stu-id="81e56-201">Medium-sized businesses and others often choose to get certificates from partner providers.</span></span> <span data-ttu-id="81e56-202">對於沒有太多 IT 專業知識或缺少專屬 IT 安全小組的組織，建議您使用此選項。</span><span class="sxs-lookup"><span data-stu-id="81e56-202">This option is recommended for organizations that don't have as much IT expertise or lack a dedicated IT security team.</span></span>

- <span data-ttu-id="81e56-203">或者，您可以使用 PowerShell 腳本產生自我簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="81e56-203">Alternatively, you can generate a self-signed certificate by using a PowerShell script.</span></span> <span data-ttu-id="81e56-204">詳細資訊，請參閱 Surface [Enterprise管理模式憑證需求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="81e56-204">For more information, see the [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="81e56-205">或者，您可以使用 PowerShell 建立您自己的憑證。</span><span class="sxs-lookup"><span data-stu-id="81e56-205">Or you can use PowerShell to create your own certificate.</span></span> <span data-ttu-id="81e56-206">詳細資訊請參閱自我 [簽署憑證](https://docs.microsoft.com/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) 檔。</span><span class="sxs-lookup"><span data-stu-id="81e56-206">For more information, see the [Self-signed certificate](https://docs.microsoft.com/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) documentation.</span></span>

<span data-ttu-id="81e56-207">Surface UEFI Configurator 所建立之 SEMM 套件必須以憑證保護。</span><span class="sxs-lookup"><span data-stu-id="81e56-207">The SEMM package that Surface UEFI Configurator creates must be secured with a certificate.</span></span> <span data-ttu-id="81e56-208">憑證會先驗證組組檔案的簽章，再適用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="81e56-208">The certificate verifies the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="81e56-209">詳細資訊請參閱 [SEMM](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 檔。</span><span class="sxs-lookup"><span data-stu-id="81e56-209">For more information, see the [SEMM](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
### <a name="create-a-semm-package"></a><span data-ttu-id="81e56-210">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="81e56-210">Create a SEMM package</span></span>

1. <span data-ttu-id="81e56-211">在個別的電腦上安裝您先前下載的 Surface UEFI Configurator 工具。</span><span class="sxs-lookup"><span data-stu-id="81e56-211">On a separate PC, install the Surface UEFI Configurator tool that you downloaded earlier.</span></span>

1. <span data-ttu-id="81e56-212">開啟 Surface UEFI Configurator， **然後選取**開始 。</span><span class="sxs-lookup"><span data-stu-id="81e56-212">Open Surface UEFI Configurator, and then select **Start**.</span></span>

   ![Surface UEFI Configurator 開始畫面。](images/shm-fig2.png)
   
1. <span data-ttu-id="81e56-214">選取 **Surface Devices，** 然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="81e56-214">Select **Surface Devices**, and then select **Next**.</span></span>

   ![螢幕擷取畫面顯示已選取的 Surface Devices 選項。](images/shm-fig3.png)
  
1. <span data-ttu-id="81e56-216">選取 **組組套件**。</span><span class="sxs-lookup"><span data-stu-id="81e56-216">Select **Configuration Package**.</span></span>

   ![螢幕擷取畫面顯示已選取 「選取組組套件」。](images/shm-fig4.png)
  
1. <span data-ttu-id="81e56-218">選取 **憑證保護**。</span><span class="sxs-lookup"><span data-stu-id="81e56-218">Select **Certificate Protection**.</span></span>

   ![螢幕擷取畫面顯示是選擇 「選取憑證保護」。](images/shm-fig5.png)

   <span data-ttu-id="81e56-220">系統會提示您新增憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="81e56-220">You'll be prompted to add your certificate .pfx file.</span></span>

   ![螢幕擷取畫面顯示要新增憑證檔案的位置。](images/shm-fig6.png)
   
1. <span data-ttu-id="81e56-222">輸入您的憑證密碼， **然後選取確定**。</span><span class="sxs-lookup"><span data-stu-id="81e56-222">Enter your certificate password, and then select **OK**.</span></span>

   ![螢幕擷取畫面顯示要輸入並確認憑證密碼的欄位。](images/shm-fig7.png)

1. <span data-ttu-id="81e56-224">選取 **密碼保護** 以在 Surface UEFI 中新增密碼。</span><span class="sxs-lookup"><span data-stu-id="81e56-224">Select **Password Protection** to add a password to the Surface UEFI.</span></span> <span data-ttu-id="81e56-225">每次啟動至 UEFI 時，您都需要這個密碼。</span><span class="sxs-lookup"><span data-stu-id="81e56-225">You'll need this password whenever you boot to the UEFI.</span></span> *<span data-ttu-id="81e56-226">我們強烈建議您設定 UEFI 密碼，以在 2S Surface Hub使用。</span><span class="sxs-lookup"><span data-stu-id="81e56-226">We strongly recommend that you set a UEFI password that you'll use on Surface Hub 2S.</span></span>*

   ![螢幕擷取畫面顯示選取密碼保護位置。](images/shm-fig8.png)
   
1. <span data-ttu-id="81e56-228">設定 UEFI 密碼， **然後選取**確定 。</span><span class="sxs-lookup"><span data-stu-id="81e56-228">Set a UEFI password, and then select **OK**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="81e56-229">將密碼儲存到可管理密碼的 IT 系統管理員易於Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="81e56-229">Save the password in a secure location that's accessible to your IT admins who manage Surface Hub.</span></span> *<span data-ttu-id="81e56-230">如果密碼遺失，無法復原。</span><span class="sxs-lookup"><span data-stu-id="81e56-230">If this password is lost, it can't be recovered.</span></span>*

   ![螢幕擷取畫面顯示您設定 UEFI 密碼的地方。](images/shm-fig9.png)

1. <span data-ttu-id="81e56-232">選取**Surface Hub 2S，** 然後選取 下**一步**。</span><span class="sxs-lookup"><span data-stu-id="81e56-232">Select **Surface Hub 2S**, and then select **Next**.</span></span>

    ![螢幕擷取畫面顯示選取 2S Surface Hub位置。](images/shm-fig10.png)
   
1. <span data-ttu-id="81e56-234">再次 **選取下一** 步。</span><span class="sxs-lookup"><span data-stu-id="81e56-234">Select **Next** again.</span></span>

    ![螢幕擷取畫面顯示以選取 「選擇哪些元件」下的下一步。](images/shm-fig10a.png)

1. <span data-ttu-id="81e56-236">若要允許安裝Windows 10 專業版或Enterprise，請開啟**EnableOsMigration，** 然後選取下**一步**。</span><span class="sxs-lookup"><span data-stu-id="81e56-236">To allow installation of Windows 10 Pro or Enterprise, turn on **EnableOsMigration**, and then select **Next**.</span></span>

    ![螢幕擷取畫面顯示在何處選取啟用 O S 移移。](images/shm-fig11.png)
    
    ![螢幕擷取畫面顯示將啟用作業系統移移設定至何處。](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a><span data-ttu-id="81e56-239">管理 SEMM 註冊</span><span class="sxs-lookup"><span data-stu-id="81e56-239">Manage SEMM enrollment</span></span>

<span data-ttu-id="81e56-240">將裝置註冊到 SEMM 會影響您的管理方式。</span><span class="sxs-lookup"><span data-stu-id="81e56-240">Enrolling a device into SEMM affects how you can manage it.</span></span> <span data-ttu-id="81e56-241">例如，套用 SEMM 套件之後，所有 UEFI 設定 (UEFI) UEFI 功能表中鎖定的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="81e56-241">For example, after you apply a SEMM package, all UEFI settings are unavailable (locked) in the device's UEFI menu.</span></span> <span data-ttu-id="81e56-242">其他設定 ，例如 **IPv6 for PXE Boot 的** 預設值也無法使用。</span><span class="sxs-lookup"><span data-stu-id="81e56-242">Default values for other settings such as **IPv6 for PXE Boot** are also unavailable.</span></span>

<span data-ttu-id="81e56-243">若要在移移完成後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="81e56-243">To change UEFI settings after you finish the migration, apply another SEMM package or unenroll the device from SEMM.</span></span> <span data-ttu-id="81e56-244">如果您套用另一個 SEMM 套件來變更 UEFI 設定，則當您建立新的 SEMM 套件時，必須使用原始憑證。</span><span class="sxs-lookup"><span data-stu-id="81e56-244">If you apply another SEMM package to change the UEFI settings, you must use the original certificate when you build the new SEMM package.</span></span> <span data-ttu-id="81e56-245">使用 UEFI Configurator 工具，將**EnableOSMigration\*\*\*\* 關閉 (** 如原始移) 。</span><span class="sxs-lookup"><span data-stu-id="81e56-245">Use the UEFI Configurator tool and leave **EnableOSMigration** *off* (not *on* as in the original migration steps).</span></span>

#### <a name="if-you-work-with-partners"></a><span data-ttu-id="81e56-246">如果您與合作夥伴合作</span><span class="sxs-lookup"><span data-stu-id="81e56-246">If you work with partners</span></span>

<span data-ttu-id="81e56-247">如果您的公司將 Surface Hub 2 移轉到 Windows 10 專業版 或 Enterprise，您可能會想要讓合作夥伴將 SEMM 憑證、SEMM 套件和 UEFI 密碼傳輸至您。</span><span class="sxs-lookup"><span data-stu-id="81e56-247">If your company outsources the Surface Hub 2 migration to Windows 10 Pro or Enterprise, you may want to have the partner transfer the SEMM certificate, SEMM package, and UEFI password to you.</span></span> <span data-ttu-id="81e56-248">或者，在遷移中樞之後，您可以立即從 SEMM 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="81e56-248">Or, after you migrate the Hub, you can immediately unenroll it from SEMM.</span></span> <span data-ttu-id="81e56-249">此步驟可讓 UEFI 的本地管理，以及將裝置移轉給另一方。</span><span class="sxs-lookup"><span data-stu-id="81e56-249">This step enables local administration of UEFI and transfer of the device to another party.</span></span> <span data-ttu-id="81e56-250">但我們仍強烈建議您使用 UEFI 密碼，此密碼可在移移之後進行配置。</span><span class="sxs-lookup"><span data-stu-id="81e56-250">But we still strongly recommend that you use a UEFI password, which can be configured after migration.</span></span> <span data-ttu-id="81e56-251">若要深入瞭解，請參閱 [管理 Surface UEFI 設定](https://docs.microsoft.com/surface/manage-surface-uefi-settings)。</span><span class="sxs-lookup"><span data-stu-id="81e56-251">To learn more, see [Manage Surface UEFI settings](https://docs.microsoft.com/surface/manage-surface-uefi-settings).</span></span> 

#### <a name="to-roll-back-to-windows-10-team"></a><span data-ttu-id="81e56-252">若要返回Windows 10 團隊版</span><span class="sxs-lookup"><span data-stu-id="81e56-252">To roll back to Windows 10 Team</span></span>

<span data-ttu-id="81e56-253">如果您選擇將裝置還原為Windows 10 團隊版如本文稍後所述，建議您先從[](#to-roll-back-to-windows-10-team)SEMM 取消註冊 Hub。</span><span class="sxs-lookup"><span data-stu-id="81e56-253">If you choose to restore your device to Windows 10 Team after the migration [as described later in this article](#to-roll-back-to-windows-10-team), we recommend that you first unenroll Hub from SEMM.</span></span> <span data-ttu-id="81e56-254">若要深入瞭解，請參閱從 [SEMM 取消](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="81e56-254">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

#### <a name="save-the-semm-package-to-a-usb-drive"></a><span data-ttu-id="81e56-255">將 SEMM 套件儲存到 USB 磁碟機</span><span class="sxs-lookup"><span data-stu-id="81e56-255">Save the SEMM package to a USB drive</span></span>

1. <span data-ttu-id="81e56-256">連線 USB 磁碟機到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="81e56-256">Connect a USB drive to your PC.</span></span>
1. <span data-ttu-id="81e56-257">選擇 **中心 2S，** 然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="81e56-257">Choose **Hub 2S**, and then select **Next**.</span></span>

   ![螢幕擷取畫面顯示選取中心 2S 位置](images/shm-fig13.png)

   > [!WARNING]
   > <span data-ttu-id="81e56-259">建立 SEMM 套件時，USB 磁碟機上的所有現有資料都會清除。</span><span class="sxs-lookup"><span data-stu-id="81e56-259">All existing data on the USB drive will be erased when the SEMM package is built.</span></span> <span data-ttu-id="81e56-260">在建立 SEMM 套件之前，請從 USB 磁碟機移除任何您需要的檔案。</span><span class="sxs-lookup"><span data-stu-id="81e56-260">Before you build the SEMM package, remove any files that you need from the USB drive.</span></span>
   
1. <span data-ttu-id="81e56-261">選取 **建立**。</span><span class="sxs-lookup"><span data-stu-id="81e56-261">Select **Build**.</span></span>

   ![螢幕擷取畫面顯示選取建立位置。](images/shm-fig14.png)

1. <span data-ttu-id="81e56-263">捕獲此頁面的螢幕擷取畫面， **然後選取**結束 。</span><span class="sxs-lookup"><span data-stu-id="81e56-263">Capture a screenshot of this page, and then select **End**.</span></span> <span data-ttu-id="81e56-264">您的 SEMM 套件現在已準備就緒。</span><span class="sxs-lookup"><span data-stu-id="81e56-264">Your SEMM package is now ready.</span></span> <span data-ttu-id="81e56-265">它包含 SEMM 套件 *DfciUpdate.dfi，* 以及包含 *SEMM*指紋的文字檔 ，這是憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="81e56-265">It contains the SEMM package *DfciUpdate.dfi* and a text file that includes the SEMM *thumbprint*, which is the last two characters of the certificate's thumbprint.</span></span>

   ![螢幕擷取畫面顯示選取結束位置。](images/shm-fig15.png)
   
4. <span data-ttu-id="81e56-267">儲存憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="81e56-267">Save the certificate thumbprint's last two characters.</span></span> <span data-ttu-id="81e56-268">當您在 2S 上套用套件時，您需要這些字元Surface Hub SEMM。</span><span class="sxs-lookup"><span data-stu-id="81e56-268">You'll need these characters to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a><span data-ttu-id="81e56-269">載入 USB 快閃磁碟機Windows 10影像、SEMM 套件，Surface Hub 2 個驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="81e56-269">Load a USB flash drive with a Windows 10 image, SEMM package, and Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="81e56-270">您可以使用下列Windows 10 專業版Enterprise， (*版本 1903*或) 安裝影像：</span><span class="sxs-lookup"><span data-stu-id="81e56-270">You can install a Windows 10 Pro or Enterprise image (version *1903* or later) by using one of the following options:</span></span>

- <span data-ttu-id="81e56-271">您目前的影像解決方案。</span><span class="sxs-lookup"><span data-stu-id="81e56-271">Your current imaging solution.</span></span>

- <span data-ttu-id="81e56-272">[Surface 部署快速鍵](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator)。</span><span class="sxs-lookup"><span data-stu-id="81e56-272">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator).</span></span> <span data-ttu-id="81e56-273">使用此工具建立可啟動Windows 10圖像。</span><span class="sxs-lookup"><span data-stu-id="81e56-273">Use this tool to create a bootable Windows 10 image.</span></span> <span data-ttu-id="81e56-274">影像可以包含所有目前更新Windows 10、Microsoft Office應用程式，以及所需的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="81e56-274">The image can include all current Windows 10 updates, Microsoft Office, other apps, and the required drivers and firmware.</span></span>

- <span data-ttu-id="81e56-275">包含影像或影像Windows 10 專業版或Enterprise快Enterprise磁碟機。</span><span class="sxs-lookup"><span data-stu-id="81e56-275">A USB flash drive that contains a Windows 10 Pro or Enterprise image.</span></span> <span data-ttu-id="81e56-276">然後在 2 日安裝 Windows 10 專業版[Enterprise](https://www.microsoft.com/download/details.aspx?id=101974)驅動程式Surface Hub的Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="81e56-276">Then install [drivers and firmware for Windows 10 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974) on Surface Hub 2.</span></span>
 
<span data-ttu-id="81e56-277">下列步驟顯示如何從安裝媒體建立 USB 快閃磁碟機，然後在 2 MSI 檔案上新增 Windows 10 專業版 和 Enterprise OS 的 SEMM 套件檔案Surface Hub驅動程式和Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="81e56-277">The following steps show how to create a USB flash drive from installation media and then add the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 MSI file.</span></span> <span data-ttu-id="81e56-278">如果您使用其他部署方法，請前往[2S Surface Hub更新 UEFI 以啟用本文](#update-uefi-on-surface-hub-2s-to-enable-os-migration)的 OS 移轉到一節。</span><span class="sxs-lookup"><span data-stu-id="81e56-278">If you use another deployment method, go to the [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="81e56-279">安裝完成後，您需要現有授權Windows 10 專業版或Windows 10 企業版授權Windows 10 團隊版授權。</span><span class="sxs-lookup"><span data-stu-id="81e56-279">After you finish the installation, you'll need a valid license for Windows 10 Pro or Windows 10 Enterprise that's separate from your existing Windows 10 Team license.</span></span>

1. <span data-ttu-id="81e56-280">若要建立Windows 10 專業版，請按照指示下載媒體建立工具[，Windows 10。](https://www.microsoft.com/software-download/windows10)</span><span class="sxs-lookup"><span data-stu-id="81e56-280">To create a Windows 10 Pro installation, follow the instructions to download the media creation tool at [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span> <span data-ttu-id="81e56-281">若要下載Windows 10 企業版，請前往[Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="81e56-281">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

1. <span data-ttu-id="81e56-282">插入新的 USB 儲存檔。</span><span class="sxs-lookup"><span data-stu-id="81e56-282">Insert a new USB storage drive.</span></span>
1. <span data-ttu-id="81e56-283">開啟媒體建立工具，選取 **建立安裝媒體**，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="81e56-283">Open the media creation tool, select **Create installation media**, and then select **Next**.</span></span>

   ![螢幕擷取畫面顯示建立安裝媒體的選項。](images/shm-fig16.png)
   
3. <span data-ttu-id="81e56-285">選取語言，**然後選取**Windows 10 x64 (**64 位) 。**</span><span class="sxs-lookup"><span data-stu-id="81e56-285">Select a language, and then select **Windows 10** and **64-bit (x64)**.</span></span> <span data-ttu-id="81e56-286">然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="81e56-286">Then select **Next**.</span></span>

   ![螢幕擷取畫面顯示您選取語言、O S 版本和架構類型的地方。](images/shm-fig17.png)
   
4. <span data-ttu-id="81e56-288">選取 **USB 快閃磁碟機**，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="81e56-288">Select **USB flash drive**, and then select **Next**.</span></span>

   ![螢幕擷取畫面顯示在何處選取 US B 快閃磁碟機。](images/shm-fig18.png)
   
5. <span data-ttu-id="81e56-290">下載完成後，選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="81e56-290">When the download finishes, select **Finish**.</span></span>

   ![畫面報告美國硬碟已準備就緒，並包含完成按鈕。](images/shm-fig19.png)
   
6. <span data-ttu-id="81e56-292">將 MSI 檔案) Surface Hub (2 Surface Hub 上的 Windows 10 專業版 和 Enterprise OS 的 SEMM 套件檔案和驅動程式和固件複製到包含 Windows 10 影像的 USB 快閃磁碟機 (*BOOTME*) 根目錄。</span><span class="sxs-lookup"><span data-stu-id="81e56-292">Copy the SEMM package files and the drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (the MSI file) to the root of the USB flash drive (*BOOTME*) that contains your Windows 10 image.</span></span> <span data-ttu-id="81e56-293">BOOTME USB 磁碟機會包含：</span><span class="sxs-lookup"><span data-stu-id="81e56-293">The BOOTME USB drive will contain:</span></span>

    - <span data-ttu-id="81e56-294">您的Windows 10可啟動的影像。</span><span class="sxs-lookup"><span data-stu-id="81e56-294">Your Windows 10 bootable image.</span></span>
    
    - <span data-ttu-id="81e56-295">複製至 USB 磁碟機根目錄的 SEMM 套件檔案：</span><span class="sxs-lookup"><span data-stu-id="81e56-295">The SEMM package files, copied to the root of the USB drive:</span></span>
    
      - <span data-ttu-id="81e56-296">*DfciUpdate.dfi*。</span><span class="sxs-lookup"><span data-stu-id="81e56-296">*DfciUpdate.dfi*.</span></span>
      - <span data-ttu-id="81e56-297">包含 SEMM 指紋的文字檔。</span><span class="sxs-lookup"><span data-stu-id="81e56-297">A text file that includes the SEMM thumbprint.</span></span> <span data-ttu-id="81e56-298"> (在此範例中，檔案是 *SurfaceUEFI_2020Aug25_1058.txt*.) 自動產生的日期時間戳記會對應到您使用 Surface UEFI Configurator 建立檔案的日期。</span><span class="sxs-lookup"><span data-stu-id="81e56-298">(In this example, the file is *SurfaceUEFI_2020Aug25_1058.txt*.) The automatically generated date-time stamp corresponds to the date that you created the file by using Surface UEFI Configurator.</span></span>

   - <span data-ttu-id="81e56-299">適用于 2 Windows 10 專業版 2 Enterprise 作業系統的驅動程式Surface Hub (SurfaceHub2S_Win10_18362_20.082.25682.0.msi) 。</span><span class="sxs-lookup"><span data-stu-id="81e56-299">The drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi).</span></span> <span data-ttu-id="81e56-300">將這個檔案複製到 USB 磁碟機的根目錄。</span><span class="sxs-lookup"><span data-stu-id="81e56-300">Copy this file to the root of the USB drive.</span></span>

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a><span data-ttu-id="81e56-301">更新 2S Surface Hub UEFI 以啟用作業系統移移</span><span class="sxs-lookup"><span data-stu-id="81e56-301">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="81e56-302">將 BOOTME 磁碟機插入 2S Surface Hub USB-A 埠。</span><span class="sxs-lookup"><span data-stu-id="81e56-302">Insert your BOOTME drive into the USB-A port on the Surface Hub 2S.</span></span> <span data-ttu-id="81e56-303">有關所需內容的清單，請參閱上一節。</span><span class="sxs-lookup"><span data-stu-id="81e56-303">For a list of its required contents, see the previous section.</span></span>

1. <span data-ttu-id="81e56-304">若要啟動至 UEFI：</span><span class="sxs-lookup"><span data-stu-id="81e56-304">To boot into UEFI:</span></span>

   1. <span data-ttu-id="81e56-305">關閉您的 (2S) 關閉Surface Hub關閉。</span><span class="sxs-lookup"><span data-stu-id="81e56-305">Turn off (shut down) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="81e56-306">按住 Volume **+**，然後按並放開電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="81e56-306">Press and hold **Volume +**, and then press and release the power button.</span></span> <span data-ttu-id="81e56-307">持續按住 **音量 +** 直到 UEFI 功能表出現。</span><span class="sxs-lookup"><span data-stu-id="81e56-307">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![繪圖會顯示音量和電源按鈕。](images/shm-fig20.png)
      
3. <span data-ttu-id="81e56-309">當裝置重新開機時，輸入您先前所建立之 UEFI 密碼 ，如果適用， (建議) 。</span><span class="sxs-lookup"><span data-stu-id="81e56-309">When the device restarts, enter the UEFI password that you created earlier, if applicable (recommended).</span></span>

   ![系統密碼畫面。](images/shm-fig22.png)
   
4. <span data-ttu-id="81e56-311">從 UEFI 功能表中， **選取**管理 。</span><span class="sxs-lookup"><span data-stu-id="81e56-311">From the UEFI menu, select **Management**.</span></span> <span data-ttu-id="81e56-312">然後選取  **從 USB 安裝**。</span><span class="sxs-lookup"><span data-stu-id="81e56-312">Then select  **Install from USB**.</span></span>

   ![螢幕擷取畫面顯示在何處選取管理，然後選取「從美國 B 安裝」。](images/shm-fig21.png)
   
5. <span data-ttu-id="81e56-314">選取 **立即重新開機**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="81e56-314">Select **Restart now**, as the following image shows.</span></span> <span data-ttu-id="81e56-315">裝置會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="81e56-315">The device will restart.</span></span> <span data-ttu-id="81e56-316">它會在視窗中央顯示白色 Microsoft 標誌，然後關閉。</span><span class="sxs-lookup"><span data-stu-id="81e56-316">It will display a white Microsoft logo in the middle of the window and then shut down.</span></span>

   ![螢幕擷取畫面顯示一則訊息，提示您重新開機。](images/shm-fig25.png)
   
6. <span data-ttu-id="81e56-318">按並放開電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="81e56-318">Press and release the power button.</span></span> <span data-ttu-id="81e56-319">在出現的紅色對話方塊中，選擇啟用 Surface Enterprise管理模式。</span><span class="sxs-lookup"><span data-stu-id="81e56-319">In the red dialog box that appears, choose to activate Surface Enterprise Management Mode.</span></span>

7. <span data-ttu-id="81e56-320">輸入雙字元憑證指紋和 UEFI 設定密碼。</span><span class="sxs-lookup"><span data-stu-id="81e56-320">Enter your two-character certificate thumbprint and your UEFI settings password.</span></span> <span data-ttu-id="81e56-321">然後選取 **確定**。</span><span class="sxs-lookup"><span data-stu-id="81e56-321">Then select **OK**.</span></span>

   ![螢幕擷取畫面顯示確認啟用對話方塊，您可以在此輸入雙字元憑證指紋和 UEFI 設定密碼。](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="81e56-323">在裝置上啟用 SEMM 之後，會採用新的 UEFI 設定**EnableOSMigration。**</span><span class="sxs-lookup"><span data-stu-id="81e56-323">After you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="81e56-324">您無法再存取Windows 10 團隊版。</span><span class="sxs-lookup"><span data-stu-id="81e56-324">You can no longer access Windows 10 Team.</span></span> <span data-ttu-id="81e56-325">您必須繼續下一個步驟，並安裝 Windows 10 專業版 或 Windows 10 企業版。</span><span class="sxs-lookup"><span data-stu-id="81e56-325">Instead, you must continue to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span>

   <span data-ttu-id="81e56-326">裝置會重新開機。</span><span class="sxs-lookup"><span data-stu-id="81e56-326">The device reboots.</span></span> <span data-ttu-id="81e56-327">它會在畫面中央顯示白色標誌，然後再次關閉。</span><span class="sxs-lookup"><span data-stu-id="81e56-327">It displays the white logo in the middle of the screen and then shuts down again.</span></span>

### <a name="install-windows-10-pro-or-enterprise"></a><span data-ttu-id="81e56-328">安裝Windows 10 專業版或Enterprise</span><span class="sxs-lookup"><span data-stu-id="81e56-328">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="81e56-329">如果您的可啟動Windows 10 專業版或Enterprise磁碟機尚未在 2 USB-A 埠Surface Hub，請現在插入。</span><span class="sxs-lookup"><span data-stu-id="81e56-329">If your bootable Windows 10 Pro or Enterprise drive isn't already in the Surface Hub 2 USB-A port, insert it now.</span></span> <span data-ttu-id="81e56-330">然後按並放開電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="81e56-330">Then press and release the power button.</span></span>

    <span data-ttu-id="81e56-331">當裝置啟動時，畫面中央就會看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="81e56-331">When the device starts, you'll see the white logo in the middle of the screen.</span></span> <span data-ttu-id="81e56-332">接著，白色標誌下方會出現旋轉的圓圈。</span><span class="sxs-lookup"><span data-stu-id="81e56-332">Then a spinning circle appears below the white logo.</span></span>

3. <span data-ttu-id="81e56-333">如果 Surface 裝置無法自動啟動至 USB 磁碟機，請關閉裝置電源 (拔下電源線，然後將它插回) 。</span><span class="sxs-lookup"><span data-stu-id="81e56-333">If the Surface device doesn't automatically boot to the USB drive, power off the device (unplug the power cord and then plug it back in).</span></span> <span data-ttu-id="81e56-334">再次插入電源線後，裝置應該幾秒鐘後應該會啟動。</span><span class="sxs-lookup"><span data-stu-id="81e56-334">After you plug in the power cord again, the device should boot after a few seconds.</span></span> <span data-ttu-id="81e56-335">接著，畫面中央就會看到白色標誌。</span><span class="sxs-lookup"><span data-stu-id="81e56-335">Then you'll see the white logo in the middle of screen.</span></span>

    <span data-ttu-id="81e56-336">如果裝置未開啟，請按並放開電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="81e56-336">If the device doesn't turn on, press and release the power button.</span></span> <span data-ttu-id="81e56-337">在畫面中間看到標誌之後，請按住向下捲動按鈕，直到您看到白色標誌下方的旋轉圓圈。</span><span class="sxs-lookup"><span data-stu-id="81e56-337">Immediately after you see the logo in the middle of the screen, press and hold the Volume down button until you see the spinning circle below the white logo.</span></span>
 
   ![音量和電源按鈕的圖片。](images/shm-fig26.png)
   
4. <span data-ttu-id="81e56-339">當 OOBE (OOBE) 開始時，請按照指示安裝 Windows 10 專業版 或 Enterprise (版本 1903 或更新版本) 。</span><span class="sxs-lookup"><span data-stu-id="81e56-339">When the out-of-box experience (OOBE) setup starts, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <a name="install-surface-hub-2-drivers-and-firmware"></a><span data-ttu-id="81e56-340">安裝 Surface Hub 2 個驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="81e56-340">Install Surface Hub 2 drivers and firmware</span></span>

<span data-ttu-id="81e56-341">若要確保您的 Surface Hub 2 為最新版本，請安裝適用于 Windows 10 專業版 和 Enterprise[的驅動程式和Enterprise。](https://www.microsoft.com/download/details.aspx?id=101974)</span><span class="sxs-lookup"><span data-stu-id="81e56-341">To ensure that your Surface Hub 2 is up to date, install [drivers and firmware for Windows 10 Pro and Enterprise](https://www.microsoft.com/download/details.aspx?id=101974).</span></span> <span data-ttu-id="81e56-342">然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="81e56-342">Then reboot the device.</span></span> <span data-ttu-id="81e56-343">將 Surface 保持開啟一小時，然後再重新開機一次。</span><span class="sxs-lookup"><span data-stu-id="81e56-343">Keep the Surface turned on for an hour, and then reboot it again.</span></span> <span data-ttu-id="81e56-344">系統不會提示您進行第二次重新開機。</span><span class="sxs-lookup"><span data-stu-id="81e56-344">You won't be prompted for the second reboot.</span></span> <span data-ttu-id="81e56-345">此暫停和額外重新開機可確保完整更新的固件。</span><span class="sxs-lookup"><span data-stu-id="81e56-345">This pause and extra reboot ensures that the firmware has been fully updated.</span></span>
 
## <a name="configure-recommended-settings"></a><span data-ttu-id="81e56-346">設定建議設定</span><span class="sxs-lookup"><span data-stu-id="81e56-346">Configure recommended settings</span></span>

<span data-ttu-id="81e56-347">若要將 Surface Hub 2S 設定為個人生產力裝置，請參閱在 Windows 10 專業版[2](surface-hub-2-post-install.md)Enterprise 設定 Surface Hub 裝置。</span><span class="sxs-lookup"><span data-stu-id="81e56-347">To configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="81e56-348">如果您無法按照本文所述步驟Windows 10 專業版或 Enterprise 2 Surface Hub成功將裝置遷移到 Surface Hub 或 Enterprise，請聯絡[客戶支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。</span><span class="sxs-lookup"><span data-stu-id="81e56-348">If you can't successfully migrate your device to Windows 10 Pro or Enterprise for Surface Hub 2 by following the steps outlined in this article, contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <a name="to-roll-back-to-windows-10-team"></a><span data-ttu-id="81e56-349">若要返回Windows 10 團隊版</span><span class="sxs-lookup"><span data-stu-id="81e56-349">To roll back to Windows 10 Team</span></span>

<span data-ttu-id="81e56-350">如果您想要將裝置還原為 Windows 10 團隊版，請參閱重設及復原[Surface Hub 2S](surface-hub-2s-recover-reset.md)。</span><span class="sxs-lookup"><span data-stu-id="81e56-350">If you want to restore your device to Windows 10 Team, see [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md).</span></span>

> [!NOTE]
> <span data-ttu-id="81e56-351">在您卷回 Windows 10 團隊版之前，建議您先從 SEMM 取消Surface Hub卷Surface Hub卷起。</span><span class="sxs-lookup"><span data-stu-id="81e56-351">Before you roll back to Windows 10 Team, we recommended that you first unenroll the Surface Hub from SEMM.</span></span> <span data-ttu-id="81e56-352">若要深入瞭解，請參閱 [從 SEMM 取消](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="81e56-352">To learn more, see [Unenroll Surface devices from SEMM](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm).</span></span>

## <a name="version-history"></a><span data-ttu-id="81e56-353">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="81e56-353">Version history</span></span>

<span data-ttu-id="81e56-354">下表摘要列出本文的變更。</span><span class="sxs-lookup"><span data-stu-id="81e56-354">The following table summarizes changes to this article.</span></span>

| <span data-ttu-id="81e56-355">版本</span><span class="sxs-lookup"><span data-stu-id="81e56-355">Version</span></span> | <span data-ttu-id="81e56-356">日期</span><span class="sxs-lookup"><span data-stu-id="81e56-356">Date</span></span>               | <span data-ttu-id="81e56-357">說明</span><span class="sxs-lookup"><span data-stu-id="81e56-357">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="81e56-358">五。</span><span class="sxs-lookup"><span data-stu-id="81e56-358">v.</span></span> <span data-ttu-id="81e56-359">1.4</span><span class="sxs-lookup"><span data-stu-id="81e56-359">1.4</span></span>  | <span data-ttu-id="81e56-360">2020 年 12 月 14 日</span><span class="sxs-lookup"><span data-stu-id="81e56-360">December 14, 2020</span></span> | <span data-ttu-id="81e56-361">提供有關[在](#install-surface-hub-2-drivers-and-firmware)Surface Hub 2 上安裝 Windows 10 專業版 和 Enterprise OS 的驅動程式和固件的 MSI 檔案的進一步資訊，建議視系統狀態而可能需要第二次重新開機。</span><span class="sxs-lookup"><span data-stu-id="81e56-361">Provides [further info](#install-surface-hub-2-drivers-and-firmware) about installing the MSI file for "Drivers and firmware for Windows 10 Pro and Enterprise OS on Surface Hub 2," advising that a second reboot may be necessary depending on the state of your system.</span></span>                                                          |
| <span data-ttu-id="81e56-362">五。</span><span class="sxs-lookup"><span data-stu-id="81e56-362">v.</span></span> <span data-ttu-id="81e56-363">1.3</span><span class="sxs-lookup"><span data-stu-id="81e56-363">1.3</span></span>  | <span data-ttu-id="81e56-364">2020 年 12 月 3 日</span><span class="sxs-lookup"><span data-stu-id="81e56-364">December 3, 2020</span></span> | <span data-ttu-id="81e56-365">更新為管理 [SEMM 註冊的指南](#manage-semm-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="81e56-365">Updated with guidance about [managing SEMM enrollment](#manage-semm-enrollment).</span></span>                                                       |
| <span data-ttu-id="81e56-366">五。</span><span class="sxs-lookup"><span data-stu-id="81e56-366">v.</span></span> <span data-ttu-id="81e56-367">1.2</span><span class="sxs-lookup"><span data-stu-id="81e56-367">1.2</span></span>  | <span data-ttu-id="81e56-368">2020 年 9 月 29 日</span><span class="sxs-lookup"><span data-stu-id="81e56-368">September 29, 2020</span></span> | <span data-ttu-id="81e56-369">解決可用性意見回饋的雜項更新。</span><span class="sxs-lookup"><span data-stu-id="81e56-369">Miscellaneous updates that address usability feedback.</span></span>                                                        |
| <span data-ttu-id="81e56-370">五。</span><span class="sxs-lookup"><span data-stu-id="81e56-370">v.</span></span> <span data-ttu-id="81e56-371">1.1</span><span class="sxs-lookup"><span data-stu-id="81e56-371">1.1</span></span>  | <span data-ttu-id="81e56-372">2020 年 9 月 15 日</span><span class="sxs-lookup"><span data-stu-id="81e56-372">September 15, 2020</span></span> | <span data-ttu-id="81e56-373">在簡介中新增一個說明，說明安裝新作業系統的授權需求。</span><span class="sxs-lookup"><span data-stu-id="81e56-373">Placed an additional note in the introduction that clarifies licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="81e56-374">五。</span><span class="sxs-lookup"><span data-stu-id="81e56-374">v.</span></span> <span data-ttu-id="81e56-375">1.0</span><span class="sxs-lookup"><span data-stu-id="81e56-375">1.0</span></span>  | <span data-ttu-id="81e56-376">2020 年 9 月 1 日</span><span class="sxs-lookup"><span data-stu-id="81e56-376">September 1, 2020</span></span>  | <span data-ttu-id="81e56-377">新文章。</span><span class="sxs-lookup"><span data-stu-id="81e56-377">New article.</span></span>                                                                                           |
