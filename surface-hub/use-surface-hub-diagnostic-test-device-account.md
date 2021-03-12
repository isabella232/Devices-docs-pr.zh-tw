---
title: 使用 Surface Hub 硬體診斷工具來測試裝置帳戶
description: 使用 Surface Hub 硬體診斷工具來測試裝置帳戶
ms.assetid: a87b7d41-d0a7-4acc-bfa6-b9070f99bc9c
keywords: 協助工具設定, \[設定\] 應用程式, 輕鬆存取
ms.prod: surface-hub
ms.sitesec: library
author: v-miegge
ms.author: v-miegge
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: 6661f2347d2f411ed11fe6057ede8ca2bab07c33
ms.sourcegitcommit: f0c976664116c45605edf3d56c4f58119a246b93
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "11406666"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a><span data-ttu-id="1f947-104">使用 Surface Hub 硬體診斷工具來測試裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="1f947-104">Using the Surface Hub Hardware Diagnostic Tool to test a device account</span></span>

## <a name="introduction"></a><span data-ttu-id="1f947-105">簡介</span><span class="sxs-lookup"><span data-stu-id="1f947-105">Introduction</span></span>

> [!NOTE]
> <span data-ttu-id="1f947-106">Surface Hub 硬體診斷工具的「帳戶設定」區段不會收集任何資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-106">The "Account Settings" section of the Surface Hub Hardware Diagnostic tool doesn’t collect any information.</span></span> <span data-ttu-id="1f947-107">輸入為輸入的電子郵件和密碼只會直接用於您的環境，不會收集或傳輸給任何人。</span><span class="sxs-lookup"><span data-stu-id="1f947-107">The email and password that are entered as input are used only directly on your environment and not collected or transferred to anyone.</span></span> <span data-ttu-id="1f947-108">登入資訊只會持續直到應用程式關閉或您結束 Surface Hub 上的目前會話。</span><span class="sxs-lookup"><span data-stu-id="1f947-108">The login information persists only until the application is closed or you end the current session on the Surface Hub.</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="1f947-109">執行此應用程式不需要系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="1f947-109">Administrator privileges are not required to run this application.</span></span>
> * <span data-ttu-id="1f947-110">在您向 Microsoft 開啟服務通話之前，應該先與本地系統管理員討論診斷結果。</span><span class="sxs-lookup"><span data-stu-id="1f947-110">The results of the diagnostic should be discussed with your local administrator before you open a service call with Microsoft.</span></span>

### <a name="surface-hub-hardware-diagnostic"></a><span data-ttu-id="1f947-111">Surface Hub 硬體診斷</span><span class="sxs-lookup"><span data-stu-id="1f947-111">Surface Hub Hardware Diagnostic</span></span>

