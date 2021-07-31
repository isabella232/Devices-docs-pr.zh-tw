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
ms.date: 7/30/2021
ms.openlocfilehash: 935cec6eed15b7831bffafdc2078a9cadf2067e2
ms.sourcegitcommit: 6a7f96a497c8749a5997972db139542563769101
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2021
ms.locfileid: "11710577"
---
# <a name="wake-on-lan-with-surface-dock-2"></a>使用 Surface Dock 2 的網路喚醒

若要讓裝置保持在最新狀態，IT 系統管理員必須能夠在裝置不在使用時管理裝置，通常是在夜間維護期間。 Surface Dock 2 提供 LAN 喚醒 (WOL) 的最佳支援，讓系統管理員能夠遠端喚醒 Surface 裝置，並自動使用 Microsoft 端點管理員 或其他協力廠商解決方案執行管理工作。

## <a name="requirements"></a>需求

裝置必須與 Surface Dock 2 建立有線連接，並持續與 AC Power 保持連接。

> [!div class="mx-imgBorder"]
> ![Surface Dock 2](images/surface-dock2-angled.png)

> [!NOTE]
> 喚醒連接到 Surface Dock 2 的裝置不需要使用 Surface Enterprise管理模式 (SEMM) 或啟用任何 UEFI 策略設定。
 
## <a name="supported-surface-devices"></a>支援的 Surface 裝置

- Surface Laptop 4 (Intel 處理器) 
- Surface Laptop 4 (處理器) 
- Surface Laptop 3 (Intel 處理器) 
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop去
- Surface Book 3

Surface Dock 2 為下列電源狀態中的裝置提供 WOL 支援：

- 連線待命
- S4 電源 (休眠) 
- 關閉 (S5 「柔關閉」電源狀態) 

若要深入瞭解電源狀態，請參閱 [系統電源狀態](/windows/win32/power/system-power-states)。

## <a name="how-it-works"></a>運作方式

不使用時，Surface 裝置會進入空閒、低電源狀態，稱為新式備用或已連接備用。 或者，根據裝置上設定 (電源設定) 裝置 (S5) 進入休眠狀態或關機。 IT 系統管理員可以使用喚醒要求 (魔術封包) 遠端觸發裝置，其中包含目標 Surface 裝置 (MAC) 位址。 許多管理解決方案 ，Microsoft Endpoint Configuration Manager協力廠商應用程式Microsoft Store提供 WOL 的內建支援。

若要在沒有 Surface Dock 2 的裝置上啟用 WOL，請參閱：

- [在 SURFACE 裝置上的 LAN 喚醒](wake-on-lan-for-surface-devices.md)

## <a name="learn-more"></a>深入了解

- [Surface Dock 2](https://www.microsoft.com/p/surface-dock-2-for-business/8q4hgc6kbmdq?)
- [適用於 Surface 裝置的網路喚醒](wake-on-lan-for-surface-devices.md)
- [系統電源狀態](/windows/win32/power/system-power-states)

