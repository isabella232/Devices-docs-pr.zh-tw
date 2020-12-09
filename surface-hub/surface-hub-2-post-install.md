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
ms.date: 12/08/2020
appliesto:
- Surface Hub 2S
ms.openlocfilehash: 7accbe3d905af3b295f92c002eecd5d77356672d
ms.sourcegitcommit: e126b8ac66a781ebe42cdd677af3fe6a2eb5e72c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2020
ms.locfileid: "11203550"
---
# <span data-ttu-id="c988e-104">設定 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="c988e-104">Configure Windows 10 Pro or Enterprise on Surface Hub 2</span></span>

<span data-ttu-id="c988e-105">完成遷移至 Windows 10 專業版或企業版的安裝程式後，您可以執行下列步驟來設定 Surface Hub 2 上的 app 和設定。</span><span class="sxs-lookup"><span data-stu-id="c988e-105">After you have completed the installation process of migrating to Windows 10 Pro or Enterprise, you can perform the following steps to configure apps and settings on your Surface Hub 2.</span></span> <span data-ttu-id="c988e-106">建議使用這些步驟，以確保使用此個人化大型螢幕觸控和手寫筆電腦時的最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="c988e-106">These steps are recommended to ensure the best experience when using this personalized large screen touch and pen computer.</span></span>

<span data-ttu-id="c988e-107">執行這些步驟時，您可能會發現使用有線或無線鍵盤和滑鼠很有用。</span><span class="sxs-lookup"><span data-stu-id="c988e-107">When performing these steps, you might find it useful to use a wired or wireless keyboard and mouse.</span></span>

## <span data-ttu-id="c988e-108">設定系統設定</span><span class="sxs-lookup"><span data-stu-id="c988e-108">Configure system settings</span></span>

1. <span data-ttu-id="c988e-109">使用具有裝置上的本機系統管理員許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="c988e-109">Sign in with an account that has local administrator privileges on the device.</span></span>  

    - <span data-ttu-id="c988e-110">在 Azure AD 已加入的裝置上，執行 Azure AD 連接的使用者會自動新增到本機管理員群組中。</span><span class="sxs-lookup"><span data-stu-id="c988e-110">On Azure AD joined devices, the user that performs the Azure AD join is automatically added to the local administrator group.</span></span> <span data-ttu-id="c988e-111">Azure AD 全域系統管理員和 Azure AD 裝置管理員 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本機管理員 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-111">Azure AD global administrators and Azure AD devices administrators are <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank">also local administrators</a>.</span></span> 
    
    - <span data-ttu-id="c988e-112">您可以在命令提示字元中輸入 **net localgroup 管理員** ，以列出具有本機系統管理員許可權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c988e-112">You can type **net localgroup administrators** at a command prompt to list the accounts that have local administrator rights.</span></span>
    
2. <span data-ttu-id="c988e-113">使用易記的名稱重新命名裝置，例如： **username-SHub-Desktop**。</span><span class="sxs-lookup"><span data-stu-id="c988e-113">Rename the device using a friendly name, for example: **username-SHub-Desktop**.</span></span>

3. <span data-ttu-id="c988e-114">選取 [**啟動**  >  **設定**  >  **帳戶**] [  >  **同步處理您的設定**]，然後關閉同步處理**設定**。</span><span class="sxs-lookup"><span data-stu-id="c988e-114">Select **Start** > **Settings** > **Accounts** > **Sync your settings** and turn **Sync settings** off.</span></span> 

    - <span data-ttu-id="c988e-115">這裡使用的設定是用來啟用最佳的螢幕觸控體驗，因此您可能不想同步處理其他裝置。</span><span class="sxs-lookup"><span data-stu-id="c988e-115">The settings used here are intended to enable the best large-screen touch experience, and therefore you may not want to sync other devices.</span></span>
    
4. <span data-ttu-id="c988e-116">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="c988e-116">Restart the device.</span></span>

## <span data-ttu-id="c988e-117">啟用觸控式鍵盤與觸控板</span><span class="sxs-lookup"><span data-stu-id="c988e-117">Enable the touch keyboard and touchpad</span></span>

1. <span data-ttu-id="c988e-118">按住或以滑鼠右鍵按一下工作列，然後選取 [ **顯示觸控式鍵盤] 按鈕** ，然後選取 [ **顯示觸控板] 按鈕**。</span><span class="sxs-lookup"><span data-stu-id="c988e-118">Tap and hold or right-click the taskbar and then select **Show touch keyboard button** and **Show touchpad button**.</span></span> 

    - <span data-ttu-id="c988e-119">觸控式鍵盤對直接使用者輸入很有説明，而虛擬觸控板可協助您精確選擇、懸停工具提示，或代替按一下滑鼠右鍵。</span><span class="sxs-lookup"><span data-stu-id="c988e-119">The touch keyboard is helpful for direct user input, and the virtual touchpad helps with precise selections, hovering screen tips, or as an alternative to tap and hold for right-click.</span></span> 
    
    - <span data-ttu-id="c988e-120">請參閱以下範例。</span><span class="sxs-lookup"><span data-stu-id="c988e-120">See the following example.</span></span>

      ![觸控設定](images/touch.png)

2. <span data-ttu-id="c988e-122">將觸控式鍵盤設定成標準和浮動。</span><span class="sxs-lookup"><span data-stu-id="c988e-122">Configure the touch keyboard to QWERTY and floating.</span></span>

    1. <span data-ttu-id="c988e-123">選取工作列上的 **鍵盤** 圖示以顯示觸控式鍵盤。</span><span class="sxs-lookup"><span data-stu-id="c988e-123">Select the **Keyboard** icon on the taskbar to show the touch keyboard.</span></span>
    
    2. <span data-ttu-id="c988e-124">在觸控式鍵盤上，選取左上角的 [鍵盤] 圖示以開啟 [鍵盤設定]。</span><span class="sxs-lookup"><span data-stu-id="c988e-124">On the touch keyboard, select the keyboard icon in the upper left corner to open keyboard settings.</span></span>
    
    3. <span data-ttu-id="c988e-125">選取上方列的 [最後一個鍵盤類型] 旁的 [啟用標準]，然後在第二個數據列的最後一個選項上啟用 [浮動]，這在這個大型螢幕上很有説明。</span><span class="sxs-lookup"><span data-stu-id="c988e-125">Select the next to last keyboard type on the top row to enable QWERTY, and the last option on the second row to enable floating, which is very helpful on this large screen.</span></span> <span data-ttu-id="c988e-126">請參閱以下範例。</span><span class="sxs-lookup"><span data-stu-id="c988e-126">See the following examples.</span></span>

       ![鍵盤設定](images/kbd.png)
 
3. <span data-ttu-id="c988e-128">設定軟鍵盤設定。</span><span class="sxs-lookup"><span data-stu-id="c988e-128">Configure the soft keyboard settings.</span></span>

    1. <span data-ttu-id="c988e-129">選取觸控式鍵盤上的 [ **設定** ] 圖示，或搜尋並開啟 **輸入設定**。</span><span class="sxs-lookup"><span data-stu-id="c988e-129">Select the **Settings** icon on the touch keyboard or search for and open **Typing settings**.</span></span>
    
       ![軟鍵盤設定](images/sh2-softkeyboard.png)

    1. <span data-ttu-id="c988e-131">啟用 [拼寫檢查]、[輸入] 和 [觸控式鍵盤] 底下的所有選項。</span><span class="sxs-lookup"><span data-stu-id="c988e-131">Enable all the options under Spelling, Typing, and Touch keyboard.</span></span>


<span data-ttu-id="c988e-132">下列範例顯示軌跡板，這對流覽和選取選項很有用。</span><span class="sxs-lookup"><span data-stu-id="c988e-132">The following example shows the trackpad, which is useful to navigate and select options.</span></span> <span data-ttu-id="c988e-133">使用螢幕小鍵盤來搜尋 Microsoft Store：</span><span class="sxs-lookup"><span data-stu-id="c988e-133">The onscreen keyboard is being used to search the Microsoft Store:</span></span>

![使用軌跡板](images/store.png)

## <span data-ttu-id="c988e-135">設定藍牙鍵盤和滑鼠 (選用) </span><span class="sxs-lookup"><span data-stu-id="c988e-135">Configure Bluetooth keyboard and mouse (optional)</span></span>

<span data-ttu-id="c988e-136">如果您使用的是裝置作為主要 Windows 裝置，或者您經常使用它來輸入或精確作業，請連接鍵盤和滑鼠。</span><span class="sxs-lookup"><span data-stu-id="c988e-136">Connect a keyboard and mouse if you are using the device as your primary Windows device, or you use it often for typing or precision work.</span></span>

