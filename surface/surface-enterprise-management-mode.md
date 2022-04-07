---
title: Surface 企業管理模式 (SEMM)
description: 瞭解 Surface 裝置搭配 Surface UEFI 的這項功能如何協助您保護及管理組織內的韌體設定。
keywords: uefi， 設定， 韌體， 安全， semm
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 9e08b3dd804b8b4ac6e2ee4dd4041ed2e684d5d7
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472642"
---
# <a name="microsoft-surface-enterprise-management-mode-semm"></a>MICROSOFT Surface Enterprise管理模式 (SEMM) 

Microsoft Surface Enterprise管理模式 (SEMM) 是 Surface 裝置的功能，具有 Surface Unified Extensible Firmware Interface (UEFI) 。 您可以使用 SEMM 來：

- 保護及管理組織中的韌體設定。
- 準備 UEFI 設定，並將其安裝在 Surface 裝置上。

SEMM 也會使用憑證來保護設定，避免未經授權的竄改或移除。 若要將Surface Hub 2S 移轉至Windows 10 專業版或Windows Enterprise，需要 SEMM。

## <a name="supported-devices"></a>支援的裝置

SEMM 僅適用于具有 Surface UEFI 韌體的裝置，包括： 

- 僅Surface Pro 8 個 (商業 SKU) 
- Surface Pro 4及更新版本 (所有 SKU) 
- Surface Pro X (所有 SKU) 
- Surface Laptop SE (所有 SKU) 
- Surface Laptop Studio 僅 (商業 SKU)  
- Surface Hub 2S
- 僅Surface Laptop 4 個 (商業 SKU) 
- 僅Surface Laptop 3 (Intel 處理器) 
- Surface Laptop Go 
- Surface Book (所有世代) 
- Surface Go、Surface Go 2
- 僅限 Surface Go 3 (商業 SKU) 
- Surface Studio 

>[!TIP]
> 商業 SKU (也稱為Surface 商務版) 執行Windows 10 專業版/Enterprise或Windows 11 專業版/Enterprise;取用者 SKU 執行Windows 10/Windows 11 家用版。 若要深入瞭解， [請參閱檢視您的系統資訊](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00)。 


## <a name="getting-started"></a>開始使用 

當 Surface 裝置由 SEMM 設定並使用 SEMM 憑證保護時，系統會將它們視為已在 SEMM 中 *註冊* 。 移除 SEMM 憑證，並將 UEFI 設定的控制權傳回給裝置的使用者時，Surface 裝置會被視為在 SEMM 中 *取消註冊* 。

有兩個系統管理選項可用來管理 SEMM 和註冊 Surface 裝置：

- 本文將說明 SEMM 獨立工具 Microsoft Surface UEFI Configurator。

- 與 Microsoft Endpoint Configuration Manager 整合。 如需詳細資訊，請[參閱使用Microsoft Endpoint Configuration Manager以 SEMM 管理裝置](use-system-center-configuration-manager-to-manage-devices-with-semm.md)。

## <a name="microsoft-surface-uefi-configurator"></a>Microsoft Surface UEFI 設定程式

SEMM 的主要工作區是 Microsoft Surface UEFI Configurator，如圖 1 所示。

您可以使用 Microsoft Surface UEFI Configurator 來：

- 建立 Windows 安裝程式 (.msi) 套件。
- 使用 WinPE 映射在 Surface 裝置上註冊、設定及取消註冊 SEMM。

這些套件包含指定 UEFI 設定的組態檔。 SEMM 套件也包含安裝並儲存在韌體中的憑證，並用來在套用 UEFI 設定之前驗證組態檔的簽章。

>[!TIP]
>您現在可以使用 Surface UEFI Configurator 和 SEMM 來管理 Surface 擴充座 2 上的埠。 若要深入瞭解，請參閱 [使用 SEMM 保護 Surface 擴充座 2 埠](secure-surface-dock-ports-semm.md)。

