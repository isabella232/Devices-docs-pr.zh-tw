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
ms.date: 9/14/2020
ms.openlocfilehash: 31f11db8c3ab12d1af754267022d9060d3a8c026
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271099"
---
# <span data-ttu-id="91983-104">Windows Autopilot 與 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="91983-104">Windows Autopilot and Surface devices</span></span>

<span data-ttu-id="91983-105">Windows Autopilot 是 Windows 10 中的雲端部署技術。</span><span class="sxs-lookup"><span data-stu-id="91983-105">Windows Autopilot is a cloud-based deployment technology in Windows 10.</span></span> <span data-ttu-id="91983-106">您可以使用 Windows Autopilot 從盒中的零觸程式直接部署和設定裝置。</span><span class="sxs-lookup"><span data-stu-id="91983-106">You can use Windows Autopilot to remotely deploy and configure devices in a zero-touch process right out of the box.</span></span>

<span data-ttu-id="91983-107">傳統上，IT 專業人員需要花大量的時間來建立和自訂影像，這些影像會在已安裝好的裝置上部署到已隨附的裝置上。</span><span class="sxs-lookup"><span data-stu-id="91983-107">Traditionally, IT pros spend a lot of time building and customizing images that will later be deployed to devices that already come with a perfectly good OS already installed on them.</span></span> <span data-ttu-id="91983-108">Windows Autopilot 推出了新的零觸控部署方法，可使用安裝及設定 Windows 裝置的技術集合。</span><span class="sxs-lookup"><span data-stu-id="91983-108">Windows Autopilot introduces a new zero-touch deployment approach using a collection of technologies to set up and configure Windows devices.</span></span> <span data-ttu-id="91983-109">這可讓 IT 部門設定/自訂影像，幾乎不需要管理任何基礎結構，也簡單易懂。</span><span class="sxs-lookup"><span data-stu-id="91983-109">This enables an IT department to configure/customize images with little to no infrastructure to manage and a process that is easy and simple.</span></span> <span data-ttu-id="91983-110">從使用者的角度來看，只需要幾個簡單的步驟，就能讓表面達到生產狀態。</span><span class="sxs-lookup"><span data-stu-id="91983-110">From the user’s perspective, it only takes a few simple steps to get Surface to a productive state.</span></span> <span data-ttu-id="91983-111">事實上，最終使用者所需的唯一互動是連線到網路並驗證其認證。</span><span class="sxs-lookup"><span data-stu-id="91983-111">In fact, the only interaction required from the end user is to connect to a network and to verify their credentials.</span></span> <span data-ttu-id="91983-112">此之後的所有專案都會完全自動化。</span><span class="sxs-lookup"><span data-stu-id="91983-112">Everything after that is fully automated.</span></span>

<span data-ttu-id="91983-113">Windows Autopilot 可讓您：</span><span class="sxs-lookup"><span data-stu-id="91983-113">Windows Autopilot allows you to:</span></span>

- <span data-ttu-id="91983-114">自動將裝置加入 Azure Active Directory (Azure AD) 。</span><span class="sxs-lookup"><span data-stu-id="91983-114">Automatically join devices to Azure Active Directory (Azure AD).</span></span>
- <span data-ttu-id="91983-115">自動註冊裝置至 MDM 服務，例如 Microsoft Intune (需要 Azure AD Premium 訂閱) 。</span><span class="sxs-lookup"><span data-stu-id="91983-115">Auto-enroll devices into MDM services, such as Microsoft Intune (requires an Azure AD Premium subscription).</span></span>
- <span data-ttu-id="91983-116">限制建立系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="91983-116">Restrict the Administrator account creation.</span></span> <span data-ttu-id="91983-117">Autopilot 是讓第一個登入 Windows 的人員進入標準使用者的唯一方式。</span><span class="sxs-lookup"><span data-stu-id="91983-117">Autopilot is the only way to have the first person who logs into Windows enter as a standard user.</span></span>
- <span data-ttu-id="91983-118">根據裝置設定檔建立並自動將裝置指派給配置群組。</span><span class="sxs-lookup"><span data-stu-id="91983-118">Create and auto-assign devices to configuration groups based on device profiles.</span></span>
- <span data-ttu-id="91983-119">自訂 OOBE (不在盒外體驗) 內容和品牌，以符合組織的需求。</span><span class="sxs-lookup"><span data-stu-id="91983-119">Customize OOBE (Out of Box Experience) content and branding to meet organizational requirements.</span></span>
- <span data-ttu-id="91983-120">使用 Intune 啟用完整裝置設定。</span><span class="sxs-lookup"><span data-stu-id="91983-120">Enable full device configuration with Intune.</span></span>
- <span data-ttu-id="91983-121">遠端重設或重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="91983-121">Reset or restart devices remotely.</span></span>

