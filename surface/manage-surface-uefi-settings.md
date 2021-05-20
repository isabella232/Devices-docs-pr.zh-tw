---
title: 管理 Surface UEFI 設定
description: 使用 Surface UEFI 設定以啟用或停用裝置或元件、設定安全性設定，以及調整 Surface 裝置開機設定。
keywords: firmware, security, features, configure, hardware, 韌體、安全性、功能、設定、硬體
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.date: 04/13/2021
ms.openlocfilehash: ea995eda277ecf235eedd92f3af6edb0b60ae68a
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576503"
---
# <a name="manage-surface-uefi-settings"></a><span data-ttu-id="418f9-104">管理 Surface UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="418f9-104">Manage Surface UEFI settings</span></span>

 <span data-ttu-id="418f9-105">Surface PC 裝置的設計目的是使用 Microsoft 專為這些裝置 (UEFI) 統一可擴展的固件介面。</span><span class="sxs-lookup"><span data-stu-id="418f9-105">Surface PC devices are designed to utilize a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="418f9-106">Surface UEFI 設定提供啟用或停用內建裝置和元件、保護 UEFI 設定不受變更，以及調整 Surface 裝置開機設定的能力。</span><span class="sxs-lookup"><span data-stu-id="418f9-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <a name="supported-products"></a><span data-ttu-id="418f9-107">支援的產品</span><span class="sxs-lookup"><span data-stu-id="418f9-107">Supported products</span></span>

<span data-ttu-id="418f9-108">下列支援 UEFI 管理：</span><span class="sxs-lookup"><span data-stu-id="418f9-108">UEFI management is supported on the following:</span></span> 

