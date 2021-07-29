---
title: Microsoft Surface Dock 1 固件更新
description: 本文說明如何使用 Microsoft Surface Dock 固件更新在原始的 Surface Dock 1 上安裝及管理固件。 當您安裝在 Surface 裝置上時，它會更新附加至 Surface 裝置上的 Surface Dock 1 裝置。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.date: 2/08/2021
ms.openlocfilehash: 544aa8ab7cb9bb443f368bfbbcecb1fa256d32c5
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708754"
---
# <a name="surface-dock-1-firmware-update"></a>Surface Dock 1 韌體更新

本文說明如何使用 Microsoft Surface Dock 1 的固件更新，在原始的 Surface Dock 1 上安裝及管理固件。 當您安裝在 Surface 裝置上時，它會更新附加至 Surface 裝置上的 Surface Dock 1 裝置。

> [!NOTE]
> 本文不適用於[Surface Dock 2，因為 Surface Dock 2](surface-dock-whats-new.md)會透過更新或Windows或其他 MSI 部署工具Microsoft Endpoint Configuration Manager接收更新。

此工具取代先前 Microsoft Surface Dock Updater 工具，先前可下載為 IT 用 Surface Tools 的一部分。 先前工具的Surface_Dock_Updater_vx.xx.xxx.x.msi (x 代表版本號碼) 且無法再下載，因此不應使用。

