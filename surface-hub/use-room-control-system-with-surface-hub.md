---
title: 使用會議室控制系統 (Surface Hub)
description: 會議室控制系統可以與您的 Microsoft Surface Hub 搭配使用。
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: 會議室控制系統, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831336"
---
# <span data-ttu-id="b25c3-104">使用會議室控制系統 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="b25c3-104">Using a room control system (Surface Hub)</span></span>


<span data-ttu-id="b25c3-105">會議室控制系統可以與您的 Microsoft Surface Hub 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="b25c3-105">Room control systems can be used with your Microsoft Surface Hub.</span></span>

<span data-ttu-id="b25c3-106">將會議室控制系統與您的 Surface Hub 搭配使用，包括將會議室控制硬體連接到 Surface Hub (通常是透過 Surface Hub 底部的 RJ11 序列埠來連接)。</span><span class="sxs-lookup"><span data-stu-id="b25c3-106">Using a room control system with your Surface Hub involves connecting room control hardware to the Surface Hub, usually through the RJ11 serial port on the bottom of the Surface Hub.</span></span>

## <a name="terminal-settings"></a><span data-ttu-id="b25c3-107">終端機設定</span><span class="sxs-lookup"><span data-stu-id="b25c3-107">Terminal settings</span></span>

<span data-ttu-id="b25c3-108">若要連接到會議室控制系統的控制台，您不需要在 Surface Hub 上設定任何終端機設定。</span><span class="sxs-lookup"><span data-stu-id="b25c3-108">To connect to a room control system control panel, you don't need to configure any terminal settings on the Surface Hub.</span></span> <span data-ttu-id="b25c3-109">如果您想要將電腦或膝上型電腦連接到 Surface Hub 並從 Surface Hub 傳送序列命令，您可以使用終端機模擬器程式 (例如 Tera Term 或 PuTTY)。</span><span class="sxs-lookup"><span data-stu-id="b25c3-109">If you want to connect a PC or laptop to your Surface Hub and send serial commands from the Surface Hub, you can use a terminal emulator program like Tera Term or PuTTY.</span></span> 

| <span data-ttu-id="b25c3-110">設定</span><span class="sxs-lookup"><span data-stu-id="b25c3-110">Setting</span></span> | <span data-ttu-id="b25c3-111">值</span><span class="sxs-lookup"><span data-stu-id="b25c3-111">Value</span></span> |
| --- | --- |
| <span data-ttu-id="b25c3-112">傳輸速率</span><span class="sxs-lookup"><span data-stu-id="b25c3-112">Baud rate</span></span> | <span data-ttu-id="b25c3-113">115200</span><span class="sxs-lookup"><span data-stu-id="b25c3-113">115200</span></span> |
| <span data-ttu-id="b25c3-114">資料位元</span><span class="sxs-lookup"><span data-stu-id="b25c3-114">Data bits</span></span> | <span data-ttu-id="b25c3-115">型</span><span class="sxs-lookup"><span data-stu-id="b25c3-115">8</span></span> | 
| <span data-ttu-id="b25c3-116">停止位元</span><span class="sxs-lookup"><span data-stu-id="b25c3-116">Stop bits</span></span> | <span data-ttu-id="b25c3-117">sr-1</span><span class="sxs-lookup"><span data-stu-id="b25c3-117">1</span></span> |
| <span data-ttu-id="b25c3-118">同位</span><span class="sxs-lookup"><span data-stu-id="b25c3-118">Parity</span></span> | <span data-ttu-id="b25c3-119">無</span><span class="sxs-lookup"><span data-stu-id="b25c3-119">none</span></span> |
| <span data-ttu-id="b25c3-120">流量控制</span><span class="sxs-lookup"><span data-stu-id="b25c3-120">Flow control</span></span> | <span data-ttu-id="b25c3-121">無</span><span class="sxs-lookup"><span data-stu-id="b25c3-121">none</span></span> |
| <span data-ttu-id="b25c3-122">換行字元</span><span class="sxs-lookup"><span data-stu-id="b25c3-122">Line feed</span></span> | <span data-ttu-id="b25c3-123">每個歸位字元</span><span class="sxs-lookup"><span data-stu-id="b25c3-123">every carriage return</span></span> |
 

