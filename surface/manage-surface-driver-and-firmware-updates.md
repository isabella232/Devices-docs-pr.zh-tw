---
title: 管理和部署 Surface 驅動程式與韌體更新
description: 本文將說明管理及部署 Surface 裝置之固件和驅動程式更新的可用選項。
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface, Surface Pro 3, firmware, update, device, manage, deploy, driver, USB, 韌體, 更新, 裝置, 管理, 部署, 驅動程式
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 10/12/2020
ms.openlocfilehash: afc7b2e82519fb42ca07b107bff73ddea894cfdf
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911638"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>管理和部署 Surface 驅動程式與韌體更新

如何管理 Surface 驅動程式和固件更新會根據您的環境和組織需求而不同。 在 Surface 裝置上，固件會以驅動程式方式公開至作業系統，且顯示在 Device Manager 中。 這可讓裝置固件和驅動程式使用 Windows 更新或Windows更新功能自動更新。 雖然這種簡化的方法可能適用于初創企業和中小型企業，但較大的組織通常需要 IT 系統管理員在內部發佈更新。 這可能包括全面規劃、應用程式相容性測試，以及試驗及驗證更新，然後再在整個網路上進行最終核准和發佈。

> [!NOTE]
> 本文適用于技術支援人員與 IT 專業人員，僅適用于 Surface 裝置。 如果您正在尋找在家用裝置上安裝 Surface 更新或固件的協助，請參閱更新[Surface](https://support.microsoft.com/help/4023505)Windows 10。

雖然企業級軟體發佈解決方案持續演進，集中管理更新的企業理念仍然保持不變：維護 Surface 裝置的安全性，並持續更新最新作業系統和改良功能。 這是維持穩定的生產環境，並確保使用者不會遭到生產力封鎖所不可或缺的。 本文提供建議工具與程式概觀，供較大型組織完成這些目的。

## <a name="central-update-management-in-commercial-environments"></a>商業環境中的中央更新管理

Microsoft 已簡化裝置管理工具 ，包括驅動程式[和](https://devicemanagement.microsoft.com/)固件更新，以單一統一體驗Microsoft 端點管理員系統管理中心，且從 devicemanagement.microsoft.com[存取。](https://devicemanagement.microsoft.com/#home)

### <a name="manage-updates-with-configuration-manager-and-intune"></a>使用 Configuration Manager 和 Intune 管理更新

Microsoft Endpoint Configuration Manager可讓您與 Configuration Manager 用戶端同步處理及部署 Surface 固件和驅動程式更新。 與 Microsoft Intune整合可讓您在單一位置查看所有受管理、共同管理及合作夥伴管理的裝置。 這是大型組織管理 Surface 更新的建議解決方案。

有關詳細步驟，請參閱下列資源：

- [在 Configuration Manager 中管理 Surface 驅動程式更新](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [使用 Configuration Manager 部署應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [端點組組管理員檔](https://docs.microsoft.com/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>使用 Microsoft 部署工具組管理更新

Microsoft 部署工具組 (MDT) 包含在端點群組原則管理器中。 它包含視您的環境而您可能想要使用的選擇性部署工具。 這些包括 Windows 評定和部署套件 (Windows ADK) 、Windows 系統映射管理員 (Windows SIM 卡) 、部署影像維護與管理 (DISM) ，以及使用者狀態移移工具 (USMT) 。 您可以從 Microsoft 部署工具組下載頁面下載 [最新版本](https://www.microsoft.com/download/details.aspx?id=54259)的 MDT。

有關詳細步驟，請參閱下列資源：

- [Microsoft 部署工具組檔](https://docs.microsoft.com/configmgr/mdt/)
- [使用 Microsoft Deployment Toolkit 部署 Windows10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [使用 microsoft Windows 10工具組將部署至 Surface 裝置](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

Surface 驅動程式和固件更新會封裝Windows安裝程式 (*.msi) 檔案。 若要部署這些Windows安裝程式套件，您可以使用端點群組原則管理員或 MDT。 若要瞭解如何為裝置和作業系統.msi正確的檔案，請參閱下列各節中有關下載檔案.msi指南。

有關如何使用端點 Configuration Manager 部署更新的指示，請參閱 [使用 Configuration Manager 部署應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)。 有關如何使用 MDT 部署更新的指示，請參閱使用[MDT](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)部署Windows 10映射。

**WindowsPE 和 Surface 的固件和驅動程式**

端點組Windows和 MDT 在部署 (WindowsPE) 預先安裝環境。 WindowsPE 僅支援一組有限的基本驅動程式，例如網路介面卡和儲存控制器的驅動程式。 非 WindowsPE Windows元件的驅動程式可能會產生錯誤。 最佳做法是，您可以將部署程式在 WindowsPE 階段期間只使用所需的驅動程式，以防止這類錯誤。

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

從端點 Configuration Manager 開始，您可以使用 Configuration Manager 用戶端同步處理及部署 Microsoft Surface 固件和驅動程式更新。 有關其他資訊，請參閱 KB [4098906，如何在 Configuration Manager](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)中管理 Surface 驅動程式更新。

## <a name="supported-devices"></a>支援的裝置

除了在 ARM .msi 上執行 Windows 10 X 之外，Surface Pro 2 或更新 (裝置Surface Pro可下載Windows 10) 檔案。

## <a name="managing-firmware-with-dfci"></a>使用 DFCI 管理固件

有了 Intune (內建的 DFCI) 設定檔 (現在可在公用預覽 [) ](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows) 中使用，Surface UEFI 管理可將新式管理堆疊延伸至 UEFI 硬體層級。 DFCI 支援零接觸式部署、消除BIOS 密碼、提供安全性設定 (包括啟動選項和內建的周邊設備) 的控制權，以及為未來的進一步安全性案例打下基礎。 如需詳細資訊，請參閱下列文章：

- [Surface UEFI 設定的 Intune 管理](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019：宣佈從 Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)遠端系統管理 Surface UEFI 設定。

## <a name="best-practices-for-update-deployment-processes"></a>更新部署程式的最佳作法

若要維持穩定的環境，我們強烈建議您維持與最新版本的 Windows 10。  有關最佳做法建議，請參閱為更新[建立部署Windows 10環](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)。

## <a name="downloadable-surface-update-packages"></a>可下載的 Surface 更新套件

特定的版本Windows 10個別.msi檔案，每個檔案都包含 Surface 裝置所需的所有累積驅動程式和固件更新。 更新套件可能包含下列部分或所有元件：

- Wi-Fi和 LTE
- 影片
- 固態硬碟
- 系統匯總器模組 (SAM) 
- 電池
- 鍵盤控制器
- 內嵌控制器 (EC) 
- 管理引擎 (ME) 
- 統一可擴展的 UEFI (介面) 

### <a name="downloading-msi-files"></a>下載.msi檔案

1. 流覽至 [Microsoft 下載中心上的下載 Surface](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) 驅動程式和固件。
2. 選取.msi與 Surface 模型和版本名稱Windows。 .msi檔案名包含安裝驅動程式和Windows所需的最低支援建制編號。 例如，請參閱下圖。 若要更新具有 Surface Book 18362 的 Windows 10 2，請選擇**SurfaceBook2_Win10_18362_19.101.13994.msi。** 對於具有 Surface Book 16299 的 Surface Book 2，請選擇**SurfaceBook2_Win10_16299_1803509_3.msi**Windows 10 。

    ![圖 1。 下載 Surface 更新。](images/fig1-downloads-msi.png)

    *圖 1。 下載 Surface 更新*

### <a name="surface-msi-naming-convention"></a>Surface .msi命名慣例

自 2019 年 8 月.msi，所有檔案都使用下列命名慣例：

- *產品*_*Windows版本Windows*_ 版本*號碼*_**_ 版本號碼 版本號碼版本號碼修訂 (一般為*零) 。*

**範例**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

此檔案名提供下列資訊：

- **產品：** SurfacePro6
- **Windows發行：** Win10
- **建立** ：18362
- **版本** ：19.073.44195 – 這會顯示建立檔案的日期和時間，如下所示：
  - **年份** ：2019 (19) 
  - **月與周** ：073 (年 7 月的第三周) 
  - **一個月的分鐘數** ：44195
- **版本修訂：0 (** 版本第一次發行) 

### <a name="legacy-surface-msi-naming-convention"></a>舊版 Surface .msi命名慣例

舊版.msi檔案 (于 2019 年 8 月前建立) 遵循相同的整體命名公式，但使用不同的方法來推匯出版本號碼。

**範例**

- SurfacePro6_Win10_16299_1900307_0.msi

此檔案名提供下列資訊：

- **產品：** SurfacePro6
- **Windows發行：** Win10
- **建立** ：16299
- **版本：1900307** – 這會顯示檔案的建立日期及其在發行順序中的位置，如下所示：
  - **年份** ：2019 (19) 
  - **發行數量** ：003 (年第三次發行) 
  - **產品版本號碼：07** (Surface Pro 6 正式為第七版 Surface Pro) 
- **版本修訂：0 (** 版本第一次發行) 

## <a name="learn-more"></a>深入了解

- [下載 Surface 的驅動程式和固件](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [如何在 Configuration Manager 中管理 Surface 驅動程式更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [使用 Configuration Manager 部署應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [端點組組管理員檔](https://docs.microsoft.com/configmgr/)
- [Microsoft 部署工具組檔](https://docs.microsoft.com/configmgr/mdt/)
- [使用 Microsoft Deployment Toolkit 部署 Windows10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [使用 microsoft Windows 10工具組將部署至 Surface 裝置](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Surface UEFI 設定的 Intune 管理](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019：宣佈從 Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)遠端系統管理 Surface UEFI 設定。
- [為 Windows 10 更新建置部署更新步調](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
