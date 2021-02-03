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
ms.date: 02/02/2021
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: fb51dd3785882e74c90d8b2717e4cc499d492d6f
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312059"
---
# <span data-ttu-id="0c5b9-104">如何在 MDT 部署期間啟用 Surface 膝上型電腦鍵盤</span><span class="sxs-lookup"><span data-stu-id="0c5b9-104">How to enable the Surface Laptop keyboard during MDT deployment</span></span>

<span data-ttu-id="0c5b9-105">本文討論使用 Microsoft 部署工具組 (MDT) 的部署方法。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-105">This article addresses a deployment approach that uses Microsoft Deployment Toolkit (MDT).</span></span> <span data-ttu-id="0c5b9-106">您也可以將此資訊套用到其他部署方法。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-106">You can also apply this information to other deployment methodologies.</span></span> <span data-ttu-id="0c5b9-107">在大部分的 Surface 裝置上，鍵盤應該在 (LTI) 的精簡觸控安裝期間運作。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-107">On most types of Surface devices, the keyboard should work during Lite Touch Installation (LTI).</span></span> <span data-ttu-id="0c5b9-108">不過，Surface 膝上型電腦需要一些其他驅動程式，才能啟用鍵盤。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-108">However, Surface Laptop requires some additional drivers to enable the keyboard.</span></span> <span data-ttu-id="0c5b9-109">針對 Surface 膝上型電腦 (1 Gen) 和 Surface 膝上型電腦2裝置，您必須準備可讓您指定使用鍵盤驅動程式的資料夾結構和選取設定檔，以便在 Windows 預先安裝環境 (Windows PE) 階段（在 LTI 中）使用。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-109">For Surface Laptop (1st Gen) and Surface Laptop 2 devices, you must prepare the folder structure and selection profiles that allow you to specify keyboard drivers for use during the Windows Preinstallation Environment (Windows PE) phase of LTI.</span></span> <span data-ttu-id="0c5b9-110">如需此資料夾結構的詳細資訊，請參閱 [使用 MDT 部署 Windows 10 影像：步驟5：準備驅動程式儲存庫](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-110">For more information about this folder structure, see [Deploy a Windows 10 image using MDT: Step 5: Prepare the drivers repository](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository).</span></span>

> [!TIP]    
> <span data-ttu-id="0c5b9-111">在相同的 Windows PE 啟動實例中，針對 Surface 膝上型電腦2和 Surface 膝上型電腦3使用鍵盤驅動程式時，如果 Windows PE 中的鍵盤或觸控板無法運作，您可能需要手動重設固件：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-111">When using keyboard drivers for Surface Laptop 2 and Surface Laptop 3 in the same Windows PE boot instance, you may need to manually reset the firmware if the keyboard or touchpad don’t work in Windows PE:</span></span>
>
> - <span data-ttu-id="0c5b9-112">按住電源按鈕30秒鐘。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-112">Press and hold the Power button for 30 seconds.</span></span> <span data-ttu-id="0c5b9-113">如果您已連線至 (PSU) 的電源裝置，請按住電源按鈕，直到您看到 PSU 線尾端的燈短暫關閉，然後再重新開啟。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-113">If you are connected to a power supply unit (PSU), press and hold the Power button until you see the light at the end of the PSU cord briefly turn off before turning back on.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0c5b9-114">如果您要將 Windows 10 影像部署到已預先安裝 Windows 10 的 Surface 膝上型電腦，請參閱 KB [4032347：在 s 模式中，將 windows 部署到已預先安裝 windows 10 的 surface 裝置時會發生問題](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-114">If you are deploying a Windows 10 image to a Surface Laptop that has Windows 10 in S mode preinstalled, see KB [4032347, Problems when deploying Windows to Surface devices with preinstalled Windows 10 in S mode](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues).</span></span>

<span data-ttu-id="0c5b9-115">若要將鍵盤驅動程式新增至選取設定檔，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-115">To add the keyboard drivers to the selection profile, follow these steps:</span></span>

