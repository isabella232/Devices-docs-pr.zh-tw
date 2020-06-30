---
title: 更新 Surface Hub 秒的畫筆固件
description: 此頁面說明如何更新 Surface Hub 2 筆的固件。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831470"
---
# <span data-ttu-id="db2d8-104">更新 Surface Hub 秒的畫筆固件</span><span class="sxs-lookup"><span data-stu-id="db2d8-104">Update pen firmware on Surface Hub 2S</span></span>

<span data-ttu-id="db2d8-105">您可以從商務用 Windows Update，或透過將固件更新下載到個別的電腦，在 Surface Hub 2 筆上更新固件。</span><span class="sxs-lookup"><span data-stu-id="db2d8-105">You can update firmware on Surface Hub 2 pen from Windows Update for Business or by downloading the firmware update to a separate PC.</span></span> <span data-ttu-id="db2d8-106">您可以從2020年2月26日開始的 Windows 更新取得更新的固件。</span><span class="sxs-lookup"><span data-stu-id="db2d8-106">Updated firmware is available from Windows Update beginning February 26, 2020.</span></span> 

## <span data-ttu-id="db2d8-107">使用 Windows 版企業更新更新手寫筆固件</span><span class="sxs-lookup"><span data-stu-id="db2d8-107">Update pen firmware using Windows Update for Business</span></span>

