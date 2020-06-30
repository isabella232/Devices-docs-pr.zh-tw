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
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831654"
---
# <span data-ttu-id="750c4-104">管理 Surface UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="750c4-104">Manage Surface UEFI settings</span></span>

<span data-ttu-id="750c4-105">所有目前及未來的 Surface 裝置代都使用專為這些裝置設計的獨特的整合可延伸韌體介面（UEFI）。</span><span class="sxs-lookup"><span data-stu-id="750c4-105">All current and future generations of Surface devices use a unique Unified Extensible Firmware Interface (UEFI) engineered by Microsoft specifically for these devices.</span></span> <span data-ttu-id="750c4-106">Surface UEFI 設定能讓您啟用或停用內建的裝置和元件、保護 UEFI 設定不被變更，以及調整 Surface 裝置的啟動設定。</span><span class="sxs-lookup"><span data-stu-id="750c4-106">Surface UEFI settings provide the ability to enable or disable built-in devices and components, protect UEFI settings from being changed, and adjust the Surface device boot settings.</span></span> 

## <span data-ttu-id="750c4-107">支援雲端管理</span><span class="sxs-lookup"><span data-stu-id="750c4-107">Support for cloud-based management</span></span>

<span data-ttu-id="750c4-108">在內置於 Microsoft Intune 中的裝置固件配置介面（DFCI）設定檔（現已在公用預覽中提供），Surface UEFI 管理會將新式管理堆疊延伸到 UEFI 硬體層級。</span><span class="sxs-lookup"><span data-stu-id="750c4-108">With Device Firmware Configuration Interface (DFCI) profiles built into Microsoft Intune (now available in public preview), Surface UEFI management extends the modern management stack down to the UEFI hardware level.</span></span> <span data-ttu-id="750c4-109">DFCI 支援零觸控配，消除 BIOS 密碼，提供安全性設定（包括啟動選項和內建週邊設備）的控制權，並針對未來的高級安全性案例奠定基礎。</span><span class="sxs-lookup"><span data-stu-id="750c4-109">DFCI supports zero-touch provisioning, eliminates BIOS passwords, provides control of security settings including boot options and built-in peripherals, and lays the groundwork for advanced security scenarios in the future.</span></span> <span data-ttu-id="750c4-110">DFCI 目前可供 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3使用。</span><span class="sxs-lookup"><span data-stu-id="750c4-110">DFCI is currently available for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> <span data-ttu-id="750c4-111">如需詳細資訊，請參閱[SURFACE UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="750c4-111">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="750c4-112">開啟 Surface UEFI 功能表</span><span class="sxs-lookup"><span data-stu-id="750c4-112">Open Surface UEFI menu</span></span>

<span data-ttu-id="750c4-113">在系統啟動期間調整 UEFI 設定：</span><span class="sxs-lookup"><span data-stu-id="750c4-113">To adjust UEFI settings during system startup:</span></span>

1. <span data-ttu-id="750c4-114">關閉表面並等候大約10秒鐘，以確定它已關閉。</span><span class="sxs-lookup"><span data-stu-id="750c4-114">Shut down your Surface and wait about 10 seconds to make sure it's off.</span></span>
2. <span data-ttu-id="750c4-115">按住**音量調高**按鈕，同步選取電源按鈕，然後放開 [**電源] 按鈕。**</span><span class="sxs-lookup"><span data-stu-id="750c4-115">Press and hold the **Volume-up** button  and - at the same time - press and release the **Power button.**</span></span>
3. <span data-ttu-id="750c4-116">當您的螢幕上出現 Microsoft 或 Surface 標誌時，請繼續按住**音量**按鈕，直到出現 [UEFI] 畫面。</span><span class="sxs-lookup"><span data-stu-id="750c4-116">As the Microsoft or Surface logo appears on your screen, continue to hold the **Volume-up** button until the UEFI screen appears.</span></span>

## <span data-ttu-id="750c4-117">[UEFI 電腦資訊] 頁面</span><span class="sxs-lookup"><span data-stu-id="750c4-117">UEFI PC information page</span></span>

<span data-ttu-id="750c4-118">[電腦資訊] 頁面包含 Surface 裝置的詳細資訊：</span><span class="sxs-lookup"><span data-stu-id="750c4-118">The PC information page includes detailed information about your Surface device:</span></span> 

- <span data-ttu-id="750c4-119">**模型**-您的 surface 裝置模型將會顯示在這裡，例如 surface Book 2 或 surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="750c4-119">**Model** – Your Surface device’s model will be displayed here, such as Surface Book 2 or Surface Pro 7.</span></span> <span data-ttu-id="750c4-120">裝置的確切組態並不會顯示 (例如處理器、磁碟大小或記憶體大小)。</span><span class="sxs-lookup"><span data-stu-id="750c4-120">The exact configuration of your device is not shown, (such as processor, disk size, or memory size).</span></span> 
- <span data-ttu-id="750c4-121">**UUID** – 這個通用唯一識別碼是裝置特定的號碼，用來在部署或管理期間識別裝置。</span><span class="sxs-lookup"><span data-stu-id="750c4-121">**UUID** – This Universally Unique Identification number is specific to your device and is used to identify the device during deployment or management.</span></span> 

- <span data-ttu-id="750c4-122">**序號** – 此號碼是用來識別這個特定的 Surface 裝置，以進行資產標記和支援案例。</span><span class="sxs-lookup"><span data-stu-id="750c4-122">**Serial Number** – This number is used to identify this specific Surface device for asset tagging and support scenarios.</span></span>
- <span data-ttu-id="750c4-123">**資產標記**– 資產標記是使用[資產標記工具](https://docs.microsoft.com/surface/assettag)指派至 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="750c4-123">**Asset Tag** – The asset tag is assigned to the Surface device with the [Asset Tag Tool](https://docs.microsoft.com/surface/assettag).</span></span> 

<span data-ttu-id="750c4-124">您也能找到 Surface 裝置韌體的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="750c4-124">You will also find detailed information about the firmware of your Surface device.</span></span> <span data-ttu-id="750c4-125">Surface 裝置擁有數個內部元件，每個元件都會執行不同版本的韌體。</span><span class="sxs-lookup"><span data-stu-id="750c4-125">Surface devices have several internal components that each run different versions of firmware.</span></span> <span data-ttu-id="750c4-126">下列裝置的個別韌體版本都會顯示於 \[電腦資訊\] 頁面上 \(如圖 1 所示\)：\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="750c4-126">The firmware version of each of the following devices is displayed on the **PC information** page (as shown in Figure 1):</span></span> 

- <span data-ttu-id="750c4-127">系統 UEFI</span><span class="sxs-lookup"><span data-stu-id="750c4-127">System UEFI</span></span> 

- <span data-ttu-id="750c4-128">SAM 控制器</span><span class="sxs-lookup"><span data-stu-id="750c4-128">SAM Controller</span></span> 

- <span data-ttu-id="750c4-129">Intel 管理引擎</span><span class="sxs-lookup"><span data-stu-id="750c4-129">Intel Management Engine</span></span> 

- <span data-ttu-id="750c4-130">系統內嵌控制器</span><span class="sxs-lookup"><span data-stu-id="750c4-130">System Embedded Controller</span></span> 

- <span data-ttu-id="750c4-131">觸控韌體</span><span class="sxs-lookup"><span data-stu-id="750c4-131">Touch Firmware</span></span> 

![系統資訊和韌體版本資訊](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*<span data-ttu-id="750c4-133">圖 1.</span><span class="sxs-lookup"><span data-stu-id="750c4-133">Figure 1.</span></span> <span data-ttu-id="750c4-134">系統資訊和韌體版本資訊</span><span class="sxs-lookup"><span data-stu-id="750c4-134">System information and firmware version information</span></span>*

<span data-ttu-id="750c4-135">您可以在裝置的 [Surface 更新記錄](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中找到 Surface 裝置最新韌體版本的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="750c4-135">You can find up-to-date information about the latest firmware version for your Surface device in the [Surface Update History](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history) for your device.</span></span> 

## <span data-ttu-id="750c4-136">UEFI 安全性頁面</span><span class="sxs-lookup"><span data-stu-id="750c4-136">UEFI Security page</span></span> 

![設定 Surface UEFI 安全性設定](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*<span data-ttu-id="750c4-138">圖 2.</span><span class="sxs-lookup"><span data-stu-id="750c4-138">Figure 2.</span></span> <span data-ttu-id="750c4-139">設定 Surface UEFI 安全性設定</span><span class="sxs-lookup"><span data-stu-id="750c4-139">Configure Surface UEFI security settings</span></span>*

<span data-ttu-id="750c4-140">[安全性] 頁面可讓您設定密碼來保護 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="750c4-140">The Security page allows you to set a password to protect UEFI settings.</span></span> <span data-ttu-id="750c4-141">此密碼必須在將 Surface 裝置開機至 UEFI 時輸入。</span><span class="sxs-lookup"><span data-stu-id="750c4-141">This password must be entered when you boot the Surface device to UEFI.</span></span> <span data-ttu-id="750c4-142">密碼可以包含下列字元（如圖3所示）：</span><span class="sxs-lookup"><span data-stu-id="750c4-142">The password can contain the following characters (as shown in Figure 3):</span></span> 

- <span data-ttu-id="750c4-143">大寫字母：A-Z</span><span class="sxs-lookup"><span data-stu-id="750c4-143">Uppercase letters: A-Z</span></span> 

- <span data-ttu-id="750c4-144">小寫字母：a-z</span><span class="sxs-lookup"><span data-stu-id="750c4-144">Lowercase letters: a-z</span></span> 

- <span data-ttu-id="750c4-145">數字：1-0</span><span class="sxs-lookup"><span data-stu-id="750c4-145">Numbers: 1-0</span></span> 

- <span data-ttu-id="750c4-146">特殊字元：！ @ # $% ^& \* （）？ <>{} []-_ = + |.，;： "" "</span><span class="sxs-lookup"><span data-stu-id="750c4-146">Special characters: !@#$%^&\*()?<>{}[]-_=+|.,;:’\`”</span></span> 

<span data-ttu-id="750c4-147">密碼必須至少為 6 個字元，並會區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="750c4-147">The password must be at least 6 characters and is case sensitive.</span></span> 

![新增密碼以保護 Surface UEFI 設定](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*<span data-ttu-id="750c4-149">圖 3.</span><span class="sxs-lookup"><span data-stu-id="750c4-149">Figure 3.</span></span> <span data-ttu-id="750c4-150">新增密碼以保護 Surface UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="750c4-150">Add a password to protect Surface UEFI settings</span></span>*

<span data-ttu-id="750c4-151">您也可以在 \[安全性\] 頁面上變更 Surface 裝置的安全開機設定。</span><span class="sxs-lookup"><span data-stu-id="750c4-151">On the Security page you can also change the configuration of Secure Boot on your Surface device.</span></span> <span data-ttu-id="750c4-152">安全開機技術能防止未經授權的啟動碼將您的 Surface 裝置開機，這將能針對 Bookit 和 Rootkit 類型的惡意程式碼感染提供保護。</span><span class="sxs-lookup"><span data-stu-id="750c4-152">Secure Boot technology prevents unauthorized boot code from booting on your Surface device, which protects against bootkit and rootkit-type malware infections.</span></span> <span data-ttu-id="750c4-153">您可以停用安全開機以允許 Surface 裝置使用第三方作業系統或可開機媒體進行開機。</span><span class="sxs-lookup"><span data-stu-id="750c4-153">You can disable Secure Boot to allow your Surface device to boot third-party operating systems or bootable media.</span></span> <span data-ttu-id="750c4-154">您也可以設定 [安全啟動]，與協力廠商憑證搭配使用，如圖4所示。</span><span class="sxs-lookup"><span data-stu-id="750c4-154">You can also configure Secure Boot to work with third-party certificates, as shown in Figure 4.</span></span> <span data-ttu-id="750c4-155">於 TechNet Library 深入了解[安全開機](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)。</span><span class="sxs-lookup"><span data-stu-id="750c4-155">Read more about [Secure Boot](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview) in the TechNet Library.</span></span>

![設定安全開機](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*<span data-ttu-id="750c4-157">圖 4.</span><span class="sxs-lookup"><span data-stu-id="750c4-157">Figure 4.</span></span> <span data-ttu-id="750c4-158">設定安全開機</span><span class="sxs-lookup"><span data-stu-id="750c4-158">Configure Secure Boot</span></span>*

<span data-ttu-id="750c4-159">視您的裝置而定，您可能也可以查看您的 TPM 是已啟用或停用。</span><span class="sxs-lookup"><span data-stu-id="750c4-159">Depending on your device, you may also be able to see if your TPM is enabled or disabled.</span></span> <span data-ttu-id="750c4-160">如果您沒有看到 [**啟用 TPM** ] 設定，請在 Windows 中開啟 [services.msc] 來檢查狀態，如圖5所示。</span><span class="sxs-lookup"><span data-stu-id="750c4-160">If you do not see the **Enable TPM**  setting, open tpm.msc in Windows to check the status, as shown in Figure 5.</span></span> <span data-ttu-id="750c4-161">TPM 是用來以 BitLocker 為您裝置的資料驗證加密。</span><span class="sxs-lookup"><span data-stu-id="750c4-161">The TPM is used to authenticate encryption for your device’s data with BitLocker.</span></span> <span data-ttu-id="750c4-162">若要深入瞭解，請參閱[BitLocker 簡介](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。</span><span class="sxs-lookup"><span data-stu-id="750c4-162">To learn more, see [BitLocker overview](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview).</span></span> 

![TPM 主控台](images/manage-surface-uefi-fig5-a.png "TPM console")

*<span data-ttu-id="750c4-164">圖 5.</span><span class="sxs-lookup"><span data-stu-id="750c4-164">Figure 5.</span></span> <span data-ttu-id="750c4-165">TPM 主控台</span><span class="sxs-lookup"><span data-stu-id="750c4-165">TPM console</span></span>*


## <span data-ttu-id="750c4-166">UEFI 功能表：裝置</span><span class="sxs-lookup"><span data-stu-id="750c4-166">UEFI menu: Devices</span></span> 

<span data-ttu-id="750c4-167">[裝置] 頁面可讓您啟用或停用特定裝置和元件，包括：</span><span class="sxs-lookup"><span data-stu-id="750c4-167">The Devices page allows you to  enable or disable specific devices and components including:</span></span>

- <span data-ttu-id="750c4-168">擴充座和 USB 連接埠</span><span class="sxs-lookup"><span data-stu-id="750c4-168">Docking and USB Ports</span></span> 

- <span data-ttu-id="750c4-169">MicroSD 或 SD 記憶卡插槽</span><span class="sxs-lookup"><span data-stu-id="750c4-169">MicroSD or SD Card Slot</span></span> 

- <span data-ttu-id="750c4-170">後方攝影機</span><span class="sxs-lookup"><span data-stu-id="750c4-170">Rear Camera</span></span> 

- <span data-ttu-id="750c4-171">前方攝影機</span><span class="sxs-lookup"><span data-stu-id="750c4-171">Front Camera</span></span> 

- <span data-ttu-id="750c4-172">紅外線 (IR) 相機</span><span class="sxs-lookup"><span data-stu-id="750c4-172">Infrared (IR) Camera</span></span> 

- <span data-ttu-id="750c4-173">Wi-Fi 和藍牙</span><span class="sxs-lookup"><span data-stu-id="750c4-173">Wi-Fi and Bluetooth</span></span> 

- <span data-ttu-id="750c4-174">內建音訊 (擴音器和麥克風)</span><span class="sxs-lookup"><span data-stu-id="750c4-174">Onboard Audio (Speakers and Microphone)</span></span> 

<span data-ttu-id="750c4-175">列出的每個裝置都有一個滑杆按鈕，您可以將它移至 [**開啟**] （啟用）或 [**關閉**] （停用）位置，如圖6所示。</span><span class="sxs-lookup"><span data-stu-id="750c4-175">Each device is listed with a slider button that you can move to **On** (enabled) or **Off** (disabled) position, as shown in Figure 6.</span></span> 

![啟用或停用特定裝置](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*<span data-ttu-id="750c4-177">圖 6.</span><span class="sxs-lookup"><span data-stu-id="750c4-177">Figure 6.</span></span> <span data-ttu-id="750c4-178">啟用或停用特定裝置</span><span class="sxs-lookup"><span data-stu-id="750c4-178">Enable and disable specific devices</span></span>*

## <span data-ttu-id="750c4-179">UEFI 功能表：啟動設定</span><span class="sxs-lookup"><span data-stu-id="750c4-179">UEFI menu: Boot configuration</span></span> 

<span data-ttu-id="750c4-180">[啟動設定] 頁面可讓您變更啟動裝置的順序，以及啟用或停用啟動下列裝置：</span><span class="sxs-lookup"><span data-stu-id="750c4-180">The Boot Configuration page allows you to change the order of your boot devices as well as enable or disable boot of the following devices:</span></span> 

- <span data-ttu-id="750c4-181">Windows 開機管理程式</span><span class="sxs-lookup"><span data-stu-id="750c4-181">Windows Boot Manager</span></span> 

- <span data-ttu-id="750c4-182">USB 儲存裝置</span><span class="sxs-lookup"><span data-stu-id="750c4-182">USB Storage</span></span> 

- <span data-ttu-id="750c4-183">PXE 網路</span><span class="sxs-lookup"><span data-stu-id="750c4-183">PXE Network</span></span> 

- <span data-ttu-id="750c4-184">內部儲存裝置</span><span class="sxs-lookup"><span data-stu-id="750c4-184">Internal Storage</span></span> 

<span data-ttu-id="750c4-185">您可以立即從特定的裝置開機，或是使用觸控螢幕在該裝置於清單中的項目上向左撥動。</span><span class="sxs-lookup"><span data-stu-id="750c4-185">You can boot from a specific device immediately, or you can swipe left on that device’s entry in the list using the touchscreen.</span></span> <span data-ttu-id="750c4-186">您也可以在 Surface 裝置電源關閉的情況下，立即開機至 USB 裝置或 USB 乙太網路介面卡，方法是同時按下 \[降低音量\] 按鈕和 \[電源\] 按鈕。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="750c4-186">You can also boot immediately to a USB device or USB Ethernet adapter when the Surface device is powered off by pressing the **Volume Down** button and the **Power** button simultaneously.</span></span> 

<span data-ttu-id="750c4-187">若要讓指定的引導順序生效，您必須將 [**啟用備用啟動順序**] 選項設定為 [**開啟**]，如圖7所示。</span><span class="sxs-lookup"><span data-stu-id="750c4-187">For the specified boot order to take effect, you must set the **Enable Alternate Boot Sequence** option to **On**, as shown in Figure 7.</span></span> 

![設定 Surface 裝置的開機順序](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*<span data-ttu-id="750c4-189">圖 7.</span><span class="sxs-lookup"><span data-stu-id="750c4-189">Figure 7.</span></span> <span data-ttu-id="750c4-190">設定 Surface 裝置的開機順序</span><span class="sxs-lookup"><span data-stu-id="750c4-190">Configure the boot order for your Surface device</span></span>* 

<span data-ttu-id="750c4-191">您也可以透過 \[針對 PXE 網路開機啟用 IPv6\] 選項，針對 PXE 開啟或關閉 IPv6 支援，例如使用 PXE 執行 Windows 部署，而 PXE 伺服器僅針對 IPv4 進行設定的情況。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="750c4-191">You can also turn on and off IPv6 support for PXE with the **Enable IPv6 for PXE Network Boot** option, for example when performing a Windows deployment using PXE where the PXE server is configured for IPv4 only.</span></span>  

## <span data-ttu-id="750c4-192">UEFI 功能表：管理</span><span class="sxs-lookup"><span data-stu-id="750c4-192">UEFI menu: Management</span></span>
<span data-ttu-id="750c4-193">[管理] 頁面可讓您管理在合格的裝置上使用零觸控 UEFI 管理和其他功能，包括 Surface Pro 7、Surface Pro X 及 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="750c4-193">The Management page allows you to manage use of Zero Touch UEFI Management and other features on eligible devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

![<span data-ttu-id="750c4-194">管理零觸控 UEFI 管理的存取權和其他功能 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *圖8。管理零觸控 UEFI 管理和其他功能的存取權*</span><span class="sxs-lookup"><span data-stu-id="750c4-194">Manage access to Zero Touch UEFI Management and other features](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
*Figure 8. Manage access to Zero Touch UEFI Management and other features*</span></span> 


<span data-ttu-id="750c4-195">零觸控 UEFI 管理可讓您在名為 Device 固件配置介面（DFCI）的 Intune 中使用裝置設定檔來遠端系統管理 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="750c4-195">Zero Touch UEFI Management lets you remotely manage UEFI settings  by using a device profile within Intune called Device Firmware Configuration Interface (DFCI).</span></span> <span data-ttu-id="750c4-196">如果您未設定此設定，管理具有 DFCI 的合格裝置的功能會設定為 [**就緒**]。</span><span class="sxs-lookup"><span data-stu-id="750c4-196">If you do not configure this setting, the ability to manage eligible devices with DFCI is set to **Ready**.</span></span> <span data-ttu-id="750c4-197">若要防止 DFCI，**請選取 [退出宣告]**。</span><span class="sxs-lookup"><span data-stu-id="750c4-197">To prevent DFCI, select **Opt-Out**.</span></span> 

> [!NOTE]
> <span data-ttu-id="750c4-198">只有 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3提供 [UEFI 管理設定] 頁面和使用 DFCI。</span><span class="sxs-lookup"><span data-stu-id="750c4-198">The UEFI Management settings page and use of DFCI is only available on Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>  

<span data-ttu-id="750c4-199">如需詳細資訊，請參閱[SURFACE UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="750c4-199">For more information, refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

## <span data-ttu-id="750c4-200">UEFI 功能表：結束</span><span class="sxs-lookup"><span data-stu-id="750c4-200">UEFI menu: Exit</span></span> 

<span data-ttu-id="750c4-201">使用 [結束 **] 頁面上的 [** **立即重新開機**] 按鈕，即可結束 UEFI 設定，如圖9所示。</span><span class="sxs-lookup"><span data-stu-id="750c4-201">Use the **Restart Now** button on the **Exit** page to exit UEFI settings, as shown in Figure 9.</span></span> 

![結束 Surface UEFI 並重新啟動裝置](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*<span data-ttu-id="750c4-203">圖 9.</span><span class="sxs-lookup"><span data-stu-id="750c4-203">Figure 9.</span></span> <span data-ttu-id="750c4-204">按一下 \[立即重新啟動\] 以結束 Surface UEFI 並重新啟動裝置</span><span class="sxs-lookup"><span data-stu-id="750c4-204">Click Restart Now to exit Surface UEFI and restart the device</span></span>*

## <span data-ttu-id="750c4-205">Surface UEFI 開機畫面</span><span class="sxs-lookup"><span data-stu-id="750c4-205">Surface UEFI boot screens</span></span>

<span data-ttu-id="750c4-206">當您使用 Windows Update 或手動安裝更新 Surface 裝置韌體時，更新不會立即套用到裝置，而是在下一個重新開機循環期間套用。</span><span class="sxs-lookup"><span data-stu-id="750c4-206">When you update Surface device firmware, by using either Windows Update or manual installation, the updates are not applied immediately to the device, but instead during the next reboot cycle.</span></span> <span data-ttu-id="750c4-207">您可以在[管理 Surface 的驅動程式和韌體更新](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)中深入了解 Surface 韌體更新過程。</span><span class="sxs-lookup"><span data-stu-id="750c4-207">You can find out more about the Surface firmware update process in [Manage Surface driver and firmware updates](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates).</span></span> <span data-ttu-id="750c4-208">畫面上會顯示韌體更新進度，進度列會以不同的色彩來表示每個元件的韌體。</span><span class="sxs-lookup"><span data-stu-id="750c4-208">The progress of the firmware update is displayed on a screen with progress bars of differing colors to indicate the firmware for each component.</span></span> <span data-ttu-id="750c4-209">每個元件的進度列都會顯示在 [圖 9] 到 [18] 中。</span><span class="sxs-lookup"><span data-stu-id="750c4-209">Each component’s progress bar is shown in Figures 9 through 18.</span></span>

![Surface UEFI 韌體更新與藍色進度列](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*<span data-ttu-id="750c4-211">圖 10.</span><span class="sxs-lookup"><span data-stu-id="750c4-211">Figure 10.</span></span> <span data-ttu-id="750c4-212">Surface UEFI 韌體更新會顯示藍色進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-212">The Surface UEFI firmware update displays a blue progress bar</span></span>*

![系統內嵌控制器韌體與綠色進度列](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*<span data-ttu-id="750c4-214">圖 11.</span><span class="sxs-lookup"><span data-stu-id="750c4-214">Figure 11.</span></span> <span data-ttu-id="750c4-215">系統內嵌控制器韌體更新會顯示綠色進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-215">The System Embedded Controller firmware update displays a green progress bar</span></span>*

![SAM 控制器韌體更新與橘色進度列](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*<span data-ttu-id="750c4-217">圖 12.</span><span class="sxs-lookup"><span data-stu-id="750c4-217">Figure 12.</span></span> <span data-ttu-id="750c4-218">SAM 控制器韌體更新會顯示橘色進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-218">The SAM Controller firmware update displays an orange progress bar</span></span>*

![Intel Management Engine 韌體與紅色進度列](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*<span data-ttu-id="750c4-220">圖 13.</span><span class="sxs-lookup"><span data-stu-id="750c4-220">Figure 13.</span></span> <span data-ttu-id="750c4-221">Intel Management Engine 韌體更新會顯示紅色進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-221">The Intel Management Engine firmware update displays a red progress bar</span></span>*

![Surface 觸控韌體與灰色進度列](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*<span data-ttu-id="750c4-223">圖 14.</span><span class="sxs-lookup"><span data-stu-id="750c4-223">Figure 14.</span></span> <span data-ttu-id="750c4-224">Surface 觸控韌體更新會顯示灰色進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-224">The Surface touch firmware update displays a gray progress bar</span></span>*

![表面 KIP 固件為淺綠色的進度列](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*<span data-ttu-id="750c4-226">圖 15.</span><span class="sxs-lookup"><span data-stu-id="750c4-226">Figure 15.</span></span> <span data-ttu-id="750c4-227">Surface KIP 固件更新會顯示淺綠色的進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-227">The Surface KIP firmware update displays a light green progress bar</span></span>*

![表面 ISH 固件與粉紅色的進度列](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*<span data-ttu-id="750c4-229">圖 16 Surface ISH 固件更新顯示淺粉紅色的進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-229">Figure 16 The Surface ISH firmware update displays a light pink progress bar</span></span>*

![具有灰色進度列的 Surface 軌跡板固件](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*<span data-ttu-id="750c4-231">圖 17.</span><span class="sxs-lookup"><span data-stu-id="750c4-231">Figure 17.</span></span> <span data-ttu-id="750c4-232">Surface 軌跡板固件更新顯示粉紅色的進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-232">The Surface Trackpad firmware update displays a pink progress bar</span></span>*

![含淺灰色進度列的 Surface TCON 固件](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*<span data-ttu-id="750c4-234">圖 18.</span><span class="sxs-lookup"><span data-stu-id="750c4-234">Figure 18.</span></span> <span data-ttu-id="750c4-235">Surface TCON 固件更新會顯示淺灰色進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-235">The Surface TCON firmware update displays a light gray progress bar</span></span>*


![含淺紫色進度列的 Surface TPM 固件](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*<span data-ttu-id="750c4-237">圖 19.</span><span class="sxs-lookup"><span data-stu-id="750c4-237">Figure 19.</span></span> <span data-ttu-id="750c4-238">Surface TPM 固件更新顯示紫色進度列</span><span class="sxs-lookup"><span data-stu-id="750c4-238">The Surface TPM firmware update displays a purple progress bar</span></span>*


>[!NOTE]
><span data-ttu-id="750c4-239">隨即會顯示另一個指示安全啟動已停用的警告訊息，如圖19所示。</span><span class="sxs-lookup"><span data-stu-id="750c4-239">An additional warning message that indicates Secure Boot is disabled is displayed, as shown in Figure 19.</span></span>

![表示安全開機已停用的 Surface 開機畫面](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*<span data-ttu-id="750c4-241">圖 20.</span><span class="sxs-lookup"><span data-stu-id="750c4-241">Figure 20.</span></span> <span data-ttu-id="750c4-242">表示 Surface UEFI 設定中安全開機已停用的 Surface 開機畫面</span><span class="sxs-lookup"><span data-stu-id="750c4-242">Surface boot screen that indicates Secure Boot has been disabled in Surface UEFI settings</span></span>*

## <span data-ttu-id="750c4-243">相關主題</span><span class="sxs-lookup"><span data-stu-id="750c4-243">Related topics</span></span>

- [<span data-ttu-id="750c4-244">Surface UEFI 設定的 Intune 管理</span><span class="sxs-lookup"><span data-stu-id="750c4-244">Intune management of Surface UEFI settings</span></span>](surface-manage-dfci-guide.md)

-  [<span data-ttu-id="750c4-245">Surface 企業管理模式</span><span class="sxs-lookup"><span data-stu-id="750c4-245">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
