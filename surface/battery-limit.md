---
title: 'Surface (設定) '
description: 電池限制是 UEFI 設定，可變更 Surface 裝置電池的充電狀態，並延長電池的使用時間。
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
ms.openlocfilehash: 52e43a1ac14f89f5671b6fad8fc2e1ef49480470
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911838"
---
# <a name="battery-limit-setting"></a>電池限制設定

電池限制選項是 UEFI 設定，可變更 Surface 裝置電池的充電方式，並延長電池的使用時間。 建議在裝置持續連接電源的情況下 ，例如將裝置整合至資訊站解決方案時，使用這項設定。  

## <a name="how-battery-limit-works"></a>電池限制如何運作

在電池限制上設定裝置會變更為裝置電池充電的通訊協定。 啟用電池限制時，電池的充電量會限制為其最大容量的 50%。 系統內報告的費用Windows反映此限制。 因此，它會顯示電池的充電上限為 50%，且不會超出此限制。 如果您在裝置充電超過 50% 時啟用電池限制，則電池圖示會顯示裝置已插入電源但正在卸載，直到裝置達到最大充電容量的 50%。  

## <a name="supported-devices"></a>支援的裝置

電池限制 UEFI 設定內建于最新的 Surface 裝置中，Surface Pro 7+、Surface Pro 7 和 Surface Laptop 3。 較早的裝置需要[Surface UEFI](manage-surface-driver-and-firmware-updates.md)Windows更新，透過更新或 Surface 支援網站的 MSI 驅動程式和[固件套件提供](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)。 針對 [每個支援](https://support.microsoft.com/help/4464941) 裝置所需的特定 Surface UEFI 版本，針對必須插入很長一段時間的 Surface 裝置，檢查啟用「電池限制」。

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-4-and-later"></a>在 Surface UEFI 中啟用電池 (Surface Pro 4及) 

Surface UEFI 電池限制設定可以在開啟裝置時啟動至 Surface UEFI (**Power +Vol Up** 來設定) 。 選擇 **啟動組**式，然後在進步 **選項**下，將 **啟用電池限制模式切換** 為 **開啟**。  

![電池限制進位選項。](images/enable-bl.png)

## <a name="enabling-battery-limit-on-surface-go-and-surface-go-2"></a>啟用 Surface Go 和 Surface Go 2 上的電池限制

Surface 電池限制設定可以在開啟裝置時啟動至 Surface UEFI (**Power +Vol Up** 來) 。 選擇 **啟動設定**，然後在 Kiosk **模式**下，將滑杆移到右側，將電池限制設定為 **啟用**。  

![Surface Go 中的 Kiosk 模式電池限制。](images/go-batterylimit.png)

## <a name="enabling-battery-limit-in-surface-uefi-surface-pro-3"></a>在 Surface UEFI 中啟用電池 (Surface Pro 3) 

Surface UEFI 電池限制設定可以在開啟裝置時啟動至 Surface UEFI (**Power +Vol Up** 來設定) 。 選擇 **Kiosk 模式**，選取 **電池限制**，然後選擇 **啟用**。

![進位選項的螢幕擷取畫面。](images/enable-bl-sp3.png)

![進位選項。](images/enable-bl-sp3-2.png)

## <a name="enabling-battery-limit-using-surface-enterprise-management-mode-semm-or-surface-pro-3-firmware-powershell-scripts"></a>使用 Surface Enterprise管理模式啟用電池 (SEMM) 或 Surface Pro PowerShell 腳本

Surface UEFI 電池限制也可透過下列方法進行組組：

- Surface Pro 4及之後
  - [Microsoft Surface UEFI Configurator](surface-enterprise-management-mode.md)  
    - Surface UEFI Manager Powershell 腳本 (SEMM_Powershell.zip) [適用于 IT 的 Surface Tools 下載](https://www.microsoft.com/download/details.aspx?id=46703)

### <a name="using-microsoft-surface-uefi-configurator"></a>使用 Microsoft Surface UEFI Configurator

若要設定電池限制模式，請設定**** SEMM 設定**** 中進 (Surface Pro 4及) 。

![進位設定螢幕擷取畫面。](images/semm-bl.png)

### <a name="using-surface-uefi-manager-powershell-scripts"></a>使用 Surface UEFI Manager PowerShell 腳本

電池限制功能會透過下列設定控制：  

`407 = Battery Profile`

**描述**：電池使用模式的主動式管理方案

**預設**：  `0`

將此選項設定 `1` 為啟用電池限制。
