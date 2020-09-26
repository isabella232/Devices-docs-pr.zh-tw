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
ms.date: 07/23/2020
ms.localizationpriority: Medium
ms.openlocfilehash: a031fd7fd861e5d45194ec1a8c391621a2bcb71a
ms.sourcegitcommit: 5fa5efefd510ce6f435d7142fb2f2cc08b520da9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/25/2020
ms.locfileid: "11078743"
---
# 使用 Intune 管理 Surface Hub 2S

## 使用 Intune 註冊 Surface Hub 2S

Surface Hub 2S 可讓 IT 系統管理員使用行動裝置管理（MDM）提供者管理設定和原則。 Surface Hub 2S 具備內建的管理元件，可與管理伺服器溝通，因此不需要在裝置上安裝其他用戶端。

### 手動註冊

1. 開啟 Surface Hub 2 的 [ **設定** ] 應用程式，並以本機管理員身分登入。 點選 **Surface Hub** > ** [裝置管理]**，之後選擇 **+** 新增。
2. 系統會提示您使用要用於 Intune 的帳戶登入。 驗證完成之後，裝置就會進行 Intune 自動註冊。

   ![使用 Intune 註冊 Surface Hub 2S](images/sh2-set-intune1.png)<br>
   
> [!NOTE]
> 用於驗證的帳戶將是 Intune 登記帳戶，且必須以 Intune 授權。

### 自動註冊－ Azure Active Directory 附屬連結

在初始設定過程中，在將 Surface Hub 連結至一個已啟用 Intune 自動註冊功能的 Azure AD 租用者帳號時，裝置便會進行 Intune 的自動註冊程序。 如需更多詳細資訊，可參照 [ Windows 裝置適用的 Intune 註冊方法](https://docs.microsoft.com/intune/enrollment/windows-enrollment-methods)。 Surface Hub 要成為 Intune 的「相容裝置」，則必須具有 Azure AD 的附屬連結和 Intune 的自動註冊功能。 

## 使用 Intune 管理 Windows 10 團隊設定

1. 登入**Microsoft 端點管理員**，選取 [**裝置**設定配置  >  **檔**]  >  **建立設定檔**。 
2. 在 [**平臺**] 底下，選取 windows 10 小組 (的**windows 10 及更新**的  >  **裝置限制) **然後選取 [**建立**]。 
3. 您現在可以流覽並選取 [Surface Hub] 和 [Surface Hub 2] 的 [預置裝置限制] 設定。

 ![設定 Surface Hub 2S 的裝置限制。](images/sh2-set-intune3.png) <br>

這些設定涵蓋下列類別： App 與體驗、Azure operational insights、維護、會話及無線投影。  

##  (Csp) 支援的 Configuration services 提供者

除了可透過 Intune 主控台直接使用的原則之外，還有許多配置服務提供者 (與登錄機碼或檔案對應的 Csp) 。 

Microsoft 通常會針對每個新版本的 Windows 10 作業系統，提供新的 Csp。 透過 Windows 測試人員計畫在預覽中提供的 [Windows 10 Team 2020 更新](surface-hub-install-2020preview.md)，包含超過20個適用于 surface Hub 和 surface hub 2 的新功能和更新裝置管理原則。 這些 MDM 原則賦予 IT 管理員對來自 Microsoft Store 的 app 更新的控制權，以及無線投影設定（例如服務品質與 802.1 x 有線驗證），以及新的隱私權/GDPR 相關設定等。

如需詳細資訊，請參閱下列資源： 

- [設定服務提供者參考](https://docs.microsoft.com/windows/client-management/mdm/configuration-service-provider-reference) 
- [SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)
- [Microsoft Surface Hub 支援的 CSPs 原則](https://docs.microsoft.com/windows/client-management/mdm/policy-csps-supported-by-surface-hub)

## 服務品質（QoS）設定

為了確保 Surface Hub 2S 的最佳影片和音訊品質，請將下列 QoS 設定新增到裝置。 

### Microsoft Teams 的 QoS 設定 

| 名稱 | 說明 | OMA-URI | 類型 | 值 |
|:------ |:------------- |:--------- |:------ |:------- |
|**音效連接埠**| 音訊連接埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DestinationPortMatchCondition | 字串  | 3478-3479 |
|**音效 DSCP**| 音訊連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction | 整數 | 46 |
|**影片連接埠**| 影片連接埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DestinationPortMatchCondition | 字串  | 3480 |
|**影片 DSCP**| 影片連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction | 整數 | 34 |
|**P2P 音效連接埠**| 音訊連接埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DestinationPortMatchCondition | 字串  | 50000-50019 |
|**P2P 音效 DSCP**| 音訊連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PAudio/DSCPAction | 整數 | 46 |
|**P2P 影片連接埠**| 影片連接埠範圍 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DestinationPortMatchCondition | 字串  | 50020-50039 |
|**P2P 影片 DSCP**| 影片連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsP2PVideo/DSCPAction | 整數 | 34 |


### 商務用 Skype QoS 設定

| 名稱               | 說明         | OMA-URI                                                                  | 類型    | 值                          |
| ------------------ | ------------------- | ------------------------------------------------------------------------ | ------- | ------------------------------ |
| 音效連接埠        | 音訊連接埠範圍    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/SourcePortMatchCondition  | 字串  | 50000-50019                    |
| 音效 DSCP         | 音訊連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/DSCPAction                | 整數 | 46                             |
| 音訊媒體來源 | Skype App 名稱      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBAudio/AppPathNameMatchCondition | 字串  | Microsoft.PPISkype.Windows.exe |
| 多個影片連接埠        | 影片連接埠範圍    | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/SourcePortMatchCondition  | 字串  | 50020-50039                    |
| 影片 DSCP         | 影片連接埠標示 | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/DSCPAction                | 整數 | 34                             |
| 影片媒體來源 | Skype App 名稱      | ./Device/Vendor/MSFT/NetworkQoSPolicy/SfBVideo/AppPathNameMatchCondition | 字串  | Microsoft.PPISkype.Windows.exe |

> [!NOTE]
> 兩個表格都顯示出預設的連接埠範圍。 系統管理員可以變更商務用 Skype 和 Teams 控制台的連接埠範圍。

## Microsoft Teams 模式設定

您可以使用 Intune 設定 Microsoft Teams 應用程式的模式。 Surface Hub 2S 會在模式 0 中隨 Microsoft Teams 一起安裝完成，可支援 Microsoft Teams 和商務用 Skype。 您可以調整模式，如下所示。

### 模式：

- 模式 0－ 商務用 Skype 具 Microsoft Teams 功能，適於排定會議期程。
- 模式 1－ Microsoft Teams 具商務用 Skype 功能,適於排定會議期程。
- 模式 2－ 僅具 Microsoft Teams 功能。

若要設定模式，請在自訂 [裝置設定設定檔] 中新增下列設定。

| 名稱 | 說明 | OMA-URI | 類型 | 值 |
|:--- |:--- |:--- |:--- |:--- |
|**Teams 應用程式識別碼**|App 名稱|./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId|字串| Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams|
|**Teams 應用程式模式**|Teams 模式|./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode|整數| 0 或 1 或 2|
