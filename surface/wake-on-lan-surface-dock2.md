---
title: 使用 Surface Dock 2 的網路喚醒
description: Surface Dock 2 提供 LAN 喚醒和 WOL (的最佳) ，讓系統管理員能夠遠端喚醒裝置並自動執行管理工作。
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
ms.date: 7/02/2021
ms.openlocfilehash: 4a74efb8af776e9805ad3148ea656f0a65d5d09c
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643849"
---
# <a name="wake-on-lan-with-surface-dock-2"></a><span data-ttu-id="d7af2-104">使用 Surface Dock 2 的網路喚醒</span><span class="sxs-lookup"><span data-stu-id="d7af2-104">Wake On LAN with Surface Dock 2</span></span>

<span data-ttu-id="d7af2-105">若要讓裝置保持在最新狀態，IT 系統管理員必須能夠在裝置不在使用時管理裝置，通常是在夜間維護期間。</span><span class="sxs-lookup"><span data-stu-id="d7af2-105">To keep devices fully up to date, IT admins need to be able to manage devices when they’re not in use, typically during nightly maintenance windows.</span></span> <span data-ttu-id="d7af2-106">Surface Dock 2 提供 LAN (WOL) 喚醒的最佳支援，讓系統管理員能夠遠端喚醒裝置，並自動使用 Microsoft 端點管理員 或其他協力廠商解決方案執行管理工作。</span><span class="sxs-lookup"><span data-stu-id="d7af2-106">Surface Dock 2 provides the best support for Wake on LAN (WOL) enabling admins to remotely wake up devices and automatically perform management tasks with Microsoft Endpoint Manager or other third party solutions.</span></span>

## <a name="requirements"></a><span data-ttu-id="d7af2-107">需求</span><span class="sxs-lookup"><span data-stu-id="d7af2-107">Requirements</span></span>

<span data-ttu-id="d7af2-108">裝置必須與 Surface Dock 2 建立有線連接，並持續與 AC Power 保持連接。</span><span class="sxs-lookup"><span data-stu-id="d7af2-108">Devices must have a wired connection with Surface Dock 2 and stay connected to AC Power.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

## <a name="supported-surface-devices"></a><span data-ttu-id="d7af2-110">支援的 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="d7af2-110">Supported Surface devices</span></span>

- <span data-ttu-id="d7af2-111">Surface Laptop 4 (Intel 處理器) </span><span class="sxs-lookup"><span data-stu-id="d7af2-111">Surface Laptop 4 (Intel processors)</span></span>
- <span data-ttu-id="d7af2-112">Surface Laptop 4 (處理器) </span><span class="sxs-lookup"><span data-stu-id="d7af2-112">Surface Laptop 4 (AMD processors)</span></span>
- <span data-ttu-id="d7af2-113">Surface Laptop 3 (Intel 處理器) </span><span class="sxs-lookup"><span data-stu-id="d7af2-113">Surface Laptop 3 (Intel processors)</span></span>
- <span data-ttu-id="d7af2-114">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="d7af2-114">Surface Pro 7+</span></span>
- <span data-ttu-id="d7af2-115">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="d7af2-115">Surface Pro 7</span></span>
- <span data-ttu-id="d7af2-116">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="d7af2-116">Surface Pro X</span></span>
- <span data-ttu-id="d7af2-117">Surface Go 2</span><span class="sxs-lookup"><span data-stu-id="d7af2-117">Surface Go 2</span></span>
- <span data-ttu-id="d7af2-118">Surface Laptop去</span><span class="sxs-lookup"><span data-stu-id="d7af2-118">Surface Laptop Go</span></span>
- <span data-ttu-id="d7af2-119">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="d7af2-119">Surface Book 3</span></span>

<span data-ttu-id="d7af2-120">Surface Dock 2 為下列電源狀態中的裝置提供 WOL 支援：</span><span class="sxs-lookup"><span data-stu-id="d7af2-120">Surface Dock 2 provides WOL support for devices in the following power states:</span></span>

- <span data-ttu-id="d7af2-121">連線待命</span><span class="sxs-lookup"><span data-stu-id="d7af2-121">Connected standby</span></span>
- <span data-ttu-id="d7af2-122">S4 電源 (休眠) </span><span class="sxs-lookup"><span data-stu-id="d7af2-122">Hibernation (S4 power state)</span></span>
- <span data-ttu-id="d7af2-123">關閉 (S5 「柔關閉」電源狀態) </span><span class="sxs-lookup"><span data-stu-id="d7af2-123">Shutdown (S5 “soft off” power state)</span></span>

<span data-ttu-id="d7af2-124">若要深入瞭解電源狀態，請參閱 [系統電源狀態](/windows/win32/power/system-power-states)。</span><span class="sxs-lookup"><span data-stu-id="d7af2-124">To learn more about power states, see [System Power States](/windows/win32/power/system-power-states).</span></span>

## <a name="how-it-works"></a><span data-ttu-id="d7af2-125">運作方式</span><span class="sxs-lookup"><span data-stu-id="d7af2-125">How it works</span></span>

<span data-ttu-id="d7af2-126">不使用時，Surface 裝置會進入空閒、低電源狀態，稱為新式備用或已連接備用。</span><span class="sxs-lookup"><span data-stu-id="d7af2-126">When not in use, Surface devices enter an idle, low powered state known as Modern Standby or Connected Standby.</span></span> <span data-ttu-id="d7af2-127">IT 系統管理員可以使用喚醒要求 (魔術封包) 遠端觸發裝置，其中包含目標 Surface 裝置 (MAC) 位址。</span><span class="sxs-lookup"><span data-stu-id="d7af2-127">IT admins can remotely trigger devices using a wake request (magic packet) that contains the Media Access Control (MAC) address of the target Surface device.</span></span> <span data-ttu-id="d7af2-128">許多管理解決方案 ，Microsoft Endpoint Configuration Manager協力廠商應用程式Microsoft Store提供 WOL 的內建支援。</span><span class="sxs-lookup"><span data-stu-id="d7af2-128">Many management solutions, such as Microsoft Endpoint Configuration Manager and third-party Microsoft Store apps provide built-in support for WOL.</span></span>

<span data-ttu-id="d7af2-129">若要在沒有 Surface Dock 2 的裝置上啟用 WOL，請參閱 Surface [裝置在 LAN 上喚醒](wake-on-lan-for-surface-devices.md)。</span><span class="sxs-lookup"><span data-stu-id="d7af2-129">To enable WOL on devices without Surface Dock 2, see [Wake on LAN for Surface devices](wake-on-lan-for-surface-devices.md).</span></span>

## <a name="learn-more"></a><span data-ttu-id="d7af2-130">深入了解</span><span class="sxs-lookup"><span data-stu-id="d7af2-130">Learn more</span></span>

- [<span data-ttu-id="d7af2-131">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="d7af2-131">Surface Dock 2</span></span>](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [<span data-ttu-id="d7af2-132">適用於 Surface 裝置的網路喚醒</span><span class="sxs-lookup"><span data-stu-id="d7af2-132">Wake On LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)
- [<span data-ttu-id="d7af2-133">系統電源狀態</span><span class="sxs-lookup"><span data-stu-id="d7af2-133">System Power States</span></span>](/windows/win32/power/system-power-states)
- [<span data-ttu-id="d7af2-134">在 LAN 上設定喚醒 - Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="d7af2-134">Configure Wake on LAN - Configuration Manager</span></span>](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)
