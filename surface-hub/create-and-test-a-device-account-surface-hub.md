---
title: 建立和測試裝置帳戶 (Surface Hub)
description: 本主題介紹如何建立和測試 Microsoft Surface Hub 用來與 Microsoft Exchange 和 Skype 通訊的裝置帳戶。
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: 建立和測試裝置帳戶, 裝置帳戶, Surface Hub 與 Microsoft Exchange, Surface Hub 與 Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/01/2021
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: c925cb952c7fd04a86d824dfba99a373c07b313e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472622"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>建立和測試裝置帳戶 (Surface Hub)

建立Surface Hub裝置帳戶 (也稱為資源帳戶/會議室信箱) 可讓Surface Hub接收、核准或拒絕會議邀請和加入會議。

在Surface Hub上布建裝置帳戶之後，人們就可以將此帳戶新增至會議邀請，就像邀請會議室一樣。 

您可以在全新 [體驗 (OOBE) 設定期間設定](first-run-program-surface-hub.md)裝置帳戶。 如有需要，您也可以稍後在**設定**  >  **Surface Hub**  >  **Accounts 中**加以變更。

## <a name="configuration-overview"></a>設定概觀

下表說明建立裝置帳戶的主要步驟和設定決策。
 
| 步驟 | 說明                     |  用途                             |
|------|---------------------------------|--------------------------------------|
| 1    | 建立已啟用登入的會議室信箱 (Exchange Online或Exchange Server 2016 和更新版本)  | 這種類型的信箱可讓裝置維護會議行事曆、接收會議邀請，以及傳送郵件。 它必須啟用登入，才能與Surface Hub搭配使用。 |
| 2    | 設定信箱屬性 | 信箱必須設定為正確屬性，以在 Surface Hub 上提供最佳的會議體驗。 如需信箱屬性的詳細資訊，請參閱[信箱屬性](exchange-properties-for-surface-hub-device-accounts.md)。 |
| 3    | 確定已啟用 Exchange Web 服務 (EWS) ，並停用 MFA)  (多重要素驗證 | Surface Hub會使用 EWS 來同步處理其行事曆。 如果您預設不允許環境中的 EWS，則中樞信箱必須明確啟用它。 當Surface Hub在背景中登入Exchange，而沒有使用者互動時，就無法回應任何互動提示，例如 MFA。 您建立的裝置帳戶必須排除在任何這類驗證需求之外。 否則，Surface Hub 將無法同步處理郵件和行事曆資訊。 |
| 4    | 啟用 Teams 或 2015 商務用 Skype (商務用 Skype Server 更新版本的帳戶)  | 商務用 Skype或Teams必須啟用，才能使用會議功能，例如視訊通話和螢幕畫面分享。 如需啟用Teams的授權詳細資訊，請[參閱Teams 會議室授權](/MicrosoftTeams/rooms/rooms-licensing)和[Teams服務描述](/office365/servicedescriptions/teams-service-description)。 Surface Hub上的Teams和 SfB 應用程式與Azure AD條件[式存取](/azure/active-directory/conditional-access/concept-conditional-access-policies)原則不相容，這些原則需要裝置資訊 (例如合規性) 。 您建立的裝置帳戶必須排除在任何這類 CA 原則之外。 否則，Surface Hub無法使用任何會議功能。 |
| 5    | (選擇性) 停用密碼到期 | 為了簡化管理作業，您可以將裝置帳戶的密碼到期關閉，並允許 Surface Hub 自動循環裝置帳戶密碼。 如需密碼管理的詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。  |

> [!NOTE]  
> Surface Hub裝置帳戶不支援協力廠商同盟識別提供者 (idPs) ，而且必須透過 Active Directory 或 Azure Active Directory 進行驗證。

## <a name="detailed-configuration-steps"></a>詳細設定步驟 

裝置帳戶設定步驟可能會根據環境而有所不同。 從下表中選取您的部署案例以尋找適當的步驟，並記下 [要使用的格式] 資料行，以便在布建帳戶之後設定 Surface Hub。

| 組織部署             |  說明                  |        設定期間要使用的格式Surface Hub
|---------------------------------|--------------------------------------|
| [線上部署 (Microsoft 365) ](/MicrosoftTeams/rooms/with-office-365?tabs=m365-admin-center) |您組織的環境完全部署在Microsoft 365上。 | username@domain.com |
| [混合式部署 (Exchange內部部署) ](/MicrosoftTeams/rooms/with-office-365?tabs=exchange-server) | 您的組織混合使用服務，Exchange Server裝載于內部部署和線上Microsoft Teams。 | username@domain.com 是否已在 Exchange 中啟用[混合式新式驗證](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication)，否則為 DOMAIN\username |
| [混合式部署 (Exchange Online) ](/skypeforbusiness/deploy/deploy-clients/hybrid-deployments) | 您的組織混合使用服務，商務用 Skype Server裝載于內部部署和Exchange Online。 | username@domain.com 是否已在 SfB 中啟用 [混合式新式驗證](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) ，否則為 DOMAIN\username |
| [內部部署 (單一樹系)](/skypeforbusiness/deploy/deploy-clients/single-forest-on-premises-deployments) | 您的組織擁有其所控制的伺服器，其中 Active Directory、Exchange 和 商務用 Skype Server 裝載于單一樹系環境中。  | DOMAIN\username |
| [內部部署 (多重樹系)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | 您的組織擁有其所控制的伺服器，其中 Active Directory、Exchange 和 商務用 Skype Server 裝載于多樹系環境中。 | ACCOUNTFOREST\username |

針對線上部署，另外還有一個[部署精靈可供直接](https://admin.microsoft.com/Adminportal/Home#/modernonboarding/surfacehubsetupguide)在 M365 系統管理中心Microsoft 365系統管理員使用。 此精靈可協助您建立新的裝置帳戶，或驗證您擁有的現有資源帳戶，以協助將它們轉換成相容Surface Hub裝置帳戶。
