---
title: 最佳化 Surface 裝置的 Wi-Fi 連線能力
description: 本主題描述建議的 Wi-fi 設定，以確保 Surface 裝置在擁塞的網路環境和行動案例中保持連線。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.audience: itpro
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: tokatz
manager: laurawi
ms.openlocfilehash: 2fb64f86e3c1da0e4ba3834877548898e98fd893
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831511"
---
# <span data-ttu-id="4228f-103">最佳化 Surface 裝置的 Wi-Fi 連線能力</span><span class="sxs-lookup"><span data-stu-id="4228f-103">Optimize Wi-Fi connectivity for Surface devices</span></span>


<span data-ttu-id="4228f-104">為了與全天的電池使用時間保持連線，Surface 裝置會實施無線連線設定，以平衡效能和電源保留。</span><span class="sxs-lookup"><span data-stu-id="4228f-104">To stay connected with all-day battery life, Surface devices implement wireless connectivity settings that balance performance and power conservation.</span></span> <span data-ttu-id="4228f-105">在最苛刻的行動案例之外，使用者可以維持足夠的無線連線，而不需修改預設的網路介面卡或相關設定。</span><span class="sxs-lookup"><span data-stu-id="4228f-105">Outside of the most demanding mobility scenarios, users can maintain sufficient wireless connectivity without modifying default network adapter or related settings.</span></span> 

<span data-ttu-id="4228f-106">在擁塞的網路環境中，組織可以在多個網路存取點上實現專門建立的無線通訊協定，以方便漫遊。</span><span class="sxs-lookup"><span data-stu-id="4228f-106">In congested network environments, organizations can implement purpose-built wireless protocols across multiple network access points to facilitate roaming.</span></span> <span data-ttu-id="4228f-107">此頁面重點說明使用 Surface Pro 3 及更新版本、surface Book、surface 膝上型電腦和表面的行動案例中的重要無線連線考慮。</span><span class="sxs-lookup"><span data-stu-id="4228f-107">This page highlights key wireless connectivity considerations in mobile scenarios utilizing Surface Pro 3 and later, Surface Book, Surface Laptop, and Surface Go.</span></span>

## <span data-ttu-id="4228f-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="4228f-108">Prerequisites</span></span>

<span data-ttu-id="4228f-109">本檔假設您已成功部署支援 802.11 n （Wi-fi 4）或更新版本的無線網路，符合主要設備廠商的最佳做法建議。</span><span class="sxs-lookup"><span data-stu-id="4228f-109">This document assumes you have successfully deployed a wireless network that supports 802.11n (Wi-Fi 4) or later in accordance with best practice recommendations from leading equipment vendors.</span></span>

## <span data-ttu-id="4228f-110">針對最佳漫遊功能設定存取點</span><span class="sxs-lookup"><span data-stu-id="4228f-110">Configuring access points for optimal roaming capabilities</span></span>

<span data-ttu-id="4228f-111">如果您管理的無線網路通常是許多不同類型的用戶端裝置，建議您在 WLAN 中啟用存取點（Ap）上的特定通訊協定，如[使用 802.11 k、802.11 v 和 802.11 r 的快速漫遊](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)中所述。</span><span class="sxs-lookup"><span data-stu-id="4228f-111">If you’re managing a wireless network that’s typically accessed by many different types of client devices, it’s recommended to enable specific protocols on access points (APs) in your WLAN, as described in [Fast Roaming with 802.11k, 802.11v, and 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r).</span></span> <span data-ttu-id="4228f-112">Surface 裝置可以利用下列無線通訊協定：</span><span class="sxs-lookup"><span data-stu-id="4228f-112">Surface devices can take advantage of the following wireless protocols:</span></span>

- **<span data-ttu-id="4228f-113">802.11 r。</span><span class="sxs-lookup"><span data-stu-id="4228f-113">802.11r.</span></span>** <span data-ttu-id="4228f-114">「**快速 BSS 轉換**」可減少您在裝置上移動到其他 AP 之前所需的機架數，以加速連線到新的無線存取點。</span><span class="sxs-lookup"><span data-stu-id="4228f-114">“**Fast BSS Transition”** accelerates connecting to new wireless access points by reducing the number of frames required before your device can access another AP as you move around with your device.</span></span>
- **<span data-ttu-id="4228f-115">802.11 k。</span><span class="sxs-lookup"><span data-stu-id="4228f-115">802.11k.</span></span>** <span data-ttu-id="4228f-116">**[鄰居報告]** 可在鄰近存取點提供目前條件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4228f-116">**“Neighbor Reports”** provides devices with information on current conditions at neighboring access points.</span></span> <span data-ttu-id="4228f-117">它可以協助您的 Surface 裝置使用信號強度（例如 AP 利用率）以外的準則來選擇最佳 AP。</span><span class="sxs-lookup"><span data-stu-id="4228f-117">It can help your Surface device choose the best AP using criteria other than signal strength such as AP utilization.</span></span>

