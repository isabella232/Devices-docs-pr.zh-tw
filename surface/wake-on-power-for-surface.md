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
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903003"
---
# <span data-ttu-id="3b3e4-104">在 Surface 裝置上喚醒電源</span><span class="sxs-lookup"><span data-stu-id="3b3e4-104">Wake on Power for Surface devices</span></span>

<span data-ttu-id="3b3e4-105">您可以在離開辦公桌時關閉 Surface 裝置，或將它設為睡眠模式，以節省電池。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-105">Surface devices can be powered off while away from the desk or set to hibernate mode to save battery.</span></span> <span data-ttu-id="3b3e4-106">若要改善這些裝置的可管理性，請先喚醒電源啟用相容的 Surface 裝置，以便在重新電源開啟時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-106">To improve the manageability of these devices, Wake on Power enables compatible Surface devices to automatically start when reconnected to power.</span></span> <span data-ttu-id="3b3e4-107">設定 [在 Power 喚醒] 需要使用 Surface Enterprise 管理模式（SEMM），不論是透過 Surface UEFI 配置或 UEFI 管理員。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-107">Configuring Wake on Power requires using Surface Enterprise Management Mode (SEMM) either through Surface UEFI Configurator or the UEFI Manager.</span></span>

<span data-ttu-id="3b3e4-108">[電源開啟] 是下列裝置上可用的功能：</span><span class="sxs-lookup"><span data-stu-id="3b3e4-108">Wake on Power is a feature available on the following devices:</span></span>

- <span data-ttu-id="3b3e4-109">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="3b3e4-109">Surface Book 3</span></span>
- <span data-ttu-id="3b3e4-110">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="3b3e4-110">Surface Pro 7</span></span>
- <span data-ttu-id="3b3e4-111">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="3b3e4-111">Surface Laptop 3</span></span>
- <span data-ttu-id="3b3e4-112">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="3b3e4-112">Surface Pro X</span></span> 

## <span data-ttu-id="3b3e4-113">概述與先決條件</span><span class="sxs-lookup"><span data-stu-id="3b3e4-113">Overview and prerequisites</span></span>

<span data-ttu-id="3b3e4-114">您可以使用 Surface UEFI 配置單元來設定個別的 UEFI 設定，這些設定是儲存在 Windows 安裝程式的 .msi 套件中，以發佈至目標裝置。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-114">You can use the Surface UEFI Configurator to configure individual UEFI settings that are saved in a Windows Installer .msi package for distribution to target devices.</span></span> 

> [!NOTE]
> <span data-ttu-id="3b3e4-115">本文假設您熟悉如何使用 SEMM。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-115">This article assumes that you are familiar with using SEMM.</span></span> <span data-ttu-id="3b3e4-116">如需詳細資訊，請參閱[Surface Enterprise 管理模式（SEMM）](surface-enterprise-management-mode.md)檔。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-116">For more information, see [Surface Enterprise Management Mode (SEMM)](surface-enterprise-management-mode.md) documentation.</span></span>

## <span data-ttu-id="3b3e4-117">啟用喚醒功能</span><span class="sxs-lookup"><span data-stu-id="3b3e4-117">To enable Wake on Power</span></span>

