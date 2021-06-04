---
title: 將裝置連接至 Surface Hub 2S
description: 此頁面說明如何將外部裝置連接至 Surface Hub 2 秒。
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
ms.openlocfilehash: 1c4f9b4a74b50edb5587185f28a18163a02d62f9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831598"
---
# 將裝置連接至 Surface Hub 2S
Surface Hub 2 秒可讓您連線外部裝置、將 Surface Hub 上的顯示鏡像至另一個裝置，以及連接多個協力廠商週邊設備，包括視訊會議攝影機、會議電話和會議室系統裝置。

您可以將裝置中的內容顯示在 Surface Hub 的2秒。 如果來源裝置是 Windows 基礎，則該裝置也可以提供 TouchBack 和 InkBack，這會從已連接的裝置取得影片和音訊，並在 Surface Hub 2 上呈現它們。 如果 Surface Hub 2 遇到高頻寬的數位內容保護（HDCP）信號（例如藍光 DVD 播放程式），來源會顯示為黑色影像。

> [!NOTE]
> Surface Hub 2 秒使用選取的視頻輸入，直到建立新的連線為止，現有的連線中斷，或連線 app 已關閉。

##  <a name="recommended-wired-configurations"></a>建議的有線設定 

一般來說，建議您盡可能使用原生纜線連線（例如，將 usb-C 連線至 USB-C，或從 HDMI 移至 HDMI）。 其他組合（例如，MiniDP 到 HDMI 或 MiniDP 至 USB）也會運作。 如本頁面所述，可能需要進行一些其他設定，才能優化 vcd 體驗。

| **[連線]** | **功能** | **描述**|
| --- | --- | ---|
| HDMI + USB-C | [音訊及視頻] 的 HDMI<br><br>TouchBack 和 InkBack 的 USB-C | USB-C 支援使用 HDMI A/V 連接來 TouchBack 和 InkBack。<br><br>使用 USB-A 連線至 USB-A 連線至傳統電腦。<br><br>**注意：** 若要取得最佳結果，請先連接 HDMI，然後再連接 USB-C 資料線。 如果您用的是用於 HDMI 的電腦與 TouchBack 和 InkBack 不相容，您就不需要使用 USB-C 纜線。 |
| USB-C <br> （透過計算模組） | 影片-in <br>Audio in | A/V 需要單一線纜<br><br>支援 TouchBack 和 InkBack<br><br>HDCP 已啟用 |
| HDMI （在埠中） | 影片、音訊進入 Surface Hub 的2秒 | A/V 需要單一線纜<br><br>不支援 TouchBack 和 InkBack<br><br>HDCP 已啟用 |
| MiniDP 1.2 輸出 | 例如，將影像移至較大的投影儀。 | A/V 需要單一線纜 |

當您透過 USB-C 埠將來賓電腦連線至 Surface Hub 2，會發現並設定數個 USB 裝置。 這些週邊裝置是針對 TouchBack 和 InkBack 建立的。 如下表所示，您可以在 [裝置管理器] 中查看週邊裝置，這會顯示部分裝置的重複名稱，如下表所示。

 
|**周邊設備**| **[裝置管理器] 中的清單** |
| ---------------------------- |------------- | ------------------------------|
| 人性化介面裝置 | 符合 HID 標準的消費者控制裝置<br>符合 HID 標準的手寫筆<br>符合 HID 標準的手寫筆 (重複項目)<br>符合 HID 標準的手寫筆 (重複項目)<br>符合 HID 標準的觸控式螢幕<br>USB 輸入裝置<br>USB 輸入裝置 (重複項目) |
| 鍵盤 | 標準 PS/2 鍵盤 |
| 滑鼠及其他指標裝置 | 符合 HID 標準的滑鼠 |
| USB 控制器 | 一般 USB 集線器<br>USB 複合裝置 |

##  <a name="connecting-video-in-to-surface-hub-2s"></a>將影片連接至 Surface Hub 2 秒

您可以使用 USB-C 或 HDMI，將影片輸入至 Surface Hub 2：（如下表所示）。  

###  <a name="surface-hub-2s-video-in-settings"></a>Surface Hub 2 到2影片-in 設定

| **訊號類型** | **解析度** | **畫面播放速率** | **HDMI** | **USB-C** |
| --------------- | -------------- | -------------- | -------- | --------- |
| PC              | 640 x 480      | 60             | X        | X         |
| 電腦              | 720 x 480      | 60             | X        | X         |
| 電腦              | 1024 x 768     | 60             | X        | X         |
| 電腦              | 1920 x 1080    | 60             | X        | X         |
| 電腦              | 3840x2560      | 為期             | X        | X         |
| HDTV            | 720p           | 60             | X        | X         |
| HDTV            | 1080p          | 60             | X        | X         |
| 4K UHD          | 3840x2560      | 為期             | X        | X         |

> [!NOTE]
> 只有在連線到計算模組上的埠時，才支援 4K UHD 解析度（3840×2560）。 在裝置左、上、右端的「來賓」 USB 埠上不支援。

