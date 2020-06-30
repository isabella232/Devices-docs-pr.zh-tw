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
# 混合式部署 (Surface Hub)

混合式部署需要特殊處理，才能設定適用於 Microsoft Surface Hub 的裝置帳戶。 如果您使用混合式部署 (您的組織具有混合的服務，其中有些是內部部署裝載的服務，有一些則是線上裝載的服務)，則您的組態將取決於裝載每個服務的位置。 本主題探討 [內部部署託管 Exchange](#exchange-on-premises)、[線上託管 Exchange](#exchange-online)、商務用 Skype 內部部署、商務用 Skype Online，以及商務用 Skype 混合式部署。 由於這種類型的部署中有許多不同的變化，因此無法提供所有變化的詳細指示。 下列程序將適用於多個組態。 如果此程序不適合您的設定，我們建議您使用 PowerShell (請參閱[附錄：PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)) 來達到此處所述的相同結果，並取得其他部署選項的說明。 您接著應該使用提供的 PowerShell 指令碼來確認 Surface Hub 設定。 (請參閱[帳戶驗證指令碼](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts))。

> [!NOTE]
> 在 Exchange 混合式環境中，請依照[exchange 內部部署](#exchange-on-premises)的步驟進行。 若要將 Exchange 物件移至 Office 365，請使用[MoveRequest](https://docs.microsoft.com/powershell/module/exchange/move-and-migration/new-moverequest?view=exchange-ps) Cmdlet。

## Exchange 內部部署

如果您使用 Exchange 內部部署，請使用此程序。

1. 進行此程序時，您要使用 AD 系統管理工具來新增內部部署網域帳戶的電子郵件地址。 此帳戶將同步處理至 Office 365。

- 在 **[Active Directory 使用者和電腦]** AD 工具中，以滑鼠右鍵按一下將在其上建立 Surface Hub 帳戶的資料夾或組織單位，然後依序按一下 **[新增]** 和 **[使用者]**。
- 在 **[完整名稱]** 方塊中輸入從上一個 Cmdlet 取得的顯示名稱，然後在 **[使用者登入名稱]** 方塊中輸入別名。 按 **[下一步]**。<p>

![在 Active Directory 中用來建立新使用者的新物件方塊。](images/hybriddeployment-01a.png)

- 輸入此帳戶的密碼。 您需要重新輸入密碼以進行驗證。 確定 **[密碼永久有效]** 核取方塊是唯一選取的選項。

> **重要** 您必須在 Surface Hub 上針對商務用 Skype 選取 **[密碼永久有效]**。 您的網域規則可能禁止使用不會過期的密碼。 如果是這樣，您就需要為每個 Surface Hub 裝置帳戶建立例外狀況。

![顯示密碼對話方塊的影像。](images/hybriddeployment-02a.png)

-   按一下 **[完成]** 以建立帳戶。

![顯示新使用者的帳戶名稱、登入名稱及密碼選項的影像。](images/hybriddeployment-03a.png)

2. 啟用遠端信箱。

以系統管理員權限開啟內部部署 Exchange 管理命令介面，並執行此 Cmdlet。

```PowerShell
Enable-RemoteMailbox 'HUB01@contoso.com' -RemoteRoutingAddress 'HUB01@contoso.com' -Room
```

> [!NOTE]
> 如果您沒有內部部署 Exchange 環境來執行此 Cmdlet，可以直接對帳戶的 Active Directory 物件進行相同的變更。
>
> msExchRemoteRecipientType = 33
>
> msExchRecipientDisplayType = -2147481850
>
> msExchRecipientTypeDetails = 8589934592

3. 建立帳戶之後，請執行目錄同步處理。 完成後，請移至 Microsoft 365 系統管理中心的 [使用者] 頁面，確認在先前步驟中建立的帳戶已合併至 [線上]。

4. 連線到 Microsoft Exchange Online，並在 Office 365 中設定帳戶的某些屬性。

在電腦上啟動遠端 PowerShell 工作階段，並連線到 Microsoft Exchange。 確定您已設定正確的權限來執行相關聯的 Cmdlet。

後續步驟將在您的 Office 365 租用戶上執行。

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://ps.outlook.com/powershell' -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

5. 建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。

設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。

Surface Hub 只會與具有 ActiveSync 原則且已將 **PasswordEnabled** 屬性設為 False 的裝置帳戶相容。 如果未正確設定此屬性，將無法啟用 Surface Hub 上的 Exchange 服務 (電子郵件、行事曆及加入會議)。

如果您尚未建立相容的原則，請使用下列 Cmdlet，此 Cmdlet 會建立名為 "Surface Hubs" 的原則。 一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

一旦您擁有相容的原則，就必須將原則套用到裝置帳戶。 

```PowerShell
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
```

6. 設定 Exchange 屬性

在裝置帳戶上設定 Exchange 屬性來改善會議體驗。 您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md) 一節中看到需要設定哪些屬性。

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Surface Hub room!'
```

7. 連線到 Azure AD。

您首先需要安裝 PowerShell 版本 2 的 Azure AD 模組。 在提升許可權的 PowerShell 提示中，執行下列命令：

```PowerShell
Install-Module -Name AzureAD
```

您需要連線到 Azure AD，以套用一些帳戶設定。 您可以執行這個 Cmdlet 來連線。

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. 指派 Office 365 授權。

裝置帳戶必須具備有效的 Office 365 (O365) 授權，否則 Exchange 和商務用 Skype 將無法運作。 如果您具有授權，就需要將使用位置指派給您的裝置帳戶，這會決定哪些授權 SKU 可供您的帳戶使用。

您可以使用 `Get-AzureADSubscribedSku` 擷取可供 O365 租用戶使用的 SKU 清單。

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

接下來，您可以搭配[商務用 Skype Online](#skype-for-business-online)、[商務用 Skype 內部部署](#skype-for-business-on-premises)，或[商務用 Skype Hybrid](#skype-for-business-hybrid) 啟用裝置帳戶。

### 商務用 Skype Online

您的租用戶使用者必須有 Exchange 信箱 (租用戶中至少需有一個 Exchange 信箱)。 下表說明您需要哪些方案或其他服務。

| Skype 會議室系統案例 | 如果您有 Office 365 Premium、適用于企業的 Microsoft 365 應用程式，或商務用 Skype 獨立方案2，您需要： | 如果您擁有企業方案，您需要： | 如果您有商務用 Skype Server 2015 （內部部署或混合式），您需要： |
| --- | --- | --- | --- |
| 加入已排程的會議 | 商務用 Skype 獨立方案 1 | E1、3、4 或 5 | 商務用 Skype Server Standard CAL |
| 起始臨時會議 | 商務用 Skype 獨立方案 2  | E 1、3、4 或 5 | 商務用 Skype Server Standard CAL 或 Enterprise CAL |
| 起始臨時會議並從會議撥出電話號碼 | 商務用 Skype 獨立方案2與音訊會議</br></br>**注意**PSTN 消費帳單為選用 | 使用音訊會議或 E5 的 E1 或 E3| 商務用 Skype Server Standard CAL 或 Enterprise CAL |
| 提供會議室電話號碼、從會議室撥出電話或接電話，或使用的電話號碼加入會議 | 商務用 Skype 獨立方案2與電話系統和 PSTN 語音通話方案 | [E1] 或 [E3] 與 [電話系統] 與 [PSTN 語音通話方案] 或 [E5] | 商務用 Skype Server Standard CAL 或 Plus CAL |

下表列出 Office 365 方案和商務用 Skype 選項。

| O365 方案 | 商務用 Skype | 電話系統 | 音訊會議 | 通話方案 |
| --- | --- | --- | --- | --- |
| O365 商務基本版 | 內含 |  |  |  |
| O365 商務進階版 | 內含 |  |  |  |
| E1 | 內含 | 附加元件 | 附加元件 | 附加元件（需要電話系統附加元件） |
| E3 | 內含 | 附加元件 | 附加元件 | 附加元件（需要電話系統附加元件） |
| E5 | 內含 | 內含 | 內含 | 附加元件  |

1. 請從電腦對商務用 Skype Online 環境建立遠端 PowerShell 工作階段做為開始。

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. 若要針對商務用 Skype Server 啟用您的 Surface Hub 帳戶，請執行下列 Cmdlet：

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet，從現有的商務用 Skype 使用者取得值：

```PowerShell
Get-CsOnlineUser -Identity ‘HUB01@contoso.com’| fl *registrarpool*
```

3. 將商務用 Skype 授權指派給您的 Surface Hub 帳戶。

 當您完成先前步驟以在商務用 Skype Online 上啟用 Surface Hub 帳戶之後，您需要將授權指派給 Surface Hub。 使用 O365 管理入口網站，將商務用 Skype Online （方案2）或商務用 Skype Online （方案3）授權指派到裝置。

- 以租用戶系統管理員身分登入、開啟 O365 系統管理入口網站，然後按一下 [系統管理] app。

- 依序按一下 **[使用者和群組]** 和 **[新增使用者、重設密碼及其他]**。

- 按一下 Surface Hub 帳戶，然後按一下畫筆圖示來編輯帳戶資訊。

- 按一下 **[授權]**。

- 在 [**指派授權**] 中，選取 [商務用 Skype （方案1）] 或 [商務用 Skype （方案2）]，視您的授權和企業語音需求而定。 如果您想要在 Surface Hub 上使用企業語音，就必須使用 [方案2授權]。

- 按一下 **\[儲存\]**。

> [!NOTE]
> 您也可以使用適用於 Windows PowerShell 的 Windows Azure Active Directory 模組，來執行指派這其中一個授權所需的 Cmdlet，但此處並未涵蓋相關說明。

若要進行驗證，您應該能夠使用任一個商務用 Skype 用戶端 (電腦、Android 等) 來登入此帳戶。

### 商務用 Skype 內部部署

若要執行此 Cmdlet，您需要連線到其中一個 Skype 前端。 開啟 Skype PowerShell 並執行：

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### 商務用 Skype Hybrid

如果您的組織已經設定[商務用 Skype 伺服器和商務用 Skype Online 之間的混合式連線](https://technet.microsoft.com/library/jj205403.aspx)，建立帳戶的指導方針就會和標準 Surface Hub 部署不一樣。

Surface Hub 需要 `meetingroom` 類型的 Skype 帳戶，一般的使用者則是在 Skype 中使用 user 類型帳戶。 如果您的 Skype 伺服器是針對混合式設定，其中可能有位於本機 Skype 伺服器的使用者和在 Office 365 中裝載的使用者，您可能會在嘗試建立 Surface Hub 帳戶時遇到幾個問題。

在商務用 Skype Server 2015 的混合式環境中，您要在商務用 Skype Online 中的任何使用者，都必須先在內部部署中建立，才能在 Active Directory 網域服務中建立使用者帳戶。 然後，您可以將使用者移至商務用 Skype Online。 從內部部署到線上的使用者帳戶移動是透過[move-csuser](https://technet.microsoft.com/library/gg398528.aspx) Cmdlet 來完成。 若要移動 Csmeetingroom 物件，請使用[Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) Cmdlet。

> [!NOTE]
> 若要使用 CsMeetingRoom Cmdlet，您必須已[針對商務用 Skype server 2015 安裝 2017 2017 年5月累積更新 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ，或安裝[Lync Server 2013 的累計更新 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)。


## Exchange Online

如果您使用 Exchange Online，請使用此程序。

1. 在 Office 365 中建立電子郵件帳戶。

在電腦上啟動遠端 PowerShell 工作階段，並連線到 Exchange。 確定您已設定正確的權限來執行相關聯的 Cmdlet。

```PowerShell
Set-ExecutionPolicy RemoteSigned
$cred=Get-Credential -Message "Please use your Office 365 admin credentials"
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/PowerShell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2. 設定信箱。

建立工作階段之後，您將建立新的信箱並啟用為 RoomMailboxAccount，或是變更現有會議室信箱的設定。 這可讓帳戶向 Surface Hub 進行驗證。

如果您正在變更現有的資源信箱：

```PowerShell
Set-Mailbox -Identity 'HUB01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

如果您正在建立新的資源信箱：

```PowerShell
New-Mailbox -MicrosoftOnlineServicesID 'HUB01@contoso.com' -Alias HUB01 -Name "Hub-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3. 建立 Exchange ActiveSync 原則。

設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。

Surface Hub 只會與具有已將 **PasswordEnabled** 屬性設為 False 之 ActiveSync 原則的裝置帳戶相容。 如果未正確設定，表面中樞（[郵件]、[行事曆] 和 [加入會議]）上的 Exchange 服務將不會啟用。

如果您尚未建立相容的原則，請使用下列 Cmdlet，此 Cmdlet 會建立名為 "Surface Hubs" 的原則。 一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。

```PowerShell
$easPolicy = New-MobileDeviceMailboxPolicy -Name “SurfaceHubs” -PasswordEnabled $false
```

一旦您擁有相容的原則，就必須將原則套用到裝置帳戶。 不過，原則只能套用到使用者帳戶，不能套用到資源信箱。 您需要將信箱轉換成使用者類型、套用原則，然後將它轉換回信箱 - 您可能也需要重新啟用它並再次設定密碼。

```PowerShell
Set-Mailbox 'HUB01@contoso.com' -Type Regular
Set-CASMailbox 'HUB01@contoso.com' -ActiveSyncMailboxPolicy $easPolicy.id
Set-Mailbox 'HUB01@contoso.com' -Type Room
$credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
Set-Mailbox 'HUB01@contoso.com' -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
```

4. 設定 Exchange 屬性

您必須在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。 您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)區段中查看需要設定哪些屬性。

