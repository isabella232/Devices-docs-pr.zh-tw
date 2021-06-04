---
title: Surface Hub 如何處理 Wi-Fi Direct 的安全性問題
description: Wi-fi 直接安全風險的相關指導方針。
keywords: 變更歷程記錄
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/27/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: d877d9b6a4e330a74a9d79cf1150487d89c0da23
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831374"
---
# Surface Hub 如何處理 Wi-Fi Direct 的安全性問題

Microsoft Surface Hub 是一種多合一的生產力裝置，可讓團隊更輕鬆地進行腦力激盪、共同作業並分享想法。 Surface Hub 是透過 Wi-fi Direct，依靠 Miracast 進行無線投影。

本文將說明 Wi-fi Direct 安全性漏洞，以及 Surface Hub 如何解決這些風險，以及系統管理員可以如何針對最高的安全性設定 Surface Hub。 這項資訊將協助具備高安全性需求的客戶，保護其 Surface Hub 連接的網路和傳輸中的資料。

本文章的預期物件是，也就是想要在公司環境中使用最佳安全性設定來部署 Surface Hub 的 IT 和網路系統管理員。

##  <a name="overview"></a>概觀

Surface Hub 的安全性廣泛地在 Wi-fi Direct/Miracast 以及相關聯的802.11、Wi-fi 保護存取（WPA2）及無線保護設定（WPS）標準上。 因為裝置只支援 WPS （而不是 WPA2 預共用金鑰 [PSK] 或 WPA2 Enterprise），所以通常會簡化與802.11 加密相關的問題。

Surface Hub 與 Miracast 接收器的欄位在 par 上運作。 因此，它容易受到與所有以 WPS 為基礎的無線網路裝置類似的入侵集合。 但內建其他預防措施的是 WPS Surface Hub 實現。 此外，它的內部架構可協助防止已將 Wi-fi Direct/Miracast 層的攻擊者移到其他攻擊表面，以及已連線的商業網路。

##  <a name="wi-fi-direct-background"></a>Wi-Fi Direct 背景

Miracast 是 wi-fi [顯示標準] 的一部分，它受 Wi-fi Direct 通訊協定支援。 現代行動裝置的畫面分享以及共同作業功能支援這些標準。

Wi-fi Direct 或 Wi-fi "對等" （P2P）是「Ad Hoc」網路的 Wi-fi 聯盟的標準。 支援的裝置可以直接通訊，並在沒有一般 Wi-fi 存取點或網際網路連線的情況下建立網路群組。

Wi-fi Direct 的安全性是由 WPA2 在 WPS 標準下提供的。 裝置的驗證機制可以是數位 pin （WPS）、物理或虛擬推入按鈕（WPS-PBC），或在近距離欄位通訊（WPS-OOO）中的外訊息。 Surface Hub 支援引腳方法和按鈕方法，這是預設值。

在 Wi-fi Direct 中，會建立下列其中一種類型的群組：
- *Persistent*，在此情況下，會使用儲存的金鑰資料自動重新連接
- *暫時*，裝置無法在不使用使用者動作的情況下重新進行驗證

Wi-fi Direct 群組會透過協商通訊協定來決定*群組擁有*者（GO），這會模仿已建立的 wi-fi Direct 群組的「工作站」或「存取點」功能。 Wi-fi Direct GO 提供驗證（透過「內部註冊機構」），並協助上游網路連線。 針對 Surface Hub，不會發生這種轉協商。 網路只會以「自治」模式運作，而 Surface Hub 則永遠是群組擁有者。 最後，Surface Hub 本身不會以用戶端的身分加入其他 Wi-fi Direct 網路。

##  <a name="how-surface-hub-addresses-wi-fi-direct-vulnerabilities"></a>Surface Hub 如何解決 Wi-fi 直接漏洞

**Wi-fi Direct 邀請、廣播和探索流程中的漏洞與攻擊：** Wi-fi Direct/Miracast 攻擊可能會以群組建立、對等搜尋、裝置廣播或邀請程式中的弱點為目標。

