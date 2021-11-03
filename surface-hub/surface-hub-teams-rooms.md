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
ms.reviewer: dpandre
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d5586e41a400c8e39c82aabf403db477f8af5c0e
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154158"
---
# <a name="microsoft-teams-rooms-on-surface-hub"></a>Surface Hub 上的 Microsoft Teams 會議室

Teams 會議室 ，Surface Hub [KB5004196、KB5004198 和 KB5004199](surface-hub-update-history.md)時，系統會自動取代先前的 Surface Hub Teams 應用程式。 [](hub-teams-app.md)

## <a name="whats-new"></a>有何新功能？

- 從歡迎畫面Surface Hub新議程頁面加入的會議正在加入「Edge to Edge」，將人員放在前景。
- 熟悉的會議功能，包括聊天泡泡、反應、桌面和應用程式共用、提供及控制及音訊、PowerPoint即時支援、共同模式和大型圖庫。
- Teams 會議室應用程式Surface Hub應用程式並排執行，或最小化執行。
- 系統管理員可以設定功能，例如協調會議及鄰近連接Surface Hub。 [XML 檔案](/microsoftteams/rooms/surface-hub-manage-config#teams-configuration-file-syntax) 受到支援，將會移至新的設定模型。
- 新的 QoS 選項和網路需求。 若要深入瞭解，請參閱在 Surface Hub 上設定會議室[的網路Microsoft Teams服務品質](surface-hub-teams-rooms-networking.md)。
- 如果尚未是預設值，Teams通話和通話的預設應用程式，設定Surface Hub** **  >  ****  >  **通話&音訊**。 若要深入瞭解會議模式，並透過 MDM 策略進行Surface Hub，請參閱使用 MDM 提供者管理[會議模式](manage-settings-with-mdm-for-surface-hub.md#changing-default-app-for-meetings--calls)。

## <a name="in-meeting-experience"></a>在會議體驗中

Teams 會議室會議Surface Hub與使用者從個人裝置所熟悉的體驗對齊，並針對大型螢幕裝置優化進行調整。 在 Teams 開啟Surface Hub可讓使用者存取主要功能，包括一鍵式會議加入、立即開會，以及 PSTN 或對等通話的撥號鍵台。

:::image type="content" source="images/teamsroomsagendascreen.png" alt-text="Teams 會議室議程Surface Hub。":::

:::image type="content" source="images/teamsroomsmeeting.png" alt-text="Teams 會議室會議Surface Hub會議。":::

## <a name="manage-teams-rooms-on-surface-hub"></a>在 Teams 會議室 管理Surface Hub

 輸入系統管理認證Teams，您可以直接從 設定 功能表自訂系統管理體驗，包括：

- 設定 [協調會議](/microsoftteams/rooms/coordinated-meetings) 與鄰近連接。
- 調整預設麥克風、相機和喇叭的設定。
- 檢查用戶端版本並搜尋最新更新。

:::image type="content" source="images/teamsroomssetttings.png" alt-text="Teams 會議室 設定。":::

適用于用戶端Teams 會議室的新Surface Hub會自動套用透過 XML 檔案、部署套件或 MDM 提供者所設定的現有設定。 這些方法在 Surface Hub 上的管理[Microsoft Teams](/microsoftteams/rooms/surface-hub-manage-config)組式中說明，將會由新的雲端式解決方案取代，[如下所述](#simplified-management-of-teams-coming-to-surface-hub)，Teams即將Surface Hub。

### <a name="prepare-networking-for-teams-rooms"></a>準備網路Teams 會議室

若要優化Teams 會議室請參閱在 Surface Hub 上為會議室設定網路與服務品質Microsoft Teams[所述的需求Surface Hub。](surface-hub-teams-rooms-networking.md)

### <a name="simplified-management-of-teams-coming-to-surface-hub"></a>簡化管理即將Teams的Surface Hub

當Teams 會議室Surface Hub公開發行時，系統管理員可以利用下列解決方案：

- **Teams系統管理中心。** Teams系統管理中心提供完整的自我管理平臺，以監控和管理Teams 會議室裝置Teams體驗。 Teams系統管理中心可供Microsoft Teams 會議室使用者使用，且無需支付額外費用。
- **Microsoft Teams 會議室管理服務。** Microsoft Teams 會議室[管理服務](/microsoftteams/rooms/microsoft-teams-rooms-premium)是一項雲端式 IT 管理和監控服務，可保持 Microsoft Teams 會議室 裝置及其周邊設備最新狀態並主動監控，支援優化環境，以創造良好的使用者體驗。


## <a name="support-for-teams-rooms-in-government-community-cloud-high-gcc-h"></a>支援 Teams 會議室 政府社群雲端 (GCC-H) 

當 Teams 會議室 Surface Hub 的 Surface Hub 於今年稍後公開發行時，用戶端需要一次手動更新至版本 1.4.00.25354，才能連接到 GCC-H 租使用者，然後自動保持最新狀態：

 - 確認您的中樞已安裝 KB5005611 或更新版本Windows累積更新
 - 使用[Teams_Uninstall_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Uninstall_Win32.ppkg)移除Teams 會議室上的Surface Hub
 - 重新開機裝置
 - 安裝 [Teams_win32.ppkg](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Teams_Win32.ppkg) 以安裝版本 1.4.00.25354
 - 再次重新開機您的裝置

詳細步驟：

1. 將兩個部署套件儲存到 USB 磁碟機的根目錄。
2.  將 USB 磁碟機插入您的Surface Hub。
3.  在 Surface Hub上，開啟[開始] 功能表，選取所有應用程式，然後選取 設定。
4.  當系統提示時，請提供您的中樞系統管理員認證。
5.  前往裝置**管理Surface Hub**  >  ****  >  **新增或移除部署套件**，然後選取新增**套件**。
6.  在**選取套件下**，選取 Teams_Uninstall_win32.ppkg 置備套件，然後重新開機Surface Hub。
7.  在 Surface Hub上，開啟[開始] 功能表，選取所有應用程式，然後選取 設定。
8.  當系統提示時，請提供您的中樞系統管理員認證。
9.  前往裝置**管理Surface Hub**  >  ****  >  **新增或移除部署套件**，然後選取新增**套件**。
10. 在**選取套件下**，選取 Teams_win32.ppkg 置備套件，然後重新開機Surface Hub。
