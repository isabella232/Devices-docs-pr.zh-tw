---
title: 如何在 MDT 部署期間啟用 Surface 膝上型電腦鍵盤
description: 當您使用 MDT 將 Windows 10 部署到 Surface 膝上型電腦時，您必須匯入鍵盤驅動程式，才能在 Windows PE 環境中使用。
keywords: windows 10 surface、自動化、自訂、mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831303"
---
# <span data-ttu-id="02cae-104">如何在 MDT 部署期間啟用 Surface 膝上型電腦鍵盤</span><span class="sxs-lookup"><span data-stu-id="02cae-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="02cae-105">本文討論使用 Microsoft 部署工具套件（MDT）的部署方法。</span><span class="sxs-lookup"><span data-stu-id="02cae-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="02cae-106">您也可以將此資訊套用到其他部署方法。</span><span class="sxs-lookup"><span data-stu-id="02cae-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="02cae-107">在大多數類型的 Surface 裝置上，鍵盤應該在精簡的觸控安裝（LTI）期間運作。</span><span class="sxs-lookup"><span data-stu-id="02cae-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="02cae-108">不過，Surface 膝上型電腦需要一些其他驅動程式，才能啟用鍵盤。</span><span class="sxs-lookup"><span data-stu-id="02cae-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="02cae-109">針對 Surface 膝上型電腦（1 Gen）和 Surface 膝上型電腦2裝置，您必須準備可讓您指定鍵盤驅動程式的資料夾結構和選取設定檔，以便在 LTI 的 Windows 預先安裝環境（Windows PE）階段使用。</span><span class="sxs-lookup"><span data-stu-id="02cae-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="02cae-110">如需此資料夾結構的詳細資訊，請參閱[使用 MDT 部署 Windows 10 影像：步驟5：準備驅動程式儲存庫](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。</span><span class="sxs-lookup"><span data-stu-id="02cae-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!NOTE]
> <span data-ttu-id="02cae-111">由於驅動程式衝突，目前不支援在相同的 Windows PE 啟動實例中新增 Surface 膝上型電腦2和 Surface 膝上型電腦3的鍵盤驅動程式。請改為使用個別的實例。</span><span class="sxs-lookup"><span data-stu-id="02cae-111">It is currently not supported to add Surface Laptop 2 and Surface Laptop 3 keyboard drivers in the same Windows PE boot instance due to a driver conflict; use separate instances instead.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02cae-112">如果您要將 Windows 10 影像部署到已預先安裝 Windows 10 的 Surface 膝上型電腦，請參閱 KB [4032347：在 s 模式中，將 windows 部署到已預先安裝 windows 10 的 surface 裝置時會發生問題](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)。</span><span class="sxs-lookup"><span data-stu-id="02cae-112">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="02cae-113">若要將鍵盤驅動程式新增至選取設定檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="02cae-113">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="02cae-114">從適當的位置下載最新的 Surface 膝上型電腦 MSI 檔案：</span><span class="sxs-lookup"><span data-stu-id="02cae-114">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="02cae-115">Surface 膝上型電腦（第1代）驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="02cae-115">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="02cae-116">Surface 膝上型電腦2驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="02cae-116">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="02cae-117">含英特爾處理器驅動程式和固件的 Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="02cae-117">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="02cae-118">將 Surface 膝上型電腦 MSI 檔案的內容解壓至您可以輕鬆找到的資料夾（例如，c：\ surface_laptop_drivers）。</span><span class="sxs-lookup"><span data-stu-id="02cae-118">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="02cae-119">若要解壓縮內容，請開啟提升許可權的命令提示字元視窗，然後執行下列範例中的命令：</span><span class="sxs-lookup"><span data-stu-id="02cae-119">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="02cae-120">開啟部署工作臺，然後展開 [**部署共用**] 節點和您的部署共用，然後流覽至 [ **WindowsPEX64** ] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="02cae-120">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![在部署工作臺中顯示 WindowsPEX64 資料夾位置的影像](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="02cae-122">以滑鼠右鍵按一下 [ **WindowsPEX64** ] 資料夾，然後選取 [匯**入驅動程式**]。</span><span class="sxs-lookup"><span data-stu-id="02cae-122">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="02cae-123">依照 [匯入驅動程式] 嚮導中的指示，將驅動程式資料夾匯入 [WindowsPEX64] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="02cae-123">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="02cae-124">檢查已下載的 MSI 套件，以判斷格式和目錄結構。</span><span class="sxs-lookup"><span data-stu-id="02cae-124">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="02cae-125">目錄結構會從 SurfacePlatformInstaller （較舊的 MSI 檔案）或 SurfaceUpdate （較新的 MSI 檔案）開始，視 MSI 的發行時間而定。</span><span class="sxs-lookup"><span data-stu-id="02cae-125">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="02cae-126">若要支援 Surface 膝上型電腦（第1代），請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="02cae-126">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="02cae-127">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-127">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="02cae-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-128">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="02cae-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-129">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="02cae-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="02cae-130">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="02cae-131">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="02cae-131">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="02cae-132">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-132">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="02cae-133">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-133">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="02cae-134">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-134">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="02cae-135">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="02cae-135">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="02cae-136">若要支援 Surface 膝上型電腦2，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="02cae-136">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="02cae-137">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-137">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="02cae-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-138">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="02cae-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-139">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="02cae-140">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="02cae-140">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="02cae-141">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="02cae-141">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="02cae-142">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="02cae-142">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="02cae-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="02cae-143">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="02cae-144">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="02cae-144">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="02cae-145">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-145">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="02cae-146">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="02cae-146">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="02cae-147">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="02cae-147">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="02cae-148">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="02cae-148">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="02cae-149">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="02cae-149">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="02cae-150">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="02cae-150">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="02cae-151">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="02cae-151">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="02cae-152">若要支援含英特爾處理器的 Surface 膝上型電腦3，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="02cae-152">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="02cae-153">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-153">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="02cae-154">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="02cae-154">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="02cae-155">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="02cae-155">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="02cae-156">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="02cae-156">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="02cae-157">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="02cae-157">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="02cae-158">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="02cae-158">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="02cae-159">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="02cae-159">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="02cae-160">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="02cae-160">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="02cae-161">匯入下列資料夾將在 Surface 膝上型電腦3的 PE 中啟用完整的鍵盤、軌跡板和觸控功能。</span><span class="sxs-lookup"><span data-stu-id="02cae-161">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="02cae-162">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-162">IclSerialIOGPIO</span></span>
- <span data-ttu-id="02cae-163">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="02cae-163">IclSerialIOI2C</span></span>
- <span data-ttu-id="02cae-164">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="02cae-164">IclSerialIOSPI</span></span>
- <span data-ttu-id="02cae-165">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="02cae-165">IclSerialIOUART</span></span>
- <span data-ttu-id="02cae-166">itouch</span><span class="sxs-lookup"><span data-stu-id="02cae-166">itouch</span></span>
- <span data-ttu-id="02cae-167">IclChipset</span><span class="sxs-lookup"><span data-stu-id="02cae-167">IclChipset</span></span>
- <span data-ttu-id="02cae-168">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="02cae-168">IclChipsetLPSS</span></span>
- <span data-ttu-id="02cae-169">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="02cae-169">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="02cae-170">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="02cae-170">ManagementEngine</span></span>
- <span data-ttu-id="02cae-171">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="02cae-171">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="02cae-172">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="02cae-172">SurfaceBattery</span></span>
- <span data-ttu-id="02cae-173">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="02cae-173">SurfaceDockIntegration</span></span>
- <span data-ttu-id="02cae-174">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="02cae-174">SurfaceHidMini</span></span>
- <span data-ttu-id="02cae-175">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="02cae-175">SurfaceHotPlug</span></span>
- <span data-ttu-id="02cae-176">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="02cae-176">SurfaceIntegration</span></span>
- <span data-ttu-id="02cae-177">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="02cae-177">SurfaceSerialHub</span></span>
- <span data-ttu-id="02cae-178">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="02cae-178">SurfaceService</span></span>
- <span data-ttu-id="02cae-179">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="02cae-179">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="02cae-180">檢查已下載的 MSI 套件，以判斷格式和目錄結構。</span><span class="sxs-lookup"><span data-stu-id="02cae-180">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="02cae-181">目錄結構會從 SurfacePlatformInstaller （較舊的 MSI 檔案）或 SurfaceUpdate （較新的 MSI 檔案）開始，視 MSI 的發行時間而定。</span><span class="sxs-lookup"><span data-stu-id="02cae-181">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="02cae-182">若要支援 Surface 膝上型電腦（第1代），請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="02cae-182">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="02cae-183">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-183">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="02cae-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-184">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="02cae-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-185">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="02cae-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="02cae-186">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="02cae-187">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="02cae-187">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="02cae-188">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-188">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="02cae-189">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-189">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="02cae-190">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-190">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="02cae-191">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="02cae-191">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="02cae-192">若要支援 Surface 膝上型電腦2，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="02cae-192">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="02cae-193">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-193">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="02cae-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-194">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="02cae-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="02cae-195">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="02cae-196">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="02cae-196">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="02cae-197">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="02cae-197">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="02cae-198">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="02cae-198">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="02cae-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="02cae-199">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="02cae-200">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="02cae-200">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="02cae-201">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-201">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="02cae-202">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="02cae-202">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="02cae-203">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="02cae-203">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="02cae-204">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="02cae-204">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="02cae-205">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="02cae-205">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="02cae-206">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="02cae-206">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="02cae-207">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="02cae-207">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="02cae-208">若要支援含英特爾處理器的 Surface 膝上型電腦3，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="02cae-208">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="02cae-209">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="02cae-209">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="02cae-210">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="02cae-210">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="02cae-211">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="02cae-211">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="02cae-212">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="02cae-212">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="02cae-213">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="02cae-213">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="02cae-214">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="02cae-214">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="02cae-215">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="02cae-215">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="02cae-216">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="02cae-216">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="02cae-217">針對含英特爾處理器的 Surface 膝上型電腦3，模型為 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="02cae-217">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="02cae-218">剩餘的 Surface 膝上型電腦驅動程式位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦 3] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="02cae-218">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="02cae-219">確認 WindowsPEX64 資料夾現在包含已匯入的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="02cae-219">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="02cae-220">該資料夾應如下所示：</span><span class="sxs-lookup"><span data-stu-id="02cae-220">The folder should resemble the following:</span></span>  

   ![在部署工作臺的 [WindowsPEX64] 資料夾中顯示新匯入驅動程式的影像](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="02cae-222">設定使用 WindowsPEX64 資料夾的選取設定檔。</span><span class="sxs-lookup"><span data-stu-id="02cae-222">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="02cae-223">選取設定檔應如下所示：</span><span class="sxs-lookup"><span data-stu-id="02cae-223">The selection profile should resemble the following:</span></span>  

   ![顯示選取為選取設定檔一部分之 WindowsPEX64 資料夾的影像](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="02cae-225">將 MDT 部署共用的 Windows PE 屬性設定為使用新的選取設定檔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="02cae-225">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="02cae-226">針對 [**平臺**]，選取 [ **x64**]。</span><span class="sxs-lookup"><span data-stu-id="02cae-226">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="02cae-227">針對 [**選取設定檔**]，選取新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="02cae-227">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="02cae-228">選取 **[包含選取設定檔中的所有驅動程式**]。</span><span class="sxs-lookup"><span data-stu-id="02cae-228">Select **Include all drivers from the selection profile**.</span></span>
   
   ![顯示 MDT 部署共用的 Windows PE 屬性的圖像](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="02cae-230">使用選取設定檔或**DriverGroup001**變數，確認您已設定剩餘的 Surface 膝上型電腦驅動程式。</span><span class="sxs-lookup"><span data-stu-id="02cae-230">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="02cae-231">針對 Surface 膝上型電腦（1 Gen），模型是**Surface 膝上型電腦**。</span><span class="sxs-lookup"><span data-stu-id="02cae-231">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="02cae-232">剩餘的 Surface 膝上型電腦驅動程式應該位於 \MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦資料夾中，如以下清單所示。</span><span class="sxs-lookup"><span data-stu-id="02cae-232">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="02cae-233">如果是 Surface 膝上型電腦2，則模型為**Surface 膝上型電腦 2**。</span><span class="sxs-lookup"><span data-stu-id="02cae-233">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="02cae-234">剩餘的 Surface 膝上型電腦驅動程式應該位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型 2] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="02cae-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="02cae-235">針對含英特爾處理器的 Surface 膝上型電腦3，模型為 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="02cae-235">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="02cae-236">剩餘的 Surface 膝上型電腦驅動程式位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦 3] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="02cae-236">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![在部署工作臺的 [Surface 膝上型電腦] 資料夾中顯示一般 Surface 膝上型電腦（第1代）驅動程式的影像](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="02cae-238">將 MDT 部署共用設定為使用新的選取設定檔和相關設定之後，請按照[使用 MDT 部署 Windows 10 映射](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)中的說明，繼續進行部署程式：建立部署任務序列。</span><span class="sxs-lookup"><span data-stu-id="02cae-238">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
