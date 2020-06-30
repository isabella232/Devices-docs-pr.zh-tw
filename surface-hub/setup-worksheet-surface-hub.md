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
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831950"
---
# 設定工作表 (Surface Hub)


當您完成預先設定並準備好開始第一次設定 Microsoft Surface Hub 時，請確定您擁有本節列出的所有資訊。

儘管部分資訊可以用在所有的 Surface Hub 上 (例如 Proxy 資訊或網域認證)，但您還是應該針對需要設定的每個 Surface Hub 填寫一份清單。 根據您決定設定裝置的方式而定，或根據為組織基礎結構設定環境的方式而定，這其中的某些資訊可能是不需要的。

<table>
<tr>
<th>屬性</th>
<th>用途</th>
<th>範例</th>
<th>實際值</th>
</tr>
<tr>
<td>
<p>Proxy 資訊</p>
</td>
<td>
<p>如果您的網路使用 Proxy 進行網路和/或網際網路存取，您就必須提供指令碼或伺服器/連接埠資訊。</p>
</td>
<td>
<p>Proxy 指令碼︰ <code>http://contoso/proxy.pa</code> </br>
- 或 - </br>
伺服器與連接埠資訊︰10.10.10.100，連接埠 80
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>無線網路認證 (使用者名稱與密碼)</p>
</td>
<td>
<p>如果您決定將裝置連線到 Wi-Fi，而且您的無線網路需要使用者認證。</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>裝置帳戶 UPN 或網域\使用者名稱與裝置帳戶密碼</p>
</td>
<td>
<p>這是使用者主體名稱 (UPN) 或網域\使用者名稱，以及裝置帳戶的密碼。 電子郵件、行事曆和商務用 Skype 取決於相容的裝置帳戶。</p>
</td>
<td>
<p> UPN：ConfRoom15@contoso.com，#Passw0rd1 </br>
- 或 - <br> 
網域和使用者名稱︰CONTOSO\ConfRoom15，#Passw0rd1</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>裝置帳戶 Microsoft Exchange Server</p>
</td>
<td>
<p>此為裝置帳戶的 Exchange Server。
電子郵件、行事曆和商務用 Skype 取決於相容的裝置帳戶。
若要讓電子郵件和行事曆能夠運作，裝置帳戶必須具備有效的 Exchange Server。 裝置會試著自動尋找此伺服器。</p>
</td>
<td>
<p>outlook.office365.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>裝置帳戶工作階段初始通訊協定 (SIP) 位址</p>
</td>
<td>
<p>此為裝置帳戶的商務用 Skype SIP 位址。
電子郵件、行事曆和商務用 Skype 取決於相容的裝置帳戶。
若要讓商務用 Skype 能夠運作，裝置帳戶必須具備有效的 SIP 位址。 裝置會試著自動尋找此伺服器。</p>
</td>
<td>
<p>sip：ConfRoom15@contoso.com</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>易記名稱</p>
</td>
<td>
<p>裝置的易記名稱是使用者嘗試以無線方式連線到 Surface Hub 時所看見的廣播名稱。 這個名稱將顯示於 Surface Hub 畫面的顯著位置上。
我們建議您選擇可辨識且唯一的易記名稱，讓使用者在嘗試連線時可以從多個 Surface Hub 中區別出某一個 Surface Hub。</p>
</td>
<td>
<p>Conference Room 15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>裝置名稱</p>
</td>
<td>
<p>裝置名稱是用於加入網域的名稱，以及如果已將裝置註冊到 MDM，您將會在 MDM 提供者中看見的身分識別
您選擇的裝置名稱不得與使用者的 Active Directory 網域中的任何其他裝置相同 (如果您決定將裝置加入網域)。 如果裝置名稱不是唯一的，就不能加入網域。
</p>
</td>
<td>
<p>confroom15</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>如果您正在加入 AZURE AD</b></p>
</td>
</tr>
<tr>
<td>
<p>Azure AD 租用戶使用者認證 (使用者名稱與密碼)</p>
</td>
<td>
<p>如果您決定要讓 Azure Active Directory (Azure AD) 組織中的使用者成為裝置上的系統管理員，則您需要加入 Azure AD。
若要加入 Azure AD，您需要有效的使用者認證。</p>
</td>
<td>
<p>admin1@contoso.com, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>如果您正在加入網域</b></p>
</td>
</tr>
<tr>
<td>
<p>要加入的網域</p>
</td>
<td>
<p>這是您需要加入的網域，讓您選擇的安全性群組可做為裝置的系統管理員。
您需要完整網域名稱 (FQDN)。</p>
</td>
<td>
<p>contoso (簡短名稱) 或 contoso.corp.com (FQDN)</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>網域帳戶認證 (使用者名稱與密碼)</p>
</td>
<td>
<p>除非您提供足夠的帳戶認證來加入網域，否則無法加入網域。 當您提供要加入的網域和要加入網域的認證之後，您選擇的安全性群組接著就會變更裝置上的設定。</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p>系統管理員安全性群組別名</p>
</td>
<td>
<p>這是 Active Directory (AD) 中的安全性群組；這個安全性群組的所有成員都能變更裝置上的設定。</p>
</td>
<td>
<p>SurfaceHubAdmins</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>如果您使用本機系統管理員</b></p>
</td>
</tr>
<tr>
<td>
<p>本機系統管理員帳戶認證 (使用者名稱與密碼)</p>
</td>
<td>
<p>如果您決定不加入 AD 網域或 Azure AD，您可以在裝置上建立本機系統管理員帳戶。</p>
</td>
<td>
<p>admin1, #MyPassw0rd</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b>如果您需要安裝憑證或應用程式</b></p>
</td>
</tr>
<tr>
<td>
<p>USB 磁碟機</p>
</td>
<td>
<p>如果您在初次執行之前知道您想要安裝憑證或跨平台應用程式，請依照<a href="provisioning-packages-for-certificates-surface-hub.md">建立佈建套件</a>中的步驟執行。 您的佈建套件將建立於 USB 磁碟機上。</p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 





