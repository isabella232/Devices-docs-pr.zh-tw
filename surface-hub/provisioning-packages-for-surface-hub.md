---
title: 建立佈建套件
description: 針對Windows 10或Windows 11，可以使用布建套件來設定使用登錄或設定服務提供者 (CSP) 的設定。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: dpandre
manager: laurawi
keywords: 新增憑證, 佈建套件
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/20/2021
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 1f1e084b8be0ab44c853fe003236ba7f25b4ff4c
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497636"
---
# <a name="create-provisioning-packages-for-surface-hub"></a>建立 Surface Hub 的佈建套件

布建套件可讓您自動化重要功能的部署，協助在組織中的所有 Surface Hub 之間提供一致的體驗。  使用Windows設定設計工具 (個別電腦上的 WCD) ，您可以完成下列工作：

- 註冊 Active Directory 或 Azure Active Directory
- 建立裝置系統管理員帳戶
- 新增應用程式與憑證
- 設定 Proxy 設定
- 新增 Surface Hub 設定檔
- 設定設定 [服務提供者 (CSP) 設定](/windows/client-management/mdm/surfacehub-csp)

## <a name="overview"></a>概觀

1. 在執行 Windows 10 或 Windows 11 的個別電腦上，從[Microsoft Store安裝 Windows](https://www.microsoft.com/store/apps/9nblggh4tx22)設定設計工具。
1. 選[**取 [布建Surface Hub裝置**](#use-surface-hub-provisioning-wizard)]，以使用精靈設定一般設定。 或選取 [[進階布](#use-advanced-provisioning) 建] 以檢視和設定所有可能的設定。
1. 建立布建套件，並將其儲存至 USB 磁片磁碟機。
1. 在第一次執行安裝期間，或透過 設定 應用程式，將套件部署到您的Surface Hub。 若要深入瞭解，請 [參閱建立布建套件](/windows/configuration/provisioning-packages/provisioning-create-package)。

## <a name="use-surface-hub-provisioning-wizard"></a>使用Surface Hub布建精靈

1. 開Windows設定設計工具，然後選**取 [布建Surface Hub裝置]**。<br>
    ![使用Surface Hub布建精靈。](images/sh-prov-start.png)
    
2. 為您的專案命名，然後選取 **[下一步]**。

### <a name="add-certificates"></a>新增憑證

> [!div class="mx-imgBorder"]
> ![新增憑證。](images/sh-prov-cert.png)

若要使用憑證布建裝置，請選取 [ **新增憑證]**。 輸入憑證的名稱，然後流覽以選取要使用的憑證。  如需進階布建選項，請參閱下方 [將憑證新增至您的套件一](#add-a-certificate-to-your-package)節。

### <a name="configure-proxy-settings"></a>設定 Proxy 設定

> [!div class="mx-imgBorder"]
> ![設定 Proxy 設定。](images/sh-prov-proxy.png)

1. 將 Proxy 設定切換為 **\[是\]** 或 **\[否\]**。 根據預設，Surface Hub會自動偵測 Proxy 設定。 不過，如果您的基礎結構過去需要使用 Proxy 伺服器，但已變更為不需要 Proxy 伺服器，您可以選取 **\[是\]** 和 **\[自動偵測設定\]**，使用佈建套件將 Surface Hub 裝置還原回預設設定。
2. 如果您切換 [ **是**]，您可以選擇自動偵測 Proxy 設定，或輸入下列其中一項手動設定設定：

    - 安裝腳本的 URL。
    - 靜態 Proxy 伺服器位址和埠資訊。

3. 如果您想要使用安裝腳本或 Proxy 伺服器，請關閉 **[自動偵測設定]**。 您可以使用安裝腳本 *或* Proxy 伺服器，而不是兩者。
4. 輸入 (位址的例外狀況，Surface Hub在不使用 Proxy 伺服器) 的情況下直接連線到該位址。 **範例：** *.office365.com
5. 識別是否要將 Proxy 伺服器用於本機位址。

### <a name="set-up-device-admins"></a>設定裝置系統管理員

 > [!div class="mx-imgBorder"]
 > ![加入 Active Directory、Azure AD或建立本機系統管理員帳戶。](images/sh2-wcd.png)

您可以在 Active Directory 中註冊裝置，並指定安全性群組使用「設定」應用程式、註冊 Azure Active Directory 以允許全域系統管理員使用「設定」應用程式，或在裝置上建立本機系統管理員。

1. 若要在 Active Directory 中註冊裝置，請輸入最低權限使用者帳戶的認證以將裝置加入網域，並指定該安全性群組在 Surface Hub 上擁有系統管理員認證。 如果將套件套用至已重設的Surface Hub，您可以使用相同的網域帳戶，只要它是一開始設定Surface Hub的相同帳戶即可。 否則，必須在佈建套件中使用不同的網域帳戶。
2. 使用Windows設定設計工具來設定大量Azure AD註冊之前，請[規劃您的Azure AD聯結實作](/azure/active-directory/devices/azureadjoin-plan)。 您 Azure AD 租用戶中的 **\[每位使用者的裝置數目上限\]** 設定決定您在精靈中使用的大量權杖可使用多少次。
3. 若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。 設定權杖的到期日 (上限為自您取得權杖起的 30 天)。 選 **取 [取得大量權杖]**。 在 **\[Let's get you signed in\]** (讓我們將您登入) 視窗中，輸入具有權限將裝置加入 Azure AD 的帳戶，然後輸入密碼。 選**取 [接受**] 以提供Windows設定設計工具必要的許可權。
4. 若要建立本機系統管理員帳戶，請選取該選項，並輸入使用者名稱與密碼。

> [!IMPORTANT]
> 如果您在佈建套件中建立本機帳戶，您必須使用 **\[設定\]** 應用程式每隔 42 天變更一次密碼。 如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。

### <a name="enroll-in-third-party-mdm-provider"></a>註冊協力廠商 MDM 提供者

> [!div class="mx-imgBorder"]
> ![註冊協力廠商行動裝置管理。](images/sh-prov-mdm.png)

如果您使用協力廠商行動裝置管理 (MDM) 提供者，您可以使用本節來註冊Surface Hub。 若要註冊Intune，請先依照上一節所述的設定Azure AD加入，並遵循下列Intune檔中的指示：[快速入門：設定Windows 10/11 裝置的自動註冊](/mem/intune/enrollment/quickstart-setup-auto-enrollment)。

1. 針對協力廠商 MDM 中的註冊，切換 [ **是** ] 或 [ **否** ]。
2. 如果您切換 [ **是**]，請提供授權註冊裝置並指定驗證類型的服務帳戶和密碼或憑證指紋。
3. 如果您的 MDM 提供者需要，請輸入探索服務、註冊服務和原則服務的 URL。

 若要深入瞭解，請[參閱使用 MDM 提供者管理Surface Hub。](manage-settings-with-mdm-for-surface-hub.md)

### <a name="add-applications"></a>新增應用程式

> [!div class="mx-imgBorder"]
> ![新增應用程式。](images/sh-prov-apps.png)

您可以在佈建套件中安裝多個通用 Windows 平台 (UWP) 應用程式。 若要深入瞭解，請參閱 [使用應用程式布建電腦](/windows/configuration/provisioning-packages/provision-pcs-with-apps)。

> [!NOTE]
> 雖然Windows設定設計工具可讓您將傳統 Win32 應用程式新增至布建套件，Surface Hub只接受 UWP 應用程式。 如果您包含傳統型 Win32 應用程式，佈建將會失敗。

### <a name="add-a-configuration-file"></a>新增組態檔

除了此布建套件之外，您還可以使用Surface Hub設定檔，讓您更輕鬆地設定裝置。 Surface Hub組態檔包含連線到Exchange、Microsoft Teams或商務用 Skype的裝置帳戶清單，以及無線投影的「易記名稱」。

**若要建立Surface Hub組態檔：**

1. 開啟 Microsoft Excel (或其他.csv編輯器) ，建立名為SurfaceHubConfiguration.csv的 _.csv_檔案。

2. 以下列格式輸入裝置帳戶和易記名稱的清單：

    ```
    <DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
    ```

    > [!NOTE]
    > 設定檔不得包含欄標頭。 當包含在套用至Surface Hub的布建套件中時，您可以從檔案中選取裝置的帳戶和易記名稱。 若要建立.csv檔案，請使用 UPN 位址格式 (rainier@contoso.com) 或下層登入名稱格式 (contoso\rainier) 。

    rainier@contoso.com，password，Rainier Surface Hub

3. 將檔案儲存到您的專案資料夾，並使用您的布建套件將它複製到 USB 金鑰。

> [!NOTE]
> 組態檔只能在第一次執行安裝期間套用。

### <a name="password-protect-provisioning-package"></a>密碼保護布建套件

如果您選擇使用密碼，則每次將布建套件套用至裝置時都必須輸入密碼。

### <a name="complete-provisioning-wizard"></a>完成布建精靈

如果您只需要設定一般設定，請選取 **[完成**  >  ][**建立**]，然後跳至[[建置您的套件]](#build-your-package)區段。 或者，切換至 [進階布建] 以繼續設定設定。

## <a name="use-advanced-provisioning"></a>使用進階布建

> [!TIP]
> 使用精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定。<br><br> ![切換至進階編輯器。](images/icd-simple-edit.png)

1. 如果繼續上一節，請選取 **[切換至進階編輯**器]，否則**請開啟Windows設定設計工具**]，然後選取 [**進階布建]**。

   ![使用進階布建。](images/sh-prov-adv.png)

2. 為您的專案命名，然後選取 **[下一步]**。

3. 選**取 [通用Windows 10 團隊版**]，選取 [**下一步**]，然後選取 [**完成]**。

   ![WCD 新專案。](images/icd-new-project.png)

4. 在專案中的 [ **可用的自訂] 下**，選取 [ **一般小組設定]**。

   :::image type="content" alt-text="WCD 通用設定。" source="images/icd-common-settings.png":::

### <a name="add-a-certificate-to-your-package"></a>將憑證新增到您的套件

您可以使用佈建套件來安裝憑證，讓裝置可向 Microsoft Exchange 驗證。

> [!NOTE]
> 佈建套件只能將憑證安裝到裝置 (本機電腦) 存放區，不能安裝到使用者存放區。 如果您的組織要求將憑證安裝到使用者存放區，請使用中樞**設定**應用程式：**更新 &** **SecurityCertificatesImport**  >   >  **憑證。**
或者，您可以使用  [**MDM 原則**](manage-settings-with-mdm-for-surface-hub.md) 將憑證部署到裝置存放區或使用者存放區。

> [!TIP]
> **ClientCertificates**區段適用于具有私密金鑰的 .pfx 檔案;根 CA 的 .cer 檔案應放在**RootCertificates**區段，而**CACertificates**區段中的中繼 CA 則為 。

1. 在**Windows組態設計工具**  >  **][可用自訂]** 中，移至 **[執行時間設定**  >  ][憑**證**  >  **][CientCertificates]**。
2. 輸入 **CertificateName** 的標籤，然後選取 [ **新增]**。
3. 輸入 **CertificatePassword**。
4. 針對 **[CertificatePath]**，瀏覽並選取要使用的憑證。
5. 將 **[ExportCertificate]** 設定為 **[False]**。
6. 針對 \[KeyLocation\]，選取 \[僅限軟體\]。********

### <a name="add-a-uwp-app-to-your-package"></a>將 UWP 應用程式新增至您的套件

若要將 UWP 應用程式新增至布建套件，您需要應用程式套件 (.appx 或 .appxbundle 檔案) 和任何相依性檔案。 如果您從商務用 Microsoft Store 取得應用程式，您也需要*未編碼的*應用程式授權。 請參閱[散發離線應用程式](/microsoft-store/distribute-offline-apps) (英文) 以了解如何從商務用 Microsoft Store 下載這些項目。

**若要新增 UWP 應用程式：**

1. 在 **\[可用的自訂項目\]** 窗格中，移至** \[執行階段設定\]** > **\[UniversalAppInstall\]** > **\[DeviceContextApp\]**。

2. 輸入應用程式的 **PackageFamilyName** ，然後選取 [ **新增]**。 為了保持一致性，請使用應用程式的套件系列名稱。 如果您從商務用 Microsoft Store 取得應用程式，您可以在應用程式授權中找到套件系列名稱。 使用文字編輯器開啟授權檔案，並在 PFM 標記之間使用 值。

3. 針對 **[ApplicationFile**]，選取 [ **流覽** ] 以尋找並選取目標應用程式 ( .appx 或 .appxbundle) 。

4. 針對 **[DependencyAppxFiles]**，選取 [ **流覽** ] 以尋找並新增應用程式的任何相依性。 針對 Surface Hub，您將僅需要這些相依性的 x64 版本。

如果您從商務用 Microsoft Store取得應用程式，您必須將應用程式授權新增至布建套件。

**若要新增應用程式授權：**

1. 建立應用程式授權的複本，然後將它重新命名為使用 **.ms-windows-store-license** 副檔名。 例如，將 「example.xml」 重新命名為 「example.ms-windows-store-license」。

2. 在Windows組態設計工具中，移至 **[可用的自訂]**  >  [**執行時間設定**  >  ][UniversalAppInstallDeviceCoNtextAppLicense****  >  **]**。

3. 輸入 **LicenseProductId** ，然後選取 [ **新增]**。 為了保持一致性，請使用應用程式授權中的應用程式授權識別碼。 使用文字編輯器開啟授權檔案。 然後，在 **[授權]** 標籤中，使用 **LicenseID** 屬性中的值。

4. 選取新的 **[LicenseProductId]** 節點。 針對 **[授權][安裝**]，選取 [ **流覽** ] 以尋找並選取您重新命名的授權檔案 (example.ms-windows-store-license) 。

### <a name="add-a-policy-to-your-package"></a>新增原則至套件

Surface Hub 支援[原則設定服務提供者](/windows/client-management/mdm/policy-configuration-service-provider)中一部分的原則。 其中有些原則可以使用 Windows 設定設計工具來設定。

 **若要新增 [CSP 原則](/windows/client-management/mdm/policies-in-policy-csp-supported-by-surface-hub)：**

1. 移至 **[可用的自訂]**  >  [**執行時間設定**  >  **][原則]**。
2. 選取您想要管理的元件，並視需要設定原則設定。 例如，若要防止員工在Surface Hub上使用 InPrivate 網站流覽，請選取 **[AllowInPrivate**]，然後選取 [**停用]**。  

   :::image type="content" alt-text="設定原則設定。" source="images/sh-prov-policies.png" lightbox="images/sh-prov-policies.png":::

### <a name="add-surface-hub-settings-to-your-package"></a>將 Surface Hub 設定新增至套件

您可以從 [SurfaceHub 設定服務提供者](/windows/client-management/mdm/surfacehub-csp)將設定新增到佈建套件。

1. 移至 **[可用的自訂]**  >  **[Common Team Edition 設定**]。
1. 選取您想要管理的元件，並視需要設定原則設定。
1. 當您完成布建套件的設定時，請選取 **[檔案**  >  **][儲存]**。
1. 閱讀專案檔可能包含敏感性資訊的警告，然後選取 [ **確定]**

### <a name="build-your-package"></a>建置您的套件

當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。  將專案檔儲存在安全的位置，或在不再需要時刪除。

1. 開**Windows設定設計工具**  >  **ExportProvisioning**  >  **套件**。

2. 將 **擁有者** 變更為 **IT 系統管理員**。  

3. 設定 **[套件版本]** 的值，然後選取 **[下一步]**。

   > [!TIP]
   > 將擁有者設定為 IT 系統管理員可確保套件設定會維持適當的「優先順序屬性」，並在後續從其他來源套用其他布建套件時，在Surface Hub上維持作用。

   > [!TIP]
   > 您可以修改現有的套件，並變更版本號碼以更新先前套用的套件。

4. 選擇性：您可以選擇加密套件並啟用套件簽署：

    1. 選取 **[加密套件** ]，然後輸入密碼。
    1. 選**取 [簽署套件**  >  **][流覽]**，並視需要選擇憑證。

    > [!IMPORTANT]
    > 建議您在布建套件中包含受信任的布建憑證。 當套件套用至裝置時，憑證會新增至系統存放區，讓後續套件能夠以無訊息方式套用。

5. 選 **取 [下一步** ] 以指定輸出位置。 Windows 設定設計工具預設會使用專案資料夾做為輸出位置。 或選取 **[流覽** ] 以變更預設輸出位置。 選取 **[下一步]**。

6. 選 **取 [建置** ] 以開始建置套件。 專案資訊會顯示在建置頁面中。

7. 如果您的建置失敗，會出現錯誤訊息，其中包含專案資料夾的連結。 檢閱記錄以診斷錯誤，並嘗試再次建置套件。

8. 如果您的組建成功，則會顯示布建套件、輸出目錄和專案目錄的名稱。 選 **取 [完成** ] 以關閉精靈，然後返回 [自訂] 頁面。

9. 選  **取輸出位置**  以移至封裝的位置。 將 .ppkg 複製到空的 USB 快閃磁碟機。

## <a name="apply-a-provisioning-package-to-surface-hub"></a>將佈建套件套用到 Surface Hub

有兩種方式可將布建套件部署至Surface Hub：

- [第一次執行安裝程式。](#apply-a-provisioning-package-during-first-run) 您可以套用布建套件來自訂多個選項，包括Wi-Fi設定、Proxy 設定、裝置帳戶詳細資料、Azure AD聯結和相關設定。  
- [設定應用程式。](#apply-a-provisioning-package-using-settings-app) 第一次執行安裝程式之後，您可以透過設定應用程式套用布建套件。 

### <a name="apply-a-provisioning-package-during-first-run"></a>在初次執行期間套用佈建套件

1. 當您第一次開啟Surface Hub時，初次執行的程式會顯示 [[**您好] 頁面**](first-run-program-surface-hub.md)。 繼續之前，請確定已進行適當設定。

2. 將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。 如果套件位於磁碟機的根目錄中，初次執行程式將會識別它，並詢問您是否要設定裝置。 選取 **[設定]**。

3. 下一個畫面會要求您選取佈建來源。 選取 \[抽取式媒體\]**** 並點選 \[下一步\]****。

4. 選取您要套用的布建套件 (*.ppkg) ，然後點選 [ **下一步]**。 請注意，您在初次執行期間只能安裝一個套件。

5. 初次執行程式會向您顯示佈建套件將套用的變更摘要。 選取 **\[是，請將它新增\]**。

6. 如果設定檔包含在 USB 快閃磁碟機的根目錄中，您將會看到 **\[選取設定\]**。 將會顯示設定檔中的第一個裝置帳戶，以及將套用到 Surface Hub 的帳戶資訊摘要。

7. 在 **[選取設定**] 中，選取要套用的裝置名稱，然後選取 [ **下一步]**。

佈建套件中的設定將套用到裝置上，OOBE 將會完成。 裝置重新開機後，您便可以移除 USB 快閃磁碟機。

### <a name="apply-a-provisioning-package-using-settings-app"></a>使用設定應用程式套用布建套件

1. 將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。
2. 從Surface Hub，啟動**設定**，並在出現提示時輸入系統管理員認證。
3. 瀏覽至 **\[Surface Hub\]** > **\[裝置管理\]**。 在 [**布建套件] 底**下，選取 **[新增或移除布建套**  >  件 **][新增套件]**。
4. 選擇您的佈建套件，然後選取 **[新增]**。  如果出現提示，請再次輸入您的系統管理員認證。
5. 您會看到要套用的變更摘要。 選取 **\[是，請將它新增\]**。

## <a name="learn-more"></a>深入了解

- [下載Windows組態設計工具](https://www.microsoft.com/store/apps/9nblggh4tx22)
- [建立佈建套件](/windows/configuration/provisioning-packages/provisioning-create-package)
- [使用 MDM 提供者管理 Surface Hub](manage-settings-with-mdm-for-surface-hub.md)
