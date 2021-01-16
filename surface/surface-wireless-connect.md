---
title: 最佳化 Surface 裝置的 Wi-Fi 連線能力
description: 本主題描述建議的 Wi-Fi 設定，以確保 Surface 裝置在擁塞的網路環境和行動案例中保持連線。
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
ms.date: 01/15/2021
ms.openlocfilehash: 69ca7bc7383a122dfd4f069135319b92ff7edfb0
ms.sourcegitcommit: 1053479c191fd10651d31a466fad1769fb0cd28b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/16/2021
ms.locfileid: "11271377"
---
# <span data-ttu-id="907bb-103">最佳化 Surface 裝置的 Wi-Fi 連線能力</span><span class="sxs-lookup"><span data-stu-id="907bb-103">Optimize Wi-Fi connectivity for Surface devices</span></span>


<span data-ttu-id="907bb-104">為了與全天的電池使用時間保持連線，Surface 裝置會實施無線連線設定，以平衡效能和電源保留。</span><span class="sxs-lookup"><span data-stu-id="907bb-104">To stay connected with all-day battery life, Surface devices implement wireless connectivity settings that balance performance and power conservation.</span></span> <span data-ttu-id="907bb-105">在最苛刻的行動案例之外，使用者可以維持足夠的無線連線，而不需修改預設的網路介面卡或相關設定。</span><span class="sxs-lookup"><span data-stu-id="907bb-105">Outside of the most demanding mobility scenarios, users can maintain sufficient wireless connectivity without modifying default network adapter or related settings.</span></span> <span data-ttu-id="907bb-106">此頁面重點說明行動案例中使用最新 Surface 裝置（包括 Surface Pro 7 +、Surface 膝上型電腦 Go、Surface Go 2、surface Pro X、Surface mobile 3、Surface Book 3 和 Surface Pro 7）的重要無線連線考慮。</span><span class="sxs-lookup"><span data-stu-id="907bb-106">This page highlights key wireless connectivity considerations in mobile scenarios using the latest Surface devices including Surface Pro 7+, Surface Laptop Go, Surface Go 2, Surface Pro X, Surface Laptop 3, Surface Book 3, and Surface Pro 7.</span></span>

## <span data-ttu-id="907bb-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="907bb-107">Prerequisites</span></span>

<span data-ttu-id="907bb-108">本檔假設您已成功部署支援 802.11 n (Wi-fi 4) 或更新版本的無線網路，以符合主要設備廠商的最佳做法建議。</span><span class="sxs-lookup"><span data-stu-id="907bb-108">This document assumes you have successfully deployed a wireless network that supports 802.11n (Wi-Fi 4) or later in accordance with best practice recommendations from leading equipment vendors.</span></span>

## <span data-ttu-id="907bb-109">針對最佳漫遊功能設定存取點</span><span class="sxs-lookup"><span data-stu-id="907bb-109">Configuring access points for optimal roaming capabilities</span></span>

