---
title: 在 Surface Hub 上管理 Windows 更新
description: 您可以設定 [維護] 視窗、推遲更新，或使用 Windows Server Update Services (WSUS) ，以管理 Microsoft Surface Hub 或 Surface Hub 2 的 Windows 更新。
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: 管理 Windows 更新, Surface Hub, WindowsServer Update Services, WSUS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 72214ec9436e6ea106d9e42c957664631ee88a0a
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103787"
---
# 在 Surface Hub 上管理 Windows 更新

新版本的 Surface Hub 作業系統是透過 Windows Update 發行，和 Windows10 版本一樣。 您有幾個方式可以管理要在您的 Surface Hub 上安裝哪些更新，以及套用更新的時間。
- **商務用 Windows Update**：商務用 Windows Update 是 Windows10 中的一組新功能，是針對為企業提供額外控制能力所設計，可讓企業控制 Windows Update 安裝版本的方式與時機，同時降低裝置管理成本。 使用此方法，Surface Hub 就會直接連線到 Microsoft 的 Windows Update 服務。
- **WindowsServer Update Services (WSUS)**：這是一組服務，可以讓 IT 系統管理員取得 Windows Update 判斷適用於他們企業裝置的更新、對更新執行其他測試和評估，並可選取想要安裝的更新。 使用此方法，Surface Hub 將會從 WSUS 接收更新，而非從 Windows Update 接收更新。

