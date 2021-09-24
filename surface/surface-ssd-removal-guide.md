---
title: 相容 Surface 裝置中的 SSD 移除
description: 本文適用于合格的 IT 技術人員，說明在 Surface Laptop 4、Surface Laptop 3、Surface Pro 7+、Surface Pro X 和 Surface Laptop Go 中移除和取代 SSD 的建議最佳做法。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: mccoybot
ms.author: brrecord
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: ''
manager: laurawi
ms.audience: itpro
audience: ITPro
appliesto:
- Surface Laptop Studio
- Surface Pro 8
- Surface Pro 7+
- Surface Pro X
- Surface Laptop Go
- Surface Laptop 3
- Surface Laptop 4
ms.custom:
- CI 121887
- CSSTroubleshoot
ms.openlocfilehash: 6df16955eda79d52097fc4f9490b6d1e445b7e26
ms.sourcegitcommit: 760a3bdd2e40ecefe4f588703fa9281dd8f2b4b7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/24/2021
ms.locfileid: "12037505"
---
# <a name="best-practices-for-ssd-removal-from-compatible-surface-devices"></a>從相容的 Surface 裝置移除 SSD 的最佳作法

> [!IMPORTANT]
> 本文僅供企業組織中合格的 IT 技術人員使用。 本文說明合格 IT 技術人員在移除及取代下列相容 Surface 裝置中的 SSD 時所建議的最佳作法：

- Surface Laptop演播室
- Surface Pro 8
- Surface Pro 7+
- Surface Pro X
- Surface Laptop去
- Surface Laptop 3
- Surface Laptop 4

> [!WARNING]
> 開啟裝置及取代裝置元件時，可能會造成觸電、裝置損壞、起火和個人傷亡風險，以及其他危險。  進行這類活動時，務必小心。 請遵循[rSSD](https://www.microsoft.com/download/100440)移除指南所識別的安全注意事項Enterprise。 如果您無法遵循「rSSD 移除指南」中指定的安全注意事項和程式，建議您獲得專業協助Enterprise。

## <a name="prerequisites"></a>必要條件

> [!IMPORTANT]
> 本文假設您瞭解「rSSD 移除指南」所述的一般安全注意事項及安全Enterprise。

## <a name="prepare-for-ssd-removal"></a>準備移除 SSD

### <a name="install-the-latest-updates"></a>安裝最新更新

開始之前，請確定您的Windows已安裝最新的更新：

1. 請前往**** 開始  >  **設定**  >  **更新&安全性**，然後選取**檢查更新**。
2. 安裝所有可用的更新。
3. 驗證存取裝置所需的任何密碼。  

## <a name="manage-bitlocker"></a>[管理 BitLocker]

> [!NOTE]
> 本節包含針對已啟用硬碟 BitLocker 加密的組織的建議。 詳細資訊，請參閱  [BitLocker 修復指南](/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)。

### <a name="if-bitlocker-encryption-is-disabled-during-ssd-removal-and-replacement"></a>如果在 SSD 移除和更換期間停用 BitLocker 加密

如果裝置在移除和更換 SSD 之前可以取消加密，請遵循下列步驟關閉 BitLocker：

1. 在**設定**中，輸入**BitLocker，** 然後選取**管理 BitLocker**。
2. 選取 **關閉 BitLocker**。
3. 關閉裝置電源。

### <a name="if-bitlocker-encryption-is-enabled-during-ssd-removal-and-replacement"></a>如果在 SSD 移除和更換期間啟用 BitLocker 加密

如果裝置在移除和更換 SSD 之前已加密，請按照下列步驟產生 BitLocker 修復金鑰，並將其儲存到 USB 儲存空間：

1. 在**設定**中，輸入**BitLocker**。
2. 選取**管理 BitLocker**  > **產生 BitLocker 修復金鑰**。
2. 插入 USB 磁碟機。
4. 將修復金鑰儲存到 USB 儲存空間。  
5. 移除 USB 磁碟機。  
6. 關閉裝置電源。

## <a name="remove-and-replace-ssd"></a>移除及取代 SSD

1. 使用[rSSD](https://www.microsoft.com/download/100440)移除指南中適用于您裝置的適當指示來移除 SSD Enterprise。
2. 將原始的 SSD 放入新裝置，然後將新裝置連接到有線網際網路連接。
3. 在新裝置上電源。 裝置在啟動期間可能會經歷一次固件更新。  

## <a name="after-ssd-removal-and-replacement"></a>在移除和取代 SSD 之後

### <a name="manage-unencrypted-ssds"></a>管理未加密的 SSD

如果在傳輸期間未加密 SSD，請遵循下列步驟：

1. 請**前往左側按鍵** (以代表的登錄選項密碼  >  ** **) 。  
2. 輸入密碼並完成雙因素驗證並 (如果適用) 。
3. 完成登錄後，請前往**開始**  >  **帳戶**  >  **登出**。  
4. 使用密碼重新登錄，並設定Windows Hello提示時輸入密碼和 PIN。
    - 如果裝置已停用 BitLocker，以協助移除和取代 SSD，而您想要在取代之後啟用 BitLocker，請前往**BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker**。  
6. 執行 [商務用 Microsoft Surface 診斷工具](surface-diagnostic-toolkit-for-business-intro.md) (SDT) 驗證完整的裝置功能。  
7. 流覽至 Windows 啟用 以**檢查設定**  >  **啟用**。  如果您看到任何錯誤訊息，請選取 疑 **難解答**。
8. 開啟 Office App，流覽至檔案Office**** 帳戶，然後****  >  **** 檢查是否有錯誤訊息，以檢查帳戶。  

### <a name="managing-encrypted-ssds"></a>管理加密的 SSD

> [!NOTE]
> 您必須有第二個裝置，以讀取儲存于 USB 磁碟機上的 BitLocker 修復金鑰。

如果在傳輸期間將 SSD 加密，請遵循下列步驟：

1. 將包含 BitLocker 修復金鑰的 USB 磁碟機插入第二個裝置。
2. 開啟.txt Bitlocker 修復金鑰的檔案。
3. 在包含原始 SSD 的新裝置上手動輸入 BitLocker 修復金鑰。  
4. 成功輸入 BitLocker 修復金鑰之後，請前往 (**** 左側按鍵圖示代表的登錄選項密碼  >  ** **) 。  
5. 在雙因素驗證完成之前，輸入密碼並 (並) 。
6. 完成登錄後，請前往**開始**  >  **帳戶**  >  **登出**。  
7. 使用密碼重新登錄，然後設定Windows Hello並新增 PIN。
8. 如果裝置已停用 BitLocker，以方便移除和取代 SSD，而且如果您想要在取代之後啟用 BitLocker，請前往 設定****  >  **BitLocker**  >  **Manage BitLocker**  >  **Resume BitLocker**。  
9. 執行 **[SDT](surface-diagnostic-toolkit-for-business-intro.md)** 以驗證完整的裝置功能。  
10. 若要檢查Windows，請選取**設定**  >  **啟用**。  如果您看到任何錯誤訊息，請選取 疑 **難解答**。
11. 若要檢查帳戶Office，請開啟 Office **App，** 然後前往檔案帳戶檢查****  >  **** 是否有錯誤訊息。

## <a name="learn-more"></a>深入了解

- [rSSD 移除指南Enterprise](https://www.microsoft.com/download/100440)
- [BitLocker 修復指南](/windows/security/information-protection/bitlocker/bitlocker-recovery-guide-plan)

仍需要協助？ 前往[Microsoft Community。](https://answers.microsoft.com/)
