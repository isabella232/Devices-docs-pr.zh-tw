---
title: Surface 系統 SKU 參考
description: 本主題提供系統 SKU 名稱的參考，您可以用來快速判斷特定裝置的電腦狀態。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831400"
---
# <span data-ttu-id="aba85-103">Surface System SKU 參考</span><span class="sxs-lookup"><span data-stu-id="aba85-103">Surface System SKU Reference</span></span>
<span data-ttu-id="aba85-104">本檔提供系統 SKU 名稱的參考，您可以使用 PowerShell、WMI 及相關工具快速判斷特定裝置的電腦狀態。</span><span class="sxs-lookup"><span data-stu-id="aba85-104">This document provides a reference of System SKU names that you can use to quickly determine the machine state of a specific device using PowerShell, WMI, and related tools.</span></span> 

<span data-ttu-id="aba85-105">系統 SKU 是儲存在 Surface 裝置的 UEFI 層中系統管理 BIOS （SMBIOS）資料表中的變數（以及系統模型及其他元件）。</span><span class="sxs-lookup"><span data-stu-id="aba85-105">System SKU is a variable (along with System Model and others) stored in System Management BIOS (SMBIOS) tables in the UEFI layer of Surface devices.</span></span>  <span data-ttu-id="aba85-106">每當您需要區分具有相同系統模型名稱（例如 Surface Pro 和 Surface Pro）與 LTE Advanced 的裝置時，請使用系統 SKU 名稱。</span><span class="sxs-lookup"><span data-stu-id="aba85-106">Use the System SKU name whenever you need to differentiate between devices with the same System Model name, such as Surface Pro and Surface Pro with LTE Advanced.</span></span> 

