---
title: 相容 Surface 裝置中的 SSD 移除
description: 如何將 SSD 從一個 Surface 裝置轉移到另一個 Surface 裝置。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 9cde08c8106703b50218bf7f5ed60e3d7fea0b67
ms.sourcegitcommit: 83530906c7e34c92bbee90b723321acd61e77669
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/08/2020
ms.locfileid: "10918950"
---
# <span data-ttu-id="ef3d6-103">相容 Surface 裝置中的 SSD 移除最佳做法</span><span class="sxs-lookup"><span data-stu-id="ef3d6-103">Best practices for SSD removal in compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef3d6-104">本文僅供企業組織中合格的 IT 技術人員使用。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="ef3d6-105">它描述在使用 [可移動 SSDs] 移除及取代 Surface 裝置中的 SSDs 時，合格的 IT 技術人員所建議的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-105">It describes the recommended best practices for use by qualified IT technicians when removing and replacing SSDs in Surface devices with removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="ef3d6-106">開啟裝置和取代裝置元件可能會帶來電擊、裝置損壞、火災及個人傷亡風險，以及其他危害。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="ef3d6-107">在進行這類活動時，請務必小心。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-107">Always use caution when undertaking such activities.</span></span> <span data-ttu-id="ef3d6-108">遵循企業 rSSD 移除指南中所述的安全預防措施及程式。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-108">Follow the safety precautions and procedures identified in the rSSD Removal Guide for Enterprise.</span></span> <span data-ttu-id="ef3d6-109">如果您無法遵循在企業 rSSD 移除指南中所指定的安全預防措施及程式，Microsoft 建議您尋求專業協助。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-109">Microsoft recommends that you seek professional assistance if you are unable to follow the safety precautions and procedures specified in the rSSD Removal Guide for Enterprise.</span></span> 

## <span data-ttu-id="ef3d6-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="ef3d6-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef3d6-111">本文假設您瞭解[企業 RSSD 移除指南](https://www.microsoft.com/download/100440)中所述的一般安全預防措施及安全原則與程式。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-111">This article assumes you understand the General Safety Precautions and Safety policies and procedures described in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span>

## <span data-ttu-id="ef3d6-112">準備進行 SSD 移除</span><span class="sxs-lookup"><span data-stu-id="ef3d6-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="ef3d6-113">安裝最新的更新</span><span class="sxs-lookup"><span data-stu-id="ef3d6-113">Install the latest updates</span></span> 

<span data-ttu-id="ef3d6-114">開始之前，請確定您的 Windows 版本有最新的更新。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-114">Before you begin, make sure your version of Windows has the latest updates.</span></span>

1.  <span data-ttu-id="ef3d6-115">移至 [**啟動**  >  **設定**]  >  **& 安全性更新**，然後選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-115">Go to **Start** > **Settings** > **Update & Security** and select **Check for updates**.</span></span> <span data-ttu-id="ef3d6-116">安裝所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-116">Install all available updates.</span></span>  

2.  <span data-ttu-id="ef3d6-117">確認您有存取裝置所需的任何密碼。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-117">Confirm that you have any passwords needed to access the device.</span></span>  
 
## <span data-ttu-id="ef3d6-118">管理 Bitlocker</span><span class="sxs-lookup"><span data-stu-id="ef3d6-118">Manage Bitlocker</span></span> 

