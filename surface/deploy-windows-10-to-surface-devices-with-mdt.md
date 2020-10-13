---
title: 使用 Microsoft 部署工具組 (Surface) 將 Windows 10 部署到 Surface 裝置
description: 逐步瞭解如何使用 Microsoft 部署工具套件將 Windows 10 部署到 Surface 裝置的建議程式。
keywords: windows 10 surface、自動化、自訂、mdt
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
ms.date: 10/12/2020
ms.openlocfilehash: 858b6726f1127e3c439864f8946274ed0ea1edd3
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114561"
---
# <span data-ttu-id="8c41f-104">使用 Microsoft 部署工具組將 Windows 10 部署到 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="8c41f-104">Deploy Windows 10 to Surface devices with Microsoft Deployment Toolkit</span></span>

**<span data-ttu-id="8c41f-105">適用於</span><span class="sxs-lookup"><span data-stu-id="8c41f-105">Applies to</span></span>**

- <span data-ttu-id="8c41f-106">Surface Studio 及更新版本</span><span class="sxs-lookup"><span data-stu-id="8c41f-106">Surface Studio and later</span></span>
- <span data-ttu-id="8c41f-107">Surface Pro 4 及更新版本</span><span class="sxs-lookup"><span data-stu-id="8c41f-107">Surface Pro 4 and later</span></span>
- <span data-ttu-id="8c41f-108">Surface Book 及更新版本</span><span class="sxs-lookup"><span data-stu-id="8c41f-108">Surface Book and later</span></span>
- <span data-ttu-id="8c41f-109">Surface 膝上型電腦及更新版本</span><span class="sxs-lookup"><span data-stu-id="8c41f-109">Surface Laptop and later</span></span>
- <span data-ttu-id="8c41f-110">Surface 膝上型電腦前往</span><span class="sxs-lookup"><span data-stu-id="8c41f-110">Surface Laptop Go</span></span>
- <span data-ttu-id="8c41f-111">Surface Go</span><span class="sxs-lookup"><span data-stu-id="8c41f-111">Surface Go</span></span>
- <span data-ttu-id="8c41f-112">Surface 3</span><span class="sxs-lookup"><span data-stu-id="8c41f-112">Surface 3</span></span>
- <span data-ttu-id="8c41f-113">Windows 10</span><span class="sxs-lookup"><span data-stu-id="8c41f-113">Windows 10</span></span>

> [!NOTE]
> <span data-ttu-id="8c41f-114">Surface Pro X 不支援 MDT。如需詳細資訊，請參閱 [部署、管理及維護 Surface Pro X](surface-pro-arm-app-management.md)。</span><span class="sxs-lookup"><span data-stu-id="8c41f-114">MDT is not supported on Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>

<span data-ttu-id="8c41f-115">如需有關使用 MDT 的最新資訊，請參閱 [使用 Mdt 部署 Windows 10 影像](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)。</span><span class="sxs-lookup"><span data-stu-id="8c41f-115">For the latest information about using MDT, refer to [Deploy a Windows 10 image using MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt).</span></span>

