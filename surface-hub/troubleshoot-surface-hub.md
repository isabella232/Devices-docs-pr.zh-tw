---
title: 疑難排解 Microsoft Surface Hub
description: 對常見問題進行疑難排解，包括設定問題、Exchange ActiveSync 錯誤。
ms.assetid: CF58F74D-8077-48C3-981E-FCFDCA34B34A
ms.reviewer: ''
manager: laurawi
keywords: 針對常見問題、設定問題、Exchange ActiveSync 錯誤進行疑難排解。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2018
ms.localizationpriority: medium
ms.openlocfilehash: fe87c56474a05152f991a5b63f6abf0cf05e8b03
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831347"
---
# 對 Microsoft Surface Hub 進行疑難排解


對常見問題進行疑難排解，包括設定問題、Exchange ActiveSync 錯誤。

[Surface Hub 硬體診斷工具](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab)包含互動式測試，可讓您確認 Hub 的必要功能依預期正常運作。 除了測試硬體之外，診斷工具還可以測試資源帳戶，驗證是否正確設定您的環境。 如果遇到問題，可以將結果儲存起來，與 Surface Hub 支援小組分享。 如需使用方式資訊，請參閱[使用 Surface Hub 硬體診斷工具來測試裝置帳戶](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun)。

下表列出常見問題，以及原因和可能的修正程式。 [設定疑難排解](#setup-troubleshooting)一節包含裝置上的問題清單，以及在初次執行體驗期間可能遇到的數個類型的問題。 [Exchange ActiveSync 錯誤](#exchange-activesync-errors)一節列出嘗試與 Microsoft Exchange ActiveSync 伺服器進行同步時，裝置可能遇到的常見錯誤。




## 設定疑難排解


本節將列出原因及可能的修正程式，以協助疑難排解您可能會在設定 Microsoft Surface Hub 時發現的問題。

### 在裝置上

當您完成初次執行程式之後，可能適用於 Surface Hub 上所發生之問題的修正程式。

<table>
<tr>
<th>問題</th>
<th>原因</th>
<th>可能的修正程式</th>
</tr>
<tr>
<td rowspan="2">
<p>未收到自動接受/拒絕訊息。</p>
</td>
<td>
<p>未將裝置帳戶設定為自動接受/拒絕訊息。</p>
</td>
<td>
<p>使用 PowerShell Cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>。</p>
</td>
</tr>
<tr>
<td>
<p>未將裝置帳戶設定為處理外部會議邀請。</p>
</td>
<td>
<p>使用 PowerShell Cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>。</p>
</td>
</tr>
<tr>
<td>
<p>行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新 (未佈建任何帳戶)」的訊息。</p>
</td>
<td>
<p>未在這個 Surface Hub 上設定任何裝置帳戶。</p>
</td>
<td>
<p>透過 [設定] 佈建裝置帳戶。</p>
</td>
</tr>
<tr>
<td>
<p>行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新 (佈建過多)」的訊息。</p>
</td>
<td>
<p>已將裝置帳戶佈建於太多裝置上。</p>
</td>
<td>
<p>從佈建裝置帳戶的其他裝置移除該裝置帳戶。 您可以使用 Exchange 管理入口網站來執行此動作。</p>
</td>
</tr>
<tr>
<td>
<p>行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新 (無效的認證)」的訊息。</p>
</td>
<td>
<p>裝置帳戶的密碼已過期且不再有效。</p>
</td>
<td>
<p>在 [設定] 中更新帳戶的密碼。 另請參閱<a href="password-management-for-surface-hub-device-accounts.md">密碼管理</a>。</p>
</td>
</tr>
<tr>
<td>
<p>行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新 (帳戶原則)」的訊息。</p>
</td>
<td>
<p>裝置帳戶正在使用無效的 ActiveSync 原則。</p>
</td>
<td>
<p>請確定裝置帳戶具有 <code>PasswordEnabled == False</code> 的 ActiveSync 原則</p>
</td>
</tr>
<tr>
<td>
<p>行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新」的訊息。</p>
</td>
<td>
<p>未啟用 Exchange。</p>
</td>
<td>透過 [設定]，啟用適用於 Exchange 服務的裝置帳戶。 您需要確定您具備一組正確的 ActiveSync 原則，而且也安裝了任何讓 Exchange 服務運作所需的憑證。</td>
</tr>
<tr>
<td>
<p>無法登入商務用 Skype。</p>
</td>
<td>
<p>裝置帳戶不具工作階段初始通訊協定 (SIP) 位址屬性。</p>
</td>
<td>
<p>帳戶不具 SIP 位址屬性，而其使用者主體名稱 (UPN) 和實際的 SIP 位址不符。 帳戶必須設定其 SIP 位址，或者應該使用 [設定] 應用程式來新增 SIP 位址。</p>
</td>
</tr>
<tr>
<td>
<p>無法登入商務用 Skype。</p>
</td>
<td>
<p>裝置帳戶要求憑證以便向商務用 Skype 進行驗證。</p>
</td>
<td>
<p>使用佈建套件安裝適當的憑證。</p>
</td>
</tr>
</table>
 

### 初次執行

可能適用於 Surface Hub 初次執行程式問題的修正程式。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">原因</th>
<th align="left">可能的修正程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>要求網域和使用者名稱時找不到帳戶。</p></td>
<td align="left"><p>網域需要是完整網域名稱 (FQDN)。</p></td>
<td align="left"><p>您應該在網域欄位中提供 FQDN。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a>裝置帳戶頁面，新帳戶設定的問題

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">原因</th>
<th align="left">可能的修正程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Azure AD 中找不到提供的帳戶。</p></td>
<td align="left"><p>所提供帳戶的使用者主體名稱 (UPN) 具有無法在 Azure AD 中觸達的租用戶。</p></td>
<td align="left"><p>確定您具備運作中的網際網路連線，而且裝置可以觸達 Microsoft Online Services。 確定您已正確輸入帳戶認證。</p></td>
</tr>
<tr class="even">
<td align="left"><p>無法觸達指定的目錄。</p></td>
<td align="left"><p>提供的帳戶網域指定無法觸達的網域。</p></td>
<td align="left"><p>確定您具備運作中的網路連線，而且裝置可以觸達網域控制站。 確定您已正確輸入帳戶認證。 您也可以嘗試改用 FQDN。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>無法自動探索 Exchange Server。</p></td>
<td align="left"><p>未將 Exchange Server 設定為自動探索。</p></td>
<td align="left"><p>針對裝置帳戶啟用 Exchange Server 的自動探索，或手動輸入帳戶的 Exchange Server 位址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>輸入帳戶認證之後，無法探索到 SIP 位址。</p></td>
<td align="left"><p>在 Active Directory 或 Azure AD 中沒有 SIP 位址項目。</p></td>
<td align="left"><p>確定帳戶是使用商務用 Skype 來啟用，且具備 SIP 位址。 如果不是，您可以在文字方塊中手動輸入 SIP 位址。</p></td>
</tr>
</tbody>
</table>

 

### 裝置帳戶頁面，現有帳戶設定的問題

<table>
<tr>
<th>問題</th>
<th>原因</th>
<th>錯誤碼</th>
<th>可能的修正程式</th>
</tr>
<tr>
<td>
<p>帳戶無法利用指定的認證進行驗證。</p>
</td>
<td>
<p>帳戶不是利用 Active Directory (AD) 中的使用者身分來啟用、需要密碼進行驗證，或者密碼不正確。</p>
</td>
<td>
<p>無</p>
</td>
<td>
<p>確定已正確輸入認證。 以 AD 中的使用者身分啟用帳戶並新增密碼，或設定 RoomMailboxPassword</p>. </td>
</tr>
<tr>
<td>
<p>提供 Exchange Server 時，顯示錯誤 0x800C0019。</p>
</td>
<td>
<p>裝置帳戶要求憑證以進行驗證。</p>
</td>
<td>
<p>0x800C0019</p>
</td>
<td>
<p>使用佈建套件安裝適當的憑證。</p>
</td>
</tr>
<tr>
<td>
<p>裝置帳戶認證對於提供的 Exchange Server 無效。</p>
</td>
<td>
<p>提供的 Exchange Server 不是裝載裝置帳戶信箱的位置。</p>
</td>
<td>
<p>無</p>
</td>
<td>
<p>確定您針對裝置帳戶提供了正確的 Exchange 郵件伺服器。</p>
</td>
</tr>
<tr>
<td>
<p>嘗試觸達 Exchange Server 時 HTTP 逾時。</p>
</td>
<td></td>
<td>
<p>0x80072EE2</p>
</td>
<td></td>
</tr>
<tr>
<td>
<p>找不到提供的 Exchange Server。</p>
</td>
<td>
<p>找不到提供的 Exchange Server。</p>
</td>
<td>
<p>無</p>
</td>
<td>
<p>確定您具備可運作的網路或網際網路連線，而且您提供了正確的 Exchange Server。</p>
</td>
</tr>
<tr>
<td>
<p>不支援 HTTP。</p>
</td>
<td>
<p>提供使用 <i>http://</i> 而不是 <i>https://</i> 的 Exchange Server。</p>
</td>
<td>
<p>無</p>
</td>
<td>
<p>利用使用 HTTPS 的 Exchange Server。</p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p>使用者位於關於 ActiveSync 且標題為「此帳戶發生問題」的頁面中。</p>
</div>
<div> </div>
</td>
<td>
<p>ActiveSync 原則 PasswordEnabled 已設為 True (或 1)。</p>
</td>
<td>
<p>無</p>
</td>
<td>
<p>建立新的 ActiveSync 原則並將 PasswordEnabled 設為 False (或 0)，然後將該原則套用到帳戶。</p>
</td>
</tr>
<tr>
<td>
<p>Surface Hub 沒有與 Exchange 的連線。</p>
</td>
<td>
<p>無</p>
</td>
<td>
<p>確定您具備可運作的網路或網際網路連線。</p>
</td>
</tr>
<tr>
<td>
<p>Exchange 傳回表示發生錯誤的狀態碼。</p>
</td>
<td>
<p>無</p>
</td>
<td>
<p>確定您具備可運作的網路或網際網路連線。</p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a>初次執行，網域加入頁面問題

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">原因</th>
<th align="left">可能的修正程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>嘗試加入網域時，有錯誤顯示帳戶無法使用指定的認證進行驗證。</p></td>
<td align="left"><p>提供的認證不能加入指定的網域。</p></td>
<td align="left"><p>針對存在於指定網域中的帳戶輸入正確的認證。</p></td>
</tr>
<tr class="even">
<td align="left"><p>指定網域的群組時，有錯誤顯示網域中找不到群組。</p></td>
<td align="left"><p>群組可能已經移除或已不存在。</p></td>
<td align="left"><p>確認群組存在網域中。</p></td>
</tr>
</tbody>
</table>

 

### 初次執行，Exchange Server 頁面

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">原因</th>
<th align="left">可能的修正程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用者位於這個要求 Exchange 伺服器位址的頁面上。</p></td>
<td align="left"><p>未將 Exchange Server 設定為自動探索。</p></td>
<td align="left"><p>針對裝置帳戶啟用 Exchange Server 的自動探索，或手動輸入帳戶的 Exchange Server 位址。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a>初次執行，裝置上的問題

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">問題</th>
<th align="left">原因</th>
<th align="left">錯誤碼</th>
<th align="left">可能的修正程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>無法同步處理電子郵件/行事曆。</p></td>
<td align="left"><p>帳戶不允許 Surface Hub 做為允許的裝置。</p></td>
<td align="left"><p>0x86000C1C</p></td>
<td align="left"><p>設定信箱的 ActiveSyncAllowedDeviceIds 屬性，將 Surface Hub 裝置識別碼新增到允許清單中 <strong> </strong> 。</p></td>
</tr>
</tbody>
</table>

 



 

## Exchange ActiveSync 錯誤


本章節列出了狀態碼、對應、使用者訊息，以及系統管理員可採取來解決 Exchange ActiveSync 錯誤的動作。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">十六進位碼</th>
<th align="left">對應</th>
<th align="left">易懂的訊息</th>
<th align="left">系統管理員應該採取的動作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0x85010002</p></td>
<td align="left"><p>E_HTTP_DENIED</p></td>
<td align="left"><p>密碼必須更新。</p></td>
<td align="left"><p>更新密碼。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072EFD</p></td>
<td align="left"><p>WININET_E_CANNOT_CONNECT</p></td>
<td align="left"><p>目前無法連接至伺服器。 等候一段時間，然後再試一次，或者檢查帳戶設定。</p></td>
<td align="left"><p>確認伺服器名稱正確且保持連線。 確認裝置已連線至網路。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C29</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_NOTPROVISIONED （原則不相符）</p></td>
<td align="left"><p>帳戶是使用與 Surface Hub 不相容的原則來設定。</p></td>
<td align="left"><p>停用此帳戶的 <strong>PasswordEnabled</strong> 原則。</p>
<p>如果帳戶在原則重新整理間隔內沒有收到任何伺服器通知，我們就會有錯誤。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C4C</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</p></td>
<td align="left"><p>帳戶有太多的裝置合作關係。</p></td>
<td align="left"><p>刪除伺服器上的一或多個合作關係。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C0A</p></td>
<td align="left"><p>E_NEXUS_STATUS_SERVERERROR_RETRYLATER</p></td>
<td align="left"><p>目前無法連接至伺服器。</p></td>
<td align="left"><p>等待，直到伺服器恢復連線。 如果問題持續發生，請重新佈建帳戶。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050003</p></td>
<td align="left"><p>E_CREDENTIALS_EXPIRED (認證已過期且需要更新)</p></td>
<td align="left"><p>密碼必須更新。</p></td>
<td align="left"><p>更新密碼。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x8505000D</p></td>
<td align="left"><p>E_AIRSYNC_RESET_RETRY</p></td>
<td align="left"><p>目前無法連接至伺服器。 稍等片刻，或檢查帳戶的設定。</p></td>
<td align="left"><p>這通常是暫時性錯誤，但如果問題持續發生，請檢查與帳戶相關聯的裝置數目，如果數目很大，請刪除其中一些裝置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C16</p></td>
<td align="left"><p>E_NEXUS_STATUS_USER_HASNOMAILBOX</p></td>
<td align="left"><p>信箱已移轉至不同的伺服器。</p></td>
<td align="left"><p>您應該永遠不會看到這個錯誤。 如果問題持續發生，請重新佈建帳戶。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010004</p></td>
<td align="left"><p>E_HTTP_FORBIDDEN</p></td>
<td align="left"><p>目前無法連接至伺服器。 稍等片刻，然後再試一次，或檢查帳戶的設定。</p></td>
<td align="left"><p>確認伺服器名稱，以確定它是正確的。 如果帳戶使用憑證式驗證，請確定憑證仍然有效，如果無效，請加以更新。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85030028</p></td>
<td align="left"><p>E_ACTIVESYNC_PASSWORD_OR_GETCERT</p></td>
<td align="left"><p>帳戶的密碼或用戶端憑證遺失或無效。</p></td>
<td align="left"><p>更新密碼和/或部署用戶端憑證。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x86000C2A</p></td>
<td align="left"><p>E_NEXUS_STATUS_DEVICE_POLICYREFRESH</p></td>
<td align="left"><p>帳戶是使用與 Surface Hub 不相容的原則來設定。</p></td>
<td align="left"><p>停用此帳戶的 PasswordEnabled 原則。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85050002</p></td>
<td align="left"><p>E_CREDENTIALS_UNAVAILABLE</p></td>
<td align="left"><p>密碼必須更新。</p></td>
<td align="left"><p>更新密碼。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE2</p></td>
<td align="left"><p>WININET_E_TIMEOUT</p></td>
<td align="left"><p>網路不支援接收伺服器通知所需的最小空閒超時時，或伺服器已離線。</p></td>
<td align="left"><p>確認伺服器正在執行中。 確認 NAT 設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85002004</p></td>
<td align="left"><p>E_FAIL_ABORT</p></td>
<td align="left"><p>這個錯誤是用來插斷懸置同步處理，而且將不會公開給使用者。 如果您強制執行互動式同步、刪除帳戶或更新其設定，它將會顯示於診斷資料中。</p></td>
<td align="left"><p>無。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010017</p></td>
<td align="left"><p>E_HTTP_SERVICE_UNAVAIL</p></td>
<td align="left"><p>目前無法連接至伺服器。 稍等片刻，或檢查帳戶的設定。</p></td>
<td align="left"><p>確認伺服器名稱，以確定它是正確的。 等待，直到伺服器恢復連線。 如果問題持續發生，請重新佈建帳戶。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C0D</p></td>
<td align="left"><p>E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</p></td>
<td align="left"><p>目前無法連接至伺服器。 稍等片刻，或檢查帳戶的設定。</p></td>
<td align="left"><p>確認伺服器名稱，以確定它是正確的。 等待，直到伺服器恢復連線。 如果問題持續發生，請重新佈建帳戶。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85030027</p></td>
<td align="left"><p>E_ACTIVESYNC_GETCERT</p></td>
<td align="left"><p>Exchange Server 要求憑證。</p></td>
<td align="left"><p>在 Surface Hub 上匯入適當的 EAS 憑證。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x86000C2B</p></td>
<td align="left"><p>E_NEXUS_STATUS_INVALID_POLICYKEY</p></td>
<td align="left"><p>帳戶是使用與 Surface Hub 不相容的原則來設定。</p></td>
<td align="left"><p>停用此帳戶的 PasswordEnabled 原則。</p>
<p>如果帳戶在原則重新整理間隔內沒有收到任何伺服器通知，我們就會有錯誤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x85010005</p></td>
<td align="left"><p>E_HTTP_NOT_FOUND</p></td>
<td align="left"><p>伺服器名稱無效。</p></td>
<td align="left"><p>確認伺服器名稱，以確定它是正確的。 如果問題持續發生，請重新佈建帳戶。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x85010014</p></td>
<td align="left"><p>E_HTTP_SERVER_ERROR</p></td>
<td align="left"><p>無法連接至伺服器。</p></td>
<td align="left"><p>確認伺服器名稱，以確定它是正確的。 觸發同步處理，如果問題持續發生，請重新佈建帳戶。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80072EE7</p></td>
<td align="left"><p>WININET_E_NAME_NOT_RESOLVED</p></td>
<td align="left"><p>無法解析伺服器名稱或位址。</p></td>
<td align="left"><p>確定已正確輸入伺服器名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x8007052F</p></td>
<td align="left"><p>ERROR_ACCOUNT_RESTRICTION</p></td>
<td align="left"><p>自動探索 Exchange Server 時，即會套用原則，以防止登入的使用者登入伺服器。</p></td>
<td align="left"><p>此為計時問題。 重新驗證帳戶的認證。 如果它們是正確的，請嘗試重新佈建。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x800C0019</p></td>
<td align="left"><p>INET_E_INVALID_CERTIFICATE</p></td>
<td align="left"><p>存取此資源所需的安全性憑證無效。</p></td>
<td align="left"><p>針對提供的裝置帳戶安裝所需的正確 ActiveSync 憑證。</p></td>
</tr>
<tr class="even">
<td align="left"><p>0x80072F0D</p></td>
<td align="left"><p>WININET_E_INVALID_CA</p></td>
<td align="left"><p>憑證授權單位無效或不正確。 無法自動探索 Exchange Server，因為憑證已遺失。</p></td>
<td align="left"><p>針對提供的裝置帳戶安裝所需的正確 ActiveSync 憑證。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>0x80004005</p></td>
<td align="left"><p>E_FAIL</p></td>
<td align="left"><p>找不到提供的網域。 無法自動探索 Exchange Server，且未在設定中提供它。</p></td>
<td align="left"><p>請確定輸入的網域為 FQDN，並且已在 Exchange Server 文字方塊中輸入 Exchange Server。</p></td>
</tr>
</tbody>
</table>

##  <a name="contact-support"></a>連絡客戶支援

如果您有任何疑問或需要協助，您可以[建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。


 
## 相關內容

- [連線到 Surface Hub 的 Miracast 疑難排解](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 





