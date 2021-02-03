---
title: 使用 Surface Hub Recovery Tool
description: 如何使用 Surface Hub 恢復工具來重新影像 SSD。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 12/18/2020
ms.localizationpriority: medium
ms.openlocfilehash: 9df9de731ac5c8f8acb393db3d4b16e9d1c98a9e
ms.sourcegitcommit: 5cfac94c220c8a8d4620c6a7fa75ae2fae089c7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2021
ms.locfileid: "11312029"
---
# <span data-ttu-id="061eb-104">使用 Surface Hub Recovery Tool</span><span class="sxs-lookup"><span data-stu-id="061eb-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="061eb-105">[Microsoft Surface Hub 恢復工具](https://www.microsoft.com/download/details.aspx?id=52210)可協助您使用 Windows 10 傳統型裝置重新鏡像 Surface Hub 固態磁片磁碟機 (SSD) ，而不需呼叫支援或取代 SSD。</span><span class="sxs-lookup"><span data-stu-id="061eb-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="061eb-106">透過此工具，您可以重新組成具有未知系統管理員密碼的 SSD、啟動錯誤、無法完成雲端復原，或針對舊版作業系統的裝置進行重新鏡像。</span><span class="sxs-lookup"><span data-stu-id="061eb-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="061eb-107">此工具不會修正實際損毀的 SSDs。</span><span class="sxs-lookup"><span data-stu-id="061eb-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="061eb-108">若要使用 [恢復] 工具重新影像 Surface Hub SSD，您必須從 Surface Hub 中移除 SSD，將磁碟機連接至 USB 至 SATA 纜線，然後將纜線連接至安裝了復原工具的桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="061eb-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="061eb-109">如需如何從 Surface Hub 移除現有磁片磁碟機的詳細資訊，請參閱 [Surface HUB SSD 取代](surface-hub-ssd-replacement.md)。</span><span class="sxs-lookup"><span data-stu-id="061eb-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="061eb-110">請勿讓裝置移至 [睡眠] 或 [中斷影像檔案的下載]。</span><span class="sxs-lookup"><span data-stu-id="061eb-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="061eb-111">如果此工具無法在您的磁片磁碟機中進行磁片映射，請與 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="061eb-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="061eb-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="061eb-112">Prerequisites</span></span>

### <span data-ttu-id="061eb-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="061eb-113">Mandatory</span></span>

- <span data-ttu-id="061eb-114">運行64位版本的 Windows 10 版本1607或更高版本的主機電腦。</span><span class="sxs-lookup"><span data-stu-id="061eb-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="061eb-115">網路與網際網路存取</span><span class="sxs-lookup"><span data-stu-id="061eb-115">Internet access</span></span>
- <span data-ttu-id="061eb-116">開啟 USB 2.0 或更多埠</span><span class="sxs-lookup"><span data-stu-id="061eb-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="061eb-117">USB 至 SATA 纜線</span><span class="sxs-lookup"><span data-stu-id="061eb-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="061eb-118">主機電腦上有 10 GB 的可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="061eb-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="061eb-119">SSDs 隨附 Surface Hub 或支援部門提供的 SSD 來取代。</span><span class="sxs-lookup"><span data-stu-id="061eb-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="061eb-120">不支援 Microsoft 未提供的 SSDs。</span><span class="sxs-lookup"><span data-stu-id="061eb-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="061eb-121">建議執行</span><span class="sxs-lookup"><span data-stu-id="061eb-121">Recommended</span></span>

- <span data-ttu-id="061eb-122">高速網際網路連線</span><span class="sxs-lookup"><span data-stu-id="061eb-122">High-speed Internet connection</span></span>
- <span data-ttu-id="061eb-123">開啟 USB 3.0 埠</span><span class="sxs-lookup"><span data-stu-id="061eb-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="061eb-124">USB 3.0 或更高的 USB 至 SATA 纜線</span><span class="sxs-lookup"><span data-stu-id="061eb-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="061eb-125">已使用下列的纜線製作與模型來測試影像工具：</span><span class="sxs-lookup"><span data-stu-id="061eb-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="061eb-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="061eb-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="061eb-127">Rosewill RCUC16001</span><span class="sxs-lookup"><span data-stu-id="061eb-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="061eb-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="061eb-128">Ugreen 20231</span></span>

