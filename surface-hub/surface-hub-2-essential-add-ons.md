---
title: 適用于 Surface Hub 2 的 Windows 10 專業版與企業版的重要附加元件
description: 本文提供有關您可以在 Surface Hub 2 上的 Windows 10 專業版或企業版中使用之選用附屬元件的資訊。
keywords: Surface Hub、Windows 10、desktop、指紋辨識器、Windows Hello
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.author: greglin
ms.date: 09/18/2020
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: 24998848f16803585bc414d50e2099745943dcc7
ms.sourcegitcommit: 13015036a3e5cb5909924d7e4289473a1572cf9d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/19/2020
ms.locfileid: "11030420"
---
# 適用于 Surface Hub 2 的 Windows 10 專業版與企業版的重要附加元件

如果您已從 Windows 10 團隊遷移至 Windows 10 專業版或 Surface Hub 2 上的企業，您可以選擇各種不同的附件，這些附屬元件是透過 USB-C、USB A、HDMI 或藍牙進行連接。 

## Surface Hub 2 指紋辨識器

如果您在 Surface Hub 2 上執行 Windows 10 專業版或 Windows 10 企業版，您可以使用選用的 Surface Hub 2 指紋辨識器（使用 [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)的生物特徵驗證選項）登入。

### 依據

商業客戶可以透過其表面授權的裝置轉銷商來放置訂單。

**若要使用 Surface Hub 2 指紋讀取程式：**

1. 將指紋辨識器插入任何位於裝置每側的 USB C 擋板埠。
2. **移至 [開始**  >  ]**設定**  > **帳戶**  > 登**入選項**  > **Windows Hello 指紋**可供您註冊指紋。

如需設定指紋辨識器以使用 Windows Hello 登入的詳細資訊，請參閱下列內容：

- [了解與設定 Windows Hello](https://support.microsoft.com/help/4028017/windows-learn-about-windows-hello-and-set-it-up)
- [企業版中的 Windows Hello 生物特徵](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-biometrics-in-enterprise)。

  
### 表 1. Surface Hub 2 指紋辨識器技術規格


| 元件                       | 說明                                                                                                                          |
| ------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| **USB**                         | 自訂的 USB 類型-C                                                                                                           |
| **系統需求**          | Windows 10 專業版（Windows 10 企業版）。                                                                                               |
| **Windows 認證**       | Windows 10                                                                                                                           |
| ** (遠) 的接受率** | 1/1.5 萬美元。 顯示生物特徵安全系統不正確地接受未經授權使用者的存取嘗試的可能性。 |
| **False 拒絕比率 (FRR) ** | 4.9%。 FRR 顯示生物識別安全系統不正確拒絕受授權使用者的存取嘗試的可能性。 |


> [!NOTE]
> 在 Surface Hub 2 上執行的 Windows 10 小組不支援 Surface Hub 2 指紋辨識器。 這是因為 Windows 10 小組已設計為允許多個使用者與會議會議室環境中的裝置互動。 
 
## Windows Hello 面孔知名度

Windows 10 專業版和企業版 Surface Hub 2 支援 Windows Hello 驗證，且需要 Windows Hello 認證相機附件。 請注意，表面中樞秒的內建相機並不是為驗證而設計，也不支援 Windows Hello。 如需詳細資訊，請參閱 [Windows Hello。](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)


## 音訊及視頻附件

您可以使用 USB C 或 USB 埠，延伸 Surface Hub 2 的音訊和視頻功能，以及音訊和相機外設。

如需建議附件的相關資訊，請參閱：

- [針對 Microsoft 團隊認證的 USB 音訊與視頻裝置](https://docs.microsoft.com/microsoftteams/devices/usb-devices)
- [Microsoft 團隊的 IP 手機認證](https://docs.microsoft.com/microsoftteams/devices/teams-ip-phones)



## 其他附件
Surface Hub 2 包含下列埠，可用於連接各種不同的裝置。 

- 1 x USB [計算] 模組上的埠 (位於 [顯示]) 
- bezels 上的 4 x USB C 埠
- 藍牙4.1 支援
- HDMI 2。0

 ![I/O 連線和物理按鈕的正面朝右和中下方視圖](images/hub2s-schematic.png)

如需詳細資訊，請參閱 [Surface Hub 2 到2埠和小鍵盤概述](surface-hub-2s-port-keypad-overview.md)


## 深入了解

- [在 Surface Hub 2 上設定 Windows 10 專業版或企業版](surface-hub-2-post-install.md)。