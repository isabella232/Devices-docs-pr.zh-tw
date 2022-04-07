---
title: Windows 10 團隊版 2020 更新的新功能
description: 查看 Surface Hub 作業系統最新更新的新功能，Windows 10 團隊版 2020 更新]。
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
ms.openlocfilehash: 6a35783c08fdc4da3b3c7aabcd99da385c292d24
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472532"
---
# <a name="whats-new-in-windows-10-team-2020-updates"></a>Windows 10 團隊版 2020 更新的新功能

Surface Hub提供新功能的定期更新所帶來的好處。 2020 Update (20H2 會) Windows 10 團隊版，後續更新 1 & Update 2，提供裝置部署和管理能力的重大改善，以及最新的Windows 10功能。

## <a name="windows-10-team-2020-update-2"></a>Windows 10 團隊版 2020 Update 2 

### <a name="gcc-high-support"></a>GCC高支援

安裝此更新 ([KB5010415](https://support.microsoft.com/help/5010415)或後續的 Windows CU) 之後，GCC High 環境中支援 Surface Hub。 此時，需要[額外的步驟](surface-hub-teams-rooms.md#support-for-teams-rooms-in-government-community-cloud-high-gcc-h)，Teams 會議室用戶端才能成功連線到 GCC High 租使用者。

### <a name="support-for-surface-hub-2-smart-camera"></a>支援 Surface Hub 2 智慧相機

AI 支援的 Surface Hub 2 智慧相機已針對混合式小組優化，可讓遠端參與者查看人員與Surface Hub上的內容互動，同時檢視會議室中的其他人。  若要深入瞭解，請參閱[安裝和管理 Surface Hub 2 智慧相機]](surface-hub-2-smart-camera.md) 。 

### <a name="support-for-progressive-web-apps-pwas"></a>支援漸進式Web Apps (PWA) 

系統管理員可以使用行動裝置管理提供者 (MDM) 套用布建套件，從遠端安裝 Surface Hub 上的 PWA。 若要深入瞭解，請參閱[在Surface Hub上安裝漸進式Web Apps](install-pwa-surface-hub.md)。 

### <a name="ease-of-access-updates"></a>輕鬆存取更新

使用者可以在Surface Hub會話期間調整 [輕鬆存取] 設定，並關閉應用程式，就像在其他版本的Windows 10一樣。 

- **輕鬆存取**。 使用者可以在不登入的情況下調整下列設定：顯示器、文字游標、放大鏡、高對比、朗讀程式、隱藏式輔助字幕和鍵盤。 
- **應用程式的熟悉 UI**。 使用者可以選取應用程式右上角的 [關閉] 按鈕，以關閉Surface Hub上的應用程式。 這可讓您將應用程式拖曳到Surface Hub顯示器的底部，藉此關閉應用程式的需求。  (注意：這項功能將在 Edge 瀏覽器上作為下一個 Edge 更新的一部分提供，排程為 2022 年 3 月。)  

若要深入瞭解，請[參閱調整Surface Hub的輕鬆存取設定](accessibility-surface-hub.md)。

### <a name="administrator-updates"></a>系統管理員更新

- **事件檢視器**。 系統管理員可以直接從設定應用程式存取Windows 事件檢視器。 
- **新的行動裝置管理 (MDM) 原則設定**。 新的設定服務提供者 (CSP) 包括：

  - [TimeLanguageSettings-CSP](/windows/client-management/mdm/policy-csp-timelanguagesettings)
  - [LocalUsersAndGroups-CSP](/windows/client-management/mdm/policy-csp-localusersandgroups) 

若要深入瞭解，[請參閱在 Surface Hub 上設定非全域系統管理員帳戶](surface-hub-2s-nonglobal-admin.md)。


## <a name="windows-10-team-2020-update-1"></a>Windows 10 團隊版 2020 Update 1

### <a name="support-for-new-teams-rooms-application"></a>支援新的Teams 會議室應用程式

安裝此更新 ([KB5005101](https://support.microsoft.com/help/5005101)或後續的 Windows CU) 之後，Surface Hubs 支援透過 Windows Update 自動升級至新的[Teams 會議室 客戶](surface-hub-teams-rooms.md)端。

### <a name="support-for-new-whiteboard-application"></a>支援新的 Whiteboard 應用程式

安裝此更新之後，Surface Hub 支援透過Microsoft Store更新) 新的[Whiteboard 應用程式](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/unified-whiteboard-experience-coming-to-surface-hub/ba-p/3145226)時，自動升級 (。

### <a name="new-microsoft-edge-browser-installed-by-default"></a>預設會安裝新的Microsoft Edge瀏覽器

安裝此更新之後，Surface Hub 會自動將其舊版 Microsoft Edge瀏覽器取代為新的Chromium型 Edge 瀏覽器。  若要深入瞭解，請[參閱管理Surface Hub上的Microsoft Edge](surface-hub-install-chromium-edge.md)。 安裝此更新或後續的Windows CU 之後，Windows 10 團隊版就不再提供舊版 Edge。


## <a name="windows-10-team-2020-update-20h2"></a>Windows 10 團隊版 2020 更新 (20H2) 

### <a name="deployment-and-manageability"></a>部署和管理能力

- **雲端裝置帳戶的新式驗證**。 Surface Hub支援Exchange Web 服務 (EWS) 和 Active Directory 驗證程式庫 (ADAL) 型驗證來連線到Exchange，讓客戶能夠取代基本驗證的使用。 若要深入瞭解，請參閱[Surface Hub 的新式驗證](surface-hub-modern-auth.md)。
- **超過 20 個新的和更新的 MDM 原則設定**。  這些原則設定可讓 IT 系統管理員改善對多個裝置設定的控制，包括來自Microsoft Store的應用程式更新、透過基礎結構Miracast等無線投影設定、服務品質和 802.1x 有線驗證等網路設定，以及新的隱私權/GDPR 相關設定。 新的 CSP 包括：

  - [帳戶 CSP](/windows/client-management/mdm/accounts-csp)
  - [Firewall-CSP](/windows/client-management/mdm/firewall-csp)
  - [RemoteWipe CSP](/windows/client-management/mdm/remotewipe-csp)
  - [Wifi-CSP](/windows/client-management/mdm/wifi-csp)
  - [Wirednetwork-CSP](/windows/client-management/mdm/wirednetwork-csp)

若要深入瞭解，請參閱：

- [Microsoft Surface Hub中支援的 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [使用 MDM 提供者管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)

### <a name="azure-active-directory-joined-devices"></a>Azure Active Directory加入的裝置

- **已加入Azure AD裝置的單一登入 (SSO) **。 當使用者使用其Microsoft 365認證登入**我的會議和檔案**時，其認證會順暢地從應用程式流向應用程式，包括瀏覽器中的Microsoft 365體驗。
- **已加入Azure AD裝置的條件式存取 (CA) **。 IT 系統管理員可以根據其公司安全性和合規性需求指派裝置原則，以控制使用者從已加入Azure AD Surface Hub 對組織資源的存取。
- **支援已加入Azure AD裝置的非全域系統**管理員。 客戶可以在其系統管理階層中選擇一組更細微的系統管理員來管理Surface Hub。 若要深入瞭解，[請參閱在 Surface Hub 上設定非全域系統管理員帳戶](surface-hub-2s-nonglobal-admin.md)。

### <a name="inking-improvements"></a>筆跡改善

- **支援在 Surface Hub 2S 上使用雙手寫筆筆跡**。  使用白板，並以兩個 Surface Hub 2 手寫筆在 Surface Hub 2S 上並行共同作業。 升級至 Windows 10 團隊版 2020 之後安裝的任何系統硬體更新，都會為此案例新增韌體支援。

### <a name="microsoft-teams"></a>Microsoft Teams  

- **預設會安裝Microsoft Teams**。 Microsoft Teams是新Surface Hub裝置上會議、通話和共同作業的預設應用程式，可透過 MDM 或直接在使用設定應用程式的Surface Hub上進行變更或設定。 若要深入瞭解，請[參閱部署Microsoft Teams](/MicrosoftTeams/teams-surface-hub)。
- **支援與 Microsoft Teams 的鄰近聯結**。  鄰近聯結可讓使用者使用膝上型電腦或手機，在附近的Surface Hub上進行排程Microsoft Teams通話。  它也可讓使用者將進行中的會議轉換到附近的Surface Hub。 Windows 10 團隊版 2020 Update 新增行動裝置管理 (MDM) 支援來設定鄰近聯結。 若要深入瞭解，請參閱：

  - [Microsoft Teams部落格。](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)
  - [在 Surface Hub 上管理 Microsoft Teams 設定](/MicrosoftTeams/rooms/surface-hub-manage-config)

- **支援與Microsoft Teams協調會議**。 在具有Surface Hub和Microsoft Teams會議室裝置的會議室，或具有兩個Surface Hub裝置的空格中，協調會議可讓使用者在Microsoft Teams會議期間快速運用這兩個裝置。 使用者可以透過單一點選從任一裝置加入會議，並在一部裝置上顯示影片摘要，並在另一部裝置上顯示數位白板或內容，以將螢幕空間最大化。 Windows 10 團隊版 2020 更新會新增行動裝置管理 (MDM) 支援來設定協調會議，而此功能後續會透過 Microsoft Store 發行為Microsoft Teams更新。 若要深入瞭解，[請參閱使用Microsoft Teams 會議室和Surface Hub](/MicrosoftTeams/rooms/coordinated-meetings)設定協調會議。

### <a name="security"></a>安全性

- **使用 FIDO2 安全性金鑰的無密碼登入**使用 FIDO2 安全性金鑰，使用者可以快速登入Surface Hub，而不需要輸入使用者名稱和密碼。 這項功能結合單一Sign-On (SSO) ，可在會議期間為檔案、應用程式和網站提供快速且順暢的驗證。 若要深入瞭解，[請參閱在 Surface Hub 上設定無密碼登入](surface-hub-2s-phone-authenticate.md)。
- **使用 Microsoft Authenticator 的無密碼登入改善**。  對於使用 Azure AD 的組織，使用者可以使用Microsoft Authenticator應用程式登入。 此外，使用者可以在 Azure AD 中使用慣用的電子郵件別名或其使用者主體名稱 (UPN) 登入。 若要深入瞭解，[請參閱使用 Microsoft Authenticator 登入Surface Hub](surface-hub-authenticator-app.md)。

## <a name="learn-more"></a>深入了解

- [Windows 10 團隊版 2020 Update 1 發行至所有 Surface Hub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/windows-10-team-2020-update-1-released-to-all-surface-hubs/ba-p/2653503)
- [Windows 10 團隊版 2020 更新 10 月 27 日推出](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-available-october-27/ba-p/1810739)
- [安裝 Windows 10 團隊版 2020 更新](surface-hub-2020-update.md)
