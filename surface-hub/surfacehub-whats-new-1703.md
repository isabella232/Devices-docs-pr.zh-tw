---
title: Windows10 (版本 1703) 中 Surface Hub 的新增功能
description: Windows 10 版本 1703 (Creators Update) 為 Microsoft Surface Hub 帶來了新的功能。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 722309a6b018c32bde329cb7b2cdd68b859fc1ca
ms.sourcegitcommit: 8e809e8481023fe4421abcdaa1e055a6f2f74f5f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/11/2020
ms.locfileid: "10924939"
---
# Windows10 (版本 1703) 中 Microsoft Surface Hub 的新增功能有哪些？

觀賞 Surface Hub 工程師 Jordan Marchese 展示 Windows 10 版本 1703 (Creators Update) 之 Microsoft Surface Hub 更新。 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

Windows 10 版本 1703 (也稱為 Creators Update)，為 Microsoft Surface Hub 引入了下列變更。

## 新設定

設定已新增至行動裝置管理 (MDM) 和設定服務提供者 (CSP)，以擴大 Surface Hub 的管理功能。 [新的設定包括](manage-settings-with-mdm-for-surface-hub.md)：

- InBoxApps/SkypeForBusiness/DomainName
- InBoxApps/Connect/AutoLaunch
- Properties/DefaultVolume
- Properties/ScreenTimeout
- Properties/SessionTimeout
- Properties/SleepTimeout
- Properties/AllowSessionResume
- Properties/AllowAutoProxyAuth
- Properties/DisableSigninSuggestions
- Properties/DoNotShowMyMeetingsAndFiles
- System/AllowStorageCard

加號設定根據新的 [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) 和 [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp)。
</br>

## 佈建精靈

簡單易用精靈可協助您快速建立佈建套件，供您套用至多個 Surface Hub 裝置，並且包括了大量加入 Azure Active Directory。 [了解如何為 Surface Hub 建立佈建套件。](provisioning-packages-for-certificates-surface-hub.md)

![佈建 Surface Hub 裝置精靈中的步驟](images/wcd-wizard.png)
    
## 您現有無線網路或區域網路上的 Miracast 

Microsoft 擴充了[透過區域網路傳送 Miracast 串流的能力](miracast-over-infrastructure.md)，而不是透過直接的無線連結。 
    
## 雲端復原

當您重設 Surface Hub 裝置時，您現在可以從雲端下載並安裝作業系統的原廠組建。 [深入了解雲端復原。](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
>如果您使用的是 Proxy 伺服器，則無法使用雲端復原。
    
![重新安裝](images/reinstall.png)
    
## 結束工作階段

**[我已完成]** 現在已更名為 **[結束工作階段]**。 [了解如何使用 [結束工作階段]。](finishing-your-surface-hub-meeting.md) 

![結束工作階段](images/end-session.png)



 

 
