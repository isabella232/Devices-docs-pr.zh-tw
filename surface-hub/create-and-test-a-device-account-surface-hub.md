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
ms.openlocfilehash: 685359f1371a1bef8bd216223a98b934c997a1d8
ms.sourcegitcommit: 879e80200aea26f6705c887fa392db5db35b99ed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/03/2021
ms.locfileid: "11475087"
---
# <a name="create-and-test-a-device-account-surface-hub"></a>建立和測試裝置帳戶 (Surface Hub)

建立 Surface Hub 裝置帳戶 (也稱為資源帳戶/會議室信箱) 可讓 Surface Hub 接收、核准或拒絕會議要求並加入會議。

在 Surface Hub 上配置裝置帳戶後，人員可以將此帳戶新增到會議邀請，其方式與邀請會議室的方式相同。 

您可以在 OOBE 的開箱即用體驗期間設定 ([裝置) 帳戶](first-run-program-surface-hub.md)。 如有必要，您也可以稍後在設定****  >  **Surface Hub 帳戶中**  >  **變更。**

## <a name="configuration-overview"></a>設定概觀

下表說明建立裝置帳戶的主要步驟和設定決策。
 
| 步驟 | 說明                     |  用途                             |
|------|---------------------------------|--------------------------------------|
| 1    | 在 Exchange Online 或 Exchange Server 2016 (建立啟用登入的會議室信箱)  | 這種類型的信箱可讓裝置維護會議日曆、接收會議要求，以及傳送郵件。 您必須啟用登入，才能與 Surface Hub 一起使用。 |
| 2    | 設定信箱屬性 | 信箱必須設定為正確屬性，以在 Surface Hub 上提供最佳的會議體驗。 如需信箱屬性的詳細資訊，請參閱[信箱屬性](exchange-properties-for-surface-hub-device-accounts.md)。 |
| 3    | 請確保已啟用 EWS (Exchange Web Services) ，並停用 MFA (多重要素) 驗證 | Surface Hub 會使用 EWS 來同步處理其日曆。 如果您預設不允許環境中有 EWS，中心信箱必須明確啟用。 當 Surface Hub 在沒有使用者互動的情況下，在背景中登錄 Exchange 時，無法回應任何互動式提示，例如 MFA。 您建立之裝置帳戶必須排除在任何這類驗證需求之外。 否則，Surface Hub 將無法同步處理郵件和行事曆資訊。 |
| 4    | 啟用 Teams 或商務用 Skype 帳戶 (商務用 Skype Server 2015 及更新)  | 商務用 Skype 或 Teams 必須啟用，以使用視像通話、IM 和螢幕分享等會議功能。 有關啟用 Teams 的授權詳細資訊，請參閱 [Teams 會議室授權和](https://docs.microsoft.com/MicrosoftTeams/rooms/rooms-licensing) [Teams 服務描述](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)。 |
| 5    | (選擇性) 停用密碼到期 | 為了簡化管理作業，您可以將裝置帳戶的密碼到期關閉，並允許 Surface Hub 自動循環裝置帳戶密碼。 如需密碼管理的詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。  |
| 6    |  (選擇性) 設定 Exchange 策略以允許 ActiveSync | 在某些內部部署 Exchange Server & Active Directory 部署中，ActiveSync 會用來同步處理裝置帳戶郵件和日曆資訊。 若要進一步設定相關政策，請參閱 [Surface Hub 帳戶的 ActiveSync 策略](apply-activesync-policies-for-surface-hub-device-accounts.md)。 |

> [!NOTE]  
> Surface Hub 裝置帳戶不支援協力廠商聯合身分識別提供者 (Idp) 且必須透過 Active Directory 或 Azure Active Directory 進行驗證。

## <a name="detailed-configuration-steps"></a>詳細設定步驟 

我們建議您使用遠端 Windows PowerShell 設定 Surface Hub 裝置帳戶。 Microsoft 提供 [SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此腳本可協助建立新資源帳戶，或驗證您現有的資源帳戶，以便協助您將這些帳戶轉換為相容的 Surface Hub 裝置帳戶。 如果您願意，您可以從下表選擇一個選項，然後根據您的組織部署遵循詳細的 PowerShell 步驟。

| 組織部署             |  說明                  |        Surface Hub 設定期間使用的格式
|---------------------------------|--------------------------------------|
| [Microsoft 365 (Office 365) ](https://docs.microsoft.com/microsoftteams/rooms/with-office-365) |貴組織的環境完全部署在 Microsoft 365 或 Office 365 上。 | username@domain.com |
| [Exchange 內部部署 (Exchange 內部部署) ](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-on-premises) | 貴組織有各種服務，其中 Exchange Server 託管于內部部署和 Microsoft Teams 線上。 | username@domain.com [Exchange](https://docs.microsoft.com/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication) 中啟用混合式新式驗證時，否則使用 DOMAIN\username |
| [Exchange Online (混合式部署) ](https://docs.microsoft.com/microsoftteams/rooms/with-exchange-online) | 貴組織有各種服務，其中商務用 Skype Server 託管于內部部署和 Exchange Online。 | username@domain.com [在](https://docs.microsoft.com/microsoft-365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication) SfB 中啟用混合式新式驗證時，否則使用 DOMAIN\username |
| [內部部署 (單一樹系)](https://docs.microsoft.com/microsoftteams/rooms/with-skype-for-business-server-2015) | 貴組織有它控制的伺服器，其中 Active Directory、Exchange 和商務用 Skype Server 是託管在單一林環境中。  | DOMAIN\username |
| [內部部署 (多重樹系)](https://docs.microsoft.com/skypeforbusiness/deploy/deploy-clients/multiple-forest-on-premises-deployments) | 貴組織有它所控制的伺服器，Active Directory、Exchange 和商務用 Skype Server 都託管在多林環境中。 | ACCOUNTFOREST\username |


## <a name="account-verification-and-testing"></a>帳戶驗證與測試

您可以使用兩種方法來驗證和測試 Surface Hub 裝置 [ 帳戶：SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) 和 [Surface Hub 硬體診斷應用程式](https://www.microsoft.com/store/apps/9nblggh51f2g)。 帳戶配置腳本可以從您的電腦使用 PowerShell 驗證先前建立的設備帳戶。 Surface Hub 硬體診斷應用程式已安裝在 Surface Hub 上，並且會提供有關登入及通訊失敗的詳細意見反應。 兩者都是要測試新建立裝置帳戶的實用工具，您應該用來確保最佳的帳戶可用性。