<span data-ttu-id="4228f-118">特定 Surface 裝置也可以使用 802.11 v 「BSS 轉換管理幀」，這項功能很像 802.11 k，提供附近的候選人 Ap 資訊。</span><span class="sxs-lookup"><span data-stu-id="4228f-118">Specific Surface devices can also use 802.11v “BSS Transition Management Frames,” which functions much like 802.11k in providing information on nearby candidate APs.</span></span> <span data-ttu-id="4228f-119">這些包括 Surface Go、Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="4228f-119">These include Surface Go, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

## <span data-ttu-id="4228f-120">管理使用者設定</span><span class="sxs-lookup"><span data-stu-id="4228f-120">Managing user settings</span></span>

<span data-ttu-id="4228f-121">您可以透過在所有存取點都支援 802.11 r 和 802.11 k 的精心設計網路，來實現最佳的漫遊功能。</span><span class="sxs-lookup"><span data-stu-id="4228f-121">You can achieve optimal roaming capabilities through a well-designed network that supports  802.11r and 802.11k across all access points.</span></span> <span data-ttu-id="4228f-122">確保您的網路正確設定為提供最佳的無線體驗，是建議的方法，而不是嘗試管理個別裝置上的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="4228f-122">Ensuring that your network is properly configured to provide users with the best wireless experience is the recommended approach versus attempting to manage user settings on individual devices.</span></span> <span data-ttu-id="4228f-123">此外，在許多公司環境 Surface 裝置中，使用者將無法在沒有明確許可權或本機系統管理員許可權的情況下，存取高級網路介面卡設定。</span><span class="sxs-lookup"><span data-stu-id="4228f-123">Moreover, in many corporate environments Surface device users won’t be able to access advanced network adapter settings without explicit permissions or local admin rights.</span></span> <span data-ttu-id="4228f-124">在其他輕中管理的網路中，使用者可以瞭解特定設定對保持連線的能力有何影響，以獲得好處。</span><span class="sxs-lookup"><span data-stu-id="4228f-124">In other lightly managed networks, users can benefit by knowing how specific settings can impact their ability to remain connected.</span></span>

### <span data-ttu-id="4228f-125">建議的使用者設定和最佳做法</span><span class="sxs-lookup"><span data-stu-id="4228f-125">Recommended user settings and best practices</span></span>

<span data-ttu-id="4228f-126">在某些情況下，修改內建在 Surface 裝置中的高級網路介面卡設定，就能協助更可靠的連線。</span><span class="sxs-lookup"><span data-stu-id="4228f-126">In certain situations, modifying advanced network adapter settings built into Surface devices may facilitate a more reliable connection.</span></span> <span data-ttu-id="4228f-127">請記住，由於存取點問題、網路設計缺陷或環境網站問題，無法連線至無線資源是很常見的。</span><span class="sxs-lookup"><span data-stu-id="4228f-127">Keep in mind however that an inability to connect to wireless resources is more often due to an access point issue, networking design flaw, or environmental site issue.</span></span>

> [!NOTE]
> <span data-ttu-id="4228f-128">您保留 Surface Pro 或 Surface Go 的方式也會影響信號強度。</span><span class="sxs-lookup"><span data-stu-id="4228f-128">How you hold your Surface Pro or Surface Go can also affect signal strength.</span></span> <span data-ttu-id="4228f-129">如果您遇到頻寬遺失的情況，請確認您不是在顯示 Wi-fi 無線電收發器所在的位置上。</span><span class="sxs-lookup"><span data-stu-id="4228f-129">If you’re experiencing a loss of bandwidth, check that you’re not holding the top of the display, where the Wi-Fi radio receiver is located.</span></span> <span data-ttu-id="4228f-130">雖然按住顯示器頂端不會封鎖無線信號，但它可以觸發裝置驅動程式，以啟動減少連線性的變更。</span><span class="sxs-lookup"><span data-stu-id="4228f-130">Although holding the top of the display does not block wireless signals, it can trigger the device driver to initiate changes that reduce connectivity.</span></span>

