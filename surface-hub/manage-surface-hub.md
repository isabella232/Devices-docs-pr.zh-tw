---
title: 管理 Microsoft Surface Hub
description: 如何在完成初次執行程式之後管理 Surface Hub。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/17/2018
ms.localizationpriority: medium
ms.openlocfilehash: 7fa715c679803da460cc1d57bd6e84fa33d30413
ms.sourcegitcommit: d9c413f1c50908a81e5489aca2c6023eab573148
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/13/2021
ms.locfileid: "12093040"
---
# <a name="manage-microsoft-surface-hub"></a>管理 Microsoft Surface Hub

在初始設定Microsoft Surface Hub，裝置設定和設定可以修改或變更為幾種方式：

- **本機管理** - 使用個別 Surface Hub 上的 **\[設定\]** 應用程式來在本機上設定。 為防止未經授權的使用者變更設定，[設定]應用程式要求您必須提供系統管理員認證才能開啟應用程式。 如需詳細資訊，請參閱[Surface Hub 設定的本機管理](local-management-surface-hub-settings.md)。
- 遠端**管理**- Surface Hub允許 IT 系統管理員使用行動裝置管理 (MDM) 提供者 ，例如 Microsoft Intune、Microsoft Endpoint Configuration Manager 和其他協力廠商提供者來管理設定和策略。 此外，系統管理員可以使用 Azure 監視器監控 Surface Hub。  詳細資訊請參閱使用 [MDM](manage-settings-with-mdm-for-surface-hub.md)提供者管理設定，以及使用 Azure 監視器監控 Surface Hub 以 [追蹤其健康情況](/azure/azure-monitor/insights/surface-hubs)。 

> [!NOTE]
> 這些管理方法不會互斥。 裝置可以同時是本機管理與遠端管理 (如果您選擇的話)。 不過，當系統與管理伺服器同步處理時，MDM Surface Hub會覆寫本地變更。 

## <a name="in-this-section"></a>本節內容

深入了解管理及更新 Surface Hub。

| 主題 | 描述 |
| ----- | ----------- |
| [遠端 Surface Hub 管理](remote-surface-hub-management.md) |有關遠端管理 Surface Hub 的主題。 包含安裝應用程式、使用 MDM 管理設定與使用 Operations Management Suite 監視。 |
| [管理 Surface Hub 設定](manage-surface-hub-settings.md) |有關管理 Surface Hub 的主題：協助工具、裝置管理、裝置重設、完整網域名稱、Windows Update 設定，以及無線網路 |
| [在 Surface Hub 上安裝應用程式](install-apps-on-surface-hub.md) | 系統管理員可以從 Microsoft Store 或商務用 Microsoft Store 安裝應用程式。|
[設定 Surface Hub 的 [開始] 功能表](surface-hub-start-menu.md) | 使用 MDM 來自訂 Surface Hub 的 [開始] 功能表。
| [設定和使用 Microsoft Whiteboard](whiteboard-collaboration.md)  | Microsoft Whiteboard 的最新更新包含兩個 Surface Hub 的功能，如此即可在相同白板上即時共同作業。   |
| [使用結束工作階段結束會議](finishing-your-surface-hub-meeting.md) | 在結束會議時，使用者可以點選 **\[結束工作階段\]** 來清除任何敏感性資料，並準備裝置以供下一場會議。|
| [使用 Microsoft Authenticator 登入 Surface Hub](surface-hub-authenticator-app.md) | 在 Android 和 iOS 使用 Microsoft Authenticator 應用程式，可以不使用密碼即登入 Surface Hub。   |
| [儲存您的 BitLocker 金鑰](save-bitlocker-key-surface-hub.md) | 每個 Surface Hub 都是使用 BitLocker 磁碟機加密軟體自動設定。 Microsoft 強烈建議您務必備份您的 BitLocker 修復金鑰。|
| [連接其他裝置並以 Surface Hub 顯示](connect-and-display-with-surface-hub.md) | 您可以將其他裝置連接到 Surface Hub 來顯示內容。|
| [現有無線網路或區域網路上的 Miracast](miracast-over-infrastructure.md) | 您可以在您的無線網路或區域網路上使用 Miracast 以連接到 Surface Hub。 |
 [啟用 802.1x 有線驗證](enable-8021x-wired-authentication.md) | Surface Hub 裝置上已啟用 802.1x 有線驗證 MDM 原則。 
| [使用會議室控制系統](use-room-control-system-with-surface-hub.md) | 會議室控制系統可以與您的 Microsoft Surface Hub 搭配使用。|
[使用 Surface Hub Recovery Tool](surface-hub-recovery-tool.md) | 使用 Surface Hub修復工具，重新影像處理SURFACE HUB SSD。
[Surface Hub SSD 取代](surface-hub-ssd-replacement.md) | 瞭解如何移除及取代硬碟中的Surface Hub。

## <a name="related-topics"></a>相關主題

- [檢視 Surface Hub 及 Windows 10 上的 Power BI 簡報模式](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)
