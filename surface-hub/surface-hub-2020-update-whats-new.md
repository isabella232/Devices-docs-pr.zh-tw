---
title: Windows 10 團隊版 2020 更新中的新功能
description: 查看 Surface Hub 作業系統 Windows 10 小組 2020 Update 最新更新的新增功能。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 96452885e19adc9784bb8d14be8ac6f2f86e883d
ms.sourcegitcommit: 6c362c5d5f67449f1adf4618847093eaf6ad087b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/22/2021
ms.locfileid: "11442867"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Windows 10 團隊版 2020 更新中的新功能

Windows 10 小組 2020 Update 為裝置部署和可管理性以及最新的 Windows 10 功能帶來重大改善。

##  <a name="deployment-and-manageability"></a>部署與可管理性

- **雲端裝置帳戶的新式驗證**。 Surface Hub 支援 Exchange Web Services (EWS) 和 Active Directory 驗證庫 (ADAL) 型驗證以連接到 Exchange，讓客戶可以取消使用基本驗證。 若要深入瞭解，請參閱 [Surface Hub 上的新式驗證](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)。
- **超過 20 個新的和更新**行動裝置管理 (MDM) 策略。      這些策略為 IT 系統管理員改善了對多種裝置設定的控制，包括：Microsoft Store 中的應用程式更新、無線投影設定 ，例如 Miracast 對基礎結構、網路設定 ，例如品質-服務與 802.1x 有線驗證，以及新的隱私權/GDPR 相關設定。 若要深入瞭解，請參閱： 
- [使用 Microsoft Intune 管理 Surface Hub。](surface-hub-2s-manage-intune.md)
- [Microsoft Surface Hub 支援的 CSPs 原則](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  <a name="azure-active-directory-joined-devices"></a>Azure Active Directory 已加入裝置

- **Azure AD (裝置) SSO 帳戶**上的單一登入。 當使用者使用他們的 Microsoft 365 認證以「我的會議和檔案」進行登錄時，他們的使用者認證會從應用程式順暢地在應用程式之間流暢地移動 ，包括瀏覽器中的 Microsoft 365 體驗。
- **Azure AD (的 CA) 條件式存取**。       IT 系統管理員可以將裝置層級安全性原則部署到其已加入 Azure AD 的 Surface Hub，以根據公司安全性和合規性需求控制組織資源的存取權。
- **支援 Azure AD 加入裝置的非全域系統管理員**。 客戶可以選擇其系統管理階層中的一組更精細的系統管理員來管理 Surface Hub。 若要深入瞭解，請參閱 [在 Surface Hub 上設定非全域系統管理員帳戶](surface-hub-2s-nonglobal-admin.md)。


## <a name="browser-and-pen"></a>瀏覽器和筆

- **支援新的 Microsoft Edge**。 Microsoft Edge 經過重建，以獲得最佳相容性、安全性和隱私權。 若要深入瞭解，請參閱在 Surface Hub 上安裝和設定 [新的 Microsoft Edge](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)。
- **Surface Hub 2S**上的雙筆書寫。   使用者可以使用兩支 Surface Hub 2 觸控筆在 Surface Hub 2S 上白板並排共同合作。 啟用雙筆書寫所需的固件更新會隨後續更新一起發行。

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams 預設安裝**。        Microsoft Teams 包含在新的 Surface Hub 裝置上的預設會議、通話和共同合作應用程式，這些裝置可透過 MDM 變更或設定，或直接在 Surface Hub 使用設定 App 進行設定。 若要深入瞭解，請參閱 [部署 Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)。
- **支援 Microsoft Teams 的鄰近加入**。  鄰近連接可讓使用者使用膝上型電腦/電話，在附近的 Surface Hub 進行排定的 Microsoft Teams 通話，或順暢地將進行中的會議轉換為附近的 Surface Hub。 Windows 10 小組 2020 Update 會新增行動裝置管理 (MDM) 以設定鄰近連接。 若要深入瞭解，請參閱： 

  - [Microsoft Teams 部落格](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。 
  - [在 Surface Hub 上管理 Microsoft Teams 設定](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **支援與 Microsoft Teams 協調會議**。 在配備 Surface Hub 和 Microsoft Teams 會議室裝置或具有兩個 Surface Hub 裝置的空間的會議室中，協調會議可讓使用者在 Microsoft Teams 會議期間輕鬆運用這兩個裝置。 使用者只需點一下，就可以從其中一個裝置加入會議，在一個裝置上顯示視音訊摘要，另一個裝置上顯示數位白板或內容，以最大化螢幕空間。 Windows 10 小組 2020 Update 新增行動裝置管理 (MDM) 支援，以設定協調會議，這項功能會隨著 Microsoft Teams 更新透過 Microsoft Store.To 進一步發佈，請參閱使用 Microsoft Teams 會議室和 [Surface Hub](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)設定協調會議。

## <a name="security"></a>安全性

- **使用 FIDO2 安全性金鑰進行無密碼登錄**     使用 FIDO2 安全性金鑰，客戶可以快速且輕鬆地登錄 Surface Hub，而不需要輸入使用者名稱和密碼。 此功能與單一Sign-On (SSO) 結合，在會議期間提供快速流暢的檔案、應用程式和網站的驗證。 若要深入瞭解，請參閱在 Surface Hub 上設定 [無密碼的登錄](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)。
- **使用 Microsoft Authenticator 進行無密碼登錄的改良功能**。  對於使用 Azure AD 的組織，使用者可以使用 Microsoft Authenticator 應用程式來登錄，而不需要輸入使用者名稱和密碼。 此外，除了使用者主體名稱或 UPN (之外，使用者可以在 Azure AD 中使用他們偏好的電子郵件別名) 。 若要深入瞭解，請參閱使用[Microsoft Authenticator 登錄 Surface Hub。](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)


## <a name="learn-more"></a>深入了解

- [Windows 10 團隊版的更新推出](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [安裝 Windows 10 團隊版 2020 更新](surface-hub-2020-update.md)  
 