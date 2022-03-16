---
title: 適用於 Surface 裝置的最佳電源設定
description: 本主題提供維護最佳電源設定的最佳作法建議，並說明 Surface 如何簡化電源管理體驗。 本文適用于目前支援的所有 Surface 裝置，包括 Surface Pro 7+、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 1/15/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: b4a9a1756abc4d7a45c5b4eb5081e8f5a72565eb
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448306"
---
# <a name="best-practice-power-settings-for-surface-devices"></a>適用於 Surface 裝置的最佳電源設定

Surface 裝置是專為利用行動裝置能源消費的最新進展所設計，以提供跨工作負載優化的簡化體驗。 根據您執行的工作，Surface 會動態微調電源流向個別硬體元件的方式，暫時喚醒系統元件以處理背景工作 ，例如傳入的電子郵件或網路流量，然後再回到低電力空閒狀態 (S0ix) 。

## <a name="summary-of-recommendations-for-it-administrators"></a>適用于 IT 系統管理員的建議摘要

為了確保整個組織的 Surface 裝置完全受益于 Surface 電源優化功能：

-  從更新或 Surface 驅動程式和Windows MSI 安裝最新的驅動程式和固件。 這可建立平衡的電源 (，) 電源設定檔，並設定最佳電源設定。  詳情請參閱管理及部署 [Surface 驅動程式和固件更新](manage-surface-driver-and-firmware-updates.md)。
- 避免建立自訂電源設定檔或調整預設 UI 中看不到的進 (**SystemPower**  >  &**睡眠) **。
- 如果您必須管理整個網路 (例如高度管理組織) 中的裝置電源設定檔，請使用 powercfg 命令工具，從 Surface 裝置原廠映像匯出電源配置，然後將它匯入 Surface 裝置的部署套件。 

    >[!NOTE]
    >您只可以在相同類型的 Surface 裝置上匯出電源配置。  例如，您無法從系統匯出電源Surface Laptop，並匯Surface Pro。  詳情請參閱設定 [電源設定](/windows-hardware/customize/power-settings/configure-power-settings)。

- 將 Surface 裝置排除在任何現有的電源管理策略設定中。 

## <a name="background"></a>背景

Surface 的電源管理方式與先前 OS 標準有顯著差異，因為較早的作業系統標準會透過一系列的睡眠狀態逐漸減少並關閉電源;例如，迴圈流覽 S1、S2、S3 等。

相反地，Surface 會以自訂電源設定檔來影像，以新式備用功能和動態微調取代舊版睡眠和耗能功能。 此自訂電源設定檔是透過 Surface Serial Hub Driver 和系統匯總器模組 (>) 。 當 Surface 裝置電源策略擁有者使用演算法來計算最佳電力需求時，該SAM 晶片會發揮功能。 它可與 power manager Windows一起使用，以只配置或節流硬體元件運作所需的確切電力量。 本文適用于目前支援的所有 Surface 裝置，包括 Surface Pro 7+、Surface Laptop Go、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。

## <a name="utilizing-the-custom-power-profile-in-surface"></a>在 Surface 中運用自訂電源設定檔

如果您進入 Surface 裝置上的電源選項，會看到有單一電源配置可供使用。 這是自訂電源設定檔。 如果您前往進位電源設定，與一般電腦相比，您看到的電源選項子集會小得多，Windows 10或Windows 11。 與一般裝置不同，Surface 具有可管理這些電源選項的固件和自訂群組件。


## <a name="modern-standby"></a>新式備用

演算法內嵌的自訂電源設定檔可讓 Surface 保持低電源狀態，以立即關閉智慧型手機的典型功能，以啟用新式的備用連接。 S0ix ，也稱為 Deepest Runtime 閒置平臺狀態 (點) ，是 Surface 裝置的預設電源模式。 新式待機有兩種模式：

- **已連接待命狀態。** 即時傳送電子郵件、訊息和雲端同步處理資料的預設模式，已連接Wi-Fi維持網路連接。

- **已中斷待命。** 可延長電池使用時間的選擇性模式，中斷連接的備用狀態可提供相同的立即開啟體驗，並關閉 Wi-Fi、藍牙和相關網路連接，以節省電力。

若要深入瞭解新式備用，請參閱[Microsoft 硬體開發人員中心](/windows-hardware/design/device-experiences/modern-standby-wake-sources)。

## <a name="how-surface-streamlines-the-power-management-experience"></a>Surface 如何簡化電源管理體驗 

Surface 整合下列功能，可協助使用者優化電源管理體驗：

