---
title: 系統 SKU 參考（Surface）
description: 請參閱系統模型和系統 SKU 名稱的參考。
keywords: uefi、設定、固件、安全、semm
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 03/09/2020
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 1fa192902b17ca811d4ecc8eac65abe1655ce370
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831515"
---
# 系統 SKU 參考

本檔提供系統模型和系統 SKU 名稱的參考，您可以使用 PowerShell 或 WMI 快速判斷特定裝置的電腦狀態。

系統模型和系統 SKU 是儲存在 Surface 裝置的 UEFI 層中系統管理 BIOS （SMBIOS）資料表中的變數。 必須有系統 SKU 名稱，才能區分具有相同系統模型名稱的裝置，例如 Surface Pro 以及含 LTE Advanced 的 Surface Pro。 

| 裝置   | 系統模型 | 系統 SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| &T 上的 Surface 3 LTE                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| 北美洲的 Surface 3 LTE                                  | Surface 3        | Surface_3_NAG                    |
| 北美洲與 Y 之間的 Surface 3 LTE （在日本）移動 | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| 配備 LTE Advanced 的 Surface Pro                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13 "                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15 "                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Go LTE 消費者  | Surface Go | Surface_Go_1825_Consumer |
| 表面 [移至商業版] | 系統移至 | Surface_Go_1825_Commercial |
| Surface Go 消費者                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface 商業                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Pro 6 消費者                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 商業版                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface 膝上型電腦                                               | Surface 膝上型電腦   | Surface_Laptop                   |
| Surface 膝上型電腦2消費者                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface 膝上型電腦2商業版                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Pro 7                 | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro X                 | Surface Pro X    | Surface_Pro_X_1876         |
| Surface 膝上型電腦 3 13 "英特爾 | Surface 膝上型電腦3 | Surface_Laptop_3_1867：1868 |
| Surface 膝上型電腦 3 15 "英特爾 | Surface 膝上型電腦3 | Surface_Laptop_3_1872      |
| Surface 膝上型電腦 3 15 "AMD   | Surface 膝上型電腦3 | Surface_Laptop_3_1873      | 

## 範例 

**使用 PowerShell 來檢索 SKU**  
使用下列 PowerShell 命令來提取系統 SKU 資訊：

 ``` powershell  
gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 
```

**使用系統資訊來檢索 SKU**  
您也可以在 [**系統資訊**] 中找到裝置的系統 SKU 和系統模型。 若要這樣做，請執行下列步驟：

1. 選取 [**開始**]，然後在搜尋方塊中輸入 [ **MSInfo32** ]。  
1. 選取 [**系統資訊**]。

**在任務序列中使用 SKU WMI 條件**  
您可以在 Microsoft 部署工具組（MDT）或 Microsoft 端點設定管理員中使用系統 SKU 資訊，做為「任務序列 WMI」條件的一部分。

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ``` 
