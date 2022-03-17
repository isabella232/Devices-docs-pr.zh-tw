---
title: Surface Hub 更新歷程記錄
description: Surface Hub 更新歷程記錄
ms.assetid: d66a9392-2b14-4cb2-95c3-92db0ae2de34
keywords: ''
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: dpandre
ms.topic: article
ms.localizationpriority: high
ms.openlocfilehash: a5556181b6d7642933bcb10c3073ffddc494015f
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449126"
---
# <a name="surface-hub-update-history"></a>Surface Hub 更新歷程記錄

Windows 10 是專為服務所設計，這表示它會自動透過定期軟體更新而變得更好。 好消息是，您通常不需要執行任何動作，即可取得最新的 Windows 10 更新 — 系統會在更新可供使用時，自動下載並安裝。

大部分 Windows 更新的重點在於效能和安全性改良，以便全年無休的運作。

我們得知您希望深入了解 Windows 10 的更新內容，因此會在此頁面上提供更多詳細資料。 在下列清單中，會先列出具有 Surface Hub 特定改良功能的最新 Windows 更新。 更新是累積性，因此安裝最新的可用 Windows 更新 (即使未列在下方清單中) 也可確保您受益于任何先前更新的改良功能。 Microsoft Store 應用程式會透過 Microsoft Store 更新 (由 Surface Hub 的系統管理員管理)。 有關應用程式更新的詳細資訊，會依各應用程式進行提供。

只要有新的更新發行，我們便會重新整理此頁面，因此請持續留意最新的資訊。 同時，感謝您協助我們學習成長，透過每次更新變得更好！

請參閱 [[Surface Hub 重要資訊](https://support.microsoft.com/products/surface-devices/surface-hub)] 頁面，了解可能需要您注意的目前與過去版本相關主題。

## <a name="windows-10-team-2020-update-20h2"></a>Windows 10 團隊版 2020 更新 (20H2) 

<details>
<summary>2022 年 2 月 15 日 - 根據 KB5010415* (作業系統組建 19042.1566) 的團隊版更新</summary>

 此 Surface Hub 更新包括品質改良與安全性問題修正。 [Windows 10 團隊版 2020 更新 2](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-2) 中概述了 Surface Hub 的重要更新，同時也包含下列內容：

* 修正了允許在 [裝置帳戶] 設定期間停用 Exchange 服務的問題。
* 改善使用內部部署 Exchange 信箱時，某些 [裝置帳戶] 設定案例的可靠性。
* 提高了使用 SurfaceHub CSP 時某些 MDM 原則設定案例的可靠性。
* 提高了在使用商務用 Skype 時來電案例的可靠性。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB5010415](https://support.microsoft.com/help/5010415)
</details>

<details>
<summary>2022 年 1 月 25 日 - 根據 KB5009596* (作業系統組建 19042.1503) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4581839/windows-10-update-history) 中概述，包括：

* 解決 Surface Hub 無法向其已設定的 Azure Log Analytics 工作區報告資料的問題。
* 解決從 Surface Hub 的 [歡迎] 畫面啟動商務用 Skype 會議可能會導致 SfB 用戶端完全最大化，無法最小化的問題。
* 解決加入 Azure AD 的 Surface Hub 不會預先使用會議受邀者清單填入 [會議與檔案] 登錄的問題。
* 解決某些內部部署案例無法啟用裝置帳戶密碼輪替的問題。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB5009596](https://support.microsoft.com/help/5009596)
</details>

<details>
<summary>2022 年 1 月 21 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface UEFI 更新 - 694.3924.768.0
  * 改善系統安全性與穩定性。
* Intel(R) Management Engine Interface 驅動程式 - 2120.100.0.1085
  * 改善系統安全性與穩定性。
</details>

<details>
<summary>2021 年 11 月 22 日 - 根據 KB5007253* (作業系統組建 19042.1387) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4581839/windows-10-update-history) 中概述，包括：

