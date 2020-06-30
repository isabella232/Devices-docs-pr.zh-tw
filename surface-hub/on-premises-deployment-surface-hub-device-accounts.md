---
title: 內部部署單一樹系 (Surface Hub)
description: 本主題說明當您擁有單一樹系的內部部署時，如何為您的 Microsoft Surface Hub 新增裝置帳戶。
ms.assetid: 80E12195-A65B-42D1-8B84-ECC3FCBAAFC6
ms.reviewer: ''
manager: laurawi
keywords: 單一樹系部署, 內部部署, 裝置帳戶, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.date: 08/28/2018
ms.localizationpriority: medium
ms.openlocfilehash: 37b157268769ddcdeaef67b7e19cc7260cd392b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831810"
---
# 在單一樹系環境中的 Surface Hub 內部部署


本主題說明當您擁有單一樹系的內部部署時，如何為您的 Microsoft Surface Hub 新增裝置帳戶。

如果您擁有使用 Microsoft Exchange 2013 或更新版本以及商務用 Skype 2013 或更新版本的單一樹系內部部署，則可[使用提供的 PowerShell 指令碼](appendix-a-powershell-scripts-for-surface-hub.md#create-on-premises-ps-scripts)來建立裝置帳戶。 如果您使用多樹系部署，請參閱[在多樹系環境中的 Surface Hub 內部部署](on-premises-deployment-surface-hub-multi-forest.md)。

1. 從電腦上啟動遠端 PowerShell 工作階段，並連線到 Exchange。

   確定您已設定正確的權限來執行相關聯的 Cmdlet。

   請注意此處的 `$strExchangeServer` 是 Exchange Server 的完整網域名稱 (FQDN)，而 `$strLyncFQDN` 是商務用 Skype Server 的 FQDN。

   ```PowerShell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.microsoft.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

2. 建立工作階段之後，您將建立新的信箱並啟用為 RoomMailboxAccount，或是變更現有會議室信箱的設定。 這可讓帳戶向 Surface Hub 進行驗證。

   如果您正在變更現有的資源信箱：

   ```PowerShell
   Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   如果您正在建立新的資源信箱：

   ```PowerShell
   New-Mailbox -UserPrincipalName HUB01@contoso.com -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
> [!IMPORTANT] 
> 需要啟用 ActiveSync 虛擬目錄基本驗證，因為 Surface Hub 無法使用其他驗證方法進行驗證。

3. 設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。

   Surface Hub 只會與具有已將 **PasswordEnabled** 屬性設為 False 之 ActiveSync 原則的裝置帳戶相容。 如果未正確設定此屬性，將無法啟用 Surface Hub 上的 Exchange 服務 (電子郵件、行事曆及加入會議)。

   如果您尚未建立相容的原則，請使用下列 Cmdlet，此 Cmdlet 會建立名為 "Surface Hubs" 的原則。 一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。

   ```PowerShell
   $easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
   ```

   當您具備相容的原則之後，您接著需要將原則套用到裝置帳戶。 不過，原則只能套用到使用者帳戶，不能套用到資源信箱。 您需要將信箱轉換成使用者類型、套用原則，然後將它轉換回信箱 - 您可能也需要重新啟用它並再次設定密碼。

   ```PowerShell
   $acctUpn = Get-Mailbox -Identity "<mailbox identity>"
   $credNewAccount.Password = ConvertTo-SecureString -String <room mailbox password> -AsPlainText -Force
   Set-Mailbox $acctUpn -Type Regular
   Set-CASMailbox $acctUpn -ActiveSyncMailboxPolicy $easPolicy
   Set-Mailbox $acctUpn -Type Room
   Set-Mailbox $acctUpn -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```

4. 您可以在裝置帳戶上設定各種不同的 Exchange 屬性，來改善使用者的會議體驗。 您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)一節中看到需要設定哪些屬性。

   ```PowerShell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
   ```

5. 如果您決定要讓密碼永久有效，也可以使用 PowerShell Cmdlet 來設定。 如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。

   ```PowerShell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

6. 啟用 Active Directory 中的帳戶，如此一來，該帳戶將會向 Surface Hub 進行驗證。

   ```PowerShell
   Set-AdUser $acctUpn -Enabled $true
   ```

7. 在商務用 Skype Server 集區上啟用您的 Surface Hub AD 帳戶，藉以使用商務用 Skype 來啟用裝置帳戶：

   ```PowerShell
   Enable-CsMeetingRoom -SipAddress "sip:HUB01@contoso.com"
    -DomainController DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com
    -Identity HUB01
   ```

   您需要針對 Surface Hub 使用工作階段初始通訊協定 (SIP) 位址與網域控制站，以及您自己的商務用 Skype Server 集區識別碼和使用者身分識別。

8. 選用：您也可以藉由為帳戶啟用企業語音，讓 Surface Hub 能夠撥打和接聽公用交換電話網路 (PSTN) 通話。 企業語音並非 Surface Hub 的需求，但若您想要針對 Surface Hub 用戶端使用 PSTN 撥號功能，以下是啟用它的方式：

   ```PowerShell
   Set-CsMeetingRoom  -Identity HUB01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"  -EnterpriseVoiceEnabled $true
   ```

   同樣地，您必須以您自己的資訊取代所提供的網網域控制站和電話號碼範例。 讓參數值 `$true` 保持不變。
    

 ## 停用匿名電子郵件和 IM




Surface Hub 使用裝置帳戶來提供電子郵件和共同作業服務（IM、影片、語音）。 此裝置帳戶是在傳送電子郵件、IM 及撥打電話時，用來做為來源身分識別（「寄件者」方）。 由於這個帳戶不是來自個人、辨識的使用者，因此被視為「匿名」，因為它源自 Surface Hub 的裝置帳戶。  

假設您已將每個使用者的用戶端原則指派給每一個會議室裝置，且其身分為**SurfaceHubPolicy**身分識別。 若要停用匿名電子郵件和訊息，您可以使用下列命令，將 clientPolicyEntry 新增至此用戶端原則。

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $false
$clientPolicy = Get-CsClientPolicy -Identity SurfaceHubPolicy
$clientPolicy.PolicyEntry.Add($policyEntry)
Set-CsClientPolicy -Instance $clientPolicy
```

若要確認已設定原則：

```
Select-Object -InputObject $clientPolicy -Property PolicyEntry
```

輸出應為：

```
PolicyEntry
-----------
{Name=AllowResourceAccountSendMessage;Value=False}
```
    
    
若要變更原則專案：

```
$policyEntry =  New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Replace = $policyEntry}
``` 
    
若要移除原則專案：

```
$policyEntry = New-CsClientPolicyEntry -Name AllowResourceAccountSendMessage -value $true
$clientPolicy | Set-CsClientPolicy -PolicyEntry @{Remove = $policyEntry}
```

 





