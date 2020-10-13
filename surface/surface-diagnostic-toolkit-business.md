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
ms.date: 10/12/2020
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 1f2661811516507abd432dba602cf8ce81e6dbb3
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114661"
---
# <span data-ttu-id="cfa5c-103">部署商務用 Surface 診斷工具組</span><span class="sxs-lookup"><span data-stu-id="cfa5c-103">Deploy Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="cfa5c-104">商務 () SDT 的 Microsoft Surface 診斷工具組可讓 IT 系統管理員快速調查、疑難排解及解決 Surface 裝置的硬體、軟體及固件問題。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-104">The Microsoft Surface Diagnostic Toolkit for Business (SDT) enables IT administrators to quickly investigate, troubleshoot, and resolve hardware, software, and firmware issues with Surface devices.</span></span> <span data-ttu-id="cfa5c-105">除了取得裝置健康情況深入資訊以及解決問題的指示之外，您還可以執行診斷測試和軟體修復範圍。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-105">You can run a range of diagnostic tests and software repairs in addition to obtaining device health insights and guidance for resolving issues.</span></span> 

<span data-ttu-id="cfa5c-106">具體來說，SDT for Business 可讓您：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-106">Specifically, SDT for Business enables you to:</span></span>

- [<span data-ttu-id="cfa5c-107">自訂套件。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-107">Customize the package.</span></span>](#create-custom-sdt)
- [<span data-ttu-id="cfa5c-108">使用命令執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-108">Run the app using commands.</span></span>](surface-diagnostic-toolkit-command-line.md)
- [<span data-ttu-id="cfa5c-109">執行多個硬體測試以進行問題的疑難排解。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-109">Run multiple hardware tests to troubleshoot issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [<span data-ttu-id="cfa5c-110">產生記錄來分析問題。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-110">Generate logs for analyzing issues.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [<span data-ttu-id="cfa5c-111">取得對比裝置與最佳設定的詳細報告。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-111">Obtain detailed report comparing device vs optimal configuration.</span></span>](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## <span data-ttu-id="cfa5c-112">主要案例和下載資源</span><span class="sxs-lookup"><span data-stu-id="cfa5c-112">Primary scenarios and download resources</span></span> 

<span data-ttu-id="cfa5c-113">若要執行 SDT for Business，請下載下表所列的元件。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-113">To run SDT for Business, download the components listed in the following table.</span></span>


<span data-ttu-id="cfa5c-114">模式</span><span class="sxs-lookup"><span data-stu-id="cfa5c-114">Mode</span></span> |  <span data-ttu-id="cfa5c-115">主要案例</span><span class="sxs-lookup"><span data-stu-id="cfa5c-115">Primary scenarios</span></span> | <span data-ttu-id="cfa5c-116">下載</span><span class="sxs-lookup"><span data-stu-id="cfa5c-116">Download</span></span> | <span data-ttu-id="cfa5c-117">深入了解</span><span class="sxs-lookup"><span data-stu-id="cfa5c-117">Learn more</span></span>
--- | --- | --- | ---
<span data-ttu-id="cfa5c-118">桌面模式</span><span class="sxs-lookup"><span data-stu-id="cfa5c-118">Desktop mode</span></span> |  <span data-ttu-id="cfa5c-119">協助使用者在其 Surface 裝置上執行 SDT，以針對問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-119">Assist users in running SDT on their Surface devices to troubleshoot issues.</span></span><br><span data-ttu-id="cfa5c-120">建立要在一或多個 Surface 裝置上部署的自訂套件，讓使用者可以選取要收集及分析的特定記錄。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-120">Create a custom package to deploy on one or more Surface devices allowing users to select specific logs to collect and analyze.</span></span> | <span data-ttu-id="cfa5c-121">SDT 可發佈的 MSI 套件：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-121">SDT distributable MSI package:</span></span><br><span data-ttu-id="cfa5c-122">商務用 Microsoft Surface 安裝工具</span><span class="sxs-lookup"><span data-stu-id="cfa5c-122">Microsoft Surface Diagnostic Toolkit for Business Installer</span></span><br>[<span data-ttu-id="cfa5c-123">適用於 IT 的 Surface 工具</span><span class="sxs-lookup"><span data-stu-id="cfa5c-123">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="cfa5c-124">在桌面圖案中使用表面診斷工具箱</span><span class="sxs-lookup"><span data-stu-id="cfa5c-124">Use Surface Diagnostic Toolkit in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
<span data-ttu-id="cfa5c-125">命令列</span><span class="sxs-lookup"><span data-stu-id="cfa5c-125">Command line</span></span> |  <span data-ttu-id="cfa5c-126">使用標準工具（例如 Configuration Manager），直接在沒有使用者互動的情況下遠端疑難排解 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-126">Directly troubleshoot Surface devices remotely without user interaction, using standard tools such as Configuration Manager.</span></span> <span data-ttu-id="cfa5c-127">它包含下列命令：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-127">It includes the following commands:</span></span><br>`-DataCollector` <span data-ttu-id="cfa5c-128">收集所有記錄檔</span><span class="sxs-lookup"><span data-stu-id="cfa5c-128">collects all log files</span></span><br>`-bpa` <span data-ttu-id="cfa5c-129">使用最佳做法分析程式來執行健康情況分析。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-129">runs health diagnostics using Best Practice Analyzer.</span></span><br>`-windowsupdate` <span data-ttu-id="cfa5c-130">針對缺少的固件或驅動程式更新檢查 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-130">checks Windows Update for missing firmware or driver updates.</span></span><br>`-warranty` <span data-ttu-id="cfa5c-131">檢查保修資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-131">checks warranty information.</span></span> <br><br>| <span data-ttu-id="cfa5c-132">SDT 主控台 app：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-132">SDT console app:</span></span><br><span data-ttu-id="cfa5c-133">Microsoft Surface Diagnostics 應用程式主控台</span><span class="sxs-lookup"><span data-stu-id="cfa5c-133">Microsoft Surface Diagnostics App Console</span></span><br>[<span data-ttu-id="cfa5c-134">適用於 IT 的 Surface 工具</span><span class="sxs-lookup"><span data-stu-id="cfa5c-134">Surface Tools for IT</span></span>](https://www.microsoft.com/download/details.aspx?id=46703) | [<span data-ttu-id="cfa5c-135">使用命令執行表面診斷工具箱</span><span class="sxs-lookup"><span data-stu-id="cfa5c-135">Run Surface Diagnostic Toolkit using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="cfa5c-136">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="cfa5c-136">Supported devices</span></span> 

<span data-ttu-id="cfa5c-137">在 Surface 3 和更新版本的裝置上支援 SDT for Business，包括：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-137">SDT for Business is supported on Surface 3 and later devices, including:</span></span>

- <span data-ttu-id="cfa5c-138">Surface 膝上型電腦前往</span><span class="sxs-lookup"><span data-stu-id="cfa5c-138">Surface Laptop Go</span></span>
- <span data-ttu-id="cfa5c-139">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="cfa5c-139">Surface Book 3</span></span>
- <span data-ttu-id="cfa5c-140">表面移2</span><span class="sxs-lookup"><span data-stu-id="cfa5c-140">Surface Go 2</span></span>
- <span data-ttu-id="cfa5c-141">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="cfa5c-141">Surface Pro X</span></span>
- <span data-ttu-id="cfa5c-142">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="cfa5c-142">Surface Pro 7</span></span>
- <span data-ttu-id="cfa5c-143">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="cfa5c-143">Surface Laptop 3</span></span>
- <span data-ttu-id="cfa5c-144">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="cfa5c-144">Surface Pro 6</span></span>
- <span data-ttu-id="cfa5c-145">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="cfa5c-145">Surface Laptop 2</span></span>
- <span data-ttu-id="cfa5c-146">Surface Go</span><span class="sxs-lookup"><span data-stu-id="cfa5c-146">Surface Go</span></span>
- <span data-ttu-id="cfa5c-147">使用 LTE 的 Surface</span><span class="sxs-lookup"><span data-stu-id="cfa5c-147">Surface Go with LTE</span></span>
- <span data-ttu-id="cfa5c-148">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="cfa5c-148">Surface Book 2</span></span>
- <span data-ttu-id="cfa5c-149">配備 LTE Advanced 的 Surface Pro (型號 1807)</span><span class="sxs-lookup"><span data-stu-id="cfa5c-149">Surface Pro with LTE Advanced (Model 1807)</span></span>
- <span data-ttu-id="cfa5c-150">Surface Pro (型號 1796)</span><span class="sxs-lookup"><span data-stu-id="cfa5c-150">Surface Pro (Model 1796)</span></span>
- <span data-ttu-id="cfa5c-151">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="cfa5c-151">Surface Laptop</span></span>
- <span data-ttu-id="cfa5c-152">Surface Studio</span><span class="sxs-lookup"><span data-stu-id="cfa5c-152">Surface Studio</span></span>
- <span data-ttu-id="cfa5c-153">Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="cfa5c-153">Surface Studio 2</span></span>
- <span data-ttu-id="cfa5c-154">Surface Book</span><span class="sxs-lookup"><span data-stu-id="cfa5c-154">Surface Book</span></span>
- <span data-ttu-id="cfa5c-155">Surface Pro 4</span><span class="sxs-lookup"><span data-stu-id="cfa5c-155">Surface Pro 4</span></span>
- <span data-ttu-id="cfa5c-156">Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="cfa5c-156">Surface 3 LTE</span></span>
- <span data-ttu-id="cfa5c-157">Surface 3</span><span class="sxs-lookup"><span data-stu-id="cfa5c-157">Surface 3</span></span>
- <span data-ttu-id="cfa5c-158">Surface Pro 3</span><span class="sxs-lookup"><span data-stu-id="cfa5c-158">Surface Pro 3</span></span>

## <span data-ttu-id="cfa5c-159">安裝適用于商務的 Surface 診斷工具箱</span><span class="sxs-lookup"><span data-stu-id="cfa5c-159">Installing Surface Diagnostic Toolkit for Business</span></span>

<span data-ttu-id="cfa5c-160">若要建立可發佈給組織中使用者的 SDT 套件：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-160">To create an SDT package that you can distribute to users in your organization:</span></span>

1. <span data-ttu-id="cfa5c-161">使用系統管理員帳戶登入您的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-161">Sign in to your Surface device using the Administrator account.</span></span>
2. <span data-ttu-id="cfa5c-162">從 [ [表面工具](https://www.microsoft.com/download/details.aspx?id=46703) ] 下載 Windows 安裝程式套件 ( .msi) ，然後將它複製到 surface 裝置上的可取位置，例如 [桌面]。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-162">Download SDT Windows Installer Package (.msi) from the [Surface Tools for IT download page](https://www.microsoft.com/download/details.aspx?id=46703) and copy it to a preferred location on your Surface device, such as Desktop.</span></span>
3. <span data-ttu-id="cfa5c-163">[SDT 設定] 嚮導隨即出現，如圖1所示。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-163">The SDT setup wizard appears, as shown in figure 1.</span></span> <span data-ttu-id="cfa5c-164">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-164">Click **Next**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="cfa5c-165">如果沒有出現 [安裝精靈]，請確定您已登入您電腦上的系統管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-165">If the setup wizard does not appear, ensure that you are signed into the Administrator account on your computer.</span></span> 

    ![歡迎使用 Surface 診斷工具組設定向導](images/sdt-1.png)

    *<span data-ttu-id="cfa5c-167">圖 1。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-167">Figure 1.</span></span> <span data-ttu-id="cfa5c-168">表面診斷工具組設定向導</span><span class="sxs-lookup"><span data-stu-id="cfa5c-168">Surface Diagnostic Toolkit setup wizard</span></span>*

4. <span data-ttu-id="cfa5c-169">當 [SDT 安裝精靈] 出現時，請按 **[下一步]**，接受使用者授權合約 (EULA) </span><span class="sxs-lookup"><span data-stu-id="cfa5c-169">When the SDT setup wizard appears, click **Next**, accept the End User License Agreement (EULA)</span></span>

5. <span data-ttu-id="cfa5c-170">在 [安裝選項] 畫面上，視需要變更預設安裝位置。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-170">On the Install Options screen, change the default install location if desired.</span></span> 
6. <span data-ttu-id="cfa5c-171">選取 [設定類型] 底下的 [ **高級**]。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-171">Under Setup Type, select **Advanced**.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="cfa5c-172">標準選項可讓使用者在其 Surface 裝置上直接執行診斷工具，前提是他們已使用系統管理員帳戶登入他們的裝置。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-172">The standard option allows users to run the diagnostic tool directly on their Surface device provided they are signed into their device using an Administrator account.</span></span> 
    
     ![安裝選項：高級](images/sdt-install.png)

7. <span data-ttu-id="cfa5c-174">按一下 **[下一步]** ，然後按一下 [ **安裝**]。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-174">Click **Next** and then click **Install**.</span></span> 

## <span data-ttu-id="cfa5c-175">使用命令列安裝</span><span class="sxs-lookup"><span data-stu-id="cfa5c-175">Installing using the command line</span></span>
<span data-ttu-id="cfa5c-176">如有需要，您可以在命令提示字元中安裝 SDT，並設定自訂旗標以在 [管理員模式] 中安裝該工具。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-176">If desired, you can install SDT at a command prompt and set a custom flag to install the tool in admin mode.</span></span> <span data-ttu-id="cfa5c-177">SDT 包含下列安裝選項標誌：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-177">SDT contains the following install option flags:</span></span>

- `SENDTELEMETRY` <span data-ttu-id="cfa5c-178">將遙測資料傳送給 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-178">sends telemetry data to Microsoft.</span></span> <span data-ttu-id="cfa5c-179">標誌接受 `0` 停用或 `1` 啟用。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-179">The flag accepts `0` for disabled or `1` for enabled.</span></span> <span data-ttu-id="cfa5c-180">預設值為 [ `1` 傳送遙測]。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-180">The default value is `1` to send telemetry.</span></span>
- `ADMINMODE` <span data-ttu-id="cfa5c-181">將工具設定為以 [系統管理模式] 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-181">configures the tool to be installed in admin mode.</span></span> <span data-ttu-id="cfa5c-182">標誌接受 `0` 用戶端模式或 `1` IT 系統管理員模式。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-182">The flag accepts `0` for client mode or `1` for IT Administrator mode.</span></span> <span data-ttu-id="cfa5c-183">預設值為 `0`。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-183">The default value is `0`.</span></span>

### <span data-ttu-id="cfa5c-184">若要從命令列安裝 SDT：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-184">To install SDT from the command line:</span></span>

1. <span data-ttu-id="cfa5c-185">開啟命令提示字元，然後按 enter 鍵：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-185">Open a command prompt and enter:</span></span>

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **<span data-ttu-id="cfa5c-186">範例：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-186">Example:</span></span>**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <span data-ttu-id="cfa5c-187">在 Surface 裝置上尋找 SDT</span><span class="sxs-lookup"><span data-stu-id="cfa5c-187">Locating SDT on your Surface device</span></span>

<span data-ttu-id="cfa5c-188">[SDT] 和 [SDT] 應用程式主控台都已安裝 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-188">Both SDT and the SDT app console are installed at `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business`.</span></span>

<span data-ttu-id="cfa5c-189">除了 .exe 檔案之外，SDT 還會安裝 JSON 檔案和 admin.dll 檔案 ( # A1) ，如圖2所示。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-189">In addition to the .exe file, SDT installs a JSON file and an admin.dll file (modules\admin.dll), as shown in figure 2.</span></span>

![檔案資源管理器中的 SDT 已安裝檔案清單](images/sdt-2.png)

*<span data-ttu-id="cfa5c-191">圖 2.</span><span class="sxs-lookup"><span data-stu-id="cfa5c-191">Figure 2.</span></span> <span data-ttu-id="cfa5c-192">由 SDT 安裝的檔案</span><span class="sxs-lookup"><span data-stu-id="cfa5c-192">Files installed by SDT</span></span>*

<span id="create-custom-sdt" />

## <span data-ttu-id="cfa5c-193">準備用於發佈的 SDT 套件</span><span class="sxs-lookup"><span data-stu-id="cfa5c-193">Preparing the SDT package for distribution</span></span>

<span data-ttu-id="cfa5c-194">建立自訂套件可讓您將工具目標設定為特定的已知問題。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-194">Creating a custom package allows you to target the tool to specific known issues.</span></span>

1. <span data-ttu-id="cfa5c-195">按一下 [ **開始 > 執行**]、輸入 **表面** ，然後按一下 [ **表面診斷工具] 以取得商務**用。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-195">Click **Start > Run**, enter **Surface** and then click **Surface Diagnostic Toolkit for Business**.</span></span> 
2. <span data-ttu-id="cfa5c-196">當工具開啟時，按一下 [ **建立自訂套件**]，如圖3所示。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-196">When the tool opens, click **Create Custom Package**, as shown in figure 3.</span></span>

    ![[建立自訂套件] 選項](images/sdt-3.png)

    *<span data-ttu-id="cfa5c-198">圖 3.</span><span class="sxs-lookup"><span data-stu-id="cfa5c-198">Figure 3.</span></span> <span data-ttu-id="cfa5c-199">建立自訂套件</span><span class="sxs-lookup"><span data-stu-id="cfa5c-199">Create custom package</span></span>*

### <span data-ttu-id="cfa5c-200">語言和遙測設定</span><span class="sxs-lookup"><span data-stu-id="cfa5c-200">Language and telemetry settings</span></span>

  <span data-ttu-id="cfa5c-201">建立套件時，您可以選取 [語言設定] 或 [選擇不傳送遙測資訊給 Microsoft]。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-201">When creating a package, you can select language settings or opt out of sending telemetry information to Microsoft.</span></span> <span data-ttu-id="cfa5c-202">根據預設，SDT 會將遙測傳送至 Microsoft，以使用 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)來改善應用程式。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-202">By default, SDT sends telemetry to Microsoft that is used to improve the application in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> <span data-ttu-id="cfa5c-203">如果您想要拒絕，請在建立自訂套件時清除核取方塊，如下所示。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-203">If you wish to decline, clear the check box when creating a custom package, as shown below.</span></span> <span data-ttu-id="cfa5c-204">或者，在 [**安裝選項**] 頁面上，清除 [在 SDT 設定期間，**傳送遙測至 Microsoft** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-204">Or clear the **Send telemetry to Microsoft** check box on the **Install Options** page during SDT Setup.</span></span> 

>[!NOTE]
><span data-ttu-id="cfa5c-205">此設定不會影響執行需要網際網路連線（例如 Windows Update 和軟體修復），或使用 app 工具列中的 [笑臉] 或 [苦臉] 按鈕提供意見反應的測試及修復時，在 Microsoft 伺服器上自動儲存的最小遙測。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-205">This setting does not affect the minimal telemetry automatically stored on Microsoft servers when running tests and repairs that require an Internet connection, such as Windows Update and Software repair, or providing feedback using the Smile or Frown buttons in the app toolbar.</span></span> 


![選取語言和遙測設定](images/sdt-4.png)

*<span data-ttu-id="cfa5c-207">圖 4.</span><span class="sxs-lookup"><span data-stu-id="cfa5c-207">Figure 4.</span></span> <span data-ttu-id="cfa5c-208">選取語言和遙測設定</span><span class="sxs-lookup"><span data-stu-id="cfa5c-208">Select language and telemetry settings</span></span>*


### <span data-ttu-id="cfa5c-209">[Windows Update] 頁面</span><span class="sxs-lookup"><span data-stu-id="cfa5c-209">Windows Update page</span></span>

<span data-ttu-id="cfa5c-210">選取適用于貴組織的選項。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-210">Select the option appropriate for your organization.</span></span> <span data-ttu-id="cfa5c-211">大多數擁有多個使用者的組織通常會選取透過 Windows Server Update Services (WSUS 接收更新) ，如圖5所示。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-211">Most organizations with multiple users will typically select to receive updates via Windows Server Update Services (WSUS), as shown in figure 5.</span></span> <span data-ttu-id="cfa5c-212">如果您使用的是 [本機 Windows 更新套件] 或 [WSUS]，請視需要輸入路徑。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-212">If using local Windows Update packages or WSUS, enter the path as appropriate.</span></span> 

![選取 [Windows Update] 選項](images/sdt-5.png)

*<span data-ttu-id="cfa5c-214">圖 5.</span><span class="sxs-lookup"><span data-stu-id="cfa5c-214">Figure 5.</span></span> <span data-ttu-id="cfa5c-215">[Windows Update] 選項</span><span class="sxs-lookup"><span data-stu-id="cfa5c-215">Windows Update option</span></span>*

### <span data-ttu-id="cfa5c-216">軟體修復頁面</span><span class="sxs-lookup"><span data-stu-id="cfa5c-216">Software repair page</span></span>

<span data-ttu-id="cfa5c-217">這可讓您選取或移除執行軟體修復更新的選項。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-217">This allows you to select or remove the option to run software repair updates.</span></span> 

![選取軟體修復選項](images/sdt-6.png)

*<span data-ttu-id="cfa5c-219">圖 6.</span><span class="sxs-lookup"><span data-stu-id="cfa5c-219">Figure 6.</span></span> <span data-ttu-id="cfa5c-220">軟體修復選項</span><span class="sxs-lookup"><span data-stu-id="cfa5c-220">Software repair option</span></span>*

### <span data-ttu-id="cfa5c-221">收集記錄及儲存套件頁面</span><span class="sxs-lookup"><span data-stu-id="cfa5c-221">Collecting logs and saving package page</span></span>

<span data-ttu-id="cfa5c-222">您可以選取在應用程式、驅動程式、硬體及作業系統上執行各種不同的記錄。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-222">You can select to run a wide range of logs across applications, drivers, hardware, and the operating system.</span></span> <span data-ttu-id="cfa5c-223">按一下適當的區域，然後從 [可用的記錄] 功能表中選取。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-223">Click the appropriate area and select from the menu of available logs.</span></span> <span data-ttu-id="cfa5c-224">然後，您可以將套件儲存至使用者可以存取的軟體發佈點或對等位置。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-224">You can then save the package to a software distribution point or equivalent location that users can access.</span></span> 

![選取記錄選項](images/sdt-7.png)

*<span data-ttu-id="cfa5c-226">圖 7.</span><span class="sxs-lookup"><span data-stu-id="cfa5c-226">Figure 7.</span></span> <span data-ttu-id="cfa5c-227">記錄選項並儲存套件</span><span class="sxs-lookup"><span data-stu-id="cfa5c-227">Log option and save package</span></span>*

## <span data-ttu-id="cfa5c-228">後續步驟</span><span class="sxs-lookup"><span data-stu-id="cfa5c-228">Next steps</span></span>

- [<span data-ttu-id="cfa5c-229">在桌面模式中使用商務用 Surface 診斷工具組</span><span class="sxs-lookup"><span data-stu-id="cfa5c-229">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>](surface-diagnostic-toolkit-desktop-mode.md)
- [<span data-ttu-id="cfa5c-230">使用命令的 [表面診斷工具] 進行商務用</span><span class="sxs-lookup"><span data-stu-id="cfa5c-230">Use Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

## <span data-ttu-id="cfa5c-231">變更與更新</span><span class="sxs-lookup"><span data-stu-id="cfa5c-231">Changes and updates</span></span>

### <span data-ttu-id="cfa5c-232">版本2.124.139。0</span><span class="sxs-lookup"><span data-stu-id="cfa5c-232">Version 2.124.139.0</span></span>

<span data-ttu-id="cfa5c-233">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-233">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cfa5c-234">順暢整合的支援</span><span class="sxs-lookup"><span data-stu-id="cfa5c-234">Seamless integrated support</span></span>
- <span data-ttu-id="cfa5c-235">儲存所有測試結果</span><span class="sxs-lookup"><span data-stu-id="cfa5c-235">Save all test results</span></span>
- <span data-ttu-id="cfa5c-236">檢查影像是否已建立自訂</span><span class="sxs-lookup"><span data-stu-id="cfa5c-236">Check if the image is custom created</span></span>
- <span data-ttu-id="cfa5c-237">在裝置管理器中包含警告</span><span class="sxs-lookup"><span data-stu-id="cfa5c-237">Include warnings from device manager</span></span>
- <span data-ttu-id="cfa5c-238">Dock 固件版本</span><span class="sxs-lookup"><span data-stu-id="cfa5c-238">Dock firmware version</span></span>
- <span data-ttu-id="cfa5c-239">在儲存測試中將磁碟機標示為可能的失敗</span><span class="sxs-lookup"><span data-stu-id="cfa5c-239">Flag drives as potential failures in storage test</span></span>
- <span data-ttu-id="cfa5c-240">移除商店連結</span><span class="sxs-lookup"><span data-stu-id="cfa5c-240">Remove store link</span></span> 

### <span data-ttu-id="cfa5c-241">版本2.121.139</span><span class="sxs-lookup"><span data-stu-id="cfa5c-241">Version 2.121.139</span></span>
*<span data-ttu-id="cfa5c-242">發行日期： 31 2020 年7月</span><span class="sxs-lookup"><span data-stu-id="cfa5c-242">Release date: July 31 2020</span></span>*<br>
<span data-ttu-id="cfa5c-243">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-243">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cfa5c-244">順暢支援體驗</span><span class="sxs-lookup"><span data-stu-id="cfa5c-244">Seamless support experience</span></span>
- <span data-ttu-id="cfa5c-245">錯誤修正</span><span class="sxs-lookup"><span data-stu-id="cfa5c-245">Bug fixes</span></span>

### <span data-ttu-id="cfa5c-246">版本2.94.139。0</span><span class="sxs-lookup"><span data-stu-id="cfa5c-246">Version 2.94.139.0</span></span>
*<span data-ttu-id="cfa5c-247">發行日期：2020年5月11日</span><span class="sxs-lookup"><span data-stu-id="cfa5c-247">Release date: May 11, 2020</span></span>*<br>
<span data-ttu-id="cfa5c-248">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-248">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cfa5c-249">能夠略過 Windows Update 來執行硬體檢查。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-249">Ability to skip Windows Update to perform hardware check.</span></span>
- <span data-ttu-id="cfa5c-250">能夠接收最新版本更新的通知</span><span class="sxs-lookup"><span data-stu-id="cfa5c-250">Ability to receive notifications for about the latest version update</span></span>
- <span data-ttu-id="cfa5c-251">表面移2</span><span class="sxs-lookup"><span data-stu-id="cfa5c-251">Surface Go 2</span></span>
- <span data-ttu-id="cfa5c-252">Surface Book 3</span><span class="sxs-lookup"><span data-stu-id="cfa5c-252">Surface Book 3</span></span>
- <span data-ttu-id="cfa5c-253">顯示進度指標</span><span class="sxs-lookup"><span data-stu-id="cfa5c-253">Show progress indicator</span></span>


### <span data-ttu-id="cfa5c-254">版本2.43.139。0</span><span class="sxs-lookup"><span data-stu-id="cfa5c-254">Version 2.43.139.0</span></span>
*<span data-ttu-id="cfa5c-255">發行日期：2019年10月21日</span><span class="sxs-lookup"><span data-stu-id="cfa5c-255">Release date: October 21, 2019</span></span>*<br>
<span data-ttu-id="cfa5c-256">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-256">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span>

- <span data-ttu-id="cfa5c-257">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="cfa5c-257">Surface Pro 7</span></span>
- <span data-ttu-id="cfa5c-258">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="cfa5c-258">Surface Laptop 3</span></span>

### <span data-ttu-id="cfa5c-259">版本2.42.139。0</span><span class="sxs-lookup"><span data-stu-id="cfa5c-259">Version 2.42.139.0</span></span>
*<span data-ttu-id="cfa5c-260">發行日期：2019年9月24日</span><span class="sxs-lookup"><span data-stu-id="cfa5c-260">Release date: September 24, 2019</span></span>*<br>
<span data-ttu-id="cfa5c-261">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-261">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="cfa5c-262">下載硬體報告的能力。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-262">Ability to download hardware reports.</span></span>
- <span data-ttu-id="cfa5c-263">直接從工具直接聯繫 Microsoft 支援人員的能力。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-263">Ability to contact Microsoft Support directly from the tool.</span></span> <br>

### <span data-ttu-id="cfa5c-264">版本2.41.139。0</span><span class="sxs-lookup"><span data-stu-id="cfa5c-264">Version 2.41.139.0</span></span>
*<span data-ttu-id="cfa5c-265">發行日期：2019年6月24日</span><span class="sxs-lookup"><span data-stu-id="cfa5c-265">Release date: June 24, 2019</span></span>*<br>
<span data-ttu-id="cfa5c-266">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-266">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="cfa5c-267">記錄和報告中包含的驅動程式版本資訊。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-267">Driver version information included in logs and report.</span></span>
- <span data-ttu-id="cfa5c-268">提供關於 app 的意見反應的能力。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-268">Ability to provide feedback about the app.</span></span><br>


### <span data-ttu-id="cfa5c-269">版本2.36.139。0</span><span class="sxs-lookup"><span data-stu-id="cfa5c-269">Version 2.36.139.0</span></span>
*<span data-ttu-id="cfa5c-270">發行日期：2019年4月26日</span><span class="sxs-lookup"><span data-stu-id="cfa5c-270">Release date: April 26, 2019</span></span>*<br>
<span data-ttu-id="cfa5c-271">此版本的商業表面診斷工具組會新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="cfa5c-271">This version of Surface Diagnostic Toolkit for Business adds support for the following:</span></span> 
- <span data-ttu-id="cfa5c-272">[高級設定] 選項可透過安裝程式 UI 解除系統管理員許可權，而不需要命令列設定。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-272">Advanced Setup option to unlock admin capabilities through the installer UI, without requiring command line configuration.</span></span>
- <span data-ttu-id="cfa5c-273">協助工具增強功能。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-273">Accessibility improvements.</span></span>
- <span data-ttu-id="cfa5c-274">記錄中包含 Surface 亮度控制設定。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-274">Surface brightness control settings included in logs.</span></span>
- <span data-ttu-id="cfa5c-275">報表發生器中的外部監視器相容性支援連結。</span><span class="sxs-lookup"><span data-stu-id="cfa5c-275">External monitor compatibility support link in report generator.</span></span>
