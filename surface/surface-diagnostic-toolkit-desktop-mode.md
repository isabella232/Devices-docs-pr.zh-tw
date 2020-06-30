---
title: 在桌面模式中使用商務用 Surface 診斷工具組
description: 如何使用 SDT 來協助貴組織中的使用者執行該工具，以找出並診斷 Surface 裝置的問題。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 9e6b34a8d34081fc12cab4851104f0b67c3dfea4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831191"
---
# <span data-ttu-id="69621-103">在桌面模式中使用商務用 Surface 診斷工具組</span><span class="sxs-lookup"><span data-stu-id="69621-103">Use Surface Diagnostic Toolkit for Business in desktop mode</span></span>

<span data-ttu-id="69621-104">本主題說明如何使用 Surface 診斷工具箱（SDT），協助貴組織中的使用者執行該工具，以找出並診斷 Surface 裝置的問題。</span><span class="sxs-lookup"><span data-stu-id="69621-104">This topic explains how to use the Surface Diagnostic Toolkit (SDT) to help users in your organization run the tool to identify and diagnose issues with the Surface device.</span></span> <span data-ttu-id="69621-105">成功執行 SDT 可以快速判斷問題是否是由失敗的硬體或使用者錯誤所導致。</span><span class="sxs-lookup"><span data-stu-id="69621-105">Successfully running SDT can quickly determine if a reported issue is caused by failed hardware or user error.</span></span> <span data-ttu-id="69621-106">如需在 SDT 中支援的 Surface 裝置清單，請參閱適用于[企業的部署表面診斷工具](surface-diagnostic-toolkit-business.md)組。</span><span class="sxs-lookup"><span data-stu-id="69621-106">For a list of supported Surface devices in SDT, refer to [Deploy Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-business.md).</span></span>


1. <span data-ttu-id="69621-107">引導使用者從軟體發佈點或網路共用安裝[SDT 套件](surface-diagnostic-toolkit-business.md#create-custom-sdt)。</span><span class="sxs-lookup"><span data-stu-id="69621-107">Direct the user to install [the SDT package](surface-diagnostic-toolkit-business.md#create-custom-sdt) from a software distribution point or network share.</span></span> <span data-ttu-id="69621-108">安裝完成後，您就可以透過一系列測試來引導使用者。</span><span class="sxs-lookup"><span data-stu-id="69621-108">After it is installed, you’re ready to guide the user through a series of tests.</span></span> 

2. <span data-ttu-id="69621-109">從首頁開始，讓使用者輸入問題的描述，然後按一下 [**繼續**]，如圖1所示。</span><span class="sxs-lookup"><span data-stu-id="69621-109">Begin at the home page, which allows users to enter a description of the issue, and click **Continue**, as shown in figure 1.</span></span>

    ![<span data-ttu-id="69621-110">在桌面圖案中開始 SDT ](images/sdt-desk-1.png)
 *圖1。桌面圖案中的 SDT*</span><span class="sxs-lookup"><span data-stu-id="69621-110">Start SDT in desktop mode](images/sdt-desk-1.png)
*Figure 1. SDT in desktop mode*</span></span>

3. <span data-ttu-id="69621-111">當 SDT 代表裝置有最新的更新時，請按一下 [**繼續**] 以移至可用測試的目錄，如圖2所示。</span><span class="sxs-lookup"><span data-stu-id="69621-111">When SDT indicates the device has the latest updates, click **Continue** to advance to the catalog of available tests, as shown in figure 2.</span></span>

    ![<span data-ttu-id="69621-112">從 SDT 選項中選取 ](images/sdt-desk-2.png)
 *圖2。從 SDT 選項中選取*</span><span class="sxs-lookup"><span data-stu-id="69621-112">Select from SDT options](images/sdt-desk-2.png)
*Figure 2. Select from SDT options*</span></span>

4. <span data-ttu-id="69621-113">您可以選擇執行所有診斷測試。</span><span class="sxs-lookup"><span data-stu-id="69621-113">You can choose to run all the diagnostic tests.</span></span> <span data-ttu-id="69621-114">或者，如果您已懷疑某個特定問題（例如出現錯誤的顯示或電源問題），請按一下 [**選取**] 以從可用的測試中進行選擇，然後按一下 [**執行已選取**]，如圖3所示。</span><span class="sxs-lookup"><span data-stu-id="69621-114">Or, if you already suspect a particular issue such as a faulty display or a power supply problem, click **Select** to choose from the available tests and click **Run Selected**, as shown in figure 3.</span></span> <span data-ttu-id="69621-115">如需每個測試的詳細資料，請參閱下表。</span><span class="sxs-lookup"><span data-stu-id="69621-115">See the following table for details of each test.</span></span> 

    ![<span data-ttu-id="69621-116">選取 [硬體測試 ](images/sdt-desk-3.png)
 *圖 3]。選取硬體測試*</span><span class="sxs-lookup"><span data-stu-id="69621-116">Select hardware tests](images/sdt-desk-3.png)
