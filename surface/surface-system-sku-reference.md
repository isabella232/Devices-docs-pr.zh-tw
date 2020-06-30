---
title: 系統 SKU 參考（Surface）
description: 請參閱系統模型和系統 SKU 名稱的參考。
keywords: uefi、設定、固件、安全、semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 03/09/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 1fa192902b17ca811d4ecc8eac65abe1655ce370
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831515"
---
# <span data-ttu-id="cca1a-104">系統 SKU 參考</span><span class="sxs-lookup"><span data-stu-id="cca1a-104">System SKU reference</span></span>

<span data-ttu-id="cca1a-105">本檔提供系統模型和系統 SKU 名稱的參考，您可以使用 PowerShell 或 WMI 快速判斷特定裝置的電腦狀態。</span><span class="sxs-lookup"><span data-stu-id="cca1a-105">This document provides a reference of System Model and System SKU names that you can use to quickly determine the machine state of a specific device by using PowerShell or WMI.</span></span>

<span data-ttu-id="cca1a-106">系統模型和系統 SKU 是儲存在 Surface 裝置的 UEFI 層中系統管理 BIOS （SMBIOS）資料表中的變數。</span><span class="sxs-lookup"><span data-stu-id="cca1a-106">System Model and System SKU are variables that are stored in the System Management BIOS (SMBIOS) tables in the UEFI layer of Surface devices.</span></span> <span data-ttu-id="cca1a-107">必須有系統 SKU 名稱，才能區分具有相同系統模型名稱的裝置，例如 Surface Pro 以及含 LTE Advanced 的 Surface Pro。</span><span class="sxs-lookup"><span data-stu-id="cca1a-107">The System SKU name is required to differentiate between devices that have the same System Model name, such as Surface Pro and Surface Pro with LTE Advanced.</span></span> 