### <span data-ttu-id="4228f-131">保留雙頻寬功能的預設自動設定</span><span class="sxs-lookup"><span data-stu-id="4228f-131">Keep default Auto setting for dual bandwidth capability</span></span>
<span data-ttu-id="4228f-132">在大部分的 Surface 裝置上，您可以將用戶端網路介面卡設定設定為只透過5千兆赫（GHz）連線至無線 Ap，只需連接 2.4 GHz，或讓作業系統選擇最佳選項（預設為 [自動設定]）。</span><span class="sxs-lookup"><span data-stu-id="4228f-132">On most Surface devices, you can configure client network adapter settings to only connect to wireless APs over 5 gigahertz (GHz), only connect over 2.4 GHz, or let the operating system choose the best option (default Auto setting).</span></span>

**<span data-ttu-id="4228f-133">若要存取網路介面卡設定，請移至：</span><span class="sxs-lookup"><span data-stu-id="4228f-133">To access network adapter settings go to:</span></span>**

- <span data-ttu-id="4228f-134">**開始**  > **[控制台]**  > **網路與共享中心**  > **您的 wi-fi 配接器**  > **屬性**  > **設定**  > [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="4228f-134">**Start** > **Control panel** > **Network and Sharing Center** > **your Wi-Fi adapter** > **Properties** > **Configure** > **Advanced**.</span></span>

![\* wifi 區段設定 \*](images/wifi-band.png) <br>

<span data-ttu-id="4228f-136">請記住，2.4 GHz 與 5 GHz 相比有一些優點：它進一步延伸，且更容易 penetrates 穿過牆或其他實體物件。</span><span class="sxs-lookup"><span data-stu-id="4228f-136">Keep in mind that 2.4 GHz has some advantages over 5 GHz: It extends further and more easily penetrates through walls or other solid objects.</span></span> <span data-ttu-id="4228f-137">除非您有可保證連線至 5 GHz 的明確使用案例，否則建議您將波段設定留在預設狀態，以避免可能產生不利的後果。</span><span class="sxs-lookup"><span data-stu-id="4228f-137">Unless you have a clear use case that warrants connecting to 5 GHz, it’s recommended to leave the Band setting in the default state to avoid possible adverse consequences.</span></span> <span data-ttu-id="4228f-138">例如：</span><span class="sxs-lookup"><span data-stu-id="4228f-138">For example:</span></span>


- <span data-ttu-id="4228f-139">在旅館、咖啡店和機場中發現的許多熱點仍只使用 2.4 GHz，只要將波段設定為 5 GHz，就能有效封鎖裝置的存取權。</span><span class="sxs-lookup"><span data-stu-id="4228f-139">Many hotspots found in hotels, coffee shops, and airports still only use 2.4 GHz, effectively blocking access to devices if Band is set to 5 GHz Only.</span></span>
- <span data-ttu-id="4228f-140">由於 Miracast 無線顯示器連線需要在 2.4 GHz 通道完成初始握手，否則裝置將無法在 5 GHz 內連線。</span><span class="sxs-lookup"><span data-stu-id="4228f-140">Since Miracast wireless display connections require the initial handshake to be completed over 2.4 GHz channels, devices won’t be able to connect at 5 GHz Only.</span></span>

> [!NOTE]
> <span data-ttu-id="4228f-141">根據預設，Surface 裝置會優先連接至 5 GHz （如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="4228f-141">By default Surface devices will prefer connecting to 5 GHz if available.</span></span> <span data-ttu-id="4228f-142">不過，若要在電池計量不足時保持電能，Surface 會先尋找 2.4 GHz 連線。</span><span class="sxs-lookup"><span data-stu-id="4228f-142">However, to preserve power  in a low battery state, Surface will first look for a 2.4 GHz connection.</span></span>

<span data-ttu-id="4228f-143">您也可以視需要切換區段設定以符合您的環境。</span><span class="sxs-lookup"><span data-stu-id="4228f-143">You can also toggle the band setting as needed to suit your environment.</span></span> <span data-ttu-id="4228f-144">例如，生活在具有多個 Wi-fi 熱點的高密度公寓建築物中，無論消費者裝置的目前狀態是透過 2.4 GHz 廣播，都有可能帶來益處，只需將其 Surface 裝置設定為僅以 5 GHz 連線，然後在需要時回復到 Auto。</span><span class="sxs-lookup"><span data-stu-id="4228f-144">For example, users living in high density apartment buildings with multiple Wi-Fi hotspots  —  amid the presence of consumer devices all broadcasting via 2.4 GHz  —  will likely benefit by setting their Surface device to connect on 5 GHz only and then revert to Auto when needed.</span></span>

### <span data-ttu-id="4228f-145">表面上的漫遊加強設定</span><span class="sxs-lookup"><span data-stu-id="4228f-145">Roaming aggressiveness settings on Surface Go</span></span>

<span data-ttu-id="4228f-146">使用 Surface Go 的前線工作者可能想要選取信號強度閾值，以提示裝置在信號強度下降（漫遊加強）時搜尋新的存取點。</span><span class="sxs-lookup"><span data-stu-id="4228f-146">Front-line workers using Surface Go may wish to select a signal strength threshold that prompts the device to search for a new access point when signal strength drops (roaming aggressiveness).</span></span> <span data-ttu-id="4228f-147">根據預設，如果信號強度下降低於**中型**（50% 信號強度），Surface devices 就會嘗試漫遊到新的存取點。</span><span class="sxs-lookup"><span data-stu-id="4228f-147">By default, Surface devices attempt to roam to a new access point if the signal strength drops below **Medium** (50 percent signal strength).</span></span> <span data-ttu-id="4228f-148">請注意，每當您增加漫遊加強，就能加速電池計量消耗。</span><span class="sxs-lookup"><span data-stu-id="4228f-148">Note that whenever you increase roaming aggressiveness, you accelerate battery power consumption.</span></span>

<span data-ttu-id="4228f-149">除非您遇到特定行動案例中的連線性問題（例如執行環境網站檢查），同時在會議會議期間維持語音與視頻連線，否則請將漫遊的入侵設定保留在預設狀態。</span><span class="sxs-lookup"><span data-stu-id="4228f-149">Leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="4228f-150">如果您沒有注意到任何改善會復原為預設**媒體**狀態。</span><span class="sxs-lookup"><span data-stu-id="4228f-150">If you don’t notice any improvement revert to the default **Medium** state.</span></span>

**<span data-ttu-id="4228f-151">若要在表面上啟用漫遊加強，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="4228f-151">To enable roaming aggressiveness on Surface Go:</span></span>**

1. <span data-ttu-id="4228f-152">移至 [**開始] > [控制台**  >  **網路和網際網路**  >  **網路及共用中心]。**</span><span class="sxs-lookup"><span data-stu-id="4228f-152">Go to **Start > Control Panel** > **Network and Internet** > **Network and Sharing Center.**</span></span>
2. <span data-ttu-id="4228f-153">在 [連線] 底下，選取 [ **wi-fi** ]，**然後選取 [** **屬性]。**</span><span class="sxs-lookup"><span data-stu-id="4228f-153">Under **Connections** select **Wi-Fi** and then select **Properties.**</span></span>
3. <span data-ttu-id="4228f-154">選取 [ **Microsoft 網路用戶端**]，然後選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="4228f-154">Select **Client for Microsoft Networks** and then select **Configure**</span></span>
4. <span data-ttu-id="4228f-155">選取 [**高級**  >  **漫遊加強**]，然後從下拉式功能表中選擇您想要的值。</span><span class="sxs-lookup"><span data-stu-id="4228f-155">Select **Advanced** > **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 漫遊加強設定 \*](images/wifi-roaming.png) <br>

## <span data-ttu-id="4228f-157">總結</span><span class="sxs-lookup"><span data-stu-id="4228f-157">Conclusion</span></span>

<span data-ttu-id="4228f-158">Surface 裝置的設計使用預設設定來實現最佳無線連線平衡，且需要保留電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="4228f-158">Surface devices are designed with default settings for optimal wireless connectivity balanced alongside the need to preserve battery life.</span></span> <span data-ttu-id="4228f-159">為 Surface 裝置啟用可靠連接的最有效方法，是透過設計良好的網路，支援 802.11 r 和 802.11 k。</span><span class="sxs-lookup"><span data-stu-id="4228f-159">The most effective way of enabling reliable connectivity for Surface devices is through a well-designed network that supports 802.11r and 802.11k.</span></span> <span data-ttu-id="4228f-160">使用者可以調整網路介面卡設定或漫遊加強，但應只針對特定的環境因素作出回應，並在沒有明顯的改進時還原為預設狀態。</span><span class="sxs-lookup"><span data-stu-id="4228f-160">Users can adjust network adapter settings or roaming aggressiveness but should only do so in response to specific environmental factors and revert to default state if there’s no noticeable improvement.</span></span>