*Figure 3. Select hardware tests*</span></span>

    <span data-ttu-id="69621-117">硬體測試</span><span class="sxs-lookup"><span data-stu-id="69621-117">Hardware test</span></span> | <span data-ttu-id="69621-118">描述</span><span class="sxs-lookup"><span data-stu-id="69621-118">Description</span></span>
    --- | ---
    <span data-ttu-id="69621-119">電源與電池</span><span class="sxs-lookup"><span data-stu-id="69621-119">Power Supply and Battery</span></span> |  <span data-ttu-id="69621-120">檢查電源運作最佳</span><span class="sxs-lookup"><span data-stu-id="69621-120">Checks Power supply is functioning optimally</span></span>
    <span data-ttu-id="69621-121">顯示與音效</span><span class="sxs-lookup"><span data-stu-id="69621-121">Display and Sound</span></span>   | <span data-ttu-id="69621-122">檢查亮度、滯留或死圖元、喇叭和麥克風運作</span><span class="sxs-lookup"><span data-stu-id="69621-122">Checks brightness, stuck or dead pixels, speaker and microphone functioning</span></span>
    <span data-ttu-id="69621-123">埠與附屬配件</span><span class="sxs-lookup"><span data-stu-id="69621-123">Ports and Accessories</span></span>   | <span data-ttu-id="69621-124">檢查附件、螢幕附加和 USB 運作</span><span class="sxs-lookup"><span data-stu-id="69621-124">Checks accessories, screen attach and USB functioning</span></span>
    <span data-ttu-id="69621-125">連線性</span><span class="sxs-lookup"><span data-stu-id="69621-125">Connectivity</span></span> |  <span data-ttu-id="69621-126">檢查藍牙、無線和 LTE 連線性</span><span class="sxs-lookup"><span data-stu-id="69621-126">Checks Bluetooth, wireless and LTE connectivity</span></span>
    <span data-ttu-id="69621-127">安全性</span><span class="sxs-lookup"><span data-stu-id="69621-127">Security</span></span>    | <span data-ttu-id="69621-128">檢查安全性相關問題</span><span class="sxs-lookup"><span data-stu-id="69621-128">Checks security related issues</span></span>
    <span data-ttu-id="69621-129">觸控</span><span class="sxs-lookup"><span data-stu-id="69621-129">Touch</span></span>   | <span data-ttu-id="69621-130">檢查觸控相關問題</span><span class="sxs-lookup"><span data-stu-id="69621-130">Checks touch related issues</span></span>
    <span data-ttu-id="69621-131">鍵盤和觸控</span><span class="sxs-lookup"><span data-stu-id="69621-131">Keyboard and touch</span></span> |    <span data-ttu-id="69621-132">檢查整合式鍵盤連接並輸入封面</span><span class="sxs-lookup"><span data-stu-id="69621-132">Checks integrated keyboard connection and type cover</span></span>
    <span data-ttu-id="69621-133">感應器</span><span class="sxs-lookup"><span data-stu-id="69621-133">Sensors</span></span> | <span data-ttu-id="69621-134">檢查裝置中不同感應器的運作方式</span><span class="sxs-lookup"><span data-stu-id="69621-134">Checks functioning of different sensors in the device</span></span>
    <span data-ttu-id="69621-135">硬體</span><span class="sxs-lookup"><span data-stu-id="69621-135">Hardware</span></span> |  <span data-ttu-id="69621-136">檢查不同硬體元件（例如圖形卡和相機）的問題</span><span class="sxs-lookup"><span data-stu-id="69621-136">Checks issues with different hardware components such as graphics card and camera</span></span>





<span id="multiple" />

## <span data-ttu-id="69621-137">執行多個硬體測試以疑難排解問題</span><span class="sxs-lookup"><span data-stu-id="69621-137">Running multiple hardware tests to troubleshoot issues</span></span>

<span data-ttu-id="69621-138">SDT 是以互動式工具的方式設計，可執行一系列測試。</span><span class="sxs-lookup"><span data-stu-id="69621-138">SDT is designed as an interactive tool that runs a series of tests.</span></span> <span data-ttu-id="69621-139">在每個測試中，SDT 都提供說明測試本質的指示，以及使用者應該預期或尋找哪些專案，才能成功進行測試。</span><span class="sxs-lookup"><span data-stu-id="69621-139">For each test, SDT provides instructions summarizing  the nature of the test and what users should expect or look for in order for the test to be successful.</span></span> <span data-ttu-id="69621-140">例如，若要診斷顯示器亮度是否正常運作，SDT 會從零開始，並將亮度增加至100%，要求使用者確認是否已正常運作**Yes** ，如**No**圖4所示。</span><span class="sxs-lookup"><span data-stu-id="69621-140">For example, to diagnose if the display brightness is working properly, SDT starts at zero and increases the brightness to 100 percent, asking users to confirm – by answering **Yes** or **No** -- that brightness is functioning as expected, as shown in figure 4.</span></span> 

