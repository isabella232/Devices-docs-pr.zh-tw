---
title: 使用 Surface Enterprise 管理模式（SEMM）的安全 Surface Dock 2 埠
description: 這份檔在連線至相容的 Surface 裝置（包括 Surface Book 3、Surface 膝上型電腦3和 Surface Pro 7）時，提供設定 Surface Dock 2 的 UEFI 埠設定的指導方針。
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
ms.date: 06/08/2020
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: de16d76581926a90585b2c6beb2a7bf3b7a695bc
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831210"
---
# 使用 Surface Enterprise 管理模式（SEMM）的安全 Surface Dock 2 埠

## 簡介

Surface Enterprise 管理模式（SEMM）可讓 IT 管理員透過在 Windows 安裝程式設定套件（。MSI 檔案），在整個公司環境中部署至相容的 Surface 裝置。

### 支援的裝置

使用 SEMM 的管理 Surface Dock 2 可供固定連接至 Surface Book 3、Surface 膝上型3和 Surface Pro 7 的塢站使用。 這些相容的 Surface 裝置通常稱為**主機裝置**。 根據主機裝置是否**經過驗證**或未**驗證**，將套件套用到主機裝置。 設定的設定會駐留在主機裝置上的 UEFI 層中，讓您（IT 系統管理員）管理 Surface Dock 2，就像相機中的任何其他內建外設一樣。

>[!NOTE]
>只有當 Dock 連接至下列其中一個相容的裝置時，才能管理 Surface Dock 2 埠： Surface Book 3、Surface 膝上型電腦3和 Surface Pro 7。 任何沒有收到 UEFI 驗證原則設定的裝置，本身就是未獲驗證的裝置。

### 案例

