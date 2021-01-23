---
title: 移轉到 Windows 10 專業版或 Surface Hub 2 企業版
description: 如何從位於 Surface Hub 2 的 Windows 10 團隊遷移到 Windows 10 專業版或 Windows 10 Enterprise。
keywords: Surface Hub 桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: d7ecee2ca66640b054efc106191d12c1844b90a1
ms.sourcegitcommit: 1bc22f7343af9b1b1b8b375d540adee2af68e693
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/23/2021
ms.locfileid: "11297636"
---
# 移轉到 Windows 10 專業版或 Surface Hub 2 企業版

- [文章版本歷程記錄](#version-history)

Surface Hub 2 與已安裝 Windows 10 的小組。 此自訂版本的 Windows 10 有利於在會議室環境中共同作業。 您現在可以改為執行 Windows 10 專業版或企業版來使用 Surface Hub 2，就像任何其他電腦一樣。

> [!IMPORTANT]
> 此遷移程式需要您遵循本文所述的特定程式。 繼續之前，請先閱讀 [解決方案元件](#solution-components) 及 [遷移和安裝工作流程](#migration-and-installation-workflow-summary)。

> [!NOTE]
> 當您安裝 Windows 10 專業版或企業版時，您需要與現有的 Windows 10 小組授權不同的新授權。

使用不同的電腦和可下載的 *SURFACE UEFI 配置介面* 工具，從 Windows 10 團隊開始遷移。 此工具會建立一個套件，其中包含您套用至 Surface Hub 2 秒的新 UEFI 設定。  

Surface UEFI 配置處理常式在 (SEMM) 中，成為 Surface Enterprise 管理模式的介面。 它可集中管理公司環境中的 Surface 裝置上的固件設定。 如需詳細資訊，請參閱 [Microsoft Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。
 
## 解決方案元件

- 執行 Windows 10 小組的 Surface Hub 2 秒裝置
- 運行 Windows 10 的個別裝置
- 用於建立 SEMM 套件的 Surface UEFI 設定檔工具
- Windows 10 專業版或企業版作業系統影像、版本1903或更新版本
- 兩個有 16 GB 儲存空間的 USB 磁片磁碟機，FAT32 格式
- 在 Surface Hub 2 中，Windows 10 專業版與企業版的驅動程式與固件，在 Microsoft Windows 安裝程式 (的 MSI) 檔案
- 網際網路連線
- 影像處理方案 (選用) 
 
## 遷移和安裝工作流程摘要

| 步驟  | 動作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| sr-1 | [驗證 Surface Hub 2 上的 UEFI 版本](#verify-the-uefi-version-on-surface-hub-2s)。                                  | UEFI 版本必須是 *694.2938.768.0* 或更新版本。                                                                                                                                                                                                                                                                                                                                                      |
| pplx-2 | [下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件。](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 在 [ **[表面工具](https://www.microsoft.com/download/details.aspx?id=46703)** ] 頁面上 </a> ，選取 [ **下載**]。 然後選取並下載 **SURFACE UEFI 設定檔 MSI**檔案，並將它安裝在不同的電腦上。 此外，請下載 [適用于 Surface Hub 2 MSI 檔案的 Windows 10 專業版與企業作業系統的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。</a> 儲存此套件以供在步驟5使用。 |
| 3 | [準備 SEMM 憑證。](#prepare-the-semm-certificate)                                                                          | 準備運行 Surface UEFI 配置器所需的憑證，或使用您目前的憑證。                                                                                                                                                                                                                                                                                                      |
| 4 | [建立 SEMM 套件。](#create-a-semm-package)                                                                               | 啟動 Surface UEFI 設定檔以在 USB 磁片磁碟機上建立 SEMM 套件。 這個套件將包含您需要在 Surface Hub 2 的設定檔。 將這些 SEMM 套件檔案複製到您電腦上的資料夾。                                                                                                                                                                                          |
| 500 | [使用 Windows 10 影像、SEMM 套件以及驅動程式和固件載入 USB 快閃記憶體磁片磁碟機。](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 建立包含 Windows 10 影像的 USB 磁片磁碟機。 在這個範例中，磁片磁碟機名為 *BOOTME*。 在 Surface Hub 2 (的 Windows 10 專業版和 Enterprise OS 中新增驅動程式及固件，) 從步驟 2) 到 *BOOTME* 磁片的 SEMM (套件檔案。                                                                                                                                                                                                  |
| 6 | [更新 Surface Hub 2 的 UEFI，以啟用作業系統遷移。](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用 *BOOTME* 磁片磁碟機啟動 Surface Hub 2 至 UEFI 功能表，然後安裝 SEMM 套件。|
| utf-7 | [安裝 Windows 10 專業版或企業版。](#install-windows-10-pro-or-enterprise)                                        | 使用 *BOOTME* 磁片磁碟機來安裝 Windows 10 專業版或企業版本1903或更新版本。                                                                                                                                                                                                                                                                                 |
| 型 | [安裝適用于 Windows 10 專業版與企業版的驅動程式和固件。](#install-surface-hub-2-drivers-and-firmware)                                        | 若要確保您的裝置擁有所有最新的更新和驅動程式，請 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 在 Surface Hub 2 MSI 檔案上安裝 Windows 10 專業版和企業版 OS 的驅動程式和固件。</a>                                                                                                                                                                                                                                                                                  |
| 9 | [將 Surface Hub 秒設定為個人生產力裝置。](#configure-recommended-settings)                                        |  啟用建議的設定和應用程式，以將 Surface Hub 秒優化為個人生產力裝置。                                                                                                                                                                                                                                                                    |

### 驗證 Surface Hub 2 上的 UEFI 版本

在您將 Surface Hub 從 Windows 10 小組遷移至 Windows 10 桌上出版前，您需要 UEFI 版本 *694.2938.768.0* 或更新版本。
 
**若要在您的系統上驗證 UEFI 版本：**

1. 在 Surface Hub 2 的 [首頁] 頁面上，選取 [**開始**]，然後在 [**所有應用程式**]  >  **表面**) 開啟 [Surface app] (。

2. 選取 **您的 surface** 以顯示 Surface Hub 的相關資訊，包括裝置上目前的 UEFI 版本。 
   - 如果 UEFI 版本是 *694.2938.768.0* 或更新版本，如下列影像所示，您可以建立 SEMM 套件來啟用作業系統遷移。

       ![螢幕擷取畫面顯示 Surface app 中的 [您的 Surface] 頁面。](images/shm-fig1.png)
 
   - 如果 UEFI 版本早于版本 *694.2938.768.0*，請使用下列其中一種方法來取得較新的版本
   
#### 透過 Windows Update 更新 UEFI

1. 在 Surface Hub 2 秒，請以系統 **管理員**身分登入。

    >[!Note]
    > 如果您不知道您的使用者名稱或系統管理員密碼，您必須重設裝置。 如需詳細資訊，請參閱 [重設及恢復 Surface Hub 2 秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-recover-reset)。

1. 移至 [**所有應用程式**]  >  **設定**[  >  **更新與安全性**]  >  **Windows update**，然後安裝所有更新。
1. 重新開機裝置。
1. 使用 Surface app 驗證 UEFI 版本。 如果 UEFI 版本不是版本 *694.2938.768.0* 或更新版本，請重複這些步驟，或使用下列程式來取得最新的 UEFI 版本。

#### 透過裸機復原 (BMR) 影像來更新 UEFI

1.  移至 [ [surface](https://support.microsoft.com/surfacerecoveryimage) 復原] 網站，然後選取 [ **Surface Hub 2 秒**]。
3.  輸入您的中樞序列值。 它位於中樞背面的電源連接旁邊。
4.  按照指示，透過安裝 Windows 10 Team 2020 更新，將影像下載到格式化的 USB 磁片磁碟機上。
5.  更新之後，裝置會在 (OOBE) 設定中輸入現成的體驗。 您不需要完成設定。 UEFI 版本已更新。 請改為按住電源按鈕，直到螢幕關閉為止，再關閉裝置電源。

### 下載 Surface UEFI 配置器和 Surface Hub 2 驅動程式與固件

在不同的電腦上，請遵循下列步驟：

1. 在 [ <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> 表面工具] 頁面上 </a> ，選取 [ **下載**]。  
1. 選取並下載 Surface UEFI 設定檔 MSI 檔案，並將它安裝在不同的電腦上。 安裝 Windows 10 小組版時，Surface UEFI 組態工具無法在 Surface Hub 2 上執行。

1. 下載 [Surface Hub 2 驅動程式和固件 Windows 安裝程式 MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案。 當您安裝新的作業系統時，您將會用到這個檔案。

### 準備 SEMM 憑證

如果您尚未使用 Surface UEFI 配置器，您必須準備證書。 這個憑證可確保在裝置註冊 SEMM 之後，您只能使用以核准憑證建立的套件來修改 UEFI 設定。

您取得憑證的方式取決於貴組織的規模或複雜度。

- 企業組織通常會維持自己的基礎結構，以根據標準安全慣例產生證書。

- 中型企業及其他人通常選擇從合作夥伴提供者取得憑證。 對於不具備 IT 專業人員或缺乏專門 IT 安全小組的組織而言，建議使用此選項。

- 或者，您也可以使用 PowerShell 腳本來產生自我簽署憑證。 如需詳細資訊，請參閱 [企業管理模式證書需求](https://docs.microsoft.com/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 或者，您可以使用 PowerShell 建立您自己的憑證。 如需詳細資訊，請參閱 [新的 SelfSignedCertificate](https://docs.microsoft.com/powershell/module/pkiclient/new-selfsignedcertificate) 檔。

Surface UEFI 設定檔建立的 SEMM 套件必須以憑證加以保護。 憑證會驗證設定檔的簽名，然後才能套用 UEFI 設定。 如需詳細資訊，請參閱 [SEMM](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 檔。
 
### 建立 SEMM 套件

1. 在另一部電腦上，安裝您先前下載的 Surface UEFI 組態工具。

1. 開啟 Surface UEFI 配置器，然後選取 [ **開始**]。

   ![Surface UEFI 配置器開始畫面。](images/shm-fig2.png)
   
1. 選取 [ **Surface 裝置**]，然後選取 **[下一步]**。

   ![螢幕擷取畫面顯示已選取 [Surface 裝置] 選項。](images/shm-fig3.png)
  
1. 選取 [設定 **套件**]。

   ![螢幕擷取畫面顯示已選取 [選取配置套件]。](images/shm-fig4.png)
  
1. 選取 [ **憑證保護**]。

   ![螢幕擷取畫面顯示如何選擇 [選取憑證保護]。](images/shm-fig5.png)

   系統會提示您新增憑證 .pfx 檔案。

   ![螢幕擷取畫面顯示在何處新增您的憑證檔案。](images/shm-fig6.png)
   
1. 輸入您的憑證密碼，然後選取 **[確定]**。

   ![螢幕擷取畫面顯示用於輸入並確認您的憑證密碼的欄位。](images/shm-fig7.png)

1. 選取 [ **密碼保護** ]，將密碼新增至 Surface UEFI。 每當您啟動至 UEFI 時，就會需要此密碼。 *我們強烈建議您設定要在 Surface Hub 的2秒使用的 UEFI 密碼。*

   ![螢幕擷取畫面顯示在何處選取密碼保護。](images/shm-fig8.png)
   
1. 設定 UEFI 密碼，然後選取 **[確定]**。

   > [!IMPORTANT]
   > 將密碼儲存在可供管理 Surface Hub 之 IT 系統管理員存取的安全位置。 *如果此密碼遺失，就無法復原。*

   ![螢幕擷取畫面顯示您設定 UEFI 密碼的位置。](images/shm-fig9.png)

1. 選取 [ **Surface Hub 2 秒**]，然後選取 **[下一步]**。

    ![螢幕擷取畫面顯示在何處選取 Surface Hub 2 到2。](images/shm-fig10.png)
   
1. 再次選取 **[下一步]** 。

    ![螢幕擷取畫面顯示如何選取 [選擇哪些元件] 下的 [下一步]。](images/shm-fig10a.png)

1. 若要允許安裝 Windows 10 專業版或企業版，請開啟 **EnableOsMigration**，然後選取 **[下一步]**。

    ![螢幕擷取畫面顯示如何選取 [啟用 O S] 遷移。](images/shm-fig11.png)
    
    ![螢幕擷取畫面顯示如何將啟用 OS 遷移的位置設定為 [開啟]。](images/shm-fig12.png)

### 管理 SEMM 登記

將裝置註冊至 SEMM 會影響您可以管理它的方式。 例如，在您套用 SEMM 套件之後，所有的 UEFI 設定都無法在裝置的 UEFI 功能表中 (鎖定) 。 其他設定（例如 **IPv6 FOR PXE 啟動** ）的預設值也無法使用。

若要在完成遷移後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。 如果您套用另一個 SEMM 套件來變更 UEFI 設定，則在建立新的 SEMM 套件時，您必須使用原始證書。 使用 UEFI 組態工具工具，並將 **EnableOSMigration** *關閉* (*不在) 的原始* 遷移步驟中。

#### 如果您與合作夥伴合作

如果您的公司 outsources Surface Hub 2 遷移至 Windows 10 專業版或企業版，您可能會想要讓合作夥伴將 SEMM 憑證、SEMM 套件和 UEFI 密碼轉讓給您。 或者，在您遷移中心之後，您可以立即取消將其從 SEMM 取消註冊。 此步驟可讓您對 UEFI 進行本機管理，並將裝置傳輸至另一方。 但我們還是強烈建議您使用 UEFI 密碼，這可以在遷移之後進行設定。 若要深入瞭解，請參閱 [管理 SURFACE UEFI 設定](https://docs.microsoft.com/surface/manage-surface-uefi-settings)。 

#### 回退至 Windows 10 團隊

如果您選擇在進行遷移之後將裝置還原至 Windows 10 小組，請 [參閱本文稍後所述](#to-roll-back-to-windows-10-team)，我們建議您先取消從 SEMM 取消中樞。 若要深入瞭解，請參閱 [從 SEMM 取消註冊 Surface 裝置](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。

#### 將 SEMM 套件儲存至 USB 磁片磁碟機

1. 將 USB 磁片磁碟機連線至您的電腦。
1. 選擇 [ **中心2秒**]，然後選取 **[下一步]**。

   ![螢幕擷取畫面顯示在何處選取中心2秒](images/shm-fig13.png)

   > [!WARNING]
   > 在建立 SEMM 套件時，USB 磁片磁碟機上的所有現有資料都會被清除。 在您建立 SEMM 套件之前，請先從 USB 磁片磁碟機移除任何您需要的檔案。
   
1. 選取 [ **建立**]。

   ![螢幕擷取畫面顯示要選取組建的位置。](images/shm-fig14.png)

1. 捕獲此頁面的螢幕擷取畫面，然後選取 [ **結束**]。 您的 SEMM 套件現已準備就緒。 它包含 SEMM 套件 *DfciUpdate. dfi* ，以及包含 SEMM *指紋*的文字檔，也就是憑證指紋的最後兩個字元。

   ![螢幕擷取畫面顯示要選取結束的位置。](images/shm-fig15.png)
   
4. 儲存憑證指紋的最後兩個字元。 當您在 Surface Hub 2 上套用套件時，您必須使用這些字元來啟用 SEMM。

### 使用 Windows 10 影像、SEMM 套件及 Surface Hub 2 驅動程式和固件載入 USB 快閃磁碟機

您可以使用下列其中一個選項，在版本 *1903* 或更新版本) 中安裝 Windows 10 專業版或企業版影像 (：

- 您目前的影像解決方案。

- [Surface 部署加速器](https://docs.microsoft.com/surface/microsoft-surface-deployment-accelerator)。 使用這個工具來建立可引導的 Windows 10 影像。 影像可以包含所有目前的 Windows 10 更新、Microsoft Office、其他 app，以及所需的驅動程式和固件。

- 包含 Windows 10 專業版或企業版影像的 USB 快閃記憶體磁片磁碟機。 然後在 Surface Hub 2 上安裝 [適用于 Windows 10 專業版與企業版的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974) 。
 
下列步驟說明如何從安裝媒體建立 USB 快閃記憶體磁片磁碟機，然後新增 SEMM 套件檔案，以及 Windows 10 專業版和企業作業系統在 Surface Hub 2 MSI 檔案中的驅動程式與固件。 如果您使用其他部署方法，請移至 [Surface Hub 2 上的更新 UEFI，以啟用本文的作業系統遷移](#update-uefi-on-surface-hub-2s-to-enable-os-migration) 一節。

> [!NOTE]
> 完成安裝之後，您需要適用于 Windows 10 專業版或 Windows 10 Enterprise 的有效授權，與現有的 Windows 10 小組授權不同。

1. 若要建立 Windows 10 專業版安裝，請按照指示下載 [windows 10](https://www.microsoft.com/software-download/windows10)中的媒體建立工具。 若要下載 Windows 10 企業版，請移至 [Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。

1. 插入新的 USB 儲存空間磁片磁碟機。
1. 開啟 [媒體建立工具]，選取 [ **建立安裝媒體**]，然後選取 **[下一步]**。

   ![螢幕擷取畫面顯示建立安裝媒體的選項。](images/shm-fig16.png)
   
3. 選取 [語言]，然後選取 [ **Windows 10** ] 和 [ **64 (x64) **]。 然後選取 **[下一步]**。

   ![螢幕擷取畫面顯示您選取語言、O S 及架構類型的位置。](images/shm-fig17.png)
   
4. 選取 [ **USB 快閃記憶體磁片磁碟機**]，然後選取 **[下一步]**。

   ![螢幕擷取畫面顯示如何選取 [U S B] 快閃記憶體磁片磁碟機。](images/shm-fig18.png)
   
5. 下載完成後，請選取 **[完成]**。

   ![顯示 U S B 磁片磁碟機已準備就緒且包含 [完成] 按鈕的畫面。](images/shm-fig19.png)
   
6. 在 Surface Hub 2 上複製 SEMM 套件檔案和 Windows 10 專業版作業系統的驅動程式及固件， (MSI 檔案) 到包含您 Windows 10 影像 (*BOOTME*) 的 USB 快閃記憶體磁片磁碟機根目錄。 BOOTME USB 磁片磁碟機將包含：

    - 您的 Windows 10 可引導影像。
    
    - 複製到 USB 磁片磁碟機根目錄的 SEMM 套件檔案：
    
      - *DfciUpdate dfi*。
      - 包含 SEMM 指紋的文字檔。  (在這個範例中，檔案是 *SurfaceUEFI_2020Aug25_1058.txt*。 ) 自動產生的日期時間戳記會對應到您使用 Surface UEFI 設定檔建立檔案的日期。

   - Surface Hub 2 上的 Windows 10 專業版與 Enterprise OS 的驅動程式和固件 ( # A0) 。 將此檔案複製到 USB 磁片磁碟機的根目錄。

### 更新 Surface Hub 2 的 UEFI 以啟用作業系統遷移

1. 將您的 BOOTME 磁片磁碟機插入 Surface Hub 2 的 USB-A 埠。 如需其所需內容的清單，請參閱上一節。

1. 若要引導至 UEFI：

   1. 關閉) Surface Hub 2 的 (關閉。
   1. 按住 [ **音量 +**]，然後按下再放開 [電源] 按鈕。 保留 [ **音量 +** ]，直到 UEFI 功能表出現為止。
   
      ![[繪圖] 會顯示 [音量] 和 [電源] 按鈕。](images/shm-fig20.png)
      
3. 當裝置重新開機時，請輸入您先前所建立的 UEFI 密碼（如果適用 (建議) ）。

   ![系統密碼] 畫面。](images/shm-fig22.png)
   
4. 從 [UEFI] 功能表中，選取 [ **管理**]。 然後選取 [  **從 USB 安裝**]。

   ![螢幕擷取畫面顯示要選取管理的位置，然後按一下 [從 U S B 安裝]。](images/shm-fig21.png)
   
5. 選取 [ **立即重新開機**]，如下圖所示。 裝置會重新啟動。 它會在視窗中間顯示白色 Microsoft 標誌，然後關閉。

   ![螢幕擷取畫面顯示一則訊息，提示您重新開機。](images/shm-fig25.png)
   
6. 按下並放開 [電源] 按鈕。 在出現的紅色對話方塊中，選擇 [啟用 Surface Enterprise 管理模式]。

7. 輸入您的雙字元憑證指紋及您的 UEFI 設定密碼。 然後選取 **[確定]**。

   ![螢幕擷取畫面顯示 [確認啟用] 對話方塊，您可以在此輸入雙字元憑證指紋及您的 UEFI 設定密碼。](images/shm-fig23.png)
 
   > [!NOTE]
   > 在裝置上啟用 SEMM 之後，就會套用新的 UEFI 設定 **EnableOSMigration** 。 您不能再存取 Windows 10 小組。 相反地，您必須繼續進行下一個步驟，並安裝 Windows 10 專業版或 Windows 10 Enterprise。

   裝置會重新開機。 它會在畫面中間顯示白色標誌，然後再次關閉。

### 安裝 Windows 10 專業版或企業版

1. 如果您的可引導 Windows 10 專業版或企業版磁碟機尚不在 Surface Hub 2 USB-A 埠中，請立即插入。 然後按下並放開 [電源] 按鈕。

    裝置啟動時，您會在畫面中間看到白色標誌。 然後旋轉的圓圈會出現在白色標誌下方。

3. 如果 Surface 裝置不會自動引導至 USB 磁片磁碟機，請關閉裝置 (拔下電源線，然後再插回) 。 再次插入電源線之後，裝置會在幾秒後啟動。 然後，您會在畫面中間看到白色標誌。

    如果裝置沒有開啟，請按下並放開 [電源] 按鈕。 在畫面中間看到標誌之後，按住 [音量] 按鈕，直到您看到白色標誌下方的旋轉圓形。
 
   ![[音量] 和 [電源] 按鈕的圖片。](images/shm-fig26.png)
   
4. 當 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10 專業版或 Enterprise (版本1903或) 更新版本。

### 安裝 Surface Hub 2 驅動程式和固件

若要確保 Surface Hub 2 是最新版本，請安裝 [適用于 Windows 10 專業版與企業版的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。 然後重新開機裝置。 讓表面保持開啟一個小時，然後再次重新開機。 第二次重新開機時，系統不會提示您。 這種暫停和額外的重新開機可確保固件已完全更新。
 
## 設定建議的設定

若要將 Surface Hub 秒設定為個人生產力裝置，請參閱在 [Surface Hub 2 上設定 Windows 10 專業版或企業版](surface-hub-2-post-install.md)。

> [!NOTE]
>如果您無法成功將裝置遷移至 Windows 10 專業版或 Surface Hub 的 Enterprise，請依照本文所述的步驟，接觸 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

## 回退至 Windows 10 團隊

如果您想要將裝置還原至 Windows 10 小組，請參閱 [重設及恢復 Surface Hub 2 秒](surface-hub-2s-recover-reset.md)。

> [!NOTE]
> 在您回滾至 Windows 10 團隊之前，建議您先從 SEMM 取消對 Surface Hub 的註冊。 若要深入瞭解，請參閱 [從 SEMM 取消註冊 Surface 裝置](https://docs.microsoft.com/surface/unenroll-surface-devices-from-semm)。

## 版本歷程記錄

下表摘要列出本文所做的變更。

| 版本 | 日期               | 說明                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| 向量. 1.4  | 2020年12月14日 | 提供有關安裝 MSI 檔案（適用于 Surface Hub 2 的 Windows 10 專業版和 Enterprise OS）的 [詳細資訊](#install-surface-hub-2-drivers-and-firmware) ，說明您可能需要重新開機第二次，視系統的狀態而定。                                                          |
| 向量. 1.3  | 2020年12月3日 | 更新了有關 [管理 SEMM 註冊](#manage-semm-enrollment)的指導方針。                                                       |
| 向量. 1.2  | 2020年9月29日 | 針對可用性意見反應的各種更新。                                                        |
| 向量. 1.1  | 2020年9月15日 | 在簡介中放置了說明安裝新作業系統的授權需求。 |
| 向量. 1.0  | 2020年9月1日  | 新文章。                                                                                           |
