---
title: 建立和測試裝置帳戶 (Surface Hub)
description: 本主題介紹如何建立和測試 Microsoft Surface Hub 用來與 Microsoft Exchange 和 Skype 通訊的裝置帳戶。
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: 建立和測試裝置帳戶, 裝置帳戶, Surface Hub 與 Microsoft Exchange, Surface Hub 與 Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831897"
---
# <span data-ttu-id="48c07-104">建立和測試裝置帳戶 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="48c07-104">Create and test a device account (Surface Hub)</span></span>


<span data-ttu-id="48c07-105">本主題介紹如何建立和測試 Microsoft Surface Hub 用來與 Microsoft Exchange 和 Skype 通訊的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="48c07-105">This topic introduces how to create and test the device account that Microsoft Surface Hub uses to communicate with Microsoft Exchange and Skype.</span></span>

<span data-ttu-id="48c07-106">**「裝置帳戶」** 是 Surface Hub 用來執行下列動作的 Exchange 資源帳戶：</span><span class="sxs-lookup"><span data-stu-id="48c07-106">A **device account** is an Exchange resource account that Surface Hub uses to:</span></span>

-   <span data-ttu-id="48c07-107">顯示會議行事曆</span><span class="sxs-lookup"><span data-stu-id="48c07-107">Display its meeting calendar</span></span>
-   <span data-ttu-id="48c07-108">加入小組或商務用 Skype 通話</span><span class="sxs-lookup"><span data-stu-id="48c07-108">Join Teams or Skype for Business calls</span></span>
-   <span data-ttu-id="48c07-109">傳送電子郵件 (例如以電子郵件寄送會議的白板內容)</span><span class="sxs-lookup"><span data-stu-id="48c07-109">Send email (for example, email whiteboard content from a meeting)</span></span>

<span data-ttu-id="48c07-110">當裝置帳戶已佈建到 Surface Hub 之後，人員便可以利用和邀請會議室相同的方式，將此帳戶新增到會議邀請。</span><span class="sxs-lookup"><span data-stu-id="48c07-110">Once the device account is provisioned to a Surface Hub, people can add this account to a meeting invitation the same way that they would invite a meeting room.</span></span> 

## <span data-ttu-id="48c07-111">設定概觀</span><span class="sxs-lookup"><span data-stu-id="48c07-111">Configuration overview</span></span>

<span data-ttu-id="48c07-112">下表說明建立裝置帳戶的主要步驟和設定決策。</span><span class="sxs-lookup"><span data-stu-id="48c07-112">This table explains the main steps and configuration decisions when you create a device account.</span></span> 
 
