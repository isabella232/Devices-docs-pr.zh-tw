---
title: 結束工作階段 - 結束 Surface Hub 會議
description: 若要結束 Surface Hub 會議，請點選 \[結束工作階段\]。 Surface Hub 會清除應用程式狀態、作業系統狀態以及使用者介面，這樣 Surface Hub 就可以準備進行下一場會議。
keywords: 我已完成, 結束 Surface Hub 會議, 完成 Surface Hub 會議, 清除 Surface Hub 會議
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: b18bc4b15b8a3925aeecdd9999b09b61011d1db5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831845"
---
# <span data-ttu-id="702f4-105">利用 \[結束工作階段\] 結束 Surface Hub 會議</span><span class="sxs-lookup"><span data-stu-id="702f4-105">End a Surface Hub meeting with End session</span></span>
<span data-ttu-id="702f4-106">Surface Hub 為針對由不同群組的人員在會議空間中使用所設計的共同作業裝置。</span><span class="sxs-lookup"><span data-stu-id="702f4-106">Surface Hub is a collaboration device designed to be used in meeting spaces by different groups of people.</span></span> <span data-ttu-id="702f4-107">在結束會議時，使用者可以點選 **\[結束工作階段\]** 來清除任何敏感性資料，並準備裝置以供下一場會議。</span><span class="sxs-lookup"><span data-stu-id="702f4-107">At the end of a meeting, users can tap **End session** to clean up any sensitive data and prepare the device for the next meeting.</span></span> <span data-ttu-id="702f4-108">Surface Hub 將會清理 (或重設) 下列狀態：</span><span class="sxs-lookup"><span data-stu-id="702f4-108">Surface Hub will clean up, or reset, the following states:</span></span>
- <span data-ttu-id="702f4-109">應用程式</span><span class="sxs-lookup"><span data-stu-id="702f4-109">Applications</span></span>
- <span data-ttu-id="702f4-110">作業系統</span><span class="sxs-lookup"><span data-stu-id="702f4-110">Operating system</span></span>
- <span data-ttu-id="702f4-111">使用者介面</span><span class="sxs-lookup"><span data-stu-id="702f4-111">User interface</span></span>

<span data-ttu-id="702f4-112">這個主題說明 **\[結束工作階段\]** 會為每一個狀態重設什麼項目。</span><span class="sxs-lookup"><span data-stu-id="702f4-112">This topic explains what **End session** resets for each of these states.</span></span>

## <span data-ttu-id="702f4-113">應用程式</span><span class="sxs-lookup"><span data-stu-id="702f4-113">Applications</span></span>
<span data-ttu-id="702f4-114">當您在 Surface Hub 上啟動應用程式時，應用程式會儲存在記憶體，而資料會儲存在應用程式層級。</span><span class="sxs-lookup"><span data-stu-id="702f4-114">When you start apps on Surface Hub, they are stored in memory and data is stored at the application level.</span></span> <span data-ttu-id="702f4-115">資料會在該工作階段 (或會議) 期間提供給所有使用者使用，直到資料遭到移除或覆寫。</span><span class="sxs-lookup"><span data-stu-id="702f4-115">Data is available to all users during that session (or meeting) until date is removed or overwritten.</span></span> <span data-ttu-id="702f4-116">當選取 **\[結束工作階段\]** 時，會關閉應用程式、刪除瀏覽器歷程記錄、重設應用程式，以及移除 Skype 記錄檔，藉此清除 Surface Hub 應用程式狀態。</span><span class="sxs-lookup"><span data-stu-id="702f4-116">When **End session** is selected, Surface Hub application state is cleared out by closing applications, deleting browser history, resetting applications, and removing Skype logs.</span></span>

### <span data-ttu-id="702f4-117">關閉應用程式</span><span class="sxs-lookup"><span data-stu-id="702f4-117">Close applications</span></span>
<span data-ttu-id="702f4-118">Surface Hub 會關閉所有顯示的視窗，包括 Win32 和通用 Windows 平台 (UWP) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="702f4-118">Surface Hub closes all visible windows, including Win32 and Universal Windows Platform (UWP) applications.</span></span> <span data-ttu-id="702f4-119">應用程式關閉階段使用多工處理檢視，以查詢顯示的視窗。</span><span class="sxs-lookup"><span data-stu-id="702f4-119">The application close stage uses the multitasking view to query the visible windows.</span></span> <span data-ttu-id="702f4-120">未在特定時間範圍內關閉的 Win32 視窗，會使用 **TerminateProcess** 來關閉。</span><span class="sxs-lookup"><span data-stu-id="702f4-120">Win32 windows that do not close within a certain timeframe are closed using **TerminateProcess**.</span></span> 
   
