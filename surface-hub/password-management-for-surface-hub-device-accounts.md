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
ms.openlocfilehash: 215736527121306c712932f57a5a3a853fb3bb20
ms.sourcegitcommit: 366eedceb9f859f5e87ba032b161f248360cb895
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "11445579"
---
# <a name="password-management-surface-hub"></a><span data-ttu-id="c6ece-104">密碼管理 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="c6ece-104">Password management (Surface Hub)</span></span>

<span data-ttu-id="c6ece-105">每個 Microsoft Surface Hub 裝置帳戶都需要密碼來驗證和啟用裝置上的功能。</span><span class="sxs-lookup"><span data-stu-id="c6ece-105">Every Microsoft Surface Hub device account requires a password to authenticate and enable features on the device.</span></span> <span data-ttu-id="c6ece-106">基於安全性考量，您可能想要定期變更 (或「循環使用」) 此密碼。</span><span class="sxs-lookup"><span data-stu-id="c6ece-106">For security reasons, you may want to change (or "rotate") this password regularly.</span></span> <span data-ttu-id="c6ece-107">不過，如果裝置帳戶的密碼變更，之前儲存在 Surface Hub 上的密碼將會無效，而取決於該裝置帳戶的所有功能都將停用。</span><span class="sxs-lookup"><span data-stu-id="c6ece-107">However, if the device account’s password changes, the password that was previously stored on the Surface Hub will be invalid, and all features that depend on the device account will be disabled.</span></span> <span data-ttu-id="c6ece-108">您將需要在 Surface Hub 上，從 \[設定\] 應用程式更新裝置帳戶的密碼，以重新啟用這些功能。</span><span class="sxs-lookup"><span data-stu-id="c6ece-108">You will need to update the device account’s password on the Surface Hub from the Settings app to re-enable these features.</span></span>

<span data-ttu-id="c6ece-109">有兩個選項可簡化您 Surface Hub 裝置帳戶的密碼管理：</span><span class="sxs-lookup"><span data-stu-id="c6ece-109">To simplify password management for your Surface Hub device accounts, there are two options:</span></span>

1.  <span data-ttu-id="c6ece-110">關閉裝置帳戶的密碼到期功能。</span><span class="sxs-lookup"><span data-stu-id="c6ece-110">Turn off password expiration for the device account.</span></span>
2.  <span data-ttu-id="c6ece-111">允許 Surface Hub 自動循環使用裝置帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="c6ece-111">Allow the Surface Hub to automatically rotate the device account’s password.</span></span>


## <a name="turn-off-password-rotation-for-the-device-account"></a><span data-ttu-id="c6ece-112">關閉裝置帳戶的密碼循環使用</span><span class="sxs-lookup"><span data-stu-id="c6ece-112">Turn off password rotation for the device account</span></span>

<span data-ttu-id="c6ece-113">將裝置帳戶的 **PasswordNeverExpires** 屬性設為 True。</span><span class="sxs-lookup"><span data-stu-id="c6ece-113">Set the device account’s **PasswordNeverExpires** property to True.</span></span> <span data-ttu-id="c6ece-114">您應該確認這是否符合組織的安全性需求。</span><span class="sxs-lookup"><span data-stu-id="c6ece-114">You should verify whether this meets your organization’s security requirements.</span></span>


## <a name="allow-the-surface-hub-to-automatically-rotate-the-device-accounts-password"></a><span data-ttu-id="c6ece-115">允許 Surface Hub 自動循環使用裝置帳戶的密碼</span><span class="sxs-lookup"><span data-stu-id="c6ece-115">Allow the Surface Hub to automatically rotate the device account’s password</span></span>

