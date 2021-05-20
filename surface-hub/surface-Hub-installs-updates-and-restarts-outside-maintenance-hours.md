---
title: Surface Hub 可能會安裝更新，並在維護時間外重新開機
description: 自動更新Surface Hub疑難排解資訊
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: Surface Hub、維護視窗、更新
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.date: 04/15/2021
ms.openlocfilehash: 7df7857258c1baeedf4ff239eda17c66c93a531c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577023"
---
# <a name="surface-hub-may-install-updates-and-restart-outside-maintenance-hours"></a>Surface Hub 可能會安裝更新，並在維護時間外重新開機

在某些情況下，Surface Hub安裝更新，而不是在一般維護時段內安裝更新。 如有需要，裝置隨即重新開機。 在程式完成之前，您無法使用裝置。

> [!NOTE]  
> 這是錯過維護視窗時所未預期的行為。 只有當裝置長時間過期時，才會發生此情況。

## <a name="cause"></a>原因

為了確保系統Surface Hub使用，中心已配置為在 設定 (中定義的維護時段期間執行系統管理功能，請參閱) 下方的「參考資料」。 在此維護期間，中心會自動透過 WUfB Windows 更新或商務Windows更新 (任何) 。 更新完成後，中樞可能會重新開機。

更新只能在維護視窗期間安裝，Surface Hub開啟，但並未使用或保留更新。 例如，如果 Surface Hub排定為持續 24 小時的會議，則排程要安裝的任何更新都會延後，直到下一個維護視窗提供中樞。 如果 Hub 持續忙碌，並錯過多個維護視窗，則中樞最終會開始安裝並下載更新。 這可能發生在維護視窗期間或外部。 下載和安裝開始後，裝置可能會重新開機。

## <a name="to-avoid-this-issue"></a>若要避免此問題

您必須預留維護時間，Surface Hub系統管理功能。 將裝置Surface Hub 24 小時，或在維護視窗期間使用裝置延遲安裝更新。 我們建議您在排定的維護期間，不要使用或保留中樞。 應該保留兩小時的視窗以進行更新。

您可以使用其中一個選項來控制更新的可用性，Windows商務用更新。

## <a name="learn-more"></a>深入了解
 
- [更新 Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 
- [維護期間](manage-windows-updates-for-surface-hub.md#maintenance-window) 
