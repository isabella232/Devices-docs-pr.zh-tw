---
title: 監視您的 Microsoft Surface Hub
description: 監視 Microsoft Surface Hub 裝置是透過 Microsoft Operations Management Suite (OMS) 來啟用。
ms.assetid: 1D2ED317-DFD9-423D-B525-B16C2B9D6942
ms.reviewer: ''
manager: laurawi
keywords: 監視 Surface Hub, Microsoft Operations Management Suite, OMS
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 108f24036a0e02295cf2a5588bb6b51e517eba8d
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831817"
---
# 監視您的 Microsoft Surface Hub

對 Microsoft Surface Hub 裝置的監視是透過 Microsoft Operations Management Suite (OMS) 來啟用。 [Operations Management Suite](https://go.microsoft.com/fwlink/?LinkId=718138) 是 Microsoft 的 IT 管理解決方案，可協助您管理和保護您的整個 IT 基礎結構 (包括 Surface Hub)。


Surface Hub 在 OMS 中是以 Log Analytics 方案提供，讓您能夠收集並檢視您所有 Surface Hub 的使用狀況和可靠性資料。 Surface Hub 方案可用於：
- 清查 Surface Hub。
- 檢視 Skype 會議、有線和無線投影及 Surface Hub 上應用程式的使用狀況和可靠性資料的快照。
- 建立自訂警示，以便在 Surface Hub 報告軟體或硬體問題時快速回應。

## 將 Surface Hub 新增到 Operations Management Suite

1. **登入 Operations Management Suite (OMS)**。 您可以使用 Microsoft 帳戶或是公司或學校帳戶來建立工作區。 如果您的公司已經使用 Azure Active Directory (Azure AD)，在登入 OMS 的時候請使用公司或學校帳戶。 使用公司或學校帳戶可讓您使用來自 Azure AD 的身分管理 OMS 中的權限。
2. **建立新的 OMS 工作區**。 輸入工作區的名稱，選取工作區區域，然後提供您想要與此工作區相關聯的電子郵件地址。 選取 **\[建立\]**。
3. **將 Azure 訂用帳戶連結到工作區**。 如果您的組織已經有 Azure 訂用帳戶，您可以將它連結到您的工作區。 請注意，您可能需要向組織的 Azure 系統管理員要求存取權。

    > [!NOTE] 
    > 如果您的組織沒有 Azure 訂用帳戶，請建立一個新的，或從清單中選取預設的 OMS Azure 訂用帳戶。 您的工作區就會開啟。

4. **新增 Surface Hub 方案**。 在「方案庫」中，選取 **\[Surface Hub\]** 磚，然後選取方案詳細資料頁面上的 **\[新增\]**。 方案現已顯示在您的工作區。

## 使用 Surface Hub 儀表板
從 OMS 工作區中的 **\[概觀\]** 頁面，按一下 Surface Hub 磚來查看 Surface Hub 儀表板。 使用儀表板取得您的所有 Surface Hub 的使用狀況和可靠性資料。 按一下儀表板上的各檢視來查看詳細資料，視需要修改查詢並建立警示。

> [!NOTE]
> 這些檢視大部分會顯示過去 30 天的資料，但這是由訂用帳戶的資料保留原則決定。

**使用中的 Surface Hub**

使用這個檢視來取得所有您的 Surface Hub 的詳細目錄。 一旦連線到 OMS，每部 Surface Hub 都會定期傳送「活動訊號」事件到伺服器。 這個檢視會顯示在過去 24 小時曾經回報活動訊號的 Surface Hub。

<!--
**Skype meetings**

Use this view to get usage data for Skype over the past 30 days. The graph shows the total number of Skype Meetings started across your Surface Hubs, and a breakdown between scheduled meetings, ad hoc meetings, and PSTN calls.
-->
 
**無線投影**

使用這個檢視來取得過去 30 天無線投影的使用狀況和可靠性資料。 該圖表會顯示您所有 Surface Hub 上的無線連線總數，可做為組織中的人員是否使用此功能的指標。 如果數目低，可能表示需要提供訓練，以協助組織中的人員了解如何以無線的方式連線到 Surface Hub。
 
此外，圖表也會顯示連線成功及失敗的詳細資料。 如果您發現失敗的數目高，裝置可能未適當支援使用 Miracast 進行無線投影。 為獲得最佳效能，Microsoft 建議裝置執行 WDI Wi-Fi 驅動程式和 WDDM 2.0 圖形驅動程式。 使用詳細資料來檢視無線投影問題是否常發生在特定裝置。
 
如果使用者是使用 Windows 膝上型電腦或手機，當連線失敗時他們也可以執行以下步驟：
- 從 **\[設定\]** > **\[裝置\]** > **\[連線的裝置\]** 移除已配對的裝置，然後再嘗試連線一次。
- 將裝置重新開機。
 
**有線投影**

使用這個檢視來取得過去 30 天有線投影的使用狀況和可靠性資料。 如果圖表顯示大量連線失敗數目，可能表示視聽線路連接有問題。 例如，如果使用 HDMI 中繼器或會議室中控台，則可能需要將它們重新啟動。
 
**應用程式使用狀況**

使用此檢視來取得過去 30 天 Surface Hub 上應用程式的使用狀況資料。 該資料來自在 Surface Hub 上啟動的應用程式，但不包括「商務用 Skype」。 這個檢視可協助您了解哪個 Surface Hub應用程式在組織中最有價值。 如果您正在環境中部署新的企業營運應用程式，這也能幫助您了解它們被使用的頻率。
 
**應用程式當機**

使用此檢視來取得過去 30 天 Surface Hub 上應用程式的可靠性資料。 該資料來自 Surface Hub 上發生當機的應用程式。 這個檢視可協助您偵測執行不順的內建和企業營運應用程式並通知應用程式開發人員。
 
**範例查詢**

使用此範例根據一組建議的查詢來建立自訂的警示。 警示能協助您在 Surface Hub 報告軟體或硬體問題時快速回應。 如需詳細資訊，請參閱[使用範例查詢設定警示](#set-up-alerts-with-sample-queries)。

## 使用範例查詢設定警示

使用警示可在 Surface Hub 報告軟體或硬體問題時快速回應。 警示規則會根據排程自動執行記錄搜尋，如果結果符合特定條件就會執行一或多個動作。 如需詳細資訊，請參閱 [Log Analytics 中的警示](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/)。
 
Surface Hub Log Analytics 方案隨附一組範例查詢，可協助您設定適當的警示，並了解如何解決可能遇到的問題。 將它們當作起始點，規劃您的監視和支援策略。

下表描述 Surface Hub 方案中的範例查詢：

| 警示類型 | 影響 | 建議的補救措施 | 詳細資料 |
| ---------- | ------ | ----------------------- | ------- |
| 軟體   | 錯誤  | **將裝置重新開機**。 <br> 手動重新開機，或使用 [Reboot 設定服務提供者](https://msdn.microsoft.com/library/windows/hardware/mt720802(v=vs.85).aspx)。 <br> 建議在會議以外的時間執行，以減少對組織內人員的影響。 | 觸發條件： <br> - Surface Hub 作業系統中的重要處理程序，例如殼層、投影或 Skype 發生當機或變成沒有回應。 <br> - 裝置在過去 24 小時內未曾回報活動訊號。 這可能是因為網路連線問題或網路相關硬體故障所造成，或者是診斷資料報告系統發生錯誤。 |
| 軟體   | 錯誤  | **檢查 Exchange 服務**。 <br> 確認： <br> - 服務可供使用。 <br> - 裝置帳戶密碼是最新狀態 (如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md))。| 會在使用 Exchange 同步處理裝置行事曆發生錯誤時觸發。 |
| 軟體   | 錯誤  | **檢查商務用 Skype 服務**。 <br> 確認： <br> - 服務可供使用。 <br> - 裝置帳戶密碼是最新狀態 (如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md))。 <br> - 已適當設定商務用 Skype 的網域名稱 (請參閱[設定網域名稱](use-fully-qualified-domain-name-surface-hub.md))。 | 會在登入 Skype 失敗時觸發。 |
| 軟體   | 錯誤  | **重設裝置**。 <br> 這需要一些時間，因此應讓裝置離線。 <br> 如需詳細資訊，請參閱[裝置重設](device-reset-surface-hub.md)。| 會在結束工作階段清理使用者和應用程式資料發生錯誤時觸發。 當這個作業重複地失敗時，裝置將會鎖定以保護使用者資料。 您必須重設裝置才能繼續。 |
| 硬體   | 警告 | **無**。 指出對功能的影響可忽略不計。| 會在下列任何硬體元件發生問題時觸發： <br> - 虛擬手寫筆插槽 <br> - NFC 驅動程式 <br> - USB 集線器驅動程式 <br> - 藍牙驅動程式 <br> - 近接感測器 <br> - 圖形效能 (視訊卡驅動程式) <br> - 不相符的硬碟 <br> - 未偵測到鍵盤/滑鼠 |
| 硬體   | 錯誤 | **連絡 Microsoft 支援服務**。 <br> 指出核心功能受到影響 (如 Skype、投影、觸控及網路連線)。 <br> **注意** 某些事件 (包括活動訊號) 會包含裝置的序號，您在連絡支援服務的時候會用到它。| 會在下列任何硬體元件發生問題時觸發。 <br> **影響 Skype 的元件**： <br> - 喇叭驅動程式 <br> - 麥克風驅動程式 <br> - 相機驅動程式 <br> **影響有線和無線投影的元件**： <br> - 有線 Touchback 驅動程式 <br> - 有線內嵌驅動程式 <br> - 無線介面卡驅動程式 <br> - Wi-Fi Direct 錯誤 <br> **其他元件**： <br> - 觸控數位板驅動程式 <br> - 網路介面卡錯誤 (沒有對 OMS 回報)|

**設定警示**
1. 從 Surface Hub 方案選取其中一個範例查詢。
2. 視需要修改查詢。 若要深入了解，請參閱 Log Analytics 搜尋參考資料。
3. 按一下頁面頂端的 **\[警示\]** 以開啟 **\[新增警示規則\]** 畫面。 如需設定警示之選項的詳細資料，請參閱 [Log Analytics 中的警示](https://azure.microsoft.com/documentation/articles/log-analytics-alerts/)。
4. 按一下 **\[儲存\]** 以完成警示規則。 它會立即開始執行。

## 註冊 Surface Hub

若要讓 Surface Hub 連線到 OMS 服務並向服務註冊，它必須能存取您網域的連接埠號碼和 URL。 下表列出 OMS 所需的連接埠。 如需詳細資訊，請參閱[設定 Log Analytics 中的 Proxy 和防火牆設定](https://azure.microsoft.com/documentation/articles/log-analytics-proxy-firewall/)。

>[!NOTE]
>Surface Hub 目前不支援 proxy 伺服器與 OMS 服務的通訊。

| 代理程式資源              | 連接埠 | 是否略過 HTTPS 檢查？ |
| --------------------------- | ----- | ------------------------ |
| *.ods.opinsights.azure.com  | 443   | 是 |
| *.oms.opinsights.azure.com  | 443   | 是 |
| *.blob.core.windows.net     | 443   | 是 |
| ods.systemcenteradvisor.com | 443   | 否  |

Microsoft Monitoring Agent 是用來將裝置連線到 OMS，它已經與 Surface Hub 作業系統整合，因此不需要安裝其他用戶端來將 Surface Hub 連線到 OMS。
 
一旦設定好 OMS 工作區，就有幾種方法可以註冊您的 Surface Hub 裝置：
- [「設定」應用程式](#enroll-using-the-settings-app)
- [佈建套件](#enroll-using-a-provisioning-package)
- [MDM 提供者](#enroll-using-a-mdm-provider)，例如 Microsoft Intune 和 Configuration Manager
 
您將需要 OMS 工作區的工作區識別碼和主索引鍵。 您可以從 OMS 入口網站取得這些資訊。
 
### 使用「設定」應用程式註冊

**使用「設定」應用程式註冊**

1. 從您的 Surface Hub 啟動 **\[設定\]**。
2. 出現提示時，請輸入裝置系統管理員認證。
3. 選取 **\[此裝置\]**，然後瀏覽到 **\[裝置管理\]**。
4. 在 **\[監視\]** 下，選取 **\[設定 OMS 設定\]**。
5. 在 \[OMS 設定\] 對話方塊中，選取 **\[啟用監視\]**。
6. 輸入 OMS 工作區的工作區識別碼和主索引鍵。 您可以從 OMS 入口網站取得這些資訊。
7. 按一下 **\[確定\]** 以完成設定。
 
隨即會出現一個確認對話方塊，告知您 OMS 設定是否已順利套用至裝置。 如果是，裝置就會開始將資料傳送至 OMS。

### 使用佈建套件註冊
您可以使用佈建套件來註冊 Surface Hub。 如需詳細資訊，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。
 
### 使用 MDM 提供者註冊
您可以使用 SurfaceHub CSP 將 Surface Hub 註冊到 OMS。 Intune 和 Configuration Manager 提供內建體驗，可協助您建立 Surface Hub 的原則範本。 如需詳細資訊，請參閱[使用 MDM 提供者管理 Surface Hub 設定](manage-settings-with-mdm-for-surface-hub.md)。

## 相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)

 

 





