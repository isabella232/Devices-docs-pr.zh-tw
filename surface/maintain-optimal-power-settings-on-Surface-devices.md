---
title: Surface 裝置的最佳做法電源設定
description: 本主題提供維護最佳電源設定的最佳做法建議，並說明 Surface 如何簡化電源管理體驗。 本文適用于所有目前支援的 Surface 裝置，包括 Surface Pro 7、Surface Pro X 及 Surface 膝上型電腦3。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2019
ms.openlocfilehash: 73a74dc05a5a6929fa6360e04aac5d342b9c06a8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831289"
---
# <span data-ttu-id="15acb-104">Surface 裝置的最佳做法電源設定</span><span class="sxs-lookup"><span data-stu-id="15acb-104">Best practice power settings for Surface devices</span></span>

<span data-ttu-id="15acb-105">Surface 裝置的設計目的是充分利用行動裝置能源消耗中的最新進步，以提供跨工作負載優化的簡化體驗。</span><span class="sxs-lookup"><span data-stu-id="15acb-105">Surface devices are designed to take advantage of the latest advances in mobile device energy consumption to deliver a streamlined experience optimized across workloads.</span></span> <span data-ttu-id="15acb-106">視您所執行的動作而定，Surface 會以動態方式來調整如何將電源流向個別的硬體元件，暫時是為了處理背景工作（例如內送電子郵件或網路流量），在返回低能量空閒狀態（S0ix）之前。</span><span class="sxs-lookup"><span data-stu-id="15acb-106">Depending on what you’re doing, Surface dynamically fine tunes how power flows to individual hardware components, momentarily waking up system components to handle background tasks -- such as an incoming email or network traffic -- before returning to a low power idle state (S0ix).</span></span>

## <span data-ttu-id="15acb-107">IT 系統管理員建議摘要</span><span class="sxs-lookup"><span data-stu-id="15acb-107">Summary of recommendations for IT administrators</span></span>

<span data-ttu-id="15acb-108">為了確保整個組織的 Surface 裝置能充分享受 Surface 電源優化功能的好處：</span><span class="sxs-lookup"><span data-stu-id="15acb-108">To ensure Surface devices across your organization fully benefit from Surface power optimization features:</span></span>

