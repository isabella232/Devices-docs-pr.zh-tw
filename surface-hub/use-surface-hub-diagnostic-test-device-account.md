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
ms.openlocfilehash: 0a9914f5c07a33306cc8a3ef87de85df47a05a20
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911428"
---
# <a name="using-the-surface-hub-hardware-diagnostic-tool-to-test-a-device-account"></a>使用 Surface Hub 硬體診斷工具來測試裝置帳戶

## <a name="introduction"></a>簡介

> [!NOTE]
> 硬體診斷設定的「Surface Hub」區段不會收集任何資訊。 輸入為輸入的電子郵件和密碼只會直接用於您的環境，不會收集或傳送給任何人。 登入資訊只會持續到應用程式關閉或您結束目前會話Surface Hub。

> [!IMPORTANT]
> * 執行此應用程式不需要系統管理員許可權。
> * 在向 Microsoft 開啟服務通話之前，應該先與您的當地系統管理員討論診斷結果。

### <a name="surface-hub-hardware-diagnostic"></a>Surface Hub硬體診斷

根據預設[，Surface Hub](https://www.microsoft.com/store/apps/9nblggh51f2g)診斷應用程式不會安裝在較舊版本的 Surface Hub系統中。 應用程式可從應用程式Microsoft Store。 安裝應用程式需要系統管理員許可權。

   ![硬體診斷的螢幕擷取畫面。](images/01-diagnostic.png)

## <a name="about-the-surface-hub-hardware-diagnostic-tool"></a>關於 Surface Hub診斷工具

Surface Hub診斷工具是一種易於流覽的工具，可讓使用者在裝置內測試Surface Hub元件。 此工具也可以測試及驗證Surface Hub帳戶。 本文將說明如何在硬體診斷工具設定帳戶Surface Hub測試。

> [!NOTE]
> 完成任何測試Surface Hub應先建立帳戶的裝置帳戶。 系統管理員Surface Hub指南提供指示和 PowerShell 腳本，可協助您建立內部部署、線上 (Office365) 或混合式裝置帳戶。 若要詳細資訊，請前往指南中建立[ (Surface Hub) 測試裝置](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub)帳戶。

### <a name="device-account-testing-process"></a>裝置帳戶測試程式

1. 流覽至**所有應用程式**，然後找到 Surface Hub診斷應用程式。

    ![所有 App 的螢幕擷取畫面。](images/02-all-apps.png)

1. 應用程式啟動時，歡迎頁面會**** 提供一個文字視窗，以記錄您測試中心的原因。 此筆記可以連同測試結束時的診斷結果一起儲存到 USB。 輸入完筆記之後，請 **選取繼續按鈕** 。

    >[!NOTE]
    >當保存診斷結果時，請勿變更預設路徑或選取子目錄。 檔案稍後可透過檔案檔案管理器應用程式複製。

    ![歡迎畫面快照。](images/03-welcome.png)

1. 下一個畫面提供您測試所有或部分元件Surface Hub選項。 若要開始測試裝置帳戶，請 **選取測試結果圖示** 。

    ![測試選項的螢幕擷取畫面。](images/04-test-results-1.png)

    ![測試結果的螢幕擷取畫面。](images/05-test-results-2.png)

1. 選取**帳戶設定。**  

    ![帳戶帳戶的螢幕設定。](images/06-account-settings.png)

    帳戶設定畫面是用來測試您的裝置帳戶。

    ![帳戶與詳細設定螢幕擷取畫面。](images/07-account-settings-details.png)

1. 輸入裝置帳戶的電子郵件地址。 密碼為選擇性，但建議使用。 準備好 **要繼續** 時，請選取測試帳戶按鈕。

    ![測試帳戶的螢幕擷取畫面。](images/08-test-account.png)

1. 測試完成後，檢閱四個測試區域的結果。 選取每個主題旁的加號或減號，即可展開或展開每個節。

    **網路**

    ![網路螢幕擷取畫面。](images/09-network.png)

    **環境**

    ![環境螢幕擷取畫面。](images/10-environment.png)

    **憑證**

    ![憑證的螢幕擷取畫面。](images/11-certificates.png)

    **信任模型**

    ![信任模型的螢幕擷取畫面。](images/12-trust-model.png)

## <a name="appendix"></a>附錄

### <a name="field-messages-and-resolution"></a>域訊息和解決

#### <a name="network"></a>網路

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
網際網路連接 |裝置具有網際網路連接 |裝置沒有網際網路連接 |驗證網際網路連接，包括 Proxy 連接 |
HTTP 版本 |1.1 |1.0 |如果找到 HTTP 1.0，則會導致 WU 和 Store 發生問題 |
直接網際網路連接 |裝置有 Proxy 已配置的裝置沒有已配置的 Proxy |不適用 |資訊。 您的裝置是否位於 Proxy 後面？ |
Proxy 位址 | | |如果已配置，會返回 Proxy 位址。 |
Proxy 驗證 |Proxy 不需要驗證 |Proxy 需要 Proxy 驗證 |如果使用者已經在 Edge 中開啟會話，而且已經透過 Proxy 進行驗證，則結果可能是誤誤。 |
Proxy 驗證類型 | | |如果使用 Proxy 驗證，請返回 Proxy 所宣告的驗證方法。  |

#### <a name="environment"></a>環境

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
SIP 網域 | | |資訊。  |
Skype環境 |商務用 Skype線上，商務用 Skype OnPrem，商務用 Skype 混合式 |資訊。 |偵測到的環境類型。 注意：只有在輸入密碼時，才能偵測混合式。
LyncDiscover FQDN | | |資訊。 顯示 LyncDiscover DNS 結果 |
LyncDiscover URI | | |資訊。 顯示用於在環境中執行 LyncDiscover 的 URL。|
LyncDiscover |連接成功 |連接失敗 |LyncDiscover Web 服務的回應。 |
SIP Pool Hostname | | |資訊。 顯示從 LyncDiscover 所發現的 SIP 資源庫名稱 |

#### <a name="certificates-in-premises-hybrid-only"></a>憑證 (內部部署混合式) 

LyncDiscover 憑證

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
LyncDiscover Cert CN | | |資訊。 顯示 LDL 證書共同名稱 |
LyncDiscover Cert CA | | |資訊。 顯示 LD Cert CA |
LyncDiscover Cert Root CA | | |資訊。 顯示 LDL Cert Root CA ，如果可用。 |
LDL 信任狀態 |憑證為信任。 |憑證不可信任，請新增根 CA。 |針對本地證書存放區驗證憑證。 如果電腦信任憑證，則會返回正數。|[使用 PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / 下載商務用 Skype部署憑證[適用于資源Surface Hub套件的支援專案](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

SIP Pool 認證

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
SIP Pool Cert CN | | | (內容)  |
SIP Pool Cert CA | | | (內容)  |
SIP Pool 信任狀態 |憑證為信任。 |憑證不可信任，請新增根 CA。 |針對本地證書存放區驗證憑證，如果裝置信任憑證，則會退回正數。 |
SIP Pool Cert Root CA | | |資訊。 顯示 SIP Pool Cert Root CA ，如果可用。 |

#### <a name="trust-model-on-premises-hybrid-only"></a>信任模型 (內部部署混合式) 

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
信任模型狀態 |未偵測到信任模型問題。 |SIP 網域和伺服器網域不同，請新增下列網域。 |檢查用於信任模型問題的LD FQDN/LD Server Name/Pool Server 名稱。 
功能變數名稱 ()  | | |返回應新增的網域清單，讓 SFB 連結。 |
