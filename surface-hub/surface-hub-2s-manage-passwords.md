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
# <span data-ttu-id="dda9d-104">管理裝置帳戶密碼變換</span><span class="sxs-lookup"><span data-stu-id="dda9d-104">Manage device account password rotation</span></span>

<span data-ttu-id="dda9d-105">您可以將 Surface Hub 2 設定為自動變更裝置帳戶密碼，而不需要您手動更新裝置帳戶資訊。</span><span class="sxs-lookup"><span data-stu-id="dda9d-105">You can configure Surface Hub 2S to automatically change a device account password without requiring you to manually update the device account information.</span></span>

<span data-ttu-id="dda9d-106">如果您開啟 [密碼旋轉]，Surface Hub 2 秒會每隔7天變更一次密碼。</span><span class="sxs-lookup"><span data-stu-id="dda9d-106">If you turn on Password Rotation, Surface Hub 2S changes the password every 7 days.</span></span> <span data-ttu-id="dda9d-107">自動產生的密碼包含15-32 字元，包括大小寫字母、數位和特殊字元的組合。</span><span class="sxs-lookup"><span data-stu-id="dda9d-107">The automatically generated passwords contain 15-32 characters including  a combination of uppercase and lowercase letters, numbers, and special characters.</span></span>

<span data-ttu-id="dda9d-108">密碼在會議期間不會變更。</span><span class="sxs-lookup"><span data-stu-id="dda9d-108">Passwords do not change during a meeting.</span></span> <span data-ttu-id="dda9d-109">如果 Surface Hub 的2秒是關閉的，它會在開啟或每10分鐘後立即嘗試變更密碼，直到成功為止。</span><span class="sxs-lookup"><span data-stu-id="dda9d-109">If Surface Hub 2S is turned off, it attempts to change the password immediately when turned on or every 10 minutes until successful.</span></span>