### <span data-ttu-id="702f4-121">刪除瀏覽器歷程記錄</span><span class="sxs-lookup"><span data-stu-id="702f4-121">Delete browser history</span></span>
<span data-ttu-id="702f4-122">Surface Hub 會在 Edge 中使用瀏覽器歷程記錄 (DBH)，以清除 Edge 歷程記錄及快取的資料。</span><span class="sxs-lookup"><span data-stu-id="702f4-122">Surface Hub uses Delete Browser History (DBH) in Edge to clear Edge history and cached data.</span></span> <span data-ttu-id="702f4-123">這和使用者如何手動清除其瀏覽器歷程記錄很類似，但是 **\[結束工作階段\]** 還會在下一個工作階段或會議開始之前，確保將應用程式狀態清除並移除資料。</span><span class="sxs-lookup"><span data-stu-id="702f4-123">This is similar to how a user can clear out their browser history manually, but **End session** also ensures that application states are cleared and data is removed before the next session, or meeting, starts.</span></span> 
 
### <span data-ttu-id="702f4-124">重設應用程式</span><span class="sxs-lookup"><span data-stu-id="702f4-124">Reset applications</span></span>
<span data-ttu-id="702f4-125">**\[結束工作階段\]** 會重設 Surface Hub 上所安裝每一個應用程式的狀態。</span><span class="sxs-lookup"><span data-stu-id="702f4-125">**End session** resets the state of each application that is installed on the Surface Hub.</span></span> <span data-ttu-id="702f4-126">重設應用程式會清除所有背景工作、應用程式資料、通知及使用者同意對話方塊。</span><span class="sxs-lookup"><span data-stu-id="702f4-126">Resetting an application clears all background tasks, application data, notifications, and user consent dialogs.</span></span> <span data-ttu-id="702f4-127">應用程式會返回其初次執行狀態，以供下一位使用 Surface Hub 的人使用。</span><span class="sxs-lookup"><span data-stu-id="702f4-127">Applications are returned to their first-run state for the next people that use Surface Hub.</span></span>  
 
### <span data-ttu-id="702f4-128">移除 Skype 記錄檔</span><span class="sxs-lookup"><span data-stu-id="702f4-128">Remove Skype logs</span></span>
<span data-ttu-id="702f4-129">Skype 不會在 Surface Hub 上儲存個人識別資訊。</span><span class="sxs-lookup"><span data-stu-id="702f4-129">Skype does not store personally-identifiable information on Surface Hub.</span></span> <span data-ttu-id="702f4-130">資訊是儲存在 Skype 服務，以符合現有的商務用 Skype 指導方針。</span><span class="sxs-lookup"><span data-stu-id="702f4-130">Information is stored in the Skype service to meet existing Skype for Business guidance.</span></span> <span data-ttu-id="702f4-131">當選取 **\[結束工作階段\]** 時，唯一會移除的資料是本機 Skype 記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="702f4-131">Local Skype logging information is the only data removed when **End session** is selected.</span></span> <span data-ttu-id="702f4-132">這包含整合通訊用戶端平台 (UCCP) 記錄檔和媒體記錄檔。</span><span class="sxs-lookup"><span data-stu-id="702f4-132">This includes Unified Communications Client Platform (UCCP) logs and media logs.</span></span>   

## <span data-ttu-id="702f4-133">作業系統</span><span class="sxs-lookup"><span data-stu-id="702f4-133">Operating System</span></span>
<span data-ttu-id="702f4-134">作業系統裝載有關每個 Surface Hub 會議後所需清除工作階段狀態的各種不同資訊。</span><span class="sxs-lookup"><span data-stu-id="702f4-134">The operating system hosts a variety of information about the state of the sessions that needs to be cleared after each Surface Hub meeting.</span></span> 

### <span data-ttu-id="702f4-135">檔案系統</span><span class="sxs-lookup"><span data-stu-id="702f4-135">File System</span></span>
<span data-ttu-id="702f4-136">會議出席者可以存取 Surface Hub 上的一組有限目錄。</span><span class="sxs-lookup"><span data-stu-id="702f4-136">Meeting attendees have access to a limited set of directories on the Surface Hub.</span></span> <span data-ttu-id="702f4-137">當選取 **\[結束工作階段\]** 時，Surface Hub 會清除這些目錄︰</span><span class="sxs-lookup"><span data-stu-id="702f4-137">When **End session** is selected, Surface Hub clears these directories:</span></span><br>
- <span data-ttu-id="702f4-138">音樂</span><span class="sxs-lookup"><span data-stu-id="702f4-138">Music</span></span>
- <span data-ttu-id="702f4-139">影片</span><span class="sxs-lookup"><span data-stu-id="702f4-139">Videos</span></span>
- <span data-ttu-id="702f4-140">文件</span><span class="sxs-lookup"><span data-stu-id="702f4-140">Documents</span></span>
- <span data-ttu-id="702f4-141">圖片</span><span class="sxs-lookup"><span data-stu-id="702f4-141">Pictures</span></span>
- <span data-ttu-id="702f4-142">下載</span><span class="sxs-lookup"><span data-stu-id="702f4-142">Downloads</span></span>

