---
title: 建立 Surface Hub 2S 裝置帳戶
description: 此頁面說明建立 Surface Hub 2S 裝置帳戶的程式。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/18/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 3afd4115ff4bd22a84f9a5fb86ceb6805c347f8a
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385221"
---
# <a name="create-surface-hub-2s-device-account"></a>建立 Surface Hub 2S 裝置帳戶

建立 Surface Hub 裝置帳戶 (也稱為會議室信箱) 可讓 Surface Hub 2S 接收、核准或拒絕會議要求並加入會議。 設定 OOBE 的開箱即用體驗 (裝置) 帳戶。 如果需要，您可以稍後變更 (OOBE 設定) 。

您可以結合 Windows PowerShell，從 Microsoft 365 系統管理中心建立帳戶： 

- **透過系統管理中心建立帳戶**。 若要符合最低需求，您可以直接從 [Microsoft 365](https://admin.microsoft.com/AdminPortal)系統管理中心設定帳戶所需的一切。 某些功能 ，例如直接從白板應用程式共用白板，需要使用 PowerShell 來設定 ActiveSync;如果 [此頁面需要使用電子郵件應用程式](#enable-activesync-if-use-of-email-app-is-required) ，請參閱啟用 ActiveSync。

- **透過 PowerShell 建立帳戶**。 您可以使用 PowerShell 腳本來協助建立多個裝置帳戶，並快速設定特定功能，包括：
    - 每個 Surface Hub 裝置帳戶的日曆處理。
    - 自訂自動回復排程要求。
    - 如果其他人或其他程式已經修改預設的 ActiveSync 信箱策略，您可能必須建立並指派新的 ActiveSync 信箱策略。

> [!TIP]
> 您可以執行下方的帳戶驗證腳本來 [檢查帳戶](#account-verification-script) 設定。

> [!NOTE]  
> Surface Hub 裝置帳戶不支援協力廠商聯合身分識別提供者 (FI) ，而且必須是標準 Active Directory 或 Azure Active Directory 帳戶。

## <a name="create-account-via-admin-center"></a>透過系統管理中心建立帳戶

1. 在 Microsoft 365 系統管理中心****，前往資源並選擇會議室 **&設備，** 然後選取 **+ 新增資源**。

2. 提供裝置帳戶的名稱和電子郵件地址。 將其餘的設定維持在預設狀態不變。

   ![提供名稱和電子郵件地址](images/sh2-account2.png)

   ![將剩餘設定維持在預設狀態不變](images/sh2-account3.png)

3. 設定裝置帳戶的密碼。 若要設定密碼， **請選擇使用者，** 然後選取 **使用中使用者**。 現在，搜尋新建立的使用者以設定密碼。 請確定您 **未選取** 選項，讓使用者 **在首次登錄時變更其密碼。**

   ![設定裝置帳戶的密碼](images/sh2-account4.png)

4. 使用 Office 365 授權指派會議室。 建議您指派 Office 365 會議室授權****，以自動啟用 Microsoft Teams 和商務用 Skype 帳戶。

   ![指派 Office 365 授權](images/sh2-account5.png)


> [!NOTE]  
> 如果使用商務用 Skype，您必須透過 PowerShell -- 商務用 Skype 日曆：設定此帳戶的日曆 [自動](#set-calendar-auto-processing-skype-for-business-only) 處理完成設定。 

## <a name="create-account-via-powershell"></a>透過 PowerShell 建立帳戶

 使用 PowerShell 快速自動化 Surface Hub 上的工作，不一定需要 PowerShell 專業知識。 在此頁面上使用適當的腳本之前，確定您已完成設定先決條件。

### <a name="prerequisites-for-using-powershell-to-manage-surface-hub"></a>使用 PowerShell 管理 Surface Hub 的先決條件 

1. 以提升的帳戶許可權啟動 PowerShell (**以** 系統管理員) 並確保您的系統已設置為執行 PowerShell 腳本。 若要深入瞭解，請參閱關於 [執行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。 
2. [安裝 Azure PowerShell 模組](https://docs.microsoft.com/powershell/azure/install-az-ps)。


### <a name="connect-to-exchange-online-powershell"></a>連線到 Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <a name="create-mailbox"></a>建立信箱

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <a name="set-calendar-auto-processing-skype-for-business-only"></a>設定只 (商務用 Skype 的) 

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <a name="enable-activesync-if-use-of-email-app-is-required"></a>如果需要使用電子郵件應用程式，請啟用 ActiveSync

 預設 ActiveSync Policy 會維持不變。 否則，請建立新策略並指派。

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```

### <a name="connect-to-azure-ad"></a>連線到 Azure AD

```powershell
Connect-AzureAD
```

### <a name="assign-a-license"></a>指派授權

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <a name="check-for-available-licenses"></a>檢查可用的授權

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```

## <a name="account-verification-script"></a>帳戶驗證指令碼

建立裝置帳戶之後，您可以執行下列驗證腳本。 此腳本會驗證先前建立之裝置帳戶，並產生摘要報表。 例如：

``` syntax
15 tests executed
0 failures
2 warnings
15 passed
```

系統將不會顯示特定設定的詳細資料。

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

## <a name="learn-more"></a>深入了解

- [使用 PowerShell 建立 Surface Hub 2S 內部部署帳戶](surface-hub-2s-onprem-powershell.md)