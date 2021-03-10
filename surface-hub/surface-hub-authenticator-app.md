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
# <a name="sign-in-to-surface-hub-with-microsoft-authenticator"></a>使用 Microsoft Authenticator 登入 Surface Hub

在 Android 和 iOS 使用 Microsoft Authenticator 應用程式，您組織中的人員可以不使用密碼即登入 Surface Hub。

## <a name="organization-prerequisites"></a>組織必要條件

若想要讓您組織中的人員直接從他們的手機與其他裝置，而不用密碼登入 Surface Hub，請確定您的組織符合下列必要條件： 

- 您的組織必須是混合式或僅限雲端架構組織，由 Azure Active Directory (Azure AD) 提供支援。 如需詳細資訊，請參閱[什麼是 Azure Active Directory？](https://docs.microsoft.com/azure/active-directory/active-directory-whatis)

- 請確定您至少有 Office 365 E3 訂閱。 

- [設定多重要素驗證](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-mfasettings)。 請確定已選取 **\[透過行動裝置應用程式通知\]**。 

    ![多重要素驗證](images/mfa-options.png)

- 在 Azure AD 服務上啟用內容託管，例如 Office、SharePoint 等。 

- Surface Hub 必須執行 Windows 10，版本為 1703 或更新版本。

- 使用本機或加入網域的帳戶設定 Surface Hub。

## <a name="individual-prerequisites"></a>個人必要條件

- 執行 6.0 或更新版本的 Android 手機，或執行 iOS9 或更新版本的 iPhone 或 iPad 

- 在適當的應用程式市集的最新 Microsoft Authenticator 應用程式版本

    >[!NOTE]
    >在 iOS 上，應用程式版本必須是 5.4.0 或更新版本。
    >
    >手機上執行 Windows 作業系統的 Microsoft Authenticator 應用程式無法用來登入 Surface Hub。

- 已在您裝置上啟用密碼或螢幕鎖定功能

## <a name="how-to-set-up-the-microsoft-authenticator-app"></a>如何使用 Microsoft Authenticator 應用程式

>[!NOTE]
>如果已在 Android 裝置上安裝公司入口網站，請在設定 Microsoft Authenticator 之前先解除安裝。 設定應用程式之後，您可以重新安裝公司入口網站。
>
>如果您已經在手機上設定 Microsoft Authenticator，且已註冊您的裝置，請移至登入指示。

1. 新增您的公司或學校帳戶至 Microsoft Authenticator 以進行多重要素驗證。 您將需要您 IT 部門提供的 QR 代碼。 如需相關說明，請參閱[開始使用 Microsoft Authenticator 應用程式](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)。
2. 移至 **\[設定\]** 並註冊您的裝置。
3. 返回帳戶頁面，並從帳戶下拉式清單中選擇 **\[啟用以手機登入\]**。

## <a name="how-to-sign-in-to-surface-hub-during-a-meeting"></a>如何在會議期間登入 Surface Hub

1. 設定好會議之後，請移至 Surface Hub，然後選取 **\[登入以查看您的會議與檔案\]**。

    >[!NOTE]
    >如果您不確定如何在 Surface Hub 上為會議排程，請參閱[在 Surface Hub 上為會議排程](https://support.microsoft.com/help/17325/surfacehub-schedulemeeting)。

    ![Surface Hub 上登入選項的螢幕擷取畫面](images/sign-in.png)

2. 您會看到一份會議邀請人員名單。 選取您自己 (或想要登的入 – 請確定此人員在加入會議之前已完成所有裝置設定步驟)，然後選取 **\[繼續\]**。

    ![會議出席者名單的螢幕擷取畫面](images/attendees.png)

    您會在 Surface Hub 上看到程式碼。

    ![核准登入的程式碼螢幕擷取畫面](images/approve-signin.png)

3. 若要核准登入，請開啟 Authenticator 應用程式，輸入顯示在 Surface Hub 上的四位數代碼，並選取 **\[核准\]**。 系統將會要求您輸入 PIN 碼，或使用指紋來完成登入。 

    ![Microsoft Authenticator 中 [核准] 登入畫面的螢幕擷取畫面](images/approve-signin2.png)

您現在可以透過 OneDrive 應用程式存取所有檔案。
