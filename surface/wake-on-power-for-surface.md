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
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
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
ms.openlocfilehash: dee2a2962cf6b70a1bf11cf597b4d41f4b5568e4
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114571"
---
# <span data-ttu-id="36ae2-104">適用於 Surface 裝置的電源喚醒</span><span class="sxs-lookup"><span data-stu-id="36ae2-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="36ae2-105">當您不在辦公室時，可以關閉 Surface 裝置，或設定為睡眠模式，以節省電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="36ae2-105">Surface devices can be powered off while you're away from your desk, or set to hibernate mode to save battery life.</span></span> <span data-ttu-id="36ae2-106">若要改善這些裝置的可管理性，當電源電源開啟時，可讓相容的 Surface 裝置自動啟動。</span><span class="sxs-lookup"><span data-stu-id="36ae2-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when they're reconnected to power.</span></span> <span data-ttu-id="36ae2-107">若要設定喚醒功能，您可以使用 Surface Enterprise 管理模式 (SEMM) 透過 Surface UEFI 配置器或 UEFI 管理員來進行。</span><span class="sxs-lookup"><span data-stu-id="36ae2-107">To configure Wake on Power, you can use Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="36ae2-108">在下列裝置上可使用 [喚醒電源] 功能：</span><span class="sxs-lookup"><span data-stu-id="36ae2-108">The Wake on Power feature is available on the following devices:</span></span>

- <span data-ttu-id="36ae2-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="36ae2-109">Surface Book 3</span></span>
- <span data-ttu-id="36ae2-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="36ae2-110">Surface Pro 7</span></span>
- <span data-ttu-id="36ae2-111">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="36ae2-111">Surface Laptop 3</span></span>
- <span data-ttu-id="36ae2-112">Surface 膝上型電腦前往</span><span class="sxs-lookup"><span data-stu-id="36ae2-112">Surface Laptop Go</span></span>
- <span data-ttu-id="36ae2-113">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="36ae2-113">Surface Pro X</span></span> 


## <span data-ttu-id="36ae2-114">概述與先決條件</span><span class="sxs-lookup"><span data-stu-id="36ae2-114">Overview and prerequisites</span></span>

<span data-ttu-id="36ae2-115">Surface UEFI 設定檔可讓您將個別的 UEFI 設定儲存在 Windows 安裝程式的 .msi 套件中，以發佈至目標裝置。</span><span class="sxs-lookup"><span data-stu-id="36ae2-115">Surface UEFI Configurator lets you save individual UEFI settings in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="36ae2-116">本文假設您知道如何使用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="36ae2-116">This article assumes that you know how to use SEMM.</span></span> <span data-ttu-id="36ae2-117">如需詳細資訊，請參閱 [ (SEMM) 檔的 Surface Enterprise 管理模式 ](surface-enterprise-management-mode.md) 。</span><span class="sxs-lookup"><span data-stu-id="36ae2-117">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="36ae2-118">啟用喚醒功能</span><span class="sxs-lookup"><span data-stu-id="36ae2-118">To enable Wake on Power</span></span>

