---
title: 管理和部署 Surface 驅動程式與韌體更新
description: 本文將說明管理和部署 Surface 裝置的固件與驅動程式更新的可用選項。
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, update, device, manage, deploy, driver, USB, 韌體, 更新, 裝置, 管理, 部署, 驅動程式
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: f41974193d62e4c0cbc1e286976105c20534d906
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897061"
---
# <span data-ttu-id="56331-104">管理和部署 Surface 驅動程式與韌體更新</span><span class="sxs-lookup"><span data-stu-id="56331-104">Manage and deploy Surface driver and firmware updates</span></span>

<span data-ttu-id="56331-105">您管理 Surface 驅動程式和固件更新的方式會視您的環境和組織需求而有所不同。</span><span class="sxs-lookup"><span data-stu-id="56331-105">How you manage Surface driver and firmware updates varies depending on your environment and organizational requirements.</span></span> <span data-ttu-id="56331-106">在 Surface 裝置上，固件會公開給作業系統作為驅動程式，且會顯示在 [裝置管理器] 中。</span><span class="sxs-lookup"><span data-stu-id="56331-106">On Surface devices, firmware is exposed to the operating system as a driver and is visible in Device Manager.</span></span> <span data-ttu-id="56331-107">這可讓裝置固件及驅動程式使用 Windows Update 或商務用 Windows Update 來自動更新。</span><span class="sxs-lookup"><span data-stu-id="56331-107">This enables device firmware and drivers to be automatically updated using Windows Update or Windows Update for Business.</span></span> <span data-ttu-id="56331-108">雖然這種簡化的方法可能適用于啟動和中小型企業，但大型組織通常需要 IT 系統管理員在內部發佈更新。</span><span class="sxs-lookup"><span data-stu-id="56331-108">Although this simplified approach may be feasible for startups and small or medium-sized businesses, larger organizations typically need IT admins to distribute updates internally.</span></span> <span data-ttu-id="56331-109">這可能會涉及完整的規劃、應用程式相容性測試，以及先導和驗證更新，然後再在整個網路上進行最終核准與發佈。</span><span class="sxs-lookup"><span data-stu-id="56331-109">This may involve comprehensive planning, application compatibility testing, and piloting and validating updates before final approval and distribution across the network.</span></span>

