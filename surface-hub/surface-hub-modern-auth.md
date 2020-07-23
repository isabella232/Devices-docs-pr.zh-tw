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
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 387d799e15ae25bb1043e9ee3417aa3c31676825
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893130"
---
# <span data-ttu-id="32b6d-104">Surface Hub 上的新式驗證</span><span class="sxs-lookup"><span data-stu-id="32b6d-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="32b6d-105">在 Windows 10 Team 2020 更新中，對雲端帳戶的新式驗證的支援會完全整合，讓您可以從舊版基本驗證進行遷移，並充分利用 Microsoft Azure 與 Exchange Online 中的最新安全性。</span><span class="sxs-lookup"><span data-stu-id="32b6d-105">Support for modern authentication of cloud-based accounts is fully integrated in Windows 10 Team 2020 Update, allowing you to migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="32b6d-106">有了2020更新，Surface Hub 支援 Exchange Web 服務（EWS）協定和 Active Directory 驗證庫（ADAL）的驗證，讓裝置帳戶同步處理啟用 Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="32b6d-106">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="32b6d-107">針對新的雲端帳戶，Surface Hub 會自動使用新式驗證來連線至 Exchange Online，而不只需要使用 [格式] [alias@contoso.com](mailto:alias@contoso.com)建立裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="32b6d-107">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="32b6d-108">請勿使用舊版驗證所不支援的舊版格式– Contoso\alias。</span><span class="sxs-lookup"><span data-stu-id="32b6d-108">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="32b6d-109">如需詳細資訊，請參閱[建立 Surface Hub 2 版裝置帳戶](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。</span><span class="sxs-lookup"><span data-stu-id="32b6d-109">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="32b6d-110">Surface Hub 不支援內部部署帳戶的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="32b6d-110">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="32b6d-111">帳戶必須在雲端建立。</span><span class="sxs-lookup"><span data-stu-id="32b6d-111">The accounts must be created in the cloud.</span></span>

