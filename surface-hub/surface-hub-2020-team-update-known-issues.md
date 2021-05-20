---
title: 已知問題：Surface Hub
description: 此頁面提供 Surface Hub 的已知問題清單
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
ms.openlocfilehash: 172495530c4799ea59bf218dc1411bb4b230eef2
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576893"
---
# <a name="known-issues-surface-hub"></a>已知問題：Surface Hub

本文列出目前作業系統的 Surface Hub 已知問題，Windows 10 團隊版 2020 Update。

若要確保Surface Hub收到最新的更新，請以系統管理員帳戶登錄，然後選取 設定 更新和安全性**** Windows所有應用程式，  >  ****  >  ****  >  **然後安裝所有**更新。




| 問題                                                                                                   | 說明                                                                                                                                                                                                                                                                                                                                                                                                                             | 解決方式                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 在裝置上Surface Hub Whiteboard 應用程式時，無法透過電子郵件共用內容。             | 當執行 Whiteboard 匯出流程以電子郵件方式將 Whiteboard 應用程式的內容以電子郵件方式Surface Hub，這些裝置目前會顯示「您的裝置未設定為電子郵件」。  因此，白板內容無法透過電子郵件共用。                                                                                                                                                                                                                   | Microsoft 已發現這個問題，並正在積極調查此問題。  Microsoft 會儘快提供有關解決方案的其他資訊。                                                                                                                                                                                                                                                                                                                                                                   |
| 某些 Surface Hub 在 Azure 記錄分析中遇到連接問題 (稱為 OMS) 工作區。                                                                        | 對於受影響的Surface Hub，使用 Azure 監視器時，不會向工作區報告任何資料。                                                                                                                                                                                                                                      | Microsoft 已發現這個問題，並正在積極調查此問題。  Microsoft 會儘快提供有關解決方案的其他資訊。                                                                                                                                                                                                                                                                                                                                                                   |
| 一小部分的 v1 Surface Hub裝置無法自動升級至 2020 Windows 10 團隊版更新。                                            | 此 v1 裝置Surface Hub子集合的狀態，無法透過更新直接升級Windows相容。                                                                                                                                          | 使用修復工具手動將裝置重新影像Windows 10 團隊版 2020 更新Surface Hub[影像](surface-hub-recovery-tool.md)。                                                                                                                                                                                 |
| Surface Hub安裝 2020 更新之後，系統會顯示「Windows 10 團隊版裝置」訊息。                                                                        | 在 Windows 2020 Windows 10 團隊版更新程式期間，某些 Hub v1 裝置會進入無法啟動的狀態。                                                                                                                                                                                                                                       | 使用修復工具手動將裝置重新影像Windows 10 團隊版 2020 更新Surface Hub[影像](surface-hub-recovery-tool.md)。                                                                                                                                                          |
| 混合式裝置帳戶與內部部署信箱的日曆同步處理失敗。   | Surface Hub預設為使用 Azure AD 中帳戶的新式驗證，即使其內部部署信箱無法使用此功能。 在這種情況下，Exchange停止將會議同步到裝置。 因此，裝置不會接收或顯示新的會議。                                                                                                    | [安裝 KB4598291](https://support.microsoft.com/help/4598291) (或後續 Windows CU) 之後[，SurfaceHub CSP](https://docs.microsoft.com/windows/client-management/mdm/surfacehub-csp)會提供新的 ExchangeModernAuthEnabled 參數，可切換新式驗證的使用。 這可透過 MDM 策略或設定套件[](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg)設定為 false，以防止 Hub 使用新式驗證。                                                                                                |
| 中樞 2S 裝置無法使用 WSUS 接收驅動程式更新。                                             | Surface Hub 2S 支援Windows更新Windows商務用更新來發佈驅動程式;不支援透過 Windows Server Update Services (WSUS) 發佈。                                                                                                                                                                                                                                                                      | 如果使用 WSUS，請Windows商務用更新。<br> <br>**深入瞭解：**[什麼是Windows更新？](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)                                                                                                                                                                                                                                                                                                                            |
| 使用 Edge Legacy 瀏覽器時，無法透過電子郵件共用網頁筆記。 | 建立網頁筆記並流覽共用流程以以電子郵件傳送筆記之後，「傳送」按鈕不會出現。 因此，記事無法透過電子郵件共用。 | 已安裝 2020 更新的 Surface Hub 可以升級至新的 Microsoft Edge 瀏覽器，而透過電子郵件共用筆記則適用于該瀏覽器。<br> <br>**深入瞭解：**[在 Microsoft Edge 安裝Surface Hub](surface-hub-install-chromium-edge.md) |
| 控制中心有一個無法設定連結。 | 此連結不應出現在Windows 10 團隊版，並可能會造成混淆。   | 功能與 2020 更新之前相同;應該會使用開始功能表的 App 區段來啟動 設定應用程式。    |
