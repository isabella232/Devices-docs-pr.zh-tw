---
title: '電池限制設定 (表面) '
description: 電池計量限制是一種 UEFI 設定，可變更 Surface 裝置電池的充電速度，並可能延長其壽命。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271140"
---
# <span data-ttu-id="b43cb-103">電池限制設定</span><span class="sxs-lookup"><span data-stu-id="b43cb-103">Battery Limit setting</span></span>

<span data-ttu-id="b43cb-104">[電池限制] 選項是 [UEFI] 設定，可變更 Surface 裝置電池的充電方式，並可能延長其壽命。</span><span class="sxs-lookup"><span data-stu-id="b43cb-104">Battery Limit option is a UEFI setting that changes how the Surface device battery is charged and may prolong its longevity.</span></span> <span data-ttu-id="b43cb-105">在裝置持續連接電源的情況下（例如，裝置已整合至 kiosk 解決方案）時，建議使用此設定。</span><span class="sxs-lookup"><span data-stu-id="b43cb-105">This setting is recommended in  cases  in which the device is continuously connected to power, for example when devices are integrated into kiosk solutions.</span></span>  

## <span data-ttu-id="b43cb-106">電池計量限制的運作方式</span><span class="sxs-lookup"><span data-stu-id="b43cb-106">How Battery Limit works</span></span>

<span data-ttu-id="b43cb-107">將裝置設定為電池限制會變更用來為裝置電池充電的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="b43cb-107">Setting the device on Battery Limit changes the protocol for charging the device battery.</span></span> <span data-ttu-id="b43cb-108">啟用電池計量限制後，電池計量將限制在其最大容量的50%。</span><span class="sxs-lookup"><span data-stu-id="b43cb-108">When Battery Limit is enabled, the battery charge will be limited to 50% of its maximum capacity.</span></span> <span data-ttu-id="b43cb-109">Windows 中報告的費用層級會反映此限制。</span><span class="sxs-lookup"><span data-stu-id="b43cb-109">The charge level reported in Windows will reflect this limit.</span></span> <span data-ttu-id="b43cb-110">因此，它會顯示電池計量已計費至50%，且不會超出此限制。</span><span class="sxs-lookup"><span data-stu-id="b43cb-110">Therefore, it will show that the battery is charged up to 50% and will not charge beyond  this limit.</span></span> <span data-ttu-id="b43cb-111">如果您在裝置超過50% 時啟用電池限制，電池圖示會顯示裝置已插入但正在放電，直到裝置達到其最大充電容量的50%。</span><span class="sxs-lookup"><span data-stu-id="b43cb-111">If you enable Battery Limit while the device is above 50% charge, the Battery icon will show that the device is plugged in but discharging until the device reaches 50% of its maximum charge capacity.</span></span>  

## <span data-ttu-id="b43cb-112">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="b43cb-112">Supported devices</span></span>

