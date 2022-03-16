---
title: '使用 Surface 管理模式和 SEMM Enterprise保護 Surface Dock 2 (埠) '
description: 本檔提供在連接至相容的 Surface 裝置時設定 Surface Dock 2 的 UEFI 埠設定，包括 Surface Book 3、Surface Laptop 3 和 Surface Pro 7。
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
ms.reviewer: ''
manager: laurawi
keywords: 疑難排解常見問題, 設定問題
ms.prod: w10
ms.mktglfcycl: support
ms.sitesec: library
ms.pagetype: surfacehub
author: v-miegge
ms.author: jesko
ms.topic: article
ms.date: 08/02/2021
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 3eae976b1559c59bf44a94a62eb98dd3a3687424
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448486"
---
# <a name="secure-surface-dock-2-ports-with-surface-enterprise-management-mode-semm"></a>使用 Surface 管理模式和 SEMM Enterprise保護 Surface Dock 2 (埠) 

## <a name="introduction"></a>簡介

Surface Enterprise 管理模式 (SEMM) 可讓 IT 系統管理員在 Windows Installer 設定套件 (.msi 檔案) 中設定部署至整個公司環境中相容 Surface 裝置中的 UEFI 設定，以保護和管理 Surface Dock 2 埠。

### <a name="supported-devices"></a>支援的裝置

使用 SEMM 管理 Surface Dock 2 適用于連接到 Surface Book 3、Surface Laptop Studio、Surface Laptop 4、Surface Laptop 3、Surface Laptop Go、Surface Pro 8、Surface Pro 7+、Surface Pro 7 和 Surface Pro X。這些相容的 Surface 裝置通常稱為**主機裝置**。 套件會根據主機裝置是否經過驗證或未經驗證，套用至**** 主機**裝置**。 設定設定會位於主機裝置上的 UEFI 圖層中，以便您管理 Surface Dock 2，就像任何其他內建的外接裝置 ，例如相機一樣。

>[!NOTE]
>只有當 Dock 連接到下列其中一個相容裝置時，才能管理 Surface Dock 2 埠：Surface Pro 8、Surface Laptop Studio、Surface Book 3、Surface Laptop 4、Surface Laptop 3、Surface Pro 7+，以及Surface Pro 7。 任何未收到 UEFI 驗證策略設定的裝置，其本身都是未經驗證的裝置。

### <a name="scenarios"></a>案例

