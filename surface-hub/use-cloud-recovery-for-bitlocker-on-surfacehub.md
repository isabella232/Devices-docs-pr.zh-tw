---
title: 如何在 Surface Hub 上使用適用於 BitLocker 的雲端復原
description: 如何在 Surface Hub 上使用適用於 BitLocker 的雲端復原
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: 協助工具設定, \[設定\] 應用程式, 輕鬆存取
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831342"
---
# 摘要

本文說明如何使用雲端復原函數（如果您在 Surface Hub 裝置上不會受到 BitLocker 的意外提示）。

> [!NOTE]
> 只有在 BitLocker 復原金鑰無法使用時，才能按照這些步驟進行。

> [!WARNING]
> * 此恢復程式會刪除內部磁片磁碟機的內容。 如果處理常式失敗，內部磁片磁碟機就會無法使用。 如果發生這種情況，您必須向 Microsoft 記錄服務要求，以解決問題。
> * 完成恢復程式後，裝置將會重設成出廠設定，並傳回它的 [不在畫面] 體驗狀態。
> * 在恢復之後，Surface Hub 必須完全重新配置。

> [!IMPORTANT]
> 這個程式需要開啟無法使用 proxy 或其他驗證方法的網際網路連線。

## 雲端恢復程式

若要執行雲端恢復，請遵循下列步驟：

1. 選取 [**按 Esc] 以取得更多復原選項**。

   ![[取消轉義] 的螢幕擷取畫面](images/01-escape.png)

1. 選取 [**略過這個磁片磁碟機**]。

   ![略過此磁片磁碟機的螢幕擷取畫面](images/02-skip-this-drive.png)

1. 選取 **[從雲端復原**]。

   ![從雲端復原的螢幕擷取畫面](images/03-recover-from-cloud.png)

1. 選取 **[是]**。

   ![[是] 的螢幕擷取畫面](images/04-yes.png)

1. 選取 [**重新安裝**]。

   ![重新安裝的螢幕擷取畫面](images/05a-reinstall.png)

   ![下載的螢幕擷取畫面](images/05b-downloading.png)

1. 雲端復原程式完成後，請使用**全新的體驗**來開始重新配置。

   ![[外框] 畫面的螢幕擷取畫面](images/06-out-of-box.png)

## 「發生錯誤」錯誤訊息

此錯誤通常是由在恢復下載期間發生的網路問題所造成。 發生這個問題時，請不要關閉中樞，因為您無法重新開機。 如果您收到此錯誤訊息，請返回「從雲端復原」步驟，然後重新啟動修復程式。

1. 選取 [**取消**]。

   ![[取消] 的螢幕擷取畫面](images/07-cancel.png)

1. 選取 [**疑難排解**]。

   ![疑難排解的螢幕擷取畫面](images/08-troubleshoot.png)

1. 選取 **[從雲端復原**]。

   ![從雲端復原的螢幕擷取畫面](images/09-recover-from-cloud2.png)

1. 如果出現 [**找不到有線網路**] 錯誤，請選取 [**取消**]，然後讓 Surface Hub 重新探查有線網路。

   ![找不到有線網路的螢幕擷取畫面](images/10-cancel.png)