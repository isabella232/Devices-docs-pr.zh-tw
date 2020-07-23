---
title: 安裝 Windows 10 Team 2020 更新預覽組建
description: 新的 Surface Hub 作業系統、Windows 10 團隊2020更新現已推出。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/22/2020
ms.localizationpriority: Medium
ms.openlocfilehash: 9177b184d7a1d6dca63e94740b6208987d97229f
ms.sourcegitcommit: df1e178b724966e4cf8ff219c5e937e6c31cd9b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/22/2020
ms.locfileid: "10894109"
---
# <span data-ttu-id="74617-104">安裝 Windows 10 Team 2020 更新預覽組建</span><span class="sxs-lookup"><span data-stu-id="74617-104">Install Windows 10 Team 2020 Update Preview Build</span></span> 

<span data-ttu-id="74617-105">「Surface Hub」作業系統、 **Windows 10 團隊2020更新**的最新更新現已提供給 windows 測試人員[計畫](https://insider.windows.com)中的 surface hub 50-寸和 surface hub 2 55 寸裝置的額外成本。</span><span class="sxs-lookup"><span data-stu-id="74617-105">The latest update of the Surface Hub operating system, **Windows 10 Team 2020 Update**, is now available at no additional cost for the Surface Hub 50-inch and Surface Hub 2S 55-inch devices from the [Windows Insider Program](https://insider.windows.com).</span></span> <span data-ttu-id="74617-106">Windows 10 Team 2020 更新最終版本中將支援 Surface Hub 84-寸模型。</span><span class="sxs-lookup"><span data-stu-id="74617-106">The Surface Hub 84-inch model will be supported in the final release of Windows 10 Team 2020 Update.</span></span>

<span data-ttu-id="74617-107">Windows 10 團隊2020更新帶來了主要的裝置部署和管理功能以及最新的 Windows 10 功能。</span><span class="sxs-lookup"><span data-stu-id="74617-107">Windows 10 Team 2020 Update brings major improvements to device deployment and manageability along with the latest Windows 10 features.</span></span> <span data-ttu-id="74617-108">若要深入瞭解新功能，請參閱下列博客文章：已[發行適用于公眾預覽版的新 Surface HUB 作業系統更新。](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span><span class="sxs-lookup"><span data-stu-id="74617-108">To learn more about what's new, see the following blog post: [New Surface Hub OS update released for public preview.](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)</span></span> <span data-ttu-id="74617-109">如有已知問題，請參閱下方的「已知問題」一節。</span><span class="sxs-lookup"><span data-stu-id="74617-109">For known issues, refer to the "Known issues" section below.</span></span>
 
## <span data-ttu-id="74617-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="74617-110">Prerequisites</span></span>

- <span data-ttu-id="74617-111">使用 Windows 測試人員[計畫](https://insider.windows.com/)進行註冊。</span><span class="sxs-lookup"><span data-stu-id="74617-111">Register with the [Windows Insider Program](https://insider.windows.com/).</span></span>
- <span data-ttu-id="74617-112">從「Windows 測試人員計畫快速頻道」下載 Windows 10 Team 2020 更新預覽組建。</span><span class="sxs-lookup"><span data-stu-id="74617-112">Download the Windows 10 Team 2020 Update Preview Build from the Windows Insider Program Fast Channel.</span></span>
- <span data-ttu-id="74617-113">安裝預覽組建之後，請下載所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="74617-113">After you install the Preview build, download the required firmware updates.</span></span> <span data-ttu-id="74617-114">注意：即使您決定離開 Windows 測試人員計畫，也無法卸載固件更新。</span><span class="sxs-lookup"><span data-stu-id="74617-114">Note: Firmware updates cannot be uninstalled even if you decide to leave the Windows Insider Program.</span></span>

## <span data-ttu-id="74617-115">準備 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="74617-115">Prepare your Surface Hub</span></span>

<span data-ttu-id="74617-116">開始之前，請檢查 Surface Hub 是否已從 Windows Update 取得最新的更新，並確認您已儲存與您的裝置相關聯的 BitLocker 金鑰。</span><span class="sxs-lookup"><span data-stu-id="74617-116">Before you begin, check that your Surface Hub has the latest updates from Windows Update and make sure you save the BitLocker key associated with your device.</span></span>

**<span data-ttu-id="74617-117">若要手動檢查更新：</span><span class="sxs-lookup"><span data-stu-id="74617-117">To manually check for updates:</span></span>**

1. <span data-ttu-id="74617-118">在 Surface Hub 上，開啟 [**設定**]，然後在出現提示時輸入您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="74617-118">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="74617-119">流覽至 [**更新 Windows & 安全性**]  >  **更新**，然後選取 [**檢查更新**]。</span><span class="sxs-lookup"><span data-stu-id="74617-119">Navigate to **Update & Security** > **Windows Update** and then select **Check for updates**.</span></span>

<span data-ttu-id="74617-120">如需詳細資訊，請參閱[管理 Surface Hub 上的 Windows 更新](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="74617-120">For more information, see [Manage Windows updates on Surface Hub](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub).</span></span>

**<span data-ttu-id="74617-121">若要手動儲存您的 BitLocker 金鑰：</span><span class="sxs-lookup"><span data-stu-id="74617-121">To manually save your BitLocker key:</span></span>**

1. <span data-ttu-id="74617-122">在 Surface Hub 中插入 USB 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="74617-122">Insert a USB drive into Surface Hub.</span></span>
2. <span data-ttu-id="74617-123">在 Surface Hub 上，開啟 [**設定**]，然後在出現提示時輸入您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="74617-123">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
3. <span data-ttu-id="74617-124">流覽至 [**更新 & 安全性**復原]  >  \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="74617-124">Navigate to **Update & Security** > **Recovery**.</span></span>
4. <span data-ttu-id="74617-125">在 [ **BitLocker**] 底下，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="74617-125">Under **BitLocker**, select **Save**.</span></span> <span data-ttu-id="74617-126">BitLocker 金鑰會儲存到 USB 磁片磁碟機上的文字檔中。</span><span class="sxs-lookup"><span data-stu-id="74617-126">The BitLocker key is saved to a text file on the USB drive.</span></span>

<span data-ttu-id="74617-127">如需詳細資訊，請參閱[儲存 BitLocker 金鑰](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="74617-127">For more information, see [Save your BitLocker key](https://docs.microsoft.com/surface-hub/save-bitlocker-key-surface-hub).</span></span>
 
## <span data-ttu-id="74617-128">安裝 Windows 10 Team 2020 更新預覽組建</span><span class="sxs-lookup"><span data-stu-id="74617-128">Install the Windows 10 Team 2020 Update Preview Build</span></span>

1. <span data-ttu-id="74617-129">在 Surface Hub 上，開啟 [**設定**]，然後在出現提示時輸入您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="74617-129">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="74617-130">流覽至 [**更新 & 安全性**  >  **Windows**測試人員計畫]，然後選取 [**開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="74617-130">Navigate to **Update & Security** > **Windows Insider Program** and then select **Get started**.</span></span>
3. <span data-ttu-id="74617-131">請依照提示使用您的公司帳戶（建議）或您的個人 Microsoft 帳戶，將其註冊為 Windows 測試人員。</span><span class="sxs-lookup"><span data-stu-id="74617-131">Follow the prompts to register as a Windows Insider using either your work account (recommended) or your personal Microsoft account.</span></span> <span data-ttu-id="74617-132">如需使用您的公司帳戶登記之好處的詳細資料，請參閱[註冊商務用 Windows](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register)測試人員計畫。</span><span class="sxs-lookup"><span data-stu-id="74617-132">For details on the benefits of registering with your work account, see [Register for the Windows Insider Program for Business](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-register).</span></span>
4. <span data-ttu-id="74617-133">在 [**挑選您**的測試人員設定] 底下，選取 [**快速**]。</span><span class="sxs-lookup"><span data-stu-id="74617-133">Under **Pick your Insider settings**, select **Fast**.</span></span>
5. <span data-ttu-id="74617-134">允許 Surface Hub 在未來3到4天自動安裝預覽組建及所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="74617-134">Allow the Surface Hub to automatically install the Preview Build and the required firmware updates over the next 3 to 4 days.</span></span> <span data-ttu-id="74617-135">裝置將會在每日[維護時段](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window)自動下載並安裝更新。</span><span class="sxs-lookup"><span data-stu-id="74617-135">The device will automatically download and install the updates during daily [maintenance windows](https://docs.microsoft.com/surface-hub/manage-windows-updates-for-surface-hub#maintenance-window).</span></span> <span data-ttu-id="74617-136">例如：</span><span class="sxs-lookup"><span data-stu-id="74617-136">For example:</span></span>

- <span data-ttu-id="74617-137">在第一個維護視窗期間，Surface Hub 開始從 Windows Update 下載預覽組建。</span><span class="sxs-lookup"><span data-stu-id="74617-137">During the first maintenance window, Surface Hub starts downloading the Preview Build from Windows Update.</span></span>
- <span data-ttu-id="74617-138">在第二個維護視窗期間，裝置會重新開機以完成更新。</span><span class="sxs-lookup"><span data-stu-id="74617-138">During a second maintenance window, the device restarts to complete the update.</span></span>
- <span data-ttu-id="74617-139">在第三個維護視窗期間，裝置會下載並安裝所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="74617-139">During a third maintenance window, the device downloads and installs the required firmware updates.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74617-140">Microsoft 建議您保留3-4 天的 Surface Hub，以允許裝置完成預覽版及必要的固件更新。</span><span class="sxs-lookup"><span data-stu-id="74617-140">Microsoft recommends reserving the Surface Hub for 3-4 days to allow the device to finish installing the Preview Build and the required firmware updates.</span></span> <span data-ttu-id="74617-141">如果您在此程式中使用裝置，您可能會遇到圖形、音訊和使用者介面問題。</span><span class="sxs-lookup"><span data-stu-id="74617-141">You may experience graphics, audio, and user interface issues if you use the device during this process.</span></span>

### <span data-ttu-id="74617-142">如果您選擇手動安裝預覽組建及必要的固件更新：</span><span class="sxs-lookup"><span data-stu-id="74617-142">If you choose to manually install the Preview Build and required firmware updates:</span></span>

1. <span data-ttu-id="74617-143">在您向 Windows 測試人員計畫註冊之後，請移至 [**設定**  >  **更新] & 安全性**  >  **Windows 更新**，然後選取 [**檢查更新**] 以安裝預覽組建。</span><span class="sxs-lookup"><span data-stu-id="74617-143">After you've registered with the Windows Insider Program, go to **Settings** > **Update & Security** > **Windows Update** and select **Check for updates** to install the Preview Build.</span></span>
2. <span data-ttu-id="74617-144">預覽組建安裝之後（可能需要長達14小時），請選取 [**立即重新開機**] 以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="74617-144">Once the Preview Build installs (it may take up to 14 hours), select **Restart now** to complete the installation.</span></span>
3. <span data-ttu-id="74617-145">裝置重新開機之後，請移至 [**設定**  >  **更新] & 安全性**  >  **Windows 更新**，然後選取 [**檢查更新以安裝必要的固件更新**]。</span><span class="sxs-lookup"><span data-stu-id="74617-145">After the device restarts, go to **Settings** > **Update & Security** > **Windows Update**, and select **Check for updates to install required firmware updates**.</span></span>
4. <span data-ttu-id="74617-146">固件安裝之後，請選取 [**立即重新開機**]。</span><span class="sxs-lookup"><span data-stu-id="74617-146">Once the firmware installs, select **Restart now**.</span></span>

> [!WARNING]
> <span data-ttu-id="74617-147">如果您安裝 [預覽組建] 但不安裝必要的固件更新，您可能會看到圖形、音訊和使用者介面問題。</span><span class="sxs-lookup"><span data-stu-id="74617-147">You may see graphics, audio, and user interface issues if you install the Preview Build without installing the required firmware updates.</span></span>

> [!NOTE]
> <span data-ttu-id="74617-148">如果您選擇離開 Windows 測試人員計畫，並將 Surface Hub 還原為舊版的作業系統，您必須先[重設裝置](https://docs.microsoft.com/surface-hub/device-reset-surface-hub)。</span><span class="sxs-lookup"><span data-stu-id="74617-148">If you choose to leave the Windows Insider Program and revert your Surface Hub to an older version of the operating system, you must first [reset your device](https://docs.microsoft.com/surface-hub/device-reset-surface-hub).</span></span> <span data-ttu-id="74617-149">接著，您將需要執行[第一個 run 程式](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub)來重新設定您的裝置。</span><span class="sxs-lookup"><span data-stu-id="74617-149">Afterwards, you will need to go through the [first run program](https://docs.microsoft.com/surface-hub/first-run-program-surface-hub) to re-configure your device.</span></span>
 
## <span data-ttu-id="74617-150">已知問題： Windows 10 Team 2020 更新預覽組建</span><span class="sxs-lookup"><span data-stu-id="74617-150">Known issues: Windows 10 Team 2020 Update Preview Build</span></span>

### <span data-ttu-id="74617-151">圖形、音訊和使用者介面問題</span><span class="sxs-lookup"><span data-stu-id="74617-151">Graphics, audio, and user interface issues</span></span> 

<span data-ttu-id="74617-152">如果您安裝 [預覽組建] 時，您可能會遇到各種圖形和使用者介面問題，但不會在此後立即安裝所需的固件更新。</span><span class="sxs-lookup"><span data-stu-id="74617-152">You may experience various graphics and user interface issues if you install the Preview Build, but do not immediately install the required firmware updates afterward.</span></span> <span data-ttu-id="74617-153">Microsoft 方案可在 Windows 10 Team 2020 更新的發行組建中修正這些問題。</span><span class="sxs-lookup"><span data-stu-id="74617-153">Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="74617-154">Surface Hub 84-寸：圖形與使用者介面問題</span><span class="sxs-lookup"><span data-stu-id="74617-154">Surface Hub 84-inch: graphics and user interface issues</span></span>

<span data-ttu-id="74617-155">如果您在第一代 Surface 中樞84寸裝置上安裝預覽版，您可能會遇到各種圖形與使用者介面問題。</span><span class="sxs-lookup"><span data-stu-id="74617-155">You may experience various graphics and user interface issues if you install the Preview Build on a first-generation Surface Hub 84-inch device.</span></span> <span data-ttu-id="74617-156">Windows 10 Team 2020 更新最終版本中將會支援 Surface Hub 84-寸。</span><span class="sxs-lookup"><span data-stu-id="74617-156">The Surface Hub 84-inch will be supported in the final release of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="74617-157">套用條件式存取原則時，登入會受到影響</span><span class="sxs-lookup"><span data-stu-id="74617-157">Sign in is impacted when Conditional Access policies are applied</span></span>

- <span data-ttu-id="74617-158">嘗試登入應用程式（例如 Microsoft 白板）時登入失敗。</span><span class="sxs-lookup"><span data-stu-id="74617-158">Sign in fails when attempting to sign into apps such as Microsoft Whiteboard.</span></span> <span data-ttu-id="74617-159">使用者必須先從 [開始] 功能表中的 [[我的會議] 和](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub)[檔案] 登入。</span><span class="sxs-lookup"><span data-stu-id="74617-159">Users must first sign in from [My meetings and files](https://support.microsoft.com/help/4506480/sign-in-to-see-your-meetings-and-files-on-surface-hub) from the Start menu.</span></span>

- <span data-ttu-id="74617-160">如果您的使用者帳戶登錄至不同的 Azure AD 租使用者，而不是 Surface Hub 對 Azure AD join 所使用的租使用者，請登入失敗。</span><span class="sxs-lookup"><span data-stu-id="74617-160">Sign in fails if your user account is registered to a different Azure AD tenant than the one used by Surface Hub to Azure AD join.</span></span>

<span data-ttu-id="74617-161">Microsoft 方案可在 Windows 10 Team 2020 更新的發行組建中修正這些問題。</span><span class="sxs-lookup"><span data-stu-id="74617-161">Microsoft plans to fix these issues in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="74617-162">Windows Update 在沒有可用的新驅動程式時提示安裝</span><span class="sxs-lookup"><span data-stu-id="74617-162">Windows Update prompts to install new drivers when none are available</span></span>

<span data-ttu-id="74617-163">當您在**Settings**  >  安裝 windows 10 Team 2020 更新及所需的固件更新之後，移至 [設定**更新] & 安全性**  >  **Windows 更新**，您可能會看到下列錯誤：</span><span class="sxs-lookup"><span data-stu-id="74617-163">When you go to **Settings** > **Update & Security** > **Windows Update** after you’ve installed Windows 10 Team 2020 Update and the required firmware updates, you may see the following error:</span></span> 

- <span data-ttu-id="74617-164">「您電腦上目前的驅動程式可能比我們嘗試安裝的驅動程式好。</span><span class="sxs-lookup"><span data-stu-id="74617-164">“A current driver on your PC may be better than the driver we’re trying to install.</span></span> <span data-ttu-id="74617-165">我們會持續嘗試安裝。」</span><span class="sxs-lookup"><span data-stu-id="74617-165">We’ll keep trying to install.”</span></span> 

<span data-ttu-id="74617-166">您可以放心地忽略此錯誤。</span><span class="sxs-lookup"><span data-stu-id="74617-166">This error can be safely ignored.</span></span> <span data-ttu-id="74617-167">Microsoft 正在積極調查這個問題。</span><span class="sxs-lookup"><span data-stu-id="74617-167">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="74617-168">無法使用預配套件安裝 Surface Hub 原則</span><span class="sxs-lookup"><span data-stu-id="74617-168">Unable to install Surface Hub policies using provisioning packages</span></span>

<span data-ttu-id="74617-169">無法安裝使用 Surface Hub 配置服務提供者（CSP）中原則的預配套件。</span><span class="sxs-lookup"><span data-stu-id="74617-169">Provisioning packages that use policies from the Surface Hub Configuration Service Provider (CSP) fail to install.</span></span> <span data-ttu-id="74617-170">現在，請使用 Microsoft Intune 或其他行動裝置管理（MDM）提供者來套用 Surface Hub 原則。</span><span class="sxs-lookup"><span data-stu-id="74617-170">For now, use Microsoft Intune or another mobile device management (MDM) provider to apply Surface Hub policies.</span></span> <span data-ttu-id="74617-171">Microsoft 方案可在 Windows 10 Team 2020 更新的發行組建中修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="74617-171">Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="74617-172">第一次執行時，系統會提示您提前移除 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="74617-172">Prompt to remove USB drive prematurely during first run</span></span>

<span data-ttu-id="74617-173">在第一次執行期間使用預配套件來設定 Surface Hub 時，系統會提示您移除 USB 磁片磁碟機，讓裝置能夠讀取 Surface Hub 設定檔。</span><span class="sxs-lookup"><span data-stu-id="74617-173">When using a provisioning package to setup Surface Hub during first run, you’re prompted to remove the USB drive before the device is able to read the Surface Hub configuration file.</span></span> <span data-ttu-id="74617-174">如果您是使用 [設定檔案] 來設定您的裝置帳戶，請忽略此訊息。</span><span class="sxs-lookup"><span data-stu-id="74617-174">Ignore the message if you’re using a configure file to setup your device account.</span></span> <span data-ttu-id="74617-175">Microsoft 正在積極調查這個問題。</span><span class="sxs-lookup"><span data-stu-id="74617-175">Microsoft is actively investigating this issue.</span></span>
 
### <span data-ttu-id="74617-176">無法在第一次執行期間設定 proxy 設定</span><span class="sxs-lookup"><span data-stu-id="74617-176">Unable to set up proxy settings during first run</span></span>

<span data-ttu-id="74617-177">如果您使用 proxy 連線至網際網路，在第一次執行程式期間，您的網際網路連線可能會受到限制。</span><span class="sxs-lookup"><span data-stu-id="74617-177">If you use a proxy to connect to the Internet, you may have limited Internet connectivity during the first run program.</span></span> <span data-ttu-id="74617-178">Microsoft 方案可在 Windows 10 Team 2020 更新的發行組建中修正這個問題。</span><span class="sxs-lookup"><span data-stu-id="74617-178">Microsoft plans to fix this issue in the release build of Windows 10 Team 2020 Update.</span></span>
 
### <span data-ttu-id="74617-179">從 Microsoft Store 下載應用程式時出現錯誤</span><span class="sxs-lookup"><span data-stu-id="74617-179">An error appears when you download apps from Microsoft Store</span></span>

<span data-ttu-id="74617-180">若要從 Microsoft 網上商店下載 app，您會看到 [登入] 的提示。</span><span class="sxs-lookup"><span data-stu-id="74617-180">To download an app from the Microsoft Store, you will see a prompt to sign in.</span></span> <span data-ttu-id="74617-181">已知問題會導致在登入時出現錯誤，但這不會影響您下載 app 的能力。</span><span class="sxs-lookup"><span data-stu-id="74617-181">A known issue causes an error to appear during sign-in, but this doesn't affect your ability to download apps.</span></span> <span data-ttu-id="74617-182">Microsoft 正在積極調查這個問題。</span><span class="sxs-lookup"><span data-stu-id="74617-182">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="74617-183">Surface Hub 2 間歇中斷 Wi-fi 連線</span><span class="sxs-lookup"><span data-stu-id="74617-183">Surface Hub 2S intermittently loses Wi-Fi connection</span></span>

<span data-ttu-id="74617-184">嘗試拔出裝置並將其插回，或使用乙太網線連線至網際網路。</span><span class="sxs-lookup"><span data-stu-id="74617-184">Try unplugging your device and plugging it back in, or using an Ethernet cable to connect to the Internet.</span></span> <span data-ttu-id="74617-185">Microsoft 正在積極調查這個問題。</span><span class="sxs-lookup"><span data-stu-id="74617-185">Microsoft is actively investigating this issue.</span></span>

### <span data-ttu-id="74617-186">Surface Hub 秒間歇無法從睡眠狀態繼續</span><span class="sxs-lookup"><span data-stu-id="74617-186">Surface Hub 2S intermittently fails to resume from sleep</span></span>

<span data-ttu-id="74617-187">Surface Hub 秒可能間歇無法完全從睡眠中繼續執行，並在顯示 Microsoft 標誌的畫面上顯示為停止回應。</span><span class="sxs-lookup"><span data-stu-id="74617-187">Surface Hub 2S may intermittently fail to fully resume from sleep and appear to stop responding on a screen showing the Microsoft logo.</span></span> <span data-ttu-id="74617-188">嘗試拔出您的裝置，然後再插回裝置。</span><span class="sxs-lookup"><span data-stu-id="74617-188">Try unplugging your device and plugging it back in.</span></span> 

<span data-ttu-id="74617-189">若要避免此問題：</span><span class="sxs-lookup"><span data-stu-id="74617-189">To prevent this issue:</span></span>

1. <span data-ttu-id="74617-190">在 Surface Hub 上，開啟 [**設定**]，然後在出現提示時輸入您的系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="74617-190">On Surface Hub, open **Settings** and enter your admin credentials when prompted.</span></span>
2. <span data-ttu-id="74617-191">流覽至 [ **Surface Hub**]  >  **會話 & [電源**]。</span><span class="sxs-lookup"><span data-stu-id="74617-191">Navigate to **Surface Hub** > **Session & power**.</span></span> 
3. <span data-ttu-id="74617-192">在 **[當裝置進入睡眠狀態時，請使用此電源設定**] 底下，選取 [**已連接待機]。**</span><span class="sxs-lookup"><span data-stu-id="74617-192">Under **When the device goes to sleep, use this power setting**, select **Connected Standby.**</span></span>
4. <span data-ttu-id="74617-193">在 [**沒有任何人時，請將裝置移至睡眠狀態**] 底下，選取 [**永不]。**</span><span class="sxs-lookup"><span data-stu-id="74617-193">Under **When no one is present, put the device to sleep after**, select **Never.**</span></span>

<span data-ttu-id="74617-194">Microsoft 方案在 Windows 10 Team 2020 更新的最終發行前，在固件更新中修正此問題。</span><span class="sxs-lookup"><span data-stu-id="74617-194">Microsoft plans to fix this issue in a firmware update prior to the final release of Windows 10 Team 2020 Update.</span></span>

### <span data-ttu-id="74617-195">[連線] app 不在視野中時的投影問題</span><span class="sxs-lookup"><span data-stu-id="74617-195">Projection issues when the Connect app is not in view</span></span>

- <span data-ttu-id="74617-196">當您使用光纜來投影 Surface Hub 時，如果您流覽到 [連接] app，touchback 就會停止運作。</span><span class="sxs-lookup"><span data-stu-id="74617-196">When you use a cable to project to Surface Hub, touchback stops working if you navigate away from the Connect app.</span></span>
- <span data-ttu-id="74617-197">當您使用 Miracast 來投影至 Surface Hub 時，當您離開連接應用程式後，無線連線就會立即中斷。</span><span class="sxs-lookup"><span data-stu-id="74617-197">When you project to Surface Hub using Miracast, the wireless connection drops soon after you navigate away from the Connect app.</span></span>

<span data-ttu-id="74617-198">Microsoft 正在積極調查這些問題。</span><span class="sxs-lookup"><span data-stu-id="74617-198">Microsoft is actively investigating these issues.</span></span>

### <span data-ttu-id="74617-199">商務用 Skype 沒有使用 proxy 來進行媒體流量</span><span class="sxs-lookup"><span data-stu-id="74617-199">Skype for Business isn't using proxy for media traffic</span></span>

<span data-ttu-id="74617-200">針對使用 proxy 的一些裝置，商務用 Skype 可以登入，但不會使用 proxy 伺服器來傳送媒體流量。</span><span class="sxs-lookup"><span data-stu-id="74617-200">For some devices that use a proxy, Skype for Business can sign in, but will not use the proxy server for media traffic.</span></span> <span data-ttu-id="74617-201">Microsoft 正在積極調查這個問題。</span><span class="sxs-lookup"><span data-stu-id="74617-201">Microsoft is actively investigating this issue.</span></span>

<span data-ttu-id="74617-202">我們邀請您與 Microsoft 支援人員分享您的見解與建議。</span><span class="sxs-lookup"><span data-stu-id="74617-202">We invite you to share your insights and suggestions with Microsoft Support.</span></span>

## <span data-ttu-id="74617-203">深入了解</span><span class="sxs-lookup"><span data-stu-id="74617-203">Learn more</span></span>

- [<span data-ttu-id="74617-204">新的 Surface Hub 作業系統更新已發行以進行公開預覽。</span><span class="sxs-lookup"><span data-stu-id="74617-204">New Surface Hub OS update released for public preview.</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/new-surface-hub-os-update-released-for-public-preview/ba-p/1534823)
- [<span data-ttu-id="74617-205">開始使用商務用 Windows 測試人員計畫</span><span class="sxs-lookup"><span data-stu-id="74617-205">Getting started with the Windows Insider Program for Business</span></span>](https://docs.microsoft.com/windows-insider/at-work-pro/wip-4-biz-manage)