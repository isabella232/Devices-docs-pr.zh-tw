---
title: 移轉到 Windows 10 專業版或 Surface Hub 2 企業版
description: 本文將說明從 Surface Hub 2 上的 Windows 10 小組遷移到 Windows 10 專業版或 Windows 10 企業版的程式。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/11/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 44e7ca08ca4b8c077d430cba2a8cb4b674b68631
ms.sourcegitcommit: ae0dae16e0b7bb9c906de78095634c3070a58c61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/11/2020
ms.locfileid: "11013433"
---
# <span data-ttu-id="dc9e8-104">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="dc9e8-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

## <span data-ttu-id="dc9e8-105">簡介</span><span class="sxs-lookup"><span data-stu-id="dc9e8-105">Introduction</span></span>

<span data-ttu-id="dc9e8-106">Surface Hub 秒數是由 Windows 10 小組預先安裝的，這是 Windows 10 的自訂版本，可協助在會議室環境中輕鬆共同作業。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-106">Surface Hub 2S comes pre-installed with Windows 10 Team, a customized edition of Windows 10 designed to facilitate easy collaboration in meeting room environments.</span></span> <span data-ttu-id="dc9e8-107">現在，您可以選擇執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="dc9e8-108">與典型的升級或遷移不同，此程式必須遵循說明性程式，如本頁面所述。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described on this page.</span></span> <span data-ttu-id="dc9e8-109">在繼續之前，請先查看 [解決方案元件](#solution-components) 與 [遷移及安裝工作流程](#migration-and-installation-workflow-summary) 。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before proceeding.</span></span>

