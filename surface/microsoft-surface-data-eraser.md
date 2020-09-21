---
title: Microsoft Surface Data Eraser (Surface)
description: 了解 Microsoft Surface Data Eraser 工具能如何協助您安全地抹除 Surface 裝置上的資料。
ms.assetid: 8DD3F9FE-5458-4467-BE26-E9200341CF10
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: tool, USB, data, erase, 工具, 資料, 清除
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
audience: itpro
ms.date: 09/18/2020
ms.openlocfilehash: dc1a9b4480f37af6d74699a2e693ef8d5318da76
ms.sourcegitcommit: 8bd03770279d5e53446436781226ffd51eeec916
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/18/2020
ms.locfileid: "11029227"
---
# Microsoft Surface Data Eraser


了解 Microsoft Surface Data Eraser 工具能如何協助您安全地抹除 Surface 裝置上的資料。

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) 是可以從 USB 磁碟機開機的工具，讓您能夠安全抹除相容 Surface 裝置上的所有資料。 Microsoft Surface Data Eraser USB 磁碟機僅須具備從 USB 開機的能力。 使用提供的精靈 (Microsoft Surface Data Eraser Wrapper) 輕鬆就能建立 USB 隨身碟，且有易於使用的簡易圖形介面，不需要命令列。 如需深入了解資料抹除功能及 Microsoft 在 Surface 維修過程中所使用的做法，請參閱[將您的 Surface 寄回維修時保護您的資料](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy)。

>[!IMPORTANT]
>Microsoft Surface Data Eraser 會依據 [NIST 特殊發佈 800-88 修訂版 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) 中的授權，使用 NVM Express (NVMe) 格式命令來清除資料。 

相容的 Surface 裝置包括：

- Surface Book (所有版本) 
- 表面移 (所有版本) 
- Surface Pro X (所有版本) 
- Surface 膝上型電腦 (所有版本) 
- Surface Studio (所有版本) 
- Surface Pro 2 及更新版本
- 在 Surface Hub 2 上的 Windows 10 專業版與企業版

某些 Microsoft Surface Data Eraser 可發揮作用的情況包括：

-   準備將 Surface 裝置寄回維修

-   解除將從企業或組織用途移除的 Surface 裝置

-   將 Surface 裝置供新部門或新使用者重複使用的用途

-   為用於機密資料的裝置重新安裝映像的標準做法

>[!NOTE]
>第三方裝置、執行 Windows RT 的 Surface 裝置 (包括 Surface 和 Surface 2)，以及 Surface Pro，皆與 Microsoft Surface Data Eraser 不相容。

>[!NOTE]
>因為執行 Microsoft Surface Data Eraser 需要能夠從 USB 開機，如果裝置未設定成可從 USB 開機，或裝置無法成功開機或 POST，則無法使用 Microsoft Surface Data Eraser。

>[!NOTE]
>Surface Studio 和 Surface Studio 2 上的 [表面資料] 橡皮擦可能需要長達6分鐘的時間才能開始進行 WinPE，然後才能進行磁片擦除。


## 如何建立 Microsoft Surface Data Eraser USB 磁碟機


若要建立 Microsoft Surface Data Eraser USB 磁碟機，請先使用本文章開頭提供的連結從 Microsoft 下載中心安裝 Microsoft Surface Data Eraser 安裝工具。 您不需要 Surface 裝置來建立 *USB* 磁碟機。 下載安裝檔到電腦之後，請按照下列步驟安裝 Microsoft Surface Data Eraser 建立工具：

1.  執行您從 [Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=46703)下載的 DataEraserSetup.msi 安裝檔。

2.  選取接受授權條款的核取方塊，然後按一下 **\[安裝\]**。

3.  按一下 **\[完成\]** 來關閉 Microsoft Surface Data Eraser 設定視窗。

安裝建立工具之後，按照下列步驟建立 Microsoft Surface Data Eraser USB 磁碟機。 在您開始這些步驟之前，請確定您已連接 4 GB 或更大的 USB 3.0 磁碟機到電腦。

1. 從開始目錄或開始畫面啟動 Microsoft Surface Data Eraser。

2. 按一下 **\[建立\]** 來開始 Microsoft Surface Data Eraser USB 的建立程序。 

