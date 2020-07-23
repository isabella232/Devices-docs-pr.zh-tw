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
# 設定 Surface Hub 上的 passwordless 登入

 
Passwordless 登入可簡化您的應用程式、會議及檔案的存取權。 Surface Hub 支援使用 Microsoft 驗證器應用程式登入，並 FIDO2 貴組織提供的安全金鑰。

**重要：** 此內容適用于使用者。 若要使用 passwordless 登入，您的 IT 系統管理員必須為貴組織啟用 passwordless 驗證。 如需詳細資訊，請參閱：

- [啟用 passwordless 電話登入](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [啟用 passwordless 安全金鑰登入](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## 使用 Microsoft 驗證器應用程式設定登入

**注意：** 從 Windows 10 Team 2020 更新開始，使用者可以在 Azure AD 中使用其慣用的電子郵件別名，以及其使用者主體名稱（UPN），以使用 Microsoft 驗證器登入。 例如，使用者可以使用其慣用的別名（John.Doe@contoso.com）或其 UPN （jdoe@contoso.com）登入。
 
Microsoft 驗證器 app 可協助您使用行動裝置登入 Surface Hub。 若要使用 Microsoft 驗證器設定登入：


1. 在您的行動裝置上，下載 Microsoft 驗證器 app。
    - Google Android：在您的 Android 裝置上，移至 [Google Play]，[下載並安裝 Microsoft 驗證器應用程式](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)。
    - Apple iOS：在您的 Apple iOS 裝置上，移至 [App Store][下載並安裝 Microsoft 驗證器應用程式](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)。
2. 在您的電腦上，從您的公司或學校帳戶[的 [安全性資訊] 頁面設定 Microsoft 驗證器 app](https://docs.microsoft.com/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page) 。
3. 從您的行動裝置上的 Microsoft 驗證器 app，[開啟並使用手機](https://docs.microsoft.com/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account)或學校帳戶的電話登入。

 
## 使用 FIDO2 安全性金鑰設定登入

> [!NOTE]
>  在 Surface Hub 上使用 FIDO2 安全參數 Passwordless 登入需要 Windows 10 Team 2020 更新。

> [!IMPORTANT]
> Surface Hub 只支援 USB 安全金鑰。
 
您也可以使用貴組織提供的 FIDO2 安全金鑰登入 Surface Hub。 

### 若要使用安全金鑰來設定登入：


1. 在您的電腦上，移至您的 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 頁面並登入您的公司或學校帳戶。
2. 從左側流覽窗格或**安全性資訊**區塊中的連結選取 [**安全性資訊**]，然後從 [**安全性資訊**] 頁面選取 [**新增方法**]。
3. 在 [**新增方法**] 頁面上，從下拉式清單中選取 [**安全性金鑰**]，然後選取 [**新增**]。
4. 在 [**安全性金鑰**] 頁面上，選擇 [ **USB 裝置**]。
5. 準備好您的安全金鑰，然後選取 **[下一步]**。
6. 在出現的對話方塊中，按照指示插入安全參數、建立或輸入 PIN，然後執行所需的手勢（生物辨識或觸控）。
7. 在 [**安全性金鑰**] 頁面上，為您的安全性金鑰命名，然後選取 **[下一步]**。
8. 選取 [**完成**] 以完成程式。

## 登入 Surface Hub

一旦您設定 passwordless 登入之後，您就可以使用它，讓您更輕鬆地在 Surface Hub 上存取您的應用程式、會議和檔案：

- 快速加入您的會議，並開啟最近的 Microsoft 365 檔案。 如需詳細資訊，請參閱登[**入以查看您的會議和**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)檔案。
- 快速登入 Microsoft 應用程式，例如白板、PowerPoint、Word、Excel、OneDrive 和 Power BI。
- 快速登入新的 Microsoft Edge，以存取您的 [我的最愛] 和 [流覽] 喜好設定。 如需詳細資訊，請參閱[安裝及設定新的 Microsoft Edge](surface-hub-install-chromium-edge.md)。
- 登入 Surface Hub 之後，您就可以使用其他應用程式，而不需再次登入，直到您選取 [**結束會話**]。 選取 [**結束會話**] 會從裝置中刪除您的認證、檔案和個人資料。 如需詳細資訊，請參閱[結束會話](finishing-your-surface-hub-meeting.md)。


## 深入了解

- [Azure Active Directory 的 Passwordless 驗證選項](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless)
- [使用 Microsoft 驗證器應用程式的 Passwordless 登入](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [使用 FIDO2 安全金鑰 Passwordless 登入](https://docs.microsoft.com/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

