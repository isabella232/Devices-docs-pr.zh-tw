---
title: '使用 Microsoft 端點設定管理員來管理含 SEMM (Surface 的裝置) '
description: 瞭解如何使用端點建構管理員來管理 Microsoft Surface Enterprise 管理模式 (SEMM) 。
keywords: 註冊、更新、腳本、設定
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/13/2020
ms.openlocfilehash: bfd10df3bb7a7dd031c1719d4191ffc46418c4e3
ms.sourcegitcommit: 30c1eb469610dfd2ad9169c154ca07e565240fdb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117849"
---
# <span data-ttu-id="50e94-104">搭配 SEMM 使用 Microsoft Endpoint Configuration Manager 管理裝置</span><span class="sxs-lookup"><span data-stu-id="50e94-104">Use Microsoft Endpoint Configuration Manager to manage devices with SEMM</span></span>

<span data-ttu-id="50e94-105">「Microsoft Surface Enterprise 管理」模式 (SEMM Surface UEFI 裝置的) 功能，可讓系統管理員管理並協助保護 Surface UEFI 設定的配置。</span><span class="sxs-lookup"><span data-stu-id="50e94-105">The Microsoft Surface Enterprise Management Mode (SEMM) feature of Surface UEFI devices lets administrators manage and help secure the configuration of Surface UEFI settings.</span></span> <span data-ttu-id="50e94-106">對於大多陣列織而言，這個程式是透過使用 Microsoft Surface UEFI 設定檔工具建立 Windows Installer ( .msi) 套件來完成。</span><span class="sxs-lookup"><span data-stu-id="50e94-106">For most organizations, this process is accomplished by creating Windows Installer (.msi) packages with the Microsoft Surface UEFI Configurator tool.</span></span> <span data-ttu-id="50e94-107">接著，這些套件會執行或部署至用戶端 Surface 裝置，以在 SEMM 中註冊裝置，並更新 Surface UEFI 設定設定。</span><span class="sxs-lookup"><span data-stu-id="50e94-107">These packages are then run or deployed to the client Surface devices to enroll the devices in SEMM and to update the Surface UEFI settings configuration.</span></span>

<span data-ttu-id="50e94-108">對於有 Microsoft 端點設定管理員的組織，您可以使用 Microsoft Surface UEFI 配置處理常式 .msi 程式來部署及管理 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-108">For organizations with Microsoft Endpoint Configuration Manager there is an alternative to using the Microsoft Surface UEFI Configurator .msi process to deploy and administer SEMM.</span></span> <span data-ttu-id="50e94-109">Microsoft Surface UEFI 管理員是一種羽量級安裝程式，可讓您在裝置上提供 SEMM 管理所需的元件。</span><span class="sxs-lookup"><span data-stu-id="50e94-109">Microsoft Surface UEFI Manager is a lightweight installer that makes required assemblies for SEMM management available on a device.</span></span> <span data-ttu-id="50e94-110">透過在受管理的用戶端上安裝這些元件與 Microsoft Surface UEFI 管理器，SEMM 可以由 Configuration Manager 使用 PowerShell 腳本管理，並部署為應用程式。</span><span class="sxs-lookup"><span data-stu-id="50e94-110">By installing these assemblies with Microsoft Surface UEFI Manager on a managed client, SEMM can be administered by Configuration Manager with PowerShell scripts, deployed as applications.</span></span> <span data-ttu-id="50e94-111">在這個程式中，SEMM 管理是在 Configuration Manager 中執行，因此不需要外部 Microsoft Surface UEFI 組態工具。</span><span class="sxs-lookup"><span data-stu-id="50e94-111">With this process, SEMM management is performed within Configuration Manager, which eliminates the need for the external Microsoft Surface UEFI Configurator tool.</span></span>

> [!Note]
> <span data-ttu-id="50e94-112">雖然本文所述的程式可能適用于舊版的 Endpoint Configuration Manager 或其他協力廠商管理解決方案，但只有端點設定管理員的目前分支支援使用 Microsoft Surface UEFI 管理員和 PowerShell 的 SEMM 管理。</span><span class="sxs-lookup"><span data-stu-id="50e94-112">Although the process described in this article may work with earlier versions of Endpoint Configuration Manager or with other third-party management solutions, management of SEMM with Microsoft Surface UEFI Manager and PowerShell is supported only with the Current Branch of Endpoint Configuration Manager.</span></span>

#### <span data-ttu-id="50e94-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="50e94-113">Prerequisites</span></span>

<span data-ttu-id="50e94-114">開始本文所述的程式之前，請先熟悉下列技術與工具：</span><span class="sxs-lookup"><span data-stu-id="50e94-114">Before you begin the process outlined in this article, familiarize yourself with the following technologies and tools:</span></span>