## <a name="wiring-diagram"></a><span data-ttu-id="b25c3-124">線路圖</span><span class="sxs-lookup"><span data-stu-id="b25c3-124">Wiring diagram</span></span>

<span data-ttu-id="b25c3-125">您可以使用標準的 RJ-11 (6P6C) 連接器，將 Surface Hub 序列埠連接到會議室控制系統。</span><span class="sxs-lookup"><span data-stu-id="b25c3-125">You can use a standard RJ-11 (6P6C) connector to connect the Surface Hub serial port to a room control system.</span></span> <span data-ttu-id="b25c3-126">這是建議的方法。</span><span class="sxs-lookup"><span data-stu-id="b25c3-126">This is the recommended method.</span></span> <span data-ttu-id="b25c3-127">您也可以使用 4 導線的 RJ-11 纜線，但我們不建議使用這個方法。</span><span class="sxs-lookup"><span data-stu-id="b25c3-127">You can also use an RJ-11 4-conductor cable, but we do not recommend this method.</span></span>

<span data-ttu-id="b25c3-128">下圖顯示 RJ-11 (6P6C) 至 DB9 纜線的正確針腳對應。</span><span class="sxs-lookup"><span data-stu-id="b25c3-128">This diagram shows the correct pinout used for an RJ-11 (6P6C) to DB9 cable.</span></span>

![顯示路線圖的影像。](images/room-control-wiring-diagram.png)

## <a name="command-sets"></a><span data-ttu-id="b25c3-130">命令集</span><span class="sxs-lookup"><span data-stu-id="b25c3-130">Command sets</span></span>

<span data-ttu-id="b25c3-131">會議室控制系統會針對命令使用常見的會議室案例。</span><span class="sxs-lookup"><span data-stu-id="b25c3-131">Room control systems use common meeting-room scenarios for commands.</span></span> <span data-ttu-id="b25c3-132">命令源自會議室控制系統，並透過序列式連線來與 Surface Hub 通訊。</span><span class="sxs-lookup"><span data-stu-id="b25c3-132">Commands originate from the room control system, and are communicated over a serial connection to a Surface Hub.</span></span> <span data-ttu-id="b25c3-133">命令是以 ASCII 為基礎，而且 Surface Hub 將會在發生狀態變更時進行確認。</span><span class="sxs-lookup"><span data-stu-id="b25c3-133">Commands are ASCII based, and the Surface Hub will acknowledge when state changes occur.</span></span>

<span data-ttu-id="b25c3-134">您可以使用下列命令修飾詞。</span><span class="sxs-lookup"><span data-stu-id="b25c3-134">The following command modifiers are available.</span></span> <span data-ttu-id="b25c3-135">命令是以新行字元 (/n) 來結尾。</span><span class="sxs-lookup"><span data-stu-id="b25c3-135">Commands terminate with a new line character (\n).</span></span> <span data-ttu-id="b25c3-136">回應可隨時進行，以回應不是由管理連接埠命令直接觸發的狀態變更。</span><span class="sxs-lookup"><span data-stu-id="b25c3-136">Responses can come at any time in response to state changes not triggered directly by a management port command.</span></span>

| <span data-ttu-id="b25c3-137">修飾詞</span><span class="sxs-lookup"><span data-stu-id="b25c3-137">Modifier</span></span> | <span data-ttu-id="b25c3-138">結果</span><span class="sxs-lookup"><span data-stu-id="b25c3-138">Result</span></span> |
| --- | --- |
| + | <span data-ttu-id="b25c3-139">遞增值</span><span class="sxs-lookup"><span data-stu-id="b25c3-139">Increment a value</span></span> |
| - | <span data-ttu-id="b25c3-140">遞減值</span><span class="sxs-lookup"><span data-stu-id="b25c3-140">Decrease a value</span></span> |
| = | <span data-ttu-id="b25c3-141">設定離散值</span><span class="sxs-lookup"><span data-stu-id="b25c3-141">Set a discrete value</span></span> |
| <span data-ttu-id="b25c3-142">?</span><span class="sxs-lookup"><span data-stu-id="b25c3-142">?</span></span> | <span data-ttu-id="b25c3-143">查詢目前的值</span><span class="sxs-lookup"><span data-stu-id="b25c3-143">Queries for a current value</span></span> |
 

