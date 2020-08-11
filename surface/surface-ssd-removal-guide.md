---
title: 相容 Surface 裝置中的 SSD 移除
description: 如何將 SSD 從一個 Surface 裝置轉移到另一個 Surface 裝置。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: v-todmc
ms.topic: article
ms.date: 8/7/2020
ms.reviewer: johnk
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 66860af06f4fad8f19ca26702350f19cc85ffef1
ms.sourcegitcommit: bad416f04c6877f2200f134a69146bb633155f22
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/10/2020
ms.locfileid: "10919222"
---
# 從相容的 Surface 裝置移除 SSD 的最佳做法

> [!IMPORTANT]
> 本文僅供企業組織中合格的 IT 技術人員使用。 它描述合格的 IT 技術人員在有可移除 SSDs 的 Surface 裝置中移除及取代 SSDs 時所建議的最佳做法。 

> [!WARNING]
> 開啟裝置和取代裝置元件可能會帶來電擊、裝置損壞、火災及個人傷亡風險，以及其他危害。  當您執行這類活動時，請務必謹慎使用。 遵循[企業 RSSD 移除指南](https://www.microsoft.com/download/100440)中所識別的安全預防措施和程式。 如果您無法遵循「在企業版 rSSD 移除指南」中所指定的安全預防措施及程式，我們建議您取得專業協助。

## 必要條件

> [!IMPORTANT]
> 本文假設您瞭解「適用于企業的 rSSD 移除指南」中所述的一般安全預防措施及安全原則與程式。

## 準備進行 SSD 移除 

### 安裝最新的更新 

在開始之前，請確定您的 Windows 版本已 intalled 最新的更新：

1.  移至 [**啟動**  >  **設定**  >  **更新 & 安全性**]，然後選取 [**檢查更新**]。 安裝所有可用的更新。 
2. 安裝所有可用的更新。
3. 確認您有任何需要存取裝置的密碼。  
 
## [管理 BitLocker] 

> [!NOTE]
> 本節包含對硬碟啟用 BitLocker 加密的組織的建議。 如需詳細資訊，請參閱[BitLocker 恢復指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。 

### 如果在 SSD 移除與取代期間停用 BitLocker 加密

如果可在 SSD 移除與取代之前解除加密裝置，請遵循下列步驟關閉 BitLocker：

1.  在 [**設定**] 中，輸入**bitlocker**，然後選取 [**管理 bitlocker**]。 
2.  選取 [**關閉 Bitlocker**]。 
3.  關閉裝置電源。 

### 如果在 SSD 移除與取代期間啟用 BitLocker 加密

如果在 SSD 移除和取代之前，裝置經過加密，請遵循下列步驟來產生 BitLocker 復原金鑰，並將它儲存至 USB 儲存空間：

1.  在 [**設定**] 中，輸入**Bitlocker**。
2. 選取 [**管理 bitlocker**  > **產生 bitlocker 復原金鑰**]。
2.  插入 USB 磁片磁碟機。 
3.  將修復金鑰儲存至 USB 儲存空間。  
4.  移除 USB 磁片磁碟機。  
5.  關閉裝置電源。 

## 移除並取代 SSD 

1.  使用適用于[企業的 RSSD 移除指南](https://www.microsoft.com/download/100440)中的指示來移除 SSD。 
2. 將原始的 SSD 放入新的裝置，然後將新裝置連接至有線網際網路連線。
2.  開啟新裝置的電源。 在啟動期間，裝置可能會進行固件更新。  
 
## 在 SSD 移除和取代後

### 管理未加密的 SSDs 

如果 SSD 在傳輸期間保持不加密，請遵循下列步驟： 

1.  移至 [登**入選項**]  >  (左側的 [金鑰] 圖示所代表的**密碼**) 。  
2.  輸入密碼，並登入 [待處理的雙因素驗證] (（如果適用的話）) 。
3.  當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。  
4.  使用密碼重新登入，然後在系統提示時設定 Windows Hello 及 PIN。 
    - 如果裝置已在 BitLocker 停用，以協助 SSD 移除及取代，且您想要在更換之後啟用 bitlocker，請移至**bitlocker**  >  **管理 bitlocker**[  >  **繼續 bitlocker**]。  
6.  執行適用于商務 () SDT 的 Microsoft Surface 診斷工具組，以驗證完整的裝置功能。  
7.  流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  ** **。  如果您看到任何錯誤訊息，請選取 [**疑難排解**]。 
8.  開啟**office 應用程式**，然後**流覽至 [** 檔案  >  **帳戶**]，然後檢查是否有任何錯誤訊息，以檢查 office 帳戶。  

### 管理加密 SSDs 

> [!NOTE]
> 您必須有第二個裝置，才能讀取儲存在 USB 磁片磁碟機上的 BitLocker 復原金鑰。 

如果 SSD 在傳輸期間仍保持加密，請遵循下列步驟：

1.  將內含 Bitlocker 復原金鑰的 USB 磁片磁碟機插入第二個裝置。 
2.  開啟內含 Bitlocker 復原金鑰的 .txt 檔案。 
3.  在包含原始 SSD 的新裝置上手動輸入 Bitlocker 復原金鑰。  
4.  成功輸入 BitLocker 復原金鑰之後，請移至 [登**入選項**]  >  (左邊的 [金鑰] 圖示所代表的**密碼**) 。  
5.  如果適用) 的話，請輸入密碼並登入，以待執行的雙因素驗證 (完成。
6.  當您完全登入後，請移至 [**開始**  >  **帳戶**  >  **登出**]。  
7.  使用密碼重新登入，然後設定 Windows Hello 並新增 PIN。 
8.  如果裝置是 BitLocker 停用的，可協助 SSD 移除及取代，而且如果您想要在更換後啟用 bitlocker，請移至 [**設定**  >  **bitlocker**  >  **管理 bitlocker**  >  **繼續 bitlocker**]。  
9.  執行**SDT**以驗證完整的裝置功能。  
10. 流覽至 [**設定**啟用] 以檢查 Windows 啟用  >  ** **。  如果您看到任何錯誤訊息，請選取 [**疑難排解**]。
11. 若要檢查 office 帳戶的狀態，請開啟**office 應用程式**，然後**移至 [** 檔案帳戶]，  >  **Account**檢查是否有任何錯誤訊息。

## 詳細資訊 

如需詳細資訊，請參閱下列文章：

- [企業版的 rSSD 移除指南](https://www.microsoft.com/download/100440)
- [BitLocker 修復指南](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

仍需要協助？ 移至[Microsoft 社區](https://answers.microsoft.com/)。