<span data-ttu-id="b43cb-113">電池限制 UEFI 設定會內置於最新的 Surface 裝置中，包括 Surface Pro 7 +、Surface Pro 7 及 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="b43cb-113">The Battery Limit UEFI setting is built into the latest Surface devices including Surface Pro 7+, Surface Pro 7, and Surface Laptop 3.</span></span> <span data-ttu-id="b43cb-114">較舊的裝置需要 [SURFACE UEFI 固件更新](manage-surface-driver-and-firmware-updates.md)，可透過 Windows update 或透過 [Surface 支援網站](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)上的 MSI 驅動程式和固件套件進行。</span><span class="sxs-lookup"><span data-stu-id="b43cb-114">Earlier devices require a [Surface UEFI firmware update](manage-surface-driver-and-firmware-updates.md), available through Windows Update or via the MSI driver and firmware packages on the [Surface Support site](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface).</span></span> <span data-ttu-id="b43cb-115">針對每個支援的裝置所需的特定 Surface UEFI 版本，核取 [ [啟用 [電池限制]：必須插入長時間的 surface 裝置](https://support.microsoft.com/help/4464941) 。</span><span class="sxs-lookup"><span data-stu-id="b43cb-115">Check [Enable "Battery Limit" for Surface devices that have to be plugged in for extended periods of time](https://support.microsoft.com/help/4464941) for the specific Surface UEFI version required for each supported device.</span></span> 

## <span data-ttu-id="b43cb-116">在 Surface UEFI 中啟用電池計量限制 (Surface Pro 4 及更新版本) </span><span class="sxs-lookup"><span data-stu-id="b43cb-116">Enabling Battery Limit in Surface UEFI (Surface Pro 4 and later)</span></span>

<span data-ttu-id="b43cb-117">您可以在開啟裝置) 時，透過啟動至 Surface UEFI (**電源 + Vol** ，來設定 Surface Uefi 電池限制設定。</span><span class="sxs-lookup"><span data-stu-id="b43cb-117">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="b43cb-118">選擇 [ **啟動**設定]，然後在 [ **高級選項**] 底下，將 [ **啟用電池限制模式]** 切換為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="b43cb-118">Choose **boot configuration**, and then, under **Advanced Options**, toggle **Enable Battery Limit Mode** to **On**.</span></span>  

![電池限制高級選項](images/enable-bl.png) 

## <span data-ttu-id="b43cb-120">在表面移至表面的 [移至 2] 啟用電量限制</span><span class="sxs-lookup"><span data-stu-id="b43cb-120">Enabling battery limit on Surface Go and Surface Go 2</span></span>
<span data-ttu-id="b43cb-121">您可以在開啟裝置) 時，透過啟動至 Surface UEFI (**電源 + Vol** 來設定表面電量限制設定。</span><span class="sxs-lookup"><span data-stu-id="b43cb-121">The Surface Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="b43cb-122">選擇 [ **啟動**設定]，然後在 [ **展臺模式]** 下，將滑杆向右移動以將電池限制設定為 [ **已啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b43cb-122">Choose **boot configuration**, and then, under **Kiosk Mode**, move the slider to the right to set Battery Limit to **Enabled**.</span></span>  

![在 Surface 中轉時的 Kiosk 模式電池計量限制](images/go-batterylimit.png) 

## <span data-ttu-id="b43cb-124">在 Surface UEFI 中啟用電池限制 (Surface Pro 3) </span><span class="sxs-lookup"><span data-stu-id="b43cb-124">Enabling Battery Limit in Surface UEFI (Surface Pro 3)</span></span>

<span data-ttu-id="b43cb-125">您可以在開啟裝置) 時，透過啟動至 Surface UEFI (**電源 + Vol** ，來設定 Surface Uefi 電池限制設定。</span><span class="sxs-lookup"><span data-stu-id="b43cb-125">The Surface UEFI Battery Limit setting can be configured by booting into Surface UEFI (**Power + Vol Up** when turning on the device).</span></span> <span data-ttu-id="b43cb-126">選擇 [ **展臺模式]**，選取 [ **電量限制**]，然後選擇 [ **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b43cb-126">Choose **Kiosk Mode**, select **Battery Limit**, and then choose **Enabled**.</span></span>

![[高級] 選項的螢幕擷取畫面](images/enable-bl-sp3.png) 

![進階選項](images/enable-bl-sp3-2.png) 

## <span data-ttu-id="b43cb-129">使用 [Surface Enterprise 管理] 模式 (SEMM) 或 Surface Pro 3 固件 PowerShell 腳本啟用電池限制</span><span class="sxs-lookup"><span data-stu-id="b43cb-129">Enabling Battery Limit using Surface Enterprise Management Mode (SEMM) or Surface Pro 3 firmware PowerShell scripts</span></span>

<span data-ttu-id="b43cb-130">您也可以透過下列方法，使用表面 UEFI 電池限制：</span><span class="sxs-lookup"><span data-stu-id="b43cb-130">The Surface UEFI battery limit is also available for configuration via the following methods:</span></span>

- <span data-ttu-id="b43cb-131">Surface Pro 4 及更新版本</span><span class="sxs-lookup"><span data-stu-id="b43cb-131">Surface Pro 4 and later</span></span> 
    - [<span data-ttu-id="b43cb-132">Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="b43cb-132">Microsoft Surface UEFI Configurator</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - <span data-ttu-id="b43cb-133">Surface UEFI 管理員 Powershell 腳本在[IT 下載的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中 ( # A0) </span><span class="sxs-lookup"><span data-stu-id="b43cb-133">Surface UEFI Manager Powershell scripts (SEMM_Powershell.zip) in the [Surface Tools for IT downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span>
- <span data-ttu-id="b43cb-134">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="b43cb-134">Surface Pro 3</span></span> 
    - [<span data-ttu-id="b43cb-135">SP3_Firmware_Powershell_Scripts.zip</span><span class="sxs-lookup"><span data-stu-id="b43cb-135">SP3_Firmware_Powershell_Scripts.zip</span></span>](https://www.microsoft.com/download/details.aspx?id=46703)

### <span data-ttu-id="b43cb-136">使用 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="b43cb-136">Using Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="b43cb-137">若要設定電池限制模式，請在 SEMM (Surface Pro 4 及更新) 版本的 [**高級設定**] 設定頁面上，設定 [ **Kiosk 覆蓋**] 設定。</span><span class="sxs-lookup"><span data-stu-id="b43cb-137">To configure Battery Limit mode, set the **Kiosk Overrides** setting on the **Advanced Settings** configuration page in SEMM (Surface Pro 4 and later).</span></span>

![[高級] 設定的螢幕擷取畫面](images/semm-bl.png)

### <span data-ttu-id="b43cb-139">使用 Surface UEFI 管理器 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="b43cb-139">Using Surface UEFI Manager PowerShell scripts</span></span>

<span data-ttu-id="b43cb-140">電池限制功能是透過下列設定加以控制：</span><span class="sxs-lookup"><span data-stu-id="b43cb-140">The battery limit feature is controlled via the following setting:</span></span>  

`407 = Battery Profile`

<span data-ttu-id="b43cb-141">**描述**：電池使用模式的活動管理配置</span><span class="sxs-lookup"><span data-stu-id="b43cb-141">**Description**:  Active management scheme for battery usage pattern</span></span>

<span data-ttu-id="b43cb-142">**預設值**：</span><span class="sxs-lookup"><span data-stu-id="b43cb-142">**Default**:</span></span>  `0` 

<span data-ttu-id="b43cb-143">將此設定為 `1` 以啟用電量限制。</span><span class="sxs-lookup"><span data-stu-id="b43cb-143">Set this to `1` to enable Battery Limit.</span></span>

### <span data-ttu-id="b43cb-144">使用 Surface Pro 3 固件工具</span><span class="sxs-lookup"><span data-stu-id="b43cb-144">Using Surface Pro 3 firmware tools</span></span>

<span data-ttu-id="b43cb-145">電池限制功能是透過下列設定加以控制：</span><span class="sxs-lookup"><span data-stu-id="b43cb-145">The battery limit feature is controlled via the following setting:</span></span>  

<span data-ttu-id="b43cb-146">**名稱**： BatteryLimitEnable</span><span class="sxs-lookup"><span data-stu-id="b43cb-146">**Name**: BatteryLimitEnable</span></span>

<span data-ttu-id="b43cb-147">**描述**： BatteryLimit</span><span class="sxs-lookup"><span data-stu-id="b43cb-147">**Description**:  BatteryLimit</span></span>

<span data-ttu-id="b43cb-148">**目前值**：</span><span class="sxs-lookup"><span data-stu-id="b43cb-148">**Current Value**:</span></span>  `0` 

<span data-ttu-id="b43cb-149">**預設值**：</span><span class="sxs-lookup"><span data-stu-id="b43cb-149">**Default Value**:</span></span> `0`

<span data-ttu-id="b43cb-150">**建議值**：</span><span class="sxs-lookup"><span data-stu-id="b43cb-150">**Proposed Value**:</span></span> `0` 

<span data-ttu-id="b43cb-151">將此設定為 `1` 以啟用電量限制。</span><span class="sxs-lookup"><span data-stu-id="b43cb-151">Set this to `1` to enable Battery Limit.</span></span>

>[!NOTE]
><span data-ttu-id="b43cb-152">若要設定此設定，您必須使用 [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="b43cb-152">To configure this setting, you must use [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> 

