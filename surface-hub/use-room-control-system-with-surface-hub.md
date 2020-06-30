---
title: 使用會議室控制系統 (Surface Hub)
description: 會議室控制系統可以與您的 Microsoft Surface Hub 搭配使用。
ms.assetid: DC365002-6B35-45C5-A2B8-3E1EB0CB8B50
ms.reviewer: ''
manager: laurawi
keywords: 會議室控制系統, Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 0e3b1706e58edb6e37156eda8d06fb0faefa4c91
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831336"
---
# 使用會議室控制系統 (Surface Hub)


會議室控制系統可以與您的 Microsoft Surface Hub 搭配使用。

將會議室控制系統與您的 Surface Hub 搭配使用，包括將會議室控制硬體連接到 Surface Hub (通常是透過 Surface Hub 底部的 RJ11 序列埠來連接)。

## 終端機設定

若要連接到會議室控制系統的控制台，您不需要在 Surface Hub 上設定任何終端機設定。 如果您想要將電腦或膝上型電腦連接到 Surface Hub 並從 Surface Hub 傳送序列命令，您可以使用終端機模擬器程式 (例如 Tera Term 或 PuTTY)。 

| 設定 | 值 |
| --- | --- |
| 傳輸速率 | 115200 |
| 資料位元 | 型 | 
| 停止位元 | sr-1 |
| 同位 | 無 |
| 流量控制 | 無 |
| 換行字元 | 每個歸位字元 |
 

## 線路圖

您可以使用標準的 RJ-11 (6P6C) 連接器，將 Surface Hub 序列埠連接到會議室控制系統。 這是建議的方法。 您也可以使用 4 導線的 RJ-11 纜線，但我們不建議使用這個方法。

下圖顯示 RJ-11 (6P6C) 至 DB9 纜線的正確針腳對應。

![顯示路線圖的影像。](images/room-control-wiring-diagram.png)

## 命令集

會議室控制系統會針對命令使用常見的會議室案例。 命令源自會議室控制系統，並透過序列式連線來與 Surface Hub 通訊。 命令是以 ASCII 為基礎，而且 Surface Hub 將會在發生狀態變更時進行確認。

您可以使用下列命令修飾詞。 命令是以新行字元 (/n) 來結尾。 回應可隨時進行，以回應不是由管理連接埠命令直接觸發的狀態變更。

| 修飾詞 | 結果 |
| --- | --- |
| + | 遞增值 |
| - | 遞減值 |
| = | 設定離散值 |
| ? | 查詢目前的值 |
 

## 電源

Surface Hub 可以處於下列其中一個電源狀態。

| 狀態 | 能源之星狀態| 說明 |
| --- | --- | --- |
| 0 | S5 | 關閉 |
| sr-1 | - | 開啟電源 (不確定) |
| pplx-2 | S3 | 睡眠 |
| 500 | S0 | 就緒 |


在「替代電腦」模式中，電源狀態只有「就緒」和「關閉」，且只會變更顯示器。 管理埠無法用來將替代電腦開機。 

| 狀態 | 能源之星狀態| 說明 |
| --- | --- | --- |
| 0 | S5 | 關閉 |
| 500 | S0 | 就緒 |

針對控制裝置，「5 / 就緒」以外的任何值都被視為關閉。 每個 PowerOn 命令都會產生兩種狀態變更與回應。 

| 命令 | 狀態變更| 回應 |
| --- | --- | --- |
| PowerOn | 開啟裝置 (顯示器 + 電腦)。</br></br>電腦服務通知 SMC 電腦已經就緒。 |  Power=0</br></br>Power=5 |
| PowerOff | 裝置轉換成環境狀態 (電腦開啟，顯示器變暗)。 |  Power=0 |
| Power? |  SMC 回報已知的最後電源狀態。 |  Power=<#> |



## 亮度

目前的亮度等級是介於 0 到 100 的範圍。

對於亮度等級的變更可以透過會議室控制系統或其他系統來傳送。

