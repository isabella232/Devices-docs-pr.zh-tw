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
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831422"
---
# 在 Surface Hub 上實施服務品質（QoS）

服務品質（QoS）是網路技術的組合，可讓系統管理員優化即時音訊/視頻與應用程式共用通訊的體驗。
 
在 Surface Hub 上設定[商務用 Skype 的 QoS，](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)就可以使用行動[裝置管理（MDM）提供者](manage-settings-with-mdm-for-surface-hub.md)或[提供套件](provisioning-packages-for-surface-hub.md)來完成。 
 
 
此程式說明如何使用 Microsoft Intune 設定 Surface Hub 的 QoS。 

1. 在 Intune 中，[建立自訂原則](https://docs.microsoft.com/intune/custom-settings-configure)。

    ![Intune 中的 [自訂策略建立] 對話方塊的螢幕擷取畫面](images/qos-create.png)

2. 在 [**自訂 OMA URI 設定**] 中，選取 [**新增**]。 針對您所新增的每個設定，您將會輸入名稱、描述（選擇性）、資料類型、OMA URI 及值。

    ![空白 [OMA URI 設定] 對話方塊的螢幕擷取畫面](images/qos-setting.png)

3. 新增下列自訂 OMA URI 設定：

    名稱 | 資料類型 | OMA-URI<br>./Device/Vendor/MSFT/NetworkQoSPolicy |  值
    --- | --- | --- | ---
    音訊來源埠 | 字串 |  /HubAudio/SourcePortMatchCondition  |   從您的 Skype 系統管理員取得值
    音效 DSCP | 整數 |  /HubAudio/DSCPAction  |   46
    影片來源埠 | 字串 |  /HubVideo/SourcePortMatchCondition   |  從您的 Skype 系統管理員取得值
    影片 DSCP | 整數 |  /HubVideo/DSCPAction   |   34
    音訊進程名稱 | 字串 |  /HubAudio/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe
    影片名稱 | 字串 |  /HubVideo/AppPathNameMatchCondition  |   Microsoft.PPISkype.Windows.exe

    >[!IMPORTANT]
    >每個**OMA URI**路徑都以開頭 `./Device/Vendor/MSFT/NetworkQoSPolicy` 。 例如，[音訊來源埠] 設定的完整路徑就是 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。




4. 原則建立之後，[就可以將它部署到 Surface Hub。](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)


>[!WARNING]
>目前，您無法在[NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)中設定設定**IPProtocolMatchCondition** 。 如果已設定此設定，原則將無法套用。
 
