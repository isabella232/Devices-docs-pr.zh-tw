---
title: 使用 Intune 將應用程式部署到 Surface Hub 2S
description: 瞭解您可以如何使用 Intune 將 app 部署到 Surface Hub 2。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831570"
---
# <span data-ttu-id="69b72-104">使用 Intune 將應用程式部署到 Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="69b72-104">Deploy apps to Surface Hub 2S using Intune</span></span>

<span data-ttu-id="69b72-105">您可以安裝其他 app 來符合您團隊或組織的需求。</span><span class="sxs-lookup"><span data-stu-id="69b72-105">You can install additional apps to fit your team or organization's needs.</span></span>

## <span data-ttu-id="69b72-106">開發人員指導方針</span><span class="sxs-lookup"><span data-stu-id="69b72-106">Developer guidelines</span></span>

- <span data-ttu-id="69b72-107">Surface Hub 僅能執行[通用 Windows 平台 (UWP) 應用程式](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)。</span><span class="sxs-lookup"><span data-stu-id="69b72-107">Surface Hub only runs [Universal Windows Platform (UWP) apps](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp).</span></span> <span data-ttu-id="69b72-108">使用 [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) 建立的應用程式將無法在 Surface Hub 上執行。</span><span class="sxs-lookup"><span data-stu-id="69b72-108">Apps created using the [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) will not run on Surface Hub.</span></span>
- <span data-ttu-id="69b72-109">應用程式必須以[通用裝置系列](https://msdn.microsoft.com/library/windows/apps/dn894631)或 Windows 小組裝置系列為目標。</span><span class="sxs-lookup"><span data-stu-id="69b72-109">Apps must be targeted for the [Universal device family](https://msdn.microsoft.com/library/windows/apps/dn894631) or Windows Team device family.</span></span>
- <span data-ttu-id="69b72-110">Surface Hub 只支援來自[Microsoft Store For Business](https://businessstore.microsoft.com/store)的[離線授權 app](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 。</span><span class="sxs-lookup"><span data-stu-id="69b72-110">Surface Hub only supports [offline-licensed apps](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) from [Microsoft Store for Business](https://businessstore.microsoft.com/store).</span></span>
- <span data-ttu-id="69b72-111">根據預設，應用程式必須經過市集簽署才能安裝。</span><span class="sxs-lookup"><span data-stu-id="69b72-111">By default, apps must be Store-signed to be installed.</span></span> <span data-ttu-id="69b72-112">在測試和開發期間，您也可以選擇將裝置切換到開發人員模式來執行開發人員簽署的 UWP app。</span><span class="sxs-lookup"><span data-stu-id="69b72-112">During testing and development, you can also choose to run developer-signed UWP apps by placing the device in developer mode.</span></span>
- <span data-ttu-id="69b72-113">在開發並提交應用程式至 Microsoft Store 時，請設定裝置系列可用性與組織授權選項，以確保 app 可在 Surface Hub 上執行。</span><span class="sxs-lookup"><span data-stu-id="69b72-113">When developing and submitting apps to the Microsoft Store, set Device family availability and Organizational licensing options to ensure that apps are available to run on Surface Hub.</span></span>
- <span data-ttu-id="69b72-114">您需要系統管理員認證，才能在 Surface Hub 上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="69b72-114">You need admin credentials to install apps on Surface Hub.</span></span> <span data-ttu-id="69b72-115">為在會議室和其他共用空間中使用而設計，Surface Hub 可防止一般使用者存取 Microsoft Store 來下載及安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="69b72-115">Designed for use in meeting rooms and other shared spaces, Surface Hub prevents regular users from accessing the Microsoft Store to download and install apps.</span></span>

## <span data-ttu-id="69b72-116">部署指導方針</span><span class="sxs-lookup"><span data-stu-id="69b72-116">Deployment guidelines</span></span>

<span data-ttu-id="69b72-117">您可以使用 Intune 將通用 Windows 平臺（UWP） app 部署至 Surface Hub 2-2，緩動 app 部署到裝置。</span><span class="sxs-lookup"><span data-stu-id="69b72-117">You can deploy Universal Windows Platform (UWP) apps to Surface Hub 2S using Intune, easing app deployment to devices.</span></span>

1. <span data-ttu-id="69b72-118">若要部署應用程式，請為您的組織啟用 MDM。</span><span class="sxs-lookup"><span data-stu-id="69b72-118">To deploy apps, enable MDM for your organization.</span></span> <span data-ttu-id="69b72-119">在 Intune 入口網站中，選取 [ **Intune** ] 做為您的 MDM 頒發機構（建議）。</span><span class="sxs-lookup"><span data-stu-id="69b72-119">In the Intune portal, select **Intune** as your MDM Authority (recommended).</span></span> <br>

    ![選擇 MDM 頒發機構](images/sh2-set-intune5.png)

2. <span data-ttu-id="69b72-121">在 Intune 中啟用商務用 Microsoft 網上商店。</span><span class="sxs-lookup"><span data-stu-id="69b72-121">Enable the Microsoft Store for Business in Intune.</span></span> <span data-ttu-id="69b72-122">開啟 Intune，選取 [**用戶端應用程式**  >  **Microsoft 網上商店]。**</span><span class="sxs-lookup"><span data-stu-id="69b72-122">Open Intune, select **Client apps** > **Microsoft Store for Business.**</span></span> <br>

    ![啟用商務用商店](images/sh2-deploy-apps-sync.png)

3. <span data-ttu-id="69b72-124">在 Intune 中開啟 [**商務用 Microsoft Store** ]，然後選取 [**設定**  >  **散佈**  >  **管理工具**]。</span><span class="sxs-lookup"><span data-stu-id="69b72-124">In Intune open **Microsoft Store for Business** and select **Settings** > **Distribute** > **Management tools**.</span></span> <span data-ttu-id="69b72-125">選擇 [ **Microsoft Intune** ] 做為您的管理工具。</span><span class="sxs-lookup"><span data-stu-id="69b72-125">Choose **Microsoft Intune** as your management tool.</span></span> <br>

    ![新增 Intune 作為您的管理工具](images/sh2-set-intune8.png)

4. <span data-ttu-id="69b72-127">在 [商務用 Microsoft 網上商店] 中，選取 [**設定**  >  **車間**  >  **購物經驗**]，然後選取 [**顯示離線應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="69b72-127">In Microsoft Store for Business, select **Settings** > **Shop** > **Shopping Experience**, and then select **Show offline apps**.</span></span> <span data-ttu-id="69b72-128">離線應用程式指的是可以同步處理到 Intune 並集中部署到裝置的 app。</span><span class="sxs-lookup"><span data-stu-id="69b72-128">Offline apps refer to apps that can be synced to Intune and centrally deployed to a device.</span></span>
5. <span data-ttu-id="69b72-129">啟用離線購物之後，您可以為可同步處理到 Intune 並部署為裝置授權的 app 取得離線授權。</span><span class="sxs-lookup"><span data-stu-id="69b72-129">After enabling Offline shopping, you can acquire offline licenses for apps that you can sync to Intune and deploy as Device licensing.</span></span>
6. <span data-ttu-id="69b72-130">在**Intune**  >  **用戶端 app**  >  **Microsoft Store for Business**中，選取 [**同步**處理]。</span><span class="sxs-lookup"><span data-stu-id="69b72-130">In **Intune** > **Client apps** > **Microsoft Store for Business**, select **Sync**.</span></span>
7. <span data-ttu-id="69b72-131">在 [用戶端應用程式] 頁面上，于 [應用程式] 清單中搜尋應用程式。</span><span class="sxs-lookup"><span data-stu-id="69b72-131">In the Client apps page, search for the app in the apps list.</span></span> <span data-ttu-id="69b72-132">將應用程式指派給想要的裝置群組或群組。</span><span class="sxs-lookup"><span data-stu-id="69b72-132">Assign the apps to the desired device group or groups.</span></span> <span data-ttu-id="69b72-133">選取 [**作業**  >  **新增] 群組**。</span><span class="sxs-lookup"><span data-stu-id="69b72-133">Select **Assignments** > **Add group**.</span></span> <br>

![\* 將 app 指派給群組 \*](images/sh2-assign-group.png) <br>

8. <span data-ttu-id="69b72-135">在 [作業類型] 底下，選擇 [**必要**]。</span><span class="sxs-lookup"><span data-stu-id="69b72-135">Under assignment type, choose **Required**.</span></span> <br>

![\* 將 app 指派給群組 \*](images/sh2-add-group.png) <br>

9. <span data-ttu-id="69b72-137">針對選取的群組，選擇 [**裝置授權**]，然後選取 **[確定]** 並儲存作業。</span><span class="sxs-lookup"><span data-stu-id="69b72-137">For the selected groups, choose **Device licensing** and then select **OK** and save the assignment.</span></span> <br>
 
![\* 將 app 指派給群組 \*](images/sh2-apps-assign.png)
