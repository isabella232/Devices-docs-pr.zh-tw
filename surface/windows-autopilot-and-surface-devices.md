---
title: Windows Autopilot 與 Surface 裝置
ms.reviewer: ''
manager: laurawi
description: 瞭解適用于 Surface 裝置的 Windows Autopilot 部署選項。
keywords: autopilot、windows 10、surface、部署
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831279"
---
# <span data-ttu-id="850f6-104">Windows Autopilot 與 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="850f6-104">Windows Autopilot and Surface devices</span></span>

<span data-ttu-id="850f6-105">Windows Autopilot 是 Windows 10 中的雲端部署技術。</span><span class="sxs-lookup"><span data-stu-id="850f6-105">Windows Autopilot is a cloud-based deployment technology in Windows 10.</span></span> <span data-ttu-id="850f6-106">您可以使用 Windows Autopilot 從盒中的零觸程式直接部署和設定裝置。</span><span class="sxs-lookup"><span data-stu-id="850f6-106">You can use Windows Autopilot to remotely deploy and configure devices in a zero-touch process right out of the box.</span></span>

<span data-ttu-id="850f6-107">Windows Autopilot 已註冊的裝置會在第一次啟動時透過一個名為「*硬體雜湊*」的唯一裝置簽名來識別網際網路。</span><span class="sxs-lookup"><span data-stu-id="850f6-107">Windows Autopilot-registered devices are identified over the Internet at first startup through a unique device signature that's called a *hardware hash*.</span></span> <span data-ttu-id="850f6-108">它們是使用新式管理解決方案（例如 Azure Active Directory （Azure AD）與行動裝置管理）自動進行註冊和設定。</span><span class="sxs-lookup"><span data-stu-id="850f6-108">They're automatically enrolled and configured by using modern management solutions such as Azure Active Directory (Azure AD) and mobile device management.</span></span>

<span data-ttu-id="850f6-109">您可以從已啟用 Windows Autopilot 的 Surface 合作夥伴處，在購買時登記 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="850f6-109">You can register Surface devices at the time of purchase from a Surface partner that's enabled for Windows Autopilot.</span></span> <span data-ttu-id="850f6-110">這些合作夥伴可以直接將新裝置傳送給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="850f6-110">These partners can ship new devices directly to your users.</span></span> <span data-ttu-id="850f6-111">裝置第一次開啟時，系統會自動進行註冊和設定。</span><span class="sxs-lookup"><span data-stu-id="850f6-111">The devices will be automatically enrolled and configured when they are first turned on.</span></span> <span data-ttu-id="850f6-112">這個程式會在部署期間消除映射，這可讓您實現裝置管理和發佈的新敏捷方法。</span><span class="sxs-lookup"><span data-stu-id="850f6-112">This process eliminates reimaging during deployment, which lets you implement new, agile methods of device management and distribution.</span></span>

## <span data-ttu-id="850f6-113">現代化管理</span><span class="sxs-lookup"><span data-stu-id="850f6-113">Modern management</span></span>

<span data-ttu-id="850f6-114">Autopilot 是適用于 Surface 裝置的建議部署選項，包括 Surface Pro 7、Surface 膝上型3和 Surface Pro X （專為透過 Autopilot 進行部署而設計）。</span><span class="sxs-lookup"><span data-stu-id="850f6-114">Autopilot is the recommended deployment option for Surface devices, including Surface Pro 7, Surface Laptop 3, and Surface Pro X, which is specifically designed for deployment through Autopilot.</span></span>

 <span data-ttu-id="850f6-115">最佳做法是使用 Microsoft 雲端解決方案提供者的說明來註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="850f6-115">It's best to enroll your Surface devices with the help of a Microsoft Cloud Solution Provider.</span></span> <span data-ttu-id="850f6-116">此步驟可讓您直接從 Intune 管理 Surface 中的 UEFI 固件設定。</span><span class="sxs-lookup"><span data-stu-id="850f6-116">This step allows you to manage UEFI firmware settings on Surface directly from Intune.</span></span> <span data-ttu-id="850f6-117">它不需要實際觸控裝置就能管理證書。</span><span class="sxs-lookup"><span data-stu-id="850f6-117">It eliminates the need to physically touch devices for certificate management.</span></span> <span data-ttu-id="850f6-118">如需詳細資訊，請參閱[Intune 的 SURFACE UEFI 設定](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="850f6-118">See [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md) for details.</span></span>

