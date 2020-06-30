---
title: 使用 SEMM 來保護及管理 Surface Hub 的2秒
description: 深入瞭解使用 SEMM 保護 Surface Hub 的詳細資料。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831442"
---
# <span data-ttu-id="e256c-104">使用 SEMM 和 UEFI 保護及管理 Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="e256c-104">Secure and manage Surface Hub 2S with SEMM and UEFI</span></span>

<span data-ttu-id="e256c-105">在 Surface Hub 2 的新功能中，您可以使用 SEMM 來管理裝置的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="e256c-105">New in Surface Hub 2S, you can use SEMM to manage the UEFI setting of the device.</span></span>
<span data-ttu-id="e256c-106">使用 Microsoft Surface UEFI 配置器來控制下列元件：</span><span class="sxs-lookup"><span data-stu-id="e256c-106">Use the Microsoft Surface UEFI Configurator to control the following components:</span></span>

- <span data-ttu-id="e256c-107">有線 LAN</span><span class="sxs-lookup"><span data-stu-id="e256c-107">Wired LAN</span></span>
- <span data-ttu-id="e256c-108">相機</span><span class="sxs-lookup"><span data-stu-id="e256c-108">Cameras</span></span>
- <span data-ttu-id="e256c-109">藍牙</span><span class="sxs-lookup"><span data-stu-id="e256c-109">Bluetooth</span></span>
- <span data-ttu-id="e256c-110">Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="e256c-110">Wi-Fi</span></span>
- <span data-ttu-id="e256c-111">佔用感應器</span><span class="sxs-lookup"><span data-stu-id="e256c-111">Occupancy sensor</span></span>

<span data-ttu-id="e256c-112">使用 Microsoft Surface UEFI 配置器來開啟或關閉下列 UEFI 設定：</span><span class="sxs-lookup"><span data-stu-id="e256c-112">Use the Microsoft Surface UEFI Configurator to turn on or off the following UEFI settings:</span></span>

- <span data-ttu-id="e256c-113">開機</span><span class="sxs-lookup"><span data-stu-id="e256c-113">Boot</span></span>

    - <span data-ttu-id="e256c-114">適用於 PXE 開機 的 IPv6</span><span class="sxs-lookup"><span data-stu-id="e256c-114">IPv6 for PXE Boot</span></span>
    - <span data-ttu-id="e256c-115">替代開機</span><span class="sxs-lookup"><span data-stu-id="e256c-115">Alternate Boot</span></span>
    - <span data-ttu-id="e256c-116">開機順序鎖定</span><span class="sxs-lookup"><span data-stu-id="e256c-116">Boot Order Lock</span></span>
    - <span data-ttu-id="e256c-117">USB 開機</span><span class="sxs-lookup"><span data-stu-id="e256c-117">USB Boot</span></span>
- <span data-ttu-id="e256c-118">UEFI 首頁</span><span class="sxs-lookup"><span data-stu-id="e256c-118">UEFI Front Page</span></span>

    - <span data-ttu-id="e256c-119">裝置</span><span class="sxs-lookup"><span data-stu-id="e256c-119">Devices</span></span>
    - <span data-ttu-id="e256c-120">開機</span><span class="sxs-lookup"><span data-stu-id="e256c-120">Boot</span></span>
    - <span data-ttu-id="e256c-121">日期/時間</span><span class="sxs-lookup"><span data-stu-id="e256c-121">Date/Time</span></span>

## <span data-ttu-id="e256c-122">建立 UEFI 配置圖像</span><span class="sxs-lookup"><span data-stu-id="e256c-122">Create UEFI configuration image</span></span>

