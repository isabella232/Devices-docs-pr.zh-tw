---
title: 部署、管理及維護 Surface Pro X
description: 本文概述部署、管理及維護 Surface Pro X 的重要考量。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: high
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 202818488f19c82ba9d08cfcbfcd091e3e8b7bf6
ms.sourcegitcommit: 7d5b0a7948eb540d6849a0e2c70a1058584cc5f8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2020
ms.locfileid: "11105838"
---
# 部署、管理及維護 Surface Pro X

## 簡介

Surface Pro X 專為滿足高效能商業需求而打造，結合了該等級中空前強大的處理器 Microsoft SQ1 以及 Microsoft SQ1 ARM 晶片組，從而開創了全新的局面。

Surface Pro X 由 3GHz CPU 與 2.1 teraflop GPU 提供支援，讓您享有完整的 Windows 體驗。 電池使用時間長達 15 小時並且內建 Gigabit LTE，集觸控、手寫筆、平板電腦、和膝上型電腦為一身，非常適合金融、法律和醫學等領域的各類第一線員工及專業人員，或任何需要超長電池使用時間和持續連線功能的職務角色。

Surface Pro X 是專為現代化雲端式環境所設計，最適合與 Microsoft 365、Intune 和 Windows Autopilot 搭配使用。 本文將對具體內容多所著墨，並概述部署、管理及維護 Surface Pro X 的重要考量。

## 部署 Surface Pro X

為獲得最佳體驗，請使用 Windows Autopilot 在 Microsoft 雲端解決方案提供者的協助下部署 Surface Pro X，或是使用 Autopilot 部署設定檔和相關功能進行自我佈建。 如需詳細資訊，請參閱：

- [Windows Autopilot 與 Surface 裝置](windows-autopilot-and-surface-devices.md)
- [Windows Autopilot 概觀](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot)

Autopilot 部署有幾個優點：允許您使用針對全自動部署所簡化的原廠佈建作業系統，將預先安裝的 Office Pro Plus 納入其中。

已經使用現代化管理、安全性及生產力解決方案的組織具備得天獨厚的優勢，可以利用 Surface Pro X 中特有的效能功能。使用現代化企業營運應用程式、Microsoft Store (UWP) 應用程式或遠端桌面解決方案的客戶也將受益匪淺。

## 映像式部署考量

Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager (舊稱 System Center Configuration Manager) 目前不支援 Surface Pro X 進行作業系統部署。 在持續評估轉換至現代部署解決方案適當時機的期間，仰賴映像式部署的客戶不妨考慮 Surface Pro 7。 

## 管理 Surface Pro X 裝置

### Intune

Intune 是 Microsoft Enterprise Mobility + Security 的元件，可與 Azure Active Directory 整合以進行身分識別和存取控制，並可提供對已註冊 Surface Pro X 裝置的細微管理。 Intune 行動裝置管理 (MDM) 原則與舊版內部部署工具 (例如 Windows 群組原則) 相比，具有許多優勢。 這包括更快速的裝置登入時間，以及更加簡化得可以完全從雲端管理裝置的原則資料目錄。 例如，您可以使用 eSIM 設定檔管理 LTE 以設定行動數據方案，並將啟動碼部署至多個裝置。<br> 

