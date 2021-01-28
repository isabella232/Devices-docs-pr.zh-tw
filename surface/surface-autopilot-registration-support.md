---
title: 適用於 Windows Autopilot 的 Surface 註冊支援
description: 本文說明提交 Autopilot 註冊要求至 Microsoft 支援的需求。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: b31cacad5a744dcb29fc3dd2822c656d528fcd40
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304836"
---
# <span data-ttu-id="dab45-103">適用於 Windows Autopilot 的 Surface 註冊支援</span><span class="sxs-lookup"><span data-stu-id="dab45-103">Surface Registration Support for Windows Autopilot</span></span>

<span data-ttu-id="dab45-104">您現在可以在 Microsoft 支援中取得為 Windows Autopilot 部署註冊 Surface 裝置的簡化程式。</span><span class="sxs-lookup"><span data-stu-id="dab45-104">A simplified process of registering Surface devices for Windows Autopilot deployment is now available from Microsoft Support.</span></span> <span data-ttu-id="dab45-105">從2020年9月起，客戶與 Microsoft 雲端解決方案供應商 (Csp) 可以透過提交要求到 Microsoft 支援來註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="dab45-105">Beginning September 2020, customers and Microsoft Cloud Solution Providers (CSPs) can register Surface devices by submitting requests to Microsoft Support.</span></span> <span data-ttu-id="dab45-106">此頁面概述下列支援的 Autopilot 註冊案例的需求：</span><span class="sxs-lookup"><span data-stu-id="dab45-106">This page outlines the requirements for the following supported Autopilot registration scenarios:</span></span>
 
- <span data-ttu-id="dab45-107">**Surface Device Autopilot 註冊**。</span><span class="sxs-lookup"><span data-stu-id="dab45-107">**Surface Device Autopilot Registration**.</span></span> <span data-ttu-id="dab45-108">提交要求以在 Windows Autopilot 中註冊 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="dab45-108">Submits request to register Surface devices into Windows Autopilot.</span></span>
- **<span data-ttu-id="dab45-109">Surface 裝置硬體雜湊要求。</span><span class="sxs-lookup"><span data-stu-id="dab45-109">Surface Device Hardware Hash Request.</span></span>** <span data-ttu-id="dab45-110">提交 Microsoft 支援的要求，為您提供客戶或 Csp 可用來透過 Microsoft Intune 或 Microsoft 合作夥伴中心自行註冊裝置的硬體雜湊值。</span><span class="sxs-lookup"><span data-stu-id="dab45-110">Submits request to Microsoft Support to provide you with hardware hashes that customers or CSPs can use to self-register devices via Microsoft Intune or the Microsoft Partner Center.</span></span>
- **<span data-ttu-id="dab45-111">[Surface 裝置] Autopilot [取消註冊]。</span><span class="sxs-lookup"><span data-stu-id="dab45-111">Surface Device Autopilot Deregistration.</span></span>** <span data-ttu-id="dab45-112">提交從 Windows Autopilot 刪除裝置的要求，通常用於裝置的生命週期結束案例。</span><span class="sxs-lookup"><span data-stu-id="dab45-112">Submits request to delete devices from Windows Autopilot, typically used in device end of life scenarios.</span></span>

<span data-ttu-id="dab45-113">請參閱下表，瞭解在將註冊要求提交至 Microsoft 支援之前所需收集的資訊的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dab45-113">See the following table for details of the information you will need to collect prior to submitting registration requests to Microsoft Support.</span></span> <span data-ttu-id="dab45-114">如需所有 Surface 裝置的正式系統模型名稱，請參閱 [Surface SYSTEM SKU 參考](surface-system-sku-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="dab45-114">For the official System Model names of all Surface devices, refer to [Surface System SKU reference](surface-system-sku-reference.md).</span></span>
 
**<span data-ttu-id="dab45-115">表 1.</span><span class="sxs-lookup"><span data-stu-id="dab45-115">Table 1.</span></span> <span data-ttu-id="dab45-116">Autopilot 註冊要求所需的資訊</span><span class="sxs-lookup"><span data-stu-id="dab45-116">Required information for Autopilot registration requests</span></span>**
 