<span data-ttu-id="c988e-137">如果您的 Surface Hub 裝置靠近電腦，您可以使用 <a href="https://aka.ms/mm" target="_blank"> 沒有框線的滑鼠在 </a> surface HUB 和電腦之間順暢移動。</span><span class="sxs-lookup"><span data-stu-id="c988e-137">If your Surface Hub device is near to a PC, you can use <a href="https://aka.ms/mm" target="_blank"> Mouse without Borders</a> to move seamlessly between the Surface Hub and the PC.</span></span> <span data-ttu-id="c988e-138">如需詳細資訊，請參閱 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 從車庫取得 Microsoft 下載：不含框線的滑鼠。</span><span class="sxs-lookup"><span data-stu-id="c988e-138">For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders.</span></span> </a>

## <span data-ttu-id="c988e-139">工作列版面配置範例</span><span class="sxs-lookup"><span data-stu-id="c988e-139">Example of Taskbar layout</span></span>

<span data-ttu-id="c988e-140">完成下列步驟以設定/設定您的 Surface Hub （適用于 Windows 10 專業版或企業版）之後，我們建議您利用將最常用的應用程式釘選到工作列，以快速地啟動每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="c988e-140">After completing the below steps to setup/configure your Surface Hub 2 for Windows 10 Professional or Enterprise, we recommend you utilize pinning your most used applications to the Taskbar for a quick one-touch launch of each application.</span></span> <span data-ttu-id="c988e-141">以下是工作列可能看起來的範例：</span><span class="sxs-lookup"><span data-stu-id="c988e-141">Below is an example of what your taskbar could look like:</span></span>

 ![工作列版面配置](images/taskblyt.png)
### <span data-ttu-id="c988e-143">更新已安裝的應用程式</span><span class="sxs-lookup"><span data-stu-id="c988e-143">Update installed apps</span></span>

<span data-ttu-id="c988e-144">若要更新所有已安裝的 Microsoft Store 應用程式：</span><span class="sxs-lookup"><span data-stu-id="c988e-144">To update all installed Store apps:</span></span>

1. <span data-ttu-id="c988e-145">開啟 Microsoft Store 應用程式，然後選取右上角的 [ **查看更多** 省略號]。</span><span class="sxs-lookup"><span data-stu-id="c988e-145">Open Microsoft Store app and select the **See more** ellipsis in the top-right corner.</span></span>
2. <span data-ttu-id="c988e-146">選取 [ **下載與更新]。**</span><span class="sxs-lookup"><span data-stu-id="c988e-146">Select **Downloads and updates.**</span></span>
3. <span data-ttu-id="c988e-147">選取 [**取得更新**]</span><span class="sxs-lookup"><span data-stu-id="c988e-147">Select **Get updates**</span></span>

### <span data-ttu-id="c988e-148">掃描並安裝所有的 Windows 更新</span><span class="sxs-lookup"><span data-stu-id="c988e-148">Scan for and install all Windows Updates</span></span>
<span data-ttu-id="c988e-149">遷移至 Windows 10 專業版或 Windows 10 企業版後，可能會有可供您安裝的服務和功能更新。</span><span class="sxs-lookup"><span data-stu-id="c988e-149">After migrating to Windows 10 Professional or Windows 10 Enterprise, there may be servicing and feature updates available for you to install.</span></span> 

