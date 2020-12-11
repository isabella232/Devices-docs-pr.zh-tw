---
title: Surface Hub 上的新式驗證
description: 此頁面說明在 Surface Hub 上使用新式驗證與傳統基本驗證的對比。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: dd0b0ad257abbc52c443b075e62db00dcf5713ea
ms.sourcegitcommit: 4b1cfcac090910a3ea634929942063eb51fc54f9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/11/2020
ms.locfileid: "11206277"
---
# Surface Hub 上的新式驗證

在 [Windows 10 Team 2020 更新](surface-hub-2020-update.md)中，對雲端帳戶的新式驗證的支援完全整合。 安裝2020更新之後，您就可以從舊版基本驗證中進行遷移，並使用 Microsoft Azure 與 Exchange Online 中的最新安全性增強功能。 有了2020更新，Surface Hub 支援 Exchange Web 服務 (EWS) 通訊協定和 Active Directory 驗證庫 (ADAL) 以啟用裝置帳戶同步處理的 Exchange Online 的驗證。

針對新的雲端帳戶，Surface Hub 會自動使用新式驗證來連線至 Exchange Online，而不只需要使用 [格式] [alias@contoso.com](mailto:alias@contoso.com)建立裝置帳戶。 請勿使用舊版驗證所不支援的舊版格式– Contoso\alias。 如需詳細資訊，請參閱 [建立 Surface Hub 2 版裝置帳戶](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。

> [!NOTE]
> Surface Hub 不支援內部部署帳戶的新式驗證。 帳戶必須在雲端建立。

