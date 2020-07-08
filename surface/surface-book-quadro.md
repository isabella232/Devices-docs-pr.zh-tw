---
title: Surface Book 3 Quadro RTX 3000 技術概觀
description: 本文將說明使用 Nvidia Quadro RTX 3000 的高級功能，在商務用15寸模型中選取 Surface Book 3，並包含 ISV 測試應用程式的相關資訊。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 7/02/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: 52de90847d85698cba25cc511a4c6eda327c810d
ms.sourcegitcommit: 1b673d9d3240d6217b36fcc5fea53c23ab8cf367
ms.contentlocale: zh-TW
ms.lasthandoff: 07/07/2020
ms.locfileid: "10857580"
---
# Surface Book 3 Quadro RTX 3000 技術概觀

NVIDIA® Quadro RTX™ 3000 GPU 的 Surface Book 3，專為需要即時轉譯、AI 加速、高級圖形及計算效能的專業人員建立。 Quadro RTX 3000 基本會變更您可以使用的新 Surface Book （3）執行的動作：

- **Ray 追蹤**-在使用 30 RT 核心來進行硬體加速的 Ray 追蹤前，產生精美的轉譯、設計和動畫速度。
- **人工智慧**-使用 GPU 加速 AI 的 240 Tensor 核心版，移除重複、繁瑣的工作及計算密集型作業。
- **先進的圖形和計算技術**在您的最高效能中使用非凡的速度和互動，並以 1920 CUDA 核心及 6GB GDDR6 記憶體來計算工作負載。

## 企業成績方案

針對商業客戶而言，Quadro RTX 3000 提供了一種完全專業的方案，可結合加速的 ray 追蹤和深入的學習功能，以及整合的企業層級管理和支援方案。 Quadro 驅動程式是透過領先的 Isv 來測試和認證，100以提供額外的品質保證，以驗證穩定性、可靠性和效能。
 
Quadro 包含專為 Quadro RTX 3000 遠端系統管理 Surface Book 3 裝置的專用企業工具。 IT 管理員可以遠端設定圖形系統、儲存/還原配置、連續監視圖形系統，並視需要執行遠端疑難排解。 這些功能以及部署工具可協助最大化正常運作時間並將 IT 支援需求降至最低。
 
NVIDIA 開發並維持企業（ODE）的 Quadro 最佳驅動程式，這些驅動程式已經過調整、測試和驗證，以提供企業級的穩定性、可靠性、可用性，以及支援延伸產品的可用性。 每個驅動程式版本都涉及超過2000名使用專業應用程式測試套件與測試案例，以及 WHQL 認證的測試人員數。 系統會持續監視安全威脅，併發行定期安全更新，以防範新探索到的漏洞。 此外，透過 Windows Update 發行之前，Quadro 驅動程式也會透過 Surface 工程進行額外的測試層。
 

## 專為計算密集型工作負載所打造

Surface Book 3 （含 Quadro RTX 3000）可提供任何 Surface 膝上型電腦的最佳圖形效能，讓高級專業人員能隨時隨地進行工作。
 
- **創意專業人員，例如設計人員與 animators。** Quadro RTX 可透過 Turing 優化的 ray 追蹤 Api （例如 NVIDIA OptiX、Microsoft DXR 和 Vulkan）來啟用即時電影品質轉譯。
- **使用大型、複雜電腦輔助設計（CAD）模型和元件的架構師和工程人員。** RTX 平臺的功能是新的 NGX SDK，可將功能強大的 AI 功能 infuse 至視覺應用程式。 這能透過智慧操作來釋放影像的時間和資源、重複執行的工作自動化，以及優化計算密集型程式。
- **跨製造業、媒體和娛樂、內科及其他行業的軟體發展人員。** Quadro RTX 利用業界領先的軟體 Sdk 和 Api，透過光線追蹤、深入學習及點陣化功能來加快應用程式開發。
- **資料科學家使用 Tensor 核心與 CUDA 核心，以加速計算密集型工作與其他深入學習作業。** 透過使用感應器、增加連線能力和深入瞭解，研究人員與開發人員可以讓您從自治機動車到科學研究等所有專案啟用 AI 應用程式。

 
**表 1. Quadro RTX 3000 效能功能**

