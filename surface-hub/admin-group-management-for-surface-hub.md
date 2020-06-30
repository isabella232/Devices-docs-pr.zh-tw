---
title: 系統管理員群組管理 (Surface Hub)
description: 您可以在裝置上開啟 \[設定\] 應用程式，個別設定每一個 Microsoft Surface Hub。
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: 系統管理員群組管理, \[設定\] 應用程式, 設定 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 716e409bf988e7178ec45e21165aad070d027eee
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831898"
---
# <span data-ttu-id="397f1-104">系統管理員群組管理 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="397f1-104">Admin group management (Surface Hub)</span></span>


<span data-ttu-id="397f1-105">在個別裝置上使用 \[設定\] 應用程式，可各自設定其上的 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="397f1-105">Every Surface Hub can be configured locally using the Settings app on the device.</span></span> <span data-ttu-id="397f1-106">為防止未經授權的使用者變更設定，\[設定\] 應用程式要求您必須提供系統管理員認證才能開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="397f1-106">To prevent unauthorized users from changing settings, the Settings app requires admin credentials to open the app.</span></span>


## <span data-ttu-id="397f1-107">系統管理員群組管理</span><span class="sxs-lookup"><span data-stu-id="397f1-107">Admin Group Management</span></span>

<span data-ttu-id="397f1-108">您可以使用下列三種方式的其中一種來設定裝置的系統管理員帳戶：</span><span class="sxs-lookup"><span data-stu-id="397f1-108">You can set up administrator accounts for the device in one of three ways:</span></span>

-   <span data-ttu-id="397f1-109">建立本機系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="397f1-109">Create a local admin account</span></span>
-   <span data-ttu-id="397f1-110">將裝置加入 Active Directory (AD) 網域</span><span class="sxs-lookup"><span data-stu-id="397f1-110">Domain join the device to Active Directory (AD)</span></span>
-   <span data-ttu-id="397f1-111">Azure Active Directory (Azure AD) 加入裝置</span><span class="sxs-lookup"><span data-stu-id="397f1-111">Azure Active Directory (Azure AD) join the device</span></span>


### <span data-ttu-id="397f1-112">建立本機系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="397f1-112">Create a local admin account</span></span>

