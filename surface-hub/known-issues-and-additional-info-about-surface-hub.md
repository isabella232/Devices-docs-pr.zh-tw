---
title: Microsoft Surface Hub 已知問題及其他相關資訊
description: 概述 Microsoft Surface Hub 的已知問題。
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: surface、hub、問題
ms.prod: surface-hub
ms.sitesec: library
author: todmccoy
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ec6746098203b5e91e2aaf3b044d21b81c31c897
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831482"
---
# Microsoft Surface Hub 已知問題及其他相關資訊

我們正在聆聽。 [品質] 是頭等大事，我們想要讓您知道有哪些問題會影響客戶。 下列是 Microsoft Surface Hub 的一些已知問題：

- **商務用 Skype 沒有與 RS2 使用 proxy 來進行媒體流量**
<br/>對於位於 proxy 之後的某些 Surface Hub 使用者，商務用 Skype 不會使用 proxy 伺服器來執行媒體。 不過，Surface Hub 將能夠登入帳戶。 我們收到您的意見反應，而且您在使用 proxy 時會發現媒體流量問題。 我們正在積極調查這個問題，一旦發現並測試解決方案，就會立即發行修正程式。 

- **針對 AAD 加入的裝置，當使用者嘗試登入「我的會議 & 檔案」時，Surface Hub 會報告沒有網際網路連線**
<br/>我們已注意到一組影響 Surface Hub 上的登入和檔存取的問題。 我們正在積極調查這些問題。 如有解決方法，客戶可以重設裝置，並將其中樞設定為使用本機管理員帳戶。 重新配置為使用本機管理員帳戶之後，「我的會議與檔案」就會如期運作。
- **Azure AD 加入時的單一登入**
<br/>Surface Hub 是專為公用空格設計的，會影響使用者認證的儲存方式。 因此，目前在裝置加入 Azure AD 時，單一登入的運作方式目前有一些限制。 Microsoft 已注意到這項限制，且正在積極調查解析度的選項。
- **如果 Surface Hub 在易記名稱中有點字元（.），則可在基礎結構投影上使用 Miracast**
<br/>如果易記的名稱在名稱（.）中包含句號或點（例如，"Room42"），Surface Hub 使用者可能會遇到投影裝置的問題。 若要解決此問題，請在 [**設定**Surface Hub] 中變更中樞的易記名稱  >  **Surface Hub**  >  ** **，然後重新開機裝置。 Microsoft 正在努力解決這個問題。