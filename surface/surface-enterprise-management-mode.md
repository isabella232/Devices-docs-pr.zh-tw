---
title: 'Surface Enterprise管理模式 (Surface) '
description: 瞭解 Surface 裝置與 Surface UEFI 的這項功能如何協助保護及管理貴組織的固件設定。
keywords: uefi， configure， firmware， secure， semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
audience: itpro
ms.date: 12/08/2021
ms.openlocfilehash: 8b9a39d412efeff30a7f864d5c38b6135dca4b9b
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338096"
---
# <a name="microsoft-surface-enterprise-management-mode"></a>Microsoft Surface Enterprise管理模式

Microsoft Surface Enterprise管理模式 (SEMM) 是 Surface 裝置與 Surface Unified Unified 可擴展的固件介面 (UEFI) 。 您可以使用 SEMM：

- 保護和管理貴組織的固件設定。
- 準備 UEFI 設定設定，並安裝在 Surface 裝置上。

SEMM 也會使用憑證來保護組組，避免未經授權的竄改或移除。 若要將 2S Surface Hub 2S Windows 10 專業版或Windows Enterprise，需要 SEMM。

## <a name="supported-devices"></a>支援的裝置

SEMM 僅適用于具有 Surface UEFI 固件的裝置，包括： 

- Surface Pro只 (8 個商業 SKUS) 
- Surface Pro 4之後 (所有 SKUs) 
- Surface Pro X (所有 SKUs) 
- Surface Laptop SE (所有 SKUs) 
- Surface Laptop Studio (只供應商業 SKUs)  
- Surface Hub 2S
- Surface Laptop只 (4 個商業 SKUS) 
- Surface Laptop 3 (Intel 處理器) 
- Surface Laptop Go 
- Surface Book (代) 
- Surface Go， Surface Go 2
- Surface Go 3 (商務 SKUs) 
- Surface Studio 

>[!TIP]
> 商業 SKUs (或 Surface 商務版) Windows 10 專業版/Enterprise 或 Windows 11 專業版/Enterprise;消費者 SKUs Windows 10/Windows 11 家用版。 若要深入瞭解，請參閱 [查看系統資訊](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00)。 


## <a name="getting-started"></a>開始使用 

當 Surface 裝置是由 SEMM 所配置，且使用 SEMM 憑證進行保護時，這些裝置會被視為已** 註冊于 SEMM。 移除 SEMM 憑證，且將 UEFI 設定控制權退還給裝置使用者時，Surface 裝置在 SEMM 中視為未註冊。* *

您可以使用兩種系統管理選項來管理 SEMM 並註冊 Surface 裝置：

- 本文說明 SEMM 獨立工具 Microsoft Surface UEFI Configurator。

- 與 Microsoft Endpoint Configuration Manager 整合。 有關資訊，請參閱[使用Microsoft Endpoint Configuration Manager SEMM 管理裝置](use-system-center-configuration-manager-to-manage-devices-with-semm.md)。

## <a name="microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI Configurator

SEMM 的主要工作區是 Microsoft Surface UEFI Configurator，如圖 1 所示。

您可以使用 Microsoft Surface UEFI Configurator：

- 建立Windows安裝程式 (.msi) 套件。
- 使用 WinPE 影像在 Surface 裝置上註冊、設定及取消註冊 SEMM。

這些套件包含指定 UEFI 設定的設定檔。 SEMM 套件也包含已安裝並儲存在固件中的憑證，用於驗證組組檔案的簽名，然後再套用 UEFI 設定。

>[!TIP]
>現在，您可以使用 Surface UEFI Configurator 和 SEMM 來管理 Surface Dock 2 上的埠。 若要深入瞭解，請參閱使用 [SEMM 保護 Surface Dock 2 埠](secure-surface-dock-ports-semm.md)。

