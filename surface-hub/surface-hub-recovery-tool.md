---
title: 使用 Surface Hub Recovery Tool
description: 如何使用 Surface Hub 修復工具來重新映射處理 SSD。
ms.assetid: FDB6182C-1211-4A92-A930-6C106BCD5DC1
ms.reviewer: ''
manager: laurawi
keywords: 管理 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 02/11/2020
ms.localizationpriority: medium
ms.openlocfilehash: 0cc444eab51e9c3cc0bf2f9c2f0c36ac491906b1
ms.sourcegitcommit: 7b09b4bc757c5385c4f5560713cb03448afde9ea
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/16/2021
ms.locfileid: "11339364"
---
# <span data-ttu-id="bd3b0-104">使用 Surface Hub Recovery Tool</span><span class="sxs-lookup"><span data-stu-id="bd3b0-104">Using the Surface Hub Recovery Tool</span></span>

<span data-ttu-id="bd3b0-105">[Microsoft Surface Hub 修復](https://www.microsoft.com/download/details.aspx?id=52210)工具可協助您將 Surface Hub 實心磁片磁碟機 (SSD) 使用 Windows 10 桌面裝置重新映射，而不需要致電支援人員或更換 SSD。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-105">The [Microsoft Surface Hub Recovery Tool](https://www.microsoft.com/download/details.aspx?id=52210) helps you re-image your Surface Hub Solid State Drive (SSD) using a Windows 10 desktop device, without calling support or replacing the SSD.</span></span> <span data-ttu-id="bd3b0-106">使用這項工具，您可以為具有未知的系統管理員密碼、開機錯誤、無法完成雲端復原的 SSD，或是作業系統較舊版本的裝置重新建立映射。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-106">With this tool, you can reimage an SSD that has an unknown Administrator password, boot errors, was unable to complete a cloud recovery, or for a device that has an older version of the operating system.</span></span> <span data-ttu-id="bd3b0-107">此工具無法修正實體損壞的 SSD。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-107">The tool will not fix physically damaged SSDs.</span></span>

<span data-ttu-id="bd3b0-108">若要使用修復工具重新映射 Surface Hub SSD，您必須從 Surface Hub 移除 SSD、將磁片磁碟機連接到 USB-to-SATA 纜線，然後將纜線連接到安裝修復工具的桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-108">To re-image the Surface Hub SSD using the Recovery Tool, you'll need to remove the SSD from the Surface Hub, connect the drive to the USB-to-SATA cable, and then connect the cable to the desktop PC on which the Recovery Tool is installed.</span></span> <span data-ttu-id="bd3b0-109">若要瞭解如何從 Surface Hub 移除現有磁片磁碟機，請參閱[Surface Hub SSD 更換。](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="bd3b0-109">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd3b0-110">請勿讓裝置進入睡眠或中斷圖像檔案的下載。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-110">Do not let the device go to sleep or interrupt the download of the image file.</span></span>

<span data-ttu-id="bd3b0-111">如果工具無法重新映射您的硬碟，請聯絡 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人員。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-111">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="bd3b0-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="bd3b0-112">Prerequisites</span></span>

### <span data-ttu-id="bd3b0-113">Mandatory</span><span class="sxs-lookup"><span data-stu-id="bd3b0-113">Mandatory</span></span>

- <span data-ttu-id="bd3b0-114">主機電腦是 64 位版本的 Windows 10，版本 1607 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-114">Host PC running 64-bit version of Windows 10, version 1607 or higher.</span></span>
- <span data-ttu-id="bd3b0-115">網路與網際網路存取</span><span class="sxs-lookup"><span data-stu-id="bd3b0-115">Internet access</span></span>
- <span data-ttu-id="bd3b0-116">開啟 USB 2.0 或更大的埠</span><span class="sxs-lookup"><span data-stu-id="bd3b0-116">Open USB 2.0 or greater port</span></span>
- <span data-ttu-id="bd3b0-117">USB-to-SATA 纜線</span><span class="sxs-lookup"><span data-stu-id="bd3b0-117">USB-to-SATA cable</span></span>
- <span data-ttu-id="bd3b0-118">主機電腦上 10 GB 的可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="bd3b0-118">10 GB of free disk space on the host computer</span></span>
- <span data-ttu-id="bd3b0-119">SSD 會與 Surface Hub 或支援人員提供的 SSD 一起提供，做為替代產品。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-119">SSDs shipped with Surface Hub or a SSD provided by Support as a replacement.</span></span> <span data-ttu-id="bd3b0-120">不支援 Microsoft 未提供的 SSD。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-120">SSDs not supplied by Microsoft are not supported.</span></span>

### <span data-ttu-id="bd3b0-121">建議執行</span><span class="sxs-lookup"><span data-stu-id="bd3b0-121">Recommended</span></span>

- <span data-ttu-id="bd3b0-122">高速網際網路連接</span><span class="sxs-lookup"><span data-stu-id="bd3b0-122">High-speed Internet connection</span></span>
- <span data-ttu-id="bd3b0-123">開啟 USB 3.0 埠</span><span class="sxs-lookup"><span data-stu-id="bd3b0-123">Open USB 3.0 port</span></span>
- <span data-ttu-id="bd3b0-124">USB 3.0 或更高版本的 USB-to-SATA 纜線</span><span class="sxs-lookup"><span data-stu-id="bd3b0-124">USB 3.0 or higher USB-to-SATA cable</span></span>
- <span data-ttu-id="bd3b0-125">影像工具已使用下列纜線的製造和型號進行測試：</span><span class="sxs-lookup"><span data-stu-id="bd3b0-125">The imaging tool was tested with the following make and model of cables:</span></span>
    - <span data-ttu-id="bd3b0-126">Startech USB312SAT3CB</span><span class="sxs-lookup"><span data-stu-id="bd3b0-126">Startech USB312SAT3CB</span></span>
    - <span data-ttu-id="bd3b0-127">Rosew RCUC16001</span><span class="sxs-lookup"><span data-stu-id="bd3b0-127">Rosewill RCUC16001</span></span>
    - <span data-ttu-id="bd3b0-128">Ugreen 20231</span><span class="sxs-lookup"><span data-stu-id="bd3b0-128">Ugreen 20231</span></span>

## <span data-ttu-id="bd3b0-129">下載 Surface Hub 修復工具</span><span class="sxs-lookup"><span data-stu-id="bd3b0-129">Download Surface Hub Recovery Tool</span></span>

<span data-ttu-id="bd3b0-130">Surface Hub 修復工具可從適用于[IT](https://www.microsoft.com/download/details.aspx?id=52210)的 Surface Hub 工具下載，檔案名為**SurfaceHub_Recovery_v2.7.139.0.msi。**</span><span class="sxs-lookup"><span data-stu-id="bd3b0-130">Surface Hub Recovery Tool is available for download from [Surface Hub Tools for IT](https://www.microsoft.com/download/details.aspx?id=52210)  under the file name **SurfaceHub_Recovery_v2.7.139.0.msi**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd3b0-131">此版本于 2021 年 2 月 11 日發行，取代先前無法再運作的版本。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-131">This version, released Feb 11, 2021, replaces the earlier build, which is no longer functional.</span></span> <span data-ttu-id="bd3b0-132">如果您先前下載過此工具，請卸載並安裝目前版本。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-132">If you downloaded this tool previously, please uninstall it and install the current version.</span></span>

<span data-ttu-id="bd3b0-133">若要開始下載，請按一下\*\*\*\*[下載**SurfaceHub_Recovery_v2.7.139.0.msi，然後**按 [下一**步**。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-133">To start the download, click **Download**, choose **SurfaceHub_Recovery_v2.7.139.0.msi**  from the list, and click **Next**.</span></span> <span data-ttu-id="bd3b0-134">從快顯視窗選擇下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="bd3b0-134">From the pop-up, choose one of the following:</span></span>

- <span data-ttu-id="bd3b0-135">按一下 **[** 執行並立即開始安裝。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-135">Click **Run** to start the installation immediately.</span></span>
- <span data-ttu-id="bd3b0-136">按一下 **[儲存** 以將下載複製到您的電腦，供日後安裝。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-136">Click **Save** to copy the download to your computer for later installation.</span></span>

<span data-ttu-id="bd3b0-137">在主機電腦上安裝 Surface Hub 修復工具。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-137">Install Surface Hub Recovery Tool on the host PC.</span></span>

## <span data-ttu-id="bd3b0-138">執行 Surface Hub 修復工具</span><span class="sxs-lookup"><span data-stu-id="bd3b0-138">Run Surface Hub Recovery Tool</span></span>

1. <span data-ttu-id="bd3b0-139">在主 PC 上，選取 **開始按鈕、** 捲動左側的字母清單，然後選取修復工具快速鍵。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-139">On the host PC, select the **Start** button, scroll through the alphabetical list on the left, and select the recovery tool shortcut.</span></span>

    ![Microsoft Surface Hub 修復工具快速鍵](images/shrt-shortcut.png)

2. <span data-ttu-id="bd3b0-141">按一下 **\[開始\]**。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-141">Click **Start**.</span></span>

    ![修復工具的開始按鈕](images/shrt-start.png)


3. <span data-ttu-id="bd3b0-143">在指引 **視窗中** ，按一下 [下 **一步**。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-143">In the **Guidance** window, click **Next**.</span></span>

    ![請勿讓電腦進入睡眠指引](images/shrt-guidance.png)

4. <span data-ttu-id="bd3b0-145">在選取圖像視窗中，按一下**RS2**或其後續版本\*\*\*\*\*\*20H2，\*\* 選取 [繼續，然後選取**下載影像。**</span><span class="sxs-lookup"><span data-stu-id="bd3b0-145">In the Select image window, click either **RS2** or its successor **20H2**, select **Continue,** and then select **Download image.**</span></span>

     <span data-ttu-id="bd3b0-146">![修復工具選取圖像 ](images/shrt-select-image.png) ![ 修復工具下載圖像](images/shrt-download-image.png)</span><span class="sxs-lookup"><span data-stu-id="bd3b0-146">![Recovery Tool Select image](images/shrt-select-image.png) ![Recovery Tool Download image](images/shrt-download-image.png)</span></span>

5. <span data-ttu-id="bd3b0-147">下載復原映射的時間取決於網際網路連線速度。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-147">Time to download the recovery image is dependent on internet connection speeds.</span></span> <span data-ttu-id="bd3b0-148">在一般的公司關係上，最多可能需要一小時的時間下載 8 GB 圖像檔案。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-148">On an average corporate connection, it can take up to an hour to download the 8GB image file.</span></span>

    ![下載圖像](images/shrt-download.png)



5. <span data-ttu-id="bd3b0-150">下載完成後，工具會指示您連接 SSD 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-150">When the download is complete, the tool instructs you to connect an SSD drive.</span></span> <span data-ttu-id="bd3b0-151">如果工具找不到附加的磁片磁碟機，使用中的纜線很有可能不會向 Windows 報告 SSD 名稱。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-151">If the tool is unable to locate the attached drive, there is a good chance that the cable being used is not reporting the name of the SSD to Windows.</span></span>  <span data-ttu-id="bd3b0-152">影像工具必須先將光碟機名稱尋找為「LITEON L CH-128V2S USB 裝置」，才能繼續。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-152">The imaging tool must find the name of the drive as "LITEON L CH-128V2S USB Device" before it can continue.</span></span>  <span data-ttu-id="bd3b0-153">若要瞭解如何從 Surface Hub 移除現有磁片磁碟機，請參閱[Surface Hub SSD 更換。](surface-hub-ssd-replacement.md)</span><span class="sxs-lookup"><span data-stu-id="bd3b0-153">For more information on how to remove the existing drive from your Surface Hub, see [Surface Hub SSD replacement](surface-hub-ssd-replacement.md).</span></span>

    ![連接 SSD](images/shrt-drive.png)

6. <span data-ttu-id="bd3b0-155">當硬碟被識別時，按一下 **[開始** 著手進行重新映射處理。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-155">When the drive is recognized, click **Start** to begin the re-imaging process.</span></span> <span data-ttu-id="bd3b0-156">在硬碟上所有資料都會清除的警告上，按一下 **[確定**。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-156">On the warning that all data on the drive will be erased, click **OK**.</span></span>



    <span data-ttu-id="bd3b0-157">將系統映射新用至磁片磁碟機之前，系統會重新區整並格式化 SSD。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-157">Prior to applying the system image to the drive, the SSD is repartitioned and formatted.</span></span> <span data-ttu-id="bd3b0-158">複製系統二進位檔案大約需要 30 分鐘，但可能需要較長的時間，視 USB 母線的速度、使用的纜線或您系統安裝的防毒軟體而不同。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-158">Copying the system binaries will take approximately 30 minutes, but can take longer depending on the speed of your USB bus, the cable being used, or antivirus software installed on your system.</span></span>



## <span data-ttu-id="bd3b0-159">疑難排解和常見問題</span><span class="sxs-lookup"><span data-stu-id="bd3b0-159">Troubleshooting and common problems</span></span>

<span data-ttu-id="bd3b0-160">問題</span><span class="sxs-lookup"><span data-stu-id="bd3b0-160">Issue</span></span> | <span data-ttu-id="bd3b0-161">附註</span><span class="sxs-lookup"><span data-stu-id="bd3b0-161">Notes</span></span>
--- | ---
<span data-ttu-id="bd3b0-162">工具無法對 SSD 進行影像</span><span class="sxs-lookup"><span data-stu-id="bd3b0-162">The tool fails to image the SSD</span></span> | <span data-ttu-id="bd3b0-163">請確定您使用的是出廠時提供的 SSD 和其中一個測試纜線。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-163">Make sure you are using a factory-supplied SSD and one of the tested cables.</span></span>
<span data-ttu-id="bd3b0-164">重新製作程式顯示為暫停/凍結</span><span class="sxs-lookup"><span data-stu-id="bd3b0-164">The reimaging process appears halted/frozen</span></span> | <span data-ttu-id="bd3b0-165">可以放心關閉並重新啟動 Surface Hub 修復工具，對 SSD 不會造成任何影響。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-165">It is safe to close and restart the Surface Hub Recovery Tool with no ill effect to the SSD.</span></span>
<span data-ttu-id="bd3b0-166">工具無法識別該磁碟機</span><span class="sxs-lookup"><span data-stu-id="bd3b0-166">The drive isn’t recognized by the tool</span></span> | <span data-ttu-id="bd3b0-167">確認 Surface Hub SSD 列舉為Lite-On LITEON L CH-128V2S USB 裝置」的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-167">Verify that the Surface Hub SSD is enumerated as a Lite-On drive, "LITEON L CH-128V2S USB Device".</span></span>  <span data-ttu-id="bd3b0-168">如果硬碟被識別為另一個已命名的裝置，表示您目前的纜線不相容。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-168">If the drive is recognized as another named device, your current cable isn’t compatible.</span></span> <span data-ttu-id="bd3b0-169">請嘗試上述其他纜線或其中一條測試纜線。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-169">Try another cable or one of the tested cable listed above.</span></span>
<span data-ttu-id="bd3b0-170">錯誤：-2147024809</span><span class="sxs-lookup"><span data-stu-id="bd3b0-170">Error: -2147024809</span></span> | <span data-ttu-id="bd3b0-171">開啟磁片管理器並移除 Surface Hub 磁片磁碟機上的磁碟分割。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-171">Open Disk Manager and remove the partitions on the Surface Hub drive.</span></span>  <span data-ttu-id="bd3b0-172">將硬碟中斷連接並重新連接到主機電腦。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-172">Disconnect and reconnect the drive to the host machine.</span></span> <span data-ttu-id="bd3b0-173">重新開機影像工具。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-173">Restart the imaging tool again.</span></span>

<span data-ttu-id="bd3b0-174">如果工具無法重新映射您的硬碟，請聯絡 [Surface Hub 支援](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support)人員。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-174">If the tool is unsuccessful in reimaging your drive, please contact [Surface Hub Support](https://support.microsoft.com/help/4037644/surface-contact-surface-warranty-and-software-support).</span></span>

## <span data-ttu-id="bd3b0-175">版本歷程記錄</span><span class="sxs-lookup"><span data-stu-id="bd3b0-175">Version history</span></span>


### <span data-ttu-id="bd3b0-176">版本 2.7.139.0</span><span class="sxs-lookup"><span data-stu-id="bd3b0-176">Version v2.7.139.0</span></span>

*<span data-ttu-id="bd3b0-177">發行日期：2021 年 2 月 11 日</span><span class="sxs-lookup"><span data-stu-id="bd3b0-177">Release date: February 11, 2021</span></span>*<br>
<span data-ttu-id="bd3b0-178">此版本的 Surface Hub 修復工具新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="bd3b0-178">This version of Surface Hub Recovery Tool adds support for the following:</span></span>

- <span data-ttu-id="bd3b0-179">安全性更新</span><span class="sxs-lookup"><span data-stu-id="bd3b0-179">Security update</span></span>


### <span data-ttu-id="bd3b0-180">版本 2.0.139.0</span><span class="sxs-lookup"><span data-stu-id="bd3b0-180">Version v2.0.139.0</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd3b0-181">此版本已無法運作。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-181">This version is no longer functional.</span></span> <span data-ttu-id="bd3b0-182">請下載上列的目前版本。</span><span class="sxs-lookup"><span data-stu-id="bd3b0-182">Please download the current version, listed above.</span></span> 

*<span data-ttu-id="bd3b0-183">發行日期：2020 年 12 月 18 日</span><span class="sxs-lookup"><span data-stu-id="bd3b0-183">Release date: December 18, 2020</span></span>*<br>
<span data-ttu-id="bd3b0-184">此版本的 Surface Hub 修復工具新增下列支援：</span><span class="sxs-lookup"><span data-stu-id="bd3b0-184">This version of Surface Hub Recovery Tool adds support for the following:</span></span>
- <span data-ttu-id="bd3b0-185">更新以支援 Windows 10 小組 2020 更新 (20H2) </span><span class="sxs-lookup"><span data-stu-id="bd3b0-185">Update to support Windows 10 Team 2020 Update (20H2)</span></span>
- <span data-ttu-id="bd3b0-186">使用者體驗改進</span><span class="sxs-lookup"><span data-stu-id="bd3b0-186">User experience improvements</span></span>
- <span data-ttu-id="bd3b0-187">架構變更</span><span class="sxs-lookup"><span data-stu-id="bd3b0-187">Architectural changes</span></span>
- <span data-ttu-id="bd3b0-188">遙測新增專案</span><span class="sxs-lookup"><span data-stu-id="bd3b0-188">Telemetry additions</span></span>

