---
title: 使用 SEMM (Surface) 註冊及設定 Surface 裝置
description: 瞭解如何建立 Surface UEFI 組態套件來控制 Surface UEFI 的設定，以及在 SEMM 中註冊 Surface 裝置。
keywords: Surface Enterprise 管理
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: hachinda
manager: laurawi
ms.date: 1/15/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 6df11e1c6e0b28616cb4d365e159f134195c0ecb
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472361"
---
# <a name="enroll-and-configure-surface-devices-with-semm"></a>使用 SEMM 註冊及設定 Surface 裝置

透過 Microsoft Surface Enterprise管理模式 (SEMM) ，您可以安全地在 Surface 裝置上設定 Surface UEFI 的設定，並在組織中的 Surface 裝置上管理這些設定。 當 Surface 裝置由 SEMM 管理時，該裝置會被視為 *已註冊* (有時稱為啟用) 。 本文說明如何建立 Surface UEFI 組態套件，以控制 Surface UEFI 的設定，並在 SEMM 中註冊 Surface 裝置。

如需更高層級的 SEMM 概觀，請參閱[Microsoft Surface Enterprise管理模式](surface-enterprise-management-mode.md)。

作為 SEMM 的替代方案，較新的 Surface 裝置支援透過 Microsoft Intune 遠端系統管理韌體設定的子集。 如需詳細資訊，請參閱[surface UEFI 設定Intune管理](surface-manage-dfci-guide.md)。

> [!NOTE]
> 只有透過 UEFI 管理員在 Surface Pro X 上才支援 SEMM。 如需詳細資訊，請參閱[部署、管理和維護Surface Pro X](surface-pro-arm-app-management.md)。

#### <a name="download-and-install-microsoft-surface-uefi-configurator"></a>下載並安裝 Microsoft Surface UEFI 設定程式

用來建立 SEMM 套件的工具是 Microsoft Surface UEFI 設定程式。 您可以從 Microsoft 下載中心的 Surface [Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) 頁面下載 Microsoft Surface UEFI 設定程式。
執行 Microsoft Surface UEFI Configurator Windows Installer (.msi) 檔案以開始安裝工具。 安裝程式完成時，請在您[開始] 功能表的 [所有應用程式] 區段中尋找 Microsoft Surface UEFI 設定程式。

>[!NOTE]
>只有Windows 10和Windows 11才支援 Microsoft Surface UEFI 設定器。

## <a name="create-a-surface-uefi-configuration-package"></a>建立 Surface UEFI 設定套件

Surface UEFI 組態套件會執行將 Surface UEFI 設定的新設定套用至使用 SEMM 管理的 Surface 裝置的角色，以及在 SEMM 中註冊 Surface 裝置的角色。 建立組態套件時，您必須擁有要與 SEMM 搭配使用的簽署憑證，以保護每個 Surface 裝置上的 UEFI 設定。 如需 SEMM 憑證需求的詳細資訊，請參閱[Microsoft Surface Enterprise管理模式](surface-enterprise-management-mode.md)。

若要建立 Surface UEFI 設定套件，請遵循下列步驟：

1. 從[開始] 功能表開啟 Microsoft Surface UEFI 設定器。

2. 按一下 **\[開始\]**。

