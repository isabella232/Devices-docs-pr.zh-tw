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
# <a name="modern-authentication-on-surface-hub"></a><span data-ttu-id="dcfd5-104">Surface Hub 上的新式驗證</span><span class="sxs-lookup"><span data-stu-id="dcfd5-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="dcfd5-105">在某些情況下，Windows 10 小組 2020 Update 會新增中樞裝置帳戶新式驗證的支援。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-105">The Windows 10 Team 2020 Update adds support for modern authentication of the Hub device account in some scenarios.</span></span> <span data-ttu-id="dcfd5-106">安裝 2020 更新後，如果裝置帳戶透過 Azure Active Directory 進行驗證，且帳戶的信箱是託管在 Exchange Online 中，您可以從舊版基本驗證進行遷移，以使用最新的安全性改良功能。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-106">Once you install the 2020 update, you can migrate from legacy basic authentication to make use of the latest security improvements if the device account authenticates via Azure Active Directory and the account's mailbox is hosted in Exchange Online.</span></span> <span data-ttu-id="dcfd5-107">Surface Hub 使用 2020 Update 支援 Exchange Web Services (EWS) 通訊協定和 Active Directory 驗證庫 (ADAL) 型驗證，將裝置帳戶與 Exchange Online 同步處理。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication when syncing the device account with Exchange Online.</span></span>

<span data-ttu-id="dcfd5-108">對於新的雲端帳戶，Surface Hub 會自動使用新式驗證連線到 Exchange Online，而不需要額外的組組，而不需要使用 alias@contoso.com [格式將](mailto:alias@contoso.com)裝置帳戶新加到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-108">For new cloud-based accounts, the Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply adding the device account to the Surface Hub using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="dcfd5-109">請勿使用舊版格式 ： Contoso\alias，而新式驗證不支援此格式。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="dcfd5-110">詳細資訊，請參閱 [建立和測試裝置帳戶](create-and-test-a-device-account-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-110">For more information, see [create and test a device account](create-and-test-a-device-account-surface-hub.md).</span></span>

> [!NOTE]
> <span data-ttu-id="dcfd5-111">內部部署 Surface Hub 帳戶不支援新式驗證。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-111">Modern authentication is not supported for on-premises Surface Hub accounts.</span></span> <span data-ttu-id="dcfd5-112">帳戶只能使用 Azure AD 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="dcfd5-112">The accounts must use only Azure AD for authentication.</span></span>