3. 按一下 **\[開始\]** 以確認您有大小至少為 4 GB 的 USB 磁碟機，如圖 1 所示。

   ![啟動 Microsoft Surface Data Eraser 工具](images/dataeraser-start-tool.png "Start the Microsoft Surface Data Eraser tool")

   *圖 1. 啟動 Microsoft Surface Data Eraser 工具*
4.  在 [**架構選取範圍**] 頁面中，選擇 [適用于 Surface Pro X 的大多數 surface 裝置或**ARM64** ] 的 [ **x64** ]，如圖2所示。 選取 **\[繼續\]**。

    ![結構選取](images/dataeraser-arch.png "Architecture Selection")<br>
       *圖 2. 選取裝置架構*
    

4. 從 [ **Usb 拇指磁片磁碟機選項** ] 頁面選取您選擇的 usb 磁片磁碟機，如圖3所示，然後按一下 [ **開始** ] 以開始 USB 建立程式。 將會格式化您選取的磁碟機，且其中的資料將會遺失。

   >[!NOTE]
   >如果 \[開始\] 按鈕已停用，請檢查您的抽取式磁碟機總容量至少為 4 GB。
  
   ![選擇 USB 磁碟機](images/dataeraser-usb-selection.png "USB thumb drive selection")

   *圖 3. 選擇 USB 磁碟機*

5. 建立程序完成之後，則 USB 磁碟機已經格式化且所有二進位檔都已經複製到其中。 按一下 **\[成功\]**。

6. 顯示 **\[恭喜\]** 畫面之後，即可退出並移除 USB 磁碟機。 這個 USB 磁碟機現在可插入 Surface 裝置，從其開機並抹除該裝置上的所有檔案。 按一下 [ **完成** ] 以完成 USB 建立進程，如圖4所示。

   ![Surface Data Eraser USB 建立程序](images/dataeraser-complete-process.png "Surface Data Eraser USB creation process")

   *圖 4. 完成 Microsoft Surface Data Eraser USB 建立程序*

7. 按一下 **\[X\]** 來關閉 Microsoft Surface Data Eraser。

## 如何使用 Microsoft Surface Data Eraser USB 磁碟機


建立 Microsoft Surface Data Eraser USB 磁碟機之後，您可以遵循下列程序將支援的 Surface 裝置從該 USB 磁碟機開機：

1. 將可開機的 Microsoft Surface Data Eraser USB 磁碟機插入支援的 Surface 裝置。

2. 將您的 Surface 裝置從 Microsoft Surface Data Erase USB 隨身碟開機。 若要將您的裝置從 USB 隨身碟開機，請依照下列步驟執行︰

   a. 將您的 Surface 裝置關機。

   b. 長按 **\[降低音量\]** 按鈕。

   c. 按下並放開 **\[電源\]** 按鈕。

   d. 放開 **\[降低音量\]** 按鈕。
    
   >[!NOTE]
   >如果您的裝置無法使用這些步驟開機至 USB，您可能需要開啟 Surface UEFI 中的 **\[Enable Alternate Boot Sequence\] (啟用替代開機順序)** 選項。 您可以在[管理 Surface UEFI 設定](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)中深入了解Surface UEFI 開機設定。

