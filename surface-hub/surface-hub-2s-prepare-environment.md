---
title: 針對 Surface Hub 2S 準備您的環境
description: 瞭解您需要採取哪些做法來準備您的環境以進行 Surface Hub 的2秒。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/21/2019
ms.localizationpriority: Medium
ms.openlocfilehash: dddab2adce1bec9ff722a3324b9c4b1be609ae89
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934843"
---
# <span data-ttu-id="51e25-104">針對 Surface Hub 2S 準備您的環境</span><span class="sxs-lookup"><span data-stu-id="51e25-104">Prepare your environment for Surface Hub 2S</span></span>

## <span data-ttu-id="51e25-105">Office 365 就緒</span><span class="sxs-lookup"><span data-stu-id="51e25-105">Office 365 readiness</span></span>

<span data-ttu-id="51e25-106">如果您使用的是 Exchange Online、商務用 Skype Online、Microsoft 團隊或 Microsoft 白板，且想要在 Intune 中管理 Surface Hub 2，請先查看 [端點的 Office 365 需求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。</span><span class="sxs-lookup"><span data-stu-id="51e25-106">If you use Exchange Online, Skype for Business Online, Microsoft Teams, or Microsoft Whiteboard, and intend to manage Surface Hub 2S with Intune, first review the [Office 365 requirements for endpoints](https://docs.microsoft.com/office365/enterprise/office-365-endpoints).</span></span>

<span data-ttu-id="51e25-107">Office 365 端點可透過防火牆直接傳送所有受信任的 Office 365 網路要求，以繞過所有其他的資料包層級檢查或處理，協助優化您的網路。</span><span class="sxs-lookup"><span data-stu-id="51e25-107">Office 365 endpoints help optimize your network by sending all trusted Office 365 network requests directly through your firewall, bypassing all additional packet-level inspection or processing.</span></span> <span data-ttu-id="51e25-108">此功能可減少延遲及您的周邊容量需求。</span><span class="sxs-lookup"><span data-stu-id="51e25-108">This feature reduces latency and your perimeter capacity requirements.</span></span>

<span data-ttu-id="51e25-109">Microsoft 會定期使用新功能和功能更新 Office 365 服務，這可能會改變所需的埠、Url 和 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="51e25-109">Microsoft regularly updates the Office 365 service with new features and functionality, which may alter required ports, URLs, and IP addresses.</span></span> <span data-ttu-id="51e25-110">若要評估、設定及掌握最新變更，請訂閱 [Office 365 IP 位址和 URL Web 服務](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。</span><span class="sxs-lookup"><span data-stu-id="51e25-110">To evaluate, configure, and stay up to date with changes, subscribe to the [Office 365 IP Address and URL Web service](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service).</span></span>

## <span data-ttu-id="51e25-111">裝置附屬</span><span class="sxs-lookup"><span data-stu-id="51e25-111">Device affiliation</span></span>

<span data-ttu-id="51e25-112">使用裝置附屬關係來管理使用者對 Surface Hub 2 上的 [設定] app 的存取權。</span><span class="sxs-lookup"><span data-stu-id="51e25-112">Use Device affiliation to manage user access to the Settings app on Surface Hub 2S.</span></span>
<span data-ttu-id="51e25-113">在 Surface Hub 2) 上執行的 Windows 10 小組作業系統 (，只有獲授權的使用者才能使用 [設定] app 來調整設定。</span><span class="sxs-lookup"><span data-stu-id="51e25-113">With the Windows 10 Team operating system (that runs on Surface Hub 2S),  only authorized users can adjust settings using the Settings app.</span></span> <span data-ttu-id="51e25-114">由於選擇 [隸屬關係] 可能會影響功能可用性，請適當地規劃，以確保使用者可以依預期存取功能。</span><span class="sxs-lookup"><span data-stu-id="51e25-114">Since choosing the affiliation can impact feature availability, plan appropriately to ensure that users can access features as intended.</span></span>

> [!NOTE]
> <span data-ttu-id="51e25-115">您只能在 (OOBE) 安裝程式的初始全新體驗期間設定裝置附屬。</span><span class="sxs-lookup"><span data-stu-id="51e25-115">You can only set Device affiliation during the initial out-of-box experience (OOBE) setup.</span></span> <span data-ttu-id="51e25-116">如果您需要重設裝置附屬關係，您必須重複 OOBE 設定。</span><span class="sxs-lookup"><span data-stu-id="51e25-116">If you need to reset Device affiliation, you’ll have to repeat OOBE setup.</span></span>

## <span data-ttu-id="51e25-117">無隸屬關係</span><span class="sxs-lookup"><span data-stu-id="51e25-117">No affiliation</span></span>

<span data-ttu-id="51e25-118">沒有任何隸屬關係，就像是在擁有各個 Surface Hub 2 的不同本機系統管理員帳戶的工作組中都有 Surface Hub 2。</span><span class="sxs-lookup"><span data-stu-id="51e25-118">No affiliation is like having Surface Hub 2S in a workgroup with a different local Administrator account on each Surface Hub 2S.</span></span> <span data-ttu-id="51e25-119">如果您選擇 [無附屬]，您必須在本機將 [BitLocker 金鑰儲存至 USB 拇指磁片磁碟機](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)。</span><span class="sxs-lookup"><span data-stu-id="51e25-119">If you choose No affiliation, you must locally save the [BitLocker Key to a USB thumb drive](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq).</span></span> <span data-ttu-id="51e25-120">您仍然可以使用 Intune 註冊裝置;不過，只有本機管理員才能使用在 OOBE 期間設定的帳號憑證來存取 [設定] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="51e25-120">You can still enroll the device with Intune; however, only the local admin can access the Settings app using the account credentials configured during OOBE.</span></span> <span data-ttu-id="51e25-121">您可以從 [設定] app 變更系統管理員帳戶密碼。</span><span class="sxs-lookup"><span data-stu-id="51e25-121">You can change the Administrator account password from the Settings app.</span></span>

## <span data-ttu-id="51e25-122">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="51e25-122">Active Directory Domain Services</span></span>

<span data-ttu-id="51e25-123">如果您使用內部部署的 Active Directory 網域服務來建立 Surface Hub 2 的關聯，您必須使用網域上的安全性群組來管理 [設定] app 的存取權。</span><span class="sxs-lookup"><span data-stu-id="51e25-123">If you affiliate Surface Hub 2S with on-premises Active Directory Domain Services, you need to manage access to the Settings app using a security group on your domain.</span></span> <span data-ttu-id="51e25-124">這有助於確保所有安全群組成員都有權變更 Surface Hub 2 的設定。</span><span class="sxs-lookup"><span data-stu-id="51e25-124">This helps ensure that all security group members have permissions to change settings on Surface Hub 2S.</span></span> <span data-ttu-id="51e25-125">另請注意下列事項：</span><span class="sxs-lookup"><span data-stu-id="51e25-125">Also note the following:</span></span>

- <span data-ttu-id="51e25-126">當 Surface Hub 2 擁有您的內部部署 Active Directory 網域服務的子公司時，可將 BitLocker 金鑰儲存在 Active Directory 架構中。</span><span class="sxs-lookup"><span data-stu-id="51e25-126">When Surface Hub 2S affiliates with your on-premises Active Directory Domain Services, the BitLocker key can be saved in the Active Directory Schema.</span></span> <span data-ttu-id="51e25-127">如需詳細資訊，請參閱 [準備貴組織以進行 BitLocker：規劃與原則](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。</span><span class="sxs-lookup"><span data-stu-id="51e25-127">For more information, see [Prepare your organization for BitLocker: Planning and policies](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies).</span></span> 
- <span data-ttu-id="51e25-128">貴組織的根信任 Ca 會推送至 Surface Hub 2 中的相同容器，這表示您不需要使用置備套件匯入它們。</span><span class="sxs-lookup"><span data-stu-id="51e25-128">Your organization’s Trusted Root CAs are pushed to the same container in Surface Hub 2S, which means you don’t need to import them using a provisioning package.</span></span>
- <span data-ttu-id="51e25-129">您仍可在 Intune 中註冊裝置，以集中管理 Surface Hub 2 的設定。</span><span class="sxs-lookup"><span data-stu-id="51e25-129">You can still enroll the device with Intune to centrally manage settings on your Surface Hub 2S.</span></span>

## <span data-ttu-id="51e25-130">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="51e25-130">Azure Active Directory</span></span>

<span data-ttu-id="51e25-131">當您選擇將 Surface Hub 2 與 Azure Active Directory (Azure AD) 結合時，全域系統管理員安全性群組中的任何使用者都可以在 Surface Hub 2 的 [設定] 應用程式中登入。</span><span class="sxs-lookup"><span data-stu-id="51e25-131">When you choose to affiliate your Surface Hub 2S with Azure Active Directory (Azure AD), any user in the Global Admins Security Group can sign in to the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="51e25-132">目前，不能委派其他群組登入 Surface Hub 2 上的 [設定] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="51e25-132">Currently, no other group can be delegated to sign in to the Settings app on Surface Hub 2S.</span></span>

<span data-ttu-id="51e25-133">如果您為組織啟用 Intune 自動登記，Surface Hub 秒將會自動使用 Intune 註冊自己。</span><span class="sxs-lookup"><span data-stu-id="51e25-133">If you enabled Intune Automatic Enrollment for your organization, Surface Hub 2S will automatically enroll itself with Intune.</span></span> <span data-ttu-id="51e25-134">裝置的 BitLocker 金鑰會自動儲存在 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="51e25-134">The device’s BitLocker key is automatically saved in Azure AD.</span></span> <span data-ttu-id="51e25-135">當 affiliating Surface Hub 2 和 Azure AD 時，單一登入和輕鬆驗證將無法運作。</span><span class="sxs-lookup"><span data-stu-id="51e25-135">When affiliating Surface Hub 2S with Azure AD, single sign-on and Easy Authentication will not work.</span></span>
