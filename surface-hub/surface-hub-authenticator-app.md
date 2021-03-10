---
title: 使用 Microsoft Authenticator 登入 Surface Hub
description: 使用行動裝置上的 Microsoft Authenticator 登入 Surface Hub。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/28/2017
ms.reviewer: ''
manager: laurawi
localizationpriority: medium
ms.openlocfilehash: f8a2bf8ddb75ca6dd3ff89e16fe0d37e099be29d
ms.sourcegitcommit: 85f5a2e67b34fe073ec588ed441ebee239ab0ac6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "11400734"
---
# <a name="sign-in-to-surface-hub-with-microsoft-authenticator"></a><span data-ttu-id="12c1e-103">使用 Microsoft Authenticator 登入 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="12c1e-103">Sign in to Surface Hub with Microsoft Authenticator</span></span>

<span data-ttu-id="12c1e-104">在 Android 和 iOS 使用 Microsoft Authenticator 應用程式，您組織中的人員可以不使用密碼即登入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="12c1e-104">People in your organization can sign in to a Surface Hub  without a password using the Microsoft Authenticator app, available on Android and iOS.</span></span>

## <a name="organization-prerequisites"></a><span data-ttu-id="12c1e-105">組織必要條件</span><span class="sxs-lookup"><span data-stu-id="12c1e-105">Organization prerequisites</span></span>

<span data-ttu-id="12c1e-106">若想要讓您組織中的人員直接從他們的手機與其他裝置，而不用密碼登入 Surface Hub，請確定您的組織符合下列必要條件：</span><span class="sxs-lookup"><span data-stu-id="12c1e-106">To let people in your organization sign in to Surface Hub with their phones and other devices instead of a password, you’ll need to make sure that your organization meets these prerequisites:</span></span> 

