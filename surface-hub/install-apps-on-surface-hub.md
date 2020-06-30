---
title: 在 Microsoft Surface Hub 上安裝應用程式
description: 系統管理員可以從 Microsoft 網上商店或商務用 Microsoft 網上商店安裝應用程式。
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: install apps, Microsoft Store, Microsoft Store for Business, 安裝應用程式, Microsoft 網上商店, 商務用 Microsoft 網上商店
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 462b76451bd12547d1c1560054a51bb88c218f96
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831617"
---
# <span data-ttu-id="b09f8-104">在 Microsoft Surface Hub 上安裝應用程式</span><span class="sxs-lookup"><span data-stu-id="b09f8-104">Install apps on your Microsoft Surface Hub</span></span>

<span data-ttu-id="b09f8-105">您可以在 Surface Hub 上安裝其他應用程式，以滿足您團隊或組織的需求。</span><span class="sxs-lookup"><span data-stu-id="b09f8-105">You can install additional apps on your Surface Hub to fit your team or organization's needs.</span></span> <span data-ttu-id="b09f8-106">有不同的方法可安裝應用程式，取決於您是否在開發及測試應用程式，或是要部署已發佈的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-106">There are different methods for installing apps depending on whether you are developing and testing an app, or deploying a released app.</span></span> <span data-ttu-id="b09f8-107">本主題會針對不同案例說明安裝應用程式的方法。</span><span class="sxs-lookup"><span data-stu-id="b09f8-107">This topic describes methods for installing apps for either scenario.</span></span>

