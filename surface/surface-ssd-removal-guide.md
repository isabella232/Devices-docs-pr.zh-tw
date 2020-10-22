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
ms.date: 10/21/2020
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
- Surface Laptop Go
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 56c740b39d86ea3fab386e88efa6932e050bb957
ms.sourcegitcommit: 959d2d856b1e5b5c72cd636f576b5feb1b633048
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/21/2020
ms.locfileid: "11133168"
---
# <span data-ttu-id="8b4b8-103">從相容的 Surface 裝置移除 SSD 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="8b4b8-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b4b8-104">本文僅供企業組織中合格的 IT 技術人員使用。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="8b4b8-105">它描述由合格的 IT 技術人員在下列相容 Surface 裝置中移除及取代 SSDs 的建議最佳做法：</span><span class="sxs-lookup"><span data-stu-id="8b4b8-105">It describes the recommended best practices for use by qualified IT technicians in the removal and replacement of SSDs in the following compatible Surface devices:</span></span> 

- <span data-ttu-id="8b4b8-106">Surface 膝上型電腦3</span><span class="sxs-lookup"><span data-stu-id="8b4b8-106">Surface Laptop 3</span></span> 
- <span data-ttu-id="8b4b8-107">Surface Pro X</span><span class="sxs-lookup"><span data-stu-id="8b4b8-107">Surface Pro X</span></span> 
- <span data-ttu-id="8b4b8-108">Surface 膝上型電腦前往</span><span class="sxs-lookup"><span data-stu-id="8b4b8-108">Surface Laptop Go</span></span>

