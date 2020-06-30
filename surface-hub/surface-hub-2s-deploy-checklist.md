---
title: Surface Hub 秒部署檢查清單
description: 使用預先部署和後期部署檢查清單來驗證 Surface Hub 的配置。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 3c30892a3ae4f534006aa32ad6d969b42a52cbf2
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831910"
---
# Surface Hub 秒部署檢查清單

## Surface Hub 2 預部署檢查清單

|**項目**|**回應**|
|:------ |:------ |
|**裝置帳戶名稱**| |
|**裝置帳戶 UPN**| |
|**ActiveSync 原則**| |
|**已完成行事曆處理設定**| ☐ [是] <br>  ☐否 |
|**裝置易記名稱**| |
|**裝置主機名稱**| |
|**從屬**| ☐無 <br> ☐ Active Directory 隸屬關係 <br> ☐ Azure Active Directory |
|**Microsoft 團隊模式**| ☐模式0 <br> ☐模式1 <br> ☐模式2 |
|**裝置管理**| ☐是，Microsoft Intune <br> ☐是的，其他行動裝置管理員 [MDM] <br> ☐無 |  
|**Proxy**| ☐自動設定 <br> ☐ Proxy 伺服器 <br> ☐ Proxy 自動 config （PAC）檔案 |
|**Proxy 驗證**| ☐裝置帳號憑證 <br> ☐提示輸入認證 |
|**密碼循環使用**| ☐ <br> ☐關閉 |
|**商務用 Skype 其他網功能變數名稱稱（僅限內部部署）**| |
|**會話超時時間**| |
|**會話超時動作**| ☐結束會話 <br> ☐允許繼續 |
|**我的會議與檔案**| ☐啟用 <br> ☐停用 |
|**鎖定畫面超時**| |
|**睡眠空閒超時**| |
|**藍牙**| ☐ <br> ☐關閉 |
|**僅使用 BitLocker USB 磁片磁碟機**| ☐ <br> ☐關閉 |
|**安裝額外的憑證（僅限內部部署）**| |
|**Windows Update**| ☐商務用 Windows Update <br> ☐ Windows Server Update Services [WSUS] |
|**Surface app 喇叭設定**| ☐滾動支架 <br> ☐牆-已掛載 |
|**IP 位址**| ☐有線-DHCP <br> ☐有線-DHCP 保留 <br> ☐無線-DHCP <br> ☐無線-DHCP 保留 |

## [Surface Hub 2] 部署之後的檢查清單

|**檢查**|**回應**|
|:------|:---------|
|**裝置帳戶同步處理**| ☐ [是] <br> ☐否 |
|**Bitlocker 金鑰**| ☐儲存至檔案（無隸屬關係） <br> ☐儲存在 Active Directory （廣告隸屬關係）中 <br>已儲存在 Azure AD 中的☐（Azure AD 從屬關係） |
|**裝置 OS 更新**| ☐已完成 |
|**Windows 網上商店更新**| ☐自動 <br> ☐手動 |
|**Microsoft 團隊排程會議**| 收到☐確認電子郵件 <br> [開始] 畫面上顯示☐會議 <br>  ☐單觸連接函數 <br> ☐能夠加入音訊 <br> ☐能夠加入影片 <br> ☐能共用畫面 ||
|**商務用 Skype 排程會議**| 收到☐確認電子郵件 <br> [開始] 畫面上顯示☐會議 <br> 正確☐單觸連接函數 <br> ☐能夠加入音訊 <br> ☐能夠加入影片 <br> ☐能共用畫面 <br> ☐能夠傳送/接收 IM |
|**已邀請的已排程會議**| 拒絕☐會議 |
|**Microsoft 團隊零星會議**| ☐邀請其他使用者使用 <br> ☐能夠加入音訊 <br> ☐能夠加入影片 <br> ☐能共用畫面 |
|**商務用 Skype 排程會議**| ☐邀請其他使用者使用 <br> ☐能夠加入音訊 <br> ☐能夠加入影片 <br> ☐能共用畫面 <br> ☐能夠傳送/接收 IM |
|**Microsoft Whiteboard**| 從歡迎/開始畫面☐啟動 <br> 從 Microsoft 團隊開始☐啟動 | 
|**來電的 Skype/小組通話**| ☐能夠加入音訊<br>☐能夠加入影片 <br> ☐能共用畫面 <br> ☐能夠傳送/接收 IM （僅適用于商務用 Skype） |
|**傳入的即時影片串流**| ☐最大2（商務用 Skype） <br> ☐最多4個（Microsoft 團隊） |
|**Microsoft 團隊模式0行為**| [歡迎/開始] 畫面上的 [商務用 Skype] 磚☐ <br> ☐可以加入已排程的商務用 Skype 會議（Skype UI） <br> ☐可以加入排程的小組會議（團隊 UI） |
|**Microsoft 團隊模式1行為**| [歡迎/開始] 畫面上的 [☐團隊] 磚 <br> ☐可以加入已排程的商務用 Skype 會議（Skype UI） <br> ☐可以加入排程的小組會議（團隊 UI） |
|**Microsoft 團隊模式2行為**| [歡迎/開始] 畫面上的 [☐團隊] 磚 <br> ☐可以加入排程的小組會議 <br> ☐無法加入商務用 Skype 會議 |
