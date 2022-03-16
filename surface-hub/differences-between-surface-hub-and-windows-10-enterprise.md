---
title: 作業系統基本資訊 (Surface Hub)
description: 本主題說明作業系統的獨特Windows 10 團隊版，以及它與作業系統Windows 10 企業版。
keywords: 變更歷程記錄
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/15/2022
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 6963a51b492bfbdc09da5ec667d091d62eed4569
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449236"
---
# <a name="operating-system-essentials-surface-hub"></a>作業系統基本資訊 (Surface Hub)

Surface Hub 作業系統 Windows 10 團隊版是以 Windows 10 企業版為基礎，針對企業管理、安全性及其他功能提供豐富支援。 但是，它們之間有重要差異。 企業版是針對電腦設計，Windows 10 團隊版則是針對大型螢幕和會議室從頭開始設計。 當您評估 Surface Hub 的安全性和管理需求時，最好是將它視為新的作業系統。 本文的設計是為協助凸顯 Surface Hub 上的 Windows 10 團隊版和 Windows 10 企業版的主要差異，以及這些差異對您的組織有哪些意義。

從 2020 年 9 月開始，客戶可選擇在 2S Windows 10 專業版 Enterprise移Surface Hub移。 若要深入了解，請參閱下列主題：

- [于 2 日宣佈Windows 10 專業版Enterprise Surface Hub可用](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/announcing-the-availability-of-windows-10-pro-and-enterprise-on/ba-p/1624107)。

- [移轉到 Windows 10 專業版或 Surface Hub 2 企業版](surface-hub-2s-migrate-os.md)

## <a name="user-interface"></a>使用者介面

### <a name="shell-os-user-interface"></a>殼層 (作業系統使用者介面)

Surface Hub 的殼層是針對大型螢幕和將觸控功能最佳化而從頭開始設計。 它並沒有使用和 Windows 10 企業版相同的殼層。

*這可能會影響下列組織原則：* 

- Windows 10 企業版殼層中相關控制向的設定不適用於 Surface Hub。

### <a name="lock-screen-and-screensaver"></a>鎖定畫面和螢幕保護程式

Surface Hub 沒有鎖定畫面或螢幕保護裝置，但它有稱為歡迎畫面的類似功能。 歡迎畫面會顯示裝置帳戶的行事曆中排定的會議，以及對以下 Surface Hub 最常用應用程式的簡易進入點 - 商務用 Skype、白板及連線。

*這可能會影響下列組織原則：* 

- 鎖定畫面、螢幕逾時及螢幕保護程式的設定不適用於 Surface Hub。

### <a name="user-sign-in"></a>使用者登入

Surface Hub 是針對在公共空間 (例如會議室) 使用所設計。 與 Windows 電腦不同，任何人都能接觸和使用 Surface Hub，且不需要使用者登入。 為了啟用這項公用功能，Surface Hub 不支援和 Windows 10 企業版登入方式一樣的 Windows 登入 (例如，將使用者登入作業系統，並在整個作業系統使用這些認證)。 反而是，永遠有本機自動登入的低權限使用者登入 Surface Hub。 不支援登入任何另外的使用者，包括系統管理員使用者 (例如，當系統管理員登入時，他們並未登入作業系統)。

使用者可以登入 Surface Hub，但無法登入作業系統。 例如，使用者登入 [應用程式] 或 [我的會議和檔案] 時，使用者只是登入應用程式或服務，而不是作業系統。 如此一來，登入的使用者可以存取他們儲存在雲端的雲端檔案及個人會議，而在啟動 **\[結束工作階段\]** 時捨棄這些認證。

*這可能會影響下列組織原則：* 

- 一般而言，Surface Hub 會使用鎖定功能，而不是使用者存取控制，來強制執行安全性。 與密碼需求、互動式登入、使用者帳戶，以及存取控制有關的原則不適用於 Surface Hub。

### <a name="saving-and-browsing-files"></a>儲存及瀏覽檔案

