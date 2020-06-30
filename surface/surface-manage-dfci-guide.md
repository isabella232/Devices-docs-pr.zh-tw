---
title: Surface UEFI 設定的 Intune 管理
description: 本文說明如何在 Microsoft Intune 中設定 DFCI 環境，以及如何管理目標 Surface 裝置的固件設定。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 11/13/2019
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 0aa69bb229f0d76972620bc58f236e43e03075b2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831520"
---
# <span data-ttu-id="fc182-103">Surface UEFI 設定的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="fc182-103">Intune management of Surface UEFI settings</span></span>

## <span data-ttu-id="fc182-104">簡介</span><span class="sxs-lookup"><span data-stu-id="fc182-104">Introduction</span></span>

<span data-ttu-id="fc182-105">從雲端管理裝置的能力在整個生命週期中大大簡化 IT 部署與資源調配。</span><span class="sxs-lookup"><span data-stu-id="fc182-105">The ability to manage devices from the cloud has dramatically simplified IT deployment and provisioning across the lifecycle.</span></span> <span data-ttu-id="fc182-106">在內置於 Microsoft Intune 中的裝置固件配置介面（DFCI）設定檔（現已在[公用預覽](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)中提供），Surface UEFI 管理會將新式管理堆疊延伸到 UEFI 硬體層級。</span><span class="sxs-lookup"><span data-stu-id="fc182-106">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in [public preview](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="fc182-107">DFCI 支援零觸控配，消除 BIOS 密碼，提供安全性設定（包括啟動選項和內建週邊設備）的控制權，並針對未來的高級安全性案例奠定基礎。</span><span class="sxs-lookup"><span data-stu-id="fc182-107">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="fc182-108">如需常見問題的解答，請參閱[Ignite 2019：宣佈從 Intune 遠端系統管理 SURFACE UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。</span><span class="sxs-lookup"><span data-stu-id="fc182-108">For answers to frequently asked questions, see [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

### <span data-ttu-id="fc182-109">背景</span><span class="sxs-lookup"><span data-stu-id="fc182-109">Background</span></span>

<span data-ttu-id="fc182-110">就像任何執行 Windows 10 的電腦一樣，Surface 裝置都依賴儲存在 SoC 中的程式碼，讓 CPU 能夠與硬碟進行介面、顯示裝置、USB 埠及其他裝置。</span><span class="sxs-lookup"><span data-stu-id="fc182-110">Like any computer running Windows 10, Surface devices rely on code stored in the SoC that enables the CPU to interface with hard drives, display devices, USB ports, and other devices.</span></span> <span data-ttu-id="fc182-111">儲存在這個唯讀記憶體（ROM）中的程式稱為固件（而儲存在動態媒體中的程式稱為軟體）。</span><span class="sxs-lookup"><span data-stu-id="fc182-111">The programs stored in this read-only memory (ROM) are known as firmware (while programs stored in dynamic media are known as software).</span></span>

<span data-ttu-id="fc182-112">與目前市場上提供的其他 Windows 10 裝置相比，Surface 提供 IT 管理員能夠透過一組豐富的 UEFI 設定設定來設定及管理固件。</span><span class="sxs-lookup"><span data-stu-id="fc182-112">In contrast to other Windows 10 devices available in the market today, Surface provides IT admins with the ability to configure and manage firmware through a rich set of UEFI configuration settings.</span></span> <span data-ttu-id="fc182-113">這會在以軟體為基礎的原則管理（透過行動裝置管理（MDM）原則、Configuration Manager 或群組原則）中提供一個層級的硬體控制。</span><span class="sxs-lookup"><span data-stu-id="fc182-113">This provides a layer of hardware control on top of software-based policy management as implemented via mobile device management (MDM) policies, Configuration Manager or Group Policy.</span></span> <span data-ttu-id="fc182-114">例如，在高度安全的區域中部署含機密資訊的裝置，可以移除硬體層級的功能，以避免相機的使用。</span><span class="sxs-lookup"><span data-stu-id="fc182-114">For example, organizations deploying devices in highly secure areas with sensitive information can prevent camera use by removing functionality at the hardware level.</span></span> <span data-ttu-id="fc182-115">從裝置的角度來看，透過固件設定將攝像頭關閉，相當於實際移除相機。</span><span class="sxs-lookup"><span data-stu-id="fc182-115">From a device standpoint, turning the camera off via a firmware setting is equivalent to physically removing the camera.</span></span> <span data-ttu-id="fc182-116">比較在固件層級管理所增加的安全性，只依賴作業系統軟體設定。</span><span class="sxs-lookup"><span data-stu-id="fc182-116">Compare the added security of managing at the firmware level to relying only on operating system software settings.</span></span> <span data-ttu-id="fc182-117">例如，如果您透過網域環境中的原則設定停用 Windows 音訊服務，本機管理員仍可重新啟用服務。</span><span class="sxs-lookup"><span data-stu-id="fc182-117">For example, if you disable the Windows audio service via a policy setting in a domain environment, a local admin could still re-enable the service.</span></span>

### <span data-ttu-id="fc182-118">DFCI 與 SEMM</span><span class="sxs-lookup"><span data-stu-id="fc182-118">DFCI versus SEMM</span></span>

<span data-ttu-id="fc182-119">到目前為止，管理固件所需的將裝置註冊裝置至 Surface Enterprise 管理模式（SEMM），以及持續進行手動 IT 密集型工作的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="fc182-119">Until now, managing firmware required enrolling devices into Surface Enterprise Management Mode (SEMM) with the overhead of ongoing manual IT-intensive tasks.</span></span> <span data-ttu-id="fc182-120">例如，SEMM 需要 IT 員工以實際方式存取每個電腦，以在證書管理程式中輸入兩位數的 pin。</span><span class="sxs-lookup"><span data-stu-id="fc182-120">As an example, SEMM requires IT staff to physically access each PC to enter a two-digit pin as part of the certificate management process.</span></span> <span data-ttu-id="fc182-121">雖然 SEMM 對於嚴格內部部署環境中的組織而言是一個不錯的解決方案，但其複雜性和 IT 密集型需求都能讓使用成本變得非常昂貴。</span><span class="sxs-lookup"><span data-stu-id="fc182-121">Although SEMM remains a good solution for organizations in a strictly on-premises environment, its complexity and IT-intensive requirements make it costly to use.</span></span>

<span data-ttu-id="fc182-122">現在，您可以在 Microsoft Intune 中使用新的整合式 UEFI 固件管理功能，在單一主機中進行提供、安全性和精簡更新等新功能，讓您能更輕鬆地使用鎖定硬體的功能，現在已與[Microsoft 端點管理員](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)整合</span><span class="sxs-lookup"><span data-stu-id="fc182-122">Now with newly integrated UEFI firmware management capabilities in Microsoft Intune, the ability to lock down hardware is simplified and easier to use with new features for provisioning, security, and streamlined updating all in a single console, now unified as [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span> <span data-ttu-id="fc182-123">下圖顯示直接在裝置上查看的 UEFI 設定（左圖），以及在端點管理器主控台（右側）查看。</span><span class="sxs-lookup"><span data-stu-id="fc182-123">The following figure shows UEFI settings viewed directly on the device (left) and viewed in the Endpoint Manager console (right).</span></span>

![在裝置（左）和端點管理員主控台（右側）中顯示的 UEFI 設定](images/uefidfci.png)

<span data-ttu-id="fc182-125">Crucially、DFCI 啟用零觸控管理，不需要 IT 系統管理員手動互動。</span><span class="sxs-lookup"><span data-stu-id="fc182-125">Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins.</span></span> <span data-ttu-id="fc182-126">DFCI 是透過 Windows Autopilot 使用 Intune 中的裝置設定檔功能來部署。</span><span class="sxs-lookup"><span data-stu-id="fc182-126">DFCI is deployed via Windows Autopilot using the device profiles capability in Intune.</span></span> <span data-ttu-id="fc182-127">裝置設定檔可讓您新增並設定設定，然後將這些設定部署至在組織內註冊管理的裝置。</span><span class="sxs-lookup"><span data-stu-id="fc182-127">A device profile allows you to add and configure settings which can then be deployed to devices enrolled in management within your organization.</span></span> <span data-ttu-id="fc182-128">裝置收到裝置設定檔之後，就會自動套用這些功能與設定。</span><span class="sxs-lookup"><span data-stu-id="fc182-128">Once the device receives the device profile, the features and settings are applied automatically.</span></span> <span data-ttu-id="fc182-129">常見裝置設定檔的範例包括電子郵件、裝置限制、VPN、Wi-fi 和管理範本。</span><span class="sxs-lookup"><span data-stu-id="fc182-129">Examples of common device profiles include Email, Device restrictions, VPN, Wi-Fi, and Administrative templates.</span></span> <span data-ttu-id="fc182-130">DFCI 只是一個額外的裝置設定檔，可讓您從雲端管理 UEFI 配置設定，而不必維護內部部署基礎結構。</span><span class="sxs-lookup"><span data-stu-id="fc182-130">DFCI is simply an additional device profile that enables you to manage UEFI configuration settings from the cloud without having to maintain on-premises infrastructure.</span></span>  

## <span data-ttu-id="fc182-131">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="fc182-131">Supported devices</span></span>

<span data-ttu-id="fc182-132">目前，下列裝置支援 DFCI：</span><span class="sxs-lookup"><span data-stu-id="fc182-132">At this time, DFCI is supported in the following devices:</span></span>

- <span data-ttu-id="fc182-133">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="fc182-133">Surface Pro 7</span></span>
- <span data-ttu-id="fc182-134">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="fc182-134">Surface Pro X</span></span>
- <span data-ttu-id="fc182-135">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="fc182-135">Surface Laptop 3</span></span>

> [!NOTE]
> <span data-ttu-id="fc182-136">Surface Pro X 不支援內建相機、音訊和 Wi-fi/藍牙的 DFCI 設定管理。</span><span class="sxs-lookup"><span data-stu-id="fc182-136">Surface Pro X does not support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.</span></span>

## <span data-ttu-id="fc182-137">必要條件</span><span class="sxs-lookup"><span data-stu-id="fc182-137">Prerequisites</span></span>

- <span data-ttu-id="fc182-138">裝置必須由[Microsoft 雲端解決方案提供者（CSP）合作夥伴](https://partner.microsoft.com/membership/cloud-solution-provider)或 OEM 發行商在 Windows Autopilot 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="fc182-138">Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor.</span></span>

- <span data-ttu-id="fc182-139">在配置 Surface 的 DFCI 之前，您應該熟悉[Microsoft Intune](https://docs.microsoft.com/intune/)和[Azure Active DIRECTORY](https://docs.microsoft.com/azure/active-directory/) （Azure AD）中的 Autopilot 設定需求。</span><span class="sxs-lookup"><span data-stu-id="fc182-139">Before configuring DFCI for Surface, you should be familiar with Autopilot configuration requirements in  [Microsoft Intune](https://docs.microsoft.com/intune/) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).</span></span>

## <span data-ttu-id="fc182-140">在您開始前</span><span class="sxs-lookup"><span data-stu-id="fc182-140">Before you begin</span></span>

<span data-ttu-id="fc182-141">將您的目標 Surface 裝置新增至 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="fc182-141">Add your target Surface devices to an Azure AD security group.</span></span> <span data-ttu-id="fc182-142">如需有關建立及管理安全性群組的詳細資訊，請參閱[Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="fc182-142">For more information about creating and managing security groups, refer to [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).</span></span>

## <span data-ttu-id="fc182-143">設定 Surface 裝置的 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="fc182-143">Configure DFCI management for Surface devices</span></span>

<span data-ttu-id="fc182-144">DFCI 環境需要設定包含設定的 DFCI 設定檔，以及將設定套用到已註冊裝置的 Autopilot 設定檔。</span><span class="sxs-lookup"><span data-stu-id="fc182-144">A DFCI environment requires setting up a DFCI profile that contains  the settings and an Autopilot profile to apply the settings to registered devices.</span></span> <span data-ttu-id="fc182-145">建議使用註冊狀態設定檔，以確保在使用者第一次啟動裝置時，在 OOBE 設定期間將設定推向下。</span><span class="sxs-lookup"><span data-stu-id="fc182-145">An enrollment status profile is also recommended to ensure settings are pushed down during OOBE setup when users first start the device.</span></span> <span data-ttu-id="fc182-146">本指南說明如何設定 DFCI 環境，以及如何管理目標 Surface 裝置的 UEFI 配置設定。</span><span class="sxs-lookup"><span data-stu-id="fc182-146">This guide explains how to configure the DFCI environment and manage UEFI configuration settings for targeted Surface devices.</span></span>

## <span data-ttu-id="fc182-147">建立 DFCI 設定檔</span><span class="sxs-lookup"><span data-stu-id="fc182-147">Create DFCI profile</span></span>

<span data-ttu-id="fc182-148">在設定 DFCI 原則設定之前，請先建立 DFCI 設定檔，然後將它指派給包含您目標裝置的 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="fc182-148">Before configuring DFCI policy settings, first create a DFCI profile and assign it to the Azure AD security group that contains your target devices.</span></span>

1. <span data-ttu-id="fc182-149">在 devicemanagement.microsoft.com 登入您的租使用者。</span><span class="sxs-lookup"><span data-stu-id="fc182-149">Sign into your tenant at  devicemanagement.microsoft.com.</span></span>
2. <span data-ttu-id="fc182-150">在 Microsoft 端點管理員系統管理中心，選取 [**裝置] > 配置設定檔] > [建立配置**檔]，然後輸入名稱;例如， **DFCI [配置原則]。**</span><span class="sxs-lookup"><span data-stu-id="fc182-150">In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**</span></span>
3. <span data-ttu-id="fc182-151">針對 [平臺類型] 選取 [ **Windows 10 及更新版本**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-151">Select **Windows 10 and later** for platform type.</span></span>
4. <span data-ttu-id="fc182-152">在 [配置檔案類型] 下拉式清單中，選取 [**裝置固件配置介面**] 來開啟包含所有可用原則設定的 DFCI blade。</span><span class="sxs-lookup"><span data-stu-id="fc182-152">In the Profile type drop down list, select **Device Firmware Configuration Interface** to open the DFCI blade containing all available policy settings.</span></span> <span data-ttu-id="fc182-153">如需 DFCI 設定的詳細資訊，請參閱此頁面上的資料表1或[Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="fc182-153">For information on DFCI settings, refer to Table 1 on this page or the [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span> <span data-ttu-id="fc182-154">您可以在初始安裝程式期間設定 DFCI 設定，或在稍後編輯 DFCI 設定檔。</span><span class="sxs-lookup"><span data-stu-id="fc182-154">You can configure DFCI settings during the initial setup process or later by editing the DFCI profile.</span></span>

    ![建立 DFCI 設定檔](images/df1.png)

5. <span data-ttu-id="fc182-156">按一下 **[確定]** ，然後選取 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-156">Click **OK** and then select **Create**.</span></span>
6. <span data-ttu-id="fc182-157">選取 [**作業**]，然後在 [**選取要包含的群組**] 底下，選取包含您目標裝置的 Azure AD 安全性群組，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="fc182-157">Select **Assignments** and under **Select groups to include** select the Azure AD security group that contains your target devices, as shown in the following figure.</span></span> <span data-ttu-id="fc182-158">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="fc182-158">Click **Save**.</span></span>

    ![指派安全性群組](images/df2a.png)

## <span data-ttu-id="fc182-160">建立 Autopilot 設定檔</span><span class="sxs-lookup"><span data-stu-id="fc182-160">Create Autopilot profile</span></span>

1. <span data-ttu-id="fc182-161">在 devicemanagement.microsoft.com 的端點管理員中，選取 [**裝置] > Windows 註冊**，然後向下滾動至 [**部署設定檔**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-161">In Endpoint Manager at  devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles**.</span></span>
2. <span data-ttu-id="fc182-162">選取 [**建立設定檔**]，然後輸入名稱;例如，**我的 Autopilot 設定檔**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fc182-162">Select **Create profile** and enter a name; for example, **My Autopilot profile**, and select **Next**.</span></span>
3. <span data-ttu-id="fc182-163">選取下列設定：</span><span class="sxs-lookup"><span data-stu-id="fc182-163">Select the following settings:</span></span>

    - <span data-ttu-id="fc182-164">部署模式：**使用者導向**。</span><span class="sxs-lookup"><span data-stu-id="fc182-164">Deployment mode: **User-Driven**.</span></span>
    - <span data-ttu-id="fc182-165">加入類型： Azure **AD 已加入**。</span><span class="sxs-lookup"><span data-stu-id="fc182-165">Join type: Azure **AD joined**.</span></span>

4. <span data-ttu-id="fc182-166">將剩餘的預設設定保持不變，然後選取 **[下一步]**，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="fc182-166">Leave the remaining default settings unchanged and select **Next**, as shown in the following figure.</span></span>

    ![建立 Autopilot 設定檔](images/df3b.png)

5. <span data-ttu-id="fc182-168">在 [作業] 頁面上，選擇 [**選取要包含的群組**]，然後按一下您的 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="fc182-168">On the Assignments page, choose **Select groups to include** and click your Azure AD security group.</span></span> <span data-ttu-id="fc182-169">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fc182-169">Select **Next**.</span></span>
6. <span data-ttu-id="fc182-170">接受摘要，然後選取 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-170">Accept the summary and then select **Create**.</span></span> <span data-ttu-id="fc182-171">Autopilot 設定檔隨即會建立並指派給群組。</span><span class="sxs-lookup"><span data-stu-id="fc182-171">The Autopilot profile is now created and assigned to the group.</span></span>

## <span data-ttu-id="fc182-172">[設定註冊狀態] 頁面</span><span class="sxs-lookup"><span data-stu-id="fc182-172">Configure Enrollment Status Page</span></span>

<span data-ttu-id="fc182-173">為了確保裝置在使用者登入時在 OOBE 期間套用 DFCI 設定，您必須設定註冊狀態。</span><span class="sxs-lookup"><span data-stu-id="fc182-173">To ensure that devices apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status.</span></span>

<span data-ttu-id="fc182-174">如需詳細資訊，請參閱[設定 [註冊狀態] 頁面](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="fc182-174">For more information, refer to [Set up an enrollment status page](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).</span></span>


## <span data-ttu-id="fc182-175">在 Surface 裝置上設定 DFCI 設定</span><span class="sxs-lookup"><span data-stu-id="fc182-175">Configure DFCI settings on Surface devices</span></span>

<span data-ttu-id="fc182-176">DFCI 包含一組經過簡化的 UEFI 配置原則，可在硬體層級鎖定裝置，提供額外的安全性。</span><span class="sxs-lookup"><span data-stu-id="fc182-176">DFCI includes a streamlined set of UEFI configuration policies that provide an extra level of security by locking down devices at the hardware level.</span></span> <span data-ttu-id="fc182-177">DFCI 的設計目的是與軟體層級的行動裝置管理設定搭配使用。</span><span class="sxs-lookup"><span data-stu-id="fc182-177">DFCI is designed to be used in conjunction with mobile device management settings at the software level.</span></span> <span data-ttu-id="fc182-178">請注意，[DFCI 設定] 只會影響已內建到 Surface 裝置的硬體元件，且不會延伸到連接的外設（例如 USB 網路攝影機）。</span><span class="sxs-lookup"><span data-stu-id="fc182-178">Note that DFCI settings only affect hardware components built into Surface devices and do not extend to attached peripherals such as USB webcams.</span></span> <span data-ttu-id="fc182-179">（不過，您可以在 Intune 中使用裝置限制原則，關閉軟體層級附屬週邊設備的存取權）。</span><span class="sxs-lookup"><span data-stu-id="fc182-179">(However, you can use Device restriction policies in Intune to turn off access to attached peripherals at the software level).</span></span>

<span data-ttu-id="fc182-180">您可以從端點管理員編輯 DFCI 設定檔，以設定 DFCI 原則設定，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="fc182-180">You configure DFCI policy settings by editing the DFCI profile from Endpoint Manager, as shown in the figure below.</span></span> 

- <span data-ttu-id="fc182-181">在 devicemanagement.microsoft.com 的 [端點管理員] 中，選取 **[裝置] > Windows > 設定設定檔 > 「DFCI profile name」 > 屬性 > 設定**。</span><span class="sxs-lookup"><span data-stu-id="fc182-181">In Endpoint Manager at  devicemanagement.microsoft.com, select **Devices > Windows > Configuration Profiles > “DFCI profile name” > Properties > Settings**.</span></span>

    ![設定 DFCI 設定](images/dfciconfig.png)

### <span data-ttu-id="fc182-183">封鎖使用者對 UEFI 設定的存取權</span><span class="sxs-lookup"><span data-stu-id="fc182-183">Block user access to UEFI settings</span></span>

<span data-ttu-id="fc182-184">對於許多客戶而言，封鎖使用者變更 UEFI 設定的能力至關重要，且主要是使用 DFCI 的理由。</span><span class="sxs-lookup"><span data-stu-id="fc182-184">For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI.</span></span> <span data-ttu-id="fc182-185">如資料表1所列，這是透過設定 [**允許本機使用者變更 UEFI 設定**] 來管理。</span><span class="sxs-lookup"><span data-stu-id="fc182-185">As listed in Table 1, this is managed via the setting **Allow local user to change UEFI settings**.</span></span> <span data-ttu-id="fc182-186">如果您沒有編輯或設定此設定，本機使用者將能夠變更任何不由 Intune 管理的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="fc182-186">If you do not edit or configure this setting, local users will be able to change any UEFI setting not managed by Intune.</span></span> <span data-ttu-id="fc182-187">因此，強烈建議您停用 [**允許本機使用者變更 UEFI 設定]。**</span><span class="sxs-lookup"><span data-stu-id="fc182-187">Therefore, it’s highly recommended to disable **Allow local user to change UEFI settings.**</span></span>
<span data-ttu-id="fc182-188">其餘的 [DFCI] 設定可讓您關閉其他使用者可以使用的功能。</span><span class="sxs-lookup"><span data-stu-id="fc182-188">The rest of the DFCI settings enable you to turn off functionality that would otherwise be available to users.</span></span> <span data-ttu-id="fc182-189">例如，如果您需要在高度安全的區域中保護機密資訊，您可以停用相機，如果不想讓使用者從 USB 磁片磁碟機啟動，您也可以停用。</span><span class="sxs-lookup"><span data-stu-id="fc182-189">For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don’t want users booting from USB drives, you can disable that also.</span></span>

### <span data-ttu-id="fc182-190">表 1.</span><span class="sxs-lookup"><span data-stu-id="fc182-190">Table 1.</span></span> <span data-ttu-id="fc182-191">DFCI 案例</span><span class="sxs-lookup"><span data-stu-id="fc182-191">DFCI scenarios</span></span>

| <span data-ttu-id="fc182-192">裝置管理目標</span><span class="sxs-lookup"><span data-stu-id="fc182-192">Device management goal</span></span>                        | <span data-ttu-id="fc182-193">設定步驟</span><span class="sxs-lookup"><span data-stu-id="fc182-193">Configuration steps</span></span>                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="fc182-194">封鎖本機使用者變更 UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="fc182-194">Block local users from changing UEFI settings</span></span> | <span data-ttu-id="fc182-195">在 [**安全性功能] 底下 > [允許本機使用者變更 UEFI 設定**] 底下，選取 [**無**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-195">Under **Security Features > Allow local user to change UEFI settings**, select **None**.</span></span>              |
| <span data-ttu-id="fc182-196">停用相機</span><span class="sxs-lookup"><span data-stu-id="fc182-196">Disable cameras</span></span>                               | <span data-ttu-id="fc182-197">在 [**內置於硬體 > 相機**] 底下，選取 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-197">Under **Built in Hardware > Cameras**, select **Disabled**.</span></span>                                       |
| <span data-ttu-id="fc182-198">停用麥克風和喇叭</span><span class="sxs-lookup"><span data-stu-id="fc182-198">Disable Microphones and speakers</span></span>              | <span data-ttu-id="fc182-199">在 [**內置於硬體 > 麥克風和喇叭**] 底下，選取 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-199">Under **Built in Hardware > Microphones and speakers**, select **Disabled**.</span></span>                      |
| <span data-ttu-id="fc182-200">停用無線電（藍牙，Wi-fi）</span><span class="sxs-lookup"><span data-stu-id="fc182-200">Disable radios (Bluetooth, Wi-Fi)</span></span>             | <span data-ttu-id="fc182-201">在 **[內置於硬體 > 無線電（藍牙、wi-fi 等 ...）**] 底下，選取 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-201">Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc…)**, select **Disabled**.</span></span>                   |
| <span data-ttu-id="fc182-202">停用外部媒體（USB、SD）的啟動</span><span class="sxs-lookup"><span data-stu-id="fc182-202">Disable Boot from external media (USB, SD)</span></span>    | <span data-ttu-id="fc182-203">在 **[內置硬體 > 啟動選項] 下 > 從外部媒體（USB、SD）引導**]，選取 [**停用**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-203">Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**.</span></span> |

> [!CAUTION]
> <span data-ttu-id="fc182-204">[**停用無線收發機（Bluetooth、wi-fi）** ] 設定只能在有有線乙太網連線的裝置上使用。</span><span class="sxs-lookup"><span data-stu-id="fc182-204">The **Disable radios (Bluetooth, Wi-Fi)** setting should only be used on devices that have a wired Ethernet connection.</span></span>
 
> [!NOTE]
>  <span data-ttu-id="fc182-205">Intune 中的 DFCI 包括兩個目前不適用於 Surface 裝置的設定：（1） CPU 和 IO 虛擬化，（2）從網路介面卡停用啟動。</span><span class="sxs-lookup"><span data-stu-id="fc182-205">DFCI in Intune includes two settings that do not currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.</span></span>
 
<span data-ttu-id="fc182-206">Intune 提供作用中標籤來委派管理權利和適用性規則來管理裝置類型。</span><span class="sxs-lookup"><span data-stu-id="fc182-206">Intune provides Scope tags to delegate administrative rights and Applicability Rules to manage device types.</span></span> <span data-ttu-id="fc182-207">如需有關原則管理支援的詳細資訊，以及所有 DFCI 設定的完整詳細資訊，請參閱[Microsoft Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="fc182-207">For more information about policy management support and full details on all DFCI settings, refer to [Microsoft Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span>

## <span data-ttu-id="fc182-208">在 Autopilot 中註冊裝置</span><span class="sxs-lookup"><span data-stu-id="fc182-208">Register devices in Autopilot</span></span>

<span data-ttu-id="fc182-209">如上述所述，DFCI 只能套用在由您的轉銷商或分銷商在 Windows Autopilot 中註冊的裝置上，而且目前僅支援（在 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3）。</span><span class="sxs-lookup"><span data-stu-id="fc182-209">As stated above, DFCI can only be applied on devices registered in Windows Autopilot by your reseller or distributor and is only supported, at this time, on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="fc182-210">基於安全性的考慮，您無法將裝置「自行提供」 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="fc182-210">For security reasons, it’s not possible to “self-provision” your devices into Autopilot.</span></span>

## <span data-ttu-id="fc182-211">手動同步處理 Autopilot 裝置</span><span class="sxs-lookup"><span data-stu-id="fc182-211">Manually Sync Autopilot devices</span></span>

<span data-ttu-id="fc182-212">雖然 Intune 原則設定通常會立即套用，但在目標裝置上設定會生效，可能會有10分鐘的延遲。</span><span class="sxs-lookup"><span data-stu-id="fc182-212">Although Intune policy settings typically get applied almost immediately, there may be a delay of 10 minutes before the settings take effect on targeted devices.</span></span> <span data-ttu-id="fc182-213">在極少數情況下，可能會延遲長達8小時。</span><span class="sxs-lookup"><span data-stu-id="fc182-213">In rare circumstances, delays of up to 8 hours are possible.</span></span> <span data-ttu-id="fc182-214">若要確保設定儘快套用（例如在測試案例中），您可以手動同步處理目標裝置。</span><span class="sxs-lookup"><span data-stu-id="fc182-214">To ensure settings apply as soon as possible, (such as in test scenarios), you can manually sync the target devices.</span></span>

- <span data-ttu-id="fc182-215">在 devicemanagement.microsoft.com 的 [端點管理員] 中，移至 [裝置] **> 裝置註冊 > windows 註冊 > Windows Autopilot 裝置**，然後選取 [**同步**處理]。</span><span class="sxs-lookup"><span data-stu-id="fc182-215">In Endpoint Manager at  devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync**.</span></span>

 <span data-ttu-id="fc182-216">如需詳細資訊，請參閱[手動同步處理您的 Windows 裝置](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。</span><span class="sxs-lookup"><span data-stu-id="fc182-216">For more information, refer to [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).</span></span>

> [!NOTE]
> <span data-ttu-id="fc182-217">在 UEFI 中直接調整設定時，您必須確保裝置完全重新開機至標準的 Windows 登入。</span><span class="sxs-lookup"><span data-stu-id="fc182-217">When adjusting settings directly in UEFI, you need to ensure the device fully restarts to the standard Windows login.</span></span>

## <span data-ttu-id="fc182-218">在 DFCI 管理的裝置上驗證 UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="fc182-218">Verifying UEFI settings on DFCI-managed devices</span></span>

<span data-ttu-id="fc182-219">在測試環境中，您可以驗證 Surface UEFI 介面中的設定。</span><span class="sxs-lookup"><span data-stu-id="fc182-219">In a test environment, you can verify settings in the Surface UEFI interface.</span></span>

1. <span data-ttu-id="fc182-220">[開啟 Surface UEFI]，其中包括同步選取 [**音量 +** ] 和 [**電源**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="fc182-220">Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.</span></span>
2. <span data-ttu-id="fc182-221">選取 [**裝置**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-221">Select **Devices**.</span></span> <span data-ttu-id="fc182-222">UEFI 功能表會反映已設定的設定，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="fc182-222">The UEFI menu will reflect configured settings, as shown in the following figure.</span></span>

    ![Surface UEFI](images/df3.png)

    <span data-ttu-id="fc182-224">注意做法：</span><span class="sxs-lookup"><span data-stu-id="fc182-224">Note how:</span></span>

      - <span data-ttu-id="fc182-225">這些設定會呈現灰色，因為 [**允許本機使用者變更 UEFI] 設定**為 [無]。</span><span class="sxs-lookup"><span data-stu-id="fc182-225">The settings are greyed out because **Allow local user to change UEFI setting** is set to None.</span></span>
      - <span data-ttu-id="fc182-226">因為**麥克風和喇叭**設定為 [**停用**]，所以音訊已設定為 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="fc182-226">Audio is set to off because **Microphones and speakers** are set to **Disabled**.</span></span>

## <span data-ttu-id="fc182-227">移除 DFCI 原則設定</span><span class="sxs-lookup"><span data-stu-id="fc182-227">Removing DFCI policy settings</span></span>

<span data-ttu-id="fc182-228">當您建立 DFCI 設定檔時，所有設定的設定都會在設定檔的管理範圍內的所有裝置上保持生效。</span><span class="sxs-lookup"><span data-stu-id="fc182-228">When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile’s scope of management.</span></span> <span data-ttu-id="fc182-229">您只能透過直接編輯 DFCI 設定檔來移除 DFCI 原則設定。</span><span class="sxs-lookup"><span data-stu-id="fc182-229">You can only remove DFCI policy settings by editing the DFCI profile directly.</span></span>

<span data-ttu-id="fc182-230">如果原始的 DFCI 設定檔已遭刪除，您可以建立新的設定檔，然後視需要編輯設定，以移除原則設定。</span><span class="sxs-lookup"><span data-stu-id="fc182-230">If the original DFCI profile has been deleted, you can remove policy settings by creating a new profile and then editing the settings, as appropriate.</span></span>

## <span data-ttu-id="fc182-231">移除 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="fc182-231">Removing DFCI management</span></span>

**<span data-ttu-id="fc182-232">若要移除 DFCI 管理，並將裝置傳回工廠新狀態：</span><span class="sxs-lookup"><span data-stu-id="fc182-232">To remove DFCI management and return device to factory new state:</span></span>**

1. <span data-ttu-id="fc182-233">從 Intune 停用裝置：</span><span class="sxs-lookup"><span data-stu-id="fc182-233">Retire the device from Intune:</span></span>
    1. <span data-ttu-id="fc182-234">在 devicemanagement.microsoft.com 的 [端點管理員] 中，選擇 [**群組 > 所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-234">In Endpoint Manager at  devicemanagement.microsoft.com, choose **Groups > All Devices**.</span></span> <span data-ttu-id="fc182-235">選取您要撤出的裝置，然後選擇 [**停用/清除]。**</span><span class="sxs-lookup"><span data-stu-id="fc182-235">Select the devices you want to retire, and then choose **Retire/Wipe.**</span></span> <span data-ttu-id="fc182-236">若要深入瞭解，請參閱[使用 [擦除]、[停用] 或 [手動 unenrolling 裝置] 來移除裝置](https://docs.microsoft.com/intune/remote-actions/devices-wipe)。</span><span class="sxs-lookup"><span data-stu-id="fc182-236">To learn more refer to [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span></span> 
2. <span data-ttu-id="fc182-237">從 Intune 刪除 Autopilot 註冊：</span><span class="sxs-lookup"><span data-stu-id="fc182-237">Delete the Autopilot registration from Intune:</span></span>
    1.  <span data-ttu-id="fc182-238">選擇 [**裝置註冊] > Windows 註冊 > 裝置**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-238">Choose **Device enrollment > Windows enrollment > Devices**.</span></span>
    2. <span data-ttu-id="fc182-239">在 [Windows Autopilot 裝置] 下，選擇您要刪除的裝置，然後選擇 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="fc182-239">Under Windows Autopilot devices, choose the devices you want to delete, and then choose **Delete**.</span></span>
3. <span data-ttu-id="fc182-240">使用 Surface 品牌乙太網卡將裝置連線至有線網際網路。</span><span class="sxs-lookup"><span data-stu-id="fc182-240">Connect device to wired internet with Surface-branded ethernet adapter.</span></span> <span data-ttu-id="fc182-241">重新開機裝置，然後開啟 [UEFI] 功能表（按住音量按鈕，同步選取並放開電源按鈕）。</span><span class="sxs-lookup"><span data-stu-id="fc182-241">Restart device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).</span></span>
4. <span data-ttu-id="fc182-242">選取 [**管理] > 設定 [從網路 >** 重新整理]，然後選擇 [**退出]。**</span><span class="sxs-lookup"><span data-stu-id="fc182-242">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span></span>

<span data-ttu-id="fc182-243">若要繼續使用 Intune 管理裝置，但不 DFCI 管理，請自行註冊裝置以 Autopilot 並將它註冊至 Intune。</span><span class="sxs-lookup"><span data-stu-id="fc182-243">To keep managing the device with Intune, but without DFCI management, self-register the device to Autopilot and enroll it to Intune.</span></span> <span data-ttu-id="fc182-244">DFCI 將不會套用到自行註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="fc182-244">DFCI will not be applied to self-registered devices.</span></span>

## <span data-ttu-id="fc182-245">深入了解</span><span class="sxs-lookup"><span data-stu-id="fc182-245">Learn more</span></span>
- <span data-ttu-id="fc182-246">[Ignite 2019：宣佈從 Intune 進行 SURFACE UEFI 設定的遠端系統管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="fc182-246">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span></span>
- [<span data-ttu-id="fc182-247">Windows Autopilot 與 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="fc182-247">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md) 
- [<span data-ttu-id="fc182-248">在 Microsoft Intune 中使用 Windows 裝置上的 DFCI 設定檔</span><span class="sxs-lookup"><span data-stu-id="fc182-248">Use DFCI profiles on Windows devices in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
