---
title: 使用商務用 Surface 診斷工具套件執行命令列應用程式主控台
description: 如何在命令主控台中執行 Surface 診斷工具套件
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: bdd91df1f1ce105ecd19ea15e78bd9dc29d0ee95
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448466"
---
# <a name="run-command-line-app-console-with-surface-diagnostic-toolkit-for-business"></a>使用商務用 Surface 診斷工具套件執行命令列應用程式主控台

執行 Surface 診斷工具 (SDT) 命令提示時，需要下載 SDT 應用程式主控台。 安裝之後，您可以透過 Windows 命令主控台 (cmd.exe) 或 Windows PowerShell #C1 命令提示符執行 SDT，包括 PowerShell 整合腳本環境 (ISE) ，提供命令、複製/貼上及其他功能自動完成的支援。  有關 SDT 中支援的 Surface 裝置清單，請參閱 [部署商務用 Surface 診斷工具組](surface-diagnostic-toolkit-business.md)。

>[!NOTE]
>若要使用命令執行 SDT，您必須已登錄系統管理員帳戶，或已登錄成為 Surface 裝置上系統管理員群組成員的帳戶。

## <a name="running-sdt-app-console"></a>執行 SDT 應用程式主控台

1. 從 Surface Tools for IT 下載頁面下載並安裝 [SDT App 主機](https://www.microsoft.com/download/details.aspx?id=46703)。

- 針對 Intel/AMD 裝置，請 ** 下載：Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0.exe**
- 針對 ARM 裝置，請 ** 下載：Microsoft.Surface.Diagnostics.App.Console.v2.168.139.0_x86.exe**

2. 使用 Windows命令提示 (cmd.exe) 或Windows PowerShell：

- 收集所有記錄檔案
- 使用最佳做法分析程式執行健康診斷
- 檢查更新中缺少的固件或驅動程式更新

>[!NOTE]
>在此版本中，SDT 應用程式主控台僅支援單一命令。 執行多個命令列選項時，必須針對每個命令分別執行主控台 exe。

根據預設，輸出檔案會儲存于與主控台應用程式相同的位置。 請參閱下表以查看完整的命令清單。

命令 | 附註
--- | ---
-DataCollector"輸出檔案" | 將系統詳細資料收集到 zip 檔案中。 「輸出檔案」是建立系統詳細資料 zip 檔案的檔案路徑。<br><br>**範例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa"輸出檔案" | 檢查裝置中的多個設定和健康情況指示器。 「輸出檔案」是建立 HTML 報表的檔案路徑。<br><br>**範例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | 檢查Windows更新線上伺服器，以尋找遺失的固件和/或驅動程式更新。<br><br>**範例**：<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-保固"輸出檔案" | 檢查裝置上的保固資訊 (有效或無效) 。 選擇性的「輸出檔案」是建立 xml 檔案的檔案路徑。 <br><br>**範例**： <br>Microsoft.Surface.Diagnostics.App.Console.exe –保固「warranty.xml」

>[!NOTE]
>若要在目標裝置上遠端執行 SDT 應用程式主控台，您可以使用組Microsoft Endpoint Configuration Manager。 或者，您可以建立包含.zip應用程式及適當主控台命令的檔案，並根據貴組織的軟體發佈程式進行部署。

## <a name="running-best-practice-analyzer"></a>執行最佳做法分析程式

您可以跨重要元件執行 BPA 測試，例如 BitLocker、Secure Boot 和受信任的平臺模組 (TPM) ，然後將結果輸出至可共用檔案。 此工具會產生一系列表格，包含色彩編碼的標題和條件描述項，以及如何解決此問題的指引。

- 綠色表示元件以最佳狀態執行， (最佳) 。
- Orange 表示元件未在最佳狀態執行， (優化) 。
- 紅色表示元件狀態異常。

### <a name="sample-bpa-results-output"></a>BPA 結果輸出樣本

<table>
<tr><th colspan="2">BitLocker</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查系統磁碟機上是否已啟用 BitLocker。</td></tr>
<tr><td><strong>值：</strong></td><td>保護功能已上</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>強烈建議您啟用 BitLocker 以保護您的資料。</td></tr>
</table>

<table>
<tr><th colspan="2">安全開機</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用安全啟動。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>強烈建議您啟用安全啟動以保護您的電腦。</td></tr>
</table>

<table>
<tr><th colspan="2">信賴平台模組</th></tr>
<tr><td><strong>描述：</strong></td><td>確保 TPM 運作正常。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>如果沒有功能型 TPM，例如 BitLocker 等安全性型函數可能無法正常運作。</td></tr>
</table>

<table>
<tr><th colspan="2">已連接待命狀態</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用連接待命。</td></tr>
<tr><td><strong>值：</strong></td><td>True</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>已連接待命可讓 Surface 裝置在未使用時接收更新和通知。 為了獲得最佳體驗，應啟用連接待命。</td></tr>
</table>

<table>
<tr><th colspan="2">藍牙</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查藍牙是否已啟用。</td></tr>
<tr><td><strong>值：</strong></td><td>啟用</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2">偵錯模式</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查作業系統是否位於 Debug 模式。</td></tr>
<tr><td><strong>值：</strong></td><td>一般</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>調試啟動選項可啟用或停用作業系統的Windows程式。 啟用此選項可能會導致系統不穩定，並可防止 DRM (數位版權管理) 受保護的媒體播放。</td></tr>
</table>

<table>
<tr><th colspan="2">測試簽署</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用測試簽署。</td></tr>
<tr><td><strong>值：</strong></td><td>一般</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>測試簽署是Windows啟動設定，只應用來測試版驅動程式。</td></tr>
</table>

<table>
<tr><th colspan="2">使用中電源配置</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查正確的電源配置是否有效。</td></tr>
<tr><td><strong>值：</strong></td><td>平衡</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>強烈建議使用「平衡」電源配置，以最大化生產力和電池使用時間。</td></tr>
</table>

<table>
<tr><th colspan="2">Windows Update</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查裝置是否最新，Windows更新。</td></tr>
<tr><td><strong>值：</strong></td><td>Microsoft Silverlight (KB4023307) 、Windows Defender 防毒軟體 定義更新 - KB2267602 (定義 1.279.1433.0) </td></tr>
<tr><td><strong>條件：</strong></td><td>未優化</td></tr>
<tr><td><strong>指導：</strong></td><td>更新至最新視窗，確保您使用最新的固件和驅動程式。 建議您隨時將裝置保持在最新狀態</td></tr>
</table>

<table>
<tr><th colspan="2">免費硬碟空間</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查空閒硬碟空間是否不足。</td></tr>
<tr><td><strong>值：</strong></td><td>66%</td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>為了獲得最佳效果，您的硬碟至少應具有 10% 的可用空間。</td></tr>
</table>

<table>
<tr><th colspan="2">功能不全的裝置</th></tr>
<tr><td><strong>描述：</strong></td><td>Device Manager 中功能不全的裝置清單。</td></tr>
<tr><td><strong>值：</strong></td><td></td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>Device Manager 中的非功能裝置可能會導致 Surface 裝置發生無法預測的問題，例如，但不限於，各硬體元件不會節省電力。</td></tr>
</table>

<table>
<tr><th colspan="2">外部監視器</th></tr>
<tr><td><strong>描述：</strong></td><td>檢查可能有相容性問題的外部監視器。</td></tr>
<tr><td><strong>值：</strong></td><td></td></tr>
<tr><td><strong>條件：</strong></td><td>最優</td></tr>
<tr><td><strong>指導：</strong></td><td>請與原始設備製造商確認您的 Surface 裝置相容性。</td></tr>
</table>
