---
title: 在 Surface Hub 2S 上更新手寫筆韌體
description: 此頁面說明如何更新 2 支Surface Hub的固件。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 6f1ca4f05653ec798ed1b47d2e42e974e7f7414d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576953"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a><span data-ttu-id="fd3cb-104">在 Surface Hub 2S 上更新手寫筆韌體</span><span class="sxs-lookup"><span data-stu-id="fd3cb-104">Update pen firmware on Surface Hub 2S</span></span>

<span data-ttu-id="fd3cb-105">您可以在 2 支Surface Hub上更新Windows商務用更新，或將固件更新下載到另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-105">You can update firmware on Surface Hub 2 pen from Windows Update for Business or by downloading the firmware update to a separate PC.</span></span> <span data-ttu-id="fd3cb-106">從 2020 年 2 月 26 Windows開始更新的固件。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-106">Updated firmware is available from Windows Update beginning February 26, 2020.</span></span> 

## <a name="update-pen-firmware-using-windows-update-for-business"></a><span data-ttu-id="fd3cb-107">使用商務用Windows更新更新筆式固件</span><span class="sxs-lookup"><span data-stu-id="fd3cb-107">Update pen firmware using Windows Update for Business</span></span>

<span data-ttu-id="fd3cb-108">本節說明如何透過自動維護週期更新筆Windows更新，根據預設，這項作業預設為在上午 3 點進行。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-108">This section describes how to update pen firmware via the automated maintenance cycles for Windows Update, configured by default to occur nightly at 3 a.m.</span></span> <span data-ttu-id="fd3cb-109">您必須規劃兩個維護週期才能完成，才能將更新套用至 2 支Surface Hub筆。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-109">You will need to plan for two maintenance cycles to complete before applying the update to the Surface Hub 2 pen.</span></span> <span data-ttu-id="fd3cb-110">或者，就像任何其他更新一樣，您也可以使用商務Windows更新 (WUfB) 來使用筆式固件。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-110">Alternately, like any other update, you can use Windows Update for Business (WUfB) to apply the pen firmware.</span></span> <span data-ttu-id="fd3cb-111">詳細資訊，請參閱管理[Windows 上的Surface Hub。](manage-windows-updates-for-surface-hub.md)</span><span class="sxs-lookup"><span data-stu-id="fd3cb-111">For more information, see [Managing Windows updates on Surface Hub](manage-windows-updates-for-surface-hub.md).</span></span>

1. <span data-ttu-id="fd3cb-112">請Surface Hub 2 支筆配對Surface Hub 2S：按住頂端按鈕，直到白色指示器 LED\*\*\*\* 指示燈開始閃爍。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-112">Ensure the Surface Hub 2 pen is paired to Surface Hub 2S: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 支筆](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="fd3cb-114">在 Surface Hub登入為系統管理員，開啟 設定 **，然後**掃描藍牙裝置。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-114">On Surface Hub, login as an Admin, open **Settings**, and then scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="fd3cb-115">選取觸控筆以完成配對程式。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-115">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="fd3cb-116">按 **觸控筆** 上的頂端按鈕以適用更新。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-116">Press the **top** button on the pen to apply the update.</span></span> <span data-ttu-id="fd3cb-117">最多可能需要兩小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-117">It may take up to two hours to complete.</span></span>

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a><span data-ttu-id="fd3cb-118">下載至個別電腦以更新觸控筆的固件</span><span class="sxs-lookup"><span data-stu-id="fd3cb-118">Update pen firmware by downloading to separate PC</span></span>

<span data-ttu-id="fd3cb-119">您可以從執行 Surface Hub 的個別電腦更新 2 支Windows 10。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-119">You can update the firmware on Surface Hub 2 pen from a separate PC running Windows 10.</span></span> <span data-ttu-id="fd3cb-120">這個方法也可讓您確認筆式固件已成功更新至最新版本。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-120">This method also enables you to verify that the pen firmware has successfully updated to the latest version.</span></span>

