---
title: 使用 Microsoft Store for Business 或 Microsoft Store for 教育 (Surface) 部署 Surface app
description: 瞭解如何使用 Microsoft Store for Business 或 Microsoft Store for 教育，以及使用 PowerShell 和 MDT 安裝 Surface app 來新增和下載 Surface app。
keywords: surface app、app、部署、自訂
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
ms.date: 1/15/2021
ms.openlocfilehash: 87e24bcfa1e2d4ab05d24a05b203fea92637d3f4
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271070"
---
# <span data-ttu-id="227ff-104">使用 Microsoft Store for Business 和教育版部署 Surface app</span><span class="sxs-lookup"><span data-stu-id="227ff-104">Deploy Surface app with Microsoft Store for Business and Education</span></span>

**<span data-ttu-id="227ff-105">適用於</span><span class="sxs-lookup"><span data-stu-id="227ff-105">Applies to</span></span>**

- <span data-ttu-id="227ff-106">Surface Pro 7 +</span><span class="sxs-lookup"><span data-stu-id="227ff-106">Surface Pro 7+</span></span>
- <span data-ttu-id="227ff-107">Surface 膝上型電腦前往</span><span class="sxs-lookup"><span data-stu-id="227ff-107">Surface Laptop Go</span></span>
- <span data-ttu-id="227ff-108">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="227ff-108">Surface Pro 7</span></span>
- <span data-ttu-id="227ff-109">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="227ff-109">Surface Laptop 3</span></span>
- <span data-ttu-id="227ff-110">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="227ff-110">Surface Pro 6</span></span>
- <span data-ttu-id="227ff-111">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="227ff-111">Surface Laptop 2</span></span>
- <span data-ttu-id="227ff-112">Surface Go</span><span class="sxs-lookup"><span data-stu-id="227ff-112">Surface Go</span></span>
- <span data-ttu-id="227ff-113">使用 LTE 的 Surface</span><span class="sxs-lookup"><span data-stu-id="227ff-113">Surface Go with LTE</span></span>
- <span data-ttu-id="227ff-114">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="227ff-114">Surface Book 2</span></span>
- <span data-ttu-id="227ff-115">配備 LTE Advanced 的 Surface Pro (型號 1807)</span><span class="sxs-lookup"><span data-stu-id="227ff-115">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="227ff-116">Surface Pro (型號 1796)</span><span class="sxs-lookup"><span data-stu-id="227ff-116">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="227ff-117">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="227ff-117">Surface Laptop</span></span>
- <span data-ttu-id="227ff-118">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="227ff-118">Surface Studio</span></span>
- <span data-ttu-id="227ff-119">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="227ff-119">Surface Studio 2</span></span>
- <span data-ttu-id="227ff-120">Surface Book</span><span class="sxs-lookup"><span data-stu-id="227ff-120">Surface Book</span></span>
- <span data-ttu-id="227ff-121">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="227ff-121">Surface Pro 4</span></span>
- <span data-ttu-id="227ff-122">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="227ff-122">Surface 3 LTE</span></span>
- <span data-ttu-id="227ff-123">Surface 3</span><span class="sxs-lookup"><span data-stu-id="227ff-123">Surface 3</span></span>
- <span data-ttu-id="227ff-124">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="227ff-124">Surface Pro 3</span></span>


<span data-ttu-id="227ff-125">Surface app 是一個可讓您控制許多 Surface 特定設定和選項的輕型 Microsoft Store 應用程式，包括：</span><span class="sxs-lookup"><span data-stu-id="227ff-125">The Surface app is a lightweight Microsoft Store app that provides control of many Surface-specific settings and options, including:</span></span> 

* <span data-ttu-id="227ff-126">啟用或停用 Surface 裝置上的 Windows 鍵</span><span class="sxs-lookup"><span data-stu-id="227ff-126">Enable or disable the Windows button on the Surface device</span></span> 

* <span data-ttu-id="227ff-127">調整 Surface 手寫筆的敏感度</span><span class="sxs-lookup"><span data-stu-id="227ff-127">Adjust the sensitivity of a Surface Pen</span></span> 

