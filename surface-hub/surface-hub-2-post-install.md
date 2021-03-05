---
title: 設定 Windows 10 專業版或 Surface Hub 2 企業版
description: 本文包含建議，以確保使用個人化大型螢幕觸控和觸控筆電腦時獲得最佳體驗。
keywords: Surface Hub， Windows 10， 電腦版， 安裝， 組式
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
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 076d29462ffb949492291e120bcdad538f4287ec
ms.sourcegitcommit: e859374f90d640a5cd4be1c8dcc823bcd537ebdc
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/05/2021
ms.locfileid: "11393590"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a><span data-ttu-id="14ee3-104">設定 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="14ee3-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="14ee3-105">完成移移至 Windows 10 專業版或企業版之安裝程式之後，您可以執行下列步驟，在 Surface Hub 2 上設定應用程式和設定。</span><span class="sxs-lookup"><span data-stu-id="14ee3-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="14ee3-106">建議您執行這些步驟，以確保使用這個個人化的大型螢幕觸控和觸控筆電腦時獲得最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="14ee3-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="14ee3-107">執行這些步驟時，您可能會發現使用有線或無線鍵盤和滑鼠很有用。</span><span class="sxs-lookup"><span data-stu-id="14ee3-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <a name="configure-system-settings"></a><span data-ttu-id="14ee3-108">設定系統設定</span><span class="sxs-lookup"><span data-stu-id="14ee3-108">Configure system settings</span></span>

1. <span data-ttu-id="14ee3-109">使用在裝置上具有當地系統管理員許可權的帳戶進行登錄。</span><span class="sxs-lookup"><span data-stu-id="14ee3-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="14ee3-110">在 Azure AD 加入的裝置上，執行 Azure AD 加入的使用者會自動新增到本地系統管理員群組。</span><span class="sxs-lookup"><span data-stu-id="14ee3-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="14ee3-111">Azure AD 全域系統管理員和 Azure AD 裝置系統管理員 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本地系統管理員 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="14ee3-112">您可以在命令提示輸入 net **localgroup** 系統管理員，以列出具有本地系統管理員許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="14ee3-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="14ee3-113">使用好用的名稱重新命名裝置，例如 **：username-SHub-Desktop。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="14ee3-114">選取**開始**  >  **設定**  >  **帳戶**  >  **同步您的設定**，並關閉**同步**設定。</span><span class="sxs-lookup"><span data-stu-id="14ee3-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="14ee3-115">此處使用的設定旨在啟用最佳的大螢幕觸控體驗，因此您可能不想同步其他裝置。</span><span class="sxs-lookup"><span data-stu-id="14ee3-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="14ee3-116">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="14ee3-116">Restart the device.</span></span>

## <a name="enable-the-touch-keyboard-and-touchpad"></a><span data-ttu-id="14ee3-117">啟用觸控式鍵盤和觸控板</span><span class="sxs-lookup"><span data-stu-id="14ee3-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="14ee3-118">選取**開始**  >  **設定**  >  **裝置**  >  \*\*輸入，\*\*\*\*\*\* 在未在平板電腦模式且未連接鍵盤時開啟顯示觸控式鍵盤。</span><span class="sxs-lookup"><span data-stu-id="14ee3-118">Select **Start** > **Settings** > **Devices** > **Typing** and turn **Show the touch keyboard when not in tablet mode and there's no keyboard attached** on.</span></span>