|Wi-fi Direct 漏洞 | Surface Hub 緩解 |
| --- | --- |
| 探索程式在一段時間內可能會保持使用中，這樣就可以在不核准裝置擁有者的情況下，建立邀請和連線。 | Surface Hub 只會以群組擁有者的身分運作，不會執行用戶端探索或前往協商處理常式。 您可以完全停用無線投影來關閉廣播。 |
| 透過 PBC 的邀請和探索可讓未經驗證的攻擊者執行重複的連線嘗試，或自動接受未驗證的連線。 | 依需要使用 WPS PIN 安全性，管理員可以降低此類未經授權連線或「邀請 bombs」的可能性，直到使用者誤接受邀請時，才會重複傳送邀請。 |

**Wi-fi 受保護設定（WPS）按鈕連接（PBC）與 PIN 輸入：** 已在 WPS PIN 方法設計與實現中示範公開的弱點。 WPS-PBC 有其他漏洞，可以針對專為一次性使用的通訊協定允許活動攻擊。

| Wi-fi Direct 漏洞 | Surface Hub 緩解 |
| --- | --- |
| WPS-PBC 很容易受到主動式攻擊。 WPS 規格聲明： "PBC 方法具有零的熵位數，只針對被動竊聽攻擊提供保護。 PBC 保護竊聽攻擊，並且避免裝置加入未經過擁有者選取的網路。 不過，如果沒有驗證，就表示 PBC 無法防範作用中的攻擊。」 攻擊者可以使用選擇性的無線擁塞或其他拒絕服務技術來觸發非預期的 Wi-fi 直向或連線。 此外，只擁有實體鄰近性的作用中攻擊者也會重複地拉下任何 Wi-fi Direct 群組，並嘗試攻擊，直到成功為止。 | 在 Surface Hub 設定中啟用 WPS PIN 安全性。 Wi-fi WPS 規格指出：「只有沒有支援 PIN 能力的註冊機構，且 WLAN 使用者願意接受與 PBC 相關聯的風險時，才能使用 PBC 方法。」 |
| WPS-PIN 實現可能受到強力攻擊，其目標是 WPS 標準中的漏洞。 在一系列 Wi-fi 硬體製造商的過去幾年中，將分割 PIN 驗證導向到多個實施漏洞的設計。 在2011中，研究人員寫照 Viehböck 和 Craig Heffner 發佈有關此漏洞的資訊，以及「Reaver」等工具（如「」）作為概念驗證。 |   Surface Hub 中的 Microsoft 實現 WPS 每30秒變更一次 PIN。 若要破解 PIN，攻擊者必須在30秒以內完成整個利用方式。 考慮到此區域中的工具和研究的目前狀態，透過 WPS 進行暴力式 PIN 破解的攻擊不大可能會成功。 |
| 由於弱初始金鑰（E-S1、E S2）熵，因此可透過離線攻擊來破解 WPS PIN。 在2014中，Dominique Bongard 描述的是「Pixie 灰塵」攻擊，在無線裝置中的偽亂數字發生器（PRNG）中初始隨機性不佳，就表示您允許離線暴力攻擊。 | Surface Hub 中的 Microsoft WPS 實現不容易受到此離線 PIN 強力攻擊。 每次連線都會隨機產生 WPS-PIN。 |

**網路服務的意外暴露：** 針對乙太網或 WLAN 服務而設計的網路守護程式可能會因為配置錯誤（例如系結到 "all"/0.0.0.0 介面）而意外公開。 其他可能的原因包括設定不當的裝置防火牆或防火牆規則遺失。

| Wi-fi Direct 漏洞 | Surface Hub 緩解 |
| --- | --- |
| 錯誤設定會將安全性漏洞或未經驗證的網路服務聯繫到「所有」的介面，其中也包括 Wi-Fi Direct 介面。 這會公開無法存取 Wi-fi Direct 用戶端的服務，這可能是弱或自動驗證的。 | 在 Surface Hub 中，預設的防火牆規則只允許所需的 TCP 和 UDP 網路埠，而且預設會拒絕所有輸入連線。 透過啟用 WPS PIN 模式來設定加強驗證。|

