---
title: 已知問題：Surface Hub
description: 此頁面提供 Surface Hub 的已知問題清單
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/09/2021
ms.localizationpriority: Medium
ms.openlocfilehash: a9435db1de48b33d062d5e79d0d622f1d17815f0
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497483"
---
# <a name="known-issues-surface-hub"></a>已知問題：Surface Hub

本文列出執行目前作業系統的 Surface Hub 已知問題，Windows 10 團隊版 2020 Update。

若要確保Surface Hub收到最新的更新，請使用系統管理員帳戶登入，然後選取 [**所有應用程式**  >  **設定**  >  **更新和安全**  >  **性Windows Update**，然後安裝所有更新。

| 問題               | 描述           | 解決方式                 |
|---------------------|-----------------------|------------------------|
| 在Surface Hub裝置上使用 Whiteboard 應用程式時，無法透過電子郵件共用內容。 | 「Easy Share」 功能已從新版的 Whiteboard 應用程式中移除。 | 儲存 Whiteboard 內容的建議方式是登入應用程式。 如果無法登入，映射檔案可以儲存至本機儲存體，然後透過 Edge 瀏覽器透過使用者慣用的服務共用。 「簡單共用」功能會在未來的 Whiteboard 版本中傳回。 [深入瞭解白板共用案例。](https://support.microsoft.com/office/enable-microsoft-whiteboard-for-your-organization-1caaa2e2-5c18-4bdf-b878-2d98f1da4b24) |
| 當使用者選取 [結束會話] 時，某些 Surface Hub 會重新開機。  | 當Surface Hub裝置使用者選取「結束會話」功能來清除使用者資料時，Surface Hub裝置可能會錯誤地偵測到清除失敗，強制重新開機Windows以確保清除成功發生。  | Microsoft 已瞭解並正在積極調查此問題。  Microsoft 會儘快提供有關解決方案的其他資訊。|
| 在 GCC High 環境中使用 Surface Hub 時，歡迎畫面行事曆中的單鍵會議加入無法運作。 | 在 GCC High 環境中，按一下Teams會議Surface Hub行事曆中的 [加入] 並不會自動啟動會議。 | 若要加入會議，請啟動Teams，然後從Teams用戶端顯示的議程中加入會議。 <br></br>Microsoft 也會積極調查此問題，並儘快提供有關解決方案的其他資訊。 |
| 服務品質 (QoS) 設定無法如預期般運作 | 透過 MDM 原則或布建套件設定 QoS 設定之後，不會將 DSCP 標記套用至Teams或商務用 Skype (SfB) 媒體流量。 | Microsoft 已瞭解並正在積極調查此問題。  Microsoft 會儘快提供有關解決方案的其他資訊。 |
| 混合式裝置帳戶與內部部署信箱的行事曆同步處理失敗。 | Surface Hub裝置預設為針對存在於Azure AD中的帳戶使用新式驗證，即使其在未啟用[混合式新式驗證](/microsoft-365/enterprise/configure-exchange-server-for-hybrid-modern-authentication)的內部部署環境中有信箱也一樣。 在此案例中，Exchange會停止將會議同步至裝置。 因此，裝置不會接收或顯示新的會議。 | [在 KB4598291](https://support.microsoft.com/help/4598291) (或後續Windows CU) 安裝之後，[SurfaceHub CSP](/windows/client-management/mdm/surfacehub-csp)有新的 ExchangeModernAuthEnabled 參數可用來切換新式驗證的使用。 這可以透過 MDM 原則或 [布建套件](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/ExchangeModernAuthDisabled.ppkg) 設定為 false，以防止中樞使用新式驗證。 |
| v1 Surface Hub裝置的小型子集無法自動升級至 Windows 10 團隊版 2020 Update。 | v1 Surface Hub裝置的這個小型子集處於無法透過 Windows Update 直接升級的相容性狀態。 | [使用 Surface Hub Recovery Tool](surface-hub-recovery-tool.md)手動將裝置重新映射到 Windows 10 團隊版 2020 更新。 |
| Surface Hub在嘗試安裝 Windows 10 團隊版 2020 更新之後，顯示「沒有可開機裝置」訊息。 | 在 Windows 10 團隊版 2020 的Windows Update程式中，某些中樞 v1 裝置會進入無法啟動的狀態。 | [使用 Surface Hub Recovery Tool](surface-hub-recovery-tool.md)手動將裝置重新映射到 Windows 10 團隊版 2020 更新。 |
| 中樞 2S 裝置無法使用 WSUS 接收驅動程式更新。 | Surface Hub 2S 支援Windows Update和商務用Windows Update散發驅動程式;不支援透過 Windows Server Update Services (WSUS) 進行散發。 | 如果使用 WSUS，請移轉至商務用 Windows Update。<br> <br>**深入瞭解**：[什麼是商務Windows更新？](/windows/deployment/update/waas-manage-updates-wufb) |
| 控制中心有一個無法點選的設定連結。 | 此連結不應該出現在Windows 10 團隊版中，而且可能會造成混淆。 | 此功能與 2020 更新之前相同;[開始] 功能表的 [應用程式] 區段應該用來啟動設定應用程式。  |
| 一些易於存取的設定會在會話結束後保存| 當使用者從 [快速動作] 功能表或從設定應用程式開啟 [高對比] 切換時，此切換會在使用者會話結束後持續存在。 同樣地，如果使用者將通知顯示變更為表示 7 秒與系統管理員定義的 5 秒，則會維持 7 秒，即使其他設定重設為系統管理員定義的值也一樣。 | 使用者可以在中樞上啟動會話之後，立即從工作列上可存取的快速動作 (插入號) 功能表關閉 [高對比] 切換。 下一位使用者可以透過設定應用程式，將通知的顯示持續時間設定為不同的值 - 所有使用者都可以存取此設定。 Microsoft 正積極尋找此問題的解決方法。| 