| 命令 | 狀態變更 |回應 |
| --- | --- | --- |
| Brightness+ | 系統管理控制器 (SMC) 會傳送增加亮度命令。</br></br>會議室控制系統上的電腦服務會通知 SMC 新的亮度等級。 |  Brightness = 51 |
| Brightness- |  SMC 會傳送降低亮度命令。</br></br>電腦服務會通知 SMC 新的亮度等級。 | Brightness = 50 |

## 音量

目前的音量等級是介於 0 到 100 的範圍。

對於音量大小的變更可以透過會議室控制系統或其他系統來傳送。

>[!NOTE]
>音量命令只會控制內嵌或取代用電腦模式的音量，而不會控制[客體來源](connect-and-display-with-surface-hub.md)。

| 命令 | 狀態變更 | 回應</br>(關於 [取代用電腦模式](connect-and-display-with-surface-hub.md#replacement-pc-mode)) |
| --- | --- | --- |
| Volume+ |  SMC 會傳送調高音量的命令。</br></br>電腦服務會通知 SMC 新的音量大小。 |  Volume = 51 |
| Volume- |  SMC 會傳送降低音量的命令。</br></br>電腦服務會通知 SMC 新的音量等級。 |  Volume = 50 |


 

## 音訊靜音

可將音訊設為靜音。

| 命令 | 狀態變更 | 回應 |
| --- | --- | --- |
| AudioMute+ |  SMC 會傳送將音訊設為靜音的命令。</br></br>電腦服務會通知 SMC 將音訊設為靜音。 |  無 |


 

## 視訊來源

可以使用數個顯示來源。

| 狀態 | 說明 | 
| --- | --- |
| 0 |  內建的電腦 |
| sr-1 |  DisplayPort |
| pplx-2 |  HDMI |
| 3 |  VGA |


 

對於顯示來源的變更可以透過會議室控制系統或其他系統來傳送。

| 命令 | 狀態變更 | 回應 |
| --- | --- | --- |
| Source=# |  SMC 會對所需的來源進行變更。</br></br>電腦服務會通知 SMC 已切換顯示來源。 |  Source=&lt;#&gt; |
| Source+ |  SMC 會循環至下一個作用中的輸入來源。</br></br>電腦服務會通知 SMC 目前的輸入來源。 |  Source=&lt;#&gt; |
| Source- | SMC 會循環至上一個作用中的輸入來源。</br></br>電腦服務會通知 SMC 目前的輸入來源。 |  Source=&lt;#&gt; |
| Source? |  SMC 會查詢電腦服務以取得作用中的輸入來源。</br></br>電腦服務會通知 SMC 目前的輸入來源。 | Source=&lt;#&gt; |

## 錯誤

錯誤會以此表格中的格式傳回。

| 錯誤 | 附註 |
| --- | --- |
| 錯誤: 未知的命令 '&lt;input&gt;'。 |  指示包含未知的初始命令。 例如，&quot;VOL+&quot; 將會是無效的，並傳回 &quot;錯誤: 未知命令 'VOL'&quot;。 |
| 錯誤: 未知的運算子 '&lt;input&gt;'。 |  指示包含未知的運算子。 例如，&quot;Volume!&quot; 將會無效，並傳回 &quot;錯誤: 未知運算子 '!'&quot;。 |
| 錯誤: 未知的參數 '&lt;input&gt;'。 |  指示包含未知的參數。 例如，&quot;Volume=abc&quot; 將會是無效的，並傳回 &quot;錯誤: 未知參數 'abc'&quot;。 |
| 錯誤: 關閉時無法使用命令 '&lt;input&gt;'。 |  當 Surface Hub 關閉時，針對「電源」以外的命令會傳回這個錯誤。 例如，&quot;Volume+&quot; 將會是無效的，並傳回 &quot;錯誤: 關閉時無法使用命令 'Volume'&quot;。 |


 

## 相關主題


[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)

 

 





