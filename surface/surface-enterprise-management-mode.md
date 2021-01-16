---
title: 'Surface Enterprise 管理模式 (Surface) '
description: 瞭解使用 Surface UEFI 的 Surface 裝置的這項功能如何協助您保護及管理貴組織內的固件設定。
keywords: uefi、設定、固件、安全、semm
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
ms.date: 01/15/2021
ms.openlocfilehash: e6f81639253c646f5d3956243a80f4d61c91028a
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271417"
---
# Microsoft Surface Enterprise 管理模式

Microsoft Surface Enterprise 管理模式 (SEMM) 是具有 Surface UEFI 的 Surface 裝置功能，可讓您保護及管理貴組織內的固件設定。 有了 SEMM，IT 專業人員就能準備 UEFI 設定的設定，並在 Surface 裝置上安裝它們。 除了能夠設定 UEFI 設定之外，SEMM 也會使用憑證來保護設定不會受到未經授權的篡改或移除。 SEMM 是必須能夠將 Surface Hub 2 級遷移到 Windows 10 專業版與企業版的需求。

>[!NOTE]
>SEMM 只能在具有 Surface UEFI 固件的裝置上使用。 這是由大多數其他 Surface 裝置組成，包括 Surface Pro 7 +、Surface Pro X、Surface Hub 2 及 Surface 膝上型3商業 Sku （含 Intel 處理器），以及 Surface 膝上型電腦。 SEMM 在15「Surface 膝上型電腦 3 SKU （含 AMD 處理器）上不受支援， (僅提供零售 SKU) 。 

當 Surface 裝置是由 SEMM 進行設定，並以 SEMM 憑證加以保護時，它們會被視為已在 SEMM 中 *註冊* 。 移除 SEMM 憑證並將 UEFI 設定傳回給裝置的使用者時，Surface 裝置會被視為 SEMM 中的 *unenrolled* 。

