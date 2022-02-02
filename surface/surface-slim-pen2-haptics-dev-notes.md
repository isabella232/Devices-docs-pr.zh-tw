---
title: Surface Slim Pen 2 haptics dev Notes
description: 此頁面提供適用于想要擴充 Surface Slim 手寫筆 2 Windows 11功能的應用程式開發人員的實現注意事項。
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 12/07/2021
ms.reviewer: gusing
manager: laurawi
audience: itpro
ms.openlocfilehash: 8a3dbbdde85cfdceaf5674750a68fc21d3fcd877
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338652"
---
# <a name="surface-slim-pen-2-haptics-dev-notes"></a>Surface Slim Pen 2 haptics dev Notes

此頁面提供適用于想要擴充 Surface Slim 手寫筆 2 Windows 11功能的應用程式開發人員[的實現注意事項](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)。 可自訂的觸感功能包括下列專案：

- **模擬筆** 、鉛筆及其他書寫或繪圖工具之風格之筆墨意見回饋。
- **直接回應** 使用者動作的互動意見反應，例如將游標停留在按鈕上、按一下按鈕，或使用觸控筆完成工作。

如果您要自訂 Surface Slim 觸控筆 2 相關應用程式，請參閱觸控筆互動Windows Ink觸控筆互動和美感意見回饋中所述的[](/windows/apps/design/input/pen-haptics) Windows Ink 指導方針，然後參閱下列筆記。

## <a name="implementation-notes"></a>執行注意事項

Surface Slim 手寫筆 2 符合Windows 11筆墨規範，但下列例外：

- **互動波形。** 如 「傳送及停止互動意見 [回饋」區](/windows/apps/design/input/pen-haptics#send-and-stop-interaction-feedback)段所述，在播放書寫波形時傳送互動波形會暫時中斷書寫波形。 不過，使用目前精簡型觸控筆 2 的實現，當互動波形停止時，筆下波形可能不會繼續。 因此，如果仍然需要，在互動意見回饋之後，必須重新啟用書寫波形。 不需要等待互動意見回饋完成。
- **不支援的功能。** 如 [Haptic](/windows/apps/design/input/pen-haptics#haptic-feedback-customizations)意見回饋自訂一節所述，Surface Slim 觸控筆 2 不支援下列選擇性功能：播放次數和重播暫停間隔。 雖然這些使用方式會顯示在描述項中，但目前不受支援。 因此，下列函數會返回不正確的值：IsPlayCountSupported、IsPlayDurationSupported、IsReplayPauseIntervalSupported。

## <a name="learn-more"></a>深入了解

- [應用程式中的筆Windows Ink和Windows筆](/windows/apps/design/input/pen-and-stylus-interactions)
- [Surface Slim Pen 2 for Business](https://www.microsoft.com/d/surface-slim-pen-2-for-business/8mjc4rmvltj0?)
- [Surface 觸控筆功能與相容性](https://support.microsoft.com/surface/identify-your-surface-pen-and-features-c82a0208-2e35-b347-dae0-d7f4922edc77)

