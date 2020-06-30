---
title: Surface Hub 可能會安裝更新，並在維護時間外重新開機
description: 關於「自動更新」的 Surface Hub 疑難排解資訊
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub，維護視窗，更新
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831929"
---
# <span data-ttu-id="f937d-104">Surface Hub 可能會安裝更新，並在維護時間外重新開機</span><span class="sxs-lookup"><span data-stu-id="f937d-104">Surface Hub may install updates and restart outside maintenance hours</span></span>

<span data-ttu-id="f937d-105">在特定情況下，Surface Hub 會在上班時間期間安裝更新，而不是在一般維護視窗期間進行。</span><span class="sxs-lookup"><span data-stu-id="f937d-105">Under specific circumstances, Surface Hub installs updates during business hours instead of during the regular maintenance window.</span></span> <span data-ttu-id="f937d-106">裝置然後視需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="f937d-106">The device then restarts if it is necessary.</span></span> <span data-ttu-id="f937d-107">在處理常式完成之前，您無法使用裝置。</span><span class="sxs-lookup"><span data-stu-id="f937d-107">You cannot use the device until the process is completed.</span></span>

> [!NOTE]  
> <span data-ttu-id="f937d-108">這並不是遺失維護視窗的預期行為。</span><span class="sxs-lookup"><span data-stu-id="f937d-108">This isn't expected behavior for missing a maintenance window.</span></span> <span data-ttu-id="f937d-109">只有在裝置已過期時，才會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="f937d-109">It occurs only if the device is out-of-date for a long time.</span></span>

## <span data-ttu-id="f937d-110">原因</span><span class="sxs-lookup"><span data-stu-id="f937d-110">Cause</span></span>
<span data-ttu-id="f937d-111">為了確保 Surface Hub 在上班時間期間仍可供使用，中心設定為在 [設定] 中定義的維護視窗期間執行系統管理功能（請參閱下方的「參考」）。</span><span class="sxs-lookup"><span data-stu-id="f937d-111">To ensure that Surface Hub remains available for use during business hours, the Hub is configured to perform administrative functions during a maintenance window that is defined in Settings (see "References," below).</span></span> <span data-ttu-id="f937d-112">在此維護期間，Hub 會透過 Windows Update 或 Windows Server Update Services （WSUS）自動安裝任何可用的更新。</span><span class="sxs-lookup"><span data-stu-id="f937d-112">During this maintenance period, the Hub automatically installs any available updates through Windows Update or Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="f937d-113">更新完成後，中樞可能會重新開機。</span><span class="sxs-lookup"><span data-stu-id="f937d-113">Once updates are complete, the Hub may restart.</span></span>

<span data-ttu-id="f937d-114">您可以在 [維護] 視窗期間安裝更新，只要 Surface Hub 開啟但未使用或未保留。</span><span class="sxs-lookup"><span data-stu-id="f937d-114">Updates can be installed during the maintenance window only if the Surface Hub is turned on but not in use or reserved.</span></span> <span data-ttu-id="f937d-115">例如，如果 Surface Hub 排程的是持續24小時的會議，任何排程要安裝的更新將會延遲，直到在下一個維護時段內提供該中樞。</span><span class="sxs-lookup"><span data-stu-id="f937d-115">For example, if the Surface Hub is scheduled for a meeting that lasts 24 hours, any updates that are scheduled to be installed will be deferred until the Hub is available during the next maintenance window.</span></span> <span data-ttu-id="f937d-116">如果中樞繼續繁忙且未命中多個維護視窗，則中心將會最終開始安裝並下載更新。</span><span class="sxs-lookup"><span data-stu-id="f937d-116">If the Hub continues to be busy and misses multiple maintenance windows, the Hub will eventually begin to install and download updates.</span></span> <span data-ttu-id="f937d-117">這可能會在維護視窗期間或外發生。</span><span class="sxs-lookup"><span data-stu-id="f937d-117">This can occur during or outside the maintenance window.</span></span> <span data-ttu-id="f937d-118">下載和安裝開始之後，裝置可能會重新開機。</span><span class="sxs-lookup"><span data-stu-id="f937d-118">Once the download and installation has begun, the device may restart.</span></span>

## <span data-ttu-id="f937d-119">若要避免此問題</span><span class="sxs-lookup"><span data-stu-id="f937d-119">To avoid this issue</span></span>

<span data-ttu-id="f937d-120">請務必為 Surface Hub 留出維護時間，以執行管理功能。</span><span class="sxs-lookup"><span data-stu-id="f937d-120">It's important that you set aside maintenance time for Surface Hub to perform administrative functions.</span></span> <span data-ttu-id="f937d-121">保留24小時間隔的 Surface Hub，或在維護視窗期間使用裝置會延遲安裝更新。</span><span class="sxs-lookup"><span data-stu-id="f937d-121">Reserving the Surface Hub for 24 hour intervals or using the device during the maintenance window delays installing updates.</span></span> <span data-ttu-id="f937d-122">我們建議您在排程的維護期間不要使用或保留中樞。</span><span class="sxs-lookup"><span data-stu-id="f937d-122">We recommend that you not use or reserve the Hub during scheduled maintenance period.</span></span> <span data-ttu-id="f937d-123">必須保留兩個小時的視窗，才能進行更新。</span><span class="sxs-lookup"><span data-stu-id="f937d-123">A two-hour window should be reserved for updating.</span></span>

<span data-ttu-id="f937d-124">您可以用來控制更新可用性的一個選項是「Windows Server Update Services （WSUS）」。</span><span class="sxs-lookup"><span data-stu-id="f937d-124">One option that you can use to control the availability of updates is Windows Server Update Service (WSUS).</span></span> <span data-ttu-id="f937d-125">WSUS 提供控制要安裝的更新和時間。</span><span class="sxs-lookup"><span data-stu-id="f937d-125">WSUS provides control over what updates are installed and when.</span></span>

## <span data-ttu-id="f937d-126">參考資料</span><span class="sxs-lookup"><span data-stu-id="f937d-126">References</span></span> 
 
[<span data-ttu-id="f937d-127">更新 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f937d-127">Update the Surface Hub</span></span>](first-run-program-surface-hub.md#update-the-surface-hub) 

[<span data-ttu-id="f937d-128">維護期間</span><span class="sxs-lookup"><span data-stu-id="f937d-128">Maintenance window</span></span>](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[<span data-ttu-id="f937d-129">使用 WindowsServer Update Services (WSUS) 來部署 Windows10 更新</span><span class="sxs-lookup"><span data-stu-id="f937d-129">Deploy Windows 10 updates using Windows Server Update Services (WSUS)</span></span>](/windows/deployment/update/waas-manage-updates-wsus) 