* 在 Surface Hub 上使用 MDM 原則設定 [自訂名稱] 時，會強制執行 32 個字元限制的修正。
* 當 AllowStorageCard MDM 從值 0 還原為值 1 (允許的儲存空間) 時，會校正 AllowStorageCard MDM 原則行為的修正。
* 更新以允許 Edge (Chromium) 瀏覽器存取 [檔案總管] 中可存取的相同檔案位置，包括連接的 USB 磁碟機。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB5007253](https://support.microsoft.com/help/5007253)
</details>

<details>
<summary>2021 年 9 月 30 日 - KB5004196、KB5004198 和 KB5004199</summary>

這些對 Surface Hub 的更新可提供 Teams 會議室用戶端、Teams 系統管理中心代理程式及受管理的會議室代理程式。 [Surface Hub 中的 Teams 會議室](surface-hub-teams-rooms.md) 概述了主要功能。
 
如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
</details>

<details>
<summary>2021 年 9 月 30 日 - 根據 KB5005611* (作業系統組建 19042.1266) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4581839/windows-10-update-history) 中概述，包括：

* 使用模式 2 功能 (僅適用于 Teams) 取代會議模式 1 (Teams 偏好/SfB 可用)；這兩個設定都可以使用，但兩者的效果相同。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB5005611](https://support.microsoft.com/help/5005611)
</details>

<details>
<summary>2021 年 9 月 1 日 - 根據 KB5005101* (作業系統組建 19042.1202) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 [Windows 10 團隊版 2020 更新 1](surface-hub-2020-update-whats-new.md#windows-10-team-2020-update-1) 中概述了 Surface Hub 的重要更新，同時也包含下列內容：

* 改善使用內部部署 Exchange 信箱時，某些 [裝置帳戶] 設定案例的可靠性。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB5005101](https://support.microsoft.com/help/5005101)
</details>

<details>
<summary>2021 年 7 月 29 日 - 根據 KB5004296* (作業系統組建 19042.1151) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4581839/windows-10-update-history) 中概述，包括：

* 更新至「收集記錄」功能，以 csv 格式包含 Windows 診斷資料。
* 可確保 [結束工作階段] 清理完全移除與 Edge Chromium 相關的所有資料之修正。
* 改善使用 [驗證器] 應用程式時，加入 Azure AD 的 Surface Hub 的某些案例。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB5004296](https://support.microsoft.com/help/5004296)
</details>

<details>
<summary>2021 年 6 月 10 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface UEFI 更新 - 694.3751.768.0
  * 處理重大資訊安全漏洞並改善系統穩定性。
* Surface ME 韌體更新 - 11.8.86.3877
  * 處理重大資訊安全漏洞並改善系統穩定性。
* Intel(R) Management Engine Interface驅動程式 - 2102.100.0.1044
  * 處理重大資訊安全漏洞並改善系統穩定性。
</details>

<details>
<summary>2021 年 4 月 13 日 - 根據 KB5001330* (作業系統組建 19042.928) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4581839/windows-10-update-history) 中概述，包括：

* 解決某些 Surface Hub 裝置只安裝每月 Windows 安全性更新，而非所有 Windows 累積更新的問題。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB5001330](https://support.microsoft.com/help/5001330)
</details>

<details>
<summary>2021 年 3 月 13 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Intel(R) 藍牙驅動程式 - 22.30.0.4
  * 改善系統安全性與穩定性。
* Intel(R) 圖形驅動程式 - 27.20.100.8682
  * 改善系統安全性與穩定性。
* Intel(R) Wi-Fi 驅動程式 - 22.30.0.11
  * 改善系統安全性與穩定性。
</details>

<details>
<summary>2021 年 2 月 2 日 - 根據 KB4598291* (作業系統組建 19042.789) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4581839/windows-10-update-history) 中概述，包括：

* 當 [裝置帳戶] 的 UPN 不等於其 SMTP 時，允許與 Exchange 進行行事曆同步處理的修正。
* 新增系統管理員在與 Exchange 進行行事曆同步處理期間，停用新式驗證的能力。
* 確保啟用「使用裝置帳號憑證」功能之後，不會提示 Surface Hub 使用者輸入 Proxy 認證。
* 解決若使用需要驗證的 Proxy 時，Windows Update 和 Store 更新檢查永遠不會完成的問題。
* 改善有線內接案例期間，[連接應用程式] 的可靠性。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB4598291](https://support.microsoft.com/help/4598291)
</details>

<details>
<summary>2021 年 1 月 15 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface SMC 韌體更新 - 3.93.139.0
* Surface UEFI 更新 - 694.3473.768.0
</details>

<details>
<summary>2020 年 12 月 11 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface SMC 韌體更新 - 3.92.139.0
* Surface UEFI 更新 - 694.3447.768.0
</details>

<details>
<summary>2020 年 11 月 30 日 - 根據 KB4586853* (作業系統組建 19042.662) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4581839/windows-10-update-history) 中概述，包括：

