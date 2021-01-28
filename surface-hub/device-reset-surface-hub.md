---
title: 重設或復原 Surface Hub
description: 描述 Surface Hub 的重設和復原程式，並提供指示。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重設 Surface Hub，復原
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/31/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73c7cf5a387bf7506bb69f62100171df4d94ad2d
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304816"
---
# <span data-ttu-id="e801a-104">重設或復原 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e801a-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="e801a-105">本文說明如何重設或復原 Microsoft Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="e801a-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="e801a-106">[重設 Surface Hub](#reset-a-surface-hub) 會將其作業系統傳回至上一個累積式 Windows 更新，並移除所有本機使用者檔案和配置資訊。</span><span class="sxs-lookup"><span data-stu-id="e801a-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="e801a-107">移除的資訊包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="e801a-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="e801a-108">裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="e801a-108">The device account</span></span>
- <span data-ttu-id="e801a-109">裝置本機系統管理員的帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="e801a-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="e801a-110">網域加入或 Azure AD 加入資訊</span><span class="sxs-lookup"><span data-stu-id="e801a-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="e801a-111">行動裝置管理 (MDM) 註冊資訊</span><span class="sxs-lookup"><span data-stu-id="e801a-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="e801a-112">使用 MDM 或 [設定] 應用程式所設定的配置資訊</span><span class="sxs-lookup"><span data-stu-id="e801a-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="e801a-113">[從雲端復原 Surface Hub](#recover-a-surface-hub-from-the-cloud) 也會移除此資訊。</span><span class="sxs-lookup"><span data-stu-id="e801a-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="e801a-114">此外，Surface Hub 會下載新的作業系統映射並進行安裝。</span><span class="sxs-lookup"><span data-stu-id="e801a-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="e801a-115">您可以指定是否要讓復原處理常式保留其他儲存在 Surface Hub 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="e801a-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="e801a-116">如果您需要復原其中兩個選項都無法使用的 Surface Hub， [Surface Hub 恢復工具](surface-hub-recovery-tool.md) 會使用相同的作業系統影像。</span><span class="sxs-lookup"><span data-stu-id="e801a-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <span data-ttu-id="e801a-117">重設 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e801a-117">Reset a Surface Hub</span></span>

<span data-ttu-id="e801a-118">您可能需要重設 Surface Hub，原因如下：</span><span class="sxs-lookup"><span data-stu-id="e801a-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="e801a-119">您要為新的會議空間重新調整裝置的用途，並想要重新設定。</span><span class="sxs-lookup"><span data-stu-id="e801a-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="e801a-120">您想要變更在本機管理裝置的方式。</span><span class="sxs-lookup"><span data-stu-id="e801a-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="e801a-121">裝置帳戶或系統管理員帳戶的使用者名稱或密碼遺失。</span><span class="sxs-lookup"><span data-stu-id="e801a-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="e801a-122">安裝更新之後，裝置的效能就會減少。</span><span class="sxs-lookup"><span data-stu-id="e801a-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="e801a-123">在重設程式期間，如果您長時間內看到空白畫面，請稍候，並不採取任何動作。</span><span class="sxs-lookup"><span data-stu-id="e801a-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="e801a-124">裝置重設程式可能需要長達6小時的時間。</span><span class="sxs-lookup"><span data-stu-id="e801a-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="e801a-125">請勿關閉或拔下 Surface Hub，直到程式完成為止。</span><span class="sxs-lookup"><span data-stu-id="e801a-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="e801a-126">如果您中斷程式，裝置就無法操作。</span><span class="sxs-lookup"><span data-stu-id="e801a-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="e801a-127">裝置需要保修服務才能再次運作。</span><span class="sxs-lookup"><span data-stu-id="e801a-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="e801a-128">在 Surface Hub 上，開啟 **\[設定\]**。</span><span class="sxs-lookup"><span data-stu-id="e801a-128">On your Surface Hub, open **Settings**.</span></span>

   ![顯示 Surface Hub 之 [設定] 應用程式的影像。](images/sh-settings.png)

2. <span data-ttu-id="e801a-130">選取 [ **更新 & 安全性**]。</span><span class="sxs-lookup"><span data-stu-id="e801a-130">Select **Update & Security**.</span></span>

   ![在 Surface Hub 的 [設定] app 中顯示 [更新 & 安全群組的影像。](images/sh-settings-update-security.png)

3. <span data-ttu-id="e801a-132">選取 [ **恢復**]，然後在 [ **重設裝置**] 底下，選取 [ **開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="e801a-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="e801a-133">在重設裝置之前，請確定您有可用的 BitLocker 金鑰，因為稍後會提示您輸入。</span><span class="sxs-lookup"><span data-stu-id="e801a-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="e801a-134">若要深入瞭解，請參閱 [儲存您的 BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="e801a-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="e801a-135">當中樞重新開機至 [恢復] 分區時，系統會提示您輸入 BitLocker 金鑰。</span><span class="sxs-lookup"><span data-stu-id="e801a-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="e801a-136">跳過該提示會導致重設失敗。</span><span class="sxs-lookup"><span data-stu-id="e801a-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![在 Surface Hub 的 [設定] 應用程式中顯示 [重設裝置] 選項的影像。](images/sh-settings-reset-device.png)

   <span data-ttu-id="e801a-138">重設程式完成後，Surface Hub 會再次開始 [執行第一個 run 程式](first-run-program-surface-hub.md) 。</span><span class="sxs-lookup"><span data-stu-id="e801a-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="e801a-139">如果重設程式遇到問題，它會將 Surface Hub 滾回到先前現有的作業系統影像，然後顯示 [歡迎] 畫面。</span><span class="sxs-lookup"><span data-stu-id="e801a-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <span data-ttu-id="e801a-140">從雲端復原 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e801a-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="e801a-141">如果由於某種原因，Surface Hub 無法使用，您仍然可以從雲端將它復原，而不需要 Microsoft 支援部門取得協助。</span><span class="sxs-lookup"><span data-stu-id="e801a-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="e801a-142">Surface Hub 可以從雲端下載全新的作業系統影像，並使用該影像來重新安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="e801a-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="e801a-143">在下列情況下，您可能必須使用這種類型的復原程式：</span><span class="sxs-lookup"><span data-stu-id="e801a-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="e801a-144">Surface Hub 或其相關帳戶已進入不穩定狀態</span><span class="sxs-lookup"><span data-stu-id="e801a-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="e801a-145">Surface Hub 已鎖定</span><span class="sxs-lookup"><span data-stu-id="e801a-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="e801a-146">**從雲端程式復原**需要有線連線， (沒有 proxy 或其他驗證提示) 。</span><span class="sxs-lookup"><span data-stu-id="e801a-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <span data-ttu-id="e801a-147">還原不良狀態中的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e801a-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="e801a-148">如果裝置帳戶出現無法穩定的狀態，或如果管理員帳戶遇到問題，您可以使用 [設定] app 來啟動雲端復原程式。</span><span class="sxs-lookup"><span data-stu-id="e801a-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="e801a-149">當 [裝置重設](#reset-a-surface-hub) 處理常式無法修正問題時，您應該只使用雲端復原程式。</span><span class="sxs-lookup"><span data-stu-id="e801a-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="e801a-150">在 Surface Hub 上，選取 [ **設定** &gt; **更新 & 安全性**復原] &gt; \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="e801a-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="e801a-151">在 **[從雲端復原**] 底下，選取 [ **立即重新開機**]。</span><span class="sxs-lookup"><span data-stu-id="e801a-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![從雲端復原](images/recover-from-the-cloud.png)

### <span data-ttu-id="e801a-153">復原鎖定的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e801a-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="e801a-154">在極少數的情況下，Surface Hub 可能會在工作階段末端清理使用者和應用程式資料時遇到錯誤。</span><span class="sxs-lookup"><span data-stu-id="e801a-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="e801a-155">發生這種情況時，裝置會自動重新開機並再次嘗試該作業。</span><span class="sxs-lookup"><span data-stu-id="e801a-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="e801a-156">但如果此操作重複失敗，裝置會自動鎖定以保護使用者資料。</span><span class="sxs-lookup"><span data-stu-id="e801a-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="e801a-157">若要解除鎖定，您必須 [重設裝置](#reset-a-surface-hub) ，或者如果沒有作用，請從雲端復原。</span><span class="sxs-lookup"><span data-stu-id="e801a-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="e801a-158">在 Surface Hub 底部找出電源開關。</span><span class="sxs-lookup"><span data-stu-id="e801a-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="e801a-159">電源開關位於電源線連接的旁邊。</span><span class="sxs-lookup"><span data-stu-id="e801a-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="e801a-160">如需有關 power 開關的詳細資訊，請參閱 [Surface Hub 網站準備就緒指南 (PDF) ](surface-hub-site-readiness-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="e801a-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="e801a-161">當 Surface Hub 顯示 [歡迎] 畫面時，請使用 power 開關關閉 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="e801a-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="e801a-162">使用 power 開關來再次開啟 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="e801a-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="e801a-163">裝置隨即啟動並顯示 Surface Hub 標誌畫面。</span><span class="sxs-lookup"><span data-stu-id="e801a-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="e801a-164">當您在 Surface Hub 標誌底下看到旋轉點時，請使用 power 開關再次關閉 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="e801a-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="e801a-165">重複步驟 3 3 的時間，或直到 Surface Hub 顯示「正在準備自動修復」訊息。</span><span class="sxs-lookup"><span data-stu-id="e801a-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="e801a-166">顯示此訊息之後，Surface Hub 就會顯示 [Windows RE] 畫面。</span><span class="sxs-lookup"><span data-stu-id="e801a-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

5. <span data-ttu-id="e801a-167">選取 [ **高級選項**]。</span><span class="sxs-lookup"><span data-stu-id="e801a-167">Select **Advanced Options**.</span></span>

6. <span data-ttu-id="e801a-168">選取 **[從雲端復原**]。</span><span class="sxs-lookup"><span data-stu-id="e801a-168">Select **Recover from the cloud**.</span></span> <span data-ttu-id="e801a-169"> (（您也可以選取 [ **重設**]）。</span><span class="sxs-lookup"><span data-stu-id="e801a-169">(Optionally, you can select **Reset**.</span></span> <span data-ttu-id="e801a-170">不過， **從雲端復原** 是建議的方法。 ) </span><span class="sxs-lookup"><span data-stu-id="e801a-170">However, **Recover from the cloud** is the recommended approach.)</span></span>

   ![從雲端復原](images/recover-from-cloud.png)
7. <span data-ttu-id="e801a-172">如果系統提示您輸入 Bitlocker 金鑰，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="e801a-172">If you are prompted to enter the Bitlocker key, do one of the following:</span></span>

   - <span data-ttu-id="e801a-173">若要保留 Bitlocker 在 Surface Hub 上保護的資訊，請輸入 Bitlocker 金鑰。</span><span class="sxs-lookup"><span data-stu-id="e801a-173">To preserve the information that Bitlocker protects on the Surface Hub, enter the Bitlocker key.</span></span>
   - <span data-ttu-id="e801a-174">若要捨棄受保護的資訊，請選取 [**略過此磁片磁碟機**]</span><span class="sxs-lookup"><span data-stu-id="e801a-174">To discard the protected information, select **Skip this drive**</span></span>  

8. <span data-ttu-id="e801a-175">出現提示時，請選取 [ **重新安裝**]。</span><span class="sxs-lookup"><span data-stu-id="e801a-175">When you are prompted, select **Reinstall**.</span></span>

    ![重新安裝](images/reinstall.png)

9. <span data-ttu-id="e801a-177">若要重新分區磁片，請選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="e801a-177">To repartition the disk, select **Yes**.</span></span>

   ![重新分割](images/repartition.png)

   <span data-ttu-id="e801a-179">首先，恢復程式會從雲端下載作業系統影像。</span><span class="sxs-lookup"><span data-stu-id="e801a-179">First, the recovery process downloads the operating system image from the cloud.</span></span>  

   ![下載 97&](images/recover-progress.png)

   <span data-ttu-id="e801a-181">下載完成後，恢復程式會根據您選取的選項，復原 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="e801a-181">When the download finishes, the recovery process restores the Surface Hub according to the options that you selected.</span></span>
   

## <span data-ttu-id="e801a-182">連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="e801a-182">Contact Support</span></span>

<span data-ttu-id="e801a-183">如果您有任何疑問或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="e801a-183">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <span data-ttu-id="e801a-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="e801a-184">Related topics</span></span>

[<span data-ttu-id="e801a-185">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="e801a-185">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="e801a-186">Microsoft Surface Hub 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="e801a-186">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
