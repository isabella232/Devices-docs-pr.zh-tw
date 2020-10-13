---
title: 管理和部署 Surface 驅動程式與韌體更新
description: 本文說明管理和部署 Surface 裝置的固件與驅動程式更新的可用選項。
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
ms.openlocfilehash: 39022ca631e35f4328d3c353b7b0d1e2ebaee6a7
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114631"
---
# 管理和部署 Surface 驅動程式與韌體更新

您管理 Surface 驅動程式和固件更新的方式會視您的環境和組織需求而有所不同。 在 Surface 裝置上，固件會公開給作業系統作為驅動程式，且會顯示在 [裝置管理器] 中。 這可讓裝置固件及驅動程式使用 Windows Update 或商務用 Windows Update 來自動更新。 雖然這種簡化的方法可能適用于啟動和中小型企業，但大型組織通常需要 IT 系統管理員在內部發佈更新。 這可能會涉及完整的規劃、應用程式相容性測試，以及先導和驗證更新，然後再在整個網路上進行最終核准與發佈。

> [!NOTE]
> 本文適用于技術支援代理商和 IT 專業人員，且僅適用于 Surface 裝置。 如果您正在尋找在家用裝置上安裝 Surface 更新或固件的協助，請參閱 [更新 Surface 固件和 Windows 10](https://support.microsoft.com/help/4023505)。

雖然企業級軟體分發方案會繼續發展，但集中管理更新的商業基本原理仍會保持不變：維持 Surface 裝置的安全性，並使用最新的作業系統及功能改善來保持更新。 這對於維持穩定的生產環境至關重要，並確保不會封鎖使用者的生產力。 本文概述針對大型組織完成這些目標所建議的工具與程式。

## 在商業環境中的中央更新管理

Microsoft 有精簡的工具可用於管理裝置，包括驅動程式和固件更新--融入名為 [Microsoft 端點管理員](https://devicemanagement.microsoft.com/) 系統管理中心且從 [devicemanagement.microsoft.com](https://devicemanagement.microsoft.com/#home)存取的單一整合體驗。

### 使用 Configuration Manager 和 Intune 管理更新

Microsoft 端點 Configuration Manager 可讓您與 Configuration Manager 用戶端同步處理及部署 Surface 固件及驅動程式更新。 與 Microsoft Intune 整合可讓您在同一個位置查看所有受管理、共同管理和合作夥伴管理的裝置。 這是大型組織管理 Surface 更新的建議方案。

如需詳細步驟，請參閱下列資源：

- [在 Configuration Manager 中管理 Surface 驅動程式更新](https://docs.microsoft.com/surface/manage-surface-driver-updates-configuration-manager)
- [使用 Configuration Manager 部署應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [端點建構管理員檔](https://docs.microsoft.com/configmgr/)

### 使用 Microsoft 部署工具組管理更新

[端點設定管理員] 中包含 Microsoft 部署工具組 (MDT) 。 它包含您可能會想要使用的選用部署工具（視您的環境而定）。 其中包括 Windows 評估與部署套件 (Windows ADK) 、Windows 系統影像管理員 (Windows SIM) 、部署影像服務與管理 (DISM) ，以及使用者狀態遷移工具 (USMT) 。 您可以從 [ [Microsoft 部署工具](https://www.microsoft.com/download/details.aspx?id=54259)] 的 [下載] 頁面下載最新版本的 MDT。

如需詳細步驟，請參閱下列資源：

- [Microsoft 部署工具組檔](https://docs.microsoft.com/configmgr/mdt/)
- [使用 Microsoft Deployment Toolkit 部署 Windows10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [使用 Microsoft 部署工具組將 Windows 10 部署到 Surface 裝置](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)

表面驅動程式和固件更新封裝為 Windows 安裝程式 ( * .msi) 檔案。 若要部署這些 Windows 安裝程式套件，您可以使用端點建構管理員或 MDT。 如需如何為裝置和作業系統選取正確的 .msi 檔案的相關資訊，請參閱下列章節有關下載 .msi 檔案的指導方針。

如需有關如何使用端點建構管理員部署更新的指示，請參閱使用 [Configuration Manager 部署應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)。 如需如何使用 MDT 部署更新的相關指示，請參閱 [使用 Mdt 部署 Windows 10 影像](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt)。

**WindowsPE 和 Surface 固件與驅動程式**

端點設定管理員和 MDT 都在部署程式期間使用 Windows 預先安裝環境 (WindowsPE) 。 WindowsPE 僅支援一組有限的基本驅動程式，例如網路介面卡和儲存控制器的驅動程式。 不屬於 WindowsPE 的 Windows 元件驅動程式可能會產生錯誤。 最佳做法是，將部署程式設定為在 WindowsPE 階段只使用所需的驅動程式，就能避免這類錯誤。

### Endpoint Configuration Manager

從端點設定管理員開始，您可以使用 Configuration Manager 用戶端來同步處理及部署 Microsoft Surface 固件與驅動程式更新。 如需其他資訊，請參閱 KB 4098906， [如何在 Configuration Manager 中管理表面驅動程式更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)。

## 支援的裝置

您可以在 Surface Pro 2 和更新版本的裝置上使用可下載的 .msi 檔案，除了在) ARM 上執行 Windows 10 的 Surface Pro X 外 (。

## 使用 DFCI 管理固件

透過將裝置固件配置介面 (DFCI) 內置在 Intune 中的設定檔 (現已在 [公用預覽版](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)) 中提供，Surface UEFI 管理會將現代管理堆疊延伸到 UEFI 硬體層級。 DFCI 支援零觸控配，消除 BIOS 密碼，提供 (的安全性設定，包括啟動選項和內建的週邊) ，以及未來的高級安全性案例奠定基礎。 如需詳細資訊，請參閱下列文章：

- [Surface UEFI 設定的 Intune 管理](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019：宣佈從 Intune 遠端系統管理 SURFACE UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

## 更新部署程式的最佳做法

若要維持穩定的環境，我們強烈建議您使用最新版本的 Windows 10 維護同位。  如需最佳做法建議，請參閱 [建立適用于 Windows 10 更新的部署環](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)。

## 可下載的 Surface 更新套件

Windows 10 的特定版本有個別的 .msi 檔案，每個檔案都包含 Surface 裝置所需的所有必要累計驅動程式和固件更新。 更新套件可能包含以下部分或所有元件：

- Wi-Fi 與 LTE
- 影片
- 實體狀態磁片磁碟機
- 系統聚合模組 (SAM) 
- 電池
- 鍵盤控制器
- 內嵌控制器 (EC) 
- 管理引擎 (我) 
- 整合的可延伸韌體介面 (UEFI) 

### 下載 .msi 檔案

1. 在 Microsoft 下載中心，流覽以 [下載 Surface 的驅動程式和固件](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware) 。
2. 選取與 Surface 模型和 Windows 版本相符的 .msi 檔案名。 .Msi 檔案名包括安裝驅動程式和固件所需的最低 Windows 組建編號。 例如，請參閱下圖。 若要更新具有 Windows 10 組建18362的 Surface Book 2，請選擇 [ **SurfaceBook2_Win10_18362_19.101.13994.msi]。** 針對 Windows 10 版組建16299的 Surface Book 2，請選擇 [ **SurfaceBook2_Win10_16299_1803509_3.msi**]。

    ![圖 1。 下載 Surface 更新](images/fig1-downloads-msi.png)

    *圖 1。 下載 Surface 更新*

### 您的 Surface. msi 命名慣例

自2019年8月起，.msi 檔案使用下列命名慣例：

- *產品*_*windows 發行*_*windows 組建*版本號版本號碼的_*版本編號*_*修訂 (通常是零) *。

**範例**

- SurfacePro6_Win10_18362_19.073.44195_0.msi

此檔案名提供下列資訊：

- **產品：** SurfacePro6
- **Windows 版本：** Win10
- **組建：** 18362
- **版本：** 19.073.44195 –這會顯示檔的建立日期和時間，如下所示：
  - **年份：** 19 (2019) 
  - **月份與星期：** 073 (七月) 第三周
  - **月份的分鐘數：** 44195
- **版本：** 0 (第一次發行此版本) 

### 傳統 Surface. msi 命名慣例

舊版 .msi 檔案 (在) 2019 年8月之前建立的檔案，但已使用相同的整體命名公式，但使用不同的方法來衍生版本號碼。

**範例**

- SurfacePro6_Win10_16299_1900307_0.msi

此檔案名提供下列資訊：

- **產品：** SurfacePro6
- **Windows 版本：** Win10
- **組建：** 16299
- **版本：** 1900307 –這會顯示建立檔案的日期，以及其在發行順序中的位置，如下所示：
  - **年份：** 19 (2019) 
  - **發行次數：** 003 (年的第三版) 
  - **產品版本號碼：** 07 (surface pro 6 正式是第七版 Surface pro) 
- **版本：** 0 (第一次發行此版本) 

## 深入了解

- [下載 Surface 的驅動程式和固件](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware)
- [如何在 Configuration Manager 中管理 Surface driver 更新](https://support.microsoft.com/help/4098906/manage-surface-driver-updates-in-configuration-manager)
- [使用 Configuration Manager 部署應用程式](https://docs.microsoft.com/configmgr/apps/deploy-use/deploy-applications)
- [端點建構管理員檔](https://docs.microsoft.com/configmgr/)
- [Microsoft 部署工具組檔](https://docs.microsoft.com/configmgr/mdt/)
- [使用 Microsoft Deployment Toolkit 部署 Windows10](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-windows-10-with-the-microsoft-deployment-toolkit)
- [使用 Microsoft 部署工具組將 Windows 10 部署到 Surface 裝置](https://docs.microsoft.com/surface/deploy-windows-10-to-surface-devices-with-mdt)  
- [Surface UEFI 設定的 Intune 管理](https://docs.microsoft.com/surface/surface-manage-dfci-guide)
- [Ignite 2019：宣佈從 Intune 遠端系統管理 SURFACE UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。
- [為 Windows10 更新建置部署更新步調](https://docs.microsoft.com/windows/deployment/update/waas-deployment-rings-windows-10-updates)