- <span data-ttu-id="418f9-109">Surface Pro 4，Surface Pro (第 5 代) ，Surface Pro 6，Surface Pro 7，Surface Pro 7+，Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="418f9-109">Surface Pro 4, Surface Pro (5th Gen), Surface Pro 6, Surface Pro 7, Surface Pro 7+, Surface Pro X</span></span>
- <span data-ttu-id="418f9-110">Surface Laptop (第 1 代) ，Surface Laptop 2，Surface Laptop 3，Surface Laptop，Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="418f9-110">Surface Laptop (1st Gen), Surface Laptop 2, Surface Laptop 3, Surface Laptop Go, Surface Laptop 4</span></span>
- <span data-ttu-id="418f9-111">Surface Studio (第 1 代) ，Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="418f9-111">Surface Studio (1st Gen), Surface Studio 2</span></span>
- <span data-ttu-id="418f9-112">Surface Book，Surface Book 2，Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="418f9-112">Surface Book, Surface Book 2, Surface Book 3</span></span>
- <span data-ttu-id="418f9-113">Surface Go， Surface Go 2[ <sup> 1 </sup> ](#references)</span><span class="sxs-lookup"><span data-stu-id="418f9-113">Surface Go, Surface Go 2[<sup>1</sup>](#references)</span></span>

## <a name="support-for-cloud-based-management"></a><span data-ttu-id="418f9-114">支援雲端管理</span><span class="sxs-lookup"><span data-stu-id="418f9-114">Support for cloud-based management</span></span>

<span data-ttu-id="418f9-115">有了裝置 (DFCI) 設定檔內建的 Microsoft Intune (現在可在公用預覽) 中使用，Surface UEFI 管理可將新式管理堆疊延伸至 UEFI 硬體層級。</span><span class="sxs-lookup"><span data-stu-id="418f9-115">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="418f9-116">DFCI 支援零接觸式設定、消除BIOS 密碼、提供安全性設定控制，包括開機選項和內建的周邊設備，以及為日後進一步的安全性案例打下基礎。</span><span class="sxs-lookup"><span data-stu-id="418f9-116">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="418f9-117">DFCI 目前適用于 Surface Pro 7+、Surface Laptop、Surface Book 3、Surface Laptop 3、Surface Pro 7 和 Surface Pro X。 詳細資訊，請參閱 Surface [UEFI 設定 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="418f9-117">DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 3, Surface Pro 7, and Surface Pro X.  For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <a name="open-surface-uefi-menu"></a><span data-ttu-id="418f9-118">開啟 Surface UEFI 功能表</span><span class="sxs-lookup"><span data-stu-id="418f9-118">Open Surface UEFI menu</span></span>

<span data-ttu-id="418f9-119">若要在系統啟動期間調整 UEFI 設定：</span><span class="sxs-lookup"><span data-stu-id="418f9-119">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="418f9-120">關閉 Surface 並等候約 10 秒，確定已關閉。</span><span class="sxs-lookup"><span data-stu-id="418f9-120">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="418f9-121">按住放大 **音量** 按鈕，並同步選取並放開 **Power 按鈕。**</span><span class="sxs-lookup"><span data-stu-id="418f9-121">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="418f9-122">當 Microsoft 或 Surface 標誌出現在您的螢幕上時，請\*\*\*\* 繼續按住放大按鈕，直到 UEFI 畫面出現。</span><span class="sxs-lookup"><span data-stu-id="418f9-122">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <a name="uefi-pc-information-page"></a><span data-ttu-id="418f9-123">UEFI 電腦資訊頁面</span><span class="sxs-lookup"><span data-stu-id="418f9-123">UEFI PC information page</span></span>

<span data-ttu-id="418f9-124">電腦資訊頁面包含 Surface 裝置的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="418f9-124">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="418f9-125">**模型**– 您的 Surface 裝置模型會顯示在這裡，例如 2 或 Surface Book 7 Surface Pro顯示。</span><span class="sxs-lookup"><span data-stu-id="418f9-125">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="418f9-126">裝置的確切組態並不會顯示 (例如處理器、磁碟大小或記憶體大小)。</span><span class="sxs-lookup"><span data-stu-id="418f9-126">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="418f9-127">**UUID** – 這個通用唯一識別碼是裝置特定的號碼，用來在部署或管理期間識別裝置。</span><span class="sxs-lookup"><span data-stu-id="418f9-127">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="418f9-128">**序號** – 此號碼是用來識別這個特定的 Surface 裝置，以進行資產標記和支援案例。</span><span class="sxs-lookup"><span data-stu-id="418f9-128">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="418f9-129">**資產標記**– 資產標記是使用[資產標記工具](https://docs.microsoft.com/surface/assettag)指派至 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="418f9-129">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="418f9-130">您也能找到 Surface 裝置韌體的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="418f9-130">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="418f9-131">Surface 裝置擁有數個內部元件，每個元件都會執行不同版本的韌體。</span><span class="sxs-lookup"><span data-stu-id="418f9-131">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="418f9-132">下列裝置的個別韌體版本都會顯示於 \[電腦資訊\] 頁面上 \(如圖 1 所示\)：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="418f9-132">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="418f9-133">系統 UEFI</span><span class="sxs-lookup"><span data-stu-id="418f9-133">System UEFI</span></span> 

- <span data-ttu-id="418f9-134">SAM 控制器</span><span class="sxs-lookup"><span data-stu-id="418f9-134">SAM Controller</span></span> 

- <span data-ttu-id="418f9-135">Intel 管理引擎</span><span class="sxs-lookup"><span data-stu-id="418f9-135">Intel Management Engine</span></span> 

- <span data-ttu-id="418f9-136">系統內嵌控制器</span><span class="sxs-lookup"><span data-stu-id="418f9-136">System Embedded Controller</span></span> 

- <span data-ttu-id="418f9-137">觸控韌體</span><span class="sxs-lookup"><span data-stu-id="418f9-137">Touch Firmware</span></span> 

![系統資訊和韌體版本資訊](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="418f9-139">圖 1.</span><span class="sxs-lookup"><span data-stu-id="418f9-139">Figure 1.</span></span> <span data-ttu-id="418f9-140">系統資訊和韌體版本資訊</span><span class="sxs-lookup"><span data-stu-id="418f9-140">System information and firmware version information</span></span>*

<span data-ttu-id="418f9-141">您可以在裝置的 [Surface 更新記錄](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中找到 Surface 裝置最新韌體版本的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="418f9-141">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <a name="uefi-security-page"></a><span data-ttu-id="418f9-142">UEFI 安全性頁面</span><span class="sxs-lookup"><span data-stu-id="418f9-142">UEFI Security page</span></span> 

![設定 Surface UEFI 安全性設定](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="418f9-144">圖 2.</span><span class="sxs-lookup"><span data-stu-id="418f9-144">Figure 2.</span></span> <span data-ttu-id="418f9-145">設定 Surface UEFI 安全性設定</span><span class="sxs-lookup"><span data-stu-id="418f9-145">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="418f9-146">安全性頁面可讓您設定密碼以保護 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="418f9-146">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="418f9-147">此密碼必須在將 Surface 裝置開機至 UEFI 時輸入。</span><span class="sxs-lookup"><span data-stu-id="418f9-147">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="418f9-148">密碼可以包含下列字元 (如圖 3 所示) ：</span><span class="sxs-lookup"><span data-stu-id="418f9-148">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="418f9-149">大寫字母：A-Z</span><span class="sxs-lookup"><span data-stu-id="418f9-149">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="418f9-150">小寫字母：a-z</span><span class="sxs-lookup"><span data-stu-id="418f9-150">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="418f9-151">數字：1-0</span><span class="sxs-lookup"><span data-stu-id="418f9-151">Numbers: 1-0</span></span> 

- <span data-ttu-id="418f9-152">特殊字元：！@#$%^&\* () ？<>{} []-_=+|.;：''</span><span class="sxs-lookup"><span data-stu-id="418f9-152">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="418f9-153">密碼必須至少為 6 個字元，並會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="418f9-153">The password must be at least 6 characters and is case sensitive.</span></span> 

![新增密碼以保護 Surface UEFI 設定](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="418f9-155">圖 3.</span><span class="sxs-lookup"><span data-stu-id="418f9-155">Figure 3.</span></span> <span data-ttu-id="418f9-156">新增密碼以保護 Surface UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="418f9-156">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="418f9-157">您也可以在 \[安全性\] 頁面上變更 Surface 裝置的安全開機設定。</span><span class="sxs-lookup"><span data-stu-id="418f9-157">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="418f9-158">安全開機技術能防止未經授權的啟動碼將您的 Surface 裝置開機，這將能針對 Bookit 和 Rootkit 類型的惡意程式碼感染提供保護。</span><span class="sxs-lookup"><span data-stu-id="418f9-158">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="418f9-159">您可以停用安全開機以允許 Surface 裝置使用第三方作業系統或可開機媒體進行開機。</span><span class="sxs-lookup"><span data-stu-id="418f9-159">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="418f9-160">您也可以設定安全啟動以使用協力廠商憑證，如圖 4 所示。</span><span class="sxs-lookup"><span data-stu-id="418f9-160">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="418f9-161">於 TechNet Library 深入了解[安全開機](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)。</span><span class="sxs-lookup"><span data-stu-id="418f9-161">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![設定安全開機](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="418f9-163">圖 4.</span><span class="sxs-lookup"><span data-stu-id="418f9-163">Figure 4.</span></span> <span data-ttu-id="418f9-164">設定安全開機</span><span class="sxs-lookup"><span data-stu-id="418f9-164">Configure Secure Boot</span></span>*

<span data-ttu-id="418f9-165">視您的裝置不同，您也可以查看 TPM 是否已啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="418f9-165">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="418f9-166">如果您沒看到啟用**TPM**設定，請在 Windows 中開啟 tpm.msc 以檢查狀態，如圖 5 所示。</span><span class="sxs-lookup"><span data-stu-id="418f9-166">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="418f9-167">TPM 是用來以 BitLocker 為您裝置的資料驗證加密。</span><span class="sxs-lookup"><span data-stu-id="418f9-167">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="418f9-168">若要深入瞭解，請參閱BitLocker[概觀](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。</span><span class="sxs-lookup"><span data-stu-id="418f9-168">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM 主機](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="418f9-170">圖 5.</span><span class="sxs-lookup"><span data-stu-id="418f9-170">Figure 5.</span></span> <span data-ttu-id="418f9-171">TPM 主機</span><span class="sxs-lookup"><span data-stu-id="418f9-171">TPM console</span></span>*


## <a name="uefi-menu-devices"></a><span data-ttu-id="418f9-172">UEFI 功能表：裝置</span><span class="sxs-lookup"><span data-stu-id="418f9-172">UEFI menu: Devices</span></span> 

<span data-ttu-id="418f9-173">裝置頁面可讓您啟用或停用特定裝置和元件，包括：</span><span class="sxs-lookup"><span data-stu-id="418f9-173">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="418f9-174">擴充座和 USB 連接埠</span><span class="sxs-lookup"><span data-stu-id="418f9-174">Docking and USB Ports</span></span> 

- <span data-ttu-id="418f9-175">MicroSD 或 SD 記憶卡插槽</span><span class="sxs-lookup"><span data-stu-id="418f9-175">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="418f9-176">後方攝影機</span><span class="sxs-lookup"><span data-stu-id="418f9-176">Rear Camera</span></span> 

- <span data-ttu-id="418f9-177">前方攝影機</span><span class="sxs-lookup"><span data-stu-id="418f9-177">Front Camera</span></span> 

- <span data-ttu-id="418f9-178">紅外線 (IR) 相機</span><span class="sxs-lookup"><span data-stu-id="418f9-178">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="418f9-179">Wi-Fi 和藍牙</span><span class="sxs-lookup"><span data-stu-id="418f9-179">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="418f9-180">內建音訊 (擴音器和麥克風)</span><span class="sxs-lookup"><span data-stu-id="418f9-180">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="418f9-181">每個裝置都列出一個滑杆按鈕，您可以移至啟用\*\*\*\* (的) 或關閉 (\*\*\*\* 已停用) 位置，如圖 6 所示。</span><span class="sxs-lookup"><span data-stu-id="418f9-181">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![啟用或停用特定裝置](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="418f9-183">圖 6.</span><span class="sxs-lookup"><span data-stu-id="418f9-183">Figure 6.</span></span> <span data-ttu-id="418f9-184">啟用或停用特定裝置</span><span class="sxs-lookup"><span data-stu-id="418f9-184">Enable and disable specific devices</span></span>*

## <a name="uefi-menu-boot-configuration"></a><span data-ttu-id="418f9-185">UEFI 功能表：啟動組式</span><span class="sxs-lookup"><span data-stu-id="418f9-185">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="418f9-186">啟動組配置頁面可讓您變更啟動裝置的順序，以及啟用或停用下列裝置啟動：</span><span class="sxs-lookup"><span data-stu-id="418f9-186">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="418f9-187">Windows 開機管理程式</span><span class="sxs-lookup"><span data-stu-id="418f9-187">Windows Boot Manager</span></span> 

- <span data-ttu-id="418f9-188">USB 儲存裝置</span><span class="sxs-lookup"><span data-stu-id="418f9-188">USB Storage</span></span> 

- <span data-ttu-id="418f9-189">PXE 網路</span><span class="sxs-lookup"><span data-stu-id="418f9-189">PXE Network</span></span> 

- <span data-ttu-id="418f9-190">內部儲存裝置</span><span class="sxs-lookup"><span data-stu-id="418f9-190">Internal Storage</span></span> 

<span data-ttu-id="418f9-191">您可以立即從特定的裝置開機，或是使用觸控螢幕在該裝置於清單中的項目上向左撥動。</span><span class="sxs-lookup"><span data-stu-id="418f9-191">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="418f9-192">您也可以在 Surface 裝置電源關閉的情況下，立即開機至 USB 裝置或 USB 乙太網路介面卡，方法是同時按下 \[降低音量\] 按鈕和 \[電源\] 按鈕。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="418f9-192">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="418f9-193">若要讓指定的啟動順序生效，您必須將啟用替代啟動順序\*\*\*\* 選項設定為**On**，如圖 7 所示。</span><span class="sxs-lookup"><span data-stu-id="418f9-193">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![設定 Surface 裝置的開機順序](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="418f9-195">圖 7.</span><span class="sxs-lookup"><span data-stu-id="418f9-195">Figure 7.</span></span> <span data-ttu-id="418f9-196">設定 Surface 裝置的開機順序</span><span class="sxs-lookup"><span data-stu-id="418f9-196">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="418f9-197">您也可以透過 \[針對 PXE 網路開機啟用 IPv6\] 選項，針對 PXE 開啟或關閉 IPv6 支援，例如使用 PXE 執行 Windows 部署，而 PXE 伺服器僅針對 IPv4 進行設定的情況。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="418f9-197">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <a name="uefi-menu-management"></a><span data-ttu-id="418f9-198">UEFI 功能表：管理</span><span class="sxs-lookup"><span data-stu-id="418f9-198">UEFI menu: Management</span></span>
<span data-ttu-id="418f9-199">管理頁面可讓您管理零觸控 UEFI 管理和其他功能在合格裝置上的使用，包括 Surface Pro 7、Surface Pro X 和 Surface Laptop 3。</span><span class="sxs-lookup"><span data-stu-id="418f9-199">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="418f9-200">管理零觸控 UEFI 管理和其他功能的存取權 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *圖 8。管理零觸控 UEFI 管理和其他功能的存取權*</span><span class="sxs-lookup"><span data-stu-id="418f9-200">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="418f9-201">零觸控 UEFI 管理可讓您在 Intune 中使用稱為 DFCI (的裝置設定檔，以遠端系統管理 UEFI) 。</span><span class="sxs-lookup"><span data-stu-id="418f9-201">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="418f9-202">如果您沒有設定此設定，使用 DFCI 管理合格裝置的能力會設定為 **Ready**。</span><span class="sxs-lookup"><span data-stu-id="418f9-202">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="418f9-203">若要防止 DFCI，請選取 **退出宣告**。</span><span class="sxs-lookup"><span data-stu-id="418f9-203">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="418f9-204">UEFI 管理設定頁面及 DFCI 的使用目前適用于 Surface Pro 7+、Surface Laptop Go、Surface Book 3、Surface Laptop 4、Surface Laptop 3、Surface Pro 7 和 Surface Pro X。若要深入瞭解，請參閱[Surface UEFI 設定 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="418f9-204">The UEFI Management settings page and use of DFCI is currently available for Surface Pro 7+, Surface Laptop Go, Surface Book 3, Surface Laptop 4, Surface Laptop 3, Surface Pro 7, and Surface Pro X. To learn more, see [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <a name="uefi-menu-exit"></a><span data-ttu-id="418f9-205">UEFI 功能表：離開</span><span class="sxs-lookup"><span data-stu-id="418f9-205">UEFI menu: Exit</span></span> 

<span data-ttu-id="418f9-206">使用離開**頁面上**的立即重新開機按鈕\*\*\*\* 來退出 UEFI 設定，如圖 9 所示。</span><span class="sxs-lookup"><span data-stu-id="418f9-206">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![結束 Surface UEFI 並重新啟動裝置](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="418f9-208">圖 9.</span><span class="sxs-lookup"><span data-stu-id="418f9-208">Figure 9.</span></span> <span data-ttu-id="418f9-209">按一下 \[立即重新啟動\] 以結束 Surface UEFI 並重新啟動裝置</span><span class="sxs-lookup"><span data-stu-id="418f9-209">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <a name="surface-uefi-boot-screens"></a><span data-ttu-id="418f9-210">Surface UEFI 開機畫面</span><span class="sxs-lookup"><span data-stu-id="418f9-210">Surface UEFI boot screens</span></span>

<span data-ttu-id="418f9-211">當您使用 Windows Update 或手動安裝更新 Surface 裝置韌體時，更新不會立即套用到裝置，而是在下一個重新開機循環期間套用。</span><span class="sxs-lookup"><span data-stu-id="418f9-211">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="418f9-212">您可以在管理及部署 Surface 驅動程式和固件更新中，進一步瞭解 Surface 固件 [更新程式](manage-surface-driver-and-firmware-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="418f9-212">You can find out more about the Surface firmware update process in [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span> <span data-ttu-id="418f9-213">畫面上會顯示韌體更新進度，進度列會以不同的色彩來表示每個元件的韌體。</span><span class="sxs-lookup"><span data-stu-id="418f9-213">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="418f9-214">每個元件的進度列會顯示在圖 9 到 18 中。</span><span class="sxs-lookup"><span data-stu-id="418f9-214">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Surface UEFI 韌體更新與藍色進度列](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="418f9-216">圖 10.</span><span class="sxs-lookup"><span data-stu-id="418f9-216">Figure 10.</span></span> <span data-ttu-id="418f9-217">Surface UEFI 韌體更新會顯示藍色進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-217">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![系統內嵌控制器韌體與綠色進度列](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="418f9-219">圖 11.</span><span class="sxs-lookup"><span data-stu-id="418f9-219">Figure 11.</span></span> <span data-ttu-id="418f9-220">系統內嵌控制器韌體更新會顯示綠色進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-220">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![SAM 控制器韌體更新與橘色進度列](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="418f9-222">圖 12.</span><span class="sxs-lookup"><span data-stu-id="418f9-222">Figure 12.</span></span> <span data-ttu-id="418f9-223">SAM 控制器韌體更新會顯示橘色進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-223">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Intel Management Engine 韌體與紅色進度列](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="418f9-225">圖 13.</span><span class="sxs-lookup"><span data-stu-id="418f9-225">Figure 13.</span></span> <span data-ttu-id="418f9-226">Intel Management Engine 韌體更新會顯示紅色進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-226">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Surface 觸控韌體與灰色進度列](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="418f9-228">圖 14.</span><span class="sxs-lookup"><span data-stu-id="418f9-228">Figure 14.</span></span> <span data-ttu-id="418f9-229">Surface 觸控韌體更新會顯示灰色進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-229">The Surface touch firmware update displays a gray progress bar</span></span>*

![具有淺綠色進度條的 Surface KIP 固件](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="418f9-231">圖 15.</span><span class="sxs-lookup"><span data-stu-id="418f9-231">Figure 15.</span></span> <span data-ttu-id="418f9-232">Surface KIP 固件更新會顯示淺綠色進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-232">The Surface KIP firmware update displays a light green progress bar</span></span>*

![具有粉紅色進度條的 Surface ISH 固件](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="418f9-234">圖 16 Surface ISH 的固件更新會顯示淺粉紅色的進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-234">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![具有灰色進度列的 Surface 軌跡板固件](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="418f9-236">圖 17.</span><span class="sxs-lookup"><span data-stu-id="418f9-236">Figure 17.</span></span> <span data-ttu-id="418f9-237">Surface Trackpad 的固件更新會顯示粉紅色的進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-237">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![具有淺灰色進度條的 Surface TCON 固件](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="418f9-239">圖 18.</span><span class="sxs-lookup"><span data-stu-id="418f9-239">Figure 18.</span></span> <span data-ttu-id="418f9-240">Surface TCON 固件更新會顯示淺灰色進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-240">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![具有淺紫色進度條的 Surface TPM 固件](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="418f9-242">圖 19.</span><span class="sxs-lookup"><span data-stu-id="418f9-242">Figure 19.</span></span> <span data-ttu-id="418f9-243">Surface TPM 的固件更新會顯示紫色的進度列</span><span class="sxs-lookup"><span data-stu-id="418f9-243">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="418f9-244">系統會顯示另一則警告訊息，指出安全啟動已停用，如圖 19 所示。</span><span class="sxs-lookup"><span data-stu-id="418f9-244">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![表示安全開機已停用的 Surface 開機畫面](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="418f9-246">圖 20.</span><span class="sxs-lookup"><span data-stu-id="418f9-246">Figure 20.</span></span> <span data-ttu-id="418f9-247">表示 Surface UEFI 設定中安全開機已停用的 Surface 開機畫面</span><span class="sxs-lookup"><span data-stu-id="418f9-247">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <a name="references"></a><span data-ttu-id="418f9-248">參考</span><span class="sxs-lookup"><span data-stu-id="418f9-248">References</span></span>

1. <span data-ttu-id="418f9-249">Surface Go 和 Surface Go 2 使用協力廠商 UEFI，且不支援 DFCI。</span><span class="sxs-lookup"><span data-stu-id="418f9-249">Surface Go and Surface Go 2 use a third-party UEFI and do not support DFCI.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="418f9-250">相關主題</span><span class="sxs-lookup"><span data-stu-id="418f9-250">Related topics</span></span>

- [<span data-ttu-id="418f9-251">Surface UEFI 設定的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="418f9-251">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="418f9-252">Surface 企業管理模式</span><span class="sxs-lookup"><span data-stu-id="418f9-252">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
