---
title: 管理裝置帳戶密碼變換
description: 瞭解如何使用 PowerShell 設定 Surface Hub 2 內部部署帳戶
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: ea445588fe2242e3200284a39fdb4a3a8473f94a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832046"
---
# 管理裝置帳戶密碼變換

您可以將 Surface Hub 2 設定為自動變更裝置帳戶密碼，而不需要您手動更新裝置帳戶資訊。

如果您開啟 [密碼旋轉]，Surface Hub 2 秒會每隔7天變更一次密碼。 自動產生的密碼包含15-32 字元，包括大小寫字母、數位和特殊字元的組合。

密碼在會議期間不會變更。 如果 Surface Hub 的2秒是關閉的，它會在開啟或每10分鐘後立即嘗試變更密碼，直到成功為止。