將 Surface Dock 2 限制為已簽署公司主機裝置的授權人員，可提供另一層資料保護。 這種鎖定 Surface Dock 2 的能力對於在高度安全的環境中想要擴展座功能與生產力優勢，同時維持嚴格安全性通訊協定合規性的特定客戶來說至關重要。 我們預期與 Surface Dock 2 一起使用的 SEMM 在開放式辦公室和共用空間中會特別實用，尤其是針對因安全性考慮想要鎖定 USB 埠的客戶。 如要觀看影片示範，請查看 [Surface Dock 2 的 SEMM](https://youtu.be/VLV19ISvq_s)。

## <a name="configuring-and-deploying-uefi-settings-for-surface-dock-2"></a>設定及部署 Surface Dock 2 的 UEFI 設定

本節提供下列工作逐步指南：

1. 從 **適用于 IT 的 Surface** Tools 安裝 Surface UEFI [Configurator](https://www.microsoft.com/download/details.aspx?id=46703)。
1. 建立或取得公用金鑰憑證。
1. 建立.msi套件。
   1. 新增您的憑證。
   1. 輸入 Surface Dock 2 裝置 16 位數的 RN 號碼。
   1. 設定 UEFI 設定。
1. 在 7. (Surface Book 3、Surface Laptop 3 或 7.Surface Pro中建立並套用組) 

>[!NOTE]
>隨機 **數 (RN) ** 是一個唯一的 16 位數十六進位代碼識別碼，在出廠時提供，且以小型類型列印于固定座的背面。 RN 與大多數的序列值不同，因為無法以電子方式讀取。 這可確保主要只有在實際存取裝置時讀取 RN，才能建立擁有證明。 RN 也可能在購買交易期間取得，並記錄在 Microsoft 庫存系統中。

### <a name="install-semm-and-surface-uefi-configurator"></a>安裝 SEMM 和 Surface UEFI 配置器

若要安裝 SEMM， ** 請SurfaceUEFI_Configurator_v2.83.139.0.msi。** 這是獨立的安裝程式，包含建立及發佈 Surface Dock 2 組組套件所需的一切。

- 從 **適用于 IT 的 Surface** Tools 下載 Surface UEFI [Configurator](https://www.microsoft.com/download/details.aspx?id=46703)。

## <a name="create-public-key-certificates"></a>建立公用金鑰憑證

本節提供建立管理 Surface Dock 2 埠所需的憑證的規格。

### <a name="prerequisites"></a>必要條件

本文假設您從協力廠商提供者取得憑證，或您已有 PKI 憑證服務專業知識，並知道如何建立自己的證書。  您應該熟悉並遵循 Surface Enterprise 管理模式 ([SEMM](surface-enterprise-management-mode.md)) 中所述建立憑證的一般建議，但只有一個例外。 在此頁面上所記錄之憑證的到期期限為 Dock **證書**頒發機構為 30 年，主機驗證憑證為 20 **年**。

詳細資訊，請參閱憑證服務[](/windows/win32/seccrypto/certificate-services-architecture)架構檔，並參閱 Microsoft Press 提供的[Windows Server 2019 內](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)外部或[Windows Server 2008 PKI](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)和憑證安全性中的適當章節。

### <a name="root-and-host-certificate-requirements"></a>根憑證和主機憑證需求

在建立組組套件之前，您需要準備公用金鑰憑證，以驗證 Surface Dock 2 的擁有權，並有助於在裝置生命週期期間對擁有權進行任何後續變更。 主機和布備憑證需要輸入 EKU 識別碼，也稱為用戶端驗證增強金鑰使用量 ** (EKU) 物件識別碼 (OIDs **) 。

所需的 EKU 值會列在資料表 1 和表格 2 中。

#### <a name="table-1-root-and-dock-certificate-requirements"></a>表 1. 根憑證和 Dock 憑證需求

|憑證|演算法|描述|到期|EKU OID|
|---|---|---|---|---|
|根憑證授權單位|ECDSA_P384|- 具有 384 位主要省略號曲線數位簽章演算法的根憑證 (ECDSA) <br>- SHA 256 金鑰使用量：<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>- CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30 年|不適用
|Dock 憑證授權單位|ECC P256 曲線|- 具有 256 位省略號曲線加密法的主機憑證 (ECC) <br>- SHA 256 金鑰使用量：<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>- 路徑長度限制式 = 0|20 年|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >Dock CA 必須匯出為 .p7b 檔案。

### <a name="provisioning-administration-certificate-requirements"></a>資源配置系統管理憑證需求

每個主機裝置都必須有檔 CA 和兩個憑證，如表 2 所示。

#### <a name="table-2-provisioning-administration-certificate-requirements"></a>表 2. 資源配置系統管理憑證需求

|憑證|演算法|描述|EKU OID|
|---|---|---|---|
|主機驗證憑證|ECC P256<br>SHA 256|證明主機裝置身分識別。|1.3.6.1.4.1.311.76.9.21.2|
|資源建構管理憑證|ECC P256<br>SHA256|可讓您取代目前安裝在固定座上的 CA，以變更 Dock 擁有權和/或策略設定。|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >主機驗證和置備憑證必須匯出為 .pfx 檔案。

### <a name="create-configuration-package"></a>建立組組套件

當您取得或建立憑證時，就可以建立套用至目標 Surface .msi組組套件。

1. 執行 Surface **UEFI Configurator**。

   ![執行 Surface UEFI Configurator。](images/secure-surface-dock-ports-semm-1.png)

1. 選取 **Surface Dock**。

   ![選取 Surface Dock。](images/secure-surface-dock-ports-semm-2.png)

1. 在憑證 **頁面上**  輸入適當的憑證。 可從適用于 IT 的[Surface Tools](https://www.microsoft.com/download/details.aspx?id=46703)**：下載SEMM_PowerShell.zip**，**並參閱CreateSurfaceDock2Certificates.ps1**。 執行示範腳本 **SurfaceDock2_WmiInstanceProvider** ，請確定您安裝此程式。

   ![輸入適當的憑證。](images/secure-surface-dock-ports-semm-3.png)

1. 在清單中新增適當的 dock RNs。

   >[!TIP]
   >當您為多個 Surface Dock 2 裝置建立組組套件時，您可以使用包含 RNs 清單的 .csv 檔案，而不是手動輸入每個 RN。

1. 指定 USB 資料、乙太網路和音訊埠的策略設定。 UEFI 設定器可讓您設定已驗證使用者 (已驗證) 和未經驗證的使用者 (未驗證) 。 下圖顯示已驗證使用者的埠存取已開啟，且未驗證的使用者已關閉。

   ![選擇您想要啟用或停用的元件。](images/secure-surface-dock-ports-semm-4.png)

   - 已驗證的使用者是指已安裝適當憑證的 Surface Device，.msi套用至目標裝置之組.msi套件中所配置。 它適用于任何已驗證使用者，並登錄裝置的使用者。
   - 未經驗證的使用者是指任何其他裝置。
   - 選取 **「重** 設」以建立特殊的「重設」套件，以移除 Dock 先前接受的任何設定套件。

1. 選取 **建立** 以建立指定的套件。

### <a name="apply-the-configuration-package-to-a-surface-dock-2"></a>將組組套件套用至 Surface Dock 2

1. 請.msi Surface UEFI Configurator 產生的檔案，並安裝于 Surface 主機裝置上。 相容的主機裝置Surface Book 3、Surface Laptop Studio、Surface Laptop 3、Surface Laptop 4、Surface Pro 7+和 Surface Pro 7。
1. 連線主機裝置至 Surface Dock 2。 當您連接固定座時，會採用 UEFI 原則設定。

## <a name="verify-managed-state-using-the-surface-app"></a>使用 Surface App 驗證受管理狀態

套用組態套件之後，您可以直接從 Surface App 快速驗證固定程式的結果原則狀態，此程式預設會安裝在所有 Surface 裝置上。 如果裝置上沒有 Surface App，您可以從裝置下載並Microsoft Store。

### <a name="test-scenario"></a>測試案例

目標：設定策略設定，只允許經過驗證的使用者進行埠存取。

1. 開啟已驗證使用者的所有埠，並針對未經驗證的使用者關閉這些埠。

   ![為已驗證的使用者啟用埠。](images/secure-surface-dock-ports-semm-4.png)

1. 將組組套件套用至目標裝置，然後連接 Surface Dock 2。

1. 開啟 **Surface App** ，然後選取 **Surface Dock** 來查看 Surface Dock 的結果策略狀態。 如果已應用原則設定，Surface App 會指出埠可供使用。

   ![Surface App 顯示所有埠都可供經過驗證的使用者使用。](images/secure-surface-dock-ports-semm-5.png)

1. 現在您需要確認策略設定已成功關閉未驗證使用者的所有埠。 連線 Surface Dock 2 到未管理的裝置，即您建立之組組套件管理範圍外的任何 Surface 裝置。

1. 開啟 **Surface App** ，然後選取 **Surface Dock**。 結果的策略狀態會指出埠已關閉。

   ![Surface App 顯示未驗證使用者的埠已關閉。](images/secure-surface-dock-ports-semm-6.png)

>[!TIP]
>如果您想要保留裝置的擁有權，但允許所有使用者完全存取，您可以製作一個新的套件，並開啟所有專案。 如果您想要完全移除裝置的限制和擁有權 (將其取消管理) ，請選取 Surface UEFI 設定器中的重設以建立套件以套**** 用至目標裝置。

祝賀。 您已成功管理目標主機裝置上的 Surface Dock 2 埠。

## <a name="learn-more"></a>深入了解

- [SURFACE Enterprise管理模式 (SEMM) 檔](surface-enterprise-management-mode.md)
- [憑證服務架構](/windows/win32/seccrypto/certificate-services-architecture)
- [Windows伺服器 2019 從內到外](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows伺服器 2008 PKI 和憑證安全性](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
