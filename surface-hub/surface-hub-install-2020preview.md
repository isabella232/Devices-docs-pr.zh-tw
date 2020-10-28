---
title: 安裝 Windows 10 團隊版 2020 更新預覽組建
description: 新的 Surface Hub 作業系統、Windows 10 團隊2020更新現已推出。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 6d370db0232ae1f93d1ba6b8ff15b5ff2cfa9f10
ms.sourcegitcommit: 19d2a78242777590bd09af3ac6552c07b032e0a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "11142902"
---
# <span data-ttu-id="f9b47-104">安裝 Windows 10 團隊版 2020 更新預覽組建</span><span class="sxs-lookup"><span data-stu-id="f9b47-104">Install Windows 10 Team 2020 Update Preview Build</span></span> 

<span data-ttu-id="f9b47-105">[Surface Hub] 作業系統、[ **windows 10 Team 2020 更新預覽**] 的 [預覽組建] 可提供給「windows 測試人員 [計畫](https://insider.windows.com)」，而不需額外成本。</span><span class="sxs-lookup"><span data-stu-id="f9b47-105">The preview build of the Surface Hub operating system, **Windows 10 Team 2020 Update Preview**, is available at no additional cost from the [Windows Insider Program](https://insider.windows.com).</span></span> 

> [!NOTE] 
> <span data-ttu-id="f9b47-106">Windows 10 Team 2020 更新的最終公開發行現已推出。</span><span class="sxs-lookup"><span data-stu-id="f9b47-106">The final public release of Windows 10 Team 2020  Update is now available.</span></span> <span data-ttu-id="f9b47-107">若要深入瞭解，請參閱 [Windows 10 Team 2020 更新](surface-hub-2020-update.md)。</span><span class="sxs-lookup"><span data-stu-id="f9b47-107">To learn more, see [Windows 10 Team 2020 Update](surface-hub-2020-update.md).</span></span>

<span data-ttu-id="f9b47-108">Windows 10 團隊2020更新帶來了主要的裝置部署和管理功能以及最新的 Windows 10 功能。</span><span class="sxs-lookup"><span data-stu-id="f9b47-108">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="f9b47-109">若要深入瞭解新功能，請參閱下列博客文章：已 [發行適用于公眾預覽版的新 Surface HUB 作業系統更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span><span class="sxs-lookup"><span data-stu-id="f9b47-109">To learn more about what's new, see the following blog post: [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span></span> <span data-ttu-id="f9b47-110">如有已知問題，請參閱 [已知問題： Windows 10 Team 2020 更新](surface-hub-2020-team-update-known-issues.md)</span><span class="sxs-lookup"><span data-stu-id="f9b47-110">For known issues, refer to [Known issues: Windows 10 Team 2020 Update](surface-hub-2020-team-update-known-issues.md)</span></span>
 
## <span data-ttu-id="f9b47-111">必要條件</span><span class="sxs-lookup"><span data-stu-id="f9b47-111">Prerequisites</span></span>

- <span data-ttu-id="f9b47-112">使用 Windows 測試人員 [計畫](https://insider.windows.com/)進行註冊。</span><span class="sxs-lookup"><span data-stu-id="f9b47-112">Register with the [Windows Insider Program](https://insider.windows.com/).</span></span>
- <span data-ttu-id="f9b47-113">從「Windows 測試人員計畫快速頻道」下載 Windows 10 Team 2020 更新預覽組建。</span><span class="sxs-lookup"><span data-stu-id="f9b47-113">Download the Windows 10 Team 2020 Update Preview Build from the Windows Insider Program Fast Channel.</span></span>
- <span data-ttu-id="f9b47-114">安裝預覽組建之後，請下載所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="f9b47-114">After you install the Preview build, download the required firmware updates.</span></span> <span data-ttu-id="f9b47-115">注意：即使您決定離開 Windows 測試人員計畫，也無法卸載固件更新。</span><span class="sxs-lookup"><span data-stu-id="f9b47-115">Note: Firmware updates cannot be uninstalled even if you decide to leave the Windows Insider Program.</span></span>

## <span data-ttu-id="f9b47-116">準備 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="f9b47-116">Prepare your Surface Hub</span></span>

<span data-ttu-id="f9b47-117">開始之前，請檢查 Surface Hub 是否已從 Windows Update 取得最新的更新，並確認您已儲存與您的裝置相關聯的 BitLocker 金鑰。</span><span class="sxs-lookup"><span data-stu-id="f9b47-117">Before you begin, check that your Surface Hub has the latest updates from Windows Update and make sure you save the BitLocker key associated with your device.</span></span>

**<span data-ttu-id="f9b47-118">若要手動檢查更新：</span><span class="sxs-lookup"><span data-stu-id="f9b47-118">To manually check for updates:</span></span>**

1. <span data-ttu-id="f9b47-119">在 Surface Hub 上，開啟 [ **設定** ]，然後在出現提示時輸入您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f9b47-119">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="f9b47-120">流覽至 [**更新 Windows & 安全性**]  >  **更新**，然後選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="f9b47-120">Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.</span></span>

<span data-ttu-id="f9b47-121">如需詳細資訊，請參閱 [管理 Surface Hub 上的 Windows 更新](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="f9b47-121">For more information, see [Manage Windows updates on Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).</span></span>

**<span data-ttu-id="f9b47-122">若要手動儲存您的 BitLocker 金鑰：</span><span class="sxs-lookup"><span data-stu-id="f9b47-122">To manually save your BitLocker key:</span></span>**

1. <span data-ttu-id="f9b47-123">在 Surface Hub 中插入 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f9b47-123">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="f9b47-124">在 Surface Hub 上，開啟 [ **設定** ]，然後在出現提示時輸入您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f9b47-124">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="f9b47-125">流覽至 [**更新 & 安全性**復原]  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="f9b47-125">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="f9b47-126">在 [ **BitLocker**] 底下，選取 [ **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f9b47-126">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="f9b47-127">BitLocker 金鑰會儲存到 USB 磁片磁碟機上的文字檔中。</span><span class="sxs-lookup"><span data-stu-id="f9b47-127">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="f9b47-128">如需詳細資訊，請參閱 [儲存 BitLocker 金鑰](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="f9b47-128">For more information, see [Save your BitLocker key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).</span></span>
 
## <span data-ttu-id="f9b47-129">安裝 Windows 10 Team 2020 更新預覽組建</span><span class="sxs-lookup"><span data-stu-id="f9b47-129">Install the Windows 10 Team 2020 Update Preview Build</span></span>

1. <span data-ttu-id="f9b47-130">在 Surface Hub 上，開啟 [ **設定** ]，然後在出現提示時輸入您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f9b47-130">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="f9b47-131">流覽至 **隱私權 > 診斷 & 意見** 反應，並將診斷資料設定為 [已 **滿**]。</span><span class="sxs-lookup"><span data-stu-id="f9b47-131">Navigate to **Privacy > Diagnostics & feedback** and set Diagnostic data to **Full**.</span></span> <span data-ttu-id="f9b47-132">某些地區或組織可能需要透過 MDM policy 或 PPKG 檔案來套用此設定：</span><span class="sxs-lookup"><span data-stu-id="f9b47-132">Some regions or organizations may need to apply this setting via MDM policy or PPKG file:</span></span>
   - <span data-ttu-id="f9b47-133">**針對 MDM：** 設定下列原則：。使用整數值3的 **/Vendor/MSFT/Policy/System/AllowTelemetry** ：</span><span class="sxs-lookup"><span data-stu-id="f9b47-133">**For MDM:** Set the following policy: .**/Vendor/MSFT/Policy/System/AllowTelemetry** with the integer value of 3:</span></span>
    
        ![將 AllowTelemetry 設定為3](images/hub-2020-allow-telemetry.png)

    - <span data-ttu-id="f9b47-135">**針對 PPKG：** 下載 [PPKG](https://aka.ms/HubTltmtry)檔案。</span><span class="sxs-lookup"><span data-stu-id="f9b47-135">**For PPKG:** Download the [PPKG file](https://aka.ms/HubTltmtry).</span></span>

3. <span data-ttu-id="f9b47-136">流覽至 [**更新 & 安全性**  >  **Windows**測試人員計畫]，然後選取 [**開始**使用] 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="f9b47-136">Navigate to **Update & Security** > **Windows Insider Program** and then select **Get started** to enroll.</span></span>
4. <span data-ttu-id="f9b47-137">請按照提示使用您的公司帳戶（ (建議的) 或您的個人 Microsoft 帳戶）來註冊為 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="f9b47-137">Follow the prompts to register as a Windows Insider using either your work account (recommended) or your personal Microsoft account.</span></span> <span data-ttu-id="f9b47-138">如需使用您的公司帳戶登記之好處的詳細資料，請參閱 [註冊商務用 Windows](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)測試人員計畫。</span><span class="sxs-lookup"><span data-stu-id="f9b47-138">For details on the benefits of registering with your work account, see [Register for the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).</span></span>
5. <span data-ttu-id="f9b47-139">在 [ **挑選您**的測試人員設定] 底下，選取 [ **快速**]。</span><span class="sxs-lookup"><span data-stu-id="f9b47-139">Under **Pick your Insider settings**, select **Fast**.</span></span>
6. <span data-ttu-id="f9b47-140">允許 Surface Hub 在未來3到4天自動安裝預覽組建及所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="f9b47-140">Allow the Surface Hub to automatically install the Preview Build and the required firmware updates over the next 3 to 4 days.</span></span> <span data-ttu-id="f9b47-141">裝置將會在每日 [維護時段](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)自動下載並安裝更新。</span><span class="sxs-lookup"><span data-stu-id="f9b47-141">The device will automatically download and install the updates during daily [maintenance windows](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window).</span></span> <span data-ttu-id="f9b47-142">例如：</span><span class="sxs-lookup"><span data-stu-id="f9b47-142">For example:</span></span>

- <span data-ttu-id="f9b47-143">在第一個維護視窗期間，Surface Hub 開始從 Windows Update 下載預覽組建。</span><span class="sxs-lookup"><span data-stu-id="f9b47-143">During the first maintenance window, Surface Hub starts downloading the Preview Build from Windows Update.</span></span>
- <span data-ttu-id="f9b47-144">在第二個維護視窗期間，裝置會重新開機以完成更新。</span><span class="sxs-lookup"><span data-stu-id="f9b47-144">During a second maintenance window, the device restarts to complete the update.</span></span>
- <span data-ttu-id="f9b47-145">在第三個維護視窗期間，裝置會下載並安裝所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="f9b47-145">During a third maintenance window, the device downloads and installs the required firmware updates.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f9b47-146">Microsoft 建議您保留3-4 天的 Surface Hub，以允許裝置完成預覽版及必要的固件更新。</span><span class="sxs-lookup"><span data-stu-id="f9b47-146">Microsoft recommends reserving the Surface Hub for 3-4 days to allow the device to finish installing the Preview Build and the required firmware updates.</span></span> <span data-ttu-id="f9b47-147">如果您在此程式中使用裝置，您可能會遇到圖形、音訊和使用者介面問題。</span><span class="sxs-lookup"><span data-stu-id="f9b47-147">You may experience graphics, audio, and user interface issues if you use the device during this process.</span></span>

### <span data-ttu-id="f9b47-148">如果您選擇手動安裝預覽組建及必要的固件更新：</span><span class="sxs-lookup"><span data-stu-id="f9b47-148">If you choose to manually install the Preview Build and required firmware updates:</span></span>

1. <span data-ttu-id="f9b47-149">在您向 Windows 測試人員計畫註冊之後，請移至 [**設定**  >  **更新] & 安全性**  >  **Windows 更新**，然後選取 [**檢查更新**] 以安裝預覽組建。</span><span class="sxs-lookup"><span data-stu-id="f9b47-149">After you've registered with the Windows Insider Program, go to **Settings** > **Update & Security** > **Windows Update** and select **Check for updates** to install the Preview Build.</span></span>
2. <span data-ttu-id="f9b47-150">一旦預覽組建安裝 (可能需要長達14小時的) ，請選取 [ **立即重新開機** ] 以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="f9b47-150">Once the Preview Build installs (it may take up to 14 hours), select **Restart now** to complete the installation.</span></span>
3. <span data-ttu-id="f9b47-151">裝置重新開機之後，請移至 [**設定**  >  **更新] & 安全性**  >  **Windows 更新**，然後選取 [**檢查更新以安裝必要的固件更新**]。</span><span class="sxs-lookup"><span data-stu-id="f9b47-151">After the device restarts, go to **Settings** > **Update & Security** > **Windows Update**, and select **Check for updates to install required firmware updates**.</span></span>
4. <span data-ttu-id="f9b47-152">固件安裝之後，請選取 [ **立即重新開機**]。</span><span class="sxs-lookup"><span data-stu-id="f9b47-152">Once the firmware installs, select **Restart now**.</span></span>

> [!WARNING]
> <span data-ttu-id="f9b47-153">如果您安裝 [預覽組建] 但不安裝必要的固件更新，您可能會看到圖形、音訊和使用者介面問題。</span><span class="sxs-lookup"><span data-stu-id="f9b47-153">You may see graphics, audio, and user interface issues if you install the Preview Build without installing the required firmware updates.</span></span>

> [!NOTE]
> <span data-ttu-id="f9b47-154">如果您選擇離開 Windows 測試人員計畫，並將 Surface Hub 還原為舊版的作業系統，您必須先 [重設裝置](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="f9b47-154">If you choose to leave the Windows Insider Program and revert your Surface Hub to an older version of the operating system, you must first [reset your device](https://docs.microsoft.com/surface-hub/device-reset-surface-hub).</span></span> <span data-ttu-id="f9b47-155">接著，您將需要執行 [第一個 run 程式](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) 來重新設定您的裝置。</span><span class="sxs-lookup"><span data-stu-id="f9b47-155">Afterwards, you will need to go through the [first run program](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) to re-configure your device.</span></span>
 

## <span data-ttu-id="f9b47-156">深入了解</span><span class="sxs-lookup"><span data-stu-id="f9b47-156">Learn more</span></span>

- [<span data-ttu-id="f9b47-157">已知問題： Windows 10 Team 2020 更新</span><span class="sxs-lookup"><span data-stu-id="f9b47-157">Known issues: Windows 10 Team 2020 Update</span></span>](surface-hub-2020-team-update-known-issues.md)
- [<span data-ttu-id="f9b47-158">新的 Surface Hub 作業系統更新已發行以進行公開預覽。</span><span class="sxs-lookup"><span data-stu-id="f9b47-158">New Surface Hub OS update released for public preview.</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [<span data-ttu-id="f9b47-159">開始使用商務用 Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="f9b47-159">Getting started with the Windows Insider Program for Business</span></span>](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)