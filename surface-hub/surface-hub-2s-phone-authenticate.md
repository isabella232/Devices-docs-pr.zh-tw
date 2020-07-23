---
title: 在 Surface Hub 上設定密碼較少
description: 瞭解如何簡化登入 Surface Hub 的操作。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/21/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 0eaa48200be9ff3c8087530b6dfddeb9aa4620d8
ms.sourcegitcommit: 8738f44f2f4c86e3a45e9fbcbe6469388fc15924
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "10893045"
---
# <span data-ttu-id="fd877-104">設定 Surface Hub 上的 passwordless 登入</span><span class="sxs-lookup"><span data-stu-id="fd877-104">Configure passwordless sign-in on Surface Hub</span></span>

 
<span data-ttu-id="fd877-105">Passwordless 登入可簡化您的應用程式、會議及檔案的存取權。</span><span class="sxs-lookup"><span data-stu-id="fd877-105">Passwordless sign-in simplifies access to your apps, meetings, and files.</span></span> <span data-ttu-id="fd877-106">Surface Hub 支援使用 Microsoft 驗證器應用程式登入，並 FIDO2 貴組織提供的安全金鑰。</span><span class="sxs-lookup"><span data-stu-id="fd877-106">Surface Hub supports signing in using the Microsoft Authenticator app and FIDO2 security keys provided by your organization.</span></span>

<span data-ttu-id="fd877-107">**重要：** 此內容適用于使用者。</span><span class="sxs-lookup"><span data-stu-id="fd877-107">**Important:** This content is intended for users.</span></span> <span data-ttu-id="fd877-108">若要使用 passwordless 登入，您的 IT 系統管理員必須為貴組織啟用 passwordless 驗證。</span><span class="sxs-lookup"><span data-stu-id="fd877-108">To use passwordless sign-in, your IT admin must enable passwordless authentication for your organization.</span></span> <span data-ttu-id="fd877-109">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="fd877-109">For more information, see:</span></span>

- [<span data-ttu-id="fd877-110">啟用 passwordless 電話登入</span><span class="sxs-lookup"><span data-stu-id="fd877-110">Enable passwordless phone sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="fd877-111">啟用 passwordless 安全金鑰登入</span><span class="sxs-lookup"><span data-stu-id="fd877-111">Enable passwordless security key sign-in</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <span data-ttu-id="fd877-112">使用 Microsoft 驗證器應用程式設定登入</span><span class="sxs-lookup"><span data-stu-id="fd877-112">Configure sign-in using Microsoft Authenticator app</span></span>

<span data-ttu-id="fd877-113">**注意：** 從 Windows 10 Team 2020 更新開始，使用者可以在 Azure AD 中使用其慣用的電子郵件別名，以及其使用者主體名稱（UPN），以使用 Microsoft 驗證器登入。</span><span class="sxs-lookup"><span data-stu-id="fd877-113">**Note:** Starting with Windows 10 Team 2020 Update, users can use their preferred email aliases in Azure AD, as well as their User Principal Name (UPN), to sign in using Microsoft Authenticator.</span></span> <span data-ttu-id="fd877-114">例如，使用者可以使用其慣用的別名（John.Doe@contoso.com）或其 UPN （jdoe@contoso.com）登入。</span><span class="sxs-lookup"><span data-stu-id="fd877-114">For example, a user can use either their preferred alias (John.Doe@contoso.com) or their UPN (jdoe@contoso.com) to sign in.</span></span>
 
<span data-ttu-id="fd877-115">Microsoft 驗證器 app 可協助您使用行動裝置登入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="fd877-115">The Microsoft Authenticator app helps you sign-in to Surface Hub using your mobile device.</span></span> <span data-ttu-id="fd877-116">若要使用 Microsoft 驗證器設定登入：</span><span class="sxs-lookup"><span data-stu-id="fd877-116">To configure sign-in using Microsoft Authenticator:</span></span>


1. <span data-ttu-id="fd877-117">在您的行動裝置上，下載 Microsoft 驗證器 app。</span><span class="sxs-lookup"><span data-stu-id="fd877-117">On your mobile device, download the Microsoft Authenticator app.</span></span>
    - <span data-ttu-id="fd877-118">Google Android：在您的 Android 裝置上，移至 [Google Play]，[下載並安裝 Microsoft 驗證器應用程式](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)。</span><span class="sxs-lookup"><span data-stu-id="fd877-118">Google Android: On your Android device, go to Google Play to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator).</span></span>
    - <span data-ttu-id="fd877-119">Apple iOS：在您的 Apple iOS 裝置上，移至 [App Store][下載並安裝 Microsoft 驗證器應用程式](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)。</span><span class="sxs-lookup"><span data-stu-id="fd877-119">Apple iOS: On your Apple iOS device, go to the App Store to [download and install the Microsoft Authenticator app](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458).</span></span>
