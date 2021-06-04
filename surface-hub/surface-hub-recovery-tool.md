---
title: 使用 Surface Hub Recovery Tool
description: 如何使用 Surface Hub 修復工具來重新映射處理 SSD。
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
ms.openlocfilehash: 0cc444eab51e9c3cc0bf2f9c2f0c36ac491906b1
ms.sourcegitcommit: 7b09b4bc757c5385c4f5560713cb03448afde9ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2021
ms.locfileid: "11339364"
---
# 使用 Surface Hub Recovery Tool

[Microsoft Surface Hub 修復](https://www.microsoft.com/download/details.aspx?id=52210)工具可協助您將 Surface Hub 實心磁片磁碟機 (SSD) 使用 Windows 10 桌面裝置重新映射，而不需要致電支援人員或更換 SSD。 使用這項工具，您可以為具有未知的系統管理員密碼、開機錯誤、無法完成雲端復原的 SSD，或是作業系統較舊版本的裝置重新建立映射。 此工具無法修正實體損壞的 SSD。

若要使用修復工具重新映射 Surface Hub SSD，您必須從 Surface Hub 移除 SSD、將磁片磁碟機連接到 USB-to-SATA 纜線，然後將纜線連接到安裝修復工具的桌上型電腦。 若要瞭解如何從 Surface Hub 移除現有磁片磁碟機，請參閱[Surface Hub SSD 更換。](surface-hub-ssd-replacement.md)

> [!IMPORTANT]
> 請勿讓裝置進入睡眠或中斷圖像檔案的下載。

如果工具無法重新映射您的硬碟，請聯絡 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人員。

##  <a name="prerequisites"></a>必要條件

###  <a name="mandatory"></a>Mandatory

- 主機電腦是 64 位版本的 Windows 10，版本 1607 或更新版本。
- 網路與網際網路存取
- 開啟 USB 2.0 或更大的埠
- USB-to-SATA 纜線
- 主機電腦上 10 GB 的可用磁碟空間
- SSD 會與 Surface Hub 或支援人員提供的 SSD 一起提供，做為替代產品。 不支援 Microsoft 未提供的 SSD。

###  <a name="recommended"></a>建議執行

- 高速網際網路連接
- 開啟 USB 3.0 埠
- USB 3.0 或更高版本的 USB-to-SATA 纜線
- 影像工具已使用下列纜線的製造和型號進行測試：
    - Startech USB312SAT3CB
    - Rosew RCUC16001
    - Ugreen 20231

##  <a name="download-surface-hub-recovery-tool"></a>下載 Surface Hub 修復工具

Surface Hub 修復工具可從適用于[IT](https://www.microsoft.com/download/details.aspx?id=52210)的 Surface Hub 工具下載，檔案名為**SurfaceHub_Recovery_v2.7.139.0.msi。**

> [!IMPORTANT]
> 此版本于 2021 年 2 月 11 日發行，取代先前無法再運作的版本。 如果您先前下載過此工具，請卸載並安裝目前版本。

若要開始下載，請按一下****[下載**SurfaceHub_Recovery_v2.7.139.0.msi，然後**按 [下一**步**。 從快顯視窗選擇下列其中一項：

- 按一下 **[** 執行並立即開始安裝。
- 按一下 **[儲存** 以將下載複製到您的電腦，供日後安裝。

在主機電腦上安裝 Surface Hub 修復工具。

##  <a name="run-surface-hub-recovery-tool"></a>執行 Surface Hub 修復工具

1. 在主 PC 上，選取 **開始按鈕、** 捲動左側的字母清單，然後選取修復工具快速鍵。

    ![Microsoft Surface Hub 修復工具快速鍵](images/shrt-shortcut.png)

2. 按一下 **\[開始\]**。

    ![修復工具的開始按鈕](images/shrt-start.png)


3. 在指引 **視窗中** ，按一下 [下 **一步**。

    ![請勿讓電腦進入睡眠指引](images/shrt-guidance.png)

4. 在選取圖像視窗中，按一下**RS2**或其後續版本******20H2，** 選取 [繼續，然後選取**下載影像。**

     ![修復工具選取圖像 ](images/shrt-select-image.png) ![ 修復工具下載圖像](images/shrt-download-image.png)

5. 下載復原映射的時間取決於網際網路連線速度。 在一般的公司關係上，最多可能需要一小時的時間下載 8 GB 圖像檔案。

    ![下載圖像](images/shrt-download.png)



5. 下載完成後，工具會指示您連接 SSD 磁片磁碟機。 如果工具找不到附加的磁片磁碟機，使用中的纜線很有可能不會向 Windows 報告 SSD 名稱。  影像工具必須先將光碟機名稱尋找為「LITEON L CH-128V2S USB 裝置」，才能繼續。  若要瞭解如何從 Surface Hub 移除現有磁片磁碟機，請參閱[Surface Hub SSD 更換。](surface-hub-ssd-replacement.md)

    ![連接 SSD](images/shrt-drive.png)

6. 當硬碟被識別時，按一下 **[開始** 著手進行重新映射處理。 在硬碟上所有資料都會清除的警告上，按一下 **[確定**。



    將系統映射新用至磁片磁碟機之前，系統會重新區整並格式化 SSD。 複製系統二進位檔案大約需要 30 分鐘，但可能需要較長的時間，視 USB 母線的速度、使用的纜線或您系統安裝的防毒軟體而不同。



##  <a name="troubleshooting-and-common-problems"></a>疑難排解和常見問題

問題 | 附註
--- | ---
工具無法對 SSD 進行影像 | 請確定您使用的是出廠時提供的 SSD 和其中一個測試纜線。
重新製作程式顯示為暫停/凍結 | 可以放心關閉並重新啟動 Surface Hub 修復工具，對 SSD 不會造成任何影響。
工具無法識別該磁碟機 | 確認 Surface Hub SSD 列舉為Lite-On LITEON L CH-128V2S USB 裝置」的磁片磁碟機。  如果硬碟被識別為另一個已命名的裝置，表示您目前的纜線不相容。 請嘗試上述其他纜線或其中一條測試纜線。
錯誤：-2147024809 | 開啟磁片管理器並移除 Surface Hub 磁片磁碟機上的磁碟分割。  將硬碟中斷連接並重新連接到主機電腦。 重新開機影像工具。

如果工具無法重新映射您的硬碟，請聯絡 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人員。

##  <a name="version-history"></a>版本歷程記錄


###  <a name="version-v2.7.139.0"></a>版本 2.7.139.0

*發行日期：2021 年 2 月 11 日*<br>
此版本的 Surface Hub 修復工具新增下列支援：

- 安全性更新


###  <a name="version-v2.0.139.0"></a>版本 2.0.139.0

> [!IMPORTANT]
> 此版本已無法運作。 請下載上列的目前版本。 

*發行日期：2020 年 12 月 18 日*<br>
此版本的 Surface Hub 修復工具新增下列支援：
- 更新以支援 Windows 10 小組 2020 更新 (20H2) 
- 使用者體驗改進
- 架構變更
- 遙測新增專案

