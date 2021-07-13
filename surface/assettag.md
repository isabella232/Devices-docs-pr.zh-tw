---
title: Surface 資產圖章工具
description: 本主題說明如何使用 Surface 資產圖章工具。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.date: 06/29/2021
manager: laurawi
ms.openlocfilehash: b130f6b0bf52dc1c3a28231a2330cae51a5ef44a
ms.sourcegitcommit: d020d899e9c7e1eb0b85193ecb0a17a85bb39fe6
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/12/2021
ms.locfileid: "11643829"
---
# <a name="surface-asset-tag-tool"></a>Surface 資產圖章工具

Surface Asset Tag 是 CLI (工具) 介面，可讓您查看、指派及修改 Surface 裝置指派的資產標記值。 它適用于 Surface Pro 3 及所有較新的 Surface 裝置。

## <a name="system-requirements"></a>系統需求

- Surface Pro 3 或更高版本

- UEFI 固件版本 3.9.150.0 或更新版本

## <a name="using-surface-asset-tag"></a>使用 Surface 資產標記

若要執行 Surface 資產標記：

1. 在 Surface 裝置上，從[Microsoft](https://www.microsoft.com/download/details.aspx?id=46703)下載中心Tag.zipSurface **Asset** Tag.zip，解壓縮 zip 檔案，然後將 AssetTag.exe 儲存到想要的資料夾 (在此範例中，C：\\assets) 。

    > [!NOTE]
    > 針對 Surface Pro X，請使用 ZIP**檔案AssetTag_x86**名為 AssetTag_x86的應用程式。

2. 以系統管理員角色開啟命令主控台，然後AssetTag.exe輸入工具的完整路徑。

3. 重新開機 Surface。

    > [!NOTE]
    > 設定資產標記之後，需要第二次重新開機，才能在 WMI 中顯示。

### <a name="asset-tag-tool-commands"></a>資產圖章工具命令

在下列範例中，AssetTag.exe C：\assets (本機電腦上儲存) 。

若要取得建議的資產標記，請執行**AssetTag -g：**

```console
C:\assets\AssetTag.exe -g
```

若要清除建議的資產標記，請執行 **AssetTag -s**：

```console
C:\assets\AssetTag.exe -s
```

若要設定建議的資產標記，請執行**AssetTag -s testassettag12：**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
>資產標記值必須包含 1 到 36 個字元。 有效的字元包括 A-Z、a-z、0-9、期間 (.) 及連字號 (-) 。

## <a name="managing-asset-tags"></a>管理資產標記

您可以在裝置資訊 (控制台> **修復**>進啟動> UEFI 設定中>現有資產標記 。) 

下圖顯示在 Surface Go 上執行資產圖章工具的結果。

![在 Surface Go 上執行 Surface 資產圖章工具的結果。](images/assettag-fig1.png)

> **圖 1。** 在 Surface Go 上執行 Surface 資產圖章工具的結果

或者，您也可以使用 WMI 查詢裝置上現有的資產標記：

 (Get-WmiObject -query "從 Win32_SystemEnclosure 選取 *") 

### <a name="example"></a>範例

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a>使用 PowerShell

您可以使用下列腳本來取得建議的值，並解譯任何錯誤。

```powershell
AssetTag -g \> $asset\_tag 2\> $error\_message  
$asset\_tag\_return\_code = $LASTEXITCODE  
$asset\_tag = $asset\_tag.Trim("\`r\`n")

if ($asset\_tag\_return\_code -eq 0) {  
Write-Output ("Good Tag = " + $asset\_tag)  
} else {  
Write-Output (  
"Failure: Code = " + $asset\_tag\_return\_code +  
"Tag = " + $asset\_tag +  
"Message = " + $error\_message)

}
```
