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
# 建立 Surface Hub 2S 裝置帳戶

建立 Surface Hub 裝置帳戶（又稱為會議室信箱），Surface Hub 2 是透過 Microsoft 團隊或商務用 Skype 來接收、核准或拒絕會議邀請，並加入會議。 在全新安裝體驗（OOBE）設定期間，設定裝置帳戶。 如有需要，您可以稍後再變更（不需進行 OOBE 設定）。

與預設停用的標準會議室信箱不同，您必須啟用 Surface Hub 2 裝置帳戶，才能登入 Microsoft 團隊和商務用 Skype。 Surface Hub 2/2 依賴 Exchange ActiveSync，這需要裝置帳戶上的 ActiveSync 信箱原則。 套用 Exchange Online 隨附的預設 ActiveSync 信箱原則。

使用 Microsoft 365 管理中心或使用 PowerShell 來建立帳戶。 您可以使用 Exchange Online PowerShell 來設定特定功能，包括：

- 每個 Surface Hub 裝置帳戶的行事曆處理。
- 針對排程要求自訂自動回復。
- 如果預設 ActiveSync 信箱原則已由其他人或其他程式修改，您可能需要建立並指派新的 ActiveSync 信箱原則。

> [!NOTE]  
> Surface Hub 裝置帳戶不支援協力廠商聯合身分識別身分識別提供者（FIPs），而且必須是標準的 Active Directory 或 Azure Active Directory 帳戶。

## 使用 Microsoft 365 系統管理中心建立帳戶

1. 在 Microsoft 365 系統管理中心中，移至 [**資源**]，然後選擇 [**會議室] & 裝置**]，然後選取 [ **+ 會議室**]。

2. 提供裝置帳戶的名稱和電子郵件地址。 保留預設狀態中不變的剩餘設定。

   ![提供名稱和電子郵件地址](images/sh2-account2.png)

   ![保留預設狀態中不變的剩餘設定](images/sh2-account3.png)

3. 設定裝置帳戶的密碼。 若要設定密碼，請選擇 [**使用者**]，然後選取 [作用中的**使用者**]。 現在，搜尋新建立的使用者來設定密碼。 確定您**沒有**選取 [**讓此使用者在第一次登入時變更密碼**] 選項。

   ![設定裝置帳戶的密碼](images/sh2-account4.png)

4. 使用 Office 365 授權指派會議室。 建議您指派**Office 365 會議室**授權，這個新選項會自動啟用商務用 Skype Online 和 Microsoft 團隊的帳戶。

   ![指派 Office 365 授權](images/sh2-account5.png)

### 透過 PowerShell 完成設定

- **商務用 Skype：** 若是 [僅限商務用 Skype] （內部部署或線上），您可以執行 [**啟用-CsMeetingRoom** ] 來啟用商務用 skype 物件，以啟用音訊和大廳保留等功能。

- **Microsoft 團隊及商務用 Skype 行事曆：** 為此帳戶設定行事[**曆自動處理**](https://docs.microsoft.com/surface-hub/surface-hub-2s-account?source=docs#set-calendar-auto-processing)。

## 使用 PowerShell 建立帳戶

您可以使用 PowerShell 建立帳戶，而不是使用 Microsoft 系統管理中心入口網站。

### 連線至 Exchange Online PowerShell

```powershell
$365Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://ps.outlook.com/powershell -Credential (Get-Credential) -Authentication Basic –AllowRedirection
$ImportResults = Import-PSSession $365Session
```

### 建立新的會議室信箱

```powershell
New-Mailbox -MicrosoftOnlineServicesID account@YourDomain.com -Alias SurfaceHub2S -Name SurfaceHub2S -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString  -String "<Enter Strong Password>" -AsPlainText -Force)
```

### 設定行事曆自動處理

```powershell
Set-CalendarProcessing -Identity "account@YourDomain.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

### 指派授權

```powershell
Connect-MsolService
Set-Msoluser -UserPrincipalName account@YourDomain.com -UsageLocation IE
Set-MsolUserLicense -UserPrincipalName "account@YourDomain.com" -AddLicenses "contoso:MEETING_ROOM"
```

## 使用 PowerShell 連線到商務用 Skype Online

### 安裝預備元件

- [Visual c + + 2017 可轉散發元件](https://aka.ms/vs/15/release/vc_redist.x64.exe)
- [商務用 Skype Online PowerShell 模組](https://www.microsoft.com/download/confirmation.aspx?id=39366)

```powershell
Import-Module LyncOnlineConnector
$SfBSession = New-CsOnlineSession -Credential (Get-Credential)
Import-PSSession $SfBSession -AllowClobber

# Enable the Skype for Business meeting room
Enable-CsMeetingRoom -Identity account@YourDomain.com -RegistrarPool(Get-CsTenant).Registrarpool -SipAddressType EmailAddress
```