<span data-ttu-id="1f947-112">根據預設 [，Surface Hub 硬體](https://www.microsoft.com/store/apps/9nblggh51f2g) 診斷應用程式未安裝在較舊版本的 Surface Hub 系統中。</span><span class="sxs-lookup"><span data-stu-id="1f947-112">By default, the [Surface Hub Hardware Diagnostic](https://www.microsoft.com/store/apps/9nblggh51f2g) application isn’t installed in earlier versions of the Surface Hub system.</span></span> <span data-ttu-id="1f947-113">應用程式可從 Microsoft Store 免費提供。</span><span class="sxs-lookup"><span data-stu-id="1f947-113">The application is available for free from the Microsoft Store.</span></span> <span data-ttu-id="1f947-114">安裝應用程式需要系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="1f947-114">Administrator privileges are required to install the application.</span></span>

   ![硬體診斷的螢幕擷取畫面](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a><span data-ttu-id="1f947-116">關於 Surface Hub 硬體診斷工具</span><span class="sxs-lookup"><span data-stu-id="1f947-116">About the Surface Hub Hardware Diagnostic Tool</span></span>

<span data-ttu-id="1f947-117">Surface Hub 硬體診斷工具是一種易於流覽的工具，可讓使用者測試 Surface Hub 裝置中的許多硬體元件。</span><span class="sxs-lookup"><span data-stu-id="1f947-117">The Surface Hub Hardware Diagnostic tool is an easy-to-navigate tool that lets the user test many of the hardware components within the Surface Hub device.</span></span> <span data-ttu-id="1f947-118">此工具也可以測試及驗證 Surface Hub 裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="1f947-118">This tool can also test and verify a Surface Hub device account.</span></span> <span data-ttu-id="1f947-119">本文將說明如何在 Surface Hub 硬體診斷工具內使用帳戶設定測試。</span><span class="sxs-lookup"><span data-stu-id="1f947-119">This article describes how to use the Account Settings test within the Surface Hub Hardware Diagnostic tool.</span></span>

> [!NOTE]
> <span data-ttu-id="1f947-120">Surface Hub 的裝置帳戶應該先建立，再執行任何測試。</span><span class="sxs-lookup"><span data-stu-id="1f947-120">The device account for the Surface Hub should be created before any testing is done.</span></span> <span data-ttu-id="1f947-121">Surface Hub 系統管理員指南提供指示和 PowerShell 腳本，可協助您建立內部部署、線上 office365 (或) 裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="1f947-121">The Surface Hub Administrator Guide provides instructions and PowerShell scripts to help you create on-premises, online (Office365), or hybrid device accounts.</span></span> <span data-ttu-id="1f947-122">若要詳細資訊，請前往指南中的 Surface Hub ([建立 ](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub)) 裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="1f947-122">For more information, go to the [Create and test a device account (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) topic in the guide.</span></span>

### <a name="device-account-testing-process"></a><span data-ttu-id="1f947-123">裝置帳戶測試程式</span><span class="sxs-lookup"><span data-stu-id="1f947-123">Device account testing process</span></span>

1. <span data-ttu-id="1f947-124">流覽至 **所有應用程式**，然後找出 Surface Hub 硬體診斷應用程式。</span><span class="sxs-lookup"><span data-stu-id="1f947-124">Navigate to **All Apps**, and then locate the Surface Hub Hardware Diagnostic application.</span></span>

    ![所有應用程式的螢幕擷取畫面](images/02-all-apps.png)

1. <span data-ttu-id="1f947-126">應用程式啟動時， **歡迎頁面會** 提供文字視窗，說明您測試中樞的原因。</span><span class="sxs-lookup"><span data-stu-id="1f947-126">When the application starts, the **Welcome** page provides a text window to document the reason why you are testing the Hub.</span></span> <span data-ttu-id="1f947-127">此筆記可以連同測試結束時的診斷結果一起儲存到 USB。</span><span class="sxs-lookup"><span data-stu-id="1f947-127">This note can be saved to USB together with the diagnostic results at the conclusion of testing.</span></span> <span data-ttu-id="1f947-128">輸入筆記完成後，請 **選取繼續按鈕** 。</span><span class="sxs-lookup"><span data-stu-id="1f947-128">After you finish entering a note, select the **Continue** button.</span></span>

    >[!NOTE]
    ><span data-ttu-id="1f947-129">在存存診斷結果時，請勿變更預設路徑或選取子目錄。</span><span class="sxs-lookup"><span data-stu-id="1f947-129">When saving diagnostic results, do not change the default path or select a subdirectory.</span></span> <span data-ttu-id="1f947-130">檔案稍後可以透過檔案檔案管理器應用程式複製。</span><span class="sxs-lookup"><span data-stu-id="1f947-130">The files can be copied later via the File Explorer app.</span></span>

    ![歡迎的螢幕擷取畫面](images/03-welcome.png)

1. <span data-ttu-id="1f947-132">下一個畫面會提供您測試所有或部分 Surface Hub 元件的選項。</span><span class="sxs-lookup"><span data-stu-id="1f947-132">The next screen provides you the option to test all or some of the Surface Hub components.</span></span> <span data-ttu-id="1f947-133">若要開始測試裝置帳戶，請 **選取測試結果圖示** 。</span><span class="sxs-lookup"><span data-stu-id="1f947-133">To begin testing the device account, select the **Test Results** icon.</span></span>

    ![測試選項的螢幕擷取畫面](images/04-test-results-1.png)

    ![測試結果的螢幕擷取畫面](images/05-test-results-2.png)

1. <span data-ttu-id="1f947-136">選取 **帳戶設定**。</span><span class="sxs-lookup"><span data-stu-id="1f947-136">Select **Account Settings**.</span></span>  

    ![帳戶設定螢幕擷取畫面](images/06-account-settings.png)

    <span data-ttu-id="1f947-138">帳戶設定畫面可用來測試您的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="1f947-138">The Account Settings screen is used to test your device account.</span></span>

    ![帳戶設定詳細資料螢幕擷取畫面](images/07-account-settings-details.png)

1. <span data-ttu-id="1f947-140">輸入裝置帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="1f947-140">Enter the email address of your device account.</span></span> <span data-ttu-id="1f947-141">密碼為選擇性，但建議使用。</span><span class="sxs-lookup"><span data-stu-id="1f947-141">The password is optional but is recommended.</span></span> <span data-ttu-id="1f947-142">當您準備好 **繼續時** ，請選取測試帳戶按鈕。</span><span class="sxs-lookup"><span data-stu-id="1f947-142">Select the **Test Account** button when you are ready to continue.</span></span>

    ![測試帳戶的螢幕擷取畫面](images/08-test-account.png)

1. <span data-ttu-id="1f947-144">測試完成後，請檢閱四個測試區域的結果。</span><span class="sxs-lookup"><span data-stu-id="1f947-144">After testing is finished, review the results for the four areas of testing.</span></span> <span data-ttu-id="1f947-145">選取每個主題旁邊的加號或減號，即可展開或展開每個區段。</span><span class="sxs-lookup"><span data-stu-id="1f947-145">Each section can be expanded or collapsed by selecting the Plus or Minus sign next to each topic.</span></span>

    **<span data-ttu-id="1f947-146">網路</span><span class="sxs-lookup"><span data-stu-id="1f947-146">Network</span></span>**

    ![網路螢幕擷取畫面](images/09-network.png)

    **<span data-ttu-id="1f947-148">環境</span><span class="sxs-lookup"><span data-stu-id="1f947-148">Environment</span></span>**

    ![環境螢幕擷取畫面](images/10-environment.png)

    **<span data-ttu-id="1f947-150">憑證</span><span class="sxs-lookup"><span data-stu-id="1f947-150">Certificates</span></span>**

    ![憑證的螢幕擷取畫面](images/11-certificates.png)

    **<span data-ttu-id="1f947-152">信任模型</span><span class="sxs-lookup"><span data-stu-id="1f947-152">Trust Model</span></span>**

    ![信任模型的螢幕擷取畫面](images/12-trust-model.png)

## <a name="appendix"></a><span data-ttu-id="1f947-154">附錄</span><span class="sxs-lookup"><span data-stu-id="1f947-154">Appendix</span></span>

### <a name="field-messages-and-resolution"></a><span data-ttu-id="1f947-155">域訊息和解決方案</span><span class="sxs-lookup"><span data-stu-id="1f947-155">Field messages and resolution</span></span>

#### <a name="network"></a><span data-ttu-id="1f947-156">網路</span><span class="sxs-lookup"><span data-stu-id="1f947-156">Network</span></span>

<span data-ttu-id="1f947-157">欄位</span><span class="sxs-lookup"><span data-stu-id="1f947-157">Field</span></span> |<span data-ttu-id="1f947-158">成功</span><span class="sxs-lookup"><span data-stu-id="1f947-158">Success</span></span> |<span data-ttu-id="1f947-159">失敗</span><span class="sxs-lookup"><span data-stu-id="1f947-159">Failure</span></span> |<span data-ttu-id="1f947-160">留言</span><span class="sxs-lookup"><span data-stu-id="1f947-160">Comment</span></span> |<span data-ttu-id="1f947-161">參考</span><span class="sxs-lookup"><span data-stu-id="1f947-161">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f947-162">網際網路連接</span><span class="sxs-lookup"><span data-stu-id="1f947-162">Internet Connectivity</span></span> |<span data-ttu-id="1f947-163">裝置具有網際網路連接</span><span class="sxs-lookup"><span data-stu-id="1f947-163">Device does have Internet connectivity</span></span> |<span data-ttu-id="1f947-164">裝置沒有網際網路連接</span><span class="sxs-lookup"><span data-stu-id="1f947-164">Device does not have Internet connectivity</span></span> |<span data-ttu-id="1f947-165">驗證網際網路連接能力，包括 Proxy 連接</span><span class="sxs-lookup"><span data-stu-id="1f947-165">Verifies internet connectivity, including proxy connection</span></span> |
<span data-ttu-id="1f947-166">HTTP 版本</span><span class="sxs-lookup"><span data-stu-id="1f947-166">HTTP Version</span></span> |<span data-ttu-id="1f947-167">1.1</span><span class="sxs-lookup"><span data-stu-id="1f947-167">1.1</span></span> |<span data-ttu-id="1f947-168">1.0</span><span class="sxs-lookup"><span data-stu-id="1f947-168">1.0</span></span> |<span data-ttu-id="1f947-169">如果找到 HTTP 1.0，就會導致 WU 和 Store 發生問題</span><span class="sxs-lookup"><span data-stu-id="1f947-169">If HTTP 1.0 found, it will cause issue with WU and Store</span></span> |
<span data-ttu-id="1f947-170">直接網際網路連接</span><span class="sxs-lookup"><span data-stu-id="1f947-170">Direct Internet Connectivity</span></span> |<span data-ttu-id="1f947-171">裝置已配置 Proxy 的裝置未進行 Proxy 的安裝</span><span class="sxs-lookup"><span data-stu-id="1f947-171">Device has a Proxy configured Device has no Proxy configured</span></span> |<span data-ttu-id="1f947-172">無</span><span class="sxs-lookup"><span data-stu-id="1f947-172">N/A</span></span> |<span data-ttu-id="1f947-173">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-173">Informational.</span></span> <span data-ttu-id="1f947-174">您的裝置是否位於 Proxy 後面？</span><span class="sxs-lookup"><span data-stu-id="1f947-174">Is your device behind a proxy?</span></span> |
<span data-ttu-id="1f947-175">Proxy 位址</span><span class="sxs-lookup"><span data-stu-id="1f947-175">Proxy Address</span></span> | | |<span data-ttu-id="1f947-176">如果已配置，會返回 Proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="1f947-176">If configured, returns proxy address.</span></span> |
<span data-ttu-id="1f947-177">Proxy 驗證</span><span class="sxs-lookup"><span data-stu-id="1f947-177">Proxy Authentication</span></span> |<span data-ttu-id="1f947-178">Proxy 不需要驗證</span><span class="sxs-lookup"><span data-stu-id="1f947-178">Proxy does not require Authentication</span></span> |<span data-ttu-id="1f947-179">Proxy 需要 Proxy 驗證</span><span class="sxs-lookup"><span data-stu-id="1f947-179">Proxy requires Proxy Auth</span></span> |<span data-ttu-id="1f947-180">如果使用者已在 Edge 中開啟會話，而且已透過 Proxy 進行驗證，則結果可能是誤誤。</span><span class="sxs-lookup"><span data-stu-id="1f947-180">Result may be a false positive if a user already has an open session in Edge and has authenticated through the proxy.</span></span> |
<span data-ttu-id="1f947-181">Proxy 驗證類型</span><span class="sxs-lookup"><span data-stu-id="1f947-181">Proxy Auth Types</span></span> | | |<span data-ttu-id="1f947-182">如果使用 Proxy 驗證，請返回 Proxy 所宣告的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="1f947-182">If proxy authentication is used, return the Authentication methods advertised by the proxy.</span></span>  |

#### <a name="environment"></a><span data-ttu-id="1f947-183">環境</span><span class="sxs-lookup"><span data-stu-id="1f947-183">Environment</span></span>

<span data-ttu-id="1f947-184">欄位</span><span class="sxs-lookup"><span data-stu-id="1f947-184">Field</span></span> |<span data-ttu-id="1f947-185">成功</span><span class="sxs-lookup"><span data-stu-id="1f947-185">Success</span></span> |<span data-ttu-id="1f947-186">失敗</span><span class="sxs-lookup"><span data-stu-id="1f947-186">Failure</span></span> |<span data-ttu-id="1f947-187">留言</span><span class="sxs-lookup"><span data-stu-id="1f947-187">Comment</span></span> |<span data-ttu-id="1f947-188">參考</span><span class="sxs-lookup"><span data-stu-id="1f947-188">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f947-189">SIP 網域</span><span class="sxs-lookup"><span data-stu-id="1f947-189">SIP Domain</span></span> | | |<span data-ttu-id="1f947-190">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-190">Informational.</span></span>  |
<span data-ttu-id="1f947-191">Skype 環境</span><span class="sxs-lookup"><span data-stu-id="1f947-191">Skype Environment</span></span> |<span data-ttu-id="1f947-192">商務用 Skype Online、商務用 Skype OnPrem、商務用 Skype 混合式</span><span class="sxs-lookup"><span data-stu-id="1f947-192">Skype for Business Online, Skype for Business OnPrem, Skype for Business Hybrid</span></span> |<span data-ttu-id="1f947-193">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-193">Informational.</span></span> |<span data-ttu-id="1f947-194">偵測到的環境類型。</span><span class="sxs-lookup"><span data-stu-id="1f947-194">What type of environment was detected.</span></span> <span data-ttu-id="1f947-195">注意：只有在輸入密碼時，才能偵測混合式。</span><span class="sxs-lookup"><span data-stu-id="1f947-195">Note: Hybrid can only be detected if the password is entered.</span></span>
<span data-ttu-id="1f947-196">LyncDiscover FQDN</span><span class="sxs-lookup"><span data-stu-id="1f947-196">LyncDiscover FQDN</span></span> | | |<span data-ttu-id="1f947-197">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-197">Informational.</span></span> <span data-ttu-id="1f947-198">顯示 LyncDiscover DNS 結果</span><span class="sxs-lookup"><span data-stu-id="1f947-198">Displays the LyncDiscover DNS result</span></span> |
<span data-ttu-id="1f947-199">LyncDiscover URI</span><span class="sxs-lookup"><span data-stu-id="1f947-199">LyncDiscover URI</span></span> | | |<span data-ttu-id="1f947-200">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-200">Informational.</span></span> <span data-ttu-id="1f947-201">顯示用來在您的環境中執行 LyncDiscover 的 URL。</span><span class="sxs-lookup"><span data-stu-id="1f947-201">Displays the URL used to perform a LyncDiscover on your environment.</span></span>|
<span data-ttu-id="1f947-202">LyncDiscover</span><span class="sxs-lookup"><span data-stu-id="1f947-202">LyncDiscover</span></span> |<span data-ttu-id="1f947-203">成功連接</span><span class="sxs-lookup"><span data-stu-id="1f947-203">Connection Successful</span></span> |<span data-ttu-id="1f947-204">連接失敗</span><span class="sxs-lookup"><span data-stu-id="1f947-204">Connection Failed</span></span> |<span data-ttu-id="1f947-205">LyncDiscover Web 服務的回應。</span><span class="sxs-lookup"><span data-stu-id="1f947-205">Response from LyncDiscover web service.</span></span> |
<span data-ttu-id="1f947-206">SIP Pool Hostname</span><span class="sxs-lookup"><span data-stu-id="1f947-206">SIP Pool Hostname</span></span> | | |<span data-ttu-id="1f947-207">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-207">Informational.</span></span> <span data-ttu-id="1f947-208">顯示從 LyncDiscover 所探索的 SIP 資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="1f947-208">Display the SIP pool name discovered from LyncDiscover</span></span> |

#### <a name="certificates-in-premises-hybrid-only"></a><span data-ttu-id="1f947-209">憑證 (內部部署混合式) </span><span class="sxs-lookup"><span data-stu-id="1f947-209">Certificates (in-premises hybrid only)</span></span>

<span data-ttu-id="1f947-210">LyncDiscover 憑證</span><span class="sxs-lookup"><span data-stu-id="1f947-210">LyncDiscover Certificate</span></span>

<span data-ttu-id="1f947-211">欄位</span><span class="sxs-lookup"><span data-stu-id="1f947-211">Field</span></span> |<span data-ttu-id="1f947-212">成功</span><span class="sxs-lookup"><span data-stu-id="1f947-212">Success</span></span> |<span data-ttu-id="1f947-213">失敗</span><span class="sxs-lookup"><span data-stu-id="1f947-213">Failure</span></span> |<span data-ttu-id="1f947-214">留言</span><span class="sxs-lookup"><span data-stu-id="1f947-214">Comment</span></span> |<span data-ttu-id="1f947-215">參考</span><span class="sxs-lookup"><span data-stu-id="1f947-215">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f947-216">LyncDiscover Cert CN</span><span class="sxs-lookup"><span data-stu-id="1f947-216">LyncDiscover Cert CN</span></span> | | |<span data-ttu-id="1f947-217">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-217">Informational.</span></span> <span data-ttu-id="1f947-218">顯示 DL 認證共同名稱</span><span class="sxs-lookup"><span data-stu-id="1f947-218">Displays the LD cert Common name</span></span> |
<span data-ttu-id="1f947-219">LyncDiscover Cert CA</span><span class="sxs-lookup"><span data-stu-id="1f947-219">LyncDiscover Cert CA</span></span> | | |<span data-ttu-id="1f947-220">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-220">Informational.</span></span> <span data-ttu-id="1f947-221">顯示 DL Cert CA</span><span class="sxs-lookup"><span data-stu-id="1f947-221">Displays the LD Cert CA</span></span> |
<span data-ttu-id="1f947-222">LyncDiscover 認證根 CA</span><span class="sxs-lookup"><span data-stu-id="1f947-222">LyncDiscover Cert Root CA</span></span> | | |<span data-ttu-id="1f947-223">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-223">Informational.</span></span> <span data-ttu-id="1f947-224">顯示 DL 證書根 CA ，如果可用。</span><span class="sxs-lookup"><span data-stu-id="1f947-224">Displays the LD Cert Root CA, if available.</span></span> |
<span data-ttu-id="1f947-225">DL 信任狀態</span><span class="sxs-lookup"><span data-stu-id="1f947-225">LD Trust Status</span></span> |<span data-ttu-id="1f947-226">憑證為信任。</span><span class="sxs-lookup"><span data-stu-id="1f947-226">Certificate is Trusted.</span></span> |<span data-ttu-id="1f947-227">憑證不可信任，請新增根 CA。</span><span class="sxs-lookup"><span data-stu-id="1f947-227">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="1f947-228">針對本地憑證存放區驗證憑證。</span><span class="sxs-lookup"><span data-stu-id="1f947-228">Verify the certificate against the local cert store.</span></span> <span data-ttu-id="1f947-229">如果電腦信任憑證，則會以正數表示。</span><span class="sxs-lookup"><span data-stu-id="1f947-229">Returns positive if the machine trusts the certificate.</span></span>|<span data-ttu-id="1f947-230">[使用 PowerShell 下載及部署商務用 Skype 憑證](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) /[Surface Hub 資源配置套件的支援專案](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="1f947-230">[Download and deploy Skype for Business certificates using PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/)/[Supported items for Surface Hub provisioning packages](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span></span>

<span data-ttu-id="1f947-231">SIP Pool 認證</span><span class="sxs-lookup"><span data-stu-id="1f947-231">SIP Pool Certification</span></span>

<span data-ttu-id="1f947-232">欄位</span><span class="sxs-lookup"><span data-stu-id="1f947-232">Field</span></span> |<span data-ttu-id="1f947-233">成功</span><span class="sxs-lookup"><span data-stu-id="1f947-233">Success</span></span> |<span data-ttu-id="1f947-234">失敗</span><span class="sxs-lookup"><span data-stu-id="1f947-234">Failure</span></span> |<span data-ttu-id="1f947-235">留言</span><span class="sxs-lookup"><span data-stu-id="1f947-235">Comment</span></span> |<span data-ttu-id="1f947-236">參考</span><span class="sxs-lookup"><span data-stu-id="1f947-236">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f947-237">SIP Pool Cert CN</span><span class="sxs-lookup"><span data-stu-id="1f947-237">SIP Pool Cert CN</span></span> | | |<span data-ttu-id="1f947-238"> (內容) </span><span class="sxs-lookup"><span data-stu-id="1f947-238">(CONTENTS)</span></span> |
<span data-ttu-id="1f947-239">SIP Pool Cert CA</span><span class="sxs-lookup"><span data-stu-id="1f947-239">SIP Pool Cert CA</span></span> | | |<span data-ttu-id="1f947-240"> (內容) </span><span class="sxs-lookup"><span data-stu-id="1f947-240">(CONTENTS)</span></span> |
<span data-ttu-id="1f947-241">SIP Pool 信任狀態</span><span class="sxs-lookup"><span data-stu-id="1f947-241">SIP Pool Trust Status</span></span> |<span data-ttu-id="1f947-242">憑證為信任。</span><span class="sxs-lookup"><span data-stu-id="1f947-242">Certificate is Trusted.</span></span> |<span data-ttu-id="1f947-243">憑證不可信任，請新增根 CA。</span><span class="sxs-lookup"><span data-stu-id="1f947-243">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="1f947-244">針對本地憑證存放區驗證憑證，如果裝置信任憑證，則退回正數。</span><span class="sxs-lookup"><span data-stu-id="1f947-244">Verify the certificate against the local cert store and return a positive if the devices trusts the certificate.</span></span> |
<span data-ttu-id="1f947-245">SIP Pool Cert Root CA</span><span class="sxs-lookup"><span data-stu-id="1f947-245">SIP Pool Cert Root CA</span></span> | | |<span data-ttu-id="1f947-246">資訊。</span><span class="sxs-lookup"><span data-stu-id="1f947-246">Information.</span></span> <span data-ttu-id="1f947-247">顯示 SIP Pool Cert Root CA ，如果可用。</span><span class="sxs-lookup"><span data-stu-id="1f947-247">Display the SIP Pool Cert Root CA, if available.</span></span> |

#### <a name="trust-model-on-premises-hybrid-only"></a><span data-ttu-id="1f947-248">信任模型 (內部部署混合式) </span><span class="sxs-lookup"><span data-stu-id="1f947-248">Trust Model (on-premises hybrid only)</span></span>

<span data-ttu-id="1f947-249">欄位</span><span class="sxs-lookup"><span data-stu-id="1f947-249">Field</span></span> |<span data-ttu-id="1f947-250">成功</span><span class="sxs-lookup"><span data-stu-id="1f947-250">Success</span></span> |<span data-ttu-id="1f947-251">失敗</span><span class="sxs-lookup"><span data-stu-id="1f947-251">Failure</span></span> |<span data-ttu-id="1f947-252">留言</span><span class="sxs-lookup"><span data-stu-id="1f947-252">Comment</span></span> |<span data-ttu-id="1f947-253">參考</span><span class="sxs-lookup"><span data-stu-id="1f947-253">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="1f947-254">信任模型狀態</span><span class="sxs-lookup"><span data-stu-id="1f947-254">Trust Model Status</span></span> |<span data-ttu-id="1f947-255">未偵測到信任模型問題。</span><span class="sxs-lookup"><span data-stu-id="1f947-255">No Trust Model Issue Detected.</span></span> |<span data-ttu-id="1f947-256">SIP 網域和伺服器網域不同，請新增下列網域。</span><span class="sxs-lookup"><span data-stu-id="1f947-256">SIP Domain and server domain are different please add the following domains.</span></span> |<span data-ttu-id="1f947-257">檢查 IBM FQDN/IBM Server 名稱/資料庫伺服器名稱以尋找信任模型問題。</span><span class="sxs-lookup"><span data-stu-id="1f947-257">Check the LD FQDN/ LD Server Name/ Pool Server name for Trust model issue.</span></span> 
<span data-ttu-id="1f947-258">功能變數名稱 () </span><span class="sxs-lookup"><span data-stu-id="1f947-258">Domain Name(s)</span></span> | | |<span data-ttu-id="1f947-259">返回應該新增的網域清單，讓 SFB 能夠連接。</span><span class="sxs-lookup"><span data-stu-id="1f947-259">Return the list of domains that should be added for SFB to connect.</span></span> |
