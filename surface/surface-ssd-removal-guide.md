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
ms.openlocfilehash: 66860af06f4fad8f19ca26702350f19cc85ffef1
ms.sourcegitcommit: bad416f04c6877f2200f134a69146bb633155f22
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919222"
---
# <span data-ttu-id="2955f-103">從相容的 Surface 裝置移除 SSD 的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2955f-103">Best practices for SSD removal from compatible Surface devices</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2955f-104">本文僅供企業組織中合格的 IT 技術人員使用。</span><span class="sxs-lookup"><span data-stu-id="2955f-104">This article is intended for use by qualified IT technicians in an enterprise organization only.</span></span> <span data-ttu-id="2955f-105">它描述合格的 IT 技術人員在有可移除 SSDs 的 Surface 裝置中移除及取代 SSDs 時所建議的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="2955f-105">It describes the recommended best practices for use by qualified IT technicians when they remove and replace SSDs in Surface devices that have removable SSDs.</span></span> 

> [!WARNING]
> <span data-ttu-id="2955f-106">開啟裝置和取代裝置元件可能會帶來電擊、裝置損壞、火災及個人傷亡風險，以及其他危害。</span><span class="sxs-lookup"><span data-stu-id="2955f-106">Opening devices and replacing device components can present electric shock, device damage, fire, and personal injury risks, and other hazards.</span></span>  <span data-ttu-id="2955f-107">當您執行這類活動時，請務必謹慎使用。</span><span class="sxs-lookup"><span data-stu-id="2955f-107">Always use caution when you undertake such activities.</span></span> <span data-ttu-id="2955f-108">遵循[企業 RSSD 移除指南](https://www.microsoft.com/download/100440)中所識別的安全預防措施和程式。</span><span class="sxs-lookup"><span data-stu-id="2955f-108">Follow the safety precautions and procedures that are identified in the [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> <span data-ttu-id="2955f-109">如果您無法遵循「在企業版 rSSD 移除指南」中所指定的安全預防措施及程式，我們建議您取得專業協助。</span><span class="sxs-lookup"><span data-stu-id="2955f-109">We recommend that you get professional assistance if you cannot follow the safety precautions and procedures that are specified in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="2955f-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="2955f-110">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2955f-111">本文假設您瞭解「適用于企業的 rSSD 移除指南」中所述的一般安全預防措施及安全原則與程式。</span><span class="sxs-lookup"><span data-stu-id="2955f-111">This article assumes that you understand the General Safety Precautions and Safety policies and procedures that are described in the "rSSD Removal Guide for Enterprise."</span></span>

## <span data-ttu-id="2955f-112">準備進行 SSD 移除</span><span class="sxs-lookup"><span data-stu-id="2955f-112">Prepare for SSD removal</span></span> 

### <span data-ttu-id="2955f-113">安裝最新的更新</span><span class="sxs-lookup"><span data-stu-id="2955f-113">Install the latest updates</span></span> 

<span data-ttu-id="2955f-114">在開始之前，請確定您的 Windows 版本已 intalled 最新的更新：</span><span class="sxs-lookup"><span data-stu-id="2955f-114">Before you begin, make sure that your version of Windows has the latest updates intalled:</span></span>

1.  <span data-ttu-id="2955f-115">移至 [**啟動**  >  **設定**  >  **更新 & 安全性**]，然後選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-115">Go to **Start** > **Settings** > **Update & Security**, and select **Check for updates**.</span></span> <span data-ttu-id="2955f-116">安裝所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="2955f-116">Install all available updates.</span></span> 
2. <span data-ttu-id="2955f-117">安裝所有可用的更新。</span><span class="sxs-lookup"><span data-stu-id="2955f-117">Install all available updates.</span></span>
3. <span data-ttu-id="2955f-118">確認您有任何需要存取裝置的密碼。</span><span class="sxs-lookup"><span data-stu-id="2955f-118">Verify that you have any passwords that are necessary to access the device.</span></span>  
 
## <span data-ttu-id="2955f-119">[管理 BitLocker]</span><span class="sxs-lookup"><span data-stu-id="2955f-119">Manage BitLocker</span></span> 

> [!NOTE]
> <span data-ttu-id="2955f-120">本節包含對硬碟啟用 BitLocker 加密的組織的建議。</span><span class="sxs-lookup"><span data-stu-id="2955f-120">This section includes recommendations for organizations that have enabled BitLocker encryption for hard disks.</span></span> <span data-ttu-id="2955f-121">如需詳細資訊，請參閱[BitLocker 恢復指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。</span><span class="sxs-lookup"><span data-stu-id="2955f-121">For more information, see the [BitLocker Recovery Guide](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan).</span></span> 

### <span data-ttu-id="2955f-122">如果在 SSD 移除與取代期間停用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="2955f-122">If BitLocker encryption is disabled during SSD removal and replacement</span></span>

<span data-ttu-id="2955f-123">如果可在 SSD 移除與取代之前解除加密裝置，請遵循下列步驟關閉 BitLocker：</span><span class="sxs-lookup"><span data-stu-id="2955f-123">If the device can be unencrypted before SSD removal and replacement, follow these steps to turn off BitLocker:</span></span>

1.  <span data-ttu-id="2955f-124">在 [**設定**] 中，輸入**bitlocker**，然後選取 [**管理 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-124">In **Settings**, type **Bitlocker**, and then select **Manage Bitlocker**.</span></span> 
2.  <span data-ttu-id="2955f-125">選取 [**關閉 Bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-125">Select **Turn Off Bitlocker**.</span></span> 
3.  <span data-ttu-id="2955f-126">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="2955f-126">Power down the device.</span></span> 

### <span data-ttu-id="2955f-127">如果在 SSD 移除與取代期間啟用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="2955f-127">If BitLocker encryption is enabled during SSD removal and replacement</span></span>

<span data-ttu-id="2955f-128">如果在 SSD 移除和取代之前，裝置經過加密，請遵循下列步驟來產生 BitLocker 復原金鑰，並將它儲存至 USB 儲存空間：</span><span class="sxs-lookup"><span data-stu-id="2955f-128">If the device is encrypted before SSD removal and replacement, follow these steps to generate a BitLocker recovery key and save it to USB storage:</span></span>

1.  <span data-ttu-id="2955f-129">在 [**設定**] 中，輸入**Bitlocker**。</span><span class="sxs-lookup"><span data-stu-id="2955f-129">In **Settings**, type **Bitlocker**.</span></span>
2. <span data-ttu-id="2955f-130">選取 [**管理 bitlocker**  > **產生 bitlocker 復原金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-130">Select **Manage Bitlocker** >**Generate Bitlocker Recovery Key**.</span></span>
2.  <span data-ttu-id="2955f-131">插入 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="2955f-131">Insert a USB drive.</span></span> 
3.  <span data-ttu-id="2955f-132">將修復金鑰儲存至 USB 儲存空間。</span><span class="sxs-lookup"><span data-stu-id="2955f-132">Save the recovery key to USB storage.</span></span>  
4.  <span data-ttu-id="2955f-133">移除 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="2955f-133">Remove the USB drive.</span></span>  
5.  <span data-ttu-id="2955f-134">關閉裝置電源。</span><span class="sxs-lookup"><span data-stu-id="2955f-134">Power down the device.</span></span> 

## <span data-ttu-id="2955f-135">移除並取代 SSD</span><span class="sxs-lookup"><span data-stu-id="2955f-135">Remove and replace the SSD</span></span> 

1.  <span data-ttu-id="2955f-136">使用適用于[企業的 RSSD 移除指南](https://www.microsoft.com/download/100440)中的指示來移除 SSD。</span><span class="sxs-lookup"><span data-stu-id="2955f-136">Remove the SSD by using the instructions in [rSSD Removal Guide for Enterprise](https://www.microsoft.com/download/100440).</span></span> 
2. <span data-ttu-id="2955f-137">將原始的 SSD 放入新的裝置，然後將新裝置連接至有線網際網路連線。</span><span class="sxs-lookup"><span data-stu-id="2955f-137">Put the original SSD into a new device, and connect the new device to a wired internet connection.</span></span>
2.  <span data-ttu-id="2955f-138">開啟新裝置的電源。</span><span class="sxs-lookup"><span data-stu-id="2955f-138">Power on the new device.</span></span> <span data-ttu-id="2955f-139">在啟動期間，裝置可能會進行固件更新。</span><span class="sxs-lookup"><span data-stu-id="2955f-139">The device may go through a firmware update during startup.</span></span>  
 
## <span data-ttu-id="2955f-140">在 SSD 移除和取代後</span><span class="sxs-lookup"><span data-stu-id="2955f-140">After SSD removal and replacement</span></span>

### <span data-ttu-id="2955f-141">管理未加密的 SSDs</span><span class="sxs-lookup"><span data-stu-id="2955f-141">Manage unencrypted SSDs</span></span> 

<span data-ttu-id="2955f-142">如果 SSD 在傳輸期間保持不加密，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2955f-142">If the SSD remains unencrypted during the transfer, follow these steps:</span></span> 

1.  <span data-ttu-id="2955f-143">移至 [登**入選項**]  >  (左側的 [金鑰] 圖示所代表的**密碼**) 。</span><span class="sxs-lookup"><span data-stu-id="2955f-143">Go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
2.  <span data-ttu-id="2955f-144">輸入密碼，並登入 [待處理的雙因素驗證] (（如果適用的話）) 。</span><span class="sxs-lookup"><span data-stu-id="2955f-144">Enter the password, and sign in pending completion of two-factor authentication (if applicable).</span></span>
3.  <span data-ttu-id="2955f-145">當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-145">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
4.  <span data-ttu-id="2955f-146">使用密碼重新登入，然後在系統提示時設定 Windows Hello 及 PIN。</span><span class="sxs-lookup"><span data-stu-id="2955f-146">Sign back in by using the password, and set up Windows Hello and a PIN when you are prompted.</span></span> 
    - <span data-ttu-id="2955f-147">如果裝置已在 BitLocker 停用，以協助 SSD 移除及取代，且您想要在更換之後啟用 bitlocker，請移至**bitlocker**  >  **管理 bitlocker**[  >  **繼續 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-147">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and you want to enable BitLocker after the replacement, go to **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
6.  <span data-ttu-id="2955f-148">執行適用于商務 () SDT 的 Microsoft Surface 診斷工具組，以驗證完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="2955f-148">Run the Microsoft Surface Diagnostic Toolkit for Business (SDT) to verify full device functionality.</span></span>  
7.  <span data-ttu-id="2955f-149">流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="2955f-149">Check for Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="2955f-150">如果您看到任何錯誤訊息，請選取 [**疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-150">If you see any error messages, select **Troubleshoot**.</span></span> 
8.  <span data-ttu-id="2955f-151">開啟**office 應用程式**，然後**流覽至 [** 檔案  >  **帳戶**]，然後檢查是否有任何錯誤訊息，以檢查 office 帳戶。</span><span class="sxs-lookup"><span data-stu-id="2955f-151">Check the Office account by opening the **Office App**, navigate to **File** > **Account** and then check for any error messages.</span></span>  

### <span data-ttu-id="2955f-152">管理加密 SSDs</span><span class="sxs-lookup"><span data-stu-id="2955f-152">Managing encrypted SSDs</span></span> 

> [!NOTE]
> <span data-ttu-id="2955f-153">您必須有第二個裝置，才能讀取儲存在 USB 磁片磁碟機上的 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="2955f-153">You will have to have a second device to read the BitLocker Recovery key that was saved on the USB drive.</span></span> 

<span data-ttu-id="2955f-154">如果 SSD 在傳輸期間仍保持加密，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="2955f-154">If the SSD remained encrypted during the transfer, follow these steps:</span></span>

1.  <span data-ttu-id="2955f-155">將內含 Bitlocker 復原金鑰的 USB 磁片磁碟機插入第二個裝置。</span><span class="sxs-lookup"><span data-stu-id="2955f-155">Insert the USB drive that contains the Bitlocker recovery key into the second device.</span></span> 
2.  <span data-ttu-id="2955f-156">開啟內含 Bitlocker 復原金鑰的 .txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="2955f-156">Open the .txt file that contains the Bitlocker recovery key.</span></span> 
3.  <span data-ttu-id="2955f-157">在包含原始 SSD 的新裝置上手動輸入 Bitlocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="2955f-157">Manually enter the Bitlocker recovery key on the new device that contains the original SSD.</span></span>  
4.  <span data-ttu-id="2955f-158">成功輸入 BitLocker 復原金鑰之後，請移至 [登**入選項**]  >  (左邊的 [金鑰] 圖示所代表的**密碼**) 。</span><span class="sxs-lookup"><span data-stu-id="2955f-158">After you have successfully entered the BitLocker recovery key, go to **Sign-In Options** > **Password** (represented by the key icon on the left side).</span></span>  
5.  <span data-ttu-id="2955f-159">如果適用) 的話，請輸入密碼並登入，以待執行的雙因素驗證 (完成。</span><span class="sxs-lookup"><span data-stu-id="2955f-159">Enter the password and sign in, pending completion of two-factor authentication (if applicable).</span></span>
6.  <span data-ttu-id="2955f-160">當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-160">After you are fully signed in, go to **Start** > **Account** > **Sign out**.</span></span>  
7.  <span data-ttu-id="2955f-161">使用密碼重新登入，然後設定 Windows Hello 並新增 PIN。</span><span class="sxs-lookup"><span data-stu-id="2955f-161">Sign back in by using the password, and then set up Windows Hello and add a PIN.</span></span> 
8.  <span data-ttu-id="2955f-162">如果裝置是 BitLocker 停用的，可協助 SSD 移除及取代，而且如果您想要在更換後啟用 bitlocker，請移至 [**設定**  >  **bitlocker**  >  **管理 bitlocker**  >  **繼續 bitlocker**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-162">If the device was BitLocker-disabled to facilitate SSD removal and replacement, and if you want to enable BitLocker after the replacement, go to **Settings** > **Bitlocker** > **Manage Bitlocker** > **Resume Bitlocker**.</span></span>  
9.  <span data-ttu-id="2955f-163">執行**SDT**以驗證完整的裝置功能。</span><span class="sxs-lookup"><span data-stu-id="2955f-163">Run **SDT** to verify full device functionality.</span></span>  
10. <span data-ttu-id="2955f-164">流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="2955f-164">Check Windows activation by navigating to **Settings** > **Activation**.</span></span>  <span data-ttu-id="2955f-165">如果您看到任何錯誤訊息，請選取 [**疑難排解**]。</span><span class="sxs-lookup"><span data-stu-id="2955f-165">If you see any error messages, select **Troubleshoot**.</span></span>
11. <span data-ttu-id="2955f-166">若要檢查 office 帳戶的狀態，請開啟**office 應用程式**，然後**移至 [** 檔案帳戶]，  >  **Account**檢查是否有任何錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="2955f-166">To check the status of the Office account, open the **Office App**, then go to **File** > **Account** to check for any error messages.</span></span>

## <span data-ttu-id="2955f-167">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="2955f-167">More information</span></span> 

<span data-ttu-id="2955f-168">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="2955f-168">For more information, see the following articles:</span></span>

- [<span data-ttu-id="2955f-169">企業版的 rSSD 移除指南</span><span class="sxs-lookup"><span data-stu-id="2955f-169">rSSD Removal Guide for Enterprise</span></span>](https://www.microsoft.com/download/100440)
- [<span data-ttu-id="2955f-170">BitLocker 修復指南</span><span class="sxs-lookup"><span data-stu-id="2955f-170">BitLocker Recovery Guide</span></span>](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

<span data-ttu-id="2955f-171">仍需要協助？</span><span class="sxs-lookup"><span data-stu-id="2955f-171">Still need help?</span></span> <span data-ttu-id="2955f-172">移至[Microsoft 社區](https://answers.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="2955f-172">Go to [Microsoft Community](https://answers.microsoft.com/).</span></span>