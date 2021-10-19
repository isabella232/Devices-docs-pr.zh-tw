---
title: 在 Surface Hub 上設定無密碼登入
description: 瞭解如何簡化登錄Surface Hub。
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
ms.openlocfilehash: 5449a3a168821c61b7c8969bfe445db91f357a2b
ms.sourcegitcommit: 4012a9499f658799197fedc7ea1a0c35d6127ed5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2021
ms.locfileid: "12101171"
---
# <a name="configure-passwordless-sign-in-on-surface-hub"></a>在 Surface Hub 上設定無密碼的登錄

 
無密碼登錄可簡化應用程式、會議和檔案的存取。 Surface Hub支援使用貴組織提供的 Microsoft Authenticator App 和 FIDO2 安全性金鑰來登錄。

**重要：** 此內容是供使用者使用。 若要使用無密碼登錄，您的 IT 系統管理員必須為貴組織啟用無密碼驗證。 如需詳細資訊，請參閱：

- [啟用無密碼電話登錄](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [啟用無密碼安全性金鑰登錄](/azure/active-directory/authentication/howto-authentication-passwordless-security-key)


## <a name="configure-sign-in-using-microsoft-authenticator-app"></a>使用應用程式設定Microsoft Authenticator登錄

**注意：** 從 Windows 10 團隊版 2020 Update 開始，使用者可以使用 Azure AD 中偏好的電子郵件別名，以及使用者主體名稱 (UPN) ，使用 Microsoft Authenticator。 例如，使用者可以使用他們偏好的別名 (John.Doe@contoso.com) 他們的 UPN (jdoe@contoso.com) 來登錄。
 
Microsoft Authenticator應用程式可協助您使用行動裝置Surface Hub帳戶。 若要使用帳戶設定Microsoft Authenticator：


1. 在行動裝置上，下載Microsoft Authenticator應用程式。
    - Google Android：在您的 Android 裝置上，前往 Google Play[下載並](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fplay.google.com%2Fstore%2Fapps%2Fdetails%3Fid%3Dcom.azure.authenticator)安裝Microsoft Authenticator應用程式。
    - Apple iOS：在您的 Apple iOS 裝置上，前往 App Store 下載並安裝 Microsoft Authenticator [App。](https://app.adjust.com/e3rxkc_7lfdtm?fallback=https%3A%2F%2Fitunes.apple.com%2Fus%2Fapp%2Fmicrosoft-authenticator%2Fid983156458)
2. 在您的電腦上，從Microsoft Authenticator或學校帳戶的安全性[資訊頁面設定](/azure/active-directory/user-help/security-info-setup-auth-app#set-up-the-microsoft-authenticator-app-from-the-security-info-page)應用程式。
3. 從Microsoft Authenticator裝置上的應用程式，開啟並使用公司或學校帳戶[](/azure/active-directory/user-help/user-help-auth-app-sign-in#turn-on-and-use-phone-sign-in-for-your-work-or-school-account)的電話登錄。

 
## <a name="configure-sign-in-using-fido2-security-keys"></a>使用 FIDO2 安全金鑰設定登錄

> [!NOTE]
>  使用 FIDO2 安全Surface Hub上的無密碼Windows 10 團隊版 2020 Update。

> [!IMPORTANT]
> Surface Hub僅支援 USB 安全金鑰。
 
您也可以使用貴Surface Hub提供的 FIDO2 安全性金鑰來登錄帳戶。 

### <a name="to-configure-sign-in-using-a-security-key"></a>若要使用安全金鑰設定登錄：


1. 在您的電腦上，請前往 [https://myprofile.microsoft.com/](https://myprofile.microsoft.com/) 您的頁面並登錄您的公司或學校帳戶。
2. 從**左側流覽**窗格或安全性資訊區塊中的連結選取安全性資訊，**** 然後從安全性**資訊**頁面選取新增**** 方法。
3. 在新增 **方法頁面上** ，從下拉式 **清單中** 選取安全性鍵， **然後選取新增**。
4. 在安全性 **金鑰** 頁面上，選擇 **USB 裝置**。
5. 準備好您的安全金鑰，然後選取下 **一步**。
6. 在出現的對話方塊中，按照指示插入安全性金鑰、建立或輸入 PIN，以及執行所需的手勢 (生物識別或觸控) 。
7. 在安全性 **金鑰** 頁面上，為安全性金鑰命名，然後選取下 **一步**。
8. 選取 **完成** 以完成程式。

## <a name="sign-in-to-surface-hub"></a>請Surface Hub

一旦已設好無密碼的登錄，就可以使用它，更輕鬆地存取應用程式、會議和檔案Surface Hub：

- 快速加入會議並開啟最近的Microsoft 365檔案。 詳細資訊，請參閱 [**登出以查看您的會議和檔案**](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)。
- 快速登錄 Microsoft 應用程式，例如 Whiteboard、PowerPoint、Word、Excel、OneDrive和 Power BI。
- 快速登錄新帳戶Microsoft Edge存取我的最愛和流覽喜好設定。 詳細資訊，請參閱[安裝並設定新的Microsoft Edge。](surface-hub-install-chromium-edge.md)
- 一旦已Surface Hub，就可以使用其他應用程式，而不需要再次登錄，直到您選取結束**會話。** 選取 **結束會話** 會從您的裝置中刪除您的認證、檔案和個人資料。 詳細資訊，請參閱 [結束會話](finishing-your-surface-hub-meeting.md)。


## <a name="learn-more"></a>深入了解

- [無密碼驗證選項Azure Active Directory](/azure/active-directory/authentication/concept-authentication-passwordless)
- [使用應用程式進行無密碼Microsoft Authenticator登錄](/azure/active-directory/authentication/howto-authentication-passwordless-phone)
- [使用 FIDO2 安全金鑰進行無密碼登錄](/azure/active-directory/authentication/howto-authentication-passwordless-security-key#user-registration-and-management-of-fido2-security-keys)

