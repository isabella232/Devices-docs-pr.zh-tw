---
title: 在 Surface Hub 2S 上更新手寫筆韌體
description: 此頁面說明如何更新 Surface Hub 2 手寫筆的韌體。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 04/15/2021
ms.localizationpriority: Medium
ms.openlocfilehash: b1955f1806c963ce553d5d2eef99e72e90c5adfe
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497716"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>在 Surface Hub 2S 上更新手寫筆韌體

您可以從商務用 Windows Update 或將韌體更新下載到個別的電腦，在 Surface Hub 2 手寫筆上更新韌體。 從 2020 年 2 月 26 日開始，Windows Update提供更新的韌體。 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>使用商務用Windows Update更新畫筆韌體

本節說明如何透過自動維護週期來更新手寫筆韌體，Windows Update依預設設定為在晚上 3 點發生。 您必須先規劃兩個維護週期才能完成，才能將更新套用至 Surface Hub 2 手寫筆。 或者，如同任何其他更新，您可以使用商務用 Windows Update (WUfB) 來套用畫筆韌體。 如需詳細資訊，請[參閱管理Surface Hub上的Windows更新](manage-windows-updates-for-surface-hub.md)。

1. 確定 Surface Hub 2 手寫筆與Surface Hub 2S 配對：按**住頂端**按鈕，直到白色指標 LED 燈開始閃爍為止。

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 個畫筆。](images/sh2-pen-1.png)

2. 在Surface Hub上，以系統管理員身分登入、開**啟設定**，然後掃描是否有新的藍牙裝置。

3. 選取畫筆以完成配對程式。

4. 按下畫筆上的 **頂端** 按鈕以套用更新。 最多可能需要兩個小時才能完成。

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>將手寫筆韌體下載到個別的電腦，以更新手寫筆韌體

您可以從執行 Windows 10 或 Windows 11 的個別電腦，更新 Surface Hub 2 手寫筆上的韌體。 此方法也可讓您確認手寫筆韌體已成功更新為最新版本。

1. 將Surface Hub 2 手寫筆與藍牙電腦配對：按**住頂端**按鈕，直到白色指標 LED 燈開始閃爍為止。

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 個畫筆。](images/sh2-pen-1.png)

2. 在電腦上，掃描新的藍牙裝置。

3. 選取畫筆以完成配對程式。

4. 開始新的更新之前，請先中斷所有其他Surface Hub 2s 手寫筆的連線。

5. 將[Surface Hub 2 手寫筆韌體更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下載到您的電腦。

6. 執行 **PenCfu.exe。** 安裝進度會顯示在工具中。 可能需要幾分鐘的時間才能完成更新。 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>檢查 Surface Hub 2 手寫筆的韌體版本

1. 執行 **get_version.bat** ，然後按畫筆上的 **頂端** 按鈕。

2. 此工具會報告畫筆的韌體版本。 

   範例：
    - 舊的韌體是 468.2727.368
    - 新的韌體為 468.3347.368

## <a name="command-line-options"></a>命令列選項

您可以從命令列執行 Surface Hub 2 手寫筆韌體更新工具 (PenCfu.exe) 。

1. 將畫筆與您的電腦配對，然後按一下畫筆上的 **頂端** 按鈕。

2. 按兩下 **PenCfu.exe** 以起始韌體更新。 請注意，組態檔和韌體映射檔必須儲存在與工具相同的資料夾中。

3. 如需其他選項，請 ** 執行PenCfu.exe -h** 以顯示可用的參數，如下表所列。  

   範例： `PenCfu.exe -h`

4. 輸入 **Ctrl+C** 以安全地關閉工具。


| 命令 | 描述 |
| -------------- |---------------------------- |
| -h 說明        | 顯示工具命令列介面說明並結束。 |
| -v 版本     | 顯示工具版本並結束。 |
| -l log-filter  | 設定記錄檔的篩選層級。 記錄訊息有 4 個可能的層級：偵錯 (最低) 、INFO、WARNING 和 ERROR (最高) 。 設定記錄篩選層級會將記錄訊息篩選為僅具有相同層級或更高等級的訊息。 例如，如果篩選層級設定為 WARNING，則只會記錄 WARNING 和 ERROR 訊息。 根據預設，此選項會設定為 OFF，這會停用記錄。 |
| -g get-version | 如果指定，此工具只會取得與與工具儲存在相同資料夾中的組態檔相符的連線畫筆 FW 版本。  |

