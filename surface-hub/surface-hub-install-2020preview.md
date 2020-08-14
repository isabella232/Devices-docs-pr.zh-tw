---
title: 安裝 Windows 10 團隊版 2020 更新預覽組建
description: 新的 Surface Hub 作業系統、Windows 10 團隊2020更新現已推出。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/13/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 51d6b9169b0074eb474ddc89b6fe9b43a921bb07
ms.sourcegitcommit: feb81137d009d9b7c743aabd7d02615e89842200
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/14/2020
ms.locfileid: "10929761"
---
# 安裝 Windows 10 團隊版 2020 更新預覽組建 

「Surface Hub」作業系統、 **Windows 10 團隊2020更新**的最新更新現已提供給 windows 測試人員 [計畫](https://insider.windows.com)中的 surface hub 50-寸和 surface hub 2 55 寸裝置的額外成本。 Windows 10 Team 2020 更新最終版本中將支援 Surface Hub 84-寸模型。

Windows 10 團隊2020更新帶來了主要的裝置部署和管理功能以及最新的 Windows 10 功能。 若要深入瞭解新功能，請參閱下列博客文章：已 [發行適用于公眾預覽版的新 Surface HUB 作業系統更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823) 如有已知問題，請參閱下方的「已知問題」一節。
 
## 必要條件

- 使用 Windows 測試人員 [計畫](https://insider.windows.com/)進行註冊。
- 從「Windows 測試人員計畫快速頻道」下載 Windows 10 Team 2020 更新預覽組建。
- 安裝預覽組建之後，請下載所需的固件更新。 注意：即使您決定離開 Windows 測試人員計畫，也無法卸載固件更新。

## 準備 Surface Hub

開始之前，請檢查 Surface Hub 是否已從 Windows Update 取得最新的更新，並確認您已儲存與您的裝置相關聯的 BitLocker 金鑰。

**若要手動檢查更新：**

1. 在 Surface Hub 上，開啟 [ **設定** ]，然後在出現提示時輸入您的系統管理員認證。
2. 流覽至 [**更新 Windows & 安全性**]  >  **更新**，然後選取 [**檢查更新**]。

如需詳細資訊，請參閱 [管理 Surface Hub 上的 Windows 更新](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)。

**若要手動儲存您的 BitLocker 金鑰：**

1. 在 Surface Hub 中插入 USB 磁片磁碟機。
2. 在 Surface Hub 上，開啟 [ **設定** ]，然後在出現提示時輸入您的系統管理員認證。
3. 流覽至 [**更新 & 安全性**復原]  >  ** **。
4. 在 [ **BitLocker**] 底下，選取 [ **儲存**]。 BitLocker 金鑰會儲存到 USB 磁片磁碟機上的文字檔中。

如需詳細資訊，請參閱 [儲存 BitLocker 金鑰](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。
 
## 安裝 Windows 10 Team 2020 更新預覽組建

1. 在 Surface Hub 上，開啟 [ **設定** ]，然後在出現提示時輸入您的系統管理員認證。
2. 流覽至 **隱私權 > 診斷 & 意見** 反應，並將診斷資料設定為 [已 **滿**]。 某些地區或組織可能需要透過 MDM policy 或 PPKG 檔案來套用此設定：
   - **針對 MDM：** 設定下列原則：。使用整數值3的 **/Vendor/MSFT/Policy/System/AllowTelemetry** ：
    
        ![將 AllowTelemetry 設定為3](images/hub-2020-allow-telemetry.png)

    - **針對 PPKG：** 下載 [PPKG](https://aka.ms/HubTltmtry)檔案。

3. 流覽至 [**更新 & 安全性**  >  **Windows**測試人員計畫]，然後選取 [**開始**使用] 進行註冊。
4. 請按照提示使用您的公司帳戶（ (建議的) 或您的個人 Microsoft 帳戶）來註冊為 Windows 測試人員。 如需使用您的公司帳戶登記之好處的詳細資料，請參閱 [註冊商務用 Windows](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)測試人員計畫。
5. 在 [ **挑選您**的測試人員設定] 底下，選取 [ **快速**]。
6. 允許 Surface Hub 在未來3到4天自動安裝預覽組建及所需的固件更新。 裝置將會在每日 [維護時段](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)自動下載並安裝更新。 例如：

- 在第一個維護視窗期間，Surface Hub 開始從 Windows Update 下載預覽組建。
- 在第二個維護視窗期間，裝置會重新開機以完成更新。
- 在第三個維護視窗期間，裝置會下載並安裝所需的固件更新。

> [!IMPORTANT]
> Microsoft 建議您保留3-4 天的 Surface Hub，以允許裝置完成預覽版及必要的固件更新。 如果您在此程式中使用裝置，您可能會遇到圖形、音訊和使用者介面問題。

### 如果您選擇手動安裝預覽組建及必要的固件更新：

1. 在您向 Windows 測試人員計畫註冊之後，請移至 [**設定**  >  **更新] & 安全性**  >  **Windows 更新**，然後選取 [**檢查更新**] 以安裝預覽組建。
2. 一旦預覽組建安裝 (可能需要長達14小時的) ，請選取 [ **立即重新開機** ] 以完成安裝。
3. 裝置重新開機之後，請移至 [**設定**  >  **更新] & 安全性**  >  **Windows 更新**，然後選取 [**檢查更新以安裝必要的固件更新**]。
4. 固件安裝之後，請選取 [ **立即重新開機**]。

> [!WARNING]
> 如果您安裝 [預覽組建] 但不安裝必要的固件更新，您可能會看到圖形、音訊和使用者介面問題。

> [!NOTE]
> 如果您選擇離開 Windows 測試人員計畫，並將 Surface Hub 還原為舊版的作業系統，您必須先 [重設裝置](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)。 接著，您將需要執行 [第一個 run 程式](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) 來重新設定您的裝置。
 

## 深入了解

- [已知問題： Windows 10 Team 2020 更新](surface-hub-2020-team-update-known-issues.md)
- [新的 Surface Hub 作業系統更新已發行以進行公開預覽。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [開始使用商務用 Windows 測試人員計畫](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)