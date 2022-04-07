---
title: 在 Surface Hub 上安裝漸進式Web Apps
description: 說明系統管理員如何透過Intune或布建套件，在Surface Hub上安裝漸進式Web Apps (PWA) 。
keywords: Surface Hub、PWA、應用程式
ms.reviewer: dpandre
manager: laurawi
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/22/2022
ms.localizationpriority: medium
audience: ITPro
ms.openlocfilehash: ea30f25451b0be54bd2b6eaa2552036e0d78ff27
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472707"
---
# <a name="install-progressive-web-apps-on-surface-hub"></a>在 Surface Hub 上安裝漸進式Web Apps

系統管理員可以使用行動裝置管理提供者 (MDM) ，例如 Microsoft Intune 或布建套件，在 Surface Hub 上遠端安裝漸進式Web Apps ([PWA](/microsoft-edge/progressive-web-apps-chromium/)) 。 PWA 的運作方式如同在支援的平臺上安裝的原生應用程式，而且其運作方式就像其他瀏覽器上的一般網站一樣。 當系統管理員在Surface Hub上安裝 PWA 時，使用者可以直接從 [應用程式] 功能表執行它們。 

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

    :::image type="content" source="images/pwa-hubpwainstall.png" alt-text="建立Intune組態設定檔" :::

5. 為設定檔命名，輸入選擇性描述，然後選取 [ **下一步]**。

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="名稱設定檔" :::

### <a name="configure-force-installed-web-apps-policy-intune"></a>設定強制安裝Web Apps原則 (Intune) 

1. 選**Microsoft Edge**設定]，然後在 [搜尋] 方塊中輸入**force-installed**，選取 **[強制安裝Web Apps**]，然後選取 [**已啟用]**。

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="設定強制安裝的Web Apps" :::