| **元件**                                       | **說明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| RT 核心                                            | 專用的硬體式射線式 ray 追蹤技術可讓 GPU 以實際精確的陰影、反射及 refractions 來轉譯電影品質、擁有照片的物件和環境。  即時 ray 追蹤引擎可與 NVIDIA OptiX、Microsoft DXR 和 Vulkan Api 搭配使用，以提供更多的真實感，遠遠超出使用傳統轉譯技術所能達到的程度。 RT 核心使用少量的射線 casted 穿過圖元，加速限制式大量階層（BVH）遍歷和光線轉換函數。                                     |
| 增強的 tensor 核心                               | 混合式精確度核心專門針對深入學習矩陣演算法而構建，提供與前代相比的訓練的 8x TFLOPS。  Quadro RTX 3000 使用 240 Tensor 核心;每個 Tensor 核心會針對每個時鐘執行64浮點數融合式乘法-add （FMA）運算，每個流式處理多處理器（SM）會在每個時鐘上執行總共1024個浮點運算。 除了支援 FP16/FP32 矩陣運算之外，新的 Tensor 核心新增了 INT8 （每個時鐘2048的整數運算），以及適用于矩陣運算的實驗 INT4 和 INT1 （二進位）精確度模式。 |
| Turing 優化的軟體                           | 深入學習架構（例如 Microsoft 認知工具（CNTK）、Caffe2、MXNet、TensorFlow 及其他人，提供極快的訓練時間及更高的多重節點訓練效能。 GPU 加速文件庫（例如 cuDNN、cuBLAS 和 TensorRT）可提供較高的效能，以深入瞭解學習與高效能計算（HPC）應用程式。                                                                                                                                                                                           |
| NVIDIA CUDA 平行計算平臺             | 從本機執行標準程式設計語言（例如，C/c + + 和 Fortran），以及 Api （例如 OpenCL、OpenACC 和直接計算），以加速諸如光線追蹤、影片和影像處理等技術，以及計算流體的動態。                                                                                                                                                                                                                                                                                                                                        |
| 高級流式處理多處理器（SM）架構 | 合併的共用記憶體與 L1 快取會大大改善效能，同時簡化程式設計並減少達到最佳應用程式效能所需的調整。                                                                                                                                                                                                                                                                                                                                                                                                |
| 高效能 GDDR6 記憶體             | Quadro RTX 3000 功能6GB 的框架緩衝區，讓它成為處理大型資料集與延遲區分應用程式的理想平臺。                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| 單一指令、多個執行緒（SIMT）          | 新的獨立執行緒排程功能可在小型作業間共用資源，以進行更精細的同步處理及在平行線程之間共同作業。                                                                                                                                                                                                                                                                                                                                                                                                             |
| 混合式精確度計算                           | 16位浮點精度計算可讓您訓練及部署較大的神經網路。 透過獨立的並行整數和浮點數據路徑，Turing SM 能使用混合式計算和定址計算來更有效率地處理工作負載。                                                                                                                                                                                                                                                                                          |
| 動態負載平衡                              | 提供圖形的 GPU 資源的動態分配功能，並視需要計算工作，以最大化資源利用率。                                                                                                                                                                                                                                                                                                                                                                                                                                                                |
| 計算搶佔                                  | 指令等級的搶佔可提供更精細的計算任務控制，以避免長時間執行的應用程式不需要獨佔系統資源或超時。                                                                                                                                                                                                                                                                                                                                                                                            |
| H-p、.H 265 及 HEVC 編碼/解碼引擎         | 使用兩個專用的 .H 和 HEVC 編碼引擎，以及與 3D/計算管線無關的專用解碼引擎，來實現轉碼、視頻編輯及其他編碼應用程式的即時效能。                                                                                                                                                                                                                                                                                                                                        |
| NVIDIA GPU 提升4。0                                |  在不超過 GPU 的 power 和導熱信封的情況下，自動最大化應用程式的效能。  將應用程式保持在較高溫度閾值以內，然後再移到第二溫度設定基礎時鐘。                                                                                                                                                                                                                                                                                               |

 **表 2. Quadro RTX 技術規格**

| **元件**                                              | **說明** |
| ---------------------------------------------------------- | --------------- |
| NVIDIA CUDA 處理核心                               | 1920           |
| NVIDIA RT 核心                                            | 為期              |
| Tensor 核心                                               | 240             |
| GPU 記憶體                                                 | 6 GB            |
| 記憶體頻寬                                           | 288 Gbps        |
| 記憶體類型                                                | GDDR6           |
| 記憶體介面                                           | 192位         |
| TGP 最大功耗                                  | 65W             |
| 顯示埠                                               | 1.4             |
| OpenGL                                                     | 4.6             |
| 著色器模型                                               | 5.1             |
| DirectX                                                    | 12.1            |
| PCIe 產生                                            | 3               |
| 單精確度浮點效能（TFLOPS，峰值） | 5.4             |
| Tensor 效能（頂端、峰值）                            | 42.9            |
| NVIDIA FXAA/TX AA 消除鋸齒                             | 是             |
| 影片的 GPU 直接                                       | 是             |
| Vulkan 支援                                             | 是             |
| NVIDIA 3D 視覺視覺專業版                                       | 是             |
| NVIDIA Optimus                                             | 是             |

 
## & app 加速的 ISV 測試

