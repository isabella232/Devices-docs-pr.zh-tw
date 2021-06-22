---
title: 適用於 Surface 裝置的網路喚醒
description: 瞭解如何使用 LAN 喚醒來遠端喚醒裝置，以自動執行管理工作。
keywords: 更新、部署、驅動程式、wol、wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 6/04/2021
ms.openlocfilehash: 83989461ca557d27740252149418056688774d3f
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613795"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="a0c41-104">適用於 Surface 裝置的網路喚醒</span><span class="sxs-lookup"><span data-stu-id="a0c41-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="a0c41-105">若要讓裝置保持在最新狀態，IT 系統管理員必須能夠在裝置不在使用時管理裝置，通常是在夜間維護期間。</span><span class="sxs-lookup"><span data-stu-id="a0c41-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="a0c41-106">使用 WOL (喚醒) 可讓系統管理員遠端喚醒裝置，並自動使用 Microsoft 端點管理員 或協力廠商解決方案執行管理工作。</span><span class="sxs-lookup"><span data-stu-id="a0c41-106">Wake on LAN (WOL) enables admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or third-party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="a0c41-107">需求</span><span class="sxs-lookup"><span data-stu-id="a0c41-107">Requirements</span></span>

<span data-ttu-id="a0c41-108">裝置必須連接到交流電源，並且與下列其中一個相容的乙太網路介面卡進行有線連接：</span><span class="sxs-lookup"><span data-stu-id="a0c41-108">Devices must be connected to AC power and have a wired connection with one of the following compatible Ethernet adapters:</span></span>

- <span data-ttu-id="a0c41-109">Surface USB 3.0 Gb 乙太網路介面卡</span><span class="sxs-lookup"><span data-stu-id="a0c41-109">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>
- <span data-ttu-id="a0c41-110">Surface 乙太網路介面卡</span><span class="sxs-lookup"><span data-stu-id="a0c41-110">Surface Ethernet Adapter</span></span>
- <span data-ttu-id="a0c41-111">Surface USB-C 到乙太網路和 USB 介面卡</span><span class="sxs-lookup"><span data-stu-id="a0c41-111">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="a0c41-112">Microsoft USB-C 旅遊介面卡中心</span><span class="sxs-lookup"><span data-stu-id="a0c41-112">Microsoft USB-C Travel Adapter Hub</span></span>
- <span data-ttu-id="a0c41-113">Surface 擴充座</span><span class="sxs-lookup"><span data-stu-id="a0c41-113">Surface Dock</span></span>
- <span data-ttu-id="a0c41-114">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="a0c41-114">Surface Dock 2</span></span>

> [!NOTE]
> <span data-ttu-id="a0c41-115">Surface Dock 2 提供 LAN 喚醒的最佳支援，而不需要任何其他 IT 組組。</span><span class="sxs-lookup"><span data-stu-id="a0c41-115">Surface Dock 2 provides the best support for Wake on LAN without the need for any additional IT configuration.</span></span> <span data-ttu-id="a0c41-116">若要深入瞭解，請參閱 Surface [Dock 2 的 LAN 喚醒](wake-on-lan-surface-dock2.md)</span><span class="sxs-lookup"><span data-stu-id="a0c41-116">To learn more, see [Wake on LAN for Surface Dock 2](wake-on-lan-surface-dock2.md)</span></span>

## <a name="how-it-works"></a><span data-ttu-id="a0c41-117">運作方式</span><span class="sxs-lookup"><span data-stu-id="a0c41-117">How it works</span></span>

<span data-ttu-id="a0c41-118">不使用時，Surface 裝置會進入空閒、低電源狀態，稱為新式備用或已連接備用。</span><span class="sxs-lookup"><span data-stu-id="a0c41-118">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="a0c41-119">IT 系統管理員可以使用喚醒要求 (魔術封包) 遠端觸發裝置，其中包含目標 Surface 裝置之媒體存取控制 (MAC) 位址。</span><span class="sxs-lookup"><span data-stu-id="a0c41-119">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="a0c41-120">許多管理解決方案 ，Microsoft Endpoint Configuration Manager協力廠商應用程式Microsoft Store提供 WOL 的內建支援。</span><span class="sxs-lookup"><span data-stu-id="a0c41-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="a0c41-121">若要深入瞭解使用端點設定管理員喚醒裝置，請參閱在 LAN [上設定喚醒 - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)。</span><span class="sxs-lookup"><span data-stu-id="a0c41-121">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>

<span data-ttu-id="a0c41-122">LAN 喚醒支援會因睡眠狀態而異：已連接待命或休眠 (S4 電源狀態) 。</span><span class="sxs-lookup"><span data-stu-id="a0c41-122">Support for Wake on LAN varies depending on sleep state:  Connected Standby or Hibernation (S4 power state).</span></span>

## <a name="connected-standby"></a><span data-ttu-id="a0c41-123">已連接待命狀態</span><span class="sxs-lookup"><span data-stu-id="a0c41-123">Connected Standby</span></span>

<span data-ttu-id="a0c41-124">根據預設，Windows 10在已連接待命的 Surface 裝置上支援 LAN 喚醒。</span><span class="sxs-lookup"><span data-stu-id="a0c41-124">By default, Windows 10 supports Wake on LAN for Surface devices in Connected Standby.</span></span>

### <a name="supported-surface-devices---connected-standby"></a><span data-ttu-id="a0c41-125">支援的 Surface 裝置 - 已連接備用裝置</span><span class="sxs-lookup"><span data-stu-id="a0c41-125">Supported Surface devices - Connected Standby</span></span>

