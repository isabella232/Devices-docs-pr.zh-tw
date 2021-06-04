---
title: Surface Pro 3 進階 UEFI 安全性功能 (Surface)
description: 本文說明如何安裝及設定 v3.11.760.0 UEFI 更新，以啟用 Surface Pro 3 裝置額外的安全性選項。
ms.assetid: 90F790C0-E5FC-4482-AD71-60589E3C9C93
ms.reviewer: ''
manager: laurawi
keywords: security, features, configure, hardware, device, custom, script, update, 安全性, 功能, 設定, 硬體, 裝置, 自訂, 指令碼, 更新
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 6a5c53c3e161bd4c49069a0665896762ce587618
ms.sourcegitcommit: e9190a6fe68b8a7cd9b024aea4be9f885f0de388
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/10/2020
ms.locfileid: "11163182"
---
# Surface Pro 3 進階 UEFI 安全性功能


本文說明如何安裝及設定 v3.11.760.0 UEFI 更新，以啟用 Surface Pro 3 裝置額外的安全性選項。

為了處理 Surface 裝置的安全性控制細節，v3.11.760.0 UEFI 更新提供額外的安全性選項，讓您能夠停用特定硬體裝置或防止從特定裝置啟動。 在裝置上安裝 UEFI 更新之後，您可以手動設定，或執行指令碼來自動設定。

##  <a name="manually-install-the-uefi-update"></a>手動安裝 UEFI 更新


