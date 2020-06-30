---
title: Windows10 (版本 1703) 中 Surface Hub 的新增功能
description: Windows 10 版本 1703 (Creators Update) 為 Microsoft Surface Hub 帶來了新的功能。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 01/18/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: bdc6e384839606fe6138c75e190d68a84679f5b4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831348"
---
# <span data-ttu-id="0129f-103">Windows10 (版本 1703) 中 Microsoft Surface Hub 的新增功能有哪些？</span><span class="sxs-lookup"><span data-stu-id="0129f-103">What's new in Windows 10, version 1703 for Microsoft Surface Hub?</span></span>

<span data-ttu-id="0129f-104">觀賞 Surface Hub 工程師 Jordan Marchese 展示 Windows 10 版本 1703 (Creators Update) 之 Microsoft Surface Hub 更新。</span><span class="sxs-lookup"><span data-stu-id="0129f-104">Watch Surface Hub engineer Jordan Marchese present updates to Microsoft Surface Hub with Windows 10, version 1703 (Creators Update).</span></span> 

<a href="https://www.youtube.com/watch?v=R8tX10VIgq0" target="_blank"> <img src="images/whats-new-video-thumbnail.png" alt="Link to Surface Hub video on Youtube" /></a>

<span data-ttu-id="0129f-105">Windows 10 版本 1703 (也稱為 Creators Update)，為 Microsoft Surface Hub 引入了下列變更。</span><span class="sxs-lookup"><span data-stu-id="0129f-105">Windows 10, version 1703 (also called the Creators Update), introduces the following changes for Microsoft Surface Hub.</span></span>

## <span data-ttu-id="0129f-106">新設定</span><span class="sxs-lookup"><span data-stu-id="0129f-106">New settings</span></span>

<span data-ttu-id="0129f-107">設定已新增至行動裝置管理 (MDM) 和設定服務提供者 (CSP)，以擴大 Surface Hub 的管理功能。</span><span class="sxs-lookup"><span data-stu-id="0129f-107">Settings have been added to mobile device management (MDM) and configuration service providers (CSPs) to expand the Surface Hub management capabilities.</span></span> <span data-ttu-id="0129f-108">[新的設定包括](manage-settings-with-mdm-for-surface-hub.md)：</span><span class="sxs-lookup"><span data-stu-id="0129f-108">[New settings include](manage-settings-with-mdm-for-surface-hub.md):</span></span>

- <span data-ttu-id="0129f-109">InBoxApps/SkypeForBusiness/DomainName</span><span class="sxs-lookup"><span data-stu-id="0129f-109">InBoxApps/SkypeForBusiness/DomainName</span></span>
- <span data-ttu-id="0129f-110">InBoxApps/Connect/AutoLaunch</span><span class="sxs-lookup"><span data-stu-id="0129f-110">InBoxApps/Connect/AutoLaunch</span></span>
- <span data-ttu-id="0129f-111">Properties/DefaultVolume</span><span class="sxs-lookup"><span data-stu-id="0129f-111">Properties/DefaultVolume</span></span>
- <span data-ttu-id="0129f-112">Properties/ScreenTimeout</span><span class="sxs-lookup"><span data-stu-id="0129f-112">Properties/ScreenTimeout</span></span>
- <span data-ttu-id="0129f-113">Properties/SessionTimeout</span><span class="sxs-lookup"><span data-stu-id="0129f-113">Properties/SessionTimeout</span></span>
- <span data-ttu-id="0129f-114">Properties/SleepTimeout</span><span class="sxs-lookup"><span data-stu-id="0129f-114">Properties/SleepTimeout</span></span>
- <span data-ttu-id="0129f-115">Properties/AllowSessionResume</span><span class="sxs-lookup"><span data-stu-id="0129f-115">Properties/AllowSessionResume</span></span>
- <span data-ttu-id="0129f-116">Properties/AllowAutoProxyAuth</span><span class="sxs-lookup"><span data-stu-id="0129f-116">Properties/AllowAutoProxyAuth</span></span>
- <span data-ttu-id="0129f-117">Properties/DisableSigninSuggestions</span><span class="sxs-lookup"><span data-stu-id="0129f-117">Properties/DisableSigninSuggestions</span></span>
- <span data-ttu-id="0129f-118">Properties/DoNotShowMyMeetingsAndFiles</span><span class="sxs-lookup"><span data-stu-id="0129f-118">Properties/DoNotShowMyMeetingsAndFiles</span></span>
- <span data-ttu-id="0129f-119">System/AllowStorageCard</span><span class="sxs-lookup"><span data-stu-id="0129f-119">System/AllowStorageCard</span></span>

