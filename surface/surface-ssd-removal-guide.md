---
title: 相容 Surface 裝置中的 SSD 移除
description: 本文適用于合格的 IT 技術人員，說明在 Surface Laptop 4、Surface Laptop 3、Surface Pro 7+、Surface Pro X 和 Surface Laptop Go 中移除和取代 SSD 的建議最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 7ba66981c021f1f0a08ebf33aab0a73481111a4d
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576903"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a><span data-ttu-id="32bfc-103">從相容的 Surface 裝置移除 SSD 的最佳作法</span><span class="sxs-lookup"><span data-stu-id="32bfc-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32bfc-104">本文僅供企業組織中合格的 IT 技術人員使用。</span><span class="sxs-lookup"><span data-stu-id="32bfc-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="32bfc-105">本文說明合格 IT 技術人員在移除及取代下列相容 Surface 裝置中的 SSD 時所建議的最佳作法：</span><span class="sxs-lookup"><span data-stu-id="32bfc-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="32bfc-106">Surface Pro 7+</span><span class="sxs-lookup"><span data-stu-id="32bfc-106">Surface Pro 7+</span></span>
- <span data-ttu-id="32bfc-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="32bfc-107">Surface Pro X</span></span>
- <span data-ttu-id="32bfc-108">Surface Laptop去</span><span class="sxs-lookup"><span data-stu-id="32bfc-108">Surface Laptop Go</span></span>
- <span data-ttu-id="32bfc-109">Surface Laptop 3</span><span class="sxs-lookup"><span data-stu-id="32bfc-109">Surface Laptop 3</span></span>
- <span data-ttu-id="32bfc-110">Surface Laptop 4</span><span class="sxs-lookup"><span data-stu-id="32bfc-110">Surface Laptop 4</span></span>