## <span data-ttu-id="850f6-119">Windows 版本注意事項</span><span class="sxs-lookup"><span data-stu-id="850f6-119">Windows version considerations</span></span>

<span data-ttu-id="850f6-120">透過 Windows Autopilot 廣泛部署 Surface 裝置，包括購買時由 Surface 合作夥伴進行登記，需要 Windows 10 版本1709（秋季創意者更新）或更新版本。</span><span class="sxs-lookup"><span data-stu-id="850f6-120">Broad deployment of Surface devices through Windows Autopilot, including enrollment by Surface partners at the time of purchase, requires Windows 10 Version 1709 (Fall Creators Update) or later.</span></span>

<span data-ttu-id="850f6-121">這些 Windows 版本支援4000位元組（4k）的雜湊值，可唯一識別 Windows Autopilot 的裝置，而這是在規模部署時所需的。</span><span class="sxs-lookup"><span data-stu-id="850f6-121">These Windows versions support a 4,000-byte (4k) hash value that uniquely identifies devices for Windows Autopilot, which is necessary for deployments at scale.</span></span> <span data-ttu-id="850f6-122">所有新的 Surface 裝置，包括 Surface Pro 7、Surface Pro X 及 Surface 膝上型電腦3，隨附于 Windows 10 版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="850f6-122">All new Surface devices, including Surface Pro 7, Surface Pro X, and Surface Laptop 3, ship with Windows 10 Version 1903 or later.</span></span>

## <span data-ttu-id="850f6-123">需要修復或更換的 Surface 裝置上的 Exchange 體驗</span><span class="sxs-lookup"><span data-stu-id="850f6-123">Exchange experience on Surface devices in need of repair or replacement</span></span>

<span data-ttu-id="850f6-124">Microsoft 會自動檢查 Autopilot 註冊的每個 Surface，並將裝置從客戶的租使用者取消註冊。</span><span class="sxs-lookup"><span data-stu-id="850f6-124">Microsoft automatically checks every Surface for Autopilot enrollment and will deregister the device from the customer's tenant.</span></span>  <span data-ttu-id="850f6-125">只要將更換傳回給客戶，Microsoft 就能確保將更換裝置登記至 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="850f6-125">Microsoft ensures the replacement device is enrolled into Windows Autopilot once a replacement is shipped back to the customer.</span></span> <span data-ttu-id="850f6-126">此服務可在所有裝置 exchange 服務訂單上直接使用 Microsoft 取得。</span><span class="sxs-lookup"><span data-stu-id="850f6-126">This service is available on all device exchange service orders directly with Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="850f6-127">當客戶使用合作夥伴傳回裝置時，合作夥伴負責管理 exchange 程式，包括將裝置登出並註冊至 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="850f6-127">When customers use a Partner to return devices, the Partner is responsible for managing the exchange process including deregistering and enrolling devices into Windows Autopilot.</span></span>

## <span data-ttu-id="850f6-128">已啟用 Windows Autopilot 的 Surface 合作夥伴</span><span class="sxs-lookup"><span data-stu-id="850f6-128">Surface partners enabled for Windows Autopilot</span></span>

<span data-ttu-id="850f6-129">選取 [Surface partner （Surface）合作夥伴] 可在購買時為您在 Windows Autopilot 中註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="850f6-129">Select Surface partners can enroll Surface devices in Windows Autopilot for you at the time of purchase.</span></span> <span data-ttu-id="850f6-130">他們也可以直接將已註冊的裝置傳送給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="850f6-130">They can also ship enrolled devices directly to your users.</span></span> <span data-ttu-id="850f6-131">您可以使用 Windows Autopilot、Azure AD 及行動裝置管理，完全透過零觸控程式來設定裝置。</span><span class="sxs-lookup"><span data-stu-id="850f6-131">The devices can be configured entirely through a zero-touch process by using Windows Autopilot, Azure AD, and mobile device management.</span></span>

