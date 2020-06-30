---
title: Surface 系統 SKU 參考
description: 本主題提供系統 SKU 名稱的參考，您可以用來快速判斷特定裝置的電腦狀態。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 29cd47beb855c9b643fca42d91c7b316c374fcca
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831400"
---
# Surface System SKU 參考
本檔提供系統 SKU 名稱的參考，您可以使用 PowerShell、WMI 及相關工具快速判斷特定裝置的電腦狀態。 

系統 SKU 是儲存在 Surface 裝置的 UEFI 層中系統管理 BIOS （SMBIOS）資料表中的變數（以及系統模型及其他元件）。  每當您需要區分具有相同系統模型名稱（例如 Surface Pro 和 Surface Pro）與 LTE Advanced 的裝置時，請使用系統 SKU 名稱。 

| **裝置**| **系統模型** | **系統 SKU**|
| --- | ---| --- |
| Surface 3 WiFI                                               | Surface 3        | Surface_3                        |
| &T 上的 Surface 3 LTE                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| 北美洲的 Surface 3 LTE                                  | Surface 3        | Surface_3_NAG                    |
| 在北美與 T-Mobile 外部的 Surface 3 LTE | Surface 3        | Surface_3_ROW                    |
| Surface Pro                                                  | Surface Pro      | Surface_Pro_1796                 |
| 配備 LTE Advanced 的 Surface Pro                                | Surface Pro      | Surface_Pro_1807                 |
| Surface Book 2 13inch                                        | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15inch                                        | Surface Book 2   | Surface_Book_1793                |
| Surface Go 消費者                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface 商業                                        | Surface Go       | Surface_Go_1824_Commercial       |
| 表面移2                                                 | 表面移2     | Surface_Go_2_1927                |
| Surface Pro 6 消費者                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 6 商業版                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface 膝上型電腦2消費者                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface 膝上型電腦2商業版                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |

## 使用系統 SKU 變數 

### PowerShell

     gwmi -namespace root\wmi -class MS_SystemInformation | select SystemSKU 

### 系統資訊
您也可以在 [系統資訊] 中找到裝置的系統 SKU 和系統模型。 
- 按一下 [**開始**  >   **MSInfo32**]。  

### CIM
您可以在 Microsoft 部署工具套件（MDT）或 Microsoft 端點設定管理員的 [任務序列] 中，使用「系統 SKU 變數」 WMI 條件。 例如： 

    - WMI 命名空間-Root\WMI
    - WQL 查詢–從 MS_SystemInformation 中選取 [*]，SystemSKU = "Surface_Pro_1796"

 
 
 


