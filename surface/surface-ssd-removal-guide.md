---
title: 相容 Surface 裝置中的 SSD 移除
description: 本文適用于合格的 IT 技術人員，說明在 Surface 膝上型電腦3、Surface Pro X 和 Surface 膝上型電腦版中移除及取代 SSDs 的建議最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 01/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 51ef676e7379f0898d6b601bb08c96002c9e6ace
ms.sourcegitcommit: d4e2a29aa21a911ee55642cd66b4337b89eebdd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/14/2021
ms.locfileid: "11270628"
---
# 從相容的 Surface 裝置移除 SSD 的最佳做法

> [!IMPORTANT]
> 本文僅供企業組織中合格的 IT 技術人員使用。 它描述由合格的 IT 技術人員在下列相容 Surface 裝置中移除及取代 SSDs 的建議最佳做法： 

- Surface Pro 7 +
- Surface Pro X
- Surface 膝上型電腦前往
- Surface 膝上型電腦3

> [!WARNING]
> 開啟裝置和取代裝置元件可能會帶來電擊、裝置損壞、火災及個人傷亡風險，以及其他危害。  當您執行這類活動時，請務必謹慎使用。 遵循 [企業 RSSD 移除指南](https://www.microsoft.com/download/100440)中所識別的安全預防措施和程式。 如果您無法遵循「在企業版 rSSD 移除指南」中所指定的安全預防措施及程式，我們建議您取得專業協助。

## 必要條件

> [!IMPORTANT]
> 本文假設您瞭解「適用于企業的 rSSD 移除指南」中所述的一般安全預防措施及安全原則與程式。

## 準備進行 SSD 移除 

### 安裝最新的更新 

在開始之前，請確定您的 Windows 版本已安裝最新的更新：

1.  移至 [**啟動**  >  **設定**  >  **更新 & 安全性**]，然後選取 [**檢查更新**]。
2. 安裝所有可用的更新。
3. 確認任何存取裝置所需的密碼。  
 
## [管理 BitLocker] 

> [!NOTE]
> 本節包含對硬碟啟用 BitLocker 加密的組織的建議。 如需詳細資訊，請參閱  [BitLocker 恢復指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。 

### 如果在 SSD 移除與取代期間停用 BitLocker 加密

如果可在 SSD 移除與取代之前解除加密裝置，請遵循下列步驟關閉 BitLocker：

1.  在 [ **設定**] 中，輸入 **BitLocker** ，然後選取 [ **管理 bitlocker**]。 
2.  選取 [ **關閉 BitLocker**]。 
3.  關閉裝置電源。 

### 如果在 SSD 移除與取代期間啟用 BitLocker 加密

如果在 SSD 移除和取代之前，裝置經過加密，請遵循下列步驟來產生 BitLocker 復原金鑰，並將它儲存至 USB 儲存空間：

1.  在 [ **設定**] 中，輸入 **BitLocker**。
2. 選取 [**管理 bitlocker**  > **產生 bitlocker 復原金鑰**]。
2.  插入 USB 磁片磁碟機。 
4.  將修復金鑰儲存至 USB 儲存空間。  
5.  移除 USB 磁片磁碟機。  
6.  關閉裝置電源。 

## 移除並取代 SSD 

1.  使用適用于 [企業的 RSSD 移除指南](https://www.microsoft.com/download/100440)中所包含的裝置指示，移除 SSD。 
2.  將原始的 SSD 放入新的裝置，並將新裝置連接至有線網際網路連線。
3.  開啟新裝置的電源。 在啟動期間，裝置可能會進行固件更新。  
 
## 在 SSD 移除和取代後

### 管理未加密的 SSDs 

如果 SSD 在傳輸期間未加密，請遵循下列步驟： 

1.  移至 [登**入選項**]  >  (左側的 [金鑰] 圖示所代表的**密碼**) 。  
2.  輸入密碼，並登入 [待處理的雙因素驗證] (（如果適用的話）) 。
3.  當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。  
4.  使用密碼重新登入，並在系統提示時設定 Windows Hello 和 PIN。 
    - 如果裝置已在 BitLocker 停用，以協助 SSD 移除及取代，且您想要在更換之後啟用 bitlocker，請移至**bitlocker**  >  **管理 bitlocker**[  >  **繼續 bitlocker**]。  
6.  執行適用于商務 () SDT 的 [Microsoft Surface 診斷工具](surface-diagnostic-toolkit-for-business-intro.md) 組，以驗證完整的裝置功能。  
7.  流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  ** **。  如果您看到任何錯誤訊息，請選取 [ **疑難排解**]。 
8.  開啟**office 應用程式**，然後**流覽至 [** 檔案  >  **帳戶**]，然後檢查是否有任何錯誤訊息，以檢查 office 帳戶。  

### 管理加密 SSDs 

> [!NOTE]
> 您必須有第二個裝置，才能讀取儲存在 USB 磁片磁碟機上的 BitLocker 復原金鑰。 

如果 SSD 在傳輸期間經過加密，請遵循下列步驟：

1.  將內含 BitLocker 復原金鑰的 USB 磁片磁碟機插入第二個裝置。 
2.  開啟內含 Bitlocker 復原金鑰的 .txt 檔案。 
3.  在包含原始 SSD 的新裝置上手動輸入 BitLocker 復原金鑰。  
4.  成功輸入 BitLocker 復原金鑰之後，請移至 [登**入選項**]  >  (左邊的 [金鑰] 圖示所代表的**密碼**) 。  
5.  如果適用) 的話，請輸入密碼並登入，以待執行的雙因素驗證 (完成。
6.  當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。  
7.  使用密碼重新登入，然後設定 Windows Hello 並新增 PIN。 
8.  如果裝置是 BitLocker 停用的，可協助 SSD 移除及取代，而且如果您想要在更換後啟用 bitlocker，請移至 [**設定**  >  **bitlocker**  >  **管理 bitlocker**  >  **繼續 bitlocker**]。  
9.  執行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以驗證完整的裝置功能。  
10. 若要查看 Windows 啟用，請選取 [**設定**  >  **啟用**]。  如果您看到任何錯誤訊息，請選取 [ **疑難排解**]。
11. 若要檢查 office 帳戶的狀態，請開啟**office 應用程式**，然後**移至 [** 檔案帳戶]，  >  **** 檢查是否有任何錯誤訊息。

## 深入了解

- [企業版的 rSSD 移除指南](https://www.microsoft.com/download/100440)
- [BitLocker 修復指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

仍需要協助？ 移至 [Microsoft 社區](https://answers.microsoft.com/)。