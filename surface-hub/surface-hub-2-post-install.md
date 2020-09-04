---
title: 在 Surface Hub 2 上設定 Windows 10 專業版或企業版
description: 本文包含可確保使用個人化大型螢幕觸控和手寫筆電腦時的最佳體驗的建議。
keywords: Surface Hub、Windows 10、桌面、安裝、設定
ms.prod: surface-hub
ms.mktglfcycl: deploy
ms.localizationpriority: low
ms.sitesec: library
ms.pagetype: deploy
audience: admin
manager: laurawi
ms.audience: itpro
author: greg-lindsay
ms.collection: M365-modern-desktop
ms.topic: article
ms.openlocfilehash: 47852284c35d213b81dd7b87ca875b400d8c713f
ms.sourcegitcommit: c74835239cf4e304af59465fb6fc785de4a0c5cc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/03/2020
ms.locfileid: "10994589"
---
# <span data-ttu-id="dd708-104">在 Surface Hub 2 上設定 Windows 10 專業版或企業版</span><span class="sxs-lookup"><span data-stu-id="dd708-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

**<span data-ttu-id="dd708-105">適用于： Surface Hub 秒</span><span class="sxs-lookup"><span data-stu-id="dd708-105">Applies to: Surface Hub 2S</span></span>** 

<span data-ttu-id="dd708-106">完成遷移至 Windows 10 專業版或企業版的安裝程式後，您可以執行下列步驟來設定 Surface Hub 2 上的 app 和設定。</span><span class="sxs-lookup"><span data-stu-id="dd708-106">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="dd708-107">建議使用這些步驟，以確保使用此個人化大型螢幕觸控和手寫筆電腦時的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="dd708-107">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="dd708-108">執行這些步驟時，您可能會發現使用有線或無線鍵盤和滑鼠很有用。</span><span class="sxs-lookup"><span data-stu-id="dd708-108">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="dd708-109">設定系統設定</span><span class="sxs-lookup"><span data-stu-id="dd708-109">Configure system settings</span></span>

1. <span data-ttu-id="dd708-110">使用具有裝置上的本機系統管理員許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="dd708-110">Sign in with an account that has local administrator privileges on the device.</span></span>  
    - <span data-ttu-id="dd708-111">在 Azure AD 已加入的裝置上，執行 Azure AD 連接的使用者會自動新增到本機管理員群組中。</span><span class="sxs-lookup"><span data-stu-id="dd708-111">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="dd708-112">Azure AD 全域系統管理員和 Azure AD 裝置管理員 [也是本機管理員](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)。</span><span class="sxs-lookup"><span data-stu-id="dd708-112">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    - <span data-ttu-id="dd708-113">您可以在命令提示字元中輸入 **net localgroup 管理員** ，以列出具有本機系統管理員許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="dd708-113">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
2. <span data-ttu-id="dd708-114">使用易記的名稱重新命名裝置，例如： **username-SHub-Desktop**。</span><span class="sxs-lookup"><span data-stu-id="dd708-114">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>
3. <span data-ttu-id="dd708-115">選取 [**啟動**  >  **設定**  >  **帳戶**] [  >  **同步處理您的設定**]，然後關閉同步處理**設定**。</span><span class="sxs-lookup"><span data-stu-id="dd708-115">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 
    - <span data-ttu-id="dd708-116">這裡使用的設定是用來啟用最佳的螢幕觸控體驗，因此您可能不想同步處理其他裝置。</span><span class="sxs-lookup"><span data-stu-id="dd708-116">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
4. <span data-ttu-id="dd708-117">將裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="dd708-117">Reboot the device.</span></span>

## <span data-ttu-id="dd708-118">啟用觸控式鍵盤與觸控板</span><span class="sxs-lookup"><span data-stu-id="dd708-118">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="dd708-119">按住或以滑鼠右鍵按一下工作列，然後選取 [ **顯示觸控式鍵盤] 按鈕** ，然後選取 [ **顯示觸控板] 按鈕**。</span><span class="sxs-lookup"><span data-stu-id="dd708-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 
    - <span data-ttu-id="dd708-120">觸控式鍵盤對直接使用者輸入很有説明，而虛擬觸控板可協助您精確選擇、懸停工具提示，或代替按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="dd708-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="dd708-121">請參閱以下範例。</span><span class="sxs-lookup"><span data-stu-id="dd708-121">See the following example.</span></span>

     ![觸控設定](images/touch.png)

2. <span data-ttu-id="dd708-123">將觸控式鍵盤設定成標準和浮動。</span><span class="sxs-lookup"><span data-stu-id="dd708-123">Configure the touch keyboard to QWERTY and floating.</span></span>
    1. <span data-ttu-id="dd708-124">選取工作列上的鍵盤圖示以顯示觸控式鍵盤。</span><span class="sxs-lookup"><span data-stu-id="dd708-124">Select the keyboard icon on the taskbar to show the touch keyboard.</span></span>
    2. <span data-ttu-id="dd708-125">在觸控式鍵盤上，選取左上角的 [鍵盤] 圖示以開啟 [鍵盤設定]。</span><span class="sxs-lookup"><span data-stu-id="dd708-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    3. <span data-ttu-id="dd708-126">選取上方列的 [最後一個鍵盤類型] 旁的 [啟用標準]，然後在第二個數據列的最後一個選項上啟用 [浮動]，這在這個大型螢幕上很有説明。</span><span class="sxs-lookup"><span data-stu-id="dd708-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="dd708-127">請參閱以下範例。</span><span class="sxs-lookup"><span data-stu-id="dd708-127">See the following examples.</span></span>

     ![鍵盤設定](images/kbd.png)

