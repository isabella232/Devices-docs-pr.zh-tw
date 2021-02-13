---
title: 在 Surface Hub 上安裝及設定新的 Microsoft Edge
description: 在 Surface Hub 上安裝和設定新的 Microsoft Edge。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/10/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 2bc11fb18137ce21cba27368e0c12bbb9e73a4c2
ms.sourcegitcommit: 7e028c1e66fb393dc0e8917dac257ce95e5e9ce7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/12/2021
ms.locfileid: "11327307"
---
# 在 Surface Hub 上安裝及設定新的 Microsoft Edge

Windows 10 小組 2020 更新支援以 Chromium (版本 85 及更新版本) 為基礎的新 Microsoft Edge，做為 Surface Hub 2S 和 Surface Hub (v1) 的建議瀏覽器。 本文說明如何使用三種方法之一安裝瀏覽器：提供套件、Microsoft Intune 或 MDM 提供者的協力廠商行動 (管理) 。

> [!IMPORTANT]
> 根據預設，Surface Hub 裝置會預先安裝 Microsoft Edge 舊版 (版本 44) 。 安裝 [2020 Update](surface-hub-2020-update.md)之後，建議您切換到新的 Microsoft Edge 瀏覽器;Microsoft [Edge](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0) 舊版的支援將于 2021 年 3 月 9 日結束。

## 使用部署套件安裝 Microsoft Edge

