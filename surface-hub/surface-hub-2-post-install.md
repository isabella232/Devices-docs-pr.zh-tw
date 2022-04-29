---
title: 在 Surface Hub 2 上設定 Windows 10/11 Pro 或 Enterprise
description: 本文包含使用個人化大型螢幕觸控和手寫筆電腦時，確保最佳體驗的建議。
keywords: Surface Hub， Windows 10， 桌面， 安裝， 設定
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
- Windows 10
- Windows 11
ms.openlocfilehash: 2b645ef580eda85a91bf282c8772c42c09cbb67d
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497766"
---
# <a name="configure-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>在 Surface Hub 2 上設定 Windows 10/11 Pro 或 Enterprise

移轉至 Windows 10/11 Pro或Enterprise之後，您可以設定應用程式和設定，以確保使用這個個人化大型螢幕觸控和手寫筆電腦的最佳體驗。

執行這些步驟時，您可能會發現使用有線或無線鍵盤和滑鼠很有説明。

## <a name="configure-system-settings"></a>設定系統設定

1. 使用在裝置上具有本機系統管理員許可權的帳戶登入。  

    - 在已加入Azure AD裝置上執行Azure AD加入的使用者會自動新增至本機系統管理員群組。  Azure AD全域管理員和Azure AD裝置系統管理員 <a href="/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本機系統 </a> 管理員。 

    - 您可以在命令提示字元中輸入 **net localgroup administrators** ，以列出具有本機系統管理員許可權的帳戶。
    
2. 使用易記名稱重新命名裝置，例如 **username-SHub-Desktop**。

3. 選取 **[開始**  >  **設定**  >  ]**[**  >  帳戶]**[同步處理您的設定**]，然後關閉 **[同步處理設定**]。 

    - 此處使用的設定旨在啟用最佳的大螢幕觸控體驗，因此您可能不想同步處理其他裝置。
    
4. 重新開機裝置。

## <a name="enable-the-touch-keyboard-and-touchpad"></a>啟用觸控式鍵盤和觸控板

1. 選取 **[開始**  >  **設定**  >  ****  >  ][裝置**類型**]，然後開啟 [**不在平板電腦模式下顯示觸控式鍵盤，而且沒有附加鍵盤時顯示觸控式鍵盤]**。

2. 點選並按住或以滑鼠右鍵按一下工作列，然後選取 **[顯示觸控式鍵盤] 按鈕** 和 [ **顯示觸控板] 按鈕**。 

    - 觸控式鍵盤對於直接使用者輸入很有説明，而虛擬觸控板有助於精確選取、暫留工具提示，或做為點選並按住滑鼠右鍵的替代方案。 
    
    - 請參閱以下範例。

      ![觸控設定。](images/touch.png)

3. 將觸控式鍵盤設定為 QWERTY 並浮動。

    1. 選取任務 **欄上的鍵盤** 圖示以顯示觸控式鍵盤。
    
    1. 在觸控式鍵盤上，選取左上角的鍵盤圖示以開啟鍵盤設定。
    
    1. 選取頂端資料列上最後一個鍵盤類型旁的 ，以啟用 QWERTY，並選取第二個數據列上的最後一個選項來啟用浮動，這對於這個大型畫面很有説明。 請參閱以下範例。

       ![鍵盤設定。](images/kbd.png)
 
4. 設定軟式鍵盤設定。

    1. 選**取觸**控式鍵盤上的設定圖示，或搜尋並開啟 **[輸入設定]**。
    
       ![軟式鍵盤設定。](images/sh2-softkeyboard.png)

    1. 啟用 [拼字]、[鍵入] 和 [觸控式] 鍵盤下的所有選項。


下列範例顯示追蹤板，這對於巡覽和選取選項很有用。 螢幕上的鍵盤正用來搜尋Microsoft Store：

