---
title: 使用 Surface Hub Recovery Tool
description: 如何使用 Surface Hub 恢復工具來重新影像 SSD。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/22/2018
ms.localizationpriority: medium
ms.openlocfilehash: 1988a6ed59525d7dc77872e532247dbc50f01bdf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832169"
---
# 使用 Surface Hub Recovery Tool

[Microsoft Surface Hub 恢復工具](https://www.microsoft.com/download/details.aspx?id=52210)可協助您使用 Windows 10 傳統型裝置重新鏡像 Surface Hub 固態磁片磁碟機（SSD），而不需呼叫支援或取代 SSD。 透過此工具，您可以重新組成具有未知系統管理員密碼的 SSD、啟動錯誤、無法完成雲端復原，或針對舊版作業系統的裝置進行重新鏡像。 此工具不會修正實際損毀的 SSDs。

若要使用 [恢復] 工具重新影像 Surface Hub SSD，您必須從 Surface Hub 中移除 SSD，將磁碟機連接至 USB 至 SATA 纜線，然後將纜線連接至安裝了復原工具的桌上型電腦。 如需如何從 Surface Hub 移除現有磁片磁碟機的詳細資訊，請參閱[Surface HUB SSD 取代](surface-hub-ssd-replacement.md)。

> [!IMPORTANT]
> 請勿讓裝置移至 [睡眠] 或 [中斷影像檔案的下載]。

如果此工具無法在您的磁片磁碟機中進行磁片映射，請與[Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人員聯繫。

## 必要條件

### Mandatory

- 運行64位版本的 Windows 10 版本1607或更高版本的主機電腦。
- 網路與網際網路存取
- 開啟 USB 2.0 或更多埠
- USB 至 SATA 纜線
- 主機電腦上有 10 GB 的可用磁碟空間
- SSDs 隨附 Surface Hub 或支援部門提供的 SSD 來取代。 不支援 Microsoft 未提供的 SSDs。

### 建議執行

- 高速網際網路連線
- 開啟 USB 3.0 埠
- USB 3.0 或更高的 USB 至 SATA 纜線
- 已使用下列的纜線製作與模型來測試影像工具：
    - Startech USB312SAT3CB
    - Rosewill RCUC16001
    - Ugreen 20231

## 下載 Surface Hub 中心恢復工具

Surface Hub 恢復工具可從[Surface Hub 工具](https://www.microsoft.com/download/details.aspx?id=52210)的 [ **SurfaceHub_Recovery_v1.14.137.0.msi**的檔案名] 中下載。

若要開始下載，請按一下 [**下載**]，從清單中選擇 [ **SurfaceHub_Recovery_v1.14.137.0.msi** ]，然後按 **[下一步]**。 從快顯視窗中，選擇下列其中一項：

- 按一下 [**執行**]，立即開始安裝。
- 按一下 [**儲存**] 以將下載內容複寫到您的電腦，以供日後安裝。

在主機電腦上安裝 Surface Hub 恢復工具。

## 執行 Surface Hub 恢復工具

1. 在主機電腦上，選取 [**開始**] 按鈕，在左側的 [字母順序] 清單中滾動，然後選取 [恢復工具] 快捷方式。

    ![Microsoft Surface Hub 恢復工具快速鍵](images/shrt-shortcut.png)

2. 按一下 **\[開始\]**。

    ![[恢復工具] [開始] 按鈕](images/shrt-start.png)

3. 在 [**指導**方針] 視窗中，按一下 **[下一步]**。

    ![請勿讓您的電腦移至 [睡眠] 指南](images/shrt-guidance.png)

4. 按一下 **[是]** 下載影像。 下載復原影像所需的時間取決於網際網路連線速度。 在一般的企業連線中，最多可能需要一個小時的時間來下載8GB 圖像檔案。

    ![下載影像？](images/shrt-download.png)

5. 下載完成後，工具會指示您連接 SSD 磁片磁碟機。 如果工具無法找到已附加的磁片磁碟機，很可能是使用纜線不會將 SSD 的名稱報告給 Windows。  在繼續之前，影像工具必須找到磁碟機的名稱為「LITEON L CH-128V2S USB 裝置」。  如需如何從 Surface Hub 移除現有磁片磁碟機的詳細資訊，請參閱[Surface HUB SSD 取代](surface-hub-ssd-replacement.md)。

    ![連接 SSD](images/shrt-drive.png)

6. 辨識磁碟機後，請按一下 [**開始**] 以開始重新影像處理常式。 在警告中，磁片上的所有資料都會被清除，按一下 **[確定]**。

    ![開始重新影像 SSD](images/shrt-drive-start.png)

    在將系統映射套用到磁片磁碟機之前，SSD 會進行重新分區及格式化。 複製系統二進位檔案大約需要30分鐘，但可能需要較長的時間，視您的 USB 匯流排速度、使用的纜線，或系統上安裝的防毒軟體而定。

    ![複製完成](images/shrt-done.png)

    ![映射結束](images/shrt-complete.png)

## 疑難排解及常見問題

問題 | 附註
--- | ---
此工具無法將 SSD 影像 | 請確定您使用的是 factory 提供的 SSD，以及其中一個已測試的纜線。
此映射程式會顯示暫停/凍結狀態 | 關閉並重新啟動 Surface Hub 恢復工具，不會對 SSD 產生任何不正確的影響，是安全的。
工具無法辨識此磁碟機 | 確認 Surface Hub SSD 已列舉為精簡式磁片磁碟機，"LITEON L CH-128V2S USB 裝置"。  如果該磁碟機被識別為另一個已命名的裝置，您目前的纜線不相容。 試試上面所列的另一根電纜或其中一個已測試的電纜。
錯誤：-2147024809 | 開啟磁片管理器並移除 Surface Hub 磁片磁碟機上的分區。  中斷連線並將磁碟機重新連接到主機電腦。 重新開機影像工具。

如果此工具無法在您的磁片磁碟機中進行磁片映射，請與[Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人員聯繫。