* [<span data-ttu-id="50e94-115">Surface UEFI</span><span class="sxs-lookup"><span data-stu-id="50e94-115">Surface UEFI</span></span>](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [<span data-ttu-id="50e94-116">Surface 企業管理模式 (SEMM)</span><span class="sxs-lookup"><span data-stu-id="50e94-116">Surface Enterprise Management Mode (SEMM)</span></span>](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [<span data-ttu-id="50e94-117">PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="50e94-117">PowerShell scripting</span></span>](https://technet.microsoft.com/scriptcenter/dd742419)
* [<span data-ttu-id="50e94-118">System Center Configuration Manager 應用程式部署</span><span class="sxs-lookup"><span data-stu-id="50e94-118">System Center Configuration Manager application deployment</span></span>](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* <span data-ttu-id="50e94-119">憑證管理</span><span class="sxs-lookup"><span data-stu-id="50e94-119">Certificate management</span></span>

> [!Note]
> <span data-ttu-id="50e94-120">您也需要使用您想要用來保護 SEMM 的憑證的存取權。</span><span class="sxs-lookup"><span data-stu-id="50e94-120">You will also need access to the certificate that you intend to use to secure SEMM.</span></span> <span data-ttu-id="50e94-121">如需此憑證需求的詳細資訊，請參閱 [Surface Enterprise 管理模式憑證需求](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。</span><span class="sxs-lookup"><span data-stu-id="50e94-121">For details about the requirements for this certificate, see [Surface Enterprise Management Mode certificate requirements](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements).</span></span>
> 
> <span data-ttu-id="50e94-122">必須將此憑證存放在安全的位置並正確備份，這一點非常重要。</span><span class="sxs-lookup"><span data-stu-id="50e94-122">It is very important that this certificate be kept in a safe location and properly backed up.</span></span> <span data-ttu-id="50e94-123">如果此憑證遺失或無法使用，就無法重設 Surface UEFI、變更 managed Surface UEFI 設定，或從已註冊的 Surface 裝置移除 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-123">If this certificate becomes lost or unusable, it is not possible to reset Surface UEFI, change managed Surface UEFI settings, or remove SEMM from an enrolled Surface device.</span></span>

#### <span data-ttu-id="50e94-124">下載 Microsoft Surface UEFI 管理員</span><span class="sxs-lookup"><span data-stu-id="50e94-124">Download Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="50e94-125">使用 Configuration Manager 的 SEMM 管理需要在每個用戶端 Surface 裝置上安裝 Microsoft Surface UEFI 管理器。</span><span class="sxs-lookup"><span data-stu-id="50e94-125">Management of SEMM with Configuration Manager requires the installation of Microsoft Surface UEFI Manager on each client Surface device.</span></span> <span data-ttu-id="50e94-126">您可以從 Microsoft 下載中心的 [ [表面工具](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面上，下載 MICROSOFT Surface UEFI 管理員 ( # A0) 。</span><span class="sxs-lookup"><span data-stu-id="50e94-126">You can download Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center.</span></span>

#### <span data-ttu-id="50e94-127">下載 Configuration Manager 的 SEMM 腳本</span><span class="sxs-lookup"><span data-stu-id="50e94-127">Download SEMM scripts for Configuration Manager</span></span>

<span data-ttu-id="50e94-128">在用戶端 Surface 裝置上安裝 Microsoft Surface UEFI 管理員之後，就會使用 PowerShell 腳本來部署和管理 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-128">After Microsoft Surface UEFI Manager is installed on the client Surface device, SEMM is deployed and managed with PowerShell scripts.</span></span> <span data-ttu-id="50e94-129">您可以從下載中心下載 [SEMM 管理腳本](https://www.microsoft.com/download/details.aspx?id=46703) 的範例。</span><span class="sxs-lookup"><span data-stu-id="50e94-129">You can download samples of the [SEMM management scripts](https://www.microsoft.com/download/details.aspx?id=46703) from the Download Center.</span></span>

## <span data-ttu-id="50e94-130">部署 Microsoft Surface UEFI 管理員</span><span class="sxs-lookup"><span data-stu-id="50e94-130">Deploy Microsoft Surface UEFI Manager</span></span>

<span data-ttu-id="50e94-131">部署 Microsoft Surface UEFI 管理員是一個典型的應用程式部署。</span><span class="sxs-lookup"><span data-stu-id="50e94-131">Deployment of Microsoft Surface UEFI Manager is a typical application deployment.</span></span> <span data-ttu-id="50e94-132">Microsoft Surface UEFI 管理員安裝程式檔案是標準的 Windows 安裝程式檔案，您可以使用 [標準安靜選項](https://msdn.microsoft.com/library/windows/desktop/aa367988)進行安裝。</span><span class="sxs-lookup"><span data-stu-id="50e94-132">The Microsoft Surface UEFI Manager installer file is a standard Windows Installer file that you can install with the [standard quiet option](https://msdn.microsoft.com/library/windows/desktop/aa367988).</span></span>

<span data-ttu-id="50e94-133">安裝 Microsoft Surface UEFI Manager 的命令如下所示。</span><span class="sxs-lookup"><span data-stu-id="50e94-133">The command to install Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

<span data-ttu-id="50e94-134">卸載 Microsoft Surface UEFI Manager 的命令如下所示。</span><span class="sxs-lookup"><span data-stu-id="50e94-134">The command to uninstall Microsoft Surface UEFI Manager is as follows.</span></span>

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

<span data-ttu-id="50e94-135">若要建立新的應用程式，並將它部署到包含 Surface 裝置的集合，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="50e94-135">To create a new application and deploy it to a collection that contains your Surface devices, perform the following steps:</span></span>

1. <span data-ttu-id="50e94-136">從 [ **開始** ] 畫面或 [ **開始** ] 功能表開啟 Configuration Manager 主控台。</span><span class="sxs-lookup"><span data-stu-id="50e94-136">Open Configuration Manager Console from the **Start** screen or **Start** menu.</span></span>
2. <span data-ttu-id="50e94-137">選取視窗左下角的 [ **軟體庫** ]。</span><span class="sxs-lookup"><span data-stu-id="50e94-137">Select **Software Library** in the bottom left corner of the window.</span></span>
3. <span data-ttu-id="50e94-138">展開軟體庫的 [ **應用程式管理** ] 節點，然後選取 [ **應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-138">Expand the **Application Management** node of the Software Library, and then select **Applications**.</span></span>
4. <span data-ttu-id="50e94-139">在視窗頂端的 [**常用] 索引**標籤底下，選取 [**建立應用程式**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="50e94-139">Select the **Create Application** button under the **Home** tab at the top of the window.</span></span> <span data-ttu-id="50e94-140">這會啟動 [建立應用程式] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="50e94-140">This starts the Create Application Wizard.</span></span>
5. <span data-ttu-id="50e94-141">[建立應用程式] 嚮導會顯示一系列步驟：</span><span class="sxs-lookup"><span data-stu-id="50e94-141">The Create Application Wizard presents a series of steps:</span></span>

   * <span data-ttu-id="50e94-142">**[一般** ]：預設會選取 [ **自動偵測此應用程式的安裝檔案相關資訊** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="50e94-142">**General** – The **Automatically detect information about this application from installation files** option is selected by default.</span></span> <span data-ttu-id="50e94-143">在 [ **Type** ] （類型）欄位中，預設也會選取 [ \*\*Windows 安裝程式] ( .msi 檔案) \*\* 。</span><span class="sxs-lookup"><span data-stu-id="50e94-143">In the **Type** field, **Windows Installer (.msi file)** is also selected by default.</span></span> <span data-ttu-id="50e94-144">選取 **[流覽]** 以流覽至 [ **SurfaceUEFIManagerSetup.msi**]，然後選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-144">Select **Browse** to navigate to and select **SurfaceUEFIManagerSetup.msi**, and then select **Next**.</span></span>
   
      > [!Note]
      > <span data-ttu-id="50e94-145">SurfaceUEFIManagerSetup.msi 的位置必須位於網路共用位置，且位於不含其他檔案的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="50e94-145">The location of SurfaceUEFIManagerSetup.msi must be on a network share and located in a folder that contains no other files.</span></span> <span data-ttu-id="50e94-146">無法使用本機檔案位置。</span><span class="sxs-lookup"><span data-stu-id="50e94-146">A local file location cannot be used.</span></span>

   * <span data-ttu-id="50e94-147">匯**入資訊**-[建立應用程式] 嚮導會分析 .msi 檔案並讀取**應用程式名稱**和**產品代碼**。</span><span class="sxs-lookup"><span data-stu-id="50e94-147">**Import Information** – The Create Application Wizard will parse the .msi file and read the **Application Name** and **Product Code**.</span></span> <span data-ttu-id="50e94-148">SurfaceUEFIManagerSetup.msi 應該線上條 **內容**檔案下以唯一的檔案的形式列出，如圖1所示。</span><span class="sxs-lookup"><span data-stu-id="50e94-148">SurfaceUEFIManagerSetup.msi should be listed as the only file under the line **Content Files**, as shown in Figure 1.</span></span> <span data-ttu-id="50e94-149">選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="50e94-149">Select **Next** to proceed.</span></span>

      ![來自 Surface UEFI 管理員設定的資訊會自動進行分析](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *<span data-ttu-id="50e94-151">圖 1。</span><span class="sxs-lookup"><span data-stu-id="50e94-151">Figure 1.</span></span> <span data-ttu-id="50e94-152">來自 Microsoft Surface UEFI 管理員設定的資訊會自動進行分析</span><span class="sxs-lookup"><span data-stu-id="50e94-152">Information from Microsoft Surface UEFI Manager setup is automatically parsed</span></span>*

   * <span data-ttu-id="50e94-153">**一般資訊** –您可以修改應用程式的名稱，以及有關發行者與版本的資訊，或在此頁面上新增批註。</span><span class="sxs-lookup"><span data-stu-id="50e94-153">**General Information** – You can modify the name of the application and information about the publisher and version, or add comments on this page.</span></span> <span data-ttu-id="50e94-154">Microsoft Surface UEFI Manager 的 [安裝] 命令會顯示在 [安裝程式] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="50e94-154">The installation command for Microsoft Surface UEFI Manager is displayed in the Installation Program field.</span></span> <span data-ttu-id="50e94-155">安裝系統的預設安裝行為將允許 Microsoft Surface UEFI 管理員安裝 SEMM 的必要元件，即使使用者沒有登入 Surface 裝置也一樣。</span><span class="sxs-lookup"><span data-stu-id="50e94-155">The default installation behavior of Install for system will allow Microsoft Surface UEFI Manager to install the required assemblies for SEMM even if a user is not logged on to the Surface device.</span></span> <span data-ttu-id="50e94-156">選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="50e94-156">Select **Next** to proceed.</span></span>
   * <span data-ttu-id="50e94-157">**摘要** ：在 [匯 **入資訊** ] 步驟中分析的資訊，以及您在 [ **一般資訊** ] 步驟中選取的資訊會顯示在此頁面上。</span><span class="sxs-lookup"><span data-stu-id="50e94-157">**Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page.</span></span> <span data-ttu-id="50e94-158">選取 **[下一步]** ，確認您的選擇並建立應用程式。</span><span class="sxs-lookup"><span data-stu-id="50e94-158">Select **Next** to confirm your selections and create the application.</span></span>
   * <span data-ttu-id="50e94-159">**進度** –當應用程式匯入並新增至軟體文件庫時，會顯示進度列和狀態。</span><span class="sxs-lookup"><span data-stu-id="50e94-159">**Progress** – Displays a progress bar and status as the application is imported and added to the Software Library.</span></span>
   * <span data-ttu-id="50e94-160">**完成** –當應用程式建立處理常式完成時，就會顯示成功建立應用程式的確認。</span><span class="sxs-lookup"><span data-stu-id="50e94-160">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="50e94-161">選取 [ **關閉** ] 以完成 [建立應用程式] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="50e94-161">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="50e94-162">在 Configuration Manager 中建立應用程式後，您可以將它發佈到您的發佈點，並將它部署到集合（包括 Surface 裝置）。</span><span class="sxs-lookup"><span data-stu-id="50e94-162">After the application is created in Configuration Manager, you can distribute it to your distribution points and deploy it to the collections including your Surface devices.</span></span> <span data-ttu-id="50e94-163">這個應用程式不會在 Surface 裝置上安裝或啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-163">This application will not install or enable SEMM on the Surface device.</span></span> <span data-ttu-id="50e94-164">它只會提供使用 PowerShell 腳本啟用 SEMM 所需的元件。</span><span class="sxs-lookup"><span data-stu-id="50e94-164">It only provides the assemblies required for SEMM to be enabled using the PowerShell script.</span></span>

<span data-ttu-id="50e94-165">如果您不想要在不是使用 SEMM 管理的裝置上安裝 Microsoft Surface UEFI 管理器元件，您可以將 Microsoft Surface UEFI 管理員設定為 SEMM Configuration Manager 腳本的相依性。</span><span class="sxs-lookup"><span data-stu-id="50e94-165">If you do not want to install the Microsoft Surface UEFI Manager assemblies on devices that will not be managed with SEMM, you can configure Microsoft Surface UEFI Manager as a dependency of the SEMM Configuration Manager scripts.</span></span> <span data-ttu-id="50e94-166">此案例將在本文稍後的 [ [部署 SEMM Configuration Manager 腳本](#deploy-semm-configuration-manager-scripts) ] 區段中講述。</span><span class="sxs-lookup"><span data-stu-id="50e94-166">This scenario is covered in the [Deploy SEMM Configuration Manager Scripts](#deploy-semm-configuration-manager-scripts) section later in this article.</span></span>

## <span data-ttu-id="50e94-167">建立或修改 SEMM Configuration Manager 腳本</span><span class="sxs-lookup"><span data-stu-id="50e94-167">Create or modify the SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="50e94-168">在裝置上安裝所需的元件之後，在 SEMM 中註冊裝置並設定 Surface UEFI 的程式是使用 PowerShell 腳本完成，並以 Configuration Manager 的形式部署為腳本應用程式。</span><span class="sxs-lookup"><span data-stu-id="50e94-168">After the required assemblies have been installed on the devices, the process of enrolling the devices in SEMM and configuring Surface UEFI is done with PowerShell scripts and deployed as a script application with Configuration Manager.</span></span> <span data-ttu-id="50e94-169">您可以修改這些腳本，以符合貴組織與環境的需求。</span><span class="sxs-lookup"><span data-stu-id="50e94-169">These scripts can be modified to fit the needs of your organization and environment.</span></span> <span data-ttu-id="50e94-170">例如，您可以針對不同部門或角色中的受管理 Surface 裝置建立多個設定。</span><span class="sxs-lookup"><span data-stu-id="50e94-170">For example, you can create multiple configurations for managed Surface devices in different departments or roles.</span></span> <span data-ttu-id="50e94-171">您可以從本文開頭的 [ [先決條件](#prerequisites) ] 區段中的連結，下載 SEMM 與 Configuration Manager 腳本的範例。</span><span class="sxs-lookup"><span data-stu-id="50e94-171">You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.</span></span>

<span data-ttu-id="50e94-172">您必須有兩個主要的腳本，才能使用 Configuration Manager 執行 SEMM 部署：</span><span class="sxs-lookup"><span data-stu-id="50e94-172">There are two primary scripts you will need in order to perform a SEMM deployment with Configuration Manager:</span></span>

* <span data-ttu-id="50e94-173">**ConfigureSEMM.ps1** –使用此腳本來為 surface 裝置建立配置套件，以使用您想要的 surface UEFI 設定，將指定的設定套用至 Surface 裝置、在 SEMM 中註冊裝置，以及設定用來識別 SEMM 中裝置註冊的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="50e94-173">**ConfigureSEMM.ps1** – Use this script to create configuration packages for your Surface devices with your desired Surface UEFI settings to apply the specified settings to a Surface device, to enroll the device in SEMM, and to set a registry key used to identify the enrollment of the device in SEMM.</span></span>
* <span data-ttu-id="50e94-174">**ResetSEMM.ps1** –使用此腳本在 surface 裝置上重設 SEMM，這會從 SEMM 中 unenrolls 它，並移除對 surface UEFI 設定的控制。</span><span class="sxs-lookup"><span data-stu-id="50e94-174">**ResetSEMM.ps1** – Use this script to reset SEMM on a Surface device, which unenrolls it from SEMM and removes the control over Surface UEFI settings.</span></span>

<span data-ttu-id="50e94-175">範例腳本包含如何設定 Surface UEFI 設定，以及如何控制這些設定許可權的範例。</span><span class="sxs-lookup"><span data-stu-id="50e94-175">The sample scripts include examples of how to set Surface UEFI settings and how to control permissions to those settings.</span></span> <span data-ttu-id="50e94-176">您可以將這些設定修改為安全 Surface UEFI，並根據您的環境需求設定 Surface UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="50e94-176">These settings can be modified to secure Surface UEFI and set Surface UEFI settings according to the needs of your environment.</span></span> <span data-ttu-id="50e94-177">本文的下列各節將說明 ConfigureSEMM.ps1 腳本，並探索您需要對腳本所做的修改，以符合您的需求。</span><span class="sxs-lookup"><span data-stu-id="50e94-177">The following sections of this article explain the ConfigureSEMM.ps1 script and explore the modifications you need to make to the script to fit your requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="50e94-178">SEMM Configuration Manager 腳本和匯出的 SEMM 憑證檔案 ( .pfx) 應該放在與其他檔案不在同一個資料夾中，才能新增至 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="50e94-178">The SEMM Configuration Manager scripts and the exported SEMM certificate file (.pfx) should be placed in the same folder with no other files before they are added to Configuration Manager.</span></span>

### <span data-ttu-id="50e94-179">指定憑證及套件名稱</span><span class="sxs-lookup"><span data-stu-id="50e94-179">Specify certificate and package names</span></span>

<span data-ttu-id="50e94-180">您需要修改的腳本第一個區域是指定及載入 SEMM 憑證的部分，也會指出 SurfaceUEFIManager 版本，以及 SEMM configuration 套件的名稱，以及 SEMM 重設套件。</span><span class="sxs-lookup"><span data-stu-id="50e94-180">The first region of the script that you need to modify is the portion that specifies and loads the SEMM certificate, and also indicates SurfaceUEFIManager version, and the names for the SEMM configuration package and SEMM reset package.</span></span> <span data-ttu-id="50e94-181">認證名稱和 SurfaceUEFIManager 版本是在 ConfigureSEMM.ps1 腳本中的第56至73行上指定。</span><span class="sxs-lookup"><span data-stu-id="50e94-181">The certificate name and SurfaceUEFIManager version are specified on lines 56 through 73 in the ConfigureSEMM.ps1 script.</span></span>

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

<span data-ttu-id="50e94-182">將 **$certName**變數的**FabrikamSEMMSample**值，以 SEMM 憑證檔案的名稱取代到行58。</span><span class="sxs-lookup"><span data-stu-id="50e94-182">Replace the **FabrikamSEMMSample.pfx** value for the **$certName** variable with the name of your SEMM Certificate file on line 58.</span></span> <span data-ttu-id="50e94-183">此腳本會在您的腳本所在的資料夾中，建立一個 (命名的 Config) 的工作目錄，然後將證書檔案複製到此工作目錄。</span><span class="sxs-lookup"><span data-stu-id="50e94-183">The script will create a working directory (named Config) in the folder where your scripts are located, and then copies the certificate file to this working directory.</span></span>

<span data-ttu-id="50e94-184">您也會在 Config 目錄中建立擁有者封裝及重設套件，並保留由腳本產生的 Surface UEFI 設定和許可權的配置。</span><span class="sxs-lookup"><span data-stu-id="50e94-184">Owner package and reset package will also be created in the Config directory and hold the configuration for Surface UEFI settings and permissions generated by the script.</span></span>

<span data-ttu-id="50e94-185">在 line 73 上，將 **$password** 變數的值（從 **1234** ）取代為憑證檔案的密碼。</span><span class="sxs-lookup"><span data-stu-id="50e94-185">On line 73, replace the value of the **$password** variable, from **1234** to the password for your certificate file.</span></span> <span data-ttu-id="50e94-186">如果不需要密碼，請刪除 **1234** 文字。</span><span class="sxs-lookup"><span data-stu-id="50e94-186">If a password is not required, delete the **1234** text.</span></span>

> [!Note]
> <span data-ttu-id="50e94-187">您必須在 SEMM 中註冊裝置，才能使用憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="50e94-187">The last two characters of the certificate thumbprint are required to enroll a device in SEMM.</span></span> <span data-ttu-id="50e94-188">此腳本會將這些數字顯示給使用者，讓使用者或技術人員在系統重新開機前記錄這些數位，以在 SEMM 中註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="50e94-188">This script will display these digits to the user, which allows the user or technician to record these digits before the system reboots to enroll the device in SEMM.</span></span> <span data-ttu-id="50e94-189">此腳本會使用下列程式碼（在150-155 行中找到）來完成這項作業。</span><span class="sxs-lookup"><span data-stu-id="50e94-189">The script uses the following code, found on lines 150-155, to accomplish this.</span></span>

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

您可以在 CertMgr 中開啟 .pfx 檔案，讓擁有證書檔案存取權的管理員 ( .pfx) 可隨時讀取指紋。 <span data-ttu-id="50e94-191">若要使用 CertMgr 查看指紋，請遵循此程式：</span><span class="sxs-lookup"><span data-stu-id="50e94-191">To view the thumbprint with CertMgr, follow this process:</span></span>

1. <span data-ttu-id="50e94-192">以滑鼠右鍵按一下 .pfx 檔案，然後選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-192">Right-click the .pfx file, and then select **Open**.</span></span>
2. <span data-ttu-id="50e94-193">展開 [功能窗格] 中的資料夾。</span><span class="sxs-lookup"><span data-stu-id="50e94-193">Expand the folder in the navigation pane.</span></span>
3. <span data-ttu-id="50e94-194">選取 [ **憑證**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-194">Select **Certificates**.</span></span>
4. <span data-ttu-id="50e94-195">在主要窗格中，以滑鼠右鍵按一下您的憑證，然後選取 [ **開啟**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-195">Right-click your certificate in the main pane, and then select **Open**.</span></span>
5. <span data-ttu-id="50e94-196">選取 [ **詳細資料** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="50e94-196">Select the **Details** tab.</span></span>
6. <span data-ttu-id="50e94-197">[**全部**] 或 [**僅限屬性**] 必須在 [**顯示**] 下拉式功能表中選取。</span><span class="sxs-lookup"><span data-stu-id="50e94-197">**All** or **Properties Only** must be selected in the **Show** drop-down menu.</span></span>
7. <span data-ttu-id="50e94-198">選取欄位 **指紋**。</span><span class="sxs-lookup"><span data-stu-id="50e94-198">Select the field **Thumbprint**.</span></span>

> [!NOTE]
> <span data-ttu-id="50e94-199">您也必須在 ResetSEMM.ps1 腳本的此區段中輸入 SEMM 憑證名稱和密碼，才能讓 Configuration Manager 從裝置中移除 SEMM 與卸載動作。</span><span class="sxs-lookup"><span data-stu-id="50e94-199">The SEMM certificate name and password must also be entered in this section of the ResetSEMM.ps1 script to enable Configuration Manager to remove SEMM from the device with the uninstall action.</span></span>

### <span data-ttu-id="50e94-200">設定許可權</span><span class="sxs-lookup"><span data-stu-id="50e94-200">Configure permissions</span></span>

<span data-ttu-id="50e94-201">您將在其中指定 Surface UEFI 配置的腳本第一個區域是 [ **設定許可權** ] 區域。</span><span class="sxs-lookup"><span data-stu-id="50e94-201">The first region of the script where you will specify the configuration for Surface UEFI is the **Configure Permissions** region.</span></span> <span data-ttu-id="50e94-202">這個區域會從範例腳本中的第210列開始，並以批註 **# 設定許可權** ，並繼續到第247列。</span><span class="sxs-lookup"><span data-stu-id="50e94-202">This region begins at line 210 in the sample script with the comment **# Configure Permissions** and continues to line 247.</span></span> <span data-ttu-id="50e94-203">下列程式碼片段首先將許可權設定為所有 Surface UEFI 設定，以便僅供 SEMM 修改，然後新增明確許可權，以允許本機使用者修改 Surface UEFI 密碼、TPM 以及前臺和後置相機。</span><span class="sxs-lookup"><span data-stu-id="50e94-203">The following code fragment first sets permissions to all Surface UEFI settings so that they may be modified by SEMM only, then adds explicit permissions to allow the local user to modify the Surface UEFI password, TPM, and front and rear cameras.</span></span>

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

<span data-ttu-id="50e94-204">每個 **$uefiV 2** 變數都透過設定名稱或識別碼來識別 Surface UEFI 設定，然後將許可權設定為下列其中一個值：</span><span class="sxs-lookup"><span data-stu-id="50e94-204">Each **$uefiV2** variable identifies a Surface UEFI setting by setting name or ID, and then configures the permissions to one of the following values:</span></span>

* <span data-ttu-id="50e94-205">**$ownerOnly** –修改此設定的許可權僅獲授與 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-205">**$ownerOnly** – Permission to modify this setting is granted only to SEMM.</span></span>
* <span data-ttu-id="50e94-206">**$ownerAndLocalUser** –修改此設定的許可權會被授與本機使用者引導至 Surface UEFI，以及 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-206">**$ownerAndLocalUser** – Permission to modify this setting is granted to a local user booting to Surface UEFI, as well as to SEMM.</span></span>

<span data-ttu-id="50e94-207">您可以在本文的 [ [設定名稱和識別碼](#settings-names-and-ids) ] 區段中，找到有關 Surface UEFI 可用之設定名稱和識別碼的資訊。</span><span class="sxs-lookup"><span data-stu-id="50e94-207">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.</span></span>

### <span data-ttu-id="50e94-208">進行設定</span><span class="sxs-lookup"><span data-stu-id="50e94-208">Configure settings</span></span>

<span data-ttu-id="50e94-209">您將在其中指定 Surface UEFI 配置的腳本第二個區域是 ConfigureSEMM.ps1 腳本的 [設定 **設定** ] 區域，它會設定是否已啟用或停用每個設定。</span><span class="sxs-lookup"><span data-stu-id="50e94-209">The second region of the script where you will specify the configuration for Surface UEFI is the **Configure Settings** region of the ConfigureSEMM.ps1 script, which configures whether each setting is enabled or disabled.</span></span> <span data-ttu-id="50e94-210">範例腳本包含將所有設定設為預設值的指示。</span><span class="sxs-lookup"><span data-stu-id="50e94-210">The sample script includes instructions to set all settings to their default values.</span></span> <span data-ttu-id="50e94-211">然後，腳本會提供針對 PXE 啟動停用 IPv6 的明確指示，並讓 Surface UEFI 管理員密碼保持不變。</span><span class="sxs-lookup"><span data-stu-id="50e94-211">The script then provides explicit instructions to disable IPv6 for PXE Boot and to leave the Surface UEFI Administrator password unchanged.</span></span> <span data-ttu-id="50e94-212">您可以在範例腳本中，從第291至 line 335 的 **# 設定設定** 批註開始，找到這個區域。</span><span class="sxs-lookup"><span data-stu-id="50e94-212">You can find this region beginning with the **# Configure Settings** comment at line 291 through line 335 in the sample script.</span></span> <span data-ttu-id="50e94-213">區域如下所示。</span><span class="sxs-lookup"><span data-stu-id="50e94-213">The region appears as follows.</span></span>

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

<span data-ttu-id="50e94-214">就像在腳本的 [ **設定許可權** ] 區段中設定的許可權，每個 Surface UEFI 設定的設定都是透過定義 **$uefiV 2** 變數來執行。</span><span class="sxs-lookup"><span data-stu-id="50e94-214">Like the permissions set in the **Configure Permissions** section of the script, the configuration of each Surface UEFI setting is performed by defining the **$uefiV2** variable.</span></span> <span data-ttu-id="50e94-215">針對定義 **$uefiV 2** 變數的每個線條，Surface UEFI 設定是透過設定名稱或識別碼來加以識別，且已設定的值會設定為 [ **啟用** ] 或 [ **已停用**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-215">For each line defining the **$uefiV2** variable, a Surface UEFI setting is identified by setting name or ID and the configured value is set to **Enabled** or **Disabled**.</span></span>

<span data-ttu-id="50e94-216">如果您不想要變更 Surface UEFI 設定的設定，例如，以確保將所有 Surface UEFI 設定重設為預設值的動作無法清除 Surface UEFI 系統管理員密碼，您可以使用 \*\*ClearConfiguredValue ( # B1 \*\* 來強制變更此設定。</span><span class="sxs-lookup"><span data-stu-id="50e94-216">If you do not want to alter the configuration of a Surface UEFI setting, for example to ensure that the Surface UEFI administrator password is not cleared by the action of resetting all Surface UEFI settings to their default, you can use **ClearConfiguredValue()** to enforce that this setting will not be altered.</span></span> <span data-ttu-id="50e94-217">在範例腳本中，在 line 323 上使用此選項，以避免清除 Surface UEFI 系統管理員密碼，在範例腳本中以其設定識別碼（ **501**）加以識別。</span><span class="sxs-lookup"><span data-stu-id="50e94-217">In the sample script, this is used on line 323 to prevent the clearing of the Surface UEFI Administrator password, identified in the sample script by its setting ID, **501**.</span></span>

<span data-ttu-id="50e94-218">您可以在本文稍後的 [ [設定名稱和識別碼](#settings-names-and-ids) ] 區段中，找到有關 Surface UEFI 可用設定名稱和識別碼的資訊。</span><span class="sxs-lookup"><span data-stu-id="50e94-218">You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.</span></span>

### <span data-ttu-id="50e94-219">[設定] 登錄機碼</span><span class="sxs-lookup"><span data-stu-id="50e94-219">Settings registry key</span></span>

<span data-ttu-id="50e94-220">若要識別 Configuration Manager 的已註冊系統，ConfigureSEMM.ps1 腳本會寫入登錄機碼，以用於識別已註冊的系統（即已使用 SEMM 設定腳本安裝）。</span><span class="sxs-lookup"><span data-stu-id="50e94-220">To identify enrolled systems for Configuration Manager, the ConfigureSEMM.ps1 script writes registry keys that can be used to identify enrolled systems as having been installed with the SEMM configuration script.</span></span> <span data-ttu-id="50e94-221">您可以在下列位置找到這些金鑰。</span><span class="sxs-lookup"><span data-stu-id="50e94-221">These keys can be found at the following location.</span></span>

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

<span data-ttu-id="50e94-222">下列程式碼片段（在380-477 行中找到）是用來撰寫這些登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="50e94-222">The following code fragment, found on lines 380-477, is used to write these registry keys.</span></span>

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <span data-ttu-id="50e94-223">設定名稱和識別碼</span><span class="sxs-lookup"><span data-stu-id="50e94-223">Settings names and IDs</span></span>

<span data-ttu-id="50e94-224">若要設定 Surface uefi 設定或 Surface UEFI 設定的許可權，您必須透過其設定名稱或設定識別碼來參照每一個設定。</span><span class="sxs-lookup"><span data-stu-id="50e94-224">To configure Surface UEFI settings or permissions for Surface UEFI settings, you must refer to each setting by either its setting name or setting ID.</span></span> <span data-ttu-id="50e94-225">針對 Surface UEFI 的每個新更新，可能會新增新設定。</span><span class="sxs-lookup"><span data-stu-id="50e94-225">With each new update for Surface UEFI, new settings may be added.</span></span> <span data-ttu-id="50e94-226">若要取得 Surface 裝置上可用設定的完整清單，以及設定名稱和設定識別碼，就是在[IT 下載的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中使用 ShowSettingsOptions.ps1 腳本 SEMM_Powershell.zip</span><span class="sxs-lookup"><span data-stu-id="50e94-226">The best way to get a complete list of the settings available on a Surface device, along with the settings name and settings IDs, is to use the ShowSettingsOptions.ps1 script from SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703)</span></span> 

<span data-ttu-id="50e94-227">執行 ShowSettingsOptions.ps1 的電腦必須安裝 Microsoft Surface UEFI 管理員，但腳本不需要 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="50e94-227">The computer where ShowSettingsOptions.ps1 is run must have Microsoft Surface UEFI Manager installed, but the script does not require a Surface device.</span></span>

<span data-ttu-id="50e94-228">若要查看裝置最新的設定名稱和識別碼，最好的方法是使用 ConfigureSEMM.ps1 腳本，或 <device name> 從 [IT 下載的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中的 SEMM_Powershell.zip 中 ConfigureSEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-228">The best way to view the most current Setting names and IDs for devices is to use the ConfigureSEMM.ps1 script or the ConfigureSEMM - <device name>.ps1 from the SEMM_Powershell.zip in [Surface Tools for IT Downloads](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>

<span data-ttu-id="50e94-229">您可以在 ConfigureSEMM.ps1 腳本中查看所有裝置的名稱和識別碼。</span><span class="sxs-lookup"><span data-stu-id="50e94-229">Setting names and IDs for all devices can be seen in the ConfigureSEMM.ps1 script.</span></span>

<span data-ttu-id="50e94-230">您可以在 ConfigureSEMM-ps1 腳本中看到設定特定裝置的名稱和識別碼 <device name> 。</span><span class="sxs-lookup"><span data-stu-id="50e94-230">Setting names and IDs for specific devices can be seen in the ConfigureSEMM - <device name>.ps1 scripts.</span></span> 

## <span data-ttu-id="50e94-231">部署 SEMM Configuration Manager 腳本</span><span class="sxs-lookup"><span data-stu-id="50e94-231">Deploy SEMM Configuration Manager scripts</span></span>

<span data-ttu-id="50e94-232">準備好要在用戶端裝置上設定及啟用 SEMM 的腳本之後，下一步就是在 Configuration Manager 中將這些腳本新增為應用程式。</span><span class="sxs-lookup"><span data-stu-id="50e94-232">After your scripts are prepared to configure and enable SEMM on the client device, the next step is to add these scripts as an application in Configuration Manager.</span></span> <span data-ttu-id="50e94-233">在您開啟 Configuration Manager 前，請確定下列檔案位於不含其他檔案的共用資料夾中：</span><span class="sxs-lookup"><span data-stu-id="50e94-233">Before you open Configuration Manager, ensure that the following files are in a shared folder that does not include other files:</span></span>

* <span data-ttu-id="50e94-234">ConfigureSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="50e94-234">ConfigureSEMM.ps1</span></span>
* <span data-ttu-id="50e94-235">ResetSEMM.ps1</span><span class="sxs-lookup"><span data-stu-id="50e94-235">ResetSEMM.ps1</span></span>
* <span data-ttu-id="50e94-236">您的 SEMM 憑證 (例如 SEMMCertificate .pfx) </span><span class="sxs-lookup"><span data-stu-id="50e94-236">Your SEMM certificate (for example SEMMCertificate.pfx)</span></span>

<span data-ttu-id="50e94-237">SEMM Configuration Manager 腳本將會新增至 Configuration Manager，做為腳本應用程式。</span><span class="sxs-lookup"><span data-stu-id="50e94-237">The SEMM Configuration Manager scripts will be added to Configuration Manager as a script application.</span></span> <span data-ttu-id="50e94-238">使用 ConfigureSEMM.ps1 安裝 SEMM 的命令如下所示。</span><span class="sxs-lookup"><span data-stu-id="50e94-238">The command to install SEMM with ConfigureSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

<span data-ttu-id="50e94-239">使用 ResetSEMM.ps1 卸載 SEMM 的命令如下所示。</span><span class="sxs-lookup"><span data-stu-id="50e94-239">The command to uninstall SEMM with ResetSEMM.ps1 is as follows.</span></span>

`Powershell.exe -file ".\ResetSEMM.ps1"`

<span data-ttu-id="50e94-240">若要將 SEMM Configuration Manager 腳本新增至 Configuration Manager 做為應用程式，請使用下列程式：</span><span class="sxs-lookup"><span data-stu-id="50e94-240">To add the SEMM Configuration Manager scripts to Configuration Manager as an application, use the following process:</span></span>

1. <span data-ttu-id="50e94-241">從本文先前的 [部署 Microsoft SURFACE UEFI 管理員](#deploy-microsoft-surface-uefi-manager) 區段中，使用步驟1到步驟5啟動 [建立應用程式] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="50e94-241">Start the Create Application Wizard using Step 1 through Step 5 from the [Deploy Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) section earlier in this article.</span></span>

2. <span data-ttu-id="50e94-242">依下列步驟繼續執行 [建立應用程式] 嚮導：</span><span class="sxs-lookup"><span data-stu-id="50e94-242">Proceed through The Create Application Wizard as follows:</span></span>

   - <span data-ttu-id="50e94-243">**一般** –選取 [ **手動指定應用程式資訊**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="50e94-243">**General** – Select **Manually specify the application information**, and then select **Next**.</span></span>

   - <span data-ttu-id="50e94-244">**一般資訊** –輸入應用程式 (的名稱，例如 SEMM) 及您想要的任何其他資訊（例如，此頁面上的 publisher、版本或批註）。</span><span class="sxs-lookup"><span data-stu-id="50e94-244">**General Information** – Enter a name for the application (for example SEMM) and any other information you want such as publisher, version, or comments on this page.</span></span> <span data-ttu-id="50e94-245">選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="50e94-245">Select **Next** to proceed.</span></span>

   - <span data-ttu-id="50e94-246">[**應用程式目錄**] –此頁面上的欄位可以保留其預設值。</span><span class="sxs-lookup"><span data-stu-id="50e94-246">**Application Catalog** – The fields on this page can be left with their default values.</span></span> <span data-ttu-id="50e94-247">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="50e94-247">Select **Next**.</span></span>

   - <span data-ttu-id="50e94-248">**部署類型** –選取 [ **新增** ] 以啟動 [建立部署類型] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="50e94-248">**Deployment Types** – Select **Add** to start the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="50e94-249">依照 [建立部署類型] 嚮導中的步驟進行，如下所示：</span><span class="sxs-lookup"><span data-stu-id="50e94-249">Proceed through the steps of the Create Deployment Type Wizard, as follows:</span></span>

     * <span data-ttu-id="50e94-250">**一般**-從 [**類型**] 下拉式功能表選取 [**腳本安裝程式**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-250">**General** – Select **Script Installer** from the **Type** drop-down menu.</span></span> <span data-ttu-id="50e94-251">[ **手動指定部署類型資訊** ] 選項會自動選取。</span><span class="sxs-lookup"><span data-stu-id="50e94-251">The **Manually specify the deployment type information** option will automatically be selected.</span></span> <span data-ttu-id="50e94-252">選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="50e94-252">Select **Next** to proceed.</span></span>
     * <span data-ttu-id="50e94-253">**一般資訊** -在 (輸入部署類型的名稱，例如 SEMM [設定腳本]) ，然後選取 **[下一步]** 以繼續。</span><span class="sxs-lookup"><span data-stu-id="50e94-253">**General Information** – Enter a name for the deployment type (for example SEMM Configuration Scripts), and then select **Next** to continue.</span></span>
     * <span data-ttu-id="50e94-254">**內容**–選取 [**內容位置**] 欄位旁的 **[流覽]** ，然後選取您的 SEMM Configuration Manager 腳本所在的資料夾。</span><span class="sxs-lookup"><span data-stu-id="50e94-254">**Content** – Select **Browse** next to the **Content Location** field, and then select the folder where your SEMM Configuration Manager scripts are located.</span></span> <span data-ttu-id="50e94-255">在 [ **安裝程式** ] 欄位中，輸入本文前文所述的 [安裝命令](#deploy-semm-configuration-manager-scripts) 。</span><span class="sxs-lookup"><span data-stu-id="50e94-255">In the **Installation Program** field, type the [installation command](#deploy-semm-configuration-manager-scripts) found earlier in this article.</span></span> <span data-ttu-id="50e94-256">在 [ **卸載程式** ] 欄位中，輸入您在本文先前所見到的 [卸載命令](#deploy-semm-configuration-manager-scripts) (圖 2) 所示。</span><span class="sxs-lookup"><span data-stu-id="50e94-256">In the **Uninstall Program** field, enter the [uninstallation command](#deploy-semm-configuration-manager-scripts) found earlier in this article (shown in Figure 2).</span></span> <span data-ttu-id="50e94-257">選取 **[下一步]** ，移至下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="50e94-257">Select **Next** to move to the next page.</span></span>
    
     ![將 SEMM Configuration Manager 腳本設定為安裝與卸載命令](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *<span data-ttu-id="50e94-259">圖 2.</span><span class="sxs-lookup"><span data-stu-id="50e94-259">Figure 2.</span></span> <span data-ttu-id="50e94-260">將 SEMM Configuration Manager 腳本設定為安裝與卸載命令</span><span class="sxs-lookup"><span data-stu-id="50e94-260">Set the SEMM Configuration Manager scripts as the install and uninstall commands</span></span>*

     * <span data-ttu-id="50e94-261">**偵測方法** –選取 **add 子句** 以新增 SEMM Configuration Manager 腳本登錄金鑰偵測規則。</span><span class="sxs-lookup"><span data-stu-id="50e94-261">**Detection Method** – Select **Add Clause** to add the SEMM Configuration Manager script registry key detection rule.</span></span> <span data-ttu-id="50e94-262">隨即會顯示 [ **偵測規則** ] 視窗，如圖3所示。</span><span class="sxs-lookup"><span data-stu-id="50e94-262">The **Detection Rule** window is displayed, as shown in Figure 3.</span></span> <span data-ttu-id="50e94-263">使用下列設定：</span><span class="sxs-lookup"><span data-stu-id="50e94-263">Use the following settings:</span></span>

       - <span data-ttu-id="50e94-264">從 [**設定類型**] 下拉式功能表中選取 [**註冊表**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-264">Select **Registry** from the **Setting Type** drop-down menu.</span></span>
       - <span data-ttu-id="50e94-265">從 [**配置單元**] 下拉式功能表中選取 [ **HKEY_LOCAL_MACHINE** ]。</span><span class="sxs-lookup"><span data-stu-id="50e94-265">Select **HKEY_LOCAL_MACHINE** from the **Hive** drop-down menu.</span></span>
       - <span data-ttu-id="50e94-266">在 [索引**鍵**] 欄位中輸入**SOFTWARE\Microsoft\Surface\SEMM** 。</span><span class="sxs-lookup"><span data-stu-id="50e94-266">Enter **SOFTWARE\Microsoft\Surface\SEMM** in the **Key** field.</span></span>
       - <span data-ttu-id="50e94-267">在 [**值**] 欄位中輸入**CertName** 。</span><span class="sxs-lookup"><span data-stu-id="50e94-267">Enter **CertName** in the **Value** field.</span></span>
       - <span data-ttu-id="50e94-268">從 [**資料類型**] 下拉式功能表中選取 [**字串**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-268">Select **String** from the **Data Type** drop-down menu.</span></span>
       - <span data-ttu-id="50e94-269">選取 [ **此登錄設定必須符合下列規則，才能指出此應用程式的目前狀態** ] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="50e94-269">Select the **This registry setting must satisfy the following rule to indicate the presence of this application** button.</span></span>
       - <span data-ttu-id="50e94-270">在 [ **值** ] 欄位中，輸入您在腳本的 [行 58] 中輸入的憑證名稱。</span><span class="sxs-lookup"><span data-stu-id="50e94-270">Enter the name of the certificate you entered in line 58 of the script in the **Value** field.</span></span>
       - <span data-ttu-id="50e94-271">選取 **[確定]** 以關閉 [ **偵測規則** ] 視窗。</span><span class="sxs-lookup"><span data-stu-id="50e94-271">Select **OK** to close the **Detection Rule** window.</span></span>

     ![使用登錄機碼來識別註冊 SEMM 的裝置](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *<span data-ttu-id="50e94-273">圖 3.</span><span class="sxs-lookup"><span data-stu-id="50e94-273">Figure 3.</span></span> <span data-ttu-id="50e94-274">使用登錄機碼來識別註冊 SEMM 的裝置</span><span class="sxs-lookup"><span data-stu-id="50e94-274">Use a registry key to identify devices enrolled in SEMM</span></span>*

     * <span data-ttu-id="50e94-275">選取 **[下一步]** ，繼續進行下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="50e94-275">Select **Next** to proceed to the next page.</span></span>
     
     * <span data-ttu-id="50e94-276">**使用者體驗**-從 [**安裝行為**] 下拉式功能表選取 [**安裝系統**]。</span><span class="sxs-lookup"><span data-stu-id="50e94-276">**User Experience** – Select **Install for system** from the **Installation Behavior** drop-down menu.</span></span> <span data-ttu-id="50e94-277">如果您想讓使用者錄製並輸入證書指紋本身，請將登錄需求只設定為 **在使用者登入時才**設定。</span><span class="sxs-lookup"><span data-stu-id="50e94-277">If you want your users to record and enter the certificate thumbprint themselves, leave the logon requirement set to **Only when a user is logged on**.</span></span> <span data-ttu-id="50e94-278">如果您想要讓系統管理員為使用者輸入指紋，且使用者不需要看到指紋，請從 [**登錄需求**] 下拉式功能表選取使用者是否已**登入**。</span><span class="sxs-lookup"><span data-stu-id="50e94-278">If you want your administrators to enter the thumbprint for users and the users do not need to see the thumbprint, select **Whether or not a user is logged on** from the **Logon Requirement** drop-down menu.</span></span>

     * <span data-ttu-id="50e94-279">**需求** -ConfigureSEMM.ps1 腳本會在嘗試啟用 SEMM 前，自動確認裝置是 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="50e94-279">**Requirements** – The ConfigureSEMM.ps1 script automatically verifies that the device is a Surface device before attempting to enable SEMM.</span></span> <span data-ttu-id="50e94-280">不過，如果您想要將此腳本應用程式部署到集合，而不是使用 SEMM 管理的裝置，您可以在這裡新增需求，以確保此應用程式只會在 Surface 裝置或您想要使用 SEMM 管理的裝置上執行。</span><span class="sxs-lookup"><span data-stu-id="50e94-280">However, if you intend to deploy this script application to a collection with devices other than those to be managed with SEMM, you could add requirements here to ensure this application would run only on Surface devices or devices you intend to manage with SEMM.</span></span> <span data-ttu-id="50e94-281">選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="50e94-281">Select **Next** to continue.</span></span>
     
     * <span data-ttu-id="50e94-282">相依性–選取 [**新增** **]** 以開啟 [**新增**相依性] 視窗。</span><span class="sxs-lookup"><span data-stu-id="50e94-282">**Dependencies** – Select **Add** to open the **Add Dependency** window.</span></span>

       * <span data-ttu-id="50e94-283">選取 [ **新增** ] 以開啟 [ **指定所需的應用程式** ] 視窗。</span><span class="sxs-lookup"><span data-stu-id="50e94-283">Select **Add** to open the **Specify Required Application** window.</span></span>

          - <span data-ttu-id="50e94-284">在 [相依性 **群組名稱** ] (欄位中輸入 SEMM 相依性的名稱，例如， *SEMM 元件*) 。</span><span class="sxs-lookup"><span data-stu-id="50e94-284">Enter a name for the SEMM dependencies in the **Dependency Group Name** field (for example, *SEMM Assemblies*).</span></span>

          - <span data-ttu-id="50e94-285">從**可用應用程式**及 MSI 部署類型清單中選取 [ **Microsoft Surface UEFI 管理員**]，然後選取 **[確定**] 以關閉 [**指定所需的應用程式**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="50e94-285">Select **Microsoft Surface UEFI Manager** from the list of **Available Applications** and the MSI deployment type, and then select **OK** to close the **Specify Required Application** window.</span></span>
          
         *   <span data-ttu-id="50e94-286">如果您想要在裝置上使用 Configuration Manager 腳本啟用 SEMM，請將 [ **自動安裝** ] 核取方塊保持為已選取。</span><span class="sxs-lookup"><span data-stu-id="50e94-286">Keep the **Auto Install** check box selected if you want Microsoft Surface UEFI Manager installed automatically on devices when you attempt to enable SEMM with the Configuration Manager scripts.</span></span> <span data-ttu-id="50e94-287">選取 **[確定** ] 以關閉 [ **新增** 相依性] 視窗。</span><span class="sxs-lookup"><span data-stu-id="50e94-287">Select **OK** to close the **Add Dependency** window.</span></span>

     * <span data-ttu-id="50e94-288">選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="50e94-288">Select **Next** to proceed.</span></span>
     
     * <span data-ttu-id="50e94-289">**摘要** -您在整個 [建立部署類型] 嚮導中輸入的資訊會顯示在此頁面上。</span><span class="sxs-lookup"><span data-stu-id="50e94-289">**Summary** – The information you have entered throughout the Create Deployment Type wizard is displayed on this page.</span></span> <span data-ttu-id="50e94-290">選取 **[下一步]** 以確認您的選擇。</span><span class="sxs-lookup"><span data-stu-id="50e94-290">Select **Next** to confirm your selections.</span></span>
     
     * <span data-ttu-id="50e94-291">**進度** –將在此頁面上顯示 SEMM 腳本應用程式的進度列和狀態作為部署類型。</span><span class="sxs-lookup"><span data-stu-id="50e94-291">**Progress** – A progress bar and status as the deployment type is added for the SEMM script application is displayed on this page.</span></span>
     
     * <span data-ttu-id="50e94-292">**完成** –在處理常式完成時，會顯示部署類型建立的確認。</span><span class="sxs-lookup"><span data-stu-id="50e94-292">**Completion** – Confirmation of the deployment type creation is displayed when the process is complete.</span></span> <span data-ttu-id="50e94-293">選取 [ **關閉** ] 以完成 [建立部署類型] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="50e94-293">Select **Close** to finish the Create Deployment Type Wizard.</span></span>

   - <span data-ttu-id="50e94-294">**摘要** ：您在整個 [建立應用程式] 嚮導中輸入的資訊都會顯示。</span><span class="sxs-lookup"><span data-stu-id="50e94-294">**Summary** – The information that you entered throughout the Create Application Wizard is displayed.</span></span> <span data-ttu-id="50e94-295">選取 **[下一步]** 來建立應用程式。</span><span class="sxs-lookup"><span data-stu-id="50e94-295">Select **Next** to create the application.</span></span>

   - <span data-ttu-id="50e94-296">**進度** –在此頁面上顯示應用程式新增至軟體文件庫的進度列和狀態。</span><span class="sxs-lookup"><span data-stu-id="50e94-296">**Progress** – A progress bar and status as the application is added to the Software Library is displayed on this page.</span></span>

   - <span data-ttu-id="50e94-297">**完成** –當應用程式建立處理常式完成時，就會顯示成功建立應用程式的確認。</span><span class="sxs-lookup"><span data-stu-id="50e94-297">**Completion** – Confirmation of the successful application creation is displayed when the application creation process is complete.</span></span> <span data-ttu-id="50e94-298">選取 [ **關閉** ] 以完成 [建立應用程式] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="50e94-298">Select **Close** to finish the Create Application Wizard.</span></span>

<span data-ttu-id="50e94-299">在 Configuration Manager 的軟體庫中提供腳本應用程式之後，您就可以使用您準備好到裝置或集合的腳本來發佈及部署 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-299">After the script application is available in the Software Library of Configuration Manager, you can distribute and deploy SEMM using the scripts you prepared to devices or collections.</span></span> <span data-ttu-id="50e94-300">如果您已將 Microsoft Surface UEFI 系統管理員元件設定為將自動安裝的相依性，您可以在單一步驟中部署 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-300">If you have configured the Microsoft Surface UEFI Manager assemblies as a dependency that will be automatically installed, you can deploy SEMM in a single step.</span></span> <span data-ttu-id="50e94-301">如果您沒有將元件設定為相依性，您必須先將其安裝在您想要管理的裝置上，才能啟用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="50e94-301">If you have not configured the assemblies as a dependency, they must be installed on the devices you intend to manage before you enable SEMM.</span></span>

<span data-ttu-id="50e94-302">當您使用此腳本應用程式及最終使用者可見的設定部署 SEMM 時，PowerShell 腳本將會啟動，並由 PowerShell 視窗顯示憑證的指紋。</span><span class="sxs-lookup"><span data-stu-id="50e94-302">When you deploy SEMM using this script application and with a configuration that is visible to the end user, the PowerShell script will start and the thumbprint for the certificate will be displayed by the PowerShell window.</span></span> <span data-ttu-id="50e94-303">您可以讓使用者記錄這個指紋，並在裝置重新開機後，在 Surface UEFI 出現提示時輸入它。</span><span class="sxs-lookup"><span data-stu-id="50e94-303">You can have your users record this thumbprint and enter it when prompted by Surface UEFI after the device reboots.</span></span>

<span data-ttu-id="50e94-304">或者，您可以將應用程式安裝設定為自動重新開機，並以不可見的使用者的安裝。</span><span class="sxs-lookup"><span data-stu-id="50e94-304">Alternatively, you can configure the application installation to reboot automatically and to install invisibly to the user.</span></span> <span data-ttu-id="50e94-305">在這種情況下，系統會在重新開機時，在每個裝置上輸入指紋。</span><span class="sxs-lookup"><span data-stu-id="50e94-305">In this scenario, a technician will be required to enter the thumbprint on each device as it reboots.</span></span> <span data-ttu-id="50e94-306">任何擁有憑證檔案存取權的技術人員，都可以透過 CertMgr 查看憑證來讀取指紋。</span><span class="sxs-lookup"><span data-stu-id="50e94-306">Any technician with access to the certificate file can read the thumbprint by viewing the certificate with CertMgr.</span></span> <span data-ttu-id="50e94-307">使用 CertMgr 查看指紋的指示是在本文的 [ [建立或修改 SEMM Configuration Manager 腳本](#create-or-modify-the-semm-configuration-manager-scripts) ] 區段中。</span><span class="sxs-lookup"><span data-stu-id="50e94-307">Instructions for viewing the thumbprint with CertMgr are in the [Create or modify the SEMM Configuration Manager scripts](#create-or-modify-the-semm-configuration-manager-scripts) section of this article.</span></span>

<span data-ttu-id="50e94-308">從使用 Configuration Manager 部署的裝置中移除 SEMM，就像透過 Configuration Manager 卸載應用程式一樣簡單。</span><span class="sxs-lookup"><span data-stu-id="50e94-308">Removal of SEMM from a device deployed with Configuration Manager using these scripts is as easy as uninstalling the application with Configuration Manager.</span></span> <span data-ttu-id="50e94-309">這個動作會啟動 ResetSEMM.ps1 腳本，並使用與 SEMM 部署期間使用相同的憑證檔案正確 unenrolls 裝置。</span><span class="sxs-lookup"><span data-stu-id="50e94-309">This action starts the ResetSEMM.ps1 script and properly unenrolls the device with the same certificate file that was used during the deployment of SEMM.</span></span>

> [!NOTE]
> <span data-ttu-id="50e94-310">Microsoft Surface 建議您只有在您需要取消註冊裝置時，才能建立 [重設套件]。</span><span class="sxs-lookup"><span data-stu-id="50e94-310">Microsoft Surface recommends that you create reset packages only when you need to unenroll a device.</span></span> <span data-ttu-id="50e94-311">這些重設套件通常只適用于一個裝置，且由其序列值識別。</span><span class="sxs-lookup"><span data-stu-id="50e94-311">These reset packages are typically valid for only one device, identified by its serial number.</span></span> <span data-ttu-id="50e94-312">不過，您可以針對使用此憑證註冊的任何裝置，建立可使用的通用重設套件。</span><span class="sxs-lookup"><span data-stu-id="50e94-312">You can, however, create a universal reset package that would work for any device enrolled in SEMM with this certificate.</span></span>
> 
> <span data-ttu-id="50e94-313">我們強烈建議您在 SEMM 中使用您用來註冊裝置的憑證，謹慎保護您的通用重設套件。</span><span class="sxs-lookup"><span data-stu-id="50e94-313">We strongly recommend that you protect your universal reset package as carefully as the certificate you used to enroll devices in SEMM.</span></span> <span data-ttu-id="50e94-314">請記住，就像證書本身一樣，此通用重設套件可以用來從 SEMM 取消您組織的任何 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="50e94-314">Please remember that, just like the certificate itself, this universal reset package can be used to unenroll any of your organization’s Surface devices from SEMM.</span></span>
> 
> <span data-ttu-id="50e94-315">當您安裝重設套件時， (LSV) 最低支援的值會重設為1的值。</span><span class="sxs-lookup"><span data-stu-id="50e94-315">When you install a reset package, the Lowest Supported Value (LSV) is reset to a value of 1.</span></span> <span data-ttu-id="50e94-316">您可以使用現有的配置套件重新註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="50e94-316">You can reenroll a device by using an existing configuration package.</span></span> <span data-ttu-id="50e94-317">在取得擁有權之前，裝置會提示您輸入憑證指紋。</span><span class="sxs-lookup"><span data-stu-id="50e94-317">The device will prompt for the certificate thumbprint before ownership is taken.</span></span>
> 
> <span data-ttu-id="50e94-318">基於這個原因，SEMM 中的裝置 reenrollment 會要求在該裝置上建立並安裝新套件。</span><span class="sxs-lookup"><span data-stu-id="50e94-318">For this reason, the reenrollment of a device in SEMM would require a new package to be created and installed on that device.</span></span> <span data-ttu-id="50e94-319">因為此動作是新的註冊，而裝置上已註冊的裝置設定不會變更，所以在取得擁有權之前，裝置會提示您輸入憑證指紋。</span><span class="sxs-lookup"><span data-stu-id="50e94-319">Because this action is a new enrollment and not a change in configuration on a device already enrolled in SEMM, the device will prompt for the certificate thumbprint before ownership is taken.</span></span>
