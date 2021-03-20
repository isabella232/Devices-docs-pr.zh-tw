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
ms.date: 3/19/2021
ms.openlocfilehash: 1fbbf899876d154469d48fa75a179196697205c1
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442155"
---
# <a name="wake-on-lan-for-surface-devices"></a>適用於 Surface 裝置的網路喚醒

使用 Surface 乙太網路介面卡連接到有線網路的 Surface 裝置可以利用從已連接待命 (喚醒 LAN) WOL。 使用 WOL，您可以使用 Microsoft 端點管理員/Microsoft Intune 等管理解決方案，遠端喚醒裝置並自動執行管理工作。

## <a name="wol-supported-devices"></a>支援 WOL 的裝置

- Surface 乙太網路介面卡
- Surface USB-C 到乙太網路和 USB 介面卡
- Surface Dock 2
- Surface Pro 6 及更高版本
- Surface Book (代) 
- Surface Laptop (代代) 
- Surface Go (代) 
- Surface Studio 2 (請參閱) 


## <a name="using-surface-wol"></a>使用 Surface WOL

IT 系統管理員可以使用 LAN 要求喚醒 (包含目的電腦的 MAC 位址的) 封包來觸發裝置。 若要傳送神奇的封包，然後使用 WOL 喚醒裝置，您必須知道目標裝置和乙太網路介面卡的 MAC 位址。 由於魔術封包不使用 IP 網路通訊協定，因此無法使用裝置 IP 位址或 DNS 名稱。

許多管理解決方案 ，例如 Microsoft 端點組組管理員和協力廠商 Microsoft Store 應用程式，都提供 WOL 的內建支援。 請注意，裝置必須處於已 (睡眠模式) 並連接到 AC 電源。 若要深入瞭解使用端點設定管理員喚醒裝置，請參閱在 LAN [上設定喚醒 - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan)。


## <a name="to-check-wol-is-enabled-on-your-device"></a>若要檢查您的裝置上已啟用 WOL

1. 在乙太網路連接裝置上，選取您的網路介面卡，然後 **選取屬性**。

   > [!div class="mx-imgBorder"]
   > ![Surface 乙太網路介面卡](images/surface-ethernet.png)

2. 選取**設定**  >  **進位**。
3. 卷起 **至新式備用 WoL 魔術封包** ，並確保 **已選取啟用** 。

     ![檢查您的裝置上已啟用 WOL](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a>附件：Surface Studio 2

若要在 Surface Studio 2 上啟用 WOL，請使用下列程式。

1. 建立下列登錄機碼：

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. 執行下列命令

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a>深入了解

- [Microsoft Surface USB-C 到乙太網路和 USB 介面卡](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [Surface USB 3.0 Gb 乙太網路介面卡](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
