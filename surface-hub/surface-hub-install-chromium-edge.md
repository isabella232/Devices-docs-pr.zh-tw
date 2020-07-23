---
title: 在 Surface Hub 上安裝及設定新的 Microsoft Edge
description: 在 Surface Hub 上安裝及設定新的 Microsoft Edge。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: cf4d909a8c06bddf2bb0b3e42259f0b69cd97109
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894099"
---
# 在 Surface Hub 上安裝及設定新的 Microsoft Edge

Windows 10 Team 2020 更新支援以 Chromium （版本85及更新版本）為基礎的新 Microsoft Edge 作為 Surface Hub 的建議瀏覽器。 您可以使用預配套件手動安裝 Microsoft Edge，或使用 Microsoft Intune 或您慣用的行動裝置管理（MDM）提供者進行遠端安裝。

 根據預設，Surface Hub 裝置是預先預先安裝的 Microsoft Edge 舊版（版本44）。

> [!IMPORTANT]
> Surface Hub 需要新版 Microsoft Edge 的版本85或更新版本，且可用性僅限於「[開發人員通道](https://docs.microsoft.com/deployedge/microsoft-edge-channels)」，其設計目的是讓 IT 系統管理員儘早瞭解即將進行的邊緣功能，並準備好進行下一個 Beta 版本。  針對 Windows 測試人員暫時啟用開發人員通道的支援以預覽 Microsoft Edge。 （通常，Surface Hub 只支援發行到 "穩定通道" 的版本）。如需詳細資訊，請參閱[Microsoft Edge 頻道概覽。](https://docs.microsoft.com/deployedge/microsoft-edge-channels)
 
### 安裝 Microsoft Edge 開發人員通道組建 

- 根據設計，Microsoft Edge 開發管道會與 Microsoft Edge 舊版進行並排安裝，而使用者會在 Surface Hub [開始] 功能表中看到「Microsoft Edge 開發人員」（版本85）和「Microsoft Edge」（版本44）。 相反地，Microsoft Edge 穩定通道會將 Microsoft Edge 傳統版取代為預設瀏覽器。
- 安裝完成後，Microsoft Edge 開發通道不會自動顯示為釘選的 app。 若要開啟，請選取 [**啟動**  >  **所有 app**]。 相反地，Microsoft Edge 穩定通道會自動將 Microsoft Edge 舊版取代為 [所有應用程式] 清單中的固定應用程式。
- 將版本85升級為穩定通道後，Microsoft Edge 開發頻道就會自動從 [開始] 功能表中消失，而且您必須在 Surface Hub 上安裝 Microsoft Edge 穩定通道。

> [!NOTE]
>  若要移除新的 Microsoft Edge，必須重設裝置。 如需詳細資訊，請參閱[重設或復原 Surface Hub](https://docs.microsoft.com/surface-hub/device-reset-surface-hub) 。

## 安裝 Microsoft Edge

### 使用預配套件安裝 Microsoft Edge

1. 從電腦將[Microsoft Edge 置備套件](https://aka.ms/HubEdge)（MicrosoftEdgeDevInstaller）下載至 USB 磁片磁碟機的根資料夾。
2. 將 USB 磁片磁碟機插入 Surface Hub 中。
3. 從 Surface Hub 中，開啟 [**設定**]，並在出現提示時輸入您的系統管理員認證。
4. 瀏覽至 **\[Surface Hub\]** > **\[裝置管理\]**。 在 **\[佈建套件\]** 底下，選取 **\[新增或移除佈建套件\]**。
5. 選取 **[新增套件]**。
6. 選擇 [Microsoft Edge 預配套件]，然後選取 [**新增**]。
7. 您將會看到預配套件所套用變更的摘要。 選取 **\[是，請將它新增\]**。
8. 等待 Microsoft Edge 安裝完成。 安裝之後，請流覽至 Surface Hub [開始] 功能表，以存取新的 Microsoft Edge。              
還行
> [!IMPORTANT]
>  安裝完成後，Microsoft Edge 開發通道不會自動出現在 Surface Hub [開始] 功能表中的固定應用程式。 相反地，使用者會在 [**啟動**  >  **所有 app**] 底下找到它。 如果您使用的是預設的 [開始] 功能表版面配置，您可以將 [開始] 功能表與[Microsoft edge 置備套件](https://aka.ms/HubEdge)一起安裝，以將 Microsoft edge 新增為釘選的 app。 如需詳細資訊，請參閱以下章節：[在 Microsoft edge [開始] 功能表中顯示 Microsoft edge](#display-start)。

> [!NOTE]
> 如果有較新版本的 Microsoft Edge 可用，則會自動更新。
 
### 使用 Intune 安裝 Microsoft Edge
 
> [!NOTE]
> Surface Hub 裝置必須使用 Intune 進行註冊及管理。 如需詳細資訊，請參閱[使用 Microsoft Intune 管理 Surface Hub 的2秒](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)。
 

1. [從 Microsoft 下載 Microsoft Edge 安裝程式](https://www.microsoft.com/edge/business/download)。
    - 使用[開發人員通道](https://docs.microsoft.com/deployedge/microsoft-edge-channels)的目前版本 **（版本85）**
    - 選擇 [ **Windows 64 位**]
2. [將 Microsoft Edge 安裝程式新增為 Microsoft Intune 中的商務線 app](https://docs.microsoft.com/mem/intune/apps/lob-apps-windows)。
    - 如果您選擇使用 Microsoft Edge 更新來處理 Microsoft Edge 的自動更新，請務必設定 [忽略 app**版本**] 設定 [**應用程式資訊**] 窗格。 當您將此設定切換為 **[是]** 時，Microsoft Intune 將不會強制執行安裝在 Surface Hub 裝置上的 app 版本。

 
### 使用行動裝置管理安裝 Microsoft Edge

1. [從 Microsoft 下載 Microsoft Edge 安裝程式](https://www.microsoft.com/edge/business/download)。
    - 使用[開發人員通道](https://docs.microsoft.com/deployedge/microsoft-edge-channels)的目前版本 **（版本85）**
    - 選擇 [ **Windows 64 位**]
2. 在託管位置（例如本機檔案共用（\\server\share\MicrosoftEdgeEnterpriseX64.msi））暫存 Microsoft Edge 安裝程式。 Surface Hub 裝置必須具備存取託管位置的許可權。
3. 透過您的 MDM 提供者使用[EnterpriseDesktopAppManagement 配置服務提供者（CSP）](https://docs.microsoft.com/windows/client-management/mdm/enterprisedesktopappmanagement-csp)來安裝 Microsoft Edge。

 

## 設定 Microsoft Edge

### Surface Hub 的預設 Microsoft Edge 原則
Microsoft Edge 預先配置了下列原則，可為 Surface Hub 提供最優化的體驗。
 
> [!NOTE]
>  我們建議您保留這些原則的預設值。
 

| Microsoft Edge 原則                                                                                                    | 建議的體驗                                                                                                                                                                                                                                               | 預設值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](https://docs.microsoft.com/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 請勿自動從 Microsoft Edge 舊版中匯入資料類型和設定。 這樣可避免使用 Surface Hub 中的共用設定變更登入使用者的設定檔。                                                                                                 | 4                 |
| [BackgroundModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允許 Microsoft Edge 程式繼續在背景中執行，即使在最後一個瀏覽器視窗關閉之後，仍能在會話期間更快速地存取 web 應用程式。                                                                                                      | sr-1                 |
| [BrowserAddProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 請勿允許使用者在 Microsoft Edge 中建立新的設定檔。 這簡化了流覽和登入體驗。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 只允許一個使用者登入 Microsoft Edge。 這簡化了流覽和登入體驗                                                                                                                                                                | 0                 |
| [BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)                           | 讓使用者在 Microsoft Edge 中盡情享受單一登入（SSO）。 當使用者登入 Surface Hub 時，其認證可以流過支援的網站，而不需要重新驗證。  | sr-1                 |
| [ExtensionInstallBlockList](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 防止非系統管理員使用者在 Microsoft Edge 中安裝新的擴充功能。 若要設定預設安裝的延伸清單，請使用[ExtensionInstallForcelist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#extensioninstallforcelist)。 | *                 |
| [HideFirstRunExperience](https://docs.microsoft.com/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 在使用者第一次執行 Microsoft Edge 時，隱藏第一次執行體驗和啟動顯示畫面。 由於 Surface Hub 是共用的裝置，因此可簡化使用者體驗。                                                                      | sr-1                 |
| [InPrivateModeAvailability](https://docs.microsoft.com/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 停用 InPrivate 模式。 因為結束會話已經清除流覽資料，所以這簡化了流覽和登入體驗。                                                                                                                                          | sr-1                 |
| [NewTabPageSetFeedType](https://docs.microsoft.com/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 顯示 [新增] 索引標籤頁面上的 Office 365 摘要體驗。 當使用者登入 Surface Hub 時，這可讓您快速存取 Office 365 上的檔案和內容。                                                                                                        | sr-1                 |
| [NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 當使用者登入 Surface Hub 時，系統會使用其組織帳戶建立不會移動的設定檔。 這可簡化單一登入（SSO）體驗。                                                                                                 | sr-1                 |
| [PrintingEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#printingenabled)                       | 停用 Microsoft Edge 中的列印。 Surface Hub 不支援列印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 讓 Microsoft Edge 使用 Microsoft 服務主動驗證已登入的使用者。 這可簡化單一登入（SSO）體驗。                                                                                                                         | sr-1                 |
| [PromptForDownloadLocation](https://docs.microsoft.com/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自動將檔案儲存到 [下載] 資料夾，而不是要求使用者儲存檔案的位置。 這簡化了流覽體驗。                                                                                                                             | 0                 |

 
### 設定 Microsoft Edge 原則

使用[Microsoft edge 瀏覽器原則](https://docs.microsoft.com/deployedge/microsoft-edge-policies)來設定 microsoft edge 中的瀏覽器設定。 您可以使用下列原則來套用這些原則：

- [Microsoft Intune](https://docs.microsoft.com/deployedge/configure-edge-with-intune)、
- [支援 ADMX 攝取的偏好行動裝置管理（MDM）提供者](https://docs.microsoft.com/deployedge/configure-edge-with-mdm)，或
- [使用 Windows 配置設計工具中的 ADMX 攝取來預配套件](https://docs.microsoft.com/windows/configuration/wcd/wcd-admxingestion)。

 
### 設定 Microsoft Edge 更新

根據預設，Microsoft Edge 會自動更新。 使用[Microsoft edge 更新原則](https://docs.microsoft.com/deployedge/microsoft-edge-update-policies)來設定 Microsoft edge 更新的設定。
請注意，Surface Hub 不支援下列 Microsoft Edge 更新原則：

- **Allowsxs** –在 Surface Hub 上，Microsoft Edge 穩定通道總是取代 Microsoft edge 舊版。
- **CreateDesktopShortcut** – Surface Hub 不使用桌面快速鍵。

> [!NOTE]
>  Microsoft Edge 需要連線接到網際網路，以支援其功能。 確定所[需的網域 url](https://docs.microsoft.com/deployedge/microsoft-edge-security-endpoints)已新增至允許清單，以確保透過防火牆和其他安全機制進行通訊。
 
### <a name="display-start"></a> 在 Surface Hub [開始] 功能表中顯示 Microsoft Edge

安裝完成後，Microsoft Edge 開發通道不會自動出現在 Surface Hub [開始] 功能表中的固定應用程式。 相反地，使用者會在 [**啟動**  >  **所有 app**] 底下找到它。
如果您使用的是預設的 [開始] 功能表配置，您可以將 [開始] 功能表與 Microsoft Edge 預配套件一起安裝，以將 Microsoft Edge 新增為釘選的 app。
如果您想要套用自訂的 [開始] 功能表版面配置，請使用下列 XML 來新增 Microsoft Edge 的釘選磚。

```xml

<start:DesktopApplicationTile

DesktopApplicationLinkPath="C:\Program Files (x86)\Microsoft\Edge Dev\Application\msedge.exe"

Size="2x2"

Row="0"

Column="0"/>
```

如需詳細資訊，請參閱[設定 Surface Hub [開始] 功能表](https://docs.microsoft.com/surface-hub/surface-hub-start-menu)。
 
> [!NOTE]
> 新的 Microsoft Edge 不支援使用 SecondaryTiles 的釘選網站和連結。

## 相關連結

- [Microsoft Edge 檔](https://docs.microsoft.com/microsoft-edge/)。

