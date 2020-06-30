---
title: 在 Surface Hub 上實現服務品質
ms.reviewer: ''
manager: laurawi
description: 瞭解如何在 Surface Hub 上設定 QoS。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 99172e77be260559c770f5fc8a1438734bed660f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831422"
---
# <span data-ttu-id="4e13c-103">在 Surface Hub 上實施服務品質（QoS）</span><span class="sxs-lookup"><span data-stu-id="4e13c-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="4e13c-104">服務品質（QoS）是網路技術的組合，可讓系統管理員優化即時音訊/視頻與應用程式共用通訊的體驗。</span><span class="sxs-lookup"><span data-stu-id="4e13c-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="4e13c-105">在 Surface Hub 上設定[商務用 Skype 的 QoS，](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)就可以使用行動[裝置管理（MDM）提供者](manage-settings-with-mdm-for-surface-hub.md)或[提供套件](provisioning-packages-for-surface-hub.md)來完成。</span><span class="sxs-lookup"><span data-stu-id="4e13c-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="4e13c-106">此程式說明如何使用 Microsoft Intune 設定 Surface Hub 的 QoS。</span><span class="sxs-lookup"><span data-stu-id="4e13c-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="4e13c-107">在 Intune 中，[建立自訂原則](https://docs.microsoft.com/intune/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="4e13c-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    ![Intune 中的 [自訂策略建立] 對話方塊的螢幕擷取畫面](images/qos-create.png)

2. <span data-ttu-id="4e13c-109">在 [**自訂 OMA URI 設定**] 中，選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4e13c-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="4e13c-110">針對您所新增的每個設定，您將會輸入名稱、描述（選擇性）、資料類型、OMA URI 及值。</span><span class="sxs-lookup"><span data-stu-id="4e13c-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    ![空白 [OMA URI 設定] 對話方塊的螢幕擷取畫面](images/qos-setting.png)

3. <span data-ttu-id="4e13c-112">新增下列自訂 OMA URI 設定：</span><span class="sxs-lookup"><span data-stu-id="4e13c-112">Add the following custom OMA-URI settings:</span></span>

    <span data-ttu-id="4e13c-113">名稱</span><span class="sxs-lookup"><span data-stu-id="4e13c-113">Name</span></span> | <span data-ttu-id="4e13c-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="4e13c-114">Data type</span></span> | <span data-ttu-id="4e13c-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="4e13c-115">OMA-URI</span></span><br><span data-ttu-id="4e13c-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="4e13c-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="4e13c-117">值</span><span class="sxs-lookup"><span data-stu-id="4e13c-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="4e13c-118">音訊來源埠</span><span class="sxs-lookup"><span data-stu-id="4e13c-118">Audio Source Port</span></span> | <span data-ttu-id="4e13c-119">字串</span><span class="sxs-lookup"><span data-stu-id="4e13c-119">String</span></span> |  <span data-ttu-id="4e13c-120">/HubAudio/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="4e13c-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="4e13c-121">從您的 Skype 系統管理員取得值</span><span class="sxs-lookup"><span data-stu-id="4e13c-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="4e13c-122">音效 DSCP</span><span class="sxs-lookup"><span data-stu-id="4e13c-122">Audio DSCP</span></span> | <span data-ttu-id="4e13c-123">整數</span><span class="sxs-lookup"><span data-stu-id="4e13c-123">Integer</span></span> |  <span data-ttu-id="4e13c-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="4e13c-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="4e13c-125">46</span><span class="sxs-lookup"><span data-stu-id="4e13c-125">46</span></span>
    <span data-ttu-id="4e13c-126">影片來源埠</span><span class="sxs-lookup"><span data-stu-id="4e13c-126">Video Source Port</span></span> | <span data-ttu-id="4e13c-127">字串</span><span class="sxs-lookup"><span data-stu-id="4e13c-127">String</span></span> |  <span data-ttu-id="4e13c-128">/HubVideo/SourcePortMatchCondition</span><span class="sxs-lookup"><span data-stu-id="4e13c-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="4e13c-129">從您的 Skype 系統管理員取得值</span><span class="sxs-lookup"><span data-stu-id="4e13c-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="4e13c-130">影片 DSCP</span><span class="sxs-lookup"><span data-stu-id="4e13c-130">Video DSCP</span></span> | <span data-ttu-id="4e13c-131">整數</span><span class="sxs-lookup"><span data-stu-id="4e13c-131">Integer</span></span> |  <span data-ttu-id="4e13c-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="4e13c-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="4e13c-133">34</span><span class="sxs-lookup"><span data-stu-id="4e13c-133">34</span></span>
    <span data-ttu-id="4e13c-134">音訊進程名稱</span><span class="sxs-lookup"><span data-stu-id="4e13c-134">Audio Process Name</span></span> | <span data-ttu-id="4e13c-135">字串</span><span class="sxs-lookup"><span data-stu-id="4e13c-135">String</span></span> |  <span data-ttu-id="4e13c-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="4e13c-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="4e13c-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="4e13c-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="4e13c-138">影片名稱</span><span class="sxs-lookup"><span data-stu-id="4e13c-138">Video Process Name</span></span> | <span data-ttu-id="4e13c-139">字串</span><span class="sxs-lookup"><span data-stu-id="4e13c-139">String</span></span> |  <span data-ttu-id="4e13c-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="4e13c-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="4e13c-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="4e13c-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="4e13c-142">每個**OMA URI**路徑都以開頭 `./Device/Vendor/MSFT/NetworkQoSPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="4e13c-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="4e13c-143">例如，[音訊來源埠] 設定的完整路徑就是 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。</span><span class="sxs-lookup"><span data-stu-id="4e13c-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>




4. <span data-ttu-id="4e13c-144">原則建立之後，[就可以將它部署到 Surface Hub。](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span><span class="sxs-lookup"><span data-stu-id="4e13c-144">When the policy has been created, [deploy it to the Surface Hub.](manage-settings-with-mdm-for-surface-hub.md#manage-surface-hub-settings-with-mdm)</span></span>


>[!WARNING]
><span data-ttu-id="4e13c-145">目前，您無法在[NETWORKQOSPOLICY CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)中設定設定**IPProtocolMatchCondition** 。</span><span class="sxs-lookup"><span data-stu-id="4e13c-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="4e13c-146">如果已設定此設定，原則將無法套用。</span><span class="sxs-lookup"><span data-stu-id="4e13c-146">If this setting is configured, the policy will fail to apply.</span></span>
 
