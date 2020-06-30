---
title: Microsoft Surface Dock 固件更新-適用于 IT 系統管理員的技術資訊
description: 本文說明如何使用 Microsoft Surface Dock 固件更新來更新 Surface Dock 固件。 當您在 Surface 裝置上安裝時，它會更新連接至 Surface 裝置的任何 Surface Dock。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: aab4c67a6a262b11cd5982ebe145afbddfeaa1c9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831282"
---
# <span data-ttu-id="ca146-104">Microsoft Surface Dock 固件更新：適用于 IT 系統管理員的技術資訊</span><span class="sxs-lookup"><span data-stu-id="ca146-104">Microsoft Surface Dock Firmware Update: Technical information for IT administrators</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca146-105">本文包含適用于 IT 系統管理員的技術指示。</span><span class="sxs-lookup"><span data-stu-id="ca146-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="ca146-106">如果您是家用版使用者，請參閱如何在 Microsoft 支援網站上[更新 Surface Dock 固件](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   。</span><span class="sxs-lookup"><span data-stu-id="ca146-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="ca146-107">支援網站上的指示與下列一般安裝步驟相同，但本文有其他資訊可監視、驗證和部署到網路上的多個裝置的更新。</span><span class="sxs-lookup"><span data-stu-id="ca146-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="ca146-108">本文說明如何使用 Microsoft Surface Dock 固件更新來更新 Surface Dock 固件。</span><span class="sxs-lookup"><span data-stu-id="ca146-108">This article explains how to use Microsoft Surface Dock Firmware Update to update Surface Dock firmware.</span></span> <span data-ttu-id="ca146-109">當您在 Surface 裝置上安裝時，它會更新連接至 Surface 裝置的任何 Surface Dock。</span><span class="sxs-lookup"><span data-stu-id="ca146-109">When installed on your Surface device, it will update any Surface Dock attached to your Surface device.</span></span> 

