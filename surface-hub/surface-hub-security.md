---
title: Surface Hub 安全性概述
description: 本頁說明 Surface Hub 深入防禦的設計，並說明 Surface Hub 2S、無線安全性保護和相關功能的安全性增強功能。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: coveminer
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 01/26/2021
ms.localizationpriority: High
ms.openlocfilehash: cd0112f805b60b16c7f32099d5f5e3fde3c821fb
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911378"
---
# <a name="surface-hub-security-overview"></a>Surface Hub 安全性概述

Surface Hub 提供鎖定的類設備體驗，具有執行 Windows 10 團隊版作業系統的自訂平台韌體。 產生的裝置採用傳統「單一使用」安全 kiosk，「只執行所需的」哲學，並為其提供新式工作。 Surface Hub 是建置以支援豐富的共同作業使用者體驗，受到保護以防禦不斷演變的安全性威脅。

Surface Hub 內建在 Windows 10 上，提供企業級新式安全性，讓 IT 系統管理員能夠使用 BitLocker、信賴平台模組 2.0 (TPM) 強制執行資料保護，以及使用 Windows Defender (也稱為 Microsoft Defender) 的雲端技術安全性。

## <a name="defense-in-depth-security"></a>深入防禦安全性

當 Surface Hub 開啟時，就會立即開始安全性通訊協定。 從韌體層級開始，Surface Hub 只會載入作業系統及其元件，以回應多重安全性檢查。 Surface Hub 採用稱為「深入防禦」的策略，其中涉及到分層獨立防護子元件，以便在部分失敗時保護整個系統。 這個產業實務已證明，在針對子元件中的潛在單邊入侵和弱點方面是非常有效。

Microsoft 會靜態且安全地設定新式整合可延伸韌體介面 (UEFI)，只從內部儲存體啟動經過驗證的 Windows 10 團隊版作業系統。  在 Surface Hub 上執行的每一行程式碼，在執行前都會驗證其簽章。 只有由 Microsoft 所簽署的應用程式 (屬於作業系統或是透過 Microsoft Store 安裝)，才能在 Surface Hub 上執行。 無法符合這些需求的程式碼或應用程式會遭到封鎖。

Surface Hub 安全性系統包含下列項目：

- **開機時防護。** 僅載入信任的 Surface Hub 作業系統元件。
- **作業系統防護。** 防範執行非預期或惡意軟體或程式碼。
- **使用者介面防護。** 提供對於使用者而言是安全的使用者介面，防止存取潛在有風險的活動，例如，從命令列執行可執行檔。

### <a name="boot-time-defenses"></a>開機時防護

SoC 的安全處理器與其他核心不同。 當您第一次啟動 Surface Hub 時，僅有安全處理器會先啟動，然後才載入其他任何項目。

![Hub 啟動開機階段顯示著安全處理器保護。](images/hub-sec-1.png)

#### <a name="secure-boot"></a>安全開機

