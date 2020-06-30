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
# 使用 Surface Hub 硬體診斷工具來測試裝置帳戶

## 簡介

> [!NOTE]
> Surface Hub 硬體診斷工具的 [帳戶設定] 區段不會收集任何資訊。 輸入為輸入的電子郵件和密碼只會直接在您的環境中使用，不會收集或轉讓給任何人。 登入資訊只有在應用程式關閉或您結束 Surface Hub 上的目前會話，才會持續出現。

> [!IMPORTANT]
> * 執行這個應用程式不需要系統管理員許可權。
> * 在使用 Microsoft 開啟服務電話之前，請先與您的本機系統管理員討論診斷結果。

### Surface Hub 硬體診斷

根據預設， [Surface Hub 硬體診斷](https://www.microsoft.com/store/apps/9nblggh51f2g)應用程式不會安裝在舊版 Surface Hub 系統中。 您可以從 Microsoft 網上商店免費取得該應用程式。 必須具備系統管理員許可權才能安裝應用程式。

   ![硬體診斷的螢幕擷取畫面](images/01-diagnostic.png)

## 關於 Surface Hub 硬體診斷工具

Surface Hub 硬體診斷工具是一種易於流覽的工具，可讓使用者在 Surface Hub 裝置中測試許多硬體元件。 這個工具也可以測試並驗證 Surface Hub 裝置帳戶。 本文說明如何在 Surface Hub 硬體診斷工具中使用帳戶設定測試。

> [!NOTE]
> 必須先建立 Surface Hub 的裝置帳戶，才能完成任何測試。 Surface Hub 管理員指南提供指示和 PowerShell 腳本，可協助您建立內部部署、線上（Office365）或混合式裝置帳戶。 如需詳細資訊，請移至指南中的[建立和測試裝置帳戶（Surface Hub）](https://docs.microsoft.com/surface-hub/create-and-test-a-device-account-surface-hub)主題。

### 裝置帳戶測試程式

1. 流覽至 [**所有應用程式**]，然後找出 Surface Hub 硬體診斷應用程式。

    ![[所有應用程式] 的螢幕擷取畫面](images/02-all-apps.png)

1. 當應用程式啟動時，[**歡迎**] 頁面會提供文字視窗，以記錄您測試中樞的原因。 在測試結束時，您可以將此筆記連同診斷結果一起儲存至 USB。 完成輸入筆記後，請選取 [**繼續**] 按鈕。

    ![歡迎的螢幕擷取畫面](images/03-welcome.png)

1. 下一個畫面會提供測試全部或部分 Surface Hub 元件的選項。 若要開始測試裝置帳戶，請選取 [**測試結果**] 圖示。

    ![測試結果的螢幕擷取畫面](images/04-test-results-1.png)

    ![測試結果的螢幕擷取畫面](images/05-test-results-2.png)

1. 選取 [**帳戶設定**]。  

    ![帳戶設定的螢幕擷取畫面](images/06-account-settings.png)

    [帳戶設定] 畫面可用來測試您的裝置帳戶。

    ![[帳戶設定] 詳細資料的螢幕擷取畫面](images/07-account-settings-details.png)

1. 輸入您的裝置帳戶的電子郵件地址。 密碼是選擇性的，但建議使用。 當您準備好要繼續時，請選取 [**測試帳戶**] 按鈕。

    ![測試帳戶的螢幕擷取畫面](images/08-test-account.png)

1. 測試完成後，請檢查四個測試區域的結果。 您可以透過選取每個主題旁的加號或減號，展開或折迭每個區段。

    **網路**

    ![網路的螢幕擷取畫面](images/09-network.png)

    **環境**

    ![環境的螢幕擷取畫面](images/10-environment.png)

    **憑證**

    ![憑證的螢幕擷取畫面](images/11-certificates.png)

    **信任模型**

    ![信任模型的螢幕擷取畫面](images/12-trust-model.png)

## 附錄

### 欄位訊息及解析度

#### 網路

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
網際網路連線能力 |裝置有網際網路連線能力 |裝置沒有網際網路連線能力 |驗證網際網路連通性，包括 proxy 連線 |
HTTP 版本 |1.1 |1.0 |如果找到 HTTP 1.0，將會在 WU 和 Store 中造成問題 |
直接網際網路連線 |裝置已設定 Proxy 的裝置沒有設定 Proxy |無 |參考. 您的裝置是在 proxy 後嗎？ |
Proxy 位址 | | |如果已設定，則會傳回 proxy 位址。 |
Proxy 驗證 |Proxy 不需要驗證 |Proxy 需要 Proxy 驗證 |如果使用者已在 Edge 中有開啟的會話，且已透過 proxy 進行驗證，結果可能是誤報。 |
Proxy 驗證類型 | | |如果使用 proxy 驗證，請傳回 proxy 宣告的驗證方法。  |

#### 環境

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
SIP 網域 | | |參考.  |
Skype 環境 |商務用 skype Online、商務用 Skype OnPrem、商務用 Skype 混合式 |參考. |偵測到的環境類型。 注意：只有在輸入密碼時，才能檢測到混合式。
LyncDiscover FQDN | | |參考. 顯示 LyncDiscover 的 DNS 結果 |
LyncDiscover URI | | |參考. 顯示用於在您的環境上執行 LyncDiscover 的 URL。|
LyncDiscover |連接成功 |連線失敗 |從 LyncDiscover web 服務回應。 |
SIP 池主機名稱 | | |參考. 顯示從 LyncDiscover 探索的 SIP 池名稱 |

#### 憑證（僅限內部部署混合式）

LyncDiscover 憑證

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
LyncDiscover Cert CN | | |參考. 顯示 LD cert 公用名稱 |
LyncDiscover Cert CA | | |參考. 顯示 LD Cert CA |
LyncDiscover Cert 根 CA | | |參考. 顯示 LD Cert 根 CA （如果有的話）。 |
LD 信任狀態 |憑證是受信任的。 |證書不受信任，請新增根 CA。 |對照本機憑證存放區驗證憑證。 如果電腦信任憑證，則傳回正值。|[使用 PowerShell](https://blogs.msdn.microsoft.com/surfacehub/2016/06/07/download-and-deploy-skype-for-business-certificates-using-powershell/) / 下載及部署商務用 Skype 憑證[Surface Hub 置備套件支援的專案](https://docs.microsoft.com/surface-hub/provisioning-packages-for-surface-hub#supported-items-for-surface-hub-provisioning-packages)

SIP 池認證

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
SIP 池 Cert CN | | |目錄 |
SIP 池證書 CA | | |目錄 |
SIP 池信任狀態 |憑證是受信任的。 |證書不受信任，請新增根 CA。 |根據本機憑證存放區驗證憑證，如果裝置信任憑證，則傳回正面。 |
SIP 池證書根 CA | | |錯誤資訊. 顯示 SIP 池證書根 CA （如果有的話）。 |

#### 信任模型（僅限內部部署混合式）

欄位 |成功 |失敗 |留言 |參考
|------|------|------|------|------|
信任模型狀態 |未偵測到信任模型問題。 |SIP 網域和伺服器網域不同，請新增下列網域。 |針對信任模型問題，檢查 LD FQDN/LD 伺服器名稱/池伺服器名稱。 
網功能變數名稱稱 | | |傳回應為 SFB 新增的網域清單以進行連線。 |
