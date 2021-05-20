---
title: '使用 Surface 應用程式商務用 Microsoft Store或教育用 Microsoft Store (Surface) '
description: 瞭解如何新增及下載 Surface App 商務用 Microsoft Store或教育用 Microsoft Store，以及使用 PowerShell 和 MDT 安裝 Surface App。
keywords: surface App、App、部署、自訂
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 4/16/2021
ms.openlocfilehash: c7a882859339ff3d7feeb685c62672bc57c301ec
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576523"
---
# <a name="deploy-surface-app-with-microsoft-store-for-business-and-education"></a><span data-ttu-id="4593f-104">使用教育商務用 Microsoft Store部署 Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="4593f-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="4593f-105">適用對象</span><span class="sxs-lookup"><span data-stu-id="4593f-105">Applies to</span></span>**

- <span data-ttu-id="4593f-106">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="4593f-106">Surface Laptop 4</span></span>
- <span data-ttu-id="4593f-107">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="4593f-107">Surface Pro 7+</span></span>
- <span data-ttu-id="4593f-108">Surface Laptop去</span><span class="sxs-lookup"><span data-stu-id="4593f-108">Surface Laptop Go</span></span>
- <span data-ttu-id="4593f-109">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="4593f-109">Surface Pro 7</span></span>
- <span data-ttu-id="4593f-110">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="4593f-110">Surface Laptop 3</span></span>
- <span data-ttu-id="4593f-111">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="4593f-111">Surface Pro 6</span></span>
- <span data-ttu-id="4593f-112">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="4593f-112">Surface Laptop 2</span></span>
- <span data-ttu-id="4593f-113">Surface Go</span><span class="sxs-lookup"><span data-stu-id="4593f-113">Surface Go</span></span>
- <span data-ttu-id="4593f-114">Surface Go 與 LTE</span><span class="sxs-lookup"><span data-stu-id="4593f-114">Surface Go with LTE</span></span>
- <span data-ttu-id="4593f-115">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="4593f-115">Surface Book 2</span></span>
- <span data-ttu-id="4593f-116">配備 LTE Advanced 的 Surface Pro (型號 1807)</span><span class="sxs-lookup"><span data-stu-id="4593f-116">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="4593f-117">Surface Pro (型號 1796)</span><span class="sxs-lookup"><span data-stu-id="4593f-117">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="4593f-118">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="4593f-118">Surface Laptop</span></span>
- <span data-ttu-id="4593f-119">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="4593f-119">Surface Studio</span></span>
- <span data-ttu-id="4593f-120">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="4593f-120">Surface Studio 2</span></span>
- <span data-ttu-id="4593f-121">Surface Book</span><span class="sxs-lookup"><span data-stu-id="4593f-121">Surface Book</span></span>
- <span data-ttu-id="4593f-122">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="4593f-122">Surface Pro 4</span></span>
- <span data-ttu-id="4593f-123">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="4593f-123">Surface 3 LTE</span></span>
- <span data-ttu-id="4593f-124">Surface 3</span><span class="sxs-lookup"><span data-stu-id="4593f-124">Surface 3</span></span>
- <span data-ttu-id="4593f-125">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="4593f-125">Surface Pro 3</span></span>


<span data-ttu-id="4593f-126">Surface 應用程式是輕Microsoft Store應用程式，可控制許多 Surface 特定設定和選項，包括：</span><span class="sxs-lookup"><span data-stu-id="4593f-126">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="4593f-127">啟用或停用 Surface 裝置上的 Windows 鍵</span><span class="sxs-lookup"><span data-stu-id="4593f-127">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="4593f-128">調整 Surface 手寫筆的敏感度</span><span class="sxs-lookup"><span data-stu-id="4593f-128">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="4593f-129">自訂 Surface 手寫筆按鈕動作</span><span class="sxs-lookup"><span data-stu-id="4593f-129">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="4593f-130">啟用或停用 Surface 音訊增強功能</span><span class="sxs-lookup"><span data-stu-id="4593f-130">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="4593f-131">快速存取裝置的支援檔和資訊</span><span class="sxs-lookup"><span data-stu-id="4593f-131">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="4593f-132">使用更新Windows通常會收到 Surface App，做為自動更新的一部分。</span><span class="sxs-lookup"><span data-stu-id="4593f-132">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="4593f-133">但如果您的組織正在準備部署至 Surface 裝置的圖像，您可能會想要將 Surface 應用程式 (之前稱為 Surface Hub) 納入您的影像和部署程式，而不是要求每個個別裝置的使用者從 Microsoft Store 或您的 商務用 Microsoft Store 下載並安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="4593f-133">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="4593f-134">本文不適用於 X Surface Pro。詳細資訊，請參閱部署[、管理](surface-pro-arm-app-management.md)及維護 X Surface Pro</span><span class="sxs-lookup"><span data-stu-id="4593f-134">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <a name="surface-app-overview"></a><span data-ttu-id="4593f-135">Surface 應用程式概觀</span><span class="sxs-lookup"><span data-stu-id="4593f-135">Surface app overview</span></span>