3. <span data-ttu-id="dd708-129">設定軟鍵盤設定。</span><span class="sxs-lookup"><span data-stu-id="dd708-129">Configure the soft keyboard settings.</span></span>
    1. <span data-ttu-id="dd708-130">搜尋及開啟 **輸入設定**</span><span class="sxs-lookup"><span data-stu-id="dd708-130">Search for and open **Typing settings**</span></span> 
    2. <span data-ttu-id="dd708-131">啟用 [拼寫檢查]、[輸入] 和 [觸控式鍵盤] 底下的所有選項。</span><span class="sxs-lookup"><span data-stu-id="dd708-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="dd708-132">下列範例顯示軌跡板，這對流覽和選取選項很有用。</span><span class="sxs-lookup"><span data-stu-id="dd708-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="dd708-133">使用螢幕小鍵盤來搜尋 Microsoft Store：</span><span class="sxs-lookup"><span data-stu-id="dd708-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![使用軌跡板](images/store.png)

## <span data-ttu-id="dd708-135">設定藍牙鍵盤和滑鼠 (選用) </span><span class="sxs-lookup"><span data-stu-id="dd708-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="dd708-136">如果您使用的是裝置作為主要 Windows 裝置，或者您經常使用它來輸入或精確作業，請連接鍵盤和滑鼠。</span><span class="sxs-lookup"><span data-stu-id="dd708-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="dd708-137">如果您的 Surface Hub 裝置靠近電腦，您可以使用 [沒有框線的滑鼠](https://aka.ms/mm) 在 surface HUB 和電腦之間順暢移動。</span><span class="sxs-lookup"><span data-stu-id="dd708-137">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="dd708-138">如需詳細資訊，請參閱 [從車庫取得 Microsoft 下載：不含框線的滑鼠](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/)。</span><span class="sxs-lookup"><span data-stu-id="dd708-138">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="dd708-139">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="dd708-139">OneDrive for Business</span></span>

