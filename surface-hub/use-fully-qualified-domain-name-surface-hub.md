---
title: 搭配 Surface Hub 使用完整網域名稱
description: 對常見問題進行疑難排解，包括設定問題、Exchange ActiveSync 錯誤。
keywords:
- 疑難排解常見問題
- 設定問題
- Exchange ActiveSync 錯誤
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: c9617ec9c77d0f0c0333a156448ca24c18aec1db
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911758"
---
# <a name="configure-domain-name-for-skype-for-business"></a>為商務用 Skype 設定網域名稱

在幾個情況下您需要指定商務用 Skype 伺服器的網域名稱：
- **多重 DNS 尾碼**：您的商務用 Skype 基礎結構的命名空間不接續，造成有一或多個伺服器的 DNS 尾碼與商務用 Skype 登入位址 (SIP) 的 DNS 尾碼不相符。  
- **商務用 Skype 與 Exchange 尾碼不同**：商務用 Skype 的登入位址尾碼，與用於裝置帳戶的 Exchange 位址尾碼不同。
- **使用憑證**- 具有內部部署伺服器的大型商務用 Skype通常使用具有其根憑證授權單位或 CA (憑證) 。 CA 網域通常會和商務用 Skype 伺服器的網域不同，這會造成憑證無法信任，進而使登入失敗。  Skype 必須知道憑證的網域名稱才能設定信任關係。 企業通常會使用群組原則將此資訊推送到電腦版 Skype，但 Surface Hub 上並不支援群組原則。

**若要為您的商務用 Skype 伺服器設定網域名稱**</br>
1. 在 Surface Hub 上，開啟 **[設定]**。
2. 按一下 **[Surface Hub]**，然後按一下 **[通話和音訊]**。 
3. 在 **[商務用 Skype 設定]** 底下，按一下 **[設定網域名稱]**。 
4. 為您的商務用 Skype 伺服器輸入網域名稱，然後按一下 **[確定]**。 
   > [!TIP]
   > 您可以輸入多個網域名稱 (使用逗號分隔)。 <br> 例如：lync.com, outlook.com, lync.glbdns.microsoft.com。

    ![新增商務用 Skype FQDN 到 設定。](images/system-settings-add-fqdn.png)