<span data-ttu-id="b09f8-108">關於 Surface Hub 上的應用程式，必須先了解幾件事：</span><span class="sxs-lookup"><span data-stu-id="b09f8-108">A few things to know about apps on Surface Hub:</span></span>
- <span data-ttu-id="b09f8-109">Surface Hub 僅能執行[通用 Windows 平台 (UWP) 應用程式](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-109">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="b09f8-110">使用 [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) 建立的應用程式將無法在 Surface Hub 上執行。</span><span class="sxs-lookup"><span data-stu-id="b09f8-110">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="b09f8-111">應用程式必須以[通用裝置系列](https://msdn.microsoft.com/library/windows/apps/dn894631)或 Windows 小組裝置系列為目標。</span><span class="sxs-lookup"><span data-stu-id="b09f8-111">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="b09f8-112">Surface Hub 只支援來自[Microsoft Store For Business](https://businessstore.microsoft.com/store)的[離線授權 app](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 。</span><span class="sxs-lookup"><span data-stu-id="b09f8-112">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="b09f8-113">根據預設，應用程式必須經過市集簽署才能安裝。</span><span class="sxs-lookup"><span data-stu-id="b09f8-113">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="b09f8-114">在測試和開發期間，您也可以選擇將裝置切換到開發人員模式來執行開發人員簽署的 UWP app。</span><span class="sxs-lookup"><span data-stu-id="b09f8-114">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="b09f8-115">當您將應用程式提交到 Microsoft Store 時，開發人員需要設定裝置系列的可用性與組織授權選項，以確保可在 Surface Hub 上執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-115">When submitting an app to the Microsoft Store, developers need to set Device family availability and Organizational licensing options to make sure an app will be available to run on Surface Hub.</span></span>
- <span data-ttu-id="b09f8-116">您需要系統管理員認證，才能在 Surface Hub 上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-116">You need admin credentials to install apps on your Surface Hub.</span></span> <span data-ttu-id="b09f8-117">由於裝置是針對在共用空間 (例如會議室) 中使用所設計，因此人員無法存取 Microsoft 網上商店來下載和安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-117">Since the device is designed to be used in communal spaces like meeting rooms, people can't access the Microsoft Store to download and install apps.</span></span>


## <span data-ttu-id="b09f8-118">開發和測試應用程式</span><span class="sxs-lookup"><span data-stu-id="b09f8-118">Develop and test apps</span></span>
<span data-ttu-id="b09f8-119">當您開發自己的應用程式時，有幾個選項可在 Surface Hub 上測試應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-119">While you're developing your own app, there are a few options for testing apps on Surface Hub.</span></span>

### <span data-ttu-id="b09f8-120">開發人員模式</span><span class="sxs-lookup"><span data-stu-id="b09f8-120">Developer Mode</span></span>
<span data-ttu-id="b09f8-121">根據預設，Surface Hub 僅能執行已發佈到 Microsoft 網上商店並經由市集簽署的 UWP應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-121">By default, Surface Hub only runs UWP apps that have been published to and signed by the Microsoft Store.</span></span> <span data-ttu-id="b09f8-122">提交到 Microsoft 網上商店的應用程式會在[應用程式認證程序](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process)中進行安全性及合規性測試，因此這有助於保護您的 Surface Hub 防範惡意應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-122">Apps submitted to the Microsoft Store go through security and compliance tests as part of the [app certification process](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process), so this helps safeguard your Surface Hub against malicious apps.</span></span>
 
<span data-ttu-id="b09f8-123">透過啟用開發人員模式，您也可以安裝開發人員簽署的 UWP應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-123">By enabling developer mode, you can also install developer-signed UWP apps.</span></span>
 
> [!IMPORTANT]
> <span data-ttu-id="b09f8-124">啟用開發人員模式之後，您必須重設 Surface Hub 才能將它停用。</span><span class="sxs-lookup"><span data-stu-id="b09f8-124">After developer mode has been enabled, you will need to reset the Surface Hub to disable it.</span></span> <span data-ttu-id="b09f8-125">重設裝置會移除所有本機使用者檔案和設定，然後重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="b09f8-125">Resetting the device removes all local user files and configurations and then reinstalls Windows.</span></span>

**<span data-ttu-id="b09f8-126">開啟開發人員模式</span><span class="sxs-lookup"><span data-stu-id="b09f8-126">To turn on developer mode</span></span>** 
1. <span data-ttu-id="b09f8-127">從您的 Surface Hub 啟動 **\[設定\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-127">From your Surface Hub, start **Settings**.</span></span>
2. <span data-ttu-id="b09f8-128">出現提示時，請輸入裝置系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="b09f8-128">Type the device admin credentials when prompted.</span></span>
3. <span data-ttu-id="b09f8-129">瀏覽至 **\[更新與安全性\]** > **\[開發人員專用\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-129">Navigate to **Update & security** > **For developers**.</span></span>
4. <span data-ttu-id="b09f8-130">選取 **\[開發人員模式\]** 並接受警告提示。</span><span class="sxs-lookup"><span data-stu-id="b09f8-130">Select **Developer mode** and accept the warning prompt.</span></span>

### <span data-ttu-id="b09f8-131">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b09f8-131">Visual Studio</span></span>
<span data-ttu-id="b09f8-132">在開發期間，在 Surface Hub 上測試您應用程式的最簡單方式是使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="b09f8-132">During development, the easiest way to test your app on a Surface Hub is using Visual Studio.</span></span> <span data-ttu-id="b09f8-133">Visual Studio 的遠端偵錯功能可協助您在廣泛部署應用程式之前發現問題。</span><span class="sxs-lookup"><span data-stu-id="b09f8-133">Visual Studio's remote debugging feature helps you discover issues in your app before deploying it broadly.</span></span> <span data-ttu-id="b09f8-134">如需詳細資訊，請參閱[使用 Visual Studio 測試 Surface Hub應用程式](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-134">For more information, see [Test Surface Hub apps using Visual Studio](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio).</span></span>

### <span data-ttu-id="b09f8-135">佈建套件</span><span class="sxs-lookup"><span data-stu-id="b09f8-135">Provisioning package</span></span>
<span data-ttu-id="b09f8-136">使用 Visual Studio 為您的 UWP應用程式[建立應用程式套件](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx)，並使用測試憑證簽署。</span><span class="sxs-lookup"><span data-stu-id="b09f8-136">Use Visual Studio to [create an app package](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx) for your UWP app, signed using a test certificate.</span></span> <span data-ttu-id="b09f8-137">然後使用 Windows 映像處理與設定設計工具 (ICD) 建立包含應用程式套件的佈建套件。</span><span class="sxs-lookup"><span data-stu-id="b09f8-137">Then use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package.</span></span> <span data-ttu-id="b09f8-138">如需詳細資訊，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-138">For more information, see [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md).</span></span>


## <span data-ttu-id="b09f8-139">將應用程式提交至 Microsoft 網上商店</span><span class="sxs-lookup"><span data-stu-id="b09f8-139">Submit apps to the Microsoft Store</span></span>
<span data-ttu-id="b09f8-140">一旦應用程式準備好發佈，開發人員必須提交應用程式並發佈至 Microsoft 網上商店。</span><span class="sxs-lookup"><span data-stu-id="b09f8-140">Once an app is ready for release, developers need to submit and publish it to the Microsoft Store.</span></span> <span data-ttu-id="b09f8-141">如需詳細資訊，請參閱[發佈 Windows 應用程式](https://developer.microsoft.com/store/publish-apps)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-141">For more information, see [Publish Windows apps](https://developer.microsoft.com/store/publish-apps).</span></span>

<span data-ttu-id="b09f8-142">在應用程式提交過程中，開發人員必須設定 **\[裝置系列可用性\]** 與 **\[組織授權\]** 選項，以確保應用程式可在 Surface Hub 上執行。</span><span class="sxs-lookup"><span data-stu-id="b09f8-142">During app submission, developers need to set **Device family availability** and **Organizational licensing** options to make sure the app will be available to run on Surface Hub.</span></span>

**<span data-ttu-id="b09f8-143">設定裝置系列可用性</span><span class="sxs-lookup"><span data-stu-id="b09f8-143">To set device family availability</span></span>**  
1. <span data-ttu-id="b09f8-144">在 [Windows 開發人員中心](https://developer.microsoft.com)上，瀏覽至您的 app 提交頁面。</span><span class="sxs-lookup"><span data-stu-id="b09f8-144">On the [Windows Dev Center](https://developer.microsoft.com), navigate to your app submission page.</span></span>
2. <span data-ttu-id="b09f8-145">選取 **\[套件\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-145">Select **Packages**.</span></span>
3. <span data-ttu-id="b09f8-146">在 **\[裝置系列可用性\]** 底下，選取下列選項：</span><span class="sxs-lookup"><span data-stu-id="b09f8-146">Under **Device family availability**, select these options:</span></span>
    
    - **<span data-ttu-id="b09f8-147">Windows 10 團隊版</span><span class="sxs-lookup"><span data-stu-id="b09f8-147">Windows 10 Team</span></span>**
    - **<span data-ttu-id="b09f8-148">讓 Microsoft 決定是否使應用程式可提供給任何未來的裝置系列</span><span class="sxs-lookup"><span data-stu-id="b09f8-148">Let Microsoft decide whether to make the app available to any future device families</span></span>**
  
![顯示 \[裝置系列可用性\] 頁面的影像 - Microsoft 網上商店應用程式提交程序的一部分](images/device-family.png)  
    
<span data-ttu-id="b09f8-150">如需詳細資訊，請參閱[裝置系列可用性](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-150">For more information, see [Device family availability](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability).</span></span>

**<span data-ttu-id="b09f8-151">設定組織授權</span><span class="sxs-lookup"><span data-stu-id="b09f8-151">To set organizational licensing</span></span>**
1. <span data-ttu-id="b09f8-152">在 [Windows 開發人員中心](https://developer.microsoft.com)上，瀏覽至您的應用程式提交頁面。</span><span class="sxs-lookup"><span data-stu-id="b09f8-152">On the [Windows Dev Center](https://developer.microsoft.com), navigate to your app submission page.</span></span>
2. <span data-ttu-id="b09f8-153">選取 **\[定價和可用性\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-153">Select **Pricing and availability**.</span></span>
3. <span data-ttu-id="b09f8-154">在 \[組織授權\] 底下，選取 **\[允許組織中斷連線 (離線) 授權\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-154">Under Organizational licensing, select **Allow disconnected (offline) licensing for organizations**.</span></span>

![顯示 \[組織授權\] 頁面的影像 - Microsoft 網上商店應用程式提交程序的一部分。](images/sh-org-licensing.png)

> [!NOTE]
> <span data-ttu-id="b09f8-156">預設已選取 **\[利用「市集」管理 (線上) 大量授權提供組織使用我的應用程式\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-156">**Make my app available to organizations with Store-managed (online) licensing and distribution** is selected by default.</span></span>

> [!NOTE]
> <span data-ttu-id="b09f8-157">開發人員也可以直接將企業營運應用程式發佈到企業，而不需要在市集中廣泛提供。</span><span class="sxs-lookup"><span data-stu-id="b09f8-157">Developers can also publish line-of-business apps directly to enterprises without making them broadly available in the Store.</span></span> <span data-ttu-id="b09f8-158">如需詳細資訊，請參閱[發佈 LOB 應用程式到企業](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-158">For more information, see [Distribute LOB apps to enterprises](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises).</span></span>

<span data-ttu-id="b09f8-159">如需詳細資訊，請參閱[組織授權選項](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-159">For more information, see [Organizational licensing options](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing).</span></span>


## <span data-ttu-id="b09f8-160">部署已發佈的應用程式</span><span class="sxs-lookup"><span data-stu-id="b09f8-160">Deploy released apps</span></span>

<span data-ttu-id="b09f8-161">有幾個選項可用於安裝已發佈到 Microsoft 網上商店的應用程式，取決於您要在少數裝置上評估它們，或是在組織中廣泛部署。</span><span class="sxs-lookup"><span data-stu-id="b09f8-161">There are several options for installing apps that have been released to the Microsoft Store, depending on whether you want to evaluate them on a few devices, or deploy them broadly to your organization.</span></span>

<span data-ttu-id="b09f8-162">安裝已發佈的應用程式：</span><span class="sxs-lookup"><span data-stu-id="b09f8-162">To install released apps:</span></span>
- <span data-ttu-id="b09f8-163">使用 Microsoft 網上商店應用程式下載應用程式，或</span><span class="sxs-lookup"><span data-stu-id="b09f8-163">Download the app using the Microsoft Store app, or</span></span>
- <span data-ttu-id="b09f8-164">從商務用 Microsoft 網上商店下載應用程式套件，然後使用佈建套件或支援的 MDM 提供者發佈。</span><span class="sxs-lookup"><span data-stu-id="b09f8-164">Download the app package from the Microsoft Store for Business, and distribute it using a provisioning package or a supported MDM provider.</span></span>

### <span data-ttu-id="b09f8-165">Microsoft 網上商店應用程式</span><span class="sxs-lookup"><span data-stu-id="b09f8-165">Microsoft Store app</span></span>
<span data-ttu-id="b09f8-166">若要評估在 Microsoft 網上商店上發佈的應用程式，請在 Surface Hub 上使用 Microsoft 網上商店應用程式來瀏覽並下載應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-166">To evaluate apps released on the Microsoft Store, use the Microsoft Store app on the Surface Hub to browse and download apps.</span></span>

> [!NOTE]
> <span data-ttu-id="b09f8-167">不建議使用 Microsoft 網上商店應用程式做為在組織中大規模部署應用程式的方法：</span><span class="sxs-lookup"><span data-stu-id="b09f8-167">Using the Microsoft Store app is not the recommended method of deploying apps at scale to your organization:</span></span>
> - <span data-ttu-id="b09f8-168">若要下載應用程式，您必須使用 Microsoft 帳戶或組織帳戶登入 Microsoft 網上商店應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-168">To download apps, you must sign in to the Microsoft Store app with a Microsoft account or organizational account.</span></span> <span data-ttu-id="b09f8-169">不過，您一次只能將帳戶連線到最多 10 部裝置。</span><span class="sxs-lookup"><span data-stu-id="b09f8-169">However, you can only connect an account to a maximum of 10 devices at once.</span></span> <span data-ttu-id="b09f8-170">如果您擁有超過 10 部 Surface Hub，您將需要建立多個帳戶，或在應用程式安裝期間從您的帳戶中移除裝置。</span><span class="sxs-lookup"><span data-stu-id="b09f8-170">If you have more than 10 Surface Hubs, you will need to create multiple accounts or remove devices from your account between app installations.</span></span>
> - <span data-ttu-id="b09f8-171">若要安裝應用程式，您必須在所擁有的每部 Surface Hub 上手動登入 Microsoft 網上商店應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-171">To install apps, you will need to manually sign in to the Microsoft Store app on each Surface Hub you own.</span></span>

**<span data-ttu-id="b09f8-172">在 Surface Hub 上瀏覽 Microsoft 網上商店</span><span class="sxs-lookup"><span data-stu-id="b09f8-172">To browse the Microsoft Store on Surface Hub</span></span>** 
1. <span data-ttu-id="b09f8-173">從您的 Surface Hub 啟動 **\[設定\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-173">From your Surface Hub, start **Settings**.</span></span>
2. <span data-ttu-id="b09f8-174">出現提示時，請輸入裝置系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="b09f8-174">Type the device admin credentials when prompted.</span></span>
3. <span data-ttu-id="b09f8-175">瀏覽至 **\[此裝置\]** > **\[應用程式與功能\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-175">Navigate to **This device** > **Apps & features**.</span></span>
4. <span data-ttu-id="b09f8-176">選取 **\[開啟市集\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-176">Select **Open Store**.</span></span>

### <span data-ttu-id="b09f8-177">從商務用 Microsoft 網上商店下載應用程式套件</span><span class="sxs-lookup"><span data-stu-id="b09f8-177">Download app packages from Microsoft Store for Business</span></span>
<span data-ttu-id="b09f8-178">若要下載在 Surface Hub 上安裝應用程式所需的應用程式套件，請造訪[商務用 Microsoft 網上商店](https://www.microsoft.com/business-store)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-178">To download the app package you need to install apps on your Surface Hub, visit the [Microsoft Store for Business](https://www.microsoft.com/business-store).</span></span> <span data-ttu-id="b09f8-179">商務用 Store 是您可以為組織中的 Windows10 裝置 (包括 Surface Hub) 尋找、取得和管理應用程式的地方。</span><span class="sxs-lookup"><span data-stu-id="b09f8-179">The Store for Business is where you can find, acquire, and manage apps for the Windows 10 devices in your organization, including Surface Hub.</span></span>
 
> [!NOTE]
> <span data-ttu-id="b09f8-180">目前，Surface Hub 僅支援透過商務用 Store 提供的離線授權應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-180">Currently, Surface Hub only supports offline-licensed apps available through the Store for Business.</span></span> <span data-ttu-id="b09f8-181">應用程式開發人員在提交應用程式時會設定離線授權可用性。</span><span class="sxs-lookup"><span data-stu-id="b09f8-181">App developers set offline-license availability when they submit apps.</span></span>

<span data-ttu-id="b09f8-182">尋找並取得您要的應用程式，然後下載：</span><span class="sxs-lookup"><span data-stu-id="b09f8-182">Find and acquire the app you want, then download:</span></span>
- <span data-ttu-id="b09f8-183">離線授權應用程式套件 (.appx 或 .appxbundle)</span><span class="sxs-lookup"><span data-stu-id="b09f8-183">The offline-licensed app package (either an .appx or an .appxbundle)</span></span>
- <span data-ttu-id="b09f8-184">「未編碼的」\*\* 授權檔案 (如果您要使用佈建套件安裝應用程式)</span><span class="sxs-lookup"><span data-stu-id="b09f8-184">The *unencoded* license file (if you're using provisioning packages to install the app)</span></span>
- <span data-ttu-id="b09f8-185">「已編碼的」\*\* 授權檔案 (如果您要使用 MDM 發佈應用程式)</span><span class="sxs-lookup"><span data-stu-id="b09f8-185">The *encoded* license file (if you're using MDM to distribute the app)</span></span>
- <span data-ttu-id="b09f8-186">任何必要的相依性檔案</span><span class="sxs-lookup"><span data-stu-id="b09f8-186">Any necessary dependency files</span></span>

<span data-ttu-id="b09f8-187">如需詳細資訊，請參閱[下載離線授權應用程式](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-187">For more information, see [Download an offline-licensed app](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).</span></span>

### <span data-ttu-id="b09f8-188">佈建套件</span><span class="sxs-lookup"><span data-stu-id="b09f8-188">Provisioning package</span></span>
<span data-ttu-id="b09f8-189">您可以使用佈建套件，在少數 Surface Hub 上手動安裝從商務用 Store 下載的離線授權應用程式。</span><span class="sxs-lookup"><span data-stu-id="b09f8-189">You can manually install the offline-licensed apps that you downloaded from the Store for Business on a few Surface Hubs using provisioning packages.</span></span> <span data-ttu-id="b09f8-190">使用 Windows 映像處理與設定設計工具 (ICD) 建立佈建套件，其中包含應用程式套件與您從商務用 Store 下載的「未編碼」\*\* 授權檔案。</span><span class="sxs-lookup"><span data-stu-id="b09f8-190">Use Windows Imaging and Configuration Designer (ICD) to create a provisioning package containing the app package and *unencoded* license file that you downloaded from the Store for Business.</span></span> <span data-ttu-id="b09f8-191">如需詳細資訊，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-191">For more information, see [Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md).</span></span>

### <span data-ttu-id="b09f8-192">支援的 MDM 提供者</span><span class="sxs-lookup"><span data-stu-id="b09f8-192">Supported MDM provider</span></span>
<span data-ttu-id="b09f8-193">若要將應用程式部署到組織中大量的 Surface Hub，請使用支援的 MDM 提供者。</span><span class="sxs-lookup"><span data-stu-id="b09f8-193">To deploy apps to a large number of Surface Hubs in your organization, use a supported MDM provider.</span></span> <span data-ttu-id="b09f8-194">下表顯示哪些 MDM 提供者支援部署離線授權應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="b09f8-194">The table below shows which MDM providers support deploying offline-licensed app packages.</span></span>

| <span data-ttu-id="b09f8-195">MDM 提供者</span><span class="sxs-lookup"><span data-stu-id="b09f8-195">MDM provider</span></span>                | <span data-ttu-id="b09f8-196">支援離線授權應用程式套件</span><span class="sxs-lookup"><span data-stu-id="b09f8-196">Supports offline-licensed app packages</span></span> |
|-----------------------------|----------------------------------------|
| <span data-ttu-id="b09f8-197">含 Configuration Manager 的內部部署 MDM （從版本1602開始）</span><span class="sxs-lookup"><span data-stu-id="b09f8-197">On-premises MDM with  Configuration Manager (beginning in version 1602)</span></span> | <span data-ttu-id="b09f8-198">是</span><span class="sxs-lookup"><span data-stu-id="b09f8-198">Yes</span></span> |
|
| <span data-ttu-id="b09f8-199">協力廠商 MDM 提供者</span><span class="sxs-lookup"><span data-stu-id="b09f8-199">Third-party MDM provider</span></span>    | <span data-ttu-id="b09f8-200">檢查以確認您的 MDM 提供者支援部署離線授權應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="b09f8-200">Check to make sure your MDM provider supports deploying offline-licensed app packages.</span></span> |

**<span data-ttu-id="b09f8-201">使用 Microsoft 端點 Configuration Manager 遠端部署應用程式</span><span class="sxs-lookup"><span data-stu-id="b09f8-201">To deploy apps remotely using Microsoft Endpoint Configuration Manager</span></span>**

> [!NOTE]
> <span data-ttu-id="b09f8-202">這些指示是以 Microsoft 端點建構管理員的目前分支為基礎。</span><span class="sxs-lookup"><span data-stu-id="b09f8-202">These instructions are based on the current branch of Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="b09f8-203">向 Configuration Manager 註冊 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="b09f8-203">Enroll your Surface Hubs to Configuration Manager.</span></span> <span data-ttu-id="b09f8-204">如需詳細資訊，請參閱[將 Surface Hub 註冊到 MDM](manage-settings-with-mdm-for-surface-hub.md#enroll-into-mdm)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-204">For more information, see [Enroll a Surface Hub into MDM](manage-settings-with-mdm-for-surface-hub.md#enroll-into-mdm).</span></span>
2. <span data-ttu-id="b09f8-205">從商務用 Store 下載離線授權應用程式套件、「已編碼的」\*\* 授權檔案，和任何必要的相依性檔案。</span><span class="sxs-lookup"><span data-stu-id="b09f8-205">Download the offline-licensed app package, the *encoded* license file, and any necessary dependency files from the Store for Business.</span></span> <span data-ttu-id="b09f8-206">如需詳細資訊，請參閱[下載離線授權應用程式](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-206">For more information, see [Download an offline-licensed app](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app).</span></span> <span data-ttu-id="b09f8-207">將下載的檔案放入網路共用上的相同資料夾。</span><span class="sxs-lookup"><span data-stu-id="b09f8-207">Place the downloaded files in the same folder on a network share.</span></span>
3. <span data-ttu-id="b09f8-208">在 Configuration Manager 主控台的 **\[軟體程式庫\]** 工作區中，按一下 **\[概觀\]** > **\[應用程式管理\]** > **\[應用程式\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-208">In the **Software Library** workspace of the Configuration Manager console, click **Overview** > **Application Management** > **Applications**.</span></span>
4. <span data-ttu-id="b09f8-209">在 **\[首頁\]** 索引標籤上的 **\[建立\]** 群組中，按一下 **\[建立應用程式\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-209">On the **Home** tab, in the **Create** group, click **Create Application**.</span></span>
5. <span data-ttu-id="b09f8-210">在 **\[建立應用程式精靈\]** 的 **\[一般\]** 頁面，選取 **\[從安裝檔案自動偵測此應用程式的相關資訊\]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b09f8-210">On the **General** page of the **Create Application Wizard**, select the **Automatically detect information about this application from installation files** check box.</span></span>
6. <span data-ttu-id="b09f8-211">在 **\[類型\]** 下拉式清單中，選取 **\[Windows 應用程式套件 (\*.appx, \*.appxbundle)\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-211">In the **Type** drop-down list, select **Windows app package (\*.appx, \*.appxbundle)**.</span></span>
7. <span data-ttu-id="b09f8-212">在 **\[位置\]** 欄位中，以下列格式針對您從商務用 Store 下載的離線授權應用程式套件指定 UNC 路徑：\\server\share\\filename。</span><span class="sxs-lookup"><span data-stu-id="b09f8-212">In the **Location** field, specify the UNC path in the form \\server\share\\filename for the offline-licensed app package that you downloaded from the Store for Business.</span></span> <span data-ttu-id="b09f8-213">您也可以按一下 **\[瀏覽\]** 來瀏覽到應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="b09f8-213">Alternatively, click **Browse** to browse to the app package.</span></span>
8. <span data-ttu-id="b09f8-214">在 **\[匯入資訊\]** 頁面上檢閱匯入的資訊，然後按一下 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="b09f8-214">On the **Import Information** page, review the information that was imported, and then click **Next**.</span></span> <span data-ttu-id="b09f8-215">如有需要，您可以按一下 **\[上一步\]** 返回並更正任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="b09f8-215">If necessary, you can click **Previous** to go back and correct any errors.</span></span>
9. <span data-ttu-id="b09f8-216">在 **\[一般資訊\]** 頁面上，完成關於應用程式的其他詳細資料。</span><span class="sxs-lookup"><span data-stu-id="b09f8-216">On the **General Information** page, complete additional details about the app.</span></span> <span data-ttu-id="b09f8-217">如果該應用程式是從應用程式套件中自動取得的，則可能已經填入一些資訊。</span><span class="sxs-lookup"><span data-stu-id="b09f8-217">Some of this information might already be populated if it was automatically obtained from the app package.</span></span>
10. <span data-ttu-id="b09f8-218">按一下 **\[下一步\]**，檢閱 \[摘要\] 頁面上的應用程式資訊，然後完成 \[建立應用程式精靈\]。</span><span class="sxs-lookup"><span data-stu-id="b09f8-218">Click **Next**, review the application information on the Summary page, and then complete the Create Application Wizard.</span></span> 
11. <span data-ttu-id="b09f8-219">建立應用程式的部署類型。</span><span class="sxs-lookup"><span data-stu-id="b09f8-219">Create a deployment type for the application.</span></span> <span data-ttu-id="b09f8-220">如需詳細資訊，請參閱[建立應用程式的部署類型](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-220">For more information, see [Create deployment types for the application](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application).</span></span>
12. <span data-ttu-id="b09f8-221">將應用程式部署到您的 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="b09f8-221">Deploy the application to your Surface Hubs.</span></span> <span data-ttu-id="b09f8-222">如需詳細資訊，請參閱[使用 Microsoft 端點 Configuration Manager 部署應用程式](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-222">For more information, see [Deploy applications with Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications).</span></span>
13. <span data-ttu-id="b09f8-223">視需要從商務用 Store 下載新的套件來更新應用程式，以及在 Configuration Manager 中發佈應用程式修訂。</span><span class="sxs-lookup"><span data-stu-id="b09f8-223">As needed, update the app by downloading a new package from the Store for Business, and publishing an application revision in Configuration Manager.</span></span> <span data-ttu-id="b09f8-224">如需詳細資訊，請參閱[使用 Microsoft 端點設定管理員更新及停用應用程式](https://technet.microsoft.com/library/mt595704.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-224">For more information, see [Update and retire applications with Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt595704.aspx).</span></span> 

> [!NOTE] 
> <span data-ttu-id="b09f8-225">如果您使用的是 Microsoft 端點設定管理員（目前分支），您可以將商務用書店連接至 Configuration Manager，以略過上述步驟。</span><span class="sxs-lookup"><span data-stu-id="b09f8-225">If you are using Microsoft Endpoint Configuration Manager (current branch), you can bypass the above steps by connecting the Store for Business to Configuration Manager.</span></span> <span data-ttu-id="b09f8-226">如此一來，您就可以將您購買的應用程式清單與 Configuration Manager 進行同步處理，並在 Configuration Manager 主控台中查看這些 app，然後像您需要任何其他應用程式一樣部署它們。</span><span class="sxs-lookup"><span data-stu-id="b09f8-226">By doing so, you can synchronize the list of apps you've purchased with Configuration Manager, view these in the Configuration Manager console, and deploy them like you would any other app.</span></span> <span data-ttu-id="b09f8-227">如需詳細資訊，請參閱[使用 Configuration Manager 管理商務用 Microsoft 網上商店的 app](https://technet.microsoft.com/library/mt740630.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b09f8-227">For more information, see [Manage apps from the Microsoft Store for Business with Configuration Manager](https://technet.microsoft.com/library/mt740630.aspx).</span></span>


## <span data-ttu-id="b09f8-228">摘要</span><span class="sxs-lookup"><span data-stu-id="b09f8-228">Summary</span></span>

<span data-ttu-id="b09f8-229">在 Surface Hub 上安裝應用程式的方式有幾種，這要視您是在開發應用程式、評估 app 在少數裝置上，或是將 app 廣泛部署到貴組織而定。</span><span class="sxs-lookup"><span data-stu-id="b09f8-229">There are a few different ways to install apps on your Surface Hub depending on whether you are developing apps, evaluating apps on a small number of devices, or deploying apps broadly to your organization.</span></span> <span data-ttu-id="b09f8-230">下表摘要說明所支援的方法：</span><span class="sxs-lookup"><span data-stu-id="b09f8-230">This table summarizes the supported methods:</span></span>

| <span data-ttu-id="b09f8-231">安裝方法</span><span class="sxs-lookup"><span data-stu-id="b09f8-231">Install method</span></span>             | <span data-ttu-id="b09f8-232">開發應用程式</span><span class="sxs-lookup"><span data-stu-id="b09f8-232">Developing apps</span></span> | <span data-ttu-id="b09f8-233">在少數裝置上</span><span class="sxs-lookup"><span data-stu-id="b09f8-233">Evaluating apps on</span></span> <br> <span data-ttu-id="b09f8-234">評估應用程式</span><span class="sxs-lookup"><span data-stu-id="b09f8-234">a few devices</span></span> | <span data-ttu-id="b09f8-235">將應用程式廣泛部署</span><span class="sxs-lookup"><span data-stu-id="b09f8-235">Deploying apps broadly</span></span> <br> <span data-ttu-id="b09f8-236">到組織中</span><span class="sxs-lookup"><span data-stu-id="b09f8-236">to your organization</span></span> |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| <span data-ttu-id="b09f8-237">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b09f8-237">Visual Studio</span></span>              | <span data-ttu-id="b09f8-238">X</span><span class="sxs-lookup"><span data-stu-id="b09f8-238">X</span></span> |   |   |
| <span data-ttu-id="b09f8-239">佈建套件</span><span class="sxs-lookup"><span data-stu-id="b09f8-239">Provisioning package</span></span>       | <span data-ttu-id="b09f8-240">X</span><span class="sxs-lookup"><span data-stu-id="b09f8-240">X</span></span> | <span data-ttu-id="b09f8-241">X</span><span class="sxs-lookup"><span data-stu-id="b09f8-241">X</span></span> |   |
| <span data-ttu-id="b09f8-242">Microsoft 網上商店應用程式</span><span class="sxs-lookup"><span data-stu-id="b09f8-242">Microsoft Store app</span></span>          |   | <span data-ttu-id="b09f8-243">X</span><span class="sxs-lookup"><span data-stu-id="b09f8-243">X</span></span> |   |
| <span data-ttu-id="b09f8-244">支援的 MDM 提供者</span><span class="sxs-lookup"><span data-stu-id="b09f8-244">Supported MDM provider</span></span>     |   |   | <span data-ttu-id="b09f8-245">X</span><span class="sxs-lookup"><span data-stu-id="b09f8-245">X</span></span> |

## <span data-ttu-id="b09f8-246">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="b09f8-246">More information</span></span>

- [<span data-ttu-id="b09f8-247">部落格文章：使用 Intune 將 Windows 市集應用程式部署到 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="b09f8-247">Blog post:  Deploy Windows Store apps to Surface Hub using Intune</span></span>](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## <span data-ttu-id="b09f8-248">相關主題</span><span class="sxs-lookup"><span data-stu-id="b09f8-248">Related topics</span></span>

[<span data-ttu-id="b09f8-249">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="b09f8-249">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="b09f8-250">Microsoft Surface Hub 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="b09f8-250">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