1. 從電腦下載 Microsoft [Edge 資源](https://aka.ms/HubEdge) (MicrosoftEdgeInstaller.ppkg) 到 USB 磁碟機的根資料夾。
2. 將 USB 磁碟機插入 Surface Hub。
3. 在 Surface Hub 中，開啟 **設定** ，並輸入系統管理認證時出現提示。
4. 瀏覽至 **\[Surface Hub\]** > **\[裝置管理\]**。 在 **\[佈建套件\]** 底下，選取 **\[新增或移除佈建套件\]**。
5. 選取 **[新增套件]**。
6. 選擇 Microsoft Edge 的部署套件， **然後選取新增**。
7. 您會看到部署套件套用之變更的摘要。 選取 **\[是，請將它新增\]**。
8. 等待 Microsoft Edge 安裝完成。 安裝之後，流覽至 Surface Hub 的開始功能表以存取新的 Microsoft Edge。              

> [!NOTE]
> 如果有較新版本的 Microsoft Edge 可用，系統將會自動更新。
 
## 使用 Intune 安裝 Microsoft Edge
 
> [!NOTE]
> Surface Hub 裝置必須使用 Intune 註冊和管理。 詳細資訊請參閱使用 Microsoft Intune 管理[Surface Hub 2S。](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)
 

1. [下載 Microsoft Edge 安裝程式](https://www.microsoft.com/edge/business/download)。
    - 使用目前版本從[穩定通道 (](https://docs.microsoft.com/deployedge/microsoft-edge-channels)**版本 85) **
    - 選擇 **Windows 64 位**
2. [將 Microsoft Edge 安裝程式新增為商務用應用程式至 Microsoft Intune。](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - 如果您選擇使用 Microsoft Edge Update 來處理 Microsoft Edge 的自動更新，請務必設定忽略**應用程式版本設定****應用程式資訊**窗格。 當您將這項設定切換為 **Yes**時，Microsoft Intune 不會強制執行 Surface Hub 裝置上安裝的應用程式版本。

## 使用協力廠商 MDM 提供者安裝 Microsoft Edge

1. [從 Microsoft 下載 Microsoft Edge 安裝程式](https://www.microsoft.com/edge/business/download)。
    - 使用目前版本從[穩定通道 (](https://docs.microsoft.com/deployedge/microsoft-edge-channels)**版本 85) **
    - 選擇 **Windows 64 位**
2. 將 Microsoft Edge 安裝程式階段化于託管位置，例如本地檔案共用 (\\server\share\MicrosoftEdgeEnterpriseX64.msi) 。 Surface Hub 裝置必須擁有存取託管位置的許可權。
3. 透過 [MDM 提供者使用 EnterpriseDesktopAppManagement ](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) (CSP) 安裝 Microsoft Edge。

## 設定 Microsoft Edge

### Surface Hub 的預設 Microsoft Edge 政策

Microsoft Edge 已預先設定下列策略設定，為 Surface Hub 提供優化的體驗。
 
> [!TIP]
> 建議您保留這些策略設定的預設值。
 

| 政策設定                                                                                                   | 建議體驗                                                                                                                                                                                                                                               | 預設值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 請勿從舊版 Microsoft Edge 自動導入資料類型和設定。 這可避免使用 Surface Hub 的共用設定變更已登錄使用者的設定檔。                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允許 Microsoft Edge 程式即使在最後一個瀏覽器視窗關閉後，也持續在背景執行，讓會話期間能更快速地存取 Web App。                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允許使用者在 Microsoft Edge 中建立新設定檔。 這簡化了流覽和已簽署體驗。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 僅讓一個使用者可以登錄 Microsoft Edge。 這簡化了流覽和已登錄體驗                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 讓使用者在 Microsoft Edge Sign-On (SSO) 單一登入。 當使用者已簽署 Surface Hub 時，他們的認證可以流程至支援的網站，而不需要他們重新驗證。  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 防止非系統管理員使用者在 Microsoft Edge 中安裝新的擴充功能。 若要設定預設要安裝的擴充功能清單，請使用[ExtensionInstallForcelist。](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist) | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隱藏使用者第一次執行 Microsoft Edge 時通常會顯示的首次執行體驗和啟動畫面。 由於 Surface Hub 是共用裝置，因此可簡化使用者體驗。                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 停用 InPrivate 模式。 由於結束會話已清除流覽資料，因此這可簡化流覽和已簽署體驗。                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 顯示新索引鍵頁面上的 Office 365 進紙體驗。 當使用者已簽署 Surface Hub 時，這可讓您快速存取 Office 365 上的檔案和內容。                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 當使用者已簽署 Surface Hub 時，將會使用其組織帳戶建立非可移除的設定檔。 這簡化了單一Sign-On (SSO) 體驗。                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | 停用 Microsoft Edge 中的列印功能。 Surface Hub 不支援列印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 讓 Microsoft Edge 主動驗證使用 Microsoft 服務的已登錄使用者。 這簡化了單一Sign-On (SSO) 體驗。                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自動將檔案儲存到下載資料夾，而不是詢問使用者要儲存檔案的位置。 這簡化了流覽體驗。                                                                                                                             | 0                 |

> [!IMPORTANT]
> Windows 10 小組 (目前) PBA 中部署漸進式 Web 應用程式。  另請注意，Surface Hub 不支援 Microsoft Edge 策略設定[WebAppInstallForceList。](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist) 

### 設定 Microsoft Edge 政策設定

使用 [Microsoft Edge 瀏覽器策略](https://docs.microsoft.com/deployedge/microsoft-edge-policies) 在 Microsoft Edge 中設定瀏覽器設定。 您可以使用以下方法來使用這些原則：

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)，
- [您偏好的行動裝置管理 (MDM) 支援 ADMX Ingestion](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)的提供者，或
- [在 Windows 組配置設計工具中使用 ADMX Ingestion 來部署套件](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)。

 
### 設定 Microsoft Edge 更新

根據預設，Microsoft Edge 會自動更新。 使用 [Microsoft Edge 更新政策](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies) 來設定 Microsoft Edge Update 的設定。
請注意，Surface Hub 不支援下列 Microsoft Edge 更新政策：

- **Allowsxs** – 在 Surface Hub 上，Microsoft Edge 穩定通道永遠會取代舊版 Microsoft Edge。
- **CreateDesktopShortcut** – Surface Hub 不使用桌面快速鍵。

> [!TIP]
>  Microsoft Edge 需要連線接到網際網路，以支援其功能。 確保必要的 [網域 URL](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) 已新加到允許清單中，以確保透過防火牆及其他安全性機制進行通訊。

## 相關連結

- [Microsoft Edge 文件](https://docs.microsoft.com/microsoft-edge/)

