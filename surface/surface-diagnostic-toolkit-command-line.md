---
title: 使用命令執行商務用 Surface 診斷工具組
description: 如何在命令主控台中執行 Surface 診斷工具套件
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
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327327"
---
# <span data-ttu-id="dcbfd-103">使用命令執行商務用 Surface 診斷工具組</span><span class="sxs-lookup"><span data-stu-id="dcbfd-103">Run Surface Diagnostic Toolkit for Business using commands</span></span>

<span data-ttu-id="dcbfd-104">在命令提示 (SDT) 執行 Surface 診斷工具套件，需要下載 SDT 應用程式主控台。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-104">Running the Surface Diagnostic Toolkit (SDT) at a command prompt requires downloading the SDT app console.</span></span> <span data-ttu-id="dcbfd-105">安裝之後，您可以透過 Windows 命令主控台 (cmd.exe) 或 Windows PowerShell ，包括 PowerShell 整合式腳本環境 (ISE) ，在命令、複製/貼上及其他功能自動完成時，在命令提示符上執行 SDT。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-105">After it's installed, you can run SDT at a command prompt via the Windows command console (cmd.exe) or using Windows PowerShell, including PowerShell Integrated Scripting Environment (ISE), which provides support for autocompletion of commands, copy/paste, and other features.</span></span>  <span data-ttu-id="dcbfd-106">有關 SDT 中支援的 Surface 裝置清單，請參閱部署商務用 [Surface 診斷工具組](surface-diagnostic-toolkit-business.md)。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>

>[!NOTE]
><span data-ttu-id="dcbfd-107">若要使用命令執行 SDT，您必須已登錄系統管理員帳戶，或是在 Surface 裝置上是系統管理員群組成員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-107">To run SDT using commands, you must be signed in to the Administrator account or signed in to an account that is a member of the Administrator group on your Surface device.</span></span>

## <span data-ttu-id="dcbfd-108">執行 SDT 應用程式主機</span><span class="sxs-lookup"><span data-stu-id="dcbfd-108">Running SDT app console</span></span>

