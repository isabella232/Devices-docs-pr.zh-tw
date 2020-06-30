---
title: 使用 PowerShell 設定 Surface Hub 2 內部部署帳戶
description: 瞭解如何使用 PowerShell 設定 Surface Hub 2 內部部署帳戶
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
ms.openlocfilehash: 6832f4e4b5bc307746ec5838c0f80d043a22021a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832049"
---
# <span data-ttu-id="05f4a-104">使用 PowerShell 設定 Surface Hub 2 內部部署帳戶</span><span class="sxs-lookup"><span data-stu-id="05f4a-104">Configure Surface Hub 2S on-premises accounts with PowerShell</span></span>

## <span data-ttu-id="05f4a-105">連線到 Exchange Server PowerShell</span><span class="sxs-lookup"><span data-stu-id="05f4a-105">Connect to Exchange Server PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05f4a-106">您將需要內部部署 Exchange server 的用戶端存取服務的完整功能變數名稱（FQDN），才能取得這些 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="05f4a-106">You'll need the Fully Qualified Domain Name (FQDN) for the Client Access service of the on-premises Exchange server for some of these cmdlets.</span></span>

```PowerShell
$ExchServer = Read-Host "Please Enter the FQDN of your Exchange Server"
$ExchSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri http://$ExchServer/PowerShell/ -Authentication Kerberos -Credential (Get-Credential)
Import-PSSession $ExchSession
```

## <span data-ttu-id="05f4a-107">建立裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="05f4a-107">Create the device account</span></span>

```PowerShell
New-Mailbox -UserPrincipalName Hub01@contoso.com -Alias Hub01 -Name "Hub 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

## <span data-ttu-id="05f4a-108">設定自動行事曆處理</span><span class="sxs-lookup"><span data-stu-id="05f4a-108">Set automatic calendar processing</span></span>

```PowerShell
Set-CalendarProcessing -Identity "HUB01@contoso.com" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This room is equipped with a Surface Hub"
```

## <span data-ttu-id="05f4a-109">啟用商務用 Skype 物件</span><span class="sxs-lookup"><span data-stu-id="05f4a-109">Enable the Skype for Business object</span></span>

> [!NOTE]
> <span data-ttu-id="05f4a-110">您必須知道商務用 Skype 註冊機構的 FQDN，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="05f4a-110">It is important that you know the FQDN of the Skype for Business Registrar Pool.</span></span>

```PowerShell
Enable-CsMeetingRoom -Identity Contoso\HUB01 -SipAddressType emailaddress -RegistrarPool SfbIEFE01.contoso.local
```

## <span data-ttu-id="05f4a-111">行動裝置信箱原則</span><span class="sxs-lookup"><span data-stu-id="05f4a-111">Mobile Device Mailbox Policy</span></span>

<span data-ttu-id="05f4a-112">您可能需要建立行動裝置信箱原則（也稱為 ActiveSync 原則），以允許 Surface Hub 連線到您的線上或內部部署環境。</span><span class="sxs-lookup"><span data-stu-id="05f4a-112">You may need to create a Mobile Device Mailbox Policy (also known as ActiveSync Policy) to allow your Surface Hub to connect to your online or on-premises environment.</span></span>

## <span data-ttu-id="05f4a-113">建立 Surface Hub 行動裝置信箱原則</span><span class="sxs-lookup"><span data-stu-id="05f4a-113">Create a Surface Hub mobile device mailbox policy</span></span>

```PowerShell
New-MobileDeviceMailboxPolicy -Name “Surface Hubs” -PasswordEnabled $false
```

## <span data-ttu-id="05f4a-114">其他設定</span><span class="sxs-lookup"><span data-stu-id="05f4a-114">Additional settings</span></span>

<span data-ttu-id="05f4a-115">建議您將寄件提醒新增至 Surface Hub 會議室，讓使用者記得讓會議召開商務用 Skype 或團隊會議：</span><span class="sxs-lookup"><span data-stu-id="05f4a-115">It is recommended to add a MailTip to Surface Hub rooms so users remember to make the meeting a Skype for Business or Teams meeting:</span></span>

```PowerShell
Set-Mailbox "Surface Hub 2S" -MailTip "This is a Surface Hub room. Please make sure this is a Microsoft Teams meeting."
```
