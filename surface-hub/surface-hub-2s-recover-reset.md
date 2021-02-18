---
title: Surface Hub 2S 的重設及復原
description: 瞭解如何復原和重設 Surface Hub 2S。
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
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342973"
---
# Surface Hub 2S 的重設及復原

如果您遇到 Surface Hub 2S 的問題，您可以將裝置重設為出廠設定，或使用 USB 磁碟機進行還原。

若要開始，請以系統管理員認證來登錄 Surface Hub 2S、開啟 **設定應用程式、** 選取更新 **&安全性**， **然後選取復原**。

## 重設裝置

   > [!IMPORTANT]
   > 在重設裝置之前，請確認您擁有 BitLocker 金鑰，因為稍後會提示您。 若要深入瞭解，請參閱儲存 [BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。

1. 若要重設裝置 **，請選取**開始使用。

2. 出現 **準備好重設此裝置** 視窗時，請選取重 **設**。 
  
   > [!IMPORTANT]
   > 當中樞重新開機至修復磁碟分割時，會提示您輸入 BitLocker 鍵。 略過該提示會導致重設失敗。 輸入 BitLocker 金鑰後，Hub 會從修復磁碟分割重新安裝作業系統。 這最多可能需要一小時才能完成。
  
3. 若要重新設定裝置，請執行第一次安裝程式。

4. 如果您使用 Microsoft Intune 或其他行動裝置管理解決方案管理裝置，請淘汰並刪除上一個記錄，然後重新註冊新裝置。 詳細資訊請參閱使用抹 [除、](https://docs.microsoft.com/intune/devices-wipe)淘汰或手動取消註冊裝置來移除裝置。

   > [!div class="mx-imgBorder"]
   > ![*Surface Hub 2S 的重設及復原*](images/sh2-reset.png)
   <br/>*圖 1。 Surface Hub 2S 的重設及復原* 

## 使用 USB 修復磁碟機復原 Surface Hub 2S

Surface Hub 2S 的新功能，現在您可以使用修復映射重新安裝裝置。

### 從 USB 磁碟機進行復原

使用 Surface Hub 2S，您可以使用修復映射重新安裝裝置。 這樣一來，如果您遺失 BitLocker 金鑰，或如果您不再擁有設定應用程式的系統管理員認證，您可以將裝置重新安裝到出廠設定。

>[!NOTE]
>使用儲存空間為 8 GB 或 16 GB 的 USB 3.0 磁片磁碟機，格式為 FAT32。

1. 從另一部電腦，從 [Surface Recovery](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 網站下載 .zip 檔案復原映射，然後返回這些指示。 

1. 在工作列上的搜尋方塊中，輸入**修復磁碟機**，然後從結果中選取建立修復**磁碟機****機或**修復磁碟機機。 您可能需要輸入系統管理員密碼或確認您的選擇。

1. 在使用者帳戶**控制方塊中**，選取**Yes。**

1. 請務必清除備份系統檔案**** 到修復磁碟機核取方塊，然後選取下**一步**。

1. 選取您的 USB 磁碟機，然後選取下一 **>建立**。  有些公用程式需要複製到修復磁碟機機，因此這可能需要幾分鐘的時間。

1. 當修復磁碟機準備就緒時， **請選取完成**。

1. 按兩下您先前下載的復原映射 .zip 檔案以開啟該檔案。

1. 從復原映射資料夾中選取所有檔案，將它們複製到 USB 磁碟機的根目錄，然後選取選擇 **以取代目的地中的檔案**。

1. 檔案複製完成後，請選取工作列上的安全移除 **硬體與彈出** 媒體圖示，然後移除您的 USB 磁碟機。

1. 將 USB 磁碟機連接到 Surface Hub 2S 上的任何 USB-C 或 USB-A 埠。

1. 關閉集線器，然後執行下列步驟從 USB 磁碟機開機：

   1. 按下音量降低按鈕時，請按電源按鈕。
   1. 繼續按這兩個按鈕，直到您看到 Windows 標誌。
   1. 放開電源按鈕，但繼續按住音量降低按鈕，直到安裝 UI 開始。

      ![*使用降低音量和電源按鈕來啟動復原*](images/sh2-keypad.png)
      <br>*圖 2. 音量和電源按鈕*

1. 在語言選取畫面上，選取 Surface Hub 2S 的顯示語言。

1. 選取**從磁碟機復原並****完全清除硬碟**，**然後選取復原**。 如果系統提示您輸入 BitLocker 鍵，請選取 **跳過此磁碟機**。 Surface Hub 2S 會重新開機數次，大約需要 30 分鐘才能完成復原程式。

第一次設定畫面出現時，請移除 USB 磁碟機。

## 連絡客戶支援

如果您有任何問題或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。
