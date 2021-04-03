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
ms.openlocfilehash: 1afa4d63dde793e61e30d1c4dd54f552b5581a81
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470453"
---
# <a name="manage-surface-hub-with-an-mdm-provider"></a>使用 MDM 提供者管理 Surface Hub

Surface Hub 可讓 IT 系統管理員使用行動裝置管理與 MDM (管理) Microsoft Intune。 Surface Hub 有內建的管理元件，可與管理伺服器通訊。 不需要在裝置上安裝其他用戶端。

## <a name="enrolling-surface-hub-into-mdm-management"></a>將 Surface Hub 註冊到 MDM 管理 

您可以手動或自動註冊，將 Surface 註冊到 Microsoft Intune 或其他 MDM 提供者。

### <a name="manual-enrollment"></a>手動註冊

1. 開啟設定 **應用程式** ，然後以當地系統管理員的登錄。 選取**Surface Hub**  >  **裝置管理**，然後選取 **+裝置管理**。
2. 系統會提示您使用帳戶進行登錄，以用於 MDM 提供者。 驗證之後，裝置會自動向 MDM 提供者註冊。

> [!TIP]
> 如果您使用的是 Intune 且未偵測到伺服器位址，請輸入**manage.microsoft.com。**
   
> [!NOTE]
>  MDM 註冊會使用提供給驗證的帳戶詳細資料。 帳戶必須具有註冊 Windows 裝置的許可權，以及 Intune 授權 (或您協力廠商 MDM 提供者) 中所配置的同等註冊授權。

### <a name="auto-enrollment--azure-ad-affiliated"></a>自動註冊 - Azure AD 關聯

在初始設定程式期間，當將 Surface Hub 與已啟用 Intune 自動註冊的 Azure Active Directory (AD) 租使用者關聯時，裝置會自動向 Intune 註冊。 若要深入瞭解，請參閱 Windows 裝置 [Intune 註冊方法](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)。 Surface Hub 要成為 Intune 的「相容裝置」，則必須具有 Azure AD 的附屬連結和 Intune 的自動註冊功能。 

## <a name="manage-surface-hub-windows-10-team-settings-with-intune"></a>使用 Intune 管理 Surface Hub Windows 10 小組設定

Intune 和其他 MDM 提供者中策略設定管理的基礎組塊是 XML 型 Open Mobile Alliance-Device管理 (OMA-DM) 協定。 Windows 10 透過許多可用的組組服務提供者 (CSP) 名稱 #D0 例如 AccountManagement CSP、DeviceStatus CSP、Wirednetwork-CSP 等) 來實施 OMA-DM XML。 若要完整清單，請參閱 Microsoft Surface Hub 中支援的[CSP。](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)


Microsoft Intune 和其他 MDM 提供者使用 CSP 提供 UI，可讓您在設定設定檔中設定策略設定。 Intune 會使用 Surface Hub CSP 作為其內建設定檔 #A0 裝置限制  ** (Windows 10 小組) #A1， ** 讓您設定基本設定，例如防止 Surface Hub 在鄰近範圍內附近移動時「喚醒」。 若要管理 Intune 內建設定檔以外的中樞設定和功能，您必須使用自訂設定檔[，如下所示。](#create-custom-configuration-profile) 

若要摘要說明，在 Intune 中設定及管理原則設定的選項包括： 
 
