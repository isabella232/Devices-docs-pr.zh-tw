---
title: 在 Surface 裝置上啟用 PEAP、EAP-FAST 和 Cisco LEAP (Surface)
description: 了解如何讓 Surface 裝置支援 PEAP、EAP-FAST 和 Cisco LEAP 通訊協定。
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: network, wireless, device, deploy, authentication, protocol, 網路, 無線, 裝置, 部署, 驗證, 通訊協定
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 1a9bef0a6e0bfdd4bede1b508b4013fd14e1a0bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831713"
---
# <span data-ttu-id="93c3d-104">在 Surface 裝置上啟用 PEAP、EAP-FAST 和 Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="93c3d-104">Enable PEAP, EAP-FAST, and Cisco LEAP on Surface devices</span></span>


<span data-ttu-id="93c3d-105">了解如何讓 Surface 裝置支援 PEAP、EAP-FAST 和 Cisco LEAP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="93c3d-105">Find out how to enable support for PEAP, EAP-FAST, or Cisco LEAP protocols on your Surface device.</span></span>

<span data-ttu-id="93c3d-106">如果您的企業中使用 PEAP、EAP-FAST 或 Cisco LEAP，您可能已經知道 Surface 裝置並不支援這三種無線驗證通訊協定。</span><span class="sxs-lookup"><span data-stu-id="93c3d-106">If you use PEAP, EAP-FAST, or Cisco LEAP in your enterprise network, you probably already know that these three wireless authentication protocols are not supported by Surface devices out of the box.</span></span> <span data-ttu-id="93c3d-107">有些使用者可能在嘗試連線到無線網路時發現，有些則可能是在無法存取網路內部資源 (例如檔案共用和內部網站) 時發現。</span><span class="sxs-lookup"><span data-stu-id="93c3d-107">Some users may discover this when they attempt to connect to your wireless network; others may discover it when they are unable to gain access to resources inside the network, like file shares and internal sites.</span></span> <span data-ttu-id="93c3d-108">如需詳細資訊，請參閱[可延伸的驗證通訊協定](https://technet.microsoft.com/network/bb643147)。</span><span class="sxs-lookup"><span data-stu-id="93c3d-108">For more information, see [Extensible Authentication Protocol](https://technet.microsoft.com/network/bb643147).</span></span>

<span data-ttu-id="93c3d-109">您可以從 USB 或檔案共用執行小型的 MSI 套件來新增對各通訊協定的支援。</span><span class="sxs-lookup"><span data-stu-id="93c3d-109">You can add support for each protocol by executing a small MSI package from a USB stick or from a file share.</span></span> <span data-ttu-id="93c3d-110">對於想要在其 Surface 裝置上啟用 EAP 支援的組織，MSI 套件格式支援使用許多管理和部署工具（例如 Microsoft 部署工具箱（MDT）與 Microsoft 端點設定管理員）進行部署。</span><span class="sxs-lookup"><span data-stu-id="93c3d-110">For organizations that want to enable EAP support on their Surface devices, the MSI package format supports deployment with many management and deployment tools, like the Microsoft Deployment Toolkit (MDT) and Microsoft Endpoint Configuration Manager.</span></span>

## <a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a><span data-ttu-id="93c3d-111">下載 PEAP、EAP-FAST 或 Cisco LEAP 安裝檔</span><span class="sxs-lookup"><span data-stu-id="93c3d-111">Download PEAP, EAP-FAST, or Cisco LEAP installation files</span></span>


<span data-ttu-id="93c3d-112">您可以從 Microsoft 下載中心下載單一的 zip 壓縮檔，其中的 MSI 安裝檔適用於 PEAP、EAP-FAST 或 Cisco LEAP。</span><span class="sxs-lookup"><span data-stu-id="93c3d-112">You can download the MSI installation files for PEAP, EAP-FAST, or Cisco LEAP in a single zip archive file from the Microsoft Download Center.</span></span> <span data-ttu-id="93c3d-113">若要下載此檔案，請移至 Microsoft 下載中心的[適用於 IT 專業人員的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)頁面，按一下**下載**，然後選取 **Cisco EAP-Supplicant Installer.zip** 檔案。</span><span class="sxs-lookup"><span data-stu-id="93c3d-113">To download this file, go to the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page on the Microsoft Download Center, click **Download**, and then select the **Cisco EAP-Supplicant Installer.zip** file.</span></span>

## <span data-ttu-id="93c3d-114">使用 MDT 部署 PEAP、EAP-FAST 或 Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="93c3d-114">Deploy PEAP, EAP-FAST, or Cisco LEAP with MDT</span></span>


<span data-ttu-id="93c3d-115">如果您的組織中已經針對 Surface 裝置執行 Windows 部署，您就可以快速且輕鬆地將各通訊協定的安裝檔加入部署共用，並於部署期間設定自動安裝。</span><span class="sxs-lookup"><span data-stu-id="93c3d-115">If you are already performing a Windows deployment to Surface devices in your organization, it is quick and easy to add the installation files for each protocol to your deployment share and configure automatic installation during deployment.</span></span> <span data-ttu-id="93c3d-116">您甚至可以設定工作順序，使用相同程序來更新先前部署的 Surface 裝置以支援這些通訊協定。</span><span class="sxs-lookup"><span data-stu-id="93c3d-116">You can even configure a task sequence that updates previously deployed Surface devices to provide support for these protocols using the same process.</span></span>

<span data-ttu-id="93c3d-117">若要在新部署的 Surface 裝置上啟用對 PEAP、EAP-FAST 或 Cisco LEAP 的支援，請按照下列步驟：</span><span class="sxs-lookup"><span data-stu-id="93c3d-117">To enable support for PEAP, EAP-FAST, or Cisco LEAP on newly deployed Surface devices, follow these steps:</span></span>

1.  <span data-ttu-id="93c3d-118">下載各通訊協定的安裝檔並解壓縮至位於易存取位置的個別資料夾。</span><span class="sxs-lookup"><span data-stu-id="93c3d-118">Download and extract the installation files for each protocol to separate folders in an easily accessible location.</span></span>

2.  <span data-ttu-id="93c3d-119">開啟 MDT Deployment Workbench 並展開部署共用至 **\[Applications\] (應用程式)** 資料夾。</span><span class="sxs-lookup"><span data-stu-id="93c3d-119">Open the MDT Deployment Workbench and expand your deployment share to the **Applications** folder.</span></span>

3.  <span data-ttu-id="93c3d-120">從 **\[Action\] (動作)** 窗格選取 **\[New Application\] (新增應用程式)**。</span><span class="sxs-lookup"><span data-stu-id="93c3d-120">Select **New Application** from the **Action** pane.</span></span>

4.  <span data-ttu-id="93c3d-121">選擇 **\[Application with source files\] (應用程式與來源檔案)** 以將 MSI 檔案複製到部署共用。</span><span class="sxs-lookup"><span data-stu-id="93c3d-121">Choose **Application with source files** to copy the MSI files into the Deployment Share.</span></span>

5.  <span data-ttu-id="93c3d-122">選取在步驟 1 時為所需通訊協定建立的資料夾。</span><span class="sxs-lookup"><span data-stu-id="93c3d-122">Select the folder you created in step 1 for the desired protocol.</span></span>

6.  <span data-ttu-id="93c3d-123">為部署共用中將儲存安裝檔的資料夾命名。</span><span class="sxs-lookup"><span data-stu-id="93c3d-123">Name the folder in the deployment share where the installation files will be stored.</span></span>

7.  <span data-ttu-id="93c3d-124">指定命令列來部署應用程式：</span><span class="sxs-lookup"><span data-stu-id="93c3d-124">Specify the command line to deploy the application:</span></span>

    -   <span data-ttu-id="93c3d-125">PEAP 使用 **EAP-PEAP.msi /qn /norestart**。</span><span class="sxs-lookup"><span data-stu-id="93c3d-125">For PEAP use **EAP-PEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="93c3d-126">LEAP 使用 **EAP-LEAP.msi /qn /norestart**。</span><span class="sxs-lookup"><span data-stu-id="93c3d-126">For LEAP use **EAP-LEAP.msi /qn /norestart**.</span></span>

    -   <span data-ttu-id="93c3d-127">EAP-FAST 使用 **EAP-FAST.msi /qn /norestart**。</span><span class="sxs-lookup"><span data-stu-id="93c3d-127">For EAP-FAST use **EAP-FAST.msi /qn /norestart**.</span></span>

8.  <span data-ttu-id="93c3d-128">使用預設選項來完成 New Application Wizard (新增應用程式精靈)。</span><span class="sxs-lookup"><span data-stu-id="93c3d-128">Use the default options to complete the New Application Wizard.</span></span>

9.  <span data-ttu-id="93c3d-129">針對各個所需的通訊協定重複步驟 3 至步驟 8。</span><span class="sxs-lookup"><span data-stu-id="93c3d-129">Repeat steps 3 through 8 for each desired protocol.</span></span>

<span data-ttu-id="93c3d-130">執行這些步驟將三個 MSI 套件以應用程式的方式匯入 MDT 之後，將可以從 Windows Deployment Wizard (Windows 部署精靈) 的 \[Applications\] (應用程式) 頁面選取它們。</span><span class="sxs-lookup"><span data-stu-id="93c3d-130">After you’ve performed these steps to import the three MSI packages as applications into MDT, they will be available for selection in the Applications page of the Windows Deployment Wizard.</span></span> <span data-ttu-id="93c3d-131">雖然在某些簡單的部署情況下，技術人員只需要在部署時選取每個套件即可，但不建議這麼做。</span><span class="sxs-lookup"><span data-stu-id="93c3d-131">Although in some simple deployment scenarios it might be sufficient to have technicians select each package at the time of deployment, it is not recommended.</span></span> <span data-ttu-id="93c3d-132">此做法可能會造成技術人員嘗試將這些套件套用至 Surface 裝置以外的其他電腦，或因人為錯誤而在沒有支援 EAP 的情況下部署 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="93c3d-132">This practice introduces the possibility that a technician could attempt to apply these packages to computers other than Surface devices, or that a Surface device could be deployed without EAP support due to human error.</span></span>

<span data-ttu-id="93c3d-133">若要在「安裝應用程式」頁面隱藏這些應用程式，請選取各應用程式的 **[在部署精靈中隱藏此應用程式]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="93c3d-133">To hide these applications from the Install Applications page, select the **Hide this application in the Deployment Wizard** checkbox in the properties of each application.</span></span> <span data-ttu-id="93c3d-134">隱藏應用程式之後，它們就不會在部署期間顯示為選用的應用程式。</span><span class="sxs-lookup"><span data-stu-id="93c3d-134">After the applications are hidden, they will not be displayed as optional applications during deployment.</span></span> <span data-ttu-id="93c3d-135">若要透過您的 Surface 部署工作順序部署它們，就必須透過工作順序中的個別步驟明確定義它們來加以安裝。</span><span class="sxs-lookup"><span data-stu-id="93c3d-135">To deploy them in your Surface deployment task sequence, they must be explicitly defined for installation through a separate step in the task sequence.</span></span>

<span data-ttu-id="93c3d-136">若要明確指定通訊協定，請按照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="93c3d-136">To specify the protocol(s) explicitly, follow these steps:</span></span>

1.  <span data-ttu-id="93c3d-137">從 MDT Deployment Workbench 開啟 Surface 部署工作順序內容。</span><span class="sxs-lookup"><span data-stu-id="93c3d-137">Open your Surface deployment task sequence properties from the MDT Deployment Workbench.</span></span>

2.  <span data-ttu-id="93c3d-138">在 **\[Task Sequence\] (工作順序)** 索引標籤中，選取 **\[State Restore\] (狀態還原)** 底下的 **\[Install Applications\] (安裝應用程式)**。</span><span class="sxs-lookup"><span data-stu-id="93c3d-138">On the **Task Sequence** tab, select the **Install Applications** step under **State Restore**.</span></span> <span data-ttu-id="93c3d-139">通常可以在應用程式安裝前和應用程式安裝後 Windows Update 步驟之間找到。</span><span class="sxs-lookup"><span data-stu-id="93c3d-139">This is typically found between the pre-application and post-application Windows Update steps.</span></span>

3.  <span data-ttu-id="93c3d-140">使用 **\[Add\] (新增)** 按鈕來從 **\[General\] (一般)** 類別建立新的 **\[Install Application\] (安裝應用程式)** 步驟。</span><span class="sxs-lookup"><span data-stu-id="93c3d-140">Use the **Add** button to create a new **Install Application** step from the **General** category.</span></span>

4.  <span data-ttu-id="93c3d-141">在步驟 **\[Properties\] (內容)** 索引標籤中選取 **\[Install a single application\] (安裝單一應用程式)**。</span><span class="sxs-lookup"><span data-stu-id="93c3d-141">Select **Install a single application** in the step **Properties** tab.</span></span>

5.  <span data-ttu-id="93c3d-142">從清單中選取所需的 EAP 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="93c3d-142">Select the desired EAP protocol from the list.</span></span>

6.  <span data-ttu-id="93c3d-143">針對各個所需的通訊協定重複步驟 2 至步驟 5。</span><span class="sxs-lookup"><span data-stu-id="93c3d-143">Repeat steps 2 through 5 for each desired protocol.</span></span>

## <span data-ttu-id="93c3d-144">使用 Configuration Manager 部署 PEAP、EAP-FAST 或 Cisco LEAP</span><span class="sxs-lookup"><span data-stu-id="93c3d-144">Deploy PEAP, EAP-FAST, or Cisco LEAP with Configuration Manager</span></span>


<span data-ttu-id="93c3d-145">對於使用 Configuration Manager 管理 Surface 裝置的組織而言，部署 PEAP、EAP-FAST 或 Cisco LEAP 甚至更為容易。</span><span class="sxs-lookup"><span data-stu-id="93c3d-145">For organizations that manage Surface devices with Configuration Manager, it is even easier to deploy PEAP, EAP-FAST, or Cisco LEAP support to Surface devices.</span></span> <span data-ttu-id="93c3d-146">只要將每個 MSI 檔案以應用程式的方式從 Software Library 匯入，並對 Surface 裝置集合設定部署即可。</span><span class="sxs-lookup"><span data-stu-id="93c3d-146">Simply import each MSI file as an application from the Software Library and configure a deployment to your Surface device collection.</span></span>

<span data-ttu-id="93c3d-147">如需以 Configuration Manager 部署應用程式的方法的詳細資訊，請參閱[如何在 Configuration Manager 中建立應用程式](https://technet.microsoft.com/library/gg682159.aspx)和[如何在 Configuration Manager 中部署應用程式](https://technet.microsoft.com/library/gg682082.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93c3d-147">For more information on how to deploy applications with Configuration Manager see [How to Create Applications in Configuration Manager](https://technet.microsoft.com/library/gg682159.aspx) and [How to Deploy Applications in Configuration Manager](https://technet.microsoft.com/library/gg682082.aspx).</span></span>

 

 