* 更新至 [隱私權設定] 頁面以提供其他選項。
* 解決已啟動的會議未顯示在 [歡迎]/[開始] 畫面的問題。
* 解決非美國地區之雲端復原的問題。
* 商務用 Skype
  * 改善方向音訊的效能。
  * 降低在商務用 Skype 通話期間使用手寫筆時的「手寫筆點選」音效。
* 改善註冊 Windows 測試人員計畫的可靠性。
* 改善 Windows 團隊版殼層的可靠性。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。 *[KB4586853](https://support.microsoft.com/help/4586853)
</details>

<details>
<summary>2020 年 11 月 24 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface SMC 韌體更新 - 3.91.139.0
  * 改善連線待命可靠性。
* Surface Touch 韌體更新 - 3.91.139.0
  * 改善連線待命觸控回應。
* Surface USB 音訊韌體更新 - 3.91.139.0
* Surface 觸控筆韌體更新 - 3.91.139.0
</details>

<details>
<summary>2020 年 10 月 27 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface System Aggregator 韌體更新 - 4.14.139.0
* Surface UEFI 更新 - 694.3386.768.0
</details>

<details>
<summary>適用於 Surface Hub 的 Windows 10 團隊版 2020 更新 - 一般版本資訊 (作業系統組建 19042.572)</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 尚未在 [Windows 10 更新記錄](https://support.microsoft.com/help/4581839/windows-10-update-history) 中概述的 Surface Hub 的重要更新，會記錄在「[Windows 10 團隊版 2020 更新的新功能](/surface-hub/surface-hub-2020-update-whats-new)」頁面上。

請參閱「[安裝 Windows 10 團隊版 2020 更新](/surface-hub/surface-hub-2020-update)」頁面，以瞭解有關更新可用性 (按地區、發佈方法和裝置類型) 的資訊。
</details>

## <a name="windows-10-team-creators-update-1703"></a>Windows 10 團隊版 Creators 更新 (1703) 

<details>
<summary>2020 年 9 月 1 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface SMC 韌體更新 - 1.177.139.0
  * 改善欄位修復案例。
* Surface SSD 韌體更新 - 5.14.139.0
  * 改善系統穩定性。
* Surface Serial Hub 驅動程式 - 9.40.139.0
  * 改善系統穩定性。
</details>

<details>
<summary>2020 年 5 月 4 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface USB 音訊驅動程式 - 15.3.6.0
  * 改善方向音訊的效能。
* Intel(R) 顯示音訊驅動程式 - 10.27.0.5
  * 改善螢幕共用案例。
* Intel(R) 圖形驅動程式 - 26.20.100.7263
  * 改善系統穩定性。
* Surface 系統驅動程式 - 1.7.139.0
  * 改善系統穩定性。
* Surface SMC 韌體更新 - 1.176.139.0
  * 改善系統穩定性。
</details>

<details>
<summary>2020 年 2 月 28 日 - 適用於 Surface Hub 2S 的更新</summary>

此更新是 Surface Hub 2S 特有的更新，並提供以下所述的驅動程式和韌體更新：

* Surface Integration 驅動程式 - 13.46.139.0 
  * 改善顯示亮度案例。
* Intel(R) Management Engine Interface驅動程式 - 1914.12.0.1256
  * 改善系統穩定性。
* Surface SMC 韌體更新 - 1.161.139.0
  * 改善觸控筆電池效能。
* Surface UEFI 更新 - 694.2938.768.0
  * 改善系統穩定性。
</details>

<details>
<summary>2020 年 2 月 11 日 - 根據 KB4537765* (作業系統組建 15063.2284) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 解決在商務用 Skype 通話期間，其他參與者無法清楚聽到 Hub 2S 的問題。
* 改善在 Surface Hub 上某些阿拉伯文、希伯來文及其他 RTL 語言使用案例的可靠性。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4537765](https://support.microsoft.com/help/4537765)
</details>

<details>
<summary>2020 年 1 月 14 日 - 根據 KB4534296* (作業系統組建 15063.2254) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 處理 Microsoft Surface Hub 2S 記錄集合的問題。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4534296](https://support.microsoft.com/help/4534296)
</details>

<details>
<summary>2019 年 9 月 24 日 - 根據 KB4516059* (作業系統組建 15063.2078) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

 * 更新至 Surface Hub 2S 修復設定頁面，以正確反映復原選項。
 * 更新至 Surface Hub 2S [歡迎] 畫面以改善裝置可識別性。
 * 已處理 Windows 團隊版殼層背景顯示錯誤的問題。
 * 已處理使用 MDM 原則進行設定時，[開始功能表] 版面配置持續性的問題。
 * 已修正瀏覽某些內部網站時，Microsoft Edge 中所發生的問題。
 * 已修正以全螢幕模式進行簡報時所發生的商務用 Skype 問題。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>2019 年 8 月 17 日 - 根據 KB4512474* (作業系統組建 15063.2021) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

 * 確保 Hub 2S 上的 Video Out 預設為「重複」模式。
 * 改善在 Surface Hub 上某些阿拉伯文使用案例的可靠性。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4503289](https://support.microsoft.com/help/4503289)
 </details>

<details>
<summary>2019 年 6 月 18 日 - 根據 KB4503289* (作業系統組建 15063.1897) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 處理使用者無法以 Azure Active Directory 帳戶來登錄 Microsoft Surface Hub 裝置的問題。 發生此問題的原因是先前的工作階段未成功結束的關係。
* 在裝置帳戶設定案例新增對識別提供者和 Exchange 的 TLS 1.2 連接支援。
* 改善 Hub 2S 上 [硬體診斷應用程式] 可靠性的修正。 
* 改善 Hub 2S 上首次執行安裝體驗的一致性之修正。 

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4503289](https://support.microsoft.com/help/4503289)
</details>

<details>
<summary>2019 年 5 月 28 日 - 根據 KB4499162* (作業系統組建 15063.1835) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 確保啟用「使用裝置帳號憑證」功能之後，不會提示 Surface Hub 使用者輸入 Proxy 認證。
* 解決因為音訊/視訊未使用正確的 Proxy，導致 Skype 連接定期失敗的問題。
* 在商務用 Skype 中新增對 TLS 1.2 的支援。
* 解決 Skype 伺服器停用 TLS 1.0 或 TLS 1.1 時，Skype 用戶端的 SIP 連接失敗。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4499162](https://support.microsoft.com/help/4499162)
</details>

<details>
<summary>2019 年 4 月 25 日 - 根據 KB4493436* (作業系統組建 15063.1784) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 解決某些連接到 Surface Hub 的 USB 裝置出現視訊和音訊的同步處理問題。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4493436](https://support.microsoft.com/help/4493436)
</details>

<details>
<summary>2018 年 11 月 27 日 - 根據 KB4467699* (作業系統組建 15063.1478) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 處理導致某些使用者無法登錄「我的會議和檔案」的問題。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KBKB4467699](https://support.microsoft.com/help/KB4467699)
</details>

<details>
<summary>2018 年 10 月 18 日 - 根據 KB4462939* (作業系統組建 15063.1418) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 商務用 Skype 修正： 
  * 解決從睡眠狀態恢復時商務用 Skype 的連線問題
  * 解決裝置連線到網路時，商務用 Skype 的網路連線問題
  * 解決從目錄搜尋使用者時，商務用 Skype 當機的問題
* 解決 Hub 錯誤地回報企業 Proxy 環境中「沒有網路連線」的問題。
* 已實施一項功能，允許客戶選擇加入新的 [白板] 體驗。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4462939](https://support.microsoft.com/help/4462939)
</details>

<details>
<summary>2018 年 8 月 31 日 - 根據 KB4343889* (作業系統組建 15063.1292) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 新增對 Microsoft Teams 的支援
* 解決使用 Intune 註冊的工作管理問題
* 可讓系統管理員停用 Hub 的立即訊息和電子郵件服務
* 適用於 Surface Hub 商務用 Skype 應用程式的其他錯誤修正與可靠性改進

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4343889](https://support.microsoft.com/help/4343889)
</details>

<details>
<summary>2018 年 6 月 21 日 - 根據 KB4284830* (作業系統組建 15063.1182) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 支援 EMEA 中的 GDPR 需求的遙測變更

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4284830](https://support.microsoft.com/help/KB4284830)
</details>

<details>
<summary>2018 年 4 月 17 日 - 根據 KB4093117* (作業系統組建 15063.1058) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 解決有線投影問題
* 啟用特定 MDM (行動裝置管理) 原則的大量更新
* 解決國際通話的電話撥號程式問題
* 處理 2 個 Surface Hub 加入相同會議時的圖像解析度問題
* 解決 OMS (Operations Management Suite) 憑證處理錯誤
* 處理在工作階段結束時進行清除的安全性問題
* 處理當 Surface Hub 指定給頻道 149 到 165 時發生的 Miracast 問題
  * 由於區域政府法規，歐洲、日本或以色列將依然無法使用頻道 149 到 165

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4093117](https://support.microsoft.com/help/4093117)
</details>

<details>
<summary>2018 年 2 月 23 日 - 根據 KB4077528* (作業系統組建 15063.907) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 解決未正確套用 MDM 設定的問題
* 改善清理程序

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4077528](https://support.microsoft.com/help/4077528)
</details>

<details>
<summary>2018 年 1 月 16 日 - 根據 KB4057144* (作業系統組建 15063.877) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 新增透過 MDM 管理 [開始] 功能表磚配置的能力
* 密碼輪替設定的 MDM 錯誤修正

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4057144](https://support.microsoft.com/help/4057144)
</details>

<details>
<summary>2017 年 12 月 12 日 - 根據 KB4053580* (作業系統組建 15063.786) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 解決相機視訊在商務用 Skype 通話期間閃爍 (撕裂或閃動) 的問題
* 解決通知中心 SSD ID 問題

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4053580](https://support.microsoft.com/help/4053580)
</details>

<details>
<summary>2017 年 11 月 14 日 - 根據 KB4048954* (作業系統組建 15063.726) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 允許客戶使用 MDM 原則啟用 802.1x 有線網路驗證的功能更新。
* 可讓使用者在開啟檔案時，動態選取自選應用程式的功能更新。
* 可確保 [結束工作階段] 清理會完全移除使用者帳戶及裝置間的連線的修正。
* 可改進清理時間以及 Miracast 連線時間的效能修正。
* 引進在臨時會議期間使用簡單驗證。
* 可確保服務元件使用在裝置間設定的相同 Proxy 的修正。
* 減少及更徹底保護裝置傳送的遙測資料，以減少頻寬使用量。
* 啟用允許使用者在會議結束後提供意見反應給 Microsoft 的功能。

如需啟用/停用裝置功能和服務的詳細資訊，請參閱 [Surface Hub 系統管理員指南](/surface-hub/)。
*[KB4048954](https://support.microsoft.com/help/4048954)
</details>

<details>
<summary>2017 年 10 月 10 日 - 根據 KB4041676* (作業系統組建 15063.674) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 商務用 Skype
  * 解決從睡眠狀態恢復時，需要重新開機裝置的問題。
  * 修正外部連絡人無法透過 Skype Online Hub 帳戶解析問題。
* PowerPoint
  * 修正某些 PowerPoint 簡報無法投影到 Hub 的問題。
* 一般
  * 修正以解決系統管理員無法停用 USB 連接埠的問題。

*[KB4041676](https://support.microsoft.com/help/4041676)
</details>

<details>
<summary>2017 年 9 月 12 日 - 根據 KB4038788* (作業系統組建 15063.605) 的團隊版更新 </summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 安全性
  * 解決裝置從睡眠狀態喚醒時的 Bitlocker 問題。
* 一般
  * 減少裝置健康情況遙測的頻率/數量，改善系統效能。
  * 修正導致裝置無法收集系統記錄檔的問題。

*[KB4038788](https://support.microsoft.com/help/4038788)
</details>

<details>
<summary>2017 年 8 月 1 日 — 根據 KB4032188* (作業系統組建 15063.498) 的團隊版更新</summary>

* 商務用 Skype 
  * 解決商務用 Skype 需要重試或系統重新開機的登入問題。
  * 解決商務用 Skype 會議的時間顯示不正確的問題。
  * 修正以改進 Surface Hub 商務用 Skype 的可靠性。

*[KB4032188](https://support.microsoft.com/help/4032188)
</details>

<details>
<summary>2017 年 6 月 27 日 - 根據 KB4022716* (作業系統組建 15063.442) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 處理 NVIDIA 驅動程式當機，此問題可能迫使處於睡眠模式的 84" Surface Hub 電源關閉，需要手動重新開機。
* 解決部分應用程式無法在 84" Surface Hub 上啟動的問題。

*[KB4022716](https://support.microsoft.com/help/4022716)
</details>

<details>
<summary>2017 年 6 月 13 日 - 根據 KB4022725* (作業系統組建 15063.413) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 一般
  * 已解決使用手寫筆時，手寫筆筆跡中斷的問題
  * 解決造成「清理」會議時時間延長的問題

*[KB4022725](https://support.microsoft.com/help/4022725)
</details>

<details>
<summary>2017 年 5 月 24 日 - 根據 KB4021573* (作業系統組建 15063.328) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 一般
  * 已解決更新期間 Proxy 設定保留的問題

*[KB4021573](https://support.microsoft.com/help/4021573)
</details>

<details>
<summary>2017 年 5 月 9 日 - 根據 KB4016871* (作業系統組建 15063.296) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 一般
  * 已處理睡眠/喚醒循環問題
  * 已解決數個重設和復原問題
  * 已處理 [更新記錄] 索引標籤問題
  * 已解決 Miracast 服務啟動問題
* 應用程式
  * 已修正應用程式套件更新錯誤

*[KB4016871](https://support.microsoft.com/help/4016871)
</details>

<details>
<summary>適用於 Surface Hub 的 Windows 10 團隊版 Creators Update 1703 — 一般版本資訊 (作業系統組建 15063.0)</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 改良大型螢幕體驗 
  * 已改進 [歡迎] 與 [開始] 畫面中的會議浮動切換
  * 直接從 [開始] 功能表加入會議及結束工作階段
  * 應用程式在工作階段期間可以運用更多螢幕空間
  * 簡化 Skype 控制項
  * 已改善提供意見反應的機制
* 存取我的個人內容*
  * 從 [歡迎] 或 [開始] 畫面進行個人單一登入
  * 直接從 [開始] 功能表加入會議及結束工作階段
  * 直接從 [開始] 畫面透過商務用 OneDrive 存取個人檔案
  * 預先填入的出席登登錄
  * 使用「驗證器」應用程式簡化驗證流程**
* 部署與管理性 
  * 透過大量佈建簡化 OOBE 體驗
  * 雲端式裝置修復服務
  * 企業用戶端憑證支援
  * 改善 Proxy 認證支援
  * 新增與改善 Skype 服務品質 (QoS) 設定支援
  * 新增在 [設定] 中設定預設裝置音量的功能
  * 改善針對 Surface Hub [設定](/surface-hub/remote-surface-hub-management)的 MDM 支援
* 已改善的安全性 
  * 已新增將 USB 磁碟機限制為僅限 BitLocker 的能力
  * 已新增透過 MDM 停用 USB 連接埠的能力
  * 已新增在逾時時停用「繼續工作階段」功能的能力
  * 新增有線 802.1x 的支援
* 音訊與投影
  * Dolby Audio「人性化喇叭」增強功能
  * 降低在商務用 Skype 通話期間使用手寫筆時的「手寫筆點選」音效
  * 新增 Miracast 基礎結構連線的支援
* 可靠性和效能修正
  * 已解決數個重設和復原問題
  * 已解決使用用戶端憑證時的 Surface Hub Exchange 驗證問題
  * 已改善 Wi-Fi 網路連線和認證穩定性
  * 已修正視訊播放期間的 Miracast 音訊彈出和同步處理問題
  * 已加入停用自動連線行為的設定

*單一登入功能需要使用 Office365 和 商務用 OneDrive **請參閱 [系統管理指南] 以了解服務需求

</details>

## <a name="windows-10-team-anniversary-update-1607"></a>Windows 10 團隊版年度更新版 (1607)

<details>
<summary>2017 年 3 月 14 日 — 根據 KB4013429* (作業系統組建 14393.953) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 一般
  * [檔案總管] 的安全性問題修正，此問題會阻止瀏覽至限制的檔案位置
* 商務用 Skype
  * 修正以解決遠端桌面型螢幕畫面分享期間發生的延遲問題

*[KB4013429](https://support.microsoft.com/help/4013429)
</details>

<details>
<summary>2017 年 1 月 10 日 — 根據 KB4000825* (作業系統組建 14393.693) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 啟用選取 106/109 鍵盤配置以用於日文實體鍵盤

*[KB4000825](https://support.microsoft.com/help/4000825)
</details>

<details>
<summary>2016 年 12 月 13 日 — 根據 KB3206632* (作業系統組建 14393.576) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 解決有線連線音訊失真的問題

*[KB3206632](https://support.microsoft.com/help/3206632)
</details>

<details>
<summary>2016 年 11 月 4 日 - 根據 KB3200970* (作業系統組建 14393.447) 的團隊版更新</summary>

此適用於 Surface Hub 的 Windows 10 團隊版年度更新版 (版本 1607) 的更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 商務用 Skype 錯誤修正以改進可靠性

*[KB3200970](https://support.microsoft.com/help/3200970)
</details>

<details>
<summary>2016 年 10 月 25 日 - 根據 KB3197954* (作業系統組建 14393.351) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 在作業系統與 Bios 中啟用新的睡眠功能，降低 Surface Hub 的耗電量並改善其長期可靠性
* 一般
  * 解決螢幕小鍵盤有時候不會出現的狀況
  * 解決在開啟已排程會議時 [白板] 應用程式有時會移位的問題
  * 解決在重設裝置之後阻止系統管理員變更本機系統管理員密碼的問題
  * 變更 BIOS 以解決裝置重設期間狀態列追蹤的問題
  * 更新 UEFI 以解決關閉電源問題

*[KB3197954](https://support.microsoft.com/help/3197954)
</details>

<details>
<summary>2016 年 10 月 11 日 - 根據 KB3194496* (作業系統組建 14393.222) 的團隊版更新</summary>

此更新讓 Windows 10 團隊版年度更新版適用於 Surface Hub，並包括品質改良與安全性問題修正。 (安裝之後，您的裝置將會執行 Windows 10 版本 1607。) Surface Hub 的重要更新，尚未在 [Windows 10 更新記錄](https://support.microsoft.com/help/4018124/windows-10-update-history) 中列出，包括：

* 商務用 Skype
  * 改進加入會議時的效能，包括使用聯盟帳戶加入會議時的問題
  * 適用於 Surface Hub 的商務用 Skype 現已提供以視訊為基礎的螢幕共用 (VBSS) 支援
  * 已解決閒置 5 分鐘之後便會中斷連線的問題
  * 已解決 Skype Hub 到 Hub 螢幕畫面分享失敗的問題
  * 針對 Skype 視訊的改進內容，包括：
    * 在有多位視訊簡報者的會議中遺失視訊的問題
    * 在通話期間裁剪視訊
    * 撥出電話視訊不會顯示給其他參與者
  * 已處理 UPN 登入錯誤的問題
  * 已處理使用工作階段初始通訊協定 (SIP) 通話期間的撥號鍵台問題
* 白板
  * 使用者現在可以使用 OneDrive 線上服務儲存並恢復 [白板] 工作階段 (透過 [共用] 功能)
  * 改善從擴充座移除手寫筆時啟動 [白板]
* 應用程式
  * 預先安裝 OneDrive 應用程式，以存取您的個人和工作檔案
  * 預先安裝 [相片] 應用程式，以檢視相片和影片
  * 預先安裝 PowerBI 應用程式，以檢視儀表板
  * Office 應用程式 – Word、Excel、PowerPoint – 都已啟用筆跡
  * Surface Hub 上的 Edge 現在支援 Flash 型網站
* 一般
  * 已啟用音訊裝置選擇 (適用於使用外部音訊裝置連接的 Surface Hub)
  * 已啟用支援 DisplayPort 輸出接頭上的 HDCP
  * 對設定進行系統 UI 變更以將可用性最佳化 (如需詳細資訊，請參閱 [使用者和系統管理指南](https://www.microsoft.com/surface/support/surface-hub))
  * 錯誤修正和效能最佳化，以加速 Azure Active Directory 登錄流程
  * 已大幅改進重設與還原 Surface Hub 的所需時間
  * Windows Defender UI 已加入設定中
  * 已改善 UX 觸控以啟動
  * 已啟用支援透過 Miracast 在受支援的裝置上進行大於 1080p 的無線投影
  * 已解決啟動時，「沒有網際網路連線」和「預約可能已過期」的錯誤通知狀態
  * 已改善螢幕小鍵盤的可靠性
  * 其他支援，包括使用 Windows 映像處理與設定設計工具 (ICD) 建立 Surface Hub 佈建套件，以及改善 Operations Management Suite 上的 Surface Hub 監控解決方案

*[KB3194496](https://support.microsoft.com/help/3194496)
</details>

## <a name="updates-for-windows-10-version-1511"></a>適用於 Windows 10 版本 1511 的更新

<details>
<summary>2016 年 11 月 4 日 - 根據 KB3198586* (作業版本組建 10586.679) 的團隊版更新</summary>

此適用於 Surface Hub 的 Windows 10 團隊版 (版本 1511) 更新包括品質改良與安全性問題修正，如 [Windows 10 更新記錄](https://support.microsoft.com/help/4018124/windows-10-update-history)中所述。 此更新中沒有 Surface Hub 特定項目。

*[KB3198586](https://support.microsoft.com/help/3198586)
</details>

<details>
<summary>2016 年 7 月 12 日 - 根據 KB3172985* (作業系統組建 10586.494) 的團隊版更新</summary>

此更新包括品質改良與安全性修正。 本更新未引進任何新的作業系統功能。 Surface Hub 專屬的重要更新 (這些更新尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述)，包括：

* 已修正導致 Windows 系統當機的問題
* 已修正導致 Edge 重複當機的問題
* 已修正造成關機前服務當機的問題
* 已修正某些應用程式資料在工作階段後不正確移除的問題
* 已更新 Broadcom NFC 驅動程式以改善 NFC 效能
* 已更新 Marvell Wi-Fi 驅動程式，以改善 Miracast 效能
* 已更新 Nvidia 驅動程式，以修正 84" Surface Hub 裝置顯示過暗或模糊內容的顯示錯誤
* 已修正數個商務用 Skype 的問題，包括： 
  * 造成商務用 Skype 在會議期間中斷連線的問題
  * 會議召集人使用聯盟設定時，使用者無法加入會議的問題
  * 啟用商務用 Skype 應用程式共用
  * 造成 Skype 應用程式當機的問題
* 在「設定」中新增提示，通知使用者如果裝置重設在完成之前中斷可能會造成作業系統損毀

*[KB3172985](https://support.microsoft.com/help/3172985)
</details>

<details>
<summary>2016 年 6 月 14 日 - 根據 KB3163018* (作業系統組建 10586.420) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 本更新未引進任何新的作業系統功能。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 限制的版本。 請參閱 2016 年 7 月 12 日 — [KB3172985](https://support.microsoft.com/en-us/help/3172985) (作業系統組建 10586.494) 以了解 Surface Hub 特定套件詳細資料

*[KB3163018](https://support.microsoft.com/help/3163018)
</details>

<details>
<summary>2016 年 5 月 10 日 - 根據 KB3156421* (作業系統組建 10586.318) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 本更新未引進任何新的作業系統功能。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 已修正某些 Store 應用程式 (OneDrive) 無法安裝的問題
* 已修正造成應用程式中觸控輸入停止回應的問題

*[KB3156421](https://support.microsoft.com/help/3156421)
</details>

<details>
<summary>2016 年 4 月 12 日 - 根據 KB3147458* (作業系統組建 10586.218) 的團隊版更新</summary>

此 Surface Hub 更新包括品質改良與安全性問題修正。 本更新未引進任何新的作業系統功能。 Surface Hub 的重要更新，尚未於 [[Windows 10 更新記錄]](https://support.microsoft.com/help/4018124/windows-10-update-history) 中概述，包括：

* 已修正工作階段之間音量未正確重設的問題

*[KB3147458](https://support.microsoft.com/help/3147458)
</details>

## <a name="related-topics"></a>相關主題

* [Windows 10 版本資訊](https://go.microsoft.com/fwlink/p/?LinkId=724328)
* [Windows 10 11 月更新：常見問題](https://windows.microsoft.com/windows-10/windows-update-faq)
* [Microsoft Surface 更新記錄](https://go.microsoft.com/fwlink/p/?LinkId=724327)
* [Microsoft Lumia 更新記錄](https://go.microsoft.com/fwlink/p/?LinkId=785968)
* [取得 Windows 10](https://go.microsoft.com/fwlink/p/?LinkId=616447)
