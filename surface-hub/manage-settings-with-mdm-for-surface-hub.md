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
ms.date: 03/03/2021
ms.localizationpriority: medium
ms.openlocfilehash: d09a95d25b4f4ae86d64acd7d7f16f004f991ce3
ms.sourcegitcommit: 5c904229a0257297be7f724c264e484d2c4b5168
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387500"
---
# <a name="manage-settings-with-an-mdm-provider-surface-hub"></a>使用 MDM 提供者管理設定 (Surface Hub)

Surface Hub 和其他 Windows10 裝置允許 IT 系統管理員使用行動裝置管理 (MDM) 提供者管理設定與原則。 內建的管理元件會與管理伺服器通訊，因此不需要在裝置上安裝額外的用戶端。 如需詳細資訊，請參閱 [Windows10 行動裝置管理](https://msdn.microsoft.com/library/windows/hardware/dn914769.aspx)。

Surface Hub 已與 Microsoft 的第一方 MDM 提供者進行驗證：
- Microsoft Intune 獨立式
- 使用 Microsoft 端點群組原則管理員的內部部署 MDM

您也可以使用任何可以使用 MDM 通訊協定與 Windows10 通訊的協力廠商 MDM 提供者來管理 Surface Hub。

## <a name="enroll-a-surface-hub-into-mdm"></a><a href="" id="enroll-into-mdm"></a>將 Surface Hub 註冊到 MDM
您可以使用大量、手動或自動註冊來註冊 Surface Hub。

### <a name="bulk-enrollment"></a>大量註冊
**設定大量註冊**
- Surface Hub 支援使用[佈建 CSP](https://msdn.microsoft.com/library/windows/hardware/mt203665.aspx) 來大量註冊到 MDM。 如需詳細資訊，請參閱 [Windows10 大量註冊](https://msdn.microsoft.com/library/windows/hardware/mt613115.aspx)。<br>
--或--
- 如果您有內部部署 Microsoft Endpoint Configuration Manager 基礎結構，請參閱如何在 Microsoft 端點群組原則管理員中大量註冊使用 [內部部署行動裝置管理的裝置](https://docs.microsoft.com/configmgr/mdm/deploy-use/bulk-enroll-devices-on-premises-mdm)。

### <a name="manual-enrollment"></a>手動註冊
**設定手動註冊**
1. 在 Surface Hub 上，開啟 **\[設定\]**。
2. 出現提示時，請輸入裝置系統管理員認證。
3. 選取 **\[此裝置\]**，然後瀏覽到 **\[裝置管理\]**。
4. 在 **\[裝置管理\]** 下，選取 **\[+ 裝置管理\]**。
5. 依照對話方塊中的指示來連線到您的 MDM 提供者。

### <a name="automatic-enrollment-via-azure-active-directory-join"></a>透過 Azure Active Directory 加入自動註冊

Surface Hub 現在支援將裝置加入 Azure Active Directory 以自動註冊 Intune 的能力。 

第一個步驟是設定自動 MDM 註冊。 請參閱 [啟用 Windows 10 自動註冊](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)。

然後在首次執行期間設定裝置時，加入宣告 Azure Active Directory 的選項，請參閱設定此裝置 [頁面的系統管理員](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub#set-up-admins-for-this-device-page)

## <a name="manage-surface-hub-settings-with-mdm"></a>使用 MDM 管理 Surface Hub 設定

您可以使用 MDM 管理某些 [Surface Hub CSP 設定](#supported-surface-hub-csp-settings)，以及某些 [Windows10 設定](#supported-windows-10-settings)。 根據您使用的 MDM 提供者，您可以使用內建使用者介面設定這些設定，或者部署自訂 SyncML。 Microsoft Intune 和 Microsoft Endpoint Configuration Manager 提供內建體驗，可協助建立 Surface Hub 的策略範本。 請參閱您的 MDM 提供者文件，以了解如何建立及部署 SyncML。

### <a name="supported-surface-hub-csp-settings"></a>支援的 Surface Hub CSP 設定

您可以使用 MDM，設定下列表格中的 Surface Hub 設定。 表格可識別 Microsoft Intune、Microsoft 端點組設定管理員或 SyncML 是否支援此設定。

如需詳細資訊，請參閱 [SurfaceHub 設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/mt608323)。 


|                                     設定                                      |                                                    SurfaceHub CSP 中的節點                                                    |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|----------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                                維護時間                                 |                        MaintenanceHoursSimple/Hours/StartTime <br> MaintenanceHoursSimple/Hours/Duration                         |                       是                        |                       是                       |             是             |
|              自動使用動作感應器開啟螢幕               |                                                 InBoxApps/Welcome/AutoWakeScreen                                                 |                       是                        |                       是                       |             是             |
|                      需要 PIN 才能進行無線投影                       |                                             InBoxApps/WirelessProjection/PINRequired                                             |                       是                        |                       是                       |             是             |
|                            啟用無線投影                            |                                               InBoxApps/WirelessProjection/Enabled                                               |                       是                        | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                 針對無線投影使用的 Miracast 通道                  |                                               InBoxApps/WirelessProjection/Channel                                               |                       是                        | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|              連線到您的 Operations Management Suite 工作區               |                                         MOMAgent/WorkspaceID <br> MOMAgent/WorkspaceKey                                          |                       是                        | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                         歡迎畫面背景影像                          |                                             InBoxApps/Welcome/CurrentBackgroundPath                                              |                       是                        | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               歡迎畫面上顯示的會議資訊                |                                               InBoxApps/Welcome/MeetingInfoOption                                                |                       是                        | 是。<br> [使用自訂設定]。 (#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager |             是             |
|                      無線投影的易記名稱                       |                                                     Properties/FriendlyName                                                      | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                   裝置帳戶                                                 | DeviceAccount/*`<name_of_policy>`* <br> 請參閱 [SurfaceHub CSP](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx)。 |                        否                        |                       否                        |             是             |
|                               指定 Skype 網域                               |                                              InBoxApps/SkypeForBusiness/DomainName                                               |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               投影初始化時自動啟動線應用程式               |                                                   InBoxApps/Connect/AutoLaunch                                                   |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                                設定預設音量                                |                                                     Properties/DefaultVolume                                                     |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                                設定螢幕逾時                                |                                                     Properties/ScreenTimeout                                                     |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                               設定工作階段逾時                                |                                                    Properties/SessionTimeout                                                     |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                                設定睡眠逾時                                 |                                                     Properties/SleepTimeout                                                      |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                   允許螢幕閒置之後繼續工作階段                   |                                                  Properties/AllowSessionResume                                                   |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|             允許裝置帳戶用於 Proxy 驗證             |                                                  Properties/AllowAutoProxyAuth                                                   |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
| 停用從已排程會議自動填入邀請的登入對話方塊 |                                               Properties/DisableSignInSuggestions                                                |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|              停用 [開始] 功能表中的「我的會議和檔案」功能               |                                              Properties/DoNotShowMyMeetingsAndFiles                                              |                    是 </br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                     設定 LanProfile 用於 802.1x 有線驗證                     |                                                         Dot3/LanProfile                                                          | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                    設定 EapUserData 用於 802.1x 有線驗證                     |                                                         Dot3/EapUserData                                                         | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

### <a name="supported-windows-10-settings"></a>支援的 Windows10 設定

除了 Surface Hub 特定設定以外，還有許多所有 Windows10 裝置通用的設定。 這些設定定義在[設定服務提供者參考](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference)中。 

下表包含已使用 Surface Hub 驗證之 Windows10 設定的相關資訊。 有包含下列領域之設定的表格：安全性、瀏覽器、Windows 更新、Windows Defender、遠端重新開機、憑證和記錄檔。 每個資料表會識別 Microsoft Intune、Microsoft 端點組設定管理員或 SyncML 是否支援該設定。

#### <a name="security-settings"></a>安全性設定

|      設定       |                                            詳細資料                                             |                                                                          CSP 參考                                                                           |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|--------------------|------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|  允許藍牙   |                      保持啟用，以支援藍牙周邊裝置。                       |                   [Connectivity/AllowBluetooth](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Connectivity_AllowBluetooth)                   |                    是。 <br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
| 藍牙原則 | 用來設定藍牙裝置名稱，以及封鎖廣告、探索和自動配對。 |                     Bluetooth/*`<name of policy>`* <br> 請參閱[原則 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)                      |                    是。 <br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|    允許相機    |                           針對商務用 Skype 保持啟用。                            |                            [Camera/AllowCamera](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Camera_AllowCamera)                            |                    是。 <br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|   允許定位   |                        保持啟用，以支援 [地圖] 等應用程式。                         |                          [System/AllowLocation](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowLocation)                          |                   是。 <br> .                    | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|  允許遙測   |                    保持啟用，以協助 Microsoft 改善 Surface Hub。                    |                         [System/AllowTelemetry](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#System_AllowTelemetry)                         |                    是。 <br>                     | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|  允許 USB 磁碟機  |                     啟用此項目可在 Surface Hub 上支援 USB 磁碟機                     | [System/AllowStorageCard](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/policy-configuration-service-provider#system-allowstoragecard) | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。 

#### <a name="browser-settings"></a>瀏覽器設定

|                          設定                          |                                                                        詳細資料                                                                        |                                                                             CSP 參考                                                                              |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|-----------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|                         首頁                         |                                               用來設定 Microsoft Edge 中的預設首頁。                                               |                                [Browser/Homepages](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_Homepages)                                | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                       允許 Cookie                       |                    Surface Hub 會在工作階段結束時自動刪除 Cookie。 使用此設定來封鎖工作階段內的 Cookie。                     |                             [Browser/AllowCookies](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowCookies)                             | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                   允許開發人員工具                   |                                                   用來防止使用者使用 F12 開發人員工具。                                                   |                      [Browser/AllowDeveloperTools](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDeveloperTools)                      | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                    允許不要追蹤功能                     |                                                          用來啟用「不要追蹤」標頭。                                                          |                          [Browser/AllowDoNotTrack](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowDoNotTrack)                          | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                       允許快顯視窗                       |                                                         用來封鎖快顯瀏覽器視窗。                                                          |                              [Browser/AllowPopups](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowPopups)                              | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                 允許搜尋建議                  |                                                  用來封鎖網址列中的搜尋建議。                                                  |       [Browser/AllowSearchSuggestionsinAddressBar](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSearchSuggestionsinAddressBar)       | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|                     允許 Windows Defender SmartScreen                     |                                                       保持啟用此功能以開啟 Windows Defender SmartScreen。                                                       |                         [Browser/AllowSmartScreen](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_AllowSmartScreen)                         | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
| 避免忽略網站的 Windows Defender SmartScreen 警告 |     為增加安全性，請使用來避免使用者忽略 Windows Defender SmartScreen 警告，並封鎖他們存取潛在惡意網站。     |         [Browser/PreventSmartScreenPromptOverride](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverride)         | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|  防止忽略檔案的 Windows Defender SmartScreen 警告   | 為了增加安全性，請使用防止使用者忽略 Windows Defender SmartScreen 警告，並禁止他們從 Microsoft Edge 下載未驗證的檔案。 | [Browser/PreventSmartScreenPromptOverrideForFiles](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Browser_PreventSmartScreenPromptOverrideForFiles) | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

#### <a name="windows-update-settings"></a>Windows Update 設定

|                      設定                      |                                                                                                           詳細資料                                                                                                            |                                                                    CSP 參考                                                                    |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|---------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| 使用最新分支或最新商務分支 |                                                       用來設定 Windows Update for Business – 請參閱 [Windows Update](manage-windows-updates-for-surface-hub.md)。                                                       |            [Update/BranchReadinessLevel](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_BranchReadinessLevel)             | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               延遲功能更新               |                                                                                                          請參閱上面的資訊。                                                                                                          | [Update/ DeferFeatureUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferFeatureUpdatesPeriodInDays) | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               延遲品質更新               |                                                                                                          請參閱上面的資訊。                                                                                                          | [Update/DeferQualityUpdatesPeriodInDays](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_DeferQualityUpdatesPeriodInDays)  | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               暫停功能更新               |                                                                                                          請參閱上面的資訊。                                                                                                          |             [Update/PauseFeatureUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseFeatureUpdates)              | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               暫停品質更新               |                                                                                                          請參閱上面的資訊。                                                                                                          |             [Update/PauseQualityUpdates](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_PauseQualityUpdates)              | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|           設定裝置使用 WSUS            |                                            用來將您的 Surface Hub 連線至 WSUS 而非 Windows Update – 請參閱 [Windows Update](manage-windows-updates-for-surface-hub.md)。                                             |                [Update/UpdateServiceUrl](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx#Update_UpdateServiceUrl)                 | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|               傳遞最佳化               | 使用點對點內容共用來降低更新期間的頻寬問題。 如需詳細資訊，請參閱[為 Windows10 設定傳遞最佳化](https://technet.microsoft.com/itpro/windows/manage/waas-delivery-optimization)。 |         DeliveryOptimization/*`<name of policy>`* <br> 請參閱[原則 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx)          | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

#### <a name="windows-defender-settings"></a>Windows Defender 設定

|      設定      |                                              詳細資料                                               |                                                     CSP 參考                                                      |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|-------------------|----------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| Defender 原則 |            用來設定各種 Defender 設定，包括排定的掃描時間。            | Defender/*`<name of policy>`* <br> 請參閱[原則 CSP](https://msdn.microsoft.com/library/windows/hardware/dn904962.aspx) | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
|  Defender 狀態  | 用於啟動 Defender 掃描、強制安全性智慧更新、查詢偵測到的任何威脅。 |                   [Defender CSP](https://msdn.microsoft.com/library/windows/hardware/mt187856.aspx)                    |                       是                        |                       是                       |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

#### <a name="remote-reboot"></a>遠端重新開機

|                       設定                        |                                                          詳細資料                                                          |                                                             CSP 參考                                                             |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
|            立即將裝置重新開機             | 與 Azure 監視器一起使用以將支援成本降到最低 – 請參閱監控[您的 Microsoft Surface Hub。](monitor-surface-hub.md) |        ./Vendor/MSFT/Reboot/RebootNow <br> 請參閱[重新開機 CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)        |                       是                        |                       否                        |             是             |
|    在排定的日期和時間將裝置重新開機    |                                                        請參閱上面的資訊。                                                         |     ./Vendor/MSFT/Reboot/Schedule/Single <br> 請參閱[重新開機 CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx)     | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |
| 每日在排定的日期和時間將裝置重新開機 |                                                        請參閱上面的資訊。                                                         | ./Vendor/MSFT/Reboot/Schedule/DailyRecurrent <br> 請參閱[重新開機 CSP](https://msdn.microsoft.com/library/windows/hardware/mt720802.aspx) | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

#### <a name="install-certificates"></a>安裝憑證

|             設定             |                           詳細資料                            |                                           CSP 參考                                            |                                                         支援<br>Intune？                                                          |                                                                  支援<br>Configuration Manager？                                                                  | 支援<br>SyncML\*? |
|---------------------------------|--------------------------------------------------------------|----------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------|
| 安裝受信任的 CA 憑證 | 用來部署受信任的根與中繼 CA 憑證。 | [RootCATrustedCertificates CSP](https://msdn.microsoft.com/library/windows/hardware/dn904970.aspx) | 是。 <br> 請參閱[設定 Intune 憑證設定檔](https://docs.microsoft.com/intune/deploy-use/configure-intune-certificate-profiles)。 | 是。 <br> 瞭解如何 [在 Microsoft Endpoint Configuration Manager 中建立憑證設定檔](https://docs.microsoft.com/configmgr/protect/deploy-use/create-certificate-profiles)。 |             是             |

<!--
| Install client certificates  | Use to deploy Personal Information Exchange (.pfx, .p12) certificates. | [ClientCertificateInstall CSP](https://msdn.microsoft.com/library/windows/hardware/dn920023.aspx) | Yes. <br> See [How to Create and Deploy PFX Certificate Profiles in Intune Standalone](https://blogs.technet.microsoft.com/karanrustagi/2016/03/16/want-to-push-a-certificate-to-device-but-cant-use-ndes-continue-reading/). | Yes. <br> See [How to create PFX certificate profiles in Microsoft Endpoint Configuration Manager](https://docs.microsoft.com/configmgr/protect/deploy-use/create-pfx-certificate-profiles). | Yes |
-->
\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

#### <a name="collect-logs"></a>收集記錄檔

|     設定      |                      詳細資料                       |                                     CSP 參考                                      | 支援<br>Intune？ | 支援<br>Configuration Manager？ | 支援<br>SyncML\*? |
|------------------|----------------------------------------------------|----------------------------------------------------------------------------------------|---------------------------|------------------------------------------|-----------------------------|
| 收集 ETW 記錄檔 | 用來從 Surface Hub 遠端收集 ETW 記錄檔。 | [DiagnosticLog CSP](https://msdn.microsoft.com/library/windows/hardware/mt219118.aspx) |            否             |                    否                    |             是             |

<!--
| Collect security auditing logs | Use to remotely collect security auditing logs from Surface Hub. | SecurityAuditing node in [Reporting CSP](https://msdn.microsoft.com/library/windows/hardware/mt608321.aspx) | No | No | Yes |-->
\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

#### <a name="set-network-quality-of-service-qos-policy"></a>設定網路服務品質 (QoS) 原則

|        設定         |                                                            詳細資料                                                             |                                                    CSP 參考                                                     |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|------------------------|--------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| 設定網路 QoS 原則 | 用於設定 QoS 原則以執行一組網路流量的動作。 這對於設定 Skype 網路封包優先順序很實用。 | [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

#### <a name="set-network-proxy"></a>設定網路 Proxy

|      設定      |                               詳細資料                               |                                                CSP 參考                                                 |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|-------------------|---------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| 設定網路 Proxy | NetworkProxy CSP 用來設定乙太網路和 Wi-Fi 連線的 proxy 伺服器。 | [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp) | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

#### <a name="configure-start-menu"></a>設定 [開始] 功能表

|       設定        |                                                                       詳細資料                                                                        |                                                        CSP 參考                                                         |            支援<br>Intune？             |    支援<br>Configuration Manager？     | 支援<br>SyncML\*? |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------|-------------------------------------------------|-----------------------------|
| 設定 [開始] 功能表 | 用來設定 [開始] 功能表顯示哪些應用程式。 如需詳細資訊，請參閱[設定 Surface Hub 的 [開始] 功能表](surface-hub-start-menu.md) | [原則 CSP：Start/StartLayout](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-start#start-startlayout) | 是 <br> [使用自訂原則。](#example-manage-surface-hub-settings-with-microsoft-intune) | 是。<br> [使用自訂設定。](#example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager) |             是             |

\*SyncML 支援的「設定」也可以在 Windows 設定設計工具佈建套件中設定。

### <a name="generate-oma-uris-for-settings"></a>產生設定的 OMA URI 
您必須使用設定 OMA URI 在 Intune 中建立自訂策略，或在 Microsoft 端點組設定管理員中建立自訂設定。

**產生 CSP 文件中任何設定的 OMA URI**
1. 在 CSP 文件中，識別 CSP 的根節點。 一般而言，這看起來像是 `./Vendor/MSFT/<name of CSP>` <br>
*例如，[SurfaceHub CSP](https://msdn.microsoft.com/library/windows/hardware/mt608323.aspx) 的根節點是 `./Vendor/MSFT/SurfaceHub`。*
2. 找出您要使用之設定的節點路徑。 <br>
*例如，啟用無線投影之設定的節點路徑為 `InBoxApps/WirelessProjection/Enabled`。*
3. 將節點路徑附加到根節點，以產生 OMA URI。 <br>
*例如，啟用無線投影之設定的 OMA URI 是 `./Vendor/MSFT/SurfaceHub/InBoxApps/WirelessProjection/Enabled`。*

資料類型也會在 CSP 文件中說明。 最常見的資料類型包括︰
- char (字串)
- int (整數)
- bool (布林值)


## <a name="example-manage-surface-hub-settings-with-microsoft-intune"></a>範例︰使用 Microsoft Intune 管理 Surface Hub 設定

您可以使用 Microsoft Intune 管理 Surface Hub 設定。 如需了解自訂設定，請依照[如何在 Microsoft Intune 中設定自訂裝置設定](https://docs.microsoft.com/intune/custom-settings-configure)中的指示進行。 針對 **\[平台\]** 選取 **\[Windows 10 和更新版本\]**，並在 **\[設定檔類型\]** 中選取 **\[裝置限制 (Windows 10 團隊版)\]**。



## <a name="example-manage-surface-hub-settings-with-microsoft-endpoint-configuration-manager"></a>範例：使用 Microsoft Endpoint Configuration Manager 管理 Surface Hub 設定
Configuration Manager 支援管理不需要 Configuration Manager 用戶端來管理的新式裝置，包括 Surface Hub。 如果您已經使用 Configuration Manager 來管理貴組織的其他裝置，您可以繼續使用 Configuration Manager 主控台做為管理 Surface Hub 的單一位置。

> [!NOTE]
> 這些指示是以 Configuration Manager 目前的分支為基礎。

**建立 Surface Hub 設定的設定項目**

1. 在 Configuration Manager 主控台的 **\[資產與合規性\]** 工作區上，按一下 **\[概觀\]** > **\[合規性設定\]** > **\[設定項目\]**。
2. 在 **\[首頁\]** 索引標籤上的 **\[建立\]** 群組中，按一下 **\[建立設定項目\]**。
3. 在「建立設定項目精靈」的 **\[一般\] **頁面上，指定設定項目的名稱和選用描述。
4. 在**\[未使用 Configuration Manager 用戶端管理之裝置的設定\]** 底下，選取 **\[Windows 8.1 和 Windows 10]**，然後按一下 **\[下一步\]**。

    ![UI 範例](images/configmgr-create.png)
5. 在 **\[支援的平台\]** 頁面上，展開 **\[Windows10\]** 並選取 **\[所有 Windows10 團隊版和更新版本\]**。 取消選取其他 Windows 平台，然後按一下 **\[下一步\]**。

    ![選取平台](images/configmgr-platform.png)
7. 在 **\[裝置設定\]** 頁面上的 **\[裝置設定群組\]** 下，選取 **\[Windows10 團隊版\]**。


8. 在 **\[Windows10 團隊版\]** 頁面上，設定您需要的設定。

    ![Windows 10 團隊版](images/configmgr-team.png)
9. 您將必須建立自訂設定來管理 \[Windows10 團隊版\] 頁面中未提供的設定。 在 **\[裝置設定\]** 頁面上，選取 **\[設定不在預設設定群組中的其他設定\]** 核取方塊。

    ![其他設定](images/configmgr-additional.png)
10. 在 **\[其他設定\]** 頁面上，按一下 **\[新增\]**。
11. 在 **\[瀏覽設定\]** 對話方塊中，按一下 **\[建立設定\]**。
12. 在 **\[建立設定\]** 對話方塊中的 **\[一般\]** 索引標籤下，指定自訂設定的名稱與選用描述。
13. 在 **\[設定類型\]** 下，選取 **\[OMA URI\]**。
14. 完成表單以建立新的設定，然後按一下 **\[確定\]**。

    ![OMA URI 設定](images/configmgr-oma-uri.png)
15. 在 **\[瀏覽設定\]** 對話方塊上的 **\[可用的設定\]** 底下，選取您建立的新設定，然後按一下 **\[選取\]**。
16. 在 **\[建立規則\]** 對話方塊上，完成表單以指定設定的規則，然後按一下 **\[確定\]**。
17. 針對您想要新增到設定項目的每個自訂設定重複步驟 9 到 15。
18. 一旦您完成後，在 **\[瀏覽設定\]** 對話方塊上，按一下 **\[關閉\]**。
19. 完成精靈。 <br> 您可以在 **\[資產與合規性\]** 工作區的 **\[設定項目\]** 節點中檢視新的設定項目。

有關詳細資訊，請參閱建立 [Windows 8.1 和 Windows 10](https://docs.microsoft.com/configmgr/compliance/deploy-use/create-configuration-items-for-windows-8.1-and-windows-10-devices-managed-without-the-client)裝置在沒有 Microsoft 端點 Configuration Manager 用戶端的情況下管理的組組專案。

## <a name="related-topics"></a>相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)











