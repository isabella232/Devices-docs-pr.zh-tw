---
title: Surface Book 3 GPU 技術概述
description: 本文提供在 Surface Book 3 模型之間的 GPU 功能技術評估。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 5/06/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: a3bfe6eec313c9cd9a38f966a1bed46fbc1ca92b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831195"
---
# Surface Book 3 GPU 技術概述

## 簡介

表面書籍3是功能最強大的 Surface 膝上型電腦，可將完整新式的計算和圖形功能整合成其著名的可分離形式。  由四核 Gen 英特爾®核心™ i7 和 NVIDIA® Quadro RTX™3000圖形處理單元（GPU）在15寸模型上，Surface Book 3 會提供多種配置供消費者、創造性專業人員、架構師、工程師及資料科學家使用。 本文說明在 Surface Book 3 的13英寸及15寸模型之間的 GPU 配置之間的主要差異。

在 Surface Book 3 模型中有一個重要的區別，就是 GPU 配置。 除了內置於所有模型中的整合式英特爾 GPU 之外，除了入門級 13.5-寸核心 i5 裝置之外，還有一個具有最大 Q 設計的離散 NVIDIA GPU，其中包含可針對行動裝置規格優化能源效率的功能。

在鍵盤基底內建，額外的 NVIDIA GPU 提供了先進的圖形轉譯功能，且有兩種主要的設定： GeForce®® GTX 為消費者或創造性專業人員提供的 1650/1660 Ti，以及針對需要先進圖形或深入學習功能之其他商務專業人員的 Quadro RTX 3000。 本文也說明如何透過指定哪些 app 應該使用整合 iGPU 與離散 NVIDIA GPU，來優化 Gpu 的 app 利用率。

## Surface Book 3 Gpu

