---
title: Surface UEFI 設定的 Intune 管理
description: 本文將說明如何在 Microsoft Intune 中設定 DFCI 環境，以及管理目標 Surface 裝置的固件設定。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
- Surface Laptop 4
ms.openlocfilehash: b74aeab45dd2354550f0dff712af5b37b853111c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576513"
---
# <a name="intune-management-of-surface-uefi-settings"></a><span data-ttu-id="ed47c-103">Surface UEFI 設定的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="ed47c-103">Intune management of Surface UEFI settings</span></span>

## <a name="introduction"></a><span data-ttu-id="ed47c-104">簡介</span><span class="sxs-lookup"><span data-stu-id="ed47c-104">Introduction</span></span>

<span data-ttu-id="ed47c-105">從雲端管理裝置的能力大幅簡化了整個生命週期的 IT 部署和部署。</span><span class="sxs-lookup"><span data-stu-id="ed47c-105">The ability to manage devices from the cloud has dramatically simplified IT deployment and provisioning across the lifecycle.</span></span> <span data-ttu-id="ed47c-106">Surface UEFI 管理 (DFCI) 內建的[DFCI](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)Microsoft Intune 設定檔，將新式管理堆疊延伸至 UEFI 硬體層級。</span><span class="sxs-lookup"><span data-stu-id="ed47c-106">With Device Firmware Configuration Interface (DFCI) profiles built into [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="ed47c-107">DFCI 支援零接觸式設定、消除BIOS 密碼、提供安全性設定控制，包括開機選項和內建的周邊設備，以及為日後進一步的安全性案例打下基礎。</span><span class="sxs-lookup"><span data-stu-id="ed47c-107">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="ed47c-108">有關常見問題的解答，請參閱 [Ignite 2019：宣佈從 Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)遠端系統管理 Surface UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-108">For answers to frequently asked questions, see [Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333).</span></span>

### <a name="background"></a><span data-ttu-id="ed47c-109">背景</span><span class="sxs-lookup"><span data-stu-id="ed47c-109">Background</span></span>

<span data-ttu-id="ed47c-110">如同執行Windows 10，Surface 裝置會仰賴儲存在 SoC 中的程式碼，讓 CPU 能夠與硬碟、顯示裝置、USB 埠及其他裝置進行介面。</span><span class="sxs-lookup"><span data-stu-id="ed47c-110">Like any computer running Windows 10, Surface devices rely on code stored in the SoC that enables the CPU to interface with hard drives, display devices, USB ports, and other devices.</span></span> <span data-ttu-id="ed47c-111">儲存在此唯讀記憶體中的程式 (ROM) 稱為 (，而儲存在動態媒體中的程式稱為軟體) 。</span><span class="sxs-lookup"><span data-stu-id="ed47c-111">The programs stored in this read-only memory (ROM) are known as firmware (while programs stored in dynamic media are known as software).</span></span>

<span data-ttu-id="ed47c-112">與現今市Windows 10的其他裝置不同，Surface 提供 IT 系統管理員透過豐富的 UEFI 設定設定集來設定及管理固件的能力。</span><span class="sxs-lookup"><span data-stu-id="ed47c-112">In contrast to other Windows 10 devices available in the market today, Surface provides IT admins with the ability to configure and manage firmware through a rich set of UEFI configuration settings.</span></span> <span data-ttu-id="ed47c-113">這會在軟體型策略管理上提供一層硬體控制，透過行動裝置管理或 MDM (、Configuration Manager 或組) 策略來執行。</span><span class="sxs-lookup"><span data-stu-id="ed47c-113">This provides a layer of hardware control on top of software-based policy management as implemented via mobile device management (MDM) policies, Configuration Manager or Group Policy.</span></span> <span data-ttu-id="ed47c-114">例如，將裝置部署在具有敏感性資訊的高度安全區域的組織，可以移除硬體層級的功能，以防止相機使用。</span><span class="sxs-lookup"><span data-stu-id="ed47c-114">For example, organizations deploying devices in highly secure areas with sensitive information can prevent camera use by removing functionality at the hardware level.</span></span> <span data-ttu-id="ed47c-115">從裝置角度而言，透過固件設定關閉相機相當於實際移除相機。</span><span class="sxs-lookup"><span data-stu-id="ed47c-115">From a device standpoint, turning the camera off via a firmware setting is equivalent to physically removing the camera.</span></span> <span data-ttu-id="ed47c-116">比較新增的在固件層級管理的安全性，只仰賴作業系統軟體設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-116">Compare the added security of managing at the firmware level to relying only on operating system software settings.</span></span> <span data-ttu-id="ed47c-117">例如，如果您透過網域Windows設定停用音訊服務，則當地系統管理員仍可重新啟用服務。</span><span class="sxs-lookup"><span data-stu-id="ed47c-117">For example, if you disable the Windows audio service via a policy setting in a domain environment, a local admin could still re-enable the service.</span></span>

### <a name="dfci-versus-semm"></a><span data-ttu-id="ed47c-118">DFCI 與 SEMM</span><span class="sxs-lookup"><span data-stu-id="ed47c-118">DFCI versus SEMM</span></span>

<span data-ttu-id="ed47c-119">之前，管理固件時，需要將裝置註冊到 Surface Enterprise管理模式 (SEMM) ，而需要持續進行大量手動 IT 工作。</span><span class="sxs-lookup"><span data-stu-id="ed47c-119">Previously, managing firmware required enrolling devices into Surface Enterprise Management Mode (SEMM) with the overhead of ongoing manual IT-intensive tasks.</span></span> <span data-ttu-id="ed47c-120">例如，SEMM 要求 IT 員工以實體方式存取每部電腦，才能在憑證管理程式過程中輸入兩位數的圖釘。</span><span class="sxs-lookup"><span data-stu-id="ed47c-120">As an example, SEMM requires IT staff to physically access each PC to enter a two-digit pin as part of the certificate management process.</span></span> <span data-ttu-id="ed47c-121">雖然 SEMM 仍然是嚴格內部部署環境中組織的良好解決方案，但其複雜度和 IT 需求高，因此使用成本高。</span><span class="sxs-lookup"><span data-stu-id="ed47c-121">Although SEMM remains a good solution for organizations in a strictly on-premises environment, its complexity and IT-intensive requirements make it costly to use.</span></span>

 <span data-ttu-id="ed47c-122">有了 Microsoft Intune 中整合的 UEFI 固件管理功能，鎖定硬體的功能變得簡單且更容易與新功能一起使用，以在單一主機中進行部署、安全性和簡化更新，現在統一為[Microsoft 端點管理員。](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)</span><span class="sxs-lookup"><span data-stu-id="ed47c-122">With integrated UEFI firmware management capabilities in Microsoft Intune, the ability to lock down hardware is simplified and easier to use with new features for provisioning, security, and streamlined updating all in a single console, now unified as [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span> <span data-ttu-id="ed47c-123">下圖顯示直接在裝置上的 UEFI 設定 (左) ，端點管理員主控台 (右) 。</span><span class="sxs-lookup"><span data-stu-id="ed47c-123">The following figure shows UEFI settings viewed directly on the device (left) and viewed in the Endpoint Manager console (right).</span></span>

![裝置上顯示的 UEFI 設定 (左) ，端點管理員主控台 (右) ](images/uefidfci.png)

<span data-ttu-id="ed47c-125">最重要的是，DFCI 可啟用零觸控管理，而不需要 IT 系統管理員手動互動。</span><span class="sxs-lookup"><span data-stu-id="ed47c-125">Crucially, DFCI enables zero touch management, eliminating the need for manual interaction by IT admins.</span></span> <span data-ttu-id="ed47c-126">使用 Intune 中的裝置設定檔功能，Windows Autopilot 部署 DFCI。</span><span class="sxs-lookup"><span data-stu-id="ed47c-126">DFCI is deployed via Windows Autopilot using the device profiles capability in Intune.</span></span> <span data-ttu-id="ed47c-127">裝置設定檔可讓您新增和設定設定，然後部署至您組織中註冊管理中的裝置。</span><span class="sxs-lookup"><span data-stu-id="ed47c-127">A device profile allows you to add and configure settings which can then be deployed to devices enrolled in management within your organization.</span></span> <span data-ttu-id="ed47c-128">一旦裝置收到裝置設定檔，就會自動應用功能和設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-128">Once the device receives the device profile, the features and settings are applied automatically.</span></span> <span data-ttu-id="ed47c-129">常見的裝置設定檔範例包括電子郵件、裝置限制、VPN、Wi-Fi 及系統管理範本。</span><span class="sxs-lookup"><span data-stu-id="ed47c-129">Examples of common device profiles include Email, Device restrictions, VPN, Wi-Fi, and Administrative templates.</span></span> <span data-ttu-id="ed47c-130">DFCI 只是額外的裝置設定檔，可讓您從雲端管理 UEFI 設定設定，而不需要維護內部部署基礎結構。</span><span class="sxs-lookup"><span data-stu-id="ed47c-130">DFCI is simply an additional device profile that enables you to manage UEFI configuration settings from the cloud without having to maintain on-premises infrastructure.</span></span>  

## <a name="supported-devices"></a><span data-ttu-id="ed47c-131">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="ed47c-131">Supported devices</span></span>

<span data-ttu-id="ed47c-132">下列裝置支援 DFCI：</span><span class="sxs-lookup"><span data-stu-id="ed47c-132">DFCI is supported in the following devices:</span></span>

- <span data-ttu-id="ed47c-133">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="ed47c-133">Surface Pro 7+</span></span>
- <span data-ttu-id="ed47c-134">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="ed47c-134">Surface Pro 7</span></span>
- <span data-ttu-id="ed47c-135">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="ed47c-135">Surface Pro X</span></span>
- <span data-ttu-id="ed47c-136">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="ed47c-136">Surface Laptop 3</span></span>
- <span data-ttu-id="ed47c-137">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="ed47c-137">Surface Book 3</span></span>
- <span data-ttu-id="ed47c-138">Surface Laptop去</span><span class="sxs-lookup"><span data-stu-id="ed47c-138">Surface Laptop Go</span></span>
- <span data-ttu-id="ed47c-139">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="ed47c-139">Surface Laptop 4</span></span>

> [!NOTE]
> <span data-ttu-id="ed47c-140">Surface ProX 不支援內建相機、音訊和 Wi-Fi/藍牙。</span><span class="sxs-lookup"><span data-stu-id="ed47c-140">Surface Pro X does not support DFCI settings management for built-in camera, audio, and Wi-Fi/Bluetooth.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ed47c-141">必要條件</span><span class="sxs-lookup"><span data-stu-id="ed47c-141">Prerequisites</span></span>

- <span data-ttu-id="ed47c-142">裝置必須由合作夥伴或 OEM Windows[的 CSP](https://partner.microsoft.com/membership/cloud-solution-provider) Microsoft 雲端解決方案提供者 (在 Autopilot) 註冊。</span><span class="sxs-lookup"><span data-stu-id="ed47c-142">Devices must be registered with Windows Autopilot by a [Microsoft Cloud Solution Provider (CSP) partner](https://partner.microsoft.com/membership/cloud-solution-provider) or OEM distributor.</span></span>

- <span data-ttu-id="ed47c-143">在針對 Surface 配置 DFCI 之前，您應該先熟悉 Microsoft Intune 和[](https://docs.microsoft.com/intune/)Azure Active Directory (Azure [](https://docs.microsoft.com/azure/active-directory/) AD) 。</span><span class="sxs-lookup"><span data-stu-id="ed47c-143">Before configuring DFCI for Surface, you should be familiar with Autopilot configuration requirements in  [Microsoft Intune](https://docs.microsoft.com/intune/) and [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/) (Azure AD).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ed47c-144">開始之前</span><span class="sxs-lookup"><span data-stu-id="ed47c-144">Before you begin</span></span>

<span data-ttu-id="ed47c-145">將目標 Surface 裝置新增到 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ed47c-145">Add your target Surface devices to an Azure AD security group.</span></span> <span data-ttu-id="ed47c-146">有關建立及管理安全性群組的資訊，請參閱 [Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。</span><span class="sxs-lookup"><span data-stu-id="ed47c-146">For more information about creating and managing security groups, refer to [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups).</span></span>

## <a name="configure-dfci-management-for-surface-devices"></a><span data-ttu-id="ed47c-147">設定 Surface 裝置 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="ed47c-147">Configure DFCI management for Surface devices</span></span>

<span data-ttu-id="ed47c-148">DFCI 環境需要設定包含設定和 Autopilot 設定檔的 DFCI 設定檔，以將設定適用于已註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="ed47c-148">A DFCI environment requires setting up a DFCI profile that contains  the settings and an Autopilot profile to apply the settings to registered devices.</span></span> <span data-ttu-id="ed47c-149">此外，建議使用註冊狀態設定檔，以確保使用者第一次啟動裝置時，在 OOBE 設定期間將設定向下推入。</span><span class="sxs-lookup"><span data-stu-id="ed47c-149">An enrollment status profile is also recommended to ensure settings are pushed down during OOBE setup when users first start the device.</span></span> <span data-ttu-id="ed47c-150">本指南說明如何設定 DFCI 環境，以及管理目標 Surface 裝置之 UEFI 設定設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-150">This guide explains how to configure the DFCI environment and manage UEFI configuration settings for targeted Surface devices.</span></span>

## <a name="create-dfci-profile"></a><span data-ttu-id="ed47c-151">建立 DFCI 設定檔</span><span class="sxs-lookup"><span data-stu-id="ed47c-151">Create DFCI profile</span></span>

<span data-ttu-id="ed47c-152">設定 DFCI 策略設定之前，先建立 DFCI 設定檔，並將其指派給包含您目標裝置之 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ed47c-152">Before configuring DFCI policy settings, first create a DFCI profile and assign it to the Azure AD security group that contains your target devices.</span></span>

1. <span data-ttu-id="ed47c-153">請于您的租使用者 devicemanagement.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="ed47c-153">Sign into your tenant at  devicemanagement.microsoft.com.</span></span>
2. <span data-ttu-id="ed47c-154">在系統管理Microsoft 端點管理員中，選取 >**設定檔**的裝置>建立設定檔並輸入名稱;例如 **，DFCI 群組原則。**</span><span class="sxs-lookup"><span data-stu-id="ed47c-154">In the Microsoft Endpoint Manager Admin Center, select **Devices > Configuration profiles > Create profile** and enter a name; for example, **DFCI Configuration Policy.**</span></span>
3. <span data-ttu-id="ed47c-155">選取**Windows 10及稍後**的平臺類型。</span><span class="sxs-lookup"><span data-stu-id="ed47c-155">Select **Windows 10 and later** for platform type.</span></span>
4. <span data-ttu-id="ed47c-156">在配置檔案類型下拉式清單中，選取 **裝置固件設定介面** 以開啟包含所有可用策略設定之 DFCI 邊欄選項卡。</span><span class="sxs-lookup"><span data-stu-id="ed47c-156">In the Profile type drop down list, select **Device Firmware Configuration Interface** to open the DFCI blade containing all available policy settings.</span></span> <span data-ttu-id="ed47c-157">有關 DFCI 設定的資訊，請參閱此頁面的表格 1 或 [Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="ed47c-157">For information on DFCI settings, refer to Table 1 on this page or the [Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span> <span data-ttu-id="ed47c-158">您可以在初始設定程式或稍後編輯 DFCI 設定檔時設定 DFCI 設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-158">You can configure DFCI settings during the initial setup process or later by editing the DFCI profile.</span></span>

    ![建立 DFCI 設定檔](images/df1.png)

5. <span data-ttu-id="ed47c-160">按一下 **[確定** ，然後選取 **[建立**> 。</span><span class="sxs-lookup"><span data-stu-id="ed47c-160">Click **OK** and then select **Create**.</span></span>
6. <span data-ttu-id="ed47c-161">選取 **作業** ，在選取 **群組下選取** 包含您目標裝置之 Azure AD 安全性群組，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="ed47c-161">Select **Assignments** and under **Select groups to include** select the Azure AD security group that contains your target devices, as shown in the following figure.</span></span> <span data-ttu-id="ed47c-162">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ed47c-162">Click **Save**.</span></span>

    ![指派安全性群組](images/df2a.png)

## <a name="create-autopilot-profile"></a><span data-ttu-id="ed47c-164">建立 Autopilot 設定檔</span><span class="sxs-lookup"><span data-stu-id="ed47c-164">Create Autopilot profile</span></span>

1. <span data-ttu-id="ed47c-165">在 端點管理員的 devicemanagement.microsoft.com，選取 **> Windows的裝置**，然後向下卷起至**部署設定檔**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-165">In Endpoint Manager at  devicemanagement.microsoft.com, select **devices > Windows enrollment** and scroll down to **Deployment profiles**.</span></span>
2. <span data-ttu-id="ed47c-166">選取 **建立設定檔** 並輸入名稱;例如，我的 **Autopilot 設定檔**，然後選取 下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-166">Select **Create profile** and enter a name; for example, **My Autopilot profile**, and select **Next**.</span></span>
3. <span data-ttu-id="ed47c-167">選取下列設定：</span><span class="sxs-lookup"><span data-stu-id="ed47c-167">Select the following settings:</span></span>

    - <span data-ttu-id="ed47c-168">部署模式： **使用者導向**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-168">Deployment mode: **User-Driven**.</span></span>
    - <span data-ttu-id="ed47c-169">加入類型：已加入**Azure AD。**</span><span class="sxs-lookup"><span data-stu-id="ed47c-169">Join type: Azure **AD joined**.</span></span>

4. <span data-ttu-id="ed47c-170">將其餘的預設設定維持不變， **然後選取下**一步，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="ed47c-170">Leave the remaining default settings unchanged and select **Next**, as shown in the following figure.</span></span>

    ![建立 Autopilot 設定檔](images/df3b.png)

5. <span data-ttu-id="ed47c-172">在 [作業」 頁面上，選擇 **[選取要** 包含的群組，然後按一下您的 Azure AD 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="ed47c-172">On the Assignments page, choose **Select groups to include** and click your Azure AD security group.</span></span> <span data-ttu-id="ed47c-173">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-173">Select **Next**.</span></span>
6. <span data-ttu-id="ed47c-174">接受摘要， **然後選取建立**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-174">Accept the summary and then select **Create**.</span></span> <span data-ttu-id="ed47c-175">Autopilot 設定檔現在已建立並指派給群組。</span><span class="sxs-lookup"><span data-stu-id="ed47c-175">The Autopilot profile is now created and assigned to the group.</span></span>

## <a name="configure-enrollment-status-page"></a><span data-ttu-id="ed47c-176">設定註冊狀態頁面</span><span class="sxs-lookup"><span data-stu-id="ed47c-176">Configure Enrollment Status Page</span></span>

<span data-ttu-id="ed47c-177">若要在使用者登錄前，確保裝置在 OOBE 期間適用 DFCI 設定，您必須設定註冊狀態。</span><span class="sxs-lookup"><span data-stu-id="ed47c-177">To ensure that devices apply the DFCI configuration during OOBE before users sign in, you need to configure enrollment status.</span></span>

<span data-ttu-id="ed47c-178">若要詳細資訊，請參閱 [設定註冊狀態頁面](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。</span><span class="sxs-lookup"><span data-stu-id="ed47c-178">For more information, refer to [Set up an enrollment status page](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status).</span></span>


## <a name="configure-dfci-settings-on-surface-devices"></a><span data-ttu-id="ed47c-179">在 Surface 裝置上設定 DFCI 設定</span><span class="sxs-lookup"><span data-stu-id="ed47c-179">Configure DFCI settings on Surface devices</span></span>

<span data-ttu-id="ed47c-180">DFCI 包含一組簡化的 UEFI 設定策略，可鎖定硬體層級的裝置，提供額外的安全性等級。</span><span class="sxs-lookup"><span data-stu-id="ed47c-180">DFCI includes a streamlined set of UEFI configuration policies that provide an extra level of security by locking down devices at the hardware level.</span></span> <span data-ttu-id="ed47c-181">DFCI 是設計用來與軟體層級的行動裝置管理設定一起使用。</span><span class="sxs-lookup"><span data-stu-id="ed47c-181">DFCI is designed to be used in conjunction with mobile device management settings at the software level.</span></span> <span data-ttu-id="ed47c-182">請注意，DFCI 設定只會影響 Surface 裝置內建的硬體元件，不會延伸到 USB 網路網路等附加的周邊。</span><span class="sxs-lookup"><span data-stu-id="ed47c-182">Note that DFCI settings only affect hardware components built into Surface devices and do not extend to attached peripherals such as USB webcams.</span></span> <span data-ttu-id="ed47c-183"> (不過，您可以使用 Intune 中的裝置限制政策，在軟體層級關閉附加) 。</span><span class="sxs-lookup"><span data-stu-id="ed47c-183">(However, you can use Device restriction policies in Intune to turn off access to attached peripherals at the software level).</span></span>

<span data-ttu-id="ed47c-184">您可以設定 DFCI 策略設定，從 端點管理員編輯 DFCI 設定檔，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="ed47c-184">You configure DFCI policy settings by editing the DFCI profile from Endpoint Manager, as shown in the figure below.</span></span> 

- <span data-ttu-id="ed47c-185">在 端點管理員的 devicemanagement.microsoft.com 中，選取 > Windows >**設定檔> DFCI 設定檔名稱">屬性**> 設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-185">In Endpoint Manager at  devicemanagement.microsoft.com, select **Devices > Windows > Configuration Profiles > “DFCI profile name” > Properties > Settings**.</span></span>

    ![設定 DFCI 設定](images/dfciconfig.png)

### <a name="block-user-access-to-uefi-settings"></a><span data-ttu-id="ed47c-187">封鎖使用者對 UEFI 設定的存取權限</span><span class="sxs-lookup"><span data-stu-id="ed47c-187">Block user access to UEFI settings</span></span>

<span data-ttu-id="ed47c-188">對於許多客戶來說，封鎖使用者變更 UEFI 設定的能力至關重要，也是使用 DFCI 的主要理由。</span><span class="sxs-lookup"><span data-stu-id="ed47c-188">For many customers, the ability to block users from changing UEFI settings is critically important and a primary reason to use DFCI.</span></span> <span data-ttu-id="ed47c-189">如表格 1 所列，此設定會透過設定允許 **本地使用者變更 UEFI 設定進行管理**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-189">As listed in Table 1, this is managed via the setting **Allow local user to change UEFI settings**.</span></span> <span data-ttu-id="ed47c-190">如果您沒有編輯或設定此設定，則當地使用者將可以變更 Intune 未管理的任何 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-190">If you do not edit or configure this setting, local users will be able to change any UEFI setting not managed by Intune.</span></span> <span data-ttu-id="ed47c-191">因此，強烈建議您停用允許 **本地使用者變更 UEFI 設定。**</span><span class="sxs-lookup"><span data-stu-id="ed47c-191">Therefore, it’s highly recommended to disable **Allow local user to change UEFI settings.**</span></span>
<span data-ttu-id="ed47c-192">其餘的 DFCI 設定可讓使用者關閉原本可供使用者使用的功能。</span><span class="sxs-lookup"><span data-stu-id="ed47c-192">The rest of the DFCI settings enable you to turn off functionality that would otherwise be available to users.</span></span> <span data-ttu-id="ed47c-193">例如，如果您需要保護高度安全區域中的敏感性資訊，您可以停用相機，如果您不希望使用者從 USB 磁片磁碟機啟動，您也可以停用此功能。</span><span class="sxs-lookup"><span data-stu-id="ed47c-193">For example, if you need to protect sensitive information in highly secure areas, you can disable the camera, and if you don’t want users booting from USB drives, you can disable that also.</span></span>

### <a name="table-1-dfci-scenarios"></a><span data-ttu-id="ed47c-194">表 1.</span><span class="sxs-lookup"><span data-stu-id="ed47c-194">Table 1.</span></span> <span data-ttu-id="ed47c-195">DFCI 案例</span><span class="sxs-lookup"><span data-stu-id="ed47c-195">DFCI scenarios</span></span>

| <span data-ttu-id="ed47c-196">裝置管理目標</span><span class="sxs-lookup"><span data-stu-id="ed47c-196">Device management goal</span></span>                        | <span data-ttu-id="ed47c-197">組組步驟</span><span class="sxs-lookup"><span data-stu-id="ed47c-197">Configuration steps</span></span>                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ed47c-198">封鎖當地使用者變更 UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="ed47c-198">Block local users from changing UEFI settings</span></span> | <span data-ttu-id="ed47c-199">在 **安全性功能>允許本地使用者變更 UEFI 設定**，選取 **無**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-199">Under **Security Features > Allow local user to change UEFI settings**, select **None**.</span></span>              |
| <span data-ttu-id="ed47c-200">停用相機</span><span class="sxs-lookup"><span data-stu-id="ed47c-200">Disable cameras</span></span>                               | <span data-ttu-id="ed47c-201">在 **內建硬體>相機**下，選取 已 **停用**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-201">Under **Built in Hardware > Cameras**, select **Disabled**.</span></span>                                       |
| <span data-ttu-id="ed47c-202">停用麥克風和喇叭</span><span class="sxs-lookup"><span data-stu-id="ed47c-202">Disable Microphones and speakers</span></span>              | <span data-ttu-id="ed47c-203">在 **內建硬體>麥克風和喇叭**下，選取 已 **停用**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-203">Under **Built in Hardware > Microphones and speakers**, select **Disabled**.</span></span>                      |
| <span data-ttu-id="ed47c-204">停用無線 (藍牙、Wi-Fi) </span><span class="sxs-lookup"><span data-stu-id="ed47c-204">Disable radios (Bluetooth, Wi-Fi)</span></span>             | <span data-ttu-id="ed47c-205">在**內建硬體>無線 (藍牙、Wi-Fi**等...) ，選取 已**停用**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-205">Under **Built in Hardware > Radios (Bluetooth, Wi-Fi, etc…)**, select **Disabled**.</span></span>                   |
| <span data-ttu-id="ed47c-206">停用從外部媒體啟動 (USB、SD) </span><span class="sxs-lookup"><span data-stu-id="ed47c-206">Disable Boot from external media (USB, SD)</span></span>    | <span data-ttu-id="ed47c-207">在 \*\*內建硬體>啟動選項> USB、SD \*\* (從外部媒體啟動) ，選取 已 **停用**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-207">Under **Built in Hardware > Boot Options > Boot from external media (USB, SD)**, select **Disabled**.</span></span> |

> [!CAUTION]
> <span data-ttu-id="ed47c-208">停用\*\*無線 (藍牙 Wi-Fi) \*\*設定只能用於有有線乙太網路連接的裝置。</span><span class="sxs-lookup"><span data-stu-id="ed47c-208">The **Disable radios (Bluetooth, Wi-Fi)** setting should only be used on devices that have a wired Ethernet connection.</span></span>
 
> [!NOTE]
>  <span data-ttu-id="ed47c-209">Intune 中的 DFCI 包含兩個目前不適用於 Surface 裝置設定： (1) CPU 和 IO 虛擬化，以及 (2) 從網路介面卡停用開機。</span><span class="sxs-lookup"><span data-stu-id="ed47c-209">DFCI in Intune includes two settings that do not currently apply to Surface devices: (1) CPU and IO virtualization and (2) Disable Boot from network adapters.</span></span>
 
<span data-ttu-id="ed47c-210">Intune 提供範圍標記以委派系統管理許可權和適用規則來管理裝置類型。</span><span class="sxs-lookup"><span data-stu-id="ed47c-210">Intune provides Scope tags to delegate administrative rights and Applicability Rules to manage device types.</span></span> <span data-ttu-id="ed47c-211">有關策略管理支援的詳細資訊，以及所有 DFCI 設定的完整詳細資料，請參閱Microsoft Intune[檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。</span><span class="sxs-lookup"><span data-stu-id="ed47c-211">For more information about policy management support and full details on all DFCI settings, refer to [Microsoft Intune documentation](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows).</span></span>

## <a name="register-devices-in-autopilot"></a><span data-ttu-id="ed47c-212">在 Autopilot 中註冊裝置</span><span class="sxs-lookup"><span data-stu-id="ed47c-212">Register devices in Autopilot</span></span>

<span data-ttu-id="ed47c-213">如上所述，DFCI 僅適用于轉銷商或轉銷商在 Windows Autopilot 註冊的裝置，且僅支援 Surface Pro 7+、Surface Laptop Go、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="ed47c-213">As stated above, DFCI can only be applied on devices registered in Windows Autopilot by your reseller or distributor and is only supported on Surface Pro 7+, Surface Laptop Go, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="ed47c-214">基於安全性考慮，您無法將裝置「自我布供」到 Autopilot。</span><span class="sxs-lookup"><span data-stu-id="ed47c-214">For security reasons, it’s not possible to “self-provision” your devices into Autopilot.</span></span> <span data-ttu-id="ed47c-215">若要深入瞭解，請參閱適用于[Autopilot](surface-autopilot-registration-support.md)Windows Surface 註冊支援 。</span><span class="sxs-lookup"><span data-stu-id="ed47c-215">To learn more, see Surface [Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).</span></span> 

## <a name="manually-sync-autopilot-devices"></a><span data-ttu-id="ed47c-216">手動同步處理自動駕駛裝置</span><span class="sxs-lookup"><span data-stu-id="ed47c-216">Manually Sync Autopilot devices</span></span>

<span data-ttu-id="ed47c-217">雖然 Intune 原則設定通常幾乎會立即採用，但設定在目標裝置上生效之前，可能會延遲 10 分鐘。</span><span class="sxs-lookup"><span data-stu-id="ed47c-217">Although Intune policy settings typically get applied almost immediately, there may be a delay of 10 minutes before the settings take effect on targeted devices.</span></span> <span data-ttu-id="ed47c-218">在少數情況下，最多可能會延遲 8 小時。</span><span class="sxs-lookup"><span data-stu-id="ed47c-218">In rare circumstances, delays of up to 8 hours are possible.</span></span> <span data-ttu-id="ed47c-219">若要確保設定儘快適用， (例如測試案例) ，您可以手動同步處理目標裝置。</span><span class="sxs-lookup"><span data-stu-id="ed47c-219">To ensure settings apply as soon as possible, (such as in test scenarios), you can manually sync the target devices.</span></span>

- <span data-ttu-id="ed47c-220">在 端點管理員的 devicemanagement.microsoft.com，請前往 > 裝置註冊> Windows自動> Windows裝置，然後選取**同步** **。**</span><span class="sxs-lookup"><span data-stu-id="ed47c-220">In Endpoint Manager at  devicemanagement.microsoft.com, go to **Devices > Device enrollment > Windows enrollment > Windows Autopilot Devices** and select **Sync**.</span></span>

 <span data-ttu-id="ed47c-221">若要詳細資訊，請參閱手動[同步Windows同步處理您的裝置](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。</span><span class="sxs-lookup"><span data-stu-id="ed47c-221">For more information, refer to [Sync your Windows device manually](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows).</span></span>

> [!NOTE]
> <span data-ttu-id="ed47c-222">當直接在 UEFI 中調整設定時，您必須確保裝置完全重新開機至標準Windows登入。</span><span class="sxs-lookup"><span data-stu-id="ed47c-222">When adjusting settings directly in UEFI, you need to ensure the device fully restarts to the standard Windows login.</span></span>

## <a name="verifying-uefi-settings-on-dfci-managed-devices"></a><span data-ttu-id="ed47c-223">驗證 DFCI 管理的裝置上的 UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="ed47c-223">Verifying UEFI settings on DFCI-managed devices</span></span>

<span data-ttu-id="ed47c-224">在測試環境中，您可以在 Surface UEFI 介面中驗證設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-224">In a test environment, you can verify settings in the Surface UEFI interface.</span></span>

1. <span data-ttu-id="ed47c-225">開啟 Surface UEFI，這涉及同時按 **音量 +** 和 **Power** 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ed47c-225">Open Surface UEFI, which involves pressing the **Volume +** and **Power** buttons at the same time.</span></span>
2. <span data-ttu-id="ed47c-226">選取 **裝置**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-226">Select **Devices**.</span></span> <span data-ttu-id="ed47c-227">如下圖所示，UEFI 功能表會反映設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-227">The UEFI menu will reflect configured settings, as shown in the following figure.</span></span>

    ![Surface UEFI](images/df3.png)

    <span data-ttu-id="ed47c-229">請注意如何：</span><span class="sxs-lookup"><span data-stu-id="ed47c-229">Note how:</span></span>

      - <span data-ttu-id="ed47c-230">設定會以灰色顯示，因為允許 **本地使用者變更 UEFI 設定** 設為無。</span><span class="sxs-lookup"><span data-stu-id="ed47c-230">The settings are greyed out because **Allow local user to change UEFI setting** is set to None.</span></span>
      - <span data-ttu-id="ed47c-231">音訊已設為關閉， **因為麥克風和喇** 叭設定為 **已停用**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-231">Audio is set to off because **Microphones and speakers** are set to **Disabled**.</span></span>

## <a name="removing-dfci-policy-settings"></a><span data-ttu-id="ed47c-232">移除 DFCI 策略設定</span><span class="sxs-lookup"><span data-stu-id="ed47c-232">Removing DFCI policy settings</span></span>

<span data-ttu-id="ed47c-233">當您建立 DFCI 設定檔時，所有設定都會在設定檔管理範圍內的所有裝置上維持有效。</span><span class="sxs-lookup"><span data-stu-id="ed47c-233">When you create a DFCI profile, all configured settings will remain in effect across all devices within the profile’s scope of management.</span></span> <span data-ttu-id="ed47c-234">您只要直接編輯 DFCI 設定檔，才能移除 DFCI 策略設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-234">You can only remove DFCI policy settings by editing the DFCI profile directly.</span></span>

<span data-ttu-id="ed47c-235">如果原始 DFCI 設定檔已刪除，您可以建立新設定檔，然後編輯設定來移除策略設定。</span><span class="sxs-lookup"><span data-stu-id="ed47c-235">If the original DFCI profile has been deleted, you can remove policy settings by creating a new profile and then editing the settings, as appropriate.</span></span>

## <a name="removing-dfci-management"></a><span data-ttu-id="ed47c-236">移除 DFCI 管理</span><span class="sxs-lookup"><span data-stu-id="ed47c-236">Removing DFCI management</span></span>

**<span data-ttu-id="ed47c-237">若要移除 DFCI 管理，將裝置返回出廠新狀態：</span><span class="sxs-lookup"><span data-stu-id="ed47c-237">To remove DFCI management and return device to factory new state:</span></span>**

1. <span data-ttu-id="ed47c-238">從 Intune 淘汰裝置：</span><span class="sxs-lookup"><span data-stu-id="ed47c-238">Retire the device from Intune:</span></span>
    1. <span data-ttu-id="ed47c-239">在 端點管理員的 devicemanagement.microsoft.com，選擇 >**所有裝置 。**</span><span class="sxs-lookup"><span data-stu-id="ed47c-239">In Endpoint Manager at  devicemanagement.microsoft.com, choose **Groups > All Devices**.</span></span> <span data-ttu-id="ed47c-240">選取您想要淘汰的裝置，然後選擇淘汰 **/抹掉。**</span><span class="sxs-lookup"><span data-stu-id="ed47c-240">Select the devices you want to retire, and then choose **Retire/Wipe.**</span></span> <span data-ttu-id="ed47c-241">若要深入瞭解，請參閱使用 [抹除、](https://docs.microsoft.com/intune/remote-actions/devices-wipe)淘汰或手動取消註冊裝置來移除裝置。</span><span class="sxs-lookup"><span data-stu-id="ed47c-241">To learn more refer to [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/remote-actions/devices-wipe).</span></span> 
2. <span data-ttu-id="ed47c-242">從 Intune 刪除 Autopilot 註冊：</span><span class="sxs-lookup"><span data-stu-id="ed47c-242">Delete the Autopilot registration from Intune:</span></span>
    1.  <span data-ttu-id="ed47c-243">選擇**裝置註冊> Windows註冊>裝置**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-243">Choose **Device enrollment > Windows enrollment > Devices**.</span></span>
    2. <span data-ttu-id="ed47c-244">在 Windows Autopilot 裝置下，選擇您想要刪除的裝置，**然後選擇刪除**。</span><span class="sxs-lookup"><span data-stu-id="ed47c-244">Under Windows Autopilot devices, choose the devices you want to delete, and then choose **Delete**.</span></span>
3. <span data-ttu-id="ed47c-245">連線 Surface 品牌乙太網路介面卡將裝置連接到有線網際網路。</span><span class="sxs-lookup"><span data-stu-id="ed47c-245">Connect device to wired internet with Surface-branded ethernet adapter.</span></span> <span data-ttu-id="ed47c-246">重新開機裝置並開啟 UEFI 功能表 (按住放大按鈕，同時按並放開電源按鈕) 。</span><span class="sxs-lookup"><span data-stu-id="ed47c-246">Restart device and open the UEFI menu (press and hold the volume-up button while also pressing and releasing the power button).</span></span>
4. <span data-ttu-id="ed47c-247">選取 **管理>從>重新設定** ，然後選擇 **退出宣告。**</span><span class="sxs-lookup"><span data-stu-id="ed47c-247">Select **Management > Configure > Refresh from Network** and then choose **Opt-out.**</span></span>

<span data-ttu-id="ed47c-248">若要使用 Intune 持續管理裝置，但不需要 DFCI 管理，請自行將裝置註冊至 Autopilot，然後註冊至 Intune。</span><span class="sxs-lookup"><span data-stu-id="ed47c-248">To keep managing the device with Intune, but without DFCI management, self-register the device to Autopilot and enroll it to Intune.</span></span> <span data-ttu-id="ed47c-249">DFCI 不會用於自我註冊的裝置。</span><span class="sxs-lookup"><span data-stu-id="ed47c-249">DFCI will not be applied to self-registered devices.</span></span>

## <a name="learn-more"></a><span data-ttu-id="ed47c-250">深入了解</span><span class="sxs-lookup"><span data-stu-id="ed47c-250">Learn more</span></span>
- <span data-ttu-id="ed47c-251">[Ignite 2019：宣佈從 Intune 遠端系統管理 Surface UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="ed47c-251">[Ignite 2019: Announcing remote management of Surface UEFI settings from Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)</span></span>
- [<span data-ttu-id="ed47c-252">Windows Autopilot 與 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="ed47c-252">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md) 
- [<span data-ttu-id="ed47c-253">在 Windows 裝置上使用 DFCI 設定檔Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ed47c-253">Use DFCI profiles on Windows devices in Microsoft Intune</span></span>](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
