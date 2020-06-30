---
title: 混合式部署 (Surface Hub)
description: 混合式部署需要特殊處理，才能設定適用於 Microsoft Surface Hub 的裝置帳戶。
ms.assetid: 7BFBB7BE-F587-422E-9CE4-C9DDF829E4F1
ms.reviewer: ''
manager: laurawi
keywords: 混合式部署, Surface Hub 的裝置帳戶, Exchange 內部部署託管, Exchange 線上託管
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/30/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7444c3f31f7a144200a0b8b89cfa509ef7a7afc4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831829"
---
# <span data-ttu-id="ef9ff-104">混合式部署 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="ef9ff-104">Hybrid deployment (Surface Hub)</span></span>

<span data-ttu-id="ef9ff-105">混合式部署需要特殊處理，才能設定適用於 Microsoft Surface Hub 的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-105">A hybrid deployment requires special processing to set up a device account for your Microsoft Surface Hub.</span></span> <span data-ttu-id="ef9ff-106">如果您使用混合式部署 (您的組織具有混合的服務，其中有些是內部部署裝載的服務，有一些則是線上裝載的服務)，則您的組態將取決於裝載每個服務的位置。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-106">If you’re using a hybrid deployment, in which your organization has a mix of services, with some hosted on-premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="ef9ff-107">本主題探討 [內部部署託管 Exchange](#exchange-on-premises)、[線上託管 Exchange](#exchange-online)、商務用 Skype 內部部署、商務用 Skype Online，以及商務用 Skype 混合式部署。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-107">This topic covers hybrid deployments for [Exchange hosted on-premises](#exchange-on-premises), [Exchange hosted online](#exchange-online), Skype for Business on-premises, Skype for Business online, and Skype for Business hybrid.</span></span> <span data-ttu-id="ef9ff-108">由於這種類型的部署中有許多不同的變化，因此無法提供所有變化的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-108">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="ef9ff-109">下列程序將適用於多個組態。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-109">The following process will work for many configurations.</span></span> <span data-ttu-id="ef9ff-110">如果此程序不適合您的設定，我們建議您使用 PowerShell (請參閱[附錄：PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) 來達到此處所述的相同結果，並取得其他部署選項的說明。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-110">If the process isn't right for your setup, we recommend that you use PowerShell (see [Appendix: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) to achieve the same end result as documented here, and for other deployment options.</span></span> <span data-ttu-id="ef9ff-111">您接著應該使用提供的 PowerShell 指令碼來確認 Surface Hub 設定。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-111">You should then use the provided Powershell script to verify your Surface Hub setup.</span></span> <span data-ttu-id="ef9ff-112">(請參閱[帳戶驗證指令碼](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts))。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-112">(See [Account Verification Script](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts).)</span></span>

> [!NOTE]
> <span data-ttu-id="ef9ff-113">在 Exchange 混合式環境中，請依照[exchange 內部部署](#exchange-on-premises)的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-113">In an Exchange hybrid environment, follow the steps for [Exchange on-premises](#exchange-on-premises).</span></span> <span data-ttu-id="ef9ff-114">若要將 Exchange 物件移至 Office 365，請使用[MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-114">To move Exchange objects to Office 365, use the [New-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) cmdlet.</span></span>

## <span data-ttu-id="ef9ff-115">Exchange 內部部署</span><span class="sxs-lookup"><span data-stu-id="ef9ff-115">Exchange on-premises</span></span>

<span data-ttu-id="ef9ff-116">如果您使用 Exchange 內部部署，請使用此程序。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-116">Use this procedure if you use Exchange on-premises.</span></span>

1. <span data-ttu-id="ef9ff-117">進行此程序時，您要使用 AD 系統管理工具來新增內部部署網域帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-117">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span> <span data-ttu-id="ef9ff-118">此帳戶將同步處理至 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-118">This account will be synced to Office 365.</span></span>

- <span data-ttu-id="ef9ff-119">在 **[Active Directory 使用者和電腦]** AD 工具中，以滑鼠右鍵按一下將在其上建立 Surface Hub 帳戶的資料夾或組織單位，然後依序按一下 **[新增]** 和 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-119">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="ef9ff-120">在 **[完整名稱]** 方塊中輸入從上一個 Cmdlet 取得的顯示名稱，然後在 **[使用者登入名稱]** 方塊中輸入別名。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-120">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="ef9ff-121">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-121">Click **Next**.</span></span><p>

![在 Active Directory 中用來建立新使用者的新物件方塊。](images/hybriddeployment-01a.png)

- <span data-ttu-id="ef9ff-123">輸入此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-123">Type the password for this account.</span></span> <span data-ttu-id="ef9ff-124">您需要重新輸入密碼以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-124">You'll need to retype it for verification.</span></span> <span data-ttu-id="ef9ff-125">確定 **[密碼永久有效]** 核取方塊是唯一選取的選項。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-125">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> <span data-ttu-id="ef9ff-126">**重要** 您必須在 Surface Hub 上針對商務用 Skype 選取 **[密碼永久有效]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-126">**Important** Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="ef9ff-127">您的網域規則可能禁止使用不會過期的密碼。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-127">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="ef9ff-128">如果是這樣，您就需要為每個 Surface Hub 裝置帳戶建立例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-128">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![顯示密碼對話方塊的影像。](images/hybriddeployment-02a.png)

-   <span data-ttu-id="ef9ff-130">按一下 **[完成]** 以建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-130">Click **Finish** to create the account.</span></span>

![顯示新使用者的帳戶名稱、登入名稱及密碼選項的影像。](images/hybriddeployment-03a.png)

2. <span data-ttu-id="ef9ff-132">啟用遠端信箱。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-132">Enable the remote mailbox.</span></span>

<span data-ttu-id="ef9ff-133">以系統管理員權限開啟內部部署 Exchange 管理命令介面，並執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-133">Open your on-premises Exchange Management Shell with administrator permissions, and run this cmdlet.</span></span>

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> <span data-ttu-id="ef9ff-134">如果您沒有內部部署 Exchange 環境來執行此 Cmdlet，可以直接對帳戶的 Active Directory 物件進行相同的變更。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-134">If you don't have an on-premises Exchange environment to run this cmdlet, you can make the same changes directly to the Active Directory object for the account.</span></span>
>
> <span data-ttu-id="ef9ff-135">msExchRemoteRecipientType = 33</span><span class="sxs-lookup"><span data-stu-id="ef9ff-135">msExchRemoteRecipientType = 33</span></span>
>
> <span data-ttu-id="ef9ff-136">msExchRecipientDisplayType = -2147481850</span><span class="sxs-lookup"><span data-stu-id="ef9ff-136">msExchRecipientDisplayType = -2147481850</span></span>
>
> <span data-ttu-id="ef9ff-137">msExchRecipientTypeDetails = 8589934592</span><span class="sxs-lookup"><span data-stu-id="ef9ff-137">msExchRecipientTypeDetails = 8589934592</span></span>

3. <span data-ttu-id="ef9ff-138">建立帳戶之後，請執行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-138">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="ef9ff-139">完成後，請移至 Microsoft 365 系統管理中心的 [使用者] 頁面，確認在先前步驟中建立的帳戶已合併至 [線上]。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-139">When it's complete, go to the users page in your Microsoft 365 admin center and verify that the account created in the previous steps has merged to online.</span></span>

4. <span data-ttu-id="ef9ff-140">連線到 Microsoft Exchange Online，並在 Office 365 中設定帳戶的某些屬性。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-140">Connect to Microsoft Exchange Online and set some properties for the account in Office 365.</span></span>

<span data-ttu-id="ef9ff-141">在電腦上啟動遠端 PowerShell 工作階段，並連線到 Microsoft Exchange。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-141">Start a remote PowerShell session on a PC and connect to Microsoft Exchange.</span></span> <span data-ttu-id="ef9ff-142">確定您已設定正確的權限來執行相關聯的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-142">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

<span data-ttu-id="ef9ff-143">後續步驟將在您的 Office 365 租用戶上執行。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-143">The next steps will be run on your Office 365 tenant.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. <span data-ttu-id="ef9ff-144">建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-144">Create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="ef9ff-145">設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-145">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy or use a compatible existing policy.</span></span>

<span data-ttu-id="ef9ff-146">Surface Hub 只會與具有 ActiveSync 原則且已將 **PasswordEnabled** 屬性設為 False 的裝置帳戶相容。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-146">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="ef9ff-147">如果未正確設定此屬性，將無法啟用 Surface Hub 上的 Exchange 服務 (電子郵件、行事曆及加入會議)。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-147">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

<span data-ttu-id="ef9ff-148">如果您尚未建立相容的原則，請使用下列 Cmdlet，此 Cmdlet 會建立名為 "Surface Hubs" 的原則。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-148">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="ef9ff-149">一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-149">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="ef9ff-150">一旦您擁有相容的原則，就必須將原則套用到裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-150">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. <span data-ttu-id="ef9ff-151">設定 Exchange 屬性</span><span class="sxs-lookup"><span data-stu-id="ef9ff-151">Set Exchange properties.</span></span>

<span data-ttu-id="ef9ff-152">在裝置帳戶上設定 Exchange 屬性來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-152">Setting Exchange properties on the device account to improve the meeting experience.</span></span> <span data-ttu-id="ef9ff-153">您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md) 一節中看到需要設定哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-153">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. <span data-ttu-id="ef9ff-154">連線到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-154">Connect to Azure AD.</span></span>

<span data-ttu-id="ef9ff-155">您首先需要安裝 PowerShell 版本 2 的 Azure AD 模組。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-155">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="ef9ff-156">在提升許可權的 PowerShell 提示中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-156">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="ef9ff-157">您需要連線到 Azure AD，以套用一些帳戶設定。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-157">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="ef9ff-158">您可以執行這個 Cmdlet 來連線。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-158">You can run this cmdlet to connect.</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="ef9ff-159">指派 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-159">Assign an Office 365 license.</span></span>

<span data-ttu-id="ef9ff-160">裝置帳戶必須具備有效的 Office 365 (O365) 授權，否則 Exchange 和商務用 Skype 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-160">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="ef9ff-161">如果您具有授權，就需要將使用位置指派給您的裝置帳戶，這會決定哪些授權 SKU 可供您的帳戶使用。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-161">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="ef9ff-162">您可以使用 `Get-AzureADSubscribedSku` 擷取可供 O365 租用戶使用的 SKU 清單。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-162">You can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="ef9ff-163">列出 SKU 後，就必須將您想要的 SkuId 指派給 `$License.SkuId` 變數。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-163">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

<span data-ttu-id="ef9ff-164">接下來，您可以搭配[商務用 Skype Online](#skype-for-business-online)、[商務用 Skype 內部部署](#skype-for-business-on-premises)，或[商務用 Skype Hybrid](#skype-for-business-hybrid) 啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-164">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="ef9ff-165">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="ef9ff-165">Skype for Business Online</span></span>

<span data-ttu-id="ef9ff-166">您的租用戶使用者必須有 Exchange 信箱 (租用戶中至少需有一個 Exchange 信箱)。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-166">To enable Skype for Business online, your tenant users must have Exchange mailboxes (at least one Exchange mailbox in the tenant is required).</span></span> <span data-ttu-id="ef9ff-167">下表說明您需要哪些方案或其他服務。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-167">The following table explains which plans or additional services you need.</span></span>

| <span data-ttu-id="ef9ff-168">Skype 會議室系統案例</span><span class="sxs-lookup"><span data-stu-id="ef9ff-168">Skype room system scenario</span></span> | <span data-ttu-id="ef9ff-169">如果您有 Office 365 Premium、適用于企業的 Microsoft 365 應用程式，或商務用 Skype 獨立方案2，您需要：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-169">If you have Office 365 Premium, Microsoft 365 Apps for enterprise, or Skype for Business Standalone Plan 2, you need:</span></span> | <span data-ttu-id="ef9ff-170">如果您擁有企業方案，您需要：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-170">If you have an Enterprise-based plan, you need:</span></span> | <span data-ttu-id="ef9ff-171">如果您有商務用 Skype Server 2015 （內部部署或混合式），您需要：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-171">If you have Skype for Business Server 2015 (on-premises or hybrid), you need:</span></span> |
| --- | --- | --- | --- |
| <span data-ttu-id="ef9ff-172">加入已排程的會議</span><span class="sxs-lookup"><span data-stu-id="ef9ff-172">Join a scheduled meeting</span></span> | <span data-ttu-id="ef9ff-173">商務用 Skype 獨立方案 1</span><span class="sxs-lookup"><span data-stu-id="ef9ff-173">Skype for Business Standalone Plan 1</span></span> | <span data-ttu-id="ef9ff-174">E1、3、4 或 5</span><span class="sxs-lookup"><span data-stu-id="ef9ff-174">E1, 3, 4, or 5</span></span> | <span data-ttu-id="ef9ff-175">商務用 Skype Server Standard CAL</span><span class="sxs-lookup"><span data-stu-id="ef9ff-175">Skype for Business Server Standard CAL</span></span> |
| <span data-ttu-id="ef9ff-176">起始臨時會議</span><span class="sxs-lookup"><span data-stu-id="ef9ff-176">Initiate an ad-hoc meeting</span></span> | <span data-ttu-id="ef9ff-177">商務用 Skype 獨立方案 2 </span><span class="sxs-lookup"><span data-stu-id="ef9ff-177">Skype for Business Standalone Plan 2</span></span> | <span data-ttu-id="ef9ff-178">E 1、3、4 或 5</span><span class="sxs-lookup"><span data-stu-id="ef9ff-178">E 1, 3, 4, or 5</span></span> | <span data-ttu-id="ef9ff-179">商務用 Skype Server Standard CAL 或 Enterprise CAL</span><span class="sxs-lookup"><span data-stu-id="ef9ff-179">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="ef9ff-180">起始臨時會議並從會議撥出電話號碼</span><span class="sxs-lookup"><span data-stu-id="ef9ff-180">Initiate an ad-hoc meeting and dial out from a meeting to phone numbers</span></span> | <span data-ttu-id="ef9ff-181">商務用 Skype 獨立方案2與音訊會議</span><span class="sxs-lookup"><span data-stu-id="ef9ff-181">Skype for Business Standalone Plan 2 with Audio Conferencing</span></span></br></br><span data-ttu-id="ef9ff-182">**注意**PSTN 消費帳單為選用</span><span class="sxs-lookup"><span data-stu-id="ef9ff-182">**Note** PSTN consumption billing is optional</span></span> | <span data-ttu-id="ef9ff-183">使用音訊會議或 E5 的 E1 或 E3</span><span class="sxs-lookup"><span data-stu-id="ef9ff-183">E1 or E3 with Audio Conferencing, or E5</span></span>| <span data-ttu-id="ef9ff-184">商務用 Skype Server Standard CAL 或 Enterprise CAL</span><span class="sxs-lookup"><span data-stu-id="ef9ff-184">Skype for Business Server Standard CAL or Enterprise CAL</span></span> |
| <span data-ttu-id="ef9ff-185">提供會議室電話號碼、從會議室撥出電話或接電話，或使用的電話號碼加入會議</span><span class="sxs-lookup"><span data-stu-id="ef9ff-185">Give the room a phone number and make or receive calls from the room or join a dial-in conference using a phone number</span></span> | <span data-ttu-id="ef9ff-186">商務用 Skype 獨立方案2與電話系統和 PSTN 語音通話方案</span><span class="sxs-lookup"><span data-stu-id="ef9ff-186">Skype for Business Standalone Plan 2 with Phone System and a PSTN Voice Calling plan</span></span> | <span data-ttu-id="ef9ff-187">[E1] 或 [E3] 與 [電話系統] 與 [PSTN 語音通話方案] 或 [E5]</span><span class="sxs-lookup"><span data-stu-id="ef9ff-187">E1 or E3 with Phone System and a PSTN Voice Calling plan, or E5</span></span> | <span data-ttu-id="ef9ff-188">商務用 Skype Server Standard CAL 或 Plus CAL</span><span class="sxs-lookup"><span data-stu-id="ef9ff-188">Skype for Business Server Standard CAL or Plus CAL</span></span> |

<span data-ttu-id="ef9ff-189">下表列出 Office 365 方案和商務用 Skype 選項。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-189">The following table lists the Office 365 plans and Skype for Business options.</span></span>

| <span data-ttu-id="ef9ff-190">O365 方案</span><span class="sxs-lookup"><span data-stu-id="ef9ff-190">O365 Plan</span></span> | <span data-ttu-id="ef9ff-191">商務用 Skype</span><span class="sxs-lookup"><span data-stu-id="ef9ff-191">Skype for Business</span></span> | <span data-ttu-id="ef9ff-192">電話系統</span><span class="sxs-lookup"><span data-stu-id="ef9ff-192">Phone System</span></span> | <span data-ttu-id="ef9ff-193">音訊會議</span><span class="sxs-lookup"><span data-stu-id="ef9ff-193">Audio Conferencing</span></span> | <span data-ttu-id="ef9ff-194">通話方案</span><span class="sxs-lookup"><span data-stu-id="ef9ff-194">Calling Plans</span></span> |
| --- | --- | --- | --- | --- |
| <span data-ttu-id="ef9ff-195">O365 商務基本版</span><span class="sxs-lookup"><span data-stu-id="ef9ff-195">O365 Business Essentials</span></span> | <span data-ttu-id="ef9ff-196">內含</span><span class="sxs-lookup"><span data-stu-id="ef9ff-196">Included</span></span> |  |  |  |
| <span data-ttu-id="ef9ff-197">O365 商務進階版</span><span class="sxs-lookup"><span data-stu-id="ef9ff-197">O365 Business Premium</span></span> | <span data-ttu-id="ef9ff-198">內含</span><span class="sxs-lookup"><span data-stu-id="ef9ff-198">Included</span></span> |  |  |  |
| <span data-ttu-id="ef9ff-199">E1</span><span class="sxs-lookup"><span data-stu-id="ef9ff-199">E1</span></span> | <span data-ttu-id="ef9ff-200">內含</span><span class="sxs-lookup"><span data-stu-id="ef9ff-200">Included</span></span> | <span data-ttu-id="ef9ff-201">附加元件</span><span class="sxs-lookup"><span data-stu-id="ef9ff-201">Add-on</span></span> | <span data-ttu-id="ef9ff-202">附加元件</span><span class="sxs-lookup"><span data-stu-id="ef9ff-202">Add-on</span></span> | <span data-ttu-id="ef9ff-203">附加元件（需要電話系統附加元件）</span><span class="sxs-lookup"><span data-stu-id="ef9ff-203">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="ef9ff-204">E3</span><span class="sxs-lookup"><span data-stu-id="ef9ff-204">E3</span></span> | <span data-ttu-id="ef9ff-205">內含</span><span class="sxs-lookup"><span data-stu-id="ef9ff-205">Included</span></span> | <span data-ttu-id="ef9ff-206">附加元件</span><span class="sxs-lookup"><span data-stu-id="ef9ff-206">Add-on</span></span> | <span data-ttu-id="ef9ff-207">附加元件</span><span class="sxs-lookup"><span data-stu-id="ef9ff-207">Add-on</span></span> | <span data-ttu-id="ef9ff-208">附加元件（需要電話系統附加元件）</span><span class="sxs-lookup"><span data-stu-id="ef9ff-208">Add-on (requires Phone System add-on)</span></span> |
| <span data-ttu-id="ef9ff-209">E5</span><span class="sxs-lookup"><span data-stu-id="ef9ff-209">E5</span></span> | <span data-ttu-id="ef9ff-210">內含</span><span class="sxs-lookup"><span data-stu-id="ef9ff-210">Included</span></span> | <span data-ttu-id="ef9ff-211">內含</span><span class="sxs-lookup"><span data-stu-id="ef9ff-211">Included</span></span> | <span data-ttu-id="ef9ff-212">內含</span><span class="sxs-lookup"><span data-stu-id="ef9ff-212">Included</span></span> | <span data-ttu-id="ef9ff-213">附加元件</span><span class="sxs-lookup"><span data-stu-id="ef9ff-213">Add-on</span></span>  |

1. <span data-ttu-id="ef9ff-214">請從電腦對商務用 Skype Online 環境建立遠端 PowerShell 工作階段做為開始。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-214">Start by creating a remote PowerShell session from a PC to the Skype for Business online environment.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="ef9ff-215">若要針對商務用 Skype Server 啟用您的 Surface Hub 帳戶，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-215">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

<span data-ttu-id="ef9ff-216">如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet，從現有的商務用 Skype 使用者取得值：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-216">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. <span data-ttu-id="ef9ff-217">將商務用 Skype 授權指派給您的 Surface Hub 帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-217">Assign Skype for Business license to your Surface Hub account.</span></span>

 <span data-ttu-id="ef9ff-218">當您完成先前步驟以在商務用 Skype Online 上啟用 Surface Hub 帳戶之後，您需要將授權指派給 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-218">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="ef9ff-219">使用 O365 管理入口網站，將商務用 Skype Online （方案2）或商務用 Skype Online （方案3）授權指派到裝置。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-219">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="ef9ff-220">以租用戶系統管理員身分登入、開啟 O365 系統管理入口網站，然後按一下 [系統管理] app。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-220">Login as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="ef9ff-221">依序按一下 **[使用者和群組]** 和 **[新增使用者、重設密碼及其他]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-221">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="ef9ff-222">按一下 Surface Hub 帳戶，然後按一下畫筆圖示來編輯帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-222">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="ef9ff-223">按一下 **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-223">Click **Licenses**.</span></span>

- <span data-ttu-id="ef9ff-224">在 [**指派授權**] 中，選取 [商務用 Skype （方案1）] 或 [商務用 Skype （方案2）]，視您的授權和企業語音需求而定。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-224">In **Assign licenses**, select Skype for Business (Plan 1) or Skype for Business (Plan 2), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="ef9ff-225">如果您想要在 Surface Hub 上使用企業語音，就必須使用 [方案2授權]。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-225">You'll have to use a Plan 2 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="ef9ff-226">按一下 **\[儲存\]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-226">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ef9ff-227">您也可以使用適用於 Windows PowerShell 的 Windows Azure Active Directory 模組，來執行指派這其中一個授權所需的 Cmdlet，但此處並未涵蓋相關說明。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-227">You can also use the Windows Azure Active Directory Module for Windows Powershell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="ef9ff-228">若要進行驗證，您應該能夠使用任一個商務用 Skype 用戶端 (電腦、Android 等) 來登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-228">For validation, you should be able to use any Skype for Business client (PC, Android, etc.) to sign in to this account.</span></span>

### <span data-ttu-id="ef9ff-229">商務用 Skype 內部部署</span><span class="sxs-lookup"><span data-stu-id="ef9ff-229">Skype for Business on-premises</span></span>

<span data-ttu-id="ef9ff-230">若要執行此 Cmdlet，您需要連線到其中一個 Skype 前端。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-230">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="ef9ff-231">開啟 Skype PowerShell 並執行：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-231">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="ef9ff-232">商務用 Skype Hybrid</span><span class="sxs-lookup"><span data-stu-id="ef9ff-232">Skype for Business hybrid</span></span>

<span data-ttu-id="ef9ff-233">如果您的組織已經設定[商務用 Skype 伺服器和商務用 Skype Online 之間的混合式連線](https://technet.microsoft.com/library/jj205403.aspx)，建立帳戶的指導方針就會和標準 Surface Hub 部署不一樣。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-233">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="ef9ff-234">Surface Hub 需要 `meetingroom` 類型的 Skype 帳戶，一般的使用者則是在 Skype 中使用 user 類型帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-234">The Surface Hub requires a Skype account of the type `meetingroom`, while a normal user would use a user type account in Skype.</span></span> <span data-ttu-id="ef9ff-235">如果您的 Skype 伺服器是針對混合式設定，其中可能有位於本機 Skype 伺服器的使用者和在 Office 365 中裝載的使用者，您可能會在嘗試建立 Surface Hub 帳戶時遇到幾個問題。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-235">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="ef9ff-236">在商務用 Skype Server 2015 的混合式環境中，您要在商務用 Skype Online 中的任何使用者，都必須先在內部部署中建立，才能在 Active Directory 網域服務中建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-236">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="ef9ff-237">然後，您可以將使用者移至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-237">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="ef9ff-238">從內部部署到線上的使用者帳戶移動是透過[move-csuser](https://technet.microsoft.com/library/gg398528.aspx) Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-238">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="ef9ff-239">若要移動 Csmeetingroom 物件，請使用[Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-239">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="ef9ff-240">若要使用 CsMeetingRoom Cmdlet，您必須已[針對商務用 Skype server 2015 安裝 2017 2017 年5月累積更新 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ，或安裝[Lync Server 2013 的累計更新 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-240">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>


## <span data-ttu-id="ef9ff-241">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ef9ff-241">Exchange online</span></span>

<span data-ttu-id="ef9ff-242">如果您使用 Exchange Online，請使用此程序。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-242">Use this procedure if you use Exchange online.</span></span>

1. <span data-ttu-id="ef9ff-243">在 Office 365 中建立電子郵件帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-243">Create an email account in Office 365.</span></span>

<span data-ttu-id="ef9ff-244">在電腦上啟動遠端 PowerShell 工作階段，並連線到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-244">Start a remote PowerShell session on a PC and connect to Exchange.</span></span> <span data-ttu-id="ef9ff-245">確定您已設定正確的權限來執行相關聯的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-245">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. <span data-ttu-id="ef9ff-246">設定信箱。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-246">Set up a mailbox.</span></span>

<span data-ttu-id="ef9ff-247">建立工作階段之後，您將建立新的信箱並啟用為 RoomMailboxAccount，或是變更現有會議室信箱的設定。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-247">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="ef9ff-248">這可讓帳戶向 Surface Hub 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-248">This will allow the account to authenticate into the Surface Hub.</span></span>

<span data-ttu-id="ef9ff-249">如果您正在變更現有的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-249">If you're changing an existing resource mailbox:</span></span>

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

<span data-ttu-id="ef9ff-250">如果您正在建立新的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-250">If you’re creating a new resource mailbox:</span></span>

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. <span data-ttu-id="ef9ff-251">建立 Exchange ActiveSync 原則。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-251">Create Exchange ActiveSync policy.</span></span>

<span data-ttu-id="ef9ff-252">設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-252">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

<span data-ttu-id="ef9ff-253">Surface Hub 只會與具有已將 **PasswordEnabled** 屬性設為 False 之 ActiveSync 原則的裝置帳戶相容。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-253">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="ef9ff-254">如果未正確設定，表面中樞（[郵件]、[行事曆] 和 [加入會議]）上的 Exchange 服務將不會啟用。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-254">If this isn’t set properly, Exchange services on the Surface Hub (mail, calendar, and joining meetings) will not be enabled.</span></span>

<span data-ttu-id="ef9ff-255">如果您尚未建立相容的原則，請使用下列 Cmdlet，此 Cmdlet 會建立名為 "Surface Hubs" 的原則。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-255">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="ef9ff-256">一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-256">Once it’s created, you can apply the same policy to other device accounts.</span></span>

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

<span data-ttu-id="ef9ff-257">一旦您擁有相容的原則，就必須將原則套用到裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-257">Once you have a compatible policy, you will need to apply the policy to the device account.</span></span> <span data-ttu-id="ef9ff-258">不過，原則只能套用到使用者帳戶，不能套用到資源信箱。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-258">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="ef9ff-259">您需要將信箱轉換成使用者類型、套用原則，然後將它轉換回信箱 - 您可能也需要重新啟用它並再次設定密碼。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-259">You need to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox—you may need to re-enable it and set the password again too.</span></span>

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. <span data-ttu-id="ef9ff-260">設定 Exchange 屬性</span><span class="sxs-lookup"><span data-stu-id="ef9ff-260">Set Exchange properties.</span></span>

<span data-ttu-id="ef9ff-261">您必須在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-261">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="ef9ff-262">您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)區段中查看需要設定哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-262">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. <span data-ttu-id="ef9ff-263">新增內部部署網域帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-263">Add an email address for your on-premises domain account.</span></span>

<span data-ttu-id="ef9ff-264">進行此程序時，您要使用 AD 系統管理工具來新增內部部署網域帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-264">For this procedure, you'll be using AD admin tools to add an email address for your on-premises domain account.</span></span>

- <span data-ttu-id="ef9ff-265">在 **[Active Directory 使用者和電腦]** AD 工具中，以滑鼠右鍵按一下將在其上建立 Surface Hub 帳戶的資料夾或組織單位，然後依序按一下 **[新增]** 和 **[使用者]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-265">In **Active Directory Users and Computers** AD tool, right-click on the folder or Organizational Unit that your Surface Hub accounts will be created in, click **New**, and **User**.</span></span>
- <span data-ttu-id="ef9ff-266">在 **[完整名稱]** 方塊中輸入從上一個 Cmdlet 取得的顯示名稱，然後在 **[使用者登入名稱]** 方塊中輸入別名。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-266">Type the display name from the previous cmdlet into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="ef9ff-267">按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-267">Click **Next**.</span></span>

![在 Active Directory 中用來建立新使用者的新物件方塊。](images/hybriddeployment-01a.png)

- <span data-ttu-id="ef9ff-269">輸入此帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-269">Type the password for this account.</span></span> <span data-ttu-id="ef9ff-270">您需要重新輸入密碼以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-270">You'll need to retype it for verification.</span></span> <span data-ttu-id="ef9ff-271">確定 **[密碼永久有效]** 核取方塊是唯一選取的選項。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-271">Make sure the **Password never expires** checkbox is the only option selected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef9ff-272">選取 [**密碼永不過期**] 是對 Surface Hub 上的商務用 Skype 的需求。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-272">Selecting **Password never expires** is a requirement for Skype for Business on the Surface Hub.</span></span> <span data-ttu-id="ef9ff-273">您的網域規則可能禁止使用不會過期的密碼。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-273">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="ef9ff-274">如果是這樣，您就需要為每個 Surface Hub 裝置帳戶建立例外狀況。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-274">If so, you'll need to create an exception for each Surface Hub device account.</span></span>

![顯示密碼對話方塊的影像。](images/hybriddeployment-02a.png)

- <span data-ttu-id="ef9ff-276">按一下 **[完成]** 以建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-276">Click **Finish** to create the account.</span></span>

![顯示新使用者的帳戶名稱、登入名稱及密碼選項的影像。](images/hybriddeployment-03a.png)

6. <span data-ttu-id="ef9ff-278">執行目錄同步作業。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-278">Run directory synchronization.</span></span>

<span data-ttu-id="ef9ff-279">建立帳戶之後，請執行目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-279">After you've created the account, run a directory synchronization.</span></span> <span data-ttu-id="ef9ff-280">完成時，請移至使用者頁面，並確認已合併先前步驟中所建立的兩個帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-280">When it's complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

7. <span data-ttu-id="ef9ff-281">連線到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-281">Connect to Azure AD.</span></span>

<span data-ttu-id="ef9ff-282">您首先需要安裝 PowerShell 版本 2 的 Azure AD 模組。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-282">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="ef9ff-283">在提升許可權的 PowerShell 提示中，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-283">In an elevated PowerShell prompt, run the following command:</span></span>

```PowerShell
Install-Module -Name AzureAD
```

<span data-ttu-id="ef9ff-284">您需要連線到 Azure AD，以套用一些帳戶設定。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-284">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="ef9ff-285">您可以執行此 Cmdlet 來進行連接：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-285">You can run this cmdlet to connect:</span></span>

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. <span data-ttu-id="ef9ff-286">指派 Office 365 授權。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-286">Assign an Office 365 license.</span></span>

<span data-ttu-id="ef9ff-287">裝置帳戶必須具備有效的 Office 365 (O365) 授權，否則 Exchange 和商務用 Skype 將無法運作。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-287">The device account needs to have a valid Office 365 (O365) license, or Exchange and Skype for Business will not work.</span></span> <span data-ttu-id="ef9ff-288">如果您具有授權，就需要將使用位置指派給您的裝置帳戶，這會決定哪些授權 SKU 可供您的帳戶使用。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-288">If you have the license, you need to assign a usage location to your device account—this determines what license SKUs are available for your account.</span></span>

<span data-ttu-id="ef9ff-289">接下來，您可以使用 `Get-AzureADSubscribedSku` 擷取可供 O365 租用戶使用的 SKU 清單。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-289">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

<span data-ttu-id="ef9ff-290">列出 SKU 後，就必須將您想要的 SkuId 指派給 `$License.SkuId` 變數。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-290">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

```PowerShell
Set-AzureADUser -ObjectId "HUB01@contoso.com" -UsageLocation "US"

Get-AzureADSubscribedSku | Select Sku*,*Units
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = SkuId You selected 

$AssignedLicenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$AssignedLicenses.AddLicenses = $License
$AssignedLicenses.RemoveLicenses = @()

Set-AzureADUserLicense -ObjectId "HUB01@contoso.com"  -AssignedLicenses $AssignedLicenses
```

<span data-ttu-id="ef9ff-291">接下來，您可以搭配[商務用 Skype Online](#skype-for-business-online)、[商務用 Skype 內部部署](#skype-for-business-on-premises)，或[商務用 Skype Hybrid](#skype-for-business-hybrid) 啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-291">Next, you enable the device account with [Skype for Business Online](#skype-for-business-online), [Skype for Business on-premises](#skype-for-business-on-premises), or [Skype for Business hybrid](#skype-for-business-hybrid).</span></span>

### <span data-ttu-id="ef9ff-292">商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="ef9ff-292">Skype for Business Online</span></span>

<span data-ttu-id="ef9ff-293">若要啟用商務用 Skype，您的環境必須[符合商務用 Skype Online 的先決條件](#skype-for-business-online)：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-293">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](#skype-for-business-online).</span></span>

1. <span data-ttu-id="ef9ff-294">請從透過電腦建立商務用 Skype Online 環境的遠端 PowerShell 工作階段開始著手。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-294">Start by creating a remote PowerShell session to the Skype for Business online environment from a PC.</span></span>

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. <span data-ttu-id="ef9ff-295">若要針對商務用 Skype Server 啟用您的 Surface Hub 帳戶，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-295">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   <span data-ttu-id="ef9ff-296">如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet，從現有的商務用 Skype 使用者取得值：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-296">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. <span data-ttu-id="ef9ff-297">將商務用 Skype 授權指派給您的 Surface Hub 帳戶</span><span class="sxs-lookup"><span data-stu-id="ef9ff-297">Assign Skype for Business license to your Surface Hub account</span></span>

<span data-ttu-id="ef9ff-298">當您完成先前步驟以在商務用 Skype Online 上啟用 Surface Hub 帳戶之後，您需要將授權指派給 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-298">Once you've completed the preceding steps to enable your Surface Hub account in Skype for Business Online, you need to assign a license to the Surface Hub.</span></span> <span data-ttu-id="ef9ff-299">使用 O365 管理入口網站，將商務用 Skype Online （方案2）或商務用 Skype Online （方案3）授權指派到裝置。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-299">Using the O365 administrative portal, assign either a Skype for Business Online (Plan 2) or a Skype for Business Online (Plan 3) license to the device.</span></span>

- <span data-ttu-id="ef9ff-300">以租用戶系統管理員身分登入、開啟 O365 系統管理入口網站，然後按一下 \[系統管理\] app。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-300">Sign in as a tenant administrator, open the O365 Administrative Portal, and click on the Admin app.</span></span>

- <span data-ttu-id="ef9ff-301">依序按一下 **\[使用者和群組\]** 和 **\[新增使用者、重設密碼及其他\]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-301">Click on **Users and Groups** and then **Add users, reset passwords, and more**.</span></span>

- <span data-ttu-id="ef9ff-302">按一下 Surface Hub 帳戶，然後按一下畫筆圖示來編輯帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-302">Click the Surface Hub account, and then click the pen icon to edit the account information.</span></span>

- <span data-ttu-id="ef9ff-303">按一下 **[授權]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-303">Click **Licenses**.</span></span>

- <span data-ttu-id="ef9ff-304">在 **[指派授權]** 中，根據您的授權和企業語音需求來選取商務用 Skype (方案 2) 或商務用 Skype (方案 3)。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-304">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="ef9ff-305">如果您想要在 Surface Hub 上使用企業語音，就必須使用方案 3 授權。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-305">You'll have to use a Plan 3 license if you want to use Enterprise Voice on your Surface Hub.</span></span>

- <span data-ttu-id="ef9ff-306">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-306">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="ef9ff-307">您也可以使用適用於 Windows PowerShell 的 Windows Azure Active Directory 模組，來執行指派這其中一個授權所需的 Cmdlet，但此處並未涵蓋相關說明。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-307">You can also use the Windows Azure Active Directory Module for Windows PowerShell to run the cmdlets needed to assign one of these licenses, but that's not covered here.</span></span>

<span data-ttu-id="ef9ff-308">若要進行驗證，您必須能夠使用任何商務用 Skype 用戶端 (電腦、Android 等) 來登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-308">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>

### <span data-ttu-id="ef9ff-309">商務用 Skype 內部部署</span><span class="sxs-lookup"><span data-stu-id="ef9ff-309">Skype for Business on-premises</span></span>

<span data-ttu-id="ef9ff-310">若要執行此 Cmdlet，您需要連線到其中一個 Skype 前端。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-310">To run this cmdlet, you will need to connect to one of the Skype front-ends.</span></span> <span data-ttu-id="ef9ff-311">開啟 Skype PowerShell 並執行：</span><span class="sxs-lookup"><span data-stu-id="ef9ff-311">Open the Skype PowerShell and run:</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### <span data-ttu-id="ef9ff-312">商務用 Skype Hybrid</span><span class="sxs-lookup"><span data-stu-id="ef9ff-312">Skype for Business hybrid</span></span>

<span data-ttu-id="ef9ff-313">如果您的組織已經設定[商務用 Skype 伺服器和商務用 Skype Online 之間的混合式連線](https://technet.microsoft.com/library/jj205403.aspx)，建立帳戶的指導方針就會和標準 Surface Hub 部署不一樣。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-313">If your organization has set up [hybrid connectivity between Skype for Business Server and Skype for Business Online](https://technet.microsoft.com/library/jj205403.aspx), the guidance for creating accounts differs from a standard Surface Hub deployment.</span></span>

<span data-ttu-id="ef9ff-314">Surface Hub 需要 *meetingroom* 類型的 Skype 帳戶，一般的使用者則是在 Skype 中使用 *user* 類型帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-314">The Surface Hub requires a Skype account of the type *meetingroom*, while a normal user would use a *user* type account in Skype.</span></span> <span data-ttu-id="ef9ff-315">如果您的 Skype 伺服器是針對混合式設定，其中可能有位於本機 Skype 伺服器的使用者和在 Office 365 中裝載的使用者，您可能會在嘗試建立 Surface Hub 帳戶時遇到幾個問題。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-315">If your Skype server is set up for hybrid where you might have users on the local Skype server as well as users hosted in Office 365, you might run into a few issues when trying to create a Surface Hub account.</span></span>

<span data-ttu-id="ef9ff-316">在商務用 Skype Server 2015 的混合式環境中，您要在商務用 Skype Online 中的任何使用者，都必須先在內部部署中建立，才能在 Active Directory 網域服務中建立使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-316">In Skype for Business Server 2015 hybrid environment, any user that you want in Skype for Business Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="ef9ff-317">然後，您可以將使用者移至商務用 Skype Online。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-317">You can then move the user to Skype for Business Online.</span></span> <span data-ttu-id="ef9ff-318">從內部部署到線上的使用者帳戶移動是透過[move-csuser](https://technet.microsoft.com/library/gg398528.aspx) Cmdlet 來完成。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-318">The move of a user account from on-premises to online is done via the [Move-CsUser](https://technet.microsoft.com/library/gg398528.aspx) cmdlet.</span></span> <span data-ttu-id="ef9ff-319">若要移動 Csmeetingroom 物件，請使用[Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-319">To move a Csmeetingroom object, use the [Move-CsMeetingRoom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) cmdlet.</span></span>

> [!NOTE]
> <span data-ttu-id="ef9ff-320">若要使用 CsMeetingRoom Cmdlet，您必須已[針對商務用 Skype server 2015 安裝 2017 2017 年5月累積更新 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ，或安裝[Lync Server 2013 的累計更新 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)。</span><span class="sxs-lookup"><span data-stu-id="ef9ff-320">To use the Move-CsMeetingRoom cmdlet, you must have installed [the May 2017 cumulative update 6.0.9319.281 for Skype for Business Server 2015](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) or [the July 2017 cumulative update 5.0.8308.992 for Lync Server 2013](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p).</span></span>