-  <span data-ttu-id="15acb-109">從 Windows Update 或 Surface 驅動程式和固件 MSI 安裝最新的驅動程式和固件。</span><span class="sxs-lookup"><span data-stu-id="15acb-109">Install the latest  drivers and firmware from Windows Update or the Surface Driver and Firmware MSI.</span></span> <span data-ttu-id="15acb-110">這會根據預設建立平衡電源配置（亦即電源設定檔），並設定最佳電源設定。</span><span class="sxs-lookup"><span data-stu-id="15acb-110">This creates the balanced power plan (aka power profile) by default and configures optimal power settings.</span></span>  <span data-ttu-id="15acb-111">如需詳細資訊，請參閱[管理和部署 Surface 驅動程式和固件更新](manage-surface-driver-and-firmware-updates.md)。</span><span class="sxs-lookup"><span data-stu-id="15acb-111">For more information, refer to [Manage and deploy Surface driver and firmware updates](manage-surface-driver-and-firmware-updates.md).</span></span>
- <span data-ttu-id="15acb-112">避免建立自訂的 power 個人檔案或調整 [預設 UI] （**系統**  >  **power & 睡眠**）中不可見的 [高級電源] 設定。</span><span class="sxs-lookup"><span data-stu-id="15acb-112">Avoid creating custom power profiles or adjusting advanced power settings not visible in the default UI  (**System** > **Power & sleep**).</span></span>
- <span data-ttu-id="15acb-113">如果您必須在網路上管理裝置的電源設定檔（例如在高度管理的組織中），請使用 powercfg 命令工具，從 Surface 裝置的工廠影像匯出電源配置，然後將其匯入到 Surface 裝置的置備套件中。</span><span class="sxs-lookup"><span data-stu-id="15acb-113">If you must manage the power profile of devices across your network (such as in highly managed organizations), use the powercfg command tool to export the power plan from the factory image of the Surface device and then import it into the provisioning package for your Surface devices.</span></span> 

    >[!NOTE]
    ><span data-ttu-id="15acb-114">您只能在相同類型的 Surface 裝置上匯出電源配置。</span><span class="sxs-lookup"><span data-stu-id="15acb-114">You can only export a power plan across the same type of Surface device.</span></span>  <span data-ttu-id="15acb-115">例如，您無法從 Surface 膝上型電腦匯出電源配置，並將其匯入 Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="15acb-115">For example, you cannot export a power plan from Surface Laptop and import it on Surface Pro.</span></span>  <span data-ttu-id="15acb-116">如需詳細資訊，請參閱[設定電源設定](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings)。</span><span class="sxs-lookup"><span data-stu-id="15acb-116">For more information, refer to [Configure power settings](https://docs.microsoft.com/windows-hardware/customize/power-settings/configure-power-settings).</span></span>

- <span data-ttu-id="15acb-117">從任何現有的電源管理原則設定中排除 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="15acb-117">Exclude Surface devices from any existing power management policy settings.</span></span> 

## <span data-ttu-id="15acb-118">背景</span><span class="sxs-lookup"><span data-stu-id="15acb-118">Background</span></span>

<span data-ttu-id="15acb-119">表面實現電源管理的方式與較舊的 OS 標準（透過一系列睡眠狀態逐漸減少及關閉電源）有顯著差異;例如，迴圈執行 S1、S2、S3 等。</span><span class="sxs-lookup"><span data-stu-id="15acb-119">The way Surface implements power management differs significantly from the earlier OS standard that gradually reduces and turns off power via a series of sleep states; for example, cycling through S1, S2, S3, and so on.</span></span>

<span data-ttu-id="15acb-120">相反地，Surface 是使用自訂的 power profile 來取代舊版睡眠及能源消耗功能與新式待機功能以及動態微調。</span><span class="sxs-lookup"><span data-stu-id="15acb-120">Instead, Surface is imaged with a custom power profile that replaces legacy sleep and energy consumption functionality with modern standby features and dynamic fine tuning.</span></span> <span data-ttu-id="15acb-121">此自訂電源設定檔是透過 Surface 串列中樞驅動程式和系統聚合器模組（SAM）來實現。</span><span class="sxs-lookup"><span data-stu-id="15acb-121">This custom power profile is implemented via the Surface Serial Hub Driver and the system aggregator module (SAM).</span></span> <span data-ttu-id="15acb-122">SAM 晶片會充當 Surface 裝置電源原則擁有者，使用演算法來計算最佳電源需求。</span><span class="sxs-lookup"><span data-stu-id="15acb-122">The SAM chip functions as the Surface device power-policy owner, using algorithms to calculate optimal power requirements.</span></span> <span data-ttu-id="15acb-123">它與 Windows power manager 搭配使用，只可用於指派或限制硬體元件正常運作所需的實際功率量。</span><span class="sxs-lookup"><span data-stu-id="15acb-123">It works in conjunction with Windows power manager to allocate or throttle only the exact amount of power required for hardware components to function.</span></span> <span data-ttu-id="15acb-124">本文適用于所有目前支援的 Surface 裝置，包括 Surface Pro 7、Surface Pro X 及 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="15acb-124">This article applies to all currently supported Surface devices including Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span>

## <span data-ttu-id="15acb-125">在 Surface 中利用自訂電源設定檔</span><span class="sxs-lookup"><span data-stu-id="15acb-125">Utilizing the custom power profile in Surface</span></span>

<span data-ttu-id="15acb-126">如果您進入 surface 裝置上的 [電源] 選項，您會看到單一電源配置可供使用。</span><span class="sxs-lookup"><span data-stu-id="15acb-126">If you go into the power options on a  surface device, you'll see that there's a single power plan available.</span></span> <span data-ttu-id="15acb-127">此為自訂電源設定檔。</span><span class="sxs-lookup"><span data-stu-id="15acb-127">This is the custom power profile.</span></span> <span data-ttu-id="15acb-128">而且，如果您移至 [高級電源設定]，就會看到一個較小的 [電源選項] 子集，與執行 Windows 10 的一般電腦相比。</span><span class="sxs-lookup"><span data-stu-id="15acb-128">And if you go to the advanced power settings, you’ll see a much smaller subset of power options compared to a generic PC running Windows 10.</span></span> <span data-ttu-id="15acb-129">與一般裝置不同，Surface 具有固件與自訂群組件，可用於管理這些電源選項。</span><span class="sxs-lookup"><span data-stu-id="15acb-129">Unlike generic devices, Surface has firmware and custom components to manage these power options.</span></span>


## <span data-ttu-id="15acb-130">新式待機</span><span class="sxs-lookup"><span data-stu-id="15acb-130">Modern Standby</span></span>

<span data-ttu-id="15acb-131">Algorithmically 內嵌的自訂電源設定檔可針對智慧手機的一般即時/立即關閉功能維持低功耗，以啟用 Surface 的新式待機連接。</span><span class="sxs-lookup"><span data-stu-id="15acb-131">The algorithmically embedded custom power profile enables modern standby connectivity for Surface by maintaining a low power state for instant on/instant off functionality typical of smartphones.</span></span> <span data-ttu-id="15acb-132">S0ix （也稱為最深的執行時間空閒平臺狀態（DRIPS））是 Surface 裝置的預設電源模式。</span><span class="sxs-lookup"><span data-stu-id="15acb-132">S0ix, also known as Deepest Runtime Idle Platform State (DRIPS), is the default power mode for Surface devices.</span></span> <span data-ttu-id="15acb-133">新式待機有兩種模式：</span><span class="sxs-lookup"><span data-stu-id="15acb-133">Modern standby has two modes:</span></span>

- **<span data-ttu-id="15acb-134">已連線的待機模式。</span><span class="sxs-lookup"><span data-stu-id="15acb-134">Connected standby.</span></span>** <span data-ttu-id="15acb-135">傳送電子郵件、訊息及雲端同步處理資料的預設模式，已連接的待機會保持 Wi-fi 開啟，並維持網路連線能力。</span><span class="sxs-lookup"><span data-stu-id="15acb-135">The default mode for up-to-the minute delivery of emails, messaging, and cloud-synced data, connected standby keeps Wi-Fi on and maintains network connectivity.</span></span>

- **<span data-ttu-id="15acb-136">已中斷連線。</span><span class="sxs-lookup"><span data-stu-id="15acb-136">Disconnected standby.</span></span>** <span data-ttu-id="15acb-137">延長電池使用時間的選用模式，斷開的待機會提供相同的暫態體驗，並可關閉 Wi-fi、藍牙及相關的網路連線來省電。</span><span class="sxs-lookup"><span data-stu-id="15acb-137">An optional mode for extended battery life, disconnected standby delivers the same instant-on experience and saves power by turning off Wi-Fi, Bluetooth, and related network connectivity.</span></span>

<span data-ttu-id="15acb-138">若要深入瞭解新式待機，請參閱[Microsoft 硬體開發人員中心](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)。</span><span class="sxs-lookup"><span data-stu-id="15acb-138">To learn more about modern standby, refer to the [Microsoft Hardware Dev Center](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources).</span></span>

## <span data-ttu-id="15acb-139">表面如何簡化電源管理體驗</span><span class="sxs-lookup"><span data-stu-id="15acb-139">How Surface streamlines the power management experience</span></span> 

<span data-ttu-id="15acb-140">表面整合了下列功能，可協助使用者優化電源管理體驗：</span><span class="sxs-lookup"><span data-stu-id="15acb-140">Surface integrates the following features designed to help users optimize the power management experience:</span></span>

- [<span data-ttu-id="15acb-141">單數電源配置</span><span class="sxs-lookup"><span data-stu-id="15acb-141">Singular power plan</span></span>](#singular-power-plan)

- [<span data-ttu-id="15acb-142">簡化的電源設定使用者介面</span><span class="sxs-lookup"><span data-stu-id="15acb-142">Simplified power settings user interface</span></span>](#simplified-power-settings-user-interface)

- [<span data-ttu-id="15acb-143">Windows 效能電源滑杆</span><span class="sxs-lookup"><span data-stu-id="15acb-143">Windows performance power slider</span></span>](#windows-performance-power-slider)

### <span data-ttu-id="15acb-144">單數電源配置</span><span class="sxs-lookup"><span data-stu-id="15acb-144">Singular power plan</span></span>

<span data-ttu-id="15acb-145">Surface 專為簡化的電源管理體驗而設計，無需建立自訂電源配置或手動設定電源設定。</span><span class="sxs-lookup"><span data-stu-id="15acb-145">Surface is designed for a streamlined power management experience that eliminates the need to create custom power plans or manually configure power settings.</span></span> <span data-ttu-id="15acb-146">Microsoft 提供單一電源配置（已平衡）來取代標準 Windows 組建的多個電源配置，以簡化使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="15acb-146">Microsoft streamlines the user experience by delivering a single power plan (balanced) that replaces the multiple power plans from standard Windows builds.</span></span>

### <span data-ttu-id="15acb-147">簡化的電源設定使用者介面</span><span class="sxs-lookup"><span data-stu-id="15acb-147">Simplified power settings user interface</span></span>

<span data-ttu-id="15acb-148">Surface 提供簡化的 UI，以符合最佳做法電源設定建議。</span><span class="sxs-lookup"><span data-stu-id="15acb-148">Surface provides a simplified UI in accord with best practice power setting recommendations.</span></span> <span data-ttu-id="15acb-149">一般來說，建議您只調整預設使用者介面中顯示的設定，避免設定 [高級電源設定] 或 [群組原則] 設定。</span><span class="sxs-lookup"><span data-stu-id="15acb-149">In general, it's recommended to only adjust settings visible in the default user interface and avoid configuring advanced power settings or Group Policy settings.</span></span> <span data-ttu-id="15acb-150">使用預設的螢幕和睡眠超時，同時避免最大的亮度層級，是使用者保持延長電池使用時間的最有效方式。</span><span class="sxs-lookup"><span data-stu-id="15acb-150">Using the default screen and sleep timeouts while avoiding maximum brightness levels are the most effective ways for users to maintain extended battery life.</span></span>

![圖 1。](images/powerintrofig1.png)

<span data-ttu-id="15acb-153">圖 1。</span><span class="sxs-lookup"><span data-stu-id="15acb-153">Figure 1.</span></span> <span data-ttu-id="15acb-154">已簡化電源和睡眠設定</span><span class="sxs-lookup"><span data-stu-id="15acb-154">Simplified power and sleep settings</span></span>

### <span data-ttu-id="15acb-155">Windows 效能電源滑杆</span><span class="sxs-lookup"><span data-stu-id="15acb-155">Windows performance power slider</span></span>

<span data-ttu-id="15acb-156">執行 Windows 10 組建1709及更新版本的 Surface 裝置包含一個電源滑杆，可讓您在需要時排定電池使用時間優先順序，或視需要使用的效能。</span><span class="sxs-lookup"><span data-stu-id="15acb-156">Surface devices running Windows 10 build 1709 and later include a power slider allowing you to prioritize battery life when needed or favor performance if desired.</span></span> <span data-ttu-id="15acb-157">您可以按一下 [電池] 圖示，從工作列存取 [電源] 滑杆。</span><span class="sxs-lookup"><span data-stu-id="15acb-157">You can access the power slider from the taskbar by clicking on the battery icon.</span></span> <span data-ttu-id="15acb-158">向左滑動以延長電池使用時間（節電模式），或滑動以取得更高的效能。</span><span class="sxs-lookup"><span data-stu-id="15acb-158">Slide left for longer battery life (battery saver mode) or slide right for faster performance.</span></span>

![圖 2.](images/powerintrofig2a.png)

<span data-ttu-id="15acb-161">圖 2.</span><span class="sxs-lookup"><span data-stu-id="15acb-161">Figure 2.</span></span> <span data-ttu-id="15acb-162">[電源] 滑杆</span><span class="sxs-lookup"><span data-stu-id="15acb-162">Power slider</span></span>

<span data-ttu-id="15acb-163">[電源] 滑杆支援四種狀態，如下表所述：</span><span class="sxs-lookup"><span data-stu-id="15acb-163">Power slider enables four states as described in the following table:</span></span>

| <span data-ttu-id="15acb-164">滑杆模式</span><span class="sxs-lookup"><span data-stu-id="15acb-164">Slider mode</span></span>| <span data-ttu-id="15acb-165">描述</span><span class="sxs-lookup"><span data-stu-id="15acb-165">Description</span></span> |
|---|---|
| <span data-ttu-id="15acb-166">省電模式</span><span class="sxs-lookup"><span data-stu-id="15acb-166">Battery saver</span></span>| <span data-ttu-id="15acb-167">當系統斷開與電源的連線時，可協助省電並延長電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="15acb-167">Helps conserve power and prolong battery life when the system is disconnected from a power source.</span></span> <span data-ttu-id="15acb-168">當節電模式開啟時，部分 Windows 功能會停用、受到限制或行為不同。</span><span class="sxs-lookup"><span data-stu-id="15acb-168">When battery saver is on, some Windows features are disabled, throttled, or behave differently.</span></span> <span data-ttu-id="15acb-169">畫面亮度也會減少。</span><span class="sxs-lookup"><span data-stu-id="15acb-169">Screen brightness is also reduced.</span></span> <span data-ttu-id="15acb-170">節電模式只能在使用電池電源（DC）時使用。</span><span class="sxs-lookup"><span data-stu-id="15acb-170">Battery saver is only available when using battery power (DC).</span></span> <span data-ttu-id="15acb-171">若要深入瞭解，請參閱[節電](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)模式。</span><span class="sxs-lookup"><span data-stu-id="15acb-171">To learn more, see [Battery Saver](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver).</span></span>|
| <span data-ttu-id="15acb-172">建議執行</span><span class="sxs-lookup"><span data-stu-id="15acb-172">Recommended</span></span> | <span data-ttu-id="15acb-173">比舊版 Windows 的預設設定提供更長的電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="15acb-173">Delivers longer battery life than the default settings in earlier versions of Windows.</span></span> |
| <span data-ttu-id="15acb-174">效能更佳</span><span class="sxs-lookup"><span data-stu-id="15acb-174">Better Performance</span></span> | <span data-ttu-id="15acb-175">在電池使用時間上稍有優先表現，以預設滑杆模式運作。</span><span class="sxs-lookup"><span data-stu-id="15acb-175">Slightly favors performance over battery life, functioning as the default slider mode.</span></span> |
| <span data-ttu-id="15acb-176">最佳效能</span><span class="sxs-lookup"><span data-stu-id="15acb-176">Best Performance</span></span> | <span data-ttu-id="15acb-177">針對需要最佳效能與回應性的工作負載來提高效能，而不管電池功耗為何。</span><span class="sxs-lookup"><span data-stu-id="15acb-177">Favors performance over power for workloads requiring maximum performance and responsiveness, regardless of battery power consumption.</span></span>|

<span data-ttu-id="15acb-178">[電源] 滑杆模式會直接控制下表中顯示的特定硬體元件。</span><span class="sxs-lookup"><span data-stu-id="15acb-178">Power slider modes directly control specific hardware components shown in the following table.</span></span>

| <span data-ttu-id="15acb-179">元件</span><span class="sxs-lookup"><span data-stu-id="15acb-179">Component</span></span> | <span data-ttu-id="15acb-180">滑杆功能</span><span class="sxs-lookup"><span data-stu-id="15acb-180">Slider functionality</span></span> |
|---|---|
| <span data-ttu-id="15acb-181">英特爾快速移（CPU 能源寄存器）和能源效能喜好設定提示。</span><span class="sxs-lookup"><span data-stu-id="15acb-181">Intel Speed Shift (CPU energy registers) and Energy Performance Preference hint.</span></span> | <span data-ttu-id="15acb-182">針對最佳效能和功率選取最佳的運作頻率和電壓。</span><span class="sxs-lookup"><span data-stu-id="15acb-182">Selects the best operating frequency and voltage for optimal performance and power.</span></span> <span data-ttu-id="15acb-183">能源效能喜好設定（PERFEPP）是 CPU 的全域電源效率提示。</span><span class="sxs-lookup"><span data-stu-id="15acb-183">The Energy Performance Preference (PERFEPP) is a global power efficiency hint to the CPU.</span></span> |
| <span data-ttu-id="15acb-184">風扇速度（RPM）</span><span class="sxs-lookup"><span data-stu-id="15acb-184">Fan speed (RPM)</span></span>| <span data-ttu-id="15acb-185">如果適用的話，會調整變更的條件，例如，將風扇保持在節電式滑杆模式中。</span><span class="sxs-lookup"><span data-stu-id="15acb-185">Where applicable, adjusts for changing conditions such as keeping fan silent in battery saver slider mode.</span></span>|
| <span data-ttu-id="15acb-186">處理器套件電源限制（PL1/PL2）。</span><span class="sxs-lookup"><span data-stu-id="15acb-186">Processor package power limits (PL1/PL2).</span></span>| <span data-ttu-id="15acb-187">需要 CPU 管理其頻率選項，以適應穩定狀態（PL1）和 turbo （PL2）工作負載的平均功率限制。</span><span class="sxs-lookup"><span data-stu-id="15acb-187">Requires the CPU to manage its frequency choices to accommodate a running average power limit for both steady state (PL1) and turbo (PL2) workloads.</span></span>|
| <span data-ttu-id="15acb-188">處理器 turbo frequency 限制（IA turbo 限制）。</span><span class="sxs-lookup"><span data-stu-id="15acb-188">Processor turbo frequency limits (IA turbo limitations).</span></span> | <span data-ttu-id="15acb-189">調整處理器與圖形效能，讓處理器內核執行的速度更快，或速度低於額定運作頻率。</span><span class="sxs-lookup"><span data-stu-id="15acb-189">Adjusts processor and graphics performance allowing processor cores to run faster or slower than the rated operating frequency.</span></span>                                                |

>[!NOTE]
><span data-ttu-id="15acb-190">無論是從 [控制台]/[電源選項]、[群組原則] 或 [相關方法] 進行設定，電源滑杆完全獨立于作業系統電源設定。</span><span class="sxs-lookup"><span data-stu-id="15acb-190">The power slider is entirely independent of operating system power settings whether configured from Control Panel/ Power Options, Group Policy, or related methods.</span></span>

<span data-ttu-id="15acb-191">若要深入瞭解，請參閱：</span><span class="sxs-lookup"><span data-stu-id="15acb-191">To learn more, see:</span></span>

-   [<span data-ttu-id="15acb-192">自訂 Windows 效能電源滑杆</span><span class="sxs-lookup"><span data-stu-id="15acb-192">Customize the Windows performance power slider</span></span>](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

-   [<span data-ttu-id="15acb-193">節電模式。</span><span class="sxs-lookup"><span data-stu-id="15acb-193">Battery saver.</span></span>](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)

## <span data-ttu-id="15acb-194">延長電池使用時間的最佳做法</span><span class="sxs-lookup"><span data-stu-id="15acb-194">Best practices for extended battery life</span></span>


| <span data-ttu-id="15acb-195">最佳做法</span><span class="sxs-lookup"><span data-stu-id="15acb-195">Best practice</span></span> | <span data-ttu-id="15acb-196">移至</span><span class="sxs-lookup"><span data-stu-id="15acb-196">Go to</span></span> | <span data-ttu-id="15acb-197">後續步驟</span><span class="sxs-lookup"><span data-stu-id="15acb-197">Next steps</span></span> |
|---|---|---|                                                                                                                                    
| <span data-ttu-id="15acb-198">確定您的 Surface 裝置是最新的</span><span class="sxs-lookup"><span data-stu-id="15acb-198">Ensure your Surface device is up to date</span></span>| <span data-ttu-id="15acb-199">Windows Update</span><span class="sxs-lookup"><span data-stu-id="15acb-199">Windows Update</span></span> | <span data-ttu-id="15acb-200">在工作列搜尋方塊中，輸入 [ **Windows Update** ]，然後選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="15acb-200">In the taskbar search box, type **Windows Update** and select **Check for updates**.</span></span> |
| <span data-ttu-id="15acb-201">針對您正在執行的工作，選擇最佳電源設定</span><span class="sxs-lookup"><span data-stu-id="15acb-201">Choose the best power setting for what you’re doing</span></span> | <span data-ttu-id="15acb-202">[電源] 滑杆</span><span class="sxs-lookup"><span data-stu-id="15acb-202">Power slider</span></span> | <span data-ttu-id="15acb-203">在工作列中，選取電池圖示，然後選擇 [**最佳效能**]、[**最佳電池使用**中] 或 [介於] 之間的某個位置。</span><span class="sxs-lookup"><span data-stu-id="15acb-203">In the taskbar, select the battery icon, then choose **Best performance**, **Best battery life**, or somewhere in between.</span></span>|
| <span data-ttu-id="15acb-204">在電量低時節省電池</span><span class="sxs-lookup"><span data-stu-id="15acb-204">Conserve battery when it’s low</span></span> | <span data-ttu-id="15acb-205">省電模式</span><span class="sxs-lookup"><span data-stu-id="15acb-205">Battery saver</span></span> | <span data-ttu-id="15acb-206">在工作列中，選取 [電池] 圖示，然後按一下 [**電池設定**]。</span><span class="sxs-lookup"><span data-stu-id="15acb-206">In the taskbar, select the battery icon and click **Battery settings**.</span></span> <span data-ttu-id="15acb-207">選取 [**如果我的電池不足，自動開啟節電**模式]，然後將滑杆向右移動到較長的電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="15acb-207">Select **Turn battery saver on automatically if my battery falls below** and then move the slider further to the right for longer battery life.</span></span> |
| <span data-ttu-id="15acb-208">設定最佳螢幕亮度</span><span class="sxs-lookup"><span data-stu-id="15acb-208">Configure optimal screen brightness</span></span> | <span data-ttu-id="15acb-209">省電模式</span><span class="sxs-lookup"><span data-stu-id="15acb-209">Battery saver</span></span> | <span data-ttu-id="15acb-210">在工作列中，選取電池圖示，然後按一下 [**電池設定**]，**在節電模式中選取較低的螢幕亮度**。</span><span class="sxs-lookup"><span data-stu-id="15acb-210">In the taskbar, select the battery icon and click **Battery settings**, select **Lower screen brightness while in battery saver**.</span></span> |
| <span data-ttu-id="15acb-211">在未插入電源時省電</span><span class="sxs-lookup"><span data-stu-id="15acb-211">Conserve power whenever you’re not plugged in</span></span> | <span data-ttu-id="15acb-212">省電模式</span><span class="sxs-lookup"><span data-stu-id="15acb-212">Battery saver</span></span>| <span data-ttu-id="15acb-213">選取 **[開啟節電模式狀態，直到下次充電為止]**。</span><span class="sxs-lookup"><span data-stu-id="15acb-213">Select **Turn on battery saver status until next charge**.</span></span>|
| <span data-ttu-id="15acb-214">調查電源設定的問題。</span><span class="sxs-lookup"><span data-stu-id="15acb-214">Investigate problems with your power settings.</span></span> | <span data-ttu-id="15acb-215">Power 疑難排解程式</span><span class="sxs-lookup"><span data-stu-id="15acb-215">Power troubleshooter</span></span> | <span data-ttu-id="15acb-216">在工作列的 [搜尋] 中，選取疑難排解，選取 [**疑難排解**]，然後選取 [**電源**]，然後依照指示進行。</span><span class="sxs-lookup"><span data-stu-id="15acb-216">In the Taskbar search for troubleshoot, select **Troubleshoot**, and then select **Power** and follow the instructions.</span></span>|
| <span data-ttu-id="15acb-217">檢查 app 使用方式</span><span class="sxs-lookup"><span data-stu-id="15acb-217">Check app usage</span></span> | <span data-ttu-id="15acb-218">您的應用程式</span><span class="sxs-lookup"><span data-stu-id="15acb-218">Your apps</span></span> | <span data-ttu-id="15acb-219">關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="15acb-219">Close apps.</span></span>|
| <span data-ttu-id="15acb-220">檢查您的電源線是否有任何損壞。</span><span class="sxs-lookup"><span data-stu-id="15acb-220">Check your power cord for any damage.</span></span>| <span data-ttu-id="15acb-221">您的電源線</span><span class="sxs-lookup"><span data-stu-id="15acb-221">Your power cord</span></span> | <span data-ttu-id="15acb-222">如果電源線磨損或損毀，請將它取代。</span><span class="sxs-lookup"><span data-stu-id="15acb-222">Replace power cord if worn or damaged.</span></span>|

## <span data-ttu-id="15acb-223">深入了解</span><span class="sxs-lookup"><span data-stu-id="15acb-223">Learn more</span></span> 

- [<span data-ttu-id="15acb-224">新式待機</span><span class="sxs-lookup"><span data-stu-id="15acb-224">Modern   standby</span></span>](https://docs.microsoft.com/windows-hardware/design/device-experiences/modern-standby-wake-sources)

<!-- -->

- [<span data-ttu-id="15acb-225">自訂 Windows 效能電源滑杆</span><span class="sxs-lookup"><span data-stu-id="15acb-225">Customize the Windows performance power   slider</span></span>](https://docs.microsoft.com/windows-hardware/customize/desktop/customize-power-slider)

- [<span data-ttu-id="15acb-226">節電模式</span><span class="sxs-lookup"><span data-stu-id="15acb-226">Battery   saver</span></span>](https://docs.microsoft.com/windows-hardware/design/component-guidelines/battery-saver)
- [<span data-ttu-id="15acb-227">管理和部署 Surface 驅動程式與韌體更新</span><span class="sxs-lookup"><span data-stu-id="15acb-227">Manage and deploy Surface driver and firmware updates</span></span>](manage-surface-driver-and-firmware-updates.md)
