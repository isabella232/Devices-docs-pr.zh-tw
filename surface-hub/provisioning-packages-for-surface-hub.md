---
title: 建立佈建套件
description: 針對 Windows 10，您可以透過佈建套件來設定使用登錄或設定服務提供者 (CSP) 的設定。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: 新增憑證, 佈建套件
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/28/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 087826a7a0cba7a47accc0d3d66714289f2ae9d2
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613948"
---
# <a name="create-provisioning-packages-for-surface-hub"></a><span data-ttu-id="f9c57-104">為應用程式建立Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f9c57-104">Create provisioning packages for Surface Hub</span></span>

<span data-ttu-id="f9c57-105">資源調配套件可讓您自動化重要功能的部署，協助在貴組織的所有 Surface Hub 中提供一致的體驗。</span><span class="sxs-lookup"><span data-stu-id="f9c57-105">Provisioning packages allow you to automate deployment of key features, helping deliver a consistent experience across all Surface Hubs in your organization.</span></span>  <span data-ttu-id="f9c57-106">在Windows上 (WCD) ，您可以完成下列工作：</span><span class="sxs-lookup"><span data-stu-id="f9c57-106">Using  Windows Configuration Designer (WCD) on a separate PC, you can complete the following tasks:</span></span>

- <span data-ttu-id="f9c57-107">註冊 Active Directory 或 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f9c57-107">Enroll in Active Directory or Azure Active Directory</span></span>
- <span data-ttu-id="f9c57-108">建立裝置系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="f9c57-108">Create a device administrator account</span></span>
- <span data-ttu-id="f9c57-109">新增應用程式與憑證</span><span class="sxs-lookup"><span data-stu-id="f9c57-109">Add applications and certificates</span></span>
- <span data-ttu-id="f9c57-110">設定 Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="f9c57-110">Configure proxy settings</span></span>
- <span data-ttu-id="f9c57-111">新增 Surface Hub 設定檔</span><span class="sxs-lookup"><span data-stu-id="f9c57-111">Add a Surface Hub configuration file</span></span>
- <span data-ttu-id="f9c57-112">設定 [設定服務提供者 (CSP) 設定](/windows/client-management/mdm/surfacehub-csp)</span><span class="sxs-lookup"><span data-stu-id="f9c57-112">Configure [Configuration Service Provider (CSP) settings](/windows/client-management/mdm/surfacehub-csp)</span></span>

## <a name="overview"></a><span data-ttu-id="f9c57-113">概觀</span><span class="sxs-lookup"><span data-stu-id="f9c57-113">Overview</span></span>

