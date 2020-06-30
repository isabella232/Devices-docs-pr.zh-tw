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
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832066"
---
# 密碼管理 (Surface Hub)

每個 Microsoft Surface Hub 裝置帳戶都需要密碼來驗證和啟用裝置上的功能。 基於安全性考量，您可能想要定期變更 (或「循環使用」) 此密碼。 不過，如果裝置帳戶的密碼變更，之前儲存在 Surface Hub 上的密碼將會無效，而取決於該裝置帳戶的所有功能都將停用。 您將需要在 Surface Hub 上，從 \[設定\] 應用程式更新裝置帳戶的密碼，以重新啟用這些功能。

有兩個選項可簡化您 Surface Hub 裝置帳戶的密碼管理：

1.  關閉裝置帳戶的密碼到期功能。
2.  允許 Surface Hub 自動循環使用裝置帳戶的密碼。


## 關閉裝置帳戶的密碼循環使用

將裝置帳戶的 **PasswordNeverExpires** 屬性設為 True。 您應該確認這是否符合組織的安全性需求。


## 允許 Surface Hub 自動循環使用裝置帳戶的密碼

Surface Hub 可以藉由經常變更密碼來管理裝置帳戶的密碼，而不需要您手動更新裝置帳戶的資訊。 您可以在 **[設定]** 中啟用此功能。 一旦啟用之後，將會每週在維護時間變更裝置帳戶的密碼。

請注意 變更裝置帳戶的密碼時，您將不會看見新的密碼。 如果您需要登入帳戶或再次提供密碼 (例如，如果您想要在 Surface Hub 上變更裝置帳戶設定)，則您需要使用 Active Directory 或 Office 365 管理入口網站來重設密碼。

> [!IMPORTANT]
> 如果您的組織使用混合式拓樸 (部分服務是以內部部署方式裝載，部分服務是透過 Office 365 線上裝載)，您必須以 **domain\username** 格式設定裝置帳戶。 否則，密碼循環使用將無法運作。
