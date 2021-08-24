---
title: 重設或復原Surface Hub
description: 說明重設及復原程式Surface Hub，並提供指示。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重Surface Hub重設，復原
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: ee8ac1129aab34afeb3be783133681fe80434831
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911018"
---
# <a name="reset-or-recover-a-surface-hub"></a>重設或復原Surface Hub

本文將說明如何重設或復原Microsoft Surface Hub。  

[重設Surface Hub](#reset-a-surface-hub)會將其作業系統回到上次累積更新Windows，並移除所有本地使用者檔案和設定資訊。 移除的資訊包括下列專案：

- 裝置帳戶
- 裝置本地系統管理員的帳戶資訊
- 網域加入或 Azure AD-join 資訊
- 行動裝置管理 (MDM) 註冊資訊
- 使用 MDM 或應用程式設定設定資訊

[從雲端復原Surface Hub](#recover-a-surface-hub-from-the-cloud)也會移除這項資訊。 此外，Surface Hub下載新的作業系統映射並安裝。 您可以指定復原程式是否保留儲存在資料Surface Hub。 如果您需要復原上述兩個選項Surface Hub修復工具，Surface Hub會使用相同的作業系統映射。 [](surface-hub-recovery-tool.md)

## <a name="reset-a-surface-hub"></a>重設Surface Hub

您可能因為下列Surface Hub重設您的帳戶：

- 您正將裝置重新調整為新的會議空間，並想要重新配置。
- 您想要變更在本機管理裝置的方式。
- 裝置帳戶或系統管理員帳戶的使用者名稱或密碼已遺失。
- 安裝更新之後，裝置性能會降低。

在重設程式期間，如果您長時間看到空白螢幕，請稍候，不要採取任何動作。

> [!WARNING]
> 裝置重設程式最多可能需要六小時。 在程式完成之前，請勿Surface Hub或拔除電源。 如果您中斷程式，裝置就會無法操作。 裝置需要保固服務，才能再次運作。

1. 在 Surface Hub 上，開啟 **\[設定\]**。

   > [!div class="mx-imgBorder"]
   > ![顯示您設定應用程式Surface Hub。](images/sh-settings.png)

2. 選取 **更新 & 安全性**。

   > [!div class="mx-imgBorder"]
   > ![此影像顯示 & 應用程式中的更新設定安全性Surface Hub。](images/sh-settings-update-security.png)

3. 選取 **修復**，然後在重 **設裝置**下，選取 **開始**。

   > [!IMPORTANT]
   > 在重設裝置之前，請確認您擁有 BitLocker 金鑰，因為稍後會提示您。 若要深入瞭解，請參閱儲存 [BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。 當 Hub 重新開機至修復分區時，它會提示您輸入 BitLocker 鍵。 略過提示會造成重設失敗。
   
   > [!div class="mx-imgBorder"]
   > ![顯示應用程式內重設裝置選項的影像設定應用程式Surface Hub。](images/sh-settings-reset-device.png)

   重設程式完成後，Surface Hub再次[啟動第一個執行程式](first-run-program-surface-hub.md)。 如果重設程式遇到問題，它會將Surface Hub卷回先前現有的作業系統映射，然後顯示歡迎畫面。

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a>從雲端復原 Surface Hub

如果因某種Surface Hub無法使用，您仍可在不需要 Microsoft 支援服務協助的情況下從雲端復原。 使用者可以Surface Hub從雲端下載新的作業系統映射，然後使用該影像重新安裝其作業系統。

在下列情況下，您可能必須使用此類型的復原程式：

- [Surface Hub相關帳戶已進入不穩定狀態](#recover-a-surface-hub-in-a-bad-state)
- [系統Surface Hub鎖定](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>從 **雲端復原程式** 需要有線連接，提供開啟的網際網路 (Proxy 或其他驗證提示) 。

### <a name="recover-a-surface-hub-in-a-bad-state"></a>還原不良狀態中的 Surface Hub

如果裝置帳戶進入不穩定狀態，或系統管理員帳戶遇到問題，您可以使用 設定 應用程式啟動雲端復原程式。 您應該只在裝置重設程式無法修正問題時[](#reset-a-surface-hub)，才使用雲端修復程式。

1. 在您的電腦Surface Hub，選取**設定** &gt; **更新&** &gt; **安全性修復**。

2. 在 **從雲端復原下**，選取 **立即重新開機**。

   > [!div class="mx-imgBorder"]
   > ![從雲端復原。](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a>復原鎖定的 Surface Hub

在極少數的情況下，Surface Hub 可能會在工作階段末端清理使用者和應用程式資料時遇到錯誤。 發生此情況時，裝置會自動重新開機，並再次嘗試執行作業。 但如果此作業重複失敗，裝置會自動鎖定以保護使用者資料。 若要解除鎖定，您必須 [重設](#reset-a-surface-hub) 裝置，或者如果無法解除鎖定，請從雲端復原。

1. 找出電源開關底部的Surface Hub。 電源開關位於電源線連接旁邊。 有關電源開關的資訊，請參閱 PDF Surface Hub[網站 (指南) 。](surface-hub-site-readiness-guide.md)

2. 當Surface Hub顯示歡迎畫面時，請使用電源開關關閉Surface Hub。

3. 使用電源開關將電源Surface Hub重新開啟。 裝置會啟動並顯示標誌Surface Hub畫面。 當您在標誌Surface Hub下看到旋轉點時，請使用電源開關Surface Hub關閉。  

4. 重複步驟 3 三次，或直到Surface Hub顯示「準備自動修復」訊息。 顯示這則訊息之後，Surface Hub會顯示Windows RE畫面。
 
5. 選取 [重設]****。 

6. 如果系統提示您輸入 BitLocker 鍵，請執行下列其中一項操作：
   - 若要將 BitLocker 保護的資訊保留在Surface Hub，請輸入 BitLocker 鍵。
   - 若要捨棄受保護的資訊，請選取跳過此磁碟機

7. 選取 **雲端下載。** 

   ![雲端下載。](images/recover-cloud-download.png)

   >[!IMPORTANT]
   >如果您收到指出無法下載的錯誤訊息，**** 請**選取取消，** 然後再次**重設**。

8. 選取 **完全清理磁碟機。**
 
   ![復原並完全清除磁碟機。](images/recover-fully-clean-drive.png)

9. 系統將會詢問您是否 **準備好重設此裝置？**。 選取 [重設]****。 
   
   ![復原並確認重設。](images/recover-confirm-reset.png)

10. 下載會開始，且修復程式會指出 **重設此裝置**。

    ![復原。](images/recover-in-progress.png)

## <a name="contact-support"></a>連絡客戶支援

如果您有任何問題或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。


## <a name="related-topics"></a>相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)
