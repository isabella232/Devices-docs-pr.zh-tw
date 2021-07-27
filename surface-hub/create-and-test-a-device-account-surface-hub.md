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
ms.openlocfilehash: 9d2214453c8cb4c8d03f526dd4ac83264d2a16ad
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676377"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>建立和測試裝置帳戶 (Surface Hub)

建立Surface Hub裝置帳戶 (也稱為資源帳戶/會議室信箱) 可讓 Surface Hub 接收、核准或拒絕會議要求並加入會議。

一旦裝置帳戶在 Surface Hub上配置後，人員就可以將此帳戶新加到會議邀請中，其方式與邀請會議室的方式相同。 

您可以在 OOBE 的開箱即用體驗期間設定 ([裝置) 帳戶](first-run-program-surface-hub.md)。 如果需要，您也可以稍後在帳戶**設定Surface Hub**  >  ****  >  **變更**。

## <a name="configuration-overview"></a>設定概觀

下表說明建立裝置帳戶的主要步驟和設定決策。
 
| 步驟 | 說明                     |  用途                             |
|------|---------------------------------|--------------------------------------|
| 1    | 在 2016 (Exchange Online或 2016 Exchange Server建立啟用登入的會議室信箱)  | 這種類型的信箱可讓裝置維護會議日曆、接收會議要求，以及傳送郵件。 您必須啟用登入，才能與 Surface Hub。 |
| 2    | 設定信箱屬性 | 信箱必須設定為正確屬性，以在 Surface Hub 上提供最佳的會議體驗。 如需信箱屬性的詳細資訊，請參閱[信箱屬性](exchange-properties-for-surface-hub-device-accounts.md)。 |
| 3    | 請Exchange啟用 EWS (Web Services) ，並停用 MFA (多重要素) 驗證 | 此Surface Hub使用 EWS 來同步其日曆。 如果您預設不允許環境中有 EWS，中心信箱必須明確啟用。 當Surface Hub在背景Exchange使用者互動時，無法回應任何互動式提示，例如 MFA。 您建立之裝置帳戶必須排除在任何這類驗證需求之外。 否則，Surface Hub 將無法同步處理郵件和行事曆資訊。 |
| 4    | 為 2015 Teams或 商務用 Skype (商務用 Skype Server啟用帳戶)  | 商務用 Skype或Teams，使用視像通話和螢幕分享等會議功能。 有關啟用授權或授權Teams，請參閱Teams 會議室[授權](/MicrosoftTeams/rooms/rooms-licensing)Teams[描述](/office365/servicedescriptions/teams-service-description)。 Teams上的 Surface Hub 和 SfB 應用程式與[Azure AD 條件](/azure/active-directory/conditional-access/concept-conditional-access-policies)式 Access 要求裝置資訊 (例如合規性) 。 您建立之裝置帳戶必須排除在任何這類 CA 策略之外。 否則，Surface Hub無法使用任何會議功能。 |
| 5    | (選擇性) 停用密碼到期 | 為了簡化管理作業，您可以將裝置帳戶的密碼到期關閉，並允許 Surface Hub 自動循環裝置帳戶密碼。 如需密碼管理的詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。  |
| 6    |  (選擇性) 設定Exchange以允許 ActiveSync | 使用特定內部部署Exchange Server & Active Directory 部署，ActiveSync 會用來同步處理裝置帳戶郵件和日曆資訊。 若要進一步瞭解有關設定之政策的資訊，請參閱[適用于 Surface Hub 的 ActiveSync 政策](apply-activesync-policies-for-surface-hub-device-accounts.md)。 |

> [!NOTE]  
> Surface Hub裝置帳戶不支援協力廠商聯合身分識別提供者 (IdPs) ，而且必須透過 Active Directory 或 Azure Active Directory。

## <a name="detailed-configuration-steps"></a>詳細設定步驟 

我們建議您使用遠端Surface Hub來設定您的Windows PowerShell。 Microsoft 提供[SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新資源帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為Surface Hub帳戶。 如果您願意，您可以從下表選擇一個選項，然後根據您的組織部署遵循詳細的 PowerShell 步驟。

| 組織部署             |  說明                  |        設定期間Surface Hub格式
|---------------------------------|--------------------------------------|
| [線上部署 (Microsoft 365或Office 365) ](/MicrosoftTeams/rooms/with-office-365) |貴組織的環境完全部署在 Microsoft 365 或 Office 365。 | username@domain.com |
| [內部部署 (Exchange部署) ](/MicrosoftTeams/rooms/with-exchange-on-premises) | 貴組織有混合式服務，Exchange Server內部部署和Microsoft Teams主機。 | username@domain.com[中啟用](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication)混合式新式驗證時，否則Exchange網域\使用者名稱 |
| [混合式部署 (Exchange Online) ](/MicrosoftTeams/rooms/with-exchange-online) | 貴組織有混合式服務，商務用 Skype Server內部部署和Exchange Online。 | username@domain.com [在](/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) SfB 中啟用混合式新式驗證時，否則使用 DOMAIN\username |
| [內部部署 (單一樹系)](/MicrosoftTeams/rooms/with-skype-for-business-server-2015) | 貴組織有它控制的伺服器，其中 Active Directory、Exchange和商務用 Skype Server託管在單一林環境中。  | DOMAIN\username |
| [內部部署 (多重樹系)](/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | 貴組織有它控制的伺服器，其中 Active Directory、Exchange 和 商務用 Skype Server託管在多林環境中。 | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>帳戶驗證與測試

您可以使用兩種方法來驗證和測試[Surface Hub帳戶](https://go.microsoft.com/fwlink/?linkid=870105)：SkypeRoomProvisioningScript.ps1和 Surface Hub[診斷應用程式](https://www.microsoft.com/store/apps/9nblggh51f2g)。 帳戶配置腳本可以從您的電腦使用 PowerShell 驗證先前建立的設備帳戶。 Surface Hub 硬體診斷應用程式已安裝在 Surface Hub 上，並且會提供有關登入及通訊失敗的詳細意見反應。 兩者都是要測試新建立裝置帳戶的實用工具，您應該用來確保最佳的帳戶可用性。