## <a name="power"></a><span data-ttu-id="b25c3-144">電源</span><span class="sxs-lookup"><span data-stu-id="b25c3-144">Power</span></span>

<span data-ttu-id="b25c3-145">Surface Hub 可以處於下列其中一個電源狀態。</span><span class="sxs-lookup"><span data-stu-id="b25c3-145">Surface Hub can be in one of these power states.</span></span>

| <span data-ttu-id="b25c3-146">狀態</span><span class="sxs-lookup"><span data-stu-id="b25c3-146">State</span></span> | <span data-ttu-id="b25c3-147">能源之星狀態</span><span class="sxs-lookup"><span data-stu-id="b25c3-147">Energy Star state</span></span>| <span data-ttu-id="b25c3-148">說明</span><span class="sxs-lookup"><span data-stu-id="b25c3-148">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b25c3-149">0</span><span class="sxs-lookup"><span data-stu-id="b25c3-149">0</span></span> | <span data-ttu-id="b25c3-150">S5</span><span class="sxs-lookup"><span data-stu-id="b25c3-150">S5</span></span> | <span data-ttu-id="b25c3-151">關閉</span><span class="sxs-lookup"><span data-stu-id="b25c3-151">Off</span></span> |
| <span data-ttu-id="b25c3-152">sr-1</span><span class="sxs-lookup"><span data-stu-id="b25c3-152">1</span></span> | - | <span data-ttu-id="b25c3-153">開啟電源 (不確定)</span><span class="sxs-lookup"><span data-stu-id="b25c3-153">Power up (indeterminate)</span></span> |
| <span data-ttu-id="b25c3-154">pplx-2</span><span class="sxs-lookup"><span data-stu-id="b25c3-154">2</span></span> | <span data-ttu-id="b25c3-155">S3</span><span class="sxs-lookup"><span data-stu-id="b25c3-155">S3</span></span> | <span data-ttu-id="b25c3-156">睡眠</span><span class="sxs-lookup"><span data-stu-id="b25c3-156">Sleep</span></span> |
| <span data-ttu-id="b25c3-157">500</span><span class="sxs-lookup"><span data-stu-id="b25c3-157">5</span></span> | <span data-ttu-id="b25c3-158">S0</span><span class="sxs-lookup"><span data-stu-id="b25c3-158">S0</span></span> | <span data-ttu-id="b25c3-159">就緒</span><span class="sxs-lookup"><span data-stu-id="b25c3-159">Ready</span></span> |


<span data-ttu-id="b25c3-160">在「替代電腦」模式中，電源狀態只有「就緒」和「關閉」，且只會變更顯示器。</span><span class="sxs-lookup"><span data-stu-id="b25c3-160">In Replacement PC mode, the power states are only Ready and Off and only change the display.</span></span> <span data-ttu-id="b25c3-161">管理埠無法用來將替代電腦開機。</span><span class="sxs-lookup"><span data-stu-id="b25c3-161">The management port can't be used to power on the replacement PC.</span></span> 

| <span data-ttu-id="b25c3-162">狀態</span><span class="sxs-lookup"><span data-stu-id="b25c3-162">State</span></span> | <span data-ttu-id="b25c3-163">能源之星狀態</span><span class="sxs-lookup"><span data-stu-id="b25c3-163">Energy Star state</span></span>| <span data-ttu-id="b25c3-164">說明</span><span class="sxs-lookup"><span data-stu-id="b25c3-164">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b25c3-165">0</span><span class="sxs-lookup"><span data-stu-id="b25c3-165">0</span></span> | <span data-ttu-id="b25c3-166">S5</span><span class="sxs-lookup"><span data-stu-id="b25c3-166">S5</span></span> | <span data-ttu-id="b25c3-167">關閉</span><span class="sxs-lookup"><span data-stu-id="b25c3-167">Off</span></span> |
| <span data-ttu-id="b25c3-168">500</span><span class="sxs-lookup"><span data-stu-id="b25c3-168">5</span></span> | <span data-ttu-id="b25c3-169">S0</span><span class="sxs-lookup"><span data-stu-id="b25c3-169">S0</span></span> | <span data-ttu-id="b25c3-170">就緒</span><span class="sxs-lookup"><span data-stu-id="b25c3-170">Ready</span></span> |

