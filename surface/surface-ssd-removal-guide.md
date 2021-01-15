---
title: 相容 Surface 裝置中的 SSD 移除
description: 本文適用于合格的 IT 技術人員，說明在 Surface 膝上型電腦3、Surface Pro X 和 Surface 膝上型電腦版中移除及取代 SSDs 的建議最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270628"
---
# <span data-ttu-id="00520-103">從相容的 Surface 裝置移除 SSD 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="00520-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00520-104">本文僅供企業組織中合格的 IT 技術人員使用。</span><span class="sxs-lookup"><span data-stu-id="00520-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="00520-105">它描述由合格的 IT 技術人員在下列相容 Surface 裝置中移除及取代 SSDs 的建議最佳做法：</span><span class="sxs-lookup"><span data-stu-id="00520-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="00520-106">Surface Pro 7 +</span><span class="sxs-lookup"><span data-stu-id="00520-106">Surface Pro 7+</span></span>
- <span data-ttu-id="00520-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="00520-107">Surface Pro X</span></span>
- <span data-ttu-id="00520-108">Surface 膝上型電腦前往</span><span class="sxs-lookup"><span data-stu-id="00520-108">Surface Laptop Go</span></span>
- <span data-ttu-id="00520-109">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="00520-109">Surface Laptop 3</span></span>

