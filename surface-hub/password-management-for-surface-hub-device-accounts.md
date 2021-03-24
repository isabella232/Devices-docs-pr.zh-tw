---
title: 密碼管理 (Surface Hub)
description: 每個 Microsoft Surface Hub 裝置帳戶都需要密碼來驗證和啟用裝置上的功能。
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: 密碼, 密碼管理, 密碼循環使用, 裝置帳戶
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 215736527121306c712932f57a5a3a853fb3bb20
ms.sourcegitcommit: 366eedceb9f859f5e87ba032b161f248360cb895
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445579"
---
# <a name="password-management-surface-hub"></a>密碼管理 (Surface Hub)

每個 Microsoft Surface Hub 裝置帳戶都需要密碼來驗證和啟用裝置上的功能。 基於安全性考量，您可能想要定期變更 (或「循環使用」) 此密碼。 不過，如果裝置帳戶的密碼變更，之前儲存在 Surface Hub 上的密碼將會無效，而取決於該裝置帳戶的所有功能都將停用。 您將需要在 Surface Hub 上，從 \[設定\] 應用程式更新裝置帳戶的密碼，以重新啟用這些功能。

有兩個選項可簡化您 Surface Hub 裝置帳戶的密碼管理：

1.  關閉裝置帳戶的密碼到期功能。
2.  允許 Surface Hub 自動循環使用裝置帳戶的密碼。


## <a name="turn-off-password-rotation-for-the-device-account"></a>關閉裝置帳戶的密碼循環使用

將裝置帳戶的 **PasswordNeverExpires** 屬性設為 True。 您應該確認這是否符合組織的安全性需求。


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>允許 Surface Hub 自動循環使用裝置帳戶的密碼

Surface Hub 可以自動變更裝置帳戶的密碼，而不需要您手動更新密碼。 您可以在設定 Surface Hub**** 帳戶中  >  ****  >  **啟用此功能**。 如果您開啟密碼旋轉，Surface Hub 會嘗試在維護期間每 7 天變更密碼。 密碼在會議期間不會變更。 如果自上次密碼旋轉以來已過了 7 天，但 Surface Hub 已關閉，它會嘗試在開啟時立即變更密碼，或每隔 10 分鐘變更密碼，直到成功。

自動產生的密碼包含 15-32 個字元，包括大寫和小寫字母、數位和特殊字元的組合。 請注意，當裝置帳戶的密碼變更時，系統不會顯示新的密碼。 如果您需要登錄帳戶，或再次提供密碼 (例如，如果您想要變更 Surface Hub) 上的裝置帳戶設定，則需要使用 Active Directory 或 Microsoft 365 系統管理入口網站重設密碼。

> [!IMPORTANT]
> 將裝置帳戶新增到 Surface Hub 時所使用的格式會影響必須使用哪個裝置[](prepare-your-environment-for-surface-hub.md)關聯選項，才能讓密碼旋轉工作。 如果以網域 **\使用者名稱格式** 新增帳戶，在初始設定期間將 Hub 與內部部署 Active Directory 關聯。 如果以格式新增帳戶，在初始設定期間，將 `username@domain.com` Hub 與 Azure Active Directory 關聯。 否則，密碼循環使用將無法運作。