如需有關使用 Intune 的詳細資訊，請參閱 [Intune 文件](https://docs.microsoft.com/intune/)。

### 共同管理

使用 Autopilot 進行部署後，您可以將 Surface Pro X 裝置加入 Azure AD 或 Active Directory (混合式 Azure AD Join)，這樣就能在其中使用 Intune 來管理裝置，或是使用 Endpoint Configuration Manager (將會安裝 32 位元 x86 ConfigMgr 用戶端) 來共同管理這些裝置。

### 協力廠商 MDM 解決方案

您或許可以使用協力廠商 MDM 工具來管理 Surface Pro X 裝置。 如需詳細資訊，請連絡 MDM 提供者。

### 防毒軟體

Windows Defender 會在 Windows 10 裝置的支援期間協助保護 ARM 型電腦上的 Windows 10。 

部分協力廠商防毒軟體無法安裝在使用 ARM 型處理器執行的 Windows 10 電腦。 仍持續與協力廠商防毒軟體提供者進行合作，處理防毒應用程式在 ARM 型電腦上的整備工作。 請連絡防毒軟體提供者，以了解他們的應用程式何時會推出。

## 維護 Surface Pro X

Surface Pro X 會附帶 Windows 10 版本 2004，且支援 Windows 10 版本 1903 和更新的版本。 由於是 ARM 型裝置，此產品在維持最新驅動程式和韌體方面有特定需求。 

Surface Pro X 已設計成使用 Windows Update 來為家庭使用者和小型企業使用者簡化保持驅動程式及韌體處於最新狀態的程序。 使用預設的設定來接收自動更新。  若要確認：

1. 移至 **\[開始\]** > **\[設定\] > \[更新與安全性\] > \[Windows Update\]** > **\[進階選項\]**。
2. 在 **\[擇更新安裝方式\]** 下方選取 **\[自動 (建議選項)\]**。

### 對商業客戶的建議

- 使用 Windows Update 或商務用 Windows Update 來維護最新的驅動程式和韌體。 如需詳細資訊，請參閱[使用商務用 Windows Update 來部署更新](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)。
- 如需有關在 Surface 裝置上部署和管理更新的詳細資訊，請參閱[管理和部署 Surface 驅動程式與韌體更新](manage-surface-driver-and-firmware-updates.md)。
- 請注意，Windows Server Update Services (WSUS) 不支援傳遞驅動程式和韌體至 Surface Pro X 的功能。

## 在 Surface Pro X 上執行應用程式

除了少數例外，大部分應用程式都會在 ARM 型 Windows 10 電腦上執行。

### 支援的應用程式

- 大部分 x86 Win32 應用程式會在 Surface Pro X 上執行。
- 原生 ARM64 和 Microsoft Store UWP 應用程式在最佳化電池使用時間的同時，利用 ARM 型處理器的完整原生速度提供絕佳使用者體驗。
- 使用專為透過 ARM 型處理器執行之 Windows 10 電腦所設計的驅動程式的應用程式。

> [!NOTE]
> 使用預覽版中透過 Windows 測試人員計畫即將推出的 64 位元模擬，您就能在 Surface Pro X 上執行 64 位元 (x64) 應用程式。

### FastTrack 應用程式 Assure 

The App Assure 計劃可供商業客戶用於 ARM 上針對 Windows 10 的 LOB、ISV 和 Microsoft 第一方應用程。 如果商業版在 ARM 上使用 Windows 10 發生應用程式相容性問題，Microsoft 會提供開發人員資源，以便在不額外付費的情況下，進行疑難排解和協助修復應用程式。 若要深入瞭解，請瀏覽 aka.ms/AppAssure


如需有關在 Surface Pro X 上執行應用程式的詳細資訊，請參閱：

- [Windows 10 ARM 型電腦支援常見問題集](https://support.microsoft.com/help/4521606)
- [ARM 上的 Windows 10 文件](https://docs.microsoft.com/windows/arm)

## 虛擬桌面 (VDI)

Windows 虛擬桌面可讓您在任何運算裝置或平台上，從任何位置存取 Windows 桌面、應用程式和資料 若要深入了解，請參閱 [Windows 虛擬桌面網站](https://aka.ms/wvd)。 

## 使用 Surface Pro X 進行瀏覽

在 Surface Pro X 上執行的熱門瀏覽器：

- 內建 Edge、Firefox、Chrome 和 Internet Explorer 都可在 Surface Pro X 上執行。
- 以 Chromium 為基礎的內建 Firefox 和 Microsoft Edge 以原生方式執行，因此效能在使用 ARM 型處理器的 Windows 10 電腦上有所提升。

## 安裝和使用 Microsoft Office

- 在使用 ARM 型處理器的 Windows 10 電腦上使用 Office 365 可獲得最佳體驗。
- Office 365「隨選即用」會安裝 Outlook、Word、Excel 和 PowerPoint，並已經過最佳化，可在使用 ARM 型處理器的 Windows 10 電腦上執行。
- Microsoft Teams 在 Surface Pro X 上的執行效能絕佳。
- 對於 Office 的「永久版本」(例如 Office 2019)，請安裝 32 位元版本。

## VPN

若要確認特定協力廠商 VPN 是否支援使用 ARM 型處理器的 Windows 10 電腦，請連絡 VPN 提供者。

## 重點摘要

下表顯示 Surface Pro X 在配合 ARM 上的 Windows 10 使用時，可用的特選關鍵功能。


**部署**

| 功能                                                           | 是/否 | 附註                                                                                                                             |
| ----------------------------------------------------------------- | --- | --------------------------------------------------------------------------------------------------------------------------------- |
| Windows Autopilot                                                 | 是 |                                                                                                                                   |
| 支援網路開機 (PXE)                                    | 否  |                                                                                                                                   |
| Windows 設定設計工具                                    | 否  | 不建議用於 Surface Pro X。                                                                                                |
| WinPE                                                             | 是 | 不建議用於 Surface Pro X。Microsoft 不提供支援與 WinPE 搭配使用 Surface Pro X 所需的 .ISO 和驅動程式。 |
| Endpoint Configuration Manager：作業系統部署 (OSD) | 否  | 在 Surface Pro X 上不支援。                                                                                                   |
| MDT                                                               | 否  | 在 Surface Pro X 上不支援。                                                                                                   |

 
 
 **Management**
 

| 功能                                       | 是/否     | 附註                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| Intune                                        | 是     | 使用 eSIM 設定檔管理 LTE。                                                        |
| Windows Autopilot                             | 是     |                                                                                       |
| Azure AD (共同管理)                      | 是     | 將 Surface Pro X 加入 Azure AD 或 Active Directory (混合式 Azure AD Join) 的功能。 |
| Endpoint Configuration Manager                | 是     |                                                                                       |
| AC 恢復時開啟電源                      | 是     |                                                                                       |
| 商務用 Surface 診斷工具組 (SDT) | 是     |                                                                                       |
| Surface 資產標記工具                        | 是     |                                                                                       |
| Surface 企業管理模式 (SEMM)     | 部分 | Surface Pro X 沒有在韌體層級停用硬體的選項。                 |
| Surface UEFI 設定程式                     | 否      | 沒有停用硬體的選項。 在 Surface Pro X 的韌體層級上。                |
| Surface UEFI 管理員                          | 部分 | Surface Pro X 沒有在韌體層級停用硬體的選項。                 |

 

**安全性**
 

 功能                                       | 是/否     | 附註                                                                                 |
| --------------------------------------------- | ------- | ------------------------------------------------------------------------------------- |
| BitLocker                                     | 是     |                                                       |
| Windows Defender                              | 是     |                                                                                       |
| 支援協力廠商防毒軟體             | 請參閱附註| 部分協力廠商防毒軟體無法安裝在使用 ARM 型處理器執行的 Windows 10 電腦。 仍持續與協力廠商防毒軟體提供者進行合作，處理防毒應用程式在 ARM 型電腦上的整備工作。 請連絡防毒軟體提供者，以了解他們的應用程式何時會推出。 |
| 安全開機               | 是     |                                                                                       |
| Windows 資訊保護                      | 是     |                                                                                       |
| Surface Data Eraser (SDE)     | 是     |                                                                                       |




## 常見問題集

### 是否可以使用 MDT 或 Endpoint Configuration Manager 來部署 Surface Pro X？

Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager 目前不支援 Surface Pro X 進行作業系統部署。仰賴映像式部署的客戶在持續評估轉換至雲端適當時機的期間，應考慮使用 Surface Pro 7。

### 如何部署 Surface Pro X？

使用 Windows Autopilot 來部署 Surface Pro X。

### 可以使用 BMR 嗎？

是，請參閱 [下載 Surface 的復原影像](https://support.microsoft.com/surfacerecoveryimage).。

### 是否必須有 Intune 才能管理 Surface Pro X？

建議使用 Intune，但並非必要。 使用 Autopilot 進行部署後，您可以將 Surface Pro X 裝置加入 Azure AD 或 Active Directory (混合式 Azure AD Join)，這樣就能在其中使用 Intune 來管理裝置，或是使用 Endpoint Configuration Manager (將會安裝 32 位元 x86 ConfigMgr 用戶端) 來共同管理這些裝置。
