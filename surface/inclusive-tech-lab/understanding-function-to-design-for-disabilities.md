---
title: 瞭解適用于殘障人士設計的函數
description: 來自包容性技術實驗室的 Microsoft 包容性設計參考
ms.localizationpriority: medium
ms.sitesec: library
author: InclusiveTechLab
ms.author: brycejo
ms.topic: article
ms.date: 05/20/2021
manager: krhunter
ms.prod: surface
ms.technology: windows
ms.openlocfilehash: d423fb3e4aa6f87ae0d6686607cd30920ecad5b8
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11577534"
---
# <a name="understanding-function-to-design-for-disabilities"></a><span data-ttu-id="b6b48-103">瞭解適用于殘障人士設計的函數</span><span class="sxs-lookup"><span data-stu-id="b6b48-103">Understanding Function to Design for Disabilities</span></span>
**<span data-ttu-id="b6b48-104">來自包容性技術實驗室的 Microsoft 包容性設計參考</span><span class="sxs-lookup"><span data-stu-id="b6b48-104">A Microsoft Inclusive Design reference from the Inclusive Tech Lab</span></span>**

<span data-ttu-id="b6b48-105">在 Microsoft 的包容性設計練習中，我們相信我們一 &ldquo; 無所有，沒有我們。 &rdquo; 我們設計與殘障人士社群合作，以建立產品與服務，讓殘障人士能夠達成更多目標。</span><span class="sxs-lookup"><span data-stu-id="b6b48-105">In our Inclusive Design practice at Microsoft, we believe in &ldquo;Nothing About Us, Without Us.&rdquo; We design with the disability community to create products and services that empower people with disabilities to achieve more.</span></span> 

<span data-ttu-id="b6b48-106">在我們的練習中，我們已發現，工程師和設計師有時候會難以為與他們合作的人傳達功能層面。</span><span class="sxs-lookup"><span data-stu-id="b6b48-106">In our practice we have observed that engineers and designers sometimes struggle to communicate the aspects of function for the people they are working with.</span></span> <span data-ttu-id="b6b48-107">嘗試瞭解診斷或條件可能會起反作用。</span><span class="sxs-lookup"><span data-stu-id="b6b48-107">Trying to understand diagnosis or conditions can be counter productive.</span></span> <span data-ttu-id="b6b48-108">我們大多數人不是醫療專業人員，因此缺少詞彙;此外，也不一定適合使用醫療術語。</span><span class="sxs-lookup"><span data-stu-id="b6b48-108">Most of us aren’t medical professionals so we lack the vocabulary; also medical terminology isn’t always appropriate.</span></span>

<span data-ttu-id="b6b48-109">我們建立了這個參照，讓工程師和設計師瞭解及討論可能導致互動障礙的功能層面，以及克服這些障礙所需的協助者。</span><span class="sxs-lookup"><span data-stu-id="b6b48-109">We created this reference to provide engineers and designers a way to understand and discuss the aspects of function that can lead to barriers in interaction, and the facilitators needed to overcome these barriers.</span></span> <span data-ttu-id="b6b48-110">我們採用包容性設計作法的目的是要先認識這些障礙，然後再實做。</span><span class="sxs-lookup"><span data-stu-id="b6b48-110">The goal of our inclusive design practice is to recognize the barriers before we implement them.</span></span> <span data-ttu-id="b6b48-111">建立能促進人類多樣性函數的表單。</span><span class="sxs-lookup"><span data-stu-id="b6b48-111">To create forms that facilitate the function of human diversity.</span></span>

