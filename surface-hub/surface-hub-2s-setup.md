---
title: Surface Hub 2S 第一次設定
description: 瞭解如何完成 Surface Hub 2S 第一次設定。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 9cbce8bf0cc9c729af4cd052167fef016197274f
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442191"
---
# <a name="first-time-setup-for-surface-hub-2s"></a><span data-ttu-id="0e75b-104">Surface Hub 2S 第一次設定</span><span class="sxs-lookup"><span data-stu-id="0e75b-104">First time Setup for Surface Hub 2S</span></span>

<span data-ttu-id="0e75b-105">當您第一次啟動 Surface Hub 2S 時，裝置會自動進入第一次設定模式，以引導您完成帳戶設定和相關設定。</span><span class="sxs-lookup"><span data-stu-id="0e75b-105">When you first start Surface Hub 2S, the device automatically enters first time Setup mode to guide you through account configuration and related settings.</span></span>

## <a name="configuring-surface-hub-2s-account"></a><span data-ttu-id="0e75b-106">正在配置 Surface Hub 2S 帳戶</span><span class="sxs-lookup"><span data-stu-id="0e75b-106">Configuring Surface Hub 2S account</span></span>

1. **<span data-ttu-id="0e75b-107">設定您的地區設定。</span><span class="sxs-lookup"><span data-stu-id="0e75b-107">Configure your locale.</span></span>** <span data-ttu-id="0e75b-108">輸入地區、語言、鍵盤配置和時區資訊。</span><span class="sxs-lookup"><span data-stu-id="0e75b-108">Enter region, language, keyboard layout and time zone information.</span></span> <span data-ttu-id="0e75b-109">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="0e75b-109">Select **Next**.</span></span>

   ![\* 設定您的地區設定 \*](images/sh2-run1.png)

1. **<span data-ttu-id="0e75b-111">連接到無線網路。</span><span class="sxs-lookup"><span data-stu-id="0e75b-111">Connect  to a wireless network.</span></span>** <span data-ttu-id="0e75b-112">選擇您偏好的無線網路，然後選取下 **一步。**</span><span class="sxs-lookup"><span data-stu-id="0e75b-112">Choose your preferred wireless network and select **Next.**</span></span>

   - <span data-ttu-id="0e75b-113">如果使用乙太網路纜線連接，則不會顯示此選項。</span><span class="sxs-lookup"><span data-stu-id="0e75b-113">This option is not shown if connected using an Ethernet cable.</span></span>

   - <span data-ttu-id="0e75b-114">您無法在將登錄要求重新導向到提供者 (入口網站或) 中，連接到無線網路。</span><span class="sxs-lookup"><span data-stu-id="0e75b-114">You cannot connect to a wireless network in hotspots (captive portals) that redirect sign-in requests to a provider's website.</span></span>

3. **<span data-ttu-id="0e75b-115">輸入裝置帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="0e75b-115">Enter device account info.</span></span>** <span data-ttu-id="0e75b-116">針對 **內部部署和** 混合式環境使用網域\user，以及適用于線上 example.com 使用者 **\@example.com** 使用者。</span><span class="sxs-lookup"><span data-stu-id="0e75b-116">Use **domain\user** for on-premises and hybrid environments and **user\@example.com** for online environments.</span></span> <span data-ttu-id="0e75b-117">選取 **下一步。**</span><span class="sxs-lookup"><span data-stu-id="0e75b-117">Select **Next.**</span></span>

   ![\* 輸入裝置帳戶資訊 \*](images/sh2-run2.png)

1. **<span data-ttu-id="0e75b-119">輸入其他資訊。</span><span class="sxs-lookup"><span data-stu-id="0e75b-119">Enter additional info.</span></span>** <span data-ttu-id="0e75b-120">如果要求，請提供您的 Exchange 伺服器位址，然後選取下 **一步。**</span><span class="sxs-lookup"><span data-stu-id="0e75b-120">If requested, provide your Exchange server address and then select **Next.**</span></span>

   ![\* 輸入詳細資訊;例如 Exchange 伺服器名稱\*](images/sh2-run3.png)

