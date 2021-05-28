---
title: Microsoft Surface Dock 1 固件更新
description: 本文說明如何使用 Microsoft Surface Dock 固件更新來安裝和管理原始 Surface Dock 1 上的固件。 在 Surface 裝置上安裝後，它會更新連接至 Surface 裝置的 Surface Dock 1 裝置。
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
ms.date: 2/08/2021
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319207"
---
# <span data-ttu-id="4c1bc-104">Microsoft Surface Dock 固件更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-104">Microsoft Surface Dock Firmware Update</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c1bc-105">本文包含適用于 IT 系統管理員的技術指示。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-105">This article contains technical instructions for IT administrators.</span></span> <span data-ttu-id="4c1bc-106">如果您是家用版使用者，請參閱如何在 Microsoft 支援網站上[更新 Surface Dock 固件](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-106">If you are a home user, please see [How to update your Surface Dock Firmware](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) on the Microsoft Support site.</span></span> <span data-ttu-id="4c1bc-107">支援網站上的指示與下列一般安裝步驟相同，但本文有其他資訊可監視、驗證和部署到網路上的多個裝置的更新。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-107">The instructions at the support site are the same as the general installation steps below, but this article has additional information for monitoring, verifying, and deploying the update to multiple devices on a network.</span></span>

<span data-ttu-id="4c1bc-108">本文說明如何使用 Microsoft Surface Dock 固件更新來安裝和管理原始 Surface Dock 1 上的固件。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-108">This article explains how to use Microsoft Surface Dock Firmware Update to install and manage firmware on the original Surface Dock 1.</span></span> <span data-ttu-id="4c1bc-109">在 Surface 裝置上安裝後，它會更新連接至 Surface 裝置的 Surface Dock 1 裝置。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-109">When installed on your Surface device, it will update Surface Dock 1 devices attached to your Surface device.</span></span>

> [!NOTE]
> <span data-ttu-id="4c1bc-110">本文不適用於透過 Windows Update 或使用 Microsoft 端點建構管理員或其他 MSI 部署工具自動接收更新的 Surface Dock 2。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-110">This article does not apply to Surface Dock 2, which receives updates automatically via Windows Update or by using Microsoft Endpoint Configuration Manager or other MSI deployment tools.</span></span> <span data-ttu-id="4c1bc-111">若要深入瞭解，請參閱 [Surface Dock 的新增功能](surface-dock-whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-111">To learn more, see [What’s new in Surface Dock](surface-dock-whats-new.md).</span></span>

<span data-ttu-id="4c1bc-112">這個工具取代舊版的 Microsoft Surface Dock 更新程式工具，先前可供下載，成為它的 Surface 工具的一部分。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-112">This tool supersedes the earlier Microsoft Surface Dock Updater tool, previously available for download as part of Surface Tools for IT.</span></span> <span data-ttu-id="4c1bc-113">舊版工具已命名為 Surface_Dock_Updater_vx.xx.xxx.x.msi (其中 x 表示版本號碼) 且不再提供下載，因此不應使用。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-113">The earlier tool was named Surface_Dock_Updater_vx.xx.xxx.x.msi (where x indicates the version number) and is no longer available for download and should not be used.</span></span>

## <a name="install-the-surface-dock-firmware-update"></a><span data-ttu-id="4c1bc-114">安裝 Surface Dock 固件更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-114">Install the Surface Dock Firmware Update</span></span>

<span data-ttu-id="4c1bc-115">本節說明如何手動安裝固件更新。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-115">This section describes how to manually install the firmware update.</span></span>

> [!NOTE]
> <span data-ttu-id="4c1bc-116">Microsoft 會定期發行新版本的 Surface Dock 固件更新。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-116">Microsoft periodically releases new versions of Surface Dock Firmware Update.</span></span> <span data-ttu-id="4c1bc-117">MSI 檔案不是自我更新。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-117">The MSI file is not self-updating.</span></span> <span data-ttu-id="4c1bc-118">如果您已將 MSI 部署到 Surface 裝置，且發行新版本的固件，您將需要部署新版本。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-118">If you have deployed the MSI to Surface devices and a new version of the firmware is released, you will need to deploy the new version.</span></span>

