---
title: 在 Surface 裝置上喚醒局域網（Surface）
description: 瞭解您可以如何使用 LAN 喚醒來遠端喚醒裝置，以執行管理或維護工作，或自動啟用管理解決方案，即使裝置已斷電也一樣。
keywords: 更新、部署、驅動程式、wol、局域網喚醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831502"
---
# <span data-ttu-id="e920e-104">適用於 Surface 裝置的網路喚醒</span><span class="sxs-lookup"><span data-stu-id="e920e-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="e920e-105">執行 Windows 10 （版本1607（又稱為 Windows 10 年度更新版）或更新版本的 surface 裝置，並使用 Surface 乙太網卡連線至有線網路，就能從連線的待機（WOL）喚醒。</span><span class="sxs-lookup"><span data-stu-id="e920e-105">Surface devices that run Windows 10, version 1607 (also known as Windows 10 Anniversary Update) or later and use a Surface Ethernet adapter to connect to a wired network, are capable of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="e920e-106">有了 WOL，您就可以遠端喚醒裝置來執行管理或維護工作，或自動啟用管理解決方案（例如 Microsoft 端點建構管理員）。</span><span class="sxs-lookup"><span data-stu-id="e920e-106">With WOL, you can remotely wake up devices to perform management or maintenance tasks or enable management solutions (such as Microsoft Endpoint Configuration Manager) automatically.</span></span> <span data-ttu-id="e920e-107">例如，您可以將應用程式部署到與 Surface Dock 或 Surface Pro 3 插接站固定的 Surface 裝置，方法是在夜間辦公室是空的情況下，使用 Microsoft 端點組態管理員。</span><span class="sxs-lookup"><span data-stu-id="e920e-107">For example, you can deploy applications to Surface devices left docked with a Surface Dock or Surface Pro 3 Docking Station by using Microsoft Endpoint Configuration Manager during a window in the middle of the night, when the office is empty.</span></span>

>[!NOTE]
><span data-ttu-id="e920e-108">Surface 裝置必須連線到交流電源，且處於連線的待機（睡眠）以支援 WOL。</span><span class="sxs-lookup"><span data-stu-id="e920e-108">Surface devices must be connected to AC power and in Connected Standby (Sleep) to support WOL.</span></span> <span data-ttu-id="e920e-109">在休眠或關閉的裝置中無法進行 WOL。</span><span class="sxs-lookup"><span data-stu-id="e920e-109">WOL is not possible from devices that are in hibernation or powered off.</span></span>

## <span data-ttu-id="e920e-110">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="e920e-110">Supported devices</span></span>

<span data-ttu-id="e920e-111">WOL 支援下列裝置：</span><span class="sxs-lookup"><span data-stu-id="e920e-111">The following devices are supported for WOL:</span></span>

* <span data-ttu-id="e920e-112">Surface 乙太網卡</span><span class="sxs-lookup"><span data-stu-id="e920e-112">Surface Ethernet adapter</span></span>
* <span data-ttu-id="e920e-113">從 USB 到乙太網路和 USB 配接器的 Surface</span><span class="sxs-lookup"><span data-stu-id="e920e-113">Surface USB-C to Ethernet and USB Adapter</span></span>
* <span data-ttu-id="e920e-114">Surface 擴充座</span><span class="sxs-lookup"><span data-stu-id="e920e-114">Surface Dock</span></span>
* <span data-ttu-id="e920e-115">Surface Pro 3 的 surface 插接站</span><span class="sxs-lookup"><span data-stu-id="e920e-115">Surface Docking Station for Surface Pro 3</span></span>
* <span data-ttu-id="e920e-116">Surface 3</span><span class="sxs-lookup"><span data-stu-id="e920e-116">Surface 3</span></span>
* <span data-ttu-id="e920e-117">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="e920e-117">Surface Pro 3</span></span>
* <span data-ttu-id="e920e-118">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="e920e-118">Surface Pro 4</span></span>
* <span data-ttu-id="e920e-119">Surface Pro （第5代）</span><span class="sxs-lookup"><span data-stu-id="e920e-119">Surface Pro (5th Gen)</span></span>
* <span data-ttu-id="e920e-120">使用 LTE Advanced 的 Surface Pro （第5代）</span><span class="sxs-lookup"><span data-stu-id="e920e-120">Surface Pro (5th Gen) with LTE Advanced</span></span>
* <span data-ttu-id="e920e-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="e920e-121">Surface Book</span></span>
* <span data-ttu-id="e920e-122">Surface 膝上型電腦（第1代）</span><span class="sxs-lookup"><span data-stu-id="e920e-122">Surface Laptop (1st Gen)</span></span>
* <span data-ttu-id="e920e-123">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="e920e-123">Surface Pro 6</span></span>
* <span data-ttu-id="e920e-124">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="e920e-124">Surface Book 2</span></span>
* <span data-ttu-id="e920e-125">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="e920e-125">Surface Laptop 2</span></span>
* <span data-ttu-id="e920e-126">Surface Go</span><span class="sxs-lookup"><span data-stu-id="e920e-126">Surface Go</span></span>
* <span data-ttu-id="e920e-127">配備 LTE Advanced 的 Surface Go</span><span class="sxs-lookup"><span data-stu-id="e920e-127">Surface Go with LTE Advanced</span></span>
* <span data-ttu-id="e920e-128">Surface Studio 2 （請參閱以下的 Surface Studio 2 指示）</span><span class="sxs-lookup"><span data-stu-id="e920e-128">Surface Studio 2 (see Surface Studio 2 instructions below)</span></span>
* <span data-ttu-id="e920e-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="e920e-129">Surface Pro 7</span></span>
* <span data-ttu-id="e920e-130">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="e920e-130">Surface Laptop 3</span></span>