```PowerShell
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'HUB01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
```

5. 新增內部部署網域帳戶的電子郵件地址。

進行此程序時，您要使用 AD 系統管理工具來新增內部部署網域帳戶的電子郵件地址。

- 在 **[Active Directory 使用者和電腦]** AD 工具中，以滑鼠右鍵按一下將在其上建立 Surface Hub 帳戶的資料夾或組織單位，然後依序按一下 **[新增]** 和 **[使用者]**。
- 在 **[完整名稱]** 方塊中輸入從上一個 Cmdlet 取得的顯示名稱，然後在 **[使用者登入名稱]** 方塊中輸入別名。 按 **[下一步]**。

![在 Active Directory 中用來建立新使用者的新物件方塊。](images/hybriddeployment-01a.png)

- 輸入此帳戶的密碼。 您需要重新輸入密碼以進行驗證。 確定 **[密碼永久有效]** 核取方塊是唯一選取的選項。

> [!IMPORTANT]
> 選取 [**密碼永不過期**] 是對 Surface Hub 上的商務用 Skype 的需求。 您的網域規則可能禁止使用不會過期的密碼。 如果是這樣，您就需要為每個 Surface Hub 裝置帳戶建立例外狀況。

![顯示密碼對話方塊的影像。](images/hybriddeployment-02a.png)