1. **<span data-ttu-id="0e75b-122">為此裝置命名。</span><span class="sxs-lookup"><span data-stu-id="0e75b-122">Name this device.</span></span>** <span data-ttu-id="0e75b-123">輸入您裝置的名稱，或根據帳戶的顯示名稱和使用者原則名稱 [UPN] 使用建議的名稱。</span><span class="sxs-lookup"><span data-stu-id="0e75b-123">Enter a name for your device or use the suggested one based on your account’s display name and user principle name [UPN].</span></span> <span data-ttu-id="0e75b-124">**選取 下一個**。</span><span class="sxs-lookup"><span data-stu-id="0e75b-124">**Select Next**.</span></span>

   - <span data-ttu-id="0e75b-125">Surface **Hub** 2S 左下角會顯示好用名稱，且在專案到裝置時會顯示。</span><span class="sxs-lookup"><span data-stu-id="0e75b-125">The **Friendly name** is visible on the bottom left corner of Surface Hub 2S and is shown when projecting to the device.</span></span>

   - <span data-ttu-id="0e75b-126">裝置 **名稱** 會識別與 Active Directory 或 Azure Active Directory 有關系，以及使用 Intune 註冊裝置時，裝置。</span><span class="sxs-lookup"><span data-stu-id="0e75b-126">The **Device name** identifies the device when affiliated with Active Directory or Azure Active Directory, and when enrolling the device with Intune.</span></span>

   ![\* 命名此裝置\*](images/sh2-run4.png)
 

## <a name="configuring-device-admin-accounts"></a><span data-ttu-id="0e75b-128">正在配置裝置系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="0e75b-128">Configuring device admin accounts</span></span>

<span data-ttu-id="0e75b-129">您只能在第一次設定期間設定裝置系統管理員。</span><span class="sxs-lookup"><span data-stu-id="0e75b-129">You can only set up device admins during first time Setup.</span></span> <span data-ttu-id="0e75b-130">詳細資訊，請參閱 Surface [Hub 2S 裝置關聯。](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)</span><span class="sxs-lookup"><span data-stu-id="0e75b-130">For more information, refer to [Surface Hub 2S device affiliation](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation).</span></span>

<span data-ttu-id="0e75b-131">在此裝置 **視窗** 的安裝程式系統管理員中，選取下列其中一個選項：Active Directory Domain Services、Azure Active Directory 或 Local admin。</span><span class="sxs-lookup"><span data-stu-id="0e75b-131">In the **Setup admins for this device** window, select one of the following options: Active Directory Domain Services, Azure Active Directory, or Local admin.</span></span>

![\* 此裝置設定系統管理員 \*](images/sh2-run5.png)

### <a name="active-directory-domain-services"></a><span data-ttu-id="0e75b-133">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="0e75b-133">Active Directory Domain Services</span></span>

1. <span data-ttu-id="0e75b-134">輸入具有將裝置加入 Active Directory 之許可權之使用者的認證。</span><span class="sxs-lookup"><span data-stu-id="0e75b-134">Enter the credentials of a user who has permissions to join the device to Active Directory.</span></span>

    ![\* 使用網域加入設定系統管理員 \*](images/sh2-run6.png)

2. <span data-ttu-id="0e75b-136">選取包含允許成員登入 Surface Hub 2S 上的設定 App 的 Active Directory 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="0e75b-136">Select the Active Directory Security Group containing members allowed to log on to the Settings app on Surface Hub 2S.</span></span>

   ![\* 輸入安全性群組 \*](images/sh2-run7.png)

1. <span data-ttu-id="0e75b-138">選取 **完成**。</span><span class="sxs-lookup"><span data-stu-id="0e75b-138">Select **Finish**.</span></span> <span data-ttu-id="0e75b-139">裝置會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="0e75b-139">The device will restart.</span></span>

### <a name="azure-active-directory"></a><span data-ttu-id="0e75b-140">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="0e75b-140">Azure Active Directory</span></span>

