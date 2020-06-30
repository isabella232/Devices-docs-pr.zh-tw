---
title: Surface 裝置的長期服務通道（Surface）
description: 一般用途 Surface 裝置不支援 LTSB，因此只適用于專用裝置。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 591ab98e79ea1ea7d373a3cdf8867601c7c0e832
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831550"
---
# <span data-ttu-id="da4a1-103">Surface 裝置的長期服務通道（LTSC）</span><span class="sxs-lookup"><span data-stu-id="da4a1-103">Long-Term Servicing Channel (LTSC) for Surface devices</span></span>

>[!WARNING]
><span data-ttu-id="da4a1-104">如需本主題的更新資訊，請參閱[與 Windows 10 長期服務通道的 Surface 裝置相容性](surface-device-compatibility-with-windows-10-ltsc.md)。</span><span class="sxs-lookup"><span data-stu-id="da4a1-104">For updated information on this topic, see [Surface device compatibility with Windows 10 Long-Term Servicing Channel](surface-device-compatibility-with-windows-10-ltsc.md).</span></span> <span data-ttu-id="da4a1-105">如需此更新的其他資訊，請參閱適用于 IT 專業人員的 Surface 博客上的[surface 和 Windows 10 LTSB 相容性](https://blogs.technet.microsoft.com/surface/2017/04/11/documentation-updates-for-surface-and-windows-10-ltsb-compatibility)文章的相關資訊更新。</span><span class="sxs-lookup"><span data-stu-id="da4a1-105">For additional information on this update, see the [Documentation Updates for Surface and Windows 10 LTSB Compatibility](https://blogs.technet.microsoft.com/surface/2017/04/11/documentation-updates-for-surface-and-windows-10-ltsb-compatibility) post on the Surface Blog for IT Pros.</span></span>

<span data-ttu-id="da4a1-106">不支援長期服務通道（LTSC）中的一般用途 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="da4a1-106">General-purpose Surface devices in the Long-Term Servicing Channel (LTSC) are not supported.</span></span> <span data-ttu-id="da4a1-107">一般來說，如果 Surface 裝置執行生產力軟體（例如 Microsoft Office），它是一般用途的裝置，不符合 LTSC，因此應該在半年通道上。</span><span class="sxs-lookup"><span data-stu-id="da4a1-107">As a general guideline, if a Surface device runs productivity software, such as Microsoft Office, it is a general-purpose device that does not qualify for LTSC and should instead be on the Semi-Annual Channel.</span></span> 

>[!NOTE]
><span data-ttu-id="da4a1-108">如需服務分支的詳細資訊，請參閱[將 Windows 作為服務的概覽](https://technet.microsoft.com/itpro/windows/manage/waas-overview)。</span><span class="sxs-lookup"><span data-stu-id="da4a1-108">For more information about the servicing branches, see [Overview of Windows as a service](https://technet.microsoft.com/itpro/windows/manage/waas-overview).</span></span>

<span data-ttu-id="da4a1-109">LTSC 會防止 Surface 裝置收到重要的 Windows 10 功能更新，以及某些不安全的服務更新。</span><span class="sxs-lookup"><span data-stu-id="da4a1-109">LTSC prevents Surface devices from receiving critical Windows 10 feature updates and certain non-security servicing updates.</span></span> <span data-ttu-id="da4a1-110">在 LTSC 設定中使用 Surface 裝置的客戶不佳，系統會指示您切換到半年頻道。</span><span class="sxs-lookup"><span data-stu-id="da4a1-110">Customers with poor experiences using Surface devices in the LTSC configuration will be instructed to switch to the Semi-Annual Channel.</span></span> <span data-ttu-id="da4a1-111">此外，Windows 10 企業版 LTSB 版本也會移除 Surface 裝置的核心功能，包括無縫筆跡和觸控友好的應用程式。</span><span class="sxs-lookup"><span data-stu-id="da4a1-111">Furthermore, the Windows 10 Enterprise LTSB edition removes core features of Surface devices, including seamless inking and touch-friendly applications.</span></span> <span data-ttu-id="da4a1-112">它不包含主要的內含應用程式，包括 Microsoft Edge、OneNote、行事曆或攝影機。</span><span class="sxs-lookup"><span data-stu-id="da4a1-112">It does not contain key in-box applications including Microsoft Edge, OneNote, Calendar or Camera.</span></span> <span data-ttu-id="da4a1-113">因此，生產力會受到影響，且功能受到限制。</span><span class="sxs-lookup"><span data-stu-id="da4a1-113">Therefore, productivity is impacted and functionality is limited.</span></span> <span data-ttu-id="da4a1-114">LTSC 不支援做為適用于一般用途 Surface 裝置的服務方案。</span><span class="sxs-lookup"><span data-stu-id="da4a1-114">LTSC is not supported as a suitable servicing solution for general-purpose Surface devices.</span></span> 

<span data-ttu-id="da4a1-115">一般用途的 Surface 裝置是要在半年通道上執行，以接收完整的服務和固件更新，並與新的 Surface 功能的引進相容。</span><span class="sxs-lookup"><span data-stu-id="da4a1-115">General-purpose Surface devices are intended to run on the Semi-Annual Channel to receive full servicing and firmware updates and forward compatibility with the introduction of new Surface features.</span></span> <span data-ttu-id="da4a1-116">在半年頻道中，Microsoft 釋放功能後，就可以使用功能更新。</span><span class="sxs-lookup"><span data-stu-id="da4a1-116">In the Semi-Annual Channel, feature updates are available as soon as Microsoft releases them.</span></span>

<span data-ttu-id="da4a1-117">在特殊案例中的 Surface 裝置，例如控制醫療裝置、銷售點系統和 Atm 的電腦-可能會考慮使用 LTSC。</span><span class="sxs-lookup"><span data-stu-id="da4a1-117">Surface devices in specialized scenarios–such as PCs that control medical equipment, point-of-sale systems, and ATMs–might consider the use of LTSC.</span></span> <span data-ttu-id="da4a1-118">這些特殊用途的系統通常會執行單一工作，且不需要功能更新，就像組織中的其他裝置一樣。</span><span class="sxs-lookup"><span data-stu-id="da4a1-118">These special-purpose systems typically perform a single task and do not require feature updates as frequently as other devices in the organization.</span></span> 

## <span data-ttu-id="da4a1-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="da4a1-119">Related topics</span></span>

- [<span data-ttu-id="da4a1-120">Surface IT 專業人員部落格</span><span class="sxs-lookup"><span data-stu-id="da4a1-120">Surface IT Pro Blog</span></span>](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/bg-p/SurfaceITPro)

