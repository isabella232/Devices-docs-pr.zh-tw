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
# <span data-ttu-id="c62e7-104">對 Microsoft Surface Hub 進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="c62e7-104">Troubleshoot Microsoft Surface Hub</span></span>


<span data-ttu-id="c62e7-105">對常見問題進行疑難排解，包括設定問題、Exchange ActiveSync 錯誤。</span><span class="sxs-lookup"><span data-stu-id="c62e7-105">Troubleshoot common problems, including setup issues, Exchange ActiveSync errors.</span></span>

<span data-ttu-id="c62e7-106">[Surface Hub 硬體診斷工具](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab)包含互動式測試，可讓您確認 Hub 的必要功能依預期正常運作。</span><span class="sxs-lookup"><span data-stu-id="c62e7-106">The [Surface Hub Hardware Diagnostic tool](https://www.microsoft.com/store/p/surface-hub-hardware-diagnostic/9nblggh51f2g?rtc=1&activetab=pivot%3aoverviewtab) contains interactive tests which allow you to confirm essential functionality of your Hub is working as expected.</span></span> <span data-ttu-id="c62e7-107">除了測試硬體之外，診斷工具還可以測試資源帳戶，驗證是否正確設定您的環境。</span><span class="sxs-lookup"><span data-stu-id="c62e7-107">In addition to testing hardware, the diagnostic can test the resource account to verify that it is configured properly for your environment.</span></span> <span data-ttu-id="c62e7-108">如果遇到問題，可以將結果儲存起來，與 Surface Hub 支援小組分享。</span><span class="sxs-lookup"><span data-stu-id="c62e7-108">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="c62e7-109">如需使用方式資訊，請參閱[使用 Surface Hub 硬體診斷工具來測試裝置帳戶](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun)。</span><span class="sxs-lookup"><span data-stu-id="c62e7-109">For usage information, see [Using the Surface Hub Hardware Diagnostic Tool to test a device account](https://support.microsoft.com/help/4077574/using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-accoun).</span></span>

<span data-ttu-id="c62e7-110">下表列出常見問題，以及原因和可能的修正程式。</span><span class="sxs-lookup"><span data-stu-id="c62e7-110">Common issues are listed in the following table, along with causes and possible fixes.</span></span> <span data-ttu-id="c62e7-111">[設定疑難排解](#setup-troubleshooting)一節包含裝置上的問題清單，以及在初次執行體驗期間可能遇到的數個類型的問題。</span><span class="sxs-lookup"><span data-stu-id="c62e7-111">The [Setup troubleshooting](#setup-troubleshooting) section contains a listing of on-device problems, along with several types of issues that may be encountered during the first-run experience.</span></span> <span data-ttu-id="c62e7-112">[Exchange ActiveSync 錯誤](#exchange-activesync-errors)一節列出嘗試與 Microsoft Exchange ActiveSync 伺服器進行同步時，裝置可能遇到的常見錯誤。</span><span class="sxs-lookup"><span data-stu-id="c62e7-112">The [Exchange ActiveSync errors](#exchange-activesync-errors) section lists common errors the device may encounter when trying to synchronize with an Microsoft Exchange ActiveSync server.</span></span>




## <a name="setup-troubleshooting"></a><span data-ttu-id="c62e7-113">設定疑難排解</span><span class="sxs-lookup"><span data-stu-id="c62e7-113">Setup troubleshooting</span></span>


<span data-ttu-id="c62e7-114">本節將列出原因及可能的修正程式，以協助疑難排解您可能會在設定 Microsoft Surface Hub 時發現的問題。</span><span class="sxs-lookup"><span data-stu-id="c62e7-114">This section lists causes, and possible fixes to help troubleshoot issues you might find when you set up your Microsoft Surface Hub.</span></span>

### <a name="on-device"></a><span data-ttu-id="c62e7-115">在裝置上</span><span class="sxs-lookup"><span data-stu-id="c62e7-115">On-device</span></span>

<span data-ttu-id="c62e7-116">當您完成初次執行程式之後，可能適用於 Surface Hub 上所發生之問題的修正程式。</span><span class="sxs-lookup"><span data-stu-id="c62e7-116">Possible fixes for issues on the Surface Hub after you've completed the first-run program.</span></span>

<table>
<tr>
<th><span data-ttu-id="c62e7-117">問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-117">Issue</span></span></th>
<th><span data-ttu-id="c62e7-118">原因</span><span class="sxs-lookup"><span data-stu-id="c62e7-118">Causes</span></span></th>
<th><span data-ttu-id="c62e7-119">可能的修正程式</span><span class="sxs-lookup"><span data-stu-id="c62e7-119">Possible fixes</span></span></th>
</tr>
<tr>
<td rowspan="2">
<p><span data-ttu-id="c62e7-120">未收到自動接受/拒絕訊息。</span><span class="sxs-lookup"><span data-stu-id="c62e7-120">Not receiving automatic accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-121">未將裝置帳戶設定為自動接受/拒絕訊息。</span><span class="sxs-lookup"><span data-stu-id="c62e7-121">The device account isn't configured to automatically accept/decline messages.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-122">使用 PowerShell Cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>。</span><span class="sxs-lookup"><span data-stu-id="c62e7-122">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -AutomateProcessing AutoAccept</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-123">未將裝置帳戶設定為處理外部會議邀請。</span><span class="sxs-lookup"><span data-stu-id="c62e7-123">The device account isn't configured to process external meeting requests.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-124">使用 PowerShell Cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>。</span><span class="sxs-lookup"><span data-stu-id="c62e7-124">Use PowerShell cmdlet <code>Set-CalendarProcessing $upn -ProcessExternalMeetingMessages $true</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-125">行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新 (未佈建任何帳戶)」的訊息。</span><span class="sxs-lookup"><span data-stu-id="c62e7-125">Calendar is not showing on the Welcome screen, or message "Appointments of date (no account provisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-126">未在這個 Surface Hub 上設定任何裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-126">No device account is set up on this Surface Hub.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-127">透過 [設定] 佈建裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-127">Provision a device account through Settings.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-128">行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新 (佈建過多)」的訊息。</span><span class="sxs-lookup"><span data-stu-id="c62e7-128">Calendar is not showing on the Welcome screen or message "Appointments of date (overprovisioned)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-129">已將裝置帳戶佈建於太多裝置上。</span><span class="sxs-lookup"><span data-stu-id="c62e7-129">The device account is provisioned on too many devices.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-130">從佈建裝置帳戶的其他裝置移除該裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-130">Remove the device account from other devices that it's provisioned to.</span></span> <span data-ttu-id="c62e7-131">您可以使用 Exchange 管理入口網站來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="c62e7-131">This can be done using the Exchange admin portal.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-132">行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新 (無效的認證)」的訊息。</span><span class="sxs-lookup"><span data-stu-id="c62e7-132">Calendar is not showing on the Welcome screen or message "Appointments of date (invalid credentials)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-133">裝置帳戶的密碼已過期且不再有效。</span><span class="sxs-lookup"><span data-stu-id="c62e7-133">The device account's password has expired and is no longer valid.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-134">在 [設定] 中更新帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="c62e7-134">Update the account's password in Settings.</span></span> <span data-ttu-id="c62e7-135">另請參閱<a href="password-management-for-surface-hub-device-accounts.md">密碼管理</a>。</span><span class="sxs-lookup"><span data-stu-id="c62e7-135">Also see <a href="password-management-for-surface-hub-device-accounts.md">Password management</a>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-136">行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新 (帳戶原則)」的訊息。</span><span class="sxs-lookup"><span data-stu-id="c62e7-136">Calendar is not showing on the Welcome screen or message "Appointments of date (account policy)" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-137">裝置帳戶正在使用無效的 ActiveSync 原則。</span><span class="sxs-lookup"><span data-stu-id="c62e7-137">The device account is using an invalid ActiveSync policy.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-138">請確定裝置帳戶具有 <code>PasswordEnabled == False</code> 的 ActiveSync 原則</span><span class="sxs-lookup"><span data-stu-id="c62e7-138">Make sure the device account has an ActiveSync policy where <code>PasswordEnabled == False</code>.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-139">行事曆未顯示於歡迎畫面上，或者顯示了「約會可能未更新」的訊息。</span><span class="sxs-lookup"><span data-stu-id="c62e7-139">Calendar is not showing on the Welcome screen or message "Appointments may be out of date" is being displayed.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-140">未啟用 Exchange。</span><span class="sxs-lookup"><span data-stu-id="c62e7-140">Exchange is not enabled.</span></span></p>
</td>
<td><span data-ttu-id="c62e7-141">透過 [設定]，啟用適用於 Exchange 服務的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-141">Enable the device account for Exchange services through Settings.</span></span> <span data-ttu-id="c62e7-142">您需要確定您具備一組正確的 ActiveSync 原則，而且也安裝了任何讓 Exchange 服務運作所需的憑證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-142">You need to make sure you have the right set of ActiveSync policies and have also installed any necessary certificates for Exchange services to work.</span></span></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-143">無法登入商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="c62e7-143">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-144">裝置帳戶不具工作階段初始通訊協定 (SIP) 位址屬性。</span><span class="sxs-lookup"><span data-stu-id="c62e7-144">The device account does not have a Session Initiation Protocol (SIP) address property.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-145">帳戶不具 SIP 位址屬性，而其使用者主體名稱 (UPN) 和實際的 SIP 位址不符。</span><span class="sxs-lookup"><span data-stu-id="c62e7-145">The account does not have a SIP address property and its User Principal Name (UPN) does not match the actual SIP address.</span></span> <span data-ttu-id="c62e7-146">帳戶必須設定其 SIP 位址，或者應該使用 [設定] 應用程式來新增 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="c62e7-146">The account must have its SIP address set, or the SIP address should be added using the Settings app.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-147">無法登入商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="c62e7-147">Can't log in to Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-148">裝置帳戶要求憑證以便向商務用 Skype 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-148">The device account requires a certificate to authenticate into Skype for Business.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-149">使用佈建套件安裝適當的憑證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-149">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
</table>
 

### <a name="first-run"></a><span data-ttu-id="c62e7-150">初次執行</span><span class="sxs-lookup"><span data-stu-id="c62e7-150">First run</span></span>

<span data-ttu-id="c62e7-151">可能適用於 Surface Hub 初次執行程式問題的修正程式。</span><span class="sxs-lookup"><span data-stu-id="c62e7-151">Possible fixes for issues with Surface Hub first-run program.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c62e7-152">問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-152">Issue</span></span></th>
<th align="left"><span data-ttu-id="c62e7-153">原因</span><span class="sxs-lookup"><span data-stu-id="c62e7-153">Causes</span></span></th>
<th align="left"><span data-ttu-id="c62e7-154">可能的修正程式</span><span class="sxs-lookup"><span data-stu-id="c62e7-154">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-155">要求網域和使用者名稱時找不到帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-155">Cannot find account when asked for domain and user name.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-156">網域需要是完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="c62e7-156">Domain needs to be the fully qualified domain name (FQDN).</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-157">您應該在網域欄位中提供 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c62e7-157">The FQDN should be provided in the domain field.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-device-acct-page"></a><span data-ttu-id="c62e7-158">裝置帳戶頁面，新帳戶設定的問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-158">Device account page, issues for new account settings</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c62e7-159">問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-159">Issue</span></span></th>
<th align="left"><span data-ttu-id="c62e7-160">原因</span><span class="sxs-lookup"><span data-stu-id="c62e7-160">Causes</span></span></th>
<th align="left"><span data-ttu-id="c62e7-161">可能的修正程式</span><span class="sxs-lookup"><span data-stu-id="c62e7-161">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-162">在 Azure AD 中找不到提供的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-162">Unable to find the provided account in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-163">所提供帳戶的使用者主體名稱 (UPN) 具有無法在 Azure AD 中觸達的租用戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-163">The provided account's User Principal Name (UPN) has a tenant that can't be reached in Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-164">確定您具備運作中的網際網路連線，而且裝置可以觸達 Microsoft Online Services。</span><span class="sxs-lookup"><span data-stu-id="c62e7-164">Make sure that you have a working Internet connection, and that the device can reach Microsoft Online Services.</span></span> <span data-ttu-id="c62e7-165">確定您已正確輸入帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-165">Make sure the account credentials are entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-166">無法觸達指定的目錄。</span><span class="sxs-lookup"><span data-stu-id="c62e7-166">Unable to reach the specified directory.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-167">提供的帳戶網域指定無法觸達的網域。</span><span class="sxs-lookup"><span data-stu-id="c62e7-167">The provided account domain specifies a domain that can't be reached.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-168">確定您具備運作中的網路連線，而且裝置可以觸達網域控制站。</span><span class="sxs-lookup"><span data-stu-id="c62e7-168">Make sure that you have a working network connection, and that the device can reach the domain controller.</span></span> <span data-ttu-id="c62e7-169">確定您已正確輸入帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-169">Make sure the account credentials are entered correctly.</span></span> <span data-ttu-id="c62e7-170">您也可以嘗試改用 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c62e7-170">You can also try using the FQDN instead.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-171">無法自動探索 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="c62e7-171">Can't auto-discover Exchange server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-172">未將 Exchange Server 設定為自動探索。</span><span class="sxs-lookup"><span data-stu-id="c62e7-172">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-173">針對裝置帳戶啟用 Exchange Server 的自動探索，或手動輸入帳戶的 Exchange Server 位址。</span><span class="sxs-lookup"><span data-stu-id="c62e7-173">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-174">輸入帳戶認證之後，無法探索到 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="c62e7-174">Could not discover the SIP address after entering the account credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-175">在 Active Directory 或 Azure AD 中沒有 SIP 位址項目。</span><span class="sxs-lookup"><span data-stu-id="c62e7-175">There was no SIP address entry in Active Directory or Azure AD.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-176">確定帳戶是使用商務用 Skype 來啟用，且具備 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="c62e7-176">Make sure the account is enabled with Skype for Business and has a SIP address.</span></span> <span data-ttu-id="c62e7-177">如果不是，您可以在文字方塊中手動輸入 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="c62e7-177">If not, you can enter the SIP address manually into the text box.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a name="device-account-page,-issues-for-existing-account-settings"></a><span data-ttu-id="c62e7-178">裝置帳戶頁面，現有帳戶設定的問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-178">Device account page, issues for existing account settings</span></span>

<table>
<tr>
<th><span data-ttu-id="c62e7-179">問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-179">Issue</span></span></th>
<th><span data-ttu-id="c62e7-180">原因</span><span class="sxs-lookup"><span data-stu-id="c62e7-180">Causes</span></span></th>
<th><span data-ttu-id="c62e7-181">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="c62e7-181">Error codes</span></span></th>
<th><span data-ttu-id="c62e7-182">可能的修正程式</span><span class="sxs-lookup"><span data-stu-id="c62e7-182">Possible fixes</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-183">帳戶無法利用指定的認證進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-183">Account could not authenticate with the specified credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-184">帳戶不是利用 Active Directory (AD) 中的使用者身分來啟用、需要密碼進行驗證，或者密碼不正確。</span><span class="sxs-lookup"><span data-stu-id="c62e7-184">The account is not enabled as a user in Active Directory (AD), needs a password to authenticate, or the password is incorrect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-185">無</span><span class="sxs-lookup"><span data-stu-id="c62e7-185">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-186">確定已正確輸入認證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-186">Make sure the credentials are entered correctly.</span></span> <span data-ttu-id="c62e7-187">以 AD 中的使用者身分啟用帳戶並新增密碼，或設定 RoomMailboxPassword</span><span class="sxs-lookup"><span data-stu-id="c62e7-187">Enable the account as a user in AD and add a password, or set the RoomMailboxPassword</span></span></p><span data-ttu-id="c62e7-188">.</span><span class="sxs-lookup"><span data-stu-id="c62e7-188">.</span></span> </td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-189">提供 Exchange Server 時，顯示錯誤 0x800C0019。</span><span class="sxs-lookup"><span data-stu-id="c62e7-189">Error 0x800C0019 is displayed when providing an Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-190">裝置帳戶要求憑證以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-190">The device account requires a certificate to authenticate.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-191">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="c62e7-191">0x800C0019</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-192">使用佈建套件安裝適當的憑證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-192">Install the appropriate certificate using provisioning packages.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-193">裝置帳戶認證對於提供的 Exchange Server 無效。</span><span class="sxs-lookup"><span data-stu-id="c62e7-193">Device account credentials are not valid for the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-194">提供的 Exchange Server 不是裝載裝置帳戶信箱的位置。</span><span class="sxs-lookup"><span data-stu-id="c62e7-194">The provided Exchange server is not where the device account's mailbox is hosted.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-195">無</span><span class="sxs-lookup"><span data-stu-id="c62e7-195">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-196">確定您針對裝置帳戶提供了正確的 Exchange 郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-196">Make sure you are providing the correct Exchange mail server for the device account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-197">嘗試觸達 Exchange Server 時 HTTP 逾時。</span><span class="sxs-lookup"><span data-stu-id="c62e7-197">HTTP timeout while trying to reach Exchange server.</span></span></p>
</td>
<td></td>
<td>
<p><span data-ttu-id="c62e7-198">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="c62e7-198">0x80072EE2</span></span></p>
</td>
<td></td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-199">找不到提供的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="c62e7-199">Couldn't find the provided Exchange server.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-200">找不到提供的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="c62e7-200">The Exchange server provided could not be found.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-201">無</span><span class="sxs-lookup"><span data-stu-id="c62e7-201">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-202">確定您具備可運作的網路或網際網路連線，而且您提供了正確的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="c62e7-202">Ensure that you have a working network or Internet connection, and that the Exchange server you provided is correct.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-203">不支援 HTTP。</span><span class="sxs-lookup"><span data-stu-id="c62e7-203">http not supported.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-204">提供使用 <i>http://</i> 而不是 <i>https://</i> 的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="c62e7-204">An Exchange server with <i>http://</i> instead of <i>https://</i> was provided.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-205">無</span><span class="sxs-lookup"><span data-stu-id="c62e7-205">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-206">利用使用 HTTPS 的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="c62e7-206">Use an Exchange server that uses https.</span></span></p>
</td>
</tr>
<tr>
<td rowspan="3">
<div><p><span data-ttu-id="c62e7-207">使用者位於關於 ActiveSync 且標題為「此帳戶發生問題」的頁面中。</span><span class="sxs-lookup"><span data-stu-id="c62e7-207">People land on the page titled "There's a problem with this account" regarding ActiveSync.</span></span></p>
</div>
<div> </div>
</td>
<td>
<p><span data-ttu-id="c62e7-208">ActiveSync 原則 PasswordEnabled 已設為 True (或 1)。</span><span class="sxs-lookup"><span data-stu-id="c62e7-208">The ActiveSync policy PasswordEnabled is set to True (or 1).</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-209">無</span><span class="sxs-lookup"><span data-stu-id="c62e7-209">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-210">建立新的 ActiveSync 原則並將 PasswordEnabled 設為 False (或 0)，然後將該原則套用到帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-210">Create a new ActiveSync policy where PasswordEnabled is set to False (or 0), and then apply that policy to the account.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-211">Surface Hub 沒有與 Exchange 的連線。</span><span class="sxs-lookup"><span data-stu-id="c62e7-211">The Surface Hub doesn't have a connection to Exchange.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-212">無</span><span class="sxs-lookup"><span data-stu-id="c62e7-212">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-213">確定您具備可運作的網路或網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="c62e7-213">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="c62e7-214">Exchange 傳回表示發生錯誤的狀態碼。</span><span class="sxs-lookup"><span data-stu-id="c62e7-214">Exchange returns a status code indicating an error.</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-215">無</span><span class="sxs-lookup"><span data-stu-id="c62e7-215">None</span></span></p>
</td>
<td>
<p><span data-ttu-id="c62e7-216">確定您具備可運作的網路或網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="c62e7-216">Make sure that you have a working network or Internet connection.</span></span></p>
</td>
</tr>
</table>
 

### <a href="" id="first-run-domain-join-page"></a><span data-ttu-id="c62e7-217">初次執行，網域加入頁面問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-217">First run, Domain join page issues</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c62e7-218">問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-218">Issue</span></span></th>
<th align="left"><span data-ttu-id="c62e7-219">原因</span><span class="sxs-lookup"><span data-stu-id="c62e7-219">Causes</span></span></th>
<th align="left"><span data-ttu-id="c62e7-220">可能的修正程式</span><span class="sxs-lookup"><span data-stu-id="c62e7-220">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-221">嘗試加入網域時，有錯誤顯示帳戶無法使用指定的認證進行驗證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-221">When trying to join a domain, an error shows that the account couldn't authenticate using the specified credentials.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-222">提供的認證不能加入指定的網域。</span><span class="sxs-lookup"><span data-stu-id="c62e7-222">The credentials provided are not capable of joining the specified domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-223">針對存在於指定網域中的帳戶輸入正確的認證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-223">Enter correct credentials for an account that exists in the specified domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-224">指定網域的群組時，有錯誤顯示網域中找不到群組。</span><span class="sxs-lookup"><span data-stu-id="c62e7-224">When specifying a group from a domain, an error shows that the group couldn't be found on the domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-225">群組可能已經移除或已不存在。</span><span class="sxs-lookup"><span data-stu-id="c62e7-225">The group may have been removed or no longer exists.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-226">確認群組存在網域中。</span><span class="sxs-lookup"><span data-stu-id="c62e7-226">Verify that the group exists within the domain.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a name="first-run,-exchange-server-page"></a><span data-ttu-id="c62e7-227">初次執行，Exchange Server 頁面</span><span class="sxs-lookup"><span data-stu-id="c62e7-227">First run, Exchange server page</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c62e7-228">問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-228">Issue</span></span></th>
<th align="left"><span data-ttu-id="c62e7-229">原因</span><span class="sxs-lookup"><span data-stu-id="c62e7-229">Causes</span></span></th>
<th align="left"><span data-ttu-id="c62e7-230">可能的修正程式</span><span class="sxs-lookup"><span data-stu-id="c62e7-230">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-231">使用者位於這個要求 Exchange 伺服器位址的頁面上。</span><span class="sxs-lookup"><span data-stu-id="c62e7-231">People land on this page and are asked for the Exchange server address.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-232">未將 Exchange Server 設定為自動探索。</span><span class="sxs-lookup"><span data-stu-id="c62e7-232">The Exchange server isn't configured for auto-discovery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-233">針對裝置帳戶啟用 Exchange Server 的自動探索，或手動輸入帳戶的 Exchange Server 位址。</span><span class="sxs-lookup"><span data-stu-id="c62e7-233">Enable auto-discovery of the Exchange server for the device account, or enter the account's Exchange server address manually.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="first-run-on-device"></a><span data-ttu-id="c62e7-234">初次執行，裝置上的問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-234">First run, On-device issues</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c62e7-235">問題</span><span class="sxs-lookup"><span data-stu-id="c62e7-235">Issue</span></span></th>
<th align="left"><span data-ttu-id="c62e7-236">原因</span><span class="sxs-lookup"><span data-stu-id="c62e7-236">Causes</span></span></th>
<th align="left"><span data-ttu-id="c62e7-237">錯誤碼</span><span class="sxs-lookup"><span data-stu-id="c62e7-237">Error codes</span></span></th>
<th align="left"><span data-ttu-id="c62e7-238">可能的修正程式</span><span class="sxs-lookup"><span data-stu-id="c62e7-238">Possible fixes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-239">無法同步處理電子郵件/行事曆。</span><span class="sxs-lookup"><span data-stu-id="c62e7-239">Can't sync mail/calendar.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-240">帳戶不允許 Surface Hub 做為允許的裝置。</span><span class="sxs-lookup"><span data-stu-id="c62e7-240">The account has not allowed the Surface Hub as an allowed device.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-241">0x86000C1C</span><span class="sxs-lookup"><span data-stu-id="c62e7-241">0x86000C1C</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-242">設定信箱的 ActiveSyncAllowedDeviceIds 屬性，將 Surface Hub 裝置識別碼新增到允許清單中 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="c62e7-242">Add the Surface Hub device ID to the allowed list by setting the <strong>ActiveSyncAllowedDeviceIds</strong> property for the mailbox.</span></span></p></td>
</tr>
</tbody>
</table>

 



 

## <a name="exchange-activesync-errors"></a><span data-ttu-id="c62e7-243">Exchange ActiveSync 錯誤</span><span class="sxs-lookup"><span data-stu-id="c62e7-243">Exchange ActiveSync errors</span></span>


<span data-ttu-id="c62e7-244">本章節列出了狀態碼、對應、使用者訊息，以及系統管理員可採取來解決 Exchange ActiveSync 錯誤的動作。</span><span class="sxs-lookup"><span data-stu-id="c62e7-244">This section lists status codes, mapping, user messages, and actions an admin can take to solve Exchange ActiveSync errors.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c62e7-245">十六進位碼</span><span class="sxs-lookup"><span data-stu-id="c62e7-245">Hex Code</span></span></th>
<th align="left"><span data-ttu-id="c62e7-246">對應</span><span class="sxs-lookup"><span data-stu-id="c62e7-246">Mapping</span></span></th>
<th align="left"><span data-ttu-id="c62e7-247">易懂的訊息</span><span class="sxs-lookup"><span data-stu-id="c62e7-247">User-Friendly Message</span></span></th>
<th align="left"><span data-ttu-id="c62e7-248">系統管理員應該採取的動作</span><span class="sxs-lookup"><span data-stu-id="c62e7-248">Action admin should take</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-249">0x85010002</span><span class="sxs-lookup"><span data-stu-id="c62e7-249">0x85010002</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-250">E_HTTP_DENIED</span><span class="sxs-lookup"><span data-stu-id="c62e7-250">E_HTTP_DENIED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-251">密碼必須更新。</span><span class="sxs-lookup"><span data-stu-id="c62e7-251">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-252">更新密碼。</span><span class="sxs-lookup"><span data-stu-id="c62e7-252">Update the password.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-253">0x80072EFD</span><span class="sxs-lookup"><span data-stu-id="c62e7-253">0x80072EFD</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-254">WININET_E_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="c62e7-254">WININET_E_CANNOT_CONNECT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-255">目前無法連接至伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-255">Can't connect to the server right now.</span></span> <span data-ttu-id="c62e7-256">等候一段時間，然後再試一次，或者檢查帳戶設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-256">Wait a while and try again, or check the account settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-257">確認伺服器名稱正確且保持連線。</span><span class="sxs-lookup"><span data-stu-id="c62e7-257">Verify that the server name is correct and reachable.</span></span> <span data-ttu-id="c62e7-258">確認裝置已連線至網路。</span><span class="sxs-lookup"><span data-stu-id="c62e7-258">Verify that the device is connected to the network.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-259">0x86000C29</span><span class="sxs-lookup"><span data-stu-id="c62e7-259">0x86000C29</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED （原則不相符）</span><span class="sxs-lookup"><span data-stu-id="c62e7-260">E_NEXUS_STATUS_DEVICE_NOTPROVISIONED (policies don't match)</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-261">帳戶是使用與 Surface Hub 不相容的原則來設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-261">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-262">停用此帳戶的 <strong>PasswordEnabled</strong> 原則。</span><span class="sxs-lookup"><span data-stu-id="c62e7-262">Disable the <strong>PasswordEnabled</strong> policy for this account.</span></span></p>
<p><span data-ttu-id="c62e7-263">如果帳戶在原則重新整理間隔內沒有收到任何伺服器通知，我們就會有錯誤。</span><span class="sxs-lookup"><span data-stu-id="c62e7-263">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-264">0x86000C4C</span><span class="sxs-lookup"><span data-stu-id="c62e7-264">0x86000C4C</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span><span class="sxs-lookup"><span data-stu-id="c62e7-265">E_NEXUS_STATUS_MAXIMUMDEVICESREACHED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-266">帳戶有太多的裝置合作關係。</span><span class="sxs-lookup"><span data-stu-id="c62e7-266">The account has too many device partnerships.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-267">刪除伺服器上的一或多個合作關係。</span><span class="sxs-lookup"><span data-stu-id="c62e7-267">Delete one or more partnerships on the server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-268">0x86000C0A</span><span class="sxs-lookup"><span data-stu-id="c62e7-268">0x86000C0A</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span><span class="sxs-lookup"><span data-stu-id="c62e7-269">E_NEXUS_STATUS_SERVERERROR_RETRYLATER</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-270">目前無法連接至伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-270">Can't connect to the server right now.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-271">等待，直到伺服器恢復連線。</span><span class="sxs-lookup"><span data-stu-id="c62e7-271">Wait until the server comes back online.</span></span> <span data-ttu-id="c62e7-272">如果問題持續發生，請重新佈建帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-272">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-273">0x85050003</span><span class="sxs-lookup"><span data-stu-id="c62e7-273">0x85050003</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-274">E_CREDENTIALS_EXPIRED (認證已過期且需要更新)</span><span class="sxs-lookup"><span data-stu-id="c62e7-274">E_CREDENTIALS_EXPIRED (Credentials have expired and need to be updated)</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-275">密碼必須更新。</span><span class="sxs-lookup"><span data-stu-id="c62e7-275">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-276">更新密碼。</span><span class="sxs-lookup"><span data-stu-id="c62e7-276">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-277">0x8505000D</span><span class="sxs-lookup"><span data-stu-id="c62e7-277">0x8505000D</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-278">E_AIRSYNC_RESET_RETRY</span><span class="sxs-lookup"><span data-stu-id="c62e7-278">E_AIRSYNC_RESET_RETRY</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-279">目前無法連接至伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-279">Can't connect to the server right now.</span></span> <span data-ttu-id="c62e7-280">稍等片刻，或檢查帳戶的設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-280">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-281">這通常是暫時性錯誤，但如果問題持續發生，請檢查與帳戶相關聯的裝置數目，如果數目很大，請刪除其中一些裝置。</span><span class="sxs-lookup"><span data-stu-id="c62e7-281">This is normally a transient error but if the issue persists check the number of devices associated with the account and delete some of them if the number is large.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-282">0x86000C16</span><span class="sxs-lookup"><span data-stu-id="c62e7-282">0x86000C16</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span><span class="sxs-lookup"><span data-stu-id="c62e7-283">E_NEXUS_STATUS_USER_HASNOMAILBOX</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-284">信箱已移轉至不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-284">The mailbox was migrated to a different server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-285">您應該永遠不會看到這個錯誤。</span><span class="sxs-lookup"><span data-stu-id="c62e7-285">You should never see this error.</span></span> <span data-ttu-id="c62e7-286">如果問題持續發生，請重新佈建帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-286">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-287">0x85010004</span><span class="sxs-lookup"><span data-stu-id="c62e7-287">0x85010004</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-288">E_HTTP_FORBIDDEN</span><span class="sxs-lookup"><span data-stu-id="c62e7-288">E_HTTP_FORBIDDEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-289">目前無法連接至伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-289">Can't connect to the server right now.</span></span> <span data-ttu-id="c62e7-290">稍等片刻，然後再試一次，或檢查帳戶的設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-290">Wait a while and try again, or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-291">確認伺服器名稱，以確定它是正確的。</span><span class="sxs-lookup"><span data-stu-id="c62e7-291">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c62e7-292">如果帳戶使用憑證式驗證，請確定憑證仍然有效，如果無效，請加以更新。</span><span class="sxs-lookup"><span data-stu-id="c62e7-292">If the account is using cert based authentication make sure the certificate is still valid and update it if not.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-293">0x85030028</span><span class="sxs-lookup"><span data-stu-id="c62e7-293">0x85030028</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span><span class="sxs-lookup"><span data-stu-id="c62e7-294">E_ACTIVESYNC_PASSWORD_OR_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-295">帳戶的密碼或用戶端憑證遺失或無效。</span><span class="sxs-lookup"><span data-stu-id="c62e7-295">The account's password or client certificate are missing or invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-296">更新密碼和/或部署用戶端憑證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-296">Update the password and/or deploy the client certificate.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-297">0x86000C2A</span><span class="sxs-lookup"><span data-stu-id="c62e7-297">0x86000C2A</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span><span class="sxs-lookup"><span data-stu-id="c62e7-298">E_NEXUS_STATUS_DEVICE_POLICYREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-299">帳戶是使用與 Surface Hub 不相容的原則來設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-299">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-300">停用此帳戶的 PasswordEnabled 原則。</span><span class="sxs-lookup"><span data-stu-id="c62e7-300">Disable the PasswordEnabled policy for this account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-301">0x85050002</span><span class="sxs-lookup"><span data-stu-id="c62e7-301">0x85050002</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-302">E_CREDENTIALS_UNAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c62e7-302">E_CREDENTIALS_UNAVAILABLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-303">密碼必須更新。</span><span class="sxs-lookup"><span data-stu-id="c62e7-303">The password must be updated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-304">更新密碼。</span><span class="sxs-lookup"><span data-stu-id="c62e7-304">Update the password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-305">0x80072EE2</span><span class="sxs-lookup"><span data-stu-id="c62e7-305">0x80072EE2</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-306">WININET_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="c62e7-306">WININET_E_TIMEOUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-307">網路不支援接收伺服器通知所需的最小空閒超時時，或伺服器已離線。</span><span class="sxs-lookup"><span data-stu-id="c62e7-307">The network doesn't support the minimum idle timeout required to receive server notification, or the server is offline.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-308">確認伺服器正在執行中。</span><span class="sxs-lookup"><span data-stu-id="c62e7-308">Verify that the server is running.</span></span> <span data-ttu-id="c62e7-309">確認 NAT 設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-309">Verify the NAT settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-310">0x85002004</span><span class="sxs-lookup"><span data-stu-id="c62e7-310">0x85002004</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-311">E_FAIL_ABORT</span><span class="sxs-lookup"><span data-stu-id="c62e7-311">E_FAIL_ABORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-312">這個錯誤是用來插斷懸置同步處理，而且將不會公開給使用者。</span><span class="sxs-lookup"><span data-stu-id="c62e7-312">This error is used to interrupt the hanging sync, and will not be exposed to users.</span></span> <span data-ttu-id="c62e7-313">如果您強制執行互動式同步、刪除帳戶或更新其設定，它將會顯示於診斷資料中。</span><span class="sxs-lookup"><span data-stu-id="c62e7-313">It will be shown in the diagnostic data if you force an interactive sync, delete the account, or update its settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-314">無。</span><span class="sxs-lookup"><span data-stu-id="c62e7-314">Nothing.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-315">0x85010017</span><span class="sxs-lookup"><span data-stu-id="c62e7-315">0x85010017</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-316">E_HTTP_SERVICE_UNAVAIL</span><span class="sxs-lookup"><span data-stu-id="c62e7-316">E_HTTP_SERVICE_UNAVAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-317">目前無法連接至伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-317">Can't connect to the server right now.</span></span> <span data-ttu-id="c62e7-318">稍等片刻，或檢查帳戶的設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-318">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-319">確認伺服器名稱，以確定它是正確的。</span><span class="sxs-lookup"><span data-stu-id="c62e7-319">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c62e7-320">等待，直到伺服器恢復連線。</span><span class="sxs-lookup"><span data-stu-id="c62e7-320">Wait until the server comes back online.</span></span> <span data-ttu-id="c62e7-321">如果問題持續發生，請重新佈建帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-321">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-322">0x86000C0D</span><span class="sxs-lookup"><span data-stu-id="c62e7-322">0x86000C0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span><span class="sxs-lookup"><span data-stu-id="c62e7-323">E_NEXUS_STATUS_MAILBOX_SERVEROFFLINE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-324">目前無法連接至伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-324">Can't connect to the server right now.</span></span> <span data-ttu-id="c62e7-325">稍等片刻，或檢查帳戶的設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-325">Wait a while or check the account's settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-326">確認伺服器名稱，以確定它是正確的。</span><span class="sxs-lookup"><span data-stu-id="c62e7-326">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c62e7-327">等待，直到伺服器恢復連線。</span><span class="sxs-lookup"><span data-stu-id="c62e7-327">Wait until the server comes back online.</span></span> <span data-ttu-id="c62e7-328">如果問題持續發生，請重新佈建帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-328">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-329">0x85030027</span><span class="sxs-lookup"><span data-stu-id="c62e7-329">0x85030027</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-330">E_ACTIVESYNC_GETCERT</span><span class="sxs-lookup"><span data-stu-id="c62e7-330">E_ACTIVESYNC_GETCERT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-331">Exchange Server 要求憑證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-331">The Exchange server requires a certificate.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-332">在 Surface Hub 上匯入適當的 EAS 憑證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-332">Import the appropriate EAS certificate on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-333">0x86000C2B</span><span class="sxs-lookup"><span data-stu-id="c62e7-333">0x86000C2B</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span><span class="sxs-lookup"><span data-stu-id="c62e7-334">E_NEXUS_STATUS_INVALID_POLICYKEY</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-335">帳戶是使用與 Surface Hub 不相容的原則來設定。</span><span class="sxs-lookup"><span data-stu-id="c62e7-335">The account is configured with policies not compatible with Surface Hub.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-336">停用此帳戶的 PasswordEnabled 原則。</span><span class="sxs-lookup"><span data-stu-id="c62e7-336">Disable the PasswordEnabled policy for this account.</span></span></p>
<p><span data-ttu-id="c62e7-337">如果帳戶在原則重新整理間隔內沒有收到任何伺服器通知，我們就會有錯誤。</span><span class="sxs-lookup"><span data-stu-id="c62e7-337">We have a bug were we may surface policy errors if the account doesn't receive any server notifications within the policy refresh interval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-338">0x85010005</span><span class="sxs-lookup"><span data-stu-id="c62e7-338">0x85010005</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-339">E_HTTP_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="c62e7-339">E_HTTP_NOT_FOUND</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-340">伺服器名稱無效。</span><span class="sxs-lookup"><span data-stu-id="c62e7-340">The server name is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-341">確認伺服器名稱，以確定它是正確的。</span><span class="sxs-lookup"><span data-stu-id="c62e7-341">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c62e7-342">如果問題持續發生，請重新佈建帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-342">If the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-343">0x85010014</span><span class="sxs-lookup"><span data-stu-id="c62e7-343">0x85010014</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-344">E_HTTP_SERVER_ERROR</span><span class="sxs-lookup"><span data-stu-id="c62e7-344">E_HTTP_SERVER_ERROR</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-345">無法連接至伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-345">Can't connect to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-346">確認伺服器名稱，以確定它是正確的。</span><span class="sxs-lookup"><span data-stu-id="c62e7-346">Verify the server name to make sure it is correct.</span></span> <span data-ttu-id="c62e7-347">觸發同步處理，如果問題持續發生，請重新佈建帳戶。</span><span class="sxs-lookup"><span data-stu-id="c62e7-347">Trigger a sync and, if the issue persists, re-provision the account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-348">0x80072EE7</span><span class="sxs-lookup"><span data-stu-id="c62e7-348">0x80072EE7</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-349">WININET_E_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="c62e7-349">WININET_E_NAME_NOT_RESOLVED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-350">無法解析伺服器名稱或位址。</span><span class="sxs-lookup"><span data-stu-id="c62e7-350">The server name or address could not be resolved.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-351">確定已正確輸入伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="c62e7-351">Make sure the server name is entered correctly.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-352">0x8007052F</span><span class="sxs-lookup"><span data-stu-id="c62e7-352">0x8007052F</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-353">ERROR_ACCOUNT_RESTRICTION</span><span class="sxs-lookup"><span data-stu-id="c62e7-353">ERROR_ACCOUNT_RESTRICTION</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-354">自動探索 Exchange Server 時，即會套用原則，以防止登入的使用者登入伺服器。</span><span class="sxs-lookup"><span data-stu-id="c62e7-354">While auto-discovering the Exchange server, a policy is applied that prevents the logged-in user from logging in to the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-355">此為計時問題。</span><span class="sxs-lookup"><span data-stu-id="c62e7-355">This is a timing issue.</span></span> <span data-ttu-id="c62e7-356">重新驗證帳戶的認證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-356">Re-verify the account's credentials.</span></span> <span data-ttu-id="c62e7-357">如果它們是正確的，請嘗試重新佈建。</span><span class="sxs-lookup"><span data-stu-id="c62e7-357">Try to re-provision when they're correct.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-358">0x800C0019</span><span class="sxs-lookup"><span data-stu-id="c62e7-358">0x800C0019</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-359">INET_E_INVALID_CERTIFICATE</span><span class="sxs-lookup"><span data-stu-id="c62e7-359">INET_E_INVALID_CERTIFICATE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-360">存取此資源所需的安全性憑證無效。</span><span class="sxs-lookup"><span data-stu-id="c62e7-360">Security certificate required to access this resource is invalid.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-361">針對提供的裝置帳戶安裝所需的正確 ActiveSync 憑證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-361">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c62e7-362">0x80072F0D</span><span class="sxs-lookup"><span data-stu-id="c62e7-362">0x80072F0D</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-363">WININET_E_INVALID_CA</span><span class="sxs-lookup"><span data-stu-id="c62e7-363">WININET_E_INVALID_CA</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-364">憑證授權單位無效或不正確。</span><span class="sxs-lookup"><span data-stu-id="c62e7-364">The certificate authority is invalid or is incorrect.</span></span> <span data-ttu-id="c62e7-365">無法自動探索 Exchange Server，因為憑證已遺失。</span><span class="sxs-lookup"><span data-stu-id="c62e7-365">Could not auto-discover the Exchange server because a certificate is missing.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-366">針對提供的裝置帳戶安裝所需的正確 ActiveSync 憑證。</span><span class="sxs-lookup"><span data-stu-id="c62e7-366">Install the correct ActiveSync certificate needed for the provided device account.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c62e7-367">0x80004005</span><span class="sxs-lookup"><span data-stu-id="c62e7-367">0x80004005</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-368">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c62e7-368">E_FAIL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-369">找不到提供的網域。</span><span class="sxs-lookup"><span data-stu-id="c62e7-369">The domain provided couldn't be found.</span></span> <span data-ttu-id="c62e7-370">無法自動探索 Exchange Server，且未在設定中提供它。</span><span class="sxs-lookup"><span data-stu-id="c62e7-370">The Exchange server could not be auto-discovered and was not provided in the settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="c62e7-371">請確定輸入的網域為 FQDN，並且已在 Exchange Server 文字方塊中輸入 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="c62e7-371">Make sure that the domain entered is the FQDN, and that there is an Exchange server entered in the Exchange server text box.</span></span></p></td>
</tr>
</tbody>
</table>

## <a name="contact-support"></a><span data-ttu-id="c62e7-372">連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="c62e7-372">Contact Support</span></span>

<span data-ttu-id="c62e7-373">如果您有任何疑問或需要協助，您可以[建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="c62e7-373">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


 
## <a name="related-content"></a><span data-ttu-id="c62e7-374">相關內容</span><span class="sxs-lookup"><span data-stu-id="c62e7-374">Related content</span></span>

- [<span data-ttu-id="c62e7-375">連線到 Surface Hub 的 Miracast 疑難排解</span><span class="sxs-lookup"><span data-stu-id="c62e7-375">Troubleshooting Miracast connection to the Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/miracast-troubleshooting)
 





