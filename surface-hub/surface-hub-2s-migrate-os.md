---
title: 移轉到 Windows 10 專業版或 Surface Hub 2 企業版
description: 本文將說明如何從 Surface Hub 2 上的 Windows 10 團隊遷移到 Windows 10 專業版或 Windows 10 Enterprise。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 713bd2e76f144b4dca7c0fad5c584b06ea12b0b5
ms.sourcegitcommit: 3ca1d1bc77452acca914d0af03e252ee260ebf1a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "11154140"
---
# 移轉到 Windows 10 專業版或 Surface Hub 2 企業版

Surface Hub 秒是預先預先安裝了 Windows 10 團隊。 此自訂版本的 Windows 10 是設計來協助在會議室環境中共同作業。 現在，您可以選擇執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。 

> [!IMPORTANT]
>與典型的升級或遷移不同，此程式必須遵循說明性程式，如本文所述。 繼續之前，請先查看 [解決方案元件](#solution-components) 與 [遷移及安裝工作流程](#migration-and-installation-workflow-summary) 。


> [!NOTE]
> 當您安裝 Windows 10 專業版或企業版時，您需要與現有的 Windows 10 小組授權不同的新授權。 


使用個別的電腦和可下載的工具 *SURFACE UEFI 配置*器，從 Windows 10 小組開始遷移。 使用此工具來建立包含您套用至 Surface Hub 2 秒的新 UEFI 設定的套件。  

Surface UEFI 配置處理常式在 (SEMM) 中，成為 Surface Enterprise 管理模式的介面。 它旨在協助集中管理公司環境中的 Surface 裝置上的固件設定。 如需詳細資訊，請參閱 [MICROSOFT SEMM 檔](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。
 

## 解決方案元件

- 執行 Windows 10 小組作業系統的 Surface Hub 2 秒裝置
- 運行 Windows 10 的個別裝置
- 用於建立 SEMM 套件的 Surface UEFI 設定檔工具
- Windows 10 專業版或企業版作業系統影像、版本1903或更新版本
- 兩個有 16 GB 儲存空間的 USB 磁片磁碟機，FAT32 格式
- Windows 10 專業版和企業作業系統在 Surface Hub 2 上的驅動程式與固件，Microsoft Windows Installer (的 MSI) 檔案
- 網際網路連線
- 影像處理方案 (選用) 

 
## 遷移和安裝工作流程摘要

| 步驟  | 動作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sr-1 | [確認 Surface Hub 2 上的 UEFI 版本符合最低需求。](#verify-uefi-version-on-surface-hub-2s-meets-minimum-requirements)                                  | 確定 UEFI 版本為694.2938.768.0 或更新版本。                                                                                                                                                                                                                                                                                                                                                      |
| pplx-2 | [下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件。](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 在 [ [**表面工具**](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面上，選取 [ **下載**]。 然後選取並下載 **SURFACE UEFI 配置器。MSI** 檔案，並將它安裝在不同的電腦上。 下載 [適用于 Surface Hub 2 MSI 檔案的 Windows 10 專業版和企業版 OS 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。 將它儲存在步驟5中以供使用。 |
| 3 | [準備 SEMM 憑證。](#prepare-the-semm-certificate)                                                                          | 準備運行 Surface UEFI 配置器所需的憑證。 或使用您目前的憑證。                                                                                                                                                                                                                                                                                                      |
| 4 | [建立 SEMM 套件。](#create-a-semm-package)                                                                               | 啟動 Surface UEFI 設定檔以在 USB 磁片磁碟機上建立 SEMM 套件，這將包含您需要在 Surface Hub 2 上套用的配置檔案。 將這些 SEMM 套件檔案複製到您電腦上的資料夾。                                                                                                                                                                                          |
| 500 | [準備 USB 快閃記憶體磁片磁碟機，其中包含適用于 Surface Hub 2 的 windows 10 專業版與企業作業系統的 SEMM 套件、驅動程式和固件。](#prepare-a-usb-flash-drive-that-contains-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 建立包含 Windows 10 影像的單一 USB 磁片磁碟機。 在這個範例中，磁片磁碟機名為 *BOOTME*。 在 Surface Hub 2 (的 Windows 10 專業版與企業作業系統的驅動程式和固件，請 (步驟 2) 並 SEMM 套件檔案步驟 4) 移至 *BOOTME* 磁片磁碟機。                                                                                                                                                                                                  |
| 6 | [更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移。](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 *BOOTME* 磁片磁碟機來啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。|
| utf-7 | [安裝 Windows 10 專業版或企業版1903或更新版本。](#install-windows-10-pro-or-enterprise)                                        | 使用 *BOOTME* 磁片磁碟機來安裝 Windows 10 專業版或企業版本1903或更新版本。                                                                                                                                                                                                                                                                                 |
| 型 | [安裝適用于 Surface Hub 2 的 Windows 10 專業版和企業版作業系統的驅動程式和固件。](#install-surface-hub-2-drivers-and-firmware)                                        | 為了確保您的裝置擁有所有最新的更新和驅動程式，請 [在 Surface Hub 2 的 MSI 檔案上安裝 Windows 10 專業版和企業版 OS 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。                                                                                                                                                                                                                                                                                  |
| 9 | [將 Surface Hub 2 完整設定為個人生產力裝置。](#configure-recommended-settings)                                        |  啟用建議的設定和應用程式，以將 Surface Hub 秒優化為個人生產力裝置。                                                                                                                                                                                                                                                                    |

### 驗證 Surface Hub 2 上的 UEFI 版本是否符合最低需求

在您將 Surface Hub 從 Windows 10 小組遷移至 Windows 10 桌上出版前，您需要至少 *694.2938.768.0*的 UEFI 版本。
 
若要在您的系統上驗證 UEFI 版本：

1. 在 Surface Hub 2 的 [首頁] 頁面上，選取 [**開始**]，然後在 [**所有應用程式**]  >  **表面**) 開啟 [Surface app] (。

2. 選取 **您的 surface** 以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。 
   - 如果 UEFI 版本是 *694.2938.768.0* 或更新版本，如下列影像所示，您可以建立 SEMM 套件來啟用作業系統遷移。

       ![在 Surface app 中顯示您的 Surface 頁面的螢幕擷取畫面。](images/shm-fig1.png)
 
   - 如果 UEFI 版本早于 *694.2938.768.0*，請使用 Windows Update 取得目前的版本。

若要使用 Windows Update 來更新 UEFI：

1. 在 Surface Hub 2 秒，請以系統 **管理員**身分登入。 
    >[!Note]
    > 如果您不知道您的使用者名稱或系統管理員密碼，您必須重設裝置。 如需詳細資訊，請參閱 [重設及恢復 Surface Hub 2 秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)。

1. 移至 [**所有應用程式**設定] 的 [  >  **Settings**  >  **更新與安全性**]  >  **Windows update**，然後安裝所有更新。 
1. 重新開機裝置。 
1. 使用 Surface app 驗證 UEFI 版本。 
2. 重複這些步驟，直到 UEFI 版本為 *694.2938.768.0* 或更新版本。
3. 如果您在多次嘗試後沒看到更新的 UEFI，請核取 [ **更新歷程記錄** ] 並尋找任何失敗的固件安裝實例。 您可能需要重設裝置 (**設定**  >  **更新 & 安全**  >  **重設裝置**) 。

### 下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件

在不同的電腦上：

1. 在 [ [表面工具] 頁面](https://www.microsoft.com/download/details.aspx?id=46703)上，選取 [ **下載**]。  
1. 選取並下載 Surface UEFI 設定檔 MSI 檔案，並將它安裝在不同的電腦上。 安裝 Windows 10 小組版時，Surface UEFI 組態工具無法在 Surface Hub 2 上執行。

1. 下載 [Surface Hub 2 驅動程式和固件 Windows 安裝程式 MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案。 當您安裝新的作業系統時，您將會用到這個檔案。

### 準備 SEMM 憑證

如果您尚未使用 Surface UEFI 配置器，您必須準備證書。 這個憑證可確保在裝置註冊 SEMM 之後，您只能使用以核准憑證建立的套件來修改 UEFI 設定。 

您取得憑證的方式取決於貴組織的規模或複雜度。

- 企業組織通常會維持自己的基礎結構，以根據標準安全慣例產生證書。

- 中型企業及其他人可能選擇從合作夥伴提供者取得憑證。 對於沒有足夠 IT 專業知識或專門 IT 安全小組的組織，建議使用此選項。

- 或者，您也可以使用 PowerShell 腳本來產生自我簽署憑證。 如需詳細資訊，請參閱 [企業管理模式證書需求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 或者，您可以使用 PowerShell 建立您自己的憑證。 如需詳細資訊，請參閱 [新的 SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 檔。

Surface UEFI 設定檔建立的 SEMM 套件必須以憑證加以保護。 憑證會驗證設定檔的簽名，然後才能套用 UEFI 設定。 如需詳細資訊，請參閱 [SEMM 檔](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。
 
 
### 建立 SEMM 套件

1. 在另一部電腦上，安裝您先前下載的 Surface UEFI 組態工具。 

2. 開啟 Surface UEFI 配置器，然後選取 [ **開始**]。

   ![開啟 Surface UEFI 配置器。](images/shm-fig2.png)
   
3. 選取 [ **Surface 裝置**]，然後選取 **[下一步]**。

   ![選取 [Surface 裝置]。](images/shm-fig3.png)
  
4. 選取 [設定 **套件**]。

   ![選取 [設定套件]。](images/shm-fig4.png)
  
5. 選取 [ **憑證保護**]。

   ![選取 [憑證保護]。](images/shm-fig5.png)

   系統會提示您新增憑證 .pfx 檔案。

   ![新增您的憑證。](images/shm-fig6.png)
   
7. 輸入您的憑證密碼，然後選取 **[確定]**。

   ![輸入您的憑證密碼，然後選取 [確定]。](images/shm-fig7.png)

8. 選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。 每當您引導至 UEFI 時，就會需要此密碼。 我們 *強烈建議* 您設定要在 Surface Hub 的2秒使用的 UEFI 密碼。

   ![選取 [密碼保護]。](images/shm-fig8.png)
   
9. 設定 UEFI 密碼，然後選取 **[確定]**。

   > [!IMPORTANT]
   > 將密碼儲存在可供管理 Surface Hub 之 IT 系統管理員存取的安全位置。 如果密碼遺失，就無法復原。 

   ![輸入您的 UEFI 密碼。](images/shm-fig9.png)

10. 選取 [ **Surface Hub 2 秒**]，然後選取 **[下一步]**。

    ![選取 [Surface Hub 2 秒]。](images/shm-fig10.png)
   
11. 選取 **\[下一步\]**。

    ![選取 \[下一步\]。](images/shm-fig10a.png)

12. 若要允許安裝 Windows 10 專業版或企業版，請開啟 **EnableOsMigration**，然後選取 **[下一步]**。

    ![選取 [啟用 O S 遷移]。](images/shm-fig11.png)
    
    ![將 [啟用作業系統遷移] 設定為 [開啟]。](images/shm-fig12.png)

> [!NOTE]
> 在您套用 SEMM 套件之後，請在裝置的 UEFI 功能表中，所有的 UEFI 設定都無法使用 (鎖定) 。 其他設定（例如 **IPv6 FOR PXE 啟動** ）的預設值也無法使用。 
>
>若要在完成遷移後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。 如果您套用另一個 SEMM 套件來變更 UEFI 設定，則在建立新的 SEMM 套件時，您必須使用原始證書。 使用 UEFI 組態工具工具，並將 **EnableOSMigration** 關閉 (不在開啟，如原始的遷移步驟) 所示。

#### 將 SEMM 套件儲存至 USB 磁片磁碟機

1. 將 USB 磁片磁碟機連線至您的電腦。 
1. 選擇 [ **中心2秒**]，然後選取 **[下一步]**。

   ![選取 [USB]](images/shm-fig13.png)

   > [!WARNING]
   > 在建立 SEMM 套件時，會清除 USB 磁片磁碟機上的所有現有資料。 在建立 SEMM 套件之前，請先從您要儲存的 USB 磁片磁碟機中移除任何檔案。
   
2. 選取 [ **建立**]。

   ![選取 [建立]。](images/shm-fig14.png)

3. 捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。 您的 SEMM 套件現已準備就緒。 它包含 SEMM 套件 *DfciUpdate dfi* 和文字檔，其中包含 SEMM 指紋 (憑證的指紋) 中的最後兩個字元。

   ![選取 [結束]。](images/shm-fig15.png)
   
4. 儲存憑證指紋的最後兩個字元。 當您在 Surface Hub 2 上套用套件時，您必須使用這些字元來啟用 SEMM。

### 準備包含 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式與固件的 USB 快閃記憶體磁片磁碟機

您可以使用下列其中一個選項，在版本1903或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：

- 您目前的影像解決方案。

- [Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator)。 使用這個工具來建立可引導的 Windows 10 影像。 影像可以包含所有目前的 Windows 10 更新、Office、您選擇的其他應用程式，以及所需的驅動程式和固件。 

- 包含 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機。 然後 [在 Surface Hub 2 上安裝 Windows 10 專業版和企業版作業系統的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。
 
下列程式說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後新增 SEMM 套件檔案，以及 Windows 10 專業版的驅動程式和固件（Surface Hub 2 MSI 檔案）。 如果您使用的是其他部署方法，請前往 [Surface Hub 2 上的更新 UEFI，以啟用](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 本文中的 [作業系統遷移] 區段。

> [!NOTE]
> 完成安裝之後，您需要適用于 Windows 10 專業版或 Windows 10 Enterprise 的有效授權，與現有的 Windows 10 小組授權不同。

1. 若要建立 Windows 10 專業版安裝，請在 [ [**下載 windows 10**](https://www.microsoft.com/software-download/windows10) ] 頁面上，依照指示下載媒體建立工具。 若要下載 Windows 10 企業版，請移至 [Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。

2. 插入新的 USB 儲存空間磁片磁碟機。 
1. 開啟 [媒體建立工具]，選取 [ **建立安裝媒體**]，然後選取 **[下一步]**。

   ![建立安裝媒體。](images/shm-fig16.png)
   
3. 選取 [語言]，然後選擇 [ **Windows 10** ] 和 [ **64 位 (x64) **]。 然後選取 **[下一步]**。

   ![選取 [語言]，然後選擇 [Windows 10] 和 [64 位]。 然後選取 [下一步]。](images/shm-fig17.png)
   
4. 選取 [ **USB 快閃記憶體磁片磁碟機**]，然後選取 **[下一步]**。

   ![選取 [U S B 快閃記憶體磁碟機]，然後選取 [下一步]。](images/shm-fig18.png)
   
5. 下載完成後，請選取 **[完成]**。

   ![選取 [完成]。](images/shm-fig19.png)
   
6. 在 Surface Hub 2 上複製 SEMM 套件檔案和 Windows 10 專業版作業系統的驅動程式及固件， (MSI 檔案) 到包含您 Windows 10 影像 (*BOOTME*) 的 USB 快閃記憶體磁片磁碟機根目錄。 BOOTME USB 磁片磁碟機包含：

    - 您的 Windows 10 可引導影像。
    
    - SEMM 套件檔案 (複製到 USB 磁片磁碟機的根目錄) 。
    
      - *DfciUpdate dfi*。
      - 包含 SEMM 指紋的文字檔。  (在這個範例中，檔案是 *SurfaceUEFI_2020Aug25_1058.txt*。 ) 自動產生的日期時間戳記會對應到您使用 Surface UEFI 設定檔建立檔案的日期。

   - Surface Hub 2 上的 Windows 10 專業版與企業作業系統的驅動程式和固件 ( # A0) 。 將此檔案複製到 USB 磁片磁碟機的根目錄。

### 更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移

1. 將您的 BOOTME 硬碟插入到 Surface Hub 2 的 USB-A 埠。 如需檔案的清單，請參閱上一節。

2. 若要引導至 UEFI：

   1. 關閉) Surface Hub 2 的 (關閉。
   1. 按住 [ **音量 +**]，然後按下再放開 [電源] 按鈕。
   1. 保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。
   
      ![按住調高音量按鈕，直到 UEFI 功能表出現為止。](images/shm-fig20.png)
      
3. 當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (強烈建議) ）。

   ![輸入 UEFI 密碼。](images/shm-fig22.png)
   
4. 在 UEFI 功能表中，選取**Management**[  >  **從 USB 安裝**管理元件]。

   ![選取 [管理] 並從 U S B 安裝。](images/shm-fig21.png)
   
5. 選取 [ **立即重新開機**]，如下圖所示。 裝置會重新開機。 它會在視窗中間顯示白色 Microsoft 標誌，然後關閉。

   ![選取 [立即重新開機]。](images/shm-fig25.png)
   
6. 按下並放開 [電源] 按鈕。 在出現的紅色視窗中，啟動 Surface Enterprise 管理模式。 

7. 輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。 然後選取 **[確定]**。

   ![輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。](images/shm-fig23.png)
 
   > [!NOTE]
   > 在裝置上啟用 SEMM 之後，就會套用新的 UEFI 設定 **EnableOSMigration** 。 您將無法再存取 Windows 10 小組。 相反地，您必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。 

   裝置會重新開機。 它會在畫面中間顯示白色標誌，然後再次關閉。

### 安裝 Windows 10 專業版或企業版

1. 如果您的可引導 Windows 10 專業版或企業版磁碟機尚不在 Surface Hub 2 USB-A 埠中，請立即插入。 然後按下並放開 [電源] 按鈕。 

    裝置啟動時，您會在畫面中間看到白色標誌。 接著，您會看到白色標誌下方的旋轉圓形。

3. 如果裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置 (拔下電源線，然後再插回) 。 再次插入電源線之後，裝置會在幾秒後啟動。 然後，您會在畫面中間看到白色標誌。 

    如果裝置沒有開啟，請按下並放開 [電源] 按鈕。 在畫面中間看到標誌之後，按住 [音量] 按鈕，直到您看到白色標誌下方的旋轉圓形。
 
   ![從 U S B 磁片磁碟機啟動至 Windows 10。](images/shm-fig26.png)
   
4. 當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或 Enterprise (版本1903或) 更新版本。

### 安裝 Surface Hub 2 驅動程式和固件

為了確保您的裝置擁有所有最新的更新和驅動程式，請 [在 Surface Hub 2 上安裝適用于 Windows 10 專業版和 ENTERPRISE OS 的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。
 
## 設定建議的設定

若要將 Surface Hub 2 完整設定為個人生產力裝置，請參閱在 [Surface Hub 2 上設定 Windows 10 專業版或企業版](surface-hub-2-post-install.md)。

> [!NOTE]
>如果本文所述的步驟無法成功將您的裝置遷移至 Windows 10 專業版或 Surface Hub 2 的 Enterprise，請接觸 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

## 回退至 Windows 10 團隊

如果您想要將裝置還原至 Windows 10 小組，請參閱 [重設及恢復 Surface Hub 2 秒](surface-hub-2s-recover-reset.md)。

## 版本歷程記錄

下表摘要列出本文所做的變更。

| 版本 | 日期               | 描述                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| 向量. 1.2  | 2020年9月29日 | 針對可用性意見反應的各種更新。                                                        |
| 向量. 1.1  | 2020年9月15日 | 在簡介中放置了說明安裝新作業系統的授權需求。 |
| 向量. 1.0  | 2020年9月1日  | 新文章。                                                                                           |
