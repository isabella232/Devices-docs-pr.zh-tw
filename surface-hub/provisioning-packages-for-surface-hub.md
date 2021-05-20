---
title: 建立佈建套件 (Surface Hub)
description: 針對 Windows 10，您可以透過佈建套件來設定使用登錄或設定服務提供者 (CSP) 的設定。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: 新增憑證, 佈建套件
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: 5e0714d284cc5c8207633719ec8fb52cec9f95cb
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576983"
---
# <a name="create-provisioning-packages-surface-hub"></a><span data-ttu-id="b15b2-104">建立佈建套件 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="b15b2-104">Create provisioning packages (Surface Hub)</span></span>

<span data-ttu-id="b15b2-105">本主題說明如何使用 Windows 設定設計工具建立佈建套件，並將它套用至 Surface Hub 裝置。</span><span class="sxs-lookup"><span data-stu-id="b15b2-105">This topic explains how to create a provisioning package using the Windows Configuration Designer, and apply it to Surface Hub devices.</span></span> <span data-ttu-id="b15b2-106">針對 Surface Hub，您可以使用佈建套件來新增憑證、安裝通用 Windows 平台 (UWP) 應用程式，並自訂原則和設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-106">For Surface Hub, you can use provisioning packages to add certificates, install Universal Windows Platform (UWP) apps, and customize policies and settings.</span></span>

<span data-ttu-id="b15b2-107">您可以在初次執行設定時使用隨身碟，或透過**設定**應用程式，來套用佈建套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-107">You can apply a provisioning package using a USB stick during first-run setup, or through the **Settings** app.</span></span> 


## <a name="advantages"></a><span data-ttu-id="b15b2-108">優點</span><span class="sxs-lookup"><span data-stu-id="b15b2-108">Advantages</span></span>
-   <span data-ttu-id="b15b2-109">不使用行動裝置管理 (MDM) 提供者，快速設定裝置。</span><span class="sxs-lookup"><span data-stu-id="b15b2-109">Quickly configure devices without using a mobile device management (MDM) provider.</span></span>

-   <span data-ttu-id="b15b2-110">不需要網路連線。</span><span class="sxs-lookup"><span data-stu-id="b15b2-110">No network connectivity required.</span></span>

-   <span data-ttu-id="b15b2-111">套用方式簡單。</span><span class="sxs-lookup"><span data-stu-id="b15b2-111">Simple to apply.</span></span>

