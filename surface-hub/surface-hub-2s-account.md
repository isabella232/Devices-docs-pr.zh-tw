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
# 建立 Surface Hub 2S 裝置帳戶

建立 Surface Hub 裝置帳戶 (也稱為會議室信箱) 可讓 Surface Hub 2 使用 Microsoft 團隊或商務用 Skype 來接收、核准或拒絕會議邀請，並加入會議。 在全新的體驗中設定裝置帳戶 (OOBE) 設定。 如有需要，您可以在稍後 (進行變更，而不需要在 OOBE 設定) 。

與預設停用的標準會議室信箱不同，您必須啟用 Surface Hub 2 裝置帳戶，才能登入 Microsoft 團隊和商務用 Skype。 Surface Hub 2/2 依賴 Exchange ActiveSync，這需要裝置帳戶上的 ActiveSync 信箱原則。 套用 Exchange Online 隨附的預設 ActiveSync 信箱原則。

使用 Microsoft 365 管理中心或使用 PowerShell 來建立帳戶。 您可以使用 Exchange Online PowerShell 來設定特定功能，包括：

- 每個 Surface Hub 裝置帳戶的行事曆處理。
- 針對排程要求自訂自動回復。
- 如果預設 ActiveSync 信箱原則已由其他人或其他程式修改，您可能需要建立並指派新的 ActiveSync 信箱原則。

> [!NOTE]  
> Surface Hub 裝置帳戶不支援協力廠商同盟身分識別提供者 (FIPs) ，而且必須是標準的 Active Directory 或 Azure Active Directory 帳戶。

## 使用 Microsoft 365 系統管理中心建立帳戶

1. 在 Microsoft 365 系統管理中心中，移至 [ **資源** ]，然後選擇 [ **會議室] & 裝置** ]，然後選取 [ **+ 會議室**]。

2. 提供裝置帳戶的名稱和電子郵件地址。 保留預設狀態中不變的剩餘設定。

   ![提供名稱和電子郵件地址](images/sh2-account2.png)

   ![保留預設狀態中不變的剩餘設定](images/sh2-account3.png)

3. 設定裝置帳戶的密碼。 若要設定密碼，請選擇 [ **使用者** ]，然後選取 [作用中的 **使用者**]。 現在，搜尋新建立的使用者來設定密碼。 確定您**沒有**選取 [**讓此使用者在第一次登入時變更密碼**] 選項。

   ![設定裝置帳戶的密碼](images/sh2-account4.png)

4. 使用 Office 365 授權指派會議室。 建議您指派 **Office 365 會議室** 授權，這個新選項會自動啟用商務用 Skype Online 和 Microsoft 團隊的帳戶。

   ![指派 Office 365 授權](images/sh2-account5.png)

### 透過 PowerShell 完成設定

- **Microsoft 團隊及商務用 Skype 行事曆：** 為此帳戶設定行事 [**曆自動處理**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing) 。

## 使用 PowerShell 建立帳戶

您可以使用 PowerShell 建立帳戶，而不是使用 Microsoft 系統管理中心入口網站。

### 連線至 Exchange Online PowerShell

```powershell
Install-Module -Name ExchangeOnlineManagement
Import-Module ExchangeOnlineManagement
Connect-ExchangeOnline -UserPrincipalName admin@contoso.com -ShowProgress $true
```

### 建立信箱

```powershell
New-Mailbox -MicrosoftOnlineServicesID 'SurfaceHub01@contoso.com' -Alias SurfaceHub01 -Name "Surface Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'Pass@word1' -AsPlainText -Force)
```

### 設定行事曆自動處理

```powershell
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity 'SurfaceHub01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Surface Hub. Please make sure this meeting is a Microsoft Teams meeting!"
```

### 如果需要使用電子郵件應用程式，請啟用 ActiveSync

 如果 unchnaged，預設的 ActiveSync 原則就會運作。 否則，請建立新的原則並指派。

```powershell
New-MobileDeviceMailboxPolicy -Name:"SurfaceHub" -PasswordEnabled:$false
#Assign Policy to Hub:
Set-CASMailbox -Identity SurfaceHub01@contoso.com -ActiveSyncMailboxPolicy "SurfaceHub"
```
### 連線到 Azure AD

```powershell
Connect-AzureAD
```

### 指派授權

```powershell
Set-AzureADUser -ObjectId 'SurfaceHub01@contoso.com' -UsageLocation US
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense 
$License.SkuId = "c7df2760-2c81-4ef7-b578-5b5392b571df" 
$Licenses = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses 
$Licenses.AddLicenses = $License 
Set-AzureADUserLicense -ObjectId 'SurfaceHub01@contoso.com' -AssignedLicenses $Licenses
```

### 檢查可用的授權

```powershell
Get-AzureADUser -Filter "userPrincipalName eq 'SurfaceHub01@contoso.com'" |fl *
#Meeting Room Standard SKU:
6070a4c8-34c6-4937-8dfb-39bbc6397a60
```