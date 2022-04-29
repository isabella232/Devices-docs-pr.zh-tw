---
title: 使用 MDM 提供者管理設定 (Surface Hub)
description: Microsoft Surface Hub 提供企業管理解決方案，協助 IT 系統管理員使用行動裝置管理 (MDM) 解決方案來管理裝置上的原則和商務應用程式。
ms.assetid: 18EB8464-6E22-479D-B0C3-21C4ADD168FE
ms.reviewer: ''
manager: laurawi
keywords: 行動裝置管理, MDM, 管理原則
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: e126799fe023d97468e58c01b003ce4b605f2db7
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497786"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>使用 MDM 提供者管理 Surface Hub

Surface Hub可讓 IT 系統管理員使用行動裝置管理 (MDM) 提供者來管理設定和原則，例如 Microsoft Intune。 Surface Hub具有內建的管理元件，可與管理伺服器通訊。 不需要在裝置上安裝其他用戶端。

## <a name="enrolling-surface-hub-into-mdm-management"></a>將Surface Hub註冊到 MDM 管理 

您可以透過手動或自動註冊，將 Surface 註冊到 Microsoft Intune 或其他 MDM 提供者。

### <a name="manual-enrollment"></a>手動註冊

1. 開啟**設定**應用程式，並以本機系統管理員身分登入。 選**Surface Hub**  >  裝置**管理**]，然後選取 **[+裝置管理]**。
2. 系統會提示您使用帳戶登入，以用於您的 MDM 提供者。 驗證之後，裝置會自動向您的 MDM 提供者註冊。

> [!TIP]
> 如果您使用Intune，且未偵測到伺服器位址，請輸入**manage.microsoft.com**。
   
> [!NOTE]
> MDM 註冊會使用提供給驗證的帳戶詳細資料。 帳戶必須具有註冊Windows裝置的許可權，以及Intune授權 (或在協力廠商 MDM 提供者) 中設定的對等註冊程式。

### <a name="auto-enrollment--azure-ad-affiliated"></a>自動註冊 — Azure AD附屬

在初始設定程式中，將Surface Hub與已啟用Intune自動註冊的 Azure Active Directory (AD) 租使用者建立關聯時，裝置會自動向Intune註冊。 若要深入瞭解，請參閱[Intune Windows裝置的註冊方法](/intune/enrollment/windows-enrollment-methods)。 Surface Hub 要成為 Intune 的「相容裝置」，則必須具有 Azure AD 的附屬連結和 Intune 的自動註冊功能。 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>使用 Intune 管理Surface Hub Windows 10 團隊版設定

Intune 和其他 MDM 提供者中原則設定管理的基礎建置組塊是 XML 型 Open Mobile Alliance-Device Management (OMA-DM) 通訊協定。 Windows會透過許多可用的設定服務提供者之一實作 OMA-DM XML (CSP) 名稱，例如 AccountManagement CSP、DeviceStatus CSP、WiFi-CSP 等等。 如需完整清單，請參閱[Microsoft Surface Hub 中支援的 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)。

