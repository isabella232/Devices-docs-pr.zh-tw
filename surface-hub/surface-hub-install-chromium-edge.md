---
title: 在 Microsoft Edge 管理Surface Hub
description: 本文將說明設定Microsoft Edge設定瀏覽器設定的預設策略和工具。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 08/17/2021
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 80e861fd575324db21be458f7b82cd5fdb538b50
ms.sourcegitcommit: 68b6e86919d6e29155bf9386d05279866e1157e5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/19/2021
ms.locfileid: "12100711"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>在 Microsoft Edge 管理Surface Hub

使用[Microsoft Edge瀏覽器](/deployedge/microsoft-edge-policies)政策，透過下列任何Microsoft Edge在瀏覽器中設定瀏覽器設定：

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [您偏好的行動裝置管理 (MDM) 支援 ADMX Ingestion 的提供者](/deployedge/configure-edge-with-mdm)
- [在配置設計工具中使用 ADMX ingestion Windows套件](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> 若要離開全螢幕模式，請從螢幕手勢頂端向下滑動，需要使用兩指Microsoft Edge。 長按一下後，操作功能表中也會顯示退出全螢幕動作。

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>系統Microsoft Edge預設Surface Hub

Microsoft Edge預設定下列策略設定，為 Surface Hub。


> [!TIP]
> 建議您保留這些策略設定的預設值。

| 策略設定                                                                                                   | 建議的體驗                                                                                                                                                                                                                                               | 預設值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 請勿從系統自動從 舊版 Microsoft Edge。 這可避免使用共用設定變更已登錄使用者的設定檔，Surface Hub。                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允許Microsoft Edge程式即使在最後一個瀏覽器視窗關閉之後，也能夠持續在背景執行，讓網頁應用程式在會話期間能更快速地存取。                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允許使用者在檔案中建立Microsoft Edge。 這簡化了流覽和登錄體驗。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 啟用只有一個使用者可以Microsoft Edge。 這簡化了流覽和登錄體驗                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | 讓使用者在單一Sign-On (SSO) 中Microsoft Edge。 當使用者在帳戶上Surface Hub，他們的認證可以流程至支援的網站，而不需要重新驗證。  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 防止非系統管理員使用者在 Microsoft Edge 中安裝Microsoft Edge。 若要設定預設要安裝的擴充功能清單，請使用 [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist)。 | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隱藏第一次執行體驗，以及使用者第一次執行Microsoft Edge時通常會顯示的啟動畫面。 由於 Surface Hub是共用裝置，因此簡化了使用者體驗。                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 停用 InPrivate 模式。 由於 End Session 已經清除流覽資料，因此簡化了流覽和登錄體驗。                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 顯示新Office 365頁面上的新增進紙體驗。 當使用者已登錄檔案Surface Hub，這可讓您快速存取其檔案和Office 365。                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 當使用者在帳戶上Surface Hub，將會使用其組織帳戶建立無法移除的設定檔。 這簡化了單一Sign-On (SSO) 體驗。                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | 停用列印Microsoft Edge。 Surface Hub不支援列印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 啟用Microsoft Edge，以主動驗證已登錄的使用者Microsoft 服務。 這簡化了單一Sign-On (SSO) 體驗。                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自動將檔案儲存到下載資料夾，而不是詢問使用者儲存檔案的位置。 這簡化了流覽體驗。                                                                                                                             | 0                 |

> [!IMPORTANT]
> 目前作業系統不支援 (PWA) 可部署漸進式 web 應用程式Windows 10 團隊版應用程式。  另請注意，Microsoft Edge不支援[WebAppInstallForceList](/deployedge/microsoft-edge-policies#webappinstallforcelist)的 Surface Hub。

### <a name="configure-microsoft-edge-updates"></a>設定Microsoft Edge更新

根據預設，Microsoft Edge自動更新。 使用[Microsoft Edge更新策略](/deployedge/microsoft-edge-update-policies)來設定 Microsoft Edge Update。 請注意，Surface Hub**不支援 CreateDesktopShortcut**策略設定，Surface Hub使用桌面快捷方式。

> [!TIP]
> Microsoft Edge 需要連線接到網際網路，以支援其功能。 在允許清單中新增必要的網域 [URL，](/deployedge/microsoft-edge-security-endpoints) 以確保透過防火牆和其他安全性機制進行通訊。

## <a name="related-links"></a>相關連結

- [Microsoft Edge 文件](/microsoft-edge/)