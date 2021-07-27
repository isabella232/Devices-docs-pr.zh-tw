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
ms.openlocfilehash: ab2726577201157ed9a7ff4d265e826c063cf477
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676607"
---
# <a name="password-management-surface-hub"></a>密碼管理 (Surface Hub)

每個 Microsoft Surface Hub 裝置帳戶都需要密碼來驗證和啟用裝置上的功能。 基於安全性考量，您可能想要定期變更 (或「循環使用」) 此密碼。 不過，如果裝置帳戶的密碼變更，之前儲存在 Surface Hub 上的密碼將會無效，而取決於該裝置帳戶的所有功能都將停用。 您將需要在 Surface Hub 上，從 \[設定\] 應用程式更新裝置帳戶的密碼，以重新啟用這些功能。

有兩個選項可簡化您 Surface Hub 裝置帳戶的密碼管理：

1.  關閉裝置帳戶的密碼到期功能。
2.  允許 Surface Hub 自動循環使用裝置帳戶的密碼。


## <a name="turn-off-password-rotation-for-the-device-account"></a>關閉裝置帳戶的密碼循環使用

將裝置帳戶的 **PasswordNeverExpires** 屬性設為 True。 您應該確認這是否符合組織的安全性需求。


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a>允許 Surface Hub 自動循環使用裝置帳戶的密碼

使用者Surface Hub自動變更裝置帳戶的密碼，而不需要您手動更新密碼。 您可以在帳戶的**設定Surface Hub**  >  ****  >  **啟用此功能**。 如果您開啟密碼旋轉，系統Surface Hub維護期間每 7 天嘗試變更密碼一次。 密碼在會議期間不會變更。 如果自上次密碼旋轉以來已過了 7 天，但 Surface Hub 已關閉，它會嘗試在開啟時立即變更密碼，或每隔 10 分鐘變更密碼，直到成功。

自動產生的密碼包含 15-32 個字元，包括大寫和小寫字母、數位和特殊字元的組合。 請注意，當裝置帳戶的密碼變更時，系統不會顯示新的密碼。 如果您需要登錄帳戶，或再次提供密碼 (例如，如果您想要變更 Surface Hub) 上的裝置帳戶設定，則需要使用 Active Directory 或 Microsoft 365 系統管理入口網站重設密碼。

> [!IMPORTANT]
> 在[初始設定](prepare-your-environment-for-surface-hub.md)密碼期間選取的裝置關聯Surface Hub會影響哪些裝置帳戶格式可以與密碼旋轉一起使用。 附屬於內部部署 Active Directory 的中樞只能旋轉以網域 **\使用者** 名稱格式輸入的裝置帳戶密碼。 附屬於 Azure Active Directory 的中樞只能旋轉以格式輸入的裝置帳戶密碼，但只有在帳戶為雲端，或 AAD 網域已針對雲端驗證和密碼回寫進行配置時，才能旋轉 `username@domain.com` 。 [](/azure/active-directory/hybrid/choose-ad-authn#cloud-authentication) [](/azure/active-directory/authentication/concept-sspr-writeback)
