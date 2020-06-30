---
title: 使用 UI 建立裝置帳戶 (Surface Hub)
description: 如果您習慣使用圖形化使用者介面，您可以使用 Office 365 UI 或 Exchange 系統管理中心，來為 Microsoft Surface Hub 建立裝置帳戶。
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: 建立裝置帳戶、Office 365 UI、Exchange 系統管理中心、Microsoft 365 系統管理中心、商務用 Skype、行動裝置信箱原則
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: e1f82f084103d4eef942e812c5e4f0e8bf425def
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832098"
---
# <span data-ttu-id="c6925-104">使用 UI 建立裝置帳戶 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="c6925-104">Create a device account using UI (Surface Hub)</span></span>


<span data-ttu-id="c6925-105">如果您習慣使用圖形化使用者介面，您可以使用 [Office 365 UI](#create-device-acct-o365) 或 [Exchange 系統管理中心](#create-device-acct-eac)，來為 Microsoft Surface Hub 建立裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-105">If you prefer to use a graphical user interface, you can create a device account for your Microsoft Surface Hub with either the [Office 365 UI](#create-device-acct-o365) or the [Exchange Admin Center](#create-device-acct-eac).</span></span>

## <a href="" id="create-device-acct-o365"></a><span data-ttu-id="c6925-106">使用 Office 365 建立裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="c6925-106">Create a device account using Office 365</span></span>


1.  <span data-ttu-id="c6925-107">[在 Microsoft 365 系統管理中心建立帳戶](#create-device-acct-o365-admin-ctr)。</span><span class="sxs-lookup"><span data-stu-id="c6925-107">[Create the account in the Microsoft 365 Admin Center](#create-device-acct-o365-admin-ctr).</span></span>
2.  <span data-ttu-id="c6925-108">[從 Microsoft Exchange 系統管理員中心建立行動裝置信箱 (ActiveSync) 原則](#create-device-acct-o365-mbx-policy)。</span><span class="sxs-lookup"><span data-stu-id="c6925-108">[Create a mobile device mailbox (ActiveSync) policy from the Microsoft Exchange Admin Center](#create-device-acct-o365-mbx-policy).</span></span>
3.  <span data-ttu-id="c6925-109">[使用 Windows PowerShell 完成裝置帳戶的建立](#create-device-acct-o365-complete-acct)。</span><span class="sxs-lookup"><span data-stu-id="c6925-109">[Use PowerShell to complete device account creation](#create-device-acct-o365-complete-acct).</span></span>
4.  <span data-ttu-id="c6925-110">[使用 PowerShell 設定帳戶的 Exchange 屬性](#create-device-acct-o365-configure-exch-prop)。</span><span class="sxs-lookup"><span data-stu-id="c6925-110">[Use PowerShell to configure Exchange properties of the account](#create-device-acct-o365-configure-exch-prop).</span></span>
5.  <span data-ttu-id="c6925-111">[使用商務用 Skype 啟用帳戶](#create-device-acct-o365-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="c6925-111">[Enable the account with Skype for Business](#create-device-acct-o365-skype-for-business).</span></span>

### <a href="" id="create-device-acct-o365-admin-ctr"></a><span data-ttu-id="c6925-112">在系統管理中心建立帳戶</span><span class="sxs-lookup"><span data-stu-id="c6925-112">Create the account in the admin center</span></span>

1.  <span data-ttu-id="c6925-113">透過造訪登入 Office 365https://portal.office.com</span><span class="sxs-lookup"><span data-stu-id="c6925-113">Sign in to Office 365 by visiting https://portal.office.com</span></span>
2.  <span data-ttu-id="c6925-114">為您的 Office 365 租用戶提供系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="c6925-114">Provide the admin credentials for your Office 365 tenant.</span></span> <span data-ttu-id="c6925-115">這會將您帶到您的 Microsoft 365 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c6925-115">This will take you to your Microsoft 365 Admin Center.</span></span>

    ![Microsoft 365 系統管理中心。](images/setupdeviceaccto365-02.png)

3. <span data-ttu-id="c6925-117">在系統管理中心中，流覽至左面板中的 [**資源**]，然後按一下 [**會議室] & 裝置**]。</span><span class="sxs-lookup"><span data-stu-id="c6925-117">In the admin center, navigate to **Resources** in the left panel, and then click **Rooms & equipment**.</span></span>

    ![系統管理中心的會議室 & 裝置] 選項](images/room-equipment.png)

4. <span data-ttu-id="c6925-119">按一下 **\[新增\]** 以建立新的會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-119">Click **Add** to create a new Room account.</span></span> <span data-ttu-id="c6925-120">輸入帳戶的顯示名稱和電子郵件地址，然後按一下 **\[新增\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-120">Enter a display name and email address for the account, and then click **Add**.</span></span>

    ![[建立新的會議室帳戶] 視窗](images/room-add.png)

5. <span data-ttu-id="c6925-122">在 [作用中使用者] 清單中選取您剛建立的會議室帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-122">Select the Room account you just created in the Active Users list.</span></span> <span data-ttu-id="c6925-123">在右面板中，可以看到帳戶屬性和數個選用動作。</span><span class="sxs-lookup"><span data-stu-id="c6925-123">In the right panel, you can see the account properties and several optional actions.</span></span> <span data-ttu-id="c6925-124">因為無法從 Surface Hub 登入流程中變更密碼，請按一下 **\[重設密碼\]** 變更密碼，然後取消選取 **\[讓這個使用者在第一次登入時變更其密碼\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-124">Click **Reset password** to change the password, and unselect **Make this user change their password when they first sign in**, because it is not possible to change the password from the Surface Hub sign-in flow.</span></span>

6. <span data-ttu-id="c6925-125">在 **\[指派的授權\]** 區段中，按一下 **\[編輯\]**，然後按一下適當授權旁邊的下拉箭頭以展開詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c6925-125">In the **Assigned license** section, click **Edit**, and then click the dropdown arrow next to the appropriate license to expand the details.</span></span> <span data-ttu-id="c6925-126">選取使用者位置，並切換開啟授權清單中的**\[商務用 Skype Online (方案 2)\]**，然後按一下 **\[儲存\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-126">Select a user location, and in the list of licenses, toggle on **Skype for Business Online (Plan 2)**, and then click **Save**.</span></span> <span data-ttu-id="c6925-127">授權會隨您的組織而改變 (例如，您可能有方案 2 或方案 3)。</span><span class="sxs-lookup"><span data-stu-id="c6925-127">The license may vary depending on your organization (for example, you might have Plan 2 or Plan 3).</span></span>

### <a href="" id="create-device-acct-o365-mbx-policy"></a><span data-ttu-id="c6925-128">從 Exchange 系統管理員中心建立行動裝置信箱 (ActiveSync) 原則</span><span class="sxs-lookup"><span data-stu-id="c6925-128">Create a mobile device mailbox (ActiveSync) policy from the Exchange Admin Center</span></span>

1.  <span data-ttu-id="c6925-129">在系統管理中心的左面板中，按一下 [系統**管理**]，然後按一下 [ **Exchange**]。</span><span class="sxs-lookup"><span data-stu-id="c6925-129">In the admin center’s left panel, click **ADMIN**, and then click **Exchange**.</span></span>

    ![[系統管理中心]，顯示 exchange 作用中的使用者。](images/setupdeviceaccto365-08.png)

2.  <span data-ttu-id="c6925-131">這將會在您的瀏覽器上開啟另一個索引標籤，並將您帶至 Exchange 系統管理中心，您可以在此處為 Surface Hub 建立並設定信箱設定。</span><span class="sxs-lookup"><span data-stu-id="c6925-131">This will open another tab on your browser to take you to the Exchange Admin Center, where you can create and set the Mailbox Setting for Surface Hub.</span></span>

    ![Exchange 系統管理中心。](images/setupdeviceaccto365-09.png)

3.  <span data-ttu-id="c6925-133">若要建立行動裝置信箱原則，請按一下左面板的 **\[行動\]**，然後按一下 **\[行動裝置信箱原則\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-133">To create a Mobile Device Mailbox Policy, click **Mobile** from the left panel and then click **Mobile device mailbox policies**.</span></span> <span data-ttu-id="c6925-134">Surface Hub 要求帳戶包含不需要密碼的行動裝置信箱原則，因此，如果您的現有原則已經符合此需求，就可以將該原則套用到帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-134">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="c6925-135">否則，使用下列步驟來建立僅限用於 Surface Hub 裝置帳戶的新原則。</span><span class="sxs-lookup"><span data-stu-id="c6925-135">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![Exchange 系統管理員中心 - 建立行動裝置信箱原則。](images/setupdeviceaccto365-10.png)

4.  <span data-ttu-id="c6925-137">若要建立新的 Surface Hub 行動裝置信箱原則，按一下原則清單上方控制項的 **+** 按鈕來新增原則。</span><span class="sxs-lookup"><span data-stu-id="c6925-137">To create a New Surface Hub mobile device mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="c6925-138">針對名稱，請提供一個可以協助您區分此原則與其他裝置帳戶的名稱 (例如，*SurfaceHubDeviceMobilePolicy*)。</span><span class="sxs-lookup"><span data-stu-id="c6925-138">For the name, provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="c6925-139">請確定原則不需要針對指派的目標裝置使用密碼，因此請確定 **\[需要密碼\]** 保持未核取，然後按一下 **\[儲存\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-139">Make sure the policy does not require a password for the devices assigned to, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![顯示新行動裝置原則的影像。](images/setupdeviceaccto365-11.png)

5.  <span data-ttu-id="c6925-141">建立新的行動裝置信箱原則之後，請回到 **\[Exchange 系統管理中心\]**，您將會看到列出的新原則。</span><span class="sxs-lookup"><span data-stu-id="c6925-141">After you have created the new mobile device mailbox policy, go back to the **Exchange Admin Center** and you will see the new policy listed.</span></span>

    ![Exchange 系統管理中心內新行動裝置信箱原則的影像。](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a><span data-ttu-id="c6925-143">使用 Windows PowerShell 完成裝置帳戶的建立</span><span class="sxs-lookup"><span data-stu-id="c6925-143">Use PowerShell to complete device account creation</span></span>

<span data-ttu-id="c6925-144">從現在開始，您需要使用 PowerShell 來設定一些組態，以完成帳戶建立程序。</span><span class="sxs-lookup"><span data-stu-id="c6925-144">From here on, you'll need to finish the account creation process using PowerShell to set up some configuration.</span></span>

<span data-ttu-id="c6925-145">若要執行這些 PowerShell 指令碼所使用的 Cmdlet，必須針對 PowerShell 系統管理主控台安裝下列項目：</span><span class="sxs-lookup"><span data-stu-id="c6925-145">In order to run cmdlets used by these PowerShell scripts, the following must be installed for the admin PowerShell console:</span></span>

-   [<span data-ttu-id="c6925-146">適用于 IT 專業人員的 Microsoft Online Services 登入小幫手 RTW</span><span class="sxs-lookup"><span data-stu-id="c6925-146">Microsoft Online Services Sign-In Assistant for IT Professionals RTW</span></span>](https://www.microsoft.com/download/details.aspx?id=41950)
-   [<span data-ttu-id="c6925-147">適用於 Windows PowerShell 的 Windows Azure Active Directory 模組</span><span class="sxs-lookup"><span data-stu-id="c6925-147">Windows Azure Active Directory Module for Windows PowerShell</span></span>](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [<span data-ttu-id="c6925-148">商務用 Skype Online，Windows PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="c6925-148">Skype for Business Online, Windows PowerShell Module</span></span>](https://www.microsoft.com/download/details.aspx?id=39366)

<span data-ttu-id="c6925-149">在 Powershell 中安裝下列模組</span><span class="sxs-lookup"><span data-stu-id="c6925-149">Install the following module in Powershell</span></span>
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### <span data-ttu-id="c6925-150">連線到線上服務</span><span class="sxs-lookup"><span data-stu-id="c6925-150">Connecting to online services</span></span>

1.  <span data-ttu-id="c6925-151">以系統管理員身分執行 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="c6925-151">Run Windows PowerShell as Administrator.</span></span>

    ![顯示如何啟動 Windows PowerShell 並以系統管理員身分執行的影像。](images/setupdeviceaccto365-17.png)

2.  <span data-ttu-id="c6925-153">建立認證物件，然後建立新的工作階段以連線到商務用 Skype Online，並提供全域租用戶系統管理員帳戶，然後按一下 **\[確定\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-153">Create a Credentials object, then create a new session that connects to Skype for Business Online, and provide the global tenant administrator account, then click **OK**.</span></span>

    ![Windows PowerShell 認證要求的影像。](images/setupdeviceaccto365-18.png)

3.  <span data-ttu-id="c6925-155">若要連線到 Microsoft Online Services，請執行：</span><span class="sxs-lookup"><span data-stu-id="c6925-155">To connect to Microsoft Online Services, run:</span></span>

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-19.png)

4.  <span data-ttu-id="c6925-157">現在若要連線到商務用 Skype Online 服務，請執行：</span><span class="sxs-lookup"><span data-stu-id="c6925-157">Now to connect to Skype for Business Online Services, run:</span></span>

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-20.png)

5.  <span data-ttu-id="c6925-159">最後，若要連線到 Exchange Online 服務，請執行：</span><span class="sxs-lookup"><span data-stu-id="c6925-159">Finally, to connect to Exchange Online Services, run:</span></span>

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-21.png)

6.  <span data-ttu-id="c6925-161">現在您必須匯入剛才建立的商務用 Skype Online 工作階段和 Exchange Online 工作階段，這將會匯入 Exchange 和 Skype 命令，讓您可以在本機使用它們。</span><span class="sxs-lookup"><span data-stu-id="c6925-161">Now you have to import the Skype for Business Online Session and the Exchange Online session you have just created, which will import the Exchange and Skype Commands so you can use them locally.</span></span>

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    <span data-ttu-id="c6925-162">請注意，這可能需要一段時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="c6925-162">Note that this could take a while to complete.</span></span>

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-22.png)

7.  <span data-ttu-id="c6925-164">一旦連線到線上服務之後，您需要執行更多 Cmdlet，以便將此帳戶設定為 Surface Hub 裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-164">Once you’re connected to the online services you need to run a few more cmdlets to configure this account as a Surface Hub device account.</span></span>

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a><span data-ttu-id="c6925-165">使用 PowerShell 設定帳戶的 Exchange 屬性</span><span class="sxs-lookup"><span data-stu-id="c6925-165">Use PowerShell to configure Exchange properties of the account</span></span>

<span data-ttu-id="c6925-166">您現在已連線到線上服務，您可以完成設定裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-166">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="c6925-167">您將使用裝置帳戶電子郵件地址來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c6925-167">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="c6925-168">將信箱類型從一般變更為會議室。</span><span class="sxs-lookup"><span data-stu-id="c6925-168">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="c6925-169">設定密碼並啟用會議室信箱帳戶</span><span class="sxs-lookup"><span data-stu-id="c6925-169">Set the password and enable the room mailbox account</span></span>
-   <span data-ttu-id="c6925-170">變更各種 Exchange 屬性</span><span class="sxs-lookup"><span data-stu-id="c6925-170">Change various Exchange properties</span></span>
-   <span data-ttu-id="c6925-171">將使用者帳戶密碼設定為永久有效。</span><span class="sxs-lookup"><span data-stu-id="c6925-171">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="c6925-172">您需要輸入帳戶的電子郵件地址，然後使用該值來建立變數：</span><span class="sxs-lookup"><span data-stu-id="c6925-172">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="c6925-173">若要儲存值，請從信箱取得它：</span><span class="sxs-lookup"><span data-stu-id="c6925-173">To store the value get it from the mailbox:</span></span>

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="c6925-174">列印值：</span><span class="sxs-lookup"><span data-stu-id="c6925-174">Print the value:</span></span>

    ```powershell
    $strEmail
    ```

    <span data-ttu-id="c6925-175">您將會看到正確的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="c6925-175">You will see the correct email address.</span></span>

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-23.png)

2. <span data-ttu-id="c6925-177">執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c6925-177">Run the following cmdlet:</span></span>

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  <span data-ttu-id="c6925-178">您可以在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="c6925-178">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="c6925-179">您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)一節中看到需要設定哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="c6925-179">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-26.png)

5.  <span data-ttu-id="c6925-181">如果您決定要讓密碼永久有效，也可以使用 PowerShell Cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="c6925-181">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="c6925-182">如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="c6925-182">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a><span data-ttu-id="c6925-183">使用商務用 Skype 啟用帳戶</span><span class="sxs-lookup"><span data-stu-id="c6925-183">Enable the account with Skype for Business</span></span>

<span data-ttu-id="c6925-184">使用商務用 Skype 啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-184">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="c6925-185">為了啟用商務用 Skype，您的環境需要符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="c6925-185">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="c6925-186">您必須在 O365 方案中有商務用 Skype Online 獨立方案2或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c6925-186">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="c6925-187">方案必須支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="c6925-187">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="c6925-188">如果您需要使用企業語音（PSTN 電話）使用 Surface Hub 的電話服務提供者，您需要商務用 Skype Online 獨立方案3。</span><span class="sxs-lookup"><span data-stu-id="c6925-188">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="c6925-189">您的租用戶使用者必須擁有 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="c6925-189">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="c6925-190">您的 Surface Hub 帳戶需要商務用 Skype Online 獨立方案2或商務用 Skype Online 獨立方案3授權，但不需要 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="c6925-190">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="c6925-191">一開始先從電腦建立遠端 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="c6925-191">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  <span data-ttu-id="c6925-192">若要針對商務用 Skype Server 啟用您的 Surface Hub 帳戶，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c6925-192">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    <span data-ttu-id="c6925-193">如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet，從現有的商務用 Skype 使用者取得值：</span><span class="sxs-lookup"><span data-stu-id="c6925-193">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a><span data-ttu-id="c6925-194">使用 Exchange 系統管理訊息中心建立裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="c6925-194">Create a device account using the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="c6925-195">只有當您從內部部署的 Active Directory 進行同步處理時，才能使用這個方法。</span><span class="sxs-lookup"><span data-stu-id="c6925-195">This method will only work if you are syncing from an on-premises Active Directory.</span></span>

<span data-ttu-id="c6925-196">您可以使用 Exchange 系統管理中心來建立裝置帳戶：</span><span class="sxs-lookup"><span data-stu-id="c6925-196">You can use the Exchange Admin Center to create a device account:</span></span>

1.  <span data-ttu-id="c6925-197">[使用 Exchange 系統管理中心建立帳戶和信箱](#create-device-acct-exch-admin-ctr)。</span><span class="sxs-lookup"><span data-stu-id="c6925-197">[Create an account and mailbox with the Exchange Admin Center](#create-device-acct-exch-admin-ctr).</span></span>
2.  <span data-ttu-id="c6925-198">[從 Exchange 系統管理中心建立行動裝置信箱原則](#create-device-acct-exch-mbx-policy)。</span><span class="sxs-lookup"><span data-stu-id="c6925-198">[Create a mobile device mailbox policy from the Exchange Admin Center](#create-device-acct-exch-mbx-policy).</span></span>
3.  <span data-ttu-id="c6925-199">[使用 PowerShell 設定帳戶](#create-device-acct-exch-powershell-conf)。</span><span class="sxs-lookup"><span data-stu-id="c6925-199">[Use PowerShell to configure the account](#create-device-acct-exch-powershell-conf).</span></span>
4.  <span data-ttu-id="c6925-200">[使用商務用 Skype 啟用帳戶](#create-device-acct-exch-skype-for-business)。</span><span class="sxs-lookup"><span data-stu-id="c6925-200">[Enable the account with Skype for Business](#create-device-acct-exch-skype-for-business).</span></span>

### <a href="" id="create-device-acct-exch-admin-ctr"></a><span data-ttu-id="c6925-201">使用 Exchange 系統管理中心建立帳戶和信箱</span><span class="sxs-lookup"><span data-stu-id="c6925-201">Create an account and mailbox with the Exchange Admin Center</span></span>

1.  <span data-ttu-id="c6925-202">使用 Exchange 系統管理員認證，登入您的 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c6925-202">Sign in to your Exchange Admin Center using Exchange admin credentials.</span></span>
2.  <span data-ttu-id="c6925-203">當您處於 Exchange 系統管理中心 (EAC) 時，請瀏覽到左面板中的 **\[收件者\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-203">Once you are at the Exchange Admin Center (EAC), navigate to **Recipients** in the left panel.</span></span>

    ![顯示 Exchange 系統管理中心內信箱的影像。](images/setupdeviceacctexch-01.png)

3.  <span data-ttu-id="c6925-205">在信箱清單上方的控制項上，選擇 **+** 以建立一個新信箱，然後提供 **「顯示名稱」**、**「名稱」** 和 **「使用者登入名稱」**，然後按一下 **\[儲存\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-205">On the controls above the list of mailboxess, choose **+** to create a new one, and provide a **Display name**, **Name**, and **User logon name**, and then click **Save**.</span></span>

    ![顯示建立新信箱的影像。](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a><span data-ttu-id="c6925-207">從 Exchange 系統管理中心建立行動裝置信箱原則</span><span class="sxs-lookup"><span data-stu-id="c6925-207">Create a mobile device mailbox policy from the Exchange Admin Center</span></span>

>[!NOTE]
><span data-ttu-id="c6925-208">如果您想要建立並指派原則給您所建立的帳戶，且使用 Exchange 2010，請在使用 EMC （Exchange 管理主控台）時查詢原則建立與原則指派的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="c6925-208">If you want to create and assign a policy to the account you created, and are using Exchange 2010, look up the corresponding information regarding policy creation and policy assignment when using the EMC (Exchange management console).</span></span>

 

1.  <span data-ttu-id="c6925-209">移至 Exchange 系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="c6925-209">Go to the Exchange Admin Center.</span></span>

    ![顯示 Exchange 系統管理中心的影像。](images/setupdeviceacctexch-03.png)

2.  <span data-ttu-id="c6925-211">若要建立行動裝置信箱原則，請按一下左面板的 **\[行動\]**，然後按一下 **\[行動裝置信箱原則\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-211">To create a mobile device mailbox policy, click **Mobile** from the left panel, then **Mobile device mailbox policies**.</span></span> <span data-ttu-id="c6925-212">Surface Hub 要求帳戶包含不需要密碼的行動裝置信箱原則，因此，如果您的現有原則已經符合此需求，就可以將該原則套用到帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-212">Surface Hubs require an account with a mobile device mailbox policy that does not require a password, so if you already have an existing policy that matches this requirement, you can apply that policy to the account.</span></span> <span data-ttu-id="c6925-213">否則，使用下列步驟來建立僅限用於 Surface Hub 裝置帳戶的新原則。</span><span class="sxs-lookup"><span data-stu-id="c6925-213">Otherwise use the following steps to create a new one to be used only for Surface Hub device accounts.</span></span>

    ![使用 Exchange 系統管理中心建立行動裝置信箱原則的影像。](images/setupdeviceacctexch-05.png)

3.  <span data-ttu-id="c6925-215">若要建立新的行動裝置帳戶信箱原則，按一下原則清單上方控制項的 **+** 按鈕來新增原則。</span><span class="sxs-lookup"><span data-stu-id="c6925-215">To create a new mobile device account mailbox policy, click the **+** button from the controls above the list of policies to add a new policy.</span></span> <span data-ttu-id="c6925-216">針對名稱，請提供一個可以協助您區分此原則與其他裝置帳戶的名稱 (例如，*SurfaceHubDeviceMobilePolicy*)。</span><span class="sxs-lookup"><span data-stu-id="c6925-216">For the name provide a name that will help you distinguish this policy from other device accounts (for example, *SurfaceHubDeviceMobilePolicy*).</span></span> <span data-ttu-id="c6925-217">原則不得受到密碼保護，因此請確定 **\[需要密碼\]** 保持未核取，然後按一下 **\[儲存\]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-217">The policy must not be password-protected, so make sure **Require a Password** remains unchecked, then click **Save**.</span></span>

    ![顯示新的行動裝置信箱原則的影像。](images/setupdeviceacctexch-06.png)

4.  <span data-ttu-id="c6925-219">建立新的行動裝置信箱原則之後，請回到 Exchange 系統管理中心，您將會看到列出的新原則。</span><span class="sxs-lookup"><span data-stu-id="c6925-219">After you have created the new mobile device mailbox policy, go back to the Exchange Admin Center and you will see the new policy listed.</span></span>

    ![顯示 Exchange 系統管理訊息中心內新行動裝置信箱原則的影像。](images/setupdeviceacctexch-07.png)

5.  <span data-ttu-id="c6925-221">若要在不使用 PowerShell 的情況下套用 ActiveSync 原則，您可以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c6925-221">To apply the ActiveSync policy without using PowerShell, you can do the following:</span></span>

    -   <span data-ttu-id="c6925-222">在 EAC 中，按一下 **\[收件者\]** &gt; **\[信箱\]**，然後選取信箱。</span><span class="sxs-lookup"><span data-stu-id="c6925-222">In the EAC, click **Recipients** &gt; **Mailboxes** and select a mailbox.</span></span>

        ![顯示 Exchange 系統管理中心的影像。](images/setupdeviceacctexch-08.png)

    -   <span data-ttu-id="c6925-224">在 **[詳細資料]** 窗格中，捲動至 **[電話和語音功能]**，然後按一下 **[檢視詳細資料]** 以顯示 **[行動裝置詳細資料]** 畫面。</span><span class="sxs-lookup"><span data-stu-id="c6925-224">In the **Details** pane, scroll to **Phone and Voice Features** and click **View details** to display the **Mobile Device Details** screen.</span></span>

        ![顯示信箱詳細資料的影像。](images/setupdeviceacctexch-09.png)

    -   <span data-ttu-id="c6925-226">隨即顯示目前指派的行動裝置信箱原則。</span><span class="sxs-lookup"><span data-stu-id="c6925-226">The mobile device mailbox policy that’s currently assigned is displayed.</span></span> <span data-ttu-id="c6925-227">若要變更行動裝置信箱原則，可按一下 **[瀏覽]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-227">To change the mobile device mailbox policy, click **Browse**.</span></span>

        ![顯示目前指派的行動裝置信箱原則的影像。](images/setupdeviceacctexch-10.png)

    -   <span data-ttu-id="c6925-229">從清單中選擇適當的行動裝置信箱原則，然後依序按一下\*\* [確定]\*\* 和 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="c6925-229">Choose the appropriate mobile device mailbox policy from the list, click **OK** and then click **Save**.</span></span>

        ![顯示行動裝置信箱原則清單的影像。](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a><span data-ttu-id="c6925-231">使用 PowerShell 設定帳戶</span><span class="sxs-lookup"><span data-stu-id="c6925-231">Use PowerShell to configure the account</span></span>

<span data-ttu-id="c6925-232">您現在已連線到線上服務，您可以完成設定裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-232">Now that you're connected to the online services, you can finish setting up the device account.</span></span> <span data-ttu-id="c6925-233">您將使用裝置帳戶電子郵件地址來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c6925-233">You'll use the device account email address to:</span></span>

-   <span data-ttu-id="c6925-234">將信箱類型從一般變更為會議室。</span><span class="sxs-lookup"><span data-stu-id="c6925-234">Change the mailbox type from regular to room.</span></span>
-   <span data-ttu-id="c6925-235">變更各種 Exchange 屬性</span><span class="sxs-lookup"><span data-stu-id="c6925-235">Change various Exchange properties</span></span>
-   <span data-ttu-id="c6925-236">將使用者帳戶密碼設定為永久有效。</span><span class="sxs-lookup"><span data-stu-id="c6925-236">Set the user account password to never expire.</span></span>

1.  <span data-ttu-id="c6925-237">您需要輸入帳戶的電子郵件地址，然後使用該值來建立變數：</span><span class="sxs-lookup"><span data-stu-id="c6925-237">You’ll need to enter the account’s mail address and create a variable with that value:</span></span>

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    <span data-ttu-id="c6925-238">若要儲存值，請從信箱取得它：</span><span class="sxs-lookup"><span data-stu-id="c6925-238">To store the value got it from the mailbox:</span></span>

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    <span data-ttu-id="c6925-239">執行下列動作來列印值：</span><span class="sxs-lookup"><span data-stu-id="c6925-239">Print the value by running:</span></span>

    ``` syntax
    $strEmail
    ```

    <span data-ttu-id="c6925-240">您將會看到正確的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="c6925-240">You will see the correct email address.</span></span>

2.  <span data-ttu-id="c6925-241">您需要將帳戶轉換成會議室信箱，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="c6925-241">You need to convert the account into a room mailbox, so run:</span></span>

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  <span data-ttu-id="c6925-242">為了讓裝置帳戶可在 Surface Hub 上進行驗證，您需要啟用會議室信箱帳戶並設定密碼，如此一來裝置便能使用帳戶，利用 ActiveSync 來取得會議資訊並登入商務用 Skype。</span><span class="sxs-lookup"><span data-stu-id="c6925-242">In order for the device account to be authenticated on a Surface Hub, you need to enable the room mailbox account and set a password, so the account can be used by the device to get meeting information using ActiveSync and log in to Skype for Business.</span></span>

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  <span data-ttu-id="c6925-243">您可以在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。</span><span class="sxs-lookup"><span data-stu-id="c6925-243">Various Exchange properties can be set on the device account to improve the meeting experience.</span></span> <span data-ttu-id="c6925-244">您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)一節中看到需要設定哪些屬性。</span><span class="sxs-lookup"><span data-stu-id="c6925-244">You can see which properties need to be set in the [Exchange properties](exchange-properties-for-surface-hub-device-accounts.md) section.</span></span>

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  <span data-ttu-id="c6925-245">現在我們必須在 AD 中設定一些屬性。</span><span class="sxs-lookup"><span data-stu-id="c6925-245">Now we have to set some properties in AD.</span></span> <span data-ttu-id="c6925-246">若要這樣做，您需要帳戶別名 (這會在 UPN 中成為 “@” 之前的一部分)。</span><span class="sxs-lookup"><span data-stu-id="c6925-246">To do that, you need the alias of the account (this is the part of the UPN that becomes before the “@”).</span></span>

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  <span data-ttu-id="c6925-247">使用者必須在其可向 Surface Hub 進行驗證之前，於 AD 中加以啟用。</span><span class="sxs-lookup"><span data-stu-id="c6925-247">The user needs to be enabled in AD before it can authenticate with a Surface Hub.</span></span> <span data-ttu-id="c6925-248">執行：</span><span class="sxs-lookup"><span data-stu-id="c6925-248">Run:</span></span>

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  <span data-ttu-id="c6925-249">如果您決定要讓密碼永久有效，也可以使用 PowerShell Cmdlet 來設定。</span><span class="sxs-lookup"><span data-stu-id="c6925-249">If you decide to have the password not expire, you can set that with PowerShell cmdlets too.</span></span> <span data-ttu-id="c6925-250">如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="c6925-250">See [Password management](password-management-for-surface-hub-device-accounts.md) for more information.</span></span>

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a><span data-ttu-id="c6925-251">使用商務用 Skype 啟用帳戶</span><span class="sxs-lookup"><span data-stu-id="c6925-251">Enable the account with Skype for Business</span></span>

<span data-ttu-id="c6925-252">使用商務用 Skype 啟用裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="c6925-252">Enable the device account with Skype for Business.</span></span>

<span data-ttu-id="c6925-253">為了啟用商務用 Skype，您的環境需要符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="c6925-253">In order to enable Skype for Business, your environment will need to meet the following prerequisites:</span></span>

-   <span data-ttu-id="c6925-254">您必須在 O365 方案中有商務用 Skype Online 獨立方案2或更高版本。</span><span class="sxs-lookup"><span data-stu-id="c6925-254">You'll need to have Skype for Business Online Standalone Plan 2 or higher in your O365 plan.</span></span> <span data-ttu-id="c6925-255">方案必須支援會議功能。</span><span class="sxs-lookup"><span data-stu-id="c6925-255">The plan needs to support conferencing capability.</span></span>
-   <span data-ttu-id="c6925-256">如果您需要使用企業語音（PSTN 電話）使用 Surface Hub 的電話服務提供者，您需要商務用 Skype Online 獨立方案3。</span><span class="sxs-lookup"><span data-stu-id="c6925-256">If you need Enterprise Voice (PSTN telephony) using telephony service providers for the Surface Hub, you need Skype for Business Online Standalone Plan 3.</span></span>
-   <span data-ttu-id="c6925-257">您的租用戶使用者必須擁有 Exchange 信箱。</span><span class="sxs-lookup"><span data-stu-id="c6925-257">Your tenant users must have Exchange mailboxes.</span></span>
-   <span data-ttu-id="c6925-258">您的 Surface Hub 帳戶需要商務用 Skype Online 獨立方案2或商務用 Skype Online 獨立方案3授權，但不需要 Exchange Online 授權。</span><span class="sxs-lookup"><span data-stu-id="c6925-258">Your Surface Hub account does require a Skype for Business Online Standalone Plan 2 or Skype for Business Online Standalone Plan 3 license, but it does not require an Exchange Online license.</span></span>

1.  <span data-ttu-id="c6925-259">一開始先從電腦建立遠端 PowerShell 工作階段。</span><span class="sxs-lookup"><span data-stu-id="c6925-259">Start by creating a remote PowerShell session from a PC.</span></span>

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="c6925-260">檢索 Surface Hub 帳戶註冊機構池</span><span class="sxs-lookup"><span data-stu-id="c6925-260">Retrieve your Surface Hub account Registrar Pool</span></span>

<span data-ttu-id="c6925-261">如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet，從現有的商務用 Skype 使用者取得值：</span><span class="sxs-lookup"><span data-stu-id="c6925-261">If you aren't sure what value to use for the `RegistrarPool` parameter in your environment, you can get the value from an existing Skype for Business user using this cmdlet:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. <span data-ttu-id="c6925-262">若要針對商務用 Skype Server 啟用您的 Surface Hub 帳戶，請執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="c6925-262">To enable your Surface Hub account for Skype for Business Server, run this cmdlet:</span></span>

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    





