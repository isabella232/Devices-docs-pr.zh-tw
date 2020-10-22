---
title: 設定 Windows 10 專業版或 Surface Hub 2 企業版
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
ms.author: greglin
ms.collection: M365-modern-desktop
ms.topic: article
ms.date: 10/21/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 25705f889f70e3d12dfef690c34e03d98254725e
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133178"
---
# <span data-ttu-id="e3bc5-104">設定 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="e3bc5-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="e3bc5-105">完成遷移至 Windows 10 專業版或企業版的安裝程式後，您可以執行下列步驟來設定 Surface Hub 2 上的 app 和設定。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="e3bc5-106">建議使用這些步驟，以確保使用此個人化大型螢幕觸控和手寫筆電腦時的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="e3bc5-107">執行這些步驟時，您可能會發現使用有線或無線鍵盤和滑鼠很有用。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="e3bc5-108">設定系統設定</span><span class="sxs-lookup"><span data-stu-id="e3bc5-108">Configure system settings</span></span>

1. <span data-ttu-id="e3bc5-109">使用具有裝置上的本機系統管理員許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="e3bc5-110">在 Azure AD 已加入的裝置上，執行 Azure AD 連接的使用者會自動新增到本機管理員群組中。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="e3bc5-111">Azure AD 全域系統管理員和 Azure AD 裝置管理員 [也是本機管理員](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin)。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-111">Azure AD global administrators and Azure AD devices administrators are [also local administrators](https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin).</span></span> 
    
    - <span data-ttu-id="e3bc5-112">您可以在命令提示字元中輸入 **net localgroup 管理員** ，以列出具有本機系統管理員許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="e3bc5-113">使用易記的名稱重新命名裝置，例如： **username-SHub-Desktop**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="e3bc5-114">選取 [**啟動**  >  **設定**  >  **帳戶**] [  >  **同步處理您的設定**]，然後關閉同步處理**設定**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="e3bc5-115">這裡使用的設定是用來啟用最佳的螢幕觸控體驗，因此您可能不想同步處理其他裝置。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="e3bc5-116">將裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-116">Reboot the device.</span></span>

## <span data-ttu-id="e3bc5-117">啟用觸控式鍵盤與觸控板</span><span class="sxs-lookup"><span data-stu-id="e3bc5-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="e3bc5-118">按住或以滑鼠右鍵按一下工作列，然後選取 [ **顯示觸控式鍵盤] 按鈕** ，然後選取 [ **顯示觸控板] 按鈕**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="e3bc5-119">觸控式鍵盤對直接使用者輸入很有説明，而虛擬觸控板可協助您精確選擇、懸停工具提示，或代替按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    - <span data-ttu-id="e3bc5-120">請參閱以下範例。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-120">See the following example.</span></span>

      ![觸控設定](images/touch.png)

2. <span data-ttu-id="e3bc5-122">將觸控式鍵盤設定成標準和浮動。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="e3bc5-123">選取工作列上的 **鍵盤** 圖示以顯示觸控式鍵盤。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="e3bc5-124">在觸控式鍵盤上，選取左上角的 [鍵盤] 圖示以開啟 [鍵盤設定]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="e3bc5-125">選取上方列的 [最後一個鍵盤類型] 旁的 [啟用標準]，然後在第二個數據列的最後一個選項上啟用 [浮動]，這在這個大型螢幕上很有説明。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="e3bc5-126">請參閱以下範例。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-126">See the following examples.</span></span>

      ![鍵盤設定](images/kbd.png)
 