- **建立裝置限制設定檔。** 使用 Intune 的內建設定檔，並直接在 Intune UI 中設定設定。 請參閱 [建立裝置限制設定檔](#create-device-restriction-profile)。
- **建立裝置組組設定檔。**  選取專注于特定功能或技術的範本，例如 Microsoft Defender 或安全性憑證。 請參閱 [建立裝置組組設定檔](#create-device-configuration-profile)。
- **建立自訂群組組設定檔。**  從 Microsoft Surface Hub 支援的任何 [CSP](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport) (OMA URI) 擴展您的管理範圍。 請參閱 [建立自訂群組組設定檔](#create-custom-configuration-profile)。


## <a name="create-device-restriction-profile"></a>建立裝置限制設定檔

1. 請登錄[**Microsoft 端點管理員系統管理中心**](https://endpoint.microsoft.com/)，選取**裝置**  >  **組組設定檔**  >  **+** **建立設定檔**。
2. 在 **平臺下**，選取 **Windows 10 及更新版本** >
3. 在 ***個人資料類型**下，** 選取 **範本** ，然後選取 **Windows 10 小組 (裝置) **
4. 選取 **建立**，新增名稱，然後選取下 **一步。**
6. 現在，您可以流覽並選擇 Surface Hub 的裝置限制設定，包括下列類別：應用程式與體驗、Azure 操作深入資訊、維護、會話和無線投影。 下圖所示的範例指定 4 小時的維護視窗，以及螢幕、睡眠和會話繼續的 15 分鐘超時。

     ![使用 Intune 裝置限制設定檔設定 Surface Hub 設定](images/sh-device-restrictions.png)

有關建立及管理設定檔詳細資訊，請參閱在 Microsoft Intune 中限制使用 [策略的裝置功能](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-configure#create-the-profile)。
 
若要瞭解如何管理 Surface Hub 功能和設定，請參閱 Microsoft Intune 中的 [Surface Hub Windows 10 小組裝置限制](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10-teams)
 

## <a name="create-device-configuration-profile"></a>建立裝置組組設定檔

1. 請登錄[**Microsoft 端點管理員系統管理中心**](https://endpoint.microsoft.com/)，選取**裝置**  >  **組組設定檔**  >  **+ 建立設定檔**。
2. 在 **平臺下**，選取 **Windows 10 及更新版本** >
3. 在 **配置檔案類型**下 **，選取範本** ，然後選擇 Surface Hub 上支援的下列範本：

    - Windows 10 (的裝置限制) 如上一節 [所述](#create-device-restriction-profile)。
    - Microsoft Defender for Endpoint (Windows 10 桌上出版) 
    - PCKCS 憑證
    - PKCS 已輸入憑證
    - SCEP 憑證
    - 信任的憑證

## <a name="create-custom-configuration-profile"></a>建立自訂群組組設定檔

您可以使用 Microsoft Surface Hub[](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)支援的任何[CSP，](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)使用 OMA URI 建立自訂設定檔，以擴充管理範圍。 CSP 中的每個設定都有對應的 OMA-URI，您可以使用 Intune 中的自訂設定設定檔來設定。 有關 Surface Hub 支援的 CSP 詳細資料，您可以參照下列資源： 

- [設定服務提供者參考](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)
- [Microsoft Surface Hub 支援的 CSPs 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
> [!NOTE]
> Intune 目前無法使用 [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) 中的設定來管理裝置帳戶，而且需要使用協力廠商 MDM 提供者。

若要執行以 CSP 為基礎的策略設定，首先請產生 OMA URI，然後將它新增到 Intune 中的自訂設定設定檔。

### <a name="generate-oma-uri-for-target-setting"></a>產生目標設定的 OMA URI
 
若要產生任何設定的 OMA URI：

1. 在 [CSP 檔中](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference#surfacehubcspsupport)，識別 CSP 的根節點。 一般而言，這看起來像 **./Vendor/MSFT/ <name of CSP> **。 
    - **範例：** SurfaceHub CSP 的 [根節點](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp) 為 **./Vendor/MSFT/SurfaceHub**。
2. 找出您要使用之設定的節點路徑。 
    - **範例：** 啟用無線投影的設定節點路徑為 **InBoxApps/WirelessProjection/Enabled**。
3. 將節點路徑附加到根節點，以產生 OMA URI。 
    - **範例：** 啟用無線投影的 OMA URI 為 **./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled。**
4. 資料類型也會在 CSP 文件中說明。 最常見的資料類型包括︰
    - char (字串)
    - int (整數)
    - bool (布林值)

### <a name="add-oma-uri-to-custom-configuration-profile"></a>新增 OMA URI 至自訂群組組設定檔

1. 在端點管理員中，**選取裝置**  >  **組組設定檔**  >  **建立設定檔**。
2. 在平臺下 **選取 Windows 10 及更新版本。** 在設定檔下， **選取自訂**，然後選取建立 **。**
3. 新增名稱和選擇性描述，然後選取下 **一步。**
4. 在**設定設定**  >  **OMA-URI**設定**** 下，選取 新增 。

  
## <a name="manage-specific-surface-hub-features"></a>管理特定的 Surface Hub 功能

本節會著重說明您可以透過 Intune 或其他 MDM 提供者管理的功能相關資訊。 這包括：

- [QoS (服務品質) ](#quality-of-service-settings)
- [Microsoft Teams 和商務用 Skype](#microsoft-teams-and-skype-for-business-settings)

### <a name="quality-of-service-settings"></a>服務品質設定

若要確保 Surface Hub 上的最佳視音訊品質，請新增下列 QoS 設定至裝置。 

| 名稱 | 說明 | OMA-URI | 類型 | 值 |
|:------ |:------------- |:--------- |:------ |:------- |
|**音效連接埠**| 音訊連接埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | 字串  | 3478-3479 |
|**音效 DSCP**| 音訊連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | 整數 | 46 |
|**影片連接埠**| 影片連接埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | 字串  | 3480 |
|**影片 DSCP**| 影片連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | 整數 | 34 |
|**共用埠**| 共用埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DestinationPortMatchCondition | 字串  | 3481 |
|**共用 DSCP**| 共用埠標記 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction | 整數 | 18 |
|**P2P 音效連接埠**| 音訊連接埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | 字串  | 50000-50019 |
|**P2P 音效 DSCP**| 音訊連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | 整數 | 46 |
|**P2P 影片連接埠**| 影片連接埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | 字串  | 50020-50039 |
|**P2P 影片 DSCP**| 影片連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | 整數 | 34 |
|**P2P 共用埠**| 共用埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortchCondition | 字串  | 50040-50059 |
|**P2P 共用 DSCP**| 共用埠標記 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | 整數 | 18 |


#### <a name="skype-for-business-qos-settings"></a>商務用 Skype QoS 設定

| 名稱                 | 說明           | OMA-URI                                                                    | 類型    | 值                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| 音效連接埠          | 音訊連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | 字串  | 50000-50019                    |
| 音效 DSCP           | 音訊連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | 整數 | 46                             |
| 音訊媒體來源   | Skype App 名稱        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | 字串  | Microsoft.PPISkype.Windows.exe |
| 多個影片連接埠          | 影片連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | 字串  | 50020-50039                    |
| 影片 DSCP           | 影片連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | 整數 | 34                             |
| 影片媒體來源   | Skype App 名稱        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | 字串  | Microsoft.PPISkype.Windows.exe |
| 共用埠        | 共用埠範圍    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortchCondition  | 字串  | 50040-50059                    |
| 共用 DSCP         | 共用埠標記 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | 整數 | 18                             |
| 共用媒體來源 | Skype App 名稱        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | 字串  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> 兩個表格都顯示出預設的連接埠範圍。 系統管理員可以變更商務用 Skype 和 Teams 控制台的連接埠範圍。

### <a name="microsoft-teams-and-skype-for-business-settings"></a>Microsoft Teams 和商務用 Skype 設定

您可以建立自訂群組組設定檔來管理 Teams 協調會議、鄰近連接及其他功能。 若要深入瞭解，請參閱 [在 Surface Hub 上管理 Microsoft Teams 組配置](https://docs.microsoft.com/microsoftteams/rooms/surface-hub-manage-config)。

#### <a name="changing-default-business-communications-platform"></a>變更預設商務通訊平臺

Surface Hub 上的預設商務通訊平臺會因您安裝 Windows 10 小組 2020 更新 (Windows 10 20H2) 。 如果您將 Surface Hub 重新映射至 Windows 10 20H2，Microsoft Teams 會設定為預設值，而商務用 Skype 功能 (模式 1) 。 如果您從較舊版本升級中樞，商務用 Skype 會維持為預設值，除非您已經將 Teams 做為預設，否則 Teams 功能 (模式 0) 提供。 

若要變更預設安裝，請使用 [自訂設定檔](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) ，方法如下設定 Teams App 模式：  

- 模式 0－ 商務用 Skype 具 Microsoft Teams 功能，適於排定會議期程。
- 模式 1－ Microsoft Teams 具商務用 Skype 功能,適於排定會議期程。
- 模式 2－ 僅具 Microsoft Teams 功能。

| 名稱 | 說明 | OMA-URI | 類型 | 值 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 應用程式識別碼**|App 名稱|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 應用程式模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整數| 0 或 1 或 2|