| <span data-ttu-id="dab45-117">必要資訊</span><span class="sxs-lookup"><span data-stu-id="dab45-117">Required information</span></span>                   | <span data-ttu-id="dab45-118">說明</span><span class="sxs-lookup"><span data-stu-id="dab45-118">Description</span></span>                                                                                                                                                                                                                                                                                    | <span data-ttu-id="dab45-119">Autopilot 註冊</span><span class="sxs-lookup"><span data-stu-id="dab45-119">Autopilot Registration</span></span> | <span data-ttu-id="dab45-120">硬體雜湊要求</span><span class="sxs-lookup"><span data-stu-id="dab45-120">Hardware Hash Request</span></span> | <span data-ttu-id="dab45-121">Autopilot</span><span class="sxs-lookup"><span data-stu-id="dab45-121">Autopilot</span></span><br><span data-ttu-id="dab45-122">登出</span><span class="sxs-lookup"><span data-stu-id="dab45-122">Deregistration</span></span> |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **<span data-ttu-id="dab45-123">Azure Active Directory 租使用者識別碼</span><span class="sxs-lookup"><span data-stu-id="dab45-123">Azure Active Directory Tenant ID</span></span>**   | <span data-ttu-id="dab45-124">您的 Azure Active Directory 租使用者識別碼是與您的組織名稱或網域不同 (GUID) 的全域唯一識別碼。</span><span class="sxs-lookup"><span data-stu-id="dab45-124">Your Azure Active Directory tenant ID is a globally unique identifier (GUID) that is different than your organization name or domain.</span></span><br> <br><span data-ttu-id="dab45-125">若要尋找您的租使用者識別碼，請在 [這裡](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)登入 Azure 入口網站。</span><span class="sxs-lookup"><span data-stu-id="dab45-125">To find your Tenant ID sign into the Azure Portal [here](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> | <span data-ttu-id="dab45-126">是</span><span class="sxs-lookup"><span data-stu-id="dab45-126">Y</span></span>                      | <span data-ttu-id="dab45-127">否</span><span class="sxs-lookup"><span data-stu-id="dab45-127">N</span></span>                     | <span data-ttu-id="dab45-128">是</span><span class="sxs-lookup"><span data-stu-id="dab45-128">Y</span></span>                           |
| **<span data-ttu-id="dab45-129">Azure Active Directory 網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="dab45-129">Azure Active Directory Domain Name</span></span>** | <span data-ttu-id="dab45-130">您最上層的功能變數名稱;例如，contoso.com。</span><span class="sxs-lookup"><span data-stu-id="dab45-130">Your top-level domain name; for example, contoso.com.</span></span>                                                                                                                                                                                                                                          | <span data-ttu-id="dab45-131">是</span><span class="sxs-lookup"><span data-stu-id="dab45-131">Y</span></span>                      | <span data-ttu-id="dab45-132">否</span><span class="sxs-lookup"><span data-stu-id="dab45-132">N</span></span>                     | <span data-ttu-id="dab45-133">是</span><span class="sxs-lookup"><span data-stu-id="dab45-133">Y</span></span>                           |
| **<span data-ttu-id="dab45-134">擁有權憑證</span><span class="sxs-lookup"><span data-stu-id="dab45-134">Proof of ownership</span></span>**                 | <span data-ttu-id="dab45-135">以 PDF 格式上傳原始的銷售帳單或發票，以驗證擁有權。</span><span class="sxs-lookup"><span data-stu-id="dab45-135">Verify proof of ownership by uploading the original bill of sale or invoice in PDF format.</span></span> <span data-ttu-id="dab45-136">螢幕擷取畫面不接受。</span><span class="sxs-lookup"><span data-stu-id="dab45-136">Screenshots are not accepted.</span></span><br> <br><span data-ttu-id="dab45-137">[帳單] 或 [發票] 必須包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="dab45-137">The bill of sale or invoice  must include the following:</span></span><br><span data-ttu-id="dab45-138">裝置序列值。</span><span class="sxs-lookup"><span data-stu-id="dab45-138">Device serial numbers.</span></span><br><span data-ttu-id="dab45-139">[公司名稱]。</span><span class="sxs-lookup"><span data-stu-id="dab45-139">Company name.</span></span>                                                           | <span data-ttu-id="dab45-140">是</span><span class="sxs-lookup"><span data-stu-id="dab45-140">Y</span></span>                      | <span data-ttu-id="dab45-141">是</span><span class="sxs-lookup"><span data-stu-id="dab45-141">Y</span></span>                     | <span data-ttu-id="dab45-142">是</span><span class="sxs-lookup"><span data-stu-id="dab45-142">Y</span></span>                           |
| **<span data-ttu-id="dab45-143">裝置序列值</span><span class="sxs-lookup"><span data-stu-id="dab45-143">Device serial numbers</span></span>**              | <span data-ttu-id="dab45-144">以 CSV 格式上傳 Excel 檔案，並在新的一行中使用每個裝置的序列值。</span><span class="sxs-lookup"><span data-stu-id="dab45-144">Upload Excel file in CSV format with each device serial number in a new line.</span></span>                                                                                                                                                                                                                  | <span data-ttu-id="dab45-145">是</span><span class="sxs-lookup"><span data-stu-id="dab45-145">Y</span></span>                      | <span data-ttu-id="dab45-146">是</span><span class="sxs-lookup"><span data-stu-id="dab45-146">Y</span></span>                     | <span data-ttu-id="dab45-147">是</span><span class="sxs-lookup"><span data-stu-id="dab45-147">Y</span></span>                           |

 

## <span data-ttu-id="dab45-148">提交支援要求</span><span class="sxs-lookup"><span data-stu-id="dab45-148">Submit support requests</span></span>

  [![G<span data-ttu-id="dab45-149">et Autopilot 註冊支援 Surface]</span><span class="sxs-lookup"><span data-stu-id="dab45-149">et Autopilot Registration Support for Surface]</span></span>(images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <span data-ttu-id="dab45-150">深入了解</span><span class="sxs-lookup"><span data-stu-id="dab45-150">Learn more</span></span>

- [<span data-ttu-id="dab45-151">Windows Autopilot 與 Surface 裝置</span><span class="sxs-lookup"><span data-stu-id="dab45-151">Windows Autopilot and Surface devices</span></span>](windows-autopilot-and-surface-devices.md)
- [<span data-ttu-id="dab45-152">使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置</span><span class="sxs-lookup"><span data-stu-id="dab45-152">Enroll Windows devices in Intune by using Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [<span data-ttu-id="dab45-153">Windows Autopilot 概觀</span><span class="sxs-lookup"><span data-stu-id="dab45-153">Overview of Windows Autopilot</span></span>](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [<span data-ttu-id="dab45-154">Surface 系統 SKU 參考</span><span class="sxs-lookup"><span data-stu-id="dab45-154">Surface System SKU reference</span></span>](surface-system-sku-reference.md)

 
 
 

