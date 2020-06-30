---
title: 更新 Surface Hub 秒的畫筆固件
description: 此頁面說明如何更新 Surface Hub 2 筆的固件。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/26/2020
ms.localizationpriority: Medium
ms.openlocfilehash: c0ad8f275d2476e42c9a5bd3f1130fbca85a5599
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831470"
---
# 更新 Surface Hub 秒的畫筆固件

您可以從商務用 Windows Update，或透過將固件更新下載到個別的電腦，在 Surface Hub 2 筆上更新固件。 您可以從2020年2月26日開始的 Windows 更新取得更新的固件。 

## 使用 Windows 版企業更新更新手寫筆固件

本節說明如何透過 Windows Update 的自動維護週期來更新手寫筆固件（預設為在夜間 3 a.m. 進行）設定。 在將更新套用至 Surface Hub 2 筆前，您必須規劃兩個維護週期才能完成。 或者，您可以使用 Windows Server Update Services （WSUS）來套用手寫筆固件，就像任何其他更新一樣。 如需詳細資訊，請參閱[管理 Surface Hub 上的 Windows 更新](manage-windows-updates-for-surface-hub.md)。

1. 確定 Surface Hub 2 筆已配對至 Surface Hub 2：按住**上方**按鈕，直到白色的指示燈開始閃爍為止。 <br>
![Surface Hub 2 筆](images/sh2-pen-1.png) <br>
2. 在 Surface Hub 上，以系統管理員身分登入，然後開啟 [**設定**]，然後掃描新的藍牙裝置。
3. 選取手寫筆以完成配對程式。
4. 按手寫筆上的**上方**按鈕來套用更新。 可能需要長達兩個小時才能完成。

## 透過下載到個別電腦來更新手寫筆固件

您可以從執行 Windows 10 的另一部電腦，在 Surface Hub 2 筆上更新固件。 這個方法也可讓您確認畫筆固件已成功更新為最新版本。

1. 將 Surface Hub 2 筆與支援藍牙功能的電腦配對：按住**上方**按鈕，直到白色的指示燈開始閃爍為止。 <br>
![Surface Hub 2 筆](images/sh2-pen-1.png) <br>
2. 在電腦上，掃描新的藍牙裝置。
3. 選取手寫筆以完成配對程式。
4. 在開始新的更新之前，請中斷所有其他 Surface Hub 2 的筆。
3. 將[Surface Hub 2 手寫筆固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下載到您的電腦。
4. 執行**PenCfu.exe。** 安裝進度會顯示在工具中。 完成更新可能需要幾分鐘的時間。 


## 檢查 Surface Hub 2 手寫筆的固件版本

1. 執行**get_version.bat**然後按手寫筆上的**上方**按鈕。
2. 此工具會報告手寫筆的固件版本。 範例：
    - 舊的固件為468.2727.368
    - 新的固件為468.2863.369

## 命令列選項

您可以從命令列執行 Surface Hub 2 手寫筆固件更新工具（PenCfu.exe）。

1. 將筆與您的電腦配對，然後按一下手寫筆上的**上方**按鈕。
2. 按兩下 [ **PenCfu.exe** ] 以啟動固件更新。 請注意，設定檔和固件映射檔必須與工具儲存在相同的資料夾中。
3. 如需其他選項，請執行**PenCfu.exe h**以顯示可用的參數，如下表所列。  
    - 範例： PenCfu.exe-h
4. 輸入**Ctrl + C**以安全地關閉工具。

 

| **命令**    | **描述**                                                                                                                                                                                                                                                                                                                                                                                |
| -------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -h 說明        | 顯示工具命令列介面說明及結束。                                                                                                                                                                                                                                                                                                                                             |
| -v 版本     | [顯示工具版本] 和 [結束]。                                                                                                                                                                                                                                                                                                                                                                 |
| -l 記錄-篩選  | 設定記錄檔的篩選層級。 記錄訊息有4種可能的層次：調試（最低）、資訊、警告和錯誤（最高）。 設定記錄篩選層級篩選只會將記錄記錄在相同層級或更新版本的訊息中。 例如，如果篩選層級設定為 [警告]，則只會記錄警告和錯誤訊息。 根據預設，此選項會設定為 [關閉]，這會停用記錄。 |
| -g 取得版本 | 如果已指定，工具將只會取得與工具相同資料夾中所儲存之設定檔相符的已連接手寫筆固件版本。                                                                                                                                                                                                                                    