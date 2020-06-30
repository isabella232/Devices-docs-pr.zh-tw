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
# <span data-ttu-id="bed22-103">跨基礎結構的 Miracast</span><span class="sxs-lookup"><span data-stu-id="bed22-103">Miracast over infrastructure</span></span>

<span data-ttu-id="bed22-104">在 Windows 10 版本 1703 中，Microsoft 擴充了透過區域網路傳送 Miracast 串流的能力，而不是透過直接的無線連結。</span><span class="sxs-lookup"><span data-stu-id="bed22-104">In the Windows 10, version 1703, Microsoft has extended the ability to send a Miracast stream over a local network rather than over a direct wireless link.</span></span> <span data-ttu-id="bed22-105">這項功能是根據 [Miracast 基礎結構連接建立通訊協定 (毫秒滑鼠) ](https://msdn.microsoft.com/library/mt796768.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bed22-105">This functionality is based on the [Miracast over Infrastructure Connection Establishment Protocol (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx).</span></span>

<span data-ttu-id="bed22-106">Miracast 透過基礎結構提供數個優點：</span><span class="sxs-lookup"><span data-stu-id="bed22-106">Miracast over Infrastructure offers a number of benefits:</span></span>

- <span data-ttu-id="bed22-107">Windows 會自動偵測是否可使用此路徑傳送視訊串流。</span><span class="sxs-lookup"><span data-stu-id="bed22-107">Windows automatically detects when sending the video stream over this path is applicable.</span></span>
- <span data-ttu-id="bed22-108">Windows 只會在透過乙太網路或安全的 Wi-Fi 網路連線時才選擇者個路徑。</span><span class="sxs-lookup"><span data-stu-id="bed22-108">Windows will only choose this route if the connection is over Ethernet or a secure Wi-Fi network.</span></span>
- <span data-ttu-id="bed22-109">使用者不必變更他們連接到 Miracast 接收器的方式。</span><span class="sxs-lookup"><span data-stu-id="bed22-109">Users do not have to change how they connect to a Miracast receiver.</span></span> <span data-ttu-id="bed22-110">它們與標準 Miracast 連線使用相同的 UX。</span><span class="sxs-lookup"><span data-stu-id="bed22-110">They use the same UX as for standard Miracast connections.</span></span>
- <span data-ttu-id="bed22-111">不需要對目前的無線驅動程式或 PC 硬體進行任何變更。</span><span class="sxs-lookup"><span data-stu-id="bed22-111">No changes to current wireless drivers or PC hardware are required.</span></span>
- <span data-ttu-id="bed22-112">它與舊版未經過 Miracast 透過 Wi-FI Direct 最佳化的無限硬體可以良好的搭配。</span><span class="sxs-lookup"><span data-stu-id="bed22-112">It works well with older wireless hardware that is not optimized for Miracast over Wi-Fi Direct.</span></span>
- <span data-ttu-id="bed22-113">它會使用現有的連接，同時降低連線時間，並提供非常穩定的串流。</span><span class="sxs-lookup"><span data-stu-id="bed22-113">It leverages an existing connection which both reduces the time to connect and provides a very stable stream.</span></span>


## <span data-ttu-id="bed22-114">運作方式</span><span class="sxs-lookup"><span data-stu-id="bed22-114">How it works</span></span>

<span data-ttu-id="bed22-115">使用者會嘗試透過其 Wi-fi 配接器連線到 Miracast 接收器，就像先前的一樣。</span><span class="sxs-lookup"><span data-stu-id="bed22-115">Users attempt to connect to a Miracast receiver through their Wi-Fi adapter as they did previously.</span></span> <span data-ttu-id="bed22-116">當填入 Miracast 接收器清單時，Windows 10 會辨識有能力透過基礎結構支援連接的接受器。</span><span class="sxs-lookup"><span data-stu-id="bed22-116">When the list of Miracast receivers is populated, Windows 10 will identify that the receiver is capable of supporting a connection over the infrastructure.</span></span> <span data-ttu-id="bed22-117">當使用者選取 Miracast 接收器時，Windows 10 會嘗試透過標準 DNS，以及透過多點 DNS (mDNS) 解析裝置的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="bed22-117">When the user selects a Miracast receiver, Windows 10 will attempt to resolve the device's hostname via standard DNS, as well as via multicast DNS (mDNS).</span></span> <span data-ttu-id="bed22-118">如過任一 DNS 均無法解析名稱時，Windows 10 會改為使用標準 Wi-Fi direct 連接建立 Miracast 工作階段。</span><span class="sxs-lookup"><span data-stu-id="bed22-118">If the name is not resolvable via either DNS method, Windows 10 will fall back to establishing the Miracast session using the standard Wi-Fi direct connection.</span></span>

> [!NOTE]
> <span data-ttu-id="bed22-119">如需連線協商順序的詳細資訊，請參閱在[基礎結構連線建立協定（MS-滑鼠）上的 Miracast](https://msdn.microsoft.com/library/mt796768.aspx)</span><span class="sxs-lookup"><span data-stu-id="bed22-119">For more information on the connection negotiation sequence, see [Miracast over Infrastructure Connection Establishment Protocol (MS-MICE)](https://msdn.microsoft.com/library/mt796768.aspx)</span></span>




## <span data-ttu-id="bed22-120">啟用 Miracast 透過基礎結構</span><span class="sxs-lookup"><span data-stu-id="bed22-120">Enabling Miracast over Infrastructure</span></span> 

<span data-ttu-id="bed22-121">如果您的 Surface Hub 或其他 Windows 10 裝置已更新至 Windows 10 版本 1703，則您自動擁有此新功能。</span><span class="sxs-lookup"><span data-stu-id="bed22-121">If you have a Surface Hub or other Windows 10 device that has been updated to Windows 10, version 1703, then you automatically have this new feature.</span></span> <span data-ttu-id="bed22-122">若要在您的環境中充分利用它，您需要下列部署中的項目為真：</span><span class="sxs-lookup"><span data-stu-id="bed22-122">To take advantage of it in your environment, you need to ensure the following is true within your deployment:</span></span>

- <span data-ttu-id="bed22-123">Surface Hub 或裝置 (Windows 電腦或手機) 需要執行 Windows 10 版本 1703。</span><span class="sxs-lookup"><span data-stu-id="bed22-123">The Surface Hub or device (Windows PC or phone) needs to be running Windows 10, version 1703.</span></span>
- <span data-ttu-id="bed22-124">開啟 TCP 埠： **7250**。</span><span class="sxs-lookup"><span data-stu-id="bed22-124">Open TCP port: **7250**.</span></span>
- <span data-ttu-id="bed22-125">Surface Hub 或 Windows 電腦可以做為 Miracast 透過基礎結構的*接收器*。</span><span class="sxs-lookup"><span data-stu-id="bed22-125">A Surface Hub or Windows PC can act as a Miracast over Infrastructure *receiver*.</span></span> <span data-ttu-id="bed22-126">Windows 電腦或手機可以做為 Miracast 透過基礎結構的*來源*。</span><span class="sxs-lookup"><span data-stu-id="bed22-126">A Windows PC or phone can act as a Miracast over Infrastructure *source*.</span></span>
    - <span data-ttu-id="bed22-127">做為 Miracast 接收器，Surface Hub 或裝置必須透過乙太網路或安全的 Wi-Fi 連接 (例如使用 WPA2-PSK 或 WPA2-企業安全性) 連線至您的企業網路。</span><span class="sxs-lookup"><span data-stu-id="bed22-127">As a Miracast receiver, the Surface Hub or device must be connected to your enterprise network via either Ethernet or a secure Wi-Fi connection (e.g. using either WPA2-PSK or WPA2-Enterprise security).</span></span> <span data-ttu-id="bed22-128">如果 Surface Hub 或裝置連線到開啟的 Wi-fi 連線，則跨基礎結構的 Miracast 功能將會自行停用。</span><span class="sxs-lookup"><span data-stu-id="bed22-128">If the Surface Hub or device is connected to an open Wi-Fi connection, Miracast over Infrastructure will disable itself.</span></span>
    - <span data-ttu-id="bed22-129">做為 Miracast 來源，Windows 電腦或手機必須透過乙太網路或安全的 Wi-Fi 連接連線至相同的企業網路。</span><span class="sxs-lookup"><span data-stu-id="bed22-129">As a Miracast source, the Windows PC or phone must be connected to the same enterprise network via Ethernet or a secure Wi-Fi connection.</span></span>
- <span data-ttu-id="bed22-130">Surface Hub 或裝置的 DNS 主機名稱（裝置名稱）必須能夠透過您的 DNS 伺服器解析。</span><span class="sxs-lookup"><span data-stu-id="bed22-130">The DNS Hostname (device name) of the Surface Hub or device needs to be resolvable via your DNS servers.</span></span> <span data-ttu-id="bed22-131">達到此目的的方法不是透過動態 DNS 讓您的 Surface Hub 自動登錄，就是以手動方式建立 Surface Hub 主機名稱的 A 或 AAAA 記錄。</span><span class="sxs-lookup"><span data-stu-id="bed22-131">You can achieve this by either allowing your Surface Hub to register automatically via Dynamic DNS, or by manually creating an A or AAAA record for the Surface Hub's hostname.</span></span> 
- <span data-ttu-id="bed22-132">Windows 10 電腦上必須透過乙太網路或安全的 Wi-Fi 連接連線至相同的企業網路。</span><span class="sxs-lookup"><span data-stu-id="bed22-132">Windows 10 PCs must be connected to the same enterprise network via Ethernet or a secure Wi-Fi connection.</span></span> 
-   <span data-ttu-id="bed22-133">在 Windows 10 電腦上，在 [系統設定] 中必須啟用 [**投影到此電腦**] 功能，而且裝置必須啟用 wi-fi 介面，才能回應僅透過 wi-fi 配接器進行的探索要求。</span><span class="sxs-lookup"><span data-stu-id="bed22-133">On Windows 10 PCs, the **Projecting to this PC** feature must be enabled in System Settings, and the device must have a Wi-Fi interface enabled in order to respond to discovery requests that only occur through the Wi-Fi adapter.</span></span>


<span data-ttu-id="bed22-134">請務必注意，Miracast 透過基礎結構無法取代標準 Miracast。</span><span class="sxs-lookup"><span data-stu-id="bed22-134">It is important to note that Miracast over Infrastructure is not a replacement for standard Miracast.</span></span> <span data-ttu-id="bed22-135">其反而是功能的補充，並提供優勢給屬於企業網路的一部分的使用者。</span><span class="sxs-lookup"><span data-stu-id="bed22-135">Instead, the functionality is complementary, and provides an advantage to users who are part of the enterprise network.</span></span> <span data-ttu-id="bed22-136">在特定位置之身分為來賓，且無法存取企業網路的使用者會繼續使用 Wi-Fi Direct 連線方式來連線。</span><span class="sxs-lookup"><span data-stu-id="bed22-136">Users who are guests to a particular location and don’t have access to the enterprise network will continue to connect using the Wi-Fi Direct connection method.</span></span>

<span data-ttu-id="bed22-137">在 ([SurfaceHub 設定服務提供者 (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp)) 中的 **InBoxApps/WirelessProjection/PinRequired** 設定並不需要用於 Miracast 透過基礎結構。</span><span class="sxs-lookup"><span data-stu-id="bed22-137">The **InBoxApps/WirelessProjection/PinRequired** setting in the [SurfaceHub configuration service provider (CSP)](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/surfacehub-csp) is not required for Miracast over Infrastructure.</span></span> <span data-ttu-id="bed22-138">這是因為 Miracast 透過基礎結構只能在裝置連接到相同企業網路時運作。</span><span class="sxs-lookup"><span data-stu-id="bed22-138">This is because Miracast over Infrastructure only works when both devices are connected to the same enterprise network.</span></span> <span data-ttu-id="bed22-139">這會移除 Miracast 先前遺漏的安全性限制。</span><span class="sxs-lookup"><span data-stu-id="bed22-139">This removes the security restriction that was previously missing from Miracast.</span></span> <span data-ttu-id="bed22-140">我們建議您繼續使用此設定 (如果您之前曾經使用)，不然的話 Miracast 會改為使用一般的 Miracast (如果基礎結構連線未運作)。</span><span class="sxs-lookup"><span data-stu-id="bed22-140">We recommend that you continue using this setting (if you used it previously) as Miracast will fall back to regular Miracast if the infrastructure connection does not work.</span></span> 

## <span data-ttu-id="bed22-141">常見問題集</span><span class="sxs-lookup"><span data-stu-id="bed22-141">FAQ</span></span>
**<span data-ttu-id="bed22-142">為什麼仍需要使用 Wi-fi 才能透過基礎結構使用 Miracast？</span><span class="sxs-lookup"><span data-stu-id="bed22-142">Why do I still need Wi-Fi to use Miracast over infrastructure?</span></span>**<br>
<span data-ttu-id="bed22-143">識別 Miracast 接收器的探索要求只能透過 Wi-fi 配接器來進行。</span><span class="sxs-lookup"><span data-stu-id="bed22-143">Discovery requests to identify Miracast receivers can only occur through the Wi-Fi adapter.</span></span> <span data-ttu-id="bed22-144">當接收器已確定之後，Windows 10 就可以嘗試連線到網路。</span><span class="sxs-lookup"><span data-stu-id="bed22-144">Once the receivers have been identified, Windows 10 can then attempt the connection to the network.</span></span>
