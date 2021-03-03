---
title: Surface Hub 上的新式驗證
description: 此頁面說明 Surface Hub 上新式驗證的使用方式，與舊版基本驗證相反。
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
ms.openlocfilehash: 1674b7abd74a666e2ab1040f66d9ea548ab3c201
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385161"
---
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="84f82-104">Surface Hub 上的新式驗證</span><span class="sxs-lookup"><span data-stu-id="84f82-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="84f82-105">在某些情況下，Windows 10 小組 2020 更新會新增中樞裝置帳戶新式驗證的支援。</span><span class="sxs-lookup"><span data-stu-id="84f82-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="84f82-106">安裝 2020 更新之後，如果裝置帳戶透過 Azure Active Directory 進行驗證，且帳戶的信箱是託管在 Exchange Online 中，就可以從舊版基本驗證進行遷移，以使用最新的安全性改良功能。</span><span class="sxs-lookup"><span data-stu-id="84f82-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="84f82-107">Surface Hub 在同步處理裝置帳戶與 Exchange Online 時，支援 Exchange Web Services (EWS) 通訊協定和 Active Directory 驗證庫 (ADAL) 型驗證。</span><span class="sxs-lookup"><span data-stu-id="84f82-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="84f82-108">針對新的雲端式帳戶，Surface Hub 會自動使用新式驗證連線到 Exchange Online，除了使用以下格式建立裝置帳戶之外， [不需要](mailto:alias@contoso.com)alias@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="84f82-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="84f82-109">請勿使用舊版格式 ： Contoso\alias，新式驗證不支援此格式。</span><span class="sxs-lookup"><span data-stu-id="84f82-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="84f82-110">詳細資訊請參閱建立 [Surface Hub 2S 裝置帳戶](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。</span><span class="sxs-lookup"><span data-stu-id="84f82-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="84f82-111">Surface Hub 不支援內部部署帳戶的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="84f82-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="84f82-112">帳戶必須在雲端中建立。</span><span class="sxs-lookup"><span data-stu-id="84f82-112">The accounts must be created in the cloud.</span></span>

