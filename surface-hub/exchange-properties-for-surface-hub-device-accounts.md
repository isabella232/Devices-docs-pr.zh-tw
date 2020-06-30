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
# Microsoft Exchange 屬性 (Surface Hub)


裝置帳戶的部分 Microsoft Exchange 屬性必須設定為特定值，才能在 Microsoft Surface Hub 上取得最佳的會議體驗。 下表會根據 PowerShell Cmdlet 參數、其用途，以及應將它們設為哪些值，來列出各種 Exchange 屬性。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">描述</th>
<th align="left">值</th>
<th align="left">影響</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AutomateProcessing</p></td>
<td align="left"><p>AutomateProcessing 參數會啟用或停用在信箱上處理行事曆的功能。</p></td>
<td align="left"><p>AutoAccept</p></td>
<td align="left"><p>Surface Hub 將能夠根據其可用性自動接受或拒絕會議邀請。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AddOrganizerToSubject</p></td>
<td align="left"><p>AddOrganizerToSubject 參數會指定是否要使用會議召集人的名稱來做為會議邀請的主旨。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>歡迎畫面將不會顯示會議召集人兩次 (而不會將它顯示為召集人以及顯示於會議主旨中)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowConflicts</p></td>
<td align="left"><p>AllowConflicts 參數會指定是否允許衝突的會議邀請。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>Surface Hub 將拒絕與另一個會議時間發生衝突的會議邀請。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteComments</p></td>
<td align="left"><p>DeleteComments 參數會指定是否要移除或保留傳入的會議邀請訊息內文中的任何文字。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>如果您在會議期間需要會議的訊息內文，即可保留並從 Surface Hub 中擷取它。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeleteSubject</p></td>
<td align="left"><p>DeleteSubject 參數會指定是否要移除或保留傳入的會議邀請的主旨。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>會議邀請主旨可顯示於 Surface Hub 上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePrivateProperty</p></td>
<td align="left"><p>RemovePrivateProperty 參數會指定是否要清除傳入的會議邀請的私人標幟。</p></td>
<td align="left"><p>$False</p></td>
<td align="left"><p>私人會議主旨會在歡迎畫面上顯示為 [私人]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AddAdditionalResponse</p></td>
<td align="left"><p>AddAdditionalResponse 參數會指定在回應會議邀請時，是否要傳送來自資源信箱的的其他資訊。</p></td>
<td align="left"><p>$True</p></td>
<td align="left"><p>將回應傳送到會議邀請時，將在回應中提供自訂文字。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AdditionalResponse</p></td>
<td align="left"><p>AdditionalResponse 參數會指定要在會議邀請的回應中包含的其他資訊。</p>
<div class="alert">
<strong>備註 </strong> 除非 [AddAdditionalResponse] 設定為 [$True]，否則不會傳送此文字。
</div>
<div>
 
</div></td>
<td align="left"><p>您可以選擇使用其他回應，來通知使用者如何使用 Surface Hub 或將它們指向資源。</p></td>
<td align="left"><p>新增其他回應訊息，可以為使用者提供其如何在會議中使用 Surface Hub 的簡介。</p></td>
</tr>
</tbody>
</table>

 

 

 





