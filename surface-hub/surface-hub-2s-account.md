---
title: 建立 Surface Hub 2S 裝置帳戶
description: 此頁面說明建立 Surface Hub 2 裝置帳戶的程式。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/01/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 76ac960be2ab30a30b4e29618f350a13a284f52a
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312019"
---
# <span data-ttu-id="6c665-104">建立 Surface Hub 2S 裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="6c665-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="6c665-105">建立 Surface Hub 裝置帳戶 (也稱為會議室信箱) 可讓 Surface Hub 2 來接收、核准或拒絕會議邀請並加入會議。</span><span class="sxs-lookup"><span data-stu-id="6c665-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings.</span></span> <span data-ttu-id="6c665-106">在全新的體驗中設定裝置帳戶 (OOBE) 設定。</span><span class="sxs-lookup"><span data-stu-id="6c665-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="6c665-107">如有需要，您可以在稍後 (進行變更，而不需要在 OOBE 設定) 。</span><span class="sxs-lookup"><span data-stu-id="6c665-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="6c665-108">您可以將 Microsoft 365 系統管理中心的帳戶與 Windows PowerShell 結合使用：</span><span class="sxs-lookup"><span data-stu-id="6c665-108">You can create the account from  Microsoft 365 Admin center in combination with Windows PowerShell:</span></span> 

- <span data-ttu-id="6c665-109">透過系統**管理中心建立帳戶**。</span><span class="sxs-lookup"><span data-stu-id="6c665-109">**Create account via Admin center**.</span></span> <span data-ttu-id="6c665-110">若要符合最低需求，您可以直接從 [Microsoft 365 系統管理中心](https://admin.microsoft.com/AdminPortal)設定帳戶所需的所有專案。</span><span class="sxs-lookup"><span data-stu-id="6c665-110">To meet minimum requirements, you can configure everything you need for the account directly from the [Microsoft 365 admin center](https://admin.microsoft.com/AdminPortal).</span></span> <span data-ttu-id="6c665-111">從白板 app 直接共用白板等一些功能，都需要使用 PowerShell 來設定 ActiveSync;如果此頁面 [需要使用電子郵件應用程式，請參閱啟用 ActiveSync](#enable-activesync-if-use-of-email-app-is-required) 。</span><span class="sxs-lookup"><span data-stu-id="6c665-111">Some features like sharing whiteboards directly from the whiteboard app require using PowerShell to configure ActiveSync; see [Enable ActiveSync if use of email app is required](#enable-activesync-if-use-of-email-app-is-required) on this page.</span></span>

- <span data-ttu-id="6c665-112">透過**PowerShell 建立帳戶**。</span><span class="sxs-lookup"><span data-stu-id="6c665-112">**Create account via PowerShell**.</span></span> <span data-ttu-id="6c665-113">您可以使用 PowerShell 腳本來協助您建立多個裝置帳戶，並快速設定特定功能，包括：</span><span class="sxs-lookup"><span data-stu-id="6c665-113">You can use PowerShell scripts to facilitate creation of multiple device accounts and quickly configure specific features including:</span></span>
    - <span data-ttu-id="6c665-114">每個 Surface Hub 裝置帳戶的行事曆處理。</span><span class="sxs-lookup"><span data-stu-id="6c665-114">Calendar processing for every Surface Hub device account.</span></span>
    - <span data-ttu-id="6c665-115">針對排程要求自訂自動回復。</span><span class="sxs-lookup"><span data-stu-id="6c665-115">Custom auto replies to scheduling requests.</span></span>
    - <span data-ttu-id="6c665-116">如果預設 ActiveSync 信箱原則已由其他人或其他程式修改，您可能需要建立並指派新的 ActiveSync 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="6c665-116">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!TIP]
> <span data-ttu-id="6c665-117">您可以執行下列 [帳戶驗證腳本](#account-verification-script) 來檢查帳戶設定。</span><span class="sxs-lookup"><span data-stu-id="6c665-117">You can check account setup by running the [Account verification script](#account-verification-script) below.</span></span>

> [!NOTE]  
> <span data-ttu-id="6c665-118">Surface Hub 裝置帳戶不支援協力廠商同盟身分識別提供者 (FIPs) ，而且必須是標準的 Active Directory 或 Azure Active Directory 帳戶。</span><span class="sxs-lookup"><span data-stu-id="6c665-118">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="6c665-119">透過系統管理中心建立帳戶</span><span class="sxs-lookup"><span data-stu-id="6c665-119">Create account via admin center</span></span>

1. <span data-ttu-id="6c665-120">在 Microsoft 365 系統管理中心中，移至 [ **資源** ]，然後選擇 [ **會議室] & 裝置** ]，然後選取 [ **+ 新增資源**]。</span><span class="sxs-lookup"><span data-stu-id="6c665-120">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Add resource**.</span></span>

