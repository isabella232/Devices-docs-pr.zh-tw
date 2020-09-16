---
title: 移轉到 Windows 10 專業版或 Surface Hub 2 企業版
description: 本文將說明從 Surface Hub 2 上的 Windows 10 小組遷移到 Windows 10 專業版或 Windows 10 企業版的程式。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 09/15/2020
ms.localizationpriority: Medium
ms.openlocfilehash: d36f42485107dd84be08c20291b36540662503da
ms.sourcegitcommit: c2df79cab0e59e9d7ea6640e5899531b57cd383f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016452"
---
# 移轉到 Windows 10 專業版或 Surface Hub 2 企業版

## 簡介

Surface Hub 秒數是由 Windows 10 小組預先安裝的，這是 Windows 10 的自訂版本，可協助在會議室環境中輕鬆共同作業。 現在，您可以選擇執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。 

> [!IMPORTANT]
>與典型的升級或遷移不同，此程式必須遵循說明性程式，如本頁面所述。 在繼續之前，請先查看 [解決方案元件](#solution-components) 與 [遷移及安裝工作流程](#migration-and-installation-workflow-summary) 。


> [!NOTE]
> 當您安裝 Windows 10 專業版或企業版時，您將需要與現有的 Windows 10 小組授權分開的新授權。 


您可以從 Windows 10 小組開始遷移，使用不同的電腦和可下載的工具- **SURFACE UEFI 配置** 器，建立包含您套用至 Surface Hub 2 秒的新 UEFI 設定的套件。  Surface UEFI 配置處理常式會將介面轉換成 Surface Enterprise 管理模式 (SEMM) ，旨在協助集中管理公司環境中的 Surface 裝置。 若要深入瞭解 SEMM，請參閱 [Microsoft Surface Enterprise 管理模式檔](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。
 

## 解決方案元件

- 執行 Windows 10 小組作業系統的 Surface Hub 2 秒裝置
- 運行 Windows 10 的個別裝置
- Surface UEFI 組態工具
- Windows 10 專業版或企業版作業系統影像、版本1903或更高版本
- 含儲存空間、FAT32 格式的兩個 USB 磁片磁碟機
- Windows 10 專業版的驅動程式和固件，以及 Surface Hub 2、Windows 安裝程式。MSI 檔案
- 網際網路連線
- 影像處理方案 (選用) 

 
## 遷移和安裝工作流程摘要

| 步驟  | 動作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sr-1 | [驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | 確定 UEFI 版本為694.2938.768.0 或更新版本。                                                                                                                                                                                                                                                                                                                                                      |
| pplx-2 | [下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 從表面工具下載 [SURFACE UEFI 配置](https://www.microsoft.com/download/details.aspx?id=46703) 器，並將它安裝在不同的電腦上。 [在 Surface Hub 2 上下載適用于 Windows 10 專業版與企業版的驅動程式及固件。MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案並將其儲存，以便在步驟5中使用。 |
| 3 | [準備 SEMM 憑證](#prepare-semm-certificate)                                                                          | 準備運行 Surface UEFI 配置器所需的憑證，或使用您目前的憑證。                                                                                                                                                                                                                                                                                                      |
| 4 | [建立 SEMM 套件](#create-semm-package)                                                                               | 啟動 Surface UEFI 設定檔，以在 USB 磁片磁碟機上建立 SEMM 套件，這將包含要套用到 Surface Hub 2 的必要配置檔案。 將這些 SEMM 套件檔案複製到您電腦上的資料夾。                                                                                                                                                                                          |
| 500 | [準備包含 Windows 10 影像、SEMM 套件，以及 Windows 10 專業版的驅動程式和固件的 USB 快閃記憶體磁片磁碟機，以及 Surface Hub 2 的 Enterprise](#prepare-usb-flash-drive-containing-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 在此範例中建立單一 USB 磁片磁碟機 (名為 **BOOTME** ，) 包含 Windows 10 影像。 在 Surface Hub 2 (的 Windows 10 專業版和企業版中新增您的驅動程式與固件，請 (步驟 2) 並 SEMM 封裝檔案步驟 4) 移至 **BOOTME** 磁片磁碟機。                                                                                                                                                                                                  |
| 6 | [更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 **BOOTME** 磁片磁碟機來啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。|
| utf-7 | [安裝 Windows 10 專業版或企業版1903或更新版本](#install-windows-10-pro-or-enterprise)                                        | 使用 **BOOTME** 磁片磁碟機來安裝 **Windows 10 專業版或企業** 版本1903或更新版本。                                                                                                                                                                                                                                                                                 |
| 型 | [在 Surface Hub 2 上安裝適用于 Windows 10 專業版與企業版的驅動程式及固件](#install-surface-hub-2-drivers-and-firmware)                                        | 為了確保您的裝置擁有所有最新的更新和驅動程式，請[在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 Enterprise 的驅動程式和固件。MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案                                                                                                                                                                                                                                                                                  |
| 9 | [將 Surface Hub 2 完整設定為個人生產力裝置](#next-steps)                                        |  啟用一組建議的設定和應用程式，以優化使用 Surface Hub 2 作為個人生產力裝置。                                                                                                                                                                                                                                                                    |

### 驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求

將 Surface Hub 從 Windows 10 小組移植到 Windows 10 Desktop 之前所需的最低 UEFI 版本是 **694.2938.768.0**。
 
**若要在您的系統上驗證目前的 UEFI 版本：**

1. 在 Surface Hub 秒主畫面上，選取 [**開始**]，然後開啟 [ **SurfaceApp** ] (**所有 app**  >  **Surface**) 。

2. 選取 **您的 surface** ，以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。 如果 UEFI 版本是 **694.2938.768.0** 或更新版本（如下所示），則 uefi 適合您建立 SEMM 套件以啟用作業系統遷移。

    ![開啟 Surface App & 選取您的表面](images/shm-fig1.png)
 
3. 如果 UEFI 版本早于版本 **694.2938.768.0**，您將需要使用 Windows Update 取得目前的版本。

**若要從 Windows Update 更新 UEFI：**
1. 在 Surface Hub 2 秒，請以**管理員**身分登入，移至 [**所有應用程式**  >  **設定** >  **更新及安全性**]  >  **Windows 更新**並安裝所有更新，然後重新開機裝置。 使用 Surface App 驗證 UEFI 版本。 注意：如果您不知道您的使用者名稱或系統管理員密碼，您將需要重設裝置。 若要深入瞭解，請參閱 [重設及復原 Surface Hub 2 秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)。

2. 重複這些步驟，直到 UEFI 版本為 **694.2938.768.0** 或更新版本。

3. 如果您在多次嘗試之後仍沒有看到更新的 UEFI，請核取 [ **更新歷程記錄** ] 並尋找任何失敗的固件安裝實例。 您可能需要重設裝置 (**設定**  >  **更新 & 安全**  >  **重設裝置**) 。

### 下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件

在不同的電腦上：

- 從表面工具下載並安裝 Microsoft [SURFACE UEFI 配置](https://www.microsoft.com/download/details.aspx?id=46703) 檔。 安裝 Windows 10 團隊後，surface UEFI 配置器不能在 Surface Hub 2 秒執行。

- 下載 [Surface Hub 2 驅動程式和固件 Windows 安裝程式。](https://www.microsoft.com/download/details.aspx?id=101974) 安裝新作業系統時要套用的 MSI 檔案。

### 準備 SEMM 憑證

如果這是您第一次使用 Surface UEFI 配置器，您必須準備證書。 這個憑證可確保在裝置註冊 SEMM 之後，只可使用已核准憑證建立的套件來修改 UEFI 設定。 您取得憑證的方式可能會根據貴組織的規模或複雜度而有所不同：

- 大型企業組織通常會維護自己的憑證基礎結構，以針對每個標準安全性做法產生證書。

- 中型企業及其他人可以選擇從協力廠商提供者取得憑證。 對於沒有足夠 IT 專業知識或專門 IT 安全小組的組織而言，這是我們的建議選項。

- 或者，您也可以根據下列檔來產生含 PowerShell 腳本的自我簽署憑證： [Surface Enterprise 管理模式憑證需求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 或者，您可以使用 PowerShell 根據下列檔來建立您自己的憑證： [ [新-SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate)]。

SEMM 套件必須使用憑證加以保護，才能驗證設定檔的簽名，然後才能套用 UEFI 設定。 若要深入瞭解，請參閱 [Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 檔。
 
 
### 建立 SEMM 套件

1. 開啟 **SURFACE UEFI 配置** 器，然後選取 [ **開始**]。

   ![開啟 Surface UEFI 配置器](images/shm-fig2.png)
   
2. 選取 [ **Surface 裝置** ]，然後選取 **[下一步]**。

   ![選取 Surface 裝置](images/shm-fig3.png)
  
3. 選取 [設定 **套件**]。

   ![選取 [設定套件]](images/shm-fig4.png)
  
4. 選取 [ **憑證保護**]。

   ![選取憑證保護](images/shm-fig5.png)

5. 系統會提示您新增憑證 .pfx 檔案。

   ![系統會提示您新增憑證](images/shm-fig6.png)
   
6. 輸入您的 **憑證密碼** ，然後選取 **[確定]**。

   ![輸入您的憑證密碼，然後選取 [確定]](images/shm-fig7.png)

7. 選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。 每當您引導至 UEFI 時，就會需要此密碼。 **強烈建議**您設定將在 Surface Hub 2 上使用的 UEFI 密碼。

   ![按一下 [密碼保護]](images/shm-fig8.png)
   
8. 設定 **UEFI 密碼** ，然後選取 **[確定]**。

   ![輸入您的 UEFI 密碼](images/shm-fig9.png)

   > [!IMPORTANT]
   > 記下您的密碼。 如果您忘記或遺失密碼，就不會有復原程式。 

9. 選取 [ **Surface Hub 2 秒** ]，然後選取 **[下一步]**。

   ![選取 Surface Hub 2 秒](images/shm-fig10.png)
   
10. 選取 **\[下一步\]**。

    ![選取 [下一步]](images/shm-fig10a.png)

11. 若要允許安裝 Windows 10 專業版或企業版，請選取 [ **EnableOsMigration]。**

    ![選取 [啟用 OS 遷移]](images/shm-fig11.png)
    
12. 將 **EnableOSMigration** 設定為 [ **開啟** ] 並選取 **[下一步]**。

    ![將 [啟用作業系統遷移] 設定為 [開啟]](images/shm-fig12.png)

> [!NOTE]
> 在您套用 SEMM 套件之後，所有的 UEFI 設定都會以灰色顯示 (在裝置上的 UEFI 功能表中的 [鎖定]) 。 這包含其他設定（例如 IPv6 for PXE 啟動）的預設值。 若要修改 UEFI 設定，您需要套用另一個 SEMM 套件，或取消將裝置從 SEMM 取消註冊。

#### 將 SEMM 套件儲存至 USB 磁片磁碟機

1. 將 USB 磁片磁碟機連線至您的電腦。 選擇 [ **中心2秒** ]，然後選取 **[下一步]**。

   ![選取 [USB]](images/shm-fig13.png)
   
2. 選取 [ **建立**]。

   ![選取組建](images/shm-fig14.png)

3. 捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。 您的 SEMM 套件現已準備就緒，且包含 SEMM 套件 **DfciUpdate. dfi** 和 SEMM thumbprint 的文字檔 (憑證的指紋) 中的最後兩個字元。

   ![選取 [結束]](images/shm-fig15.png)
   
4. 儲存憑證指紋的最後2個字元，這是您在 Surface Hub 2 上套用套件時，必須啟用 SEMM。

### 準備包含 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式與固件的 USB 快閃記憶體磁片磁碟機

您可以使用下列其中一個選項，在版本1903或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：

- 您目前的影像解決方案。

- [Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator) 可讓您建立可引導的 windows 10 影像，其中包含所有目前的 windows 10 更新、Office、您選擇的其他 app，以及所需的驅動程式和固件。 

- 具有 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機，接著  [在 Surface Hub 2 上安裝 Windows 10 專業版和 Enterprise 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。
 

此程式說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後在 Surface Hub 2 上新增適用于 Windows 10 專業版與 Enterprise 的 SEMM 套件檔案和驅動程式及固件。MSI 檔案。 如果您使用的是其他部署方法，請繼續閱讀下列章節： [更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移](#update-uefi-on-surface-hub-2s-to-enable-os-migration)。

> [!NOTE]
> 安裝之後，您將需要 Windows 10 專業版或 Windows 10 Enterprise 的有效授權。

1. 若要建立 Windows 10 專業版安裝，請依照 [下載 windows 10](https://www.microsoft.com/software-download/windows10) 頁面上使用 **媒體建立** 工具的指示進行。 若要下載 Windows 10 企業版，請移至 [Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。

2. 插入新的 **USB 儲存** 空間磁片磁碟機。 啟動 **媒體建立** 工具，選取 [ **建立安裝媒體** ]，然後選取 **[下一步]**。

   ![建立安裝媒體](images/shm-fig16.png)
   
3. 選取 [語言]、[Windows 10] 和 [64 (x64) ，然後選取 **[下一步]**。

   ![選取 [語言]、[Windows 10] 和 [64 位] & 選取 [下一步]](images/shm-fig17.png)
   
4. 選取 [ **USB 快閃磁碟機** ]，然後選取 **[下一步]**。

   ![選取 [USB 快閃磁碟機]，然後選取 [下一步]](images/shm-fig18.png)
   
5. 下載完成後，請選取 **[完成]**。

   ![選取 [完成]](images/shm-fig19.png)
   
6. 在 Surface Hub 2 上複製適用于 Windows 10 專業版與企業版的 SEMM 套件檔案和驅動程式及固件。MSI 至 USB 快閃記憶體磁片磁碟機 (**BOOTME**) 包含您的 Windows 10 影像：

    - DfciUpdate.dfi
    - 含有 SEMM 指紋的文字檔。 在此範例中 (： SurfaceUEFI_2020Aug25_1058.txt) 
    - Surface Hub 2 上的 Windows 10 專業版與企業版的驅動程式和固件 ( # A0) 

### 更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移

使用您的 **BOOTME** 磁片磁碟機來安裝 SEMM 套件檔案，並更新 UEFI，讓 Surface Hub 執行 Windows 10 專業版或企業版。 然後從 **BOOTME** 磁片磁碟機啟動以安裝 Windows 10。

1. 插入您的 **BOOTME** 磁片磁碟機，其中包含適用于 Surface Hub 2 的 Windows 10 專業版與企業版的 SEMM 套件檔案、驅動程式和固件。MSI 和 Windows 10 在 Surface Hub 2 的 USB-A 埠上安裝檔案。  

2. 若要引導至 UEFI：

   1. 第一次關閉 () Surface Hub 2 的關閉電源。
   1. 按住 [ **音量 +** ]，然後按下再放開 [ **電源** ] 按鈕。
   1. 保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。
   
      ![保留 holdling 的音量 +，直到 UEFI 功能表出現為止](images/shm-fig20.png)
      
3. 當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (強烈建議) ）。

   ![裝置重新開機後，請輸入您的 UEFI paassword](images/shm-fig22.png)
   
4. 在 UEFI 功能表中，選取**Management**[  >  **從 USB 安裝**管理元件]。

   ![選取 [管理] & 從 USB 安裝](images/shm-fig21.png)
   
5. 選取 [ **立即重新開機**]，如下所示。 裝置將會重新開機，並在畫面中間顯示白色4方形標誌，然後將它關閉。

   ![選取 [立即重新開機]](images/shm-fig25.png)
   
6. 按下並放開電源按鈕，會顯示紅色畫面，提示您啟用 Surface Enterprise 管理模式。 

7. 輸入您的兩個字元的 **憑證指紋**，您的 **UEFI 設定密碼** ，然後選取 **[確定]**。

   ![輸入2個字元的憑證指紋](images/shm-fig23.png)
 
   > [!NOTE]
   > 一旦您在裝置上啟用 SEMM，就會套用新的 UEFI 設定 **EnableOSMigration** 。 您將無法再存取 Windows 10 小組，必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。 

8. 裝置將會重新開機，在畫面中間顯示白色4方形標誌，然後再按一次將它關閉

### 安裝 Windows 10 專業版或企業版

1. 如果您的可引導 Windows 10 專業版或企業版磁片磁碟機不在 Surface Hub 2 USB-A 埠中，請將它立即插入，然後按下再放開電源按鈕。

2. 裝置將會啟動，您會在畫面中間看到白色的4方形，然後您會在白色四個方形標誌下方看到旋轉的圓形。

3. 如果裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置電源 (拔下電源線，然後再插回) 。 重新插入電源線之後，裝置會在幾秒後啟動至畫面中間的白色4方形標誌，或者，您可以按下並放開電源按鈕來重新開啟裝置。 在螢幕中間看到4方塊標誌之後，按住 [音量] 按鈕，直到您看到位於白色四個方形標誌下方的旋轉圓形。
 
   ![從 USB 啟動至 Windows 10](images/shm-fig26.png)
   
4. 當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或企業版 (版本1903或) 更新版本。

### 安裝 Surface Hub 2 驅動程式和固件

 - 為了確保您的裝置擁有所有最新的更新和驅動程式，請 [在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 Enterprise 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。
 
### 後續步驟

若要將 Surface Hub 2 完整設定為個人生產力裝置，請參閱在 [Surface Hub 2 上設定 Windows 10 專業版或企業版](surface-hub-2-post-install.md)。

> [!NOTE]
>如果遵循這份檔中所述的步驟無法將您的裝置遷移至 Windows 10 專業版或 Surface Hub 2 Enterprise，請與 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)聯繫。

### 回退至 Windows 10 團隊

如果您想要將裝置還原至 Windows 10 小組，請參閱 [重設及恢復 Surface Hub 2 秒](surface-hub-2s-recover-reset.md)

## 版本歷程記錄

| 版本 | 日期               | 描述                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| 向量. 1.1  | 2020年9月15日 | 在簡介中放入其他記事，說明安裝新作業系統的授權需求。 |
| 向量. 1.0  | 2020年9月1日  | 新文章                                                                                           |
