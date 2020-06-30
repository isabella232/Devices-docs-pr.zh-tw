---
title: 使用命令執行商務用 Surface 診斷工具組
description: 如何在命令主控台中執行表面診斷工具箱
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831198"
---
# <span data-ttu-id="db4c7-103">使用命令執行商務用 Surface 診斷工具組</span><span class="sxs-lookup"><span data-stu-id="db4c7-103">Run Surface Diagnostic Toolkit for Business using commands</span></span>

<span data-ttu-id="db4c7-104">在命令提示字元上執行表面診斷工具箱（SDT）需要下載 STD app 主控台。</span><span class="sxs-lookup"><span data-stu-id="db4c7-104">Running the Surface Diagnostic Toolkit (SDT) at a command prompt requires downloading the STD app console.</span></span> <span data-ttu-id="db4c7-105">安裝完成後，您可以透過 Windows 命令主控台（cmd.exe）或使用 Windows PowerShell （包括 PowerShell 整合腳本環境（ISE））在命令提示字元執行 SDT，這會提供支援命令、複製/貼上及其他功能的自動完成。</span><span class="sxs-lookup"><span data-stu-id="db4c7-105">After it's installed, you can run SDT at a command prompt via the Windows command console (cmd.exe) or using Windows PowerShell, including PowerShell Integrated Scripting Environment (ISE), which provides support for autocompletion of commands, copy/paste, and other features.</span></span>  <span data-ttu-id="db4c7-106">如需在 SDT 中支援的 Surface 裝置清單，請參閱適用于[企業的部署表面診斷工具](surface-diagnostic-toolkit-business.md)組。</span><span class="sxs-lookup"><span data-stu-id="db4c7-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>

>[!NOTE]
><span data-ttu-id="db4c7-107">若要使用命令執行 SDT，您必須登入系統管理員帳戶，或登入的帳戶是您 Surface 裝置上的系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="db4c7-107">To run SDT using commands, you must be signed in to the Administrator account or signed in to an account that is a member of the Administrator group on your Surface device.</span></span>

## <span data-ttu-id="db4c7-108">執行 SDT 應用程式主控台</span><span class="sxs-lookup"><span data-stu-id="db4c7-108">Running SDT app console</span></span>