<span data-ttu-id="b25c3-171">針對控制裝置，「5 / 就緒」以外的任何值都被視為關閉。</span><span class="sxs-lookup"><span data-stu-id="b25c3-171">For a control device, anything other than 5 / Ready should be considered off.</span></span> <span data-ttu-id="b25c3-172">每個 PowerOn 命令都會產生兩種狀態變更與回應。</span><span class="sxs-lookup"><span data-stu-id="b25c3-172">Each PowerOn command results in two state changes and responses.</span></span> 

| <span data-ttu-id="b25c3-173">命令</span><span class="sxs-lookup"><span data-stu-id="b25c3-173">Command</span></span> | <span data-ttu-id="b25c3-174">狀態變更</span><span class="sxs-lookup"><span data-stu-id="b25c3-174">State change</span></span>| <span data-ttu-id="b25c3-175">回應</span><span class="sxs-lookup"><span data-stu-id="b25c3-175">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b25c3-176">PowerOn</span><span class="sxs-lookup"><span data-stu-id="b25c3-176">PowerOn</span></span> | <span data-ttu-id="b25c3-177">開啟裝置 (顯示器 + 電腦)。</span><span class="sxs-lookup"><span data-stu-id="b25c3-177">Device turns on (display + PC).</span></span></br></br><span data-ttu-id="b25c3-178">電腦服務通知 SMC 電腦已經就緒。</span><span class="sxs-lookup"><span data-stu-id="b25c3-178">PC service notifies SMC that the PC is ready.</span></span> |  <span data-ttu-id="b25c3-179">Power=0</span><span class="sxs-lookup"><span data-stu-id="b25c3-179">Power=0</span></span></br></br><span data-ttu-id="b25c3-180">Power=5</span><span class="sxs-lookup"><span data-stu-id="b25c3-180">Power=5</span></span> |
| <span data-ttu-id="b25c3-181">PowerOff</span><span class="sxs-lookup"><span data-stu-id="b25c3-181">PowerOff</span></span> | <span data-ttu-id="b25c3-182">裝置轉換成環境狀態 (電腦開啟，顯示器變暗)。</span><span class="sxs-lookup"><span data-stu-id="b25c3-182">Device transitions to ambient state (PC on, display dim).</span></span> |  <span data-ttu-id="b25c3-183">Power=0</span><span class="sxs-lookup"><span data-stu-id="b25c3-183">Power=0</span></span> |
| <span data-ttu-id="b25c3-184">Power?</span><span class="sxs-lookup"><span data-stu-id="b25c3-184">Power?</span></span> |  <span data-ttu-id="b25c3-185">SMC 回報已知的最後電源狀態。</span><span class="sxs-lookup"><span data-stu-id="b25c3-185">SMC reports the last-known power state.</span></span> |  <span data-ttu-id="b25c3-186">Power=<#></span><span class="sxs-lookup"><span data-stu-id="b25c3-186">Power=<#></span></span> |



## <a name="brightness"></a><span data-ttu-id="b25c3-187">亮度</span><span class="sxs-lookup"><span data-stu-id="b25c3-187">Brightness</span></span>

<span data-ttu-id="b25c3-188">目前的亮度等級是介於 0 到 100 的範圍。</span><span class="sxs-lookup"><span data-stu-id="b25c3-188">The current brightness level is a range from 0 to 100.</span></span>