1.  <span data-ttu-id="3b3e4-118">下載最新版本的[SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-118">Download the latest version of [Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703).</span></span>
2.  <span data-ttu-id="3b3e4-119">以系統管理員身分登入您的 Surface 裝置，然後開啟**SURFACE UEFI 配置**器，選取 [ **surface 裝置**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-119">Sign into your Surface device as an Administrator, open **Surface UEFI Configurator**, select **Surface Devices**, and then select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
3.  <span data-ttu-id="3b3e4-121">選取 [**開始**]，然後在 [設定**套件**] 底下選取 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-121">Select **Start** and then under **Configuration Package** select **Create**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="選取 [建立配置套件]。":::
4.  <span data-ttu-id="3b3e4-123">選取 [**憑證保護**]，然後新增您的憑證 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-123">Select **Certificate Protection** and add your certificate .pfx file.</span></span> <span data-ttu-id="3b3e4-124">輸入密碼之後，請選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-124">After entering your password, select **Next**.</span></span> <span data-ttu-id="3b3e4-125">視需要新增**密碼保護**，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-125">Add **Password Protection**, as appropriate, and then select **Next**.</span></span>
5.  <span data-ttu-id="3b3e4-126">在 [**選擇您要設定目標的表面類型**] 頁面上，視需要選取您的目標裝置。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-126">On the **Choose which Surface type you want to target** page, select your target devices as appropriate.</span></span> <span data-ttu-id="3b3e4-127">例如， **Surface Pro 7**。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-127">For example, **Surface Pro 7**.</span></span>
6.  <span data-ttu-id="3b3e4-128">在 [**高級功能**] 頁面上，選取 [**電源喚醒**]，並設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-128">On the **Advanced Features** page, select **Wake on Power** and set to **On**.</span></span> <span data-ttu-id="3b3e4-129">選取 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-129">Select **Next**.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="選取 [電源開啟後喚醒] 並設定為 [開啟]。"::: 
7.  <span data-ttu-id="3b3e4-131">在 [**成功**] 頁面上，選取 [**結束**]。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-131">On the **Successful** page, select **End**.</span></span> <span data-ttu-id="3b3e4-132">如果這是您第一次為裝置提供設定，系統會提示您提供憑證指紋的最後兩個字元。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-132">If this is your first time providing settings to your device, you will be prompted to provide the last two characters of the certificate thumbprint.</span></span> 
8.  <span data-ttu-id="3b3e4-133">儲存 .msi 套件。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-133">Save the .msi package.</span></span> 

## <span data-ttu-id="3b3e4-134">套用 MSI 套件</span><span class="sxs-lookup"><span data-stu-id="3b3e4-134">Apply the MSI package</span></span> 

<span data-ttu-id="3b3e4-135">您可以使用軟體發佈工具（例如 Microsoft 端點設定管理員），將 MSI 套件套用到您網路上的裝置。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-135">You can apply the MSI package to devices across your network using software distribution tools such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="3b3e4-136">此套裝程式含在本機電腦上安裝套件的步驟。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-136">This procedure includes steps for installing the package on your local machine.</span></span> 

1.  <span data-ttu-id="3b3e4-137">開啟提升許可權的命令提示字元，然後輸入 .msi 檔案的完整路徑，以執行 .msi 封裝。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-137">Open an elevated command prompt and enter the full path of the .msi file to run the .msi package.</span></span> 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  <span data-ttu-id="3b3e4-138">在 [**警告**] 對話方塊中，選取 **[確定] 或 [** 視需要停用 Bitlocker]。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-138">On the **Warning** dialog box, select **OK** or disable Bitlocker as appropriate.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="視需要選取 [確定] 或 [停用 Bitlocker]。":::
3.  <span data-ttu-id="3b3e4-140">在 [歡迎] 頁面上，選取 **[下一步]** 以執行套件，並套用新設定的 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-140">On the Welcome page, select **Next** to run the package and apply the newly configured UEFI setting.</span></span>

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="在 [歡迎] 頁面中，選取 [下一步]。":::
4.  <span data-ttu-id="3b3e4-142">重新開機您的裝置。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-142">Restart your device.</span></span> 

<span data-ttu-id="3b3e4-143">[電源開啟] 現已設定。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-143">Wake on Power is now configured.</span></span> <span data-ttu-id="3b3e4-144">若要測試設定，請關閉您的裝置，中斷電源連接，然後重新連接電源。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-144">To test the setting, turn off your device, disconnect the power, and then reconnect the power.</span></span> <span data-ttu-id="3b3e4-145">裝置將會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-145">The device will start automatically.</span></span> 

## <span data-ttu-id="3b3e4-146">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="3b3e4-146">More information</span></span>

<span data-ttu-id="3b3e4-147">如需詳細資訊，請參閱下列文章。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-147">For more information, see the following articles.</span></span> 

- [<span data-ttu-id="3b3e4-148">Surface 企業管理模式</span><span class="sxs-lookup"><span data-stu-id="3b3e4-148">Surface Enterprise Management Mode</span></span>](surface-enterprise-management-mode.md)
- [<span data-ttu-id="3b3e4-149">在 Surface 裝置上喚醒局域網</span><span class="sxs-lookup"><span data-stu-id="3b3e4-149">Wake on LAN for Surface devices</span></span>](wake-on-lan-for-surface-devices.md)

<span data-ttu-id="3b3e4-150">仍需要協助？</span><span class="sxs-lookup"><span data-stu-id="3b3e4-150">Still need help?</span></span> <span data-ttu-id="3b3e4-151">移至[Microsoft 社區](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="3b3e4-151">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>