如表格3所示，Surface Book 3 （含 Quadro RTX 3000）是由主要的 Isv 進行測試和核准，並能在專業應用程式之間提供極快的加速。 SPECview perf 13 基準測試結果比較 Surface Book 3 15-英寸與 nvidia Quadro RTX 3000，以及使用 NVIDIA GeForce GTX 1060 裝置的 Surface Book 2 15-寸。

**表 3. 使用 Quadro RTX 3000 在 Surface Book 3 上 & 應用程式加速進行 ISV 測試**

| **App**                                             | **說明**                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| --------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Adobe Dimension**                                 | **Adobe-在 Surface Book 3 中使用 Quadro RTX 3000 進行測試及核准**<br><br>-RTX-加速光線追蹤功能可為2D 演出者和設計工具提供全面的3D 轉譯。                                                                                                                                                                                                                                                                                                             |
| **Adobe Illustrator**                               | -更快速地使用 GPU 加速畫布來平移和縮放，讓圖形設計人員和 illustrators 能夠流暢且互動地在複雜的向量圖形之間移動及放大和縮小。                                                                                                                                                                                                                                                                                             |
| **Adobe Lightroom**                                 | **Adobe-在 Surface Book 3 中使用 Quadro RTX 3000 進行測試及核准**<br><br>-更快速地編輯含 GPU 加速視口的高解析度影像，這可讓您更大的3D 場景進行模型，以及更複雜的動畫 rigging。<br><br>-GPU 加速影像處理可大大改善回應，特別是在4K 或更高解析度的顯示器上。<br><br>-GPU 加速的已加上 AI-已準備好的 [增強詳細資料]，以微調原始影像的色彩詳細資料。 |
| **Adobe Photoshop**                                 | **Adobe-在 Surface Book 3 中使用 Quadro RTX 3000 進行測試及核准**<br><br>-CUDA 核心加速可讓您快速進行編輯，包括 [模糊] 圖庫、[液化]、[智慧銳化] 和 [透視] 等功能，讓您可以順利且快速地修改影像。                                                                                                                                                                              |
| **各個**<br>**Premiere Pro**                       | **Adobe-在 Surface Book 3 中使用 Quadro RTX 3000 進行測試及核准**<br><br>-使用 GPU 加速效果對 CPU 的更快速地編輯及轉譯影片。<br><br>-GPU CUDA 技術的 GPU 速度效果，可即時進行影片編輯及更快的最終畫面轉譯。<br><br>-GPU-加速 AI 自動 Reframe 功能，可將橫向影片智慧地轉換為動態追蹤或方形影片。                                           |
| **Adobe 物質 Alchemist**                       | -利用 RTX 加速的 AI，輕鬆建立及混合材質。                                                                                                                                                                                                                                                                                                                                                                                                                    |
| **Adobe 物質刷**                         | **Adobe-在 Surface Book 3 中使用 Quadro RTX 3000 進行測試及核准**<br><br>將素材繪製到3d 模型上（含 RTX 加速 bakers）和 Iray RTX 轉譯，以針對互動式及批次轉譯工作流程產生影像影像。                                                                                                                                                                                                                            |
| **Adobe 物質設計工具**                        | -撰寫含 RTX 加速 bakers 的程式化資料。<br><br>-使用 NVIDIA Iray 轉譯，包括紋理/物質和點陣圖紋理匯出，以在任何與 MDL 相容的 Iray 中轉譯。<br><br>-DXR-加速的輕型與環境遮蔽選擇。                                                                                                                                                                                                              |
| **ANSYS**<br>**探索即時**                     | ANSYS 即時工程模擬工具（ANSYS 發現活）建立于 CUDA 上。                                                                                                                                                                                                                                                                                                                                                                                                      |
| **Autodesk**<br>**Revit**                           | **Autodesk-已針對 Surface Book 3 （含 Quadro RTX 3000）測試及核准**<br><br>-GPU 加速的視口，可讓您更順暢、更具交互性的設計體驗。<br><br>-支援協力廠商 GPU-加速的3D 輸出（例如 V-射線與 Enscape）。                                                                                                                                                                                                                                        |
| **Autodesk**<br>**3ds 最大值**                         | **Autodesk-已針對 Surface Book 3 （含 Quadro RTX 3000）測試及核准**<br><br>-可讓您快速、互動式3D 建模及設計的 GPU 加速視口圖形。<br><br>-RTX-加速的射線追蹤和 AI denoising，並使用預設的 Arnold 轉譯器。<br><br>-與 Surface Book 2 15 相比，速度超過70%。                                                                                                                                                        |
| **Autodesk**<br>**Maya**                            | **Autodesk-已針對 Surface Book 3 （含 Quadro RTX 3000）測試及核准**<br><br>-RTX-加速的射線追蹤和 AI denoising，並使用預設的 Arnold 轉譯器。<br><br>-OpenGL 視口加速度。                                                                                                                                                                                                                                                                                  |
| **Bentley MicroStation**                            | **Bentley-已針對 Surface Book 3 （含 Quadro RTX 3000）測試及核准**                                                                                                                                                                                                                                                                                                                                                                                                                  |
| **Dassault Systemes**<br>**3D 體驗平臺** | -CATIA 互動射線追蹤器（即時轉譯），加速了 RT 核心。<br><br>-Catia 與 Surface Book 2 15 相比，可執行檔速度超過100%。                                                                                                                                                                                                                                                                                                                                     |
| **Dassault Systemes**<br>**Solidworks**             | -Solidworks 互動式 Ray 追蹤（視覺效果），由 RT 核心和 Tensor 內核加速;AI-加速 denoiser。<br><br>-與 Surface Book 2 15 相比，執行的速度超過50%。                                                                                                                                                                                                                                                                                             |
| **ImageVis3D**                                      | -與 Surface Book 2 15 相比，執行的速度超過2倍。                                                                                                                                                                                                                                                                                                                                                                                                                             |
| **Esri ArcGIS**                                     | -即時的結果，是由於 DL inferencing 利用 tensor 的核心而產生的時間和周數。                                                                                                                                                                                                                                                                                                                                                                                        |
| **Luxion KeyShot**                                  | -Solidworks、Creo 和 Rhino 使用的協力廠商互動式 Ray 追蹤。 OptiX™ AI-加速 denoising，以 RT 核心為加速。                                                                                                                                                                                                                                                                                                                                                        |
| **McNeel & 關聯**<br>**Rhino 3D**             | **Rhino-已針對 Surface Book 3 （含 Quadro RTX 3000）測試及核准**<br><br>-GPU-加速的視口，提供流暢且互動式的建模及設計體驗。<br><br>-支援 GPU 加速3D 轉譯的週期。                                                                                                                                                                                                                                                         |
| **PTC Creo**                                        | -Creo 的即時工程模擬工具（Creo 類比活）是以 CUDA 為基礎。<br><br>-與 Surface Book 2 15 相比，執行的速度超過15%。                                                                                                                                                                                                                                                                                                                                |
| **Siemens NX**                                      | -Siemens NX 互動式射線追蹤器（Ray 追蹤錄音室）加速了 RT 核心。<br><br>-與 Surface Book 2 15 相比，執行的速度超過10倍。                                                                                                                                                                                                                                                                                                                                    |






