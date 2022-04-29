---
title: 在 Surface Hub 上管理 Microsoft Edge
description: 本文說明設定瀏覽器設定的預設Microsoft Edge原則設定和工具。
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
ms.openlocfilehash: b652b990ce798d807ff2a27e87d212d01f3c23a2
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497726"
---
# <a name="manage-microsoft-edge-on-surface-hub"></a>在 Surface Hub 上管理 Microsoft Edge

使用[Microsoft Edge瀏覽器原則](/deployedge/microsoft-edge-policies)，透過下列任一方法在 Microsoft Edge 中設定瀏覽器設定：

- [Microsoft Intune](/deployedge/configure-edge-with-intune)
- [支援 ADMX 擷取的慣用行動裝置管理 (MDM) 提供者](/deployedge/configure-edge-with-mdm)
- [在Windows設定設計工具中使用 ADMX 擷取布建套件](/windows/configuration/wcd/wcd-admxingestion)

> [!TIP]
> 從螢幕頂端向下撥動以結束全螢幕模式需要兩只手指搭配新的Microsoft Edge。 結束全螢幕動作也可在長按觸控之後顯示的操作功能表中使用。

## <a name="default-microsoft-edge-policies-for-surface-hub"></a>Surface Hub的預設Microsoft Edge原則

Microsoft Edge會預先設定下列原則設定，以提供Surface Hub的優化體驗。


> [!TIP]
> 建議您保留這些原則設定的預設值。

| 原則設定                                                                                                   | 建議的體驗                                                                                                                                                                                                                                               | 預設值 |
| ---------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------- |
| [AutoImportAtFirstRun](/deployedge/microsoft-edge-policies#autoimportatfirstrun)             | 請勿自動從舊版 Microsoft Edge匯入資料類型和設定。 這可避免使用來自Surface Hub的共用設定來變更登入使用者的設定檔。                                                                                                 | 4                 |
| [BackgroundModeEnabled](/deployedge/microsoft-edge-policies#backgroundmodeenabled)           | 允許Microsoft Edge進程即使在關閉最後一個瀏覽器視窗之後仍繼續在背景中執行，以便在會話期間更快速地存取 Web 應用程式。                                                                                                      | 1                 |
| [BrowserAddProfileEnabled](/deployedge/microsoft-edge-policies#browseraddprofileenabled)     | 不允許使用者在Microsoft Edge中建立新的設定檔。 這可簡化流覽和登入體驗。                                                                                                                                                      | 0                 |
| [BrowserGuestModeEnabled](/deployedge/microsoft-edge-policies#browserguestmodeenabled)       | 只讓一位使用者登入Microsoft Edge。 這可簡化流覽和登入體驗                                                                                                                                                                | 0                 |
| [BrowserSignin](/deployedge/microsoft-edge-policies#browsersignin)                           | 可讓使用者在Microsoft Edge中享受單一Sign-On (SSO) 。 當使用者登入Surface Hub時，其認證可以流向支援的網站，而不需要他們重新驗證。  | 1                 |
| [ExtensionInstallBlockList](/deployedge/microsoft-edge-policies#extensioninstallblocklist)   | 防止非系統管理員使用者在 Microsoft Edge 中安裝新的擴充功能。 若要設定預設要安裝的擴充功能清單，請使用 [ExtensionInstallForcelist](/deployedge/microsoft-edge-policies#extensioninstallforcelist)。 | *                 |
| [HideFirstRunExperience](/deployedge/microsoft-edge-policies#hidefirstrunexperience)         | 隱藏使用者第一次執行Microsoft Edge時，通常會顯示的第一個執行體驗和啟動顯示畫面。 由於Surface Hub是共用裝置，這可簡化使用者體驗。                                                                      | 1                 |
| [InPrivateModeAvailability](/deployedge/microsoft-edge-policies#inprivatemodeavailability)   | 停用 InPrivate 模式。 由於結束會話已清除流覽資料，因此這可簡化流覽和登入體驗。                                                                                                                                          | 1                 |
| [NewTabPageSetFeedType](/deployedge/microsoft-edge-policies#newtabpagesetfeedtype)           | 在新的索引標籤頁面上顯示Office 365摘要體驗。 當使用者登入Surface Hub時，這可讓您快速存取其檔案和Office 365上的內容。                                                                                                        | 1                 |
| [NonRemovableProfileEnabled](/deployedge/microsoft-edge-policies#nonremovableprofileenabled) | 當使用者登入Surface Hub時，將會使用其組織帳戶建立非抽取式設定檔。 這可簡化單一Sign-On (SSO) 體驗。                                                                                                 | 1                 |
| [PrintingEnabled](/deployedge/microsoft-edge-policies#printingenabled)                       | 停用Microsoft Edge中的列印。 Surface Hub不支援列印。                                                                                                                                                                                              | 0                 |
| [ProActiveAuthEnabled](/deployedge/microsoft-edge-policies#proactiveauthenabled)             | 可讓Microsoft Edge使用Microsoft 服務主動驗證已登入的使用者。 這可簡化單一Sign-On (SSO) 體驗。                                                                                                                         | 1                 |
| [PromptForDownloadLocation](/deployedge/microsoft-edge-policies#promptfordownloadlocation)   | 自動將檔案儲存至 Downloads 資料夾，而不是要求使用者將檔案儲存在何處。 這可簡化流覽體驗。                                                                                                                             | 0                 |

> [!TIP]
> Windows 10 團隊版作業系統現在支援可部署的漸進式 Web 應用程式 (PWA) 。 若要深入瞭解，請參閱[在Surface Hub上安裝漸進式Web Apps](install-pwa-surface-hub.md)。 

### <a name="configure-microsoft-edge-updates"></a>設定Microsoft Edge更新

根據預設，Microsoft Edge會自動更新。 使用[Microsoft Edge更新原則](/deployedge/microsoft-edge-update-policies)來設定Microsoft Edge Update的設定。 請注意，Surface Hub不支援**CreateDesktopShortcut**原則設定，因為Surface Hub不使用桌面快捷方式。

> [!TIP]
> Microsoft Edge 需要連線接到網際網路，以支援其功能。 將 [必要的網域 URL 新](/deployedge/microsoft-edge-security-endpoints) 增至 [允許] 清單，以確保透過防火牆和其他安全性機制進行通訊。

## <a name="related-links"></a>相關連結

- [Microsoft Edge 文件](/microsoft-edge/)