> [!NOTE]
> <span data-ttu-id="56331-110">本文適用于技術支援代理商和 IT 專業人員，且僅適用于 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="56331-110">This article is intended for technical support agents and IT professionals and applies to Surface devices only.</span></span> <span data-ttu-id="56331-111">如果您正在尋找在家用裝置上安裝 Surface 更新或固件的協助，請參閱[更新 Surface 固件和 Windows 10](https://support.microsoft.com/help/4023505)。</span><span class="sxs-lookup"><span data-stu-id="56331-111">If you're looking for help to install Surface updates or firmware on a home device, see [Update Surface firmware and Windows 10](https://support.microsoft.com/help/4023505).</span></span>

<span data-ttu-id="56331-112">雖然企業級軟體分發方案會繼續發展，但集中管理更新的商業基本原理仍會保持不變：維持 Surface 裝置的安全性，並使用最新的作業系統及功能改善來保持更新。</span><span class="sxs-lookup"><span data-stu-id="56331-112">While enterprise-grade software distribution solutions continue to evolve, the business rationale for centrally managing  updates remains the same: Maintain the security of Surface devices and keep them updated with the latest operating system and feature improvements.</span></span> <span data-ttu-id="56331-113">這對於維持穩定的生產環境至關重要，並確保不會封鎖使用者的生產力。</span><span class="sxs-lookup"><span data-stu-id="56331-113">This is essential for sustaining a stable production environment and making sure that users aren't blocked from being productive.</span></span> <span data-ttu-id="56331-114">本文概述針對大型組織完成這些目標所建議的工具與程式。</span><span class="sxs-lookup"><span data-stu-id="56331-114">This article provides an overview of recommended tools and processes for larger organizations to accomplish these goals.</span></span>

## <span data-ttu-id="56331-115">在商業環境中的中央更新管理</span><span class="sxs-lookup"><span data-stu-id="56331-115">Central update management in commercial environments</span></span>

<span data-ttu-id="56331-116">Microsoft 有精簡的工具可用於管理裝置，包括驅動程式和固件更新--融入名為[Microsoft 端點管理員](https://devicemanagement.microsoft.com/)系統管理中心且從[devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home)存取的單一整合體驗。</span><span class="sxs-lookup"><span data-stu-id="56331-116">Microsoft has streamlined tools for managing devices – including driver and firmware updates -- into a single unified experience that is named [Microsoft Endpoint Manager admin center](https://devicemanagement.microsoft.com/) and is accessed from [devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home).</span></span>

### <span data-ttu-id="56331-117">使用 Configuration Manager 和 Intune 管理更新</span><span class="sxs-lookup"><span data-stu-id="56331-117">Manage updates with Configuration Manager and Intune</span></span>

<span data-ttu-id="56331-118">Microsoft 端點 Configuration Manager 可讓您與 Configuration Manager 用戶端同步處理及部署 Surface 固件及驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="56331-118">Microsoft Endpoint Configuration Manager allows you to synchronize and deploy Surface firmware and driver updates with the Configuration Manager client.</span></span> <span data-ttu-id="56331-119">與 Microsoft Intune 整合可讓您在同一個位置查看所有受管理、共同管理和合作夥伴管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="56331-119">Integration with Microsoft Intune lets you see all your managed, co-managed, and partner-managed devices in one place.</span></span> <span data-ttu-id="56331-120">這是大型組織管理 Surface 更新的建議方案。</span><span class="sxs-lookup"><span data-stu-id="56331-120">This is the recommended solution for large organizations to manage Surface updates.</span></span>

<span data-ttu-id="56331-121">如需詳細步驟，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="56331-121">For detailed steps, see the following resources:</span></span>

- [<span data-ttu-id="56331-122">在 Configuration Manager 中管理 Surface 驅動程式更新</span><span class="sxs-lookup"><span data-stu-id="56331-122">Manage Surface driver updates in Configuration Manager</span></span>](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [<span data-ttu-id="56331-123">使用 Configuration Manager 部署應用程式</span><span class="sxs-lookup"><span data-stu-id="56331-123">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [<span data-ttu-id="56331-124">端點建構管理員檔</span><span class="sxs-lookup"><span data-stu-id="56331-124">Endpoint Configuration Manager documentation</span></span>](https://docs.microsoft.com/configmgr/)

### <span data-ttu-id="56331-125">使用 Microsoft 部署工具組管理更新</span><span class="sxs-lookup"><span data-stu-id="56331-125">Manage updates with Microsoft Deployment Toolkit</span></span>

<span data-ttu-id="56331-126">Microsoft 部署工具組（MDT）包含在端點建構管理員中。</span><span class="sxs-lookup"><span data-stu-id="56331-126">The Microsoft Deployment Toolkit (MDT) is included in Endpoint Configuration Manager.</span></span> <span data-ttu-id="56331-127">它包含您可能會想要使用的選用部署工具（視您的環境而定）。</span><span class="sxs-lookup"><span data-stu-id="56331-127">It contains optional deployment tools that you may want to use, depending on your environment.</span></span> <span data-ttu-id="56331-128">這些包括 Windows 評估與部署套件（Windows ADK）、Windows 系統圖像管理器（Windows SIM）、部署映射服務與管理（DISM），以及使用者狀態遷移工具（USMT）。</span><span class="sxs-lookup"><span data-stu-id="56331-128">These include the Windows Assessment and Deployment Kit (Windows ADK), Windows System Image Manager (Windows SIM), Deployment Image Servicing and Management (DISM), and User State Migration Tool (USMT).</span></span> <span data-ttu-id="56331-129">您可以從 [ [Microsoft 部署工具](https://www.microsoft.com/download/details.aspx?id=54259)] 的 [下載] 頁面下載最新版本的 MDT。</span><span class="sxs-lookup"><span data-stu-id="56331-129">You can download the latest version of MDT from the [Microsoft Deployment Toolkit download page](https://www.microsoft.com/download/details.aspx?id=54259).</span></span>

<span data-ttu-id="56331-130">如需詳細步驟，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="56331-130">For detailed steps, see the following resources:</span></span>

- [<span data-ttu-id="56331-131">Microsoft 部署工具組檔</span><span class="sxs-lookup"><span data-stu-id="56331-131">Microsoft Deployment Toolkit documentation</span></span>](https://docs.microsoft.com/configmgr/mdt/)
- [<span data-ttu-id="56331-132">使用 Microsoft Deployment Toolkit 部署 Windows10</span><span class="sxs-lookup"><span data-stu-id="56331-132">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [<span data-ttu-id="56331-133">使用 Microsoft 部署工具組將 Windows 10 部署到 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="56331-133">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

<span data-ttu-id="56331-134">表面驅動程式和固件更新封裝為 Windows Installer （\* .msi）檔案。</span><span class="sxs-lookup"><span data-stu-id="56331-134">Surface driver and firmware updates are packaged as Windows Installer (\*.msi) files.</span></span> <span data-ttu-id="56331-135">若要部署這些 Windows 安裝程式套件，您可以使用端點建構管理員或 MDT。</span><span class="sxs-lookup"><span data-stu-id="56331-135">To deploy these Windows Installer packages, you can use Endpoint Configuration Manager or MDT.</span></span> <span data-ttu-id="56331-136">如需如何為裝置和作業系統選取正確的 .msi 檔案的相關資訊，請參閱下列章節有關下載 .msi 檔案的指導方針。</span><span class="sxs-lookup"><span data-stu-id="56331-136">For information about how to select the correct .msi file for a device and operating system, refer to the guidance in the following sections about downloading .msi files.</span></span>

<span data-ttu-id="56331-137">如需有關如何使用端點建構管理員部署更新的指示，請參閱使用[Configuration Manager 部署應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)。</span><span class="sxs-lookup"><span data-stu-id="56331-137">For instructions about how to deploy updates by using Endpoint Configuration Manager, see [Deploy applications with Configuration Manager](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications).</span></span> <span data-ttu-id="56331-138">如需如何使用 MDT 部署更新的相關指示，請參閱[使用 Mdt 部署 Windows 10 影像](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)。</span><span class="sxs-lookup"><span data-stu-id="56331-138">For instructions about how to deploy updates by using MDT, see [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).</span></span>

**<span data-ttu-id="56331-139">WindowsPE 和 Surface 固件與驅動程式</span><span class="sxs-lookup"><span data-stu-id="56331-139">WindowsPE and Surface firmware and drivers</span></span>**

<span data-ttu-id="56331-140">端點設定管理員和 MDT 在部署程式期間都使用 Windows 預先安裝環境（WindowsPE）。</span><span class="sxs-lookup"><span data-stu-id="56331-140">Endpoint Configuration Manager and MDT both use the Windows Preinstallation Environment (WindowsPE) during the deployment process.</span></span> <span data-ttu-id="56331-141">WindowsPE 僅支援一組有限的基本驅動程式，例如網路介面卡和儲存控制器的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="56331-141">WindowsPE supports only a limited set of basic drivers such as those for network adapters and storage controllers.</span></span> <span data-ttu-id="56331-142">不屬於 WindowsPE 的 Windows 元件驅動程式可能會產生錯誤。</span><span class="sxs-lookup"><span data-stu-id="56331-142">Drivers for Windows components that are not part of WindowsPE might produce errors.</span></span> <span data-ttu-id="56331-143">最佳做法是，將部署程式設定為在 WindowsPE 階段只使用所需的驅動程式，就能避免這類錯誤。</span><span class="sxs-lookup"><span data-stu-id="56331-143">As a best practice, you can prevent such errors by configuring the deployment process to use only the required drivers during the WindowsPE phase.</span></span>

### <span data-ttu-id="56331-144">Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="56331-144">Endpoint Configuration Manager</span></span>

<span data-ttu-id="56331-145">從端點設定管理員開始，您可以使用 Configuration Manager 用戶端來同步處理及部署 Microsoft Surface 固件與驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="56331-145">Starting in Endpoint Configuration Manager, you can synchronize and deploy Microsoft Surface firmware and driver updates by using the Configuration Manager client.</span></span> <span data-ttu-id="56331-146">如需其他資訊，請參閱 KB 4098906，[如何在 Configuration Manager 中管理表面驅動程式更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)。</span><span class="sxs-lookup"><span data-stu-id="56331-146">For additional information, see KB 4098906, [How to manage Surface driver updates in Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager).</span></span>

## <span data-ttu-id="56331-147">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="56331-147">Supported devices</span></span>

<span data-ttu-id="56331-148">可下載的 .msi 檔案可供 Surface Pro 2 和更新版本的裝置使用。</span><span class="sxs-lookup"><span data-stu-id="56331-148">Downloadable .msi files are available for the Surface Pro 2 and later devices.</span></span> <span data-ttu-id="56331-149">在發行時，此頁面提供最新 Surface 裝置（例如 Surface Pro 7 及 Surface 膝上型3） .msi 檔案的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="56331-149">Information about .msi files for the newest Surface devices, such as Surface Pro 7 and Surface Laptop 3, will be available from this page upon release.</span></span>

## <span data-ttu-id="56331-150">使用 DFCI 管理固件</span><span class="sxs-lookup"><span data-stu-id="56331-150">Managing firmware with DFCI</span></span>

<span data-ttu-id="56331-151">透過將裝置固件配置介面（DFCI）設定檔內建到 Intune （現已提供給[公用預覽](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)），Surface UEFI 管理會將新式管理堆疊延伸到 UEFI 硬體層級。</span><span class="sxs-lookup"><span data-stu-id="56331-151">By having Device Firmware Configuration Interface (DFCI) profiles built into Intune (now available in [public preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="56331-152">DFCI 支援零觸控配，消除 BIOS 密碼，提供安全性設定（包括啟動選項和內建週邊設備）的控制權，並針對未來的高級安全性案例奠定基礎。</span><span class="sxs-lookup"><span data-stu-id="56331-152">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings (including startup options and built-in peripherals), and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="56331-153">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="56331-153">For more information, see the following articles:</span></span>

- [<span data-ttu-id="56331-154">Surface UEFI 設定的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="56331-154">Intune management of Surface UEFI settings</span></span>](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- <span data-ttu-id="56331-155">[Ignite 2019：宣佈從 Intune 遠端系統管理 SURFACE UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。</span><span class="sxs-lookup"><span data-stu-id="56331-155">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

## <span data-ttu-id="56331-156">更新部署程式的最佳做法</span><span class="sxs-lookup"><span data-stu-id="56331-156">Best practices for update deployment processes</span></span>

<span data-ttu-id="56331-157">若要維持穩定的環境，我們強烈建議您使用最新版本的 Windows 10 維護同位。</span><span class="sxs-lookup"><span data-stu-id="56331-157">To maintain a stable environment, we strongly recommend that you maintain parity with the most recent version of Windows 10.</span></span>  <span data-ttu-id="56331-158">如需最佳做法建議，請參閱[建立適用于 Windows 10 更新的部署環](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)。</span><span class="sxs-lookup"><span data-stu-id="56331-158">For best practice recommendations, see [Build deployment rings for Windows 10 updates](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates).</span></span>

## <span data-ttu-id="56331-159">可下載的 Surface 更新套件</span><span class="sxs-lookup"><span data-stu-id="56331-159">Downloadable Surface update packages</span></span>

<span data-ttu-id="56331-160">Windows 10 的特定版本有個別的 .msi 檔案，每個檔案都包含 Surface 裝置所需的所有必要累計驅動程式和固件更新。</span><span class="sxs-lookup"><span data-stu-id="56331-160">Specific versions of Windows 10 have separate .msi files, each containing all the required cumulative driver and firmware updates for Surface devices.</span></span> <span data-ttu-id="56331-161">更新套件可能包含以下部分或所有元件：</span><span class="sxs-lookup"><span data-stu-id="56331-161">Update packages may include some or all the following components:</span></span>

- <span data-ttu-id="56331-162">Wi-fi 和 LTE</span><span class="sxs-lookup"><span data-stu-id="56331-162">Wi-Fi and LTE</span></span>
- <span data-ttu-id="56331-163">影片</span><span class="sxs-lookup"><span data-stu-id="56331-163">Video</span></span>
- <span data-ttu-id="56331-164">實體狀態磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="56331-164">Solid state drive</span></span>
- <span data-ttu-id="56331-165">系統聚合模組（SAM）</span><span class="sxs-lookup"><span data-stu-id="56331-165">System aggregator module (SAM)</span></span>
- <span data-ttu-id="56331-166">電池</span><span class="sxs-lookup"><span data-stu-id="56331-166">Battery</span></span>
- <span data-ttu-id="56331-167">鍵盤控制器</span><span class="sxs-lookup"><span data-stu-id="56331-167">Keyboard controller</span></span>
- <span data-ttu-id="56331-168">內嵌控制器（EC）</span><span class="sxs-lookup"><span data-stu-id="56331-168">Embedded controller (EC)</span></span>
- <span data-ttu-id="56331-169">管理引擎（ME）</span><span class="sxs-lookup"><span data-stu-id="56331-169">Management engine (ME)</span></span>
- <span data-ttu-id="56331-170">整合的可延伸韌體介面（UEFI）</span><span class="sxs-lookup"><span data-stu-id="56331-170">Unified extensible firmware interface (UEFI)</span></span>

### <span data-ttu-id="56331-171">下載 .msi 檔案</span><span class="sxs-lookup"><span data-stu-id="56331-171">Downloading .msi files</span></span>

1. <span data-ttu-id="56331-172">在 Microsoft 下載中心，流覽以[下載 Surface 的驅動程式和固件](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)。</span><span class="sxs-lookup"><span data-stu-id="56331-172">Browse to [Download drivers and firmware for Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) on the Microsoft Download Center.</span></span>
2. <span data-ttu-id="56331-173">選取與 Surface 模型和 Windows 版本相符的 .msi 檔案名。</span><span class="sxs-lookup"><span data-stu-id="56331-173">Select the .msi file name that matches the Surface model and version of Windows.</span></span> <span data-ttu-id="56331-174">.Msi 檔案名包括安裝驅動程式和固件所需的最低 Windows 組建編號。</span><span class="sxs-lookup"><span data-stu-id="56331-174">The .msi file name includes the minimum supported Windows build number that's required to install the drivers and firmware.</span></span> <span data-ttu-id="56331-175">例如，請參閱下圖。</span><span class="sxs-lookup"><span data-stu-id="56331-175">For example, refer to the following figure.</span></span> <span data-ttu-id="56331-176">若要更新具有 Windows 10 組建18362的 Surface Book 2，請選擇 [ **SurfaceBook2_Win10_18362_19.101.13994.msi]。**</span><span class="sxs-lookup"><span data-stu-id="56331-176">To update a Surface Book 2 that has build 18362 of Windows 10, choose **SurfaceBook2_Win10_18362_19.101.13994.msi.**</span></span> <span data-ttu-id="56331-177">針對 Windows 10 版組建16299的 Surface Book 2，請選擇 [ **SurfaceBook2_Win10_16299_1803509_3.msi**]。</span><span class="sxs-lookup"><span data-stu-id="56331-177">For a Surface Book 2 that has build 16299 of Windows 10, choose **SurfaceBook2_Win10_16299_1803509_3.msi**.</span></span>

    ![圖 1。](images/fig1-downloads-msi.png)

    *<span data-ttu-id="56331-180">圖 1。</span><span class="sxs-lookup"><span data-stu-id="56331-180">Figure 1.</span></span> <span data-ttu-id="56331-181">下載 Surface 更新</span><span class="sxs-lookup"><span data-stu-id="56331-181">Downloading Surface updates</span></span>*

### <span data-ttu-id="56331-182">您的 Surface. msi 命名慣例</span><span class="sxs-lookup"><span data-stu-id="56331-182">Surface .msi naming convention</span></span>

<span data-ttu-id="56331-183">自2019年8月起，.msi 檔案使用下列命名慣例：</span><span class="sxs-lookup"><span data-stu-id="56331-183">Since August 2019, .msi files are using the following naming convention:</span></span>

- <span data-ttu-id="56331-184">*產品*_*windows 發行*_*windows 組建*版本號碼的_*版本編號*_*（通常是零）*。</span><span class="sxs-lookup"><span data-stu-id="56331-184">*Product*_*Windows release*_*Windows build number*_*Version number*_*Revision of version number (typically zero)*.</span></span>

**<span data-ttu-id="56331-185">範例</span><span class="sxs-lookup"><span data-stu-id="56331-185">Example</span></span>**

- <span data-ttu-id="56331-186">SurfacePro6_Win10_18362_19.073.44195_0.msi</span><span class="sxs-lookup"><span data-stu-id="56331-186">SurfacePro6_Win10_18362_19.073.44195_0.msi</span></span>

<span data-ttu-id="56331-187">此檔案名提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="56331-187">This file name provides the following information:</span></span>

- <span data-ttu-id="56331-188">**產品：** SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="56331-188">**Product:** SurfacePro6</span></span>
- <span data-ttu-id="56331-189">**Windows 版本：** Win10</span><span class="sxs-lookup"><span data-stu-id="56331-189">**Windows release:** Win10</span></span>
- <span data-ttu-id="56331-190">**組建：** 18362</span><span class="sxs-lookup"><span data-stu-id="56331-190">**Build:** 18362</span></span>
- <span data-ttu-id="56331-191">**版本：** 19.073.44195 –這會顯示檔的建立日期和時間，如下所示：</span><span class="sxs-lookup"><span data-stu-id="56331-191">**Version:** 19.073.44195 – This shows the date and time that the file was created, as follows:</span></span>
  - <span data-ttu-id="56331-192">**年：** 19 （2019）</span><span class="sxs-lookup"><span data-stu-id="56331-192">**Year:** 19 (2019)</span></span>
  - <span data-ttu-id="56331-193">**月份與星期：** 073 （7月的第三周）</span><span class="sxs-lookup"><span data-stu-id="56331-193">**Month and week:** 073 (third week of July)</span></span>
  - <span data-ttu-id="56331-194">**月份的分鐘數：** 44195</span><span class="sxs-lookup"><span data-stu-id="56331-194">**Minute of the month:** 44195</span></span>
- <span data-ttu-id="56331-195">**版本：** 0 （此版本的第一次發行）</span><span class="sxs-lookup"><span data-stu-id="56331-195">**Revision of version:** 0 (first release of this version)</span></span>

### <span data-ttu-id="56331-196">傳統 Surface. msi 命名慣例</span><span class="sxs-lookup"><span data-stu-id="56331-196">Legacy Surface .msi naming convention</span></span>

<span data-ttu-id="56331-197">舊版 .msi 檔案（在2019年8月之前建立的檔案）遵循相同的整體命名公式，但使用不同的方法來衍生版本號碼。</span><span class="sxs-lookup"><span data-stu-id="56331-197">Legacy .msi files (files that were built before August 2019) followed the same overall naming formula but used a different method to derive the version number.</span></span>

**<span data-ttu-id="56331-198">範例</span><span class="sxs-lookup"><span data-stu-id="56331-198">Example</span></span>**

- <span data-ttu-id="56331-199">SurfacePro6_Win10_16299_1900307_0.msi</span><span class="sxs-lookup"><span data-stu-id="56331-199">SurfacePro6_Win10_16299_1900307_0.msi</span></span>

<span data-ttu-id="56331-200">此檔案名提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="56331-200">This file name provides the following information:</span></span>

- <span data-ttu-id="56331-201">**產品：** SurfacePro6</span><span class="sxs-lookup"><span data-stu-id="56331-201">**Product:** SurfacePro6</span></span>
- <span data-ttu-id="56331-202">**Windows 版本：** Win10</span><span class="sxs-lookup"><span data-stu-id="56331-202">**Windows release:** Win10</span></span>
- <span data-ttu-id="56331-203">**組建：** 16299</span><span class="sxs-lookup"><span data-stu-id="56331-203">**Build:** 16299</span></span>
- <span data-ttu-id="56331-204">**版本：** 1900307 –這會顯示建立檔案的日期，以及其在發行順序中的位置，如下所示：</span><span class="sxs-lookup"><span data-stu-id="56331-204">**Version:** 1900307 – This shows the date that the file was created and its position in the release sequence, as follows:</span></span>
  - <span data-ttu-id="56331-205">**年：** 19 （2019）</span><span class="sxs-lookup"><span data-stu-id="56331-205">**Year:** 19 (2019)</span></span>
  - <span data-ttu-id="56331-206">**發行數：** 003 （年份的第三版）</span><span class="sxs-lookup"><span data-stu-id="56331-206">**Number of release:** 003 (third release of the year)</span></span>
  - <span data-ttu-id="56331-207">**產品版本號碼：** 07 （surface pro 6 正式是第七個 Surface pro 版本）</span><span class="sxs-lookup"><span data-stu-id="56331-207">**Product version number:** 07 (Surface Pro 6 is officially the seventh version of Surface Pro)</span></span>
- <span data-ttu-id="56331-208">**版本：** 0 （此版本的第一次發行）</span><span class="sxs-lookup"><span data-stu-id="56331-208">**Revision of version:** 0 (first release of this version)</span></span>

## <span data-ttu-id="56331-209">深入了解</span><span class="sxs-lookup"><span data-stu-id="56331-209">Learn more</span></span>

- [<span data-ttu-id="56331-210">下載 Surface 的驅動程式和固件</span><span class="sxs-lookup"><span data-stu-id="56331-210">Download drivers and firmware for Surface</span></span>](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [<span data-ttu-id="56331-211">如何在 Configuration Manager 中管理 Surface driver 更新</span><span class="sxs-lookup"><span data-stu-id="56331-211">How to manage Surface driver updates in Configuration Manager</span></span>](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [<span data-ttu-id="56331-212">使用 Configuration Manager 部署應用程式</span><span class="sxs-lookup"><span data-stu-id="56331-212">Deploy applications with Configuration Manager</span></span>](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [<span data-ttu-id="56331-213">端點建構管理員檔</span><span class="sxs-lookup"><span data-stu-id="56331-213">Endpoint Configuration Manager documentation</span></span>](https://docs.microsoft.com/configmgr/)
- [<span data-ttu-id="56331-214">Microsoft 部署工具組檔</span><span class="sxs-lookup"><span data-stu-id="56331-214">Microsoft Deployment Toolkit documentation</span></span>](https://docs.microsoft.com/configmgr/mdt/)
- [<span data-ttu-id="56331-215">使用 Microsoft Deployment Toolkit 部署 Windows10</span><span class="sxs-lookup"><span data-stu-id="56331-215">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [<span data-ttu-id="56331-216">使用 Microsoft 部署工具組將 Windows 10 部署到 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="56331-216">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [<span data-ttu-id="56331-217">Surface UEFI 設定的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="56331-217">Intune management of Surface UEFI settings</span></span>](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- <span data-ttu-id="56331-218">[Ignite 2019：宣佈從 Intune 遠端系統管理 SURFACE UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。</span><span class="sxs-lookup"><span data-stu-id="56331-218">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>
- [<span data-ttu-id="56331-219">為 Windows10 更新建置部署更新步調</span><span class="sxs-lookup"><span data-stu-id="56331-219">Build deployment rings for Windows 10 updates</span></span>](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
