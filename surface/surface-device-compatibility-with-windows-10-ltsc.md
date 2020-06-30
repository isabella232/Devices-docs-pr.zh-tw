---
title: 與 Windows 10 長期服務通道（Surface）相容的 Surface 裝置相容性
description: 瞭解執行 Windows 10 企業 LTSB 版的 Surface 裝置的相容性與限制。
keywords: ltsb、更新、surface 服務選項
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: db3dfd57c3b79fcec507ffd146483915490801b9
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831197"
---
# Surface 裝置與 Windows 10 長期服務通道的相容性（LTSC）

Surface 裝置的設計目的是為了在生產力與一般用途案例中提供一流的體驗。 定期更新可讓 Surface 裝置移至新的創新，並利用 Windows 10 功能更新所提供的新功能來演化。 功能更新只能在 Windows 10 專業版或 Windows 10 企業版中使用，這些版本會透過半年通道（SAC）接收連續更新。

與 SAC 服務選項（以前稱為 [目前分支（CB）] 或 [目前商務用分支（CBB）服務選項] 相反），您無法在 Windows 10 的 [設定] 中選取長期服務通道（LTSC）選項。 若要使用 LTSC 服務選項，您必須安裝個別版本的 Windows 10 Enterprise （稱為 Windows 10 企業版 LTSC，即 windows 10 企業版 LTSB （長期服務分支）。 除了提供延伸的服務模型之外，Windows 10 Enterprise LTSC edition 也提供已移除多個 Windows 元件的環境。 受 LTSC 影響的核心表面體驗包括：

* Windows 功能更新，包括增強功能，例如：

  *  改善在 Windows 10 版本1607（也稱為周年紀念更新）中提供的直接筆跡和 palm 拒絕
  *  改善 Windows 10 版本1703（也稱為創意者更新）中提供的高 DPI 應用程式支援

* Surface app 提供的壓力靈敏度設定

* Windows Ink 工作區

* 重要的觸控優化的主機殼內應用程式，包括 Microsoft Edge、OneNote、行事曆及攝影機

在 Surface 裝置上使用 Windows 10 企業 LTSC 環境會產生欠最佳的最終使用者體驗，因此您應該避免在使用者想要且預期是最新的使用者體驗的環境中使用。

LTSC 服務選項是針對裝置類型和案例設計的，其中的主要屬性是功能或功能永遠不會變更。 例如，在您的 Atm 或機場的系統中，例如，有電力製造或醫療裝置或內嵌系統的系統。

>[!NOTE]
>如需 Windows 服務分支（包括 LTSC）的一般資訊，請參閱[將 Windows 作為服務的概覽](https://technet.microsoft.com/itpro/windows/update/waas-overview#long-term-servicing-branch)。

一般來說，符合下列準則的裝置會被視為一般用途的裝置，且應與 Windows 10 專業版或 Windows 10 Enterprise 搭配使用半年通道服務選項進行配對：

* 執行生產力軟體（例如 Microsoft Office）的裝置

* 使用 Microsoft Store 應用程式的裝置

* 用於一般網際網路流覽的裝置（例如，研究或存取社交媒體）

在您選擇要在 Surface 裝置上使用 Windows 10 企業版 LTSC 版本前，請考慮下列限制：

* 驅動程式和固件更新不會針對 Windows 10 Enterprise LTSC 的發行進行明確的測試。

* 如果您遇到問題，Microsoft 支援人員將會提供疑難排解協助。 不過，由於 Windows LTSC 的服務性質，解決問題可能需要將裝置升級為更新版本的 Windows 10 Enterprise LTSC，或是使用 SAC 服務選項升級至 Windows 10 專業版或企業版。

* 週邊裝置更換（例如，在保修期內更換的裝置）可能會在需要更新裝置驅動程式和固件的硬體元件中包含微小的變化。 相容性與這些更新，可能需要安裝更新版本的 Windows 10 Enterprise LTSC 或 Windows 10 專業版或 Enterprise （含 SAC 服務選項）。

>[!NOTE]
>在特定版本的 Windows 10 Enterprise LTSC 上進行標準化的組織，可能無法採用 surface Pro 7、Surface Pro X 或 Surface 膝上型電腦3等新代，而不需要更新至較新版本的 Windows 10 Enterprise LTSC 或 Windows 10 專業版或企業版。 如需詳細資訊，請參閱**如何支援 windows 10 LTSBs？** [[生命週期原則常見問題-windows 產品](https://support.microsoft.com/help/18581/lifecycle-policy-faq-windows-products#b4)] 區段中的 [支援**最新的處理器和晶片組**] 主題。

執行 Windows 10 Enterprise LTSC edition 的 Surface 裝置將不會收到新功能。 在許多情況下，客戶要求這些功能來改善 Surface 硬體的可用性與功能。 例如，Windows 10 （版本1703）中高 DPI 應用程式的新改良功能。 在 LTSC 設定中使用 Surface 裝置的客戶將不會看到改善，直到它們更新為新的 Windows 10 企業版 LTSC 發行或升級至 Windows 10 版本，並支援 SAC 服務選項。

裝置可從 Windows 10 Enterprise LTSC 變更為更新版本的 Windows 10 Enterprise，支援 SAC 處理選項，而不需要執行升級安裝，就不會遺失使用者資料。 您也可以利用 Microsoft 部署工具套件（MDT）和 Microsoft 端點設定管理員提供的升級任務順序範本，在多個裝置上執行升級安裝。 如需詳細資訊，請參閱[使用 Microsoft 部署工具組將 Surface 裝置升級至 Windows 10](https://technet.microsoft.com/itpro/surface/upgrade-surface-devices-to-windows-10-with-mdt)。
