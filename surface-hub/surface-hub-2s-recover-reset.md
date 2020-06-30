---
title: 重設及恢復 Surface Hub 2
description: 瞭解如何復原及重設 Surface Hub 秒數。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/05/2019
ms.localizationpriority: Medium
ms.openlocfilehash: fb7e1a39d96c2da6d27d5558ebefcff52bd6e159
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831453"
---
# <span data-ttu-id="00a8b-104">重設及恢復 Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="00a8b-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="00a8b-105">如果您遇到 Surface Hub 2 的問題，您可以使用 USB 磁片磁碟機將裝置重設成出廠設定或還原。</span><span class="sxs-lookup"><span data-stu-id="00a8b-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="00a8b-106">若要開始，請使用系統管理員認證登入 Surface Hub 2，開啟 [**設定**] 應用程式，選取 [**更新 & 安全性**]，然後選取 [復原 **]。**</span><span class="sxs-lookup"><span data-stu-id="00a8b-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="00a8b-107">重設裝置</span><span class="sxs-lookup"><span data-stu-id="00a8b-107">Reset the device</span></span>

1. <span data-ttu-id="00a8b-108">若要重設裝置，請選取 [**開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="00a8b-108">To reset the device, select **Get Started**.</span></span>
2. <span data-ttu-id="00a8b-109">出現 [**準備好重設此裝置**] 視窗時，請選取 [**重設**]。</span><span class="sxs-lookup"><span data-stu-id="00a8b-109">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
  >[!NOTE]
  ><span data-ttu-id="00a8b-110">Surface Hub 2 秒從恢復分區重新安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="00a8b-110">Surface Hub 2S reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="00a8b-111">這可能需要長達一小時的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="00a8b-111">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="00a8b-112">若要重新設定裝置，請執行第一次設定程式。</span><span class="sxs-lookup"><span data-stu-id="00a8b-112">To reconfigure the device, run the first-time Setup program.</span></span>
4. <span data-ttu-id="00a8b-113">如果您使用 Microsoft Intune 或其他行動裝置管理解決方案管理裝置，請停用並刪除前一筆記錄，然後重新註冊新的裝置。</span><span class="sxs-lookup"><span data-stu-id="00a8b-113">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="00a8b-114">如需詳細資訊，請參閱[使用 [擦除]、[停用] 或 [手動 unenrolling 裝置] 移除裝置](https://docs.microsoft.com/intune/devices-wipe)。</span><span class="sxs-lookup"><span data-stu-id="00a8b-114">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

![\* Surface Hub 2 秒的重設與復原 \*](images/sh2-reset.png)<br>
*<span data-ttu-id="00a8b-116">圖 1。</span><span class="sxs-lookup"><span data-stu-id="00a8b-116">Figure 1.</span></span> <span data-ttu-id="00a8b-117">重設及恢復 Surface Hub 2</span><span class="sxs-lookup"><span data-stu-id="00a8b-117">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="00a8b-118">使用 USB 恢復磁片磁碟機來復原 Surface Hub 的2到2秒</span><span class="sxs-lookup"><span data-stu-id="00a8b-118">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="00a8b-119">在 Surface Hub 2 的新功能中，您現在可以使用復原影像來重新安裝裝置。</span><span class="sxs-lookup"><span data-stu-id="00a8b-119">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="00a8b-120">從 USB 磁片磁碟機復原</span><span class="sxs-lookup"><span data-stu-id="00a8b-120">Recovery from a USB drive</span></span>

<span data-ttu-id="00a8b-121">使用 Surface Hub 2-2，您可以使用復原影像來重新安裝裝置。</span><span class="sxs-lookup"><span data-stu-id="00a8b-121">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="00a8b-122">如此一來，如果您遺失 BitLocker 金鑰，或您不再擁有 [設定] 應用程式的系統管理員認證，就可以將裝置重新安裝到出廠設定。</span><span class="sxs-lookup"><span data-stu-id="00a8b-122">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="00a8b-123">使用具有 8 GB 或 16 GB 儲存空間的 USB 3.0 磁片磁碟機，格式化為 FAT32 格式。</span><span class="sxs-lookup"><span data-stu-id="00a8b-123">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="00a8b-124">從個別的電腦，從[表面恢復網站](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s)下載 .zip 檔案復原影像，然後返回這些指示。</span><span class="sxs-lookup"><span data-stu-id="00a8b-124">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 
1. <span data-ttu-id="00a8b-125">將下載的檔案解壓縮至 USB 磁片磁碟機的根目錄。</span><span class="sxs-lookup"><span data-stu-id="00a8b-125">Unzip the downloaded file onto the root of the USB drive.</span></span>  
1. <span data-ttu-id="00a8b-126">將 USB 磁片磁碟機連接至 Surface Hub 2 上的任何 USB 或 USB 埠。</span><span class="sxs-lookup"><span data-stu-id="00a8b-126">Connect the USB drive to any USB-C or USB-A port on Surface Hub 2S.</span></span>
1. <span data-ttu-id="00a8b-127">關閉裝置：</span><span class="sxs-lookup"><span data-stu-id="00a8b-127">Turn off the device:</span></span>
   1. <span data-ttu-id="00a8b-128">按住 [音量] 按鈕，然後按下 [電源] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="00a8b-128">While holding down the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="00a8b-129">一直按住兩個按鈕，直到您看到 [Windows 標誌]。</span><span class="sxs-lookup"><span data-stu-id="00a8b-129">Keep holding both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="00a8b-130">放開電源按鈕，但繼續按住音量，直到安裝 UI 開始。</span><span class="sxs-lookup"><span data-stu-id="00a8b-130">Release the Power button but continue to hold the Volume until the Install UI begins.</span></span>

    ![\* 使用 [音量] 和 [電源] 按鈕來啟動復原 \*](images/sh2-keypad.png) <br>
   **<span data-ttu-id="00a8b-132">圖 2.</span><span class="sxs-lookup"><span data-stu-id="00a8b-132">Figure 2.</span></span> <span data-ttu-id="00a8b-133">[音量] 和 [電源] 按鈕</span><span class="sxs-lookup"><span data-stu-id="00a8b-133">Volume and Power buttons</span></span>**

1. <span data-ttu-id="00a8b-134">在 [語言選取範圍] 畫面上，選取 Surface Hub 2 秒的顯示語言。</span><span class="sxs-lookup"><span data-stu-id="00a8b-134">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>
1. <span data-ttu-id="00a8b-135">選取 [**從磁片磁碟機復原**] 並**完全清除磁片磁碟機**，然後選取 [**復原**]。</span><span class="sxs-lookup"><span data-stu-id="00a8b-135">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="00a8b-136">如果系統提示您輸入 BitLocker 金鑰，請選取 [**略過此磁片磁碟機**]。</span><span class="sxs-lookup"><span data-stu-id="00a8b-136">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="00a8b-137">Surface Hub 2 秒重新開機幾次，並花大約30分鐘的時間完成恢復程式。</span><span class="sxs-lookup"><span data-stu-id="00a8b-137">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="00a8b-138">當第一次設定畫面出現時，請移除 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="00a8b-138">When the first-time setup screen appears,remove the USB drive.</span></span>

## <span data-ttu-id="00a8b-139">連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="00a8b-139">Contact Support</span></span>

<span data-ttu-id="00a8b-140">如果您有任何疑問或需要協助，您可以[建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="00a8b-140">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