2. <span data-ttu-id="fd877-120">在您的電腦上，從您的公司或學校帳戶[的 [安全性資訊] 頁面設定 Microsoft 驗證器 app](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) 。</span><span class="sxs-lookup"><span data-stu-id="fd877-120">On your PC, [setup the Microsoft Authenticator app from the Security info page](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) for your work or school account.</span></span>
3. <span data-ttu-id="fd877-121">從您的行動裝置上的 Microsoft 驗證器 app，[開啟並使用手機](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account)或學校帳戶的電話登入。</span><span class="sxs-lookup"><span data-stu-id="fd877-121">From the Microsoft Authenticator app on your mobile device, [turn on and use phone sign-in](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account) for your work or school account.</span></span>

 
## <span data-ttu-id="fd877-122">使用 FIDO2 安全性金鑰設定登入</span><span class="sxs-lookup"><span data-stu-id="fd877-122">Configure sign-in using FIDO2 security keys</span></span>

> [!NOTE]
>  <span data-ttu-id="fd877-123">在 Surface Hub 上使用 FIDO2 安全參數 Passwordless 登入需要 Windows 10 Team 2020 更新。</span><span class="sxs-lookup"><span data-stu-id="fd877-123">Passwordless sign-in on Surface Hub using FIDO2 security keys requires the Windows 10 Team 2020 Update.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fd877-124">Surface Hub 只支援 USB 安全金鑰。</span><span class="sxs-lookup"><span data-stu-id="fd877-124">Surface Hub only supports USB security keys.</span></span>
 
<span data-ttu-id="fd877-125">您也可以使用貴組織提供的 FIDO2 安全金鑰登入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="fd877-125">You can also sign into Surface Hub using a FIDO2 security key provided by your organization.</span></span> 

### <span data-ttu-id="fd877-126">若要使用安全金鑰來設定登入：</span><span class="sxs-lookup"><span data-stu-id="fd877-126">To configure sign-in using a security key:</span></span>


1. <span data-ttu-id="fd877-127">在您的電腦上，移至您的 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 頁面並登入您的公司或學校帳戶。</span><span class="sxs-lookup"><span data-stu-id="fd877-127">On your PC, go to your [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) page and sign in to your work or school account.</span></span>
2. <span data-ttu-id="fd877-128">從左側流覽窗格或**安全性資訊**區塊中的連結選取 [**安全性資訊**]，然後從 [**安全性資訊**] 頁面選取 [**新增方法**]。</span><span class="sxs-lookup"><span data-stu-id="fd877-128">Select **Security info** from the left navigation pane or from the link in the **Security info** block, and then select **Add method** from the **Security info** page.</span></span>
3. <span data-ttu-id="fd877-129">在 [**新增方法**] 頁面上，從下拉式清單中選取 [**安全性金鑰**]，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="fd877-129">On the **Add a method** page, select **Security key** from the drop-down list, and then select **Add**.</span></span>
4. <span data-ttu-id="fd877-130">在 [**安全性金鑰**] 頁面上，選擇 [ **USB 裝置**]。</span><span class="sxs-lookup"><span data-stu-id="fd877-130">On the **Security key** page, choose **USB device**.</span></span>
5. <span data-ttu-id="fd877-131">準備好您的安全金鑰，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fd877-131">Have your security key ready and select **Next**.</span></span>
6. <span data-ttu-id="fd877-132">在出現的對話方塊中，按照指示插入安全參數、建立或輸入 PIN，然後執行所需的手勢（生物辨識或觸控）。</span><span class="sxs-lookup"><span data-stu-id="fd877-132">In the dialog box that appears, follow the instructions to insert the security key, create or enter a PIN, and perform the required gesture (either biometric or touch).</span></span>
7. <span data-ttu-id="fd877-133">在 [**安全性金鑰**] 頁面上，為您的安全性金鑰命名，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fd877-133">On the **Security key** page, give your security key a name, then select **Next**.</span></span>
8. <span data-ttu-id="fd877-134">選取 [**完成**] 以完成程式。</span><span class="sxs-lookup"><span data-stu-id="fd877-134">Select **Done** to complete the process.</span></span>