<span data-ttu-id="c6ece-116">Surface Hub 可以自動變更裝置帳戶的密碼，而不需要您手動更新密碼。</span><span class="sxs-lookup"><span data-stu-id="c6ece-116">The Surface Hub can automatically change a device account's password without requiring you to manually update it.</span></span> <span data-ttu-id="c6ece-117">您可以在設定 Surface Hub\*\*\*\* 帳戶中  >  \*\*\*\*  >  **啟用此功能**。</span><span class="sxs-lookup"><span data-stu-id="c6ece-117">You can enable this feature in **Settings** > **Surface Hub** > **Accounts**.</span></span> <span data-ttu-id="c6ece-118">如果您開啟密碼旋轉，Surface Hub 會嘗試在維護期間每 7 天變更密碼。</span><span class="sxs-lookup"><span data-stu-id="c6ece-118">If you turn on Password Rotation, the Surface Hub will attempt to change the password every 7 days during maintenance hours.</span></span> <span data-ttu-id="c6ece-119">密碼在會議期間不會變更。</span><span class="sxs-lookup"><span data-stu-id="c6ece-119">Passwords do not change during a meeting.</span></span> <span data-ttu-id="c6ece-120">如果自上次密碼旋轉以來已過了 7 天，但 Surface Hub 已關閉，它會嘗試在開啟時立即變更密碼，或每隔 10 分鐘變更密碼，直到成功。</span><span class="sxs-lookup"><span data-stu-id="c6ece-120">If 7 days have passed since the last password rotation, but the Surface Hub was off, it will attempt to change the password immediately when turned on or every 10 minutes until successful.</span></span>

<span data-ttu-id="c6ece-121">自動產生的密碼包含 15-32 個字元，包括大寫和小寫字母、數位和特殊字元的組合。</span><span class="sxs-lookup"><span data-stu-id="c6ece-121">The automatically generated passwords contain 15-32 characters including a combination of uppercase and lowercase letters, numbers, and special characters.</span></span> <span data-ttu-id="c6ece-122">請注意，當裝置帳戶的密碼變更時，系統不會顯示新的密碼。</span><span class="sxs-lookup"><span data-stu-id="c6ece-122">Note that when the device account's password is changed, you will not be shown the new password.</span></span> <span data-ttu-id="c6ece-123">如果您需要登錄帳戶，或再次提供密碼 (例如，如果您想要變更 Surface Hub) 上的裝置帳戶設定，則需要使用 Active Directory 或 Microsoft 365 系統管理入口網站重設密碼。</span><span class="sxs-lookup"><span data-stu-id="c6ece-123">If you need to sign in to the account, or to provide the password again (for example, if you want to change the device account settings on the Surface Hub), then you'll need use Active Directory or the Microsoft 365 admin portal to reset the password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c6ece-124">將裝置帳戶新增到 Surface Hub 時所使用的格式會影響必須使用哪個裝置[](prepare-your-environment-for-surface-hub.md)關聯選項，才能讓密碼旋轉工作。</span><span class="sxs-lookup"><span data-stu-id="c6ece-124">The format used when adding the device account to the Surface Hub has an impact on which [device affiliation](prepare-your-environment-for-surface-hub.md) option must be used in order for password rotation to work.</span></span> <span data-ttu-id="c6ece-125">如果以網域 **\使用者名稱格式** 新增帳戶，在初始設定期間將 Hub 與內部部署 Active Directory 關聯。</span><span class="sxs-lookup"><span data-stu-id="c6ece-125">If adding the account in **domain\username** format, affiliate the Hub with on-premises Active Directory during initial setup.</span></span> <span data-ttu-id="c6ece-126">如果以格式新增帳戶，在初始設定期間，將 `username@domain.com` Hub 與 Azure Active Directory 關聯。</span><span class="sxs-lookup"><span data-stu-id="c6ece-126">If adding the account in `username@domain.com` format, affiliate the Hub with Azure Active Directory during initial setup.</span></span> <span data-ttu-id="c6ece-127">否則，密碼循環使用將無法運作。</span><span class="sxs-lookup"><span data-stu-id="c6ece-127">Otherwise, password rotation will not work.</span></span>
