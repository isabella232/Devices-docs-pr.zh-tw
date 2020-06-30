---
title: 變更 Microsoft Surface Hub 裝置帳戶
description: 您可以在 &#91;設定&#93; 中變更裝置帳戶，如果尚未佈建任何帳戶，即可新增一個，或是變更已經佈建之帳戶的任何屬性。
ms.assetid: AFC43043-3319-44BC-9310-29B1F375E672
ms.reviewer: ''
manager: laurawi
keywords: 變更裝置帳戶, 變更屬性, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: b90ef3e208f1e76e4b02fb9f49e3e24030947bc7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832102"
---
# 變更 Microsoft Surface Hub 裝置帳戶


您可以在 &#91;設定&#93; 中變更裝置帳戶，如果尚未佈建任何帳戶，即可新增一個，或是變更已經佈建之帳戶的任何屬性。

## 詳細資訊


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">值</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用者主體名稱</p></td>
<td align="left"><p>裝置帳戶的使用者主體名稱 (UPN)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>密碼</p></td>
<td align="left"><p>裝置帳戶的對應密碼。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>網域</p></td>
<td align="left"><p>裝置帳戶所屬的網域。 您不需要針對 Office 365 帳戶提供這個欄位。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用者名稱</p></td>
<td align="left"><p>裝置帳戶的使用者名稱。 您不需要針對 Office 365 帳戶提供這個欄位。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>工作階段初始通訊協定 (SIP) 位址</p></td>
<td align="left"><p>裝置帳戶的 SIP 位址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Exchange Server</p></td>
<td align="left"><p>此為裝置帳戶的 Exchange Server。 裝置帳戶的使用者名稱與密碼必須能夠驗證特定的 Exchange Server。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>啟用 Exchange 服務</p></td>
<td align="left"><p>有選取時，將啟用所有的 Exchange 服務 (例如，歡迎畫面上的行事曆，以電子郵件傳送白板)。 未選取時，將停用所有的 Exchange 服務，而且不需要提供 Exchange Server。</p></td>
</tr>
</tbody>
</table>

 

## 發生什麼事？


UPN 與密碼是用來驗證 AD 或 Azure AD 中的帳戶。 如果驗證失敗，您可能需要提供網域和使用者名稱。

我們將嘗試使用提供的認證來探索 SIP 位址。 如果找不到 SIP 位址，則商務用 Skype 將使用 UPN 做為 SIP 位址。 如果這不是帳戶的 SIP 位址，您將需要提供 SIP 位址。

如果裝置找不到與登入認證相關聯的伺服器，就需要提供 Exchange 伺服器位址。 Microsoft Surface Hub 將使用 Exchange Server 來與 ActiveSync 通訊，其會在裝置上啟用數個重要功能。

## 相關主題


[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)

 

 





