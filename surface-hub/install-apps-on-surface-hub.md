---
title: 在 Microsoft Surface Hub 上安裝應用程式
description: 系統管理員可以從 Microsoft 網上商店或商務用 Microsoft 網上商店安裝應用程式。
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: dpandre
manager: laurawi
keywords: install apps, Microsoft Store, Microsoft Store for Business, 安裝應用程式, Microsoft 網上商店, 商務用 Microsoft 網上商店
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/16/2021
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: a8c11406c7786e379999ff32f482815d6b180b24
ms.sourcegitcommit: 62b85dfb85abbe0d880b04e1bcee5bacc9fc045f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/24/2021
ms.locfileid: "11676657"
---
# <a name="install-apps-on-your-microsoft-surface-hub"></a>在 Microsoft Surface Hub 上安裝應用程式

您可以在 Surface Hub 上安裝其他應用程式，以滿足您團隊或組織的需求。 有不同的方法可安裝應用程式，取決於您是否在開發及測試應用程式，或是要部署已發佈的應用程式。 本主題會針對不同案例說明安裝應用程式的方法。

## <a name="supported-app-guidelines"></a>支援的 App 指導方針

- Surface Hub 僅能執行[通用 Windows 平台 (UWP) 應用程式](/windows/uwp/get-started/universal-application-platform-guide)。 使用[MSIX 封裝](/windows/msix/packaging-tool/tool-overview)工具建立的應用程式不會在 Surface Hub。
- 應用程式必須以[通用裝置系列](/windows/uwp/get-started/universal-application-platform-guide)或 Windows 小組裝置系列為目標。
- Surface Hub[僅支援](/microsoft-store/distribute-offline-apps)來自 商務用 Microsoft Store 的[離線授權商務用 Microsoft Store。](https://businessstore.microsoft.com/store/private-store)
- 根據預設，應用程式必須經過市集簽署才能安裝。 在測試和開發期間，您也可以選擇將裝置切換到開發人員模式來執行開發人員簽署的 UWP app。
- 將應用程式提交給應用程式Microsoft Store，開發人員必須設定裝置家庭可用性和組織授權選項，以確保應用程式可在 Surface Hub 上執行。
- 您需要系統管理員認證，才能在 Surface Hub 上安裝應用程式。 由於裝置是針對在共用空間 (例如會議室) 中使用所設計，因此人員無法存取 Microsoft 網上商店來下載和安裝應用程式。

## <a name="deploy-released-apps"></a>部署已發佈的應用程式

有幾個選項可用於安裝已發佈到 Microsoft 網上商店的應用程式，取決於您要在少數裝置上評估它們，或是在組織中廣泛部署。

安裝已發佈的應用程式：

- 使用 Microsoft 網上商店應用程式下載應用程式，或
- 從商務用 Microsoft 網上商店下載應用程式套件，然後使用佈建套件或支援的 MDM 提供者發佈。

### <a name="microsoft-store-app"></a>Microsoft 網上商店應用程式

若要評估在 Microsoft 網上商店上發佈的應用程式，請在 Surface Hub 上使用 Microsoft 網上商店應用程式來瀏覽並下載應用程式。

> [!NOTE]
> 不建議使用 Microsoft 網上商店應用程式做為在組織中大規模部署應用程式的方法：
>
> - 若要下載應用程式，您必須使用 Microsoft 帳戶或組織帳戶登入 Microsoft 網上商店應用程式。 不過，您一次只能將帳戶連線到最多 10 部裝置。 如果您擁有超過 10 部 Surface Hub，您將需要建立多個帳戶，或在應用程式安裝期間從您的帳戶中移除裝置。
> - 若要安裝應用程式，您必須在所擁有的每部 Surface Hub 上手動登入 Microsoft 網上商店應用程式。

#### <a name="to-browse-the-microsoft-store-on-surface-hub"></a>在 Surface Hub 上瀏覽 Microsoft 網上商店

1. 從您的 Surface Hub 啟動 **\[設定\]**。
2. 出現提示時，請輸入裝置系統管理員認證。
3. 流覽至**Surface Hub**  >  **應用程式&功能**。
4. 選取 **開啟市** /市，然後搜尋您正在尋找的應用程式。

### <a name="download-app-packages-from-microsoft-store-for-business"></a>從商務用 Microsoft 網上商店下載應用程式套件

若要下載在 Surface Hub 上安裝應用程式所需的應用程式套件，請造訪[商務用 Microsoft 網上商店](https://www.microsoft.com/business-store)。 商務用 Store 是您可以為組織中的 Windows10 裝置 (包括 Surface Hub) 尋找、取得和管理應用程式的地方。

> [!NOTE]
> 目前，Surface Hub 僅支援透過商務用 Store 提供的離線授權應用程式。 應用程式開發人員在提交應用程式時會設定離線授權可用性。

尋找並取得您要的應用程式，然後下載：

- 離線授權應用程式套件 (.appx 或 .appxbundle)
- 「未編碼的」** 授權檔案 (如果您要使用佈建套件安裝應用程式)
- 「已編碼的」** 授權檔案 (如果您要使用 MDM 發佈應用程式)
- 任何必要的相依性檔案

如需詳細資訊，請參閱[下載離線授權應用程式](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)。

### <a name="install-offline-licensed-apps-via-provisioning-package"></a>透過部署套件安裝離線授權的應用程式

您可以使用佈建套件，在少數 Surface Hub 上手動安裝從商務用 Store 下載的離線授權應用程式。 使用 Windows 映像處理與設定設計工具 (ICD) 建立佈建套件，其中包含應用程式套件與您從商務用 Store 下載的「未編碼」** 授權檔案。 如需詳細資訊，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。

### <a name="supported-mdm-provider"></a>支援的 MDM 提供者

若要將應用程式部署到組織中大量的 Surface Hub，請使用支援的 MDM 提供者。 下表顯示哪些 MDM 提供者支援部署離線授權應用程式套件。

| MDM 提供者                | 支援離線授權應用程式套件 |
|-----------------------------|----------------------------------------|
| 從版本 1602 (開始，具有 Configuration Manager 的內部部署 MDM)  | 是 |
|
| 協力廠商 MDM 提供者    | 檢查以確認您的 MDM 提供者支援部署離線授權應用程式套件。 |

> [!NOTE]
> 若要使用應用程式遠端部署離線Microsoft Intune，請參閱從 商務用 Microsoft Store 管理[VPP 應用程式](/mem/intune/apps/windows-store-for-business)。 Surface Hub應用程式部署僅支援指派給裝置群組並使用裝置授權類型的離線應用程式。

## <a name="develop-and-test-apps"></a>開發和測試應用程式

本節提供應用程式開發人員在應用程式上測試應用程式Surface Hub。

### <a name="developer-mode"></a>開發人員模式

根據預設，Surface Hub 僅能執行已發佈到 Microsoft 網上商店並經由市集簽署的 UWP應用程式。 提交到 Microsoft 網上商店的應用程式會在[應用程式認證程序](/windows/uwp/publish/the-app-certification-process)中進行安全性及合規性測試，因此這有助於保護您的 Surface Hub 防範惡意應用程式。

透過啟用開發人員模式，您也可以安裝開發人員簽署的 UWP應用程式。

> [!IMPORTANT]
> 啟用開發人員模式之後，您必須重設 Surface Hub 才能將它停用。 重設裝置會移除所有本機使用者檔案和設定，然後重新安裝 Windows。

#### <a name="to-turn-on-developer-mode"></a>開啟開發人員模式

1. 從您的 Surface Hub 啟動 **\[設定\]**。
2. 出現提示時，請輸入裝置系統管理員認證。
3. 瀏覽至 **\[更新與安全性\]** > **\[開發人員專用\]**。
4. 選取 **\[開發人員模式\]** 並接受警告提示。

### <a name="visual-studio"></a>Visual Studio

在開發期間，在 Surface Hub 上測試您應用程式的最簡單方式是使用 Visual Studio。 Visual Studio 的遠端偵錯功能可協助您在廣泛部署應用程式之前發現問題。 如需詳細資訊，請參閱[使用 Visual Studio 測試 Surface Hub應用程式](/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio)。

#### <a name="create-provisioning-package"></a>建立部署套件

使用 Visual Studio 為您的 UWP應用程式建立應用程式套件，並使用測試憑證簽署。 然後使用 Windows 映像處理與設定設計工具 (ICD) 建立包含應用程式套件的佈建套件。 如需詳細資訊，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。

## <a name="submit-apps-to-the-microsoft-store"></a>將應用程式提交至 Microsoft 網上商店

一旦應用程式準備好發佈，開發人員必須提交應用程式並發佈至 Microsoft 網上商店。 詳細資訊，請參閱發佈[Windows應用程式與遊戲](/windows/uwp/publish)。

在應用程式提交過程中，開發人員必須設定 **\[裝置系列可用性\]** 與 **\[組織授權\]** 選項，以確保應用程式可在 Surface Hub 上執行。

### <a name="to-set-device-family-availability"></a>設定裝置系列可用性

1. 在 [Windows 開發人員中心](https://developer.microsoft.com/windows)上，瀏覽至您的應用程式提交頁面。
2. 選取 **\[套件\]**。
3. 在 **\[裝置系列可用性\]** 底下，選取下列選項：

    - **Windows 10 團隊版**
    - **讓 Microsoft 決定是否使應用程式可提供給任何未來的裝置系列**
  
   ![顯示 \[裝置系列可用性\] 頁面的影像 - Microsoft 網上商店應用程式提交程序的一部分](images/device-family.png)  

   如需詳細資訊，請參閱[裝置系列可用性](/windows/uwp/publish/upload-app-packages#device-family-availability)。

### <a name="to-set-organizational-licensing"></a>設定組織授權

1. 在 [Windows 開發人員中心](https://developer.microsoft.com/windows)上，瀏覽至您的應用程式提交頁面。

2. 選取 **\[定價和可用性\]**。

3. 在 \[組織授權\] 底下，選取 **\[允許組織中斷連線 (離線) 授權\]**。

   ![顯示 \[組織授權\] 頁面的影像 - Microsoft 網上商店應用程式提交程序的一部分。](images/sh-org-licensing.png)

   > [!NOTE]
   > 預設已選取 **\[利用「市集」管理 (線上) 大量授權提供組織使用我的應用程式\]**。

   > [!NOTE]
   > 開發人員也可以直接將企業營運應用程式發佈到企業，而不需要在市集中廣泛提供。 如需詳細資訊，請參閱[發佈 LOB 應用程式到企業](/windows/uwp/publish/distribute-lob-apps-to-enterprises)。

   如需詳細資訊，請參閱[組織授權選項](/windows/uwp/publish/organizational-licensing)。

## <a name="summary"></a>摘要

根據您開發應用程式、在少數裝置上評估應用程式，或將應用程式廣泛部署到您的組織Surface Hub在應用程式上安裝應用程式的方法有一些不同。 下表摘要說明所支援的方法：

| 安裝方法             | 開發應用程式 | 在少數裝置上 <br> 評估應用程式 | 將應用程式廣泛部署 <br> 到組織中 |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| Visual Studio              | X |   |   |
| 佈建套件       | X | X |   |
| Microsoft 網上商店應用程式          |   | X |   |
| 支援的 MDM 提供者     |   |   | X |