<span data-ttu-id="db2d8-108">本節說明如何透過 Windows Update 的自動維護週期來更新手寫筆固件（預設為在夜間 3 a.m. 進行）設定。</span><span class="sxs-lookup"><span data-stu-id="db2d8-108">This section describes how to update pen firmware via the automated maintenance cycles for Windows Update, configured by default to occur nightly at 3 a.m.</span></span> <span data-ttu-id="db2d8-109">在將更新套用至 Surface Hub 2 筆前，您必須規劃兩個維護週期才能完成。</span><span class="sxs-lookup"><span data-stu-id="db2d8-109">You will need to plan for two maintenance cycles to complete before applying the update to the Surface Hub 2 pen.</span></span> <span data-ttu-id="db2d8-110">或者，您可以使用 Windows Server Update Services （WSUS）來套用手寫筆固件，就像任何其他更新一樣。</span><span class="sxs-lookup"><span data-stu-id="db2d8-110">Alternately, like any other update, you can use Windows Server Update Services (WSUS) to apply the pen firmware.</span></span> <span data-ttu-id="db2d8-111">如需詳細資訊，請參閱[管理 Surface Hub 上的 Windows 更新](manage-windows-updates-for-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="db2d8-111">For more information, see [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).</span></span>

1. <span data-ttu-id="db2d8-112">確定 Surface Hub 2 筆已配對至 Surface Hub 2：按住**上方**按鈕，直到白色的指示燈開始閃爍為止。</span><span class="sxs-lookup"><span data-stu-id="db2d8-112">Ensure the Surface Hub 2 pen is paired to Surface Hub 2S: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 筆](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="db2d8-114">在 Surface Hub 上，以系統管理員身分登入，然後開啟 [**設定**]，然後掃描新的藍牙裝置。</span><span class="sxs-lookup"><span data-stu-id="db2d8-114">On Surface Hub, login as an Admin, open **Settings**, and then scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="db2d8-115">選取手寫筆以完成配對程式。</span><span class="sxs-lookup"><span data-stu-id="db2d8-115">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="db2d8-116">按手寫筆上的**上方**按鈕來套用更新。</span><span class="sxs-lookup"><span data-stu-id="db2d8-116">Press the **top** button on the pen to apply the update.</span></span> <span data-ttu-id="db2d8-117">可能需要長達兩個小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="db2d8-117">It may take up to two hours to complete.</span></span>

## <span data-ttu-id="db2d8-118">透過下載到個別電腦來更新手寫筆固件</span><span class="sxs-lookup"><span data-stu-id="db2d8-118">Update pen firmware by downloading to separate PC</span></span>

<span data-ttu-id="db2d8-119">您可以從執行 Windows 10 的另一部電腦，在 Surface Hub 2 筆上更新固件。</span><span class="sxs-lookup"><span data-stu-id="db2d8-119">You can update the firmware on Surface Hub 2 pen from a separate PC running Windows 10.</span></span> <span data-ttu-id="db2d8-120">這個方法也可讓您確認畫筆固件已成功更新為最新版本。</span><span class="sxs-lookup"><span data-stu-id="db2d8-120">This method also enables you to verify that the pen firmware has successfully updated to the latest version.</span></span>

1. <span data-ttu-id="db2d8-121">將 Surface Hub 2 筆與支援藍牙功能的電腦配對：按住**上方**按鈕，直到白色的指示燈開始閃爍為止。</span><span class="sxs-lookup"><span data-stu-id="db2d8-121">Pair the Surface Hub 2 pen to your Bluetooth-capable PC: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 筆](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="db2d8-123">在電腦上，掃描新的藍牙裝置。</span><span class="sxs-lookup"><span data-stu-id="db2d8-123">On the PC, scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="db2d8-124">選取手寫筆以完成配對程式。</span><span class="sxs-lookup"><span data-stu-id="db2d8-124">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="db2d8-125">在開始新的更新之前，請中斷所有其他 Surface Hub 2 的筆。</span><span class="sxs-lookup"><span data-stu-id="db2d8-125">Disconnect all other Surface Hub 2s pens before starting a new update.</span></span>
3. <span data-ttu-id="db2d8-126">將[Surface Hub 2 手寫筆固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下載到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="db2d8-126">Download the [Surface Hub 2 Pen Firmware Update Tool](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) to your PC.</span></span>
4. <span data-ttu-id="db2d8-127">執行**PenCfu.exe。**</span><span class="sxs-lookup"><span data-stu-id="db2d8-127">Run **PenCfu.exe.**</span></span> <span data-ttu-id="db2d8-128">安裝進度會顯示在工具中。</span><span class="sxs-lookup"><span data-stu-id="db2d8-128">The install progress is displayed in the tool.</span></span> <span data-ttu-id="db2d8-129">完成更新可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="db2d8-129">It may take several minutes to finish updating.</span></span> 


## <span data-ttu-id="db2d8-130">檢查 Surface Hub 2 手寫筆的固件版本</span><span class="sxs-lookup"><span data-stu-id="db2d8-130">Check firmware version of Surface Hub 2 pen</span></span>

1. <span data-ttu-id="db2d8-131">執行**get_version.bat**然後按手寫筆上的**上方**按鈕。</span><span class="sxs-lookup"><span data-stu-id="db2d8-131">Run **get_version.bat** and press the **top** button on the pen.</span></span>
2. <span data-ttu-id="db2d8-132">此工具會報告手寫筆的固件版本。</span><span class="sxs-lookup"><span data-stu-id="db2d8-132">The tool will report the firmware version of the pen.</span></span> <span data-ttu-id="db2d8-133">範例：</span><span class="sxs-lookup"><span data-stu-id="db2d8-133">Example:</span></span>
    - <span data-ttu-id="db2d8-134">舊的固件為468.2727.368</span><span class="sxs-lookup"><span data-stu-id="db2d8-134">Old firmware is 468.2727.368</span></span>
    - <span data-ttu-id="db2d8-135">新的固件為468.2863.369</span><span class="sxs-lookup"><span data-stu-id="db2d8-135">New firmware is 468.2863.369</span></span>

## <span data-ttu-id="db2d8-136">命令列選項</span><span class="sxs-lookup"><span data-stu-id="db2d8-136">Command line options</span></span>

<span data-ttu-id="db2d8-137">您可以從命令列執行 Surface Hub 2 手寫筆固件更新工具（PenCfu.exe）。</span><span class="sxs-lookup"><span data-stu-id="db2d8-137">You can run Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) from the command line.</span></span>

1. <span data-ttu-id="db2d8-138">將筆與您的電腦配對，然後按一下手寫筆上的**上方**按鈕。</span><span class="sxs-lookup"><span data-stu-id="db2d8-138">Pair the pen to your PC and click the **top** button on the pen.</span></span>
2. <span data-ttu-id="db2d8-139">按兩下 [ **PenCfu.exe** ] 以啟動固件更新。</span><span class="sxs-lookup"><span data-stu-id="db2d8-139">Double click **PenCfu.exe** to initiate the firmware update.</span></span> <span data-ttu-id="db2d8-140">請注意，設定檔和固件映射檔必須與工具儲存在相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="db2d8-140">Note that the configuration file and the firmware image files must be stored in the same folder as the tool.</span></span>
3. <span data-ttu-id="db2d8-141">如需其他選項，請執行**PenCfu.exe h**以顯示可用的參數，如下表所列。</span><span class="sxs-lookup"><span data-stu-id="db2d8-141">For additional options, run **PenCfu.exe -h** to display the available parameters, as listed in the following table.</span></span>  
    - <span data-ttu-id="db2d8-142">範例： PenCfu.exe-h</span><span class="sxs-lookup"><span data-stu-id="db2d8-142">Example: PenCfu.exe -h</span></span>
4. <span data-ttu-id="db2d8-143">輸入**Ctrl + C**以安全地關閉工具。</span><span class="sxs-lookup"><span data-stu-id="db2d8-143">Enter **Ctrl+C** to safely shut down the tool.</span></span>

 

| **<span data-ttu-id="db2d8-144">命令</span><span class="sxs-lookup"><span data-stu-id="db2d8-144">Command</span></span>**    | **<span data-ttu-id="db2d8-145">描述</span><span class="sxs-lookup"><span data-stu-id="db2d8-145">Description</span></span>**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="db2d8-146">-h 說明</span><span class="sxs-lookup"><span data-stu-id="db2d8-146">-h help</span></span>        | <span data-ttu-id="db2d8-147">顯示工具命令列介面說明及結束。</span><span class="sxs-lookup"><span data-stu-id="db2d8-147">Display tool command line interface help and exit.</span></span>                                                                                                                                                                                                                                                                                                                                             |
| <span data-ttu-id="db2d8-148">-v 版本</span><span class="sxs-lookup"><span data-stu-id="db2d8-148">-v version</span></span>     | <span data-ttu-id="db2d8-149">[顯示工具版本] 和 [結束]。</span><span class="sxs-lookup"><span data-stu-id="db2d8-149">Display tool version and exit.</span></span>                                                                                                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="db2d8-150">-l 記錄-篩選</span><span class="sxs-lookup"><span data-stu-id="db2d8-150">-l log-filter</span></span>  | <span data-ttu-id="db2d8-151">設定記錄檔的篩選層級。</span><span class="sxs-lookup"><span data-stu-id="db2d8-151">Set a filter level for the log file.</span></span> <span data-ttu-id="db2d8-152">記錄訊息有4種可能的層次：調試（最低）、資訊、警告和錯誤（最高）。</span><span class="sxs-lookup"><span data-stu-id="db2d8-152">Log messages have 4 possible levels: DEBUG (lowest), INFO, WARNING and ERROR (highest).</span></span> <span data-ttu-id="db2d8-153">設定記錄篩選層級篩選只會將記錄記錄在相同層級或更新版本的訊息中。</span><span class="sxs-lookup"><span data-stu-id="db2d8-153">Setting a log filter level filters log messages to only message with the same level or higher.</span></span> <span data-ttu-id="db2d8-154">例如，如果篩選層級設定為 [警告]，則只會記錄警告和錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="db2d8-154">For example, if the filter level is set to WARNING, only WARNING and ERROR messages will be logged.</span></span> <span data-ttu-id="db2d8-155">根據預設，此選項會設定為 [關閉]，這會停用記錄。</span><span class="sxs-lookup"><span data-stu-id="db2d8-155">By default, this option is set to OFF, which disables logging.</span></span> |
| <span data-ttu-id="db2d8-156">-g 取得版本</span><span class="sxs-lookup"><span data-stu-id="db2d8-156">-g get-version</span></span> | <span data-ttu-id="db2d8-157">如果已指定，工具將只會取得與工具相同資料夾中所儲存之設定檔相符的已連接手寫筆固件版本。</span><span class="sxs-lookup"><span data-stu-id="db2d8-157">If specified, the tool will only get the FW version of the connected pen that matches the configuration file that is stored in the same folder as the tool.</span></span>                                                                                                                                                                                                                                    