<span data-ttu-id="db4c7-109">從 [ [Surface Tools FOR IT 下載] 頁面](https://www.microsoft.com/download/details.aspx?id=46703)下載並安裝 SDT 應用程式主控台。</span><span class="sxs-lookup"><span data-stu-id="db4c7-109">Download and install SDT app console from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="db4c7-110">您可以使用 Windows 命令提示字元（cmd.exe）或 Windows PowerShell 來執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="db4c7-110">You can use the Windows command prompt (cmd.exe) or Windows PowerShell to:</span></span> 

- <span data-ttu-id="db4c7-111">收集所有記錄檔。</span><span class="sxs-lookup"><span data-stu-id="db4c7-111">Collect all log files.</span></span>
- <span data-ttu-id="db4c7-112">使用最佳做法分析程式來執行健康情況診斷。</span><span class="sxs-lookup"><span data-stu-id="db4c7-112">Run health diagnostics using Best Practice Analyzer.</span></span>
- <span data-ttu-id="db4c7-113">檢查更新缺少固件或驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="db4c7-113">Check update for missing firmware or driver updates.</span></span>

>[!NOTE]
><span data-ttu-id="db4c7-114">在這個版本中，SDT 應用程式主控台只支援單一命令。</span><span class="sxs-lookup"><span data-stu-id="db4c7-114">In this release, the SDT app console supports single commands only.</span></span> <span data-ttu-id="db4c7-115">執行多個命令列選項需要針對每個命令單獨執行主控台 exe。</span><span class="sxs-lookup"><span data-stu-id="db4c7-115">Running multiple command line options requires running the console exe separately for each command.</span></span> 

<span data-ttu-id="db4c7-116">根據預設，輸出檔案會儲存在與主控台 app 相同的位置。</span><span class="sxs-lookup"><span data-stu-id="db4c7-116">By default, output files are saved in the same location as the console app.</span></span> <span data-ttu-id="db4c7-117">請參閱下表以取得完整的命令清單。</span><span class="sxs-lookup"><span data-stu-id="db4c7-117">Refer to the following table for a complete list of commands.</span></span>

<span data-ttu-id="db4c7-118">命令</span><span class="sxs-lookup"><span data-stu-id="db4c7-118">Command</span></span> | <span data-ttu-id="db4c7-119">附註</span><span class="sxs-lookup"><span data-stu-id="db4c7-119">Notes</span></span>
--- | ---
<span data-ttu-id="db4c7-120">-DataCollector "輸出檔案"</span><span class="sxs-lookup"><span data-stu-id="db4c7-120">-DataCollector "output file"</span></span> | <span data-ttu-id="db4c7-121">將系統詳細資料收集到 zip 檔案中。</span><span class="sxs-lookup"><span data-stu-id="db4c7-121">Collects system details into a zip file.</span></span> <span data-ttu-id="db4c7-122">"輸出檔案" 是建立系統詳細資料 zip 檔案的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="db4c7-122">"output file" is the file path to create system details zip file.</span></span><br><br><span data-ttu-id="db4c7-123">**範例**：</span><span class="sxs-lookup"><span data-stu-id="db4c7-123">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
<span data-ttu-id="db4c7-124">-bpa "輸出檔案"</span><span class="sxs-lookup"><span data-stu-id="db4c7-124">-bpa "output file"</span></span> | <span data-ttu-id="db4c7-125">檢查裝置中的數個設定和健康指示。</span><span class="sxs-lookup"><span data-stu-id="db4c7-125">Checks several settings and health indicators in the device.</span></span> <span data-ttu-id="db4c7-126">"輸出檔案" 是建立 HTML 報表的檔路徑。</span><span class="sxs-lookup"><span data-stu-id="db4c7-126">“output file" is the file path to create the HTML report.</span></span><br><br><span data-ttu-id="db4c7-127">**範例**：</span><span class="sxs-lookup"><span data-stu-id="db4c7-127">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
<span data-ttu-id="db4c7-128">-windowsupdate</span><span class="sxs-lookup"><span data-stu-id="db4c7-128">-windowsupdate</span></span> | <span data-ttu-id="db4c7-129">針對缺少的固件和/或驅動程式更新，檢查 Windows 更新線上伺服器。</span><span class="sxs-lookup"><span data-stu-id="db4c7-129">Checks Windows Update online servers for missing firmware and/or driver updates.</span></span><br><br><span data-ttu-id="db4c7-130">**範例**：</span><span class="sxs-lookup"><span data-stu-id="db4c7-130">**Example**:</span></span><br><span data-ttu-id="db4c7-131">Microsoft.Surface.Diagnostics.App.Console.exe windowsupdate</span><span class="sxs-lookup"><span data-stu-id="db4c7-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span></span>
<span data-ttu-id="db4c7-132">-保修 "輸出檔案"</span><span class="sxs-lookup"><span data-stu-id="db4c7-132">-warranty "output file"</span></span> | <span data-ttu-id="db4c7-133">檢查裝置上的保修資訊（有效或無效）。</span><span class="sxs-lookup"><span data-stu-id="db4c7-133">Checks warranty information on the device (valid or invalid).</span></span> <span data-ttu-id="db4c7-134">選用的 "輸出檔案" 是建立 xml 檔案的檔路徑。</span><span class="sxs-lookup"><span data-stu-id="db4c7-134">The optional “output file” is the file path to create the xml file.</span></span> <br><br><span data-ttu-id="db4c7-135">**範例**：</span><span class="sxs-lookup"><span data-stu-id="db4c7-135">**Example**:</span></span> <br><span data-ttu-id="db4c7-136">Microsoft.Surface.Diagnostics.App.Console.exe –質保 "warranty.xml"</span><span class="sxs-lookup"><span data-stu-id="db4c7-136">Microsoft.Surface.Diagnostics.App.Console.exe –warranty “warranty.xml”</span></span>


>[!NOTE]
><span data-ttu-id="db4c7-137">若要在目標裝置上遠端執行 SDT 應用程式主控台，您可以使用諸如 Microsoft 端點設定管理員之類的建構管理工具。</span><span class="sxs-lookup"><span data-stu-id="db4c7-137">To run the SDT app console remotely on target devices, you can use a configuration management tool such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="db4c7-138">或者，您也可以建立包含主控台 app 和適當的主控台命令的 .zip 檔案，然後根據貴組織的軟體發佈程式進行部署。</span><span class="sxs-lookup"><span data-stu-id="db4c7-138">Alternatively, you can create a .zip file containing the console app and appropriate console commands and deploy per your organization’s software distribution processes.</span></span> 

## <span data-ttu-id="db4c7-139">運行最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="db4c7-139">Running Best Practice Analyzer</span></span> 

<span data-ttu-id="db4c7-140">您可以跨主要元件（例如 BitLocker、安全啟動和受信任的平臺模組（TPM））執行 BPA 測試，然後將結果輸出到可共用的檔案。</span><span class="sxs-lookup"><span data-stu-id="db4c7-140">You can run BPA tests across key components such as BitLocker, Secure Boot, and Trusted Platform Module (TPM) and then output the results to a shareable file.</span></span> <span data-ttu-id="db4c7-141">此工具會產生一系列的資料表，其中包含以色彩標示的標題和條件描述項，以及如何解決問題的指導方針。</span><span class="sxs-lookup"><span data-stu-id="db4c7-141">The tool generates a series of tables with color-coded headings and condition descriptors along with guidance about how to approach resolving the issue.</span></span> 

- <span data-ttu-id="db4c7-142">綠色表示該元件正在以最佳條件執行（最佳）。</span><span class="sxs-lookup"><span data-stu-id="db4c7-142">Green indicates the component is running in an optimal condition (optimal).</span></span>
- <span data-ttu-id="db4c7-143">橙色表示元件沒有在最佳條件中執行（不是最佳的）。</span><span class="sxs-lookup"><span data-stu-id="db4c7-143">Orange indicates the component is not running in an optimal condition (not optimal).</span></span>
- <span data-ttu-id="db4c7-144">紅色表示元件處於異常狀態。</span><span class="sxs-lookup"><span data-stu-id="db4c7-144">Red indicates the component is in an abnormal state.</span></span> 

### <span data-ttu-id="db4c7-145">範例 BPA 結果輸出</span><span class="sxs-lookup"><span data-stu-id="db4c7-145">Sample BPA results output</span></span>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-146">BitLocker</span><span class="sxs-lookup"><span data-stu-id="db4c7-146">BitLocker</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-147">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-147">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-148">檢查是否已在系統磁碟機上啟用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="db4c7-148">Checks if BitLocker is enabled on the system drive.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-149">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-149">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-150">保護開啟</span><span class="sxs-lookup"><span data-stu-id="db4c7-150">Protection On</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-151">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-151">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-152">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-152">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-153">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-153">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-154">強烈建議您啟用 BitLocker 來保護您的資料。</span><span class="sxs-lookup"><span data-stu-id="db4c7-154">It is highly recommended to enable BitLocker to protect your data.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-155">安全開機</span><span class="sxs-lookup"><span data-stu-id="db4c7-155">Secure Boot</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-156">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-156">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-157">檢查是否已啟用 [安全引導]。</span><span class="sxs-lookup"><span data-stu-id="db4c7-157">Checks if Secure Boot is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-158">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-158">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-159">True</span><span class="sxs-lookup"><span data-stu-id="db4c7-159">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-160">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-160">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-161">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-161">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-162">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-162">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-163">強烈建議啟用 [安全啟動] 來保護您的電腦。</span><span class="sxs-lookup"><span data-stu-id="db4c7-163">It is highly recommended to enable Secure Boot to protect your PC.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-164">信賴平台模組</span><span class="sxs-lookup"><span data-stu-id="db4c7-164">Trusted Platform Module</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-165">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-165">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-166">確保 TPM 正常運作。</span><span class="sxs-lookup"><span data-stu-id="db4c7-166">Ensures that the TPM is functional.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-167">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-167">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-168">True</span><span class="sxs-lookup"><span data-stu-id="db4c7-168">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-169">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-169">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-170">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-170">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-171">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-171">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-172">如果沒有正常運作的 TPM，安全的功能（例如 BitLocker）可能無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="db4c7-172">Without a functional TPM, security-based functions such as BitLocker may not work properly.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-173">連線待機</span><span class="sxs-lookup"><span data-stu-id="db4c7-173">Connected Standby</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-174">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-174">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-175">檢查是否已啟用 [連線待機] 功能。</span><span class="sxs-lookup"><span data-stu-id="db4c7-175">Checks if Connected Standby is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-176">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-176">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-177">True</span><span class="sxs-lookup"><span data-stu-id="db4c7-177">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-178">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-178">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-179">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-179">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-180">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-180">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-181">[已連接待機] 可讓 Surface 裝置在未使用時接收更新和通知。</span><span class="sxs-lookup"><span data-stu-id="db4c7-181">Connected Standby allows a Surface device to receive updates and notifications while not being used.</span></span> <span data-ttu-id="db4c7-182">為了獲得最佳體驗，請啟用 [連線待機]。</span><span class="sxs-lookup"><span data-stu-id="db4c7-182">For best experience, Connected Standby should be enabled.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-183">藍牙</span><span class="sxs-lookup"><span data-stu-id="db4c7-183">Bluetooth</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-184">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-184">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-185">檢查是否已啟用藍牙功能。</span><span class="sxs-lookup"><span data-stu-id="db4c7-185">Checks if Bluetooth is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-186">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-186">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-187">啟用</span><span class="sxs-lookup"><span data-stu-id="db4c7-187">Enabled</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-188">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-188">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-189">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-189">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-190">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-190">Guidance:</span></span></strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-191">偵錯模式</span><span class="sxs-lookup"><span data-stu-id="db4c7-191">Debug Mode</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-192">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-192">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-193">檢查作業系統是否處於偵錯模式。</span><span class="sxs-lookup"><span data-stu-id="db4c7-193">Checks if the operating system is in Debug mode.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-194">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-194">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-195">一般</span><span class="sxs-lookup"><span data-stu-id="db4c7-195">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-196">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-196">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-197">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-197">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-198">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-198">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-199">[調試引導] 選項可啟用或停用 Windows 作業系統的內核調試。</span><span class="sxs-lookup"><span data-stu-id="db4c7-199">The debug boot option enables or disables kernel debugging of the Windows operating system.</span></span> <span data-ttu-id="db4c7-200">啟用此選項可能會造成系統不穩定，而且可以避免 DRM （數位版權 managemend）受保護的媒體無法播放。</span><span class="sxs-lookup"><span data-stu-id="db4c7-200">Enabling this option can cause system instability and can prevent DRM (digital rights managemend) protected media from playing.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-201">測試簽署</span><span class="sxs-lookup"><span data-stu-id="db4c7-201">Test Signing</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-202">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-202">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-203">檢查是否已啟用測試簽章。</span><span class="sxs-lookup"><span data-stu-id="db4c7-203">Checks if Test Signing is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-204">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-204">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-205">一般</span><span class="sxs-lookup"><span data-stu-id="db4c7-205">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-206">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-206">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-207">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-207">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-208">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-208">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-209">[測試簽章] 是 Windows 啟動設定，只應該用來測試預發行的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="db4c7-209">Test Signing is a Windows startup setting that should only be used to test pre-release drivers.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-210">使用中的電源配置</span><span class="sxs-lookup"><span data-stu-id="db4c7-210">Active Power Plan</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-211">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-211">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-212">檢查正確的電源配置是否處於作用中狀態。</span><span class="sxs-lookup"><span data-stu-id="db4c7-212">Checks that the correct power plan is active.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-213">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-213">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-214">平衡</span><span class="sxs-lookup"><span data-stu-id="db4c7-214">Balanced</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-215">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-215">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-216">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-216">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-217">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-217">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-218">強烈建議您使用「已平衡」電源配置，以最大限度地提高生產力和電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="db4c7-218">It is highly recommended to use the "Balanced" power plan to maximize productivity and battery life.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500"><span data-ttu-id="db4c7-219">Windows Update</span><span class="sxs-lookup"><span data-stu-id="db4c7-219">Windows Update</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-220">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-220">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-221">檢查裝置是否為最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="db4c7-221">Checks if the device is up to date with Windows updates.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-222">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-222">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-223">Microsoft Silverlight （KB4023307），適用于 Windows Defender 防病毒的定義更新-KB2267602 （定義1.279.1433.0）</span><span class="sxs-lookup"><span data-stu-id="db4c7-223">Microsoft Silverlight (KB4023307), Definition Update for Windows Defender Antivirus - KB2267602 (Definition 1.279.1433.0)</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-224">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-224">Condition:</span></span></strong></td><td><font color="ff9500"><span data-ttu-id="db4c7-225">不是最佳</span><span class="sxs-lookup"><span data-stu-id="db4c7-225">Not Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-226">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-226">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-227">更新至最新的 windows 可確保您位於最新的固件和驅動程式。</span><span class="sxs-lookup"><span data-stu-id="db4c7-227">Updating to the latest windows makes sure you are on the latest firmware and drivers.</span></span> <span data-ttu-id="db4c7-228">建議您始終將您的裝置保持在最新狀態</span><span class="sxs-lookup"><span data-stu-id="db4c7-228">It is recommended to always keep your device up to date</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-229">可用磁片磁碟空間</span><span class="sxs-lookup"><span data-stu-id="db4c7-229">Free Hard Drive Space</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-230">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-230">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-231">檢查是否有低可用的磁片磁片磁碟機空間。</span><span class="sxs-lookup"><span data-stu-id="db4c7-231">Checks for low free hard drive space.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-232">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-232">Value:</span></span></strong></td><td><span data-ttu-id="db4c7-233">66%</span><span class="sxs-lookup"><span data-stu-id="db4c7-233">66%</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-234">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-234">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-235">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-235">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-236">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-236">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-237">為了獲得最佳效能，您的硬碟應該至少有10% 的容量作為可用空間。</span><span class="sxs-lookup"><span data-stu-id="db4c7-237">For best performance, your hard drive should have at least 10% of its capacity as free space.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-238">無法運作的裝置</span><span class="sxs-lookup"><span data-stu-id="db4c7-238">Non-Functioning Devices</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-239">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-239">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-240">裝置管理器中無法運作的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="db4c7-240">List of non-functioning devices in Device Manager.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-241">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-241">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-242">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-242">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-243">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-243">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-244">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-244">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-245">在裝置管理器中無法正常運作的裝置，可能會導致表面裝置（例如但不限於）不會因個別硬體元件而節省電源的問題。</span><span class="sxs-lookup"><span data-stu-id="db4c7-245">Non-functioning devices in Device Manager may cause unpredictable problems with Surface devices such as, but not limited to, no power savings for the respective hardware component.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="db4c7-246">外部監視器</span><span class="sxs-lookup"><span data-stu-id="db4c7-246">External Monitor</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="db4c7-247">描述：</span><span class="sxs-lookup"><span data-stu-id="db4c7-247">Description:</span></span></strong></td><td><span data-ttu-id="db4c7-248">檢查是否有可能有相容性問題的外部監視器。</span><span class="sxs-lookup"><span data-stu-id="db4c7-248">Checks for an external monitor that may have compatibility issues.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-249">有效值</span><span class="sxs-lookup"><span data-stu-id="db4c7-249">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-250">疾病</span><span class="sxs-lookup"><span data-stu-id="db4c7-250">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="db4c7-251">實現</span><span class="sxs-lookup"><span data-stu-id="db4c7-251">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="db4c7-252">級</span><span class="sxs-lookup"><span data-stu-id="db4c7-252">Guidance:</span></span></strong></td><td><span data-ttu-id="db4c7-253">與原始設備製造商確認與 Surface 裝置的相容性。</span><span class="sxs-lookup"><span data-stu-id="db4c7-253">Check with the original equipment manufacturer for compatibility with your Surface device.</span></span></td></tr>
</table>
