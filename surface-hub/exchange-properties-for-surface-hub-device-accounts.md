---
title: Microsoft Exchange 屬性 (Surface Hub)
description: 裝置帳戶的部分 Microsoft Exchange 屬性必須設定為特定值，才能在 Microsoft Surface Hub 上取得最佳的會議體驗。
ms.assetid: 3E84393B-C425-45BF-95A6-D6502BA1BF29
ms.reviewer: ''
manager: laurawi
keywords: Microsoft Exchange 屬性, 裝置帳戶, Surface Hub, Windows PowerShell Cmdlet
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
ms.openlocfilehash: 8879762857146011f3e1a198b72a895bc6bf9473
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831846"
---
# <span data-ttu-id="aca91-104">Microsoft Exchange 屬性 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="aca91-104">Microsoft Exchange properties (Surface Hub)</span></span>


<span data-ttu-id="aca91-105">裝置帳戶的部分 Microsoft Exchange 屬性必須設定為特定值，才能在 Microsoft Surface Hub 上取得最佳的會議體驗。</span><span class="sxs-lookup"><span data-stu-id="aca91-105">Some Microsoft Exchange properties of the device account must be set to particular values to have the best meeting experience on Microsoft Surface Hub.</span></span> <span data-ttu-id="aca91-106">下表會根據 PowerShell Cmdlet 參數、其用途，以及應將它們設為哪些值，來列出各種 Exchange 屬性。</span><span class="sxs-lookup"><span data-stu-id="aca91-106">The following table lists various Exchange properties based on PowerShell cmdlet parameters, their purpose, and the values they should be set to.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aca91-107">屬性</span><span class="sxs-lookup"><span data-stu-id="aca91-107">Property</span></span></th>
<th align="left"><span data-ttu-id="aca91-108">描述</span><span class="sxs-lookup"><span data-stu-id="aca91-108">Description</span></span></th>
<th align="left"><span data-ttu-id="aca91-109">值</span><span class="sxs-lookup"><span data-stu-id="aca91-109">Value</span></span></th>
<th align="left"><span data-ttu-id="aca91-110">影響</span><span class="sxs-lookup"><span data-stu-id="aca91-110">Impact</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aca91-111">AutomateProcessing</span><span class="sxs-lookup"><span data-stu-id="aca91-111">AutomateProcessing</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-112">AutomateProcessing 參數會啟用或停用在信箱上處理行事曆的功能。</span><span class="sxs-lookup"><span data-stu-id="aca91-112">The AutomateProcessing parameter enables or disables calendar processing on the mailbox.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-113">AutoAccept</span><span class="sxs-lookup"><span data-stu-id="aca91-113">AutoAccept</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-114">Surface Hub 將能夠根據其可用性自動接受或拒絕會議邀請。</span><span class="sxs-lookup"><span data-stu-id="aca91-114">The Surface Hub will be able to automatically accept or decline meeting requests based on its availability.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aca91-115">AddOrganizerToSubject</span><span class="sxs-lookup"><span data-stu-id="aca91-115">AddOrganizerToSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-116">AddOrganizerToSubject 參數會指定是否要使用會議召集人的名稱來做為會議邀請的主旨。</span><span class="sxs-lookup"><span data-stu-id="aca91-116">The AddOrganizerToSubject parameter specifies whether the meeting organizer's name is used as the subject of the meeting request.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-117">$False</span><span class="sxs-lookup"><span data-stu-id="aca91-117">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-118">歡迎畫面將不會顯示會議召集人兩次 (而不會將它顯示為召集人以及顯示於會議主旨中)。</span><span class="sxs-lookup"><span data-stu-id="aca91-118">The welcome screen will not show the meeting organizer twice (instead of showing it as both the organizer and in the meeting subject).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aca91-119">AllowConflicts</span><span class="sxs-lookup"><span data-stu-id="aca91-119">AllowConflicts</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-120">AllowConflicts 參數會指定是否允許衝突的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="aca91-120">The AllowConflicts parameter specifies whether to allow conflicting meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-121">$False</span><span class="sxs-lookup"><span data-stu-id="aca91-121">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-122">Surface Hub 將拒絕與另一個會議時間發生衝突的會議邀請。</span><span class="sxs-lookup"><span data-stu-id="aca91-122">The Surface Hub will decline meeting requests that conflict with another meeting’s time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aca91-123">DeleteComments</span><span class="sxs-lookup"><span data-stu-id="aca91-123">DeleteComments</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-124">DeleteComments 參數會指定是否要移除或保留傳入的會議邀請訊息內文中的任何文字。</span><span class="sxs-lookup"><span data-stu-id="aca91-124">The DeleteComments parameter specifies whether to remove or keep any text in the message body of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-125">$False</span><span class="sxs-lookup"><span data-stu-id="aca91-125">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-126">如果您在會議期間需要會議的訊息內文，即可保留並從 Surface Hub 中擷取它。</span><span class="sxs-lookup"><span data-stu-id="aca91-126">The message body of meetings can be retained and retrieved from a Surface Hub if you need it during a meeting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aca91-127">DeleteSubject</span><span class="sxs-lookup"><span data-stu-id="aca91-127">DeleteSubject</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-128">DeleteSubject 參數會指定是否要移除或保留傳入的會議邀請的主旨。</span><span class="sxs-lookup"><span data-stu-id="aca91-128">The DeleteSubject parameter specifies whether to remove or keep the subject of incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-129">$False</span><span class="sxs-lookup"><span data-stu-id="aca91-129">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-130">會議邀請主旨可顯示於 Surface Hub 上。</span><span class="sxs-lookup"><span data-stu-id="aca91-130">Meeting request subjects can be shown on the Surface Hub.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aca91-131">RemovePrivateProperty</span><span class="sxs-lookup"><span data-stu-id="aca91-131">RemovePrivateProperty</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-132">RemovePrivateProperty 參數會指定是否要清除傳入的會議邀請的私人標幟。</span><span class="sxs-lookup"><span data-stu-id="aca91-132">The RemovePrivateProperty parameter specifies whether to clear the private flag for incoming meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-133">$False</span><span class="sxs-lookup"><span data-stu-id="aca91-133">$False</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-134">私人會議主旨會在歡迎畫面上顯示為 [私人]。</span><span class="sxs-lookup"><span data-stu-id="aca91-134">Private meeting subjects will show as Private on the welcome screen.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aca91-135">AddAdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="aca91-135">AddAdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-136">AddAdditionalResponse 參數會指定在回應會議邀請時，是否要傳送來自資源信箱的的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="aca91-136">The AddAdditionalResponse parameter specifies whether additional information will be sent from the resource mailbox when responding to meeting requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-137">$True</span><span class="sxs-lookup"><span data-stu-id="aca91-137">$True</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-138">將回應傳送到會議邀請時，將在回應中提供自訂文字。</span><span class="sxs-lookup"><span data-stu-id="aca91-138">When a response is sent to a meeting request, custom text will be provided in the response.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aca91-139">AdditionalResponse</span><span class="sxs-lookup"><span data-stu-id="aca91-139">AdditionalResponse</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-140">AdditionalResponse 參數會指定要在會議邀請的回應中包含的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="aca91-140">The AdditionalResponse parameter specifies the additional information to be included in responses to meeting requests.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="aca91-141">備註 </strong> 除非 [AddAdditionalResponse] 設定為 [$True]，否則不會傳送此文字。</span><span class="sxs-lookup"><span data-stu-id="aca91-141">Note</strong>This text will not be sent unless AddAdditionalResponse is set to $True.</span></span>
</div>
<div>
 
</div></td>
<td align="left"><p><span data-ttu-id="aca91-142">您可以選擇使用其他回應，來通知使用者如何使用 Surface Hub 或將它們指向資源。</span><span class="sxs-lookup"><span data-stu-id="aca91-142">Your choice—the additional response can be used to inform people how to use a Surface Hub or point them towards resources.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aca91-143">新增其他回應訊息，可以為使用者提供其如何在會議中使用 Surface Hub 的簡介。</span><span class="sxs-lookup"><span data-stu-id="aca91-143">Adding an additional response message can provide people an introduction to how they can use a Surface Hub in their meeting.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





