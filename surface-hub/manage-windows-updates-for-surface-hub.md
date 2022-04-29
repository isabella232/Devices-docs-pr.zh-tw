---
title: 在 Surface Hub 上管理 Windows 更新
description: 說明在 Microsoft Surface Hub 或 Surface Hub 2S 上管理更新的最佳做法。
ms.assetid: A737BD50-2D36-4DE5-A604-55053D549045
ms.reviewer: ''
manager: laurawi
keywords: 管理Windows更新、Surface Hub、Windows Server Update Services
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: ecff961e1aaa14ed2af5e6d91ffc2254e4dcfa46
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497776"
---
# <a name="manage-windows-updates-on-surface-hub"></a>在 Surface Hub 上管理 Windows 更新

新版本的Surface Hub作業系統會透過Windows Update發佈，就像發行Windows 10或Windows 11一樣。 此頁面說明管理Surface Hub裝置更新的最佳做法。 

## <a name="windows-update-for-business"></a>商務用 Windows Update

Windows Update商務用是一組功能，其設計目的是讓企業能夠進一步控制Windows Update安裝版本的方式和時間，同時降低裝置管理成本。 使用此方法，Surface Hub 就會直接連線到 Microsoft 的 Windows Update 服務。

- 直接從 Microsoft 的 Windows Update 服務接收更新，不需要額外的基礎結構。 
- 延遲更新以提供額外時間進行測試和評估。 
- 部署更新以選取裝置群組。 
- 定義維護期間以用於安裝更新。 

> [!TIP]
> 使用點對點內容共用來降低更新期間的頻寬問題。 如需詳細資訊，請參閱[優化Windows更新傳遞](/windows/deployment/do/waas-optimize-windows-10-updates)。

> [!NOTE]
> Surface Hub 目前不支援復原更新。


## <a name="surface-hub-servicing-model"></a>Surface Hub 維護模型

Surface Hub使用Windows服務模型，稱為[Windows 即服務 (WaaS) ](/windows/deployment/update/waas-overview)。 依慣例，只有每隔幾年發行一次的新版 Windows 才會加入新功能。 每個新版本都需要較長且昂貴的程序以在組織中部署。 因此，一般使用者和組織不會經常享受到新創新的好處。 「Windows 即服務」的目標是持續提供新功能，同時維持高品質。

Microsoft 會持續廣泛發佈兩種類型的 Surface Hub 版本：
- **功能更新**：會安裝最新近的特色、體驗及功能的更新。 Microsoft 預期每年發佈兩個新的功能更新。
- **品質更新**：著重於安全性問題修正、驅動程式及其他維護更新之安裝的更新。 Microsoft 預期每個月發佈一次累積品質更新。

為了改善發行品質並簡化部署，Microsoft 針對Windows 10或Windows 11發行的所有新版本，包括Surface Hub，都會累積。 這表示新的功能更新和品質更新會包含所有先前發行版本的「承載」(以最佳化方式提供，以降低儲存體及網路需求)，只要裝置安裝這個發行版本，就能完整更新到最新狀態。 另外，與舊版 Windows 不同的是，您無法安裝 Windows10 品質更新的內容子集。 例如，如果某個品質更新包含三個安全性弱點與一個可靠性問題的修正，部署更新就會同時安裝這四個修正。

