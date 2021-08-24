---
title: 使用 Surface Hub Recovery Tool
description: 如何使用修復工具Surface Hub復原工具重新映射 SSD。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: f472d42bba9270b117cfa8cb9b54eaeb020aefc4
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910978"
---
# <a name="using-the-surface-hub-recovery-tool"></a>使用 Surface Hub Recovery Tool

Microsoft Surface Hub[修復](https://www.microsoft.com/download/details.aspx?id=52210)工具可協助使用 Microsoft Surface Hub 桌面裝置重新映射您的 Surface Hub 固態硬碟 (SSD) Windows 10，而不需要撥打支援電話或更換 SSD。 使用此工具，您可以重新映射具有未知的系統管理員密碼、開機錯誤、無法完成雲端修復的 SSD，或是具有舊版作業系統的裝置。 此工具無法修正實體損壞的 SSD。

若要使用修復工具重新映射 Surface Hub SSD，您必須從 Surface Hub 移除 SSD、將磁片磁碟機連接到 USB 到 SATA 纜線，然後將纜線連接到安裝修復工具的桌上型電腦。 若要瞭解如何從您的磁片磁碟機移除現有磁片磁碟機Surface Hub，請參閱[Surface Hub更換 。](surface-hub-ssd-replacement.md)

> [!IMPORTANT]
> 請勿讓裝置進入睡眠狀態或中斷影像檔案的下載。

如果工具無法重新映射您的硬碟，請與支援[Surface Hub聯繫](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

## <a name="prerequisites"></a>必要條件

### <a name="mandatory"></a>Mandatory

- 主機電腦會以 64 位版本Windows 10版本 1607 或更新版本。
- 網路與網際網路存取
- 開啟 USB 2.0 或更大的埠
- USB 到 SATA 纜線
- 主機電腦上 10 GB 的免費磁碟空間
- 由支援提供Surface Hub或 SSD 作為替代的 SSD。 Microsoft 未提供的 SSD 不受支援。

### <a name="recommended"></a>建議執行

- 高速網際網路連接
- 開啟 USB 3.0 埠
- USB 3.0 或更高版本的 USB 到 SATA 纜線
- 影像工具已經過下列纜線的製作和模型測試：
    - Startech USB312SAT3CB
    - Rosew RCUC16001
    - Ugreen 20231

## <a name="download-surface-hub-recovery-tool"></a>下載Surface Hub修復工具

Surface Hub修復工具可從 it Surface Hub[的](https://www.microsoft.com/download/details.aspx?id=52210)檔案名下下載**SurfaceHub_Recovery_v2.7.139.0.msi。**

> [!IMPORTANT]
> 此版本于 2021 年 2 月 11 日發行，會取代先前不再運作的版本。 如果您先前下載過此工具，請卸載它並安裝目前版本。

若要開始下載，請按一下****[下載**SurfaceHub_Recovery_v2.7.139.0.msi，從**清單中選擇 [下載SurfaceHub_Recovery_v2.7.139.0.msi，然後按一下 [下**一步**。 從快顯視窗中，選擇下列其中一項：

- 按一下 **[執行** 以立即開始安裝。
- 按一下 **[儲存** 以將下載複製到您的電腦，供日後安裝。

在Surface Hub電腦上安裝修復工具。

## <a name="run-surface-hub-recovery-tool"></a>執行 Surface Hub修復工具

1. 在主機上，選取 **開始按鈕、** 捲動左側的字母順序清單，然後選取修復工具快捷方式。

    ![Microsoft Surface Hub修復工具快捷方式。](images/shrt-shortcut.png)

2. 按一下 **\[開始\]**。

    ![修復工具開始按鈕。](images/shrt-start.png)


3. 在 [ **指引」** 視窗中，按一下 [ **下一步**。

    ![請勿讓電腦進入睡眠指南。](images/shrt-guidance.png)

4. 在 [選取影像畫面> 視窗中，按一下**RS2**或後續的******20H2，** 選取 [繼續，然後**選取下載影像。**

     ![修復工具 選取影像。](images/shrt-select-image.png)
    ![修復工具下載圖像。](images/shrt-download-image.png)

5. 下載修復影像的時間取決於網際網路連線速度。 一般公司連接最多可能需要一小時，才能下載 8 GB 的圖像檔案。

    ![正在下載影像。](images/shrt-download.png)



5. 下載完成後，工具會指示您連接 SSD 磁片磁碟機。 如果工具找不到附加的磁片磁碟機，則使用中的纜線很有可能不會將 SSD 名稱Windows。  影像工具必須先將磁碟機名稱尋找為「LITEON L CH-128V2S USB 裝置」，才能繼續。  若要瞭解如何從您的磁片磁碟機移除現有磁片磁碟機Surface Hub，請參閱[Surface Hub更換 。](surface-hub-ssd-replacement.md)

    ![連線SSD。](images/shrt-drive.png)

6. 當硬碟被識別時 **，按一下** [開始>，開始重新映射程式。 在硬碟上所有資料都會清除的警告上，按一下 [ **確定**。



    在將系統映射適用于磁片磁碟機之前，系統會重新分區並格式化 SSD。 複製系統二進位檔案大約需要 30 分鐘，但可能需要較長的時間，視 USB 母線的速度、使用的纜線或系統上安裝的防毒軟體而不同。



## <a name="troubleshooting-and-common-problems"></a>疑難排解和常見問題

問題 | 附註
--- | ---
此工具無法將 SSD 圖像 | 請確定您使用的是出廠時提供的 SSD 和其中一條測試的纜線。
重新映射程式似乎已暫停/凍結 | 可以安全地關閉並重新啟動 Surface Hub修復工具，且不會對 SSD 造成任何影響。
工具無法識別硬碟 | 確認已Surface Hub SSD 作為Lite-On，即「LITEON L CH-128V2S USB 裝置」。  如果磁碟機被識別為另一個已命名的裝置，表示您目前的纜線不相容。 請嘗試其他纜線或上述其中一條已測試的纜線。
錯誤：-2147024809 | 開啟磁片管理器並移除磁片磁碟機上的Surface Hub分區。  中斷連接並重新連接硬碟至主機。 再次重新開機影像工具。

如果工具無法重新映射您的硬碟，請與支援[Surface Hub聯繫](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

## <a name="version-history"></a>版本歷程記錄


### <a name="version-v271390"></a>版本 2.7.139.0

*發行日期：2021 年 2 月 11 日*<br>
此版本的修復Surface Hub新增下列支援：

- 安全性更新


### <a name="version-v201390"></a>版本 v2.0.139.0

> [!IMPORTANT]
> 此版本已無法運作。 請下載上列的目前版本。 

*發行日期：2020 年 12 月 18 日*<br>
此版本的修復Surface Hub新增下列支援：
- 更新以支援 2020 Windows 10 團隊版 2020 (20H2) 
- 使用者體驗改良功能
- 架構變更
- 遙測新增專案