> [!IMPORTANT]
> 本文包含適用于 IT 系統管理員的技術指示。 如果您是家用使用者，請參閱如何在 Microsoft 支援網站上更新[Surface Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   固件。 支援網站上的指示與下列一般安裝步驟相同，但本文提供監控、驗證更新，以及將更新部署到網路上多個裝置的其他資訊。

## <a name="install-surface-dock-1-firmware-update"></a>安裝 Surface Dock 1 固件更新

本節說明如何在 Surface Dock 1 上手動安裝固件更新。

> [!TIP]
> Microsoft 會定期發行新版本的 Surface Dock 1 固件更新。 MSI 檔案並未自我更新。 如果您已經將 MSI 部署到 Surface 裝置，且發行新版本的固件，則需要部署新版本。

1. 請前往 [適用于 IT 的 Surface Tools，](https://www.microsoft.com/download/details.aspx?id=46703) 然後下載並安裝 .msi 名為 **Surface_Dock_FwUpdate.** 的檔案，後面接著適當的版本。 如果您是在 X 上Surface Pro，請下載 **.arm64**建立。 針對所有其他裝置，請使用 **.amd64** 版本。  

    - 更新需要 Surface 裝置Windows 10版本 1803 或更新版本。
    - 安裝 MSI 檔案可能會提示您重新開機 Surface。 不過，執行更新時不需要重新開機。

2. 將 Surface 裝置從 Surface Dock 中斷連接，請稍候約 5 秒，然後重新連接。 Surface Dock 1 的固件更新會以無提示方式在背景中更新 Dock。 程式可能需要幾分鐘才能完成，即使中斷，也會繼續進行。

## <a name="monitor-the-surface-dock-1-firmware-update"></a>監控 Surface Dock 1 的固件更新

本節為選擇性專案，並提供如何監控安裝固件更新的概述。

若要監控更新：

1. 開啟事件檢視器，流覽至 Windows記錄 >**應用程式**，然後在右側窗格中的****[動作> 下，按一下 [篩選**目前**記錄，輸入事件來源旁**的 SurfaceDockFwUpdate，** 然後按一下 **[確定**> 。 ****

2. 在提升的命令提示符中輸入下列命令：

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```

3. 如本文下一節所述， [安裝](#install-surface-dock-1-firmware-update) 更新。

4. 包含下列文字的事件 2007 表示更新成功：完成固件更新 **。hr=0 DriverTelementry EventCode = 2007**。

   如果更新失敗，則事件識別碼 2007 會顯示為錯誤事件，而不是******資訊**。 此外，註冊表中Windows版本不會為最新版本。

5. 更新完成後，更新的 DWORD 值會顯示在 Windows 註冊表中，對應到目前版本的工具。 請參閱 [本文中的版本](#versions-reference) 參考區段以瞭解詳細資料。 例如：

    - Component10CurrentFwVersion 0x04ac3970 (78395760) 
    - Component20CurrentFwVersion 0x04915a70 (76634736) 

>[!TIP]
>如果您在事件文字中看到「找不到來自來源 SurfaceDockFwUpdate 的事件識別碼 xxxx 描述」，這是預期的，而且可以忽略。

另請參閱本文中的下列各節：

- [如何驗證完成固件更新](#how-to-verify-completion-of-the-firmware-update)
  - [事件記錄](#event-logging)
  - [疑難排解提示](#troubleshooting-tips)
  - [版本參照](#versions-reference)

## <a name="network-deployment"></a>網路部署

您可以使用安裝程式Windows命令 (Msiexec.exe) Surface Dock 1 的固件更新部署到整個網路的多個裝置。 使用 Microsoft Endpoint Configuration Manager或其他部署工具時，請輸入下列語法，以確保安裝為無提示：

- **Msiexec.exe /i \<path to msi file\> /quiet /norestart**

例如：

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> 根據預設，不會建立記錄檔案。 若要建立記錄檔案，您必須附加「/l*v [path]」。例如：Msiexec.exe /i \<path to msi file\> /l*v %windir%\log\ SurfaceDockFWI.log"

詳情請參閱命令列 [選項](/windows/win32/msi/command-line-options) 檔。

> [!IMPORTANT]
> 如果您想要使用任何其他方法持續更新 Surface Dock，請參閱更新 Surface [Dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 以尋找詳細資料。

## <a name="intune-deployment"></a>Intune 部署

您可以使用 Intune 將 Surface Dock 1 的固件更新發佈至您的裝置。 首先，您需要將 MSI 檔案轉換成 .intunewin 格式，如下列檔所述 [：Intune 獨立版 - Win32 應用程式管理](/intune/apps/apps-win32-app-management)。

請使用下列命令：

- **msiexec /i \<path to msi file\> /quiet /q**

## <a name="how-to-verify-completion-of-the-firmware-update"></a>如何驗證完成固件更新

Surface Dock 固件由兩個元件組成：

- **元件10：** MICRO 控制器單元 (微控制器) 固件
- **元件20：** 在DP (顯示) 埠。

成功完成 Surface Dock 1 的固件更新後，這些固件元件會獲得新的註冊表鍵值。

### <a name="to-verify-updates"></a>若要驗證更新

1. 開啟 Regedit 並流覽至下列註冊表路徑：

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. 尋找登錄機碼 **：Component10CurrentFwVersion和 Component20CurrentFwVersion，** 這是指目前裝置上的固件。

   ![Surface Dock 1 固件更新安裝程式](images/regeditDock.png)

3. 確認新的登錄機碼值符合本檔結尾版本參照中列出的更新的登錄機碼值。 如果值相符，則已成功更新該固件。

4. 如果無法驗證，請于下一節中查看事件記錄與疑難排解提示。

## <a name="event-logging"></a>事件記錄

### <a name="table-1-log-files-for-surface-dock-1-firmware-update"></a>表 1. Surface Dock 1 固件更新的記錄檔案

| 記錄檔                              | 位置                               | 附註                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Dock 1 固件更新記錄 | 必須指定路徑 (請參閱附注)  | 此工具的較舊版本會將事件記錄至應用程式與服務記錄\Microsoft Surface Dock Updater。                                                                                                  |
| Windows裝置安裝記錄       | %windir%\inf\setupapi.dev.log           | 有關使用裝置安裝記錄程式詳細資訊，請參閱 [SetupAPI 記錄](/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) 檔。 |

### <a name="table-2-event-log-ids-for-surface-dock-1-firmware-update"></a>表 2. Surface Dock 1 固件更新的事件記錄

事件會記錄在應用程式事件記錄中。  注意：此工具的較舊版本會將事件記錄至應用程式與服務記錄\Microsoft Surface Dock Updater。

| 事件識別碼 | 事件類型                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | Dock 的固件更新已開始。                                    |
| 2002     | Dock 的固件更新已略過，因為 Dock 已知為最新狀態。 |
| 2003     | Dock 的固件更新無法取得固件版本。                 |
| 2004     | 查詢固件版本。                                       |
| 2005     | Dock 固件無法開始更新。                                |
| 2006     | 傳送優惠/有效負載組失敗。                                  |
| 2007     | 完成固件更新。                                            |
| 2008     | BEGIN dock 遙測。                                                |
| 2011     | END Dock 遙測。                                                  |

## <a name="troubleshooting-tips"></a>疑難排解提示

- 完全中斷 Surface 固定電源與交流電源的電源，以重設 Surface Dock。
- 中斷所有外接裝置，但 Surface Dock 除外。
- 卸載任何目前的 Surface Dock 1 固件更新，然後安裝最新版本。
- 請確保 Surface Dock 已中斷連接，然後允許足夠的時間讓更新完成，以透過固定埠的乙太網路埠中的 LED 進行監控。 請稍候，直到 LED 停止閃爍，再拔除 Surface Dock 電源。
- 連線 Surface Dock 到不同的裝置，以查看它是否能夠更新 Dock。

## <a name="versions-reference"></a>版本參照

>[!NOTE]
>安裝檔案會以下列命名格式發行：Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI(：Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 預設為 C：\Program Files\SurfaceUpdate。 ****

### <a name="version-1531390"></a>版本 1.53.139.0

#### <a name="release-date-august-4-2020"></a>發行日期：2020 年 8 月 4 日

此版本的 Surface Dock 1 固件更新包含錯誤修正和支援：

- 使用 x 更新 Surface Dock 1 Surface Pro程式。

#### <a name="registry-key-values"></a>登錄機碼值

指出固件更新狀態的註冊表值與此工具的先前版本沒有改變：

- Component10CurrentFwVersion更新為 **4ac3970**。
- Component20CurrentFwVersion更新為 **4a1d570**。

### <a name="version-142139"></a>版本 1.42.139

#### <a name="release-date-september-18-2019"></a>發行日期：2019 年 9 月 18 日

此版本包含于 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI，會更新背景中的固件。

#### <a name="updated-registry-key-values"></a>更新的登錄機碼值

- Component10CurrentFwVersion更新為 **4ac3970**。
- Component20CurrentFwVersion更新為 **4a1d570**。

它新增 7 和 Surface Pro 3 Surface Laptop支援。

## <a name="legacy-versions"></a>舊版

### <a name="version-2231390"></a>版本 2.23.139.0

#### <a name="release-date-10-october-2018"></a>發行日期：2018 年 10 月 10 日

此版本的 Surface Dock Updater 新增下列支援：

- 新增 6 Surface Pro支援
- 新增 2 Surface Laptop支援

### <a name="version-2221390"></a>版本 2.22.139.0

#### <a name="release-date-26-july-2018"></a>發行日期：2018 年 7 月 26 日

此版本的 Surface Dock Updater 新增下列支援：

- 提高更新可靠性
- 新增 Surface Go 支援

### <a name="version-2121360"></a>版本 2.12.136.0

#### <a name="release-date-29-january-2018"></a>發行日期：2018 年 1 月 29 日

此版本的 Surface Dock Updater 新增下列支援：

- 適用於 Surface 擴充座主要晶片組韌體的更新

- 適用於 Surface 擴充座 DisplayPort 韌體的更新

- 改善外部顯示器與 Surface Book 或 Surface Book 2 搭配使用時的顯示穩定性

此外，Surface Book 裝置上的這一版 Surface Dock Updater 安裝還包含：

- Surface Book Base Firmware 更新

- 透過以 Surface Book 裝置為目標的改進功能，加入 Surface 擴充座韌體更新支援

### <a name="version-291360"></a>版本 2.9.136.0

#### <a name="release-date-november-3-2017"></a>發行日期︰2017 年 11 月 3 日

此版本的 Surface Dock Updater 新增下列支援：

- 適用於 Surface 擴充座 DisplayPort 韌體的更新

- 解決透過被動式顯示連接埠介面卡的音訊問題

### <a name="version-21150"></a>版本 2.1.15.0

#### <a name="release-date-june-19-2017"></a>發行日期：2017 年 6 月 19 日

此版本的 Surface Dock Updater 新增下列支援：

- Surface 膝上型電腦

- Surface Pro

### <a name="version-2160"></a>版本 2.1.6.0

#### <a name="release-date-april-7-2017"></a>發行日期︰2017 年 4 月 7 日

此版本的 Surface Dock Updater 新增下列支援：

- 適用於 Surface 擴充座 DisplayPort 韌體的更新

- 需要 Windows 10

### <a name="version-20220"></a>版本 2.0.22.0

#### <a name="release-date-october-21-2016"></a>發行日期︰2016 年 10 月 21 日

此版本的 Surface Dock Updater 新增下列支援：

- 適用於 Surface 擴充座 USB 韌體的更新

- 已改進乙太網路、音訊和 USB 連接埠的穩定性

### <a name="version-1080"></a>版本 1.0.8.0

#### <a name="release-date-april-26-2016"></a>發行日期︰2016 年 4 月 26 日

此版本的 Surface Dock Updater 新增下列支援：

- 適用於 Surface 擴充座主要晶片組韌體的更新

- 適用於 Surface 擴充座 DisplayPort 韌體的更新