1. <span data-ttu-id="f9c57-114">在個別的 PC 上Windows 10，Windows[安裝](https://www.microsoft.com/store/apps/9nblggh4tx22)組Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="f9c57-114">On a separate PC running Windows 10, install [Windows Configuration Designer](https://www.microsoft.com/store/apps/9nblggh4tx22) from the Microsoft Store.</span></span>
1. <span data-ttu-id="f9c57-115">選取[**設定Surface Hub**](#use-surface-hub-provisioning-wizard)裝置，以使用精靈設定一般設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-115">Select [**Provision Surface Hub devices**](#use-surface-hub-provisioning-wizard) to configure common settings using a wizard.</span></span> <span data-ttu-id="f9c57-116">或者， [選取進位設定](#use-advanced-provisioning) 來查看和設定所有可能的設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-116">Or select [Advanced provisioning](#use-advanced-provisioning) to view and configure all possible settings.</span></span>
1. <span data-ttu-id="f9c57-117">建立部署套件，並將其儲存到 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f9c57-117">Create the provisioning package and save it to a USB drive.</span></span>
1. <span data-ttu-id="f9c57-118">在第一次執行設定Surface Hub或透過應用程式將套件部署到您的設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="f9c57-118">Deploy the package to your Surface Hub during first-run setup, or through the Settings app.</span></span> <span data-ttu-id="f9c57-119">若要深入瞭解，請參閱為 Windows 10[建立Windows 10。](/windows/configuration/provisioning-packages/provisioning-create-package)</span><span class="sxs-lookup"><span data-stu-id="f9c57-119">To learn more, see [Create a provisioning package for Windows 10](/windows/configuration/provisioning-packages/provisioning-create-package).</span></span>

## <a name="use-surface-hub-provisioning-wizard"></a><span data-ttu-id="f9c57-120">使用 Surface Hub配置精靈</span><span class="sxs-lookup"><span data-stu-id="f9c57-120">Use Surface Hub provisioning wizard</span></span>

1. <span data-ttu-id="f9c57-121">開啟 Windows設計工具，然後選取 Surface Hub**裝置**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-121">Open Windows Configuration Designer and select **Provision Surface Hub devices**.</span></span><br>
    ![使用 Surface Hub 佈建精靈](images/sh-prov-start.png)
    
2. <span data-ttu-id="f9c57-123">為專案命名，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-123">Name your project and select **Next**.</span></span>

### <a name="add-certificates"></a><span data-ttu-id="f9c57-124">新增憑證</span><span class="sxs-lookup"><span data-stu-id="f9c57-124">Add certificates</span></span>

> [!div class="mx-imgBorder"]
> ![新增憑證](images/sh-prov-cert.png)

<span data-ttu-id="f9c57-126">若要將裝置與憑證一起配置，請選取 **新增憑證**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-126">To provision the device with a certificate, select **Add a certificate**.</span></span> <span data-ttu-id="f9c57-127">輸入憑證的名稱，然後流覽以選取要使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-127">Enter a name for the certificate, and then browse to select the certificate to be used.</span></span>  <span data-ttu-id="f9c57-128">若要使用進一級的置備選項，請參閱將憑證 [新增到您的套件下方的一節](#add-a-certificate-to-your-package)。</span><span class="sxs-lookup"><span data-stu-id="f9c57-128">For advanced provisioning options, refer to the section below [Add a certificate to your package](#add-a-certificate-to-your-package).</span></span>

### <a name="configure-proxy-settings"></a><span data-ttu-id="f9c57-129">設定 Proxy 設定</span><span class="sxs-lookup"><span data-stu-id="f9c57-129">Configure proxy settings</span></span>

> [!div class="mx-imgBorder"]
> ![設定 Proxy 設定](images/sh-prov-proxy.png)

1. <span data-ttu-id="f9c57-131">將 Proxy 設定切換為 **\[是\]** 或 **\[否\]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-131">Toggle **Yes** or **No** for proxy settings.</span></span> <span data-ttu-id="f9c57-132">根據預設，Surface Hub自動偵測 Proxy 設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-132">By default, Surface Hub automatically detects proxy settings.</span></span> <span data-ttu-id="f9c57-133">不過，如果您的基礎結構過去需要使用 Proxy 伺服器，但已變更為不需要 Proxy 伺服器，您可以選取 **\[是\]** 和 **\[自動偵測設定\]**，使用佈建套件將 Surface Hub 裝置還原回預設設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-133">However, if your infrastructure previously required using a proxy server and has changed to not require a proxy server, you can use a provisioning package to revert your Surface Hub devices to the default settings by selecting **Yes** and **Automatically detect settings**.</span></span>
2. <span data-ttu-id="f9c57-134">如果您切換 **為是**，您可以選取以自動偵測 Proxy 設定，或輸入下列其中一項手動設定：</span><span class="sxs-lookup"><span data-stu-id="f9c57-134">If you toggle **Yes**, you can select to automatically detect proxy settings or manually configure the settings by entering one of the following:</span></span>

    - <span data-ttu-id="f9c57-135">設定腳本的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9c57-135">A URL to a setup script.</span></span>
    - <span data-ttu-id="f9c57-136">靜態 Proxy 伺服器位址和埠資訊。</span><span class="sxs-lookup"><span data-stu-id="f9c57-136">A static proxy server address and port information.</span></span>

3. <span data-ttu-id="f9c57-137">如果您想要使用設定腳本或 Proxy 伺服器，請關閉自動 **偵測設定**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-137">If you intend to use a setup script or proxy server, turn off **Automatically detect settings**.</span></span> <span data-ttu-id="f9c57-138">您可以使用設定腳本 *或* Proxy 伺服器，而非兩者。</span><span class="sxs-lookup"><span data-stu-id="f9c57-138">You can use a setup script *or* a proxy server, not both.</span></span>
4. <span data-ttu-id="f9c57-139">輸入 (位址的Surface Hub，而不使用 Proxy 伺服器) 。</span><span class="sxs-lookup"><span data-stu-id="f9c57-139">Enter exceptions (addresses that Surface Hub should connect to directly without using the proxy server).</span></span> <span data-ttu-id="f9c57-140">**範例：\*.office365.com**</span><span class="sxs-lookup"><span data-stu-id="f9c57-140">**Example:** \*.office365.com</span></span>
5. <span data-ttu-id="f9c57-141">識別是否要將 Proxy 伺服器用於本地位址。</span><span class="sxs-lookup"><span data-stu-id="f9c57-141">Identify whether to use the proxy server for local addresses.</span></span>

### <a name="set-up-device-admins"></a><span data-ttu-id="f9c57-142">設定裝置系統管理員</span><span class="sxs-lookup"><span data-stu-id="f9c57-142">Set up device admins</span></span>

 > [!div class="mx-imgBorder"]
 > ![加入 Active Directory、Azure AD 或建立本地系統管理員帳戶](images/sh2-wcd.png)

<span data-ttu-id="f9c57-144">您可以在 Active Directory 中註冊裝置，並指定安全性群組使用「設定」應用程式、註冊 Azure Active Directory 以允許全域系統管理員使用「設定」應用程式，或在裝置上建立本機系統管理員。</span><span class="sxs-lookup"><span data-stu-id="f9c57-144">You can enroll the device in Active Directory and specify a security group to use the Settings app, enroll in Azure Active Directory to allow global admins to use the Settings app, or create a local administrator account on the device.</span></span>

1. <span data-ttu-id="f9c57-145">若要在 Active Directory 中註冊裝置，請輸入最低權限使用者帳戶的認證以將裝置加入網域，並指定該安全性群組在 Surface Hub 上擁有系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-145">To enroll the device in Active Directory, enter the credentials for a least-privileged user account to join the device to the domain, and specify the security group to have admin credentials on Surface Hub.</span></span> <span data-ttu-id="f9c57-146">如果將套件套用至Surface Hub重設的網域帳戶，則只要是一開始設定該Surface Hub的帳戶，就可以使用相同的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="f9c57-146">If applying the package to a Surface Hub that was reset, you can use the same domain account as long as it's the same account that set up the Surface Hub initially.</span></span> <span data-ttu-id="f9c57-147">否則，必須在佈建套件中使用不同的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="f9c57-147">Otherwise, a different domain account must be used in the provisioning package.</span></span>
2. <span data-ttu-id="f9c57-148">使用組Windows設計工具來設定大量 Azure AD 註冊之前，[請規劃您的 Azure AD 加入實現](/azure/active-directory/devices/azureadjoin-plan)。</span><span class="sxs-lookup"><span data-stu-id="f9c57-148">Before you use Windows Configuration Designer to configure bulk Azure AD enrollment, [Plan your Azure AD join implementation](/azure/active-directory/devices/azureadjoin-plan).</span></span> <span data-ttu-id="f9c57-149">您 Azure AD 租用戶中的 **\[每位使用者的裝置數目上限\]** 設定決定您在精靈中使用的大量權杖可使用多少次。</span><span class="sxs-lookup"><span data-stu-id="f9c57-149">The **maximum number of devices per user** setting in your Azure AD tenant determines how many times the bulk token that you get in the wizard can be used.</span></span>
3. <span data-ttu-id="f9c57-150">若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。</span><span class="sxs-lookup"><span data-stu-id="f9c57-150">To enroll the device in Azure AD, select that option and enter a friendly name for the bulk token you will get using the wizard.</span></span> <span data-ttu-id="f9c57-151">設定權杖的到期日 (上限為自您取得權杖起的 30 天)。</span><span class="sxs-lookup"><span data-stu-id="f9c57-151">Set an expiration date for the token (maximum is 30 days from the date you get the token).</span></span> <span data-ttu-id="f9c57-152">選取 **取得大量權杖**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-152">Select **Get bulk token**.</span></span> <span data-ttu-id="f9c57-153">在 **\[Let's get you signed in\]** (讓我們將您登入) 視窗中，輸入具有權限將裝置加入 Azure AD 的帳戶，然後輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="f9c57-153">In the **Let's get you signed in** window, enter an account that has permissions to join a device to Azure AD, and then the password.</span></span> <span data-ttu-id="f9c57-154">選取**接受**以Windows組組設計工具的必要許可權。</span><span class="sxs-lookup"><span data-stu-id="f9c57-154">Select **Accept** to give Windows Configuration Designer the necessary permissions.</span></span>
4. <span data-ttu-id="f9c57-155">若要建立本機系統管理員帳戶，請選取該選項，並輸入使用者名稱與密碼。</span><span class="sxs-lookup"><span data-stu-id="f9c57-155">To create a local administrator account, select that option and enter a user name and password.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9c57-156">如果您在佈建套件中建立本機帳戶，您必須使用 **\[設定\]** 應用程式每隔 42 天變更一次密碼。</span><span class="sxs-lookup"><span data-stu-id="f9c57-156">If you create a local account in the provisioning package, you must change the password using the **Settings** app every 42 days.</span></span> <span data-ttu-id="f9c57-157">如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。</span><span class="sxs-lookup"><span data-stu-id="f9c57-157">If the password is not changed during that period, the account might be locked out and unable to sign in.</span></span>

### <a name="enroll-in-third-party-mdm-provider"></a><span data-ttu-id="f9c57-158">註冊協力廠商 MDM 提供者</span><span class="sxs-lookup"><span data-stu-id="f9c57-158">Enroll in third party MDM provider</span></span>

> [!div class="mx-imgBorder"]
> ![註冊協力廠商行動裝置管理](images/sh-prov-mdm.png)

<span data-ttu-id="f9c57-160">如果您使用協力廠商行動裝置管理 (MDM) 提供者，您可以使用本節註冊Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="f9c57-160">If you use a third party mobile device management (MDM) provider, you can use this section to enroll Surface Hub.</span></span> <span data-ttu-id="f9c57-161">若要註冊[Intune，](/mem/intune/enrollment/quickstart-setup-auto-enrollment)請如上一節所述，先設定 Azure AD 加入，然後遵循下列 Intune 檔中的指示：為裝置Windows 10註冊。</span><span class="sxs-lookup"><span data-stu-id="f9c57-161">To enroll in Intune, first setup Azure AD join, as described in the previous section, and follow the instructions in the following Intune documentation: [Set up automatic enrollment for Windows 10 devices](/mem/intune/enrollment/quickstart-setup-auto-enrollment).</span></span>

1. <span data-ttu-id="f9c57-162">針對 **第三** 方 **MDM** 的註冊切換為是或否。</span><span class="sxs-lookup"><span data-stu-id="f9c57-162">Toggle **Yes** or **No** for enrollment in third party MDM.</span></span>
2. <span data-ttu-id="f9c57-163">如果您切換 **為是**，請提供授權註冊裝置的服務帳戶和密碼或憑證指紋，並指定驗證類型。</span><span class="sxs-lookup"><span data-stu-id="f9c57-163">If you toggle **Yes**, provide a service account and password or certificate thumbprint that is authorized to enroll the device and specify the authentication type.</span></span>
3. <span data-ttu-id="f9c57-164">如果您的 MDM 提供者需要，請輸入探索服務、註冊服務和策略服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="f9c57-164">If required by your MDM provider, enter the URLs for the discovery service, enrollment service, and policy service.</span></span>

 <span data-ttu-id="f9c57-165">若要深入瞭解，請參閱使用[MDM Surface Hub管理資料。](manage-settings-with-mdm-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="f9c57-165">To learn more, see [Manage Surface Hub with an MDM provider.](manage-settings-with-mdm-for-surface-hub.md)</span></span>

### <a name="add-applications"></a><span data-ttu-id="f9c57-166">新增應用程式</span><span class="sxs-lookup"><span data-stu-id="f9c57-166">Add applications</span></span>

> [!div class="mx-imgBorder"]
> ![新增應用程式](images/sh-prov-apps.png)

<span data-ttu-id="f9c57-168">您可以在佈建套件中安裝多個通用 Windows 平台 (UWP) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f9c57-168">You can install multiple Universal Windows Platform (UWP) apps in a provisioning package.</span></span> <span data-ttu-id="f9c57-169">若要深入瞭解，請參閱將 [電腦與應用程式一起配置](/windows/configuration/provisioning-packages/provision-pcs-with-apps)。</span><span class="sxs-lookup"><span data-stu-id="f9c57-169">To learn more, see [Provision PCs with apps](/windows/configuration/provisioning-packages/provision-pcs-with-apps).</span></span>

> [!NOTE]
> <span data-ttu-id="f9c57-170">雖然Windows設計工具可讓您新增傳統 Win32 應用程式至資源配置套件，Surface Hub僅接受 UWP 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f9c57-170">Although Windows Configuration Designer lets you add a Classic Win32 app to a provisioning package, Surface Hub only accepts UWP apps.</span></span> <span data-ttu-id="f9c57-171">如果您包含傳統型 Win32 應用程式，佈建將會失敗。</span><span class="sxs-lookup"><span data-stu-id="f9c57-171">If you include a Classic Win32 app, provisioning will fail.</span></span>

### <a name="add-a-configuration-file"></a><span data-ttu-id="f9c57-172">新增組設定檔</span><span class="sxs-lookup"><span data-stu-id="f9c57-172">Add a configuration file</span></span>

<span data-ttu-id="f9c57-173">除了此設定套件之外，您還可以使用Surface Hub設定檔，更輕鬆地設定您的裝置。</span><span class="sxs-lookup"><span data-stu-id="f9c57-173">In addition to this provisioning package, you can use a Surface Hub configuration file to make it even easier to set up your devices.</span></span> <span data-ttu-id="f9c57-174">Surface Hub組設定檔包含用於連接到 Exchange、Microsoft Teams 或 商務用 Skype 的裝置帳戶清單，以及無線投影的「好用名稱」。</span><span class="sxs-lookup"><span data-stu-id="f9c57-174">A Surface Hub configuration file contains a list of device accounts for connecting to Exchange, Microsoft Teams, or Skype for Business, as well as "friendly names" for wireless projection.</span></span>

**<span data-ttu-id="f9c57-175">若要建立Surface Hub組設定檔：</span><span class="sxs-lookup"><span data-stu-id="f9c57-175">To create a Surface Hub configuration file:</span></span>**

1. <span data-ttu-id="f9c57-176">開啟Microsoft Excel (或其他.csv編輯器) ，建立.csv名為 SurfaceHubConfiguration.csv</span><span class="sxs-lookup"><span data-stu-id="f9c57-176">Open Microsoft Excel (or other .csv editor), create a .csv file named SurfaceHubConfiguration.csv</span></span>
2. <span data-ttu-id="f9c57-177">輸入此格式的裝置帳戶和好用名稱清單：</span><span class="sxs-lookup"><span data-stu-id="f9c57-177">Enter a list of device accounts and friendly names in this format:</span></span>

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > <span data-ttu-id="f9c57-178">設定檔不得包含欄標頭。</span><span class="sxs-lookup"><span data-stu-id="f9c57-178">The configuration file must not contain column headers.</span></span> <span data-ttu-id="f9c57-179">當包含在套用至 Surface Hub 的置備套件中時，您可以從檔案中選取裝置的帳戶和好用名稱。</span><span class="sxs-lookup"><span data-stu-id="f9c57-179">When included in a provisioning package applied to Surface Hub, you can select the account and friendly name for the device from the file.</span></span> <span data-ttu-id="f9c57-180">若要建立.csv，請使用 UPN 位址格式 (rainier@contoso.com) 或下層登入名稱格式 (contoso\rainier) 。</span><span class="sxs-lookup"><span data-stu-id="f9c57-180">To create the .csv file,  use either a UPN address format (rainier@contoso.com) or down-level logon name format (contoso\rainier).</span></span>

- <span data-ttu-id="f9c57-181">rainier@contoso.com，password，Rainier Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f9c57-181">rainier@contoso.com,password,Rainier Surface Hub</span></span>

3. <span data-ttu-id="f9c57-182">將檔案儲存到您的專案資料夾，然後使用您的部署套件將其複製到 USB 金鑰。</span><span class="sxs-lookup"><span data-stu-id="f9c57-182">Save the file to your project folder and copy it to the USB key with your provisioning package.</span></span>

> [!NOTE]
> <span data-ttu-id="f9c57-183">設定檔只能在第一次執行設定期間使用。</span><span class="sxs-lookup"><span data-stu-id="f9c57-183">The configuration file can only be applied during first run setup.</span></span>

### <a name="password-protect-provisioning-package"></a><span data-ttu-id="f9c57-184">密碼保護資源配置套件</span><span class="sxs-lookup"><span data-stu-id="f9c57-184">Password protect provisioning package</span></span>

<span data-ttu-id="f9c57-185">如果您選擇使用密碼，則每次將部署套件套用至裝置時，您都需要輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="f9c57-185">If you choose to use a password,  you will need to enter it each time you apply the provisioning package to a device.</span></span>

### <a name="complete-provisioning-wizard"></a><span data-ttu-id="f9c57-186">完成資源配置精靈</span><span class="sxs-lookup"><span data-stu-id="f9c57-186">Complete provisioning wizard</span></span>

<span data-ttu-id="f9c57-187">如果您只需要設定一般設定，請**選取完成**  >  **建立**，然後跳到建立[套件一節](#build-your-package)。</span><span class="sxs-lookup"><span data-stu-id="f9c57-187">If you only need to configure common settings, select **Finish** > **Create** and skip to the section [Build your package](#build-your-package).</span></span> <span data-ttu-id="f9c57-188">或切換到進一步設定，繼續設定設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-188">Or continue configuring settings by switching to Advanced provisioning.</span></span>

## <a name="use-advanced-provisioning"></a><span data-ttu-id="f9c57-189">使用進位置備</span><span class="sxs-lookup"><span data-stu-id="f9c57-189">Use Advanced provisioning</span></span>

> [!TIP]
> <span data-ttu-id="f9c57-190">使用精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-190">Use the wizard to create a package with the common settings, then switch to the advanced editor to add other settings.</span></span><br><br> ![切換至進階編輯器](images/icd-simple-edit.png)

1. <span data-ttu-id="f9c57-192">如果繼續上一節，請選取\*\*\*\* 切換至進Windows編輯器，然後Windows**進\*\*\*\*位置備**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-192">If continuing from the previous section, select **Switch to advanced editor** otherwise open **Windows Configuration Designer** and select **Advanced provisioning**.</span></span><br>
  ![使用進階佈建](images/sh-prov-adv.png)

2. <span data-ttu-id="f9c57-194">為專案命名，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-194">Name your project and select **Next**.</span></span>
3. <span data-ttu-id="f9c57-195">選取**共同Windows 10 團隊版，\*\*\*\*選取下**一步，**然後選取**完成 。</span><span class="sxs-lookup"><span data-stu-id="f9c57-195">Select **Common to Windows 10 Team**, select **Next**, and then select **Finish**.</span></span><br>
     ![WCD 新專案](images/icd-new-project.png)

4. <span data-ttu-id="f9c57-197">在專案中的可用 **自訂項下**，選取 **共同小組設定**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-197">In the project, under **Available customizations**, select **Common Team settings**.</span></span><br>
     ![WCD 常用設定](images/icd-common-settings.png)

### <a name="add-a-certificate-to-your-package"></a><span data-ttu-id="f9c57-199">將憑證新增到您的套件</span><span class="sxs-lookup"><span data-stu-id="f9c57-199">Add a certificate to your package</span></span>

<span data-ttu-id="f9c57-200">您可以使用佈建套件來安裝憑證，讓裝置可向 Microsoft Exchange 驗證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-200">You can use provisioning packages to install certificates that will allow the device to authenticate to Microsoft Exchange.</span></span>

> [!NOTE]
> <span data-ttu-id="f9c57-201">佈建套件只能將憑證安裝到裝置 (本機電腦) 存放區，不能安裝到使用者存放區。</span><span class="sxs-lookup"><span data-stu-id="f9c57-201">Provisioning packages can only install certificates to the device (local machine) store, and not to the user store.</span></span> <span data-ttu-id="f9c57-202">如果貴組織需要將憑證安裝至使用者存放區，請使用 Hub**設定**應用程式：更新\*\*\*\*&  >  **憑證**  >  **的導入憑證**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-202">If your organization requires that certificates be installed to the user store, use the Hub **Settings** app: **Update & Security** > **Certificates** > **Import Certificate**.</span></span>
<span data-ttu-id="f9c57-203">或者，您可以使用 MDM  [**策略**](manage-settings-with-mdm-for-surface-hub.md) 將憑證部署到裝置存放區或使用者存放區。</span><span class="sxs-lookup"><span data-stu-id="f9c57-203">Alternatively, you can use  [**MDM policies**](manage-settings-with-mdm-for-surface-hub.md) to deploy certificates to either the device store or the user store.</span></span>

> [!TIP]
> <span data-ttu-id="f9c57-204">**ClientCertificates**區段適用于具有私密金鑰的 .pfx 檔案;根 CA 的 .cer 檔案應放在**RootCertificates**區段，而針對**CACertificates**區段的中級 CA。</span><span class="sxs-lookup"><span data-stu-id="f9c57-204">The **ClientCertificates** section is for .pfx files with a private key; .cer files for root CAs should be placed in the **RootCertificates** section and for Intermediate CAs in the **CACertificates** section.</span></span>

1. <span data-ttu-id="f9c57-205">在**Windows設計**  >  **工具可用的自訂專案**中，請前往**Runtime settings**  >  **憑證**  >  **ClientCertificates**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-205">In **Windows Configuration Designer** > **Available customizations** , go to **Runtime settings** > **Certificates** > **ClientCertificates**.</span></span>
2. <span data-ttu-id="f9c57-206">輸入 **CertificateName 卷** 標，然後 **選取新增**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-206">Enter a label for **CertificateName** and then select **Add**.</span></span>
3. <span data-ttu-id="f9c57-207">輸入 **CertificatePassword**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-207">Enter the **CertificatePassword**.</span></span>
4. <span data-ttu-id="f9c57-208">針對 **[CertificatePath]**，瀏覽並選取要使用的憑證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-208">For **CertificatePath**, browse and select the certificate.</span></span>
5. <span data-ttu-id="f9c57-209">將 **[ExportCertificate]** 設定為 **[False]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-209">Set **ExportCertificate** to **False**.</span></span>
6. <span data-ttu-id="f9c57-210">針對 \[KeyLocation\]，選取 \[僅限軟體\]。\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f9c57-210">For **KeyLocation**, select **Software only**.</span></span>

### <a name="add-a-uwp-app-to-your-package"></a><span data-ttu-id="f9c57-211">在套件中新增 UWP 應用程式</span><span class="sxs-lookup"><span data-stu-id="f9c57-211">Add a UWP app to your package</span></span>

<span data-ttu-id="f9c57-212">若要將 UWP 應用程式新增到布建套件，您需要應用程式套件 (.appx 或 .appxbundle 檔案) 任何相依性檔案。</span><span class="sxs-lookup"><span data-stu-id="f9c57-212">To add a UWP app to a provisioning package, you will need the app package (.appx or .appxbundle files) and any dependency files.</span></span> <span data-ttu-id="f9c57-213">如果您從商務用 Microsoft Store 取得應用程式，您也需要*未編碼的*應用程式授權。</span><span class="sxs-lookup"><span data-stu-id="f9c57-213">If you acquired the app from the Microsoft Store for Business, you will also need the *unencoded* app license.</span></span> <span data-ttu-id="f9c57-214">請參閱[散發離線應用程式](/microsoft-store/distribute-offline-apps) (英文) 以了解如何從商務用 Microsoft Store 下載這些項目。</span><span class="sxs-lookup"><span data-stu-id="f9c57-214">See [Distribute offline apps](/microsoft-store/distribute-offline-apps) to learn how to download these items from the Microsoft Store for Business.</span></span>

**<span data-ttu-id="f9c57-215">若要新增 UWP 應用程式：</span><span class="sxs-lookup"><span data-stu-id="f9c57-215">To add a UWP app:</span></span>**

1. <span data-ttu-id="f9c57-216">在 **\[可用的自訂項目\]** 窗格中，移至\*\* \[執行階段設定\]\*\* > **\[UniversalAppInstall\]** > **\[DeviceContextApp\]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-216">In the **Available customizations** pane, go to **Runtime settings** > **UniversalAppInstall** > **DeviceContextApp**.</span></span>
2. <span data-ttu-id="f9c57-217">輸入 **App 的 PackageFamilyName，** 然後 **選取**新增 。</span><span class="sxs-lookup"><span data-stu-id="f9c57-217">Enter a **PackageFamilyName** for the app and then select **Add**.</span></span> <span data-ttu-id="f9c57-218">為了保持一致性，請使用應用程式的套件系列名稱。</span><span class="sxs-lookup"><span data-stu-id="f9c57-218">For consistency, use the app's package family name.</span></span> <span data-ttu-id="f9c57-219">如果您從商務用 Microsoft Store 取得應用程式，您可以在應用程式授權中找到套件系列名稱。</span><span class="sxs-lookup"><span data-stu-id="f9c57-219">If you acquired the app from the Microsoft Store for Business, you can find the package family name in the app license.</span></span> <span data-ttu-id="f9c57-220">使用文字編輯器開啟授權檔案，並使用PFM 標記之間的值。</span><span class="sxs-lookup"><span data-stu-id="f9c57-220">Open the license file using a text editor, and use the value between the PFM tags.</span></span>
3. <span data-ttu-id="f9c57-221">針對**ApplicationFile，** 選取流覽以尋找並選取目標應用程式 ( .appx 或 .appxbundle) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f9c57-221">For **ApplicationFile**, select **Browse** to find and select the target app ( .appx or .appxbundle).</span></span>
4. <span data-ttu-id="f9c57-222">針對**DependencyAppxFiles，選取\*\*\*\*流覽**以尋找並新增應用程式的任何相依性。</span><span class="sxs-lookup"><span data-stu-id="f9c57-222">For **DependencyAppxFiles**, select **Browse** to find and add any dependencies for the app.</span></span> <span data-ttu-id="f9c57-223">針對 Surface Hub，您將僅需要這些相依性的 x64 版本。</span><span class="sxs-lookup"><span data-stu-id="f9c57-223">For Surface Hub, you will only need the x64 versions of these dependencies.</span></span>

<span data-ttu-id="f9c57-224">如果您是從應用程式商務用 Microsoft Store，您必須將應用程式授權新加到您的部署套件中。</span><span class="sxs-lookup"><span data-stu-id="f9c57-224">If you acquired the app from the Microsoft Store for Business, you will need to add the app license to your provisioning package.</span></span>

**<span data-ttu-id="f9c57-225">若要新增應用程式授權：</span><span class="sxs-lookup"><span data-stu-id="f9c57-225">To add app license:</span></span>**

1. <span data-ttu-id="f9c57-226">建立應用程式授權的複本，然後將它重新命名為使用 **.ms-windows-store-license** 副檔名。</span><span class="sxs-lookup"><span data-stu-id="f9c57-226">Make a copy of the app license, and rename it to use a **.ms-windows-store-license** extension.</span></span> <span data-ttu-id="f9c57-227">例如，將"example.xml"重新命名為"example.ms-windows-store-license"。</span><span class="sxs-lookup"><span data-stu-id="f9c57-227">For example, rename "example.xml" to "example.ms-windows-store-license".</span></span>
2. <span data-ttu-id="f9c57-228">在 Windows設計工具中，前往\*\*\*\*[可用的自訂設定執行時間  >  **設定**通用  >  **應用程式Install**  >  **DeviceCoNtextAppLicense>。**</span><span class="sxs-lookup"><span data-stu-id="f9c57-228">In Windows Configuration Designer, go to **Available customizations** > **Runtime settings** > **UniversalAppInstall** > **DeviceContextAppLicense**.</span></span>
3. <span data-ttu-id="f9c57-229">輸入**LicenseProductId，\*\*\*\*然後選取**新增 。</span><span class="sxs-lookup"><span data-stu-id="f9c57-229">Enter a **LicenseProductId** and then select **Add**.</span></span> <span data-ttu-id="f9c57-230">為了保持一致性，請使用應用程式授權中的應用程式授權識別碼。</span><span class="sxs-lookup"><span data-stu-id="f9c57-230">For consistency, use the app's license ID from the app license.</span></span> <span data-ttu-id="f9c57-231">使用文字編輯器開啟授權檔案。</span><span class="sxs-lookup"><span data-stu-id="f9c57-231">Open the license file using a text editor.</span></span> <span data-ttu-id="f9c57-232">接著，在 **授權標記** 中，使用 **LicenseID 屬性中的** 值。</span><span class="sxs-lookup"><span data-stu-id="f9c57-232">Then, in the **License** tag, use the value in the **LicenseID** attribute.</span></span>
4. <span data-ttu-id="f9c57-233">選取新的 **[LicenseProductId]** 節點。</span><span class="sxs-lookup"><span data-stu-id="f9c57-233">Select the new **LicenseProductId** node.</span></span> <span data-ttu-id="f9c57-234">針對**LicenseInstall，** 選取流覽以尋找並選取您重新命名 (example.ms-windows-store-license) 。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f9c57-234">For **LicenseInstall**, select **Browse** to find and select your renamed license file (example.ms-windows-store-license).</span></span>

### <a name="add-a-policy-to-your-package"></a><span data-ttu-id="f9c57-235">新增原則至套件</span><span class="sxs-lookup"><span data-stu-id="f9c57-235">Add a policy to your package</span></span>

<span data-ttu-id="f9c57-236">Surface Hub 支援[原則設定服務提供者](/windows/client-management/mdm/policy-configuration-service-provider)中一部分的原則。</span><span class="sxs-lookup"><span data-stu-id="f9c57-236">Surface Hub supports a subset of the policies in the [Policy configuration service provider](/windows/client-management/mdm/policy-configuration-service-provider).</span></span> <span data-ttu-id="f9c57-237">其中一些策略可以使用組Windows設計工具進行。</span><span class="sxs-lookup"><span data-stu-id="f9c57-237">Some of those policies can be configured with Windows Configuration Designer.</span></span>

 **<span data-ttu-id="f9c57-238">若要新增 [CSP 政策](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)：</span><span class="sxs-lookup"><span data-stu-id="f9c57-238">To add [CSP policies](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub):</span></span>**

1. <span data-ttu-id="f9c57-239">前往 可用的**自訂專案**  >  **執行時間設定**  >  **策略**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-239">Go to  **Available customizations** > **Runtime settings** > **Policies**.</span></span>
2. <span data-ttu-id="f9c57-240">選取您想要管理的元件，並設定適當的策略設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-240">Select the component you want to manage and configure the policy setting as appropriate.</span></span> <span data-ttu-id="f9c57-241">例如，若要防止員工使用 InPrivate 網站流覽Surface Hub **AllowInPrivate，** 然後選取**停用**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-241">For example, to prevent employees from using InPrivate website browsing on Surface Hub, select **AllowInPrivate** and then select **Disable**.</span></span>  

    > [!div class="mx-imgBorder"]
    > ![設定策略設定](images/sh-prov-policies.png)

### <a name="add-surface-hub-settings-to-your-package"></a><span data-ttu-id="f9c57-243">將 Surface Hub 設定新增至套件</span><span class="sxs-lookup"><span data-stu-id="f9c57-243">Add Surface Hub settings to your package</span></span>

<span data-ttu-id="f9c57-244">您可以從 [SurfaceHub 設定服務提供者](/windows/client-management/mdm/surfacehub-csp)將設定新增到佈建套件。</span><span class="sxs-lookup"><span data-stu-id="f9c57-244">You can add settings from the [SurfaceHub configuration service provider](/windows/client-management/mdm/surfacehub-csp) to your provisioning package.</span></span>

1. <span data-ttu-id="f9c57-245">前往 可用的**自訂專案**  >  **一般小組版 設定。**</span><span class="sxs-lookup"><span data-stu-id="f9c57-245">Go to **Available customizations** > **Common Team Edition Settings**.</span></span>
1. <span data-ttu-id="f9c57-246">選取您想要管理的元件，並設定適當的策略設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-246">Select the component you want to manage and configure the policy setting as appropriate.</span></span>
1. <span data-ttu-id="f9c57-247">當您完成配置套件時，請選取 檔案\*\*\*\*  >  **儲存**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-247">When you are done configuring the provisioning package, select  **File** > **Save**.</span></span>
1. <span data-ttu-id="f9c57-248">閱讀專案檔案可能包含敏感性資訊的警告， **然後選取確定**</span><span class="sxs-lookup"><span data-stu-id="f9c57-248">Read the warning that project files may contain sensitive information, and select **OK**</span></span>

### <a name="build-your-package"></a><span data-ttu-id="f9c57-249">建置您的套件</span><span class="sxs-lookup"><span data-stu-id="f9c57-249">Build your package</span></span>

<span data-ttu-id="f9c57-250">當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。</span><span class="sxs-lookup"><span data-stu-id="f9c57-250">When you build a provisioning package, you may include sensitive information in the project files and in the provisioning package (.ppkg) file.</span></span> <span data-ttu-id="f9c57-251">雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。</span><span class="sxs-lookup"><span data-stu-id="f9c57-251">Although you have the option to encrypt the .ppkg file, project files are not encrypted.</span></span>  <span data-ttu-id="f9c57-252">將專案檔案儲存在安全的位置，或刪除不再需要的專案檔案。</span><span class="sxs-lookup"><span data-stu-id="f9c57-252">Store the project files in a secure location or delete if no longer needed.</span></span>

1. <span data-ttu-id="f9c57-253">開啟**Windows設計**  >  **工具匯出**  >  **置備套件**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-253">Open **Windows Configuration Designer** > **Export** > **Provisioning package**.</span></span>
2. <span data-ttu-id="f9c57-254">將**擁有者變更\*\*\*\*為 IT 系統管理員**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-254">Change **Owner** to **IT Admin**.</span></span>  
3. <span data-ttu-id="f9c57-255">設定 **[套件版本]** 的值，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-255">Set a value for **Package Version**, and then select **Next.**</span></span>

> [!TIP]
> <span data-ttu-id="f9c57-256">將擁有者設定為 IT 系統管理員可確保套件設定維持適當的「優先順序屬性」，Surface Hub如果其他布建套件後來從其他來源套用，則此設定仍然有效。</span><span class="sxs-lookup"><span data-stu-id="f9c57-256">Setting the owner to IT Admin ensures that package settings maintain the appropriate "precedence properties" and remain in effect on Surface Hub if other provisioning packages are subsequently applied from other sources.</span></span>

> [!TIP]
> <span data-ttu-id="f9c57-257">您可以修改現有的套件，並變更版本號碼以更新先前套用過的套件。</span><span class="sxs-lookup"><span data-stu-id="f9c57-257">You can modify existing packages and change the version number to update previously applied packages.</span></span>

4. <span data-ttu-id="f9c57-258">選用：您可以選擇加密套件並啟用套件簽名：</span><span class="sxs-lookup"><span data-stu-id="f9c57-258">Optional: You can choose to encrypt the package and enable package signing:</span></span>

    1. <span data-ttu-id="f9c57-259">選取 **加密套件** ，然後輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="f9c57-259">Select **Encrypt package** and then enter a password.</span></span>
    1. <span data-ttu-id="f9c57-260">選取**簽署套件**  >  **流覽**，並在適當時選擇憑證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-260">Select **Sign package** > **Browse** and choose the certificate as appropriate.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="f9c57-261">建議您在部署套件中包含信任的部署憑證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-261">Including a trusted provisioning certificate in your provisioning package is recommended.</span></span> <span data-ttu-id="f9c57-262">當套件套用至裝置時，憑證會新加到系統存放區，讓後續的套件以無提示方式套用。</span><span class="sxs-lookup"><span data-stu-id="f9c57-262">When the package is applied to a device, the certificate is added to the system store, enabling subsequent packages to be applied silently.</span></span>

5. <span data-ttu-id="f9c57-263">選取 **下一** 步以指定輸出位置。</span><span class="sxs-lookup"><span data-stu-id="f9c57-263">Select **Next** to specify the output location.</span></span> <span data-ttu-id="f9c57-264">Windows 設定設計工具預設會使用專案資料夾做為輸出位置。</span><span class="sxs-lookup"><span data-stu-id="f9c57-264">By default, Windows Configuration Designer uses the project folder as the output location.</span></span> <span data-ttu-id="f9c57-265">或選取 **流覽** 以變更預設輸出位置。</span><span class="sxs-lookup"><span data-stu-id="f9c57-265">Or select **Browse** to change the default output location.</span></span> <span data-ttu-id="f9c57-266">選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-266">Select **Next**.</span></span>
6. <span data-ttu-id="f9c57-267">選取 **建立** 以開始建立套件。</span><span class="sxs-lookup"><span data-stu-id="f9c57-267">Select **Build** to start building the package.</span></span> <span data-ttu-id="f9c57-268">專案資訊會顯示在建立頁面中。</span><span class="sxs-lookup"><span data-stu-id="f9c57-268">The project information is displayed in the build page.</span></span>
7. <span data-ttu-id="f9c57-269">如果您的建立失敗，會顯示錯誤訊息，並包含專案資料夾的連結。</span><span class="sxs-lookup"><span data-stu-id="f9c57-269">If your build fails, an error message appears with a link to the project folder.</span></span> <span data-ttu-id="f9c57-270">檢查記錄以診斷錯誤，然後再次嘗試建立套件。</span><span class="sxs-lookup"><span data-stu-id="f9c57-270">Review the logs to diagnose the error and try building the package again.</span></span>
8. <span data-ttu-id="f9c57-271">如果您的建置成功，系統會顯示部署套件、輸出目錄和專案目錄的名稱。</span><span class="sxs-lookup"><span data-stu-id="f9c57-271">If your build succeeds, the name of the provisioning package, output directory, and project directory are displayed.</span></span> <span data-ttu-id="f9c57-272">選取 **完成** 以關閉精靈，然後返回自訂頁面。</span><span class="sxs-lookup"><span data-stu-id="f9c57-272">Select **Finish** to close the wizard and go back to the Customizations page.</span></span>
9. <span data-ttu-id="f9c57-273">選取  **輸出位置**  以前往套件的位置。</span><span class="sxs-lookup"><span data-stu-id="f9c57-273">Select  **output location**  to go to the location of the package.</span></span> <span data-ttu-id="f9c57-274">將 .ppkg 複製到空的 USB 快閃磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f9c57-274">Copy the .ppkg to an empty USB flash drive.</span></span>

## <a name="apply-a-provisioning-package-to-surface-hub"></a><span data-ttu-id="f9c57-275">將佈建套件套用到 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f9c57-275">Apply a provisioning package to Surface Hub</span></span>

<span data-ttu-id="f9c57-276">將佈建套件部署至 Surface Hub 有兩個選項。</span><span class="sxs-lookup"><span data-stu-id="f9c57-276">There are two options for deploying provisioning packages to a Surface Hub.</span></span> <span data-ttu-id="f9c57-277">[在第一](#apply-a-provisioning-package-during-first-run)次執行精靈期間，您可以套用安裝憑證的設定套件，或在首次執行的程式完成後，使用 設定 套用設定[、應用程式和憑證的設定套件](#apply-a-provisioning-package-using-settings-app)。</span><span class="sxs-lookup"><span data-stu-id="f9c57-277">[During the first run wizard](#apply-a-provisioning-package-during-first-run), you can apply a provisioning package that installs certificates, or after the first-run program is complete, you can apply a provisioning package that configures settings, apps, and certificates by using [Settings](#apply-a-provisioning-package-using-settings-app).</span></span>

### <a name="apply-a-provisioning-package-during-first-run"></a><span data-ttu-id="f9c57-278">在初次執行期間套用佈建套件</span><span class="sxs-lookup"><span data-stu-id="f9c57-278">Apply a provisioning package during first run</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9c57-279">在第一次執行的程式期間，您只能使用部署套件來安裝憑證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-279">During the first-run program, you can only use provisioning packages to install certificates.</span></span> <span data-ttu-id="f9c57-280">使用 **[設定]** 應用程式安裝應用程式並套用其他設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-280">Use the **Settings** app to install apps and apply other settings.</span></span>

1. <span data-ttu-id="f9c57-281">當您第一次開啟 Surface Hub時，第一次執行的程式會顯示[**"您好"頁面**](first-run-program-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="f9c57-281">When you turn on the Surface Hub for the first time, the first-run program displays the [**Hi there page**](first-run-program-surface-hub.md).</span></span> <span data-ttu-id="f9c57-282">繼續之前，請確定已進行適當設定。</span><span class="sxs-lookup"><span data-stu-id="f9c57-282">Make sure that the settings are properly configured before proceeding.</span></span>
2. <span data-ttu-id="f9c57-283">將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="f9c57-283">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span> <span data-ttu-id="f9c57-284">如果套件位於磁碟機的根目錄中，初次執行程式將會識別它，並詢問您是否要設定裝置。</span><span class="sxs-lookup"><span data-stu-id="f9c57-284">If the package is in the root directory of the drive, the first-run program will recognize it and ask if you want to set up the device.</span></span> <span data-ttu-id="f9c57-285">選取 **[設定]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-285">Select **Set up**.</span></span>
3. <span data-ttu-id="f9c57-286">下一個畫面會要求您選取佈建來源。</span><span class="sxs-lookup"><span data-stu-id="f9c57-286">The next screen asks you to select a provisioning source.</span></span> <span data-ttu-id="f9c57-287">選取 \[抽取式媒體\]\*\*\*\* 並點選 \[下一步\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f9c57-287">Select **Removable Media** and tap **Next**.</span></span>
4. <span data-ttu-id="f9c57-288">選取要套用 (\*.ppkg) 套件，然後點選下一 **步**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-288">Select the provisioning package (\*.ppkg) that you want to apply, and tap **Next**.</span></span> <span data-ttu-id="f9c57-289">請注意，您在初次執行期間只能安裝一個套件。</span><span class="sxs-lookup"><span data-stu-id="f9c57-289">Note that you can only install one package during first run.</span></span>
5. <span data-ttu-id="f9c57-290">初次執行程式會向您顯示佈建套件將套用的變更摘要。</span><span class="sxs-lookup"><span data-stu-id="f9c57-290">The first-run program will show you a summary of the changes that the provisioning package will apply.</span></span> <span data-ttu-id="f9c57-291">選取 **\[是，請將它新增\]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-291">Select **Yes, add it**.</span></span>
6. <span data-ttu-id="f9c57-292">如果設定檔包含在 USB 快閃磁碟機的根目錄中，您將會看到 **\[選取設定\]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-292">If a configuration file is included in the root directory of the USB flash drive, you will see **Select a configuration**.</span></span> <span data-ttu-id="f9c57-293">將會顯示設定檔中的第一個裝置帳戶，以及將套用到 Surface Hub 的帳戶資訊摘要。</span><span class="sxs-lookup"><span data-stu-id="f9c57-293">The first device account in the configuration file will be shown with a summary of the account information that will be applied to the Surface Hub.</span></span>
7. <span data-ttu-id="f9c57-294">在 **選取群組原則中**，選取要申請的裝置名稱，然後選取下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-294">In **Select a configuration**, select the device name to apply, and then select **Next**.</span></span>

<span data-ttu-id="f9c57-295">佈建套件中的設定將套用到裝置上，OOBE 將會完成。</span><span class="sxs-lookup"><span data-stu-id="f9c57-295">The settings from the provisioning package will be applied to the device and OOBE will be complete.</span></span> <span data-ttu-id="f9c57-296">裝置重新開機後，您便可以移除 USB 快閃磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f9c57-296">After the device restarts, you can remove the USB flash drive.</span></span>

### <a name="apply-a-provisioning-package-using-settings-app"></a><span data-ttu-id="f9c57-297">使用應用程式套用設定套件</span><span class="sxs-lookup"><span data-stu-id="f9c57-297">Apply a provisioning package using Settings app</span></span>

1. <span data-ttu-id="f9c57-298">將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="f9c57-298">Insert the USB flash drive containing the .ppkg file into the Surface Hub.</span></span>
2. <span data-ttu-id="f9c57-299">從**Surface Hub開始設定**系統，並輸入系統管理認證。系統提示您輸入管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-299">From Surface Hub, start **Settings** and enter the admin credentials when prompted.</span></span>
3. <span data-ttu-id="f9c57-300">瀏覽至 **\[Surface Hub\]** > **\[裝置管理\]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-300">Navigate to **Surface Hub** > **Device management**.</span></span> <span data-ttu-id="f9c57-301">在**置備套件下**，選取新增**或移除資源調配套件**  >  **新增套件**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-301">Under **Provisioning packages**, select **Add or remove a provisioning package** > **Add a package**.</span></span>
4. <span data-ttu-id="f9c57-302">選擇您的佈建套件，然後選取 **[新增]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-302">Choose your provisioning package and select **Add**.</span></span>  <span data-ttu-id="f9c57-303">出現提示時，請再次輸入您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f9c57-303">If prompted, enter your admin credentials again.</span></span>
5. <span data-ttu-id="f9c57-304">您會看到要申請之變更的摘要。</span><span class="sxs-lookup"><span data-stu-id="f9c57-304">You'll see a summary of the changes to be applied.</span></span> <span data-ttu-id="f9c57-305">選取 **\[是，請將它新增\]**。</span><span class="sxs-lookup"><span data-stu-id="f9c57-305">Select **Yes, add it**.</span></span>

## <a name="learn-more"></a><span data-ttu-id="f9c57-306">深入了解</span><span class="sxs-lookup"><span data-stu-id="f9c57-306">Learn more</span></span>

- [<span data-ttu-id="f9c57-307">下載Windows設計工具</span><span class="sxs-lookup"><span data-stu-id="f9c57-307">Download Windows Configuration Designer</span></span>](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [<span data-ttu-id="f9c57-308">建立 Windows 10 適用的佈建套件</span><span class="sxs-lookup"><span data-stu-id="f9c57-308">Create a provisioning package for Windows 10</span></span>](/windows/configuration/provisioning-packages/provisioning-create-package)
- [<span data-ttu-id="f9c57-309">使用 MDM 提供者管理 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f9c57-309">Manage Surface Hub with an MDM provider</span></span>](manage-settings-with-mdm-for-surface-hub.md)