<span data-ttu-id="0e75b-141">選擇將裝置與 Azure Active Directory 聯屬時，裝置會立即重新開機並顯示下列頁面。</span><span class="sxs-lookup"><span data-stu-id="0e75b-141">When choosing to affiliate your device with Azure Active Directory, the device will immediately restart and display the following page.</span></span>

![\* 如果貴組織使用 Microsoft 的 Office 365 或其他商務服務，我們會向貴組織註冊此裝置\*](images/sh2-run8.png)

1. <span data-ttu-id="0e75b-143">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="0e75b-143">Select **Next**.</span></span>

1. <span data-ttu-id="0e75b-144">輸入具有 Intune 方案 **1** 或更大的帳戶的電子郵件地址或 UPN，然後選取下 **一步。**</span><span class="sxs-lookup"><span data-stu-id="0e75b-144">Enter the email address or UPN of an account **with Intune Plan 1** or greater and then select **Next.**</span></span>

   ![\* 輸入公司或學校帳戶\*](images/sh2-run9.png)

1. <span data-ttu-id="0e75b-146">如果重新導向，請使用貴組織的登入頁面進行驗證，並提供額外的登入資訊 。如果有要求，請提供其他登入資訊。</span><span class="sxs-lookup"><span data-stu-id="0e75b-146">If redirected, authenticate using your organization’s sign-in page and provide additional logon information if requested.</span></span> <span data-ttu-id="0e75b-147">裝置會重新啟動。</span><span class="sxs-lookup"><span data-stu-id="0e75b-147">The device will restart.</span></span>

## <a name="local-administrator-account"></a><span data-ttu-id="0e75b-148">本地系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="0e75b-148">Local Administrator account</span></span>

- <span data-ttu-id="0e75b-149">輸入您的當地系統管理員的使用者名稱和密碼。裝置將會重新開機。</span><span class="sxs-lookup"><span data-stu-id="0e75b-149">Enter a username and password for your local admin. The device will restart.</span></span>

  ![\* 設定系統管理員帳戶\*](images/sh2-run10.png)
 
## <a name="using-provisioning-packages"></a><span data-ttu-id="0e75b-151">使用資源調配套件</span><span class="sxs-lookup"><span data-stu-id="0e75b-151">Using provisioning packages</span></span>

<span data-ttu-id="0e75b-152">如果您在啟動 Surface Hub 2S 時，將包含部署套件的 USB 拇指磁碟機插入其中一個 USB 埠，裝置會顯示下列頁面。</span><span class="sxs-lookup"><span data-stu-id="0e75b-152">If you insert a USB thumb drive with a provisioning package into one of the USB ports when you start Surface Hub 2S, the device displays the following page.</span></span>

1. <span data-ttu-id="0e75b-153">輸入要求設定，然後選取 **設定**。</span><span class="sxs-lookup"><span data-stu-id="0e75b-153">Enter the requested settings and select **Set up**.</span></span>

   ![\* 輸入地區設定以設定套件\*](images/sh2-run11.png)

   ![\* 從可移除媒體提供此裝置\*](images/sh2-run12.png)

2. <span data-ttu-id="0e75b-156">選擇您喜歡的部署套件。</span><span class="sxs-lookup"><span data-stu-id="0e75b-156">Choose the provisioning package you’d like to use.</span></span>

   ![\* 選擇要使用的部署套件\*](images/sh2-run13.png)

3. <span data-ttu-id="0e75b-158">如果您建立了多個裝置 CSV 檔案，您就能選擇裝置組組。</span><span class="sxs-lookup"><span data-stu-id="0e75b-158">If you created a multiple devices CSV file, you will be able to choose a device configuration.</span></span> <span data-ttu-id="0e75b-159">詳細資訊，請參閱建立 [Surface Hub 2S 的部署套件](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file)。</span><span class="sxs-lookup"><span data-stu-id="0e75b-159">For more information, refer to [Create provisioning packages for Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file).</span></span>

   ![\* 從組組檔案中選取裝置帳戶和好用名稱\*](images/sh2-run14.png)

4. <span data-ttu-id="0e75b-161">按照指示完成第一次設定。</span><span class="sxs-lookup"><span data-stu-id="0e75b-161">Follow the instructions to complete first time Setup.</span></span>
