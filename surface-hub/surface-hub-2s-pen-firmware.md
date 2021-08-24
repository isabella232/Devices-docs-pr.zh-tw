---
title: 在 Surface Hub 2S 上更新手寫筆韌體
description: 此頁面說明如何更新 2 支Surface Hub的固件。
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
ms.openlocfilehash: fb0948623ec9c12aa818e4829285ea77229bf71d
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911578"
---
# <a name="update-pen-firmware-on-surface-hub-2s"></a>在 Surface Hub 2S 上更新手寫筆韌體

您可以在 2 支Surface Hub上更新Windows商務用更新，或將固件更新下載到另一部電腦。 從 2020 年 2 月 26 Windows開始更新的固件。 

## <a name="update-pen-firmware-using-windows-update-for-business"></a>使用商務Windows更新更新筆式固件

本節說明如何透過自動維護週期更新筆Windows更新，根據預設，這項作業預設為在上午 3 點進行。 您必須規劃兩個維護週期才能完成，才能將更新套用至 2 支Surface Hub筆。 或者，就像任何其他更新一樣，您也可以使用商務Windows更新 (WUfB) 來使用筆式固件。 詳細資訊，請參閱管理[Windows 上的Surface Hub。](manage-windows-updates-for-surface-hub.md)

1. 請Surface Hub 2 支筆配對Surface Hub 2S：按住頂端按鈕，直到白色指示器 LED**** 指示燈開始閃爍。

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 支筆。](images/sh2-pen-1.png)

2. 在 Surface Hub 登入為系統管理員，開啟 設定 **，然後**掃描藍牙裝置。

3. 選取觸控筆以完成配對程式。

4. 按 **觸控筆** 上的頂端按鈕以適用更新。 最多可能需要兩小時才能完成。

## <a name="update-pen-firmware-by-downloading-to-separate-pc"></a>下載至個別電腦以更新觸控筆的固件

您可以在執行 Surface Hub 的個別電腦更新 2 支Windows 10。 這個方法也可讓您確認筆式固件已成功更新至最新版本。

1. 將 Surface Hub 2 支筆配對至藍牙型電腦：按住頂端按鈕，直到白色指示器**** LED 指示燈開始閃爍。

    > [!div class="mx-imgBorder"]
    > ![Surface Hub 2 支筆。](images/sh2-pen-1.png)

2. 在 PC 上，掃描新的藍牙裝置。

3. 選取觸控筆以完成配對程式。

4. 在開始新的更新Surface Hub先中斷所有其他 2s 筆的中斷連接。

5. 將 Surface Hub [2 筆固件更新工具](https://download.microsoft.com/download/8/3/F/83FD5089-D14E-42E3-AF7C-6FC36F80D347/Pen_Firmware_Tool.zip)下載到您的電腦。

6. 執行 **PenCfu.exe。** 安裝進度會顯示在工具中。 可能需要幾分鐘才能完成更新。 


## <a name="check-firmware-version-of-surface-hub-2-pen"></a>檢查 2 支Surface Hub的固件版本

1. 執行 **get_version.bat， ** 然後按 **觸控筆** 上的頂端按鈕。

2. 此工具會報告觸控筆的固件版本。 

   範例：
    - 舊固件為 468.2727.368
    - 新的固件為 468.3347.368

## <a name="command-line-options"></a>命令列選項

您可以在命令列Surface Hub 2 筆 (PenCfu.exe) 更新工具。

1. 將筆與電腦配對，然後按一下 **筆** 上的頂端按鈕。

2. 按兩下 ** [PenCfu.exe** 以啟動固件更新。 請注意，設定檔和固件圖像檔案必須儲存在與工具相同的資料夾中。

3. 針對其他選項，請執行 **PenCfu.exe -h** 以顯示可用的參數，如下表所列。  

   範例： `PenCfu.exe -h`

4. 輸入 **Ctrl+C** 以安全地關閉工具。


| 命令 | 描述 |
| -------------- |---------------------------- |
| -h help        | 顯示工具命令列介面説明並離開。 |
| -v 版本     | 顯示工具版本並離開。 |
| -l 記錄篩選  | 設定記錄檔案的篩選層級。 記錄訊息有 4 個可能層級：DEBUG (最低) 、INFO、WARNING 和 ERROR (最高) 。 設定記錄篩選層級會篩選記錄訊息至只有相同層級或較高層級的郵件。 例如，如果篩選等級設為警告，則只會記錄警告和錯誤訊息。 根據預設，此選項會設定為 OFF，這會停用記錄。 |
| -g get-version | 如果指定，工具只會取得與該工具儲存在同一資料夾中的設定檔相符合的已連接觸控筆 FW 版本。  |

