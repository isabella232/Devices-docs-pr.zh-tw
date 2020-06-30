---
title: 使用 Office 365 進行線上部署 (Surface Hub)
description: 本主題提供當您進行單純的線上部署時，針對 Microsoft Surface Hub 新增裝置帳戶的指示。
ms.assetid: D325CA68-A03F-43DF-8520-EACF7C3EDEC1
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub 的裝置帳戶, 線上部署
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/21/2018
ms.localizationpriority: medium
ms.openlocfilehash: b38b8eb0ef13c2e945d63821e6e246ac7a59b2d7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831793"
---
# <span data-ttu-id="49ed9-104">使用 Office 365 進行線上部署 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="49ed9-104">Online deployment with Office 365 (Surface Hub)</span></span>


<span data-ttu-id="49ed9-105">本主題提供當您進行單純的線上部署時，針對 Microsoft Surface Hub 新增裝置帳戶的指示。</span><span class="sxs-lookup"><span data-stu-id="49ed9-105">This topic has instructions for adding a device account for your Microsoft Surface Hub when you have a pure, online deployment.</span></span>

<span data-ttu-id="49ed9-106">如果您是進行單純的線上 (O365) 部署，則可[使用提供的 PowerShell 指令碼](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts)來建立裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="49ed9-106">If you have a pure, online (O365) deployment, then you can [use the provided PowerShell scripts](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts) to create device accounts.</span></span> 

