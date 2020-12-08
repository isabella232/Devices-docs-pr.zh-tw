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
ms.date: 12/07/2020
ms.localizationpriority: Medium
ms.openlocfilehash: e171d7c2db8a0d69594ca8d5f3a54f33ecebc9ae
ms.sourcegitcommit: dc08a2096a1fe955eb67e736e2a4453f75e926be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/07/2020
ms.locfileid: "11196726"
---
# <span data-ttu-id="0dd9e-104">建立 Surface Hub 2S 裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="0dd9e-104">Create Surface Hub 2S device account</span></span>

<span data-ttu-id="0dd9e-105">建立 Surface Hub 裝置帳戶 (也稱為會議室信箱) 可讓 Surface Hub 2 使用 Microsoft 團隊或商務用 Skype 來接收、核准或拒絕會議邀請，並加入會議。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-105">Creating a Surface Hub device account (also known as a Room mailbox) allows Surface Hub 2S to receive, approve, or decline meeting requests and join meetings using either Microsoft Teams or Skype for Business.</span></span> <span data-ttu-id="0dd9e-106">在全新的體驗中設定裝置帳戶 (OOBE) 設定。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-106">Configure the device account during Out-of-Box Experience (OOBE) setup.</span></span> <span data-ttu-id="0dd9e-107">如有需要，您可以在稍後 (進行變更，而不需要在 OOBE 設定) 。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-107">If needed, you can change it later (without going through OOBE setup).</span></span>

<span data-ttu-id="0dd9e-108">與預設停用的標準會議室信箱不同，您必須啟用 Surface Hub 2 裝置帳戶，才能登入 Microsoft 團隊和商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-108">Unlike standard Room mailboxes that remain disabled by default, you need to enable the Surface Hub 2S device account to sign on to Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="0dd9e-109">Surface Hub 2/2 依賴 Exchange ActiveSync，這需要裝置帳戶上的 ActiveSync 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-109">Surface Hub 2S relies on Exchange ActiveSync, which requires an ActiveSync mailbox policy on the device account.</span></span> <span data-ttu-id="0dd9e-110">套用 Exchange Online 隨附的預設 ActiveSync 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-110">Apply the default ActiveSync mailbox policy that comes with Exchange Online.</span></span>

<span data-ttu-id="0dd9e-111">使用 Microsoft 365 管理中心或使用 PowerShell 來建立帳戶。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-111">Create the account by using the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="0dd9e-112">您可以使用 Exchange Online PowerShell 來設定特定功能，包括：</span><span class="sxs-lookup"><span data-stu-id="0dd9e-112">You can use Exchange Online PowerShell to configure specific features including:</span></span>

- <span data-ttu-id="0dd9e-113">每個 Surface Hub 裝置帳戶的行事曆處理。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-113">Calendar processing for every Surface Hub device account.</span></span>
- <span data-ttu-id="0dd9e-114">針對排程要求自訂自動回復。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-114">Custom auto replies to scheduling requests.</span></span>
- <span data-ttu-id="0dd9e-115">如果預設 ActiveSync 信箱原則已由其他人或其他程式修改，您可能需要建立並指派新的 ActiveSync 信箱原則。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-115">If the default ActiveSync mailbox policy has already been modified by someone else or by another process, you will likely have to create and assign a new ActiveSync mailbox policy.</span></span>

> [!NOTE]  
> <span data-ttu-id="0dd9e-116">Surface Hub 裝置帳戶不支援協力廠商同盟身分識別提供者 (FIPs) ，而且必須是標準的 Active Directory 或 Azure Active Directory 帳戶。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-116">The Surface Hub device account doesn’t support third-party Federated Identity Providers (FIPs) and must be a standard Active Directory or Azure Active Directory account.</span></span>

## <span data-ttu-id="0dd9e-117">使用 Microsoft 365 系統管理中心建立帳戶</span><span class="sxs-lookup"><span data-stu-id="0dd9e-117">Create account using Microsoft 365 admin center</span></span>

1. <span data-ttu-id="0dd9e-118">在 Microsoft 365 系統管理中心中，移至 [ **資源** ]，然後選擇 [ **會議室] & 裝置** ]，然後選取 [ **+ 會議室**]。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-118">In the Microsoft 365 admin center, go to **Resources** and choose **Rooms & Equipment** and then select **+ Room**.</span></span>

