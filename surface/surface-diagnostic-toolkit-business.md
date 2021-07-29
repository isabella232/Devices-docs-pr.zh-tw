---
title: 商務用 Surface 診斷工具組
description: 本主題說明如何部署及使用商務用 Surface 診斷工具組，讓 IT 系統管理員能快速調查、疑難排解及解決 Surface 裝置的硬體、軟體及固件問題。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 07/27/2021
ms.reviewer: hachidan
manager: laurawi
audience: itpro
ms.openlocfilehash: 13480c4b642ff64883c0ee69c73161a51f3f1e96
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708804"
---
# <a name="surface-diagnostic-toolkit-for-business"></a>商務用 Surface 診斷工具組

如果您的 Surface 無法正常運作，Microsoft Surface 診斷工具組 (商務用 SDT) 可協助您或您的系統管理員尋找並解決問題。  商務用 SDT 可讓您在整個網路中快速調查、疑難排解及解決 Surface 裝置的硬體、軟體和固件問題。

> [!NOTE]
> 商務用 Surface 診斷工具套件專為商業裝置所打造。 如果您的裝置是個人裝置，而且並非由公司或學校管理，請改為執行 [Surface 診斷工具](https://support.microsoft.com/en-us/help/4037239/surface-fix-common-surface-problems-using-surface-diagnostic-toolkit) 套件。

具體來說，商務用 SDT 可讓您：

- [自訂套件。](#preparing-the-sdt-package-for-distribution)
- [使用命令執行應用程式。](surface-diagnostic-toolkit-command-line.md)
- [執行多個硬體測試以疑難排解問題。](surface-diagnostic-toolkit-desktop-mode.md#multiple)
- [產生記錄以分析問題。](surface-diagnostic-toolkit-desktop-mode.md#logs)
- [取得詳細的報告，比較裝置與優化組配置。](surface-diagnostic-toolkit-desktop-mode.md#detailed-report)

## <a name="primary-scenarios-and-download-resources"></a>主要案例和下載資源

若要執行商務用 Surface 診斷工具組，請下載下表中列出的元件。

模式 | 主要案例 | 下載 | 深入了解
--- | --- | --- | ---
桌面模式 | 協助使用者在 Surface 裝置上執行 SDT 以疑難排解問題。<br>建立自訂套件以部署在一或多個 Surface 裝置上，允許使用者選取要收集及分析的特定記錄。 | SDT 可分配的 MSI 套件：<br>商務用 Microsoft Surface 診斷工具套件安裝程式<br>[適用於 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703) | [在桌面圖案中使用 Surface 診斷工具套件](surface-diagnostic-toolkit-desktop-mode.md)
命令列 | 使用標準工具 ，例如 Configuration Manager，直接針對 Surface 裝置進行遠端疑難排解，而不需要使用者互動。 它包含下列命令：<br>`-DataCollector` 收集所有記錄檔案<br>`-bpa` 使用最佳做法分析程式執行健康診斷。<br>`-windowsupdate` 檢查Windows更新是否遺失的固件或驅動程式更新。<br>`-warranty` 檢查保固資訊。 <br><br>| SDT 主機應用程式：<br>Microsoft Surface 診斷應用程式主控台<br>[適用於 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703) | [使用命令執行 Surface 診斷工具組](surface-diagnostic-toolkit-command-line.md)

## <a name="supported-devices"></a>支援的裝置

商務用 SDT 支援 Surface 3 及更新版本裝置 (S 模式所配置的裝置除外) ：

- Surface Book - 所有代
- Surface Go - 所有代
- Surface Laptop - 所有代
- Surface Pro 3 及更高版本
- Surface ProX - 所有代
- Surface Studio - 所有代
- Surface 3 LTE
- Surface 3

## <a name="installing-surface-diagnostic-toolkit-for-business"></a>安裝商務用 Surface 診斷工具套件

若要建立可發佈給貴組織中使用者的 SDT 套件：

1. 使用系統管理員帳戶來登錄您的 Surface 裝置。
2. 從適用于 IT Windows工具 (.msi) 下載 SDT 和[](https://www.microsoft.com/download/details.aspx?id=46703)安裝程式套件，然後複製到 Surface 裝置上偏好的位置 ，例如桌面。
3. SDT 設定精靈會出現，如圖 1 所示。 按 **\[下一步\]**。

    >[!NOTE]
    >如果沒有顯示設定精靈，請確保您已在電腦上登錄系統管理員帳戶。

    ![歡迎使用 Surface 診斷工具套件設定精靈](images/sdt-1.png)

    *圖 1。 Surface 診斷工具套件設定精靈*

4. 當 SDT 設定精靈出現時，按一下 **[下**一步，接受使用者授權合約 (EULA) 

5. 在安裝選項畫面上，如果需要，變更預設安裝位置。
6. 在設定類型下，選取進 **位**。

    >[!NOTE]
    >標準選項允許使用者直接在 Surface 裝置上執行診斷工具，只要他們使用系統管理員帳戶已登錄其裝置。

     ![安裝選項：進一步](images/sdt-install.png)

7. 按一下 **[下** 一步，然後按一下 **[安裝**> 。

## <a name="installing-using-the-command-line"></a>使用命令列安裝

如果需要，您可以在命令提示符上安裝 SDT，並設定自訂標標，以在系統管理模式中安裝工具。 SDT 包含下列安裝選項標標：

- `SENDTELEMETRY` 傳送遙測資料至 Microsoft。 標號接受 `0` 為已停用 `1` 或已啟用。 預設值是 `1` 傳送遙測。
- `ADMINMODE` 設定要以系統管理模式安裝的工具。 標號接受 `0` 用戶端模式或 `1` IT 系統管理員模式。 預設值為 `0`。

### <a name="to-install-sdt-from-the-command-line"></a>從命令列安裝 SDT

1. 開啟命令提示符並輸入：

    ```
    msiexec.exe /i <the path of installer> ADMINMODE=1. 
    ```

    **範例：**

    ```
    C:\Users\Administrator> msiexec.exe/I"C:\Users\Administrator\Desktop\Microsoft_Surface_Diagnostic_Toolkit_for_Business_Installer.msi" ADMINMODE=1
    ```

## <a name="locating-sdt-on-your-surface-device"></a>在 Surface 裝置上找到 SDT

SDT 和 SDT 應用程式主控台都安裝在 `C:\Program Files\Microsoft\Surface\Microsoft Surface Diagnostic Toolkit for Business` 。

除了該.exe，SDT 會安裝 JSON 檔案和 admin.dll檔案 (modules\admin.dll) ，如圖 2 所示。

![檔案檔案管理器中已安裝 SDT 檔案的清單](images/sdt-2.png)

*圖 2. SDT 安裝的檔案*

## <a name="preparing-the-sdt-package-for-distribution"></a>準備 SDT 套件以發佈

建立自訂套件可讓您將工具定位到特定的已知問題。

1. 按一下 **[開始>** 執行>，輸入 **Surface，** 然後按一下 **[商務用 Surface 診斷工具套件**>。
2. 當工具開啟時，按一下 **[建立自訂套件**，如圖 3 所示。

    ![建立自訂套件選項](images/sdt-3.png)

    *圖 3. 建立自訂套件*

### <a name="language-and-telemetry-settings"></a>語言和遙測設定

  建立套件時，您可以選取語言設定，或退出宣告傳送遙測資訊至 Microsoft。 根據預設，SDT 會傳送遙測給 Microsoft，用來根據 [Microsoft 隱私權聲明改善應用程式](https://privacy.microsoft.com/privacystatement)。 如果您想要拒絕，請在建立自訂套件時清除核取方塊，如下所示。 或者，在**** SDT 設定期間清除安裝**** 選項頁面上的傳送遙測至 Microsoft 核取方塊。

>[!NOTE]
>這項設定不會影響執行需要網際網路連接的測試與修復時，自動儲存在 Microsoft 伺服器中的最小遙測資料，例如 Windows 更新和軟體修復，或使用應用程式工具列中的笑臉或快發按鈕提供意見回饋。

![選取語言和遙測設定](images/sdt-4.png)

*圖 4. 選取語言和遙測設定*

### <a name="windows-update-page"></a>Windows更新頁面

選取適合貴組織的選項。 具有多個使用者的大多陣列織通常會選取以透過 WSUS Windows Server Update Services (接收) ，如圖 5 所示。 如果使用本地Windows更新套件或 WSUS，請在適當時輸入路徑。

![選取 Windows更新選項](images/sdt-5.png)

*圖 5. Windows更新選項*

### <a name="software-repair-page"></a>軟體修復頁面

這可讓您選取或移除執行軟體修復更新的選項。

![選取軟體修復選項](images/sdt-6.png)

*圖 6. 軟體修復選項*

### <a name="collecting-logs-and-saving-package-page"></a>收集記錄並保存套件頁面

您可以選取以跨應用程式、驅動程式、硬體和作業系統執行各種記錄。 按一下適當的區域，然後從可用記錄功能表中選取。 接著，您可以將套件儲存到軟體發佈點或使用者可以存取的對等位置。

![選取記錄選項](images/sdt-7.png)

*圖 7. 記錄選項和儲存套件*

## <a name="next-steps"></a>後續步驟

- [在桌面模式中使用商務用 Surface 診斷工具組](surface-diagnostic-toolkit-desktop-mode.md)
- [使用商務用 Surface 診斷工具組使用命令](surface-diagnostic-toolkit-command-line.md)

## <a name="changes-and-updates"></a>變更與更新

### <a name="version-21311390"></a>版本 2.131.139.0

此版本的商務用 Surface 診斷工具組新增下列支援：

- 支援 Surface Pro 7+
- X 上的流暢支援Surface Pro體驗
- 安全性改進
- 包含使用者體驗的改良功能

### <a name="version-21241390"></a>版本 2.124.139.0

此版本的商務用 Surface 診斷工具組新增下列支援：

- 順暢整合的支援
- 儲存所有測試結果
- 檢查影像是否自訂建立
- 包含裝置管理員的警告
- Dock 固件版本
- 將磁片磁碟機標為儲存測試的潛在失敗
- 移除市面連結

### <a name="version-2121139"></a>版本 2.121.139

*發行日期：2020 年 7 月 31 日*<br>
此版本的商務用 Surface 診斷工具組新增下列支援：

- 流暢的支援體驗
- 錯誤修正

### <a name="version-2941390"></a>版本 2.94.139.0

*發行日期：2020 年 5 月 11 日*<br>
此版本的商務用 Surface 診斷工具組新增下列支援：

- 可跳過更新Windows執行硬體檢查。
- 接收最新版更新通知的能力
- Surface Go 2
- Surface Book 3
- 顯示進度指示器

### <a name="version-2431390"></a>版本 2.43.139.0

*發行日期：2019 年 10 月 21 日*<br>
此版本的商務用 Surface 診斷工具組新增下列支援：

- Surface Pro 7
- Surface Laptop 3

### <a name="version-2421390"></a>版本 2.42.139.0

*發行日期：2019 年 9 月 24 日*<br>
此版本的商務用 Surface 診斷工具組新增下列支援：

- 下載硬體報告的能力。
- 可以直接從工具與 Microsoft 支援服務聯繫。 <br>

### <a name="version-2411390"></a>版本 2.41.139.0

*發行日期：2019 年 6 月 24 日*<br>
此版本的商務用 Surface 診斷工具組新增下列支援：

- 記錄與報告中包含的驅動程式版本資訊。
- 提供有關應用程式的意見回饋的能力。<br>

### <a name="version-2361390"></a>版本 2.36.139.0

*發行日期：2019 年 4 月 26 日*<br>
此版本的商務用 Surface 診斷工具組新增下列支援：

- 進一步設定選項可透過安裝程式 UI 解除鎖定管理功能，而不需要命令列設定。
- 協助工具改良功能。
- 記錄中包含的 Surface 亮度控制設定。
- 報表產生器中的外部監視器相容性支援連結。
