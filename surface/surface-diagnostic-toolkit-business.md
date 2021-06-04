---
title: 部署商務用 Surface 診斷工具組
description: 本主題說明如何使用適用于商務的 Surface 診斷工具組。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/15/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 227463e484a6f3b933fc1118d9dec058f93074a8
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271577"
---
# 部署商務用 Surface 診斷工具組

商務 () SDT 的 Microsoft Surface 診斷工具組可讓 IT 系統管理員快速調查、疑難排解及解決 Surface 裝置的硬體、軟體及固件問題。 除了取得裝置健康情況深入資訊以及解決問題的指示之外，您還可以執行診斷測試和軟體修復範圍。 

具體來說，SDT for Business 可讓您：

- [自訂套件。](#preparing-the-sdt-package-for-distribution)
- [使用命令執行應用程式。](surface-diagnostic-toolkit-command-line.md)
- [執行多個硬體測試以進行問題的疑難排解。](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [產生記錄來分析問題。](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [取得對比裝置與最佳設定的詳細報告。](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)


## 主要案例和下載資源 

若要執行 SDT for Business，請下載下表所列的元件。


模式 |  主要案例 | 下載 | 深入了解
--- | --- | --- | ---
桌面模式 |  協助使用者在其 Surface 裝置上執行 SDT，以針對問題進行疑難排解。<br>建立要在一或多個 Surface 裝置上部署的自訂套件，讓使用者可以選取要收集及分析的特定記錄。 | SDT 可發佈的 MSI 套件：<br>商務用 Microsoft Surface 安裝工具<br>[適用於 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703) | [在桌面圖案中使用表面診斷工具箱](surface-diagnostic-toolkit-desktop-mode.md)
命令列 |  使用標準工具（例如 Configuration Manager），直接在沒有使用者互動的情況下遠端疑難排解 Surface 裝置。 它包含下列命令：<br>`-DataCollector` 收集所有記錄檔<br>`-bpa` 使用最佳做法分析程式來執行健康情況分析。<br>`-windowsupdate` 針對缺少的固件或驅動程式更新檢查 Windows 更新。<br>`-warranty` 檢查保修資訊。 <br><br>| SDT 主控台 app：<br>Microsoft Surface Diagnostics 應用程式主控台<br>[適用於 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703) | [使用命令執行表面診斷工具箱](surface-diagnostic-toolkit-command-line.md)

##  <a name="supported-devices"></a>支援的裝置 

在 Surface 3 和更新版本的裝置上支援 SDT for Business，包括：

- Surface Book-所有代
- 表面上移-全部代
- Surface 膝上型電腦-所有代
- Surface Pro 3 及更新版本
- Surface Pro X-所有代
- Surface Studio-所有代
- Surface 3 LTE
- Surface 3


## 安裝適用于商務的 Surface 診斷工具箱

若要建立可發佈給組織中使用者的 SDT 套件：

1. 使用系統管理員帳戶登入您的 Surface 裝置。
2. 從 [ [表面工具](https://www.microsoft.com/download/details.aspx?id=46703) ] 下載 Windows 安裝程式套件 ( .msi) ，然後將它複製到 surface 裝置上的可取位置，例如 [桌面]。
3. [SDT 設定] 嚮導隨即出現，如圖1所示。 按 **\[下一步\]**。 

    >[!NOTE]
    >如果沒有出現 [安裝精靈]，請確定您已登入您電腦上的系統管理員帳戶。 

    ![歡迎使用 Surface 診斷工具組設定向導](images/sdt-1.png)

    *圖 1。 表面診斷工具組設定向導*

4. 當 [SDT 安裝精靈] 出現時，請按 **[下一步]**，接受使用者授權合約 (EULA) 

5. 在 [安裝選項] 畫面上，視需要變更預設安裝位置。 
6. 選取 [設定類型] 底下的 [ **高級**]。 

    >[!NOTE]
    >標準選項可讓使用者在其 Surface 裝置上直接執行診斷工具，前提是他們已使用系統管理員帳戶登入他們的裝置。 
    
     ![安裝選項：高級](images/sdt-install.png)

7. 按一下 **[下一步]** ，然後按一下 [ **安裝**]。 

## 使用命令列安裝
如有需要，您可以在命令提示字元中安裝 SDT，並設定自訂旗標以在 [管理員模式] 中安裝該工具。 SDT 包含下列安裝選項標誌：

- `SENDTELEMETRY` 將遙測資料傳送給 Microsoft。 標誌接受 `0` 停用或 `1` 啟用。 預設值為 [ `1` 傳送遙測]。
- `ADMINMODE` 將工具設定為以 [系統管理模式] 進行安裝。 標誌接受 `0` 用戶端模式或 `1` IT 系統管理員模式。 預設值為 `0`。

### 若要從命令列安裝 SDT：

1. 開啟命令提示字元，然後按 enter 鍵：

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```
    **範例：**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## 在 Surface 裝置上尋找 SDT

[SDT] 和 [SDT] 應用程式主控台都已安裝 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 。

除了 .exe 檔案之外，SDT 還會安裝 JSON 檔案和 admin.dll 檔案 ( # A1) ，如圖2所示。

![檔案資源管理器中的 SDT 已安裝檔案清單](images/sdt-2.png)

*圖 2. 由 SDT 安裝的檔案*

## 準備用於發佈的 SDT 套件

建立自訂套件可讓您將工具目標設定為特定的已知問題。

1. 按一下 [ **開始 > 執行**]、輸入 **表面** ，然後按一下 [ **表面診斷工具] 以取得商務**用。 
2. 當工具開啟時，按一下 [ **建立自訂套件**]，如圖3所示。

    ![[建立自訂套件] 選項](images/sdt-3.png)

    *圖 3. 建立自訂套件*

### 語言和遙測設定

  建立套件時，您可以選取 [語言設定] 或 [選擇不傳送遙測資訊給 Microsoft]。 根據預設，SDT 會將遙測傳送至 Microsoft，以使用 [Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)來改善應用程式。 如果您想要拒絕，請在建立自訂套件時清除核取方塊，如下所示。 或者，在 [**安裝選項**] 頁面上，清除 [在 SDT 設定期間，**傳送遙測至 Microsoft** ] 核取方塊。 

>[!NOTE]
>此設定不會影響執行需要網際網路連線（例如 Windows Update 和軟體修復），或使用 app 工具列中的 [笑臉] 或 [苦臉] 按鈕提供意見反應的測試及修復時，在 Microsoft 伺服器上自動儲存的最小遙測。 


![選取語言和遙測設定](images/sdt-4.png)

*圖 4. 選取語言和遙測設定*


### [Windows Update] 頁面

選取適用于貴組織的選項。 大多數擁有多個使用者的組織通常會選取透過 Windows Server Update Services (WSUS 接收更新) ，如圖5所示。 如果您使用的是 [本機 Windows 更新套件] 或 [WSUS]，請視需要輸入路徑。 

![選取 [Windows Update] 選項](images/sdt-5.png)

*圖 5. [Windows Update] 選項*

### 軟體修復頁面

這可讓您選取或移除執行軟體修復更新的選項。 

![選取軟體修復選項](images/sdt-6.png)

*圖 6. 軟體修復選項*

### 收集記錄及儲存套件頁面

您可以選取在應用程式、驅動程式、硬體及作業系統上執行各種不同的記錄。 按一下適當的區域，然後從 [可用的記錄] 功能表中選取。 然後，您可以將套件儲存至使用者可以存取的軟體發佈點或對等位置。 

![選取記錄選項](images/sdt-7.png)

*圖 7. 記錄選項並儲存套件*

## 後續步驟

- [在桌面模式中使用商務用 Surface 診斷工具組](surface-diagnostic-toolkit-desktop-mode.md)
- [使用命令的 [表面診斷工具] 進行商務用](surface-diagnostic-toolkit-command-line.md)

##  <a name="changes-and-updates"></a>變更與更新

### 版本2.131.139。0

此版本的商業表面診斷工具組會新增下列支援：

- Surface Pro 7 + 支援
- Surface Pro X 的流暢支援體驗
- 安全性改進
- 包括的使用者經驗改進

### 版本2.124.139。0

此版本的商業表面診斷工具組會新增下列支援：

- 順暢整合的支援
- 儲存所有測試結果
- 檢查影像是否已建立自訂
- 在裝置管理器中包含警告
- Dock 固件版本
- 在儲存測試中將磁碟機標示為可能的失敗
- 移除商店連結 

### 版本2.121.139
*發行日期： 31 2020 年7月*<br>
此版本的商業表面診斷工具組會新增下列支援：

- 順暢支援體驗
- 錯誤修正

### 版本2.94.139。0
*發行日期：2020年5月11日*<br>
此版本的商業表面診斷工具組會新增下列支援：

- 能夠略過 Windows Update 來執行硬體檢查。
- 能夠接收最新版本更新的通知
- 表面移2
- Surface Book 3
- 顯示進度指標


### 版本2.43.139。0
*發行日期：2019年10月21日*<br>
此版本的商業表面診斷工具組會新增下列支援：

- Surface Pro 7
- Surface 膝上型電腦3

### 版本2.42.139。0
*發行日期：2019年9月24日*<br>
此版本的商業表面診斷工具組會新增下列支援： 
- 下載硬體報告的能力。
- 直接從工具直接聯繫 Microsoft 支援人員的能力。 <br>

### 版本2.41.139。0
*發行日期：2019年6月24日*<br>
此版本的商業表面診斷工具組會新增下列支援： 
- 記錄和報告中包含的驅動程式版本資訊。
- 提供關於 app 的意見反應的能力。<br>


### 版本2.36.139。0
*發行日期：2019年4月26日*<br>
此版本的商業表面診斷工具組會新增下列支援： 
- [高級設定] 選項可透過安裝程式 UI 解除系統管理員許可權，而不需要命令列設定。
- 協助工具增強功能。
- 記錄中包含 Surface 亮度控制設定。
- 報表發生器中的外部監視器相容性支援連結。
