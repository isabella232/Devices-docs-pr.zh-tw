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
ms.date: 03/25/2021
ms.localizationpriority: medium
ms.openlocfilehash: 32d7493dc4a76b8e7642b927ec5db41a1e697b2a
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470481"
---
# <a name="implement-quality-of-service-qos-on-surface-hub"></a><span data-ttu-id="50d9d-103">在 Surface Hub 上 (QoS) 服務品質</span><span class="sxs-lookup"><span data-stu-id="50d9d-103">Implement Quality of Service (QoS) on Surface Hub</span></span>

<span data-ttu-id="50d9d-104">QoS (服務品質) 是網路技術的組合，可讓系統管理員優化即時音訊/視訊和應用程式共用通訊的體驗。</span><span class="sxs-lookup"><span data-stu-id="50d9d-104">Quality of Service (QoS) is a combination of network technologies that allows the administrators to optimize the experience of real time audio/video and application sharing communications.</span></span>
 
<span data-ttu-id="50d9d-105">您可以在 Surface Hub 上使用行動裝置管理或透過 MDM (或) 套件，在 Surface Hub 上配置商務用[Skype](manage-settings-with-mdm-for-surface-hub.md) [的](provisioning-packages-for-surface-hub.md) [QoS。](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)</span><span class="sxs-lookup"><span data-stu-id="50d9d-105">Configuring [QoS for Skype for Business](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp) on the Surface Hub can be done using your [mobile device management (MDM) provider](manage-settings-with-mdm-for-surface-hub.md) or through a [provisioning package](provisioning-packages-for-surface-hub.md).</span></span> 
 
 
<span data-ttu-id="50d9d-106">此程式說明如何使用 Microsoft Intune 設定 Surface Hub 的 QoS。</span><span class="sxs-lookup"><span data-stu-id="50d9d-106">This procedure explains how to configure QoS for Surface Hub using Microsoft Intune.</span></span> 

