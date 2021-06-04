---
title: 現有無線網路或區域網路上的 Miracast
description: Windows 10 可讓您經由區域網路傳送 Miracast 資料流。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 04/24/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d63b3de0f76cb70fe86fff246d82cbe166278461
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834205"
---
# 跨基礎結構的 Miracast

在 Windows 10 版本 1703 中，Microsoft 擴充了透過區域網路傳送 Miracast 串流的能力，而不是透過直接的無線連結。 這項功能是根據 [Miracast 基礎結構連接建立通訊協定 (毫秒滑鼠) ](https://msdn.microsoft.com/library/mt796768.aspx)。

Miracast 透過基礎結構提供數個優點：

- Windows 會自動偵測是否可使用此路徑傳送視訊串流。
- Windows 只會在透過乙太網路或安全的 Wi-Fi 網路連線時才選擇者個路徑。
- 使用者不必變更他們連接到 Miracast 接收器的方式。 它們與標準 Miracast 連線使用相同的 UX。
- 不需要對目前的無線驅動程式或 PC 硬體進行任何變更。
- 它與舊版未經過 Miracast 透過 Wi-FI Direct 最佳化的無限硬體可以良好的搭配。
- 它會使用現有的連接，同時降低連線時間，並提供非常穩定的串流。


##  <a name="how-it-works"></a>運作方式

使用者會嘗試透過其 Wi-fi 配接器連線到 Miracast 接收器，就像先前的一樣。 當填入 Miracast 接收器清單時，Windows 10 會辨識有能力透過基礎結構支援連接的接受器。 當使用者選取 Miracast 接收器時，Windows 10 會嘗試透過標準 DNS，以及透過多點 DNS (mDNS) 解析裝置的主機名稱。 如過任一 DNS 均無法解析名稱時，Windows 10 會改為使用標準 Wi-Fi direct 連接建立 Miracast 工作階段。

> [!NOTE]
> 如需連線協商順序的詳細資訊，請參閱在[基礎結構連線建立協定（MS-滑鼠）上的 Miracast](https://msdn.microsoft.com/library/mt796768.aspx)




##  <a name="enabling-miracast-over-infrastructure-"></a>啟用 Miracast 透過基礎結構 

如果您的 Surface Hub 或其他 Windows 10 裝置已更新至 Windows 10 版本 1703，則您自動擁有此新功能。 若要在您的環境中充分利用它，您需要下列部署中的項目為真：

- Surface Hub 或裝置 (Windows 電腦或手機) 需要執行 Windows 10 版本 1703。
- 開啟 TCP 埠： **7250**。
- Surface Hub 或 Windows 電腦可以做為 Miracast 透過基礎結構的*接收器*。 Windows 電腦或手機可以做為 Miracast 透過基礎結構的*來源*。
    - 做為 Miracast 接收器，Surface Hub 或裝置必須透過乙太網路或安全的 Wi-Fi 連接 (例如使用 WPA2-PSK 或 WPA2-企業安全性) 連線至您的企業網路。 如果 Surface Hub 或裝置連線到開啟的 Wi-fi 連線，則跨基礎結構的 Miracast 功能將會自行停用。
    - 做為 Miracast 來源，Windows 電腦或手機必須透過乙太網路或安全的 Wi-Fi 連接連線至相同的企業網路。
- Surface Hub 或裝置的 DNS 主機名稱（裝置名稱）必須能夠透過您的 DNS 伺服器解析。 達到此目的的方法不是透過動態 DNS 讓您的 Surface Hub 自動登錄，就是以手動方式建立 Surface Hub 主機名稱的 A 或 AAAA 記錄。 
- Windows 10 電腦上必須透過乙太網路或安全的 Wi-Fi 連接連線至相同的企業網路。 
-   在 Windows 10 電腦上，在 [系統設定] 中必須啟用 [**投影到此電腦**] 功能，而且裝置必須啟用 wi-fi 介面，才能回應僅透過 wi-fi 配接器進行的探索要求。


請務必注意，Miracast 透過基礎結構無法取代標準 Miracast。 其反而是功能的補充，並提供優勢給屬於企業網路的一部分的使用者。 在特定位置之身分為來賓，且無法存取企業網路的使用者會繼續使用 Wi-Fi Direct 連線方式來連線。

在 ([SurfaceHub 設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp)) 中的 **InBoxApps/WirelessProjection/PinRequired** 設定並不需要用於 Miracast 透過基礎結構。 這是因為 Miracast 透過基礎結構只能在裝置連接到相同企業網路時運作。 這會移除 Miracast 先前遺漏的安全性限制。 我們建議您繼續使用此設定 (如果您之前曾經使用)，不然的話 Miracast 會改為使用一般的 Miracast (如果基礎結構連線未運作)。 

##  <a name="faq"></a>常見問題集
**為什麼仍需要使用 Wi-fi 才能透過基礎結構使用 Miracast？**<br>
識別 Miracast 接收器的探索要求只能透過 Wi-fi 配接器來進行。 當接收器已確定之後，Windows 10 就可以嘗試連線到網路。
