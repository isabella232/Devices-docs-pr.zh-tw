---
title: Microsoft Surface Dock 1 固件更新
description: 本文說明如何使用 Microsoft Surface Dock 固件更新來安裝和管理原始 Surface Dock 1 上的固件。 在 Surface 裝置上安裝後，它會更新連接至 Surface 裝置的 Surface Dock 1 裝置。
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
ms.openlocfilehash: a0acaaf0676c3f4403a2b233297781579ca1f4ae
ms.sourcegitcommit: 7029e80d9ca1a3de5c336cf662e566ed4b6b3e7a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/09/2021
ms.locfileid: "11319207"
---
# Microsoft Surface Dock 固件更新

> [!IMPORTANT]
> 本文包含適用于 IT 系統管理員的技術指示。 如果您是家用版使用者，請參閱如何在 Microsoft 支援網站上[更新 Surface Dock 固件](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock)   。 支援網站上的指示與下列一般安裝步驟相同，但本文有其他資訊可監視、驗證和部署到網路上的多個裝置的更新。

本文說明如何使用 Microsoft Surface Dock 固件更新來安裝和管理原始 Surface Dock 1 上的固件。 在 Surface 裝置上安裝後，它會更新連接至 Surface 裝置的 Surface Dock 1 裝置。

> [!NOTE]
> 本文不適用於透過 Windows Update 或使用 Microsoft 端點建構管理員或其他 MSI 部署工具自動接收更新的 Surface Dock 2。 若要深入瞭解，請參閱 [Surface Dock 的新增功能](surface-dock-whats-new.md)。

這個工具取代舊版的 Microsoft Surface Dock 更新程式工具，先前可供下載，成為它的 Surface 工具的一部分。 舊版工具已命名為 Surface_Dock_Updater_vx.xx.xxx.x.msi (其中 x 表示版本號碼) 且不再提供下載，因此不應使用。

## 安裝 Surface Dock 固件更新

本節說明如何手動安裝固件更新。

> [!NOTE]
> Microsoft 會定期發行新版本的 Surface Dock 固件更新。 MSI 檔案不是自我更新。 如果您已將 MSI 部署到 Surface 裝置，且發行新版本的固件，您將需要部署新版本。

