---
title: 使用 SEMM (Surface) 來註冊及設定 Surface 裝置
description: 瞭解如何建立 Surface UEFI 配置套件來控制 Surface UEFI 的設定，以及在 SEMM 中註冊 Surface 裝置。
keywords: surface enterprise 管理
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
ms.openlocfilehash: f310b4a43a8a0fc0e77295344ac723770ce821bc
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271060"
---
# 使用 SEMM 註冊及設定 Surface 裝置

使用 Microsoft Surface Enterprise 管理模式 (SEMM) ，您可以在 Surface 裝置上安全地設定 Surface UEFI 的設定，並在組織中的 Surface 裝置上管理這些設定。 當 Surface 裝置由 SEMM 管理時，該裝置會被視為已 *註冊* ， (有時稱為「已啟用) 」。 本文說明如何建立 Surface UEFI 配置套件，該套件不僅可控制 Surface UEFI 的設定，也會在 SEMM 中註冊 Surface 裝置。

如需 SEMM 的更高層次概覽，請參閱 [Microsoft Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

就 SEMM 而言，較新的 Surface 裝置支援透過 Microsoft Intune 來遠端系統管理部分固件設定。 如需詳細資訊，請參閱 [SURFACE UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)。

> [!NOTE]
> 僅透過 UEFI Manager 支援 Surface Pro X 的 SEMM。 如需詳細資訊，請參閱 [部署、管理及維護 Surface Pro X](surface-pro-arm-app-management.md)。

#### 下載並安裝 Microsoft Surface UEFI 配置器

用來建立 SEMM 套件的工具是 Microsoft Surface UEFI 設定檔。 您可以從 Microsoft 下載中心的 [ [表面工具](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面下載 MICROSOFT Surface UEFI 設定檔。
執行 Microsoft Surface UEFI 設定檔 Windows 安裝程式 ( .msi) 檔案以開始安裝工具。 安裝程式完成後，請在 [開始] 功能表的 [所有應用程式] 區段中尋找 Microsoft Surface UEFI 配置器。

>[!NOTE]
>只有 Windows 10 支援 Microsoft Surface UEFI 配置器。

## 建立 Surface UEFI 配置套件

Surface UEFI 配置套件會執行將 Surface UEFI 設定的新設定套用到 SEMM 中 SEMM 的 Surface 裝置，以及在中註冊 Surface 裝置的角色。 建立配置套件時，您必須具備與 SEMM 搭配使用的簽署憑證，以保護每個 Surface 裝置上的 UEFI 設定。 如需有關 SEMM 憑證需求的詳細資訊，請參閱 [Microsoft Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

若要建立 Surface UEFI 配置套件，請遵循下列步驟：

1. 從 [開始] 功能表開啟 Microsoft Surface UEFI 配置器。
2. 按一下 **\[開始\]**。
3. 按一下 [設定 **套件**]，如圖1所示。

   ![建立 SEMM 註冊套件](images/surface-ent-mgmt-fig1-uefi-configurator.png "Create a package for SEMM enrollment")

   *圖 1。 選取 [設定套件]，建立 SEMM 註冊與設定的套件*

4. 按一下 [ **憑證保護** ] 以新增您匯出的憑證檔案，其中包含私密金鑰 ( .pfx) ，如圖2所示。 流覽到您憑證檔案的位置，選取檔案，然後按一下 **[確定]**。

   ![將 SEM 憑證和 Surface UEFI 密碼新增至 [配置套件]](images/surface-ent-mgmt-fig2-securepackage.png "Add the SEM certificate and Surface UEFI password to configuration package")

   *圖 2. 將 SEMM 憑證和 Surface UEFI 密碼新增至 Surface UEFI 配置套件*

5. 當系統提示您確認憑證密碼時，請輸入並確認您的憑證檔案密碼，然後按一下 **[確定]**。
6. 按一下 [ **密碼保護** ]，將密碼新增至 Surface UEFI。 每當您引導至 UEFI 時，就會需要此密碼。 如果未輸入此密碼，則只會顯示 **電腦資訊**、[ **關於**]、[ **企業管理** **] 和 [** 結束] 頁面。 這是選用步驟。
7. 出現提示時，請輸入並確認您所選取的 Surface UEFI 密碼，然後按一下 **[確定]**。 如果您要清除現有的 Surface UEFI 密碼，請將密碼欄位留白。
8. 如果您不想要將 Surface UEFI 套件套用到特定裝置，請在 [ **選擇您想要設定目標的表面類型** ] 頁面上，按一下對應 Surface Book 或 Surface Pro 4 影像底下的滑杆，使其位於 [ **關閉** ] 位置。  (如圖3所示。 ) 
   > [!NOTE] 
   > 預設會選取 [沒有] 時，您必須選取 [裝置]。

   ![選擇要封裝相容性的裝置](images/surface-semm-enroll-fig3.jpg "Choose devices for package compatibility")

   *圖 3. 選擇要封裝相容性的裝置*

9. 按 **\[下一步\]**。
10. 如果您想要停用受管理的 Surface 裝置上的元件，請在 [ **選擇您要啟用或停用的元件** ] 頁面上，按一下您想要停用之任何裝置或裝置群組旁邊的滑杆，以使滑杆位於 [ **關閉** ] 位置。 圖4所示的 (。 ) 每個裝置的預設設定為 [ **開啟**]。 如果您想要將所有滑杆回到預設位置，請按一下 [ **重設** ] 按鈕。

    ![停用或啟用 Surface 元件](images/surface-ent-mgmt-fig3-enabledisable.png "Disable or enable Surface components")

    *圖 4. 停用或啟用個別 Surface 元件*

11. 按 **\[下一步\]**。
12. 若要在 Surface UEFI 中啟用或停用高級選項，或顯示 Surface UEFI 頁面，請在 [ **選擇裝置的高級設定** ] 頁面上，按一下 [所需設定] 旁的滑杆，以將該選項設定為 [ **開啟** ] 或 [ **關閉** 圖 5) 中所示的 (。 在 [ **UEFI 首頁** ] 區段中，您可以使用 [ **安全性**]、[ **裝置**] 和 [ **啟動** ] 滑杆來控制啟動至 Surface UEFI 的使用者所能使用的頁面。  (如需 Surface UEFI 設定的詳細資訊，請參閱 [管理 SURFACE uefi 設定](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)。當您完成選取選項來產生並儲存套件時，請 ) 按一下 [ **組建** ]。

    ![控制高級 Surface UEFI 設定和 Surface UEFI 頁面](images/surface-ent-mgmt-fig4-advancedsettings.png "Control advanced Surface UEFI settings and Surface UEFI pages")

    *圖 5. 使用 SEMM 控制高級 Surface UEFI 設定和 Surface UEFI 頁面*

13. 在 [ **另存** 新檔] 對話方塊中，指定 Surface UEFI 配置套件的名稱，流覽至您要儲存檔案的位置，然後按一下 [ **儲存**]。
14. 建立並儲存套件後，就會顯示 **成功** 的頁面。

>[!NOTE]
>記錄此頁面上顯示的憑證指紋字元，如圖6所示。 您將需要這些字元，以確認在 SEMM 中註冊新的 Surface 裝置。 按一下 [ **結束** ] 以完成套件建立，然後關閉 MICROSOFT Surface UEFI 配置器。

![顯示憑證指紋字元](images/surface-ent-mgmt-fig5-success.png "Display of certificate thumbprint characters")

*圖 6. 證書指紋的最後兩個字元會顯示在成功的頁面上*

現在您已經建立 Surface UEFI 配置套件，您可以註冊或設定 Surface 裝置。

>[!NOTE]
>建立 Surface UEFI 配置套件時，會在桌面上建立記錄檔案，並提供 [設定套件設定] 和 [選項] 的詳細資料。

## 在 SEMM 中註冊 Surface 裝置
在執行 Surface UEFI 設定套件時，會在 Surface 裝置的固件儲存區中暫存 SEMM 憑證和 Surface UEFI 配置檔案。 當 Surface 裝置重新開機時，Surface UEFI 會處理這些檔案，並開始應用 Surface UEFI 設定或在 SEMM 中註冊 Surface 裝置的程式，如圖7所示。

![SEMM 處理常式以取得 Surface UEFI 或登記的配置](images/surface-semm-enroll-fig7.png "SEMM process for configuration of Surface UEFI or enrollment")

*圖 7. 配置 Surface UEFI 或對 Surface 裝置進行註冊的 SEMM 處理常式*

在您開始在 SEMM 中註冊 Surface 裝置之前，請先確定您已有證書指紋的最後兩個字元。 您將需要這些字元來確認裝置的註冊 (請參閱圖 6) 。

若要在 SEMM 中使用 Surface UEFI 設定套件註冊 Surface 裝置，請依照下列步驟進行：

1. 在您想要在 SEMM 註冊的 Surface 裝置上執行 Surface UEFI 配置套件 .msi 檔案。 這會在裝置的固件中設定 Surface UEFI 設定檔。
2. 選取 [ **我接受授權合約中的條款** ] 核取方塊，以接受使用者授權合約 (EULA) ，然後按一下 [ **安裝** ] 以開始安裝程式。
3. 按一下 **[完成]** 以完成 surface UEFI 設定套件安裝，當系統提示您時，請重新開機 surface 裝置。
4. Surface UEFI 將載入設定檔案，並判斷裝置上未啟用 SEMM。 然後，Surface UEFI 就會開始 SEMM 註冊程式，如下所示：
   * Surface UEFI 將確認 SEMM 設定檔包含 SEMM 憑證。
   * Surface UEFI 會提示您輸入憑證指紋的最後兩個字元，以確認在 SEMM 中註冊 Surface 裝置，如圖8所示。

      ![SEMM 註冊需要證書指紋的最後兩個字元](images/surface-semm-enroll-fig8.png "SEMM enrollment requires last two characters of certificate thumbprint")

      *圖 8. 在 SEMM 中註冊需要證書指紋的最後兩個字元*

   * Surface UEFI 會將 SEMM 憑證儲存在固件中，並套用在 Surface UEFI 設定檔中指定的設定設定。
   
5. 表面裝置現在已註冊為 SEMM，並會啟動至 Windows。

您可以在 [**程式和 (功能**] 中尋找 [ **Microsoft surface Configuration 套件**]，以確認 Surface 裝置已順利登入 SEMM，如圖 9) 所示，或儲存在**Microsoft surface UEFI**設定檔記錄中的事件中，在 [事件檢視器] 中的 [**應用程式和服務記錄** (] 下找到，如圖 10) 所示。

![驗證程式和功能 SEMM 中的 Surface 裝置註冊](images/surface-semm-enroll-fig9.png "Verify enrollment of Surface device in SEMM in Programs and Features")

*圖 9. 確認在 [程式和功能] 中的 SEMM 中註冊 Surface 裝置*

![驗證在事件檢視器的 SEMM 中註冊 Surface 裝置](images/surface-semm-enroll-fig10.png "Verify enrollment of Surface device in SEMM in Event Viewer")

*圖 10. 驗證在事件檢視器的 SEMM 中註冊 Surface 裝置*

您也可以確認裝置已註冊在 Surface UEFI 中 SEMM，而 Surface UEFI 將包含 **企業管理** 頁面 (如圖 11) 所示。

![Surface UEFI 企業版管理頁面](images/surface-semm-enroll-fig11.png "Surface UEFI Enterprise management page")

*圖 11. Surface UEFI 企業版管理頁面*


## 使用 SEMM 設定 Surface UEFI 設定

在 SEMM 中註冊裝置之後，您可以執行使用相同 SEMM 憑證簽署的 Surface UEFI 配置套件，以套用新的 Surface UEFI 設定。 在下次啟動裝置時，系統會自動套用這些設定，而不需要使用者進行任何互動。 您可以使用應用程式部署解決方案（例如 Microsoft 端點設定管理員），將 Surface UEFI 配置套件部署到 Surface 裝置，以變更或管理 Surface UEFI 中的設定。

如需有關如何使用 Configuration Manager 部署 Windows Installer ( .msi) 檔案的詳細資訊，請參閱使用 [Microsoft 端點 Configuration Manager 部署及管理應用程式](https://technet.microsoft.com/library/mt627959)。

如果您有安全的 Surface UEFI 與密碼，則不含嘗試引導至 Surface UEFI 之密碼的使用者，將只會顯示**電腦資訊**、[**關於**]、[**企業管理**]，以及 [結束 **] 頁面。**

如果您使用的是密碼或使用者正確輸入密碼時沒有安全的 Surface UEFI，則使用 SEMM 設定的設定會變暗， (無法使用]) 且您組織所管理的一些設定的文字會顯示在頁面頂端，如圖12所示。

![在 Surface UEFI 中停用 SEMM 管理的設定](images/surface-semm-enroll-fig12.png "Settings managed by SEMM disabled in Surface UEFI")

*圖 12. SEMM 管理的設定將會在 Surface UEFI 中停用*
