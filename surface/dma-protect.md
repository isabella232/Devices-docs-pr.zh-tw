---
title: Surface DMA 保護
description: 本文將說明相容 Surface 裝置上的 DMA 保護
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 1/14/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.openlocfilehash: af5187a2b110804a2dff82291f1d5f912ac61a7b
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270618"
---
# Surface 裝置上的 DMA 保護

直接記憶體存取 (DMA) 保護是專門用來減輕與使用可移動 SSDs 或外部儲存裝置相關的潛在安全性漏洞。 較新的 Surface 裝置預設為啟用 DMA 保護。 其中包括 Surface Pro 7 +。 Surface Pro 7、Surface 膝上型電腦3和 Surface Pro X。 若要檢查您裝置上的 DMA 保護功能是否存在，請 (**啟動**msinfo32.exe) 中開啟 [系統資訊]  >  **** ，如下圖所示。

![顯示已啟用 DMA 保護的系統資訊](images/systeminfodma.png)

如果表面移除 SSD 遭到篡改，裝置就會關閉電源。 所產生的重新開機會導致 UEFI 擦除記憶體，以清除任何剩餘的資料。
