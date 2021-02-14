---
title: 使用 Intune 管理 Surface Hub 2S
description: 瞭解如何使用 Intune 更新及管理 Surface Hub 2S。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/10/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 3b3b5ed47e3a34369c6890aac051436db1f42347
ms.sourcegitcommit: f8f32455b1230742c58ee74004cbaaad037069b6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/14/2021
ms.locfileid: "11328207"
---
# 使用 Intune 管理 Surface Hub 2S

## 使用 Intune 註冊 Surface Hub 2S

Surface Hub 2S 可讓 IT 系統管理員使用行動裝置管理（MDM）提供者管理設定和原則。 Surface Hub 2S 具備內建的管理元件，可與管理伺服器溝通，因此不需要在裝置上安裝其他用戶端。

### 手動註冊

1. 在 **Surface** Hub 2S 上開啟設定應用程式，然後以當地系統管理員的登錄。 點選 **Surface Hub** > ** [裝置管理]**，之後選擇 **+** 新增。
2. 系統會提示您以帳戶登入，以用於 Intune。 驗證完成之後，裝置就會進行 Intune 自動註冊。

   ![使用 Intune 註冊 Surface Hub 2S](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> 用於驗證的帳戶為 Intune 註冊帳戶，且必須獲得 Intune 授權。

### 自動註冊－ Azure Active Directory 附屬連結

在初始設定過程中，在將 Surface Hub 連結至一個已啟用 Intune 自動註冊功能的 Azure AD 租用者帳號時，裝置便會進行 Intune 的自動註冊程序。 如需更多詳細資訊，可參照 [ Windows 裝置適用的 Intune 註冊方法](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)。 Surface Hub 要成為 Intune 的「相容裝置」，則必須具有 Azure AD 的附屬連結和 Intune 的自動註冊功能。 

## 使用 Intune 管理 Windows 10 團隊設定

1. 請進入**Microsoft 端點管理員**，選取**裝置**  >  **組組設定檔**  >  **建立設定檔**。 
2. 在**平臺下**，選取**Windows 10**及更新版本在  >  **Windows 10 (裝置限制) **然後選取**** 建立。 
3. 現在，您可以流覽並選取 Surface Hub 和 Surface Hub 2S 的預先設定裝置限制設定。

 ![設定 Surface Hub 2S 的裝置限制。](images/sh2-set-intune3.png) <br>

這些設定涵蓋下列類別：應用程式與體驗、Azure 操作深入資訊、維護、會話和無線投影。  

## 支援的組 (組) 

除了透過 Intune 主機直接提供之 (，有許多組) 會與登錄機機密鑰或檔案進行連結。 

Microsoft 通常會在每個新版本的 Windows 10 作業系統中提供新的 CSP。 [Windows 10 小組 2020](surface-hub-2020-update.md)更新包含 20 多個適用于 Surface Hub 和 Surface Hub 2S 的新和更新裝置管理政策。 這些 MDM 政策讓 IT 系統管理員改善了 Microsoft Store 應用程式更新、無線投影設定 ，例如 Miracast 對基礎結構的控制、網路設定 ，例如服務品質與 802.1x 有線驗證，以及新的隱私權/GDPR 相關設定。

如需詳細資訊，請參閱下列資源： 

- [設定服務提供者參考](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Microsoft Surface Hub 支援的 CSPs 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)
- [Surface Hub Team 2020 Update 的新增功能](surface-hub-2020-update-whats-new.md)

## 服務品質（QoS）設定

為了確保 Surface Hub 2S 的最佳影片和音訊品質，請將下列 QoS 設定新增到裝置。 

### Microsoft Teams 的 QoS 設定 

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
|**P2P 共用埠**| 共用埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DestinationPortMatchCondition | 字串  | 50040-50059 |
|**P2P 共用 DSCP**| 共用埠標記 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PSharing/DSCPAction | 整數 | 18 |


### 商務用 Skype QoS 設定

| 名稱                 | 說明           | OMA-URI                                                                    | 類型    | 值                          |
| -------------------- | --------------------- | -------------------------------------------------------------------------- | ------- | ------------------------------ |
| 音效連接埠          | 音訊連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition    | 字串  | 50000-50019                    |
| 音效 DSCP           | 音訊連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                  | 整數 | 46                             |
| 音訊媒體來源   | Skype App 名稱        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition   | 字串  | Microsoft.PPISkype.Windows.exe |
| 多個影片連接埠          | 影片連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition    | 字串  | 50020-50039                    |
| 影片 DSCP           | 影片連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                  | 整數 | 34                             |
| 影片媒體來源   | Skype App 名稱        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition   | 字串  | Microsoft.PPISkype.Windows.exe |
| 共用埠        | 共用埠範圍    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/SourcePortMatchCondition  | 字串  | 50040-50059                    |
| 共用 DSCP         | 共用埠標記 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/DSCPAction                | 整數 | 18                             |
| 共用媒體來源 | Skype App 名稱        | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBSharing/AppPathNameMatchCondition | 字串  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> 兩個表格都顯示出預設的連接埠範圍。 系統管理員可以變更商務用 Skype 和 Teams 控制台的連接埠範圍。

## Microsoft Teams 設定

您可以使用 Intune 設定各種 Microsoft Teams 設定。

### 模式

Surface Hub 2S 會在模式 0 中隨 Microsoft Teams 一起安裝完成，可支援 Microsoft Teams 和商務用 Skype。 模式函數如下所述：

- 模式 0－ 商務用 Skype 具 Microsoft Teams 功能，適於排定會議期程。
- 模式 1－ Microsoft Teams 具商務用 Skype 功能,適於排定會議期程。
- 模式 2－ 僅具 Microsoft Teams 功能。

若要調整模式，請新增下列設定至 [自訂裝置設定設定檔](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure)。

| 名稱 | 說明 | OMA-URI | 類型 | 值 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 應用程式識別碼**|App 名稱|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 應用程式模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整數| 0 或 1 或 2|

### 協調會議和鄰近區連接

Teams 協調式會議與鄰近連接功能可透過 [透過](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure) Intune 設定檔部署的 XML 檔案進行配置。