![Microsoft Surface UEFI Configurator。](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*圖 1。 Microsoft Surface UEFI Configurator*

您可以在三種模式中使用 Microsoft Surface UEFI Configurator 工具：

- [Surface UEFI 組組套件](#configuration-package)。 使用此模式建立 Surface UEFI 設定套件，以在 SEMM 中註冊 Surface 裝置，以及設定已註冊的裝置上的 UEFI 設定。
- [Surface UEFI 重設套件](#reset-package)。 使用此模式從 SEMM 取消註冊 Surface 裝置。
- [Surface UEFI 修復要求](#recovery-request)。 使用此模式回應復原要求，從 SEMM 取消註冊 Surface 裝置，而重設套件作業失敗。

### <a name="download-microsoft-surface-uefi-configurator"></a>下載 Microsoft Surface UEFI Configurator

您可以從 Microsoft 下載中心的 SURFACE IT 工具頁面下載 Microsoft Surface [](https://www.microsoft.com/download/details.aspx?id=46703) UEFI 配置程式。

- 針對 Intel/AMD 裝置，請 ** 下載：SurfaceUEFI_Configurator_v2.94.139.0_x64.msi**
- 針對 ARM 裝置，請下載： **SurfaceUEFI_Configurator_v2.94.139.0_x86.msi。**

### <a name="configuration-package"></a>組組套件

Surface UEFI 組組套件是在 Surface 裝置上執行和管理 SEMM 的主要機制。 這些套件包含組設定檔和憑證檔案，如圖 2 所示。 設定檔包含在 Microsoft Surface UEFI Configurationator 中建立套件時指定的 UEFI 設定。 當組組套件第一次在尚未在 SEMM 註冊的 Surface 裝置上執行時，它會在裝置的固件中規定憑證檔案，並註冊 SEMM 中的裝置。 在 SEMM 中註冊裝置時，以及憑證儲存及註冊完成之前，系統會提示您提供 SEMM 憑證指紋的最後兩位數以確認作業。 此確認要求使用者在註冊期間實際出席裝置，才能執行確認。

![使用憑證保護 SEMM 組組套件。](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*圖 2. 使用憑證保護 SEMM 組組套件*

有關 SEMM 憑證需求的資訊，請參閱本文稍後Enterprise [Surface Enterprise管理模式憑證](#surface-enterprise-management-mode-certificate-requirements)需求>一節。

>[!TIP]
>您可以選擇使用 SEMM 要求 UEFI 密碼。 如果您這麼做，您必須輸入密碼才能查看 Surface UEFI **** 的安全性、**** 裝置、**啟動Enterprise****管理**頁面。

在 SEMM 中註冊裝置之後，系統即會讀取組組檔案，且檔案中指定的設定會適用于 UEFI。 當您在已在 SEMM 註冊的裝置上執行組組套件時，設定檔的簽名會針對儲存在裝置固件中的憑證進行檢查。 如果簽章不相符，系統不會對裝置進行任何變更。

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>在 Surface UEFI 中啟用或停用具有 SEMM 的裝置

下列清單顯示您可以在 SEMM 中管理的所有可用裝置：

- 固定 USB 埠
- 板載音訊
- 數位圖形處理單元
- 類型保護蓋
- Micro SD 卡片
- 前方相機
- 後方相機
- 適用于 (相機Windows Hello) 
- 藍牙只
- 無線網路和藍牙
- LTE (長期) 

 >[!NOTE]
>在 UEFI 裝置頁面上，內建裝置可能會根據您的裝置或公司環境而不同。 例如，X 版不支援 UEFI 裝置Surface Pro頁面;LTE 只會顯示在配備 LTE 的裝置上。

### <a name="configure-advanced-settings-with-semm"></a>使用 SEMM 設定進位設定

**表 1. 進階設定**

| 設定                            | 描述                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 適用於 PXE 開機 的 IPv6                  | 可讓您管理 PXE 啟動的 IPv6 支援。 如果您沒有設定此設定，PXE 啟動的 IPv6 支援會停用。                                                                               |
| 替代開機                     | 可讓您在啟動期間同步選取降低音量按鈕和 Power 按鈕，管理使用備用啟動順序以直接引導至 USB 或乙太網路裝置。 如果您沒有設定此設定，系統即會啟用備用啟動。 |
| 開機順序鎖定                    | 可讓您鎖定啟動順序以防止變更。 如果您沒有設定此設定，則啟動順序鎖定會停用。                                                                                                        |
| USB 開機                           | 可讓您管理啟動至 USB 裝置。 如果您沒有設定此設定，即會啟用 USB 啟動。                                                                                                                 |
| 網路堆疊                      | 可讓您管理網路堆疊啟動設定。 如果您沒有設定此設定，則管理網路堆疊啟動設定的能力會停用。                                                                                                           |
| 自動上電                      | 可讓您管理自動開機設定。 如果您沒有設定此設定，即會啟用自動電源。                                                                                                        |
| 同時使用 SMT (執行緒)  | 可讓您管理 SMT 的同步多執行緒 (，) 啟用或停用超執行緒。 如果您沒有設定此設定，SMT 會啟用。                                                  |
|啟用電池限制| 可讓您管理電池限制功能。 如果您沒有設定此設定，則啟用電池限制 |
| 安全性                           | 顯示 Surface UEFI **安全性** 頁面。 如果您沒有設定此設定，系統會顯示安全性頁面。                                                                                                                 |
| 裝置                            | 顯示 Surface UEFI **裝置** 頁面。 如果您沒有設定此設定，會顯示裝置頁面。                                                                                                                     |
| 開機                               | 顯示 Surface UEFI **啟動** 頁面。 如果您沒有設定此設定，系統會顯示啟動頁面。                                                                                                                                                            |
| DateTime                           | 顯示 Surface UEFI **DateTime** 頁面。 如果您沒有設定此設定，則會顯示 DateTime 頁面。                                                                                                                |
| EnableOSMigration                          | 可讓您將 Surface Hub 2 從 Windows 10 團隊版 Windows 10 專業版 Enterprise。 如果您沒有設定此設定，Surface Hub 2 個裝置只能執行 Windows 10 團隊版 OS。 注意：Windows 10 團隊版和 Windows 10 專業版/Enterprise 2 無法Surface Hub啟動。                                                                                                           |

>[!TIP]
>當您建立 SEMM 組組套件時，成功頁面上會顯示兩個字元，**** 如圖 3 所示。

![憑證指紋顯示。](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*圖 3. 在成功頁面上顯示憑證指紋的最後兩個字元*

這些字元是憑證指紋的最後兩個字元，應該寫下或錄製。 需要字元才能確認在 Surface 裝置上註冊 SEMM，如圖 4 所示。

![SEMM 中的註冊確認。](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*圖 4. 使用 SEMM 憑證指紋在 SEMM 中註冊確認*

>[!TIP]
>具有憑證檔案 (.pfx) 的系統管理員隨時都可以在 CertMgr 中開啟 .pfx 檔案來讀取指紋。 若要使用 CertMgr 來查看指紋：
>
>1. 選取並按住 (或以滑鼠右) .pfx 檔案，然後選取 [ **開啟**。
>2. 在流覽窗格中展開資料夾。
>3. 選取 **憑證**。
>4. 在主窗格中，選取並按住 (或以滑鼠右鍵) 您的憑證，然後選取 [ **開啟**。
>5. Select the **Details** tab.
>6. 在顯示**下拉式功能表****中，必須**選取所有或**僅**屬性。
>7. 選取 **指紋欄位** 。

若要在 SEMM 中註冊 Surface 裝置，或從組組套件套用 UEFI 組.msi，在預定的 Surface 裝置上執行具有系統管理許可權的 .msi 檔案。 您可以使用應用程式部署或作業系統部署技術，例如 Microsoft Endpoint Configuration Manager[或 Microsoft 部署工具組](/mem/configmgr/mdt)。[ ](/mem/configmgr) 當您在 SEMM 中註冊裝置時，您必須實際出席，以確認裝置上的註冊。 當您將組配置適用于已在 SEMM 中註冊的裝置時，不需要使用者互動。

若要逐步瞭解如何在 SEMM 中註冊 Surface 裝置，或在 SEMM 中適用 Surface UEFI 設定，請參閱使用 [SEMM](enroll-and-configure-surface-devices-with-semm.md)註冊及設定 Surface 裝置。

### <a name="reset-package"></a>重設套件

Surface UEFI 重設套件只會用來執行一項工作 ，從 SEMM 取消註冊 Surface 裝置。 重設套件包含簽署指示，以從裝置固件移除 SEMM 憑證，以及將 UEFI 設定重設為出廠預設設定。 就像 Surface UEFI 設定套件一樣，重設套件必須以 Surface 裝置上所配置的相同 SEMM 憑證簽署。 當您建立 SEMM 重設套件時，您必須提供要重設的 Surface 裝置序號。 SEMM 重設套件並非通用套件，而是特定于一個裝置。

### <a name="recovery-request"></a>復原要求

在某些情況下，可能無法使用 Surface UEFI 重設套件。  (例如，如果 Windows 在 Surface 裝置上無法使用。) 在這些情況下，您可以使用修復要求作業，透過 Surface UEFI (的**Enterprise**) 管理頁面，從 SEMM 取消捲動 Surface 裝置。

> [!div class="mx-imgBorder"]
> ![啟動 SEMM 復原要求。](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*圖 5. 在管理頁面上啟動 SEMM Enterprise要求*

當您使用系統管理頁面上Enterprise在**** Surface 裝置上重設 SEMM 時，系統將會提供重設要求。 此重設要求可以儲存為檔案至 USB 磁碟機、複製為文字，或以 QR 程式碼與行動裝置一起讀取，以輕鬆以電子郵件或訊息進行。 使用 Microsoft Surface UEFI 設定程式重設要求選項來載入重設要求檔案，或輸入重設要求文字或 QR 程式碼。 Microsoft Surface UEFI Configurator 會產生可在 Surface 裝置上輸入的驗證碼。 如果您在 Surface 裝置上輸入程式碼，然後 **選取重新開機，** 則裝置會從 SEMM 取消註冊。

>[!NOTE]
>重設要求會在建立後的兩小時到期。

若要逐步瞭解如何從 SEMM 取消註冊 Surface 裝置，請參閱從 SEMM 取消卷起 [Surface 裝置](unenroll-surface-devices-from-semm.md)。

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Surface Enterprise管理模式憑證需求

當您將 SEMM 與 Microsoft Surface UEFI 設定器一起使用，並想要適用 UEFI 設定時，需要憑證才能驗證組組檔案的簽名。 此憑證可確保在裝置註冊 SEMM 之後，只有使用核准憑證所建立套件才能用來修改 UEFI 設定。

>[!NOTE]
>若要在註冊的 Surface 裝置上對 SEMM 或 Surface UEFI 設定進行任何修改，必須提供 SEMM 憑證。 如果 SEMM 憑證損壞或遺失，則無法移除或重設 SEMM。 使用適當的備份及復原解決方案管理 SEMM 憑證

使用 Microsoft Surface UEFI Configurator 工具所建立套件會以憑證簽署。 此憑證可確保在裝置註冊 SEMM 之後，只有使用核准憑證所建立套件才能用來修改 UEFI 的設定。

### <a name="recommended-certificate-settings"></a>建議的憑證設定

SEMM 憑證建議使用下列設定：

- **金鑰演算法** – RSA
- **金鑰長度** – 2048
- **雜湊演算法** – SHA-256
- **類型** - SSL Server 驗證
- **金鑰使用量** – 數位簽章、金鑰加密
- **提供者** – Microsoft 增強版 RSA 和 AES 加密提供者
- **到期日** – 自建立憑證起 15 個月
- **金鑰匯出政策** – 可匯出

此外，建議在兩層公用金鑰基礎結構 (PKI) 架構中驗證 SEMM 憑證，其中中間憑證授權單位 (CA) 專門負責 SEMM，啟用憑證撤銷。 有關雙層級 PKI 組的資訊，請參閱測試實驗室指南 [：在 PKI 階層中部署 AD CS Two-Tier CS](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831348(v=ws.11))。

### <a name="self-signed-certificate"></a>自我簽署憑證

您可以使用下列範例 PowerShell 腳本來建立自我簽署憑證，以用於概念證明案例。
若要使用此腳本，請複製下列文字至 記事本，然後將檔案儲存為 PowerShell 腳本 (.ps1) 。

> [!NOTE]
> 此腳本會建立具有 密碼的憑證 `12345678` 。 此腳本產生的憑證不建議用於生產環境。
  
```powershell
if (-not (Test-Path "Demo Certificate"))  { New-Item -ItemType Directory -Force -Path "Demo Certificate" }
if (Test-Path "Demo Certificate\TempOwner.pfx") { Remove-Item "Demo Certificate\TempOwner.pfx" }

# Generate the Ownership private signing key with password 12345678
$pw = ConvertTo-SecureString "12345678" -AsPlainText -Force

$TestUefiV2 = New-SelfSignedCertificate `
  -Subject "CN=Surface Demo Kit, O=Contoso Corporation, C=US" `
  -Type SSLServerAuthentication `
  -HashAlgorithm sha256 `
  -KeyAlgorithm RSA `
  -KeyLength 2048 `
  -KeyUsage KeyEncipherment `
  -KeyUsageProperty All `
  -Provider "Microsoft Enhanced RSA and AES Cryptographic Provider" `
  -NotAfter (Get-Date).AddYears(25) `
  -TextExtension @("2.5.29.37={text}1.2.840.113549.1.1.1") `
  -KeyExportPolicy Exportable

$TestUefiV2 | Export-PfxCertificate -Password $pw -FilePath "Demo Certificate\TempOwner.pfx"
```

>[!IMPORTANT]
>如要與 SEMM 和 Microsoft Surface UEFI Configurator 一起使用，憑證必須以私密金鑰和密碼保護方式匯出。 Microsoft Surface UEFI Configurator 會提示您選取 SEMM 憑證檔案 (.pfx) 和憑證密碼。

若要建立自我簽署的憑證：

1. 在 C：磁碟機上，建立要儲存腳本的資料夾;例如，C：\SEMM。
2. 將範例腳本複製到記事本 (或相等的文字編輯器) ，然後將檔案儲存為 PowerShell 腳本 (.ps1) 。
3. 使用系統管理員認證來登錄您的電腦，然後開啟提升的 PowerShell 會話。
4. 請確定您的許可權已設定為允許腳本執行。 根據預設，除非您修改執行策略，否則腳本會禁止執行。 若要深入瞭解，請參閱 [關於執行策略](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。
5. 在命令提示符中，輸入腳本的完整路徑，然後按 **Enter**。 腳本會建立名為 TempOwner.pfx 的示範憑證。

或者，您可以使用 PowerShell 建立自己的自我簽署憑證。 詳細資訊，請參閱 [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate)。

>[!NOTE]
>對於在 PKI 基礎結構中使用離線根目錄的組織，Microsoft Surface UEFI Configurator 必須在連線至根 CA 的環境中執行，以驗證 SEMM 憑證。 Microsoft Surface UEFI Configurator 產生的套件可以以檔案方式傳輸，以便以可移除的儲存空間 ，例如 USB 記憶棒等，在離線網路環境外傳輸。

### <a name="managing-certificates-faq"></a>管理憑證常見問題

建議的最小 *長度* 為 15 個月。 您可以使用在 15 個月內到期的憑證，或使用超過 15 個月的憑證。

>[!NOTE]
>憑證到期時，它不會自動續約。

**過期的憑證會影響 SEMM 註冊的裝置功能嗎？**<br><br>
否，憑證只會影響 SEMM 中的 IT 系統管理員管理工作，且在到期時不會影響裝置功能。

**需要在所有擁有 SEMM 套件和憑證的機器上更新嗎？**<br><br>
如果您希望 SEMM 重設或復原能夠生效，憑證必須有效且不會過期。

**可以針對我們訂購的每個曲面建立大量重設套件嗎？ 可以建立重設環境中所有電腦的能力嗎？**<br><br>
為特定裝置類型建立設定套件的 PowerShell 範例也可以用來建立與序列值無關的重設套件。 如果憑證仍然有效，您可以使用 PowerShell 建立重設套件來重設 SEMM。

## <a name="version-history"></a>版本歷程記錄

### <a name="version-2941390"></a>版本 2.94.139.0

此版本的 SEMM 包括：

- 支援 Surface Laptop Studio、Surface Pro 8 和 Surface Go 3

### <a name="version-2831390"></a>版本 2.83.139.0

此版本的 SEMM 包括：

- 支援 Surface Laptop 4
- 支援 7 的同步多執行緒Surface Pro選項
- 移除過時的 SEMM 設定  
- 改良 MSI 簽名

### <a name="version-2791390"></a>版本 2.79.139.0

此版本的 SEMM 包括：

- 支援 Surface Pro 7+。
- 使用者體驗改良功能。

### <a name="version-2781390"></a>版本 2.78.139.0

此版本的 SEMM 包括：

- 支援使用 Surface Laptop X 和 Surface Pro X。
- 新版本版本的通知。
- 建立自訂套件以變更擁有權的能力。
- 錯誤修正。

### <a name="version-2731360"></a>版本 2.73.136.0

此版本的 SEMM 包括：

- 使用 SEMM 在 Surface Hub2S 上停用音訊的能力。
- 支援適用于 Dock Surface Pro X 的 X。
- 支援 Dock 2 相關作業的 UEFI Manager。
- Surface Go 重設套件錯誤修正程式。
- 支援將 2 Surface Hub從作業系統Windows 10 團隊版移Windows 10 專業版或Enterprise。

### <a name="version-2711390"></a>版本 2.71.139.0

此版本的 SEMM 新增了 Surface Dock 2 管理功能的支援，Surface Book 3、Surface Laptop 3 和 Surface Pro 7。 其中包含：

- 能夠啟用音訊 (鎖定/解除鎖定) 乙太網路和 USB 埠。
- 為已驗證和未經驗證的主機建立固定套件的能力。

### <a name="version-2701300"></a>版本 2.70.130.0

此版本的 SEMM 包括：

- 支援 Surface Go 2。
- 支援 Surface Book 3。
- 錯誤修正。

### <a name="version-2591390"></a>版本 2.59.139.0

此版本的 SEMM 包括：

- 支援 Surface Pro 7 Surface Pro X 和 Surface Laptop 3 13.5" 和 15" 型號的 Intel 處理器。
    >[!NOTE]
    >Surface Laptop 3 個 15" 的AMD 處理器不受支援。
- 支援 Power 喚醒功能。

### <a name="version-2541390"></a>版本 2.54.139.0

此版本的 SEMM 包括：

- 支援 Surface Hub 2S。
- 錯誤修正。

### <a name="version-2431360"></a>版本 2.43.136.0

此版本的 SEMM 包括：

- 支援啟用/停用同時多執行緒。
- 針對部分裝置，針對無線網路和藍牙個別選項。
- 已移除電池Surface Studio。

### <a name="version-2261360"></a>版本 2.26.136.0

此版本的 SEMM 包括：

- 支援 Surface Studio 2。
- 電池限制功能。

### <a name="version-2211360"></a>版本 2.21.136.0

此版本的 SEMM 包括：

- 支援 6 Surface Pro 6。
- 支援 Surface Laptop 2。

### <a name="version-2141360"></a>版本 2.14.136.0

此版本的 SEMM 包括：

- 支援 Surface Go。

### <a name="version-291360"></a>版本 2.9.136.0

此版本的 SEMM 包括：

- 支援 Surface Book 2。
- 支援 LTE Surface Pro LTE。
- 協助工具改良功能。

### <a name="version-10740"></a>版本 1.0.74.0

此版本的 SEMM 包括：

- 支援Surface Laptop。
- 支援Surface Pro。
- 錯誤修正和一般改良功能。

## <a name="related-topics"></a>相關主題

- [使用 SEMM 註冊及設定 Surface 裝置](enroll-and-configure-surface-devices-with-semm.md)
- [從 SEMM 取消 Surface 裝置的註冊](unenroll-surface-devices-from-semm.md)
- [使用 SEMM 保護 Surface Dock 2 連接埠的安全](secure-surface-dock-ports-semm.md)
