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
ms.openlocfilehash: 54105e8d518e6ef9e89788d4298c877dab9db4ef
ms.sourcegitcommit: 7ffb1d2d86a713a3ed4a7faa8ac82cfc49dbd55e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/05/2021
ms.locfileid: "12068459"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>使用 MDM 提供者管理 Surface Hub

Surface Hub可讓 IT 系統管理員使用行動裝置管理來管理 MDM (和) ，例如Microsoft Intune。 Surface Hub內建的管理元件，可與管理伺服器通訊。 不需要在裝置上安裝其他用戶端。

## <a name="enrolling-surface-hub-into-mdm-management"></a>註冊 mdm Surface Hub MDM 管理 

您可以透過手動或Microsoft Intune註冊，將 Surface 註冊到其他 MDM 提供者。

### <a name="manual-enrollment"></a>手動註冊

1. 開啟**設定應用程式**，然後以當地系統管理員的登錄。 選取**Surface Hub**  >  **裝置管理**，然後選取 **+裝置管理**。
2. 系統會提示您使用帳戶進行登錄，以用於 MDM 提供者。 驗證之後，裝置會自動向 MDM 提供者註冊。

> [!TIP]
> 如果您使用的是 Intune 且未偵測到伺服器位址，請輸入**manage.microsoft.com。**
   
> [!NOTE]
> MDM 註冊會使用提供給驗證的帳戶詳細資料。 帳戶必須擁有註冊 Windows 裝置的許可權，以及 Intune 授權 (或協力廠商 MDM 提供者中所配置的對等註冊) 。

### <a name="auto-enrollment--azure-ad-affiliated"></a>自動註冊 - Azure AD 關聯

在初始設定程式期間，Surface Hub啟用 Intune 自動註冊的 Azure Active Directory (AD) 租使用者關聯時，裝置會自動向 Intune 註冊。 若要深入瞭解，請參閱適用于裝置之[intune Windows方法](/intune/enrollment/windows-enrollment-methods)。 Surface Hub 要成為 Intune 的「相容裝置」，則必須具有 Azure AD 的附屬連結和 Intune 的自動註冊功能。 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>使用 intune Surface Hub Windows 10 團隊版管理您的設定

Intune 和其他 MDM 提供者中策略設定管理的基礎組塊是 XML 型 Open Mobile Alliance-Device管理 (OMA-DM) 協定。 Windows 10許多可用的組組服務提供者 (CSP) 名稱 #D0 例如 AccountManagement CSP、DeviceStatus CSP、WiFi-CSP 等) 來實施 OMA-DM XML。 若要獲得完整的清單，請參閱在 Microsoft Surface Hub 中[支援的MICROSOFT SURFACE HUB。](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)

Microsoft Intune MDM 提供者使用 CSP 提供 UI，可讓您在設定設定檔中設定策略設定。 Intune 會使用 Surface Hub CSP 作為內建設定檔 **#A0**裝置限制 (Windows 10 團隊版) #A1，讓您設定基本設定，例如防止 Surface Hub 在鄰近範圍內附近移動時「喚醒」。 若要管理 Intune 內建設定檔以外的中樞設定和功能，您必須使用自訂設定檔， [如下所示](#create-custom-configuration-profile)。 

若要摘要說明，在 Intune 中設定及管理原則設定的選項包括： 
 
