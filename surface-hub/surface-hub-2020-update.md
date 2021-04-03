---
title: 安裝 Windows 10 團隊版 2020 更新
description: 取得 Surface Hub 作業系統 Windows 10 小組 2020 Update 的最新更新。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/17/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4d68f751bd15ef6529bcd16a6305d8c682970747
ms.sourcegitcommit: f9e7c091a26df0f99500c0d8b6cf40a81133e4e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/01/2021
ms.locfileid: "11470411"
---
# <a name="install-windows-10-team-2020-update"></a>安裝 Windows 10 團隊版 2020 更新 

新的 Surface Hub 作業系統 **Windows 10 小組 2020 Update**，以 Windows 10 版本 20H2 為基礎，現已適用于 Surface Hub 2S 和原始的 Surface Hub (v1) 。 

- 另請參閱： [已知問題：Windows 10 小組 2020 更新](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>分佈

您可以使用下列其中一種方法取得 Windows 2020 Update：

- **商務用 Windows Update**。
- **BMR 圖像中的 (修復) 復原**。 建議將裝置加入 Azure Active Directory 或不允許其裝置從網際網路接收更新的客戶。 若要開始使用，請參閱下載 Surface [的修復映射](https://support.microsoft.com/surfacerecoveryimage)。
- **Windows Update：** 可用性會因地區/國家/地區而異，如下表所示：

| 階段 | 國家/地區                         | 開始          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ、澳洲、加拿大、比利時、墨西哥 | 2020 年 10 月  |
| 2     | 英國、日本、瑞士、義大利          | 2020 年 11 月 |
| 3     | 德國、荷蘭                   | 2021 年 2 月底 |
| 4     | 全球                                 | 2021 年 3 月初 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>使用 Windows 10 小組版 1703 維護 Surface Hub 

Windows 10 小組版 [1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f) 的完整維護支援預計持續到 2021 年 3 月 16 日。

### <a name="2s-devices"></a>2S 裝置 

所有地區的客戶都可以更新其 Surface Hub 2S 裝置至 2020 透過 Windows Update、商務用 Windows Update 更新，或是使用裸露金屬修復 (BMR) 影像，如 [Surface Hub 2S](surface-hub-2s-recover-reset.md)的重設及修復說明。

### <a name="v1-devices"></a>V1 裝置 

所有地區的客戶都可以更新其 Surface Hub v1 裝置至 2020 透過 Windows Update、商務用 Windows Update 或 [Surface Hub](surface-hub-recovery-tool.md)修復工具更新。 必須安裝 KB5000749 才能在空中接收更新。 若要深入瞭解，請參閱 [Surface IT 專業部落格](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371)。
 
## <a name="whats-new"></a>新增功能

Windows 10 小組 2020 Update 為裝置部署和可管理性帶來重大改良，以及最新的 Windows 10 功能。 若要深入瞭解，請參閱 [Windows 10 小組 2020 Update 的新增功能](surface-hub-2020-update-whats-new.md)。
 
## <a name="before-you-begin"></a>開始之前

安裝 Windows 10 小組 2020 Update 之前，請務必儲存與裝置相關聯的 BitLocker 金鑰。 

**若要手動儲存 BitLocker 金鑰**

1. 將 USB 磁碟機插入 Surface Hub。
2. 在 Surface Hub 上， **開啟設定** ，並輸入系統提示時您的系統管理員認證。
3. 流覽至**更新&**  >  **安全性修復**。
4. 在**BitLocker 下****，選取**儲存 。 BitLocker 鍵會儲存到 USB 磁碟機上的文字檔。

若要深入瞭解，請參閱儲存 [BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。

## <a name="learn-more"></a>深入了解

- [Windows 10 團隊版 2020 更新中的新功能](surface-hub-2020-update-whats-new.md)
- [Windows 10 團隊版的更新推出](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