<span data-ttu-id="b25c3-189">對於亮度等級的變更可以透過會議室控制系統或其他系統來傳送。</span><span class="sxs-lookup"><span data-stu-id="b25c3-189">Changes to brightness levels can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="b25c3-190">命令</span><span class="sxs-lookup"><span data-stu-id="b25c3-190">Command</span></span> | <span data-ttu-id="b25c3-191">狀態變更</span><span class="sxs-lookup"><span data-stu-id="b25c3-191">State change</span></span> |<span data-ttu-id="b25c3-192">回應</span><span class="sxs-lookup"><span data-stu-id="b25c3-192">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b25c3-193">Brightness+</span><span class="sxs-lookup"><span data-stu-id="b25c3-193">Brightness+</span></span> | <span data-ttu-id="b25c3-194">系統管理控制器 (SMC) 會傳送增加亮度命令。</span><span class="sxs-lookup"><span data-stu-id="b25c3-194">System management controller (SMC) sends the brightness up command.</span></span></br></br><span data-ttu-id="b25c3-195">會議室控制系統上的電腦服務會通知 SMC 新的亮度等級。</span><span class="sxs-lookup"><span data-stu-id="b25c3-195">PC service on the room control system notifies SMC of new brightness level.</span></span> |  <span data-ttu-id="b25c3-196">Brightness = 51</span><span class="sxs-lookup"><span data-stu-id="b25c3-196">Brightness = 51</span></span> |
| <span data-ttu-id="b25c3-197">Brightness-</span><span class="sxs-lookup"><span data-stu-id="b25c3-197">Brightness-</span></span> |  <span data-ttu-id="b25c3-198">SMC 會傳送降低亮度命令。</span><span class="sxs-lookup"><span data-stu-id="b25c3-198">SMC sends the brightness down command.</span></span></br></br><span data-ttu-id="b25c3-199">電腦服務會通知 SMC 新的亮度等級。</span><span class="sxs-lookup"><span data-stu-id="b25c3-199">PC service notifies SMC of new brightness level.</span></span> | <span data-ttu-id="b25c3-200">Brightness = 50</span><span class="sxs-lookup"><span data-stu-id="b25c3-200">Brightness = 50</span></span> |

## <a name="volume"></a><span data-ttu-id="b25c3-201">音量</span><span class="sxs-lookup"><span data-stu-id="b25c3-201">Volume</span></span>

<span data-ttu-id="b25c3-202">目前的音量等級是介於 0 到 100 的範圍。</span><span class="sxs-lookup"><span data-stu-id="b25c3-202">The current volume level is a range from 0 to 100.</span></span>

<span data-ttu-id="b25c3-203">對於音量大小的變更可以透過會議室控制系統或其他系統來傳送。</span><span class="sxs-lookup"><span data-stu-id="b25c3-203">Changes to volume levels can be sent by a room control system, or other system.</span></span>

