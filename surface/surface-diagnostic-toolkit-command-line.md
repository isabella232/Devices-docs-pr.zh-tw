---
title: 使用命令執行商務用 Surface 診斷工具組
description: 如何在命令主控台中執行表面診斷工具箱
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
ms.openlocfilehash: 6a56e1231ff5d2f672305d7166bbfa46d1bc0354
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831198"
---
# 使用命令執行商務用 Surface 診斷工具組

在命令提示字元上執行表面診斷工具箱（SDT）需要下載 STD app 主控台。 安裝完成後，您可以透過 Windows 命令主控台（cmd.exe）或使用 Windows PowerShell （包括 PowerShell 整合腳本環境（ISE））在命令提示字元執行 SDT，這會提供支援命令、複製/貼上及其他功能的自動完成。  如需在 SDT 中支援的 Surface 裝置清單，請參閱適用于[企業的部署表面診斷工具](surface-diagnostic-toolkit-business.md)組。

>[!NOTE]
>若要使用命令執行 SDT，您必須登入系統管理員帳戶，或登入的帳戶是您 Surface 裝置上的系統管理員群組的成員。

## 執行 SDT 應用程式主控台

從 [ [Surface Tools FOR IT 下載] 頁面](https://www.microsoft.com/download/details.aspx?id=46703)下載並安裝 SDT 應用程式主控台。 您可以使用 Windows 命令提示字元（cmd.exe）或 Windows PowerShell 來執行下列作業： 

- 收集所有記錄檔。
- 使用最佳做法分析程式來執行健康情況診斷。
- 檢查更新缺少固件或驅動程式更新。

>[!NOTE]
>在這個版本中，SDT 應用程式主控台只支援單一命令。 執行多個命令列選項需要針對每個命令單獨執行主控台 exe。 

根據預設，輸出檔案會儲存在與主控台 app 相同的位置。 請參閱下表以取得完整的命令清單。

命令 | 附註
--- | ---
-DataCollector "輸出檔案" | 將系統詳細資料收集到 zip 檔案中。 "輸出檔案" 是建立系統詳細資料 zip 檔案的檔案路徑。<br><br>**範例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -DataCollector SDT_DataCollection.zip`
-bpa "輸出檔案" | 檢查裝置中的數個設定和健康指示。 "輸出檔案" 是建立 HTML 報表的檔路徑。<br><br>**範例**：<br>`Microsoft.Surface.Diagnostics.App.Console.exe -bpa BPA.html`
-windowsupdate | 針對缺少的固件和/或驅動程式更新，檢查 Windows 更新線上伺服器。<br><br>**範例**：<br>Microsoft.Surface.Diagnostics.App.Console.exe windowsupdate
-保修 "輸出檔案" | 檢查裝置上的保修資訊（有效或無效）。 選用的 "輸出檔案" 是建立 xml 檔案的檔路徑。 <br><br>**範例**： <br>Microsoft.Surface.Diagnostics.App.Console.exe –質保 "warranty.xml"


>[!NOTE]
>若要在目標裝置上遠端執行 SDT 應用程式主控台，您可以使用諸如 Microsoft 端點設定管理員之類的建構管理工具。 或者，您也可以建立包含主控台 app 和適當的主控台命令的 .zip 檔案，然後根據貴組織的軟體發佈程式進行部署。 

## 運行最佳做法分析程式 

您可以跨主要元件（例如 BitLocker、安全啟動和受信任的平臺模組（TPM））執行 BPA 測試，然後將結果輸出到可共用的檔案。 此工具會產生一系列的資料表，其中包含以色彩標示的標題和條件描述項，以及如何解決問題的指導方針。 

- 綠色表示該元件正在以最佳條件執行（最佳）。
- 橙色表示元件沒有在最佳條件中執行（不是最佳的）。
- 紅色表示元件處於異常狀態。 

### 範例 BPA 結果輸出

<table>
<tr><th colspan="2"><font color="00ff00">BitLocker</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已在系統磁碟機上啟用 BitLocker。</td></tr>
<tr><td><strong>有效值</strong></td><td>保護開啟</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>強烈建議您啟用 BitLocker 來保護您的資料。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">安全開機</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用 [安全引導]。</td></tr>
<tr><td><strong>有效值</strong></td><td>True</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>強烈建議啟用 [安全啟動] 來保護您的電腦。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">信賴平台模組</font></th></tr>
<tr><td><strong>描述：</strong></td><td>確保 TPM 正常運作。</td></tr>
<tr><td><strong>有效值</strong></td><td>True</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>如果沒有正常運作的 TPM，安全的功能（例如 BitLocker）可能無法正常運作。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">連線待機</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用 [連線待機] 功能。</td></tr>
<tr><td><strong>有效值</strong></td><td>True</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>[已連接待機] 可讓 Surface 裝置在未使用時接收更新和通知。 為了獲得最佳體驗，請啟用 [連線待機]。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">藍牙</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用藍牙功能。</td></tr>
<tr><td><strong>有效值</strong></td><td>啟用</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td></td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">偵錯模式</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查作業系統是否處於偵錯模式。</td></tr>
<tr><td><strong>有效值</strong></td><td>一般</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>[調試引導] 選項可啟用或停用 Windows 作業系統的內核調試。 啟用此選項可能會造成系統不穩定，而且可以避免 DRM （數位版權 managemend）受保護的媒體無法播放。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">測試簽署</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否已啟用測試簽章。</td></tr>
<tr><td><strong>有效值</strong></td><td>一般</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>[測試簽章] 是 Windows 啟動設定，只應該用來測試預發行的驅動程式。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">使用中的電源配置</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查正確的電源配置是否處於作用中狀態。</td></tr>
<tr><td><strong>有效值</strong></td><td>平衡</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>強烈建議您使用「已平衡」電源配置，以最大限度地提高生產力和電池使用時間。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="ff9500">Windows Update</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查裝置是否為最新的 Windows 更新。</td></tr>
<tr><td><strong>有效值</strong></td><td>Microsoft Silverlight （KB4023307），適用于 Windows Defender 防病毒的定義更新-KB2267602 （定義1.279.1433.0）</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="ff9500">不是最佳</font></td></tr>
<tr><td><strong>級</strong></td><td>更新至最新的 windows 可確保您位於最新的固件和驅動程式。 建議您始終將您的裝置保持在最新狀態</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">可用磁片磁碟空間</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否有低可用的磁片磁片磁碟機空間。</td></tr>
<tr><td><strong>有效值</strong></td><td>66%</td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>為了獲得最佳效能，您的硬碟應該至少有10% 的容量作為可用空間。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">無法運作的裝置</font></th></tr>
<tr><td><strong>描述：</strong></td><td>裝置管理器中無法運作的裝置清單。</td></tr>
<tr><td><strong>有效值</strong></td><td></td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>在裝置管理器中無法正常運作的裝置，可能會導致表面裝置（例如但不限於）不會因個別硬體元件而節省電源的問題。</td></tr>
</table>

<table>
<tr><th colspan="2"><font color="00ff00">外部監視器</font></th></tr>
<tr><td><strong>描述：</strong></td><td>檢查是否有可能有相容性問題的外部監視器。</td></tr>
<tr><td><strong>有效值</strong></td><td></td></tr>
<tr><td><strong>疾病</strong></td><td><font color="00ff00">實現</font></td></tr>
<tr><td><strong>級</strong></td><td>與原始設備製造商確認與 Surface 裝置的相容性。</td></tr>
</table>
