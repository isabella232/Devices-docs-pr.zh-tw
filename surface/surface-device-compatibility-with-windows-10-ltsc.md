---
title: 'Surface 裝置與 Surface Windows 10 Long-Term維護通道 (相容性) '
description: 瞭解執行 LTSB 版本之 Surface Windows 10 企業版相容性和限制。
keywords: ltsb、update、Surface 維護選項
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 07/21/2021
ms.reviewer: scottmca
manager: laurawi
ms.openlocfilehash: 6127685edb0c098235734439ffbffac8c2c508ca
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338441"
---
# <a name="surface-device-compatibility-with-windows-10-long-term-servicing-channel-ltsc"></a>Surface 裝置與 LTSC Windows 10 Long-Term維護通道 (相容性) 

Surface 裝置是專為提供生產力和一般用途案例的最佳體驗所設計。 定期更新可讓 Surface 裝置發揮新的創新功能，並隨著功能更新提供的新功能Windows 10演進。 功能更新僅適用于透過 Windows 10 專業版 SAC Windows 10 企業版頻道或 SAC Semi-Annual接收 (更新) 。

與 SAC 維護選項相反，在 Windows 10 設定中，您無法選取 Long-Term 維護通道 (LTSC) 選項，這之前稱為目前分支 (CB) 或目前商務分支 (CBB) 維護選項。 若要使用 LTSC 維護選項，您必須安裝另一版的 Windows 10 企業版，稱為 Windows 10 企業版 LTSC，也稱為 Windows 10 企業版 LTSB (長期維護分支。

>[!TIP]
>有關 LTSC 的最新資訊，請參閱下列常見問題：下一Windows 10長期維護通道 ([LTSC) 發行](https://techcommunity.microsoft.com/t5/windows-it-pro-blog/the-next-windows-10-long-term-servicing-channel-ltsc-release/ba-p/2147232)。

 除了提供延伸維護模型之外，ltSC Windows 10 企業版還提供一個已移除多個Windows環境。 受 LTSC 影響的核心 Surface 體驗包括：

* Windows功能更新，包括增強功能，例如：

  *  在版本 1607 Windows 10版本 1607 中提供的 Direct Ink 和掌心拒絕 (也稱為周年紀念更新) 
  *  改良了在 Windows 10 版本 1703 (也稱為 Creators Update) 

* Surface 應用程式所提供的壓力敏感度設定

* Windows Ink 工作區

* 按鍵觸控優化的盒內應用程式，包括 Microsoft Edge、OneNote、日曆和相機

在 Surface 裝置上使用 Windows 10 企業版 LTSC 環境會導致使用者體驗的不理想，因此您應該避免在使用者想要且預期有進一無二、最新使用者體驗的環境中使用。

LTSC 維護選項是專為裝置類型和案例所設計，其中功能或功能的關鍵屬性永遠不會變更。 範例包括為製造或醫療設備提供電力的系統，或資訊站中的內嵌系統，例如 ATM 或機場票務系統。

>[!NOTE]
>有關維護分支的一Windows，包括 LTSC，請參閱服務[Windows 即服務。](/windows/deployment/update/waas-overview)

一般而言，符合下列準則的裝置視為一般用途裝置，應該使用 Windows 10 專業版 或 Windows 10 企業版 通道維護選項Semi-Annual配對：

* 執行生產力軟體的裝置，例如Microsoft Office

* 使用應用程式Microsoft Store裝置

* 用於一般網際網路流覽的裝置 (例如研究或存取社交媒體) 

選擇在 Surface 裝置Windows 10 企業版 LTSC 版本之前，請考慮下列限制：

* 驅動程式和固件更新並未針對 ltSC 版本Windows 10 企業版測試。

* 如果您遇到問題，Microsoft 支援服務會提供疑難排解協助。 不過，由於 Windows LTSC 的維護性質，問題解決可能會要求裝置升級至較新版本的 Windows 10 企業版 LTSC，或是使用 SAC 維護選項升級至 Windows 10 專業版 或 Enterprise。

* Surface 裝置更換 (例如，根據保固) 更換的裝置，可能含有需要更新裝置驅動程式和固件的硬體元件中的細微變化。 與這些更新的相容性可能需要使用 SAC 維護選項安裝較新版本的 Windows 10 企業版 LTSC 或 Windows 10 專業版或Enterprise更新。

>[!NOTE]
>以特定版本的 Windows 10 企業版 LTSC 進行標準化的組織可能無法採用新一代的 Surface 硬體，例如 Surface Pro 8、Surface Pro X 或 Surface Laptop 4，而不會更新至較新版本的 Windows 10 企業版 LTSC 或Windows 10 專業版或Enterprise。 若要詳細資訊，請參閱生命週期[常見問題 - Windows](/lifecycle/faq/windows#what-are-the-requirements-for-servicing-and-updating-the-windows-10-long-term-servicing-channel--ltsc--)。

在 LTSC Windows 10 企業版的 Surface 裝置將不會收到新功能。 在許多情況下，客戶會要求這些功能以改善 Surface 硬體的可用性和功能。 例如，適用于版本 1703 Windows 10 DPI 應用程式的新改良功能。 在 LTSC 組配置中使用 Surface 裝置的客戶，除非他們更新至新的 Windows 10 企業版 LTSC 版本，或是升級到支援 SAC 維護選項的 Windows 10 版本，否則不會看到改良功能。

裝置可以從 Windows 10 企業版 LTSC 變更為較新版本的 Windows 10 企業版，且支援 SAC 維護選項，而不會因為執行升級安裝而遺失使用者資料。 您也可以利用 Microsoft Deployment Toolkit (MDT) 和 Microsoft Endpoint Configuration Manager 中提供的升級工作順序範本，在多個裝置上執行升級安裝。 若要詳細資訊，請參閱[升級 Surface 裝置Windows 10 Microsoft 部署工具組](upgrade-surface-devices-to-windows-10-with-mdt.md)。