- **建立裝置限制設定檔。** 使用 Intune 的內建設定檔，並直接在 Intune UI 中設定設定。 請參閱 [建立裝置限制設定檔](#create-device-restriction-profile)。
- **建立裝置組組設定檔。**  選取專注于特定功能或技術的範本，例如 Microsoft Defender 或安全性憑證。 請參閱 [建立裝置組組設定檔](#create-device-configuration-profile)。
- **建立自訂群組組設定檔。**  使用 OMA 統一資源識別項 (OMA URI) 擴展管理範圍[，Microsoft Surface Hub。](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) 請參閱 [建立自訂群組組設定檔](#create-custom-configuration-profile)。

> [!NOTE]
> 設定檔應指派給包含已註冊的裝置Surface Hub群組。

## <a name="create-device-restriction-profile"></a>建立裝置限制設定檔

1. 請Microsoft 端點管理員[**系統管理中心**](https://endpoint.microsoft.com/)，選取**裝置**  >  **組組設定檔**  >  **+** **建立設定檔**。
2. 在**平臺**下，Windows 10**及稍後** >
3. 在 ***配置檔案類型**下，** 選取**範本**，然後選取裝置**限制** (Windows 10 團隊版) 
4. 選取 **建立**，新增名稱，然後選取下 **一步。**
6. 現在，您可以流覽及選擇下列類別Surface Hub應用程式與體驗、Azure 操作深入資訊、維護、會話和無線投影的裝置限制設定。 下圖所示的範例指定 4 小時的維護視窗，以及螢幕、睡眠和會話繼續的 15 分鐘超時。

     ![使用 intune Surface Hub限制設定檔設定您的設定。](images/sh-device-restrictions.png)

有關建立及管理設定檔詳細資訊，請參閱在 Microsoft Intune 中限制裝置[Microsoft Intune。](/mem/intune/configuration/device-restrictions-configure#create-the-profile)
 
若要進一Surface Hub功能和設定，請參閱Surface Hub Windows 10 團隊版[裝置限制Microsoft Intune](/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>建立裝置組組設定檔

1. 請Microsoft 端點管理員[**系統管理中心**](https://endpoint.microsoft.com/)，選取**裝置**  >  **組組設定檔**  >  **+ 建立設定檔**。
2. 在**平臺**下，Windows 10**及稍後** >
3. 在**配置檔案類型**下，**選取範本**，然後選擇下列支援範本Surface Hub：

    - 裝置限制 (Windows 10 團隊版) ，如上一節[所述](#create-device-restriction-profile)。
    - Microsoft Defender for Endpoint (Windows 10桌面) 
    - PCKCS 憑證
    - PKCS 已輸入憑證
    - SCEP 憑證
    - 信任的憑證

## <a name="create-custom-configuration-profile"></a>建立自訂群組組設定檔

您可以使用 OMA URI[](/mem/intune/configuration/custom-settings-configure)建立自訂設定檔，從 Microsoft Surface Hub 中支援[的任何 CSP 建立自訂設定檔，以擴充管理Microsoft Surface Hub。](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) CSP 中的每個設定都有對應的 OMA-URI，您可以使用 Intune 中的自訂設定設定檔來設定。 有關您支援之 CSP 的詳細資訊Surface Hub，您可以參照下列資源： 

- [設定服務提供者參考](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Microsoft Surface Hub 支援的 CSPs 原則](/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> 目前無法使用 Intune 使用 [SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp) 的設定來管理裝置帳戶，而且需要使用協力廠商 MDM 提供者。

若要執行以 CSP 為基礎的策略設定，首先請產生 OMA URI，然後將它新增到 Intune 中的自訂設定設定檔。

### <a name="generate-oma-uri-for-target-setting"></a>產生目標設定 OMA URI
 
若要產生任何設定的 OMA URI：

1. 在 [CSP 檔中](/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)，識別 CSP 的根節點。 一般而言，這看起來像 **./Vendor/MSFT/NameOfCSP**。 
    - **範例：** SurfaceHub CSP 的 [根節點](/windows/client-management/mdm/surfacehub-csp) 為 **./Vendor/MSFT/SurfaceHub**。
2. 找出您要使用之設定的節點路徑。 
    - **範例：** 啟用無線投影的設定節點路徑為 **InBoxApps/WirelessProjection/Enabled**。
3. 將節點路徑附加到根節點，以產生 OMA URI。 
    - **範例：** 啟用無線投影的 OMA URI 為 **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled。**
4. 資料類型也會在 CSP 文件中說明。 最常見的資料類型包括︰
    - char (字串)
    - int (整數)
    - bool (布林值)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>新增 OMA URI 至自訂群組組設定檔

1. 在 端點管理員中，選取**裝置**  >  **組組設定檔**  >  **建立設定檔**。
2. 在平臺下選取**Windows 10及稍後。** 在設定檔下， **選取自訂**，然後選取建立 **。**
3. 新增名稱和選擇性描述，然後選取下 **一步。**
4. 在**設定設定**  >  **OMA-URI 設定**下，選取**** 新增 。

  
## <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams和商務用 Skype設定

本節會Teams商務用 Skype透過 Intune 或其他 MDM 提供者管理的設定和設定。 這包括：

- [QoS (服務品質) ](#quality-of-service-settings)
- [管理Teams特定功能](#manage-teams-specific-features)

### <a name="quality-of-service-settings"></a>服務品質設定

若要確保裝置上的最佳視Surface Hub品質，請新增下列 QoS 設定至裝置。 

| 名稱                 | 說明           | OMA-URI                                                                 | 類型    | 值                          |
| -------------------- | --------------------- | ----------------------------------------------------------------------- | ------- | ------------------------------ |
| 音效連接埠          | 音訊連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/SourcePortchCondition    | 字串  | 50000-50019                    |
| 音效 DSCP           | 音訊連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Audio/DSCPAction                  | 整數 | 46                             |
| 多個影片連接埠          | 影片連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/SourcePortmatchCondition    | 字串  | 50020-50039                    |
| 影片 DSCP           | 影片連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/Video/DSCPAction                  | 整數 | 34                             |
| 共用埠        | 共用埠範圍    | ./Device/Vendor/MSFT/NetworkQoSPolicy/sharing/SourcePortmatchCondition  | 字串  | 50040-50059                    |
| 共用 DSCP         | 共用埠標記 | ./Device/Vendor/MSFT/NetworkQoSPolicy/sharing/DSCPAction                | 整數 | 18                             |

> [!NOTE]
> 表格顯示預設埠範圍。 系統管理員可以變更商務用 Skype 和 Teams 控制台的連接埠範圍。

### <a name="manage-teams-specific-features"></a>管理Teams特定功能

您可以建立自訂設定檔，以管理Teams會議、鄰近連接及其他功能。 若要深入瞭解，請參閱在 Microsoft Teams[管理 Surface Hub。](/microsoftteams/rooms/surface-hub-manage-config)

### <a name="changing-default-app-for-meetings--calls"></a>變更會議的預設應用程式&通話

& 上的會議Surface Hub應用程式會視您安裝 Windows 10 團隊版 2020 更新 (或 20H2 小組版 Windows 10 20H2 小組) 。 如果您重新將 Surface Hub圖像Windows 10 20H2，Microsoft Teams 會設為預設值，商務用 Skype模式 1 (中) 。 如果您從較舊版本升級中樞，商務用 Skype 會維持為預設值， (模式 0) 提供 Teams 功能，除非您已將 Teams 做為預設值。 

若要變更預設安裝，請使用[自訂](/mem/intune/configuration/custom-settings-configure)設定檔Teams會議模式，如下所示：  

- 模式 0－ 商務用 Skype 具 Microsoft Teams 功能，適於排定會議期程。
- 模式 1 - Microsoft Teams模式。

| 名稱 | 說明 | OMA-URI | 類型 | 值 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 應用程式識別碼**|App 名稱|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 應用程式模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整數| 0 或 1|


