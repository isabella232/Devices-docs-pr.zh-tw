---
title: 表面 DMA 保護
description: 本文將說明相容 Surface 裝置上的 DMA 保護
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 6/10/2020
ms.reviewer: carlol
manager: laurawi
audience: itpro
ms.openlocfilehash: 00994263cd61086ab86996920543a717a63d5078
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831401"
---
# <span data-ttu-id="33841-103">Surface 裝置上的 DMA 保護</span><span class="sxs-lookup"><span data-stu-id="33841-103">DMA Protection on Surface devices</span></span>

<span data-ttu-id="33841-104">[直接記憶體存取（DMA）] 保護旨在減少與使用可移動 SSDs 或外部儲存裝置相關的潛在安全性漏洞。</span><span class="sxs-lookup"><span data-stu-id="33841-104">Direct Memory Access (DMA) protection is designed to mitigate potential security vulnerabilities associated with using removable SSDs or external storage devices.</span></span> <span data-ttu-id="33841-105">較新的 Surface 裝置預設為啟用 DMA 保護。</span><span class="sxs-lookup"><span data-stu-id="33841-105">Newer Surface devices come with DMA Protection enabled by default.</span></span> <span data-ttu-id="33841-106">這些包括 Surface Pro 7、Surface 膝上型3和 Surface Pro X。 若要檢查您裝置上的 DMA 保護功能是否存在，請開啟 [系統資訊] （**啟動**  >  **msinfo32.exe**），如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="33841-106">These include Surface Pro 7, Surface Laptop 3, and Surface Pro X.  To check the presence of DMA protection feature on your device, open System Information (**Start** > **msinfo32.exe**), as shown in the figure below.</span></span>

![顯示已啟用 DMA 保護的系統資訊](images/systeminfodma.png)

<span data-ttu-id="33841-108">如果表面移除 SSD 遭到篡改，裝置就會關閉電源。</span><span class="sxs-lookup"><span data-stu-id="33841-108">If a Surface removable SSD is tampered with, the device will shutoff power.</span></span> <span data-ttu-id="33841-109">所產生的重新開機會導致 UEFI 擦除記憶體，以清除任何剩餘的資料。</span><span class="sxs-lookup"><span data-stu-id="33841-109">The resulting reboot causes UEFI to wipe memory, to erase any residual data.</span></span>