![Microsoft Surface UEFI 設定程式。](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*圖 1。 Microsoft Surface UEFI 設定程式*

您可以在三種模式中使用 Microsoft Surface UEFI 設定器工具：

- [Surface UEFI 組態套件](#configuration-package)。 使用此模式來建立 Surface UEFI 設定套件，以在 SEMM 中註冊 Surface 裝置，並在已註冊的裝置上設定 UEFI 設定。
- [Surface UEFI 重設套件](#reset-package)。 使用此模式可從 SEMM 取消註冊 Surface 裝置。
- [Surface UEFI 復原要求](#recovery-request)。 使用此模式來回應復原要求，以從重設封裝作業未成功的 SEMM 取消註冊 Surface 裝置。

### <a name="download-microsoft-surface-uefi-configurator"></a>下載 Microsoft Surface UEFI 設定程式

您可以從 Microsoft 下載中心的 Surface [Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) 頁面下載 Microsoft Surface UEFI 設定程式。

- 針對 Intel/AMD 裝置，請下載： **SurfaceUEFI_Configurator_v2.94.139.0_x64.msi**
- 針對 ARM 裝置，請下載： **SurfaceUEFI_Configurator_v2.94.139.0_x86.msi。**

### <a name="configuration-package"></a>組態套件

Surface UEFI 設定套件是實作和管理 Surface 裝置上 SEMM 的主要機制。 這些套件包含組態檔和憑證檔案，如圖 2 所示。 組態檔包含在 Microsoft Surface UEFI Configurator 中建立套件時所指定的 UEFI 設定。 當組態套件第一次在尚未在 SEMM 中註冊的 Surface 裝置上執行時，它會在裝置的韌體中布建憑證檔案，並在 SEMM 中註冊裝置。 在 SEMM 中註冊裝置時，以及在憑證儲存並註冊完成之前，系統會提示您提供 SEMM 憑證指紋的最後兩位數來確認作業。 這項確認需要使用者在註冊期間實際出現在裝置上，才能執行確認。

![使用憑證保護 SEMM 設定套件。](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*圖 2. 使用憑證保護 SEMM 設定套件*

如需 SEMM 憑證需求的詳細資訊，請參閱本文稍後的[Surface Enterprise管理模式憑證需求](#surface-enterprise-management-mode-certificate-requirements)一節。

>[!TIP]
>您可以選擇使用 SEMM 要求 UEFI 密碼。 如果您這樣做，則需要密碼才能檢視 Surface UEFI**的 [安全**性]、[**裝置**]、[**開機****設定] 和 [Enterprise 管理**] 頁面。

在 SEMM 中註冊裝置之後，會讀取組態檔，並將檔案中指定的設定套用至 UEFI。 當您在已在 SEMM 中註冊的裝置上執行組態套件時，會根據儲存在裝置韌體中的憑證檢查組態檔的簽章。 如果簽章不相符，則不會對裝置套用任何變更。

### <a name="enable-or-disable-devices-in-surface-uefi-with-semm"></a>使用 SEMM 在 Surface UEFI 中啟用或停用裝置

下列清單顯示您可以在 SEMM 中管理的所有可用裝置：

- 停駐 USB 埠
- 上架音訊
- 數位圖形處理單位
- 類型涵蓋
- Micro SD 記憶卡
- 前方相機
- 後方相機
- 適用于 Windows Hello) 的紅外線相機 (
- 僅限藍牙
- 無線網路和藍牙
- LTE)  (長期演進

 >[!NOTE]
>在 [UEFI 裝置] 頁面上，內建裝置可能會根據您的裝置或公司環境而有所不同。 例如，Surface Pro X 上不支援 [UEFI 裝置] 頁面;LTE 只會出現在配備 LTE 的裝置上。

### <a name="configure-advanced-settings-with-semm"></a>使用 SEMM 設定進階設定

**表 1. 進階設定**

| 設定                            | 描述                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 適用於 PXE 開機 的 IPv6                  | 可讓您管理 PXE 開機的 IPv6 支援。 如果您未設定此設定，則會停用 PXE 開機的 IPv6 支援。                                                                               |
| 替代開機                     | 可讓您在開機期間按下 [音量關閉] 按鈕和 [電源] 按鈕，以管理使用替代開機順序直接開機到 USB 或乙太網路裝置。 如果您未設定此設定，則會啟用替代開機。 |
| 開機順序鎖定                    | 可讓您鎖定開機順序以防止變更。 如果您未設定此設定，則會停用開機順序鎖定。                                                                                                        |
| USB 開機                           | 可讓您管理 USB 裝置的開機。 如果您未設定此設定，則會啟用 USB 開機。                                                                                                                 |
| 網路堆疊                      | 可讓您管理網路堆疊開機設定。 如果您未設定此設定，則會停用管理網路堆疊開機設定的能力。                                                                                                           |
| 自動開啟電源                      | 可讓您管理自動開機電源設定。 如果您未設定此設定，則會啟用自動開啟電源。                                                                                                        |
| 同時多執行緒 (SMT)  | 可讓您管理同時多執行緒 (SMT) ，以啟用或停用超執行緒。 如果您未設定此設定，則會啟用 SMT。                                                  |
|啟用電池限制| 可讓您管理電池限制功能。 如果您未設定此設定，則會啟用電池限制 |
| 安全性                           | 顯示 [Surface UEFI **安全性** ] 頁面。 如果您未設定此設定，則會顯示 [安全性] 頁面。                                                                                                                 |
| 裝置                            | 顯示 [Surface UEFI **裝置]** 頁面。 如果您未設定此設定，則會顯示 [裝置] 頁面。                                                                                                                     |
| 開機                               | 顯示 [Surface UEFI **開機]** 頁面。 如果您未設定此設定，則會顯示 [開機] 頁面。                                                                                                                                                            |
| DateTime                           | 顯示 Surface UEFI **DateTime** 頁面。 如果您未設定此設定，則會顯示 DateTime 頁面。                                                                                                                |
| EnableOSMigration                          | 可讓您將 Surface Hub 2 從 Windows 10 團隊版 移轉至 Windows 10/11 Pro或Enterprise。 如果您未設定此設定，Surface Hub 2 個裝置只能執行Windows 10 團隊版作業系統。 注意：Surface Hub 2 上無法使用 Windows 10 團隊版 與 Windows 10/11 Pro/Enterprise之間的雙重開機。                                                                                                           |

>[!TIP]
>當您建立 SEMM 組態套件時，[ **成功** ] 頁面上會顯示兩個字元，如圖 3 所示。

![憑證指紋顯示。](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*圖 3. 在 [成功] 頁面上顯示憑證指紋的最後兩個字元*

這些字元是憑證指紋的最後兩個字元，應該寫下或錄製。 需要字元才能確認 Surface 裝置上的 SEMM 註冊，如圖 4 所示。

![SEMM 中的註冊確認。](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*圖 4. 使用 SEMM 憑證指紋在 SEMM 中註冊確認*

>[!TIP]
>具有憑證檔案 (.pfx) 存取權的系統管理員隨時都可以在 CertMgr 中開啟 .pfx 檔案來讀取指紋。 若要使用 CertMgr 檢視指紋：
>
>1. 選取並按住 (，或以滑鼠右鍵按一下 .pfx 檔案) ，然後選取 [ **開啟]**。
>2. 在流覽窗格中，展開 資料夾。
>3. 選 **取 [憑證]**。
>4. 在主窗格中，選取並按住 (，或以滑鼠右鍵按一下) 您的憑證，然後選取 [ **開啟]**。
>5. 選取 [ **詳細資料] 索** 引標籤。
>6. 在 [ **顯示** ] 下拉式功能表中，必須選取 [ **全部** ] 或 [ **僅限屬性** ]。
>7. 選取 [ **指紋]** 欄位。

若要在 SEMM 中註冊 Surface 裝置，或從組態套件套用 UEFI 組態，請在預定的 Surface 裝置上以系統管理許可權執行.msi檔案。 您可以使用應用程式部署或作業系統部署技術，例如[Microsoft Endpoint Configuration Manager](/mem/configmgr)或[Microsoft Deployment Toolkit](/mem/configmgr/mdt)。 當您在 SEMM 中註冊裝置時，您必須實際存在，才能確認裝置上的註冊。 當您將設定套用至已在 SEMM 中註冊的裝置時，不需要使用者互動。

如需如何在 SEMM 中註冊 Surface 裝置或使用 SEMM 套用 Surface UEFI 設定的逐步解說，請參閱使用 [SEMM 註冊和設定 Surface 裝置](enroll-and-configure-surface-devices-with-semm.md)。

### <a name="reset-package"></a>重設套件

Surface UEFI 重設套件僅用來執行一項工作 ， 以從 SEMM 取消註冊 Surface 裝置。 重設套件包含已簽署的指示，可從裝置的韌體中移除 SEMM 憑證，以及將 UEFI 設定重設為原廠預設設定。 如同 Surface UEFI 設定套件，重設套件必須使用 Surface 裝置上布建的相同 SEMM 憑證進行簽署。 當您建立 SEMM 重設套件時，必須提供您想要重設之 Surface 裝置的序號。 SEMM 重設套件不是通用的，它們專屬於一個裝置。

### <a name="recovery-request"></a>復原要求

在某些情況下，可能無法使用 Surface UEFI 重設套件。  (例如，如果 Surface 裝置上的Windows變得無法使用。) 在這些案例中，您可以透過圖 5) 復原要求作業所示的 Surface UEFI (Enterprise**管理頁面，** 從 SEMM 取消註冊 Surface 裝置。

> [!div class="mx-imgBorder"]
> ![起始 SEMM 復原要求。](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*圖 5. 在 [Enterprise 管理] 頁面上起始 SEMM 復原要求*

當您在 **[Enterprise 管理**] 頁面上使用此程式在 Surface 裝置上重設 SEMM 時，會收到重設要求。 此重設要求可以儲存為 USB 磁片磁碟機的檔案、複製為文字，或是以 QR 代碼讀取，並使用行動裝置輕鬆地以電子郵件傳送或傳送訊息。 使用 Microsoft Surface UEFI 設定程式重設要求選項來載入重設要求檔案，或輸入重設要求文字或 QR 代碼。 Microsoft Surface UEFI Configurator 會產生可在 Surface 裝置上輸入的驗證碼。 如果您在 Surface 裝置上輸入程式碼，然後選取 [ **重新開機**]，裝置就會從 SEMM 取消註冊。

>[!NOTE]
>重設要求會在建立後兩小時到期。

如需如何從 SEMM 取消註冊 Surface 裝置的逐步解說，請參閱 [從 SEMM 取消註冊 Surface 裝置](unenroll-surface-devices-from-semm.md)。

## <a name="surface-enterprise-management-mode-certificate-requirements"></a>Surface Enterprise管理模式憑證需求

當您搭配 Microsoft Surface UEFI Configurator 使用 SEMM 並想要套用 UEFI 設定時，需要憑證才能驗證組態檔的簽章。 此憑證可確保裝置在 SEMM 中註冊之後，只能使用使用核准憑證建立的套件來修改 UEFI 設定。

>[!NOTE]
>若要對已註冊 Surface 裝置上的 SEMM 或 Surface UEFI 設定進行任何修改，需要 SEMM 憑證。 如果 SEMM 憑證損毀或遺失，則無法移除或重設 SEMM。 使用適當的備份和復原解決方案，據以管理您的 SEMM 憑證

使用 Microsoft Surface UEFI Configurator 工具建立的套件會使用憑證簽署。 此憑證可確保在 SEMM 中註冊裝置之後，只有使用核准憑證建立的套件可以用來修改 UEFI 的設定。

### <a name="recommended-certificate-settings"></a>建議的憑證設定

針對 SEMM 憑證建議使用下列設定：

- **金鑰演算法** – RSA
- **金鑰長度** – 2048
- **雜湊演算法** – SHA-256
- **類型** – SSL Server 驗證
- **金鑰使用方式** – 數位簽章、金鑰加密
- **提供者** – Microsoft 增強型 RSA 和 AES 密碼編譯提供者
- **到期日** – 憑證建立後 15 個月
- **金鑰匯出原則** – 可匯出

也建議在兩層式公開金鑰基礎結構中驗證 SEMM 憑證， (PKI) 架構，其中中繼憑證授權單位單位 (CA) 專用於 SEMM，以啟用憑證撤銷。 如需兩層式 PKI 設定的詳細資訊，請 [參閱測試實驗室指南：部署 AD CS Two-Tier PKI 階層](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831348(v=ws.11))。

### <a name="self-signed-certificate"></a>自我簽署憑證

您可以使用下列範例 PowerShell 腳本來建立自我簽署憑證，以用於概念證明案例。
若要使用此腳本，請將下列文字複製到 記事本，然後將檔案儲存為 PowerShell 腳本 (.ps1) 。

> [!NOTE]
> 此腳本會建立密碼為 的 `12345678` 憑證。 不建議針對生產環境使用此腳本所產生的憑證。
  
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
>若要搭配 SEMM 和 Microsoft Surface UEFI Configurator 使用，必須使用私密金鑰和密碼保護來匯出憑證。 Microsoft Surface UEFI 設定程式會提示您選取 SEMM 憑證檔案 (.pfx) 和憑證密碼。

若要建立自我簽署憑證：

1. 在 C： 磁片磁碟機上，建立您要儲存腳本的資料夾;例如 C：\SEMM。
2. 將範例腳本複製到記事本 (或對等文字編輯器) ，然後將檔案儲存為 PowerShell 腳本 (.ps1) 。
3. 使用系統管理員認證登入您的電腦，然後開啟提升許可權的 PowerShell 會話。
4. 請確定您的許可權已設定為允許腳本執行。 根據預設，除非您修改執行原則，否則腳本會遭到封鎖而無法執行。 若要深入瞭解，請 [參閱關於執行原則](/powershell/module/microsoft.powershell.core/about/about_execution_policies)。
5. 在命令提示字元中，輸入腳本的完整路徑，然後按 **Enter**。 腳本會建立名為 TempOwner.pfx 的示範憑證。

或者，您可以使用 PowerShell 建立自己的自我簽署憑證。 如需詳細資訊，請 [參閱 New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate)。

>[!NOTE]
>對於在其 PKI 基礎結構中使用離線根目錄的組織，必須在連線到根 CA 的環境中執行 Microsoft Surface UEFI 設定程式，才能驗證 SEMM 憑證。 Microsoft Surface UEFI Configurator 所產生的套件可以當做檔案傳輸，因此可以使用抽取式儲存體在離線網路環境外傳輸，例如 USB 搖桿。

### <a name="managing-certificates-faq"></a>管理憑證常見問題

建議 *的最小* 長度為 15 個月。 您可以使用在 15 個月內過期的憑證，或使用過期超過 15 個月的憑證。

>[!NOTE]
>當憑證過期時，它不會自動更新。

**過期的憑證是否會影響已註冊 SEMM 的裝置功能？**<br><br>
否，憑證只會影響 SEMM 中的 IT 系統管理員管理工作，而且在裝置功能到期時不會有任何影響。

**SEMM 套件和憑證是否需要在擁有 SEMM 套件的所有電腦上更新？**<br><br>
如果您想要讓 SEMM 重設或復原運作，憑證必須有效且未過期。

**是否可以針對我們訂購的每個介面建立大量重設套件？ 可以建置一個可重設環境中所有機器的機器嗎？**<br><br>
針對特定裝置類型建立組態套件的 PowerShell 範例，也可以用來建立與序號無關的重設套件。 如果憑證仍然有效，您可以使用 PowerShell 建立重設套件來重設 SEMM。

## <a name="version-history"></a>版本歷程記錄

### <a name="version-2941390"></a>版本 2.94.139.0

此版本的 SEMM 包括：

- 支援 Surface Laptop Studio、Surface Pro 8 和 Surface Go 3

### <a name="version-2831390"></a>版本 2.83.139.0

此版本的 SEMM 包括：

- 支援Surface Laptop 4
- 支援 Surface Pro 7 的同時多執行緒選項
- 移除過時的 SEMM 設定  
- 改善的 MSI 簽署

### <a name="version-2791390"></a>版本 2.79.139.0

此版本的 SEMM 包括：

- 支援 Surface Pro 7+。
- 使用者體驗改善。

### <a name="version-2781390"></a>版本 2.78.139.0

此版本的 SEMM 包括：

- 支援 Surface Laptop Go 和 Surface Pro X。
- 新版本版本的通知。
- 建立自訂套件以變更擁有權的能力。
- 錯誤修正。

### <a name="version-2731360"></a>版本 2.73.136.0

此版本的 SEMM 包括：

- 使用 SEMM 在 Surface Hub2S 上停用音訊的能力。
- 支援 Surface Pro X for Dock 2。
- 支援擴充座 2 相關作業的 UEFI 管理員。
- Surface Go 重設套件錯誤修正。
- 支援將 Surface Hub 2 裝置從 Windows 10 團隊版 OS 移轉至 Windows 10 專業版 或 Enterprise。

### <a name="version-2711390"></a>版本 2.71.139.0

此版本的 SEMM 新增對 Surface 擴充座 2 管理功能的支援，適用于 Surface Book 3、Surface Laptop 3 和 Surface Pro 7。 其中包含：

- 啟用音訊 (鎖定/解除鎖定) ，以及乙太網路和 USB 埠的能力。
- 能夠為已驗證和未經驗證的主機建立擴充套件。

### <a name="version-2701300"></a>版本 2.70.130.0

此版本的 SEMM 包括：

- 支援 Surface Go 2。
- 支援 Surface Book 3。
- 錯誤修正。

### <a name="version-2591390"></a>版本 2.59.139.0

此版本的 SEMM 包括：

- 支援使用 Intel 處理器Surface Pro 7、Surface Pro X 和 Surface Laptop 3 13.5" 和 15" 模型。
    >[!NOTE]
    >不支援 Surface Laptop 3 15 吋 AMD 處理器。
- 支援電源喚醒功能。

### <a name="version-2541390"></a>版本 2.54.139.0

此版本的 SEMM 包括：

- 支援 Surface Hub 2S。
- 錯誤修正。

### <a name="version-2431360"></a>2.43.136.0 版

此版本的 SEMM 包括：

- 支援啟用/停用同時多執行緒。
- 針對某些裝置的無線網路功能和藍牙個別選項。
- 已移除Surface Studio的電池限制。

### <a name="version-2261360"></a>版本 2.26.136.0

此版本的 SEMM 包括：

- 支援 Surface Studio 2。
- 電池限制功能。

### <a name="version-2211360"></a>2.21.136.0 版

此版本的 SEMM 包括：

- 支援Surface Pro 6。
- 支援 Surface Laptop 2。

### <a name="version-2141360"></a>版本 2.14.136.0

此版本的 SEMM 包括：

- 支援 Surface Go。

### <a name="version-291360"></a>版本 2.9.136.0

此版本的 SEMM 包括：

- 支援 Surface Book 2。
- 支援 Surface Pro LTE。
- 協助工具改善。

### <a name="version-10740"></a>1.0.74.0 版

此版本的 SEMM 包括：

- 支援Surface Laptop。
- 支援Surface Pro。
- 錯誤修正和一般改善。

## <a name="related-topics"></a>相關主題

- [使用 SEMM 註冊及設定 Surface 裝置](enroll-and-configure-surface-devices-with-semm.md)
- [從 SEMM 取消 Surface 裝置的註冊](unenroll-surface-devices-from-semm.md)
- [使用 SEMM 保護 Surface Dock 2 連接埠的安全](secure-surface-dock-ports-semm.md)
