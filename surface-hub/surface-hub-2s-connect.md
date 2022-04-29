---
title: 將裝置連接至 Surface Hub 2S
description: 此頁面說明如何將外部裝置連線至 Surface Hub 2S。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/24/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e3d1aa79ad056e790d5dc6a46f299cbaa9b5f9b0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497473"
---
# <a name="connect-devices-to-surface-hub-2s"></a>將裝置連接至 Surface Hub 2S

Surface Hub 2S 可讓您連接外部裝置、將Surface Hub 2S 上的顯示鏡鏡像到另一部裝置，以及連接多個協力廠商周邊，包括視訊會議攝影機、會議電話和會議室系統裝置。

您可以將裝置的內容顯示到 Surface Hub 2S。 如果來源裝置是以Windows為基礎，該裝置也可以提供 TouchBack 和 InkBack，這會從連線的裝置擷取視訊和音訊，並將其呈現在Surface Hub 2S 上。 如果 Surface Hub 2S 遇到High-Bandwidth數位內容保護 (HDCP) 訊號，例如 Blu-ray DVD 播放機，則來源會顯示為黑色影像。

> [!NOTE]
> Surface Hub 2S 會使用選取的視訊輸入，直到建立新的連線、中斷現有的連線，或關閉連線應用程式為止。

## <a name="recommended-wired-configurations"></a>建議的有線設定 

一般而言，建議盡可能使用原生纜線連線，例如 USB-C 到 USB-C 或 HDMI 到 HDMI。 其他組合，例如 MiniDP 至 HDMI 或 MiniDP 至 USB-C 也可運作。 可能需要一些額外的設定，才能優化影片輸出體驗，如本頁面所述。