<span data-ttu-id="dd708-140">使用 [商務用 OneDrive](https://docs.microsoft.com/onedrive/onedrive) 在您所有的工作裝置之間輕鬆共用工具、記錄及其他檔案。</span><span class="sxs-lookup"><span data-stu-id="dd708-140">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="dd708-141">OneDrive 可讓您在膝上型電腦、Surface Hub 桌面與 Intune 管理的行動裝置之間共用您的工作檔案。</span><span class="sxs-lookup"><span data-stu-id="dd708-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="dd708-142">您可以在任何裝置上編輯檔案，而且所有網路連接的裝置都會隨變更進行更新。</span><span class="sxs-lookup"><span data-stu-id="dd708-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="dd708-143">考慮 Surface Hub SSD 的大小 (128GB) ，如果您在 Surface Hub 桌面裝置上設定 OneDrive，請確定預設設定是在您使用它們時，讓檔案保持線上並下載檔案。</span><span class="sxs-lookup"><span data-stu-id="dd708-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="dd708-144">若要將 OneDrive 設定為只在需要時下載檔案，請設定 [檔案 **隨選** ] 設定，以 **在您使用時儲存空間和下載**檔案。</span><span class="sxs-lookup"><span data-stu-id="dd708-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="dd708-145">如需詳細資訊，請參閱 [在 Windows 中查詢及設定檔案的隨選狀態](https://docs.microsoft.com/onedrive/files-on-demand-windows)。</span><span class="sxs-lookup"><span data-stu-id="dd708-145">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![OneDrive 設定](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="dd708-147">您也可以重複這些步驟來設定個人 OneDrive，但請務必保留磁片磁碟機空間，並在需要時下載檔案。</span><span class="sxs-lookup"><span data-stu-id="dd708-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="dd708-148">SharePoint 與團隊</span><span class="sxs-lookup"><span data-stu-id="dd708-148">SharePoint and Teams</span></span>

<span data-ttu-id="dd708-149">SharePoint 和團隊通道檔案也可以使用 OneDrive 同步處理引擎，在本機同步處理到您的桌面裝置，例如膝上型電腦和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="dd708-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="dd708-150">若要將內部公司檔案與 OneDrive 同步處理應用程式同步處理至您的本機磁片磁碟機：</span><span class="sxs-lookup"><span data-stu-id="dd708-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="dd708-151">移至 SharePoint 網站，然後流覽至最上層檔目錄，尋找您想要從本機裝置查看或編輯的檔案。</span><span class="sxs-lookup"><span data-stu-id="dd708-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>
2. <span data-ttu-id="dd708-152">在 SharePoint 功能區頂端的 [ **同步** 處理] 按鈕上選取。</span><span class="sxs-lookup"><span data-stu-id="dd708-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>
3. <span data-ttu-id="dd708-153">在快顯功能表上選取 [**開啟\*\*\*\*此網站]，以嘗試開啟 Microsoft OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="dd708-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>
4. <span data-ttu-id="dd708-154">選取工作列右下角的 [OneDrive] 圖示，以確認 SharePoint 檔案正在同步處理到您的本機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="dd708-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>
5. <span data-ttu-id="dd708-155">確認設定設定為讓檔案保持線上，且只在您使用檔案時才下載檔案：</span><span class="sxs-lookup"><span data-stu-id="dd708-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>
    1. <span data-ttu-id="dd708-156">開啟 [檔案資源管理器]。</span><span class="sxs-lookup"><span data-stu-id="dd708-156">Open file explorer.</span></span>
    2. <span data-ttu-id="dd708-157">在\*\*Microsoft \ \<SharePoint Document Folder Name\> \*\*上流覽並以滑鼠右鍵選取。</span><span class="sxs-lookup"><span data-stu-id="dd708-157">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="dd708-158">選取 [ **釋放空間**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-158">Select **Free up space**.</span></span>
    4. <span data-ttu-id="dd708-159">[狀態] 欄會顯示 [檔案] 和 [資料夾] 的狀態。</span><span class="sxs-lookup"><span data-stu-id="dd708-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="dd708-160">如需詳細資訊，請參閱 [使用 OneDrive 同步處理用戶端同步處理 SharePoint](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd)檔案。</span><span class="sxs-lookup"><span data-stu-id="dd708-160">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
6. <span data-ttu-id="dd708-161">團隊通道檔案是儲存在 SharePoint 網站中，所有的 SharePoint 檔功能都相同，包括版本歷程記錄，以及同步處理到您的本機桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="dd708-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="dd708-162">若要同步處理團隊通道檔：</span><span class="sxs-lookup"><span data-stu-id="dd708-162">To sync Teams Channel files:</span></span>
    1. <span data-ttu-id="dd708-163">流覽至 [感興趣的 **小組] 頻道** ，然後選取頂端的 [檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dd708-163">Navigate to the Teams Channel of interest and select on the **Files** tab at the top.</span></span> <span data-ttu-id="dd708-164">然後選取 [**同步**處理]。檔案將會開始進行同步處理，並會顯示在桌上型電腦的 [檔案資源管理器] \*\*\ [Microsoft \ \<name of the Teams Channel\> \*\*]。</span><span class="sxs-lookup"><span data-stu-id="dd708-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="dd708-165">使用您用來同步處理 SharePoint 網站的相同程式，將檔案保留在雲端，並只在使用時進行下載，只要在 [團隊頻道名稱] 上按一下並按住或以滑鼠右鍵按一下，然後選取 [ **釋放空間**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="dd708-166">配對 Surface Hub 筆</span><span class="sxs-lookup"><span data-stu-id="dd708-166">Pair the Surface Hub pen</span></span>

<span data-ttu-id="dd708-167">若要配對手寫筆裝置：</span><span class="sxs-lookup"><span data-stu-id="dd708-167">To pair the pen device:</span></span>

1. <span data-ttu-id="dd708-168">選取 [**啟動**  >  **設定**  >  **裝置**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-168">Select **Start** > **Settings** > **Devices**.</span></span>
2. <span data-ttu-id="dd708-169">選取 [ **新增藍牙] 或 [其他裝置**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-169">Select **Add Bluetooth or other device**.</span></span>
3. <span data-ttu-id="dd708-170">選擇 [ **藍牙**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-170">Choose **Bluetooth**.</span></span>
4. <span data-ttu-id="dd708-171">移除畫筆尾部按鈕，然後搖動以斷開電池連線。</span><span class="sxs-lookup"><span data-stu-id="dd708-171">Remove the pen tail button and shake to disconnect the battery connection.</span></span>
5. <span data-ttu-id="dd708-172">再次將 cap 放回，然後按住 cap，直到配對指示燈閃爍為止。</span><span class="sxs-lookup"><span data-stu-id="dd708-172">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>
6. <span data-ttu-id="dd708-173">在 Surface Hub 藍牙設定中，選擇 [ **Surface hub 2 筆**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-173">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>
7. <span data-ttu-id="dd708-174">完成配對操作。</span><span class="sxs-lookup"><span data-stu-id="dd708-174">Complete the pairing operation.</span></span> 
8. <span data-ttu-id="dd708-175">如果配對失敗，請嘗試再次配對筆。</span><span class="sxs-lookup"><span data-stu-id="dd708-175">If the pairing is not successful, attempt to pair the pen again.</span></span> <span data-ttu-id="dd708-176">如有需要，請重新開機裝置，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="dd708-176">If necessary, reboot the device and then try again.</span></span>

## <span data-ttu-id="dd708-177">相機配置</span><span class="sxs-lookup"><span data-stu-id="dd708-177">Camera configuration</span></span>

<span data-ttu-id="dd708-178">您可以將相機安裝在裝置的頂端或任一側。</span><span class="sxs-lookup"><span data-stu-id="dd708-178">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="dd708-179">如果您是將中樞與桌面支架（而非車）配合使用，或者與中樞接近，請將相機安裝在位置，以優化相機角度。</span><span class="sxs-lookup"><span data-stu-id="dd708-179">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="dd708-180">相機不會自動旋轉，因此您必須使用2mm 十六進位金鑰來手動旋轉相機。</span><span class="sxs-lookup"><span data-stu-id="dd708-180">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="dd708-181">如需如何將相機側邊裝載並手動旋轉相機的詳細資訊，請參閱 [Surface Hub 2 的相機鏡頭方向](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation)。</span><span class="sxs-lookup"><span data-stu-id="dd708-181">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="dd708-182">Windows Hello 設定</span><span class="sxs-lookup"><span data-stu-id="dd708-182">Windows Hello configuration</span></span>

<span data-ttu-id="dd708-183">執行 Windows 10 企業版的 Surface Hub 2-2 可提供完整的 Win32 桌面應用程式，以及生物識別 Windows Hello 選項。</span><span class="sxs-lookup"><span data-stu-id="dd708-183">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="dd708-184">Surface Hub 2 指紋辨識器配件可以插入裝置上的任何 USB 埠。</span><span class="sxs-lookup"><span data-stu-id="dd708-184">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

> <i><span data-ttu-id="dd708-185">Surface Hub 2 指紋辨識器將可在稍後購買。</span><span class="sxs-lookup"><span data-stu-id="dd708-185">The Surface Hub 2 Fingerprint Reader will be available for purchase soon.</span></span> <span data-ttu-id="dd708-186">如需詳細資訊，請參閱此頁面，包括如何購買。</span><span class="sxs-lookup"><span data-stu-id="dd708-186">Please check back on this page for more information including how to purchase.</span></span></i>

<span data-ttu-id="dd708-187">插入指紋閱讀程式後，請選取 [**啟動**  >  **設定**  >  **帳戶**] 登  >  **入選項**  >  **Windows Hello 指紋**以註冊您的指紋。</span><span class="sxs-lookup"><span data-stu-id="dd708-187">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="dd708-188">使用 Windows Hello 認證裝置進行面孔認可。</span><span class="sxs-lookup"><span data-stu-id="dd708-188">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="dd708-189">Surface Hub 2 版攝像頭不支援 Windows Hello 面孔認可。</span><span class="sxs-lookup"><span data-stu-id="dd708-189">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="dd708-190">在工作列上啟用鎖定畫面快捷方式圖示</span><span class="sxs-lookup"><span data-stu-id="dd708-190">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="dd708-191">若要將圖示新增到工作列，以啟用單一觸控螢幕鎖定，類似 Windows-L 鍵盤快速鍵：</span><span class="sxs-lookup"><span data-stu-id="dd708-191">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="dd708-192">在桌面上按一下並按住或按一下滑鼠右鍵，然後選取 [**新增**  >  **快速鍵**  >  **流覽**  >  **桌面**] [  >  **OK**  >  **下一步**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-192">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="dd708-193">提供快捷方式的名稱，例如 **鎖定我的電腦**，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="dd708-193">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="dd708-194">以滑鼠右鍵按一下或輕觸並按住桌面上新建立的快捷方式，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-194">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="dd708-195">在 [ **快捷方式** ] 索引標籤上的 [ **目標** ] 欄位中，輸入下列內容： **Rundll32.exe User32.dll、LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="dd708-195">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="dd708-196">選取 [ **變更] 圖示** 按鈕，然後流覽至 [ **C:\Windows\System32\imageres.dll** ]，然後選取要使用的圖示。</span><span class="sxs-lookup"><span data-stu-id="dd708-196">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="dd708-197">請參閱下列範例：</span><span class="sxs-lookup"><span data-stu-id="dd708-197">See the following example:</span></span>

    ![選擇圖示](images/lock.png)
    
1.  <span data-ttu-id="dd708-199">選取 **[確定]** 儲存快捷方式。</span><span class="sxs-lookup"><span data-stu-id="dd708-199">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="dd708-200">以滑鼠右鍵按一下或輕觸並按住快速鍵，然後選取 [ **釘選到工作列**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-200">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

## <span data-ttu-id="dd708-201">應用程式</span><span class="sxs-lookup"><span data-stu-id="dd708-201">Applications</span></span>

### <span data-ttu-id="dd708-202">更新已安裝的應用程式</span><span class="sxs-lookup"><span data-stu-id="dd708-202">Update installed apps</span></span>

<span data-ttu-id="dd708-203">若要更新所有已安裝的 Microsoft Store 應用程式：</span><span class="sxs-lookup"><span data-stu-id="dd708-203">To update all installed Store apps:</span></span>

1. <span data-ttu-id="dd708-204">開啟 Microsoft Store 應用程式，然後選取右上角的 [ **查看更多** 省略號]。</span><span class="sxs-lookup"><span data-stu-id="dd708-204">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="dd708-205">選取 **[下載和更新]**。</span><span class="sxs-lookup"><span data-stu-id="dd708-205">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="dd708-206">選取 **[取得更新]**。</span><span class="sxs-lookup"><span data-stu-id="dd708-206">Select **Get updates**.</span></span>

### <span data-ttu-id="dd708-207">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="dd708-207">Microsoft Whiteboard</span></span>

<span data-ttu-id="dd708-208">若要安裝 Microsoft 白板：</span><span class="sxs-lookup"><span data-stu-id="dd708-208">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="dd708-209">選取工作列右下角的 [ **Windows Ink 工作區** ] 圖示，然後下載 [ **白板**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-209">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![筆跡工作區](images/ink.png) 

<span data-ttu-id="dd708-211">或者，您可以從 Microsoft 網上商店安裝白板：</span><span class="sxs-lookup"><span data-stu-id="dd708-211">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="dd708-212">開啟 Microsoft Store app 並搜尋 **白板**。</span><span class="sxs-lookup"><span data-stu-id="dd708-212">Open Microsoft Store app and search for **Whiteboard**.</span></span>
2. <span data-ttu-id="dd708-213">選擇 [ **不用] 感謝您** 在裝置上登入及使用。</span><span class="sxs-lookup"><span data-stu-id="dd708-213">Choose **No thanks** to sign in and use across devices.</span></span>
3. <span data-ttu-id="dd708-214">將白板釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="dd708-214">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="dd708-215">Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="dd708-215">Surface app</span></span>

1. <span data-ttu-id="dd708-216">在 Microsoft Store 中，搜尋 **Surface**。</span><span class="sxs-lookup"><span data-stu-id="dd708-216">In the Microsoft Store, search for **Surface**.</span></span>
2. <span data-ttu-id="dd708-217">將 [ **在篩選上可用** ] 設定為 [ **所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-217">Set the **Available on** filter to **All devices**.</span></span>
3. <span data-ttu-id="dd708-218">安裝 **Surface** app。</span><span class="sxs-lookup"><span data-stu-id="dd708-218">Install the **Surface** app.</span></span> <span data-ttu-id="dd708-219">這應該是第一個列出的 app。</span><span class="sxs-lookup"><span data-stu-id="dd708-219">This should be the first app listed.</span></span> <span data-ttu-id="dd708-220">您可能需要將您的 MSA 與書店建立關聯，才能安裝 app。</span><span class="sxs-lookup"><span data-stu-id="dd708-220">You might need to associate your MSA to the Store in order to install the app.</span></span>
4. <span data-ttu-id="dd708-221">將 **表面** app 釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="dd708-221">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="dd708-222">剪取 & 素描</span><span class="sxs-lookup"><span data-stu-id="dd708-222">Snip & Sketch</span></span>

1. <span data-ttu-id="dd708-223">開啟 [ **剪取 & 草圖** ] app，然後將它釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="dd708-223">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>
2. <span data-ttu-id="dd708-224">選取右上角的省略號，然後選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-224">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>
3. <span data-ttu-id="dd708-225">在 [ **設定**] 中，開啟 [ **自動複製到剪貼**簿]、[ **儲存截圖**]，以及 **多個 windows** (選擇性) 。</span><span class="sxs-lookup"><span data-stu-id="dd708-225">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="dd708-226">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="dd708-226">Microsoft Office</span></span>

1. <span data-ttu-id="dd708-227">開啟 [Office 入口網站](https://portal.office.com/account#installs) ，並安裝您想要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd708-227">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>
2. <span data-ttu-id="dd708-228">將所需的 Office 應用程式釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="dd708-228">Pin desired Office applications to the taskbar.</span></span>
3. <span data-ttu-id="dd708-229">如果已安裝 Outlook，請務必將 Outlook OST 設定為只儲存最後兩周的快取。</span><span class="sxs-lookup"><span data-stu-id="dd708-229">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="dd708-230">這將大大減少磁片使用量和設定時間。</span><span class="sxs-lookup"><span data-stu-id="dd708-230">This will vastly reduce disk usage and setup time.</span></span>
    - <span data-ttu-id="dd708-231">選取 **[** 檔案  >  **帳戶設定**]，然後選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="dd708-231">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="dd708-232">選取 [ **變更** ]，然後將 [使用快取 **Exchange 模式]** 的滑杆設定為14天。</span><span class="sxs-lookup"><span data-stu-id="dd708-232">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="dd708-233">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dd708-233">Microsoft Teams</span></span>

1. <span data-ttu-id="dd708-234">下載並安裝 [Microsoft 團隊](https://teams.microsoft.com/downloads)。</span><span class="sxs-lookup"><span data-stu-id="dd708-234">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>
2. <span data-ttu-id="dd708-235">將設定設定為自動啟動應用程式 (選用的) 。</span><span class="sxs-lookup"><span data-stu-id="dd708-235">Configure settings to Auto-start application (optional).</span></span>
3. <span data-ttu-id="dd708-236">將團隊釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="dd708-236">Pin Teams to the taskbar.</span></span>
4. <span data-ttu-id="dd708-237">請考慮減少裝置上的小組通知，避免干擾 (選用的) 。</span><span class="sxs-lookup"><span data-stu-id="dd708-237">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

  ![團隊通知](images/teams.png)

### <span data-ttu-id="dd708-239">Connect app</span><span class="sxs-lookup"><span data-stu-id="dd708-239">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd708-240">在 Windows 10 版本2004及更新版本中，預設不會安裝使用 Miracast 進行無線投影的連線應用程式，但可將它做為選用的功能。</span><span class="sxs-lookup"><span data-stu-id="dd708-240">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="dd708-241">若要安裝應用程式，請選取 [**設定**  >  **應用程式**] [  >  **選用功能**]，  >  **新增一個功能**，然後安裝 [**無線顯示**] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd708-241">To install the app, select on **Settings** > **Apps** > **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

1. <span data-ttu-id="dd708-242">搜尋 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="dd708-242">Search for **Connect**.</span></span>
2. <span data-ttu-id="dd708-243">開啟 app，然後將它關閉 (**Project 至此電腦** 可能無法正常運作，除非 app 已至少執行過一次) 。</span><span class="sxs-lookup"><span data-stu-id="dd708-243">Open the app and then close it (**Project to this PC** might not work unless the app has been run at least once).</span></span>
3. <span data-ttu-id="dd708-244">按住或以滑鼠右鍵按一下以釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="dd708-244">Tap and hold or right-click to pin to taskbar.</span></span>
4. <span data-ttu-id="dd708-245">搜尋 **投影設定**。</span><span class="sxs-lookup"><span data-stu-id="dd708-245">Search for **Projection settings**.</span></span>
5. <span data-ttu-id="dd708-246">在 **某些 Windows 和 Android 裝置下，當您說出 [確定] 時，可以在這台電腦上進行投影**，如果裝置不在商業網路上，請選擇 [ **所有位置都可用** ]。</span><span class="sxs-lookup"><span data-stu-id="dd708-246">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose **Available everywhere** if the device is not on a corporate network.</span></span> <span data-ttu-id="dd708-247">否則，您可以選擇 [ **所有位置都能在安全網路上使用**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-247">Otherwise, you can choose **Available everywhere on secure networks**.</span></span>
6. <span data-ttu-id="dd708-248">在 [ **要求 project to 此電腦**] 底下，選擇 [ **僅限第一次**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-248">Under **Ask to project to this PC**, choose **First time only**.</span></span>
7. <span data-ttu-id="dd708-249">在 [ **需要 PIN 以進行配對**] 下，選擇 [ **永不**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-249">Under **Require PIN for pairing**, choose **Never**.</span></span>

<span data-ttu-id="dd708-250">在公司網路不使用時的建議配置：</span><span class="sxs-lookup"><span data-stu-id="dd708-250">Recommended configuration when not on the corporate network:</span></span>

  ![在家中的設定](images/project1.png)

<span data-ttu-id="dd708-252">公司網路上的建議配置：</span><span class="sxs-lookup"><span data-stu-id="dd708-252">Recommended configuration on the corporate network:</span></span>

  ![工作中的設定](images/project2.png)

### <span data-ttu-id="dd708-254">您的手機</span><span class="sxs-lookup"><span data-stu-id="dd708-254">Your Phone</span></span>

<span data-ttu-id="dd708-255">**您的電話**app 預設會安裝在 Windows 10 上。</span><span class="sxs-lookup"><span data-stu-id="dd708-255">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="dd708-256">如果不存在，您也可以從 Windows 市集中安裝它。</span><span class="sxs-lookup"><span data-stu-id="dd708-256">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="dd708-257">如需設定 app 的相關資訊，請參閱 [如何在 Windows 10 設定您的電話，以及如何在您的電腦與手機之間同步處理資料](https://www.windowscentral.com/how-set-your-phone-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="dd708-257">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="dd708-258">另請參閱 [如何修正您在 Windows 10 上的手機應用程式常見問題](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="dd708-258">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="dd708-259">超級別致區域</span><span class="sxs-lookup"><span data-stu-id="dd708-259">Super Fancy Zones</span></span>

<span data-ttu-id="dd708-260">**Super 別致區域** 可協助使用者排列視窗，以最大化螢幕空間。</span><span class="sxs-lookup"><span data-stu-id="dd708-260">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="dd708-261">它現在包含在 GitHub 上的 [PowerToys](https://github.com/microsoft/PowerToys/releases) 中。</span><span class="sxs-lookup"><span data-stu-id="dd708-261">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="dd708-262">Edge Chromium 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="dd708-262">Edge Chromium browser</span></span>

<span data-ttu-id="dd708-263">下載並安裝新的 [Edge Chromium 瀏覽器](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL)。</span><span class="sxs-lookup"><span data-stu-id="dd708-263">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="dd708-264">其他設定</span><span class="sxs-lookup"><span data-stu-id="dd708-264">Additional settings</span></span>

### <span data-ttu-id="dd708-265">選取以啟動白板的 [畫筆尾部]</span><span class="sxs-lookup"><span data-stu-id="dd708-265">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="dd708-266">搜尋 **手寫筆** ，然後選取 [ **畫筆] & Windows Ink 設定**。</span><span class="sxs-lookup"><span data-stu-id="dd708-266">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>
2. <span data-ttu-id="dd708-267">在靠近頁面底部的 [ **畫筆快速鍵** ] 底下，將 [ **選取一次** 至 **Microsoft 白板**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-267">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="dd708-268">[電源] 和 [睡眠] 設定</span><span class="sxs-lookup"><span data-stu-id="dd708-268">Power and sleep settings</span></span>

1. <span data-ttu-id="dd708-269">選取 [**開始**  >  **設定**] [  >  **系統**  >  **電源 & 睡眠**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-269">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>
2. <span data-ttu-id="dd708-270">設定 [電源模式] 滑杆以 **獲得最佳效能**。</span><span class="sxs-lookup"><span data-stu-id="dd708-270">Set the power mode slider to **Best performance**.</span></span>
3. <span data-ttu-id="dd708-271">將畫面和睡眠值設定為您的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="dd708-271">Configure screen and sleep values to your preference.</span></span>

### <span data-ttu-id="dd708-272">螢幕保護裝置程式</span><span class="sxs-lookup"><span data-stu-id="dd708-272">Screen saver</span></span>

1. <span data-ttu-id="dd708-273">搜尋 **鎖定畫面** 並開啟 **鎖定畫面設定**。</span><span class="sxs-lookup"><span data-stu-id="dd708-273">Search for **Lock Screen** and open **Lock screen settings**.</span></span>
2. <span data-ttu-id="dd708-274">將 **螢幕超時設定** 和 **螢幕保護裝置程式設定** 設定為您的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="dd708-274">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span>

### <span data-ttu-id="dd708-275">儲存空間感知器</span><span class="sxs-lookup"><span data-stu-id="dd708-275">Storage Sense</span></span>

<span data-ttu-id="dd708-276">Surface Hub 2 在本機儲存空間中有一個 128GB SSD，所以在正常使用期間，必須考慮使用儲存空間儲存量值。</span><span class="sxs-lookup"><span data-stu-id="dd708-276">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="dd708-277">若要設定儲存空間的意義：</span><span class="sxs-lookup"><span data-stu-id="dd708-277">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="dd708-278">搜尋 [**系統設定**] 底下的 [**儲存設定**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-278">Search for **storage settings**, which is found under **System settings**.</span></span>
2.  <span data-ttu-id="dd708-279">在 [ **設定**] 底下，選取 [ **開啟儲存空間感知** ]，開啟 [ **儲存空間** 設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="dd708-279">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>
3.  <span data-ttu-id="dd708-280">開啟 [儲存空間感知 **]。**</span><span class="sxs-lookup"><span data-stu-id="dd708-280">Turn Storage Sense to **On**.</span></span>
4.  <span data-ttu-id="dd708-281">選取 [ **設定儲存空間感知] 或 [立即執行** ]，然後設定設定，盡可能讓檔案保持在線上， (因為磁碟空間) 有限。</span><span class="sxs-lookup"><span data-stu-id="dd708-281">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="dd708-282">建議的設定：</span><span class="sxs-lookup"><span data-stu-id="dd708-282">Recommended settings:</span></span>
- <span data-ttu-id="dd708-283">每日執行儲存感知 =。</span><span class="sxs-lookup"><span data-stu-id="dd708-283">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="dd708-284">刪除我的 app 無法使用的臨時檔案 = 每隔14天 (至少) 。</span><span class="sxs-lookup"><span data-stu-id="dd708-284">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="dd708-285">如果在 [我的下載] 資料夾中有超過30天的檔案，請將它們刪除。</span><span class="sxs-lookup"><span data-stu-id="dd708-285">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="dd708-286">OneDrive：如果未開啟超過 = 30 天的時間，內容就會變成 [線上]。</span><span class="sxs-lookup"><span data-stu-id="dd708-286">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="dd708-287">平板電腦模式</span><span class="sxs-lookup"><span data-stu-id="dd708-287">Tablet mode</span></span>

<span data-ttu-id="dd708-288">如有需要，請開啟平板電腦模式以取得協助工具需求。</span><span class="sxs-lookup"><span data-stu-id="dd708-288">Turn on Tablet mode if desired for accessibility needs.</span></span>

### <span data-ttu-id="dd708-289">電源管理</span><span class="sxs-lookup"><span data-stu-id="dd708-289">Power management</span></span>

> [!NOTE]
> <span data-ttu-id="dd708-290">在執行下列程式前，請向您的 IT 部門確認，以核准從全域電源管理原則中排除 Surface Hub 2-2 裝置。</span><span class="sxs-lookup"><span data-stu-id="dd708-290">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="dd708-291">某些電源管理設定可以停用目前狀態偵測函數。</span><span class="sxs-lookup"><span data-stu-id="dd708-291">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="dd708-292">搜尋 **軟體中心** 並將它開啟。</span><span class="sxs-lookup"><span data-stu-id="dd708-292">Search for **Software Center** and open it.</span></span>
2. <span data-ttu-id="dd708-293">選取 [功能窗格] 中的 **選項** 。</span><span class="sxs-lookup"><span data-stu-id="dd708-293">Select **Options** in the navigation pane.</span></span>
3. <span data-ttu-id="dd708-294">展開 [ **電源管理** ] 區段，然後選取 [ **不要將 IT 部門的電源設定套用至此電腦**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-294">Expand the **Power management** section and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![軟體設定](images/soft-cntr.png)

### <span data-ttu-id="dd708-296">音效設定</span><span class="sxs-lookup"><span data-stu-id="dd708-296">Sound settings</span></span>

1. <span data-ttu-id="dd708-297">搜尋 [ **聲音設定** ]，然後開啟此頁面。</span><span class="sxs-lookup"><span data-stu-id="dd708-297">Search for **Sounds settings** and open this page.</span></span>
2. <span data-ttu-id="dd708-298">選取右側的 [ **音效** 控制台]，然後選取 [ **聲音** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="dd708-298">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>
3. <span data-ttu-id="dd708-299">在 [**程式事件**]**下，將** **[裝置**連線] 與 **[裝置中斷連線]**</span><span class="sxs-lookup"><span data-stu-id="dd708-299">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="dd708-300">靜音通知</span><span class="sxs-lookup"><span data-stu-id="dd708-300">Silence notifications</span></span>

1. <span data-ttu-id="dd708-301">搜尋 **焦點協助** ，然後開啟此頁面。</span><span class="sxs-lookup"><span data-stu-id="dd708-301">Search for **Focus assist** and open this page.</span></span>
2. <span data-ttu-id="dd708-302">選取 [ **僅限鬧鐘**]。</span><span class="sxs-lookup"><span data-stu-id="dd708-302">Select **Alarms Only**.</span></span> <span data-ttu-id="dd708-303">這將避免持續通知飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="dd708-303">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="dd708-304">磁碟清理</span><span class="sxs-lookup"><span data-stu-id="dd708-304">Disk Cleanup</span></span>

1. <span data-ttu-id="dd708-305">搜尋 [ **磁片清理** ] 並開啟此應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd708-305">Search for **Disk Cleanup** and open this app.</span></span>
2. <span data-ttu-id="dd708-306">在 [ **要刪除**的檔案] 底下，選取您要刪除的檔案。</span><span class="sxs-lookup"><span data-stu-id="dd708-306">Under **Files to delete**, select the files you wish to delete.</span></span> 
3. <span data-ttu-id="dd708-307">同時選取 [ **清理系統**檔案]。</span><span class="sxs-lookup"><span data-stu-id="dd708-307">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="dd708-308">完成並驗證</span><span class="sxs-lookup"><span data-stu-id="dd708-308">Complete and verify</span></span>

1. <span data-ttu-id="dd708-309">掃描並安裝所有的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="dd708-309">Scan for and install all Windows Updates.</span></span>
2. <span data-ttu-id="dd708-310">更新群組原則</span><span class="sxs-lookup"><span data-stu-id="dd708-310">Update Group Policy</span></span>
    1. <span data-ttu-id="dd708-311">在提升許可權的命令提示字元中，輸入 **gpupdate/force/boot/wait： 0**。</span><span class="sxs-lookup"><span data-stu-id="dd708-311">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
3. <span data-ttu-id="dd708-312">將裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="dd708-312">Reboot the device.</span></span>
4. <span data-ttu-id="dd708-313">驗證工作列 app。</span><span class="sxs-lookup"><span data-stu-id="dd708-313">Verify taskbar apps.</span></span>
    - <span data-ttu-id="dd708-314">Connect App</span><span class="sxs-lookup"><span data-stu-id="dd708-314">Connect App</span></span>
    - <span data-ttu-id="dd708-315">[鎖定] 圖示</span><span class="sxs-lookup"><span data-stu-id="dd708-315">Lock Icon</span></span>
    - <span data-ttu-id="dd708-316">剪取 & 素描</span><span class="sxs-lookup"><span data-stu-id="dd708-316">Snip & Sketch</span></span>
    - <span data-ttu-id="dd708-317">小組 (（如果適用）) </span><span class="sxs-lookup"><span data-stu-id="dd708-317">Teams (if applicable)</span></span>
    - <span data-ttu-id="dd708-318">Office 應用程式 (（如果適用）) </span><span class="sxs-lookup"><span data-stu-id="dd708-318">Office Apps (if applicable)</span></span>
    - <span data-ttu-id="dd708-319">Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="dd708-319">Surface App</span></span>
    - <span data-ttu-id="dd708-320">白板</span><span class="sxs-lookup"><span data-stu-id="dd708-320">Whiteboard</span></span>
5. <span data-ttu-id="dd708-321">確認目前狀態偵測。</span><span class="sxs-lookup"><span data-stu-id="dd708-321">Verify presence detection.</span></span>
    - <span data-ttu-id="dd708-322">目前系統託盤中的目前狀態偵測將是綠色圖示</span><span class="sxs-lookup"><span data-stu-id="dd708-322">Presence detection will be a green icon in the system tray</span></span>
6. <span data-ttu-id="dd708-323">[確認投影到此電腦] 已啟用 [連線] App (應用程式在連接) 之前不需要執行。</span><span class="sxs-lookup"><span data-stu-id="dd708-323">Verify projecting to this PC is enabled with the Connect App (the application does not need to be running before connecting).</span></span>
7. <span data-ttu-id="dd708-324">驗證電源和睡眠設定。</span><span class="sxs-lookup"><span data-stu-id="dd708-324">Verify power and sleep settings.</span></span>
    - <span data-ttu-id="dd708-325">螢幕保護裝置程式：15分鐘，設定為 (無]) 、Mystify 或空白;已選取 [需要密碼的核取方塊]</span><span class="sxs-lookup"><span data-stu-id="dd708-325">Screen Saver: 15 minutes, set to (none), Mystify or Blank; check box for requiring password is checked</span></span>
    - <span data-ttu-id="dd708-326">螢幕：2小時</span><span class="sxs-lookup"><span data-stu-id="dd708-326">Screen: 2 hours</span></span>
    - <span data-ttu-id="dd708-327">電腦：4小時</span><span class="sxs-lookup"><span data-stu-id="dd708-327">PC: 4 hours</span></span>
8. <span data-ttu-id="dd708-328">驗證 Windows Hello 是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="dd708-328">Verify Windows Hello is working.</span></span>
9. <span data-ttu-id="dd708-329">驗證電源設定。</span><span class="sxs-lookup"><span data-stu-id="dd708-329">Verify power settings.</span></span>
10. <span data-ttu-id="dd708-330">驗證同步處理您的設定已停用。</span><span class="sxs-lookup"><span data-stu-id="dd708-330">Verify sync your settings is disabled.</span></span>
11. <span data-ttu-id="dd708-331">確認啟動 app。</span><span class="sxs-lookup"><span data-stu-id="dd708-331">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="dd708-332">安裝並設定 Windows 10 之後，Surface Hub 的配置可以像管理任何其他的 Windows 10 裝置一樣進行管理。</span><span class="sxs-lookup"><span data-stu-id="dd708-332">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="dd708-333">相關主題</span><span class="sxs-lookup"><span data-stu-id="dd708-333">Related topics</span></span>

[<span data-ttu-id="dd708-334">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="dd708-334">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)
