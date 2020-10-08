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
ms.date: 10/01/2020
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 40aa2a89c3f3c4371d2a6ecaeb8d2769e5b420f7
ms.sourcegitcommit: e0047f07c42b1e3cbd074b66a4704ea72e9d7bae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/02/2020
ms.locfileid: "11093913"
---
# Surface Pro X 應用程式相容性



 ![電腦使用者的影像](images/4527790_en_4.png)<br><br>



Windows 10 ARM 電腦可協助您隨時隨地繼續運作。 以下是一些主要優點：

- **永遠連線至網際網路。** 透過行動資料連線，無論您身在何處，您都可以在線上取得行動電話信號。 當您在公司、家用或其他您信任的 Wi-fi 網路時，您可以連線到 Wi-fi 來儲存行動資料並繼續運作。

- **電池使用時間超過全天。**  您使用的功耗少於其他電腦，因此您可以在一般的工作或學校中使用，而不需用完電池，或擔心找出要插入的插座。 如果您想要使用電腦來尋找更多有趣的東西，您可以在電腦上播放儲存在您電腦上的影片，但不需要在您的電池之間充電。

- **立即開啟。** 當您不是使用您的電腦時，只要按下電源按鈕，就像您在行動電話上關閉螢幕。 當您取出電腦並將它重新開啟時，它會立即開啟。 每當您在課程、會議或其他活動之間有幾分鐘的時間，您就可以在不等待您的電腦啟動的情況下完成工作。

請注意，應用程式在 ARM 的 Windows 10 電腦（例如 Surface Pro X）上會以不同的方式執行。限制包括下列各項：

- **硬體、遊戲和應用程式的驅動程式只有專為 Windows 10 ARM 電腦所設計時才能運作**。 如需詳細資訊，請諮詢硬體製造商或開發驅動程式的組織。 驅動程式是與硬體裝置通訊的軟體程式，通常用於防毒軟體與反惡意程式碼、列印或 PDF 軟體、輔助技術、CD 和 DVD 公用程式，以及虛擬化軟體。 如果驅動程式無法運作，依賴它的應用程式或硬體將無法正常運作， (至少無法完全) 。 只有在 Windows 10 中內建群組件所依賴的驅動程式，或硬體開發人員已為裝置發行 ARM64 驅動程式時，才能使用週邊設備和裝置。
- **64 位 (x64) app**。 透過 Windows 測試人員計畫立即在預覽中使用64位模擬，您就可以在 Surface Pro X 上執行64位 (x64) app。在沒有64位模擬支援的情況下，您64可以使用 x86 模擬器 (， (ARM64) app、32位 (ARM32) 應用程式，或32位) x86 (app。 您通常可以找出 32 (x86) 應用程式版本，但某些 app 開發人員只提供64位 (x64) app。
- **有些遊戲無法運作**。 如果遊戲和應用程式使用的 OpenGL 版本大於1.1，或它們所依賴的是不是針對 Windows 10 ARM 電腦的「防型」驅動程式，則無法使用遊戲和 app。 請與您的遊戲發行者確認遊戲是否可正常運作。
- **自訂 Windows 體驗的 app 可能會有問題**。 這包括一些輸入法編輯器 (Ime) 、輔助技術及雲端儲存應用程式。 開發應用程式的組織會決定其應用程式是否可在 Windows 10 ARM 電腦上運作。
- **無法安裝某些協力廠商防毒軟體**。 您無法在 Windows 10 ARM 的電腦上安裝某些協力廠商的防毒軟體。 不過，Windows 安全性將協助您保護 Windows 10 裝置支援的存留期。
- **Windows 傳真及掃描**功能無法使用。 此功能無法在 Windows 10 ARM 電腦上使用。

## App 保證

Microsoft 致力於確保客戶在 ARM64 裝置上（例如 Surface Pro X）上的 Windows 10 具有良好的相容性體驗。我們已拓展應用程式，讓工程師能透過提供疑難排解並提供應用程式 remediations，來支援遇到應用程式相容性問題的客戶，無需額外費用。 您可以在 ARM64 上以 Windows 10 為目標，為您的 LOB、ISV 及 Microsoft 第一方 EDU 客戶供應商業及客戶的服務。 

如需應用程式相容性的詳細資訊，請參閱 [Windows 10 ARM 電腦版常見問題](https://support.microsoft.com/en-us/help/4521606)。