<span data-ttu-id="907bb-110">如果您管理的無線網路通常是許多不同類型的用戶端裝置，建議您在 WLAN 中 (Ap) 的存取點上啟用特定通訊協定，如 [使用 802.11 k、802.11 v 和 802.11 r 的快速漫遊](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)中所述。</span><span class="sxs-lookup"><span data-stu-id="907bb-110">If you’re managing a wireless network that’s typically accessed by many different types of client devices, it’s recommended to enable specific protocols on access points (APs) in your WLAN, as described in [Fast Roaming with 802.11k, 802.11v, and 802.11r](https://docs.microsoft.com/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r).</span></span> <span data-ttu-id="907bb-111">Surface 裝置可以利用下列無線通訊協定：</span><span class="sxs-lookup"><span data-stu-id="907bb-111">Surface devices can take advantage of the following wireless protocols:</span></span>

- **<span data-ttu-id="907bb-112">802.11 r。</span><span class="sxs-lookup"><span data-stu-id="907bb-112">802.11r.</span></span>** <span data-ttu-id="907bb-113">「**快速 BSS 轉換** 」可減少您在裝置上移動到其他 AP 之前所需的機架數，以加速連線到新的無線存取點。</span><span class="sxs-lookup"><span data-stu-id="907bb-113">“**Fast BSS Transition”** accelerates connecting to new wireless access points by reducing the number of frames required before your device can access another AP as you move around with your device.</span></span> <span data-ttu-id="907bb-114">在2019之後發行的新一代 Surface 裝置中，使用者可能會在裝置上存取漫遊加強設定。</span><span class="sxs-lookup"><span data-stu-id="907bb-114">In the new generation of Surface devices released since 2019, end users may gain access to roaming aggressiveness settings on their device.</span></span> <span data-ttu-id="907bb-115">雖然建議您不要修改預設設定，但使用者應該知道這項功能，並瞭解特定設定對保持連線的能力有何影響。</span><span class="sxs-lookup"><span data-stu-id="907bb-115">Although modifying default settings is not recommended, users should be aware of this capability and understand how specific settings can impact their ability to remain connected.</span></span>
- **<span data-ttu-id="907bb-116">802.11 k。</span><span class="sxs-lookup"><span data-stu-id="907bb-116">802.11k.</span></span>** <span data-ttu-id="907bb-117">**[鄰居報告]** 可在鄰近存取點提供目前條件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="907bb-117">**“Neighbor Reports”** provides devices with information on current conditions at neighboring access points.</span></span> <span data-ttu-id="907bb-118">它可以協助您的 Surface 裝置使用信號強度（例如 AP 利用率）以外的準則來選擇最佳 AP。</span><span class="sxs-lookup"><span data-stu-id="907bb-118">It can help your Surface device choose the best AP using criteria other than signal strength such as AP utilization.</span></span>

<span data-ttu-id="907bb-119">特定 Surface 裝置也可以使用 802.11 v 「BSS 轉換管理幀」，這項功能很像 802.11 k，提供附近的候選人 Ap 資訊。</span><span class="sxs-lookup"><span data-stu-id="907bb-119">Specific Surface devices can also use 802.11v “BSS Transition Management Frames,” which functions much like 802.11k in providing information on nearby candidate APs.</span></span> <span data-ttu-id="907bb-120">這些包括 Surface Pro 7 +、表面移、表面移至2、Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3。</span><span class="sxs-lookup"><span data-stu-id="907bb-120">These include Surface Pro 7+, Surface Go, Surface Go 2, Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

## <span data-ttu-id="907bb-121">管理使用者設定</span><span class="sxs-lookup"><span data-stu-id="907bb-121">Managing user settings</span></span>

<span data-ttu-id="907bb-122">您可以透過在所有存取點都支援 802.11 r 和 802.11 k 的精心設計網路，來實現最佳的漫遊功能。</span><span class="sxs-lookup"><span data-stu-id="907bb-122">You can achieve optimal roaming capabilities through a well-designed network that supports  802.11r and 802.11k across all access points.</span></span> <span data-ttu-id="907bb-123">確保您的網路正確設定為提供最佳的無線體驗，是建議的方法，而不是嘗試管理個別裝置上的使用者設定。</span><span class="sxs-lookup"><span data-stu-id="907bb-123">Ensuring that your network is properly configured to provide users with the best wireless experience is the recommended approach versus attempting to manage user settings on individual devices.</span></span> 

### <span data-ttu-id="907bb-124">建議的使用者設定和最佳做法</span><span class="sxs-lookup"><span data-stu-id="907bb-124">Recommended user settings and best practices</span></span>

<span data-ttu-id="907bb-125">在某些情況下，修改內建在 Surface 裝置中的高級網路介面卡設定，就能協助更可靠的連線。</span><span class="sxs-lookup"><span data-stu-id="907bb-125">In certain situations, modifying advanced network adapter settings built into Surface devices may facilitate a more reliable connection.</span></span> <span data-ttu-id="907bb-126">請記住，由於存取點問題、網路設計缺陷或環境網站問題，無法連線至無線資源是很常見的。</span><span class="sxs-lookup"><span data-stu-id="907bb-126">Keep in mind however that an inability to connect to wireless resources is more often due to an access point issue, networking design flaw, or environmental site issue.</span></span>

> [!NOTE]
> <span data-ttu-id="907bb-127">您保留 Surface Pro 或 Surface Go 的方式也會影響信號強度。</span><span class="sxs-lookup"><span data-stu-id="907bb-127">How you hold your Surface Pro or Surface Go can also affect signal strength.</span></span> <span data-ttu-id="907bb-128">如果您遇到頻寬遺失的情況，請確認您不是顯示 Wi-Fi 無線電接收器所在的顯示器頂端。</span><span class="sxs-lookup"><span data-stu-id="907bb-128">If you’re experiencing a loss of bandwidth, check that you’re not holding the top of the display, where the Wi-Fi radio receiver is located.</span></span> <span data-ttu-id="907bb-129">雖然按住顯示器頂端不會封鎖無線信號，但它可以觸發裝置驅動程式，以啟動減少連線性的變更。</span><span class="sxs-lookup"><span data-stu-id="907bb-129">Although holding the top of the display does not block wireless signals, it can trigger the device driver to initiate changes that reduce connectivity.</span></span>

### <span data-ttu-id="907bb-130">保留雙頻寬功能的預設自動設定</span><span class="sxs-lookup"><span data-stu-id="907bb-130">Keep default Auto setting for dual bandwidth capability</span></span>

<span data-ttu-id="907bb-131">在大部分的 Surface 裝置上，您可以設定用戶端網路介面卡設定，以便只透過5千兆赫 (GHz) 連線至無線 Ap，只需連接 2.4 GHz，或讓作業系統選擇最佳選項 (預設的 [自動設定]) 。</span><span class="sxs-lookup"><span data-stu-id="907bb-131">On most Surface devices, you can configure client network adapter settings to only connect to wireless APs over 5 gigahertz (GHz), only connect over 2.4 GHz, or let the operating system choose the best option (default Auto setting).</span></span>

**<span data-ttu-id="907bb-132">若要存取網路介面卡設定，請移至：</span><span class="sxs-lookup"><span data-stu-id="907bb-132">To access network adapter settings go to:</span></span>**

- <span data-ttu-id="907bb-133">**開始**  > **[控制台]**  > **網路與共享中心**  > **您的 Wi-Fi 配接器**  > **屬性**  > **設定**  > [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="907bb-133">**Start** > **Control panel** > **Network and Sharing Center** > **your Wi-Fi adapter** > **Properties** > **Configure** > **Advanced**.</span></span>

![\* wifi 區段設定 \*](images/wifi-band.png) <br>

<span data-ttu-id="907bb-135">請記住，2.4 GHz 與 5 GHz 相比有一些優點：它進一步延伸，且更容易 penetrates 穿過牆或其他實體物件。</span><span class="sxs-lookup"><span data-stu-id="907bb-135">Keep in mind that 2.4 GHz has some advantages over 5 GHz: It extends further and more easily penetrates through walls or other solid objects.</span></span> <span data-ttu-id="907bb-136">除非您有可保證連線至 5 GHz 的明確使用案例，否則建議您將波段設定留在預設狀態，以避免可能產生不利的後果。</span><span class="sxs-lookup"><span data-stu-id="907bb-136">Unless you have a clear use case that warrants connecting to 5 GHz, it’s recommended to leave the Band setting in the default state to avoid possible adverse consequences.</span></span> <span data-ttu-id="907bb-137">例如：</span><span class="sxs-lookup"><span data-stu-id="907bb-137">For example:</span></span>


- <span data-ttu-id="907bb-138">在旅館、咖啡店和機場中發現的許多熱點仍只使用 2.4 GHz，只要將波段設定為 5 GHz，就能有效封鎖裝置的存取權。</span><span class="sxs-lookup"><span data-stu-id="907bb-138">Many hotspots found in hotels, coffee shops, and airports still only use 2.4 GHz, effectively blocking access to devices if Band is set to 5 GHz Only.</span></span>
- <span data-ttu-id="907bb-139">由於 Miracast 無線顯示器連線需要在 2.4 GHz 通道完成初始握手，否則裝置將無法在 5 GHz 內連線。</span><span class="sxs-lookup"><span data-stu-id="907bb-139">Since Miracast wireless display connections require the initial handshake to be completed over 2.4 GHz channels, devices won’t be able to connect at 5 GHz Only.</span></span>

> [!NOTE]
> <span data-ttu-id="907bb-140">根據預設，Surface 裝置會優先連接至 5 GHz （如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="907bb-140">By default Surface devices will prefer connecting to 5 GHz if available.</span></span> <span data-ttu-id="907bb-141">不過，若要在電池計量不足時保持電能，Surface 會先尋找 2.4 GHz 連線。</span><span class="sxs-lookup"><span data-stu-id="907bb-141">However, to preserve power  in a low battery state, Surface will first look for a 2.4 GHz connection.</span></span>

<span data-ttu-id="907bb-142">您也可以視需要切換區段設定以符合您的環境。</span><span class="sxs-lookup"><span data-stu-id="907bb-142">You can also toggle the band setting as needed to suit your environment.</span></span> <span data-ttu-id="907bb-143">例如，生活在具有多個 Wi-Fi 熱點的高密度公寓建築物中（無論消費者裝置都透過 2.4 GHz 廣播），都有可能帶來益處，只是將其 Surface 裝置設定為僅以 5 GHz 連線，然後在需要時回復到 Auto。</span><span class="sxs-lookup"><span data-stu-id="907bb-143">For example, users living in high density apartment buildings with multiple Wi-Fi hotspots  —  amid the presence of consumer devices all broadcasting via 2.4 GHz  —  will likely benefit by setting their Surface device to connect on 5 GHz only and then revert to Auto when needed.</span></span>

### <span data-ttu-id="907bb-144">含英特爾配接器的 Surface 裝置上的漫遊加強設定</span><span class="sxs-lookup"><span data-stu-id="907bb-144">Roaming aggressiveness settings on Surface devices with Intel adapters</span></span> 

<span data-ttu-id="907bb-145">使用者可能會想要選取一個信號強度閾值，當信號下降時，系統會提示裝置搜尋新的存取點 (漫遊的入侵) 。</span><span class="sxs-lookup"><span data-stu-id="907bb-145">Users may wish to select a signal strength threshold that prompts the device to search for a new access point when the signal drops (roaming aggressiveness).</span></span> <span data-ttu-id="907bb-146">根據預設，含英特爾配接器的 Surface 裝置會嘗試漫遊到新的存取點（如果信號強度低於 [ **中** ] (72% 信號強度) 。</span><span class="sxs-lookup"><span data-stu-id="907bb-146">By default, Surface devices with Intel adapters attempt to roam to a new access point if the signal strength drops below **Medium** (72 percent signal strength).</span></span> <span data-ttu-id="907bb-147">另請注意，組織可以在多個網路存取點上實現專門建立的無線通訊協定，以協助漫遊擁塞的網路環境，如本頁面先前所述。</span><span class="sxs-lookup"><span data-stu-id="907bb-147">Note also that organizations can implement purpose-built wireless protocols across multiple network access points to facilitate roaming congested network environments, as explained earlier on this page.</span></span> 

<span data-ttu-id="907bb-148">雖然在高擁擠的 office 或家用環境中提高漫遊效率，但在逐步執行這些環境時 **，可能會** 導致連線能力下降。</span><span class="sxs-lookup"><span data-stu-id="907bb-148">While increasing roaming aggressiveness above **Medium** may yield improved connectivity in highly congested office or residential environments, it can result in degraded connectivity when stepping outside of these environments.</span></span> 

<span data-ttu-id="907bb-149">除非您遇到特定行動案例中的連線性問題（例如執行環境網站檢查，同時也會維持會議會議期間的語音和視頻連線），否則建議您在預設狀態中留下漫遊的入侵設定。</span><span class="sxs-lookup"><span data-stu-id="907bb-149">It’s recommended to leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="907bb-150">如果您沒有注意到任何改善，請還原為預設的 [中] 狀態。</span><span class="sxs-lookup"><span data-stu-id="907bb-150">If you don’t notice any improvement, revert to the default Medium state.</span></span> <span data-ttu-id="907bb-151">請注意，如果您增加漫遊加強，您也可以加速電池計量消耗。</span><span class="sxs-lookup"><span data-stu-id="907bb-151">Note that if you increase roaming aggressiveness, you also accelerate battery power consumption.</span></span> 

**<span data-ttu-id="907bb-152">若要在 Surface 上啟用漫遊加強：</span><span class="sxs-lookup"><span data-stu-id="907bb-152">To enable roaming aggressiveness on Surface:</span></span>**

1. <span data-ttu-id="907bb-153">移至 [**啟動**  >  **裝置管理器**]。</span><span class="sxs-lookup"><span data-stu-id="907bb-153">Go to **Start** > **Device Manager**.</span></span>
2. <span data-ttu-id="907bb-154">在 [ **網路介面卡** ] 底下選取 [ **Intel Wi-Fi 6** ，然後以滑鼠右鍵按一下 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="907bb-154">Under **Network adapters** select **Intel Wi-Fi 6** and then right click **Properties**.</span></span>
3. <span data-ttu-id="907bb-155">選取 [ **高級** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="907bb-155">Select the **Advanced** tab.</span></span>
4. <span data-ttu-id="907bb-156">選取 [ **漫遊加強** ]，然後從下拉式功能表中選擇您想要的值。</span><span class="sxs-lookup"><span data-stu-id="907bb-156">Select **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 漫遊加強設定-英特爾 \*](images/wifi-roaming-int.png) <br>

### <span data-ttu-id="907bb-158">表面移至 surface Pro X 上的漫遊加強設定</span><span class="sxs-lookup"><span data-stu-id="907bb-158">Roaming aggressiveness settings on Surface Go and Surface Pro X</span></span>

<span data-ttu-id="907bb-159">使用 Surface Go 的前線工作者可能想要選取信號強度閾值，當信號強度下降 (漫遊加強) 時，就會提示裝置搜尋新的存取點。</span><span class="sxs-lookup"><span data-stu-id="907bb-159">Front-line workers using Surface Go may wish to select a signal strength threshold that prompts the device to search for a new access point when signal strength drops (roaming aggressiveness).</span></span> <span data-ttu-id="907bb-160">根據預設，Surface 裝置會嘗試漫遊到新的存取點（如果信號強度低於 [ **中** ] (50% 信號強度) 。</span><span class="sxs-lookup"><span data-stu-id="907bb-160">By default, Surface devices attempt to roam to a new access point if the signal strength drops below **Medium** (50 percent signal strength).</span></span> <span data-ttu-id="907bb-161">請注意，每當您增加漫遊加強，就能加速電池計量消耗。</span><span class="sxs-lookup"><span data-stu-id="907bb-161">Note that whenever you increase roaming aggressiveness, you accelerate battery power consumption.</span></span>

<span data-ttu-id="907bb-162">除非您遇到特定行動案例中的連線性問題（例如執行環境網站檢查），同時在會議會議期間維持語音與視頻連線，否則請將漫遊的入侵設定保留在預設狀態。</span><span class="sxs-lookup"><span data-stu-id="907bb-162">Leave the roaming aggressiveness setting in the default state unless you’re encountering connectivity issues in specific mobile scenarios such as conducting environmental site inspections while also maintaining voice and video connectivity during a conference meeting.</span></span> <span data-ttu-id="907bb-163">如果您沒有注意到任何改善會復原為預設 **媒體** 狀態。</span><span class="sxs-lookup"><span data-stu-id="907bb-163">If you don’t notice any improvement revert to the default **Medium** state.</span></span>

**<span data-ttu-id="907bb-164">若要在表面上啟用漫遊加強，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="907bb-164">To enable roaming aggressiveness on Surface Go:</span></span>**

1. <span data-ttu-id="907bb-165">移至 [**開始] > [控制台**  >  **網路和網際網路**  >  **網路及共用中心]。**</span><span class="sxs-lookup"><span data-stu-id="907bb-165">Go to **Start > Control Panel** > **Network and Internet** > **Network and Sharing Center.**</span></span>
2. <span data-ttu-id="907bb-166">在 [連線] 底下，選取 [ **wi-fi** ]，**然後選取 [** **屬性]。**</span><span class="sxs-lookup"><span data-stu-id="907bb-166">Under **Connections** select **Wi-Fi** and then select **Properties.**</span></span>
3. <span data-ttu-id="907bb-167">選取 [ **Microsoft 網路用戶端**]，然後選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="907bb-167">Select **Client for Microsoft Networks** and then select **Configure**</span></span>
4. <span data-ttu-id="907bb-168">選取 [**高級**  >  **漫遊加強**]，然後從下拉式功能表中選擇您想要的值。</span><span class="sxs-lookup"><span data-stu-id="907bb-168">Select **Advanced** > **Roaming Aggressiveness** and choose your preferred value from the drop-down menu.</span></span>

![\* 漫遊加強設定-QualComm \*](images/wifi-roaming.png) <br>


## <span data-ttu-id="907bb-170">總結</span><span class="sxs-lookup"><span data-stu-id="907bb-170">Conclusion</span></span>

<span data-ttu-id="907bb-171">Surface 裝置的設計使用預設設定來實現最佳無線連線平衡，且需要保留電池使用時間。</span><span class="sxs-lookup"><span data-stu-id="907bb-171">Surface devices are designed with default settings for optimal wireless connectivity balanced alongside the need to preserve battery life.</span></span> <span data-ttu-id="907bb-172">為 Surface 裝置啟用可靠連接的最有效方法，是透過設計良好的網路，支援 802.11 r 和 802.11 k。</span><span class="sxs-lookup"><span data-stu-id="907bb-172">The most effective way of enabling reliable connectivity for Surface devices is through a well-designed network that supports 802.11r and 802.11k.</span></span> <span data-ttu-id="907bb-173">使用者可以調整網路介面卡設定或漫遊加強，但應只針對特定的環境因素作出回應，並在沒有明顯的改進時還原為預設狀態。</span><span class="sxs-lookup"><span data-stu-id="907bb-173">Users can adjust network adapter settings or roaming aggressiveness but should only do so in response to specific environmental factors and revert to default state if there’s no noticeable improvement.</span></span>
