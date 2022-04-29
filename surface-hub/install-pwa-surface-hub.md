---
title: 在 Surface Hub 上安裝漸進式 Web 應用程式
description: 說明系統管理員如何透過Intune或布建套件，在Surface Hub上安裝漸進式Web Apps (PWA) 。
keywords: Surface Hub、PWA、應用程式
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/27/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: 687dd85d3490d420133edc5b7de3b2af0c0433ef
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497533"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>在 Surface Hub 上安裝漸進式 Web 應用程式

漸進式 Web 應用程式 (PWA) 支援會開啟豐富的新應用程式來源，大幅擴充可在 Suface Hub 上執行的可用應用程式程式庫。  使用者可以在Microsoft Store外部存取豐富的應用程式，並直接從 [應用程式] 功能表執行這些應用程式。  相較于網頁，PWA 的行為更像具有離線功能的原生應用程式、在背景中更新的能力，以及其他獨特的功能。 大部分的網站都可以安裝為 PWA，並利用 Web 開發人員所啟用的任何其他功能。

系統管理員可以透過行動裝置管理 (MDM) 提供者，從遠端安裝 Surface Hub 上的 PWA，例如 Microsoft Intune。 或者，您可以使用布建套件。 本文說明這兩種方法，其中包含安裝 YouTube、WebEx、Zoom 和 Uber 的範例程式碼，以及安裝您自己的 PWA 的指示。 若要深入瞭解，請參閱[漸進式Web Apps概觀](/microsoft-edge/progressive-web-apps-chromium/)。