<span data-ttu-id="69621-141">針對每個測試，如果功能無法如期運作，而使用者按一下 [**否**]，SDT 就會產生可能的原因，以及疑難排解的方法。</span><span class="sxs-lookup"><span data-stu-id="69621-141">For each test, if functionality does not work as expected and the user clicks **No**, SDT generates a report of the possible causes and ways to troubleshoot it.</span></span> 

![<span data-ttu-id="69621-142">執行硬體診斷 ](images/sdt-desk-4.png)
 *圖4。執行硬體診斷*</span><span class="sxs-lookup"><span data-stu-id="69621-142">Running hardware diagnostics](images/sdt-desk-4.png)
*Figure 4. Running hardware diagnostics*</span></span>

1. <span data-ttu-id="69621-143">如果亮度順利地從0-100% 調整成預期，請讓使用者按一下 **[是]** ，然後按一下 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="69621-143">If the brightness successfully adjusts from 0-100 percent as expected, direct the user to click **Yes** and then click **Continue**.</span></span> 
2. <span data-ttu-id="69621-144">如果亮度無法如期調整0-100%，請直接將使用者按一下 [**否**]，然後按一下 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="69621-144">If the brightness fails to adjust from 0-100 percent as expected, direct the user to click **No** and then click **Continue**.</span></span> 
3. <span data-ttu-id="69621-145">視需要引導使用者完成剩餘的測試。</span><span class="sxs-lookup"><span data-stu-id="69621-145">Guide users through remaining tests as appropriate.</span></span> <span data-ttu-id="69621-146">完成後，SDT 會自動提供報告的高層次摘要，包括任何硬體問題的可能原因，以及解決方法的指導方針。</span><span class="sxs-lookup"><span data-stu-id="69621-146">When finished, SDT automatically provides a high-level summary of the report, including the possible causes of any hardware issues along with guidance for resolution.</span></span>


### <span data-ttu-id="69621-147">修復應用程式</span><span class="sxs-lookup"><span data-stu-id="69621-147">Repairing applications</span></span>

<span data-ttu-id="69621-148">SDT 可讓您診斷並修復可能造成問題的應用程式，如圖5所示。</span><span class="sxs-lookup"><span data-stu-id="69621-148">SDT enables you to diagnose and repair applications that may be causing issues, as shown in figure 5.</span></span>

![<span data-ttu-id="69621-149">執行修復 ](images/sdt-desk-5.png)
 *圖5。執行修復*</span><span class="sxs-lookup"><span data-stu-id="69621-149">Running repairs](images/sdt-desk-5.png)
*Figure 5. Running repairs*</span></span>
<span id="logs" />

### <span data-ttu-id="69621-150">產生記錄來分析問題</span><span class="sxs-lookup"><span data-stu-id="69621-150">Generating logs for analyzing issues</span></span> 

<span data-ttu-id="69621-151">SDT 可跨應用程式、驅動程式、硬體及作業系統問題提供廣泛的記錄啟用診斷支援，如圖6所示。</span><span class="sxs-lookup"><span data-stu-id="69621-151">SDT provides extensive log-enabled diagnosis support across applications, drivers, hardware, and operating system issues, as shown in figure 6.</span></span>

![<span data-ttu-id="69621-152">產生記錄 ](images/sdt-desk-6.png)
 *圖6。產生記錄*</span><span class="sxs-lookup"><span data-stu-id="69621-152">Generating logs](images/sdt-desk-6.png)
*Figure 6. Generating logs*</span></span>

<span id="detailed-report" />

### <span data-ttu-id="69621-153">產生與最佳配置對比的詳細報告</span><span class="sxs-lookup"><span data-stu-id="69621-153">Generating detailed report comparing device vs. optimal configuration</span></span>

<span data-ttu-id="69621-154">根據記錄，SDT 會針對軟體及固件的問題產生報告，您可以將這些問題儲存至預先推薦的位置。</span><span class="sxs-lookup"><span data-stu-id="69621-154">Based on the logs, SDT generates a report for software- and firmware-based issues that you can save to a preferred location.</span></span>

## <span data-ttu-id="69621-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="69621-155">Related topics</span></span>

- [<span data-ttu-id="69621-156">使用命令執行商務用 Surface 診斷工具組</span><span class="sxs-lookup"><span data-stu-id="69621-156">Run Surface Diagnostic Toolkit for Business using commands</span></span>](surface-diagnostic-toolkit-command-line.md)

