---
title: 管理和部署 Surface 驅動程式與韌體更新
description: 本文提供可下載套件的連結，其中包含 Surface 裝置驅動程式和固件更新，並說明可用的管理和部署解決方案。
ms.assetid: CD1219BA-8EDE-4BC8-BEEF-99B50C211D73
ms.reviewer: ''
manager: laurawi
keywords: Surface， Surface Pro 8， Surface Go， Surface Laptop， Surface Studio， Surface Pro 3， 固件， 更新， 裝置， 管理， 部署， 驅動程式， USB
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 12/14/2021
ms.openlocfilehash: 6cfe5f44c156c8042172741739fffbfed3ceba07
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338576"
---
# <a name="manage-and-deploy-surface-driver-and-firmware-updates"></a>管理和部署 Surface 驅動程式與韌體更新

您管理 Surface 驅動程式和固件更新方式可能會根據您的環境與組織需求而有所差異。 在較大的組織中，IT 系統管理員通常會在內部階段部署，並撥出時間測試升級，然後再將升級推出至使用者裝置。

> [!NOTE]
> 本文適用于 IT 專業人員和技術支援代理，僅適用于 Surface 裝置。 如果您正在尋找在家用裝置上安裝 Surface 更新或固件的協助，請參閱下載 Surface 的驅動程式 [和固件](https://support.microsoft.com/help/4023505)。

雖然企業級軟體發佈解決方案持續演進，集中管理更新的企業理念仍然保持不變：維護 Surface 裝置的安全性，並持續更新最新作業系統和改良功能。 這是維持穩定的生產環境，並確保使用者不會遭到生產力封鎖所不可或缺的。

## <a name="whats-in-surface-driver-and-firmware-updates"></a>Surface 驅動程式和固件更新中的功能

Windows安裝程式.msi檔案包含所有 Surface 裝置所需的累積驅動程式和固件更新。 更新套件可能包含下列部分或所有元件：

- Wi-Fi和 LTE
- 影片
- 固態硬碟
- 系統匯總器模組 (SAM) 
- 電池
- 鍵盤控制器
- 內嵌控制器 (EC) 
- 管理引擎 (ME) 
- 統一可擴展的 UEFI (介面) 

## <a name="download-msi-files"></a>下載.msi檔案

本節提供可下載套件的直接連結，其中包含 Surface 裝置驅動程式和固件更新。 

1. 請Windows 10或Windows 11或選項。 
2. 針對有多個檔案.msi的裝置，請.msi與組織中部署的 Surface 模型和版本Windows名稱。  


| Surface 裝置                                                                                                                                        | 可下載.msi                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| ----------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Pro**                                                                                                                                       | - [Surface Pro 8](https://www.microsoft.com/en-us/download/details.aspx?id=103503)<br>- [Surface Pro 7+ Surface Pro 7+ (LTE) ](https://www.microsoft.com/en-us/download/details.aspx?id=102633)<br>- [Surface Pro 7](https://www.microsoft.com/download/details.aspx?id=100419)<br>- [Surface Pro 6](https://www.microsoft.com/download/details.aspx?id=57514)<br>- [Surface Pro 5 (LTE) ](https://www.microsoft.com/download/details.aspx?id=56278)<br>- [Surface Pro 5 (Wi-Fi) ](https://www.microsoft.com/download/details.aspx?id=55484)<br>- [Surface Pro 4](https://www.microsoft.com/download/details.aspx?id=49498)<br>- [Surface Pro 3](https://www.microsoft.com/download/details.aspx?id=38826)<br>- [Surface Pro 2](https://www.microsoft.com/download/details.aspx?id=49042)<br>- [Surface Pro](https://www.microsoft.com/download/details.aspx?id=49038) |
| **Surface 膝上型電腦**                                                                                                                                    | - [Surface Laptop Go](https://www.microsoft.com/download/details.aspx?id=102261)<br>- [Surface Laptop Intel 處理器使用 4](https://www.microsoft.com/download/details.aspx?id=102924)<br>- [Surface Laptop 4 使用AMD 處理器](https://www.microsoft.com/download/details.aspx?id=102923)<br>- [Surface Laptop 3 與 Intel 處理器](https://www.microsoft.com/download/details.aspx?id=100429)<br>- [Surface Laptop 3 與AMD 處理器](https://www.microsoft.com/download/details.aspx?id=100428)<br>- [Surface Laptop 2](https://www.microsoft.com/download/details.aspx?id=57515)<br>- [Surface Laptop](https://www.microsoft.com/en-us/download/details.aspx?id=55489)                                                                                                                                                                                    |
| **Surface Laptop工作室**                                                                                                                             | - [Surface Laptop工作室](https://www.microsoft.com/en-us/download/details.aspx?id=103505)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| **Surface Book**                                                                                                                                      | - [Surface Book 3](https://www.microsoft.com/download/details.aspx?id=101315)<br>- [Surface Book 2](https://www.microsoft.com/download/details.aspx?id=56261)<br>- [Surface Book](https://www.microsoft.com/download/details.aspx?id=49497)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Surface Go**                                                                                                                                        | - [Surface Go 3](https://www.microsoft.com/en-us/download/details.aspx?id=103504)<br>- [Surface Go 2](https://www.microsoft.com/download/details.aspx?id=101304)<br>- [Surface Go (Wi-Fi) ](https://www.microsoft.com/download/details.aspx?id=57439)<br>- [Surface Go (LTE) ](https://www.microsoft.com/download/details.aspx?id=57601)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Surface Studio**                                                                                                                                    | - [Surface Studio 2](https://www.microsoft.com/download/details.aspx?id=57593)<br>- [Surface Studio](https://www.microsoft.com/download/details.aspx?id=54311)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| **Surface 3**                                                                                                                                         | - [Surface 3 (Wi-Fi) ](https://www.microsoft.com/download/details.aspx?id=49040)<br>- [Surface 3 (LTE) - ATT](https://www.microsoft.com/download/details.aspx?id=49039)<br>- [Surface 3 (LTE) - Verizon](https://www.microsoft.com/download/details.aspx?id=49920)<br>- [Surface 3 (LTE) - 北美電信公司未鎖定](https://www.microsoft.com/download/details.aspx?id=49037)<br>- [Surface 3 (LTE) - 北美以外的地區，以及日本 Y！mobile](https://www.microsoft.com/download/details.aspx?id=49041)                                                                                                                                                                                                                                                                                                                                                   |
| **Surface Hub Windows 10 專業版**[**或Windows 10 企業版**](/surface-hub/surface-hub-2s-migrate-os)   | - [Windows 10 專業版 2 Enterprise上的 Surface Hub作業系統](https://www.microsoft.com/download/details.aspx?id=101974)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| **Surface Hub 2020 Windows 10 Teams更新**                                                                                                  | - 請參閱[管理Windows更新Surface Hub](/surface-hub/manage-windows-updates-for-surface-hub)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| **Surface Dock 2**                                                                                                                                    | - [Surface Dock 2](https://www.microsoft.com/download/details.aspx?id=101317)                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

 

> [!TIP]
> 針對包含不同版本不同檔案Windows的較舊版本，請選取.msi與 Surface 模型和版本名稱Windows。 .msi檔案名包含安裝驅動程式和Windows所需的最低支援建制編號。 例如，若要更新具有 Surface Book 18362 的 Windows 10 2，請選擇SurfaceBook2_Win10_18362_19.101.13994.msi **。** 對於具有 Surface Book 16299 之 Windows 10 2 的**SurfaceBook2_Win10_16299_1803509_3.msi。**

## <a name="central-update-management-in-commercial-environments"></a>商業環境中的中央更新管理

管理裝置的工具 ，包括驅動程式和固件更新 ，包含在[Microsoft 端點管理員。](https://devicemanagement.microsoft.com/) 

### <a name="manage-updates-with-configuration-manager-and-intune"></a>使用 Configuration Manager 和 Intune 管理更新

Microsoft Endpoint Configuration Manager可讓您與 Configuration Manager 用戶端同步處理及部署 Surface 固件和驅動程式更新。 與 Microsoft Intune整合可讓您在單一位置查看所有受管理、共同管理及合作夥伴管理的裝置。 這是大型組織管理 Surface 更新的建議解決方案。

有關詳細步驟，請參閱下列資源：

- [在 Configuration Manager 中管理 Surface 驅動程式更新](manage-surface-driver-updates-configuration-manager.md)
- [使用 Configuration Manager 部署應用程式](/configmgr/apps/deploy-use/deploy-applications)
- [端點組組管理員檔](/configmgr/)

### <a name="manage-updates-with-microsoft-deployment-toolkit"></a>使用 Microsoft 部署工具組管理更新

Microsoft 部署工具組 (MDT) 包含在端點群組原則管理器中。 視您的環境，它包含您可能想要使用的選擇性部署工具。  這些包括 Windows 評定和部署套件 (Windows ADK) 、Windows System Image Manager (Windows SIM) 、部署影像維護與管理 (DISM) ，以及使用者狀態移移工具 (USMT) 。 您可以從 Microsoft 部署工具組下載頁面下載 [最新版本的 MDT](https://www.microsoft.com/download/details.aspx?id=54259)。

有關詳細步驟，請參閱下列資源：

- [Microsoft 部署工具組檔](/configmgr/mdt/)
- [準備使用 MDT 進行部署](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)

有關如何使用端點 Configuration Manager 部署更新的指示，請參閱 [使用 Configuration Manager 部署應用程式](/configmgr/apps/deploy-use/deploy-applications)。 有關如何使用 MDT 部署更新的指示，請參閱使用[MDT 部署Windows 10映射](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)。

**WindowsPE 和 Surface 的固件和驅動程式**

端點組Windows和 MDT 在部署過程中 (WindowsPE) 預先安裝環境。 WindowsPE 僅支援一組有限的基本驅動程式，例如網路介面卡和儲存控制器。 非 WindowsPE Windows元件的驅動程式可能會產生錯誤。 最佳做法是，您可以將部署程式在 WindowsPE 階段期間只使用所需的驅動程式，以防止這類錯誤。

### <a name="endpoint-configuration-manager"></a>Endpoint Configuration Manager

從端點 Configuration Manager 開始，您可以使用 Configuration Manager 用戶端同步處理及部署 Microsoft Surface 固件和驅動程式更新。 有關其他資訊，請參閱 KB 4098906 [管理 Configuration Manager 中的 Surface 驅動程式更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)。

## <a name="supported-devices"></a>支援的裝置

除了在 ARM .msi 上執行 Windows 10 X 以外，Surface Pro 2 或更新 (裝置Surface Pro可下載) 。

## <a name="managing-firmware-with-dfci"></a>使用 DFCI 管理固件

Surface UEFI 管理 (內建 DFCI) [設定檔](/intune/configuration/device-firmware-configuration-interface-windows)，將新式管理堆疊延伸至 UEFI 硬體層級。 DFCI 支援零點式資源配置、消除BIOS 密碼、提供安全性設定 (包括啟動選項和內建的周邊設備) 的控制權，並打下未來進一步安全性案例的基礎。 如需詳細資訊，請參閱下列各項：

- [在 Surface 裝置上管理 DFCI](surface-manage-dfci-guide.md)
- [Ignite 2019：宣佈從 Intune 遠端系統管理 Surface UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

## <a name="best-practices-for-update-deployment-processes"></a>更新部署程式的最佳作法

若要維持穩定的環境，我們強烈建議您保持與最新版本的 Windows 10。  有關最佳做法建議，請參閱[準備用戶端更新Windows策略](/windows/deployment/update/waas-deployment-rings-windows-10-updates)。

### <a name="surface-msi-naming-convention"></a>Surface .msi命名慣例

自 2019 年 8 月.msi，所有檔案都使用下列命名慣例：

- *產品*_*Windows發行*_*Windows建立 numberVersion* _* *_ *numberRevision 版本*號碼 (一般為零) 。

**範例**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

此檔案名提供下列資訊：

- **產品：** SurfacePro6
- **Windows發行：** Win10
- **建立：** 18362
- **版本：** 19.073.44195 – 這會顯示建立檔案的日期和時間，如下所示：
  - **年份：** 2019 (19) 
  - **月與周：** 073 (年 7 月的第三周) 
  - **一個月的分鐘數：** 44195
- **版本修訂：0 (** 版本第一次發行) 

### <a name="legacy-surface-msi-naming-convention"></a>舊版 Surface .msi命名慣例

舊版.msi檔案 (于 2019 年 8 月之前) 遵循相同的整體命名公式，但使用不同的方法來推匯出版本號碼。

**範例**

- SurfacePro6_Win10_16299_1900307_0.msi

此檔案名提供下列資訊：

- **產品：** SurfacePro6
- **Windows發行：** Win10
- **建立：** 16299
- **版本：** 1900307 – 這會顯示檔案的建立日期及其在發行順序中的位置，如下所示：
  - **年份：** 2019 (19) 
  - **發行數量：** 003 (年第三次發行) 
  - **產品版本號碼：** 07 (Surface Pro 6 正式為第七版Surface Pro) 
- **版本修訂：0 (** 版本第一次發行) 

## <a name="learn-more"></a>深入了解

- [為 Windows 用戶端更新準備維護策略](/windows/deployment/update/waas-deployment-rings-windows-10-updates)
- [在 Configuration Manager 中管理 Surface 驅動程式更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [使用 Configuration Manager 部署應用程式](/configmgr/apps/deploy-use/deploy-applications)
- [端點組組管理員檔](/configmgr/)
- [Microsoft 部署工具組檔](/configmgr/mdt/)
- [準備使用 MDT 進行部署](/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [在 Surface 裝置上管理 DFCI](surface-manage-dfci-guide.md)
- [Ignite 2019：宣佈從 Intune 遠端系統管理 Surface UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

