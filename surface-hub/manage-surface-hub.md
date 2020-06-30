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
ms.openlocfilehash: 04eb2b08ebc8fc7034ab5d27a038c5d517a2eda3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834228"
---
# 管理 Microsoft Surface Hub

完成 Microsoft Surface Hub 的初始設定之後，就可以使用下列數種方法來修改或變更裝置的設定和組態：

- **本機管理** - 使用個別 Surface Hub 上的 **\[設定\]** 應用程式來在本機上設定。 為防止未經授權的使用者變更設定，[設定]應用程式要求您必須提供系統管理員認證才能開啟應用程式。 如需詳細資訊，請參閱[Surface Hub 設定的本機管理](local-management-surface-hub-settings.md)。
- **遠端系統管理**-Surface HUB 允許 IT 管理員使用行動裝置管理（MDM）提供者（例如 microsoft Intune、Microsoft Endpoint Configuration Manager 及其他協力廠商提供者）來管理設定與原則。 此外，系統管理員可以使用 Microsoft Operations Management Suite (OMS) 監視 Surface Hub。 如需詳細資訊，請參閱[使用 MDM 提供者管理設定](manage-settings-with-mdm-for-surface-hub.md)與[監視您的 Microsoft Surface Hub](monitor-surface-hub.md)。 

> [!NOTE]
> 這些管理方法不會互斥。 裝置可以同時是本機管理與遠端管理 (如果您選擇的話)。 不過，當 Surface Hub 與管理伺服器同步時，MDM 原則與設定會覆寫任何本機變更。 

## 本節內容

深入了解管理及更新 Surface Hub。

| 主題 | 描述 |
| ----- | ----------- |
| [遠端 Surface Hub 管理](remote-surface-hub-management.md) |有關遠端管理 Surface Hub 的主題。 包含安裝應用程式、使用 MDM 管理設定與使用 Operations Management Suite 監視。 |
| [管理 Surface Hub 設定](manage-surface-hub-settings.md) |有關管理 Surface Hub 的主題：協助工具、裝置管理、裝置重設、完整網域名稱、Windows Update 設定，以及無線網路 |
| [在 Surface Hub 上安裝應用程式]( https://technet.microsoft.com/itpro/surface-hub/install-apps-on-surface-hub) | 系統管理員可以從 Microsoft Store 或商務用 Microsoft Store 安裝應用程式。|
[設定 Surface Hub 的 [開始] 功能表](surface-hub-start-menu.md) | 使用 MDM 來自訂 Surface Hub 的 [開始] 功能表。
| [設定和使用 Microsoft Whiteboard](whiteboard-collaboration.md)  | Microsoft Whiteboard 的最新更新包含兩個 Surface Hub 的功能，如此即可在相同白板上即時共同作業。   |
| [使用結束工作階段結束會議](https://technet.microsoft.com/itpro/surface-hub/i-am-done-finishing-your-surface-hub-meeting) | 在結束會議時，使用者可以點選 **\[結束工作階段\]** 來清除任何敏感性資料，並準備裝置以供下一場會議。|
| [使用 Microsoft Authenticator 登入 Surface Hub](surface-hub-authenticator-app.md) | 在 Android 和 iOS 使用 Microsoft Authenticator 應用程式，可以不使用密碼即登入 Surface Hub。   |
| [儲存您的 BitLocker 金鑰](https://technet.microsoft.com/itpro/surface-hub/save-bitlocker-key-surface-hub) | 每個 Surface Hub 都是使用 BitLocker 磁碟機加密軟體自動設定。 Microsoft 強烈建議您務必備份您的 BitLocker 修復金鑰。|
| [連接其他裝置並以 Surface Hub 顯示](https://technet.microsoft.com/itpro/surface-hub/connect-and-display-with-surface-hub) | 您可以將其他裝置連接到 Surface Hub 來顯示內容。|
| [現有無線網路或區域網路上的 Miracast](miracast-over-infrastructure.md) | 您可以在您的無線網路或區域網路上使用 Miracast 以連接到 Surface Hub。 |
 [啟用 802.1x 有線驗證](enable-8021x-wired-authentication.md) | Surface Hub 裝置上已啟用 802.1x 有線驗證 MDM 原則。 
| [使用會議室控制系統](https://technet.microsoft.com/itpro/surface-hub/use-room-control-system-with-surface-hub) | 會議室控制系統可以與您的 Microsoft Surface Hub 搭配使用。|
[使用 Surface Hub Recovery Tool](surface-hub-recovery-tool.md) | 使用 Surface Hub 恢復工具來重新影像 Surface Hub SSD。
[Surface Hub SSD 取代](surface-hub-ssd-replacement.md) | 瞭解如何在 Surface Hub 中移除及取代固態硬碟。

## 相關主題

- [檢視 Surface Hub 及 Windows 10 上的 Power BI 簡報模式](https://powerbi.microsoft.com/documentation/powerbi-mobile-win10-app-presentation-mode/)
