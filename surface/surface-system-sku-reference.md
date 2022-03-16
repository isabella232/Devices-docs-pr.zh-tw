---
title: Surface 系統 SKU 參考
description: 請參閱所有 Surface 裝置之系統模型和系統 SKU 名稱的參照。
keywords: uefi， configure， firmware， secure， semm， Autopilot
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 02/03/2022
ms.reviewer: carlol
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 45fd61ff59273e5ae3fc269058b663f271e641d4
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448686"
---
# <a name="surface-system-sku-reference"></a>Surface 系統 SKU 參考

本檔提供可用於各種 IT 工作 ，例如執行命令或根據裝置模型/SKU 名稱安裝驅動程式的參考。 系統模型和 System SKU 是儲存在 Surface 裝置 UEFI 圖層中系統管理BIOS (SMBIOS) 資料表中的變數。 當您需要區分具有相同系統模型名稱的裝置時，請使用 System SKU 名稱，例如使用 LTE Advanced Surface Pro Surface Pro裝置。 下表所列的 SKUS 是指商業裝置，除非標示為消費者。 

| 裝置   | 系統模型 | System SKU       |
| ---------- | ----------- | -------------- |
| Surface 3 Wi-FI                                               | Surface 3        | Surface_3                        |
| Surface 3 LTE AT&T                                           | Surface 3        | Surface_3_US1                    |
| Surface 3 LTE Verizon                                        | Surface 3        | Surface_3_US2                    |
| Surface 3 LTE 北美                                  | Surface 3        | Surface_3_NAG                    |
| Surface 3 LTE 北美以外地區，日本 Y！mobile | Surface 3        | Surface_3_ROW                    |
| Surface Book 2 13"                                           | Surface Book 2   | Surface_Book_1832                |
| Surface Book 2 15"                                           | Surface Book 2   | Surface_Book_1793                |
| Surface Book 3 13"                                           | Surface Book 3   | Surface_Book_3_1900                |
| Surface Book 3 15"                                           | Surface Book 3   | Surface_Book_3_1899
| Surface Go Commercial                                        | Surface Go       | Surface_Go_1824_Commercial       |
| Surface Go 消費者                                          | Surface Go       | Surface_Go_1824_Consumer         |
| Surface Go LTE 商業                                    | Surface Go       | Surface_Go_1825_Commercial |
| Surface Go 2 商業                                      | Surface Go 2     | Surface_Go_2_1926                |
| Surface Go 2 消費者                                        | Surface Go 2     | Surface_Go_2_1901                |
| Surface Go 2 LTE                                             | Surface Go 2     | Surface_Go_2_1927                |
| Surface Go 3 商業版                                      | Surface Go 3     | Surface_Go_3_1926                |
| Surface Go 3 消費者                                        | Surface Go 3     | Surface_Go_3_1901                |
| Surface Go 3 LTE                                             | Surface Go 3     | Surface_Go_3_2022                |
| Surface Hub 2S 50"                                           | Surface Hub 2S   | Surface Hub 2S                   |
| Surface Hub 2S 85"                                           | Surface Hub 2S   | Surface Hub 2S 85                |
| Surface 膝上型電腦                                               | Surface 膝上型電腦   | Surface_Laptop                   |
| Surface Laptop 2 商業                                  | Surface Laptop 2 | Surface_Laptop_2_1769_Commercial |
| Surface Laptop 2 消費者                                    | Surface Laptop 2 | Surface_Laptop_2_1769_Consumer   |
| Surface Laptop 3 13" Intel                                   | Surface Laptop 3 | Surface_Laptop_3_1867：1868 |
| Surface Laptop 3 15"                                     | Surface Laptop 3 | Surface_Laptop_3_1873      |
| Surface Laptop 3 15" Intel                                   | Surface Laptop 3 | Surface_Laptop_3_1872      |
| Surface Laptop 4 13"                                     | Surface Laptop 4 | Surface_Laptop_4_1958：1959    |
| Surface Laptop 4 13" Intel                                   | Surface Laptop 4 | Surface_Laptop_4_1950：1951 |
| Surface Laptop 4 15"                                     | Surface Laptop 4 | Surface_Laptop_4_1952：1953     |
| Surface Laptop 4 15" Intel                                   | Surface Laptop 4 | Surface_Laptop_4_1978：1979     |
| Surface Laptop Go                                            | Surface Laptop Go | Surface_Laptop_Go_1943      |
| Surface Laptop SE                                            | Surface Laptop SE | Surface Laptop SE            |
| Surface Laptop Studio                                        | Surface Laptop Studio | Surface_Laptop_Studio_1964 |
| Surface Pro (第 5 代)                                         | Surface Pro      | Surface_Pro_1796                 |
| Surface Pro LTE Advanced (第 5 代)                       | Surface Pro      | Surface_Pro_1807                 |
| Surface Pro 6 商業版                                     | Surface Pro 6    | Surface_Pro_6_1796_Commercial    |
| Surface Pro 6 消費者                                       | Surface Pro 6    | Surface_Pro_6_1796_Consumer      |
| Surface Pro 7                                                | Surface Pro 7    | Surface_Pro_7_1866         |
| Surface Pro 7+                                               | Surface Pro 7+   | Surface_Pro_7+_1960|
| Surface Pro 7+ LTE                                           | Surface Pro 7+   | Surface_Pro_7+_with_LTE_Advanced_1961|
| Surface Pro 8                                                | Surface Pro 8    | Surface_Pro_8_for_Business_1983|
| Surface Pro 8 消費者                                       | Surface Pro 8    | Surface_Pro_8_1983|
| Surface Pro 8 LTE                                            | Surface Pro 8    | Surface_Pro_8_for_Business_with_LTE_Advanced_1982|
| Surface Pro SQ1 處理器的 X                             | Surface Pro X    | Surface_Pro_X_1876         |
| Surface Pro SQ2 處理器的 X                             | Surface Pro X    | Surface_Pro_X_H_1876        |
| Surface Pro X (Wi-Fi)                                         | Surface Pro X    | Surface_Pro_X_2010        |
| Surface Studio                                               | Surface Studio   | Surface_Studio   |
| Surface Studio 2                                             | Surface Studio 2 | Surface_Studio_2_1707_Commercial   |


## <a name="examples"></a>範例

**使用 PowerShell 來取回 SKU**  
使用下列 PowerShell 命令來提取 System SKU 資訊：

 ``` powershell  
(Get-CimInstance -Namespace root\wmi -ClassName MS_SystemInformation).SystemSKU
```

**使用 系統資訊**  
您也可以在 系統資訊 中找到裝置的系統 SKU**和系統系統資訊**。 若要這樣做，請執行下列步驟：

1. 選取 **開始**，然後在搜尋方塊中輸入 **MSInfo32** 。  
1. 選取**系統資訊**。

**在工作順序 WMI 條件中使用 SKU**  
您可以將 Microsoft 部署工具組 (MDT) 或 Microsoft Endpoint Configuration Manager 中的系統 SKU 資訊做為工作順序 WMI 條件的一部分。

 ``` powershell  
    - WMI Namespace – Root\WMI
    - WQL Query – SELECT * FROM MS_SystemInformation WHERE SystemSKU = "Surface_Pro_1796"
 ```

## <a name="learn-more"></a>深入了解

- [WMI 參照](/windows/win32/wmisdk/wmi-reference)
- [適用於 Windows Autopilot 的 Surface 註冊支援](surface-autopilot-registration-support.md)
