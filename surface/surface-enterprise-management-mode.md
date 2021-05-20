---
title: 'Surface Enterprise管理模式 (Surface) '
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
ms.date: 04/16/2021
ms.openlocfilehash: 3c7eea524daa3210a329c41536f4c47a2c012bcf
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576583"
---
# <a name="microsoft-surface-enterprise-management-mode"></a><span data-ttu-id="c4c15-104">Microsoft Surface Enterprise管理模式</span><span class="sxs-lookup"><span data-stu-id="c4c15-104">Microsoft Surface Enterprise Management Mode</span></span>

<span data-ttu-id="c4c15-105">Microsoft Surface Enterprise管理模式 (SEMM) 是 Surface 裝置與 Surface Unified Unified 可擴展的固件介面 (UEFI) 。</span><span class="sxs-lookup"><span data-stu-id="c4c15-105">Microsoft Surface Enterprise Management Mode (SEMM) is a feature of Surface devices with Surface Unified Extensible Firmware Interface (UEFI).</span></span> <span data-ttu-id="c4c15-106">您可以使用 SEMM：</span><span class="sxs-lookup"><span data-stu-id="c4c15-106">You can use SEMM to:</span></span>

- <span data-ttu-id="c4c15-107">保護和管理貴組織的固件設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-107">Secure and manage firmware settings in your organization.</span></span>
- <span data-ttu-id="c4c15-108">準備 UEFI 設定設定，並安裝在 Surface 裝置上。</span><span class="sxs-lookup"><span data-stu-id="c4c15-108">Prepare UEFI settings configurations and install them on a Surface device.</span></span> 

<span data-ttu-id="c4c15-109">SEMM 也會使用憑證來保護組組，避免未經授權的竄改或移除。</span><span class="sxs-lookup"><span data-stu-id="c4c15-109">SEMM also uses a certificate to protect the configuration from unauthorized tampering or removal.</span></span> <span data-ttu-id="c4c15-110">若要將 Surface Hub 2S Windows 10 專業版或 Windows Enterprise，需要 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c4c15-110">To migrate a Surface Hub 2S to Windows 10 Pro or Windows Enterprise, SEMM is required.</span></span>

>[!NOTE]
><span data-ttu-id="c4c15-111">SEMM 僅適用于具有 Surface UEFI 固件的裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-111">SEMM is only available on devices with Surface UEFI firmware.</span></span> <span data-ttu-id="c4c15-112">這包括大多數的其他 Surface 裝置，包括 Surface Pro 7+、Surface Pro X、Surface Hub 2S、Surface Laptop 4 個含有 Intel 處理器的商業 SKUS、Surface Laptop 4 個含有AMD 處理器的商業 SUS、Surface Laptop 3 個含有 Intel 處理器的商業 SUS，以及 Surface Laptop Go。</span><span class="sxs-lookup"><span data-stu-id="c4c15-112">This includes most other Surface devices including Surface Pro 7+, Surface Pro X, Surface Hub 2S, Surface Laptop 4 commercial SKUs with an Intel processor, Surface Laptop 4 commercial SKUs with AMD processor, Surface Laptop 3 commercial SKUs with an Intel processor, and Surface Laptop Go.</span></span> <span data-ttu-id="c4c15-113">3 SKU 的 15" Surface Laptop SKU 不支援 SEMM， (僅提供零售 SKU) 。</span><span class="sxs-lookup"><span data-stu-id="c4c15-113">SEMM is not supported on the 15" Surface Laptop 3 SKU with AMD processor (available only as a retail SKU).</span></span> 

<span data-ttu-id="c4c15-114">當 Surface 裝置是由 SEMM 所配置，且使用 SEMM 憑證進行保護時\*\*，即視為已註冊于 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c4c15-114">When Surface devices are configured by SEMM and secured with the SEMM certificate, they're considered *enrolled* in SEMM.</span></span> <span data-ttu-id="c4c15-115">移除 SEMM 憑證，且將 UEFI 設定控制權退還給裝置使用者時，Surface 裝置在 SEMM 中視為未註冊。 \*\*</span><span class="sxs-lookup"><span data-stu-id="c4c15-115">When the SEMM certificate is removed and control of UEFI settings is returned to the user of the device, the Surface device is considered *unenrolled* in SEMM.</span></span>

<span data-ttu-id="c4c15-116">您可以使用兩種系統管理選項來管理 SEMM 並註冊 Surface 裝置：</span><span class="sxs-lookup"><span data-stu-id="c4c15-116">There are two administrative options that you can use to manage SEMM and enroll Surface devices:</span></span>

- <span data-ttu-id="c4c15-117">本文說明 SEMM 獨立工具 Microsoft Surface UEFI Configurator。</span><span class="sxs-lookup"><span data-stu-id="c4c15-117">SEMM standalone tool, Microsoft Surface UEFI Configurator, is described in this article.</span></span> 

