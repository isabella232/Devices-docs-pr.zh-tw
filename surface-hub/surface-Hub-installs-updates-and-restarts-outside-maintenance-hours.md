---
title: Surface Hub 可能會安裝更新，並在維護時間外重新開機
description: 關於「自動更新」的 Surface Hub 疑難排解資訊
ms.assetid: 6C09A9F8-F9CF-4491-BBFB-67A1A1DED0AA
keywords: surface hub，維護視窗，更新
ms.prod: surface-hub
ms.sitesec: library
author: Teresa-MOTIV
ms.author: v-tea
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 117c18cfce6dfb84b4fe2156ea98198f96da2abf
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831929"
---
# Surface Hub 可能會安裝更新，並在維護時間外重新開機

在特定情況下，Surface Hub 會在上班時間期間安裝更新，而不是在一般維護視窗期間進行。 裝置然後視需要重新開機。 在處理常式完成之前，您無法使用裝置。

> [!NOTE]  
> 這並不是遺失維護視窗的預期行為。 只有在裝置已過期時，才會發生這種情況。

## 原因
為了確保 Surface Hub 在上班時間期間仍可供使用，中心設定為在 [設定] 中定義的維護視窗期間執行系統管理功能（請參閱下方的「參考」）。 在此維護期間，Hub 會透過 Windows Update 或 Windows Server Update Services （WSUS）自動安裝任何可用的更新。 更新完成後，中樞可能會重新開機。

您可以在 [維護] 視窗期間安裝更新，只要 Surface Hub 開啟但未使用或未保留。 例如，如果 Surface Hub 排程的是持續24小時的會議，任何排程要安裝的更新將會延遲，直到在下一個維護時段內提供該中樞。 如果中樞繼續繁忙且未命中多個維護視窗，則中心將會最終開始安裝並下載更新。 這可能會在維護視窗期間或外發生。 下載和安裝開始之後，裝置可能會重新開機。

## 若要避免此問題

請務必為 Surface Hub 留出維護時間，以執行管理功能。 保留24小時間隔的 Surface Hub，或在維護視窗期間使用裝置會延遲安裝更新。 我們建議您在排程的維護期間不要使用或保留中樞。 必須保留兩個小時的視窗，才能進行更新。

您可以用來控制更新可用性的一個選項是「Windows Server Update Services （WSUS）」。 WSUS 提供控制要安裝的更新和時間。

## 參考資料 
 
[更新 Surface Hub](first-run-program-surface-hub.md#update-the-surface-hub) 

[維護期間](manage-windows-updates-for-surface-hub.md#maintenance-window) 

[使用 WindowsServer Update Services (WSUS) 來部署 Windows10 更新](/windows/deployment/update/waas-manage-updates-wsus) 


