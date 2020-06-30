---
title: 使用 Microsoft 部署工具套件（Surface）將 Surface 裝置升級到 Windows 10
description: 瞭解如何執行 Windows 10 升級部署到您的 Surface 裝置。
keywords: windows 10 surface、upgrade、自訂、mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 04/24/2020
ms.openlocfilehash: e1a1d34c4d32c5e6f95c985e335e405c0d9e59e4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831508"
---
# <span data-ttu-id="e6287-104">使用 Microsoft 部署工具組將 Surface 裝置升級到 Windows 10</span><span class="sxs-lookup"><span data-stu-id="e6287-104">Upgrade Surface devices to Windows 10 with Microsoft Deployment Toolkit</span></span>

#### <span data-ttu-id="e6287-105">適用於</span><span class="sxs-lookup"><span data-stu-id="e6287-105">Applies to</span></span>
- <span data-ttu-id="e6287-106">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="e6287-106">Surface Pro 6</span></span>
- <span data-ttu-id="e6287-107">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="e6287-107">Surface Laptop 2</span></span>
- <span data-ttu-id="e6287-108">Surface Go</span><span class="sxs-lookup"><span data-stu-id="e6287-108">Surface Go</span></span>
- <span data-ttu-id="e6287-109">使用 LTE 的 Surface</span><span class="sxs-lookup"><span data-stu-id="e6287-109">Surface Go with LTE</span></span>
- <span data-ttu-id="e6287-110">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="e6287-110">Surface Book 2</span></span>
- <span data-ttu-id="e6287-111">配備 LTE Advanced 的 Surface Pro (型號 1807)</span><span class="sxs-lookup"><span data-stu-id="e6287-111">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="e6287-112">Surface Pro (型號 1796)</span><span class="sxs-lookup"><span data-stu-id="e6287-112">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="e6287-113">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="e6287-113">Surface Laptop</span></span>
- <span data-ttu-id="e6287-114">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="e6287-114">Surface Studio</span></span>
- <span data-ttu-id="e6287-115">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="e6287-115">Surface Studio 2</span></span>
- <span data-ttu-id="e6287-116">Surface Book</span><span class="sxs-lookup"><span data-stu-id="e6287-116">Surface Book</span></span>
- <span data-ttu-id="e6287-117">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="e6287-117">Surface Pro 4</span></span>
- <span data-ttu-id="e6287-118">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="e6287-118">Surface 3 LTE</span></span>
- <span data-ttu-id="e6287-119">Surface 3</span><span class="sxs-lookup"><span data-stu-id="e6287-119">Surface 3</span></span>
- <span data-ttu-id="e6287-120">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="e6287-120">Surface Pro 3</span></span>
- <span data-ttu-id="e6287-121">Surface Pro 2</span><span class="sxs-lookup"><span data-stu-id="e6287-121">Surface Pro 2</span></span>
- <span data-ttu-id="e6287-122">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="e6287-122">Surface Pro</span></span>
- <span data-ttu-id="e6287-123">Windows 10</span><span class="sxs-lookup"><span data-stu-id="e6287-123">Windows 10</span></span>

<span data-ttu-id="e6287-124">除了 [重設裝置] 的傳統部署方法之外，想要升級執行 Windows 8.1 或 Windows 10 的 Surface 裝置的系統管理員可以選擇部署升級。</span><span class="sxs-lookup"><span data-stu-id="e6287-124">In addition to the traditional deployment method of reimaging devices, administrators who want to upgrade Surface devices that are running Windows 8.1 or Windows 10 have the option of deploying upgrades.</span></span> <span data-ttu-id="e6287-125">透過執行升級部署，Windows 10 可以套用到裝置，而不需移除使用者、應用程式或設定。</span><span class="sxs-lookup"><span data-stu-id="e6287-125">By performing an upgrade deployment, Windows 10 can be applied to devices without removing users, apps, or configuration.</span></span> <span data-ttu-id="e6287-126">已部署的裝置使用者只要繼續使用與升級之前所使用之相同 app 和設定的裝置即可。</span><span class="sxs-lookup"><span data-stu-id="e6287-126">The users of the deployed devices can simply continue using the devices with the same apps and settings that they used prior to the upgrade.</span></span> 

<span data-ttu-id="e6287-127">如需使用 MDT 升級 surface 裝置的最新資訊，請參閱[使用 Mdt 執行就地升級至 Windows 10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit)。</span><span class="sxs-lookup"><span data-stu-id="e6287-127">For the latest information about upgrading surface devices using MDT, refer to [Perform an in-place upgrade to Windows 10 with MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/upgrade-to-windows-10-with-the-microsoft-deployment-toolkit).</span></span>

