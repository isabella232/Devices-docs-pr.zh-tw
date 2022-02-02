---
title: '在 Surface (中註冊及設定 Surface) '
description: 瞭解如何建立 Surface UEFI 設定套件，以控制 Surface UEFI 的設定，以及如何在 SEMM 中註冊 Surface 裝置。
keywords: surface 企業管理
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
ms.openlocfilehash: 61b15bf1d7ae5f99d57fb4dcd7bd9f83d9eb4b0a
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337936"
---
# <a name="enroll-and-configure-surface-devices-with-semm"></a>使用 SEMM 註冊及設定 Surface 裝置

使用 Microsoft Surface Enterprise管理模式 (SEMM) ，您可以安全地設定 Surface 裝置上的 Surface UEFI 設定，並管理貴組織 Surface 裝置上的這些設定。 當 Surface 裝置由 SEMM 管理時，該裝置會視為已註冊 (** 有時稱為已啟用) 。 本文將說明如何建立 Surface UEFI 設定套件，此套件不僅可控制 Surface UEFI 的設定，也會在 SEMM 中註冊 Surface 裝置。

有關 SEMM 的更高層級概觀，請參閱[Microsoft Surface Enterprise管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

作為 SEMM 的替代方案，較新的 Surface 裝置支援透過 Microsoft Intune 遠端系統管理部分Microsoft Intune。 詳情請參閱 [Surface UEFI 設定 Intune 管理](surface-manage-dfci-guide.md)。

> [!NOTE]
> 僅透過 UEFI Manager Surface Pro X 支援 SEMM。 若要詳細資訊，請參閱[部署、管理及維護 X Surface Pro。](surface-pro-arm-app-management.md)

#### <a name="download-and-install-microsoft-surface-uefi-configurator"></a>下載並安裝 Microsoft Surface UEFI Configurator

用來建立 SEMM 套件的工具是 Microsoft Surface UEFI Configurator。 您可以從 Microsoft 下載中心的 SURFACE IT 工具頁面下載 Microsoft Surface [](https://www.microsoft.com/download/details.aspx?id=46703) UEFI 配置程式。
執行 Microsoft Surface UEFI 組Windows安裝程式 (.msi) 檔案，以開始安裝工具。 安裝程式完成後，在安裝程式的 區段尋找 Microsoft Surface UEFI [開始] 功能表。

>[!NOTE]
>Microsoft Surface UEFI 組Windows 10。

## <a name="create-a-surface-uefi-configuration-package"></a>建立 Surface UEFI 組組套件

Surface UEFI 設定套件會同時執行將 Surface UEFI 設定新設定套用至使用 SEMM 管理的 Surface 裝置的角色，以及註冊 SEMM 中的 Surface 裝置角色。 建立組組套件時，您必須有簽名憑證，以與 SEMM 一起使用，以確保每個 Surface 裝置上的 UEFI 設定設定安全。 有關 SEMM 憑證需求的資訊，請參閱[Microsoft Surface Enterprise管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

若要建立 Surface UEFI 組組套件，請遵循下列步驟：

1. 從應用程式開啟 Microsoft Surface UEFI [開始] 功能表。

2. 按一下 **\[開始\]**。

3. 按一下 **[組組套件**，如圖 1 所示。

   ![建立 SEMM 註冊的套件。](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *圖 1。 選取組組套件以建立適用于 SEMM 註冊和配置的套件*

4. 按一下 **[憑證保護** > 以使用私密金鑰 (.pfx) 匯出的憑證檔案，如圖 2 所示。 流覽至憑證檔案的位置，選取該檔案，然後按一下 [ **確定**。

   ![新增 SEM 憑證和 Surface UEFI 密碼至組組套件。](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *圖 2. 新增 SEMM 憑證和 Surface UEFI 密碼至 Surface UEFI 組組套件*

5. 當系統提示您確認憑證密碼時，請輸入並確認憑證檔案的密碼，然後按一下 [ **確定**。

6. 按一下 **[密碼保護** 以在 Surface UEFI 中新增密碼。 每次您啟動至 UEFI 時，都會需要這個密碼。 如果未輸入此密碼，則只會顯示電腦**** 資訊、關於****、Enterprise**管理**，以及**離開**頁面。 這是選用步驟。

7. 出現提示時，請輸入並確認您所選擇的 Surface UEFI 密碼，然後按一下 [ **確定**。 如果您想要清除現有的 Surface UEFI 密碼，請保留密碼欄位空白。

8. 如果您不希望 Surface UEFI 套件套用至特定裝置，請在 [選擇您想要的目標**Surface**類型？** **
   > [!TIP] 
   > 您必須選取裝置，因為預設不會選取任何裝置。

   ![選擇套件相容性的裝置。](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *圖 3. 選擇套件相容性的裝置*

9. 按 **\[下一步\]**。

10. 如果您想要停用受管理的 Surface 裝置上的元件，請在 [選擇要啟用或停用的元件****？** **  (圖 4.) 顯示每個裝置的預設組組為 **On**。 如果您想要 **將所有** 滑杆返回預設位置，請按一下 [重設按鈕。

    ![停用或啟用 Surface 元件。](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *圖 4. 停用或啟用個別的 Surface 元件*

11. 按 **\[下一步\]**。

12. 若要在 Surface UEFI 或 Surface UEFI 頁面的顯示中啟用或停用進位選項，請在 [選擇裝置進一步設定> 頁面上，按一下所需設定旁的滑杆，將該選項設定為 [開**** 或關閉**** (如圖 5) 所示。** ** 在**UEFI**首頁區段，您可以使用安全性、裝置和啟動的滑杆來控制哪些**** 頁面可供啟動至**** Surface UEFI 的使用者使用。** **  (有關 Surface UEFI 設定的詳細資訊，請參閱管理[Surface UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)設定。) 當您完成選取選項以產生及儲存套件時****，請按一下 [建立>。

    ![控制進位的 Surface UEFI 設定和 Surface UEFI 頁面。](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *圖 5. 使用 SEMM 控制進位的 Surface UEFI 設定和 Surface UEFI 頁面*

13. 在 [ **另** 存新用圖> 對話方塊中，指定 Surface UEFI 組式套件的名稱，流覽至要儲存檔案的位置，然後按一下 [ **儲存**。

14. 建立並儲存套件時，會顯示 **成功** 頁面。

    >[!NOTE]
    >錄製此頁面上顯示的憑證指紋字元，如圖 6 所示。 您需要這些字元以確認在 SEMM 中註冊新的 Surface 裝置。 按一下 **[結束** 以完成套件建立並關閉 Microsoft Surface UEFI Configurator。
    
    ![顯示憑證指紋字元。](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")
    
    *圖 6. 憑證指紋的最後兩個字元會顯示在成功頁面上*

現在，您建立了 Surface UEFI 設定套件，您可以註冊或設定 Surface 裝置。

>[!NOTE]
>建立 Surface UEFI 組組套件時，會以桌面建立記錄檔案，並包含組組套件設定和選項詳細資料。

## <a name="enroll-a-surface-device-in-semm"></a>在 SEMM 中註冊 Surface 裝置
執行 Surface UEFI 組組套件時，SEMM 憑證和 Surface UEFI 組組檔案會分期在 Surface 裝置的固件儲存空間中。 當 Surface 裝置重新開機時，Surface UEFI 會處理這些檔案，並開始在 SEMM 中申請 Surface UEFI 組配置或註冊 Surface 裝置，如圖 7 所示。

![Surface UEFI 或註冊之配置的 SEMM 程式。](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*圖 7. Surface UEFI 或 Surface 裝置註冊的 SEMM 程式*

在開始在 SEMM 中註冊 Surface 裝置之前，請確保您手上有憑證指紋的最後兩個字元。 您需要這些字元以確認裝置註冊 (請參閱圖 6) 。

若要使用 Surface UEFI 組組套件在 SEMM 中註冊 Surface 裝置，請遵循下列步驟：

1. 在您想要在 SEMM .msi的 Surface 裝置上，執行 Surface UEFI 組.msi套件。 這會在裝置固件中配置 Surface UEFI 組設定檔。
2. 選取 **[我**接受授權合約中的條款> 核取方塊，接受 [使用者授權合約 (EULA) ，然後按一下 [安裝> 以開始安裝程式。** **
3. 按一下 **[完成** 以完成 Surface UEFI 組組套件安裝並重新啟動 Surface 裝置時，系統提示您執行此作業。
4. Surface UEFI 會載入組組檔案，並確定裝置上未啟用 SEMM。 Surface UEFI 接著會開始 SEMM 註冊程式，如下所示：
   * Surface UEFI 會確認 SEMM 設定檔包含 SEMM 憑證。
   * Surface UEFI 會提示您輸入憑證指紋的最後兩個字元，以確認在 SEMM 中註冊 Surface 裝置，如圖 8 所示。

      ![SEMM 註冊需要憑證指紋的最後兩個字元。](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *圖 8. 在 SEMM 中註冊需要憑證指紋的最後兩個字元*

   * Surface UEFI 會將 SEMM 憑證儲存在固件中，並適用 Surface UEFI 設定檔中指定的設定設定。
   
5. Surface 裝置現在已註冊于 SEMM，而且會啟動Windows。

您可以在程式和**功能 (中**尋找**Microsoft Surface**組組套件 ，如圖 9) 所示，或在儲存在事件檢視器 (中的應用程式和服務記錄中的**Microsoft Surface UEFI Configurationator**記錄中，如圖 10) 所示，確認 Surface 裝置已成功註冊 SEMM。** **

:::image type="content" alt-text="在程式和功能中驗證 Surface 裝置在 SEMM 中的註冊。" source="images/surface-semm-enroll-fig9.png":::

*圖 9. 在程式和功能中驗證 Surface 裝置在 SEMM 中的註冊*

:::image type="content" alt-text="在事件檢視器中驗證 Surface 裝置在 SEMM 中的註冊。" source="images/surface-semm-enroll-fig10.png":::

*圖 10. 在事件檢視器中驗證 Surface 裝置在 SEMM 中的註冊*

您也可以確認裝置已註冊 Surface UEFI 中的 SEMM ，而裝置已註冊時，Surface UEFI 會包含**Enterprise 管理**頁面 (如圖 11) 。

:::image type="content" alt-text="Surface UEFI Enterprise管理頁面。" source="images/surface-semm-enroll-fig11.png":::

*圖 11. Surface UEFI Enterprise管理頁面*


## <a name="configure-surface-uefi-settings-with-semm"></a>使用 SEMM 設定 Surface UEFI 設定

在 SEMM 中註冊裝置之後，您可以執行以相同 SEMM 憑證簽署的 Surface UEFI 設定套件，以套用新的 Surface UEFI 設定。 這些設定會在裝置下次啟動時自動套用，而不需要使用者進行任何互動。 您可以使用應用程式部署解決方案 ，Microsoft Endpoint Configuration Manager將 Surface UEFI 設定套件部署到 Surface 裝置，以變更或管理 Surface UEFI 中的設定。

若要瞭解如何使用 Configuration Manager Windows安裝程式 (.msi) 部署應用程式，請參閱使用[Microsoft Endpoint Configuration Manager。](https://technet.microsoft.com/library/mt627959)

如果您用密碼保護 Surface UEFI，沒有密碼的使用者若嘗試啟動到 Surface UEFI，則只會顯示電腦資訊、關於、Enterprise管理，**** 以及顯示給他們**** 的離開**** 頁面。** **

如果您沒有使用密碼保護 Surface UEFI，或使用者正確輸入密碼，則使用 SEMM 設定設定會呈現暗灰色 (無法使用) 且組織管理的文字會顯示在頁面頂端，如圖 12 所示。

:::image type="content" alt-text="設定在 Surface UEFI 中停用的 SEMM 管理。" source="images/surface-semm-enroll-fig12.png":::

*圖 12. 設定由 SEMM 管理的系統將在 Surface UEFI 中停用*