* <span data-ttu-id="227ff-128">自訂 Surface 手寫筆按鈕動作</span><span class="sxs-lookup"><span data-stu-id="227ff-128">Customize Surface Pen button actions</span></span> 

* <span data-ttu-id="227ff-129">啟用或停用 Surface 音訊增強功能</span><span class="sxs-lookup"><span data-stu-id="227ff-129">Enable or disable Surface audio enhancements</span></span> 

* <span data-ttu-id="227ff-130">快速存取您裝置的支援檔與資訊</span><span class="sxs-lookup"><span data-stu-id="227ff-130">Quick access to support documentation and information for your device</span></span>

<span data-ttu-id="227ff-131">使用 Windows Update 的客戶通常會接收 Surface app 作為自動更新的一部分。</span><span class="sxs-lookup"><span data-stu-id="227ff-131">Customers using Windows Update will ordinarily receive Surface app as part of automatic updates.</span></span> <span data-ttu-id="227ff-132">但如果您的組織準備將影像部署至 Surface 裝置，您可能會想要在您的影像和部署程式中包含 surface 應用程式 (先前稱為 Surface Hub) ，而不需要每個人裝置的使用者從 Microsoft 網上商店或您的 Microsoft 網上商店下載並安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="227ff-132">But if your organization is preparing images for deployment to your Surface devices, you may want to include the Surface app (formerly called the Surface Hub) in your imaging and deployment process instead of requiring users of each individual device to download and install the app from the Microsoft Store or your Microsoft Store for Business.</span></span> 

