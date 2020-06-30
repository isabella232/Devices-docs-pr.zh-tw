---
title: 設定工作表 (Surface Hub)
description: 當您完成預先設定並準備好開始第一次設定 Microsoft Surface Hub 時，請確定您擁有本節列出的所有資訊。
ms.assetid: AC6F925B-BADE-48F5-8D53-8B6FFF6EE3EB
ms.reviewer: ''
manager: laurawi
keywords: 設定工作表, 預先設定, 第一次設定
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: e0c31082669336d3762fd02f46a939aa8b0ff1bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831950"
---
# <span data-ttu-id="add65-104">設定工作表 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="add65-104">Setup worksheet (Surface Hub)</span></span>


<span data-ttu-id="add65-105">當您完成預先設定並準備好開始第一次設定 Microsoft Surface Hub 時，請確定您擁有本節列出的所有資訊。</span><span class="sxs-lookup"><span data-stu-id="add65-105">When you've finished pre-setup and are ready to start first-time setup for your Microsoft Surface Hub, make sure you have all the information listed in this section.</span></span>

<span data-ttu-id="add65-106">儘管部分資訊可以用在所有的 Surface Hub 上 (例如 Proxy 資訊或網域認證)，但您還是應該針對需要設定的每個 Surface Hub 填寫一份清單。</span><span class="sxs-lookup"><span data-stu-id="add65-106">You should fill out one list for each Surface Hub you need to configure, although some information can be used on all Surface Hubs, like the proxy information or domain credentials.</span></span> <span data-ttu-id="add65-107">根據您決定設定裝置的方式而定，或根據為組織基礎結構設定環境的方式而定，這其中的某些資訊可能是不需要的。</span><span class="sxs-lookup"><span data-stu-id="add65-107">Some of this information may not be needed, depending on how you've decided to configure your device, or depending on how the environment is configured for your organization's infrastructure.</span></span>