- <span data-ttu-id="c4c15-118">與 Microsoft Endpoint Configuration Manager 整合。</span><span class="sxs-lookup"><span data-stu-id="c4c15-118">Integration with Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="c4c15-119">詳細資訊，請參閱[使用 Microsoft Endpoint Configuration Manager SEMM 管理裝置](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-119">For information, see [Use Microsoft Endpoint Configuration Manager to manage devices with SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm).</span></span>

> [!NOTE]
> <span data-ttu-id="c4c15-120">僅透過 UEFI Manager Surface Pro X 支援 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c4c15-120">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="c4c15-121">您可以從 IT 的 Surface Tools 下載 UEFI [Manager。](https://www.microsoft.com/download/details.aspx?id=46703)</span><span class="sxs-lookup"><span data-stu-id="c4c15-121">You can download UEFI Manager from [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="c4c15-122">若要詳細資訊，請參閱部署、管理及維護[X Surface Pro。](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="c4c15-122">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>


## <a name="microsoft-surface-uefi-configurator"></a><span data-ttu-id="c4c15-123">Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="c4c15-123">Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="c4c15-124">SEMM 的主要工作區是 Microsoft Surface UEFI Configurator，如圖 1 所示。</span><span class="sxs-lookup"><span data-stu-id="c4c15-124">The primary workspace of SEMM is Microsoft Surface UEFI Configurator, as shown in Figure 1.</span></span> 

<span data-ttu-id="c4c15-125">您可以使用 Microsoft Surface UEFI Configurator：</span><span class="sxs-lookup"><span data-stu-id="c4c15-125">You can use Microsoft Surface UEFI Configurator to:</span></span>

- <span data-ttu-id="c4c15-126">建立Windows安裝程式 (.msi) 套件。</span><span class="sxs-lookup"><span data-stu-id="c4c15-126">Create Windows Installer (.msi) packages.</span></span>
- <span data-ttu-id="c4c15-127">使用 WinPE 影像在 Surface 裝置上註冊、設定及取消註冊 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c4c15-127">Use WinPE images to enroll, configure, and unenroll SEMM on a Surface device.</span></span> 

<span data-ttu-id="c4c15-128">這些套件包含指定 UEFI 設定的設定檔。</span><span class="sxs-lookup"><span data-stu-id="c4c15-128">These packages contain a configuration file that specifies the UEFI settings.</span></span> <span data-ttu-id="c4c15-129">SEMM 套件也包含已安裝並儲存在固件中的憑證，用於驗證組組檔案的簽名，然後再套用 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-129">SEMM packages also contain a certificate that's installed and stored in firmware and is used to verify the signature of configuration files before UEFI settings are applied.</span></span>

>[!TIP]
><span data-ttu-id="c4c15-130">現在，您可以使用 Surface UEFI Configurator 和 SEMM 來管理 Surface Dock 2 上的埠。</span><span class="sxs-lookup"><span data-stu-id="c4c15-130">You can now use Surface UEFI Configurator and SEMM to manage ports on Surface Dock 2.</span></span> <span data-ttu-id="c4c15-131">若要深入瞭解，請參閱使用 SEMM 保護 [Surface Dock 2 埠](secure-surface-dock-ports-semm.md)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-131">To learn more, see [Secure Surface Dock 2 ports with SEMM](secure-surface-dock-ports-semm.md).</span></span>

![Microsoft Surface UEFI Configurator](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*<span data-ttu-id="c4c15-133">圖 1。</span><span class="sxs-lookup"><span data-stu-id="c4c15-133">Figure 1.</span></span> <span data-ttu-id="c4c15-134">Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="c4c15-134">Microsoft Surface UEFI Configurator</span></span>*

<span data-ttu-id="c4c15-135">您可以在三種模式中使用 Microsoft Surface UEFI Configurator 工具：</span><span class="sxs-lookup"><span data-stu-id="c4c15-135">You can use the Microsoft Surface UEFI Configurator tool in three modes:</span></span>

- <span data-ttu-id="c4c15-136">[Surface UEFI 組組套件](#configuration-package)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-136">[Surface UEFI Configuration Package](#configuration-package).</span></span> <span data-ttu-id="c4c15-137">使用此模式可建立 Surface UEFI 設定套件，以在 SEMM 中註冊 Surface 裝置，以及設定已註冊的裝置上的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-137">Use this mode to create a Surface UEFI configuration package to enroll a Surface device in SEMM and to configure UEFI settings on enrolled devices.</span></span>
- <span data-ttu-id="c4c15-138">[Surface UEFI 重設套件](#reset-package)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-138">[Surface UEFI Reset Package](#reset-package).</span></span> <span data-ttu-id="c4c15-139">使用此模式從 SEMM 取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-139">Use this mode to unenroll a Surface device from SEMM.</span></span>
- <span data-ttu-id="c4c15-140">[Surface UEFI 修復要求](#recovery-request)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-140">[Surface UEFI Recovery Request](#recovery-request).</span></span> <span data-ttu-id="c4c15-141">使用此模式回應復原要求，從 SEMM 取消註冊 Surface 裝置，而重設套件作業失敗。</span><span class="sxs-lookup"><span data-stu-id="c4c15-141">Use this mode to respond to a recovery request to unenroll a Surface device from SEMM where a Reset Package operation is not successful.</span></span>

#### <a name="download-microsoft-surface-uefi-configurator"></a><span data-ttu-id="c4c15-142">下載 Microsoft Surface UEFI Configurator</span><span class="sxs-lookup"><span data-stu-id="c4c15-142">Download Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="c4c15-143">您可以從 Microsoft 下載中心的 SURFACE IT[](https://www.microsoft.com/download/details.aspx?id=46703)工具頁面下載 Microsoft Surface UEFI 配置程式。</span><span class="sxs-lookup"><span data-stu-id="c4c15-143">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

### <a name="configuration-package"></a><span data-ttu-id="c4c15-144">組組套件</span><span class="sxs-lookup"><span data-stu-id="c4c15-144">Configuration package</span></span>

<span data-ttu-id="c4c15-145">Surface UEFI 組組套件是在 Surface 裝置上執行和管理 SEMM 的主要機制。</span><span class="sxs-lookup"><span data-stu-id="c4c15-145">Surface UEFI configuration packages are the primary mechanism to implement and manage SEMM on Surface devices.</span></span> <span data-ttu-id="c4c15-146">這些套件包含組設定檔和憑證檔案，如圖 2 所示。</span><span class="sxs-lookup"><span data-stu-id="c4c15-146">These packages contain a configuration file and a certificate file, as shown in Figure 2.</span></span> <span data-ttu-id="c4c15-147">設定檔包含在 Microsoft Surface UEFI Configurationator 中建立套件時指定的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-147">The configuration file contains UEFI settings that are specified when the package is created in Microsoft Surface UEFI Configurator.</span></span> <span data-ttu-id="c4c15-148">當組組套件第一次在尚未在 SEMM 註冊的 Surface 裝置上執行時，它會在裝置的固件中規定憑證檔案，並註冊 SEMM 中的裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-148">When a configuration package runs for the first time on a Surface device that's not already enrolled in SEMM, it provisions the certificate file in the device’s firmware and enrolls the device in SEMM.</span></span> <span data-ttu-id="c4c15-149">在 SEMM 中註冊裝置時，以及憑證儲存及註冊完成之前，系統會提示您提供 SEMM 憑證指紋的最後兩位數以確認作業。</span><span class="sxs-lookup"><span data-stu-id="c4c15-149">When enrolling a device in SEMM, and before the certificate is stored and the enrollment finishes, you're prompted to confirm the operation by providing the last two digits of the SEMM certificate thumbprint.</span></span> <span data-ttu-id="c4c15-150">此確認要求使用者在註冊期間實際出席裝置，才能執行確認。</span><span class="sxs-lookup"><span data-stu-id="c4c15-150">This confirmation requires a user to be physically present at the device during enrollment to perform the confirmation.</span></span>

![使用憑證保護 SEMM 組組套件](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*<span data-ttu-id="c4c15-152">圖 2.</span><span class="sxs-lookup"><span data-stu-id="c4c15-152">Figure 2.</span></span> <span data-ttu-id="c4c15-153">使用憑證保護 SEMM 組組套件</span><span class="sxs-lookup"><span data-stu-id="c4c15-153">Secure a SEMM configuration package with a certificate</span></span>*

<span data-ttu-id="c4c15-154">有關 SEMM 憑證需求的資訊，請參閱本文稍後Enterprise [Surface Enterprise管理模式憑證](#surface-enterprise-management-mode-certificate-requirements)需求>一節。</span><span class="sxs-lookup"><span data-stu-id="c4c15-154">For more information about the requirements for the SEMM certificate, see the [Surface Enterprise Management Mode certificate requirements](#surface-enterprise-management-mode-certificate-requirements) section later in this article.</span></span>

>[!TIP]
><span data-ttu-id="c4c15-155">您可以選擇使用 SEMM 要求 UEFI 密碼。</span><span class="sxs-lookup"><span data-stu-id="c4c15-155">You have the option to require a UEFI password with SEMM.</span></span> <span data-ttu-id="c4c15-156">如果您這麼做，您必須輸入密碼才能查看 Surface \*\* **UEFI 的安全性\*\*\*\*、裝置、啟動Enterprise**管理\*\*頁面。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c4c15-156">If you do, the password is required to view the **Security**, **Devices**, **Boot Configuration**, and **Enterprise Management** pages of Surface UEFI.</span></span>

<span data-ttu-id="c4c15-157">在 SEMM 中註冊裝置之後，系統即會讀取組組檔案，且檔案中指定的設定會適用于 UEFI。</span><span class="sxs-lookup"><span data-stu-id="c4c15-157">After a device is enrolled in SEMM, the configuration file is read, and the settings specified in the file are applied to UEFI.</span></span> <span data-ttu-id="c4c15-158">當您在已在 SEMM 註冊的裝置上執行組組套件時，設定檔的簽名會針對儲存在裝置固件中的憑證進行檢查。</span><span class="sxs-lookup"><span data-stu-id="c4c15-158">When you run a configuration package on a device that's already enrolled in SEMM, the signature of the configuration file is checked against the certificate that's stored in the device firmware.</span></span> <span data-ttu-id="c4c15-159">如果簽章不相符，系統不會對裝置進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="c4c15-159">If the signature doesn't match, no changes are applied to the device.</span></span>

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a><span data-ttu-id="c4c15-160">在 Surface UEFI 中啟用或停用具有 SEMM 的裝置</span><span class="sxs-lookup"><span data-stu-id="c4c15-160">Enable or disable devices in Surface UEFI with SEMM</span></span>

<span data-ttu-id="c4c15-161">下列清單顯示您可以在 SEMM 中管理的所有可用裝置：</span><span class="sxs-lookup"><span data-stu-id="c4c15-161">The following list shows all the available devices that you can manage in SEMM:</span></span>

- <span data-ttu-id="c4c15-162">固定 USB 埠</span><span class="sxs-lookup"><span data-stu-id="c4c15-162">Docking USB port</span></span>
- <span data-ttu-id="c4c15-163">板載音訊</span><span class="sxs-lookup"><span data-stu-id="c4c15-163">On-board audio</span></span>
- <span data-ttu-id="c4c15-164">數位圖形處理單元</span><span class="sxs-lookup"><span data-stu-id="c4c15-164">Digital graphics processing unit</span></span>
- <span data-ttu-id="c4c15-165">類型保護蓋</span><span class="sxs-lookup"><span data-stu-id="c4c15-165">Type cover</span></span>
- <span data-ttu-id="c4c15-166">Micro SD 卡片</span><span class="sxs-lookup"><span data-stu-id="c4c15-166">Micro SD card</span></span>
- <span data-ttu-id="c4c15-167">前方相機</span><span class="sxs-lookup"><span data-stu-id="c4c15-167">Front camera</span></span>
- <span data-ttu-id="c4c15-168">後方相機</span><span class="sxs-lookup"><span data-stu-id="c4c15-168">Rear camera</span></span>
- <span data-ttu-id="c4c15-169">您好 (的Windows相機) </span><span class="sxs-lookup"><span data-stu-id="c4c15-169">Infrared camera (for Windows Hello)</span></span>
- <span data-ttu-id="c4c15-170">藍牙只</span><span class="sxs-lookup"><span data-stu-id="c4c15-170">Bluetooth only</span></span>
- <span data-ttu-id="c4c15-171">無線網路和藍牙</span><span class="sxs-lookup"><span data-stu-id="c4c15-171">Wireless network and Bluetooth</span></span>
- <span data-ttu-id="c4c15-172">LTE (長期) </span><span class="sxs-lookup"><span data-stu-id="c4c15-172">Long-term evolution (LTE)</span></span>

 >[!NOTE]
><span data-ttu-id="c4c15-173">在 UEFI 裝置頁面上，內建裝置可能會根據您的裝置或公司環境而不同。</span><span class="sxs-lookup"><span data-stu-id="c4c15-173">On the UEFI Devices page, the built-in devices might vary, depending on your device or corporate environment.</span></span> <span data-ttu-id="c4c15-174">例如，X 版不支援 UEFI 裝置Surface Pro頁面;LTE 只會顯示在配備 LTE 的裝置上。</span><span class="sxs-lookup"><span data-stu-id="c4c15-174">For example, the UEFI Devices page isn't supported on Surface Pro X; LTE appears only on LTE-equipped devices.</span></span> 
### <a name="configure-advanced-settings-with-semm"></a><span data-ttu-id="c4c15-175">使用 SEMM 設定進位設定</span><span class="sxs-lookup"><span data-stu-id="c4c15-175">Configure advanced settings with SEMM</span></span>
**<span data-ttu-id="c4c15-176">表 1.</span><span class="sxs-lookup"><span data-stu-id="c4c15-176">Table 1.</span></span> <span data-ttu-id="c4c15-177">進階設定</span><span class="sxs-lookup"><span data-stu-id="c4c15-177">Advanced settings</span></span>**

| <span data-ttu-id="c4c15-178">設定</span><span class="sxs-lookup"><span data-stu-id="c4c15-178">Setting</span></span>                            | <span data-ttu-id="c4c15-179">說明</span><span class="sxs-lookup"><span data-stu-id="c4c15-179">Description</span></span>                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="c4c15-180">適用於 PXE 開機 的 IPv6</span><span class="sxs-lookup"><span data-stu-id="c4c15-180">IPv6 for PXE Boot</span></span>                  | <span data-ttu-id="c4c15-181">可讓您管理 PXE 啟動的 IPv6 支援。</span><span class="sxs-lookup"><span data-stu-id="c4c15-181">Allows you to manage IPv6 support for PXE boot.</span></span> <span data-ttu-id="c4c15-182">如果您沒有設定此設定，PXE 啟動的 IPv6 支援會停用。</span><span class="sxs-lookup"><span data-stu-id="c4c15-182">If you don't configure this setting, IPv6 support for PXE boot is disabled.</span></span>                                                                               |
| <span data-ttu-id="c4c15-183">替代開機</span><span class="sxs-lookup"><span data-stu-id="c4c15-183">Alternate Boot</span></span>                     | <span data-ttu-id="c4c15-184">可讓您在啟動期間同步選取降低音量按鈕和 Power 按鈕，管理使用備用啟動順序以直接引導至 USB 或乙太網路裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-184">Allows you to manage the use of an Alternate boot order to boot directly to a USB or Ethernet device by pressing both the Volume Down button and Power button during boot.</span></span> <span data-ttu-id="c4c15-185">如果您沒有設定此設定，系統即會啟用備用啟動。</span><span class="sxs-lookup"><span data-stu-id="c4c15-185">If you don't configure this setting, Alternate boot is enabled.</span></span> |
| <span data-ttu-id="c4c15-186">開機順序鎖定</span><span class="sxs-lookup"><span data-stu-id="c4c15-186">Boot Order Lock</span></span>                    | <span data-ttu-id="c4c15-187">可讓您鎖定啟動順序，以防止變更。</span><span class="sxs-lookup"><span data-stu-id="c4c15-187">Allows you to lock the boot order to prevent changes.</span></span> <span data-ttu-id="c4c15-188">如果您沒有設定此設定，則啟動順序鎖定會停用。</span><span class="sxs-lookup"><span data-stu-id="c4c15-188">If you don't configure this setting, Boot Order Lock is disabled.</span></span>                                                                                                        |
| <span data-ttu-id="c4c15-189">USB 開機</span><span class="sxs-lookup"><span data-stu-id="c4c15-189">USB Boot</span></span>                           | <span data-ttu-id="c4c15-190">可讓您管理啟動至 USB 裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-190">Allows you to manage booting to USB devices.</span></span> <span data-ttu-id="c4c15-191">如果您沒有設定此設定，即會啟用 USB 啟動。</span><span class="sxs-lookup"><span data-stu-id="c4c15-191">If you don't configure this setting, USB Boot is enabled.</span></span>                                                                                                                 |
| <span data-ttu-id="c4c15-192">網路堆疊</span><span class="sxs-lookup"><span data-stu-id="c4c15-192">Network Stack</span></span>                      | <span data-ttu-id="c4c15-193">可讓您管理網路堆疊啟動設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-193">Allows you to manage Network Stack boot settings.</span></span> <span data-ttu-id="c4c15-194">如果您沒有設定此設定，則管理網路堆疊啟動設定的能力會停用。</span><span class="sxs-lookup"><span data-stu-id="c4c15-194">If you don't configure this setting,  the ability to manage Network Stack boot settings is disabled.</span></span>                                                                                                           |
| <span data-ttu-id="c4c15-195">自動上電</span><span class="sxs-lookup"><span data-stu-id="c4c15-195">Auto Power On</span></span>                      | <span data-ttu-id="c4c15-196">可讓您管理自動開機設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-196">Allows you to manage Auto Power On boot settings.</span></span> <span data-ttu-id="c4c15-197">如果您沒有設定此設定，即會啟用自動電源。</span><span class="sxs-lookup"><span data-stu-id="c4c15-197">If you don't configure this setting, Auto Power on is enabled.</span></span>                                                                                                        |
| <span data-ttu-id="c4c15-198">同時使用 SMT (執行緒) </span><span class="sxs-lookup"><span data-stu-id="c4c15-198">Simultaneous Multi-Threading (SMT)</span></span> | <span data-ttu-id="c4c15-199">可讓您管理 SMT 的同步多執行緒 (，) 啟用或停用超執行緒。</span><span class="sxs-lookup"><span data-stu-id="c4c15-199">Allows you to manage Simultaneous Multi-Threading (SMT) to enable or disable hyperthreading.</span></span> <span data-ttu-id="c4c15-200">如果您沒有設定此設定，SMT 會啟用。</span><span class="sxs-lookup"><span data-stu-id="c4c15-200">If you don't configure this setting, SMT is enabled.</span></span>                                                  |
|<span data-ttu-id="c4c15-201">啟用電池限制</span><span class="sxs-lookup"><span data-stu-id="c4c15-201">Enable Battery limit</span></span>| <span data-ttu-id="c4c15-202">可讓您管理電池限制功能。</span><span class="sxs-lookup"><span data-stu-id="c4c15-202">Allows you to manage Battery limit functionality.</span></span> <span data-ttu-id="c4c15-203">如果您沒有設定此設定，則啟用電池限制</span><span class="sxs-lookup"><span data-stu-id="c4c15-203">If you don't configure this setting, Battery limit is enabled</span></span> |
| <span data-ttu-id="c4c15-204">安全性</span><span class="sxs-lookup"><span data-stu-id="c4c15-204">Security</span></span>                           | <span data-ttu-id="c4c15-205">顯示 Surface UEFI **安全性** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c4c15-205">Displays the Surface UEFI **Security** page.</span></span> <span data-ttu-id="c4c15-206">如果您沒有設定此設定，系統會顯示安全性頁面。</span><span class="sxs-lookup"><span data-stu-id="c4c15-206">If you don't configure this setting, the Security page is displayed.</span></span>                                                                                                                 |
| <span data-ttu-id="c4c15-207">裝置</span><span class="sxs-lookup"><span data-stu-id="c4c15-207">Devices</span></span>                            | <span data-ttu-id="c4c15-208">顯示 Surface UEFI **裝置** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c4c15-208">Displays the Surface UEFI **Devices** page.</span></span> <span data-ttu-id="c4c15-209">如果您沒有設定此設定，會顯示裝置頁面。</span><span class="sxs-lookup"><span data-stu-id="c4c15-209">If you don't configure this setting,  the Devices page is displayed.</span></span>                                                                                                                     |
| <span data-ttu-id="c4c15-210">開機</span><span class="sxs-lookup"><span data-stu-id="c4c15-210">Boot</span></span>                               | <span data-ttu-id="c4c15-211">顯示 Surface UEFI **啟動** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c4c15-211">Displays the Surface UEFI **Boot** page.</span></span> <span data-ttu-id="c4c15-212">如果您沒有設定此設定，系統會顯示啟動頁面。</span><span class="sxs-lookup"><span data-stu-id="c4c15-212">If you don't configure this setting, the Boot page is displayed.</span></span>                                                                                                                                                            |
| <span data-ttu-id="c4c15-213">DateTime</span><span class="sxs-lookup"><span data-stu-id="c4c15-213">DateTime</span></span>                           | <span data-ttu-id="c4c15-214">顯示 Surface UEFI **DateTime** 頁面。</span><span class="sxs-lookup"><span data-stu-id="c4c15-214">Displays the Surface UEFI **DateTime** page.</span></span> <span data-ttu-id="c4c15-215">如果您沒有設定此設定，則會顯示 DateTime 頁面。</span><span class="sxs-lookup"><span data-stu-id="c4c15-215">If you don't configure this setting, the DateTime page is displayed.</span></span>                                                                                                                |
| <span data-ttu-id="c4c15-216">EnableOSMigration</span><span class="sxs-lookup"><span data-stu-id="c4c15-216">EnableOSMigration</span></span>                          | <span data-ttu-id="c4c15-217">可讓您將 2 Surface Hub 2 從 Windows 10 團隊版 Windows 10 專業版或Enterprise。</span><span class="sxs-lookup"><span data-stu-id="c4c15-217">Allows you to migrate Surface Hub 2 from Windows 10 Team to Windows 10 Pro or Enterprise.</span></span> <span data-ttu-id="c4c15-218">如果您沒有設定此設定，Surface Hub 2 個裝置只能執行Windows 10 團隊版作業系統。</span><span class="sxs-lookup"><span data-stu-id="c4c15-218">If you don't configure this setting, Surface Hub 2 devices can run only the Windows 10 Team OS.</span></span> <span data-ttu-id="c4c15-219">注意：Windows 10 團隊版和 Windows 10 專業版/Enterprise 2 無法進行雙Surface Hub啟動。</span><span class="sxs-lookup"><span data-stu-id="c4c15-219">Note: Dual booting between Windows 10 Team and Windows 10 Pro/Enterprise isn't available on Surface Hub 2.</span></span>                                                                                                           |


>[!NOTE]
><span data-ttu-id="c4c15-220">當您建立 SEMM 組組套件時，成功頁面上會顯示兩\*\*\*\* 個字元，如圖 3 所示。</span><span class="sxs-lookup"><span data-stu-id="c4c15-220">When you create a SEMM configuration package, two characters are shown on the **Successful** page, as shown in Figure 3.</span></span>

![憑證指紋顯示](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*<span data-ttu-id="c4c15-222">圖 3.</span><span class="sxs-lookup"><span data-stu-id="c4c15-222">Figure 3.</span></span> <span data-ttu-id="c4c15-223">在成功頁面上顯示憑證指紋的最後兩個字元</span><span class="sxs-lookup"><span data-stu-id="c4c15-223">Display of the last two characters of the certificate thumbprint on the Successful page</span></span>*

<span data-ttu-id="c4c15-224">這些字元是憑證指紋的最後兩個字元，應該寫下或錄製。</span><span class="sxs-lookup"><span data-stu-id="c4c15-224">These characters are the last two characters of the certificate thumbprint and should be written down or recorded.</span></span> <span data-ttu-id="c4c15-225">需要字元才能確認在 Surface 裝置上註冊 SEMM，如圖 4 所示。</span><span class="sxs-lookup"><span data-stu-id="c4c15-225">The characters are required to confirm enrollment in SEMM on a Surface device, as shown in Figure 4.</span></span>

![SEMM 中的註冊確認](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*<span data-ttu-id="c4c15-227">圖 4.</span><span class="sxs-lookup"><span data-stu-id="c4c15-227">Figure 4.</span></span> <span data-ttu-id="c4c15-228">使用 SEMM 憑證指紋在 SEMM 中註冊確認</span><span class="sxs-lookup"><span data-stu-id="c4c15-228">Enrollment confirmation in SEMM with the SEMM certificate thumbprint</span></span>*

>[!NOTE]
><span data-ttu-id="c4c15-229">具有憑證檔案 (.) 許可權的系統管理員，隨時都可以在 CertMgr 中開啟 .pfx 檔案來讀取指紋。</span><span class="sxs-lookup"><span data-stu-id="c4c15-229">Administrators with access to the certificate file (.pfx) can read the thumbprint at any time by opening the .pfx file in CertMgr.</span></span> <span data-ttu-id="c4c15-230">若要使用 CertMgr 來查看指紋：</span><span class="sxs-lookup"><span data-stu-id="c4c15-230">To view the thumbprint with CertMgr:</span></span>
>1. <span data-ttu-id="c4c15-231">選取並按住 (或以滑鼠右鍵) .pfx 檔案，然後選取 [ **開啟**。</span><span class="sxs-lookup"><span data-stu-id="c4c15-231">Select and hold (or right-click) the .pfx file, and then select **Open**.</span></span>
>2. <span data-ttu-id="c4c15-232">在流覽窗格中展開資料夾。</span><span class="sxs-lookup"><span data-stu-id="c4c15-232">In the navigation pane, expand the folder.</span></span>
>3. <span data-ttu-id="c4c15-233">選取 **憑證**。</span><span class="sxs-lookup"><span data-stu-id="c4c15-233">Select **Certificates**.</span></span>
>4. <span data-ttu-id="c4c15-234">在主窗格中，選取並按住 (或以滑鼠右鍵) 您的憑證，然後選取 [ **開啟**。</span><span class="sxs-lookup"><span data-stu-id="c4c15-234">In the main pane, select and hold (or right-click) your certificate, and then select **Open**.</span></span>
>5. <span data-ttu-id="c4c15-235">Select the **Details** tab.</span><span class="sxs-lookup"><span data-stu-id="c4c15-235">Select the **Details** tab.</span></span>
>6. <span data-ttu-id="c4c15-236">在顯示**下拉式功能表\*\*\*\*中，必須**選取所有或**僅**屬性。</span><span class="sxs-lookup"><span data-stu-id="c4c15-236">In the **Show** drop-down menu, **All** or **Properties Only** must be selected.</span></span>
>7. <span data-ttu-id="c4c15-237">選取指紋 **欄位** 。</span><span class="sxs-lookup"><span data-stu-id="c4c15-237">Select the **Thumbprint** field.</span></span>

<span data-ttu-id="c4c15-238">若要在 SEMM 中註冊 Surface 裝置，或從組組套件套用 UEFI 組.msi，在預定的 Surface 裝置上執行具有系統管理許可權的檔案。</span><span class="sxs-lookup"><span data-stu-id="c4c15-238">To enroll a Surface device in SEMM or apply the UEFI configuration from a configuration package, run the .msi file with administrative privileges on the intended Surface device.</span></span> <span data-ttu-id="c4c15-239">您可以使用應用程式部署或作業系統部署技術，例如 Microsoft Endpoint Configuration Manager 或[](https://technet.microsoft.com/library/mt346023) [Microsoft 部署工具組](https://technet.microsoft.com/windows/dn475741)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-239">You can use application deployment or operating system deployment technologies, like [Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt346023) or the [Microsoft Deployment Toolkit](https://technet.microsoft.com/windows/dn475741).</span></span> <span data-ttu-id="c4c15-240">當您在 SEMM 中註冊裝置時，您必須實際出席，以確認裝置上的註冊。</span><span class="sxs-lookup"><span data-stu-id="c4c15-240">When you enroll a device in SEMM, you must be physically present to confirm the enrollment on the device.</span></span> <span data-ttu-id="c4c15-241">當您將群組原則適用于已在 SEMM 中註冊的裝置時，不需要使用者互動。</span><span class="sxs-lookup"><span data-stu-id="c4c15-241">When you apply a configuration to devices that are already enrolled in SEMM, user interaction isn’t required.</span></span>

<span data-ttu-id="c4c15-242">若要逐步瞭解如何在 SEMM 中註冊 Surface 裝置，或在 SEMM 中適用 Surface UEFI 設定，請參閱使用 [SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)註冊及設定 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-242">For a step-by-step walkthrough of how to enroll a Surface device in SEMM or apply a Surface UEFI configuration with SEMM, see [Enroll and configure Surface devices with SEMM](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm).</span></span>

### <a name="reset-package"></a><span data-ttu-id="c4c15-243">重設套件</span><span class="sxs-lookup"><span data-stu-id="c4c15-243">Reset package</span></span>

<span data-ttu-id="c4c15-244">Surface UEFI 重設套件只會用來執行一項工作 ，從 SEMM 取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-244">A Surface UEFI reset package is used to perform only one task — to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="c4c15-245">重設套件包含簽署指示，以從裝置固件移除 SEMM 憑證，以及將 UEFI 設定重設為出廠預設設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-245">The reset package contains signed instructions to remove the SEMM certificate from the device’s firmware and to reset UEFI settings to the factory default settings.</span></span> <span data-ttu-id="c4c15-246">就像 Surface UEFI 設定套件一樣，重設套件必須以 Surface 裝置上所配置的相同 SEMM 憑證簽署。</span><span class="sxs-lookup"><span data-stu-id="c4c15-246">Like a Surface UEFI configuration package, a reset package must be signed with the same SEMM certificate that’s provisioned on the Surface device.</span></span> <span data-ttu-id="c4c15-247">當您建立 SEMM 重設套件時，您必須提供要重設的 Surface 裝置序號。</span><span class="sxs-lookup"><span data-stu-id="c4c15-247">When you create a SEMM reset package, you’re required to supply the serial number of the Surface device that you intend to reset.</span></span> <span data-ttu-id="c4c15-248">SEMM 重設套件並非通用套件，而是特定于一個裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-248">SEMM reset packages aren’t universal — they’re specific to one device.</span></span>

### <a name="recovery-request"></a><span data-ttu-id="c4c15-249">復原要求</span><span class="sxs-lookup"><span data-stu-id="c4c15-249">Recovery request</span></span>

<span data-ttu-id="c4c15-250">在某些情況下，可能無法使用 Surface UEFI 重設套件。</span><span class="sxs-lookup"><span data-stu-id="c4c15-250">In some scenarios, it might be impossible to use a Surface UEFI reset package.</span></span> <span data-ttu-id="c4c15-251"> (例如，如果 Windows 在 Surface 裝置上無法使用。) 在這些情況下，您可以使用修復要求作業，透過 Surface UEFI (的**Enterprise**) 管理頁面，從 SEMM 取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-251">(For example, if Windows becomes unusable on the Surface device.) In these scenarios you can unenroll the Surface device from SEMM through the **Enterprise Management** page of Surface UEFI (shown in Figure 5) with a Recovery Request operation.</span></span>

> [!div class="mx-imgBorder"]
> ![啟動 SEMM 復原要求](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*<span data-ttu-id="c4c15-253">圖 5.</span><span class="sxs-lookup"><span data-stu-id="c4c15-253">Figure 5.</span></span> <span data-ttu-id="c4c15-254">在管理頁面啟動 SEMM Enterprise要求</span><span class="sxs-lookup"><span data-stu-id="c4c15-254">Initiate a SEMM recovery request on the Enterprise Management page</span></span>*

<span data-ttu-id="c4c15-255">當您使用系統管理頁面上**Enterprise**在 Surface 裝置上重設 SEMM 時，系統將會提供重設要求。</span><span class="sxs-lookup"><span data-stu-id="c4c15-255">When you use the process on the **Enterprise Management** page to reset SEMM on a Surface device, you’re given a Reset Request.</span></span> <span data-ttu-id="c4c15-256">此重設要求可以儲存為檔案至 USB 磁碟機、複製為文字，或以 QR 程式碼與行動裝置一起讀取，以輕鬆以電子郵件或訊息進行。</span><span class="sxs-lookup"><span data-stu-id="c4c15-256">This Reset Request can be saved as a file to a USB drive, copied as text, or read as a QR Code with a mobile device to be easily emailed or messaged.</span></span> <span data-ttu-id="c4c15-257">使用 Microsoft Surface UEFI 設定程式重設要求選項來載入重設要求檔案，或輸入重設要求文字或 QR 程式碼。</span><span class="sxs-lookup"><span data-stu-id="c4c15-257">Use the Microsoft Surface UEFI Configurator Reset Request option to load a Reset Request file or to enter the Reset Request text or QR Code.</span></span> <span data-ttu-id="c4c15-258">Microsoft Surface UEFI Configurator 會產生可在 Surface 裝置上輸入的驗證碼。</span><span class="sxs-lookup"><span data-stu-id="c4c15-258">Microsoft Surface UEFI Configurator generates a verification code that can be entered on the Surface device.</span></span> <span data-ttu-id="c4c15-259">如果您在 Surface 裝置上輸入程式碼，然後 **選取重新開機，** 則裝置會從 SEMM 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="c4c15-259">If you enter the code on the Surface device and select **Restart**, the device is unenrolled from SEMM.</span></span> 

>[!NOTE]
><span data-ttu-id="c4c15-260">重設要求會在建立後的兩小時到期。</span><span class="sxs-lookup"><span data-stu-id="c4c15-260">A Reset Request expires two hours after it's created.</span></span>

<span data-ttu-id="c4c15-261">若要逐步瞭解如何從 SEMM 取消註冊 Surface 裝置，請參閱從 [SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)取消註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="c4c15-261">For a step-by-step walkthrough of how to unenroll Surface devices from SEMM, see [Unenroll Surface devices from SEMM](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm).</span></span>

## <a name="surface-enterprise-management-mode-certificate-requirements"></a><span data-ttu-id="c4c15-262">Surface Enterprise管理模式憑證需求</span><span class="sxs-lookup"><span data-stu-id="c4c15-262">Surface Enterprise Management Mode certificate requirements</span></span>
<span data-ttu-id="c4c15-263">當您將 SEMM 與 Microsoft Surface UEFI 設定器一起使用，並想要適用 UEFI 設定時，需要憑證才能驗證組組檔案的簽名。</span><span class="sxs-lookup"><span data-stu-id="c4c15-263">When you use SEMM with Microsoft Surface UEFI Configurator and want to apply UEFI settings, a certificate is required to verify the signature of configuration files.</span></span> <span data-ttu-id="c4c15-264">此憑證可確保在裝置註冊 SEMM 之後，只有使用核准憑證所建立套件才能用來修改 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-264">This certificate ensures that after a device enrolls in SEMM, only packages created with the approved certificate can be used to modify the UEFI settings.</span></span>

>[!NOTE]
><span data-ttu-id="c4c15-265">若要在註冊的 Surface 裝置上對 SEMM 或 Surface UEFI 設定進行任何修改，必須提供 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="c4c15-265">To make any modification to SEMM or Surface UEFI settings on enrolled Surface devices, the SEMM certificate is required.</span></span> <span data-ttu-id="c4c15-266">如果 SEMM 憑證損壞或遺失，無法移除或重設 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c4c15-266">If the SEMM certificate is corrupt or lost, SEMM can’t be removed or reset.</span></span> <span data-ttu-id="c4c15-267">使用適當的備份及復原解決方案管理您的 SEMM 憑證</span><span class="sxs-lookup"><span data-stu-id="c4c15-267">Manage your SEMM certificate accordingly with an appropriate solution for backup and recovery</span></span>

<span data-ttu-id="c4c15-268">使用 Microsoft Surface UEFI Configurator 工具所建立套件會以憑證簽署。</span><span class="sxs-lookup"><span data-stu-id="c4c15-268">Packages created with the Microsoft Surface UEFI Configurator tool are signed with a certificate.</span></span> <span data-ttu-id="c4c15-269">此憑證可確保在裝置註冊 SEMM 之後，只有使用核准憑證建立套件才能用來修改 UEFI 的設定。</span><span class="sxs-lookup"><span data-stu-id="c4c15-269">This certificate ensures that after a device is enrolled in SEMM, only packages created with the approved certificate can be used to modify the settings of UEFI.</span></span> 
### <a name="recommended-certificate-settings"></a><span data-ttu-id="c4c15-270">建議的憑證設定</span><span class="sxs-lookup"><span data-stu-id="c4c15-270">Recommended certificate settings</span></span>
<span data-ttu-id="c4c15-271">SEMM 憑證建議使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="c4c15-271">The following settings are recommended for the SEMM certificate:</span></span>

- <span data-ttu-id="c4c15-272">**金鑰演算法** – RSA</span><span class="sxs-lookup"><span data-stu-id="c4c15-272">**Key Algorithm** – RSA</span></span> 
- <span data-ttu-id="c4c15-273">**金鑰長度** – 2048</span><span class="sxs-lookup"><span data-stu-id="c4c15-273">**Key Length** – 2048</span></span>
- <span data-ttu-id="c4c15-274">**雜湊演算法** – SHA-256</span><span class="sxs-lookup"><span data-stu-id="c4c15-274">**Hash Algorithm** – SHA-256</span></span>
- <span data-ttu-id="c4c15-275">**類型** - SSL Server 驗證</span><span class="sxs-lookup"><span data-stu-id="c4c15-275">**Type** – SSL Server Authentication</span></span>
- <span data-ttu-id="c4c15-276">**金鑰使用量** – 數位簽章、金鑰加密</span><span class="sxs-lookup"><span data-stu-id="c4c15-276">**Key Usage** – Digital signature, Key Encipherment</span></span>
- <span data-ttu-id="c4c15-277">**提供者** – Microsoft 增強版 RSA 和 AES 加密提供者</span><span class="sxs-lookup"><span data-stu-id="c4c15-277">**Provider** – Microsoft Enhanced RSA and AES Cryptographic Provider</span></span>
- <span data-ttu-id="c4c15-278">**到期日** – 自建立憑證起 15 個月</span><span class="sxs-lookup"><span data-stu-id="c4c15-278">**Expiration Date** – 15 Months from certificate creation</span></span>
- <span data-ttu-id="c4c15-279">**金鑰匯出政策** – 可匯出</span><span class="sxs-lookup"><span data-stu-id="c4c15-279">**Key Export Policy** – Exportable</span></span>

<span data-ttu-id="c4c15-280">此外，建議在兩層公用金鑰基礎結構 (PKI) 架構中驗證 SEMM 憑證，其中中間憑證授權單位 (CA) 專門負責 SEMM，啟用憑證撤銷。</span><span class="sxs-lookup"><span data-stu-id="c4c15-280">It's also recommended that the SEMM certificate be authenticated in a two-tier public key infrastructure (PKI) architecture where the intermediate certification authority (CA) is dedicated to SEMM, enabling certificate revocation.</span></span> <span data-ttu-id="c4c15-281">有關雙層級 PKI 組的資訊，請參閱測試實驗室指南：部署 [AD CS Two-Tier PKI 階層](https://technet.microsoft.com/library/hh831348)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-281">For more information about a two-tier PKI configuration, see [Test Lab Guide: Deploying an AD CS Two-Tier PKI Hierarchy](https://technet.microsoft.com/library/hh831348).</span></span>

### <a name="self-signed-certificate"></a><span data-ttu-id="c4c15-282">自我簽署憑證</span><span class="sxs-lookup"><span data-stu-id="c4c15-282">Self-signed certificate</span></span> 
<span data-ttu-id="c4c15-283">您可以使用下列範例 PowerShell 腳本建立自我簽署憑證，以用於概念證明案例。</span><span class="sxs-lookup"><span data-stu-id="c4c15-283">You can use the following example PowerShell script to create a self-signed certificate for use in proof-of-concept scenarios.</span></span>
<span data-ttu-id="c4c15-284">若要使用此腳本，請複製下列文字至 記事本，然後將檔案儲存為 PowerShell 腳本 (.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="c4c15-284">To use this script, copy the following text into Notepad, and then save the file as a PowerShell script (.ps1).</span></span> 

> [!NOTE]
> <span data-ttu-id="c4c15-285">此腳本會建立具有 密碼的憑證 `12345678` 。</span><span class="sxs-lookup"><span data-stu-id="c4c15-285">This script creates a certificate with a password of `12345678`.</span></span> <span data-ttu-id="c4c15-286">此腳本產生的憑證不建議用於生產環境。</span><span class="sxs-lookup"><span data-stu-id="c4c15-286">The certificate generated by this script isn't recommended for production environments.</span></span>
  
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
><span data-ttu-id="c4c15-287">為了與 SEMM 和 Microsoft Surface UEFI Configurator 一起使用，憑證必須以私密金鑰和密碼保護方式匯出。</span><span class="sxs-lookup"><span data-stu-id="c4c15-287">For use with SEMM and Microsoft Surface UEFI Configurator, the certificate must be exported with the private key and with password protection.</span></span> <span data-ttu-id="c4c15-288">Microsoft Surface UEFI Configurator 會提示您選取 SEMM 憑證檔案 (.pfx) 和憑證密碼。</span><span class="sxs-lookup"><span data-stu-id="c4c15-288">Microsoft Surface UEFI Configurator prompts you to select the SEMM certificate file (.pfx) and certificate password.</span></span>

<span data-ttu-id="c4c15-289">若要建立自我簽署的憑證：</span><span class="sxs-lookup"><span data-stu-id="c4c15-289">To create a self-signed certificate:</span></span>
1.  <span data-ttu-id="c4c15-290">在 C：磁碟機上，建立要儲存腳本的資料夾;例如，C：\SEMM。</span><span class="sxs-lookup"><span data-stu-id="c4c15-290">On your C: drive, create the folder where you'll save the script; for example, C:\SEMM.</span></span>
2.  <span data-ttu-id="c4c15-291">將範例腳本複製到記事本 (或同等) 編輯器中，然後將檔案儲存為 PowerShell 腳本 (.ps1) 。</span><span class="sxs-lookup"><span data-stu-id="c4c15-291">Copy the example script into Notepad (or equivalent text editor), and then save the file as a PowerShell script (.ps1).</span></span>
3.  <span data-ttu-id="c4c15-292">使用系統管理員認證來登錄您的電腦，然後開啟提升的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="c4c15-292">Sign in to your computer with administrator credentials, and then open an elevated PowerShell session.</span></span>
4.  <span data-ttu-id="c4c15-293">請確定您的許可權已設定為允許腳本執行。</span><span class="sxs-lookup"><span data-stu-id="c4c15-293">Make sure that your permissions are set to allow scripts to run.</span></span> <span data-ttu-id="c4c15-294">根據預設，除非您修改執行策略，否則腳本會禁止執行。</span><span class="sxs-lookup"><span data-stu-id="c4c15-294">By default, scripts are blocked from running unless you modify the execution policy.</span></span> <span data-ttu-id="c4c15-295">若要深入瞭解，請參閱 [關於執行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-295">To learn more, see [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies).</span></span>
5.  <span data-ttu-id="c4c15-296">在命令提示符中，輸入腳本的完整路徑，然後按**Enter。**</span><span class="sxs-lookup"><span data-stu-id="c4c15-296">At the command prompt, enter the full path of the script and then press **Enter**.</span></span> <span data-ttu-id="c4c15-297">腳本會建立名為 TempOwner.pfx 的示範憑證。</span><span class="sxs-lookup"><span data-stu-id="c4c15-297">The script creates a Demo Certificate named TempOwner.pfx.</span></span>

<span data-ttu-id="c4c15-298">或者，您可以使用 PowerShell 建立自己的自我簽署憑證。</span><span class="sxs-lookup"><span data-stu-id="c4c15-298">Alternatively, you can create your own self-signed certificate using PowerShell.</span></span> <span data-ttu-id="c4c15-299">詳細資訊，請參閱 [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)。</span><span class="sxs-lookup"><span data-stu-id="c4c15-299">For more information, see [New-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate).</span></span>

>[!NOTE]
><span data-ttu-id="c4c15-300">針對在 PKI 基礎結構中使用離線根目錄的組織，Microsoft Surface UEFI Configurator 必須在連線至根 CA 的環境中執行，以驗證 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="c4c15-300">For organizations that use an offline root in their PKI infrastructure, Microsoft Surface UEFI Configurator must be run in an environment connected to the root CA to authenticate the SEMM certificate.</span></span> <span data-ttu-id="c4c15-301">Microsoft Surface UEFI Configurator 產生的套件可以以檔案方式傳輸，以便以可移除的儲存空間 ，例如 USB 記憶棒等，在離線網路環境外傳輸。</span><span class="sxs-lookup"><span data-stu-id="c4c15-301">The packages generated by Microsoft Surface UEFI Configurator can be transferred as files, so they can be transferred outside the offline network environment with removable storage, such as a USB stick.</span></span>

### <a name="managing-certificates-faq"></a><span data-ttu-id="c4c15-302">管理憑證常見問題</span><span class="sxs-lookup"><span data-stu-id="c4c15-302">Managing certificates FAQ</span></span>

<span data-ttu-id="c4c15-303">建議的最小 *長度* 為 15 個月。</span><span class="sxs-lookup"><span data-stu-id="c4c15-303">The recommended *minimum* length is 15 months.</span></span> <span data-ttu-id="c4c15-304">您可以使用在 15 個月內到期的憑證，或使用超過 15 個月的憑證。</span><span class="sxs-lookup"><span data-stu-id="c4c15-304">You can use a certificate that expires in less than 15 months or use a certificate that expires in longer than 15 months.</span></span>

>[!NOTE] 
><span data-ttu-id="c4c15-305">憑證到期時，它不會自動續約。</span><span class="sxs-lookup"><span data-stu-id="c4c15-305">When a certificate expires, it doesn't automatically renew.</span></span> 

**<span data-ttu-id="c4c15-306">過期的憑證會影響 SEMM 註冊的裝置功能嗎？</span><span class="sxs-lookup"><span data-stu-id="c4c15-306">Will an expired certificate affect the functionality of SEMM-enrolled devices?</span></span>**<br><br>
<span data-ttu-id="c4c15-307">否，憑證只會影響 SEMM 中的 IT 系統管理員管理工作，且在到期時不會影響裝置功能。</span><span class="sxs-lookup"><span data-stu-id="c4c15-307">No, a certificate only impacts IT admin management tasks in SEMM and has no effect on device functionality when it expires.</span></span>

**<span data-ttu-id="c4c15-308">需要在所有擁有 SEMM 套件和憑證的機器上更新嗎？</span><span class="sxs-lookup"><span data-stu-id="c4c15-308">Will the SEMM package and certificate need to be updated on all machines that have it?</span></span>**<br><br>
<span data-ttu-id="c4c15-309">如果您希望 SEMM 重設或復原能夠生效，憑證必須有效且不會過期。</span><span class="sxs-lookup"><span data-stu-id="c4c15-309">If you want SEMM reset or recovery to work, the certificate needs to be valid and not expired.</span></span> 

**<span data-ttu-id="c4c15-310">可以針對我們訂購的每個曲面建立大量重設套件嗎？</span><span class="sxs-lookup"><span data-stu-id="c4c15-310">Can bulk reset packages be created for each surface that we order?</span></span> <span data-ttu-id="c4c15-311">可以建立可重設環境中所有電腦之機器的建立嗎？</span><span class="sxs-lookup"><span data-stu-id="c4c15-311">Can one be built that resets all machines in our environment?</span></span>**<br><br>
<span data-ttu-id="c4c15-312">為特定裝置類型建立設定套件的 PowerShell 範例，也可以用來建立與序列值無關的重設套件。</span><span class="sxs-lookup"><span data-stu-id="c4c15-312">The PowerShell samples that create a config package for a specific device type can also be used to create a reset package that's serial-number independent.</span></span> <span data-ttu-id="c4c15-313">如果憑證仍然有效，您可以使用 PowerShell 建立重設套件來重設 SEMM。</span><span class="sxs-lookup"><span data-stu-id="c4c15-313">If the certificate is still valid, you can create a reset package using PowerShell to reset SEMM.</span></span>

## <a name="version-history"></a><span data-ttu-id="c4c15-314">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="c4c15-314">Version history</span></span>


### <a name="version-2831390"></a><span data-ttu-id="c4c15-315">版本 2.83.139.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-315">Version 2.83.139.0</span></span>

<span data-ttu-id="c4c15-316">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-316">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-317">支援 Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="c4c15-317">Support for Surface Laptop 4</span></span>
- <span data-ttu-id="c4c15-318">支援 7 月 7 日同時Surface Pro選項</span><span class="sxs-lookup"><span data-stu-id="c4c15-318">Support for simultaneous multithreading option for Surface Pro 7</span></span>
- <span data-ttu-id="c4c15-319">移除過時的 SEMM 設定</span><span class="sxs-lookup"><span data-stu-id="c4c15-319">Removal of obsolete SEMM settings</span></span>  
- <span data-ttu-id="c4c15-320">改良 MSI 簽名</span><span class="sxs-lookup"><span data-stu-id="c4c15-320">Improved MSI signing</span></span> 

### <a name="version-2791390"></a><span data-ttu-id="c4c15-321">版本 2.79.139.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-321">Version 2.79.139.0</span></span>

<span data-ttu-id="c4c15-322">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-322">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-323">支援 Surface Pro 7+。</span><span class="sxs-lookup"><span data-stu-id="c4c15-323">Support for Surface Pro 7+.</span></span>
- <span data-ttu-id="c4c15-324">使用者體驗改良功能。</span><span class="sxs-lookup"><span data-stu-id="c4c15-324">User experience improvements.</span></span>

### <a name="version-2781390"></a><span data-ttu-id="c4c15-325">版本 2.78.139.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-325">Version 2.78.139.0</span></span>

<span data-ttu-id="c4c15-326">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-326">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-327">支援使用 Surface Laptop X Surface Pro功能。</span><span class="sxs-lookup"><span data-stu-id="c4c15-327">Support for Surface Laptop Go and Surface Pro X.</span></span>
- <span data-ttu-id="c4c15-328">新版本版本的通知。</span><span class="sxs-lookup"><span data-stu-id="c4c15-328">Notifications for new version releases.</span></span>
- <span data-ttu-id="c4c15-329">建立自訂套件以變更擁有權的能力。</span><span class="sxs-lookup"><span data-stu-id="c4c15-329">The ability to create custom packages to change ownership.</span></span>
- <span data-ttu-id="c4c15-330">錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="c4c15-330">Bug fixes.</span></span>

### <a name="version-2731360"></a><span data-ttu-id="c4c15-331">版本 2.73.136.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-331">Version 2.73.136.0</span></span>

<span data-ttu-id="c4c15-332">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-332">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-333">使用 SEMM 在 Surface Hub2S 上停用音訊的能力。</span><span class="sxs-lookup"><span data-stu-id="c4c15-333">The ability for audio to be disabled on Surface Hub2S using SEMM.</span></span>
- <span data-ttu-id="c4c15-334">支援適用于 Dock Surface Pro X 的 X。</span><span class="sxs-lookup"><span data-stu-id="c4c15-334">Support for Surface Pro X for Dock 2.</span></span>
- <span data-ttu-id="c4c15-335">支援 Dock 2 相關作業的 UEFI Manager。</span><span class="sxs-lookup"><span data-stu-id="c4c15-335">Support for UEFI Manager for Dock 2-related operations.</span></span>
- <span data-ttu-id="c4c15-336">Surface Go 重設套件錯誤修正程式。</span><span class="sxs-lookup"><span data-stu-id="c4c15-336">A Surface Go reset package bug fix.</span></span>
- <span data-ttu-id="c4c15-337">支援將 2 Surface Hub 從作業系統移Windows 10 團隊版到 Windows 10 專業版 或 Enterprise。</span><span class="sxs-lookup"><span data-stu-id="c4c15-337">Support for migrating Surface Hub 2 devices from Windows 10 Team OS to Windows 10 Pro or Enterprise.</span></span>

### <a name="version-2711390"></a><span data-ttu-id="c4c15-338">版本 2.71.139.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-338">Version 2.71.139.0</span></span>

<span data-ttu-id="c4c15-339">此版本的 SEMM 新增了 Surface Dock 2 管理功能的支援，Surface Book 3、Surface Laptop 3 和 Surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="c4c15-339">This version of SEMM adds support for Surface Dock 2 management features for Surface Book 3, Surface Laptop 3, and Surface Pro 7.</span></span> <span data-ttu-id="c4c15-340">其中包含：</span><span class="sxs-lookup"><span data-stu-id="c4c15-340">It includes:</span></span>

- <span data-ttu-id="c4c15-341">能夠啟用音訊 (鎖定/解除鎖定) 乙太網路和 USB 埠。</span><span class="sxs-lookup"><span data-stu-id="c4c15-341">The ability to enable audio (lock/unlock), and Ethernet and USB ports.</span></span>
- <span data-ttu-id="c4c15-342">為已驗證和未經驗證的主機建立固定套件的能力。</span><span class="sxs-lookup"><span data-stu-id="c4c15-342">The ability to create dock packages for both authenticated and unauthenticated hosts.</span></span>

### <a name="version-2701300"></a><span data-ttu-id="c4c15-343">版本 2.70.130.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-343">Version 2.70.130.0</span></span>

<span data-ttu-id="c4c15-344">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-344">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-345">支援 Surface Go 2。</span><span class="sxs-lookup"><span data-stu-id="c4c15-345">Support for Surface Go 2.</span></span>
- <span data-ttu-id="c4c15-346">支援 Surface Book 3。</span><span class="sxs-lookup"><span data-stu-id="c4c15-346">Support for Surface Book 3.</span></span>
- <span data-ttu-id="c4c15-347">錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="c4c15-347">Bug fixes.</span></span>

### <a name="version-2591390"></a><span data-ttu-id="c4c15-348">版本 2.59.139.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-348">Version 2.59.139.0</span></span>

<span data-ttu-id="c4c15-349">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-349">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-350">支援 Surface Pro 7 Surface Pro X 和 Surface Laptop 3 13.5" 和 15" 型號的 Intel 處理器。</span><span class="sxs-lookup"><span data-stu-id="c4c15-350">Support for Surface Pro 7, Surface Pro X, and Surface Laptop 3 13.5" and 15" models with Intel processor.</span></span> 
    >[!NOTE]
    ><span data-ttu-id="c4c15-351">Surface Laptop不支援 3 個 15" 的AMD 處理器。</span><span class="sxs-lookup"><span data-stu-id="c4c15-351">Surface Laptop 3 15" AMD processor isn't supported.</span></span>
- <span data-ttu-id="c4c15-352">支援 Power 喚醒功能。</span><span class="sxs-lookup"><span data-stu-id="c4c15-352">Support for the Wake on Power feature.</span></span>

### <a name="version-2541390"></a><span data-ttu-id="c4c15-353">版本 2.54.139.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-353">Version 2.54.139.0</span></span>

<span data-ttu-id="c4c15-354">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-354">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-355">支援 Surface Hub 2S。</span><span class="sxs-lookup"><span data-stu-id="c4c15-355">Support for Surface Hub 2S.</span></span>
- <span data-ttu-id="c4c15-356">錯誤修正。</span><span class="sxs-lookup"><span data-stu-id="c4c15-356">Bug fixes.</span></span>

### <a name="version-2431360"></a><span data-ttu-id="c4c15-357">版本 2.43.136.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-357">Version 2.43.136.0</span></span>

<span data-ttu-id="c4c15-358">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-358">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-359">支援啟用/停用同時多執行緒。</span><span class="sxs-lookup"><span data-stu-id="c4c15-359">Support to enable/disable simultaneous multithreading.</span></span>
- <span data-ttu-id="c4c15-360">針對部分裝置，個別藍牙無線網路和通訊選項。</span><span class="sxs-lookup"><span data-stu-id="c4c15-360">Separate options for wireless networking and Bluetooth for some devices.</span></span>
- <span data-ttu-id="c4c15-361">已移除電池Surface Studio。</span><span class="sxs-lookup"><span data-stu-id="c4c15-361">Battery Limit removed for Surface Studio.</span></span>

### <a name="version-2261360"></a><span data-ttu-id="c4c15-362">版本 2.26.136.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-362">Version 2.26.136.0</span></span>

<span data-ttu-id="c4c15-363">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-363">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-364">支援 Surface Studio 2。</span><span class="sxs-lookup"><span data-stu-id="c4c15-364">Support for Surface Studio 2.</span></span>
- <span data-ttu-id="c4c15-365">電池限制功能。</span><span class="sxs-lookup"><span data-stu-id="c4c15-365">Battery Limit feature.</span></span>

### <a name="version-2211360"></a><span data-ttu-id="c4c15-366">版本 2.21.136.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-366">Version 2.21.136.0</span></span>

<span data-ttu-id="c4c15-367">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-367">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-368">支援 Surface Pro 6。</span><span class="sxs-lookup"><span data-stu-id="c4c15-368">Support for Surface Pro 6.</span></span>
- <span data-ttu-id="c4c15-369">支援 Surface Laptop 2。</span><span class="sxs-lookup"><span data-stu-id="c4c15-369">Support for Surface Laptop 2.</span></span>

### <a name="version-2141360"></a><span data-ttu-id="c4c15-370">版本 2.14.136.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-370">Version 2.14.136.0</span></span>

<span data-ttu-id="c4c15-371">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-371">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-372">支援 Surface Go。</span><span class="sxs-lookup"><span data-stu-id="c4c15-372">Support for Surface Go.</span></span>

### <a name="version-291360"></a><span data-ttu-id="c4c15-373">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-373">Version 2.9.136.0</span></span>

<span data-ttu-id="c4c15-374">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-374">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-375">支援 Surface Book 2。</span><span class="sxs-lookup"><span data-stu-id="c4c15-375">Support for Surface Book 2.</span></span>
- <span data-ttu-id="c4c15-376">支援 LTE Surface Pro LTE。</span><span class="sxs-lookup"><span data-stu-id="c4c15-376">Support for Surface Pro LTE.</span></span>
- <span data-ttu-id="c4c15-377">協助工具改良功能。</span><span class="sxs-lookup"><span data-stu-id="c4c15-377">Accessibility improvements.</span></span>

### <a name="version-10740"></a><span data-ttu-id="c4c15-378">版本 1.0.74.0</span><span class="sxs-lookup"><span data-stu-id="c4c15-378">Version 1.0.74.0</span></span>

<span data-ttu-id="c4c15-379">此版本的 SEMM 包括：</span><span class="sxs-lookup"><span data-stu-id="c4c15-379">This version of SEMM includes:</span></span>

- <span data-ttu-id="c4c15-380">支援Surface Laptop。</span><span class="sxs-lookup"><span data-stu-id="c4c15-380">Support for Surface Laptop.</span></span>
- <span data-ttu-id="c4c15-381">支援Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="c4c15-381">Support for Surface Pro.</span></span>
- <span data-ttu-id="c4c15-382">錯誤修正和一般改良功能。</span><span class="sxs-lookup"><span data-stu-id="c4c15-382">Bug fixes and general improvements.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c4c15-383">相關主題</span><span class="sxs-lookup"><span data-stu-id="c4c15-383">Related topics</span></span>

- [<span data-ttu-id="c4c15-384">使用 SEMM 註冊及設定 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="c4c15-384">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)
- [<span data-ttu-id="c4c15-385">從 SEMM 取消 Surface 裝置的註冊</span><span class="sxs-lookup"><span data-stu-id="c4c15-385">Unenroll Surface devices from SEMM</span></span>](unenroll-surface-devices-from-semm.md)
- [<span data-ttu-id="c4c15-386">使用 SEMM 保護 Surface Dock 2 連接埠的安全</span><span class="sxs-lookup"><span data-stu-id="c4c15-386">Secure Surface Dock 2 ports with SEMM</span></span>](secure-surface-dock-ports-semm.md)
