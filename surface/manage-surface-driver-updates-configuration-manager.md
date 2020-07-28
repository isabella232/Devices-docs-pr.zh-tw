---
title: 在 Configuration Manager 中管理 Surface 驅動程式更新
description: 本文將說明管理和部署 Surface 裝置的固件與驅動程式更新的可用選項。
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, update, device, manage, deploy, driver, USB, 韌體, 更新, 裝置, 管理, 部署, 驅動程式
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
ms.openlocfilehash: be32309b26ff6a873c36927cc39595022c4dbb90
ms.sourcegitcommit: ed4478dd3c6116a25b1e01a3a0f5ff6c1f940013
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/27/2020
ms.locfileid: "10897071"
---
# <span data-ttu-id="9a5b9-104">在 Configuration Manager 中管理 Surface 驅動程式更新</span><span class="sxs-lookup"><span data-stu-id="9a5b9-104">Manage Surface driver updates in Configuration Manager</span></span>

## <span data-ttu-id="9a5b9-105">摘要</span><span class="sxs-lookup"><span data-stu-id="9a5b9-105">Summary</span></span>

<span data-ttu-id="9a5b9-106">從[Microsoft System Center Configuration Manager 版本 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates)開始，您可以直接透過 Configuration Manager 用戶端同步處理和部署 Microsoft Surface 固件及驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-106">Starting in [Microsoft System Center Configuration Manager version 1710](https://docs.microsoft.com/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates), you can synchronize and deploy Microsoft Surface firmware and driver updates directly through the Configuration Manager client.</span></span> <span data-ttu-id="9a5b9-107">此程式類似于部署定期更新。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-107">The process resembles deploying regular updates.</span></span> <span data-ttu-id="9a5b9-108">不過，需要進行一些其他設定，才能讓 Surface 驅動程式更新到您的目錄中。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-108">However, some additional configurations are required to get the Surface driver updates into your catalog.</span></span>

## <span data-ttu-id="9a5b9-109">必要條件</span><span class="sxs-lookup"><span data-stu-id="9a5b9-109">Prerequisites</span></span>

<span data-ttu-id="9a5b9-110">若要管理 Surface driver 更新，必須符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-110">To manage Surface driver updates, the following prerequisites must be met:</span></span>

- <span data-ttu-id="9a5b9-111">您必須使用 Configuration Manager 版本1710或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-111">You must use Configuration Manager version 1710 or a later version.</span></span>
- <span data-ttu-id="9a5b9-112">所有軟體更新點（SUPs）都必須執行 Windows Server 2016 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-112">All Software Update Points (SUPs) must run Windows Server 2016 or a later version.</span></span> <span data-ttu-id="9a5b9-113">否則，Configuration Manager 會忽略此設定，且表面驅動程式將無法同步處理。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-113">Otherwise, Configuration Manager ignores this setting and Surface drivers won't be synchronized.</span></span>

