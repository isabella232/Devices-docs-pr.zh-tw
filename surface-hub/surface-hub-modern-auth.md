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
ms.date: 09/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 14be433923ca564123952c2d1d7b1c158e725af3
ms.sourcegitcommit: d24759da42dfe0b913fd9ebf716407a673c2b818
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/09/2020
ms.locfileid: "11004465"
---
# <span data-ttu-id="6cca7-104">Surface Hub 上的新式驗證</span><span class="sxs-lookup"><span data-stu-id="6cca7-104">Modern authentication on Surface Hub</span></span>

<span data-ttu-id="6cca7-105">在即將推出的 Windows 10 Team 2020 更新中，支援可從 Windows 測試人員 [計畫](https://insider.windows.com/)取得預覽版的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="6cca7-105">Support for modern authentication of cloud-based accounts is fully integrated in the upcoming Windows 10 Team 2020 Update, with preview builds available from the [Windows Insider Program](https://insider.windows.com/).</span></span> <span data-ttu-id="6cca7-106">[安裝預覽組建](surface-hub-install-2020preview.md)之後，您就可以從舊版基本驗證中進行遷移，並利用 Microsoft Azure 與 Exchange Online 中的最新安全性增強功能。</span><span class="sxs-lookup"><span data-stu-id="6cca7-106">Once you [install the preview build](surface-hub-install-2020preview.md), you can migrate from legacy basic authentication and utilize the latest security improvements from Microsoft Azure and Exchange Online.</span></span> <span data-ttu-id="6cca7-107">有了2020更新，Surface Hub 支援 Exchange Web 服務 (EWS) 通訊協定和 Active Directory 驗證庫 (ADAL) 以啟用裝置帳戶同步處理的 Exchange Online 的驗證。</span><span class="sxs-lookup"><span data-stu-id="6cca7-107">With the 2020 Update, Surface Hub supports Exchange Web Services (EWS) protocols and Active Directory Authentication Library (ADAL) based authentication enabling Exchange Online for Device Account syncing.</span></span>

<span data-ttu-id="6cca7-108">針對新的雲端帳戶，Surface Hub 會自動使用新式驗證來連線至 Exchange Online，而不只需要使用 [格式] [alias@contoso.com](mailto:alias@contoso.com)建立裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="6cca7-108">For new cloud-based accounts, Surface Hub automatically uses Modern Authentication to connect to Exchange Online without requiring additional configuration beyond simply creating device accounts using the format [alias@contoso.com](mailto:alias@contoso.com).</span></span> <span data-ttu-id="6cca7-109">請勿使用舊版驗證所不支援的舊版格式– Contoso\alias。</span><span class="sxs-lookup"><span data-stu-id="6cca7-109">Do not use the legacy format – Contoso\alias, which is not supported for modern authentication.</span></span> <span data-ttu-id="6cca7-110">如需詳細資訊，請參閱 [建立 Surface Hub 2 版裝置帳戶](https://docs.microsoft.com/surface-hub/surface-hub-2s-account)。</span><span class="sxs-lookup"><span data-stu-id="6cca7-110">For more information, see [Create Surface Hub 2S device account](https://docs.microsoft.com/surface-hub/surface-hub-2s-account).</span></span>

> [!NOTE]
> <span data-ttu-id="6cca7-111">Surface Hub 不支援內部部署帳戶的新式驗證。</span><span class="sxs-lookup"><span data-stu-id="6cca7-111">Surface Hub does not support modern authentication for on-premises accounts.</span></span> <span data-ttu-id="6cca7-112">帳戶必須在雲端建立。</span><span class="sxs-lookup"><span data-stu-id="6cca7-112">The accounts must be created in the cloud.</span></span>

