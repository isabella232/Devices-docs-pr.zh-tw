---
title: 針對 Microsoft Surface Hub 準備您的環境
description: 此頁面說明設定及管理 Surface Hub v1 或 Surface Hub 2S 的相依性。
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: 準備環境、Surface Hub、裝置帳戶、網路可用性、M365 端點、Intune
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 33724f84171cb9485bd20ff5c437ad8b3f60a463
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442121"
---
# <a name="prepare-your-environment-for-microsoft-surface-hub"></a>針對 Microsoft Surface Hub 準備您的環境

 
此頁面說明設定及管理 Surface Hub v1 或 Surface Hub 2S 的相依性。
 

## <a name="infrastructure-dependencies"></a>基礎結構相依性

檢閱這些相依性，以確定 Surface Hub 功能可在您的 IT 環境中運作。
 
 
| 相依性                                                                                                                                  | 說明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               | 深入了解                                                                                                                                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| 內部部署服務和 Active Directory 或 M365                                                                                           |  Surface Hub 使用 Active Directory 或 Azure AD 帳戶 (稱為裝置帳戶 **) 存取** Exchange 和 Teams (或商務用 Skype) 服務。 Surface Hub 必須能夠連線到 Active Directory 網域控制站或 Azure AD 租用戶來驗證裝置帳戶的認證，以及存取諸如裝置帳戶的顯示名稱、別名、Exchange 伺服器與工作階段初始通訊協定 (SIP) 位址等資訊。  <br><br>**注意：Surface Hubs 可與 Microsoft Teams、商務用 Skype Server 2019、商務用 Skype Server 2015 或商務用 Skype Online 合作。 不支援較早的平臺 ，例如 Lync Server 2013。 GCC High 或 DoD 環境不支援 Surface Hub。**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         | [Microsoft 365 端點](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-endpoints) <br> <br> [建立和測試裝置帳戶](create-and-test-a-device-account-surface-hub.md)                                                                                                                                                    |
| Windows Update、Store 和診斷                                                                                                       | 需要存取 Windows Update 或商務用 Windows Update，才能使用作業系統功能和品質更新維護 Surface Hub。 若要維護應用程式，必須存取 Microsoft Store。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | [管理適用於 Windows 10 企業版 (版本 20H2) 的連線端點](https://docs.microsoft.com/windows/privacy/manage-windows-20h2-endpoints)<br> <br>[在 Surface Hub 上管理 Windows 更新](manage-windows-updates-for-surface-hub.md) |
| 行動裝置管理 (MDM) 解決方案 (Microsoft Intune、Microsoft 端點組組管理員或支援的協力廠商 MDM 提供者)  | 如果您想要從遠端一次就套用設定或安裝應用程式到多個裝置，您必須設定 MDM 解決方案，並將裝置註冊到該解決方案。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | [Microsoft Intune 的網路端點](https://docs.microsoft.com/mem/intune/fundamentals/intune-endpoints)<br> <br>[使用 MDM 提供者管理設定](manage-settings-with-mdm-for-surface-hub.md)                                  |
| Azure 監視器                                                                                                                               | Azure 監視器可用來監控 Surface Hub 裝置的健康情況。 <br><br>**注意：Surface Hub 目前不支援使用 Proxy 伺服器與 Azure 監視器使用的記錄分析服務通訊。**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  | [記錄分析端點](https://docs.microsoft.com/azure/azure-monitor/agents/log-analytics-agent#firewall-requirements)<br> <br> [使用 Azure 監視器監控 Surface Hub 以追蹤其健康情況](https://docs.microsoft.com/azure/azure-monitor/insights/surface-hubs)。                                                                                                                                               |
| 網路存取                                                                                                                              |  Surface Hubs 支援有線或無線網路 (有線連接是) 。 <br> <br>**802.1X 驗證**<br>在 Windows 10 小組 20H2 中，雖然有線和無線網路的 802.1X 驗證預設為啟用，但您必須確保 Surface Hub 也安裝了 802.1x 網路設定檔和驗證憑證。 如果您使用 Intune 或其他行動裝置管理解決方案管理 Surface [Hub，您可以使用 ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp)傳遞憑證。 否則，您可以 [建立一個設定套件](provisioning-packages-for-surface-hub.md) ，並在第一次執行安裝期間安裝，或是使用設定應用程式。 當憑證被使用時，802.1X 驗證會自動開始。<br> <br>**動態 IP**<br>Surface Hub 無法配置為使用靜態 IP。 他們必須透過 DHCP 指派 IP 位址。<br> <br>**連接埠**<br>Surface Hub 需要下列開啟埠：<br><br>HTTPS：443<br>HTTP：80<br>NTP：123 | [啟用 802.1x 有線驗證](enable-8021x-wired-authentication.md)  <br><br>[建立 Surface Hub 2S 的佈建套件](surface-hub-2s-deploy.md)                                                                                 |

## <a name="device-affiliation"></a>裝置關聯

使用裝置關聯管理使用者對 Surface Hub 上的設定應用程式的存取權。 使用在 Surface Hub (上的 Windows 10 小組作業系統) ，只有授權使用者可以使用設定應用程式來調整設定。 由於選擇關聯可能會影響功能可用性，請妥善規劃以確保使用者可以如預期存取功能。
 
 
> [!NOTE]
> 在 OOBE 設定的初始開箱即用體驗期間， (裝置) 關聯。 如果您需要重設裝置關聯，您必須重複 OOBE 設定。
 

### <a name="no-affiliation"></a>沒有關聯

沒有任何從屬關係，就像是在每個 Surface Hub 上擁有不同本地系統管理員帳戶的工作組中擁有 Surface Hub。 如果您選擇不加入，您必須將 [BitLocker Key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)儲存到 USB 拇指磁碟機。 您仍然可以使用 Intune 註冊裝置;不過，只有當地系統管理員可以使用在 OOBE 期間設定的帳號憑證存取設定應用程式。 您可以從設定應用程式變更系統管理員帳戶密碼。
 

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

如果您將 Surface Hub 與內部部署 Active Directory 網域服務聯屬，您必須使用網域上的安全性群組來管理對 Settings App 的存取權。 這有助於確保所有安全性群組成員都有權變更 Surface Hub 上的設定。 另請注意：當您內部部署 Active Directory 網域服務的 Surface Hub 關係企業時，BitLocker 金鑰可以儲存于 Active Directory 架構中。 詳細資訊，請參閱為 [貴組織準備 BitLocker：規劃與政策](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。
 
貴組織的受根信任 CAs 會推送到 Surface Hub 中的同一個容器，這表示您不需要使用資源調配套件進行導入。
 
您仍可使用 Intune 註冊裝置，以集中管理 Surface Hub 上的設定。
 

### <a name="azure-active-directory"></a>Azure Active Directory

當您選擇將 Surface Hub 與 Azure Active Directory (Azure AD) 關聯時，全域系統管理員安全性群組的任何使用者都可以登錄 Surface Hub 上的設定應用程式。 您也可以設定非全域系統管理員帳戶，將許可權限制為管理 Surface Hub 上的設定應用程式。 這可讓您只限制 Surface Hub 的系統管理員許可權，並防止整個 Azure AD 網域可能不想要的系統管理員存取權。

如果您為貴組織啟用 [Intune 自動](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment) 註冊，Surface Hub 會自動使用 Intune 註冊。 裝置 BitLocker 金鑰會自動儲存于 Azure AD 中。

若要深入瞭解使用 Azure AD 管理 Surface Hub，請參閱：

- [系統管理員群組管理](admin-group-management-for-surface-hub.md)
- [在 Surface Hub 上設定非全域系統管理員帳戶](surface-hub-2s-nonglobal-admin.md)

### <a name="review-and-complete-surface-hub-setup-worksheet-optional"></a>檢閱並完成 Surface Hub 設定工作表 (選擇性)

當您完成 Surface Hub 的初次執行程式時，還需要提供一些資訊。 設定工作表摘要說明該資訊，並提供完成初次執行程式時所需的環境特定資訊的清單。 如需詳細資訊，請參閱[設定工作表](setup-worksheet-surface-hub.md)。