| **<span data-ttu-id="aba85-107">裝置</span><span class="sxs-lookup"><span data-stu-id="aba85-107">Device</span></span>**| **<span data-ttu-id="aba85-108">系統模型</span><span class="sxs-lookup"><span data-stu-id="aba85-108">System Model</span></span>** | **<span data-ttu-id="aba85-109">系統 SKU</span><span class="sxs-lookup"><span data-stu-id="aba85-109">System SKU</span></span>**|
| --- | ---| --- |
| <span data-ttu-id="aba85-110">Surface 3 WiFI</span><span class="sxs-lookup"><span data-stu-id="aba85-110">Surface 3 WiFI</span></span>                                               | <span data-ttu-id="aba85-111">Surface 3</span><span class="sxs-lookup"><span data-stu-id="aba85-111">Surface 3</span></span>        | <span data-ttu-id="aba85-112">Surface_3</span><span class="sxs-lookup"><span data-stu-id="aba85-112">Surface_3</span></span>                        |
| <span data-ttu-id="aba85-113">&T 上的 Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="aba85-113">Surface 3 LTE AT&T</span></span>                                           | <span data-ttu-id="aba85-114">Surface 3</span><span class="sxs-lookup"><span data-stu-id="aba85-114">Surface 3</span></span>        | <span data-ttu-id="aba85-115">Surface_3_US1</span><span class="sxs-lookup"><span data-stu-id="aba85-115">Surface_3_US1</span></span>                    |
| <span data-ttu-id="aba85-116">Surface 3 LTE Verizon</span><span class="sxs-lookup"><span data-stu-id="aba85-116">Surface 3 LTE Verizon</span></span>                                        | <span data-ttu-id="aba85-117">Surface 3</span><span class="sxs-lookup"><span data-stu-id="aba85-117">Surface 3</span></span>        | <span data-ttu-id="aba85-118">Surface_3_US2</span><span class="sxs-lookup"><span data-stu-id="aba85-118">Surface_3_US2</span></span>                    |
| <span data-ttu-id="aba85-119">北美洲的 Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="aba85-119">Surface 3 LTE North America</span></span>                                  | <span data-ttu-id="aba85-120">Surface 3</span><span class="sxs-lookup"><span data-stu-id="aba85-120">Surface 3</span></span>        | <span data-ttu-id="aba85-121">Surface_3_NAG</span><span class="sxs-lookup"><span data-stu-id="aba85-121">Surface_3_NAG</span></span>                    |
| <span data-ttu-id="aba85-122">在北美與 T-Mobile 外部的 Surface 3 LTE</span><span class="sxs-lookup"><span data-stu-id="aba85-122">Surface 3 LTE Outside of North America and T-Mobile In Japan</span></span> | <span data-ttu-id="aba85-123">Surface 3</span><span class="sxs-lookup"><span data-stu-id="aba85-123">Surface 3</span></span>        | <span data-ttu-id="aba85-124">Surface_3_ROW</span><span class="sxs-lookup"><span data-stu-id="aba85-124">Surface_3_ROW</span></span>                    |
| <span data-ttu-id="aba85-125">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="aba85-125">Surface Pro</span></span>                                                  | <span data-ttu-id="aba85-126">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="aba85-126">Surface Pro</span></span>      | <span data-ttu-id="aba85-127">Surface_Pro_1796</span><span class="sxs-lookup"><span data-stu-id="aba85-127">Surface_Pro_1796</span></span>                 |
| <span data-ttu-id="aba85-128">配備 LTE Advanced 的 Surface Pro</span><span class="sxs-lookup"><span data-stu-id="aba85-128">Surface Pro with LTE Advanced</span></span>                                | <span data-ttu-id="aba85-129">Surface Pro</span><span class="sxs-lookup"><span data-stu-id="aba85-129">Surface Pro</span></span>      | <span data-ttu-id="aba85-130">Surface_Pro_1807</span><span class="sxs-lookup"><span data-stu-id="aba85-130">Surface_Pro_1807</span></span>                 |
| <span data-ttu-id="aba85-131">Surface Book 2 13inch</span><span class="sxs-lookup"><span data-stu-id="aba85-131">Surface Book 2 13inch</span></span>                                        | <span data-ttu-id="aba85-132">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="aba85-132">Surface Book 2</span></span>   | <span data-ttu-id="aba85-133">Surface_Book_1832</span><span class="sxs-lookup"><span data-stu-id="aba85-133">Surface_Book_1832</span></span>                |
| <span data-ttu-id="aba85-134">Surface Book 2 15inch</span><span class="sxs-lookup"><span data-stu-id="aba85-134">Surface Book 2 15inch</span></span>                                        | <span data-ttu-id="aba85-135">Surface Book 2</span><span class="sxs-lookup"><span data-stu-id="aba85-135">Surface Book 2</span></span>   | <span data-ttu-id="aba85-136">Surface_Book_1793</span><span class="sxs-lookup"><span data-stu-id="aba85-136">Surface_Book_1793</span></span>                |
| <span data-ttu-id="aba85-137">Surface Go 消費者</span><span class="sxs-lookup"><span data-stu-id="aba85-137">Surface Go Consumer</span></span>                                          | <span data-ttu-id="aba85-138">Surface Go</span><span class="sxs-lookup"><span data-stu-id="aba85-138">Surface Go</span></span>       | <span data-ttu-id="aba85-139">Surface_Go_1824_Consumer</span><span class="sxs-lookup"><span data-stu-id="aba85-139">Surface_Go_1824_Consumer</span></span>         |
| <span data-ttu-id="aba85-140">Surface 商業</span><span class="sxs-lookup"><span data-stu-id="aba85-140">Surface Go Commercial</span></span>                                        | <span data-ttu-id="aba85-141">Surface Go</span><span class="sxs-lookup"><span data-stu-id="aba85-141">Surface Go</span></span>       | <span data-ttu-id="aba85-142">Surface_Go_1824_Commercial</span><span class="sxs-lookup"><span data-stu-id="aba85-142">Surface_Go_1824_Commercial</span></span>       |
| <span data-ttu-id="aba85-143">表面移2</span><span class="sxs-lookup"><span data-stu-id="aba85-143">Surface Go 2</span></span>                                                 | <span data-ttu-id="aba85-144">表面移2</span><span class="sxs-lookup"><span data-stu-id="aba85-144">Surface Go 2</span></span>     | <span data-ttu-id="aba85-145">Surface_Go_2_1927</span><span class="sxs-lookup"><span data-stu-id="aba85-145">Surface_Go_2_1927</span></span>                |
| <span data-ttu-id="aba85-146">Surface Pro 6 消費者</span><span class="sxs-lookup"><span data-stu-id="aba85-146">Surface Pro 6 Consumer</span></span>                                       | <span data-ttu-id="aba85-147">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="aba85-147">Surface Pro 6</span></span>    | <span data-ttu-id="aba85-148">Surface_Pro_6_1796_Consumer</span><span class="sxs-lookup"><span data-stu-id="aba85-148">Surface_Pro_6_1796_Consumer</span></span>      |
| <span data-ttu-id="aba85-149">Surface Pro 6 商業版</span><span class="sxs-lookup"><span data-stu-id="aba85-149">Surface Pro 6 Commercial</span></span>                                     | <span data-ttu-id="aba85-150">Surface Pro 6</span><span class="sxs-lookup"><span data-stu-id="aba85-150">Surface Pro 6</span></span>    | <span data-ttu-id="aba85-151">Surface_Pro_6_1796_Commercial</span><span class="sxs-lookup"><span data-stu-id="aba85-151">Surface_Pro_6_1796_Commercial</span></span>    |
| <span data-ttu-id="aba85-152">Surface 膝上型電腦2消費者</span><span class="sxs-lookup"><span data-stu-id="aba85-152">Surface Laptop 2 Consumer</span></span>                                    | <span data-ttu-id="aba85-153">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="aba85-153">Surface Laptop 2</span></span> | <span data-ttu-id="aba85-154">Surface_Laptop_2_1769_Consumer</span><span class="sxs-lookup"><span data-stu-id="aba85-154">Surface_Laptop_2_1769_Consumer</span></span>   |
| <span data-ttu-id="aba85-155">Surface 膝上型電腦2商業版</span><span class="sxs-lookup"><span data-stu-id="aba85-155">Surface Laptop 2 Commercial</span></span>                                  | <span data-ttu-id="aba85-156">Surface Laptop 2</span><span class="sxs-lookup"><span data-stu-id="aba85-156">Surface Laptop 2</span></span> | <span data-ttu-id="aba85-157">Surface_Laptop_2_1769_Commercial</span><span class="sxs-lookup"><span data-stu-id="aba85-157">Surface_Laptop_2_1769_Commercial</span></span> |

