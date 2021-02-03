---
title: Windows 10 團隊版 2020 更新中的新功能
description: 查看最新的 Surface Hub 作業系統、Windows 10 Team 2020 更新更新功能。
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
ms.openlocfilehash: f87b8f084b8731bfb329b6c52403d565bca03e3e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312049"
---
# Windows 10 團隊版 2020 更新中的新功能

Windows 10 團隊2020更新帶來了主要的裝置部署和管理功能以及最新的 Windows 10 功能。

##  部署與可管理性

- **雲端裝置帳戶的新式驗證**。 Surface Hub 支援 Exchange Web 服務 (EWS) 和 Active Directory 驗證庫 (ADAL) 以連線到 Exchange 的驗證，讓客戶能夠取代基本驗證的使用。 若要深入瞭解，請參閱 [Surface Hub 上的新式驗證](https://docs.microsoft.com/surface-hub/surface-hub-modern-auth)。
- **超過20個新增及更新的行動裝置管理 (MDM) 原則**。      這些原則賦予 IT 管理員改善多個裝置設定的控制權，包括： Microsoft Store 的 app 更新、無線投影設定（例如服務品質與 802.1 x 有線驗證），以及新的隱私權/GDPR 相關設定。 若要深入瞭解，請參閱： 
- [使用 Microsoft Intune 管理 Surface Hub](surface-hub-2s-manage-intune.md)2。
- [Microsoft Surface Hub 支援的 CSPs 原則](https://docs.microsoft.com//windows/client-management/mdm/policy-csps-supported-by-surface-hub)

##  Azure Active Directory 已加入裝置

- **針對 AZURE AD 已加入裝置的單一登入 (SSO) **。 當使用者使用 Microsoft 365 認證登入 [我的會議與檔案] 時，他們的使用者認證流程無法順利地從 app 移至 app，包括在瀏覽器中的 Microsoft 365 體驗。
- **AZURE AD 已加入裝置的條件式存取 (CA) **。       IT 管理員可以將裝置層級的安全性原則部署到其 Azure AD 聯結 Surface Hub，以根據公司安全性與合規性需求控制對組織資源的存取權。
- **支援針對 AZURE AD 已加入裝置的非全域管理員**。 客戶可以在其系統管理階層選擇一組更精確的管理員，以管理 Surface Hub。 若要深入瞭解，請參閱 [在 Surface Hub 2 秒設定非全域管理員帳戶](surface-hub-2s-nonglobal-admin.md)。


## 瀏覽器和手寫筆

- **支援新的 Microsoft Edge**。 為了獲得最佳相容性效能、安全性和隱私權，已重建 Microsoft Edge。 若要深入瞭解，請參閱 [在 Surface Hub 上安裝及設定新的 Microsoft Edge](https://docs.microsoft.com/surface-hub/surface-hub-install-chromium-edge)。
- - **Surface Hub 2 上的雙筆筆跡**。   使用者可以使用兩個 Surface Hub 2 筆，在 Surface Hub 2 秒並排進行白板和共同作業。 啟動雙筆筆跡所需的固件更新將會以後續更新發行。

## Microsoft Teams  

- **預設會安裝 Microsoft 團隊**。        Microsoft 團隊會以預設會議、呼叫和共同作業的方式提供給新 Surface Hub 裝置，您可以透過 MDM 變更或設定，或直接在 Surface Hub 上使用 [設定] 應用程式進行設定。 若要深入瞭解，請參閱 [部署 Microsoft 團隊](https://docs.microsoft.com/MicrosoftTeams/teams-surface-hub)。
- **支援與 Microsoft 團隊的鄰近性加入**。  鄰近性連接能讓使用者使用膝上型電腦/手機在附近的 Surface Hub 上進行排程的 Microsoft 團隊通話，或將進行中的會議無縫轉換為附近的 Surface Hub。 Windows 10 小組2020更新會新增行動裝置管理 (MDM) 支援，以設定鄰近性聯結。 若要深入瞭解，請參閱： 

  - [Microsoft 團隊博客](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/microsoft-teams-devices-for-shared-spaces-july-and-august-update/ba-p/1604833)。 
  - [在 Surface Hub 上管理 Microsoft Teams 設定](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)

- **支援與 Microsoft 團隊進行協同會議**。 在具備 Surface Hub 及 Microsoft 球隊房間裝置的會議室中，或有含有兩個 Surface 中樞裝置的空間，共同合作的會議可讓使用者在 Microsoft 團隊會議期間輕鬆地利用這兩個裝置。 只要按一下滑鼠，使用者就能從任一裝置加入會議，並透過在單一裝置上顯示影片摘要，以及另一個裝置上的數位白板或內容，來最大化畫面。 Windows 10 Team 2020 更新會新增行動裝置管理 (的 MDM) 支援來設定協調會議，且後續功能將會透過 Microsoft Store.To 進行 Microsoft 團隊更新深入瞭解，請參閱 [使用 Microsoft 團隊聊天室和 Surface Hub 設定協調的會議](https://docs.microsoft.com/microsoftteams/rooms/coordinated-meetings)。

## 安全性

- **使用 FIDO2 安全金鑰 Passwordless 登入**     客戶可以使用 FIDO2 安全金鑰，快速且輕鬆地登入 Surface Hub，而不必輸入使用者名稱和密碼。 與單一 Sign-On (SSO) 結合，這項功能可在會議期間，提供檔案、應用程式及網站的快速且流暢的驗證。 若要深入瞭解，請參閱 [設定 Surface Hub 上的 passwordless 登入](https://docs.microsoft.com/surface-hub/surface-hub-2s-phone-authenticate)。
- **使用 Microsoft 驗證 passwordless 登入的改良功能**。  對於使用 Azure AD 的組織，使用者可以使用 Microsoft 驗證器應用程式來登入，而無需輸入使用者名稱和密碼。 此外，使用者也可以在 Azure AD 中使用其慣用的電子郵件別名，除了其使用者主體名稱 (UPN) 。 若要深入瞭解，請參閱 [使用 Microsoft 驗證器登入 Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-authenticator-app)。


## 深入了解

- [Windows 10 團隊版的更新推出](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/update-to-the-windows-10-team-rollout/ba-p/1669655)
- [安裝 Windows 10 團隊版 2020 更新](surface-hub-2020-update.md)  
 