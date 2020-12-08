---
title: 在 Surface Hub 2 秒設定非全域管理員帳戶
description: 本文說明如何設定非全域管理員帳戶來管理 Surface Hub 2 秒。
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196792"
---
# <span data-ttu-id="1ca5f-104">在 Surface Hub 2 秒設定非全域管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="1ca5f-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="1ca5f-105">當您將 Surface Hub 秒數連接至 Azure AD 網域時，您可以設定非全域管理員帳戶，限制在 Surface Hub 2 的設定應用程式管理許可權。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="1ca5f-106">這可讓您只對 Surface Hub 2 的作用域管理員許可權，並防止可能不需要的管理員存取整個 Azure AD 網域。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access an entire Azure AD domain.</span></span> <span data-ttu-id="1ca5f-107">開始之前，請確定您的 Surface Hub 秒已連接至 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="1ca5f-108">如果不是，您將需要重設 Surface Hub 2，並完成第一次、現成的 (OOBE) 安裝程式，加入宣告 Azure AD 的選項。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <span data-ttu-id="1ca5f-109">摘要</span><span class="sxs-lookup"><span data-stu-id="1ca5f-109">Summary</span></span> 

<span data-ttu-id="1ca5f-110">建立非全域系統管理員帳戶的套裝程式含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1ca5f-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="1ca5f-111">在 Microsoft Intune 中，建立包含指定要管理 Surface Hub 2 秒的管理員的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="1ca5f-112">使用 PowerShell 取得 Azure AD 群組 SID。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="1ca5f-113">建立包含 Azure AD 群組 SID 的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="1ca5f-114">建立包含由非全域系統管理員安全性群組管理的 Surface Hub 2 裝置的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="1ca5f-115">建立針對內含 Surface Hub 2 裝置之安全性群組的自訂設定檔。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <span data-ttu-id="1ca5f-116">建立 Azure AD 安全性群組</span><span class="sxs-lookup"><span data-stu-id="1ca5f-116">Create Azure AD security groups</span></span>

<span data-ttu-id="1ca5f-117">首先，建立包含管理員帳戶的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="1ca5f-118">然後為 Surface Hub 裝置建立另一個安全性群組。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-118">Then create another security group for Surface Hub devices.</span></span>  

### <span data-ttu-id="1ca5f-119">建立管理員帳戶的安全性群組</span><span class="sxs-lookup"><span data-stu-id="1ca5f-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="1ca5f-120">透過[Microsoft 端點管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)登入 Intune，選取 [**群組**  >  **新群組**] >，然後在 [群組類型] 底下，選取 [**安全性]。**</span><span class="sxs-lookup"><span data-stu-id="1ca5f-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="1ca5f-121">輸入組名（例如 **Surface Hub 本機管理員** ），然後選取 [ **建立]。**</span><span class="sxs-lookup"><span data-stu-id="1ca5f-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![建立中樞管理員的安全性群組](images/sh-create-sec-group.png)