<span data-ttu-id="0129f-120">加號設定根據新的 [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) 和 [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp)。</span><span class="sxs-lookup"><span data-stu-id="0129f-120">Plus settings based on the new [NetworkQoSPolicy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkqospolicy-csp) and [NetworkProxy CSP](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/networkproxy-csp).</span></span>
</br>

## <span data-ttu-id="0129f-121">佈建精靈</span><span class="sxs-lookup"><span data-stu-id="0129f-121">Provisioning wizard</span></span>

<span data-ttu-id="0129f-122">簡單易用精靈可協助您快速建立佈建套件，供您套用至多個 Surface Hub 裝置，並且包括了大量加入 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="0129f-122">An easy-to-use wizard helps you quickly create provisioning packages that you can apply to multiple Surface Hub devices, and includes bulk join to Azure Active Directory.</span></span> [<span data-ttu-id="0129f-123">了解如何為 Surface Hub 建立佈建套件。</span><span class="sxs-lookup"><span data-stu-id="0129f-123">Learn how to create a provisioning package for Surface Hub.</span></span>](provisioning-packages-for-certificates-surface-hub.md)

![佈建 Surface Hub 裝置精靈中的步驟](images/wcd-wizard.png)
    
## <span data-ttu-id="0129f-125">您現有無線網路或區域網路上的 Miracast</span><span class="sxs-lookup"><span data-stu-id="0129f-125">Miracast on your existing wireless network or LAN</span></span> 

<span data-ttu-id="0129f-126">Microsoft 擴充了[透過區域網路傳送 Miracast 串流的能力](miracast-over-infrastructure.md)，而不是透過直接的無線連結。</span><span class="sxs-lookup"><span data-stu-id="0129f-126">Microsoft has extended the ability to [send a Miracast stream over a local network](miracast-over-infrastructure.md) rather than over a direct wireless link.</span></span> 
    
## <span data-ttu-id="0129f-127">雲端復原</span><span class="sxs-lookup"><span data-stu-id="0129f-127">Cloud recovery</span></span>

<span data-ttu-id="0129f-128">當您重設 Surface Hub 裝置時，您現在可以從雲端下載並安裝作業系統的原廠組建。</span><span class="sxs-lookup"><span data-stu-id="0129f-128">When you reset a Surface Hub device, you now have the ability to download and install a factory build of the operating system from the cloud.</span></span> [<span data-ttu-id="0129f-129">深入了解雲端復原。</span><span class="sxs-lookup"><span data-stu-id="0129f-129">Learn more about cloud recovery.</span></span>](device-reset-surface-hub.md#cloud-recovery)

>[!NOTE]
><span data-ttu-id="0129f-130">如果您使用的是 Proxy 伺服器，則無法使用雲端復原。</span><span class="sxs-lookup"><span data-stu-id="0129f-130">Cloud recovery doesn't work if you use proxy servers.</span></span>
    
![重新安裝](images/reinstall.png)
    
## <span data-ttu-id="0129f-132">結束工作階段</span><span class="sxs-lookup"><span data-stu-id="0129f-132">End session</span></span>

<span data-ttu-id="0129f-133">**[我已完成]** 現在已更名為 **[結束工作階段]**。</span><span class="sxs-lookup"><span data-stu-id="0129f-133">**I'm done** is now **End session**.</span></span> [<span data-ttu-id="0129f-134">了解如何使用 [結束工作階段]。</span><span class="sxs-lookup"><span data-stu-id="0129f-134">Learn how to use End session.</span></span>](i-am-done-finishing-your-surface-hub-meeting.md) 

![結束工作階段](images/end-session.png)



 

 
