---
title: Surface Hub 上的 Microsoft Teams 會議室
description: 本文概觀說明Microsoft Teams 會議室Surface Hub。
keywords: Teams 會議室、Surface Hub、Intune、QoS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 08/20/2021
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 05160bc2c1b77843b8ad832452501d7b065a8bc6
ms.sourcegitcommit: 38bde856b6091097d25745f6d080edebf72e3e17
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/21/2021
ms.locfileid: "12030818"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Surface Hub 上的 Microsoft Teams 會議室

Teams 會議室，Surface Hub應用程式會自動取代目前的 Surface Hub Teams 應用程式，作為自[](hub-teams-app.md)9 月 30 日開始為期 4 周的全域推出之一部分。 有關新版體驗的示範Teams，目前透過測試人員計畫提供預覽Windows，請參閱在 Teams 會議室 上[Surface Hub。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-teams-rooms-on-surface-hub/ba-p/2118373)

## <a name="whats-new"></a>有何新功能？

- 從歡迎畫面Surface Hub新議程頁面加入的會議正在加入「Edge 到 Edge」，將人員放在前景。
- 熟悉的會議功能，包括聊天泡泡、反應、桌面和應用程式共用、提供及控制及音訊、PowerPoint即時支援、共同模式和大型圖庫。
- Teams 會議室應用程式Surface Hub應用程式並排執行，或最小化執行。
- 系統管理員可以設定功能，例如協調會議及鄰近連接Surface Hub。 [XML 檔案](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) 受到支援，將會移至新的設定模型。
- 新的 QoS 選項和網路需求。 若要深入瞭解，請參閱在 Surface Hub 上設定會議室[的網路Microsoft Teams服務品質](surface-hub-teams-rooms-networking.md)Surface Hub。
- 變更為Teams模式，商務用 Skype預設共同合作和會議應用程式。 若要深入瞭解，請參閱為 Microsoft Teams[部署Surface Hub。](/MicrosoftTeams/teams-surface-hub)

## <a name="in-meeting-experience"></a>在會議體驗中

Teams 會議室會議Surface Hub與使用者從個人裝置所熟悉的體驗保持一致，並針對大型螢幕裝置進行優化而進行調整。 在 Teams開啟Surface Hub可讓使用者存取主要功能，包括一鍵式會議加入、立即開會，以及 PSTN 或對等通話的撥號鍵台。

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Teams 會議室議程Surface Hub。":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Teams 會議室會議Surface Hub會議。":::

## <a name="manage-teams-rooms-on-surface-hub"></a>在 Teams 會議室 管理Surface Hub

 輸入系統管理認證Teams，您可以直接從 設定 功能表自訂系統體驗，包括：

- 設定 [協調會議](/microsoftteams/rooms/coordinated-meetings) 與鄰近連接。
- 調整預設麥克風、相機和喇叭的設定。
- 檢查用戶端版本並搜尋最新更新。

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Teams 會議室 設定。":::

適用于用戶端Teams 會議室的新Surface Hub會自動套用透過 XML 檔案、部署套件或 MDM 提供者所設定的現有設定。 這些方法在[Surface Hub](/microsoftteams/rooms/surface-hub-manage-config)上的管理 Microsoft Teams 組式中說明，將會由新的雲端式解決方案取代，[如下文](#simplified-management-of-teams-coming-to-surface-hub)所述，Teams即將Surface Hub。

### <a name="prepare-networking-for-teams-rooms"></a>準備網路Teams 會議室

若要優化Teams 會議室請參閱在 Microsoft Teams 會議室設定網路和服務品質Microsoft Teams[所述Surface Hub。](surface-hub-teams-rooms-networking.md)

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>簡化管理即將Teams的Surface Hub

當Teams 會議室Surface Hub公開發行時，系統管理員可以利用下列解決方案：

- **Teams系統管理中心。** Teams系統管理中心提供完整的自我管理平臺，以監控和管理Teams 會議室裝置Teams體驗。 Teams系統管理中心可供Microsoft Teams 會議室使用者使用，無需支付額外費用。
- **Microsoft Teams 會議室管理服務。** Microsoft Teams 會議室[管理服務](/microsoftteams/rooms/microsoft-teams-rooms-premium)是一項雲端式 IT 管理與監控服務，可保持 Microsoft Teams 會議室 裝置及其周邊設備最新狀態，並主動監控，支援優化環境以創造最佳使用者體驗。
