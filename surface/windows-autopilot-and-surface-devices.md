---
title: Windows Autopilot 與 Surface 裝置
ms.reviewer: ''
manager: laurawi
description: 瞭解適用于 Surface 裝置的 Windows Autopilot 部署選項。
keywords: autopilot、windows 10、surface、部署
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: ea5920649a4a29841b102de73c88187440968910
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831279"
---
# Windows Autopilot 與 Surface 裝置

Windows Autopilot 是 Windows 10 中的雲端部署技術。 您可以使用 Windows Autopilot 從盒中的零觸程式直接部署和設定裝置。

Windows Autopilot 已註冊的裝置會在第一次啟動時透過一個名為「*硬體雜湊*」的唯一裝置簽名來識別網際網路。 它們是使用新式管理解決方案（例如 Azure Active Directory （Azure AD）與行動裝置管理）自動進行註冊和設定。

您可以從已啟用 Windows Autopilot 的 Surface 合作夥伴處，在購買時登記 Surface 裝置。 這些合作夥伴可以直接將新裝置傳送給您的使用者。 裝置第一次開啟時，系統會自動進行註冊和設定。 這個程式會在部署期間消除映射，這可讓您實現裝置管理和發佈的新敏捷方法。

## 現代化管理

Autopilot 是適用于 Surface 裝置的建議部署選項，包括 Surface Pro 7、Surface 膝上型3和 Surface Pro X （專為透過 Autopilot 進行部署而設計）。

 最佳做法是使用 Microsoft 雲端解決方案提供者的說明來註冊 Surface 裝置。 此步驟可讓您直接從 Intune 管理 Surface 中的 UEFI 固件設定。 它不需要實際觸控裝置就能管理證書。 如需詳細資訊，請參閱[Intune 的 SURFACE UEFI 設定](surface-manage-dfci-guide.md)。

## Windows 版本注意事項

透過 Windows Autopilot 廣泛部署 Surface 裝置，包括購買時由 Surface 合作夥伴進行登記，需要 Windows 10 版本1709（秋季創意者更新）或更新版本。

這些 Windows 版本支援4000位元組（4k）的雜湊值，可唯一識別 Windows Autopilot 的裝置，而這是在規模部署時所需的。 所有新的 Surface 裝置，包括 Surface Pro 7、Surface Pro X 及 Surface 膝上型電腦3，隨附于 Windows 10 版本1903或更新版本。

## 需要修復或更換的 Surface 裝置上的 Exchange 體驗

Microsoft 會自動檢查 Autopilot 註冊的每個 Surface，並將裝置從客戶的租使用者取消註冊。  只要將更換傳回給客戶，Microsoft 就能確保將更換裝置登記至 Windows Autopilot。 此服務可在所有裝置 exchange 服務訂單上直接使用 Microsoft 取得。

> [!NOTE]
> 當客戶使用合作夥伴傳回裝置時，合作夥伴負責管理 exchange 程式，包括將裝置登出並註冊至 Windows Autopilot。

## 已啟用 Windows Autopilot 的 Surface 合作夥伴

選取 [Surface partner （Surface）合作夥伴] 可在購買時為您在 Windows Autopilot 中註冊 Surface 裝置。 他們也可以直接將已註冊的裝置傳送給您的使用者。 您可以使用 Windows Autopilot、Azure AD 及行動裝置管理，完全透過零觸控程式來設定裝置。

已啟用 Windows Autopilot 的 Surface 合作夥伴包括：

| 美國合作夥伴 | 全球合作夥伴 | 美國分銷商 |
|--------------|---------------|-------------------|
| * [CDW](https://www.cdw.com/) | * [也](https://www.also.com/ec/cms5/de_1010/1010_anbieter/microsoft/windows-autopilot/index.jsp) | * [Synnex](https://www.synnexcorp.com/us/microsoft/surface-autopilot/)  |
| * [連結](https://www.connection.com/brand/microsoft/microsoft-surface)   | * [ATEA](https://www.atea.com/) | * [Techdata](https://www.techdata.com/)  |
| * [見解](https://www.insight.com/en_US/buy/partner/microsoft/surface/windows-autopilot.html)  | * [Bechtle](https://www.bechtle.com/marken/microsoft/microsoft-windows-autopilot) | * [Ingram](https://go.microsoft.com/fwlink/p/?LinkID=2128954)   |
| * [SHI](https://www.shi.com/Surface) | * [Cancom](https://www.cancom.de/) |    |
| * [LDI 連接](https://www.myldi.com/managed-it/)  | * [Computacenter](https://www.computacenter.com/uk) |    |
| * [複合鍵](https://www.functiononeit.com/#empower)  |   |  |
| * [受保護的信任](https://go.microsoft.com/fwlink/p/?LinkID=2129005) | | | 

## 深入了解

如需有關 Windows Autopilot 的詳細資訊，請參閱：
- [Windows Autopilot 概觀](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-10-autopilot)
- [Windows Autopilot 需求](https://docs.microsoft.com/windows/deployment/windows-autopilot/windows-autopilot-requirements)