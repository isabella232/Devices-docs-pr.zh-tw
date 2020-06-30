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
# 使用 Office 365 進行線上部署 (Surface Hub)


本主題提供當您進行單純的線上部署時，針對 Microsoft Surface Hub 新增裝置帳戶的指示。

如果您是進行單純的線上 (O365) 部署，則可[使用提供的 PowerShell 指令碼](appendix-a-powershell-scripts-for-surface-hub.md#create-os356-ps-scripts)來建立裝置帳戶。 

1. 在電腦上啟動遠端 PowerShell 工作階段，並連線到 Exchange。

   確定您已設定正確的權限來執行相關聯的 Cmdlet。

   ```PowerShell
   Set-ExecutionPolicy RemoteSigned
   $org='contoso.microsoft.com'
   $cred=Get-Credential admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```

2. 建立工作階段之後，您將建立新的信箱並啟用為 RoomMailboxAccount，或是變更現有會議室信箱的設定。 這可讓帳戶向 Surface Hub 進行驗證。

   如果您正在變更現有的資源信箱：

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   如果您正在建立新的資源信箱：

   ```PowerShell
   New-Mailbox -MicrosoftOnlineServicesID HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。

   Surface Hub 只會與具有已將 **PasswordEnabled** 屬性設為 False 之 ActiveSync 原則的裝置帳戶相容。 如果未正確設定此屬性，將無法啟用 Surface Hub 上的 Exchange 服務 (電子郵件、行事曆及加入會議)。

   如果您尚未建立相容的原則，請使用下列 Cmdlet，此 Cmdlet 會建立名為 "Surface Hubs" 的原則。 一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false -AllowNonProvisionableDevices $True
   ```

   當您具備相容的原則之後，您接著需要將原則套用到裝置帳戶。

   ```PowerShell
   Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.Id
   ```

4. 您必須在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。 您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md) 一節中看到需要設定哪些屬性。

   ```PowerShell
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. 連線到 Azure AD。
    
   您首先需要安裝 PowerShell 版本 2 的 Azure AD 模組。 在提升權限的 PowerShell 提示執行下列命令：
    
   ```PowerShell
   Install-Module -Name AzureAD
   ```
   您需要連線到 Azure AD，以套用一些帳戶設定。 您可以執行這個 Cmdlet 來連線。

   ```PowerShell
   Import-Module AzureAD
   Connect-AzureAD -Credential $cred
   ```

6. 如果您決定要讓密碼永久有效，也可以使用 PowerShell Cmdlet 來設定。 如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。

   ```PowerShell
   Set-AzureADUser -ObjectId "HUB01@contoso.com" -PasswordPolicies "DisablePasswordExpiration"
   ```

7. Surface Hub 需要商務用 Skype 功能的授權。 為了啟用商務用 Skype，您的環境必須符合[商務用 Skype Online 的先決條件](hybrid-deployment-surface-hub-device-accounts.md#skype-for-business-online)。
   
   接下來，您可以使用 `Get-AzureADSubscribedSku` 來擷取可供 O365 租用戶使用的 SKU 清單。

   列出 SKU 後，就必須將您想要的 SkuId 指派給 `$License.SkuId` 變數。

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

8. 使用商務用 Skype 啟用裝置帳戶。
   如果未安裝商務用 Skype PowerShell 模組，請[下載商務用 Skype Online Windows PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)。 

   - 一開始先從電腦建立遠端 PowerShell 工作階段。

     ```PowerShell
     Import-Module SkypeOnlineConnector  
     $cssess=New-CsOnlineSession -Credential $cred  
     Import-PSSession $cssess -AllowClobber
     ```

   - 接下來，如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet (例如 <em>alice@contoso.com</em>)，從現有的商務用 Skype 使用者取得值：

       ```PowerShell
       Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool
       ```
       或者藉由設定變數
        
       ```PowerShell
    $strRegistrarPool = Get-CsOnlineUser -Identity 'alice@contoso.com' | fl registrarpool | out-string
    $strRegistrarPool = $strRegistrarPool.Substring($strRegistrarPool.IndexOf(':') + 2)
       ```
        
   - 使用下列 Cmdlet 啟用 Surface Hub 帳戶︰
      
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool yourRegistrarPool -SipAddressType EmailAddress
       ```
        
       或者使用上述的 $strRegistarPool 變數
        
       ```PowerShell
       Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool $strRegistrarPool -SipAddressType EmailAddress
       ```

若要進行驗證，您應該能夠使用任何一個商務用 Skype 用戶端 (電腦、Android 等) 登入此帳戶。





