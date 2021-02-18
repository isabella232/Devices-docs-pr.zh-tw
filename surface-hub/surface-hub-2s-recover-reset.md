---
title: Surface Hub 2S 的重設及復原
description: 瞭解如何復原和重設 Surface Hub 2S。
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
ms.openlocfilehash: 64ceee291d3d3e067f581707d9431fa92398c785
ms.sourcegitcommit: ecb4909c091e69b7bdb1faacfc8c34b480dc884b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/17/2021
ms.locfileid: "11342973"
---
# <span data-ttu-id="db3b0-104">Surface Hub 2S 的重設及復原</span><span class="sxs-lookup"><span data-stu-id="db3b0-104">Reset and recovery for Surface Hub 2S</span></span>

<span data-ttu-id="db3b0-105">如果您遇到 Surface Hub 2S 的問題，您可以將裝置重設為出廠設定，或使用 USB 磁碟機進行還原。</span><span class="sxs-lookup"><span data-stu-id="db3b0-105">If you encounter problems with Surface Hub 2S, you can reset the device to factory settings or restore by using a USB drive.</span></span>

<span data-ttu-id="db3b0-106">若要開始，請以系統管理員認證來登錄 Surface Hub 2S、開啟 **設定應用程式、** 選取更新 **&安全性**， **然後選取復原**。</span><span class="sxs-lookup"><span data-stu-id="db3b0-106">To begin, sign in to Surface Hub 2S with admin credentials, open the **Settings** app, select **Update & security**, and then select **Recovery**.</span></span>

## <span data-ttu-id="db3b0-107">重設裝置</span><span class="sxs-lookup"><span data-stu-id="db3b0-107">Reset the device</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="db3b0-108">在重設裝置之前，請確認您擁有 BitLocker 金鑰，因為稍後會提示您。</span><span class="sxs-lookup"><span data-stu-id="db3b0-108">Ensure that you have your BitLocker key available before resetting the device, as you will be prompted for it later.</span></span> <span data-ttu-id="db3b0-109">若要深入瞭解，請參閱儲存 [BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。</span><span class="sxs-lookup"><span data-stu-id="db3b0-109">To learn more, see [Save your BitLocker key](save-bitlocker-key-surface-hub.md).</span></span>

1. <span data-ttu-id="db3b0-110">若要重設裝置 **，請選取**開始使用。</span><span class="sxs-lookup"><span data-stu-id="db3b0-110">To reset the device, select **Get Started**.</span></span>

2. <span data-ttu-id="db3b0-111">出現 **準備好重設此裝置** 視窗時，請選取重 **設**。</span><span class="sxs-lookup"><span data-stu-id="db3b0-111">When the **Ready to reset this device** window appears, select **Reset**.</span></span> 
  
   > [!IMPORTANT]
   > <span data-ttu-id="db3b0-112">當中樞重新開機至修復磁碟分割時，會提示您輸入 BitLocker 鍵。</span><span class="sxs-lookup"><span data-stu-id="db3b0-112">When the Hub reboots to the recovery partition, it will prompt you to enter the BitLocker key.</span></span> <span data-ttu-id="db3b0-113">略過該提示會導致重設失敗。</span><span class="sxs-lookup"><span data-stu-id="db3b0-113">Skipping that prompt will cause reset to fail.</span></span> <span data-ttu-id="db3b0-114">輸入 BitLocker 金鑰後，Hub 會從修復磁碟分割重新安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="db3b0-114">Once you enter the BitLocker key the Hub reinstalls the operating system from the recovery partition.</span></span> <span data-ttu-id="db3b0-115">這最多可能需要一小時才能完成。</span><span class="sxs-lookup"><span data-stu-id="db3b0-115">This may take up to one hour to complete.</span></span>
  
3. <span data-ttu-id="db3b0-116">若要重新設定裝置，請執行第一次安裝程式。</span><span class="sxs-lookup"><span data-stu-id="db3b0-116">To reconfigure the device, run the first-time Setup program.</span></span>

