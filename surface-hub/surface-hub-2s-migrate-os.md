---
title: 移轉到 Windows 10 專業版或 Surface Hub 2 企業版
description: 如何從 2 Windows 10 團隊版 2 Surface Hub到 Windows 10 專業版 或 Windows 10 企業版。
keywords: Surface Hub桌面Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
ms.openlocfilehash: bdf39a2e664aa9abbd2fbf4790aec0b04c084f64
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911878"
---
# <a name="migrate-to-windows-10-pro-or-enterprise-on-surface-hub-2"></a>移轉到 Windows 10 專業版或 Surface Hub 2 企業版

- [文章版本歷程記錄](#version-history)

Surface Hub 2S 隨附Windows 10 團隊版安裝。 此自訂版本的 Windows 10可促進在會議室環境中共同合作。 現在，您可以改為Windows 10 專業版或Enterprise 2S Surface Hub使用您的 2S，就像任何其他電腦一樣。

> [!IMPORTANT]
> 此移移程式要求您遵循本文所述的特定程式。 在您繼續之前，請閱讀[解決方案元件及](#solution-components)[移移和安裝工作流程](#migration-and-installation-workflow-summary)。

> [!NOTE]
> 當您在 Windows 10 專業版 Enterprise 2S 上Surface Hub或裝置時，您需要與裝置所提供的現有 Windows 10 團隊版 授權不同的新授權。

使用另一部Windows 10 團隊版和可下載*的 Surface UEFI Configurator*工具，從伺服器開始移移。 此工具會建立一個套件，其中包含套用至 2S Surface Hub UEFI 設定。  

Surface UEFI Configurator 在 SEMM 管理模式中Enterprise介面 (介面) 。 它可在公司環境中集中管理 Surface 裝置上的固件設定。 詳細資訊，請參閱[Microsoft Surface Enterprise管理模式](/surface/surface-enterprise-management-mode)。
 
## <a name="solution-components"></a>解決方案元件

- Surface Hub 2S 裝置Windows 10 團隊版
- 個別裝置Windows 10
- Surface UEFI Configurator 工具可建立 SEMM 套件
- Windows 10 專業版或Enterprise OS 映射、版本 1903 或更新版本
- 兩個 USB 磁片磁碟機的儲存空間為 16 GB，採用 FAT32 格式
- Microsoft 2 Windows 10 專業版安裝程式Enterprise的驅動程式和Surface Hub Windows MSI () 
- 網際網路連線
- 影像解決方案 (選) 
 
## <a name="migration-and-installation-workflow-summary"></a>移移和安裝工作流程摘要

| 步驟  | 動作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [驗證 2S 上的 UEFI Surface Hub版本](#verify-the-uefi-version-on-surface-hub-2s)。                                  | UEFI 版本必須是版本 *694.2938.768.0* 或更新版本。                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [下載 Surface UEFI 組Surface Hub 2 個驅動程式和固件。](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 在 IT**[版 Surface 工具頁面上](https://www.microsoft.com/download/details.aspx?id=46703)** </a> ，選取 下載****。 然後選取並下載 **Surface UEFI Configurator MSI 檔案**，然後將它安裝在另一部電腦上安裝。 此外，在[2 MSI](https://www.microsoft.com/download/details.aspx?id=101974)檔案上下載 Windows 10 專業版 Enterprise OS Surface Hub驅動程式和固件。</a> 儲存此套件以用於步驟 5。 |
| 3 | [準備 SEMM 憑證。](#prepare-the-semm-certificate)                                                                          | 準備執行 Surface UEFI Configurator 所需的憑證，或使用您目前的憑證。                                                                                                                                                                                                                                                                                                      |
| 4 | [建立 SEMM 套件。](#create-a-semm-package)                                                                               | 啟動 Surface UEFI Configurator，在 USB 磁碟機上建立 SEMM 套件。 此套件會包含您需要套用至 2S Surface Hub的組Surface Hub檔案。 將這些 SEMM 套件檔案複製到您 PC 上的資料夾。                                                                                                                                                                                          |
| 5 | [載入 USB 快閃Windows 10圖像、SEMM 套件、驅動程式和固件。](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 建立包含影像的 USB Windows 10磁碟機。 在此範例中，該磁碟機名為 *BOOTME*。 在步驟) 2 Surface Hub (2 (上新增 Windows 10 專業版 和 Enterprise OS 的驅動程式和固件，以及步驟 4 (的 SEMM 套件檔案) 至*BOOTME*磁碟機。                                                                                                                                                                                                  |
| 6 | [更新 2S Surface Hub上的 UEFI，以啟用 OS 移移。](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用*BOOTME*磁碟機將 Surface Hub 2S 引導至 UEFI 功能表並安裝 SEMM 套件。|
| 7 | [安裝Windows 10 專業版或Enterprise。](#install-windows-10-pro-or-enterprise)                                        | 使用*BOOTME*磁碟機Windows 10 專業版或Enterprise版本 1903 或更新版本。                                                                                                                                                                                                                                                                                 |
| 8 | [安裝適用于 Windows 10 專業版 和 Enterprise 的驅動程式和Enterprise。](#install-surface-hub-2-drivers-and-firmware)                                        | 若要確保您的裝置擁有所有最新的更新和驅動程式，請于 2 MSI 檔案上安裝 Windows 10 專業版 和 Enterprise OS Surface Hub <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 驅動程式和固件。</a>                                                                                                                                                                                                                                                                                  |
| 9 | [將 Surface Hub 2S 設定為個人生產力裝置。](#configure-recommended-settings)                                        |  啟用建議的設定和應用程式，Surface Hub個人生產力裝置來優化 2S。                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>在 2S 上驗證 UEFI Surface Hub版本

在您將 Surface Hub Windows 10 團隊版 Windows 10電腦版之前，您需要 UEFI 版本*694.2938.768.0*或更新版本。
 
**若要驗證您系統的 UEFI 版本：**

1. 在 Surface Hub 2S 首頁上，選取開始 **，然後**開啟 Surface 應用程式 (所有**App**  >  **Surface**) 。

2. 選取**您的 Surface**以顯示Surface Hub，包括裝置上目前的 UEFI 版本。 
   - 如果 UEFI 版本 *是 694.2938.768.0* 或更新版本，如下圖所示，您可以建立 SEMM 套件來啟用 OS 移移。

       ![螢幕擷取畫面顯示 Surface 應用程式中的 「您的 Surface」頁面。](images/shm-fig1.png)
 
   - 如果 UEFI 版本早于版本 *694.2938.768.0，* 請使用下列其中一種方法取得較新版本
   
#### <a name="update-uefi-via-windows-update"></a>透過更新更新 UEFI Windows UEFI

1. 在 2S Surface Hub上，以系統管理員**的登錄。**

    >[!Note]
    > 如果您不知道使用者名稱或系統管理員密碼，則需要重設裝置。 詳細資訊請參閱[2S 的重設Surface Hub復原](/surface-hub/surface-hub-2s-recover-reset)。

1. 請前往所有**應用程式**  >  **設定**  >  **更新**和安全性Windows  >  **更新**，並安裝所有更新。
1. 重新開機裝置。
1. 使用 Surface 應用程式驗證 UEFI 版本。 如果 UEFI 版本不是版本 *694.2938.768.0* 或更新版本，請重複這些步驟，或使用下列程式取得最新的 UEFI 版本。

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>透過裸露金屬修復更新 UEFI (BMR) 圖像

1.  前往[Surface 修復網站，](https://support.microsoft.com/surfacerecoveryimage)然後選取**Surface Hub 2S**。
3.  輸入您的中樞序號。 它位於電源連接旁的中樞背面。
4.  請遵循指示，安裝 2020 Update Windows 10 團隊版格式化的 USB 磁碟機。
5.  更新之後，裝置在 OOBE 設定中 (即) 體驗。 您不需要完成設定。 UEFI 版本已經更新。 而是按住電源按鈕，直到螢幕關閉，以關閉裝置電源。

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>下載 Surface UEFI 組Surface Hub 2 個驅動程式和固件

在個別的 PC 上，請遵循下列步驟：

1. 在 IT <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> 版 Surface 工具頁面上 </a> ，選取 下載 。 ****  
1. 選取並下載 Surface UEFI Configurator MSI 檔案，然後安裝在另一部電腦上安裝。 Surface UEFI Configurator 工具無法于安裝 Surface Hub 2S Windows 10 團隊版上執行。

1. 下載安裝程式 MSI Surface Hub 2 個驅動程式[和Windows的驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=101974)。 當您安裝新作業系統時，會使用此檔案。

### <a name="prepare-the-semm-certificate"></a>準備 SEMM 憑證

如果您之前尚未使用 Surface UEFI Configurator，則需要準備憑證。 此憑證可確保在裝置註冊 SEMM 之後，您只能使用使用核准憑證所建立套件來修改 UEFI 設定。

取得憑證的方式取決於貴組織的大小或複雜度：

- Enterprise組織通常會維護自己的基礎結構，以根據標準安全性做法產生憑證。

- 中型企業和其他企業通常會選擇從合作夥伴提供者取得憑證。 對於沒有太多 IT 專業知識或缺少專屬 IT 安全小組的組織，建議您使用此選項。

- 或者，您可以使用 PowerShell 腳本產生自我簽署的憑證。 詳細資訊，請參閱 Surface [Enterprise管理模式憑證需求](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 或者，您可以使用 PowerShell 建立您自己的憑證。 詳細資訊請參閱自我 [簽署憑證](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) 檔。

Surface UEFI Configurator 所建立之 SEMM 套件必須以憑證保護。 憑證會先驗證組組檔案的簽章，再適用 UEFI 設定。 詳細資訊請參閱 [SEMM](/surface/surface-enterprise-management-mode) 檔。
 
### <a name="create-a-semm-package"></a>建立 SEMM 套件

1. 在個別的電腦上安裝您先前下載的 Surface UEFI Configurator 工具。

1. 開啟 Surface UEFI Configurator， **然後選取**開始 。

   ![Surface UEFI Configurator 開始畫面。](images/shm-fig2.png)
   
1. 選取 **Surface Devices，** 然後選取下 **一步**。

   ![螢幕擷取畫面顯示已選取的 Surface Devices 選項。](images/shm-fig3.png)
  
1. 選取 **組組套件**。

   ![螢幕擷取畫面顯示已選取 「選取組組套件」。](images/shm-fig4.png)
  
1. 選取 **憑證保護**。

   ![螢幕擷取畫面顯示是選擇 「選取憑證保護」。](images/shm-fig5.png)

   系統會提示您新增憑證 .pfx 檔案。

   ![螢幕擷取畫面顯示要新增憑證檔案的位置。](images/shm-fig6.png)
   
1. 輸入您的憑證密碼， **然後選取確定**。

   ![螢幕擷取畫面顯示要輸入並確認憑證密碼的欄位。](images/shm-fig7.png)

1. 選取 **密碼保護** 以在 Surface UEFI 中新增密碼。 每次啟動至 UEFI 時，您都需要這個密碼。 *我們強烈建議您設定 UEFI 密碼，以在 2S Surface Hub使用。*

   ![螢幕擷取畫面顯示選取密碼保護位置。](images/shm-fig8.png)
   
1. 設定 UEFI 密碼， **然後選取確定**。

   > [!IMPORTANT]
   > 將密碼儲存在安全的位置，讓管理密碼的 IT 系統管理員能夠Surface Hub。 *如果這個密碼遺失，就無法復原。*

   ![螢幕擷取畫面顯示您設定 UEFI 密碼的地方。](images/shm-fig9.png)

1. 選取**Surface Hub 2S，** 然後選取 下**一步**。

    ![螢幕擷取畫面顯示選取 2S Surface Hub位置。](images/shm-fig10.png)
   
1. 再次 **選取下一** 步。

    ![螢幕擷取畫面顯示以選取 「選擇哪些元件」下的下一步。](images/shm-fig10a.png)

1. 若要允許安裝Windows 10 專業版或Enterprise，請開啟**EnableOsMigration，** 然後選取下**一步**。

    ![螢幕擷取畫面顯示在何處選取啟用 O S 移移。](images/shm-fig11.png)
    
    ![螢幕擷取畫面顯示將啟用作業系統移移設定至何處。](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>管理 SEMM 註冊

將裝置註冊到 SEMM 會影響您的管理方式。 例如，套用 SEMM 套件之後，所有 UEFI 設定 (裝置 UEFI) 鎖定的設定。 其他設定 ，例如 **IPv6 for PXE Boot 的** 預設值也無法使用。

若要在移移完成後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。 如果您套用另一個 SEMM 套件來變更 UEFI 設定，則當您建立新的 SEMM 套件時，必須使用原始憑證。 使用 UEFI Configurator 工具，讓**EnableOSMigration**** 關閉 (** 無法如原始移) 。

#### <a name="if-you-work-with-partners"></a>如果您與合作夥伴合作

如果您的公司將 Surface Hub 2 移轉到 Windows 10 專業版 或 Enterprise，您可能會想要讓合作夥伴將 SEMM 憑證、SEMM 套件和 UEFI 密碼移轉給您。 或者，在遷移中樞之後，您可以立即從 SEMM 取消註冊。 此步驟可讓 UEFI 的本地管理，以及將裝置移轉給另一方。 但我們仍強烈建議您使用 UEFI 密碼，此密碼可在移移之後進行配置。 若要深入瞭解，請參閱 [管理 Surface UEFI 設定](/surface/manage-surface-uefi-settings)。 

#### <a name="to-roll-back-to-windows-10-team"></a>若要返回Windows 10 團隊版

如果您選擇在移Windows 10 團隊版之後將裝置還原至其他裝置，我們建議您先從[](#to-roll-back-to-windows-10-team)SEMM 取消註冊 Hub。 若要深入瞭解，請參閱 [從 SEMM 取消](/surface/unenroll-surface-devices-from-semm)註冊 Surface 裝置。

#### <a name="save-the-semm-package-to-a-usb-drive"></a>將 SEMM 套件儲存到 USB 磁碟機

1. 連線 USB 磁碟機到您的電腦。
1. 選擇 **中心 2S，** 然後選取下 **一步**。

   ![螢幕擷取畫面顯示選取中心 2S 位置。](images/shm-fig13.png)

   > [!WARNING]
   > 建立 SEMM 套件時，USB 磁碟機上的所有現有資料都會清除。 在建立 SEMM 套件之前，請從 USB 磁碟機移除任何您需要的檔案。
   
1. 選取 **建立**。

   ![螢幕擷取畫面顯示選取建立位置。](images/shm-fig14.png)

1. 捕獲此頁面的螢幕擷取畫面， **然後選取**結束 。 您的 SEMM 套件現在已準備就緒。 它包含 SEMM 套件 *DfciUpdate.dfi，* 以及包含 *SEMM*指紋的文字檔 ，這是憑證指紋的最後兩個字元。

   ![螢幕擷取畫面顯示選取結束位置。](images/shm-fig15.png)
   
4. 儲存憑證指紋的最後兩個字元。 當您在 2S 上套用套件時，您需要這些字元Surface Hub SEMM。

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>載入 USB 快閃Windows 10圖像、SEMM 套件，Surface Hub 2 個驅動程式和固件

您可以使用下列Windows 10 專業版Enterprise， (*版本 1903*或) 安裝影像：

- 您目前的影像解決方案。

- [Surface 部署快速鍵](/surface/microsoft-surface-deployment-accelerator)。 使用此工具建立可啟動Windows 10圖像。 影像可以包含所有目前Windows 10更新、Microsoft Office、其他應用程式，以及所需的驅動程式和固件。

- 包含圖像或Windows 10 專業版或Enterprise快Enterprise磁碟機。 在設定 OOBE Wi-Fi之後，才能使用此選項 (OOBE) 使用。 設定完成後，在裝置上Surface Hub [2](https://www.microsoft.com/download/details.aspx?id=101974)個驅動程式和Windows 10 專業版Enterprise和Enterprise。
 
下列步驟顯示如何從安裝媒體建立 USB 快閃磁碟機，然後在 2 MSI 檔案上新增 Windows 10 專業版 和 Enterprise OS 的 SEMM 套件檔案Surface Hub驅動程式和Surface Hub。 如果您使用其他部署方法，請前往[2S Surface Hub更新 UEFI 以啟用本文](#update-uefi-on-surface-hub-2s-to-enable-os-migration)的 OS 移轉到一節。

> [!NOTE]
> 安裝完成後，您需要現有授權Windows 10 專業版或Windows 10 企業版授權Windows 10 團隊版授權。

1. 若要建立Windows 10 專業版，請按照指示下載媒體建立工具[，Windows 10。](https://www.microsoft.com/software-download/windows10) 若要下載Windows 10 企業版，請前往[Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。

1. 插入新的 USB 儲存檔。
1. 開啟媒體建立工具，選取 **建立安裝媒體**，然後選取下 **一步**。

   ![螢幕擷取畫面顯示建立安裝媒體的選項。](images/shm-fig16.png)
   
3. 選取語言，**然後選取**Windows 10 x64 (**64 位) 。** 然後選取下 **一步**。

   ![螢幕擷取畫面顯示您選取語言、O S 版本和架構類型的地方。](images/shm-fig17.png)
   
4. 選取 **USB 快閃磁碟機**，然後選取下 **一步**。

   ![螢幕擷取畫面顯示在何處選取 US B 快閃磁碟機。](images/shm-fig18.png)
   
5. 下載完成後，選取 **完成**。

   ![畫面報告美國硬碟已準備就緒，並包含完成按鈕。](images/shm-fig19.png)
   
6. 將 MSI 檔案) Surface Hub (2 Windows 10 專業版 和 Enterprise OS 上的 SEMM 套件檔案和驅動程式和固件複製到包含 Windows 10 影像的 USB 快閃磁碟機 (*BOOTME*) 根目錄。 BOOTME USB 磁碟機會包含：

    - 您的Windows 10可啟動的影像。
    
    - 複製至 USB 磁碟機根目錄的 SEMM 套件檔案：
    
      - *DfciUpdate.dfi*。
      - 包含 SEMM 指紋的文字檔。  (在此範例中，檔案是 *SurfaceUEFI_2020Aug25_1058.txt*.) 自動產生的日期時間戳記會對應到您使用 Surface UEFI Configurator 建立檔案的日期。

   - 2 Windows 10 專業版 2 Enterprise 上的 Surface Hub 和 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi) 。 將這個檔案複製到 USB 磁碟機的根目錄。

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>更新 2S Surface Hub UEFI 以啟用 OS 移移

1. 將 BOOTME 磁碟機插入 2S Surface Hub USB-A 埠。 有關所需內容的清單，請參閱上一節。

1. 若要啟動至 UEFI：

   1. 關閉您的 (2S) 關閉Surface Hub關閉。
   1. 按住 Volume **+**，然後按並放開電源按鈕。 持續按住 **音量 +** 直到 UEFI 功能表出現。
   
      ![繪圖會顯示音量和電源按鈕。](images/shm-fig20.png)
      
3. 當裝置重新開機時，輸入您先前所建立之 UEFI 密碼 ，如果適用 (建議) 。

   ![系統密碼畫面。](images/shm-fig22.png)
   
4. 從 UEFI 功能表中， **選取**管理 。 然後選取  **從 USB 安裝**。

   ![螢幕擷取畫面顯示在何處選取管理，然後選取「從美國 B 安裝」。](images/shm-fig21.png)
   
5. 選取 **立即重新開機**，如下圖所示。 裝置會重新啟動。 它會在視窗中央顯示白色 Microsoft 標誌，然後關閉。

   ![螢幕擷取畫面顯示一則訊息，提示您重新開機。](images/shm-fig25.png)
   
6. 按並放開電源按鈕。 在出現的紅色對話方塊中，選擇啟用 Surface Enterprise管理模式。

7. 輸入雙字元憑證指紋和 UEFI 設定密碼。 然後選取 **確定**。

   ![螢幕擷取畫面顯示確認啟用對話方塊，您可以在此輸入雙字元憑證指紋和 UEFI 設定密碼。](images/shm-fig23.png)
 
   > [!NOTE]
   > 在裝置上啟用 SEMM 之後，會採用新的 UEFI 設定**EnableOSMigration。** 您無法再存取Windows 10 團隊版。 您必須繼續下一個步驟，並安裝 Windows 10 專業版 或 Windows 10 企業版。

   裝置會重新開機。 它會在畫面中央顯示白色標誌，然後再次關閉。

### <a name="install-windows-10-pro-or-enterprise"></a>安裝Windows 10 專業版或Enterprise

1. 如果您的可啟動Windows 10 專業版或Enterprise磁碟機尚未在 2 USB-A 埠Surface Hub，請現在插入。 然後按並放開電源按鈕。

    當裝置啟動時，畫面中央就會看到白色標誌。 接著，白色標誌下方會出現旋轉的圓圈。

3. 如果 Surface 裝置無法自動啟動至 USB 磁碟機，請關閉裝置電源 (拔下電源線，然後將它插回) 。 再次插入電源線後，裝置應該幾秒鐘後應該會啟動。 接著，畫面中央就會看到白色標誌。

    如果裝置未開啟，請按並放開電源按鈕。 在畫面中間看到標誌之後，請按住向下捲動按鈕，直到您看到白色標誌下方的旋轉圓圈。
 
   ![音量和電源按鈕的圖片。](images/shm-fig26.png)
   
4. 當立即使用 OOBE (開始) 時，請按照指示安裝 Windows 10 專業版 或 Enterprise (版本 1903 或更新版本) 。

### <a name="install-surface-hub-2-drivers-and-firmware"></a>安裝 Surface Hub 2 個驅動程式和固件

若要確保您的 Surface Hub 2 為最新版本，請安裝適用于 Windows 10 專業版 和 Enterprise[的驅動程式和Enterprise。](https://www.microsoft.com/download/details.aspx?id=101974) 然後重新開機裝置。 將 Surface 保持開啟一小時，然後再重新開機一次。 系統不會提示您進行第二次重新開機。 此暫停和額外重新開機可確保完整更新的固件。
 
## <a name="configure-recommended-settings"></a>設定建議設定

若要將 Surface Hub 2S 設定為個人生產力裝置，請參閱在 Windows 10 專業版[2](surface-hub-2-post-install.md)Enterprise設定Surface Hub裝置。

> [!NOTE]
>如果您無法按照本文所述步驟Windows 10 專業版或 Enterprise 2 Surface Hub成功將裝置遷移到 Surface Hub 或 Surface Hub，請Surface Hub[客戶支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)。

## <a name="to-roll-back-to-windows-10-team"></a>若要返回Windows 10 團隊版

如果您想要將裝置還原為 Windows 10 團隊版，請參閱重設及復原[Surface Hub 2S](surface-hub-2s-recover-reset.md)。

> [!NOTE]
> 在您卷回Windows 10 團隊版之前，建議您先從 SEMM 取消Surface Hub卷Surface Hub卷。 若要深入瞭解，請參閱 [從 SEMM 取消](/surface/unenroll-surface-devices-from-semm)註冊 Surface 裝置。

## <a name="version-history"></a>版本歷程記錄

下表摘要列出本文的變更。

| 版本 | 日期               | 描述                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| V。 1.4  | 2020 年 12 月 14 日 | 提供有關[安裝](#install-surface-hub-2-drivers-and-firmware)MSI 檔案的進一步資訊，以安裝 「Surface Hub 2 上的 Windows 10 專業版 和 Enterprise OS 的驅動程式和固件」，並告知您可能需要視系統狀態進行第二次重新開機。                                                          |
| V。 1.3  | 2020 年 12 月 3 日 | 更新為管理 [SEMM 註冊的指南](#manage-semm-enrollment)。                                                       |
| V。 1.2  | 2020 年 9 月 29 日 | 解決可用性意見回饋的雜項更新。                                                        |
| V。 1.1  | 2020 年 9 月 15 日 | 在簡介中新增一個說明，說明安裝新作業系統的授權需求。 |
| V。 1.0  | 2020 年 9 月 1 日  | 新文章。                                                                                           |