| <span data-ttu-id="cca1a-108">裝置</span><span class="sxs-lookup"><span data-stu-id="cca1a-108">Device</span></span>   | <span data-ttu-id="cca1a-109">系統模型</span><span class="sxs-lookup"><span data-stu-id="cca1a-109">System Model</span></span> | <span data-ttu-id="cca1a-110">系統 SKU</span><span class="sxs-lookup"><span data-stu-id="cca1a-110">System SKU</span></span>       |
| ---------- | ----------- | -------------- |
| <span data-ttu-id="cca1a-111">Surface 3 WiFI</span><span class="sxs-lookup"><span data-stu-id="cca1a-111">Surface 3 WiFI</span></span>                                               | <span data-ttu-id="cca1a-112">Surface 3</span><span class="sxs-lookup"><span data-stu-id="cca1a-112">Surface 3</span></span>        | <span data-ttu-id="cca1a-113">Surface_3</span><span class="sxs-lookup"><span data-stu-id="cca1a-113">Surface_3</span></span>                        |
| <span data-ttu-id="cca1a-114">&T 上的 Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="cca1a-114">Surface 3 LTE AT&T</span></span>                                           | <span data-ttu-id="cca1a-115">Surface 3</span><span class="sxs-lookup"><span data-stu-id="cca1a-115">Surface 3</span></span>        | <span data-ttu-id="cca1a-116">Surface_3_US1</span><span class="sxs-lookup"><span data-stu-id="cca1a-116">Surface_3_US1</span></span>                    |
| <span data-ttu-id="cca1a-117">Surface 3 LTE Verizon</span><span class="sxs-lookup"><span data-stu-id="cca1a-117">Surface 3 LTE Verizon</span></span>                                        | <span data-ttu-id="cca1a-118">Surface 3</span><span class="sxs-lookup"><span data-stu-id="cca1a-118">Surface 3</span></span>        | <span data-ttu-id="cca1a-119">Surface_3_US2</span><span class="sxs-lookup"><span data-stu-id="cca1a-119">Surface_3_US2</span></span>                    |
| <span data-ttu-id="cca1a-120">北美洲的 Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="cca1a-120">Surface 3 LTE North America</span></span>                                  | <span data-ttu-id="cca1a-121">Surface 3</span><span class="sxs-lookup"><span data-stu-id="cca1a-121">Surface 3</span></span>        | <span data-ttu-id="cca1a-122">Surface_3_NAG</span><span class="sxs-lookup"><span data-stu-id="cca1a-122">Surface_3_NAG</span></span>                    |
| <span data-ttu-id="cca1a-123">北美洲與 Y 之間的 Surface 3 LTE （在日本）移動</span><span class="sxs-lookup"><span data-stu-id="cca1a-123">Surface 3 LTE outside of North America and Y!mobile in Japan</span></span> | <span data-ttu-id="cca1a-124">Surface 3</span><span class="sxs-lookup"><span data-stu-id="cca1a-124">Surface 3</span></span>        | <span data-ttu-id="cca1a-125">Surface_3_ROW</span><span class="sxs-lookup"><span data-stu-id="cca1a-125">Surface_3_ROW</span></span>                    |
| <span data-ttu-id="cca1a-126">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="cca1a-126">Surface Pro</span></span>                                                  | <span data-ttu-id="cca1a-127">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="cca1a-127">Surface Pro</span></span>      | <span data-ttu-id="cca1a-128">Surface_Pro_1796</span><span class="sxs-lookup"><span data-stu-id="cca1a-128">Surface_Pro_1796</span></span>                 |
| <span data-ttu-id="cca1a-129">配備 LTE Advanced 的 Surface Pro</span><span class="sxs-lookup"><span data-stu-id="cca1a-129">Surface Pro with LTE Advanced</span></span>                                | <span data-ttu-id="cca1a-130">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="cca1a-130">Surface Pro</span></span>      | <span data-ttu-id="cca1a-131">Surface_Pro_1807</span><span class="sxs-lookup"><span data-stu-id="cca1a-131">Surface_Pro_1807</span></span>                 |
| <span data-ttu-id="cca1a-132">Surface Book 2 13 "</span><span class="sxs-lookup"><span data-stu-id="cca1a-132">Surface Book 2 13"</span></span>                                        | <span data-ttu-id="cca1a-133">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="cca1a-133">Surface Book 2</span></span>   | <span data-ttu-id="cca1a-134">Surface_Book_1832</span><span class="sxs-lookup"><span data-stu-id="cca1a-134">Surface_Book_1832</span></span>                |
| <span data-ttu-id="cca1a-135">Surface Book 2 15 "</span><span class="sxs-lookup"><span data-stu-id="cca1a-135">Surface Book 2 15"</span></span>                                        | <span data-ttu-id="cca1a-136">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="cca1a-136">Surface Book 2</span></span>   | <span data-ttu-id="cca1a-137">Surface_Book_1793</span><span class="sxs-lookup"><span data-stu-id="cca1a-137">Surface_Book_1793</span></span>                |
| <span data-ttu-id="cca1a-138">Surface Go LTE 消費者</span><span class="sxs-lookup"><span data-stu-id="cca1a-138">Surface Go LTE Consumer</span></span>  | <span data-ttu-id="cca1a-139">Surface Go</span><span class="sxs-lookup"><span data-stu-id="cca1a-139">Surface Go</span></span> | <span data-ttu-id="cca1a-140">Surface_Go_1825_Consumer</span><span class="sxs-lookup"><span data-stu-id="cca1a-140">Surface_Go_1825_Consumer</span></span> |
| <span data-ttu-id="cca1a-141">表面 [移至商業版]</span><span class="sxs-lookup"><span data-stu-id="cca1a-141">Surface Go LTE Commercial</span></span> | <span data-ttu-id="cca1a-142">系統移至</span><span class="sxs-lookup"><span data-stu-id="cca1a-142">System Go</span></span> | <span data-ttu-id="cca1a-143">Surface_Go_1825_Commercial</span><span class="sxs-lookup"><span data-stu-id="cca1a-143">Surface_Go_1825_Commercial</span></span> |
| <span data-ttu-id="cca1a-144">Surface Go 消費者</span><span class="sxs-lookup"><span data-stu-id="cca1a-144">Surface Go Consumer</span></span>                                          | <span data-ttu-id="cca1a-145">Surface Go</span><span class="sxs-lookup"><span data-stu-id="cca1a-145">Surface Go</span></span>       | <span data-ttu-id="cca1a-146">Surface_Go_1824_Consumer</span><span class="sxs-lookup"><span data-stu-id="cca1a-146">Surface_Go_1824_Consumer</span></span>         |
| <span data-ttu-id="cca1a-147">Surface 商業</span><span class="sxs-lookup"><span data-stu-id="cca1a-147">Surface Go Commercial</span></span>                                        | <span data-ttu-id="cca1a-148">Surface Go</span><span class="sxs-lookup"><span data-stu-id="cca1a-148">Surface Go</span></span>       | <span data-ttu-id="cca1a-149">Surface_Go_1824_Commercial</span><span class="sxs-lookup"><span data-stu-id="cca1a-149">Surface_Go_1824_Commercial</span></span>       |
| <span data-ttu-id="cca1a-150">Surface Pro 6 消費者</span><span class="sxs-lookup"><span data-stu-id="cca1a-150">Surface Pro 6 Consumer</span></span>                                       | <span data-ttu-id="cca1a-151">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="cca1a-151">Surface Pro 6</span></span>    | <span data-ttu-id="cca1a-152">Surface_Pro_6_1796_Consumer</span><span class="sxs-lookup"><span data-stu-id="cca1a-152">Surface_Pro_6_1796_Consumer</span></span>      |
| <span data-ttu-id="cca1a-153">Surface Pro 6 商業版</span><span class="sxs-lookup"><span data-stu-id="cca1a-153">Surface Pro 6 Commercial</span></span>                                     | <span data-ttu-id="cca1a-154">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="cca1a-154">Surface Pro 6</span></span>    | <span data-ttu-id="cca1a-155">Surface_Pro_6_1796_Commercial</span><span class="sxs-lookup"><span data-stu-id="cca1a-155">Surface_Pro_6_1796_Commercial</span></span>    |
| <span data-ttu-id="cca1a-156">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="cca1a-156">Surface Laptop</span></span>                                               | <span data-ttu-id="cca1a-157">Surface 膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="cca1a-157">Surface Laptop</span></span>   | <span data-ttu-id="cca1a-158">Surface_Laptop</span><span class="sxs-lookup"><span data-stu-id="cca1a-158">Surface_Laptop</span></span>                   |
| <span data-ttu-id="cca1a-159">Surface 膝上型電腦2消費者</span><span class="sxs-lookup"><span data-stu-id="cca1a-159">Surface Laptop 2 Consumer</span></span>                                    | <span data-ttu-id="cca1a-160">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="cca1a-160">Surface Laptop 2</span></span> | <span data-ttu-id="cca1a-161">Surface_Laptop_2_1769_Consumer</span><span class="sxs-lookup"><span data-stu-id="cca1a-161">Surface_Laptop_2_1769_Consumer</span></span>   |
| <span data-ttu-id="cca1a-162">Surface 膝上型電腦2商業版</span><span class="sxs-lookup"><span data-stu-id="cca1a-162">Surface Laptop 2 Commercial</span></span>                                  | <span data-ttu-id="cca1a-163">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="cca1a-163">Surface Laptop 2</span></span> | <span data-ttu-id="cca1a-164">Surface_Laptop_2_1769_Commercial</span><span class="sxs-lookup"><span data-stu-id="cca1a-164">Surface_Laptop_2_1769_Commercial</span></span> |
| <span data-ttu-id="cca1a-165">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="cca1a-165">Surface Pro 7</span></span>                 | <span data-ttu-id="cca1a-166">Surface Pro 7</span><span class="sxs-lookup"><span data-stu-id="cca1a-166">Surface Pro 7</span></span>    | <span data-ttu-id="cca1a-167">Surface_Pro_7_1866</span><span class="sxs-lookup"><span data-stu-id="cca1a-167">Surface_Pro_7_1866</span></span>         |
| <span data-ttu-id="cca1a-168">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="cca1a-168">Surface Pro X</span></span>                 | <span data-ttu-id="cca1a-169">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="cca1a-169">Surface Pro X</span></span>    | <span data-ttu-id="cca1a-170">Surface_Pro_X_1876</span><span class="sxs-lookup"><span data-stu-id="cca1a-170">Surface_Pro_X_1876</span></span>         |
| <span data-ttu-id="cca1a-171">Surface 膝上型電腦 3 13 "英特爾</span><span class="sxs-lookup"><span data-stu-id="cca1a-171">Surface Laptop 3 13" Intel</span></span> | <span data-ttu-id="cca1a-172">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="cca1a-172">Surface Laptop 3</span></span> | <span data-ttu-id="cca1a-173">Surface_Laptop_3_1867：1868</span><span class="sxs-lookup"><span data-stu-id="cca1a-173">Surface_Laptop_3_1867:1868</span></span> |
| <span data-ttu-id="cca1a-174">Surface 膝上型電腦 3 15 "英特爾</span><span class="sxs-lookup"><span data-stu-id="cca1a-174">Surface Laptop 3 15" Intel</span></span> | <span data-ttu-id="cca1a-175">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="cca1a-175">Surface Laptop 3</span></span> | <span data-ttu-id="cca1a-176">Surface_Laptop_3_1872</span><span class="sxs-lookup"><span data-stu-id="cca1a-176">Surface_Laptop_3_1872</span></span>      |
| <span data-ttu-id="cca1a-177">Surface 膝上型電腦 3 15 "AMD</span><span class="sxs-lookup"><span data-stu-id="cca1a-177">Surface Laptop 3 15" AMD</span></span>   | <span data-ttu-id="cca1a-178">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="cca1a-178">Surface Laptop 3</span></span> | <span data-ttu-id="cca1a-179">Surface_Laptop_3_1873</span><span class="sxs-lookup"><span data-stu-id="cca1a-179">Surface_Laptop_3_1873</span></span>      | 

