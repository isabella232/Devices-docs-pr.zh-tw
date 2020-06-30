---
title: Surface 資產圖章工具
description: 本主題說明如何使用 [Surface 資產標記] 工具。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.openlocfilehash: ca6a71a6b864692953fcd96eb687c2752527c9f5
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831311"
---
# Surface 資產圖章工具

[Surface 資產標記] 是命令列介面（CLI）公用程式，可讓您查看、指派及修改 Surface 裝置的指派資產標記值。 它適用于 Surface Pro 3 和所有較新的 Surface 裝置。

## 系統需求

- Surface Pro 3 或更新版本

- UEFI 固件版本3.9.150.0 或更新版本

## 使用 Surface 資產標記 

執行表面資產標記：

1.  在 Surface 裝置上，從[Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=46703)下載**表面資產 Tag.zip** ，解壓縮 zip 檔案，然後將 AssetTag.exe 儲存在所需的資料夾中（在此範例中為 C:\\assets）。

    > [!NOTE]
    > 針對 Surface Pro X，請在 ZIP 檔案中使用名為**AssetTag_x86**的應用程式。 

2.  以系統管理員身分開啟命令主控台，然後執行 AssetTag.exe，輸入工具的完整路徑。

3.  重新開機表面。

### 資產圖章工具命令   
在下列範例中，AssetTag.exe 會儲存在本機電腦上的目錄中（C:\assets）。 

若要取得建議的資產標記，請執行 AssetTag-g。

**範例**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 若要清除建議的資產標記，請執行 AssetTag-s。
 
 **範例**
 
   ```
C:\assets\AssetTag.exe -s
  ```
若要設定建議的資產標記，請執行 AssetTag-s testassettag12。

**範例**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>資產標記值必須包含1到36個字元。 有效的字元包括 A-z、a-z、0-9、句點（.）及連字號（-）。


## 管理資產標記

您可以在 [裝置資訊] 下的 [UEFI 設定] （[**控制台] > > [高級 > 啟動**] 中，[立即重新開機]），查看現有資產標記。

下圖顯示在表面上執行資產圖章工具的結果。

![表面上執行的表面資產圖章工具的結果。
](images/assettag-fig1.png)

> **圖 1。** 表面上執行的表面資產圖章工具結果

或者，您可以使用 WMI 來查詢裝置上的現有資產標記：

（WmiObject-query "從 Win32_SystemEnclosure 選取 *）

**範例**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### 使用 PowerShell

您可以使用下列腳本來取得建議值並解釋任何錯誤。

 ```
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim(“\`r\`n”)

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output (“Good Tag = ” + $asset\_tag)  
} else {  
Write-Output (  
“Failure: Code = ” + $asset\_tag\_return\_code +  
“Tag = ” + $asset\_tag +  
“Message = ” + $error\_message)

}
 ```