1. <span data-ttu-id="4c1bc-119">下載並安裝 [Microsoft Surface Dock 固件更新](https://www.microsoft.com/download/details.aspx?id=46703)。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-119">Download and install [Microsoft Surface Dock Firmware Update](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
    - <span data-ttu-id="4c1bc-120">更新需要執行 Windows 10 版本1803或更新版本的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-120">The update requires a Surface device running Windows 10, version 1803 or later.</span></span>
    - <span data-ttu-id="4c1bc-121">安裝 MSI 檔案時，可能會提示您重新開機表面。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-121">Installing the MSI file might prompt you to restart Surface.</span></span> <span data-ttu-id="4c1bc-122">不過，不需要重新開機就能執行更新。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-122">However, restarting is not required to perform the update.</span></span>

2. <span data-ttu-id="4c1bc-123">中斷 Surface 裝置與 Surface Dock 的連接，請等候大約5秒，然後重新連接。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-123">Disconnect your Surface device from the Surface Dock, wait ~5 seconds, and then reconnect.</span></span> <span data-ttu-id="4c1bc-124">Surface Dock 固件更新將在背景中悄悄地更新 Dock。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-124">The Surface Dock Firmware Update will update the dock silently in background.</span></span> <span data-ttu-id="4c1bc-125">這個程式可能需要幾分鐘的時間才能完成，即使中斷也會繼續。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-125">The process can take a few minutes to complete and will continue even if interrupted.</span></span> 

## <a name="monitor-the-surface-dock-firmware-update"></a><span data-ttu-id="4c1bc-126">監視 Surface Dock 固件更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-126">Monitor the Surface Dock Firmware Update</span></span>

<span data-ttu-id="4c1bc-127">本節是選擇性的，並提供如何監視固件更新安裝的概覽。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-127">This section is optional and provides an overview of how to monitor installation of the firmware update.</span></span> 

<span data-ttu-id="4c1bc-128">若要監視更新：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-128">To monitor the update:</span></span>

1. <span data-ttu-id="4c1bc-129">開啟事件檢視器、流覽至**Windows 記錄 > 應用程式**，然後在右側窗格的 [**動作**] 下，按一下 [**篩選目前的記錄**]，輸入**事件來源**旁邊的**SurfaceDockFwUpdate** ，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-129">Open Event Viewer, browse to **Windows Logs > Application**, and then under **Actions** in the right-hand pane click **Filter Current Log**, enter **SurfaceDockFwUpdate** next to **Event sources**, and then click **OK**.</span></span>

2. <span data-ttu-id="4c1bc-130">在提升許可權的命令提示字元中輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-130">Type the following command at an elevated command prompt:</span></span>

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. <span data-ttu-id="4c1bc-131">如本文 [下一節](#install-the-surface-dock-firmware-update) 所述，安裝更新。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-131">Install the update as described in the [next section](#install-the-surface-dock-firmware-update) of this article.</span></span>

4. <span data-ttu-id="4c1bc-132">事件2007與下列文字表示成功更新： **固件更新已完成。 hr = 0 DriverTelementry EventCode = 2007**。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-132">Event 2007 with the following text indicates a successful update: **Firmware update finished. hr=0 DriverTelementry EventCode = 2007**.</span></span> 

   <span data-ttu-id="4c1bc-133">如果更新未成功，則事件 ID 2007 將會顯示為 **錯誤** 事件，而不是 **資訊**。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-133">If the update is not successful, then event ID 2007 will be displayed as an **Error** event rather than **Information**.</span></span> <span data-ttu-id="4c1bc-134">此外，Windows 登錄版中報告的版本不會是最新版本。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-134">Additionally, the version reported in the Windows Registry will not be current.</span></span>
   
5. <span data-ttu-id="4c1bc-135">更新完成後，Windows 登錄會顯示更新的 DWORD 值，與目前的工具版本相對應。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-135">When the update is complete, updated DWORD values will be displayed in the Windows Registry, corresponding to the current version of the tool.</span></span> <span data-ttu-id="4c1bc-136">如需詳細資訊，請參閱本文的 [版本參考](#versions-reference) 一節。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-136">See the [Versions reference](#versions-reference) section in this article for details.</span></span> <span data-ttu-id="4c1bc-137">例如：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-137">For example:</span></span>

    - <span data-ttu-id="4c1bc-138">Component10CurrentFwVersion 0x04ac3970 (78395760) </span><span class="sxs-lookup"><span data-stu-id="4c1bc-138">Component10CurrentFwVersion 0x04ac3970 (78395760)</span></span>
    - <span data-ttu-id="4c1bc-139">Component20CurrentFwVersion 0x04915a70 (76634736) </span><span class="sxs-lookup"><span data-stu-id="4c1bc-139">Component20CurrentFwVersion 0x04915a70 (76634736)</span></span>

>[!TIP]
><span data-ttu-id="4c1bc-140">如果您在事件文字中看到「無法找到來源 SurfaceDockFwUpdate 的事件 ID xxxx 的描述」，就表示這是預期的方式，而且可以忽略。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-140">If you see "The description for Event ID xxxx from source SurfaceDockFwUpdate cannot be found" in event text, this is expected and can be ignored.</span></span>

<span data-ttu-id="4c1bc-141">另請參閱本文中的下列各節：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-141">Also see the following sections in this article:</span></span> 
  - [<span data-ttu-id="4c1bc-142">如何驗證固件更新完成</span><span class="sxs-lookup"><span data-stu-id="4c1bc-142">How to verify completion of firmware update</span></span>](#how-to-verify-completion-of-the-firmware-update)
  - [<span data-ttu-id="4c1bc-143">事件記錄</span><span class="sxs-lookup"><span data-stu-id="4c1bc-143">Event logging</span></span>](#event-logging)
  - [<span data-ttu-id="4c1bc-144">疑難排解提示</span><span class="sxs-lookup"><span data-stu-id="4c1bc-144">Troubleshooting tips</span></span>](#troubleshooting-tips)
  - [<span data-ttu-id="4c1bc-145">版本參考</span><span class="sxs-lookup"><span data-stu-id="4c1bc-145">Versions reference</span></span>](#versions-reference)

## <a name="network-deployment"></a><span data-ttu-id="4c1bc-146">網路部署</span><span class="sxs-lookup"><span data-stu-id="4c1bc-146">Network deployment</span></span>

<span data-ttu-id="4c1bc-147">您可以使用 Windows 安裝程式命令 ( # A0) ，將 Surface Dock 固件更新部署到網路上的多個裝置。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-147">You can use Windows Installer commands (Msiexec.exe) to deploy Surface Dock Firmware Update to multiple devices across your network.</span></span> <span data-ttu-id="4c1bc-148">使用 Microsoft 端點建構管理員或其他部署工具時，請輸入下列語法，以確保安裝為緘默：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-148">When using Microsoft Endpoint Configuration Manager or other deployment tool, enter the following syntax to ensure the installation is silent:</span></span>

- **<span data-ttu-id="4c1bc-149">Msiexec.exe/i \<path to msi file\> /quiet/norestart</span><span class="sxs-lookup"><span data-stu-id="4c1bc-149">Msiexec.exe /i \<path to msi file\> /quiet /norestart</span></span>** 

<span data-ttu-id="4c1bc-150">例如：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-150">For example:</span></span>

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> <span data-ttu-id="4c1bc-151">預設不會建立記錄檔。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-151">A log file is not created by default.</span></span> <span data-ttu-id="4c1bc-152">若要建立記錄檔，您需要附加 "/l*v [path]"。例如： Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI .log "</span><span class="sxs-lookup"><span data-stu-id="4c1bc-152">In order to create a log file, you will need to append "/l*v [path]". For example: Msiexec.exe /i \<path to msi file\> /l*v %windir%\logs\ SurfaceDockFWI.log"</span></span>

<span data-ttu-id="4c1bc-153">如需詳細資訊，請參閱 [命令列選項](https://docs.microsoft.com/windows/win32/msi/command-line-options) 檔。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-153">For more information, refer to [Command line options](https://docs.microsoft.com/windows/win32/msi/command-line-options) documentation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c1bc-154">如果您想要使用任何其他方法，讓 Surface Dock 保持更新，請參閱 [更新 Surface dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 以取得詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-154">If you want to keep your Surface Dock updated using any other method, refer to [Update your Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) for details.</span></span>

## <a name="intune-deployment"></a><span data-ttu-id="4c1bc-155">Intune 部署</span><span class="sxs-lookup"><span data-stu-id="4c1bc-155">Intune deployment</span></span>

<span data-ttu-id="4c1bc-156">您可以使用 Intune 將 Surface Dock 固件更新發佈到您的裝置。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-156">You can use Intune to distribute Surface Dock Firmware Update to your devices.</span></span> <span data-ttu-id="4c1bc-157">首先，您需要將 MSI 檔案轉換成 intunewin 格式，如下列檔所述： [Intune 獨立-Win32 app 管理](https://docs.microsoft.com/intune/apps/apps-win32-app-management)。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-157">First you will need to convert the MSI file to the .intunewin format, as described in the following documentation: [Intune Standalone - Win32 app management](https://docs.microsoft.com/intune/apps/apps-win32-app-management).</span></span>

<span data-ttu-id="4c1bc-158">使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-158">Use the following command:</span></span>
  - **<span data-ttu-id="4c1bc-159">msiexec/i \<path to msi file\> /quiet/q</span><span class="sxs-lookup"><span data-stu-id="4c1bc-159">msiexec /i \<path to msi file\> /quiet /q</span></span>**

## <a name="how-to-verify-completion-of-the-firmware-update"></a><span data-ttu-id="4c1bc-160">如何驗證固件更新已完成</span><span class="sxs-lookup"><span data-stu-id="4c1bc-160">How to verify completion of the firmware update</span></span>

<span data-ttu-id="4c1bc-161">Surface dock 固件由兩個元件組成：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-161">Surface dock firmware consists of two components:</span></span>

- <span data-ttu-id="4c1bc-162">**Component10：** (MCU) 固件的微控制器單元</span><span class="sxs-lookup"><span data-stu-id="4c1bc-162">**Component10:** Micro controller unit (MCU) firmware</span></span>
- <span data-ttu-id="4c1bc-163">**Component20：** 顯示埠 (DP) 固件。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-163">**Component20:** Display port (DP) firmware.</span></span>

<span data-ttu-id="4c1bc-164">成功完成 Surface Dock 固件更新會產生這些固件元件的新登錄項值。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-164">Successful completion of Surface Dock Firmware Update results in new registry key values for these firmware components.</span></span>

**<span data-ttu-id="4c1bc-165">驗證更新：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-165">To verify updates:</span></span>**

1. <span data-ttu-id="4c1bc-166">開啟 Regedit 並流覽至下列登錄路徑：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-166">Open Regedit and navigate to the following registry path:</span></span>

    - **<span data-ttu-id="4c1bc-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span><span class="sxs-lookup"><span data-stu-id="4c1bc-167">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters</span></span>**

2. <span data-ttu-id="4c1bc-168">尋找登錄機碼： **Component10CurrentFwVersion 和 Component20CurrentFwVersion**，這是指目前在裝置上的固件。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-168">Look for the registry keys: **Component10CurrentFwVersion and Component20CurrentFwVersion**, which refer to the firmware that is currently on the device.</span></span>

   ![Surface Dock 固件更新安裝程式](images/regeditDock.png)

3. <span data-ttu-id="4c1bc-170">確認新的登錄機碼值符合本檔結尾版本參考中所列的更新登錄機碼值。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-170">Verify the new registry key values match the updated registry key values listed in the Versions reference at the end of this document.</span></span> <span data-ttu-id="4c1bc-171">如果值相符，即已成功更新固件。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-171">If the values match, the firmware was updated successfully.</span></span>

4. <span data-ttu-id="4c1bc-172">如果無法驗證，請在下一節中查看事件記錄和疑難排解秘訣。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-172">If unable to verify, review Event logging and Troubleshooting tips in the next section.</span></span>

## <a name="event-logging"></a><span data-ttu-id="4c1bc-173">事件記錄</span><span class="sxs-lookup"><span data-stu-id="4c1bc-173">Event logging</span></span>

**<span data-ttu-id="4c1bc-174">表 1.</span><span class="sxs-lookup"><span data-stu-id="4c1bc-174">Table 1.</span></span> <span data-ttu-id="4c1bc-175">Surface Dock 固件更新的記錄檔</span><span class="sxs-lookup"><span data-stu-id="4c1bc-175">Log files for Surface Dock Firmware Update</span></span>**

| <span data-ttu-id="4c1bc-176">記錄檔</span><span class="sxs-lookup"><span data-stu-id="4c1bc-176">Log</span></span>                              | <span data-ttu-id="4c1bc-177">Location</span><span class="sxs-lookup"><span data-stu-id="4c1bc-177">Location</span></span>                               | <span data-ttu-id="4c1bc-178">附註</span><span class="sxs-lookup"><span data-stu-id="4c1bc-178">Notes</span></span>                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="4c1bc-179">Surface Dock 固件更新記錄</span><span class="sxs-lookup"><span data-stu-id="4c1bc-179">Surface Dock Firmware Update log</span></span> | <span data-ttu-id="4c1bc-180">需要指定路徑 (請參閱記事) </span><span class="sxs-lookup"><span data-stu-id="4c1bc-180">Path needs to be specified (see note)</span></span> | <span data-ttu-id="4c1bc-181">此工具的舊版版本會將事件寫入應用程式和服務 Logs\Microsoft Surface Dock 更新程式。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-181">Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>                                                                                                  |
| <span data-ttu-id="4c1bc-182">Windows 裝置安裝記錄</span><span class="sxs-lookup"><span data-stu-id="4c1bc-182">Windows Device Install log</span></span>       | <span data-ttu-id="4c1bc-183">%windir%\inf\setupapi.dev.log</span><span class="sxs-lookup"><span data-stu-id="4c1bc-183">%windir%\inf\setupapi.dev.log</span></span>           | <span data-ttu-id="4c1bc-184">如需使用裝置安裝記錄的詳細資訊，請參閱 [SetupAPI 記錄](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) 檔。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-184">For more information about using Device Install Log, refer to [SetupAPI Logging](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) documentation.</span></span> |


**<span data-ttu-id="4c1bc-185">表 2.</span><span class="sxs-lookup"><span data-stu-id="4c1bc-185">Table 2.</span></span> <span data-ttu-id="4c1bc-186">Surface Dock 固件更新的事件記錄識別碼</span><span class="sxs-lookup"><span data-stu-id="4c1bc-186">Event log IDs for Surface Dock Firmware Update</span></span>**<br>
<span data-ttu-id="4c1bc-187">事件會記錄在應用程式事件日誌中。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-187">Events are logged in the Application Event Log.</span></span>  <span data-ttu-id="4c1bc-188">注意：此工具的舊版版本會將事件寫入應用程式和服務 Logs\Microsoft Surface Dock 更新程式。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-188">Note:  Earlier versions of this tool wrote events to Applications and Services Logs\Microsoft Surface Dock Updater.</span></span>

| <span data-ttu-id="4c1bc-189">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="4c1bc-189">Event ID</span></span> | <span data-ttu-id="4c1bc-190">事件類型</span><span class="sxs-lookup"><span data-stu-id="4c1bc-190">Event type</span></span>                                                           |
| -------- | -------------------------------------------------------------------- |
| <span data-ttu-id="4c1bc-191">2001</span><span class="sxs-lookup"><span data-stu-id="4c1bc-191">2001</span></span>     | <span data-ttu-id="4c1bc-192">已開始插接固件更新。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-192">Dock firmware update has started.</span></span>                                    |
| <span data-ttu-id="4c1bc-193">2002</span><span class="sxs-lookup"><span data-stu-id="4c1bc-193">2002</span></span>     | <span data-ttu-id="4c1bc-194">已略過 dock 固件更新，因為已已知 dock 是最新的。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-194">Dock firmware update skipped because dock is known to be up to date.</span></span> |
| <span data-ttu-id="4c1bc-195">2003</span><span class="sxs-lookup"><span data-stu-id="4c1bc-195">2003</span></span>     | <span data-ttu-id="4c1bc-196">Dock 固件更新無法取得固件版本。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-196">Dock firmware update failed to get firmware version.</span></span>                 |
| <span data-ttu-id="4c1bc-197">2004</span><span class="sxs-lookup"><span data-stu-id="4c1bc-197">2004</span></span>     | <span data-ttu-id="4c1bc-198">查詢固件版本。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-198">Querying the firmware version.</span></span>                                       |
| <span data-ttu-id="4c1bc-199">2005</span><span class="sxs-lookup"><span data-stu-id="4c1bc-199">2005</span></span>     | <span data-ttu-id="4c1bc-200">Dock 固件無法啟動更新。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-200">Dock firmware failed to start update.</span></span>                                |
| <span data-ttu-id="4c1bc-201">2006</span><span class="sxs-lookup"><span data-stu-id="4c1bc-201">2006</span></span>     | <span data-ttu-id="4c1bc-202">無法傳送優惠/載荷對。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-202">Failed to send offer/payload pairs.</span></span>                                  |
| <span data-ttu-id="4c1bc-203">2007</span><span class="sxs-lookup"><span data-stu-id="4c1bc-203">2007</span></span>     | <span data-ttu-id="4c1bc-204">固件更新已完成。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-204">Firmware update finished.</span></span>                                            |
| <span data-ttu-id="4c1bc-205">2008</span><span class="sxs-lookup"><span data-stu-id="4c1bc-205">2008</span></span>     | <span data-ttu-id="4c1bc-206">開始停靠遙測。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-206">BEGIN dock telemetry.</span></span>                                                |
| <span data-ttu-id="4c1bc-207">2011</span><span class="sxs-lookup"><span data-stu-id="4c1bc-207">2011</span></span>     | <span data-ttu-id="4c1bc-208">結束 dock 遙測。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-208">END dock telemetry.</span></span>                                                  |

## <a name="troubleshooting-tips"></a><span data-ttu-id="4c1bc-209">疑難排解提示</span><span class="sxs-lookup"><span data-stu-id="4c1bc-209">Troubleshooting tips</span></span>

- <span data-ttu-id="4c1bc-210">從交流電源完全拔下表面停靠的電源，以重設 Surface Dock。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-210">Completely disconnect power for Surface dock from the AC power to reset the Surface Dock.</span></span>
- <span data-ttu-id="4c1bc-211">拔下除表面固定以外的所有週邊設備。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-211">Disconnect all peripherals except for the Surface Dock.</span></span>
- <span data-ttu-id="4c1bc-212">卸載任何目前的 Surface Dock 固件更新，然後安裝最新版本。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-212">Uninstall any current Surface Dock Firmware Update and then install the latest version.</span></span>
- <span data-ttu-id="4c1bc-213">請確定已中斷 Surface Dock 的連接，然後允許在插接的乙太網埠中，透過指示燈來完成更新，以取得足夠的時間。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-213">Ensure that the Surface Dock is disconnected, and then allow enough time for the update to complete as monitored via an LED in the Ethernet port of the dock.</span></span> <span data-ttu-id="4c1bc-214">等到指示燈停止閃爍之後，才能從電源拔出表面 Dock。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-214">Wait until the LED stops blinking before you unplug Surface Dock from power.</span></span>
- <span data-ttu-id="4c1bc-215">將表面 Dock 連接到另一個裝置，看看它能否更新 Dock。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-215">Connect the Surface Dock to a different device to see if it is able to update the dock.</span></span>

## <a name="versions-reference"></a><span data-ttu-id="4c1bc-216">版本參考</span><span class="sxs-lookup"><span data-stu-id="4c1bc-216">Versions reference</span></span>

>[!NOTE]
><span data-ttu-id="4c1bc-217">安裝檔案是以下列命名格式發行： **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex： Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 並預設安裝至 C:\Program Files\SurfaceUpdate。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-217">The installation file is released with the following naming format: **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex: Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) and installs by default to C:\Program Files\SurfaceUpdate.</span></span>

### <a name="version-1.53.139.0"></a><span data-ttu-id="4c1bc-218">版本1.53.139。0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-218">Version 1.53.139.0</span></span>
*<span data-ttu-id="4c1bc-219">發行日期：2020年8月4日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-219">Release Date: August 4, 2020</span></span>*

<span data-ttu-id="4c1bc-220">此版本的 Surface Dock 固件更新包含錯誤修正及支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-220">This version of Surface Dock Firmware Update includes bug fixes and support for:</span></span>
- <span data-ttu-id="4c1bc-221">使用 Surface Pro X 更新 Surface Dock 1。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-221">Updating Surface Dock 1 using Surface Pro X.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="4c1bc-222">如果您正在執行 Surface Pro X，請下載。ARM64 組建。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-222">If you're running Surface Pro X, download the .ARM64 build.</span></span> <span data-ttu-id="4c1bc-223">針對所有其他裝置，請使用 AMD64 組建。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-223">For all other devices, use the AMD64 build.</span></span> 

#### <span data-ttu-id="4c1bc-224">登錄機碼值</span><span class="sxs-lookup"><span data-stu-id="4c1bc-224">Registry key values</span></span>

<span data-ttu-id="4c1bc-225">指示固件更新狀態的登錄值不會與舊版此工具保持相同：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-225">The registry values that indicate the status of firmware updates are unchanged from the previous version of this tool:</span></span> 

- <span data-ttu-id="4c1bc-226">Component10CurrentFwVersion 更新到 **4ac3970**。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-226">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="4c1bc-227">Component20CurrentFwVersion 更新到 **4a1d570**。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-227">Component20CurrentFwVersion updated to **4a1d570**.</span></span>
 
### <a name="version-1.42.139"></a><span data-ttu-id="4c1bc-228">版本1.42.139</span><span class="sxs-lookup"><span data-stu-id="4c1bc-228">Version 1.42.139</span></span> 
*<span data-ttu-id="4c1bc-229">發行日期： 18 2019 年9月</span><span class="sxs-lookup"><span data-stu-id="4c1bc-229">Release Date: September 18 2019</span></span>*

<span data-ttu-id="4c1bc-230">此版本（包含在 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI 中）會更新背景中的固件。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-230">This version, contained in Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI, updates firmware in the background.</span></span> 

#### <span data-ttu-id="4c1bc-231">更新的登錄機碼值</span><span class="sxs-lookup"><span data-stu-id="4c1bc-231">Updated registry key values</span></span>

- <span data-ttu-id="4c1bc-232">Component10CurrentFwVersion 更新到 **4ac3970**。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-232">Component10CurrentFwVersion updated to **4ac3970**.</span></span>
- <span data-ttu-id="4c1bc-233">Component20CurrentFwVersion 更新到 **4a1d570**。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-233">Component20CurrentFwVersion updated to **4a1d570**.</span></span>

<span data-ttu-id="4c1bc-234">它會新增 Surface Pro 7 和 Surface 膝上型電腦3的支援。</span><span class="sxs-lookup"><span data-stu-id="4c1bc-234">It adds support for Surface Pro 7 and Surface Laptop 3.</span></span>

## <a name="legacy-versions"></a><span data-ttu-id="4c1bc-235">舊版版本</span><span class="sxs-lookup"><span data-stu-id="4c1bc-235">Legacy versions</span></span>

### <a name="version-2.23.139.0"></a><span data-ttu-id="4c1bc-236">版本2.23.139。0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-236">Version 2.23.139.0</span></span>
*<span data-ttu-id="4c1bc-237">發行日期：2018年10月10日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-237">Release Date: 10 October 2018</span></span>*

<span data-ttu-id="4c1bc-238">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-238">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="4c1bc-239">新增 Surface Pro 6 支援</span><span class="sxs-lookup"><span data-stu-id="4c1bc-239">Add support for Surface Pro 6</span></span>
- <span data-ttu-id="4c1bc-240">新增對 Surface 膝上型電腦2的支援</span><span class="sxs-lookup"><span data-stu-id="4c1bc-240">Add support for Surface Laptop 2</span></span>


### <a name="version-2.22.139.0"></a><span data-ttu-id="4c1bc-241">版本2.22.139。0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-241">Version 2.22.139.0</span></span>
*<span data-ttu-id="4c1bc-242">發行日期：2018年7月26日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-242">Release Date: 26 July 2018</span></span>*

<span data-ttu-id="4c1bc-243">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-243">This version of Surface Dock Updater adds support for the following:</span></span>

- <span data-ttu-id="4c1bc-244">提高更新的可靠性</span><span class="sxs-lookup"><span data-stu-id="4c1bc-244">Increase update reliability</span></span>
- <span data-ttu-id="4c1bc-245">新增 Surface Go 支援</span><span class="sxs-lookup"><span data-stu-id="4c1bc-245">Add support for Surface Go</span></span>

### <a name="version-2.12.136.0"></a><span data-ttu-id="4c1bc-246">版本 2.12.136.0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-246">Version 2.12.136.0</span></span>
*<span data-ttu-id="4c1bc-247">發行日期：2018 年 1 月 29 日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-247">Release Date: 29 January 2018</span></span>*

<span data-ttu-id="4c1bc-248">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-248">This version of Surface Dock Updater adds support for the following:</span></span>
* <span data-ttu-id="4c1bc-249">適用於 Surface 擴充座主要晶片組韌體的更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-249">Update for Surface Dock Main Chipset Firmware</span></span>
* <span data-ttu-id="4c1bc-250">適用於 Surface 擴充座 DisplayPort 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-250">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="4c1bc-251">改善外部顯示器與 Surface Book 或 Surface Book 2 搭配使用時的顯示穩定性</span><span class="sxs-lookup"><span data-stu-id="4c1bc-251">Improved display stability for external displays when used with Surface Book or Surface Book 2</span></span>

<span data-ttu-id="4c1bc-252">此外，Surface Book 裝置上的這一版 Surface Dock Updater 安裝還包含：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-252">Additionally, installation of this version of Surface Dock Updater on Surface Book devices includes the following:</span></span>
* <span data-ttu-id="4c1bc-253">Surface Book Base Firmware 更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-253">Update for Surface Book Base Firmware</span></span>
* <span data-ttu-id="4c1bc-254">透過以 Surface Book 裝置為目標的改進功能，加入 Surface 擴充座韌體更新支援</span><span class="sxs-lookup"><span data-stu-id="4c1bc-254">Added support for Surface Dock firmware updates with improvements targeted to Surface Book devices</span></span>


### <a name="version-2.9.136.0"></a><span data-ttu-id="4c1bc-255">版本 2.9.136.0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-255">Version 2.9.136.0</span></span>
*<span data-ttu-id="4c1bc-256">發行日期︰2017 年 11 月 3 日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-256">Release date: November 3, 2017</span></span>*

<span data-ttu-id="4c1bc-257">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-257">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="4c1bc-258">適用於 Surface 擴充座 DisplayPort 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-258">Update for Surface Dock DisplayPort Firmware</span></span>
* <span data-ttu-id="4c1bc-259">解決透過被動式顯示連接埠介面卡的音訊問題</span><span class="sxs-lookup"><span data-stu-id="4c1bc-259">Resolves an issue with audio over passive display port adapters</span></span>

### <a name="version-2.1.15.0"></a><span data-ttu-id="4c1bc-260">版本 2.1.15.0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-260">Version 2.1.15.0</span></span>
*<span data-ttu-id="4c1bc-261">發行日期：2017 年 6 月 19 日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-261">Release date: June 19, 2017</span></span>*

<span data-ttu-id="4c1bc-262">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-262">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="4c1bc-263">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="4c1bc-263">Surface Laptop</span></span>
* <span data-ttu-id="4c1bc-264">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="4c1bc-264">Surface Pro</span></span>

### <a name="version-2.1.6.0"></a><span data-ttu-id="4c1bc-265">版本 2.1.6.0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-265">Version 2.1.6.0</span></span>
*<span data-ttu-id="4c1bc-266">發行日期︰2017 年 4 月 7 日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-266">Release date: April 7, 2017</span></span>*

<span data-ttu-id="4c1bc-267">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-267">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="4c1bc-268">適用於 Surface 擴充座 DisplayPort 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-268">Update for Surface Dock DisplayPort firmware</span></span>
* <span data-ttu-id="4c1bc-269">需要 Windows 10</span><span class="sxs-lookup"><span data-stu-id="4c1bc-269">Requires Windows 10</span></span>

### <a name="version-2.0.22.0"></a><span data-ttu-id="4c1bc-270">版本 2.0.22.0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-270">Version 2.0.22.0</span></span>
*<span data-ttu-id="4c1bc-271">發行日期︰2016 年 10 月 21 日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-271">Release date: October 21, 2016</span></span>*

<span data-ttu-id="4c1bc-272">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-272">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="4c1bc-273">適用於 Surface 擴充座 USB 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-273">Update for Surface Dock USB firmware</span></span>
* <span data-ttu-id="4c1bc-274">已改進乙太網路、音訊和 USB 連接埠的穩定性</span><span class="sxs-lookup"><span data-stu-id="4c1bc-274">Improved reliability of Ethernet, audio, and USB ports</span></span>

### <a name="version-1.0.8.0"></a><span data-ttu-id="4c1bc-275">版本 1.0.8.0</span><span class="sxs-lookup"><span data-stu-id="4c1bc-275">Version 1.0.8.0</span></span>
*<span data-ttu-id="4c1bc-276">發行日期︰2016 年 4 月 26 日</span><span class="sxs-lookup"><span data-stu-id="4c1bc-276">Release date: April 26, 2016</span></span>*

<span data-ttu-id="4c1bc-277">此版本的 Surface Dock Updater 新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="4c1bc-277">This version of Surface Dock Updater adds support for the following:</span></span>

* <span data-ttu-id="4c1bc-278">適用於 Surface 擴充座主要晶片組韌體的更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-278">Update for Surface Dock Main Chipset firmware</span></span>
* <span data-ttu-id="4c1bc-279">適用於 Surface 擴充座 DisplayPort 韌體的更新</span><span class="sxs-lookup"><span data-stu-id="4c1bc-279">Update for Surface Dock DisplayPort firmware</span></span>