您也可以設定 Surface Hub 從商務用 Windows Update 與 WSUS 接收更新。 請參閱[將商務用 Windows Update 與 WindowsServer Update Services 整合](https://technet.microsoft.com/itpro/windows/manage/waas-integrate-wufb#integrate-windows-update-for-business-with-windows-server-update-services)以了解詳細資料。

| 功能 | 商務用 Windows Update | Windows Server Update Services (WSUS) |
| ------------ | --------------------------- | ------------------------------------- |
| 直接從 Microsoft 的 Windows Update 服務接收更新，不需要額外的基礎結構。  | 是  | 否  |
| 延遲更新以提供額外時間進行測試和評估。 | 是  | 是  |
| 部署更新以選取裝置群組。 | 是 | 是 |
| 定義維護期間以用於安裝更新。 | 是  | 是  |

> [!TIP]
> 使用點對點內容共用來降低更新期間的頻寬問題。 請參閱[為 Windows10 更新最佳化更新傳遞](https://technet.microsoft.com/itpro/windows/manage/waas-optimize-windows-10-updates)以了解詳細資料。

> [!NOTE]
> Surface Hub 目前不支援復原更新。


## Surface Hub 維護模型

Surface Hub 使用 Windows 10 維護模型，稱為 [Windows 即服務 (WaaS)](https://docs.microsoft.com/windows/deployment/update/waas-overview)。 依慣例，只有每隔幾年發行一次的新版 Windows 才會加入新功能。 每個新版本都需要較長且昂貴的程序以在組織中部署。 因此，一般使用者和組織不會經常享受到新創新的好處。 「Windows 即服務」的目標是持續提供新功能，同時維持高品質。

Microsoft 會持續廣泛發佈兩種類型的 Surface Hub 版本：
- **功能更新**：會安裝最新近的特色、體驗及功能的更新。 Microsoft 預期每年發佈兩個新的功能更新。
- **品質更新**：著重於安全性問題修正、驅動程式及其他維護更新之安裝的更新。 Microsoft 預期每個月發佈一次累積品質更新。

為了改善發行品質和簡化部署，Microsoft 為 Windows10 發行的所有新發行版本 (包括 Surface Hub) 將為「累積式」。 這表示新的功能更新和品質更新會包含所有先前發行版本的「承載」(以最佳化方式提供，以降低儲存體及網路需求)，只要裝置安裝這個發行版本，就能完整更新到最新狀態。 另外，與舊版 Windows 不同的是，您無法安裝 Windows10 品質更新的內容子集。 例如，如果某個品質更新包含三個安全性弱點與一個可靠性問題的修正，部署更新就會同時安裝這四個修正。

Surface Hub 作業系統會在[半年度管道](https://docs.microsoft.com/windows/deployment/update/waas-overview#naming-changes)上接收更新。 與 Windows 10 的其他版本一樣，維護存留期是有限的。 您必須在執行這些分支的電腦上安裝新功能更新，才能繼續收到品質更新。

如需「Windows 即服務」的詳細資訊，請參閱 [Windows 即服務概觀](https://technet.microsoft.com/itpro/windows/manage/waas-overview)。


## 使用商務用 Windows Update
和所有 Windows10 裝置一樣，Surface Hub 也包括**商務用 Windows Update (WUfB)**，可讓您控制裝置的更新方式。 商務用 Windows Update 有助於減少裝置管理的成本、提供所有更新部署的控制、更快速地存取安全性更新，並持續提供來自 Microsoft 的最新創新功能。 如需詳細資訊，請參閱[使用商務用 Windows Update 來管理更新](https://technet.microsoft.com/itpro/windows/manage/waas-manage-updates-wufb)。

**設定商務用 Windows Update：**
1. [將 Surface Hub 群組到部署更新步調](#group-surface-hub-into-deployment-rings)
2. [設定 Surface Hub 接收更新的時機](#configure-when-surface-hub-receives-updates)。

> [!NOTE]
> 您可以使用 Microsoft Intune、Microsoft 端點建構管理員或支援的協力廠商 MDM 提供者來設定 WUfB。 [逐步解說：使用 Microsoft Intune 來設定商務用 Windows Update。](https://docs.microsoft.com/windows/deployment/update/waas-wufb-intune)


### 將 Surface Hub 群組到部署更新步調
使用部署更新步調來控制更新將推出到您 Surface Hub 的時間，讓您有時間驗證它們。 例如，您可以先更新一小群的裝置以確認品質，然後再更廣泛地向您的組織推出。 視您組織中管理 Surface Hub 的人員而定，可以考慮將 Surface Hub 合併到您已經為其他 Windows10 裝置建置的部署更新步調中。 如需部署更新步調的相關詳細資訊，請參閱[為 Windows10 更新建置部署更新步調](https://technet.microsoft.com/itpro/windows/manage/waas-deployment-rings-windows-10-updates)。

此表格提供部署更新步調的範例。

| 部署更新步調 | 更新步調大小 | 維護分支 | 功能更新延遲 | 品質更新延遲 (安全性修正、驅動程式及其他更新) | 驗證步驟 |
| --------- | --------- | --------- | --------- | --------- | --------- |
| 評估 (例如非重要或測試裝置) | 小型 | Windows 預覽 | 無。  | 無。  | 手動測試及評估新功能。 如果有問題請暫停更新。 |
| 試驗 (例如所選團隊使用的裝置) | 中型 | 半年度管道  | 無。 | 無。  | 監視裝置使用情況和使用者意見反應。 如果有問題請暫停更新。 |
| 廣泛部署 (例如您組織中的大部分裝置) | 大型 | 半年度管道 |  發行之後 120 天。 | 發行之後 7-14 天。 | 監視裝置使用情況和使用者意見反應。 如果有問題請暫停更新。 |
| 任務關鍵性 (例如執行董事會中的裝置) | 小型 | 半年度管道 |  發行之後 180 天 (功能更新的最長延遲天數)。 | 發行之後 30 天 (品質更新的最長延遲天數)。 | 監視裝置使用情況和使用者意見反應。 |





### 設定 Surface Hub 接收更新的時機
在您已經為 Surface Hub 決定部署更新步調之後，請針對每個更新步調設定更新延遲原則：
- 若要延遲功能更新，請為每個更新步調設定適當的 [Update/DeferFeatureUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) 原則。
- 若要延遲品質更新，請為每個更新步調設定適當的 [Update/DeferQualityUpdatesPeriodInDays](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) 原則。

> [!NOTE]
> 如果您在更新推出期間遇到問題，您可以使用 [Update/PauseFeatureUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) 和 [Update/PauseQualityUpdates](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates) 暫停更新。


## 使用 Windows Server Update Services

您可以將 Surface Hub 連線到您的 Windows Server Update Services (WSUS) 伺服器來管理更新。 更新將會透過您 WSUS 伺服器中設定的核准或自動部署規則來控制，所以將不會在您選擇部署新的升級之前部署它們。

**手動將 Surface Hub 連線到 WSUS 伺服器：**
1. 在 Surface Hub 上，開啟 **\[設定\]**。
2. 出現提示時，請輸入裝置系統管理員認證。
3. 瀏覽至 **\[更新與安全性\]** > **\[Windows Update\]** > **\[進階選項\]** > **\[設定 WindowsServer Update Services (WSUS) 伺服器\]**。
4. 按一下 **\[使用 WSUS 伺服器以下載更新\]**，然後輸入您 WSUS 伺服器的 URL。

若要使用 MDM 將 Surface Hub 連線到 WSUS 伺服器，請設定適當的 [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl) 原則。

**如果您使用 proxy 伺服器或其他方法封鎖 URL**

如果您使用 WSUS 以外的其他方式封鎖特定的 URL 並避免更新時，您需要將以下 Windows Update 信任的網站 URL 新增到「允許清單」：
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

安裝好 Windows 10 小組年度更新版之後，您可以移除這些網址讓 Surface Hub 回到先前的狀態。

## 維護期間

為確保裝置在上班時間一律可以使用，Surface Hub 會在指定的維護期間執行其管理功能。 在維護視窗期間，Surface Hub 會透過 Windows Update 或 WSUS 自動安裝更新，並在視窗結束之前的20分鐘重新開機裝置。

Surface Hub 會依照這些指導方針套用更新：
- 在下一個維護期間安裝更新。 如果會議排程在維護期間開始，或者如果 Surface Hub 感應器偵測到裝置為使用中，則擱置的更新將延遲至下一個維護期間。
- 如果下一個維護期間超過規定的寬限期，裝置將會使用來自更新中繼資料的評估安裝時間，計算上班時間的下一個可用空檔。 如果已經排定會議，或 Surface Hub 感應器偵測到裝置為使用中，它將會繼續延後更新。
- 如果下一個維護視窗 **未** 超出更新的寬限期，Surface Hub 將繼續推遲更新。
- 如果需要重新開機，Surface Hub 將會在下一個維護期間自動重新開機。

> [!NOTE]
> 在您第一次設定 Surface Hub 時，請保留時間以用於更新。 例如，可能有病毒定義的待處理項目可用，這應該要立即安裝。

為所有新的 Surface Hub 設定預設的維護期間：
-   **開始時間：** 上午2:00
-   **工期：** 2 小時

**手動變更維護期間：**
1.  在 Surface Hub 上，開啟 **\[設定\]**。
2.  瀏覽至 **\[更新與安全性\]** > **\[Windows Update\]** > **\[進階選項\]**。
3.  在 **\[維護時間\]** 下方，選取 **\[變更\]**。

若要使用 MDM 變更維護期間，請設定 [SurfaceHub 設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)中的 **\[MOMAgent\]** 節點。 如需更多詳細資料，請參閱[使用 MDM 提供者管理設定](manage-settings-with-mdm-for-surface-hub.md)。


## 詳細資訊

- [博客文章：使用 Intune 進行 Surface Hub (的服務、正式及管理更新（當然就是）！ ) ](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## 相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)