2. 在 [**要以無訊息方式安裝Web Apps的 URL**下，從下列語法建立 XML 程式碼片段，或從下列范[例](#example-pwas)複製。 

    ```
    [ { "url": "https://www.contoso.com ",   "default_launch_container": "window" }, 
    
   { "url": "https://www.fabrikam.com/",   "default_launch_container": "tab"  }, ]
    ```
    
#### <a name="example-pwas"></a>範例 PWA

此範例會安裝適用于 YoutTube、Webex、Zoom 和 Uber 的 PWA。

```
    [
{ "url": "https://www.youtube.com/",       "default_launch_container": "window" },
{ "url": "https://signin.webex.com/join",  "default_launch_container": "window" },
{ "url": "https://zoom.us/join",           "default_launch_container": "window" },
{ "url": "https://www.uber.com/",          "default_launch_container": "tab"}
]
```

3. 輸入程式碼片段，其中包含您想要安裝之應用程式的 URL。
4. 視需要輸入選用的 [範圍標籤]，然後選取 [ **下一步]。**
5. 視需要指派給使用者。
6. 指派給包含您想要設為目標之 Surface Hub 的群組。 若要深入瞭解，請 [參閱新增群組以組織使用者和裝置](/mem/intune/fundamentals/groups-add)
7. 檢閱 ，然後選取 [ **建立]**。

    :::image type="content" source="images/pwa-hubwebappscreateprofile.png" alt-text="建立設定檔" :::
    

8. 視需要同步處理目標裝置。
9. 在Surface Hub上，啟動 Edge。 PWA 會安裝並出現在 [所有應用程式[開始] 功能表清單中。

## <a name="install-pwas-via-provisioning-package"></a>透過布建套件安裝 PWA

您可以使用 USB 磁片磁碟機將布建套件套用至 Surface Hub，以安裝 PWA。 若要深入瞭解，請參閱 [建立布建套件](/surface-hub/provisioning-packages-for-surface-hub#use-surface-hub-provisioning-wizard)。

### <a name="get-started-with-provisioning"></a>布建開始

1. 在執行 Windows 10 或 Windows 11 的個別電腦上，從[Microsoft Store 安裝 Windows](https://www.microsoft.com/store/apps/9nblggh4tx22)設定設計工具 (WCD) 。
2. 在 WCD 中，建立新的Project。 選 **取 [布建桌面裝置]，** 提供專案的名稱，然後選擇 [ **完成]。**
3. 選 **取 [切換至進階編輯器]** ，然後選取 [ **是** ] 以確認。

### <a name="configure-msedgepolicy"></a>設定 MSEdgePolicy

1. 在 WCD 的 [可用的自訂] 窗格中，移至**\Runtime 設定\ADMXIngestion\ConfigOperations\ADMXInstall\AppName**
2. 在 [自訂編輯] 窗格中，輸入應用程式名稱做為 **MSEdgePolicy** ，然後選取 [ **新增]**。

    :::image type="content" source="images/pwa-add-edge-policy.png" alt-text="輸入應用程式名稱作為 MSEdgePolicy" :::

3. 在 [可用的自訂] 窗格中，選取 **[AppName： MSEdgePolicy]** ，然後在編輯窗格中，將 **[SettingType]** 變更為 [ **原則]** ，然後選擇 [ **新增]**。
4. 在 [可用的自訂] 窗格中，選取 [ **設定類型：原則** ]，然後在編輯窗格中，將 **AdmxFileUid** 設定為 **MSEdgePolicy，** 然後選擇 [ **新增]**。
5. 在 [可用的自訂] 窗格中，選取 **[AdmxFileUid： MSEdgePolicy** ]，然後在編輯窗格中，以單行文字輸入下列程式碼來設定 **MSEdgePolicy** ：

   :::image type="content" source="images/pwa-enter-edge-policy.png" alt-text="輸入 MSEdgePolicy 的程式碼" :::   
   
    ```
    <policyDefinitions revision="1.0" schemaVersion="1.0" xmlns="http://www.microsoft.com/GroupPolicy/PolicyDefinitions">  <!--microsoft_edge version: 96.0.1054.53-->  <policyNamespaces>    <target namespace="Microsoft.Policies.Edge" prefix="microsoft_edge"/>    <using namespace="Microsoft.Policies.Windows" prefix="windows"/>  </policyNamespaces>  <resources minRequiredRevision="1.0"/>  <supportedOn>    <definitions>      <definition displayName="$(string.SUPPORTED_WIN7_V80)" name="SUPPORTED_WIN7_V80"/>     </definitions>  </supportedOn>  <categories>    <category displayName="$(string.microsoft_edge)" name="microsoft_edge"/>    <category displayName="$(string.microsoft_edge_recommended)" name="microsoft_edge_recommended"/>  </categories>  <policies>    <policy class="Both" displayName="$(string.WebAppInstallForceList)" explainText="$(string.WebAppInstallForceList_Explain)" key="Software\Policies\Microsoft\Edge" name="WebAppInstallForceList" presentation="$(presentation.WebAppInstallForceList)">      <parentCategory ref="microsoft_edge"/>      <supportedOn ref="SUPPORTED_WIN7_V80"/>      <elements>        <text id="WebAppInstallForceList" maxLength="1000000" valueName="WebAppInstallForceList"/>      </elements>    </policy>    </policies></policyDefinitions>
    ```
 
### <a name="configure-force-installed-web-apps-policy-provisioning-package"></a>設定強制安裝Web Apps原則 (布建套件) 

1. 在 WCD 的 [可用的自訂] 窗格中，移至：**\Runtime 設定\ADMXIngestion\ConfigADMXInstalledPolicy\AreaName**
2. 在 [自訂編輯] 窗格中，輸入 Areaname 作為 **MSEdgePolicy~Policy~microsoft_edge，** 然後選取 [ **新增]**。
3. 在 [可用的自訂] 窗格中，選取 **[區功能變數名稱稱：MSEdgePolicy~Policy~microsoft_edge** ]，然後在編輯窗格中，將 [ **原則名稱** ] 設定為 **[WebAppInstallForceList]** ，然後選取 [ **新增]**。
4. 在 [可用的自訂] 窗格中，選取 [ **原則名稱：WebAppInstallForceList]** ，然後在 **WebAppInstallForceList** 的編輯窗格中，以單行文字輸入下列程式碼。

    :::image type="content" source="images/pwa-force-web-app-install.png" alt-text="輸入強制安裝Web Apps原則的程式碼" :::   

 > [!TIP]
 > 本範例會將 You Tube 安裝為PWA。 適當地取代 URL。 

```
    <enabled/><data id="WebAppInstallForceList" value="[{&quot;url&quot;: &quot;https://www.youtube.com&quot;, &quot;create_desktop_shortcut&quot;: true, &quot;default_launch_container&quot;: &quot;window&quot;}]"/>
```    

### <a name="export-provisioning-package-and-apply-to-surface-hubs"></a>匯出布建套件並套用至 Surface Hub

1. 在功能表列中，選取 [ **匯出**]，選取 [ **布建套件** ]，然後依照提示產生 .ppkg 檔案。
2. 插入空的 USB 快閃磁片磁碟機。 選取輸出位置以移至封裝的位置。 將 .ppkg 檔案複製到 USB 磁片磁碟機。
3. 透過設定應用程式或初次執行安裝期間套用布建套件。 若要深入瞭解，請 [參閱建立布建套件](/surface-hub/provisioning-packages-for-surface-hub#apply-a-provisioning-package-to-surface-hub)

## <a name="learn-more"></a>深入了解

- [WCD 參考：ADMXIngestion](/windows/configuration/wcd/wcd-admxingestion)
- [漸進式Web Apps (PWA) 概觀](/microsoft-edge/progressive-web-apps-chromium/)
