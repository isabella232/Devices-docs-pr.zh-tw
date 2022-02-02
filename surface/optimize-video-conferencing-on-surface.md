---
title: 優化 Surface 裝置上的視訊會議
description: 此頁面提供在 Surface 裝置上Microsoft Teams和其他視訊會議解決方案的最佳作法
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/10/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
ms.openlocfilehash: dd72bf940309fe9f3d7b4bf334a94a557cffe016
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338608"
---
# <a name="optimize-video-conferencing-on-surface-devices"></a>優化 Surface 裝置上的視訊會議

Surface 裝置會利用行動裝置能源消費的最新進展，提供跨工作負載優化的簡化體驗。 對大部分的工作量來說，這會提供很好的體驗。 針對某些使用Microsoft Teams或其他視訊會議應用程式的工作量，您應該遵循這些建議，以確保獲得最佳體驗。

## <a name="surface-drivers-and-firmware"></a>Surface 驅動程式和固件

Microsoft 會定期發佈 Surface 裝置更新，併發行數個以視訊會議工作負載為目標的 Surface 更新，包括：

- 系統改良功能
- 相機磁碟機的耗電改良功能
- 圖形驅動程式更新
- 電源設定優化

### <a name="get-updates-to-all-devices"></a>取得所有裝置的更新

請確認貴組織有讓裝置接收這些更新的流程。 如果您使用的是商務Windows更新Windows[更新](/windows/deployment/update/waas-manage-updates-wufb)，則當更新發行時，已經收到最新的 Surface 更新。 使用更新檢查Windows更新，並確認已安裝最新的 Surface 更新。 若要深入瞭解，請參閱：

- [Surface 更新記錄](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)
- [安裝 Surface Windows更新](https://www.microsoft.com/surface/support/performance-and-maintenance/install-software-updates-for-surface?)

如果您使用其他選項來安裝 Surface 驅動程式和固件更新，您必須使用已發佈的 MSI 檔案手動安裝最新的 Surface 更新，或使用 Configuration Manager 安裝更新。 若要深入瞭解，請參閱：

- [下載 Surface 的驅動程式和固件](https://support.microsoft.com/help/4023482)
- [管理和部署 Surface 驅動程式與韌體更新](manage-surface-driver-and-firmware-updates.md)
- [如何在 Configuration Manager 中管理 Surface 驅動程式更新](https://support.microsoft.com/help/4098906)

### <a name="graphics-driver-updates-for-microsoft-teams"></a>圖形驅動程式更新Microsoft Teams

第 10 代和第 11 代 Intel 處理器的較新 Surface 裝置型號已收到圖形驅動程式更新，有助於解決視訊會議工作負載。 若要啟用這些改良功能，請確定您安裝下列專案：

- Microsoft Teams**版本 1.4.00.22472**或更新版本。
- Intel 圖形驅動程式 **27.20.100.9621** 或更新程式。

### <a name="power-settings-optimizations"></a>電源設定優化

Surface 裝置可以在 Windows 中變更Windows 10的電源滑杆位置，Windows 11。

某些 Surface 裝置已收到更新，其中包括根據電源滑杆位置或電源模式針對視訊會議工作負載的電源設定優化。 不過，Windows 10 Windows 11使用視訊會議工作負載的推薦電源滑杆位置和**** 電源模式位置，您必須調整電源滑杆，才能啟用這些優化：

1. 連線電源 (使用電池電源時，系統不會執行) 。  
2. 調整電源滑杆或電源模式位置，以使用更好的**效果****或最佳效果。**

## <a name="learn-more"></a>深入了解

- [適用於 Surface 裝置的最佳電源設定](maintain-optimal-power-settings-on-surface-devices.md)
- [最大化 Surface 電池使用時間](https://support.microsoft.com/surface/maximize-your-surface-battery-life-45479867-a7fa-33dd-fc4d-6762e9b3b11a)