3. 當 Surface 裝置啟動時，會顯示 **SoftwareLicenseTerms** 文字檔，如圖5所示。

   ![使用 Microsoft Surface Data Eraser USB 磁碟機開機](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *圖 5. 使用 Microsoft Surface Data Eraser USB 磁碟機開機*

4. 閱讀軟體授權條款，然後關閉記事本檔案。

5. 輸入 **Accept** (接受) 或 **Decline** (拒絕) 來接受或拒絕軟體授權條款。 您必須接受授權條款才能繼續。

6. Microsoft Surface Data Eraser 指令碼會偵測出現在您的 Surface 裝置中的存放裝置，並顯示原生存放裝置的詳細資訊。 若要繼續，按 **\[Y\]** (這個動作會執行 Microsoft Surface Data Eraser，並將所有資料從存放裝置移除)，或按 **\[N\]** (這個動作會將裝置關機而且不移除資料)。

   >[!NOTE]
   >Microsoft Surface Data Eraser 工具會以安全且無法復原方式刪除所有資料，包括將裝置開機所需的 Windows 作業系統檔案。 若要將已使用 Microsoft Surface Data Eraser 清除的 Surface 裝置開機，您必須重新安裝 Windows 作業系統。 若要移除 Surface 裝置的資料，而不移除 Windows 作業系統，您可以使用 **\[重設您的電腦\]** 功能。 不過，這無法防止以鑑證或資料修復功能復原您的資料。 請參閱 [Windows 10 中的復原選項](https://support.microsoft.com/help/12415/windows-10-recovery-options)以取得詳細資訊。

   ![顯示將要清除的磁碟分割](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *圖 6. Microsoft Surface Data Eraser 中會顯示將要清除的磁碟分割*

7. 如果您在步驟 6 按下 **\[Y\]**，因為資料清除程序之破壞性，系統會顯示額外的對話方塊以確認您的選擇。

8. 按一下 **\[Yes\]** 按鈕以繼續清除 Surface 裝置上的資料。

   >[!NOTE]
   >在 Surface Data Eraser USB 磁碟機上執行 Surface Data Eraser 時，**SurfaceDataEraserLogs** 資料夾中會產生記錄檔。

## 變更與更新

Microsoft 會定期更新 Microsoft Surface Data Eraser。 如需有關每個新版本所提供之變更的詳細資訊，請參閱下列各項：

### 3.33.139
*發行日期：2020年9月9日*

這個版本的 Surface 資料橡皮擦包含錯誤修正，並新增支援： 

- 重新設計架構以減少更新新產品發行的需求
- 提供新工具更新通知
- 遙測新增
- 在 Surface Hub 2 上的 Windows 10 專業版與企業版


### 3.30.139
*發行日期： 11 2020 年5月11日*

這個版本的 Surface Data 橡皮擦會新增下列各項的支援： 
- Surface Book 3
- 表面移2
- 新的 SSD 在 Surface 中轉中

### 3.28.137
*發行日期：2019年11月11日* 此版本的表面資料橡皮擦：

- 包含錯誤修正

### 版本3.21.137
*發行日期：2019年10月 21* 日這個版本的 Surface 資料橡皮擦是針對 x86 編譯，並新增下列裝置的支援：

- 支援 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3

### 版本3.2.78。0
*發行日期：2018年12月4日*

此版本的表面資料橡皮擦：

- 包含錯誤修正


### 版本3.2.75。0
*發行日期：2018年11月12日*

此版本的表面資料橡皮擦：

- 將支援新增至 Surface Studio 2
- 修正 SD 記憶卡的相關問題

### 版本3.2.69。0
*發行日期：2018年10月12日*

此版本的表面資料橡皮擦會增加下列專案的支援：

- Surface Pro 6
- Surface Laptop 2

### 版本3.2.68。0
此版本的 Microsoft Surface Data Eraser 新增下列支援：

- Surface Go


### 版本3.2.58。0
此版本的 Microsoft Surface Data Eraser 新增下列支援：

- 針對 Surface Pro 和 Surface 膝上型電腦裝置 (磁片磁碟機) 的其他儲存裝置


### 版本 3.2.46.0
此版本的 Microsoft Surface Data Eraser 新增下列支援：

- 配備 LTE Advanced 的 Surface Pro


### 版本 3.2.45.0

此版本的 Microsoft Surface Data Eraser 新增下列支援：

- Surface Book 2

- Surface Pro 1TB

   >[!NOTE]
   >Surface Data Eraser v3.2.45.0 和更新版本可以在裝置顯示兩個不同 512GB 磁碟區，或嘗試部署或安裝 Windows 10 時發生錯誤的案例中，用來還原使用 1TB 儲存選項的 Surface Pro 或 Surface 膝上型電腦裝置。 如需詳細資訊，請參閱 [Surface Pro 型號 1796 和 Surface 膝上型電腦 1TB 顯示兩個磁碟機](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives)。


### 版本 3.2.36.0

此版本的 Microsoft Surface Data Eraser 新增下列支援：

- Surface Pro

- Surface 膝上型電腦

>[!NOTE]
>Microsoft Surface Data Eraser USB 磁碟機建立工具無法在 Windows 10 S 上執行。若要抹除 執行 Windows 10 S 的 Surface Laptop，您必須先在安裝 Windows 10 專業版或 Windows 10 企業版的另一部電腦上建立的 Microsoft Surface Data Eraser USB 磁碟機。
