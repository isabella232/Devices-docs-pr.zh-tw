---
title: 如何啟用表面電源喚醒
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: 說明如何啟用和停用適用于 Surface 裝置的喚醒功能。
keywords: 更新、部署、驅動程式、wol、局域網喚醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 272c19baedb295abac08e90012246e453b88f42f
ms.sourcegitcommit: 6fd7008992503db9ae1f56654aa80110348924d3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/03/2020
ms.locfileid: "10903392"
---
# <span data-ttu-id="e4b30-104">適用於 Surface 裝置的電源喚醒</span><span class="sxs-lookup"><span data-stu-id="e4b30-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="e4b30-105">當您不在辦公室時，可以關閉 Surface 裝置，或設定為睡眠模式，以節省電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="e4b30-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="e4b30-106">若要改善這些裝置的可管理性，當電源電源開啟時，可讓相容的 Surface 裝置自動啟動。</span><span class="sxs-lookup"><span data-stu-id="e4b30-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="e4b30-107">若要設定喚醒功能，您可以透過 Surface UEFI 配置器或 UEFI 管理員使用 Surface Enterprise 管理模式（SEMM）。</span><span class="sxs-lookup"><span data-stu-id="e4b30-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="e4b30-108">在下列裝置上可使用 [喚醒電源] 功能：</span><span class="sxs-lookup"><span data-stu-id="e4b30-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="e4b30-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="e4b30-109">Surface Book 3</span></span>
- <span data-ttu-id="e4b30-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="e4b30-110">Surface Pro 7</span></span>
- <span data-ttu-id="e4b30-111">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="e4b30-111">Surface Laptop 3</span></span>
- <span data-ttu-id="e4b30-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="e4b30-112">Surface Pro X</span></span> 

## <span data-ttu-id="e4b30-113">概述與先決條件</span><span class="sxs-lookup"><span data-stu-id="e4b30-113">Overview and prerequisites</span></span>

<span data-ttu-id="e4b30-114">Surface UEFI 設定檔可讓您將個別的 UEFI 設定儲存在 Windows 安裝程式的 .msi 套件中，以發佈至目標裝置。</span><span class="sxs-lookup"><span data-stu-id="e4b30-114">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="e4b30-115">本文假設您知道如何使用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="e4b30-115">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="e4b30-116">如需詳細資訊，請參閱[Surface Enterprise 管理模式（SEMM）](surface-enterprise-management-mode.md)檔。</span><span class="sxs-lookup"><span data-stu-id="e4b30-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="e4b30-117">啟用喚醒功能</span><span class="sxs-lookup"><span data-stu-id="e4b30-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="e4b30-118">下載最新版本的[SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。</span><span class="sxs-lookup"><span data-stu-id="e4b30-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="e4b30-119">以系統管理員身分登入您的 Surface 裝置，然後開啟 [ **SURFACE UEFI 配置**單元]，選取 [ **surface 裝置**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e4b30-119">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
3.  <span data-ttu-id="e4b30-121">選取 [**開始**]，然後選取 [設定**套件**] 下的 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="e4b30-121">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="選取 [建立配置套件]。":::
4.  <span data-ttu-id="e4b30-123">選取 [**憑證保護**]，然後新增您的憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="e4b30-123">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="e4b30-124">輸入您的密碼，選取 **[下一步]**，視需要新增**密碼保護**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e4b30-124">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="e4b30-125">在 [**選擇您要設定目標的表面類型**] 頁面上，視需要選取您的目標裝置。</span><span class="sxs-lookup"><span data-stu-id="e4b30-125">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="e4b30-126">例如，選取 [ **Surface Pro 7**]。</span><span class="sxs-lookup"><span data-stu-id="e4b30-126">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="e4b30-127">在 [**高級功能**] 頁面上，選取 [**電源喚醒**]，將功能設定為 [**開啟**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e4b30-127">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="選取 [電源開啟後喚醒] 並設定為 [開啟]。"::: 
8.  <span data-ttu-id="e4b30-129">在 [**成功**] 頁面上，選取 [**結束**]。</span><span class="sxs-lookup"><span data-stu-id="e4b30-129">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e4b30-130">如果這是您第一次將設定提供給您的裝置，系統會提示您同時提供憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="e4b30-130">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="e4b30-131">儲存 .msi 套件。</span><span class="sxs-lookup"><span data-stu-id="e4b30-131">Save the .msi package.</span></span> 

## <span data-ttu-id="e4b30-132">套用 MSI 套件</span><span class="sxs-lookup"><span data-stu-id="e4b30-132">Apply the MSI package</span></span> 

<span data-ttu-id="e4b30-133">您可以使用軟體發佈工具（例如 Microsoft 端點設定管理員），將 MSI 套件套用到整個網路的裝置。</span><span class="sxs-lookup"><span data-stu-id="e4b30-133">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="e4b30-134">此套裝程式含在您的本機電腦上安裝套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="e4b30-134">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="e4b30-135">在提升許可權的命令提示字元中，輸入 .msi 檔案的完整路徑，以執行 .msi 封裝。</span><span class="sxs-lookup"><span data-stu-id="e4b30-135">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="e4b30-136">在 [**警告**] 對話方塊中，視需要選取 **[確定] 或 [** 停用 BitLocker]。</span><span class="sxs-lookup"><span data-stu-id="e4b30-136">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="視需要選取 [確定] 或 [停用 BitLocker]。":::
3.  <span data-ttu-id="e4b30-138">在 [歡迎] 頁面上，選取 **[下一步]** 以執行套件，並套用新設定的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="e4b30-138">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="在 [歡迎] 頁面中，選取 [下一步]。":::
4.  <span data-ttu-id="e4b30-140">重新開機您的裝置。</span><span class="sxs-lookup"><span data-stu-id="e4b30-140">Restart your device.</span></span> 

<span data-ttu-id="e4b30-141">[電源開啟] 現已設定。</span><span class="sxs-lookup"><span data-stu-id="e4b30-141">Wake on Power is now configured.</span></span> <span data-ttu-id="e4b30-142">若要測試設定，請關閉您的裝置，中斷電源連接，然後重新連接電源。</span><span class="sxs-lookup"><span data-stu-id="e4b30-142">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="e4b30-143">裝置應該會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="e4b30-143">The device should start automatically.</span></span> 

## <span data-ttu-id="e4b30-144">參考</span><span class="sxs-lookup"><span data-stu-id="e4b30-144">References</span></span>

<span data-ttu-id="e4b30-145">如需詳細資訊，請參閱下列文章。</span><span class="sxs-lookup"><span data-stu-id="e4b30-145">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="e4b30-146">Surface 企業管理模式</span><span class="sxs-lookup"><span data-stu-id="e4b30-146">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="e4b30-147">在 Surface 裝置上喚醒局域網</span><span class="sxs-lookup"><span data-stu-id="e4b30-147">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="e4b30-148">仍需要協助？</span><span class="sxs-lookup"><span data-stu-id="e4b30-148">Still need help?</span></span> <span data-ttu-id="e4b30-149">移至[Microsoft 社區](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="e4b30-149">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>