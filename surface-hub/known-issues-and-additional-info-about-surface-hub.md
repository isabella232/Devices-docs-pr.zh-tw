---
title: Microsoft Surface Hub 已知問題及其他相關資訊
description: 概述 Microsoft Surface Hub 的已知問題。
ms.assetid: aee90a0c-fb05-466e-a2b1-92de89d0f2b7
keywords: surface、hub、問題
ms.prod: surface-hub
ms.sitesec: library
author: todmccoy
ms.author: v-todmc
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: ec6746098203b5e91e2aaf3b044d21b81c31c897
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831482"
---
# <span data-ttu-id="53a60-104">Microsoft Surface Hub 已知問題及其他相關資訊</span><span class="sxs-lookup"><span data-stu-id="53a60-104">Known issues and additional information about Microsoft Surface Hub</span></span>

<span data-ttu-id="53a60-105">我們正在聆聽。</span><span class="sxs-lookup"><span data-stu-id="53a60-105">We're listening.</span></span> <span data-ttu-id="53a60-106">[品質] 是頭等大事，我們想要讓您知道有哪些問題會影響客戶。</span><span class="sxs-lookup"><span data-stu-id="53a60-106">Quality is a top priority, and we want to keep you informed about issues impacting customers.</span></span> <span data-ttu-id="53a60-107">下列是 Microsoft Surface Hub 的一些已知問題：</span><span class="sxs-lookup"><span data-stu-id="53a60-107">The following are some known issues of Microsoft Surface Hub:</span></span>

- **<span data-ttu-id="53a60-108">商務用 Skype 沒有與 RS2 使用 proxy 來進行媒體流量</span><span class="sxs-lookup"><span data-stu-id="53a60-108">Skype for Business isn't using proxy for media traffic with RS2</span></span>**
<br/><span data-ttu-id="53a60-109">對於位於 proxy 之後的某些 Surface Hub 使用者，商務用 Skype 不會使用 proxy 伺服器來執行媒體。</span><span class="sxs-lookup"><span data-stu-id="53a60-109">For some Surface Hub users who are behind a proxy, Skype for Business won't use the proxy server for media.</span></span> <span data-ttu-id="53a60-110">不過，Surface Hub 將能夠登入帳戶。</span><span class="sxs-lookup"><span data-stu-id="53a60-110">However, the Surface Hub will be able to sign in to the account.</span></span> <span data-ttu-id="53a60-111">我們收到您的意見反應，而且您在使用 proxy 時會發現媒體流量問題。</span><span class="sxs-lookup"><span data-stu-id="53a60-111">We received your feedback and are aware of the media traffic issue when you are using proxy.</span></span> <span data-ttu-id="53a60-112">我們正在積極調查這個問題，一旦發現並測試解決方案，就會立即發行修正程式。</span><span class="sxs-lookup"><span data-stu-id="53a60-112">We're actively investigating this issue and will release fixes as soon as a solution is identified and tested.</span></span> 

- **<span data-ttu-id="53a60-113">針對 AAD 加入的裝置，當使用者嘗試登入「我的會議 & 檔案」時，Surface Hub 會報告沒有網際網路連線</span><span class="sxs-lookup"><span data-stu-id="53a60-113">For AAD joined devices, when a user tries to sign in to "My meetings & files", Surface Hub reports that there is no Internet connection</span></span>**
<br/><span data-ttu-id="53a60-114">我們已注意到一組影響 Surface Hub 上的登入和檔存取的問題。</span><span class="sxs-lookup"><span data-stu-id="53a60-114">We’re aware of a set of issues that affect sign-in and document access on Surface Hub.</span></span> <span data-ttu-id="53a60-115">我們正在積極調查這些問題。</span><span class="sxs-lookup"><span data-stu-id="53a60-115">We're actively investigating these issues.</span></span> <span data-ttu-id="53a60-116">如有解決方法，客戶可以重設裝置，並將其中樞設定為使用本機管理員帳戶。</span><span class="sxs-lookup"><span data-stu-id="53a60-116">As a workaround until a resolution is released, customers can reset their devices and set up their Hub to use a local admin account.</span></span> <span data-ttu-id="53a60-117">重新配置為使用本機管理員帳戶之後，「我的會議與檔案」就會如期運作。</span><span class="sxs-lookup"><span data-stu-id="53a60-117">After reconfiguring to use the local admin account, "My meetings and files" will work as expected.</span></span>
- **<span data-ttu-id="53a60-118">Azure AD 加入時的單一登入</span><span class="sxs-lookup"><span data-stu-id="53a60-118">Single sign-in when Azure AD joined</span></span>**
<br/><span data-ttu-id="53a60-119">Surface Hub 是專為公用空格設計的，會影響使用者認證的儲存方式。</span><span class="sxs-lookup"><span data-stu-id="53a60-119">Surface Hub was designed for communal spaces, which impacts the way user credentials are stored.</span></span> <span data-ttu-id="53a60-120">因此，目前在裝置加入 Azure AD 時，單一登入的運作方式目前有一些限制。</span><span class="sxs-lookup"><span data-stu-id="53a60-120">Because of this, there are currently limitations in how single sign-in works when devices are Azure AD joined.</span></span> <span data-ttu-id="53a60-121">Microsoft 已注意到這項限制，且正在積極調查解析度的選項。</span><span class="sxs-lookup"><span data-stu-id="53a60-121">Microsoft is aware of this limitation and is actively investigating options for a resolution.</span></span>
- **<span data-ttu-id="53a60-122">如果 Surface Hub 在易記名稱中有點字元（.），則可在基礎結構投影上使用 Miracast</span><span class="sxs-lookup"><span data-stu-id="53a60-122">Miracast over Infrastructure projection to Surface Hub fails if the Surface Hub has a dot character (.) in the friendly name</span></span>**
<br/><span data-ttu-id="53a60-123">如果易記的名稱在名稱（.）中包含句號或點（例如，"Room42"），Surface Hub 使用者可能會遇到投影裝置的問題。</span><span class="sxs-lookup"><span data-stu-id="53a60-123">Surface Hub users may experience issues projecting to their device if the Friendly Name includes a period or dot in the name (.) -- for example, "Conf.Room42".</span></span> <span data-ttu-id="53a60-124">若要解決此問題，請在 [**設定**Surface Hub] 中變更中樞的易記名稱  >  **Surface Hub**  >  \*\* \*\*，然後重新開機裝置。</span><span class="sxs-lookup"><span data-stu-id="53a60-124">To work around the issue, change the Friendly Name of the Hub in **Settings** > **Surface Hub** > **About**, and then restart the device.</span></span> <span data-ttu-id="53a60-125">Microsoft 正在努力解決這個問題。</span><span class="sxs-lookup"><span data-stu-id="53a60-125">Microsoft is working on a solution to this issue.</span></span>