---
title: 'Surface Enterprise management mode (Surface) '
description: 瞭解 Surface 裝置與 Surface UEFI 的這項功能如何協助保護及管理貴組織的固件設定。
keywords: uefi， configure， firmware， secure， semm
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
ms.date: 03/18/2021
ms.openlocfilehash: 011f4d0270c47b976e10dbece2adb70559222b79
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442181"
---
# <a name="microsoft-surface-enterprise-management-mode"></a><span data-ttu-id="c6205-104">Microsoft Surface 企業管理模式</span><span class="sxs-lookup"><span data-stu-id="c6205-104">Microsoft Surface Enterprise Management Mode</span></span>

<span data-ttu-id="c6205-105">Microsoft Surface 企業管理模式 (SEMM) 是 Surface UEFI 的 Surface 裝置功能，可讓您保護和管理貴組織的固件設定。</span><span class="sxs-lookup"><span data-stu-id="c6205-105">Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface UEFI that allows you to secure and manage firmware settings within your organization.</span></span> <span data-ttu-id="c6205-106">使用 SEMM，IT 專業人員可以準備 UEFI 設定設定，並安裝在 Surface 裝置上。</span><span class="sxs-lookup"><span data-stu-id="c6205-106">With SEMM, IT professionals can prepare configurations of UEFI settings and install them on a Surface device.</span></span> <span data-ttu-id="c6205-107">除了能夠設定 UEFI 設定之外，SEMM 也會使用憑證來保護設定，避免未經授權的竄改或移除。</span><span class="sxs-lookup"><span data-stu-id="c6205-107">In addition to the ability to configure UEFI settings, SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal.</span></span> <span data-ttu-id="c6205-108">SEMM 是能夠將 Surface Hub 2S 遷移到 Windows 10 專業版和企業版的需求。</span><span class="sxs-lookup"><span data-stu-id="c6205-108">SEMM is a requirement to be able to migrate a Surface Hub 2S to Windows 10 Pro and Enterprise.</span></span>

>[!NOTE]
><span data-ttu-id="c6205-109">SEMM 僅適用于具有 Surface UEFI 固件的裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-109">SEMM is only available on devices with Surface UEFI firmware.</span></span> <span data-ttu-id="c6205-110">這包括大多數 Surface 裝置，包括 Surface Pro 7+、Surface Pro 7、Surface Pro X、Surface Hub 2S、Surface Laptop 3 具有 Intel 處理器的商業 SUS，以及 Surface Laptop Go。</span><span class="sxs-lookup"><span data-stu-id="c6205-110">This includes most Surface devices including Surface Pro 7+, Surface Pro 7, Surface Pro X, Surface Hub 2S, Surface Laptop 3 commercial SKUs with an Intel processor, and Surface Laptop Go.</span></span> <span data-ttu-id="c6205-111">具有AMD 處理器的 15" Surface Laptop 3 SKU 不支援 SEMM (僅提供零售 SKU) 。</span><span class="sxs-lookup"><span data-stu-id="c6205-111">SEMM is not supported on the 15" Surface Laptop 3 SKU with AMD processor (only available as a retail SKU).</span></span> 

<span data-ttu-id="c6205-112">當 Surface 裝置是由 SEMM 所配置，且使用 SEMM 憑證進行保護\*\* 時，即視為已註冊于 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c6205-112">When Surface devices are configured by SEMM and secured with the SEMM certificate, they are considered *enrolled* in SEMM.</span></span> <span data-ttu-id="c6205-113">移除 SEMM 憑證，且將 UEFI 設定控制權退還給裝置使用者時，Surface 裝置在 SEMM 中視為未註冊。 \*\*</span><span class="sxs-lookup"><span data-stu-id="c6205-113">When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.</span></span>

<span data-ttu-id="c6205-114">您可以使用兩種系統管理選項來管理 SEMM 並註冊 Surface 裝置 ：獨立工具或與 Microsoft 端點 Configuration Manager 整合。</span><span class="sxs-lookup"><span data-stu-id="c6205-114">There are two administrative options you can use to manage SEMM and enroll Surface devices – a standalone tool or integration with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="c6205-115">本文說明 SEMM 獨立工具 ，稱為 Microsoft Surface UEFI Configurator。</span><span class="sxs-lookup"><span data-stu-id="c6205-115">The SEMM standalone tool, called the Microsoft Surface UEFI Configurator, is described in this article.</span></span> <span data-ttu-id="c6205-116">若要瞭解如何使用 Microsoft 端點群組原則管理員管理 SEMM，請參閱使用 Microsoft 端點組組管理員使用 [SEMM 管理裝置](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)。</span><span class="sxs-lookup"><span data-stu-id="c6205-116">For more information about how to manage SEMM with Microsoft Endpoint Configuration Manager, see [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).</span></span>

> [!NOTE]
> <span data-ttu-id="c6205-117">Surface Pro X 僅透過 UEFI Manager 支援 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c6205-117">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="c6205-118">您可以從 IT 的 Surface Tools 下載 UEFI [Manager。](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="c6205-118">You can download UEFI Manager from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="c6205-119">詳細資訊，請參閱[部署、管理及維護 Surface Pro X。](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="c6205-119">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>


## <a name="microsoft-surface-uefi-configurator"></a><span data-ttu-id="c6205-120">Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="c6205-120">Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="c6205-121">SEMM 的主要工作區是 Microsoft Surface UEFI Configurator，如圖 1 所示。</span><span class="sxs-lookup"><span data-stu-id="c6205-121">The primary workspace of SEMM is Microsoft Surface UEFI Configurator, as shown in Figure 1.</span></span> <span data-ttu-id="c6205-122">Microsoft Surface UEFI 設定器是用來建立 Windows Installer (.msi) 套件或 WinPE 影像的工具，用來在 Surface 裝置上註冊、設定及取消註冊 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c6205-122">Microsoft Surface UEFI Configurator is a tool used to create Windows Installer (.msi) packages or WinPE images used to enroll, configure, and unenroll SEMM on a Surface device.</span></span> <span data-ttu-id="c6205-123">這些套件包含設定檔案，其中指定 UEFI 的設定。</span><span class="sxs-lookup"><span data-stu-id="c6205-123">These packages contain a configuration file where the settings for UEFI are specified.</span></span> <span data-ttu-id="c6205-124">SEMM 套件也包含憑證，該憑證會安裝並儲存在固件中，用來在套用 UEFI 設定之前驗證組組檔案的簽名。</span><span class="sxs-lookup"><span data-stu-id="c6205-124">SEMM packages also contain a certificate, which is installed and stored in firmware and used to verify the signature of configuration files before UEFI settings are applied.</span></span>

>[!TIP]
><span data-ttu-id="c6205-125">現在，您可以使用 Surface UEFI Configurator 和 SEMM 來管理 Surface Dock 2 上的埠。</span><span class="sxs-lookup"><span data-stu-id="c6205-125">You can now use Surface UEFI Configurator and SEMM to manage ports on Surface Dock 2.</span></span> <span data-ttu-id="c6205-126">若要深入瞭解，請參閱使用 SEMM 保護 [Surface Dock 2 埠](secure-surface-dock-ports-semm.md)。</span><span class="sxs-lookup"><span data-stu-id="c6205-126">To learn more, see [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).</span></span>

