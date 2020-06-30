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
# <span data-ttu-id="cc355-104">線上或混合式部署，使用 Skype 混合語音環境 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="cc355-104">Online or hybrid deployment using Skype Hybrid Voice environment  (Surface Hub)</span></span>

<span data-ttu-id="cc355-105">本主題說明如何透過 Cloud Connector 版或商務用 Skype 2015 集區，以內部部署公用交換電話網路 (PSTN) 連線啟用商務用 Skype 雲端 PBX。</span><span class="sxs-lookup"><span data-stu-id="cc355-105">This topic explains how to enable Skype for Business Cloud PBX with on-premises Public Switched Telephone Network (PSTN) connectivity via Cloud Connector Edition or Skype for Business 2015 pool.</span></span> <span data-ttu-id="cc355-106">在此選項中，</span><span class="sxs-lookup"><span data-stu-id="cc355-106">In this option.</span></span> <span data-ttu-id="cc355-107">您的商務用 Skype 主集區與 Exchange 伺服器會在雲端，並由 PSTN 透過執行商務用 Skype 2015 或 Cloud Connector 版的內部部署集區連線。</span><span class="sxs-lookup"><span data-stu-id="cc355-107">your Skype for Business home pools and Exchange servers are in the cloud, and are connected by PSTN via an on-premises pool running Skype for Business 2015 or Cloud Connector edition.</span></span> <span data-ttu-id="cc355-108">[深入了解不同的雲端 PBX 選項](https://technet.microsoft.com/library/mt612869.aspx) (英文)。</span><span class="sxs-lookup"><span data-stu-id="cc355-108">[Learn more about different Cloud PBX options](https://technet.microsoft.com/library/mt612869.aspx).</span></span>  

<span data-ttu-id="cc355-109">如果您已部署有其中一個混音選項的商務用 Skype 雲端 PBX，請依照下列步驟為 Surface Hub 啟用會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc355-109">If you deployed Skype for Business Cloud PBX with one of the hybrid voice options, follow the steps below to enable the room account for Surface Hub.</span></span> <span data-ttu-id="cc355-110">請務必先建立一般使用者帳戶，再指派所有混音選項與電話號碼，然後將帳戶轉換為會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc355-110">It is important to create a regular user account first, assign all hybrid voice options and phone numbers, and then convert the account to a room account.</span></span> <span data-ttu-id="cc355-111">如果您未依照此順序進行，則無法指派混合電話號碼。</span><span class="sxs-lookup"><span data-stu-id="cc355-111">If you do not follow this order, you will not be able to assign a hybrid phone number.</span></span>  

>[!WARNING]
><span data-ttu-id="cc355-112">如果您先建立帳戶，再設定混音 (您執行 Enable-CSMeetingRoom 命令)，則將無法設定所需的混音參數。</span><span class="sxs-lookup"><span data-stu-id="cc355-112">If you create an account before configuration of Hybrid voice (you run Enable-CSMeetingRoom command), you will not be able to configure required hybrid voice parameters.</span></span> <span data-ttu-id="cc355-113">為了替先前設定的帳戶設定混音參數，或要重新設定電話號碼，請刪除 E5 或 E3 + 雲端 PBX 附加元件授權，然後依照下列步驟執行，從步驟 3 開始。</span><span class="sxs-lookup"><span data-stu-id="cc355-113">In order to configure hybrid voice parameters for a previously configured account or to reconfigure a phone number, delete the E5 or E3  + Cloud PBX add-on license, and then follow the steps below, starting at step 3.</span></span>

1. <span data-ttu-id="cc355-114">為 Surface Hub 建立新的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc355-114">Create a new user account for Surface Hub.</span></span> <span data-ttu-id="cc355-115">這個範例使用 <strong> surfacehub2@adatum.com </strong> 。</span><span class="sxs-lookup"><span data-stu-id="cc355-115">This example uses <strong>surfacehub2@adatum.com</strong>.</span></span> <span data-ttu-id="cc355-116">您可以在本機 Active Directory 中建立帳戶並同步處理到雲端，或直接在雲端建立。</span><span class="sxs-lookup"><span data-stu-id="cc355-116">The account can be created in local Active Directory and synchronized to the cloud, or created directly in the cloud.</span></span> 

    ![新物件使用者](images/new-user-hybrid-voice.png)

2. <span data-ttu-id="cc355-118">選取 **\[密碼永久有效\]**。</span><span class="sxs-lookup"><span data-stu-id="cc355-118">Select **Password Never Expires**.</span></span> <span data-ttu-id="cc355-119">這對於 Surface Hub 裝置而言很重要。</span><span class="sxs-lookup"><span data-stu-id="cc355-119">This is important for a Surface Hub device.</span></span>

   ![密碼永久有效](images/new-user-password-hybrid-voice.png)

3. <span data-ttu-id="cc355-121">在 Office 365 中，將 **E5** 授權或 **E3 與雲端 PBX** 附加元件新增至為會議室建立的帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc355-121">In Office 365, add **E5** license or **E3 and Cloud PBX** add-on to the user account created for the room.</span></span> <span data-ttu-id="cc355-122">這是讓混音能夠運作所需要的。</span><span class="sxs-lookup"><span data-stu-id="cc355-122">This is required for Hybrid Voice to work.</span></span>

   ![新增產品授權](images/product-license-hybrid-voice.png)

4. <span data-ttu-id="cc355-124">等待約 15 分鐘，直到會議室的使用者帳戶出現在商務用 Skype Online 中。</span><span class="sxs-lookup"><span data-stu-id="cc355-124">Wait approximately 15 minutes until the user account for the room appears in Skype for Business Online.</span></span>

5. <span data-ttu-id="cc355-125">在商務用 Skype Online 中建立會議室的使用者帳戶後，請執行下列 Cmdlet 為商務用 Skype 遠端 PowerShell 中的混音啟用此帳戶：</span><span class="sxs-lookup"><span data-stu-id="cc355-125">After the user account for room is created in Skype for Business Online, enable it for Hybrid Voice in Skype for Business Remote PowerShell by running the following cmdlet:</span></span>

   ```
   Set-csuser surfacehub2@adatum.com EnterpriseVoiceEnabled $true -HostedVoiceMail $true -onpremlineuri tel:+15005000102
   ```
    
6. <span data-ttu-id="cc355-126">透過從 Surface Hub 撥打測試電話來驗證混音通話流程。</span><span class="sxs-lookup"><span data-stu-id="cc355-126">Validate Hybrid Voice call flow by placing test calls from the Surface Hub.</span></span>

7. <span data-ttu-id="cc355-127">在電腦上啟動遠端 PowerShell 工作階段，然後執行下列 Cmdlet 連線至 Exchange。</span><span class="sxs-lookup"><span data-stu-id="cc355-127">Start a remote PowerShell session on a PC and connect to Exchange by running the following cmdlets.</span></span>

   ```
   Set-ExecutionPolicy Unrestricted
   $cred=Get-Credential -Message "Please use your Office 365 admin credentials"
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
   Import-PSSession $sess
   ```
    
8. <span data-ttu-id="cc355-128">建立工作階段後，透過建立下列 Cmdlet 修改會議室的使用者帳戶，讓帳戶成為 **RoomMailboxAccount**。</span><span class="sxs-lookup"><span data-stu-id="cc355-128">After establishing a session, modify the user account for the room to enable it as a **RoomMailboxAccount** by running the following cmdlets.</span></span> <span data-ttu-id="cc355-129">這可讓帳戶向 Surface Hub 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="cc355-129">This allows the account to authenticate with Surface Hub.</span></span>

   ```
   Set-Mailbox surfacehub2@adatum.com -Type Room
   Set-Mailbox surfacehub2@adatum.com -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```
    
9. <span data-ttu-id="cc355-130">設定信箱之後，您需要建立新的 Exchange ActiveSync 原則，或使用相容的現有原則。</span><span class="sxs-lookup"><span data-stu-id="cc355-130">After setting up the mailbox, you will need to either create a new Exchange ActiveSync policy, or use a compatible existing policy.</span></span>

   <span data-ttu-id="cc355-131">Surface Hub 只會與具有已將 **PasswordEnabled** 屬性設為 **False** 之 ActiveSync 原則的裝置帳戶相容。</span><span class="sxs-lookup"><span data-stu-id="cc355-131">Surface Hubs are only compatible with device accounts that have an ActiveSync policy where the **PasswordEnabled** property is set to **False**.</span></span> <span data-ttu-id="cc355-132">如果未正確設定此屬性，將無法啟用 Surface Hub 上的 Exchange 服務 (電子郵件、行事曆及加入會議)。</span><span class="sxs-lookup"><span data-stu-id="cc355-132">If this isn’t set properly, then Exchange services on the Surface Hub (mail, calendar, and joining meetings), will not be enabled.</span></span>
    
   <span data-ttu-id="cc355-133">如果您尚未建立相容的原則，請使用下列 Cmdlet (此 Cmdlet 會建立名為 "Surface Hubs" 的原則)。</span><span class="sxs-lookup"><span data-stu-id="cc355-133">If you haven’t created a compatible policy yet, use the following cmdlet (this one creates a policy called "Surface Hubs").</span></span> <span data-ttu-id="cc355-134">一旦建立之後，您就可以將相同原則套用到其他的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc355-134">After it’s created, you can apply the same policy to other device accounts.</span></span>

   ```
   $easPolicy = New-MobileDeviceMailboxPolicy -Name "SurfaceHubs" -PasswordEnabled $false
   ```
    
   <span data-ttu-id="cc355-135">當您具備相容的原則之後，您接著需要將原則套用到裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="cc355-135">After you have a compatible policy, then you will need to apply the policy to the device account.</span></span> <span data-ttu-id="cc355-136">不過，原則只能套用到使用者帳戶，不能套用到資源信箱。</span><span class="sxs-lookup"><span data-stu-id="cc355-136">However, policies can only be applied to user accounts and not resource mailboxes.</span></span> <span data-ttu-id="cc355-137">執行下列 Cmdlet 將信箱轉換成使用者類型、套用原則，然後將它轉換回信箱 (您可能需要重新啟用帳戶並再次設定密碼)。</span><span class="sxs-lookup"><span data-stu-id="cc355-137">Run the following cmdlets to convert the mailbox into a user type, apply the policy, and then convert it back into a mailbox (you may need to re-enable the account and set the password again).</span></span>
    
   ```
   Set-Mailbox surfacehub2@adatum.com -Type Regular
   Set-CASMailbox surfacehub2@adatum.com -ActiveSyncMailboxPolicy $easPolicy.id
   Set-Mailbox surfacehub2@adatum.com -Type Room
   $credNewAccount = Get-Credential -Message "Please provide the Surface Hub username and password"
   Set-Mailbox surfacehub2@adatum.com -RoomMailboxPassword $credNewAccount.Password -EnableRoomMailboxAccount $true
   ```
    
10. <span data-ttu-id="cc355-138">您必須在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="cc355-138">Various Exchange properties must be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="cc355-139">您也可以看到哪些屬性可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)中設定。</span><span class="sxs-lookup"><span data-stu-id="cc355-139">You can see which properties can be set in [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> <span data-ttu-id="cc355-140">下列 Cmdlet 提供設定 Exchange 屬性的範例。</span><span class="sxs-lookup"><span data-stu-id="cc355-140">The following cmdlets provide an example of setting Exchange properties.</span></span>

    ```
    Set-CalendarProcessing surfacehub2@adatum.com -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing surfacehub2@adatum.com -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

11. <span data-ttu-id="cc355-141">啟用信箱作為商務用 Skype Online 中的會議裝置。</span><span class="sxs-lookup"><span data-stu-id="cc355-141">Enable the mailbox as a meeting device in Skype for Business Online.</span></span> <span data-ttu-id="cc355-142">執行下列可讓帳戶成為會議裝置的 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cc355-142">Run the following cmdlet which enables the account as a meeting device.</span></span> 

    ```
    Get-CsTenant | select registrarpool
    Enable-CsMeetingRoom surfacehub2@adatum.com -RegistrarPool  'sippoolbl20a04.infra.lync.com' -SipAddressType UserPrincipalName
    ```
    
    <span data-ttu-id="cc355-143">由於執行此 Cmdlet，因此系統會詢問使用者是否在會議室中，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="cc355-143">As a result of running this cmdlet, users will be asked if they are in a meeting room, as shown in the following image.</span></span> <span data-ttu-id="cc355-144">選取 **\[是\]** 會將麥克風及喇叭設為靜音。</span><span class="sxs-lookup"><span data-stu-id="cc355-144">**Yes** will mute the microphone and speaker.</span></span>

    ![](images/adjust-room-audio.png)


    
<span data-ttu-id="cc355-145">目前會議室帳戶已完整設定，包括混音。</span><span class="sxs-lookup"><span data-stu-id="cc355-145">At this moment the room account is fully configured, including Hybrid Voice.</span></span> <span data-ttu-id="cc355-146">如果您使用內部部署的 Skype，您可以設定內部部署的其他屬性，包括描述、位置等。</span><span class="sxs-lookup"><span data-stu-id="cc355-146">If you use Skype on-premises, you can configure additional attributes, like description, location, etc., on-premises.</span></span> <span data-ttu-id="cc355-147">如果您在 Skype Online 建立會議室，則這些參數可線上設定。</span><span class="sxs-lookup"><span data-stu-id="cc355-147">If you create a room in Skype Online, these parameters can be set online.</span></span> 

<span data-ttu-id="cc355-148">在下圖中，您可以看見裝置如何對使用者顯示。</span><span class="sxs-lookup"><span data-stu-id="cc355-148">In the following image, you can see how the device appears to users.</span></span>


![](images/select-room-hybrid-voice.png)