1. <span data-ttu-id="0c5b9-116">從適當的位置下載最新的 Surface 膝上型電腦 MSI 檔案：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-116">Download the latest Surface Laptop MSI file from the appropriate locations:</span></span>
    - [<span data-ttu-id="0c5b9-117">Surface 膝上型電腦 (1 Gen) 驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="0c5b9-117">Surface Laptop (1st Gen) Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=55489)
    - [<span data-ttu-id="0c5b9-118">Surface 膝上型電腦2驅動程式與固件</span><span class="sxs-lookup"><span data-stu-id="0c5b9-118">Surface Laptop 2 Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=57515)
    - [<span data-ttu-id="0c5b9-119">含英特爾處理器驅動程式和固件的 Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="0c5b9-119">Surface Laptop 3 with Intel Processor Drivers and Firmware</span></span>](https://www.microsoft.com/download/details.aspx?id=100429)

2. <span data-ttu-id="0c5b9-120">將 Surface 膝上型電腦 MSI 檔案的內容解壓至資料夾，您可以輕鬆地找到 (例如 c：\ surface_laptop_drivers) 。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-120">Extract the contents of the Surface Laptop MSI file to a folder that you can easily locate (for example, c:\surface_laptop_drivers).</span></span> <span data-ttu-id="0c5b9-121">若要解壓縮內容，請開啟提升許可權的命令提示字元視窗，然後執行下列範例中的命令：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-121">To extract the contents, open an elevated Command Prompt window and run the command from the following example:</span></span>

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. <span data-ttu-id="0c5b9-122">開啟部署工作臺，然後展開 [ **部署共用** ] 節點和您的部署共用，然後流覽至 [ **WindowsPEX64** ] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-122">Open the Deployment Workbench and expand the **Deployment Shares** node and your deployment share, then navigate to the **WindowsPEX64** folder.</span></span>

   ![在部署工作臺中顯示 WindowsPEX64 資料夾位置的影像](./images/surface-laptop-keyboard-1.png)

4. <span data-ttu-id="0c5b9-124">以滑鼠右鍵按一下 [ **WindowsPEX64** ] 資料夾，然後選取 [匯 **入驅動程式**]。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-124">Right-click the **WindowsPEX64** folder and select **Import Drivers**.</span></span>

5. <span data-ttu-id="0c5b9-125">依照 [匯入驅動程式] 嚮導中的指示，將驅動程式資料夾匯入 [WindowsPEX64] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-125">Follow the instructions in the Import Driver Wizard to import the driver folders into the WindowsPEX64 folder.</span></span>  

    > [!NOTE]
    >  <span data-ttu-id="0c5b9-126">檢查已下載的 MSI 套件，以判斷格式和目錄結構。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-126">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="0c5b9-127">目錄結構將會以 SurfacePlatformInstaller (較舊的 MSI 檔案) 或 SurfaceUpdate (較新的 MSI 檔案，) 視 MSI 的發行時間而定。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-127">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

    <span data-ttu-id="0c5b9-128">若要支援 Surface 膝上型電腦 (1 Gen) ，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-128">To support Surface Laptop (1st Gen), import the following folders:</span></span>

     - <span data-ttu-id="0c5b9-129">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-129">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="0c5b9-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-130">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
     - <span data-ttu-id="0c5b9-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-131">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="0c5b9-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-132">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="0c5b9-133">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-133">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="0c5b9-134">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-134">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="0c5b9-135">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-135">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="0c5b9-136">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-136">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="0c5b9-137">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-137">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="0c5b9-138">若要支援 Surface 膝上型電腦2，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-138">To support Surface Laptop 2, import the following folders:</span></span>

     - <span data-ttu-id="0c5b9-139">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-139">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
     - <span data-ttu-id="0c5b9-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-140">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
     - <span data-ttu-id="0c5b9-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-141">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
     - <span data-ttu-id="0c5b9-142">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="0c5b9-142">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
     - <span data-ttu-id="0c5b9-143">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="0c5b9-143">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
     - <span data-ttu-id="0c5b9-144">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="0c5b9-144">SurfacePlatformInstaller\Drivers\System\UART</span></span>
     - <span data-ttu-id="0c5b9-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-145">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="0c5b9-146">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-146">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="0c5b9-147">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-147">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="0c5b9-148">SurfaceUpdate\serialioi2c</span><span class="sxs-lookup"><span data-stu-id="0c5b9-148">SurfaceUpdate\serialioi2c</span></span>
    - <span data-ttu-id="0c5b9-149">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0c5b9-149">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="0c5b9-150">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0c5b9-150">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="0c5b9-151">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0c5b9-151">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="0c5b9-152">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0c5b9-152">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="0c5b9-153">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-153">SurfaceUpdate\Itouch</span></span>

     
    <span data-ttu-id="0c5b9-154">若要支援含英特爾處理器的 Surface 膝上型電腦3，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-154">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="0c5b9-155">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-155">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="0c5b9-156">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0c5b9-156">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="0c5b9-157">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0c5b9-157">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="0c5b9-158">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0c5b9-158">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="0c5b9-159">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0c5b9-159">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="0c5b9-160">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0c5b9-160">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="0c5b9-161">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="0c5b9-161">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="0c5b9-162">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-162">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="0c5b9-163">匯入下列資料夾將在 Surface 膝上型電腦3的 PE 中啟用完整的鍵盤、軌跡板和觸控功能。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-163">Importing the following folders will enable full keyboard, trackpad, and touch functionality in PE for Surface Laptop 3.</span></span>

    - <span data-ttu-id="0c5b9-164">SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-164">SerialIOGPIO</span></span>
    - <span data-ttu-id="0c5b9-165">SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0c5b9-165">SerialIOI2C</span></span>
    - <span data-ttu-id="0c5b9-166">SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0c5b9-166">SerialIOSPI</span></span>
    - <span data-ttu-id="0c5b9-167">SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0c5b9-167">SerialIOUART</span></span>
    - <span data-ttu-id="0c5b9-168">itouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-168">itouch</span></span>
    - <span data-ttu-id="0c5b9-169">高速晶片組</span><span class="sxs-lookup"><span data-stu-id="0c5b9-169">Chipset</span></span>
    - <span data-ttu-id="0c5b9-170">ChipsetLPSS</span><span class="sxs-lookup"><span data-stu-id="0c5b9-170">ChipsetLPSS</span></span>
    - <span data-ttu-id="0c5b9-171">ChipsetNorthpeak</span><span class="sxs-lookup"><span data-stu-id="0c5b9-171">ChipsetNorthpeak</span></span>
    - <span data-ttu-id="0c5b9-172">ManagementEngine</span><span class="sxs-lookup"><span data-stu-id="0c5b9-172">ManagementEngine</span></span>
    - <span data-ttu-id="0c5b9-173">SurfaceAcpiNotify</span><span class="sxs-lookup"><span data-stu-id="0c5b9-173">SurfaceAcpiNotify</span></span>
    - <span data-ttu-id="0c5b9-174">SurfaceBattery</span><span class="sxs-lookup"><span data-stu-id="0c5b9-174">SurfaceBattery</span></span>
    - <span data-ttu-id="0c5b9-175">SurfaceDockIntegration</span><span class="sxs-lookup"><span data-stu-id="0c5b9-175">SurfaceDockIntegration</span></span>
    - <span data-ttu-id="0c5b9-176">SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0c5b9-176">SurfaceHidMini</span></span>
    - <span data-ttu-id="0c5b9-177">SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="0c5b9-177">SurfaceHotPlug</span></span>
    - <span data-ttu-id="0c5b9-178">SurfaceIntegration</span><span class="sxs-lookup"><span data-stu-id="0c5b9-178">SurfaceIntegration</span></span>
    - <span data-ttu-id="0c5b9-179">SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0c5b9-179">SurfaceSerialHub</span></span>
    - <span data-ttu-id="0c5b9-180">SurfaceService</span><span class="sxs-lookup"><span data-stu-id="0c5b9-180">SurfaceService</span></span>
    - <span data-ttu-id="0c5b9-181">SurfaceStorageFwUpdate</span><span class="sxs-lookup"><span data-stu-id="0c5b9-181">SurfaceStorageFwUpdate</span></span>

     > [!NOTE]
     >  <span data-ttu-id="0c5b9-182">檢查已下載的 MSI 套件，以判斷格式和目錄結構。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-182">Check the downloaded MSI package to determine the format and directory structure.</span></span>  <span data-ttu-id="0c5b9-183">目錄結構將會以 SurfacePlatformInstaller (較舊的 MSI 檔案) 或 SurfaceUpdate (較新的 MSI 檔案，) 視 MSI 的發行時間而定。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-183">The directory structure will start with either SurfacePlatformInstaller (older MSI files) or SurfaceUpdate (Newer MSI files) depending on when the MSI was released.</span></span> 

     <span data-ttu-id="0c5b9-184">若要支援 Surface 膝上型電腦 (1 Gen) ，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-184">To support Surface Laptop (1st Gen), import the following folders:</span></span>

    - <span data-ttu-id="0c5b9-185">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-185">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="0c5b9-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-186">SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="0c5b9-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-187">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="0c5b9-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-188">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="0c5b9-189">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-189">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="0c5b9-190">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-190">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="0c5b9-191">SurfaceUpdate\SurfaceHidMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-191">SurfaceUpdate\SurfaceHidMiniDriver</span></span>
    - <span data-ttu-id="0c5b9-192">SurfaceUpdate\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-192">SurfaceUpdate\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="0c5b9-193">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-193">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="0c5b9-194">若要支援 Surface 膝上型電腦2，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-194">To support Surface Laptop 2, import the following folders:</span></span>

    - <span data-ttu-id="0c5b9-195">SurfacePlatformInstaller\Drivers\System\GPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-195">SurfacePlatformInstaller\Drivers\System\GPIO</span></span>
    - <span data-ttu-id="0c5b9-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-196">SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver</span></span>
    - <span data-ttu-id="0c5b9-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span><span class="sxs-lookup"><span data-stu-id="0c5b9-197">SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver</span></span>
    - <span data-ttu-id="0c5b9-198">SurfacePlatformInstaller\Drivers\System\I2C</span><span class="sxs-lookup"><span data-stu-id="0c5b9-198">SurfacePlatformInstaller\Drivers\System\I2C</span></span>
    - <span data-ttu-id="0c5b9-199">SurfacePlatformInstaller\Drivers\System\SPI</span><span class="sxs-lookup"><span data-stu-id="0c5b9-199">SurfacePlatformInstaller\Drivers\System\SPI</span></span>
    - <span data-ttu-id="0c5b9-200">SurfacePlatformInstaller\Drivers\System\UART</span><span class="sxs-lookup"><span data-stu-id="0c5b9-200">SurfacePlatformInstaller\Drivers\System\UART</span></span>
    - <span data-ttu-id="0c5b9-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-201">SurfacePlatformInstaller\Drivers\System\PreciseTouch</span></span>

    <span data-ttu-id="0c5b9-202">或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-202">Or for newer MSI files beginning with "SurfaceUpdate", use:</span></span>

    - <span data-ttu-id="0c5b9-203">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-203">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="0c5b9-204">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0c5b9-204">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="0c5b9-205">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0c5b9-205">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="0c5b9-206">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0c5b9-206">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="0c5b9-207">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0c5b9-207">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="0c5b9-208">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0c5b9-208">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="0c5b9-209">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-209">SurfaceUpdate\Itouch</span></span>

    <span data-ttu-id="0c5b9-210">若要支援含英特爾處理器的 Surface 膝上型電腦3，請匯入下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-210">To support Surface Laptop 3 with Intel Processor, import the following folders:</span></span>

    - <span data-ttu-id="0c5b9-211">SurfaceUpdate\SerialIOGPIO</span><span class="sxs-lookup"><span data-stu-id="0c5b9-211">SurfaceUpdate\SerialIOGPIO</span></span>
    - <span data-ttu-id="0c5b9-212">SurfaceUpdate\SerialIOI2C</span><span class="sxs-lookup"><span data-stu-id="0c5b9-212">SurfaceUpdate\SerialIOI2C</span></span>
    - <span data-ttu-id="0c5b9-213">SurfaceUpdate\SerialIOSPI</span><span class="sxs-lookup"><span data-stu-id="0c5b9-213">SurfaceUpdate\SerialIOSPI</span></span>
    - <span data-ttu-id="0c5b9-214">SurfaceUpdate\SerialIOUART</span><span class="sxs-lookup"><span data-stu-id="0c5b9-214">SurfaceUpdate\SerialIOUART</span></span>
    - <span data-ttu-id="0c5b9-215">SurfaceUpdate\SurfaceHidMini</span><span class="sxs-lookup"><span data-stu-id="0c5b9-215">SurfaceUpdate\SurfaceHidMini</span></span>
    - <span data-ttu-id="0c5b9-216">SurfaceUpdate\SurfaceSerialHub</span><span class="sxs-lookup"><span data-stu-id="0c5b9-216">SurfaceUpdate\SurfaceSerialHub</span></span>
    - <span data-ttu-id="0c5b9-217">SurfaceUpdate\SurfaceHotPlug</span><span class="sxs-lookup"><span data-stu-id="0c5b9-217">SurfaceUpdate\SurfaceHotPlug</span></span>
    - <span data-ttu-id="0c5b9-218">SurfaceUpdate\Itouch</span><span class="sxs-lookup"><span data-stu-id="0c5b9-218">SurfaceUpdate\Itouch</span></span>

    > [!NOTE]
    > <span data-ttu-id="0c5b9-219">針對含英特爾處理器的 Surface 膝上型電腦3，模型為 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-219">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="0c5b9-220">剩餘的 Surface 膝上型電腦驅動程式位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦 3] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-220">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

6. <span data-ttu-id="0c5b9-221">確認 WindowsPEX64 資料夾現在包含已匯入的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-221">Verify that the WindowsPEX64 folder now contains the imported drivers.</span></span> <span data-ttu-id="0c5b9-222">該資料夾應如下所示：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-222">The folder should resemble the following:</span></span>  

   ![在部署工作臺的 [WindowsPEX64] 資料夾中顯示新匯入驅動程式的影像](./images/surface-laptop-keyboard-2.png)

7. <span data-ttu-id="0c5b9-224">設定使用 WindowsPEX64 資料夾的選取設定檔。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-224">Configure a selection profile that uses the WindowsPEX64 folder.</span></span> <span data-ttu-id="0c5b9-225">選取設定檔應如下所示：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-225">The selection profile should resemble the following:</span></span>  

   ![顯示選取為選取設定檔一部分之 WindowsPEX64 資料夾的影像](./images/surface-laptop-keyboard-3.png)

8. <span data-ttu-id="0c5b9-227">將 MDT 部署共用的 Windows PE 屬性設定為使用新的選取設定檔，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0c5b9-227">Configure the Windows PE properties of the MDT deployment share to use the new selection profile, as follows:</span></span>  

   - <span data-ttu-id="0c5b9-228">針對 [ **平臺**]，選取 [ **x64**]。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-228">For **Platform**, select **x64**.</span></span>
   - <span data-ttu-id="0c5b9-229">針對 [ **選取設定檔**]，選取新的設定檔。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-229">For **Selection profile**, select the new profile.</span></span>
   - <span data-ttu-id="0c5b9-230">選取 **[包含選取設定檔中的所有驅動程式**]。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-230">Select **Include all drivers from the selection profile**.</span></span>
   
   ![顯示 MDT 部署共用的 Windows PE 屬性的圖像](./images/surface-laptop-keyboard-4.png)

9. <span data-ttu-id="0c5b9-232">使用選取設定檔或 **DriverGroup001** 變數，確認您已設定剩餘的 Surface 膝上型電腦驅動程式。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-232">Verify that you have configured the remaining Surface Laptop drivers by using either a selection profile or a **DriverGroup001** variable.</span></span>  
   - <span data-ttu-id="0c5b9-233">針對 Surface 膝上型電腦 (1 Gen) ，模型是 **Surface 膝上型電腦**。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-233">For Surface Laptop (1st Gen), the model is **Surface Laptop**.</span></span> <span data-ttu-id="0c5b9-234">剩餘的 Surface 膝上型電腦驅動程式應該位於 \MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦資料夾中，如以下清單所示。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-234">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop folder as shown in the figure that follows this list.</span></span>
   - <span data-ttu-id="0c5b9-235">如果是 Surface 膝上型電腦2，則模型為 **Surface 膝上型電腦 2**。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-235">For Surface Laptop 2, the model is **Surface Laptop 2**.</span></span> <span data-ttu-id="0c5b9-236">剩餘的 Surface 膝上型電腦驅動程式應該位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型 2] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-236">The remaining Surface Laptop drivers should reside in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 folder.</span></span> 
   - <span data-ttu-id="0c5b9-237">針對含英特爾處理器的 Surface 膝上型電腦3，模型為 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-237">For Surface Laptop 3 with Intel processor, the model is Surface Laptop 3.</span></span> <span data-ttu-id="0c5b9-238">剩餘的 Surface 膝上型電腦驅動程式位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦 3] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-238">The remaining Surface Laptop drivers are located in the \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 folder.</span></span>

   ![在部署工作臺的 [Surface 膝上型電腦] 資料夾中，顯示一般 Surface 膝上型電腦 (第一個 Gen) 驅動程式的影像](./images/surface-laptop-keyboard-5.png)

<span data-ttu-id="0c5b9-240">將 MDT 部署共用設定為使用新的選取設定檔和相關設定之後，請按照 [使用 MDT 部署 Windows 10 映射](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)中的說明，繼續進行部署程式：建立部署任務序列。</span><span class="sxs-lookup"><span data-stu-id="0c5b9-240">After configuring the MDT Deployment Share to use the new selection profile and related settings, continue the deployment process as described in [Deploy a Windows 10 image using MDT: Step 6: Create the deployment task sequence](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence).</span></span>
