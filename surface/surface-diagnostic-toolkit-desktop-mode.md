---
title: 在桌面模式中使用商務用 Surface 診斷工具組
description: 如何使用 SDT 來協助貴組織的使用者執行工具，以識別及診斷 Surface 裝置的問題，以及直接從工具提交支援要求。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 7/31/2020
ms.openlocfilehash: 7d09bc70a2e0c882bde9106ee2c241568c1fc991
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154128"
---
# <a name="use-surface-diagnostic-toolkit-for-business-in-desktop-mode"></a>在桌面模式中使用商務用 Surface 診斷工具組

本主題說明如何使用 Surface 診斷工具組 (SDT) 來協助貴組織的使用者執行工具，以找出及診斷 Surface 裝置的問題，以及直接從工具提交支援要求。 

成功執行 SDT 可以快速判斷報告的問題是由硬體失敗或使用者錯誤所導致。 有關 SDT 中支援的 Surface 裝置清單，請參閱 [部署商務用 Surface 診斷工具組](surface-diagnostic-toolkit-business.md)。


1. 指示使用者從軟體) 或網路共用安裝 [SDT](surface-diagnostic-toolkit-business.md#preparing-the-sdt-package-for-distribution) 套件。 安裝之後，就可以引導使用者完成一系列測試。 

2. 從首頁開始，讓使用者輸入問題的描述，然後按一下 **[繼續**，如圖 1 所示。

    ![在桌面圖案中啟動 SDT。](images/sdt-desk-1.png)<br/>
    *圖 1。 桌面圖案中 SDT*

3. 當 SDT 指出裝置有最新更新時，請按一下****[繼續以進一步到可用測試的目錄，如圖 2 所示。

    ![從 SDT 選項選取。](images/sdt1.png)<br/>
    *圖 2. 從 SDT 選項選取*

4. 您可以選擇執行所有診斷測試。 或者，如果您已經懷疑特定問題 ，例如顯示器錯誤或電源問題，請按一下 [選取以從**** 可用的測試選擇，然後按一下 [執行**已**選取，如圖 3 所示。 請參閱下表，瞭解每個測試的詳細資訊。 

    ![選取硬體測試。](images/sdt2.png)<br/>
    *圖 3. 選取硬體測試*

    硬體測試 | 描述
    --- | ---
    電源和電池 |  檢查電源是否運作最佳
    顯示與音效   | 檢查亮度、卡住或死亡圖元、喇叭和麥克風功能
    埠和配件   | 檢查配件、螢幕附加和 USB 功能
    連線性 |  檢查藍牙、無線和 LTE 連接
    安全性    | 檢查安全性相關問題
    觸控   | 檢查觸控相關問題
    鍵盤和觸控 |    檢查整合的鍵盤連接和鍵盤保護蓋
    感應器 | 檢查裝置中不同感應器的功能
    硬體 |  檢查圖形卡和相機等不同硬體元件的問題

5. 所有測試完成後，工具會要求您確認問題是否已修正。 

    ![您的問題已解決嗎？](images/sdt3.png)<br/>
    *圖 3a。 您的問題已解決嗎？*

6. 如果問題尚未解決，或您不知道，您可以選取立即取得協助，以提交支援**票證。** ****
 
    ![提交支援票證。](images/sdt4.png)<br/>
    *圖 3b。 提交支援票證*

<span id="multiple" />

## <a name="running-multiple-hardware-tests-to-troubleshoot-issues"></a>執行多個硬體測試以疑難排解問題

SDT 是設計成可執行一系列測試的互動式工具。 針對每個測試，SDT 會提供指示，摘要說明測試的性質，以及使用者應預期或尋找哪些專案，以便測試成功。 例如，若要診斷顯示器亮度是否正常運作，SDT 會從零開始，將亮度提高至 100%，要求使用者確認亮度是否如預期運作，如**** 圖**** 4 所示。 

針對每一個測試，如果功能無法如預期地執行，且使用者**** 按一下 No，SDT 會產生一份報告，說明可能的原因及疑難排解方法。 

![執行硬體診斷。 ](images/sdt-desk-4.png)
*圖 4.執行硬體診斷*

1. 如果亮度如預期從 0-100% 成功調整，請引導使用者按一下 [ **是** ，然後按一下 [ **繼續**> 。 
2. 如果亮度無法如預期從 0-100% 調整，請指示使用者按一下 **[否** ，然後按一下 [ **繼續**。 
3. 引導使用者完成其餘的測試。 完成後，SDT 會自動提供報表的摘要，包括任何硬體問題的可能原因，以及解決指南。


### <a name="repairing-applications"></a>修復應用程式

SDT 可讓您診斷及修復可能導致問題的應用程式，如圖 5 所示。

![正在進行修復。 ](images/sdt-desk-5.png)
*圖 5.進行修復*
<span id="logs" />

### <a name="generating-logs-for-analyzing-issues"></a>產生記錄以分析問題 

SDT 針對應用程式、驅動程式、硬體和作業系統問題提供大量啟用記錄功能的診斷支援，如圖 6 所示。

![產生記錄。 ](images/sdt-desk-6.png)
*圖 6.產生記錄*

<span id="detailed-report" />

### <a name="generating-detailed-report-comparing-device-vs-optimal-configuration"></a>產生詳細報表比較裝置與優化組配置

根據記錄，SDT 會針對軟體與固件問題產生報告，您可以將這些問題儲存到偏好的位置。

## <a name="related-topics"></a>相關主題

- [使用商務用 Surface 診斷工具套件執行命令列應用程式主控台](surface-diagnostic-toolkit-command-line.md)