4. <span data-ttu-id="db3b0-117">如果您使用 Microsoft Intune 或其他行動裝置管理解決方案管理裝置，請淘汰並刪除上一個記錄，然後重新註冊新裝置。</span><span class="sxs-lookup"><span data-stu-id="db3b0-117">If you manage the device using Microsoft Intune or another mobile device management solution, retire and delete the previous record, and then re-enroll the new device.</span></span> <span data-ttu-id="db3b0-118">詳細資訊請參閱使用抹 [除、](https://docs.microsoft.com/intune/devices-wipe)淘汰或手動取消註冊裝置來移除裝置。</span><span class="sxs-lookup"><span data-stu-id="db3b0-118">For more information, see [Remove devices by using wipe, retire, or manually unenrolling the device](https://docs.microsoft.com/intune/devices-wipe).</span></span>

   > [!div class="mx-imgBorder"]
   > ![*Surface Hub 2S 的重設及復原*](images/sh2-reset.png)
   <br/>*<span data-ttu-id="db3b0-120">圖 1。</span><span class="sxs-lookup"><span data-stu-id="db3b0-120">Figure 1.</span></span> <span data-ttu-id="db3b0-121">Surface Hub 2S 的重設及復原</span><span class="sxs-lookup"><span data-stu-id="db3b0-121">Reset and recovery for Surface Hub 2S</span></span>* 

## <span data-ttu-id="db3b0-122">使用 USB 修復磁碟機復原 Surface Hub 2S</span><span class="sxs-lookup"><span data-stu-id="db3b0-122">Recover Surface Hub 2S by using a USB recovery drive</span></span>

<span data-ttu-id="db3b0-123">Surface Hub 2S 的新功能，現在您可以使用修復映射重新安裝裝置。</span><span class="sxs-lookup"><span data-stu-id="db3b0-123">New in Surface Hub 2S, you can now reinstall the device by using a recovery image.</span></span>

### <span data-ttu-id="db3b0-124">從 USB 磁碟機進行復原</span><span class="sxs-lookup"><span data-stu-id="db3b0-124">Recovery from a USB drive</span></span>

<span data-ttu-id="db3b0-125">使用 Surface Hub 2S，您可以使用修復映射重新安裝裝置。</span><span class="sxs-lookup"><span data-stu-id="db3b0-125">Using Surface Hub 2S, you can reinstall the device by using a recovery image.</span></span> <span data-ttu-id="db3b0-126">這樣一來，如果您遺失 BitLocker 金鑰，或如果您不再擁有設定應用程式的系統管理員認證，您可以將裝置重新安裝到出廠設定。</span><span class="sxs-lookup"><span data-stu-id="db3b0-126">By doing this, you can reinstall the device to the factory settings if you lost the BitLocker key, or if you no longer have admin credentials to the Settings app.</span></span>

>[!NOTE]
><span data-ttu-id="db3b0-127">使用儲存空間為 8 GB 或 16 GB 的 USB 3.0 磁片磁碟機，格式為 FAT32。</span><span class="sxs-lookup"><span data-stu-id="db3b0-127">Use a USB 3.0 drive with 8 GB or 16 GB of storage, formatted as FAT32.</span></span>

1. <span data-ttu-id="db3b0-128">從另一部電腦，從 [Surface Recovery](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) 網站下載 .zip 檔案復原映射，然後返回這些指示。</span><span class="sxs-lookup"><span data-stu-id="db3b0-128">From a separate PC, download the .zip file recovery image from the [Surface Recovery website](https://support.microsoft.com/surfacerecoveryimage?devicetype=surfacehub2s) and then return to these instructions.</span></span> 

1. <span data-ttu-id="db3b0-129">在工作列上的搜尋方塊中，輸入**修復磁碟機**，然後從結果中選取建立修復**磁碟機\*\*\*\*機或**修復磁碟機機。</span><span class="sxs-lookup"><span data-stu-id="db3b0-129">In the search box on the taskbar, enter **recovery drive**, and then select **Create a recovery drive** or **Recovery Drive** from the results.</span></span> <span data-ttu-id="db3b0-130">您可能需要輸入系統管理員密碼或確認您的選擇。</span><span class="sxs-lookup"><span data-stu-id="db3b0-130">You may need to enter an admin password or confirm your choice.</span></span>

1. <span data-ttu-id="db3b0-131">在使用者帳戶**控制方塊中**，選取**Yes。**</span><span class="sxs-lookup"><span data-stu-id="db3b0-131">In the **User Account Control** box, select **Yes**.</span></span>

1. <span data-ttu-id="db3b0-132">請務必清除備份系統檔案\*\*\*\* 到修復磁碟機核取方塊，然後選取下**一步**。</span><span class="sxs-lookup"><span data-stu-id="db3b0-132">Make sure to clear the **Back up system files to the recovery drive** check box and then select **Next**.</span></span>

1. <span data-ttu-id="db3b0-133">選取您的 USB 磁碟機，然後選取下一 **>建立**。</span><span class="sxs-lookup"><span data-stu-id="db3b0-133">Select your USB drive, and then select **Next > Create**.</span></span>  <span data-ttu-id="db3b0-134">有些公用程式需要複製到修復磁碟機機，因此這可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="db3b0-134">Some utilities need to be copied to the recovery drive, so this might take a few minutes.</span></span>

1. <span data-ttu-id="db3b0-135">當修復磁碟機準備就緒時， **請選取完成**。</span><span class="sxs-lookup"><span data-stu-id="db3b0-135">When the recovery drive is ready, select **Finish**.</span></span>

1. <span data-ttu-id="db3b0-136">按兩下您先前下載的復原映射 .zip 檔案以開啟該檔案。</span><span class="sxs-lookup"><span data-stu-id="db3b0-136">Double-click the recovery image .zip file that you previously downloaded to open it.</span></span>

1. <span data-ttu-id="db3b0-137">從復原映射資料夾中選取所有檔案，將它們複製到 USB 磁碟機的根目錄，然後選取選擇 **以取代目的地中的檔案**。</span><span class="sxs-lookup"><span data-stu-id="db3b0-137">Select all the files from the recovery image folder, copy them to the root of your USB drive, and then select **Choose to replace the files in the destination**.</span></span>

1. <span data-ttu-id="db3b0-138">檔案複製完成後，請選取工作列上的安全移除 **硬體與彈出** 媒體圖示，然後移除您的 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="db3b0-138">Once the files have finished copying, select the **Safely Remove Hardware and Eject Media** icon on the taskbar, and remove your USB drive.</span></span>

1. <span data-ttu-id="db3b0-139">將 USB 磁碟機連接到 Surface Hub 2S 上的任何 USB-C 或 USB-A 埠。</span><span class="sxs-lookup"><span data-stu-id="db3b0-139">Connect the USB drive to any USB-C or USB-A port on the Surface Hub 2S.</span></span>

1. <span data-ttu-id="db3b0-140">關閉集線器，然後執行下列步驟從 USB 磁碟機開機：</span><span class="sxs-lookup"><span data-stu-id="db3b0-140">Turn off the Hub and then take these steps to boot from the USB drive:</span></span>

   1. <span data-ttu-id="db3b0-141">按下音量降低按鈕時，請按電源按鈕。</span><span class="sxs-lookup"><span data-stu-id="db3b0-141">While pressing the Volume down button, press the Power button.</span></span>
   1. <span data-ttu-id="db3b0-142">繼續按這兩個按鈕，直到您看到 Windows 標誌。</span><span class="sxs-lookup"><span data-stu-id="db3b0-142">Keep pressing both buttons until you see the Windows logo.</span></span>
   1. <span data-ttu-id="db3b0-143">放開電源按鈕，但繼續按住音量降低按鈕，直到安裝 UI 開始。</span><span class="sxs-lookup"><span data-stu-id="db3b0-143">Release the Power button but continue to hold the Volume down button until the Install UI begins.</span></span>

      ![*使用降低音量和電源按鈕來啟動復原*](images/sh2-keypad.png)
      <br>*<span data-ttu-id="db3b0-145">圖 2.</span><span class="sxs-lookup"><span data-stu-id="db3b0-145">Figure 2.</span></span> <span data-ttu-id="db3b0-146">音量和電源按鈕</span><span class="sxs-lookup"><span data-stu-id="db3b0-146">Volume and Power buttons</span></span>*

1. <span data-ttu-id="db3b0-147">在語言選取畫面上，選取 Surface Hub 2S 的顯示語言。</span><span class="sxs-lookup"><span data-stu-id="db3b0-147">On the language selection screen, select the display language for your Surface Hub 2S.</span></span>

1. <span data-ttu-id="db3b0-148">選取**從磁碟機復原並\*\*\*\*完全清除硬碟**，**然後選取復原**。</span><span class="sxs-lookup"><span data-stu-id="db3b0-148">Select **Recover from a drive** and **Fully clean the drive**, and then select **Recover**.</span></span> <span data-ttu-id="db3b0-149">如果系統提示您輸入 BitLocker 鍵，請選取 **跳過此磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="db3b0-149">If you're prompted for a BitLocker key, select **Skip this drive**.</span></span> <span data-ttu-id="db3b0-150">Surface Hub 2S 會重新開機數次，大約需要 30 分鐘才能完成復原程式。</span><span class="sxs-lookup"><span data-stu-id="db3b0-150">Surface Hub 2S reboots several times and takes approximately 30 minutes to complete the recovery process.</span></span>

<span data-ttu-id="db3b0-151">第一次設定畫面出現時，請移除 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="db3b0-151">When the first-time setup screen appears, remove the USB drive.</span></span>

## <span data-ttu-id="db3b0-152">連絡客戶支援</span><span class="sxs-lookup"><span data-stu-id="db3b0-152">Contact Support</span></span>

<span data-ttu-id="db3b0-153">如果您有任何問題或需要協助，您可以 [建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。</span><span class="sxs-lookup"><span data-stu-id="db3b0-153">If you have questions or need help, you can [create a support request](https://support.microsoft.com/supportforbusiness/productselection).</span></span>
