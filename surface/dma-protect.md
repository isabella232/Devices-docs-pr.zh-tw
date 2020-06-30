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
# Surface 裝置上的 DMA 保護

[直接記憶體存取（DMA）] 保護旨在減少與使用可移動 SSDs 或外部儲存裝置相關的潛在安全性漏洞。 較新的 Surface 裝置預設為啟用 DMA 保護。 這些包括 Surface Pro 7、Surface 膝上型3和 Surface Pro X。 若要檢查您裝置上的 DMA 保護功能是否存在，請開啟 [系統資訊] （**啟動**  >  **msinfo32.exe**），如下圖所示。

![顯示已啟用 DMA 保護的系統資訊](images/systeminfodma.png)

如果表面移除 SSD 遭到篡改，裝置就會關閉電源。 所產生的重新開機會導致 UEFI 擦除記憶體，以清除任何剩餘的資料。