## <span data-ttu-id="91983-122">運作方式</span><span class="sxs-lookup"><span data-stu-id="91983-122">How it works</span></span>

<span data-ttu-id="91983-123">Windows Autopilot 已註冊的裝置會在第一次啟動時透過一個名為「 *硬體雜湊*」的唯一裝置簽名來識別網際網路。</span><span class="sxs-lookup"><span data-stu-id="91983-123">Windows Autopilot-registered devices are identified over the Internet at first startup through a unique device signature that's called a *hardware hash*.</span></span> <span data-ttu-id="91983-124">它們是使用新式管理解決方案（例如 Azure Active Directory (Azure AD) 與行動裝置管理）自動進行註冊和設定。</span><span class="sxs-lookup"><span data-stu-id="91983-124">They're automatically enrolled and configured by using modern management solutions such as Azure Active Directory (Azure AD) and mobile device management.</span></span>

<span data-ttu-id="91983-125">您可以從已啟用 Windows Autopilot 的 Surface 合作夥伴處，在購買時登記 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="91983-125">You can register Surface devices at the time of purchase from a Surface partner that's enabled for Windows Autopilot.</span></span> <span data-ttu-id="91983-126">這些合作夥伴可以直接將新裝置傳送給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="91983-126">These partners can ship new devices directly to your users.</span></span> <span data-ttu-id="91983-127">裝置第一次開啟時，系統會自動進行註冊和設定。</span><span class="sxs-lookup"><span data-stu-id="91983-127">The devices will be automatically enrolled and configured when they are first turned on.</span></span> <span data-ttu-id="91983-128">這個程式會在部署期間消除映射，這可讓您實現裝置管理和發佈的新敏捷方法。</span><span class="sxs-lookup"><span data-stu-id="91983-128">This process eliminates reimaging during deployment, which lets you implement new, agile methods of device management and distribution.</span></span>

## <span data-ttu-id="91983-129">現代化管理</span><span class="sxs-lookup"><span data-stu-id="91983-129">Modern management</span></span>

<span data-ttu-id="91983-130">Autopilot 是 Surface 裝置的建議部署選項，包括 Surface Pro 7 +、Surface mobile 3、Surface Pro 7 及 Surface Pro X （專為透過 Autopilot 進行部署而設計）。</span><span class="sxs-lookup"><span data-stu-id="91983-130">Autopilot is the recommended deployment option for Surface devices, including Surface Pro 7+, Surface Laptop 3, Surface Pro 7, and Surface Pro X, which is specifically designed for deployment through Autopilot.</span></span>

 <span data-ttu-id="91983-131">最佳做法是使用 Microsoft 雲端解決方案提供者的說明來註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="91983-131">It's best to enroll your Surface devices with the help of a Microsoft Cloud Solution Provider.</span></span> <span data-ttu-id="91983-132">此步驟可讓您直接從 Intune 管理 Surface 中的 UEFI 固件設定。</span><span class="sxs-lookup"><span data-stu-id="91983-132">This step allows you to manage UEFI firmware settings on Surface directly from Intune.</span></span> <span data-ttu-id="91983-133">它不需要實際觸控裝置就能管理證書。</span><span class="sxs-lookup"><span data-stu-id="91983-133">It eliminates the need to physically touch devices for certificate management.</span></span> <span data-ttu-id="91983-134">如需詳細資訊，請參閱 [Intune 的 SURFACE UEFI 設定](surface-manage-dfci-guide.md) 。</span><span class="sxs-lookup"><span data-stu-id="91983-134">See [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md) for details.</span></span>

## <span data-ttu-id="91983-135">Windows 版本注意事項</span><span class="sxs-lookup"><span data-stu-id="91983-135">Windows version considerations</span></span>

<span data-ttu-id="91983-136">透過 Windows Autopilot 廣泛部署 Surface 裝置，包括購買時由 Surface 合作夥伴進行註冊，需要 Windows 10 版本 1709 (秋季創意者更新) 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="91983-136">Broad deployment of Surface devices through Windows Autopilot, including enrollment by Surface partners at the time of purchase, requires Windows 10 Version 1709 (Fall Creators Update) or later.</span></span>