<span data-ttu-id="b6b48-112">這項工作的靈感來自世界健康組織的運作、殘障及健康[](https://www.who.int/standards/classifications/international-classification-of-functioning-disability-and-health)國際分類及 ICF (ICF) 。</span><span class="sxs-lookup"><span data-stu-id="b6b48-112">This work was inspired by the World Health Organization’s – [International Classification of Functioning, Disability and Health](https://www.who.int/standards/classifications/international-classification-of-functioning-disability-and-health) (ICF).</span></span> <span data-ttu-id="b6b48-113">我們努力在指南中，讓這份教材更簡潔、簡單且符合我們的技術。</span><span class="sxs-lookup"><span data-stu-id="b6b48-113">We strive in our guide to make this material concise, approachable, and contextual to our field of technology.</span></span> <span data-ttu-id="b6b48-114">這是一份活生生的檔，我們預期會改變並成長。</span><span class="sxs-lookup"><span data-stu-id="b6b48-114">This is a living document that we expect will change and grow.</span></span>

<span data-ttu-id="b6b48-115">若要重申，我們設計與殘障人士社群 - 我們會看到此參照是記錄互動、建立招募篩選和問卷，以及撰寫可用性評論和錯誤等活動的一部分。</span><span class="sxs-lookup"><span data-stu-id="b6b48-115">To reiterate, we design WITH the disability community – we see this reference being part of activities like documenting interactions, creating recruitment screeners and surveys, and writing usability reviews and bugs.</span></span> <span data-ttu-id="b6b48-116">在我們的產品建立過程中，有許多可能的方法可以有效運用此材料。</span><span class="sxs-lookup"><span data-stu-id="b6b48-116">There are many potential ways that this material can be leveraged effectively as part of our product creation process.</span></span>

## <a name="what-this-is"></a><span data-ttu-id="b6b48-117">這是什麼</span><span class="sxs-lookup"><span data-stu-id="b6b48-117">What this is</span></span>

<span data-ttu-id="b6b48-118">這項工作的目標是提供在練習包容性設計時，應考慮的人類差異因素參考。</span><span class="sxs-lookup"><span data-stu-id="b6b48-118">The goal of this work is to provide a reference of human diversity factors to consider when practicing inclusive design.</span></span> <span data-ttu-id="b6b48-119">此架構概述我們每天使用之技術認知、行動能力、視力、聽力、語音和感官需求。</span><span class="sxs-lookup"><span data-stu-id="b6b48-119">This framework outlines the cognitive, mobility, vision, hearing, speech, and sensory demands of the technology we all use daily.</span></span> <span data-ttu-id="b6b48-120">透過可接近的範例，我們嘗試說明當一個人在能力等級與產品設計之間發生不一樣的互動時，可能會面對的阻礙。</span><span class="sxs-lookup"><span data-stu-id="b6b48-120">Through approachable examples, we try to illustrate barriers a person may face when they experience a mismatched interaction between their level of abilities and the design of a product.</span></span>

## <a name="what-this-is-not"></a><span data-ttu-id="b6b48-121">這不是</span><span class="sxs-lookup"><span data-stu-id="b6b48-121">What this is not</span></span>

<span data-ttu-id="b6b48-122">此參照不是建立協助工具解決方案的準則。</span><span class="sxs-lookup"><span data-stu-id="b6b48-122">This reference is not a prescriptive guideline for creating accessibility solutions.</span></span> <span data-ttu-id="b6b48-123">相反地，這是一種您可以用於識別人員可能會遇到的潛在障礙的資源。</span><span class="sxs-lookup"><span data-stu-id="b6b48-123">Rather, it’s a resource you can use to identify potential barriers a person may encounter.</span></span> <span data-ttu-id="b6b48-124">請記得，這份檔不是靜態的，而且會成長。</span><span class="sxs-lookup"><span data-stu-id="b6b48-124">It is important to remember that this document isn’t static and will grow.</span></span> <span data-ttu-id="b6b48-125">雖然我們努力做到全面，但描述的許多實例可能同時發生 (視個別情況) 且可能以不同方式呈現不同的人員。</span><span class="sxs-lookup"><span data-stu-id="b6b48-125">While we strive to be comprehensive, many instances described can occur in conjunction with one another (depending on the individual) and may present differently from one person to another.</span></span>

## <a name="contents-of-this-reference"></a><span data-ttu-id="b6b48-126">此參照的內容</span><span class="sxs-lookup"><span data-stu-id="b6b48-126">Contents of this reference</span></span>

**[<span data-ttu-id="b6b48-127">什麼是認知？</span><span class="sxs-lookup"><span data-stu-id="b6b48-127">What is cognition?</span></span>](cognition.md)** <span data-ttu-id="b6b48-128">-[注意](cognition-attention.md);[記憶體](cognition-memory.md);[判斷](cognition-judgment.md);[處理 (速度) ;](cognition-processing-speed.md)[處理 (理解) ;](cognition-processing-comprehension.md)</span><span class="sxs-lookup"><span data-stu-id="b6b48-128">— [Attention](cognition-attention.md); [Memory](cognition-memory.md); [Judgment](cognition-judgment.md); [Processing (speed)](cognition-processing-speed.md); [Processing (comprehension)](cognition-processing-comprehension.md);</span></span> 

**[<span data-ttu-id="b6b48-129">什麼是行動能力？</span><span class="sxs-lookup"><span data-stu-id="b6b48-129">What is mobility?</span></span>](mobility.md)** <span data-ttu-id="b6b48-130">-[掌握](mobility-grasp.md);[精細的駕駛技巧](mobility-fine-motor-skills.md);[協調;](mobility-coordination.md)[控制 (或不自願) ;](mobility-control.md)[速度](mobility-speed.md);[肌肉色調](mobility-muscle-tone.md);[內達](mobility-endurance.md);[狀態](mobility-posture.md);</span><span class="sxs-lookup"><span data-stu-id="b6b48-130">— [Grasp](mobility-grasp.md); [Fine motor skills](mobility-fine-motor-skills.md); [Coordination](mobility-coordination.md); [Control (voluntary vs. involuntary movement)](mobility-control.md); [Speed](mobility-speed.md); [Muscle tone](mobility-muscle-tone.md); [Endurance](mobility-endurance.md); [Posture](mobility-posture.md);</span></span> 

**[<span data-ttu-id="b6b48-131">什麼是視覺？</span><span class="sxs-lookup"><span data-stu-id="b6b48-131">What is vision?</span></span>](vision.md)** <span data-ttu-id="b6b48-132">-[視 (視或視) ;](vision-blindness-sightlessness.md)[視 (視部分視力) ;](vision-low-vision-partially-sighted.md)[降低視力](vision-decreased-acuity.md);[視覺欄位遺失](vision-visual-field-loss.md);[色盲](vision-color-blindness.md);[Photophobia (光敏感度) ;](vision-photophobia-light-sensitivity.md)</span><span class="sxs-lookup"><span data-stu-id="b6b48-132">— [Blindness (sightlessness)](vision-blindness-sightlessness.md); [Low vision (partially sighted)](vision-low-vision-partially-sighted.md); [Decreased acuity](vision-decreased-acuity.md); [Visual field loss](vision-visual-field-loss.md); [Color blindness](vision-color-blindness.md); [Photophobia (light sensitivity)](vision-photophobia-light-sensitivity.md);</span></span> 

**[<span data-ttu-id="b6b48-133">什麼是聽力？</span><span class="sxs-lookup"><span data-stu-id="b6b48-133">What is hearing?</span></span>](hearing.md)** <span data-ttu-id="b6b48-134">-[聽力損失 (輕微) ;](hearing-mild.md)[聽力損失 (中/重度) ;](hearing-moderate-severe.md)[聽力喪失 (深重) ;](hearing-profound.md)[聽力喪失 (不對稱) ;](hearing-asymmetrical.md)</span><span class="sxs-lookup"><span data-stu-id="b6b48-134">— [Hearing Loss (mild)](hearing-mild.md); [Hearing loss (moderate/severe)](hearing-moderate-severe.md); [Hearing loss (profound)](hearing-profound.md); [Hearing loss (asymmetrical)](hearing-asymmetrical.md);</span></span> 

**[<span data-ttu-id="b6b48-135">什麼是語音、語音和通訊？</span><span class="sxs-lookup"><span data-stu-id="b6b48-135">What is voice, speech, and communication?</span></span>](voice-speech-communication.md)** <span data-ttu-id="b6b48-136">-[失語症 (接受) ;](voice-speech-communication-aphasia-receptive.md)[失語症 (表達) ;](voice-speech-communication-aphasia-expressive.md)[語音品質](voice-speech-communication-speech-quality.md);[社交參與](voice-speech-communication-social-participation.md);[非語言;](voice-speech-communication-non-verbal.md)</span><span class="sxs-lookup"><span data-stu-id="b6b48-136">— [Aphasia (receptive)](voice-speech-communication-aphasia-receptive.md); [Aphasia (expressive)](voice-speech-communication-aphasia-expressive.md); [Speech quality](voice-speech-communication-speech-quality.md); [Social participation](voice-speech-communication-social-participation.md); [Non-verbal](voice-speech-communication-non-verbal.md);</span></span> 

**[<span data-ttu-id="b6b48-137">什麼是感知和感知？</span><span class="sxs-lookup"><span data-stu-id="b6b48-137">What is sensation and perception?</span></span>](sensation-perception.md)** <span data-ttu-id="b6b48-138">- [背書目](sensation-perception-vestibular.md); [長期性痛苦](sensation-perception-chronic-pain.md); [外觀完整性](sensation-perception-skin-integrity.md); [感知 (超敏感和低敏感性 ](sensation-perception-sensation.md)) ; [普裡歐裡卡裡翁](sensation-perception-proprioception.md);</span><span class="sxs-lookup"><span data-stu-id="b6b48-138">— [Vestibular](sensation-perception-vestibular.md); [Chronic pain](sensation-perception-chronic-pain.md); [Skin integrity](sensation-perception-skin-integrity.md); [Sensation (hypersensitive and hyposensitive)](sensation-perception-sensation.md); [Proprioception](sensation-perception-proprioception.md);</span></span> 

## <a name="created-by"></a><span data-ttu-id="b6b48-139">建立者</span><span class="sxs-lookup"><span data-stu-id="b6b48-139">Created by</span></span>

### <a name="authors"></a><span data-ttu-id="b6b48-140">作者</span><span class="sxs-lookup"><span data-stu-id="b6b48-140">Authors</span></span>
<span data-ttu-id="b6b48-141">KaitlynJos， Bryce Johnson， Kris Hunter</span><span class="sxs-lookup"><span data-stu-id="b6b48-141">Kaitlyn Jones, Bryce Johnson, Kris Hunter</span></span>

### <a name="illustrator"></a><span data-ttu-id="b6b48-142">插畫</span><span class="sxs-lookup"><span data-stu-id="b6b48-142">Illustrator</span></span>
<span data-ttu-id="b6b48-143">Lou Patnode</span><span class="sxs-lookup"><span data-stu-id="b6b48-143">Lou Patnode</span></span>

### <a name="editors"></a><span data-ttu-id="b6b48-144">編輯</span><span class="sxs-lookup"><span data-stu-id="b6b48-144">Editors</span></span>
<span data-ttu-id="b6b48-145">Cat Jackson, Martina Dalton, Solomon Romney</span><span class="sxs-lookup"><span data-stu-id="b6b48-145">Cat Jackson, Martina Dalton, Solomon Romney</span></span>

### <a name="special-thanks"></a><span data-ttu-id="b6b48-146">特別感謝</span><span class="sxs-lookup"><span data-stu-id="b6b48-146">Special Thanks</span></span>
<span data-ttu-id="b6b48-147">Panos Panay, Robin Seiler, Allison Flanigan, Aimee Hayes, Steve Godfrey, John Porter, Tiffany Chen, Jenny Lay-Flurrie, Mary Bellard, David Dzumba, David Dame</span><span class="sxs-lookup"><span data-stu-id="b6b48-147">Panos Panay, Robin Seiler, Allison Flanigan, Aimee Hayes, Steve Godfrey, John Porter, Tiffany Chen, Jenny Lay-Flurrie, Mary Bellard, David Dzumba, David Dame</span></span>


[comment]: # (包含頁腳)