<span data-ttu-id="dcbfd-109">從適用于 IT 的 Surface Tools 下載頁面 [下載並安裝 SDT 應用程式主機](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-109">Download and install SDT app console from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703).</span></span> <span data-ttu-id="dcbfd-110">您可以使用 Windows 命令提示 (cmd.exe) 或 Windows PowerShell 執行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-110">You can use the Windows command prompt (cmd.exe) or Windows PowerShell to:</span></span> 

- <span data-ttu-id="dcbfd-111">收集所有記錄檔案。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-111">Collect all log files.</span></span>
- <span data-ttu-id="dcbfd-112">使用最佳做法分析程式執行健康診斷。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-112">Run health diagnostics using Best Practice Analyzer.</span></span>
- <span data-ttu-id="dcbfd-113">檢查更新中缺少的中或驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-113">Check update for missing firmware or driver updates.</span></span>

>[!NOTE]
><span data-ttu-id="dcbfd-114">在這個版本中，SDT 應用程式主機僅支援單一命令。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-114">In this release, the SDT app console supports single commands only.</span></span> <span data-ttu-id="dcbfd-115">執行多個命令列選項需要個別執行每個命令的主控台執行。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-115">Running multiple command line options requires running the console exe separately for each command.</span></span> 

<span data-ttu-id="dcbfd-116">根據預設，輸出檔案會儲存于與主控台應用程式相同的位置。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-116">By default, output files are saved in the same location as the console app.</span></span> <span data-ttu-id="dcbfd-117">請參閱下表以查看完整的命令清單。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-117">Refer to the following table for a complete list of commands.</span></span>

<span data-ttu-id="dcbfd-118">命令</span><span class="sxs-lookup"><span data-stu-id="dcbfd-118">Command</span></span> | <span data-ttu-id="dcbfd-119">附註</span><span class="sxs-lookup"><span data-stu-id="dcbfd-119">Notes</span></span>
--- | ---
<span data-ttu-id="dcbfd-120">-DataCollector "output file"</span><span class="sxs-lookup"><span data-stu-id="dcbfd-120">-DataCollector "output file"</span></span> | <span data-ttu-id="dcbfd-121">將系統詳細資料收集到 zip 檔案中。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-121">Collects system details into a zip file.</span></span> <span data-ttu-id="dcbfd-122">「輸出檔案」是建立系統詳細資料 zip 檔案的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-122">"output file" is the file path to create system details zip file.</span></span><br><br><span data-ttu-id="dcbfd-123">**範例**：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-123">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
<span data-ttu-id="dcbfd-124">-bpa "output file"</span><span class="sxs-lookup"><span data-stu-id="dcbfd-124">-bpa "output file"</span></span> | <span data-ttu-id="dcbfd-125">檢查裝置中的多個設定和健康情況指示器。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-125">Checks several settings and health indicators in the device.</span></span> <span data-ttu-id="dcbfd-126">「輸出檔案」是建立 HTML 報表的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-126">“output file" is the file path to create the HTML report.</span></span><br><br><span data-ttu-id="dcbfd-127">**範例**：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-127">**Example**:</span></span><br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
<span data-ttu-id="dcbfd-128">-windowsupdate</span><span class="sxs-lookup"><span data-stu-id="dcbfd-128">-windowsupdate</span></span> | <span data-ttu-id="dcbfd-129">檢查 Windows Update 線上伺服器中缺少的內文和/或驅動程式更新。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-129">Checks Windows Update online servers for missing firmware and/or driver updates.</span></span><br><br><span data-ttu-id="dcbfd-130">**範例**：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-130">**Example**:</span></span><br><span data-ttu-id="dcbfd-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span><span class="sxs-lookup"><span data-stu-id="dcbfd-131">Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate</span></span>
<span data-ttu-id="dcbfd-132">-保固「輸出檔案」</span><span class="sxs-lookup"><span data-stu-id="dcbfd-132">-warranty "output file"</span></span> | <span data-ttu-id="dcbfd-133">檢查裝置上的保固資訊 (有效或無效) 。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-133">Checks warranty information on the device (valid or invalid).</span></span> <span data-ttu-id="dcbfd-134">選擇性的「輸出檔案」是建立 xml 檔案的檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-134">The optional “output file” is the file path to create the xml file.</span></span> <br><br><span data-ttu-id="dcbfd-135">**範例**：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-135">**Example**:</span></span> <br><span data-ttu-id="dcbfd-136">Microsoft.Surface.Diagnostics.App.Console.exe –保固 「warranty.xml」</span><span class="sxs-lookup"><span data-stu-id="dcbfd-136">Microsoft.Surface.Diagnostics.App.Console.exe –warranty “warranty.xml”</span></span>


>[!NOTE]
><span data-ttu-id="dcbfd-137">若要在目標裝置上遠端執行 SDT 應用程式主控台，您可以使用 Microsoft 端點群組原則管理員等群組原則管理工具。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-137">To run the SDT app console remotely on target devices, you can use a configuration management tool such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="dcbfd-138">或者，您可以建立一個 .zip 檔案，其中包含主控台應用程式及適當的主控台命令，並且根據貴組織的軟體發佈程式進行部署。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-138">Alternatively, you can create a .zip file containing the console app and appropriate console commands and deploy per your organization’s software distribution processes.</span></span> 

## <span data-ttu-id="dcbfd-139">執行最佳做法分析程式</span><span class="sxs-lookup"><span data-stu-id="dcbfd-139">Running Best Practice Analyzer</span></span> 

<span data-ttu-id="dcbfd-140">您可以在 BitLocker、Secure Boot 和信任的平臺模組 (TPM) 等重要元件上執行 BPA 測試，然後將結果輸出至可共用檔案。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-140">You can run BPA tests across key components such as BitLocker, Secure Boot, and Trusted Platform Module (TPM) and then output the results to a shareable file.</span></span> <span data-ttu-id="dcbfd-141">此工具會產生一系列表格，包含色彩編碼的標題和條件描述項，以及有關如何解決此問題的指引。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-141">The tool generates a series of tables with color-coded headings and condition descriptors along with guidance about how to approach resolving the issue.</span></span> 

- <span data-ttu-id="dcbfd-142">綠色表示元件以最佳狀態執行， (優化) 。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-142">Green indicates the component is running in an optimal condition (optimal).</span></span>
- <span data-ttu-id="dcbfd-143">橘色表示元件未在最佳狀況下執行， (優化) 。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-143">Orange indicates the component is not running in an optimal condition (not optimal).</span></span>
- <span data-ttu-id="dcbfd-144">紅色表示元件狀態異常。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-144">Red indicates the component is in an abnormal state.</span></span> 

### <span data-ttu-id="dcbfd-145">BPA 結果輸出範例</span><span class="sxs-lookup"><span data-stu-id="dcbfd-145">Sample BPA results output</span></span>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-146">BitLocker</span><span class="sxs-lookup"><span data-stu-id="dcbfd-146">BitLocker</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-147">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-147">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-148">檢查系統磁碟機上是否已啟用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-148">Checks if BitLocker is enabled on the system drive.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-149">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-149">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-150">保護已上</span><span class="sxs-lookup"><span data-stu-id="dcbfd-150">Protection On</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-151">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-151">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-152">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-152">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-153">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-153">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-154">強烈建議您啟用 BitLocker 來保護您的資料。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-154">It is highly recommended to enable BitLocker to protect your data.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-155">安全開機</span><span class="sxs-lookup"><span data-stu-id="dcbfd-155">Secure Boot</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-156">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-156">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-157">檢查是否已啟用安全開機。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-157">Checks if Secure Boot is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-158">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-158">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-159">True</span><span class="sxs-lookup"><span data-stu-id="dcbfd-159">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-160">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-160">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-161">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-161">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-162">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-162">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-163">強烈建議您啟用安全開機來保護您的電腦。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-163">It is highly recommended to enable Secure Boot to protect your PC.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-164">信賴平台模組</span><span class="sxs-lookup"><span data-stu-id="dcbfd-164">Trusted Platform Module</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-165">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-165">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-166">確保 TPM 能夠運作。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-166">Ensures that the TPM is functional.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-167">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-167">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-168">True</span><span class="sxs-lookup"><span data-stu-id="dcbfd-168">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-169">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-169">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-170">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-170">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-171">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-171">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-172">如果沒有功能性 TPM，例如 BitLocker 等安全性函數可能無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-172">Without a functional TPM, security-based functions such as BitLocker may not work properly.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-173">已連接待命</span><span class="sxs-lookup"><span data-stu-id="dcbfd-173">Connected Standby</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-174">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-174">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-175">檢查是否已啟用連接待命。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-175">Checks if Connected Standby is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-176">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-176">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-177">True</span><span class="sxs-lookup"><span data-stu-id="dcbfd-177">True</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-178">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-178">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-179">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-179">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-180">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-180">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-181">已連接待命可讓 Surface 裝置在未使用時接收更新和通知。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-181">Connected Standby allows a Surface device to receive updates and notifications while not being used.</span></span> <span data-ttu-id="dcbfd-182">為了獲得最佳體驗，應該啟用連接待命。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-182">For best experience, Connected Standby should be enabled.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-183">藍牙</span><span class="sxs-lookup"><span data-stu-id="dcbfd-183">Bluetooth</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-184">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-184">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-185">檢查藍牙是否已啟用。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-185">Checks if Bluetooth is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-186">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-186">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-187">啟用</span><span class="sxs-lookup"><span data-stu-id="dcbfd-187">Enabled</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-188">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-188">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-189">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-189">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-190">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-190">Guidance:</span></span></strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-191">Debug 模式</span><span class="sxs-lookup"><span data-stu-id="dcbfd-191">Debug Mode</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-192">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-192">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-193">檢查作業系統是否位於 Debug 模式。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-193">Checks if the operating system is in Debug mode.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-194">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-194">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-195">一般</span><span class="sxs-lookup"><span data-stu-id="dcbfd-195">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-196">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-196">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-197">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-197">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-198">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-198">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-199">啟用或停用 Windows 作業系統之核心的啟動啟動選項。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-199">The debug boot option enables or disables kernel debugging of the Windows operating system.</span></span> <span data-ttu-id="dcbfd-200">啟用此選項可能會導致系統不穩定，並可防止 DRM (受保護媒體) 數位版權管理。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-200">Enabling this option can cause system instability and can prevent DRM (digital rights managemend) protected media from playing.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-201">測試簽署</span><span class="sxs-lookup"><span data-stu-id="dcbfd-201">Test Signing</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-202">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-202">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-203">檢查是否已啟用測試簽署。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-203">Checks if Test Signing is enabled.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-204">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-204">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-205">一般</span><span class="sxs-lookup"><span data-stu-id="dcbfd-205">Normal</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-206">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-206">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-207">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-207">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-208">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-208">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-209">測試簽署是 Windows 啟動設定，應該只能用來測試版驅動程式。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-209">Test Signing is a Windows startup setting that should only be used to test pre-release drivers.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-210">使用中電源配置</span><span class="sxs-lookup"><span data-stu-id="dcbfd-210">Active Power Plan</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-211">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-211">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-212">檢查正確的電源配置為使用中。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-212">Checks that the correct power plan is active.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-213">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-213">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-214">平衡</span><span class="sxs-lookup"><span data-stu-id="dcbfd-214">Balanced</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-215">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-215">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-216">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-216">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-217">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-217">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-218">強烈建議使用「平衡」電源配置，以最大化生產力和電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-218">It is highly recommended to use the "Balanced" power plan to maximize productivity and battery life.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500"><span data-ttu-id="dcbfd-219">Windows Update</span><span class="sxs-lookup"><span data-stu-id="dcbfd-219">Windows Update</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-220">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-220">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-221">檢查裝置是否使用 Windows 更新為最新狀態。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-221">Checks if the device is up to date with Windows updates.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-222">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-222">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-223">Microsoft Silverlight (KB4023307) ，Windows Defender 防毒軟體的定義更新 - KB2267602 (定義 1.279.1433.0) </span><span class="sxs-lookup"><span data-stu-id="dcbfd-223">Microsoft Silverlight (KB4023307), Definition Update for Windows Defender Antivirus - KB2267602 (Definition 1.279.1433.0)</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-224">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-224">Condition:</span></span></strong></td><td><font color="ff9500"><span data-ttu-id="dcbfd-225">非優化</span><span class="sxs-lookup"><span data-stu-id="dcbfd-225">Not Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-226">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-226">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-227">更新至最新的視窗，確保您使用最新的新版或驅動程式。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-227">Updating to the latest windows makes sure you are on the latest firmware and drivers.</span></span> <span data-ttu-id="dcbfd-228">建議您隨時將裝置保持在最新狀態</span><span class="sxs-lookup"><span data-stu-id="dcbfd-228">It is recommended to always keep your device up to date</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-229">免費硬碟空間</span><span class="sxs-lookup"><span data-stu-id="dcbfd-229">Free Hard Drive Space</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-230">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-230">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-231">檢查低免費硬碟空間。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-231">Checks for low free hard drive space.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-232">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-232">Value:</span></span></strong></td><td><span data-ttu-id="dcbfd-233">66%</span><span class="sxs-lookup"><span data-stu-id="dcbfd-233">66%</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-234">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-234">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-235">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-235">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-236">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-236">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-237">為了獲得最佳效果，您的硬碟至少應擁有 10% 的可用空間。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-237">For best performance, your hard drive should have at least 10% of its capacity as free space.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-238">功能不全的裝置</span><span class="sxs-lookup"><span data-stu-id="dcbfd-238">Non-Functioning Devices</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-239">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-239">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-240">Device Manager 中功能不運作的裝置清單。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-240">List of non-functioning devices in Device Manager.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-241">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-241">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-242">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-242">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-243">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-243">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-244">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-244">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-245">Device Manager 中無法運作的裝置可能會導致 Surface 裝置發生無法預期的問題，例如 ，但不限於，無法節省各硬體元件的電力。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-245">Non-functioning devices in Device Manager may cause unpredictable problems with Surface devices such as, but not limited to, no power savings for the respective hardware component.</span></span></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00"><span data-ttu-id="dcbfd-246">外部監視器</span><span class="sxs-lookup"><span data-stu-id="dcbfd-246">External Monitor</span></span></font></th></tr>
<tr><td><strong><span data-ttu-id="dcbfd-247">描述：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-247">Description:</span></span></strong></td><td><span data-ttu-id="dcbfd-248">檢查可能有相容性問題的外部監視器。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-248">Checks for an external monitor that may have compatibility issues.</span></span></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-249">價值：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-249">Value:</span></span></strong></td><td></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-250">條件：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-250">Condition:</span></span></strong></td><td><font color="00ff00"><span data-ttu-id="dcbfd-251">最優</span><span class="sxs-lookup"><span data-stu-id="dcbfd-251">Optimal</span></span></font></td></tr>
<tr><td><strong><span data-ttu-id="dcbfd-252">指導：</span><span class="sxs-lookup"><span data-stu-id="dcbfd-252">Guidance:</span></span></strong></td><td><span data-ttu-id="dcbfd-253">請與原始設備製造商確認您的 Surface 裝置相容性。</span><span class="sxs-lookup"><span data-stu-id="dcbfd-253">Check with the original equipment manufacturer for compatibility with your Surface device.</span></span></td></tr>
</table>