> [!WARNING]
> <span data-ttu-id="00520-110">開啟裝置和取代裝置元件可能會帶來電擊、裝置損壞、火災及個人傷亡風險，以及其他危害。</span><span class="sxs-lookup"><span data-stu-id="00520-110">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="00520-111">當您執行這類活動時，請務必謹慎使用。</span><span class="sxs-lookup"><span data-stu-id="00520-111">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="00520-112">遵循 [企業 RSSD 移除指南](https://www.microsoft.com/download/100440)中所識別的安全預防措施和程式。</span><span class="sxs-lookup"><span data-stu-id="00520-112">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="00520-113">如果您無法遵循「在企業版 rSSD 移除指南」中所指定的安全預防措施及程式，我們建議您取得專業協助。</span><span class="sxs-lookup"><span data-stu-id="00520-113">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="00520-114">必要條件</span><span class="sxs-lookup"><span data-stu-id="00520-114">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="00520-115">本文假設您瞭解「適用于企業的 rSSD 移除指南」中所述的一般安全預防措施及安全原則與程式。</span><span class="sxs-lookup"><span data-stu-id="00520-115">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="00520-116">準備進行 SSD 移除</span><span class="sxs-lookup"><span data-stu-id="00520-116">Prepare for SSD removal</span></span> 

### <span data-ttu-id="00520-117">安裝最新的更新</span><span class="sxs-lookup"><span data-stu-id="00520-117">Install the latest updates</span></span> 

<span data-ttu-id="00520-118">在開始之前，請確定您的 Windows 版本已安裝最新的更新：</span><span class="sxs-lookup"><span data-stu-id="00520-118">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="00520-119">移至 [**啟動**  >  **設定**  >  **更新 & 安全性**]，然後選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="00520-119">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="00520-120">安裝所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="00520-120">Install all available updates.</span></span>
3. <span data-ttu-id="00520-121">確認任何存取裝置所需的密碼。</span><span class="sxs-lookup"><span data-stu-id="00520-121">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="00520-122">[管理 BitLocker]</span><span class="sxs-lookup"><span data-stu-id="00520-122">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="00520-123">本節包含對硬碟啟用 BitLocker 加密的組織的建議。</span><span class="sxs-lookup"><span data-stu-id="00520-123">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="00520-124">如需詳細資訊，請參閱  [BitLocker 恢復指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="00520-124">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="00520-125">如果在 SSD 移除與取代期間停用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="00520-125">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="00520-126">如果可在 SSD 移除與取代之前解除加密裝置，請遵循下列步驟關閉 BitLocker：</span><span class="sxs-lookup"><span data-stu-id="00520-126">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="00520-127">在 [ **設定**] 中，輸入 **BitLocker** ，然後選取 [ **管理 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="00520-127">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="00520-128">選取 [ **關閉 BitLocker**]。</span><span class="sxs-lookup"><span data-stu-id="00520-128">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="00520-129">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="00520-129">Power down the device.</span></span> 

### <span data-ttu-id="00520-130">如果在 SSD 移除與取代期間啟用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="00520-130">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="00520-131">如果在 SSD 移除和取代之前，裝置經過加密，請遵循下列步驟來產生 BitLocker 復原金鑰，並將它儲存至 USB 儲存空間：</span><span class="sxs-lookup"><span data-stu-id="00520-131">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="00520-132">在 [ **設定**] 中，輸入 **BitLocker**。</span><span class="sxs-lookup"><span data-stu-id="00520-132">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="00520-133">選取 [**管理 bitlocker**  > **產生 bitlocker 復原金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="00520-133">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="00520-134">插入 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="00520-134">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="00520-135">將修復金鑰儲存至 USB 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="00520-135">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="00520-136">移除 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="00520-136">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="00520-137">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="00520-137">Power down the device.</span></span> 

## <span data-ttu-id="00520-138">移除並取代 SSD</span><span class="sxs-lookup"><span data-stu-id="00520-138">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="00520-139">使用適用于 [企業的 RSSD 移除指南](https://www.microsoft.com/download/100440)中所包含的裝置指示，移除 SSD。</span><span class="sxs-lookup"><span data-stu-id="00520-139">Remove the SSD by using the appropriate instructions for your device included in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="00520-140">將原始的 SSD 放入新的裝置，並將新裝置連接至有線網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="00520-140">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="00520-141">開啟新裝置的電源。</span><span class="sxs-lookup"><span data-stu-id="00520-141">Power on the new device.</span></span> <span data-ttu-id="00520-142">在啟動期間，裝置可能會進行固件更新。</span><span class="sxs-lookup"><span data-stu-id="00520-142">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="00520-143">在 SSD 移除和取代後</span><span class="sxs-lookup"><span data-stu-id="00520-143">After SSD removal and replacement</span></span>

### <span data-ttu-id="00520-144">管理未加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="00520-144">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="00520-145">如果 SSD 在傳輸期間未加密，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="00520-145">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="00520-146">移至 [登**入選項**]  >  (左側的 [金鑰] 圖示所代表的**密碼**) 。</span><span class="sxs-lookup"><span data-stu-id="00520-146">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="00520-147">輸入密碼，並登入 [待處理的雙因素驗證] (（如果適用的話）) 。</span><span class="sxs-lookup"><span data-stu-id="00520-147">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="00520-148">當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。</span><span class="sxs-lookup"><span data-stu-id="00520-148">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="00520-149">使用密碼重新登入，並在系統提示時設定 Windows Hello 和 PIN。</span><span class="sxs-lookup"><span data-stu-id="00520-149">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="00520-150">如果裝置已在 BitLocker 停用，以協助 SSD 移除及取代，且您想要在更換之後啟用 bitlocker，請移至**bitlocker**  >  **管理 bitlocker**[  >  **繼續 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="00520-150">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="00520-151">執行適用于商務 () SDT 的 [Microsoft Surface 診斷工具](surface-diagnostic-toolkit-for-business-intro.md) 組，以驗證完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="00520-151">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="00520-152">流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="00520-152">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="00520-153">如果您看到任何錯誤訊息，請選取 [ **疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="00520-153">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="00520-154">開啟**office 應用程式**，然後**流覽至 [** 檔案  >  **帳戶**]，然後檢查是否有任何錯誤訊息，以檢查 office 帳戶。</span><span class="sxs-lookup"><span data-stu-id="00520-154">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="00520-155">管理加密 SSDs</span><span class="sxs-lookup"><span data-stu-id="00520-155">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="00520-156">您必須有第二個裝置，才能讀取儲存在 USB 磁片磁碟機上的 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="00520-156">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="00520-157">如果 SSD 在傳輸期間經過加密，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="00520-157">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="00520-158">將內含 BitLocker 復原金鑰的 USB 磁片磁碟機插入第二個裝置。</span><span class="sxs-lookup"><span data-stu-id="00520-158">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="00520-159">開啟內含 Bitlocker 復原金鑰的 .txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="00520-159">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="00520-160">在包含原始 SSD 的新裝置上手動輸入 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="00520-160">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="00520-161">成功輸入 BitLocker 復原金鑰之後，請移至 [登**入選項**]  >  (左邊的 [金鑰] 圖示所代表的**密碼**) 。</span><span class="sxs-lookup"><span data-stu-id="00520-161">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="00520-162">如果適用) 的話，請輸入密碼並登入，以待執行的雙因素驗證 (完成。</span><span class="sxs-lookup"><span data-stu-id="00520-162">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="00520-163">當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。</span><span class="sxs-lookup"><span data-stu-id="00520-163">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="00520-164">使用密碼重新登入，然後設定 Windows Hello 並新增 PIN。</span><span class="sxs-lookup"><span data-stu-id="00520-164">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="00520-165">如果裝置是 BitLocker 停用的，可協助 SSD 移除及取代，而且如果您想要在更換後啟用 bitlocker，請移至 [**設定**  >  **bitlocker**  >  **管理 bitlocker**  >  **繼續 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="00520-165">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="00520-166">執行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以驗證完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="00520-166">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="00520-167">若要查看 Windows 啟用，請選取 [**設定**  >  **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="00520-167">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="00520-168">如果您看到任何錯誤訊息，請選取 [ **疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="00520-168">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="00520-169">若要檢查 office 帳戶的狀態，請開啟**office 應用程式**，然後**移至 [** 檔案帳戶]，  >  \*\*\*\* 檢查是否有任何錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="00520-169">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="00520-170">深入了解</span><span class="sxs-lookup"><span data-stu-id="00520-170">Learn more</span></span>

- [<span data-ttu-id="00520-171">企業版的 rSSD 移除指南</span><span class="sxs-lookup"><span data-stu-id="00520-171">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="00520-172">BitLocker 修復指南</span><span class="sxs-lookup"><span data-stu-id="00520-172">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="00520-173">仍需要協助？</span><span class="sxs-lookup"><span data-stu-id="00520-173">Still need help?</span></span> <span data-ttu-id="00520-174">移至 [Microsoft 社區](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="00520-174">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>