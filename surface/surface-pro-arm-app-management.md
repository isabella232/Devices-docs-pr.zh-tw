---
title: 部署、管理及維護 Surface Pro X
description: 本文概述部署、管理及維護 Surface Pro X 的重要考量。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/15/2021
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 30f7cd7d861b6497cd536aeb0ea348b6946a2674
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271357"
---
# <span data-ttu-id="4176f-103">部署、管理及維護 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="4176f-103">Deploying, managing, and servicing Surface Pro X</span></span>

## <span data-ttu-id="4176f-104">簡介</span><span class="sxs-lookup"><span data-stu-id="4176f-104">Introduction</span></span>

<span data-ttu-id="4176f-105">Surface Pro X 專為滿足高效能商業需求而打造，結合了該等級中空前強大的處理器 Microsoft SQ1 以及 Microsoft SQ1 ARM 晶片組，從而開創了全新的局面。</span><span class="sxs-lookup"><span data-stu-id="4176f-105">Built to handle high performance commercial requirements, Surface Pro X breaks new ground by incorporating the most powerful processors in its class, the Microsoft SQ1 and Microsoft SQ1 ARM chipsets.</span></span>

<span data-ttu-id="4176f-106">Surface Pro X 由 3GHz CPU 與 2.1 teraflop GPU 提供支援，讓您享有完整的 Windows 體驗。</span><span class="sxs-lookup"><span data-stu-id="4176f-106">Powered by a 3GHz CPU and a 2.1 teraflop GPU, Surface Pro X provides a full Windows experience.</span></span> <span data-ttu-id="4176f-107">電池使用時間長達 15 小時並且內建 Gigabit LTE，集觸控、手寫筆、平板電腦、和膝上型電腦為一身，非常適合金融、法律和醫學等領域的各類第一線員工及專業人員，或任何需要超長電池使用時間和持續連線功能的職務角色。</span><span class="sxs-lookup"><span data-stu-id="4176f-107">Its 15-hour battery life built-in Gigabit LTE and the versatility of touch, pen, tablet, and laptop make it ideally suited for mobile first-line workers and professionals across the financial, legal, and medical fields or any role demanding extended battery life and continuous connectivity capabilities.</span></span>

<span data-ttu-id="4176f-108">Surface Pro X 是專為現代化雲端式環境所設計，最適合與 Microsoft 365、Intune 和 Windows Autopilot 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="4176f-108">Surface Pro X is designed almost exclusively for a modern, cloud-based environment and works best when paired with Microsoft 365, Intune and Windows Autopilot.</span></span> <span data-ttu-id="4176f-109">本文將對具體內容多所著墨，並概述部署、管理及維護 Surface Pro X 的重要考量。</span><span class="sxs-lookup"><span data-stu-id="4176f-109">This article highlights what that looks like and outlines key considerations for deploying, managing, and servicing Surface Pro X.</span></span>

## <span data-ttu-id="4176f-110">部署 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="4176f-110">Deploying Surface Pro X</span></span>

<span data-ttu-id="4176f-111">為獲得最佳體驗，請使用 Windows Autopilot 在 Microsoft 雲端解決方案提供者的協助下部署 Surface Pro X，或是使用 Autopilot 部署設定檔和相關功能進行自我佈建。</span><span class="sxs-lookup"><span data-stu-id="4176f-111">For the best experience, deploy Surface Pro X using Windows Autopilot either with the assistance of a Microsoft Cloud Solution Provider or self-provisioned using Autopilot deployment profiles and related features.</span></span> <span data-ttu-id="4176f-112">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4176f-112">For more information, refer to:</span></span>

