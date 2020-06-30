---
title: Surface Pro X 應用程式相容性
description: 本文提供 Surface Pro X ARM 電腦的簡介 app 相容性資訊。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/03/2019
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: c236bf066d22cae80f4c0df39cc04450ad57a419
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831516"
---
# Surface Pro X 應用程式相容性

應用程式在 ARM 的 Windows 10 電腦（例如 Surface Pro X）上會以不同的方式執行。限制包括下列各項：

- **硬體、遊戲和應用程式的驅動程式只有專為 Windows 10 ARM 電腦所設計時才能運作**。 如需詳細資訊，請諮詢硬體製造商或開發驅動程式的組織。 驅動程式是與硬體裝置通訊的軟體程式，通常用於防毒軟體與反惡意程式碼、列印或 PDF 軟體、輔助技術、CD 和 DVD 公用程式，以及虛擬化軟體。 如果驅動程式無法運作，依賴它的應用程式或硬體將無法運作（至少不是完全）。 只有在 Windows 10 中內建群組件所依賴的驅動程式，或硬體開發人員已為裝置發行 ARM64 驅動程式時，才能使用週邊設備和裝置。
- **無法使用64位（x64）應用程式**。 您需要64位（ARM64）應用程式、32位（ARM32）應用程式，或32位（x86）應用程式。 您通常可以找到32位（x86）的應用程式版本，但某些 app 開發人員只提供64位（x64）應用程式。
- **有些遊戲無法運作**。 如果遊戲和應用程式使用的 OpenGL 版本大於1.1，或它們所依賴的是不是針對 Windows 10 ARM 電腦的「防型」驅動程式，則無法使用遊戲和 app。 請與您的遊戲發行者確認遊戲是否可正常運作。
- **自訂 Windows 體驗的 app 可能會有問題**。 這包括一些輸入法編輯器（Ime）、輔助技術及雲端儲存應用程式。 開發應用程式的組織會決定其應用程式是否可在 Windows 10 ARM 電腦上運作。
- **無法安裝某些協力廠商防毒軟體**。 您無法在 Windows 10 ARM 的電腦上安裝某些協力廠商的防毒軟體。 不過，Windows 安全性將協助您保護 Windows 10 裝置支援的存留期。
- **Windows 傳真及掃描**功能無法使用。 此功能無法在 Windows 10 ARM 電腦上使用。

如需應用程式相容性的詳細資訊，請參閱[Windows 10 ARM 電腦常見問題（FAQ](https://support.microsoft.com/en-us/help/4521606) ）