- <span data-ttu-id="a0c41-126">Surface Laptop 4 (Intel 處理器) </span><span class="sxs-lookup"><span data-stu-id="a0c41-126">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="a0c41-127">Surface Laptop 3 (Intel 處理器) </span><span class="sxs-lookup"><span data-stu-id="a0c41-127">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="a0c41-128">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="a0c41-128">Surface Pro 7+</span></span>
- <span data-ttu-id="a0c41-129">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="a0c41-129">Surface Pro 7</span></span>
- <span data-ttu-id="a0c41-130">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="a0c41-130">Surface Pro X</span></span>
- <span data-ttu-id="a0c41-131">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="a0c41-131">Surface Go 2</span></span>
- <span data-ttu-id="a0c41-132">Surface Laptop去</span><span class="sxs-lookup"><span data-stu-id="a0c41-132">Surface Laptop Go</span></span>
- <span data-ttu-id="a0c41-133">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="a0c41-133">Surface Book 3</span></span>

## <a name="hibernation"></a><span data-ttu-id="a0c41-134">冬眠</span><span class="sxs-lookup"><span data-stu-id="a0c41-134">Hibernation</span></span>

<span data-ttu-id="a0c41-135">若要將裝置從休眠狀態喚醒，必須透過[Surface Enterprise 管理](surface-enterprise-management-mode.md)模式 (SEMM)  (啟用 UEFI 策略設定，才能連接到 Surface Dock 2) 。</span><span class="sxs-lookup"><span data-stu-id="a0c41-135">To wake devices out of Hibernation requires enabling a UEFI policy setting via [Surface Enterprise Management Mode](surface-enterprise-management-mode.md) (SEMM) (not required for devices connected to Surface Dock 2).</span></span>

### <a name="supported-surface-devices---hibernation"></a><span data-ttu-id="a0c41-136">支援的 Surface 裝置 - 休眠</span><span class="sxs-lookup"><span data-stu-id="a0c41-136">Supported Surface devices - Hibernation</span></span>

- <span data-ttu-id="a0c41-137">Surface Laptop 4 (Intel 處理器) </span><span class="sxs-lookup"><span data-stu-id="a0c41-137">Surface Laptop 4 (Intel processors only)</span></span>
- <span data-ttu-id="a0c41-138">Surface Laptop 3 (Intel 處理器) </span><span class="sxs-lookup"><span data-stu-id="a0c41-138">Surface Laptop 3 (Intel processors only)</span></span>
- <span data-ttu-id="a0c41-139">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="a0c41-139">Surface Pro 7+</span></span>
- <span data-ttu-id="a0c41-140">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="a0c41-140">Surface Pro 7</span></span>
- <span data-ttu-id="a0c41-141">Surface Laptop去</span><span class="sxs-lookup"><span data-stu-id="a0c41-141">Surface Laptop Go</span></span>
- <span data-ttu-id="a0c41-142">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="a0c41-142">Surface Book 3</span></span>

### <a name="to-enable-wake-on-lan-uefi-setting"></a><span data-ttu-id="a0c41-143">若要啟用 LAN UEFI 喚醒設定</span><span class="sxs-lookup"><span data-stu-id="a0c41-143">To enable Wake on LAN UEFI setting</span></span>

<span data-ttu-id="a0c41-144">若要啟用 LAN UEFI 喚醒設定，您需要將目標裝置註冊到 SEMM、建立組組套件，然後套用套件至裝置。</span><span class="sxs-lookup"><span data-stu-id="a0c41-144">To enable the Wake on LAN UEFI setting you need to enroll target devices into SEMM, create a configuration package, and apply the package to the devices.</span></span> <span data-ttu-id="a0c41-145">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="a0c41-145">For more information, refer to:</span></span>

- [<span data-ttu-id="a0c41-146">Surface 企業管理模式</span><span class="sxs-lookup"><span data-stu-id="a0c41-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="a0c41-147">使用 SEMM 註冊及設定 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="a0c41-147">Enroll and configure Surface devices with SEMM</span></span>](enroll-and-configure-surface-devices-with-semm.md)

1. <span data-ttu-id="a0c41-148">下載並安裝 [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="a0c41-148">Download and install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
2. <span data-ttu-id="a0c41-149">選取**開始**  >  **組組套件**  >  **建立**  > **+ 憑證保護**。</span><span class="sxs-lookup"><span data-stu-id="a0c41-149">Select **Start** > **Configuration Package** > **Create** >**+ Certificate Protection**.</span></span>
3. <span data-ttu-id="a0c41-150">前往進**位設定，** 將**LAN 喚醒切換到\*\*\*\*開啟**。</span><span class="sxs-lookup"><span data-stu-id="a0c41-150">Go to **Advanced settings** and switch **Wake on LAN** to **On**.</span></span>
4. <span data-ttu-id="a0c41-151">將套件套用至目標裝置。</span><span class="sxs-lookup"><span data-stu-id="a0c41-151">Apply the package to target devices.</span></span>

    > [!div class="mx-imgBorder"]
    > ![啟用 LAN UEFI 策略設定上的喚醒](images/wol-uefi.png)

## <a name="learn-more"></a><span data-ttu-id="a0c41-153">深入了解</span><span class="sxs-lookup"><span data-stu-id="a0c41-153">Learn more</span></span>

- [<span data-ttu-id="a0c41-154">在 LAN 上喚醒 Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="a0c41-154">Wake on LAN for Surface Dock 2</span></span>](wake-on-lan-surface-dock2.md)
- [<span data-ttu-id="a0c41-155">Microsoft Surface USB-C 到乙太網路和 USB 介面卡</span><span class="sxs-lookup"><span data-stu-id="a0c41-155">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [<span data-ttu-id="a0c41-156">Surface USB 3.0 Gb 乙太網路介面卡</span><span class="sxs-lookup"><span data-stu-id="a0c41-156">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
