---
title: 在 Surface Hub 2S 上設定非全域系統管理員帳戶
description: 本文說明如何設定非全域系統管理員帳戶來管理 Surface Hub 2S。
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
ms.openlocfilehash: e16e4f8bd4b2b253233fa9790987287cf17966c7
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385171"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub-2s"></a><span data-ttu-id="77578-104">在 Surface Hub 2S 上設定非全域系統管理員帳戶</span><span class="sxs-lookup"><span data-stu-id="77578-104">Configure non Global admin accounts on Surface Hub 2S</span></span>

<span data-ttu-id="77578-105">當您將 Surface Hub 2S 加入 Azure AD 網域時，您可以設定非全域系統管理員帳戶，以限制 Surface Hub 2S 上的設定應用程式管理許可權。</span><span class="sxs-lookup"><span data-stu-id="77578-105">When you join Surface Hub 2S to an Azure AD domain, you can configure non Global admin accounts that limit permissions to management of the Settings app on Surface Hub 2S.</span></span> <span data-ttu-id="77578-106">這可讓您只將 Surface Hub 2S 的系統管理員許可權範圍範圍，並防止整個 Azure AD 網域可能不需要的系統管理員存取權。</span><span class="sxs-lookup"><span data-stu-id="77578-106">This enables you to scope admin permissions for Surface Hub 2S only and prevent potentially unwanted admin access across an entire Azure AD domain.</span></span> <span data-ttu-id="77578-107">開始之前，請確定 Surface Hub 2S 已加入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="77578-107">Before you begin, make sure your Surface Hub 2S is joined to Azure AD.</span></span> <span data-ttu-id="77578-108">如果沒有，您必須重設 Surface Hub 2S，並完成第一次開箱即用 (OOBE) 安裝程式，加入宣告 Azure AD 的選項。</span><span class="sxs-lookup"><span data-stu-id="77578-108">If not, you will need to reset Surface Hub 2S and complete the first-time, out-of-the-box (OOBE) setup program, choosing the option to join Azure AD.</span></span>

## <a name="summary"></a><span data-ttu-id="77578-109">摘要</span><span class="sxs-lookup"><span data-stu-id="77578-109">Summary</span></span> 

<span data-ttu-id="77578-110">建立非全域系統管理員帳戶的過程涉及下列步驟：</span><span class="sxs-lookup"><span data-stu-id="77578-110">The process of creating non Global admin accounts involves the following steps:</span></span> 

1. <span data-ttu-id="77578-111">在 Microsoft Intune 中，建立一個安全性群組，其中包含指定管理 Surface Hub 2S 的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="77578-111">In Microsoft Intune, create a Security group containing the admins designated to manage Surface Hub 2S.</span></span>
2. <span data-ttu-id="77578-112">使用 PowerShell 取得 Azure AD 群組 SID。</span><span class="sxs-lookup"><span data-stu-id="77578-112">Obtain Azure AD Group SID using PowerShell.</span></span>
3. <span data-ttu-id="77578-113">建立包含 Azure AD 群組 SID 的 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="77578-113">Create XML file containing Azure AD Group SID.</span></span>
4. <span data-ttu-id="77578-114">建立一個安全性群組，其中包含由非全域系統管理員安全性群組管理的 Surface Hub 2S 裝置。</span><span class="sxs-lookup"><span data-stu-id="77578-114">Create a Security Group containing the Surface Hub 2S devices that will be managed by the non-Global admins Security group.</span></span>
5. <span data-ttu-id="77578-115">建立自訂群組設定檔，以鎖定包含 Surface Hub 2S 裝置的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="77578-115">Create a custom Configuration profile targeting the security group that contains your Surface Hub 2S devices.</span></span> 


## <a name="create-azure-ad-security-groups"></a><span data-ttu-id="77578-116">建立 Azure AD 安全性群組</span><span class="sxs-lookup"><span data-stu-id="77578-116">Create Azure AD security groups</span></span>

<span data-ttu-id="77578-117">首先建立包含系統管理員帳戶的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="77578-117">First create a security group containing the admin accounts.</span></span> <span data-ttu-id="77578-118">然後為 Surface Hub 裝置建立另一個安全性群組。</span><span class="sxs-lookup"><span data-stu-id="77578-118">Then create another security group for Surface Hub devices.</span></span>  

### <a name="create-security-group-for-admin-accounts"></a><span data-ttu-id="77578-119">為系統管理員帳戶建立安全性群組</span><span class="sxs-lookup"><span data-stu-id="77578-119">Create security group for Admin accounts</span></span>

