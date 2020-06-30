---
title: Surface Enterprise 管理模式（Surface）
description: 瞭解使用 Surface UEFI 的 Surface 裝置的這項功能如何協助您保護及管理貴組織內的固件設定。
keywords: uefi、設定、固件、安全、semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 05/26/2020
ms.openlocfilehash: 116aeb6d1d92f387efa34319f7852febda729207
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831530"
---
# <span data-ttu-id="004ed-104">Microsoft Surface Enterprise 管理模式</span><span class="sxs-lookup"><span data-stu-id="004ed-104">Microsoft Surface Enterprise Management Mode</span></span>

<span data-ttu-id="004ed-105">Microsoft Surface Enterprise 管理模式（SEMM）是具有 Surface UEFI 的 Surface 裝置功能，可讓您保護及管理貴組織內的固件設定。</span><span class="sxs-lookup"><span data-stu-id="004ed-105">Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface UEFI that allows you to secure and manage firmware settings within your organization.</span></span> <span data-ttu-id="004ed-106">有了 SEMM，IT 專業人員就能準備 UEFI 設定的設定，並在 Surface 裝置上安裝它們。</span><span class="sxs-lookup"><span data-stu-id="004ed-106">With SEMM, IT professionals can prepare configurations of UEFI settings and install them on a Surface device.</span></span> <span data-ttu-id="004ed-107">除了能夠設定 UEFI 設定之外，SEMM 也會使用憑證來保護設定不會受到未經授權的篡改或移除。</span><span class="sxs-lookup"><span data-stu-id="004ed-107">In addition to the ability to configure UEFI settings, SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal.</span></span>

>[!NOTE]
><span data-ttu-id="004ed-108">SEMM 只能在具有 Surface UEFI 固件的裝置上使用。</span><span class="sxs-lookup"><span data-stu-id="004ed-108">SEMM is only available on devices with Surface UEFI firmware.</span></span> <span data-ttu-id="004ed-109">這包括大多數的 Surface 裝置，包括 Surface Pro 7、Surface Pro X 和 Surface 膝上型3商業 Sku （含 Intel 處理器）。</span><span class="sxs-lookup"><span data-stu-id="004ed-109">This includes most Surface devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3 commercial SKUs with an Intel processor.</span></span> <span data-ttu-id="004ed-110">在 15 "Surface 膝上型電腦 3 SKU （含 AMD 處理器）上不支援 SEMM （僅適用于零售 SKU）。</span><span class="sxs-lookup"><span data-stu-id="004ed-110">SEMM is not supported on the 15" Surface Laptop 3 SKU with AMD processor (only available as a retail SKU).</span></span> 

<span data-ttu-id="004ed-111">當 Surface 裝置是由 SEMM 進行設定，並以 SEMM 憑證加以保護時，它們會被視為已在 SEMM 中*註冊*。</span><span class="sxs-lookup"><span data-stu-id="004ed-111">When Surface devices are configured by SEMM and secured with the SEMM certificate, they are considered *enrolled* in SEMM.</span></span> <span data-ttu-id="004ed-112">移除 SEMM 憑證並將 UEFI 設定傳回給裝置的使用者時，Surface 裝置會被視為 SEMM 中的*unenrolled* 。</span><span class="sxs-lookup"><span data-stu-id="004ed-112">When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.</span></span>

<span data-ttu-id="004ed-113">您可以使用兩個管理選項來管理 SEMM 和已註冊的 Surface 裝置，這是獨立的工具或與 Microsoft 端點建構管理員的整合。</span><span class="sxs-lookup"><span data-stu-id="004ed-113">There are two administrative options you can use to manage SEMM and enrolled Surface devices – a standalone tool or integration with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="004ed-114">本文將說明稱為 Microsoft Surface UEFI 配置單元的 SEMM 獨立工具。</span><span class="sxs-lookup"><span data-stu-id="004ed-114">The SEMM standalone tool, called the Microsoft Surface UEFI Configurator, is described in this article.</span></span> <span data-ttu-id="004ed-115">如需有關如何使用 Microsoft 端點設定管理員管理 SEMM 的詳細資訊，請參閱[使用 Microsoft 端點組態管理員管理裝置與 SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)。</span><span class="sxs-lookup"><span data-stu-id="004ed-115">For more information about how to manage SEMM with Microsoft Endpoint Configuration Manager, see [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).</span></span>


## <span data-ttu-id="004ed-116">Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="004ed-116">Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="004ed-117">SEMM 的主要工作區是 Microsoft Surface UEFI 配置單元，如圖1所示。</span><span class="sxs-lookup"><span data-stu-id="004ed-117">The primary workspace of SEMM is Microsoft Surface UEFI Configurator, as shown in Figure 1.</span></span> <span data-ttu-id="004ed-118">Microsoft Surface UEFI 設定檔是用來建立 Windows Installer （.msi）套件或 WinPE 影像的工具，這些元件是用來在 Surface 裝置上註冊、設定及取消封裝 SEMM。</span><span class="sxs-lookup"><span data-stu-id="004ed-118">Microsoft Surface UEFI Configurator is a tool that is used to create Windows Installer (.msi) packages or WinPE images that are used to enroll, configure, and unenroll SEMM on a Surface device.</span></span> <span data-ttu-id="004ed-119">這些套件包含指定 UEFI 設定的設定檔。</span><span class="sxs-lookup"><span data-stu-id="004ed-119">These packages contain a configuration file where the settings for UEFI are specified.</span></span> <span data-ttu-id="004ed-120">SEMM 套件也會包含安裝並儲存在固件中的憑證，並用於在應用 UEFI 設定之前驗證設定檔的簽名。</span><span class="sxs-lookup"><span data-stu-id="004ed-120">SEMM packages also contain a certificate that is installed and stored in firmware and used to verify the signature of configuration files before UEFI settings are applied.</span></span>

>[!NOTE]
><span data-ttu-id="004ed-121">您現在可以使用 Surface UEFI 配置器和 SEMM 來管理 Surface Dock 2 上的埠。</span><span class="sxs-lookup"><span data-stu-id="004ed-121">You can now use Surface UEFI Configurator and SEMM to manage ports on Surface Dock 2.</span></span> <span data-ttu-id="004ed-122">若要深入瞭解，請參閱[使用 SEMM 的安全 Surface Dock 2 埠](secure-surface-dock-ports-semm.md)。</span><span class="sxs-lookup"><span data-stu-id="004ed-122">To learn more, see [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).</span></span>