<span data-ttu-id="702f4-143">Surface Hub 也會清除以下這些目錄，因為許多應用程式經常會在其中寫入資料︰</span><span class="sxs-lookup"><span data-stu-id="702f4-143">Surface Hub also clears these directories, since many applications often write to them:</span></span>
- <span data-ttu-id="702f4-144">桌面</span><span class="sxs-lookup"><span data-stu-id="702f4-144">Desktop</span></span>
- <span data-ttu-id="702f4-145">我的最愛</span><span class="sxs-lookup"><span data-stu-id="702f4-145">Favorites</span></span>
- <span data-ttu-id="702f4-146">最近</span><span class="sxs-lookup"><span data-stu-id="702f4-146">Recent</span></span>
- <span data-ttu-id="702f4-147">公用文件</span><span class="sxs-lookup"><span data-stu-id="702f4-147">Public Documents</span></span>
- <span data-ttu-id="702f4-148">公用音樂</span><span class="sxs-lookup"><span data-stu-id="702f4-148">Public Music</span></span>
- <span data-ttu-id="702f4-149">公用影片</span><span class="sxs-lookup"><span data-stu-id="702f4-149">Public Videos</span></span>
- <span data-ttu-id="702f4-150">公用下載</span><span class="sxs-lookup"><span data-stu-id="702f4-150">Public Downloads</span></span>

### <span data-ttu-id="702f4-151">認證</span><span class="sxs-lookup"><span data-stu-id="702f4-151">Credentials</span></span>
<span data-ttu-id="702f4-152">點選 **\[結束工作階段\]** 時，會清除儲存在 **TokenBroker**、**PasswordVault** 或 **\[認證管理員\]** 的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="702f4-152">User credentials that are stored in **TokenBroker**, **PasswordVault**, or **Credential Manager** are cleared when you tap **End session**.</span></span>

## <span data-ttu-id="702f4-153">使用者介面</span><span class="sxs-lookup"><span data-stu-id="702f4-153">User interface</span></span>
<span data-ttu-id="702f4-154">選取 **\[結束工作階段\]** 時，使用者介面 (UI) 設定會返回到其預設值。</span><span class="sxs-lookup"><span data-stu-id="702f4-154">User interface (UI) settings are returned to their default values when **End session** is selected.</span></span> 

### <span data-ttu-id="702f4-155">UI 項目</span><span class="sxs-lookup"><span data-stu-id="702f4-155">UI items</span></span>
- <span data-ttu-id="702f4-156">將快速控制項目重設為預設狀態</span><span class="sxs-lookup"><span data-stu-id="702f4-156">Reset Quick Actions to default state</span></span>
- <span data-ttu-id="702f4-157">清除快顯通知</span><span class="sxs-lookup"><span data-stu-id="702f4-157">Clear Toast notifications</span></span>
- <span data-ttu-id="702f4-158">重設音量</span><span class="sxs-lookup"><span data-stu-id="702f4-158">Reset volume levels</span></span>
- <span data-ttu-id="702f4-159">重設資訊看板寬度</span><span class="sxs-lookup"><span data-stu-id="702f4-159">Reset sidebar width</span></span>
- <span data-ttu-id="702f4-160">重設平板電腦模式配置</span><span class="sxs-lookup"><span data-stu-id="702f4-160">Reset tablet mode layout</span></span>
- <span data-ttu-id="702f4-161">登入使用者退出 Office 365 會議與檔案</span><span class="sxs-lookup"><span data-stu-id="702f4-161">Sign user out of Office 365 meetings and files</span></span>

### <span data-ttu-id="702f4-162">協助工具</span><span class="sxs-lookup"><span data-stu-id="702f4-162">Accessibility</span></span>
<span data-ttu-id="702f4-163">選取 **\[結束工作階段\]** 時，協助工具功能與應用程式會返回預設設定。</span><span class="sxs-lookup"><span data-stu-id="702f4-163">Accessibility features and apps are returned to default settings when **End session** is selected.</span></span>
- <span data-ttu-id="702f4-164">篩選鍵</span><span class="sxs-lookup"><span data-stu-id="702f4-164">Filter keys</span></span>
- <span data-ttu-id="702f4-165">高對比</span><span class="sxs-lookup"><span data-stu-id="702f4-165">High contrast</span></span>
- <span data-ttu-id="702f4-166">相黏鍵</span><span class="sxs-lookup"><span data-stu-id="702f4-166">Sticky keys</span></span>
- <span data-ttu-id="702f4-167">切換鍵</span><span class="sxs-lookup"><span data-stu-id="702f4-167">Toggle keys</span></span>
- <span data-ttu-id="702f4-168">滑鼠鍵</span><span class="sxs-lookup"><span data-stu-id="702f4-168">Mouse keys</span></span>
- <span data-ttu-id="702f4-169">放大鏡</span><span class="sxs-lookup"><span data-stu-id="702f4-169">Magnifier</span></span>
- <span data-ttu-id="702f4-170">朗讀程式</span><span class="sxs-lookup"><span data-stu-id="702f4-170">Narrator</span></span>