> [!IMPORTANT]
> 安裝 PWA 之前，請確定您的Surface Hub已安裝[KB5011543](https://support.microsoft.com/help/5011543) (或後續Windows更新) 。 若要深入瞭解最新的Windows 10 團隊版更新，請參閱[Surface Hub更新歷程記錄](surface-hub-update-history.md)。

- [透過 Intune 在 Surface Hub 上安裝 PWA](#install-pwas-via-intune)
- [透過布建套件在Surface Hub上安裝 PWA](#install-pwas-via-provisioning-package)

使用者也可以安裝 PWA，以在其中樞會話期間使用。 會話結束時，會移除 PWA。 若要深入瞭解，請參閱[在 Microsoft Edge 中安裝、管理或卸載應用程式](https://support.microsoft.com/topic/install-manage-or-uninstall-apps-in-microsoft-edge-0c156575-a94a-45e4-a54f-3a84846f6113)

## <a name="install-pwas-via-intune"></a>透過 Intune 安裝 PWA

使用 Intune 或其他 MDM 提供者，在 Surface Hub 上安裝 PWA。 若要深入瞭解，請參閱 [使用 MDM 提供者管理設定](manage-settings-with-mdm-for-surface-hub.md)。

### <a name="get-started"></a>開始使用

1. 在 Microsoft 端點管理員 系統管理中心登入[**Intune入口網站**](https://endpoint.microsoft.com/)。

2. 移至 [**裝置**  >  ]**[設定原則******  >  **][建立設定檔]**。

3. 在 [平臺] 底下，選**取 [Windows 10及更新版本]**。 在 [配置檔案類型] 下，選取 **[範本]**。 在 [範本名稱] 底下，選取 [ **系統管理範本]。**

4. 選 **取 [建立]。**

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="建立Intune組態設定檔" lightbox="images/pwa-hubpwainstall.png":::

5. 為設定檔命名，輸入選擇性描述，然後選取 [ **下一步]**。

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="名稱設定檔" lightbox="images/pwa-hubwebappscreateprofile.png":::

### <a name="configure-force-installed-web-apps-policy-intune"></a>設定強制安裝Web Apps原則 (Intune) 

1. 在 **[所有設定**  >  **電腦**組態] 下，選**取 [Microsoft Edge**]，然後在 [搜尋] 方塊中輸入**force-installed**，選取 [**強制安裝Web Apps**]，然後選取 [**已啟用]**。

    :::image type="content" source="images/pwa-enable-force-install.png" alt-text="啟用強制安裝的 Web 應用程式" lightbox="images/pwa-enable-force-install.png":::

2. 在 [**要以無訊息方式安裝Web Apps的 URL**下，複製並輸入下列程式碼片段，以安裝適用于 YouTube、Webex、Zoom 和 Uber 的 PWA。 或跳至下一個步驟以安裝其他 PWA。

    :::image type="content" source="images/hub-pwa-install-enable.png" alt-text="輸入強制安裝的 Web 應用程式清單" lightbox="images/hub-pwa-install-enable.png":::

    ```json
    [
    { "url": "https://www.youtube.com/",       "default_launch_container": "window" },
    { "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
    { "url": "https://zoom.us/join",           "default_launch_container": "window" },
    { "url": "https://www.uber.com/",          "default_launch_container": "tab"}
    ]
    ```

3. 或者，您可以從下列語法建立 JSON 程式碼片段，以安裝其他 PWA。

    ```json
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  } ]
    ```

4. 在 [範圍標籤] 頁面上，選取 [ **下一步** ] 以略過。

5. 在 [指派] 頁面的 [ **包含的群組**] 下，選取 [ **新增群組]**。

    :::image type="content" source="images/pwa-add-groups.png" alt-text="新增群組" lightbox="images/pwa-add-groups.png" :::

6. 在 [ **選取要包含的群組**] 底下，輸入包含您要設為目標之 Surface Hub 的群組名稱，選擇 [ **選取**]，然後按 [ **下一步]**。 若要深入瞭解如何將組態設定檔指派給群組，請參閱 [新增群組來組織使用者和裝置](/mem/intune/fundamentals/groups-add)。

    :::image type="content" source="images/pwa-select-groups.png" alt-text="選取群組" lightbox="images/pwa-select-groups.png":::

7. 檢閱 ，然後選取 [ **建立]**。

    :::image type="content" source="images/pwa-create-profile.png" alt-text="建立設定檔" lightbox="images/pwa-create-profile.png" :::

8. 若要以固定方式套用組態設定檔，請選取 [**裝置**  >  **][所有裝置]**，然後尋找您設為目標的裝置。 開啟其 [概觀] 窗格，然後選取 [ **同步]**。

    :::image type="content" source="images/pwa-sync-tenant.png" alt-text="同步租使用者" lightbox="images/pwa-select-groups.png":::

 > [!IMPORTANT]
 > 若要完成 PWA 的安裝，請移至您的Surface Hub並啟動 Edge。 PWA 會安裝並出現在 [所有應用程式[開始] 功能表清單中。

 ### <a name="troubleshooting-intune-managed-pwas"></a>針對Intune管理的 PWA 進行疑難排解
 
如果您沒有看到 PWA 列在 **[所有應用程式] 下：**

- 請確定您的Surface Hub具有最新的更新，特別是[KB5011543](https://support.microsoft.com/help/5011543) (或後續的Windows更新) 。 若要深入瞭解最新的Windows 10 團隊版更新，請參閱[Surface Hub更新歷程記錄](surface-hub-update-history.md)。
- 檢查以確定組態設定檔已成功套用，而且與其他設定沒有任何衝突。 
- 檢查以確定組態設定檔是以包含您Surface Hub的安全性群組為目標。 
- 請記得在您的Surface Hub上啟動 Edge 一次，這是Intune受控 PWA 成功安裝的必要專案。

## <a name="install-pwas-via-provisioning-package"></a>透過布建套件安裝 PWA

您可以使用 USB 磁片磁碟機將布建套件套用至 Surface Hub，以安裝 PWA。 若要深入瞭解，請參閱 [建立布建套件](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard)。

### <a name="get-started-with-provisioning"></a>布建開始

1. 在執行 Windows 10 或 Windows 11 的個別電腦上，從[Microsoft Store 安裝 Windows](https://www.microsoft.com/store/apps/9nblggh4tx22)設定設計工具 (WCD) 。

2. 在 WCD 中，建立新的Project。 選 **取 [布建桌面裝置]，** 提供專案的名稱，然後選擇 [ **完成]。**

3. 選 **取 [切換至進階編輯器]** ，然後選取 [ **是** ] 以確認。

### <a name="configure-msedgepolicy"></a>設定 MSEdgePolicy

1. 在 WCD 的 [可用的自訂] 窗格中，移至**\Runtime 設定\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**

2. 在 [自訂編輯] 窗格中，輸入應用程式名稱做為 **MSEdgePolicy** ，然後選取 [ **新增]**。

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="輸入應用程式名稱作為 MSEdgePolicy" lightbox="images/pwa-add-edge-policy.png" :::

3. 在 [可用的自訂] 窗格中，選取 **[AppName： MSEdgePolicy]** ，然後在編輯窗格中，將 **[SettingType]** 變更為 [ **原則]** ，然後選擇 [ **新增]**。

4. 在 [可用的自訂] 窗格中，選取 [ **設定類型：原則** ]，然後在編輯窗格中，將 **AdmxFileUid** 設定為 **MSEdgePolicy，** 然後選擇 [ **新增]**。

5. 在 [可用的自訂] 窗格中，選取 **[AdmxFileUid： MSEdgePolicy** ]，然後在編輯窗格中，以單行文字輸入下列程式碼來設定 **MSEdgePolicy** ：

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="輸入 MSEdgePolicy 的程式碼" lightbox="images/pwa-enter-edge-policy.png" :::

    ```xml
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```

### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>設定強制安裝Web Apps原則 (布建套件) 

1. 在 WCD 的 [可用的自訂] 窗格中，移至：**\Runtime 設定\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**

2. 在 [自訂編輯] 窗格中，輸入 Areaname 作為 **MSEdgePolicy~Policy~microsoft_edge，** 然後選取 [ **新增]**。

3. 在 [可用的自訂] 窗格中，選取 **[區功能變數名稱稱：MSEdgePolicy~Policy~microsoft_edge** ]，然後在編輯窗格中，將 [ **原則名稱** ] 設定為 **[WebAppInstallForceList]** ，然後選取 [ **新增]**。

4. 在 [可用的自訂] 窗格中，選取 [**原則名稱：WebAppInstallForceList**]，然後在**WebAppInstallForceList**的編輯窗格中，輸入[PWA程式碼](#ppkg-code-samples)作為單行文字。

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="輸入強制安裝Web Apps原則的程式碼" lightbox="images/pwa-force-web-app-install.png":::

### <a name="ppkg-code-samples"></a>PPKG 程式碼範例

- YouTube PWA：

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- 多個 PWA，包括 YouTube、Webex、Zoom 和 Uber：

    ```xml
     <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.signin.webex.com/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://zoom.us/join&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;},{&quot;url&quot;: &quot;https://www.uber.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

- 或者，您可以從下列語法建立 JSON 程式碼片段，以安裝其他 PWA：

    ```xml
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.contoso.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
    ```

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>匯出布建套件並套用至 Surface Hub

1. 在功能表列中，選取 [ **匯出**]，選取 [ **布建套件** ]，然後依照提示產生 .ppkg 檔案。

2. 插入空的 USB 快閃磁片磁碟機。 選取輸出位置以移至封裝的位置。 將 .ppkg 檔案複製到 USB 磁片磁碟機。

3. 透過設定應用程式或初次執行安裝期間套用布建套件。 若要深入瞭解，請 [參閱建立布建套件](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

 ### <a name="troubleshooting-provisioning-package-pwas"></a>針對布建套件 PWA 進行疑難排解
 
如果您沒有看到 PWA 列在 **[所有應用程式] 下**：

- 請確定您的Surface Hub具有最新的更新，特別是[KB5011543](https://support.microsoft.com/help/5011543) (或後續的Windows更新) 。 若要深入瞭解最新的Windows 10 團隊版更新，請參閱[Surface Hub更新歷程記錄](surface-hub-update-history.md)。

## <a name="learn-more"></a>深入了解

- [WCD 參考：ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [漸進式Web Apps (PWA) 概觀](/microsoft-edge/progressive-web-apps-chromium/)
