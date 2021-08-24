---
title: 設定 Windows 10 專業版或 Surface Hub 2 企業版
description: 本文包含建議，以確保使用個人化大型螢幕觸控和觸控筆電腦時獲得最佳體驗。
keywords: Surface Hub、Windows 10、桌面、安裝、組
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
ms.openlocfilehash: 5bb207823abb462179faf72810354885050dc25f
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911228"
---
# <a name="configure-windows-10-pro-or-enterprise-on-surface-hub-2"></a>設定 Windows 10 專業版或 Surface Hub 2 企業版

完成移至 Windows 10 專業版 或 Enterprise 的安裝程式之後，您可以執行下列步驟，在 Surface Hub 2 上設定應用程式和設定。 建議您執行這些步驟，以確保使用這個個人化的大型螢幕觸控和觸控筆電腦時獲得最佳體驗。

執行這些步驟時，您可能會發現使用有線或無線鍵盤和滑鼠很有用。

## <a name="configure-system-settings"></a>設定系統設定

1. 使用在裝置上具有本地系統管理員許可權的帳戶來登錄。  

    - 在 Azure AD 加入的裝置上，執行 Azure AD 加入的使用者會自動新加入到本地系統管理員群組。 Azure AD 全域系統管理員和 Azure AD 裝置系統管理員 <a href="https://docs.microsoft.com/azure/active-directory/devices/assign-local-admin" target="_blank"> 也是本地系統管理員 </a> 。 
    
    - 您可以在命令提示符中輸入 net **localgroup** 系統管理員，以列出具有本地系統管理員許可權的帳戶。
    
2. 使用好用的名稱重新命名裝置，例如 **：username-SHub-Desktop**。

3. 選取**開始**  >  **設定**  >  ****  >  **同步您的設定，** 並**關閉同步**設定。 

    - 此處使用的設定旨在啟用最佳的大螢幕觸控體驗，因此您可能不想同步其他裝置。
    
4. 重新開機裝置。

## <a name="enable-the-touch-keyboard-and-touchpad"></a>啟用觸控式鍵盤和觸控板

1. 選取**開始**設定裝置輸入，然後開啟顯示觸控式鍵盤時，不在平板電腦模式，而且沒有  >  ****  >  ****  >  ** ****附加鍵盤**。