> [!NOTE]
> 在 Surface Hub 2 上顯示時，來自連線的外部電腦的影片可能會變得較小。

##  <a name="mirroring-surface-hub-2s-display-on-another-device"></a>鏡像 Surface Hub 2 秒顯示在另一個裝置上

您可以使用 MiniDP 將影片輸出至另一個顯示器，如下表所示。

###  <a name="surface-hub-2s-video-out-settings"></a>Surface Hub 2 秒的影片輸出設定

| **訊號類型** | **解析度** | **畫面播放速率** | **MiniDP** |
| --------------- | -------------- | -------------- | ---------- |
| PC              | 640 x 480      | 60             | X          |
| 電腦              | 720 x 480      | 60             | X          |
| 電腦              | 1024 x 768     | 60             | X          |
| 電腦              | 1920 x 1080    | 60             | X          |
| 電腦              | 3840 x 2560    | 60             | X          |
| HDTV            | 720p           | 60             | X          |
| HDTV            | 1080p          | 60             | X          |
| 4K UHD          | 3840 x 2560    | 60             | X          |


 
Surface Hub 秒包含 MiniDP 的視頻輸出埠，可將表面中樞2的視覺內容投影到另一個顯示器。 如果您打算使用 Surface Hub 2 到2來投影另一個顯示器，請注意下列建議：

- **需要鍵盤。** 開始之前，您必須將有線或支援藍牙的外部鍵盤連線至 Surface Hub 2。 請注意，與原始 Surface 中樞不同的是，Surface Hub 秒的鍵盤是單獨銷售，不包含在裝運套件中。<br><br>
- **設定重複模式。** Surface Hub 2 秒支援僅限重複模式中的 vcd。 不過，當您第一次連線時，您仍需手動設定顯示模式：
    1. 輸入**Windows 標誌鍵**  +  **P**，這會在 Surface Hub 2 的右側開啟 [專案窗格]，然後選取 [**複製**模式]。
    2. 當您完成 Surface Hub 2 秒會話後，請選取 [**結束會話**]。 這可確保針對下一個會話儲存重複的設定。<br><br>
- **規劃不同的長寬比。** 與其他 Surface 裝置一樣，Surface Hub 2 秒使用3:2 顯示長寬比（顯示器寬度和高度之間的關聯）。 支援使用不同長寬比的顯示器來投影 Surface Hub 2 至顯示器。 請注意，由於 Surface Hub 2 是複製顯示器，因此 MiniDP 輸出也只會顯示在3:2 長寬比中，這可能會導致 letterboxing 或 curtaining，視接收顯示器的長寬比而定。 

> [!NOTE]
> 如果您的第二部監視器使用16:9 長寬比（大部分電視監視器的主要比例），則會在鏡像顯示的左側和右側出現黑色線條。 如果發生這種情況，您可能會想要通知使用者不需要調整第二個顯示器。

##  <a name="selecting-cables"></a>選取纜線

請注意下列建議：

- **[USB]。** USB 3.1 Gen 2 纜線。
- **MiniDP.** DisplayPort 纜線認證最多可達3米的時間長度。
- **HDMI.** 如果需要較長的纜線，建議您視需要的經濟高效、遠距離纜線的寬屏可用性來安裝中繼器。

> [!NOTE]
> 如果偵測到 HDMI，大部分的 DisplayPort 來源會自動切換到 HDMI 信號。

##  <a name="wirelessly-connect-to-surface-hub-2s"></a>以無線方式連接至 Surface Hub 2

Windows 10 本身支援 Miracast，可讓您以無線方式連接至 Surface Hub 2 秒。<br><br>

###  <a name="to-connect-using-miracast"></a>若要使用 Miracast 連線：

1. 在您的 windows 10 裝置上，輸入**Windows 標誌鍵**  +  **K**。 
2. 在 [連接] 視窗中，在附近的裝置清單中尋找 Surface Hub 秒的名稱。 您可以在顯示器左下角找到 Surface Hub 2 的名稱。
3. 如果您的系統管理員已啟用 Miracast 連線的 PIN 設定，請輸入 PIN。 這需要您在第一次連線至 Surface Hub 2 秒時輸入 PIN 碼。

> [!NOTE]
>如果您沒有像預期那樣看到 Surface Hub s 2 裝置的名稱，可能是前一個會話已過早關閉。 如果是，請直接登入 Surface Hub 2，以結束前一個會話，然後從外部裝置連線。

##  <a name="connecting-peripherals-to-surface-hub-2s"></a>將週邊設備連接至 Surface Hub 2

###  <a name="bluetooth-accessories"></a>藍牙配件

您可以使用藍牙將下列附件連線至 Surface Hub-2：

- 滑鼠
- 鍵盤
- 耳機
- 喇叭
- Surface Hub 2 筆

> [!NOTE]
> 連接藍牙耳機或喇叭之後，您可能需要變更預設麥克風及喇叭設定。 如需詳細資訊，請參閱[**Surface Hub 的本機管理設定**](https://docs.microsoft.com/surface-hub/local-management-surface-hub-settings)。