- 按一下 **[完成]** 以建立帳戶。

![顯示新使用者的帳戶名稱、登入名稱及密碼選項的影像。](images/hybriddeployment-03a.png)

6. 執行目錄同步作業。

建立帳戶之後，請執行目錄同步處理。 完成時，請移至使用者頁面，並確認已合併先前步驟中所建立的兩個帳戶。

7. 連線到 Azure AD。

您首先需要安裝 PowerShell 版本 2 的 Azure AD 模組。 在提升許可權的 PowerShell 提示中，執行下列命令：

```PowerShell
Install-Module -Name AzureAD
```

您需要連線到 Azure AD，以套用一些帳戶設定。 您可以執行此 Cmdlet 來進行連接：

```PowerShell
Import-Module AzureAD
Connect-AzureAD -Credential $cred
```

8. 指派 Office 365 授權。

裝置帳戶必須具備有效的 Office 365 (O365) 授權，否則 Exchange 和商務用 Skype 將無法運作。 如果您具有授權，就需要將使用位置指派給您的裝置帳戶，這會決定哪些授權 SKU 可供您的帳戶使用。

接下來，您可以使用 `Get-AzureADSubscribedSku` 擷取可供 O365 租用戶使用的 SKU 清單。

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

接下來，您可以搭配[商務用 Skype Online](#skype-for-business-online)、[商務用 Skype 內部部署](#skype-for-business-on-premises)，或[商務用 Skype Hybrid](#skype-for-business-hybrid) 啟用裝置帳戶。

### 商務用 Skype Online

若要啟用商務用 Skype，您的環境必須[符合商務用 Skype Online 的先決條件](#skype-for-business-online)：

1. 請從透過電腦建立商務用 Skype Online 環境的遠端 PowerShell 工作階段開始著手。

```PowerShell
Import-Module SkypeOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

2. 若要針對商務用 Skype Server 啟用您的 Surface Hub 帳戶，請執行下列 Cmdlet：

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool  
'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
```

   如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet，從現有的商務用 Skype 使用者取得值：

```PowerShell
Get-CsOnlineUser -Identity 'HUB01@contoso.com'| fl *registrarpool*
```

10. 將商務用 Skype 授權指派給您的 Surface Hub 帳戶

當您完成先前步驟以在商務用 Skype Online 上啟用 Surface Hub 帳戶之後，您需要將授權指派給 Surface Hub。 使用 O365 管理入口網站，將商務用 Skype Online （方案2）或商務用 Skype Online （方案3）授權指派到裝置。

- 以租用戶系統管理員身分登入、開啟 O365 系統管理入口網站，然後按一下 \[系統管理\] app。

- 依序按一下 **\[使用者和群組\]** 和 **\[新增使用者、重設密碼及其他\]**。

- 按一下 Surface Hub 帳戶，然後按一下畫筆圖示來編輯帳戶資訊。

- 按一下 **[授權]**。

- 在 **[指派授權]** 中，根據您的授權和企業語音需求來選取商務用 Skype (方案 2) 或商務用 Skype (方案 3)。 如果您想要在 Surface Hub 上使用企業語音，就必須使用方案 3 授權。

- 按一下 **[儲存]**。

> [!NOTE]
> 您也可以使用適用於 Windows PowerShell 的 Windows Azure Active Directory 模組，來執行指派這其中一個授權所需的 Cmdlet，但此處並未涵蓋相關說明。

若要進行驗證，您必須能夠使用任何商務用 Skype 用戶端 (電腦、Android 等) 來登入此帳戶。

### 商務用 Skype 內部部署

若要執行此 Cmdlet，您需要連線到其中一個 Skype 前端。 開啟 Skype PowerShell 並執行：

```PowerShell
Enable-CsMeetingRoom -Identity 'HUB01@contoso.com' -RegistrarPool registrarpoolfqdn -SipAddressType UserPrincipalName 
```

### 商務用 Skype Hybrid

如果您的組織已經設定[商務用 Skype 伺服器和商務用 Skype Online 之間的混合式連線](https://technet.microsoft.com/library/jj205403.aspx)，建立帳戶的指導方針就會和標準 Surface Hub 部署不一樣。

Surface Hub 需要 *meetingroom* 類型的 Skype 帳戶，一般的使用者則是在 Skype 中使用 *user* 類型帳戶。 如果您的 Skype 伺服器是針對混合式設定，其中可能有位於本機 Skype 伺服器的使用者和在 Office 365 中裝載的使用者，您可能會在嘗試建立 Surface Hub 帳戶時遇到幾個問題。

在商務用 Skype Server 2015 的混合式環境中，您要在商務用 Skype Online 中的任何使用者，都必須先在內部部署中建立，才能在 Active Directory 網域服務中建立使用者帳戶。 然後，您可以將使用者移至商務用 Skype Online。 從內部部署到線上的使用者帳戶移動是透過[move-csuser](https://technet.microsoft.com/library/gg398528.aspx) Cmdlet 來完成。 若要移動 Csmeetingroom 物件，請使用[Csmeetingroom](https://technet.microsoft.com/library/jj204889.aspx?f=255&mspperror=-2147217396) Cmdlet。

> [!NOTE]
> 若要使用 CsMeetingRoom Cmdlet，您必須已[針對商務用 Skype server 2015 安裝 2017 2017 年5月累積更新 6.0.9319.281](https://support.microsoft.com/help/4020991/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p) ，或安裝[Lync Server 2013 的累計更新 5.0.8308.992](https://support.microsoft.com/help/4034279/enables-the-move-csmeetingroom-cmdlet-to-move-a-meeting-room-from-on-p)。
