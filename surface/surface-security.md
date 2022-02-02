---
title: Surface 安全性概觀
description: 本文提供 Surface 裝置安全性概觀
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/01/2021
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: f711c4c34beae8e1bad34c7994d1562bb3cad08f
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338556"
---
# <a name="surface-security-overview"></a>Surface 安全性概觀

安全性研究的最新進展顯示，隨著作業系統和已連接服務內建更多保護，攻擊者正在尋找其他利用方式，而將固件當做首要目標。

現今，管理裝置固件是一種不一致的體驗，而且通常涉及協力廠商提供者，讓固件難以監控且維護很複雜。 這最終可能會限制硬體製造商偵測並推出及時更新以回應威脅的能力。

自 2015 年以來，Microsoft Surface 一直透過硬體設計的完整端對端擁有權、內部固件開發，以及整體式裝置更新和管理方法，使用統一的固件保護與裝置安全性方法。

針對 Surface，我們的整合可擴展式固件介面 (UEFI) <sup> [1](#references) </sup> 會維持內部、透過 Windows Update 定期更新，並透過 Windows Autopilot 完美部署以管理，在裝置啟動前將風險最小化，並最大化控制。 Microsoft 透過 Open Source Project [Mu](https://microsoft.github.io/mu/) GitHub ，在我們的 UEFI 中提供完整Microsoft 端點管理員。

## <a name="microsoft-designed-and-built-components"></a>Microsoft 設計及建建的元件

從晶片到雲端的每一層 Surface 都是由 Microsoft 開發和維護，無論您在何處完成工作，都提供終極控制權、主動式保護，讓您安心工作。 Surface 裝置會提供 Microsoft 提供的最強安全性通訊協定，並啟用簡化的管理，降低 IT 複雜度，協助使用者專注于工作。

Surface 利用獨立的防禦子元件分層，透過深入防禦的方法來推動安全性。 從晶片到雲端，或 UEFI，確保 AI 支援 Microsoft Defender for Endpoint 的根信任，能夠防範、偵測、調查及回應進一步威脅，Surface 會強制執行 Microsoft 內建比閃電式強的位置。

<br/>

| 功能 | 描述 | 深入了解 |
| ------- | ----------- | ---------- |
| Microsoft 建建 UEFI            | 設定裝置並引導裝置Windows 10<br>控制裝置和裝置Windows 10啟動，然後提供作業系統的固件執行時間服務。 透過 SEMM on-prem 管理和 DFCI 雲端式管理，透過 Microsoft 端點管理員 | [管理 Surface UEFI 設定](manage-surface-uefi-settings.md)                                                                        |
| 實體 TPM 2.0                | 受信任的平臺模組 - 專為透過整合式加密金鑰保護硬體設計的專用微控制器。<br>加密及儲存 BitLocker、 (、Windows Hello、AD 認證、) <br>PCR - 平臺組組註冊，可保護測量和相關度量，以偵測先前配置的變更  | [信賴平台模組技術概觀](/windows/security/information-protection/tpm/trusted-platform-module-overview)                 |
| Windows Hello 企業版      | 在 PC 和行動裝置上以強大的雙因素驗證取代密碼。 此生物識別驗證封裝含系結到裝置並使用生物識別或 PIN 的新使用者認證類型。                                                                                                                   | [商務Windows Hello運作方式 - Microsoft 365安全性](/windows/security/identity-protection/hello-for-business/hello-how-it-works) |
| 整合加密           | BitLocker 已啟用整合式加密功能，可保護及加密您的資料，Windows Hello啟用無密碼登入，並結合實體 TPM 和 UEFI。                                                                                                                                                                 | [BitLocker (Windows 10) - Microsoft 365安全性](/windows/security/information-protection/bitlocker/bitlocker-overview)                     |
| 適用於端點的 Microsoft Defender | 提供專為協助商業網路防範、偵測、調查及回應進一步威脅而設計的企業端點安全性平臺。                                                                                                                                                                               | [適用於端點的 Microsoft Defender](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)                 |

## <a name="factory-level-security-protocols-and-inspection"></a>工廠層級安全性通訊協定與檢查

從固件到作業系統，以及最終組裝前硬體的每一個元件，Surface 裝置在我們的實體安全開發和製造設施中，都安全無恙地受到供應鏈攻擊。

根據定義，安全的供應鏈會提供符合品質、績效及營運目標的成品。 簡單來說，安全的供應鏈可確保所有元件都是正版，而且沒有未經授權的或惡意的操控或破壞。 我們在高度安全的工廠中製造裝置，從 UEFI 固件到作業系統等所有專案都直接來自 Microsoft。 沒有任何協力廠商BIOS 廠商參與。 這是我們如何防範 Surface 產品供應鏈攻擊的一個強大部分。 我們已移除任何未使用的程式碼，包括裝置不需要的系統管理模式 SMM 函數，來減少 UEFI 中的 Surface 攻擊。

保護設施不受外部網際網路攻擊、入侵和其他威脅，需要跨重要領域持續投資，包括：

- 在最終的組裝位置對所有元件進行嚴格的檢查和測試。
- 維護工廠中的高等級實體安全性。
- 僅使用 Microsoft 開發&維護的固件、驅動程式和作業系統。
- 直接傳送給 Microsoft 轉銷商的 Surface 裝置，確保物流和信任的電信業者傳遞。

離開工廠後，Surface 商務版裝置會透過更新Windows整個生命週期受到保護。

## <a name="advanced-windows-security-features"></a>進Windows安全性功能

許可權攻擊升級是惡意參與者的最佳朋友，而且通常會以儲存在記憶體中的敏感性資訊為目標。 這類攻擊可能會將次要使用者模式入侵轉換為作業系統與裝置的完整威脅。 為了防範這類攻擊，Microsoft 已開發虛擬化式安全性 (VBS) 和受 Hypervisor 保護的代碼完整性 (HVCI，也稱為記憶體完整性) 。 VBS 和 HVCI 使用虛擬化等硬體功能，在隔離環境中執行敏感性安全性作業，以提供更好的保護，防範常見且複雜的惡意攻擊。

Surface 會提供這些Windows功能，讓功能更加強大，讓客戶擁有內建且預設開啟的更強大的安全性。

## <a name="virtualization-based-security"></a>虛擬式安全性

虛擬化式安全性或 VBS 會使用硬體虛擬化功能來建立和隔離一般作業系統的安全記憶體區域。 Windows此「虛擬安全模式」來託管數種安全性解決方案，為這些解決方案提供大幅增強的保護，避免作業系統中的安全性漏洞，並防止使用惡意攻擊來破壞保護。

### <a name="hypervisor-enforced-code-integrity-hvci"></a>Hypervisor-Enforced程式碼完整性 (HVCI) 

HVCI 使用 VBS 大幅強化程式碼完整性原則強制執行。 核模式代碼完整性會先檢查所有核心模式驅動程式和二進位檔案，然後再啟動，並防止未簽名的驅動程式或系統檔案載入至系統記憶體。 如下圖所示，HVCI 在隔離的執行環境中執行，並依據核心簽署原則驗證核心程式代碼的完整性。

在下列 Surface 裝置中，VBS 和 HVCI 都開箱啟用：

- Surface Pro 8
- Surface Laptop工作室
- Surface Go 3
- Surface Laptop 4
- Surface Pro 7+
- Surface Book 3，
- Surface Laptop Go
- Surface Pro X

## <a name="secure-boot-and-boot-guard"></a>保護開機和開機防護

Surface 裝置的根信任目錄會檢查簽章和度量，以確保每個階段都安全且真實，然後再允許下一個啟動階段繼續進行。 由 UEFI 和 TPM 2.0 啟用，Secure Boot 可確保只有已簽署、測量及正確實用的代碼才能在 Surface 裝置上執行。

如圖 2 所示，從按電源按鈕到執行作業系統，每個階段都檢查了固件的完整性。

> [!div class="mx-imgBorder"]
> [ ![ 圖 1.Surface 裝置安全啟動。 ](images/secboot.png)](images/secboot.png#lightbox) 
 *圖 1.Surface 裝置安全啟動*

<br/>

| 步驟  | 安全啟動階段 |
| ----- | ----------------- |
| **1** | 每次從 TPM 所提供的根信任按電源按鈕時，安全性都會立即具現化。 當裝置第一次上電時，系統會執行一系列安全性檢查，以確保裝置固件未遭到竄改或損壞。 |
| **2** | 啟用時，SoC 會使用測試組廠商金鑰，使用 Intel 型裝置上的驗證程式代碼模組 (ACM)  (驗證並啟動) 。                                                                              |
| **3** | ACM 在載入前會測量 UEFI 程式碼，並將它與 TPM 平臺組組註冊器 [PCR] 中的已知度量單位進行比較，以確保 UEFI 程式碼沒有變更。                                                                |
| **4** | 在允許執行 UEFI 之前，Boot Guard 會檢查 UEFI 是否以 Surface OEM 金鑰簽署。 最初檢查的 UEFI 模組為 SEC 安全性，以及圖表中顯示的"一節之前 EFI"。                                                |
| **5** | 在載入驅動程式執行環境 DXE 模組時，一節會檢查該驅動程式執行環境上的 Surface 簽名。 DXE 模組包含啟動裝置選取階段。                                                                          |
| **6** | 選取啟動裝置後，UEFI 會先讀取啟動裝置，並檢查作業系統開機載入程式簽名，再允許執行。                                                                                                             |
| **7** | 作業系統接著在主要元件上檢查其簽名，以啟動作業系統。

### <a name="malware-protection"></a>惡意程式防護

為了協助保護您的裝置不受惡意軟體攻擊，Surface 啟用安全啟動，以確保已啟動正版 Windows 10，且該固件與出廠時一樣真實。

Surface 裝置上的 SoC 有一個與其他核心分開的安全性處理器。 當您第一次啟動 Surface 裝置時，只有安全性處理器會啟動，才能載入任何其他裝置。 「安全開機」是用來驗證開機程序的元件，包括驅動程式和作業系統，根據有效和已知的簽章進行驗證。 這可協助防止隱藏在正常使用者體驗中，來自執行惡意程式碼的複製或修改過系統的攻擊。 如需詳細資訊，請參閱[安全開機概觀](/windows-hardware/design/device-experiences/oem-secure-boot)。

一旦作業系統驗證為來自 Microsoft，您的 Surface 裝置成功完成啟動程式後，裝置會仔細檢查可執行程式碼。 我們保護作業系統的方法涉及識別所有可執行檔的程式碼簽章，只允許將通過限制的程式碼載入執行階段。 此程式碼簽署方法可讓作業系統驗證作者，並且在程式碼於裝置上執行之前確認其未變更。

## <a name="drtm-protection-in-amd-devices"></a>在AMD 裝置中的 DRTM 保護

包含AMD 處理器的 Surface 裝置以同等的方式執行安全啟動。 Surface Laptop 4 使用AMD Ryzen Microsoft Surface Edition 處理器使用動態根信任測量和 DRTM (保護) 。DRTM 會控制所有 CPU，強制沿著測量路徑執行，並重新建立各個階段的信任，以驗證系統固件/軟體的完整性。 提早轉換至此信任狀態可針對啟動階段的潛在攻擊提供進一步防護。

DRTM 可確保使用 TSME 資料總系統記憶體加密加密 (測量) 。 設定 TSME 後，除非系統重設，否則無法清除。 每一次重設的新加密金鑰可確保安全性的一次使用加密。

系統管理模式的執行時間 (SMM) 最高層級執行，如果 SMM 程式碼發生任何問題，則可能會有風險。 Surface Laptop 4 WITH AMD Ryzen 會截取系統管理中斷 (SMI) ，將 SMM 程式碼的執行分派到較低層級的 (使用者) 以保護系統不受無效程式碼和資料存取。 SMM 保護會使用硬體保護來限制可存取的代碼、資料和系統資源，進一步強制執行防範不慎或惡意事件的保護。

Surface Laptop Ryzen 的 4 版支援[NIST 800-193 平臺](https://nvlpubs.nist.gov/nistpubs/SpecialPublications/NIST.SP.800-193.pdf)韌韌復原指導方針，以及強大的韌韌更新支援。 開機固件的彈性更新機制使用 A-B 復原機制，在啟動期間如果啟動順序偵測到已損壞的固件複本，該機制會提供自動復原至備份的固件複本。

若要深入瞭解 DRTM 和 SMM，請參閱系統防護Windows Defender[如何協助保護Windows 10](/windows/security/threat-protection/windows-defender-system-guard/how-hardware-based-root-of-trust-helps-protect-windows)。

## <a name="remote-device-management-control"></a>遠端裝置管理控制項

IT 系統管理員可以遠端系統管理 Surface 裝置，而不需要實際觸碰每個裝置。 Microsoft 端點管理員 Intune 和 Windows Autopilot 功能，可讓您從 Azure Cloud 完全遠端系統管理 Surface 裝置，在啟動時提供完整配置的裝置給使用者。 抹掉和淘汰功能可以讓 IT 輕鬆為新的遠端使用者重新調整裝置用途，並抹掉遭竊的裝置。 這可讓您在 Surface 裝置遺失或被盜時，快速且安全地回應功能，讓您遠端移除所有公司資料，並重新將 Surface 重新做為全新的裝置。

<br/>

| 功能 | 描述 | 深入了解 |
| ------- | ----------- | ---------- |
| DCFI (裝置固件組)  | 使用零接觸式裝置資源配置，提供雲端規模的遠端固件管理。 Microsoft 自己的 UEFI 可讓更強大的 DCFI 實現，讓組織停用硬體元素，以及使用 Intune 遠端鎖定 UEFI。 ¹                                                                                                                                                                          | [Surface UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)<br> <br>[管理 Surface UEFI 設定](manage-surface-uefi-settings.md)                                          |
| SEMM (Surface Enterprise管理模式)       | 跨內部部署、混合式和雲端環境啟用集中式企業 UEFI 固件設定。¹                                                                                                                                                                                                                                                                                           | [Surface 企業管理模式](surface-enterprise-management-mode.md)                                                                                                                                                       |
| 商務用 Windows Update                    | 讓 IT 系統管理員將 Windows 10 裝置直接連接到更新服務，以最新的安全性防護、Windows 功能和 Surface Windows保持最新狀態。 您可以使用群組原則或 MDM 解決方案 ，例如 Microsoft Intune 設定 Windows 商務用更新設定，以控制 Surface 裝置更新的方式和時間。 | [商務用 Windows Update](/windows/deployment/update/waas-manage-updates-wufb)<br> <br>[管理和部署 Surface 驅動程式與韌體更新](manage-surface-driver-and-firmware-updates.md) |

## <a name="references"></a>參考

1. Surface Go 和 Surface Go 2 使用協力廠商 UEFI，且不支援 DFCI。 DFCI 目前適用于 Surface Laptop SE、Surface Laptop Studio、Surface Pro 8、Surface Go 3、Surface Laptop 4、Surface Laptop Go、Surface Book 3、Surface Laptop 3、Surface Pro 7+、Surface Pro 7 和 Surface Pro X。 

## <a name="learn-more"></a>深入了解

- [根據預設，新的 Surface 電腦 (VBS) 虛擬化式安全性，讓客戶能夠安全地執行更多工作](https://www.microsoft.com/security/blog/2021/01/11/new-surface-pcs-enable-virtualization-based-security-vbs-by-default-to-empower-customers-to-do-more-securely/)
- [研究強調 Surface 固件保護的關鍵性角色](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/study-highlights-critical-role-of-surface-firmware-protection/ba-p/2245244)
- [增強 Microsoft Surface 和 Microsoft Surface 和 Microsoft 365](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/enhancing-security-and-compliance-with-microsoft-surface-and/ba-p/2283062)
- [管理 Surface UEFI 設定](manage-surface-uefi-settings.md)
- [Surface UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)
- [Project Mu](https://microsoft.github.io/mu/)
