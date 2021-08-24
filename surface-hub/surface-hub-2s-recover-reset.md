---
title: 2S 的重設Surface Hub復原
description: 瞭解如何在 2S 中復原Surface Hub重設。
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
ms.openlocfilehash: 28e067852422dd8c4a4b82c337e94eaa94290fd9
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911358"
---
# <a name="reset-and-recovery-for-surface-hub-2s"></a>2S 的重設Surface Hub復原

如果您遇到 2S Surface Hub問題，您可以將裝置重設為出廠設定，或使用 USB 磁碟機還原。

若要開始，請以系統管理員認證Surface Hub 2S，開啟 設定**應用程式，** 選取 &**安全性**，然後選取修復 **。**

## <a name="reset-the-device"></a>重設裝置

   > [!IMPORTANT]
   > 在重設裝置之前，請確認您擁有 BitLocker 金鑰，因為稍後會提示您。 若要深入瞭解，請參閱儲存 [BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。

1. 若要重設裝置，請**選取**入門。

2. 當出現 **準備重設此裝置** 視窗時，請選取 重 **設**。 
  
   > [!IMPORTANT]
   > 當 Hub 重新開機至修復分區時，它會提示您輸入 BitLocker 鍵。 略過提示會造成重設失敗。 輸入 BitLocker 金鑰後，Hub 會從修復分區重新安裝作業系統。 這最多可能需要一小時才能完成。
  
3. 若要重新設定裝置，請執行第一次安裝程式。

4. 如果您使用手機或其他行動裝置Microsoft Intune管理裝置，請淘汰並刪除先前的記錄，然後重新註冊新裝置。 若要詳細資訊，請參閱使用 [抹除、](https://docs.microsoft.com/intune/devices-wipe)淘汰或手動取消註冊裝置來移除裝置。

   > [!div class="mx-imgBorder"]
   > ![*重設及復原 Surface Hub 2S*。](images/sh2-reset.png)
   <br/>*圖 1。 2S 的重設Surface Hub復原* 

## <a name="recover-surface-hub-2s-by-using-a-usb-recovery-drive"></a>使用 USB Surface Hub磁碟機復原 2S

在 Surface Hub 2S 中新增功能，您現在可以使用修復影像重新安裝裝置。

### <a name="recovery-from-a-usb-drive"></a>從 USB 磁碟機復原

您可以使用 Surface Hub 2S，使用修復影像重新安裝裝置。 這麼做之後，如果您遺失 BitLocker 金鑰，或您不再擁有該 App 的系統管理員認證，您可以將裝置重新安裝到設定設定。

>[!NOTE]
>使用 8 GB 或 16 GB 儲存空間的 USB 3.0 磁片磁碟機，格式為 FAT32。

1. 從另一部電腦，從 Surface [Recovery](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) .zip下載檔案復原影像，然後返回這些指示。 

1. 在工作列上的搜尋方塊中，輸入**修復**磁碟機，然後從結果選取建立**** 修復**磁碟機或修復**磁碟機。 您可能需要輸入系統管理員密碼或確認您的選擇。

1. 在使用者帳戶**控制方塊中****，選取**是 。

1. 請務必清除將系統檔案備份到修復 **磁碟機核取方塊，** 然後選取下 **一步**。

1. 選取您的 USB 磁碟機，然後選取 > **建立**。  有些公用程式需要複製到修復磁碟機，因此這可能需要幾分鐘的時間。

1. 復原磁碟機準備就緒時， **請選取**完成 。

1. 按兩下您先前下載.zip的復原影像以開啟該檔案。

1. 選取復原圖像資料夾中的所有檔案，將它們複製到 USB 磁碟機的根目錄，然後選取選擇以取代目的地 **中的檔案**。

1. 檔案複製完成後，請選取工作列上的安全移除硬體和 **彈出** 媒體圖示，然後移除您的 USB 磁碟機。

1. 連線 USB 磁碟機到 2S 上的任何 USB-C 或 USB-A 埠Surface Hub埠。

1. 關閉集線器，然後執行下列步驟從 USB 磁碟機啟動：

   1. 按向下音量按鈕時，請按 Power 按鈕。
   1. 繼續按這兩個按鈕，直到您看到Windows標誌。
   1. 放開 Power 按鈕，但繼續按住向下音量按鈕，直到安裝 UI 開始。

      ![*使用降低音量和電源按鈕來啟動復原*。](images/sh2-keypad.png)
      <br>*圖 2. 音量和電源按鈕*

1. 在語言選取畫面上，選取您的 2S Surface Hub語言。

1. 選取 **從磁碟機復原** 並 **完全清理磁碟機**， **然後選取**復原 。 如果系統提示您輸入 BitLocker 鍵，請選取 **跳過此磁碟機**。 Surface Hub 2S 重新開機數次，大約需要 30 分鐘才能完成復原程式。

第一次設定畫面出現時，請移除 USB 磁碟機。

## <a name="contact-support"></a>連絡客戶支援

如果您有任何問題或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。