**橋接 Wi-fi Direct 及其他有線或無線網路：** WLAN 或乙太網路間的網路橋接會違反 Wi-fi Direct 規格。 這類橋接器或錯誤配置可能會有效地降低或移除內部公司網路的無線存取控制。

| Wi-fi Direct 漏洞 | Surface Hub 緩解 |
| --- | --- |
| Wi-Fi Direct 裝置可能會允許至橋接網路連線未經驗證或不良驗證的存取。 這可能允許 Wi-fi Direct 網路將流量路由到內部乙太局域網或其他基礎結構，或是違反現有 IT 安全協定的企業 WLAN 網路。 | Surface Hub 無法設定為橋接無線介面，或允許在不同的網路之間路由。 預設韌體規則可有效加強防禦，避免這類路由或橋接連線。 |

**使用 Wi-fi Direct 「舊版」模式：** 當您在「舊版」模式下運作時，可能會發生不預期的網路或裝置。 如果未啟用 WPS-PIN，可能會發生裝置詐騙或非預期的連線。

| Wi-fi Direct 漏洞 | Surface Hub 緩解 |
| --- | --- |
| 藉由支援 Wi-Fi Direct 與 802.11 的基礎結構用戶端，系統會以「傳統」支援模式執行作業。 這可能會無限期地公開連線設定階段，允許加入群組或受邀的裝置在預定設定階段結束後進行連接。 |    Surface Hub 不支援 Wi-fi Direct 舊版用戶端。 即便是啟用 WPS-PIN 模式，也只有 Wi-Fi Direct 可以連線到連接到 Surface Hub 。 |

**連線設定期間的 Wi-fi Direct 中轉協商：** Wi-fi Direct 中的群組擁有者類似傳統802.11 無線網路中的「存取點」。 惡意的裝置可以操弄交涉過程。

|Wi-fi Direct 漏洞 |   Surface Hub 緩解 |
| --- | --- |
| 如果群組是動態建立的，或能讓 Wi-fi Direct 裝置加入新的群組，則您可以將群組擁有者協商贏由一個惡意的裝置，此裝置永遠會指定最大群組擁有者 "用途" 值15。 （但是，如果裝置設定為永遠成為群組擁有者，則連接會失敗。）  | Surface Hub 充分運用 Wi-fi Direct "自治模式"，這會跳過連線設定的 [前往協商] 階段。 而且 Surface Hub 永遠是群組擁有者。 |

**非預期或惡意的 wi-fi deauthentication：** Wi-fi deauthentication 是一種舊的攻擊，在此攻擊中，本機攻擊者可以在連線設定程式中加速資訊洩漏、觸發新的四路握手、目標 Wi-fi Direct WPS-PBC 以取得作用中的攻擊，或建立拒絕服務攻擊。

| Wi-fi Direct 漏洞 | Surface Hub 緩解 |
| --- | --- |
| 未經授權的攻擊者可以傳送 Deauthentication 資料包，讓站重新進行驗證，然後嗅探產生的握手。 在所引發的信號交換中就可以嘗試進行密碼編譯或暴力攻擊。 針對這些攻擊的緩解措施包括針對預共用金鑰強制執行長度與複雜性原則、設定存取點（如果適用）來偵測 deauthentication 資料包的惡意等級，以及使用 WPS 自動產生強金鑰。 在 PBC 模式中，使用者會與物理或虛擬按鈕互動，以允許隨意裝置關聯。 這個程式只會在設定期間在短視窗中發生。 按鈕自動 [推入] 後，裝置將會接受任何透過規範 PIN 值（全是零）相關聯的站。 解除認證可強制執行反覆的安裝程序。 |   Surface Hub 在釘選或 PBC 模式中使用 WPS。 不允許 PSK 配置。 這個方法可協助強制產生強金鑰。 最好為 Surface Hub 啟用 WPS PIN 安全性。 |
| 除了拒絕服務攻擊之外，您還可以使用 deauthentication 資料包來觸發重新連線，以針對 WPS-PBC 再次開啟活動攻擊的機會。 |   在 Surface Hub 設定中啟用 WPS PIN 安全性。 |

