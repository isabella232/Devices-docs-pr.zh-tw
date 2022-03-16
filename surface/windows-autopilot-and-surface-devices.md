---
title: Windows Autopilot 與 Surface 裝置
ms.reviewer: ''
manager: laurawi
description: 瞭解 Surface Windows的自動pilot 部署選項。
keywords: autopilot， Windows 10， Windows 11， surface， deployment
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 9/14/2020
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: ca2dab5483ecb7ae11a102c56308742e348156bb
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448526"
---
# <a name="windows-autopilot-and-surface-devices"></a>Windows Autopilot 與 Surface 裝置

Windows Autopilot 是一項雲端式部署技術，Windows 10 Windows 11。 您可以使用 Autopilot Windows，立即在零接觸程式內遠端部署和設定裝置。

根據傳統，IT 專業人員會花很多時間建立及自訂影像，這些影像稍後會部署至已安裝完美作業系統的裝置。 Windows Autopilot 推出全新的零接觸式部署方法，使用一系列技術來設定Windows裝置。 這可讓 IT 部門設定/自訂影像，而且幾乎不需要管理基礎結構，而且程式簡單簡單。 從使用者的觀點看，讓 Surface 進入生產力狀態只需要幾個簡單的步驟。 事實上，使用者唯一需要的互動是連接網路並驗證其認證。 之後的所有專案都完全自動化。

Windows Autopilot 可讓您：

- 自動將裝置加入Azure Active Directory (Azure AD) 。
- 自動將裝置註冊到 MDM 服務 ，例如Microsoft Intune (需要Azure AD Premium訂閱) 。
- 限制建立系統管理員帳戶。 Autopilot 是讓第一個以標準使用者Windows第一個登錄使用者的唯一方法。
- 根據裝置設定檔建立及自動指派裝置至組組。
- 自訂 OOBE (即用體驗) 內容和品牌，以滿足組織需求。
- 使用 Intune 啟用完整的裝置配置。
- 遠端重設或重新開機裝置。

## <a name="how-it-works"></a>運作方式

Windows自動pilot註冊的裝置，在初次開機時會透過稱為硬體雜湊的唯一裝置簽名，透過*網際網路識別*。 系統會自動使用現代化管理解決方案進行註冊和Azure Active Directory (Azure AD) 行動裝置管理。

您可以在購買時向啟用 Autopilot 的 Surface 合作夥伴註冊 Surface Windows裝置。 這些合作夥伴可以直接將新裝置出貨給使用者。 裝置會在第一次開啟時自動註冊和進行配置。 此程式可排除部署期間重新映射，讓您執行裝置管理和發佈的新敏捷方法。

## <a name="modern-management"></a>現代化管理

Autopilot 是 Surface 裝置的建議部署選項，包括 Surface Pro 8、Surface Laptop Studio、Surface Go 3、Surface Pro 7+、Surface Laptop 4 和 Surface Pro X，這是專為透過 Autopilot 進行部署所設計。

 最好在註冊您的 Surface 裝置時，使用 Microsoft 雲端解決方案提供者。 此步驟可讓您直接從 Intune 管理 Surface 上的 UEFI 固件設定。 它不需要以實體方式觸控裝置進行憑證管理。 詳細 [資料請參閱 Surface UEFI 設定 Intune](surface-manage-dfci-guide.md) 管理。

## <a name="windows-version-considerations"></a>Windows版本考慮

透過 Windows Autopilot 廣泛部署 Surface 裝置，包括 Surface 合作夥伴在購買時註冊，需要 Windows 10 版本 1709 (Fall Creators Update) 或更新。

這些 Windows 版本支援 4，000 位元組 (4k) 雜湊值，可唯一識別 Windows Autopilot 的裝置，這是大規模部署的必要功能。

## <a name="exchange-experience-on-surface-devices-in-need-of-repair-or-replacement"></a>Exchange需要維修或更換的 Surface 裝置體驗

Microsoft 會自動檢查每個 Surface For Autopilot 註冊，並取消註冊客戶的租使用者中的裝置。  Microsoft 可確保更換裝置在運送回客戶Windows自動pilot 中註冊。 此服務可直接在 Microsoft 的所有裝置交換服務訂單上提供。

> [!NOTE]
> 當客戶使用合作夥伴傳回裝置時，合作夥伴負責管理 Exchange 程式，包括取消註冊和將裝置註冊到 Windows Autopilot。

## <a name="microsoft-support-registration"></a>Microsoft 支援註冊

客戶與 Microsoft 雲端解決方案提供者 (CSP) 向 Microsoft 支援服務提交要求，以選擇註冊 Surface 裝置。 若要深入瞭解，請參閱[適用于自動Windows的 Surface 註冊支援](surface-autopilot-registration-support.md)。

## <a name="surface-partners-enabled-for-windows-autopilot"></a>Surface 合作夥伴已啟用 Windows Autopilot

選取 Surface 合作夥伴可以在購買時Windows Autopilot 中註冊 Surface 裝置。 他們也可以直接將註冊的裝置出貨給使用者。 您可以使用 Autopilot、Windows和行動裝置管理，透過零接觸程式Azure AD裝置。

啟用自動Windows的 Surface 合作夥伴包括：

| 美國合作夥伴 | 全球合作夥伴 | 美國轉銷商 |
|--------------|---------------|-------------------|
|  [CDW](https://www.cdw.com/) |  [也](https://www.also.com/ec/cms5/da_2800/2800-msportal/products-and-solutions/surface/surface-is-more/surface-and-wa/index.jsp) |  [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
|  [[連線]](https://www.connection.com/brand/microsoft/microsoft-surface)   |  [ATEA](https://www.atea.com/) |  [Techdata](https://www.techdata.com/)  |
|  [洞察 力](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  |  [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) |  [英格拉姆](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
|  [石](https://www.shi.com/Surface) |  [Cancom](https://www.cancom.de/) |    |
|  [LDI 連線](https://www.myldi.com/managed-it/)  |  [Computacenter](https://www.computacenter.com/uk) |    |
|  [F1](https://www.functiononeit.com/#empower)  |   |  |
|  [受保護的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | |

## <a name="learn-more"></a>深入了解

有關 Autopilot Windows，請參閱：

- [Windows Autopilot 概觀](/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot 需求](/windows/deployment/windows-autopilot/windows-autopilot-requirements)
- [適用於 Windows Autopilot 的 Surface 註冊支援](surface-autopilot-registration-support.md)