Surface Hub 作業系統會在[半年度管道](/windows/deployment/update/waas-overview#naming-changes)上接收更新。 如同其他版本的Windows 10或Windows 11，維護存留期是有限的。 您必須在執行這些分支的電腦上安裝新功能更新，才能繼續收到品質更新。

如需「Windows 即服務」的詳細資訊，請參閱 [Windows 即服務概觀](/windows/deployment/update/waas-overview)。


## <a name="use-windows-update-for-business"></a>使用商務用 Windows Update

和所有 Windows10 裝置一樣，Surface Hub 也包括**商務用 Windows Update (WUfB)**，可讓您控制裝置的更新方式。 商務用 Windows Update 有助於減少裝置管理的成本、提供所有更新部署的控制、更快速地存取安全性更新，並持續提供來自 Microsoft 的最新創新功能。 如需詳細資訊，請參閱[使用商務用 Windows Update 來管理更新](/windows/deployment/update/waas-manage-updates-wufb)。

> [!IMPORTANT]
> Microsoft 通常會在 2 星期二發行 (每月發行一個強制Windows安全性更新，通常稱為「B」版本) 。 連同頻外安全性更新，這些是使用 WUfB 提供給裝置的唯一更新。 不過，Surface Hub改善通常會在每月第 3 個星期二透過選擇性的非安全性更新來傳遞， (「C」 版本) 。 因此，使用商務用 Windows Update與 Surface Hub 的客戶必須等到下個月的「B」版本才會看到這些裝置上的最新改善。

**設定商務用 Windows Update：**
1. [將 Surface Hub 群組到部署更新步調](#group-surface-hub-into-deployment-rings)
2. [設定 Surface Hub 接收更新的時機](#configure-when-surface-hub-receives-updates)。

> [!NOTE]
> 您可以使用Microsoft Intune、Microsoft Endpoint Configuration Manager或支援的協力廠商 MDM 提供者來設定 WUfB。 [逐步解說：使用 Microsoft Intune 來設定商務用 Windows Update。](/windows/deployment/update/waas-wufb-intune)


### <a name="group-surface-hub-into-deployment-rings"></a>將 Surface Hub 群組到部署更新步調

使用部署更新步調來控制更新將推出到您 Surface Hub 的時間，讓您有時間驗證它們。 例如，您可以先更新一小群的裝置以確認品質，然後再更廣泛地向您的組織推出。 視組織中管理Surface Hub的人員而定，請考慮將Surface Hub納入您為其他Windows 10或Windows 11裝置建置的部署更新步調中。 如需部署更新步調的詳細資訊，請參閱[準備Windows用戶端更新的服務策略](/windows/deployment/update/waas-servicing-strategy-windows-10-updates)。

如需部署更新步調的範例，請參閱下表。

| 部署更新步調 | 更新步調大小 | 維護分支 | 功能更新延遲 | 品質更新延遲 (安全性修正、驅動程式及其他更新) | 驗證步驟 |
| --------- | --------- | --------- | --------- | --------- | --------- |
| 評估 (例如非重要或測試裝置) | 小型 | Windows Insider Preview | 無。  | 無。  | 手動測試及評估新功能。 如果有問題請暫停更新。 |
| 試驗 (例如所選團隊使用的裝置) | 中型 | 半年度管道  | 無。 | 無。  | 監視裝置使用情況和使用者意見反應。 如果有問題請暫停更新。 |
| 廣泛部署 (例如您組織中的大部分裝置) | 大型 | 半年度管道 |  發行之後 120 天。 | 發行之後 7-14 天。 | 監視裝置使用情況和使用者意見反應。 如果有問題請暫停更新。 |
| 任務關鍵性 (例如執行董事會中的裝置) | 小型 | 半年度管道 |  發行之後 180 天 (功能更新的最長延遲天數)。 | 發行之後 30 天 (品質更新的最長延遲天數)。 | 監視裝置使用情況和使用者意見反應。 |


### <a name="configure-when-surface-hub-receives-updates"></a>設定 Surface Hub 接收更新的時機

在您已經為 Surface Hub 決定部署更新步調之後，請針對每個更新步調設定更新延遲原則：
- 若要延遲功能更新，請為每個更新步調設定適當的 [Update/DeferFeatureUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#update-deferfeatureupdatesperiodindays) 原則。
- 若要延遲品質更新，請為每個更新步調設定適當的 [Update/DeferQualityUpdatesPeriodInDays](/windows/client-management/mdm/policy-csp-update#update-deferqualityupdatesperiodindays) 原則。

> [!NOTE]
> 如果您在更新推出期間遇到問題，您可以使用 [Update/PauseFeatureUpdates](/windows/client-management/mdm/policy-csp-update#update-pausefeatureupdates) 和 [Update/PauseQualityUpdates](/windows/client-management/mdm/policy-csp-update#update-pausequalityupdates) 暫停更新。

**如果您使用 proxy 伺服器或其他方法封鎖 URL**

將下列Windows將受信任的網站 URL 更新至「允許清單」：
- `http(s)://*.update.microsoft.com`
- `http://download.windowsupdate.com` 
- `http://windowsupdate.microsoft.com`

安裝好 Windows 10 小組年度更新版之後，您可以移除這些網址讓 Surface Hub 回到先前的狀態。

## <a name="maintenance-window"></a>維護期間

為確保裝置在上班時間一律可以使用，Surface Hub 會在指定的維護期間執行其管理功能。 在維護期間，Surface Hub會透過Windows Update自動安裝更新，並在視窗結束前 20 分鐘重新開機裝置。

Surface Hub 會依照這些指導方針套用更新：
- 在下一個維護期間安裝更新。 如果會議排程在維護期間開始，或者如果 Surface Hub 感應器偵測到裝置為使用中，則擱置的更新將延遲至下一個維護期間。
- 如果下一個維護期間超過規定的寬限期，裝置將會使用來自更新中繼資料的評估安裝時間，計算上班時間的下一個可用空檔。 如果已經排定會議，或 Surface Hub 感應器偵測到裝置為使用中，它將會繼續延後更新。
- 如果下一個維護期間**未**超過更新的寬限期，Surface Hub會繼續延後更新。
- 如果需要重新開機，Surface Hub 將會在下一個維護期間自動重新開機。

> [!NOTE]
> 在您第一次設定 Surface Hub 時，請保留時間以用於更新。 例如，可能有病毒定義的待處理項目可用，這應該要立即安裝。

為所有新的 Surface Hub 設定預設的維護期間：
-   **開始時間：** 上午 2：00
-   **持續時間：** 2 小時

**手動變更維護期間：**
1.  在 Surface Hub 上，開啟 **\[設定\]**。
2.  瀏覽至 **\[更新與安全性\]** > **\[Windows Update\]** > **\[進階選項\]**。
3.  在 **\[維護時間\]** 下方，選取 **\[變更\]**。

若要使用 MDM 變更維護期間，請在[SurfaceHub 設定服務提供者](/windows/client-management/mdm/surfacehub-csp)中設定**MaintenanceHoursSimple**節點。 如需更多詳細資料，請參閱[使用 MDM 提供者管理設定](manage-settings-with-mdm-for-surface-hub.md)。


## <a name="more-information"></a>其他資訊

- [部落格文章：當然，使用Intune維護、正式發行前小眾測試及管理Surface Hub (更新！) ](https://blogs.technet.microsoft.com/y0av/2018/05/31/7-3/)


## <a name="related-topics"></a>相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)

