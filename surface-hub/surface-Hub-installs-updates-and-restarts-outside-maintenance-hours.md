---
title: Surface Hub 可能會安裝更新，並在維護時間外重新開機
description: 自動更新Surface Hub疑難排解資訊
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: Surface Hub、維護視窗、更新
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/15/2021
ms.openlocfilehash: 7df7857258c1baeedf4ff239eda17c66c93a531c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577023"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a><span data-ttu-id="6b962-104">Surface Hub 可能會安裝更新，並在維護時間外重新開機</span><span class="sxs-lookup"><span data-stu-id="6b962-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="6b962-105">在某些情況下，Surface Hub安裝更新，而不是在一般維護時段內安裝更新。</span><span class="sxs-lookup"><span data-stu-id="6b962-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="6b962-106">如有需要，裝置隨即重新開機。</span><span class="sxs-lookup"><span data-stu-id="6b962-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="6b962-107">在程式完成之前，您無法使用裝置。</span><span class="sxs-lookup"><span data-stu-id="6b962-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="6b962-108">這是錯過維護視窗時所未預期的行為。</span><span class="sxs-lookup"><span data-stu-id="6b962-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="6b962-109">只有當裝置長時間過期時，才會發生此情況。</span><span class="sxs-lookup"><span data-stu-id="6b962-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <a name="cause"></a><span data-ttu-id="6b962-110">原因</span><span class="sxs-lookup"><span data-stu-id="6b962-110">Cause</span></span>

<span data-ttu-id="6b962-111">為了確保系統Surface Hub使用，中心已配置為在 設定 (中定義的維護時段期間執行系統管理功能，請參閱) 下方的「參考資料」。</span><span class="sxs-lookup"><span data-stu-id="6b962-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="6b962-112">在此維護期間，中心會自動透過 WUfB Windows 更新或商務Windows更新 (任何) 。</span><span class="sxs-lookup"><span data-stu-id="6b962-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Update for Business (WUfB).</span></span> <span data-ttu-id="6b962-113">更新完成後，中樞可能會重新開機。</span><span class="sxs-lookup"><span data-stu-id="6b962-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="6b962-114">更新只能在維護視窗期間安裝，Surface Hub開啟，但並未使用或保留更新。</span><span class="sxs-lookup"><span data-stu-id="6b962-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="6b962-115">例如，如果 Surface Hub排定為持續 24 小時的會議，則排程要安裝的任何更新都會延後，直到下一個維護視窗提供中樞。</span><span class="sxs-lookup"><span data-stu-id="6b962-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="6b962-116">如果 Hub 持續忙碌，並錯過多個維護視窗，則中樞最終會開始安裝並下載更新。</span><span class="sxs-lookup"><span data-stu-id="6b962-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="6b962-117">這可能發生在維護視窗期間或外部。</span><span class="sxs-lookup"><span data-stu-id="6b962-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="6b962-118">下載和安裝開始後，裝置可能會重新開機。</span><span class="sxs-lookup"><span data-stu-id="6b962-118">Once the download and installation has begun, the device may restart.</span></span>

## <a name="to-avoid-this-issue"></a><span data-ttu-id="6b962-119">若要避免此問題</span><span class="sxs-lookup"><span data-stu-id="6b962-119">To avoid this issue</span></span>

<span data-ttu-id="6b962-120">您必須預留維護時間，Surface Hub系統管理功能。</span><span class="sxs-lookup"><span data-stu-id="6b962-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="6b962-121">將裝置Surface Hub 24 小時，或在維護視窗期間使用裝置延遲安裝更新。</span><span class="sxs-lookup"><span data-stu-id="6b962-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="6b962-122">我們建議您在排定的維護期間，不要使用或保留中樞。</span><span class="sxs-lookup"><span data-stu-id="6b962-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="6b962-123">應該保留兩小時的視窗以進行更新。</span><span class="sxs-lookup"><span data-stu-id="6b962-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="6b962-124">您可以使用其中一個選項來控制更新的可用性，Windows商務用更新。</span><span class="sxs-lookup"><span data-stu-id="6b962-124">One option that you can use to control the availability of updates is Windows Update for Business.</span></span>

## <a name="learn-more"></a><span data-ttu-id="6b962-125">深入了解</span><span class="sxs-lookup"><span data-stu-id="6b962-125">Learn more</span></span>
 
- [<span data-ttu-id="6b962-126">更新 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="6b962-126">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 
- [<span data-ttu-id="6b962-127">維護期間</span><span class="sxs-lookup"><span data-stu-id="6b962-127">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 