「安全開機」是用來驗證開機程序的元件，包括驅動程式和作業系統，根據有效和已知的簽章進行驗證。 在 Surface Hub 上，必須先驗證平台特定簽章，然後才可以載入授權的 Windows 團隊版作業系統。 這可協助防止隱藏在正常使用者體驗中，來自執行惡意程式碼的複製或修改過系統的攻擊。  如需詳細資訊，請參閱[安全開機概觀](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。

### <a name="operating-system-defenses"></a>作業系統防護

當作業系統驗證為來自 Microsoft 且 Surface Hub 順利完成開機程序之後，裝置會仔細檢查可執行檔程式碼。 我們保護作業系統的方法涉及識別所有可執行檔的程式碼簽章，只允許將通過限制的程式碼載入執行階段。 此程式碼簽署方法可讓作業系統驗證作者，並且在程式碼於裝置上執行之前確認其未變更。

Surface Hub 在 Windows 應用程式控制 (先前稱為 Device Guard) 中，使用稱為使用者模式程式碼完整性 (UMCI) 的程式碼簽章功能。 原則設定是設定為僅允許符合下列其中一個需求的應用程式：

- [官方認證](https://docs.microsoft.com/windows/uwp/publish/the-app-certification-process)的通用 Windows 平台 (Microsoft Store) 應用程式。
- 使用唯一 Microsoft 生產環境根授權單位 (CA) 簽署的應用程式，只能由具有這些憑證存取權的 Microsoft 員工簽署。
- 以唯一 Surface Hub 生產環境根 CA 來簽署的應用程式。

設定檔是使用 Microsoft 生產環境根 CA 簽署，旨在避免由第三方移除或修改限制。 此時所有其他可執行檔都會在作業系統執行階段層級遭到封鎖，並防止存取處理能力。 此攻擊面降低可提供下列保護：

- 沒有舊版文件模式
- 沒有舊版指令碼引擎
- 沒有向量標記語言
- 沒有瀏覽器協助程式物件
- 沒有 ActiveX 控制項

除了透過 UMCI 封鎖未簽署或未正確簽署的程式碼以外，Surface Hub 還會使用 Windows 應用程式控制封鎖 Windows 元件，例如命令提示字元、PowerShell 和工作管理員。 這些保護措施會以安全計算設備的方式反映 Surface Hub 的重要設計功能。 如需詳細資訊，請參閱下列各項：

- [應用程式控制概觀](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [Windows Defender 應用程式控制和虛擬式程式碼完整性保護](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

### <a name="user-interface-defenses"></a>使用者介面防護

雖然開機時防護和作業系統鎖定保護措施會提供基礎安全性，但使用者介面提供額外層，可進一步降低風險。 為了防止惡意程式碼透過驅動程式到達裝置，Surface Hub 不會下載隨插即用 (PnP) 裝置的進階驅動程式。 採用基本驅動程式的裝置，例如 USB 快閃磁碟機或認證 Surface Hub 周邊 (喇叭、麥克風、相機) 可正常運作，但是像印表機等進階系統則無法正常運作。

使用者介面防護也可簡化 UI，進一步防止執行惡意軟體或程式碼。 下列 Surface Hub UI 元素加上由程式碼簽署所提供的一層核心安全性：

- **檔案總管。** Surface Hub 具有自訂「檔案總管」，可以快速存取 [音樂]、[影片]、[文件]、[圖片] 及 [下載] 資料夾，不需要將使用者公開至系統或應用程式檔案。 本機硬碟上的其他位置無法透過「檔案總管」取得。 此外，執行的許多檔案類型 (例如 .exe 和 .msi 安裝檔案) 無法執行，針對潛在惡意可執行檔提供另一層安全。

- **[開始] 和 [所有應用程式]。** Surface Hub 的 [開始] 和 [所有應用程式] 元件不會將存取權公開至透過應用程式控制封鎖的命令提示字元、PowerShell，或其他 Windows 元件。 此外，通常可以在電腦上從 [搜尋] 方塊存取的 Windows 執行功能，針對 Surface Hub 關閉。

## <a name="security-enhancements-in-surface-hub-2s"></a>Surface Hub 2S 的安全性增強功能

雖然 Surface Hub 和 Surface Hub 2S 都執行相同的作業系統軟體，但是部分 Surface Hub 2S 獨有的功能則提供額外的管理和安全性功能，可讓 IT 系統管理員執行下列工作：

- 使用 SEMM 管理 UEFI 設定
- 使用可開機 USB 復原 Hub
- 使用密碼變換管理裝置帳戶

### <a name="manage-uefi-settings-with-semm"></a>使用 SEMM 管理 UEFI 設定

UEFI 是基本硬體平台元件與作業系統之間的介面。 在 Surface Hub 上，自訂 UEFI 實作可讓您以精細的方式控制這些設定，並防止任何非 Microsoft 實體變更裝置的 UEFI 設定，或開機至抽取式磁碟磁碟機來修改或變更作業系統。

更高階的在工廠佈建程序期間，Surface Hub UEFI 已預先設定為啟用「安全開機」，已設定為僅從內部固態硬碟 (SSD) 開機，並且將 UEFI 功能表鎖定和快速鍵的存取權移除。 這樣可密封 UEFI 存取權，並確保裝置只能開機至安裝在 Surface Hub 上的 Windows 團隊版作業系統。

當透過 Microsoft Surface 企業管理模式 (SEMM) 進行管理時，IT 系統管理員可以在組織間的 Hub 裝置上部署 UEFI 設定。 這包括啟用或停用內建硬體元件、保護 UEFI 設定不受未經授權使用者變更，以及調整開機設定。

![Surface Hub UEFI 設定。](images/hub-sec-2.png)

系統管理員可以使用可下載的 [Microsoft Surface UEFI 設定程式](https://www.microsoft.com/download/details.aspx?id=46703) 來實作 SEMM 和註冊的 Surface Hub 2S 裝置。 如需詳細資訊，請參閱[使用 SEMM 和 UEFI 保護及管理 Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)。
使用憑證來加以保護，可保護設定不會受到未經授權的篡改或移除，SEMM 可管理下列元件：

- 有線 LAN
- 相機
- 藍牙
- Wi-Fi
- 佔用感應器
- 適用於 PXE 開機 的 IPv6
- 替代開機
- 開機順序鎖定
- USB 開機
- UEFI 首頁介面
    - 裝置
    - 開機
    - 日期/時間

    
### <a name="recover-hub-with-bootable-usb"></a>使用可開機 USB 復原 Hub

Surface Hub 2S 可讓系統管理員在不到 20 分鐘的時間內，使用復原映像將裝置重新安裝到原廠設定。 通常，只有在您的 Surface Hub 無法運作時，才需要這麼做。 如果您遺失 Bitlocker 金鑰或不再擁有 [設定] 應用程式的系統管理員認證，復原也相當實用。

### <a name="harden-device-account-with-password-rotation"></a>使用密碼變換管理裝置帳戶

Surface Hub 使用裝置帳戶 (又稱為「會議室帳戶」) 來驗證 Exchange、Microsoft Teams 及其他服務。 當您啟用密碼變換時，Hub 2S 每隔 7 天會自動產生新密碼，由大小寫字母、數字及特殊字元組合的 15-32 個字元組成。 由於沒有人知道密碼，因此裝置帳戶密碼變換可以有效降低相關風險，防止人為錯誤和潛在社交工程安全性攻擊。

## <a name="windows-10-enterprise-grade-security"></a>Windows 10 企業等級安全性

除了本文件中所述的 Surface Hub 特定設定和功能，Surface Hub 還使用 Windows 10 的標準安全性功能。 這些地方包括：

- **BitLocker**。 Surface Hub SSD 配備 BitLocker 來保護裝置上的資料。 其設定遵循業界標準。 如需詳細資訊，請參閱 [BitLocker 概觀](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)。
- **Windows Defender。** Windows Defender 反惡意程式碼引擎會持續在 Surface Hub 上執行，並可自動補救在 Surface Hub 上發現的威脅。 Windows Defender 引擎會自動接收更新，而且可透過 IT 系統管理員的遠端管理工具加以管理。 Windows Defender 引擎是我們深入防禦方法的最佳範例：如果惡意程式碼可以在我們的核心程式碼告示型安全性解決方案找到方向，就會在該處被捕捉。 如需詳細資訊，請參閱 [Windows Defender 應用程式控制和虛擬式程式碼完整性保護](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)。
- **隨插即用驅動程式。** 為了防止惡意程式碼透過驅動程式到達裝置，Surface Hub 不會下載 PnP 裝置的進階驅動程式。 這可讓運用基本驅動程式 (例如 USB 快閃磁碟機) 的裝置能夠正常運作，並封鎖更多進階系統 (例如印表機)。
- **信賴平台模組 2.0。** Surface Hub 擁有業界標準的離散信賴平台模組 (dTPM)，可產生和儲存密碼編譯金鑰和雜湊。 dTPM 可保護用於開機階段驗證的金鑰、BitLocker 主要金鑰、無密碼登入金鑰等等。 dTPM 符合 [FIPS 140-2 層級 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation) 憑證、美國政府電腦安全性性標準，且符合全世界使用[通用準則](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria)憑證的規範。

## <a name="wireless-security-for-surface-hub"></a>Surface Hub 的無線安全性

Surface Hub 使用 Wi-Fi Direct / Miracast 技術，並與 802.11、Wi-Fi 保護的存取 (WPA2) 以及無線保護設定 (WPS) 標準相關。 由於裝置僅支援 WPS (與 WPA2 預先共用金鑰 (PSK) 或 WPA2 Enterprise 相反)，通常與 802.11 加密相關的問題也因而被簡化。

Miracast 屬於 Wi-Fi 顯示標準的一部分，受到 Wi-Fi Direct 通訊協定的支援。 現代行動裝置的畫面分享以及共同作業功能支援這些標準。

Wi-Fi Direct 或 Wi-Fi「對等式網路」(P2P) 是由 Wi-Fi 聯盟為「臨機操作」網路所發佈的標準。 可以讓受支援的裝置直接通訊，並在不需要傳統 Wi-Fi 存取點或網際網路連線的情況下建立網路的群組。

Wi-Fi Direct 的安全性是 WPA2 使用 WPS 標準所提供。 裝置可以使用數字辨識碼、實體或虛擬按鈕，或使用近距離無線通訊的超出範圍訊息，進行驗證。 Surface Hub 預設支援按鈕和 PIN 方法。 如需詳細資訊，請參閱 [Surface Hub 如何處理 Wi-Fi Direct 的安全性問題](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)。

## <a name="learn-more"></a>深入了解

- [安全開機概觀](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-secure-boot)

- [Bitlocker 概觀](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)

- [應用程式控制概觀](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)

- [使用 SEMM 和 UEFI 保護及管理 Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-secure-with-uefi-semm)

- [Surface Hub 如何處理 Wi-Fi Direct 的安全性問題](https://docs.microsoft.com/surface-hub/surface-hub-wifi-direct)

- [Windows Defender 應用程式控制和虛擬式程式碼完整性保護](https://docs.microsoft.com/windows/security/threat-protection/device-guard/introduction-to-device-guard-virtualization-based-security-and-windows-defender-application-control)

- [適用於 IT 的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)

- [FIPS 140-2 層級 2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)

- [通用準則認證](https://docs.microsoft.com/windows/security/threat-protection/windows-platform-common-criteria)