## <span data-ttu-id="e920e-131">WOL 驅動程式</span><span class="sxs-lookup"><span data-stu-id="e920e-131">WOL driver</span></span>

<span data-ttu-id="e920e-132">若要在 Surface 裝置上啟用 WOL 支援，必須有 Surface 乙太網配接器的特定驅動程式。</span><span class="sxs-lookup"><span data-stu-id="e920e-132">To enable WOL support on Surface devices, a specific driver for the Surface Ethernet adapter is required.</span></span> <span data-ttu-id="e920e-133">此驅動程式不包含在 Surface 裝置的標準驅動程式和固件套件中，您必須另行下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="e920e-133">This driver is not included in the standard driver and firmware pack for Surface devices – you must download and install it separately.</span></span> <span data-ttu-id="e920e-134">您可以從 Microsoft 下載中心的 [[表面工具](https://www.microsoft.com/download/details.aspx?id=46703)] 頁面下載 surface WOL 驅動程式（SurfaceWOL.msi）。</span><span class="sxs-lookup"><span data-stu-id="e920e-134">You can download the Surface WOL driver (SurfaceWOL.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>

<span data-ttu-id="e920e-135">您可以在 Surface 裝置上執行這個 Microsoft Windows Installer （.msi）檔案來安裝 Surface WOL 驅動程式，也可以使用應用程式部署方案（例如 Microsoft 端點設定管理員）將它發佈到 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="e920e-135">You can run this Microsoft Windows Installer (.msi) file on a Surface device to install the Surface WOL driver, or you can distribute it to Surface devices with an application deployment solution, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="e920e-136">若要在部署期間包含 Surface WOL 驅動程式，您可以在部署期間將 .msi 檔案安裝為應用程式。</span><span class="sxs-lookup"><span data-stu-id="e920e-136">To include the Surface WOL driver during deployment, you can install the .msi file as an application during the deployment process.</span></span> <span data-ttu-id="e920e-137">您也可以解壓縮 Surface WOL 驅動程式檔案，將它們包含在部署程式中。</span><span class="sxs-lookup"><span data-stu-id="e920e-137">You can also extract the Surface WOL driver files to include them in the deployment process.</span></span> <span data-ttu-id="e920e-138">例如，您可以將它們包含在您的 Microsoft 部署工具箱（MDT）部署共用中。</span><span class="sxs-lookup"><span data-stu-id="e920e-138">For example, you can include them in your Microsoft Deployment Toolkit (MDT) deployment share.</span></span> <span data-ttu-id="e920e-139">您可以在[使用 Microsoft 部署工具組將 Windows 10 部署到 Surface 裝置](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)中，深入瞭解使用 MDT 的 surface 部署。</span><span class="sxs-lookup"><span data-stu-id="e920e-139">You can read more about Surface deployment with MDT in [Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt).</span></span>

> [!NOTE]
> <span data-ttu-id="e920e-140">在安裝 SurfaceWOL.msi 期間，下列登錄機碼會設定為1的值，這可讓您輕鬆識別已安裝 WOL 驅動程式的系統。</span><span class="sxs-lookup"><span data-stu-id="e920e-140">During the installation of SurfaceWOL.msi, the following registry key is set to a value of 1, which allows easy identification of systems where the WOL driver has been installed.</span></span> <span data-ttu-id="e920e-141">如果您選擇在部署期間單獨提取並安裝這些驅動程式，則不會設定此登錄機碼，且必須手動設定或使用腳本進行設定。</span><span class="sxs-lookup"><span data-stu-id="e920e-141">If you chose to extract and install these drivers separately during deployment, this registry key will not be configured and must be configured manually or with a script.</span></span>
> 
> **<span data-ttu-id="e920e-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span><span class="sxs-lookup"><span data-stu-id="e920e-142">HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests</span></span>** 

<span data-ttu-id="e920e-143">若要解壓縮 SurfaceWOL.msi 的內容，請使用 MSIExec 系統管理安裝選項（**/a**），如下列範例所示，將內容解壓縮至 [C:\WOL\] 資料夾：</span><span class="sxs-lookup"><span data-stu-id="e920e-143">To extract the contents of SurfaceWOL.msi, use the MSIExec administrative installation option (**/a**), as shown in the following example, to extract the contents to the C:\WOL\ folder:</span></span>

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## <span data-ttu-id="e920e-144">Surface Studio 2 指示</span><span class="sxs-lookup"><span data-stu-id="e920e-144">Surface Studio 2 instructions</span></span>

<span data-ttu-id="e920e-145">若要在 Surface Studio 2 上啟用 WOL，您必須使用下列程式</span><span class="sxs-lookup"><span data-stu-id="e920e-145">To enable WOL on Surface Studio 2, you must use the following procedure</span></span>

1. <span data-ttu-id="e920e-146">建立下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="e920e-146">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="e920e-147">執行下列命令</span><span class="sxs-lookup"><span data-stu-id="e920e-147">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## <span data-ttu-id="e920e-148">使用 Surface WOL</span><span class="sxs-lookup"><span data-stu-id="e920e-148">Using Surface WOL</span></span>

<span data-ttu-id="e920e-149">Surface WOL 驅動程式會符合 WOL 標準，讓裝置是由稱為幻資料包的特殊網路通訊 woken。</span><span class="sxs-lookup"><span data-stu-id="e920e-149">The Surface WOL driver conforms to the WOL standard, whereby the device is woken by a special network communication known as a magic packet.</span></span> <span data-ttu-id="e920e-150">幻數資料包包含6個位元組的255（或十六進位中的 FF），後接目的電腦之 MAC 位址的16個重複專案。</span><span class="sxs-lookup"><span data-stu-id="e920e-150">The magic packet consists of 6 bytes of 255 (or FF in hexadecimal) followed by 16 repetitions of the target computer’s MAC address.</span></span> <span data-ttu-id="e920e-151">您可以在[維琪百科](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)上進一步瞭解幻資料包和 WOL 標準。</span><span class="sxs-lookup"><span data-stu-id="e920e-151">You can read more about the magic packet and the WOL standard on [Wikipedia](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet).</span></span>

>[!NOTE]
><span data-ttu-id="e920e-152">若要使用 WOL 傳送幻資料包並喚醒裝置，您必須知道目標裝置和乙太網路介面卡的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="e920e-152">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="e920e-153">因為幻資料包不使用 IP 網路通訊協定，所以無法使用裝置的 IP 位址或 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="e920e-153">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="e920e-154">許多管理解決方案（例如建構管理員）提供 WOL 的內建支援。</span><span class="sxs-lookup"><span data-stu-id="e920e-154">Many management solutions, such as Configuration Manager, provide built-in support for WOL.</span></span> <span data-ttu-id="e920e-155">還有許多解決方案，包括 Microsoft Store app、PowerShell 模組、協力廠商應用程式，以及可讓您傳送幻資料包來喚醒裝置的協力廠商管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="e920e-155">There are also many solutions, including Microsoft Store apps, PowerShell modules, third-party applications, and third-party management solutions that allow you to send a magic packet to wake up a device.</span></span> <span data-ttu-id="e920e-156">例如，您可以使用 TechNet [腳本中心] 的 [[局域網喚醒] PowerShell 模組](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4)。</span><span class="sxs-lookup"><span data-stu-id="e920e-156">For example, you can use the [Wake On LAN PowerShell module](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4) from the TechNet Script Center.</span></span> 

>[!NOTE]
><span data-ttu-id="e920e-157">在裝置與幻資料包 woken 之後，如果應用程式不積極地在系統上預防睡眠，或 AllowSystemRequiredPowerRequests 登錄機碼沒有設定為1，裝置就會回到睡眠狀態，這可讓應用程式防止睡眠。</span><span class="sxs-lookup"><span data-stu-id="e920e-157">After a device has been woken up with a magic packet, the device will return to sleep if an application is not actively preventing sleep on the system or if the AllowSystemRequiredPowerRequests registry key is not configured to 1, which allows applications to prevent sleep.</span></span> <span data-ttu-id="e920e-158">如需此登錄機碼的詳細資訊，請參閱本文的 [ [WOL 驅動程式](#wol-driver)] 區段。</span><span class="sxs-lookup"><span data-stu-id="e920e-158">See the [WOL driver](#wol-driver) section of this article for more information about this registry key.</span></span>
