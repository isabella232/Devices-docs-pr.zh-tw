---
title: 在 Configuration Manager 中管理 Surface 驅動程式更新
description: 本文將說明管理及部署 Surface 裝置之固件和驅動程式更新的可用選項。
ms.assetid: b64879c4-37eb-4fcf-a000-e05cbb3d26ea
ms.reviewer: ''
author: v-miegge
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, update, device, manage, deploy, driver, USB, 韌體, 更新, 裝置, 管理, 部署, 驅動程式
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.author: daclark
ms.topic: article
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e27f2ade66602c53c1bd0e7ef3d326834f1d95ed
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449176"
---
# <a name="manage-surface-driver-updates-in-configuration-manager"></a>在 Configuration Manager 中管理 Surface 驅動程式更新

## <a name="summary"></a>摘要

從[Microsoft System Center Configuration Manager版本 1710](/sccm/core/plan-design/changes/whats-new-in-version-1710#software-updates)開始，您可以直接透過 Configuration Manager 用戶端同步處理及部署 Microsoft Surface 的固件和驅動程式更新。 此程式類似部署定期更新。 不過，若要將 Surface 驅動程式更新納入您的目錄，還需要一些額外的配置。

## <a name="prerequisites"></a>必要條件

若要管理 Surface 驅動程式更新，必須符合下列先決條件：

- 您必須使用 Configuration Manager 版本 1710 或更新版本。
- 所有軟體更新點 (或更新) 必須Windows Server 2016或更新版本。 否則，Configuration Manager 會忽略此設定，且 Surface 驅動程式不會同步處理。

> [!NOTE]
> 如果您的環境不符合先決條件，請參閱常見問題區段的部署 Surface 驅動程式和[](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager#1)固件[更新的替代方法](#frequently-asked-questions-faq)。

## <a name="useful-log-files"></a>實用的記錄檔案

當您管理 Surface 驅動程式更新時，下列記錄特別有用。

|記錄名稱|描述|
|---|---|
|WCM.log|記錄有關軟體更新點組配置的詳細說明，以及訂閱的更新類別、分類和語言的 WSUS 伺服器連結。|
|WsyncMgr.log|記錄軟體更新同步處理常式的詳細資訊。|

這些記錄會位於管理 SUP 的網站伺服器上，如果直接安裝在網站伺服器上，則位於 SUP 本身。
有關 Configuration Manager 記錄的完整清單，請參閱在 System Center Configuration Manager 中[記錄System Center Configuration Manager](/sccm/core/plan-design/hierarchy/log-files)。

## <a name="enabling-surface-driver-updates-management"></a>啟用 Surface 驅動程式更新管理

若要在 Configuration Manager 中啟用 Surface 驅動程式更新管理，請遵循下列步驟：

1. 在 Configuration Manager 主控台中，前往**管理**  >  **OverviewSite**  >  **ConfigurationSite******  >  。
1. 選取包含您環境頂層 SUP 伺服器的網站。
1. 在功能區上， **選取設定網站元件**，然後選取 **軟體更新點**。 或者，以滑鼠右鍵按一下網站，然後選取 [**設定網站元件**  >  **軟體更新點**。
1. On the **Classifications** tab, select the **Include Microsoft Surface drivers and firmware updates** check box.

   ![軟體更新點元件屬性。](images/manage-surface-driver-updates-1.png)

1. 出現下列警告訊息時，請**選取確定。**

   ![Configuration Manager。](images/manage-surface-driver-updates-2.png)

1. 在 選項卡上，選取您想要更新的產品， **然後選取確定**。

   大部分的驅動程式屬於下列產品群組：

   - Windows 10及更新版本驅動程式
   - Windows 10及更新版本升級&維護驅動程式
   - Windows 10年更新與更新服務驅動程式
   - Windows 10年更新及更新更新&維護驅動程式
   - Windows 10 Creators Update及更新維護驅動程式
   - Windows 10 Creators Update及更新版本升級&維護驅動程式
   - Windows 10 Fall Creators Update及更新維護驅動程式
   - Windows 10 Fall Creators Update及更新更新&維護驅動程式
   - Windows 10 S 及更新的維護驅動程式
   - Windows 10版本 1709 及更新版本的維護驅動程式進行測試
   - Windows 10版本 1709 及更新版本升級&維護驅動程式進行測試

   > [!NOTE]
   > 大部分的 Surface 驅動程式屬於多個Windows 10或Windows 11組。 您可能不需要選取此處所列的所有產品。 為了協助減少填入更新目錄的產品數量，我們建議您只選取環境同步處理所需的產品。

## <a name="verifying-the-configuration"></a>驗證組組

若要確認 SUP 已正確配置，請遵循下列步驟：

1. 開啟 WsyncMgr.log，然後尋找下列專案：

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   Sync Catalog Drivers SCF value is set to : 1
   ```

   如果下列任何一項記錄在 WsyncMgr.log 中，請重新檢查上一節中的步驟 4：

   ```console
   Sync Surface Drivers option is not set

   Sync Catalog Drivers SCF value is set to : 0
   ```

1. 開啟 WCM.log，然後尋找類似下列專案：

   ![WCM.log 設定。](images/manage-surface-driver-updates-3.png)

   此專案是一個 XML 元素，會列出目前由 SUP 伺服器同步處理的每一個產品群組和分類。 例如，您可能會看到類似下列專案：

   ```xml
   <Categories>
       <Category Id="Product:05eebf61-148b-43cf-80da-1c99ab0b8699"><![CDATA[Windows 10 and later drivers]]></Category>
       <Category Id="Product:06da2f0c-7937-4e28-b46c-a37317eade73"><![CDATA[Windows 10 Creators Update and Later Upgrade & Servicing Drivers]]></Category>
       <Category Id="Product:c1006636-eab4-4b0b-b1b0-d50282c0377e"><![CDATA[Windows 10 S and Later Servicing Drivers]]></Category>
   </Categories>
   ```

   如果您在上一節的步驟 6 找不到您選取的產品，請仔細檢查是否已儲存 SUP 設定。

   您也可以等到下一個同步處理完成，然後檢查 Surface 驅動程式和固件更新是否列在 Configuration Manager 主控台的軟體更新中。 例如，主機可能會顯示下列資訊。

   ![所有軟體更新搜尋結果。](images/manage-surface-driver-updates-4.png)

## <a name="manual-synchronization"></a>手動同步處理

如果您不想等到下一次同步處理，請按照下列步驟開始同步處理：

1. 在 Configuration Manager 主控台中，前往**軟體庫**  >  **OverviewSoftware**  >  **Updates 所有**  >  **軟體更新**。
1. 在功能區上，選取 **同步軟體更新**。 或者，以滑鼠右鍵按一下 **[所有軟體更新**，然後選取 **同步軟體更新**。
1. 在 WsyncMgr.log 中尋找下列專案，以監控同步處理進度：

   ```console
   Surface Drivers can be supported in this hierarchy since all SUPs are on Windows Server 2016, WCM SCF property Sync Catalog Drivers is set.

   sync: SMS synchronizing categories 
   sync: SMS synchronizing categories, processed 0 out of 311 items (0%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing categories, processed 311 out of 311 items (100%)
   sync: SMS synchronizing updates

   Synchronizing update 7eaa0148-c42b-45fd-a1ab-012c82972de6 - Microsoft driver update for Surface Type Cover Integration
   Synchronizing update 2dcb07f8-37ec-41ef-8cd5-030bf24dc1d8 - Surface driver update for Surface Pen Pairing
   Synchronizing update 63067414-ae52-422b-b3d1-0382a4d6519a - Surface driver update for Surface UEFI
   Synchronizing update 8e4e3a41-a784-4dd7-9a42-041f43ddb775 - Surface driver update for Surface Integration
   Synchronizing update 7f8baee8-419f-47e2-918a-045a15a188e7 - Microsoft driver update for Surface DTX
   Synchronizing update aed66e05-719b-48cd-a0e7-059e50f67fdc - Microsoft driver update for Surface Base Firmware Update
   Synchronizing update 8ffe1526-6e66-43cc-86e3-05ad92a24e3a - Surface driver update for Surface UEFI
   Synchronizing update 74102899-0a49-48cf-97e6-05bde18a27ff - Microsoft driver update for Surface UEFI
   ```

## <a name="deploying-surface-firmware-and-driver-updates"></a>部署 Surface 固件和驅動程式更新

您可以像部署其他更新一樣，以相同的方式部署 Surface 固件和驅動程式更新。

有關部署詳細資訊，請參閱[2012 System Center Configuration Manager–Part7：軟體更新 (部署) ](https://blogs.technet.microsoft.com/elie/2012/05/25/system-center-2012-configuration-managerpart7-software-updates-deploy/)。

## <a name="frequently-asked-questions-faq"></a>常見問題 (FAQ)

**按照本文中的步驟進行之後，我的 Surface 驅動程式仍未同步處理。 為什麼？**

如果您從上Windows Server Update Services (WSUS) 伺服器進行同步處理，而不是 Microsoft Update，請確定上行 WSUS 伺服器已配置為支援及同步處理 Surface 驅動程式更新。 所有下游伺服器都受限於在上行 WSUS 伺服器資料庫中提供的更新。

WSUS 中超過 68，000 個更新被歸類為驅動程式。 為了防止非 Surface 相關驅動程式同步處理至 Configuration Manager，Microsoft 會針對允許清單篩選驅動程式同步處理。 發佈新允許清單並納入 Configuration Manager 之後，新驅動程式會隨著下次同步處理後新加入主控台。 Microsoft 希望每個月將 Surface 驅動程式新增到允許清單中，以配合每月更新版本，以便將它們同步處理至 Configuration Manager。

如果您的 Configuration Manager 環境離線，每次將維護更新導入 Configuration Manager 時，都會導入新的允許清單[](/mem/configmgr/core/servers/manage/use-the-service-connection-tool)。 在 Configuration Manager 主控台中顯示更新之前，您還必須導入包含驅動程式的新 [WSUS](/mem/configmgr/sum/get-started/synchronize-software-updates-disconnected) 目錄。 由於獨立 WSUS 環境包含的驅動程式比 Configuration Manager SUP 還要多，建議您建立具有線上功能的 Configuration Manager 環境，並設定它以同步處理 Surface 驅動程式。 這提供較小的 WSUS 匯出，與離線環境非常類似。

如果您的 Configuration Manager 環境是線上且能夠偵測到新的更新，則會自動收到清單的更新。 如果您沒看到預期的驅動程式，請針對任何同步處理失敗，查看 WCM.log 和 WsyncMgr.log 檔案。

**我的 Configuration Manager 環境已離線。 我可以手動將 Surface 驅動程式導入 WSUS 嗎？**

否。 即使更新已導入 WSUS，如果更新未列在允許清單中，也不會將更新導入到 Configuration Manager 主控台進行部署。 您必須使用服務 [連接工具](/mem/configmgr/core/servers/manage/use-the-service-connection-tool) 將維護更新導入 Configuration Manager，以更新允許清單。

**我有什麼替代方法可以部署 Surface 驅動程式和固件更新？**

若要瞭解如何透過替代通道部署 Surface 驅動程式和固件更新，請參閱 [管理 Surface 驅動程式和固件更新](manage-surface-driver-and-firmware-updates.md)。 如果您想要下載或.msi.exe，然後透過傳統的軟體部署通道進行部署，請參閱使用 [Configuration Manager 保持 Surface 固件更新](/archive/blogs/thejoncallahan/keeping-surface-firmware-updated-with-configuration-manager)。

## <a name="additional-information"></a>其他資訊

有關 Surface 驅動程式和固件更新的資訊，請參閱下列文章：

- [管理 Surface 的驅動程式和韌體更新](manage-surface-driver-and-firmware-updates.md)
- [Surface 和 System Center Configuration Manager 的考量](considerations-for-surface-and-system-center-configuration-manager.md)
