---
title: 安裝 Windows 10 Team 2020 更新預覽組建
description: 新的 Surface Hub 作業系統、Windows 10 團隊2020更新現已推出。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894109"
---
# 安裝 Windows 10 Team 2020 更新預覽組建 

「Surface Hub」作業系統、 **Windows 10 團隊2020更新**的最新更新現已提供給 windows 測試人員[計畫](https://insider.windows.com)中的 surface hub 50-寸和 surface hub 2 55 寸裝置的額外成本。 Windows 10 Team 2020 更新最終版本中將支援 Surface Hub 84-寸模型。

Windows 10 團隊2020更新帶來了主要的裝置部署和管理功能以及最新的 Windows 10 功能。 若要深入瞭解新功能，請參閱下列博客文章：已[發行適用于公眾預覽版的新 Surface HUB 作業系統更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) 如有已知問題，請參閱下方的「已知問題」一節。
 
## 必要條件

- 使用 Windows 測試人員[計畫](https://insider.windows.com/)進行註冊。
- 從「Windows 測試人員計畫快速頻道」下載 Windows 10 Team 2020 更新預覽組建。
- 安裝預覽組建之後，請下載所需的固件更新。 注意：即使您決定離開 Windows 測試人員計畫，也無法卸載固件更新。

## 準備 Surface Hub

開始之前，請檢查 Surface Hub 是否已從 Windows Update 取得最新的更新，並確認您已儲存與您的裝置相關聯的 BitLocker 金鑰。

**若要手動檢查更新：**

1. 在 Surface Hub 上，開啟 [**設定**]，然後在出現提示時輸入您的系統管理員認證。
2. 流覽至 [**更新 Windows & 安全性**]  >  **更新**，然後選取 [**檢查更新**]。

如需詳細資訊，請參閱[管理 Surface Hub 上的 Windows 更新](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)。

**若要手動儲存您的 BitLocker 金鑰：**

1. 在 Surface Hub 中插入 USB 磁片磁碟機。
2. 在 Surface Hub 上，開啟 [**設定**]，然後在出現提示時輸入您的系統管理員認證。
3. 流覽至 [**更新 & 安全性**復原]  >  ** **。
4. 在 [ **BitLocker**] 底下，選取 [**儲存**]。 BitLocker 金鑰會儲存到 USB 磁片磁碟機上的文字檔中。

如需詳細資訊，請參閱[儲存 BitLocker 金鑰](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。
 
## 安裝 Windows 10 Team 2020 更新預覽組建

1. 在 Surface Hub 上，開啟 [**設定**]，然後在出現提示時輸入您的系統管理員認證。
2. 流覽至 [**更新 & 安全性**  >  **Windows**測試人員計畫]，然後選取 [**開始**使用]。
3. 請依照提示使用您的公司帳戶（建議）或您的個人 Microsoft 帳戶，將其註冊為 Windows 測試人員。 如需使用您的公司帳戶登記之好處的詳細資料，請參閱[註冊商務用 Windows](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)測試人員計畫。
4. 在 [**挑選您**的測試人員設定] 底下，選取 [**快速**]。
5. 允許 Surface Hub 在未來3到4天自動安裝預覽組建及所需的固件更新。 裝置將會在每日[維護時段](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)自動下載並安裝更新。 例如：

- 在第一個維護視窗期間，Surface Hub 開始從 Windows Update 下載預覽組建。
- 在第二個維護視窗期間，裝置會重新開機以完成更新。
- 在第三個維護視窗期間，裝置會下載並安裝所需的固件更新。

> [!IMPORTANT]
> Microsoft 建議您保留3-4 天的 Surface Hub，以允許裝置完成預覽版及必要的固件更新。 如果您在此程式中使用裝置，您可能會遇到圖形、音訊和使用者介面問題。

### 如果您選擇手動安裝預覽組建及必要的固件更新：

1. 在您向 Windows 測試人員計畫註冊之後，請移至 [**設定**  >  **更新] & 安全性**  >  **Windows 更新**，然後選取 [**檢查更新**] 以安裝預覽組建。
2. 預覽組建安裝之後（可能需要長達14小時），請選取 [**立即重新開機**] 以完成安裝。
3. 裝置重新開機之後，請移至 [**設定**  >  **更新] & 安全性**  >  **Windows 更新**，然後選取 [**檢查更新以安裝必要的固件更新**]。
4. 固件安裝之後，請選取 [**立即重新開機**]。

> [!WARNING]
> 如果您安裝 [預覽組建] 但不安裝必要的固件更新，您可能會看到圖形、音訊和使用者介面問題。

> [!NOTE]
> 如果您選擇離開 Windows 測試人員計畫，並將 Surface Hub 還原為舊版的作業系統，您必須先[重設裝置](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)。 接著，您將需要執行[第一個 run 程式](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub)來重新設定您的裝置。
 
## 已知問題： Windows 10 Team 2020 更新預覽組建

### 圖形、音訊和使用者介面問題 

如果您安裝 [預覽組建] 時，您可能會遇到各種圖形和使用者介面問題，但不會在此後立即安裝所需的固件更新。 Microsoft 方案可在 Windows 10 Team 2020 更新的發行組建中修正這些問題。

### Surface Hub 84-寸：圖形與使用者介面問題

如果您在第一代 Surface 中樞84寸裝置上安裝預覽版，您可能會遇到各種圖形與使用者介面問題。 Windows 10 Team 2020 更新最終版本中將會支援 Surface Hub 84-寸。

### 套用條件式存取原則時，登入會受到影響

- 嘗試登入應用程式（例如 Microsoft 白板）時登入失敗。 使用者必須先從 [開始] 功能表中的 [[我的會議] 和](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)[檔案] 登入。

- 如果您的使用者帳戶登錄至不同的 Azure AD 租使用者，而不是 Surface Hub 對 Azure AD join 所使用的租使用者，請登入失敗。

Microsoft 方案可在 Windows 10 Team 2020 更新的發行組建中修正這些問題。

### Windows Update 在沒有可用的新驅動程式時提示安裝

當您在**Settings**  >  安裝 windows 10 Team 2020 更新及所需的固件更新之後，移至 [設定**更新] & 安全性**  >  **Windows 更新**，您可能會看到下列錯誤： 

- 「您電腦上目前的驅動程式可能比我們嘗試安裝的驅動程式好。 我們會持續嘗試安裝。」 

您可以放心地忽略此錯誤。 Microsoft 正在積極調查這個問題。

### 無法使用預配套件安裝 Surface Hub 原則

無法安裝使用 Surface Hub 配置服務提供者（CSP）中原則的預配套件。 現在，請使用 Microsoft Intune 或其他行動裝置管理（MDM）提供者來套用 Surface Hub 原則。 Microsoft 方案可在 Windows 10 Team 2020 更新的發行組建中修正這個問題。

### 第一次執行時，系統會提示您提前移除 USB 磁片磁碟機

在第一次執行期間使用預配套件來設定 Surface Hub 時，系統會提示您移除 USB 磁片磁碟機，讓裝置能夠讀取 Surface Hub 設定檔。 如果您是使用 [設定檔案] 來設定您的裝置帳戶，請忽略此訊息。 Microsoft 正在積極調查這個問題。
 
### 無法在第一次執行期間設定 proxy 設定

如果您使用 proxy 連線至網際網路，在第一次執行程式期間，您的網際網路連線可能會受到限制。 Microsoft 方案可在 Windows 10 Team 2020 更新的發行組建中修正這個問題。
 
### 從 Microsoft Store 下載應用程式時出現錯誤

若要從 Microsoft 網上商店下載 app，您會看到 [登入] 的提示。 已知問題會導致在登入時出現錯誤，但這不會影響您下載 app 的能力。 Microsoft 正在積極調查這個問題。

### Surface Hub 2 間歇中斷 Wi-fi 連線

嘗試拔出裝置並將其插回，或使用乙太網線連線至網際網路。 Microsoft 正在積極調查這個問題。

### Surface Hub 秒間歇無法從睡眠狀態繼續

Surface Hub 秒可能間歇無法完全從睡眠中繼續執行，並在顯示 Microsoft 標誌的畫面上顯示為停止回應。 嘗試拔出您的裝置，然後再插回裝置。 

若要避免此問題：

1. 在 Surface Hub 上，開啟 [**設定**]，然後在出現提示時輸入您的系統管理員認證。
2. 流覽至 [ **Surface Hub**]  >  **會話 & [電源**]。 
3. 在 **[當裝置進入睡眠狀態時，請使用此電源設定**] 底下，選取 [**已連接待機]。**
4. 在 [**沒有任何人時，請將裝置移至睡眠狀態**] 底下，選取 [**永不]。**

Microsoft 方案在 Windows 10 Team 2020 更新的最終發行前，在固件更新中修正此問題。

### [連線] app 不在視野中時的投影問題

- 當您使用光纜來投影 Surface Hub 時，如果您流覽到 [連接] app，touchback 就會停止運作。
- 當您使用 Miracast 來投影至 Surface Hub 時，當您離開連接應用程式後，無線連線就會立即中斷。

Microsoft 正在積極調查這些問題。

### 商務用 Skype 沒有使用 proxy 來進行媒體流量

針對使用 proxy 的一些裝置，商務用 Skype 可以登入，但不會使用 proxy 伺服器來傳送媒體流量。 Microsoft 正在積極調查這個問題。

我們邀請您與 Microsoft 支援人員分享您的見解與建議。

## 深入了解

- [新的 Surface Hub 作業系統更新已發行以進行公開預覽。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [開始使用商務用 Windows 測試人員計畫](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)