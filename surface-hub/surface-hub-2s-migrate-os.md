---
title: 在 Surface Hub 2 上移轉至 Windows 10/11 Pro 或 Enterprise
description: 如何從 Surface Hub 2 上的Windows 10 團隊版移轉至Windows 10 專業版或Windows 10 企業版。
keywords: Surface Hub桌面，Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/14/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S
- Windows 10
- Windows 11
ms.openlocfilehash: 7b221b6f8b4a7753a10dd974da47ce58af41d006
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497756"
---
# <a name="migrate-to-windows-1011-pro-or-enterprise-on-surface-hub-2"></a>在 Surface Hub 2 上移轉至 Windows 10/11 Pro 或 Enterprise

- [發行項版本歷程記錄](#version-history)

Surface Hub 2S 隨附Windows 10 團隊版安裝。 這個自訂版本的Windows 10有助於在會議室環境中共同作業。 您現在可以改為執行 Windows 10/11 Pro或Enterprise來使用Surface Hub 2S，就像任何其他電腦一樣。

> [!IMPORTANT]
> 此移轉程式需要您遵循本文所述的特定程式。 繼續之前，請先閱讀 [解決方案元件](#solution-components) 和 [移轉和安裝工作流程](#migration-and-installation-workflow-summary)。

> [!NOTE]
> 當您在 Surface Hub 2S 上安裝 Windows 10/11 Pro或Enterprise時，您需要與裝置提供的現有Windows 10 團隊版授權不同的新授權。

使用個別的電腦和可下載的*Surface UEFI Configurator*工具，從Windows 10 團隊版開始移轉。 此工具會建立套件，其中包含您套用至 Surface Hub 2S 的新 UEFI 設定。  

Surface UEFI Configurator 可作為 Surface Enterprise 管理模式的介面， (SEMM) 。 它可讓您集中管理公司環境中 Surface 裝置上的韌體設定。 如需詳細資訊，請[參閱 Microsoft Surface Enterprise管理模式](/surface/surface-enterprise-management-mode)。

## <a name="solution-components"></a>解決方案元件

- Surface Hub執行 Windows 10 團隊版 的 2S 裝置
- 個別執行Windows 10的裝置
- 用來建立 SEMM 套件的 Surface UEFI 設定器工具
- Windows 10/11 Pro或 Enterprise OS 映射 20H2 版或更新版本
- 兩個具有 16 GB 儲存體的 USB 磁片磁碟機，FAT32 格式
- Surface Hub 2 Microsoft Windows Installer (MSI) 檔案中Windows 10 專業版和Enterprise的驅動程式和韌體
- 網際網路連線
- 映射處理解決方案 (選擇性) 

## <a name="migration-and-installation-workflow-summary"></a>移轉和安裝工作流程摘要

| 步驟  | 動作                                                                                                 | 摘要                                                                                                                                                                                                                                                                                                                                                                                                  |
| - | ------------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1 | [確認 Surface Hub 2S 上的 UEFI 版本](#verify-the-uefi-version-on-surface-hub-2s)。                                  | UEFI 版本必須是 *694.2938.768.0* 版或更新版本。                                                                                                                                                                                                                                                                                                                                                      |
| 2 | [下載 Surface UEFI Configurator 和 Surface Hub 2 驅動程式和韌體。](#download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware)                             | 在 [ **[適用于 IT 的 Surface 工具]](https://www.microsoft.com/download/details.aspx?id=46703)** 頁面上 </a> ，選取 [ **下載]**。 然後選取並下載 **Surface UEFI 設定程式 MSI 檔案**，然後將它安裝在不同的電腦上。 此外，在[Surface Hub 2 MSI 檔案上下載適用于 Windows 10 專業版 和 Enterprise OS 的驅動程式和韌體](https://www.microsoft.com/download/details.aspx?id=101974)。</a> 儲存此套件以供步驟 5 使用。 |
| 3 | [準備 SEMM 憑證。](#prepare-the-semm-certificate)                                                                          | 準備執行 Surface UEFI 設定程式或使用目前憑證所需的憑證。                                                                                                                                                                                                                                                                                                      |
| 4 | [建立 SEMM 套件。](#create-a-semm-package)                                                                               | 啟動 Surface UEFI 設定程式，在 USB 磁片磁碟機上建立 SEMM 套件。 此套件將包含您需要在 Surface Hub 2S 上套用的組態檔。 將這些 SEMM 套件檔案複製到您電腦上的資料夾。                                                                                                                                                                                          |
| 5 | [使用Windows 10映射、SEMM 套件，以及驅動程式和韌體載入 USB 快閃磁片磁碟機。](#load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware) | 建立包含Windows 10映射的 USB 磁片磁碟機。 在此範例中，磁片磁碟機名為 *BOOTME*。 從步驟 2) ，在Surface Hub 2 (上新增 Windows 10 專業版 和 Enterprise OS 的驅動程式和韌體，以及從步驟 4) 到*BOOTME*磁片磁碟機 (的 SEMM 套件檔案。                                                                                                                                                                                                  |
| 6 | [更新 Surface Hub 2S 上的 UEFI，以啟用 OS 移轉。](#update-uefi-on-surface-hub-2s-to-enable-os-migration)                                              | 使用*BOOTME 磁*盤磁碟機將 Surface Hub 2S 開機至 UEFI 功能表，並安裝 SEMM 套件。|
| 7 | [安裝Windows 10 專業版或Enterprise。](#install-windows-1011-pro-or-enterprise)                                        | 使用*BOOTME 磁*盤磁碟機來安裝 Windows 10 專業版 或Enterprise *20H2*版或更新版本。                                                                                                                                                                                                                                                                                 |
| 8 | [安裝適用于 Windows 10 專業版 和 Enterprise 的驅動程式和韌體。](#install-surface-hub-2-drivers-and-firmware)                                        | 若要確保您的裝置具有所有最新的更新和驅動程式，請在 Surface Hub 2 MSI 檔案上安裝 <a href="https://www.microsoft.com/download/details.aspx?id=101974" target="_blank"> 適用于 Windows 10 專業版 和 Enterprise OS 的驅動程式和韌體。</a>                                                                                                                                                                                                                                                                                  |
| 9 | [將 Surface Hub 2S 設定為個人生產力裝置。](#configure-recommended-settings)                                        |  啟用建議的設定和應用程式，將Surface Hub 2S 優化為個人生產力裝置。                                                                                                                                                                                                                                                                    |

### <a name="verify-the-uefi-version-on-surface-hub-2s"></a>確認 Surface Hub 2S 上的 UEFI 版本

將Surface Hub從 Windows 10 團隊版 移轉至 Windows 10 Desktop 之前，您需要 UEFI *694.2938.768.0*版或更新版本。

**若要確認系統上的 UEFI 版本：**

1. 在 [Surface Hub 2S] 首頁上，選取 [**開始**]，然後開啟 [**所有應用程式**] (Surface 應用程式  >  **) **。

2. 選**取您的 Surface**以顯示Surface Hub的相關資訊，包括裝置上的目前 UEFI 版本。
   - 如果 UEFI 版本是 *694.2938.768.0* 或更新版本，如下圖所示，您可以建立 SEMM 套件來啟用 OS 移轉。

    ![顯示 Surface 應用程式中 [您的 Surface] 頁面的螢幕擷取畫面。](images/shm-fig1.png)

   - 如果 UEFI 版本早于 *694.2938.768.0 版*，請使用下列其中一種方法來取得較新的版本

#### <a name="update-uefi-via-windows-update"></a>透過 Windows Update 更新 UEFI

1. 在您的 Surface Hub 2S 上，以**系統管理員身分登入**。

    >[!Note]
    > 如果您不知道您的使用者名稱或系統管理員密碼，則必須重設裝置。 如需詳細資訊，請[參閱重設和復原Surface Hub 2S](/surface-hub/surface-hub-2s-recover-reset)。

1. 移至 **[所有應用程式**  >  **設定**  >  **更新和安全**  >  **性Windows Update**，然後安裝所有更新。
1. 重新開機裝置。
1. 使用 Surface 應用程式驗證 UEFI 版本。 如果 UEFI 版本不是 *694.2938.768.0* 版或更新版本，請重複這些步驟，或使用下列程式來取得最新的 UEFI 版本。

#### <a name="update-the-uefi-via-bare-metal-recovery-bmr-image"></a>透過裸機復原 (BMR) 映射更新 UEFI

1. 移至[Surface 復原網站](https://support.microsoft.com/surfacerecoveryimage)，然後選**取 [Surface Hub 2S]**。
3. 輸入您的中樞序號。 其位於電源連線旁的中樞背面。
4. 請遵循指示，安裝 Windows 10 團隊版 2020 Update，將映射下載到格式化的 USB 磁片磁碟機上。
5. 更新之後，裝置會進入全新體驗 (OOBE) 設定。 您不需要完成設定。 UEFI 版本已更新。 而是按住電源按鈕來關閉裝置電源，直到螢幕關閉為止。

### <a name="download-surface-uefi-configurator-and-surface-hub-2-drivers-and-firmware"></a>下載 Surface UEFI 設定程式，並Surface Hub 2 個驅動程式和韌體

在個別的電腦上，遵循下列步驟：

1. 在 [ <a href="https://www.microsoft.com/download/details.aspx?id=46703" target="_blank"> 適用于 IT 的 Surface 工具] 頁面上 </a> ，選取 [ **下載]**。  
1. 選取並下載 Surface UEFI 設定程式 MSI 檔案，並將其安裝在不同的電腦上。 安裝 Windows 10 團隊版 版本時，Surface UEFI Configurator 工具無法在Surface Hub 2S 上執行。

1. 下載[Surface Hub 2 驅動程式和韌體Windows安裝程式 MSI 檔案](https://www.microsoft.com/download/details.aspx?id=101974)。 當您安裝新的作業系統時，將會使用此檔案。

### <a name="prepare-the-semm-certificate"></a>準備 SEMM 憑證

如果您之前尚未使用 Surface UEFI 設定程式，則需要準備憑證。 此憑證可確保在 SEMM 中註冊裝置之後，您只能使用以核准憑證建立的套件來修改 UEFI 設定。

取得憑證的方式取決於組織的大小或複雜度：

- Enterprise組織通常會維護自己的基礎結構，以根據標準安全性做法來產生憑證。

- 中型企業和其他公司通常會選擇從合作夥伴提供者取得憑證。 對於沒有太多 IT 專業知識或缺乏專用 IT 安全性小組的組織，建議使用此選項。

- 或者，您可以使用 PowerShell 腳本來產生自我簽署憑證。 如需詳細資訊，請參閱[Surface Enterprise管理模式憑證需求](/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。 或者，您可以使用 PowerShell 建立自己的憑證。 如需詳細資訊，請參閱 [自我簽署憑證](/dotnet/core/additional-tools/self-signed-certificates-guide#create-a-self-signed-certificate) 檔。

Surface UEFI Configurator 建立的 SEMM 套件必須使用憑證來保護。 憑證會先驗證組態檔的簽章，才能套用 UEFI 設定。 如需詳細資訊，請參閱 [SEMM](/surface/surface-enterprise-management-mode) 檔。

### <a name="create-a-semm-package"></a>建立 SEMM 套件

1. 在另一台電腦上，安裝您稍早下載的 Surface UEFI 設定器工具。

1. 開啟 [Surface UEFI 設定程式]，然後選取 [ **啟動]**。

   ![Surface UEFI 設定程式開始畫面。](images/shm-fig2.png)

1. 選取 **[Surface 裝置**]，然後選取 [ **下一步]**。

   ![顯示已選取 [Surface 裝置] 選項的螢幕擷取畫面。](images/shm-fig3.png)
  
1. 選 **取 [組態套件]**。

   ![顯示已選取 [選取組態套件] 的螢幕擷取畫面。](images/shm-fig4.png)
  
1. 選 **取 [憑證保護]**。

   ![顯示選擇 [選取憑證保護] 的螢幕擷取畫面。](images/shm-fig5.png)

   系統會提示您新增憑證 .pfx 檔案。

   ![顯示要在何處新增憑證檔案的螢幕擷取畫面。](images/shm-fig6.png)

1. 輸入您的憑證密碼，然後選取 [ **確定]**。

   ![此螢幕擷取畫面顯示輸入並確認憑證密碼的欄位。](images/shm-fig7.png)

1. 選 **取 [密碼保護** ] 以將密碼新增至 Surface UEFI。 每當您開機到 UEFI 時，您將需要此密碼。 *強烈建議您設定要在 Surface Hub 2S 上使用的 UEFI 密碼。*

   ![顯示選取 [密碼保護] 位置的螢幕擷取畫面。](images/shm-fig8.png)

1. 設定 UEFI 密碼，然後選取 [ **確定]**。

   > [!IMPORTANT]
   > 將密碼儲存在管理Surface Hub的 IT 系統管理員可存取的安全位置。 *如果遺失此密碼，則無法復原。*

   ![此螢幕擷取畫面顯示您設定 UEFI 密碼的位置。](images/shm-fig9.png)

1. 選**取 [Surface Hub 2S**]，然後選取 [**下一步]**。

    ![此螢幕擷取畫面顯示在 2S Surface Hub選取位置。](images/shm-fig10.png)

1. 再次選取 **[下一步]** 。

    ![顯示在 [選擇哪些元件] 底下選取 [下一步] 的螢幕擷取畫面。](images/shm-fig10a.png)

1. 若要允許安裝 Windows 10/11 Pro或Enterprise，請開啟**EnableOsMigration**，然後選取 [**下一步]**。

    ![顯示選取 [啟用 O S 移轉] 位置的螢幕擷取畫面。](images/shm-fig11.png)

    ![顯示 [啟用 OS 移轉] 設定為開啟位置的螢幕擷取畫面。](images/shm-fig12.png)

### <a name="manage-semm-enrollment"></a>管理 SEMM 註冊

將裝置註冊到 SEMM 會影響您管理裝置的功能。 例如，套用 SEMM 套件之後，所有 UEFI 設定都無法使用， (鎖定) 裝置的 UEFI 功能表中。 也無法使用其他設定的預設值，例如 **PXE 開機的 IPv6** 。

若要在完成移轉之後變更 UEFI 設定，請套用另一個 SEMM 套件，或從 SEMM 取消註冊裝置。 如果您套用另一個 SEMM 套件來變更 UEFI 設定，您必須在建置新的 SEMM 套件時使用原始憑證。 使用 UEFI 設定器工具，並讓 **EnableOSMigration** *關閉* (不 *開啟* ，如同原始移轉步驟) 一樣。

#### <a name="if-you-work-with-partners"></a>如果您與合作夥伴合作

如果您的公司將Surface Hub 2 移轉外包給 Windows 10/11 Pro或Enterprise，您可能會想要讓合作夥伴將 SEMM 憑證、SEMM 套件和 UEFI 密碼傳送給您。 或者，在移轉中樞之後，您可以立即從 SEMM 取消註冊。 此步驟可啟用 UEFI 的本機管理，並將裝置傳輸至另一方。 但是，我們仍強烈建議您使用 UEFI 密碼，這可以在移轉之後設定。 若要深入瞭解，請 [參閱管理 Surface UEFI 設定](/surface/manage-surface-uefi-settings)。

#### <a name="to-roll-back-to-windows-10-team"></a>復原至 Windows 10 團隊版

如果您選擇在移轉後將裝置還原至 Windows 10 團隊版，[如本文稍後所述](#to-roll-back-to-windows-10-team)，建議您先從 SEMM 取消註冊中樞。 若要深入瞭解，請 [參閱從 SEMM 取消註冊 Surface 裝置](/surface/unenroll-surface-devices-from-semm)。

>[!WARNING]
>若要從 SEMM 取消註冊裝置，並還原 Surface UEFI 設定的使用者控制，您必須擁有 SEMM 憑證，該憑證是用來在 SEMM 中註冊裝置。 如果此憑證遺失或損毀，就無法從 SEMM 取消註冊。 據此備份並保護您的 SEMM 憑證。

#### <a name="save-the-semm-package-to-a-usb-drive"></a>將 SEMM 套件儲存至 USB 磁片磁碟機

1. 將 USB 磁片磁碟機連線到您的電腦。
1. 選擇 **[中樞 2S**]，然後選取 [ **下一步]**。

   ![此螢幕擷取畫面顯示選取中樞 2S 的位置。](images/shm-fig13.png)

   > [!WARNING]
   > 建置 SEMM 套件時，將會清除 USB 磁片磁碟機上的所有現有資料。 在建置 SEMM 套件之前，請從 USB 磁片磁碟機移除您需要的任何檔案。

1. 選 **取 [建置]**。

   ![顯示選取 [建置] 位置的螢幕擷取畫面。](images/shm-fig14.png)

1. 擷取此頁面的螢幕擷取畫面，然後選取 [ **結束]**。 您的 SEMM 套件現在已就緒。 它包含 SEMM 套件 *DfciUpdate.dfi* ，以及包含 SEMM *指紋*的文字檔，也就是憑證指紋的最後兩個字元。

   ![顯示選取 [結束] 位置的螢幕擷取畫面。](images/shm-fig15.png)

4. 儲存憑證指紋的最後兩個字元。 當您在 Surface Hub 2S 上套用套件時，您將需要這些字元來啟用 SEMM。

### <a name="load-a-usb-flash-drive-with-a-windows-10-image-semm-package-and-surface-hub-2-drivers-and-firmware"></a>使用Windows 10映射、SEMM 套件，以及Surface Hub 2 個驅動程式和韌體載入 USB 快閃磁片磁碟機

您可以使用下列其中一個選項，將 Windows 10/11 Pro或Enterprise映射安裝 (*20H2*版或更新版本) ：

- 您目前的映射處理解決方案。

- [Surface 部署加速器](/surface/microsoft-surface-deployment-accelerator)。 使用此工具建立可開機Windows 10映射。 映射可以包含所有目前的Windows 10更新、Microsoft Office、其他應用程式，以及必要的驅動程式和韌體。

- USB 快閃磁片磁碟機，其中包含Windows 10/11 Pro或Enterprise映射。 在全新體驗 (OOBE) 設定之前，此選項將無法使用Wi-Fi。 安裝完成後，請在裝置上安裝[Windows 10 專業版和Enterprise所需的Surface Hub 2 驅動程式和韌體](https://www.microsoft.com/download/details.aspx?id=101974)。

下列步驟示範如何從安裝媒體建立 USB 快閃磁片磁碟機，然後在 Surface Hub 2 MSI 檔案上新增適用于 Windows 10 專業版 和 Enterprise OS 的 SEMM 套件檔案和驅動程式和韌體。 如果您使用另一個部署方法，請移至本文[的更新 UEFI on Surface Hub 2S 以啟用 OS 移轉](#update-uefi-on-surface-hub-2s-to-enable-os-migration)一節。

> [!NOTE]
> 完成安裝之後，您將需要與現有Windows 10 團隊版授權不同的Windows 10 專業版或Windows 10 企業版的有效授權。

1. 若要建立Windows 10 專業版安裝，請遵循下載Windows 10下載媒體建立工具[的](https://www.microsoft.com/software-download/windows10)指示。 若要下載Windows 10 企業版，請移至[Microsoft 大量授權服務中心](https://www.microsoft.com/licensing/servicecenter/default.aspx)。

1. 插入新的 USB 存放磁片磁碟機。
1. 開啟媒體建立工具，選取 [ **建立安裝媒體**]，然後選取 [ **下一步]**。

   ![此螢幕擷取畫面顯示建立安裝媒體的選項。](images/shm-fig16.png)

3. 選取語言，然後選**取 Windows 10**和**64 位 (x64) **。 然後選取 [ **下一步]**。

   ![此螢幕擷取畫面顯示您選取語言、O S 版本和架構類型的位置。](images/shm-fig17.png)

4. 選 **取 [USB 快閃磁片磁碟機**]，然後選取 [ **下一步]**。

   ![此螢幕擷取畫面顯示選取 U S B 快閃磁片磁碟機的位置。](images/shm-fig18.png)

5. 下載完成時，選取 [ **完成]**。

   ![螢幕報告 U S B 磁片磁碟機已就緒，並包含 [完成] 按鈕。](images/shm-fig19.png)

6. 將 SURFACE HUB 2 上的 SEMM 套件檔案和Windows 10 專業版和 Enterprise OS 的驅動程式和韌體， (MSI 檔案) 複製到包含您Windows 10映射的 USB 快閃磁片磁碟機 (*BOOTME*) 的根目錄。 BOOTME USB 磁片磁碟機將包含：

    - 您的Windows 10可開機映射。

    - 複製到 USB 磁片磁碟機根目錄的 SEMM 套件檔案：

      - *DfciUpdate.dfi*。
      - 包含 SEMM 指紋的文字檔。  (在此範例中，檔案 *SurfaceUEFI_2020Aug25_1058.txt*.) 自動產生的日期時間戳記會對應至您使用 Surface UEFI Configurator 建立檔案的日期。

   - Surface Hub 2 (SurfaceHub2S_Win10_18362_20.082.25682.0.msi) 上適用于 Windows 10 專業版 和 Enterprise OS 的驅動程式和韌體。 將此檔案複製到 USB 磁片磁碟機的根目錄。

### <a name="update-uefi-on-surface-hub-2s-to-enable-os-migration"></a>更新 Surface Hub 2S 上的 UEFI 以啟用 OS 移轉

1. 將您的 BOOTME 磁片磁碟機插入 Surface Hub 2S 上的 USB-A 埠。 如需其必要內容的清單，請參閱上一節。

1. 若要開機進入 UEFI：

   1. 關閉 (關閉) Surface Hub 2S。
   1. 按住 **Volume +**，然後按下並放開電源按鈕。 保留 **磁片區 +** 直到出現 UEFI 功能表為止。

      ![繪圖顯示音量和電源按鈕。](images/shm-fig20.png)

3. 當裝置重新開機時，如果適用，請輸入您稍早建立的 UEFI 密碼， (建議) 。

   ![系統密碼畫面。](images/shm-fig22.png)

4. 從 [UEFI] 功能表中，選取 [ **管理]**。 然後  **選取 [從 USB 安裝]**。

   ![此螢幕擷取畫面顯示選取 [管理]，然後選取 [從 U S B 安裝] 的位置。](images/shm-fig21.png)

5. 選 **取 [立即重新開機**]，如下圖所示。 裝置會重新啟動。 它會在視窗中間顯示白色 Microsoft 標誌，然後關閉。

   ![顯示訊息的螢幕擷取畫面，提示您重新開機。](images/shm-fig25.png)

6. 按下並放開電源按鈕。 在出現的紅色對話方塊中，選擇啟用 Surface Enterprise管理模式。

7. 輸入您的雙字元憑證指紋和 UEFI 設定密碼。 然後選取 **[確定]**。

   ![顯示 [確認啟用] 對話方塊的螢幕擷取畫面，您會在其中輸入雙字元憑證指紋和 UEFI 設定密碼。](images/shm-fig23.png)

   > [!NOTE]
   > 在裝置上啟用 SEMM 之後，會套用新的 UEFI 設定 **EnableOSMigration** 。 您無法再存取Windows 10 團隊版。 相反地，您必須繼續進行下一個步驟，並安裝Windows 10 專業版或Windows 10 企業版。

   裝置重新開機。 它會在畫面中間顯示白色標誌，然後再次關閉。

### <a name="install-windows-1011-pro-or-enterprise"></a>安裝 Windows 10/11 Pro 或 Enterprise

1. 如果您的可開機Windows 10/11 Pro或Enterprise磁片磁碟機尚未在 Surface Hub 2 USB-A 埠中，請立即插入。 然後按下並放開電源按鈕。

    當裝置啟動時，您會在畫面中間看到白色標誌。 接著會在白色標誌下方顯示旋轉圓圈。

3. 如果 Surface 裝置不會自動開機到 USB 磁片磁碟機，請關閉裝置電源 (拔除電源線，然後將它插入) 。 再次插入電源線之後，裝置應該會在幾秒鐘後開機。 然後您會在畫面中間看到白色標誌。

    如果裝置未開啟，請按下並放開電源按鈕。 在畫面中間看到標誌之後，按住 [音量向下] 按鈕，直到您看到白色標誌下方的旋轉圓形為止。

   ![磁片區和電源按鈕的圖片。](images/shm-fig26.png)

4. 當全新體驗 (OOBE) 安裝程式啟動時，請依照指示安裝 Windows 10/11 Pro或Enterprise (*20H2*版或更新版本) 。

### <a name="install-surface-hub-2-drivers-and-firmware"></a>安裝 Surface Hub 2 驅動程式和韌體

若要確保您的Surface Hub 2 是最新的，請安裝[適用于Windows 10 專業版和Enterprise的驅動程式和韌體](https://www.microsoft.com/download/details.aspx?id=101974)。 然後重新開機裝置。 將 Surface 保持開啟一小時，然後重新開機。 系統不會提示您進行第二次重新開機。 此暫停和額外重新開機可確保韌體已完全更新。

## <a name="configure-recommended-settings"></a>設定建議的設定

若要將 Surface Hub 2S 設定為個人生產力裝置，請[參閱在 Surface Hub 2 上設定 Windows 10/11 Pro或Enterprise](surface-hub-2-post-install.md)。

> [!NOTE]
>如果您無法依照本文所述的步驟，成功將裝置移轉至 Windows 10/11 Pro或Enterprise Surface Hub 2，請[連絡 Surface Hub 支援。](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)

## <a name="to-roll-back-to-windows-10-team"></a>復原至 Windows 10 團隊版

如果您想要將裝置還原至Windows 10 團隊版，請參閱[重設和復原Surface Hub 2S](surface-hub-2s-recover-reset.md)。

> [!NOTE]
> 復原至 Windows 10 團隊版 之前，建議您先從 SEMM 取消註冊Surface Hub。 若要深入瞭解，請 [參閱從 SEMM 取消註冊 Surface 裝置](/surface/unenroll-surface-devices-from-semm)。

## <a name="version-history"></a>版本歷程記錄

下表摘要說明本文的變更。

| 版本 | 日期               | 描述                                                                                           |
| ------- | ------------------ | ----------------------------------------------------------------------------------------------------- |
| V。 1.5  | 2021 年 12 月 1 日  | 已更新以顯示對Windows 11的支援
| V。 1.4  | 2020 年 12 月 14 日 | 提供有關在 Surface Hub 2 上安裝適用于 Windows 10 專業版 和 Enterprise OS 的驅動程式和韌體的 MSI 檔案的[進一步資訊](#install-surface-hub-2-drivers-and-firmware)，建議您可能需要根據系統狀態進行第二次重新開機。                                                          |
| V。 1.3  | 2020 年 12 月 3 日 | 已使用 [管理 SEMM 註冊](#manage-semm-enrollment)的指引進行更新。                                                       |
| V。 1.2  | 2020 年 9 月 29 日 | 處理可用性意見反應的任何其他更新。                                                        |
| V。 1.1  | 2020 年 9 月 15 日 | 請在簡介中放置其他注意事項，以厘清安裝新 OS 的授權需求。 |
| V。 1.0  | 2020 年 9 月 1 日  | 新文章。                                                                                           |