- <span data-ttu-id="c988e-150">移至 [**設定**  >  **更新 & 安全性**>，然後選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-150">Go to **Settings** > **Update & Security** > and then select **Check for updates**.</span></span>
- <span data-ttu-id="c988e-151">如果有任何更新，請安裝它們、重新開機，然後重複程式，直到您看到下列通知：</span><span class="sxs-lookup"><span data-stu-id="c988e-151">If there are any updates, install them, reboot, and then repeat the process until you see the following notification:</span></span>

> [!div class="mx-imgBorder"]
> ![Windows Update [您是最新的通知]](images/wustatus.png)


## <span data-ttu-id="c988e-153">商務用 OneDrive</span><span class="sxs-lookup"><span data-stu-id="c988e-153">OneDrive for Business</span></span>

<span data-ttu-id="c988e-154">使用 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> 商務用 OneDrive 在 </a> 您所有的工作裝置之間輕鬆共用工具、記錄及其他檔案。</span><span class="sxs-lookup"><span data-stu-id="c988e-154">Use <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> OneDrive for Business</a> to easily share tools, logs, and other files between all your work devices.</span></span>

- <span data-ttu-id="c988e-155">OneDrive 可讓您在膝上型電腦、Surface Hub 桌面與 Intune 管理的行動裝置之間共用您的工作檔案。</span><span class="sxs-lookup"><span data-stu-id="c988e-155">OneDrive enables you to share your work files between your laptops, Surface Hub Desktop, and your Intune-managed mobile devices.</span></span> <span data-ttu-id="c988e-156">您可以在任何裝置上編輯檔案，而且所有網路連接的裝置都會隨變更進行更新。</span><span class="sxs-lookup"><span data-stu-id="c988e-156">Files can be edited on any device, and all network connected devices will be updated with the changes.</span></span>

- <span data-ttu-id="c988e-157">考慮 Surface Hub SSD 的大小 (128GB) ，如果您在 Surface Hub 桌面裝置上設定 OneDrive，請確定預設設定是在您使用它們時，讓檔案保持線上並下載檔案。</span><span class="sxs-lookup"><span data-stu-id="c988e-157">Considering the size of the Surface Hub SSD (128GB), if you configure OneDrive on your Surface Hub Desktop device, make sure the default configuration is to keep the files online and download files as you use them.</span></span>

<span data-ttu-id="c988e-158">若要將 OneDrive 設定為只在需要時下載檔案，請設定 [檔案 **隨選** ] 設定，以 **在您使用時儲存空間和下載**檔案。</span><span class="sxs-lookup"><span data-stu-id="c988e-158">To configure OneDrive to download files only when needed, set the **Files On-Demand** setting to **Save space and download files as you use them**.</span></span> <span data-ttu-id="c988e-159">如需詳細資訊，請參閱 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> 在 Windows 中查詢及設定檔案的隨選狀態 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-159">For more information, see <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> Query and set Files On-Demand states in Windows</a>.</span></span>

![OneDrive 設定](images/onedrive.png)

> [!NOTE]
> <span data-ttu-id="c988e-161">您也可以重複這些步驟來設定個人 OneDrive，但請務必保留磁片磁碟機空間，並在需要時下載檔案。</span><span class="sxs-lookup"><span data-stu-id="c988e-161">You can also repeat these steps to configure a personal OneDrive but be sure to conserve drive space and only download files as you need them.</span></span>

## <span data-ttu-id="c988e-162">SharePoint 與團隊</span><span class="sxs-lookup"><span data-stu-id="c988e-162">SharePoint and Teams</span></span>

<span data-ttu-id="c988e-163">SharePoint 和團隊通道檔案也可以使用 OneDrive 同步處理引擎，在本機同步處理到您的桌面裝置，例如膝上型電腦和 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="c988e-163">SharePoint and Teams Channel files can also sync locally to your desktop devices, such as laptops and Surface Hubs, using the OneDrive sync engine.</span></span>

<span data-ttu-id="c988e-164">若要將內部公司檔案與 OneDrive 同步處理應用程式同步處理至您的本機磁片磁碟機：</span><span class="sxs-lookup"><span data-stu-id="c988e-164">To sync internal corporate files to your local drive with the OneDrive sync app:</span></span>

1. <span data-ttu-id="c988e-165">移至 SharePoint 網站，然後流覽至最上層檔目錄，尋找您想要從本機裝置查看或編輯的檔案。</span><span class="sxs-lookup"><span data-stu-id="c988e-165">Go to a SharePoint site and navigate to the top-level document directory for files that you are interested in viewing or editing from your local device.</span></span>

2. <span data-ttu-id="c988e-166">在 SharePoint 功能區頂端的 [ **同步** 處理] 按鈕上選取。</span><span class="sxs-lookup"><span data-stu-id="c988e-166">Select on the **Sync** button on the top of the SharePoint ribbon.</span></span>

3. <span data-ttu-id="c988e-167">在快顯功能表上選取 [**開啟\*\*\*\*此網站]，以嘗試開啟 Microsoft OneDrive**。</span><span class="sxs-lookup"><span data-stu-id="c988e-167">Select on **Open** on the popup **This site is trying to open Microsoft OneDrive**.</span></span>

4. <span data-ttu-id="c988e-168">選取工作列右下角的 [OneDrive] 圖示，以確認 SharePoint 檔案正在同步處理到您的本機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="c988e-168">Verify that the SharePoint files are synchronizing to your local drive by selecting on the OneDrive icon at the bottom right of the taskbar.</span></span>

5. <span data-ttu-id="c988e-169">確認設定設定為讓檔案保持線上，且只在您使用檔案時才下載檔案：</span><span class="sxs-lookup"><span data-stu-id="c988e-169">Verify the configuration is set to keep the files online and download the files only as you use them:</span></span>

    1. <span data-ttu-id="c988e-170">開啟 [檔案資源管理器]。</span><span class="sxs-lookup"><span data-stu-id="c988e-170">Open file explorer.</span></span>
    
    2. <span data-ttu-id="c988e-171">流覽至並以滑鼠右鍵按一下您的 SharePoint 名稱;例如 [ \*\*Contoso \ \<SharePoint Document Folder Name\> \*\*]。</span><span class="sxs-lookup"><span data-stu-id="c988e-171">Navigate to and right click your SharePoint name; for example, **Contoso \ \<SharePoint Document Folder Name\>**.</span></span>
    
    3. <span data-ttu-id="c988e-172">選取 [ **釋放空間**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-172">Select **Free up space**.</span></span>
    
    4. <span data-ttu-id="c988e-173">[狀態] 欄會顯示 [檔案] 和 [資料夾] 的狀態。</span><span class="sxs-lookup"><span data-stu-id="c988e-173">The Status column will display the status of files and folders.</span></span> <span data-ttu-id="c988e-174">如需詳細資訊，請參閱 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 使用 OneDrive 同步處理用戶端同步處理 SharePoint 檔案 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-174">For more information, see <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> Sync SharePoint files with the OneDrive sync client</a>.</span></span>
    
6. <span data-ttu-id="c988e-175">團隊通道檔案是儲存在 SharePoint 網站中，所有的 SharePoint 檔功能都相同，包括版本歷程記錄，以及同步處理到您的本機桌面裝置。</span><span class="sxs-lookup"><span data-stu-id="c988e-175">Teams Channel files are stored in SharePoint sites, with all of the same SharePoint document functionality, including version history and synchronizing to your local desktop devices.</span></span> <span data-ttu-id="c988e-176">若要同步處理團隊通道檔：</span><span class="sxs-lookup"><span data-stu-id="c988e-176">To sync Teams Channel files:</span></span>

    1. <span data-ttu-id="c988e-177">流覽至 [感 **興趣的小組] 頻道** ，然後選取頂端的 [檔案] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c988e-177">Navigate to the Teams Channel of interest and select the **Files** tab at the top.</span></span> <span data-ttu-id="c988e-178">然後選取 [**同步**處理]。檔案將會開始同步處理，並會顯示在\*\*桌上型電腦 \ Contoso \ \<name of the Teams Channel\> \*\*的檔案資源管理器中。</span><span class="sxs-lookup"><span data-stu-id="c988e-178">Then select **Sync**. The files will start synchronizing and will be visible in File Explorer at **Desktop \ Contoso \ \<name of the Teams Channel\>**.</span></span>
    
    2. <span data-ttu-id="c988e-179">使用您用來同步處理 SharePoint 網站的相同程式，將檔案保留在雲端，並只在使用時進行下載，只要在 [團隊頻道名稱] 上按一下並按住或以滑鼠右鍵按一下，然後選取 [ **釋放空間**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-179">Use the same procedure that you used for synchronizing SharePoint sites to keep the files in the cloud and only download them when you use them, by tap and hold or right-click in File Explorer on the Teams Channel name, and then selecting **Free up space**.</span></span>

## <span data-ttu-id="c988e-180">Surface Hub 手寫筆設定</span><span class="sxs-lookup"><span data-stu-id="c988e-180">Surface Hub pen settings</span></span>

**<span data-ttu-id="c988e-181">將藍牙 Surface 中樞觸筆配對</span><span class="sxs-lookup"><span data-stu-id="c988e-181">Pair the Bluetooth Surface Hub Pen</span></span>**

<span data-ttu-id="c988e-182">配對手寫筆以將畫筆固件保持在最新狀態，在 [藍牙裝置設定] 頁面或 Surface 應用程式中，設定繪圖筆的快捷方式，並取得電池計量資訊：</span><span class="sxs-lookup"><span data-stu-id="c988e-182">Pair the pen to keep the pen firmware up to date, set the pen shortcuts, and get battery charge information on the Bluetooth device settings page, or in the Surface app:</span></span>

1. <span data-ttu-id="c988e-183">選取 [**啟動**  >  **設定**  >  **裝置**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-183">Select **Start** > **Settings** > **Devices**.</span></span>

2. <span data-ttu-id="c988e-184">選取 [ **新增藍牙] 或 [其他裝置**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-184">Select **Add Bluetooth or other device**.</span></span>

3. <span data-ttu-id="c988e-185">選擇 [ **藍牙**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-185">Choose **Bluetooth**.</span></span>

4. <span data-ttu-id="c988e-186">移除畫筆尾部按鈕，然後搖動以斷開電池連線。</span><span class="sxs-lookup"><span data-stu-id="c988e-186">Remove the pen tail button and shake to disconnect the battery connection.</span></span>

5. <span data-ttu-id="c988e-187">再次將 cap 放回，然後按住 cap，直到配對指示燈閃爍為止。</span><span class="sxs-lookup"><span data-stu-id="c988e-187">Put the cap back on and press and hold the cap until the pairing LED flashes.</span></span>

6. <span data-ttu-id="c988e-188">在 Surface Hub 藍牙設定中，選擇 [ **Surface hub 2 筆**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-188">On the Surface Hub Bluetooth settings, choose **Surface Hub 2 Pen**.</span></span>

7. <span data-ttu-id="c988e-189">完成配對操作。</span><span class="sxs-lookup"><span data-stu-id="c988e-189">Complete the pairing operation.</span></span> 

8. <span data-ttu-id="c988e-190">如果配對失敗，您可以嘗試再次配對筆。</span><span class="sxs-lookup"><span data-stu-id="c988e-190">If the pairing is not successful, you can attempt to pair the pen again.</span></span> <span data-ttu-id="c988e-191">如果仍無法解決問題，您可以在白板應用程式中驗證手寫筆是否正常運作，以查看電池是否已充電。</span><span class="sxs-lookup"><span data-stu-id="c988e-191">If that doesn't work, you can test to see if the battery is charged by verifying the pen works in the Whiteboard application.</span></span> <span data-ttu-id="c988e-192">如果不是，請更換電池，然後再次嘗試配對筆。</span><span class="sxs-lookup"><span data-stu-id="c988e-192">If not, then replace the battery and then try to pair the pen again.</span></span> <span data-ttu-id="c988e-193">如有需要，請重新開機裝置，然後再試一次。</span><span class="sxs-lookup"><span data-stu-id="c988e-193">If necessary, restart the device and then try again.</span></span>

<span data-ttu-id="c988e-194">**設定畫筆快速鍵** Surface Hub 筆有一個快速鍵按鈕，有時稱為「箭尾按一下」。</span><span class="sxs-lookup"><span data-stu-id="c988e-194">**Set pen shortcuts** The Surface Hub pen has a shortcut button sometimes referred to as a "tail click".</span></span> <span data-ttu-id="c988e-195">[設定快速鍵] 會要求您先對筆進行配對，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="c988e-195">Configuring shortcuts requires you to first pair the pen, as described earlier.</span></span>

1. <span data-ttu-id="c988e-196">搜尋手寫筆，然後選取 [ **畫筆] & Windows Ink 設定**。</span><span class="sxs-lookup"><span data-stu-id="c988e-196">Search for Pen and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="c988e-197">在靠近頁面底部的位置，選取會開啟此對話方塊的 [筆快速鍵]，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c988e-197">Near the bottom of the page, select Pen shortcuts which opens the dialog box, shown here:</span></span>

   ![畫筆快速鍵](images/sh2-pen-shortcuts.png)

## <span data-ttu-id="c988e-199">相機配置</span><span class="sxs-lookup"><span data-stu-id="c988e-199">Camera configuration</span></span>

<span data-ttu-id="c988e-200">您可以將相機安裝在裝置的頂端或任一側。</span><span class="sxs-lookup"><span data-stu-id="c988e-200">You can mount the camera on the top or on either side of the device.</span></span> <span data-ttu-id="c988e-201">如果您是將中樞與桌面支架（而非車）配合使用，或者與中樞接近，請將相機安裝在位置，以優化相機角度。</span><span class="sxs-lookup"><span data-stu-id="c988e-201">Mount the camera in a position to optimize the camera angle if you are using the Hub with a desktop stand instead of a cart, or are in close proximity to the Hub.</span></span> <span data-ttu-id="c988e-202">相機不會自動旋轉，因此您必須使用2mm 十六進位金鑰來手動旋轉相機。</span><span class="sxs-lookup"><span data-stu-id="c988e-202">The camera does not auto-rotate, so you need to have a 2mm hex key to manually rotate the camera.</span></span> 

<span data-ttu-id="c988e-203">如需如何將相機側邊裝載並手動旋轉相機的詳細資訊，請參閱 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2 的相機鏡頭方向 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-203">For more information on how to side-mount the camera and rotate the camera manually, see <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S camera lens orientation</a>.</span></span>

## <span data-ttu-id="c988e-204">Windows Hello 設定</span><span class="sxs-lookup"><span data-stu-id="c988e-204">Windows Hello configuration</span></span>

<span data-ttu-id="c988e-205">執行 Windows 10 企業版的 Surface Hub 2-2 可提供完整的 Win32 桌面應用程式，以及生物識別 Windows Hello 選項。</span><span class="sxs-lookup"><span data-stu-id="c988e-205">Surface Hub 2S running Windows 10 Enterprise allows the full suite of Win32 desktop applications as well as biometric Windows Hello options.</span></span> <span data-ttu-id="c988e-206">Surface Hub 2 指紋辨識器配件可以插入裝置上的任何 USB 埠。</span><span class="sxs-lookup"><span data-stu-id="c988e-206">The Surface Hub 2 Fingerprint Reader accessory can be plugged into any USB-C port on the device.</span></span> 

<span data-ttu-id="c988e-207">若要定購 Surface Hub 2 指紋辨識器，或查看技術規格，請參閱 (surface-hub-2-essential-add-ons.md "target =" _blank ">適用于 Surface Hub 2 的 Windows 10 專業版和 Enterprise 的附加元件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-207">To order a Surface Hub 2 Fingerprint Reader or view technical specs, see (surface-hub-2-essential-add-ons.md" target="_blank">Essential add-ons for Windows 10 Pro and Enterprise on Surface Hub 2 </a>.</span></span> 

<span data-ttu-id="c988e-208">插入指紋閱讀程式後，請選取 [**啟動**  >  **設定**  >  **帳戶**] 登  >  **入選項**  >  **Windows Hello 指紋**以註冊您的指紋。</span><span class="sxs-lookup"><span data-stu-id="c988e-208">After inserting the fingerprint reader, select **Start** > **Settings** > **Accounts** > **Sign-in options** > **Windows Hello Fingerprint** to enroll your fingerprint.</span></span>

<span data-ttu-id="c988e-209">使用 Windows Hello 認證裝置進行面孔認可。</span><span class="sxs-lookup"><span data-stu-id="c988e-209">Use a Windows Hello certified device for face recognition.</span></span> <span data-ttu-id="c988e-210">Surface Hub 2 版攝像頭不支援 Windows Hello 面孔認可。</span><span class="sxs-lookup"><span data-stu-id="c988e-210">The Surface Hub 2S camera does not support Windows Hello face recognition.</span></span>

## <span data-ttu-id="c988e-211">在工作列上啟用鎖定畫面快捷方式圖示</span><span class="sxs-lookup"><span data-stu-id="c988e-211">Enable a Lock Screen shortcut icon on the taskbar</span></span>

<span data-ttu-id="c988e-212">若要將圖示新增到工作列，以啟用單一觸控螢幕鎖定，類似 Windows-L 鍵盤快速鍵：</span><span class="sxs-lookup"><span data-stu-id="c988e-212">To add an icon to the taskbar that enables one-touch screen lock similar to the Windows-L keyboard shortcut:</span></span> 

1.  <span data-ttu-id="c988e-213">在桌面上按一下並按住或按一下滑鼠右鍵，然後選取 [**新增**  >  **快速鍵**  >  **流覽**  >  **桌面**] [  >  **OK**  >  **下一步**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-213">Tap and hold or right-click on the desktop, select **New** > **Shortcut** > **Browse** > **Desktop** > **OK** > **Next**.</span></span>

1.  <span data-ttu-id="c988e-214">提供快捷方式的名稱，例如 **鎖定我的電腦**，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="c988e-214">Provide a name for the shortcut such as **Lock my PC**, and then select **Finish**.</span></span>

1.  <span data-ttu-id="c988e-215">以滑鼠右鍵按一下或輕觸並按住桌面上新建立的快捷方式，然後選取 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-215">Right-click or tap and hold the newly created shortcut on the desktop, and select **Properties**.</span></span> <span data-ttu-id="c988e-216">在 [ **快捷方式** ] 索引標籤上的 [ **目標** ] 欄位中，輸入下列內容： **Rundll32.exe User32.dll、LockWorkStation**</span><span class="sxs-lookup"><span data-stu-id="c988e-216">On the **Shortcut** tab, enter the following in the **Target** field: **Rundll32.exe User32.dll,LockWorkStation**</span></span>

1.  <span data-ttu-id="c988e-217">選取 [ **變更] 圖示** 按鈕，然後流覽至 [ **C:\Windows\System32\imageres.dll** ]，然後選取要使用的圖示。</span><span class="sxs-lookup"><span data-stu-id="c988e-217">Select the **Change Icon** button and browse to **C:\Windows\System32\imageres.dll** and select an icon to use.</span></span> 

    <span data-ttu-id="c988e-218">請參閱下列範例：</span><span class="sxs-lookup"><span data-stu-id="c988e-218">See the following example:</span></span>

    ![選擇圖示](images/lock.png)
    
1.  <span data-ttu-id="c988e-220">選取 **[確定]** 儲存快捷方式。</span><span class="sxs-lookup"><span data-stu-id="c988e-220">Select **OK** to save the shortcut.</span></span>

1.  <span data-ttu-id="c988e-221">以滑鼠右鍵按一下或輕觸並按住快速鍵，然後選取 [ **釘選到工作列**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-221">Right-click or tap and hold the shortcut and select **Pin to taskbar**.</span></span>

1. <span data-ttu-id="c988e-222">將鎖定快捷方式釘選到工作列之後，您就可以將它從桌上型電腦中刪除。</span><span class="sxs-lookup"><span data-stu-id="c988e-222">After you have pinned the lock shortcut to the taskbar, you can delete it from the desktop.</span></span>

## <span data-ttu-id="c988e-223">應用程式</span><span class="sxs-lookup"><span data-stu-id="c988e-223">Applications</span></span>


### <span data-ttu-id="c988e-224">Microsoft Whiteboard</span><span class="sxs-lookup"><span data-stu-id="c988e-224">Microsoft Whiteboard</span></span>

<span data-ttu-id="c988e-225">若要安裝 Microsoft 白板：</span><span class="sxs-lookup"><span data-stu-id="c988e-225">To install the Microsoft Whiteboard:</span></span>

 - <span data-ttu-id="c988e-226">選取工作列右下角的 [ **Windows Ink 工作區** ] 圖示，然後下載 [ **白板**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-226">Select the **Windows Ink Workspace** icon on the lower right of the taskbar and download **Whiteboard**.</span></span>
 
   ![筆跡工作區](images/ink.png) 

<span data-ttu-id="c988e-228">或者，您可以從 Microsoft 網上商店安裝白板：</span><span class="sxs-lookup"><span data-stu-id="c988e-228">Alternatively, you can install Whiteboard from the Microsoft Store:</span></span>

1. <span data-ttu-id="c988e-229">開啟 Microsoft Store app 並搜尋 **白板**。</span><span class="sxs-lookup"><span data-stu-id="c988e-229">Open Microsoft Store app and search for **Whiteboard**.</span></span>

2. <span data-ttu-id="c988e-230">選擇 [ **不用] 感謝您** 在裝置上登入及使用。</span><span class="sxs-lookup"><span data-stu-id="c988e-230">Choose **No thanks** to sign in and use across devices.</span></span>

3. <span data-ttu-id="c988e-231">將白板釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="c988e-231">Pin Whiteboard to the taskbar.</span></span>

### <span data-ttu-id="c988e-232">Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="c988e-232">Surface app</span></span>

1. <span data-ttu-id="c988e-233">在 Microsoft Store 中，搜尋 **Surface**。</span><span class="sxs-lookup"><span data-stu-id="c988e-233">In the Microsoft Store, search for **Surface**.</span></span>

2. <span data-ttu-id="c988e-234">將 [ **在篩選上可用** ] 設定為 [ **所有裝置**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-234">Set the **Available on** filter to **All devices**.</span></span>

3. <span data-ttu-id="c988e-235">安裝 **Surface** app。</span><span class="sxs-lookup"><span data-stu-id="c988e-235">Install the **Surface** app.</span></span> <span data-ttu-id="c988e-236">這應該是第一個列出的 app。</span><span class="sxs-lookup"><span data-stu-id="c988e-236">This should be the first app listed.</span></span> <span data-ttu-id="c988e-237">您可能需要將您的 MSA 與書店建立關聯，才能安裝 app。</span><span class="sxs-lookup"><span data-stu-id="c988e-237">You might need to associate your MSA to the Store in order to install the app.</span></span>

4. <span data-ttu-id="c988e-238">將 **表面** app 釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="c988e-238">Pin the **Surface** app to taskbar.</span></span>

### <span data-ttu-id="c988e-239">剪取與繪圖</span><span class="sxs-lookup"><span data-stu-id="c988e-239">Snip & Sketch</span></span>

1. <span data-ttu-id="c988e-240">開啟 [ **剪取 & 草圖** ] app，然後將它釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="c988e-240">Open the **Snip & Sketch** app and pin it to the taskbar.</span></span>

2. <span data-ttu-id="c988e-241">選取右上角的省略號，然後選取 [ **設定**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-241">Select the ellipsis in the upper right corner and then select **Settings**.</span></span>

3. <span data-ttu-id="c988e-242">在 [ **設定**] 中，開啟 [ **自動複製到剪貼**簿]、[ **儲存截圖**]，以及 **多個 windows** (選擇性) 。</span><span class="sxs-lookup"><span data-stu-id="c988e-242">In **Settings**, turn on **Auto copy to clipboard**, **Save snips**, and **Multiple windows** (optional).</span></span>

### <span data-ttu-id="c988e-243">Microsoft Office</span><span class="sxs-lookup"><span data-stu-id="c988e-243">Microsoft Office</span></span>

1. <span data-ttu-id="c988e-244">開啟 <a href="https://portal.office.com/account#installs" target="_blank"> Office 入口網站 </a> ，並安裝您想要的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c988e-244">Open the <a href="https://portal.office.com/account#installs" target="_blank"> Office Portal</a> and install your desired applications.</span></span>

2. <span data-ttu-id="c988e-245">將所需的 Office 應用程式釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="c988e-245">Pin desired Office applications to the taskbar.</span></span>

3. <span data-ttu-id="c988e-246">如果已安裝 Outlook，請務必將 Outlook OST 設定為只儲存最後兩周的快取。</span><span class="sxs-lookup"><span data-stu-id="c988e-246">If Outlook is installed, be sure to set the Outlook OST to only save last two weeks cache.</span></span> <span data-ttu-id="c988e-247">這將大大減少磁片使用量和設定時間。</span><span class="sxs-lookup"><span data-stu-id="c988e-247">This will vastly reduce disk usage and setup time.</span></span>

    - <span data-ttu-id="c988e-248">選取 **[** 檔案  >  **帳戶設定**]，然後選取您的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c988e-248">Select **File** > **Account Settings** and select your account.</span></span>
    
    - <span data-ttu-id="c988e-249">選取 [ **變更** ]，然後將 [使用快取 **Exchange 模式]** 的滑杆設定為14天。</span><span class="sxs-lookup"><span data-stu-id="c988e-249">Select **Change** and set the slider for **Use Cached Exchange Mode** to 14 days.</span></span>

### <span data-ttu-id="c988e-250">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c988e-250">Microsoft Teams</span></span>

1. <span data-ttu-id="c988e-251">下載並安裝 <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft 團隊 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-251">Download and install <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a>.</span></span>

2. <span data-ttu-id="c988e-252">將設定設定為自動啟動應用程式 (選用的) 。</span><span class="sxs-lookup"><span data-stu-id="c988e-252">Configure settings to Auto-start application (optional).</span></span>

3. <span data-ttu-id="c988e-253">將團隊釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="c988e-253">Pin Teams to the taskbar.</span></span>

4. <span data-ttu-id="c988e-254">請考慮減少裝置上的小組通知，避免干擾 (選用的) 。</span><span class="sxs-lookup"><span data-stu-id="c988e-254">Consider reducing Teams notifications on the device to avoid distractions (optional).</span></span>

   ![團隊通知](images/teams.png)

### <span data-ttu-id="c988e-256">Connect app</span><span class="sxs-lookup"><span data-stu-id="c988e-256">Connect app</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c988e-257">在 Windows 10 版本2004及更新版本中，預設不會安裝使用 Miracast 進行無線投影的連線應用程式，但可將它做為選用的功能。</span><span class="sxs-lookup"><span data-stu-id="c988e-257">In Windows 10, version 2004 and later, the Connect app for wireless projection using Miracast is not installed by default, but is available as an optional feature.</span></span> <span data-ttu-id="c988e-258">如果您已安裝 (或更新為) Windows 版本2004或更新版本，您可能會在 [設定] 中的 [投影至此電腦畫面] 畫面上看到下列資訊：</span><span class="sxs-lookup"><span data-stu-id="c988e-258">If you have installed (or updated to) Windows version 2004 or later, you may see the following on the Projecting to this PC screen in settings:</span></span>

![投影到這台電腦](images/sh2-project.png) 


1. <span data-ttu-id="c988e-260">若要從 [投影到此電腦] 設定頁面安裝應用程式，請選取 [**選用功能**]  >  **新增功能**，然後安裝 [**無線顯示**] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c988e-260">To install the app from the “Projecting to this PC” settings page, select **Optional features** > **Add a feature** and then install the **Wireless Display** app.</span></span>

2. <span data-ttu-id="c988e-261">在 **某些 Windows 和 Android 裝置下，當您說到 [確定] 時，可以將它投影到這台電腦**，請選擇：</span><span class="sxs-lookup"><span data-stu-id="c988e-261">Under **Some Windows and Android devices can project to this PC when you say it's OK**, choose:</span></span>

    - <span data-ttu-id="c988e-262">如果裝置不在商業網路上，就**可以使用所有位置**。</span><span class="sxs-lookup"><span data-stu-id="c988e-262">**Available everywhere** if the device is not on a corporate network.</span></span>
    - <span data-ttu-id="c988e-263">否則，請選擇 [ **所有位置都能在安全網路上使用**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-263">Otherwise, choose **Available everywhere on secure networks**.</span></span>
    
3. <span data-ttu-id="c988e-264">在 [ **要求 project to 此電腦**] 底下，選擇 [ **僅限第一次**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-264">Under **Ask to project to this PC**, choose **First time only**.</span></span>

4. <span data-ttu-id="c988e-265">在 [ **需要 PIN 以進行配對**] 下，選擇 [ **永不**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-265">Under **Require PIN for pairing**, choose **Never**.</span></span>

5. <span data-ttu-id="c988e-266">若要啟動 app 並將它釘選到工作列，請搜尋 **[連線]**。</span><span class="sxs-lookup"><span data-stu-id="c988e-266">To then launch the app and pin it to the taskbar, search for **Connect**.</span></span>

6. <span data-ttu-id="c988e-267">開啟 app。</span><span class="sxs-lookup"><span data-stu-id="c988e-267">Open the app.</span></span> <span data-ttu-id="c988e-268">在 app 開啟時，以滑鼠右鍵按一下工作列上的 [連接] 應用程式圖示，然後選取 [ **釘選到工作列**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-268">While the app is open, right-click on the Connect app icon on the taskbar, and select **pin to taskbar**.</span></span>

7. <span data-ttu-id="c988e-269">然後關閉 [連線] app。</span><span class="sxs-lookup"><span data-stu-id="c988e-269">Then close the Connect app.</span></span> <span data-ttu-id="c988e-270">除非 app 至少執行過一次，否則**此電腦的 Project**可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="c988e-270">**Project to this PC** might not work unless the app has been run at least once.</span></span>

<span data-ttu-id="c988e-271">在公司網路不使用時的建議配置：</span><span class="sxs-lookup"><span data-stu-id="c988e-271">Recommended configuration when not on the corporate network:</span></span>

![在家中的設定](images/project1.png)

<span data-ttu-id="c988e-273">公司網路上的建議配置：</span><span class="sxs-lookup"><span data-stu-id="c988e-273">Recommended configuration on the corporate network:</span></span>

![工作中的設定](images/project2.png)

### <span data-ttu-id="c988e-275">您的手機</span><span class="sxs-lookup"><span data-stu-id="c988e-275">Your Phone</span></span>

<span data-ttu-id="c988e-276">**您的電話**app 預設會安裝在 Windows 10 上。</span><span class="sxs-lookup"><span data-stu-id="c988e-276">The **Your Phone** app is installed by default on Windows 10.</span></span> <span data-ttu-id="c988e-277">如果不存在，您也可以從 Windows 市集中安裝它。</span><span class="sxs-lookup"><span data-stu-id="c988e-277">If it is not present, you can also install it from the Windows Store.</span></span>

<span data-ttu-id="c988e-278">如需設定 app 的相關資訊，請參閱 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 如何在 Windows 10 設定您的電話，以及如何在您的電腦與手機之間同步處理資料 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-278">For information about setting up the app, see <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> How to set up Your Phone on Windows 10 and sync data between your PC and phone</a>.</span></span> <span data-ttu-id="c988e-279">另請參閱 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 如何修正您在 Windows 10 上的手機應用程式常見問題 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-279">Also see <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> How to fix common problems with Your Phone app on Windows 10</a>.</span></span>

###  <span data-ttu-id="c988e-280">別致區域</span><span class="sxs-lookup"><span data-stu-id="c988e-280">Fancy Zones</span></span>


<span data-ttu-id="c988e-281">[**別致區域**] 是 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> GitHub 上稱為 PowerToys 的工具集合的一部分 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-281">**Fancy Zones** is part of a collection of tools called <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys</a> on GitHub..</span></span> <span data-ttu-id="c988e-282">在 Surface Hub 2，您可以在顯示 ( 「zone」」 ) 上定義固定的版面配置，然後選取將在每個區域中執行的 app，這是一種很好的方式。</span><span class="sxs-lookup"><span data-stu-id="c988e-282">It is a great way to utilize the screen real-estate on a Surface Hub 2 by giving you the ability to define fixed layouts on your display (“zones”), and then select which app will then run in each zone.</span></span> 


<span data-ttu-id="c988e-283">[PowerToys wiki](https://github.com/microsoft/PowerToys/wiki)提供如何使用及自訂每個工具的指示，包括[FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)。</span><span class="sxs-lookup"><span data-stu-id="c988e-283">The [PowerToys wiki](https://github.com/microsoft/PowerToys/wiki) has instructions for how to use and customize each tool, including [FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview).</span></span> <span data-ttu-id="c988e-284">在高層次上（在安裝 PowerToys 之後），您可以選取或建立自訂的版面配置，然後按住 shift 鍵，然後拖曳或使用鍵盤鍵，將執行中的 app 移至特定區域。</span><span class="sxs-lookup"><span data-stu-id="c988e-284">At a high level – after installing PowerToys, you can select or create a custom layout, and then hold the shift key down and drag or use keyboard keys to move a running app into specific zones.</span></span> <span data-ttu-id="c988e-285">使用藍牙或 USB 鍵盤和滑鼠將協助您解決此情況，或者您可以使用螢幕上的觸控式鍵盤和觸控板。</span><span class="sxs-lookup"><span data-stu-id="c988e-285">Using a Bluetooth or USB keyboard and mouse will help with this, or you can use the on-screen touch keyboard and touchpad.</span></span>

**<span data-ttu-id="c988e-286">Power 玩具秘訣</span><span class="sxs-lookup"><span data-stu-id="c988e-286">Power toys tips</span></span>**
- <span data-ttu-id="c988e-287">若要在 GitHub 上接收 PowerToys 發行更新的電子郵件通知，請按一下 [頁面](https://github.com/microsoft/PowerToys/releases)頂端的 [註冊] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c988e-287">To receive email notifications of PowerToys release updates on GitHub, click the “sign-up” button at the top of the [page](https://github.com/microsoft/PowerToys/releases).</span></span>
- <span data-ttu-id="c988e-288">安裝 PowerToys 之後，您就可以透過將 PowerToys 設定 [ **自動下載更新** ] 設定為 [開啟]，來接收 Windows 通知和/或下載並安裝最新的更新。</span><span class="sxs-lookup"><span data-stu-id="c988e-288">Once PowerToys is installed, you can receive Windows notifications and/or download and install the latest updates by configuring the PowerToys settings **Download updates automatically** to on.</span></span>
- <span data-ttu-id="c988e-289">若要移至 [PowerToys 設定]，請在工作列上選取 [向上 carat] 執行的 **應用程式** ，然後以滑鼠右鍵按一下或按住 PowerToys 圖示，直到功能表出現為止。</span><span class="sxs-lookup"><span data-stu-id="c988e-289">To get to the PowerToys settings, select the up carat **Running apps** on the taskbar, and then right click or press and hold the PowerToys icon until the menu appears.</span></span> <span data-ttu-id="c988e-290">選取 [設定]。</span><span class="sxs-lookup"><span data-stu-id="c988e-290">Select “Settings”.</span></span>
- <span data-ttu-id="c988e-291">在 [PowerToys 設定] 頁面底部，將 [ **自動下載更新** ] 設為 [開啟]。</span><span class="sxs-lookup"><span data-stu-id="c988e-291">At the bottom of the PowerToys settings page, turn **Download updates automatically** to on.</span></span>
- <span data-ttu-id="c988e-292">發佈更新時，系統會顯示 Windows 通知，提供何時安裝更新的選項。</span><span class="sxs-lookup"><span data-stu-id="c988e-292">When an update has been released, a Windows notification will appear giving you the option of when to install the update.</span></span>


### <span data-ttu-id="c988e-293">Edge Chromium 瀏覽器</span><span class="sxs-lookup"><span data-stu-id="c988e-293">Edge Chromium browser</span></span>

<span data-ttu-id="c988e-294">下載並安裝新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 瀏覽器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="c988e-294">Download and install the new <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank">Edge Chromium browser</a>.</span></span>


### <span data-ttu-id="c988e-295">Surface Hub 硬體診斷工具</span><span class="sxs-lookup"><span data-stu-id="c988e-295">Surface Hub Hardware Diagnostic tool</span></span>

<span data-ttu-id="c988e-296">您 <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> </a> 可以從 Microsoft 網上商店免費取得 Surface Hub 硬體診斷工具。</span><span class="sxs-lookup"><span data-stu-id="c988e-296">The <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub Hardware Diagnostic tool</a> available for free from the Microsoft Store.</span></span> <span data-ttu-id="c988e-297">此工具的設計目的是協助您確保 Surface Hub 發揮最佳效果。</span><span class="sxs-lookup"><span data-stu-id="c988e-297">The tool is designed to help you make sure your Surface Hub is performing at its best.</span></span> <span data-ttu-id="c988e-298">它包含可判斷您的固件是否為最新且已正確設定的測試。</span><span class="sxs-lookup"><span data-stu-id="c988e-298">It contains tests to determine if your firmware is up to date and configured correctly.</span></span> <span data-ttu-id="c988e-299">互動式測試可讓您確認必要的功能是否如預期運作。</span><span class="sxs-lookup"><span data-stu-id="c988e-299">Interactive tests allow you to confirm essential functionality is working as expected.</span></span> <span data-ttu-id="c988e-300">如果遇到問題，可以將結果儲存起來，與 Surface Hub 支援小組分享。</span><span class="sxs-lookup"><span data-stu-id="c988e-300">If problems are encountered, results can be saved and shared with the Surface Hub Support Team.</span></span> <span data-ttu-id="c988e-301">按一下連結以從 Microsoft 網上商店安裝，然後將應用程式釘選到工作列。</span><span class="sxs-lookup"><span data-stu-id="c988e-301">Click on the link to install it from the Microsoft Store, and then pin the application to your taskbar.</span></span>

## <span data-ttu-id="c988e-302">其他設定</span><span class="sxs-lookup"><span data-stu-id="c988e-302">Additional settings</span></span>

### <span data-ttu-id="c988e-303">選取以啟動白板的 [畫筆尾部]</span><span class="sxs-lookup"><span data-stu-id="c988e-303">Pen tail select to launch Whiteboard</span></span>

1. <span data-ttu-id="c988e-304">搜尋 **手寫筆** ，然後選取 [ **畫筆] & Windows Ink 設定**。</span><span class="sxs-lookup"><span data-stu-id="c988e-304">Search for **Pen** and select **Pen & Windows Ink settings**.</span></span>

2. <span data-ttu-id="c988e-305">在靠近頁面底部的 [ **畫筆快速鍵** ] 底下，將 [ **選取一次** 至 **Microsoft 白板**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-305">Near the bottom of the page, under **Pen shortcuts** set **Select once** to **Microsoft Whiteboard**.</span></span> 

### <span data-ttu-id="c988e-306">電源管理</span><span class="sxs-lookup"><span data-stu-id="c988e-306">Power management</span></span>

<span data-ttu-id="c988e-307">有數種電源設定可讓您在 Surface Hub 2 上使用 Windows 10 專業版或企業版獲得最佳體驗。</span><span class="sxs-lookup"><span data-stu-id="c988e-307">There are several power settings available to get the best experience using Windows 10 Pro or Enterprise on Surface Hub 2.</span></span> <span data-ttu-id="c988e-308">這包括螢幕和電腦的超時，以及它們如何與內建的人類目前狀態偵測進行互動 (Doppler) 、螢幕保護裝置程式及密碼保護，然後如果您想要如何針對膝上型電腦/電腦版使用者進行群組原則電源設定。</span><span class="sxs-lookup"><span data-stu-id="c988e-308">This includes screen and pc timeouts and how they interact with the built-in human presence detection (Doppler), the screen saver and password protection, and then if appropriate how to by-pass group policy power settings intended for laptop / desktop users.</span></span>

<span data-ttu-id="c988e-309">在 Surface Hub 上的 Windows 10 專業版或企業版中，您可以透過觸控、滑鼠和鍵盤動作，以及內建的人力資源偵測 (Doppler) 來保持畫面進入睡眠狀態。</span><span class="sxs-lookup"><span data-stu-id="c988e-309">Windows 10 Pro or Enterprise on Surface Hub 2 keeps the screen from going to sleep by touch, mouse, and keyboard actions, as well as the built-in human occupancy detection (Doppler).</span></span> <span data-ttu-id="c988e-310">預設會啟用 [人力資源] 偵測，但如果需要，您可以在 [Surface UEFI 組態工具] 中切換 [裝置] 選項，或建立並套用較新的 UEFI 設定套件，以將它停在 UEFI 中。</span><span class="sxs-lookup"><span data-stu-id="c988e-310">Human occupancy detection is enabled by default, but if desired it can be disabled in UEFI by toggling the device option in the Surface UEFI Configurator tool either as part of the initial migration, or by building and applying a later UEFI configuration package.</span></span> 

**<span data-ttu-id="c988e-311">電源管理：螢幕和電腦睡眠設定</span><span class="sxs-lookup"><span data-stu-id="c988e-311">Power Management: Screen and PC sleep settings</span></span>**

1. <span data-ttu-id="c988e-312">選取 [**開始**  >  **設定**] [  >  **系統**  >  **電源 & 睡眠**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-312">Select **Start** > **Settings** > **System** > **Power & sleep**.</span></span>

2. <span data-ttu-id="c988e-313">設定 [電源模式] 滑杆以 **獲得最佳效能**。</span><span class="sxs-lookup"><span data-stu-id="c988e-313">Set the power mode slider to **Best performance**.</span></span>

3. <span data-ttu-id="c988e-314">您也可以將畫面和睡眠值設定為您的喜好設定，同時也會在偵測到移動時，在 Doppler 的目前狀態偵測中喚醒。</span><span class="sxs-lookup"><span data-stu-id="c988e-314">Configure screen and sleep values to your preference while also accounting for Doppler presence detection that wakes up the device when movement is detected.</span></span> <span data-ttu-id="c988e-315">因此，建議您在**4 小時**後將畫面設定為**在2小時後**關閉，並將電腦關閉，以進行最佳做法。</span><span class="sxs-lookup"><span data-stu-id="c988e-315">Accordingly, as a best practice, it's recommended to set Screen to **Turn off after 2 hours** and the PC to **Turn off after 4 hours.**</span></span>

**<span data-ttu-id="c988e-316">電源管理：螢幕保護裝置程式</span><span class="sxs-lookup"><span data-stu-id="c988e-316">Power Management: Screen saver</span></span>**

1. <span data-ttu-id="c988e-317">搜尋 **鎖定畫面** 並開啟 **鎖定畫面設定**。</span><span class="sxs-lookup"><span data-stu-id="c988e-317">Search for **Lock Screen** and open **Lock screen settings**.</span></span>

2. <span data-ttu-id="c988e-318">將 **螢幕超時設定** 和 **螢幕保護裝置程式設定** 設定為您的喜好設定。</span><span class="sxs-lookup"><span data-stu-id="c988e-318">Configure **Screen timeout settings** and **Screen saver settings** to your preference.</span></span> <span data-ttu-id="c988e-319">建議的預設值為：</span><span class="sxs-lookup"><span data-stu-id="c988e-319">Recommended default values are:</span></span>

   - <span data-ttu-id="c988e-320">[螢幕保護裝置程式] 可 (無]) 或您選擇的螢幕保護裝置程式。</span><span class="sxs-lookup"><span data-stu-id="c988e-320">Screen saver to (None) or a screen saver of your choice.</span></span>
   - <span data-ttu-id="c988e-321">等待時間15分鐘。</span><span class="sxs-lookup"><span data-stu-id="c988e-321">Wait time to 15 minutes.</span></span>
   - <span data-ttu-id="c988e-322">在 [繼續] 上，顯示 [登入] 畫面。</span><span class="sxs-lookup"><span data-stu-id="c988e-322">On resume, display logon screen.</span></span>


**<span data-ttu-id="c988e-323">電源管理：群組原則</span><span class="sxs-lookup"><span data-stu-id="c988e-323">Power Management: Group Policy</span></span>**

<span data-ttu-id="c988e-324">在執行下列程式前，請向您的 IT 部門確認，以核准從全域電源管理原則中排除 Surface Hub 2-2 裝置。</span><span class="sxs-lookup"><span data-stu-id="c988e-324">Before performing the following procedure, check with your IT department for approval to exclude a Surface Hub 2S device from global power management policy.</span></span> <span data-ttu-id="c988e-325">某些電源管理設定可以停用目前狀態偵測函數。</span><span class="sxs-lookup"><span data-stu-id="c988e-325">Some power management settings can disable the presence detection function.</span></span>

1. <span data-ttu-id="c988e-326">搜尋 **軟體中心** 並將它開啟。</span><span class="sxs-lookup"><span data-stu-id="c988e-326">Search for **Software Center** and open it.</span></span>

2. <span data-ttu-id="c988e-327">選取 [ **選項**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-327">Select **Options**.</span></span>

3. <span data-ttu-id="c988e-328">展開 [ **電源管理**  ]，然後選取 [ **不要將 IT 部門的電源設定套用至此電腦**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-328">Expand the **Power management**  and select **Do not apply power settings from my IT department to this computer**.</span></span>

   ![軟體設定](images/soft-cntr.png)

### <span data-ttu-id="c988e-330">儲存空間感知器</span><span class="sxs-lookup"><span data-stu-id="c988e-330">Storage Sense</span></span>

<span data-ttu-id="c988e-331">Surface Hub 2 在本機儲存空間中有一個 128GB SSD，所以在正常使用期間，必須考慮使用儲存空間儲存量值。</span><span class="sxs-lookup"><span data-stu-id="c988e-331">The Surface Hub 2 has a 128GB SSD for local storage, so it is necessary to consider the use of storage saving measures during normal usage.</span></span>  <span data-ttu-id="c988e-332">若要設定儲存空間的意義：</span><span class="sxs-lookup"><span data-stu-id="c988e-332">To configure Storage Sense:</span></span>

1.  <span data-ttu-id="c988e-333">搜尋 [**系統設定**] 底下的 [**儲存設定**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-333">Search for **storage settings**, which is found under **System settings**.</span></span>

2.  <span data-ttu-id="c988e-334">在 [ **設定**] 底下，選取 [ **開啟儲存空間感知** ]，開啟 [ **儲存空間** 設定] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c988e-334">Under **Settings**, select **Turn on storage sense** to open the **Storage** settings page.</span></span>

3.  <span data-ttu-id="c988e-335">開啟 [儲存空間感知 **]。**</span><span class="sxs-lookup"><span data-stu-id="c988e-335">Turn Storage Sense to **On**.</span></span>

4.  <span data-ttu-id="c988e-336">選取 [ **設定儲存空間感知] 或 [立即執行** ]，然後設定設定，盡可能讓檔案保持在線上， (因為磁碟空間) 有限。</span><span class="sxs-lookup"><span data-stu-id="c988e-336">Select **Configure Storage Sense or run it now** and configure settings to keep files online as much as possible (due to limited drive space).</span></span>

<span data-ttu-id="c988e-337">建議的設定：</span><span class="sxs-lookup"><span data-stu-id="c988e-337">Recommended settings:</span></span>

- <span data-ttu-id="c988e-338">每日執行儲存感知 =。</span><span class="sxs-lookup"><span data-stu-id="c988e-338">Run Storage Sense = Every Day.</span></span>
- <span data-ttu-id="c988e-339">刪除我的 app 無法使用的臨時檔案 = 每隔14天 (至少) 。</span><span class="sxs-lookup"><span data-stu-id="c988e-339">Delete temporary files that my apps aren't using = Every 14 days (at least).</span></span>
- <span data-ttu-id="c988e-340">如果在 [我的下載] 資料夾中有超過30天的檔案，請將它們刪除。</span><span class="sxs-lookup"><span data-stu-id="c988e-340">Delete files in my Downloads folder if they have been there for over = 30 days.</span></span>
- <span data-ttu-id="c988e-341">OneDrive：如果未開啟超過 = 30 天的時間，內容就會變成 [線上]。</span><span class="sxs-lookup"><span data-stu-id="c988e-341">OneDrive: Content will become online-only if not opened for more than = 30 days.</span></span>

### <span data-ttu-id="c988e-342">平板電腦模式</span><span class="sxs-lookup"><span data-stu-id="c988e-342">Tablet mode</span></span>

<span data-ttu-id="c988e-343">如有需要，請開啟平板電腦模式以取得協助工具需求。</span><span class="sxs-lookup"><span data-stu-id="c988e-343">Turn on Tablet mode if desired for accessibility needs.</span></span>


### <span data-ttu-id="c988e-344">音效設定</span><span class="sxs-lookup"><span data-stu-id="c988e-344">Sound settings</span></span>

1. <span data-ttu-id="c988e-345">搜尋 [ **聲音設定** ]，然後開啟此頁面。</span><span class="sxs-lookup"><span data-stu-id="c988e-345">Search for **Sounds settings** and open this page.</span></span>

2. <span data-ttu-id="c988e-346">選取右側的 [ **音效** 控制台]，然後選取 [ **聲音** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c988e-346">Select **Sound Control Panel** on the right and select the **Sounds** tab.</span></span>

3. <span data-ttu-id="c988e-347">在 [**程式事件**]**下，將** **[裝置**連線] 與 **[裝置中斷連線]**</span><span class="sxs-lookup"><span data-stu-id="c988e-347">Under **Program Events** set **Device Connect** and **Device Disconnect** to **None**.</span></span>

### <span data-ttu-id="c988e-348">靜音通知</span><span class="sxs-lookup"><span data-stu-id="c988e-348">Silence notifications</span></span>

1. <span data-ttu-id="c988e-349">搜尋 **焦點協助** ，然後開啟此頁面。</span><span class="sxs-lookup"><span data-stu-id="c988e-349">Search for **Focus assist** and open this page.</span></span>

2. <span data-ttu-id="c988e-350">選取 [ **僅限鬧鐘**]。</span><span class="sxs-lookup"><span data-stu-id="c988e-350">Select **Alarms Only**.</span></span> <span data-ttu-id="c988e-351">這將避免持續通知飛出視窗。</span><span class="sxs-lookup"><span data-stu-id="c988e-351">This will avoid constant notification flyouts.</span></span>

### <span data-ttu-id="c988e-352">磁碟清理</span><span class="sxs-lookup"><span data-stu-id="c988e-352">Disk Cleanup</span></span>

1. <span data-ttu-id="c988e-353">搜尋 [ **磁片清理** ] 並開啟此應用程式。</span><span class="sxs-lookup"><span data-stu-id="c988e-353">Search for **Disk Cleanup** and open this app.</span></span>

2. <span data-ttu-id="c988e-354">在 [ **要刪除**的檔案] 底下，選取您要刪除的檔案。</span><span class="sxs-lookup"><span data-stu-id="c988e-354">Under **Files to delete**, select the files you wish to delete.</span></span> 

3. <span data-ttu-id="c988e-355">同時選取 [ **清理系統**檔案]。</span><span class="sxs-lookup"><span data-stu-id="c988e-355">Also select **Clean up system files**.</span></span>

## <span data-ttu-id="c988e-356">完成並驗證</span><span class="sxs-lookup"><span data-stu-id="c988e-356">Complete and verify</span></span>

1. <span data-ttu-id="c988e-357">掃描並安裝所有的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="c988e-357">Scan for and install all Windows Updates.</span></span>

2. <span data-ttu-id="c988e-358">更新群組原則。</span><span class="sxs-lookup"><span data-stu-id="c988e-358">Update Group Policy.</span></span>

   1. <span data-ttu-id="c988e-359">在提升許可權的命令提示字元中，輸入 **gpupdate/force/boot/wait： 0**。</span><span class="sxs-lookup"><span data-stu-id="c988e-359">At an elevated command prompt, enter **gpupdate /force /boot /wait:0**.</span></span>
   
3. <span data-ttu-id="c988e-360">重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="c988e-360">Restart the device.</span></span>

4. <span data-ttu-id="c988e-361">驗證工作列 app。</span><span class="sxs-lookup"><span data-stu-id="c988e-361">Verify taskbar apps.</span></span>

   - <span data-ttu-id="c988e-362">Connect App</span><span class="sxs-lookup"><span data-stu-id="c988e-362">Connect App</span></span>
   - <span data-ttu-id="c988e-363">[鎖定] 圖示</span><span class="sxs-lookup"><span data-stu-id="c988e-363">Lock Icon</span></span>
   - <span data-ttu-id="c988e-364">剪取與繪圖</span><span class="sxs-lookup"><span data-stu-id="c988e-364">Snip & Sketch</span></span>
   - <span data-ttu-id="c988e-365">小組 (（如果適用）) </span><span class="sxs-lookup"><span data-stu-id="c988e-365">Teams (if applicable)</span></span>
   - <span data-ttu-id="c988e-366">Office 應用程式 (（如果適用）) </span><span class="sxs-lookup"><span data-stu-id="c988e-366">Office Apps (if applicable)</span></span>
   - <span data-ttu-id="c988e-367">Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="c988e-367">Surface App</span></span>
   - <span data-ttu-id="c988e-368">白板</span><span class="sxs-lookup"><span data-stu-id="c988e-368">Whiteboard</span></span>
    
5. <span data-ttu-id="c988e-369">確認目前狀態偵測。</span><span class="sxs-lookup"><span data-stu-id="c988e-369">Verify presence detection.</span></span>

   - <span data-ttu-id="c988e-370">目前系統託盤中的目前狀態偵測將是綠色圖示。</span><span class="sxs-lookup"><span data-stu-id="c988e-370">Presence detection will be a green icon in the system tray.</span></span>
    
6. <span data-ttu-id="c988e-371">確認投影到此電腦的 [連線] App 已啟用。</span><span class="sxs-lookup"><span data-stu-id="c988e-371">Verify projecting to this PC is enabled with the Connect App.</span></span> <span data-ttu-id="c988e-372">**將 Project 設定為這台電腦**設定之後，請至少執行一次 [連線] App。</span><span class="sxs-lookup"><span data-stu-id="c988e-372">After configuring  **Project to this PC** settings, run the Connect App at least once.</span></span> <span data-ttu-id="c988e-373"> (接著，[連接] App 不需要執行，就能投影至 Surface Hub。 ) </span><span class="sxs-lookup"><span data-stu-id="c988e-373">(Subsequently, the Connect App does not need to be running in order to project to Surface Hub.)</span></span>

7. <span data-ttu-id="c988e-374">驗證電源和睡眠設定。</span><span class="sxs-lookup"><span data-stu-id="c988e-374">Verify power and sleep settings.</span></span>

    - <span data-ttu-id="c988e-375">螢幕保護裝置程式：15分鐘，設定為 (無]) 、Mystify 或空白;確認已選取 [需要密碼的核取方塊]。</span><span class="sxs-lookup"><span data-stu-id="c988e-375">Screen Saver: 15 minutes, set to (none), Mystify or Blank; ensure the check box for requiring password is selected.</span></span>
    - <span data-ttu-id="c988e-376">螢幕： **在2小時後關閉**。</span><span class="sxs-lookup"><span data-stu-id="c988e-376">Screen: **Turn off after 2 hours**.</span></span>
    - <span data-ttu-id="c988e-377">PC：  **4 小時後關閉**。</span><span class="sxs-lookup"><span data-stu-id="c988e-377">PC:  **Turn off after 4 hours**.</span></span>
    
8. <span data-ttu-id="c988e-378">驗證 Windows Hello 是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="c988e-378">Verify Windows Hello is working.</span></span>

9. <span data-ttu-id="c988e-379">驗證同步處理您的設定已停用。</span><span class="sxs-lookup"><span data-stu-id="c988e-379">Verify sync your settings is disabled.</span></span>

10. <span data-ttu-id="c988e-380">確認啟動 app。</span><span class="sxs-lookup"><span data-stu-id="c988e-380">Verify startup apps.</span></span>

> [!TIP]
> <span data-ttu-id="c988e-381">安裝並設定 Windows 10 之後，Surface Hub 的配置可以像管理任何其他的 Windows 10 裝置一樣進行管理。</span><span class="sxs-lookup"><span data-stu-id="c988e-381">After installing and configuring Windows 10, the Surface Hub 2S can be managed just like any other Windows 10 device.</span></span>

## <span data-ttu-id="c988e-382">相關主題</span><span class="sxs-lookup"><span data-stu-id="c988e-382">Related topics</span></span>

<a href="surface-hub-2s-migrate-os.md" target="_blank"> <span data-ttu-id="c988e-383">移轉到 Windows 10 專業版或 Surface Hub 2 企業版</span><span class="sxs-lookup"><span data-stu-id="c988e-383">Migrate to Windows 10 Pro or Enterprise on Surface Hub 2</span></span></a>
