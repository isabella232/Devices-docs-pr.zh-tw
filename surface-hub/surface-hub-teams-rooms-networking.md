---
title: 在會議室設定網路和服務品質Microsoft Teams會議室Surface Hub
description: 本文將說明網路和服務品質的需求與建議，以優化Microsoft Teams 會議室Surface Hub。
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
ms.openlocfilehash: d06a69d89d94839c3a9616a29ff1be12badec76e
ms.sourcegitcommit: b5e7ea8118b848846cf1fb332ed7bf96c4583d20
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/20/2021
ms.locfileid: "11909973"
---
# <a name="configure-networking-and-quality-of-service-for-microsoft-teams-rooms-on-surface-hub"></a>在 Microsoft Teams 會議室 設定網路和服務品質Surface Hub

本文將說明如何準備您的環境，以優化Microsoft Teams 會議室Surface Hub。

## <a name="create-and-test-a-device-account"></a>建立和測試裝置帳戶

裝置帳戶是用戶端用來從 Microsoft Teams 會議室 存取功能的帳戶Exchange例如日曆，以及啟用商務用 Skype。 [請參閱建立和測試裝置帳戶](create-and-test-a-device-account-surface-hub.md)

## <a name="check-network-availability"></a>檢查網路可用性

> [!TIP]
> 我們強烈建議使用網路連接原則中列出的網路Microsoft 365[做法](https://aka.ms/pnc)

Teams 會議室Surface Hub使用者必須能存取符合這些要求的網路：

- 存取 Active Directory 或 Azure Active Directory (Azure AD) 實例
- 存取可以使用 DHCP 提供 IP 位址的伺服器。 Microsoft Teams 會議室上的Surface Hub無法以靜態 IP 位址進行配置。
- 存取 HTTP 埠 80 和 443。
- TCP 和 UDP 埠的埠與通訊協定需求所述，Microsoft 365及Office 365 URL 和[IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)位址範圍Microsoft Teams。

> [!IMPORTANT]
> Microsoft Teams 會議室不支援 Proxy 驗證，因為它可能會干擾 Teams。 在Surface Hub裝置或Microsoft 365服務端點進入生產之前，先Teams 會議室服務端點Surface Hub。

## <a name="implement-quality-of-service-qos-on-surface-hub"></a>在 (上) QoS Surface Hub

QoS (服務品質) 是網路技術的組合，可讓系統管理員優化即時音訊/視訊和應用程式共用通訊的體驗。
您可以使用行動裝置管理Microsoft Teams MDM Surface Hub，或透過部署套件，在 (上) [QoS。](manage-settings-with-mdm-for-surface-hub.md) [](provisioning-packages-for-surface-hub.md)

若要設定 QoS Surface Hub使用 Microsoft Intune：

1. 在 Intune 中 [，建立自訂策略](/intune/custom-settings-configure)。

2. 在**自訂 OMA-URI 設定**中 **，選取**新增 。 針對您新增的每個設定，您將輸入名稱、描述 (選項) 資料類型、OMA-URI 和值。

3. 若要在裝置上確保最佳的視Surface Hub音訊品質，請新增下列 QoS 設定至裝置。

    | 名稱                  | 說明           | OMA-URI                                                                        | 類型    | 值       |
    | --------------------- | --------------------- | ------------------------------------------------------------------------------ | ------- | ----------- |
    | **音效連接埠**       | 音訊連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/SourcePortmatchCondition      | 字串  | 50000-50019 |
    | **音效 DSCP**        | 音訊連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsAudio/DSCPAction                    | 整數 | 46          |
    | **影片連接埠**        | 影片連接埠範圍      | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/SourcePortchCondition      | 字串  | 50020-50039 |
    | **影片 DSCP**        | 影片連接埠標示   | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsVideo/DSCPAction                    | 整數 | 34          |
    | **共用埠**      | 共用埠範圍    | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/SourcePortmatchCondition    | 字串  | 50040-50059 |
    | **共用 DSCP**      | 共用埠標記 | ./Device/Vendor/MSFT/NetworkQoSPolicy/TeamsSharing/DSCPAction                  | 整數 | 18          |

4. 建立策略後，請將其部署到 Surface Hub。

## <a name="learn-more"></a>深入了解

- [在 (中 (QoS) 服務品質Microsoft Teams](/microsoftteams/qos-in-teams)
