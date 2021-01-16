---
title: 使用 SEMM (Surface) 來註冊及設定 Surface 裝置
description: 瞭解如何建立 Surface UEFI 配置套件來控制 Surface UEFI 的設定，以及在 SEMM 中註冊 Surface 裝置。
keywords: surface enterprise 管理
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: hachinda
manager: laurawi
ms.date: 1/15/2021
ms.openlocfilehash: f310b4a43a8a0fc0e77295344ac723770ce821bc
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271060"
---
# <span data-ttu-id="a326c-104">使用 SEMM 註冊及設定 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="a326c-104">Enroll and configure Surface devices with SEMM</span></span>

<span data-ttu-id="a326c-105">使用 Microsoft Surface Enterprise 管理模式 (SEMM) ，您可以在 Surface 裝置上安全地設定 Surface UEFI 的設定，並在組織中的 Surface 裝置上管理這些設定。</span><span class="sxs-lookup"><span data-stu-id="a326c-105">With Microsoft Surface Enterprise Management Mode (SEMM), you can securely configure the settings of Surface UEFI on a Surface device and manage those settings on Surface devices in your organization.</span></span> <span data-ttu-id="a326c-106">當 Surface 裝置由 SEMM 管理時，該裝置會被視為已 *註冊* ， (有時稱為「已啟用) 」。</span><span class="sxs-lookup"><span data-stu-id="a326c-106">When a Surface device is managed by SEMM, that device is considered to be *enrolled* (sometimes referred to as activated).</span></span> <span data-ttu-id="a326c-107">本文說明如何建立 Surface UEFI 配置套件，該套件不僅可控制 Surface UEFI 的設定，也會在 SEMM 中註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="a326c-107">This article shows you how to create a Surface UEFI configuration package that will not only control the settings of Surface UEFI, but will also enroll a Surface device in SEMM.</span></span>

