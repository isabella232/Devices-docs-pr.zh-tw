---
title: Surface 裝置的最佳做法電源設定
description: 本主題提供維護最佳電源設定的最佳做法建議，並說明 Surface 如何簡化電源管理體驗。 本文適用于所有目前支援的 Surface 裝置，包括 Surface Pro 7、Surface Pro X 及 Surface 膝上型電腦3。
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
ms.date: 10/28/2019
ms.openlocfilehash: 73a74dc05a5a6929fa6360e04aac5d342b9c06a8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831289"
---
# Surface 裝置的最佳做法電源設定

Surface 裝置的設計目的是充分利用行動裝置能源消耗中的最新進步，以提供跨工作負載優化的簡化體驗。 視您所執行的動作而定，Surface 會以動態方式來調整如何將電源流向個別的硬體元件，暫時是為了處理背景工作（例如內送電子郵件或網路流量），在返回低能量空閒狀態（S0ix）之前。

## IT 系統管理員建議摘要

為了確保整個組織的 Surface 裝置能充分享受 Surface 電源優化功能的好處：

-  從 Windows Update 或 Surface 驅動程式和固件 MSI 安裝最新的驅動程式和固件。 這會根據預設建立平衡電源配置（亦即電源設定檔），並設定最佳電源設定。  如需詳細資訊，請參閱[管理和部署 Surface 驅動程式和固件更新](manage-surface-driver-and-firmware-updates.md)。
- 避免建立自訂的 power 個人檔案或調整 [預設 UI] （**系統**  >  **power & 睡眠**）中不可見的 [高級電源] 設定。
- 如果您必須在網路上管理裝置的電源設定檔（例如在高度管理的組織中），請使用 powercfg 命令工具，從 Surface 裝置的工廠影像匯出電源配置，然後將其匯入到 Surface 裝置的置備套件中。 

    >[!NOTE]
    >您只能在相同類型的 Surface 裝置上匯出電源配置。  例如，您無法從 Surface 膝上型電腦匯出電源配置，並將其匯入 Surface Pro。  如需詳細資訊，請參閱[設定電源設定](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)。

- 從任何現有的電源管理原則設定中排除 Surface 裝置。 

## 背景

表面實現電源管理的方式與較舊的 OS 標準（透過一系列睡眠狀態逐漸減少及關閉電源）有顯著差異;例如，迴圈執行 S1、S2、S3 等。

相反地，Surface 是使用自訂的 power profile 來取代舊版睡眠及能源消耗功能與新式待機功能以及動態微調。 此自訂電源設定檔是透過 Surface 串列中樞驅動程式和系統聚合器模組（SAM）來實現。 SAM 晶片會充當 Surface 裝置電源原則擁有者，使用演算法來計算最佳電源需求。 它與 Windows power manager 搭配使用，只可用於指派或限制硬體元件正常運作所需的實際功率量。 本文適用于所有目前支援的 Surface 裝置，包括 Surface Pro 7、Surface Pro X 及 Surface 膝上型電腦3。

## 在 Surface 中利用自訂電源設定檔

如果您進入 surface 裝置上的 [電源] 選項，您會看到單一電源配置可供使用。 此為自訂電源設定檔。 而且，如果您移至 [高級電源設定]，就會看到一個較小的 [電源選項] 子集，與執行 Windows 10 的一般電腦相比。 與一般裝置不同，Surface 具有固件與自訂群組件，可用於管理這些電源選項。


## 新式待機

Algorithmically 內嵌的自訂電源設定檔可針對智慧手機的一般即時/立即關閉功能維持低功耗，以啟用 Surface 的新式待機連接。 S0ix （也稱為最深的執行時間空閒平臺狀態（DRIPS））是 Surface 裝置的預設電源模式。 新式待機有兩種模式：

- **已連線的待機模式。** 傳送電子郵件、訊息及雲端同步處理資料的預設模式，已連接的待機會保持 Wi-fi 開啟，並維持網路連線能力。

- **已中斷連線。** 延長電池使用時間的選用模式，斷開的待機會提供相同的暫態體驗，並可關閉 Wi-fi、藍牙及相關的網路連線來省電。

若要深入瞭解新式待機，請參閱[Microsoft 硬體開發人員中心](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)。

## 表面如何簡化電源管理體驗 

表面整合了下列功能，可協助使用者優化電源管理體驗：

