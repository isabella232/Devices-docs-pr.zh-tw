---
title: 在 Surface Hub 上實現服務品質
ms.reviewer: ''
manager: laurawi
description: 瞭解如何在 Surface Hub 上設定 QoS。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470481"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a>在 Surface Hub 上 (QoS) 服務品質

QoS (服務品質) 是網路技術的組合，可讓系統管理員優化即時音訊/視訊和應用程式共用通訊的體驗。
 
您可以在 Surface Hub 上使用行動裝置管理或透過 MDM (或) 套件，在 Surface Hub 上配置商務用[Skype](manage-settings-with-mdm-for-surface-hub.md) [的](provisioning-packages-for-surface-hub.md) [QoS。](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) 
 
 
此程式說明如何使用 Microsoft Intune 設定 Surface Hub 的 QoS。 

1. 在 Intune 中 [，建立自訂策略](https://docs.microsoft.com/intune/custom-settings-configure)。

    > [!div class="mx-imgBorder"]
    > ![Intune 中自訂策略建立對話方塊的螢幕擷取畫面](images/qos-create.png)

2. 在 **自訂 OMA-URI 設定**中 **，選取**新增 。 針對您新增的每個設定，您將輸入名稱、描述 (選項) 資料類型、OMA-URI 和值。

    > [!div class="mx-imgBorder"]
    > ![空白 OMA-URI 設定對話方塊的螢幕擷取畫面](images/qos-setting.png)

3. 新增下列自訂 OMA-URI 設定：<br/><br/>

    名稱 | 資料類型 | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  值
    --- | --- | --- | ---
    音訊來源埠 | 字串 |  /HubAudio/SourcePortchCondition  |   從 Skype 系統管理員取得值
    音效 DSCP | 整數 |  /HubAudio/DSCPAction  |   46
    視音訊來源埠 | 字串 |  /HubVideo/SourcePortchCondition   |  從 Skype 系統管理員取得值
    影片 DSCP | 整數 |  /HubVideo/DSCPAction   |   34
    音訊程式名稱 | 字串 |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    視音訊程式名稱 | 字串 |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >每個 **OMA-URI** 路徑的開頭為 `./Device/Vendor/MSFT/NetworkQoSPolicy` 。 例如，音訊來源埠設定的完整路徑為 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。

4. 建立該策略後，請將其部署到 Surface Hub。


>[!WARNING]
>目前，您無法在[NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)CSP 中設定**IPProtocolMatchCondition** 。 如果已設定此設定，原則將無法適用。
 