## <span data-ttu-id="aba85-158">使用系統 SKU 變數</span><span class="sxs-lookup"><span data-stu-id="aba85-158">Using System SKU variables</span></span> 

### <span data-ttu-id="aba85-159">PowerShell</span><span class="sxs-lookup"><span data-stu-id="aba85-159">PowerShell</span></span>

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### <span data-ttu-id="aba85-160">系統資訊</span><span class="sxs-lookup"><span data-stu-id="aba85-160">System Information</span></span>
<span data-ttu-id="aba85-161">您也可以在 [系統資訊] 中找到裝置的系統 SKU 和系統模型。</span><span class="sxs-lookup"><span data-stu-id="aba85-161">You can also find the System SKU and System Model for a device in System Information.</span></span> 
- <span data-ttu-id="aba85-162">按一下 [**開始**  >   **MSInfo32**]。</span><span class="sxs-lookup"><span data-stu-id="aba85-162">Click **Start** >  **MSInfo32**.</span></span>  

### <span data-ttu-id="aba85-163">CIM</span><span class="sxs-lookup"><span data-stu-id="aba85-163">WMI</span></span>
<span data-ttu-id="aba85-164">您可以在 Microsoft 部署工具套件（MDT）或 Microsoft 端點設定管理員的 [任務序列] 中，使用「系統 SKU 變數」 WMI 條件。</span><span class="sxs-lookup"><span data-stu-id="aba85-164">You can use System SKU variables in a Task Sequence WMI Condition in the Microsoft Deployment Toolkit (MDT) or Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="aba85-165">例如：</span><span class="sxs-lookup"><span data-stu-id="aba85-165">For example:</span></span> 

    - <span data-ttu-id="aba85-166">WMI 命名空間-Root\WMI</span><span class="sxs-lookup"><span data-stu-id="aba85-166">WMI Namespace – Root\WMI</span></span>
    - <span data-ttu-id="aba85-167">WQL 查詢–從 MS_SystemInformation 中選取 [\*]，SystemSKU = "Surface_Pro_1796"</span><span class="sxs-lookup"><span data-stu-id="aba85-167">WQL Query – SELECT \* FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"</span></span>

 
 
 


