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
ms.openlocfilehash: 127be0a5f320418d8a1086aec3de62e3ef54e42a
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831345"
---
# <span data-ttu-id="943a5-104">使用 Surface Hub 硬體診斷工具來測試裝置帳戶</span><span class="sxs-lookup"><span data-stu-id="943a5-104">Using the Surface Hub Hardware Diagnostic Tool to test a device account</span></span>

## <span data-ttu-id="943a5-105">簡介</span><span class="sxs-lookup"><span data-stu-id="943a5-105">Introduction</span></span>

> [!NOTE]
> <span data-ttu-id="943a5-106">Surface Hub 硬體診斷工具的 [帳戶設定] 區段不會收集任何資訊。</span><span class="sxs-lookup"><span data-stu-id="943a5-106">The "Account Settings" section of the Surface Hub Hardware Diagnostic tool doesn’t collect any information.</span></span> <span data-ttu-id="943a5-107">輸入為輸入的電子郵件和密碼只會直接在您的環境中使用，不會收集或轉讓給任何人。</span><span class="sxs-lookup"><span data-stu-id="943a5-107">The email and password that are entered as input are used only directly on your environment and not collected or transferred to anyone.</span></span> <span data-ttu-id="943a5-108">登入資訊只有在應用程式關閉或您結束 Surface Hub 上的目前會話，才會持續出現。</span><span class="sxs-lookup"><span data-stu-id="943a5-108">The login information persists only until the application is closed or you end the current session on the Surface Hub.</span></span>

> [!IMPORTANT]
> * <span data-ttu-id="943a5-109">執行這個應用程式不需要系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="943a5-109">Administrator privileges are not required to run this application.</span></span>
> * <span data-ttu-id="943a5-110">在使用 Microsoft 開啟服務電話之前，請先與您的本機系統管理員討論診斷結果。</span><span class="sxs-lookup"><span data-stu-id="943a5-110">The results of the diagnostic should be discussed with your local administrator before you open a service call with Microsoft.</span></span>

### <span data-ttu-id="943a5-111">Surface Hub 硬體診斷</span><span class="sxs-lookup"><span data-stu-id="943a5-111">Surface Hub Hardware Diagnostic</span></span>