1. <span data-ttu-id="49ed9-107">在電腦上啟動遠端 PowerShell 工作階段，並連線到 Exchange。</span><span class="sxs-lookup"><span data-stu-id="49ed9-107">Start a remote PowerShell session on a PC and connect to Exchange.</span></span>

   <span data-ttu-id="49ed9-108">確定您已設定正確的權限來執行相關聯的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="49ed9-108">Be sure you have the right permissions set to run the associated cmdlets.</span></span>

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. <span data-ttu-id="49ed9-109">建立工作階段之後，您將建立新的信箱並啟用為 RoomMailboxAccount，或是變更現有會議室信箱的設定。</span><span class="sxs-lookup"><span data-stu-id="49ed9-109">After establishing a session, you’ll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="49ed9-110">這可讓帳戶向 Surface Hub 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="49ed9-110">This will allow the account to authenticate into the Surface Hub.</span></span>

   <span data-ttu-id="49ed9-111">如果您正在變更現有的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="49ed9-111">If you're changing an existing resource mailbox:</span></span>

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="49ed9-112">如果您正在建立新的資源信箱：</span><span class="sxs-lookup"><span data-stu-id="49ed9-112">If you’re creating a new resource mailbox:</span></span>

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="49ed9-113">設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。</span><span class="sxs-lookup"><span data-stu-id="49ed9-113">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="49ed9-114">Surface Hub 只會與具有已將 **PasswordEnabled** 屬性設為 False 之 ActiveSync 原則的裝置帳戶相容。</span><span class="sxs-lookup"><span data-stu-id="49ed9-114">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to False.</span></span> <span data-ttu-id="49ed9-115">如果未正確設定此屬性，將無法啟用 Surface Hub 上的 Exchange 服務 (電子郵件、行事曆及加入會議)。</span><span class="sxs-lookup"><span data-stu-id="49ed9-115">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>

   <span data-ttu-id="49ed9-116">如果您尚未建立相容的原則，請使用下列 Cmdlet，此 Cmdlet 會建立名為 "Surface Hubs" 的原則。</span><span class="sxs-lookup"><span data-stu-id="49ed9-116">If you haven’t created a compatible policy yet, use the following cmdlet—this one creates a policy called "Surface Hubs".</span></span> <span data-ttu-id="49ed9-117">一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="49ed9-117">Once it’s created, you can apply the same policy to other device accounts.</span></span>

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   <span data-ttu-id="49ed9-118">當您具備相容的原則之後，您接著需要將原則套用到裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="49ed9-118">Once you have a compatible policy, then you will need to apply the policy to the device account.</span></span>

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. <span data-ttu-id="49ed9-119">您必須在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="49ed9-119">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="49ed9-120">您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md) 一節中看到需要設定哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="49ed9-120">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. <span data-ttu-id="49ed9-121">連線到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="49ed9-121">Connect to Azure AD.</span></span>
    
   <span data-ttu-id="49ed9-122">您首先需要安裝 PowerShell 版本 2 的 Azure AD 模組。</span><span class="sxs-lookup"><span data-stu-id="49ed9-122">You first need to install Azure AD module for PowerShell version 2.</span></span> <span data-ttu-id="49ed9-123">在提升權限的 PowerShell 提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="49ed9-123">In an elevated powershell prompt run the following command :</span></span>
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   <span data-ttu-id="49ed9-124">您需要連線到 Azure AD，以套用一些帳戶設定。</span><span class="sxs-lookup"><span data-stu-id="49ed9-124">You need to connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="49ed9-125">您可以執行這個 Cmdlet 來連線。</span><span class="sxs-lookup"><span data-stu-id="49ed9-125">You can run this cmdlet to connect.</span></span>

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. <span data-ttu-id="49ed9-126">如果您決定要讓密碼永久有效，也可以使用 PowerShell Cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="49ed9-126">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="49ed9-127">如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="49ed9-127">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. <span data-ttu-id="49ed9-128">Surface Hub 需要商務用 Skype 功能的授權。</span><span class="sxs-lookup"><span data-stu-id="49ed9-128">Surface Hub requires a license for Skype for Business functionality.</span></span> <span data-ttu-id="49ed9-129">為了啟用商務用 Skype，您的環境必須符合[商務用 Skype Online 的先決條件](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="49ed9-129">In order to enable Skype for Business, your environment will need to meet the [prerequisites for Skype for Business online](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online).</span></span>
   
   <span data-ttu-id="49ed9-130">接下來，您可以使用 `Get-AzureADSubscribedSku` 來擷取可供 O365 租用戶使用的 SKU 清單。</span><span class="sxs-lookup"><span data-stu-id="49ed9-130">Next, you can use `Get-AzureADSubscribedSku` to retrieve a list of available SKUs for your O365 tenant.</span></span>

   <span data-ttu-id="49ed9-131">列出 SKU 後，就必須將您想要的 SkuId 指派給 `$License.SkuId` 變數。</span><span class="sxs-lookup"><span data-stu-id="49ed9-131">Once you list out the SKUs, you'll need to assign the SkuId you want to the `$License.SkuId` variable.</span></span>

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

8. <span data-ttu-id="49ed9-132">使用商務用 Skype 啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="49ed9-132">Enable the device account with Skype for Business.</span></span>
   <span data-ttu-id="49ed9-133">如果未安裝商務用 Skype PowerShell 模組，請[下載商務用 Skype Online Windows PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)。</span><span class="sxs-lookup"><span data-stu-id="49ed9-133">If the Skype for Business PowerShell module is not installed, [download the Skype for Business Online Windows PowerShell Module](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> 

   - <span data-ttu-id="49ed9-134">一開始先從電腦建立遠端 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="49ed9-134">Start by creating a remote PowerShell session from a PC.</span></span>

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - <span data-ttu-id="49ed9-135">接下來，如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet (例如 <em>alice@contoso.com</em>)，從現有的商務用 Skype 使用者取得值：</span><span class="sxs-lookup"><span data-stu-id="49ed9-135">Next, if you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet (for example, <em>alice@contoso.com</em>):</span></span>

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       <span data-ttu-id="49ed9-136">或者藉由設定變數</span><span class="sxs-lookup"><span data-stu-id="49ed9-136">OR by setting a variable</span></span>
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - <span data-ttu-id="49ed9-137">使用下列 Cmdlet 啟用 Surface Hub 帳戶︰</span><span class="sxs-lookup"><span data-stu-id="49ed9-137">Enable the Surface Hub account with the following cmdlet:</span></span>
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       <span data-ttu-id="49ed9-138">或者使用上述的 $strRegistarPool 變數</span><span class="sxs-lookup"><span data-stu-id="49ed9-138">OR using the $strRegistarPool variable from above</span></span>
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

<span data-ttu-id="49ed9-139">若要進行驗證，您應該能夠使用任何一個商務用 Skype 用戶端 (電腦、Android 等) 登入此帳戶。</span><span class="sxs-lookup"><span data-stu-id="49ed9-139">For validation, you should be able to use any Skype for Business client (PC, Android, etc) to sign in to this account.</span></span>