您可以使用兩個管理選項來管理 SEMM 和註冊 Surface 裝置，這是獨立的工具或與 Microsoft 端點建構管理員的整合。 本文將說明稱為 Microsoft Surface UEFI 配置單元的 SEMM 獨立工具。 如需有關如何使用 Microsoft 端點設定管理員管理 SEMM 的詳細資訊，請參閱 [使用 Microsoft 端點組態管理員管理裝置與 SEMM](https://technet.microsoft.com/itpro/surface/use-system-center-configuration-manager-to-manage-devices-with-semm)。


## Microsoft Surface UEFI 配置器

SEMM 的主要工作區是 Microsoft Surface UEFI 配置單元，如圖1所示。 Microsoft Surface UEFI 設定檔是用來建立 Windows 安裝程式 ( .msi) 套件或 WinPE 影像的工具，用於在 Surface 裝置上登錄、設定及取消註冊 SEMM。 這些套件包含指定 UEFI 設定的設定檔。 SEMM 套件也會包含已安裝並儲存在固件中的憑證，並用於在應用 UEFI 設定之前驗證設定檔的簽名。

>[!NOTE]
>您現在可以使用 Surface UEFI 配置器和 SEMM 來管理 Surface Dock 2 上的埠。 若要深入瞭解，請參閱 [使用 SEMM 的安全 Surface Dock 2 埠](secure-surface-dock-ports-semm.md)。

![Microsoft Surface UEFI 配置器](images/surface-ent-mgmt-fig1-uefi-configurator.png "Microsoft Surface UEFI Configurator")

*圖 1。 Microsoft Surface UEFI 配置器*


您可以在三種模式中使用 Microsoft Surface UEFI 配置單元工具：

* [SURFACE UEFI 配置套件](#configuration-package)。 使用此模式來建立 Surface UEFI 配置套件，以在 SEMM 中註冊 Surface 裝置，以及在已註冊的裝置上設定 UEFI 設定。
* [SURFACE UEFI 重設套件](#reset-package)。 使用此模式從 SEMM 取消註冊 Surface 裝置。
* [SURFACE UEFI 恢復要求](#recovery-request)。 使用此模式來回應從 SEMM 取消註冊 Surface 裝置的復原要求，而該裝置的重設套件作業不成功。


#### 下載 Microsoft Surface UEFI 配置器

您可以從 Microsoft 下載中心的 [ [表面工具](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面下載 MICROSOFT Surface UEFI 設定檔。

### 配置套件

Surface UEFI 配置套件是在 Surface 裝置上實現及管理 SEMM 的主要機制。 這些套件包含在 Microsoft Surface UEFI 設定檔和憑證檔案中建立套件時指定的 UEFI 設定檔案，如圖2所示。 當您第一次在尚未註冊 SEMM 的 Surface 裝置上執行配置套件時，它會在裝置的固件中設定證書檔案，並在 SEMM 中註冊該裝置。 在 SEMM 中註冊裝置時，系統會提示您在儲存證書檔案並完成註冊前，先提供 SEMM 憑證指紋的最後兩位數，以確認該操作。 此確認要求在註冊時，使用者必須在裝置上實際出現，才能執行確認。

![使用憑證保護 SEMM 設定套件](images/surface-ent-mgmt-fig2-securepackage.png "Secure a SEMM configuration package with a certificate")

*圖 2. 使用憑證保護 SEMM 設定套件*

如需 SEMM 憑證需求的詳細資訊，請參閱本文的 [Surface Enterprise 管理模式證書需求](#surface-enterprise-management-mode-certificate-requirements) 一節。

>[!NOTE]
>您也可以使用 SEMM 來指定 UEFI 密碼，以查看 Surface UEFI 的 **安全性**、 **裝置**、 **啟動**設定或 **企業管理** 頁面所需。

在裝置註冊 SEMM 之後，系統會讀取配置檔案，並將檔案中指定的設定套用至 UEFI。 當您在已在 SEMM 中註冊的裝置上執行設定套件時，系統會針對儲存在裝置固件中的憑證檢查設定檔的簽名。 如果簽名不相符，就不會將變更套用到裝置。

### 使用 SEMM 在 Surface UEFI 中啟用或停用裝置

下列清單顯示所有可在 SEMM 中管理的裝置：

* 插接 USB 埠
* 板載音訊
* DGPU
* 實體鍵盤保護蓋
* 微型 SD 記憶卡
* 前方攝影機
* 後方攝影機
* Windows Hello 版紅外攝影機
* 僅限藍牙
* Wi-Fi 和藍牙
*              LTE           

 >[!NOTE]
>出現在 [UEFI 裝置] 頁面上的內建裝置，可能會根據您的裝置或公司環境而有所不同。 例如，Surface Pro X 上不支援 UEFI 裝置頁面;LTE 只會出現在裝有 LTE 的裝置上。 
### 使用 SEMM 設定高級設定
**表 1. 進階設定**

| 設定                            | 描述                                                                                                                                                                                        |
| ---------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 適用於 PXE 開機 的 IPv6                  | 可讓您管理 PXE 啟動的 IPv6 支援。 如果您未設定此設定，則會停用 IPv6 啟動的 IPv6 支援。                                                                               |
| 替代開機                     | 您可以在啟動期間按下 [音量] 按鈕和 [電源] 按鈕，來管理使用替代啟動順序直接從 USB 或乙太裝置啟動。 如果您未設定此設定，則會啟用備用啟動。 |
| 開機順序鎖定                    | 可讓您鎖定啟動順序以防止變更。 如果您未設定此設定，則會停用 [啟動訂單鎖定]。                                                                                                        |
| USB 開機                           | 可讓您管理 USB 裝置的啟動。 如果您未設定此設定，則會啟用 USB 啟動。                                                                                                                 |
| 網路堆疊                      | 可讓您管理網路堆疊啟動設定。 如果您未設定此設定，系統會停用管理網路堆疊啟動設定的功能。                                                                                                           |
| 自動開啟電源                      | 可讓您管理自動啟動電源設定。 如果您未設定此設定，則會啟用 [自動加電] 功能。                                                                                                        |
| 同時多執行緒 (SMT)  | 可讓您管理同時多執行緒 (SMT) ，以啟用或停用超執行緒。 如果您未設定此設定，則會啟用 SMT。                                                  |
|啟用電池限制| 可讓您管理電池限制功能。 如果您未設定此設定，則會啟用電池計量限制 |
| 安全性                           | 顯示 [Surface UEFI **安全性** ] 頁面。 如果您未設定此設定，就會顯示 [安全性] 頁面。                                                                                                                 |
| 裝置                            | 顯示 [Surface UEFI **裝置** ] 頁面。 如果您未設定此設定，就會顯示 [裝置] 頁面。                                                                                                                     |
| 開機                               | 顯示 [Surface UEFI **啟動** ] 頁面。 如果您未設定此設定，就會顯示 [引導] 頁面。                                                                                                                                                            |
| DateTime                           | 顯示 [Surface UEFI **日期 DateTime** ] 頁面。 如果您未設定此設定，則會顯示 [日期時間] 頁面。                                                                                                                |
| EnableOSMigration                          | 可讓您將 Surface Hub 2 從 Windows 10 小組遷移至 Windows 10 專業版或企業版。 如果您未設定此設定，Surface Hub 2 裝置就只能執行 Windows 10 團隊作業系統。   注意：在 Windows 10 小組與 Windows 10 專業版/企業版之間，在 Surface Hub 2 上無法使用雙啟動。                                                                                                           |


>[!NOTE]
>當您建立 SEMM 設定套件時，[ **成功** ] 頁面上會顯示兩個字元，如圖3所示。

![憑證指紋顯示](images/surface-ent-mgmt-fig5-success.png "Certificate thumbprint display")

*圖 3. 在成功頁面上顯示證書指紋的最後兩個字元*

這些字元是憑證指紋的最後兩個字元，因此應該記下或錄製。 必須有字元來確認在 Surface 裝置上的 SEMM 註冊，如圖4所示。

![SEMM 中的註冊確認](images/surface-ent-mgmt-fig6-enrollconfirm.png "Enrollment confirmation in SEMM")

*圖 4. 在 SEMM 中使用 SEMM 憑證指紋進行註冊確認*

>[!NOTE]
>您可以在 CertMgr 中開啟 .pfx 檔案，讓擁有證書檔案存取權的管理員 ( .pfx) 可隨時讀取指紋。 若要使用 CertMgr 查看指紋，請遵循此程式：
>1. 以滑鼠右鍵按一下 .pfx 檔案，然後按一下 [ **開啟**]。
>2. 展開 [功能窗格] 中的資料夾。
>3. 按一下 [憑證]****。
>4. 在主要窗格中，以滑鼠右鍵按一下您的憑證，然後按一下 [ **開啟**]。
>5. 按一下 [ **詳細資料** ] 索引標籤。
>6. [**全部**] 或 [**僅限屬性**] 必須在 [**顯示**] 下拉式功能表中選取。
>7. 選取欄位 **指紋**。

若要在 SEMM 中註冊 Surface 裝置，或從設定套件套用 UEFI 設定，您只需執行該 .msi 檔案，並在預定的 Surface 裝置上使用系統管理許可權。 您可以使用應用程式部署或作業系統部署技術（例如 [Microsoft 端點配置系統管理器](https://technet.microsoft.com/library/mt346023) ）或 [microsoft 部署工具](https://technet.microsoft.com/windows/dn475741)組。 當您在 SEMM 中註冊裝置時，您必須在物理上顯示，以確認裝置上的註冊。 當您將設定套用到已在 SEMM 中註冊的裝置時，不需要使用者互動。

如需如何在 SEMM 中註冊 Surface 裝置或使用 SEMM 套用 Surface UEFI 設定的逐步逐步解說，請參閱 [使用 SEMM 註冊及設定 surface 裝置](https://technet.microsoft.com/itpro/surface/enroll-and-configure-surface-devices-with-semm)。

### 重設套件

Surface UEFI 重設套件只是用來執行一個工作，以取消從 SEMM 取消對 Surface 裝置的註冊。 重設套件包含從裝置的固件中移除 SEMM 憑證的 [簽署指示]，並將 [UEFI] 設定重設為 [出廠預設值]。 就像 Surface UEFI 設定套件一樣，必須使用在 Surface 裝置上預配的相同 SEMM 憑證來簽署重設套件。 當您建立 SEMM 重設套件時，您必須提供您想要重設之 Surface 裝置的序列值。 SEMM 的 [重設套件] 不是通用的，且專用於一個裝置。

### 復原要求

在某些情況下，可能無法使用 Surface UEFI 重設套件。  (例如，如果 Windows 在 Surface 裝置上無法使用 ) 。在這些案例中，您可以從 SEMM 中的 [ **企業管理** ] (頁面取消對 surface 裝置進行取消註冊，如圖 5) 中的 [恢復要求] 作業。

![啟動 SEMM 的恢復要求](images/surface-ent-mgmt-fig7-semmrecovery.png "Initiate a SEMM recovery request")

*圖 5. 在企業管理頁面上啟動 SEMM 的恢復要求*

當您在 [ **企業管理** ] 頁面上使用此程式來重設 Surface 裝置上的 SEMM 時，系統會提供您的 [重設要求]。 此重設要求可以儲存為檔案至 USB 磁片磁碟機、複製成文字，或以 QR 程式碼的形式讀取，只要行動裝置就能輕鬆地以電子郵件或 messaged 的方式進行。 使用 Microsoft Surface UEFI 設定檔重設要求選項載入重設要求檔案，或輸入重設要求文字或 QR 程式碼。 Microsoft Surface UEFI 配置器會產生可在 Surface 裝置上輸入的驗證碼。 如果您在 Surface 裝置上輸入程式碼，然後按一下 [ **重新開機**]，裝置將會從 SEMM unenrolled。 

>[!NOTE]
>重設要求在建立之後就會過期兩個小時。

如需如何從 SEMM 取消註冊 Surface 裝置的逐步逐步解說，請參閱 [從 SEMM 中取消註冊 surface 裝置](https://technet.microsoft.com/itpro/surface/unenroll-surface-devices-from-semm)。

## Surface Enterprise 管理模式證書需求
在 Microsoft Surface UEFI 設定檔中使用 SEMM 時，需要有認證，才能驗證設定檔的簽名，然後才能套用 UEFI 設定。 這個憑證可確保在裝置註冊 SEMM 之後，只可使用以核准證書建立的套件來修改 UEFI 的設定。

>[!NOTE]
>需要 SEMM 憑證，才能在已註冊的 Surface 裝置上對 SEMM 或 Surface UEFI 設定執行任何修改。 如果 SEMM 憑證損毀或遺失，SEMM 就無法移除或重設。 使用適用于備份與恢復的方案，據此管理您的 SEMM 憑證。

使用 Microsoft Surface UEFI 設定檔工具所建立的套件會以憑證簽署。 這個憑證可確保在裝置註冊 SEMM 之後，只可使用以核准證書建立的套件來修改 UEFI 的設定。 
### 建議的憑證設定
建議針對 SEMM 憑證使用下列設定：

* **金鑰演算法** -RSA 
* **金鑰長度** –2048
* **雜湊演算法** – SHA-256
* **類型** -SSL 伺服器驗證
* **金鑰使用量** -數位簽章、金鑰解碼
* **提供者** -Microsoft 增強的 RSA 和 AES 加密提供者
* **到期日** –從證書建立開始的15個月
* **金鑰匯出原則** –可匯出的

此外，建議您在雙層公開金鑰基礎結構 (的 PKI) 架構（ (CA) 專用於 SEMM，從而啟用憑證吊銷）中驗證 SEMM 憑證。 如需雙層 PKI 設定的詳細資訊，請參閱 [測試實驗室指南：部署 AD CS Two-Tier PKI](https://technet.microsoft.com/library/hh831348)階層。

### 自我簽署憑證 
您可以使用下列範例 PowerShell 腳本，建立可在概念驗證案例中使用的自我簽署憑證。
若要使用此腳本，請將下列文字複製到記事本，然後將檔案儲存為 PowerShell 腳本 (. ps1) 。 

> [!NOTE]
> 此腳本會建立密碼為的憑證 `12345678` 。建議您不要在生產環境中使用此腳本產生的憑證。
  
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
>若要與 SEMM 和 Microsoft Surface UEFI 配置器搭配使用，必須使用私密金鑰及密碼保護來匯出憑證。 Microsoft Surface UEFI 設定檔將會在必要時提示您選取 SEMM 憑證檔案 ( .pfx) 及證書密碼。

1.  在您的 C：磁片磁碟機上建立一個資料夾，您將在此儲存腳本;例如，C:\SEMM。
2.  將範例腳本複製到記事本或對等的文字編輯器，然後將檔案儲存為 PowerShell 腳本 (. ps1) 。
3.  使用系統管理員認證登入您的電腦，並開啟提升許可權的 PowerShell 會話。
4.  確定您的許可權已設定為允許腳本執行。 除非您修改執行原則，否則預設會封鎖腳本執行。 若要深入瞭解，請參閱 [關於執行原則](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies)。
5.  在命令提示字元中，輸入腳本的完整路徑，然後按 Enter。 此腳本會建立名為 TempOwner 的示範證書。

或者，您可以使用 PowerShell 建立自己的自我簽署憑證。 如需詳細資訊，請參閱下列 PowerShell 檔： [ [新-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)]。




>[!NOTE]
>對於在其 PKI 基礎結構中使用離線根目錄的組織，Microsoft Surface UEFI 配置必須在連線至根 CA 的環境中執行，以驗證 SEMM 憑證。 由 Microsoft Surface UEFI 設定檔產生的套件可以轉移成檔案，因此可以使用 [可移動儲存空間] （例如 USB 杆），在離線網路環境外傳輸。

### 管理證書常見問題

建議的 *最小* 長度為15個月。 您可以使用到期日不超過15個月的憑證，或使用超過15個月的憑證。

>[!NOTE] 
>憑證到期後，就不會自動續約。 


**過期的憑證會影響 SEMM 已註冊裝置的功能嗎？**<br><br>
否，憑證只會影響 SEMM 中的 IT 管理員管理工作，且在裝置功能到期時不會有任何影響。


**SEMM 套件和憑證是否需要在擁有它的所有電腦上更新？**

如果您想要 SEMM 重設或還原作業正常運作，憑證必須有效且未過期。 

**針對我們所訂購的每個 surface，會建立大容量重設套件嗎？ 在我們的環境中，您可以使用其中一個程式來重設所有電腦嗎？**

針對特定裝置類型建立配置套件的 PowerShell 範例也可以用來建立獨立于序號碼的重設套件。 如果憑證仍然有效，您可以使用 PowerShell 建立重設套件來重設 SEMM。

## 版本歷程記錄

### 版本2.79.139。0

此版本的 SEMM 包括：
- Surface Pro 7 + 支援
- 改善使用者體驗


### 版本2.78.139。0

此版本的 SEMM 包括：

- 支援 Surface 膝上型電腦和 Surface Pro X
- 新版本發行的通知
- 建立自訂套件以變更擁有權的能力
- 錯誤修正

### 版本2.73.136。0

此版本的 SEMM 包括：

- 現在，您可以使用 SEMM 在 Surface Hub2S 上停用音訊。
- 針對 Dock 2 的 Surface Pro X 的支援
- 針對 Dock 2 相關作業的 UEFI 管理員支援
- 表面上的 [重設套件錯誤] 修正
- 支援將 Surface Hub 2 裝置從 Windows 10 團隊作業系統遷移至 Windows 10 專業版或企業版。

### 版本2.71.139。0

此版本的 SEMM 會針對 Surface mobile 3、Surface 膝上型3和 Surface Pro 7 新增對 Surface Dock 2 管理功能的支援，包括：

- 啟用音訊 (鎖定/解鎖) 、乙太網路和 USB 埠
- 能夠為已驗證及未驗證的主機建立 dock 套件

### 版本2.70.130。0

此版本的 SEMM 包括：

- 表面 [移至 2] 支援
- Surface Book 3 的支援
- 錯誤修正


### 版本2.59.139。0

* 支援 Surface Pro 7、Surface Pro X，以及含英特爾處理器的 Surface 膝上型 3 13.5 "和 15" 模型。 注意： Surface 膝上型電腦 3 15 "不支援 AMD 處理器。

- 支援喚醒功能

### 版本2.54.139。0
* 支援至 Surface Hub 的2秒
* 錯誤修正

### 版本2.43.136。0
* 支援以啟用/停用 simulatenous multithreating 
* 針對某些裝置，分別提供 WiFi 與藍牙選項 
* 已移除 Surface Studio 的電池限制 

### 版本2.26.136。0
* 在 Surface Studio 2 中新增支援
* 電池限制功能

### 版本2.21.136。0
* 新增支援至 Surface Pro 6
* 新增支援至 Surface 膝上型電腦2

### 版本2.14.136。0
* 將支援新增至表面

### 版本 2.9.136.0
* 新增支援至 Surface Book 2
* 新增支援至 Surface Pro LTE
* 協助工具增強功能

### 版本1.0.74。0
* 新增支援至 Surface 膝上型電腦
* 將支援新增至 Surface Pro
* 錯誤修正及一般改進

## 相關主題

- [使用 SEMM 註冊及設定 Surface 裝置](enroll-and-configure-surface-devices-with-semm.md)
- [從 SEMM 取消 Surface 裝置的註冊](unenroll-surface-devices-from-semm.md)
- [使用 SEMM 保護 Surface Dock 2 連接埠的安全](secure-surface-dock-ports-semm.md)