<span data-ttu-id="ca146-110">這個工具取代舊版的 Microsoft Surface Dock 更新程式工具，先前可供下載，成為它的 Surface 工具的一部分。</span><span class="sxs-lookup"><span data-stu-id="ca146-110">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="ca146-111">舊版工具已命名為 Surface_Dock_Updater_vx.xx.xxx.x.msi （其中 x 代表版本號碼），而且不能再供下載，也不應該使用。</span><span class="sxs-lookup"><span data-stu-id="ca146-111">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <span data-ttu-id="ca146-112">安裝 Surface Dock 固件更新</span><span class="sxs-lookup"><span data-stu-id="ca146-112">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="ca146-113">本節說明如何手動安裝固件更新。</span><span class="sxs-lookup"><span data-stu-id="ca146-113">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="ca146-114">Microsoft 會定期發行新版本的 Surface Dock 固件更新。</span><span class="sxs-lookup"><span data-stu-id="ca146-114">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="ca146-115">MSI 檔案不是自我更新。</span><span class="sxs-lookup"><span data-stu-id="ca146-115">The MSI file is not self-updating.</span></span> <span data-ttu-id="ca146-116">如果您已將 MSI 部署到 Surface 裝置，且發行新版本的固件，您將需要部署新版本。</span><span class="sxs-lookup"><span data-stu-id="ca146-116">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="ca146-117">下載並安裝[Microsoft Surface Dock 固件更新](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="ca146-117">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="ca146-118">更新需要執行 Windows 10 版本1803或更新版本的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="ca146-118">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="ca146-119">安裝 MSI 檔案時，可能會提示您重新開機表面。</span><span class="sxs-lookup"><span data-stu-id="ca146-119">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="ca146-120">不過，不需要重新開機就能執行更新。</span><span class="sxs-lookup"><span data-stu-id="ca146-120">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="ca146-121">從表面固定（使用電源配接器）中斷 Surface 裝置的連接，請等候大約5秒，然後重新連接。</span><span class="sxs-lookup"><span data-stu-id="ca146-121">Disconnect your Surface device from the Surface Dock (using the power adapter), wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="ca146-122">Surface Dock 固件更新將在背景中悄悄地更新 Dock。</span><span class="sxs-lookup"><span data-stu-id="ca146-122">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="ca146-123">這個程式可能需要幾分鐘的時間才能完成，即使中斷也會繼續。</span><span class="sxs-lookup"><span data-stu-id="ca146-123">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <span data-ttu-id="ca146-124">監視 Surface Dock 固件更新</span><span class="sxs-lookup"><span data-stu-id="ca146-124">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="ca146-125">本節是選擇性的，並提供如何監視固件更新安裝的概覽。</span><span class="sxs-lookup"><span data-stu-id="ca146-125">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="ca146-126">若要監視更新：</span><span class="sxs-lookup"><span data-stu-id="ca146-126">To monitor the update:</span></span>

1. <span data-ttu-id="ca146-127">開啟事件檢視器、流覽至**Windows 記錄 > 應用程式**，然後在右側窗格的 [**動作**] 下，按一下 [**篩選目前的記錄**]，輸入**事件來源**旁邊的**SurfaceDockFwUpdate** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="ca146-127">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="ca146-128">在提升許可權的命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="ca146-128">Type the following command at an elevated command prompt:</span></span>

    ```cmd
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="ca146-129">如本文[下一節](#install-the-surface-dock-firmware-update)所述，安裝更新。</span><span class="sxs-lookup"><span data-stu-id="ca146-129">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>
4. <span data-ttu-id="ca146-130">事件2007與下列文字表示成功更新：**固件更新已完成。 hr = 0 DriverTelementry EventCode = 2007**。</span><span class="sxs-lookup"><span data-stu-id="ca146-130">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 
    - <span data-ttu-id="ca146-131">如果更新未成功，則事件 ID 2007 將會顯示為**錯誤**事件，而不是**資訊**。</span><span class="sxs-lookup"><span data-stu-id="ca146-131">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="ca146-132">此外，Windows 登錄版中報告的版本不會是最新版本。</span><span class="sxs-lookup"><span data-stu-id="ca146-132">Additionally, the version reported in the Windows Registry will not be current.</span></span>
5. <span data-ttu-id="ca146-133">更新完成後，Windows 登錄會顯示更新的 DWORD 值，與目前的工具版本相對應。</span><span class="sxs-lookup"><span data-stu-id="ca146-133">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="ca146-134">如需詳細資訊，請參閱本文的[版本參考](#versions-reference)一節。</span><span class="sxs-lookup"><span data-stu-id="ca146-134">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="ca146-135">例如：</span><span class="sxs-lookup"><span data-stu-id="ca146-135">For example:</span></span>
    - <span data-ttu-id="ca146-136">Component10CurrentFwVersion 0x04ac3970 （78395760）</span><span class="sxs-lookup"><span data-stu-id="ca146-136">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="ca146-137">Component20CurrentFwVersion 0x04915a70 （76634736）</span><span class="sxs-lookup"><span data-stu-id="ca146-137">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="ca146-138">如果您在事件文字中看到「無法找到來源 SurfaceDockFwUpdate 的事件 ID xxxx 的描述」，就表示這是預期的方式，而且可以忽略。</span><span class="sxs-lookup"><span data-stu-id="ca146-138">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="ca146-139">另請參閱本文中的下列各節：</span><span class="sxs-lookup"><span data-stu-id="ca146-139">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="ca146-140">如何驗證固件更新完成</span><span class="sxs-lookup"><span data-stu-id="ca146-140">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="ca146-141">事件記錄</span><span class="sxs-lookup"><span data-stu-id="ca146-141">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="ca146-142">疑難排解提示</span><span class="sxs-lookup"><span data-stu-id="ca146-142">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="ca146-143">版本參考</span><span class="sxs-lookup"><span data-stu-id="ca146-143">Versions reference</span></span>](#versions-reference)

## <span data-ttu-id="ca146-144">網路部署</span><span class="sxs-lookup"><span data-stu-id="ca146-144">Network deployment</span></span>

<span data-ttu-id="ca146-145">您可以使用 Windows 安裝程式命令（Msiexec.exe）來將 Surface Dock 固件更新部署到網路上的多個裝置。</span><span class="sxs-lookup"><span data-stu-id="ca146-145">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="ca146-146">使用 Microsoft 端點建構管理員或其他部署工具時，請輸入下列語法，以確保安裝為緘默：</span><span class="sxs-lookup"><span data-stu-id="ca146-146">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="ca146-147">Msiexec.exe/i \<path to msi file\> /quiet/norestart</span><span class="sxs-lookup"><span data-stu-id="ca146-147">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

  <span data-ttu-id="ca146-148">例如：</span><span class="sxs-lookup"><span data-stu-id="ca146-148">For example:</span></span>
  ```
  msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
  ```

  > [!NOTE]
  > <span data-ttu-id="ca146-149">預設不會建立記錄檔。</span><span class="sxs-lookup"><span data-stu-id="ca146-149">A log file is not created by default.</span></span> <span data-ttu-id="ca146-150">若要建立記錄檔，您需要附加 "/l*v [path]"。例如： Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI .log "</span><span class="sxs-lookup"><span data-stu-id="ca146-150">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

  <span data-ttu-id="ca146-151">如需詳細資訊，請參閱[命令列選項](https://docs.microsoft.com/windows/win32/msi/command-line-options)檔。</span><span class="sxs-lookup"><span data-stu-id="ca146-151">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca146-152">如果您想要使用任何其他方法，讓 Surface Dock 保持更新，請參閱[更新 Surface dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="ca146-152">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <span data-ttu-id="ca146-153">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="ca146-153">Intune deployment</span></span>

<span data-ttu-id="ca146-154">您可以使用 Intune 將 Surface Dock 固件更新發佈到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="ca146-154">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="ca146-155">首先，您需要將 MSI 檔案轉換成 intunewin 格式，如下列檔所述： [Intune 獨立-Win32 app 管理](https://docs.microsoft.com/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="ca146-155">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="ca146-156">使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="ca146-156">Use the following command:</span></span>
  - **<span data-ttu-id="ca146-157">msiexec/i \<path to msi file\> /quiet/q</span><span class="sxs-lookup"><span data-stu-id="ca146-157">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <span data-ttu-id="ca146-158">如何驗證固件更新已完成</span><span class="sxs-lookup"><span data-stu-id="ca146-158">How to verify completion of the firmware update</span></span>

<span data-ttu-id="ca146-159">Surface dock 固件由兩個元件組成：</span><span class="sxs-lookup"><span data-stu-id="ca146-159">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="ca146-160">**Component10：** 微控制器單元（MCU）固件</span><span class="sxs-lookup"><span data-stu-id="ca146-160">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="ca146-161">**Component20：** 顯示埠（DP）固件。</span><span class="sxs-lookup"><span data-stu-id="ca146-161">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="ca146-162">成功完成 Surface Dock 固件更新會產生這些固件元件的新登錄項值。</span><span class="sxs-lookup"><span data-stu-id="ca146-162">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="ca146-163">驗證更新：</span><span class="sxs-lookup"><span data-stu-id="ca146-163">To verify updates:</span></span>**

1. <span data-ttu-id="ca146-164">開啟 Regedit 並流覽至下列登錄路徑：</span><span class="sxs-lookup"><span data-stu-id="ca146-164">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="ca146-165">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="ca146-165">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="ca146-166">尋找登錄機碼： **Component10CurrentFwVersion 和 Component20CurrentFwVersion**，這是指目前在裝置上的固件。</span><span class="sxs-lookup"><span data-stu-id="ca146-166">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Surface Dock 固件更新安裝程式](images/regeditDock.png)

3. <span data-ttu-id="ca146-168">確認新的登錄機碼值符合本檔結尾版本參考中所列的更新登錄機碼值。</span><span class="sxs-lookup"><span data-stu-id="ca146-168">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="ca146-169">如果值相符，即已成功更新固件。</span><span class="sxs-lookup"><span data-stu-id="ca146-169">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="ca146-170">如果無法驗證，請在下一節中查看事件記錄和疑難排解秘訣。</span><span class="sxs-lookup"><span data-stu-id="ca146-170">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <span data-ttu-id="ca146-171">事件記錄</span><span class="sxs-lookup"><span data-stu-id="ca146-171">Event logging</span></span>

**<span data-ttu-id="ca146-172">表 1.</span><span class="sxs-lookup"><span data-stu-id="ca146-172">Table 1.</span></span> <span data-ttu-id="ca146-173">Surface Dock 固件更新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="ca146-173">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="ca146-174">記錄檔</span><span class="sxs-lookup"><span data-stu-id="ca146-174">Log</span></span>                              | <span data-ttu-id="ca146-175">位置</span><span class="sxs-lookup"><span data-stu-id="ca146-175">Location</span></span>                               | <span data-ttu-id="ca146-176">附註</span><span class="sxs-lookup"><span data-stu-id="ca146-176">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="ca146-177">Surface Dock 固件更新記錄</span><span class="sxs-lookup"><span data-stu-id="ca146-177">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="ca146-178">需要指定路徑（請參閱記事）</span><span class="sxs-lookup"><span data-stu-id="ca146-178">Path needs to be specified (see note)</span></span> | <span data-ttu-id="ca146-179">此工具的舊版版本會將事件寫入應用程式和服務 Logs\Microsoft Surface Dock 更新程式。</span><span class="sxs-lookup"><span data-stu-id="ca146-179">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="ca146-180">Windows 裝置安裝記錄</span><span class="sxs-lookup"><span data-stu-id="ca146-180">Windows Device Install log</span></span>       | <span data-ttu-id="ca146-181">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="ca146-181">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="ca146-182">如需使用裝置安裝記錄的詳細資訊，請參閱[SetupAPI 記錄](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-)檔。</span><span class="sxs-lookup"><span data-stu-id="ca146-182">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="ca146-183">表 2.</span><span class="sxs-lookup"><span data-stu-id="ca146-183">Table 2.</span></span> <span data-ttu-id="ca146-184">Surface Dock 固件更新的事件記錄識別碼</span><span class="sxs-lookup"><span data-stu-id="ca146-184">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="ca146-185">事件會記錄在應用程式事件日誌中。</span><span class="sxs-lookup"><span data-stu-id="ca146-185">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="ca146-186">注意：此工具的舊版版本會將事件寫入應用程式和服務 Logs\Microsoft Surface Dock 更新程式。</span><span class="sxs-lookup"><span data-stu-id="ca146-186">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="ca146-187">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="ca146-187">Event ID</span></span> | <span data-ttu-id="ca146-188">事件類型</span><span class="sxs-lookup"><span data-stu-id="ca146-188">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="ca146-189">2001</span><span class="sxs-lookup"><span data-stu-id="ca146-189">2001</span></span>     | <span data-ttu-id="ca146-190">已開始插接固件更新。</span><span class="sxs-lookup"><span data-stu-id="ca146-190">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="ca146-191">2002</span><span class="sxs-lookup"><span data-stu-id="ca146-191">2002</span></span>     | <span data-ttu-id="ca146-192">已略過 dock 固件更新，因為已已知 dock 是最新的。</span><span class="sxs-lookup"><span data-stu-id="ca146-192">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="ca146-193">2003</span><span class="sxs-lookup"><span data-stu-id="ca146-193">2003</span></span>     | <span data-ttu-id="ca146-194">Dock 固件更新無法取得固件版本。</span><span class="sxs-lookup"><span data-stu-id="ca146-194">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="ca146-195">2004</span><span class="sxs-lookup"><span data-stu-id="ca146-195">2004</span></span>     | <span data-ttu-id="ca146-196">查詢固件版本。</span><span class="sxs-lookup"><span data-stu-id="ca146-196">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="ca146-197">2005</span><span class="sxs-lookup"><span data-stu-id="ca146-197">2005</span></span>     | <span data-ttu-id="ca146-198">Dock 固件無法啟動更新。</span><span class="sxs-lookup"><span data-stu-id="ca146-198">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="ca146-199">2006</span><span class="sxs-lookup"><span data-stu-id="ca146-199">2006</span></span>     | <span data-ttu-id="ca146-200">無法傳送優惠/載荷對。</span><span class="sxs-lookup"><span data-stu-id="ca146-200">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="ca146-201">2007</span><span class="sxs-lookup"><span data-stu-id="ca146-201">2007</span></span>     | <span data-ttu-id="ca146-202">固件更新已完成。</span><span class="sxs-lookup"><span data-stu-id="ca146-202">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="ca146-203">2008</span><span class="sxs-lookup"><span data-stu-id="ca146-203">2008</span></span>     | <span data-ttu-id="ca146-204">開始停靠遙測。</span><span class="sxs-lookup"><span data-stu-id="ca146-204">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="ca146-205">2011</span><span class="sxs-lookup"><span data-stu-id="ca146-205">2011</span></span>     | <span data-ttu-id="ca146-206">結束 dock 遙測。</span><span class="sxs-lookup"><span data-stu-id="ca146-206">END dock telemetry.</span></span>                                                  |

## <span data-ttu-id="ca146-207">疑難排解提示</span><span class="sxs-lookup"><span data-stu-id="ca146-207">Troubleshooting tips</span></span>

- <span data-ttu-id="ca146-208">從交流電源完全拔下表面停靠的電源，以重設 Surface Dock。</span><span class="sxs-lookup"><span data-stu-id="ca146-208">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="ca146-209">拔下除表面固定以外的所有週邊設備。</span><span class="sxs-lookup"><span data-stu-id="ca146-209">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="ca146-210">卸載任何目前的 Surface Dock 固件更新，然後安裝最新版本。</span><span class="sxs-lookup"><span data-stu-id="ca146-210">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="ca146-211">請確定已中斷 Surface Dock 的連接，然後允許在插接的乙太網埠中，透過指示燈來完成更新，以取得足夠的時間。</span><span class="sxs-lookup"><span data-stu-id="ca146-211">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="ca146-212">等到指示燈停止閃爍之後，才能從電源拔出表面 Dock。</span><span class="sxs-lookup"><span data-stu-id="ca146-212">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="ca146-213">將表面 Dock 連接到另一個裝置，看看它能否更新 Dock。</span><span class="sxs-lookup"><span data-stu-id="ca146-213">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <span data-ttu-id="ca146-214">版本參考</span><span class="sxs-lookup"><span data-stu-id="ca146-214">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="ca146-215">安裝檔案是以下列命名格式發行： **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** （ex： Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi）並預設安裝至 C:\Program Files\SurfaceUpdate。</span><span class="sxs-lookup"><span data-stu-id="ca146-215">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <span data-ttu-id="ca146-216">版本1.42.139</span><span class="sxs-lookup"><span data-stu-id="ca146-216">Version 1.42.139</span></span> 
*<span data-ttu-id="ca146-217">發行日期： 18 2019 年9月</span><span class="sxs-lookup"><span data-stu-id="ca146-217">Release Date: September 18 2019</span></span>*

<span data-ttu-id="ca146-218">此版本（包含在 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI 中）會更新背景中的固件。</span><span class="sxs-lookup"><span data-stu-id="ca146-218">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 
**<span data-ttu-id="ca146-219">更新的登錄機碼值：</span><span class="sxs-lookup"><span data-stu-id="ca146-219">Updated registry key values:</span></span>**<br>

- <span data-ttu-id="ca146-220">Component10CurrentFwVersion 更新到**4ac3970**。</span><span class="sxs-lookup"><span data-stu-id="ca146-220">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="ca146-221">Component20CurrentFwVersion 更新到**4a1d570**。</span><span class="sxs-lookup"><span data-stu-id="ca146-221">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="ca146-222">它會新增 Surface Pro 7 和 Surface 膝上型電腦3的支援。</span><span class="sxs-lookup"><span data-stu-id="ca146-222">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <span data-ttu-id="ca146-223">舊版版本</span><span class="sxs-lookup"><span data-stu-id="ca146-223">Legacy versions</span></span>

### <span data-ttu-id="ca146-224">版本2.23.139。0</span><span class="sxs-lookup"><span data-stu-id="ca146-224">Version 2.23.139.0</span></span>
*<span data-ttu-id="ca146-225">發行日期：2018年10月10日</span><span class="sxs-lookup"><span data-stu-id="ca146-225">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="ca146-226">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="ca146-226">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="ca146-227">新增 Surface Pro 6 支援</span><span class="sxs-lookup"><span data-stu-id="ca146-227">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="ca146-228">新增對 Surface 膝上型電腦2的支援</span><span class="sxs-lookup"><span data-stu-id="ca146-228">Add support for Surface Laptop 2</span></span>


### <span data-ttu-id="ca146-229">版本2.22.139。0</span><span class="sxs-lookup"><span data-stu-id="ca146-229">Version 2.22.139.0</span></span>
*<span data-ttu-id="ca146-230">發行日期：2018年7月26日</span><span class="sxs-lookup"><span data-stu-id="ca146-230">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="ca146-231">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="ca146-231">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="ca146-232">提高更新的可靠性</span><span class="sxs-lookup"><span data-stu-id="ca146-232">Increase update reliability</span></span>
- <span data-ttu-id="ca146-233">新增 Surface Go 支援</span><span class="sxs-lookup"><span data-stu-id="ca146-233">Add support for Surface Go</span></span>

### <span data-ttu-id="ca146-234">版本 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="ca146-234">Version 2.12.136.0</span></span>
*<span data-ttu-id="ca146-235">發行日期：2018 年 1 月 29 日</span><span class="sxs-lookup"><span data-stu-id="ca146-235">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="ca146-236">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="ca146-236">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="ca146-237">適用於 Surface 擴充座主要晶片組韌體的更新</span><span class="sxs-lookup"><span data-stu-id="ca146-237">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="ca146-238">適用於 Surface 擴充座 DisplayPort 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="ca146-238">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="ca146-239">改善外部顯示器與 Surface Book 或 Surface Book 2 搭配使用時的顯示穩定性</span><span class="sxs-lookup"><span data-stu-id="ca146-239">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="ca146-240">此外，Surface Book 裝置上的這一版 Surface Dock Updater 安裝還包含：</span><span class="sxs-lookup"><span data-stu-id="ca146-240">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="ca146-241">Surface Book Base Firmware 更新</span><span class="sxs-lookup"><span data-stu-id="ca146-241">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="ca146-242">透過以 Surface Book 裝置為目標的改進功能，加入 Surface 擴充座韌體更新支援</span><span class="sxs-lookup"><span data-stu-id="ca146-242">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <span data-ttu-id="ca146-243">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="ca146-243">Version 2.9.136.0</span></span>
*<span data-ttu-id="ca146-244">發行日期︰2017 年 11 月 3 日</span><span class="sxs-lookup"><span data-stu-id="ca146-244">Release date: November 3, 2017</span></span>*

<span data-ttu-id="ca146-245">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="ca146-245">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ca146-246">適用於 Surface 擴充座 DisplayPort 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="ca146-246">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="ca146-247">解決透過被動式顯示連接埠介面卡的音訊問題</span><span class="sxs-lookup"><span data-stu-id="ca146-247">Resolves an issue with audio over passive display port adapters</span></span>

### <span data-ttu-id="ca146-248">版本 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="ca146-248">Version 2.1.15.0</span></span>
*<span data-ttu-id="ca146-249">發行日期：2017 年 6 月 19 日</span><span class="sxs-lookup"><span data-stu-id="ca146-249">Release date: June 19, 2017</span></span>*

<span data-ttu-id="ca146-250">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="ca146-250">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ca146-251">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="ca146-251">Surface Laptop</span></span>
* <span data-ttu-id="ca146-252">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="ca146-252">Surface Pro</span></span>

### <span data-ttu-id="ca146-253">版本 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="ca146-253">Version 2.1.6.0</span></span>
*<span data-ttu-id="ca146-254">發行日期︰2017 年 4 月 7 日</span><span class="sxs-lookup"><span data-stu-id="ca146-254">Release date: April 7, 2017</span></span>*

<span data-ttu-id="ca146-255">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="ca146-255">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ca146-256">適用於 Surface 擴充座 DisplayPort 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="ca146-256">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="ca146-257">需要 Windows 10</span><span class="sxs-lookup"><span data-stu-id="ca146-257">Requires Windows 10</span></span>

### <span data-ttu-id="ca146-258">版本 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="ca146-258">Version 2.0.22.0</span></span>
*<span data-ttu-id="ca146-259">發行日期︰2016 年 10 月 21 日</span><span class="sxs-lookup"><span data-stu-id="ca146-259">Release date: October 21, 2016</span></span>*

<span data-ttu-id="ca146-260">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="ca146-260">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ca146-261">適用於 Surface 擴充座 USB 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="ca146-261">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="ca146-262">已改進乙太網路、音訊和 USB 連接埠的穩定性</span><span class="sxs-lookup"><span data-stu-id="ca146-262">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <span data-ttu-id="ca146-263">版本 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="ca146-263">Version 1.0.8.0</span></span>
*<span data-ttu-id="ca146-264">發行日期︰2016 年 4 月 26 日</span><span class="sxs-lookup"><span data-stu-id="ca146-264">Release date: April 26, 2016</span></span>*

<span data-ttu-id="ca146-265">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="ca146-265">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="ca146-266">適用於 Surface 擴充座主要晶片組韌體的更新</span><span class="sxs-lookup"><span data-stu-id="ca146-266">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="ca146-267">適用於 Surface 擴充座 DisplayPort 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="ca146-267">Update for Surface Dock DisplayPort firmware</span></span>