1. <span data-ttu-id="fd3cb-121">將 Surface Hub 2 支筆配對至藍牙型電腦：按住頂端按鈕，直到白色指示燈\*\*\*\* LED 指示燈開始閃爍。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-121">Pair the Surface Hub 2 pen to your Bluetooth-capable PC: Press and hold the **top** button until the white indicator LED light begins to blink.</span></span> <br>
![Surface Hub 2 支筆](images/sh2-pen-1.png) <br>
2. <span data-ttu-id="fd3cb-123">在 PC 上，掃描新藍牙裝置。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-123">On the PC, scan for new Bluetooth devices.</span></span>
3. <span data-ttu-id="fd3cb-124">選取觸控筆以完成配對程式。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-124">Select the pen to complete the pairing process.</span></span>
4. <span data-ttu-id="fd3cb-125">在開始新Surface Hub之前，先中斷所有其他 2s 筆的中斷連接。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-125">Disconnect all other Surface Hub 2s pens before starting a new update.</span></span>
3. <span data-ttu-id="fd3cb-126">將 Surface Hub [2 筆固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下載到您的電腦。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-126">Download the [Surface Hub 2 Pen Firmware Update Tool](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip) to your PC.</span></span>
4. <span data-ttu-id="fd3cb-127">執行 **PenCfu.exe。**</span><span class="sxs-lookup"><span data-stu-id="fd3cb-127">Run **PenCfu.exe.**</span></span> <span data-ttu-id="fd3cb-128">安裝進度會顯示在工具中。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-128">The install progress is displayed in the tool.</span></span> <span data-ttu-id="fd3cb-129">可能需要幾分鐘才能完成更新。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-129">It may take several minutes to finish updating.</span></span> 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a><span data-ttu-id="fd3cb-130">檢查 2 支Surface Hub的固件版本</span><span class="sxs-lookup"><span data-stu-id="fd3cb-130">Check firmware version of Surface Hub 2 pen</span></span>

1. <span data-ttu-id="fd3cb-131">執行 \*\*get_version.bat， \*\* 然後按 **觸控筆** 上的頂端按鈕。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-131">Run **get_version.bat** and press the **top** button on the pen.</span></span>
2. <span data-ttu-id="fd3cb-132">此工具會報告觸控筆的固件版本。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-132">The tool will report the firmware version of the pen.</span></span> <span data-ttu-id="fd3cb-133">範例：</span><span class="sxs-lookup"><span data-stu-id="fd3cb-133">Example:</span></span>
    - <span data-ttu-id="fd3cb-134">舊固件為 468.2727.368</span><span class="sxs-lookup"><span data-stu-id="fd3cb-134">Old firmware is 468.2727.368</span></span>
    - <span data-ttu-id="fd3cb-135">新的固件為 468.3347.368</span><span class="sxs-lookup"><span data-stu-id="fd3cb-135">New firmware is 468.3347.368</span></span>

## <a name="command-line-options"></a><span data-ttu-id="fd3cb-136">命令列選項</span><span class="sxs-lookup"><span data-stu-id="fd3cb-136">Command line options</span></span>

<span data-ttu-id="fd3cb-137">您可以在命令列Surface Hub 2 筆 (PenCfu.exe) 更新工具。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-137">You can run Surface Hub 2 Pen Firmware Update Tool (PenCfu.exe) from the command line.</span></span>

1. <span data-ttu-id="fd3cb-138">將筆與電腦配對，然後按一下 **筆** 上的頂端按鈕。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-138">Pair the pen to your PC and click the **top** button on the pen.</span></span>
2. <span data-ttu-id="fd3cb-139">按兩下 \*\* [PenCfu.exe\*\* 以啟動固件更新。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-139">Double click **PenCfu.exe** to initiate the firmware update.</span></span> <span data-ttu-id="fd3cb-140">請注意，設定檔和固件圖像檔案必須儲存在與工具相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-140">Note that the configuration file and the firmware image files must be stored in the same folder as the tool.</span></span>
3. <span data-ttu-id="fd3cb-141">針對其他選項，請執行 **PenCfu.exe -h** 以顯示可用的參數，如下表所列。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-141">For additional options, run **PenCfu.exe -h** to display the available parameters, as listed in the following table.</span></span>  
    - <span data-ttu-id="fd3cb-142">範例：PenCfu.exe -h</span><span class="sxs-lookup"><span data-stu-id="fd3cb-142">Example: PenCfu.exe -h</span></span>
4. <span data-ttu-id="fd3cb-143">輸入 **Ctrl+C** 以安全地關閉工具。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-143">Enter **Ctrl+C** to safely shut down the tool.</span></span>

 

| **<span data-ttu-id="fd3cb-144">命令</span><span class="sxs-lookup"><span data-stu-id="fd3cb-144">Command</span></span>**    | **<span data-ttu-id="fd3cb-145">說明</span><span class="sxs-lookup"><span data-stu-id="fd3cb-145">Description</span></span>**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="fd3cb-146">-h 説明</span><span class="sxs-lookup"><span data-stu-id="fd3cb-146">-h help</span></span>        | <span data-ttu-id="fd3cb-147">顯示工具命令列介面説明並離開。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-147">Display tool command line interface help and exit.</span></span>                                                                                                                                                                                                                                                                                                                                             |
| <span data-ttu-id="fd3cb-148">-v 版本</span><span class="sxs-lookup"><span data-stu-id="fd3cb-148">-v version</span></span>     | <span data-ttu-id="fd3cb-149">顯示工具版本並離開。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-149">Display tool version and exit.</span></span>                                                                                                                                                                                                                                                                                                                                                                 |
| <span data-ttu-id="fd3cb-150">-l 記錄篩選</span><span class="sxs-lookup"><span data-stu-id="fd3cb-150">-l log-filter</span></span>  | <span data-ttu-id="fd3cb-151">設定記錄檔案的篩選層級。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-151">Set a filter level for the log file.</span></span> <span data-ttu-id="fd3cb-152">記錄訊息有 4 個可能層級：DEBUG (最低) 、INFO、WARNING 和 ERROR (最高) 。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-152">Log messages have 4 possible levels: DEBUG (lowest), INFO, WARNING and ERROR (highest).</span></span> <span data-ttu-id="fd3cb-153">設定記錄篩選層級會篩選記錄訊息至只有相同層級或較高層級的郵件。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-153">Setting a log filter level filters log messages to only message with the same level or higher.</span></span> <span data-ttu-id="fd3cb-154">例如，如果篩選等級設為警告，則只會記錄警告和錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-154">For example, if the filter level is set to WARNING, only WARNING and ERROR messages will be logged.</span></span> <span data-ttu-id="fd3cb-155">根據預設，此選項會設定為 OFF，這會停用記錄。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-155">By default, this option is set to OFF, which disables logging.</span></span> |
| <span data-ttu-id="fd3cb-156">-g get-version</span><span class="sxs-lookup"><span data-stu-id="fd3cb-156">-g get-version</span></span> | <span data-ttu-id="fd3cb-157">如果指定，工具只會取得與該工具儲存在同一個資料夾中的設定檔相符合的已連接觸控筆 FW 版本。</span><span class="sxs-lookup"><span data-stu-id="fd3cb-157">If specified, the tool will only get the FW version of the connected pen that matches the configuration file that is stored in the same folder as the tool.</span></span>                                                                                                                                                                                                                                    