2. 點選並按住工作列，或以滑鼠右鍵按一下工作列，然後選取 [顯示 **觸控式鍵盤按鈕** 及 **顯示觸控板按鈕**。 

    - 觸控式鍵盤對於直接使用者輸入很有説明，而虛擬觸控板可協助精確地選取專案、將工具提示游標停留在畫面上，或以滑鼠右鍵點選並按住。 
    
    - 請參閱以下範例。

      ![觸控設定。](images/touch.png)

3. 將觸控式鍵盤設定為 QWERTY 並浮動。

    1. 選取 **工作列** 上的鍵盤圖示以顯示觸控式鍵盤。
    
    1. 在觸控式鍵盤上，選取左上角的鍵盤圖示以開啟鍵盤設定。
    
    1. 選取頂端列上最後一個鍵盤類型旁的鍵盤類型以啟用 QWERTY，然後選取第二列上最後一個選項來啟用浮動，這對這個大型畫面非常有説明。 請參閱以下範例。

       ![鍵盤設定。](images/kbd.png)
 
4. 設定柔鍵盤設定。

    1. 選取觸控**設定**上的圖示，或搜尋並開啟**輸入設定**。
    
       ![柔鍵盤設定。](images/sh2-softkeyboard.png)

    1. 啟用拼字、輸入和觸控鍵盤下的所有選項。


下列範例顯示軌跡板，可流覽及選取選項。 螢幕小鍵盤是用來搜尋Microsoft Store：

![使用軌跡板。](images/store.png)

## <a name="configure-bluetooth-keyboard-and-mouse-optional"></a>設定藍牙鍵盤和滑鼠 (選) 

連線裝置做為主要裝置，或經常使用Windows或精確作業時，請使用鍵盤和滑鼠。

如果您的裝置Surface Hub靠近電腦，您可以使用滑鼠無邊界，在電腦與Surface Hub <a href="https://aka.ms/mm" target="_blank"> </a> 之間順暢移動。 詳細資訊請參閱 Microsoft 從 Garage 下載 <a href="https://blogs.microsoft.com/ai/microsoft-download-from-the-garage-mouse-without-borders/" target="_blank"> ：滑鼠沒有邊界。 </a>

## <a name="example-of-taskbar-layout"></a>工作列版面配置範例

完成下列步驟以設定/設定 Windows 10 Professional 或 Enterprise 的 Surface Hub 2 之後，建議您使用將最常用的應用程式釘到工作列，以快速單鍵啟動每個應用程式。 以下是工作列外觀的範例：

 ![工作列版面配置。](images/taskblyt.png)
### <a name="update-installed-apps"></a>更新已安裝的應用程式

若要更新所有已安裝的市面應用程式：

1. 開啟 Microsoft Store應用程式，然後選取右上角的**** 查看更多省略號。
2. 選取 **下載和更新。**
3. 選取 **取得更新**

### <a name="scan-for-and-install-all-windows-updates"></a>掃描並安裝所有更新Windows更新
在移Windows 10 Professional或Windows 10 企業版之後，您可能有可供您安裝的維護與功能更新。 

- 請前往**設定**  >  **安全性&更新**>，然後選取**檢查更新**。
- 如果有更新，請安裝更新、重新開機，然後重複執行程式，直到您看到下列通知：

> [!div class="mx-imgBorder"]
> ![Windows更新'您最新狀態'通知。](images/wustatus.png)


## <a name="onedrive-for-business"></a>商務用 OneDrive

您可以使用 商務用 OneDrive，輕鬆地在所有工作裝置之間共用工具、記錄及其他 <a href="https://docs.microsoft.com/onedrive/onedrive" target="_blank"> </a> 檔案。

- OneDrive可讓您在膝上型電腦、電腦Surface Hub和 Intune 管理行動裝置之間共用您的工作檔案。 檔案可以在任何裝置上編輯，所有網路連接裝置都會隨著變更而更新。

- 考慮到 Surface Hub SSD (128 GB) 的大小，如果您在 Surface Hub 桌面裝置上設定 OneDrive，請確定預設設定是讓檔案保持線上並下載檔案。

若要將OneDrive設定為僅于需要時下載檔案，請設定為**** 儲存空間，並在您使用檔案時**下載檔案**。 詳細資訊，請參閱查詢及設定檔案在 Windows <a href="https://docs.microsoft.com/onedrive/files-on-demand-windows" target="_blank"> </a> 中Windows。

![OneDrive設定。](images/onedrive.png)

> [!NOTE]
> 您也可以重複這些步驟來設定個人OneDrive但請務必節省硬碟空間，並只根據需要下載檔案。

## <a name="sharepoint-and-teams"></a>SharePoint Teams

SharePoint和Teams頻道檔案也可以使用電腦引擎，將電腦和 Surface Hub 等桌面OneDrive 同步處理同步處理。

若要將內部公司檔案同步處理至您的本地雲端硬碟，請OneDrive 同步處理應用程式：

1. 前往SharePoint網站，然後流覽至您有興趣從當地裝置檢視或編輯之檔案的頂層檔目錄。

2. 在**功能區頂端**的同步SharePoint選取。

3. 在快顯視窗**上**選取開啟**此網站正嘗試開啟Microsoft OneDrive。**

4. 選取SharePoint右下角的 OneDrive 圖示，確認這些檔案正在同步處理至您的本地磁碟機。

5. 確認設定設定為將檔案保持在線上，並只在使用檔案時下載：

    1. 開啟檔案檔案管理器。
    
    2. 流覽至您的名稱，然後以滑鼠右鍵SharePoint名稱;例如 **，Contoso \ \<SharePoint Document Folder Name\> **。
    
    3. 選取 **釋放空間**。
    
    4. 狀態列會顯示檔案和資料夾的狀態。 詳細資訊，請參閱使用 <a href="https://support.microsoft.com/office/sync-sharepoint-files-with-the-onedrive-sync-client-groove-exe-59b1de2b-519e-4d3a-8f45-51647cf291cd" target="_blank"> SharePoint 同步處理OneDrive 同步處理檔案 </a> 。
    
6. Teams頻道檔案會儲存在SharePoint網站中，具有所有相同的 SharePoint 檔功能，包括版本歷程記錄及同步處理至您的本地桌面裝置。 若要同步Teams頻道檔案：

    1. 流覽至Teams感興趣的頻道，然後**選取頂端的**檔案定位點。 然後選取 同步 **。** 檔案將會開始同步處理，而且將會顯示在桌面**\ Contoso \ 的檔案管理器 \<name of the Teams Channel\> 中**。
    
    2. 使用同步處理 SharePoint 網站時所使用的相同程式，將檔案保留于雲端，並只在使用時下載，請在 Teams 頻道名稱的 [檔案管理器中點選或以滑鼠右鍵按一下，然後選取 [釋放空間）。 ****

## <a name="surface-hub-pen-settings"></a>Surface Hub筆設定

**將筆藍牙 Surface Hub配對**

將觸控筆配對，讓觸控筆的固件保持在最新狀態、設定觸控筆快捷方式，以及取得 藍牙 裝置設定頁面或 Surface 應用程式中的電池充電資訊：

1. 選取**開始**  >  **設定**  >  **裝置**。

2. 選取**新增藍牙裝置**。

3. 選擇**藍牙**。

4. 移除觸控筆尾按鈕並搖動以中斷電池連接。

5. 將蓋放回，然後按住蓋，直到配對的 LED 閃爍。

6. 在 Surface Hub 藍牙 設定中，選擇**Surface Hub 2 支筆**。

7. 完成配對作業。 

8. 如果配對失敗，您可以再次嘗試配對。 如果無法運作，您可以驗證觸控筆在 Whiteboard 應用程式中是否運作，以測試電池是否已充電。 如果沒有，請更換電池，然後再次嘗試將筆配對。 如有需要，請重新開機裝置，然後再試一次。

**設定筆快捷方式**[Surface Hub筆有一個快捷方式按鈕，有時稱為「尾鍵」。 如先前所述，若要進行快速鍵的建立，您需先將筆配對。

1. 搜尋觸控筆，然後選取**筆& Windows Ink設定**。

2. 在頁面底部附近，選取開啟對話方塊的 [筆快捷方式，如下所示：

   ![筆快捷方式。](images/sh2-pen-shortcuts.png)

## <a name="camera-configuration"></a>相機組

您可以將相機安裝在裝置頂端或任一側。 如果您將 Hub 與桌面支架而非購物車一起使用，或接近中樞，請以位置安裝相機，以優化相機角度。 相機不會自動旋轉，因此您必須有 2mm 十六進位鍵，以手動旋轉相機。 

若要瞭解如何側向安裝相機並手動旋轉相機， <a href="https://support.microsoft.com/help/4509729/surface-hub-2s-camera-lens-orientation" target="_blank"> 請參閱Surface Hub相機鏡頭方向 </a> 。

## <a name="windows-hello-configuration"></a>Windows Hello組

Surface Hub 2S Windows 10 企業版可讓 Win32 桌面應用程式的完整套件，以及生物識別Windows Hello選項。 2 Surface Hub指紋閱讀程式配件可以插入裝置上的任何 USB-C 埠。 

若要訂購 Surface Hub 2 指紋閱讀程式或查看技術規格，請參閱 (surface-hub-2-essential-add-ons.md target="_blank">Windows 10 專業版 和 Enterprise Surface Hub 2 的基本附加元件 </a> 。 

插入指紋識別程式之後，選取****[開始設定 [帳戶登錄  >  ****  >  ****  >  **選項**Windows Hello  >  **指紋**以註冊您的指紋。

使用經過Windows Hello的裝置進行臉部識別。 2S Surface Hub相機不支援Windows Hello功能。

## <a name="enable-a-lock-screen-shortcut-icon-on-the-taskbar"></a>啟用工作列上的鎖定畫面快捷方式圖示

若要新增圖示至工作列，以啟用類似 Windows-L 鍵盤快速鍵的一鍵式螢幕鎖定： 

1.  點選並按住或以滑鼠右鍵按一下桌面，**** 選取 [  >  **新增快捷方式**  >  **流覽**  >  **桌面**  >  **確定**  >  **下一步**。

1.  提供快速鍵的名稱，例如 **鎖定我的電腦**， **然後選取**完成 。

1.  以滑鼠右鍵按一下或點選並按住桌面上新建立快速鍵，然後選取 [ **內容**> 。 在快捷方式**選項卡**上，在目標欄位中輸入下列**** 專案 **：Rundll32.exe User32.dll、LockWorkStation**

1.  選取變更 **圖示** 按鈕，然後流覽 **C:\Windows\System32\imageres.dll** 並選取要使用圖示。 

    請參閱下列範例：

    ![選擇圖示。](images/lock.png)
    
1.  選取 **確定** 以儲存快捷方式。

1.  以滑鼠右鍵按一下或點選並按住快捷方式，然後選取 [ **釘選到工作列**。

1. 將鎖定快捷方式釘到工作列之後，就可以從桌面刪除它。

## <a name="applications"></a>應用程式


### <a name="microsoft-whiteboard"></a>Microsoft Whiteboard

若要安裝Microsoft Whiteboard：

 - 選取Windows Ink 工作區**右**下角的圖示，然後下載**Whiteboard**。
 
   ![筆墨工作區。](images/ink.png) 

或者，您也可以從以下選項安裝白板Microsoft Store：

1. 開啟 Microsoft Store應用程式並搜尋**Whiteboard。**

2. 選擇 **不感謝您** 在裝置上登錄和使用。

3. 將 Whiteboard 釘到工作列。

### <a name="surface-app"></a>Surface 應用程式

1. 在 Microsoft Store中，搜尋**Surface**。

2. 將篩選 **上的** 可用設定為 **所有裝置**。

3. 安裝 **Surface** 應用程式。 這應該是第一個列出的應用程式。 您可能需要將您的 MSA 與 Store 關聯，才能安裝應用程式。

4. 將 **Surface 應用程式** 釘到工作列。

### <a name="snip--sketch"></a>剪取與繪圖

1. 開啟 **Snip** &繪圖應用程式，然後釘到工作列。

2. 選取右上角的省略號，**然後選取**設定。

3. 在**設定**中，開啟**** 自動複製到剪貼 (剪**** 貼) 。 ****

### <a name="microsoft-office"></a>Microsoft Office

1. 開啟 Office <a href="https://portal.office.com/account#installs" target="_blank"> </a> 入口網站並安裝您想要的應用程式。

2. 將想要Office應用程式釘到工作列。

3. 如果Outlook，請務必將 OUTLOOK OST 設為只儲存過去兩周的緩存。 這會大量減少磁片使用量和設定時間。

    - 選取**檔案**  >  **帳戶設定，** 然後選取您的帳戶。
    
    - 選取**變更**，將使用 Exchange**模式滑杆設定**為 14 天。

### <a name="microsoft-teams"></a>Microsoft Teams

1. 下載並安裝 <a href="https://teams.microsoft.com/downloads" target="_blank"> </a> Microsoft Teams。

2. 將設定設定設定為自動啟動應用程式 (選項) 。

3. 將Teams釘到工作列。

4. 請考慮減少Teams裝置上的通知，以避免分心 (選擇) 。

   ![Teams通知。](images/teams.png)

### <a name="connect-app"></a>連線應用程式

> [!IMPORTANT]
> 在 Windows 10版本 2004 及更新版本中，連線 應用程式不會預設安裝 Miracast 無線投影，但提供選擇性功能。 如果您已經安裝 (或更新) Windows版本 2004 或更新版本，您可能會在設定中的專案到此電腦畫面上看到下列內容：

![Project此電腦。](images/sh2-project.png) 


1. 若要從 「Projecting to this PC」 設定頁面安裝應用程式，請選取選擇性**功能**新增功能，然後  >  **** 安裝**無線顯示**應用程式。

2. 當您**說Windows時**，在一些裝置和 Android 裝置可以專案到此電腦下，選擇：

    - **如果裝置不在** 公司網路上，則所有位置都可用。
    - 否則，請選擇**安全網路上所有位置的可用 。**
    
3. 在 **邀請專案至此電腦**下，選擇僅 **第一次**。

4. 在 **需要 PIN 進行配對的**下 **，選擇永不**。

5. 若要啟動應用程式並釘上工作列，請搜尋**連線。**

6. 開啟應用程式。 當應用程式開啟時，以滑鼠右鍵按一下工作列上的 連線 應用程式圖示，然後選取 [釘選**到工作列**。

7. 然後關閉連線應用程式。 **Project此電腦**，除非應用程式至少執行一次，否則可能無法使用。

建議在不在公司網路上時進行組組：

![設定在家裡。](images/project1.png)

公司網路上建議的組組：

![設定工作。](images/project2.png)

### <a name="your-phone&quot;></a>您的手機

應用程式**您的手機**預設會安裝在 Windows 10。 如果不存在，您也可以從 Store Windows安裝。

有關設定應用程式的資訊，請參閱如何在 您的手機上Windows 10設定應用程式， <a href=&quot;https://www.windowscentral.com/how-set-your-phone-windows-10&quot; target=&quot;_blank&quot;> 以及如何同步處理電腦與手機之間的資料 </a> 。 另請參閱 <a href=&quot;https://www.windowscentral.com/how-fix-common-problems-your-phone-app-windows-10&quot; target=&quot;_blank&quot;> 如何修正應用程式上的您的手機常見問題 </a> Windows 10。

###  <a name=&quot;fancy-zones&quot;></a>花式區域


**花式**區域是名為 PowerToys 工具集合的一 <a href=&quot;https://github.com/microsoft/PowerToys/releases&quot; target=&quot;_blank&quot;> </a> GitHub。 這是在 Surface Hub 2 上運用螢幕空間的一種很好方式，讓您在顯示器 (&quot;zone") 上定義固定版面配置，然後選取要在每個區域中執行的應用程式。 


Wiki [PowerToys](https://github.com/microsoft/PowerToys/wiki)提供如何使用及自訂每個工具的指示，包括[花式區域](https://github.com/microsoft/PowerToys/wiki/FancyZones-Overview)。 在較高層級 – 安裝PowerToys之後，您可以選取或建立自訂版面配置，然後按住 shift 鍵，然後拖曳或使用鍵盤鍵將執行中的應用程式移至特定區域。 使用藍牙 USB 鍵盤和滑鼠可協助進行這項操作，或者您也可以使用螢幕觸控式鍵盤和觸控板。

**Power toys 秘訣**
- 若要在 PowerToys 收到GitHub更新的電子郵件通知，請按一下頁面頂端的 [註冊」[按鈕](https://github.com/microsoft/PowerToys/releases)。
- 安裝PowerToys之後，您可以Windows通知和/或下載並安裝最新更新，PowerToys**設定將**更新自動下載至。
- 若要取得 [PowerToys設定，請選取工作列上的 [執行**** 應用程式向上鍵，然後以滑鼠右鍵按一下或按住 PowerToys 圖示，直到功能表出現。 選取 「設定」。
- 在設定頁面PowerToys，將**下載更新自動開啟**。
- 更新發行後，系統Windows通知，讓您選擇何時安裝更新。


### <a name="edge-chromium-browser"></a>Edge Chromium瀏覽器

下載並安裝新的 <a href="https://www.microsoft.com/en-us/edge?form=MY01BL&OCID=MY01BL" target="_blank"> Edge Chromium瀏覽器 </a> 。


### <a name="surface-hub-hardware-diagnostic-tool"></a>Surface Hub硬體診斷工具

系統 <a href="https://www.microsoft.com/p/surface-hub-hardware-diagnostic/9nblggh51f2g" target="_blank"> Surface Hub硬體診斷工具 </a> 免費Microsoft Store。 此工具的設計可協助確認您的Surface Hub效果最佳。 它包含測試，以判斷您的固件是否為最新且正確配置。 互動式測試可確認基本功能是否如預期一樣正常。 如果遇到問題，可以將結果儲存起來，與 Surface Hub 支援小組分享。 按一下連結以從連結安裝Microsoft Store，然後將應用程式釘到工作列。

## <a name="additional-settings"></a>其他設定

### <a name="pen-tail-select-to-launch-whiteboard"></a>選取筆尾以啟動 Whiteboard

1. 搜尋觸控**筆**，然後選取 **& Windows Ink設定**。

2. 在頁面底部附近的觸控筆快捷方式下****，將**選取**一**次**設為Microsoft Whiteboard。 

### <a name="power-management"></a>Power Management

有幾種電源設定可在第 2 Windows 10 專業版 或 Enterprise上Surface Hub使用。 這包括螢幕和電腦超時，以及它們如何與內建的人體目前狀態偵測 (Doppler) 、螢幕保護裝置程式與密碼保護互動，以及適當時如何針對膝上型電腦/桌面使用者進行分群組原則電源設定。

Windows 10 專業版或 Enterprise 2 上的 Surface Hub 畫面會以觸控、滑鼠和鍵盤動作，以及內建的人體佔用偵測 (Doppler) 來防止螢幕進入睡眠狀態。 人體佔用偵測功能預設為啟用，但如果需要，可以在 UEFI 中停用，在 Surface UEFI Configurationator 工具中切換裝置選項做為初始移移的一部分，或建立並套用稍後的 UEFI 組組套件。 

**Power Management：螢幕和電腦睡眠設定**

1. 選取**開始**  >  **設定**  >  ****  >  **系統電源&睡眠**。

2. 將電源模式滑杆設定為 **最佳效果**。

3. 將螢幕和睡眠值設定為您的喜好設定，同時也會計算偵測到移動時喚醒裝置之 Doppler 目前狀態偵測。 因此，最佳做法是建議將螢幕設定為 **2** 小時後關閉，而電腦在 **4 小時後關閉。**

**Power Management：螢幕保護裝置程式**

1. 搜尋鎖定 **畫面並** 開啟 **鎖定畫面設定**。

2. 將**螢幕超時設定和****螢幕保護裝置程式設定設定**為您的喜好設定。 建議的預設值為：

   - 螢幕保護裝置程式 (無) 或您所選擇的螢幕保護裝置程式。
   - 等候時間到 15 分鐘。
   - 在履歷表上，顯示登入畫面。


**Power Management：群組原則**

執行下列程式之前，請先向 IT 部門進行核准，Surface Hub 2S 裝置從全域電源管理政策中排除。 某些電源管理設定可能會停用目前狀態偵測功能。

1. 搜尋 **軟體中心並** 開啟。

2. 選取 **選項**。

3. 展開 **Power Management，**  然後選取 **不要將 IT**部門的電源設定適用于此電腦。

   ![軟體設定。](images/soft-cntr.png)

### <a name="storage-sense"></a>儲存空間感知器

2 Surface Hub 2 具有 128 GB 的 SSD 供本地儲存空間使用，因此在一般使用期間，必須考慮儲存空間儲存措施的使用方式。  若要設定儲存體感知：

1.  搜尋儲存 **空間設定**，此設定位於 系統 **設定 下**。

2.  在**設定**下，選取**開啟儲存空間感知**，以開啟**儲存體設定**頁面。

3.  將 儲存體**感知功能開啟**。

4.  選取**設定儲存體感知**或現在執行，並設定設定，讓檔案盡可能保持線上 (因為磁碟機空間有限) 。

建議設定：

- 執行 儲存體 Sense = 每天。
- 刪除我的 App 未使用的暫用檔案 = 每 14 天 (至少) 。
- 如果檔案存在超過 = 30 天，請刪除我的下載資料夾中的檔案。
- OneDrive：若未開啟超過 = 30 天，則內容只會變成線上。

### <a name="tablet-mode"></a>平板電腦模式

如果需要協助工具需求，請開啟平板電腦模式。


### <a name="sound-settings"></a>音效設定

1. 搜尋音效 **設定並** 開啟此頁面。

2. 選取 **右邊的** 音效控制台，然後選取的音效 **標籤** 。

3. 在**程式事件下****，將裝置連線****裝置中斷連接至****無**。

### <a name="silence-notifications"></a>靜音通知

1. 搜尋 **焦點輔助，** 然後開啟此頁面。

2. 選取 **僅鬧鐘**。 這樣可避免持續出現通知飛出。

### <a name="disk-cleanup"></a>磁碟清理

1. 搜尋 **磁片清理並** 開啟此應用程式。

2. 在 **要刪除的檔案**下，選取要刪除的檔案。 

3. 另請 **選取 清理系統檔案**。

## <a name="complete-and-verify"></a>完成並驗證

1. 掃描並安裝所有更新Windows更新。

2. 更新群組原則。

   1. 在提升命令提示時，輸入 **gpupdate /force /boot /wait：0**。
   
3. 重新開機裝置。

4. 驗證工作列應用程式。

   - 連線應用程式
   - 鎖定圖示
   - 剪取與繪圖
   - Teams (若適用，) 
   - Office若適用 (應用程式) 
   - Surface App
   - 白板
    
5. 驗證目前狀態偵測。

   - 目前狀態偵測會為系統工作列中的綠色圖示。
    
6. 使用應用程式驗證已啟用此電腦連線。 設定此**Project設定**之後，請至少執行連線應用程式。  (之後，連線應用程式就不需要執行，因此無法Surface Hub.) 

7. 驗證電源和睡眠設定。

    - 螢幕保護裝置程式：15 分鐘，設定為無 (、) 或空白;確認已選取要求密碼的核取方塊。
    - 畫面 **：2 小時後關閉**。
    - 電腦  **：4 小時後關閉**。
    
8. 確認Windows Hello是否正常。

9. 確認已停用同步您的設定。

10. 驗證啟動應用程式。

> [!TIP]
> 安裝並Windows 10之後，Surface Hub管理 2S，就像任何其他裝置Windows 10一樣。

## <a name="related-topics"></a>相關主題

<a href="surface-hub-2s-migrate-os.md" target="_blank"> 移轉到 Windows 10 專業版或 Surface Hub 2 企業版</a>