<span data-ttu-id="850f6-132">已啟用 Windows Autopilot 的 Surface 合作夥伴包括：</span><span class="sxs-lookup"><span data-stu-id="850f6-132">Surface partners that are enabled for Windows Autopilot include:</span></span>

| <span data-ttu-id="850f6-133">美國合作夥伴</span><span class="sxs-lookup"><span data-stu-id="850f6-133">US partners</span></span> | <span data-ttu-id="850f6-134">全球合作夥伴</span><span class="sxs-lookup"><span data-stu-id="850f6-134">Global partners</span></span> | <span data-ttu-id="850f6-135">美國分銷商</span><span class="sxs-lookup"><span data-stu-id="850f6-135">US distributors</span></span> |
|--------------|---------------|-------------------|
| <span data-ttu-id="850f6-136">\* [CDW](https://www.cdw.com/)</span><span class="sxs-lookup"><span data-stu-id="850f6-136">\* [CDW](https://www.cdw.com/)</span></span> | <span data-ttu-id="850f6-137">\* [也](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="850f6-137">\* [ALSO](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span></span> | <span data-ttu-id="850f6-138">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span><span class="sxs-lookup"><span data-stu-id="850f6-138">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span></span>  |
| <span data-ttu-id="850f6-139">\* [連結](https://www.connection.com/brand/microsoft/microsoft-surface)</span><span class="sxs-lookup"><span data-stu-id="850f6-139">\* [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)</span></span>   | <span data-ttu-id="850f6-140">\* [ATEA](https://www.atea.com/)</span><span class="sxs-lookup"><span data-stu-id="850f6-140">\* [ATEA](https://www.atea.com/)</span></span> | <span data-ttu-id="850f6-141">\* [Techdata](https://www.techdata.com/)</span><span class="sxs-lookup"><span data-stu-id="850f6-141">\* [Techdata](https://www.techdata.com/)</span></span>  |
| <span data-ttu-id="850f6-142">\* [見解](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span><span class="sxs-lookup"><span data-stu-id="850f6-142">\* [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span></span>  | <span data-ttu-id="850f6-143">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="850f6-143">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span></span> | <span data-ttu-id="850f6-144">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span><span class="sxs-lookup"><span data-stu-id="850f6-144">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span></span>   |
| <span data-ttu-id="850f6-145">\* [SHI](https://www.shi.com/Surface)</span><span class="sxs-lookup"><span data-stu-id="850f6-145">\* [SHI](https://www.shi.com/Surface)</span></span> | <span data-ttu-id="850f6-146">\* [Cancom](https://www.cancom.de/)</span><span class="sxs-lookup"><span data-stu-id="850f6-146">\* [Cancom](https://www.cancom.de/)</span></span> |    |
| <span data-ttu-id="850f6-147">\* [LDI 連接](https://www.myldi.com/managed-it/)</span><span class="sxs-lookup"><span data-stu-id="850f6-147">\* [LDI Connect](https://www.myldi.com/managed-it/)</span></span>  | <span data-ttu-id="850f6-148">\* [Computacenter](https://www.computacenter.com/uk)</span><span class="sxs-lookup"><span data-stu-id="850f6-148">\* [Computacenter](https://www.computacenter.com/uk)</span></span> |    |
| <span data-ttu-id="850f6-149">\* [複合鍵](https://www.functiononeit.com/#empower)</span><span class="sxs-lookup"><span data-stu-id="850f6-149">\* [F1](https://www.functiononeit.com/#empower)</span></span>  |   |  |
| <span data-ttu-id="850f6-150">\* [受保護的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span><span class="sxs-lookup"><span data-stu-id="850f6-150">\* [Protected Trust](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span></span> | | | 

## <span data-ttu-id="850f6-151">深入了解</span><span class="sxs-lookup"><span data-stu-id="850f6-151">Learn more</span></span>

<span data-ttu-id="850f6-152">如需有關 Windows Autopilot 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="850f6-152">For more information about Windows Autopilot, see:</span></span>
- [<span data-ttu-id="850f6-153">Windows Autopilot 概觀</span><span class="sxs-lookup"><span data-stu-id="850f6-153">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [<span data-ttu-id="850f6-154">Windows Autopilot 需求</span><span class="sxs-lookup"><span data-stu-id="850f6-154">Windows Autopilot requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)