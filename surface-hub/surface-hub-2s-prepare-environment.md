---
title: 針對 Surface Hub 2S 準備您的環境
description: 瞭解準備 Surface Hub 2S 環境所需的工作。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385141"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a>針對 Surface Hub 2S 準備您的環境

## <a name="office-365-readiness"></a>Office 365 就緒

如果您使用 Exchange Online、商務用 Skype Online、Microsoft Teams 或 Microsoft Whiteboard，並打算使用 Intune 管理 Surface Hub 2S，請先審查 [端點的 Office 365 需求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。

Office 365 端點可透過防火牆直接傳送所有信任的 Office 365 網路要求，並避開所有其他封包層級的檢查或處理，協助優化您的網路。 這項功能可減少延遲和您的周邊容量需求。

Microsoft 會以新功能定期更新 Office 365 服務，可能會變更必要的埠、URL 和 IP 位址。 若要評估、設定及隨時更新變更，請訂閱 [Office 365 IP 位址和 URL Web 服務](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。

> [!NOTE]
> Surface Hub 可與 Microsoft Teams、商務用 Skype Server 2019、商務用 Skype Server 2015 或商務用 Skype Online 合作。
不支援較早的平臺，例如 Lync Server 2013。 Surface Hub 不支援GCC-High DoD 環境。


## <a name="device-affiliation"></a>裝置關聯

使用裝置關聯來管理使用者存取 Surface Hub 2S 上的設定應用程式。
使用在 Surface Hub 2S (上的 Windows 10 小組作業系統) ，只有獲得授權的使用者可以使用設定應用程式來調整設定。 由於選擇關聯可能會影響功能可用性，請妥善規劃以確保使用者可以如預期存取功能。

> [!NOTE]
> 在設定 OOBE 時，您 (裝置) 關聯。 如果您需要重設裝置關聯，您必須重複 OOBE 設定。

## <a name="no-affiliation"></a>無關聯

沒有關聯性就像是將 Surface Hub 2S 放在工作組中，在每個 Surface Hub 2S 上使用不同的本地系統管理員帳戶。 如果您選擇不關聯，您必須將 [BitLocker 金鑰](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)儲存到 USB 記憶磁碟機。 您仍然可以使用 Intune 註冊裝置;不過，只有本地系統管理員可以使用 OOBE 期間設定的帳號憑證存取設定應用程式。 您可以變更設定應用程式的系統管理員帳戶密碼。

## <a name="active-directory-domain-services"></a>Active Directory Domain Services

如果您將 Surface Hub 2S 與內部部署 Active Directory 網域服務關聯，您必須使用網域上的安全性群組來管理設定應用程式的存取權。 這有助於確保所有安全性群組成員都有權變更 Surface Hub 2S 上的設定。 另請注意下列事項：

- 當您內部部署 Active Directory 網域服務的 Surface Hub 2S 關係企業時，BitLocker 金鑰可以儲存于 Active Directory 架構中。 詳細資訊請參閱為 [貴組織準備 BitLocker：規劃和政策](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。

- 貴組織的根信任 CAS 會推送到 Surface Hub 2S 中的同一個容器，這表示您不需要使用部署套件來將它們進行導入。

- 您仍然可以使用 Intune 註冊裝置，以集中管理 Surface Hub 2S 上的設定。

## <a name="azure-active-directory"></a>Azure Active Directory

當您選擇將 Surface Hub 2S 與 Azure Active Directory (Azure AD) 進行連結時，全域系統管理員安全性群組的任何使用者都可以在 Surface Hub 2S 上登錄設定應用程式。 您也可以設定非全域系統管理員帳戶，將許可權限制為管理 Surface Hub 2S 上的設定應用程式。 這可讓您只將 Surface Hub 2S 的系統管理員許可權範圍範圍，並防止整個 Azure AD 網域可能不需要的系統管理員存取權。 

如果您為貴組織啟用 Intune 自動註冊，Surface Hub 2S 會自動向 Intune 註冊。 裝置 BitLocker 金鑰會自動儲存于 Azure AD 中。 

若要深入瞭解使用 Azure AD 管理 Surface Hub，請參閱： 

 - [系統管理員群組管理](admin-group-management-for-surface-hub.md)
 - [在 Surface Hub 2S 上設定非全域系統管理員帳戶](surface-hub-2s-nonglobal-admin.md)