2. <span data-ttu-id="6c665-121">提供裝置帳戶的名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="6c665-121">Provide a name and email address for the device account.</span></span> <span data-ttu-id="6c665-122">保留預設狀態中不變的剩餘設定。</span><span class="sxs-lookup"><span data-stu-id="6c665-122">Leave remaining settings unchanged in the default state.</span></span>

   ![提供名稱和電子郵件地址](images/sh2-account2.png)

   ![保留預設狀態中不變的剩餘設定](images/sh2-account3.png)

3. <span data-ttu-id="6c665-125">設定裝置帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="6c665-125">Set the password for the device account.</span></span> <span data-ttu-id="6c665-126">若要設定密碼，請選擇 [ **使用者** ]，然後選取 [作用中的 **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="6c665-126">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="6c665-127">現在，搜尋新建立的使用者來設定密碼。</span><span class="sxs-lookup"><span data-stu-id="6c665-127">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="6c665-128">確定您**沒有**選取 [**讓此使用者在第一次登入時變更密碼**] 選項。</span><span class="sxs-lookup"><span data-stu-id="6c665-128">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![設定裝置帳戶的密碼](images/sh2-account4.png)

4. <span data-ttu-id="6c665-130">使用 Office 365 授權指派會議室。</span><span class="sxs-lookup"><span data-stu-id="6c665-130">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="6c665-131">建議您指派 **Office 365 會議室** 授權，這會自動為 Microsoft 團隊及商務用 Skype 啟用帳戶。</span><span class="sxs-lookup"><span data-stu-id="6c665-131">It’s recommended to assign the Office 365 **Meeting Room** license, which automatically enables the account for Microsoft Teams and Skype for Business.</span></span>

   ![指派 Office 365 授權](images/sh2-account5.png)


> [!NOTE]  
> <span data-ttu-id="6c665-133">如果您使用的是商務用 Skype，您將需要透過 PowerShell 完成設定--商務用 Skype 行事曆：為此帳戶設定行事 [曆自動處理](#set-calendar-auto-processing-skype-for-business-only) 。</span><span class="sxs-lookup"><span data-stu-id="6c665-133">If using Skype for Business, you will need to finalize setup via PowerShell -- Skype for Business Calendar: Set [Calendar Autoprocessing](#set-calendar-auto-processing-skype-for-business-only) for this account.</span></span> 

## <span data-ttu-id="6c665-134">透過 PowerShell 建立帳戶</span><span class="sxs-lookup"><span data-stu-id="6c665-134">Create account via PowerShell</span></span>

 <span data-ttu-id="6c665-135">使用 PowerShell 在 Surface Hub 上快速自動作業，不一定需要 PowerShell 專業技術。</span><span class="sxs-lookup"><span data-stu-id="6c665-135">Using PowerShell to rapidly automate tasks on Surface Hub does not necessarily require PowerShell expertise.</span></span> <span data-ttu-id="6c665-136">在此頁面上使用適當的腳本之前，請確定您已完成設定先決條件。</span><span class="sxs-lookup"><span data-stu-id="6c665-136">Ensure you have completed the setup prerequisites before using the appropriate scripts on this page.</span></span>

### <span data-ttu-id="6c665-137">使用 PowerShell 來管理 Surface Hub 的先決條件</span><span class="sxs-lookup"><span data-stu-id="6c665-137">Prerequisites for using PowerShell to manage Surface Hub</span></span> 

1. <span data-ttu-id="6c665-138">使用提升的帳戶許可權啟動 PowerShell， (**以系統管理員身分執行**) ，並確保您的系統已設定為執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="6c665-138">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="6c665-139">若要深入瞭解，請參閱 [關於執行原則](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。</span><span class="sxs-lookup"><span data-stu-id="6c665-139">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="6c665-140">[安裝 Azure PowerShell 模組](https://docs.microsoft.com/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="6c665-140">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>


### <span data-ttu-id="6c665-141">連線至 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="6c665-141">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="6c665-142">建立信箱</span><span class="sxs-lookup"><span data-stu-id="6c665-142">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="6c665-143">僅限商務用 Skype (設定行事曆自動處理) </span><span class="sxs-lookup"><span data-stu-id="6c665-143">Set Calendar auto-processing (Skype for Business only)</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="6c665-144">如果需要使用電子郵件應用程式，請啟用 ActiveSync</span><span class="sxs-lookup"><span data-stu-id="6c665-144">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="6c665-145">如果不變，預設 ActiveSync 原則就會運作。</span><span class="sxs-lookup"><span data-stu-id="6c665-145">The default ActiveSync Policy will work if unchanged.</span></span> <span data-ttu-id="6c665-146">否則，請 createStupid 新原則並指派。</span><span class="sxs-lookup"><span data-stu-id="6c665-146">Otherwise createStupid a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <span data-ttu-id="6c665-147">連線到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="6c665-147">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="6c665-148">指派授權</span><span class="sxs-lookup"><span data-stu-id="6c665-148">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="6c665-149">檢查可用的授權</span><span class="sxs-lookup"><span data-stu-id="6c665-149">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <span data-ttu-id="6c665-150">帳戶驗證指令碼</span><span class="sxs-lookup"><span data-stu-id="6c665-150">Account verification script</span></span>

<span data-ttu-id="6c665-151">建立裝置帳戶之後，您可以執行下列驗證腳本。</span><span class="sxs-lookup"><span data-stu-id="6c665-151">After creating the device account, you can run the following verification script.</span></span> <span data-ttu-id="6c665-152">此腳本會驗證先前建立的裝置帳戶並產生摘要報告。</span><span class="sxs-lookup"><span data-stu-id="6c665-152">This script validates a previously-created device account and produces a summary report.</span></span> <span data-ttu-id="6c665-153">例如：</span><span class="sxs-lookup"><span data-stu-id="6c665-153">For example:</span></span>

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

<span data-ttu-id="6c665-154">系統將不會顯示特定設定的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6c665-154">Details of specific settings will not be shown.</span></span>

```PowerShell
# SHAccountValidate.ps1

$Error.Clear()
$ErrorActionPreference = "Stop"


# Cleans up set state such as remote powershell sessions
function Cleanup()
{
    if ($sessEx)
    {
        Remove-PSSession $sessEx
    }
    if ($sessSfb)
    {
        Remove-PSSession $sessSfb
    }
}

function PrintError($strMsg)
{
    Write-Host $strMsg -foregroundcolor "red"
}

function PrintSuccess($strMsg)
{
    Write-Host $strMsg -foregroundcolor "green"
}

function PrintAction($strMsg)
{
    Write-Host $strMsg -ForegroundColor Cyan
}


# Cleans up and prints an error message
function CleanupAndFail($strMsg)
{
    if ($strMsg)
    {
        PrintError($strMsg);
    }
    Cleanup
    exit 1
}

# Exits if there is an error set and prints the given message
function ExitIfError($strMsg)
{
    if ($Error)
    {
        CleanupAndFail($strMsg);
    }
}

$strUpn = Read-Host "What is the email address of the account you wish to validate?"
if (!$strUpn.Contains('@'))
{
    CleanupAndFail "$strUpn is not a valid email address"
}
$strExServer = Read-Host "What is your exchange server? (leave blank for online tenants)"
if ($strExServer.Equals(""))
{
    $fExIsOnline = $true
}
else
{
    $fExIsOnline = $false
}
$credEx = Get-Credential -Message "Please provide exchange user credentials"

$strRegistrarPool = Read-Host ("What is the Skype for Business registrar pool for $strUpn" + "? (leave blank for online tenants)")
$fSfbIsOnline = $strRegistrarPool.Equals("")

$fHasOnPrem = $true
if ($fSfbIsOnline -and $fExIsOnline)
{
    do
    {
        $strHasOnPrem = (Read-Host "Do you have an on-premises Active Directory (Y/N) (No if your domain services are hosted entirely online)").ToUpper()
    } while ($strHasOnPrem -ne "Y" -and $strHasOnPrem -ne "N")
    $fHasOnPrem = $strHasOnPrem.Equals("Y")
}

$fHasOnline = $false
if ($fSfbIsOnline -or $fExIsOnline)
{
    $fHasOnline = $true
}

if ($fSfbIsOnline)
{
    try {
        Import-Module SkypeOnlineConnector
    }
    catch
    {
        CleanupAndFail "To verify Skype for Business in online tenants you need the Lync Online Connector module from https://www.microsoft.com/download/details.aspx?id=39366"
    }
}
else
{
    $credSfb = (Get-Credential -Message "Please enter Skype for Business admin credentials")
}

if ($fHasOnline)
{
    $credSfb = $credEx
    try {
        Import-Module MSOnline
    }
    catch
    {
        CleanupAndFail "To verify accounts in online tenants you need the Azure Active Directory module for PowerShell from https://go.microsoft.com/fwlink/p/?linkid=236297"
    }
}

PrintAction "Connecting to Exchange Powershell Session..."
[System.Management.Automation.Runspaces.AuthenticationMechanism] $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Kerberos
if ($fExIsOnline)
{
    $authType = [System.Management.Automation.Runspaces.AuthenticationMechanism]::Basic
}
try
{
    $sessEx = $null
    if ($fExIsOnline)
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -WarningAction SilentlyContinue
    }
    else
    {
        $sessEx = New-PSSession -ConfigurationName microsoft.exchange -Credential $credEx -AllowRedirection -Authentication $authType -ConnectionUri https://$strExServer/powershell -WarningAction SilentlyContinue
    }
}
catch
{
}

if (!$sessEx)
{
    CleanupAndFail "Connecting to Exchange Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Exchange Powershell Session"

PrintAction "Connecting to Skype for Business Powershell Session..."

if ($fSfbIsOnline)
{
    $sessSfb = New-CsOnlineSession -Credential $credSfb
}
else
{
    $sessSfb = New-PSSession -Credential $credSfb -ConnectionURI "https://$strRegistrarPool/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
}

if (!$sessSfb)
{
    CleanupAndFail "Connecting to Skype for Business Powershell failed, please validate your server is accessible and credentials are correct"
}

PrintSuccess "Connected to Skype for Business Powershell"

if ($fHasOnline)
{
    $credMsol = $null
    if ($fExIsOnline)
    {
        $credMsol = $credEx
    }
    elseif ($fSfbIsOnline)
    {
        $credMsol = $credSfb
    }
    else
    {
        CleanupAndFail "Internal error - could not determine MS Online credentials"
    }
    try
    {
        PrintAction "Connecting to Azure Active Directory Services..."
        Connect-MsolService -Credential $credMsol
        PrintSuccess "Connected to Azure Active Directory Services"
    }
    catch
    {
        # This really shouldn't happen unless there is a network error
        CleanupAndFail "Failed to connect to MSOnline"
    }
}


PrintAction "Importing remote sessions into the local session..."
try
{
    $importEx = Import-PSSession $sessEx -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
    $importSfb = Import-PSSession $sessSfb -AllowClobber -WarningAction SilentlyContinue -DisableNameChecking
}
catch
{
}
if (!$importEx -or !$importSfb)
{
    CleanupAndFail "Import failed"
}
PrintSuccess "Import successful"


$mailbox = $null
try
{
    $mailbox = Get-Mailbox -Identity $strUpn
}
catch
{
}

if (!$mailbox)
{
    CleanupAndFail "Account exists check failed. Unable to find the mailbox for $strUpn - please make sure the Exchange account exists on $strExServer"
}

$exchange = $null
if (!$fExIsOnline)
{
    $exchange = Get-ExchangeServer
    if (!$exchange -or !$exchange.IsE14OrLater)
    {
        CleanupAndFail "A compatible exchange server version was not found. Please use at least exchange 2010."
    }
}


$strAlias = $mailbox.UserPrincipalName
$strDisplayName = $mailbox.DisplayName

$strLinkedAccount = $strLinkedDomain = $strLinkedUser = $strLinkedServer = $null
$credLinkedDomain = $Null
if (!$fExIsOnline -and ![System.String]::IsNullOrEmpty($mailbox.LinkedMasterAccount) -and !$mailbox.LinkedMasterAccount.EndsWith("\SELF"))
{
    $strLinkedAccount = $mailbox.LinkedMasterAccount
    $strLinkedDomain = $strLinkedAccount.substring(0,$strLinkedAccount.IndexOf('\'))
    $strLinkedUser = $strLinkedAccount.substring($strLinkedAccount.IndexOf('\') + 1)
    $strLinkedServer = Read-Host "What is the domain controller for the $strLinkedDomain"
    $credLinkedDomain = (Get-Credential -Message "Please provide credentials for $strLinkedDomain")
}







Write-Host
Write-Host
Write-Host
PrintAction "Performing verification checks on $strDisplayName..."
$Global:iTotalFailures = 0
$global:iTotalWarnings = 0
$Global:iTotalPasses = 0

function Validate()
{
    Param(
        [string]$Test,
        [bool]  $Condition,
        [string]$FailureMsg,
        [switch]$WarningOnly
    )

    Write-Host -NoNewline -ForegroundColor White $Test.PadRight(100,'.')
    if ($Condition)
    {
        Write-Host -ForegroundColor Green "Passed"
        $global:iTotalPasses++
    }
    else
    {
        if ($WarningOnly)
        {
            Write-Host -ForegroundColor Yellow ("Warning: "+$FailureMsg)
            $global:iTotalWarnings++
        }
        else
        {
            Write-Host -ForegroundColor Red ("Failed: "+$FailureMsg)
            $global:iTotalFailures++
        }
    }
}
```

## <span data-ttu-id="6c665-155">深入了解</span><span class="sxs-lookup"><span data-stu-id="6c665-155">Learn more</span></span>

- [<span data-ttu-id="6c665-156">使用 PowerShell 建立 Surface Hub 2S 內部部署帳戶</span><span class="sxs-lookup"><span data-stu-id="6c665-156">Create Surface Hub 2S on-premises accounts with PowerShell</span></span>](surface-hub-2s-onprem-powershell.md)