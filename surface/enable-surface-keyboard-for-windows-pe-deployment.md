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
ms.openlocfilehash: d7ae6fc434f77cad86e73f111243968493de4ff2
ms.sourcegitcommit: e6224f81f8efb6ac862afec0e60e3ddb182e9e6f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/22/2020
ms.locfileid: "11247305"
---
# <span data-ttu-id="f7017-104">如何在 MDT 部署期間啟用 Surface 膝上型電腦鍵盤</span><span class="sxs-lookup"><span data-stu-id="f7017-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="f7017-105">本文討論使用 Microsoft 部署工具組 (MDT) 的部署方法。</span><span class="sxs-lookup"><span data-stu-id="f7017-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="f7017-106">您也可以將此資訊套用到其他部署方法。</span><span class="sxs-lookup"><span data-stu-id="f7017-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="f7017-107">在大部分的 Surface 裝置上，鍵盤應該在 (LTI) 的精簡觸控安裝期間運作。</span><span class="sxs-lookup"><span data-stu-id="f7017-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="f7017-108">不過，Surface 膝上型電腦需要一些其他驅動程式，才能啟用鍵盤。</span><span class="sxs-lookup"><span data-stu-id="f7017-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="f7017-109">針對 Surface 膝上型電腦 (1 Gen) 和 Surface 膝上型電腦2裝置，您必須準備可讓您指定使用鍵盤驅動程式的資料夾結構和選取設定檔，以便在 Windows 預先安裝環境 (Windows PE) 階段（在 LTI 中）使用。</span><span class="sxs-lookup"><span data-stu-id="f7017-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="f7017-110">如需此資料夾結構的詳細資訊，請參閱 [使用 MDT 部署 Windows 10 影像：步驟5：準備驅動程式儲存庫](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。</span><span class="sxs-lookup"><span data-stu-id="f7017-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f7017-111">如果您要將 Windows 10 影像部署到已預先安裝 Windows 10 的 Surface 膝上型電腦，請參閱 KB [4032347：在 s 模式中，將 windows 部署到已預先安裝 windows 10 的 surface 裝置時會發生問題](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)。</span><span class="sxs-lookup"><span data-stu-id="f7017-111">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="f7017-112">若要將鍵盤驅動程式新增至選取設定檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="f7017-112">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="f7017-113">從適當的位置下載最新的 Surface 膝上型電腦 MSI 檔案：</span><span class="sxs-lookup"><span data-stu-id="f7017-113">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="f7017-114">Surface 膝上型電腦 (1 Gen) 驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="f7017-114">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="f7017-115">Surface 膝上型電腦2驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="f7017-115">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="f7017-116">含英特爾處理器驅動程式和固件的 Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="f7017-116">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="f7017-117">將 Surface 膝上型電腦 MSI 檔案的內容解壓至資料夾，您可以輕鬆地找到 (例如 c：\ surface_laptop_drivers) 。</span><span class="sxs-lookup"><span data-stu-id="f7017-117">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="f7017-118">若要解壓縮內容，請開啟提升許可權的命令提示字元視窗，然後執行下列範例中的命令：</span><span class="sxs-lookup"><span data-stu-id="f7017-118">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="f7017-119">開啟部署工作臺，然後展開 [ **部署共用** ] 節點和您的部署共用，然後流覽至 [ **WindowsPEX64** ] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f7017-119">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![在部署工作臺中顯示 WindowsPEX64 資料夾位置的影像](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="f7017-121">以滑鼠右鍵按一下 [ **WindowsPEX64** ] 資料夾，然後選取 [匯 **入驅動程式**]。</span><span class="sxs-lookup"><span data-stu-id="f7017-121">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>
5. <span data-ttu-id="f7017-122">依照 [匯入驅動程式] 嚮導中的指示，將驅動程式資料夾匯入 [WindowsPEX64] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f7017-122">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

> [!NOTE]
>  <span data-ttu-id="f7017-123">檢查已下載的 MSI 套件，以判斷格式和目錄結構。</span><span class="sxs-lookup"><span data-stu-id="f7017-123">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="f7017-124">目錄結構將會以 SurfacePlatformInstaller (較舊的 MSI 檔案) 或 SurfaceUpdate (較新的 MSI 檔案，) 視 MSI 的發行時間而定。</span><span class="sxs-lookup"><span data-stu-id="f7017-124">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

<span data-ttu-id="f7017-125">若要支援 Surface 膝上型電腦 (1 Gen) ，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="f7017-125">To support Surface Laptop (1st Gen), import the following folders:</span></span>

 - <span data-ttu-id="f7017-126">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-126">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="f7017-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-127">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
 - <span data-ttu-id="f7017-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-128">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="f7017-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="f7017-129">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="f7017-130">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="f7017-130">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="f7017-131">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-131">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="f7017-132">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-132">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
