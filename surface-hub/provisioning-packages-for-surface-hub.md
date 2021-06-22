---
title: 建立佈建套件
description: 針對 Windows 10，您可以透過佈建套件來設定使用登錄或設定服務提供者 (CSP) 的設定。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: 新增憑證, 佈建套件
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/28/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 087826a7a0cba7a47accc0d3d66714289f2ae9d2
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "11613948"
---
# <a name="create-provisioning-packages-for-surface-hub"></a>為應用程式建立Surface Hub

資源調配套件可讓您自動化重要功能的部署，協助在貴組織的所有 Surface Hub 中提供一致的體驗。  在Windows上 (WCD) ，您可以完成下列工作：

- 註冊 Active Directory 或 Azure Active Directory
- 建立裝置系統管理員帳戶
- 新增應用程式與憑證
- 設定 Proxy 設定
- 新增 Surface Hub 設定檔
- 設定 [設定服務提供者 (CSP) 設定](/windows/client-management/mdm/surfacehub-csp)

## <a name="overview"></a>概觀

1. 在個別的 PC 上Windows 10，Windows[安裝](https://www.microsoft.com/store/apps/9nblggh4tx22)組Microsoft Store。
1. 選取[**設定Surface Hub**](#use-surface-hub-provisioning-wizard)裝置，以使用精靈設定一般設定。 或者， [選取進位設定](#use-advanced-provisioning) 來查看和設定所有可能的設定。
1. 建立部署套件，並將其儲存到 USB 磁碟機。
1. 在第一次執行設定Surface Hub或透過應用程式將套件部署到您的設定應用程式。 若要深入瞭解，請參閱為 Windows 10[建立Windows 10。](/windows/configuration/provisioning-packages/provisioning-create-package)

## <a name="use-surface-hub-provisioning-wizard"></a>使用 Surface Hub配置精靈

1. 開啟 Windows設計工具，然後選取 Surface Hub**裝置**。<br>
    ![使用 Surface Hub 佈建精靈](images/sh-prov-start.png)
    
2. 為專案命名，然後選取下 **一步**。

### <a name="add-certificates"></a>新增憑證

> [!div class="mx-imgBorder"]
> ![新增憑證](images/sh-prov-cert.png)

若要將裝置與憑證一起配置，請選取 **新增憑證**。 輸入憑證的名稱，然後流覽以選取要使用的憑證。  若要使用進一級的置備選項，請參閱將憑證 [新增到您的套件下方的一節](#add-a-certificate-to-your-package)。

### <a name="configure-proxy-settings"></a>設定 Proxy 設定

> [!div class="mx-imgBorder"]
> ![設定 Proxy 設定](images/sh-prov-proxy.png)

1. 將 Proxy 設定切換為 **\[是\]** 或 **\[否\]**。 根據預設，Surface Hub自動偵測 Proxy 設定。 不過，如果您的基礎結構過去需要使用 Proxy 伺服器，但已變更為不需要 Proxy 伺服器，您可以選取 **\[是\]** 和 **\[自動偵測設定\]**，使用佈建套件將 Surface Hub 裝置還原回預設設定。
2. 如果您切換 **為是**，您可以選取以自動偵測 Proxy 設定，或輸入下列其中一項手動設定：

    - 設定腳本的 URL。
    - 靜態 Proxy 伺服器位址和埠資訊。

3. 如果您想要使用設定腳本或 Proxy 伺服器，請關閉自動 **偵測設定**。 您可以使用設定腳本 *或* Proxy 伺服器，而非兩者。
4. 輸入 (位址的Surface Hub，而不使用 Proxy 伺服器) 。 **範例：*.office365.com**
5. 識別是否要將 Proxy 伺服器用於本地位址。

### <a name="set-up-device-admins"></a>設定裝置系統管理員

 > [!div class="mx-imgBorder"]
 > ![加入 Active Directory、Azure AD 或建立本地系統管理員帳戶](images/sh2-wcd.png)

您可以在 Active Directory 中註冊裝置，並指定安全性群組使用「設定」應用程式、註冊 Azure Active Directory 以允許全域系統管理員使用「設定」應用程式，或在裝置上建立本機系統管理員。

1. 若要在 Active Directory 中註冊裝置，請輸入最低權限使用者帳戶的認證以將裝置加入網域，並指定該安全性群組在 Surface Hub 上擁有系統管理員認證。 如果將套件套用至Surface Hub重設的網域帳戶，則只要是一開始設定該Surface Hub的帳戶，就可以使用相同的網域帳戶。 否則，必須在佈建套件中使用不同的網域帳戶。
2. 使用組Windows設計工具來設定大量 Azure AD 註冊之前，[請規劃您的 Azure AD 加入實現](/azure/active-directory/devices/azureadjoin-plan)。 您 Azure AD 租用戶中的 **\[每位使用者的裝置數目上限\]** 設定決定您在精靈中使用的大量權杖可使用多少次。
3. 若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。 設定權杖的到期日 (上限為自您取得權杖起的 30 天)。 選取 **取得大量權杖**。 在 **\[Let's get you signed in\]** (讓我們將您登入) 視窗中，輸入具有權限將裝置加入 Azure AD 的帳戶，然後輸入密碼。 選取**接受**以Windows組組設計工具的必要許可權。
4. 若要建立本機系統管理員帳戶，請選取該選項，並輸入使用者名稱與密碼。

> [!IMPORTANT]
> 如果您在佈建套件中建立本機帳戶，您必須使用 **\[設定\]** 應用程式每隔 42 天變更一次密碼。 如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。

### <a name="enroll-in-third-party-mdm-provider"></a>註冊協力廠商 MDM 提供者

> [!div class="mx-imgBorder"]
> ![註冊協力廠商行動裝置管理](images/sh-prov-mdm.png)

如果您使用協力廠商行動裝置管理 (MDM) 提供者，您可以使用本節註冊Surface Hub。 若要註冊[Intune，](/mem/intune/enrollment/quickstart-setup-auto-enrollment)請如上一節所述，先設定 Azure AD 加入，然後遵循下列 Intune 檔中的指示：為裝置Windows 10註冊。

1. 針對 **第三** 方 **MDM** 的註冊切換為是或否。
2. 如果您切換 **為是**，請提供授權註冊裝置的服務帳戶和密碼或憑證指紋，並指定驗證類型。
3. 如果您的 MDM 提供者需要，請輸入探索服務、註冊服務和策略服務的 URL。

 若要深入瞭解，請參閱使用[MDM Surface Hub管理資料。](manage-settings-with-mdm-for-surface-hub.md)

### <a name="add-applications"></a>新增應用程式

> [!div class="mx-imgBorder"]
> ![新增應用程式](images/sh-prov-apps.png)

您可以在佈建套件中安裝多個通用 Windows 平台 (UWP) 應用程式。 若要深入瞭解，請參閱將 [電腦與應用程式一起配置](/windows/configuration/provisioning-packages/provision-pcs-with-apps)。

> [!NOTE]
> 雖然Windows設計工具可讓您新增傳統 Win32 應用程式至資源配置套件，Surface Hub僅接受 UWP 應用程式。 如果您包含傳統型 Win32 應用程式，佈建將會失敗。

### <a name="add-a-configuration-file"></a>新增組設定檔

除了此設定套件之外，您還可以使用Surface Hub設定檔，更輕鬆地設定您的裝置。 Surface Hub組設定檔包含用於連接到 Exchange、Microsoft Teams 或 商務用 Skype 的裝置帳戶清單，以及無線投影的「好用名稱」。

**若要建立Surface Hub組設定檔：**

1. 開啟Microsoft Excel (或其他.csv編輯器) ，建立.csv名為 SurfaceHubConfiguration.csv
2. 輸入此格式的裝置帳戶和好用名稱清單：

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > 設定檔不得包含欄標頭。 當包含在套用至 Surface Hub 的置備套件中時，您可以從檔案中選取裝置的帳戶和好用名稱。 若要建立.csv，請使用 UPN 位址格式 (rainier@contoso.com) 或下層登入名稱格式 (contoso\rainier) 。

- rainier@contoso.com，password，Rainier Surface Hub

3. 將檔案儲存到您的專案資料夾，然後使用您的部署套件將其複製到 USB 金鑰。

> [!NOTE]
> 設定檔只能在第一次執行設定期間使用。

### <a name="password-protect-provisioning-package"></a>密碼保護資源配置套件

如果您選擇使用密碼，則每次將部署套件套用至裝置時，您都需要輸入密碼。

### <a name="complete-provisioning-wizard"></a>完成資源配置精靈

如果您只需要設定一般設定，請**選取完成**  >  **建立**，然後跳到建立[套件一節](#build-your-package)。 或切換到進一步設定，繼續設定設定。

## <a name="use-advanced-provisioning"></a>使用進位置備

> [!TIP]
> 使用精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定。<br><br> ![切換至進階編輯器](images/icd-simple-edit.png)

1. 如果繼續上一節，請選取**** 切換至進Windows編輯器，然後Windows**進****位置備**。<br>
  ![使用進階佈建](images/sh-prov-adv.png)

2. 為專案命名，然後選取下 **一步**。
3. 選取**共同Windows 10 團隊版，****選取下**一步，**然後選取**完成 。<br>
     ![WCD 新專案](images/icd-new-project.png)

4. 在專案中的可用 **自訂項下**，選取 **共同小組設定**。<br>
     ![WCD 常用設定](images/icd-common-settings.png)

### <a name="add-a-certificate-to-your-package"></a>將憑證新增到您的套件

您可以使用佈建套件來安裝憑證，讓裝置可向 Microsoft Exchange 驗證。

> [!NOTE]
> 佈建套件只能將憑證安裝到裝置 (本機電腦) 存放區，不能安裝到使用者存放區。 如果貴組織需要將憑證安裝至使用者存放區，請使用 Hub**設定**應用程式：更新****&  >  **憑證**  >  **的導入憑證**。
或者，您可以使用 MDM  [**策略**](manage-settings-with-mdm-for-surface-hub.md) 將憑證部署到裝置存放區或使用者存放區。

> [!TIP]
> **ClientCertificates**區段適用于具有私密金鑰的 .pfx 檔案;根 CA 的 .cer 檔案應放在**RootCertificates**區段，而針對**CACertificates**區段的中級 CA。

1. 在**Windows設計**  >  **工具可用的自訂專案**中，請前往**Runtime settings**  >  **憑證**  >  **ClientCertificates**。
2. 輸入 **CertificateName 卷** 標，然後 **選取新增**。
3. 輸入 **CertificatePassword**。
4. 針對 **[CertificatePath]**，瀏覽並選取要使用的憑證。
5. 將 **[ExportCertificate]** 設定為 **[False]**。
6. 針對 \[KeyLocation\]，選取 \[僅限軟體\]。********

### <a name="add-a-uwp-app-to-your-package"></a>在套件中新增 UWP 應用程式

若要將 UWP 應用程式新增到布建套件，您需要應用程式套件 (.appx 或 .appxbundle 檔案) 任何相依性檔案。 如果您從商務用 Microsoft Store 取得應用程式，您也需要*未編碼的*應用程式授權。 請參閱[散發離線應用程式](/microsoft-store/distribute-offline-apps) (英文) 以了解如何從商務用 Microsoft Store 下載這些項目。

**若要新增 UWP 應用程式：**

1. 在 **\[可用的自訂項目\]** 窗格中，移至** \[執行階段設定\]** > **\[UniversalAppInstall\]** > **\[DeviceContextApp\]**。
2. 輸入 **App 的 PackageFamilyName，** 然後 **選取**新增 。 為了保持一致性，請使用應用程式的套件系列名稱。 如果您從商務用 Microsoft Store 取得應用程式，您可以在應用程式授權中找到套件系列名稱。 使用文字編輯器開啟授權檔案，並使用PFM 標記之間的值。
3. 針對**ApplicationFile，** 選取流覽以尋找並選取目標應用程式 ( .appx 或 .appxbundle) 。 ****
4. 針對**DependencyAppxFiles，選取****流覽**以尋找並新增應用程式的任何相依性。 針對 Surface Hub，您將僅需要這些相依性的 x64 版本。

如果您是從應用程式商務用 Microsoft Store，您必須將應用程式授權新加到您的部署套件中。

**若要新增應用程式授權：**

1. 建立應用程式授權的複本，然後將它重新命名為使用 **.ms-windows-store-license** 副檔名。 例如，將"example.xml"重新命名為"example.ms-windows-store-license"。
2. 在 Windows設計工具中，前往****[可用的自訂設定執行時間  >  **設定**通用  >  **應用程式Install**  >  **DeviceCoNtextAppLicense>。**
3. 輸入**LicenseProductId，****然後選取**新增 。 為了保持一致性，請使用應用程式授權中的應用程式授權識別碼。 使用文字編輯器開啟授權檔案。 接著，在 **授權標記** 中，使用 **LicenseID 屬性中的** 值。
4. 選取新的 **[LicenseProductId]** 節點。 針對**LicenseInstall，** 選取流覽以尋找並選取您重新命名 (example.ms-windows-store-license) 。 ****

### <a name="add-a-policy-to-your-package"></a>新增原則至套件

Surface Hub 支援[原則設定服務提供者](/windows/client-management/mdm/policy-configuration-service-provider)中一部分的原則。 其中一些策略可以使用組Windows設計工具進行。

 **若要新增 [CSP 政策](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)：**

1. 前往 可用的**自訂專案**  >  **執行時間設定**  >  **策略**。
2. 選取您想要管理的元件，並設定適當的策略設定。 例如，若要防止員工使用 InPrivate 網站流覽Surface Hub **AllowInPrivate，** 然後選取**停用**。  

    > [!div class="mx-imgBorder"]
    > ![設定策略設定](images/sh-prov-policies.png)

### <a name="add-surface-hub-settings-to-your-package"></a>將 Surface Hub 設定新增至套件

您可以從 [SurfaceHub 設定服務提供者](/windows/client-management/mdm/surfacehub-csp)將設定新增到佈建套件。

1. 前往 可用的**自訂專案**  >  **一般小組版 設定。**
1. 選取您想要管理的元件，並設定適當的策略設定。
1. 當您完成配置套件時，請選取 檔案****  >  **儲存**。
1. 閱讀專案檔案可能包含敏感性資訊的警告， **然後選取確定**

### <a name="build-your-package"></a>建置您的套件

當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。  將專案檔案儲存在安全的位置，或刪除不再需要的專案檔案。

1. 開啟**Windows設計**  >  **工具匯出**  >  **置備套件**。
2. 將**擁有者變更****為 IT 系統管理員**。  
3. 設定 **[套件版本]** 的值，然後選取 **[下一步]**。

> [!TIP]
> 將擁有者設定為 IT 系統管理員可確保套件設定維持適當的「優先順序屬性」，Surface Hub如果其他布建套件後來從其他來源套用，則此設定仍然有效。

> [!TIP]
> 您可以修改現有的套件，並變更版本號碼以更新先前套用過的套件。

4. 選用：您可以選擇加密套件並啟用套件簽名：

    1. 選取 **加密套件** ，然後輸入密碼。
    1. 選取**簽署套件**  >  **流覽**，並在適當時選擇憑證。

    > [!IMPORTANT]
    > 建議您在部署套件中包含信任的部署憑證。 當套件套用至裝置時，憑證會新加到系統存放區，讓後續的套件以無提示方式套用。

5. 選取 **下一** 步以指定輸出位置。 Windows 設定設計工具預設會使用專案資料夾做為輸出位置。 或選取 **流覽** 以變更預設輸出位置。 選取 **[下一步]**。
6. 選取 **建立** 以開始建立套件。 專案資訊會顯示在建立頁面中。
7. 如果您的建立失敗，會顯示錯誤訊息，並包含專案資料夾的連結。 檢查記錄以診斷錯誤，然後再次嘗試建立套件。
8. 如果您的建置成功，系統會顯示部署套件、輸出目錄和專案目錄的名稱。 選取 **完成** 以關閉精靈，然後返回自訂頁面。
9. 選取  **輸出位置**  以前往套件的位置。 將 .ppkg 複製到空的 USB 快閃磁碟機。

## <a name="apply-a-provisioning-package-to-surface-hub"></a>將佈建套件套用到 Surface Hub

將佈建套件部署至 Surface Hub 有兩個選項。 [在第一](#apply-a-provisioning-package-during-first-run)次執行精靈期間，您可以套用安裝憑證的設定套件，或在首次執行的程式完成後，使用 設定 套用設定[、應用程式和憑證的設定套件](#apply-a-provisioning-package-using-settings-app)。

### <a name="apply-a-provisioning-package-during-first-run"></a>在初次執行期間套用佈建套件

> [!IMPORTANT]
> 在第一次執行的程式期間，您只能使用部署套件來安裝憑證。 使用 **[設定]** 應用程式安裝應用程式並套用其他設定。

1. 當您第一次開啟 Surface Hub時，第一次執行的程式會顯示[**"您好"頁面**](first-run-program-surface-hub.md)。 繼續之前，請確定已進行適當設定。
2. 將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。 如果套件位於磁碟機的根目錄中，初次執行程式將會識別它，並詢問您是否要設定裝置。 選取 **[設定]**。
3. 下一個畫面會要求您選取佈建來源。 選取 \[抽取式媒體\]**** 並點選 \[下一步\]****。
4. 選取要套用 (*.ppkg) 套件，然後點選下一 **步**。 請注意，您在初次執行期間只能安裝一個套件。
5. 初次執行程式會向您顯示佈建套件將套用的變更摘要。 選取 **\[是，請將它新增\]**。
6. 如果設定檔包含在 USB 快閃磁碟機的根目錄中，您將會看到 **\[選取設定\]**。 將會顯示設定檔中的第一個裝置帳戶，以及將套用到 Surface Hub 的帳戶資訊摘要。
7. 在 **選取群組原則中**，選取要申請的裝置名稱，然後選取下 **一步**。

佈建套件中的設定將套用到裝置上，OOBE 將會完成。 裝置重新開機後，您便可以移除 USB 快閃磁碟機。

### <a name="apply-a-provisioning-package-using-settings-app"></a>使用應用程式套用設定套件

1. 將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。
2. 從**Surface Hub開始設定**系統，並輸入系統管理認證。系統提示您輸入管理員認證。
3. 瀏覽至 **\[Surface Hub\]** > **\[裝置管理\]**。 在**置備套件下**，選取新增**或移除資源調配套件**  >  **新增套件**。
4. 選擇您的佈建套件，然後選取 **[新增]**。  出現提示時，請再次輸入您的系統管理員認證。
5. 您會看到要申請之變更的摘要。 選取 **\[是，請將它新增\]**。

## <a name="learn-more"></a>深入了解

- [下載Windows設計工具](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [建立 Windows 10 適用的佈建套件](/windows/configuration/provisioning-packages/provisioning-create-package)
- [使用 MDM 提供者管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)
