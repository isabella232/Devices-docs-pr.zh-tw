---
title: 搭配 Surface Hub 使用完整網域名稱
description: 對常見問題進行疑難排解，包括設定問題、Exchange ActiveSync 錯誤。
keywords:
- 疑難排解常見問題
- 設定問題
- Exchange ActiveSync 錯誤
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.prod: surface-hub
ms.sitesec: library
ms.openlocfilehash: 79507f5b4bb22b23d1e6c4db6b4aab6ea891d876
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831337"
---
# <span data-ttu-id="b0b40-106">為商務用 Skype 設定網域名稱</span><span class="sxs-lookup"><span data-stu-id="b0b40-106">Configure domain name for Skype for Business</span></span>

<span data-ttu-id="b0b40-107">在幾個情況下您需要指定商務用 Skype 伺服器的網域名稱：</span><span class="sxs-lookup"><span data-stu-id="b0b40-107">There are a few scenarios where you need to specify the domain name of your Skype for Business server:</span></span>
- <span data-ttu-id="b0b40-108">**多重 DNS 尾碼**：您的商務用 Skype 基礎結構的命名空間不接續，造成有一或多個伺服器的 DNS 尾碼與商務用 Skype 登入位址 (SIP) 的 DNS 尾碼不相符。</span><span class="sxs-lookup"><span data-stu-id="b0b40-108">**Multiple DNS suffixes** - When your Skype for Business infrastructure has disjointed namespaces such that one or more servers have a DNS suffix that doesn't match the suffix of the sign-in address (SIP) for Skype for Business.</span></span>  
- <span data-ttu-id="b0b40-109">**商務用 Skype 與 Exchange 尾碼不同**：商務用 Skype 的登入位址尾碼，與用於裝置帳戶的 Exchange 位址尾碼不同。</span><span class="sxs-lookup"><span data-stu-id="b0b40-109">**Skype for Business and Exchange suffixes are different** - When the suffix of the sign-in address for Skype for Business differs from the suffix of the Exchange address used for the device account.</span></span>
- <span data-ttu-id="b0b40-110">使用**證書**-大型組織與內部部署商務用 Skype 伺服器通常會使用憑證與自己的根憑證授權單位（CA）。</span><span class="sxs-lookup"><span data-stu-id="b0b40-110">**Working with certificates** - Large organizations with on-premises Skype for Business servers commonly use certificates with their own root certificate authority (CA).</span></span> <span data-ttu-id="b0b40-111">CA 網域通常會和商務用 Skype 伺服器的網域不同，這會造成憑證無法信任，進而使登入失敗。</span><span class="sxs-lookup"><span data-stu-id="b0b40-111">It is common for the CA domain to be different than the domain of the Skype for Business server which causes the certificate to not be trusted, and sign-in fails.</span></span>  <span data-ttu-id="b0b40-112">Skype 必須知道憑證的網域名稱才能設定信任關係。</span><span class="sxs-lookup"><span data-stu-id="b0b40-112">Skype needs to know the domain name of the certificate in order to set up a trust relationship.</span></span> <span data-ttu-id="b0b40-113">企業通常會使用群組原則將此資訊推送到電腦版 Skype，但 Surface Hub 上並不支援群組原則。</span><span class="sxs-lookup"><span data-stu-id="b0b40-113">Enterprises typically use Group Policy to push this out to Skype desktop, but Group Policy is not supported on Surface Hub.</span></span>

**<span data-ttu-id="b0b40-114">若要為您的商務用 Skype 伺服器設定網域名稱</span><span class="sxs-lookup"><span data-stu-id="b0b40-114">To configure the domain name for your Skype for Business server</span></span>**</br>
1. <span data-ttu-id="b0b40-115">在 Surface Hub 上，開啟 **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="b0b40-115">On Surface Hub, open **Settings**.</span></span>
2. <span data-ttu-id="b0b40-116">按一下 **[Surface Hub]**，然後按一下 **[通話和音訊]**。</span><span class="sxs-lookup"><span data-stu-id="b0b40-116">Click **Surface Hub**, and then click **Calling & Audio**.</span></span> 
3. <span data-ttu-id="b0b40-117">在 **[商務用 Skype 設定]** 底下，按一下 **[設定網域名稱]**。</span><span class="sxs-lookup"><span data-stu-id="b0b40-117">Under **Skype for Business configuration**, click **Configure domain name**.</span></span> 
4. <span data-ttu-id="b0b40-118">為您的商務用 Skype 伺服器輸入網域名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b0b40-118">Type the domain name for your Skype for Business server, and then click **Ok**.</span></span> 
   > [!TIP]
   > <span data-ttu-id="b0b40-119">您可以輸入多個網域名稱 (使用逗號分隔)。</span><span class="sxs-lookup"><span data-stu-id="b0b40-119">You can type multiple domain names, separated by commas.</span></span> <br> <span data-ttu-id="b0b40-120">例如：lync.com, outlook.com, lync.glbdns.microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="b0b40-120">For example: lync.com, outlook.com, lync.glbdns.microsoft.com</span></span>

    ![將商務用 Skype FQDN 新增至 [設定]](images/system-settings-add-fqdn.png)
