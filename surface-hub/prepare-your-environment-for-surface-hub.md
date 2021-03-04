---
title: '準備您的環境以使用 Microsoft Surface Hub (v1) '
description: 本節包含準備您環境時所需步驟的概觀，讓您能夠使用所有的 Microsoft Surface Hub 功能。
ms.assetid: 336A206C-5893-413E-A270-61BFF3DF7DA9
ms.reviewer: ''
manager: laurawi
keywords: 準備環境, Surface Hub 的功能, 建立和測試裝置帳戶, 檢查網路可用性
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/03/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
ms.openlocfilehash: 075724153709fd86ccc00ef98ad532bf45557714
ms.sourcegitcommit: 5c904229a0257297be7f724c264e484d2c4b5168
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387443"
---
# <a name="prepare-your-environment-for-microsoft-surface-hub-v1"></a>準備您的環境以使用 Microsoft Surface Hub (v1) 


本節包含安裝程式相依性與安裝程序的概觀。 請查閱這些資訊，協助準備您的環境，並收集設定 Surface Hub 所需的資訊。


## <a name="review-infrastructure-dependencies"></a>檢閱基礎結構相依性
檢閱這些相依性，以確定 Surface Hub 功能可在您的 IT 環境中運作。

| 相依性        | 用途           |
|-------------|------------------|
| Active Directory 或 Azure Active Directory (Azure AD) | <p>Surface Hub 使用 Active Directory 或 Azure AD 帳戶 (稱為**裝置帳戶**) 來存取 Exchange 與商務用 Skype 服務。 Surface Hub 必須能夠連線到 Active Directory 網域控制站或 Azure AD 租用戶來驗證裝置帳戶的認證，以及存取諸如裝置帳戶的顯示名稱、別名、Exchange 伺服器與工作階段初始通訊協定 (SIP) 位址等資訊。</p>您也可以將 Surface Hub 加入到網域或加入到 Azure AD，以允許一組授權的使用者設定 Surface Hub 上的設定。 |
| Exchange (Exchange 2013 或更新版本或 Exchange Online) 與 Exchange ActiveSync | <p>Exchange 可用於啟用電子郵件和行事曆功能，而且也可以讓使用裝置的使用者將會議邀請傳送到 Surface Hub，以啟用單一碰觸式會議加入功能。</p>ActiveSync 可用來將裝置帳戶的行事曆和電子郵件同步處理到 Surface Hub。 如果裝置無法使用 ActiveSync，將不會在歡迎畫面中顯示會議，而且不會啟用加入會議與以電子郵件傳送白板的功能。 |
| 商務用 Skype (Lync Server 2013 或更新版本，或商務用 Skype Online)  | 商務用 Skype 可用於各種不同的會議功能，例如視訊通話、傳送即時訊息和螢幕畫面分享。|
| 行動裝置管理 (Microsoft intune) MDM (解決方案、Microsoft 端點組組管理員或支援的協力廠商 MDM 提供者)  | 如果您想要從遠端一次就套用設定或安裝應用程式到多個裝置，您必須設定 MDM 解決方案，並將裝置註冊到該解決方案。 如需詳細資訊，請參閱[使用 MDM 提供者管理設定](manage-settings-with-mdm-for-surface-hub.md)。 |
|Azure 監視器   | Azure 監視器是用來監控 Surface Hub 裝置的健康情況。 請參閱 [使用 Azure 監視器監控 Surface Hub 以追蹤其健康情況](https://docs.microsoft.com/azure/azure-monitor/insights/surface-hubs)。 
| 網路與網際網路存取   | 為正常運作，Surface Hub 必須能夠存取有線或無線網路。 整體而言，建議使用有線連線。 有線和無線連線皆支援 802.1x 驗證。</br></br></br>**802.1X 驗證：** 在 Windows 10 版本 1703 中，適用於有線和無線連線的 802.1X 驗證會在 Surface Hub 中預設啟用。 如果您的組織未使用 802.1X 驗證，並不需要設定，且 Surface Hub 仍會繼續正常運作。 如果您使用 802.1X 驗證，您必須確定驗證憑證已安裝在 Surface Hub 上。 您可以使用 MDM 中的 [ClientCertificateInstall CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/clientcertificateinstall-csp) 將憑證傳送到 Surface Hub，或者可以在初次執行或透過「設定」應用程式[建立佈建套件](provisioning-packages-for-surface-hub.md)並安裝起來。 將憑證套用到 Surface Hub 之後，802.1X 驗證將會開始自動運作。</br><br>**注意：** 如需在 Surface Hub 上啟用 802.1X 有線驗證的詳細資訊，請參閱[啟用 802.1x 有線驗證](enable-8021x-wired-authentication.md)。</br></br>**動態 IP：** 無法設定 Surface Hub 使用靜態 IP。 它必須使用 DHCP 來指派 IP 位址。</br></br>**Proxy 伺服器：** 如果您的拓撲需要連線到 Proxy 伺服器以連線網際網路服務，您可以在初次執行期間或在 \[設定\] 中設定它。 Proxy 認證會儲存在 Surface Hub 工作階段期間之間，且只需設定一次。 |

此外，請注意 Surface Hub 需要下列開放連接埠︰
- HTTPS：443
- HTTP：80
- NTP：123

如果您將 Surface Hub 與商務用 Skype 一起使用，則需要開啟其他埠。 請遵循下列指引：
- 如果您使用商務用 Skype Online，請參閱 [Office 365 IP URL 和 IP 位址範圍](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US)。
- 如果您使用商務用 Skype Server，請參閱 [商務用 Skype Server：內部伺服器的埠和通訊協定](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols)。 
- 如果您使用混合式商務用 Skype Online 和商務用 Skype Server，則需要從 [Office 365 IP URL](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US) 和 IP 位址範圍以及商務用 Skype [Server：](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/network-requirements/ports-and-protocols?toc=/SkypeForBusiness/toc.json&bc=/SkypeForBusiness/breadcrumb/toc.json)內部伺服器的埠和通訊協定開啟所有已記載的埠。

Microsoft 會收集診斷資料以協助改善您的 Surface Hub 體驗。 新增這些網站新增到您的允許清單︰
- 診斷資料用戶端端點： `https://vortex.data.microsoft.com/`
- 診斷資料設定端點： `https://settings.data.microsoft.com/`

### <a name="proxy-configuration"></a>Proxy 設定

如果您的組織會限制您網路上的電腦連線到網際網路，則針對要使用商務用 Microsoft Store 的裝置需要一組可供使用的 URL。 部分商務用 Store 功能會使用 Microsoft Store 應用程式和 Microsoft Store 服務。 使用商務用 Store 的裝置 – 無論是取得、安裝或更新 app – 都需要存取這些 URL。 如果您使用 Proxy 伺服器封鎖流量，您的設定需要允許這些 URL：

- login.live.com
- login.windows.net
- account.live.com
- clientconfig.passport.net
- windowsphone.com
- *.wns.windows.com
- *.microsoft.com
- www.msftncsi.com (在 Windows 10 版本 1607 之前)
- www.msftconnecttest.com/connecttest.txt (從 Windows 10 版本 1607 開始會取代 www.msftncsi.com)


## <a name="work-with-other-admins"></a>與其他系統管理員合作

Surface Hub 可和幾個不同的產品與服務互動。 根據您組織的規模，您的環境中可能會有多人支援不同的產品。 您會想要在 Surface Hub 部署的規劃和準備中，納入管理 Exchange、Active Directory (或 Azure Active Directory)、行動裝置管理 (MDM) 的人員與網路資源。 


## <a name="create-and-verify-device-account"></a>建立及驗證裝置帳戶

裝置帳戶是 Exchange 資源帳戶，Surface Hub 使用它來顯示其會議行事曆、加入商務用 Skype 通話、傳送電子郵件，及 (選擇性) 對 Exchange 驗證。 如需詳細資訊，請參閱[建立和測試裝置帳戶](create-and-test-a-device-account-surface-hub.md)。

建立您的裝置帳戶之後，若要確定已正確設定，請執行 Surface Hub 裝置帳戶驗證 PowerShell 指令碼。 如需詳細資訊，請參閱本指南稍後的[適用於 Surface Hub 的 PowerShell 指令碼](appendix-a-powershell-scripts-for-surface-hub.md)。 

 

## <a name="prepare-for-first-run-program"></a>準備初次執行程式 
開始[初次執行程式](first-run-program-surface-hub.md)之前，還需考慮其他幾個項目。  

### <a name="create-provisioning-packages-optional"></a>建立佈建套件 (選擇性)
您可以使用佈建套件新增憑證、自訂設定及安裝應用程式。 如需詳細資訊，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。 您可以[在初次執行時安裝佈建套件](first-run-program-surface-hub.md#first-page)。

### <a name="set-up-admin-groups"></a>設定系統管理員群組
在個別裝置上使用 [設定] 應用程式，可各自設定其上的 Surface Hub。 若要防止未經授權的使用者變更設定，[設定] 應用程式需要系統管理員認證才能開啟應用程式。 如需有關設定及管理系統管理員群組的詳細資訊，請參閱[系統管理員群組管理](admin-group-management-for-surface-hub.md)。 您將會[在初次執行時設定裝置的系統管理員](first-run-program-surface-hub.md#setup-admins)。

### <a name="review-and-complete-surface-hub-setup-worksheet-optional"></a>檢閱並完成 Surface Hub 設定工作表 (選擇性)
當您完成 Surface Hub 的初次執行程式時，還需要提供一些資訊。 設定工作表摘要說明該資訊，並提供完成初次執行程式時所需的環境特定資訊的清單。 如需詳細資訊，請參閱[設定工作表](setup-worksheet-surface-hub.md)。


## <a name="in-this-section"></a>本節內容

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">主題</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="create-and-test-a-device-account-surface-hub.md" data-raw-source="[Create and test a device account](create-and-test-a-device-account-surface-hub.md)">建立和測試裝置帳戶</a></p></td>
<td align="left"><p>本主題介紹如何建立和測試 Surface Hub 用來與 Skype 通訊的裝置帳戶。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="provisioning-packages-for-certificates-surface-hub.md" data-raw-source="[Create provisioning packages](provisioning-packages-for-certificates-surface-hub.md)">建立佈建套件</a></p></td>
<td align="left"><p>針對 Windows 10，您可以透過佈建套件來設定使用登錄或內容服務平台 (CSP) 的設定。 您也可以在初次執行期間，使用佈建來新增憑證。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="admin-group-management-for-surface-hub.md" data-raw-source="[Admin group management](admin-group-management-for-surface-hub.md)">系統管理員群組管理</a></p></td>
<td align="left"><p>您可以藉由在裝置上開啟 \[設定\] 應用程式，個別設定每一個 Surface Hub。 不過，為了防止不是系統管理員的使用者變更設定，\[設定\] 應用程式需要系統管理員認證，才能開啟應用程式和變更設定。</p>
<p>\[設定\] 應用程式需要本機系統管理員認證，才能開啟應用程式。</p></td>
</tr>
</tbody>
</table>

## <a name="more-information"></a>更多資訊

- [部落格文章：Surface Hub 和商務用 Skype 信任網域清單](https://blogs.technet.microsoft.com/y0av/2017/10/25/95/)
- [部落格文章：多網域環境中的 Surface Hub](https://blogs.technet.microsoft.com/y0av/2017/11/08/11/)
- [部落格文章：為 Surface Hub 設定 Proxy](https://blogs.technet.microsoft.com/y0av/2017/12/03/7/)

 

 