> [!WARNING]
> <span data-ttu-id="32bfc-111">開啟裝置及取代裝置元件時，可能會造成觸電、裝置損壞、起火和個人傷亡風險，以及其他危險。</span><span class="sxs-lookup"><span data-stu-id="32bfc-111">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="32bfc-112">進行這類活動時，務必小心。</span><span class="sxs-lookup"><span data-stu-id="32bfc-112">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="32bfc-113">請遵循[rSSD](https://www.microsoft.com/download/100440)移除指南所識別的安全注意事項Enterprise。</span><span class="sxs-lookup"><span data-stu-id="32bfc-113">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="32bfc-114">如果您無法遵循「rSSD 移除指南」中指定的安全注意事項和程式，建議您獲得專業協助Enterprise。</span><span class="sxs-lookup"><span data-stu-id="32bfc-114">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prerequisites"></a><span data-ttu-id="32bfc-115">必要條件</span><span class="sxs-lookup"><span data-stu-id="32bfc-115">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32bfc-116">本文假設您瞭解「rSSD 移除指南」所述的一般安全注意事項及安全Enterprise。</span><span class="sxs-lookup"><span data-stu-id="32bfc-116">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <a name="prepare-for-ssd-removal"></a><span data-ttu-id="32bfc-117">準備移除 SSD</span><span class="sxs-lookup"><span data-stu-id="32bfc-117">Prepare for SSD removal</span></span> 

### <a name="install-the-latest-updates"></a><span data-ttu-id="32bfc-118">安裝最新更新</span><span class="sxs-lookup"><span data-stu-id="32bfc-118">Install the latest updates</span></span> 

<span data-ttu-id="32bfc-119">開始之前，請確定您的 Windows已安裝最新的更新：</span><span class="sxs-lookup"><span data-stu-id="32bfc-119">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="32bfc-120">請前往\*\*\*\* 開始  >  **設定**  >  **更新&安全性**，然後選取**檢查更新**。</span><span class="sxs-lookup"><span data-stu-id="32bfc-120">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="32bfc-121">安裝所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="32bfc-121">Install all available updates.</span></span>
3. <span data-ttu-id="32bfc-122">驗證存取裝置所需的任何密碼。</span><span class="sxs-lookup"><span data-stu-id="32bfc-122">Verify any passwords that are necessary to access the device.</span></span>  
 
## <a name="manage-bitlocker"></a><span data-ttu-id="32bfc-123">[管理 BitLocker]</span><span class="sxs-lookup"><span data-stu-id="32bfc-123">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="32bfc-124">本節包含已啟用硬碟加密BitLocker組織的建議。</span><span class="sxs-lookup"><span data-stu-id="32bfc-124">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="32bfc-125">詳細資訊，請參閱修復BitLocker[指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="32bfc-125">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="32bfc-126">如果在BitLocker和更換 SSD 期間停用加密功能</span><span class="sxs-lookup"><span data-stu-id="32bfc-126">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="32bfc-127">如果裝置在移除和更換 SSD 之前可以取消加密，請按照下列步驟關閉BitLocker：</span><span class="sxs-lookup"><span data-stu-id="32bfc-127">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="32bfc-128">在**設定\*\*\*\*中，輸入**BitLocker，然後選取**管理 BitLocker。**</span><span class="sxs-lookup"><span data-stu-id="32bfc-128">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="32bfc-129">選取**關閉 BitLocker。**</span><span class="sxs-lookup"><span data-stu-id="32bfc-129">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="32bfc-130">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="32bfc-130">Power down the device.</span></span> 

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a><span data-ttu-id="32bfc-131">如果在BITLOCKER和更換期間啟用加密功能</span><span class="sxs-lookup"><span data-stu-id="32bfc-131">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="32bfc-132">如果裝置在移除和更換 SSD 之前經過加密，請按照下列步驟產生BitLocker金鑰，並將其儲存到 USB 儲存空間：</span><span class="sxs-lookup"><span data-stu-id="32bfc-132">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="32bfc-133">在**設定\*\*\*\*中，輸入**BitLocker。</span><span class="sxs-lookup"><span data-stu-id="32bfc-133">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="32bfc-134">選取**管理 BitLocker**  > **產生BitLocker金鑰**。</span><span class="sxs-lookup"><span data-stu-id="32bfc-134">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="32bfc-135">插入 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="32bfc-135">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="32bfc-136">將修復金鑰儲存到 USB 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="32bfc-136">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="32bfc-137">移除 USB 磁碟機。</span><span class="sxs-lookup"><span data-stu-id="32bfc-137">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="32bfc-138">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="32bfc-138">Power down the device.</span></span> 

## <a name="remove-and-replace-ssd"></a><span data-ttu-id="32bfc-139">移除及取代 SSD</span><span class="sxs-lookup"><span data-stu-id="32bfc-139">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="32bfc-140">使用[rSSD](https://www.microsoft.com/download/100440)移除指南中適用于您裝置的適當指示來移除ENTERPRISE。</span><span class="sxs-lookup"><span data-stu-id="32bfc-140">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="32bfc-141">將原始的 SSD 放入新裝置，然後將新裝置連接到有線網際網路連接。</span><span class="sxs-lookup"><span data-stu-id="32bfc-141">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="32bfc-142">在新裝置上電源。</span><span class="sxs-lookup"><span data-stu-id="32bfc-142">Power on the new device.</span></span> <span data-ttu-id="32bfc-143">裝置在啟動期間可能會經歷一次固件更新。</span><span class="sxs-lookup"><span data-stu-id="32bfc-143">The device may go through a firmware update during startup.</span></span>  
 
## <a name="after-ssd-removal-and-replacement"></a><span data-ttu-id="32bfc-144">在移除和取代 SSD 之後</span><span class="sxs-lookup"><span data-stu-id="32bfc-144">After SSD removal and replacement</span></span>

### <a name="manage-unencrypted-ssds"></a><span data-ttu-id="32bfc-145">管理未加密的 SSD</span><span class="sxs-lookup"><span data-stu-id="32bfc-145">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="32bfc-146">如果在傳輸期間未加密 SSD，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="32bfc-146">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="32bfc-147">請**前往左側按鍵** (以代表的登錄選項密碼  >  \*\* \*\*) 。</span><span class="sxs-lookup"><span data-stu-id="32bfc-147">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="32bfc-148">輸入密碼並完成雙因素驗證並 (如果適用) 。</span><span class="sxs-lookup"><span data-stu-id="32bfc-148">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="32bfc-149">完成登錄後，請前往**開始**  >  **帳戶**  >  **登出**。</span><span class="sxs-lookup"><span data-stu-id="32bfc-149">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="32bfc-150">使用密碼重新登錄，並設定Windows時輸入 Hello 和 PIN。</span><span class="sxs-lookup"><span data-stu-id="32bfc-150">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="32bfc-151">如果裝置已停用BitLocker以利於 SSD 移除和更換，而您想要在更換之後啟用 BitLocker，請前往 BitLocker 管理 BitLocker\*\* \*\*  >  \*\*\*\*  >  **繼續**BitLocker。</span><span class="sxs-lookup"><span data-stu-id="32bfc-151">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="32bfc-152">執行 [商務用 Microsoft Surface 診斷工具 (](surface-diagnostic-toolkit-for-business-intro.md) SDT) 驗證完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="32bfc-152">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="32bfc-153">流覽至 Windows 啟用 以**檢查設定**  >  **啟用**。</span><span class="sxs-lookup"><span data-stu-id="32bfc-153">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="32bfc-154">如果您看到任何錯誤訊息，請選取 疑 **難解答**。</span><span class="sxs-lookup"><span data-stu-id="32bfc-154">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="32bfc-155">開啟 Office App，流覽至**檔案**Office帳戶，然後\*\*\*\*  >  \*\*\*\* 檢查是否有錯誤訊息，以檢查帳戶。</span><span class="sxs-lookup"><span data-stu-id="32bfc-155">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <a name="managing-encrypted-ssds"></a><span data-ttu-id="32bfc-156">管理加密的 SSD</span><span class="sxs-lookup"><span data-stu-id="32bfc-156">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="32bfc-157">您必須有第二個裝置，BitLocker USB 磁碟機上儲存的修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="32bfc-157">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="32bfc-158">如果在傳輸期間將 SSD 加密，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="32bfc-158">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="32bfc-159">將包含修復金鑰BitLocker USB 磁碟機插入第二個裝置。</span><span class="sxs-lookup"><span data-stu-id="32bfc-159">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="32bfc-160">開啟.txt Bitlocker 修復金鑰的檔案。</span><span class="sxs-lookup"><span data-stu-id="32bfc-160">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="32bfc-161">在包含原始BITLOCKER的新裝置上，手動輸入修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="32bfc-161">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="32bfc-162">成功輸入修復金鑰BitLocker，請前往左側按鍵圖示 (的登錄選項\*\*\*\* 密碼  >  \*\* \*\*) 。</span><span class="sxs-lookup"><span data-stu-id="32bfc-162">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="32bfc-163">在雙因素驗證完成之前，輸入密碼並 (並) 。</span><span class="sxs-lookup"><span data-stu-id="32bfc-163">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="32bfc-164">完成登錄後，請前往**開始**  >  **帳戶**  >  **登出**。</span><span class="sxs-lookup"><span data-stu-id="32bfc-164">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="32bfc-165">使用密碼重新登錄，然後設定 Windows Hello 並新增 PIN。</span><span class="sxs-lookup"><span data-stu-id="32bfc-165">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="32bfc-166">如果裝置已停用BitLocker以利於 SSD 移除和更換，而且如果您想要在更換之後啟用 BitLocker，請前往 設定**BitLocker**管理 BitLocker  >  \*\*\*\*  >  \*\*\*\*  >  **繼續**BitLocker。</span><span class="sxs-lookup"><span data-stu-id="32bfc-166">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="32bfc-167">執行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以驗證完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="32bfc-167">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="32bfc-168">若要檢查Windows，請選取 設定\*\*\*\*  >  **啟用**。</span><span class="sxs-lookup"><span data-stu-id="32bfc-168">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="32bfc-169">如果您看到任何錯誤訊息，請選取 疑 **難解答**。</span><span class="sxs-lookup"><span data-stu-id="32bfc-169">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="32bfc-170">若要檢查帳戶Office，請開啟 Office **App，** 然後前往檔案帳戶檢查\*\*\*\*  >  \*\*\*\* 是否有錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="32bfc-170">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <a name="learn-more"></a><span data-ttu-id="32bfc-171">深入了解</span><span class="sxs-lookup"><span data-stu-id="32bfc-171">Learn more</span></span>

- [<span data-ttu-id="32bfc-172">rSSD 移除指南Enterprise</span><span class="sxs-lookup"><span data-stu-id="32bfc-172">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="32bfc-173">BitLocker 修復指南</span><span class="sxs-lookup"><span data-stu-id="32bfc-173">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="32bfc-174">仍需要協助？</span><span class="sxs-lookup"><span data-stu-id="32bfc-174">Still need help?</span></span> <span data-ttu-id="32bfc-175">前往[Microsoft Community。](https://answers.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="32bfc-175">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>