3. 按一下 **[組態套件**]，如圖 1 所示。

   ![建立 SEMM 註冊的套件。](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *圖 1。 選取 [組態套件] 以建立適用于 SEMM 註冊和設定的套件*

4. 按一下 **[憑證保護** ] 以使用私密金鑰 (.pfx) 新增匯出的憑證檔案，如圖 2 所示。 流覽至憑證檔案的位置，選取檔案，然後按一下 [ **確定]**。

   ![將 SEM 憑證和 Surface UEFI 密碼新增至設定套件。](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to the configuration package")

   *圖 2. 將 SEMM 憑證和 Surface UEFI 密碼新增至 Surface UEFI 設定套件*

5. 當系統提示您確認憑證密碼時，請輸入並確認憑證檔案的密碼，然後按一下 [ **確定]**。

6. 按一下 **[密碼保護** ] 將密碼新增至 Surface UEFI。 每當您開機到 UEFI 時，就需要此密碼。 如果未輸入此密碼，則只會顯示 **[電腦資訊**]、[**關於**]、**[Enterprise管理**] 和 [**結束**] 頁面。 這是選用步驟。

7. 出現提示時，輸入並確認您為 Surface UEFI 選擇的密碼，然後按一下 [ **確定]**。 如果您想要清除現有的 Surface UEFI 密碼，請將密碼欄位保留空白。

8. 如果您不想讓 Surface UEFI 套件套用至特定裝置，請在 [ **選擇您要設為目標的 Surface 類型** ] 頁面上，按一下對應裝置下方的滑杆，使其位於 **[關閉** ] 位置，如圖 3 所示。
   > [!TIP] 
   > 您必須選取裝置，因為預設不會選取任何裝置。 向右捲動以檢視所有可用的裝置。

   ![針對套件相容性選擇裝置，並向右捲動以檢視所有可用的裝置](images/surface-semm-enroll-fig3.png "Choose devices for package compatibility")

   ![選擇裝置以提供套件相容性。](images/surface-semm-enroll-fig3a.png "Choose devices for package compatibility")


   *圖 3. 針對套件相容性選擇裝置*

9. 按 **\[下一步\]**。

10. 如果您想要停用受控 Surface 裝置上的元件，請在 [ **選擇要啟用或停用的元件** ] 頁面上，按一下您想要停用的任何裝置或裝置群組旁的滑杆，使滑杆位於 **[關閉** ] 位置。  (圖 4.) 顯示每部裝置的預設設定為 **[開啟]**。 按一下 [ **重設]** 按鈕，將所有滑杆傳回預設位置。

    ![停用或啟用 Surface 元件。](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *圖 4. 停用或啟用個別 Surface 元件*

11. 按 **\[下一步\]**。

12. 若要在 Surface UEFI 中啟用或停用進階選項或顯示 Surface UEFI 頁面，請在 [ **選擇裝置的進階設定** ] 頁面上，按一下所需設定旁邊的滑杆，將該選項設定為 [開 **啟] 或** [ **關閉** ] (如圖 5) 所示。 在 **[UEFI 首頁] 區** 段中，您可以使用 **[安全**性]、[ **裝置**] 和 [ **開機** ] 滑杆來控制開機進入 Surface UEFI 的使用者可以使用哪些頁面。  (如需 Surface UEFI 設定的詳細資訊，請參閱 [管理 Surface UEFI 設定](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)。) 當您完成選取用來產生和儲存套件的選項時，請按一下 [ **建置]**。 

    ![控制進階 Surface UEFI 設定和 Surface UEFI 頁面。](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *圖 5. 使用 SEMM 控制進階 Surface UEFI 設定和 Surface UEFI 頁面*

13. 在 [ **另存新** 檔] 對話方塊中，指定 Surface UEFI 組態套件名稱，流覽至您要儲存檔案的位置，然後按一下 [ **儲存]**。

14. 建立並儲存封裝時，會顯示 [ **成功** ] 頁面。

    >[!NOTE]
    >記錄此頁面上顯示的憑證指紋字元，如圖 6 所示。 您將需要這些字元來確認在 SEMM 中註冊新的 Surface 裝置。 按一下 **[結束** ] 以完成套件建立，並關閉 [Microsoft Surface UEFI 設定程式]。
    
    ![憑證指紋字元的顯示。](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")
    
    *圖 6. 憑證指紋的最後兩個字元會顯示在 [成功] 頁面上*

現在您已建立 Surface UEFI 設定套件，您可以註冊或設定 Surface 裝置。

>[!NOTE]
>建立 Surface UEFI 組態套件時，會在桌面上顯示記錄檔，其中包含組態套件設定和選項的詳細資料。

## <a name="enroll-a-surface-device-in-semm"></a>在 SEMM 中註冊 Surface 裝置
執行 Surface UEFI 組態套件時，SEMM 憑證和 Surface UEFI 組態檔會暫存在 Surface 裝置的韌體儲存體中。 當 Surface 裝置重新開機時，Surface UEFI 會處理這些檔案，並開始在 SEMM 中套用 Surface UEFI 設定或註冊 Surface 裝置的程式，如圖 7 所示。

![用於設定 Surface UEFI 或註冊的 SEMM 程式。](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*圖 7. 設定 Surface UEFI 或註冊 Surface 裝置的 SEMM 程式*

在 SEMM 中註冊 Surface 裝置之前，請確定您手上有憑證指紋的最後兩個字元。 您將需要這些字元來確認裝置的註冊 (請參閱圖 6) 。

若要使用 Surface UEFI 設定套件在 SEMM 中註冊 Surface 裝置，請遵循下列步驟：

1. 在您要在 SEMM 中註冊的 Surface 裝置上執行 Surface UEFI 組態套件.msi檔案。 這會在裝置的韌體中布建 Surface UEFI 組態檔。
2. 選取 [ **我接受授權合約] 中的條款** 核取方塊，以接受使用者授權合約 (EULA) ，然後按一下 [ **安裝** ] 開始安裝程式。
3. 按一下 **[完成** ] 以完成 Surface UEFI 設定套件安裝，並在系統提示您這麼做時重新開機 Surface 裝置。
4. Surface UEFI 會載入組態檔，並判斷裝置上未啟用 SEMM。 Surface UEFI 接著會開始 SEMM 註冊程式，如下所示：
   * Surface UEFI 會確認 SEMM 組態檔包含 SEMM 憑證。
   * Surface UEFI 會提示您輸入憑證指紋的最後兩個字元，以確認在 SEMM 中註冊 Surface 裝置，如圖 8 所示。

      ![SEMM 註冊需要憑證指紋的最後兩個字元。](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *圖 8. SEMM 註冊需要憑證指紋的最後兩個字元*

   * Surface UEFI 會將 SEMM 憑證儲存在韌體中，並套用 Surface UEFI 組態檔中指定的組態設定。
   
5. Surface 裝置現在已在 SEMM 中註冊，並會開機至Windows。

您可以在 [**程式和功能**] (中尋找**Microsoft Surface**組態套件，如圖 9) 所示，或在儲存在**Microsoft Surface UEFI Configurator**記錄檔中的事件中，在 事件檢視器 (中尋找 [**應用程式和服務記錄**] 底下的事件，以確認 Surface 裝置是否已成功註冊，如圖 10) 所示。

:::image type="content" alt-text="在 [程式和功能] 中確認在 SEMM 中註冊 Surface 裝置。" source="images/surface-semm-enroll-fig9.png":::

*圖 9. 在 [程式和功能] 中確認在 SEMM 中註冊 Surface 裝置*

:::image type="content" alt-text="在 事件檢視器 中確認在 SEMM 中註冊 Surface 裝置。" source="images/surface-semm-enroll-fig10.png":::

*圖 10. 在 事件檢視器 中確認在 SEMM 中註冊 Surface 裝置*

您也可以確認裝置已在 Surface UEFI 的 SEMM 中註冊 – 註冊裝置時，Surface UEFI 會包含**Enterprise管理**頁面 (如圖 11) 所示。

:::image type="content" alt-text="Surface UEFI Enterprise管理頁面。" source="images/surface-semm-enroll-fig11.png":::

*圖 11. Surface UEFI Enterprise管理頁面*


## <a name="configure-surface-uefi-settings-with-semm"></a>使用 SEMM 設定 Surface UEFI 設定

在 SEMM 中註冊裝置之後，您可以執行使用相同 SEMM 憑證簽署的 Surface UEFI 組態套件，以套用新的 Surface UEFI 設定。 這些設定會在下次裝置開機時自動套用，而不會與使用者進行任何互動。 您可以使用應用程式部署解決方案，例如Microsoft Endpoint Configuration Manager將 Surface UEFI 組態套件部署至 Surface 裝置，以變更或管理 Surface UEFI 中的設定。

如需如何使用 Configuration Manager 部署 Windows Installer (.msi) 檔案的詳細資訊，請參閱[使用 Microsoft Endpoint Configuration Manager 部署和管理應用程式](/mem/configmgr/apps/deploy-use/deploy-applications)。

假設您已使用密碼保護 Surface UEFI。 在此情況下，沒有密碼嘗試開機到 Surface UEFI 的使用者只會顯示**電腦資訊**、**關於**、**Enterprise管理**及**結束**頁面。

如果您尚未使用密碼保護 Surface UEFI，或使用者正確輸入密碼，則使用 SEMM 設定的設定將會變暗， (無法使用) 表示  **某些設定是由您的組織管理**，如圖 12 所示。

:::image type="content" alt-text="設定由 SEMM 管理的會在 Surface UEFI 中停用。" source="images/surface-semm-enroll-fig12.png":::

*圖 12. 在 Surface UEFI 中將停用由 SEMM 管理的設定*
