---
title: 自訂 Surface 部署的 OOBE (Surface)
description: 本文會逐步引導您為組織中的終端使用者自訂 Surface 全新體驗的流程。
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: deploy, customize, automate, network, Pen, pair, boot, 部署, 自訂, 自動化, 網路, 手寫筆, 配對, 開機
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 97cc262d803875a76427d04c8f9b70547152f895
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831561"
---
# <span data-ttu-id="03014-104">自訂 Surface 部署的 OOBE</span><span class="sxs-lookup"><span data-stu-id="03014-104">Customize the OOBE for Surface deployments</span></span>

<span data-ttu-id="03014-105">本文將說明針對貴組織中的使用者自訂表格面全新體驗。</span><span class="sxs-lookup"><span data-stu-id="03014-105">This article describes customizing the Surface out-of-box experience for end users in your organization.</span></span>

<span data-ttu-id="03014-106">自訂所部署之電腦的使用者初次啟動體驗 (全新體驗，或簡稱為 OOBE) 是 Windows 部署中的常見做法。</span><span class="sxs-lookup"><span data-stu-id="03014-106">It is common practice in a Windows deployment to customize the user experience for the first startup of deployed computers — the out-of-box experience, or OOBE.</span></span>

>[!NOTE]
><span data-ttu-id="03014-107">OOBE 也經常用於描述 Windows 設定期間顯示使用者體驗的階段或設定階段。</span><span class="sxs-lookup"><span data-stu-id="03014-107">OOBE is also often used to describe the phase, or configuration pass, of Windows setup during which the user experience is displayed.</span></span> <span data-ttu-id="03014-108">如需設定之 OOBE 階段的詳細資訊，請參閱[設定階段的運作方式](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx)。</span><span class="sxs-lookup"><span data-stu-id="03014-108">For more information about the OOBE phase of setup, see [How Configuration Passes Work](https://msdn.microsoft.com/library/windows/hardware/dn898581.aspx).</span></span>

<span data-ttu-id="03014-109">某些情況下，您可能希望提供完整的自動部署，以確保部署完成時，使用者不需進行任何互動即可使用電腦。</span><span class="sxs-lookup"><span data-stu-id="03014-109">In some scenarios, you may want to provide complete automation to ensure that at the end of a deployment, computers are ready for use without any interaction from the user.</span></span> <span data-ttu-id="03014-110">而在其他情況下，您可能希望保留體驗中的關鍵部分，讓使用者執行必要的動作，或在重要的選項之間進行選取。</span><span class="sxs-lookup"><span data-stu-id="03014-110">In other scenarios, you may want to leave key elements of the experience for users to perform necessary actions or select between important choices.</span></span> <span data-ttu-id="03014-111">對於部署 Surface 裝置的系統管理員，這兩種情況各自有需要克服的挑戰。</span><span class="sxs-lookup"><span data-stu-id="03014-111">For administrators deploying to Surface devices, each of these scenarios presents a unique challenge to overcome.</span></span>

> [!NOTE]
> <span data-ttu-id="03014-112">本文不適用於 Surface Pro X。如需詳細資訊，請參閱[部署、管理及維護 Surface Pro X](surface-pro-arm-app-management.md)</span><span class="sxs-lookup"><span data-stu-id="03014-112">This article does not apply to Surface Pro X. For more information, refer to [Deploying, managing, and servicing Surface Pro X](surface-pro-arm-app-management.md)</span></span>

<span data-ttu-id="03014-113">本文提供部署時可能需要額外步驟之案例的摘要。</span><span class="sxs-lookup"><span data-stu-id="03014-113">This article provides a summary of the scenarios where a deployment might require additional steps.</span></span> <span data-ttu-id="03014-114">其中也提供確保任何新部署的 Surface 能達到預期之體驗的必要資訊。</span><span class="sxs-lookup"><span data-stu-id="03014-114">It also provides the required information to ensure that the desired experience is achieved on any newly deployed Surface device.</span></span> <span data-ttu-id="03014-115">本文的適用對象為熟悉部署程序及回應檔案和[建立 Windows 10 參照映像](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image)等概念的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="03014-115">This article is intended for administrators who are familiar with the deployment process, as well as concepts such as answer files and [reference images](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image).</span></span>

>[!NOTE]
><span data-ttu-id="03014-116">雖然在部署期間，在使用自動化部署方案（例如[Microsoft 部署工具套件（MDT）](https://go.microsoft.com/fwlink/p/?LinkId=618117)或 Microsoft 端點建構管理員作業系統部署（OSD）等自動部署解決方案期間，仍會執行設定的 OOBE 階段，但在部署嚮導和任務順序中提供的設定會自動進行。</span><span class="sxs-lookup"><span data-stu-id="03014-116">Although the OOBE phase of setup is still run during a deployment with an automated deployment solution such as the [Microsoft Deployment Toolkit (MDT)](https://go.microsoft.com/fwlink/p/?LinkId=618117) or Microsoft Endpoint Configuration Manager Operating System Deployment (OSD), it is automated by the settings supplied in the Deployment Wizard and task sequence.</span></span> <span data-ttu-id="03014-117">如需詳細資訊，請參閱：</span><span class="sxs-lookup"><span data-stu-id="03014-117">For more information see:</span></span><br/>
>- [<span data-ttu-id="03014-118">使用 Microsoft Deployment Toolkit 部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="03014-118">Deploy Windows 10 with the Microsoft Deployment Toolkit</span></span>](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)
>- [<span data-ttu-id="03014-119">使用 System Center 2012 R2 Configuration Manager 部署 Windows 10</span><span class="sxs-lookup"><span data-stu-id="03014-119">Deploy Windows 10 with System Center 2012 R2 Configuration Manager</span></span>](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-system-center-2012-r2-configuration-manager)

 

## <span data-ttu-id="03014-120">案例 1：使用 MDT 2013 執行 OOBE 時的無線網路功能</span><span class="sxs-lookup"><span data-stu-id="03014-120">Scenario 1: Wireless networking in OOBE with MDT 2013</span></span>


<span data-ttu-id="03014-121">當 OOBE 執行期間有無線網路介面卡存在時，會顯示 \[加入無線網路\] 頁面，並提示使用者連線至無線網路。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="03014-121">When a wireless network adapter is present during OOBE, the **Join a wireless network** page is displayed, which prompts a user to connect to a wireless network.</span></span> <span data-ttu-id="03014-122">部署技術 (包含 MDT 2013) 不會自動隱藏此頁面，因此即使已將部署設定為完全自動化仍會顯示此頁面。</span><span class="sxs-lookup"><span data-stu-id="03014-122">This page is not automatically hidden by deployment technologies, including MDT 2013, and therefore will be displayed even when a deployment is configured for complete automation.</span></span>

<span data-ttu-id="03014-123">為了確保自動部署不會因為此頁面而停止，必須在回應檔案 **HideWirelessSetupInOOBE** 中設定額外的設定來隱藏此頁面。</span><span class="sxs-lookup"><span data-stu-id="03014-123">To ensure that an automated deployment is not stopped by this page, the page must be hidden by configuring an additional setting in the answer file, **HideWirelessSetupInOOBE**.</span></span> <span data-ttu-id="03014-124">您可以在[自動 Windows 設定參考](https://technet.microsoft.com/library/ff716213.aspx)中找到關於 **HideWirelessSetupInOOBE** 設定的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="03014-124">You can find additional information about the **HideWirelessSetupInOOBE** setting in [Unattended Windows Setup Reference](https://technet.microsoft.com/library/ff716213.aspx).</span></span>

## <span data-ttu-id="03014-125">案例 2：在 OOBE 中配對 Surface 手寫筆</span><span class="sxs-lookup"><span data-stu-id="03014-125">Scenario 2: Surface Pen pairing in OOBE</span></span>


<span data-ttu-id="03014-126">當您首次將 Surface Pro 3、Surface Pro 4、Surface Book 或 Surface Studio 從套件中取出並啟動時，原廠映像的初次執行體驗會包含一個提示，要求您將隨附的 Surface 手寫筆與裝置配對。</span><span class="sxs-lookup"><span data-stu-id="03014-126">When you first take a Surface Pro 3, Surface Pro 4, Surface Book, or Surface Studio out of the package and start it up, the first-run experience of the factory image includes a prompt that asks you to pair the included Surface Pen to the device.</span></span> <span data-ttu-id="03014-127">只有裝置出廠時隨附的原廠映象會提供此提示，其他用於部署的映像則不會，例如從「大量授權服務中心」下載的 Windows 企業版安裝媒體。</span><span class="sxs-lookup"><span data-stu-id="03014-127">This prompt is only provided by the factory image that ships with the device and is not included in other images used for deployment, such as the Windows Enterprise installation media downloaded from the Volume Licensing Service Center.</span></span> <span data-ttu-id="03014-128">因為在此體驗之外配對藍牙 Surface 手寫筆需要進入「控制台」或「電腦設定」並手動配對藍牙裝置，因此您可能想要讓使用者或技術人員使用此提示來進行配對作業。</span><span class="sxs-lookup"><span data-stu-id="03014-128">Because pairing the Bluetooth Surface Pen outside of this experience requires that you enter the Control Panel or PC Settings and manually pair a Bluetooth device, you may want to have users or a technician use this prompt to perform the pairing operation.</span></span>

<span data-ttu-id="03014-129">若要在 OOBE 中提供原廠 Surface 手寫筆配對體驗，您必須從原廠 Surface 映像複製四個檔案到參考映像。</span><span class="sxs-lookup"><span data-stu-id="03014-129">To provide the factory Surface Pen pairing experience in OOBE, you must copy four files from the factory Surface image into the reference image.</span></span> <span data-ttu-id="03014-130">您可以在擷取參考映像之前，將這些檔案複製到參考環境，或者您可於稍後使用「部署映像服務與管理」(DISM) 掛接映像時再將它們加入。</span><span class="sxs-lookup"><span data-stu-id="03014-130">You can copy these files into the reference environment before you capture the reference image, or you can add them later by using Deployment Image Servicing and Management (DISM) to mount the image.</span></span> <span data-ttu-id="03014-131">四個必要的檔案是︰</span><span class="sxs-lookup"><span data-stu-id="03014-131">The four required files are:</span></span>

-   <span data-ttu-id="03014-132">%windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml</span><span class="sxs-lookup"><span data-stu-id="03014-132">%windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml</span></span>
-   <span data-ttu-id="03014-133">%windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="03014-133">%windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png</span></span>
-   <span data-ttu-id="03014-134">%windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="03014-134">%windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png</span></span>
-   <span data-ttu-id="03014-135">%windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png</span><span class="sxs-lookup"><span data-stu-id="03014-135">%windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png</span></span>

>[!NOTE]
><span data-ttu-id="03014-136">您應該從與要部署的 Surface 裝置相同型號的原廠映像複製這些檔案。</span><span class="sxs-lookup"><span data-stu-id="03014-136">You should copy the files from a factory image for the same model Surface device that you intend to deploy to.</span></span> <span data-ttu-id="03014-137">例如，您應該使用 Surface Pro 7 中的檔案來部署到 Surface Pro 7，並將 Surface Book 2 中的檔案部署到 surface Book 2，但不應使用 Surface Pro 7 中的檔案來部署 Surface Book 或 Surface Pro 6。</span><span class="sxs-lookup"><span data-stu-id="03014-137">For example, you should use the files from a Surface Pro 7 to deploy to Surface Pro 7, and the files from Surface Book 2 to deploy Surface Book 2, but you should not use the files from a Surface Pro 7 to deploy Surface Book or Surface Pro 6.</span></span>

 

<span data-ttu-id="03014-138">[部署 Surface Pro 3 手寫筆和 OneNote 的祕訣](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/)中有提供將這些必要檔案加入映像的逐步說明。</span><span class="sxs-lookup"><span data-stu-id="03014-138">The step-by-step process for adding these required files to an image is described in [Deploying Surface Pro 3 Pen and OneNote Tips](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/).</span></span> <span data-ttu-id="03014-139">這篇部落格文章也包含確保已安裝 Surface 手寫筆快速筆記體驗 (使用者只要按一下就能將筆記傳送至 OneNote) 之必要更新的祕訣。</span><span class="sxs-lookup"><span data-stu-id="03014-139">This blog post also includes tips to ensure that the necessary updates for the Surface Pen Quick Note-Taking Experience are installed, which allows users to send notes to OneNote with a single click.</span></span>

 

 





