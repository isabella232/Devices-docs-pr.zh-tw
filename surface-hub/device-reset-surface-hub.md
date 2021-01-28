---
title: 重設或復原 Surface Hub
description: 描述 Surface Hub 的重設和復原程式，並提供指示。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重設 Surface Hub，復原
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304816"
---
# 重設或復原 Surface Hub

本文說明如何重設或復原 Microsoft Surface Hub。  

[重設 Surface Hub](#reset-a-surface-hub) 會將其作業系統傳回至上一個累積式 Windows 更新，並移除所有本機使用者檔案和配置資訊。 移除的資訊包括下列各項：

- 裝置帳戶
- 裝置本機系統管理員的帳戶資訊
- 網域加入或 Azure AD 加入資訊
- 行動裝置管理 (MDM) 註冊資訊
- 使用 MDM 或 [設定] 應用程式所設定的配置資訊

[從雲端復原 Surface Hub](#recover-a-surface-hub-from-the-cloud) 也會移除此資訊。 此外，Surface Hub 會下載新的作業系統映射並進行安裝。 您可以指定是否要讓復原處理常式保留其他儲存在 Surface Hub 中的資訊。 如果您需要復原其中兩個選項都無法使用的 Surface Hub， [Surface Hub 恢復工具](surface-hub-recovery-tool.md) 會使用相同的作業系統影像。

## 重設 Surface Hub

您可能需要重設 Surface Hub，原因如下：

- 您要為新的會議空間重新調整裝置的用途，並想要重新設定。
- 您想要變更在本機管理裝置的方式。
- 裝置帳戶或系統管理員帳戶的使用者名稱或密碼遺失。
- 安裝更新之後，裝置的效能就會減少。

在重設程式期間，如果您長時間內看到空白畫面，請稍候，並不採取任何動作。

> [!WARNING]
> 裝置重設程式可能需要長達6小時的時間。 請勿關閉或拔下 Surface Hub，直到程式完成為止。 如果您中斷程式，裝置就無法操作。 裝置需要保修服務才能再次運作。

1. 在 Surface Hub 上，開啟 **\[設定\]**。

   ![顯示 Surface Hub 之 [設定] 應用程式的影像。](images/sh-settings.png)

2. 選取 [ **更新 & 安全性**]。

   ![在 Surface Hub 的 [設定] app 中顯示 [更新 & 安全群組的影像。](images/sh-settings-update-security.png)

3. 選取 [ **恢復**]，然後在 [ **重設裝置**] 底下，選取 [ **開始**使用]。

   > [!IMPORTANT]
   > 在重設裝置之前，請確定您有可用的 BitLocker 金鑰，因為稍後會提示您輸入。 若要深入瞭解，請參閱 [儲存您的 BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。 當中樞重新開機至 [恢復] 分區時，系統會提示您輸入 BitLocker 金鑰。 跳過該提示會導致重設失敗。
   
   ![在 Surface Hub 的 [設定] 應用程式中顯示 [重設裝置] 選項的影像。](images/sh-settings-reset-device.png)

   重設程式完成後，Surface Hub 會再次開始 [執行第一個 run 程式](first-run-program-surface-hub.md) 。 如果重設程式遇到問題，它會將 Surface Hub 滾回到先前現有的作業系統影像，然後顯示 [歡迎] 畫面。

<span id="cloud-recovery" />

## 從雲端復原 Surface Hub

如果由於某種原因，Surface Hub 無法使用，您仍然可以從雲端將它復原，而不需要 Microsoft 支援部門取得協助。 Surface Hub 可以從雲端下載全新的作業系統影像，並使用該影像來重新安裝作業系統。

在下列情況下，您可能必須使用這種類型的復原程式：

- [Surface Hub 或其相關帳戶已進入不穩定狀態](#recover-a-surface-hub-in-a-bad-state)
- [Surface Hub 已鎖定](#recover-a-locked-surface-hub)

>[!IMPORTANT]
>**從雲端程式復原**需要有線連線， (沒有 proxy 或其他驗證提示) 。

### 還原不良狀態中的 Surface Hub

如果裝置帳戶出現無法穩定的狀態，或如果管理員帳戶遇到問題，您可以使用 [設定] app 來啟動雲端復原程式。 當 [裝置重設](#reset-a-surface-hub) 處理常式無法修正問題時，您應該只使用雲端復原程式。

1. 在 Surface Hub 上，選取 [ **設定** &gt; **更新 & 安全性**復原] &gt; ** **。

2. 在 **[從雲端復原**] 底下，選取 [ **立即重新開機**]。

   ![從雲端復原](images/recover-from-the-cloud.png)

### 復原鎖定的 Surface Hub

在極少數的情況下，Surface Hub 可能會在工作階段末端清理使用者和應用程式資料時遇到錯誤。 發生這種情況時，裝置會自動重新開機並再次嘗試該作業。 但如果此操作重複失敗，裝置會自動鎖定以保護使用者資料。 若要解除鎖定，您必須 [重設裝置](#reset-a-surface-hub) ，或者如果沒有作用，請從雲端復原。

1. 在 Surface Hub 底部找出電源開關。 電源開關位於電源線連接的旁邊。 如需有關 power 開關的詳細資訊，請參閱 [Surface Hub 網站準備就緒指南 (PDF) ](surface-hub-site-readiness-guide.md)。

2. 當 Surface Hub 顯示 [歡迎] 畫面時，請使用 power 開關關閉 Surface Hub。

3. 使用 power 開關來再次開啟 Surface Hub。 裝置隨即啟動並顯示 Surface Hub 標誌畫面。 當您在 Surface Hub 標誌底下看到旋轉點時，請使用 power 開關再次關閉 Surface Hub。  

4. 重複步驟 3 3 的時間，或直到 Surface Hub 顯示「正在準備自動修復」訊息。 顯示此訊息之後，Surface Hub 就會顯示 [Windows RE] 畫面。

5. 選取 [ **高級選項**]。

6. 選取 **[從雲端復原**]。  (（您也可以選取 [ **重設**]）。 不過， **從雲端復原** 是建議的方法。 ) 

   ![從雲端復原](images/recover-from-cloud.png)
7. 如果系統提示您輸入 Bitlocker 金鑰，請執行下列其中一項操作：

   - 若要保留 Bitlocker 在 Surface Hub 上保護的資訊，請輸入 Bitlocker 金鑰。
   - 若要捨棄受保護的資訊，請選取 [**略過此磁片磁碟機**]  

8. 出現提示時，請選取 [ **重新安裝**]。

    ![重新安裝](images/reinstall.png)

9. 若要重新分區磁片，請選取 **[是]**。

   ![重新分割](images/repartition.png)

   首先，恢復程式會從雲端下載作業系統影像。  

   ![下載 97&](images/recover-progress.png)

   下載完成後，恢復程式會根據您選取的選項，復原 Surface Hub。
   

## 連絡客戶支援

如果您有任何疑問或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。


## 相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)