3. <span data-ttu-id="e3bc5-128">設定軟鍵盤設定。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-128">Configure the soft keyboard settings.</span></span>


    1. <span data-ttu-id="e3bc5-129">選取觸控式鍵盤上的 [ **設定** ] 圖示，或搜尋並開啟 **輸入設定**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![軟鍵盤設定](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="e3bc5-131">啟用 [拼寫檢查]、[輸入] 和 [觸控式鍵盤] 底下的所有選項。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="e3bc5-132">下列範例顯示軌跡板，這對流覽和選取選項很有用。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="e3bc5-133">使用螢幕小鍵盤來搜尋 Microsoft Store：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![使用軌跡板](images/store.png)

## <span data-ttu-id="e3bc5-135">設定藍牙鍵盤和滑鼠 (選用) </span><span class="sxs-lookup"><span data-stu-id="e3bc5-135">Configure bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="e3bc5-136">如果您使用的是裝置作為主要 Windows 裝置，或者您經常使用它來輸入或精確作業，請連接鍵盤和滑鼠。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="e3bc5-137">如果您的 Surface Hub 裝置靠近電腦，您可以使用 [沒有框線的滑鼠](https://aka.ms/mm) 在 surface HUB 和電腦之間順暢移動。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-137">If your Surface Hub device is near to a PC, you can use [Mouse without Borders](https://aka.ms/mm) to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="e3bc5-138">如需詳細資訊，請參閱 [從車庫取得 Microsoft 下載：不含框線的滑鼠](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/)。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-138">For more information, see [Microsoft download from The Garage: Mouse without Borders](https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/).</span></span>

## <span data-ttu-id="e3bc5-139">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="e3bc5-139">OneDrive for Business</span></span>

<span data-ttu-id="e3bc5-140">使用 [商務用 OneDrive](https://docs.microsoft.com/onedrive/onedrive) 在您所有的工作裝置之間輕鬆共用工具、記錄及其他檔案。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-140">Use [OneDrive for Business](https://docs.microsoft.com/onedrive/onedrive) to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="e3bc5-141">OneDrive 可讓您在膝上型電腦、Surface Hub 桌面與 Intune 管理的行動裝置之間共用您的工作檔案。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-141">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="e3bc5-142">您可以在任何裝置上編輯檔案，而且所有網路連接的裝置都會隨變更進行更新。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-142">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>
- <span data-ttu-id="e3bc5-143">考慮 Surface Hub SSD 的大小 (128GB) ，如果您在 Surface Hub 桌面裝置上設定 OneDrive，請確定預設設定是在您使用它們時，讓檔案保持線上並下載檔案。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-143">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="e3bc5-144">若要將 OneDrive 設定為只在需要時下載檔案，請設定 [檔案 **隨選** ] 設定，以 **在您使用時儲存空間和下載**檔案。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-144">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="e3bc5-145">如需詳細資訊，請參閱 [在 Windows 中查詢及設定檔案的隨選狀態](https://docs.microsoft.com/onedrive/files-on-demand-windows)。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-145">For more information, see [Query and set Files On-Demand states in Windows](https://docs.microsoft.com/onedrive/files-on-demand-windows).</span></span>

![OneDrive 設定](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="e3bc5-147">您也可以重複這些步驟來設定個人 OneDrive，但請務必保留磁片磁碟機空間，並在需要時下載檔案。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-147">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="e3bc5-148">SharePoint 與團隊</span><span class="sxs-lookup"><span data-stu-id="e3bc5-148">SharePoint and Teams</span></span>

<span data-ttu-id="e3bc5-149">SharePoint 和團隊通道檔案也可以使用 OneDrive 同步處理引擎，在本機同步處理到您的桌面裝置，例如膝上型電腦和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-149">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="e3bc5-150">若要將內部公司檔案與 OneDrive 同步處理應用程式同步處理至您的本機磁片磁碟機：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-150">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="e3bc5-151">移至 SharePoint 網站，然後流覽至最上層檔目錄，尋找您想要從本機裝置查看或編輯的檔案。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-151">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="e3bc5-152">在 SharePoint 功能區頂端的 [ **同步** 處理] 按鈕上選取。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-152">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="e3bc5-153">在快顯功能表上選取 [**開啟\*\*\*\*此網站]，以嘗試開啟 Microsoft OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-153">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="e3bc5-154">選取工作列右下角的 [OneDrive] 圖示，以確認 SharePoint 檔案正在同步處理到您的本機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-154">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="e3bc5-155">確認設定設定為讓檔案保持線上，且只在您使用檔案時才下載檔案：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-155">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="e3bc5-156">開啟 [檔案資源管理器]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-156">Open file explorer.</span></span>
    2. <span data-ttu-id="e3bc5-157">在\*\*Microsoft \ \<SharePoint Document Folder Name\> \*\*上流覽並以滑鼠右鍵選取。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-157">Navigate to and right select on the **Microsoft \ \<SharePoint Document Folder Name\>**.</span></span>
    3. <span data-ttu-id="e3bc5-158">選取 [ **釋放空間**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-158">Select **Free up space**.</span></span>
    4. <span data-ttu-id="e3bc5-159">[狀態] 欄會顯示 [檔案] 和 [資料夾] 的狀態。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-159">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="e3bc5-160">如需詳細資訊，請參閱 [使用 OneDrive 同步處理用戶端同步處理 SharePoint](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd)檔案。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-160">For more information, see [Sync SharePoint files with the OneDrive sync client](https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd).</span></span>
    
6. <span data-ttu-id="e3bc5-161">團隊通道檔案是儲存在 SharePoint 網站中，所有的 SharePoint 檔功能都相同，包括版本歷程記錄，以及同步處理到您的本機桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-161">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="e3bc5-162">若要同步處理團隊通道檔：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-162">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="e3bc5-163">流覽至 [感 **興趣的小組] 頻道** ，然後選取頂端的 [檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-163">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="e3bc5-164">然後選取 [**同步**處理]。檔案將會開始進行同步處理，並會顯示在桌上型電腦的 [檔案資源管理器] \*\*\ [Microsoft \ \<name of the Teams Channel\> \*\*]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-164">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Microsoft \ \<name of the Teams Channel\>**.</span></span>
    2. <span data-ttu-id="e3bc5-165">使用您用來同步處理 SharePoint 網站的相同程式，將檔案保留在雲端，並只在使用時進行下載，只要在 [團隊頻道名稱] 上按一下並按住或以滑鼠右鍵按一下，然後選取 [ **釋放空間**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-165">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="e3bc5-166">Surface Hub 手寫筆設定</span><span class="sxs-lookup"><span data-stu-id="e3bc5-166">Surface Hub pen settings</span></span>

**<span data-ttu-id="e3bc5-167">將藍牙 Surface 中樞觸筆配對</span><span class="sxs-lookup"><span data-stu-id="e3bc5-167">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="e3bc5-168">對筆進行配對，將畫筆固件保持在最新狀態，並在 [藍牙裝置設定] 頁面或 Surface 應用程式中取得電池計量資訊：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-168">Pair the pen to keep the pen firmware up to date and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="e3bc5-169">選取 [**啟動**  >  **設定**  >  **裝置**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-169">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="e3bc5-170">選取 [ **新增藍牙] 或 [其他裝置**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-170">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="e3bc5-171">選擇 [ **藍牙**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-171">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="e3bc5-172">移除畫筆尾部按鈕，然後搖動以斷開電池連線。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-172">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="e3bc5-173">再次將 cap 放回，然後按住 cap，直到配對指示燈閃爍為止。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-173">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="e3bc5-174">在 Surface Hub 藍牙設定中，選擇 [ **Surface hub 2 筆**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-174">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="e3bc5-175">完成配對操作。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-175">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="e3bc5-176">如果配對失敗，您可以嘗試再次配對筆。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-176">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="e3bc5-177">如果仍無法解決問題，您可以在白板應用程式中驗證手寫筆是否正常運作，以查看電池是否已充電。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-177">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="e3bc5-178">如果不是，請更換電池，然後再次嘗試配對筆。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-178">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="e3bc5-179">如有需要，請重新開機裝置，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-179">If necessary, reboot the device and then try again.</span></span>

<span data-ttu-id="e3bc5-180">**設定畫筆快速鍵** Surface Hub 筆有一個快速鍵按鈕，有時稱為「箭尾按一下」。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-180">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="e3bc5-181">[設定快速鍵] 會要求您先對筆進行配對，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-181">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="e3bc5-182">搜尋手寫筆，然後選取 [ **畫筆] & Windows Ink 設定**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-182">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="e3bc5-183">在靠近頁面底部的位置，選取會開啟此對話方塊的 [筆快速鍵]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-183">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

![畫筆快速鍵](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="e3bc5-185">相機配置</span><span class="sxs-lookup"><span data-stu-id="e3bc5-185">Camera configuration</span></span>

<span data-ttu-id="e3bc5-186">您可以將相機安裝在裝置的頂端或任一側。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-186">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="e3bc5-187">如果您是將中樞與桌面支架（而非車）配合使用，或者與中樞接近，請將相機安裝在位置，以優化相機角度。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-187">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="e3bc5-188">相機不會自動旋轉，因此您必須使用2mm 十六進位金鑰來手動旋轉相機。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-188">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="e3bc5-189">如需如何將相機側邊裝載並手動旋轉相機的詳細資訊，請參閱 [Surface Hub 2 的相機鏡頭方向](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation)。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-189">For more information on how to side-mount the camera and rotate the camera manually, see [Surface Hub 2S camera lens orientation](https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation).</span></span>

## <span data-ttu-id="e3bc5-190">Windows Hello 設定</span><span class="sxs-lookup"><span data-stu-id="e3bc5-190">Windows Hello configuration</span></span>

<span data-ttu-id="e3bc5-191">執行 Windows 10 企業版的 Surface Hub 2-2 可提供完整的 Win32 桌面應用程式，以及生物識別 Windows Hello 選項。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-191">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="e3bc5-192">Surface Hub 2 指紋辨識器配件可以插入裝置上的任何 USB 埠。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-192">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="e3bc5-193">若要定購 Surface Hub 2 指紋辨識器，或查看技術規格，請參閱 [適用于 Surface Hub 2 的 Windows 10 專業版和企業版的重要附加](surface-hub-2-essential-add-ons.md)元件。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-193">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see [Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2](surface-hub-2-essential-add-ons.md).</span></span> 

<span data-ttu-id="e3bc5-194">插入指紋閱讀程式後，請選取 [**啟動**  >  **設定**  >  **帳戶**] 登  >  **入選項**  >  **Windows Hello 指紋**以註冊您的指紋。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-194">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="e3bc5-195">使用 Windows Hello 認證裝置進行面孔認可。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-195">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="e3bc5-196">Surface Hub 2 版攝像頭不支援 Windows Hello 面孔認可。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-196">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="e3bc5-197">在工作列上啟用鎖定畫面快捷方式圖示</span><span class="sxs-lookup"><span data-stu-id="e3bc5-197">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="e3bc5-198">若要將圖示新增到工作列，以啟用單一觸控螢幕鎖定，類似 Windows-L 鍵盤快速鍵：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-198">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="e3bc5-199">在桌面上按一下並按住或按一下滑鼠右鍵，然後選取 [**新增**  >  **快速鍵**  >  **流覽**  >  **桌面**] [  >  **OK**  >  **下一步**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-199">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="e3bc5-200">提供快捷方式的名稱，例如 **鎖定我的電腦**，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-200">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="e3bc5-201">以滑鼠右鍵按一下或輕觸並按住桌面上新建立的快捷方式，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-201">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="e3bc5-202">在 [ **快捷方式** ] 索引標籤上的 [ **目標** ] 欄位中，輸入下列內容： **Rundll32.exe User32.dll、LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="e3bc5-202">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="e3bc5-203">選取 [ **變更] 圖示** 按鈕，然後流覽至 [ **C:\Windows\System32\imageres.dll** ]，然後選取要使用的圖示。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-203">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="e3bc5-204">請參閱下列範例：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-204">See the following example:</span></span>

    ![選擇圖示](images/lock.png)
    
1.  <span data-ttu-id="e3bc5-206">選取 **[確定]** 儲存快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-206">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="e3bc5-207">以滑鼠右鍵按一下或輕觸並按住快速鍵，然後選取 [ **釘選到工作列**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-207">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="e3bc5-208">將鎖定快捷方式釘選到工作列之後，您就可以將它從桌上型電腦中刪除。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-208">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="e3bc5-209">應用程式</span><span class="sxs-lookup"><span data-stu-id="e3bc5-209">Applications</span></span>

### <span data-ttu-id="e3bc5-210">更新已安裝的應用程式</span><span class="sxs-lookup"><span data-stu-id="e3bc5-210">Update installed apps</span></span>

<span data-ttu-id="e3bc5-211">若要更新所有已安裝的 Microsoft Store 應用程式：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-211">To update all installed Store apps:</span></span>

1. <span data-ttu-id="e3bc5-212">開啟 Microsoft Store 應用程式，然後選取右上角的 [ **查看更多** 省略號]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-212">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="e3bc5-213">選取 [下載與更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-213">Select **Downloads and updates**.</span></span>
2. <span data-ttu-id="e3bc5-214">選取 [取得更新]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-214">Select **Get updates**.</span></span>

### <span data-ttu-id="e3bc5-215">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="e3bc5-215">Microsoft Whiteboard</span></span>

<span data-ttu-id="e3bc5-216">若要安裝 Microsoft 白板：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-216">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="e3bc5-217">選取工作列右下角的 [ **Windows Ink 工作區** ] 圖示，然後下載 [ **白板**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-217">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![筆跡工作區](images/ink.png) 

<span data-ttu-id="e3bc5-219">或者，您可以從 Microsoft 網上商店安裝白板：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-219">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="e3bc5-220">開啟 Microsoft Store app 並搜尋 **白板**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-220">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="e3bc5-221">選擇 [ **不用] 感謝您** 在裝置上登入及使用。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-221">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="e3bc5-222">將白板釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-222">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="e3bc5-223">Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="e3bc5-223">Surface app</span></span>

1. <span data-ttu-id="e3bc5-224">在 Microsoft Store 中，搜尋 **Surface**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-224">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="e3bc5-225">將 [ **在篩選上可用** ] 設定為 [ **所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-225">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="e3bc5-226">安裝 **Surface** app。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-226">Install the **Surface** app.</span></span> <span data-ttu-id="e3bc5-227">這應該是第一個列出的 app。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-227">This should be the first app listed.</span></span> <span data-ttu-id="e3bc5-228">您可能需要將您的 MSA 與書店建立關聯，才能安裝 app。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-228">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="e3bc5-229">將 **表面** app 釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-229">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="e3bc5-230">剪取與繪圖</span><span class="sxs-lookup"><span data-stu-id="e3bc5-230">Snip & Sketch</span></span>

1. <span data-ttu-id="e3bc5-231">開啟 [ **剪取 & 草圖** ] app，然後將它釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-231">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="e3bc5-232">選取右上角的省略號，然後選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-232">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="e3bc5-233">在 [ **設定**] 中，開啟 [ **自動複製到剪貼**簿]、[ **儲存截圖**]，以及 **多個 windows** (選擇性) 。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-233">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="e3bc5-234">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="e3bc5-234">Microsoft Office</span></span>

1. <span data-ttu-id="e3bc5-235">開啟 [Office 入口網站](https://portal.office.com/account#installs) ，並安裝您想要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-235">Open the [Office Portal](https://portal.office.com/account#installs) and install your desired applications.</span></span>

2. <span data-ttu-id="e3bc5-236">將所需的 Office 應用程式釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-236">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="e3bc5-237">如果已安裝 Outlook，請務必將 Outlook OST 設定為只儲存最後兩周的快取。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-237">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="e3bc5-238">這將大大減少磁片使用量和設定時間。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-238">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="e3bc5-239">選取 **[** 檔案  >  **帳戶設定**]，然後選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-239">Select **File** > **Account Settings** and select your account.</span></span>
    - <span data-ttu-id="e3bc5-240">選取 [ **變更** ]，然後將 [使用快取 **Exchange 模式]** 的滑杆設定為14天。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-240">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="e3bc5-241">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e3bc5-241">Microsoft Teams</span></span>

1. <span data-ttu-id="e3bc5-242">下載並安裝 [Microsoft 團隊](https://teams.microsoft.com/downloads)。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-242">Download and install [Microsoft Teams](https://teams.microsoft.com/downloads).</span></span>

2. <span data-ttu-id="e3bc5-243">將設定設定為自動啟動應用程式 (選用的) 。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-243">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="e3bc5-244">將團隊釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-244">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="e3bc5-245">請考慮減少裝置上的小組通知，避免干擾 (選用的) 。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-245">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![團隊通知](images/teams.png)

### <span data-ttu-id="e3bc5-247">Connect app</span><span class="sxs-lookup"><span data-stu-id="e3bc5-247">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3bc5-248">在 Windows 10 版本2004及更新版本中，預設不會安裝使用 Miracast 進行無線投影的連線應用程式，但可將它做為選用的功能。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-248">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="e3bc5-249">如果您已安裝 (或更新為) Windows 版本2004或更新版本，您可能會在 [設定] 中的 [投影至此電腦畫面] 畫面上看到下列資訊：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-249">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![投影到這台電腦](images/sh2-project.png) 


1. <span data-ttu-id="e3bc5-251">若要從 [投影到此電腦] 設定頁面安裝應用程式，請選取 [**選用功能**]  >  **新增功能**，然後安裝 [**無線顯示**] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-251">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="e3bc5-252">在 **某些 Windows 和 Android 裝置下，當您說到 [確定] 時，可以將它投影到這台電腦**，請選擇：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-252">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="e3bc5-253">如果裝置不在商業網路上，就**可以使用所有位置**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-253">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="e3bc5-254">否則，請選擇 [ **所有位置都能在安全網路上使用**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-254">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="e3bc5-255">在 [ **要求 project to 此電腦**] 底下，選擇 [ **僅限第一次**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-255">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="e3bc5-256">在 [ **需要 PIN 以進行配對**] 下，選擇 [ **永不**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-256">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="e3bc5-257">若要啟動 app 並將它釘選到工作列，請搜尋 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-257">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="e3bc5-258">開啟 app。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-258">Open the app.</span></span> <span data-ttu-id="e3bc5-259">在 app 開啟時，以滑鼠右鍵按一下工作列上的 [連接] 應用程式圖示，然後選取 [ **釘選到工作列**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-259">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="e3bc5-260">然後關閉 [連線] app。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-260">Then close the Connect app.</span></span> <span data-ttu-id="e3bc5-261">除非 app 至少執行過一次，否則**此電腦的 Project**可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-261">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="e3bc5-262">在公司網路不使用時的建議配置：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-262">Recommended configuration when not on the corporate network:</span></span>

![在家中的設定](images/project1.png)

<span data-ttu-id="e3bc5-264">公司網路上的建議配置：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-264">Recommended configuration on the corporate network:</span></span>

![工作中的設定](images/project2.png)

### <span data-ttu-id="e3bc5-266">您的手機</span><span class="sxs-lookup"><span data-stu-id="e3bc5-266">Your Phone</span></span>

<span data-ttu-id="e3bc5-267">**您的電話**app 預設會安裝在 Windows 10 上。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-267">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="e3bc5-268">如果不存在，您也可以從 Windows 市集中安裝它。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-268">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="e3bc5-269">如需設定 app 的相關資訊，請參閱 [如何在 Windows 10 設定您的電話，以及如何在您的電腦與手機之間同步處理資料](https://www.windowscentral.com/how-set-your-phone-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-269">For information about setting up the app, see [How to set up Your Phone on Windows 10 and sync data between your PC and phone](https://www.windowscentral.com/how-set-your-phone-windows-10).</span></span> <span data-ttu-id="e3bc5-270">另請參閱 [如何修正您在 Windows 10 上的手機應用程式常見問題](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10)。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-270">Also see [How to fix common problems with Your Phone app on Windows 10](https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10).</span></span>

### <span data-ttu-id="e3bc5-271">超級別致區域</span><span class="sxs-lookup"><span data-stu-id="e3bc5-271">Super Fancy Zones</span></span>

<span data-ttu-id="e3bc5-272">**Super 別致區域** 可協助使用者排列視窗，以最大化螢幕空間。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-272">**Super Fancy Zones** helps users arrange windows to maximize screen real estate.</span></span> <span data-ttu-id="e3bc5-273">它現在包含在 GitHub 上的 [PowerToys](https://github.com/microsoft/PowerToys/releases) 中。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-273">It is now included in [PowerToys](https://github.com/microsoft/PowerToys/releases) on GitHub.</span></span>

### <span data-ttu-id="e3bc5-274">Edge Chromium 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="e3bc5-274">Edge Chromium browser</span></span>

<span data-ttu-id="e3bc5-275">下載並安裝新的 [Edge Chromium 瀏覽器](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL)。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-275">Download and install the new [Edge Chromium browser](https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL).</span></span>

## <span data-ttu-id="e3bc5-276">其他設定</span><span class="sxs-lookup"><span data-stu-id="e3bc5-276">Additional settings</span></span>

### <span data-ttu-id="e3bc5-277">選取以啟動白板的 [畫筆尾部]</span><span class="sxs-lookup"><span data-stu-id="e3bc5-277">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="e3bc5-278">搜尋 **手寫筆** ，然後選取 [ **畫筆] & Windows Ink 設定**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-278">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="e3bc5-279">在靠近頁面底部的 [ **畫筆快速鍵** ] 底下，將 [ **選取一次** 至 **Microsoft 白板**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-279">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="e3bc5-280">電源管理</span><span class="sxs-lookup"><span data-stu-id="e3bc5-280">Power management</span></span>

<span data-ttu-id="e3bc5-281">有數種電源設定可讓您在 Surface Hub 2 上使用 Windows 10 專業版或企業版獲得最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-281">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="e3bc5-282">這包括螢幕和電腦的超時，以及它們如何與內建的人類目前狀態偵測進行互動 (Doppler) 、螢幕保護裝置程式及密碼保護，然後如果您想要如何針對膝上型電腦/電腦版使用者進行群組原則電源設定。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-282">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="e3bc5-283">在 Surface Hub 上的 Windows 10 專業版或企業版中，您可以透過觸控、滑鼠和鍵盤動作，以及內建的人力資源偵測 (Doppler) 來保持畫面進入睡眠狀態。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-283">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="e3bc5-284">預設會啟用 [人力資源] 偵測，但如果需要，您可以在 [Surface UEFI 組態工具] 中切換 [裝置] 選項，或建立並套用較新的 UEFI 設定套件，以將它停在 UEFI 中。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-284">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="e3bc5-285">電源管理：螢幕和電腦睡眠設定</span><span class="sxs-lookup"><span data-stu-id="e3bc5-285">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="e3bc5-286">選取 [**開始**  >  **設定**] [  >  **系統**  >  **電源 & 睡眠**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-286">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="e3bc5-287">設定 [電源模式] 滑杆以 **獲得最佳效能**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-287">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="e3bc5-288">您也可以將畫面和睡眠值設定為您的喜好設定，同時也會在偵測到移動時，在 Doppler 的目前狀態偵測中喚醒。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-288">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="e3bc5-289">因此，建議您在**4 小時**後將畫面設定為**在2小時後**關閉，並將電腦關閉，以進行最佳做法。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-289">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="e3bc5-290">電源管理：螢幕保護裝置程式</span><span class="sxs-lookup"><span data-stu-id="e3bc5-290">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="e3bc5-291">搜尋 **鎖定畫面** 並開啟 **鎖定畫面設定**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-291">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="e3bc5-292">將 **螢幕超時設定** 和 **螢幕保護裝置程式設定** 設定為您的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-292">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="e3bc5-293">建議的預設值為：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-293">Recommended default values are:</span></span>

   - <span data-ttu-id="e3bc5-294">[螢幕保護裝置程式] 可 (無]) 或您選擇的螢幕保護裝置程式。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-294">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="e3bc5-295">等待 "時間到15分鐘。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-295">Wait” time to 15 minutes.</span></span>
   - <span data-ttu-id="e3bc5-296">在 [繼續] 上，顯示 [登入] 畫面。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-296">On resume, display logon screen.</span></span>


**<span data-ttu-id="e3bc5-297">電源管理：群組原則</span><span class="sxs-lookup"><span data-stu-id="e3bc5-297">Power Management: Group Policy</span></span>**

<span data-ttu-id="e3bc5-298">在執行下列程式前，請向您的 IT 部門確認，以核准從全域電源管理原則中排除 Surface Hub 2-2 裝置。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-298">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="e3bc5-299">某些電源管理設定可以停用目前狀態偵測函數。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-299">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="e3bc5-300">搜尋 **軟體中心** 並將它開啟。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-300">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="e3bc5-301">選取 [ **選項**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-301">Select **Options**.</span></span>

3. <span data-ttu-id="e3bc5-302">展開 [ **電源管理**  ]，然後選取 [ **不要將 IT 部門的電源設定套用至此電腦**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-302">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![軟體設定](images/soft-cntr.png)

### <span data-ttu-id="e3bc5-304">儲存空間感知器</span><span class="sxs-lookup"><span data-stu-id="e3bc5-304">Storage Sense</span></span>

<span data-ttu-id="e3bc5-305">Surface Hub 2 在本機儲存空間中有一個 128GB SSD，所以在正常使用期間，必須考慮使用儲存空間儲存量值。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-305">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="e3bc5-306">若要設定儲存空間的意義：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-306">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="e3bc5-307">搜尋 [**系統設定**] 底下的 [**儲存設定**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-307">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="e3bc5-308">在 [ **設定**] 底下，選取 [ **開啟儲存空間感知** ]，開啟 [ **儲存空間** 設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-308">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="e3bc5-309">開啟 [儲存空間感知 **]。**</span><span class="sxs-lookup"><span data-stu-id="e3bc5-309">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="e3bc5-310">選取 [ **設定儲存空間感知] 或 [立即執行** ]，然後設定設定，盡可能讓檔案保持在線上， (因為磁碟空間) 有限。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-310">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="e3bc5-311">建議的設定：</span><span class="sxs-lookup"><span data-stu-id="e3bc5-311">Recommended settings:</span></span>

- <span data-ttu-id="e3bc5-312">每日執行儲存感知 =。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-312">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="e3bc5-313">刪除我的 app 無法使用的臨時檔案 = 每隔14天 (至少) 。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-313">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="e3bc5-314">如果在 [我的下載] 資料夾中有超過30天的檔案，請將它們刪除。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-314">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="e3bc5-315">OneDrive：如果未開啟超過 = 30 天的時間，內容就會變成 [線上]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-315">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="e3bc5-316">平板電腦模式</span><span class="sxs-lookup"><span data-stu-id="e3bc5-316">Tablet mode</span></span>

<span data-ttu-id="e3bc5-317">如有需要，請開啟平板電腦模式以取得協助工具需求。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-317">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="e3bc5-318">音效設定</span><span class="sxs-lookup"><span data-stu-id="e3bc5-318">Sound settings</span></span>

1. <span data-ttu-id="e3bc5-319">搜尋 [ **聲音設定** ]，然後開啟此頁面。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-319">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="e3bc5-320">選取右側的 [ **音效** 控制台]，然後選取 [ **聲音** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-320">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="e3bc5-321">在 [**程式事件**]**下，將** **[裝置**連線] 與 **[裝置中斷連線]**</span><span class="sxs-lookup"><span data-stu-id="e3bc5-321">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="e3bc5-322">靜音通知</span><span class="sxs-lookup"><span data-stu-id="e3bc5-322">Silence notifications</span></span>

1. <span data-ttu-id="e3bc5-323">搜尋 **焦點協助** ，然後開啟此頁面。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-323">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="e3bc5-324">選取 [ **僅限鬧鐘**]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-324">Select **Alarms Only**.</span></span> <span data-ttu-id="e3bc5-325">這將避免持續通知飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-325">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="e3bc5-326">磁碟清理</span><span class="sxs-lookup"><span data-stu-id="e3bc5-326">Disk Cleanup</span></span>

1. <span data-ttu-id="e3bc5-327">搜尋 [ **磁片清理** ] 並開啟此應用程式。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-327">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="e3bc5-328">在 [ **要刪除**的檔案] 底下，選取您要刪除的檔案。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-328">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="e3bc5-329">同時選取 [ **清理系統**檔案]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-329">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="e3bc5-330">完成並驗證</span><span class="sxs-lookup"><span data-stu-id="e3bc5-330">Complete and verify</span></span>

1. <span data-ttu-id="e3bc5-331">掃描並安裝所有的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-331">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="e3bc5-332">更新群組原則</span><span class="sxs-lookup"><span data-stu-id="e3bc5-332">Update Group Policy</span></span>

   1. <span data-ttu-id="e3bc5-333">在提升許可權的命令提示字元中，輸入 **gpupdate/force/boot/wait： 0**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-333">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="e3bc5-334">將裝置重新開機。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-334">Reboot the device.</span></span>

4. <span data-ttu-id="e3bc5-335">驗證工作列 app。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-335">Verify taskbar apps.</span></span>

   - <span data-ttu-id="e3bc5-336">Connect App</span><span class="sxs-lookup"><span data-stu-id="e3bc5-336">Connect App</span></span>
   - <span data-ttu-id="e3bc5-337">[鎖定] 圖示</span><span class="sxs-lookup"><span data-stu-id="e3bc5-337">Lock Icon</span></span>
   - <span data-ttu-id="e3bc5-338">剪取與繪圖</span><span class="sxs-lookup"><span data-stu-id="e3bc5-338">Snip & Sketch</span></span>
   - <span data-ttu-id="e3bc5-339">小組 (（如果適用）) </span><span class="sxs-lookup"><span data-stu-id="e3bc5-339">Teams (if applicable)</span></span>
   - <span data-ttu-id="e3bc5-340">Office 應用程式 (（如果適用）) </span><span class="sxs-lookup"><span data-stu-id="e3bc5-340">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="e3bc5-341">Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="e3bc5-341">Surface App</span></span>
   - <span data-ttu-id="e3bc5-342">白板</span><span class="sxs-lookup"><span data-stu-id="e3bc5-342">Whiteboard</span></span>
    
5. <span data-ttu-id="e3bc5-343">確認目前狀態偵測。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-343">Verify presence detection.</span></span>

   - <span data-ttu-id="e3bc5-344">目前系統託盤中的目前狀態偵測將是綠色圖示。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-344">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="e3bc5-345">確認投影到此電腦的 [連線] App 已啟用。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-345">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="e3bc5-346">**將 Project 設定為這台電腦**設定之後，請至少執行一次 [連線] App。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-346">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="e3bc5-347"> (接著，[連接] App 不需要執行，就能投影至 Surface Hub。 ) </span><span class="sxs-lookup"><span data-stu-id="e3bc5-347">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="e3bc5-348">驗證電源和睡眠設定。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-348">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="e3bc5-349">螢幕保護裝置程式：15分鐘，設定為 (無]) 、Mystify 或空白;確認已選取 [需要密碼的核取方塊]。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-349">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="e3bc5-350">螢幕： **在2小時後關閉**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-350">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="e3bc5-351">PC：  **4 小時後關閉**。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-351">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="e3bc5-352">驗證 Windows Hello 是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-352">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="e3bc5-353">驗證同步處理您的設定已停用。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-353">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="e3bc5-354">確認啟動 app。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-354">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="e3bc5-355">安裝並設定 Windows 10 之後，Surface Hub 的配置可以像管理任何其他的 Windows 10 裝置一樣進行管理。</span><span class="sxs-lookup"><span data-stu-id="e3bc5-355">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="e3bc5-356">相關主題</span><span class="sxs-lookup"><span data-stu-id="e3bc5-356">Related topics</span></span>

[<span data-ttu-id="e3bc5-357">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="e3bc5-357">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span>](surface-hub-2s-migrate-os.md)