## <span data-ttu-id="061eb-129">下載 Surface Hub 中心恢復工具</span><span class="sxs-lookup"><span data-stu-id="061eb-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="061eb-130">Surface Hub 恢復工具可從 [Surface Hub 工具](https://www.microsoft.com/download/details.aspx?id=52210)  的 [ **SurfaceHub_Recovery_v2.0.139.0.msi**的檔案名] 中下載。</span><span class="sxs-lookup"><span data-stu-id="061eb-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.0.139.0.msi**.</span></span>

<span data-ttu-id="061eb-131">若要開始下載，請按一下 [ **下載**]，從清單中選擇 [ **SurfaceHub_Recovery_v2.0.139.0.msi** ]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="061eb-131">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.0.139.0.msi** from the list, and click **Next**.</span></span> <span data-ttu-id="061eb-132">從快顯視窗中，選擇下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="061eb-132">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="061eb-133">按一下 [ **執行** ]，立即開始安裝。</span><span class="sxs-lookup"><span data-stu-id="061eb-133">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="061eb-134">按一下 [ **儲存** ] 以將下載內容複寫到您的電腦，以供日後安裝。</span><span class="sxs-lookup"><span data-stu-id="061eb-134">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="061eb-135">在主機電腦上安裝 Surface Hub 恢復工具。</span><span class="sxs-lookup"><span data-stu-id="061eb-135">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="061eb-136">執行 Surface Hub 恢復工具</span><span class="sxs-lookup"><span data-stu-id="061eb-136">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="061eb-137">在主機電腦上，選取 [ **開始** ] 按鈕，在左側的 [字母順序] 清單中滾動，然後選取 [恢復工具] 快捷方式。</span><span class="sxs-lookup"><span data-stu-id="061eb-137">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub 恢復工具快速鍵](images/shrt-shortcut.png)

2. <span data-ttu-id="061eb-139">按一下 **\[開始\]**。</span><span class="sxs-lookup"><span data-stu-id="061eb-139">Click **Start**.</span></span>

    ![[恢復工具] [開始] 按鈕](images/shrt-start.png)


3. <span data-ttu-id="061eb-141">在 [ **指導** 方針] 視窗中，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="061eb-141">In the **Guidance** window, click **Next**.</span></span>

    ![請勿讓您的電腦移至 [睡眠] 指南](images/shrt-guidance.png)

