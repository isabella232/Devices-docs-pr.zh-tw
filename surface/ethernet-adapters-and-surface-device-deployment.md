---
title: 乙太網路卡與 Surface 部署 (Surface)
description: 本文章提供的指導方針與解答可協助您執行 Surface 裝置的網路部署。
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: ethernet, deploy, removable, network, connectivity, boot, firmware, device, adapter, PXE boot, USB, 乙太網路, 部署, 卸除式, 網路, 連線能力, 開機, 韌體, 裝置, 介面卡, PXE 開機
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: 4b0cfd9cadab33d82ae3d0acaa83e007229c6fb8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831301"
---
# <span data-ttu-id="760a0-104">乙太網路卡與 Surface 部署</span><span class="sxs-lookup"><span data-stu-id="760a0-104">Ethernet adapters and Surface deployment</span></span>


<span data-ttu-id="760a0-105">本文提供指引與解答，協助您執行網路部署至 Surface 裝置，包括 Surface Pro 3 及更新版本。</span><span class="sxs-lookup"><span data-stu-id="760a0-105">This article provides guidance and answers to help you perform a network deployment to Surface devices including Surface Pro 3 and later.</span></span>

<span data-ttu-id="760a0-106">Surface 裝置的網路部署可能會對系統管理員造成一些特殊的挑戰。</span><span class="sxs-lookup"><span data-stu-id="760a0-106">Network deployment to Surface devices can pose some unique challenges for system administrators.</span></span> <span data-ttu-id="760a0-107">因為缺少原生的有線乙太網路卡，系統管理員必須透過卸除式乙太網路卡來提供連線。</span><span class="sxs-lookup"><span data-stu-id="760a0-107">Due to the lack of a native wired Ethernet adapter, administrators must provide connectivity through a removable Ethernet adapter.</span></span>

## <span data-ttu-id="760a0-108">選取適用於 Surface 裝置的乙太網路卡</span><span class="sxs-lookup"><span data-stu-id="760a0-108">Select an Ethernet adapter for Surface devices</span></span>


<span data-ttu-id="760a0-109">您必須使用有線網路介面卡，才可以解決如何開機到部署環境，或您的部署解決方案要如何辨識裝置的問題。</span><span class="sxs-lookup"><span data-stu-id="760a0-109">Before you can address the concerns of how you will boot to your deployment environment or how devices will be recognized by your deployment solution, you have to use a wired network adapter.</span></span>