>[!NOTE]
><span data-ttu-id="b25c3-204">音量命令只會控制內嵌或取代用電腦模式的音量，而不會控制[客體來源](connect-and-display-with-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="b25c3-204">The Volume command will only control the volume for embedded or Replacement PC mode, not from [Guest sources](connect-and-display-with-surface-hub.md).</span></span>

| <span data-ttu-id="b25c3-205">命令</span><span class="sxs-lookup"><span data-stu-id="b25c3-205">Command</span></span> | <span data-ttu-id="b25c3-206">狀態變更</span><span class="sxs-lookup"><span data-stu-id="b25c3-206">State change</span></span> | <span data-ttu-id="b25c3-207">回應</span><span class="sxs-lookup"><span data-stu-id="b25c3-207">Response</span></span></br><span data-ttu-id="b25c3-208">(關於 [取代用電腦模式](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span><span class="sxs-lookup"><span data-stu-id="b25c3-208">(On in [Replacement PC mode](connect-and-display-with-surface-hub.md#replacement-pc-mode))</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b25c3-209">Volume+</span><span class="sxs-lookup"><span data-stu-id="b25c3-209">Volume+</span></span> |  <span data-ttu-id="b25c3-210">SMC 會傳送調高音量的命令。</span><span class="sxs-lookup"><span data-stu-id="b25c3-210">SMC sends the volume up command.</span></span></br></br><span data-ttu-id="b25c3-211">電腦服務會通知 SMC 新的音量大小。</span><span class="sxs-lookup"><span data-stu-id="b25c3-211">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="b25c3-212">Volume = 51</span><span class="sxs-lookup"><span data-stu-id="b25c3-212">Volume = 51</span></span> |
| <span data-ttu-id="b25c3-213">Volume-</span><span class="sxs-lookup"><span data-stu-id="b25c3-213">Volume-</span></span> |  <span data-ttu-id="b25c3-214">SMC 會傳送降低音量的命令。</span><span class="sxs-lookup"><span data-stu-id="b25c3-214">SMC sends the volume down command.</span></span></br></br><span data-ttu-id="b25c3-215">電腦服務會通知 SMC 新的音量等級。</span><span class="sxs-lookup"><span data-stu-id="b25c3-215">PC service notifies SMC of new volume level.</span></span> |  <span data-ttu-id="b25c3-216">Volume = 50</span><span class="sxs-lookup"><span data-stu-id="b25c3-216">Volume = 50</span></span> |


 

## <a name="mute-for-audio"></a><span data-ttu-id="b25c3-217">音訊靜音</span><span class="sxs-lookup"><span data-stu-id="b25c3-217">Mute for audio</span></span>

<span data-ttu-id="b25c3-218">可將音訊設為靜音。</span><span class="sxs-lookup"><span data-stu-id="b25c3-218">Audio can be muted.</span></span>

| <span data-ttu-id="b25c3-219">命令</span><span class="sxs-lookup"><span data-stu-id="b25c3-219">Command</span></span> | <span data-ttu-id="b25c3-220">狀態變更</span><span class="sxs-lookup"><span data-stu-id="b25c3-220">State change</span></span> | <span data-ttu-id="b25c3-221">回應</span><span class="sxs-lookup"><span data-stu-id="b25c3-221">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b25c3-222">AudioMute+</span><span class="sxs-lookup"><span data-stu-id="b25c3-222">AudioMute+</span></span> |  <span data-ttu-id="b25c3-223">SMC 會傳送將音訊設為靜音的命令。</span><span class="sxs-lookup"><span data-stu-id="b25c3-223">SMC sends the audio mute command.</span></span></br></br><span data-ttu-id="b25c3-224">電腦服務會通知 SMC 將音訊設為靜音。</span><span class="sxs-lookup"><span data-stu-id="b25c3-224">PC service notifies SMC that audio is muted.</span></span> |  <span data-ttu-id="b25c3-225">無</span><span class="sxs-lookup"><span data-stu-id="b25c3-225">none</span></span> |


 

## <a name="video-source"></a><span data-ttu-id="b25c3-226">視訊來源</span><span class="sxs-lookup"><span data-stu-id="b25c3-226">Video source</span></span>

<span data-ttu-id="b25c3-227">可以使用數個顯示來源。</span><span class="sxs-lookup"><span data-stu-id="b25c3-227">Several display sources can be used.</span></span>

| <span data-ttu-id="b25c3-228">狀態</span><span class="sxs-lookup"><span data-stu-id="b25c3-228">State</span></span> | <span data-ttu-id="b25c3-229">說明</span><span class="sxs-lookup"><span data-stu-id="b25c3-229">Description</span></span> | 
| --- | --- |
| <span data-ttu-id="b25c3-230">0</span><span class="sxs-lookup"><span data-stu-id="b25c3-230">0</span></span> |  <span data-ttu-id="b25c3-231">內建的電腦</span><span class="sxs-lookup"><span data-stu-id="b25c3-231">Onboard PC</span></span> |
| <span data-ttu-id="b25c3-232">sr-1</span><span class="sxs-lookup"><span data-stu-id="b25c3-232">1</span></span> |  <span data-ttu-id="b25c3-233">DisplayPort</span><span class="sxs-lookup"><span data-stu-id="b25c3-233">DisplayPort</span></span> |
| <span data-ttu-id="b25c3-234">pplx-2</span><span class="sxs-lookup"><span data-stu-id="b25c3-234">2</span></span> |  <span data-ttu-id="b25c3-235">HDMI</span><span class="sxs-lookup"><span data-stu-id="b25c3-235">HDMI</span></span> |
| <span data-ttu-id="b25c3-236">3</span><span class="sxs-lookup"><span data-stu-id="b25c3-236">3</span></span> |  <span data-ttu-id="b25c3-237">VGA</span><span class="sxs-lookup"><span data-stu-id="b25c3-237">VGA</span></span> |


 

<span data-ttu-id="b25c3-238">對於顯示來源的變更可以透過會議室控制系統或其他系統來傳送。</span><span class="sxs-lookup"><span data-stu-id="b25c3-238">Changes to display source can be sent by a room control system, or other system.</span></span>

| <span data-ttu-id="b25c3-239">命令</span><span class="sxs-lookup"><span data-stu-id="b25c3-239">Command</span></span> | <span data-ttu-id="b25c3-240">狀態變更</span><span class="sxs-lookup"><span data-stu-id="b25c3-240">State change</span></span> | <span data-ttu-id="b25c3-241">回應</span><span class="sxs-lookup"><span data-stu-id="b25c3-241">Response</span></span> |
| --- | --- | --- |
| <span data-ttu-id="b25c3-242">Source=#</span><span class="sxs-lookup"><span data-stu-id="b25c3-242">Source=#</span></span> |  <span data-ttu-id="b25c3-243">SMC 會對所需的來源進行變更。</span><span class="sxs-lookup"><span data-stu-id="b25c3-243">SMC changes to the desired source.</span></span></br></br><span data-ttu-id="b25c3-244">電腦服務會通知 SMC 已切換顯示來源。</span><span class="sxs-lookup"><span data-stu-id="b25c3-244">PC service notifies SMC that the display source has switched.</span></span> |  <span data-ttu-id="b25c3-245">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="b25c3-245">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="b25c3-246">Source+</span><span class="sxs-lookup"><span data-stu-id="b25c3-246">Source+</span></span> |  <span data-ttu-id="b25c3-247">SMC 會循環至下一個作用中的輸入來源。</span><span class="sxs-lookup"><span data-stu-id="b25c3-247">SMC cycles to the next active input source.</span></span></br></br><span data-ttu-id="b25c3-248">電腦服務會通知 SMC 目前的輸入來源。</span><span class="sxs-lookup"><span data-stu-id="b25c3-248">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="b25c3-249">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="b25c3-249">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="b25c3-250">Source-</span><span class="sxs-lookup"><span data-stu-id="b25c3-250">Source-</span></span> | <span data-ttu-id="b25c3-251">SMC 會循環至上一個作用中的輸入來源。</span><span class="sxs-lookup"><span data-stu-id="b25c3-251">SMC cycles to the previous active input source.</span></span></br></br><span data-ttu-id="b25c3-252">電腦服務會通知 SMC 目前的輸入來源。</span><span class="sxs-lookup"><span data-stu-id="b25c3-252">PC service notifies SMC of the current input source.</span></span> |  <span data-ttu-id="b25c3-253">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="b25c3-253">Source=&lt;#&gt;</span></span> |
| <span data-ttu-id="b25c3-254">Source?</span><span class="sxs-lookup"><span data-stu-id="b25c3-254">Source?</span></span> |  <span data-ttu-id="b25c3-255">SMC 會查詢電腦服務以取得作用中的輸入來源。</span><span class="sxs-lookup"><span data-stu-id="b25c3-255">SMC queries PC service for the active input source.</span></span></br></br><span data-ttu-id="b25c3-256">電腦服務會通知 SMC 目前的輸入來源。</span><span class="sxs-lookup"><span data-stu-id="b25c3-256">PC service notifies SMC of the current in;put source.</span></span> | <span data-ttu-id="b25c3-257">Source=&lt;#&gt;</span><span class="sxs-lookup"><span data-stu-id="b25c3-257">Source=&lt;#&gt;</span></span> |

## <a name="errors"></a><span data-ttu-id="b25c3-258">錯誤</span><span class="sxs-lookup"><span data-stu-id="b25c3-258">Errors</span></span>

<span data-ttu-id="b25c3-259">錯誤會以此表格中的格式傳回。</span><span class="sxs-lookup"><span data-stu-id="b25c3-259">Errors are returned following the format in this table.</span></span>

| <span data-ttu-id="b25c3-260">錯誤</span><span class="sxs-lookup"><span data-stu-id="b25c3-260">Error</span></span> | <span data-ttu-id="b25c3-261">附註</span><span class="sxs-lookup"><span data-stu-id="b25c3-261">Notes</span></span> |
| --- | --- |
| <span data-ttu-id="b25c3-262">錯誤: 未知的命令 '&lt;input&gt;'。</span><span class="sxs-lookup"><span data-stu-id="b25c3-262">Error: Unknown command '&lt;input&gt;'.</span></span> |  <span data-ttu-id="b25c3-263">指示包含未知的初始命令。</span><span class="sxs-lookup"><span data-stu-id="b25c3-263">The instruction contains an unknown initial command.</span></span> <span data-ttu-id="b25c3-264">例如，&quot;VOL+&quot; 將會是無效的，並傳回 &quot;錯誤: 未知命令 'VOL'&quot;。</span><span class="sxs-lookup"><span data-stu-id="b25c3-264">For example, &quot;VOL+&quot; would be invalid and return &quot; Error: Unknown command 'VOL'&quot;.</span></span> |
| <span data-ttu-id="b25c3-265">錯誤: 未知的運算子 '&lt;input&gt;'。</span><span class="sxs-lookup"><span data-stu-id="b25c3-265">Error: Unknown operator '&lt;input&gt;'.</span></span> |  <span data-ttu-id="b25c3-266">指示包含未知的運算子。</span><span class="sxs-lookup"><span data-stu-id="b25c3-266">The instruction contains an unknown operator.</span></span> <span data-ttu-id="b25c3-267">例如，&quot;Volume!&quot; 將會無效，並傳回 &quot;錯誤: 未知運算子 '!'&quot;。</span><span class="sxs-lookup"><span data-stu-id="b25c3-267">For example, &quot;Volume!&quot; would be invalid and return &quot; Error: Unknown operator '!'&quot;.</span></span> |
| <span data-ttu-id="b25c3-268">錯誤: 未知的參數 '&lt;input&gt;'。</span><span class="sxs-lookup"><span data-stu-id="b25c3-268">Error: Unknown parameter '&lt;input&gt;'.</span></span> |  <span data-ttu-id="b25c3-269">指示包含未知的參數。</span><span class="sxs-lookup"><span data-stu-id="b25c3-269">The instruction contains an unknown parameter.</span></span> <span data-ttu-id="b25c3-270">例如，&quot;Volume=abc&quot; 將會是無效的，並傳回 &quot;錯誤: 未知參數 'abc'&quot;。</span><span class="sxs-lookup"><span data-stu-id="b25c3-270">For example, &quot;Volume=abc&quot; would be invalid and return &quot; Error: Unknown parameter 'abc'&quot;.</span></span> |
| <span data-ttu-id="b25c3-271">錯誤: 關閉時無法使用命令 '&lt;input&gt;'。</span><span class="sxs-lookup"><span data-stu-id="b25c3-271">Error: Command not available when off '&lt;input&gt;'.</span></span> |  <span data-ttu-id="b25c3-272">當 Surface Hub 關閉時，針對「電源」以外的命令會傳回這個錯誤。</span><span class="sxs-lookup"><span data-stu-id="b25c3-272">When the Surface Hub is off, commands other than Power return this error.</span></span> <span data-ttu-id="b25c3-273">例如，&quot;Volume+&quot; 將會是無效的，並傳回 &quot;錯誤: 關閉時無法使用命令 'Volume'&quot;。</span><span class="sxs-lookup"><span data-stu-id="b25c3-273">For example, &quot;Volume+&quot; would be invalid and return &quot; Error: Command not available when off 'Volume'&quot;.</span></span> |


 

## <a name="related-topics"></a><span data-ttu-id="b25c3-274">相關主題</span><span class="sxs-lookup"><span data-stu-id="b25c3-274">Related topics</span></span>


[<span data-ttu-id="b25c3-275">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="b25c3-275">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="b25c3-276">Microsoft Surface Hub 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="b25c3-276">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