![使用追蹤板。](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>設定藍牙鍵盤和滑鼠 (選用) 

如果您使用裝置作為主要Windows裝置，或經常使用它來輸入或精確工作，請連線鍵盤和滑鼠。

如果您的Surface Hub裝置靠近電腦，您可以使用 <a href="https://aka.ms/mm" target="_blank"> 無框線 </a> 的滑鼠在Surface Hub與電腦之間順暢移動。 For more information, see <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> Microsoft download from The Garage: Mouse without Borders. </a>

## <a name="example-of-taskbar-layout"></a>工作列配置範例

完成下列步驟來設定/設定 Windows 10/11 Pro或Enterprise的 Surface Hub 2 之後，建議您利用將最常用的應用程式釘選到工作列，以快速單點啟動每個應用程式。 以下是工作列外觀的範例：

 ![工作列配置。](images/taskblyt.png)
### <a name="update-installed-apps"></a>更新已安裝的應用程式

若要更新所有已安裝的市集應用程式：

1. 開啟Microsoft Store應用程式，然後選取右上角的 **[查看更多**] 省略號。
2. 選 **取 [下載和更新]。**
3. 選 **取 [取得更新]**

### <a name="scan-for-and-install-all-windows-updates"></a>掃描並安裝所有Windows更新

移轉之後，可能會有服務和功能更新可供您安裝。 

- 移至 **[設定**  >  **][更新&安全**性>]，然後選取 **[檢查更新]**。
- 如果有任何更新，請加以安裝、重新開機，然後重複此程式，直到您看到下列通知為止：

> [!div class="mx-imgBorder"]
> ![Windows Update「您是最新狀態」通知。](images/wustatus.png)


## <a name="onedrive-for-business"></a>商務用 OneDrive

使用 <a href="/onedrive/onedrive" target="_blank"> 商務用 OneDrive </a> ，輕鬆地在所有工作裝置之間共用工具、記錄和其他檔案。

- OneDrive可讓您在膝上型電腦、Surface Hub桌上型電腦和受Intune管理的行動裝置之間共用工作檔案。 您可以在任何裝置上編輯檔案，而且所有網路連線的裝置都會隨著變更更新。

- 考慮 Surface Hub SSD (128 GB) 的大小，如果您在Surface Hub桌面裝置上設定OneDrive，請確定預設組態是讓檔案保持線上狀態，並在使用檔案時下載檔案。

若要設定OneDrive只在需要時才下載檔案，請將 **[隨選檔案**] 設定為 [儲存空間]，**並在使用檔案時下載檔案**。 如需詳細資訊，請參閱 <a href="/onedrive/files-on-demand-windows" target="_blank"> 查詢和設定Windows </a> 中的檔案隨選狀態。

![OneDrive設定。](images/onedrive.png)

> [!NOTE]
> 您也可以重複這些步驟來設定個人OneDrive但務必節省磁片磁碟機空間，並只視需要下載檔案。

## <a name="sharepoint-and-teams"></a>SharePoint和Teams

SharePoint和Teams通道檔案也可以使用 OneDrive 同步處理 引擎，在本機同步處理到桌面裝置，例如膝上型電腦和 Surface Hub。

若要使用 OneDrive 同步處理 應用程式將內部公司檔案同步至本機磁片磁碟機：

1. 移至SharePoint網站，並流覽至您想要從本機裝置檢視或編輯之檔案的最上層檔目錄。

2. 選取SharePoint功能區頂端的 [**同步**處理] 按鈕。

3. 在快顯視窗上選取 [**開**啟 **]。此網站正嘗試開啟Microsoft OneDrive**。

4. 選取工作列右下方的OneDrive圖示，確認SharePoint檔案已同步處理至本機磁片磁碟機。

5. 確認組態已設定為讓檔案保持線上狀態，並只在您使用檔案時下載檔案：

    1. 開啟檔案總管。
    
    2. 流覽至 ，然後以滑鼠右鍵按一下您的SharePoint名稱;例如**Contoso \ \<SharePoint Document Folder Name\> **。
    
    3. 選 **取 [釋放空間]**。
    
    4. [狀態] 資料行會顯示檔案和資料夾的狀態。 如需詳細資訊，請參閱 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> 使用 OneDrive 同步處理 客戶 </a> 端同步SharePoint檔案。
    
6. Teams通道檔案會儲存在SharePoint網站中，具有相同的SharePoint檔功能，包括版本歷程記錄和同步處理至本機桌面裝置。 若要同步Teams通道檔案：

    1. 流覽至感興趣的Teams通道，然後選取頂端的 [**檔案]** 索引標籤。 然後選取 **[同步]**。檔案將會開始同步處理，並顯示在**桌面 \ Contoso \ \<name of the Teams Channel\> **的檔案總管中。
    
    2. 使用您用來同步處理SharePoint網站的相同程式，將檔案保留在雲端中，並且只在您使用檔案時才下載，方法是點選並按住或以滑鼠右鍵按一下Teams通道名稱上的檔案總管，然後選取 [**釋出空間]**。

## <a name="surface-hub-pen-settings"></a>Surface Hub筆設定

**配對藍牙 Surface Hub筆**

配對手寫筆以將手寫筆韌體保持在最新狀態、設定畫筆快捷方式，以及在藍牙裝置設定頁面或 Surface 應用程式中取得電池計量資訊：

1. 選**取 [開始**  >  **設定**  >  **][裝置]**。

2. 選**取 [新增藍牙或其他裝置]**。

3. 選擇 **[藍牙**]。

4. 移除畫筆尾按鈕並搖動以中斷電池連線。

5. 重新開啟端點並按住端點，直到配對 LED 閃爍為止。

6. 在Surface Hub 藍牙設定中，選擇 **[Surface Hub 2 手寫筆]**。

7. 完成配對作業。 

8. 如果配對不成功，請嘗試再次配對畫筆。 如果無法運作，您可以藉由確認畫筆在 Whiteboard 應用程式中運作，來測試電池是否已充電。 如果沒有，請更換電池，然後嘗試再次配對畫筆。  如有必要，請重新開機裝置，然後再試一次。

**設定畫筆快捷方式**Surface Hub筆有一個有時稱為「尾按」的快捷方式按鈕。 設定快捷方式需要您先配對畫筆，如先前所述。

1. 搜尋 [畫筆]，然後選**取 [畫筆& Windows Ink設定]**。

2. 在接近頁面底部的附近，選取 [手寫筆快捷方式] 以開啟對話方塊，如下所示：

   ![畫筆快捷方式。](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>相機設定

您可以將相機掛接在裝置的頂端或任一側。 如果您使用具有桌面獨立式的中樞而非購物車，或在中樞附近，請將相機掛接在一個位置，以優化相機角度。 相機不會自動旋轉，因此您需要有 2mm 的十六進位金鑰，才能手動旋轉相機。 

如需如何側載相機並手動旋轉相機的詳細資訊，請參閱 <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> Surface Hub 2S 相機鏡頭方向 </a> 。

## <a name="windows-hello-configuration"></a>Windows Hello組態

執行 Windows 10/11 Pro 或 Enterprise 的 Surface Hub 2S 可讓您使用完整的 Win32 傳統型應用程式套件，以及生物特徵辨識Windows Hello選項。 Surface Hub 2 指紋辨識器配件可以插入裝置上的任何 USB-C 埠。 

若要排序 Surface Hub 2 指紋辨識器或檢視技術規格，請參閱 (surface-hub-2-essential-add-ons.md「 target=」_blank「>Surface Hub 2 </a> 上的 Windows 10 專業版 和 Enterprise 的基本附加元件。 

插入指紋辨識器之後，請選取 **[開始**  >  **設定**  >  **][帳戶**  >  ][**登入選項**  >  **Windows Hello [指紋**] 以註冊您的指紋。

使用Windows Hello認證裝置進行臉部辨識。 Surface Hub 2S 相機不支援Windows Hello臉部辨識。

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>在工作列上啟用鎖定畫面快捷方式圖示

若要將圖示新增至工作列，以啟用類似 Windows-L 鍵盤快速鍵的單點螢幕鎖定： 

1.  點選並按住桌面，或以滑鼠右鍵按一下桌面，選取 **[新增**  >  ][hortcutBrowseDesktopOKNext****  >  ****  >  ****  >  ****  >  **]**。

1.  提供快捷方式的名稱，例如 **[鎖定我的電腦**]，然後選取 [ **完成]**。

1.  以滑鼠右鍵按一下或點選並按住桌面上新建立的快捷方式，然後選取 [ **屬性]**。 在 [ **快捷方式] 索引卷** 標的 [ **目標** ] 欄位中輸入下列內容： **Rundll32.exe User32.dll，LockWorkStation**

1.  選取 [ **變更圖示** ] 按鈕，然後流覽至 ** [C:\Windows\System32\imageres.dll** ]，然後選取要使用的圖示。 

    請參閱下列範例：

    ![選擇圖示。](images/lock.png)
    
1.  選取 **[確定** ] 以儲存快捷方式。

1.  以滑鼠右鍵按一下或點選並按住快捷方式，然後選取 **[釘選到工作列]**。

1. 將鎖定快捷方式釘選到工作列之後，您可以從桌面刪除它。

## <a name="applications"></a>應用程式


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

若要安裝Microsoft Whiteboard：

 - 選取工作列右下角的**Windows Ink 工作區**圖示，然後下載**Whiteboard**。
 
   ![筆跡工作區。](images/ink.png) 

或者，您可以從Microsoft Store安裝 Whiteboard：

1. 開Microsoft Store應用程式並搜尋**Whiteboard**。

2. 選擇 **[否]，感謝** 您跨裝置登入並使用。

3. 將白板釘選到工作列。

### <a name="surface-app"></a>Surface 應用程式

1. 在Microsoft Store中，搜尋**Surface**。

2. 將 [ **在篩選時可用** ] 設定為 [ **所有裝置]**。

3. 安裝 **Surface** 應用程式。 這應該是第一個列出的應用程式。 您可能需要將 MSA 與市集建立關聯，才能安裝應用程式。

4. 將 **Surface** 應用程式釘選到工作列。

### <a name="snip--sketch"></a>剪取與繪圖

1. 開啟 **Snip & Sketch** 應用程式，並將它釘選到工作列。

2. 選取右上角的省略號，然後選**取 [設定]**。

3. 在**設定**中，開啟 **[自動複製到剪貼簿**]、[儲存**程式碼片段**] 和 [**多個視窗** (選擇性) 。

### <a name="microsoft-office"></a>Microsoft Office

1. 開啟 <a href="https://portal.office.com/account#installs" target="_blank"> Office 入口網站 </a> ，並安裝您想要的應用程式。

2. 將所需的Office應用程式釘選到工作列。

3. 如果已安裝Outlook，請務必將Outlook OST 設定為僅儲存過去兩周的快取。 這將大幅減少磁片使用量和設定時間。

    - 選**取 [檔案**  >  **][帳戶設定**]，然後選取您的帳戶。
    
    - 選**取 [變更**]，並將 [**使用快取Exchange模式] 的**滑杆設定為 14 天。

### <a name="microsoft-teams"></a>Microsoft Teams

1. 下載並安裝 <a href="https://teams.microsoft.com/downloads" target="_blank"> Microsoft Teams </a> 。

2. 將設定設定為自動啟動應用程式 (選擇性) 。

3. 將Teams釘選到工作列。

4. 請考慮減少裝置上的Teams通知，以避免在選擇性)  (干擾。

   ![Teams通知。](images/teams.png)

### <a name="connect-app"></a>連線應用程式

> [!IMPORTANT]
> 在 Windows 10 2004 版和更新版本中，預設不會安裝使用 Miracast 進行無線投影的連線應用程式，但可作為選擇性功能使用。 如果您已安裝 (或更新為) Windows 2004 版或更新版本，您可能會在 [投影至此電腦] 畫面的設定中看到下列內容：

![Project到此電腦。](images/sh2-project.png) 


1. 若要從 [投影至此電腦] 設定頁面安裝應用程式，請選取 **[選用功能**  >  ][**新增功能**]，然後安裝**無線顯示**器應用程式。

2. 在 [**某些Windows和 Android 裝置可以投影到這部電腦，當您說它沒問題時**，請選擇：

    - 如果裝置不在公司網路上，**則可在任何地方使用**。
    - 否則，請選擇 **[可在安全網路上隨時隨地使用]**。
    
3. 在 **[要求投影至此電腦**] 底下，選擇 [ **僅限第一次]**。

4. 在 **[需要 PIN 以進行配對] 下**，選擇 [ **永不]**。

5. 若要啟動應用程式並將它釘選到工作列，請搜尋**連線**。

6. 開啟應用程式。 當應用程式開啟時，以滑鼠右鍵按一下工作列上的連線應用程式圖示，然後選取 **[釘選到工作列]**。

7. 然後關閉連線應用程式。 除非應用程式至少執行一次 **，否則Project到此電腦**可能無法運作。

不在公司網路上時的建議設定：

![設定在家。](images/project1.png)

公司網路上的建議設定：

![設定工作。](images/project2.png)

### <a name="your-phone"></a>您的手機

**預設會在 Windows 10**上安裝您的電話應用程式。 如果不存在，您也可以從 Windows Store 安裝它。

如需設定應用程式的相關資訊，請參閱 <a href="https://www.windowscentral.com/how-set-your-phone-windows-10" target="_blank"> 如何在Windows 10上設定您的電話，以及在您的電腦與手機 </a> 之間同步處理資料。 另請參閱 <a href="https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10" target="_blank"> 如何修正 Windows 10 上您電話應用程式的 </a> 常見問題。

###  <a name="fancy-zones"></a>花式區域


**花式區域**是 GitHub 上稱為 <a href="https://github.com/microsoft/PowerToys/releases" target="_blank"> PowerToys </a> 工具集合的一部分。 這是在Surface Hub 2 上使用螢幕實際資產的絕佳方式，方法是讓您能夠在顯示器 (「區域」) 上定義固定版面配置，然後選取要在每個區域中執行的應用程式。 


[PowerToys wiki](https://github.com/microsoft/PowerToys/wiki)有如何使用和自訂每個工具的指示，包括[FancyZones](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)。 概括而言， 安裝PowerToys之後，您可以選取或建立自訂版面配置，然後按住下移鍵，然後拖曳或使用鍵盤按鍵將執行中的應用程式移至特定區域。 使用藍牙或 USB 鍵盤和滑鼠有助於解決此問題，或者您可以使用螢幕上的觸控式鍵盤和觸控板。

**Power Toys 秘訣**
- 若要在GitHub上接收PowerToys發行更新的電子郵件通知，請按一下[頁面](https://github.com/microsoft/PowerToys/releases)頂端的 [註冊] 按鈕。
- 安裝PowerToys之後，您可以收到Windows通知和/或下載並安裝最新的更新，方法是設定PowerToys設定**自動將更新下載**至開啟。
- 若要進入PowerToys設定，請選取工作列上的 [執行中**應用程式**]，然後以滑鼠右鍵按一下或按住PowerToys圖示，直到功能表出現為止。 選取 [設定]。
- 在 [PowerToys設定] 頁面底部，將 [**自動下載更新**] 開啟。
- 當更新發行時，會出現Windows通知，讓您選擇何時安裝更新。


### <a name="edge-chromium-browser"></a>Edge Chromium瀏覽器

下載並安裝新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium瀏覽器 </a> 。


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub硬體診斷工具

Surface Hub <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> 硬體診斷工具 </a> 可從Microsoft Store免費取得。 此工具的設計目的是要協助您確定Surface Hub會以最佳效能執行。 其中包含測試，以判斷您的韌體是否為最新狀態並正確設定。 互動式測試可讓您確認基本功能如預期般運作。 如果遇到問題，可以將結果儲存起來，與 Surface Hub 支援小組分享。 按一下連結以從Microsoft Store安裝它，然後將應用程式釘選到工作列。

## <a name="additional-settings"></a>其他設定

### <a name="pen-tail-select-to-launch-whiteboard"></a>手寫筆尾選取以啟動白板

1. 搜尋 **[畫筆**]，然後選**取 [畫筆& Windows Ink設定]**。

2. 在接近頁面底部的 **[畫筆] 快捷方式**下，將 **[選取一次**] 設定**為 [Microsoft Whiteboard]**。 

### <a name="power-management"></a>電源管理

有數個電源設定可用來在 Surface Hub 2 上使用 Windows 10/11 Pro或Enterprise獲得最佳體驗。 這包括螢幕和電腦逾時，以及它們如何與 Doppler) 、螢幕保護裝置和密碼保護 (內建人類目前狀態偵測互動，以及適當時如何傳遞適用于膝上型電腦/桌上型電腦使用者的群組原則電源設定。

Windows 10/11 Pro或Surface Hub 2 上的Enterprise，可讓螢幕透過觸控、滑鼠和鍵盤動作，以及 Doppler) 內建的人類佔用量偵測 (進入睡眠狀態。 根據預設會啟用人類佔用量偵測，但如有需要，可以在 UEFI 中停用，方法是切換 Surface UEFI 設定器工具中的裝置選項作為初始移轉的一部分，或建置並套用更新的 UEFI 組態套件。 

**電源管理：螢幕和電腦睡眠設定**

1. 選取 **[開始**  >  **設定**  >  ][系統 **][**  >  **&睡眠]**。

2. 將電源模式滑杆設定為 **[最佳效能]**。

3. 根據您的喜好設定螢幕和睡眠值，同時考慮偵測到移動時喚醒裝置的 Doppler 目前狀態偵測。 因此，最佳做法是將 [螢幕] 設定為 [ **在 2 小時後關閉** ]，並將電腦設定為 [ **在 4 小時後關閉]。**

**電源管理：螢幕保護裝置**

1. 搜尋 **[鎖定畫面** ] 並開啟 **[鎖定畫面設定]**。

2. 根據您的喜好設定 **螢幕逾時設定** 和 **螢幕保護裝置設定** 。 建議的預設值為：

   - 螢幕保護裝置以 (無) 或您選擇的螢幕保護裝置。
   - 等候時間為 15 分鐘。
   - 在繼續時，顯示登入畫面。


**電源管理：群組原則**

執行下列程式之前，請先洽請 IT 部門核准，以從全域電源管理原則排除Surface Hub 2S 裝置。 某些電源管理設定可以停用目前狀態偵測函式。

1. 搜尋 **軟體中心** 並加以開啟。

2. 選 **取 [選項]**。

3. 展開 **[電源管理]**  ，然後選取 [ **不要將我的 IT 部門的電源設定套用到這部電腦]**。

   ![軟體設定。](images/soft-cntr.png)

### <a name="storage-sense"></a>儲存空間感知器

Surface Hub 2 具有 128 GB 的本機儲存體 SSD，因此必須在正常使用期間考慮使用儲存量值。  若要設定 儲存體 Sense：

1.  搜尋 **[系統設定**] 底下的儲存體 **設定**。

2.  在 **[設定] 底**下，選取 [**開啟儲存體感知器**] 以開**啟 [儲存體**設定] 頁面。

3.  將 [儲存體 Sense] 開**啟**。

4.  選**取 [設定 儲存體 Sense] 或立即執行它**，並設定設定以盡可能讓檔案保持連線 (，因為磁片磁碟機空間) 有限。

建議的設定：

- 執行 儲存體 Sense = 每天。
- 刪除我的應用程式未使用的暫存檔 = 每隔 14 天至少 () 。
- 如果檔案已經存在超過 = 30 天，請刪除 [我的下載] 資料夾中的檔案。
- OneDrive：如果未開啟超過 = 30 天，內容才會變成線上。

### <a name="tablet-mode"></a>平板電腦模式

如有協助工具需求，請開啟 Tablet 模式。


### <a name="sound-settings"></a>音效設定

1. 搜尋 **[音效設定]** ，然後開啟此頁面。

2. 選取右側**的 [音效主控台**]，然後選取 [**音效] 索引**標籤。

3. 在 **[程式事件]** 底下 **，將 [裝置連線**] 和 **[裝置中斷聯**機] 設定為 **[無]**。

### <a name="silence-notifications"></a>無聲通知

1. 搜尋 **[焦點協助** ]，然後開啟此頁面。

2. 選取 **[僅警示]**。 這可避免常數通知飛出視窗。

### <a name="disk-cleanup"></a>磁碟清理

1. 搜尋磁 **盤清理** 並開啟此應用程式。

2. 在 **[要刪除的檔案] 下**，選取您想要刪除的檔案。 

3. 另選取 **[清除系統檔案]**。

## <a name="complete-and-verify"></a>完成並驗證

1. 掃描並安裝所有Windows更新。

2. 更新群組原則。

   1. 在提升許可權的命令提示字元中，輸入 **gpupdate /force /boot /wait：0**。
   
3. 重新開機裝置。

4. 驗證工作列應用程式。

   - 連線應用程式
   - 鎖定圖示
   - 剪取與繪圖
   - 如果適用，Teams () 
   - 如果適用，Office應用程式 () 
   - Surface 應用程式
   - 白板
    
5. 確認目前狀態偵測。

   - 目前狀態偵測將會是系統匣中的綠色圖示。
    
6. 確認已使用 連線 應用程式啟用此電腦的投影。 設定**Project至此電腦**設定之後，請至少執行連線應用程式一次。  (之後，連線應用程式不需要執行，即可投影到 Surface Hub.) 

7. 確認電源和睡眠設定。

    - 螢幕保護裝置：15 分鐘，設定為 (無) 、Mystify 或空白;請確定已選取要求密碼的核取方塊。
    - 畫面： **在 2 小時後關閉**。
    - 電腦：  **在 4 小時後關閉**。
    
8. 確認Windows Hello正常運作。

9. 確認您的設定已停用同步處理。

10. 確認啟動應用程式。

> [!TIP]
> 安裝和設定Windows 10之後，Surface Hub 2S 的管理方式就如同任何其他Windows 10或Windows 11裝置一樣。

## <a name="related-topics"></a>相關主題

<a href="surface-hub-2s-migrate-os.md" target="_blank"> 在 Surface Hub 2 上移轉至 Windows 10/11 Pro 或 Enterprise</a>