<span data-ttu-id="760a0-110">選擇乙太網路卡的主要考量，是該網路卡會如何從網路將您的 Surface 裝置開機。</span><span class="sxs-lookup"><span data-stu-id="760a0-110">The primary concern when selecting an Ethernet adapter is how that adapter will boot your Surface device from the network.</span></span> <span data-ttu-id="760a0-111">如果您是使用 Windows 部署服務（WDS）預暫存用戶端，或如果您使用的是 Microsoft 端點設定管理員，您可能也想要考慮將可移除的乙太網路介面卡專用於特定的 Surface 裝置，或在多個裝置之間共用。</span><span class="sxs-lookup"><span data-stu-id="760a0-111">If you are pre-staging clients with Windows Deployment Services (WDS) or if you are using Microsoft Endpoint Configuration Manager, you may also want to consider whether the removable Ethernet adapters will be dedicated to a specific Surface device or shared among multiple devices.</span></span> <span data-ttu-id="760a0-112">如需有關共用配接器之潛在衝突的詳細資訊，請參閱本文稍後的[使用可移動乙太網卡管理 MAC 位址](#manage-mac-addresses)。</span><span class="sxs-lookup"><span data-stu-id="760a0-112">For more information on potential conflicts with shared adapters, see [Manage MAC addresses with removable Ethernet adapters](#manage-mac-addresses) later in this article.</span></span>

<span data-ttu-id="760a0-113">只有使用乙太網路卡或 Microsoft 的擴充座時，才支援從網路開機 (PXE 開機)。</span><span class="sxs-lookup"><span data-stu-id="760a0-113">Booting from the network (PXE boot) is only supported when you use an Ethernet adapter or docking station from Microsoft.</span></span> <span data-ttu-id="760a0-114">若要從網路開機，乙太網路卡或擴充座中的晶片必須能在 Surface 裝置的韌體中被偵測並設定為開機裝置。</span><span class="sxs-lookup"><span data-stu-id="760a0-114">To boot from the network, the chipset in the Ethernet adapter or dock must be detected and configured as a boot device in the firmware of the Surface device.</span></span> <span data-ttu-id="760a0-115">Microsoft 乙太網路卡 (例如 Surface 乙太網路卡和 [Surface 擴充座](https://www.microsoft.com/surface/accessories/surface-dock)) 是使用與 Surface 韌體相容的晶片。</span><span class="sxs-lookup"><span data-stu-id="760a0-115">Microsoft Ethernet adapters, such as the Surface Ethernet Adapter and the [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock) use a chipset that is compatible with the Surface firmware.</span></span>

<span data-ttu-id="760a0-116">下列乙太網路裝置支援 Surface 裝置的網路開機：</span><span class="sxs-lookup"><span data-stu-id="760a0-116">The following Ethernet devices are supported for network boot with Surface devices:</span></span>

-   <span data-ttu-id="760a0-117">從 USB 到乙太網路和 USB 3.0 配接器的 Surface</span><span class="sxs-lookup"><span data-stu-id="760a0-117">Surface USB-C to Ethernet and USB 3.0 Adapter</span></span>

-   <span data-ttu-id="760a0-118">Surface USB 3.0 至千兆乙太網卡</span><span class="sxs-lookup"><span data-stu-id="760a0-118">Surface USB 3.0 to Gigabit Ethernet Adapter</span></span>

-   <span data-ttu-id="760a0-119">Surface 擴充座</span><span class="sxs-lookup"><span data-stu-id="760a0-119">Surface Dock</span></span>

-   <span data-ttu-id="760a0-120">Surface 3 擴充座</span><span class="sxs-lookup"><span data-stu-id="760a0-120">Surface 3 Docking Station</span></span>

-   <span data-ttu-id="760a0-121">Surface Pro 3 擴充座</span><span class="sxs-lookup"><span data-stu-id="760a0-121">Surface Pro 3 Docking Station</span></span>

-   <span data-ttu-id="760a0-122">適用於 Surface Pro 和 Surface Pro 2 的擴充座</span><span class="sxs-lookup"><span data-stu-id="760a0-122">Docking Station for Surface Pro and Surface Pro 2</span></span>

<span data-ttu-id="760a0-123">協力廠商乙太網路卡也支援網路部署，雖然它們不支援 PXE 開機。</span><span class="sxs-lookup"><span data-stu-id="760a0-123">Third-party Ethernet adapters are also supported for network deployment, although they do not support PXE boot.</span></span> <span data-ttu-id="760a0-124">若要使用協力廠商乙太網路卡，您必須將驅動程式載入至部署開機映像，且您必須從不同的儲存裝置 (例如 USB 隨身碟) 啟動該開機映像。</span><span class="sxs-lookup"><span data-stu-id="760a0-124">To use a third-party Ethernet adapter, you must load the drivers into the deployment boot image and you must launch that boot image from a separate storage device, such as a USB stick.</span></span>

## <span data-ttu-id="760a0-125">從網路將 Surface 裝置開機</span><span class="sxs-lookup"><span data-stu-id="760a0-125">Boot Surface devices from the network</span></span>

<span data-ttu-id="760a0-126">若要從網路或連接的 USB 隨身碟開機，您必須指示 Surface 裝置從其他開機裝置開機。</span><span class="sxs-lookup"><span data-stu-id="760a0-126">To boot from the network or a connected USB stick, you must instruct the Surface device to boot from an alternate boot device.</span></span> <span data-ttu-id="760a0-127">您可以在系統韌體中變更開機順序，以排定 USB 開機裝置的優先順序，或指示它在開機程序期間從其他的開機裝置開機。</span><span class="sxs-lookup"><span data-stu-id="760a0-127">You can alter the boot order in the system firmware to prioritize USB boot devices, or you can instruct it to boot from an alternate boot device during the boot up process.</span></span>

<span data-ttu-id="760a0-128">若要讓 Surface 裝置從其他開機裝置開機，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="760a0-128">To boot a Surface device from an alternative boot device, follow these steps:</span></span>

1.  <span data-ttu-id="760a0-129">確定 Surface 裝置電源已經關閉。</span><span class="sxs-lookup"><span data-stu-id="760a0-129">Ensure the Surface device is powered off.</span></span>
2.  <span data-ttu-id="760a0-130">長按**降低音量**按鈕。</span><span class="sxs-lookup"><span data-stu-id="760a0-130">Press and hold the **Volume Down** button.</span></span>
3.  <span data-ttu-id="760a0-131">按下並放開**電源**按鈕。</span><span class="sxs-lookup"><span data-stu-id="760a0-131">Press and release the **Power** button.</span></span>
4.  <span data-ttu-id="760a0-132">當系統開始從 USB 隨身碟或乙太網路卡開機之後，放開**降低音量**按鈕。</span><span class="sxs-lookup"><span data-stu-id="760a0-132">After the system begins to boot from the USB stick or Ethernet adapter, release the **Volume Down** button.</span></span>

>[!NOTE]
><span data-ttu-id="760a0-133">除了乙太網路卡，鍵盤也必須連接到 Surface 裝置，以進入預先安裝環境和瀏覽部署精靈。</span><span class="sxs-lookup"><span data-stu-id="760a0-133">In addition to an Ethernet adapter, a keyboard must also be connected to the Surface device to enter the preinstallation environment and navigate the deployment wizard.</span></span>

 
<span data-ttu-id="760a0-134">針對 Windows 10，1511 版本與更新版本 (包括適用於 Windows 10，1511 版本的 Windows 評定及部署套件 (Windows ADK) )，預設會有 Microsoft Surface 乙太網路卡的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="760a0-134">For Windows 10, version 1511 and later – including the Windows Assessment and Deployment Kit (Windows ADK) for Windows 10, version 1511 – the drivers for Microsoft Surface Ethernet Adapters are present by default.</span></span> <span data-ttu-id="760a0-135">如果您正在使用使用 Windows 預先安裝環境 (WinPE) 的部署解決方案 (例如 Microsoft Deployment Toolkit)，並且透過 PXE 從網路開機，請確定您的部署解決方案使用最新版本的 Windows ADK。</span><span class="sxs-lookup"><span data-stu-id="760a0-135">If you are using a deployment solution that uses Windows Preinstallation Environment (WinPE), like the Microsoft Deployment Toolkit, and booting from the network with PXE, ensure that your deployment solution is using the latest version of the Windows ADK.</span></span>

## <a href="" id="manage-mac-addresses"></a><span data-ttu-id="760a0-136">管理卸除式乙太網路卡的 MAC 位址</span><span class="sxs-lookup"><span data-stu-id="760a0-136">Manage MAC addresses with removable Ethernet adapters</span></span>

<span data-ttu-id="760a0-137">系統管理員透過網路執行 Windows 部署的另一項考量，是當您使用相同的乙太網路卡部署到多部電腦時要如何識別電腦。</span><span class="sxs-lookup"><span data-stu-id="760a0-137">Another consideration for administrators performing Windows deployment over the network is how you will identify computers when you use the same Ethernet adapter to deploy to more than one computer.</span></span> <span data-ttu-id="760a0-138">部署技術常用的識別碼是媒體存取控制 (MAC) 位址，該位址會與每個乙太網路卡關聯。</span><span class="sxs-lookup"><span data-stu-id="760a0-138">A common identifier used by deployment technologies is the Media Access Control (MAC) address that is associated with each Ethernet adapter.</span></span> <span data-ttu-id="760a0-139">不過，當使用相同的乙太網路卡來部署到多部電腦時，您無法使用會偵測 MAC 位址的部署技術，因為在不同的電腦上使用卸除式介面卡時會無法區隔 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="760a0-139">However, when you use the same Ethernet adapter to deploy to multiple computers, you cannot use a deployment technology that inspects MAC addresses because there is no way to differentiate the MAC address of the removable adapter when used on the different computers.</span></span>

<span data-ttu-id="760a0-140">避免 MAC 位址衝突最簡單的解決方案，是為每個 Surface 裝置提供專用的卸除式乙太網路介面卡。</span><span class="sxs-lookup"><span data-stu-id="760a0-140">The simplest solution to avoid MAC address conflicts is to provide a dedicated removable Ethernet adapter for each Surface device.</span></span> <span data-ttu-id="760a0-141">對於經常使用乙太網路卡或其他擴充座功能的許多案例而言，這個方法很實際。</span><span class="sxs-lookup"><span data-stu-id="760a0-141">This can make sense in many scenarios where the Ethernet adapter or the additional functionality of the docking station will be used regularly.</span></span> <span data-ttu-id="760a0-142">不過，並非所有的案例都需要使用擴充座的其他連線，或支援有線網路。</span><span class="sxs-lookup"><span data-stu-id="760a0-142">However, not all scenarios call for the additional connectivity of a docking station or support for wired networks.</span></span>

<span data-ttu-id="760a0-143">另一個在共用介面卡時避免衝突的可能解決方案，是使用 [Microsoft Deployment Toolkit (MDT)](https://technet.microsoft.com/windows/dn475741) 來執行 Surface 裝置的部署。</span><span class="sxs-lookup"><span data-stu-id="760a0-143">Another potential solution to avoid conflict when adapters are shared is to use the [Microsoft Deployment Toolkit (MDT)](https://technet.microsoft.com/windows/dn475741) to perform deployment to Surface devices.</span></span> <span data-ttu-id="760a0-144">MDT 不會使用 MAC 位址來識別個別電腦，因此不受限於此限制。</span><span class="sxs-lookup"><span data-stu-id="760a0-144">MDT does not use the MAC address to identify individual computers and thus is not subject to this limitation.</span></span> <span data-ttu-id="760a0-145">不過，MDT 會使用 Windows 部署服務來提供 PXE 開機功能，並受限於和前置階段用戶端有關的限制，本節稍後會說明。</span><span class="sxs-lookup"><span data-stu-id="760a0-145">However, MDT does use Windows Deployment Services to provide PXE boot functionality, and is subject to the limitations regarding pre-staged clients which is covered later in this section.</span></span>

<span data-ttu-id="760a0-146">當您使用共用的介面卡來部署時，針對受影響之部署技術的解決方案是使用另一種方法來識別唯一系統。</span><span class="sxs-lookup"><span data-stu-id="760a0-146">When you use a shared adapter for deployment, the solution for affected deployment technologies is to use another means to identify unique systems.</span></span> <span data-ttu-id="760a0-147">對於 Configuration Manager 和 WDS 而言，兩者皆可能受此問題影響，解決方案是使用電腦製造商內嵌於電腦韌體中的系統通用唯一識別元 (系統 UUID)。</span><span class="sxs-lookup"><span data-stu-id="760a0-147">For Configuration Manager and WDS, both of which can be affected by this issue, the solution is to use the System Universal Unique Identifier (System UUID) that is embedded in the computer firmware by the computer manufacturer.</span></span> <span data-ttu-id="760a0-148">對於 Surface 裝置，您可以在電腦韌體中的 \[裝置資訊\] 底下看到此項目。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="760a0-148">For Surface devices, you can see this entry in the computer firmware under **Device Information**.</span></span>

<span data-ttu-id="760a0-149">若要存取 Surface 裝置的韌體，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="760a0-149">To access the firmware of a Surface device, follow these steps:</span></span>

1.  <span data-ttu-id="760a0-150">確定 Surface 裝置電源已經關閉。</span><span class="sxs-lookup"><span data-stu-id="760a0-150">Ensure the Surface device is powered off.</span></span>
2.  <span data-ttu-id="760a0-151">長按**增強音量**按鈕。</span><span class="sxs-lookup"><span data-stu-id="760a0-151">Press and hold the **Volume Up** button.</span></span>
3.  <span data-ttu-id="760a0-152">按下並放開**電源**按鈕。</span><span class="sxs-lookup"><span data-stu-id="760a0-152">Press and release the **Power** button.</span></span>
4.  <span data-ttu-id="760a0-153">裝置開始開機之後，放開**增強音量**按鈕。</span><span class="sxs-lookup"><span data-stu-id="760a0-153">After the device begins to boot, release the **Volume Up** button.</span></span>

<span data-ttu-id="760a0-154">當使用 WDS 部署時，只有在部署伺服器設為僅回應已知的前置階段用戶端時，才會使用 MAC 位址識別電腦。</span><span class="sxs-lookup"><span data-stu-id="760a0-154">When deploying with WDS, the MAC address is only used to identify a computer when the deployment server is configured to respond only to known, pre-staged clients.</span></span> <span data-ttu-id="760a0-155">當預先設置用戶端時，系統管理員會在 Active Directory 中建立電腦帳戶，並根據 MAC 位址或系統 UUID 定義該電腦。</span><span class="sxs-lookup"><span data-stu-id="760a0-155">When pre-staging a client, an administrator creates a computer account in Active Directory and defines that computer by the MAC address or the System UUID.</span></span> <span data-ttu-id="760a0-156">若要避免共用乙太網路卡造成識別衝突，您應該使用[系統 UUID 來定義前置階段用戶端](https://technet.microsoft.com/library/cc742034)。</span><span class="sxs-lookup"><span data-stu-id="760a0-156">To avoid the identity conflicts caused by shared Ethernet adapters, you should use [System UUID to define pre-staged clients](https://technet.microsoft.com/library/cc742034).</span></span> <span data-ttu-id="760a0-157">或者，您可以設定 WDS 來回應不需要由 MAC 位址或系統 UUID 定義的未知用戶端，方法是選取 \[Windows 部署伺服器屬性\] 中 [\[PXE 回應\] 索引標籤](https://technet.microsoft.com/library/cc732360)上的 \[回應所有用戶端電腦 (已知及未知)\] 選項。\*\*\*\*\*\*\*\*\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="760a0-157">Alternatively, you can configure WDS to respond to unknown clients that do not require definition by either MAC address or System UUID by selecting the **Respond to all client computers (known and unknown)** option on the [**PXE Response** tab](https://technet.microsoft.com/library/cc732360) in **Windows Deployment Server Properties**.</span></span>

<span data-ttu-id="760a0-158">使用 Configuration Manager 共用乙太網路卡的衝突可能性會更高。</span><span class="sxs-lookup"><span data-stu-id="760a0-158">The potential for conflicts with shared Ethernet adapters is much higher with Configuration Manager.</span></span> <span data-ttu-id="760a0-159">WDS 只有在設定為使用 MAC 位址來定義個別系統時才會這麼做，而 Configuration Manager 則無論是執行部署到新電腦或未知電腦，皆會使用 MAC 位址來定義個別的系統。</span><span class="sxs-lookup"><span data-stu-id="760a0-159">Where WDS only uses MAC addresses to define individual systems when configured to do so, Configuration Manager uses the MAC address to define individual systems whenever performing a deployment to new or unknown computers.</span></span> <span data-ttu-id="760a0-160">這會導致裝置設定錯誤，或甚至導致無法透過共用乙太網路卡部署多個系統。</span><span class="sxs-lookup"><span data-stu-id="760a0-160">This can result in improperly configured devices or even the inability to deploy more than one system with a shared Ethernet adapter.</span></span> <span data-ttu-id="760a0-161">此情況有幾種可能的解決方案，詳細說明[如何在多個 SCCM OSD 中使用相同的外部乙太網卡](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374)，這是核心基礎結構和安全性博客的博客文章。</span><span class="sxs-lookup"><span data-stu-id="760a0-161">There are several potential solutions for this situation that are described in detail in [How to Use The Same External Ethernet Adapter For Multiple SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374), a blog post on the Core Infrastructure and Security Blog.</span></span>

 

 





