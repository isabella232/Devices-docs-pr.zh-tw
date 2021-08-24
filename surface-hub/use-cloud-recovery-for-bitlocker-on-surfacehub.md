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
ms.openlocfilehash: e220be7d4613fcb6a14180e482dc4f2c66a5ddc8
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911028"
---
# <a name="summary"></a>摘要

本文說明如何在 BitLocker 在裝置上意外提示您Surface Hub功能。

> [!NOTE]
> 只有在 BitLocker 修復金鑰無法接通，才應遵循這些步驟。

> [!WARNING]
> * 此修復程式會刪除內部磁碟機的內容。 如果程式失敗，內部磁碟機將會完全無法使用。 如果發生這種情況，您必須向 Microsoft 記錄服務要求，才能解決問題。
> * 復原程式完成後，裝置會重設至出廠設定，並回到其開箱即用體驗狀態。
> * 復原之後，Surface Hub必須完全重新配置。

> [!IMPORTANT]
> 此程式需要不使用 Proxy 或其他驗證方法的開放式網際網路連接。

## <a name="cloud-recovery-process"></a>雲端復原程式

若要執行雲端復原，請遵循下列步驟：

1. 選取 **按 Esc 以尋找更多修復選項**。

   ![Escape 的螢幕擷取畫面。](images/01-escape.png)

1. 選取 **跳過此磁碟機**。

   ![跳過此磁碟機的螢幕擷取畫面。](images/02-skip-this-drive.png)

1. 選取 **從雲端復原**。

   ![從雲端復原的螢幕擷取畫面。](images/03-recover-from-cloud.png)

1. 選取 **是**。

   ![是的螢幕擷取畫面。](images/04-yes.png)

1. 選取 **重新安裝**。

   ![重新安裝的螢幕擷取畫面。](images/05a-reinstall.png)

   ![下載的螢幕擷取畫面。](images/05b-downloading.png)

1. 完成雲端復原程式之後，使用開箱即用體驗 **開始重新配置**。

   ![開箱即用螢幕擷取畫面。](images/06-out-of-box.png)

## <a name="something-went-wrong-error-message"></a>「發生錯誤」錯誤訊息

此錯誤通常是在修復下載期間發生的網路問題所導致。 發生此問題時，請勿關閉 Hub，因為無法重新開機。 如果您收到此錯誤訊息，請回到「從雲端復原」步驟，然後重新開機復原程式。

1. 選取 **取消**。

   ![取消的螢幕擷取畫面。](images/07-cancel.png)

1. 選取 **疑難排解**。

   ![疑難排解的螢幕擷取畫面。](images/08-troubleshoot.png)

1. 選取 **從雲端復原**。

   ![從雲端復原的螢幕擷取畫面。](images/09-recover-from-cloud2.png)

1. 如果**找不到有線**網路發生錯誤，請選取 取消 **，然後**讓Surface Hub重新探索有線網路。

   ![找不到有線網路的螢幕擷取畫面。](images/10-cancel.png)