> [!NOTE]
> <span data-ttu-id="9a5b9-114">如果您的環境不符合先決條件，請參閱 [[常見問題](#frequently-asked-questions-faq)] 區段中的[替代方法](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1)，以部署 Surface 驅動程式和固件更新。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-114">If your environment doesn’t meet the prerequisites, refer to the [alternative methods](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1) to deploy Surface driver and firmware updates in the [FAQ](#frequently-asked-questions-faq) section.</span></span>

## <span data-ttu-id="9a5b9-115">有用的記錄檔</span><span class="sxs-lookup"><span data-stu-id="9a5b9-115">Useful log files</span></span>

<span data-ttu-id="9a5b9-116">當您管理 Surface driver 更新時，下列記錄特別有用。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-116">The following logs are especially useful when you manage Surface driver updates.</span></span>

|<span data-ttu-id="9a5b9-117">記錄名稱</span><span class="sxs-lookup"><span data-stu-id="9a5b9-117">Log name</span></span>|<span data-ttu-id="9a5b9-118">描述</span><span class="sxs-lookup"><span data-stu-id="9a5b9-118">Description</span></span>|
|---|---|
|<span data-ttu-id="9a5b9-119">WCM. 記錄</span><span class="sxs-lookup"><span data-stu-id="9a5b9-119">WCM.log</span></span>|<span data-ttu-id="9a5b9-120">針對訂閱的更新類別、分類及語言，記錄軟體更新點設定和 WSUS 伺服器連線的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-120">Records details about the software update point configuration and connections to the WSUS server for subscribed update categories, classifications, and languages.</span></span>|
|<span data-ttu-id="9a5b9-121">WsyncMgr 記錄</span><span class="sxs-lookup"><span data-stu-id="9a5b9-121">WsyncMgr.log</span></span>|<span data-ttu-id="9a5b9-122">記錄軟體更新同步處理常式的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-122">Records details about the software updates sync process.</span></span>|

<span data-ttu-id="9a5b9-123">這些記錄位於管理 SUP 的網站伺服器或 SUP 本身（如果直接安裝在網站伺服器上的話）。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-123">These logs are located on the site server that manages the SUP, or on the SUP itself if it's installed directly on a site server.</span></span>
<span data-ttu-id="9a5b9-124">如需 Configuration Manager 記錄的完整清單，請參閱[System Center Configuration Manager 中的記錄](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files)檔案。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-124">For a complete list of Configuration Manager logs, see [Log files in System Center Configuration Manager](https://docs.microsoft.com/sccm/core/plan-design/hierarchy/log-files).</span></span>

## <span data-ttu-id="9a5b9-125">啟用 Surface driver 更新管理</span><span class="sxs-lookup"><span data-stu-id="9a5b9-125">Enabling Surface driver updates management</span></span>

<span data-ttu-id="9a5b9-126">若要在 Configuration Manager 中啟用 Surface driver 更新管理，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-126">To enable Surface driver updates management in Configuration Manager, follow these steps:</span></span>

1. <span data-ttu-id="9a5b9-127">在 Configuration Manager 主控台中，移至 [**管理**  >  **概覽**  >  **網站**設定  >  **網站**]。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-127">In the Configuration Manager console, go to **Administration** > **Overview** > **Site Configuration** > **Sites**.</span></span>
1. <span data-ttu-id="9a5b9-128">針對您的環境選取內含最上層 SUP 伺服器的網站。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-128">Select the site that contains the top-level SUP server for your environment.</span></span>
1. <span data-ttu-id="9a5b9-129">在功能區上，選取 [**設定網站元件**]，然後選取 [**軟體更新點**]。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-129">On the ribbon, select **Configure Site Components**, and then select **Software Update Point**.</span></span> <span data-ttu-id="9a5b9-130">或者，以滑鼠右鍵按一下網站，然後選取 [**設定網站元件**  >  **軟體更新點**]。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-130">Or, right-click the site, and then select **Configure Site Components** > **Software Update Point**.</span></span>
1. <span data-ttu-id="9a5b9-131">在 [**分類**] 索引標籤上，選取 [**包括 Microsoft Surface 驅動程式及固件更新**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-131">On the **Classifications** tab, select the **Include Microsoft Surface drivers and firmware updates** check box.</span></span>

   ![軟體更新點元件屬性](images/manage-surface-driver-updates-1.png)

1. <span data-ttu-id="9a5b9-133">當您收到下列警告訊息的提示時，請選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-133">When you're prompted by the following warning message, select **OK**.</span></span>

   ![Configuration Manager](images/manage-surface-driver-updates-2.png)

1. <span data-ttu-id="9a5b9-135">在 [產品] 索引標籤上，選取您要更新的產品，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-135">On the Products tab, select the products that you want to update, and then select **OK**.</span></span>

   <span data-ttu-id="9a5b9-136">大多數的驅動程式屬於下列產品群組：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-136">Most drivers belong to the following product groups:</span></span>

   - <span data-ttu-id="9a5b9-137">Windows 10 及更新版本驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-137">Windows 10 and later version drivers</span></span>
   - <span data-ttu-id="9a5b9-138">Windows 10 及更新版本的升級 & 服務驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-138">Windows 10 and later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="9a5b9-139">Windows 10 周年紀念更新及更新版本的驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-139">Windows 10 Anniversary Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="9a5b9-140">Windows 10 周年紀念更新及更新版本 & 服務驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-140">Windows 10 Anniversary Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="9a5b9-141">Windows 10 創意者更新及更新版本的驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-141">Windows 10 Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="9a5b9-142">Windows 10 創意者更新及更新版本 & 服務驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-142">Windows 10 Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="9a5b9-143">Windows 10 秋季製作者更新及更新版本的驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-143">Windows 10 Fall Creators Update and Later Servicing Drivers</span></span>
   - <span data-ttu-id="9a5b9-144">Windows 10 秋季創意更新及更新版本 & 服務驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-144">Windows 10 Fall Creators Update and Later Upgrade & Servicing Drivers</span></span>
   - <span data-ttu-id="9a5b9-145">Windows 10 S 及更新版本的服務驅動程式</span><span class="sxs-lookup"><span data-stu-id="9a5b9-145">Windows 10 S and Later Servicing Drivers</span></span>
   - <span data-ttu-id="9a5b9-146">Windows 10 S 版本1709及更新版本的服務驅動程式以進行測試</span><span class="sxs-lookup"><span data-stu-id="9a5b9-146">Windows 10 S Version 1709 and Later Servicing Drivers for testing</span></span>
   - <span data-ttu-id="9a5b9-147">Windows 10 S 版本1709及更新版本升級 & 服務驅動程式以進行測試</span><span class="sxs-lookup"><span data-stu-id="9a5b9-147">Windows 10 S Version 1709 and Later Upgrade & Servicing Drivers for testing</span></span>

   > [!NOTE]
   > <span data-ttu-id="9a5b9-148">大部分的表面驅動程式都屬於多個 Windows 10 產品群組。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-148">Most Surface drivers belong to multiple Windows 10 product groups.</span></span> <span data-ttu-id="9a5b9-149">您可能不需要選取此處所列的所有產品。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-149">You may not have to select all the products that are listed here.</span></span> <span data-ttu-id="9a5b9-150">為了協助您減少填入更新目錄的產品數，我們建議您只選取環境所需的產品進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-150">To help reduce the number of products that populate your Update Catalog, we recommend that you select only the products that are required by your environment for synchronization.</span></span>

## <span data-ttu-id="9a5b9-151">驗證配置</span><span class="sxs-lookup"><span data-stu-id="9a5b9-151">Verifying the configuration</span></span>

<span data-ttu-id="9a5b9-152">若要確認 SUP 設定正確無誤，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-152">To verify that the SUP is configured correctly, follow these steps:</span></span>

1. <span data-ttu-id="9a5b9-153">開啟 WsyncMgr，然後尋找下列專案：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-153">Open WsyncMgr.log, and then look for the following entry:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   <span data-ttu-id="9a5b9-154">如果下列其中一個專案記錄在 WsyncMgr 中，請重新檢查上一節中的步驟4：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-154">If either of the following entries is logged in WsyncMgr.log, recheck step 4 in the previous section:</span></span>

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. <span data-ttu-id="9a5b9-155">開啟 WCM .log，然後尋找類似下列的專案：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-155">Open WCM.log, and then look for an entry that resembles the following:</span></span>

   ![WCM. 記錄設定](images/manage-surface-driver-updates-3.png)

   <span data-ttu-id="9a5b9-157">此專案是 XML 元素，列出您的 SUP 伺服器目前同步處理的每個產品群組和分類。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-157">This entry is an XML element that lists every product group and classification that's currently synchronized by your SUP server.</span></span> <span data-ttu-id="9a5b9-158">例如，您可能會看到如下所示的專案：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-158">For example, you might see an entry that resembles the following:</span></span>

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   <span data-ttu-id="9a5b9-159">如果您在前一節的步驟6中找不到您所選取的產品，請仔細檢查是否已儲存 SUP 設定。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-159">If you can't find the products that you selected in step 6 in the previous section, double-check whether the SUP settings are saved.</span></span>

   <span data-ttu-id="9a5b9-160">您也可以等到下一個同步處理完成，然後檢查 [Configuration Manager] 主控台的 [軟體更新] 中是否列出 Surface 驅動程式和固件更新。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-160">You can also wait until the next synchronization finishes, and then check whether the Surface driver and firmware updates are listed in Software Updates in the Configuration Manager console.</span></span> <span data-ttu-id="9a5b9-161">例如，主控台可能會顯示下列資訊。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-161">For example, the console might display the following information.</span></span>

   ![所有軟體更新搜尋結果](images/manage-surface-driver-updates-4.png)

## <span data-ttu-id="9a5b9-163">手動同步處理</span><span class="sxs-lookup"><span data-stu-id="9a5b9-163">Manual synchronization</span></span>

<span data-ttu-id="9a5b9-164">如果您不想等到下一個同步處理，請依照下列步驟開始同步處理：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-164">If you don't want to wait until the next synchronization, follow these steps to start a synchronization:</span></span>

1. <span data-ttu-id="9a5b9-165">在 Configuration Manager 主控台中，移至**軟體庫**  >  **概述**  >  **軟體會更新**  >  **所有軟體更新**。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-165">In the Configuration Manager console, go to **Software Library** > **Overview** > **Software Updates** > **All Software Updates**.</span></span>
1. <span data-ttu-id="9a5b9-166">在功能區上，選取 [**同步處理軟體更新**]。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-166">On the ribbon, select **Synchronize Software Updates**.</span></span> <span data-ttu-id="9a5b9-167">或者，以滑鼠右鍵按一下**所有軟體更新**，然後選取 [**同步處理軟體更新**]。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-167">Or, right-click **All Software Update**, and then select **Synchronize Software Update**.</span></span>
1. <span data-ttu-id="9a5b9-168">在 WsyncMgr 中尋找下列專案來監視同步處理進度：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-168">Monitor the synchronization progress by looking for the following entries in WsyncMgr.log:</span></span>

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <span data-ttu-id="9a5b9-169">部署 Surface 固件與驅動程式更新</span><span class="sxs-lookup"><span data-stu-id="9a5b9-169">Deploying Surface firmware and driver updates</span></span>

<span data-ttu-id="9a5b9-170">您可以與部署其他更新一樣，部署 Surface 固件與驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-170">You can deploy Surface firmware and driver updates in the same manner as you deploy other updates.</span></span>

<span data-ttu-id="9a5b9-171">如需有關部署的詳細資訊，請參閱[System Center 2012 Configuration Manager – Part7：軟體更新（部署）](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/)。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-171">For more information about deployment, see [System Center 2012 Configuration Manager–Part7: Software Updates (Deploy)](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/).</span></span>

## <span data-ttu-id="9a5b9-172">常見問題 (FAQ)</span><span class="sxs-lookup"><span data-stu-id="9a5b9-172">Frequently asked questions (FAQ)</span></span>

**<span data-ttu-id="9a5b9-173">按照本文所述的步驟操作後，我的表面驅動程式仍不會同步處理。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-173">After I follow the steps in this article, my Surface drivers are still not synchronized.</span></span> <span data-ttu-id="9a5b9-174">為什麼？</span><span class="sxs-lookup"><span data-stu-id="9a5b9-174">Why?</span></span>**

<span data-ttu-id="9a5b9-175">如果您是從上游 Windows Server Update Services （WSUS）伺服器進行同步處理，而不是 Microsoft Update，請確定上游 WSUS 伺服器已設定為支援及同步處理 Surface 驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-175">If you synchronize from an upstream Windows Server Update Services (WSUS) server, instead of Microsoft Update, make sure that the upstream WSUS server is configured to support and synchronize Surface driver updates.</span></span> <span data-ttu-id="9a5b9-176">所有下游伺服器都限制在上游 WSUS 伺服器資料庫中存在的更新中。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-176">All downstream servers are limited to updates that are present in the upstream WSUS server database.</span></span>

<span data-ttu-id="9a5b9-177">在 WSUS 中，已分類為驅動程式的68000更新超過個。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-177">There are more than 68,000 updates that are classified as drivers in WSUS.</span></span> <span data-ttu-id="9a5b9-178">為了防止非 Surface 相關的驅動程式與 Configuration Manager 同步處理，Microsoft 會篩選出針對允許清單的驅動程式同步處理。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-178">To prevent non-Surface related drivers from synchronizing to Configuration Manager, Microsoft filters driver synchronization against an allow list.</span></span> <span data-ttu-id="9a5b9-179">在新的 [允許] 清單發佈並併入 Configuration Manager 之後，新的驅動程式會在下一次同步處理之後新增到主控台。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-179">After the new allow list is published and incorporated into Configuration Manager, the new drivers are added to the console following the next synchronization.</span></span> <span data-ttu-id="9a5b9-180">Microsoft 旨在讓 Surface 驅動程式與每月更新版本保持關聯，以讓其可供同步處理至 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-180">Microsoft aims to get the Surface drivers added to the allow list each month in alignment with monthly update releases to make them available for synchronization to Configuration Manager.</span></span>

<span data-ttu-id="9a5b9-181">如果您的 Configuration Manager 環境處於離線狀態，則每次匯入[服務更新](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool)到 Configuration Manager 時，都會匯入新的 [允許] 清單。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-181">If your Configuration Manager environment is offline, a new allow list is imported every time that you import [servicing updates](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to Configuration Manager.</span></span> <span data-ttu-id="9a5b9-182">您也必須先匯入包含驅動程式的[新 WSUS 目錄](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected)，然後才會在 Configuration Manager 主控台中顯示更新。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-182">You will also have to import a [new WSUS catalog](https://docs.microsoft.com/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) that contains the drivers before the updates are displayed in the Configuration Manager console.</span></span> <span data-ttu-id="9a5b9-183">由於獨立的 WSUS 環境所含的驅動程式多於 Configuration Manager SUP，因此我們建議您建立具有線上功能的 Configuration Manager 環境，並將它設定為同步處理 Surface 驅動程式。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-183">Because a standalone WSUS environment contains more drivers than a Configuration Manager SUP, we recommend that you establish a Configuration Manager environment that has online capabilities, and that you configure it to synchronize Surface drivers.</span></span> <span data-ttu-id="9a5b9-184">這提供較小的 WSUS 匯出，與離線環境非常相似。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-184">This provides a smaller WSUS export that closely resembles the offline environment.</span></span>

<span data-ttu-id="9a5b9-185">如果您的 Configuration Manager 環境是線上且能夠偵測到新的更新，您將會自動收到清單的更新。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-185">If your Configuration Manager environment is online and able to detect new updates, you will receive updates to the list automatically.</span></span> <span data-ttu-id="9a5b9-186">如果您沒有看到預期的驅動程式，請查看 WCM .log 及 WsyncMgr 檔案，以瞭解任何同步處理失敗的問題。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-186">If you don’t see the expected drivers, please review the WCM.log and WsyncMgr.log files for any synchronization failures.</span></span>

**<span data-ttu-id="9a5b9-187">我的 Configuration Manager 環境處於離線狀態。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-187">My Configuration Manager environment is offline.</span></span> <span data-ttu-id="9a5b9-188">我可以將 Surface 驅動程式手動匯入到 WSUS 嗎？</span><span class="sxs-lookup"><span data-stu-id="9a5b9-188">Can I manually import Surface drivers into WSUS?</span></span>**

<span data-ttu-id="9a5b9-189">不。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-189">No.</span></span> <span data-ttu-id="9a5b9-190">即使更新已匯入 WSUS，如果 [允許] 清單中未列出更新，就不會匯入 Configuration Manager 主控台進行部署。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-190">Even if the update is imported into WSUS, the update won't be imported into the Configuration Manager console for deployment if it isn't listed in the allow list.</span></span> <span data-ttu-id="9a5b9-191">您必須使用[服務連線工具](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool)，才能匯入 Configuration Manager 的服務更新，以更新 [允許] 清單。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-191">You must use the [Service Connection Tool](https://docs.microsoft.com/mem/configmgr/core/servers/manage/use-the-service-connection-tool) to import servicing updates to Configuration Manager to update the allow list.</span></span>

**<span data-ttu-id="9a5b9-192">我需要哪些替代方法才能部署 Surface 驅動程式和固件更新？</span><span class="sxs-lookup"><span data-stu-id="9a5b9-192">What alternative methods do I have to deploy Surface driver and firmware updates?</span></span>**

<span data-ttu-id="9a5b9-193">如需有關如何透過替代通道部署 Surface 驅動程式和固件更新的相關資訊，請參閱[管理 Surface 驅動程式和固件更新](manage-surface-driver-and-firmware-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-193">For information about how to deploy Surface driver and firmware updates through alternative channels, see [Manage Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span> <span data-ttu-id="9a5b9-194">如果您想要下載 .msi 或 .exe 檔案，然後透過傳統軟體部署通道進行部署，請參閱[使用 Configuration Manager 讓 Surface 固件保持更新](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager)。</span><span class="sxs-lookup"><span data-stu-id="9a5b9-194">If you want to download the .msi or .exe file, and then deploy through traditional software deployment channels, see [Keeping Surface Firmware Updated with Configuration Manager](https://docs.microsoft.com/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager).</span></span>

## <span data-ttu-id="9a5b9-195">其他資訊</span><span class="sxs-lookup"><span data-stu-id="9a5b9-195">Additional Information</span></span>

<span data-ttu-id="9a5b9-196">如需有關 Surface 驅動程式和固件更新的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="9a5b9-196">For more information about Surface driver and firmware updates, see the following articles:</span></span>

- [<span data-ttu-id="9a5b9-197">管理 Surface 的驅動程式和韌體更新</span><span class="sxs-lookup"><span data-stu-id="9a5b9-197">Manage Surface driver and firmware updates</span></span>](manage-surface-driver-and-firmware-updates.md)
- [<span data-ttu-id="9a5b9-198">Surface 和 System Center Configuration Manager 的考量</span><span class="sxs-lookup"><span data-stu-id="9a5b9-198">Considerations for Surface and System Center Configuration Manager</span></span>](considerations-for-surface-and-system-center-configuration-manager.md)