- <span data-ttu-id="f7017-133">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-133">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
- <span data-ttu-id="f7017-134">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f7017-134">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="f7017-135">若要支援 Surface 膝上型電腦2，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="f7017-135">To support Surface Laptop 2, import the following folders:</span></span>

 - <span data-ttu-id="f7017-136">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-136">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
 - <span data-ttu-id="f7017-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-137">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
 - <span data-ttu-id="f7017-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-138">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
 - <span data-ttu-id="f7017-139">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="f7017-139">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
 - <span data-ttu-id="f7017-140">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="f7017-140">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
 - <span data-ttu-id="f7017-141">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="f7017-141">SurfacePlatformInstaller\Drivers\System\UART</span></span>
 - <span data-ttu-id="f7017-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="f7017-142">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

<span data-ttu-id="f7017-143">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="f7017-143">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

- <span data-ttu-id="f7017-144">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-144">SurfaceUpdate\SerialIOGPIO</span></span>
- <span data-ttu-id="f7017-145">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f7017-145">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="f7017-146">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f7017-146">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="f7017-147">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f7017-147">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="f7017-148">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f7017-148">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="f7017-149">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f7017-149">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="f7017-150">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f7017-150">SurfaceUpdate\Itouch</span></span>

 
<span data-ttu-id="f7017-151">若要支援含英特爾處理器的 Surface 膝上型電腦3，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="f7017-151">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

- <span data-ttu-id="f7017-152">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-152">SurfaceUpdate\IclSerialIOGPIO</span></span>
- <span data-ttu-id="f7017-153">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f7017-153">SurfaceUpdate\IclSerialIOI2C</span></span>
- <span data-ttu-id="f7017-154">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f7017-154">SurfaceUpdate\IclSerialIOSPI</span></span>
- <span data-ttu-id="f7017-155">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f7017-155">SurfaceUpdate\IclSerialIOUART</span></span>
- <span data-ttu-id="f7017-156">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f7017-156">SurfaceUpdate\SurfaceHidMini</span></span>
- <span data-ttu-id="f7017-157">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f7017-157">SurfaceUpdate\SurfaceSerialHub</span></span>
- <span data-ttu-id="f7017-158">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="f7017-158">SurfaceUpdate\SurfaceHotPlug</span></span>
- <span data-ttu-id="f7017-159">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f7017-159">SurfaceUpdate\Itouch</span></span>

<span data-ttu-id="f7017-160">匯入下列資料夾將在 Surface 膝上型電腦3的 PE 中啟用完整的鍵盤、軌跡板和觸控功能。</span><span class="sxs-lookup"><span data-stu-id="f7017-160">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

