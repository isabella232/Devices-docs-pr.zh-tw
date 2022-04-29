---
title: 安裝 Windows 10 團隊版 2020 更新
description: 取得 Surface Hub 作業系統的最新更新，Windows 10 團隊版 2020 Update。
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
ms.openlocfilehash: 7474787351a9371fb09fa10348ac9f6591b81f6b
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497826"
---
# <a name="install-windows-10-team-2020-update"></a>安裝 Windows 10 團隊版 2020 更新 

以 Windows 10 **20H2**版為基礎的新 Surface Hub 作業系統 Windows 10 團隊版 2020 Update 現在適用于 Surface Hub 2S 和原始 Surface Hub (v1) 。 

- 另請參閱：[已知問題：Windows 10 團隊版 2020 更新](surface-hub-2020-team-update-known-issues.md)

## <a name="distribution"></a>分佈

您可以使用下列其中一種方法取得 Windows 2020 Update：

- **Windows Update商務用。**
- **裸機復原 (BMR) 映射**。 針對加入其裝置以Azure Active Directory或不允許其裝置從網際網路接收更新的客戶，建議使用此選項。 若要開始使用，請參閱 [下載 Surface 的復原映射](https://support.microsoft.com/surfacerecoveryimage)。
- **Windows Update：** 可用性會依區域/國家/地區而有所不同，如下表所述：

| 階段 | 國家/地區                         | 開始          |
| ----- | -------------------------------------- | ----------------- |
| 1     | NZ、澳洲、加拿大、比利時、墨西哥 | 2020 年 10 月  |
| 2     | 英國、日本、瑞士、義大利          | 2020 年 11 月 |
| 3     | 德國、荷蘭                   | 2021 年 2 月底 |
| 4     | 全球                                 | 2021 年 3 月初 |

## <a name="servicing-surface-hubs-with-windows-10-team-edition-version-1703"></a>使用 Windows 10 團隊版 版本 1703 維護 Surface Hub 

[Windows 10 團隊版版 1703](https://support.microsoft.com/topic/november-12-2019-kb4525245-os-build-15063-2172-dfc81b85-11a6-54ef-4370-11408193419f)的完整維護支援已排定持續到 2021 年 3 月 16 日。

### <a name="2s-devices"></a>2S 裝置 

所有區域的客戶都可以透過Windows Update、Windows Update或使用裸機復原 (BMR) 映射，將其Surface Hub [2S 裝置更新為 2020 更新，如重設和復原 Surface Hub 2S](surface-hub-2s-recover-reset.md)中所述。

### <a name="v1-devices"></a>V1 裝置 

所有區域的客戶都可以透過Windows Update、商務用Windows Update或使用 Surface Hub 修復工具，將其Surface Hub v1 裝置更新為[2020 更新](surface-hub-recovery-tool.md)。 必須安裝 KB5000749，才能透過無線方式接收更新。 若要深入瞭解，請參閱[Surface IT Pro部落格](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-hub-v1-status/ba-p/2118371)。
 
## <a name="whats-new"></a>新功能

Windows 10 團隊版 2020 Update 提供裝置部署和管理能力的重大改善，以及最新的Windows功能。 若要深入瞭解，請參閱[Windows 10 團隊版 2020 Update](surface-hub-2020-update-whats-new.md)的新功能。
 
## <a name="before-you-begin"></a>開始之前

安裝 Windows 10 團隊版 2020 Update 之前，請務必儲存與裝置相關聯的 BitLocker 金鑰。 

**手動儲存 BitLocker 金鑰**

1. 將 USB 磁片磁碟機插入Surface Hub。
2. 在Surface Hub上，開**啟 設定**，並在出現提示時輸入您的系統管理員認證。
3. 流覽至 **[更新&安全**  >  性 **][復原]**。
4. 在 **[BitLocker] 底**下，選取 [ **儲存]**。 BitLocker 金鑰會儲存至 USB 磁片磁碟機上的文字檔。

若要深入瞭解，請參閱 [儲存 BitLocker 金鑰](save-bitlocker-key-surface-hub.md)。

## <a name="learn-more"></a>深入了解

- [Windows 10 團隊版 2020 更新中的新功能](surface-hub-2020-update-whats-new.md)
- [Windows 10 團隊版的更新推出](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/surface-hub-windows-10-team-2020-update-february-status/ba-p/2118369)
