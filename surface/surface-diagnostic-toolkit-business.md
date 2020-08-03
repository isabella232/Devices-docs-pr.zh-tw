---
title: 部署商務用 Surface 診斷工具組
description: 本主題說明如何使用適用于商務的 Surface 診斷工具組。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 07/31/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 9c250cef63b760f3faab9172aa950c305e4e47e5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "10902981"
---
# <span data-ttu-id="3a7b2-103">部署商務用 Surface 診斷工具組</span><span class="sxs-lookup"><span data-stu-id="3a7b2-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="3a7b2-104">適用于商務用 Microsoft Surface 診斷工具組（SDT）可讓 IT 系統管理員快速調查、疑難排解及解決與 Surface 裝置的硬體、軟體及固件問題。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="3a7b2-105">除了取得裝置健康情況深入資訊以及解決問題的指示之外，您還可以執行診斷測試和軟體修復範圍。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="3a7b2-106">具體來說，SDT for Business 可讓您：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="3a7b2-107">自訂套件。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-107">Customize the package.</span></span>](#create-custom-sdt)
- [<span data-ttu-id="3a7b2-108">使用命令執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="3a7b2-109">執行多個硬體測試以進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="3a7b2-110">產生記錄來分析問題。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="3a7b2-111">取得對比裝置與最佳設定的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="3a7b2-112">主要案例和下載資源</span><span class="sxs-lookup"><span data-stu-id="3a7b2-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="3a7b2-113">若要執行 SDT for Business，請下載下表所列的元件。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="3a7b2-114">模式</span><span class="sxs-lookup"><span data-stu-id="3a7b2-114">Mode</span></span> |  <span data-ttu-id="3a7b2-115">主要案例</span><span class="sxs-lookup"><span data-stu-id="3a7b2-115">Primary scenarios</span></span> | <span data-ttu-id="3a7b2-116">下載</span><span class="sxs-lookup"><span data-stu-id="3a7b2-116">Download</span></span> | <span data-ttu-id="3a7b2-117">深入了解</span><span class="sxs-lookup"><span data-stu-id="3a7b2-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="3a7b2-118">桌面模式</span><span class="sxs-lookup"><span data-stu-id="3a7b2-118">Desktop mode</span></span> |  <span data-ttu-id="3a7b2-119">協助使用者在其 Surface 裝置上執行 SDT，以針對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="3a7b2-120">建立要在一或多個 Surface 裝置上部署的自訂套件，讓使用者可以選取要收集及分析的特定記錄。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="3a7b2-121">SDT 可發佈的 MSI 套件：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="3a7b2-122">商務用 Microsoft Surface 安裝工具</span><span class="sxs-lookup"><span data-stu-id="3a7b2-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="3a7b2-123">適用於 IT 的 Surface 工具</span><span class="sxs-lookup"><span data-stu-id="3a7b2-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="3a7b2-124">在桌面圖案中使用表面診斷工具箱</span><span class="sxs-lookup"><span data-stu-id="3a7b2-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="3a7b2-125">命令列</span><span class="sxs-lookup"><span data-stu-id="3a7b2-125">Command line</span></span> |  <span data-ttu-id="3a7b2-126">使用標準工具（例如 Configuration Manager），直接在沒有使用者互動的情況下遠端疑難排解 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="3a7b2-127">它包含下列命令：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="3a7b2-128">收集所有記錄檔</span><span class="sxs-lookup"><span data-stu-id="3a7b2-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="3a7b2-129">使用最佳做法分析程式來執行健康情況分析。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="3a7b2-130">針對缺少的固件或驅動程式更新檢查 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="3a7b2-131">檢查保修資訊。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="3a7b2-132">SDT 主控台 app：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-132">SDT console app:</span></span><br><span data-ttu-id="3a7b2-133">Microsoft Surface Diagnostics 應用程式主控台</span><span class="sxs-lookup"><span data-stu-id="3a7b2-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="3a7b2-134">適用於 IT 的 Surface 工具</span><span class="sxs-lookup"><span data-stu-id="3a7b2-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="3a7b2-135">使用命令執行表面診斷工具箱</span><span class="sxs-lookup"><span data-stu-id="3a7b2-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="3a7b2-136">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="3a7b2-136">Supported devices</span></span> 

<span data-ttu-id="3a7b2-137">在 Surface 3 和更新版本的裝置上支援 SDT for Business，包括：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="3a7b2-138">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="3a7b2-138">Surface Book 3</span></span>
- <span data-ttu-id="3a7b2-139">表面移2</span><span class="sxs-lookup"><span data-stu-id="3a7b2-139">Surface Go 2</span></span>
- <span data-ttu-id="3a7b2-140">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="3a7b2-140">Surface Pro X</span></span>
- <span data-ttu-id="3a7b2-141">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="3a7b2-141">Surface Pro 7</span></span>
- <span data-ttu-id="3a7b2-142">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="3a7b2-142">Surface Laptop 3</span></span>
- <span data-ttu-id="3a7b2-143">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="3a7b2-143">Surface Pro 6</span></span>
- <span data-ttu-id="3a7b2-144">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="3a7b2-144">Surface Laptop 2</span></span>
- <span data-ttu-id="3a7b2-145">Surface Go</span><span class="sxs-lookup"><span data-stu-id="3a7b2-145">Surface Go</span></span>
- <span data-ttu-id="3a7b2-146">使用 LTE 的 Surface</span><span class="sxs-lookup"><span data-stu-id="3a7b2-146">Surface Go with LTE</span></span>
- <span data-ttu-id="3a7b2-147">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="3a7b2-147">Surface Book 2</span></span>
- <span data-ttu-id="3a7b2-148">配備 LTE Advanced 的 Surface Pro (型號 1807)</span><span class="sxs-lookup"><span data-stu-id="3a7b2-148">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="3a7b2-149">Surface Pro (型號 1796)</span><span class="sxs-lookup"><span data-stu-id="3a7b2-149">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="3a7b2-150">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="3a7b2-150">Surface Laptop</span></span>
- <span data-ttu-id="3a7b2-151">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="3a7b2-151">Surface Studio</span></span>
- <span data-ttu-id="3a7b2-152">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="3a7b2-152">Surface Studio 2</span></span>
- <span data-ttu-id="3a7b2-153">Surface Book</span><span class="sxs-lookup"><span data-stu-id="3a7b2-153">Surface Book</span></span>
- <span data-ttu-id="3a7b2-154">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="3a7b2-154">Surface Pro 4</span></span>
- <span data-ttu-id="3a7b2-155">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="3a7b2-155">Surface 3 LTE</span></span>
- <span data-ttu-id="3a7b2-156">Surface 3</span><span class="sxs-lookup"><span data-stu-id="3a7b2-156">Surface 3</span></span>
- <span data-ttu-id="3a7b2-157">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="3a7b2-157">Surface Pro 3</span></span>

## <span data-ttu-id="3a7b2-158">安裝適用于商務的 Surface 診斷工具箱</span><span class="sxs-lookup"><span data-stu-id="3a7b2-158">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="3a7b2-159">若要建立可發佈給組織中使用者的 SDT 套件：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-159">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="3a7b2-160">使用系統管理員帳戶登入您的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-160">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="3a7b2-161">從 [[表面工具](https://www.microsoft.com/download/details.aspx?id=46703)] 下載您的 Windows 安裝程式套件（.msi），並將它複製到 surface 裝置上（例如桌面）的喜好位置。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-161">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="3a7b2-162">[SDT 設定] 嚮導隨即出現，如圖1所示。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-162">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="3a7b2-163">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-163">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="3a7b2-164">如果沒有出現 [安裝精靈]，請確定您已登入您電腦上的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-164">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![歡迎使用 Surface 診斷工具組設定向導](images/sdt-1.png)

    *<span data-ttu-id="3a7b2-166">圖 1。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-166">Figure 1.</span></span> <span data-ttu-id="3a7b2-167">表面診斷工具組設定向導</span><span class="sxs-lookup"><span data-stu-id="3a7b2-167">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="3a7b2-168">[SDT 設定向導] 出現時，請按 **[下一步]**，接受使用者授權合約（EULA）。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-168">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="3a7b2-169">在 [安裝選項] 畫面上，視需要變更預設安裝位置。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-169">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="3a7b2-170">選取 [設定類型] 底下的 [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-170">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="3a7b2-171">標準選項可讓使用者在其 Surface 裝置上直接執行診斷工具，前提是他們已使用系統管理員帳戶登入他們的裝置。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-171">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![安裝選項：高級](images/sdt-install.png)

7. <span data-ttu-id="3a7b2-173">按一下 **[下一步]** ，然後按一下 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-173">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="3a7b2-174">使用命令列安裝</span><span class="sxs-lookup"><span data-stu-id="3a7b2-174">Installing using the command line</span></span>
<span data-ttu-id="3a7b2-175">如有需要，您可以在命令提示字元中安裝 SDT，並設定自訂旗標以在 [管理員模式] 中安裝該工具。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-175">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="3a7b2-176">SDT 包含下列安裝選項標誌：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-176">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="3a7b2-177">將遙測資料傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-177">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="3a7b2-178">標誌接受 `0` 停用或 `1` 啟用。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-178">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="3a7b2-179">預設值為 [ `1` 傳送遙測]。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-179">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="3a7b2-180">將工具設定為以 [系統管理模式] 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-180">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="3a7b2-181">標誌接受 `0` 用戶端模式或 `1` IT 系統管理員模式。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-181">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="3a7b2-182">預設值為 `0`。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-182">The default value is `0`.</span></span>

### <span data-ttu-id="3a7b2-183">若要從命令列安裝 SDT：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-183">To install SDT from the command line:</span></span>

1. <span data-ttu-id="3a7b2-184">開啟命令提示字元，然後按 enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-184">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="3a7b2-185">範例：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-185">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="3a7b2-186">在 Surface 裝置上尋找 SDT</span><span class="sxs-lookup"><span data-stu-id="3a7b2-186">Locating SDT on your Surface device</span></span>

<span data-ttu-id="3a7b2-187">[SDT] 和 [SDT] 應用程式主控台都已安裝 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-187">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="3a7b2-188">除了 .exe 檔案之外，SDT 還會安裝 JSON 檔案和 admin.dll 檔案（modules\admin.dll），如圖2所示。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-188">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![檔案資源管理器中的 SDT 已安裝檔案清單](images/sdt-2.png)

*<span data-ttu-id="3a7b2-190">圖 2.</span><span class="sxs-lookup"><span data-stu-id="3a7b2-190">Figure 2.</span></span> <span data-ttu-id="3a7b2-191">由 SDT 安裝的檔案</span><span class="sxs-lookup"><span data-stu-id="3a7b2-191">Files installed by SDT</span></span>*

<span id="create-custom-sdt" />

## <span data-ttu-id="3a7b2-192">準備用於發佈的 SDT 套件</span><span class="sxs-lookup"><span data-stu-id="3a7b2-192">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="3a7b2-193">建立自訂套件可讓您將工具目標設定為特定的已知問題。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-193">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="3a7b2-194">按一下 [**開始 > 執行**]、輸入**表面**，然後按一下 [**表面診斷工具] 以取得商務**用。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-194">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="3a7b2-195">當工具開啟時，按一下 [**建立自訂套件**]，如圖3所示。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-195">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![[建立自訂套件] 選項](images/sdt-3.png)

    *<span data-ttu-id="3a7b2-197">圖 3.</span><span class="sxs-lookup"><span data-stu-id="3a7b2-197">Figure 3.</span></span> <span data-ttu-id="3a7b2-198">建立自訂套件</span><span class="sxs-lookup"><span data-stu-id="3a7b2-198">Create custom package</span></span>*

### <span data-ttu-id="3a7b2-199">語言和遙測設定</span><span class="sxs-lookup"><span data-stu-id="3a7b2-199">Language and telemetry settings</span></span>

  <span data-ttu-id="3a7b2-200">建立套件時，您可以選取 [語言設定] 或 [選擇不傳送遙測資訊給 Microsoft]。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-200">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="3a7b2-201">根據預設，SDT 會將遙測傳送至 Microsoft，以使用[Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)來改善應用程式。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-201">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="3a7b2-202">如果您想要拒絕，請在建立自訂套件時清除核取方塊，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-202">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="3a7b2-203">或者，在 [**安裝選項**] 頁面上，清除 [在 SDT 設定期間，**傳送遙測至 Microsoft** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-203">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="3a7b2-204">此設定不會影響執行需要網際網路連線（例如 Windows Update 和軟體修復），或使用 app 工具列中的 [笑臉] 或 [苦臉] 按鈕提供意見反應的測試及修復時，在 Microsoft 伺服器上自動儲存的最小遙測。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-204">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![選取語言和遙測設定](images/sdt-4.png)

*<span data-ttu-id="3a7b2-206">圖 4.</span><span class="sxs-lookup"><span data-stu-id="3a7b2-206">Figure 4.</span></span> <span data-ttu-id="3a7b2-207">選取語言和遙測設定</span><span class="sxs-lookup"><span data-stu-id="3a7b2-207">Select language and telemetry settings</span></span>*


### <span data-ttu-id="3a7b2-208">[Windows Update] 頁面</span><span class="sxs-lookup"><span data-stu-id="3a7b2-208">Windows Update page</span></span>

<span data-ttu-id="3a7b2-209">選取適用于貴組織的選項。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-209">Select the option appropriate for your organization.</span></span> <span data-ttu-id="3a7b2-210">大多數擁有多個使用者的組織通常會選取透過 Windows Server Update Services （WSUS）接收更新，如圖5所示。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-210">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="3a7b2-211">如果您使用的是 [本機 Windows 更新套件] 或 [WSUS]，請視需要輸入路徑。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-211">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![選取 [Windows Update] 選項](images/sdt-5.png)

*<span data-ttu-id="3a7b2-213">圖 5.</span><span class="sxs-lookup"><span data-stu-id="3a7b2-213">Figure 5.</span></span> <span data-ttu-id="3a7b2-214">[Windows Update] 選項</span><span class="sxs-lookup"><span data-stu-id="3a7b2-214">Windows Update option</span></span>*

### <span data-ttu-id="3a7b2-215">軟體修復頁面</span><span class="sxs-lookup"><span data-stu-id="3a7b2-215">Software repair page</span></span>

<span data-ttu-id="3a7b2-216">這可讓您選取或移除執行軟體修復更新的選項。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-216">This allows you to select or remove the option to run software repair updates.</span></span> 

![選取軟體修復選項](images/sdt-6.png)

*<span data-ttu-id="3a7b2-218">圖 6.</span><span class="sxs-lookup"><span data-stu-id="3a7b2-218">Figure 6.</span></span> <span data-ttu-id="3a7b2-219">軟體修復選項</span><span class="sxs-lookup"><span data-stu-id="3a7b2-219">Software repair option</span></span>*

### <span data-ttu-id="3a7b2-220">收集記錄及儲存套件頁面</span><span class="sxs-lookup"><span data-stu-id="3a7b2-220">Collecting logs and saving package page</span></span>

<span data-ttu-id="3a7b2-221">您可以選取在應用程式、驅動程式、硬體及作業系統上執行各種不同的記錄。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-221">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="3a7b2-222">按一下適當的區域，然後從 [可用的記錄] 功能表中選取。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-222">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="3a7b2-223">然後，您可以將套件儲存至使用者可以存取的軟體發佈點或對等位置。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-223">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![選取記錄選項](images/sdt-7.png)

*<span data-ttu-id="3a7b2-225">圖 7.</span><span class="sxs-lookup"><span data-stu-id="3a7b2-225">Figure 7.</span></span> <span data-ttu-id="3a7b2-226">記錄選項並儲存套件</span><span class="sxs-lookup"><span data-stu-id="3a7b2-226">Log option and save package</span></span>*

## <span data-ttu-id="3a7b2-227">後續步驟</span><span class="sxs-lookup"><span data-stu-id="3a7b2-227">Next steps</span></span>

- [<span data-ttu-id="3a7b2-228">在桌面模式中使用商務用 Surface 診斷工具組</span><span class="sxs-lookup"><span data-stu-id="3a7b2-228">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="3a7b2-229">使用命令的 [表面診斷工具] 進行商務用</span><span class="sxs-lookup"><span data-stu-id="3a7b2-229">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="3a7b2-230">變更與更新</span><span class="sxs-lookup"><span data-stu-id="3a7b2-230">Changes and updates</span></span>


### <span data-ttu-id="3a7b2-231">版本2.121.139</span><span class="sxs-lookup"><span data-stu-id="3a7b2-231">Version 2.121.139</span></span>
*<span data-ttu-id="3a7b2-232">發行日期： 31 2020 年7月</span><span class="sxs-lookup"><span data-stu-id="3a7b2-232">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="3a7b2-233">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="3a7b2-234">順暢支援體驗</span><span class="sxs-lookup"><span data-stu-id="3a7b2-234">Seamless support experience</span></span>
- <span data-ttu-id="3a7b2-235">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="3a7b2-235">Bug fixes</span></span>

### <span data-ttu-id="3a7b2-236">版本2.94.139。0</span><span class="sxs-lookup"><span data-stu-id="3a7b2-236">Version 2.94.139.0</span></span>
*<span data-ttu-id="3a7b2-237">發行日期：2020年5月11日</span><span class="sxs-lookup"><span data-stu-id="3a7b2-237">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="3a7b2-238">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-238">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="3a7b2-239">能夠略過 Windows Update 來執行硬體檢查。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-239">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="3a7b2-240">能夠接收最新版本更新的通知</span><span class="sxs-lookup"><span data-stu-id="3a7b2-240">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="3a7b2-241">表面移2</span><span class="sxs-lookup"><span data-stu-id="3a7b2-241">Surface Go 2</span></span>
- <span data-ttu-id="3a7b2-242">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="3a7b2-242">Surface Book 3</span></span>
- <span data-ttu-id="3a7b2-243">顯示進度指標</span><span class="sxs-lookup"><span data-stu-id="3a7b2-243">Show progress indicator</span></span>


### <span data-ttu-id="3a7b2-244">版本2.43.139。0</span><span class="sxs-lookup"><span data-stu-id="3a7b2-244">Version 2.43.139.0</span></span>
*<span data-ttu-id="3a7b2-245">發行日期：2019年10月21日</span><span class="sxs-lookup"><span data-stu-id="3a7b2-245">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="3a7b2-246">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-246">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="3a7b2-247">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="3a7b2-247">Surface Pro 7</span></span>
- <span data-ttu-id="3a7b2-248">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="3a7b2-248">Surface Laptop 3</span></span>

### <span data-ttu-id="3a7b2-249">版本2.42.139。0</span><span class="sxs-lookup"><span data-stu-id="3a7b2-249">Version 2.42.139.0</span></span>
*<span data-ttu-id="3a7b2-250">發行日期：2019年9月24日</span><span class="sxs-lookup"><span data-stu-id="3a7b2-250">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="3a7b2-251">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-251">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="3a7b2-252">下載硬體報告的能力。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-252">Ability to download hardware reports.</span></span>
- <span data-ttu-id="3a7b2-253">直接從工具直接聯繫 Microsoft 支援人員的能力。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-253">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="3a7b2-254">版本2.41.139。0</span><span class="sxs-lookup"><span data-stu-id="3a7b2-254">Version 2.41.139.0</span></span>
*<span data-ttu-id="3a7b2-255">發行日期：2019年6月24日</span><span class="sxs-lookup"><span data-stu-id="3a7b2-255">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="3a7b2-256">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="3a7b2-257">記錄和報告中包含的驅動程式版本資訊。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-257">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="3a7b2-258">提供關於 app 的意見反應的能力。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-258">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="3a7b2-259">版本2.36.139。0</span><span class="sxs-lookup"><span data-stu-id="3a7b2-259">Version 2.36.139.0</span></span>
*<span data-ttu-id="3a7b2-260">發行日期：2019年4月26日</span><span class="sxs-lookup"><span data-stu-id="3a7b2-260">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="3a7b2-261">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="3a7b2-261">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="3a7b2-262">[高級設定] 選項可透過安裝程式 UI 解除系統管理員許可權，而不需要命令列設定。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-262">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="3a7b2-263">協助工具增強功能。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-263">Accessibility improvements.</span></span>
- <span data-ttu-id="3a7b2-264">記錄中包含 Surface 亮度控制設定。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-264">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="3a7b2-265">報表發生器中的外部監視器相容性支援連結。</span><span class="sxs-lookup"><span data-stu-id="3a7b2-265">External monitor compatibility support link in report generator.</span></span>