- <span data-ttu-id="f7017-161">IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-161">IclSerialIOGPIO</span></span>
- <span data-ttu-id="f7017-162">IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f7017-162">IclSerialIOI2C</span></span>
- <span data-ttu-id="f7017-163">IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f7017-163">IclSerialIOSPI</span></span>
- <span data-ttu-id="f7017-164">IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f7017-164">IclSerialIOUART</span></span>
- <span data-ttu-id="f7017-165">itouch</span><span class="sxs-lookup"><span data-stu-id="f7017-165">itouch</span></span>
- <span data-ttu-id="f7017-166">IclChipset</span><span class="sxs-lookup"><span data-stu-id="f7017-166">IclChipset</span></span>
- <span data-ttu-id="f7017-167">IclChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="f7017-167">IclChipsetLPSS</span></span>
- <span data-ttu-id="f7017-168">IclChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="f7017-168">IclChipsetNorthpeak</span></span>
- <span data-ttu-id="f7017-169">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="f7017-169">ManagementEngine</span></span>
- <span data-ttu-id="f7017-170">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="f7017-170">SurfaceAcpiNotify</span></span>
- <span data-ttu-id="f7017-171">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="f7017-171">SurfaceBattery</span></span>
- <span data-ttu-id="f7017-172">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="f7017-172">SurfaceDockIntegration</span></span>
- <span data-ttu-id="f7017-173">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f7017-173">SurfaceHidMini</span></span>
- <span data-ttu-id="f7017-174">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="f7017-174">SurfaceHotPlug</span></span>
- <span data-ttu-id="f7017-175">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="f7017-175">SurfaceIntegration</span></span>
- <span data-ttu-id="f7017-176">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f7017-176">SurfaceSerialHub</span></span>
- <span data-ttu-id="f7017-177">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="f7017-177">SurfaceService</span></span>
- <span data-ttu-id="f7017-178">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="f7017-178">SurfaceStorageFwUpdate</span></span>


    > [!NOTE]
    >  <span data-ttu-id="f7017-179">檢查已下載的 MSI 套件，以判斷格式和目錄結構。</span><span class="sxs-lookup"><span data-stu-id="f7017-179">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="f7017-180">目錄結構將會以 SurfacePlatformInstaller (較舊的 MSI 檔案) 或 SurfaceUpdate (較新的 MSI 檔案，) 視 MSI 的發行時間而定。</span><span class="sxs-lookup"><span data-stu-id="f7017-180">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="f7017-181">若要支援 Surface 膝上型電腦 (1 Gen) ，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="f7017-181">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="f7017-182">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-182">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="f7017-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-183">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="f7017-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-184">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="f7017-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="f7017-185">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="f7017-186">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="f7017-186">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="f7017-187">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-187">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="f7017-188">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-188">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="f7017-189">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-189">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="f7017-190">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f7017-190">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="f7017-191">若要支援 Surface 膝上型電腦2，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="f7017-191">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="f7017-192">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-192">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="f7017-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-193">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="f7017-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="f7017-194">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="f7017-195">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="f7017-195">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="f7017-196">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="f7017-196">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="f7017-197">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="f7017-197">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="f7017-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="f7017-198">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="f7017-199">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="f7017-199">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="f7017-200">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-200">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="f7017-201">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f7017-201">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="f7017-202">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f7017-202">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="f7017-203">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f7017-203">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="f7017-204">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f7017-204">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="f7017-205">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f7017-205">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="f7017-206">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f7017-206">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="f7017-207">若要支援含英特爾處理器的 Surface 膝上型電腦3，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="f7017-207">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="f7017-208">SurfaceUpdate\IclSerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="f7017-208">SurfaceUpdate\IclSerialIOGPIO</span></span>
    - <span data-ttu-id="f7017-209">SurfaceUpdate\IclSerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="f7017-209">SurfaceUpdate\IclSerialIOI2C</span></span>
    - <span data-ttu-id="f7017-210">SurfaceUpdate\IclSerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="f7017-210">SurfaceUpdate\IclSerialIOSPI</span></span>
    - <span data-ttu-id="f7017-211">SurfaceUpdate\IclSerialIOUART</span><span class="sxs-lookup"><span data-stu-id="f7017-211">SurfaceUpdate\IclSerialIOUART</span></span>
    - <span data-ttu-id="f7017-212">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="f7017-212">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="f7017-213">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="f7017-213">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="f7017-214">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="f7017-214">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="f7017-215">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="f7017-215">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="f7017-216">針對含英特爾處理器的 Surface 膝上型電腦3，模型為 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="f7017-216">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="f7017-217">剩餘的 Surface 膝上型電腦驅動程式位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦 3] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f7017-217">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="f7017-218">確認 WindowsPEX64 資料夾現在包含已匯入的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="f7017-218">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="f7017-219">該資料夾應如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7017-219">The folder should resemble the following:</span></span>  

   ![在部署工作臺的 [WindowsPEX64] 資料夾中顯示新匯入驅動程式的影像](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="f7017-221">設定使用 WindowsPEX64 資料夾的選取設定檔。</span><span class="sxs-lookup"><span data-stu-id="f7017-221">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="f7017-222">選取設定檔應如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7017-222">The selection profile should resemble the following:</span></span>  

   ![顯示選取為選取設定檔一部分之 WindowsPEX64 資料夾的影像](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="f7017-224">將 MDT 部署共用的 Windows PE 屬性設定為使用新的選取設定檔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f7017-224">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="f7017-225">針對 [ **平臺**]，選取 [ **x64**]。</span><span class="sxs-lookup"><span data-stu-id="f7017-225">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="f7017-226">針對 [ **選取設定檔**]，選取新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="f7017-226">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="f7017-227">選取 **[包含選取設定檔中的所有驅動程式**]。</span><span class="sxs-lookup"><span data-stu-id="f7017-227">Select **Include all drivers from the selection profile**.</span></span>
   
   ![顯示 MDT 部署共用的 Windows PE 屬性的圖像](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="f7017-229">使用選取設定檔或 **DriverGroup001** 變數，確認您已設定剩餘的 Surface 膝上型電腦驅動程式。</span><span class="sxs-lookup"><span data-stu-id="f7017-229">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="f7017-230">針對 Surface 膝上型電腦 (1 Gen) ，模型是 **Surface 膝上型電腦**。</span><span class="sxs-lookup"><span data-stu-id="f7017-230">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="f7017-231">剩餘的 Surface 膝上型電腦驅動程式應該位於 \MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦資料夾中，如以下清單所示。</span><span class="sxs-lookup"><span data-stu-id="f7017-231">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="f7017-232">如果是 Surface 膝上型電腦2，則模型為 **Surface 膝上型電腦 2**。</span><span class="sxs-lookup"><span data-stu-id="f7017-232">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="f7017-233">剩餘的 Surface 膝上型電腦驅動程式應該位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型 2] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f7017-233">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="f7017-234">針對含英特爾處理器的 Surface 膝上型電腦3，模型為 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="f7017-234">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="f7017-235">剩餘的 Surface 膝上型電腦驅動程式位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦 3] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="f7017-235">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![在部署工作臺的 [Surface 膝上型電腦] 資料夾中，顯示一般 Surface 膝上型電腦 (第一個 Gen) 驅動程式的影像](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="f7017-237">將 MDT 部署共用設定為使用新的選取設定檔和相關設定之後，請按照 [使用 MDT 部署 Windows 10 映射](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)中的說明，繼續進行部署程式：建立部署任務序列。</span><span class="sxs-lookup"><span data-stu-id="f7017-237">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