1.  <span data-ttu-id="36ae2-119">下載最新版本的 [SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。</span><span class="sxs-lookup"><span data-stu-id="36ae2-119">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="36ae2-120">以系統管理員身分登入您的 Surface 裝置，然後開啟 [ **SURFACE UEFI 配置**單元]，選取 [ **surface 裝置**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="36ae2-120">Sign in to your Surface device as an administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
3.  <span data-ttu-id="36ae2-122">選取 [**開始**]，然後選取 [設定**套件**] 下的 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="36ae2-122">Select **Start**, and then select **Create** under **Configuration Package**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
4.  <span data-ttu-id="36ae2-124">選取 [ **憑證保護**]，然後新增您的憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="36ae2-124">Select **Certificate Protection**, and add your certificate .pfx file.</span></span> 
5. <span data-ttu-id="36ae2-125">輸入您的密碼，選取 **[下一步]**，視需要新增 **密碼保護**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="36ae2-125">Enter your password, select **Next**, add **Password Protection**, as appropriate, and then select **Next**.</span></span>
6.  <span data-ttu-id="36ae2-126">在 [ **選擇您要設定目標的表面類型** ] 頁面上，視需要選取您的目標裝置。</span><span class="sxs-lookup"><span data-stu-id="36ae2-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="36ae2-127">例如，選取 [ **Surface Pro 7**]。</span><span class="sxs-lookup"><span data-stu-id="36ae2-127">For example, select **Surface Pro 7**.</span></span>
7.  <span data-ttu-id="36ae2-128">在 [ **高級功能** ] 頁面上，選取 [ **電源喚醒**]，將功能設定為 [ **開啟**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="36ae2-128">On the **Advanced Features** page, select **Wake on Power**, set the feature to **On**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。"::: 
8.  <span data-ttu-id="36ae2-130">在 [ **成功** ] 頁面上，選取 [ **結束**]。</span><span class="sxs-lookup"><span data-stu-id="36ae2-130">On the **Successful** page, select **End**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="36ae2-131">如果這是您第一次將設定提供給您的裝置，系統會提示您同時提供憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="36ae2-131">If this is the first time that you are providing settings to your device, you will be prompted to also provide the last two characters of the certificate thumbprint.</span></span> 
9.  <span data-ttu-id="36ae2-132">儲存 .msi 套件。</span><span class="sxs-lookup"><span data-stu-id="36ae2-132">Save the .msi package.</span></span> 

## <span data-ttu-id="36ae2-133">套用 MSI 套件</span><span class="sxs-lookup"><span data-stu-id="36ae2-133">Apply the MSI package</span></span> 

<span data-ttu-id="36ae2-134">您可以使用軟體發佈工具（例如 Microsoft 端點設定管理員），將 MSI 套件套用到整個網路的裝置。</span><span class="sxs-lookup"><span data-stu-id="36ae2-134">You can apply the MSI package to devices across your network by using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="36ae2-135">此套裝程式含在您的本機電腦上安裝套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="36ae2-135">This procedure includes steps to install the package on your local computer.</span></span> 

1.  <span data-ttu-id="36ae2-136">在提升許可權的命令提示字元中，輸入 .msi 檔案的完整路徑，以執行 .msi 封裝。</span><span class="sxs-lookup"><span data-stu-id="36ae2-136">At an elevated command prompt, enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="36ae2-137">在 [ **警告** ] 對話方塊中，視需要選取 **[確定] 或 [** 停用 BitLocker]。</span><span class="sxs-lookup"><span data-stu-id="36ae2-137">In the **Warning** dialog box, select **OK** or disable BitLocker, as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
3.  <span data-ttu-id="36ae2-139">在 [歡迎] 頁面上，選取 **[下一步]** 以執行套件，並套用新設定的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="36ae2-139">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
4.  <span data-ttu-id="36ae2-141">重新開機您的裝置。</span><span class="sxs-lookup"><span data-stu-id="36ae2-141">Restart your device.</span></span> 

<span data-ttu-id="36ae2-142">[電源開啟] 現已設定。</span><span class="sxs-lookup"><span data-stu-id="36ae2-142">Wake on Power is now configured.</span></span> <span data-ttu-id="36ae2-143">若要測試設定，請關閉您的裝置，中斷電源連接，然後重新連接電源。</span><span class="sxs-lookup"><span data-stu-id="36ae2-143">To test the settings, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="36ae2-144">裝置應該會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="36ae2-144">The device should start automatically.</span></span> 

## <span data-ttu-id="36ae2-145">參考</span><span class="sxs-lookup"><span data-stu-id="36ae2-145">References</span></span>

<span data-ttu-id="36ae2-146">如需詳細資訊，請參閱下列文章。</span><span class="sxs-lookup"><span data-stu-id="36ae2-146">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="36ae2-147">Surface 企業管理模式</span><span class="sxs-lookup"><span data-stu-id="36ae2-147">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="36ae2-148">在 Surface 裝置上喚醒局域網</span><span class="sxs-lookup"><span data-stu-id="36ae2-148">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="36ae2-149">仍需要協助？</span><span class="sxs-lookup"><span data-stu-id="36ae2-149">Still need help?</span></span> <span data-ttu-id="36ae2-150">移至 [Microsoft 社區](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="36ae2-150">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>