1. 下載並安裝 [Microsoft Surface Dock 固件更新](https://www.microsoft.com/download/details.aspx?id=46703)。
    - 更新需要執行 Windows 10 版本1803或更新版本的 Surface 裝置。
    - 安裝 MSI 檔案時，可能會提示您重新開機表面。 不過，不需要重新開機就能執行更新。

2. 中斷 Surface 裝置與 Surface Dock 的連接，請等候大約5秒，然後重新連接。 Surface Dock 固件更新將在背景中悄悄地更新 Dock。 這個程式可能需要幾分鐘的時間才能完成，即使中斷也會繼續。 

## 監視 Surface Dock 固件更新

本節是選擇性的，並提供如何監視固件更新安裝的概覽。 

若要監視更新：

1. 開啟事件檢視器、流覽至**Windows 記錄 > 應用程式**，然後在右側窗格的 [**動作**] 下，按一下 [**篩選目前的記錄**]，輸入**事件來源**旁邊的**SurfaceDockFwUpdate** ，然後按一下 **[確定]**。

2. 在提升許可權的命令提示字元中輸入下列命令：

    ```console
    Reg query "HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters"
    ```
3. 如本文 [下一節](#install-the-surface-dock-firmware-update) 所述，安裝更新。

4. 事件2007與下列文字表示成功更新： **固件更新已完成。 hr = 0 DriverTelementry EventCode = 2007**。 

   如果更新未成功，則事件 ID 2007 將會顯示為 **錯誤** 事件，而不是 **資訊**。 此外，Windows 登錄版中報告的版本不會是最新版本。
   
5. 更新完成後，Windows 登錄會顯示更新的 DWORD 值，與目前的工具版本相對應。 如需詳細資訊，請參閱本文的 [版本參考](#versions-reference) 一節。 例如：

    - Component10CurrentFwVersion 0x04ac3970 (78395760) 
    - Component20CurrentFwVersion 0x04915a70 (76634736) 

>[!TIP]
>如果您在事件文字中看到「無法找到來源 SurfaceDockFwUpdate 的事件 ID xxxx 的描述」，就表示這是預期的方式，而且可以忽略。

另請參閱本文中的下列各節： 
  - [如何驗證固件更新完成](#how-to-verify-completion-of-the-firmware-update)
  - [事件記錄](#event-logging)
  - [疑難排解提示](#troubleshooting-tips)
  - [版本參考](#versions-reference)

## 網路部署

您可以使用 Windows 安裝程式命令 ( # A0) ，將 Surface Dock 固件更新部署到網路上的多個裝置。 使用 Microsoft 端點建構管理員或其他部署工具時，請輸入下列語法，以確保安裝為緘默：

- **Msiexec.exe/i \<path to msi file\> /quiet/norestart** 

例如：

```console
msiexec /i "\\share\folder\Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi" /quiet /norestart
```

> [!NOTE]
> 預設不會建立記錄檔。 若要建立記錄檔，您需要附加 "/l*v [path]"。例如： Msiexec.exe/i \<path to msi file\> /l*v%windir%\logs\ SurfaceDockFWI .log "

如需詳細資訊，請參閱 [命令列選項](https://docs.microsoft.com/windows/win32/msi/command-line-options) 檔。

> [!IMPORTANT]
> 如果您想要使用任何其他方法，讓 Surface Dock 保持更新，請參閱 [更新 Surface dock](https://support.microsoft.com/help/4023478/surface-update-your-surface-dock) 以取得詳細資料。

## Intune 部署

您可以使用 Intune 將 Surface Dock 固件更新發佈到您的裝置。 首先，您需要將 MSI 檔案轉換成 intunewin 格式，如下列檔所述： [Intune 獨立-Win32 app 管理](https://docs.microsoft.com/intune/apps/apps-win32-app-management)。

使用下列命令：
  - **msiexec/i \<path to msi file\> /quiet/q**

## 如何驗證固件更新已完成

Surface dock 固件由兩個元件組成：

- **Component10：** (MCU) 固件的微控制器單元
- **Component20：** 顯示埠 (DP) 固件。

成功完成 Surface Dock 固件更新會產生這些固件元件的新登錄項值。

**驗證更新：**

1. 開啟 Regedit 並流覽至下列登錄路徑：

    - **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\WUDF\Services\SurfaceDockFwUpdate\Parameters**

2. 尋找登錄機碼： **Component10CurrentFwVersion 和 Component20CurrentFwVersion**，這是指目前在裝置上的固件。

   ![Surface Dock 固件更新安裝程式](images/regeditDock.png)

3. 確認新的登錄機碼值符合本檔結尾版本參考中所列的更新登錄機碼值。 如果值相符，即已成功更新固件。

4. 如果無法驗證，請在下一節中查看事件記錄和疑難排解秘訣。

## 事件記錄

**表 1. Surface Dock 固件更新的記錄檔**

| 記錄檔                              | Location                               | 附註                                                                                                                                                                                                         |
| -------------------------------- | --------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Dock 固件更新記錄 | 需要指定路徑 (請參閱記事)  | 此工具的舊版版本會將事件寫入應用程式和服務 Logs\Microsoft Surface Dock 更新程式。                                                                                                  |
| Windows 裝置安裝記錄       | %windir%\inf\setupapi.dev.log           | 如需使用裝置安裝記錄的詳細資訊，請參閱 [SetupAPI 記錄](https://docs.microsoft.com/windows-hardware/drivers/install/setupapi-logging--windows-vista-and-later-) 檔。 |


**表 2. Surface Dock 固件更新的事件記錄識別碼**<br>
事件會記錄在應用程式事件日誌中。  注意：此工具的舊版版本會將事件寫入應用程式和服務 Logs\Microsoft Surface Dock 更新程式。

| 事件識別碼 | 事件類型                                                           |
| -------- | -------------------------------------------------------------------- |
| 2001     | 已開始插接固件更新。                                    |
| 2002     | 已略過 dock 固件更新，因為已已知 dock 是最新的。 |
| 2003     | Dock 固件更新無法取得固件版本。                 |
| 2004     | 查詢固件版本。                                       |
| 2005     | Dock 固件無法啟動更新。                                |
| 2006     | 無法傳送優惠/載荷對。                                  |
| 2007     | 固件更新已完成。                                            |
| 2008     | 開始停靠遙測。                                                |
| 2011     | 結束 dock 遙測。                                                  |

## 疑難排解提示

- 從交流電源完全拔下表面停靠的電源，以重設 Surface Dock。
- 拔下除表面固定以外的所有週邊設備。
- 卸載任何目前的 Surface Dock 固件更新，然後安裝最新版本。
- 請確定已中斷 Surface Dock 的連接，然後允許在插接的乙太網埠中，透過指示燈來完成更新，以取得足夠的時間。 等到指示燈停止閃爍之後，才能從電源拔出表面 Dock。
- 將表面 Dock 連接到另一個裝置，看看它能否更新 Dock。

## 版本參考

>[!NOTE]
>安裝檔案是以下列命名格式發行： **Surface_Dock_FwUpdate_X.XX.XXX_Win10_XXXXX_XX.XXX.XXXXX_X.MSI** (ex： Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.msi) 並預設安裝至 C:\Program Files\SurfaceUpdate。

### 版本1.53.139。0
*發行日期：2020年8月4日*

此版本的 Surface Dock 固件更新包含錯誤修正及支援：
- 使用 Surface Pro X 更新 Surface Dock 1。 
   > [!NOTE]
   > 如果您正在執行 Surface Pro X，請下載。ARM64 組建。 針對所有其他裝置，請使用 AMD64 組建。 

#### 登錄機碼值

指示固件更新狀態的登錄值不會與舊版此工具保持相同： 

- Component10CurrentFwVersion 更新到 **4ac3970**。
- Component20CurrentFwVersion 更新到 **4a1d570**。
 
### 版本1.42.139 
*發行日期： 18 2019 年9月*

此版本（包含在 Surface_Dock_FwUpdate_1.42.139_Win10_17134_19.084.31680_0.MSI 中）會更新背景中的固件。 

####  <a name="update"></a>更新的登錄機碼值

- Component10CurrentFwVersion 更新到 **4ac3970**。
- Component20CurrentFwVersion 更新到 **4a1d570**。

它會新增 Surface Pro 7 和 Surface 膝上型電腦3的支援。

## 舊版版本

### 版本2.23.139。0
*發行日期：2018年10月10日*

此版本的 Surface Dock Updater 新增下列支援：

- 新增 Surface Pro 6 支援
- 新增對 Surface 膝上型電腦2的支援


### 版本2.22.139。0
*發行日期：2018年7月26日*

此版本的 Surface Dock Updater 新增下列支援：

- 提高更新的可靠性
- 新增 Surface Go 支援

### 版本 2.12.136.0
*發行日期：2018 年 1 月 29 日*

此版本的 Surface Dock Updater 新增下列支援：
* 適用於 Surface 擴充座主要晶片組韌體的更新
* 適用於 Surface 擴充座 DisplayPort 韌體的更新
* 改善外部顯示器與 Surface Book 或 Surface Book 2 搭配使用時的顯示穩定性

此外，Surface Book 裝置上的這一版 Surface Dock Updater 安裝還包含：
* Surface Book Base Firmware 更新
* 透過以 Surface Book 裝置為目標的改進功能，加入 Surface 擴充座韌體更新支援


### 版本 2.9.136.0
*發行日期︰2017 年 11 月 3 日*

此版本的 Surface Dock Updater 新增下列支援：

* 適用於 Surface 擴充座 DisplayPort 韌體的更新
* 解決透過被動式顯示連接埠介面卡的音訊問題

### 版本 2.1.15.0
*發行日期：2017 年 6 月 19 日*

此版本的 Surface Dock Updater 新增下列支援：

* Surface 膝上型電腦
* Surface Pro

### 版本 2.1.6.0
*發行日期︰2017 年 4 月 7 日*

此版本的 Surface Dock Updater 新增下列支援：

* 適用於 Surface 擴充座 DisplayPort 韌體的更新
* 需要 Windows 10

### 版本 2.0.22.0
*發行日期︰2016 年 10 月 21 日*

此版本的 Surface Dock Updater 新增下列支援：

* 適用於 Surface 擴充座 USB 韌體的更新
* 已改進乙太網路、音訊和 USB 連接埠的穩定性

### 版本 1.0.8.0
*發行日期︰2016 年 4 月 26 日*

此版本的 Surface Dock Updater 新增下列支援：

* 適用於 Surface 擴充座主要晶片組韌體的更新
* 適用於 Surface 擴充座 DisplayPort 韌體的更新