<span data-ttu-id="397f1-113">若要建立本機系統管理員，請[在初次執行期間選擇使用本機系統管理員](first-run-program-surface-hub.md#use-a-local-admin)。</span><span class="sxs-lookup"><span data-stu-id="397f1-113">To create a local admin, [choose to use a local admin during first run](first-run-program-surface-hub.md#use-a-local-admin).</span></span> <span data-ttu-id="397f1-114">這將在 Surface Hub 上使用您選擇的使用者名稱與密碼，來建立單一本機系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="397f1-114">This will create a single local admin account on the Surface Hub with the username and password of your choice.</span></span> <span data-ttu-id="397f1-115">使用這些認證來開啟 \[設定\] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="397f1-115">Use these credentials to open the Settings app.</span></span>

<span data-ttu-id="397f1-116">請注意，所有目錄服務都不會備份本機系統管理員帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="397f1-116">Note that the local admin account information is not backed by any directory service.</span></span> <span data-ttu-id="397f1-117">如果裝置沒有 Active Directory (AD) 或 Azure Active Directory (Azure AD) 的存取權，建議您只選擇本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="397f1-117">We recommend you only choose a local admin if the device does not have access to Active Directory (AD) or Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="397f1-118">如果您決定變更本機系統管理員的密碼，可以在 \[設定\] 中變更。</span><span class="sxs-lookup"><span data-stu-id="397f1-118">If you decide to change the local admin’s password, you can do so in Settings.</span></span> <span data-ttu-id="397f1-119">不過，如果您想要將使用本機系統管理員變更為使用來自您網域或 Azure AD 租用戶的群組，則您需要[重設裝置](device-reset-surface-hub.md)，然後再次進行初次程式。</span><span class="sxs-lookup"><span data-stu-id="397f1-119">However, if you want to change from using the local admin account to using a group from your domain or Azure AD tenant, then you’ll need to [reset the device](device-reset-surface-hub.md) and go through the first-time program again.</span></span>

### <span data-ttu-id="397f1-120">將裝置加入 Active Directory (AD) 網域</span><span class="sxs-lookup"><span data-stu-id="397f1-120">Domain join the device to Active Directory (AD)</span></span>

<span data-ttu-id="397f1-121">您可以將 Surface Hub 加入您的 AD 網域，以允許來自指定安全性群組的使用者進行設定。</span><span class="sxs-lookup"><span data-stu-id="397f1-121">You can domain join the Surface Hub to your AD domain to allow users from a specified security group to configure settings.</span></span> <span data-ttu-id="397f1-122">在初次執行時，請選擇使用 [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services)。</span><span class="sxs-lookup"><span data-stu-id="397f1-122">During first run, choose to use [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services).</span></span> <span data-ttu-id="397f1-123">您將需要提供能夠加入您選擇之網域的認證，以及現有安全性群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="397f1-123">You'll need to provide credentials that are capable of joining the domain of your choice, and the name of an existing security group.</span></span> <span data-ttu-id="397f1-124">所有屬於該安全性群組成員的使用者都可以輸入他們的認證，並將 \[設定\] 解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="397f1-124">Anyone who is a member of that security group can enter their credentials and unlock Settings.</span></span>

#### <span data-ttu-id="397f1-125">當您將 Surface Hub 加入網域時會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="397f1-125">What happens when you domain join your Surface Hub?</span></span>
<span data-ttu-id="397f1-126">Surface Hub 會透過加入網域來：</span><span class="sxs-lookup"><span data-stu-id="397f1-126">Surface Hubs use domain join to:</span></span>
- <span data-ttu-id="397f1-127">將系統管理員權限授與 AD 中指定安全性群組的成員。</span><span class="sxs-lookup"><span data-stu-id="397f1-127">Grant admin rights to members of a specified security group in AD.</span></span>
- <span data-ttu-id="397f1-128">透過將裝置的 BitLocker 修復金鑰儲存在 AD 中的電腦物件底下來備份它。</span><span class="sxs-lookup"><span data-stu-id="397f1-128">Backup the device's BitLocker recovery key by storing it under the computer object in AD.</span></span> <span data-ttu-id="397f1-129">請參閱[儲存您的 BitLocker 金鑰](save-bitlocker-key-surface-hub.md)來取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="397f1-129">See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) for details.</span></span>
- <span data-ttu-id="397f1-130">透過網域控制站同步處理系統時鐘以進行加密通訊</span><span class="sxs-lookup"><span data-stu-id="397f1-130">Synchronize the system clock with the domain controller for encrypted communication</span></span>

<span data-ttu-id="397f1-131">Surface Hub 不支援從網域控制站套用群組原則或憑證。</span><span class="sxs-lookup"><span data-stu-id="397f1-131">Surface Hub does not support applying group policies or certificates from the domain controller.</span></span>

> [!NOTE]
> <span data-ttu-id="397f1-132">如果您的 Surface Hub 失去網域的信任 (例如，如果您在 Surface Hub 加入網域之後，將它從網域移除)，您將無法在裝置中進行驗證並開啟 \[設定\]。</span><span class="sxs-lookup"><span data-stu-id="397f1-132">If your Surface Hub loses trust with the domain (for example, if you remove the Surface Hub from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="397f1-133">如果您決定移除 Surface Hub 與您網域的信任關係，請先[重設裝置](device-reset-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="397f1-133">If you decide to remove the trust relationship of the Surface Hub with your domain, [reset the device](device-reset-surface-hub.md) first.</span></span>


### <span data-ttu-id="397f1-134">Azure Active Directory (Azure AD) 加入裝置</span><span class="sxs-lookup"><span data-stu-id="397f1-134">Azure Active Directory (Azure AD) join the device</span></span>

<span data-ttu-id="397f1-135">您可以將 Surface Hub 加入 Azure AD，以允許來自您 Azure AD 租用戶的 IT 專業人員進行設定。</span><span class="sxs-lookup"><span data-stu-id="397f1-135">You can Azure AD join the Surface Hub to allow IT pros from your Azure AD tenant to configure settings.</span></span> <span data-ttu-id="397f1-136">在初次執行時，請選擇使用 [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory)。</span><span class="sxs-lookup"><span data-stu-id="397f1-136">During first run, choose to use [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory).</span></span> <span data-ttu-id="397f1-137">您需要提供能夠加入您選擇之 Azure AD 租用戶的認證。</span><span class="sxs-lookup"><span data-stu-id="397f1-137">You will need to provide credentials that are capable of joining the Azure AD tenant of your choice.</span></span> <span data-ttu-id="397f1-138">成功加入 Azure AD 之後，適當的人員將會在裝置上獲得系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="397f1-138">After you successfully Azure AD join, the appropriate people will be granted admin rights on the device.</span></span>

<span data-ttu-id="397f1-139">根據預設，所有的**全域系統管理員**都會在加入 Azure AD 的 Surface Hub 上獲得系統管理員權限。</span><span class="sxs-lookup"><span data-stu-id="397f1-139">By default, all **global administrators** will be given admin rights on an Azure AD joined Surface Hub.</span></span> <span data-ttu-id="397f1-140">透過 **Azure AD Premium** 或 **Enterprise Mobility Suite (EMS)**，您將可以新增額外的系統管理員：</span><span class="sxs-lookup"><span data-stu-id="397f1-140">With **Azure AD Premium** or **Enterprise Mobility Suite (EMS)**, you can add additional administrators:</span></span>
1.  <span data-ttu-id="397f1-141">在 [Azure 傳統入口網站](https://manage.windowsazure.com/)中，按一下 **Active Directory**，然後按一下您組織目錄的名稱。</span><span class="sxs-lookup"><span data-stu-id="397f1-141">In the [Azure classic portal](https://manage.windowsazure.com/), click **Active Directory**, and then click the name of your organization's directory.</span></span>
2.  <span data-ttu-id="397f1-142">在 **\[設定\]** 頁面上，於 **\[裝置\]**  >  **\[加入 Azure AD 之裝置的其他系統管理員\]** 底下，按一下 **\[已選取\]**。</span><span class="sxs-lookup"><span data-stu-id="397f1-142">On the **Configure** page, under **Devices** > **Additional administrators on Azure AD joined devices**, click **Selected**.</span></span>
3.  <span data-ttu-id="397f1-143">按一下 **\[新增\]**，然後選取您想要在 Surface Hub 和其他加入 Azure AD 的裝置上新增為系統管理員的使用者。</span><span class="sxs-lookup"><span data-stu-id="397f1-143">Click **Add**, and select the users you want to add as administrators on your Surface Hub and other Azure AD joined devices.</span></span>
4.  <span data-ttu-id="397f1-144">當您完成之後，請按一下核取記號以儲存變更。</span><span class="sxs-lookup"><span data-stu-id="397f1-144">When you have finished, click the checkmark button to save your change.</span></span>

#### <span data-ttu-id="397f1-145">當您將 Surface Hub 加入 Azure AD 時會發生什麼事？</span><span class="sxs-lookup"><span data-stu-id="397f1-145">What happens when you Azure AD join your Surface Hub?</span></span>
<span data-ttu-id="397f1-146">Surface Hub 會透過加入 Azure AD 來：</span><span class="sxs-lookup"><span data-stu-id="397f1-146">Surface Hubs use Azure AD join to:</span></span>
- <span data-ttu-id="397f1-147">將系統管理員權限授與 Azure AD 租用戶中適當的使用者。</span><span class="sxs-lookup"><span data-stu-id="397f1-147">Grant admin rights to the appropriate users in your Azure AD tenant.</span></span>
- <span data-ttu-id="397f1-148">透過將裝置的 BitLocker 修復金鑰儲存在用來將裝置加入 Azure AD 的帳戶底下來備份它。</span><span class="sxs-lookup"><span data-stu-id="397f1-148">Backup the device's BitLocker recovery key by storing it under the account that was used to Azure AD join the device.</span></span> <span data-ttu-id="397f1-149">請參閱[儲存您的 BitLocker 金鑰](save-bitlocker-key-surface-hub.md)來取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="397f1-149">See [Save your BitLocker key](save-bitlocker-key-surface-hub.md) for details.</span></span>

### <span data-ttu-id="397f1-150">透過 Azure Active Directory join 自動登記</span><span class="sxs-lookup"><span data-stu-id="397f1-150">Automatic enrollment via Azure Active Directory join</span></span>

<span data-ttu-id="397f1-151">Surface Hub 現在支援透過將裝置加入 Azure Active Directory 來自動註冊 Intune。</span><span class="sxs-lookup"><span data-stu-id="397f1-151">Surface Hub now supports the ability to automatically enroll in Intune by joining the device to Azure Active Directory.</span></span> 

<span data-ttu-id="397f1-152">如需詳細資訊，請參閱[啟用 Windows 10 自動註冊](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)。</span><span class="sxs-lookup"><span data-stu-id="397f1-152">For more information, see [Enable Windows 10 automatic enrollment](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment).</span></span>

### <span data-ttu-id="397f1-153">我應該選擇哪一個？</span><span class="sxs-lookup"><span data-stu-id="397f1-153">Which should I choose?</span></span>

<span data-ttu-id="397f1-154">如果您的組織使用 AD 或 Azure AD，我們建議您選擇加入網域或加入 Azure AD (主要是基於安全性考量)。</span><span class="sxs-lookup"><span data-stu-id="397f1-154">If your organization is using AD or Azure AD, we recommend you either domain join or Azure AD join, primarily for security reasons.</span></span> <span data-ttu-id="397f1-155">使用者將能夠使用自己的認證進行驗證並解除鎖定 \[設定\]，而且可以移入或移出與您的網域相關聯的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="397f1-155">People will be able to authenticate and unlock Settings with their own credentials, and can be moved in or out of the security groups associated with your domain.</span></span>

| <span data-ttu-id="397f1-156">選項</span><span class="sxs-lookup"><span data-stu-id="397f1-156">Option</span></span>                                            | <span data-ttu-id="397f1-157">需求</span><span class="sxs-lookup"><span data-stu-id="397f1-157">Requirements</span></span>                            | <span data-ttu-id="397f1-158">哪些認證可以用於存取 \[設定\] 應用程式？</span><span class="sxs-lookup"><span data-stu-id="397f1-158">Which credentials can be used to access the Settings app?</span></span>  |
|---------------------------------------------------|-----------------------------------------|-------|
| <span data-ttu-id="397f1-159">建立本機系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="397f1-159">Create a local admin account</span></span>                      | <span data-ttu-id="397f1-160">無</span><span class="sxs-lookup"><span data-stu-id="397f1-160">None</span></span>                                    | <span data-ttu-id="397f1-161">於初次執行時指定的使用者名稱和密碼</span><span class="sxs-lookup"><span data-stu-id="397f1-161">The user name and password specified during first run</span></span> |
| <span data-ttu-id="397f1-162">加入 Active Directory (AD) 網域</span><span class="sxs-lookup"><span data-stu-id="397f1-162">Domain join to Active Directory (AD)</span></span>              | <span data-ttu-id="397f1-163">您的組織使用 AD</span><span class="sxs-lookup"><span data-stu-id="397f1-163">Your organization uses AD</span></span>               | <span data-ttu-id="397f1-164">來自您網域中指定安全性群組的任何 AD 使用者</span><span class="sxs-lookup"><span data-stu-id="397f1-164">Any AD user from a specific security group in your domain</span></span> |
| <span data-ttu-id="397f1-165">Azure Active Directory (Azure AD) 加入裝置</span><span class="sxs-lookup"><span data-stu-id="397f1-165">Azure Active Directory (Azure AD) join the device</span></span> | <span data-ttu-id="397f1-166">您的組織使用 Azure AD Basic</span><span class="sxs-lookup"><span data-stu-id="397f1-166">Your organization uses Azure AD Basic</span></span>   | <span data-ttu-id="397f1-167">僅限全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="397f1-167">Global administrators only</span></span> |
| &nbsp;                                            | <span data-ttu-id="397f1-168">您的組織使用 Azure AD Premium 或 Enterprise Mobility Suite (EMS)</span><span class="sxs-lookup"><span data-stu-id="397f1-168">Your organization uses Azure AD Premium or Enterprise Mobility Suite (EMS)</span></span> | <span data-ttu-id="397f1-169">全域系統管理員及額外的系統管理員</span><span class="sxs-lookup"><span data-stu-id="397f1-169">Global administrators and additional administrators</span></span> |