1. <span data-ttu-id="77578-120">透過[Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心進入 Intune，選取群組新群組>群組類型下\*\*\*\*  >  \*\* **，選取**安全性。\*\*</span><span class="sxs-lookup"><span data-stu-id="77578-120">Sign into Intune via the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431), select **Groups** > **New Group** > and under Group type, select **Security.**</span></span> 
2. <span data-ttu-id="77578-121">輸入組名 ，例如 **Surface Hub Local Admins，** 然後選取建立 **。**</span><span class="sxs-lookup"><span data-stu-id="77578-121">Enter a Group name -- for example, **Surface Hub Local Admins** -- and then select **Create.**</span></span> 

     ![為中樞系統管理員建立安全性群組](images/sh-create-sec-group.png)

3. <span data-ttu-id="77578-123">開啟群組，選取**成員**，然後選擇新增成員，\*\*\*\* 以在 Surface Hub 2S 上輸入要指定為非全域系統管理員的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="77578-123">Open the group, select **Members**, and then choose **Add members** to enter the Administrator accounts that you wish to designate as non Global admins on Surface Hub 2S.</span></span> <span data-ttu-id="77578-124">若要深入瞭解在 Intune 中建立群組，請參閱新增  [群組以整理使用者和裝置](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。</span><span class="sxs-lookup"><span data-stu-id="77578-124">To learn more about creating groups in Intune, see  [Add groups to organize users and devices](https://docs.microsoft.com/mem/intune/fundamentals/groups-add).</span></span>

### <a name="create-security-group-for-surface-hub-2s-devices"></a><span data-ttu-id="77578-125">為 Surface Hub 2S 裝置建立安全性群組</span><span class="sxs-lookup"><span data-stu-id="77578-125">Create security group for Surface Hub 2S devices</span></span>

1. <span data-ttu-id="77578-126">重複上述程式，為中樞裝置建立個別的安全性群組;例如 **Surface Hub 裝置**。</span><span class="sxs-lookup"><span data-stu-id="77578-126">Repeat the previous procedure to create a separate security group for Hub devices; for example, **Surface Hub devices**.</span></span> 

     ![為中樞裝置建立安全性群組](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a><span data-ttu-id="77578-128">使用 PowerShell 取得 Azure AD 群組 SID</span><span class="sxs-lookup"><span data-stu-id="77578-128">Obtain Azure AD Group SID using PowerShell</span></span>

1. <span data-ttu-id="77578-129">以提升的帳戶許可權啟動 PowerShell (**以** 系統管理員) 並確保您的系統已設置為執行 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="77578-129">Launch PowerShell with elevated account privileges (**Run as Administrator**) and ensure your system is configured to run PowerShell scripts.</span></span> <span data-ttu-id="77578-130">若要深入瞭解，請參閱關於 [執行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。</span><span class="sxs-lookup"><span data-stu-id="77578-130">To learn more, refer to [About Execution Policies](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?).</span></span> 
2. <span data-ttu-id="77578-131">[安裝 Azure PowerShell 模組](https://docs.microsoft.com/powershell/azure/install-az-ps)。</span><span class="sxs-lookup"><span data-stu-id="77578-131">[Install Azure PowerShell module](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>
3. <span data-ttu-id="77578-132">請登錄您的 Azure AD 租使用者。</span><span class="sxs-lookup"><span data-stu-id="77578-132">Sign into your Azure AD tenant.</span></span>

    ```powershell
    Connect-AzureAD
    ```

4. <span data-ttu-id="77578-133">當您已進入租使用者時，請執行下列命令小程式。</span><span class="sxs-lookup"><span data-stu-id="77578-133">When you're signed into your tenant, run the following commandlet.</span></span> <span data-ttu-id="77578-134">它會提示您「請輸入 Azure AD 群組的物件識別碼」。</span><span class="sxs-lookup"><span data-stu-id="77578-134">It will prompt you to "Please type the Object ID of your Azure AD Group."</span></span>

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. <span data-ttu-id="77578-135">在 Intune 中，選取您先前所建立群組，然後複製物件識別碼，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="77578-135">In Intune, select the group you created earlier and copy the Object id, as shown in the following figure.</span></span> 

     ![複製安全性群組的物件識別碼](images/sh-objectid.png)

6. <span data-ttu-id="77578-137">執行下列命令小程式以取得安全性群組之 SID：</span><span class="sxs-lookup"><span data-stu-id="77578-137">Run the following commandlet to get the security group's SID:</span></span>

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. <span data-ttu-id="77578-138">將物件識別碼貼到 PowerShell 命令小程式，按 **Enter，** 然後將 **Azure AD 群組 SID** 複製到文字編輯器中。</span><span class="sxs-lookup"><span data-stu-id="77578-138">Paste the Object id into the PowerShell commandlet, press **Enter**, and then copy the **Azure AD Group SID** into a text editor.</span></span> 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a><span data-ttu-id="77578-139">建立包含 Azure AD 群組 SID 的 XML 檔案</span><span class="sxs-lookup"><span data-stu-id="77578-139">Create XML file containing Azure AD Group SID</span></span>

1. <span data-ttu-id="77578-140">將下列內容複寫到文字編輯器中：</span><span class="sxs-lookup"><span data-stu-id="77578-140">Copy the following into a text editor:</span></span> 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. <span data-ttu-id="77578-141">將預留位置 SID (S-1-12-1) 取代為 Azure **AD Group SID，** 然後將檔案另存為 XML;例如 **，aad-local-admin.xml。**</span><span class="sxs-lookup"><span data-stu-id="77578-141">Replace the placeholder SID (beginning with S-1-12-1) with your **Azure AD Group SID** and then save the file as XML; for example, **aad-local-admin.xml**.</span></span> 

## <a name="create-custom-configuration-profile"></a><span data-ttu-id="77578-142">建立自訂群組設定檔</span><span class="sxs-lookup"><span data-stu-id="77578-142">Create Custom configuration profile</span></span>

1. <span data-ttu-id="77578-143">在端點管理員中，選取**裝置**  >  **組組設定檔**  >  **建立設定檔**。</span><span class="sxs-lookup"><span data-stu-id="77578-143">In Endpoint Manager, select **Devices** > **Configuration profiles** > **Create profile**.</span></span> 
2. <span data-ttu-id="77578-144">在平臺下 **選取 Windows 10 及更新版本。**</span><span class="sxs-lookup"><span data-stu-id="77578-144">Under Platform select **Windows 10 and later.**</span></span> <span data-ttu-id="77578-145">在設定檔下，選取 **自訂**，然後選取建立 **。**</span><span class="sxs-lookup"><span data-stu-id="77578-145">Under Profile, select **Custom**, and then select **Create.**</span></span>
3. <span data-ttu-id="77578-146">新增名稱和描述，然後選取下 **一步。**</span><span class="sxs-lookup"><span data-stu-id="77578-146">Add a name and description and then select **Next.**</span></span>
4. <span data-ttu-id="77578-147">在**設定設定**  >  **OMA-URI**設定\*\*\*\* 下，選取新增。</span><span class="sxs-lookup"><span data-stu-id="77578-147">Under **Configuration settings** > **OMA-URI Settings**, select **Add**.</span></span>
5. <span data-ttu-id="77578-148">在新增列窗格中新增名稱，在     **OMA-URI**下新增下列字串：</span><span class="sxs-lookup"><span data-stu-id="77578-148">In the Add Row pane, add a name and under     **OMA-URI**, add the following  string:</span></span> 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. <span data-ttu-id="77578-149">在資料類型下，選取 **字串 XML** 並流覽以開啟您于上一個步驟中建立 XML 檔案。</span><span class="sxs-lookup"><span data-stu-id="77578-149">Under Data type, select **String XML** and browse to open the XML file you created in the previous step.</span></span> 

     ![上傳本地系統管理員 xml 設定檔](images/sh-local-admin-config.png)

7. <span data-ttu-id="77578-151">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="77578-151">Click **Save**.</span></span>
8. <span data-ttu-id="77578-152">按一下 **[選取群組以包含**及選擇您先前在**Surface Hub**裝置[上 (](#create-security-group-for-surface-hub-2s-devices)的安全) 。</span><span class="sxs-lookup"><span data-stu-id="77578-152">Click **Select groups to include** and choose the [security group you created earlier](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub devices**).</span></span> <span data-ttu-id="77578-153">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="77578-153">Click **Next.**</span></span>
9. <span data-ttu-id="77578-154">在可適用性規則下，依需要新增規則。</span><span class="sxs-lookup"><span data-stu-id="77578-154">Under Applicability rules, add a Rule if desired.</span></span> <span data-ttu-id="77578-155">否則，請選取下**一步\*\*\*\*，然後選取**建立。</span><span class="sxs-lookup"><span data-stu-id="77578-155">Otherwise, select **Next** and then select **Create**.</span></span>

<span data-ttu-id="77578-156">若要深入瞭解使用 OMA-URI 字串的自訂群組設定設定檔，請參閱在 Intune 中為 [Windows 10 裝置使用自訂設定](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="77578-156">To learn more about custom configuration profiles using OMA-URI strings, see [Use custom settings for Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10).</span></span>


## <a name="non-global-admins-managing-surface-hub-2s"></a><span data-ttu-id="77578-157">管理 Surface Hub 2S 的非全域系統管理員</span><span class="sxs-lookup"><span data-stu-id="77578-157">Non Global admins managing Surface Hub 2S</span></span>

<span data-ttu-id="77578-158">Surface **Hub Local Admins** Security 群組的成員現在可以在 Surface Hub 2S 上，以登錄設定應用程式並管理設定。</span><span class="sxs-lookup"><span data-stu-id="77578-158">Members of the **Surface Hub Local Admins** Security group can now sign in to the Settings app on Surface Hub 2S and manage settings.</span></span>