| <span data-ttu-id="48c07-113">步驟</span><span class="sxs-lookup"><span data-stu-id="48c07-113">Step</span></span> | <span data-ttu-id="48c07-114">說明</span><span class="sxs-lookup"><span data-stu-id="48c07-114">Description</span></span>                     |  <span data-ttu-id="48c07-115">用途</span><span class="sxs-lookup"><span data-stu-id="48c07-115">Purpose</span></span>                             |
|------|---------------------------------|--------------------------------------|
| <span data-ttu-id="48c07-116">sr-1</span><span class="sxs-lookup"><span data-stu-id="48c07-116">1</span></span>    | <span data-ttu-id="48c07-117">建立已啟用登入功能的 Exchange 資源信箱 (Exchange 2013 或更新版本，或是 Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="48c07-117">Created a logon-enabled Exchange resource mailbox (Exchange 2013 or later, or Exchange Online)</span></span> | <span data-ttu-id="48c07-118">此資源信箱允許裝置維護會議行事曆、接收會議要求，以及傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="48c07-118">This resource mailbox allows the device to maintain a meeting calendar, receive meeting requests, and send mail.</span></span> <span data-ttu-id="48c07-119">它必須已啟用登入功能以佈建到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="48c07-119">It must be logon-enabled to be provisioned to a Surface Hub.</span></span> |
| <span data-ttu-id="48c07-120">pplx-2</span><span class="sxs-lookup"><span data-stu-id="48c07-120">2</span></span>    | <span data-ttu-id="48c07-121">設定信箱屬性</span><span class="sxs-lookup"><span data-stu-id="48c07-121">Configure mailbox properties</span></span> | <span data-ttu-id="48c07-122">信箱必須設定為正確屬性，以在 Surface Hub 上提供最佳的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="48c07-122">The mailbox must be configured with the correct properties to enable the best meeting experience on Surface Hub.</span></span> <span data-ttu-id="48c07-123">如需信箱屬性的詳細資訊，請參閱[信箱屬性](exchange-properties-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="48c07-123">For more information on mailbox properties, see [Mailbox properties](exchange-properties-for-surface-hub-device-accounts.md).</span></span> |
| <span data-ttu-id="48c07-124">3</span><span class="sxs-lookup"><span data-stu-id="48c07-124">3</span></span>    | <span data-ttu-id="48c07-125">將相容的行動裝置信箱原則套用到信箱</span><span class="sxs-lookup"><span data-stu-id="48c07-125">Apply a compatible mobile device mailbox policy to the mailbox</span></span> | <span data-ttu-id="48c07-126">Surface Hub 是使用行動裝置管理 (MDM) 來管理，而不是透過行動裝置信箱原則。</span><span class="sxs-lookup"><span data-stu-id="48c07-126">Surface Hub is managed using mobile device management (MDM) rather than through mobile device mailbox policies.</span></span> <span data-ttu-id="48c07-127">為了相容性，裝置帳戶必須具有已將 **PasswordEnabled** 設定設為 False 的行動裝置信箱原則。</span><span class="sxs-lookup"><span data-stu-id="48c07-127">For compatibility, the device account must have a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="48c07-128">否則，Surface Hub 將無法同步處理郵件和行事曆資訊。</span><span class="sxs-lookup"><span data-stu-id="48c07-128">Otherwise, Surface Hub can't sync mail and calendar info.</span></span> |
| <span data-ttu-id="48c07-129">4</span><span class="sxs-lookup"><span data-stu-id="48c07-129">4</span></span>    | <span data-ttu-id="48c07-130">為信箱啟用商務用 Skype (Lync Server 2013 或更新版本，或商務用 Skype Online)</span><span class="sxs-lookup"><span data-stu-id="48c07-130">Enable mailbox with Skype for Business (Lync Server 2013 or later, or Skype for Business Online)</span></span> | <span data-ttu-id="48c07-131">必須啟用商務用 Skype，才能使用各種不同的會議功能，例如，視訊通話、IM 和螢幕畫面分享。</span><span class="sxs-lookup"><span data-stu-id="48c07-131">Skype for Business must be enabled to use conferencing features like video calls, IM, and screen sharing.</span></span>  |
| <span data-ttu-id="48c07-132">500</span><span class="sxs-lookup"><span data-stu-id="48c07-132">5</span></span>    | <span data-ttu-id="48c07-133">(選擇性) 將 ActiveSync 裝置 ID 納入允許清單</span><span class="sxs-lookup"><span data-stu-id="48c07-133">(Optional) Whitelist ActiveSync Device ID</span></span> | <span data-ttu-id="48c07-134">您的組織可能有一個全域原則，以防止裝置帳戶同步處理郵件和行事曆資訊。</span><span class="sxs-lookup"><span data-stu-id="48c07-134">Your organization may have a global policy that prevents device accounts from syncing mail and calendar info.</span></span> <span data-ttu-id="48c07-135">如果是，您必須允許您 Surface Hub 的 ActiveSync 裝置識別碼。</span><span class="sxs-lookup"><span data-stu-id="48c07-135">If so, you need to allow the ActiveSync Device ID of your Surface Hub.</span></span> |
| <span data-ttu-id="48c07-136">6</span><span class="sxs-lookup"><span data-stu-id="48c07-136">6</span></span>    | <span data-ttu-id="48c07-137">(選擇性) 停用密碼到期</span><span class="sxs-lookup"><span data-stu-id="48c07-137">(Optional) Disable password expiration</span></span> | <span data-ttu-id="48c07-138">為了簡化管理作業，您可以將裝置帳戶的密碼到期關閉，並允許 Surface Hub 自動循環裝置帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="48c07-138">To simplify management, you can turn off password expiration for the device account and allow Surface Hub to automatically rotate the device account password.</span></span> <span data-ttu-id="48c07-139">如需密碼管理的詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="48c07-139">For more information about password management, see [Password management](password-management-for-surface-hub-device-accounts.md).</span></span>  |

## <span data-ttu-id="48c07-140">詳細設定步驟</span><span class="sxs-lookup"><span data-stu-id="48c07-140">Detailed configuration steps</span></span> 

<span data-ttu-id="48c07-141">建議您使用遠端 PowerShell 來設定裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="48c07-141">We recommend setting up your device accounts using remote PowerShell.</span></span> <span data-ttu-id="48c07-142">有可協助建立並驗證裝置帳戶的 PowerShell 指令碼可供使用。如需 PowerShell 指令碼和指示的詳細資訊，請參閱[附錄 A：PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="48c07-142">There are PowerShell scripts available to help create and validate device accounts For more information on PowerShell scripts and instructions, see [Appendix A: PowerShell](appendix-a-powershell-scripts-for-surface-hub.md).</span></span> 

<span data-ttu-id="48c07-143">如需使用 PowerShell 佈建裝置帳戶的詳細步驟，請根據您的組織部署選擇表格中的選項。</span><span class="sxs-lookup"><span data-stu-id="48c07-143">For detailed steps using PowerShell to provision a device account, choose an option from the table, based on your organization deployment.</span></span> 

| <span data-ttu-id="48c07-144">組織部署</span><span class="sxs-lookup"><span data-stu-id="48c07-144">Organization deployment</span></span>             |  <span data-ttu-id="48c07-145">說明</span><span class="sxs-lookup"><span data-stu-id="48c07-145">Description</span></span>                  |
|---------------------------------|--------------------------------------|
| [<span data-ttu-id="48c07-146">線上部署 (Office 365)</span><span class="sxs-lookup"><span data-stu-id="48c07-146">Online deployment (Office 365)</span></span>](online-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="48c07-147">您組織的環境完全部署在 Office 365 上。</span><span class="sxs-lookup"><span data-stu-id="48c07-147">Your organization's environment is deployed entirely on Office 365.</span></span> |
| [<span data-ttu-id="48c07-148">內部部署 (單一樹系)</span><span class="sxs-lookup"><span data-stu-id="48c07-148">On-premises deployment (single-forest)</span></span>](on-premises-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="48c07-149">您的組織擁有其所控制的伺服器，並在單一樹系環境將它用來裝載 Active Directory、Exchange 及商務用 Skype (或 Lync)。</span><span class="sxs-lookup"><span data-stu-id="48c07-149">Your organization has servers that it controls and uses to host Active Directory, Exchange, and Skype for Business (or Lync) in a single-forest environment.</span></span> |
| [<span data-ttu-id="48c07-150">內部部署 (多重樹系)</span><span class="sxs-lookup"><span data-stu-id="48c07-150">On-premises deployment (multiple forests)</span></span>](on-premises-deployment-surface-hub-multi-forest.md) | <span data-ttu-id="48c07-151">您的組織擁有其所控制的伺服器，並在多重樹系環境將它用來裝載 Active Directory、Exchange 及商務用 Skype (或 Lync)。</span><span class="sxs-lookup"><span data-stu-id="48c07-151">Your organization has servers that it controls and uses to host Active Directory, Exchange, and Skype for Business (or Lync) in a multi-forest environment.</span></span> |
| [<span data-ttu-id="48c07-152">混合式部署</span><span class="sxs-lookup"><span data-stu-id="48c07-152">Hybrid deployment</span></span>](hybrid-deployment-surface-hub-device-accounts.md) | <span data-ttu-id="48c07-153">您的組織擁有混合的服務，其中部分是透過內部部署裝載，部分是透過 Office 365 線上裝載。</span><span class="sxs-lookup"><span data-stu-id="48c07-153">Your organization has a mix of services, with some hosted on-premises and some hosted online through Office 365.</span></span> |
| [<span data-ttu-id="48c07-154">線上或混合式部署，使用 Skype 混合語音環境</span><span class="sxs-lookup"><span data-stu-id="48c07-154">Online or hybrid deployment using Skype Hybrid Voice environment</span></span>](skype-hybrid-voice.md) | <span data-ttu-id="48c07-155">您的組織在雲端中有商務用 Skype 主集區與 Exchange 伺服器，並使用透過公用交換電話網路 (PSTN) 連線的商務用 Skype 2015 或 Cloud Connector 版的內部部署集區。</span><span class="sxs-lookup"><span data-stu-id="48c07-155">Your organization has Skype for Business home pools and Exchange servers in the cloud, and uses an on-premises pool of Skype for Business 2015 or Cloud Connector edition connected via Public Switched Telephone Network (PSTN).</span></span> |


<span data-ttu-id="48c07-156">如果您想要使用圖形化的使用者介面 (UI)，一部分的步驟可以不使用 PowerShell，而改為使用 UI 來完成。</span><span class="sxs-lookup"><span data-stu-id="48c07-156">If you prefer to use a graphical user interface (UI), some steps can be done using UI instead of PowerShell.</span></span> <span data-ttu-id="48c07-157">如需詳細資訊，請參閱[使用 UI 建立裝置帳戶](create-a-device-account-using-office-365.md)。</span><span class="sxs-lookup"><span data-stu-id="48c07-157">For more information, see [Creating a device account using UI](create-a-device-account-using-office-365.md).</span></span>

## <span data-ttu-id="48c07-158">帳戶驗證與測試</span><span class="sxs-lookup"><span data-stu-id="48c07-158">Account verification and testing</span></span>

<span data-ttu-id="48c07-159">有兩種可用方法，您可以用來驗證和測試 Surface Hub 裝置帳戶：[帳戶驗證指令碼](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)和 [Surface Hub 硬體診斷應用程式](https://www.microsoft.com/store/apps/9nblggh51f2g)。</span><span class="sxs-lookup"><span data-stu-id="48c07-159">There are two methods available that you can use to validate and test a Surface Hub device account: [account verifications scripts](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts) and the [Surface Hub Hardware Diagnostic app](https://www.microsoft.com/store/apps/9nblggh51f2g).</span></span> <span data-ttu-id="48c07-160">帳戶驗證指令碼將會從桌面使用 PowerShell 來驗證先前建立的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="48c07-160">The account verification script will validate a previously-created device account using PowerShell from your desktop.</span></span> <span data-ttu-id="48c07-161">Surface Hub 硬體診斷應用程式已安裝在 Surface Hub 上，並且會提供有關登入及通訊失敗的詳細意見反應。</span><span class="sxs-lookup"><span data-stu-id="48c07-161">The Surface Hub Hardware Diagnostic app is installed on your Surface Hub and provides detailed feedback about signin and communication failures.</span></span> <span data-ttu-id="48c07-162">兩者都是要測試新建立裝置帳戶的實用工具，您應該用來確保最佳的帳戶可用性。</span><span class="sxs-lookup"><span data-stu-id="48c07-162">Both are valuable tools to test newly created device accounts and should be used to ensure optimal account availability.</span></span>

 

 

 





