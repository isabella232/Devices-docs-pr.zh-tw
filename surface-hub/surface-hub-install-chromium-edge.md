---
title: 在 Surface Hub 上安裝及設定新的 Microsoft Edge
description: 在 Microsoft Edge 上Microsoft Edge新Surface Hub。
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
ms.openlocfilehash: 93f76cadafe2570197fbe70db88540b6be90c3f1
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576723"
---
# <a name="install-and-configure-the-new-microsoft-edge-on-surface-hub"></a>在 Surface Hub 上安裝及設定新的 Microsoft Edge

Windows 10 團隊版 2020 Update 支援 Microsoft Edge 版本 Chromium (85 及) 以上的新 Microsoft Edge，做為 Surface Hub 2S 和 Surface Hub (v1 版本) 。 本文說明如何使用三種方法之一安裝瀏覽器：部署套件、Microsoft Intune或 MDM 提供者的協力廠商行動 (管理) 。

> [!IMPORTANT]
> 根據預設，Surface Hub裝置會預先安裝于 舊版 Microsoft Edge (44) 。 安裝[2020 Update](surface-hub-2020-update.md)之後，建議您切換到新的 Microsoft Edge瀏覽器;支援舊版 Microsoft Edge[將于](https://support.microsoft.com/microsoft-edge/what-is-microsoft-edge-legacy-3e779e55-4c55-08e6-ecc8-2333768c0fb0)2021 年 3 月 9 日結束。

> [!NOTE]
> 若要離開全螢幕模式，請從螢幕手勢頂端向下滑動，需要使用兩指Microsoft Edge。 長按一下後，操作功能表中也會顯示退出全螢幕動作。


## <a name="install-microsoft-edge-using-a-provisioning-package"></a>使用Microsoft Edge套件安裝

1. 從電腦下載 MicrosoftEdgeInstaller.ppkg Microsoft Edge套件 (MicrosoftEdgeInstaller.ppkg) 到 USB 磁碟機的根資料夾。 [](https://aka.ms/HubEdge)
2. 將 USB 磁碟機插入Surface Hub。
3. 從 Surface Hub，開啟**設定，** 並輸入系統提示您的系統管理員認證。
4. 瀏覽至 **\[Surface Hub\]** > **\[裝置管理\]**。 在 **\[佈建套件\]** 底下，選取 **\[新增或移除佈建套件\]**。
5. 選取 **[新增套件]**。
6. 選擇 Microsoft Edge套件，**然後選取**新增 。
7. 您將看到部署套件所套用之變更的摘要。 選取 **\[是，請將它新增\]**。
8. 等待安裝Microsoft Edge完成。 安裝完成後，請流覽至 Surface Hub 功能表以存取新的Microsoft Edge。              

> [!NOTE]
> 如果有較新版本的可用Microsoft Edge，系統就會自動更新。
 
## <a name="install-microsoft-edge-using-intune"></a>使用 intune Microsoft Edge安裝應用程式
 
> [!NOTE]
> 若要使用此安裝方法，Surface Hub裝置必須註冊並使用 Intune 進行管理。 詳細資訊，請參閱使用[MDM Surface Hub管理 2S。](manage-settings-with-mdm-for-surface-hub.md)
 

1. [下載 Microsoft Edge安裝程式](https://www.microsoft.com/edge/business/download)。
    - 使用目前版本從 [穩定](https://docs.microsoft.com/deployedge/microsoft-edge-channels)通道 ** (版本 85) **
    - 選擇**Windows 64 位**
2. [將 Microsoft Edge安裝程式新增為商務用應用程式至 Microsoft Intune。](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)
    - 如果您選擇使用應用程式Microsoft Edge Update自動更新Microsoft Edge，請務必設定忽略**應用程式**版本設定**應用程式資訊**窗格。 當您將這項設定切換為**是時**，Microsoft Intune不會強制執行安裝在裝置上的應用程式Surface Hub版本。

## <a name="install-microsoft-edge-using-third-party-mdm-provider"></a>使用Microsoft Edge MDM 提供者安裝

1. [從 Microsoft Microsoft Edge下載安裝程式](https://www.microsoft.com/edge/business/download)。
    - 使用目前版本從 [穩定](https://docs.microsoft.com/deployedge/microsoft-edge-channels)通道 ** (版本 85) **
    - 選擇**Windows 64 位**
2. 將 Microsoft Edge安裝程式階段位於託管位置，例如本地檔案共用 (\\server\share\MicrosoftEdgeEnterpriseX64.msi) 。 Surface Hub裝置必須擁有存取託管位置的許可權。
3. 透過 MDM 提供者使用[EnterpriseDesktopAppManagement](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp) (CSP) 提供者來安裝Microsoft Edge。

## <a name="configure-microsoft-edge"></a>設定 Microsoft Edge

### <a name="default-microsoft-edge-policies-for-surface-hub"></a>系統Microsoft Edge預設Surface Hub

Microsoft Edge預設定下列策略設定，為 Surface Hub。
 
> [!TIP]
> 建議您保留這些策略設定的預設值。
 

| 策略設定                                                                                                   | 建議的體驗                                                                                                                                                                                                                                               | 預設值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 請勿從系統自動從 舊版 Microsoft Edge。 這可避免使用共用設定變更已登錄使用者的設定檔，Surface Hub。                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允許Microsoft Edge程式即使在最後一個瀏覽器視窗關閉之後，也能夠持續在背景執行，讓網頁應用程式在會話期間能更快速地存取。                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允許使用者在 Microsoft Edge 中建立Microsoft Edge。 這簡化了流覽和登錄體驗。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 僅啟用一個使用者來Microsoft Edge。 這簡化了流覽和登錄體驗                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 讓使用者在 Sign-On (中) 單Microsoft Edge SSO Microsoft Edge。 當使用者在帳戶上Surface Hub，他們的認證可以流程至支援的網站，而不需要重新驗證。  | 1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 防止非系統管理員的使用者在 Microsoft Edge。 若要設定預設要安裝的擴充功能清單，請使用 [ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist)。 | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隱藏第一次執行體驗，以及使用者第一次執行Microsoft Edge時通常會顯示的啟動畫面。 由於 Surface Hub是共用裝置，因此簡化了使用者體驗。                                                                      | 1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 停用 InPrivate 模式。 由於 End Session 已經清除流覽資料，因此簡化了流覽和登錄體驗。                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 顯示新Office 365頁面上的新增進紙體驗。 當使用者已登錄檔案Surface Hub，這可讓您快速存取其檔案和Office 365。                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 當使用者在帳戶上Surface Hub，將會使用其組織帳戶建立無法移除的設定檔。 這簡化了單一Sign-On (SSO) 體驗。                                                                                                 | 1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | 停用在 Microsoft Edge 中列印。 Surface Hub不支援列印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 啟用Microsoft Edge，以主動驗證已登錄的使用者Microsoft 服務。 這簡化了單一Sign-On (SSO) 體驗。                                                                                                                         | 1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自動將檔案儲存到下載資料夾，而不是詢問使用者儲存檔案的位置。 這簡化了流覽體驗。                                                                                                                             | 0                 |

> [!IMPORTANT]
> 目前作業系統不支援 (PWA) 可部署漸進式 web 應用程式Windows 10 團隊版應用程式。  另請注意，Microsoft Edge不支援[WebAppInstallForceList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#webappinstallforcelist)的 Surface Hub。 

### <a name="configure-microsoft-edge-policy-settings"></a>設定Microsoft Edge設定

使用[Microsoft Edge瀏覽器策略](https://docs.microsoft.com/deployedge/microsoft-edge-policies)，在瀏覽器中設定瀏覽器Microsoft Edge。 這些原則可以使用：

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)，
- [您偏好的行動裝置管理 (MDM) 支援 ADMX Ingestion](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)的提供者，或
- [使用 ADMX Ingestion 在 Windows 設計工具中部署套件](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)。

 
### <a name="configure-microsoft-edge-updates"></a>設定Microsoft Edge更新

根據預設，Microsoft Edge自動更新。 使用[Microsoft Edge更新策略](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)來設定Microsoft Edge Update。
請注意，Surface Hub不支援下列更新Microsoft Edge：

- **Allowsxs** – 在 Surface Hub，Microsoft Edge穩定通道會永遠取代舊版 Microsoft Edge。
- **CreateDesktopShortcut** - Surface Hub不使用桌面快捷方式。

> [!TIP]
>  Microsoft Edge 需要連線接到網際網路，以支援其功能。 請確保 [必要的網域 URL](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints) 新加到允許清單中，以確保透過防火牆和其他安全性機制進行通訊。

## <a name="related-links"></a>相關連結

- [Microsoft Edge 文件](https://docs.microsoft.com/microsoft-edge/)