> [!NOTE]
> <span data-ttu-id="227ff-133">本文不適用於 Surface Pro X。如需詳細資訊，請參閱 [部署、管理及維護 Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="227ff-133">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

## <span data-ttu-id="227ff-134">Surface app 概覽</span><span class="sxs-lookup"><span data-stu-id="227ff-134">Surface app overview</span></span>

<span data-ttu-id="227ff-135">您可以從 [Microsoft 網上商店](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)免費下載 Surface app。</span><span class="sxs-lookup"><span data-stu-id="227ff-135">The Surface app is available as a free download from the [Microsoft Store](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P).</span></span> <span data-ttu-id="227ff-136">使用者可以從 Microsoft 網上商店下載並安裝它，但如果您的組織使用的是商務用 Microsoft Store，您將需要將它新增到您的商店庫存，並可能包含 app 做為您的 Windows 部署程式。</span><span class="sxs-lookup"><span data-stu-id="227ff-136">Users can download and install it from the Microsoft Store, but if your organization uses Microsoft Store for Business instead, you will need to add it to your store’s inventory and possibly include the app as part of your Windows deployment process.</span></span> <span data-ttu-id="227ff-137">本文將討論這些程式。</span><span class="sxs-lookup"><span data-stu-id="227ff-137">These processes are discussed throughout this article.</span></span> <span data-ttu-id="227ff-138">如需 Microsoft 網上商店的詳細資訊，請參閱 Windows 技術中心的 [Microsoft 商務用商店](https://docs.microsoft.com/microsoft-store/) 。</span><span class="sxs-lookup"><span data-stu-id="227ff-138">For more information about Microsoft Store for Business, see [Microsoft Store for Business](https://docs.microsoft.com/microsoft-store/) in the Windows TechCenter.</span></span> 

## <span data-ttu-id="227ff-139">將 Surface 應用程式新增至 Microsoft Store for Business 帳戶</span><span class="sxs-lookup"><span data-stu-id="227ff-139">Add Surface app to a Microsoft Store for Business account</span></span> 

<span data-ttu-id="227ff-140">在使用者可以從公司的 Microsoft Store for Business 帳戶安裝或部署應用程式之前，必須先將所需的應用程式 (s) 提供給企業的使用者，然後授權給他們。</span><span class="sxs-lookup"><span data-stu-id="227ff-140">Before users can install or deploy an app from a company’s Microsoft Store for Business account, the desired app(s) must first be made available and licensed to the users of a business.</span></span> 

1. <span data-ttu-id="227ff-141">如果您尚未這麼做，請建立 [商務用 Microsoft Store 帳戶](https://www.microsoft.com/business-store)。</span><span class="sxs-lookup"><span data-stu-id="227ff-141">If you have not already done so, create a [Microsoft Store for Business account](https://www.microsoft.com/business-store).</span></span> 

2. <span data-ttu-id="227ff-142">登入入口網站。</span><span class="sxs-lookup"><span data-stu-id="227ff-142">Log on to the portal.</span></span> 

3. <span data-ttu-id="227ff-143">啟用離線授權：按一下 [ **管理]->[儲存設定**]，然後選取 [將 **離線授權的 app 顯示給在市集中購物的人員** ] 核取方塊，如圖1所示。</span><span class="sxs-lookup"><span data-stu-id="227ff-143">Enable offline licensing: click **Manage->Store settings**, and then select the **Show offline licensed apps to people shopping in the store** checkbox, as shown in Figure 1.</span></span> <span data-ttu-id="227ff-144">如需 Microsoft Store for Business 應用程式授權模型的詳細資訊，請參閱 [商務用 Microsoft store 中的 app 與教育](https://docs.microsoft.com/microsoft-store/)版。</span><span class="sxs-lookup"><span data-stu-id="227ff-144">For more information about Microsoft Store for Business app licensing models, see [Apps in Microsoft Store for Business and Education](https://docs.microsoft.com/microsoft-store/).</span></span>

   > [!div class="mx-imgBorder"]
   > ![[顯示離線授權應用程式] 核取方塊](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *<span data-ttu-id="227ff-146">圖 1。</span><span class="sxs-lookup"><span data-stu-id="227ff-146">Figure 1.</span></span> <span data-ttu-id="227ff-147">啟用 app 供離線使用</span><span class="sxs-lookup"><span data-stu-id="227ff-147">Enable apps for offline use</span></span>*

4. <span data-ttu-id="227ff-148">若要將 Surface app 新增至您的 Microsoft Store for Business 帳戶，請遵循此程式：</span><span class="sxs-lookup"><span data-stu-id="227ff-148">Add Surface app to your Microsoft Store for Business account by following this procedure:</span></span>

    * <span data-ttu-id="227ff-149">按一下 [ **車間** ] 功能表。</span><span class="sxs-lookup"><span data-stu-id="227ff-149">Click the **Shop** menu.</span></span>
    
    * <span data-ttu-id="227ff-150">在 [搜尋] 方塊中，輸入 [ **Surface app**]，然後按一下 [搜尋] 圖示。</span><span class="sxs-lookup"><span data-stu-id="227ff-150">In the search box, type **Surface app**, and then click the search icon.</span></span>
    
    * <span data-ttu-id="227ff-151">在搜尋結果中呈現 Surface 應用程式後，請按一下 app 的圖示。</span><span class="sxs-lookup"><span data-stu-id="227ff-151">After the Surface app is presented in the search results, click the app’s icon.</span></span>
    
    * <span data-ttu-id="227ff-152">您會看到一個選項 (選取 [ **線上** ] 或 [ **離線** ]) ，如圖2所示。</span><span class="sxs-lookup"><span data-stu-id="227ff-152">You are presented with a choice (select **Online** or **Offline**), as shown in Figure 2.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![選取離線授權模式，並將應用程式新增至您的庫存](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *<span data-ttu-id="227ff-154">圖 2.</span><span class="sxs-lookup"><span data-stu-id="227ff-154">Figure 2.</span></span> <span data-ttu-id="227ff-155">選取離線授權模式，並將應用程式新增至您的庫存</span><span class="sxs-lookup"><span data-stu-id="227ff-155">Select the Offline licensing mode and add the app to your inventory</span></span>*
    
    * <span data-ttu-id="227ff-156">按一下 [ **離線** ]，選取 [離線授權模式]。</span><span class="sxs-lookup"><span data-stu-id="227ff-156">Click **Offline** to select the Offline licensing mode.</span></span>
    
    * <span data-ttu-id="227ff-157">按一下 **[取得應用程式** ]，將 app 新增至您的商務用 Microsoft 市集中庫存。</span><span class="sxs-lookup"><span data-stu-id="227ff-157">Click **Get the app** to add the app to your Microsoft Store for Business inventory.</span></span> <span data-ttu-id="227ff-158">如圖3所示，您會看到一個對話方塊，提示您確認離線應用程式可以使用管理工具部署，或從其私人商店中的公司庫存頁面下載。</span><span class="sxs-lookup"><span data-stu-id="227ff-158">As shown in Figure 3, you’ll see a dialog box that prompts you to acknowledge that offline apps can be deployed using a management tool or downloaded from the company’s inventory page in their private store.</span></span>
    
      > [!div class="mx-imgBorder"]
      > ![<span data-ttu-id="227ff-159">離線授權的 app 確認視窗： ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *圖3。離線授權應用程式確認*</span><span class="sxs-lookup"><span data-stu-id="227ff-159">Offline-licensed app acknowledgement window](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
*Figure 3. Offline-licensed app acknowledgement*</span></span>
      
    * <span data-ttu-id="227ff-160">按一下**確定**。</span><span class="sxs-lookup"><span data-stu-id="227ff-160">Click **OK**.</span></span>

## <span data-ttu-id="227ff-161">從 Microsoft Store for Business 帳戶下載 Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="227ff-161">Download Surface app from a Microsoft Store for Business account</span></span>
<span data-ttu-id="227ff-162">在離線模式中，將 app 新增至商務用 Microsoft Store 帳戶之後，您就可以將 app 作為 .Appxbundle 下載並新增到部署共用中。</span><span class="sxs-lookup"><span data-stu-id="227ff-162">After you add an app to the Microsoft Store for Business account in Offline mode, you can download and add the app as an AppxBundle to a deployment share.</span></span>

1. <span data-ttu-id="227ff-163">登入 Microsoft 網上商店企業版帳戶 https://businessstore.microsoft.com 。</span><span class="sxs-lookup"><span data-stu-id="227ff-163">Log on to the Microsoft Store for Business account at https://businessstore.microsoft.com.</span></span>

2. <span data-ttu-id="227ff-164">按一下 [ **管理]->應用程式 & 軟體**。</span><span class="sxs-lookup"><span data-stu-id="227ff-164">Click **Manage->Apps & software**.</span></span> <span data-ttu-id="227ff-165">隨即會顯示您公司所有 app 的清單，包括您在 [新增 Surface 應用程式] 中新增的 Surface app 至本文的 [ [商務用 Microsoft Store 帳戶](#add-surface-app-to-a-microsoft-store-for-business-account) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="227ff-165">A list of all of your company’s apps is displayed, including the Surface app you added in the [Add Surface app to a Microsoft Store for Business account](#add-surface-app-to-a-microsoft-store-for-business-account) section of this article.</span></span>

3. <span data-ttu-id="227ff-166">在 [ **動作**] 底下，按一下省略號 (**...**) ，然後按一下 Surface app 的 [ **離線使用** ]。</span><span class="sxs-lookup"><span data-stu-id="227ff-166">Under **Actions**, click the ellipsis (**…**), and then click **Download for offline use** for the Surface app.</span></span>

4. <span data-ttu-id="227ff-167">從選取的應用程式可用的選項中，選取 [所需的 **平臺** 與 **體系結構** 選項]，如圖4所示。</span><span class="sxs-lookup"><span data-stu-id="227ff-167">Select the desired **Platform** and **Architecture** options from the available selections for the selected app, as shown in Figure 4.</span></span>

    > [!div class="mx-imgBorder"]
    > ![在 .Appxbundle 套件中的範例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *<span data-ttu-id="227ff-169">圖 4.</span><span class="sxs-lookup"><span data-stu-id="227ff-169">Figure 4.</span></span> <span data-ttu-id="227ff-170">下載應用程式的 .Appxbundle 套件</span><span class="sxs-lookup"><span data-stu-id="227ff-170">Download the AppxBundle package for an app</span></span>*
    
5. <span data-ttu-id="227ff-171">按一下 [ **下載**]。</span><span class="sxs-lookup"><span data-stu-id="227ff-171">Click **Download**.</span></span> <span data-ttu-id="227ff-172">將會下載 .Appxbundle 套件。</span><span class="sxs-lookup"><span data-stu-id="227ff-172">The AppxBundle package will be downloaded.</span></span> <span data-ttu-id="227ff-173">請確認您記下已下載檔案的路徑，因為您稍後會需要本文中的內容。</span><span class="sxs-lookup"><span data-stu-id="227ff-173">Make sure you note the path of the downloaded file because you’ll need that later in this article.</span></span>

6. <span data-ttu-id="227ff-174">按一下 [ **編碼授權** ] 或 [未 **編碼的授權** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="227ff-174">Click either the **Encoded license** or **Unencoded license** option.</span></span> <span data-ttu-id="227ff-175">使用 [編碼授權] 選項搭配 Microsoft 端點設定管理員之類的管理工具，或者當您使用 Windows 配置設計工具建立配套件時。</span><span class="sxs-lookup"><span data-stu-id="227ff-175">Use the Encoded license option with management tools like Microsoft Endpoint Configuration Manager or when you use Windows Configuration Designer to create a provisioning package.</span></span> <span data-ttu-id="227ff-176">如果您使用部署映射服務與管理 (DISM) 或以影像為基礎的部署解決方案（包括 Microsoft 部署工具套件 (MDT) ），請選取 [未加上授權] 選項。</span><span class="sxs-lookup"><span data-stu-id="227ff-176">Select the Unencoded license option when you use Deployment Image Servicing and Management (DISM) or deployment solutions based on imaging, including the Microsoft Deployment Toolkit (MDT).</span></span>

7. <span data-ttu-id="227ff-177">按一下 [ **產生** ]，以產生並下載 app 的授權。</span><span class="sxs-lookup"><span data-stu-id="227ff-177">Click **Generate** to generate and download the license for the app.</span></span> <span data-ttu-id="227ff-178">請確認您記下授權檔案的路徑，因為您稍後會需要本文中的內容。</span><span class="sxs-lookup"><span data-stu-id="227ff-178">Make sure you note the path of the license file because you’ll need that later in this article.</span></span>

>[!NOTE]
><span data-ttu-id="227ff-179">當您下載 app 供離線使用時（例如 Surface app），您可能會注意到頁面底部的 [ **必要的框架**] 中有一個區段。</span><span class="sxs-lookup"><span data-stu-id="227ff-179">When you download an app for offline use, such as the Surface app, you may notice a section at the bottom of the page labeled **Required frameworks**.</span></span> <span data-ttu-id="227ff-180">您的目的電腦必須已安裝應用程式的框架才能執行，因此您可能需要針對架構的每一個所需架構， (x86 或 x64) 中重複下載程式，也可以將它們包含在本文稍後討論的 Windows 部署中。</span><span class="sxs-lookup"><span data-stu-id="227ff-180">Your target computers must have the frameworks installed for the app to run, so you may need to repeat the download process for each of the required frameworks for your architecture (either x86 or x64) and also include them as part of your Windows deployment discussed later in this article.</span></span>

<span data-ttu-id="227ff-181">圖5顯示 Surface app 所需的框架。</span><span class="sxs-lookup"><span data-stu-id="227ff-181">Figure 5 shows the required frameworks for the Surface app.</span></span>

> [!div class="mx-imgBorder"]
> ![Surface app 所需的框架](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*<span data-ttu-id="227ff-183">圖 5.</span><span class="sxs-lookup"><span data-stu-id="227ff-183">Figure 5.</span></span> <span data-ttu-id="227ff-184">Surface app 所需的框架</span><span class="sxs-lookup"><span data-stu-id="227ff-184">Required frameworks for the Surface app</span></span>*

>[!NOTE]
><span data-ttu-id="227ff-185">Surface app 與必要框架的版本號碼會隨著 app 更新而變更。</span><span class="sxs-lookup"><span data-stu-id="227ff-185">The version numbers of the Surface app and required frameworks will change as the apps are updated.</span></span> <span data-ttu-id="227ff-186">在 Microsoft Store for Business 中查看最新版本的 Surface 應用程式和每個架構。</span><span class="sxs-lookup"><span data-stu-id="227ff-186">Check for the latest version of Surface app and each framework in Microsoft Store for Business.</span></span> <span data-ttu-id="227ff-187">使用 Microsoft Store for Business 所提供的 Surface app 和建議架構版本。</span><span class="sxs-lookup"><span data-stu-id="227ff-187">Always use the Surface app and recommended framework versions as provided by Microsoft Store for Business.</span></span> <span data-ttu-id="227ff-188">使用過時的框架或不正確的版本，可能會導致錯誤或應用程式當機。</span><span class="sxs-lookup"><span data-stu-id="227ff-188">Using outdated frameworks or the incorrect versions may result in errors or application crashes.</span></span>

<span data-ttu-id="227ff-189">若要下載 Surface app 所需的架構，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="227ff-189">To download the required frameworks for the Surface app, follow these steps:</span></span>

1. <span data-ttu-id="227ff-190">按一下 [VCLibs] 底下的 [ **下載** ] 按鈕 **140.00 _14. 0 23816 _x64__8wekyb3d8bbwe**。</span><span class="sxs-lookup"><span data-stu-id="227ff-190">Click the **Download** button under **Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="227ff-191">這會下載 VCLibs 140.00 _14. 0 23816 _x64__8wekyb3d8bbwe。Appx 檔案移至您指定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="227ff-191">This downloads the Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

2. <span data-ttu-id="227ff-192">按一下 [23406] 底下的 [ **下載** ] 按鈕 **1.1 版. 1. 0 _x64__8wekyb3d8bbwe**。</span><span class="sxs-lookup"><span data-stu-id="227ff-192">Click the **Download** button under **Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe**.</span></span> <span data-ttu-id="227ff-193">這會將 23406 _x64__8wekyb3d8bbwe .Appx 檔案下載到您指定的資料夾中（& 1.）。</span><span class="sxs-lookup"><span data-stu-id="227ff-193">This downloads the Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx file to your specified folder.</span></span>

>[!NOTE]
><span data-ttu-id="227ff-194">在 Surface 裝置上，只需要每個架構的64位 (x64) 版本。</span><span class="sxs-lookup"><span data-stu-id="227ff-194">Only the 64-bit (x64) version of each framework is required for Surface devices.</span></span> <span data-ttu-id="227ff-195">Surface 裝置是原生64位 UEFI 裝置，且與32位 (x86) 版本的 Windows （需要32位架構）不相容。</span><span class="sxs-lookup"><span data-stu-id="227ff-195">Surface devices are native 64-bit UEFI devices and are not compatible with 32-bit (x86) versions of Windows that would require 32-bit frameworks.</span></span> 

## <span data-ttu-id="227ff-196">使用 PowerShell 在您的電腦上安裝 Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="227ff-196">Install Surface app on your computer with PowerShell</span></span>
<span data-ttu-id="227ff-197">下列程式會將 Surface 應用程式置備到您的電腦，並將它提供給電腦之後所建立的任何使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="227ff-197">The following procedure provisions the Surface app onto your computer and makes it available for any user accounts created on the computer afterwards.</span></span>

1. <span data-ttu-id="227ff-198">若要使用本文所述的 [ [如何從 Microsoft Store For Business 帳戶下載 surface app](#download-surface-app-from-a-microsoft-store-for-business-account) ] 區段所述的程式，請下載 Surface app .appxbundle 和授權檔案。</span><span class="sxs-lookup"><span data-stu-id="227ff-198">Using the procedure described in the [How to download Surface app from a Microsoft Store for Business account](#download-surface-app-from-a-microsoft-store-for-business-account) section of this article, download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="227ff-199">開始已提升權限的 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="227ff-199">Begin an elevated PowerShell session.</span></span>

    >[!NOTE]
    ><span data-ttu-id="227ff-200">如果您不是以系統管理員身分執行 PowerShell，會話就不會有安裝 app 所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="227ff-200">If you don’t run PowerShell as an Administrator, the session won’t have the required permissions to install the app.</span></span>
    
3. <span data-ttu-id="227ff-201">在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰</span><span class="sxs-lookup"><span data-stu-id="227ff-201">In the elevated PowerShell session, copy and paste the following command:</span></span>

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    <span data-ttu-id="227ff-202">其中 `<DownloadPath>` 是您從 Microsoft Store For Business 帳戶下載 .appxbundle 和授權檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="227ff-202">Where `<DownloadPath>` is the folder where you downloaded the AppxBundle and license file from the Microsoft Store for Business account.</span></span>

    <span data-ttu-id="227ff-203">例如，如果您將檔案下載到 C：\Temp，您執行的命令就是：</span><span class="sxs-lookup"><span data-stu-id="227ff-203">For example, if you downloaded the files to c:\Temp, the command you run is:</span></span>
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. <span data-ttu-id="227ff-204">現在可在您目前的 Windows 電腦上使用 Surface app。</span><span class="sxs-lookup"><span data-stu-id="227ff-204">The Surface app will now be available on your current Windows computer.</span></span> 

   <span data-ttu-id="227ff-205">您也必須先提供本文先前所述的架構，才能讓 Surface app 在已設定的電腦上正常運作。</span><span class="sxs-lookup"><span data-stu-id="227ff-205">Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article.</span></span> <span data-ttu-id="227ff-206">若要設定這些架構，請在您用來置備 Surface 應用程式的提升 PowerShell 會話中使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="227ff-206">To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.</span></span>

5. <span data-ttu-id="227ff-207">在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰</span><span class="sxs-lookup"><span data-stu-id="227ff-207">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. <span data-ttu-id="227ff-208">在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰</span><span class="sxs-lookup"><span data-stu-id="227ff-208">In the elevated PowerShell session, copy and paste the following command:</span></span>

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## <span data-ttu-id="227ff-209">使用 MDT 安裝 Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="227ff-209">Install Surface app with MDT</span></span>
<span data-ttu-id="227ff-210">下列程式會使用 MDT，在部署時自動安裝 Surface app。</span><span class="sxs-lookup"><span data-stu-id="227ff-210">The following procedure uses MDT to automate installation of the Surface app at the time of deployment.</span></span> <span data-ttu-id="227ff-211">應用程式會由 MDT 在部署期間自動佈建，因此您可以利用這個程序搭配現有映像。</span><span class="sxs-lookup"><span data-stu-id="227ff-211">The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images.</span></span> <span data-ttu-id="227ff-212">此程式是將 Surface app 部署為 Windows 部署至 Surface 裝置的建議程式，因為它不會降低 Windows 影像的跨平臺相容性。</span><span class="sxs-lookup"><span data-stu-id="227ff-212">This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.</span></span>

1. <span data-ttu-id="227ff-213">使用 [本文先前](#download-surface-app-from-a-microsoft-store-for-business-account)所述的程式，下載 Surface app .appxbundle 和授權檔案。</span><span class="sxs-lookup"><span data-stu-id="227ff-213">Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file.</span></span> 

2. <span data-ttu-id="227ff-214">使用 MDT 部署工作臺中的 [新增應用程式] 嚮導，將下載的檔案匯入為含有來源檔案的新 **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="227ff-214">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="227ff-215">在 [新增應用程式] 嚮導的 [ **命令詳細資料** ] 頁面上，指定預設的 **工作目錄** ，然後針對 **命令** 指定您的 .appxbundle 檔案名，如下所示：</span><span class="sxs-lookup"><span data-stu-id="227ff-215">On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:</span></span>

   * <span data-ttu-id="227ff-216">命令</span><span class="sxs-lookup"><span data-stu-id="227ff-216">Command:</span></span>
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * <span data-ttu-id="227ff-217">工作目錄：%DEPLOYROOT%\Applications\SurfaceApp</span><span class="sxs-lookup"><span data-stu-id="227ff-217">Working Directory: %DEPLOYROOT%\Applications\SurfaceApp</span></span>

<span data-ttu-id="227ff-218">為了讓 Surface 應用程式在目的電腦上正常運作，您也需要本文前面所述的框架。</span><span class="sxs-lookup"><span data-stu-id="227ff-218">For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article.</span></span> <span data-ttu-id="227ff-219">使用下列程式將 Surface app 所需的框架匯入到 MDT，並將其設定為相依性。</span><span class="sxs-lookup"><span data-stu-id="227ff-219">Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.</span></span>

1. <span data-ttu-id="227ff-220">使用本文先前所述的程式下載架構檔案。</span><span class="sxs-lookup"><span data-stu-id="227ff-220">Using the procedure described earlier in this article, download the framework files.</span></span> <span data-ttu-id="227ff-221">將每個架構儲存在另一個資料夾中。</span><span class="sxs-lookup"><span data-stu-id="227ff-221">Store each framework in a separate folder.</span></span>

2. <span data-ttu-id="227ff-222">使用 MDT 部署工作臺中的 [新增應用程式] 嚮導，將下載的檔案匯入為含有來源檔案的新 **應用程式**。</span><span class="sxs-lookup"><span data-stu-id="227ff-222">Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.</span></span>

3. <span data-ttu-id="227ff-223">在 [ **命令詳細資料** ] 頁面上，輸入您在 **命令** 欄位中下載的每個應用程式的檔案名和預設的工作目錄。</span><span class="sxs-lookup"><span data-stu-id="227ff-223">On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.</span></span>

<span data-ttu-id="227ff-224">若要將框架設定為 Surface app 的相依性，請使用此程式：</span><span class="sxs-lookup"><span data-stu-id="227ff-224">To configure the frameworks as dependencies of the Surface app, use this process:</span></span>

1. <span data-ttu-id="227ff-225">在 MDT 部署工作臺中開啟 Surface 應用程式的屬性。</span><span class="sxs-lookup"><span data-stu-id="227ff-225">Open the properties of the Surface app in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="227ff-226">按一下 [ **依賴性** ] 索引標籤，然後按一下 [ **新增**]。</span><span class="sxs-lookup"><span data-stu-id="227ff-226">Click the **Dependencies** tab, and then click **Add**.</span></span>

3. <span data-ttu-id="227ff-227">使用您在新的應用程式精靈中所提供的名稱，選取每個架構的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="227ff-227">Select the check box for each framework using the name you provided in the New Application Wizard.</span></span>

<span data-ttu-id="227ff-228">匯入之後，就可以在 Windows 部署嚮導的 [ **應用程式** ] 步驟中選取 Surface app。</span><span class="sxs-lookup"><span data-stu-id="227ff-228">After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard.</span></span> <span data-ttu-id="227ff-229">您也可以依照下列程序，在部署工作順序中指定應用程式來自動安裝應用程式：</span><span class="sxs-lookup"><span data-stu-id="227ff-229">You can also install the application automatically by specifying the application in the deployment task sequence by following this process:</span></span>

1. <span data-ttu-id="227ff-230">在 MDT Deployment Workbench 中開啟部署工作順序。</span><span class="sxs-lookup"><span data-stu-id="227ff-230">Open your deployment task sequence in the MDT Deployment Workbench.</span></span>

2. <span data-ttu-id="227ff-231">在部署的 [State Restore]\*\*\*\* (狀態還原) 區段中新增新的 [Install Application]\*\*\*\* (安裝應用程式) 工作。</span><span class="sxs-lookup"><span data-stu-id="227ff-231">Add a new **Install Application** task in the **State Restore** section of deployment.</span></span>

3. <span data-ttu-id="227ff-232">選取 [ **安裝單一應用程式** ]，然後指定 **Surface App** 作為 **要安裝的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="227ff-232">Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.</span></span>

<span data-ttu-id="227ff-233">如需將 app 納入 Windows 部署的詳細資訊，請參閱 [使用 Microsoft 部署工具組部署 Windows 10](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)。</span><span class="sxs-lookup"><span data-stu-id="227ff-233">For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).</span></span>
