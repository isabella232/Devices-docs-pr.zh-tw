---
title: 內部部署多樹系 (Surface Hub)
description: 本主題說明當您擁有多樹系的內部部署時，如何為您的 Microsoft Surface Hub 新增裝置帳戶。
keywords: multi forest deployment, on prem deployment, device account, Surface Hub, 多樹系部署, 內部部署, 裝置帳戶
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 48fe874175a2c55b7e95ba0974cefe29f710c134
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831794"
---
# <span data-ttu-id="04f0f-104">在多樹系環境中的 Surface Hub 內部部署</span><span class="sxs-lookup"><span data-stu-id="04f0f-104">On-premises deployment for Surface Hub in a multi-forest environment</span></span>


<span data-ttu-id="04f0f-105">本主題說明當您擁有多樹系的內部部署時，如何為您的 Microsoft Surface Hub 新增裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="04f0f-105">This topic explains how you add a device account for your Microsoft Surface Hub when you have a multi-forest, on-premises deployment.</span></span>

<span data-ttu-id="04f0f-106">如果您擁有使用 Microsoft Exchange 2013 或更新版本以及商務用 Skype 2013 或更新版本的多樹系內部部署，則可[使用提供的 PowerShell 指令碼](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts)來建立裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="04f0f-106">If you have a multi-forest on-premises deployment with Microsoft Exchange 2013 or later and Skype for Business 2013 or later, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts) to create device accounts.</span></span> <span data-ttu-id="04f0f-107">如果您使用單一樹系部署，請參閱[在單一樹系環境中的 Surface Hub 內部部署](on-premises-deployment-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="04f0f-107">If you’re using a single-forest deployment, see [On-premises deployment for Surface Hub in a single-forest environment](on-premises-deployment-surface-hub-device-accounts.md).</span></span>

1.  <span data-ttu-id="04f0f-108">從電腦上啟動遠端 PowerShell 工作階段，並連線到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="04f0f-108">Start a remote PowerShell session from a PC and connect to Exchange.</span></span>

    <span data-ttu-id="04f0f-109">確定您已設定正確的權限來執行相關聯的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="04f0f-109">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

    <span data-ttu-id="04f0f-110">請注意此處的 `$strExchangeServer` 是 Exchange Server 的完整網域名稱 (FQDN)，而 `$strLyncFQDN` 是商務用 Skype Server 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="04f0f-110">Note here that `$strExchangeServer` is the fully qualified domain name (FQDN) of your Exchange server, and `$strLyncFQDN` is the FQDN of your Skype for Business server.</span></span>

    ```PowerShell
    Set-ExecutionPolicy Unrestricted
    $org='contoso.microsoft.com'
    $cred=Get-Credential $admin@$org
    $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
    $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
    Import-PSSession $sessExchange
    Import-PSSession $sessLync
    ```

2.  <span data-ttu-id="04f0f-111">建立工作階段之後，請在資源樹系中建立新的信箱。</span><span class="sxs-lookup"><span data-stu-id="04f0f-111">After establishing a session, create a new mailbox in the Resource Forest.</span></span> <span data-ttu-id="04f0f-112">這可讓帳戶向 Surface Hub 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="04f0f-112">This will allow the account to authenticate into the Surface Hub.</span></span>

    <span data-ttu-id="04f0f-113">如果您正在變更現有的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="04f0f-113">If you're changing an existing resource mailbox:</span></span>

    ```PowerShell
    New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01"
    ```

3.  <span data-ttu-id="04f0f-114">設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。</span><span class="sxs-lookup"><span data-stu-id="04f0f-114">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

    <span data-ttu-id="04f0f-115">Surface Hub 只會與具有已將 **PasswordEnabled** 屬性設為 **False** 之 ActiveSync 原則的裝置帳戶相容。</span><span class="sxs-lookup"><span data-stu-id="04f0f-115">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="04f0f-116">如果未正確設定此屬性，將無法啟用 Surface Hub 上的 Exchange 服務 (電子郵件、行事曆及加入會議)。</span><span class="sxs-lookup"><span data-stu-id="04f0f-116">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

    <span data-ttu-id="04f0f-117">如果您尚未建立相容的原則，請使用下列 Cmdlet，此 Cmdlet 會建立名為 "Surface Hubs" 的原則。</span><span class="sxs-lookup"><span data-stu-id="04f0f-117">If you haven’t created a compatible policy yet, use the following cmdlet-—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="04f0f-118">一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="04f0f-118">Once it’s created, you can apply the same policy to other device accounts.</span></span>

    ```PowerShell
    $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
    ```

    <span data-ttu-id="04f0f-119">當您具備相容的原則之後，接著就需要將原則套用到裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="04f0f-119">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span> 

    ```PowerShell
    Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy -ActiveSyncEnabled $true
    Set-Mailbox $acctUpn -Type Room
    ```

4.  <span data-ttu-id="04f0f-120">您可以在裝置帳戶上設定各種不同的 Exchange 屬性，來改善使用者的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="04f0f-120">Various Exchange properties can be set on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="04f0f-121">您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)一節中看到需要設定哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="04f0f-121">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ```PowerShell
    Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="04f0f-122">如果您決定要讓密碼永久有效，也可以使用 PowerShell Cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="04f0f-122">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="04f0f-123">如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="04f0f-123">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span> <span data-ttu-id="04f0f-124">這應該在使用者樹系中設定。</span><span class="sxs-lookup"><span data-stu-id="04f0f-124">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -PasswordNeverExpires $true
    ```

