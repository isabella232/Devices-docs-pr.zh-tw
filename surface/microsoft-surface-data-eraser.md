---
title: Microsoft Surface Data Eraser (Surface)
description: Microsoft Surface 資料橡皮擦工具可讓您安全地抹除 Surface 裝置的資料。
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
ms.date: 10/06/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e40c967003fc6dd40725e5015c01497eb3fa141a
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449646"
---
# <a name="microsoft-surface-data-eraser"></a>Microsoft Surface Data Eraser

了解 Microsoft Surface Data Eraser 工具能如何協助您安全地抹除 Surface 裝置上的資料。

[Microsoft Surface Data Eraser](https://www.microsoft.com/download/details.aspx?id=46703) 是可以從 USB 磁碟機開機的工具，讓您能夠安全抹除相容 Surface 裝置上的所有資料。 Microsoft Surface Data Eraser USB 磁碟機僅須具備從 USB 開機的能力。 如需深入了解資料抹除功能及 Microsoft 在 Surface 維修過程中所使用的做法，請參閱[將您的 Surface 寄回維修時保護您的資料](https://www.microsoft.com/surface/support/security-sign-in-and-accounts/data-wiping-policy)。

>[!IMPORTANT]
>Microsoft Surface Data Eraser 會依據 [NIST 特殊發佈 800-88 修訂版 1](http://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-88r1.pdf) 中的授權，使用 NVM Express (NVMe) 格式命令來清除資料。

相容的 Surface 裝置包括：

- Surface Laptop Studio
- Surface Book (所有版本) 
- Surface Go (所有版本) 
- Surface Pro X (所有版本) 
- Surface Laptop (所有版本) 
- Surface Laptop Go
- Surface Studio (所有版本) 
- Surface Pro 2 及更高版本
- Surface 3
- Windows 10 專業版 2 Enterprise上的Surface Hub和

某些 Microsoft Surface Data Eraser 可發揮作用的情況包括：

- 準備要送往維修的 Surface 裝置。
- 將 Surface 裝置從公司或組織使用中解除授權。
- 為新使用者重新使用 Surface 裝置。
- 重新映射包含機密資料的裝置。

## <a name="how-to-create-a-microsoft-surface-data-eraser-usb-stick"></a>如何建立 Microsoft Surface Data Eraser USB 磁碟機

安裝建立工具之後，按照下列步驟建立 Microsoft Surface Data Eraser USB 磁碟機。 在您開始這些步驟之前，請確定您已連接 4 GB 或更大的 USB 3.0 磁碟機到電腦。

1. 執行DataEraserSetup.msi從 Microsoft 下載中心下載的 [安裝檔案](https://www.microsoft.com/download/details.aspx?id=46703)。

2. 選取 **建立** 以開始 Microsoft Surface Data Eraser USB 建立程式，如圖 1 所示。

   :::image type="content" source="images/microsoft-surface-data-eraser/fig1-build.png" alt-text="圖 1。 開始使用 Microsoft Surface 資料橡皮擦工具":::<br>
  *圖 1。 開始使用 Microsoft Surface 資料橡皮擦工具*

3. 選取 **繼續** 確認您的 USB 磁碟機至少已連接 4 GB，如圖 2 所示。
   
   :::image type="content" source="images/microsoft-surface-data-eraser/fig2-continue.png" alt-text="圖 2. 確認已連接至少 4 GB 的 USB 磁碟機":::<br>
   *圖 2. 確認已連接至少 4 GB 的 USB 磁碟機*

4. 僅針對**2021 (裝置選擇 x64**) 或更新的裝置，從架構選取頁面選擇適用于 2020 及較舊版本的**x64**或 Surface Pro X 的**ARM64**，如圖-3 所示。** ** 選取 **\[繼續\]**。

   :::image type="content" source="images/microsoft-surface-data-eraser/fig3-select.png" alt-text="圖 3. 選取裝置架構":::

5. 從 USB Thumb Drive 選取頁面選取您所選擇的**USB**磁碟機，如圖 4 所示，然後選取開始建立 USB 程式。** ** 將會格式化您選取的磁碟機，且其中的資料將會遺失。

   :::image type="content" source="images/microsoft-surface-data-eraser/fig4-start.png" alt-text="圖 4. USB 大拇指磁碟機>":::<br>
   *圖 4. 選擇 USB 磁碟機*

  >[!TIP]
   >如果 \[開始\] 按鈕已停用，請檢查您的抽取式磁碟機總容量至少為 4 GB。

6. 建立程序完成之後，則 USB 磁碟機已經格式化且所有二進位檔都已經複製到其中。 選取 **成功**。

7. 顯示 **\[恭喜\]** 畫面之後，即可退出並移除 USB 磁碟機。 這個 USB 磁碟機現在可插入 Surface 裝置，從其開機並抹除該裝置上的所有檔案。 選取 **完成** 以完成 USB 建立程式，如圖 5 所示。

   :::image type="content" source="images/microsoft-surface-data-eraser/fig5-complete.png" alt-text="完成 Microsoft Surface 資料橡皮擦工具":::<br>
   *圖 5. 完成 Microsoft Surface Data Eraser USB 建立程序*

8. 選取 **X** 以關閉 Microsoft Surface 資料橡皮擦。

## <a name="how-to-use-a-microsoft-surface-data-eraser-usb-stick"></a>如何使用 Microsoft Surface Data Eraser USB 磁碟機

建立 Microsoft Surface Data Eraser USB 磁碟機之後，您可以遵循下列程序將支援的 Surface 裝置從該 USB 磁碟機開機：

>[!NOTE]
>Surface Data Eraser Surface Studio 2 Surface Studio最多可能需要 6 分鐘才能啟動到 WinPE，才能進行磁片清除。

1. 將可開機的 Microsoft Surface Data Eraser USB 磁碟機插入支援的 Surface 裝置。

2. 將您的 Surface 裝置從 Microsoft Surface Data Erase USB 隨身碟開機。 若要將您的裝置從 USB 隨身碟開機，請依照下列步驟執行︰

   a. 將您的 Surface 裝置關機。
   b. 長按 **\[降低音量\]** 按鈕。
   c. 按下並放開 **\[電源\]** 按鈕。
   d. 放開 **\[降低音量\]** 按鈕。

   >[!TIP]
   >如果您的裝置無法使用這些步驟開機至 USB，您可能需要開啟 Surface UEFI 中的 **\[Enable Alternate Boot Sequence\] (啟用替代開機順序)** 選項。 您可以在[管理 Surface UEFI 設定](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)中深入了解Surface UEFI 開機設定。

3. 當 Surface 裝置啟動時， **會顯示 SoftwareLicenseTerms** 文字檔，如圖 5 所示。

   ![啟動 Microsoft Surface 資料橡皮擦 USB 棒。](images/data-eraser-3.png "Booting the Microsoft Surface Data Eraser USB stick")

   *圖 5. 使用 Microsoft Surface Data Eraser USB 磁碟機開機*

4. 閱讀軟體授權條款，然後關閉記事本檔案。

5. 輸入 **Accept** (接受) 或 **Decline** (拒絕) 來接受或拒絕軟體授權條款。 您必須接受授權條款才能繼續。

6. Microsoft Surface Data Eraser 指令碼會偵測出現在您的 Surface 裝置中的存放裝置，並顯示原生存放裝置的詳細資訊。 若要繼續，按 **\[Y\]** (這個動作會執行 Microsoft Surface Data Eraser，並將所有資料從存放裝置移除)，或按 **\[N\]** (這個動作會將裝置關機而且不移除資料)。

   >[!CAUTION]
   >Microsoft Surface Data Eraser 工具會以安全且無法復原方式刪除所有資料，包括將裝置開機所需的 Windows 作業系統檔案。 若要將已使用 Microsoft Surface Data Eraser 清除的 Surface 裝置開機，您必須重新安裝 Windows 作業系統。 若要移除 Surface 裝置的資料，而不移除 Windows 作業系統，您可以使用 **\[重設您的電腦\]** 功能。 不過，這無法防止以鑑證或資料修復功能復原您的資料。 請參閱 [Windows 10 中的復原選項](https://support.microsoft.com/help/12415/windows-10-recovery-options)以取得詳細資訊。

   ![系統會顯示要清除的分區。](images/sda-fig5-erase.png "Partition to be erased is displayed")
  
   *圖 6. Microsoft Surface Data Eraser 中會顯示將要清除的磁碟分割*

7. 如果您在步驟 6 按下 **\[Y\]**，因為資料清除程序之破壞性，系統會顯示額外的對話方塊以確認您的選擇。

8. 選取 **是** 以繼續清除 Surface 裝置上的資料。

   >[!TIP]
   >在 Surface Data Eraser USB 磁碟機上執行 Surface Data Eraser 時，**SurfaceDataEraserLogs** 資料夾中會產生記錄檔。

## <a name="changes-and-updates"></a>變更與更新

Microsoft 會定期更新 Microsoft Surface Data Eraser。 如需有關每個新版本所提供之變更的詳細資訊，請參閱下列各項：

### <a name="3421390"></a>3.42.139.0

*發行日期：2021 年 10 月 5 日*

此版本的 Surface Data 橡皮擦包括：

- 2021 的個別選項，以及較新裝置的支援，Surface Laptop Studio、Surface Pro 8 和 Surface Go 3。

### <a name="3391390"></a>3.39.139.0

*發行日期：2021 年 4 月 13 日*

此版本的 Surface Data 橡皮擦包括：

- 支援 Surface Laptop 4

### <a name="2341390"></a>2.34.139.0

*發行日期：2021 年 1 月 15 日*

此版本的 Surface Data 橡皮擦：

- 包含錯誤修正

### <a name="333139"></a>3.33.139

*發行日期：2020 年 9 月 9 日*

此版本的 Surface Data 橡皮擦包含錯誤修正程式，並新增以下支援：

- 架構重新設計，以減少使用新產品版本更新需求
- 新工具更新可用的通知
- 遙測新增專案
- Windows 10 專業版 2 Enterprise上的Surface Hub和

### <a name="330139"></a>3.30.139

*發行日期：2020 年 5 月 11 日*

此版本的 Surface Data Eraser 新增了以下支援：

- Surface Book 3
- Surface Go 2
- Surface Go 中的新 SSD

### <a name="328137"></a>3.28.137

*發行日期：2019 年 11 月 11 日*

此版本的 Surface Data 橡皮擦：

- 包含錯誤修正

### <a name="version-321137"></a>版本 3.21.137

*發行日期：2019 年 10 月 21 日*

此版本的 Surface Data Eraser 已編譯為 x86，並新增下列裝置的支援：

- Surface Pro 7、Surface Pro X 和 Surface Laptop 3

### <a name="version-32780"></a>版本 3.2.78.0

*發行日期：2018 年 12 月 4 日*

此版本的 Surface Data 橡皮擦：

- 包含錯誤修正

### <a name="version-32750"></a>版本 3.2.75.0

*發行日期：2018 年 11 月 12 日*

此版本的 Surface Data 橡皮擦：

- 新增支援至 Surface Studio 2
- 修正 SD 卡的問題

### <a name="version-32690"></a>版本 3.2.69.0

*發行日期：2018 年 10 月 12 日*

此版本的 Surface Data Eraser 新增下列支援：

- Surface Pro 6
- Surface Laptop 2

### <a name="version-32680"></a>版本 3.2.68.0

此版本的 Microsoft Surface Data Eraser 新增下列支援：

- Surface Go

### <a name="version-32580"></a>版本 3.2.58.0

此版本的 Microsoft Surface Data Eraser 新增下列支援：

- 其他儲存裝置 () 裝置Surface Pro Surface Laptop磁片磁碟機

### <a name="version-32460"></a>版本 3.2.46.0

此版本的 Microsoft Surface Data Eraser 新增下列支援：

- 配備 LTE Advanced 的 Surface Pro

### <a name="version-32450"></a>版本 3.2.45.0

此版本的 Microsoft Surface Data Eraser 新增下列支援：

- Surface Book 2
- Surface Pro 1TB

   >[!NOTE]
   >Surface Data Eraser v3.2.45.0 和更新版本可以在裝置顯示兩個不同 512GB 磁碟區，或嘗試部署或安裝 Windows 10 時發生錯誤的案例中，用來還原使用 1TB 儲存選項的 Surface Pro 或 Surface 膝上型電腦裝置。 如需詳細資訊，請參閱 [Surface Pro 型號 1796 和 Surface 膝上型電腦 1TB 顯示兩個磁碟機](https://support.microsoft.com/help/4046105/surface-pro-model-1796-and-surface-laptop-1tb-display-two-drives)。

### <a name="version-32360"></a>版本 3.2.36.0

此版本的 Microsoft Surface Data Eraser 新增下列支援：

- Surface Pro
- Surface 膝上型電腦

>[!NOTE]
>Microsoft Surface Data Eraser USB 磁碟機建立工具無法在 s 上Windows 10執行。若要抹除執行 Surface Laptop S 的 Windows 10，您必須先在另一部電腦上使用 Windows 10/1 Pro 1 或 Windows 10/11 Enterprise 建立 Microsoft Surface Data 橡皮擦 USB 磁碟機。