<span data-ttu-id="943a5-112">根據預設， [Surface Hub 硬體診斷](https://www.microsoft.com/store/apps/9nblggh51f2g)應用程式不會安裝在舊版 Surface Hub 系統中。</span><span class="sxs-lookup"><span data-stu-id="943a5-112">By default, the [Surface Hub Hardware Diagnostic](https://www.microsoft.com/store/apps/9nblggh51f2g) application isn’t installed in earlier versions of the Surface Hub system.</span></span> <span data-ttu-id="943a5-113">您可以從 Microsoft 網上商店免費取得該應用程式。</span><span class="sxs-lookup"><span data-stu-id="943a5-113">The application is available for free from the Microsoft Store.</span></span> <span data-ttu-id="943a5-114">必須具備系統管理員許可權才能安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="943a5-114">Administrator privileges are required to install the application.</span></span>

   ![硬體診斷的螢幕擷取畫面](images/01-diagnostic.png)

## <span data-ttu-id="943a5-116">關於 Surface Hub 硬體診斷工具</span><span class="sxs-lookup"><span data-stu-id="943a5-116">About the Surface Hub Hardware Diagnostic Tool</span></span>

<span data-ttu-id="943a5-117">Surface Hub 硬體診斷工具是一種易於流覽的工具，可讓使用者在 Surface Hub 裝置中測試許多硬體元件。</span><span class="sxs-lookup"><span data-stu-id="943a5-117">The Surface Hub Hardware Diagnostic tool is an easy-to-navigate tool that lets the user test many of the hardware components within the Surface Hub device.</span></span> <span data-ttu-id="943a5-118">這個工具也可以測試並驗證 Surface Hub 裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="943a5-118">This tool can also test and verify a Surface Hub device account.</span></span> <span data-ttu-id="943a5-119">本文說明如何在 Surface Hub 硬體診斷工具中使用帳戶設定測試。</span><span class="sxs-lookup"><span data-stu-id="943a5-119">This article describes how to use the Account Settings test within the Surface Hub Hardware Diagnostic tool.</span></span>

> [!NOTE]
> <span data-ttu-id="943a5-120">必須先建立 Surface Hub 的裝置帳戶，才能完成任何測試。</span><span class="sxs-lookup"><span data-stu-id="943a5-120">The device account for the Surface Hub should be created before any testing is done.</span></span> <span data-ttu-id="943a5-121">Surface Hub 管理員指南提供指示和 PowerShell 腳本，可協助您建立內部部署、線上（Office365）或混合式裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="943a5-121">The Surface Hub Administrator Guide provides instructions and PowerShell scripts to help you create on-premises, online (Office365), or hybrid device accounts.</span></span> <span data-ttu-id="943a5-122">如需詳細資訊，請移至指南中的[建立和測試裝置帳戶（Surface Hub）](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub)主題。</span><span class="sxs-lookup"><span data-stu-id="943a5-122">For more information, go to the [Create and test a device account (Surface Hub)](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub) topic in the guide.</span></span>

### <span data-ttu-id="943a5-123">裝置帳戶測試程式</span><span class="sxs-lookup"><span data-stu-id="943a5-123">Device account testing process</span></span>

1. <span data-ttu-id="943a5-124">流覽至 [**所有應用程式**]，然後找出 Surface Hub 硬體診斷應用程式。</span><span class="sxs-lookup"><span data-stu-id="943a5-124">Navigate to **All Apps**, and then locate the Surface Hub Hardware Diagnostic application.</span></span>

    ![[所有應用程式] 的螢幕擷取畫面](images/02-all-apps.png)

1. <span data-ttu-id="943a5-126">當應用程式啟動時，[**歡迎**] 頁面會提供文字視窗，以記錄您測試中樞的原因。</span><span class="sxs-lookup"><span data-stu-id="943a5-126">When the application starts, the **Welcome** page provides a text window to document the reason why you are testing the Hub.</span></span> <span data-ttu-id="943a5-127">在測試結束時，您可以將此筆記連同診斷結果一起儲存至 USB。</span><span class="sxs-lookup"><span data-stu-id="943a5-127">This note can be saved to USB together with the diagnostic results at the conclusion of testing.</span></span> <span data-ttu-id="943a5-128">完成輸入筆記後，請選取 [**繼續**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="943a5-128">After you finish entering a note, select the **Continue** button.</span></span>

    ![歡迎的螢幕擷取畫面](images/03-welcome.png)

1. <span data-ttu-id="943a5-130">下一個畫面會提供測試全部或部分 Surface Hub 元件的選項。</span><span class="sxs-lookup"><span data-stu-id="943a5-130">The next screen provides you the option to test all or some of the Surface Hub components.</span></span> <span data-ttu-id="943a5-131">若要開始測試裝置帳戶，請選取 [**測試結果**] 圖示。</span><span class="sxs-lookup"><span data-stu-id="943a5-131">To begin testing the device account, select the **Test Results** icon.</span></span>

    ![測試結果的螢幕擷取畫面](images/04-test-results-1.png)

    ![測試結果的螢幕擷取畫面](images/05-test-results-2.png)

1. <span data-ttu-id="943a5-134">選取 [**帳戶設定**]。</span><span class="sxs-lookup"><span data-stu-id="943a5-134">Select **Account Settings**.</span></span>  

    ![帳戶設定的螢幕擷取畫面](images/06-account-settings.png)

    <span data-ttu-id="943a5-136">[帳戶設定] 畫面可用來測試您的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="943a5-136">The Account Settings screen is used to test your device account.</span></span>

    ![[帳戶設定] 詳細資料的螢幕擷取畫面](images/07-account-settings-details.png)

1. <span data-ttu-id="943a5-138">輸入您的裝置帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="943a5-138">Enter the email address of your device account.</span></span> <span data-ttu-id="943a5-139">密碼是選擇性的，但建議使用。</span><span class="sxs-lookup"><span data-stu-id="943a5-139">The password is optional but is recommended.</span></span> <span data-ttu-id="943a5-140">當您準備好要繼續時，請選取 [**測試帳戶**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="943a5-140">Select the **Test Account** button when you are ready to continue.</span></span>

    ![測試帳戶的螢幕擷取畫面](images/08-test-account.png)

1. <span data-ttu-id="943a5-142">測試完成後，請檢查四個測試區域的結果。</span><span class="sxs-lookup"><span data-stu-id="943a5-142">After testing is finished, review the results for the four areas of testing.</span></span> <span data-ttu-id="943a5-143">您可以透過選取每個主題旁的加號或減號，展開或折迭每個區段。</span><span class="sxs-lookup"><span data-stu-id="943a5-143">Each section can be expanded or collapsed by selecting the Plus or Minus sign next to each topic.</span></span>

    **<span data-ttu-id="943a5-144">網路</span><span class="sxs-lookup"><span data-stu-id="943a5-144">Network</span></span>**

    ![網路的螢幕擷取畫面](images/09-network.png)

    **<span data-ttu-id="943a5-146">環境</span><span class="sxs-lookup"><span data-stu-id="943a5-146">Environment</span></span>**

    ![環境的螢幕擷取畫面](images/10-environment.png)

    **<span data-ttu-id="943a5-148">憑證</span><span class="sxs-lookup"><span data-stu-id="943a5-148">Certificates</span></span>**

    ![憑證的螢幕擷取畫面](images/11-certificates.png)

    **<span data-ttu-id="943a5-150">信任模型</span><span class="sxs-lookup"><span data-stu-id="943a5-150">Trust Model</span></span>**

    ![信任模型的螢幕擷取畫面](images/12-trust-model.png)

## <span data-ttu-id="943a5-152">附錄</span><span class="sxs-lookup"><span data-stu-id="943a5-152">Appendix</span></span>

### <span data-ttu-id="943a5-153">欄位訊息及解析度</span><span class="sxs-lookup"><span data-stu-id="943a5-153">Field messages and resolution</span></span>

#### <span data-ttu-id="943a5-154">網路</span><span class="sxs-lookup"><span data-stu-id="943a5-154">Network</span></span>

<span data-ttu-id="943a5-155">欄位</span><span class="sxs-lookup"><span data-stu-id="943a5-155">Field</span></span> |<span data-ttu-id="943a5-156">成功</span><span class="sxs-lookup"><span data-stu-id="943a5-156">Success</span></span> |<span data-ttu-id="943a5-157">失敗</span><span class="sxs-lookup"><span data-stu-id="943a5-157">Failure</span></span> |<span data-ttu-id="943a5-158">留言</span><span class="sxs-lookup"><span data-stu-id="943a5-158">Comment</span></span> |<span data-ttu-id="943a5-159">參考</span><span class="sxs-lookup"><span data-stu-id="943a5-159">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="943a5-160">網際網路連線能力</span><span class="sxs-lookup"><span data-stu-id="943a5-160">Internet Connectivity</span></span> |<span data-ttu-id="943a5-161">裝置有網際網路連線能力</span><span class="sxs-lookup"><span data-stu-id="943a5-161">Device does have Internet connectivity</span></span> |<span data-ttu-id="943a5-162">裝置沒有網際網路連線能力</span><span class="sxs-lookup"><span data-stu-id="943a5-162">Device does not have Internet connectivity</span></span> |<span data-ttu-id="943a5-163">驗證網際網路連通性，包括 proxy 連線</span><span class="sxs-lookup"><span data-stu-id="943a5-163">Verifies internet connectivity, including proxy connection</span></span> |
<span data-ttu-id="943a5-164">HTTP 版本</span><span class="sxs-lookup"><span data-stu-id="943a5-164">HTTP Version</span></span> |<span data-ttu-id="943a5-165">1.1</span><span class="sxs-lookup"><span data-stu-id="943a5-165">1.1</span></span> |<span data-ttu-id="943a5-166">1.0</span><span class="sxs-lookup"><span data-stu-id="943a5-166">1.0</span></span> |<span data-ttu-id="943a5-167">如果找到 HTTP 1.0，將會在 WU 和 Store 中造成問題</span><span class="sxs-lookup"><span data-stu-id="943a5-167">If HTTP 1.0 found, it will cause issue with WU and Store</span></span> |
<span data-ttu-id="943a5-168">直接網際網路連線</span><span class="sxs-lookup"><span data-stu-id="943a5-168">Direct Internet Connectivity</span></span> |<span data-ttu-id="943a5-169">裝置已設定 Proxy 的裝置沒有設定 Proxy</span><span class="sxs-lookup"><span data-stu-id="943a5-169">Device has a Proxy configured Device has no Proxy configured</span></span> |<span data-ttu-id="943a5-170">無</span><span class="sxs-lookup"><span data-stu-id="943a5-170">N/A</span></span> |<span data-ttu-id="943a5-171">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-171">Informational.</span></span> <span data-ttu-id="943a5-172">您的裝置是在 proxy 後嗎？</span><span class="sxs-lookup"><span data-stu-id="943a5-172">Is your device behind a proxy?</span></span> |
<span data-ttu-id="943a5-173">Proxy 位址</span><span class="sxs-lookup"><span data-stu-id="943a5-173">Proxy Address</span></span> | | |<span data-ttu-id="943a5-174">如果已設定，則會傳回 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="943a5-174">If configured, returns proxy address.</span></span> |
<span data-ttu-id="943a5-175">Proxy 驗證</span><span class="sxs-lookup"><span data-stu-id="943a5-175">Proxy Authentication</span></span> |<span data-ttu-id="943a5-176">Proxy 不需要驗證</span><span class="sxs-lookup"><span data-stu-id="943a5-176">Proxy does not require Authentication</span></span> |<span data-ttu-id="943a5-177">Proxy 需要 Proxy 驗證</span><span class="sxs-lookup"><span data-stu-id="943a5-177">Proxy requires Proxy Auth</span></span> |<span data-ttu-id="943a5-178">如果使用者已在 Edge 中有開啟的會話，且已透過 proxy 進行驗證，結果可能是誤報。</span><span class="sxs-lookup"><span data-stu-id="943a5-178">Result may be a false positive if a user already has an open session in Edge and has authenticated through the proxy.</span></span> |
<span data-ttu-id="943a5-179">Proxy 驗證類型</span><span class="sxs-lookup"><span data-stu-id="943a5-179">Proxy Auth Types</span></span> | | |<span data-ttu-id="943a5-180">如果使用 proxy 驗證，請傳回 proxy 宣告的驗證方法。</span><span class="sxs-lookup"><span data-stu-id="943a5-180">If proxy authentication is used, return the Authentication methods advertised by the proxy.</span></span>  |

#### <span data-ttu-id="943a5-181">環境</span><span class="sxs-lookup"><span data-stu-id="943a5-181">Environment</span></span>

<span data-ttu-id="943a5-182">欄位</span><span class="sxs-lookup"><span data-stu-id="943a5-182">Field</span></span> |<span data-ttu-id="943a5-183">成功</span><span class="sxs-lookup"><span data-stu-id="943a5-183">Success</span></span> |<span data-ttu-id="943a5-184">失敗</span><span class="sxs-lookup"><span data-stu-id="943a5-184">Failure</span></span> |<span data-ttu-id="943a5-185">留言</span><span class="sxs-lookup"><span data-stu-id="943a5-185">Comment</span></span> |<span data-ttu-id="943a5-186">參考</span><span class="sxs-lookup"><span data-stu-id="943a5-186">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="943a5-187">SIP 網域</span><span class="sxs-lookup"><span data-stu-id="943a5-187">SIP Domain</span></span> | | |<span data-ttu-id="943a5-188">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-188">Informational.</span></span>  |
<span data-ttu-id="943a5-189">Skype 環境</span><span class="sxs-lookup"><span data-stu-id="943a5-189">Skype Environment</span></span> |<span data-ttu-id="943a5-190">商務用 skype Online、商務用 Skype OnPrem、商務用 Skype 混合式</span><span class="sxs-lookup"><span data-stu-id="943a5-190">Skype for Business Online, Skype for Business OnPrem, Skype for Business Hybrid</span></span> |<span data-ttu-id="943a5-191">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-191">Informational.</span></span> |<span data-ttu-id="943a5-192">偵測到的環境類型。</span><span class="sxs-lookup"><span data-stu-id="943a5-192">What type of environment was detected.</span></span> <span data-ttu-id="943a5-193">注意：只有在輸入密碼時，才能檢測到混合式。</span><span class="sxs-lookup"><span data-stu-id="943a5-193">Note: Hybrid can only be detected if the password is entered.</span></span>
<span data-ttu-id="943a5-194">LyncDiscover FQDN</span><span class="sxs-lookup"><span data-stu-id="943a5-194">LyncDiscover FQDN</span></span> | | |<span data-ttu-id="943a5-195">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-195">Informational.</span></span> <span data-ttu-id="943a5-196">顯示 LyncDiscover 的 DNS 結果</span><span class="sxs-lookup"><span data-stu-id="943a5-196">Displays the LyncDiscover DNS result</span></span> |
<span data-ttu-id="943a5-197">LyncDiscover URI</span><span class="sxs-lookup"><span data-stu-id="943a5-197">LyncDiscover URI</span></span> | | |<span data-ttu-id="943a5-198">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-198">Informational.</span></span> <span data-ttu-id="943a5-199">顯示用於在您的環境上執行 LyncDiscover 的 URL。</span><span class="sxs-lookup"><span data-stu-id="943a5-199">Displays the URL used to perform a LyncDiscover on your environment.</span></span>|
<span data-ttu-id="943a5-200">LyncDiscover</span><span class="sxs-lookup"><span data-stu-id="943a5-200">LyncDiscover</span></span> |<span data-ttu-id="943a5-201">連接成功</span><span class="sxs-lookup"><span data-stu-id="943a5-201">Connection Successful</span></span> |<span data-ttu-id="943a5-202">連線失敗</span><span class="sxs-lookup"><span data-stu-id="943a5-202">Connection Failed</span></span> |<span data-ttu-id="943a5-203">從 LyncDiscover web 服務回應。</span><span class="sxs-lookup"><span data-stu-id="943a5-203">Response from LyncDiscover web service.</span></span> |
<span data-ttu-id="943a5-204">SIP 池主機名稱</span><span class="sxs-lookup"><span data-stu-id="943a5-204">SIP Pool Hostname</span></span> | | |<span data-ttu-id="943a5-205">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-205">Informational.</span></span> <span data-ttu-id="943a5-206">顯示從 LyncDiscover 探索的 SIP 池名稱</span><span class="sxs-lookup"><span data-stu-id="943a5-206">Display the SIP pool name discovered from LyncDiscover</span></span> |

#### <span data-ttu-id="943a5-207">憑證（僅限內部部署混合式）</span><span class="sxs-lookup"><span data-stu-id="943a5-207">Certificates (in-premises hybrid only)</span></span>

<span data-ttu-id="943a5-208">LyncDiscover 憑證</span><span class="sxs-lookup"><span data-stu-id="943a5-208">LyncDiscover Certificate</span></span>

<span data-ttu-id="943a5-209">欄位</span><span class="sxs-lookup"><span data-stu-id="943a5-209">Field</span></span> |<span data-ttu-id="943a5-210">成功</span><span class="sxs-lookup"><span data-stu-id="943a5-210">Success</span></span> |<span data-ttu-id="943a5-211">失敗</span><span class="sxs-lookup"><span data-stu-id="943a5-211">Failure</span></span> |<span data-ttu-id="943a5-212">留言</span><span class="sxs-lookup"><span data-stu-id="943a5-212">Comment</span></span> |<span data-ttu-id="943a5-213">參考</span><span class="sxs-lookup"><span data-stu-id="943a5-213">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="943a5-214">LyncDiscover Cert CN</span><span class="sxs-lookup"><span data-stu-id="943a5-214">LyncDiscover Cert CN</span></span> | | |<span data-ttu-id="943a5-215">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-215">Informational.</span></span> <span data-ttu-id="943a5-216">顯示 LD cert 公用名稱</span><span class="sxs-lookup"><span data-stu-id="943a5-216">Displays the LD cert Common name</span></span> |
<span data-ttu-id="943a5-217">LyncDiscover Cert CA</span><span class="sxs-lookup"><span data-stu-id="943a5-217">LyncDiscover Cert CA</span></span> | | |<span data-ttu-id="943a5-218">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-218">Informational.</span></span> <span data-ttu-id="943a5-219">顯示 LD Cert CA</span><span class="sxs-lookup"><span data-stu-id="943a5-219">Displays the LD Cert CA</span></span> |
<span data-ttu-id="943a5-220">LyncDiscover Cert 根 CA</span><span class="sxs-lookup"><span data-stu-id="943a5-220">LyncDiscover Cert Root CA</span></span> | | |<span data-ttu-id="943a5-221">參考.</span><span class="sxs-lookup"><span data-stu-id="943a5-221">Informational.</span></span> <span data-ttu-id="943a5-222">顯示 LD Cert 根 CA （如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="943a5-222">Displays the LD Cert Root CA, if available.</span></span> |
<span data-ttu-id="943a5-223">LD 信任狀態</span><span class="sxs-lookup"><span data-stu-id="943a5-223">LD Trust Status</span></span> |<span data-ttu-id="943a5-224">憑證是受信任的。</span><span class="sxs-lookup"><span data-stu-id="943a5-224">Certificate is Trusted.</span></span> |<span data-ttu-id="943a5-225">證書不受信任，請新增根 CA。</span><span class="sxs-lookup"><span data-stu-id="943a5-225">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="943a5-226">對照本機憑證存放區驗證憑證。</span><span class="sxs-lookup"><span data-stu-id="943a5-226">Verify the certificate against the local cert store.</span></span> <span data-ttu-id="943a5-227">如果電腦信任憑證，則傳回正值。</span><span class="sxs-lookup"><span data-stu-id="943a5-227">Returns positive if the machine trusts the certificate.</span></span>|<span data-ttu-id="943a5-228">[使用 PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / 下載及部署商務用 Skype 憑證[Surface Hub 置備套件支援的專案](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span><span class="sxs-lookup"><span data-stu-id="943a5-228">[Download and deploy Skype for Business certificates using PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/)/[Supported items for Surface Hub provisioning packages](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)</span></span>

<span data-ttu-id="943a5-229">SIP 池認證</span><span class="sxs-lookup"><span data-stu-id="943a5-229">SIP Pool Certification</span></span>

<span data-ttu-id="943a5-230">欄位</span><span class="sxs-lookup"><span data-stu-id="943a5-230">Field</span></span> |<span data-ttu-id="943a5-231">成功</span><span class="sxs-lookup"><span data-stu-id="943a5-231">Success</span></span> |<span data-ttu-id="943a5-232">失敗</span><span class="sxs-lookup"><span data-stu-id="943a5-232">Failure</span></span> |<span data-ttu-id="943a5-233">留言</span><span class="sxs-lookup"><span data-stu-id="943a5-233">Comment</span></span> |<span data-ttu-id="943a5-234">參考</span><span class="sxs-lookup"><span data-stu-id="943a5-234">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="943a5-235">SIP 池 Cert CN</span><span class="sxs-lookup"><span data-stu-id="943a5-235">SIP Pool Cert CN</span></span> | | |<span data-ttu-id="943a5-236">目錄</span><span class="sxs-lookup"><span data-stu-id="943a5-236">(CONTENTS)</span></span> |
<span data-ttu-id="943a5-237">SIP 池證書 CA</span><span class="sxs-lookup"><span data-stu-id="943a5-237">SIP Pool Cert CA</span></span> | | |<span data-ttu-id="943a5-238">目錄</span><span class="sxs-lookup"><span data-stu-id="943a5-238">(CONTENTS)</span></span> |
<span data-ttu-id="943a5-239">SIP 池信任狀態</span><span class="sxs-lookup"><span data-stu-id="943a5-239">SIP Pool Trust Status</span></span> |<span data-ttu-id="943a5-240">憑證是受信任的。</span><span class="sxs-lookup"><span data-stu-id="943a5-240">Certificate is Trusted.</span></span> |<span data-ttu-id="943a5-241">證書不受信任，請新增根 CA。</span><span class="sxs-lookup"><span data-stu-id="943a5-241">Certificate is not trusted, please add the Root CA.</span></span> |<span data-ttu-id="943a5-242">根據本機憑證存放區驗證憑證，如果裝置信任憑證，則傳回正面。</span><span class="sxs-lookup"><span data-stu-id="943a5-242">Verify the certificate against the local cert store and return a positive if the devices trusts the certificate.</span></span> |
<span data-ttu-id="943a5-243">SIP 池證書根 CA</span><span class="sxs-lookup"><span data-stu-id="943a5-243">SIP Pool Cert Root CA</span></span> | | |<span data-ttu-id="943a5-244">錯誤資訊.</span><span class="sxs-lookup"><span data-stu-id="943a5-244">Information.</span></span> <span data-ttu-id="943a5-245">顯示 SIP 池證書根 CA （如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="943a5-245">Display the SIP Pool Cert Root CA, if available.</span></span> |

#### <span data-ttu-id="943a5-246">信任模型（僅限內部部署混合式）</span><span class="sxs-lookup"><span data-stu-id="943a5-246">Trust Model (on-premises hybrid only)</span></span>

<span data-ttu-id="943a5-247">欄位</span><span class="sxs-lookup"><span data-stu-id="943a5-247">Field</span></span> |<span data-ttu-id="943a5-248">成功</span><span class="sxs-lookup"><span data-stu-id="943a5-248">Success</span></span> |<span data-ttu-id="943a5-249">失敗</span><span class="sxs-lookup"><span data-stu-id="943a5-249">Failure</span></span> |<span data-ttu-id="943a5-250">留言</span><span class="sxs-lookup"><span data-stu-id="943a5-250">Comment</span></span> |<span data-ttu-id="943a5-251">參考</span><span class="sxs-lookup"><span data-stu-id="943a5-251">Reference</span></span>
|------|------|------|------|------|
<span data-ttu-id="943a5-252">信任模型狀態</span><span class="sxs-lookup"><span data-stu-id="943a5-252">Trust Model Status</span></span> |<span data-ttu-id="943a5-253">未偵測到信任模型問題。</span><span class="sxs-lookup"><span data-stu-id="943a5-253">No Trust Model Issue Detected.</span></span> |<span data-ttu-id="943a5-254">SIP 網域和伺服器網域不同，請新增下列網域。</span><span class="sxs-lookup"><span data-stu-id="943a5-254">SIP Domain and server domain are different please add the following domains.</span></span> |<span data-ttu-id="943a5-255">針對信任模型問題，檢查 LD FQDN/LD 伺服器名稱/池伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="943a5-255">Check the LD FQDN/ LD Server Name/ Pool Server name for Trust model issue.</span></span> 
<span data-ttu-id="943a5-256">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="943a5-256">Domain Name(s)</span></span> | | |<span data-ttu-id="943a5-257">傳回應為 SFB 新增的網域清單以進行連線。</span><span class="sxs-lookup"><span data-stu-id="943a5-257">Return the list of domains that should be added for SFB to connect.</span></span> |