> [!NOTE]
> <span data-ttu-id="ef3d6-119">本節包含對硬碟啟用 BitLocker 加密的組織的建議。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-119">This section includes recommendations for organizations that have enabled BitLocker encryption for hard drives.</span></span> <span data-ttu-id="ef3d6-120">如需詳細資訊，請參閱[BitLocker 恢復指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-120">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="ef3d6-121">如果在 SSD 移除與取代期間停用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="ef3d6-121">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="ef3d6-122">如果可在 SSD 移除與取代之前解除加密裝置，請遵循下列步驟關閉 BitLocker：</span><span class="sxs-lookup"><span data-stu-id="ef3d6-122">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="ef3d6-123">在 [**設定**] 中，輸入**bitlocker** ，然後選取 [**管理 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-123">In **Settings**, type **Bitlocker** and select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="ef3d6-124">選取 [**關閉 Bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-124">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="ef3d6-125">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-125">Power down the device.</span></span> 

### <span data-ttu-id="ef3d6-126">如果在 SSD 移除與取代期間啟用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="ef3d6-126">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="ef3d6-127">如果在 SSD 移除和取代之前，裝置經過加密，請遵循下列步驟來產生 BitLocker 復原金鑰，並將它儲存至 USB 儲存空間：</span><span class="sxs-lookup"><span data-stu-id="ef3d6-127">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="ef3d6-128">移至 [**設定**]，然後輸入**Bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-128">Go to **Settings** and type **Bitlocker**.</span></span>
2. <span data-ttu-id="ef3d6-129">選取 [**管理 bitlocker**  > **產生 bitlocker 復原金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-129">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="ef3d6-130">插入 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-130">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="ef3d6-131">將修復金鑰儲存至 USB 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-131">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="ef3d6-132">移除 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-132">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="ef3d6-133">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-133">Power down the device.</span></span> 

## <span data-ttu-id="ef3d6-134">移除並取代 SSD</span><span class="sxs-lookup"><span data-stu-id="ef3d6-134">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="ef3d6-135">使用適用于[企業的 RSSD 移除指南](https://www.microsoft.com/download/100440)中的指示來移除 SSD。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-135">Remove the SSD using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="ef3d6-136">將原始的 SSD 放在新的裝置中，並將新裝置連接至有線網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-136">Place the original SSD in a new device and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="ef3d6-137">開啟新裝置的電源。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-137">Power on the new device.</span></span> <span data-ttu-id="ef3d6-138">在啟動期間，裝置可能會進行固件更新。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-138">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="ef3d6-139">在 SSD 移除和取代後</span><span class="sxs-lookup"><span data-stu-id="ef3d6-139">After SSD removal and replacement</span></span>

### <span data-ttu-id="ef3d6-140">管理未加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="ef3d6-140">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="ef3d6-141">如果 SSD 在傳輸期間保持不加密，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ef3d6-141">If the SSD remains unencrypted during the transfer, complete the following:</span></span> 

1.  <span data-ttu-id="ef3d6-142">移至 [登**入選項**]  >  [**密碼**] () 左邊的 [金鑰] 圖示表示。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-142">Go to **Sign-In Options** > **Password** (represented as the key icon on the left side).</span></span>  
2.  <span data-ttu-id="ef3d6-143">輸入密碼，並登入 [待處理的雙因素驗證] (（如果適用的話）) 。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-143">Enter the password and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="ef3d6-144">完全登入後，移至 [**開始**  >  **帳戶**  >  **登出**]。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-144">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="ef3d6-145">使用密碼重新登入，並在出現提示時設定 Windows Hello 和 PIN。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-145">Sign back in with the password and set up Windows Hello and a PIN when prompted.</span></span> 
    - <span data-ttu-id="ef3d6-146">如果裝置是 BitLocker 停用的，可協助您進行 SSD 移除及更換，而且您想要在更換之後啟用 bitlocker，請移至**bitlocker**  >  **管理 bitlocker**  >  **繼續 bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-146">If the device was BitLocker-disabled to facilitate SSD removal and replacement and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="ef3d6-147">執行**SDT**以確認完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-147">Run **SDT** to confirm full device functionality.</span></span>  
7.  <span data-ttu-id="ef3d6-148">流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-148">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="ef3d6-149">如果有任何錯誤訊息，請選取 [**疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-149">If there are any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="ef3d6-150">開啟**office 應用程式**，然後**流覽至 [** 檔案  >  **帳戶**] 並檢查是否有任何錯誤訊息，以檢查 office 帳戶。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-150">Check the Office account by opening the **Office App**, then navigate to **File** > **Account** and check for any error messages.</span></span>  

### <span data-ttu-id="ef3d6-151">管理加密 SSDs</span><span class="sxs-lookup"><span data-stu-id="ef3d6-151">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="ef3d6-152">您需要使用第二個裝置來讀取儲存在 USB 磁片磁碟機上的 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-152">You will need a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="ef3d6-153">如果 SSD 在傳輸期間仍保持加密，請完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ef3d6-153">If the SSD remained encrypted during the transfer, complete the following:</span></span>

1.  <span data-ttu-id="ef3d6-154">將包含 Bitlocker 復原金鑰的 USB 磁片磁碟機插入第二個裝置。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-154">Insert the USB drive containing the Bitlocker Recovery key into the second device.</span></span> 
2.  <span data-ttu-id="ef3d6-155">開啟包含 Bitlocker 復原金鑰的 .txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-155">Open the .txt file containing the Bitlocker Recovery key.</span></span> 
3.  <span data-ttu-id="ef3d6-156">手動在包含原始 SSD 的新裝置中輸入 Bitlocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-156">Manually enter the Bitlocker Recovery key into the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="ef3d6-157">成功輸入 BitLocker 復原金鑰之後，請移至 [登**入選項**]  >  (左邊的 [金鑰] 圖示所代表的**密碼**) 。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-157">After you have successfully entered the BitLocker Recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="ef3d6-158">如果適用，請輸入密碼並登入、未決完成雙因素驗證 (（如果有的話）) </span><span class="sxs-lookup"><span data-stu-id="ef3d6-158">Enter the password and sign in, pending completion of two-factor authentication (if applicable)</span></span> 
6.  <span data-ttu-id="ef3d6-159">完全登入後，移至 [**開始**  >  **帳戶**  >  **登出**]。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-159">Once fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="ef3d6-160">使用密碼重新登入，並設定 Windows Hello 並新增 PIN 碼。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-160">Sign back in with the password and set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="ef3d6-161">如果裝置已停用 BitLocker 以協助 SSD 移除及取代，且您想要在替換之後啟用 bitlocker，請移至**設定**  >  **bitlocker**  >  **管理 bitlocker**  >  **繼續 bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-161">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="ef3d6-162">執行**SDT**以確認完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-162">Run **SDT** to confirm full device functionality.</span></span>  
10. <span data-ttu-id="ef3d6-163">流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-163">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="ef3d6-164">如果有任何錯誤訊息，請選取 [**疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-164">If there are any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="ef3d6-165">若要檢查 office 帳戶，請開啟**office 應用程式**，然後移**至 [** 檔案  >  **帳戶**]，然後檢查是否有任何錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-165">To check the Office Account, open the **Office App**, then go to **File** > **Account** and check for any error messages.</span></span>

## <span data-ttu-id="ef3d6-166">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="ef3d6-166">More information</span></span> 

<span data-ttu-id="ef3d6-167">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="ef3d6-167">For more information, see the following articles:</span></span>

- [<span data-ttu-id="ef3d6-168">企業版的 rSSD 移除指南</span><span class="sxs-lookup"><span data-stu-id="ef3d6-168">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="ef3d6-169">BitLocker 修復指南</span><span class="sxs-lookup"><span data-stu-id="ef3d6-169">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="ef3d6-170">仍需要協助？</span><span class="sxs-lookup"><span data-stu-id="ef3d6-170">Still need help?</span></span> <span data-ttu-id="ef3d6-171">移至[Microsoft 社區](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="ef3d6-171">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>