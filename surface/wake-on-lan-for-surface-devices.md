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
# <a name="wake-on-lan-for-surface-devices"></a>適用於 Surface 裝置的網路喚醒

若要讓裝置保持在最新狀態，IT 系統管理員必須能夠在裝置不在使用時管理裝置，通常是在夜間維護期間。 使用 WOL (喚醒) 可讓系統管理員遠端喚醒裝置，並自動使用 Microsoft 端點管理員 或協力廠商解決方案執行管理工作。

## <a name="requirements"></a>需求

裝置必須連接到交流電源，並且與下列其中一個相容的乙太網路介面卡進行有線連接：

- Surface USB 3.0 Gb 乙太網路介面卡
- Surface 乙太網路介面卡
- Surface USB-C 到乙太網路和 USB 介面卡
- Microsoft USB-C 旅遊介面卡中心
- Surface 擴充座
- Surface Dock 2

> [!NOTE]
> Surface Dock 2 提供 LAN 喚醒的最佳支援，而不需要任何其他 IT 組組。 若要深入瞭解，請參閱 Surface [Dock 2 的 LAN 喚醒](wake-on-lan-surface-dock2.md)

## <a name="how-it-works"></a>運作方式

不使用時，Surface 裝置會進入空閒、低電源狀態，稱為新式備用或已連接備用。 IT 系統管理員可以使用喚醒要求 (魔術封包) 遠端觸發裝置，其中包含目標 Surface 裝置之媒體存取控制 (MAC) 位址。 許多管理解決方案 ，Microsoft Endpoint Configuration Manager協力廠商應用程式Microsoft Store提供 WOL 的內建支援。 若要深入瞭解使用端點設定管理員喚醒裝置，請參閱在 LAN [上設定喚醒 - Configuration Manager](/mem/configmgr/core/clients/deploy/configure-wake-on-lan)。

LAN 喚醒支援會因睡眠狀態而異：已連接待命或休眠 (S4 電源狀態) 。

## <a name="connected-standby"></a>已連接待命狀態

根據預設，Windows 10在已連接待命的 Surface 裝置上支援 LAN 喚醒。

### <a name="supported-surface-devices---connected-standby"></a>支援的 Surface 裝置 - 已連接備用裝置

- Surface Laptop 4 (Intel 處理器) 
- Surface Laptop 3 (Intel 處理器) 
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Go 2
- Surface Laptop去
- Surface Book 3

## <a name="hibernation"></a>冬眠

若要將裝置從休眠狀態喚醒，必須透過[Surface Enterprise 管理](surface-enterprise-management-mode.md)模式 (SEMM)  (啟用 UEFI 策略設定，才能連接到 Surface Dock 2) 。

### <a name="supported-surface-devices---hibernation"></a>支援的 Surface 裝置 - 休眠

- Surface Laptop 4 (Intel 處理器) 
- Surface Laptop 3 (Intel 處理器) 
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop去
- Surface Book 3

### <a name="to-enable-wake-on-lan-uefi-setting"></a>若要啟用 LAN UEFI 喚醒設定

若要啟用 LAN UEFI 喚醒設定，您需要將目標裝置註冊到 SEMM、建立組組套件，然後套用套件至裝置。 如需詳細資訊，請參閱：

- [Surface 企業管理模式](surface-enterprise-management-mode.md)
- [使用 SEMM 註冊及設定 Surface 裝置](enroll-and-configure-surface-devices-with-semm.md)

1. 下載並安裝 [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703)。
2. 選取**開始**  >  **組組套件**  >  **建立**  > **+ 憑證保護**。
3. 前往進**位設定，** 將**LAN 喚醒切換到****開啟**。
4. 將套件套用至目標裝置。

    > [!div class="mx-imgBorder"]
    > ![啟用 LAN UEFI 策略設定上的喚醒](images/wol-uefi.png)

## <a name="learn-more"></a>深入了解

- [在 LAN 上喚醒 Surface Dock 2](wake-on-lan-surface-dock2.md)
- [Microsoft Surface USB-C 到乙太網路和 USB 介面卡](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)
- [Surface USB 3.0 Gb 乙太網路介面卡](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
