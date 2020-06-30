---
title: 密碼管理 (Surface Hub)
description: 每個 Microsoft Surface Hub 裝置帳戶都需要密碼來驗證和啟用裝置上的功能。
ms.assetid: 0FBFB546-05F0-430E-905E-87111046E4B8
ms.reviewer: ''
manager: laurawi
keywords: 密碼, 密碼管理, 密碼循環使用, 裝置帳戶
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: bef626fce875d5074f3ed47ed957e821beec7c77
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832066"
---
# <span data-ttu-id="66926-104">密碼管理 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="66926-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="66926-105">每個 Microsoft Surface Hub 裝置帳戶都需要密碼來驗證和啟用裝置上的功能。</span><span class="sxs-lookup"><span data-stu-id="66926-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="66926-106">基於安全性考量，您可能想要定期變更 (或「循環使用」) 此密碼。</span><span class="sxs-lookup"><span data-stu-id="66926-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="66926-107">不過，如果裝置帳戶的密碼變更，之前儲存在 Surface Hub 上的密碼將會無效，而取決於該裝置帳戶的所有功能都將停用。</span><span class="sxs-lookup"><span data-stu-id="66926-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="66926-108">您將需要在 Surface Hub 上，從 \[設定\] 應用程式更新裝置帳戶的密碼，以重新啟用這些功能。</span><span class="sxs-lookup"><span data-stu-id="66926-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="66926-109">有兩個選項可簡化您 Surface Hub 裝置帳戶的密碼管理：</span><span class="sxs-lookup"><span data-stu-id="66926-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="66926-110">關閉裝置帳戶的密碼到期功能。</span><span class="sxs-lookup"><span data-stu-id="66926-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="66926-111">允許 Surface Hub 自動循環使用裝置帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="66926-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <span data-ttu-id="66926-112">關閉裝置帳戶的密碼循環使用</span><span class="sxs-lookup"><span data-stu-id="66926-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="66926-113">將裝置帳戶的 **PasswordNeverExpires** 屬性設為 True。</span><span class="sxs-lookup"><span data-stu-id="66926-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="66926-114">您應該確認這是否符合組織的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="66926-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <span data-ttu-id="66926-115">允許 Surface Hub 自動循環使用裝置帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="66926-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="66926-116">Surface Hub 可以藉由經常變更密碼來管理裝置帳戶的密碼，而不需要您手動更新裝置帳戶的資訊。</span><span class="sxs-lookup"><span data-stu-id="66926-116">The Surface Hub can manage a device account’s password by changing it frequently without requiring you to manually update the device account’s information.</span></span> <span data-ttu-id="66926-117">您可以在 **[設定]** 中啟用此功能。</span><span class="sxs-lookup"><span data-stu-id="66926-117">You can enable this feature in **Settings**.</span></span> <span data-ttu-id="66926-118">一旦啟用之後，將會每週在維護時間變更裝置帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="66926-118">Once enabled, the device account's password will change weekly during maintenance hours.</span></span>

<span data-ttu-id="66926-119">請注意 變更裝置帳戶的密碼時，您將不會看見新的密碼。</span><span class="sxs-lookup"><span data-stu-id="66926-119">Note that when the device account’s password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="66926-120">如果您需要登入帳戶或再次提供密碼 (例如，如果您想要在 Surface Hub 上變更裝置帳戶設定)，則您需要使用 Active Directory 或 Office 365 管理入口網站來重設密碼。</span><span class="sxs-lookup"><span data-stu-id="66926-120">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Office 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66926-121">如果您的組織使用混合式拓樸 (部分服務是以內部部署方式裝載，部分服務是透過 Office 365 線上裝載)，您必須以 **domain\username** 格式設定裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="66926-121">If your organization uses a hybrid topology (some services are hosted on-premises and some are hosted online through Office 365), you must setup the device account in **domain\username** format.</span></span> <span data-ttu-id="66926-122">否則，密碼循環使用將無法運作。</span><span class="sxs-lookup"><span data-stu-id="66926-122">Otherwise, password rotation will not work.</span></span>
