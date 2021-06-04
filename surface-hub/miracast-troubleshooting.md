---
title: 疑難排解 Surface Hub 上的 Miracast
description: 了解如何使用 Surface Hub 上的 Miracast 解決問題。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: 96c7c42fe0176f275a8657165d88bf447e57772b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10834192"
---
# 疑難排解 Surface Hub 上的 Miracast

Surface Hub 透過 Miracast 通訊協定支援無線投影。 大部分無線顯示器和可用的介面卡目前使用 Miracast 原始的實作。 Surface Hub 使用稍有不同的 Miracast 版本稱為 **Miracast Autonomous Group Owner (AGO)**。 當無線投影至 Surface Hub 失敗時的常見疑難排解步驟是測試投影到另一個無線顯示器或介面卡。 但是，在大部分情況下，這些裝置不使用 Miracast AGO 前，並且不以和 Surface Hub 相同的方式處理無線投影。

在傳統 Miracast 中，投影裝置將連接支援 Miracast 的監視器設定的存取點，然後監視器將會使用投影裝置的網路通道，傳送流量資料回到投影裝置。 Miracast AGO 是兩步驟連線程序：

- 第一個步驟是使用 2.4 GHz 的初始連線。 
- 該初始交握之後，投射裝置會使用監視器上的無線通道設定傳送流量至監視器。 如果 Surface Hub 已連接到 Wi-Fi 網路的存取點，將會使用相同的通道做為連接的網路，否則會使用 [設定] 的 Miracast 通道。

通常 Miracast 連到 Surface Hub 的問題有兩種類型：[連線](#connect-issues)和[效能](#performance-issues)。 在任何一種情況下，最好在 Surface Hub 的位置中取得無線網路活動的一般圖片。 執行網路掃描工具會顯示可用的網路和環境中通道使用量。

## 連接問題

請確定 Surface Hub 上 [設定] 中已啟用 Miracast 和 Wi-Fi。 

如果您在執行掃描網路，您應該會看到 Surface Hub Miracast 被列示為一個存取點。 如果 Surface Hub 的 Miracast 網路出現在掃描上，但您無法將它顯示為可用的裝置，您可以嘗試調整 Surface Hub 所使用的 Miracast 通道。 

當 Surface Hub 連接 Wi-Fi 網路時，它會使用相同的通道設定做為其 Miracast 存取點的 Wi-Fi 存取點。 基於疑難排解之目的，中斷 Surface Hub 與任何 Wi-Fi 網路的連線 (但保持 Wi-Fi 連線)，如此您便可以控制 Miracast 所使用的通道。 您可以手動選取設定中的 Miracast 通道。 您需要在變更後重新啟動 Surface Hub。 一般而言，您會想要使用未顯示網路掃描之龐大使用量的通道。

連接問題也可能是連線裝置的問題所造成。 如果投影裝置正在執行 Windows，它應該會是 Miracast 完整支援的 Windows 8.1 或更新版本。 疑難排解時，再次中斷投影裝置與任何 Wi-Fi 網路的連線。 這將會消除存取點通道和 Surface Hub 上設定的 Miracast 頻道之間的任何通道切換。 此外，部分群組原則和防火牆設定可能繫結 Wi-Fi 網路。

### 檢查驅動程式

最好也能確定最新驅動程式和投影裝置上安裝的更新。 在 [裝置管理員] 中，開啟 Wi-Fi 介面卡和視訊介面卡，並檢查是否有更新的驅動程式版本。 我們強烈建議 Surface Pro 3 和 Surface Pro 4 若在較舊的 Wi-Fi 驅動程式上時使用 [Hotfix 3120232](https://support.microsoft.com/help/3120232/poor-wireless-performance-on-5-ghz-connections-on-surface-pro-3-and-surface-3)。 

### 檢查是否有 Miracast 支援

接著，確定裝置有支援 Miracast。 

1. 按下 Windows 鍵 + R 鍵並輸入 `dxdiag`。 
2. 按一下 [儲存所有資訊]。 
3. 開啟已儲存的 dxdiag.txt 並尋找 **Miracast**。 它應該會顯示 **/[對於 HDCP 可用/]**。 
    
### 檢查防火牆
    
Windows 防火牆可以封鎖 Miracast 流量。 最簡單的測試是停用防火牆及測試投影。 如果 Miracast 搭配防火牆停用，請新增例外

    C:\Windows\System32\WUDFHost.exe
    Allow In/Out connections for TCP and UDP, Ports: All.

### TPM 群組原則設定

在加入網域的裝置上，群組原則也會封鎖 Miracast。 

1. 使用 Windows 鍵 + R 鍵並輸入 `rsop.msc`，以執行 **/[原則結果組/]** 嵌入式管理單元。 這將會顯示目前套用到電腦的原則。 
2. 檢閱 **/[電腦設定/]** > **/[Windows 設定/]** > **/[安全性設定/]** > **/[無線網路 (IEEE 802.11) 原則/]**。 應該會有無線原則的設定。 
3. 按兩下無線原則設定，將會出現對話方塊。 
4. 開啟 **/[網路權限/]** 索引標籤，並選取 **/[允許每個人建立所有使用者的設定檔/]**。

### 檢查事件記錄

最後要檢查的地方是事件記錄。 Miracast 事件將記錄到 **Wlanautoconfig**。 這對於 Surface Hub 和投影裝置皆為真。 如果您匯出 Surface Hub 記錄，您可以在 [ **WindowsEventLog** ] 資料夾中，查看 Surface Hub 的 Wlanautoconfig。 事件記錄中的錯誤可以提供有關連線失敗位置的一些詳細資訊。

## 效能問題

連接無線投影後，可能會造成效能延遲問題。 這通常是整體通道飽和或是造成通道切換的飽和結果。 

對通道飽和，請參考網路掃描，然後嘗試使用較少流量的通道。

當 Wi-Fi 介面卡需傳送流量至多個通道時，造成通道切換。 某些通道支援動態頻率選擇 (DFS)。 DFS 可用於通道 49 至 148。 有些 Wi-Fi 驅動程式會顯示連接 DFS 通道時效能不佳。 如果發現連接到 DFS 通道時 Miracast 效能不佳，請嘗試投影在非 DFS 通道上。 Surface Hub 和投影裝置都應該使用非 DFS 通道。

如果 Surface Hub 和投影裝置均連接 Wi-Fi，但不同的通道使用不同的存取點，這會強制 Surface Hub 和投射裝置在連接 Miracast 時進行通道切換。 這會造過 Wi-Fi 無線投影不佳和網路效能不穩定。 不只無線投影效能被影響，通道切換將會影響所有無線流量效能。 

如果投影裝置連接與 Surface Hub 針對 Miracast 使用之通道不同的通道的 Wi-Fi 網路，也會發生通道切換。 因此，最佳做法是將 Surface Hub 的 Miracast 通道設定為與最常使用的存取點相同的通道。 

如果環境中有多個 Wi-Fi 網路或存取點，有些通道切換是無法避免的。 這可藉由確保所有 Wi-fi 驅動程式維持在最新狀態而獲得解決。

##  <a name="contact-support"></a>連絡客戶支援

如果您有任何疑問或需要協助，您可以[建立支援要求](https://support.microsoft.com/supportforbusiness/productselection)。