使用者可以存取 Surface Hub 上的一組有限目錄。
- 音樂
- 影片
- 文件
- 圖片
- 下載

儲存在這些本機目錄中的檔案會在使用者按下 **\[結束工作階段\]** 時刪除。 若要儲存會議期間建立的內容，使用者應將檔案儲存到 USB 磁碟機或 OneDrive。

*可能會影響的組織原則：*- 與存取許可權和檔案和資料夾擁有權相關的原則不適用於Surface Hub。 使用者無法瀏覽及儲存檔案到系統目錄與網路資料夾。

## <a name="applications"></a>應用程式

### <a name="default-applications"></a>預設應用程式

Surface Hub 上有幾個例外的預設通用 Windows 平台 (UWP)應用程式也可以在 Windows 10 電腦上使用。

Surface Hub 上預先安裝的 UWP應用程式：

- 鬧鐘與時鐘
- 小算盤
- 連線
- Excel Mobile
- 意見反應中樞
- 檔案總管
- 開始使用
- 地圖
- Microsoft Edge
- Microsoft Power BI
- Microsoft Teams
- Microsoft Whiteboard
- OneDrive
- 相片
- PowerPoint Mobile
- 設定
- 市集
- 提示
- Word Mobile

*這可能會影響下列組織原則：* 

- 請使用 Windows 10 企業版的指導方針來判斷 Surface Hub 上預設應用程式的功能和網路需求。

### <a name="installing-apps-drivers-and-services"></a>安裝應用程式、驅動程式及服務

為協助保留裝置原本的設備特性，Surface Hub 僅支援安裝通用 Windows 平台 (UWP) 應用程式，不支援安裝傳統 Win32應用程式、服務及驅動程式。 此外，只有系統管理員有權安裝 UWP應用程式。

*這可能會影響下列組織原則：* 

- 員工只能使用系統管理員已經安裝的應用程式，以協助防止用於非預期用途。 Surface Hub 不支援安裝大部分傳統電腦管理及監視工具所需的 Win32 代理程式。

## <a name="security-and-lockdown"></a>安全性和鎖定

針對要在公共空間 (例如會議室) 使用的 Surface Hub，其自訂作業系統會實作 Windows 10 中可用的許多安全性和鎖定功能。 若要深入瞭解，請參閱Surface Hub[概觀](surface-hub-security.md)

Surface Hub 會實作這些 Windows 10 安全性功能：

- [安全開機](/windows-hardware/design/device-experiences/oem-secure-boot)
- [Windows Defender 應用程式控制和虛擬式程式碼完整性保護](/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)
- [使用 AppLocker 的應用程式限制原則](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)
- [BitLocker 磁碟機加密](/windows/security/information-protection/bitlocker/bitlocker-overview)
- [信賴平台模組 (TPM)](/security/information-protection/tpm/trusted-platform-module-overview)
- [Microsoft Defender 防毒軟體 Windows](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)
- 用於存取設定應用程式的[使用者帳戶控制 (UAC)](/windows/security/identity-protection/user-account-control/user-account-control-overview)

這些 Surface Hub 功能可提供額外的安全性：

- 自訂 UEFI 韌體
- 自訂殼層與 \[開始\] 功能表可限制裝置只能使用會議功能
- 自訂檔案總管只會授與對 \[我的文件\] 底下的檔案和資料夾的存取權
- 自訂設定應用程式只會允許系統管理員修改裝置設定
- 已停用下載先進隨插及用驅動程式的功能

*這可能會影響下列組織原則：*

- 在針對 Surface Hub 執行您的安全性評估時，請考量這些功能。

## <a name="management"></a>管理

### <a name="device-settings"></a>裝置設定

裝置設定可以透過設定應用程式設定。 設定應用程式已經針對 Surface Hub 自訂，但也包含許多 Windows 10 Desktop 中許多熟悉的設定。 開啟設定應用程式時會顯示使用者帳戶控制 (UAC) 提示，以確認系統管理員的認證，但這樣並不會將系統管理員登入系統中。