6.  <span data-ttu-id="04f0f-125">啟用 Active Directory 中的帳戶，如此一來，該帳戶將會向 Surface Hub 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="04f0f-125">Enable the account in Active Directory so it will authenticate to the Surface Hub.</span></span> <span data-ttu-id="04f0f-126">這應該在使用者樹系中設定。</span><span class="sxs-lookup"><span data-stu-id="04f0f-126">This should be set in the User Forest.</span></span>

    ```PowerShell
    Set-AdUser $acctUpn -Enabled $true
    ```

6. <span data-ttu-id="04f0f-127">現在您需要將會議室信箱變更至已連結的信箱︰</span><span class="sxs-lookup"><span data-stu-id="04f0f-127">You now need to change the room mailbox to a linked mailbox:</span></span>

    ```PowerShell
    $cred=Get-Credential AuthForest\ADAdmin
    Set-mailbox -Alias LinkedRoomTest1 -LinkedMasterAccount AuthForest\LinkedRoomTest1 -LinkedDomainController AuthForest-4939.AuthForest.extest.contoso.com -Name LinkedRoomTest1 -LinkedCredential $cred -Identity LinkedRoomTest1
    ```

7.  <span data-ttu-id="04f0f-128">在商務用 Skype Server 集區上啟用您的 Surface Hub AD 帳戶，藉以使用商務用 Skype 來啟用裝置帳戶：</span><span class="sxs-lookup"><span data-stu-id="04f0f-128">Enable the device account with Skype for Business by enabling your Surface Hub AD account on a Skype for Business Server pool:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
     -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
     -Identity HUB01
    ```

    <span data-ttu-id="04f0f-129">您需要針對 Surface Hub 使用工作階段初始通訊協定 (SIP) 位址與網域控制站，以及您自己的商務用 Skype Server 集區識別碼和使用者身分識別。</span><span class="sxs-lookup"><span data-stu-id="04f0f-129">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Surface Hub, along with your own Skype for Business Server pool identifier and user identity.</span></span>


## <span data-ttu-id="04f0f-130">停用匿名電子郵件和 IM</span><span class="sxs-lookup"><span data-stu-id="04f0f-130">Disable anonymous email and IM</span></span>



<span data-ttu-id="04f0f-131">Surface Hub 使用裝置帳戶來提供電子郵件和共同作業服務（IM、影片、語音）。</span><span class="sxs-lookup"><span data-stu-id="04f0f-131">Surface Hub uses a device account to provide email and collaboration services (IM, video, voice).</span></span> <span data-ttu-id="04f0f-132">此裝置帳戶是在傳送電子郵件、IM 及撥打電話時，用來做為來源身分識別（「寄件者」方）。</span><span class="sxs-lookup"><span data-stu-id="04f0f-132">This device account is used as the originating identity (the “from” party) when sending email, IM, and placing calls.</span></span> <span data-ttu-id="04f0f-133">由於這個帳戶不是來自個人、辨識的使用者，因此被視為「匿名」，因為它源自 Surface Hub 的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="04f0f-133">As this account is not coming from an individual, identifiable user, it is deemed “anonymous” because it originated from the Surface Hub's device account.</span></span>  

<span data-ttu-id="04f0f-134">假設您已將每個使用者的用戶端原則指派給每一個會議室裝置，且其身分為**SurfaceHubPolicy**身分識別。</span><span class="sxs-lookup"><span data-stu-id="04f0f-134">Assume you have a per-user client policy assigned to each meeting room device with an identity of **SurfaceHubPolicy**.</span></span> <span data-ttu-id="04f0f-135">若要停用匿名電子郵件和訊息，您可以使用下列命令，將 clientPolicyEntry 新增至此用戶端原則。</span><span class="sxs-lookup"><span data-stu-id="04f0f-135">To disable anonymous email and messaging, you add a clientPolicyEntry to this client policy by using the following commands.</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

<span data-ttu-id="04f0f-136">若要確認已設定原則：</span><span class="sxs-lookup"><span data-stu-id="04f0f-136">To verify that the policy has been set:</span></span>

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

<span data-ttu-id="04f0f-137">輸出應為：</span><span class="sxs-lookup"><span data-stu-id="04f0f-137">The output should be:</span></span>

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
<span data-ttu-id="04f0f-138">若要變更原則專案：</span><span class="sxs-lookup"><span data-stu-id="04f0f-138">To change the policy entry:</span></span>

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
<span data-ttu-id="04f0f-139">若要移除原則專案：</span><span class="sxs-lookup"><span data-stu-id="04f0f-139">To remove the policy entry:</span></span>

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```
 





