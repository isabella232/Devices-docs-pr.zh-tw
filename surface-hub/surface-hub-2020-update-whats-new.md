---
title: Windows 10 團隊版 2020 更新中的新功能
description: 查看 2020 更新等作業系統Surface Hub更新Windows 10 團隊版新增功能。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 753f0b64eb05e6d18d0ec2e32af8e0566a8c50b5
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676637"
---
# <a name="whats-new-in-windows-10-team-2020-update"></a>Windows 10 團隊版 2020 更新中的新功能

Windows 10 團隊版 2020 Update 為裝置部署和可管理性帶來重大改善，以及最新的Windows 10功能。

##  <a name="deployment-and-manageability"></a>部署與可管理性

- **雲端裝置帳戶的新式驗證**。 Surface Hub支援 Exchange Web Services (EWS) 和 Active Directory 驗證庫 (ADAL) 型驗證以連接到 Exchange，讓客戶可以取消使用基本驗證。 若要深入瞭解[，請參閱在](surface-hub-modern-auth.md)Surface Hub。
- **MDM 超過 20 個新的和更新行動裝置管理 (管理) 設定**。  這些策略設定為 IT 系統管理員改善了對多個裝置設定的控制，包括：Microsoft Store 中的 App 更新、Miracast 對基礎結構的無線投影設定、網路設定 ，例如品質-服務與 802.1x 有線驗證，以及新的隱私權/GDPR 相關設定。 新的組 (服務提供者和) 包括： 

  - [帳戶 CSP](/windows/client-management/mdm/accounts-csp) 
  - [防火牆-CSP](/windows/client-management/mdm/firewall-csp) 
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp) 
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp) 
  - [有線網路-CSP](/windows/client-management/mdm/wirednetwork-csp) 

若要深入瞭解，請參閱： 
- [支援 CSP Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [使用 MDM 提供者管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)


##  <a name="azure-active-directory-joined-devices"></a>Azure Active Directory已加入的裝置

- **Azure AD (裝置) SSO 帳戶**上的單一登入。 當使用者使用自己的 Microsoft 365認證來登錄「我的會議和檔案」時，他們的使用者認證會從應用程式順暢地從應用程式Microsoft 365瀏覽器體驗。
- **Azure AD (的 CA) 條件式存取**。 IT 系統管理員可以依照其公司安全性與合規性需求指派裝置策略，以控制從 Azure AD 加入 Surface Hubs 的使用者對組織資源的存取權。
- **支援 Azure AD 加入裝置的非全域系統管理員**。 客戶可以選擇在其系統管理階層中更精細的一組系統管理員來管理Surface Hub。 若要深入瞭解，請參閱在 Surface Hub[上設定非全域系統管理員Surface Hub。](surface-hub-2s-nonglobal-admin.md)


## <a name="browser-and-pen"></a>瀏覽器和筆

- **支援新的Microsoft Edge。** Microsoft Edge已重新建立，以獲得最佳相容性、安全性和隱私權。 若要深入瞭解，請參閱在 Microsoft Edge 安裝[Surface Hub。](surface-hub-install-chromium-edge.md)
- **在 2S 上Surface Hub筆筆筆**。   使用者可以使用兩支 2 支Surface Hub在 2S 上Surface Hub並排共同合作。 啟用雙筆書寫所需的固件更新會隨後續更新一起發行。

## <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams安裝 。**        Microsoft Teams會包含在新的 Surface Hub 裝置上的預設會議、通話和共同Surface Hub應用程式，這些裝置可透過 MDM 進行變更或Surface Hub應用程式設定應用程式。 若要深入瞭解[，請參閱部署](/MicrosoftTeams/teams-surface-hub)Microsoft Teams。
- **支援使用 Microsoft Teams。**  鄰近連接可讓使用者使用膝上型Microsoft Teams/電話Surface Hub進行排定的通話，或順暢地將進行中的會議轉換為附近的會議Surface Hub。 Windows 10 團隊版 2020 Update 新增行動裝置管理 (MDM) 以設定鄰近連接。 若要深入瞭解，請參閱： 

  - [Microsoft Teams部落格](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。 
  - [在 Surface Hub 上管理 Microsoft Teams 設定](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **支援使用 Microsoft Teams。** 在具有 Surface Hub 和 Microsoft Teams 會議室裝置或兩個 Surface Hub 裝置的空間的會議室中，協調會議可讓使用者在 Microsoft Teams 會議期間輕鬆運用這兩Microsoft Teams裝置。 使用者只需點一下，就可以從其中一個裝置加入會議，在一個裝置上顯示視音訊摘要，另一個裝置上顯示數位白板或內容，以最大化螢幕空間。 Windows 10 團隊版 2020 Update 會新增行動裝置管理 (MDM) 支援，以設定協調會議，這項功能隨後會以 Microsoft Teams 更新方式Microsoft Store。若要深入瞭解，請參閱使用 Microsoft Teams 會議室 和 Surface Hub[設定Surface Hub。](/MicrosoftTeams/rooms/coordinated-meetings)

## <a name="security"></a>安全性

- **使用 FIDO2 安全性金鑰進行無密碼登錄**    使用 FIDO2 安全性金鑰，客戶可以快速且輕鬆地Surface Hub，而不需要輸入使用者名稱和密碼。 此功能與單一Sign-On (SSO) 結合，在會議期間提供快速流暢的檔案、應用程式和網站的驗證。 若要深入瞭解，請參閱在 Surface Hub[上設定無密碼Surface Hub。](surface-hub-2s-phone-authenticate.md)
- **改良使用**Microsoft Authenticator。  對於使用 Azure AD 的組織，使用者可以使用 Microsoft Authenticator 應用程式來登錄，而不需要輸入使用者名稱和密碼。 此外，除了使用者主體名稱或 UPN (之外，使用者可以在 Azure AD 中使用他們偏好的電子郵件別名) 。 若要深入瞭解，請參閱使用 Surface Hub [Microsoft Authenticator。](surface-hub-authenticator-app.md)


## <a name="learn-more"></a>深入了解

- [Windows 10 團隊版的更新推出](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [安裝 Windows 10 團隊版 2020 更新](surface-hub-2020-update.md)  
 