### <span data-ttu-id="702f4-171">剪貼簿</span><span class="sxs-lookup"><span data-stu-id="702f4-171">Clipboard</span></span>
<span data-ttu-id="702f4-172">剪貼簿會被清除，以將工作階段期間複製到剪貼簿的資料移除。</span><span class="sxs-lookup"><span data-stu-id="702f4-172">The clipboard is cleared to remove data that was copied to the clipboard during the session.</span></span> 

## <span data-ttu-id="702f4-173">常見問題集</span><span class="sxs-lookup"><span data-stu-id="702f4-173">Frequently asked questions</span></span>
**<span data-ttu-id="702f4-174">如果我在會議尾聲忘了點選 \[結束工作階段\]，會發生什麼事？其他人稍後可以使用 Surface Hub 嗎？</span><span class="sxs-lookup"><span data-stu-id="702f4-174">What happens if I forget to tap End session at the end of a meeting, and someone else uses the Surface Hub later?</span></span>**<br>
<span data-ttu-id="702f4-175">Surface Hub 只會在使用者點選 **\[結束工作階段\]** 時清理會議內容。</span><span class="sxs-lookup"><span data-stu-id="702f4-175">Surface Hub only cleans up meeting content when users tap **End session**.</span></span> <span data-ttu-id="702f4-176">如果您沒有點選 **\[結束工作階段\]** 便離開會議，該裝置會在經過一段時間之後返回歡迎畫面。</span><span class="sxs-lookup"><span data-stu-id="702f4-176">If you leave the meeting without tapping **End session**, the device will return to the welcome screen after some time.</span></span> <span data-ttu-id="702f4-177">在歡迎畫面上，使用者將可以選擇繼續先前的工作階段，或是開始新的工作階段。</span><span class="sxs-lookup"><span data-stu-id="702f4-177">From the welcome screen, users have the option to resume the previous session or start a new one.</span></span> <span data-ttu-id="702f4-178">您也可以停用若未按下 **\[結束工作階段\]** 時繼續工作階段的功能。</span><span class="sxs-lookup"><span data-stu-id="702f4-178">You can also disable the ability to resume a session if **End session** is not pressed.</span></span>

**<span data-ttu-id="702f4-179">文件可以復原嗎？</span><span class="sxs-lookup"><span data-stu-id="702f4-179">Are documents recoverable?</span></span>**<br> <span data-ttu-id="702f4-180">選取 **\[結束工作階段\]** 時，會隨即從硬碟機移除檔案，就像是從硬碟機刪除任何其他檔案一樣。</span><span class="sxs-lookup"><span data-stu-id="702f4-180">Removing files from the hard drive when **End session** is selected is just like any other file deletion from a hard disk drive.</span></span> <span data-ttu-id="702f4-181">協力廠商軟體也許能夠從硬碟機復原資料，但 Surface Hub 上不支援檔案復原功能。</span><span class="sxs-lookup"><span data-stu-id="702f4-181">Third-party software might be able to recover data from the hard disk drive, but file recovery is not a supported feature on Surface Hub.</span></span> <span data-ttu-id="702f4-182">若要防止資料遺失，請在離開會議前儲存所需的資料。</span><span class="sxs-lookup"><span data-stu-id="702f4-182">To prevent data loss, always save the data you need before leaving a meeting.</span></span>

**<span data-ttu-id="702f4-183">從 \[結束工作階段\] 所執行的清除動作符合美國國防部的清除與處理標準︰DoD 5220.22-M 嗎？</span><span class="sxs-lookup"><span data-stu-id="702f4-183">Do the clean-up actions from End session comply with the US Department of Defense clearing and sanitizing standard: DoD 5220.22-M?</span></span>**<br>
<span data-ttu-id="702f4-184">否。</span><span class="sxs-lookup"><span data-stu-id="702f4-184">No.</span></span> <span data-ttu-id="702f4-185">目前，從 **\[結束工作階段\]** 所執行的清除動作尚不符合這個標準。</span><span class="sxs-lookup"><span data-stu-id="702f4-185">Currently, the clean-up actions from **End session** do not comply with this standard.</span></span>  
  
