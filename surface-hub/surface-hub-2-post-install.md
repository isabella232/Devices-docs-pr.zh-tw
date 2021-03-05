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
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a>設定 Windows 10 專業版或 Surface Hub 2 企業版

完成移移至 Windows 10 專業版或企業版之安裝程式之後，您可以執行下列步驟，在 Surface Hub 2 上設定應用程式和設定。 建議您執行這些步驟，以確保使用這個個人化的大型螢幕觸控和觸控筆電腦時獲得最佳體驗。

執行這些步驟時，您可能會發現使用有線或無線鍵盤和滑鼠很有用。

## <a name="configure-system-settings"></a>設定系統設定

1. 使用在裝置上具有當地系統管理員許可權的帳戶進行登錄。  

    - 在 Azure AD 加入的裝置上，執行 Azure AD 加入的使用者會自動新增到本地系統管理員群組。 Azure AD 全域系統管理員和 Azure AD 裝置系統管理員 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本地系統管理員 </a> 。 
    
    - 您可以在命令提示輸入 net **localgroup** 系統管理員，以列出具有本地系統管理員許可權的帳戶。
    
2. 使用好用的名稱重新命名裝置，例如 **：username-SHub-Desktop。**

3. 選取**開始**  >  **設定**  >  **帳戶**  >  **同步您的設定**，並關閉**同步**設定。 

    - 此處使用的設定旨在啟用最佳的大螢幕觸控體驗，因此您可能不想同步其他裝置。
    
4. 重新開機裝置。

## <a name="enable-the-touch-keyboard-and-touchpad"></a>啟用觸控式鍵盤和觸控板

1. 選取**開始**  >  **設定**  >  **裝置**  >  **輸入，****** 在未在平板電腦模式且未連接鍵盤時開啟顯示觸控式鍵盤。