[<span data-ttu-id="b15b2-112">深入了解佈建套件的優點與用法。</span><span class="sxs-lookup"><span data-stu-id="b15b2-112">Learn more about the benefits and uses of provisioning packages.</span></span>](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## <a name="requirements"></a><span data-ttu-id="b15b2-113">需求</span><span class="sxs-lookup"><span data-stu-id="b15b2-113">Requirements</span></span> 

<span data-ttu-id="b15b2-114">若要建立佈建套件並套用至 Surface Hub，您將需要下列項目：</span><span class="sxs-lookup"><span data-stu-id="b15b2-114">To create and apply a provisioning package to a Surface Hub, you'll need the following:</span></span>

-   <span data-ttu-id="b15b2-115">Windows 設定設計工具，可從 透過 Microsoft Store 或 Windows 10 評定及部署套件 (ADK) 或安裝。</span><span class="sxs-lookup"><span data-stu-id="b15b2-115">Windows Configuration Designer, which can be installed from Microsoft Store or from the Windows 10 Assessment and Deployment Kit (ADK).</span></span> [<span data-ttu-id="b15b2-116">了解如何安裝 Windows 設定設計工具。</span><span class="sxs-lookup"><span data-stu-id="b15b2-116">Learn how to install Windows Configuration Designer.</span></span>](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   <span data-ttu-id="b15b2-117">USB 隨身碟。</span><span class="sxs-lookup"><span data-stu-id="b15b2-117">A USB stick.</span></span>
-   <span data-ttu-id="b15b2-118">如果您要使用**設定**應用程式套用該套件，您將需要裝置系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="b15b2-118">If you apply the package using the **Settings** app, you'll need device admin credentials.</span></span>

<span data-ttu-id="b15b2-119">您將會在執行 Windows10 的電腦上建立佈建套件、將套件儲存至 USB 磁碟機，然後將它部署到您的 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="b15b2-119">You create the provisioning package on a PC running Windows 10, save the package to a USB drive, and then deploy it to your Surface Hub.</span></span>


## <a name="supported-items-for-surface-hub-provisioning-packages"></a><span data-ttu-id="b15b2-120">Surface Hub 佈建套件的支援項目</span><span class="sxs-lookup"><span data-stu-id="b15b2-120">Supported items for Surface Hub provisioning packages</span></span>

<span data-ttu-id="b15b2-121">使用 **\[佈建 Surface Hub 裝置\]** 精靈，您可以：</span><span class="sxs-lookup"><span data-stu-id="b15b2-121">Using the **Provision Surface Hub devices** wizard, you can:</span></span>

- <span data-ttu-id="b15b2-122">註冊 Active Directory、Azure Active Directory 或 MDM</span><span class="sxs-lookup"><span data-stu-id="b15b2-122">Enroll in Active Directory, Azure Active Directory, or MDM</span></span> 
- <span data-ttu-id="b15b2-123">建立網置系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="b15b2-123">Create an device administrator account</span></span> 
- <span data-ttu-id="b15b2-124">新增應用程式與憑證</span><span class="sxs-lookup"><span data-stu-id="b15b2-124">Add applications and certificates</span></span>
- <span data-ttu-id="b15b2-125">設定 Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="b15b2-125">Configure proxy settings</span></span>
- <span data-ttu-id="b15b2-126">新增 Surface Hub 設定檔</span><span class="sxs-lookup"><span data-stu-id="b15b2-126">Add a Surface Hub configuration file</span></span>

>[!WARNING]
><span data-ttu-id="b15b2-127">您必須在 Windows 10 上執行 Windows 設定設計工具，才能使用精靈設定 Azure Active Directory 註冊。</span><span class="sxs-lookup"><span data-stu-id="b15b2-127">You must run Windows Configuration Designer on Windows 10 to configure Azure Active Directory enrollment using the wizard.</span></span>

<span data-ttu-id="b15b2-128">使用進階佈建編輯器，您可以將這些項目新增到 Surface Hub 的佈建套件：</span><span class="sxs-lookup"><span data-stu-id="b15b2-128">Using the advanced provisioning editor, you can add these items to provisioning packages for Surface Hub:</span></span>

- <span data-ttu-id="b15b2-129">**原則**：Surface Hub 支援[原則設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies)中一部分的原則。</span><span class="sxs-lookup"><span data-stu-id="b15b2-129">**Policies** - Surface Hub supports a subset of the policies in the [Policy configuration service provider](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies).</span></span> 
- <span data-ttu-id="b15b2-130">**設定**：您可以在 [SurfaceHub 設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)中設定任何設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-130">**Settings** - You can configure any setting in the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx).</span></span>

>[!TIP]
> <span data-ttu-id="b15b2-131">使用精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-131">Use the wizard to create a package with the common settings, then switch to the advanced editor to add other settings.</span></span>
>
>![開啟進階編輯器](images/icd-simple-edit.png)

## <a name="use-the-surface-hub-provisioning-wizard"></a><span data-ttu-id="b15b2-133">使用 Surface Hub 佈建精靈</span><span class="sxs-lookup"><span data-stu-id="b15b2-133">Use the Surface Hub provisioning wizard</span></span>

<span data-ttu-id="b15b2-134">[安裝 Windows 設定設計工具](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd) 後，您就可以建立佈建套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-134">After you [install Windows Configuration Designer](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), you can create a provisioning package.</span></span>

### <a name="create-the-provisioning-package"></a><span data-ttu-id="b15b2-135">建立佈建套件</span><span class="sxs-lookup"><span data-stu-id="b15b2-135">Create the provisioning package</span></span> 

1. <span data-ttu-id="b15b2-136">開啟 Windows 設定設定工具：</span><span class="sxs-lookup"><span data-stu-id="b15b2-136">Open Windows Configuration Designer:</span></span>
   - <span data-ttu-id="b15b2-137">從開始畫面或在 \[開始\] 功能表搜尋欄位，輸入「Windows 設定設計工具」，並按一下 Windows 設定設計工具捷徑。</span><span class="sxs-lookup"><span data-stu-id="b15b2-137">From either the Start screen or Start menu search, type 'Windows Configuration Designer' and click on the Windows Configuration Designer shortcut,</span></span> 
    
     <span data-ttu-id="b15b2-138">或</span><span class="sxs-lookup"><span data-stu-id="b15b2-138">or</span></span>
    
   - <span data-ttu-id="b15b2-139">如果您是從 ADK 安裝 Windows 設定設計工具，請瀏覽至 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (在 x64 電腦上) 或 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (在 x86 電腦上)，然後按兩下 **ICD.exe**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-139">If you installed Windows Configuration Designer from the ADK, navigate to `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (on an x64 computer) or `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (on an x86 computer), and then double-click **ICD.exe**.</span></span>

2. <span data-ttu-id="b15b2-140">按一下 **\[佈建 Surface Hub 裝置\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-140">Click **Provision Surface Hub devices**.</span></span>

3. <span data-ttu-id="b15b2-141">為您的專案命名，然後按一下 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-141">Name your project and click **Next**.</span></span>

### <a name="configure-settings"></a><span data-ttu-id="b15b2-142">進行設定</span><span class="sxs-lookup"><span data-stu-id="b15b2-142">Configure settings</span></span>

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br><span data-ttu-id="b15b2-143">若要使用憑證佈建裝置，請按一下 <strong>\[新增憑證\]</strong>。</span><span class="sxs-lookup"><span data-stu-id="b15b2-143">To provision the device with a certificate, click <strong>Add a certificate</strong>.</span></span> <span data-ttu-id="b15b2-144">輸入憑證的名稱，然後瀏覽至要使用的憑證並加以選取。</span><span class="sxs-lookup"><span data-stu-id="b15b2-144">Enter a name for the certificate, and then browse to and select the certificate to be used.</span></span></td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br><span data-ttu-id="b15b2-145">將 Proxy 設定切換為 <strong>\[是\]</strong> 或 <strong>\[否\]</strong>。</span><span class="sxs-lookup"><span data-stu-id="b15b2-145">Toggle <strong>Yes</strong> or <strong>No</strong> for proxy settings.</span></span> <span data-ttu-id="b15b2-146">Surface Hub 的預設設定為自動偵測 Proxy 設定，因此如果這是您要的設定，您可以選取 <strong>\[否\]</strong>。</span><span class="sxs-lookup"><span data-stu-id="b15b2-146">The default configuration for Surface Hub is to automatically detect proxy settings, so you can select <strong>No</strong> if that is the setting that you want.</span></span> <span data-ttu-id="b15b2-147">不過，如果您的基礎結構過去需要使用 Proxy 伺服器，但已變更為不需要 Proxy 伺服器，您可以選取 <strong>\[是\]</strong> 和 <strong>\[自動偵測設定\]</strong>，使用佈建套件將 Surface Hub 裝置還原回預設設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-147">However, if your infrastructure previously required using a proxy server and has changed to not require a proxy server, you can use a provisioning package to revert your Surface Hub devices to the default settings by selecting <strong>Yes</strong> and <strong>Automatically detect settings</strong>.</span></span> </br></br><span data-ttu-id="b15b2-148">如果您切換為 <strong>\[是\]</strong>，您可以選擇自動偵測 Proxy 設定，或者您可以輸入 URL 安裝指令碼或靜態 Proxy 伺服器位址以手動設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-148">If you toggle <strong>Yes</strong>, you can select to automatically detect proxy settings, or you can manually configure the settings by entering a URL to a setup script, or a static proxy server address.</span></span> <span data-ttu-id="b15b2-149">您也可以辨識是否要使用 Proxy 伺服器做為本機位址，並輸入例外狀況 (亦即 Surface Hub 不使用 Proxy 伺服器而直接連線的位址)。</span><span class="sxs-lookup"><span data-stu-id="b15b2-149">You can also identify whether to use the proxy server for local addresses, and enter exceptions (addresses that Surface Hub should connect to directly without using the proxy server).</span></span>  </td><td><img src="images/proxy-details.png" alt="proxy configuration details"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br><span data-ttu-id="b15b2-150">您可以在 Active Directory 中註冊裝置，並指定安全性群組使用「設定」應用程式、註冊 Azure Active Directory 以允許全域系統管理員使用「設定」應用程式，或在裝置上建立本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="b15b2-150">You can enroll the device in Active Directory and specify a security group to use the Settings app, enroll in Azure Active Directory to allow global admins to use the Settings app, or create a local administrator account on the device.</span></span></br></br><span data-ttu-id="b15b2-151">若要在 Active Directory 中註冊裝置，請輸入最低權限使用者帳戶的認證以將裝置加入網域，並指定該安全性群組在 Surface Hub 上擁有系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="b15b2-151">To enroll the device in Active Directory, enter the credentials for a least-privileged user account to join the device to the domain, and specify the security group to have admin credentials on Surface Hub.</span></span> <span data-ttu-id="b15b2-152">當註冊 Active Directory 裝置的佈建套件正套用到已重設的 Surface Hub 時，如果所列的帳戶是網域系統管理員，或是最初設定 Surface Hub 的同一個帳戶，則只會使用相同的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="b15b2-152">If a provisioning package that enrolls a device in Active Directory is going to be applied to a Surface Hub that was reset, the same domain account can only be used if the account listed is a domain administrator or is the same account that set up the Surface Hub initially.</span></span> <span data-ttu-id="b15b2-153">否則，必須在佈建套件中使用不同的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="b15b2-153">Otherwise, a different domain account must be used in the provisioning package.</span></span></br></br><span data-ttu-id="b15b2-154">在您使用 Windows 設定設計工具精靈設定大量 Azure AD 註冊前，請<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">設定 Azure AD 加入組織</a>。</span><span class="sxs-lookup"><span data-stu-id="b15b2-154">Before you use a Windows Configuration Designer wizard to configure bulk Azure AD enrollment, <a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">set up Azure AD join in your organization</a>.</span></span> <span data-ttu-id="b15b2-155">您 Azure AD 租用戶中的 <strong>\[每位使用者的裝置數目上限\]</strong> 設定決定您在精靈中使用的大量權杖可使用多少次。</span><span class="sxs-lookup"><span data-stu-id="b15b2-155">The <strong>maximum number of devices per user</strong> setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span> <span data-ttu-id="b15b2-156">若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。</span><span class="sxs-lookup"><span data-stu-id="b15b2-156">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="b15b2-157">設定權杖的到期日 (上限為自您取得權杖起的 30 天)。</span><span class="sxs-lookup"><span data-stu-id="b15b2-157">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="b15b2-158">按一下 <strong>\[Get bulk token\]</strong> (取得大量權杖)。</span><span class="sxs-lookup"><span data-stu-id="b15b2-158">Click <strong>Get bulk token</strong>.</span></span> <span data-ttu-id="b15b2-159">在&#39;中，輸入有權將裝置加入 Azure AD 的帳戶，然後輸入 <strong> </strong> 密碼。</span><span class="sxs-lookup"><span data-stu-id="b15b2-159">In the <strong>Let&#39;s get you signed in</strong> window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="b15b2-160">按一下 <strong>\[接受\]</strong> 將必要的權限授與 Windows 設定設計工具。</span><span class="sxs-lookup"><span data-stu-id="b15b2-160">Click <strong>Accept</strong> to give Windows Configuration Designer the necessary permissions.</span></span></br></br><span data-ttu-id="b15b2-161">若要建立本機系統管理員帳戶，請選取該選項，並輸入使用者名稱與密碼。</span><span class="sxs-lookup"><span data-stu-id="b15b2-161">To create a local administrator account, select that option and enter a user name and password.</span></span> </br></br><strong><span data-ttu-id="b15b2-162">重要：</strong>如果您在佈建套件中建立本機帳戶，您必須使用 <strong>\[設定\] </strong>應用程式每隔 42 天變更一次密碼。</span><span class="sxs-lookup"><span data-stu-id="b15b2-162">Important:</strong> If you create a local account in the provisioning package, you must change the password using the <strong>Settings</strong> app every 42 days.</span></span> <span data-ttu-id="b15b2-163">如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。</span><span class="sxs-lookup"><span data-stu-id="b15b2-163">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br><span data-ttu-id="b15b2-164">使用本節註冊 Intune 以外 MDM 提供者。</span><span class="sxs-lookup"><span data-stu-id="b15b2-164">Use this section to enroll in MDM providers besides Intune.</span></span> <span data-ttu-id="b15b2-165">針對 Intune 註冊，請使用上一節中的 Azure AD 加入，並 <a href="https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment" data-raw-source="[automatic Intune enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)"> 自動註冊 </a> Intune。</span><span class="sxs-lookup"><span data-stu-id="b15b2-165">For Intune enrollment, use Azure AD join in the previous section with <a href="https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment" data-raw-source="[automatic Intune enrollment](https://docs.microsoft.com/mem/intune/enrollment/windows-enroll#enable-windows-10-automatic-enrollment)">automatic Intune enrollment</a>.</span></span></br></br><span data-ttu-id="b15b2-166">將 MDM 中的註冊切換為 <strong>\[是\]</strong> 或 <strong>\[否\]</strong>。</span><span class="sxs-lookup"><span data-stu-id="b15b2-166">Toggle <strong>Yes</strong> or <strong>No</strong> for enrollment in MDM.</span></span> </br></br><span data-ttu-id="b15b2-167">如果您切換為 <strong>\[是\]</strong>，則必須提供服務帳戶和密碼，或經授權註冊裝置的憑證指紋，此外也必須指定驗證類型。</span><span class="sxs-lookup"><span data-stu-id="b15b2-167">If you toggle <strong>Yes</strong>, you must provide a service account and password or certificate thumbprint that is authorized to enroll the device, and also specify the authentication type.</span></span> <span data-ttu-id="b15b2-168">如果您的 MDM 提供者需要，亦請輸入探索服務、註冊服務及原則服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="b15b2-168">If required by your MDM provider, also enter the URLs for the discovery service, enrollment service, and policy service.</span></span> <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)"><span data-ttu-id="b15b2-169">深入了解使用 MDM 管理 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="b15b2-169">Learn more about managing Surface Hub with MDM.</span></span></a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br><span data-ttu-id="b15b2-170">您可以在佈建套件中安裝多個通用 Windows 平台 (UWP) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="b15b2-170">You can install multiple Universal Windows Platform (UWP) apps in a provisioning package.</span></span> <span data-ttu-id="b15b2-171">如需設定方面的協助，請參閱<a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">使用應用程式佈建電腦</a> (英文)。</span><span class="sxs-lookup"><span data-stu-id="b15b2-171">For help with the settings, see <a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">Provision PCs with apps</a>.</span></span> </br></br><strong><span data-ttu-id="b15b2-172">重要： </strong> 雖然精靈介面可讓您選取傳統 Win32 應用程式，但只會將 UWP 應用程式納入要套用至 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="b15b2-172">Important:</strong> Although the wizard interface allows you to select a Classic Win32 app, only include UWP apps in a provisioning package that will be applied to Surface Hub.</span></span> <span data-ttu-id="b15b2-173">如果您包含傳統型 Win32 應用程式，佈建將會失敗。</span><span class="sxs-lookup"><span data-stu-id="b15b2-173">If you include a Classic Win32 app, provisioning will fail.</span></span> </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br><span data-ttu-id="b15b2-174">您&#39;此步驟中設定任何設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-174">You don&#39;t configure any settings in this step.</span></span> <span data-ttu-id="b15b2-175">它會提供指示以包含內含裝置帳戶清單的設定檔。</span><span class="sxs-lookup"><span data-stu-id="b15b2-175">It provides instructions for including a configuration file that contains a list of device accounts.</span></span> <span data-ttu-id="b15b2-176">設定檔不得包含欄標頭。</span><span class="sxs-lookup"><span data-stu-id="b15b2-176">The configuration file must not contain column headers.</span></span> <span data-ttu-id="b15b2-177">當您將佈建套件套用到 Surface Hub 時，如果 USB 磁碟機上包含 Surface Hub 設定檔，您可以從檔案中選取帳戶及裝置的易記名稱。</span><span class="sxs-lookup"><span data-stu-id="b15b2-177">When you apply the provisioning package to Surface Hub, if a Surface Hub configuration file is included on the USB drive, you can select the account and friendly name for the device from the file.</span></span> <span data-ttu-id="b15b2-178">請參閱<a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">範例設定檔</a>中的範例。</span><span class="sxs-lookup"><span data-stu-id="b15b2-178">See <a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">Sample configuration file</a> for an example.</span></span></br></br><strong><span data-ttu-id="b15b2-179">重要：設定檔只能在開箱即用設定體驗期間 (OOBE) 套用，且只能用於使用 Windows 10 版本 1703 中發行之 Windows 組組設計工具所建立布備 </strong> 套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-179">Important:</strong> The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.</span></span>  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish creating your package"/></br></br><span data-ttu-id="b15b2-180">您可以設定密碼保護您的佈建套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-180">You can set a password to protect your provisioning package.</span></span> <span data-ttu-id="b15b2-181">當您將佈建套件套用到裝置上時，您必須輸入此密碼。</span><span class="sxs-lookup"><span data-stu-id="b15b2-181">You must enter this password when you apply the provisioning package to a device.</span></span></td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

<span data-ttu-id="b15b2-182">完成時按一下 **\[建立\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-182">After you're done, click **Create**.</span></span> <span data-ttu-id="b15b2-183">只需要幾秒鐘。</span><span class="sxs-lookup"><span data-stu-id="b15b2-183">It only takes a few seconds.</span></span> <span data-ttu-id="b15b2-184">套件建置時，儲存套件的位置會在頁面底端顯示成超連結。</span><span class="sxs-lookup"><span data-stu-id="b15b2-184">When the package is built, the location where the package is stored is displayed as a hyperlink at the bottom of the page.</span></span>

## <a name="sample-configuration-file"></a><span data-ttu-id="b15b2-185">範例設定檔</span><span class="sxs-lookup"><span data-stu-id="b15b2-185">Sample configuration file</span></span>

<span data-ttu-id="b15b2-186">Surface Hub 設定檔包含您的裝置可用來與 Exchange 和商務用 Skype 連線的裝置帳戶清單。</span><span class="sxs-lookup"><span data-stu-id="b15b2-186">A Surface Hub configuration file contains a list of device accounts that your device can use to connect to Exchange and Skype for Business.</span></span> <span data-ttu-id="b15b2-187">當您將佈建套件套用到 Surface Hub 時，您就可以在 USB 快閃磁碟機的根目錄中包括設定檔，然後選取所需的帳戶套用至該磁碟機。</span><span class="sxs-lookup"><span data-stu-id="b15b2-187">When you apply a provisioning package to Surface Hub, you can include a configuration file in the root directory of the USB flash drive, and then select the desired account to apply to that device.</span></span> <span data-ttu-id="b15b2-188">設定檔只會在全新安裝體驗 (OOBE) 期間套用，且只能與使用隨 Windows 10 (版本 1703) 發行的 Windows 設定設計工具所建立的佈建套件搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b15b2-188">The configuration file can only be applied during the out-of-box setup experience (OOBE) and can only be used with provisioning packages created using the Windows Configuration Designer released with Windows 10, version 1703.</span></span>

<span data-ttu-id="b15b2-189">使用 Microsoft Excel 或其他 CSV 編輯器建立名為 `SurfaceHubConfiguration.csv` 的 CSV 檔。</span><span class="sxs-lookup"><span data-stu-id="b15b2-189">Use Microsoft Excel or other CSV editor to create a CSV file named `SurfaceHubConfiguration.csv`.</span></span> <span data-ttu-id="b15b2-190">在該檔案中，以下列格式輸入裝置帳戶及易記名稱清單︰</span><span class="sxs-lookup"><span data-stu-id="b15b2-190">In the file, enter a list of device accounts and friendly names in this format:</span></span>

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
><span data-ttu-id="b15b2-191">由於設定檔會以純文字儲存裝置帳戶密碼，因此建議您將佈建套件套用到您的裝置後，請更新密碼。</span><span class="sxs-lookup"><span data-stu-id="b15b2-191">Because the configuration file stores the device account passwords in plaintext, we recommend that you update the passwords after you've applied the provisioning package to your devices.</span></span> <span data-ttu-id="b15b2-192">您可以使用 [Surface Hub 設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) 中的 [DeviceAccount 節點](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount)，來透過 MDM 更新密碼。</span><span class="sxs-lookup"><span data-stu-id="b15b2-192">You can use the [DeviceAccount node](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount) in the [Surface Hub configuration service provider (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) to update the passwords via MDM.</span></span>


<span data-ttu-id="b15b2-193">以下為 `SurfaceHubConfiguration.csv` 的範例。</span><span class="sxs-lookup"><span data-stu-id="b15b2-193">The following is an example of `SurfaceHubConfiguration.csv`.</span></span> 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## <a name="use-advanced-provisioning"></a><span data-ttu-id="b15b2-194">使用進階佈建</span><span class="sxs-lookup"><span data-stu-id="b15b2-194">Use advanced provisioning</span></span>

<span data-ttu-id="b15b2-195">[安裝 Windows 設定設計工具](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd) 後，您就可以建立佈建套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-195">After you [install Windows Configuration Designer](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd), you can create a provisioning package.</span></span>

### <a name="create-the-provisioning-package-advanced"></a><span data-ttu-id="b15b2-196">建立佈建套件 (進階)</span><span class="sxs-lookup"><span data-stu-id="b15b2-196">Create the provisioning package (advanced)</span></span>

1. <span data-ttu-id="b15b2-197">開啟 Windows 設定設定工具：</span><span class="sxs-lookup"><span data-stu-id="b15b2-197">Open Windows Configuration Designer:</span></span>
   - <span data-ttu-id="b15b2-198">從開始畫面或在 \[開始\] 功能表搜尋欄位，輸入「Windows 設定設計工具」，並按一下 Windows 設定設計工具捷徑。</span><span class="sxs-lookup"><span data-stu-id="b15b2-198">From either the Start screen or Start menu search, type 'Windows Configuration Designer' and click on the Windows Configuration Designer shortcut,</span></span> 
    
     <span data-ttu-id="b15b2-199">或</span><span class="sxs-lookup"><span data-stu-id="b15b2-199">or</span></span>
    
   - <span data-ttu-id="b15b2-200">如果您是從 ADK 安裝 Windows 設定設計工具，請瀏覽至 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (在 x64 電腦上) 或 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (在 x86 電腦上)，然後按兩下 **ICD.exe**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-200">If you installed Windows Configuration Designer from the ADK, navigate to `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (on an x64 computer) or `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (on an x86 computer), and then double-click **ICD.exe**.</span></span>

2. <span data-ttu-id="b15b2-201">按一下 **\[進階佈建\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-201">Click **Advanced provisioning**.</span></span>
   
3. <span data-ttu-id="b15b2-202">為您的專案命名，然後按一下 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-202">Name your project and click **Next**.</span></span>

4. <span data-ttu-id="b15b2-203">選取 **[常用Windows 10 團隊版，\*\*\*\*按一下**[下一步，然後按一下 **[完成**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-203">Select **Common to Windows 10 Team**, click **Next**, and then click **Finish**.</span></span>

    ![ICD 新專案](images/icd-new-project.png)

5. <span data-ttu-id="b15b2-205">在專案中的可用 **自訂項下**，選取 **共同小組設定**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-205">In the project, under **Available customizations**, select **Common Team settings**.</span></span>

    ![ICD 通用設定](images/icd-common-settings.png)


### <a name="add-a-certificate-to-your-package"></a><span data-ttu-id="b15b2-207">將憑證新增到您的套件</span><span class="sxs-lookup"><span data-stu-id="b15b2-207">Add a certificate to your package</span></span>
<span data-ttu-id="b15b2-208">您可以使用佈建套件來安裝憑證，讓裝置可向 Microsoft Exchange 驗證。</span><span class="sxs-lookup"><span data-stu-id="b15b2-208">You can use provisioning packages to install certificates that will allow the device to authenticate to Microsoft Exchange.</span></span>

> [!NOTE]
> <span data-ttu-id="b15b2-209">佈建套件只能將憑證安裝到裝置 (本機電腦) 存放區，不能安裝到使用者存放區。</span><span class="sxs-lookup"><span data-stu-id="b15b2-209">Provisioning packages can only install certificates to the device (local machine) store, and not to the user store.</span></span> <span data-ttu-id="b15b2-210">如果貴組織要求將憑證安裝至使用者市集，您可以使用 Hub &\*\*\*\* 應用程式之 **& 安全性**憑證區段的 設定  >  \*\*\*\* 按鈕。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b15b2-210">If your organization requires that certificates be installed to the user store, you can use the **Import Certificate** button in the **Update & Security** > **Certificates** section of Hub's **Settings** app.</span></span> <span data-ttu-id="b15b2-211">或者， [行動裝置管理 (MDM](manage-settings-with-mdm-for-surface-hub.md)) 可以使用將憑證部署到裝置存放區或使用者存放區。</span><span class="sxs-lookup"><span data-stu-id="b15b2-211">Alternatively, [Mobile Device Management (MDM) policies](manage-settings-with-mdm-for-surface-hub.md) can be used deploy certificates to either the device store or the user store.</span></span>

1. <span data-ttu-id="b15b2-212">在 \[可用的自訂項目\] 窗格中，移至 \[執行階段設定\] > \[憑證\] > \[ClientCertificates\]。\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b15b2-212">In the **Available customizations** pane, go to **Runtime settings** > **Certificates** > **ClientCertificates**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="b15b2-213">**ClientCertificates**區段適用于具有私密金鑰的 .pfx 檔案;根 CA 的 .cer 檔案應放在**RootCertificates**區段，而針對**CACertificates**區段的中級 CA。</span><span class="sxs-lookup"><span data-stu-id="b15b2-213">The **ClientCertificates** section is for .pfx files with a private key; .cer files for root CAs should be placed in the **RootCertificates** section and for Intermediate CAs in the **CACertificates** section.</span></span>

2. <span data-ttu-id="b15b2-214">輸入 **CertificateName 卷** 標，然後按一下 [ **新增**] 。</span><span class="sxs-lookup"><span data-stu-id="b15b2-214">Enter a label for **CertificateName** and then click **Add**.</span></span> 

2. <span data-ttu-id="b15b2-215">輸入 **CertificatePassword**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-215">Enter the **CertificatePassword**.</span></span> 

3. <span data-ttu-id="b15b2-216">針對 **[CertificatePath]**，瀏覽並選取要使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="b15b2-216">For **CertificatePath**, browse and select the certificate.</span></span> 

4. <span data-ttu-id="b15b2-217">將 **[ExportCertificate]** 設定為 **[False]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-217">Set **ExportCertificate** to **False**.</span></span>

5. <span data-ttu-id="b15b2-218">針對 **[KeyLocation]**，選取 **[僅限軟體]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-218">For **KeyLocation**, select **Software only**.</span></span>


### <a name="add-a-universal-windows-platform-uwp-app-to-your-package"></a><span data-ttu-id="b15b2-219">將通用 Windows 平台 (UWP) 應用程式新增到套件</span><span class="sxs-lookup"><span data-stu-id="b15b2-219">Add a Universal Windows Platform (UWP) app to your package</span></span>
<span data-ttu-id="b15b2-220">在將 UWP應用程式新增到佈建套件之前，您需要應用程式套件 (.appx 或 .appxbundle) 和任何的相依性檔案。</span><span class="sxs-lookup"><span data-stu-id="b15b2-220">Before adding a UWP app to a provisioning package, you need the app package (either an .appx, or .appxbundle) and any dependency files.</span></span> <span data-ttu-id="b15b2-221">如果您從商務用 Microsoft Store 取得應用程式，您也需要*未編碼的*應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="b15b2-221">If you acquired the app from the Microsoft Store for Business, you will also need the *unencoded* app license.</span></span> <span data-ttu-id="b15b2-222">請參閱[散發離線應用程式](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) (英文) 以了解如何從商務用 Microsoft Store 下載這些項目。</span><span class="sxs-lookup"><span data-stu-id="b15b2-222">See [Distribute offline apps](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) to learn how to download these items from the Microsoft Store for Business.</span></span>

1. <span data-ttu-id="b15b2-223">在 **\[可用的自訂項目\]** 窗格中，移至\*\* \[執行階段設定\]\*\* > **\[UniversalAppInstall\]** > **\[DeviceContextApp\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-223">In the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextApp**.</span></span>

2. <span data-ttu-id="b15b2-224">針對應用程式輸入 **PackageFamilyName**，然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-224">Enter a **PackageFamilyName** for the app and then click **Add**.</span></span> <span data-ttu-id="b15b2-225">為了保持一致性，請使用應用程式的套件系列名稱。</span><span class="sxs-lookup"><span data-stu-id="b15b2-225">For consistency, use the app's package family name.</span></span> <span data-ttu-id="b15b2-226">如果您從商務用 Microsoft Store 取得應用程式，您可以在應用程式授權中找到套件系列名稱。</span><span class="sxs-lookup"><span data-stu-id="b15b2-226">If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license.</span></span> <span data-ttu-id="b15b2-227">使用文字編輯器開啟授權檔案，並使用 ... 標記之間的 \<PFM\> \</PFM\> 值。</span><span class="sxs-lookup"><span data-stu-id="b15b2-227">Open the license file using a text editor, and use the value between the \<PFM\>...\</PFM\> tags.</span></span>

3. <span data-ttu-id="b15b2-228">針對 \[ApplicationFile\]，按一下 \[瀏覽\] 來尋找並選取目標 app (\*.appx 或 \*.appxbundle)。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b15b2-228">For **ApplicationFile**, click **Browse** to find and select the target app (either an \*.appx or \*.appxbundle).</span></span>

4. <span data-ttu-id="b15b2-229">針對 **[DependencyAppxFiles]**，按一下 **[瀏覽]** 來尋找並新增應用程式的任何相依性。</span><span class="sxs-lookup"><span data-stu-id="b15b2-229">For **DependencyAppxFiles**, click **Browse** to find and add any dependencies for the app.</span></span> <span data-ttu-id="b15b2-230">針對 Surface Hub，您將僅需要這些相依性的 x64 版本。</span><span class="sxs-lookup"><span data-stu-id="b15b2-230">For Surface Hub, you will only need the x64 versions of these dependencies.</span></span>

<span data-ttu-id="b15b2-231">如果您從商務用 Microsoft Store 取得應用程式，您也需要將應用程式授權新增到佈建套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-231">If you acquired the app from the Microsoft Store for Business, you will also need to add the app license to your provisioning package.</span></span>

1. <span data-ttu-id="b15b2-232">建立應用程式授權的複本，然後將它重新命名為使用 **.ms-windows-store-license** 副檔名。</span><span class="sxs-lookup"><span data-stu-id="b15b2-232">Make a copy of the app license, and rename it to use a **.ms-windows-store-license** extension.</span></span> <span data-ttu-id="b15b2-233">例如，"example.xml" 會變成 "example.ms-windows-store-license"。</span><span class="sxs-lookup"><span data-stu-id="b15b2-233">For example, "example.xml" becomes "example.ms-windows-store-license".</span></span>

2. <span data-ttu-id="b15b2-234">在 ICD 中，於 **[可用的自訂項目]** 窗格中，移至 **[執行階段設定]** > **[UniversalAppInstall]** > **[DeviceContextAppLicense]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-234">In ICD, in the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextAppLicense**.</span></span>

3. <span data-ttu-id="b15b2-235">輸入 **LicenseProductId** 然後按一下 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-235">Enter a **LicenseProductId** and then click **Add**.</span></span> <span data-ttu-id="b15b2-236">為了保持一致性，請使用應用程式授權中的應用程式授權識別碼。</span><span class="sxs-lookup"><span data-stu-id="b15b2-236">For consistency, use the app's license ID from the app license.</span></span> <span data-ttu-id="b15b2-237">使用文字編輯器開啟授權檔案。</span><span class="sxs-lookup"><span data-stu-id="b15b2-237">Open the license file using a text editor.</span></span> <span data-ttu-id="b15b2-238">接著，在 \<License\> 標記中，使用 **LicenseID 屬性中的** 值。</span><span class="sxs-lookup"><span data-stu-id="b15b2-238">Then, in the \<License\> tag, use the value in the **LicenseID** attribute.</span></span>

4. <span data-ttu-id="b15b2-239">選取新的 **[LicenseProductId]** 節點。</span><span class="sxs-lookup"><span data-stu-id="b15b2-239">Select the new **LicenseProductId** node.</span></span> <span data-ttu-id="b15b2-240">針對 **[LicenseInstall]**，按一下 **[瀏覽]** 來尋找並選取您在步驟 1 中重新命名的授權檔案。</span><span class="sxs-lookup"><span data-stu-id="b15b2-240">For **LicenseInstall**, click **Browse** to find and select the license file that you renamed in Step 1.</span></span>


### <a name="add-a-policy-to-your-package"></a><span data-ttu-id="b15b2-241">新增原則至套件</span><span class="sxs-lookup"><span data-stu-id="b15b2-241">Add a policy to your package</span></span>
<span data-ttu-id="b15b2-242">Surface Hub 支援[原則設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)中一部分的原則。</span><span class="sxs-lookup"><span data-stu-id="b15b2-242">Surface Hub supports a subset of the policies in the [Policy configuration service provider](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx).</span></span> <span data-ttu-id="b15b2-243">其中一些原則可使用 ICD 進行設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-243">Some of those policies can be configured with ICD.</span></span>

1. <span data-ttu-id="b15b2-244">在 **[可用的自訂項目]** 窗格中，移至 **[執行階段設定]** > **[原則]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-244">In the **Available customizations** pane, go to **Runtime settings** > **Policies**.</span></span>

2. <span data-ttu-id="b15b2-245">選取其中一個可用的原則區域。</span><span class="sxs-lookup"><span data-stu-id="b15b2-245">Select one of the available policy areas.</span></span>

3. <span data-ttu-id="b15b2-246">選取您要新增至佈建套件的原則並加以設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-246">Select and set the policy you want to add to your provisioning package.</span></span>


### <a name="add-surface-hub-settings-to-your-package"></a><span data-ttu-id="b15b2-247">將 Surface Hub 設定新增至套件</span><span class="sxs-lookup"><span data-stu-id="b15b2-247">Add Surface Hub settings to your package</span></span> 

<span data-ttu-id="b15b2-248">您可以從 [SurfaceHub 設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)將設定新增到佈建套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-248">You can add settings from the [SurfaceHub configuration service provider](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) to your provisioning package.</span></span> 

1. <span data-ttu-id="b15b2-249">在可用**自訂窗格中**，前往**執行時間設定**  >  **SurfaceHub**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-249">In the **Available customizations** pane, go to **Runtime settings** > **SurfaceHub**.</span></span>

2. <span data-ttu-id="b15b2-250">選取其中一個可用的設定區域。</span><span class="sxs-lookup"><span data-stu-id="b15b2-250">Select one of the available setting areas.</span></span>

3. <span data-ttu-id="b15b2-251">選取您要新增至佈建套件的設定並加以設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-251">Select and set the setting you want to add to your provisioning package.</span></span> 


## <a name="build-your-package"></a><span data-ttu-id="b15b2-252">建置您的套件</span><span class="sxs-lookup"><span data-stu-id="b15b2-252">Build your package</span></span>

1. <span data-ttu-id="b15b2-253">當您完成佈建套件設定作業之後，請按一下 \[檔案\] 功能表上的 \[儲存\]。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b15b2-253">When you are done configuring the provisioning package, on the **File** menu, click **Save**.</span></span>

2. <span data-ttu-id="b15b2-254">閱讀專案檔案可能包含機密資訊的警告，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-254">Read the warning that project files may contain sensitive information, and click **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b15b2-255">當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="b15b2-255">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="b15b2-256">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="b15b2-256">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span> <span data-ttu-id="b15b2-257">您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。</span><span class="sxs-lookup"><span data-stu-id="b15b2-257">You should store the project files in a secure location and delete the project files when they are no longer needed.</span></span>

3. <span data-ttu-id="b15b2-258">在\*\* \[匯出\] \*\*功能表上，按一下 **\[佈建套件\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-258">On the **Export** menu, click **Provisioning package**.</span></span>

4. <span data-ttu-id="b15b2-259">將 **[擁有者]** 變更為 **[IT 系統管理員]**，它會設定這個佈建套件的優先順序高於從其他來源套用到這個裝置的佈建套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-259">Change **Owner** to **IT Admin**, which will set the precedence of this provisioning package higher than provisioning packages applied to this device from other sources.</span></span>

5. <span data-ttu-id="b15b2-260">設定 **[套件版本]** 的值，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-260">Set a value for **Package Version**, and then select **Next.**</span></span>

    > [!TIP]
    > <span data-ttu-id="b15b2-261">您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-261">You can make changes to existing packages and change the version number to update previously applied packages.</span></span>

6. <span data-ttu-id="b15b2-262">選用：您可以選擇加密套件並啟用套件簽署。</span><span class="sxs-lookup"><span data-stu-id="b15b2-262">Optional: You can choose to encrypt the package and enable package signing.</span></span>

    -   <span data-ttu-id="b15b2-263">**啟用套件加密** - 如果您選擇此選項，畫面上會顯示自動產生的密碼。</span><span class="sxs-lookup"><span data-stu-id="b15b2-263">**Enable package encryption** - If you select this option, an auto-generated password will be shown on the screen.</span></span>

    -   <span data-ttu-id="b15b2-264">**啟用套件簽署**：如果您選取此選項，您必須選取有效的憑證以簽署套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-264">**Enable package signing** - If you select this option, you must select a valid certificate to use for signing the package.</span></span> <span data-ttu-id="b15b2-265">您可以按一下 **[瀏覽...]** 來指定憑證，並選擇您想要用來簽署套件的憑證。</span><span class="sxs-lookup"><span data-stu-id="b15b2-265">You can specify the certificate by clicking **Browse...** and choosing the certificate you want to use to sign the package.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="b15b2-266">我們建議您在佈建套件中包含受信任的佈建憑證。</span><span class="sxs-lookup"><span data-stu-id="b15b2-266">We recommend that you include a trusted provisioning certificate in your provisioning package.</span></span> <span data-ttu-id="b15b2-267">將套件套用到裝置時，即會將憑證加入系統存放區，而且使用該憑證簽署的任何套件之後就能以無訊息方式套用。</span><span class="sxs-lookup"><span data-stu-id="b15b2-267">When the package is applied to a device, the certificate is added to the system store and any package signed with that certificate thereafter can be applied silently.</span></span> 

7. <span data-ttu-id="b15b2-268">按 \[下一步\]，以指定佈建套件建置後的輸出位置。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="b15b2-268">Click **Next** to specify the output location where you want the provisioning package to go once it's built.</span></span> <span data-ttu-id="b15b2-269">Windows ICD 是預設使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="b15b2-269">By default, Windows ICD uses the project folder as the output location.</span></span><p>
<span data-ttu-id="b15b2-270">您也可以按一下 **\[瀏覽\]** 來變更預設的輸出位置。</span><span class="sxs-lookup"><span data-stu-id="b15b2-270">Optionally, you can click **Browse** to change the default output location.</span></span>

8. <span data-ttu-id="b15b2-271">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-271">Click **Next**.</span></span>

9. <span data-ttu-id="b15b2-272">按一下 **\[建置\]**，開始建置套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-272">Click **Build** to start building the package.</span></span> <span data-ttu-id="b15b2-273">專案資訊會顯示在建置頁面，進度列可指示建置狀態。</span><span class="sxs-lookup"><span data-stu-id="b15b2-273">The project information is displayed in the build page and the progress bar indicates the build status.</span></span><p>
<span data-ttu-id="b15b2-274">若要取消建置，請按一下 [取消] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b15b2-274">If you need to cancel the build, click **Cancel**.</span></span> <span data-ttu-id="b15b2-275">這會取消目前的建置程序、關閉精靈，並回到 [自訂項目頁面] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b15b2-275">This cancels the current build process, closes the wizard, and takes you back to the **Customizations Page**.</span></span>

10. <span data-ttu-id="b15b2-276">若建置失敗，就會顯示錯誤訊息，其中包含專案資料夾的連結。</span><span class="sxs-lookup"><span data-stu-id="b15b2-276">If your build fails, an error message will show up that includes a link to the project folder.</span></span> <span data-ttu-id="b15b2-277">您可以掃描記錄檔，以判斷造成錯誤的原因。</span><span class="sxs-lookup"><span data-stu-id="b15b2-277">You can scan the logs to determine what caused the error.</span></span> <span data-ttu-id="b15b2-278">修正問題後，請嘗試重新建置套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-278">Once you fix the issue, try building the package again.</span></span><p>
<span data-ttu-id="b15b2-279">若建置成功，便會顯示佈建套件名稱、輸出目錄，以及專案目錄。</span><span class="sxs-lookup"><span data-stu-id="b15b2-279">If your build is successful, the name of the provisioning package, output directory, and project directory will be shown.</span></span>

    -   <span data-ttu-id="b15b2-280">您也可以選擇再次建置佈建套件，並為輸出套件挑選不同的路徑。</span><span class="sxs-lookup"><span data-stu-id="b15b2-280">If you choose, you can build the provisioning package again and pick a different path for the output package.</span></span> <span data-ttu-id="b15b2-281">若要如此，請按一下 **\[返回\]** 以變更輸出套件名稱與路徑，然後按 **\[下一步\]** 以開始另一次建置。</span><span class="sxs-lookup"><span data-stu-id="b15b2-281">To do this, click **Back** to change the output package name and path, and then click **Next** to start another build.</span></span>
    
    -   <span data-ttu-id="b15b2-282">完成後，按一下 \[完成\]\*\*\*\* 以關閉精靈，並回到 \[自訂頁面\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b15b2-282">If you are done, click **Finish** to close the wizard and go back to the **Customizations Page**.</span></span>

11. <span data-ttu-id="b15b2-283">選取 **[輸出位置]** 連結，以移至套件的位置。</span><span class="sxs-lookup"><span data-stu-id="b15b2-283">Select the **output location** link to go to the location of the package.</span></span> <span data-ttu-id="b15b2-284">將 .ppkg 複製到空的 USB 快閃磁碟機。</span><span class="sxs-lookup"><span data-stu-id="b15b2-284">Copy the .ppkg to an empty USB flash drive.</span></span>


## <a name="apply-a-provisioning-package-to-surface-hub"></a><span data-ttu-id="b15b2-285">將佈建套件套用到 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="b15b2-285">Apply a provisioning package to Surface Hub</span></span>

<span data-ttu-id="b15b2-286">將佈建套件部署至 Surface Hub 有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="b15b2-286">There are two options for deploying provisioning packages to a Surface Hub.</span></span> <span data-ttu-id="b15b2-287">[在第一](#apply-a-provisioning-package-during-first-run)次執行精靈期間，您可以套用安裝憑證的設定套件，或在首次執行的程式完成後，使用 設定 套用設定[、應用程式和憑證的設定套件](#apply-a-package-using-settings)。</span><span class="sxs-lookup"><span data-stu-id="b15b2-287">[During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-package-using-settings).</span></span> 


### <a name="apply-a-provisioning-package-during-first-run"></a><span data-ttu-id="b15b2-288">在初次執行期間套用佈建套件</span><span class="sxs-lookup"><span data-stu-id="b15b2-288">Apply a provisioning package during first run</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b15b2-289">在第一次執行程式期間，您只能使用部署套件來安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="b15b2-289">During the first-run program, you can only use provisioning packages to install certificates.</span></span> <span data-ttu-id="b15b2-290">使用 **[設定]** 應用程式安裝應用程式並套用其他設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-290">Use the **Settings** app to install apps and apply other settings.</span></span>

1. <span data-ttu-id="b15b2-291">當您第一次開啟 Surface Hub 時，初次執行程式將會顯示 [**[嗨，您好]** 頁面](first-run-program-surface-hub.md#first-page)。</span><span class="sxs-lookup"><span data-stu-id="b15b2-291">When you turn on the Surface Hub for the first time, the first-run program will display the [**Hi there page**](first-run-program-surface-hub.md#first-page).</span></span> <span data-ttu-id="b15b2-292">繼續之前，請確定已進行適當設定。</span><span class="sxs-lookup"><span data-stu-id="b15b2-292">Make sure that the settings are properly configured before proceeding.</span></span>

2. <span data-ttu-id="b15b2-293">將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="b15b2-293">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span> <span data-ttu-id="b15b2-294">如果套件位於磁碟機的根目錄中，初次執行程式將會識別它，並詢問您是否要設定裝置。</span><span class="sxs-lookup"><span data-stu-id="b15b2-294">If the package is in the root directory of the drive, the first-run program will recognize it and ask if you want to set up the device.</span></span> <span data-ttu-id="b15b2-295">選取 **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-295">Select **Set up**.</span></span>

    ![設定裝置？](images/provisioningpackageoobe-01.png)

3. <span data-ttu-id="b15b2-297">下一個畫面會要求您選取佈建來源。</span><span class="sxs-lookup"><span data-stu-id="b15b2-297">The next screen asks you to select a provisioning source.</span></span> <span data-ttu-id="b15b2-298">選取 \[抽取式媒體\]\*\*\*\* 並點選 \[下一步\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b15b2-298">Select **Removable Media** and tap **Next**.</span></span>

    ![佈建此裝置](images/provisioningpackageoobe-02.png)
    
4. <span data-ttu-id="b15b2-300">選取您要套用的佈建套件 (\*.ppkg)，然後點選 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-300">Select the provisioning package (\*.ppkg) that you want to apply, and tap **Next**.</span></span> <span data-ttu-id="b15b2-301">請注意，您在初次執行期間只能安裝一個套件。</span><span class="sxs-lookup"><span data-stu-id="b15b2-301">Note that you can only install one package during first run.</span></span>

    ![選擇套件](images/provisioningpackageoobe-03.png)

5. <span data-ttu-id="b15b2-303">初次執行程式會向您顯示佈建套件將套用的變更摘要。</span><span class="sxs-lookup"><span data-stu-id="b15b2-303">The first-run program will show you a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="b15b2-304">選取 **\[是，請將它新增\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-304">Select **Yes, add it**.</span></span>  

    ![您信任此套件嗎？](images/provisioningpackageoobe-04.png)
    
6. <span data-ttu-id="b15b2-306">如果設定檔包含在 USB 快閃磁碟機的根目錄中，您將會看到 **\[選取設定\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-306">If a configuration file is included in the root directory of the USB flash drive, you will see **Select a configuration**.</span></span> <span data-ttu-id="b15b2-307">將會顯示設定檔中的第一個裝置帳戶，以及將套用到 Surface Hub 的帳戶資訊摘要。</span><span class="sxs-lookup"><span data-stu-id="b15b2-307">The first device account in the configuration file will be shown with a summary of the account information that will be applied to the Surface Hub.</span></span>

    ![選取設定](images/ppkg-config.png)    

7. <span data-ttu-id="b15b2-309">在 **\[選取設定\]** 中，選取要套用的帳戶名稱，然後按一下 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-309">In **Select a configuration**, select the device name to apply, and then click **Next**.</span></span>

    ![選取易記的裝置名稱](images/ppkg-csv.png)
    
<span data-ttu-id="b15b2-311">佈建套件中的設定將套用到裝置上，OOBE 將會完成。</span><span class="sxs-lookup"><span data-stu-id="b15b2-311">The settings from the provisioning package will be applied to the device and OOBE will be complete.</span></span> <span data-ttu-id="b15b2-312">裝置重新開機後，您便可以移除 USB 快閃磁碟機。</span><span class="sxs-lookup"><span data-stu-id="b15b2-312">After the device restarts, you can remove the USB flash drive.</span></span>

### <a name="apply-a-package-using-settings"></a><span data-ttu-id="b15b2-313">使用 \[設定\] 套用套件</span><span class="sxs-lookup"><span data-stu-id="b15b2-313">Apply a package using Settings</span></span>

1. <span data-ttu-id="b15b2-314">將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="b15b2-314">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span>

2. <span data-ttu-id="b15b2-315">從 Surface Hub，啟動 **\[設定\]**，然後當出現提示時輸入系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="b15b2-315">From the Surface Hub, start **Settings** and enter the admin credentials when prompted.</span></span>

3. <span data-ttu-id="b15b2-316">瀏覽至 **\[Surface Hub\]** > **\[裝置管理\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-316">Navigate to **Surface Hub** > **Device management**.</span></span> <span data-ttu-id="b15b2-317">在 **\[佈建套件\]** 底下，選取 **\[新增或移除佈建套件\]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-317">Under **Provisioning packages**, select **Add or remove a provisioning package**.</span></span>

4. <span data-ttu-id="b15b2-318">選取 **[新增套件]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-318">Select **Add a package**.</span></span>

5. <span data-ttu-id="b15b2-319">選擇您的佈建套件，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-319">Choose your provisioning package and select **Add**.</span></span> <span data-ttu-id="b15b2-320">您可能要重新輸入系統管理員認證 (若看到提示)。</span><span class="sxs-lookup"><span data-stu-id="b15b2-320">You may have to re-enter the admin credentials if prompted.</span></span>

6. <span data-ttu-id="b15b2-321">您會看到佈建套件將套用的變更摘要。</span><span class="sxs-lookup"><span data-stu-id="b15b2-321">You'll see a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="b15b2-322">選取 **[是的，新增]**。</span><span class="sxs-lookup"><span data-stu-id="b15b2-322">Select **Yes, add it**.</span></span>