> [!WARNING]
> <span data-ttu-id="8b4b8-109">開啟裝置和取代裝置元件可能會帶來電擊、裝置損壞、火災及個人傷亡風險，以及其他危害。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-109">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="8b4b8-110">當您執行這類活動時，請務必謹慎使用。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-110">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="8b4b8-111">遵循 [企業 RSSD 移除指南](https://www.microsoft.com/download/100440)中所識別的安全預防措施和程式。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-111">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="8b4b8-112">如果您無法遵循「在企業版 rSSD 移除指南」中所指定的安全預防措施及程式，我們建議您取得專業協助。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-112">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="8b4b8-113">必要條件</span><span class="sxs-lookup"><span data-stu-id="8b4b8-113">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b4b8-114">本文假設您瞭解「適用于企業的 rSSD 移除指南」中所述的一般安全預防措施及安全原則與程式。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-114">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="8b4b8-115">準備進行 SSD 移除</span><span class="sxs-lookup"><span data-stu-id="8b4b8-115">Prepare for SSD removal</span></span> 

### <span data-ttu-id="8b4b8-116">安裝最新的更新</span><span class="sxs-lookup"><span data-stu-id="8b4b8-116">Install the latest updates</span></span> 

<span data-ttu-id="8b4b8-117">在開始之前，請確定您的 Windows 版本已安裝最新的更新：</span><span class="sxs-lookup"><span data-stu-id="8b4b8-117">Before you begin, make sure that your version of Windows has the latest updates installed:</span></span>

1.  <span data-ttu-id="8b4b8-118">移至 [**啟動**  >  **設定**  >  **更新 & 安全性**]，然後選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-118">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span>
2. <span data-ttu-id="8b4b8-119">安裝所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-119">Install all available updates.</span></span>
3. <span data-ttu-id="8b4b8-120">確認任何存取裝置所需的密碼。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-120">Verify any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="8b4b8-121">[管理 BitLocker]</span><span class="sxs-lookup"><span data-stu-id="8b4b8-121">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="8b4b8-122">本節包含對硬碟啟用 BitLocker 加密的組織的建議。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-122">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="8b4b8-123">如需詳細資訊，請參閱  [BitLocker 恢復指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-123">For more information, see  [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="8b4b8-124">如果在 SSD 移除與取代期間停用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="8b4b8-124">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="8b4b8-125">如果可在 SSD 移除與取代之前解除加密裝置，請遵循下列步驟關閉 BitLocker：</span><span class="sxs-lookup"><span data-stu-id="8b4b8-125">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="8b4b8-126">在 [ **設定**] 中，輸入 **BitLocker** ，然後選取 [ **管理 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-126">In **Settings**, type **BitLocker** and then select **Manage BitLocker**.</span></span> 
2.  <span data-ttu-id="8b4b8-127">選取 [ **關閉 BitLocker**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-127">Select **Turn Off BitLocker**.</span></span> 
3.  <span data-ttu-id="8b4b8-128">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-128">Power down the device.</span></span> 

### <span data-ttu-id="8b4b8-129">如果在 SSD 移除與取代期間啟用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="8b4b8-129">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="8b4b8-130">如果在 SSD 移除和取代之前，裝置經過加密，請遵循下列步驟來產生 BitLocker 復原金鑰，並將它儲存至 USB 儲存空間：</span><span class="sxs-lookup"><span data-stu-id="8b4b8-130">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="8b4b8-131">在 [ **設定**] 中，輸入 **BitLocker**。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-131">In **Settings**, type **BitLocker**.</span></span>
2. <span data-ttu-id="8b4b8-132">選取 [**管理 bitlocker**  > **產生 bitlocker 復原金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-132">Select **Manage BitLocker** >**Generate BitLocker Recovery Key**.</span></span>
2.  <span data-ttu-id="8b4b8-133">插入 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-133">Insert a USB drive.</span></span> 
4.  <span data-ttu-id="8b4b8-134">將修復金鑰儲存至 USB 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-134">Save the recovery key to USB storage.</span></span>  
5.  <span data-ttu-id="8b4b8-135">移除 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-135">Remove the USB drive.</span></span>  
6.  <span data-ttu-id="8b4b8-136">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-136">Power down the device.</span></span> 

## <span data-ttu-id="8b4b8-137">移除並取代 SSD</span><span class="sxs-lookup"><span data-stu-id="8b4b8-137">Remove and replace SSD</span></span> 

1.  <span data-ttu-id="8b4b8-138">使用適用于 [企業的 RSSD 移除指南](https://www.microsoft.com/download/100440)中的指示來移除 SSD。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-138">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2.  <span data-ttu-id="8b4b8-139">將原始的 SSD 放入新的裝置，並將新裝置連接至有線網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-139">Put the original SSD into a new device and connect the new device to a wired internet connection.</span></span>
3.  <span data-ttu-id="8b4b8-140">開啟新裝置的電源。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-140">Power on the new device.</span></span> <span data-ttu-id="8b4b8-141">在啟動期間，裝置可能會進行固件更新。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-141">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="8b4b8-142">在 SSD 移除和取代後</span><span class="sxs-lookup"><span data-stu-id="8b4b8-142">After SSD removal and replacement</span></span>

### <span data-ttu-id="8b4b8-143">管理未加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="8b4b8-143">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="8b4b8-144">如果 SSD 在傳輸期間未加密，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8b4b8-144">If the SSD is unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="8b4b8-145">移至 [登**入選項**]  >  (左側的 [金鑰] 圖示所代表的**密碼**) 。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-145">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="8b4b8-146">輸入密碼，並登入 [待處理的雙因素驗證] (（如果適用的話）) 。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-146">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="8b4b8-147">當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-147">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="8b4b8-148">使用密碼重新登入，並在系統提示時設定 Windows Hello 和 PIN。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-148">Sign back in by using the password and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="8b4b8-149">如果裝置已在 BitLocker 停用，以協助 SSD 移除及取代，且您想要在更換之後啟用 bitlocker，請移至**bitlocker**  >  **管理 bitlocker**[  >  **繼續 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-149">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
6.  <span data-ttu-id="8b4b8-150">執行適用于商務 () SDT 的 [Microsoft Surface 診斷工具](surface-diagnostic-toolkit-for-business-intro.md) 組，以驗證完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-150">Run the [Microsoft Surface Diagnostic Toolkit for Business](surface-diagnostic-toolkit-for-business-intro.md) (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="8b4b8-151">流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-151">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="8b4b8-152">如果您看到任何錯誤訊息，請選取 [ **疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-152">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="8b4b8-153">開啟**office 應用程式**，然後**流覽至 [** 檔案  >  **帳戶**]，然後檢查是否有任何錯誤訊息，以檢查 office 帳戶。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-153">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="8b4b8-154">管理加密 SSDs</span><span class="sxs-lookup"><span data-stu-id="8b4b8-154">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="8b4b8-155">您必須有第二個裝置，才能讀取儲存在 USB 磁片磁碟機上的 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-155">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="8b4b8-156">如果 SSD 在傳輸期間經過加密，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="8b4b8-156">If the SSD is encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="8b4b8-157">將內含 BitLocker 復原金鑰的 USB 磁片磁碟機插入第二個裝置。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-157">Insert the USB drive that contains the BitLocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="8b4b8-158">開啟內含 Bitlocker 復原金鑰的 .txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-158">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="8b4b8-159">在包含原始 SSD 的新裝置上手動輸入 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-159">Manually enter the BitLocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="8b4b8-160">成功輸入 BitLocker 復原金鑰之後，請移至 [登**入選項**]  >  (左邊的 [金鑰] 圖示所代表的**密碼**) 。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-160">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="8b4b8-161">如果適用) 的話，請輸入密碼並登入，以待執行的雙因素驗證 (完成。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-161">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="8b4b8-162">當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-162">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="8b4b8-163">使用密碼重新登入，然後設定 Windows Hello 並新增 PIN。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-163">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="8b4b8-164">如果裝置是 BitLocker 停用的，可協助 SSD 移除及取代，而且如果您想要在更換後啟用 bitlocker，請移至 [**設定**  >  **bitlocker**  >  **管理 bitlocker**  >  **繼續 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-164">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **BitLocker** > **Manage BitLocker** > **Resume BitLocker**.</span></span>  
9.  <span data-ttu-id="8b4b8-165">執行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以驗證完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-165">Run **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** to verify full device functionality.</span></span>  
10. <span data-ttu-id="8b4b8-166">若要查看 Windows 啟用，請選取 [**設定**  >  **啟用**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-166">To check Windows activation, select **Settings** > **Activation**.</span></span>  <span data-ttu-id="8b4b8-167">如果您看到任何錯誤訊息，請選取 [ **疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-167">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="8b4b8-168">若要檢查 office 帳戶的狀態，請開啟**office 應用程式**，然後**移至 [** 檔案帳戶]，  >  **Account**檢查是否有任何錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-168">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="8b4b8-169">深入了解</span><span class="sxs-lookup"><span data-stu-id="8b4b8-169">Learn more</span></span>

- [<span data-ttu-id="8b4b8-170">企業版的 rSSD 移除指南</span><span class="sxs-lookup"><span data-stu-id="8b4b8-170">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="8b4b8-171">BitLocker 修復指南</span><span class="sxs-lookup"><span data-stu-id="8b4b8-171">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="8b4b8-172">仍需要協助？</span><span class="sxs-lookup"><span data-stu-id="8b4b8-172">Still need help?</span></span> <span data-ttu-id="8b4b8-173">移至 [Microsoft 社區](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="8b4b8-173">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>