## Sku

**表 4. 使用 Quadro RTX 3000 Sku 的 Surface Book 3**

| **顯示器** | **處理者**                     | **GPU**                                                                                          | **RAM**    | **儲存體** |
| ----------- | --------------------------------- | ------------------------------------------------------------------------------------------------ | ---------- | ----------- |
| 15英寸 | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩™加上圖形<br>NVIDIA Quadro RTX 3000。 最大-Q 設計與 6GB GDDR6 圖形記憶體 | 32 LPDDR4x | 512 GB      |
| 15英寸 | 四核 10 Gen 雙核 i7-1065G7 | 英特爾虹彩™加上圖形<br>NVIDIA Quadro RTX 3000。 最大-Q 設計與 6GB GDDR6 圖形記憶體 | 32 LPDDR4x | 1 TB        |

## 摘要

Surface Book 3 （含 Quadro RTX 3000）可提供任何 Surface 膝上型電腦的最佳圖形效能，提供架構師、工程師、開發人員和資料科學家，以及它們所需的工具，可隨時隨地有效地運作：
 
- 跨多個工作流程（例如設計、動畫、影片製作等）的 RTX 加速。
- 行動裝置規格中的桌面年級效能。
- 針對任務關鍵型專案的企業級功能、可靠性和支援。

## 深入了解

- [Surface Book 3 GPU 技術概觀](surface-book-GPU-overview.md)
- [商務用 Surface](https://www.microsoft.com/surface/business)
- [Microsoft 認知工具組（CNTK）](https://docs.microsoft.com/cognitive-toolkit/)