針對登入公司主機裝置的授權人員，限制 Surface Dock 2，提供另一個層級的資料保護。 鎖定 Surface Dock 2 的功能對於高度安全的環境中的特定客戶而言是非常重要的，他們想要在固定性的安全通訊協定中保持遵守，同時又能提供 Dock 的功能和生產力好處。 我們預計在開啟的辦公室和共用空間中使用的 SEMM，特別適合出於安全考慮而想要鎖定 USB 埠的客戶。 如需視頻示範，請查看[Surface Dock 2 的 SEMM](https://youtu.be/VLV19ISvq_s)。

## 設定及部署 Surface Dock 2 的 UEFI 設定

本節提供下列工作的逐步指導方針：

1. 安裝[**SURFACE UEFI 配置**](https://www.microsoft.com/download/details.aspx?id=46703)器。
1. 建立或取得公開金鑰憑證。
1. 建立。MSI 配置套件。
   1. 新增您的憑證。
   1. 輸入 Surface Dock 2 裝置的16位數 RN 號碼。
   1. 設定 UEFI 設定。
1. 建立設定套件並將其套用至目標 Surface 裝置（Surface Book 3、Surface 膝上型電腦3或 Surface Pro 7）。

>[!NOTE]
>**Random 數位（RN）** 是一個唯一的16位十六進位代碼識別碼，在工廠提供，並在 dock 的下方以小類型列印。 RN 不同于大多數的序列值，因為它無法以電子方式讀取。 這可確保擁有權的證據，主要是透過在實際存取裝置時讀取 RN 來建立。 您也可以在購買交易期間取得 RN，並將其記錄在 Microsoft 庫存系統中。

### 安裝 SEMM 和 Surface UEFI 配置器

透過執行**SurfaceUEFI_Configurator_v2.71.139.0.msi**來安裝 SEMM。 這是獨立的安裝程式，包含您建立並散佈 Surface Dock 2 的設定套件所需的一切。

- 從[表面工具](https://www.microsoft.com/en-us/download/details.aspx?id=46703)下載**SURFACE UEFI 配置**檔。

## 建立公開金鑰憑證

本節提供建立週邊用來管理 Surface Dock 2 埠所需的憑證的規範。

### 必要條件

本文假設您是從協力廠商提供者取得憑證，或您已經有 PKI 認證服務的專業知識，並知道如何建立您自己的憑證。  您應該熟悉並遵循建立憑證的一般建議，如[Surface Enterprise 管理模式（SEMM）](https://docs.microsoft.com/surface/surface-enterprise-management-mode)檔中所述，有一個例外狀況。 此頁面上所述的憑證需要在**Dock 憑證授權單位**的到期期限為30年，且**主機驗證憑證**為20年。

如需詳細資訊，請參閱[憑證服務架構](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)檔，並在 microsoft 新聞中查看[windows server 2019](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)中適當的章節，或是從 Microsoft 按下取得的[Windows Server 2008 PKI 與證書安全性](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)。

### 根目錄與主機憑證需求

在建立設定套件之前，您必須準備公用金鑰憑證，以驗證 Surface Dock 2 的擁有權，並在裝置週期期間協助擁有任何後續變更。 主機和置備憑證需要輸入 EKU Id，否則稱為「**用戶端驗證」增強型金鑰用法（EKU）物件識別碼（oid**）。

[資料表 1] 和 [資料表 2] 中列出所需的 EKU 值。

#### 表 1. 根目錄與 Dock 證書需求

|憑證|演算法|描述|到期|EKU OID|
|---|---|---|---|---|
|根憑證授權單位|ECDSA_P384|-具有384位質數橢圓曲線數位簽章演算法（ECDSA）的根憑證<br>-SHA 256 金鑰用法：<br>CERT_DIGITAL_SIGNATURE_KEY_USAGE<br>-CERT_KEY_CERT_SIGN_KEY_USAGE<br>CERT_CRL_SIGN_KEY_USAGE|30年|無
|Dock 憑證授權單位|ECC P256 曲線|使用256位橢圓曲線密碼加密（ECC）的主機憑證<br>-SHA 256 金鑰用法：<br>CERT_KEY_CERT_SIGN_KEY_USAGE<br>-路徑長度限制 = 0|20年|1.3.6.1.4.1.311.76.9.21.2<br>1.3.6.1.4.1.311.76.9.21.3|

   >[!NOTE]
   >Dock CA 必須匯出為. p7b 檔案。

### 提供管理憑證需求

每個主機裝置都必須擁有 [doc] CA 和兩個憑證，如資料表2所示。

#### 表 2. 提供管理憑證需求

|憑證|演算法|描述|EKU OID|
|---|---|---|---|
|主機驗證憑證|ECC P256<br>SHA 256|證明主機裝置的身分識別。|1.3.6.1.4.1.311.76.9.21.2|
|提供管理憑證|ECC P256<br>SHA256|可讓您更換目前安裝在 dock 上的 CA，以變更 dock 擁有權和/或原則設定。|1.3.6.1.4.1.311.76.9.21.3<br>1.3.6.1.4.1.311.76.9.21.4|

   >[!NOTE]
   >主機驗證與預配憑證必須匯出為 .pfx 檔案。

### 建立配置套件

取得或建立憑證之後，您就可以開始建立將套用至目標 Surface 裝置的 MSI 配置套件。

1. 執行 Surface **UEFI 配置**器。

   ![執行 Surface UEFI 配置器](images/secure-surface-dock-ports-semm-1.png)

1. 選取 [**介面固定**]。

   ![選取介面停靠](images/secure-surface-dock-ports-semm-2.png)

1. 在 [憑證] 頁面上，輸入適當的**憑證**。

   ![輸入適當的憑證](images/secure-surface-dock-ports-semm-3.png)

1. 在清單中新增適當的固定 RNs。

   >[!NOTE]
   >為多個 Surface Dock 2 裝置建立配置套件時，不是手動輸入每個 RN，而是使用包含 RNs 清單的 .csv 檔案。

1. 指定 USB 資料、乙太網路和音訊埠的原則設定。 UEFI 配置器可讓您針對經過驗證的使用者設定策略設定（經過驗證的原則）與未驗證的使用者（未驗證的原則）。 下圖顯示針對經過驗證的使用者開啟埠存取，並針對未授權的使用者關閉該功能。

   ![選擇您要啟動或停用的元件。](images/secure-surface-dock-ports-semm-4.png)

   - 已驗證使用者參照已安裝適當證書的 Surface 裝置，如中所述。您已套用至目標裝置的 MSI 配置套件。 它適用于登入裝置的任何由使用者驗證的使用者。 
   - 未驗證的使用者會參照任何其他裝置。
   - 選取 [**重設**]，建立特殊的「重設」套件，該套件將移除任何先前已接受的固定配置套件。

1. 選取 [**建立**] 以建立指定的套件。

### 將 configuration 套件套用至 Surface Dock 2

1. 讓 Surface UEFI 設定檔產生的 MSI 檔案，並將它安裝在 Surface 主機裝置上。 相容的主機裝置為 Surface Book 3、Surface 膝上型3或 Surface Pro 7。
1. 將主機裝置連接至 Surface Dock 2。 當您連線時，就會套用 dock UEFI 原則設定。

## 使用 Surface App 驗證受管理的狀態

一旦您套用了設定套件，您就可以直接從 Surface App 驗證 dock 的產生原則狀態（依預設在所有 Surface 裝置上安裝）。 如果表面 App 不存在於裝置上，您可以從 Microsoft 網上商店下載並安裝。

### 測試案例

目標：將原則設定設定為僅允許經過驗證的使用者存取埠。

1. 針對經過驗證的使用者開啟所有埠，然後將其關閉以進行未授權的使用者。

   ![為經過驗證的使用者啟用埠](images/secure-surface-dock-ports-semm-4.png)

1. 將 [設定套件] 套用到您的目標裝置，然後連接 Surface Dock 2。

1. 開啟 [ **surface] App** ，然後選取 [**表面停靠**] 來查看 surface dock 的結果原則狀態。 如果已套用原則設定，Surface App 就會指出埠可供使用。

   ![Surface app 顯示所有埠都可供經過驗證的使用者使用](images/secure-surface-dock-ports-semm-5.png)

1. 現在，您必須驗證原則設定是否已成功關閉所有埠（未經授權的使用者）。 將表面停靠2連接至未受管理的裝置，亦即，在您所建立之設定套件的管理範圍之外的任何 Surface 裝置。

1. 開啟 [ **surface] App** ，然後選取 [**介面固定**]。 產生的原則狀態將會指出埠已關閉。

   ![顯示未授權使用者的埠關閉的 Surface 應用程式 ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
>如果您想要保留裝置的擁有權，但允許所有使用者都能使用 [完全存取]，您可以建立新的套件，讓所有人都能開啟。 如果您想要完全移除裝置的限制及擁有權（使其處於未受管理的狀態），請選取 [在 Surface UEFI 設定檔中**重設**]，以建立要套用至目標裝置的套件。

！. 您已在目標主機裝置上成功管理 Surface Dock 2 埠。

## 深入了解

- [Surface Enterprise 管理模式（SEMM）檔](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [憑證服務架構](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [Windows Server 2019 內](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [Windows Server 2008 PKI 與證書安全性](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
