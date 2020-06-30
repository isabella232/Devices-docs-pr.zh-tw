---
title: 如何在 Surface Hub 上使用適用於 BitLocker 的雲端復原
description: 如何在 Surface Hub 上使用適用於 BitLocker 的雲端復原
ms.assetid: c0bde23a-49de-40f3-a675-701e3576d44d
keywords: 協助工具設定, \[設定\] 應用程式, 輕鬆存取
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 7912f9d1bab2ba625995c56d6d7da4e6b2d3df37
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831342"
---
# <span data-ttu-id="499e7-104">摘要</span><span class="sxs-lookup"><span data-stu-id="499e7-104">Summary</span></span>

<span data-ttu-id="499e7-105">本文說明如何使用雲端復原函數（如果您在 Surface Hub 裝置上不會受到 BitLocker 的意外提示）。</span><span class="sxs-lookup"><span data-stu-id="499e7-105">This article describes how to use the cloud recovery function if you are unexpectedly prompted by BitLocker on a Surface Hub device.</span></span>

> [!NOTE]
> <span data-ttu-id="499e7-106">只有在 BitLocker 復原金鑰無法使用時，才能按照這些步驟進行。</span><span class="sxs-lookup"><span data-stu-id="499e7-106">You should follow these steps only if a BitLocker recovery key isn't available.</span></span>

> [!WARNING]
> * <span data-ttu-id="499e7-107">此恢復程式會刪除內部磁片磁碟機的內容。</span><span class="sxs-lookup"><span data-stu-id="499e7-107">This recovery process deletes the contents of the internal drive.</span></span> <span data-ttu-id="499e7-108">如果處理常式失敗，內部磁片磁碟機就會無法使用。</span><span class="sxs-lookup"><span data-stu-id="499e7-108">If the process fails, the internal drive will become completely unusable.</span></span> <span data-ttu-id="499e7-109">如果發生這種情況，您必須向 Microsoft 記錄服務要求，以解決問題。</span><span class="sxs-lookup"><span data-stu-id="499e7-109">If this occurs, you will have to log a service request with Microsoft for a resolution.</span></span>
> * <span data-ttu-id="499e7-110">完成恢復程式後，裝置將會重設成出廠設定，並傳回它的 [不在畫面] 體驗狀態。</span><span class="sxs-lookup"><span data-stu-id="499e7-110">After the recovery process is complete, the device will be reset to the factory settings and returned to its Out of Box Experience state.</span></span>
> * <span data-ttu-id="499e7-111">在恢復之後，Surface Hub 必須完全重新配置。</span><span class="sxs-lookup"><span data-stu-id="499e7-111">After the recovery, the Surface Hub must be completely reconfigured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="499e7-112">這個程式需要開啟無法使用 proxy 或其他驗證方法的網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="499e7-112">This process requires an open Internet connection that does not use a proxy or other authentication method.</span></span>

## <span data-ttu-id="499e7-113">雲端恢復程式</span><span class="sxs-lookup"><span data-stu-id="499e7-113">Cloud recovery process</span></span>

<span data-ttu-id="499e7-114">若要執行雲端恢復，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="499e7-114">To perform a cloud recovery, follow these steps:</span></span>

1. <span data-ttu-id="499e7-115">選取 [**按 Esc] 以取得更多復原選項**。</span><span class="sxs-lookup"><span data-stu-id="499e7-115">Select **Press Esc for more recovery options**.</span></span>

   ![[取消轉義] 的螢幕擷取畫面](images/01-escape.png)

1. <span data-ttu-id="499e7-117">選取 [**略過這個磁片磁碟機**]。</span><span class="sxs-lookup"><span data-stu-id="499e7-117">Select **Skip this drive**.</span></span>

   ![略過此磁片磁碟機的螢幕擷取畫面](images/02-skip-this-drive.png)

1. <span data-ttu-id="499e7-119">選取 **[從雲端復原**]。</span><span class="sxs-lookup"><span data-stu-id="499e7-119">Select **Recover from the cloud**.</span></span>

   ![從雲端復原的螢幕擷取畫面](images/03-recover-from-cloud.png)

1. <span data-ttu-id="499e7-121">選取 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="499e7-121">Select **Yes**.</span></span>

   ![[是] 的螢幕擷取畫面](images/04-yes.png)

1. <span data-ttu-id="499e7-123">選取 [**重新安裝**]。</span><span class="sxs-lookup"><span data-stu-id="499e7-123">Select **Reinstall**.</span></span>

   ![重新安裝的螢幕擷取畫面](images/05a-reinstall.png)

   ![下載的螢幕擷取畫面](images/05b-downloading.png)

1. <span data-ttu-id="499e7-126">雲端復原程式完成後，請使用**全新的體驗**來開始重新配置。</span><span class="sxs-lookup"><span data-stu-id="499e7-126">After the cloud recovery process is complete, start the reconfiguration by using the **Out of Box Experience**.</span></span>

   ![[外框] 畫面的螢幕擷取畫面](images/06-out-of-box.png)

## <span data-ttu-id="499e7-128">「發生錯誤」錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="499e7-128">"Something went Wrong" error message</span></span>

<span data-ttu-id="499e7-129">此錯誤通常是由在恢復下載期間發生的網路問題所造成。</span><span class="sxs-lookup"><span data-stu-id="499e7-129">This error is usually caused by network issues that occur during the recovery download.</span></span> <span data-ttu-id="499e7-130">發生這個問題時，請不要關閉中樞，因為您無法重新開機。</span><span class="sxs-lookup"><span data-stu-id="499e7-130">When this issue occurs, don't turn off the Hub because you won't be able to restart it.</span></span> <span data-ttu-id="499e7-131">如果您收到此錯誤訊息，請返回「從雲端復原」步驟，然後重新啟動修復程式。</span><span class="sxs-lookup"><span data-stu-id="499e7-131">If you receive this error message, return to the "Recover from the cloud" step, and then restart the recovery process.</span></span>

1. <span data-ttu-id="499e7-132">選取 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="499e7-132">Select **Cancel**.</span></span>

   ![[取消] 的螢幕擷取畫面](images/07-cancel.png)

1. <span data-ttu-id="499e7-134">選取 [**疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="499e7-134">Select **Troubleshoot**.</span></span>

   ![疑難排解的螢幕擷取畫面](images/08-troubleshoot.png)

1. <span data-ttu-id="499e7-136">選取 **[從雲端復原**]。</span><span class="sxs-lookup"><span data-stu-id="499e7-136">Select **Recover from the cloud**.</span></span>

   ![從雲端復原的螢幕擷取畫面](images/09-recover-from-cloud2.png)

1. <span data-ttu-id="499e7-138">如果出現 [**找不到有線網路**] 錯誤，請選取 [**取消**]，然後讓 Surface Hub 重新探查有線網路。</span><span class="sxs-lookup"><span data-stu-id="499e7-138">If the **Wired network isn't found** error occurs, select **Cancel**, and then let the Surface Hub rediscover the wired network.</span></span>

   ![找不到有線網路的螢幕擷取畫面](images/10-cancel.png)