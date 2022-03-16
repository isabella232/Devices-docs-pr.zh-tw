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
ms.date: 12/01/2021
ms.reviewer: carlol
manager: laurawi
audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: a0f04b4dd089309ad44cab12cf738d8203d1526d
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449496"
---
# <a name="dma-protection-on-surface-devices"></a>Surface 裝置上的 DMA 保護

直接記憶體存取 (DMA) 保護是專為降低使用可移除的 SSD 或外部儲存裝置相關的潛在安全性漏洞所設計。 較新的 Surface 裝置預設會啟用 DMA 保護。 這些包括 Surface Pro 8、Surface Laptop Studio、Surface Go 3、Surface Laptop SE、Surface Pro 7+、Surface Pro 7、Surface Laptop 3 和 Surface Pro X。 若要檢查裝置上是否存在 DMA ****  >  保護功能，請開啟 系統資訊 (開始msinfo32.exe **) ** ，如下圖所示。

![系統資訊顯示已啟用 DMA 保護。](images/systeminfodma.png)

如果 Surface 可移除的 SSD 遭到竄改，裝置會關閉電源。 產生的重新開機會導致 UEFI 抹除記憶體，以清除任何剩餘資料。