1. <span data-ttu-id="50d9d-107">在 Intune 中 [，建立自訂策略](https://docs.microsoft.com/intune/custom-settings-configure)。</span><span class="sxs-lookup"><span data-stu-id="50d9d-107">In Intune, [create a custom policy](https://docs.microsoft.com/intune/custom-settings-configure).</span></span>

    > [!div class="mx-imgBorder"]
    > ![Intune 中自訂策略建立對話方塊的螢幕擷取畫面](images/qos-create.png)

2. <span data-ttu-id="50d9d-109">在 **自訂 OMA-URI 設定**中 **，選取**新增 。</span><span class="sxs-lookup"><span data-stu-id="50d9d-109">In **Custom OMA-URI Settings**, select **Add**.</span></span> <span data-ttu-id="50d9d-110">針對您新增的每個設定，您將輸入名稱、描述 (選項) 資料類型、OMA-URI 和值。</span><span class="sxs-lookup"><span data-stu-id="50d9d-110">For each setting that you add, you will enter a name, description (optional), data type, OMA-URI, and value.</span></span>

    > [!div class="mx-imgBorder"]
    > ![空白 OMA-URI 設定對話方塊的螢幕擷取畫面](images/qos-setting.png)

3. <span data-ttu-id="50d9d-112">新增下列自訂 OMA-URI 設定：</span><span class="sxs-lookup"><span data-stu-id="50d9d-112">Add the following custom OMA-URI settings:</span></span><br/><br/>

    <span data-ttu-id="50d9d-113">名稱</span><span class="sxs-lookup"><span data-stu-id="50d9d-113">Name</span></span> | <span data-ttu-id="50d9d-114">資料類型</span><span class="sxs-lookup"><span data-stu-id="50d9d-114">Data type</span></span> | <span data-ttu-id="50d9d-115">OMA-URI</span><span class="sxs-lookup"><span data-stu-id="50d9d-115">OMA-URI</span></span><br><span data-ttu-id="50d9d-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span><span class="sxs-lookup"><span data-stu-id="50d9d-116">./Device/Vendor/MSFT/NetworkQoSPolicy</span></span> |  <span data-ttu-id="50d9d-117">值</span><span class="sxs-lookup"><span data-stu-id="50d9d-117">Value</span></span>
    --- | --- | --- | ---
    <span data-ttu-id="50d9d-118">音訊來源埠</span><span class="sxs-lookup"><span data-stu-id="50d9d-118">Audio Source Port</span></span> | <span data-ttu-id="50d9d-119">字串</span><span class="sxs-lookup"><span data-stu-id="50d9d-119">String</span></span> |  <span data-ttu-id="50d9d-120">/HubAudio/SourcePortchCondition</span><span class="sxs-lookup"><span data-stu-id="50d9d-120">/HubAudio/SourcePortMatchCondition</span></span>  |   <span data-ttu-id="50d9d-121">從 Skype 系統管理員取得值</span><span class="sxs-lookup"><span data-stu-id="50d9d-121">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="50d9d-122">音效 DSCP</span><span class="sxs-lookup"><span data-stu-id="50d9d-122">Audio DSCP</span></span> | <span data-ttu-id="50d9d-123">整數</span><span class="sxs-lookup"><span data-stu-id="50d9d-123">Integer</span></span> |  <span data-ttu-id="50d9d-124">/HubAudio/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="50d9d-124">/HubAudio/DSCPAction</span></span>  |   <span data-ttu-id="50d9d-125">46</span><span class="sxs-lookup"><span data-stu-id="50d9d-125">46</span></span>
    <span data-ttu-id="50d9d-126">視音訊來源埠</span><span class="sxs-lookup"><span data-stu-id="50d9d-126">Video Source Port</span></span> | <span data-ttu-id="50d9d-127">字串</span><span class="sxs-lookup"><span data-stu-id="50d9d-127">String</span></span> |  <span data-ttu-id="50d9d-128">/HubVideo/SourcePortchCondition</span><span class="sxs-lookup"><span data-stu-id="50d9d-128">/HubVideo/SourcePortMatchCondition</span></span>   |  <span data-ttu-id="50d9d-129">從 Skype 系統管理員取得值</span><span class="sxs-lookup"><span data-stu-id="50d9d-129">Get the values from your Skype administrator</span></span>
    <span data-ttu-id="50d9d-130">影片 DSCP</span><span class="sxs-lookup"><span data-stu-id="50d9d-130">Video DSCP</span></span> | <span data-ttu-id="50d9d-131">整數</span><span class="sxs-lookup"><span data-stu-id="50d9d-131">Integer</span></span> |  <span data-ttu-id="50d9d-132">/HubVideo/DSCPAction</span><span class="sxs-lookup"><span data-stu-id="50d9d-132">/HubVideo/DSCPAction</span></span>   |   <span data-ttu-id="50d9d-133">34</span><span class="sxs-lookup"><span data-stu-id="50d9d-133">34</span></span>
    <span data-ttu-id="50d9d-134">音訊程式名稱</span><span class="sxs-lookup"><span data-stu-id="50d9d-134">Audio Process Name</span></span> | <span data-ttu-id="50d9d-135">字串</span><span class="sxs-lookup"><span data-stu-id="50d9d-135">String</span></span> |  <span data-ttu-id="50d9d-136">/HubAudio/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="50d9d-136">/HubAudio/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="50d9d-137">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="50d9d-137">Microsoft.PPISkype.Windows.exe</span></span>
    <span data-ttu-id="50d9d-138">視音訊程式名稱</span><span class="sxs-lookup"><span data-stu-id="50d9d-138">Video Process Name</span></span> | <span data-ttu-id="50d9d-139">字串</span><span class="sxs-lookup"><span data-stu-id="50d9d-139">String</span></span> |  <span data-ttu-id="50d9d-140">/HubVideo/AppPathNameMatchCondition</span><span class="sxs-lookup"><span data-stu-id="50d9d-140">/HubVideo/AppPathNameMatchCondition</span></span>  |   <span data-ttu-id="50d9d-141">Microsoft.PPISkype.Windows.exe</span><span class="sxs-lookup"><span data-stu-id="50d9d-141">Microsoft.PPISkype.Windows.exe</span></span>

    >[!IMPORTANT]
    ><span data-ttu-id="50d9d-142">每個 **OMA-URI** 路徑的開頭為 `./Device/Vendor/MSFT/NetworkQoSPolicy` 。</span><span class="sxs-lookup"><span data-stu-id="50d9d-142">Each **OMA-URI** path begins with `./Device/Vendor/MSFT/NetworkQoSPolicy`.</span></span> <span data-ttu-id="50d9d-143">例如，音訊來源埠設定的完整路徑為 `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition` 。</span><span class="sxs-lookup"><span data-stu-id="50d9d-143">The full path for the audio source port setting, for example, will be `./Device/Vendor/MSFT/NetworkQoSPolicy/HubAudio/SourcePortMatchCondition`.</span></span>

4. <span data-ttu-id="50d9d-144">建立該策略後，請將其部署到 Surface Hub。</span><span class="sxs-lookup"><span data-stu-id="50d9d-144">When the policy has been created, deploy it to Surface Hub.</span></span>


>[!WARNING]
><span data-ttu-id="50d9d-145">目前，您無法在[NetworkQoSPolicy](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp)CSP 中設定**IPProtocolMatchCondition** 。</span><span class="sxs-lookup"><span data-stu-id="50d9d-145">Currently, you cannot configure the setting **IPProtocolMatchCondition** in the [NetworkQoSPolicy CSP](https://docs.microsoft.com/windows/client-management/mdm/networkqospolicy-csp).</span></span> <span data-ttu-id="50d9d-146">如果已設定此設定，原則將無法適用。</span><span class="sxs-lookup"><span data-stu-id="50d9d-146">If this setting is configured, the policy will fail to apply.</span></span>
 
