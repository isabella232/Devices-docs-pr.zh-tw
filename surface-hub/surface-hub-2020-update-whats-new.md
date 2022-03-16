---
title: 2020 更新Windows 10 團隊版新功能
description: 查看 2020 更新等作業系統Surface Hub更新Windows 10 團隊版新增功能。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
ms.openlocfilehash: c44ec68a39158910c841375aeda0a6d6bf11635f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448266"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>2020 更新Windows 10 團隊版新功能

Surface Hub提供新功能的定期更新帶來的好處。 2020 更新 (20H2) Windows 10 團隊版，以及後續更新 1 & 更新 2，大幅改善了裝置部署和可管理性，以及最新的 Windows 10 功能。

## <a name="windows-10-team-2020-update-2"></a>Windows 10 團隊版 2020 更新 2 

### <a name="gcc-high-support"></a>GCC高支援

在[KB5010415 (或](https://support.microsoft.com/help/5010415)後續的 WINDOWS CU) 安裝此更新之後，Surface Hubs GCC支援。 目前，需要[其他步驟](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h)，讓用戶端Teams 會議室成功連接到 GCC租使用者。

### <a name="ease-of-access-updates"></a>輕鬆存取更新

使用者可以在會話期間調整輕鬆存取Surface Hub並關閉應用程式，就像在其他版本的 Windows 10。 

- **輕鬆存取**。 使用者可以在不登錄的情況下調整下列設定：顯示、文字游標、放大鏡、高對比、旁白、隱藏式字幕和鍵盤。 
- **熟悉的 App UI**。 使用者可以選取應用程式右上角Surface Hub關閉按鈕，即可關閉應用程式。 這樣一來，將 App 拖曳到顯示畫面底部，即可Surface Hub應用程式。  (：這項功能將在 Edge 瀏覽器上提供，做為下一次 Edge 更新的一部分，計畫在 2022 年 3 月)  

若要深入瞭解，請參閱在 Surface Hub 上[調整輕鬆存取Surface Hub](accessibility-surface-hub.md)。

### <a name="administrator-updates"></a>系統管理員更新

- **事件檢視器**。 管理員可以直接從應用程式Windows活動檢視器設定活動檢視器。 
- **新的行動裝置管理 (MDM) 設定**。 新的組 (服務提供者) 包括：

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

若要深入瞭解，請參閱在 Surface Hub[中設定非全域Surface Hub](surface-hub-2s-nonglobal-admin.md)。


## <a name="windows-10-team-2020-update-1"></a>Windows 10 團隊版 2020 更新 1

### <a name="support-for-new-teams-rooms-application"></a>支援新的Teams 會議室應用程式

安裝此更新 ([KB5005101](https://support.microsoft.com/help/5005101)或後續 Windows CU) 之後，Surface Hubs 支援透過 Windows Update[自動](surface-hub-teams-rooms.md)升級至新的 Teams 會議室 用戶端。

### <a name="support-for-new-whiteboard-application"></a>支援新的 Whiteboard 應用程式

安裝此更新之後，Surface Hubs 會支援自動升級 (，) 透過更新功能Microsoft Store新的[Whiteboard](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226) App。

### <a name="new-microsoft-edge-browser-installed-by-default"></a>預設Microsoft Edge瀏覽器的新增功能

安裝此更新之後，Surface Hubs 會自動將其舊版 Microsoft Edge瀏覽器取代為新的Chromium型 Edge 瀏覽器。  若要深入瞭解，請參閱在 Microsoft Edge[上Surface Hub](surface-hub-install-chromium-edge.md)。 安裝此更新或後續的 CU 之後，Windows 10 團隊版不再提供 Edge Legacy Windows版本。


## <a name="windows-10-team-2020-update-20h2"></a>Windows 10 團隊版 2020 更新 (20H2) 

### <a name="deployment-and-manageability"></a>部署與可管理性

- **雲端裝置帳戶的現代化驗證**。 Surface Hub支援 Exchange Web Services (EWS) 和 Active Directory 驗證庫 (ADAL) 型驗證以連接到 Exchange，讓客戶可以取消使用基本驗證。 若要深入瞭解[，請參閱在](surface-hub-modern-auth.md)Surface Hub。
- **超過 20 個新的和更新的 MDM 策略設定**。  這些策略設定為 IT 系統管理員改善了對多個裝置設定的控制，包括 Microsoft Store 中的應用程式更新、Miracast 對基礎結構的無線投影設定、網路設定 ，例如品質-服務與 802.1x 有線驗證，以及新的隱私權/GDPR 相關設定。 新的 CSP 包括：

  - [帳戶 CSP](/windows/client-management/mdm/accounts-csp)
  - [防火牆-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [有線網路-CSP](/windows/client-management/mdm/wirednetwork-csp)

若要深入瞭解，請參閱：

- [支援 CSP Microsoft Surface Hub](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [使用 MDM 提供者管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory已加入的裝置

- **針對已連接 (裝置) SSO Azure AD單一登入**。 當使用者以自己的認證Microsoft 365我的會議和檔案時，他們的認證**** 會從應用程式順暢地從應用程式Microsoft 365瀏覽器體驗。
- **已加入 (裝置) CA Azure AD條件式存取**。 IT 系統管理員可以控制使用者從已加入的 Surface Hub Azure AD存取組織資源，方法就是根據他們的公司安全性與合規性需求指派裝置策略。
- **支援已加入Azure AD的非全域系統管理員**。 客戶可以選擇其系統管理階層中的一組更精細的系統管理員來管理Surface Hub。 若要深入瞭解，請參閱在 Surface Hub[中設定非全域Surface Hub](surface-hub-2s-nonglobal-admin.md)。

### <a name="inking-improvements"></a>書寫改良功能

- **支援在 2S 上Surface Hub筆筆筆**。  在 2S 上使用白板並Surface Hub兩支 2 支Surface Hub共同合作。 升級至 2020 Windows 10 團隊版安裝的任何系統硬體更新都會新增此案例的固件支援。

### <a name="microsoft-teams"></a>Microsoft Teams  

- **Microsoft Teams安裝。** Microsoft Teams是新 Surface Hub 裝置上會議、通話和共同合作的預設應用程式，您可以透過 MDM 變更或Surface Hub應用程式設定應用程式。 若要深入瞭解，請參閱部署[Microsoft Teams](/MicrosoftTeams/teams-surface-hub)。
- **支援使用鄰近連接Microsoft Teams**。  鄰近連接可讓使用者使用膝上型電腦或Microsoft Teams，在附近的Surface Hub進行排定的通話。  它也允許使用者將進行中的會議切換至附近的Surface Hub。 Windows 10 團隊版 2020 Update 新增行動裝置管理 (MDM) 以設定鄰近連接。 若要深入瞭解，請參閱：

  - [Microsoft Teams部落格](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。
  - [在 Surface Hub 上管理 Microsoft Teams 設定](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **支援使用Microsoft Teams**。 在具有 Surface Hub 和 Microsoft Teams 會議室裝置或兩個 Surface Hub 裝置的空間的會議室中，協調會議可讓使用者在 Microsoft Teams 會議期間快速運用這兩Microsoft Teams裝置。 使用者只需點一下，即可從任一裝置加入會議，並可在其中一個裝置上顯示視音訊摘要，另一個裝置上顯示數位白板或內容，以最大化螢幕空間。 Windows 10 團隊版 2020 Update 新增行動裝置管理 (MDM) 支援，以設定協調會議，這項功能隨後會以 Microsoft Teams 更新方式Microsoft Store。 若要深入瞭解，請參閱[設定](/MicrosoftTeams/rooms/coordinated-meetings)具有Microsoft Teams 會議室Surface Hub。

### <a name="security"></a>安全性

- **使用 FIDO2 安全金鑰進行無密碼登錄**使用 FIDO2 安全性金鑰，使用者可以快速Surface Hub使用者名稱和密碼即可快速登錄。 此功能與單一Sign-On (SSO) 結合，在會議期間提供快速流暢的檔案、應用程式和網站的驗證。 若要深入瞭解，請參閱在 Surface Hub[上設定無密碼Surface Hub](surface-hub-2s-phone-authenticate.md)。
- **使用密碼登錄的改良功能Microsoft Authenticator**。  對於使用 Azure AD 的組織，使用者可以使用 Microsoft Authenticator 應用程式進行登錄。 此外，使用者可以使用他們偏好的電子郵件別名在 Azure AD 中，以及其使用者主體名稱 (UPN) 。 若要深入瞭解，請參閱[使用 Surface Hub Microsoft Authenticator](surface-hub-authenticator-app.md)。

## <a name="learn-more"></a>深入了解

- [Windows 10 團隊版所有 Surface Hub 的 2020 更新 1](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 團隊版 2020 年 10 月 27 日提供更新](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [安裝 Windows 10 團隊版 2020 更新](surface-hub-2020-update.md)
