---
title: 建立佈建套件 (Surface Hub)
description: 針對 Windows 10，您可以透過佈建套件來設定使用登錄或設定服務提供者 (CSP) 的設定。
ms.assetid: 8AA25BD4-8A8F-4B95-9268-504A49BA5345
ms.reviewer: ''
manager: laurawi
keywords: 新增憑證, 佈建套件
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/16/2019
ms.localizationpriority: medium
ms.openlocfilehash: ecbeca9f0910f1fa1ff2721bcf1b745195552ca2
ms.sourcegitcommit: f74253629aaf073b35b1af69439f76e63392c5aa
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103797"
---
# 建立佈建套件 (Surface Hub)

本主題說明如何使用 Windows 設定設計工具建立佈建套件，並將它套用至 Surface Hub 裝置。 針對 Surface Hub，您可以使用佈建套件來新增憑證、安裝通用 Windows 平台 (UWP) 應用程式，並自訂原則和設定。

您可以在初次執行設定時使用隨身碟，或透過**設定**應用程式，來套用佈建套件。 


## 優點
-   不使用行動裝置管理 (MDM) 提供者，快速設定裝置。

-   不需要網路連線。

-   套用方式簡單。

[深入了解佈建套件的優點與用法。](https://technet.microsoft.com/itpro/windows/configure/provisioning-packages)


## 需求 

若要建立佈建套件並套用至 Surface Hub，您將需要下列項目：

-   Windows 設定設計工具，可從 透過 Microsoft Store 或 Windows 10 評定及部署套件 (ADK) 或安裝。 [了解如何安裝 Windows 設定設計工具。](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd)
-   USB 隨身碟。
-   如果您要使用**設定**應用程式套用該套件，您將需要裝置系統管理員認證。

您將會在執行 Windows10 的電腦上建立佈建套件、將套件儲存至 USB 磁碟機，然後將它部署到您的 Surface Hub。


## Surface Hub 佈建套件的支援項目

使用 **\[佈建 Surface Hub 裝置\]** 精靈，您可以：

- 註冊 Active Directory、Azure Active Directory 或 MDM 
- 建立網置系統管理員帳戶 
- 新增應用程式與憑證
- 設定 Proxy 設定
- 新增 Surface Hub 設定檔

>[!WARNING]
>您必須在 Windows 10 上執行 Windows 設定設計工具，才能使用精靈設定 Azure Active Directory 註冊。

使用進階佈建編輯器，您可以將這些項目新增到 Surface Hub 的佈建套件：

- **原則**：Surface Hub 支援[原則設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#surfacehubpolicies)中一部分的原則。 
- **設定**：您可以在 [SurfaceHub 設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)中設定任何設定。

>[!TIP]
> 使用精靈建立含有通用設定的套件，然後切換到進階編輯器以新增其他設定。
>
>![開啟進階編輯器](images/icd-simple-edit.png)

## 使用 Surface Hub 佈建精靈

[安裝 Windows 設定設計工具](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd) 後，您就可以建立佈建套件。

### 建立佈建套件 

1. 開啟 Windows 設定設定工具：
   - 從開始畫面或在 \[開始\] 功能表搜尋欄位，輸入「Windows 設定設計工具」，並按一下 Windows 設定設計工具捷徑。 
    
     或
    
   - 如果您是從 ADK 安裝 Windows 設定設計工具，請瀏覽至 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (在 x64 電腦上) 或 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (在 x86 電腦上)，然後按兩下 **ICD.exe**。

2. 按一下 **\[佈建 Surface Hub 裝置\]**。

3. 為您的專案命名，然後按一下 **\[下一步\]**。

### 進行設定

<table>
<tr><td style="width:45%" valign="top"><img src="images/one.png" alt="step one"/> <img src="images/add-certificates.png" alt="add certificates"/></br></br>若要使用憑證佈建裝置，請按一下 <strong>\[新增憑證\]</strong>。 輸入憑證的名稱，然後瀏覽至要使用的憑證並加以選取。</td><td><img src="images/add-certificates-details.png" alt="add a certificate"/></td></tr> 
<tr><td style="width:45%" valign="top"><img src="images/two.png" alt="step two"/>  <img src="images/proxy.png" alt="configure proxy settings"/></br></br>將 Proxy 設定切換為 <strong>\[是\]</strong> 或 <strong>\[否\]</strong>。 Surface Hub 的預設設定為自動偵測 Proxy 設定，因此如果這是您要的設定，您可以選取 <strong>\[否\]</strong>。 不過，如果您的基礎結構過去需要使用 Proxy 伺服器，但已變更為不需要 Proxy 伺服器，您可以選取 <strong>\[是\]</strong> 和 <strong>\[自動偵測設定\]</strong>，使用佈建套件將 Surface Hub 裝置還原回預設設定。 </br></br>如果您切換為 <strong>\[是\]</strong>，您可以選擇自動偵測 Proxy 設定，或者您可以輸入 URL 安裝指令碼或靜態 Proxy 伺服器位址以手動設定。 您也可以辨識是否要使用 Proxy 伺服器做為本機位址，並輸入例外狀況 (亦即 Surface Hub 不使用 Proxy 伺服器而直接連線的位址)。  </td><td><img src="images/proxy-details.png" alt="configure proxy settings"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/three.png" alt="step three"/>  <img src="images/set-up-device-admins.png" alt="device admins"/></br></br>您可以在 Active Directory 中註冊裝置，並指定安全性群組使用「設定」應用程式、註冊 Azure Active Directory 以允許全域系統管理員使用「設定」應用程式，或在裝置上建立本機系統管理員。</br></br>若要在 Active Directory 中註冊裝置，請輸入最低權限使用者帳戶的認證以將裝置加入網域，並指定該安全性群組在 Surface Hub 上擁有系統管理員認證。 當註冊 Active Directory 裝置的佈建套件正套用到已重設的 Surface Hub 時，如果所列的帳戶是網域系統管理員，或是最初設定 Surface Hub 的同一個帳戶，則只會使用相同的網域帳戶。 否則，必須在佈建套件中使用不同的網域帳戶。</br></br>在您使用 Windows 設定設計工具精靈設定大量 Azure AD 註冊前，請<a href="https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup" data-raw-source="[set up Azure AD join in your organization](https://docs.microsoft.com/azure/active-directory/active-directory-azureadjoin-setup)">設定 Azure AD 加入組織</a>。 您 Azure AD 租用戶中的 <strong>\[每位使用者的裝置數目上限\]</strong> 設定決定您在精靈中使用的大量權杖可使用多少次。 若要在 Azure AD 中註冊裝置，請選取該選項，並為您將使用精靈取得的大量權杖輸入易記的名稱。 設定權杖的到期日 (上限為自您取得權杖起的 30 天)。 按一下 <strong>\[Get bulk token\]</strong> (取得大量權杖)。 在 [ <strong> Let&#39;s 已登入 </strong> ] 視窗中，輸入擁有將裝置加入至 Azure AD 的許可權，然後輸入密碼的帳戶。 按一下 <strong>\[接受\]</strong> 將必要的權限授與 Windows 設定設計工具。</br></br>若要建立本機系統管理員帳戶，請選取該選項，並輸入使用者名稱與密碼。 </br></br><strong>重要：</strong>如果您在佈建套件中建立本機帳戶，您必須使用 <strong>\[設定\] </strong>應用程式每隔 42 天變更一次密碼。 如果在該期內沒有變更密碼，帳戶會被鎖，因而無法登入。  </td><td><img src="images/set-up-device-admins-details.png" alt="join Active Directory, Azure AD, or create a local admin account"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/four.png" alt="step four"/> <img src="images/enroll-mdm.png" alt="enroll in device management"/></br></br>將 MDM 中的註冊切換為 <strong>\[是\]</strong> 或 <strong>\[否\]</strong>。 </br></br>如果您切換為 <strong>\[是\]</strong>，則必須提供服務帳戶和密碼，或經授權註冊裝置的憑證指紋，此外也必須指定驗證類型。 如果您的 MDM 提供者需要，亦請輸入探索服務、註冊服務及原則服務的 URL。 <a href="manage-settings-with-mdm-for-surface-hub.md" data-raw-source="[Learn more about managing Surface Hub with MDM.](manage-settings-with-mdm-for-surface-hub.md)">深入了解使用 MDM 管理 Surface Hub。</a></td><td><img src="images/enroll-mdm-details.png" alt="enroll in mobile device management"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/five.png" alt="step five"/> <img src="images/add-applications.png" alt="add applications"/></br></br>您可以在佈建套件中安裝多個通用 Windows 平台 (UWP) 應用程式。 如需設定方面的協助，請參閱<a href="https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps" data-raw-source="[Provision PCs with apps](https://technet.microsoft.com/itpro/windows/configure/provision-pcs-with-apps)">使用應用程式佈建電腦</a> (英文)。 </br></br><strong>重要： </strong> 雖然嚮導介面可讓您選取傳統的 Win32 應用程式，但只能在將套用至 Surface Hub 的置備套件中包含 UWP app。 如果您包含傳統型 Win32 應用程式，佈建將會失敗。 </td><td><img src="images/add-applications-details.png" alt="add an application"/></td></tr>
<tr><td style="width:45%" valign="top"><img src="images/six.png" alt="step six"/>  <img src="images/add-config-file.png" alt="Add configuration file"/></br></br>您不&#39;t 設定此步驟中的任何設定。 它會提供指示以包含內含裝置帳戶清單的設定檔。 設定檔不得包含欄標頭。 當您將佈建套件套用到 Surface Hub 時，如果 USB 磁碟機上包含 Surface Hub 設定檔，您可以從檔案中選取帳戶及裝置的易記名稱。 請參閱<a href="#sample-configuration-file" data-raw-source="[Sample configuration file](#sample-configuration-file)">範例設定檔</a>中的範例。</br></br><strong>重要：設定檔案 </strong> 只能在全新設定體驗期間套用 (OOBE) ，且只能與使用 windows 10 版本1703發行的 Windows 配置設計工具所建立的預配套件搭配使用。  </td><td><img src="images/add-config-file-details.png" alt="Add a Surface Hub configuration file"/></td></tr>
<tr><td style="width:45%" valign="top">  <img src="images/finish.png" alt="finish"/></br></br>您可以設定密碼保護您的佈建套件。 當您將佈建套件套用到裝置上時，您必須輸入此密碼。</td><td><img src="images/finish-details.png" alt="Protect your package"/></td></tr>
</table>

完成時按一下 **\[建立\]**。 只需要幾秒鐘。 套件建置時，儲存套件的位置會在頁面底端顯示成超連結。

## 範例設定檔

Surface Hub 設定檔包含您的裝置可用來與 Exchange 和商務用 Skype 連線的裝置帳戶清單。 當您將佈建套件套用到 Surface Hub 時，您就可以在 USB 快閃磁碟機的根目錄中包括設定檔，然後選取所需的帳戶套用至該磁碟機。 設定檔只會在全新安裝體驗 (OOBE) 期間套用，且只能與使用隨 Windows 10 (版本 1703) 發行的 Windows 設定設計工具所建立的佈建套件搭配使用。

使用 Microsoft Excel 或其他 CSV 編輯器建立名為 `SurfaceHubConfiguration.csv` 的 CSV 檔。 在該檔案中，以下列格式輸入裝置帳戶及易記名稱清單︰

```console
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```
>[!IMPORTANT]
>由於設定檔會以純文字儲存裝置帳戶密碼，因此建議您將佈建套件套用到您的裝置後，請更新密碼。 您可以使用 [Surface Hub 設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) 中的 [DeviceAccount 節點](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp#deviceaccount)，來透過 MDM 更新密碼。


以下為 `SurfaceHubConfiguration.csv` 的範例。 

```console
Rainier@contoso.com,password,Rainier Surface Hub
Adams@contoso.com,password,Adams Surface Hub
Baker@contoso.com,password,Baker Surface Hub
Glacier@constoso.com,password,Glacier Surface Hub
Stuart@contoso.com,password,Stuart Surface Hub
Fernow@contoso.com,password,Fernow Surface Hub
Goode@contoso.com,password,Goode Surface Hub
Shuksan@contoso.com,password,Shuksan Surface Hub
Buckner@contoso.com,password,Buckner Surface Hub
Logan@contoso.com,password,Logan Surface Hub
Maude@consoto.com,password,Maude Surface hub
Spickard@contoso.com,password,Spickard Surface Hub
Redoubt@contoso.com,password,Redoubt Surface Hub
Dome@contoso.com,password,Dome Surface Hub
Eldorado@contoso.com,password,Eldorado Surface Hub
Dragontail@contoso.com,password,Dragontail Surface Hub
Forbidden@contoso.com,password,Forbidden Surface Hub
Oval@contoso.com,password,Oval Surface Hub
StHelens@contoso.com,password,St Helens Surface Hub
Rushmore@contoso.com,password,Rushmore Surface Hub
```

## 使用進階佈建

[安裝 Windows 設定設計工具](https://technet.microsoft.com/itpro/windows/configure/provisioning-install-icd) 後，您就可以建立佈建套件。

### 建立佈建套件 (進階)

1. 開啟 Windows 設定設定工具：
   - 從開始畫面或在 \[開始\] 功能表搜尋欄位，輸入「Windows 設定設計工具」，並按一下 Windows 設定設計工具捷徑。 
    
     或
    
   - 如果您是從 ADK 安裝 Windows 設定設計工具，請瀏覽至 `C:\Program Files (x86)\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86` (在 x64 電腦上) 或 `C:\Program Files\Windows Kits\10\Assessment and Deployment Kit\Imaging and Configuration Designer\x86\ICD.exe` (在 x86 電腦上)，然後按兩下 **ICD.exe**。

2. 按一下 **\[進階佈建\]**。
   
3. 為您的專案命名，然後按一下 **\[下一步\]**。

4. 選取 [ **通用至 Windows 10 小組**]，按一下 **[下一步**]，然後按一下 **[完成]**。

    ![ICD 新專案](images/icd-new-project.png)

5. 在專案中，選取 [ **可用的自訂**設定] 底下的 [ **常用團隊設定**]。

    ![ICD 通用設定](images/icd-common-settings.png)


### 將憑證新增到您的套件
您可以使用佈建套件來安裝憑證，讓裝置可向 Microsoft Exchange 驗證。

> [!NOTE]
> 佈建套件只能將憑證安裝到裝置 (本機電腦) 存放區，不能安裝到使用者存放區。 如果組織要求必須將憑證安裝到使用者存放區，請使用行動裝置管理 (MDM) 來部署這些憑證。 如需詳細資訊，請參閱您的 MDM 解決方案文件。

1. 在 **[可用的自訂項目]** 窗格中，移至 **[執行階段設定]** > **[憑證]** > **[ClientCertificates]**。 

2. 輸入 **CertificateName**，然後按一下 \[新增\]。**** 

2. 輸入 **CertificatePassword**。 

3. 針對 **[CertificatePath]**，瀏覽並選取要使用的憑證。 

4. 將 **[ExportCertificate]** 設定為 **[False]**。

5. 針對 **[KeyLocation]**，選取 **[僅限軟體]**。


### 將通用 Windows 平台 (UWP) 應用程式新增到套件
在將 UWP應用程式新增到佈建套件之前，您需要應用程式套件 (.appx 或 .appxbundle) 和任何的相依性檔案。 如果您從商務用 Microsoft Store 取得應用程式，您也需要*未編碼的*應用程式授權。 請參閱[散發離線應用程式](https://technet.microsoft.com/itpro/windows/manage/distribute-offline-apps#download-an-offline-licensed-app) (英文) 以了解如何從商務用 Microsoft Store 下載這些項目。

1. 在 **\[可用的自訂項目\]** 窗格中，移至** \[執行階段設定\]** > **\[UniversalAppInstall\]** > **\[DeviceContextApp\]**。

2. 針對應用程式輸入 **PackageFamilyName**，然後按一下 **[新增]**。 為了保持一致性，請使用應用程式的套件系列名稱。 如果您從商務用 Microsoft Store 取得應用程式，您可以在應用程式授權中找到套件系列名稱。 使用文字編輯器開啟授權檔案，並使用 [...] 標記之間的值。 \<PFM\> \</PFM\>

3. 針對 \[ApplicationFile\]，按一下 \[瀏覽\] 來尋找並選取目標 app (\*.appx 或 \*.appxbundle)。********

4. 針對 **[DependencyAppxFiles]**，按一下 **[瀏覽]** 來尋找並新增應用程式的任何相依性。 針對 Surface Hub，您將僅需要這些相依性的 x64 版本。

如果您從商務用 Microsoft Store 取得應用程式，您也需要將應用程式授權新增到佈建套件。

1. 建立應用程式授權的複本，然後將它重新命名為使用 **.ms-windows-store-license** 副檔名。 例如，"example.xml" 會變成 "example.ms-windows-store-license"。

2. 在 ICD 中，於 **[可用的自訂項目]** 窗格中，移至 **[執行階段設定]** > **[UniversalAppInstall]** > **[DeviceContextAppLicense]**。

3. 輸入 **LicenseProductId** 然後按一下 **[新增]**。 為了保持一致性，請使用應用程式授權中的應用程式授權識別碼。 使用文字編輯器開啟授權檔案。 然後，在 \<License\> 標記中使用 **LicenseID** 屬性中的值。

4. 選取新的 **[LicenseProductId]** 節點。 針對 **[LicenseInstall]**，按一下 **[瀏覽]** 來尋找並選取您在步驟 1 中重新命名的授權檔案。


### 新增原則至套件
Surface Hub 支援[原則設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)中一部分的原則。 其中一些原則可使用 ICD 進行設定。

1. 在 **[可用的自訂項目]** 窗格中，移至 **[執行階段設定]** > **[原則]**。

2. 選取其中一個可用的原則區域。

3. 選取您要新增至佈建套件的原則並加以設定。


### 將 Surface Hub 設定新增至套件 

您可以從 [SurfaceHub 設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)將設定新增到佈建套件。 

1. 在 [**可用的自訂**] 窗格中，移至 [**執行時間設定**]  >  **SurfaceHub**。

2. 選取其中一個可用的設定區域。

3. 選取您要新增至佈建套件的設定並加以設定。 


## 建置您的套件

1. 當您完成佈建套件設定作業之後，請按一下 \[檔案\] 功能表上的 \[儲存\]。********

2. 閱讀專案檔案可能包含機密資訊的警告，然後按一下 **[確定]**。

    > [!IMPORTANT]
    > 當您建置佈建套件時，您可能會在專案檔案與佈建套件 (.ppkg) 檔案中包含機密資訊。 雖然您可以選擇加密 .ppkg 檔案，但專案檔案不會加密。 您應該將專案檔案儲存在安全的位置，當專案檔案不再需要時將它刪除。

3. 在** \[匯出\] **功能表上，按一下 **\[佈建套件\]**。

4. 將 **[擁有者]** 變更為 **[IT 系統管理員]**，它會設定這個佈建套件的優先順序高於從其他來源套用到這個裝置的佈建套件。

5. 設定 **[套件版本]** 的值，然後選取 **[下一步]**。

    > [!TIP]
    > 您可以變更現有的套件，以及變更版本號碼來更新先前套用的套件。

6. 選用：您可以選擇加密套件並啟用套件簽署。

    -   **啟用套件加密** - 如果您選擇此選項，畫面上會顯示自動產生的密碼。

    -   **啟用套件簽署**：如果您選取此選項，您必須選取有效的憑證以簽署套件。 您可以按一下 **[瀏覽...]** 來指定憑證，並選擇您想要用來簽署套件的憑證。

        > [!IMPORTANT]
        > 我們建議您在佈建套件中包含受信任的佈建憑證。 將套件套用到裝置時，即會將憑證加入系統存放區，而且使用該憑證簽署的任何套件之後就能以無訊息方式套用。 

7. 按 \[下一步\]，以指定佈建套件建置後的輸出位置。**** Windows ICD 是預設使用專案資料夾做為輸出位置。<p>
您也可以按一下 **\[瀏覽\]** 來變更預設的輸出位置。

8. 按 **\[下一步\]**。

9. 按一下 **\[建置\]**，開始建置套件。 專案資訊會顯示在建置頁面，進度列可指示建置狀態。<p>
若要取消建置，請按一下 [取消] ****。 這會取消目前的建置程序、關閉精靈，並回到 [自訂項目頁面] ****。

10. 若建置失敗，就會顯示錯誤訊息，其中包含專案資料夾的連結。 您可以掃描記錄檔，以判斷造成錯誤的原因。 修正問題後，請嘗試重新建置套件。<p>
若建置成功，便會顯示佈建套件名稱、輸出目錄，以及專案目錄。

    -   您也可以選擇再次建置佈建套件，並為輸出套件挑選不同的路徑。 若要如此，請按一下 **\[返回\]** 以變更輸出套件名稱與路徑，然後按 **\[下一步\]** 以開始另一次建置。
    
    -   完成後，按一下 \[完成\]**** 以關閉精靈，並回到 \[自訂頁面\]****。

11. 選取 **[輸出位置]** 連結，以移至套件的位置。 將 .ppkg 複製到空的 USB 快閃磁碟機。


## 將佈建套件套用到 Surface Hub

將佈建套件部署至 Surface Hub 有兩個選項。 在[第一次執行嚮導期間](#apply-a-provisioning-package-during-first-run)，您可以套用安裝憑證的預配套件，或在第一次執行的程式完成後，您可以使用 [[設定](#apply-a-package-using-settings)] 來套用配置設定、應用程式及憑證的置備套件。 


### 在初次執行期間套用佈建套件

> [!IMPORTANT]
> 在第一次執行的程式中，您只能使用預配套件來安裝證書。 使用 **[設定]** 應用程式安裝應用程式並套用其他設定。

1. 當您第一次開啟 Surface Hub 時，初次執行程式將會顯示 [**[嗨，您好]** 頁面](first-run-program-surface-hub.md#first-page)。 繼續之前，請確定已進行適當設定。

2. 將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。 如果套件位於磁碟機的根目錄中，初次執行程式將會識別它，並詢問您是否要設定裝置。 選取 **[設定]**。

    ![設定裝置？](images/provisioningpackageoobe-01.png)

3. 下一個畫面會要求您選取佈建來源。 選取 \[抽取式媒體\]**** 並點選 \[下一步\]****。

    ![佈建此裝置](images/provisioningpackageoobe-02.png)
    
4. 選取您要套用的佈建套件 (\*.ppkg)，然後點選 **[下一步]**。 請注意，您在初次執行期間只能安裝一個套件。

    ![選擇套件](images/provisioningpackageoobe-03.png)

5. 初次執行程式會向您顯示佈建套件將套用的變更摘要。 選取 **\[是，請將它新增\]**。  

    ![您信任此套件嗎？](images/provisioningpackageoobe-04.png)
    
6. 如果設定檔包含在 USB 快閃磁碟機的根目錄中，您將會看到 **\[選取設定\]**。 將會顯示設定檔中的第一個裝置帳戶，以及將套用到 Surface Hub 的帳戶資訊摘要。

    ![選取設定](images/ppkg-config.png)    

7. 在 **\[選取設定\]** 中，選取要套用的帳戶名稱，然後按一下 **\[下一步\]**。

    ![選取易記的裝置名稱](images/ppkg-csv.png)
    
佈建套件中的設定將套用到裝置上，OOBE 將會完成。 裝置重新開機後，您便可以移除 USB 快閃磁碟機。

### 使用 \[設定\] 套用套件

1. 將包含 .ppkg 檔案的 USB 快閃磁碟機插入 Surface Hub。

2. 從 Surface Hub，啟動 **\[設定\]**，然後當出現提示時輸入系統管理員認證。

3. 瀏覽至 **\[Surface Hub\]** > **\[裝置管理\]**。 在 **\[佈建套件\]** 底下，選取 **\[新增或移除佈建套件\]**。

4. 選取 **[新增套件]**。

5. 選擇您的佈建套件，然後選取 **[新增]**。 您可能要重新輸入系統管理員認證 (若看到提示)。

6. 您會看到佈建套件將套用的變更摘要。 選取 **[是的，新增]**。