*這可能會影響下列組織原則：* 

- 員工可以使用 Surface Hub 開會，但無法修改任何裝置設定。 除了鎖定功能之外，這也可以確保員工只能將裝置用於會議功能。

### <a name="administrative-features"></a>管理功能

系統不支援 Windows 10 企業版 中的管理功能，例如 Microsoft 管理主控台、執行、命令提示、PowerShell、登錄編輯器和工作管理員Surface Hub。 設定應用程式包含 Surface Hub 本機可用的所有系統管理功能。

#### <a name="event-viewer"></a>活動檢視器

Windows 10 團隊版 2020 Update 2 新增 Windows 事件檢視器的支援，與安裝在 Windows 10 專業版 或 Windows 10 企業版 的事件檢視器相同。[ ](/host-integration-server/core/windows-event-viewer1) 

**若要開啟活動檢視器：**

1. 使用系統管理員**認證設定**應用程式。
2. 選取**更新安全性&**  >  **，** 然後選取活動檢視器**下的開啟。** 

若要深入瞭解，請參閱[Windows檢視器](/host-integration-server/core/windows-event-viewer1)。

### <a name="remote-management-and-monitoring"></a>遠端管理及監視工具

Surface Hub透過行動裝置管理 (MDM) 解決方案 ，Microsoft Intune [Azure 監視器](/azure/azure-monitor/)進行監控。[ ](/mem/intune/) 

*這可能會影響下列組織原則：* 

- Surface Hub 不支援安裝大部分傳統電腦管理及監視工具所需的 Win32 代理程式，例如 System Center Operations Manager。

### <a name="group-policy"></a>群組原則

Surface Hub不支援群組Windows，包括稽核。 請改用 MDM 套用原則到您的 Surface Hub。 如需 MDM 的詳細資訊，請參閱[使用 MDM 提供者管理設定](manage-settings-with-mdm-for-surface-hub.md)。

*這可能會影響下列組織原則：* 

- 請使用 MDM 管理 Surface Hub，不要使用群組原則。

### <a name="remote-assistance"></a>遠端協助

Surface Hub 不支援遠端單協助。

*這可能會影響下列組織原則：* 

- 和遠端協助有關的原則不適用於 Surface Hub。

## <a name="network"></a>網路

### <a name="domain-join-and-azure-active-directory-azure-ad-join"></a>網域加入和 Azure Active Directory (Azure AD) 加入 

Surface Hub 主要使用網域加入和 Azure AD 加入來提供由目錄支援的系統管理員群組。 不支援混合式連接。 使用者無法使用網域帳戶登入。 如需相關資訊，請參閱[系統管理員群組管理](admin-group-management-for-surface-hub.md)。

*這可能會影響下列組織原則：* 

- 加入網域時，不會Surface Hub群組原則設定。 與網域成員資格相關的原則設定不適用於Surface Hub。

### <a name="accessing-domain-resources"></a>評估網域資源

使用者可以登入 Microsoft Edge 以存取內部網路網站和線上資源 (例如 Office 365)。 如果您的 Surface Hub 是使用裝置帳戶設定，系統會用它來存取 Exchange 和商務用 Skype。 但是，Surface Hub 不支援存取網域資源，例如檔案共用和印表機。

*這可能會影響下列組織原則：* 

- 和存取網域物件有關的原則不適用於 Surface Hub。

### <a name="diagnostic-data"></a>診斷資料

Surface Hub OS 會使用 Windows 10 已連線使用者體驗與遙測元件，來收集和傳輸診斷資料。 如需詳細資訊，請參閱[在您的組織中設定 Windows 診斷資料](/windows/privacy/configure-windows-diagnostic-data-in-your-organization)。

*這可能會影響下列組織原則：* 

- 請使用和 Windows 10 企業版相同的方式設定 Surface Hub 的診斷資料層級。
