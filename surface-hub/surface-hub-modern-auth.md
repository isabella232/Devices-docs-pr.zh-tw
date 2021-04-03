---
title: Surface Hub 上的新式驗證
description: 此頁面說明在 Surface Hub 上使用新式驗證與舊版基本驗證不同。
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
ms.openlocfilehash: 3873d0ac7ffff3fa790f44b474d937772e5a0900
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474760"
---
# <a name="modern-authentication-on-surface-hub"></a>Surface Hub 上的新式驗證

在某些情況下，Windows 10 小組 2020 Update 會新增中樞裝置帳戶新式驗證的支援。 安裝 2020 更新後，如果裝置帳戶透過 Azure Active Directory 進行驗證，且帳戶的信箱是託管在 Exchange Online 中，您可以從舊版基本驗證進行遷移，以使用最新的安全性改良功能。 Surface Hub 使用 2020 Update 支援 Exchange Web Services (EWS) 通訊協定和 Active Directory 驗證庫 (ADAL) 型驗證，將裝置帳戶與 Exchange Online 同步處理。

對於新的雲端帳戶，Surface Hub 會自動使用新式驗證連線到 Exchange Online，而不需要額外的組組，而不需要使用 alias@contoso.com [格式將](mailto:alias@contoso.com)裝置帳戶新加到 Surface Hub。 請勿使用舊版格式 ： Contoso\alias，而新式驗證不支援此格式。 詳細資訊，請參閱 [建立和測試裝置帳戶](create-and-test-a-device-account-surface-hub.md)。

> [!NOTE]
> 內部部署 Surface Hub 帳戶不支援新式驗證。 帳戶只能使用 Azure AD 進行驗證。