| **[連線]** | **功能** | **描述**|
| --- | --- | ---|
| HDMI + USB-C | 適用于音訊和視訊的 HDMI-in<br><br>適用于 TouchBack 和 InkBack 的 USB-C | USB-C 支援搭配 HDMI A/V 連線的 TouchBack 和 InkBack。<br><br>使用 USB-C 到 USB-A 連線到舊版電腦。<br><br>**注意：** 為了獲得最佳結果，請先連線 HDMI，再連接 USB-C 纜線。 如果您用於 HDMI 的電腦與 TouchBack 和 InkBack 不相容，則不需要 USB-C 纜線。 |
| USB-C <br> 透過計算模組)  ( | 影片 <br>音訊輸入 | A/V 所需的單一纜線<br><br>支援 TouchBack 和 InkBack<br><br>已啟用 HDCP |
| 埠) 中的 HDMI ( | 視訊、音訊到 Surface Hub 2S | A/V 所需的單一纜線<br><br>不支援 TouchBack 和 InkBack<br><br>已啟用 HDCP |
| MiniDP 1.2 輸出 | 視訊輸出，例如鏡像到較大的投影機。 | A/V 所需的單一纜線 |

當您透過 USB-C 埠將客體電腦連線到 Surface Hub 2S 時，會探索並設定數個 USB 裝置。 這些周邊裝置是針對 TouchBack 和 InkBack 所建立。 如下表所示，您可以在 裝置管理員 中檢視周邊裝置，這會顯示某些裝置的重複名稱，如下表所示。

 
|**周邊設備**| **裝置管理員中的清單** |
| ---------------------------- |------------- | ------------------------------|
| 人性化介面裝置 | 符合 HID 標準的消費者控制裝置<br>符合 HID 標準的手寫筆<br>符合 HID 標準的手寫筆 (重複項目)<br>符合 HID 標準的手寫筆 (重複項目)<br>符合 HID 標準的觸控式螢幕<br>USB 輸入裝置<br>USB 輸入裝置 (重複項目) |
| 鍵盤 | 標準 PS/2 鍵盤 |
| 滑鼠及其他指標裝置 | 符合 HID 標準的滑鼠 |
| USB 控制器 | 一般 USB 集線器<br>USB 複合裝置 |

## <a name="connecting-video-in-to-surface-hub-2s"></a>將影片連線到 Surface Hub 2S

您可以使用 USB-C 或 HDMI 將視訊輸入Surface Hub 2S，如下表所示。  

### <a name="surface-hub-2s-video-in-settings"></a>Surface Hub 2S 影片輸入設定

| **訊號類型** | **解析度** | **畫面播放速率** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| 電腦              | 640 x 480      | 60             | X        | X         |
| 電腦              | 720 x 480      | 60             | X        | X         |
| 電腦              | 1024 x 768     | 60             | X        | X         |
| 電腦              | 1920 x 1080    | 60             | X        | X         |
| 電腦              | 3840x2560      | 30             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 30             | X        | X         |

> [!NOTE]
> 只有連線到計算模組上的埠時，才支援 4K UHD 解析 (3840×2560) 。 位於裝置左側、上方和右側的「客體」USB 埠不支援此功能。

> [!NOTE]
> 在 Surface Hub 2S 上顯示時，來自已連線外部電腦的視訊可能會變小。

## <a name="mirroring-surface-hub-2s-display-on-another-device"></a>鏡像Surface Hub 2S 顯示在另一部裝置上

您可以使用 MiniDP 將視訊輸出到另一個顯示，如下表所示。

### <a name="surface-hub-2s-video-out-settings"></a>Surface Hub 2S 影片設置

| **訊號類型** | **解析度** | **畫面播放速率** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| 電腦              | 640 x 480      | 60             | X          |
| 電腦              | 720 x 480      | 60             | X          |
| 電腦              | 1024 x 768     | 60             | X          |
| 電腦              | 1920 x 1080    | 60             | X          |
| 電腦              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 2S 包含 MiniDP 視訊輸出埠，可將視覺內容從 Surface Hub 2S 投影到另一個顯示器。 如果您打算使用 Surface Hub 2S 投影到另一個顯示器，請注意下列建議：

- **需要鍵盤。** 開始之前，您必須將有線或已啟用藍牙的外部鍵盤連線到 Surface Hub 2S。 請注意，不同于原始Surface Hub，Surface Hub 2S 的鍵盤會個別銷售，而且不會包含在出貨套件中。<br><br>
- **設定重複模式。** Surface Hub 2S 僅支援以重複模式進行視訊輸出。 不過，當您第一次連線時，仍然需要手動設定顯示模式：
    1. 輸入**Windows標誌鍵**  +  **P**，這會開啟 Surface Hub 2S 右側的 [Project] 窗格，然後選取 [**複製**模式]。
    2. 當您完成Surface Hub 2S 會話時，請選取 **[結束會話]**。 這可確保會為下一個會話儲存重複的設定。<br><br>
- **規劃不同的外觀比例。** 如同其他 Surface 裝置，Surface Hub 2S 會使用 3：2 的顯示外觀比例， (顯示器) 寬度與高度之間的關聯性。 支援將Surface Hub 2S 投影到具有不同外觀比例的顯示器上。 不過請注意，由於 Surface Hub 2S 會複製顯示器，因此 MiniDP 輸出也只會以 3：2 的外觀比例顯示，這可能會導致信箱化或換行，視接收顯示的外觀比例而定。 

> [!NOTE]
> 如果您的第二個監視器使用 16：9 的外觀比例 (大部分電視監視器) 的主要比例，則黑色長條可能會出現在鏡像顯示器的左側和右側。 如果發生這種情況，您可能想要通知使用者不需要調整第二個顯示器。

## <a name="selecting-cables"></a>選取纜線

請注意下列建議：

- **[USB]。** USB 3.1 Gen 2 纜線。
- **MiniDP。** DisplayPort 纜線經過認證，長度高達 3 公尺。
- **HDMI。** 如果需要長纜線，建議使用 HDMI，因為符合成本效益的長纜線可視需要安裝重複器。

> [!NOTE]
> 如果偵測到 HDMI，大部分的 DisplayPort 來源都會自動切換至 HDMI 訊號。

## <a name="wirelessly-connect-to-surface-hub-2s"></a>無線連線到 Surface Hub 2S

Windows 10/11 原生支援 Miracast，可讓您無線連線到 Surface Hub 2S。<br><br>

### <a name="to-connect-using-miracast"></a>若要使用 Miracast：

1. 在您的Windows 10/11 裝置上，輸入**Windows標誌鍵**  +  **K**。 
2. 在 [連線] 視窗中，在附近的裝置清單中尋找Surface Hub 2S 的名稱。 您可以在顯示器的左下角找到Surface Hub 2S 的名稱。
3. 如果您的系統管理員已啟用Miracast連線的 PIN 設定，請輸入 PIN。 這會要求您在第一次連線到 Surface Hub 2S 時輸入 PIN 編號。

> [!NOTE]
>如果您未如預期般看到Surface Hub 2S 裝置的名稱，可能會提前關閉前一個會話。 若是如此，請直接登入 Surface Hub 2S 以結束上一個會話，然後從您的外部裝置連線。

## <a name="connecting-peripherals-to-surface-hub-2s"></a>將週邊設備連線到 Surface Hub 2S

### <a name="bluetooth-accessories"></a>藍牙配件

您可以使用 藍牙 將下列配件連線到 Surface Hub-2S：

- 滑鼠
- 鍵盤
- 耳機
- 喇叭
- Surface Hub 2 個畫筆

> [!NOTE]
> 連接藍牙耳機或喇叭之後，您可能需要變更預設麥克風及喇叭設定。 如需詳細資訊，請參閱[Surface Hub 設定的本機管理](local-management-surface-hub-settings.md)。