<table>
<tr>
<th><span data-ttu-id="add65-108">屬性</span><span class="sxs-lookup"><span data-stu-id="add65-108">Property</span></span></th>
<th><span data-ttu-id="add65-109">用途</span><span class="sxs-lookup"><span data-stu-id="add65-109">What this is used for</span></span></th>
<th><span data-ttu-id="add65-110">範例</span><span class="sxs-lookup"><span data-stu-id="add65-110">Example</span></span></th>
<th><span data-ttu-id="add65-111">實際值</span><span class="sxs-lookup"><span data-stu-id="add65-111">Actual value</span></span></th>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-112">Proxy 資訊</span><span class="sxs-lookup"><span data-stu-id="add65-112">Proxy information</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-113">如果您的網路使用 Proxy 進行網路和/或網際網路存取，您就必須提供指令碼或伺服器/連接埠資訊。</span><span class="sxs-lookup"><span data-stu-id="add65-113">If your network uses a proxy for network and/or Internet access, you must provide a script or server/port information.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-114">Proxy 指令碼︰</span><span class="sxs-lookup"><span data-stu-id="add65-114">Proxy script:</span></span> <code>http://contoso/proxy.pa</code> </br>
- <span data-ttu-id="add65-115">或 -</span><span class="sxs-lookup"><span data-stu-id="add65-115">OR -</span></span> </br>
<span data-ttu-id="add65-116">伺服器與連接埠資訊︰10.10.10.100，連接埠 80</span><span class="sxs-lookup"><span data-stu-id="add65-116">Server and port info: 10.10.10.100, port 80</span></span>
</p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-117">無線網路認證 (使用者名稱與密碼)</span><span class="sxs-lookup"><span data-stu-id="add65-117">Wireless network credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-118">如果您決定將裝置連線到 Wi-Fi，而且您的無線網路需要使用者認證。</span><span class="sxs-lookup"><span data-stu-id="add65-118">If you decide to connect your device to Wi-Fi, and your wireless network requires user credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-119">admin1@contoso.com, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="add65-119">admin1@contoso.com, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-120">裝置帳戶 UPN 或網域\使用者名稱與裝置帳戶密碼</span><span class="sxs-lookup"><span data-stu-id="add65-120">Device account UPN or Domain\username and device account password</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-121">這是使用者主體名稱 (UPN) 或網域\使用者名稱，以及裝置帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="add65-121">This is the User Principal Name (UPN) or the domain\username, and the password of the device account.</span></span> <span data-ttu-id="add65-122">電子郵件、行事曆和商務用 Skype 取決於相容的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="add65-122">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span></p>
</td>
<td>
<p> <span data-ttu-id="add65-123">UPN：ConfRoom15@contoso.com，#Passw0rd1</span><span class="sxs-lookup"><span data-stu-id="add65-123">UPN: ConfRoom15@contoso.com, #Passw0rd1</span></span> </br>
- <span data-ttu-id="add65-124">或 -</span><span class="sxs-lookup"><span data-stu-id="add65-124">OR -</span></span> <br> 
<span data-ttu-id="add65-125">網域和使用者名稱︰CONTOSO\ConfRoom15，#Passw0rd1</span><span class="sxs-lookup"><span data-stu-id="add65-125">Domain and username: CONTOSO\ConfRoom15, #Passw0rd1</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-126">裝置帳戶 Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="add65-126">Device account Microsoft Exchange server</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-127">此為裝置帳戶的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="add65-127">This is the device account's Exchange server.</span></span>
<span data-ttu-id="add65-128">電子郵件、行事曆和商務用 Skype 取決於相容的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="add65-128">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span>
<span data-ttu-id="add65-129">若要讓電子郵件和行事曆能夠運作，裝置帳戶必須具備有效的 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="add65-129">For mail and calendar to work, the device account must have a valid Exchange server.</span></span> <span data-ttu-id="add65-130">裝置會試著自動尋找此伺服器。</span><span class="sxs-lookup"><span data-stu-id="add65-130">The device will try to find this automatically.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-131">outlook.office365.com</span><span class="sxs-lookup"><span data-stu-id="add65-131">outlook.office365.com</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-132">裝置帳戶工作階段初始通訊協定 (SIP) 位址</span><span class="sxs-lookup"><span data-stu-id="add65-132">Device account Session Initiation Protocol (SIP) address</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-133">此為裝置帳戶的商務用 Skype SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="add65-133">This is the device account's Skype for Business SIP address.</span></span>
<span data-ttu-id="add65-134">電子郵件、行事曆和商務用 Skype 取決於相容的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="add65-134">Mail, calendar, and Skype for Business depend on a compatible device account.</span></span>
<span data-ttu-id="add65-135">若要讓商務用 Skype 能夠運作，裝置帳戶必須具備有效的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="add65-135">For Skype for Business to work, the device account must have a valid SIP address.</span></span> <span data-ttu-id="add65-136">裝置會試著自動尋找此伺服器。</span><span class="sxs-lookup"><span data-stu-id="add65-136">The device will try to find this automatically.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-137">sip：ConfRoom15@contoso.com</span><span class="sxs-lookup"><span data-stu-id="add65-137">sip: ConfRoom15@contoso.com</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-138">易記名稱</span><span class="sxs-lookup"><span data-stu-id="add65-138">Friendly name</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-139">裝置的易記名稱是使用者嘗試以無線方式連線到 Surface Hub 時所看見的廣播名稱。</span><span class="sxs-lookup"><span data-stu-id="add65-139">The friendly name of the device is the broadcast name that people will see when they try to wirelessly connect to the Surface Hub.</span></span> <span data-ttu-id="add65-140">這個名稱將顯示於 Surface Hub 畫面的顯著位置上。</span><span class="sxs-lookup"><span data-stu-id="add65-140">This name will be displayed prominently on the Surface Hub's screen.</span></span>
<span data-ttu-id="add65-141">我們建議您選擇可辨識且唯一的易記名稱，讓使用者在嘗試連線時可以從多個 Surface Hub 中區別出某一個 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="add65-141">We suggest that the friendly name you choose is recognizable and unique so that people can distinguish one Surface Hub from another when trying to connect.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-142">Conference Room 15</span><span class="sxs-lookup"><span data-stu-id="add65-142">Conference Room 15</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-143">裝置名稱</span><span class="sxs-lookup"><span data-stu-id="add65-143">Device name</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-144">裝置名稱是用於加入網域的名稱，以及如果已將裝置註冊到 MDM，您將會在 MDM 提供者中看見的身分識別</span><span class="sxs-lookup"><span data-stu-id="add65-144">The device name is the name that will be used for domain join, and is the identity you will see in your MDM provider if the device is enrolled into MDM.</span></span>
<span data-ttu-id="add65-145">您選擇的裝置名稱不得與使用者的 Active Directory 網域中的任何其他裝置相同 (如果您決定將裝置加入網域)。</span><span class="sxs-lookup"><span data-stu-id="add65-145">The device name you choose must not be the same name as any other device on the user’s Active Directory domain (if you decide to domain join the device).</span></span> <span data-ttu-id="add65-146">如果裝置名稱不是唯一的，就不能加入網域。</span><span class="sxs-lookup"><span data-stu-id="add65-146">The device cannot join the domain if its name is not unique.</span></span>
</p>
</td>
<td>
<p><span data-ttu-id="add65-147">confroom15</span><span class="sxs-lookup"><span data-stu-id="add65-147">confroom15</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="add65-148">如果您正在加入 AZURE AD</span><span class="sxs-lookup"><span data-stu-id="add65-148">IF YOU'RE JOINING AZURE AD</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-149">Azure AD 租用戶使用者認證 (使用者名稱與密碼)</span><span class="sxs-lookup"><span data-stu-id="add65-149">Azure AD tenant user credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-150">如果您決定要讓 Azure Active Directory (Azure AD) 組織中的使用者成為裝置上的系統管理員，則您需要加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="add65-150">If you decide to have people in your Azure Active Directory (Azure AD) organization become admins on the device, then you'll need to join Azure AD.</span></span>
<span data-ttu-id="add65-151">若要加入 Azure AD，您需要有效的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="add65-151">To join Azure AD, you will need valid user credentials.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-152">admin1@contoso.com, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="add65-152">admin1@contoso.com, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="add65-153">如果您正在加入網域</span><span class="sxs-lookup"><span data-stu-id="add65-153">IF YOU'RE JOINING A DOMAIN</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-154">要加入的網域</span><span class="sxs-lookup"><span data-stu-id="add65-154">Domain to join</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-155">這是您需要加入的網域，讓您選擇的安全性群組可做為裝置的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="add65-155">This is the domain you will need to join so that a security group of your choice can be admins for the device.</span></span>
<span data-ttu-id="add65-156">您需要完整網域名稱 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="add65-156">You may need the fully qualified domain name (FQDN).</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-157">contoso (簡短名稱) 或 contoso.corp.com (FQDN)</span><span class="sxs-lookup"><span data-stu-id="add65-157">contoso (short name) OR contoso.corp.com (FQDN)</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-158">網域帳戶認證 (使用者名稱與密碼)</span><span class="sxs-lookup"><span data-stu-id="add65-158">Domain account credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-159">除非您提供足夠的帳戶認證來加入網域，否則無法加入網域。</span><span class="sxs-lookup"><span data-stu-id="add65-159">A domain can't be joined unless you provide sufficient account credentials to join the domain.</span></span> <span data-ttu-id="add65-160">當您提供要加入的網域和要加入網域的認證之後，您選擇的安全性群組接著就會變更裝置上的設定。</span><span class="sxs-lookup"><span data-stu-id="add65-160">Once you provide a domain to join and credentials to join the domain, then a security group of your choice can change settings on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-161">admin1, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="add65-161">admin1, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-162">系統管理員安全性群組別名</span><span class="sxs-lookup"><span data-stu-id="add65-162">Admin security group alias</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-163">這是 Active Directory (AD) 中的安全性群組；這個安全性群組的所有成員都能變更裝置上的設定。</span><span class="sxs-lookup"><span data-stu-id="add65-163">This is a security group in your Active Directory (AD); any members of this security group can change settings on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-164">SurfaceHubAdmins</span><span class="sxs-lookup"><span data-stu-id="add65-164">SurfaceHubAdmins</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="add65-165">如果您使用本機系統管理員</span><span class="sxs-lookup"><span data-stu-id="add65-165">IF YOU'RE USING A LOCAL ADMIN</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-166">本機系統管理員帳戶認證 (使用者名稱與密碼)</span><span class="sxs-lookup"><span data-stu-id="add65-166">Local admin account credentials (username and password)</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-167">如果您決定不加入 AD 網域或 Azure AD，您可以在裝置上建立本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="add65-167">If you decide not to join an AD domain or Azure AD, you can create a local admin account on the device.</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-168">admin1, #MyPassw0rd</span><span class="sxs-lookup"><span data-stu-id="add65-168">admin1, #MyPassw0rd</span></span></p>
</td>
<td>
<p></p>
</td>
</tr>
<tr>
<td colspan="4">
<p><b><span data-ttu-id="add65-169">如果您需要安裝憑證或應用程式</span><span class="sxs-lookup"><span data-stu-id="add65-169">IF YOU NEED TO INSTALL CERTIFICATES OR APPS</span></span></b></p>
</td>
</tr>
<tr>
<td>
<p><span data-ttu-id="add65-170">USB 磁碟機</span><span class="sxs-lookup"><span data-stu-id="add65-170">USB drive</span></span></p>
</td>
<td>
<p><span data-ttu-id="add65-171">如果您在初次執行之前知道您想要安裝憑證或跨平台應用程式，請依照<a href="provisioning-packages-for-certificates-surface-hub.md">建立佈建套件</a>中的步驟執行。</span><span class="sxs-lookup"><span data-stu-id="add65-171">If you know before first run that you want to install certificates or universal apps, follow the steps in <a href="provisioning-packages-for-certificates-surface-hub.md">Create provisioning packages</a>.</span></span> <span data-ttu-id="add65-172">您的佈建套件將建立於 USB 磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="add65-172">Your provisioning packages will be created on a USB drive.</span></span></p>
</td>
<td>
<p></p>
</td>
<td>
<p></p>
</td>
</tr>
</table> 