2. 點選並按住或以滑鼠右鍵按一下工作列，然後選取 [顯示 **觸控式鍵盤** 按鈕和 **顯示觸控板按鈕**。 

    - 觸控式鍵盤對於直接使用者輸入很有説明，而虛擬觸控板可協助精確地選取專案、將工具提示停留在畫面上，或作為點選並按住滑鼠右鍵的替代方案。 
    
    - 請參閱以下範例。

      ![觸控設定](images/touch.png)

3. 將觸控式鍵盤設定為 QWERTY 和浮動。

    1. 選取 **工作列** 上的鍵盤圖示以顯示觸控式鍵盤。
    
    1. 在觸控式鍵盤上，選取左上角的鍵盤圖示以開啟鍵盤設定。
    
    1. 選取頂端列上最後一個鍵盤類型以啟用 QWERTY，然後選取第二列的最後一個選項來啟用浮動，這在這個大型螢幕上非常實用。 請參閱以下範例。

       ![鍵盤設定](images/kbd.png)
 
4. 設定柔式鍵盤設定。

    1. 選取觸控 **式** 鍵盤上的設定圖示，或搜尋並開啟 **輸入設定**。
    
       ![柔式鍵盤設定](images/sh2-softkeyboard.png)

    1. 啟用拼字、輸入和觸控式鍵盤下的所有選項。


下列範例顯示軌跡板，這很適用于流覽和選取選項。 螢幕小鍵盤正用於搜尋 Microsoft Store：

![使用軌跡板](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>設定藍牙鍵盤和滑鼠 (選) 

如果您是使用裝置做為主要 Windows 裝置，或經常使用鍵盤和滑鼠進行輸入或精確作業，請連接鍵盤和滑鼠。

如果您的 Surface Hub 裝置靠近電腦，您可以使用沒有邊框的滑鼠，在 Surface Hub 與電腦之間順暢 <a href="https://aka.ms/mm" target="_blank"> </a> 地移動。 詳細資訊請參閱 Microsoft 從 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> 車庫下載：滑鼠沒有邊框。 </a>

## <a name="example-of-taskbar-layout"></a>工作列版面配置範例

完成下列步驟以設定/設定 Windows 10 專業版或企業版 Surface Hub 2 後，建議您使用將最常用的應用程式釘到工作列，以快速單鍵啟動每個應用程式。 以下是工作列外觀的範例：

 ![工作列版面配置](images/taskblyt.png)
### <a name="update-installed-apps"></a>更新已安裝的應用程式

若要更新所有已安裝的市/市 App：

1. 開啟 Microsoft Store 應用程式， **然後選取右上角** 的查看更多省略號。
2. 選取 **下載和更新。**
3. 選取 **取得更新**

### <a name="scan-for-and-install-all-windows-updates"></a>掃描並安裝所有 Windows 更新
移移至 Windows 10 專業版或 Windows 10 企業版之後，可能有可供您安裝的維護及功能更新。 

- 請前往**安全性**  >  **&設定>，** 然後選取**檢查更新**。
- 如果有任何更新，請安裝更新、重新開機，然後重複此程式，直到您看到下列通知：

> [!div class="mx-imgBorder"]
> ![Windows Update 的'您為最新狀態'通知](images/wustatus.png)


## <a name="onedrive-for-business"></a>商務用 OneDrive

使用商務用 OneDrive 輕鬆在所有工作裝置之間共用工具、記錄 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 檔及其他檔案。

- OneDrive 可讓您在膝上型電腦、Surface Hub 電腦版和 Intune 管理行動裝置之間共用您的工作檔案。 您可以在任何裝置上編輯檔案，所有已連接網路之裝置都會隨著變更更新。

- 考慮 Surface Hub SSD (128 GB) 的大小，如果您在 Surface Hub 桌面裝置上設定 OneDrive，請確定預設設定是讓檔案保持線上，並隨著您的使用下載檔案。

若要將 OneDrive 設定為僅于需要時下載檔案，請設定 [檔案 **On-Demand」** 設定以節省空間，並在您使用檔案 **時下載檔案**。 有關詳細資訊，請參閱 Windows 中的查詢和設定檔案 <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> On-Demand 狀態 </a> 。

![OneDrive 設定](images/onedrive.png)

> [!NOTE]
> 您也可以重複這些步驟來設定個人 OneDrive，但請務必節省磁碟空間，並只下載您所需的檔案。

## <a name="sharepoint-and-teams"></a>SharePoint 和 Teams

SharePoint 和 Teams 頻道檔案也可以使用 OneDrive 同步處理引擎，同步處理到您的桌面裝置 ，例如膝上型電腦和 Surface Hub。

若要使用 OneDrive 同步處理應用程式將內部公司檔案同步處理至您的本地磁碟機：

1. 前往 SharePoint 網站，並流覽至最頂層的檔目錄，以尋找您有興趣從本地裝置檢視或編輯的檔案。

2. 在 SharePoint **功能區** 頂端的同步按鈕上選取。

3. 在快顯視窗**上**選取 [開啟此**網站嘗試開啟 Microsoft OneDrive。**

4. 選取工作列右下角的 OneDrive 圖示，確認 SharePoint 檔案正在同步處理至您的本地磁碟機機。

5. 確認設定設定是讓檔案保持線上，並只在使用檔案時下載：

    1. 開啟檔案檔案管理器。
    
    2. 流覽至 SharePoint 名稱，然後以滑鼠右鍵按一下;例如 **，Contoso \ \<SharePoint Document Folder Name\> **。
    
    3. 選取 **釋放空間**。
    
    4. 狀態列會顯示檔案和資料夾的狀態。 詳細資訊請參閱使用 OneDrive 同步處理 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 用戶端同步處理 SharePoint 檔案 </a> 。
    
6. Teams 頻道檔案會儲存在 SharePoint 網站中，並擁有所有相同的 SharePoint 檔功能，包括版本歷程記錄，以及同步處理至您的本地桌面裝置。 若要同步處理 Teams 頻道檔案：

    1. 流覽至感興趣的 Teams 頻道，然後選取 **頂端的檔案** 定位點。 然後選取同步 **。** 檔案會開始同步處理，而且將會顯示在**Desktop \ \<name of the Teams Channel\> Contoso \**的檔案中。
    
    2. 使用您用來同步處理 SharePoint 網站的相同程式，將檔案保留于雲端，並只在使用檔案時下載，在 Teams 頻道名稱的 [檔案檔案管理器中點選並按住或以滑鼠右鍵按一下，然後**** 選取釋放空間。

## <a name="surface-hub-pen-settings"></a>Surface Hub 觸控筆設定

**配對藍牙 Surface Hub 觸控筆**

配對觸控筆，讓觸控筆的內建保持最新狀態、設定筆快捷方式，以及取得藍牙裝置設定頁面或 Surface 應用程式中的電池充電資訊：

1. 選取**開始**  >  **設定**  >  **裝置**。

2. 選取 **新增藍牙或其他裝置**。

3. 選擇 **藍牙**。

4. 移除筆尾按鈕並搖動以中斷電池連接。

5. 重新蓋上保護蓋並按住保護蓋，直到配對的 LED 閃爍。

6. 在 Surface Hub 藍牙設定上，選擇 **Surface Hub 2 觸控筆**。

7. 完成配對作業。 

8. 如果配對失敗，您可以嘗試再次配對筆。 如果無法運作，您可以驗證觸控筆在 Whiteboard 應用程式中是否可運作，來測試電池是否充電。 如果沒有，請更換電池，然後再次嘗試配對筆。 如有需要，請重新開機裝置，然後再試一次。

**設定筆快捷方式** Surface Hub 觸控筆有一個快捷方式按鈕，有時稱為「尾鍵按一下」。 如先前所述，若要進行快速鍵的安裝，您需先將筆配對。

1. 搜尋手寫筆，然後選取 **Windows Ink &中的手寫筆**。

2. 在頁面底部附近，選取可開啟對話方塊的 [筆快捷方式，如下所示：

   ![筆快捷方式](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>相機組配置

您可以將相機安裝在裝置頂端或任一側。 如果您將中心與桌面支架而非購物車一起使用，或靠近中樞，請將相機安裝在一個位置，以優化相機角度。 相機不會自動旋轉，因此您必須有 2mm 十六進位鍵，以手動旋轉相機。 

請參閱 Surface Hub 2S 相機的相機鏡頭方向，以瞭解如何側向安裝相機並手動旋轉 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> 相機 </a> 。

## <a name="windows-hello-configuration"></a>Windows Hello 組配置

執行 Windows 10 企業版 Surface Hub 2S 可讓 Win32 桌面應用程式的完整套件，以及掃描 Windows Hello 選項。 Surface Hub 2 指紋識別器配件可以插入裝置上的任何 USB-C 埠。 

若要訂購 Surface Hub 2 指紋讀取程式或查看技術規格，請參閱 (surface-hub-2-essential-add-ons.md" target="_blank">Surface Hub 2 上的 Windows 10 專業版和企業版基本附加元件。 </a> 

插入指紋識別器之後，請選取 **[開始**  >  **設定**  >  **帳戶**登錄  >  **選項：**  >  **Windows Hello 指紋**來註冊指紋。

使用 Windows Hello 認證的裝置進行臉部識別。 Surface Hub 2S 相機不支援 Windows Hello 臉部識別。

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>啟用工作列上的鎖定畫面快捷方式圖示

若要新增圖示至工作列，以啟用類似 Windows-L 鍵盤快速鍵的單鍵螢幕鎖定： 

1.  點選並按住或以滑鼠右鍵按一下桌面，選取 **[新增**  >  **快捷方式**  >  **流覽**  >  **桌面**  >  **確定**  >  **下一步**。

1.  提供快速鍵的名稱，例如 **鎖定我的電腦**， **然後選取完成**。

1.  以滑鼠右鍵按一下或點選並按住桌面上新建立快速鍵，然後選取 [ **內容**。 在快捷方式**定位**點上，在目標欄位中輸入**** 下列專案 **：Rundll32.exe User32.dll，LockWorkStation**

1.  選取變更 **圖示** 按鈕，然後流覽C:\Windows\System32\imageres.dll** 並選取 ** 要使用圖示。 

    請參閱下列範例：

    ![選擇圖示](images/lock.png)
    
1.  選取 **確定** 以儲存快捷方式。

1.  以滑鼠右鍵按一下或點選並按住快捷方式，然後選取 [**釘選到工作列。**

1. 將鎖定快捷方式釘上工作列之後，就可以從桌面刪除它。

## <a name="applications"></a>應用程式


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

若要安裝 Microsoft Whiteboard：

 - 選取**工作列右**下角的 Windows Ink 工作區圖示，然後下載**Whiteboard。**
 
   ![筆墨工作區](images/ink.png) 

或者，您也可以從 Microsoft Store 安裝 Whiteboard：

1. 開啟 Microsoft Store 應用程式並搜尋**Whiteboard。**

2. 選擇 **否，** 感謝您在裝置上進行註冊及使用。

3. 將白板釘到工作列。

### <a name="surface-app"></a>Surface 應用程式

1. 在 Microsoft Store 中，搜尋**Surface。**

2. 將篩選 **上的可用** 設定為 **所有裝置**。

3. 安裝 **Surface** 應用程式。 這應該是列出的第一個應用程式。 您可能需要將 MSA 與 Store 關聯，才能安裝應用程式。

4. 將 **Surface 應用程式** 釘上工作列。

### <a name="snip--sketch"></a>剪取與繪圖

1. 開啟 **Snip &繪圖** 應用程式，並釘上工作列。

2. 選取右上角的省略號， **然後選取設定**。

3. 在**設定中**，開啟自動** (****複製到**剪貼****) 。

### <a name="microsoft-office"></a>Microsoft Office

1. 開啟 <a href="https://portal.office.com/account#installs" target="_blank"> Office 入口網站 </a> 並安裝您想要的應用程式。

2. 將想要的 Office 應用程式釘上工作列。

3. 如果已安裝 Outlook，請務必將 Outlook OST 設為只儲存過去兩周的緩存。 這會大量減少磁片使用量和設定時間。

    - 選取**檔案**  >  **帳戶設定，** 然後選取您的帳戶。
    
    - 選取 **變更** ，將使用 Exchange 緩存模式 **滑杆設定** 為 14 天。

### <a name="microsoft-teams"></a>Microsoft Teams

1. 下載並安裝 <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft </a> Teams。

2. 將設定為自動啟動應用程式 (選) 。

3. 將 Teams 釘到工作列。

4. 考慮減少裝置上的 Teams 通知，以避免干擾 (選擇) 。

   ![Teams 通知](images/teams.png)

### <a name="connect-app"></a>連接應用程式

> [!IMPORTANT]
> 在 Windows 10 版本 2004 及更新版本中，使用 Miracast 進行無線投影的 Connect 應用程式預設不會安裝，但提供選擇性功能。 如果您已經安裝 (或更新至) Windows 版本 2004 或更新版本，您可能會在設定中于 Projecting 到此電腦畫面上看到下列內容：

![Project 到此電腦](images/sh2-project.png) 


1. 若要從 「Projecting to this PC」設定頁面安裝應用程式，請選取選擇性**功能**新增功能  >  ** **，然後安裝**無線顯示**應用程式。

2. 當您 **說**它沒問題時，在某些 Windows 和 Android 裝置可以預測到這部電腦下，選擇：

    - **如果裝置不在** 公司網路上，則可于任何地方使用。
    - 否則，請選擇**安全網路上所有位置的可用。**
    
3. 在 **要求專案到這部電腦下**，選擇僅 **第一次**。

4. 在**需要 PIN 進行配對下****，選擇永不**。

5. 若要啟動應用程式並釘上工作列，請搜尋**Connect。**

6. 開啟應用程式。 當應用程式開啟時，以滑鼠右鍵按一下工作列上的 [連接應用程式圖示，然後選取 **釘選到工作列**上。

7. 然後關閉 Connect 應用程式。 **除非應用程式至少** 執行過一次，否則 Project 到此電腦可能無法使用。

不在公司網路上時的建議群組原則：

![家裡的設定](images/project1.png)

公司網路上的建議群組原則：

![工作中的設定](images/project2.png)

### <a name="your-phone"></a>您的手機

Windows **** 10 預設會安裝您的手機應用程式。 如果沒有，您也可以從 Windows 市儲存區安裝。

有關設定應用程式的資訊，請參閱如何在 Windows 10 上設定您的手機，以及如何同步處理 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 電腦與手機之間的資料 </a> 。 另請參閱 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 如何修正 Windows 10 上您的手機應用程式的常見問題 </a> 。

###  <a name="fancy-zones"></a>花俏的區域


**花俏區域** 是 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> GitHub 上名為 PowerToys 的工具 </a> 集合的一部分。 這是在 Surface Hub 2 上運用螢幕空間的一種好方式，讓您定義顯示器上的固定版面配置 ("區域") ，然後選取要在每個區域中執行的應用程式。 


[PowerToys Wiki](https://github.com/microsoft/PowerToys/wiki)提供如何使用及自訂每個工具的指示，包括[花式區域](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)。 在高層級 – 安裝 PowerToys 之後，您可以選取或建立自訂版面配置，然後按住 Shift 鍵並拖曳，或使用鍵盤鍵將執行中的應用程式移至特定區域。 使用藍牙或 USB 鍵盤和滑鼠可協助進行這項操作，或者您可以使用螢幕觸控式鍵盤和觸控板。

**Power toys 秘訣**
- 若要在 GitHub 上接收 PowerToys 版本更新的電子郵件通知，請按一下頁面頂端的 [註冊> [按鈕](https://github.com/microsoft/PowerToys/releases)。
- 安裝 PowerToys 之後，您可以設定 PowerToys 設定自動下載更新，以接收 Windows 通知和/或**** 下載及安裝最新的更新。
- 若要取得 PowerToys 設定，請選取工作列上**** 向上的 [執行中應用程式，然後以滑鼠右鍵按一下或按住 PowerToys 圖示，直到功能表出現。 選取 「設定」。
- 在 PowerToys 設定頁面的底部，自動開啟 **下載** 更新。
- 更新發行後，系統會顯示 Windows 通知，讓您選擇安裝更新時間。


### <a name="edge-chromium-browser"></a>Edge Chromium 瀏覽器

下載並安裝新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium 瀏覽器 </a> 。


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub 硬體診斷工具

Microsoft Store 免費提供 Surface Hub 硬體診斷 <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> </a> 工具。 此工具的設計可協助確保 Surface Hub 的執行效果最佳。 它包含測試，以判斷您的中器是否為最新狀態並正確進行安裝。 互動式測試允許您確認基本功能是否如預期地執行。 如果遇到問題，可以將結果儲存起來，與 Surface Hub 支援小組分享。 按一下連結以從 Microsoft Store 安裝，然後將應用程式釘到工作列。

## <a name="additional-settings"></a>其他設定

### <a name="pen-tail-select-to-launch-whiteboard"></a>選取筆尾以啟動 Whiteboard

1. 搜尋手寫 **筆，** 然後選取 **Windows Ink &中的手寫筆**。

2. 靠近頁面底部，在**筆快捷方式下將****選取一**次設定為**Microsoft Whiteboard。** 

### <a name="power-management"></a>電源管理

有幾個電源設定可用，以在 Surface Hub 2 上使用 Windows 10 專業版或企業版獲得最佳體驗。 這包括螢幕和電腦超時，以及它們如何與內建的人體目前狀態偵測 (Doppler) 、螢幕保護裝置與密碼保護互動，以及適當時如何為膝上型電腦/桌面使用者進行群組原則電源設定。

Surface Hub 2 上的 Windows 10 專業版或企業版可觸控、滑鼠和鍵盤動作，以及內建的人體檢出偵測功能 (Doppler) ，防止螢幕進入睡眠狀態。 系統預設會啟用人力偵測功能，但如果需要，可以在 UEFI 中停用偵測功能，方法包括切換 Surface UEFI Configurationator 工具中的裝置選項做為初始移移的一部分，或建立並套用稍後的 UEFI 群組原則套件。 

**Power Management：螢幕和電腦睡眠設定**

1. 選取**啟動**  >  **設定**  >  **系統**  >  **電源&睡眠**。

2. 將電源模式滑杆設定為 **最佳效果**。

3. 將螢幕和睡眠值設定為您的喜好設定，同時也會計算偵測到移動時喚醒裝置之 Doppler 目前狀態偵測。 因此，最佳作法是將螢幕設定為 **2** 小時後關閉，而電腦在 **4 小時後關閉。**

**Power Management：螢幕保護裝置**

1. 搜尋鎖定 **畫面並** 開啟 **鎖定畫面設定**。

2. 將**螢幕超時設定和****螢幕保護裝置設定**為您的喜好設定。 建議的預設值為：

   - 螢幕保護裝置 (無) 或您所選擇的螢幕保護裝置程式。
   - 等候時間到 15 分鐘。
   - 在履歷表上，顯示登入畫面。


**Power Management：群組原則**

執行下列程式之前，請向 IT 部門確認核准，以將 Surface Hub 2S 裝置排除在全域電源管理政策外。 某些電源管理設定可能會停用目前狀態偵測功能。

1. 搜尋軟體 **中心並** 開啟。

2. 選取 **選項**。

3. 展開 **電源管理，**  然後 **選取不要將**IT 部門的電源設定適用于這台電腦。

   ![軟體設定](images/soft-cntr.png)

### <a name="storage-sense"></a>儲存空間感知器

Surface Hub 2 具有 128 GB 的局內儲存空間 SSD，因此在一般使用期間，必須考慮儲存空間儲存量。  若要設定儲存空間感知：

1.  搜尋儲存 **空間設定**，此設定位於系統 **設定下**。

2.  在 **設定下**， **選取開啟儲存空間感知來** 開啟 **儲存空間** 設定頁面。

3.  將儲存空間感知 **功能開啟**。

4.  選取 **設定儲存空間感知程式或現在** 執行，並設定設定讓檔案盡可能保持線上 (因為磁碟空間有限) 。

建議設定：

- 執行儲存空間感知 = 每天。
- 刪除我的應用程式未使用的暫) = 每 14 天 (一次) 。
- 如果檔案存在超過 = 30 天，請刪除我的下載資料夾中的檔案。
- OneDrive：如果超過 = 30 天，內容將會變成僅線上。

### <a name="tablet-mode"></a>平板電腦模式

如果需要協助工具，請開啟平板電腦模式。


### <a name="sound-settings"></a>音效設定

1. 搜尋音效 **設定並** 開啟此頁面。

2. 選取 **右邊的** 音效控制台，然後選取的音效 **製表** 位。

3. 在**程式事件設定****下，裝置連接****與裝置中斷連****至無**。

### <a name="silence-notifications"></a>靜音通知

1. 搜尋焦點 **輔助，** 然後開啟此頁面。

2. 僅 **選取鬧鐘**。 這可避免常數通知飛出。

### <a name="disk-cleanup"></a>磁碟清理

1. 搜尋磁片 **清理並** 開啟此應用程式。

2. 在 **要刪除的檔案**下，選取要刪除的檔案。 

3. 同時選取 **清理系統檔案**。

## <a name="complete-and-verify"></a>完成並驗證

1. 掃描並安裝所有 Windows 更新。

2. 更新群組原則。

   1. 在提升許可權的命令提示符中，輸入**gpupdate /force /boot /wait：0。**
   
3. 重新開機裝置。

4. 驗證工作列應用程式。

   - 連接應用程式
   - 鎖定圖示
   - 剪取與繪圖
   - Teams (如適用，) 
   - 如果適用 (Office 應用程式) 
   - Surface App
   - 白板
    
5. 確認目前狀態偵測。

   - 目前狀態偵測會為系統磁碟機中的綠色圖示。
    
6. 使用 Connect App 確認已啟用此電腦的專案。 將  **Project 設定為此電腦** 設定之後，請至少執行一次 Connect App。  (之後，Connect App 不需要執行，也不需要執行，也不需要專案到 Surface Hub.) 

7. 確認電源和睡眠設定。

    - 螢幕保護裝置：15 分鐘，設定為 (、) 、Mystify 或 Blank;確認已選取要求密碼的核取方塊。
    - 螢幕 **：2 小時後關閉**。
    - 電腦  **：4 小時後關閉**。
    
8. 確認 Windows Hello 可以工作。

9. 確認同步您的設定已停用。

10. 驗證啟動應用程式。

> [!TIP]
> 安裝及安裝 Windows 10 之後，Surface Hub 2S 可以像管理任何其他 Windows 10 裝置一樣受到管理。

## <a name="related-topics"></a>相關主題

<a href="surface-hub-2s-migrate-os.md" target="_blank"> 移轉到 Windows 10 專業版或 Surface Hub 2 企業版</a>