2. <span data-ttu-id="0dd9e-119">提供裝置帳戶的名稱和電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-119">Provide a name and email address for the device account.</span></span> <span data-ttu-id="0dd9e-120">保留預設狀態中不變的剩餘設定。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-120">Leave remaining settings unchanged in the default state.</span></span>

   ![提供名稱和電子郵件地址](images/sh2-account2.png)

   ![保留預設狀態中不變的剩餘設定](images/sh2-account3.png)

3. <span data-ttu-id="0dd9e-123">設定裝置帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-123">Set the password for the device account.</span></span> <span data-ttu-id="0dd9e-124">若要設定密碼，請選擇 [ **使用者** ]，然後選取 [作用中的 **使用者**]。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-124">To set the password, choose **Users** and then select **Active Users**.</span></span> <span data-ttu-id="0dd9e-125">現在，搜尋新建立的使用者來設定密碼。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-125">Now search for the newly created user to set the password.</span></span> <span data-ttu-id="0dd9e-126">確定您**沒有**選取 [**讓此使用者在第一次登入時變更密碼**] 選項。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-126">Ensure that you **do not** select the option **Make this user change their password when they first sign in.**</span></span>

   ![設定裝置帳戶的密碼](images/sh2-account4.png)

4. <span data-ttu-id="0dd9e-128">使用 Office 365 授權指派會議室。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-128">Assign the room with an Office 365 license.</span></span> <span data-ttu-id="0dd9e-129">建議您指派 **Office 365 會議室** 授權，這個新選項會自動啟用商務用 Skype Online 和 Microsoft 團隊的帳戶。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-129">It’s recommended to assign the Office 365 **Meeting Room** license, a new option that automatically enables the account for Skype for Business Online and Microsoft Teams.</span></span>

   ![指派 Office 365 授權](images/sh2-account5.png)

### <span data-ttu-id="0dd9e-131">透過 PowerShell 完成設定</span><span class="sxs-lookup"><span data-stu-id="0dd9e-131">Finalize setup via PowerShell</span></span>

- <span data-ttu-id="0dd9e-132">**Microsoft 團隊及商務用 Skype 行事曆：** 為此帳戶設定行事 [**曆自動處理**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) 。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-132">**Microsoft Teams and Skype for Business Calendar:** Set [**Calendar Auto processing**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) for this account.</span></span>

## <span data-ttu-id="0dd9e-133">使用 PowerShell 建立帳戶</span><span class="sxs-lookup"><span data-stu-id="0dd9e-133">Create account using PowerShell</span></span>

<span data-ttu-id="0dd9e-134">您可以使用 PowerShell 建立帳戶，而不是使用 Microsoft 系統管理中心入口網站。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-134">Instead of using the Microsoft Admin Center portal, you can create the account using PowerShell.</span></span>

### <span data-ttu-id="0dd9e-135">連線至 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="0dd9e-135">Connect to Exchange Online PowerShell</span></span>

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### <span data-ttu-id="0dd9e-136">建立信箱</span><span class="sxs-lookup"><span data-stu-id="0dd9e-136">Create mailbox</span></span>

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### <span data-ttu-id="0dd9e-137">設定行事曆自動處理</span><span class="sxs-lookup"><span data-stu-id="0dd9e-137">Set Calendar auto-processing</span></span>

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### <span data-ttu-id="0dd9e-138">如果需要使用電子郵件應用程式，請啟用 ActiveSync</span><span class="sxs-lookup"><span data-stu-id="0dd9e-138">Enable ActiveSync if use of email app is required</span></span>

 <span data-ttu-id="0dd9e-139">如果 unchnaged，預設的 ActiveSync 原則就會運作。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-139">The default ActiveSync Policy will work if unchnaged.</span></span> <span data-ttu-id="0dd9e-140">否則，請建立新的原則並指派。</span><span class="sxs-lookup"><span data-stu-id="0dd9e-140">Otherwise create a new Policy and assign.</span></span>

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### <span data-ttu-id="0dd9e-141">連線到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="0dd9e-141">Connect to Azure AD</span></span>

```powershell
Connect-AzureAD
```

### <span data-ttu-id="0dd9e-142">指派授權</span><span class="sxs-lookup"><span data-stu-id="0dd9e-142">Assign a license</span></span>

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### <span data-ttu-id="0dd9e-143">檢查可用的授權</span><span class="sxs-lookup"><span data-stu-id="0dd9e-143">Check for available licenses</span></span>

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```