<span data-ttu-id="91983-137">這些 Windows 版本支援4000個位元組 (4k) 雜湊值，可唯一識別 Windows Autopilot 的裝置，以便在規模進行部署時使用。</span><span class="sxs-lookup"><span data-stu-id="91983-137">These Windows versions support a 4,000-byte (4k) hash value that uniquely identifies devices for Windows Autopilot, which is necessary for deployments at scale.</span></span> <span data-ttu-id="91983-138">所有新的 Surface 裝置，包括 Surface Pro 7 +、Surface Pro X 和 Surface 膝上型電腦3隨附于 Windows 10 版本1903或更新版本。</span><span class="sxs-lookup"><span data-stu-id="91983-138">All new Surface devices, including Surface Pro 7+, Surface Pro X, and Surface Laptop 3 ship with Windows 10 Version 1903 or later.</span></span>

## <span data-ttu-id="91983-139">需要修復或更換的 Surface 裝置上的 Exchange 體驗</span><span class="sxs-lookup"><span data-stu-id="91983-139">Exchange experience on Surface devices in need of repair or replacement</span></span>

<span data-ttu-id="91983-140">Microsoft 會自動檢查 Autopilot 註冊的每個 Surface，並將裝置從客戶的租使用者取消註冊。</span><span class="sxs-lookup"><span data-stu-id="91983-140">Microsoft automatically checks every Surface for Autopilot enrollment and will deregister the device from the customer's tenant.</span></span>  <span data-ttu-id="91983-141">只要將更換傳回給客戶，Microsoft 就能確保將更換裝置登記至 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="91983-141">Microsoft ensures the replacement device is enrolled into Windows Autopilot once a replacement is shipped back to the customer.</span></span> <span data-ttu-id="91983-142">此服務可在所有裝置 exchange 服務訂單上直接使用 Microsoft 取得。</span><span class="sxs-lookup"><span data-stu-id="91983-142">This service is available on all device exchange service orders directly with Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="91983-143">當客戶使用合作夥伴傳回裝置時，合作夥伴負責管理 exchange 程式，包括將裝置登出並註冊至 Windows Autopilot。</span><span class="sxs-lookup"><span data-stu-id="91983-143">When customers use a Partner to return devices, the Partner is responsible for managing the exchange process including deregistering and enrolling devices into Windows Autopilot.</span></span>

## <span data-ttu-id="91983-144">Microsoft 支援註冊</span><span class="sxs-lookup"><span data-stu-id="91983-144">Microsoft Support registration</span></span>

<span data-ttu-id="91983-145">客戶與 Microsoft 雲端方案提供者 (Csp) 可以透過提交要求到 Microsoft 支援來註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="91983-145">Customers and Microsoft Cloud Solution Providers (CSPs) have the option of registering Surface devices by submitting requests to Microsoft Support.</span></span> <span data-ttu-id="91983-146">若要深入瞭解，請參閱 [Windows Autopilot 的 Surface 註冊支援](surface-autopilot-registration-support.md)。</span><span class="sxs-lookup"><span data-stu-id="91983-146">To learn more, see [Surface Registration Support for Windows Autopilot](surface-autopilot-registration-support.md).</span></span>

## <span data-ttu-id="91983-147">已啟用 Windows Autopilot 的 Surface 合作夥伴</span><span class="sxs-lookup"><span data-stu-id="91983-147">Surface partners enabled for Windows Autopilot</span></span>

<span data-ttu-id="91983-148">選取 [Surface partner （Surface）合作夥伴] 可在購買時為您在 Windows Autopilot 中註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="91983-148">Select Surface partners can enroll Surface devices in Windows Autopilot for you at the time of purchase.</span></span> <span data-ttu-id="91983-149">他們也可以直接將已註冊的裝置傳送給您的使用者。</span><span class="sxs-lookup"><span data-stu-id="91983-149">They can also ship enrolled devices directly to your users.</span></span> <span data-ttu-id="91983-150">您可以使用 Windows Autopilot、Azure AD 及行動裝置管理，完全透過零觸控程式來設定裝置。</span><span class="sxs-lookup"><span data-stu-id="91983-150">The devices can be configured entirely through a zero-touch process by using Windows Autopilot, Azure AD, and mobile device management.</span></span>

<span data-ttu-id="91983-151">已啟用 Windows Autopilot 的 Surface 合作夥伴包括：</span><span class="sxs-lookup"><span data-stu-id="91983-151">Surface partners that are enabled for Windows Autopilot include:</span></span>