Microsoft Intune和其他 MDM 提供者會使用 CSP 來傳遞 UI，讓您能夠在組態設定檔內設定原則設定。 Intune使用 Surface Hub CSP 作為其內建設定檔 —**裝置限制 (Windows 10 團隊版) ** — 可讓您設定基本設定，例如防止Surface Hub在任何人在其鄰近範圍內移動時「喚醒」。 若要在Intune的內建設定檔之外管理中樞設定和功能，您必須使用自訂設定檔，[如下所示](#create-custom-configuration-profile)。 

總而言之，在Intune內設定和管理原則設定的選項包括下列各項： 
 
- **建立裝置限制設定檔。** 使用Intune的內建設定檔，並直接在Intune UI 中設定設定。 請參閱 [建立裝置限制設定檔](#create-device-restriction-profile)。
- **建立裝置組態設定檔。**  選取著重于特定功能或技術的範本，例如 Microsoft Defender 或安全性憑證。 請參閱 [建立裝置組態設定檔](#create-device-configuration-profile)。
- **建立自訂群組態設定檔。**  使用 OMA 統一資源識別項 (OMA URI) ，從 Microsoft Surface Hub[中支援的任何 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)擴充您的管理範圍。 請參閱 [建立自訂群組態設定檔](#create-custom-configuration-profile)。

> [!NOTE]
> 設定檔應指派給包含已註冊Surface Hub裝置的裝置群組。

## <a name="create-device-restriction-profile"></a>建立裝置限制設定檔

1. 登入[**Microsoft 端點管理員系統管理中心**](https://endpoint.microsoft.com/)，選取 [**裝置**  >  ][**設定設定檔**  >  **+** **] [建立設定檔]**。
2. 在 [**平臺]** 底下，選**取 [Windows 10及更新版本]** >
3. 在 [*][配置檔案類型] 底下 **，** 選取 **[範本**]，然後選取 [**裝置限制 (Windows 10 團隊版) **
4. 選 **取 [建立**]，新增名稱，然後選取 [ **下一步]。**
6. 您現在可以流覽及選擇下列類別Surface Hub的預設裝置限制設定：應用程式和體驗、Azure 操作見解、維護、會話和無線投影。 下圖所示的範例會指定 4 小時的維護期間，以及 15 分鐘的螢幕、睡眠和會話繼續逾時。

     ![使用Intune裝置限制設定檔來設定Surface Hub設定。](images/sh-device-restrictions.png)

如需建立和管理設定檔的詳細資訊，請參閱[在Microsoft Intune中使用原則來限制裝置功能](/mem/intune/configuration/device-restrictions-configure#create-the-profile)。
 
如需如何管理Surface Hub功能和設定的詳細資訊，請[參閱使用 Intune 在Surface Hub上允許或限制功能的Windows 10 團隊版設定Intune](/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>建立裝置組態設定檔

1. 登入[**Microsoft 端點管理員系統管理中心**](https://endpoint.microsoft.com/)，選取 [**裝置**  >  ][**設定設定檔+**  >  **建立設定檔]**。
2. 在 [**平臺]** 底下，選**取 [Windows 10及更新版本]** >
3. 在 **[配置檔案類型**] 底下，選取 **[範本**]，然後從下列支援的範本中選擇Surface Hub：

    - 裝置限制 (Windows 10 團隊版) ，如[上一節](#create-device-restriction-profile)所述。
    - 適用於端點的 Microsoft Defender (Windows 10桌面) 
    - PKCS 憑證
    - PKCS 匯入的憑證
    - SCEP 憑證
    - 受信任的憑證

## <a name="create-custom-configuration-profile"></a>建立自訂群組態設定檔

您可以使用 OMA URI 從[Microsoft Surface Hub 中支援的任何 CSP](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) [建立自訂設定檔](/mem/intune/configuration/custom-settings-configure)，以擴充管理範圍。 CSP 中的每個設定都有對應的 OMA-URI，您可以在 Intune 中使用自訂群組態設定檔進行設定。 如需Surface Hub所支援 CSP 的詳細資訊，您可以參考下列資源： 

- [設定服務提供者參考](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Microsoft Surface Hub 支援的 CSPs 原則](/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> 目前無法使用[來自 SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)的設定來管理裝置帳戶Intune，而且需要使用協力廠商 MDM 提供者。

若要實作 CSP 型原則設定，請先產生 OMA URI，然後將它新增至 Intune 中的自訂群組態設定檔。

### <a name="generate-oma-uri-for-target-setting"></a>產生目標設定的 OMA URI
 
若要產生任何設定的 OMA URI：

1. 在 [CSP 檔](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)中，識別 CSP 的根節點。 一般而言，這看起來像 **./Vendor/MSFT/NameOfCSP**。 
    - **例子：**[SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)的根節點是 **./Vendor/MSFT/SurfaceHub**。
2. 找出您要使用之設定的節點路徑。 
    - **例子：** 啟用無線投影之設定的節點路徑是 **InBoxApps/WirelessProjection/Enabled**。
3. 將節點路徑附加到根節點，以產生 OMA URI。 
    - **例子：** 啟用無線投影之設定的 OMA URI 是 **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled。**
4. 資料類型也會在 CSP 文件中說明。 最常見的資料類型包括︰
    - char (字串)
    - int (整數)
    - bool (布林值)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>將 OMA URI 新增至自訂群組態設定檔

1. 在 [端點管理員] 中，選取 [**裝置**  >  ][**設定設定檔**  >  **][建立設定檔]**。
2. 在 [平臺] 底下 **，選取 [Windows 10及更新版本]。** 在 [設定檔] 底下，選取 [ **自訂**]，然後選取 [ **建立]。**
3. 新增名稱和選擇性描述，然後選取 [ **下一步]。**
4. 在 [**組態設定**  >  **][OMA-URI] 設定**中，選取 [**新增]**。

  
## <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams和商務用 Skype設定

本節將重點說明您可以透過 Intune 或其他 MDM 提供者管理的Teams和商務用 Skype設定。 這包括：

- [QoS (服務品質) ](#quality-of-service-settings)
- [管理Teams特定功能](#manage-teams-specific-features)

### <a name="quality-of-service-settings"></a>服務品質設定

若要確保Surface Hub上的最佳視訊和音訊品質，請將下列 QoS 設定新增至裝置。 

| 名稱                 | 說明           | OMA-URI                                                                 | 類型    | 值                          |
| -------------------- | --------------------- | ----------------------------------------------------------------------- | ------- | ------------------------------ |
| 音效連接埠          | 音訊連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/SourcePortMatchCondition    | 字串  | 50000-50019                    |
| 音效 DSCP           | 音訊連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/DSCPAction                  | 整數 | 46                             |
| 多個影片連接埠          | 影片連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/SourcePortMatchCondition    | 字串  | 50020-50039                    |
| 影片 DSCP           | 影片連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/DSCPAction                  | 整數 | 34                             |
| 共用埠        | 共用埠範圍    | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/SourcePortMatchCondition  | 字串  | 50040-50059                    |
| 共用 DSCP         | 共用埠標記 | ./Device/Vendor/MSFT/NetworkQoSPolicy/Sharing/DSCPAction                | 整數 | 18                             |

> [!NOTE]
> 下表顯示預設埠範圍。 系統管理員可以變更商務用 Skype 和 Teams 控制台的連接埠範圍。

### <a name="manage-teams-specific-features"></a>管理Teams特定功能

您可以建立自訂群組態設定檔來管理Teams協調會議、鄰近聯結和其他功能。 若要深入瞭解，請[參閱管理Surface Hub上的Microsoft Teams組態](/microsoftteams/rooms/surface-hub-manage-config)。

### <a name="changing-default-app-for-meetings--calls"></a>變更會議&通話的預設應用程式

Surface Hub上會議&呼叫的預設應用程式會因您安裝 Windows 10 團隊版 2020 Update (也稱為 Windows 10 20H2 Team edition) 的方式而有所不同。 如果您將Surface Hub重新映射為 Windows 10 20H2，Microsoft Teams會設定為預設值，商務用 Skype (模式 1) 無法使用。 如果您從舊版作業系統升級您的中樞，商務用 Skype會維持為預設值，除非您已將Teams設定為預設值，否則 (模式 0) 提供Teams功能。 

若要變更預設安裝，請使用[自訂設定檔](/mem/intune/configuration/custom-settings-configure)來設定Teams會議模式，如下所示：  

- 模式 0－ 商務用 Skype 具 Microsoft Teams 功能，適於排定會議期程。
- 模式 1 - 僅Microsoft Teams。

| 名稱 | 說明 | OMA-URI | 類型 | 值 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 應用程式識別碼**|App 名稱|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 應用程式模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整數| 0 或 1|


