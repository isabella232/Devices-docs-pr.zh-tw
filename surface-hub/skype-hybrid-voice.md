---
title: 線上或混合式部署，使用 Skype 混合語音環境 (Surface Hub)
description: 本主題說明如何透過 Cloud Connector 版或商務用 Skype 2015 集區，以內部部署 PSTN 連線啟用商務用 Skype 雲端 PBX。
keywords: hybrid deployment, Skype Hybrid Voice, 混合部署, Skype 混音
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 08349a7d2decb4d4b053cb03fc95808b49d4f2f0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831942"
---
# 線上或混合式部署，使用 Skype 混合語音環境 (Surface Hub)

本主題說明如何透過 Cloud Connector 版或商務用 Skype 2015 集區，以內部部署公用交換電話網路 (PSTN) 連線啟用商務用 Skype 雲端 PBX。 在此選項中， 您的商務用 Skype 主集區與 Exchange 伺服器會在雲端，並由 PSTN 透過執行商務用 Skype 2015 或 Cloud Connector 版的內部部署集區連線。 [深入了解不同的雲端 PBX 選項](https://technet.microsoft.com/library/mt612869.aspx) (英文)。  

如果您已部署有其中一個混音選項的商務用 Skype 雲端 PBX，請依照下列步驟為 Surface Hub 啟用會議室帳戶。 請務必先建立一般使用者帳戶，再指派所有混音選項與電話號碼，然後將帳戶轉換為會議室帳戶。 如果您未依照此順序進行，則無法指派混合電話號碼。  

>[!WARNING]
>如果您先建立帳戶，再設定混音 (您執行 Enable-CSMeetingRoom 命令)，則將無法設定所需的混音參數。 為了替先前設定的帳戶設定混音參數，或要重新設定電話號碼，請刪除 E5 或 E3 + 雲端 PBX 附加元件授權，然後依照下列步驟執行，從步驟 3 開始。

1. 為 Surface Hub 建立新的使用者帳戶。 這個範例使用 <strong> surfacehub2@adatum.com </strong> 。 您可以在本機 Active Directory 中建立帳戶並同步處理到雲端，或直接在雲端建立。 

    ![新物件使用者](images/new-user-hybrid-voice.png)

2. 選取 **\[密碼永久有效\]**。 這對於 Surface Hub 裝置而言很重要。

   ![密碼永久有效](images/new-user-password-hybrid-voice.png)

3. 在 Office 365 中，將 **E5** 授權或 **E3 與雲端 PBX** 附加元件新增至為會議室建立的帳戶。 這是讓混音能夠運作所需要的。

   ![新增產品授權](images/product-license-hybrid-voice.png)

4. 等待約 15 分鐘，直到會議室的使用者帳戶出現在商務用 Skype Online 中。

5. 在商務用 Skype Online 中建立會議室的使用者帳戶後，請執行下列 Cmdlet 為商務用 Skype 遠端 PowerShell 中的混音啟用此帳戶：

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. 透過從 Surface Hub 撥打測試電話來驗證混音通話流程。

7. 在電腦上啟動遠端 PowerShell 工作階段，然後執行下列 Cmdlet 連線至 Exchange。

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. 建立工作階段後，透過建立下列 Cmdlet 修改會議室的使用者帳戶，讓帳戶成為 **RoomMailboxAccount**。 這可讓帳戶向 Surface Hub 進行驗證。

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. 設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。

   Surface Hub 只會與具有已將 **PasswordEnabled** 屬性設為 **False** 之 ActiveSync 原則的裝置帳戶相容。 如果未正確設定此屬性，將無法啟用 Surface Hub 上的 Exchange 服務 (電子郵件、行事曆及加入會議)。
    
   如果您尚未建立相容的原則，請使用下列 Cmdlet (此 Cmdlet 會建立名為 "Surface Hubs" 的原則)。 一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   當您具備相容的原則之後，您接著需要將原則套用到裝置帳戶。 不過，原則只能套用到使用者帳戶，不能套用到資源信箱。 執行下列 Cmdlet 將信箱轉換成使用者類型、套用原則，然後將它轉換回信箱 (您可能需要重新啟用帳戶並再次設定密碼)。
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. 您必須在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。 您也可以看到哪些屬性可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)中設定。 下列 Cmdlet 提供設定 Exchange 屬性的範例。

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. 啟用信箱作為商務用 Skype Online 中的會議裝置。 執行下列可讓帳戶成為會議裝置的 Cmdlet。 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    由於執行此 Cmdlet，因此系統會詢問使用者是否在會議室中，如下圖所示。 選取 **\[是\]** 會將麥克風及喇叭設為靜音。

    ![](images/adjust-room-audio.png)


    
目前會議室帳戶已完整設定，包括混音。 如果您使用內部部署的 Skype，您可以設定內部部署的其他屬性，包括描述、位置等。 如果您在 Skype Online 建立會議室，則這些參數可線上設定。 

在下圖中，您可以看見裝置如何對使用者顯示。


![](images/select-room-hybrid-voice.png)