- [單一電源配置](#singular-power-plan)

- [簡化的電源設定使用者介面](#simplified-power-settings-user-interface)

- [Windows電源滑杆](#windows-performance-power-slider)

### <a name="singular-power-plan"></a>單一電源配置

Surface 專為簡化的電源管理體驗所設計，不需要建立自訂電源配置或手動設定電源設定。 Microsoft 提供單一電源配置， (平衡) ，以取代標準版和標準Windows方案，以簡化使用者體驗。

### <a name="simplified-power-settings-user-interface"></a>簡化的電源設定使用者介面

Surface 提供符合最佳做法電源設定建議之簡化的 UI。 一般而言，建議只調整預設使用者介面中可見的設定，並避免設定進位電源設定或群組原則設定。 使用預設螢幕和睡眠超時，同時避免亮度等級上限是使用者維持延長電池使用時間最有效的方法。

![圖 1。 簡化的電源&睡眠設定。](images/powerintrofig1.png)

圖 1。 簡化的電源和睡眠設定

### <a name="windows-performance-power-slider"></a>Windows電源滑杆

執行內部Windows 10 1709 及更新版本之 Surface 裝置包含電源滑杆，讓您在需要時優先使用電池續航時間，或根據需求提升電池使用時間。 您可以按一下電池圖示，從工作列存取電源滑杆。 向左滑動以延長電池 (省電模式) 或向右滑動，以提升電池使用速度。

![圖 2. Power 滑杆。](images/powerintrofig2a.png)

圖 2. Power 滑杆

Power 滑杆會啟用下清單格所述的四種狀態：

| 滑杆模式| 描述 |
|---|---|
| 省電模式| 當系統與電源中斷連接時，有助於節省電力並延長電池使用時間。 當省電模式為啟用時，某些Windows功能會停用、節流或行為不同。 螢幕亮度也會降低。 只有在使用電池電力 (使用省電) 。 若要深入瞭解，請參閱[省電。](/windows-hardware/design/component-guidelines/battery-saver)|
| 建議執行 | 電池使用時間比先前版本預設Windows。 |
| 提升績效 | 稍微比電池使用時間更有利於使用，以預設滑杆模式運作。 |
| 最佳效果 | 無論電池電力耗用程度如何，對需要最高績效和回應的工作負載，都比電力更符合電力需求。|

Power 滑杆模式會直接控制下表中顯示的特定硬體元件。

| 元件 | 滑杆功能 |
|---|---|
| Intel Speed Shift (CPU 能源註冊) 與能源績效喜好設定提示。 | 選取最佳的作業頻率和電力，以獲得最佳的績效和電力。 PERFEPP (PERFEPP) 是 CPU 的全域電源效率提示。 |
| 扇形 (/RPM) | 如適用，可針對變更條件進行調整，例如讓風扇在省電滑杆模式中保持靜音。|
| PL1/PL2 (的處理器套件) 。| 要求 CPU 管理其頻率選擇，以配合穩定狀態 (PL1 和) PL2 負載 (平均) 限制。|
| 處理器的加速頻率限制 (IA 的加速) 。 | 調整處理器和圖形的顯示效果，讓處理器核心比已評分的操作頻率更快速或更慢地執行。                                                |

>[!NOTE]
>電源滑杆與作業系統電源設定完全無關，無論是從控制台/Power Options、群組原則或相關方法設定。

若要深入瞭解，請參閱：

-   [自訂Windows電源滑杆](/windows-hardware/customize/desktop/customize-power-slider)

-   [省電。](/windows-hardware/design/component-guidelines/battery-saver)

## <a name="best-practices-for-extended-battery-life"></a>延長電池使用時間的最佳作法


| 最佳做法 | 移至 | 後續步驟 |
|---|---|---|                                                                                                                                    
| 確保您的 Surface 裝置是最新版本| Windows Update | 在工作列搜尋方塊中，輸入Windows **，** 然後選取**檢查更新**。 |
| 針對您執行的工作選擇最佳電源設定 | Power 滑杆 | 在工作列中，選取電池圖示，然後選擇最佳**效果**、最佳電池使用**** 時間，或介於兩者之間的某個位置。|
| 在電力不足時節省電池 | 省電模式 | 在工作列中，選取電池圖示，然後按一下 **[電池設定**。 如果我 **的電池落在** 下方，請選取自動開啟省電模式，然後將滑杆進一步向右移動，延長電池使用時間。 |
| 設定最佳螢幕亮度 | 省電模式 | 在工作列中，選取電池圖示，然後按一下 [電池 **設定**>，選取 [省電時 **降低螢幕亮度**。 |
| 每當您未插入電源時，請節省電力 | 省電模式| 選取 **開啟省電狀態，直到下次充電**。|
| 調查電源設定的問題。 | Power 疑難排解員 | 在工作列搜尋疑難排解中 **，選取疑**難解答，然後選取 **Power** ，然後按照指示操作。|
| 檢查應用程式使用量 | 您的應用程式 | 關閉應用程式。|
| 檢查電源線是否有損壞。| 電源線 | 如果電源線已損毀或損毀，請取代電源線。|

## <a name="learn-more"></a>深入了解 

- [新式待機](/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [自訂Windows電源滑杆](/windows-hardware/customize/desktop/customize-power-slider)

- [省電模式](/windows-hardware/design/component-guidelines/battery-saver)
- [管理和部署 Surface 驅動程式與韌體更新](manage-surface-driver-and-firmware-updates.md)
