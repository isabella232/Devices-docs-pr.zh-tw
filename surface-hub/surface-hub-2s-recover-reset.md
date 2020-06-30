---
title: 重設及恢復 Surface Hub 2
description: 瞭解如何復原及重設 Surface Hub 秒數。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: fb7e1a39d96c2da6d27d5558ebefcff52bd6e159
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831453"
---
# 重設及恢復 Surface Hub 2

如果您遇到 Surface Hub 2 的問題，您可以使用 USB 磁片磁碟機將裝置重設成出廠設定或還原。

若要開始，請使用系統管理員認證登入 Surface Hub 2，開啟 [**設定**] 應用程式，選取 [**更新 & 安全性**]，然後選取 [復原 **]。**

## 重設裝置

1. 若要重設裝置，請選取 [**開始**使用]。
2. 出現 [**準備好重設此裝置**] 視窗時，請選取 [**重設**]。 
  
  >[!NOTE]
  >Surface Hub 2 秒從恢復分區重新安裝作業系統。 這可能需要長達一小時的時間才能完成。
  
3. 若要重新設定裝置，請執行第一次設定程式。
4. 如果您使用 Microsoft Intune 或其他行動裝置管理解決方案管理裝置，請停用並刪除前一筆記錄，然後重新註冊新的裝置。 如需詳細資訊，請參閱[使用 [擦除]、[停用] 或 [手動 unenrolling 裝置] 移除裝置](https://docs.microsoft.com/intune/devices-wipe)。

![* Surface Hub 2 秒的重設與復原 *](images/sh2-reset.png)<br>
*圖 1。 重設及恢復 Surface Hub 2* 

## 使用 USB 恢復磁片磁碟機來復原 Surface Hub 的2到2秒

在 Surface Hub 2 的新功能中，您現在可以使用復原影像來重新安裝裝置。

### 從 USB 磁片磁碟機復原

使用 Surface Hub 2-2，您可以使用復原影像來重新安裝裝置。 如此一來，如果您遺失 BitLocker 金鑰，或您不再擁有 [設定] 應用程式的系統管理員認證，就可以將裝置重新安裝到出廠設定。

>[!NOTE]
>使用具有 8 GB 或 16 GB 儲存空間的 USB 3.0 磁片磁碟機，格式化為 FAT32 格式。

1. 從個別的電腦，從[表面恢復網站](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s)下載 .zip 檔案復原影像，然後返回這些指示。 
1. 將下載的檔案解壓縮至 USB 磁片磁碟機的根目錄。  
1. 將 USB 磁片磁碟機連接至 Surface Hub 2 上的任何 USB 或 USB 埠。
1. 關閉裝置：
   1. 按住 [音量] 按鈕，然後按下 [電源] 按鈕。
   1. 一直按住兩個按鈕，直到您看到 [Windows 標誌]。
   1. 放開電源按鈕，但繼續按住音量，直到安裝 UI 開始。

    ![* 使用 [音量] 和 [電源] 按鈕來啟動復原 *](images/sh2-keypad.png) <br>
   **圖 2. [音量] 和 [電源] 按鈕**

1. 在 [語言選取範圍] 畫面上，選取 Surface Hub 2 秒的顯示語言。
1. 選取 [**從磁片磁碟機復原**] 並**完全清除磁片磁碟機**，然後選取 [**復原**]。 如果系統提示您輸入 BitLocker 金鑰，請選取 [**略過此磁片磁碟機**]。 Surface Hub 2 秒重新開機幾次，並花大約30分鐘的時間完成恢復程式。

當第一次設定畫面出現時，請移除 USB 磁片磁碟機。

## 連絡客戶支援

如果您有任何疑問或需要協助，您可以[建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。