<span data-ttu-id="dc9e8-110">您可以從 Windows 10 小組開始遷移，使用不同的電腦和可下載的工具- **SURFACE UEFI 配置** 器，建立包含您套用至 Surface Hub 2 秒的新 UEFI 設定的套件。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-110">You start the migration from Windows 10 Team using a separate PC and downloadable tool -- **Surface UEFI Configurator** --  to create a package containing a new UEFI setting that you apply to Surface Hub 2S.</span></span>  <span data-ttu-id="dc9e8-111">Surface UEFI 配置處理常式會將介面轉換成 Surface Enterprise 管理模式 (SEMM) ，旨在協助集中管理公司環境中的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-111">Surface UEFI Configurator functions as an interface into Surface Enterprise Management Mode (SEMM), designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="dc9e8-112">若要深入瞭解 SEMM，請參閱 [Microsoft Surface Enterprise 管理模式檔](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-112">To learn more about SEMM, see [Microsoft Surface Enterprise Management Mode documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="dc9e8-113">解決方案元件</span><span class="sxs-lookup"><span data-stu-id="dc9e8-113">Solution Components</span></span>

- <span data-ttu-id="dc9e8-114">執行 Windows 10 小組作業系統的 Surface Hub 2 秒裝置</span><span class="sxs-lookup"><span data-stu-id="dc9e8-114">Surface Hub 2S device running Windows 10 Team operating system</span></span>
- <span data-ttu-id="dc9e8-115">運行 Windows 10 的個別裝置</span><span class="sxs-lookup"><span data-stu-id="dc9e8-115">Separate device running Windows 10</span></span>
- <span data-ttu-id="dc9e8-116">Surface UEFI 組態工具</span><span class="sxs-lookup"><span data-stu-id="dc9e8-116">Surface UEFI Configurator tool</span></span>
- <span data-ttu-id="dc9e8-117">Windows 10 專業版或企業版作業系統影像、版本1903或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc9e8-117">Windows 10 Pro or Enterprise OS image, version 1903 or greater</span></span>
- <span data-ttu-id="dc9e8-118">含儲存空間、FAT32 格式的兩個 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="dc9e8-118">Two USB drives with 16GB of storage, FAT32 format</span></span>
- <span data-ttu-id="dc9e8-119">Windows 10 專業版的驅動程式和固件，以及 Surface Hub 2、Windows 安裝程式。MSI 檔案</span><span class="sxs-lookup"><span data-stu-id="dc9e8-119">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2, Windows Installer .MSI file</span></span>
- <span data-ttu-id="dc9e8-120">網際網路連線</span><span class="sxs-lookup"><span data-stu-id="dc9e8-120">Internet connection</span></span>
- <span data-ttu-id="dc9e8-121">影像處理方案 (選用) </span><span class="sxs-lookup"><span data-stu-id="dc9e8-121">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="dc9e8-122">遷移和安裝工作流程摘要</span><span class="sxs-lookup"><span data-stu-id="dc9e8-122">Migration and installation workflow summary</span></span>

| <span data-ttu-id="dc9e8-123">步驟</span><span class="sxs-lookup"><span data-stu-id="dc9e8-123">Step</span></span>  | <span data-ttu-id="dc9e8-124">動作</span><span class="sxs-lookup"><span data-stu-id="dc9e8-124">Action</span></span>                                                                                                 | <span data-ttu-id="dc9e8-125">摘要</span><span class="sxs-lookup"><span data-stu-id="dc9e8-125">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="dc9e8-126">sr-1</span><span class="sxs-lookup"><span data-stu-id="dc9e8-126">1</span></span> | [<span data-ttu-id="dc9e8-127">驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求</span><span class="sxs-lookup"><span data-stu-id="dc9e8-127">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="dc9e8-128">確定 UEFI 版本為694.2938.768.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-128">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="dc9e8-129">pplx-2</span><span class="sxs-lookup"><span data-stu-id="dc9e8-129">2</span></span> | [<span data-ttu-id="dc9e8-130">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="dc9e8-130">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="dc9e8-131">從表面工具下載 [SURFACE UEFI 配置](https://www.microsoft.com/download/details.aspx?id=46703) 器，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-131">Download [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT and install it on a separate PC.</span></span> <span data-ttu-id="dc9e8-132">[在 Surface Hub 2 上下載適用于 Windows 10 專業版與企業版的驅動程式及固件。MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案並將其儲存，以便在步驟5中使用。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-132">Download [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) and save it for use in Step 5.</span></span> |
| <span data-ttu-id="dc9e8-133">3</span><span class="sxs-lookup"><span data-stu-id="dc9e8-133">3</span></span> | [<span data-ttu-id="dc9e8-134">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="dc9e8-134">Prepare SEMM certificate</span></span>](#prepare-semm-certificate)                                                                          | <span data-ttu-id="dc9e8-135">準備運行 Surface UEFI 配置器所需的憑證，或使用您目前的憑證。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-135">Prepare required certificate for running Surface UEFI Configurator or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="dc9e8-136">4</span><span class="sxs-lookup"><span data-stu-id="dc9e8-136">4</span></span> | [<span data-ttu-id="dc9e8-137">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="dc9e8-137">Create SEMM package</span></span>](#create-semm-package)                                                                               | <span data-ttu-id="dc9e8-138">啟動 Surface UEFI 設定檔，以在 USB 磁片磁碟機上建立 SEMM 套件，這將包含要套用到 Surface Hub 2 的必要配置檔案。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-138">Launch Surface UEFI Configurator to create a SEMM package on a USB drive which will contain the required configuration files to apply on Surface Hub 2S.</span></span> <span data-ttu-id="dc9e8-139">將這些 SEMM 套件檔案複製到您電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-139">Copy these SEMM package  files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="dc9e8-140">500</span><span class="sxs-lookup"><span data-stu-id="dc9e8-140">5</span></span> | [<span data-ttu-id="dc9e8-141">準備包含 Windows 10 影像、SEMM 套件，以及 Windows 10 專業版的驅動程式和固件的 USB 快閃記憶體磁片磁碟機，以及 Surface Hub 2 的 Enterprise</span><span class="sxs-lookup"><span data-stu-id="dc9e8-141">Prepare USB flash drive containing Windows 10 image, SEMM package, and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="dc9e8-142">在此範例中建立單一 USB 磁片磁碟機 (名為 **BOOTME** ，) 包含 Windows 10 影像。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-142">Create a single USB drive (named **BOOTME** in this example) containing a Windows 10 image.</span></span> <span data-ttu-id="dc9e8-143">在 Surface Hub 2 (的 Windows 10 專業版和企業版中新增您的驅動程式與固件，請 (步驟 2) 並 SEMM 封裝檔案步驟 4) 移至 **BOOTME** 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-143">Add your Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (Step 2) and SEMM package files (Step 4) to the **BOOTME** drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="dc9e8-144">6</span><span class="sxs-lookup"><span data-stu-id="dc9e8-144">6</span></span> | [<span data-ttu-id="dc9e8-145">更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移</span><span class="sxs-lookup"><span data-stu-id="dc9e8-145">Update UEFI on Surface Hub 2S to enable OS migration</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="dc9e8-146">使用 **BOOTME** 磁片磁碟機來啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-146">Use the **BOOTME** drive to boot Surface Hub 2S to the UEFI menu and install SEMM package.</span></span>|
| <span data-ttu-id="dc9e8-147">utf-7</span><span class="sxs-lookup"><span data-stu-id="dc9e8-147">7</span></span> | [<span data-ttu-id="dc9e8-148">安裝 Windows 10 專業版或企業版1903或更新版本</span><span class="sxs-lookup"><span data-stu-id="dc9e8-148">Install Windows 10 Pro or Enterprise version 1903 or later</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="dc9e8-149">使用 **BOOTME** 磁片磁碟機來安裝 **Windows 10 專業版或企業** 版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-149">Use the **BOOTME** drive to Install **Windows 10 Pro or Enterprise** version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="dc9e8-150">型</span><span class="sxs-lookup"><span data-stu-id="dc9e8-150">8</span></span> | [<span data-ttu-id="dc9e8-151">在 Surface Hub 2 上安裝適用于 Windows 10 專業版與企業版的驅動程式及固件</span><span class="sxs-lookup"><span data-stu-id="dc9e8-151">Install Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="dc9e8-152">為了確保您的裝置擁有所有最新的更新和驅動程式，請[在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 Enterprise 的驅動程式和固件。MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案</span><span class="sxs-lookup"><span data-stu-id="dc9e8-152">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974)</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="dc9e8-153">9</span><span class="sxs-lookup"><span data-stu-id="dc9e8-153">9</span></span> | [<span data-ttu-id="dc9e8-154">將 Surface Hub 2 完整設定為個人生產力裝置</span><span class="sxs-lookup"><span data-stu-id="dc9e8-154">Fully configure Surface Hub 2S as a personal productivity device</span></span>](#next-steps)                                        |  <span data-ttu-id="dc9e8-155">啟用一組建議的設定和應用程式，以優化使用 Surface Hub 2 作為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-155">Enable the set of recommended settings and applications to optimize use of Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="dc9e8-156">驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求</span><span class="sxs-lookup"><span data-stu-id="dc9e8-156">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="dc9e8-157">將 Surface Hub 從 Windows 10 小組移植到 Windows 10 Desktop 之前所需的最低 UEFI 版本是 **694.2938.768.0**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-157">The minimum UEFI version required prior to migrating the Surface Hub from Windows 10 Team to Windows 10 Desktop is **694.2938.768.0**.</span></span>
 
**<span data-ttu-id="dc9e8-158">若要在您的系統上驗證目前的 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="dc9e8-158">To verify the current UEFI version on your system:</span></span>**

1. <span data-ttu-id="dc9e8-159">在 Surface Hub 秒主畫面上，選取 [**開始**]，然後開啟 [ **SurfaceApp** ] (**所有 app**  >  **Surface**) 。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-159">On Surface Hub 2S home screen, select **Start** and open the **SurfaceApp** (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="dc9e8-160">選取 **您的 surface** ，以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-160">Select **Your Surface** to display information about the Surface Hub, including the current version of the UEFI on the device.</span></span> <span data-ttu-id="dc9e8-161">如果 UEFI 版本是 **694.2938.768.0** 或更新版本（如下所示），則 uefi 適合您建立 SEMM 套件以啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-161">If the UEFI version is **694.2938.768.0** or later as shown below, the UEFI is eligible for you to create the SEMM package to enable OS migration.</span></span>

    ![開啟 Surface App & 選取您的表面](images/shm-fig1.png)
 
3. <span data-ttu-id="dc9e8-163">如果 UEFI 版本早于版本 **694.2938.768.0**，您將需要使用 Windows Update 取得目前的版本。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-163">If the UEFI version is earlier than version **694.2938.768.0**, you will need to obtain a current version using Windows Update.</span></span>

**<span data-ttu-id="dc9e8-164">若要從 Windows Update 更新 UEFI：</span><span class="sxs-lookup"><span data-stu-id="dc9e8-164">To update UEFI from Windows Update:</span></span>**
1. <span data-ttu-id="dc9e8-165">在 Surface Hub 2 秒，請以**管理員**身分登入，移至 [**所有應用程式**  >  **設定** >  **更新及安全性**]  >  **Windows 更新**並安裝所有更新，然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-165">On your Surface Hub 2S, sign in as an **Admin**, go to **All apps** > **Settings**> **Update and Security** > **Windows Update** and install all updates, then restart the device.</span></span> <span data-ttu-id="dc9e8-166">使用 Surface App 驗證 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-166">Verify the UEFI version using the Surface App.</span></span> <span data-ttu-id="dc9e8-167">注意：如果您不知道您的使用者名稱或系統管理員密碼，您將需要重設裝置。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-167">Note: If you do not know your username or admin password, you will need to reset the device.</span></span> <span data-ttu-id="dc9e8-168">若要深入瞭解，請參閱 [重設及復原 Surface Hub 2 秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-168">To learn more, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

2. <span data-ttu-id="dc9e8-169">重複這些步驟，直到 UEFI 版本為 **694.2938.768.0** 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-169">Repeat these steps until the UEFI version is **694.2938.768.0** or later.</span></span>

3. <span data-ttu-id="dc9e8-170">如果您在多次嘗試之後仍沒有看到更新的 UEFI，請核取 [ **更新歷程記錄** ] 並尋找任何失敗的固件安裝實例。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-170">If you still do not see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="dc9e8-171">您可能需要重設裝置 (**設定**  >  **更新 & 安全**  >  **重設裝置**) 。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-171">You may need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="dc9e8-172">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="dc9e8-172">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="dc9e8-173">在不同的電腦上：</span><span class="sxs-lookup"><span data-stu-id="dc9e8-173">On a separate PC:</span></span>

- <span data-ttu-id="dc9e8-174">從表面工具下載並安裝 Microsoft [SURFACE UEFI 配置](https://www.microsoft.com/download/details.aspx?id=46703) 檔。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-174">Download and install Microsoft [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT.</span></span> <span data-ttu-id="dc9e8-175">安裝 Windows 10 團隊後，surface UEFI 配置器不能在 Surface Hub 2 秒執行。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-175">Surface UEFI Configurator cannot be run on Surface Hub 2S, while Windows 10 Team is installed.</span></span>

- <span data-ttu-id="dc9e8-176">下載 [Surface Hub 2 驅動程式和固件 Windows 安裝程式。](https://www.microsoft.com/download/details.aspx?id=101974) 安裝新作業系統時要套用的 MSI 檔案。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-176">Download [Surface Hub 2 Drivers and Firmware Windows Installer .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) to be applied when installing the new operating system.</span></span>

### <span data-ttu-id="dc9e8-177">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="dc9e8-177">Prepare SEMM certificate</span></span>

<span data-ttu-id="dc9e8-178">如果這是您第一次使用 Surface UEFI 配置器，您必須準備證書。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-178">If this is your first time using Surface UEFI Configurator, you’ll need to prepare a certificate.</span></span> <span data-ttu-id="dc9e8-179">這個憑證可確保在裝置註冊 SEMM 之後，只可使用已核准憑證建立的套件來修改 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-179">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify UEFI settings.</span></span> <span data-ttu-id="dc9e8-180">您取得憑證的方式可能會根據貴組織的規模或複雜度而有所不同：</span><span class="sxs-lookup"><span data-stu-id="dc9e8-180">How you acquire a certificate may vary depending on the size or complexity of your organization:</span></span>

- <span data-ttu-id="dc9e8-181">大型企業組織通常會維護自己的憑證基礎結構，以針對每個標準安全性做法產生證書。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-181">Large enterprise organizations typically maintain their own certificate infrastructure to generate certificates per standard security practices.</span></span>

- <span data-ttu-id="dc9e8-182">中型企業及其他人可以選擇從協力廠商提供者取得憑證。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-182">Medium-sized businesses and others may choose to obtain a certificate from third party providers.</span></span> <span data-ttu-id="dc9e8-183">對於沒有足夠 IT 專業知識或專門 IT 安全小組的組織而言，這是我們的建議選項。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-183">This is the recommended option for organizations without sufficient IT expertise or dedicated IT security team.</span></span>

- <span data-ttu-id="dc9e8-184">或者，您也可以根據下列檔來產生含 PowerShell 腳本的自我簽署憑證： [Surface Enterprise 管理模式憑證需求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-184">Alternatively, you can generate a self-signed certificate with a PowerShell script per the following documentation: [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="dc9e8-185">或者，您可以使用 PowerShell 根據下列檔來建立您自己的憑證： [ [新-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps)]。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-185">Or use PowerShell to create your own certificate per the following documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate?view=win10-ps).</span></span>

<span data-ttu-id="dc9e8-186">SEMM 套件必須使用憑證加以保護，才能驗證設定檔的簽名，然後才能套用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-186">The SEMM package must be secured with a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="dc9e8-187">若要深入瞭解，請參閱 [Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 檔。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-187">To learn more, see [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
 
### <span data-ttu-id="dc9e8-188">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="dc9e8-188">Create SEMM package</span></span>

1. <span data-ttu-id="dc9e8-189">開啟 **SURFACE UEFI 配置** 器，然後選取 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-189">Open **Surface UEFI Configurator** and select **Start**.</span></span>

   ![開啟 Surface UEFI 配置器](images/shm-fig2.png)
   
2. <span data-ttu-id="dc9e8-191">選取 [ **Surface 裝置** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-191">Select **Surface Devices** and then select **Next**.</span></span>

   ![選取 Surface 裝置](images/shm-fig3.png)
  
3. <span data-ttu-id="dc9e8-193">選取 [設定 **套件**]。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-193">Select **Configuration Package**.</span></span>

   ![選取 [設定套件]](images/shm-fig4.png)
  
4. <span data-ttu-id="dc9e8-195">選取 [ **憑證保護**]。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-195">Select **Certificate Protection**.</span></span>

   ![選取憑證保護](images/shm-fig5.png)

5. <span data-ttu-id="dc9e8-197">系統會提示您新增憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-197">You will be prompted to add your certificate .pfx file.</span></span>

   ![系統會提示您新增憑證](images/shm-fig6.png)
   
6. <span data-ttu-id="dc9e8-199">輸入您的 **憑證密碼** ，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-199">Enter your **Certificate password** and select **OK**.</span></span>

   ![輸入您的憑證密碼，然後選取 [確定]](images/shm-fig7.png)

7. <span data-ttu-id="dc9e8-201">選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-201">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="dc9e8-202">每當您引導至 UEFI 時，就會需要此密碼。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-202">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="dc9e8-203">**強烈建議**您設定將在 Surface Hub 2 上使用的 UEFI 密碼。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-203">It is **strongly recommended** to set a UEFI password you will use on Surface Hub 2S.</span></span>

   ![按一下 [密碼保護]](images/shm-fig8.png)
   
8. <span data-ttu-id="dc9e8-205">設定 **UEFI 密碼** ，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-205">Set a **UEFI password** and select **OK**.</span></span>

   ![輸入您的 UEFI 密碼](images/shm-fig9.png)

   > [!IMPORTANT]
   > <span data-ttu-id="dc9e8-207">記下您的密碼。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-207">Make a note of your password.</span></span> <span data-ttu-id="dc9e8-208">如果您忘記或遺失密碼，就不會有復原程式。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-208">If you forget or lose your password, there is no recovery process.</span></span> 

9. <span data-ttu-id="dc9e8-209">選取 [ **Surface Hub 2 秒** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-209">Select **Surface Hub 2S** and then select **Next**.</span></span>

   ![選取 Surface Hub 2 秒](images/shm-fig10.png)
   
10. <span data-ttu-id="dc9e8-211">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-211">Select **Next**.</span></span>

    ![選取 [下一步]](images/shm-fig10a.png)

11. <span data-ttu-id="dc9e8-213">若要允許安裝 Windows 10 專業版或企業版，請選取 [ **EnableOsMigration]。**</span><span class="sxs-lookup"><span data-stu-id="dc9e8-213">To allow installation of Windows 10 Pro or Enterprise, select **EnableOsMigration.**</span></span>

    ![選取 [啟用 OS 遷移]](images/shm-fig11.png)
    
12. <span data-ttu-id="dc9e8-215">將 **EnableOSMigration** 設定為 [ **開啟** ] 並選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-215">Set **EnableOSMigration** to **On** and select **Next**.</span></span>

    ![將 [啟用作業系統遷移] 設定為 [開啟]](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="dc9e8-217">在您套用 SEMM 套件之後，所有的 UEFI 設定都會以灰色顯示 (在裝置上的 UEFI 功能表中的 [鎖定]) 。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-217">After you apply a SEMM package, all UEFI settings will display as grayed out (locked) in the UEFI menu on the device.</span></span> <span data-ttu-id="dc9e8-218">這包含其他設定（例如 IPv6 for PXE 啟動）的預設值。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-218">This includes default values for other settings such as IPv6 for PXE Boot.</span></span> <span data-ttu-id="dc9e8-219">若要修改 UEFI 設定，您需要套用另一個 SEMM 套件，或取消將裝置從 SEMM 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-219">To modify UEFI settings, you will need to apply another SEMM package or unenroll the device from SEMM.</span></span>

#### <span data-ttu-id="dc9e8-220">將 SEMM 套件儲存至 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="dc9e8-220">Save SEMM package to USB drive</span></span>

1. <span data-ttu-id="dc9e8-221">將 USB 磁片磁碟機連線至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-221">Connect a USB Drive to your PC.</span></span> <span data-ttu-id="dc9e8-222">選擇 [ **中心2秒** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-222">Choose **Hub 2S** and then select **Next**.</span></span>

   ![選取 [USB]](images/shm-fig13.png)
   
2. <span data-ttu-id="dc9e8-224">選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-224">Select **Build**.</span></span>

   ![選取組建](images/shm-fig14.png)

3. <span data-ttu-id="dc9e8-226">捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-226">Capture a screenshot of this page and then select **End**.</span></span> <span data-ttu-id="dc9e8-227">您的 SEMM 套件現已準備就緒，且包含 SEMM 套件 **DfciUpdate. dfi** 和 SEMM thumbprint 的文字檔 (憑證的指紋) 中的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-227">Your SEMM package is now ready and contains the SEMM package **DfciUpdate.dfi** and a text file with the SEMM thumbprint (the last two characters of the certificate’s thumbprint).</span></span>

   ![選取 [結束]](images/shm-fig15.png)
   
4. <span data-ttu-id="dc9e8-229">儲存憑證指紋的最後2個字元，這是您在 Surface Hub 2 上套用套件時，必須啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-229">Save the certificate thumbprint’s last 2 characters, which is required to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="dc9e8-230">準備包含 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式與固件的 USB 快閃記憶體磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="dc9e8-230">Prepare USB flash drive containing Windows 10 image, SEMM package, and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="dc9e8-231">您可以使用下列其中一個選項，在版本1903或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：</span><span class="sxs-lookup"><span data-stu-id="dc9e8-231">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) using one of the following options:</span></span>

- <span data-ttu-id="dc9e8-232">您目前的影像解決方案。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-232">Your current imaging solution.</span></span>

- <span data-ttu-id="dc9e8-233">[Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 可讓您建立可引導的 windows 10 影像，其中包含所有目前的 windows 10 更新、Office、您選擇的其他 app，以及所需的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-233">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) lets you create a bootable Windows 10 image which can include all of the current Windows 10 updates, Office, other apps of your choice, as well as the required drivers and firmware.</span></span> 

- <span data-ttu-id="dc9e8-234">具有 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機，接著  [在 Surface Hub 2 上安裝 Windows 10 專業版和 Enterprise 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-234">USB flash drive with Windows 10 Pro or Enterprise image, followed by installing  [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 

<span data-ttu-id="dc9e8-235">此程式說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後在 Surface Hub 2 上新增適用于 Windows 10 專業版與 Enterprise 的 SEMM 套件檔案和驅動程式及固件。MSI 檔案。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-235">This procedure describes creating a USB flash drive from installation media and then adding the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file.</span></span> <span data-ttu-id="dc9e8-236">如果您使用的是其他部署方法，請繼續閱讀下列章節： [更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-236">If you’re using other deployment methods, proceed to the following section: [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="dc9e8-237">安裝之後，您將需要 Windows 10 專業版或 Windows 10 Enterprise 的有效授權。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-237">Once installed, you will need a valid license for Windows 10 Pro or Windows 10 Enterprise.</span></span>

1. <span data-ttu-id="dc9e8-238">若要建立 Windows 10 專業版安裝，請依照 [下載 windows 10](https://www.microsoft.com/software-download/windows10) 頁面上使用 **媒體建立** 工具的指示進行。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-238">To create a Windows 10 Pro installation, follow the instructions on the [Download Windows 10](https://www.microsoft.com/software-download/windows10) page for using the **Media Creation** tool.</span></span> <span data-ttu-id="dc9e8-239">若要下載 Windows 10 企業版，請移至 [Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-239">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center.](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="dc9e8-240">插入新的 **USB 儲存** 空間磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-240">Insert a new **USB storage** drive.</span></span> <span data-ttu-id="dc9e8-241">啟動 **媒體建立** 工具，選取 [ **建立安裝媒體** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-241">Launch the **Media Creation** tool, select **Create installation media** and then select **Next**.</span></span>

   ![建立安裝媒體](images/shm-fig16.png)
   
3. <span data-ttu-id="dc9e8-243">選取 [語言]、[Windows 10] 和 [64 (x64) ，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-243">Select language, Windows 10, and 64-bit (x64) and then select **Next**.</span></span>

   ![選取 [語言]、[Windows 10] 和 [64 位] & 選取 [下一步]](images/shm-fig17.png)
   
4. <span data-ttu-id="dc9e8-245">選取 [ **USB 快閃磁碟機** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-245">Select **USB flash drive** and select **Next**.</span></span>

   ![選取 [USB 快閃磁碟機]，然後選取 [下一步]](images/shm-fig18.png)
   
5. <span data-ttu-id="dc9e8-247">下載完成後，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-247">When the download completes, select **Finish**.</span></span>

   ![選取 [完成]](images/shm-fig19.png)
   
6. <span data-ttu-id="dc9e8-249">在 Surface Hub 2 上複製適用于 Windows 10 專業版與企業版的 SEMM 套件檔案和驅動程式及固件。MSI 至 USB 快閃記憶體磁片磁碟機 (**BOOTME**) 包含您的 Windows 10 影像：</span><span class="sxs-lookup"><span data-stu-id="dc9e8-249">Copy the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI to the USB flash drive (**BOOTME**) containing your Windows 10 image:</span></span>

    - <span data-ttu-id="dc9e8-250">DfciUpdate.dfi</span><span class="sxs-lookup"><span data-stu-id="dc9e8-250">DfciUpdate.dfi</span></span>
    - <span data-ttu-id="dc9e8-251">含有 SEMM 指紋的文字檔。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-251">Text file with the SEMM thumbprint.</span></span> <span data-ttu-id="dc9e8-252">在此範例中 (： SurfaceUEFI_2020Aug25_1058.txt) </span><span class="sxs-lookup"><span data-stu-id="dc9e8-252">(In this example: SurfaceUEFI_2020Aug25_1058.txt)</span></span>
    - <span data-ttu-id="dc9e8-253">Surface Hub 2 上的 Windows 10 專業版與企業版的驅動程式和固件 ( # A0) </span><span class="sxs-lookup"><span data-stu-id="dc9e8-253">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span></span>

### <span data-ttu-id="dc9e8-254">更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移</span><span class="sxs-lookup"><span data-stu-id="dc9e8-254">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

<span data-ttu-id="dc9e8-255">使用您的 **BOOTME** 磁片磁碟機來安裝 SEMM 套件檔案，並更新 UEFI，讓 Surface Hub 執行 Windows 10 專業版或企業版。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-255">Use your **BOOTME** drive to install the SEMM package files and update the UEFI, enabling Surface Hub to run Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="dc9e8-256">然後從 **BOOTME** 磁片磁碟機啟動以安裝 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-256">Then boot from the **BOOTME** drive to install Windows 10.</span></span>

1. <span data-ttu-id="dc9e8-257">插入您的 **BOOTME** 磁片磁碟機，其中包含適用于 Surface Hub 2 的 Windows 10 專業版與企業版的 SEMM 套件檔案、驅動程式和固件。MSI 和 Windows 10 在 Surface Hub 2 的 USB-A 埠上安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-257">Insert your **BOOTME** drive containing SEMM package files, Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI, and Windows 10 install files into the USB-A port on Surface Hub 2S.</span></span>  

2. <span data-ttu-id="dc9e8-258">若要引導至 UEFI：</span><span class="sxs-lookup"><span data-stu-id="dc9e8-258">To boot into UEFI:</span></span>

   1. <span data-ttu-id="dc9e8-259">第一次關閉 () Surface Hub 2 的關閉電源。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-259">First power off (shutdown) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="dc9e8-260">按住 [ **音量 +** ]，然後按下再放開 [ **電源** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-260">Press and hold **Volume +** and then press and release the **Power** button.</span></span>
   1. <span data-ttu-id="dc9e8-261">保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-261">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![保留 holdling 的音量 +，直到 UEFI 功能表出現為止](images/shm-fig20.png)
      
3. <span data-ttu-id="dc9e8-263">當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (強烈建議) ）。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-263">When the device restarts, enter the UEFI password you created earlier, if applicable (strongly recommended).</span></span>

   ![裝置重新開機後，請輸入您的 UEFI paassword](images/shm-fig22.png)
   
4. <span data-ttu-id="dc9e8-265">在 UEFI 功能表中，選取**Management**[  >  **從 USB 安裝**管理元件]。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-265">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![選取 [管理] & 從 USB 安裝](images/shm-fig21.png)
   
5. <span data-ttu-id="dc9e8-267">選取 [ **立即重新開機**]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-267">Select **Restart now**, as shown below.</span></span> <span data-ttu-id="dc9e8-268">裝置將會重新開機，並在畫面中間顯示白色4方形標誌，然後將它關閉。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-268">The device will reboot and display the white 4-square logo in the middle of screen and then it will shut down.</span></span>

   ![選取 [立即重新開機]](images/shm-fig25.png)
   
6. <span data-ttu-id="dc9e8-270">按下並放開電源按鈕，會顯示紅色畫面，提示您啟用 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-270">Press and release the power button, a red screen will display prompting you to activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="dc9e8-271">輸入您的兩個字元的 **憑證指紋**，您的 **UEFI 設定密碼** ，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-271">Enter your two-character **certificate thumbprint**, your **UEFI settings password** and then select **OK**.</span></span>

   ![輸入2個字元的憑證指紋](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="dc9e8-273">一旦您在裝置上啟用 SEMM，就會套用新的 UEFI 設定 **EnableOSMigration** 。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-273">Once you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="dc9e8-274">您將無法再存取 Windows 10 小組，必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-274">You will no longer be able to access Windows 10 Team and must proceed to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

8. <span data-ttu-id="dc9e8-275">裝置將會重新開機，在畫面中間顯示白色4方形標誌，然後再按一次將它關閉</span><span class="sxs-lookup"><span data-stu-id="dc9e8-275">The device will reboot, display the white 4-square logo in the middle of the screen, and then again it will shut down</span></span>

### <span data-ttu-id="dc9e8-276">安裝 Windows 10 專業版或企業版</span><span class="sxs-lookup"><span data-stu-id="dc9e8-276">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="dc9e8-277">如果您的可引導 Windows 10 專業版或企業版磁片磁碟機不在 Surface Hub 2 USB-A 埠中，請將它立即插入，然後按下再放開電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-277">If your bootable Windows 10 Pro or Enterprise drive is not already in the Surface Hub 2 USB-A port, insert it now and then press and release the power button.</span></span>

2. <span data-ttu-id="dc9e8-278">裝置將會啟動，您會在畫面中間看到白色的4方形，然後您會在白色四個方形標誌下方看到旋轉的圓形。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-278">The device will start, you will see the white 4-square in the middle of the screen, and then you will see a spinning circle below the white four-square logo.</span></span>

3. <span data-ttu-id="dc9e8-279">如果裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置電源 (拔下電源線，然後再插回) 。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-279">If the device does not automatically boot to the USB drive, power off the device (unplug the power cord and plug it back in).</span></span> <span data-ttu-id="dc9e8-280">重新插入電源線之後，裝置會在幾秒後啟動至畫面中間的白色4方形標誌，或者，您可以按下並放開電源按鈕來重新開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-280">After plugging the power cord back in, the device should boot after a few seconds to the white 4-square logo in the middle of screen, or you can press and release the power button to turn the device back on.</span></span> <span data-ttu-id="dc9e8-281">在螢幕中間看到4方塊標誌之後，按住 [音量] 按鈕，直到您看到位於白色四個方形標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-281">Immediately after you see the 4-square logo in the middle of the screen, press and hold the volume down button until you see the spinning circle below the white four-square logo.</span></span>
 
   ![從 USB 啟動至 Windows 10](images/shm-fig26.png)
   
4. <span data-ttu-id="dc9e8-283">當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或企業版 (版本1903或) 更新版本。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-283">When the out of box experience (OOBE) setup launches, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="dc9e8-284">安裝 Surface Hub 2 驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="dc9e8-284">Install Surface Hub 2 drivers and firmware</span></span>

 - <span data-ttu-id="dc9e8-285">為了確保您的裝置擁有所有最新的更新和驅動程式，請 [在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 Enterprise 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-285">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
### <span data-ttu-id="dc9e8-286">後續步驟</span><span class="sxs-lookup"><span data-stu-id="dc9e8-286">Next steps</span></span>

<span data-ttu-id="dc9e8-287">若要將 Surface Hub 2 完整設定為個人生產力裝置，請參閱在 [Surface Hub 2 上設定 Windows 10 專業版或企業版](surface-hub-2-post-install.md)。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-287">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="dc9e8-288">如果遵循這份檔中所述的步驟無法將您的裝置遷移至 Windows 10 專業版或 Surface Hub 2 Enterprise，請與 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)聯繫。</span><span class="sxs-lookup"><span data-stu-id="dc9e8-288">If following the steps outlined in this document is unsuccessful in migrating your device to Windows 10 Pro or Enterprise for Surface Hub 2, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

### <span data-ttu-id="dc9e8-289">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="dc9e8-289">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="dc9e8-290">如果您想要將裝置還原至 Windows 10 小組，請參閱 [重設及恢復 Surface Hub 2 秒](surface-hub-2s-recover-reset.md)</span><span class="sxs-lookup"><span data-stu-id="dc9e8-290">If you would Like to restore your device to Windows 10 Team, refer to [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md)</span></span>