4. <span data-ttu-id="061eb-143">在 [選取影像] 視窗中，按一下 [ **RS2** ] 或其 [後續 **20H2**]，選取 [ **繼續]，** 然後選取 [ **下載影像]。**</span><span class="sxs-lookup"><span data-stu-id="061eb-143">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="061eb-144">![[恢復工具] 選取影像復原 ](images/shrt-select-image.png) ![ 工具下載圖像](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="061eb-144">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="061eb-145">下載復原影像所需的時間取決於網際網路連線速度。</span><span class="sxs-lookup"><span data-stu-id="061eb-145">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="061eb-146">在一般的企業連線中，最多可能需要一個小時的時間來下載8GB 圖像檔案。</span><span class="sxs-lookup"><span data-stu-id="061eb-146">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![下載影像](images/shrt-download.png)



5. <span data-ttu-id="061eb-148">下載完成後，工具會指示您連接 SSD 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="061eb-148">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="061eb-149">如果工具無法找到已附加的磁片磁碟機，很可能是使用纜線不會將 SSD 的名稱報告給 Windows。</span><span class="sxs-lookup"><span data-stu-id="061eb-149">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="061eb-150">在繼續之前，影像工具必須找到磁碟機的名稱為「LITEON L CH-128V2S USB 裝置」。</span><span class="sxs-lookup"><span data-stu-id="061eb-150">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="061eb-151">如需如何從 Surface Hub 移除現有磁片磁碟機的詳細資訊，請參閱 [Surface HUB SSD 取代](surface-hub-ssd-replacement.md)。</span><span class="sxs-lookup"><span data-stu-id="061eb-151">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![連接 SSD](images/shrt-drive.png)

6. <span data-ttu-id="061eb-153">辨識磁碟機後，請按一下 [ **開始** ] 以開始重新影像處理常式。</span><span class="sxs-lookup"><span data-stu-id="061eb-153">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="061eb-154">在警告中，磁片上的所有資料都會被清除，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="061eb-154">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="061eb-155">在將系統映射套用到磁片磁碟機之前，SSD 會進行重新分區及格式化。</span><span class="sxs-lookup"><span data-stu-id="061eb-155">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="061eb-156">複製系統二進位檔案大約需要30分鐘，但可能需要較長的時間，視您的 USB 匯流排速度、使用的纜線，或系統上安裝的防毒軟體而定。</span><span class="sxs-lookup"><span data-stu-id="061eb-156">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="061eb-157">疑難排解及常見問題</span><span class="sxs-lookup"><span data-stu-id="061eb-157">Troubleshooting and common problems</span></span>

<span data-ttu-id="061eb-158">問題</span><span class="sxs-lookup"><span data-stu-id="061eb-158">Issue</span></span> | <span data-ttu-id="061eb-159">附註</span><span class="sxs-lookup"><span data-stu-id="061eb-159">Notes</span></span>
--- | ---
<span data-ttu-id="061eb-160">此工具無法將 SSD 影像</span><span class="sxs-lookup"><span data-stu-id="061eb-160">The tool fails to image the SSD</span></span> | <span data-ttu-id="061eb-161">請確定您使用的是 factory 提供的 SSD，以及其中一個已測試的纜線。</span><span class="sxs-lookup"><span data-stu-id="061eb-161">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="061eb-162">此映射程式會顯示暫停/凍結狀態</span><span class="sxs-lookup"><span data-stu-id="061eb-162">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="061eb-163">關閉並重新啟動 Surface Hub 恢復工具，不會對 SSD 產生任何不正確的影響，是安全的。</span><span class="sxs-lookup"><span data-stu-id="061eb-163">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="061eb-164">工具無法辨識此磁碟機</span><span class="sxs-lookup"><span data-stu-id="061eb-164">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="061eb-165">確認 Surface Hub SSD 列舉為 Lite-On 磁片磁碟機，"LITEON L CH-128V2S USB 裝置"。</span><span class="sxs-lookup"><span data-stu-id="061eb-165">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="061eb-166">如果該磁碟機被識別為另一個已命名的裝置，您目前的纜線不相容。</span><span class="sxs-lookup"><span data-stu-id="061eb-166">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="061eb-167">試試上面所列的另一根電纜或其中一個已測試的電纜。</span><span class="sxs-lookup"><span data-stu-id="061eb-167">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="061eb-168">錯誤：-2147024809</span><span class="sxs-lookup"><span data-stu-id="061eb-168">Error: -2147024809</span></span> | <span data-ttu-id="061eb-169">開啟磁片管理器並移除 Surface Hub 磁片磁碟機上的分區。</span><span class="sxs-lookup"><span data-stu-id="061eb-169">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="061eb-170">中斷連線並將磁碟機重新連接到主機電腦。</span><span class="sxs-lookup"><span data-stu-id="061eb-170">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="061eb-171">重新開機影像工具。</span><span class="sxs-lookup"><span data-stu-id="061eb-171">Restart the imaging tool again.</span></span>

<span data-ttu-id="061eb-172">如果此工具無法在您的磁片磁碟機中進行磁片映射，請與 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="061eb-172">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="061eb-173">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="061eb-173">Version history</span></span>

### <span data-ttu-id="061eb-174">版本 v 2.0.139。0</span><span class="sxs-lookup"><span data-stu-id="061eb-174">Version v2.0.139.0</span></span>

*<span data-ttu-id="061eb-175">發行日期：2020年12月18日</span><span class="sxs-lookup"><span data-stu-id="061eb-175">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="061eb-176">這個版本的 Surface Hub 恢復工具會為下列專案新增支援：</span><span class="sxs-lookup"><span data-stu-id="061eb-176">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="061eb-177">更新以支援 Windows 10 Team 2020 更新 (20H2) </span><span class="sxs-lookup"><span data-stu-id="061eb-177">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="061eb-178">改善使用者體驗</span><span class="sxs-lookup"><span data-stu-id="061eb-178">User experience improvements</span></span>
- <span data-ttu-id="061eb-179">架構變更</span><span class="sxs-lookup"><span data-stu-id="061eb-179">Architectural changes</span></span>
- <span data-ttu-id="061eb-180">遙測新增</span><span class="sxs-lookup"><span data-stu-id="061eb-180">Telemetry additions</span></span>

