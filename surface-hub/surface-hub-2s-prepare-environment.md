---
title: 針對 Surface Hub 2S 準備您的環境
description: 瞭解準備 Surface Hub 2S 環境所需的工作。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 2/26/2021
ms.localizationpriority: Medium
ms.openlocfilehash: caa6372820222f6f2f225f028161b3441b147a82
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385141"
---
# <a name="prepare-your-environment-for-surface-hub-2s"></a><span data-ttu-id="4de3e-104">針對 Surface Hub 2S 準備您的環境</span><span class="sxs-lookup"><span data-stu-id="4de3e-104">Prepare your environment for Surface Hub 2S</span></span>

## <a name="office-365-readiness"></a><span data-ttu-id="4de3e-105">Office 365 就緒</span><span class="sxs-lookup"><span data-stu-id="4de3e-105">Office 365 readiness</span></span>

<span data-ttu-id="4de3e-106">如果您使用 Exchange Online、商務用 Skype Online、Microsoft Teams 或 Microsoft Whiteboard，並打算使用 Intune 管理 Surface Hub 2S，請先審查 [端點的 Office 365 需求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="4de3e-106">If you use Exchange Online, Skype for Business Online, Microsoft Teams, or Microsoft Whiteboard, and intend to manage Surface Hub 2S with Intune, first review the [Office 365 requirements for endpoints](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).</span></span>

<span data-ttu-id="4de3e-107">Office 365 端點可透過防火牆直接傳送所有信任的 Office 365 網路要求，並避開所有其他封包層級的檢查或處理，協助優化您的網路。</span><span class="sxs-lookup"><span data-stu-id="4de3e-107">Office 365 endpoints help optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet-level inspection or processing.</span></span> <span data-ttu-id="4de3e-108">這項功能可減少延遲和您的周邊容量需求。</span><span class="sxs-lookup"><span data-stu-id="4de3e-108">This feature reduces latency and your perimeter capacity requirements.</span></span>

<span data-ttu-id="4de3e-109">Microsoft 會以新功能定期更新 Office 365 服務，可能會變更必要的埠、URL 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="4de3e-109">Microsoft regularly updates the Office 365 service with new features and functionality, which may alter required ports, URLs, and IP addresses.</span></span> <span data-ttu-id="4de3e-110">若要評估、設定及隨時更新變更，請訂閱 [Office 365 IP 位址和 URL Web 服務](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。</span><span class="sxs-lookup"><span data-stu-id="4de3e-110">To evaluate, configure, and stay up to date with changes, subscribe to the [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

> [!NOTE]
> <span data-ttu-id="4de3e-111">Surface Hub 可與 Microsoft Teams、商務用 Skype Server 2019、商務用 Skype Server 2015 或商務用 Skype Online 合作。</span><span class="sxs-lookup"><span data-stu-id="4de3e-111">Surface Hub works with Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015, or Skype for Business Online.</span></span>
<span data-ttu-id="4de3e-112">不支援較早的平臺，例如 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="4de3e-112">Earlier platforms, such as Lync Server 2013, are not supported.</span></span> <span data-ttu-id="4de3e-113">Surface Hub 不支援GCC-High DoD 環境。</span><span class="sxs-lookup"><span data-stu-id="4de3e-113">Surface Hub is not supported in GCC-High or DoD environments.</span></span>


## <a name="device-affiliation"></a><span data-ttu-id="4de3e-114">裝置關聯</span><span class="sxs-lookup"><span data-stu-id="4de3e-114">Device affiliation</span></span>

<span data-ttu-id="4de3e-115">使用裝置關聯來管理使用者存取 Surface Hub 2S 上的設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="4de3e-115">Use Device affiliation to manage user access to the Settings app on Surface Hub 2S.</span></span>
<span data-ttu-id="4de3e-116">使用在 Surface Hub 2S (上的 Windows 10 小組作業系統) ，只有獲得授權的使用者可以使用設定應用程式來調整設定。</span><span class="sxs-lookup"><span data-stu-id="4de3e-116">With the Windows 10 Team operating system (that runs on Surface Hub 2S),  only authorized users can adjust settings using the Settings app.</span></span> <span data-ttu-id="4de3e-117">由於選擇關聯可能會影響功能可用性，請妥善規劃以確保使用者可以如預期存取功能。</span><span class="sxs-lookup"><span data-stu-id="4de3e-117">Since choosing the affiliation can impact feature availability, plan appropriately to ensure that users can access features as intended.</span></span>

> [!NOTE]
> <span data-ttu-id="4de3e-118">在設定 OOBE 時，您 (裝置) 關聯。</span><span class="sxs-lookup"><span data-stu-id="4de3e-118">You can only set Device affiliation during the initial out-of-box experience (OOBE) setup.</span></span> <span data-ttu-id="4de3e-119">如果您需要重設裝置關聯，您必須重複 OOBE 設定。</span><span class="sxs-lookup"><span data-stu-id="4de3e-119">If you need to reset Device affiliation, you’ll have to repeat OOBE setup.</span></span>

## <a name="no-affiliation"></a><span data-ttu-id="4de3e-120">無關聯</span><span class="sxs-lookup"><span data-stu-id="4de3e-120">No affiliation</span></span>

<span data-ttu-id="4de3e-121">沒有關聯性就像是將 Surface Hub 2S 放在工作組中，在每個 Surface Hub 2S 上使用不同的本地系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="4de3e-121">No affiliation is like having Surface Hub 2S in a workgroup with a different local Administrator account on each Surface Hub 2S.</span></span> <span data-ttu-id="4de3e-122">如果您選擇不關聯，您必須將 [BitLocker 金鑰](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)儲存到 USB 記憶磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4de3e-122">If you choose No affiliation, you must locally save the [BitLocker Key to a USB thumb drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq).</span></span> <span data-ttu-id="4de3e-123">您仍然可以使用 Intune 註冊裝置;不過，只有本地系統管理員可以使用 OOBE 期間設定的帳號憑證存取設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="4de3e-123">You can still enroll the device with Intune; however, only the local admin can access the Settings app using the account credentials configured during OOBE.</span></span> <span data-ttu-id="4de3e-124">您可以變更設定應用程式的系統管理員帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="4de3e-124">You can change the Administrator account password from the Settings app.</span></span>

## <a name="active-directory-domain-services"></a><span data-ttu-id="4de3e-125">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="4de3e-125">Active Directory Domain Services</span></span>

<span data-ttu-id="4de3e-126">如果您將 Surface Hub 2S 與內部部署 Active Directory 網域服務關聯，您必須使用網域上的安全性群組來管理設定應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="4de3e-126">If you affiliate Surface Hub 2S with on-premises Active Directory Domain Services, you need to manage access to the Settings app using a security group on your domain.</span></span> <span data-ttu-id="4de3e-127">這有助於確保所有安全性群組成員都有權變更 Surface Hub 2S 上的設定。</span><span class="sxs-lookup"><span data-stu-id="4de3e-127">This helps ensure that all security group members have permissions to change settings on Surface Hub 2S.</span></span> <span data-ttu-id="4de3e-128">另請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="4de3e-128">Also note the following:</span></span>

- <span data-ttu-id="4de3e-129">當您內部部署 Active Directory 網域服務的 Surface Hub 2S 關係企業時，BitLocker 金鑰可以儲存于 Active Directory 架構中。</span><span class="sxs-lookup"><span data-stu-id="4de3e-129">When Surface Hub 2S affiliates with your on-premises Active Directory Domain Services, the BitLocker key can be saved in the Active Directory Schema.</span></span> <span data-ttu-id="4de3e-130">詳細資訊請參閱為 [貴組織準備 BitLocker：規劃和政策](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="4de3e-130">For more information, see [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).</span></span>

- <span data-ttu-id="4de3e-131">貴組織的根信任 CAS 會推送到 Surface Hub 2S 中的同一個容器，這表示您不需要使用部署套件來將它們進行導入。</span><span class="sxs-lookup"><span data-stu-id="4de3e-131">Your organization’s Trusted Root CAs are pushed to the same container in Surface Hub 2S, which means you don’t need to import them using a provisioning package.</span></span>

- <span data-ttu-id="4de3e-132">您仍然可以使用 Intune 註冊裝置，以集中管理 Surface Hub 2S 上的設定。</span><span class="sxs-lookup"><span data-stu-id="4de3e-132">You can still enroll the device with Intune to centrally manage settings on your Surface Hub 2S.</span></span>

## <a name="azure-active-directory"></a><span data-ttu-id="4de3e-133">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="4de3e-133">Azure Active Directory</span></span>

<span data-ttu-id="4de3e-134">當您選擇將 Surface Hub 2S 與 Azure Active Directory (Azure AD) 進行連結時，全域系統管理員安全性群組的任何使用者都可以在 Surface Hub 2S 上登錄設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="4de3e-134">When you choose to affiliate your Surface Hub 2S with Azure Active Directory (Azure AD), any user in the Global Admins Security Group can sign in to the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="4de3e-135">您也可以設定非全域系統管理員帳戶，將許可權限制為管理 Surface Hub 2S 上的設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="4de3e-135">You can also configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="4de3e-136">這可讓您只將 Surface Hub 2S 的系統管理員許可權範圍範圍，並防止整個 Azure AD 網域可能不需要的系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="4de3e-136">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> 

<span data-ttu-id="4de3e-137">如果您為貴組織啟用 Intune 自動註冊，Surface Hub 2S 會自動向 Intune 註冊。</span><span class="sxs-lookup"><span data-stu-id="4de3e-137">If you enabled Intune Automatic Enrollment for your organization, Surface Hub 2S will automatically enroll itself with Intune.</span></span> <span data-ttu-id="4de3e-138">裝置 BitLocker 金鑰會自動儲存于 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="4de3e-138">The device’s BitLocker key is automatically saved in Azure AD.</span></span> 

<span data-ttu-id="4de3e-139">若要深入瞭解使用 Azure AD 管理 Surface Hub，請參閱：</span><span class="sxs-lookup"><span data-stu-id="4de3e-139">To learn more about managing Surface Hub with Azure AD, see:</span></span> 

 - [<span data-ttu-id="4de3e-140">系統管理員群組管理</span><span class="sxs-lookup"><span data-stu-id="4de3e-140">Admin group management</span></span>](admin-group-management-for-surface-hub.md)
 - [<span data-ttu-id="4de3e-141">在 Surface Hub 2S 上設定非全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="4de3e-141">Configure non Global admin accounts on Surface Hub 2S</span></span>](surface-hub-2s-nonglobal-admin.md)