2. <span data-ttu-id="14ee3-119">點選並按住或以滑鼠右鍵按一下工作列，然後選取 [顯示 **觸控式鍵盤** 按鈕和 **顯示觸控板按鈕**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-119">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="14ee3-120">觸控式鍵盤對於直接使用者輸入很有説明，而虛擬觸控板可協助精確地選取專案、將工具提示停留在畫面上，或作為點選並按住滑鼠右鍵的替代方案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-120">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="14ee3-121">請參閱以下範例。</span><span class="sxs-lookup"><span data-stu-id="14ee3-121">See the following example.</span></span>

      ![觸控設定](images/touch.png)

3. <span data-ttu-id="14ee3-123">將觸控式鍵盤設定為 QWERTY 和浮動。</span><span class="sxs-lookup"><span data-stu-id="14ee3-123">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="14ee3-124">選取 **工作列** 上的鍵盤圖示以顯示觸控式鍵盤。</span><span class="sxs-lookup"><span data-stu-id="14ee3-124">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    1. <span data-ttu-id="14ee3-125">在觸控式鍵盤上，選取左上角的鍵盤圖示以開啟鍵盤設定。</span><span class="sxs-lookup"><span data-stu-id="14ee3-125">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    1. <span data-ttu-id="14ee3-126">選取頂端列上最後一個鍵盤類型以啟用 QWERTY，然後選取第二列的最後一個選項來啟用浮動，這在這個大型螢幕上非常實用。</span><span class="sxs-lookup"><span data-stu-id="14ee3-126">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="14ee3-127">請參閱以下範例。</span><span class="sxs-lookup"><span data-stu-id="14ee3-127">See the following examples.</span></span>

       ![鍵盤設定](images/kbd.png)
 
4. <span data-ttu-id="14ee3-129">設定柔式鍵盤設定。</span><span class="sxs-lookup"><span data-stu-id="14ee3-129">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="14ee3-130">選取觸控 **式** 鍵盤上的設定圖示，或搜尋並開啟 **輸入設定**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-130">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![柔式鍵盤設定](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="14ee3-132">啟用拼字、輸入和觸控式鍵盤下的所有選項。</span><span class="sxs-lookup"><span data-stu-id="14ee3-132">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="14ee3-133">下列範例顯示軌跡板，這很適用于流覽和選取選項。</span><span class="sxs-lookup"><span data-stu-id="14ee3-133">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="14ee3-134">螢幕小鍵盤正用於搜尋 Microsoft Store：</span><span class="sxs-lookup"><span data-stu-id="14ee3-134">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![使用軌跡板](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a><span data-ttu-id="14ee3-136">設定藍牙鍵盤和滑鼠 (選) </span><span class="sxs-lookup"><span data-stu-id="14ee3-136">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="14ee3-137">如果您是使用裝置做為主要 Windows 裝置，或經常使用鍵盤和滑鼠進行輸入或精確作業，請連接鍵盤和滑鼠。</span><span class="sxs-lookup"><span data-stu-id="14ee3-137">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="14ee3-138">如果您的 Surface Hub 裝置靠近電腦，您可以使用沒有邊框的滑鼠，在 Surface Hub 與電腦之間順暢 <a href="https://aka.ms/mm" target="_blank"> </a> 地移動。</span><span class="sxs-lookup"><span data-stu-id="14ee3-138">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="14ee3-139">詳細資訊請參閱 Microsoft 從 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 車庫下載：滑鼠沒有邊框。</span><span class="sxs-lookup"><span data-stu-id="14ee3-139">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <a name="example-of-taskbar-layout"></a><span data-ttu-id="14ee3-140">工作列版面配置範例</span><span class="sxs-lookup"><span data-stu-id="14ee3-140">Example of Taskbar layout</span></span>

<span data-ttu-id="14ee3-141">完成下列步驟以設定/設定 Windows 10 專業版或企業版 Surface Hub 2 後，建議您使用將最常用的應用程式釘到工作列，以快速單鍵啟動每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-141">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="14ee3-142">以下是工作列外觀的範例：</span><span class="sxs-lookup"><span data-stu-id="14ee3-142">Below is an example of what your taskbar could look like:</span></span>

 ![工作列版面配置](images/taskblyt.png)
### <a name="update-installed-apps"></a><span data-ttu-id="14ee3-144">更新已安裝的應用程式</span><span class="sxs-lookup"><span data-stu-id="14ee3-144">Update installed apps</span></span>

<span data-ttu-id="14ee3-145">若要更新所有已安裝的市/市 App：</span><span class="sxs-lookup"><span data-stu-id="14ee3-145">To update all installed Store apps:</span></span>

1. <span data-ttu-id="14ee3-146">開啟 Microsoft Store 應用程式， **然後選取右上角** 的查看更多省略號。</span><span class="sxs-lookup"><span data-stu-id="14ee3-146">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="14ee3-147">選取 **下載和更新。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-147">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="14ee3-148">選取 **取得更新**</span><span class="sxs-lookup"><span data-stu-id="14ee3-148">Select **Get updates**</span></span>

### <a name="scan-for-and-install-all-windows-updates"></a><span data-ttu-id="14ee3-149">掃描並安裝所有 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="14ee3-149">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="14ee3-150">移移至 Windows 10 專業版或 Windows 10 企業版之後，可能有可供您安裝的維護及功能更新。</span><span class="sxs-lookup"><span data-stu-id="14ee3-150">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="14ee3-151">請前往**安全性**  >  **&設定>，** 然後選取**檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-151">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="14ee3-152">如果有任何更新，請安裝更新、重新開機，然後重複此程式，直到您看到下列通知：</span><span class="sxs-lookup"><span data-stu-id="14ee3-152">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Windows Update 的'您為最新狀態'通知](images/wustatus.png)


## <a name="onedrive-for-business"></a><span data-ttu-id="14ee3-154">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="14ee3-154">OneDrive for Business</span></span>

<span data-ttu-id="14ee3-155">使用商務用 OneDrive 輕鬆在所有工作裝置之間共用工具、記錄 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 檔及其他檔案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-155">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="14ee3-156">OneDrive 可讓您在膝上型電腦、Surface Hub 電腦版和 Intune 管理行動裝置之間共用您的工作檔案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-156">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="14ee3-157">您可以在任何裝置上編輯檔案，所有已連接網路之裝置都會隨著變更更新。</span><span class="sxs-lookup"><span data-stu-id="14ee3-157">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="14ee3-158">考慮 Surface Hub SSD (128 GB) 的大小，如果您在 Surface Hub 桌面裝置上設定 OneDrive，請確定預設設定是讓檔案保持線上，並隨著您的使用下載檔案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-158">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="14ee3-159">若要將 OneDrive 設定為僅于需要時下載檔案，請設定 [檔案 **On-Demand」** 設定以節省空間，並在您使用檔案 **時下載檔案**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-159">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="14ee3-160">有關詳細資訊，請參閱 Windows 中的查詢和設定檔案 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> On-Demand 狀態 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-160">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![OneDrive 設定](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="14ee3-162">您也可以重複這些步驟來設定個人 OneDrive，但請務必節省磁碟空間，並只下載您所需的檔案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-162">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <a name="sharepoint-and-teams"></a><span data-ttu-id="14ee3-163">SharePoint 和 Teams</span><span class="sxs-lookup"><span data-stu-id="14ee3-163">SharePoint and Teams</span></span>

<span data-ttu-id="14ee3-164">SharePoint 和 Teams 頻道檔案也可以使用 OneDrive 同步處理引擎，同步處理到您的桌面裝置 ，例如膝上型電腦和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="14ee3-164">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="14ee3-165">若要使用 OneDrive 同步處理應用程式將內部公司檔案同步處理至您的本地磁碟機：</span><span class="sxs-lookup"><span data-stu-id="14ee3-165">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="14ee3-166">前往 SharePoint 網站，並流覽至最頂層的檔目錄，以尋找您有興趣從本地裝置檢視或編輯的檔案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-166">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="14ee3-167">在 SharePoint **功能區** 頂端的同步按鈕上選取。</span><span class="sxs-lookup"><span data-stu-id="14ee3-167">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="14ee3-168">在快顯視窗**上**選取 [開啟此**網站嘗試開啟 Microsoft OneDrive。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-168">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="14ee3-169">選取工作列右下角的 OneDrive 圖示，確認 SharePoint 檔案正在同步處理至您的本地磁碟機機。</span><span class="sxs-lookup"><span data-stu-id="14ee3-169">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="14ee3-170">確認設定設定是讓檔案保持線上，並只在使用檔案時下載：</span><span class="sxs-lookup"><span data-stu-id="14ee3-170">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="14ee3-171">開啟檔案檔案管理器。</span><span class="sxs-lookup"><span data-stu-id="14ee3-171">Open file explorer.</span></span>
    
    2. <span data-ttu-id="14ee3-172">流覽至 SharePoint 名稱，然後以滑鼠右鍵按一下;例如 \*\*，Contoso \ \<SharePoint Document Folder Name\> \*\*。</span><span class="sxs-lookup"><span data-stu-id="14ee3-172">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="14ee3-173">選取 **釋放空間**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-173">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="14ee3-174">狀態列會顯示檔案和資料夾的狀態。</span><span class="sxs-lookup"><span data-stu-id="14ee3-174">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="14ee3-175">詳細資訊請參閱使用 OneDrive 同步處理 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 用戶端同步處理 SharePoint 檔案 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-175">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="14ee3-176">Teams 頻道檔案會儲存在 SharePoint 網站中，並擁有所有相同的 SharePoint 檔功能，包括版本歷程記錄，以及同步處理至您的本地桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="14ee3-176">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="14ee3-177">若要同步處理 Teams 頻道檔案：</span><span class="sxs-lookup"><span data-stu-id="14ee3-177">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="14ee3-178">流覽至感興趣的 Teams 頻道，然後選取 **頂端的檔案** 定位點。</span><span class="sxs-lookup"><span data-stu-id="14ee3-178">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="14ee3-179">然後選取同步 **。** 檔案會開始同步處理，而且將會顯示在\**Desktop \ \<name of the Teams Channel\> Contoso \**的檔案中。</span><span class="sxs-lookup"><span data-stu-id="14ee3-179">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="14ee3-180">使用您用來同步處理 SharePoint 網站的相同程式，將檔案保留于雲端，並只在使用檔案時下載，在 Teams 頻道名稱的 [檔案檔案管理器中點選並按住或以滑鼠右鍵按一下，然後\*\*\*\* 選取釋放空間。</span><span class="sxs-lookup"><span data-stu-id="14ee3-180">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <a name="surface-hub-pen-settings"></a><span data-ttu-id="14ee3-181">Surface Hub 觸控筆設定</span><span class="sxs-lookup"><span data-stu-id="14ee3-181">Surface Hub pen settings</span></span>

**<span data-ttu-id="14ee3-182">配對藍牙 Surface Hub 觸控筆</span><span class="sxs-lookup"><span data-stu-id="14ee3-182">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="14ee3-183">配對觸控筆，讓觸控筆的內建保持最新狀態、設定筆快捷方式，以及取得藍牙裝置設定頁面或 Surface 應用程式中的電池充電資訊：</span><span class="sxs-lookup"><span data-stu-id="14ee3-183">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="14ee3-184">選取**開始**  >  **設定**  >  **裝置**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-184">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="14ee3-185">選取 **新增藍牙或其他裝置**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-185">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="14ee3-186">選擇 **藍牙**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-186">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="14ee3-187">移除筆尾按鈕並搖動以中斷電池連接。</span><span class="sxs-lookup"><span data-stu-id="14ee3-187">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="14ee3-188">重新蓋上保護蓋並按住保護蓋，直到配對的 LED 閃爍。</span><span class="sxs-lookup"><span data-stu-id="14ee3-188">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="14ee3-189">在 Surface Hub 藍牙設定上，選擇 **Surface Hub 2 觸控筆**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-189">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="14ee3-190">完成配對作業。</span><span class="sxs-lookup"><span data-stu-id="14ee3-190">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="14ee3-191">如果配對失敗，您可以嘗試再次配對筆。</span><span class="sxs-lookup"><span data-stu-id="14ee3-191">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="14ee3-192">如果無法運作，您可以驗證觸控筆在 Whiteboard 應用程式中是否可運作，來測試電池是否充電。</span><span class="sxs-lookup"><span data-stu-id="14ee3-192">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="14ee3-193">如果沒有，請更換電池，然後再次嘗試配對筆。</span><span class="sxs-lookup"><span data-stu-id="14ee3-193">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="14ee3-194">如有需要，請重新開機裝置，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="14ee3-194">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="14ee3-195">**設定筆快捷方式** Surface Hub 觸控筆有一個快捷方式按鈕，有時稱為「尾鍵按一下」。</span><span class="sxs-lookup"><span data-stu-id="14ee3-195">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="14ee3-196">如先前所述，若要進行快速鍵的安裝，您需先將筆配對。</span><span class="sxs-lookup"><span data-stu-id="14ee3-196">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="14ee3-197">搜尋手寫筆，然後選取 **Windows Ink &中的手寫筆**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-197">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="14ee3-198">在頁面底部附近，選取可開啟對話方塊的 [筆快捷方式，如下所示：</span><span class="sxs-lookup"><span data-stu-id="14ee3-198">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![筆快捷方式](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a><span data-ttu-id="14ee3-200">相機組配置</span><span class="sxs-lookup"><span data-stu-id="14ee3-200">Camera configuration</span></span>

<span data-ttu-id="14ee3-201">您可以將相機安裝在裝置頂端或任一側。</span><span class="sxs-lookup"><span data-stu-id="14ee3-201">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="14ee3-202">如果您將中心與桌面支架而非購物車一起使用，或靠近中樞，請將相機安裝在一個位置，以優化相機角度。</span><span class="sxs-lookup"><span data-stu-id="14ee3-202">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="14ee3-203">相機不會自動旋轉，因此您必須有 2mm 十六進位鍵，以手動旋轉相機。</span><span class="sxs-lookup"><span data-stu-id="14ee3-203">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="14ee3-204">請參閱 Surface Hub 2S 相機的相機鏡頭方向，以瞭解如何側向安裝相機並手動旋轉 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> 相機 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-204">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <a name="windows-hello-configuration"></a><span data-ttu-id="14ee3-205">Windows Hello 組配置</span><span class="sxs-lookup"><span data-stu-id="14ee3-205">Windows Hello configuration</span></span>

<span data-ttu-id="14ee3-206">執行 Windows 10 企業版 Surface Hub 2S 可讓 Win32 桌面應用程式的完整套件，以及掃描 Windows Hello 選項。</span><span class="sxs-lookup"><span data-stu-id="14ee3-206">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="14ee3-207">Surface Hub 2 指紋識別器配件可以插入裝置上的任何 USB-C 埠。</span><span class="sxs-lookup"><span data-stu-id="14ee3-207">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="14ee3-208">若要訂購 Surface Hub 2 指紋讀取程式或查看技術規格，請參閱 (surface-hub-2-essential-add-ons.md" target="_blank">Surface Hub 2 上的 Windows 10 專業版和企業版基本附加元件。 </a></span><span class="sxs-lookup"><span data-stu-id="14ee3-208">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="14ee3-209">插入指紋識別器之後，請選取 **[開始**  >  **設定**  >  **帳戶**登錄  >  **選項：**  >  **Windows Hello 指紋**來註冊指紋。</span><span class="sxs-lookup"><span data-stu-id="14ee3-209">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="14ee3-210">使用 Windows Hello 認證的裝置進行臉部識別。</span><span class="sxs-lookup"><span data-stu-id="14ee3-210">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="14ee3-211">Surface Hub 2S 相機不支援 Windows Hello 臉部識別。</span><span class="sxs-lookup"><span data-stu-id="14ee3-211">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a><span data-ttu-id="14ee3-212">啟用工作列上的鎖定畫面快捷方式圖示</span><span class="sxs-lookup"><span data-stu-id="14ee3-212">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="14ee3-213">若要新增圖示至工作列，以啟用類似 Windows-L 鍵盤快速鍵的單鍵螢幕鎖定：</span><span class="sxs-lookup"><span data-stu-id="14ee3-213">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="14ee3-214">點選並按住或以滑鼠右鍵按一下桌面，選取 **[新增**  >  **快捷方式**  >  **流覽**  >  **桌面**  >  **確定**  >  **下一步**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-214">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="14ee3-215">提供快速鍵的名稱，例如 **鎖定我的電腦**， **然後選取完成**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-215">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="14ee3-216">以滑鼠右鍵按一下或點選並按住桌面上新建立快速鍵，然後選取 [ **內容**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-216">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="14ee3-217">在快捷方式**定位**點上，在目標欄位中輸入\*\*\*\* 下列專案 **：Rundll32.exe User32.dll，LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="14ee3-217">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="14ee3-218">選取變更 **圖示** 按鈕，然後流覽C:\Windows\System32\imageres.dll\*\* 並選取 \*\* 要使用圖示。</span><span class="sxs-lookup"><span data-stu-id="14ee3-218">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="14ee3-219">請參閱下列範例：</span><span class="sxs-lookup"><span data-stu-id="14ee3-219">See the following example:</span></span>

    ![選擇圖示](images/lock.png)
    
1.  <span data-ttu-id="14ee3-221">選取 **確定** 以儲存快捷方式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-221">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="14ee3-222">以滑鼠右鍵按一下或點選並按住快捷方式，然後選取 [**釘選到工作列。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-222">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="14ee3-223">將鎖定快捷方式釘上工作列之後，就可以從桌面刪除它。</span><span class="sxs-lookup"><span data-stu-id="14ee3-223">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <a name="applications"></a><span data-ttu-id="14ee3-224">應用程式</span><span class="sxs-lookup"><span data-stu-id="14ee3-224">Applications</span></span>


### <a name="microsoft-whiteboard"></a><span data-ttu-id="14ee3-225">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="14ee3-225">Microsoft Whiteboard</span></span>

<span data-ttu-id="14ee3-226">若要安裝 Microsoft Whiteboard：</span><span class="sxs-lookup"><span data-stu-id="14ee3-226">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="14ee3-227">選取**工作列右**下角的 Windows Ink 工作區圖示，然後下載**Whiteboard。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-227">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![筆墨工作區](images/ink.png) 

<span data-ttu-id="14ee3-229">或者，您也可以從 Microsoft Store 安裝 Whiteboard：</span><span class="sxs-lookup"><span data-stu-id="14ee3-229">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="14ee3-230">開啟 Microsoft Store 應用程式並搜尋**Whiteboard。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-230">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="14ee3-231">選擇 **否，** 感謝您在裝置上進行註冊及使用。</span><span class="sxs-lookup"><span data-stu-id="14ee3-231">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="14ee3-232">將白板釘到工作列。</span><span class="sxs-lookup"><span data-stu-id="14ee3-232">Pin Whiteboard to the taskbar.</span></span>

### <a name="surface-app"></a><span data-ttu-id="14ee3-233">Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="14ee3-233">Surface app</span></span>

1. <span data-ttu-id="14ee3-234">在 Microsoft Store 中，搜尋**Surface。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-234">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="14ee3-235">將篩選 **上的可用** 設定為 **所有裝置**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-235">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="14ee3-236">安裝 **Surface** 應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-236">Install the **Surface** app.</span></span> <span data-ttu-id="14ee3-237">這應該是列出的第一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-237">This should be the first app listed.</span></span> <span data-ttu-id="14ee3-238">您可能需要將 MSA 與 Store 關聯，才能安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-238">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="14ee3-239">將 **Surface 應用程式** 釘上工作列。</span><span class="sxs-lookup"><span data-stu-id="14ee3-239">Pin the **Surface** app to taskbar.</span></span>

### <a name="snip--sketch"></a><span data-ttu-id="14ee3-240">剪取與繪圖</span><span class="sxs-lookup"><span data-stu-id="14ee3-240">Snip & Sketch</span></span>

1. <span data-ttu-id="14ee3-241">開啟 **Snip &繪圖** 應用程式，並釘上工作列。</span><span class="sxs-lookup"><span data-stu-id="14ee3-241">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="14ee3-242">選取右上角的省略號， **然後選取設定**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-242">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="14ee3-243">在**設定中**，開啟自動\*\* (\*\*\*\*複製到\*\*剪貼\*\*\*\*) 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-243">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <a name="microsoft-office"></a><span data-ttu-id="14ee3-244">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="14ee3-244">Microsoft Office</span></span>

1. <span data-ttu-id="14ee3-245">開啟 <a href="https://portal.office.com/account#installs" target="_blank"> Office 入口網站 </a> 並安裝您想要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-245">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="14ee3-246">將想要的 Office 應用程式釘上工作列。</span><span class="sxs-lookup"><span data-stu-id="14ee3-246">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="14ee3-247">如果已安裝 Outlook，請務必將 Outlook OST 設為只儲存過去兩周的緩存。</span><span class="sxs-lookup"><span data-stu-id="14ee3-247">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="14ee3-248">這會大量減少磁片使用量和設定時間。</span><span class="sxs-lookup"><span data-stu-id="14ee3-248">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="14ee3-249">選取**檔案**  >  **帳戶設定，** 然後選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="14ee3-249">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="14ee3-250">選取 **變更** ，將使用 Exchange 緩存模式 **滑杆設定** 為 14 天。</span><span class="sxs-lookup"><span data-stu-id="14ee3-250">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <a name="microsoft-teams"></a><span data-ttu-id="14ee3-251">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="14ee3-251">Microsoft Teams</span></span>

1. <span data-ttu-id="14ee3-252">下載並安裝 <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft </a> Teams。</span><span class="sxs-lookup"><span data-stu-id="14ee3-252">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="14ee3-253">將設定為自動啟動應用程式 (選) 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-253">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="14ee3-254">將 Teams 釘到工作列。</span><span class="sxs-lookup"><span data-stu-id="14ee3-254">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="14ee3-255">考慮減少裝置上的 Teams 通知，以避免干擾 (選擇) 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-255">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![Teams 通知](images/teams.png)

### <a name="connect-app"></a><span data-ttu-id="14ee3-257">連接應用程式</span><span class="sxs-lookup"><span data-stu-id="14ee3-257">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14ee3-258">在 Windows 10 版本 2004 及更新版本中，使用 Miracast 進行無線投影的 Connect 應用程式預設不會安裝，但提供選擇性功能。</span><span class="sxs-lookup"><span data-stu-id="14ee3-258">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="14ee3-259">如果您已經安裝 (或更新至) Windows 版本 2004 或更新版本，您可能會在設定中于 Projecting 到此電腦畫面上看到下列內容：</span><span class="sxs-lookup"><span data-stu-id="14ee3-259">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![Project 到此電腦](images/sh2-project.png) 


1. <span data-ttu-id="14ee3-261">若要從 「Projecting to this PC」設定頁面安裝應用程式，請選取選擇性**功能**新增功能  >  \*\* **，然後安裝**無線顯示\*\*應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-261">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="14ee3-262">當您 **說**它沒問題時，在某些 Windows 和 Android 裝置可以預測到這部電腦下，選擇：</span><span class="sxs-lookup"><span data-stu-id="14ee3-262">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="14ee3-263">**如果裝置不在** 公司網路上，則可于任何地方使用。</span><span class="sxs-lookup"><span data-stu-id="14ee3-263">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="14ee3-264">否則，請選擇**安全網路上所有位置的可用。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-264">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="14ee3-265">在 **要求專案到這部電腦下**，選擇僅 **第一次**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-265">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="14ee3-266">在**需要 PIN 進行配對下\*\*\*\*，選擇永不**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-266">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="14ee3-267">若要啟動應用程式並釘上工作列，請搜尋**Connect。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-267">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="14ee3-268">開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-268">Open the app.</span></span> <span data-ttu-id="14ee3-269">當應用程式開啟時，以滑鼠右鍵按一下工作列上的 [連接應用程式圖示，然後選取 **釘選到工作列**上。</span><span class="sxs-lookup"><span data-stu-id="14ee3-269">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="14ee3-270">然後關閉 Connect 應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-270">Then close the Connect app.</span></span> <span data-ttu-id="14ee3-271">**除非應用程式至少** 執行過一次，否則 Project 到此電腦可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="14ee3-271">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="14ee3-272">不在公司網路上時的建議群組原則：</span><span class="sxs-lookup"><span data-stu-id="14ee3-272">Recommended configuration when not on the corporate network:</span></span>

![家裡的設定](images/project1.png)

<span data-ttu-id="14ee3-274">公司網路上的建議群組原則：</span><span class="sxs-lookup"><span data-stu-id="14ee3-274">Recommended configuration on the corporate network:</span></span>

![工作中的設定](images/project2.png)

### <a name="your-phone"></a><span data-ttu-id="14ee3-276">您的手機</span><span class="sxs-lookup"><span data-stu-id="14ee3-276">Your Phone</span></span>

<span data-ttu-id="14ee3-277">Windows \*\*\*\* 10 預設會安裝您的手機應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-277">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="14ee3-278">如果沒有，您也可以從 Windows 市儲存區安裝。</span><span class="sxs-lookup"><span data-stu-id="14ee3-278">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="14ee3-279">有關設定應用程式的資訊，請參閱如何在 Windows 10 上設定您的手機，以及如何同步處理 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 電腦與手機之間的資料 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-279">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="14ee3-280">另請參閱 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 如何修正 Windows 10 上您的手機應用程式的常見問題 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-280">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <a name="fancy-zones"></a><span data-ttu-id="14ee3-281">花俏的區域</span><span class="sxs-lookup"><span data-stu-id="14ee3-281">Fancy Zones</span></span>


<span data-ttu-id="14ee3-282">**花俏區域** 是 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> GitHub 上名為 PowerToys 的工具 </a> 集合的一部分。</span><span class="sxs-lookup"><span data-stu-id="14ee3-282">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="14ee3-283">這是在 Surface Hub 2 上運用螢幕空間的一種好方式，讓您定義顯示器上的固定版面配置 ("區域") ，然後選取要在每個區域中執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-283">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="14ee3-284">[PowerToys Wiki](https://github.com/microsoft/PowerToys/wiki)提供如何使用及自訂每個工具的指示，包括[花式區域](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)。</span><span class="sxs-lookup"><span data-stu-id="14ee3-284">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="14ee3-285">在高層級 – 安裝 PowerToys 之後，您可以選取或建立自訂版面配置，然後按住 Shift 鍵並拖曳，或使用鍵盤鍵將執行中的應用程式移至特定區域。</span><span class="sxs-lookup"><span data-stu-id="14ee3-285">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="14ee3-286">使用藍牙或 USB 鍵盤和滑鼠可協助進行這項操作，或者您可以使用螢幕觸控式鍵盤和觸控板。</span><span class="sxs-lookup"><span data-stu-id="14ee3-286">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="14ee3-287">Power toys 秘訣</span><span class="sxs-lookup"><span data-stu-id="14ee3-287">Power toys tips</span></span>**
- <span data-ttu-id="14ee3-288">若要在 GitHub 上接收 PowerToys 版本更新的電子郵件通知，請按一下頁面頂端的 [註冊> [按鈕](https://github.com/microsoft/PowerToys/releases)。</span><span class="sxs-lookup"><span data-stu-id="14ee3-288">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="14ee3-289">安裝 PowerToys 之後，您可以設定 PowerToys 設定自動下載更新，以接收 Windows 通知和/或\*\*\*\* 下載及安裝最新的更新。</span><span class="sxs-lookup"><span data-stu-id="14ee3-289">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="14ee3-290">若要取得 PowerToys 設定，請選取工作列上\*\*\*\* 向上的 [執行中應用程式，然後以滑鼠右鍵按一下或按住 PowerToys 圖示，直到功能表出現。</span><span class="sxs-lookup"><span data-stu-id="14ee3-290">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="14ee3-291">選取 「設定」。</span><span class="sxs-lookup"><span data-stu-id="14ee3-291">Select “Settings”.</span></span>
- <span data-ttu-id="14ee3-292">在 PowerToys 設定頁面的底部，自動開啟 **下載** 更新。</span><span class="sxs-lookup"><span data-stu-id="14ee3-292">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="14ee3-293">更新發行後，系統會顯示 Windows 通知，讓您選擇安裝更新時間。</span><span class="sxs-lookup"><span data-stu-id="14ee3-293">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <a name="edge-chromium-browser"></a><span data-ttu-id="14ee3-294">Edge Chromium 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="14ee3-294">Edge Chromium browser</span></span>

<span data-ttu-id="14ee3-295">下載並安裝新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 瀏覽器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-295">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <a name="surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="14ee3-296">Surface Hub 硬體診斷工具</span><span class="sxs-lookup"><span data-stu-id="14ee3-296">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="14ee3-297">Microsoft Store 免費提供 Surface Hub 硬體診斷 <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> </a> 工具。</span><span class="sxs-lookup"><span data-stu-id="14ee3-297">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="14ee3-298">此工具的設計可協助確保 Surface Hub 的執行效果最佳。</span><span class="sxs-lookup"><span data-stu-id="14ee3-298">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="14ee3-299">它包含測試，以判斷您的中器是否為最新狀態並正確進行安裝。</span><span class="sxs-lookup"><span data-stu-id="14ee3-299">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="14ee3-300">互動式測試允許您確認基本功能是否如預期地執行。</span><span class="sxs-lookup"><span data-stu-id="14ee3-300">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="14ee3-301">如果遇到問題，可以將結果儲存起來，與 Surface Hub 支援小組分享。</span><span class="sxs-lookup"><span data-stu-id="14ee3-301">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="14ee3-302">按一下連結以從 Microsoft Store 安裝，然後將應用程式釘到工作列。</span><span class="sxs-lookup"><span data-stu-id="14ee3-302">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <a name="additional-settings"></a><span data-ttu-id="14ee3-303">其他設定</span><span class="sxs-lookup"><span data-stu-id="14ee3-303">Additional settings</span></span>

### <a name="pen-tail-select-to-launch-whiteboard"></a><span data-ttu-id="14ee3-304">選取筆尾以啟動 Whiteboard</span><span class="sxs-lookup"><span data-stu-id="14ee3-304">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="14ee3-305">搜尋手寫 **筆，** 然後選取 **Windows Ink &中的手寫筆**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-305">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="14ee3-306">靠近頁面底部，在**筆快捷方式下將\*\*\*\*選取一**次設定為**Microsoft Whiteboard。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-306">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <a name="power-management"></a><span data-ttu-id="14ee3-307">電源管理</span><span class="sxs-lookup"><span data-stu-id="14ee3-307">Power management</span></span>

<span data-ttu-id="14ee3-308">有幾個電源設定可用，以在 Surface Hub 2 上使用 Windows 10 專業版或企業版獲得最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="14ee3-308">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="14ee3-309">這包括螢幕和電腦超時，以及它們如何與內建的人體目前狀態偵測 (Doppler) 、螢幕保護裝置與密碼保護互動，以及適當時如何為膝上型電腦/桌面使用者進行群組原則電源設定。</span><span class="sxs-lookup"><span data-stu-id="14ee3-309">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="14ee3-310">Surface Hub 2 上的 Windows 10 專業版或企業版可觸控、滑鼠和鍵盤動作，以及內建的人體檢出偵測功能 (Doppler) ，防止螢幕進入睡眠狀態。</span><span class="sxs-lookup"><span data-stu-id="14ee3-310">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="14ee3-311">系統預設會啟用人力偵測功能，但如果需要，可以在 UEFI 中停用偵測功能，方法包括切換 Surface UEFI Configurationator 工具中的裝置選項做為初始移移的一部分，或建立並套用稍後的 UEFI 群組原則套件。</span><span class="sxs-lookup"><span data-stu-id="14ee3-311">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="14ee3-312">Power Management：螢幕和電腦睡眠設定</span><span class="sxs-lookup"><span data-stu-id="14ee3-312">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="14ee3-313">選取**啟動**  >  **設定**  >  **系統**  >  **電源&睡眠**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-313">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="14ee3-314">將電源模式滑杆設定為 **最佳效果**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-314">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="14ee3-315">將螢幕和睡眠值設定為您的喜好設定，同時也會計算偵測到移動時喚醒裝置之 Doppler 目前狀態偵測。</span><span class="sxs-lookup"><span data-stu-id="14ee3-315">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="14ee3-316">因此，最佳作法是將螢幕設定為 **2** 小時後關閉，而電腦在 **4 小時後關閉。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-316">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="14ee3-317">Power Management：螢幕保護裝置</span><span class="sxs-lookup"><span data-stu-id="14ee3-317">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="14ee3-318">搜尋鎖定 **畫面並** 開啟 **鎖定畫面設定**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-318">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="14ee3-319">將**螢幕超時設定和\*\*\*\*螢幕保護裝置設定**為您的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="14ee3-319">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="14ee3-320">建議的預設值為：</span><span class="sxs-lookup"><span data-stu-id="14ee3-320">Recommended default values are:</span></span>

   - <span data-ttu-id="14ee3-321">螢幕保護裝置 (無) 或您所選擇的螢幕保護裝置程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-321">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="14ee3-322">等候時間到 15 分鐘。</span><span class="sxs-lookup"><span data-stu-id="14ee3-322">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="14ee3-323">在履歷表上，顯示登入畫面。</span><span class="sxs-lookup"><span data-stu-id="14ee3-323">On resume, display logon screen.</span></span>


**<span data-ttu-id="14ee3-324">Power Management：群組原則</span><span class="sxs-lookup"><span data-stu-id="14ee3-324">Power Management: Group Policy</span></span>**

<span data-ttu-id="14ee3-325">執行下列程式之前，請向 IT 部門確認核准，以將 Surface Hub 2S 裝置排除在全域電源管理政策外。</span><span class="sxs-lookup"><span data-stu-id="14ee3-325">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="14ee3-326">某些電源管理設定可能會停用目前狀態偵測功能。</span><span class="sxs-lookup"><span data-stu-id="14ee3-326">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="14ee3-327">搜尋軟體 **中心並** 開啟。</span><span class="sxs-lookup"><span data-stu-id="14ee3-327">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="14ee3-328">選取 **選項**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-328">Select **Options**.</span></span>

3. <span data-ttu-id="14ee3-329">展開 **電源管理，**  然後 **選取不要將**IT 部門的電源設定適用于這台電腦。</span><span class="sxs-lookup"><span data-stu-id="14ee3-329">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![軟體設定](images/soft-cntr.png)

### <a name="storage-sense"></a><span data-ttu-id="14ee3-331">儲存空間感知器</span><span class="sxs-lookup"><span data-stu-id="14ee3-331">Storage Sense</span></span>

<span data-ttu-id="14ee3-332">Surface Hub 2 具有 128 GB 的局內儲存空間 SSD，因此在一般使用期間，必須考慮儲存空間儲存量。</span><span class="sxs-lookup"><span data-stu-id="14ee3-332">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="14ee3-333">若要設定儲存空間感知：</span><span class="sxs-lookup"><span data-stu-id="14ee3-333">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="14ee3-334">搜尋儲存 **空間設定**，此設定位於系統 **設定下**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-334">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="14ee3-335">在 **設定下**， **選取開啟儲存空間感知來** 開啟 **儲存空間** 設定頁面。</span><span class="sxs-lookup"><span data-stu-id="14ee3-335">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="14ee3-336">將儲存空間感知 **功能開啟**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-336">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="14ee3-337">選取 **設定儲存空間感知程式或現在** 執行，並設定設定讓檔案盡可能保持線上 (因為磁碟空間有限) 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-337">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="14ee3-338">建議設定：</span><span class="sxs-lookup"><span data-stu-id="14ee3-338">Recommended settings:</span></span>

- <span data-ttu-id="14ee3-339">執行儲存空間感知 = 每天。</span><span class="sxs-lookup"><span data-stu-id="14ee3-339">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="14ee3-340">刪除我的應用程式未使用的暫) = 每 14 天 (一次) 。</span><span class="sxs-lookup"><span data-stu-id="14ee3-340">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="14ee3-341">如果檔案存在超過 = 30 天，請刪除我的下載資料夾中的檔案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-341">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="14ee3-342">OneDrive：如果超過 = 30 天，內容將會變成僅線上。</span><span class="sxs-lookup"><span data-stu-id="14ee3-342">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <a name="tablet-mode"></a><span data-ttu-id="14ee3-343">平板電腦模式</span><span class="sxs-lookup"><span data-stu-id="14ee3-343">Tablet mode</span></span>

<span data-ttu-id="14ee3-344">如果需要協助工具，請開啟平板電腦模式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-344">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <a name="sound-settings"></a><span data-ttu-id="14ee3-345">音效設定</span><span class="sxs-lookup"><span data-stu-id="14ee3-345">Sound settings</span></span>

1. <span data-ttu-id="14ee3-346">搜尋音效 **設定並** 開啟此頁面。</span><span class="sxs-lookup"><span data-stu-id="14ee3-346">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="14ee3-347">選取 **右邊的** 音效控制台，然後選取的音效 **製表** 位。</span><span class="sxs-lookup"><span data-stu-id="14ee3-347">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="14ee3-348">在**程式事件設定\*\*\*\*下，裝置連接\*\*\*\*與裝置中斷連\*\*\*\*至無**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-348">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <a name="silence-notifications"></a><span data-ttu-id="14ee3-349">靜音通知</span><span class="sxs-lookup"><span data-stu-id="14ee3-349">Silence notifications</span></span>

1. <span data-ttu-id="14ee3-350">搜尋焦點 **輔助，** 然後開啟此頁面。</span><span class="sxs-lookup"><span data-stu-id="14ee3-350">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="14ee3-351">僅 **選取鬧鐘**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-351">Select **Alarms Only**.</span></span> <span data-ttu-id="14ee3-352">這可避免常數通知飛出。</span><span class="sxs-lookup"><span data-stu-id="14ee3-352">This will avoid constant notification flyouts.</span></span>

### <a name="disk-cleanup"></a><span data-ttu-id="14ee3-353">磁碟清理</span><span class="sxs-lookup"><span data-stu-id="14ee3-353">Disk Cleanup</span></span>

1. <span data-ttu-id="14ee3-354">搜尋磁片 **清理並** 開啟此應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-354">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="14ee3-355">在 **要刪除的檔案**下，選取要刪除的檔案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-355">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="14ee3-356">同時選取 **清理系統檔案**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-356">Also select **Clean up system files**.</span></span>

## <a name="complete-and-verify"></a><span data-ttu-id="14ee3-357">完成並驗證</span><span class="sxs-lookup"><span data-stu-id="14ee3-357">Complete and verify</span></span>

1. <span data-ttu-id="14ee3-358">掃描並安裝所有 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="14ee3-358">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="14ee3-359">更新群組原則。</span><span class="sxs-lookup"><span data-stu-id="14ee3-359">Update Group Policy.</span></span>

   1. <span data-ttu-id="14ee3-360">在提升許可權的命令提示符中，輸入**gpupdate /force /boot /wait：0。**</span><span class="sxs-lookup"><span data-stu-id="14ee3-360">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="14ee3-361">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="14ee3-361">Restart the device.</span></span>

4. <span data-ttu-id="14ee3-362">驗證工作列應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-362">Verify taskbar apps.</span></span>

   - <span data-ttu-id="14ee3-363">連接應用程式</span><span class="sxs-lookup"><span data-stu-id="14ee3-363">Connect App</span></span>
   - <span data-ttu-id="14ee3-364">鎖定圖示</span><span class="sxs-lookup"><span data-stu-id="14ee3-364">Lock Icon</span></span>
   - <span data-ttu-id="14ee3-365">剪取與繪圖</span><span class="sxs-lookup"><span data-stu-id="14ee3-365">Snip & Sketch</span></span>
   - <span data-ttu-id="14ee3-366">Teams (如適用，) </span><span class="sxs-lookup"><span data-stu-id="14ee3-366">Teams (if applicable)</span></span>
   - <span data-ttu-id="14ee3-367">如果適用 (Office 應用程式) </span><span class="sxs-lookup"><span data-stu-id="14ee3-367">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="14ee3-368">Surface App</span><span class="sxs-lookup"><span data-stu-id="14ee3-368">Surface App</span></span>
   - <span data-ttu-id="14ee3-369">白板</span><span class="sxs-lookup"><span data-stu-id="14ee3-369">Whiteboard</span></span>
    
5. <span data-ttu-id="14ee3-370">確認目前狀態偵測。</span><span class="sxs-lookup"><span data-stu-id="14ee3-370">Verify presence detection.</span></span>

   - <span data-ttu-id="14ee3-371">目前狀態偵測會為系統磁碟機中的綠色圖示。</span><span class="sxs-lookup"><span data-stu-id="14ee3-371">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="14ee3-372">使用 Connect App 確認已啟用此電腦的專案。</span><span class="sxs-lookup"><span data-stu-id="14ee3-372">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="14ee3-373">將  **Project 設定為此電腦** 設定之後，請至少執行一次 Connect App。</span><span class="sxs-lookup"><span data-stu-id="14ee3-373">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="14ee3-374"> (之後，Connect App 不需要執行，也不需要執行，也不需要專案到 Surface Hub.) </span><span class="sxs-lookup"><span data-stu-id="14ee3-374">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="14ee3-375">確認電源和睡眠設定。</span><span class="sxs-lookup"><span data-stu-id="14ee3-375">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="14ee3-376">螢幕保護裝置：15 分鐘，設定為 (、) 、Mystify 或 Blank;確認已選取要求密碼的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="14ee3-376">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="14ee3-377">螢幕 **：2 小時後關閉**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-377">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="14ee3-378">電腦  **：4 小時後關閉**。</span><span class="sxs-lookup"><span data-stu-id="14ee3-378">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="14ee3-379">確認 Windows Hello 可以工作。</span><span class="sxs-lookup"><span data-stu-id="14ee3-379">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="14ee3-380">確認同步您的設定已停用。</span><span class="sxs-lookup"><span data-stu-id="14ee3-380">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="14ee3-381">驗證啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="14ee3-381">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="14ee3-382">安裝及安裝 Windows 10 之後，Surface Hub 2S 可以像管理任何其他 Windows 10 裝置一樣受到管理。</span><span class="sxs-lookup"><span data-stu-id="14ee3-382">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <a name="related-topics"></a><span data-ttu-id="14ee3-383">相關主題</span><span class="sxs-lookup"><span data-stu-id="14ee3-383">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="14ee3-384">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="14ee3-384">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