- [單數電源配置](#singular-power-plan)

- [簡化的電源設定使用者介面](#simplified-power-settings-user-interface)

- [Windows 效能電源滑杆](#windows-performance-power-slider)

### 單數電源配置

Surface 專為簡化的電源管理體驗而設計，無需建立自訂電源配置或手動設定電源設定。 Microsoft 提供單一電源配置（已平衡）來取代標準 Windows 組建的多個電源配置，以簡化使用者體驗。

### 簡化的電源設定使用者介面

Surface 提供簡化的 UI，以符合最佳做法電源設定建議。 一般來說，建議您只調整預設使用者介面中顯示的設定，避免設定 [高級電源設定] 或 [群組原則] 設定。 使用預設的螢幕和睡眠超時，同時避免最大的亮度層級，是使用者保持延長電池使用時間的最有效方式。

![圖 1。 簡化的 power & 睡眠設定](images/powerintrofig1.png)

圖 1。 已簡化電源和睡眠設定

### Windows 效能電源滑杆

執行 Windows 10 組建1709及更新版本的 Surface 裝置包含一個電源滑杆，可讓您在需要時排定電池使用時間優先順序，或視需要使用的效能。 您可以按一下 [電池] 圖示，從工作列存取 [電源] 滑杆。 向左滑動以延長電池使用時間（節電模式），或滑動以取得更高的效能。

![圖 2. [電源] 滑杆](images/powerintrofig2a.png)

圖 2. [電源] 滑杆

[電源] 滑杆支援四種狀態，如下表所述：

| 滑杆模式| 描述 |
|---|---|
| 省電模式| 當系統斷開與電源的連線時，可協助省電並延長電池使用時間。 當節電模式開啟時，部分 Windows 功能會停用、受到限制或行為不同。 畫面亮度也會減少。 節電模式只能在使用電池電源（DC）時使用。 若要深入瞭解，請參閱[節電](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)模式。|
| 建議執行 | 比舊版 Windows 的預設設定提供更長的電池使用時間。 |
| 效能更佳 | 在電池使用時間上稍有優先表現，以預設滑杆模式運作。 |
| 最佳效能 | 針對需要最佳效能與回應性的工作負載來提高效能，而不管電池功耗為何。|

[電源] 滑杆模式會直接控制下表中顯示的特定硬體元件。

| 元件 | 滑杆功能 |
|---|---|
| 英特爾快速移（CPU 能源寄存器）和能源效能喜好設定提示。 | 針對最佳效能和功率選取最佳的運作頻率和電壓。 能源效能喜好設定（PERFEPP）是 CPU 的全域電源效率提示。 |
| 風扇速度（RPM）| 如果適用的話，會調整變更的條件，例如，將風扇保持在節電式滑杆模式中。|
| 處理器套件電源限制（PL1/PL2）。| 需要 CPU 管理其頻率選項，以適應穩定狀態（PL1）和 turbo （PL2）工作負載的平均功率限制。|
| 處理器 turbo frequency 限制（IA turbo 限制）。 | 調整處理器與圖形效能，讓處理器內核執行的速度更快，或速度低於額定運作頻率。                                                |

>[!NOTE]
>無論是從 [控制台]/[電源選項]、[群組原則] 或 [相關方法] 進行設定，電源滑杆完全獨立于作業系統電源設定。

若要深入瞭解，請參閱：

-   [自訂 Windows 效能電源滑杆](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [節電模式。](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## 延長電池使用時間的最佳做法


| 最佳做法 | 移至 | 後續步驟 |
|---|---|---|                                                                                                                                    
| 確定您的 Surface 裝置是最新的| Windows Update | 在工作列搜尋方塊中，輸入 [ **Windows Update** ]，然後選取 [**檢查更新**]。 |
| 針對您正在執行的工作，選擇最佳電源設定 | [電源] 滑杆 | 在工作列中，選取電池圖示，然後選擇 [**最佳效能**]、[**最佳電池使用**中] 或 [介於] 之間的某個位置。|
| 在電量低時節省電池 | 省電模式 | 在工作列中，選取 [電池] 圖示，然後按一下 [**電池設定**]。 選取 [**如果我的電池不足，自動開啟節電**模式]，然後將滑杆向右移動到較長的電池使用時間。 |
| 設定最佳螢幕亮度 | 省電模式 | 在工作列中，選取電池圖示，然後按一下 [**電池設定**]，**在節電模式中選取較低的螢幕亮度**。 |
| 在未插入電源時省電 | 省電模式| 選取 **[開啟節電模式狀態，直到下次充電為止]**。|
| 調查電源設定的問題。 | Power 疑難排解程式 | 在工作列的 [搜尋] 中，選取疑難排解，選取 [**疑難排解**]，然後選取 [**電源**]，然後依照指示進行。|
| 檢查 app 使用方式 | 您的應用程式 | 關閉應用程式。|
| 檢查您的電源線是否有任何損壞。| 您的電源線 | 如果電源線磨損或損毀，請將它取代。|

## 深入了解 

- [新式待機](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [自訂 Windows 效能電源滑杆](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [節電模式](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [管理和部署 Surface 驅動程式與韌體更新](manage-surface-driver-and-firmware-updates.md)
