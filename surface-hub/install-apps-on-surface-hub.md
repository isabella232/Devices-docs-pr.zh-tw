---
title: 在 Microsoft Surface Hub 上安裝應用程式
description: 系統管理員可以從 Microsoft 網上商店或商務用 Microsoft 網上商店安裝應用程式。
ms.assetid: 3885CB45-D496-4424-8533-C9E3D0EDFD94
ms.reviewer: ''
manager: laurawi
keywords: install apps, Microsoft Store, Microsoft Store for Business, 安裝應用程式, Microsoft 網上商店, 商務用 Microsoft 網上商店
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/23/2018
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: a6e791defed4970b9a1940580b5f80bbe4f006a4
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470471"
---
# <a name="install-apps-on-your-microsoft-surface-hub"></a>在 Microsoft Surface Hub 上安裝應用程式

您可以在 Surface Hub 上安裝其他應用程式，以滿足您團隊或組織的需求。 有不同的方法可安裝應用程式，取決於您是否在開發及測試應用程式，或是要部署已發佈的應用程式。 本主題會針對不同案例說明安裝應用程式的方法。

關於 Surface Hub 上的應用程式，必須先了解幾件事：
- Surface Hub 僅能執行[通用 Windows 平台 (UWP) 應用程式](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)。 使用 [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) 建立的應用程式將無法在 Surface Hub 上執行。
- 應用程式必須以[通用裝置系列](https://msdn.microsoft.com/library/windows/apps/dn894631)或 Windows 小組裝置系列為目標。
- Surface Hub [僅支援](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 來自 [商務用 Microsoft Store 的離線授權應用程式](https://businessstore.microsoft.com/store)。
- 根據預設，應用程式必須經過市集簽署才能安裝。 在測試和開發期間，您也可以選擇將裝置切換到開發人員模式來執行開發人員簽署的 UWP app。
- 將應用程式提交至 Microsoft Store 時，開發人員必須設定裝置家庭可用性和組織授權選項，以確保 App 可在 Surface Hub 上執行。
- 您需要系統管理員認證，才能在 Surface Hub 上安裝應用程式。 由於裝置是針對在共用空間 (例如會議室) 中使用所設計，因此人員無法存取 Microsoft 網上商店來下載和安裝應用程式。


## <a name="develop-and-test-apps"></a>開發和測試應用程式
當您開發自己的應用程式時，有幾個選項可在 Surface Hub 上測試應用程式。

### <a name="developer-mode"></a>開發人員模式
根據預設，Surface Hub 僅能執行已發佈到 Microsoft 網上商店並經由市集簽署的 UWP應用程式。 提交到 Microsoft 網上商店的應用程式會在[應用程式認證程序](https://msdn.microsoft.com/windows/uwp/publish/the-app-certification-process)中進行安全性及合規性測試，因此這有助於保護您的 Surface Hub 防範惡意應用程式。
 
透過啟用開發人員模式，您也可以安裝開發人員簽署的 UWP應用程式。
 
> [!IMPORTANT]
> 啟用開發人員模式之後，您必須重設 Surface Hub 才能將它停用。 重設裝置會移除所有本機使用者檔案和設定，然後重新安裝 Windows。

**開啟開發人員模式** 
1. 從您的 Surface Hub 啟動 **\[設定\]**。
2. 出現提示時，請輸入裝置系統管理員認證。
3. 瀏覽至 **\[更新與安全性\]** > **\[開發人員專用\]**。
4. 選取 **\[開發人員模式\]** 並接受警告提示。

### <a name="visual-studio"></a>Visual Studio
在開發期間，在 Surface Hub 上測試您應用程式的最簡單方式是使用 Visual Studio。 Visual Studio 的遠端偵錯功能可協助您在廣泛部署應用程式之前發現問題。 如需詳細資訊，請參閱[使用 Visual Studio 測試 Surface Hub應用程式](https://msdn.microsoft.com/windows/uwp/debug-test-perf/test-surface-hub-apps-using-visual-studio)。

### <a name="provisioning-package"></a>佈建套件
使用 Visual Studio 為您的 UWP應用程式[建立應用程式套件](https://msdn.microsoft.com/library/windows/apps/hh454036.aspx)，並使用測試憑證簽署。 然後使用 Windows 映像處理與設定設計工具 (ICD) 建立包含應用程式套件的佈建套件。 如需詳細資訊，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。


## <a name="submit-apps-to-the-microsoft-store"></a>將應用程式提交至 Microsoft 網上商店
一旦應用程式準備好發佈，開發人員必須提交應用程式並發佈至 Microsoft 網上商店。 如需詳細資訊，請參閱[發佈 Windows 應用程式](https://developer.microsoft.com/store/publish-apps)。

在應用程式提交過程中，開發人員必須設定 **\[裝置系列可用性\]** 與 **\[組織授權\]** 選項，以確保應用程式可在 Surface Hub 上執行。

**設定裝置系列可用性**

1. 在 [Windows 開發人員中心](https://developer.microsoft.com)上，瀏覽至您的應用程式提交頁面。

2. 選取 **\[套件\]**。
3. 在 **\[裝置系列可用性\]** 底下，選取下列選項：
    
    - **Windows 10 團隊版**
    - **讓 Microsoft 決定是否使應用程式可提供給任何未來的裝置系列**
  
   ![顯示 \[裝置系列可用性\] 頁面的影像 - Microsoft 網上商店應用程式提交程序的一部分](images/device-family.png)  
    
   如需詳細資訊，請參閱[裝置系列可用性](https://msdn.microsoft.com/windows/uwp/publish/upload-app-packages#device-family-availability)。

**設定組織授權**

1. 在 [Windows 開發人員中心](https://developer.microsoft.com)上，瀏覽至您的應用程式提交頁面。

2. 選取 **\[定價和可用性\]**。

3. 在 \[組織授權\] 底下，選取 **\[允許組織中斷連線 (離線) 授權\]**。

   ![顯示 \[組織授權\] 頁面的影像 - Microsoft 網上商店應用程式提交程序的一部分。](images/sh-org-licensing.png)

   > [!NOTE]
   > 預設已選取 **\[利用「市集」管理 (線上) 大量授權提供組織使用我的應用程式\]**。

   > [!NOTE]
   > 開發人員也可以直接將企業營運應用程式發佈到企業，而不需要在市集中廣泛提供。 如需詳細資訊，請參閱[發佈 LOB 應用程式到企業](https://msdn.microsoft.com/windows/uwp/publish/distribute-lob-apps-to-enterprises)。

   如需詳細資訊，請參閱[組織授權選項](https://msdn.microsoft.com/windows/uwp/publish/organizational-licensing)。


## <a name="deploy-released-apps"></a>部署已發佈的應用程式

有幾個選項可用於安裝已發佈到 Microsoft 網上商店的應用程式，取決於您要在少數裝置上評估它們，或是在組織中廣泛部署。

安裝已發佈的應用程式：
- 使用 Microsoft 網上商店應用程式下載應用程式，或
- 從商務用 Microsoft 網上商店下載應用程式套件，然後使用佈建套件或支援的 MDM 提供者發佈。

### <a name="microsoft-store-app"></a>Microsoft 網上商店應用程式
若要評估在 Microsoft 網上商店上發佈的應用程式，請在 Surface Hub 上使用 Microsoft 網上商店應用程式來瀏覽並下載應用程式。

> [!NOTE]
> 不建議使用 Microsoft 網上商店應用程式做為在組織中大規模部署應用程式的方法：
> - 若要下載應用程式，您必須使用 Microsoft 帳戶或組織帳戶登入 Microsoft 網上商店應用程式。 不過，您一次只能將帳戶連線到最多 10 部裝置。 如果您擁有超過 10 部 Surface Hub，您將需要建立多個帳戶，或在應用程式安裝期間從您的帳戶中移除裝置。
> - 若要安裝應用程式，您必須在所擁有的每部 Surface Hub 上手動登入 Microsoft 網上商店應用程式。

**在 Surface Hub 上瀏覽 Microsoft 網上商店** 
1. 從您的 Surface Hub 啟動 **\[設定\]**。
2. 出現提示時，請輸入裝置系統管理員認證。
3. 瀏覽至 **\[此裝置\]** > **\[應用程式與功能\]**。
4. 選取 **\[開啟市集\]**。

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

### <a name="provisioning-package"></a>佈建套件
您可以使用佈建套件，在少數 Surface Hub 上手動安裝從商務用 Store 下載的離線授權應用程式。 使用 Windows 映像處理與設定設計工具 (ICD) 建立佈建套件，其中包含應用程式套件與您從商務用 Store 下載的「未編碼」** 授權檔案。 如需詳細資訊，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。

### <a name="supported-mdm-provider"></a>支援的 MDM 提供者
若要將應用程式部署到組織中大量的 Surface Hub，請使用支援的 MDM 提供者。 下表顯示哪些 MDM 提供者支援部署離線授權應用程式套件。

| MDM 提供者                | 支援離線授權應用程式套件 |
|-----------------------------|----------------------------------------|
| 從版本 1602 (開始，具有 Configuration Manager 的內部部署 MDM)  | 是 |
|
| 協力廠商 MDM 提供者    | 檢查以確認您的 MDM 提供者支援部署離線授權應用程式套件。 |

**使用 Microsoft 端點群組原則管理員遠端部署應用程式**

> [!NOTE]
> 這些指示是以 Microsoft 端點群組原則管理員目前的分支為基礎。

1. 將 Surface Hub 註冊到 MDM 管理。 詳細資訊，請參閱使用[MDM 提供者管理 Surface Hub。](manage-settings-with-mdm-for-surface-hub.md)

2. 從商務用 Store 下載離線授權應用程式套件、「已編碼的」** 授權檔案，和任何必要的相依性檔案。 如需詳細資訊，請參閱[下載離線授權應用程式](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app)。 將下載的檔案放入網路共用上的相同資料夾。

3. 在 Configuration Manager 主控台的 **\[軟體程式庫\]** 工作區中，按一下 **\[概觀\]** > **\[應用程式管理\]** > **\[應用程式\]**。

4. 在 **\[首頁\]** 索引標籤上的 **\[建立\]** 群組中，按一下 **\[建立應用程式\]**。

5. 在 **\[建立應用程式精靈\]** 的 **\[一般\]** 頁面，選取 **\[從安裝檔案自動偵測此應用程式的相關資訊\]** 核取方塊。

6. 在 **\[類型\]** 下拉式清單中，選取 **\[Windows 應用程式套件 (\*.appx, \*.appxbundle)\]**。

7. 在 **\[位置\]** 欄位中，以下列格式針對您從商務用 Store 下載的離線授權應用程式套件指定 UNC 路徑：\\server\share\\filename。 您也可以按一下 **\[瀏覽\]** 來瀏覽到應用程式套件。

8. 在 **\[匯入資訊\]** 頁面上檢閱匯入的資訊，然後按一下 **\[下一步\]**。 如有需要，您可以按一下 **\[上一步\]** 返回並更正任何錯誤。

9. 在 **\[一般資訊\]** 頁面上，完成關於應用程式的其他詳細資料。 如果該應用程式是從應用程式套件中自動取得的，則可能已經填入一些資訊。

10. 按一下 **\[下一步\]**，檢閱 \[摘要\] 頁面上的應用程式資訊，然後完成 \[建立應用程式精靈\]。 

11. 建立應用程式的部署類型。 如需詳細資訊，請參閱[建立應用程式的部署類型](https://docs.microsoft.com/sccm/apps/deploy-use/create-applications#create-deployment-types-for-the-application)。

12. 將應用程式部署到您的 Surface Hub。 詳細資訊，請參閱使用 [Microsoft 端點群組原則管理員部署應用程式](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)。

13. 視需要從商務用 Store 下載新的套件來更新應用程式，以及在 Configuration Manager 中發佈應用程式修訂。 詳細資訊，請參閱使用 [Microsoft 端點群組原則管理員更新及淘汰應用程式](https://technet.microsoft.com/library/mt595704.aspx)。 

> [!NOTE] 
> 如果您使用 Microsoft 端點組 (目前分支) ，您可以將商務用 Store 連接到 Configuration Manager，以忽略上述步驟。 如此一來，您可以使用 Configuration Manager 同步處理您購買的應用程式清單，在 Configuration Manager 主控台中查看這些應用程式，然後像部署任何其他應用程式一樣進行部署。 詳細資訊，請參閱使用 [Configuration Manager 從商務用 Microsoft Store 管理應用程式](https://technet.microsoft.com/library/mt740630.aspx)。


## <a name="summary"></a>摘要

視您是否要開發應用程式、在少數裝置上評估應用程式，或將應用程式廣泛部署至貴組織，在 Surface Hub 上安裝應用程式的方法有一些不同。 下表摘要說明所支援的方法：

| 安裝方法             | 開發應用程式 | 在少數裝置上 <br> 評估應用程式 | 將應用程式廣泛部署 <br> 到組織中 |
| -------------------------- | --------------- | ------------------------------------- | ---------------------- |
| Visual Studio              | X |   |   |
| 佈建套件       | X | X |   |
| Microsoft 網上商店應用程式          |   | X |   |
| 支援的 MDM 提供者     |   |   | X |

## <a name="more-information"></a>詳細資訊

- [部落格文章：使用 Intune 將 Windows 市集應用程式部署到 Surface Hub](https://blogs.technet.microsoft.com/y0av/2018/01/18/7-2/)


## <a name="related-topics"></a>相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)

 

 





