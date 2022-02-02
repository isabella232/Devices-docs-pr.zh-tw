---
title: 適用於 Surface 裝置的網路喚醒
description: 執行 Windows 10 版本 1607 或更新版本，並使用 Surface 乙太網路介面卡連接到有線網路的 Surface 裝置，能夠從新式待機喚醒 LAN (WOL) 喚醒。
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
ms.date: 11/30/2021
ms.openlocfilehash: eed1cbedea2a39207846301fa6b4f6c2b2f6dd56
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337906"
---
# <a name="wake-on-lan-for-surface-devices"></a>適用於 Surface 裝置的網路喚醒 

執行 Windows 10 版本 1607 或更新版本的 Surface 裝置，能夠從新式備用裝置 () 也稱為已連接待命裝置喚醒 LAN (WOL) 。 IT 系統管理員可以使用 WOL 遠端喚醒裝置，並自動使用 Microsoft 端點管理員或協力廠商解決方案執行管理工作。

>[!NOTE]
>若要支援 WOL，Surface 裝置必須插入 AC 電源，並使用已連接到有線網路的 Surface 乙太網路介面卡。

## <a name="supported-devices"></a>支援的裝置

支援 WOL 的乙太網路介面卡：

- Surface USB 3.0 Gb 乙太網路介面卡 
- Surface 乙太網路介面卡
- Surface USB-C 到乙太網路和 USB 介面卡
- Surface 擴充座
- Surface Dock 2
- 適用于 3 的 Surface 固定Surface Pro座

支援 WOL 的 Surface 裝置：

- Surface 3
- Surface Pro 3
- Surface Pro 4
- Surface Pro (第 5 代) 
- Surface Pro (LTE Advanced) 第 5 代
- Surface Book (代) 
- Surface Laptop (代) 
- Surface Pro 6
- Surface Book 2
- Surface Go (代) 
- Surface Studio 2 (請參閱Surface Studio下方 2) 
- Surface Pro 7
- Surface Pro 7+
- Surface Pro 8
- Surface Laptop Go
- Surface Laptop工作室


## <a name="using-wol"></a>使用 WOL 

不使用時，Surface 裝置會進入空閒、低電源狀態，稱為新式備用或已連接備用。 IT 系統管理員可以使用喚醒要求 (魔術封包) 遠端觸發裝置，其中包含目標 Surface 裝置之媒體存取控制 (MAC) 位址。 目的地網路介面卡 (NIC) 在喚醒裝置之前先將 MAC 位址與自己的位址進行比較。 如果魔術封包喚醒要求中的 MAC 位址與目的地 NIC 上的 MAC 位址不相符，則 NIC 不會喚醒裝置。 若要深入瞭解，請參閱 [喚醒來原始檔案](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

## <a name="modern-standby"></a>新式備用

當使用者導致系統進入睡眠狀態，或裝置根據使用者設定Windows進入睡眠狀態時，即會啟動新式備用狀態。 例如，使用者按下電源按鈕、關閉蓋，或從按鈕的電源按鈕選取 Windows [開始] 功能表。 WOL 預設適用于在版本 1607 或更新版本中執行Windows 10的 Surface 裝置。 除了第 2 個之外，Surface Studio其他 IT 組Surface Studio。

## <a name="surface-studio-2-instructions"></a>Surface Studio 2 個指示

若要在 2 Surface Studio啟用 WOL，您必須使用下列程式

1. 開啟登錄編輯程式 (**StartSearch** ** **  > regedit.exe >  **) **並建立下列登錄機碼：

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   ```

2. 執行下列命令

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

> [!NOTE]
> 如果您升級 Windows 10 2 Surface Studio (上的 Windows 10 版本，例如從 Windows 10 20H2 升級至 21H1) ，您必須再次遵循這些指示才能啟用 WOL。


### <a name="to-wake-from-hibernation-s4-or-shutdown-s5"></a>若要從 S4 中喚醒 (S4) 或關閉 S5 (S5)  

- 針對連接至 Surface Dock 2 的裝置，請參閱 [Surface Dock 2 的 LAN 喚醒](wake-on-lan-surface-dock2.md)
