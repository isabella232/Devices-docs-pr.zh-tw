---
title: 適用於 Surface 裝置的網路喚醒
description: 瞭解如何使用 LAN 喚醒來遠端喚醒裝置，以自動執行管理工作。
keywords: 更新、部署、驅動程式、wol、wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
ms.date: 3/19/2021
ms.openlocfilehash: 1fbbf899876d154469d48fa75a179196697205c1
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442155"
---
# <a name="wake-on-lan-for-surface-devices"></a><span data-ttu-id="12369-104">適用於 Surface 裝置的網路喚醒</span><span class="sxs-lookup"><span data-stu-id="12369-104">Wake On LAN for Surface devices</span></span>

<span data-ttu-id="12369-105">使用 Surface 乙太網路介面卡連接到有線網路的 Surface 裝置可以利用從已連接待命 (喚醒 LAN) WOL。</span><span class="sxs-lookup"><span data-stu-id="12369-105">Surface devices that use a Surface Ethernet adapter to connect to a wired network can take advantage of Wake On LAN (WOL) from Connected Standby.</span></span> <span data-ttu-id="12369-106">使用 WOL，您可以使用 Microsoft 端點管理員/Microsoft Intune 等管理解決方案，遠端喚醒裝置並自動執行管理工作。</span><span class="sxs-lookup"><span data-stu-id="12369-106">With WOL, you can remotely wake up devices and automatically perform management tasks using management solutions such as Microsoft Endpoint Manager/Microsoft Intune.</span></span>

## <a name="wol-supported-devices"></a><span data-ttu-id="12369-107">支援 WOL 的裝置</span><span class="sxs-lookup"><span data-stu-id="12369-107">WOL-supported devices</span></span>

- <span data-ttu-id="12369-108">Surface 乙太網路介面卡</span><span class="sxs-lookup"><span data-stu-id="12369-108">Surface Ethernet adapter</span></span>
- <span data-ttu-id="12369-109">Surface USB-C 到乙太網路和 USB 介面卡</span><span class="sxs-lookup"><span data-stu-id="12369-109">Surface USB-C to Ethernet and USB Adapter</span></span>
- <span data-ttu-id="12369-110">Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="12369-110">Surface Dock 2</span></span>
- <span data-ttu-id="12369-111">Surface Pro 6 及更高版本</span><span class="sxs-lookup"><span data-stu-id="12369-111">Surface Pro 6 and later</span></span>
- <span data-ttu-id="12369-112">Surface Book (代) </span><span class="sxs-lookup"><span data-stu-id="12369-112">Surface Book (all generations)</span></span>
- <span data-ttu-id="12369-113">Surface Laptop (代代) </span><span class="sxs-lookup"><span data-stu-id="12369-113">Surface Laptop (all generations)</span></span>
- <span data-ttu-id="12369-114">Surface Go (代) </span><span class="sxs-lookup"><span data-stu-id="12369-114">Surface Go (all generations)</span></span>
- <span data-ttu-id="12369-115">Surface Studio 2 (請參閱) </span><span class="sxs-lookup"><span data-stu-id="12369-115">Surface Studio 2 (see Appendix)</span></span>


## <a name="using-surface-wol"></a><span data-ttu-id="12369-116">使用 Surface WOL</span><span class="sxs-lookup"><span data-stu-id="12369-116">Using Surface WOL</span></span>

<span data-ttu-id="12369-117">IT 系統管理員可以使用 LAN 要求喚醒 (包含目的電腦的 MAC 位址的) 封包來觸發裝置。</span><span class="sxs-lookup"><span data-stu-id="12369-117">IT admins can trigger devices using a wake on LAN request (magic packet) that contains the target computer’s MAC address.</span></span> <span data-ttu-id="12369-118">若要傳送神奇的封包，然後使用 WOL 喚醒裝置，您必須知道目標裝置和乙太網路介面卡的 MAC 位址。</span><span class="sxs-lookup"><span data-stu-id="12369-118">To send a magic packet and wake up a device by using WOL, you must know the MAC address of the target device and Ethernet adapter.</span></span> <span data-ttu-id="12369-119">由於魔術封包不使用 IP 網路通訊協定，因此無法使用裝置 IP 位址或 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="12369-119">Because the magic packet does not use the IP network protocol, it is not possible to use the IP address or DNS name of the device.</span></span>

