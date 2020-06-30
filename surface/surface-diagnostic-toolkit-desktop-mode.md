---
title: 在桌面模式中使用商務用 Surface 診斷工具組
description: 如何使用 SDT 來協助貴組織中的使用者執行該工具，以找出並診斷 Surface 裝置的問題。
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
ms.openlocfilehash: 9e6b34a8d34081fc12cab4851104f0b67c3dfea4
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831191"
---
# 在桌面模式中使用商務用 Surface 診斷工具組

本主題說明如何使用 Surface 診斷工具箱（SDT），協助貴組織中的使用者執行該工具，以找出並診斷 Surface 裝置的問題。 成功執行 SDT 可以快速判斷問題是否是由失敗的硬體或使用者錯誤所導致。 如需在 SDT 中支援的 Surface 裝置清單，請參閱適用于[企業的部署表面診斷工具](surface-diagnostic-toolkit-business.md)組。


1. 引導使用者從軟體發佈點或網路共用安裝[SDT 套件](surface-diagnostic-toolkit-business.md#create-custom-sdt)。 安裝完成後，您就可以透過一系列測試來引導使用者。 

2. 從首頁開始，讓使用者輸入問題的描述，然後按一下 [**繼續**]，如圖1所示。

    ![在桌面圖案中開始 SDT ](images/sdt-desk-1.png)
 *圖1。桌面圖案中的 SDT*

3. 當 SDT 代表裝置有最新的更新時，請按一下 [**繼續**] 以移至可用測試的目錄，如圖2所示。

    ![從 SDT 選項中選取 ](images/sdt-desk-2.png)
 *圖2。從 SDT 選項中選取*

4. 您可以選擇執行所有診斷測試。 或者，如果您已懷疑某個特定問題（例如出現錯誤的顯示或電源問題），請按一下 [**選取**] 以從可用的測試中進行選擇，然後按一下 [**執行已選取**]，如圖3所示。 如需每個測試的詳細資料，請參閱下表。 

    ![選取 [硬體測試 ](images/sdt-desk-3.png)
 *圖 3]。選取硬體測試*

    硬體測試 | 描述
    --- | ---
    電源與電池 |  檢查電源運作最佳
    顯示與音效   | 檢查亮度、滯留或死圖元、喇叭和麥克風運作
    埠與附屬配件   | 檢查附件、螢幕附加和 USB 運作
    連線性 |  檢查藍牙、無線和 LTE 連線性
    安全性    | 檢查安全性相關問題
    觸控   | 檢查觸控相關問題
    鍵盤和觸控 |    檢查整合式鍵盤連接並輸入封面
    感應器 | 檢查裝置中不同感應器的運作方式
    硬體 |  檢查不同硬體元件（例如圖形卡和相機）的問題





<span id="multiple" />

## 執行多個硬體測試以疑難排解問題

SDT 是以互動式工具的方式設計，可執行一系列測試。 在每個測試中，SDT 都提供說明測試本質的指示，以及使用者應該預期或尋找哪些專案，才能成功進行測試。 例如，若要診斷顯示器亮度是否正常運作，SDT 會從零開始，並將亮度增加至100%，要求使用者確認是否已正常運作**Yes** ，如**No**圖4所示。 

針對每個測試，如果功能無法如期運作，而使用者按一下 [**否**]，SDT 就會產生可能的原因，以及疑難排解的方法。 

![執行硬體診斷 ](images/sdt-desk-4.png)
 *圖4。執行硬體診斷*

1. 如果亮度順利地從0-100% 調整成預期，請讓使用者按一下 **[是]** ，然後按一下 [**繼續**]。 
2. 如果亮度無法如期調整0-100%，請直接將使用者按一下 [**否**]，然後按一下 [**繼續**]。 
3. 視需要引導使用者完成剩餘的測試。 完成後，SDT 會自動提供報告的高層次摘要，包括任何硬體問題的可能原因，以及解決方法的指導方針。


### 修復應用程式

SDT 可讓您診斷並修復可能造成問題的應用程式，如圖5所示。

![執行修復 ](images/sdt-desk-5.png)
 *圖5。執行修復*
<span id="logs" />

### 產生記錄來分析問題 

SDT 可跨應用程式、驅動程式、硬體及作業系統問題提供廣泛的記錄啟用診斷支援，如圖6所示。

![產生記錄 ](images/sdt-desk-6.png)
 *圖6。產生記錄*

<span id="detailed-report" />

### 產生與最佳配置對比的詳細報告

根據記錄，SDT 會針對軟體及固件的問題產生報告，您可以將這些問題儲存至預先推薦的位置。

## 相關主題

- [使用命令執行商務用 Surface 診斷工具組](surface-diagnostic-toolkit-command-line.md)