![Microsoft Surface UEFI Configurator](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*<span data-ttu-id="c6205-128">圖 1。</span><span class="sxs-lookup"><span data-stu-id="c6205-128">Figure 1.</span></span> <span data-ttu-id="c6205-129">Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="c6205-129">Microsoft Surface UEFI Configurator</span></span>*


<span data-ttu-id="c6205-130">您可以在三種模式中使用 Microsoft Surface UEFI Configurator 工具：</span><span class="sxs-lookup"><span data-stu-id="c6205-130">You can use the Microsoft Surface UEFI Configurator tool in three modes:</span></span>

* <span data-ttu-id="c6205-131">[Surface UEFI 組組套件](#configuration-package)。</span><span class="sxs-lookup"><span data-stu-id="c6205-131">[Surface UEFI Configuration Package](#configuration-package).</span></span> <span data-ttu-id="c6205-132">使用此模式可建立 Surface UEFI 設定套件，以在 SEMM 中註冊 Surface 裝置，以及設定已註冊的裝置上的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="c6205-132">Use this mode to create a Surface UEFI configuration package to enroll a Surface device in SEMM and to configure UEFI settings on enrolled devices.</span></span>
* <span data-ttu-id="c6205-133">[Surface UEFI 重設套件](#reset-package)。</span><span class="sxs-lookup"><span data-stu-id="c6205-133">[Surface UEFI Reset Package](#reset-package).</span></span> <span data-ttu-id="c6205-134">使用此模式從 SEMM 取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-134">Use this mode to unenroll a Surface device from SEMM.</span></span>
* <span data-ttu-id="c6205-135">[Surface UEFI 修復要求](#recovery-request)。</span><span class="sxs-lookup"><span data-stu-id="c6205-135">[Surface UEFI Recovery Request](#recovery-request).</span></span> <span data-ttu-id="c6205-136">使用此模式回應復原要求，從 SEMM 取消註冊 Surface 裝置，而重設套件作業失敗。</span><span class="sxs-lookup"><span data-stu-id="c6205-136">Use this mode to respond to a recovery request to unenroll a Surface device from SEMM where a Reset Package operation is not successful.</span></span>


#### <a name="download-microsoft-surface-uefi-configurator"></a><span data-ttu-id="c6205-137">下載 Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="c6205-137">Download Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="c6205-138">您可以在 Microsoft 下載中心的 IT 版 Surface [工具](https://www.microsoft.com/download/details.aspx?id=46703) 頁面下載 Microsoft Surface UEFI 配置程式。</span><span class="sxs-lookup"><span data-stu-id="c6205-138">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

### <a name="configuration-package"></a><span data-ttu-id="c6205-139">組組套件</span><span class="sxs-lookup"><span data-stu-id="c6205-139">Configuration package</span></span>

<span data-ttu-id="c6205-140">Surface UEFI 組組套件是在 Surface 裝置上執行和管理 SEMM 的主要機制。</span><span class="sxs-lookup"><span data-stu-id="c6205-140">Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices.</span></span> <span data-ttu-id="c6205-141">這些套件包含在 Microsoft Surface UEFI 設定器中建立套件時指定的 UEFI 設定設定檔和憑證檔案，如圖 2 所示。</span><span class="sxs-lookup"><span data-stu-id="c6205-141">These packages contain a configuration file of UEFI settings specified during creation of the package in Microsoft Surface UEFI Configurator and a certificate file, as shown in Figure 2.</span></span> <span data-ttu-id="c6205-142">當第一次在尚未在 SEMM 註冊的 Surface 裝置上執行組組套件時，它會在裝置的固件中規定憑證檔案，並註冊 SEMM 中的裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-142">When a configuration package is run for the first time on a Surface device that is not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM.</span></span> <span data-ttu-id="c6205-143">在 SEMM 中註冊裝置時，系統會提示您確認作業，在儲存憑證檔案並完成註冊之前，先提供 SEMM 憑證指紋的最後兩位數。</span><span class="sxs-lookup"><span data-stu-id="c6205-143">When enrolling a device in SEMM, you will be prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint before the certificate file is stored and the enrollment can complete.</span></span> <span data-ttu-id="c6205-144">此確認要求使用者在註冊時實際存在於裝置上，才能執行確認。</span><span class="sxs-lookup"><span data-stu-id="c6205-144">This confirmation requires a user be physically present at the device at the time of enrollment to perform the confirmation.</span></span>

![使用憑證保護 SEMM 組組套件](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*<span data-ttu-id="c6205-146">圖 2.</span><span class="sxs-lookup"><span data-stu-id="c6205-146">Figure 2.</span></span> <span data-ttu-id="c6205-147">使用憑證保護 SEMM 組組套件</span><span class="sxs-lookup"><span data-stu-id="c6205-147">Secure a SEMM configuration package with a certificate</span></span>*

<span data-ttu-id="c6205-148">請參閱 [本文的 Surface Enterprise Management Mode 證書](#surface-enterprise-management-mode-certificate-requirements) 需求一節，以進一瞭解 SEMM 憑證的需求。</span><span class="sxs-lookup"><span data-stu-id="c6205-148">See the [Surface Enterprise Management Mode certificate requirements](#surface-enterprise-management-mode-certificate-requirements) section of this article for more information about the requirements for the SEMM certificate.</span></span>

>[!TIP]
><span data-ttu-id="c6205-149">您也可以使用 SEMM 指定 UEFI 密碼，以查看 Surface \*\* **UEFI\*\*\*\* 的安全性、**裝置\*\*、\*\*\*\* 開機組組或企業管理頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-149">You can also specify a UEFI password with SEMM that is required to view the **Security**, **Devices**, **Boot Configuration**, or **Enterprise Management** pages of Surface UEFI.</span></span>

<span data-ttu-id="c6205-150">在 SEMM 中註冊裝置之後，系統即會讀取設定檔，且檔案中指定的設定會適用于 UEFI。</span><span class="sxs-lookup"><span data-stu-id="c6205-150">After a device is enrolled in SEMM, the configuration file is read and the settings specified in the file are applied to UEFI.</span></span> <span data-ttu-id="c6205-151">當您在已在 SEMM 註冊的裝置上執行組組套件時，設定檔的簽名會針對儲存在裝置固件中的憑證進行檢查。</span><span class="sxs-lookup"><span data-stu-id="c6205-151">When you run a configuration package on a device that is already enrolled in SEMM, the signature of the configuration file is checked against the certificate that is stored in the device firmware.</span></span> <span data-ttu-id="c6205-152">如果簽章不相符，將不會將任何變更適用于裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-152">If the signature does not match, no changes are applied to the device.</span></span>

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a><span data-ttu-id="c6205-153">在 Surface UEFI 中啟用或停用具有 SEMM 的裝置</span><span class="sxs-lookup"><span data-stu-id="c6205-153">Enable or disable devices in Surface UEFI with SEMM</span></span>

<span data-ttu-id="c6205-154">下列清單顯示您可以在 SEMM 中管理的所有可用裝置：</span><span class="sxs-lookup"><span data-stu-id="c6205-154">The following list shows all the available devices you can manage in SEMM:</span></span>

* <span data-ttu-id="c6205-155">固定 USB 埠</span><span class="sxs-lookup"><span data-stu-id="c6205-155">Docking USB Port</span></span>
* <span data-ttu-id="c6205-156">板載音訊</span><span class="sxs-lookup"><span data-stu-id="c6205-156">On-board Audio</span></span>
* <span data-ttu-id="c6205-157">DGPU</span><span class="sxs-lookup"><span data-stu-id="c6205-157">DGPU</span></span>
* <span data-ttu-id="c6205-158">實體鍵盤保護蓋</span><span class="sxs-lookup"><span data-stu-id="c6205-158">Type Cover</span></span>
* <span data-ttu-id="c6205-159">Micro SD Card</span><span class="sxs-lookup"><span data-stu-id="c6205-159">Micro SD Card</span></span>
* <span data-ttu-id="c6205-160">前方攝影機</span><span class="sxs-lookup"><span data-stu-id="c6205-160">Front Camera</span></span>
* <span data-ttu-id="c6205-161">後方攝影機</span><span class="sxs-lookup"><span data-stu-id="c6205-161">Rear Camera</span></span>
* <span data-ttu-id="c6205-162">適用于 Windows Hello 的紅外線相機</span><span class="sxs-lookup"><span data-stu-id="c6205-162">Infrared Camera, for Windows Hello</span></span>
* <span data-ttu-id="c6205-163">僅藍牙</span><span class="sxs-lookup"><span data-stu-id="c6205-163">Bluetooth Only</span></span>
* <span data-ttu-id="c6205-164">Wi-Fi 和藍牙</span><span class="sxs-lookup"><span data-stu-id="c6205-164">Wi-Fi and Bluetooth</span></span>
* <span data-ttu-id="c6205-165">             LTE           </span><span class="sxs-lookup"><span data-stu-id="c6205-165">LTE</span></span>

 >[!NOTE]
><span data-ttu-id="c6205-166">顯示在 UEFI 裝置頁面中的內建裝置可能會根據您的裝置或公司環境而有所差異。</span><span class="sxs-lookup"><span data-stu-id="c6205-166">The built-in devices that appear in the UEFI Devices page may vary depending on your device or corporate environment.</span></span> <span data-ttu-id="c6205-167">例如，Surface Pro X 不支援 UEFI 裝置頁面;LTE 只會出現在配備 LTE 的裝置上。</span><span class="sxs-lookup"><span data-stu-id="c6205-167">For example, the UEFI Devices page is not supported on Surface Pro X; LTE only appears on LTE-equipped devices.</span></span> 
### <a name="configure-advanced-settings-with-semm"></a><span data-ttu-id="c6205-168">使用 SEMM 設定進位設定</span><span class="sxs-lookup"><span data-stu-id="c6205-168">Configure advanced settings with SEMM</span></span>
**<span data-ttu-id="c6205-169">表 1.</span><span class="sxs-lookup"><span data-stu-id="c6205-169">Table 1.</span></span> <span data-ttu-id="c6205-170">進階設定</span><span class="sxs-lookup"><span data-stu-id="c6205-170">Advanced settings</span></span>**

| <span data-ttu-id="c6205-171">設定</span><span class="sxs-lookup"><span data-stu-id="c6205-171">Setting</span></span>                            | <span data-ttu-id="c6205-172">說明</span><span class="sxs-lookup"><span data-stu-id="c6205-172">Description</span></span>                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c6205-173">適用於 PXE 開機 的 IPv6</span><span class="sxs-lookup"><span data-stu-id="c6205-173">IPv6 for PXE Boot</span></span>                  | <span data-ttu-id="c6205-174">可讓您管理 PXE 啟動的 IPv6 支援。</span><span class="sxs-lookup"><span data-stu-id="c6205-174">Allows you to manage IPv6 support for PXE boot.</span></span> <span data-ttu-id="c6205-175">如果您沒有設定此設定，則 PXE 啟動的 IPv6 支援會停用。</span><span class="sxs-lookup"><span data-stu-id="c6205-175">If you do not configure this setting, IPv6 support for PXE boot is disabled.</span></span>                                                                               |
| <span data-ttu-id="c6205-176">替代開機</span><span class="sxs-lookup"><span data-stu-id="c6205-176">Alternate Boot</span></span>                     | <span data-ttu-id="c6205-177">可讓您在啟動期間同步選取降低音量按鈕和 Power 按鈕，管理使用替代啟動順序以直接引導至 USB 或乙太網路裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-177">Allows you to manage use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot.</span></span> <span data-ttu-id="c6205-178">如果您沒有設定此設定，系統即會啟用備用啟動。</span><span class="sxs-lookup"><span data-stu-id="c6205-178">If you do not configure this setting, Alternate boot is enabled.</span></span> |
| <span data-ttu-id="c6205-179">開機順序鎖定</span><span class="sxs-lookup"><span data-stu-id="c6205-179">Boot Order Lock</span></span>                    | <span data-ttu-id="c6205-180">可讓您鎖定啟動順序，以防止變更。</span><span class="sxs-lookup"><span data-stu-id="c6205-180">Allows you to lock the boot order to prevent changes.</span></span> <span data-ttu-id="c6205-181">如果您沒有設定此設定，即會停用啟動順序鎖定。</span><span class="sxs-lookup"><span data-stu-id="c6205-181">If you do not configure this setting, Boot Order Lock is disabled.</span></span>                                                                                                        |
| <span data-ttu-id="c6205-182">USB 開機</span><span class="sxs-lookup"><span data-stu-id="c6205-182">USB Boot</span></span>                           | <span data-ttu-id="c6205-183">可讓您管理啟動至 USB 裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-183">Allows you to manage booting to USB devices.</span></span> <span data-ttu-id="c6205-184">如果您沒有設定此設定，則 USB 啟動已啟用。</span><span class="sxs-lookup"><span data-stu-id="c6205-184">If you do not configure this setting, USB Boot is enabled.</span></span>                                                                                                                 |
| <span data-ttu-id="c6205-185">網路堆疊</span><span class="sxs-lookup"><span data-stu-id="c6205-185">Network Stack</span></span>                      | <span data-ttu-id="c6205-186">可讓您管理網路堆疊啟動設定。</span><span class="sxs-lookup"><span data-stu-id="c6205-186">Allows you to manage Network Stack boot settings.</span></span> <span data-ttu-id="c6205-187">如果您沒有設定此設定，則管理網路堆疊啟動設定的能力會停用。</span><span class="sxs-lookup"><span data-stu-id="c6205-187">If you do not configure this setting,  the ability to manage Network Stack boot settings is disabled.</span></span>                                                                                                           |
| <span data-ttu-id="c6205-188">自動上電</span><span class="sxs-lookup"><span data-stu-id="c6205-188">Auto Power On</span></span>                      | <span data-ttu-id="c6205-189">可讓您管理自動開機設定。</span><span class="sxs-lookup"><span data-stu-id="c6205-189">Allows you to manage Auto Power On boot settings.</span></span> <span data-ttu-id="c6205-190">如果您沒有設定此設定，即會啟用自動電源。</span><span class="sxs-lookup"><span data-stu-id="c6205-190">If you do not configure this setting, Auto Power on is enabled.</span></span>                                                                                                        |
| <span data-ttu-id="c6205-191">同時使用 SMT (執行緒) </span><span class="sxs-lookup"><span data-stu-id="c6205-191">Simultaneous Multi-Threading (SMT)</span></span> | <span data-ttu-id="c6205-192">可讓您管理 SMT 的同步多執行緒 (，) 啟用或停用超執行緒。</span><span class="sxs-lookup"><span data-stu-id="c6205-192">Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading.</span></span> <span data-ttu-id="c6205-193">如果您沒有設定此設定，SMT 會啟用。</span><span class="sxs-lookup"><span data-stu-id="c6205-193">If you do not configure this setting, SMT is enabled.</span></span>                                                  |
|<span data-ttu-id="c6205-194">啟用電池限制</span><span class="sxs-lookup"><span data-stu-id="c6205-194">Enable Battery limit</span></span>| <span data-ttu-id="c6205-195">可讓您管理電池限制功能。</span><span class="sxs-lookup"><span data-stu-id="c6205-195">Allows you to manage Battery limit functionality.</span></span> <span data-ttu-id="c6205-196">如果您沒有設定此設定，則啟用電池限制</span><span class="sxs-lookup"><span data-stu-id="c6205-196">If you do not configure this setting, Battery limit is enabled</span></span> |
| <span data-ttu-id="c6205-197">安全性</span><span class="sxs-lookup"><span data-stu-id="c6205-197">Security</span></span>                           | <span data-ttu-id="c6205-198">顯示 Surface UEFI **安全性** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-198">Displays the Surface UEFI **Security** page.</span></span> <span data-ttu-id="c6205-199">如果您沒有設定此設定，系統會顯示安全性頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-199">If you do not configure this setting, the Security page is displayed.</span></span>                                                                                                                 |
| <span data-ttu-id="c6205-200">裝置</span><span class="sxs-lookup"><span data-stu-id="c6205-200">Devices</span></span>                            | <span data-ttu-id="c6205-201">顯示 Surface UEFI **裝置** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-201">Displays the Surface UEFI **Devices** page.</span></span> <span data-ttu-id="c6205-202">如果您沒有設定此設定，會顯示裝置頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-202">If you do not configure this setting,  the Devices page is displayed.</span></span>                                                                                                                     |
| <span data-ttu-id="c6205-203">開機</span><span class="sxs-lookup"><span data-stu-id="c6205-203">Boot</span></span>                               | <span data-ttu-id="c6205-204">顯示 Surface UEFI **啟動** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-204">Displays the Surface UEFI **Boot** page.</span></span> <span data-ttu-id="c6205-205">如果您沒有設定此設定，系統會顯示啟動頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-205">If you do not configure this setting, the Boot page is displayed.</span></span>                                                                                                                                                            |
| <span data-ttu-id="c6205-206">DateTime</span><span class="sxs-lookup"><span data-stu-id="c6205-206">DateTime</span></span>                           | <span data-ttu-id="c6205-207">顯示 Surface UEFI **DateTime** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-207">Displays the Surface UEFI **DateTime** page.</span></span> <span data-ttu-id="c6205-208">如果您沒有設定此設定，則會顯示 DateTime 頁面。</span><span class="sxs-lookup"><span data-stu-id="c6205-208">If you do not configure this setting, the DateTime page is displayed.</span></span>                                                                                                                |
| <span data-ttu-id="c6205-209">EnableOSMigration</span><span class="sxs-lookup"><span data-stu-id="c6205-209">EnableOSMigration</span></span>                          | <span data-ttu-id="c6205-210">可讓您將 Surface Hub 2 從 Windows 10 小組遷移到 Windows 10 專業版或企業版。</span><span class="sxs-lookup"><span data-stu-id="c6205-210">Allows you to migrate Surface Hub 2 from Windows 10 Team to Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="c6205-211">如果您沒有設定此設定，Surface Hub 2 裝置只能執行 Windows 10 小組作業系統。</span><span class="sxs-lookup"><span data-stu-id="c6205-211">If you do not configure this setting, Surface Hub 2 devices can only run Windows 10 Team OS.</span></span>   <span data-ttu-id="c6205-212">注意：Surface Hub 2 無法提供 Windows 10 小組與 Windows 10 專業版/企業版之間的雙開機。</span><span class="sxs-lookup"><span data-stu-id="c6205-212">Note: Dual booting between Windows 10 Team and Windows 10 Pro/Enterprise  is not available on Surface Hub 2.</span></span>                                                                                                           |


>[!NOTE]
><span data-ttu-id="c6205-213">當您建立 SEMM 組組套件時，成功頁面上會顯示兩\*\*\*\* 個字元，如圖 3 所示。</span><span class="sxs-lookup"><span data-stu-id="c6205-213">When you create a SEMM configuration package, two characters are shown on the **Successful** page, as shown in Figure 3.</span></span>

![憑證指紋顯示](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*<span data-ttu-id="c6205-215">圖 3.</span><span class="sxs-lookup"><span data-stu-id="c6205-215">Figure 3.</span></span> <span data-ttu-id="c6205-216">在成功頁面上顯示憑證指紋的最後兩個字元</span><span class="sxs-lookup"><span data-stu-id="c6205-216">Display of the last two characters of the certificate thumbprint on the Successful page</span></span>*

<span data-ttu-id="c6205-217">這些字元是憑證指紋的最後兩個字元，應該寫下或錄製。</span><span class="sxs-lookup"><span data-stu-id="c6205-217">These characters are the last two characters of the certificate thumbprint and should be written down or recorded.</span></span> <span data-ttu-id="c6205-218">需要字元才能確認在 Surface 裝置上註冊 SEMM，如圖 4 所示。</span><span class="sxs-lookup"><span data-stu-id="c6205-218">The characters are required to confirm enrollment in SEMM on a Surface device, as shown in Figure 4.</span></span>

![SEMM 中的註冊確認](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*<span data-ttu-id="c6205-220">圖 4.</span><span class="sxs-lookup"><span data-stu-id="c6205-220">Figure 4.</span></span> <span data-ttu-id="c6205-221">使用 SEMM 憑證指紋在 SEMM 中註冊確認</span><span class="sxs-lookup"><span data-stu-id="c6205-221">Enrollment confirmation in SEMM with the SEMM certificate thumbprint</span></span>*

>[!NOTE]
><span data-ttu-id="c6205-222">具有憑證檔案 (.pfx) 的系統管理員隨時都可以在 CertMgr 中開啟 .pfx 檔案來讀取指紋。</span><span class="sxs-lookup"><span data-stu-id="c6205-222">Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr.</span></span> <span data-ttu-id="c6205-223">若要使用 CertMgr 來查看指紋：</span><span class="sxs-lookup"><span data-stu-id="c6205-223">To view the thumbprint with CertMgr:</span></span> 
>1. <span data-ttu-id="c6205-224">以滑鼠右鍵按一下 .pfx 檔案，然後按一下 [ **開啟**。</span><span class="sxs-lookup"><span data-stu-id="c6205-224">Right-click the .pfx file, and then click **Open**.</span></span>
>2. <span data-ttu-id="c6205-225">展開流覽窗格中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="c6205-225">Expand the folder in the navigation pane.</span></span>
>3. <span data-ttu-id="c6205-226">按一下 [憑證]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c6205-226">Click **Certificates**.</span></span>
>4. <span data-ttu-id="c6205-227">以滑鼠右鍵按一下主窗格中的憑證，然後按一下 [ **開啟**。</span><span class="sxs-lookup"><span data-stu-id="c6205-227">Right-click your certificate in the main pane, and then click **Open**.</span></span>
>5. <span data-ttu-id="c6205-228">按一下 [ **詳細資料>** 選項卡。</span><span class="sxs-lookup"><span data-stu-id="c6205-228">Click the **Details** tab.</span></span>
>6. <span data-ttu-id="c6205-229">**在**顯示**下拉式功能表**中，必須選取所有或\*\*\*\* 僅屬性。</span><span class="sxs-lookup"><span data-stu-id="c6205-229">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
>7. <span data-ttu-id="c6205-230">選取拇 **指列印欄位**。</span><span class="sxs-lookup"><span data-stu-id="c6205-230">Select the field **Thumbprint**.</span></span>

<span data-ttu-id="c6205-231">若要在 SEMM 中註冊 Surface 裝置，或從組組套件套用 UEFI 組配置，您只需要在預定的 Surface 裝置上執行具有系統管理許可權的 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="c6205-231">To enroll a Surface device in SEMM or to apply the UEFI configuration from a configuration package, all you need to do is run the .msi file with administrative privileges on the intended Surface device.</span></span> <span data-ttu-id="c6205-232">您可以使用應用程式部署或作業系統部署技術，例如 [Microsoft 端點組組管理員](https://technet.microsoft.com/library/mt346023) 或 Microsoft [部署工具組](https://technet.microsoft.com/windows/dn475741)。</span><span class="sxs-lookup"><span data-stu-id="c6205-232">You can use application deployment or operating system deployment technologies such as [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) or the [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741).</span></span> <span data-ttu-id="c6205-233">當您在 SEMM 中註冊裝置時，您必須實際出席，以確認裝置上的註冊。</span><span class="sxs-lookup"><span data-stu-id="c6205-233">When you enroll a device in SEMM you must be physically present to confirm the enrollment on the device.</span></span> <span data-ttu-id="c6205-234">當您將群組原則適用于已在 SEMM 中註冊的裝置時，不需要使用者互動。</span><span class="sxs-lookup"><span data-stu-id="c6205-234">User interaction is not required when you apply a configuration to devices that are already enrolled in SEMM.</span></span>

<span data-ttu-id="c6205-235">若要逐步瞭解如何在 SEMM 中註冊 Surface 裝置，或在 SEMM 中適用 Surface UEFI 設定，請參閱使用 [SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)註冊及設定 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-235">For a step-by-step walkthrough of how to enroll a Surface device in SEMM or apply a Surface UEFI configuration with SEMM, see [Enroll and configure Surface devices with SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).</span></span>

### <a name="reset-package"></a><span data-ttu-id="c6205-236">重設套件</span><span class="sxs-lookup"><span data-stu-id="c6205-236">Reset package</span></span>

<span data-ttu-id="c6205-237">Surface UEFI 重設套件只會用來執行一項工作 ，從 SEMM 取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-237">A Surface UEFI reset package is used to perform only one task — to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="c6205-238">重設套件包含簽署指示，以從裝置固件移除 SEMM 憑證，以及將 UEFI 設定重設為出廠預設值。</span><span class="sxs-lookup"><span data-stu-id="c6205-238">The reset package contains signed instructions to remove the SEMM certificate from the device’s firmware and to reset UEFI settings to factory default.</span></span> <span data-ttu-id="c6205-239">就像 Surface UEFI 組組套件一樣，重設套件必須以與 Surface 裝置上所配置的相同 SEMM 憑證簽署。</span><span class="sxs-lookup"><span data-stu-id="c6205-239">Like a Surface UEFI configuration package, a reset package must be signed with the same SEMM certificate that is provisioned on the Surface device.</span></span> <span data-ttu-id="c6205-240">當您建立 SEMM 重設套件時，您必須提供要重設的 Surface 裝置序號。</span><span class="sxs-lookup"><span data-stu-id="c6205-240">When you create a SEMM reset package, you are required to supply the serial number of the Surface device you intend to reset.</span></span> <span data-ttu-id="c6205-241">SEMM 重設套件並非通用套件，且只針對一個裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-241">SEMM reset packages are not universal and are specific to one device.</span></span>

### <a name="recovery-request"></a><span data-ttu-id="c6205-242">復原要求</span><span class="sxs-lookup"><span data-stu-id="c6205-242">Recovery request</span></span>

<span data-ttu-id="c6205-243">在某些情況下，可能無法使用 Surface UEFI 重設套件。</span><span class="sxs-lookup"><span data-stu-id="c6205-243">In some scenarios, it may be impossible to use a Surface UEFI reset package.</span></span> <span data-ttu-id="c6205-244"> (例如，如果 Windows 在 Surface 裝置上無法使用。) 在這些情況下，您可以使用修復要求作業，透過 Surface UEFI () 的企業管\理\*\*\** 頁面，從 SEMM 取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-244">(For example, if Windows becomes unusable on the Surface device.) In these scenarios you can unenroll the Surface device from SEMM through the **Enterprise Management** page of Surface UEFI (shown in Figure 5) with a Recovery Request operation.</span></span>

> [!div class="mx-imgBorder"]
> ![啟動 SEMM 復原要求](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*<span data-ttu-id="c6205-246">圖 5.</span><span class="sxs-lookup"><span data-stu-id="c6205-246">Figure 5.</span></span> <span data-ttu-id="c6205-247">在企業管理頁面上啟動 SEMM 修復要求</span><span class="sxs-lookup"><span data-stu-id="c6205-247">Initiate a SEMM recovery request on the Enterprise Management page</span></span>*

<span data-ttu-id="c6205-248">當您使用企業管理頁面上的流程來重\*\*\*\* 設 Surface 裝置上的 SEMM 時，系統會提供重設要求。</span><span class="sxs-lookup"><span data-stu-id="c6205-248">When you use the process on the **Enterprise Management** page to reset SEMM on a Surface device, you are provided with a Reset Request.</span></span> <span data-ttu-id="c6205-249">此重設要求可以儲存為檔案至 USB 磁碟機、複製為文字，或以 QR 程式碼與行動裝置一起讀取，以輕鬆以電子郵件或訊息進行。</span><span class="sxs-lookup"><span data-stu-id="c6205-249">This Reset Request can be saved as a file to a USB drive, copied as text, or read as a QR Code with a mobile device to be easily emailed or messaged.</span></span> <span data-ttu-id="c6205-250">使用 Microsoft Surface UEFI 設定程式重設要求選項來載入重設要求檔案，或輸入重設要求文字或 QR 程式碼。</span><span class="sxs-lookup"><span data-stu-id="c6205-250">Use the Microsoft Surface UEFI Configurator Reset Request option to load a Reset Request file or enter the Reset Request text or QR Code.</span></span> <span data-ttu-id="c6205-251">Microsoft Surface UEFI Configurator 會產生可在 Surface 裝置上輸入的驗證碼。</span><span class="sxs-lookup"><span data-stu-id="c6205-251">Microsoft Surface UEFI Configurator will generate a verification code that can be entered on the Surface device.</span></span> <span data-ttu-id="c6205-252">如果您在 Surface 裝置上輸入程式碼，然後按一下 **[重新開機**，裝置將會從 SEMM 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="c6205-252">If you enter the code on the Surface device and click **Restart**, the device will be unenrolled from SEMM.</span></span> 

>[!NOTE]
><span data-ttu-id="c6205-253">重設要求會在建立後兩小時到期。</span><span class="sxs-lookup"><span data-stu-id="c6205-253">A Reset Request expires two hours after it is created.</span></span>

<span data-ttu-id="c6205-254">若要逐步瞭解如何從 SEMM 取消註冊 Surface 裝置，請參閱從 [SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c6205-254">For a step-by-step walkthrough of how to unenroll Surface devices from SEMM, see [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).</span></span>

## <a name="surface-enterprise-management-mode-certificate-requirements"></a><span data-ttu-id="c6205-255">Surface 企業管理模式憑證需求</span><span class="sxs-lookup"><span data-stu-id="c6205-255">Surface Enterprise Management Mode certificate requirements</span></span>
<span data-ttu-id="c6205-256">將 SEMM 與 Microsoft Surface UEFI 設定器一起使用，需要憑證來驗證組組檔案的簽名，才能使用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="c6205-256">Using SEMM with Microsoft Surface UEFI Configurator requires a certificate to verify the signature of configuration files before UEFI settings can be applied.</span></span> <span data-ttu-id="c6205-257">此憑證可確保在裝置註冊 SEMM 之後，只有使用核准憑證所建立套件才能用來修改 UEFI 的設定。</span><span class="sxs-lookup"><span data-stu-id="c6205-257">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span>

>[!NOTE]
><span data-ttu-id="c6205-258">需要 SEMM 憑證才能在已註冊的 Surface 裝置上對 SEMM 或 Surface UEFI 設定執行任何修改。</span><span class="sxs-lookup"><span data-stu-id="c6205-258">The SEMM certificate is required to perform any modification to SEMM or Surface UEFI settings on enrolled Surface devices.</span></span> <span data-ttu-id="c6205-259">如果 SEMM 憑證已損壞或遺失，就無法移除或重設 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c6205-259">If the SEMM certificate is corrupted or lost, SEMM cannot be removed or reset.</span></span> <span data-ttu-id="c6205-260">使用適當的備份及復原解決方案管理您的 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="c6205-260">Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery.</span></span>

<span data-ttu-id="c6205-261">使用 Microsoft Surface UEFI Configurator 工具所建立套件會以憑證簽署。</span><span class="sxs-lookup"><span data-stu-id="c6205-261">Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate.</span></span> <span data-ttu-id="c6205-262">此憑證可確保在裝置註冊 SEMM 之後，只有使用核准憑證所建立套件才能用來修改 UEFI 的設定。</span><span class="sxs-lookup"><span data-stu-id="c6205-262">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span> 
### <a name="recommended-certificate-settings"></a><span data-ttu-id="c6205-263">建議的憑證設定</span><span class="sxs-lookup"><span data-stu-id="c6205-263">Recommended certificate settings</span></span>
<span data-ttu-id="c6205-264">SEMM 憑證建議使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="c6205-264">The following settings are recommended for the SEMM certificate:</span></span>

* <span data-ttu-id="c6205-265">**金鑰演算法** – RSA</span><span class="sxs-lookup"><span data-stu-id="c6205-265">**Key Algorithm** – RSA</span></span> 
* <span data-ttu-id="c6205-266">**金鑰長度** – 2048</span><span class="sxs-lookup"><span data-stu-id="c6205-266">**Key Length** – 2048</span></span>
* <span data-ttu-id="c6205-267">**雜湊演算法** – SHA-256</span><span class="sxs-lookup"><span data-stu-id="c6205-267">**Hash Algorithm** – SHA-256</span></span>
* <span data-ttu-id="c6205-268">**類型** - SSL Server 驗證</span><span class="sxs-lookup"><span data-stu-id="c6205-268">**Type** – SSL Server Authentication</span></span>
* <span data-ttu-id="c6205-269">**金鑰使用量** – 數位簽章、金鑰加密</span><span class="sxs-lookup"><span data-stu-id="c6205-269">**Key Usage** – Digital signature, Key Encipherment</span></span>
* <span data-ttu-id="c6205-270">**提供者** – Microsoft 增強版 RSA 和 AES 加密提供者</span><span class="sxs-lookup"><span data-stu-id="c6205-270">**Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider</span></span>
* <span data-ttu-id="c6205-271">**到期日** – 自建立憑證起 15 個月</span><span class="sxs-lookup"><span data-stu-id="c6205-271">**Expiration Date** – 15 Months from certificate creation</span></span>
* <span data-ttu-id="c6205-272">**金鑰匯出政策** – 可匯出</span><span class="sxs-lookup"><span data-stu-id="c6205-272">**Key Export Policy** – Exportable</span></span>

<span data-ttu-id="c6205-273">此外，建議在兩層公用金鑰基礎結構 (PKI) 架構中驗證 SEMM 憑證，而中間憑證授權單位 (CA) 是專門用於 SEMM 的架構，啟用憑證撤銷。</span><span class="sxs-lookup"><span data-stu-id="c6205-273">It is also recommended that the SEMM certificate be authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation.</span></span> <span data-ttu-id="c6205-274">有關雙層級 PKI 組的資訊，請參閱測試實驗室指南：部署 [AD CS Two-Tier PKI 階層](https://technet.microsoft.com/library/hh831348)。</span><span class="sxs-lookup"><span data-stu-id="c6205-274">For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).</span></span>

### <a name="self-signed-certificate"></a><span data-ttu-id="c6205-275">自我簽署憑證</span><span class="sxs-lookup"><span data-stu-id="c6205-275">Self-signed certificate</span></span> 
<span data-ttu-id="c6205-276">您可以使用下列範例 PowerShell 腳本建立自我簽署憑證，以用於概念證明案例。</span><span class="sxs-lookup"><span data-stu-id="c6205-276">You can use the following example PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.</span></span>
<span data-ttu-id="c6205-277">若要使用此腳本，請複製下列文字至記事本，然後將檔案儲存為 PowerShell 腳本 (.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="c6205-277">To use this script, copy the following text into Notepad and save the file as a PowerShell script (.ps1).</span></span> 

> [!NOTE]
> <span data-ttu-id="c6205-278">此腳本會建立具有 密碼的憑證 `12345678` 。此腳本產生的憑證不建議用於生產環境。</span><span class="sxs-lookup"><span data-stu-id="c6205-278">This script creates a certificate with a password of `12345678`.The certificate generated by this script is not recommended for production environments.</span></span>
  
```powershell
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

>[!IMPORTANT]
><span data-ttu-id="c6205-279">為了與 SEMM 和 Microsoft Surface UEFI Configurator 一起使用，憑證必須以私密金鑰和密碼保護方式匯出。</span><span class="sxs-lookup"><span data-stu-id="c6205-279">For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection.</span></span> <span data-ttu-id="c6205-280">Microsoft Surface UEFI Configurator 會提示您視需要選取 SEMM 憑證檔案 (.pfx) 和憑證密碼。</span><span class="sxs-lookup"><span data-stu-id="c6205-280">Microsoft Surface UEFI Configurator will prompt you to select the SEMM certificate file (.pfx) and certificate password when it is required.</span></span>

1.  <span data-ttu-id="c6205-281">在 C 上建立資料夾：您將儲存腳本的磁碟機;例如，C：\SEMM。</span><span class="sxs-lookup"><span data-stu-id="c6205-281">Create a folder on your C: drive where you will save the script; for example, C:\SEMM.</span></span>
2.  <span data-ttu-id="c6205-282">將範例腳本複製到記事本或同等文字編輯器，然後以 PowerShell 腳本 (.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="c6205-282">Copy the example script into Notepad or equivalent text editor and save the file as a PowerShell script (.ps1).</span></span>
3.  <span data-ttu-id="c6205-283">使用系統管理員認證來登錄您的電腦，並開啟提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c6205-283">Sign into your PC with administrator credentials and open an elevated PowerShell session.</span></span>
4.  <span data-ttu-id="c6205-284">請確定您的許可權設定為允許腳本執行。</span><span class="sxs-lookup"><span data-stu-id="c6205-284">Ensure your permissions are set to allow scripts to run.</span></span> <span data-ttu-id="c6205-285">根據預設，除非您修改執行策略，否則腳本會禁止執行。</span><span class="sxs-lookup"><span data-stu-id="c6205-285">By default, scripts are blocked from running unless you modify the execution policy.</span></span> <span data-ttu-id="c6205-286">若要深入瞭解，請參閱 [關於執行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)。</span><span class="sxs-lookup"><span data-stu-id="c6205-286">To learn more, see [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
5.  <span data-ttu-id="c6205-287">在命令提示符中，輸入腳本的完整路徑，然後按 Enter。</span><span class="sxs-lookup"><span data-stu-id="c6205-287">At the command prompt, enter the full path of the script and then press Enter.</span></span> <span data-ttu-id="c6205-288">腳本會建立名為 TempOwner.pfx 的示範憑證。</span><span class="sxs-lookup"><span data-stu-id="c6205-288">The script creates a Demo Certificate named TempOwner.pfx.</span></span>

<span data-ttu-id="c6205-289">或者，您可以使用 PowerShell 建立自己的自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="c6205-289">Alternatively, you can create your own self-signed certificate using PowerShell.</span></span> <span data-ttu-id="c6205-290">詳細資訊，請參閱下列 PowerShell 檔 [：New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)。</span><span class="sxs-lookup"><span data-stu-id="c6205-290">For more information, see the following PowerShell documentation: [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>




>[!NOTE]
><span data-ttu-id="c6205-291">針對在 PKI 基礎結構中使用離線根目錄的組織，Microsoft Surface UEFI Configurator 必須在連線至根 CA 的環境中執行，以驗證 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="c6205-291">For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate.</span></span> <span data-ttu-id="c6205-292">Microsoft Surface UEFI Configurator 產生的套件可以以檔案方式傳輸，因此可以在離線網路環境外使用可移除的儲存空間傳輸，例如 USB 記憶棒。</span><span class="sxs-lookup"><span data-stu-id="c6205-292">The packages generated by Microsoft Surface UEFI Configurator can be transferred as files and therefore can be transferred outside the offline network environment with removable storage, such as a USB stick.</span></span>

### <a name="managing-certificates-faq"></a><span data-ttu-id="c6205-293">管理憑證常見問題</span><span class="sxs-lookup"><span data-stu-id="c6205-293">Managing certificates FAQ</span></span>

<span data-ttu-id="c6205-294">建議的最小 *長度* 為 15 個月。</span><span class="sxs-lookup"><span data-stu-id="c6205-294">The recommended *minimum* length is 15 months.</span></span> <span data-ttu-id="c6205-295">您可以使用在 15 個月內到期的憑證，或使用超過 15 個月的憑證。</span><span class="sxs-lookup"><span data-stu-id="c6205-295">You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.</span></span>

>[!NOTE] 
><span data-ttu-id="c6205-296">憑證到期時，它不會自動續約。</span><span class="sxs-lookup"><span data-stu-id="c6205-296">When a certificate expires, it does not automatically renew.</span></span> 


**<span data-ttu-id="c6205-297">過期的憑證會影響 SEMM 註冊的裝置功能嗎？</span><span class="sxs-lookup"><span data-stu-id="c6205-297">Will an expired certificate affect the functionality of SEMM-enrolled devices?</span></span>**<br><br>
<span data-ttu-id="c6205-298">否，憑證只會影響 SEMM 中的 IT 系統管理員管理工作，且在到期時不會影響裝置功能。</span><span class="sxs-lookup"><span data-stu-id="c6205-298">No, a certificate only impacts IT admin management tasks in SEMM and has no effect on device functionality when it expires.</span></span>


**<span data-ttu-id="c6205-299">需要在所有擁有 SEMM 套件和憑證的機器上更新嗎？</span><span class="sxs-lookup"><span data-stu-id="c6205-299">Will the SEMM package and certificate need to be updated on all machines that have it?</span></span>**

<span data-ttu-id="c6205-300">如果您希望 SEMM 重設或復原能夠生效，憑證必須有效且不會過期。</span><span class="sxs-lookup"><span data-stu-id="c6205-300">If you want SEMM reset or recovery to work, the certificate needs to be valid and not expired.</span></span> 

**<span data-ttu-id="c6205-301">可以針對我們訂購的每個曲面建立大量重設套件嗎？</span><span class="sxs-lookup"><span data-stu-id="c6205-301">Can bulk reset packages be created for each surface that we order?</span></span> <span data-ttu-id="c6205-302">可以建立可重設環境中所有電腦之機器的建立嗎？</span><span class="sxs-lookup"><span data-stu-id="c6205-302">Can one be built that resets all machines in our environment?</span></span>**

<span data-ttu-id="c6205-303">為特定裝置類型建立設定套件的 PowerShell 範例也可以用來建立與序列值無關的重設套件。</span><span class="sxs-lookup"><span data-stu-id="c6205-303">The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that is serial-number independent.</span></span> <span data-ttu-id="c6205-304">如果憑證仍然有效，您可以使用 PowerShell 建立重設套件來重設 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c6205-304">If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.</span></span>

## <a name="version-history"></a><span data-ttu-id="c6205-305">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="c6205-305">Version History</span></span>

### <a name="version-2791390"></a><span data-ttu-id="c6205-306">版本 2.79.139.0</span><span class="sxs-lookup"><span data-stu-id="c6205-306">Version 2.79.139.0</span></span>

<span data-ttu-id="c6205-307">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c6205-307">This version of SEMM includes:</span></span>
- <span data-ttu-id="c6205-308">支援 Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="c6205-308">Support for Surface Pro 7+</span></span>
- <span data-ttu-id="c6205-309">使用者體驗改良功能</span><span class="sxs-lookup"><span data-stu-id="c6205-309">User experience improvements</span></span>


### <a name="version-2781390"></a><span data-ttu-id="c6205-310">版本 2.78.139.0</span><span class="sxs-lookup"><span data-stu-id="c6205-310">Version 2.78.139.0</span></span>

<span data-ttu-id="c6205-311">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c6205-311">This version of SEMM includes:</span></span>

- <span data-ttu-id="c6205-312">Surface Laptop Go 和 Surface Pro X 的支援</span><span class="sxs-lookup"><span data-stu-id="c6205-312">Support for Surface Laptop Go and Surface Pro X</span></span>
- <span data-ttu-id="c6205-313">新版本發行通知</span><span class="sxs-lookup"><span data-stu-id="c6205-313">Notifications for new version release</span></span>
- <span data-ttu-id="c6205-314">建立自訂套件以變更擁有權的能力</span><span class="sxs-lookup"><span data-stu-id="c6205-314">Ability to create custom packages to change ownership</span></span>
- <span data-ttu-id="c6205-315">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="c6205-315">Bug fixes</span></span>

### <a name="version-2731360"></a><span data-ttu-id="c6205-316">版本 2.73.136.0</span><span class="sxs-lookup"><span data-stu-id="c6205-316">Version 2.73.136.0</span></span>

<span data-ttu-id="c6205-317">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c6205-317">This version of SEMM includes:</span></span>

- <span data-ttu-id="c6205-318">現在可以使用 SEMM 在 Surface Hub2S 上停用音訊</span><span class="sxs-lookup"><span data-stu-id="c6205-318">Audio can now be disabled on Surface Hub2S using SEMM</span></span>
- <span data-ttu-id="c6205-319">支援 Surface Pro X for Dock 2</span><span class="sxs-lookup"><span data-stu-id="c6205-319">Support to Surface Pro X for Dock 2</span></span>
- <span data-ttu-id="c6205-320">支援 Dock 2 相關作業的 UEFI Manager</span><span class="sxs-lookup"><span data-stu-id="c6205-320">Support to UEFI Manager for Dock 2 related operations</span></span>
- <span data-ttu-id="c6205-321">Surface Go 重設套件錯誤修正</span><span class="sxs-lookup"><span data-stu-id="c6205-321">Surface Go reset package bug fix</span></span>
- <span data-ttu-id="c6205-322">支援將 Surface Hub 2 裝置從 Windows 10 小組作業系統移遷移到 Windows 10 專業版或企業版。</span><span class="sxs-lookup"><span data-stu-id="c6205-322">Support for migrating Surface Hub 2 devices from Windows 10 Team OS to Windows 10 Pro or Enterprise.</span></span>

### <a name="version-2711390"></a><span data-ttu-id="c6205-323">版本 2.71.139.0</span><span class="sxs-lookup"><span data-stu-id="c6205-323">Version 2.71.139.0</span></span>

<span data-ttu-id="c6205-324">此版本的 SEMM 新增了 Surface Book 3、Surface Laptop 3 和 Surface Pro 7 的 Surface Dock 2 管理功能支援，包括：</span><span class="sxs-lookup"><span data-stu-id="c6205-324">This version of SEMM adds support for Surface Dock 2 management features  for Surface Book 3, Surface Laptop 3, and Surface Pro 7 including:</span></span>

- <span data-ttu-id="c6205-325">啟用音訊 (鎖定/解除鎖定) 乙太網路和 USB 埠</span><span class="sxs-lookup"><span data-stu-id="c6205-325">Enabling audio (locking/unlocking), Ethernet and USB ports</span></span>
- <span data-ttu-id="c6205-326">為已驗證和未經驗證的主機建立固定套件的能力</span><span class="sxs-lookup"><span data-stu-id="c6205-326">Ability to create dock packages for both authenticated and unauthenticated hosts</span></span>

### <a name="version-2701300"></a><span data-ttu-id="c6205-327">版本 2.70.130.0</span><span class="sxs-lookup"><span data-stu-id="c6205-327">Version 2.70.130.0</span></span>

<span data-ttu-id="c6205-328">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c6205-328">This version of SEMM includes:</span></span>

- <span data-ttu-id="c6205-329">支援 Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="c6205-329">Support for Surface Go 2</span></span>
- <span data-ttu-id="c6205-330">Surface Book 3 的支援</span><span class="sxs-lookup"><span data-stu-id="c6205-330">Support for Surface Book 3</span></span>
- <span data-ttu-id="c6205-331">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="c6205-331">Bug fixes</span></span>


### <a name="version-2591390"></a><span data-ttu-id="c6205-332">版本 2.59.139.0</span><span class="sxs-lookup"><span data-stu-id="c6205-332">Version 2.59.139.0</span></span>

* <span data-ttu-id="c6205-333">支援 Surface Pro 7、Surface Pro X 和 Surface Laptop 3 13.5" 和 15" 型號的 Intel 處理器。</span><span class="sxs-lookup"><span data-stu-id="c6205-333">Support for Surface Pro 7, Surface Pro X,  and Surface Laptop 3 13.5" and 15" models with Intel processor.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c6205-334">Surface Laptop 3 15" 的AMD 處理器不受支援。</span><span class="sxs-lookup"><span data-stu-id="c6205-334">Surface Laptop 3 15" AMD processor is not supported.</span></span>

- <span data-ttu-id="c6205-335">支援 Power 喚醒功能</span><span class="sxs-lookup"><span data-stu-id="c6205-335">Support for Wake on Power feature</span></span>

### <a name="version-2541390"></a><span data-ttu-id="c6205-336">版本 2.54.139.0</span><span class="sxs-lookup"><span data-stu-id="c6205-336">Version 2.54.139.0</span></span>
* <span data-ttu-id="c6205-337">支援 Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="c6205-337">Support to Surface Hub 2S</span></span>
* <span data-ttu-id="c6205-338">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="c6205-338">Bug fixes</span></span>

### <a name="version-2431360"></a><span data-ttu-id="c6205-339">版本 2.43.136.0</span><span class="sxs-lookup"><span data-stu-id="c6205-339">Version 2.43.136.0</span></span>
* <span data-ttu-id="c6205-340">支援啟用/停用模擬多執行緒</span><span class="sxs-lookup"><span data-stu-id="c6205-340">Support to enable/disable simulatenous multithreating</span></span> 
* <span data-ttu-id="c6205-341">部分裝置個別的 WiFi 和藍牙選項</span><span class="sxs-lookup"><span data-stu-id="c6205-341">Separate options for WiFi and Bluetooth for some devices</span></span> 
* <span data-ttu-id="c6205-342">已移除 Surface Studio 的電池限制</span><span class="sxs-lookup"><span data-stu-id="c6205-342">Battery Limit removed for Surface Studio</span></span> 

### <a name="version-2261360"></a><span data-ttu-id="c6205-343">版本 2.26.136.0</span><span class="sxs-lookup"><span data-stu-id="c6205-343">Version 2.26.136.0</span></span>
* <span data-ttu-id="c6205-344">新增支援至 Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="c6205-344">Add support to Surface Studio 2</span></span>
* <span data-ttu-id="c6205-345">電池限制功能</span><span class="sxs-lookup"><span data-stu-id="c6205-345">Battery Limit feature</span></span>

### <a name="version-2211360"></a><span data-ttu-id="c6205-346">版本 2.21.136.0</span><span class="sxs-lookup"><span data-stu-id="c6205-346">Version 2.21.136.0</span></span>
* <span data-ttu-id="c6205-347">新增支援至 Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="c6205-347">Add support to Surface Pro 6</span></span>
* <span data-ttu-id="c6205-348">新增 Surface Laptop 2 的支援</span><span class="sxs-lookup"><span data-stu-id="c6205-348">Add support to Surface Laptop 2</span></span>

### <a name="version-2141360"></a><span data-ttu-id="c6205-349">版本 2.14.136.0</span><span class="sxs-lookup"><span data-stu-id="c6205-349">Version 2.14.136.0</span></span>
* <span data-ttu-id="c6205-350">新增支援至 Surface Go</span><span class="sxs-lookup"><span data-stu-id="c6205-350">Add support to Surface Go</span></span>

### <a name="version-291360"></a><span data-ttu-id="c6205-351">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="c6205-351">Version 2.9.136.0</span></span>
* <span data-ttu-id="c6205-352">新增支援至 Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="c6205-352">Add support to Surface Book 2</span></span>
* <span data-ttu-id="c6205-353">為 Surface Pro LTE 新增支援</span><span class="sxs-lookup"><span data-stu-id="c6205-353">Add support to Surface Pro LTE</span></span>
* <span data-ttu-id="c6205-354">協助工具改良功能</span><span class="sxs-lookup"><span data-stu-id="c6205-354">Accessibility improvements</span></span>

### <a name="version-10740"></a><span data-ttu-id="c6205-355">版本 1.0.74.0</span><span class="sxs-lookup"><span data-stu-id="c6205-355">Version 1.0.74.0</span></span>
* <span data-ttu-id="c6205-356">在 Surface Laptop 中新增支援</span><span class="sxs-lookup"><span data-stu-id="c6205-356">Add support to Surface Laptop</span></span>
* <span data-ttu-id="c6205-357">新增支援至 Surface Pro</span><span class="sxs-lookup"><span data-stu-id="c6205-357">Add support to Surface Pro</span></span>
* <span data-ttu-id="c6205-358">錯誤修正和一般改進</span><span class="sxs-lookup"><span data-stu-id="c6205-358">Bug fixes and general improvement</span></span>

## <a name="related-topics"></a><span data-ttu-id="c6205-359">相關主題</span><span class="sxs-lookup"><span data-stu-id="c6205-359">Related topics</span></span>

- [<span data-ttu-id="c6205-360">使用 SEMM 註冊及設定 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="c6205-360">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)
- [<span data-ttu-id="c6205-361">從 SEMM 取消 Surface 裝置的註冊</span><span class="sxs-lookup"><span data-stu-id="c6205-361">Unenroll Surface devices from SEMM</span></span>](unenroll-surface-devices-from-semm.md)
- [<span data-ttu-id="c6205-362">使用 SEMM 保護 Surface Dock 2 連接埠的安全</span><span class="sxs-lookup"><span data-stu-id="c6205-362">Secure Surface Dock 2 ports with SEMM</span></span>](secure-surface-dock-ports-semm.md)
