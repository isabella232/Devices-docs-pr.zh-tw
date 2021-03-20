---
title: 已知問題：Windows 10 小組 2020 更新
description: 此頁面提供 Indows 10 小組 2020 Update 的已知問題清單。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/09/2021
ms.localizationpriority: Medium
ms.openlocfilehash: 903307112433d794052a4a4e9694f3e793d248c8
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442111"
---
# <a name="known-issues-windows-10-team-2020-update"></a>已知問題：Windows 10 小組 2020 更新 

本文列出 Windows 10 小組 2020 Update 的已知問題，即 Surface Hub 目前的作業系統。

若要確保 Surface Hub 收到最新的更新，請以系統管理帳戶登錄，然後選取所有**應用程式**設定更新和安全性  >  ****  >  ****  >  **Windows Update，** 然後安裝所有更新。




| 問題                                                                                                   | 說明                                                                                                                                                                                                                                                                                                                                                                                                                             | 解決方式                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 選擇性的非安全性更新 (也稱為「C」和「D」版本) 未安裝在特定中樞裝置上。            | Surface Hub 改良功能通常是透過每個月的第 3 個星期二的非安全性更新 ("C"發行) 。 此問題導致必須等到下個月的第 2 個星期二 ("B"發行安全性更新) 接收中樞特定的累積更新。 | 目前沒有任何補救。                                                                                                                                                                                                                                                                                                                                     |
| 嘗試安裝 Windows 10 小組 2020 更新之後，Surface Hub 會顯示「無法啟動裝置」訊息。                                                                        | 在更新程式期間，某些 Hub v1 裝置會進入無法啟動的狀態。                                                                                                                                                                                                                                       | 使用 Surface Hub 修復 [工具重新影像裝置](surface-hub-recovery-tool.md)。                                                                                                                                                                                                                                                                                                                                                                   |
| 混合式裝置帳戶與內部部署信箱的日曆同步處理失敗。   | Surface Hub 裝置預設會針對 Azure AD 中的帳戶使用新式驗證，即使其內部部署信箱無法使用此功能。 在這種情況下，Exchange 會停止將會議同步到裝置。 因此，裝置不會接收或顯示新的會議。                                                                                                    | [安裝 KB4598291](https://support.microsoft.com/help/4598291) (或後續的 Windows CU) 之後[，SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)會提供新的 ExchangeModernAuthEnabled 參數，可切換新式驗證的使用。 這可透過 MDM 策略或設定套件[](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg)設定為 false，以防止 Hub 使用新式驗證。                                                                                                |
| 使用條件式 Access 原則設定時，會影響登錄。                                    | 當裝置設定為使用合規性策略設定時，需要裝置層級資訊 (例如「需要防火牆」) 時，會觸發條件式存取錯誤 53000。 發生此情況時，使用者無法登錄裝置。                                                                                                                                                                                                 | 客戶可以排除在 Surface Hub 裝置上執行需要裝置層級資訊的合規性策略設定。 如果因合規性或安全性限制而無法執行這項操作，Hub 裝置不應安裝 2020 更新。 |
| 中樞 2S 裝置無法使用 WSUS 接收驅動程式更新。                                             | Surface Hub 2S 支援 Windows Update 和商務用 Windows Update 來發佈驅動程式;不支援透過 Windows Server Update Services (WSUS) 發佈。                                                                                                                                                                                                                                                                      | 如果使用 WSUS，請遷移到商務用 Windows Update。<br> <br>**深入瞭解：**[什麼是商務用 Windows 更新？](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)                                                                                                                                                                                                                                                                                                                            |
| 使用電話來登錄 Surface Hub 時，Azure Active Directory 已加入的裝置無法單一登入 | 如果 IT 系統管理員已將租使用者設成[](surface-hub-2s-phone-authenticate.md)使用無密碼驗證來登錄 Surface Hub，且裝置已加入 AAD，使用者就無法使用行動電話等行動裝置來登錄。                                                                                                       | 手動登錄 Surface Hub。                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| 使用 Edge 舊版瀏覽器時，無法透過電子郵件共用 Web Notes。 | 建立網頁筆記並流覽共用流程以以電子郵件傳送筆記之後，「傳送」按鈕不會出現。 因此，記事無法透過電子郵件共用。 | 已安裝 2020 更新的 Surface Hub 可以升級至新的 Microsoft Edge 瀏覽器，而透過電子郵件共用筆記則適用于該瀏覽器。<br> <br>**深入瞭解：**[在 Surface Hub 上安裝新的 Microsoft Edge](surface-hub-install-chromium-edge.md) |
| 控制中心有一個無法按一下的設定連結。 | 此連結不應出現在 Windows 10 小組中，而且可能會造成混淆。   | 功能與 2020 更新之前相同;應該會使用開始功能表的 App 區段來啟動設定應用程式。    |
