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
ms.date: 09/29/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0c6a52d1023377f51ae6a63879e54b86db16cb9a
ms.sourcegitcommit: 35f64110ce8e0c0b019b02023d746f648f554c1c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/29/2020
ms.locfileid: "11088627"
---
# <span data-ttu-id="24b5e-104">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="24b5e-104">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

## <span data-ttu-id="24b5e-105">簡介</span><span class="sxs-lookup"><span data-stu-id="24b5e-105">Introduction</span></span>

<span data-ttu-id="24b5e-106">Surface Hub 秒數是由 Windows 10 小組預先安裝的，這是 Windows 10 的自訂版本，可協助在會議室環境中輕鬆共同作業。</span><span class="sxs-lookup"><span data-stu-id="24b5e-106">Surface Hub 2S comes pre-installed with Windows 10 Team, a customized edition of Windows 10 designed to facilitate easy collaboration in meeting room environments.</span></span> <span data-ttu-id="24b5e-107">現在，您可以選擇執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。</span><span class="sxs-lookup"><span data-stu-id="24b5e-107">Now you have the option of running Windows 10 Pro or Enterprise to use Surface Hub 2S much like any other PC.</span></span> 

> [!IMPORTANT]
><span data-ttu-id="24b5e-108">與典型的升級或遷移不同，此程式必須遵循說明性程式，如本頁面所述。</span><span class="sxs-lookup"><span data-stu-id="24b5e-108">Unlike a typical upgrade or migration, this process requires you to follow a prescriptive procedure, as described on this page.</span></span> <span data-ttu-id="24b5e-109">在繼續之前，請先查看 [解決方案元件](#solution-components) 與 [遷移及安裝工作流程](#migration-and-installation-workflow-summary) 。</span><span class="sxs-lookup"><span data-stu-id="24b5e-109">Review the [Solution components](#solution-components) and [Migration and installation workflow](#migration-and-installation-workflow-summary) before proceeding.</span></span>


> [!NOTE]
> <span data-ttu-id="24b5e-110">當您安裝 Windows 10 專業版或企業版時，您將需要與現有的 Windows 10 小組授權分開的新授權。</span><span class="sxs-lookup"><span data-stu-id="24b5e-110">When you install Windows 10 Pro or Enterprise, you will need a new licence separate from your existing Windows 10 Team license.</span></span> 


<span data-ttu-id="24b5e-111">您可以從 Windows 10 小組開始遷移，使用不同的電腦和可下載的工具- **SURFACE UEFI 配置** 器，建立包含您套用至 Surface Hub 2 秒的新 UEFI 設定的套件。</span><span class="sxs-lookup"><span data-stu-id="24b5e-111">You start the migration from Windows 10 Team using a separate PC and downloadable tool -- **Surface UEFI Configurator** --  to create a package containing a new UEFI setting that you apply to Surface Hub 2S.</span></span>  <span data-ttu-id="24b5e-112">Surface UEFI 配置處理常式會將介面轉換成 Surface Enterprise 管理模式 (SEMM) ，旨在協助集中管理公司環境中的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="24b5e-112">Surface UEFI Configurator functions as an interface into Surface Enterprise Management Mode (SEMM), designed to facilitate centralized management of firmware settings on Surface devices in a corporate environment.</span></span> <span data-ttu-id="24b5e-113">若要深入瞭解 SEMM，請參閱 [Microsoft Surface Enterprise 管理模式檔](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="24b5e-113">To learn more about SEMM, see [Microsoft Surface Enterprise Management Mode documentation](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>
 

## <span data-ttu-id="24b5e-114">解決方案元件</span><span class="sxs-lookup"><span data-stu-id="24b5e-114">Solution Components</span></span>

- <span data-ttu-id="24b5e-115">執行 Windows 10 小組作業系統的 Surface Hub 2 秒裝置</span><span class="sxs-lookup"><span data-stu-id="24b5e-115">Surface Hub 2S device running Windows 10 Team operating system</span></span>
- <span data-ttu-id="24b5e-116">運行 Windows 10 的個別裝置</span><span class="sxs-lookup"><span data-stu-id="24b5e-116">Separate device running Windows 10</span></span>
- <span data-ttu-id="24b5e-117">用於建立 SEMM 套件的 Surface UEFI 設定檔工具</span><span class="sxs-lookup"><span data-stu-id="24b5e-117">Surface UEFI Configurator tool to create the SEMM package</span></span>
- <span data-ttu-id="24b5e-118">Windows 10 專業版或企業版作業系統影像、版本1903或更高版本</span><span class="sxs-lookup"><span data-stu-id="24b5e-118">Windows 10 Pro or Enterprise OS image, version 1903 or greater</span></span>
- <span data-ttu-id="24b5e-119">含儲存空間、FAT32 格式的兩個 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="24b5e-119">Two USB drives with 16GB of storage, FAT32 format</span></span>
- <span data-ttu-id="24b5e-120">Windows 10 專業版的驅動程式和固件，以及 Surface Hub 2、Windows 安裝程式。MSI 檔案</span><span class="sxs-lookup"><span data-stu-id="24b5e-120">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2, Windows Installer .MSI file</span></span>
- <span data-ttu-id="24b5e-121">網際網路連線</span><span class="sxs-lookup"><span data-stu-id="24b5e-121">Internet connection</span></span>
- <span data-ttu-id="24b5e-122">影像處理方案 (選用) </span><span class="sxs-lookup"><span data-stu-id="24b5e-122">Imaging solution (optional)</span></span>

 
## <span data-ttu-id="24b5e-123">遷移和安裝工作流程摘要</span><span class="sxs-lookup"><span data-stu-id="24b5e-123">Migration and installation workflow summary</span></span>

| <span data-ttu-id="24b5e-124">步驟</span><span class="sxs-lookup"><span data-stu-id="24b5e-124">Step</span></span>  | <span data-ttu-id="24b5e-125">動作</span><span class="sxs-lookup"><span data-stu-id="24b5e-125">Action</span></span>                                                                                                 | <span data-ttu-id="24b5e-126">摘要</span><span class="sxs-lookup"><span data-stu-id="24b5e-126">Summary</span></span>                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="24b5e-127">sr-1</span><span class="sxs-lookup"><span data-stu-id="24b5e-127">1</span></span> | [<span data-ttu-id="24b5e-128">驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求</span><span class="sxs-lookup"><span data-stu-id="24b5e-128">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | <span data-ttu-id="24b5e-129">確定 UEFI 版本為694.2938.768.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="24b5e-129">Ensure the UEFI version is 694.2938.768.0 or later.</span></span>                                                                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="24b5e-130">pplx-2</span><span class="sxs-lookup"><span data-stu-id="24b5e-130">2</span></span> | [<span data-ttu-id="24b5e-131">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="24b5e-131">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | <span data-ttu-id="24b5e-132">選取 [ [表面工具](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面上的 [下載] 按鈕，選取並下載 **SURFACE UEFI 設定檔。MSI** 檔案，並將它安裝在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="24b5e-132">Select the Download button on the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page, select and download the **Surface UEFI Configurator .MSI file** and install it on a separate PC.</span></span> <span data-ttu-id="24b5e-133">[在 Surface Hub 2 上下載適用于 Windows 10 專業版與企業版的驅動程式及固件。MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案並將其儲存，以便在步驟5中使用。</span><span class="sxs-lookup"><span data-stu-id="24b5e-133">Download [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) and save it for use in Step 5.</span></span> |
| <span data-ttu-id="24b5e-134">3</span><span class="sxs-lookup"><span data-stu-id="24b5e-134">3</span></span> | [<span data-ttu-id="24b5e-135">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="24b5e-135">Prepare SEMM certificate</span></span>](#prepare-semm-certificate)                                                                          | <span data-ttu-id="24b5e-136">準備運行 Surface UEFI 配置器所需的憑證，或使用您目前的憑證。</span><span class="sxs-lookup"><span data-stu-id="24b5e-136">Prepare required certificate for running Surface UEFI Configurator or use your current certificate.</span></span>                                                                                                                                                                                                                                                                                                      |
| <span data-ttu-id="24b5e-137">4</span><span class="sxs-lookup"><span data-stu-id="24b5e-137">4</span></span> | [<span data-ttu-id="24b5e-138">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="24b5e-138">Create SEMM package</span></span>](#create-semm-package)                                                                               | <span data-ttu-id="24b5e-139">啟動 Surface UEFI 設定檔，以在 USB 磁片磁碟機上建立 SEMM 套件，這將包含要套用到 Surface Hub 2 的必要配置檔案。</span><span class="sxs-lookup"><span data-stu-id="24b5e-139">Launch Surface UEFI Configurator to create a SEMM package on a USB drive which will contain the required configuration files to apply on Surface Hub 2S.</span></span> <span data-ttu-id="24b5e-140">將這些 SEMM 套件檔案複製到您電腦上的資料夾。</span><span class="sxs-lookup"><span data-stu-id="24b5e-140">Copy these SEMM package  files to a folder on your PC.</span></span>                                                                                                                                                                                          |
| <span data-ttu-id="24b5e-141">500</span><span class="sxs-lookup"><span data-stu-id="24b5e-141">5</span></span> | [<span data-ttu-id="24b5e-142">準備包含 Windows 10 影像、SEMM 套件，以及 Windows 10 專業版的驅動程式和固件的 USB 快閃記憶體磁片磁碟機，以及 Surface Hub 2 的 Enterprise</span><span class="sxs-lookup"><span data-stu-id="24b5e-142">Prepare USB flash drive containing Windows 10 image, SEMM package, and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | <span data-ttu-id="24b5e-143">在此範例中建立單一 USB 磁片磁碟機 (名為 **BOOTME** ，) 包含 Windows 10 影像。</span><span class="sxs-lookup"><span data-stu-id="24b5e-143">Create a single USB drive (named **BOOTME** in this example) containing a Windows 10 image.</span></span> <span data-ttu-id="24b5e-144">在 Surface Hub 2 (的 Windows 10 專業版和企業版中新增您的驅動程式與固件，請 (步驟 2) 並 SEMM 封裝檔案步驟 4) 移至 **BOOTME** 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="24b5e-144">Add your Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (Step 2) and SEMM package files (Step 4) to the **BOOTME** drive.</span></span>                                                                                                                                                                                                  |
| <span data-ttu-id="24b5e-145">6</span><span class="sxs-lookup"><span data-stu-id="24b5e-145">6</span></span> | [<span data-ttu-id="24b5e-146">更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移</span><span class="sxs-lookup"><span data-stu-id="24b5e-146">Update UEFI on Surface Hub 2S to enable OS migration</span></span>](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | <span data-ttu-id="24b5e-147">使用 **BOOTME** 磁片磁碟機來啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。</span><span class="sxs-lookup"><span data-stu-id="24b5e-147">Use the **BOOTME** drive to boot Surface Hub 2S to the UEFI menu and install SEMM package.</span></span>|
| <span data-ttu-id="24b5e-148">utf-7</span><span class="sxs-lookup"><span data-stu-id="24b5e-148">7</span></span> | [<span data-ttu-id="24b5e-149">安裝 Windows 10 專業版或企業版1903或更新版本</span><span class="sxs-lookup"><span data-stu-id="24b5e-149">Install Windows 10 Pro or Enterprise version 1903 or later</span></span>](#install-windows-10-pro-or-enterprise)                                        | <span data-ttu-id="24b5e-150">使用 **BOOTME** 磁片磁碟機來安裝 **Windows 10 專業版或企業** 版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="24b5e-150">Use the **BOOTME** drive to Install **Windows 10 Pro or Enterprise** version 1903 or later.</span></span>                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="24b5e-151">型</span><span class="sxs-lookup"><span data-stu-id="24b5e-151">8</span></span> | [<span data-ttu-id="24b5e-152">在 Surface Hub 2 上安裝適用于 Windows 10 專業版與企業版的驅動程式及固件</span><span class="sxs-lookup"><span data-stu-id="24b5e-152">Install Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2</span></span>](#install-surface-hub-2-drivers-and-firmware)                                        | <span data-ttu-id="24b5e-153">為了確保您的裝置擁有所有最新的更新和驅動程式，請[在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 Enterprise 的驅動程式和固件。MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案</span><span class="sxs-lookup"><span data-stu-id="24b5e-153">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file](https://www.microsoft.com/download/details.aspx?id=101974)</span></span>                                                                                                                                                                                                                                                                                  |
| <span data-ttu-id="24b5e-154">9</span><span class="sxs-lookup"><span data-stu-id="24b5e-154">9</span></span> | [<span data-ttu-id="24b5e-155">將 Surface Hub 2 完整設定為個人生產力裝置</span><span class="sxs-lookup"><span data-stu-id="24b5e-155">Fully configure Surface Hub 2S as a personal productivity device</span></span>](#next-steps)                                        |  <span data-ttu-id="24b5e-156">啟用一組建議的設定和應用程式，以優化使用 Surface Hub 2 作為個人生產力裝置。</span><span class="sxs-lookup"><span data-stu-id="24b5e-156">Enable the set of recommended settings and applications to optimize use of Surface Hub 2S as a personal productivity device.</span></span>                                                                                                                                                                                                                                                                    |

### <span data-ttu-id="24b5e-157">驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求</span><span class="sxs-lookup"><span data-stu-id="24b5e-157">Verify UEFI version on Surface Hub 2S meets minimum requirements</span></span>

<span data-ttu-id="24b5e-158">將 Surface Hub 從 Windows 10 小組移植到 Windows 10 Desktop 之前所需的最低 UEFI 版本是 **694.2938.768.0**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-158">The minimum UEFI version required prior to migrating the Surface Hub from Windows 10 Team to Windows 10 Desktop is **694.2938.768.0**.</span></span>
 
**<span data-ttu-id="24b5e-159">若要在您的系統上驗證目前的 UEFI 版本：</span><span class="sxs-lookup"><span data-stu-id="24b5e-159">To verify the current UEFI version on your system:</span></span>**

1. <span data-ttu-id="24b5e-160">在 Surface Hub 秒主畫面上，選取 [**開始**]，然後開啟 [ **SurfaceApp** ] (**所有 app**  >  **Surface**) 。</span><span class="sxs-lookup"><span data-stu-id="24b5e-160">On Surface Hub 2S home screen, select **Start** and open the **SurfaceApp** (**All Apps** > **Surface**).</span></span>

2. <span data-ttu-id="24b5e-161">選取 **您的 surface** ，以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="24b5e-161">Select **Your Surface** to display information about the Surface Hub, including the current version of the UEFI on the device.</span></span> <span data-ttu-id="24b5e-162">如果 UEFI 版本是 **694.2938.768.0** 或更新版本（如下所示），則 uefi 適合您建立 SEMM 套件以啟用作業系統遷移。</span><span class="sxs-lookup"><span data-stu-id="24b5e-162">If the UEFI version is **694.2938.768.0** or later as shown below, the UEFI is eligible for you to create the SEMM package to enable OS migration.</span></span>

    ![開啟 Surface App & 選取您的表面](images/shm-fig1.png)
 
3. <span data-ttu-id="24b5e-164">如果 UEFI 版本早于版本 **694.2938.768.0**，您將需要使用 Windows Update 取得目前的版本。</span><span class="sxs-lookup"><span data-stu-id="24b5e-164">If the UEFI version is earlier than version **694.2938.768.0**, you will need to obtain a current version using Windows Update.</span></span>

**<span data-ttu-id="24b5e-165">若要從 Windows Update 更新 UEFI：</span><span class="sxs-lookup"><span data-stu-id="24b5e-165">To update UEFI from Windows Update:</span></span>**

1. <span data-ttu-id="24b5e-166">在 Surface Hub 2 秒，請以**管理員**身分登入，移至 [**所有應用程式**  >  **設定** >  **更新及安全性**]  >  **Windows 更新**並安裝所有更新，然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="24b5e-166">On your Surface Hub 2S, sign in as an **Admin**, go to **All apps** > **Settings**> **Update and Security** > **Windows Update** and install all updates, then restart the device.</span></span> <span data-ttu-id="24b5e-167">使用 Surface App 驗證 UEFI 版本。</span><span class="sxs-lookup"><span data-stu-id="24b5e-167">Verify the UEFI version using the Surface App.</span></span> <span data-ttu-id="24b5e-168">注意：如果您不知道您的使用者名稱或系統管理員密碼，您將需要重設裝置。</span><span class="sxs-lookup"><span data-stu-id="24b5e-168">Note: If you do not know your username or admin password, you will need to reset the device.</span></span> <span data-ttu-id="24b5e-169">若要深入瞭解，請參閱 [重設及復原 Surface Hub 2 秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)。</span><span class="sxs-lookup"><span data-stu-id="24b5e-169">To learn more, see [Reset and recovery for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset).</span></span>

2. <span data-ttu-id="24b5e-170">重複這些步驟，直到 UEFI 版本為 **694.2938.768.0** 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="24b5e-170">Repeat these steps until the UEFI version is **694.2938.768.0** or later.</span></span>

3. <span data-ttu-id="24b5e-171">如果您在多次嘗試之後仍沒有看到更新的 UEFI，請核取 [ **更新歷程記錄** ] 並尋找任何失敗的固件安裝實例。</span><span class="sxs-lookup"><span data-stu-id="24b5e-171">If you still do not see the updated UEFI after multiple attempts, check **Update History** and look for any instances of failed firmware installations.</span></span> <span data-ttu-id="24b5e-172">您可能需要重設裝置 (**設定**  >  **更新 & 安全**  >  **重設裝置**) 。</span><span class="sxs-lookup"><span data-stu-id="24b5e-172">You may need to reset your device (**Settings** > **Update & security** > **Reset device**).</span></span>

### <span data-ttu-id="24b5e-173">下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="24b5e-173">Download Surface UEFI Configurator and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="24b5e-174">在不同的電腦上：</span><span class="sxs-lookup"><span data-stu-id="24b5e-174">On a separate PC:</span></span>

- <span data-ttu-id="24b5e-175">從表面工具下載 Microsoft [SURFACE UEFI 配置](https://www.microsoft.com/download/details.aspx?id=46703) 器。</span><span class="sxs-lookup"><span data-stu-id="24b5e-175">Download Microsoft [Surface UEFI Configurator](https://www.microsoft.com/download/details.aspx?id=46703) from Surface Tools for IT.</span></span> <span data-ttu-id="24b5e-176">安裝 Windows 10 團隊後，surface UEFI 配置器不能在 Surface Hub 2 秒執行。</span><span class="sxs-lookup"><span data-stu-id="24b5e-176">Surface UEFI Configurator cannot be run on Surface Hub 2S, while Windows 10 Team is installed.</span></span>

- <span data-ttu-id="24b5e-177">下載 [Surface Hub 2 驅動程式和固件 Windows 安裝程式。](https://www.microsoft.com/download/details.aspx?id=101974) 安裝新作業系統時要套用的 MSI 檔案。</span><span class="sxs-lookup"><span data-stu-id="24b5e-177">Download [Surface Hub 2 Drivers and Firmware Windows Installer .MSI file](https://www.microsoft.com/download/details.aspx?id=101974) to be applied when installing the new operating system.</span></span>

### <span data-ttu-id="24b5e-178">準備 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="24b5e-178">Prepare SEMM certificate</span></span>

<span data-ttu-id="24b5e-179">如果這是您第一次使用 Surface UEFI 配置器，您必須準備證書。</span><span class="sxs-lookup"><span data-stu-id="24b5e-179">If this is your first time using Surface UEFI Configurator, you’ll need to prepare a certificate.</span></span> <span data-ttu-id="24b5e-180">這個憑證可確保在裝置註冊 SEMM 之後，只可使用已核准憑證建立的套件來修改 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="24b5e-180">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify UEFI settings.</span></span> <span data-ttu-id="24b5e-181">您取得憑證的方式可能會根據貴組織的規模或複雜度而有所不同：</span><span class="sxs-lookup"><span data-stu-id="24b5e-181">How you acquire a certificate may vary depending on the size or complexity of your organization:</span></span>

- <span data-ttu-id="24b5e-182">大型企業組織通常會維護自己的憑證基礎結構，以針對每個標準安全性做法產生證書。</span><span class="sxs-lookup"><span data-stu-id="24b5e-182">Large enterprise organizations typically maintain their own certificate infrastructure to generate certificates per standard security practices.</span></span>

- <span data-ttu-id="24b5e-183">中型企業及其他人可以選擇從協力廠商提供者取得憑證。</span><span class="sxs-lookup"><span data-stu-id="24b5e-183">Medium-sized businesses and others may choose to obtain a certificate from third party providers.</span></span> <span data-ttu-id="24b5e-184">對於沒有足夠 IT 專業知識或專門 IT 安全小組的組織而言，這是我們的建議選項。</span><span class="sxs-lookup"><span data-stu-id="24b5e-184">This is the recommended option for organizations without sufficient IT expertise or dedicated IT security team.</span></span>

- <span data-ttu-id="24b5e-185">或者，您也可以根據下列檔來產生含 PowerShell 腳本的自我簽署憑證： [Surface Enterprise 管理模式憑證需求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="24b5e-185">Alternatively, you can generate a self-signed certificate with a PowerShell script per the following documentation: [Surface Enterprise Management Mode certificate requirements](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span> <span data-ttu-id="24b5e-186">或者，您可以使用 PowerShell 根據下列檔來建立您自己的憑證： [ [新-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)]。</span><span class="sxs-lookup"><span data-stu-id="24b5e-186">Or use PowerShell to create your own certificate per the following documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>

<span data-ttu-id="24b5e-187">使用 Surface UEFI 組態工具所建立的 SEMM 套件必須使用憑證加以保護，才能驗證設定檔的簽名，然後才能套用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="24b5e-187">The SEMM package created by using the Surface UEFI Configurator tool must be secured with a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="24b5e-188">若要深入瞭解，請參閱 [Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 檔。</span><span class="sxs-lookup"><span data-stu-id="24b5e-188">To learn more, see [Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation.</span></span>
 
 
### <span data-ttu-id="24b5e-189">建立 SEMM 套件</span><span class="sxs-lookup"><span data-stu-id="24b5e-189">Create SEMM package</span></span>

1. <span data-ttu-id="24b5e-190">安裝先前下載到個別電腦的 **SURFACE UEFI 配置** 工具。</span><span class="sxs-lookup"><span data-stu-id="24b5e-190">Install the **Surface UEFI Configurator** tool downloaded earlier to a separate PC.</span></span> 
2. <span data-ttu-id="24b5e-191">開啟 **SURFACE UEFI 配置** 器，然後選取 [ **開始**]。</span><span class="sxs-lookup"><span data-stu-id="24b5e-191">Open **Surface UEFI Configurator** and select **Start**.</span></span>

   ![開啟 Surface UEFI 配置器](images/shm-fig2.png)
   
3. <span data-ttu-id="24b5e-193">選取 [ **Surface 裝置** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-193">Select **Surface Devices** and then select **Next**.</span></span>

   ![選取 Surface 裝置](images/shm-fig3.png)
  
4. <span data-ttu-id="24b5e-195">選取 [設定 **套件**]。</span><span class="sxs-lookup"><span data-stu-id="24b5e-195">Select **Configuration Package**.</span></span>

   ![選取 [設定套件]](images/shm-fig4.png)
  
5. <span data-ttu-id="24b5e-197">選取 [ **憑證保護**]。</span><span class="sxs-lookup"><span data-stu-id="24b5e-197">Select **Certificate Protection**.</span></span>

   ![選取憑證保護](images/shm-fig5.png)

6. <span data-ttu-id="24b5e-199">系統會提示您新增憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="24b5e-199">You will be prompted to add your certificate .pfx file.</span></span>

   ![系統會提示您新增憑證](images/shm-fig6.png)
   
7. <span data-ttu-id="24b5e-201">輸入您的 **憑證密碼** ，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-201">Enter your **Certificate password** and select **OK**.</span></span>

   ![輸入您的憑證密碼，然後選取 [確定]](images/shm-fig7.png)

8. <span data-ttu-id="24b5e-203">選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="24b5e-203">Select **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="24b5e-204">每當您引導至 UEFI 時，就會需要此密碼。</span><span class="sxs-lookup"><span data-stu-id="24b5e-204">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="24b5e-205">**強烈建議**您設定將在 Surface Hub 2 上使用的 UEFI 密碼。</span><span class="sxs-lookup"><span data-stu-id="24b5e-205">It is **strongly recommended** to set a UEFI password you will use on Surface Hub 2S.</span></span>

   ![按一下 [密碼保護]](images/shm-fig8.png)
   
9. <span data-ttu-id="24b5e-207">設定 **UEFI 密碼** ，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-207">Set a **UEFI password** and select **OK**.</span></span>

 > [!IMPORTANT]
   > <span data-ttu-id="24b5e-208">將密碼儲存在您的組織中負責管理 Surface Hub 的 IT 系統管理員可存取的安全位置。</span><span class="sxs-lookup"><span data-stu-id="24b5e-208">Save the password in a secure location accessible to IT admins in your organization responsible for managing Surface Hubs.</span></span> <span data-ttu-id="24b5e-209">如果密碼遺失，就不會有復原程式。</span><span class="sxs-lookup"><span data-stu-id="24b5e-209">If the password is lost, there is no recovery process.</span></span> 

   ![輸入您的 UEFI 密碼](images/shm-fig9.png)

10. <span data-ttu-id="24b5e-211">選取 [ **Surface Hub 2 秒** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-211">Select **Surface Hub 2S** and then select **Next**.</span></span>

   ![選取 Surface Hub 2 秒](images/shm-fig10.png)
   
11. <span data-ttu-id="24b5e-213">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-213">Select **Next**.</span></span>

    ![選取 [下一步]](images/shm-fig10a.png)

12. <span data-ttu-id="24b5e-215">若要允許安裝 Windows 10 專業版或企業版，請選取 [ **EnableOsMigration]。**</span><span class="sxs-lookup"><span data-stu-id="24b5e-215">To allow installation of Windows 10 Pro or Enterprise, select **EnableOsMigration.**</span></span>

    ![選取 [啟用 OS 遷移]](images/shm-fig11.png)
    
13. <span data-ttu-id="24b5e-217">將 **EnableOSMigration** 設定為 [ **開啟** ] 並選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-217">Set **EnableOSMigration** to **On** and select **Next**.</span></span>

    ![將 [啟用作業系統遷移] 設定為 [開啟]](images/shm-fig12.png)

> [!NOTE]
> <span data-ttu-id="24b5e-219">在您套用 SEMM 套件之後，所有的 UEFI 設定都會以灰色顯示 (在裝置上的 UEFI 功能表中的 [鎖定]) 。</span><span class="sxs-lookup"><span data-stu-id="24b5e-219">After you apply a SEMM package, all UEFI settings will display as grayed out (locked) in the UEFI menu on the device.</span></span> <span data-ttu-id="24b5e-220">這包含其他設定（例如 IPv6 for PXE 啟動）的預設值。</span><span class="sxs-lookup"><span data-stu-id="24b5e-220">This includes default values for other settings such as IPv6 for PXE Boot.</span></span> <span data-ttu-id="24b5e-221">若要修改 UEFI 設定，您需要套用另一個 SEMM 套件，或取消將裝置從 SEMM 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="24b5e-221">To modify UEFI settings, you will need to apply another SEMM package or unenroll the device from SEMM.</span></span>

#### <span data-ttu-id="24b5e-222">將 SEMM 套件儲存至 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="24b5e-222">Save SEMM package to USB drive</span></span>

1. <span data-ttu-id="24b5e-223">將 USB 磁片磁碟機連線至您的電腦。</span><span class="sxs-lookup"><span data-stu-id="24b5e-223">Connect a USB Drive to your PC.</span></span> <span data-ttu-id="24b5e-224">選擇 [ **中心2秒** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-224">Choose **Hub 2S** and then select **Next**.</span></span>

   ![選取 [USB]](images/shm-fig13.png)
   
2. <span data-ttu-id="24b5e-226">選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="24b5e-226">Select **Build**.</span></span>

   ![選取組建](images/shm-fig14.png)

3. <span data-ttu-id="24b5e-228">捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。</span><span class="sxs-lookup"><span data-stu-id="24b5e-228">Capture a screenshot of this page and then select **End**.</span></span> <span data-ttu-id="24b5e-229">您的 SEMM 套件現已準備就緒，且包含 SEMM 套件 **DfciUpdate. dfi** 和 SEMM thumbprint 的文字檔 (憑證的指紋) 中的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="24b5e-229">Your SEMM package is now ready and contains the SEMM package **DfciUpdate.dfi** and a text file with the SEMM thumbprint (the last two characters of the certificate’s thumbprint).</span></span>

   ![選取 [結束]](images/shm-fig15.png)
   
4. <span data-ttu-id="24b5e-231">儲存憑證指紋的最後2個字元，這是您在 Surface Hub 2 上套用套件時，必須啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="24b5e-231">Save the certificate thumbprint’s last 2 characters, which is required to activate SEMM when you apply the package on Surface Hub 2S.</span></span>

### <span data-ttu-id="24b5e-232">準備包含 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式與固件的 USB 快閃記憶體磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="24b5e-232">Prepare USB flash drive containing Windows 10 image, SEMM package, and Surface Hub 2 Drivers and Firmware</span></span>

<span data-ttu-id="24b5e-233">您可以使用下列其中一個選項，在版本1903或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：</span><span class="sxs-lookup"><span data-stu-id="24b5e-233">You can install a Windows 10 Pro or Enterprise image (version 1903 or later) using one of the following options:</span></span>

- <span data-ttu-id="24b5e-234">您目前的影像解決方案。</span><span class="sxs-lookup"><span data-stu-id="24b5e-234">Your current imaging solution.</span></span>

- <span data-ttu-id="24b5e-235">[Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 可讓您建立可引導的 windows 10 影像，其中包含所有目前的 windows 10 更新、Office、您選擇的其他 app，以及所需的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="24b5e-235">[Surface Deployment Accelerator](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) lets you create a bootable Windows 10 image which can include all of the current Windows 10 updates, Office, other apps of your choice, as well as the required drivers and firmware.</span></span> 

- <span data-ttu-id="24b5e-236">具有 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機，接著  [在 Surface Hub 2 上安裝 Windows 10 專業版和 Enterprise 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="24b5e-236">USB flash drive with Windows 10 Pro or Enterprise image, followed by installing  [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
<span data-ttu-id="24b5e-237">此程式說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後在 Surface Hub 2 上新增適用于 Windows 10 專業版與 Enterprise 的 SEMM 套件檔案和驅動程式及固件。MSI 檔案。</span><span class="sxs-lookup"><span data-stu-id="24b5e-237">This procedure describes creating a USB flash drive from installation media and then adding the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 .MSI file.</span></span> <span data-ttu-id="24b5e-238">如果您使用的是其他部署方法，請繼續閱讀下列章節： [更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)。</span><span class="sxs-lookup"><span data-stu-id="24b5e-238">If you’re using other deployment methods, proceed to the following section: [Update UEFI on Surface Hub 2S to enable OS migration](#update-uefi-on-surface-hub-2s-to-enable-os-migration).</span></span>

> [!NOTE]
> <span data-ttu-id="24b5e-239">安裝之後，您將需要 Windows 10 專業版或 Windows 10 Enterprise 的有效授權。</span><span class="sxs-lookup"><span data-stu-id="24b5e-239">Once installed, you will need a valid license for Windows 10 Pro or Windows 10 Enterprise.</span></span>

1. <span data-ttu-id="24b5e-240">若要建立 Windows 10 專業版安裝，請依照 [下載 windows 10](https://www.microsoft.com/software-download/windows10) 頁面上使用 **媒體建立** 工具的指示進行。</span><span class="sxs-lookup"><span data-stu-id="24b5e-240">To create a Windows 10 Pro installation, follow the instructions on the [Download Windows 10](https://www.microsoft.com/software-download/windows10) page for using the **Media Creation** tool.</span></span> <span data-ttu-id="24b5e-241">若要下載 Windows 10 企業版，請移至 [Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。</span><span class="sxs-lookup"><span data-stu-id="24b5e-241">To download Windows 10 Enterprise, go to the [Microsoft Volume Licensing Service Center.](https://www.microsoft.com/licensing/servicecenter/default.aspx).</span></span>

2. <span data-ttu-id="24b5e-242">插入新的 **USB 儲存** 空間磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="24b5e-242">Insert a new **USB storage** drive.</span></span> <span data-ttu-id="24b5e-243">啟動 **媒體建立** 工具，選取 [ **建立安裝媒體** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-243">Launch the **Media Creation** tool, select **Create installation media** and then select **Next**.</span></span>

   ![建立安裝媒體](images/shm-fig16.png)
   
3. <span data-ttu-id="24b5e-245">選取 [語言]、[Windows 10] 和 [64 (x64) ，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-245">Select language, Windows 10, and 64-bit (x64) and then select **Next**.</span></span>

   ![選取 [語言]、[Windows 10] 和 [64 位] & 選取 [下一步]](images/shm-fig17.png)
   
4. <span data-ttu-id="24b5e-247">選取 [ **USB 快閃磁碟機** ]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-247">Select **USB flash drive** and select **Next**.</span></span>

   ![選取 [USB 快閃磁碟機]，然後選取 [下一步]](images/shm-fig18.png)
   
5. <span data-ttu-id="24b5e-249">下載完成後，請選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-249">When the download completes, select **Finish**.</span></span>

   ![選取 [完成]](images/shm-fig19.png)
   
6. <span data-ttu-id="24b5e-251">在 Surface Hub ( 2 上複製 Windows 10 專業版與企業版的 SEMM 套件檔案和驅動程式及固件。MSI 檔案) 至 USB 快閃記憶體磁片磁碟機的根目錄 (**BOOTME**) 包含您的 Windows 10 影像。</span><span class="sxs-lookup"><span data-stu-id="24b5e-251">Copy the SEMM package files and Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (.MSI file) to the ROOT of the USB flash drive (**BOOTME**) containing your Windows 10 image.</span></span> <span data-ttu-id="24b5e-252">BOOTME USB 磁片磁碟機包含：</span><span class="sxs-lookup"><span data-stu-id="24b5e-252">BOOTME USB drive contains:</span></span>

    - <span data-ttu-id="24b5e-253">您的 Windows 10 可引導影像</span><span class="sxs-lookup"><span data-stu-id="24b5e-253">Your Windows 10 bootable image</span></span>
    - <span data-ttu-id="24b5e-254">SEMM 套件檔案 (複製到 USB 磁片磁碟機的根目錄) </span><span class="sxs-lookup"><span data-stu-id="24b5e-254">SEMM package files (copied to the root of the USB drive)</span></span>
        - <span data-ttu-id="24b5e-255">DfciUpdate.dfi</span><span class="sxs-lookup"><span data-stu-id="24b5e-255">DfciUpdate.dfi</span></span>
        - <span data-ttu-id="24b5e-256">含有 SEMM 指紋的文字檔。</span><span class="sxs-lookup"><span data-stu-id="24b5e-256">Text file with the SEMM thumbprint.</span></span> <span data-ttu-id="24b5e-257">在此範例中 (： SurfaceUEFI_2020Aug25_1058.txt。</span><span class="sxs-lookup"><span data-stu-id="24b5e-257">(In this example: SurfaceUEFI_2020Aug25_1058.txt.</span></span> <span data-ttu-id="24b5e-258">自動產生的日期時間戳記會對應到您使用 Surface UEFI 設定檔建立檔案的日期。 ) </span><span class="sxs-lookup"><span data-stu-id="24b5e-258">The auto-generated date timestamp corresponds to the date that you created the file using Surface UEFI Configurator.)</span></span>
    - <span data-ttu-id="24b5e-259">Surface Hub 2 上的 Windows 10 專業版與企業版的驅動程式和固件 ( # A0) </span><span class="sxs-lookup"><span data-stu-id="24b5e-259">Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi)</span></span>

### <span data-ttu-id="24b5e-260">更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移</span><span class="sxs-lookup"><span data-stu-id="24b5e-260">Update UEFI on Surface Hub 2S to enable OS migration</span></span>

1. <span data-ttu-id="24b5e-261">將您的 **BOOTME** 磁片磁碟機插入 Surface Hub 2 的 USB-A 埠。</span><span class="sxs-lookup"><span data-stu-id="24b5e-261">Insert your **BOOTME** drive into the USB-A port on the Surface Hub 2S.</span></span>

2. <span data-ttu-id="24b5e-262">若要引導至 UEFI：</span><span class="sxs-lookup"><span data-stu-id="24b5e-262">To boot into UEFI:</span></span>

   1. <span data-ttu-id="24b5e-263">第一次關閉 () Surface Hub 2 的關閉電源。</span><span class="sxs-lookup"><span data-stu-id="24b5e-263">First power off (shutdown) your Surface Hub 2S.</span></span>
   1. <span data-ttu-id="24b5e-264">按住 [ **音量 +** ]，然後按下再放開 [ **電源** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="24b5e-264">Press and hold **Volume +** and then press and release the **Power** button.</span></span>
   1. <span data-ttu-id="24b5e-265">保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。</span><span class="sxs-lookup"><span data-stu-id="24b5e-265">Keep holding **Volume +** until the UEFI menu appears.</span></span>
   
      ![保留 holdling 的音量 +，直到 UEFI 功能表出現為止](images/shm-fig20.png)
      
3. <span data-ttu-id="24b5e-267">當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (強烈建議) ）。</span><span class="sxs-lookup"><span data-stu-id="24b5e-267">When the device restarts, enter the UEFI password you created earlier, if applicable (strongly recommended).</span></span>

   ![裝置重新開機後，請輸入您的 UEFI paassword](images/shm-fig22.png)
   
4. <span data-ttu-id="24b5e-269">在 UEFI 功能表中，選取**Management**[  >  **從 USB 安裝**管理元件]。</span><span class="sxs-lookup"><span data-stu-id="24b5e-269">In the UEFI menu, select **Management** > **Install from USB**.</span></span>

   ![選取 [管理] & 從 USB 安裝](images/shm-fig21.png)
   
5. <span data-ttu-id="24b5e-271">選取 [ **立即重新開機**]，如下所示。</span><span class="sxs-lookup"><span data-stu-id="24b5e-271">Select **Restart now**, as shown below.</span></span> <span data-ttu-id="24b5e-272">裝置將會重新開機，並在畫面中間顯示白色4方形標誌，然後將它關閉。</span><span class="sxs-lookup"><span data-stu-id="24b5e-272">The device will reboot and display the white 4-square logo in the middle of screen and then it will shut down.</span></span>

   ![選取 [立即重新開機]](images/shm-fig25.png)
   
6. <span data-ttu-id="24b5e-274">按下並放開電源按鈕，會顯示紅色畫面，提示您啟用 Surface Enterprise 管理模式。</span><span class="sxs-lookup"><span data-stu-id="24b5e-274">Press and release the power button, a red screen will display prompting you to activate Surface Enterprise Management Mode.</span></span> 

7. <span data-ttu-id="24b5e-275">輸入您的兩個字元的 **憑證指紋**，您的 **UEFI 設定密碼** ，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="24b5e-275">Enter your two-character **certificate thumbprint**, your **UEFI settings password** and then select **OK**.</span></span>

   ![輸入2個字元的憑證指紋](images/shm-fig23.png)
 
   > [!NOTE]
   > <span data-ttu-id="24b5e-277">一旦您在裝置上啟用 SEMM，就會套用新的 UEFI 設定 **EnableOSMigration** 。</span><span class="sxs-lookup"><span data-stu-id="24b5e-277">Once you activate SEMM on your device, the new UEFI setting **EnableOSMigration** is applied.</span></span> <span data-ttu-id="24b5e-278">您將無法再存取 Windows 10 小組，必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="24b5e-278">You will no longer be able to access Windows 10 Team and must proceed to the next step and install Windows 10 Pro or Windows 10 Enterprise.</span></span> 

8. <span data-ttu-id="24b5e-279">裝置將會重新開機，在畫面中間顯示白色4方形標誌，然後再按一次將它關閉</span><span class="sxs-lookup"><span data-stu-id="24b5e-279">The device will reboot, display the white 4-square logo in the middle of the screen, and then again it will shut down</span></span>

### <span data-ttu-id="24b5e-280">安裝 Windows 10 專業版或企業版</span><span class="sxs-lookup"><span data-stu-id="24b5e-280">Install Windows 10 Pro or Enterprise</span></span>

1. <span data-ttu-id="24b5e-281">如果您的可引導 Windows 10 專業版或企業版磁片磁碟機不在 Surface Hub 2 USB-A 埠中，請將它立即插入，然後按下再放開電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="24b5e-281">If your bootable Windows 10 Pro or Enterprise drive is not already in the Surface Hub 2 USB-A port, insert it now and then press and release the power button.</span></span>

2. <span data-ttu-id="24b5e-282">裝置將會啟動，您會在畫面中間看到白色的4方形，然後您會在白色四個方形標誌下方看到旋轉的圓形。</span><span class="sxs-lookup"><span data-stu-id="24b5e-282">The device will start, you will see the white 4-square in the middle of the screen, and then you will see a spinning circle below the white four-square logo.</span></span>

3. <span data-ttu-id="24b5e-283">如果裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置電源 (拔下電源線，然後再插回) 。</span><span class="sxs-lookup"><span data-stu-id="24b5e-283">If the device does not automatically boot to the USB drive, power off the device (unplug the power cord and plug it back in).</span></span> <span data-ttu-id="24b5e-284">重新插入電源線之後，裝置會在幾秒後啟動至畫面中間的白色4方形標誌，或者，您可以按下並放開電源按鈕來重新開啟裝置。</span><span class="sxs-lookup"><span data-stu-id="24b5e-284">After plugging the power cord back in, the device should boot after a few seconds to the white 4-square logo in the middle of screen, or you can press and release the power button to turn the device back on.</span></span> <span data-ttu-id="24b5e-285">在螢幕中間看到4方塊標誌之後，按住 [音量] 按鈕，直到您看到位於白色四個方形標誌下方的旋轉圓形。</span><span class="sxs-lookup"><span data-stu-id="24b5e-285">Immediately after you see the 4-square logo in the middle of the screen, press and hold the volume down button until you see the spinning circle below the white four-square logo.</span></span>
 
   ![從 USB 啟動至 Windows 10](images/shm-fig26.png)
   
4. <span data-ttu-id="24b5e-287">當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或企業版 (版本1903或) 更新版本。</span><span class="sxs-lookup"><span data-stu-id="24b5e-287">When the out of box experience (OOBE) setup launches, follow the instructions to install Windows 10 Pro or Enterprise (version 1903 or later).</span></span>

### <span data-ttu-id="24b5e-288">安裝 Surface Hub 2 驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="24b5e-288">Install Surface Hub 2 drivers and firmware</span></span>

 - <span data-ttu-id="24b5e-289">為了確保您的裝置擁有所有最新的更新和驅動程式，請 [在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 Enterprise 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</span><span class="sxs-lookup"><span data-stu-id="24b5e-289">To ensure your device has all the latest updates and drivers, install [Drivers and Firmware for Windows 10 Pro and Enterprise on Surface Hub 2](https://www.microsoft.com/download/details.aspx?id=101974).</span></span>
 
### <span data-ttu-id="24b5e-290">後續步驟</span><span class="sxs-lookup"><span data-stu-id="24b5e-290">Next steps</span></span>

<span data-ttu-id="24b5e-291">若要將 Surface Hub 2 完整設定為個人生產力裝置，請參閱在 [Surface Hub 2 上設定 Windows 10 專業版或企業版](surface-hub-2-post-install.md)。</span><span class="sxs-lookup"><span data-stu-id="24b5e-291">To fully configure Surface Hub 2S as a personal productivity device, see [Configure Windows 10 Pro or Enterprise on Surface Hub 2](surface-hub-2-post-install.md).</span></span>

> [!NOTE]
><span data-ttu-id="24b5e-292">如果遵循這份檔中所述的步驟無法將您的裝置遷移至 Windows 10 專業版或 Surface Hub 2 Enterprise，請與 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)聯繫。</span><span class="sxs-lookup"><span data-stu-id="24b5e-292">If following the steps outlined in this document is unsuccessful in migrating your device to Windows 10 Pro or Enterprise for Surface Hub 2, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

### <span data-ttu-id="24b5e-293">回退至 Windows 10 團隊</span><span class="sxs-lookup"><span data-stu-id="24b5e-293">Rolling back to Windows 10 Team</span></span>

<span data-ttu-id="24b5e-294">如果您想要將裝置還原至 Windows 10 小組，請參閱 [重設及恢復 Surface Hub 2 秒](surface-hub-2s-recover-reset.md)</span><span class="sxs-lookup"><span data-stu-id="24b5e-294">If you would Like to restore your device to Windows 10 Team, refer to [Reset and recovery for Surface Hub 2S](surface-hub-2s-recover-reset.md)</span></span>

## <span data-ttu-id="24b5e-295">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="24b5e-295">Version history</span></span>

| <span data-ttu-id="24b5e-296">版本</span><span class="sxs-lookup"><span data-stu-id="24b5e-296">Version</span></span> | <span data-ttu-id="24b5e-297">日期</span><span class="sxs-lookup"><span data-stu-id="24b5e-297">Date</span></span>               | <span data-ttu-id="24b5e-298">描述</span><span class="sxs-lookup"><span data-stu-id="24b5e-298">Description</span></span>                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="24b5e-299">向量.</span><span class="sxs-lookup"><span data-stu-id="24b5e-299">v.</span></span> <span data-ttu-id="24b5e-300">1.2</span><span class="sxs-lookup"><span data-stu-id="24b5e-300">1.2</span></span>  | <span data-ttu-id="24b5e-301">2020年9月29日</span><span class="sxs-lookup"><span data-stu-id="24b5e-301">September 29, 2020</span></span> | <span data-ttu-id="24b5e-302">每個可用性意見反應的其他更新。</span><span class="sxs-lookup"><span data-stu-id="24b5e-302">Miscellaneous updates per usability feedback.</span></span>                                                        |
| <span data-ttu-id="24b5e-303">向量.</span><span class="sxs-lookup"><span data-stu-id="24b5e-303">v.</span></span> <span data-ttu-id="24b5e-304">1.1</span><span class="sxs-lookup"><span data-stu-id="24b5e-304">1.1</span></span>  | <span data-ttu-id="24b5e-305">2020年9月15日</span><span class="sxs-lookup"><span data-stu-id="24b5e-305">September 15, 2020</span></span> | <span data-ttu-id="24b5e-306">在簡介中放入其他記事，說明安裝新作業系統的授權需求。</span><span class="sxs-lookup"><span data-stu-id="24b5e-306">Placed additional note in the Introduction clarifying licensing requirements for installing a new OS.</span></span> |
| <span data-ttu-id="24b5e-307">向量.</span><span class="sxs-lookup"><span data-stu-id="24b5e-307">v.</span></span> <span data-ttu-id="24b5e-308">1.0</span><span class="sxs-lookup"><span data-stu-id="24b5e-308">1.0</span></span>  | <span data-ttu-id="24b5e-309">2020年9月1日</span><span class="sxs-lookup"><span data-stu-id="24b5e-309">September 1, 2020</span></span>  | <span data-ttu-id="24b5e-310">新文章。</span><span class="sxs-lookup"><span data-stu-id="24b5e-310">New article.</span></span>                                                                                           |