<span data-ttu-id="12369-120">許多管理解決方案 ，例如 Microsoft 端點組組管理員和協力廠商 Microsoft Store 應用程式，都提供 WOL 的內建支援。</span><span class="sxs-lookup"><span data-stu-id="12369-120">Many management solutions, such as Microsoft Endpoint Configuration Manager and third party Microsoft Store apps provide built-in support for WOL.</span></span> <span data-ttu-id="12369-121">請注意，裝置必須處於已 (睡眠模式) 並連接到 AC 電源。</span><span class="sxs-lookup"><span data-stu-id="12369-121">Note that devices need to be in Connected Standby (Sleep) mode and connected to AC power.</span></span> <span data-ttu-id="12369-122">若要深入瞭解使用端點設定管理員喚醒裝置，請參閱在 LAN [上設定喚醒 - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan)。</span><span class="sxs-lookup"><span data-stu-id="12369-122">To learn more about waking devices with Endpoint Configuration Manager, see [Configure Wake on LAN - Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/clients/deploy/configure-wake-on-lan).</span></span>


## <a name="to-check-wol-is-enabled-on-your-device"></a><span data-ttu-id="12369-123">若要檢查您的裝置上已啟用 WOL</span><span class="sxs-lookup"><span data-stu-id="12369-123">To check WOL is enabled on your device</span></span>

1. <span data-ttu-id="12369-124">在乙太網路連接裝置上，選取您的網路介面卡，然後 **選取屬性**。</span><span class="sxs-lookup"><span data-stu-id="12369-124">On your Ethernet connected device, select your network adapter, and then select **Properties**.</span></span>

   > [!div class="mx-imgBorder"]
   > ![Surface 乙太網路介面卡](images/surface-ethernet.png)

2. <span data-ttu-id="12369-126">選取**設定**  >  **進位**。</span><span class="sxs-lookup"><span data-stu-id="12369-126">Select **Configure** > **Advanced**.</span></span>
3. <span data-ttu-id="12369-127">卷起 **至新式備用 WoL 魔術封包** ，並確保 **已選取啟用** 。</span><span class="sxs-lookup"><span data-stu-id="12369-127">Scroll to **Modern Standby WoL Magic Packet** and ensure **Enabled** is selected.</span></span>

     ![檢查您的裝置上已啟用 WOL](images/ethernet-wol-setting.png)

## <a name="appendix-surface-studio-2"></a><span data-ttu-id="12369-129">附件：Surface Studio 2</span><span class="sxs-lookup"><span data-stu-id="12369-129">Appendix: Surface Studio 2</span></span>

<span data-ttu-id="12369-130">若要在 Surface Studio 2 上啟用 WOL，請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="12369-130">To enable WOL on Surface Studio 2, use the following procedure.</span></span>

1. <span data-ttu-id="12369-131">建立下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="12369-131">Create the following registry keys:</span></span>

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. <span data-ttu-id="12369-132">執行下列命令</span><span class="sxs-lookup"><span data-stu-id="12369-132">Run the following command</span></span>

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```


## <a name="learn-more"></a><span data-ttu-id="12369-133">深入了解</span><span class="sxs-lookup"><span data-stu-id="12369-133">Learn more</span></span>

- [<span data-ttu-id="12369-134">Microsoft Surface USB-C 到乙太網路和 USB 介面卡</span><span class="sxs-lookup"><span data-stu-id="12369-134">Microsoft Surface USB-C to Ethernet and USB Adapter</span></span>](https://www.microsoft.com/p/surface-usb-c-to-ethernet-and-usb-adapter/8wt81cglrblp?)

- [<span data-ttu-id="12369-135">Surface USB 3.0 Gb 乙太網路介面卡</span><span class="sxs-lookup"><span data-stu-id="12369-135">Surface USB 3.0 Gigabit Ethernet Adapter</span></span>](https://www.microsoft.com/p/surface-usb-30-gigabit-ethernet-adapter/8xn9fqvzbvq0?)
