---
title: 連接其他裝置並以 Surface Hub 顯示
description: 您可以將其他裝置連接到 Surface Hub 來顯示內容。
ms.assetid: 8BB80FA3-D364-4A90-B72B-65F0F0FC1F0D
ms.reviewer: ''
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 6985d6a87e14df70d244457dfeddabd673bb2bdc
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911388"
---
# <a name="connect-other-devices-and-display-with-surface-hub"></a>連接其他裝置並以 Surface Hub 顯示


您可以將其他裝置連接到 Microsoft Surface Hub 來顯示內容。 本主題描述可透過有線連線方式使用的來賓模式、取代電腦模式及 Video Out 功能，並且會列出可使用[藍牙](#bluetooth-accessories)連線到 Surface Hub 的配件。

>[!NOTE]
>Surface Hub使用您選取的視音訊輸入，直到建立新連接、中斷現有連接，或關閉 連線 App。

## <a name="which-method-should-i-choose"></a>我應該選擇哪一種方法？

連線外部裝置和顯示器到 Surface Hub 時，有幾個可用的選項。 您使用的方法將需視您的情況和需求而定。 

| 如果您想要： | 使用這個方法： |
| --- | --- |
| 在另一部裝置上鏡像處理 Surface Hub 的顯示畫面。 | [Video Out (視訊輸出)](#video-out) |
| 在 Surface Hub 螢幕上呈現另一部裝置的顯示畫面，以及和裝置上的內容與內建 Surface Hub 體驗互動。 | [來賓模式](#guest-mode) |
| 從外接的 Windows 10 電腦為 Surface Hub 提供顯示內容，關閉 Surface Hub 內嵌的電腦。 除了手寫筆和觸控功能之外，相機、麥克風、喇叭及其他周邊裝置，會傳送到外部電腦。 | [取代電腦模式](#replacement-pc-mode) |


## <a name="guest-mode"></a>來賓模式


來賓模式使用有線的連線，讓使用者可以將他們裝置的內容顯示在 Surface Hub。 如果是 Windows 型的來源裝置，該裝置也可以提供 Touchback 與 Inkback。 Surface Hub 的內部電腦會從連接的裝置取得視訊和音訊並呈現在 Surface Hub 上。 如果您Surface Hub HDCP High-Bandwidth數位內容保護 (HDCP) ，來源會顯示為黑色影像。 若要在不違反 HDCP 需求的情況下顯示您的內容，請使用 Surface Hub 右側的數字鍵台，直接選擇外部來源。

>[!NOTE]
>連接 HDCP 來源時，請使用側邊鍵台變更輸入來源。

### <a name="ports"></a>連接埠

使用 Surface Hub 上的這些連接埠來使用來賓模式。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>介面</th>
<th>類型</th>
<th>說明</th>
<th>功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>顯示連接埠 1.1a</p></td>
<td><p>視訊輸入</p></td>
<td><p>來賓輸入 #1</p></td>
<td><ul>
<li><p>支援連同來賓輸入 #2 與來賓輸入 #3 一起同時顯示來賓輸入 (一個高解析度、兩個縮圖)。</p></li>
<li><p>在略過模式中，可與 HDCP 相容</p></li>
<li><p>Touchback 已啟用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>HDMI 1.4</p></td>
<td><p>視訊輸入</p></td>
<td><p>來賓輸入 #2</p></td>
<td><ul>
<li><p>支援連同來賓輸入 #1 與來賓輸入 #3 一起同時顯示來賓輸入 (一個高解析度、兩個縮圖)。</p></li>
<li><p>在略過模式中，可與 HDCP 相容</p></li>
<li><p>Touchback 已啟用</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>VGA</p></td>
<td><p>視訊輸入</p></td>
<td><p>來賓輸入 #3</p></td>
<td><ul>
<li><p>支援連同來賓輸入 #1 與來賓輸入 #2 一起同時顯示來賓輸入 (一個高解析度、兩個縮圖)。</p></li>
<li><p>在略過模式中，可與 HDCP 相容</p></li>
<li><p>Touchback 已啟用</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>3.5 公釐插孔</p></td>
<td><p>音訊輸入</p></td>
<td><p>類比音訊輸入</p></td>
<td><ul>
<li><p>通常利用 VGA 視訊輸入，內嵌到 Surface Hub 電腦中。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 2.0，類型 B</p></td>
<td><p>USB 輸出</p></td>
<td><p>Touchback</p></td>
<td><ul>
<li><p>提供存取來賓電腦的 HID 輸入裝置，如滑鼠、觸控、鍵盤和手寫筆。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="port-locations"></a>連接埠位置

這些是 55 英吋及 84 英吋 Surface Hub 上可用於來賓模式的連接埠連線。

![顯示 55 英吋 Surface Hub 上來賓連接埠的影像。](images/sh-55-guest-ports.png)

55 英吋 Surface Hub 上的有線連接埠連線

![顯示 84 英吋 Surface Hub 上來賓連接埠的影像。](images/sh-84-guest-ports.png)

84 英吋 Surface Hub 上的有線連接埠連線

### <a name="port-enumeration"></a>連接埠列舉

當 Surface Hub 利用 USB 連接埠以有線連接方式連接到來賓電腦時，可以找到及設定幾個 USB 裝置。 這些是為 Touchback 和 Inkback 建立的周邊裝置。 周邊裝置可以在 \[裝置管理員\] 中檢視。 \[裝置管理員\] 顯示的某些裝置名稱會重複。

**人性化介面裝置**

-   符合 HID 標準的消費者控制裝置

-   符合 HID 標準的手寫筆

-   符合 HID 標準的手寫筆 (重複項目)

-   符合 HID 標準的手寫筆 (重複項目)

-   符合 HID 標準的觸控式螢幕

-   USB 輸入裝置

-   USB 輸入裝置 (重複項目)

**鍵盤**

-   標準 PS/2 鍵盤

**滑鼠及其他指標裝置**

-   符合 HID 標準的滑鼠

**通用序列匯流排控制器**

-   一般 USB 集線器

-   USB 複合裝置

### <a name="guest-mode-connectivity"></a>來賓模式連線

您選擇的視訊纜線將會決定可用的來源輸入。 Surface Hub 有 DisplayPort、HDMI 和 VGA 這三種視訊輸入選擇。 請參閱下表以了解可用的解析度。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th>訊號類型</th>
<th>解析度</th>
<th>畫面播放速率</th>
<th>HDMI - RGB</th>
<th>DisplayPort</th>
<th>VGA</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>電腦</p></td>
<td><p>640 x 480</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>電腦</p></td>
<td><p>720 x 480</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>電腦</p></td>
<td><p>1024 x 768</p></td>
<td><p>60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="even">
<td><p>HDTV</p></td>
<td><p>720p</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
<tr class="odd">
<td><p>HDTV</p></td>
<td><p>1080p</p></td>
<td><p>59.94/60</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
<td><p>X</p></td>
</tr>
</tbody>
</table>

 

來源音訊是透過 DisplayPort 和 HDMI 纜線提供。 如果您必須使用 VGA，Surface Hub 有一個使用 3.5 公釐插頭的音訊輸入連接埠。 Surface Hub 也可以使用 USB 纜線，從 Surface Hub 向相容的 Windows 10 裝置提供 Touchback 和 Inkback 功能。 已與纜線連接的任何視訊輸入，都可以和 USB 纜線一起使用。

使用來賓模式時會採用下列其中一個選項來連接電腦︰

**DisplayPort** -- DisplayPort 纜線和 USB 2.0 纜線

**HDMI** -- HDMI 纜線和 USB 2.0 纜線

**VGA** -- VGA 纜線、3.5 公釐音訊纜線和 USB 2.0 纜線

如果您使用來賓模式的電腦與 Touchback 和 Inkback 不相容，您將不需要 USB 纜線。

## <a name="replacement-pc-mode"></a>取代電腦模式


在取代電腦模式中，會關閉 Surface Hub 的內嵌電腦，然後將外部電腦連線到 Surface Hub。 連接到取代電腦連接埠，就可以存取 Surface Hub 上的主要周邊設備，包括螢幕、手寫筆及觸控功能。 這表示您的 Surface Hub 不會受益於 Windows 小組體驗，但您將可以彈性地提供和管理自己的 Windows 電腦。

### <a name="software-requirements"></a>軟體需求

您可以使用 64 位元版本的 Windows 10 家用版、Windows 10 專業版和 Windows 10 企業版，在取代電腦模式中執行 Surface Hub。 您可以從 Microsoft 下載中心下載 [Surface Hub 取代電腦驅動程式套件](https://www.microsoft.com/download/details.aspx?id=52210)。 建議您在打算當成取代電腦使用的任何電腦上安裝這些驅動程式。

### <a name="hardware-requirements"></a>硬體需求

Surface Hub 可與一系列的硬體相容。 選擇確認相容的處理器與記憶體用於取代電腦，如此才會支援您將要使用的程式。 您的取代電腦硬體必須支援 64 位元版本的 Windows 10。

### <a name="graphics-adapter"></a>圖形介面卡

在取代電腦模式中，Surface Hub 可支援任何能產生 DisplayPort 訊號的圖形介面卡。 使用符合 Surface Hub 的解析度和重新整理頻率的圖形介面卡，將可改善您的體驗。 例如，使用 120Hz 視訊訊號，可在 Surface Hub 上獲得最佳與建議的取代電腦體驗。

**55 英吋 Surface Hub** - 使用可達 1080p 解析度、120Hz 的圖形卡，能獲得最佳體驗。

**84英吋 Surface Hub** - 使用能輸出四個 DisplayPort 1.2 串流，產生 2160p、120Hz (3840 x 2160、120Hz 垂直重新整理) 的圖形卡，能獲得最佳體驗。 我們已經確認這可以配合 NVIDIA Quadro K2200、NVIDIA Quadro K4200、NVIDIA Quadro M6000、AMD FirePro W5100、AMD FirePro W7100 及 AMD FirePro W9100 運作。 圖形卡不只這些，其他圖形卡也可以從其他廠商取得。 

直接與圖形卡廠商連絡，取得最新的驅動程式。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>圖形卡廠商</th>
<th>驅動程式下載頁面</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NVIDIA</p></td>
<td><p><a href="http://nvidia.com/Download/index.aspx" data-raw-source="[http://nvidia.com/Download/index.aspx](http://nvidia.com/Download/index.aspx)">http://nvidia.com/Download/index.aspx</a></p></td>
</tr>
<tr class="even">
<td><p>AMD</p></td>
<td><p><a href="http://support.amd.com/en-us/download" data-raw-source="[http://support.amd.com/en-us/download](http://support.amd.com/en-us/download)">http://support.amd.com/en-us/download</a></p></td>
</tr>
<tr class="odd">
<td><p>Intel</p></td>
<td><p><a href="https://downloadcenter.intel.com/" data-raw-source="[https://downloadcenter.intel.com/](https://downloadcenter.intel.com/)">https://downloadcenter.intel.com/</a></p></td>
</tr>
</tbody>
</table>

 

### <a name="ports"></a>連接埠

55 英吋 Surface Hub 上的取代電腦連接埠。

![顯示 55 英吋 Surface Hub 上取代電腦連接埠的影像。](images/sh-55-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>說明</th>
<th>類型</th>
<th>介面</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>電腦視訊</p></td>
<td><p>視訊輸入</p></td>
<td><p>DP 1.2</p></td>
<td><ul>
<li><p>以 1080p、120 Hz 全螢幕顯示，再加上音訊</p></li>
<li><p>HDCP 相容</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>內部周邊設備</p></td>
<td><p>USB 輸出</p></td>
<td><p>USB 2.0 類型 B</p></td>
<td><ul>
<li><p>觸控</p></li>
<li><p>手寫筆</p></li>
<li><p>喇叭</p></li>
<li><p>麥克風</p></li>
<li><p>相機</p></li>
<li><p>NFC 感應器</p></li>
<li><p>周遭環境光感應器</p></li>
<li><p>被動式紅外線感應器</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 集線器</p></td>
<td><p>USB 輸出</p></td>
<td><p>USB 2.0 類型 B</p></td>
<td><ul>
<li><p>下方的 USB 連接埠</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

84 英吋 Surface Hub 上的取代電腦連接埠。

![顯示 84 英吋 Surface Hub 上取代電腦連接埠的影像。](images/sh-84-rpc-ports.png)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th>說明</th>
<th>類型</th>
<th>介面</th>
<th>詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>電腦視訊</p></td>
<td><p>視訊輸入</p></td>
<td><p>DP 1.2 (2x)</p></td>
<td><ul>
<li><p>以 2160p、120 Hz 全螢幕顯示，再加上音訊</p></li>
<li><p>HDCP 相容</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>內部周邊設備</p></td>
<td><p>USB 輸出</p></td>
<td><p>USB 2.0 類型 B</p></td>
<td><ul>
<li><p>觸控</p></li>
<li><p>手寫筆</p></li>
<li><p>喇叭</p></li>
<li><p>麥克風</p></li>
<li><p>相機</p></li>
<li><p>NFC 感應器</p></li>
<li><p>周遭環境光感應器</p></li>
<li><p>被動式紅外線感應器</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>USB 集線器</p></td>
<td><p>USB 輸出</p></td>
<td><p>USB 2.0 類型 B</p></td>
<td><ul>
<li><p>下方的 USB 連接埠</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="replacement-pc-setup-instructions"></a>取代電腦安裝指示

**使用取代電腦模式**

1.  下載並在取代電腦上安裝 [Surface Hub 取代電腦驅動程式套件](https://www.microsoft.com/download/details.aspx?id=52210)。

    >[!NOTE]
    >建議您在取代電腦上設定睡眠或休眠，以便在不使用 Surface Hub 時將顯示器關閉。

2.  使用電源纜線旁邊的電源開關來關閉 Surface Hub。

3.  從 Surface Hub 的取代電腦連接埠將纜線連接到替代電腦。 這些連接埠通常會覆蓋著卸除式塑膠封蓋。

    55 英吋 Surface Hub -- 連接一條 DisplayPort 纜線和兩條 USB 纜線。

    84 英吋 Surface Hub -- 連接兩條 DisplayPort 纜線和兩條 USB 纜線。

4.  將模式開關切換至「取代電腦」。**** 模式開關位在取代電腦連接埠的旁邊。

5.  使用電源纜線旁邊的電源開關來開啟 Surface Hub。

6.  按下 Surface Hub 右側的電源按鈕。

您可以隨時將 Surface Hub 切換成使用內部電腦。

**切換回內部電腦**

1.  使用電源纜線旁邊的電源開關來關閉 Surface Hub。

2.  將模式開關切換至內部電腦。 模式開關位在取代電腦連接埠的旁邊。

3.  使用電源纜線旁邊的電源開關來開啟 Surface Hub。

 
## <a name="video-out"></a>Video Out (視訊輸出)
 
Surface Hub 包括一個 Video Out 連接埠，可用於將視覺內容從 Surface Hub 鏡像處理到另一部顯示器。

### <a name="ports"></a>連接埠

55 吋 Surface Hub 上的 Video Out 連接埠

![影片輸出埠的圖例。](images/video-out-55.png)

84 吋 Surface Hub 上的 Video Out 連接埠

![影片輸出埠的圖例。](images/video-out-84.png)

<table>
<thead>
<tr class="header">
<th>描述</th>
<th>類型</th>
<th>介面</th>
<th>功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>視訊輸出鏡像</p></td>
<td><p>視訊輸出</p></td>
<td><p>視訊輸出</p></td>
<td><ul>
<li><p>支援連接至標準 DisplayPort 監視器 (僅支援 1080p60 顯示解析度、24bpp 的 x4 連結)</p></li>
<li><p>支援使用 DisplayPort 轉 HDMI 轉接器搭配 HDMI 監視器 (支援 1080p60) 使用</p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="cables"></a>纜線

55 吋和 84 吋 Surface Hub 裝置已通過使用認證的 DisplayPort 和 HDMI 纜線的測試。  廠商有在銷售可搭配 Surface Hub 使用的較長纜線，但是只有已通過測試實驗室認證的纜線，能確實搭配集線器使用。 舉例來說，經認證的 DisplayPort 纜線最長只到 3 公尺，但是仍有許多廠商銷售 3 倍長度的纜線。 如果需要長纜線，我們極力建議使用 HDMI。  HDMI 有許多具成本效益的長纜線方案，包括使用中繼器。 如果偵測到 HDMI 接收器，幾乎每個 DisplayPort 來源都會自動切換成 HDMI 訊號。


## <a name="bluetooth-accessories"></a>藍牙配件

使用藍牙，將下列配件連線到 Surface Hub︰

- 滑鼠
- 鍵盤
- 耳機
- 喇叭

>[!NOTE]
>連接藍牙耳機或喇叭之後，您可能需要變更[預設麥克風及喇叭設定](local-management-surface-hub-settings.md)。
