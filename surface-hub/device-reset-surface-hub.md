---
title: 重設及復原Surface Hub
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
ms.openlocfilehash: f0292d4c2ec599ba620ab87930fbecf3bab9e078
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449276"
---
# <a name="reset-and-recovery-for-surface-hub"></a>重設及復原Surface Hub

本文將說明如何重設Microsoft Surface Hub。  

[重設Surface Hub](#reset-a-surface-hub)會將其作業系統回到上次累積更新Windows，並移除所有本地使用者檔案和設定資訊。 移除的資訊包括下列專案：

- 裝置帳戶
- 裝置本地系統管理員的帳戶資訊
- 網域加入或Azure AD加入資訊
- 行動裝置管理 (MDM) 註冊資訊
- 使用 MDM 或應用程式設定設定資訊

您可以指定復原程式是否保留儲存在資料Surface Hub。 如果無法使用重設選項，Surface Hub[修復](surface-hub-recovery-tool.md)工具可以直接重新Surface Hub SSD。

## <a name="reset-a-surface-hub"></a>重設Surface Hub

您可能因為下列Surface Hub重設您的帳戶：

- 您正將裝置重新調整為新的會議空間，並想要重新配置。
- 您想要變更在本機管理裝置的方式。

在重設程式期間，如果您長時間看到空白螢幕，請稍候，不要採取任何動作。

> [!WARNING]
> 裝置重設程式最多可能需要六小時。 在程式完成之前，請勿Surface Hub或拔除電源。 如果您中斷程式，裝置就會無法操作。 裝置需要保固服務，才能再次運作。

1. 在 Surface Hub 上，開啟 **\[設定\]**。

   > [!div class="mx-imgBorder"]
   > ![顯示 設定 應用程式Surface Hub。](images/sh-settings.png)

2. 選取 **更新&安全性**。

   > [!div class="mx-imgBorder"]
   > ![此影像顯示 & 應用程式中的更新設定安全性Surface Hub。](images/sh-settings-update-security.png)

3. 選取 **修復**，然後在重 **設裝置**下，選取 **開始**。

   > [!IMPORTANT]
   > 在重設裝置之前，請確認您擁有 BitLocker 金鑰，因為稍後會提示您。 若要深入瞭解，請參閱儲存 [BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。 當 Hub 重新開機至修復分區時，它會提示您輸入 BitLocker 鍵。 略過提示會造成重設失敗。
   
   > [!div class="mx-imgBorder"]
   > ![顯示應用程式內重設裝置選項的影像設定應用程式Surface Hub。](images/sh-settings-reset-device.png)

   重設程式完成後，Surface Hub再次[啟動第一個執行程式](first-run-program-surface-hub.md)。 如果重設程式遇到問題，它會將Surface Hub卷回先前現有的作業系統映射，然後顯示歡迎畫面。

## <a name="recover-a-locked-surface-hub"></a>復原鎖定的 Surface Hub

如果因為某種Surface Hub無法使用，而且您無法從 設定 App 啟動重設，如果您有 BitLocker 修復金鑰Surface Hub您仍然可以重設 Surface Hub。

1. 找出電源開關底部的Surface Hub。 電源開關位於電源線連接旁邊。 有關電源開關的資訊，請參閱 PDF Surface Hub[網站 (指南) ](surface-hub-site-readiness-guide.md)。

2. 當Surface Hub顯示歡迎畫面時，請使用電源開關關閉Surface Hub。

3. 使用電源開關將電源Surface Hub開啟。 裝置會啟動並顯示標誌Surface Hub畫面。 當您在標誌Surface Hub看到旋轉點時，請使用電源開關再次Surface Hub關閉。  

4. 重複步驟 3 兩次，或直到Surface Hub顯示「準備自動修復」訊息。 顯示這則訊息之後，Surface Hub會顯示Windows RE畫面。
 
5. 選取 [重設]****。

6. 選取 **重新安裝本地。**

7. 選取 **完全清理磁碟機。**
 
   ![復原並完全清除磁碟機。](images/recover-fully-clean-drive.png)

8. 系統將會詢問 **您是否準備好重設此裝置？**。 選取 [重設]****。 
   
   ![復原並確認重設。](images/recover-confirm-reset.png)


## <a name="contact-support"></a>連絡客戶支援

如果您有任何問題或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。


## <a name="related-topics"></a>相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)