3. <span data-ttu-id="1ca5f-123">開啟 [群組]，選取 [ **成員**]，然後選擇 [ **新增成員** ]，輸入您想要指定為「Surface Hub」的非全域管理員的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="1ca5f-124">若要深入瞭解如何在 Intune 中建立群組，請參閱  [新增群組以組織使用者和裝置](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <span data-ttu-id="1ca5f-125">建立 Surface Hub 2 裝置的安全性群組</span><span class="sxs-lookup"><span data-stu-id="1ca5f-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="1ca5f-126">重複上述程式來為中樞裝置建立個別的安全性群組;例如， **Surface Hub 裝置**。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![建立中樞裝置的安全性群組](images/sh-create-sec-group-devices.png) 

## <span data-ttu-id="1ca5f-128">使用 PowerShell 取得 Azure AD 群組 SID</span><span class="sxs-lookup"><span data-stu-id="1ca5f-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="1ca5f-129">使用提升的帳戶許可權啟動 PowerShell， (**以系統管理員身分執行**) ，並確保您的系統已設定為執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="1ca5f-130">若要深入瞭解，請參閱 [關於執行原則](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="1ca5f-131">[安裝 Azure PowerShell 模組](https://docs.microsoft.com/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="1ca5f-132">登入您的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="1ca5f-133">當您登入您的租使用者時，請執行下列 commandlet。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="1ca5f-134">它會提示您 [請輸入您的 Azure AD 群組的物件識別碼]。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="1ca5f-135">在 Intune 中，選取您先前建立的群組，然後複製物件識別碼，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![複製安全性群組的物件識別碼](images/sh-objectid.png)

6. <span data-ttu-id="1ca5f-137">執行下列 commandlet 來取得安全性群組的 SID：</span><span class="sxs-lookup"><span data-stu-id="1ca5f-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="1ca5f-138">將物件識別碼貼到 PowerShell commandlet 中，按 **enter**，然後將 **AZURE AD 群組 SID** 複製到文字編輯器。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <span data-ttu-id="1ca5f-139">建立包含 Azure AD 群組 SID 的 XML 檔</span><span class="sxs-lookup"><span data-stu-id="1ca5f-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="1ca5f-140">將下列內容複寫到文字編輯器中：</span><span class="sxs-lookup"><span data-stu-id="1ca5f-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="1ca5f-141">使用您的 **AZURE AD 群組 SID** 來取代以 S-1-12-1) 開頭的預留位置 (SID，然後將檔案儲存為 XML;例如， **aad-local-admin.xml**。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <span data-ttu-id="1ca5f-142">建立自訂設定檔</span><span class="sxs-lookup"><span data-stu-id="1ca5f-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="1ca5f-143">在端點管理員中，選取 [**裝置**設定配置  >  **檔**]  >  **建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="1ca5f-144">在 [平臺] 底下，選取 [ **Windows 10 及更新版本]。**</span><span class="sxs-lookup"><span data-stu-id="1ca5f-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="1ca5f-145">選取 [設定檔] 底下的 [ **自訂**]，然後選取 [ **建立]。**</span><span class="sxs-lookup"><span data-stu-id="1ca5f-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="1ca5f-146">新增名稱和描述，然後選取 **[下一步]。**</span><span class="sxs-lookup"><span data-stu-id="1ca5f-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="1ca5f-147">在 [**設定設定**  >  **OMA-URI 設定**] 底下，選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="1ca5f-148">在 [Add Row] （新增列）窗格中，新增名稱，然後在 [     **OMA URI**] 底下，新增下列字串：</span><span class="sxs-lookup"><span data-stu-id="1ca5f-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="1ca5f-149">在 [資料類型] 底下，選取 [ **字串 XML** ]，然後流覽以開啟您在上一個步驟中建立的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![上傳本機系統管理 xml 設定檔](images/sh-local-admin-config.png)

7. <span data-ttu-id="1ca5f-151">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-151">Click **Save**.</span></span>
8. <span data-ttu-id="1ca5f-152">按一下 [ **選取要包含的群組** ]，然後選擇 [您先前建立的安全性群組](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub 裝置**) 。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="1ca5f-153">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-153">Click **Next.**</span></span>
9. <span data-ttu-id="1ca5f-154">如有需要，請在 [適用性規則] 底下新增規則。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="1ca5f-155">否則，選取 **[下一步]** ，然後選取 [ **建立**]。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="1ca5f-156">若要深入瞭解使用 OMA-URI 字串自訂設定檔的詳細資訊，請參閱 [在 Intune 中使用適用于 Windows 10 裝置的自訂設定](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <span data-ttu-id="1ca5f-157">非全域管理員管理 Surface Hub 的2秒</span><span class="sxs-lookup"><span data-stu-id="1ca5f-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="1ca5f-158">**Surface hub 「本機管理員**」安全性群組的成員現在可以登入 surface hub 2 的 [設定] 應用程式，然後管理 [設定]。</span><span class="sxs-lookup"><span data-stu-id="1ca5f-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