<span data-ttu-id="a326c-108">如需 SEMM 的更高層次概覽，請參閱 [Microsoft Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="a326c-108">For a more high-level overview of SEMM, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

<span data-ttu-id="a326c-109">就 SEMM 而言，較新的 Surface 裝置支援透過 Microsoft Intune 來遠端系統管理部分固件設定。</span><span class="sxs-lookup"><span data-stu-id="a326c-109">As an alternative to SEMM, newer Surface devices support remote management of a subset of firmware settings via Microsoft Intune.</span></span> <span data-ttu-id="a326c-110">如需詳細資訊，請參閱 [SURFACE UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="a326c-110">For more information,refer to [Intune management of Surface UEFI settings](surface-manage-dfci-guide.md).</span></span>

> [!NOTE]
> <span data-ttu-id="a326c-111">僅透過 UEFI Manager 支援 Surface Pro X 的 SEMM。</span><span class="sxs-lookup"><span data-stu-id="a326c-111">SEMM is supported on Surface Pro X via the UEFI Manager only.</span></span> <span data-ttu-id="a326c-112">如需詳細資訊，請參閱 [部署、管理及維護 Surface Pro X](surface-pro-arm-app-management.md)。</span><span class="sxs-lookup"><span data-stu-id="a326c-112">For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md).</span></span>

#### <span data-ttu-id="a326c-113">下載並安裝 Microsoft Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="a326c-113">Download and install Microsoft Surface UEFI Configurator</span></span>

<span data-ttu-id="a326c-114">用來建立 SEMM 套件的工具是 Microsoft Surface UEFI 設定檔。</span><span class="sxs-lookup"><span data-stu-id="a326c-114">The tool used to create SEMM packages is Microsoft Surface UEFI Configurator.</span></span> <span data-ttu-id="a326c-115">您可以從 Microsoft 下載中心的 [ [表面工具](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面下載 MICROSOFT Surface UEFI 設定檔。</span><span class="sxs-lookup"><span data-stu-id="a326c-115">You can download Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span>
<span data-ttu-id="a326c-116">執行 Microsoft Surface UEFI 設定檔 Windows 安裝程式 ( .msi) 檔案以開始安裝工具。</span><span class="sxs-lookup"><span data-stu-id="a326c-116">Run the Microsoft Surface UEFI Configurator Windows Installer (.msi) file to start the installation of the tool.</span></span> <span data-ttu-id="a326c-117">安裝程式完成後，請在 [開始] 功能表的 [所有應用程式] 區段中尋找 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="a326c-117">When the installer completes, find Microsoft Surface UEFI Configurator in the All Apps section of your Start menu.</span></span>

>[!NOTE]
><span data-ttu-id="a326c-118">只有 Windows 10 支援 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="a326c-118">Microsoft Surface UEFI Configurator is supported only on Windows 10.</span></span>

## <span data-ttu-id="a326c-119">建立 Surface UEFI 配置套件</span><span class="sxs-lookup"><span data-stu-id="a326c-119">Create a Surface UEFI configuration package</span></span>

<span data-ttu-id="a326c-120">Surface UEFI 配置套件會執行將 Surface UEFI 設定的新設定套用到 SEMM 中 SEMM 的 Surface 裝置，以及在中註冊 Surface 裝置的角色。</span><span class="sxs-lookup"><span data-stu-id="a326c-120">The Surface UEFI configuration package performs both the role of applying a new configuration of Surface UEFI settings to a Surface device managed with SEMM and the role of enrolling Surface devices in SEMM.</span></span> <span data-ttu-id="a326c-121">建立配置套件時，您必須具備與 SEMM 搭配使用的簽署憑證，以保護每個 Surface 裝置上的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="a326c-121">The creation of a configuration package requires you to have a signing certificate to be used with SEMM to secure the configuration of UEFI settings on each Surface device.</span></span> <span data-ttu-id="a326c-122">如需有關 SEMM 憑證需求的詳細資訊，請參閱 [Microsoft Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="a326c-122">For more information about the requirements for the SEMM certificate, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

<span data-ttu-id="a326c-123">若要建立 Surface UEFI 配置套件，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="a326c-123">To create a Surface UEFI configuration package, follow these steps:</span></span>

1. <span data-ttu-id="a326c-124">從 [開始] 功能表開啟 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="a326c-124">Open Microsoft Surface UEFI Configurator from the Start menu.</span></span>
2. <span data-ttu-id="a326c-125">按一下 **\[開始\]**。</span><span class="sxs-lookup"><span data-stu-id="a326c-125">Click **Start**.</span></span>
3. <span data-ttu-id="a326c-126">按一下 [設定 **套件**]，如圖1所示。</span><span class="sxs-lookup"><span data-stu-id="a326c-126">Click **Configuration Package**, as shown in Figure 1.</span></span>

   ![建立 SEMM 註冊套件](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *<span data-ttu-id="a326c-128">圖 1。</span><span class="sxs-lookup"><span data-stu-id="a326c-128">Figure 1.</span></span> <span data-ttu-id="a326c-129">選取 [設定套件]，建立 SEMM 註冊與設定的套件</span><span class="sxs-lookup"><span data-stu-id="a326c-129">Select Configuration Package to create a package for SEMM enrollment and configuration</span></span>*

4. <span data-ttu-id="a326c-130">按一下 [ **憑證保護** ] 以新增您匯出的憑證檔案，其中包含私密金鑰 ( .pfx) ，如圖2所示。</span><span class="sxs-lookup"><span data-stu-id="a326c-130">Click **Certificate Protection** to add your exported certificate file with private key (.pfx), as shown in Figure 2.</span></span> <span data-ttu-id="a326c-131">流覽到您憑證檔案的位置，選取檔案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a326c-131">Browse to the location of your certificate file, select the file, and then click **OK**.</span></span>

   ![將 SEM 憑證和 Surface UEFI 密碼新增至 [配置套件]](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *<span data-ttu-id="a326c-133">圖 2.</span><span class="sxs-lookup"><span data-stu-id="a326c-133">Figure 2.</span></span> <span data-ttu-id="a326c-134">將 SEMM 憑證和 Surface UEFI 密碼新增至 Surface UEFI 配置套件</span><span class="sxs-lookup"><span data-stu-id="a326c-134">Add the SEMM certificate and Surface UEFI password to a Surface UEFI configuration package</span></span>*

5. <span data-ttu-id="a326c-135">當系統提示您確認憑證密碼時，請輸入並確認您的憑證檔案密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a326c-135">When you are prompted to confirm the certificate password, enter and confirm the password for your certificate file, and then click **OK**.</span></span>
6. <span data-ttu-id="a326c-136">按一下 [ **密碼保護** ]，將密碼新增至 Surface UEFI。</span><span class="sxs-lookup"><span data-stu-id="a326c-136">Click **Password Protection** to add a password to Surface UEFI.</span></span> <span data-ttu-id="a326c-137">每當您引導至 UEFI 時，就會需要此密碼。</span><span class="sxs-lookup"><span data-stu-id="a326c-137">This password will be required whenever you boot to UEFI.</span></span> <span data-ttu-id="a326c-138">如果未輸入此密碼，則只會顯示 **電腦資訊**、[ **關於**]、[ **企業管理** **] 和 [** 結束] 頁面。</span><span class="sxs-lookup"><span data-stu-id="a326c-138">If this password is not entered, only the **PC information**, **About**, **Enterprise management**, and **Exit** pages will be displayed.</span></span> <span data-ttu-id="a326c-139">這是選用步驟。</span><span class="sxs-lookup"><span data-stu-id="a326c-139">This step is optional.</span></span>
7. <span data-ttu-id="a326c-140">出現提示時，請輸入並確認您所選取的 Surface UEFI 密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a326c-140">When you are prompted, enter and confirm your chosen password for Surface UEFI, and then click **OK**.</span></span> <span data-ttu-id="a326c-141">如果您要清除現有的 Surface UEFI 密碼，請將密碼欄位留白。</span><span class="sxs-lookup"><span data-stu-id="a326c-141">If you want to clear an existing Surface UEFI password, leave the password field blank.</span></span>
8. <span data-ttu-id="a326c-142">如果您不想要將 Surface UEFI 套件套用到特定裝置，請在 [ **選擇您想要設定目標的表面類型** ] 頁面上，按一下對應 Surface Book 或 Surface Pro 4 影像底下的滑杆，使其位於 [ **關閉** ] 位置。</span><span class="sxs-lookup"><span data-stu-id="a326c-142">If you do not want the Surface UEFI package to apply to a particular device, on the **Choose which Surface type you want to target** page, click the slider beneath the corresponding Surface Book or Surface Pro 4 image so that it is in the **Off** position.</span></span> <span data-ttu-id="a326c-143"> (如圖3所示。 ) </span><span class="sxs-lookup"><span data-stu-id="a326c-143">(As shown in Figure 3.)</span></span>
   > [!NOTE] 
   > <span data-ttu-id="a326c-144">預設會選取 [沒有] 時，您必須選取 [裝置]。</span><span class="sxs-lookup"><span data-stu-id="a326c-144">You must select a device as none are selected by default.</span></span>

   ![選擇要封裝相容性的裝置](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *<span data-ttu-id="a326c-146">圖 3.</span><span class="sxs-lookup"><span data-stu-id="a326c-146">Figure 3.</span></span> <span data-ttu-id="a326c-147">選擇要封裝相容性的裝置</span><span class="sxs-lookup"><span data-stu-id="a326c-147">Choose the devices for package compatibility</span></span>*

9. <span data-ttu-id="a326c-148">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="a326c-148">Click **Next**.</span></span>
10. <span data-ttu-id="a326c-149">如果您想要停用受管理的 Surface 裝置上的元件，請在 [ **選擇您要啟用或停用的元件** ] 頁面上，按一下您想要停用之任何裝置或裝置群組旁邊的滑杆，以使滑杆位於 [ **關閉** ] 位置。</span><span class="sxs-lookup"><span data-stu-id="a326c-149">If you want to deactivate a component on managed Surface devices, on the **Choose which components you want to activate or deactivate** page, click the slider next to any device or group of devices you want to deactivate so that the slider is in the **Off** position.</span></span> <span data-ttu-id="a326c-150">圖4所示的 (。 ) 每個裝置的預設設定為 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="a326c-150">(Shown in Figure 4.) The default configuration for each device is **On**.</span></span> <span data-ttu-id="a326c-151">如果您想要將所有滑杆回到預設位置，請按一下 [ **重設** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a326c-151">Click the **Reset** button if you want to return all sliders to the default position.</span></span>

    ![停用或啟用 Surface 元件](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *<span data-ttu-id="a326c-153">圖 4.</span><span class="sxs-lookup"><span data-stu-id="a326c-153">Figure 4.</span></span> <span data-ttu-id="a326c-154">停用或啟用個別 Surface 元件</span><span class="sxs-lookup"><span data-stu-id="a326c-154">Disable or enable individual Surface components</span></span>*

11. <span data-ttu-id="a326c-155">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="a326c-155">Click **Next**.</span></span>
12. <span data-ttu-id="a326c-156">若要在 Surface UEFI 中啟用或停用高級選項，或顯示 Surface UEFI 頁面，請在 [ **選擇裝置的高級設定** ] 頁面上，按一下 [所需設定] 旁的滑杆，以將該選項設定為 [ **開啟** ] 或 [ **關閉** 圖 5) 中所示的 (。</span><span class="sxs-lookup"><span data-stu-id="a326c-156">To enable or disable advanced options in Surface UEFI or the display of Surface UEFI pages, on the **Choose the advanced settings for your devices** page, click the slider beside the desired setting to configure that option to **On** or **Off** (shown in Figure 5).</span></span> <span data-ttu-id="a326c-157">在 [ **UEFI 首頁** ] 區段中，您可以使用 [ **安全性**]、[ **裝置**] 和 [ **啟動** ] 滑杆來控制啟動至 Surface UEFI 的使用者所能使用的頁面。</span><span class="sxs-lookup"><span data-stu-id="a326c-157">In the **UEFI Front Page** section, you can use the sliders for **Security**, **Devices**, and **Boot** to control what pages are available to users who boot into Surface UEFI.</span></span> <span data-ttu-id="a326c-158"> (如需 Surface UEFI 設定的詳細資訊，請參閱 [管理 SURFACE uefi 設定](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)。當您完成選取選項來產生並儲存套件時，請 ) 按一下 [ **組建** ]。</span><span class="sxs-lookup"><span data-stu-id="a326c-158">(For more information about Surface UEFI settings, see [Manage Surface UEFI settings](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings).) Click **Build** when you have finished selecting options to generate and save the package.</span></span>

    ![控制高級 Surface UEFI 設定和 Surface UEFI 頁面](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *<span data-ttu-id="a326c-160">圖 5.</span><span class="sxs-lookup"><span data-stu-id="a326c-160">Figure 5.</span></span> <span data-ttu-id="a326c-161">使用 SEMM 控制高級 Surface UEFI 設定和 Surface UEFI 頁面</span><span class="sxs-lookup"><span data-stu-id="a326c-161">Control advanced Surface UEFI settings and Surface UEFI pages with SEMM</span></span>*

13. <span data-ttu-id="a326c-162">在 [ **另存** 新檔] 對話方塊中，指定 Surface UEFI 配置套件的名稱，流覽至您要儲存檔案的位置，然後按一下 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="a326c-162">In the **Save As** dialog box, specify a name for the Surface UEFI configuration package, browse to the location where you would like to save the file, and then click **Save**.</span></span>
14. <span data-ttu-id="a326c-163">建立並儲存套件後，就會顯示 **成功** 的頁面。</span><span class="sxs-lookup"><span data-stu-id="a326c-163">When the package is created and saved, the **Successful** page is displayed.</span></span>

>[!NOTE]
><span data-ttu-id="a326c-164">記錄此頁面上顯示的憑證指紋字元，如圖6所示。</span><span class="sxs-lookup"><span data-stu-id="a326c-164">Record the certificate thumbprint characters that are displayed on this page, as shown in Figure 6.</span></span> <span data-ttu-id="a326c-165">您將需要這些字元，以確認在 SEMM 中註冊新的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="a326c-165">You will need these characters to confirm enrollment of new Surface devices in SEMM.</span></span> <span data-ttu-id="a326c-166">按一下 [ **結束** ] 以完成套件建立，然後關閉 MICROSOFT Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="a326c-166">Click **End** to complete package creation and close Microsoft Surface UEFI Configurator.</span></span>

![顯示憑證指紋字元](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*<span data-ttu-id="a326c-168">圖 6.</span><span class="sxs-lookup"><span data-stu-id="a326c-168">Figure 6.</span></span> <span data-ttu-id="a326c-169">證書指紋的最後兩個字元會顯示在成功的頁面上</span><span class="sxs-lookup"><span data-stu-id="a326c-169">The last two characters of the certificate thumbprint are displayed on the Successful page</span></span>*

<span data-ttu-id="a326c-170">現在您已經建立 Surface UEFI 配置套件，您可以註冊或設定 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="a326c-170">Now that you have created your Surface UEFI configuration package, you can enroll or configure Surface devices.</span></span>

>[!NOTE]
><span data-ttu-id="a326c-171">建立 Surface UEFI 配置套件時，會在桌面上建立記錄檔案，並提供 [設定套件設定] 和 [選項] 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="a326c-171">When a Surface UEFI configuration package is created, a log file is created on the desktop with details of the configuration package settings and options.</span></span>

## <span data-ttu-id="a326c-172">在 SEMM 中註冊 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="a326c-172">Enroll a Surface device in SEMM</span></span>
<span data-ttu-id="a326c-173">在執行 Surface UEFI 設定套件時，會在 Surface 裝置的固件儲存區中暫存 SEMM 憑證和 Surface UEFI 配置檔案。</span><span class="sxs-lookup"><span data-stu-id="a326c-173">When the Surface UEFI configuration package is executed, the SEMM certificate and Surface UEFI configuration files are staged in the firmware storage of the Surface device.</span></span> <span data-ttu-id="a326c-174">當 Surface 裝置重新開機時，Surface UEFI 會處理這些檔案，並開始應用 Surface UEFI 設定或在 SEMM 中註冊 Surface 裝置的程式，如圖7所示。</span><span class="sxs-lookup"><span data-stu-id="a326c-174">When the Surface device reboots, Surface UEFI processes these files and begins the process of applying the Surface UEFI configuration or enrolling the Surface device in SEMM, as shown in Figure 7.</span></span>

![SEMM 處理常式以取得 Surface UEFI 或登記的配置](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*<span data-ttu-id="a326c-176">圖 7.</span><span class="sxs-lookup"><span data-stu-id="a326c-176">Figure 7.</span></span> <span data-ttu-id="a326c-177">配置 Surface UEFI 或對 Surface 裝置進行註冊的 SEMM 處理常式</span><span class="sxs-lookup"><span data-stu-id="a326c-177">The SEMM process for configuration of Surface UEFI or enrollment of a Surface device</span></span>*

<span data-ttu-id="a326c-178">在您開始在 SEMM 中註冊 Surface 裝置之前，請先確定您已有證書指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="a326c-178">Before you begin the process to enroll a Surface device in SEMM, ensure that you have the last two characters of the certificate thumbprint on hand.</span></span> <span data-ttu-id="a326c-179">您將需要這些字元來確認裝置的註冊 (請參閱圖 6) 。</span><span class="sxs-lookup"><span data-stu-id="a326c-179">You will need these characters to confirm the device’s enrollment (see Figure 6).</span></span>

<span data-ttu-id="a326c-180">若要在 SEMM 中使用 Surface UEFI 設定套件註冊 Surface 裝置，請依照下列步驟進行：</span><span class="sxs-lookup"><span data-stu-id="a326c-180">To enroll a Surface device in SEMM with a Surface UEFI configuration package, follow these steps:</span></span>

1. <span data-ttu-id="a326c-181">在您想要在 SEMM 註冊的 Surface 裝置上執行 Surface UEFI 配置套件 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="a326c-181">Run the Surface UEFI configuration package .msi file on the Surface device you want to enroll in SEMM.</span></span> <span data-ttu-id="a326c-182">這會在裝置的固件中設定 Surface UEFI 設定檔。</span><span class="sxs-lookup"><span data-stu-id="a326c-182">This will provision the Surface UEFI configuration file in the device’s firmware.</span></span>
2. <span data-ttu-id="a326c-183">選取 [ **我接受授權合約中的條款** ] 核取方塊，以接受使用者授權合約 (EULA) ，然後按一下 [ **安裝** ] 以開始安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a326c-183">Select the **I accept the terms in the License Agreement** check box to accept the End User License Agreement (EULA), and then click **Install** to begin the installation process.</span></span>
3. <span data-ttu-id="a326c-184">按一下 **[完成]** 以完成 surface UEFI 設定套件安裝，當系統提示您時，請重新開機 surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="a326c-184">Click **Finish** to complete the Surface UEFI configuration package installation and restart the Surface device when you are prompted to do so.</span></span>
4. <span data-ttu-id="a326c-185">Surface UEFI 將載入設定檔案，並判斷裝置上未啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="a326c-185">Surface UEFI will load the configuration file and determine that SEMM is not enabled on the device.</span></span> <span data-ttu-id="a326c-186">然後，Surface UEFI 就會開始 SEMM 註冊程式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="a326c-186">Surface UEFI will then begin the SEMM enrollment process, as follows:</span></span>
   * <span data-ttu-id="a326c-187">Surface UEFI 將確認 SEMM 設定檔包含 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="a326c-187">Surface UEFI will verify that the SEMM configuration file contains a SEMM certificate.</span></span>
   * <span data-ttu-id="a326c-188">Surface UEFI 會提示您輸入憑證指紋的最後兩個字元，以確認在 SEMM 中註冊 Surface 裝置，如圖8所示。</span><span class="sxs-lookup"><span data-stu-id="a326c-188">Surface UEFI will prompt you to enter the last two characters of the certificate thumbprint to confirm enrollment of the Surface device in SEMM, as shown in Figure 8.</span></span>

      ![SEMM 註冊需要證書指紋的最後兩個字元](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *<span data-ttu-id="a326c-190">圖 8.</span><span class="sxs-lookup"><span data-stu-id="a326c-190">Figure 8.</span></span> <span data-ttu-id="a326c-191">在 SEMM 中註冊需要證書指紋的最後兩個字元</span><span class="sxs-lookup"><span data-stu-id="a326c-191">Enrollment in SEMM requires the last two characters of the certificate thumbprint</span></span>*

   * <span data-ttu-id="a326c-192">Surface UEFI 會將 SEMM 憑證儲存在固件中，並套用在 Surface UEFI 設定檔中指定的設定設定。</span><span class="sxs-lookup"><span data-stu-id="a326c-192">Surface UEFI will store the SEMM certificate in firmware and apply the configuration settings that are specified in the Surface UEFI configuration file.</span></span>
   
5. <span data-ttu-id="a326c-193">表面裝置現在已註冊為 SEMM，並會啟動至 Windows。</span><span class="sxs-lookup"><span data-stu-id="a326c-193">The Surface device is now enrolled in SEMM and will boot to Windows.</span></span>

<span data-ttu-id="a326c-194">您可以在 [**程式和 (功能**] 中尋找 [ **Microsoft surface Configuration 套件**]，以確認 Surface 裝置已順利登入 SEMM，如圖 9) 所示，或儲存在**Microsoft surface UEFI**設定檔記錄中的事件中，在 [事件檢視器] 中的 [**應用程式和服務記錄** (] 下找到，如圖 10) 所示。</span><span class="sxs-lookup"><span data-stu-id="a326c-194">You can verify that a Surface device has been successfully enrolled in SEMM by looking for **Microsoft Surface Configuration Package** in **Programs and Features** (as shown in Figure 9), or in the events stored in the **Microsoft Surface UEFI Configurator** log, found under **Applications and Services Logs** in Event Viewer (as shown in Figure 10).</span></span>

![驗證程式和功能 SEMM 中的 Surface 裝置註冊](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*<span data-ttu-id="a326c-196">圖 9.</span><span class="sxs-lookup"><span data-stu-id="a326c-196">Figure 9.</span></span> <span data-ttu-id="a326c-197">確認在 [程式和功能] 中的 SEMM 中註冊 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="a326c-197">Verify the enrollment of a Surface device in SEMM in Programs and Features</span></span>*

![驗證在事件檢視器的 SEMM 中註冊 Surface 裝置](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*<span data-ttu-id="a326c-199">圖 10.</span><span class="sxs-lookup"><span data-stu-id="a326c-199">Figure 10.</span></span> <span data-ttu-id="a326c-200">驗證在事件檢視器的 SEMM 中註冊 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="a326c-200">Verify the enrollment of a Surface device in SEMM in Event Viewer</span></span>*

<span data-ttu-id="a326c-201">您也可以確認裝置已註冊在 Surface UEFI 中 SEMM，而 Surface UEFI 將包含 **企業管理** 頁面 (如圖 11) 所示。</span><span class="sxs-lookup"><span data-stu-id="a326c-201">You can also verify that the device is enrolled in SEMM in Surface UEFI – while the device is enrolled, Surface UEFI will contain the **Enterprise management** page (as shown in Figure 11).</span></span>

![Surface UEFI 企業版管理頁面](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*<span data-ttu-id="a326c-203">圖 11.</span><span class="sxs-lookup"><span data-stu-id="a326c-203">Figure 11.</span></span> <span data-ttu-id="a326c-204">Surface UEFI 企業版管理頁面</span><span class="sxs-lookup"><span data-stu-id="a326c-204">The Surface UEFI Enterprise management page</span></span>*


## <span data-ttu-id="a326c-205">使用 SEMM 設定 Surface UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="a326c-205">Configure Surface UEFI settings with SEMM</span></span>

<span data-ttu-id="a326c-206">在 SEMM 中註冊裝置之後，您可以執行使用相同 SEMM 憑證簽署的 Surface UEFI 配置套件，以套用新的 Surface UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="a326c-206">After a device is enrolled in SEMM, you can run Surface UEFI configuration packages signed with the same SEMM certificate to apply new Surface UEFI settings.</span></span> <span data-ttu-id="a326c-207">在下次啟動裝置時，系統會自動套用這些設定，而不需要使用者進行任何互動。</span><span class="sxs-lookup"><span data-stu-id="a326c-207">These settings are applied automatically the next time the device boots, without any interaction from the user.</span></span> <span data-ttu-id="a326c-208">您可以使用應用程式部署解決方案（例如 Microsoft 端點設定管理員），將 Surface UEFI 配置套件部署到 Surface 裝置，以變更或管理 Surface UEFI 中的設定。</span><span class="sxs-lookup"><span data-stu-id="a326c-208">You can use application deployment solutions like Microsoft Endpoint Configuration Manager to deploy Surface UEFI configuration packages to Surface devices to change or manage the settings in Surface UEFI.</span></span>

<span data-ttu-id="a326c-209">如需有關如何使用 Configuration Manager 部署 Windows Installer ( .msi) 檔案的詳細資訊，請參閱使用 [Microsoft 端點 Configuration Manager 部署及管理應用程式](https://technet.microsoft.com/library/mt627959)。</span><span class="sxs-lookup"><span data-stu-id="a326c-209">For more information about how to deploy Windows Installer (.msi) files with Configuration Manager, see [Deploy and manage applications with Microsoft Endpoint Configuration Manager](https://technet.microsoft.com/library/mt627959).</span></span>

<span data-ttu-id="a326c-210">如果您有安全的 Surface UEFI 與密碼，則不含嘗試引導至 Surface UEFI 之密碼的使用者，將只會顯示**電腦資訊**、[**關於**]、[**企業管理**]，以及 [結束 **] 頁面。**</span><span class="sxs-lookup"><span data-stu-id="a326c-210">If you have secured Surface UEFI with a password, users without the password who attempt to boot to Surface UEFI will only have the **PC information**, **About**, **Enterprise management**, and **Exit** pages displayed to them.</span></span>

<span data-ttu-id="a326c-211">如果您使用的是密碼或使用者正確輸入密碼時沒有安全的 Surface UEFI，則使用 SEMM 設定的設定會變暗， (無法使用]) 且您組織所管理的一些設定的文字會顯示在頁面頂端，如圖12所示。</span><span class="sxs-lookup"><span data-stu-id="a326c-211">If you have not secured Surface UEFI with a password or a user enters the password correctly, settings that are configured with SEMM will be dimmed (unavailable) and the text Some settings are managed by your organization will be displayed at the top of the page, as shown in Figure 12.</span></span>

![在 Surface UEFI 中停用 SEMM 管理的設定](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*<span data-ttu-id="a326c-213">圖 12.</span><span class="sxs-lookup"><span data-stu-id="a326c-213">Figure 12.</span></span> <span data-ttu-id="a326c-214">SEMM 管理的設定將會在 Surface UEFI 中停用</span><span class="sxs-lookup"><span data-stu-id="a326c-214">Settings managed by SEMM will be disabled in Surface UEFI</span></span>*