<span data-ttu-id="4593f-136">Surface 應用程式可從 Microsoft Store[免費下載](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)。</span><span class="sxs-lookup"><span data-stu-id="4593f-136">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="4593f-137">使用者可以從 Microsoft Store 下載並安裝它，但如果您的組織改為使用 商務用 Microsoft Store，您必須將其新加到商店的庫存中，並可能將應用程式納入 Windows 部署程式。</span><span class="sxs-lookup"><span data-stu-id="4593f-137">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="4593f-138">本文將討論這些程式。</span><span class="sxs-lookup"><span data-stu-id="4593f-138">These processes are discussed throughout this article.</span></span> <span data-ttu-id="4593f-139">如要進一商務用 Microsoft Store，請參閱[商務用 Microsoft Store](https://docs.microsoft.com/microsoft-store/)技術中心Windows></span><span class="sxs-lookup"><span data-stu-id="4593f-139">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <a name="add-surface-app-to-a-microsoft-store-for-business-account"></a><span data-ttu-id="4593f-140">將 Surface 應用程式新商務用 Microsoft Store帳戶</span><span class="sxs-lookup"><span data-stu-id="4593f-140">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="4593f-141">在使用者可以從公司的 商務用 Microsoft Store 帳戶安裝或部署應用程式之前，必須先提供 (應用程式) 並授權給企業使用者。</span><span class="sxs-lookup"><span data-stu-id="4593f-141">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="4593f-142">如果您尚未這麼做，請建立商務用 Microsoft Store[帳戶](https://www.microsoft.com/business-store)。</span><span class="sxs-lookup"><span data-stu-id="4593f-142">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="4593f-143">登入入口網站。</span><span class="sxs-lookup"><span data-stu-id="4593f-143">Log on to the portal.</span></span> 

3. <span data-ttu-id="4593f-144">啟用離線授權：按一下 **[管理>** 商店設定，然後選取 [向在市中購物的使用者顯示離線授權應用程式」 **核取方塊，** 如圖 1 所示。</span><span class="sxs-lookup"><span data-stu-id="4593f-144">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="4593f-145">有關應用程式授權商務用 Microsoft Store，請參閱應用程式與教育商務用 Microsoft Store[應用程式](https://docs.microsoft.com/microsoft-store/)。</span><span class="sxs-lookup"><span data-stu-id="4593f-145">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![顯示離線授權應用程式核取方塊](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="4593f-147">圖 1。</span><span class="sxs-lookup"><span data-stu-id="4593f-147">Figure 1.</span></span> <span data-ttu-id="4593f-148">啟用應用程式以離線使用</span><span class="sxs-lookup"><span data-stu-id="4593f-148">Enable apps for offline use</span></span>*

4. <span data-ttu-id="4593f-149">請遵循下列程式商務用 Microsoft Store Surface App 新增到您的帳戶：</span><span class="sxs-lookup"><span data-stu-id="4593f-149">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="4593f-150">按一下 [ **商店>** 功能表。</span><span class="sxs-lookup"><span data-stu-id="4593f-150">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="4593f-151">在搜尋方塊中，輸入 **Surface App**，然後按一下搜尋圖示。</span><span class="sxs-lookup"><span data-stu-id="4593f-151">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="4593f-152">在搜尋結果中顯示 Surface 應用程式之後，按一下應用程式的圖示。</span><span class="sxs-lookup"><span data-stu-id="4593f-152">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="4593f-153">系統會顯示一個選項， (線上或離線) ，如圖\*\*\*\* 2 所示。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="4593f-153">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![選取離線授權模式，並新增應用程式至您的庫存](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="4593f-155">圖 2.</span><span class="sxs-lookup"><span data-stu-id="4593f-155">Figure 2.</span></span> <span data-ttu-id="4593f-156">選取離線授權模式，並新增應用程式至您的庫存</span><span class="sxs-lookup"><span data-stu-id="4593f-156">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="4593f-157">按一下 **[離線** 以選取離線授權模式。</span><span class="sxs-lookup"><span data-stu-id="4593f-157">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="4593f-158">按一下 **[取得應用程式**以將應用程式新增到您的商務用 Microsoft Store庫存。</span><span class="sxs-lookup"><span data-stu-id="4593f-158">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="4593f-159">如圖 3 所示，您會看到一個對話方塊，提示您確認離線應用程式可以使用管理工具部署，或從公司私人商店的庫存頁面下載。</span><span class="sxs-lookup"><span data-stu-id="4593f-159">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="4593f-160">離線授權應用程式確認視窗 ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *圖 3。離線授權應用程式確認*</span><span class="sxs-lookup"><span data-stu-id="4593f-160">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="4593f-161">按一下**確定**。</span><span class="sxs-lookup"><span data-stu-id="4593f-161">Click **OK**.</span></span>

## <a name="download-surface-app-from-a-microsoft-store-for-business-account"></a><span data-ttu-id="4593f-162">從帳戶下載 Surface 應用程式商務用 Microsoft Store應用程式</span><span class="sxs-lookup"><span data-stu-id="4593f-162">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="4593f-163">在離線模式中將應用程式新商務用 Microsoft Store至帳戶後，您可以將應用程式下載並新增為 AppxBundle 至部署共用。</span><span class="sxs-lookup"><span data-stu-id="4593f-163">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="4593f-164">在 登入 商務用 Microsoft Store 帳戶 https://businessstore.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="4593f-164">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="4593f-165">按一下 **[管理->應用程式&軟體**。</span><span class="sxs-lookup"><span data-stu-id="4593f-165">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="4593f-166">系統會顯示您公司所有應用程式的清單，包括您于本文的新增 Surface 應用程式中新增到 商務用 Microsoft Store[帳戶區](#add-surface-app-to-a-microsoft-store-for-business-account)段的 Surface 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4593f-166">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="4593f-167">在 **[動作**> 下，按一下 [ (**...**) 省略號，然後按一下\*\*\*\*[下載以離線使用 Surface 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4593f-167">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="4593f-168">從所選**App** \*\*\*\* 的可用選項中選取所需的平臺和架構選項，如圖 4 所示。</span><span class="sxs-lookup"><span data-stu-id="4593f-168">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![AppxBundle 套件範例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="4593f-170">圖 4.</span><span class="sxs-lookup"><span data-stu-id="4593f-170">Figure 4.</span></span> <span data-ttu-id="4593f-171">下載 App 的 AppxBundle 套件</span><span class="sxs-lookup"><span data-stu-id="4593f-171">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="4593f-172">按一下 **[下載**。</span><span class="sxs-lookup"><span data-stu-id="4593f-172">Click **Download**.</span></span> <span data-ttu-id="4593f-173">AppxBundle 套件將會下載。</span><span class="sxs-lookup"><span data-stu-id="4593f-173">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="4593f-174">請確定您記下下載檔案的路徑，因為本文稍後會需要該路徑。</span><span class="sxs-lookup"><span data-stu-id="4593f-174">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="4593f-175">按一下 [**編碼授權或\*\*\*\*未編碼授權選項**。</span><span class="sxs-lookup"><span data-stu-id="4593f-175">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="4593f-176">使用編碼授權選項與管理工具 ，例如 Microsoft Endpoint Configuration Manager，或使用Windows設計工具來建立資源配置套件。</span><span class="sxs-lookup"><span data-stu-id="4593f-176">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="4593f-177">當您使用部署影像維護與管理 (DISM) 或部署解決方案時，請選取未編碼授權選項，包括 Microsoft 部署工具組 (MDT) 。</span><span class="sxs-lookup"><span data-stu-id="4593f-177">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="4593f-178">按一下 **[** 產生來產生並下載應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="4593f-178">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="4593f-179">請確定您記下授權檔案的路徑，因為本文稍後會需要該路徑。</span><span class="sxs-lookup"><span data-stu-id="4593f-179">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="4593f-180">當您下載離線使用的應用程式時 ，例如 Surface App，您可能會注意到頁面底部標示為必要的架構 **的區段**。</span><span class="sxs-lookup"><span data-stu-id="4593f-180">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="4593f-181">您的目的電腦必須安裝架構，才能執行應用程式，因此您可能需要針對架構 (x86 或 x64) 的每個必要的架構重複下載程式，並且將它們納入本文稍後討論的 Windows 部署中。</span><span class="sxs-lookup"><span data-stu-id="4593f-181">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="4593f-182">圖 5 顯示 Surface 應用程式所需的架構。</span><span class="sxs-lookup"><span data-stu-id="4593f-182">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface 應用程式所需的架構](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="4593f-184">圖 5.</span><span class="sxs-lookup"><span data-stu-id="4593f-184">Figure 5.</span></span> <span data-ttu-id="4593f-185">Surface 應用程式所需的架構</span><span class="sxs-lookup"><span data-stu-id="4593f-185">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="4593f-186">Surface App 的版本號碼和必要的架構會隨著應用程式更新而變更。</span><span class="sxs-lookup"><span data-stu-id="4593f-186">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="4593f-187">檢查最新版本的 Surface App，以及每個商務用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="4593f-187">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="4593f-188">請一直使用 Surface App 和由 商務用 Microsoft Store 提供的建議商務用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="4593f-188">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="4593f-189">使用過時的架構或不正確的版本可能會導致錯誤或應用程式當機。</span><span class="sxs-lookup"><span data-stu-id="4593f-189">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="4593f-190">若要下載 Surface 應用程式所需的架構，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="4593f-190">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="4593f-191">按一下 [**下載\*\*\*\*Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**。</span><span class="sxs-lookup"><span data-stu-id="4593f-191">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="4593f-192">這會下載 Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe。Appx 檔案至您指定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="4593f-192">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="4593f-193">按一下 [**下載\*\*\*\*Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**。</span><span class="sxs-lookup"><span data-stu-id="4593f-193">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="4593f-194">這會將 Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx 檔案下載到指定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="4593f-194">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="4593f-195">Surface 裝置只需要每個 (x64) 64 位 x64 版本。</span><span class="sxs-lookup"><span data-stu-id="4593f-195">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="4593f-196">Surface 裝置是原生的 64 位 UEFI 裝置，與需要 32 位架構的 32 位 (x86) Windows 版本不相容。</span><span class="sxs-lookup"><span data-stu-id="4593f-196">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <a name="install-surface-app-on-your-computer-with-powershell"></a><span data-ttu-id="4593f-197">使用 PowerShell 在您的電腦上安裝 Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="4593f-197">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="4593f-198">下列程式會將 Surface 應用程式規定至您的電腦，並可供之後在電腦上建立的任何使用者帳戶使用。</span><span class="sxs-lookup"><span data-stu-id="4593f-198">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="4593f-199">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span><span class="sxs-lookup"><span data-stu-id="4593f-199">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="4593f-200">開始已提升權限的 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="4593f-200">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="4593f-201">如果您沒有以系統管理員的名次執行 PowerShell，會話將沒有安裝應用程式所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="4593f-201">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="4593f-202">在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰</span><span class="sxs-lookup"><span data-stu-id="4593f-202">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="4593f-203">您 `<DownloadPath>` 從應用程式帳戶下載 AppxBundle 和授權檔案的資料夾商務用 Microsoft Store位置。</span><span class="sxs-lookup"><span data-stu-id="4593f-203">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="4593f-204">例如，如果您將檔案下載至 c：\Temp，您執行的命令為：</span><span class="sxs-lookup"><span data-stu-id="4593f-204">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="4593f-205">現在可在您目前的 Windows 電腦上使用 Surface app。</span><span class="sxs-lookup"><span data-stu-id="4593f-205">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="4593f-206">在 Surface App 在已置備的電腦上運作之前，您也必須提供本文前面所述之架構。</span><span class="sxs-lookup"><span data-stu-id="4593f-206">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="4593f-207">若要提供這些架構，請使用下列程式在升級的 PowerShell 會話中，您用來配置 Surface App。</span><span class="sxs-lookup"><span data-stu-id="4593f-207">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="4593f-208">在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰</span><span class="sxs-lookup"><span data-stu-id="4593f-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="4593f-209">在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰</span><span class="sxs-lookup"><span data-stu-id="4593f-209">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <a name="install-surface-app-with-mdt"></a><span data-ttu-id="4593f-210">使用 MDT 安裝 Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="4593f-210">Install Surface app with MDT</span></span>
<span data-ttu-id="4593f-211">下列程式使用 MDT 在部署時自動安裝 Surface App。</span><span class="sxs-lookup"><span data-stu-id="4593f-211">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="4593f-212">應用程式會由 MDT 在部署期間自動佈建，因此您可以利用這個程序搭配現有映像。</span><span class="sxs-lookup"><span data-stu-id="4593f-212">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="4593f-213">這是將 Surface 應用程式部署為 Windows 部署至 Surface 裝置的建議程式，因為它不會降低該影像Windows相容性。</span><span class="sxs-lookup"><span data-stu-id="4593f-213">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="4593f-214">使用本文 [前面所述的程式](#download-surface-app-from-a-microsoft-store-for-business-account)，下載 Surface App AppxBundle 和授權檔案。</span><span class="sxs-lookup"><span data-stu-id="4593f-214">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="4593f-215">使用 MDT Deployment Workbench 中的新應用程式精靈，將下載的檔案以新的應用程式與 **來源檔案一併輸入**。</span><span class="sxs-lookup"><span data-stu-id="4593f-215">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="4593f-216">在新增應用程式**精靈**的命令詳細資料頁面上，指定預設的**工作**目錄，而命令則指定\*\*\*\* AppxBundle 的檔案名，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4593f-216">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="4593f-217">命令：</span><span class="sxs-lookup"><span data-stu-id="4593f-217">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="4593f-218">工作目錄：%DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="4593f-218">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="4593f-219">若要讓 Surface App 在目的電腦上運作，也需要本文前面所述的架構。</span><span class="sxs-lookup"><span data-stu-id="4593f-219">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="4593f-220">使用下列程式將 Surface App 所需的架構導入 MDT，並設定為相依性。</span><span class="sxs-lookup"><span data-stu-id="4593f-220">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="4593f-221">使用本文前面所述的程式，下載框架檔案。</span><span class="sxs-lookup"><span data-stu-id="4593f-221">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="4593f-222">將每個框架儲存在個別資料夾中。</span><span class="sxs-lookup"><span data-stu-id="4593f-222">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="4593f-223">使用 MDT Deployment Workbench 中的新應用程式精靈，將下載的檔案以新的應用程式與 **來源檔案一併輸入**。</span><span class="sxs-lookup"><span data-stu-id="4593f-223">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="4593f-224">在命令**詳細資料**頁面上，輸入您于命令欄位中下載的每個應用程式的檔案名，以及預設的\*\*\*\* 工作目錄。</span><span class="sxs-lookup"><span data-stu-id="4593f-224">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="4593f-225">若要將架構設定為 Surface App 的相依性，請使用以下程式：</span><span class="sxs-lookup"><span data-stu-id="4593f-225">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="4593f-226">在 MDT 部署工作臺上開啟 Surface 應用程式的屬性。</span><span class="sxs-lookup"><span data-stu-id="4593f-226">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="4593f-227">按一下 [ **相依性>** 選項卡，然後按一下 [ **新增**。</span><span class="sxs-lookup"><span data-stu-id="4593f-227">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="4593f-228">使用您于新應用程式精靈中提供的名稱，選取每個架構的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4593f-228">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="4593f-229">在導入之後，Surface 應用程式可在部署精靈的 Windows\*\*\*\* 步驟中選取。</span><span class="sxs-lookup"><span data-stu-id="4593f-229">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="4593f-230">您也可以依照下列程序，在部署工作順序中指定應用程式來自動安裝應用程式：</span><span class="sxs-lookup"><span data-stu-id="4593f-230">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="4593f-231">在 MDT Deployment Workbench 中開啟部署工作順序。</span><span class="sxs-lookup"><span data-stu-id="4593f-231">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="4593f-232">在部署的 [State Restore]\*\*\*\* (狀態還原) 區段中新增新的 [Install Application]\*\*\*\* (安裝應用程式) 工作。</span><span class="sxs-lookup"><span data-stu-id="4593f-232">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="4593f-233">選取 **安裝單一應用程式，** 然後指定 **Surface App** **為要安裝的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="4593f-233">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="4593f-234">有關將應用程式納入您的部署Windows，請參閱使用 Microsoft 部署工具Windows 10[部署應用程式](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)。</span><span class="sxs-lookup"><span data-stu-id="4593f-234">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
