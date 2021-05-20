---
title: 設定工作表 (Surface Hub)
description: 當您完成預先設定並準備好開始第一次設定 Microsoft Surface Hub 時，請確定您擁有本節列出的所有資訊。
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: 設定工作表, 預先設定, 第一次設定
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/14/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: c0bba196aa71c751d092b4e1f2f6005d653b2f69
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576713"
---
# <a name="setup-worksheet-surface-hub"></a>設定工作表 (Surface Hub)

當您完成預先設定並準備好開始第一次設定 Microsoft Surface Hub 時，請確定您擁有本節列出的所有資訊。

儘管部分資訊可以用在所有的 Surface Hub 上 (例如 Proxy 資訊或網域認證)，但您還是應該針對需要設定的每個 Surface Hub 填寫一份清單。 根據您決定設定裝置的方式而定，或根據為組織基礎結構設定環境的方式而定，這其中的某些資訊可能是不需要的。

完成後，請檢閱 [下方張貼部署檢查](#post-deployment-checklist) 清單。

| 屬性                                                          | 用途                                                                                                                                                                                                                                                                                                                                                           | 範例                                                                                                                               | 深入了解                                                                                                                                                                                                                                                              |
| ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Proxy 資訊                                                 | 如果您使用 Proxy 進行網路或網際網路存取，則必須提供腳本或伺服器/埠資訊。                                                                                                                                                                                                                                                                        |  Proxy 腳本： http://contoso/proxy.pac <br><br>或：<br><br>伺服器與連接埠資訊︰10.10.10.100，連接埠 80                                  | [使用部署套件設定 Proxy。](surface-hub-2s-deploy.md)                                                                                                                           |
| 無線網路認證 (使用者名稱與密碼)              | 如果將您的裝置連接到 Wi-Fi，而您的無線網路需要使用者認證。                                                                                                                                                                                                                                                                                           | admin1@contoso.com, #MyPassw0rd                                                                                                       | [無線網路管理](wireless-network-management-for-surface-hub.md)                                                                                                                                                 |
| 裝置帳戶 UPN 或網域\使用者名稱與裝置帳戶密碼 | 這是使用者主體名稱 (UPN) 或網域\使用者名稱，以及裝置帳戶的密碼。 郵件、日曆、Microsoft Teams和商務用 Skype取決於相容的裝置帳戶。                                                                                                                                                                            | UPN：ConfRoom15@contoso.com，#Passw0rd1 <br><br>或：<br><br>網域和使用者名稱︰CONTOSO\ConfRoom15，#Passw0rd1                        | [建立和測試裝置帳戶](create-and-test-a-device-account-surface-hub.md) |
| 信箱屬性                                                | 信箱必須設定為正確屬性，以在 Surface Hub 上提供最佳的會議體驗。                                                                                                                                                                                                                                                                | 請參閱[Microsoft Exchange屬性](exchange-properties-for-surface-hub-device-accounts.md) |                                                                                                                                        |
| 裝置帳戶信箱的 EWS URL                              | 此為裝置帳戶的 Exchange Server。 郵件、日曆、Microsoft Teams和商務用 Skype取決於相容的裝置帳戶。 若要讓電子郵件和行事曆能夠運作，裝置帳戶必須具備有效的 Exchange Server。 裝置會試著自動尋找此伺服器。                                                                                               | https://outlook.office365.com/EWS/exchange.asmx                                                                                                                 | [建立和測試裝置帳戶](create-and-test-a-device-account-surface-hub.md)<br><br>[Microsoft Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)      |
| 裝置帳戶工作階段初始通訊協定 (SIP) 位址          | 這是裝置帳戶的 SIP 位址。 郵件、日曆、Microsoft Teams和商務用 Skype取決於相容的裝置帳戶。 若要讓Skype小組或企業使用者使用，裝置帳戶必須擁有有效的 SIP 位址 裝置會嘗試自動尋找此位址。                                                                                              | sip：ConfRoom15@contoso.com                                                                                                           |                                                                                                                                                                                                                                                                         |
| 裝置帳戶密碼                                           | 若要簡化管理，您可以停用裝置帳戶的密碼到期，或允許Surface Hub自動旋轉裝置帳戶密碼。 <br> <br>**注意：** 如果以網域\使用者名稱格式新增帳戶，在初始設定期間，將 Hub 與內部部署 Active Directory 關聯。 如果以 username@domain.com 格式新增帳戶，在初始設定Azure Active Directory將 Hub 與帳戶關聯。 否則，密碼循環使用將無法運作。                                                                                                                                                                                                                 |                                                                                                                                       | [密碼管理](password-management-for-surface-hub-device-accounts.md)                                                                                                                                                 |
| ExchangeWeb Services (EWS)                                        | 啟用 EWS。 Surface Hub EWS 來同步其日曆。                                                                                                                                                                                                                                                                                                                          |                                                                                                                                       | [Surface Hub 上的新式驗證](surface-hub-modern-auth.md)                                                                                                                                                            |
| 多重要素驗證                                        | 停用裝置帳戶上的多重要素驗證。 當Surface Hub在背景Exchange使用者互動時，無法回應任何互動式提示，例如多重要素驗證。                                                                                                                                                                         |                                                                                                                                       |                                                                                                                                                                                                                                                                         |
| MDM 註冊詳細資料                                            | 如果您想要手動將裝置註冊到 MDM，您必須擁有適用于 MDM 提供者和註冊 URL 的使用者認證。 裝置會嘗試自動尋找註冊 URL。 | manage.microsoft.com | [使用 MDM 提供者管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md) |
| 易記名稱                                                     | 裝置的易記名稱是使用者嘗試以無線方式連線到 Surface Hub 時所看見的廣播名稱。 這個名稱將顯示於 Surface Hub 畫面的顯著位置上。 我們建議您選擇可辨識且唯一的易記名稱，讓使用者在嘗試連線時可以從多個 Surface Hub 中區別出某一個 Surface Hub。             | Conference Room 15                                                                                                                    | [第一次設定Surface Hub](surface-hub-2s-setup.md)                                                                                                                                                                   |
| 裝置名稱                                                       | 裝置名稱是用於加入網域的名稱，以及如果已將裝置註冊到 MDM，您將會在 MDM 提供者中看見的身分識別 如果您選擇的裝置名稱不得與 Active Directory 網域中任何其他裝置的名稱相同 (如果您決定將網域加入裝置) 。 沒有唯一名稱，裝置就無法加入網域。  | confroom15                                                                                                                            | [第一次設定Surface Hub](surface-hub-2s-setup.md)                                                                                                                                                                   |
| Teams 應用程式模式                                                    | - 模式 0 - 商務用 Skype排定Microsoft Teams會議的功能。<br>- 模式 1 - Microsoft Teams排定商務用 Skype會議的功能。<br>- 模式 2 - Microsoft Teams模式                                                                                                                                                         |                                                                                                                                       | [變更預設商務通訊平臺](manage-settings-with-mdm-for-surface-hub.md)                                                                            |

## <a name="device-affiliation"></a>裝置關聯

使用裝置關聯管理使用者對 設定 應用程式Surface Hub。 使用Windows 10 團隊版作業系統 (，Surface Hub) 授權使用者才能使用應用程式設定設定。 由於選擇關聯可能會影響功能可用性，請妥善規劃以確保使用者可以如預期存取功能。

> [!NOTE]
> 在 OOBE 設定的初始開箱即用體驗期間， (裝置) 關聯。 如果您需要重設裝置關聯，您必須重複 OOBE 設定。

### <a name="if-youre-joining-azure-ad"></a>如果您要加入 Azure AD

| 屬性                                                 | 用途                                                                                                                                                                                                                                                    | 範例                         | 深入了解                                                                                                                        |
| -------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| Azure AD 租用戶使用者認證 (使用者名稱與密碼) | 如果您決定讓 Azure Active Directory (Azure AD) 中的人員成為裝置上的系統管理員，則您必須將 Surface Hub加入 Azure AD。 若要將帳戶加入 Azure AD，您必須為租使用者中的帳戶提供有效的認證。                                                               | admin1@contoso.com, #MyPassw0rd | [系統管理員群組管理](admin-group-management-for-surface-hub.md)                     |
| 非全域系統管理員帳戶                                | 針對Surface Hub Azure AD 的裝置，您可以將系統管理許可權限制為管理 設定 應用程式Surface Hub。 這可讓您將系統管理許可權範圍Surface Hub，並防止可能不需要的系統管理員存取整個 Azure AD 網域。 |                                 | [在 Surface Hub 上設定非全域系統管理員帳戶](surface-hub-2s-nonglobal-admin.md) |

### <a name="if-youre-joining-a-domain"></a>如果您要加入網域

| 屬性                                           | 用途                                                                                                                                                                                                                        | 範例                                         |
| -------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------- |
| 要加入的網域                                     | 這是您需要加入的網域，讓您選擇的安全性群組可做為裝置的系統管理員。 您需要完整網域名稱 (FQDN)。                                                                          | contoso (簡短名稱) 或 contoso.corp.com (FQDN) |
| 網域帳戶認證 (使用者名稱與密碼) | 除非您提供足夠的帳戶認證來加入網域，否則無法加入網域。 當您提供要加入的網域和要加入網域的認證之後，您選擇的安全性群組接著就會變更裝置上的設定。 | admin1, #MyPassw0rd                             |
| 系統管理員安全性群組別名                         | 這是 Active Directory (AD) 中的安全性群組；這個安全性群組的所有成員都能變更裝置上的設定。                                                                                                                | SurfaceHubAdmins                                |

### <a name="if-youre-using-a-local-admin"></a>如果您使用的是本地系統管理員

| 屬性                                                | 用途                                                                                   | 範例             |
| ------------------------------------------------------- | ------------------------------------------------------------------------------------------------------- | ------------------- |
| 本機系統管理員帳戶認證 (使用者名稱與密碼) | 如果您決定不加入 AD 網域或 Azure AD，您可以在裝置上建立本機系統管理員帳戶。 | admin1, #MyPassw0rd |

### <a name="if-you-need-to-install-certificates-or-apps"></a>如果您需要安裝憑證或應用程式

| 屬性  | 用途                                                                                                                                                                                                                                                                                        |
| --------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| USB 磁碟機 | 如果您在初次執行之前知道您想要安裝憑證或跨平台應用程式，請依照[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)中的步驟執行。 您的佈建套件將建立於 USB 磁碟機上。 |

## <a name="post-deployment-checklist"></a>部署後檢查清單

| 檢查                                      | 回應                                                                                                                                                                                                          |
| ------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **裝置帳戶同步**                 | ☐是 <br><br>☐否                                                                                                                                                                                                |
| **Bitlocker 鍵**                          | ☐儲存至檔案 (沒有關聯)  <br><br>☐ Active Directory 中儲存 (AD 關聯)  <br><br>☐ Azure AD 中儲存 (Azure AD 關聯)                                                                           |
| **裝置作業系統更新**                      | ☐完成                                                                                                                                                                                                       |
| **Windows儲存更新**                  | ☐自動 <br><br>☐手冊                                                                                                                                                                                      |
| **Microsoft Teams排定的會議**      | ☐收到確認電子郵件 <br><br>☐會議會顯示在開始畫面上 <br><br>☐觸控連接函數 <br><br>☐能夠加入音訊 <br><br>☐可以加入影片 <br><br>☐共用畫面               |
| **商務用 Skype排定的會議**   | ☐收到確認電子郵件<br>☐會議會顯示在開始畫面上<br>☐觸控連接功能<br>☐能夠加入音訊<br>☐可以加入影片<br>☐共用畫面<br>☐傳送/接收 IM |
| **已受邀時排定的會議** | ☐拒絕會議                                                                                                                                                                                                |
| **Microsoft Teams臨時會議**         | ☐邀請其他使用者工作 <br><br>☐能夠加入音訊 <br><br>☐可以加入影片 <br><br>☐共用畫面                                                                                                |
| **Microsoft Whiteboard**                   | ☐歡迎啟動 / 開始畫面 <br><br>☐從 Microsoft Teams                                                                                                                                        |
| **來電Teams/Skype來電**              | ☐能夠加入音訊<br>☐可以加入影片<br>☐共用畫面<br>☐只能傳送/接收 IM (商務用 Skype或)                                                                                      |
| **傳入即時視音訊流**            | ☐最多 2 (商務用 Skype) <br>☐最多 4 (Microsoft Teams)                                                                                                                                                  |
| **Microsoft Teams模式 0 行為**        | ☐ 商務用 Skype歡迎/開始畫面上的磚<br>☐可以加入已排定商務用 Skype會議 (Skype UI) <br>☐可以加入已排定Teams會議 (Teams UI)                                                 |
| **Microsoft Teams模式 1 行為**        | ☐ Teams歡迎/開始畫面上的磚<br>☐可以加入已排定商務用 Skype會議 (Skype UI) <br>☐可以加入已排定Teams會議 (Teams UI)                                                              |
| **Microsoft Teams模式 2 行為**        | ☐ Teams歡迎 / 開始畫面上的磚<br>☐可以加入排定Teams會議<br>☐無法加入商務用 Skype會議                                                                                       |