## <span data-ttu-id="cca1a-180">範例</span><span class="sxs-lookup"><span data-stu-id="cca1a-180">Examples</span></span> 

**<span data-ttu-id="cca1a-181">使用 PowerShell 來檢索 SKU</span><span class="sxs-lookup"><span data-stu-id="cca1a-181">Retrieving the SKU by using PowerShell</span></span>**  
<span data-ttu-id="cca1a-182">使用下列 PowerShell 命令來提取系統 SKU 資訊：</span><span class="sxs-lookup"><span data-stu-id="cca1a-182">Use the following PowerShell command to pull the System SKU information:</span></span>

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**<span data-ttu-id="cca1a-183">使用系統資訊來檢索 SKU</span><span class="sxs-lookup"><span data-stu-id="cca1a-183">Retrieving the SKU by using System Information</span></span>**  
<span data-ttu-id="cca1a-184">您也可以在 [**系統資訊**] 中找到裝置的系統 SKU 和系統模型。</span><span class="sxs-lookup"><span data-stu-id="cca1a-184">You can also find the System SKU and System Model for a device in **System Information**.</span></span> <span data-ttu-id="cca1a-185">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cca1a-185">To do this, follow these steps:</span></span>

1. <span data-ttu-id="cca1a-186">選取 [**開始**]，然後在搜尋方塊中輸入 [ **MSInfo32** ]。</span><span class="sxs-lookup"><span data-stu-id="cca1a-186">Select **Start**, and then type **MSInfo32** in the search box.</span></span>  
1. <span data-ttu-id="cca1a-187">選取 [**系統資訊**]。</span><span class="sxs-lookup"><span data-stu-id="cca1a-187">Select **System Information**.</span></span>

**<span data-ttu-id="cca1a-188">在任務序列中使用 SKU WMI 條件</span><span class="sxs-lookup"><span data-stu-id="cca1a-188">Using the SKU in a task sequence WMI condition</span></span>**  
<span data-ttu-id="cca1a-189">您可以在 Microsoft 部署工具組（MDT）或 Microsoft 端點設定管理員中使用系統 SKU 資訊，做為「任務序列 WMI」條件的一部分。</span><span class="sxs-lookup"><span data-stu-id="cca1a-189">You can use the System SKU information in the Microsoft Deployment Toolkit (MDT) or Microsoft Endpoint Configuration Manager as part of a task sequence WMI condition.</span></span>

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
