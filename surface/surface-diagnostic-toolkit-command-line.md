---
title: 使用命令執行商務用 Surface 診斷工具組
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
ms.openlocfilehash: f3856499bd769b96e22c0a47323c984eb38d8a18
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327327"
---
# 使用命令執行商務用 Surface 診斷工具組

在命令提示 (SDT) 執行 Surface 診斷工具套件，需要下載 SDT 應用程式主控台。 安裝之後，您可以透過 Windows 命令主控台 (cmd.exe) 或 Windows PowerShell ，包括 PowerShell 整合式腳本環境 (ISE) ，在命令、複製/貼上及其他功能自動完成時，在命令提示符上執行 SDT。  有關 SDT 中支援的 Surface 裝置清單，請參閱部署商務用 [Surface 診斷工具組](surface-diagnostic-toolkit-business.md)。

>[!NOTE]
>若要使用命令執行 SDT，您必須已登錄系統管理員帳戶，或是在 Surface 裝置上是系統管理員群組成員的帳戶。

##  <a name="running-sdt-app-console"></a>執行 SDT 應用程式主機

從適用于 IT 的 Surface Tools 下載頁面 [下載並安裝 SDT 應用程式主機](https://www.microsoft.com/download/details.aspx?id=46703)。 您可以使用 Windows 命令提示 (cmd.exe) 或 Windows PowerShell 執行以下操作： 

- 收集所有記錄檔案。
- 使用最佳做法分析程式執行健康診斷。
- 檢查更新中缺少的中或驅動程式更新。

>[!NOTE]
>在這個版本中，SDT 應用程式主機僅支援單一命令。 執行多個命令列選項需要個別執行每個命令的主控台執行。 

根據預設，輸出檔案會儲存于與主控台應用程式相同的位置。 請參閱下表以查看完整的命令清單。

命令 | 附註
--- | ---
-DataCollector "output file" | 將系統詳細資料收集到 zip 檔案中。 「輸出檔案」是建立系統詳細資料 zip 檔案的檔案路徑。<br><br>**範例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "output file" | 檢查裝置中的多個設定和健康情況指示器。 「輸出檔案」是建立 HTML 報表的檔案路徑。<br><br>**範例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | 檢查 Windows Update 線上伺服器中缺少的內文和/或驅動程式更新。<br><br>**範例**：<br>Microsoft.Surface.Diagnostics.App.Console.exe -windowsupdate
-保固「輸出檔案」 | 檢查裝置上的保固資訊 (有效或無效) 。 選擇性的「輸出檔案」是建立 xml 檔案的檔案路徑。 <br><br>**範例**： <br>Microsoft.Surface.Diagnostics.App.Console.exe –保固 「warranty.xml」


>[!NOTE]
>若要在目標裝置上遠端執行 SDT 應用程式主控台，您可以使用 Microsoft 端點群組原則管理員等群組原則管理工具。 或者，您可以建立一個 .zip 檔案，其中包含主控台應用程式及適當的主控台命令，並且根據貴組織的軟體發佈程式進行部署。 

##  <a name="running-best-practice-analyzer"></a>執行最佳做法分析程式 

您可以在 BitLocker、Secure Boot 和信任的平臺模組 (TPM) 等重要元件上執行 BPA 測試，然後將結果輸出至可共用檔案。 此工具會產生一系列表格，包含色彩編碼的標題和條件描述項，以及有關如何解決此問題的指引。 

- 綠色表示元件以最佳狀態執行， (優化) 。
- 橘色表示元件未在最佳狀況下執行， (優化) 。
- 紅色表示元件狀態異常。 

###  <a name="sample-bpa-results-output"></a>BPA 結果輸出範例

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查系統磁碟機上是否已啟用 BitLocker。</td></tr>
<tr><td><strong>價值：</strong></td><td>保護已上</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>強烈建議您啟用 BitLocker 來保護您的資料。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">安全開機</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用安全開機。</td></tr>
<tr><td><strong>價值：</strong></td><td>True</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>強烈建議您啟用安全開機來保護您的電腦。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">信賴平台模組</font></th></tr>
<tr><td><strong>描述：</strong></td><td>確保 TPM 能夠運作。</td></tr>
<tr><td><strong>價值：</strong></td><td>True</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>如果沒有功能性 TPM，例如 BitLocker 等安全性函數可能無法正常運作。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">已連接待命</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用連接待命。</td></tr>
<tr><td><strong>價值：</strong></td><td>True</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>已連接待命可讓 Surface 裝置在未使用時接收更新和通知。 為了獲得最佳體驗，應該啟用連接待命。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">藍牙</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查藍牙是否已啟用。</td></tr>
<tr><td><strong>價值：</strong></td><td>啟用</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">Debug 模式</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查作業系統是否位於 Debug 模式。</td></tr>
<tr><td><strong>價值：</strong></td><td>一般</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>啟用或停用 Windows 作業系統之核心的啟動啟動選項。 啟用此選項可能會導致系統不穩定，並可防止 DRM (受保護媒體) 數位版權管理。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">測試簽署</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用測試簽署。</td></tr>
<tr><td><strong>價值：</strong></td><td>一般</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>測試簽署是 Windows 啟動設定，應該只能用來測試版驅動程式。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">使用中電源配置</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查正確的電源配置為使用中。</td></tr>
<tr><td><strong>價值：</strong></td><td>平衡</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>強烈建議使用「平衡」電源配置，以最大化生產力和電池使用時間。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows Update</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查裝置是否使用 Windows 更新為最新狀態。</td></tr>
<tr><td><strong>價值：</strong></td><td>Microsoft Silverlight (KB4023307) ，Windows Defender 防毒軟體的定義更新 - KB2267602 (定義 1.279.1433.0) </td></tr>
<tr><td><strong>條件：</strong></td><td><font color="ff9500">非優化</font></td></tr>
<tr><td><strong>指導：</strong></td><td>更新至最新的視窗，確保您使用最新的新版或驅動程式。 建議您隨時將裝置保持在最新狀態</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">免費硬碟空間</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查低免費硬碟空間。</td></tr>
<tr><td><strong>價值：</strong></td><td>66%</td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>為了獲得最佳效果，您的硬碟至少應擁有 10% 的可用空間。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">功能不全的裝置</font></th></tr>
<tr><td><strong>描述：</strong></td><td>Device Manager 中功能不運作的裝置清單。</td></tr>
<tr><td><strong>價值：</strong></td><td></td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>Device Manager 中無法運作的裝置可能會導致 Surface 裝置發生無法預期的問題，例如 ，但不限於，無法節省各硬體元件的電力。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">外部監視器</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查可能有相容性問題的外部監視器。</td></tr>
<tr><td><strong>價值：</strong></td><td></td></tr>
<tr><td><strong>條件：</strong></td><td><font color="00ff00">最優</font></td></tr>
<tr><td><strong>指導：</strong></td><td>請與原始設備製造商確認您的 Surface 裝置相容性。</td></tr>
</table>