## <span data-ttu-id="fd877-135">登入 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="fd877-135">Sign-in to Surface Hub</span></span>

<span data-ttu-id="fd877-136">一旦您設定 passwordless 登入之後，您就可以使用它，讓您更輕鬆地在 Surface Hub 上存取您的應用程式、會議和檔案：</span><span class="sxs-lookup"><span data-stu-id="fd877-136">Once you've configured passwordless sign-in, you can use it to make it easier to access your apps, meetings, and files on the Surface Hub:</span></span>

- <span data-ttu-id="fd877-137">快速加入您的會議，並開啟最近的 Microsoft 365 檔案。</span><span class="sxs-lookup"><span data-stu-id="fd877-137">Quickly join your meetings and open recent Microsoft 365 files.</span></span> <span data-ttu-id="fd877-138">如需詳細資訊，請參閱登[**入以查看您的會議和**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)檔案。</span><span class="sxs-lookup"><span data-stu-id="fd877-138">For more information, see [**Sign in to see your meetings and files**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub).</span></span>
- <span data-ttu-id="fd877-139">快速登入 Microsoft 應用程式，例如白板、PowerPoint、Word、Excel、OneDrive 和 Power BI。</span><span class="sxs-lookup"><span data-stu-id="fd877-139">Quickly sign in to Microsoft apps like Whiteboard, PowerPoint, Word, Excel, OneDrive, and Power BI.</span></span>
- <span data-ttu-id="fd877-140">快速登入新的 Microsoft Edge，以存取您的 [我的最愛] 和 [流覽] 喜好設定。</span><span class="sxs-lookup"><span data-stu-id="fd877-140">Quickly sign in to the new Microsoft Edge to access your favorites and browsing preferences.</span></span> <span data-ttu-id="fd877-141">如需詳細資訊，請參閱[安裝及設定新的 Microsoft Edge](surface-hub-install-chromium-edge.md)。</span><span class="sxs-lookup"><span data-stu-id="fd877-141">For more information, see [Install and configure the new Microsoft Edge](surface-hub-install-chromium-edge.md).</span></span>
- <span data-ttu-id="fd877-142">登入 Surface Hub 之後，您就可以使用其他應用程式，而不需再次登入，直到您選取 [**結束會話**]。</span><span class="sxs-lookup"><span data-stu-id="fd877-142">Once you've signed into Surface Hub, you can use other apps without having to sign in again until you select **End session**.</span></span> <span data-ttu-id="fd877-143">選取 [**結束會話**] 會從裝置中刪除您的認證、檔案和個人資料。</span><span class="sxs-lookup"><span data-stu-id="fd877-143">Selecting **End session** deletes your credentials, files, and personal data from the device.</span></span> <span data-ttu-id="fd877-144">如需詳細資訊，請參閱[結束會話](finishing-your-surface-hub-meeting.md)。</span><span class="sxs-lookup"><span data-stu-id="fd877-144">For more information, see [End session](finishing-your-surface-hub-meeting.md).</span></span>


## <span data-ttu-id="fd877-145">深入了解</span><span class="sxs-lookup"><span data-stu-id="fd877-145">Learn more</span></span>

- [<span data-ttu-id="fd877-146">Azure Active Directory 的 Passwordless 驗證選項</span><span class="sxs-lookup"><span data-stu-id="fd877-146">Passwordless authentication options for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [<span data-ttu-id="fd877-147">使用 Microsoft 驗證器應用程式的 Passwordless 登入</span><span class="sxs-lookup"><span data-stu-id="fd877-147">Passwordless sign-in with the Microsoft Authenticator app</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [<span data-ttu-id="fd877-148">使用 FIDO2 安全金鑰 Passwordless 登入</span><span class="sxs-lookup"><span data-stu-id="fd877-148">Passwordless sign-in using FIDO2 security keys</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