<span data-ttu-id="e256c-123">與其他 Surface 裝置不同，您無法使用 MSI 檔案或 Win PE 映射，在 Surface Hub 2 秒上套用這些設定。</span><span class="sxs-lookup"><span data-stu-id="e256c-123">Unlike other Surface devices, you cannot use an MSI file or a Win PE image to apply these settings on Surface Hub 2S.</span></span> <span data-ttu-id="e256c-124">相反地，您需要建立要載入到裝置的 USB 影像。</span><span class="sxs-lookup"><span data-stu-id="e256c-124">Instead, you need to create a USB image to load into the device.</span></span> <span data-ttu-id="e256c-125">若要建立 Surface Hub 2 的 UEFI 設定影像，請從 Microsoft 下載中心的 [ [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面下載並安裝最新版本的 MICROSOFT Surface UEFI 設定檔。</span><span class="sxs-lookup"><span data-stu-id="e256c-125">To create a Surface Hub 2S UEFI configuration image, download and install the latest version of the Microsoft Surface UEFI Configurator from the [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) page in the Microsoft Download Center.</span></span> <span data-ttu-id="e256c-126">如需有關使用 UEFI 與 SEMM 的詳細資訊，請參閱[Microsoft Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="e256c-126">For more information about using UEFI and SEMM, see [Microsoft Surface Enterprise Management Mode](https://docs.microsoft.com/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="e256c-127">在 Surface Hub 2 秒上設定 UEFI</span><span class="sxs-lookup"><span data-stu-id="e256c-127">To configure UEFI on Surface Hub 2S</span></span>

1. <span data-ttu-id="e256c-128">啟動 UEFI 配置器，然後在第一個畫面上，選擇 [設定**套件**]。</span><span class="sxs-lookup"><span data-stu-id="e256c-128">Start the UEFI Configurator and on the first screen, choose **Configuration Package**.</span></span><br><br>
![\* 啟動 UEFI 配置器並選擇 [設定套件] \*](images/sh2-uefi1.png) <br> <br>
2. <span data-ttu-id="e256c-130">若要將憑證新增到您的套件，您必須有有效的憑證，且私密金鑰是 .pfx 檔案格式，才能簽署及保護套件。</span><span class="sxs-lookup"><span data-stu-id="e256c-130">To add the certificate to your package, you must have a valid certificate with the private key in a .pfx file format to sign and protect the package.</span></span> <span data-ttu-id="e256c-131">選取 [ **+ 憑證保護]。**</span><span class="sxs-lookup"><span data-stu-id="e256c-131">Select **+ Certificate Protection.**</span></span> <br>
![\* 選取 + 憑證保護 \*](images/sh2-uefi2.png) <br><br>
3. <span data-ttu-id="e256c-133">輸入證書的私密金鑰密碼。</span><span class="sxs-lookup"><span data-stu-id="e256c-133">Enter the certificate’s private key’s password.</span></span><br>
![\* 輸入證書的私人金鑰密碼 \*](images/sh2-uefi3.png) <br><br>
4. <span data-ttu-id="e256c-135">匯入私人金鑰之後，繼續建立套件。</span><span class="sxs-lookup"><span data-stu-id="e256c-135">After importing the private key, continue creating the package.</span></span><br>
![\* 繼續建立套件 \*](images/sh2-uefi4.png) <br><br>
5. <span data-ttu-id="e256c-137">選擇 [**中樞**] 和 [ **Surface hub** 2] 作為 UEFI 配置套件的目標。</span><span class="sxs-lookup"><span data-stu-id="e256c-137">Choose **Hub** and **Surface Hub 2S** as the target for the UEFI configuration package.</span></span><br>
![\* 選擇 [中樞] 和 [Surface Hub 2] 作為 UEFI 配置套件的目標 \*](images/sh2-uefi5.png) <br><br>
6. <span data-ttu-id="e256c-139">選擇您想要在 Surface Hub 2 秒啟動或停用的元件和設定。</span><span class="sxs-lookup"><span data-stu-id="e256c-139">Choose the components and settings you want to activate or deactivate on Surface Hub 2S.</span></span><br>
![\* 選擇您想要啟動或停用的元件和設定 \*](images/sh2-uefi6.png) <br><br>
7. <span data-ttu-id="e256c-141">使用 USB 選項匯出檔案。</span><span class="sxs-lookup"><span data-stu-id="e256c-141">Use the USB option to export the file.</span></span><br>
![\* 使用 USB 選項匯出檔案 \*](images/sh2-uefi8.png) <br><br>
8. <span data-ttu-id="e256c-143">插入並選擇您想要用於此套件的 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="e256c-143">Insert and choose the USB drive you’d like to use for this package.</span></span> <span data-ttu-id="e256c-144">USB 磁片磁碟機將會格式化，而且您會遺失任何您在其上的資訊。</span><span class="sxs-lookup"><span data-stu-id="e256c-144">The USB drive will be formatted and you lose any information you have on it.</span></span><br>
![\* 插入並選擇您套件的 USB 磁片磁碟機 \*](images/sh2-uefi9.png) <br><br>
9. <span data-ttu-id="e256c-146">成功建立套件後，配置器就會顯示憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="e256c-146">Upon successful creation of the package, the Configurator will display the last two characters of your certificate’s thumbprint.</span></span> <span data-ttu-id="e256c-147">當您匯入到 [Surface Hub 2] 的配置時，您需要這些字元。</span><span class="sxs-lookup"><span data-stu-id="e256c-147">You need these characters when you import to the configuration to Surface Hub 2S.</span></span><br>
![\* 套件的成功設定 \*](images/sh2-uefi10.png) <br>

## <span data-ttu-id="e256c-149">若要引導至 UEFI</span><span class="sxs-lookup"><span data-stu-id="e256c-149">To boot into UEFI</span></span>

<span data-ttu-id="e256c-150">關閉 Surface Hub 秒。</span><span class="sxs-lookup"><span data-stu-id="e256c-150">Turn off Surface Hub 2S.</span></span> <span data-ttu-id="e256c-151">按住**音量**按鈕，然後按下 [**電源**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="e256c-151">Press and hold the **Volume Up** button and press the **Power** Button.</span></span> <span data-ttu-id="e256c-152">一直按住音量按鈕，直到 UEFI 功能表出現為止。</span><span class="sxs-lookup"><span data-stu-id="e256c-152">Keep holding the Volume Up button until the UEFI menu appears.</span></span>
