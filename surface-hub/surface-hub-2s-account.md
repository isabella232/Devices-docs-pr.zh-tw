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
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 6d8c41872481d86316d8985871fe74823e005ed8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831917"
---
# <span data-ttu-id="29de0-104">建立 Surface Hub 2S 裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="29de0-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="29de0-105">建立 Surface Hub 裝置帳戶（又稱為會議室信箱），Surface Hub 2 是透過 Microsoft 團隊或商務用 Skype 來接收、核准或拒絕會議邀請，並加入會議。</span><span class="sxs-lookup"><span data-stu-id="29de0-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="29de0-106">在全新安裝體驗（OOBE）設定期間，設定裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="29de0-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="29de0-107">如有需要，您可以稍後再變更（不需進行 OOBE 設定）。</span><span class="sxs-lookup"><span data-stu-id="29de0-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="29de0-108">與預設停用的標準會議室信箱不同，您必須啟用 Surface Hub 2 裝置帳戶，才能登入 Microsoft 團隊和商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="29de0-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="29de0-109">Surface Hub 2/2 依賴 Exchange ActiveSync，這需要裝置帳戶上的 ActiveSync 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="29de0-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="29de0-110">套用 Exchange Online 隨附的預設 ActiveSync 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="29de0-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="29de0-111">使用 Microsoft 365 管理中心或使用 PowerShell 來建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="29de0-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="29de0-112">您可以使用 Exchange Online PowerShell 來設定特定功能，包括：</span><span class="sxs-lookup"><span data-stu-id="29de0-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="29de0-113">每個 Surface Hub 裝置帳戶的行事曆處理。</span><span class="sxs-lookup"><span data-stu-id="29de0-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="29de0-114">針對排程要求自訂自動回復。</span><span class="sxs-lookup"><span data-stu-id="29de0-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="29de0-115">如果預設 ActiveSync 信箱原則已由其他人或其他程式修改，您可能需要建立並指派新的 ActiveSync 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="29de0-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="29de0-116">Surface Hub 裝置帳戶不支援協力廠商聯合身分識別身分識別提供者（FIPs），而且必須是標準的 Active Directory 或 Azure Active Directory 帳戶。</span><span class="sxs-lookup"><span data-stu-id="29de0-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="29de0-117">使用 Microsoft 365 系統管理中心建立帳戶</span><span class="sxs-lookup"><span data-stu-id="29de0-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="29de0-118">在 Microsoft 365 系統管理中心中，移至 [**資源**]，然後選擇 [**會議室] & 裝置**]，然後選取 [ **+ 會議室**]。</span><span class="sxs-lookup"><span data-stu-id="29de0-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="29de0-119">提供裝置帳戶的名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="29de0-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="29de0-120">保留預設狀態中不變的剩餘設定。</span><span class="sxs-lookup"><span data-stu-id="29de0-120">Leave remaining settings unchanged in the default state.</span></span>

   ![提供名稱和電子郵件地址](images/sh2-account2.png)

   ![保留預設狀態中不變的剩餘設定](images/sh2-account3.png)

3. <span data-ttu-id="29de0-123">設定裝置帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="29de0-123">Set the password for the device account.</span></span> <span data-ttu-id="29de0-124">若要設定密碼，請選擇 [**使用者**]，然後選取 [作用中的**使用者**]。</span><span class="sxs-lookup"><span data-stu-id="29de0-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="29de0-125">現在，搜尋新建立的使用者來設定密碼。</span><span class="sxs-lookup"><span data-stu-id="29de0-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="29de0-126">確定您**沒有**選取 [**讓此使用者在第一次登入時變更密碼**] 選項。</span><span class="sxs-lookup"><span data-stu-id="29de0-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![設定裝置帳戶的密碼](images/sh2-account4.png)

4. <span data-ttu-id="29de0-128">使用 Office 365 授權指派會議室。</span><span class="sxs-lookup"><span data-stu-id="29de0-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="29de0-129">建議您指派**Office 365 會議室**授權，這個新選項會自動啟用商務用 Skype Online 和 Microsoft 團隊的帳戶。</span><span class="sxs-lookup"><span data-stu-id="29de0-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![指派 Office 365 授權](images/sh2-account5.png)

### <span data-ttu-id="29de0-131">透過 PowerShell 完成設定</span><span class="sxs-lookup"><span data-stu-id="29de0-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="29de0-132">**商務用 Skype：** 若是 [僅限商務用 Skype] （內部部署或線上），您可以執行 [**啟用-CsMeetingRoom** ] 來啟用商務用 skype 物件，以啟用音訊和大廳保留等功能。</span><span class="sxs-lookup"><span data-stu-id="29de0-132">**Skype for Business:** For Skype for Business only (on-premises or online), you can enable the Skype for Business object by running **Enable-CsMeetingRoom** to enable features such as Meeting room prompt for audio and Lobby hold.</span></span>

- <span data-ttu-id="29de0-133">**Microsoft 團隊及商務用 Skype 行事曆：** 為此帳戶設定行事[**曆自動處理**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing)。</span><span class="sxs-lookup"><span data-stu-id="29de0-133">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="29de0-134">使用 PowerShell 建立帳戶</span><span class="sxs-lookup"><span data-stu-id="29de0-134">Create account using PowerShell</span></span>

<span data-ttu-id="29de0-135">您可以使用 PowerShell 建立帳戶，而不是使用 Microsoft 系統管理中心入口網站。</span><span class="sxs-lookup"><span data-stu-id="29de0-135">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="29de0-136">連線至 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="29de0-136">Connect to Exchange Online PowerShell</span></span>

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### <span data-ttu-id="29de0-137">建立新的會議室信箱</span><span class="sxs-lookup"><span data-stu-id="29de0-137">Create a new Room mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### <span data-ttu-id="29de0-138">設定行事曆自動處理</span><span class="sxs-lookup"><span data-stu-id="29de0-138">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### <span data-ttu-id="29de0-139">指派授權</span><span class="sxs-lookup"><span data-stu-id="29de0-139">Assign a license</span></span>

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## <span data-ttu-id="29de0-140">使用 PowerShell 連線到商務用 Skype Online</span><span class="sxs-lookup"><span data-stu-id="29de0-140">Connect to Skype for Business Online using PowerShell</span></span>

### <span data-ttu-id="29de0-141">安裝預備元件</span><span class="sxs-lookup"><span data-stu-id="29de0-141">Install pre-requisites</span></span>

- [<span data-ttu-id="29de0-142">Visual c + + 2017 可轉散發元件</span><span class="sxs-lookup"><span data-stu-id="29de0-142">Visual C++ 2017 Redistributable</span></span>](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [<span data-ttu-id="29de0-143">商務用 Skype Online PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="29de0-143">Skype for Business Online PowerShell Module</span></span>](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