- [<span data-ttu-id="4176f-113">Windows Autopilot 與 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="4176f-113">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md)
- [<span data-ttu-id="4176f-114">Windows Autopilot 概觀</span><span class="sxs-lookup"><span data-stu-id="4176f-114">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

<span data-ttu-id="4176f-115">Autopilot 部署有幾個優點：允許您使用針對全自動部署所簡化的原廠佈建作業系統，將預先安裝的 Office Pro Plus 納入其中。</span><span class="sxs-lookup"><span data-stu-id="4176f-115">Autopilot deployment has several advantages: It allows you to use the factory provisioned operating system, streamlined for zero-touch deployment, to include pre-installation of Office Pro Plus.</span></span>

<span data-ttu-id="4176f-116">已經使用現代化管理、安全性及生產力解決方案的組織具備得天獨厚的優勢，可以利用 Surface Pro X 中特有的效能功能。使用現代化企業營運應用程式、Microsoft Store (UWP) 應用程式或遠端桌面解決方案的客戶也將受益匪淺。</span><span class="sxs-lookup"><span data-stu-id="4176f-116">Organizations already using modern management, security, and productivity solutions are well positioned to take advantage of the unique performance features in Surface Pro X. Customers using modernized line of business apps, Microsoft store (UWP) apps, or remote desktop solutions also stand to benefit.</span></span>

## <span data-ttu-id="4176f-117">映像式部署考量</span><span class="sxs-lookup"><span data-stu-id="4176f-117">Image-based deployment considerations</span></span>

<span data-ttu-id="4176f-118">Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager (舊稱 System Center Configuration Manager) 目前不支援 Surface Pro X 進行作業系統部署。</span><span class="sxs-lookup"><span data-stu-id="4176f-118">Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager (formerly System Center Configuration Manager) currently do not support Surface Pro X for operating system deployment.</span></span> <span data-ttu-id="4176f-119">在持續評估轉換至現代部署解決方案適當時機的期間，仰賴映像式部署的客戶不妨考慮 Surface Pro 7+。</span><span class="sxs-lookup"><span data-stu-id="4176f-119">Customers relying on image-based deployment should consider Surface Pro 7+ while they continue to evaluate the right time to transition to modern deployment solutions.</span></span> 

## <span data-ttu-id="4176f-120">管理 Surface Pro X 裝置</span><span class="sxs-lookup"><span data-stu-id="4176f-120">Managing Surface Pro X devices</span></span>

### <span data-ttu-id="4176f-121">Intune</span><span class="sxs-lookup"><span data-stu-id="4176f-121">Intune</span></span>

<span data-ttu-id="4176f-122">Intune 是 Microsoft Enterprise Mobility + Security 的元件，可與 Azure Active Directory 整合以進行身分識別和存取控制，並可提供對已註冊 Surface Pro X 裝置的細微管理。</span><span class="sxs-lookup"><span data-stu-id="4176f-122">A component of Microsoft Enterprise Mobility + Security, Intune integrates with Azure Active Directory for identity and access control and provides granular management of enrolled Surface Pro X devices.</span></span> <span data-ttu-id="4176f-123">Intune 行動裝置管理 (MDM) 原則與舊版內部部署工具 (例如 Windows 群組原則) 相比，具有許多優勢。</span><span class="sxs-lookup"><span data-stu-id="4176f-123">Intune mobile device management (MDM) policies have a number of advantages over older on-premises tools such as Windows Group Policy.</span></span> <span data-ttu-id="4176f-124">這包括更快速的裝置登入時間，以及更加簡化得可以完全從雲端管理裝置的原則資料目錄。</span><span class="sxs-lookup"><span data-stu-id="4176f-124">This includes faster device login times and a more streamlined catalog of policies enabling full device management from the cloud.</span></span> <span data-ttu-id="4176f-125">例如，您可以使用 eSIM 設定檔管理 LTE 以設定行動數據方案，並將啟動碼部署至多個裝置。</span><span class="sxs-lookup"><span data-stu-id="4176f-125">For example, you can manage LTE using eSIM profiles to configure data plans and deploy activation codes to multiple devices.</span></span><br> 

<span data-ttu-id="4176f-126">如需有關使用 Intune 的詳細資訊，請參閱 [Intune 文件](https://docs.microsoft.com/intune/)。</span><span class="sxs-lookup"><span data-stu-id="4176f-126">For more information about using Intune, refer to the [Intune documentation](https://docs.microsoft.com/intune/).</span></span>

### <span data-ttu-id="4176f-127">共同管理</span><span class="sxs-lookup"><span data-stu-id="4176f-127">Co-management</span></span>

<span data-ttu-id="4176f-128">使用 Autopilot 進行部署後，您可以將 Surface Pro X 裝置加入 Azure AD 或 Active Directory (混合式 Azure AD Join)，這樣就能在其中使用 Intune 來管理裝置，或是使用 Endpoint Configuration Manager (將會安裝 32 位元 x86 ConfigMgr 用戶端) 來共同管理這些裝置。</span><span class="sxs-lookup"><span data-stu-id="4176f-128">Once deployed in Autopilot, you can join Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join) where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.</span></span>

### <span data-ttu-id="4176f-129">協力廠商 MDM 解決方案</span><span class="sxs-lookup"><span data-stu-id="4176f-129">Third party MDM solutions</span></span>

<span data-ttu-id="4176f-130">您或許可以使用協力廠商 MDM 工具來管理 Surface Pro X 裝置。</span><span class="sxs-lookup"><span data-stu-id="4176f-130">You may be able to use third-party MDM tools to manage Surface Pro X devices.</span></span> <span data-ttu-id="4176f-131">如需詳細資訊，請連絡 MDM 提供者。</span><span class="sxs-lookup"><span data-stu-id="4176f-131">For details, contact your MDM provider.</span></span>

### <span data-ttu-id="4176f-132">防毒軟體</span><span class="sxs-lookup"><span data-stu-id="4176f-132">Antivirus software</span></span>

<span data-ttu-id="4176f-133">Windows Defender 會在 Windows 10 裝置的支援期間協助保護 ARM 型電腦上的 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="4176f-133">Windows Defender will help protect Windows 10 on ARM-based PCs for the supported lifetime of the Windows 10 device.</span></span> 

<span data-ttu-id="4176f-134">部分協力廠商防毒軟體無法安裝在使用 ARM 型處理器執行的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="4176f-134">Some third-party antivirus software cannot be installed on a Windows 10 PC running on an ARM-based processor.</span></span> <span data-ttu-id="4176f-135">仍持續與協力廠商防毒軟體提供者進行合作，處理防毒應用程式在 ARM 型電腦上的整備工作。</span><span class="sxs-lookup"><span data-stu-id="4176f-135">Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs.</span></span> <span data-ttu-id="4176f-136">請連絡防毒軟體提供者，以了解他們的應用程式何時會推出。</span><span class="sxs-lookup"><span data-stu-id="4176f-136">Contact your antivirus software provider to understand when their apps will be available.</span></span>

## <span data-ttu-id="4176f-137">維護 Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="4176f-137">Servicing Surface Pro X</span></span>

<span data-ttu-id="4176f-138">Surface Pro X 會附帶 Windows 10 版本 2004，且支援 Windows 10 版本 1903 和更新的版本。</span><span class="sxs-lookup"><span data-stu-id="4176f-138">Surface Pro X ships with Windows 10 version 2004 and supports Windows 10, version 1903 and later.</span></span> <span data-ttu-id="4176f-139">由於是 ARM 型裝置，此產品在維持最新驅動程式和韌體方面有特定需求。</span><span class="sxs-lookup"><span data-stu-id="4176f-139">As an ARM-based device, it has specific requirements for maintaining the latest drivers and firmware.</span></span> 

<span data-ttu-id="4176f-140">Surface Pro X 已設計成使用 Windows Update 來為家庭使用者和小型企業使用者簡化保持驅動程式及韌體處於最新狀態的程序。</span><span class="sxs-lookup"><span data-stu-id="4176f-140">Surface Pro X was designed to use Windows Update to simplify the process of keeping drivers and firmware up to date for both home users and small business users.</span></span> <span data-ttu-id="4176f-141">使用預設的設定來接收自動更新。</span><span class="sxs-lookup"><span data-stu-id="4176f-141">Use the default settings to receive Automatic updates.</span></span>  <span data-ttu-id="4176f-142">若要確認：</span><span class="sxs-lookup"><span data-stu-id="4176f-142">To verify:</span></span>

1. <span data-ttu-id="4176f-143">移至 **\[開始\]** > **\[設定\] > \[更新與安全性\] > \[Windows Update\]** > **\[進階選項\]**。</span><span class="sxs-lookup"><span data-stu-id="4176f-143">Go to **Start** > **Settings > Update & Security > Windows Update** > **Advanced Options.**</span></span>
2. <span data-ttu-id="4176f-144">在 **\[擇更新安裝方式\]** 下方選取 **\[自動 (建議選項)\]**。</span><span class="sxs-lookup"><span data-stu-id="4176f-144">Under **Choose how updates are installed,** select **Automatic (recommended)**.</span></span>

### <span data-ttu-id="4176f-145">對商業客戶的建議</span><span class="sxs-lookup"><span data-stu-id="4176f-145">Recommendations for commercial customers</span></span>

- <span data-ttu-id="4176f-146">使用 Windows Update 或商務用 Windows Update 來維護最新的驅動程式和韌體。</span><span class="sxs-lookup"><span data-stu-id="4176f-146">Use Windows Update or Windows Update for Business for maintaining the latest drivers and firmware.</span></span> <span data-ttu-id="4176f-147">如需詳細資訊，請參閱[使用商務用 Windows Update 來部署更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)。</span><span class="sxs-lookup"><span data-stu-id="4176f-147">For more information, see [Deploy Updates using Windows Update for Business](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb).</span></span>
- <span data-ttu-id="4176f-148">如需有關在 Surface 裝置上部署和管理更新的詳細資訊，請參閱[管理和部署 Surface 驅動程式與韌體更新](manage-surface-driver-and-firmware-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="4176f-148">For more information about deploying and managing updates on Surface devices, see [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span>
- <span data-ttu-id="4176f-149">請注意，Windows Server Update Services (WSUS) 不支援傳遞驅動程式和韌體至 Surface Pro X 的功能。</span><span class="sxs-lookup"><span data-stu-id="4176f-149">Note that Windows Server Update Services (WSUS) does not support the ability to deliver drivers and firmware to Surface Pro X.</span></span>

## <span data-ttu-id="4176f-150">在 Surface Pro X 上執行應用程式</span><span class="sxs-lookup"><span data-stu-id="4176f-150">Running apps on Surface Pro X</span></span>

<span data-ttu-id="4176f-151">除了少數例外，大部分應用程式都會在 ARM 型 Windows 10 電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="4176f-151">Most apps run on ARM-based Windows 10 PCs with limited exclusions.</span></span>

### <span data-ttu-id="4176f-152">支援的應用程式</span><span class="sxs-lookup"><span data-stu-id="4176f-152">Supported apps</span></span>

- <span data-ttu-id="4176f-153">大部分 x86 Win32 應用程式會在 Surface Pro X 上執行。</span><span class="sxs-lookup"><span data-stu-id="4176f-153">Most x86 Win32 apps run on Surface Pro X.</span></span>
- <span data-ttu-id="4176f-154">原生 ARM64 和 Microsoft Store UWP 應用程式在最佳化電池使用時間的同時，利用 ARM 型處理器的完整原生速度提供絕佳使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="4176f-154">Native ARM64 and Microsoft Store UWP apps provide an excellent user experience utilizing the full native speed of the ARM-based processor while optimizing battery life.</span></span>
- <span data-ttu-id="4176f-155">使用專為透過 ARM 型處理器執行之 Windows 10 電腦所設計的驅動程式的應用程式。</span><span class="sxs-lookup"><span data-stu-id="4176f-155">Apps that use drivers designed for a Windows 10 PC running on an ARM-based processor.</span></span>

> [!NOTE]
> <span data-ttu-id="4176f-156">使用預覽版中透過 Windows 測試人員計畫即將推出的 64 位元模擬，您就能在 Surface Pro X 上執行 64 位元 (x64) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4176f-156">With 64-bit emulation coming soon in Preview via the Windows Insider program, you'll be able to run 64-bit (x64) apps on Surface Pro X.</span></span>

### <span data-ttu-id="4176f-157">FastTrack 應用程式 Assure</span><span class="sxs-lookup"><span data-stu-id="4176f-157">FastTrack App Assure</span></span> 

<span data-ttu-id="4176f-158">The App Assure 計劃可供商業客戶用於 ARM 上針對 Windows 10 的 LOB、ISV 和 Microsoft 第一方應用程。</span><span class="sxs-lookup"><span data-stu-id="4176f-158">The App Assure program is available to commercial customers for their LOB, ISV and Microsoft first-party apps targeting Windows 10 on ARM.</span></span> <span data-ttu-id="4176f-159">如果商業客戶在 ARM 上使用 Windows 10 發生應用程式相容性問題，Microsoft 會提供開發人員資源，以便在不額外付費的情況下，進行疑難排解和協助修復應用程式。</span><span class="sxs-lookup"><span data-stu-id="4176f-159">If commercial customers encounter an app compatibility issue using Windows 10 on ARM, Microsoft will provide developer resources to troubleshoot and assist with app remediations, at no additional cost.</span></span> <span data-ttu-id="4176f-160">若要深入瞭解，請瀏覽 [aka.ms/AppAssure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure) (英文)。</span><span class="sxs-lookup"><span data-stu-id="4176f-160">To learn more,visit [aka.ms/AppAssure](https://docs.microsoft.com/fasttrack/products-and-capabilities#app-assure).</span></span>

<span data-ttu-id="4176f-161">如需有關在 Surface Pro X 上執行應用程式的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4176f-161">For more information about running apps on Surface Pro X, refer to:</span></span>

- [<span data-ttu-id="4176f-162">Windows 10 ARM 型電腦支援常見問題集</span><span class="sxs-lookup"><span data-stu-id="4176f-162">Windows 10 ARM-based PCs Support FAQ</span></span>](https://support.microsoft.com/help/4521606)
- [<span data-ttu-id="4176f-163">ARM 上的 Windows 10 文件</span><span class="sxs-lookup"><span data-stu-id="4176f-163">Windows 10 on ARM documentation</span></span>](https://docs.microsoft.com/windows/arm)

## <span data-ttu-id="4176f-164">虛擬桌面 (VDI)</span><span class="sxs-lookup"><span data-stu-id="4176f-164">Virtual Desktops (VDI)</span></span>

<span data-ttu-id="4176f-165">Windows 虛擬桌面可讓您在任何運算裝置或平台上，從任何位置存取 Windows 桌面、應用程式和資料</span><span class="sxs-lookup"><span data-stu-id="4176f-165">Windows Virtual Desktop enables access to Windows desktops,applications, and data on any computing device or platform, from any location.</span></span> <span data-ttu-id="4176f-166">若要深入了解，請參閱 [Windows 虛擬桌面網站](https://aka.ms/wvd)。</span><span class="sxs-lookup"><span data-stu-id="4176f-166">To learn more, refer to the [Windows Virtual Desktop site](https://aka.ms/wvd).</span></span> 

## <span data-ttu-id="4176f-167">使用 Surface Pro X 進行瀏覽</span><span class="sxs-lookup"><span data-stu-id="4176f-167">Browsing with Surface Pro X</span></span>

<span data-ttu-id="4176f-168">在 Surface Pro X 上執行的熱門瀏覽器：</span><span class="sxs-lookup"><span data-stu-id="4176f-168">Popular browsers run on Surface Pro X:</span></span>

- <span data-ttu-id="4176f-169">內建 Edge、Firefox、Chrome 和 Internet Explorer 都可在 Surface Pro X 上執行。</span><span class="sxs-lookup"><span data-stu-id="4176f-169">In-box Edge, Firefox, Chrome, and Internet Explorer all run on Surface Pro X.</span></span>
- <span data-ttu-id="4176f-170">以 Chromium 為基礎的內建 Firefox 和 Microsoft Edge 以原生方式執行，因此效能在使用 ARM 型處理器的 Windows 10 電腦上有所提升。</span><span class="sxs-lookup"><span data-stu-id="4176f-170">Firefox and Microsoft Edge based on Chromium run natively and therefore have enhanced performance on a Windows 10 PC on an ARM-based processor.</span></span>

## <span data-ttu-id="4176f-171">安裝和使用 Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="4176f-171">Installing and using Microsoft Office</span></span>

- <span data-ttu-id="4176f-172">在使用 ARM 型處理器的 Windows 10 電腦上使用 Office 365 可獲得最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="4176f-172">Use Office 365 for the best experience on a Windows 10 PC on an ARM-based processor.</span></span>
- <span data-ttu-id="4176f-173">Office 365「隨選即用」會安裝 Outlook、Word、Excel 和 PowerPoint，並已經過最佳化，可在使用 ARM 型處理器的 Windows 10 電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="4176f-173">Office 365 "click-to-run" installs Outlook, Word, Excel, and PowerPoint, optimized to run on a Windows 10 PC on an ARM-based processor.</span></span>
- <span data-ttu-id="4176f-174">Microsoft Teams 在 Surface Pro X 上的執行效能絕佳。</span><span class="sxs-lookup"><span data-stu-id="4176f-174">Microsoft Teams runs great on Surface Pro X.</span></span>
- <span data-ttu-id="4176f-175">對於 Office 的「永久版本」(例如 Office 2019)，請安裝 32 位元版本。</span><span class="sxs-lookup"><span data-stu-id="4176f-175">For "perpetual versions" of Office such as Office 2019, install the 32-bit version.</span></span>

## <span data-ttu-id="4176f-176">VPN</span><span class="sxs-lookup"><span data-stu-id="4176f-176">VPN</span></span>

<span data-ttu-id="4176f-177">若要確認特定協力廠商 VPN 是否支援使用 ARM 型處理器的 Windows 10 電腦，請連絡 VPN 提供者。</span><span class="sxs-lookup"><span data-stu-id="4176f-177">To confirm if a specific third-party VPN supports a Windows 10 PC on an ARM-based processor, contact the VPN provider.</span></span>

## <span data-ttu-id="4176f-178">重點摘要</span><span class="sxs-lookup"><span data-stu-id="4176f-178">Feature summary</span></span>

<span data-ttu-id="4176f-179">下表顯示 Surface Pro X 在配合 ARM 上的 Windows 10 使用時，可用的特選關鍵功能。</span><span class="sxs-lookup"><span data-stu-id="4176f-179">The following tables show the availability of selected key features on Surface Pro X with Windows 10 on ARM.</span></span>


**<span data-ttu-id="4176f-180">部署</span><span class="sxs-lookup"><span data-stu-id="4176f-180">Deployment</span></span>**

| <span data-ttu-id="4176f-181">功能</span><span class="sxs-lookup"><span data-stu-id="4176f-181">Feature</span></span>                                                           | <span data-ttu-id="4176f-182">是/否</span><span class="sxs-lookup"><span data-stu-id="4176f-182">Y/N</span></span> | <span data-ttu-id="4176f-183">附註</span><span class="sxs-lookup"><span data-stu-id="4176f-183">Notes</span></span>                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="4176f-184">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="4176f-184">Windows Autopilot</span></span>                                                 | <span data-ttu-id="4176f-185">是</span><span class="sxs-lookup"><span data-stu-id="4176f-185">Yes</span></span> |                                                                                                                                   |
| <span data-ttu-id="4176f-186">支援網路開機 (PXE)</span><span class="sxs-lookup"><span data-stu-id="4176f-186">Support for Network Boot (PXE)</span></span>                                    | <span data-ttu-id="4176f-187">否</span><span class="sxs-lookup"><span data-stu-id="4176f-187">No</span></span>  |                                                                                                                                   |
| <span data-ttu-id="4176f-188">Windows 設定設計工具</span><span class="sxs-lookup"><span data-stu-id="4176f-188">Windows Configuration Designer</span></span>                                    | <span data-ttu-id="4176f-189">否</span><span class="sxs-lookup"><span data-stu-id="4176f-189">No</span></span>  | <span data-ttu-id="4176f-190">不建議用於 Surface Pro X。</span><span class="sxs-lookup"><span data-stu-id="4176f-190">Not recommended for Surface Pro X.</span></span>                                                                                                |
| <span data-ttu-id="4176f-191">WinPE</span><span class="sxs-lookup"><span data-stu-id="4176f-191">WinPE</span></span>                                                             | <span data-ttu-id="4176f-192">是</span><span class="sxs-lookup"><span data-stu-id="4176f-192">Yes</span></span> | <span data-ttu-id="4176f-193">不建議用於 Surface Pro X。Microsoft 不提供支援與 WinPE 搭配使用 Surface Pro X 所需的 .ISO 和驅動程式。</span><span class="sxs-lookup"><span data-stu-id="4176f-193">Not recommended for Surface Pro X. Microsoft does not provide the necessary .ISO and drivers to support WinPE with Surface Pro X.</span></span> |
| <span data-ttu-id="4176f-194">Endpoint Configuration Manager：作業系統部署 (OSD)</span><span class="sxs-lookup"><span data-stu-id="4176f-194">Endpoint Configuration Manager: Operating System Deployment (OSD)</span></span> | <span data-ttu-id="4176f-195">否</span><span class="sxs-lookup"><span data-stu-id="4176f-195">No</span></span>  | <span data-ttu-id="4176f-196">在 Surface Pro X 上不支援。</span><span class="sxs-lookup"><span data-stu-id="4176f-196">Not supported on Surface Pro X.</span></span>                                                                                                   |
| <span data-ttu-id="4176f-197">MDT</span><span class="sxs-lookup"><span data-stu-id="4176f-197">MDT</span></span>                                                               | <span data-ttu-id="4176f-198">否</span><span class="sxs-lookup"><span data-stu-id="4176f-198">No</span></span>  | <span data-ttu-id="4176f-199">在 Surface Pro X 上不支援。</span><span class="sxs-lookup"><span data-stu-id="4176f-199">Not supported on Surface Pro X.</span></span>                                                                                                   |

 
 
 **<span data-ttu-id="4176f-200">Management</span><span class="sxs-lookup"><span data-stu-id="4176f-200">Management</span></span>**
 

| <span data-ttu-id="4176f-201">功能</span><span class="sxs-lookup"><span data-stu-id="4176f-201">Feature</span></span>                                       | <span data-ttu-id="4176f-202">是/否</span><span class="sxs-lookup"><span data-stu-id="4176f-202">Y/N</span></span>     | <span data-ttu-id="4176f-203">附註</span><span class="sxs-lookup"><span data-stu-id="4176f-203">Notes</span></span>                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="4176f-204">Intune</span><span class="sxs-lookup"><span data-stu-id="4176f-204">Intune</span></span>                                        | <span data-ttu-id="4176f-205">是</span><span class="sxs-lookup"><span data-stu-id="4176f-205">Yes</span></span>     | <span data-ttu-id="4176f-206">使用 eSIM 設定檔管理 LTE。</span><span class="sxs-lookup"><span data-stu-id="4176f-206">Manage LTE with eSIM profiles.</span></span>                                                        |
| <span data-ttu-id="4176f-207">Windows Autopilot</span><span class="sxs-lookup"><span data-stu-id="4176f-207">Windows Autopilot</span></span>                             | <span data-ttu-id="4176f-208">是</span><span class="sxs-lookup"><span data-stu-id="4176f-208">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="4176f-209">Azure AD (共同管理)</span><span class="sxs-lookup"><span data-stu-id="4176f-209">Azure AD (co-management)</span></span>                      | <span data-ttu-id="4176f-210">是</span><span class="sxs-lookup"><span data-stu-id="4176f-210">Yes</span></span>     | <span data-ttu-id="4176f-211">將 Surface Pro X 加入 Azure AD 或 Active Directory (混合式 Azure AD Join) 的功能。</span><span class="sxs-lookup"><span data-stu-id="4176f-211">Ability to join Surface Pro X to Azure AD or Active Directory (Hybrid Azure AD Join).</span></span> |
| <span data-ttu-id="4176f-212">Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4176f-212">Endpoint Configuration Manager</span></span>                | <span data-ttu-id="4176f-213">是</span><span class="sxs-lookup"><span data-stu-id="4176f-213">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="4176f-214">AC 恢復時開啟電源</span><span class="sxs-lookup"><span data-stu-id="4176f-214">Power on When AC Restore</span></span>                      | <span data-ttu-id="4176f-215">是</span><span class="sxs-lookup"><span data-stu-id="4176f-215">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="4176f-216">商務用 Surface 診斷工具組 (SDT)</span><span class="sxs-lookup"><span data-stu-id="4176f-216">Surface Diagnostic Toolkit (SDT) for Business</span></span> | <span data-ttu-id="4176f-217">是</span><span class="sxs-lookup"><span data-stu-id="4176f-217">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="4176f-218">Surface 資產標記工具</span><span class="sxs-lookup"><span data-stu-id="4176f-218">Surface Asset Tag tool</span></span>                        | <span data-ttu-id="4176f-219">是</span><span class="sxs-lookup"><span data-stu-id="4176f-219">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="4176f-220">Surface 企業管理模式 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="4176f-220">Surface Enterprise management Mode (SEMM)</span></span>     | <span data-ttu-id="4176f-221">部分</span><span class="sxs-lookup"><span data-stu-id="4176f-221">Partial</span></span> | <span data-ttu-id="4176f-222">Surface Pro X 沒有在韌體層級停用硬體的選項。</span><span class="sxs-lookup"><span data-stu-id="4176f-222">No option to disable hardware on Surface Pro X at the firmware level.</span></span>                 |
| <span data-ttu-id="4176f-223">Surface UEFI 設定程式</span><span class="sxs-lookup"><span data-stu-id="4176f-223">Surface UEFI Configurator</span></span>                     | <span data-ttu-id="4176f-224">否</span><span class="sxs-lookup"><span data-stu-id="4176f-224">No</span></span>      | <span data-ttu-id="4176f-225">沒有停用硬體的選項。</span><span class="sxs-lookup"><span data-stu-id="4176f-225">No option to disable hardware.</span></span> <span data-ttu-id="4176f-226">在 Surface Pro X 的韌體層級上。</span><span class="sxs-lookup"><span data-stu-id="4176f-226">on Surface Pro X at the firmware level.</span></span>                |
| <span data-ttu-id="4176f-227">Surface UEFI 管理員</span><span class="sxs-lookup"><span data-stu-id="4176f-227">Surface UEFI Manager</span></span>                          | <span data-ttu-id="4176f-228">部分</span><span class="sxs-lookup"><span data-stu-id="4176f-228">Partial</span></span> | <span data-ttu-id="4176f-229">Surface Pro X 沒有在韌體層級停用硬體的選項。</span><span class="sxs-lookup"><span data-stu-id="4176f-229">No option to disable hardware on Surface Pro X at the firmware level.</span></span>                 |

 

**<span data-ttu-id="4176f-230">安全性</span><span class="sxs-lookup"><span data-stu-id="4176f-230">Security</span></span>**
 

 <span data-ttu-id="4176f-231">功能</span><span class="sxs-lookup"><span data-stu-id="4176f-231">Feature</span></span>                                       | <span data-ttu-id="4176f-232">是/否</span><span class="sxs-lookup"><span data-stu-id="4176f-232">Y/N</span></span>     | <span data-ttu-id="4176f-233">附註</span><span class="sxs-lookup"><span data-stu-id="4176f-233">Notes</span></span>                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| <span data-ttu-id="4176f-234">BitLocker</span><span class="sxs-lookup"><span data-stu-id="4176f-234">BitLocker</span></span>                                     | <span data-ttu-id="4176f-235">是</span><span class="sxs-lookup"><span data-stu-id="4176f-235">Yes</span></span>     |                                                       |
| <span data-ttu-id="4176f-236">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="4176f-236">Windows Defender</span></span>                              | <span data-ttu-id="4176f-237">是</span><span class="sxs-lookup"><span data-stu-id="4176f-237">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="4176f-238">支援協力廠商防毒軟體</span><span class="sxs-lookup"><span data-stu-id="4176f-238">Support for third-party antivirus</span></span>             | <span data-ttu-id="4176f-239">請參閱附註</span><span class="sxs-lookup"><span data-stu-id="4176f-239">See note</span></span>| <span data-ttu-id="4176f-240">部分協力廠商防毒軟體無法安裝在使用 ARM 型處理器執行的 Windows 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="4176f-240">Some third-party antivirus software cannot be installed on a Windows 10 PC running on an ARM-based processor.</span></span> <span data-ttu-id="4176f-241">仍持續與協力廠商防毒軟體提供者進行合作，處理防毒應用程式在 ARM 型電腦上的整備工作。</span><span class="sxs-lookup"><span data-stu-id="4176f-241">Collaboration with third-party antivirus software providers is continuing for AV app readiness on ARM-based PCs.</span></span> <span data-ttu-id="4176f-242">請連絡防毒軟體提供者，以了解他們的應用程式何時會推出。</span><span class="sxs-lookup"><span data-stu-id="4176f-242">Contact your antivirus software provider to understand when their apps will be available.</span></span> |
| <span data-ttu-id="4176f-243">安全開機</span><span class="sxs-lookup"><span data-stu-id="4176f-243">Secure Boot</span></span>               | <span data-ttu-id="4176f-244">是</span><span class="sxs-lookup"><span data-stu-id="4176f-244">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="4176f-245">Windows 資訊保護</span><span class="sxs-lookup"><span data-stu-id="4176f-245">Windows Information Protection</span></span>                      | <span data-ttu-id="4176f-246">是</span><span class="sxs-lookup"><span data-stu-id="4176f-246">Yes</span></span>     |                                                                                       |
| <span data-ttu-id="4176f-247">Surface Data Eraser (SDE)</span><span class="sxs-lookup"><span data-stu-id="4176f-247">Surface Data Eraser (SDE)</span></span>     | <span data-ttu-id="4176f-248">是</span><span class="sxs-lookup"><span data-stu-id="4176f-248">Yes</span></span>     |                                                                                       |




## <span data-ttu-id="4176f-249">常見問題集</span><span class="sxs-lookup"><span data-stu-id="4176f-249">FAQ</span></span>

### <span data-ttu-id="4176f-250">是否可以使用 MDT 或 Endpoint Configuration Manager 來部署 Surface Pro X？</span><span class="sxs-lookup"><span data-stu-id="4176f-250">Can I deploy Surface Pro X with MDT or Endpoint Configuration Manager?</span></span>

<span data-ttu-id="4176f-251">Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager 目前不支援 Surface Pro X 進行作業系統部署。</span><span class="sxs-lookup"><span data-stu-id="4176f-251">The Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager  currently do not support Surface Pro X for operating system deployment.</span></span> <span data-ttu-id="4176f-252">仰賴映像式部署的客戶在持續評估轉換至雲端適當時機的期間，應考慮使用 Surface Pro 7+。</span><span class="sxs-lookup"><span data-stu-id="4176f-252">Customers relying on image-based deployment should consider Surface Pro 7+ while they continue to evaluate the right time to transition to the cloud.</span></span>

### <span data-ttu-id="4176f-253">如何部署 Surface Pro X？</span><span class="sxs-lookup"><span data-stu-id="4176f-253">How can I deploy Surface Pro X?</span></span>

<span data-ttu-id="4176f-254">使用 Windows Autopilot 來部署 Surface Pro X。</span><span class="sxs-lookup"><span data-stu-id="4176f-254">Deploy Surface Pro X using Windows Autopilot.</span></span>

### <span data-ttu-id="4176f-255">可以使用 BMR 嗎？</span><span class="sxs-lookup"><span data-stu-id="4176f-255">Is a BMR available?</span></span>

<span data-ttu-id="4176f-256">是，請參閱 [下載 Surface 的復原影像](https://support.microsoft.com/surfacerecoveryimage).。</span><span class="sxs-lookup"><span data-stu-id="4176f-256">Yes, refer to [Download a recovery image for your Surface](https://support.microsoft.com/surfacerecoveryimage).</span></span>

### <span data-ttu-id="4176f-257">是否必須有 Intune 才能管理 Surface Pro X？</span><span class="sxs-lookup"><span data-stu-id="4176f-257">Is Intune required to manage Surface Pro X?</span></span>

<span data-ttu-id="4176f-258">建議使用 Intune，但並非必要。</span><span class="sxs-lookup"><span data-stu-id="4176f-258">Intune is recommended but not required.</span></span> <span data-ttu-id="4176f-259">使用 Autopilot 進行部署後，您可以將 Surface Pro X 裝置加入 Azure AD 或 Active Directory (混合式 Azure AD Join)，這樣就能在其中使用 Intune 來管理裝置，或是使用 Endpoint Configuration Manager (將會安裝 32 位元 x86 ConfigMgr 用戶端) 來共同管理這些裝置。</span><span class="sxs-lookup"><span data-stu-id="4176f-259">Once deployed in Autopilot, you can join Surface Pro X devices to Azure AD or Active Directory (Hybrid Azure AD Join) where you will be able to manage the devices with Intune or co-manage them with Endpoint Configuration Manager, which will install the 32-bit x86 ConfigMgr client.</span></span>
