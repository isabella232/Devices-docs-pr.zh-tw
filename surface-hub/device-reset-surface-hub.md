---
title: 重設或復原 Surface Hub
description: 說明 Surface Hub 的重設及復原程式，並提供指示。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重設 Surface Hub，復原
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406616"
---
# <a name="reset-or-recover-a-surface-hub"></a>重設或復原 Surface Hub

本文說明如何重設或復原 Microsoft Surface Hub。  

[重設 Surface Hub 會](#reset-a-surface-hub) 將其作業系統回到上一次累積 Windows 更新，並移除所有本地使用者檔案和設定資訊。 移除的資訊包括下列各項：

- 裝置帳戶
- 裝置當地系統管理員的帳戶資訊
- 網域加入或 Azure AD-join 資訊
- 行動裝置管理 (MDM) 註冊資訊
- 使用 MDM 或設定應用程式所設定設定的資訊

[從雲端復原 Surface Hub](#recover-a-surface-hub-from-the-cloud) 也會移除這項資訊。 此外，Surface Hub 會下載新的作業系統映射並安裝。 您可以指定復原程式是否保留儲存在 Surface Hub 上的其他資訊。 如果您需要復原 Surface [Hub，](surface-hub-recovery-tool.md) 但無法針對其中任何一個選項使用 Surface Hub，Surface Hub 修復工具會使用相同的作業系統映射。

## <a name="reset-a-surface-hub"></a>重設 Surface Hub

您可能需要重設 Surface Hub 的原因如下：

- 您正重新配置裝置以用於新的會議空間，並想要重新進行重新配置。
- 您想要變更在本機管理裝置的方式。
- 裝置帳戶或系統管理員帳戶的使用者名稱或密碼已遺失。
- 安裝更新之後，裝置執行會降低。

在重設程式期間，如果您看到螢幕很長一段時間，請稍候，不要執行任何動作。

> [!WARNING]
> 裝置重設程式最多可能需要六個小時。 在程式完成之前，請勿關閉或拔除 Surface Hub。 如果您中斷程式，裝置就會無法操作。 裝置需要保固服務才能再次運作。

1. 在 Surface Hub 上，開啟 **\[設定\]**。

   ![顯示 Surface Hub 的設定應用程式的影像。](images/sh-settings.png)

2. 選取 **更新&安全性**。

   ![顯示 Surface Hub &設定應用程式中更新安全性群組的影像。](images/sh-settings-update-security.png)

3. 選取 **復原**， **然後在重設**裝置下選取 **開始使用**。

   > [!IMPORTANT]
   > 在重設裝置之前，請確認您擁有 BitLocker 金鑰，因為稍後會提示您輸入。 若要深入瞭解，請參閱儲存 [BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。 當中樞重新開機至修復磁碟分割時，會提示您輸入 BitLocker 鍵。 略過該提示會導致重設失敗。
   
   ![顯示 Surface Hub 設定應用程式中的重設裝置選項的影像。](images/sh-settings-reset-device.png)

   重設程式完成之後，Surface Hub 會再次啟動 [第一個執行](first-run-program-surface-hub.md) 程式。 如果重設程式發生問題，它會將 Surface Hub 卷回先前現有的作業系統映射，然後顯示歡迎畫面。

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a>從雲端復原 Surface Hub

如果 Surface Hub 因某種原因無法使用，您仍可在未獲得 Microsoft 支援服務協助的情況下從雲端復原。 Surface Hub 可以從雲端下載全新的作業系統映射，然後使用該映射重新安裝其作業系統。

在下列情況下，您可能必須使用此類型的復原程式：

- [Surface Hub 或其相關帳戶已進入不穩定狀態](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub 已鎖定](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>從 **雲端程式復原** 需要有線連接，提供開放式網際網路連接， (Proxy 或其他驗證提示) 。

### <a name="recover-a-surface-hub-in-a-bad-state"></a>還原不良狀態中的 Surface Hub

如果裝置帳戶進入不穩定狀態，或系統管理員帳戶遇到問題，您可以使用設定應用程式啟動雲端復原程式。 只有當裝置重設程式無法修正問題時，[](#reset-a-surface-hub)才應該使用雲端復原程式。

1. 在 Surface Hub 上，選取 **安全性** &gt; **&更新** &gt; ** **。

2. 在 **雲端復原下，** 選取立即 **重新開機**。

   ![從雲端復原](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a>復原鎖定的 Surface Hub

在極少數的情況下，Surface Hub 可能會在工作階段末端清理使用者和應用程式資料時遇到錯誤。 發生這種情況時，裝置會自動重新開機，並再次嘗試執行作業。 但如果此作業重複失敗，裝置會自動鎖定以保護使用者資料。 若要解除鎖定裝置，您必須 [重](#reset-a-surface-hub) 設裝置，如果還是無法解除鎖定，請從雲端復原。

1. 找出 Surface Hub 底部的電源開關。 電源開關位於電源線連接旁邊。 有關電源開關的資訊，請參閱 SURFACE Hub 網站備 ([指南) 。](surface-hub-site-readiness-guide.md)

2. 當 Surface Hub 顯示歡迎畫面時，請使用電源開關關閉 Surface Hub。

3. 使用電源開關重新開啟 Surface Hub。 裝置會啟動並顯示 Surface Hub 標誌畫面。 當您在 Surface Hub 標誌下看到旋轉點時，請使用電源開關再次關閉 Surface Hub。  

4. 重複步驟 3 三次，或直到 Surface Hub 顯示「準備自動修復」訊息。 顯示這則訊息之後，Surface Hub 會顯示 Windows RE 畫面。

 
5. 選取**重設以重新安裝 Windows。** 
![重設以重新安裝](images/recover-from-cloud.png)

8. 選取 **雲端下載。** 

   ![雲端下載](images/recover-cloud-download.png)

>[!IMPORTANT]
>如果您收到錯誤訊息指出無法下載 **，** 請選取 **取消** ，然後再試一次。

9. 選取**完全清除硬碟。**  
![復原並完全清除硬碟](images/recover-fully-clean-drive.png)

10. 系統將會詢問您是否**準備好重設此裝置？** 選取 [重設]****。 
![復原並確認重設](images/recover-confirm-reset.png)

11. 下載會開始，且復原程式會 **指出要重設此裝置**。 
![顯示進行中的復原](images/recover-in-progress.png)

## <a name="contact-support"></a>連絡客戶支援

如果您有任何問題或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。


## <a name="related-topics"></a>相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)