本節說明在 Surface Book 3 模型之間的整合和離散 Gpu。 如需所有模型的配置詳細資料，請參閱[附錄 A： Surface Book 3 sku](#)。

### 英特爾虹彩™加上圖形

所有 Surface Book 3 模型所含的整合 GPU （iGPU）結合了較寬的圖形引擎和重新設計的記憶體控制器（支援 LPDDR4X）。 在大部分 Surface Book 3 模型上安裝為次要 GPU，英特爾虹彩加上圖形函數是核心 i5、13.5 寸模型中的單數 GPU。 雖然在 Surface Book 3 行中 nominally 進入層級裝置，但它提供高級圖形功能，讓消費者、hobbyists 和線上製作者執行最新的生產力軟體（例如 Adobe 創意雲端），或在1080p 中欣賞遊戲標題。  

### NVIDIA GeForce GTX 1650

NVIDIA GeForce GTX 1650 （含最大的 Q 設計）可提供核心流式處理多處理器的主要升級，以更有效率地處理新式遊戲的複雜圖形。 其浮點數和整數運算的並存執行會提高現代遊戲的計算繁重工作負載的效能。 新的整合記憶體架構，其前置任務的快取都可在複雜的新式遊戲中取得較佳的效能。 新的陰影改良功能改善效能、增強影像品質，並提供新的幾何複雜性層次。

### NVIDIA GeForce GTX 1660 Ti

與 GeForce GTX 1650 相比，速度較快的 GeForce GTX 1660 Ti 提供了 Surface Book 3 的其他效能改善，包括新的和升級的 NVIDIA 編碼器，讓消費者、玩家、live streamers 和創造性的專業人員都能更好。

您有 6 GB 的 GDDR6 圖形記憶體，配有 NVIDIA GeForce GTX 1660 TI 的 Surface Book 3 模型，在執行最新式的標題或 livestreaming 時，就能提供最佳的商業生產力軟體和流行的遊戲速度。 有了選用的 2 TB SSD （僅適用于美國），15英寸模型（含 GeForce GTX 1660 Ti）可提供任何 Surface Book 3 裝置的最大儲存空間。

### NVIDIA Quadro RTX 3000

NVIDIA Quadro RTX 3000 可為專業使用者提供幾項重要功能： ray 追蹤轉譯與 AI 加速，以及高級圖形與計算效能。 30 RT 核、240 tensor 核心，以及 6 GB 的 GDDR6 圖形記憶體可支援多種高級工作負載，包括工作中工作流程、3D 內容建立、高級影片編輯、專業廣播和多個 app 工作流程。 企業級硬體和軟體支援整合部署工具，以最大化正常運作時間並最小化 IT 支援需求。 針對世界上最先進的軟體認證，Quadro 驅動程式已針對專業應用程式進行優化，且經過調整、測試和驗證，以提供應用程式認證、企業級穩定性、可靠性、可用性，以及支援延伸產品的可用性。
 

## 在 Surface Book 3 中比較 Gpu

NVIDIA Gpu 可為使用者提供出色的遊戲、即時資料流及內容建立效能。 GeForce GTX 產品非常適合玩家和內容製作者。 Quadro RTX 產品以專業使用者為目標，在遊戲和內容建立時提供出色的效能，同時也新增下列功能：

- 光線追蹤和 AI 的 RTX 加速。 這樣就能以實際精確的陰影、反射及 refractions 來轉譯電影品質、擁有照片的物件和環境。  而且其硬體加速的 AI 功能意味著在流行的應用程式中，高級 AI 的功能，執行速度會比以往更快。
- 企業級的硬體、驅動程式和支援，以及 ISV app 認證。
- IT 管理功能包括可協助最大化正常運作時間並最小化 IT 支援需求的其他專用企業版管理工具。

 除非您在高級工程、設計、架構或資料科學專業人員的排名中計算自己，否則，配有 NVIDIA GeForce 圖形功能的 Surface Book 3 將可能符合您的需求。 相反地，如果您已在內或 aspiring 進行加入，即需要以筆記本形式提供高度高級圖形功能的職業（可讓您從任何位置進行工作），而 Surface Book 3 （含 Quadro RTX 3000）值得慎重考慮。 若要深入瞭解，請參閱 Surface Book 3 Quadro RTX 3000 技術概覽。
 
**表 1. Surface Book 3 上的離散 Gpu**

|                      | **GeForce GTX 1650**                   | **GeForce GTX 1660 Ti**                            | **Quadro RTX 3000**                                                                                       |
| -------------------- | -------------------------------------- | -------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **目標使用者**     | 玩家、hobbyists 及線上創意者  | 玩家、創造性的專業人員，以及線上創意者 | 創造性的專業人員、架構師、工程師、開發人員、資料科學家                                |
| **工作流程**        | 圖形設計<br>攝影<br>影片 | 圖形設計<br>攝影<br>影片             | Al 工作流程  <br>App 認證<br>高解析度影片<br>專業廣播<br>多重 app 工作流程 |
| **主要應用程式**         | Adobe 創意套件                   | Adobe 創意套件                               | Adobe 創意套件<br>Autodesk AutoCAD<br>Dassault Systemes SolidWorks                                  |
| **GPU 加速** | 影片與影像處理             | 影片與影像處理                         | Ray 追蹤 + AI + 6K 影片<br>Pro 廣播功能<br>企業支援                            |


**表 2. Surface Book 3 上的 GPU 技術規格**

|                                                          | **GeForce GTX 1650** | **GeForce GTX 1660 Ti** | **Quadro RTX 3000** |
| -------------------------------------------------------- | -------------------- | ----------------------- | ------------------- |
| **NVIDIA CUDA 處理核心**                         | 1024                 | 1536                    | 1920                |
| **NVIDIA Tensor 核心**                                  | 否                   | 否                      | 240                 |
| **NVIDIA RT 核心**                                      | 否                   | 否                      | 為期                  |
| **GPU 記憶體**                                           | 4 GB                 | 6 GB                    | 6 GB                |
| **記憶體頻寬（GB/秒）**                            | 最多112            | 最多288               | 最多288           |
| **記憶體類型**                                          | GDDR5                | GDDR6                   | GDDR6               |
| **記憶體介面**                                     | 128位              | 192位                 | 192位             |
| **大幅提升時鐘 MHz**                                      | 1245                 | 1425                    | 1305                |
| **基底時鐘（MHz）**                                     | 1020                 | 1245                    | 765                 |
| **即時光線追蹤**                                | 否                   | 否                      | 是                 |
| **AI 硬體加速**                             | 否                   | 否                      | 是                 |
| **硬體編碼器**                                     | 是                  | 是                     | 是                 |
| **遊戲就緒驅動程式（GRD）**                              | 是 <sup> 1</sup>                                   | 是 <sup> 1</sup>          |是 <sup> 2</sup> 
| **Studio 驅動程式（SD）**                                   | 是 <sup> 1</sup>            | 是 <sup> 1</sup>                 | 是 <sup> 1</sup>           |
| **企業的最佳驅動程式（ODE）**                  | 否                   | 否                      | 是            |
| **Quadro 新功能驅動程式（QNF）**                      | 否                   | 否                      | 是            |
| **Microsoft DirectX 12 API、Vulkan API、開啟總帳4。6**    | 是                  | 是                     | 是                 |
| **高頻寬數位內容保護（HDCP）2。2** | 是                  | 是                     | 是                 |
| **NVIDIA GPU 提升**                                     | 是                  | 是                     | 是                 |


 1. *建議執行*
 2.  *支援*

## 在 Surface Book 3 上優化電源和效能

Windows 10 包含具有效能滑杆的節電模式，可讓您最大化 app 效能（以向右滑動），或保持電池使用時間（向左滑動）。 Surface Book 3 實現此功能 algorithmically，以優化下列元件的功率和效能：

- CPU 能源效率寄存器（英特爾速度變化技術）及其他 SoC 調整參數，以獲得最佳效能。
- 含四種模式的風扇最大 RPM：安靜、額定、效能和最大值。
- 處理器電源上限（PL1/PL2）。
- 處理器 IA Turbo 限制。

根據預設，當電池低於20% 時，節電模式會調整設定以延長電池使用時間。 連線至 power 時，Surface Book 3 預設為「最佳效能」設定，以確保應用程式在所有 i7 Surface Book 3 系統上的次要 NVIDIA GPU 上都以高效能模式執行。

使用預設設定是作為膝上型電腦或在平板電腦或畫室式模式中分離時的最佳效能。 您可以選取工作列最右邊的電池圖示來存取節電模式。

### 遊戲模式

Surface Book 3 包含新的遊戲模式，可在啟動時自動選取 [最佳效能] 設定。

### 安全分離

在 Surface Book 3 中新增新功能，可讓您在 app 使用 GPU 時中斷連線。 對於支援的應用程式（例如*Warcraft*），您的工作會移至 iGPU。

### 修改 app 設定，以永遠使用特定的 GPU

您可以在節能，但仍支援內建的英特爾圖形及功能更強大的獨立 NVIDIA GPU，並將 GPU 與特定 app 建立關聯。 根據預設，Windows 10 會自動選擇適當的 GPU，並將要求較高的 app 指派給離散的 NVIDIA GPU。 在大部分的情況下，不需要手動調整這些設定。 不過，如果您在使用圖形化苛刻的 app 時，經常會從鍵盤基底分離並重新附加顯示器，您通常需要在分離前先關閉 app。 若要啟用應用程式的連續使用，而不需要在每次拆下或重新附加顯示器時都關閉該 app，您可以將它指派給整合式 GPU，但不會降低圖形效能。  

在某些情況下，Windows 10 可能會指派要 iGPU 的圖形化苛刻 app。例如，如果應用程式未針對混合式圖形進行完全優化。 若要修正此情況，您可以手動將 app 指派給離散的 NVIDIA GPU。

**若要使用自訂的每個 GPU 選項來設定 app：**  

1. 移至 [**設定**  >  **系統**  >  **顯示**]，然後選取 [**圖形設定**]。

    1. 針對 Windows 桌面程式，請選擇 [**傳統 App**  >  **流覽]** ，然後找出程式。
    2. 如果是 UWP app，請選擇 [**通用 app** ]，然後從下拉式清單中選取 app。

2. 選取 [**新增**]，在清單上為您所選的程式建立新專案，選取選項以開啟圖形規格，然後選取您想要的選項。

   ![選取 [省電] 或 [高效能 GPU] 選項](./images/graphics-settings2.png)

3. 若要確認每個應用程式所使用的是哪些 GPU，請開啟 [**工作管理員]，** 選取 [**效能]，** 然後查看 [ **gpu 引擎**] 欄。


## 附錄 A： Surface Book 3 Sku

| **顯示器**   | **處理者**                     | **GPU**                                                                                              | **RAM**    | **儲存體** |
| ------------- | --------------------------------- | ---------------------------------------------------------------------------------------------------- | ---------- | ----------- |
| **13.5-寸** | 四核 10 Gen 核心 i5-1035G7 | 英特爾虹彩™加上圖形                                                                            | 16 LPDDR4x | 256 GB      |
| **13.5-寸** | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA GeForce GTX 1650。 含 4GB GDDR5 圖形記憶體的 Max-Q 設計    | 16 LPDDR4x | 256 GB      |
| **13.5-寸** | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA GeForce GTX 1650。 含 4GB GDDR5 圖形記憶體的 Max-Q 設計    | 32 LPDDR4x | 512 GB      |
| **13.5-寸** | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA GeForce GTX 1650。 含 4GB GDDR5 圖形記憶體的 Max-Q 設計    | 32 LPDDR4x | 1 TB        |
| **15英寸**   | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA GeForce GTX 1660 Ti。 最大-Q 設計與 6GB GDDR6 圖形記憶體 | 16 LPDDR4x | 256 GB      |
| **15英寸**   | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA GeForce GTX 1660 Ti。 最大-Q 設計與 6GB GDDR6 圖形記憶體 | 32 LPDDR4x | 512 GB      |
| **15英寸**   | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA GeForce GTX 1660 Ti。 最大-Q 設計與 6GB GDDR6 圖形記憶體 | 32 LPDDR4x | 1 TB        |
| **15英寸**   | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA GeForce GTX 1660 Ti。 最大-Q 設計與 6GB GDDR6 圖形記憶體 | 32 LPDDR4x | 2 TB        |
| **15英寸**   | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA Quadro RTX 3000。 最大-Q 設計與 6GB GDDR6 圖形記憶體     | 32 LPDDR4x | 512 GB      |
| **15英寸**   | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩加上圖形<br>NVIDIA Quadro RTX 3000。 最大-Q 設計與 6GB GDDR6 圖形記憶體     | 32 LPDDR4x | 1 TB        |

> [!NOTE]
> 2TB SSD 僅適用于美國： Surface Book 3 15 "與 NVIDIA GTX 1660Ti

## 摘要

針對效能建立，Surface Book 3 包含不同的 GPU 設定，以符合特定的工作負載和使用需求。 整合式英特爾虹彩圖形 GPU 在進入層級核心 i5 裝置上是唯一的 GPU，另一種是所有其他模型上的次要 GPU。 GeForce GTX 1650 的主要升級核心流式處理多處理器，以更有效率地執行複雜的圖形。 GeForce GTX 1660 Ti 的快速協助工具提供 Surface Book 3，讓客戶、玩家、live streamers 及創造性專業人員更能充分發揮效能。 Quadro RTX 3000 可為專業版使用者解除許多重要的功能： ray 追蹤轉譯與 AI 加速，以及高級圖形與計算效能。


## 深入了解

- [Surface Book 3 Quadro RTX 3000 技術概述](surface-book-quadro.md)
- [商務用 Surface](https://www.microsoft.com/surface/business)
