---
title: 重設或復原 Surface Hub
description: 說明 Surface Hub 的重設及復原程式，並提供指示。
ms.assetid: 44E82EEE-1905-464B-A758-C2A1463909FF
ms.reviewer: ''
manager: laurawi
keywords: 重設 Surface Hub，復原
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/10/2021
ms.localizationpriority: medium
ms.openlocfilehash: 4b6797a83936b919aa43a7ae9fc8ae4dd720223a
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406616"
---
# <a name="reset-or-recover-a-surface-hub"></a><span data-ttu-id="a28ac-104">重設或復原 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a28ac-104">Reset or recover a Surface Hub</span></span>

<span data-ttu-id="a28ac-105">本文說明如何重設或復原 Microsoft Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a28ac-105">This article describes how to reset or recover a Microsoft Surface Hub.</span></span>  

<span data-ttu-id="a28ac-106">[重設 Surface Hub 會](#reset-a-surface-hub) 將其作業系統回到上一次累積 Windows 更新，並移除所有本地使用者檔案和設定資訊。</span><span class="sxs-lookup"><span data-stu-id="a28ac-106">[Resetting the Surface Hub](#reset-a-surface-hub) returns its operating system to the last cumulative Windows update, and removes all local user files and configuration information.</span></span> <span data-ttu-id="a28ac-107">移除的資訊包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="a28ac-107">The information that is removed includes the following:</span></span>

- <span data-ttu-id="a28ac-108">裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="a28ac-108">The device account</span></span>
- <span data-ttu-id="a28ac-109">裝置當地系統管理員的帳戶資訊</span><span class="sxs-lookup"><span data-stu-id="a28ac-109">Account information for the device's local administrators</span></span>
- <span data-ttu-id="a28ac-110">網域加入或 Azure AD-join 資訊</span><span class="sxs-lookup"><span data-stu-id="a28ac-110">Domain-join or Azure AD-join information</span></span>
- <span data-ttu-id="a28ac-111">行動裝置管理 (MDM) 註冊資訊</span><span class="sxs-lookup"><span data-stu-id="a28ac-111">Mobile Device Management (MDM) enrollment information</span></span>
- <span data-ttu-id="a28ac-112">使用 MDM 或設定應用程式所設定設定的資訊</span><span class="sxs-lookup"><span data-stu-id="a28ac-112">Configuration information that was set by using MDM or the Settings app</span></span>

<span data-ttu-id="a28ac-113">[從雲端復原 Surface Hub](#recover-a-surface-hub-from-the-cloud) 也會移除這項資訊。</span><span class="sxs-lookup"><span data-stu-id="a28ac-113">[Recovering a Surface Hub from the cloud](#recover-a-surface-hub-from-the-cloud) also removes this information.</span></span> <span data-ttu-id="a28ac-114">此外，Surface Hub 會下載新的作業系統映射並安裝。</span><span class="sxs-lookup"><span data-stu-id="a28ac-114">In addition, the Surface Hub downloads a new operating system image and installs it.</span></span> <span data-ttu-id="a28ac-115">您可以指定復原程式是否保留儲存在 Surface Hub 上的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a28ac-115">You can specify whether the recovery process preserves other information that is stored on the Surface Hub.</span></span> <span data-ttu-id="a28ac-116">如果您需要復原 Surface [Hub，](surface-hub-recovery-tool.md) 但無法針對其中任何一個選項使用 Surface Hub，Surface Hub 修復工具會使用相同的作業系統映射。</span><span class="sxs-lookup"><span data-stu-id="a28ac-116">The same operating system image is used by the [Surface Hub Recovery Tool](surface-hub-recovery-tool.md) if you need to recover a Surface Hub for which neither of these options can be used.</span></span>

## <a name="reset-a-surface-hub"></a><span data-ttu-id="a28ac-117">重設 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a28ac-117">Reset a Surface Hub</span></span>

<span data-ttu-id="a28ac-118">您可能需要重設 Surface Hub 的原因如下：</span><span class="sxs-lookup"><span data-stu-id="a28ac-118">You may have to reset your Surface Hub for reasons such as the following:</span></span>

- <span data-ttu-id="a28ac-119">您正重新配置裝置以用於新的會議空間，並想要重新進行重新配置。</span><span class="sxs-lookup"><span data-stu-id="a28ac-119">You are re-purposing the device for a new meeting space and want to reconfigure it.</span></span>
- <span data-ttu-id="a28ac-120">您想要變更在本機管理裝置的方式。</span><span class="sxs-lookup"><span data-stu-id="a28ac-120">You want to change how you locally manage the device.</span></span>
- <span data-ttu-id="a28ac-121">裝置帳戶或系統管理員帳戶的使用者名稱或密碼已遺失。</span><span class="sxs-lookup"><span data-stu-id="a28ac-121">The user name or password for the device account or the Administrator account has been lost.</span></span>
- <span data-ttu-id="a28ac-122">安裝更新之後，裝置執行會降低。</span><span class="sxs-lookup"><span data-stu-id="a28ac-122">After you install an update, the performance of the device decreases.</span></span>

<span data-ttu-id="a28ac-123">在重設程式期間，如果您看到螢幕很長一段時間，請稍候，不要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="a28ac-123">During the reset process, if you see a blank screen for long periods of time, please wait and do not take any action.</span></span>

> [!WARNING]
> <span data-ttu-id="a28ac-124">裝置重設程式最多可能需要六個小時。</span><span class="sxs-lookup"><span data-stu-id="a28ac-124">The device reset process may take up to six hours.</span></span> <span data-ttu-id="a28ac-125">在程式完成之前，請勿關閉或拔除 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a28ac-125">Do not turn off or unplug the Surface Hub until the process has finished.</span></span> <span data-ttu-id="a28ac-126">如果您中斷程式，裝置就會無法操作。</span><span class="sxs-lookup"><span data-stu-id="a28ac-126">If you interrupt the process, the device becomes inoperable.</span></span> <span data-ttu-id="a28ac-127">裝置需要保固服務才能再次運作。</span><span class="sxs-lookup"><span data-stu-id="a28ac-127">The device requires warranty service in order to become functional again.</span></span>

1. <span data-ttu-id="a28ac-128">在 Surface Hub 上，開啟 **\[設定\]**。</span><span class="sxs-lookup"><span data-stu-id="a28ac-128">On your Surface Hub, open **Settings**.</span></span>

   ![顯示 Surface Hub 的設定應用程式的影像。](images/sh-settings.png)

2. <span data-ttu-id="a28ac-130">選取 **更新&安全性**。</span><span class="sxs-lookup"><span data-stu-id="a28ac-130">Select **Update & Security**.</span></span>

   ![顯示 Surface Hub &設定應用程式中更新安全性群組的影像。](images/sh-settings-update-security.png)

3. <span data-ttu-id="a28ac-132">選取 **復原**， **然後在重設**裝置下選取 **開始使用**。</span><span class="sxs-lookup"><span data-stu-id="a28ac-132">Select **Recovery**, and then, under **Reset device**, select **Get started**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="a28ac-133">在重設裝置之前，請確認您擁有 BitLocker 金鑰，因為稍後會提示您輸入。</span><span class="sxs-lookup"><span data-stu-id="a28ac-133">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="a28ac-134">若要深入瞭解，請參閱儲存 [BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="a28ac-134">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span> <span data-ttu-id="a28ac-135">當中樞重新開機至修復磁碟分割時，會提示您輸入 BitLocker 鍵。</span><span class="sxs-lookup"><span data-stu-id="a28ac-135">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="a28ac-136">略過該提示會導致重設失敗。</span><span class="sxs-lookup"><span data-stu-id="a28ac-136">Skipping that prompt will cause reset to fail.</span></span>
   
   ![顯示 Surface Hub 設定應用程式中的重設裝置選項的影像。](images/sh-settings-reset-device.png)

   <span data-ttu-id="a28ac-138">重設程式完成之後，Surface Hub 會再次啟動 [第一個執行](first-run-program-surface-hub.md) 程式。</span><span class="sxs-lookup"><span data-stu-id="a28ac-138">After the reset process finishes, the Surface Hub starts the [first run program](first-run-program-surface-hub.md) again.</span></span> <span data-ttu-id="a28ac-139">如果重設程式發生問題，它會將 Surface Hub 卷回先前現有的作業系統映射，然後顯示歡迎畫面。</span><span class="sxs-lookup"><span data-stu-id="a28ac-139">If the reset process encounters a problem, it rolls the Surface Hub back to the previously-existing operating system image and then displays the Welcome screen.</span></span>

<span id="cloud-recovery" />

## <a name="recover-a-surface-hub-from-the-cloud"></a><span data-ttu-id="a28ac-140">從雲端復原 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a28ac-140">Recover a Surface Hub from the cloud</span></span>

<span data-ttu-id="a28ac-141">如果 Surface Hub 因某種原因無法使用，您仍可在未獲得 Microsoft 支援服務協助的情況下從雲端復原。</span><span class="sxs-lookup"><span data-stu-id="a28ac-141">If for some reason the Surface Hub becomes unusable, you can still recover it from the cloud without assistance from Microsoft Support.</span></span> <span data-ttu-id="a28ac-142">Surface Hub 可以從雲端下載全新的作業系統映射，然後使用該映射重新安裝其作業系統。</span><span class="sxs-lookup"><span data-stu-id="a28ac-142">The Surface Hub can download a fresh operating system image from the cloud, and use that image to reinstall its operating system.</span></span>

<span data-ttu-id="a28ac-143">在下列情況下，您可能必須使用此類型的復原程式：</span><span class="sxs-lookup"><span data-stu-id="a28ac-143">You may have to use this type of recovery process under the following circumstances:</span></span>

- [<span data-ttu-id="a28ac-144">Surface Hub 或其相關帳戶已進入不穩定狀態</span><span class="sxs-lookup"><span data-stu-id="a28ac-144">The Surface Hub or its related accounts have entered an unstable state</span></span>](#recover-a-surface-hub-in-a-bad-state)
- [<span data-ttu-id="a28ac-145">Surface Hub 已鎖定</span><span class="sxs-lookup"><span data-stu-id="a28ac-145">The Surface Hub is locked</span></span>](#recover-a-locked-surface-hub)

>[!IMPORTANT]
><span data-ttu-id="a28ac-146">從 **雲端程式復原** 需要有線連接，提供開放式網際網路連接， (Proxy 或其他驗證提示) 。</span><span class="sxs-lookup"><span data-stu-id="a28ac-146">The **Recover from the cloud** process requires a wired connection that provides open internet connectivity (no proxy or other authentication prompts).</span></span>

### <a name="recover-a-surface-hub-in-a-bad-state"></a><span data-ttu-id="a28ac-147">還原不良狀態中的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a28ac-147">Recover a Surface Hub in a bad state</span></span>

<span data-ttu-id="a28ac-148">如果裝置帳戶進入不穩定狀態，或系統管理員帳戶遇到問題，您可以使用設定應用程式啟動雲端復原程式。</span><span class="sxs-lookup"><span data-stu-id="a28ac-148">If the device account gets into an unstable state or if the administrator account encounters problems, you can use the Settings app to start the cloud recovery process.</span></span> <span data-ttu-id="a28ac-149">只有當裝置重設程式無法修正問題時，[](#reset-a-surface-hub)才應該使用雲端復原程式。</span><span class="sxs-lookup"><span data-stu-id="a28ac-149">You should only use the cloud recovery process when the [device reset](#reset-a-surface-hub) process doesn't fix the problem.</span></span>

1. <span data-ttu-id="a28ac-150">在 Surface Hub 上，選取 **安全性** &gt; **&更新** &gt; \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="a28ac-150">On your Surface Hub, select **Settings** &gt; **Update & security** &gt; **Recovery**.</span></span>

2. <span data-ttu-id="a28ac-151">在 **雲端復原下，** 選取立即 **重新開機**。</span><span class="sxs-lookup"><span data-stu-id="a28ac-151">Under **Recover from the cloud**, select **Restart now**.</span></span>

   ![從雲端復原](images/recover-from-the-cloud.png)

### <a name="recover-a-locked-surface-hub"></a><span data-ttu-id="a28ac-153">復原鎖定的 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a28ac-153">Recover a locked Surface Hub</span></span>

<span data-ttu-id="a28ac-154">在極少數的情況下，Surface Hub 可能會在工作階段末端清理使用者和應用程式資料時遇到錯誤。</span><span class="sxs-lookup"><span data-stu-id="a28ac-154">On rare occasions, a Surface Hub may encounter an error while cleaning up user and app data at the end of a session.</span></span> <span data-ttu-id="a28ac-155">發生這種情況時，裝置會自動重新開機，並再次嘗試執行作業。</span><span class="sxs-lookup"><span data-stu-id="a28ac-155">When this happens, the device automatically restarts and tries the operation again.</span></span> <span data-ttu-id="a28ac-156">但如果此作業重複失敗，裝置會自動鎖定以保護使用者資料。</span><span class="sxs-lookup"><span data-stu-id="a28ac-156">But if this operation fails repeatedly, the device automatically locks to protect user data.</span></span> <span data-ttu-id="a28ac-157">若要解除鎖定裝置，您必須 [重](#reset-a-surface-hub) 設裝置，如果還是無法解除鎖定，請從雲端復原。</span><span class="sxs-lookup"><span data-stu-id="a28ac-157">To unlock it, you must [reset the device](#reset-a-surface-hub) or, if that doesn't work, recover it from the cloud.</span></span>

1. <span data-ttu-id="a28ac-158">找出 Surface Hub 底部的電源開關。</span><span class="sxs-lookup"><span data-stu-id="a28ac-158">Locate the power switch on the bottom of Surface Hub.</span></span> <span data-ttu-id="a28ac-159">電源開關位於電源線連接旁邊。</span><span class="sxs-lookup"><span data-stu-id="a28ac-159">The power switch is next to the power cord connection.</span></span> <span data-ttu-id="a28ac-160">有關電源開關的資訊，請參閱 SURFACE Hub 網站備 ([指南) 。](surface-hub-site-readiness-guide.md)</span><span class="sxs-lookup"><span data-stu-id="a28ac-160">For more information about the power switch, see the [Surface Hub Site Readiness Guide (PDF)](surface-hub-site-readiness-guide.md).</span></span>

2. <span data-ttu-id="a28ac-161">當 Surface Hub 顯示歡迎畫面時，請使用電源開關關閉 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a28ac-161">While the Surface Hub displays the Welcome screen, use the power switch to turn off the Surface Hub.</span></span>

3. <span data-ttu-id="a28ac-162">使用電源開關重新開啟 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a28ac-162">Use the power switch to turn the Surface Hub back on.</span></span> <span data-ttu-id="a28ac-163">裝置會啟動並顯示 Surface Hub 標誌畫面。</span><span class="sxs-lookup"><span data-stu-id="a28ac-163">The device starts and displays the Surface Hub Logo screen.</span></span> <span data-ttu-id="a28ac-164">當您在 Surface Hub 標誌下看到旋轉點時，請使用電源開關再次關閉 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="a28ac-164">When you see spinning dots under the Surface Hub Logo, use the power switch to turn the Surface Hub off again.</span></span>  

4. <span data-ttu-id="a28ac-165">重複步驟 3 三次，或直到 Surface Hub 顯示「準備自動修復」訊息。</span><span class="sxs-lookup"><span data-stu-id="a28ac-165">Repeat step 3 three times, or until the Surface Hub displays the "Preparing Automatic Repair" message.</span></span> <span data-ttu-id="a28ac-166">顯示這則訊息之後，Surface Hub 會顯示 Windows RE 畫面。</span><span class="sxs-lookup"><span data-stu-id="a28ac-166">After it displays this message, the Surface Hub displays the Windows RE screen.</span></span>

 
5. <span data-ttu-id="a28ac-167">選取**重設以重新安裝 Windows。**</span><span class="sxs-lookup"><span data-stu-id="a28ac-167">Select **Reset to re-install Windows**.</span></span> 
![重設以重新安裝](images/recover-from-cloud.png)

8. <span data-ttu-id="a28ac-169">選取 **雲端下載。**</span><span class="sxs-lookup"><span data-stu-id="a28ac-169">Select **Cloud download.**</span></span> 

   ![雲端下載](images/recover-cloud-download.png)

>[!IMPORTANT]
><span data-ttu-id="a28ac-171">如果您收到錯誤訊息指出無法下載 **，** 請選取 **取消** ，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="a28ac-171">If you get an error message indicating **Unable to Download**, select **Cancel** and try again.</span></span>

9. <span data-ttu-id="a28ac-172">選取**完全清除硬碟。**  
![復原並完全清除硬碟</span><span class="sxs-lookup"><span data-stu-id="a28ac-172">Select **Fully clean the drive.** 
![recover and fully clean drive</span></span>](images/recover-fully-clean-drive.png)

10. <span data-ttu-id="a28ac-173">系統將會詢問您是否**準備好重設此裝置？**</span><span class="sxs-lookup"><span data-stu-id="a28ac-173">You will be asked **Are you ready to reset this device?**.</span></span> <span data-ttu-id="a28ac-174">選取 [重設]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a28ac-174">Select **Reset**.</span></span> 
![復原並確認重設](images/recover-confirm-reset.png)

11. <span data-ttu-id="a28ac-176">下載會開始，且復原程式會 **指出要重設此裝置**。</span><span class="sxs-lookup"><span data-stu-id="a28ac-176">The download begins and the recovery process indicates **Resetting this device**.</span></span> 
![顯示進行中的復原](images/recover-in-progress.png)

## <a name="contact-support"></a><span data-ttu-id="a28ac-178">連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="a28ac-178">Contact Support</span></span>

<span data-ttu-id="a28ac-179">如果您有任何問題或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="a28ac-179">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>


## <a name="related-topics"></a><span data-ttu-id="a28ac-180">相關主題</span><span class="sxs-lookup"><span data-stu-id="a28ac-180">Related topics</span></span>

[<span data-ttu-id="a28ac-181">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="a28ac-181">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="a28ac-182">Microsoft Surface Hub 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="a28ac-182">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)