您必須先安裝 v3.11.760.0 UEFI 更新，才能設定 Surface 裝置的進階安全性功能。 如果您是從 Windows Update 接收更新，則系統已經自動安裝此更新。 如需如何使用 Windows Update 設定 Windows 自動更新的相關詳細資訊，請參閱[如何設定及使用 Windows 的自動更新](https://support.microsoft.com/kb/306525)。

若要在 Surface Pro 3 上更新 UEFI，您能以 Surface Pro 3 韌體和驅動程式套件之一部分的方式下載並安裝 Surface UEFI 更新。 這些韌體和驅動程式套件可從 Microsoft 下載中心上的 [Surface Pro 3 頁面](https://www.microsoft.com/download/details.aspx?id=38826)取得。 您可以在[下載 Surface 裝置的最新韌體和驅動程式](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)找到韌體和驅動程式套件的詳細資訊。 韌體和驅動程式套件將以獨立的 Windows Installer (.msi) 和封存 (.zip) 格式提供。 若要深入了解上述兩種格式，以及如何使用它們來更新驅動程式，請參閱[管理 Surface 的驅動程式和韌體更新](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates)。

##  <a name="manually-configure-additional-security-settings"></a>手動設定額外的安全性設定


>[!NOTE]
>若要進入 Surface 裝置的韌體設定，請先將裝置關機，按住**音量提高**按鈕，然後按下並放開**電源按紐**，當裝置開始開機之後再放開**音量提高**按鈕。

在 Surface 裝置上安裝 v3.11.760.0 UEFI 更新之後，即可使用名稱為 [Advanced Device Security]**** (進階裝置安全性) 的額外 UEFI 功能表。 如果您按一下這個功能表，會顯示下列選項：

| 選項         | 說明                                                                                                                                                                          | 可用的設定 (預設設定以粗體列出) |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| 網路開機   | 啟用或停用 Surface 裝置從網路開機的功能 (也稱為 PXE 開機)。                                                                            | **已啟用**、不可開機                   |
| 側邊 USB       | 啟用或停用 Surface 裝置側邊的 USB 連接埠。 此外，可以啟用 USB 連接埠，但不允許以其開機。                                                | **已啟用**、不可開機、已停用         |
| 擴充座連接埠   | 啟用或停用 Surface 擴充座上的連接埠。 此外，可以啟用擴充座，但封鎖以擴充座上的任何 USB 或乙太網路連接埠開機。 | **已啟用**、不可開機、已停用         |
| 前方攝影機   | 啟用或停用 Surface 裝置前方的攝影機。                                                                                                                   | **已啟用**、已停用                       |
| 後方攝影機    | 啟用或停用 Surface 裝置後方的攝影機。                                                                                                                    | **已啟用**、已停用                       |
| 內建音訊 | 啟用或停用 Surface 裝置上的音訊。                                                                                                                                     | **已啟用**、已停用                       |
| microSD        | 啟用或停用 Surface 裝置上的 microSD 插槽。                                                                                                                          | **已啟用**、已停用                       |
| WiFi           | 啟用或停用 Surface 裝置內建的 Wi-Fi 收發機。 此設定也會停用藍牙。                                                                              | **已啟用**、已停用                       |
| 藍牙      | 啟用或停用 Surface 裝置內建的藍牙收發機。                                                                                                        | **已啟用**、已停用                       |

 

##  <a name="automate-additional-security-settings"></a>自動化其他安全性設定


身為具備系統管理員權限的 IT 專業人員，您可以利用能在 Microsoft 下載中心取得的 [Surface Pro 3 韌體工具 (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038)，來自動化設定 UEFI 設定。 這些工具會安裝可從任何自訂的應用程式或指令碼呼叫的 .NET 組件。

**先決條件**

-   以下範例指令碼是利用前述的延伸模組，因此假設正受到管理的裝置已安裝該工具。
-   必須具有系統管理權限才能執行指令碼。
-   如果範例指令碼未經數位簽署，您必須先呼叫 Windows PowerShell 命令 [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) 才能執行範例指令碼。

**範例指令碼**

> [!NOTE]
> 以下範例指令碼中所使用的 UEFI 密碼會以純文字呈現。 我們強烈建議您將指令碼儲存在受保護的位置，並於受控制的環境中執行。


顯示所有可設定的選項：

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
foreach ($uefiOption in $uefiOptions) 
{ 
    Write-Host "Name:" $uefiOption.Name 
    Write-Host " Description =" $uefiOption.Description 
    Write-Host " Current Value =" $uefiOption.CurrentValue 
    Write-Host " Default Value =" $uefiOption.DefaultValue 
    Write-Host " Proposed Value =" $uefiOption.ProposedValue 
     
    # This gives usage and validation information 
    Write-Host " Allowed Values =" $uefiOption.FriendlyRegEx 
    Write-Host " Regular Expression =" $uefiOption.RegEx 
     
    Write-Host 
}
```

設定或變更 UEFI 密碼：

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

查看所建議之變更的狀態：

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Check update status 
$updateStatus = [Microsoft.Surface.FirmwareOption]::UpdateStatus 
$updateIteration = [Microsoft.Surface.FirmwareOption]::UpdateIteration 
Write-Host "Last Update Status =" $updateStatus 
Write-Host "Last Update Iteration =" $updateIteration 
 
# Get the individual results for the last proposed update 
# If the device has never had an update attempt this will be an empty list 
$details = [Microsoft.Surface.FirmwareOption]::UpdateStatusDetails 
Write-Host $details.Count "Settings were proposed" 
if ($details.Count -gt 0) 
{ 
    Write-Host "Result Details" 
    foreach ($detail in $details.GetEnumerator()) 
    { 
        Write-Host " " $detail.Key "=" $detail.Value 
    } 
}
```

將 UEFI 還原為預設值：

```powershell
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
# Get the collection of all configurable settings 
$uefiOptions = [Microsoft.Surface.FirmwareOption]::All() 
 
# Reset all options to the factory default 
foreach ($uefiOption in $uefiOptions) 
{ 
    $uefiOption.ProposedValue = $uefiOption.DefaultValue 
}
```

狀態碼解讀

-   00 - 建議的更新已成功設定
-   02 - 其中一個建議值為無效值
-   03 - 無法辨識其中一組建議值
-   0F - 解除鎖定密碼與目前設定的密碼不符

 