![Microsoft Surface UEFI 配置器](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*<span data-ttu-id="004ed-124">圖 1。</span><span class="sxs-lookup"><span data-stu-id="004ed-124">Figure 1.</span></span> <span data-ttu-id="004ed-125">Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="004ed-125">Microsoft Surface UEFI Configurator</span></span>*


<span data-ttu-id="004ed-126">您可以在三種模式中使用 Microsoft Surface UEFI 配置單元工具：</span><span class="sxs-lookup"><span data-stu-id="004ed-126">You can use the Microsoft Surface UEFI Configurator tool in three modes:</span></span>

* <span data-ttu-id="004ed-127">[SURFACE UEFI 配置套件](#configuration-package)。</span><span class="sxs-lookup"><span data-stu-id="004ed-127">[Surface UEFI Configuration Package](#configuration-package).</span></span> <span data-ttu-id="004ed-128">使用此模式來建立 Surface UEFI 配置套件，以在 SEMM 中註冊 Surface 裝置，以及在已註冊的裝置上設定 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="004ed-128">Use this mode to create a Surface UEFI configuration package to enroll a Surface device in SEMM and to configure UEFI settings on enrolled devices.</span></span>
* <span data-ttu-id="004ed-129">[SURFACE UEFI 重設套件](#reset-package)。</span><span class="sxs-lookup"><span data-stu-id="004ed-129">[Surface UEFI Reset Package](#reset-package).</span></span> <span data-ttu-id="004ed-130">使用此模式從 SEMM 取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="004ed-130">Use this mode to unenroll a Surface device from SEMM.</span></span>
* <span data-ttu-id="004ed-131">[SURFACE UEFI 恢復要求](#recovery-request)。</span><span class="sxs-lookup"><span data-stu-id="004ed-131">[Surface UEFI Recovery Request](#recovery-request).</span></span> <span data-ttu-id="004ed-132">使用此模式來回應從 SEMM 取消註冊 Surface 裝置的復原要求，而該裝置的重設套件作業不成功。</span><span class="sxs-lookup"><span data-stu-id="004ed-132">Use this mode to respond to a recovery request to unenroll a Surface device from SEMM where a Reset Package operation is not successful.</span></span>


#### <span data-ttu-id="004ed-133">下載 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="004ed-133">Download Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="004ed-134">您可以從 Microsoft 下載中心的 [[表面工具](https://www.microsoft.com/download/details.aspx?id=46703)] 頁面下載 MICROSOFT Surface UEFI 設定檔。</span><span class="sxs-lookup"><span data-stu-id="004ed-134">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

### <span data-ttu-id="004ed-135">配置套件</span><span class="sxs-lookup"><span data-stu-id="004ed-135">Configuration package</span></span>

<span data-ttu-id="004ed-136">Surface UEFI 配置套件是在 Surface 裝置上實現及管理 SEMM 的主要機制。</span><span class="sxs-lookup"><span data-stu-id="004ed-136">Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices.</span></span> <span data-ttu-id="004ed-137">這些套件包含在 Microsoft Surface UEFI 設定檔和憑證檔案中建立套件時指定的 UEFI 設定檔案，如圖2所示。</span><span class="sxs-lookup"><span data-stu-id="004ed-137">These packages contain a configuration file of UEFI settings specified during creation of the package in Microsoft Surface UEFI Configurator and a certificate file, as shown in Figure 2.</span></span> <span data-ttu-id="004ed-138">當您第一次在尚未註冊 SEMM 的 Surface 裝置上執行配置套件時，它會在裝置的固件中設定證書檔案，並在 SEMM 中註冊該裝置。</span><span class="sxs-lookup"><span data-stu-id="004ed-138">When a configuration package is run for the first time on a Surface device that is not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM.</span></span> <span data-ttu-id="004ed-139">在 SEMM 中註冊裝置時，系統會提示您在儲存證書檔案並完成註冊前，先提供 SEMM 憑證指紋的最後兩位數，以確認該操作。</span><span class="sxs-lookup"><span data-stu-id="004ed-139">When enrolling a device in SEMM, you will be prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint before the certificate file is stored and the enrollment can complete.</span></span> <span data-ttu-id="004ed-140">此確認要求在註冊時，在裝置上提供使用者，以執行確認。</span><span class="sxs-lookup"><span data-stu-id="004ed-140">This confirmation requires that a user be present at the device at the time of enrollment to perform the confirmation.</span></span>

![使用憑證保護 SEMM 設定套件](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*<span data-ttu-id="004ed-142">圖 2.</span><span class="sxs-lookup"><span data-stu-id="004ed-142">Figure 2.</span></span> <span data-ttu-id="004ed-143">使用憑證保護 SEMM 設定套件</span><span class="sxs-lookup"><span data-stu-id="004ed-143">Secure a SEMM configuration package with a certificate</span></span>*

<span data-ttu-id="004ed-144">如需 SEMM 憑證需求的詳細資訊，請參閱本文的[Surface Enterprise 管理模式證書需求](#surface-enterprise-management-mode-certificate-requirements)一節。</span><span class="sxs-lookup"><span data-stu-id="004ed-144">See the [Surface Enterprise Management Mode certificate requirements](#surface-enterprise-management-mode-certificate-requirements) section of this article for more information about the requirements for the SEMM certificate.</span></span>

>[!NOTE]
><span data-ttu-id="004ed-145">您也可以使用 SEMM 來指定 UEFI 密碼，以查看 Surface UEFI 的**安全性**、**裝置**、**啟動**設定或**企業管理**頁面所需。</span><span class="sxs-lookup"><span data-stu-id="004ed-145">You can also specify a UEFI password with SEMM that is required to view the **Security**, **Devices**, **Boot Configuration**, or **Enterprise Management** pages of Surface UEFI.</span></span>

<span data-ttu-id="004ed-146">在裝置註冊 SEMM 之後，系統會讀取配置檔案，並將檔案中指定的設定套用至 UEFI。</span><span class="sxs-lookup"><span data-stu-id="004ed-146">After a device is enrolled in SEMM, the configuration file is read and the settings specified in the file are applied to UEFI.</span></span> <span data-ttu-id="004ed-147">當您在已在 SEMM 中註冊的裝置上執行設定套件時，系統會針對儲存在裝置固件中的憑證檢查設定檔的簽名。</span><span class="sxs-lookup"><span data-stu-id="004ed-147">When you run a configuration package on a device that is already enrolled in SEMM, the signature of the configuration file is checked against the certificate that is stored in the device firmware.</span></span> <span data-ttu-id="004ed-148">如果簽名不相符，就不會將變更套用到裝置。</span><span class="sxs-lookup"><span data-stu-id="004ed-148">If the signature does not match, no changes are applied to the device.</span></span>

### <span data-ttu-id="004ed-149">使用 SEMM 在 Surface UEFI 中啟用或停用裝置</span><span class="sxs-lookup"><span data-stu-id="004ed-149">Enable or disable devices in Surface UEFI with SEMM</span></span>

<span data-ttu-id="004ed-150">下列清單顯示所有可在 SEMM 中管理的裝置：</span><span class="sxs-lookup"><span data-stu-id="004ed-150">The following list shows all the available devices you can manage in SEMM:</span></span>

* <span data-ttu-id="004ed-151">插接 USB 埠</span><span class="sxs-lookup"><span data-stu-id="004ed-151">Docking USB Port</span></span>
* <span data-ttu-id="004ed-152">板載音訊</span><span class="sxs-lookup"><span data-stu-id="004ed-152">On-board Audio</span></span>
* <span data-ttu-id="004ed-153">DGPU</span><span class="sxs-lookup"><span data-stu-id="004ed-153">DGPU</span></span>
* <span data-ttu-id="004ed-154">實體鍵盤保護蓋</span><span class="sxs-lookup"><span data-stu-id="004ed-154">Type Cover</span></span>
* <span data-ttu-id="004ed-155">微型 SD 記憶卡</span><span class="sxs-lookup"><span data-stu-id="004ed-155">Micro SD Card</span></span>
* <span data-ttu-id="004ed-156">前方攝影機</span><span class="sxs-lookup"><span data-stu-id="004ed-156">Front Camera</span></span>
* <span data-ttu-id="004ed-157">後方攝影機</span><span class="sxs-lookup"><span data-stu-id="004ed-157">Rear Camera</span></span>
* <span data-ttu-id="004ed-158">Windows Hello 版紅外攝影機</span><span class="sxs-lookup"><span data-stu-id="004ed-158">Infrared Camera, for Windows Hello</span></span>
* <span data-ttu-id="004ed-159">僅限藍牙</span><span class="sxs-lookup"><span data-stu-id="004ed-159">Bluetooth Only</span></span>
* <span data-ttu-id="004ed-160">Wi-Fi 和藍牙</span><span class="sxs-lookup"><span data-stu-id="004ed-160">Wi-Fi and Bluetooth</span></span>
* <span data-ttu-id="004ed-161">             LTE           </span><span class="sxs-lookup"><span data-stu-id="004ed-161">LTE</span></span>

 >[!NOTE]
><span data-ttu-id="004ed-162">出現在 [UEFI 裝置] 頁面上的內建裝置，可能會根據您的裝置或公司環境而有所不同。</span><span class="sxs-lookup"><span data-stu-id="004ed-162">The built-in devices that appear in the UEFI Devices page may vary depending on your device or corporate environment.</span></span> <span data-ttu-id="004ed-163">例如，Surface Pro X 上不支援 UEFI 裝置頁面;LTE 只會出現在裝有 LTE 的裝置上。</span><span class="sxs-lookup"><span data-stu-id="004ed-163">For example, the UEFI Devices page is not supported on Surface Pro X; LTE only appears on LTE-equipped devices.</span></span> 
### <span data-ttu-id="004ed-164">使用 SEMM 設定高級設定</span><span class="sxs-lookup"><span data-stu-id="004ed-164">Configure advanced settings with SEMM</span></span>
**<span data-ttu-id="004ed-165">表 1.</span><span class="sxs-lookup"><span data-stu-id="004ed-165">Table 1.</span></span> <span data-ttu-id="004ed-166">進階設定</span><span class="sxs-lookup"><span data-stu-id="004ed-166">Advanced settings</span></span>**

| <span data-ttu-id="004ed-167">設定</span><span class="sxs-lookup"><span data-stu-id="004ed-167">Setting</span></span>                            | <span data-ttu-id="004ed-168">描述</span><span class="sxs-lookup"><span data-stu-id="004ed-168">Description</span></span>                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="004ed-169">適用於 PXE 開機 的 IPv6</span><span class="sxs-lookup"><span data-stu-id="004ed-169">IPv6 for PXE Boot</span></span>                  | <span data-ttu-id="004ed-170">可讓您管理 PXE 啟動的 Ipv6 支援。</span><span class="sxs-lookup"><span data-stu-id="004ed-170">Allows you to manage Ipv6 support for PXE boot.</span></span> <span data-ttu-id="004ed-171">如果您未設定此設定，則會停用 IPv6 啟動的 IPv6 支援。</span><span class="sxs-lookup"><span data-stu-id="004ed-171">If you do not configure this setting, IPv6 support for PXE boot is disabled.</span></span>                                                                               |
| <span data-ttu-id="004ed-172">替代開機</span><span class="sxs-lookup"><span data-stu-id="004ed-172">Alternate Boot</span></span>                     | <span data-ttu-id="004ed-173">您可以在啟動期間按下 [音量] 按鈕和 [電源] 按鈕，來管理使用替代啟動順序直接從 USB 或乙太裝置啟動。</span><span class="sxs-lookup"><span data-stu-id="004ed-173">Allows you to manage use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot.</span></span> <span data-ttu-id="004ed-174">如果您未設定此設定，則會啟用備用啟動。</span><span class="sxs-lookup"><span data-stu-id="004ed-174">If you do not configure this setting, Alternate boot is enabled.</span></span> |
| <span data-ttu-id="004ed-175">開機順序鎖定</span><span class="sxs-lookup"><span data-stu-id="004ed-175">Boot Order Lock</span></span>                    | <span data-ttu-id="004ed-176">可讓您鎖定啟動順序以防止變更。</span><span class="sxs-lookup"><span data-stu-id="004ed-176">Allows you to lock the boot order to prevent changes.</span></span> <span data-ttu-id="004ed-177">如果您未設定此設定，則會停用 [啟動訂單鎖定]。</span><span class="sxs-lookup"><span data-stu-id="004ed-177">If you do not configure this setting, Boot Order Lock is disabled.</span></span>                                                                                                        |
| <span data-ttu-id="004ed-178">USB 開機</span><span class="sxs-lookup"><span data-stu-id="004ed-178">USB Boot</span></span>                           | <span data-ttu-id="004ed-179">可讓您管理 USB 裝置的啟動。</span><span class="sxs-lookup"><span data-stu-id="004ed-179">Allows you to manage booting to USB devices.</span></span> <span data-ttu-id="004ed-180">如果您未設定此設定，則會啟用 USB 啟動。</span><span class="sxs-lookup"><span data-stu-id="004ed-180">If you do not configure this setting, USB Boot is enabled.</span></span>                                                                                                                 |
| <span data-ttu-id="004ed-181">網路堆疊</span><span class="sxs-lookup"><span data-stu-id="004ed-181">Network Stack</span></span>                      | <span data-ttu-id="004ed-182">可讓您管理網路堆疊啟動設定。</span><span class="sxs-lookup"><span data-stu-id="004ed-182">Allows you to manage Network Stack boot settings.</span></span> <span data-ttu-id="004ed-183">如果您未設定此設定，系統會停用管理網路堆疊啟動設定的功能。</span><span class="sxs-lookup"><span data-stu-id="004ed-183">If you do not configure this setting,  the ability to manage Network Stack boot settings is disabled.</span></span>                                                                                                           |
| <span data-ttu-id="004ed-184">自動開啟電源</span><span class="sxs-lookup"><span data-stu-id="004ed-184">Auto Power On</span></span>                      | <span data-ttu-id="004ed-185">可讓您管理自動啟動電源設定。</span><span class="sxs-lookup"><span data-stu-id="004ed-185">Allows you to manage Auto Power On boot settings.</span></span> <span data-ttu-id="004ed-186">如果您未設定此設定，則會啟用 [自動加電] 功能。</span><span class="sxs-lookup"><span data-stu-id="004ed-186">If you do not configure this setting, Auto Power on is enabled.</span></span>                                                                                                        |
| <span data-ttu-id="004ed-187">同時多重執行緒（SMT）</span><span class="sxs-lookup"><span data-stu-id="004ed-187">Simultaneous Multi-Threading (SMT)</span></span> | <span data-ttu-id="004ed-188">可讓您管理同時多執行緒處理（SMT），以啟用或停用超執行緒。</span><span class="sxs-lookup"><span data-stu-id="004ed-188">Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading.</span></span> <span data-ttu-id="004ed-189">如果您未設定此設定，則會啟用 SMT。</span><span class="sxs-lookup"><span data-stu-id="004ed-189">If you do not configure this setting, SMT is enabled.</span></span>                                                  |
|<span data-ttu-id="004ed-190">啟用電池限制</span><span class="sxs-lookup"><span data-stu-id="004ed-190">Enable Battery limit</span></span>| <span data-ttu-id="004ed-191">可讓您管理電池限制功能。</span><span class="sxs-lookup"><span data-stu-id="004ed-191">Allows you to manage Battery limit functionality.</span></span> <span data-ttu-id="004ed-192">如果您未設定此設定，則會啟用電池計量限制</span><span class="sxs-lookup"><span data-stu-id="004ed-192">If you do not configure this setting, Battery limit is enabled</span></span> |
| <span data-ttu-id="004ed-193">安全性</span><span class="sxs-lookup"><span data-stu-id="004ed-193">Security</span></span>                           | <span data-ttu-id="004ed-194">顯示 [Surface UEFI**安全性**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="004ed-194">Displays the Surface UEFI **Security** page.</span></span> <span data-ttu-id="004ed-195">如果您未設定此設定，就會顯示 [安全性] 頁面。</span><span class="sxs-lookup"><span data-stu-id="004ed-195">If you do not configure this setting, the Security page is displayed.</span></span>                                                                                                                 |
| <span data-ttu-id="004ed-196">裝置</span><span class="sxs-lookup"><span data-stu-id="004ed-196">Devices</span></span>                            | <span data-ttu-id="004ed-197">顯示 [Surface UEFI**裝置**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="004ed-197">Displays the Surface UEFI **Devices** page.</span></span> <span data-ttu-id="004ed-198">如果您未設定此設定，就會顯示 [裝置] 頁面。</span><span class="sxs-lookup"><span data-stu-id="004ed-198">If you do not configure this setting,  the Devices page is displayed.</span></span>                                                                                                                     |
| <span data-ttu-id="004ed-199">開機</span><span class="sxs-lookup"><span data-stu-id="004ed-199">Boot</span></span>                               | <span data-ttu-id="004ed-200">顯示 [Surface UEFI**啟動**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="004ed-200">Displays the Surface UEFI **Boot** page.</span></span> <span data-ttu-id="004ed-201">如果您未設定此設定，就會顯示 [引導] 頁面。</span><span class="sxs-lookup"><span data-stu-id="004ed-201">If you do not configure this setting, the Boot page is displayed.</span></span>                                                                                                                                                            |
| <span data-ttu-id="004ed-202">DateTime</span><span class="sxs-lookup"><span data-stu-id="004ed-202">DateTime</span></span>                           | <span data-ttu-id="004ed-203">顯示 [Surface UEFI**日期 DateTime** ] 頁面。</span><span class="sxs-lookup"><span data-stu-id="004ed-203">Displays the Surface UEFI **DateTime** page.</span></span> <span data-ttu-id="004ed-204">如果您未設定此設定，則會顯示 [日期時間] 頁面。</span><span class="sxs-lookup"><span data-stu-id="004ed-204">If you do not configure this setting, the DateTime page is displayed.</span></span>                                                                                                                |



>[!NOTE]
><span data-ttu-id="004ed-205">當您建立 SEMM 設定套件時，[**成功**] 頁面上會顯示兩個字元，如圖3所示。</span><span class="sxs-lookup"><span data-stu-id="004ed-205">When you create a SEMM configuration package, two characters are shown on the **Successful** page, as shown in Figure 3.</span></span>

![憑證指紋顯示](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*<span data-ttu-id="004ed-207">圖 3.</span><span class="sxs-lookup"><span data-stu-id="004ed-207">Figure 3.</span></span> <span data-ttu-id="004ed-208">在成功頁面上顯示證書指紋的最後兩個字元</span><span class="sxs-lookup"><span data-stu-id="004ed-208">Display of the last two characters of the certificate thumbprint on the Successful page</span></span>*

<span data-ttu-id="004ed-209">這些字元是憑證指紋的最後兩個字元，因此應該記下或錄製。</span><span class="sxs-lookup"><span data-stu-id="004ed-209">These characters are the last two characters of the certificate thumbprint and should be written down or recorded.</span></span> <span data-ttu-id="004ed-210">必須有字元來確認在 Surface 裝置上的 SEMM 註冊，如圖4所示。</span><span class="sxs-lookup"><span data-stu-id="004ed-210">The characters are required to confirm enrollment in SEMM on a Surface device, as shown in Figure 4.</span></span>

![SEMM 中的註冊確認](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*<span data-ttu-id="004ed-212">圖 4.</span><span class="sxs-lookup"><span data-stu-id="004ed-212">Figure 4.</span></span> <span data-ttu-id="004ed-213">在 SEMM 中使用 SEMM 憑證指紋進行註冊確認</span><span class="sxs-lookup"><span data-stu-id="004ed-213">Enrollment confirmation in SEMM with the SEMM certificate thumbprint</span></span>*

>[!NOTE]
><span data-ttu-id="004ed-214">擁有憑證檔案（.pfx）存取權的系統管理員可以在 CertMgr 中開啟 .pfx 檔案，隨時讀取指紋。</span><span class="sxs-lookup"><span data-stu-id="004ed-214">Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr.</span></span> <span data-ttu-id="004ed-215">若要使用 CertMgr 查看指紋，請遵循此程式：</span><span class="sxs-lookup"><span data-stu-id="004ed-215">To view the thumbprint with CertMgr, follow this process:</span></span>
>1. <span data-ttu-id="004ed-216">以滑鼠右鍵按一下 .pfx 檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="004ed-216">Right-click the .pfx file, and then click **Open**.</span></span>
>2. <span data-ttu-id="004ed-217">展開 [功能窗格] 中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="004ed-217">Expand the folder in the navigation pane.</span></span>
>3. <span data-ttu-id="004ed-218">按一下 [憑證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="004ed-218">Click **Certificates**.</span></span>
>4. <span data-ttu-id="004ed-219">在主要窗格中，以滑鼠右鍵按一下您的憑證，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="004ed-219">Right-click your certificate in the main pane, and then click **Open**.</span></span>
>5. <span data-ttu-id="004ed-220">按一下 [**詳細資料**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="004ed-220">Click the **Details** tab.</span></span>
>6. <span data-ttu-id="004ed-221">[**全部**] 或 [**僅限屬性**] 必須在 [**顯示**] 下拉式功能表中選取。</span><span class="sxs-lookup"><span data-stu-id="004ed-221">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
>7. <span data-ttu-id="004ed-222">選取欄位**指紋**。</span><span class="sxs-lookup"><span data-stu-id="004ed-222">Select the field **Thumbprint**.</span></span>

<span data-ttu-id="004ed-223">若要在 SEMM 中註冊 Surface 裝置，或從設定套件套用 UEFI 設定，您只需執行該 .msi 檔案，並在預定的 Surface 裝置上使用系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="004ed-223">To enroll a Surface device in SEMM or to apply the UEFI configuration from a configuration package, all you need to do is run the .msi file with administrative privileges on the intended Surface device.</span></span> <span data-ttu-id="004ed-224">您可以使用應用程式部署或作業系統部署技術（例如[Microsoft 端點配置系統管理器](https://technet.microsoft.com/library/mt346023)）或[microsoft 部署工具](https://technet.microsoft.com/windows/dn475741)組。</span><span class="sxs-lookup"><span data-stu-id="004ed-224">You can use application deployment or operating system deployment technologies such as [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) or the [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741).</span></span> <span data-ttu-id="004ed-225">當您在 SEMM 中註冊裝置時，您必須在場，才能確認裝置上的註冊。</span><span class="sxs-lookup"><span data-stu-id="004ed-225">When you enroll a device in SEMM you must be present to confirm the enrollment on the device.</span></span> <span data-ttu-id="004ed-226">當您將設定套用到已在 SEMM 中註冊的裝置時，不需要使用者互動。</span><span class="sxs-lookup"><span data-stu-id="004ed-226">User interaction is not required when you apply a configuration to devices that are already enrolled in SEMM.</span></span>

<span data-ttu-id="004ed-227">如需如何在 SEMM 中註冊 Surface 裝置或使用 SEMM 套用 Surface UEFI 設定的逐步逐步解說，請參閱[使用 SEMM 註冊及設定 surface 裝置](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)。</span><span class="sxs-lookup"><span data-stu-id="004ed-227">For a step-by-step walkthrough of how to enroll a Surface device in SEMM or apply a Surface UEFI configuration with SEMM, see [Enroll and configure Surface devices with SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).</span></span>

### <span data-ttu-id="004ed-228">重設套件</span><span class="sxs-lookup"><span data-stu-id="004ed-228">Reset package</span></span>

<span data-ttu-id="004ed-229">Surface UEFI 重設套件只是用來執行一個工作，以取消從 SEMM 取消對 Surface 裝置的註冊。</span><span class="sxs-lookup"><span data-stu-id="004ed-229">A Surface UEFI reset package is used to perform only one task — to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="004ed-230">重設套件包含從裝置的固件中移除 SEMM 憑證的 [簽署指示]，並將 [UEFI] 設定重設為 [出廠預設值]。</span><span class="sxs-lookup"><span data-stu-id="004ed-230">The reset package contains signed instructions to remove the SEMM certificate from the device’s firmware and to reset UEFI settings to factory default.</span></span> <span data-ttu-id="004ed-231">就像 Surface UEFI 設定套件一樣，必須使用在 Surface 裝置上預配的相同 SEMM 憑證來簽署重設套件。</span><span class="sxs-lookup"><span data-stu-id="004ed-231">Like a Surface UEFI configuration package, a reset package must be signed with the same SEMM certificate that is provisioned on the Surface device.</span></span> <span data-ttu-id="004ed-232">當您建立 SEMM 重設套件時，您必須提供您想要重設之 Surface 裝置的序列值。</span><span class="sxs-lookup"><span data-stu-id="004ed-232">When you create a SEMM reset package, you are required to supply the serial number of the Surface device you intend to reset.</span></span> <span data-ttu-id="004ed-233">SEMM 的 [重設套件] 不是通用的，且專用於一個裝置。</span><span class="sxs-lookup"><span data-stu-id="004ed-233">SEMM reset packages are not universal and are specific to one device.</span></span>

### <span data-ttu-id="004ed-234">復原要求</span><span class="sxs-lookup"><span data-stu-id="004ed-234">Recovery request</span></span>

<span data-ttu-id="004ed-235">在某些情況下，可能無法使用 Surface UEFI 重設套件。</span><span class="sxs-lookup"><span data-stu-id="004ed-235">In some scenarios, it may be impossible to use a Surface UEFI reset package.</span></span> <span data-ttu-id="004ed-236">（例如，如果表面裝置上的 Windows 無法使用）。在這些情況下，您可以從 SEMM 中取消註冊 Surface 裝置，透過 Surface UEFI 的 [**企業管理**] 頁面（如圖5所示）進行復原要求作業。</span><span class="sxs-lookup"><span data-stu-id="004ed-236">(For example, if Windows becomes unusable on the Surface device.) In these scenarios you can unenroll the Surface device from SEMM through the **Enterprise Management** page of Surface UEFI (shown in Figure 5) with a Recovery Request operation.</span></span>

![啟動 SEMM 的恢復要求](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*<span data-ttu-id="004ed-238">圖 5.</span><span class="sxs-lookup"><span data-stu-id="004ed-238">Figure 5.</span></span> <span data-ttu-id="004ed-239">在企業管理頁面上啟動 SEMM 的恢復要求</span><span class="sxs-lookup"><span data-stu-id="004ed-239">Initiate a SEMM recovery request on the Enterprise Management page</span></span>*

<span data-ttu-id="004ed-240">當您在 [**企業管理**] 頁面上使用此程式來重設 Surface 裝置上的 SEMM 時，系統會提供您的 [重設要求]。</span><span class="sxs-lookup"><span data-stu-id="004ed-240">When you use the process on the **Enterprise Management** page to reset SEMM on a Surface device, you are provided with a Reset Request.</span></span> <span data-ttu-id="004ed-241">此重設要求可以儲存為檔案至 USB 磁片磁碟機、複製成文字，或以 QR 程式碼的形式讀取，只要行動裝置就能輕鬆地以電子郵件或 messaged 的方式進行。</span><span class="sxs-lookup"><span data-stu-id="004ed-241">This Reset Request can be saved as a file to a USB drive, copied as text, or read as a QR Code with a mobile device to be easily emailed or messaged.</span></span> <span data-ttu-id="004ed-242">使用 Microsoft Surface UEFI 設定檔重設要求選項載入重設要求檔案，或輸入重設要求文字或 QR 程式碼。</span><span class="sxs-lookup"><span data-stu-id="004ed-242">Use the Microsoft Surface UEFI Configurator Reset Request option to load a Reset Request file or enter the Reset Request text or QR Code.</span></span> <span data-ttu-id="004ed-243">Microsoft Surface UEFI 配置器會產生可在 Surface 裝置上輸入的驗證碼。</span><span class="sxs-lookup"><span data-stu-id="004ed-243">Microsoft Surface UEFI Configurator will generate a verification code that can be entered on the Surface device.</span></span> <span data-ttu-id="004ed-244">如果您在 Surface 裝置上輸入程式碼，然後按一下 [**重新開機**]，裝置將會從 SEMM unenrolled。</span><span class="sxs-lookup"><span data-stu-id="004ed-244">If you enter the code on the Surface device and click **Restart**, the device will be unenrolled from SEMM.</span></span> 

>[!NOTE]
><span data-ttu-id="004ed-245">重設要求在建立之後就會過期兩個小時。</span><span class="sxs-lookup"><span data-stu-id="004ed-245">A Reset Request expires two hours after it is created.</span></span>

<span data-ttu-id="004ed-246">如需如何從 SEMM 取消註冊 Surface 裝置的逐步逐步解說，請參閱[從 SEMM 中取消註冊 surface 裝置](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)。</span><span class="sxs-lookup"><span data-stu-id="004ed-246">For a step-by-step walkthrough of how to unenroll Surface devices from SEMM, see [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).</span></span>

## <span data-ttu-id="004ed-247">Surface Enterprise 管理模式證書需求</span><span class="sxs-lookup"><span data-stu-id="004ed-247">Surface Enterprise Management Mode certificate requirements</span></span>

>[!NOTE]
><span data-ttu-id="004ed-248">需要 SEMM 憑證，才能在已註冊的 Surface 裝置上對 SEMM 或 Surface UEFI 設定執行任何修改。</span><span class="sxs-lookup"><span data-stu-id="004ed-248">The SEMM certificate is required to perform any modification to SEMM or Surface UEFI settings on enrolled Surface devices.</span></span> <span data-ttu-id="004ed-249">如果 SEMM 憑證損毀或遺失，SEMM 就無法移除或重設。</span><span class="sxs-lookup"><span data-stu-id="004ed-249">If the SEMM certificate is corrupted or lost, SEMM cannot be removed or reset.</span></span> <span data-ttu-id="004ed-250">使用適用于備份與恢復的方案，據此管理您的 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="004ed-250">Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery.</span></span>

<span data-ttu-id="004ed-251">使用 Microsoft Surface UEFI 設定檔工具所建立的套件會以憑證簽署。</span><span class="sxs-lookup"><span data-stu-id="004ed-251">Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate.</span></span> <span data-ttu-id="004ed-252">這個憑證可確保在裝置註冊 SEMM 之後，只可使用以核准證書建立的套件來修改 UEFI 的設定。</span><span class="sxs-lookup"><span data-stu-id="004ed-252">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span> <span data-ttu-id="004ed-253">建議針對 SEMM 憑證使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="004ed-253">The following settings are recommended for the SEMM certificate:</span></span>

* <span data-ttu-id="004ed-254">**金鑰演算法**-RSA</span><span class="sxs-lookup"><span data-stu-id="004ed-254">**Key Algorithm** – RSA</span></span> 
* <span data-ttu-id="004ed-255">**金鑰長度**–2048</span><span class="sxs-lookup"><span data-stu-id="004ed-255">**Key Length** – 2048</span></span>
* <span data-ttu-id="004ed-256">**雜湊演算法**– SHA-256</span><span class="sxs-lookup"><span data-stu-id="004ed-256">**Hash Algorithm** – SHA-256</span></span>
* <span data-ttu-id="004ed-257">**類型**-SSL 伺服器驗證</span><span class="sxs-lookup"><span data-stu-id="004ed-257">**Type** – SSL Server Authentication</span></span>
* <span data-ttu-id="004ed-258">**金鑰使用量**-數位簽章、金鑰解碼</span><span class="sxs-lookup"><span data-stu-id="004ed-258">**Key Usage** – Digital signature, Key Encipherment</span></span>
* <span data-ttu-id="004ed-259">**提供者**-Microsoft 增強的 RSA 和 AES 加密提供者</span><span class="sxs-lookup"><span data-stu-id="004ed-259">**Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider</span></span>
* <span data-ttu-id="004ed-260">**到期日**–從證書建立開始的15個月</span><span class="sxs-lookup"><span data-stu-id="004ed-260">**Expiration Date** – 15 Months from certificate creation</span></span>
* <span data-ttu-id="004ed-261">**金鑰匯出原則**–可匯出的</span><span class="sxs-lookup"><span data-stu-id="004ed-261">**Key Export Policy** – Exportable</span></span>

<span data-ttu-id="004ed-262">我們也建議在中間憑證授權單位（CA）專用於 SEMM 的雙層公開金鑰基礎結構（PKI）架構中驗證 SEMM 憑證，以啟用憑證吊銷。</span><span class="sxs-lookup"><span data-stu-id="004ed-262">It is also recommended that the SEMM certificate be authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation.</span></span> <span data-ttu-id="004ed-263">如需雙層 PKI 設定的詳細資訊，請參閱[測試實驗室指南：部署 AD CS 雙層 Pki 層次結構](https://technet.microsoft.com/library/hh831348)。</span><span class="sxs-lookup"><span data-stu-id="004ed-263">For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).</span></span>

>[!NOTE]
><span data-ttu-id="004ed-264">您可以使用下列 PowerShell 腳本來建立可在概念驗證案例中使用的自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="004ed-264">You can use the following PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.</span></span>
 > <span data-ttu-id="004ed-265">若要使用此腳本，請將下列文字複製到記事本，並將檔案另存為 PowerShell 腳本（ps1）。</span><span class="sxs-lookup"><span data-stu-id="004ed-265">To use this script, copy the following text into Notepad and save the file as a PowerShell script (.ps1).</span></span> <span data-ttu-id="004ed-266">此腳本會建立密碼為的憑證 `12345678` 。</span><span class="sxs-lookup"><span data-stu-id="004ed-266">This script creates a certificate with a password of `12345678`.</span></span><br/><br/><span data-ttu-id="004ed-267">建議您不要在生產環境中使用此腳本產生的憑證。</span><span class="sxs-lookup"><span data-stu-id="004ed-267">The certificate generated by this script is not recommended for production environments.</span></span>
  
   ```
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
   ```

<span data-ttu-id="004ed-268">若要與 SEMM 和 Microsoft Surface UEFI 配置器搭配使用，必須使用私密金鑰及密碼保護來匯出憑證。</span><span class="sxs-lookup"><span data-stu-id="004ed-268">For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection.</span></span> <span data-ttu-id="004ed-269">Microsoft Surface UEFI 設定檔將會在需要時提示您選取 SEMM 憑證檔案（.pfx）及證書密碼。</span><span class="sxs-lookup"><span data-stu-id="004ed-269">Microsoft Surface UEFI Configurator will prompt you to select the SEMM certificate file (.pfx) and certificate password when it is required.</span></span>

>[!NOTE]
><span data-ttu-id="004ed-270">對於在其 PKI 基礎結構中使用離線根目錄的組織，Microsoft Surface UEFI 配置必須在連線至根 CA 的環境中執行，以驗證 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="004ed-270">For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate.</span></span> <span data-ttu-id="004ed-271">由 Microsoft Surface UEFI 設定檔產生的套件可以轉移成檔案，因此可以使用 [可移動儲存空間] （例如 USB 杆），在離線網路環境外傳輸。</span><span class="sxs-lookup"><span data-stu-id="004ed-271">The packages generated by Microsoft Surface UEFI Configurator can be transferred as files and therefore can be transferred outside the offline network environment with removable storage, such as a USB stick.</span></span>

### <span data-ttu-id="004ed-272">管理證書常見問題</span><span class="sxs-lookup"><span data-stu-id="004ed-272">Managing certificates FAQ</span></span>

<span data-ttu-id="004ed-273">建議的*最小*長度為15個月。</span><span class="sxs-lookup"><span data-stu-id="004ed-273">The recommended *minimum* length is 15 months.</span></span> <span data-ttu-id="004ed-274">您可以使用到期日不超過15個月的憑證，或使用超過15個月的憑證。</span><span class="sxs-lookup"><span data-stu-id="004ed-274">You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.</span></span>

>[!NOTE] 
><span data-ttu-id="004ed-275">憑證到期後，就不會自動續約。</span><span class="sxs-lookup"><span data-stu-id="004ed-275">When a certificate expires, it does not automatically renew.</span></span> 

**<span data-ttu-id="004ed-276">在15個月之後，現有的電腦會繼續套用 bios 設定嗎？</span><span class="sxs-lookup"><span data-stu-id="004ed-276">Will existing machines continue to apply the bios settings after 15 months?</span></span>**

<span data-ttu-id="004ed-277">是，但僅在證書有效時才簽署套件本身。</span><span class="sxs-lookup"><span data-stu-id="004ed-277">Yes, but only if the package itself was signed when the certificate was valid.</span></span>

<span data-ttu-id="004ed-278">**Will** **SEMM 套件和憑證是否需要在擁有它的所有電腦上更新？**</span><span class="sxs-lookup"><span data-stu-id="004ed-278">**Will** **the SEMM package and certificate need to be updated on all machines that have it?**</span></span>

<span data-ttu-id="004ed-279">如果您想要 SEMM 重設或還原作業正常運作，憑證必須有效且未過期。</span><span class="sxs-lookup"><span data-stu-id="004ed-279">If you want SEMM reset or recovery to work, the certificate needs to be valid and not expired.</span></span> 

**<span data-ttu-id="004ed-280">針對我們所訂購的每個 surface，會建立大容量重設套件嗎？</span><span class="sxs-lookup"><span data-stu-id="004ed-280">Can bulk reset packages be created for each surface that we order?</span></span> <span data-ttu-id="004ed-281">在我們的環境中，您可以使用其中一個程式來重設所有電腦嗎？</span><span class="sxs-lookup"><span data-stu-id="004ed-281">Can one be built that resets all machines in our environment?</span></span>**

<span data-ttu-id="004ed-282">針對特定裝置類型建立配置套件的 PowerShell 範例也可以用來建立獨立于序號碼的重設套件。</span><span class="sxs-lookup"><span data-stu-id="004ed-282">The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that is serial-number independent.</span></span> <span data-ttu-id="004ed-283">如果憑證仍然有效，您可以使用 PowerShell 建立重設套件來重設 SEMM。</span><span class="sxs-lookup"><span data-stu-id="004ed-283">If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.</span></span>

## <span data-ttu-id="004ed-284">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="004ed-284">Version History</span></span>

### <span data-ttu-id="004ed-285">版本2.71.139。0</span><span class="sxs-lookup"><span data-stu-id="004ed-285">Version 2.71.139.0</span></span>

<span data-ttu-id="004ed-286">此版本的 SEMM 會針對 Surface mobile 3、Surface 膝上型3和 Surface Pro 7 新增對 Surface Dock 2 管理功能的支援，包括：</span><span class="sxs-lookup"><span data-stu-id="004ed-286">This version of SEMM adds support for Surface Dock 2 management features  for Surface Book 3, Surface Laptop 3, and Surface Pro 7 including:</span></span>

- <span data-ttu-id="004ed-287">啟用音訊（鎖定/解鎖）、乙太網路和 USB 埠</span><span class="sxs-lookup"><span data-stu-id="004ed-287">Enabling audio (locking/unlocking), Ethernet and USB ports</span></span>
- <span data-ttu-id="004ed-288">能夠為已驗證及未驗證的主機建立 dock 套件</span><span class="sxs-lookup"><span data-stu-id="004ed-288">Ability to create dock packages for both authenticated and unauthenticated hosts</span></span>

### <span data-ttu-id="004ed-289">版本2.70.130。0</span><span class="sxs-lookup"><span data-stu-id="004ed-289">Version 2.70.130.0</span></span>

<span data-ttu-id="004ed-290">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="004ed-290">This version of SEMM includes:</span></span>

- <span data-ttu-id="004ed-291">表面 [移至 2] 支援</span><span class="sxs-lookup"><span data-stu-id="004ed-291">Support for Surface Go 2</span></span>
- <span data-ttu-id="004ed-292">Surface Book 3 的支援</span><span class="sxs-lookup"><span data-stu-id="004ed-292">Support for Surface Book 3</span></span>
- <span data-ttu-id="004ed-293">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="004ed-293">Bug fixes</span></span>


### <span data-ttu-id="004ed-294">版本2.59.139。0</span><span class="sxs-lookup"><span data-stu-id="004ed-294">Version 2.59.139.0</span></span>

* <span data-ttu-id="004ed-295">支援 Surface Pro 7、Surface Pro X，以及含英特爾處理器的 Surface 膝上型 3 13.5 "和 15" 模型。</span><span class="sxs-lookup"><span data-stu-id="004ed-295">Support for Surface Pro 7, Surface Pro X,  and Surface Laptop 3 13.5" and 15" models with Intel processor.</span></span> <span data-ttu-id="004ed-296">注意： Surface 膝上型電腦 3 15 "不支援 AMD 處理器。</span><span class="sxs-lookup"><span data-stu-id="004ed-296">Note:  Surface Laptop 3 15" AMD processor is not supported.</span></span>

- <span data-ttu-id="004ed-297">支援喚醒功能</span><span class="sxs-lookup"><span data-stu-id="004ed-297">Support for Wake on Power feature</span></span>

### <span data-ttu-id="004ed-298">版本2.54.139。0</span><span class="sxs-lookup"><span data-stu-id="004ed-298">Version 2.54.139.0</span></span>
* <span data-ttu-id="004ed-299">支援至 Surface Hub 的2秒</span><span class="sxs-lookup"><span data-stu-id="004ed-299">Support to Surface Hub 2S</span></span>
* <span data-ttu-id="004ed-300">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="004ed-300">Bug fixes</span></span>

### <span data-ttu-id="004ed-301">版本2.43.136。0</span><span class="sxs-lookup"><span data-stu-id="004ed-301">Version 2.43.136.0</span></span>
* <span data-ttu-id="004ed-302">支援以啟用/停用 simulatenous multithreating</span><span class="sxs-lookup"><span data-stu-id="004ed-302">Support to enable/disable simulatenous multithreating</span></span> 
* <span data-ttu-id="004ed-303">針對某些裝置，分別提供 WiFi 與藍牙選項</span><span class="sxs-lookup"><span data-stu-id="004ed-303">Separate options for WiFi and Bluetooth for some devices</span></span> 
* <span data-ttu-id="004ed-304">已移除 Surface Studio 的電池限制</span><span class="sxs-lookup"><span data-stu-id="004ed-304">Battery Limit removed for Surface Studio</span></span> 

### <span data-ttu-id="004ed-305">版本2.26.136。0</span><span class="sxs-lookup"><span data-stu-id="004ed-305">Version 2.26.136.0</span></span>
* <span data-ttu-id="004ed-306">在 Surface Studio 2 中新增支援</span><span class="sxs-lookup"><span data-stu-id="004ed-306">Add support to Surface Studio 2</span></span>
* <span data-ttu-id="004ed-307">電池限制功能</span><span class="sxs-lookup"><span data-stu-id="004ed-307">Battery Limit feature</span></span>

### <span data-ttu-id="004ed-308">版本2.21.136。0</span><span class="sxs-lookup"><span data-stu-id="004ed-308">Version 2.21.136.0</span></span>
* <span data-ttu-id="004ed-309">新增支援至 Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="004ed-309">Add support to Surface Pro 6</span></span>
* <span data-ttu-id="004ed-310">新增支援至 Surface 膝上型電腦2</span><span class="sxs-lookup"><span data-stu-id="004ed-310">Add support to Surface Laptop 2</span></span>

### <span data-ttu-id="004ed-311">版本2.14.136。0</span><span class="sxs-lookup"><span data-stu-id="004ed-311">Version 2.14.136.0</span></span>
* <span data-ttu-id="004ed-312">將支援新增至表面</span><span class="sxs-lookup"><span data-stu-id="004ed-312">Add support to Surface Go</span></span>

### <span data-ttu-id="004ed-313">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="004ed-313">Version 2.9.136.0</span></span>
* <span data-ttu-id="004ed-314">新增支援至 Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="004ed-314">Add support to Surface Book 2</span></span>
* <span data-ttu-id="004ed-315">新增支援至 Surface Pro LTE</span><span class="sxs-lookup"><span data-stu-id="004ed-315">Add support to Surface Pro LTE</span></span>
* <span data-ttu-id="004ed-316">協助工具增強功能</span><span class="sxs-lookup"><span data-stu-id="004ed-316">Accessibility improvements</span></span>

### <span data-ttu-id="004ed-317">版本1.0.74。0</span><span class="sxs-lookup"><span data-stu-id="004ed-317">Version 1.0.74.0</span></span>
* <span data-ttu-id="004ed-318">新增支援至 Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="004ed-318">Add support to Surface Laptop</span></span>
* <span data-ttu-id="004ed-319">將支援新增至 Surface Pro</span><span class="sxs-lookup"><span data-stu-id="004ed-319">Add support to Surface Pro</span></span>
* <span data-ttu-id="004ed-320">錯誤修正及一般改進</span><span class="sxs-lookup"><span data-stu-id="004ed-320">Bug fixes and general improvement</span></span>

## <span data-ttu-id="004ed-321">相關主題</span><span class="sxs-lookup"><span data-stu-id="004ed-321">Related topics</span></span>

- [<span data-ttu-id="004ed-322">使用 SEMM 註冊及設定 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="004ed-322">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)
- [<span data-ttu-id="004ed-323">從 SEMM 取消 Surface 裝置的註冊</span><span class="sxs-lookup"><span data-stu-id="004ed-323">Unenroll Surface devices from SEMM</span></span>](unenroll-surface-devices-from-semm.md)
- [<span data-ttu-id="004ed-324">使用 SEMM 的安全 Surface Dock 2 埠</span><span class="sxs-lookup"><span data-stu-id="004ed-324">Secure Surface Dock 2 ports with SEMM</span></span>](secure-surface-dock-ports-semm.md)