- <span data-ttu-id="12c1e-107">您的組織必須是混合式或僅限雲端架構組織，由 Azure Active Directory (Azure AD) 提供支援。</span><span class="sxs-lookup"><span data-stu-id="12c1e-107">Your organization must be a hybrid or cloud-only organization, backed by Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="12c1e-108">如需詳細資訊，請參閱[什麼是 Azure Active Directory？](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span><span class="sxs-lookup"><span data-stu-id="12c1e-108">For more information, see [What is Azure Active Directory?](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)</span></span>

- <span data-ttu-id="12c1e-109">請確定您至少有 Office 365 E3 訂閱。</span><span class="sxs-lookup"><span data-stu-id="12c1e-109">Make sure you have at minimum an Office 365 E3 subscription.</span></span> 

- <span data-ttu-id="12c1e-110">[設定多重要素驗證](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings)。</span><span class="sxs-lookup"><span data-stu-id="12c1e-110">[Configure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings).</span></span> <span data-ttu-id="12c1e-111">請確定已選取 **\[透過行動裝置應用程式通知\]**。</span><span class="sxs-lookup"><span data-stu-id="12c1e-111">Make sure **Notification through mobile app** is selected.</span></span> 

    ![多重要素驗證](images/mfa-options.png)

- <span data-ttu-id="12c1e-113">在 Azure AD 服務上啟用內容託管，例如 Office、SharePoint 等。</span><span class="sxs-lookup"><span data-stu-id="12c1e-113">Enable content hosting on Azure AD services such as Office, SharePoint, etc.</span></span> 

- <span data-ttu-id="12c1e-114">Surface Hub 必須執行 Windows 10，版本為 1703 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="12c1e-114">Surface Hub must be running Windows 10, version 1703 or later.</span></span>

- <span data-ttu-id="12c1e-115">使用本機或加入網域的帳戶設定 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="12c1e-115">Surface Hub is set up with either a local or domain-joined account.</span></span>

## <a name="individual-prerequisites"></a><span data-ttu-id="12c1e-116">個人必要條件</span><span class="sxs-lookup"><span data-stu-id="12c1e-116">Individual prerequisites</span></span>

- <span data-ttu-id="12c1e-117">執行 6.0 或更新版本的 Android 手機，或執行 iOS9 或更新版本的 iPhone 或 iPad</span><span class="sxs-lookup"><span data-stu-id="12c1e-117">An Android phone running 6.0 or later, or an iPhone or iPad running iOS9 or later</span></span> 

- <span data-ttu-id="12c1e-118">在適當的應用程式市集的最新 Microsoft Authenticator 應用程式版本</span><span class="sxs-lookup"><span data-stu-id="12c1e-118">The most recent version of the Microsoft Authenticator app from the appropriate app store</span></span>

    >[!NOTE]
    ><span data-ttu-id="12c1e-119">在 iOS 上，應用程式版本必須是 5.4.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="12c1e-119">On iOS, the app version must be 5.4.0 or higher.</span></span>
    >
    ><span data-ttu-id="12c1e-120">手機上執行 Windows 作業系統的 Microsoft Authenticator 應用程式無法用來登入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="12c1e-120">The Microsoft Authenticator app on phones running a Windows operating system can't be used to sign in to Surface Hub.</span></span>

- <span data-ttu-id="12c1e-121">已在您裝置上啟用密碼或螢幕鎖定功能</span><span class="sxs-lookup"><span data-stu-id="12c1e-121">Passcode or screen lock on your device is enabled</span></span>

## <a name="how-to-set-up-the-microsoft-authenticator-app"></a><span data-ttu-id="12c1e-122">如何使用 Microsoft Authenticator 應用程式</span><span class="sxs-lookup"><span data-stu-id="12c1e-122">How to set up the Microsoft Authenticator app</span></span>

>[!NOTE]
><span data-ttu-id="12c1e-123">如果已在 Android 裝置上安裝公司入口網站，請在設定 Microsoft Authenticator 之前先解除安裝。</span><span class="sxs-lookup"><span data-stu-id="12c1e-123">If Company Portal is installed on your Android device, uninstall it before you set up Microsoft Authenticator.</span></span> <span data-ttu-id="12c1e-124">設定應用程式之後，您可以重新安裝公司入口網站。</span><span class="sxs-lookup"><span data-stu-id="12c1e-124">After you set up the app, you can reinstall Company Portal.</span></span>
>
><span data-ttu-id="12c1e-125">如果您已經在手機上設定 Microsoft Authenticator，且已註冊您的裝置，請移至登入指示。</span><span class="sxs-lookup"><span data-stu-id="12c1e-125">If you have already set up Microsoft Authenticator on your phone and registered your device, go to the sign-in instructions.</span></span>

1. <span data-ttu-id="12c1e-126">新增您的公司或學校帳戶至 Microsoft Authenticator 以進行多重要素驗證。</span><span class="sxs-lookup"><span data-stu-id="12c1e-126">Add your work or school account to Microsoft Authenticator for Multi-Factor Authentication.</span></span> <span data-ttu-id="12c1e-127">您將需要您 IT 部門提供的 QR 代碼。</span><span class="sxs-lookup"><span data-stu-id="12c1e-127">You will need a QR code provided by your IT department.</span></span> <span data-ttu-id="12c1e-128">如需相關說明，請參閱[開始使用 Microsoft Authenticator 應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。</span><span class="sxs-lookup"><span data-stu-id="12c1e-128">For help, see [Get started with the Microsoft Authenticator app](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to).</span></span>
2. <span data-ttu-id="12c1e-129">移至 **\[設定\]** 並註冊您的裝置。</span><span class="sxs-lookup"><span data-stu-id="12c1e-129">Go to **Settings** and register your device.</span></span>
3. <span data-ttu-id="12c1e-130">返回帳戶頁面，並從帳戶下拉式清單中選擇 **\[啟用以手機登入\]**。</span><span class="sxs-lookup"><span data-stu-id="12c1e-130">Return to the accounts page and choose **Enable phone sign-in** from the account dropdown menu.</span></span>

## <a name="how-to-sign-in-to-surface-hub-during-a-meeting"></a><span data-ttu-id="12c1e-131">如何在會議期間登入 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="12c1e-131">How to sign in to Surface Hub during a meeting</span></span>

1. <span data-ttu-id="12c1e-132">設定好會議之後，請移至 Surface Hub，然後選取 **\[登入以查看您的會議與檔案\]**。</span><span class="sxs-lookup"><span data-stu-id="12c1e-132">After you’ve set up a meeting, go to the Surface Hub and select **Sign in to see your meetings and files**.</span></span>

    >[!NOTE]
    ><span data-ttu-id="12c1e-133">如果您不確定如何在 Surface Hub 上為會議排程，請參閱[在 Surface Hub 上為會議排程](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting)。</span><span class="sxs-lookup"><span data-stu-id="12c1e-133">If you’re not sure how to schedule a meeting on a Surface Hub, see [Schedule a meeting on Surface Hub](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting).</span></span>

    ![Surface Hub 上登入選項的螢幕擷取畫面](images/sign-in.png)

2. <span data-ttu-id="12c1e-135">您會看到一份會議邀請人員名單。</span><span class="sxs-lookup"><span data-stu-id="12c1e-135">You’ll see a list of the people invited to the meeting.</span></span> <span data-ttu-id="12c1e-136">選取您自己 (或想要登的入 – 請確定此人員在加入會議之前已完成所有裝置設定步驟)，然後選取 **\[繼續\]**。</span><span class="sxs-lookup"><span data-stu-id="12c1e-136">Select yourself (or the person who wants to sign in – make sure this person has gone through the steps to set up their device before your meeting), and then select **Continue**.</span></span>

    ![會議出席者名單的螢幕擷取畫面](images/attendees.png)

    <span data-ttu-id="12c1e-138">您會在 Surface Hub 上看到程式碼。</span><span class="sxs-lookup"><span data-stu-id="12c1e-138">You'll see a code on the Surface Hub.</span></span>

    ![核准登入的程式碼螢幕擷取畫面](images/approve-signin.png)

3. <span data-ttu-id="12c1e-140">若要核准登入，請開啟 Authenticator 應用程式，輸入顯示在 Surface Hub 上的四位數代碼，並選取 **\[核准\]**。</span><span class="sxs-lookup"><span data-stu-id="12c1e-140">To approve the sign-in, open the Authenticator app, enter the four-digit code that’s displayed on the Surface Hub, and select **Approve**.</span></span> <span data-ttu-id="12c1e-141">系統將會要求您輸入 PIN 碼，或使用指紋來完成登入。</span><span class="sxs-lookup"><span data-stu-id="12c1e-141">You will then be asked to enter the PIN or use your fingerprint to complete the sign in.</span></span> 

    ![Microsoft Authenticator 中 [核准] 登入畫面的螢幕擷取畫面](images/approve-signin2.png)

<span data-ttu-id="12c1e-143">您現在可以透過 OneDrive 應用程式存取所有檔案。</span><span class="sxs-lookup"><span data-stu-id="12c1e-143">You can now access all files through the OneDrive app.</span></span>