**基本無線資訊披露：** 無線網路、802.11 或其他方式本身就是資訊洩露的危險。 雖然此資訊大多是連線或裝置中繼資料，但此問題仍是任何802.11 網路系統管理員的已知風險。 透過 WPS-PIN 的 Wi-Fi Direct 裝置驗證，能有效揭露與 PSK 或企業 802.11 網路的相同資訊。

| Wi-fi Direct 漏洞 | Surface Hub 緩解 |
| --- | --- |
| 在廣播、連線設定或甚至是已加密連線的一般操作中，裝置和資料包大小的基本資訊會以無線方式傳送。 在基本階層，位於無線範圍內的本機攻擊者可以檢查相關的802.11 資訊元素，以判斷無線裝置的名稱、通訊設備的 MAC 位址，以及可能的其他詳細資料，例如無線堆疊版本、資料包大小，或已設定的存取點或群組擁有者選項。  | Surface Hub 使用的 Wi-fi Direct 網路無法進一步保護中繼資料洩漏，就像 802.11 Enterprise 或 PSK 無線網路一樣。 物理安全性以及移除無線鄰近性的潛在威脅可協助減少潛在的資訊洩漏。 |

**無線的惡意攻擊或哄騙攻擊：** 哄騙無線名稱是一種簡單且眾所周知的漏洞，本機攻擊者可利用此漏洞引誘不知情或誤認為使用者連接。

| Wi-fi Direct 漏洞 | Surface Hub 緩解 |
| --- | --- |
| 攻擊者可透過電子欺騙或仿製目標網路的無線名稱或「SSID」來誘讓使用者連接到虛假的惡意網路。 透過支援無人驗證的自動加入 Miracast，攻擊者可以捕獲所需的顯示資料，或在連線裝置上啟動網路攻擊。 | 在無法加入欺騙 Surface Hub 的情況下，此漏洞會以兩種方式部分緩解。 首先，任何可能的攻擊必須要在實際的 Wi-Fi 範圍內。 其次，此攻擊只能在第一次連線期間進行。 後續連線會使用永久性 Wi-fi Direct 群組，而且在未來的中樞使用期間，Windows 將會記住並優先處理這個先前的連接。 （注意：不考慮在此報告中假冒 MAC 位址、Wi-fi 通道及 SSID，可能會造成不一致的 Wi-fi 行為。）總的來說，對於缺少企業版 WPA2 通訊協定的任何802.11 無線網路（例如 EAP-TLS 或 EAP-PWD，不支援哪些 Wi-fi），這個缺點是一個基本問題。 |

##  <a name="surface-hub-hardening-guidelines"></a>Surface Hub 強化指導方針

Surface Hub 可協助共同作業，並讓使用者快速並有效率地開始或加入會議。 Surface Hub 的預設 Wi-fi Direct 設定已針對此案例進行優化。

如需其他無線介面安全性，Surface Hub 使用者應該啟用 WPS PIN 安全性設定。 此設定會停用 WPS PBC 模式並提供用戶端驗證。 它可防止未經授權的介面連接至 Surface Hub，提供最強的保護層級。

如果您仍然擔心 Surface Hub 的驗證與授權，我們建議您將裝置連線到另一個網路。 您可以使用 Wi-fi （例如「來賓」 Wi-fi 網路）或個別的乙太網路，最好是完全不同的物理網路。 但 VLAN 也可以提供額外的安全性。 當然，此方法可能會排除與內部網路資源或服務的連線，而且可能需要額外的網路設定才能重新取得存取。

其他建議︰
- [安裝定期系統更新](manage-windows-updates-for-surface-hub.md) 
- 更新 Miracast 設定以停用自動認可模式

##  <a name="learn-more"></a>深入了解

- [Wi-Fi Direct 規格](http://www.wi-fi.org/discover-wi-fi/wi-fi-direct)
- [無線保護設定 (WPS) 規格](http://www.wi-fi.org/discover-wi-fi/wi-fi-protected-setup)