| <span data-ttu-id="91983-152">美國合作夥伴</span><span class="sxs-lookup"><span data-stu-id="91983-152">US partners</span></span> | <span data-ttu-id="91983-153">全球合作夥伴</span><span class="sxs-lookup"><span data-stu-id="91983-153">Global partners</span></span> | <span data-ttu-id="91983-154">美國分銷商</span><span class="sxs-lookup"><span data-stu-id="91983-154">US distributors</span></span> |
|--------------|---------------|-------------------|
| <span data-ttu-id="91983-155">\* [CDW](https://www.cdw.com/)</span><span class="sxs-lookup"><span data-stu-id="91983-155">\* [CDW](https://www.cdw.com/)</span></span> | <span data-ttu-id="91983-156">\* [也](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span><span class="sxs-lookup"><span data-stu-id="91983-156">\* [ALSO](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp)</span></span> | <span data-ttu-id="91983-157">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span><span class="sxs-lookup"><span data-stu-id="91983-157">\* [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)</span></span>  |
| <span data-ttu-id="91983-158">\* [連結](https://www.connection.com/brand/microsoft/microsoft-surface)</span><span class="sxs-lookup"><span data-stu-id="91983-158">\* [Connection](https://www.connection.com/brand/microsoft/microsoft-surface)</span></span>   | <span data-ttu-id="91983-159">\* [ATEA](https://www.atea.com/)</span><span class="sxs-lookup"><span data-stu-id="91983-159">\* [ATEA](https://www.atea.com/)</span></span> | <span data-ttu-id="91983-160">\* [Techdata](https://www.techdata.com/)</span><span class="sxs-lookup"><span data-stu-id="91983-160">\* [Techdata](https://www.techdata.com/)</span></span>  |
| <span data-ttu-id="91983-161">\* [見解](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span><span class="sxs-lookup"><span data-stu-id="91983-161">\* [Insight](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)</span></span>  | <span data-ttu-id="91983-162">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span><span class="sxs-lookup"><span data-stu-id="91983-162">\* [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot)</span></span> | <span data-ttu-id="91983-163">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span><span class="sxs-lookup"><span data-stu-id="91983-163">\* [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)</span></span>   |
| <span data-ttu-id="91983-164">\* [SHI](https://www.shi.com/Surface)</span><span class="sxs-lookup"><span data-stu-id="91983-164">\* [SHI](https://www.shi.com/Surface)</span></span> | <span data-ttu-id="91983-165">\* [Cancom](https://www.cancom.de/)</span><span class="sxs-lookup"><span data-stu-id="91983-165">\* [Cancom](https://www.cancom.de/)</span></span> |    |
| <span data-ttu-id="91983-166">\* [LDI 連接](https://www.myldi.com/managed-it/)</span><span class="sxs-lookup"><span data-stu-id="91983-166">\* [LDI Connect](https://www.myldi.com/managed-it/)</span></span>  | <span data-ttu-id="91983-167">\* [Computacenter](https://www.computacenter.com/uk)</span><span class="sxs-lookup"><span data-stu-id="91983-167">\* [Computacenter](https://www.computacenter.com/uk)</span></span> |    |
| <span data-ttu-id="91983-168">\* [複合鍵](https://www.functiononeit.com/#empower)</span><span class="sxs-lookup"><span data-stu-id="91983-168">\* [F1](https://www.functiononeit.com/#empower)</span></span>  |   |  |
| <span data-ttu-id="91983-169">\* [受保護的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span><span class="sxs-lookup"><span data-stu-id="91983-169">\* [Protected Trust](https://go.microsoft.com/fwlink/p/?LinkID=2129005)</span></span> | | | 

## <span data-ttu-id="91983-170">深入了解</span><span class="sxs-lookup"><span data-stu-id="91983-170">Learn more</span></span>

<span data-ttu-id="91983-171">如需有關 Windows Autopilot 的詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="91983-171">For more information about Windows Autopilot, see:</span></span>
- [<span data-ttu-id="91983-172">Windows Autopilot 概觀</span><span class="sxs-lookup"><span data-stu-id="91983-172">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [<span data-ttu-id="91983-173">Windows Autopilot 需求</span><span class="sxs-lookup"><span data-stu-id="91983-173">Windows Autopilot requirements</span></span>](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [<span data-ttu-id="91983-174">適用於 Windows Autopilot 的 Surface 註冊支援</span><span class="sxs-lookup"><span data-stu-id="91983-174">Surface Registration Support for Windows Autopilot</span></span>](surface-autopilot-registration-support.md)