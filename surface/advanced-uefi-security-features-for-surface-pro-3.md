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
ms.openlocfilehash: 9460b4a5e8b44cbf4b6af57d01aab3b09afb49de
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831312"
---
# <span data-ttu-id="dc408-104">Surface Pro 3 進階 UEFI 安全性功能</span><span class="sxs-lookup"><span data-stu-id="dc408-104">Advanced UEFI security features for Surface Pro 3</span></span>


<span data-ttu-id="dc408-105">本文說明如何安裝及設定 v3.11.760.0 UEFI 更新，以啟用 Surface Pro 3 裝置額外的安全性選項。</span><span class="sxs-lookup"><span data-stu-id="dc408-105">This article describes how to install and configure the v3.11.760.0 UEFI update to enable additional security options for Surface Pro 3 devices.</span></span>

<span data-ttu-id="dc408-106">為了處理 Surface 裝置的安全性控制細節，v3.11.760.0 UEFI 更新提供額外的安全性選項，讓您能夠停用特定硬體裝置或防止從特定裝置啟動。</span><span class="sxs-lookup"><span data-stu-id="dc408-106">To address more granular control over the security of Surface devices, the v3.11.760.0 UEFI update provides additional security options that allow you to disable specific hardware devices or to prevent starting from those devices.</span></span> <span data-ttu-id="dc408-107">在裝置上安裝 UEFI 更新之後，您可以手動設定，或執行指令碼來自動設定。</span><span class="sxs-lookup"><span data-stu-id="dc408-107">After the UEFI update is installed on a device, you can configure it manually or automatically by running a script.</span></span>

## <span data-ttu-id="dc408-108">手動安裝 UEFI 更新</span><span class="sxs-lookup"><span data-stu-id="dc408-108">Manually install the UEFI update</span></span>


<span data-ttu-id="dc408-109">您必須先安裝 v3.11.760.0 UEFI 更新，才能設定 Surface 裝置的進階安全性功能。</span><span class="sxs-lookup"><span data-stu-id="dc408-109">Before you can configure the advanced security features of your Surface device, you must first install the v3.11.760.0 UEFI update.</span></span> <span data-ttu-id="dc408-110">如果您是從 Windows Update 接收更新，則系統已經自動安裝此更新。</span><span class="sxs-lookup"><span data-stu-id="dc408-110">This update is installed automatically if you receive your updates from Windows Update.</span></span> <span data-ttu-id="dc408-111">如需如何使用 Windows Update 設定 Windows 自動更新的相關詳細資訊，請參閱[如何設定及使用 Windows 的自動更新](https://support.microsoft.com/kb/306525)。</span><span class="sxs-lookup"><span data-stu-id="dc408-111">For more information about how to configure Windows to update automatically by using Windows Update, see [How to configure and use Automatic Updates in Windows](https://support.microsoft.com/kb/306525).</span></span>

<span data-ttu-id="dc408-112">若要在 Surface Pro 3 上更新 UEFI，您能以 Surface Pro 3 韌體和驅動程式套件之一部分的方式下載並安裝 Surface UEFI 更新。</span><span class="sxs-lookup"><span data-stu-id="dc408-112">To update the UEFI on Surface Pro 3, you can download and install the Surface UEFI updates as part of the Surface Pro 3 Firmware and Driver Pack.</span></span> <span data-ttu-id="dc408-113">這些韌體和驅動程式套件可從 Microsoft 下載中心上的 [Surface Pro 3 頁面](https://www.microsoft.com/download/details.aspx?id=38826)取得。</span><span class="sxs-lookup"><span data-stu-id="dc408-113">These firmware and driver packs are available from the [Surface Pro 3 page](https://www.microsoft.com/download/details.aspx?id=38826) on the Microsoft Download Center.</span></span> <span data-ttu-id="dc408-114">您可以在[下載 Surface 裝置的最新韌體和驅動程式](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices)找到韌體和驅動程式套件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="dc408-114">You can find out more about the firmware and driver packs at [Download the latest firmware and drivers for Surface devices](https://technet.microsoft.com/itpro/surface/deploy-the-latest-firmware-and-drivers-for-surface-devices).</span></span> <span data-ttu-id="dc408-115">韌體和驅動程式套件將以獨立的 Windows Installer (.msi) 和封存 (.zip) 格式提供。</span><span class="sxs-lookup"><span data-stu-id="dc408-115">The firmware and driver packs are available as both self-contained Windows Installer (.msi) and archive (.zip) formats.</span></span> <span data-ttu-id="dc408-116">若要深入了解上述兩種格式，以及如何使用它們來更新驅動程式，請參閱[管理 Surface 的驅動程式和韌體更新](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates)。</span><span class="sxs-lookup"><span data-stu-id="dc408-116">You can find out more about these two formats and how you can use them to update your drivers at [Manage Surface driver and firmware updates](https://technet.microsoft.com/itpro/surface/manage-surface-pro-3-firmware-updates).</span></span>

## <span data-ttu-id="dc408-117">手動設定額外的安全性設定</span><span class="sxs-lookup"><span data-stu-id="dc408-117">Manually configure additional security settings</span></span>


>[!NOTE]
><span data-ttu-id="dc408-118">若要進入 Surface 裝置的韌體設定，請先將裝置關機，按住**音量提高**按鈕，然後按下並放開**電源按紐**，當裝置開始開機之後再放開**音量提高**按鈕。</span><span class="sxs-lookup"><span data-stu-id="dc408-118">To enter firmware setup on a Surface device, begin with the device powered off, press and hold the **Volume Up** button, then press and release the **Power** button, then release the **Volume Up** button after the device has begun to boot.</span></span>

<span data-ttu-id="dc408-119">在 Surface 裝置上安裝 v3.11.760.0 UEFI 更新之後，即可使用名稱為 [Advanced Device Security]\*\*\*\* (進階裝置安全性) 的額外 UEFI 功能表。</span><span class="sxs-lookup"><span data-stu-id="dc408-119">After the v3.11.760.0 UEFI update is installed on a Surface device, an additional UEFI menu named **Advanced Device Security** becomes available.</span></span> <span data-ttu-id="dc408-120">如果您按一下這個功能表，會顯示下列選項：</span><span class="sxs-lookup"><span data-stu-id="dc408-120">If you click this menu, the following options are displayed:</span></span>

| <span data-ttu-id="dc408-121">選項</span><span class="sxs-lookup"><span data-stu-id="dc408-121">Option</span></span>         | <span data-ttu-id="dc408-122">說明</span><span class="sxs-lookup"><span data-stu-id="dc408-122">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="dc408-123">可用的設定 (預設設定以粗體列出)</span><span class="sxs-lookup"><span data-stu-id="dc408-123">Available settings (default listed in bold)</span></span> |
|----------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------|
| <span data-ttu-id="dc408-124">網路開機</span><span class="sxs-lookup"><span data-stu-id="dc408-124">Network Boot</span></span>   | <span data-ttu-id="dc408-125">啟用或停用 Surface 裝置從網路開機的功能 (也稱為 PXE 開機)。</span><span class="sxs-lookup"><span data-stu-id="dc408-125">Enables or disables the ability of your Surface device to boot from the network (also known as PXE boot).</span></span>                                                                            | <span data-ttu-id="dc408-126">**已啟用**、不可開機</span><span class="sxs-lookup"><span data-stu-id="dc408-126">**Enabled**, Not Bootable</span></span>                   |
| <span data-ttu-id="dc408-127">側邊 USB</span><span class="sxs-lookup"><span data-stu-id="dc408-127">Side USB</span></span>       | <span data-ttu-id="dc408-128">啟用或停用 Surface 裝置側邊的 USB 連接埠。</span><span class="sxs-lookup"><span data-stu-id="dc408-128">Enables or disables the USB port on the side of the Surface device.</span></span> <span data-ttu-id="dc408-129">此外，可以啟用 USB 連接埠，但不允許以其開機。</span><span class="sxs-lookup"><span data-stu-id="dc408-129">Additionally, the USB port can be enabled, but not allow booting.</span></span>                                                | <span data-ttu-id="dc408-130">**已啟用**、不可開機、已停用</span><span class="sxs-lookup"><span data-stu-id="dc408-130">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="dc408-131">擴充座連接埠</span><span class="sxs-lookup"><span data-stu-id="dc408-131">Docking Port</span></span>   | <span data-ttu-id="dc408-132">啟用或停用 Surface 擴充座上的連接埠。</span><span class="sxs-lookup"><span data-stu-id="dc408-132">Enables or disables the ports on the Surface docking station.</span></span> <span data-ttu-id="dc408-133">此外，可以啟用擴充座，但封鎖以擴充座上的任何 USB 或乙太網路連接埠開機。</span><span class="sxs-lookup"><span data-stu-id="dc408-133">Additionally, the docking port can be enabled, but block booting from any USB or Ethernet port in the docking station.</span></span> | <span data-ttu-id="dc408-134">**已啟用**、不可開機、已停用</span><span class="sxs-lookup"><span data-stu-id="dc408-134">**Enabled**, Not Bootable, Disabled</span></span>         |
| <span data-ttu-id="dc408-135">前方攝影機</span><span class="sxs-lookup"><span data-stu-id="dc408-135">Front Camera</span></span>   | <span data-ttu-id="dc408-136">啟用或停用 Surface 裝置前方的攝影機。</span><span class="sxs-lookup"><span data-stu-id="dc408-136">Enables or disables the camera on the front of the Surface device.</span></span>                                                                                                                   | <span data-ttu-id="dc408-137">**已啟用**、已停用</span><span class="sxs-lookup"><span data-stu-id="dc408-137">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="dc408-138">後方攝影機</span><span class="sxs-lookup"><span data-stu-id="dc408-138">Rear Camera</span></span>    | <span data-ttu-id="dc408-139">啟用或停用 Surface 裝置後方的攝影機。</span><span class="sxs-lookup"><span data-stu-id="dc408-139">Enables or disables the camera on the rear of the Surface device.</span></span>                                                                                                                    | <span data-ttu-id="dc408-140">**已啟用**、已停用</span><span class="sxs-lookup"><span data-stu-id="dc408-140">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="dc408-141">內建音訊</span><span class="sxs-lookup"><span data-stu-id="dc408-141">On Board Audio</span></span> | <span data-ttu-id="dc408-142">啟用或停用 Surface 裝置上的音訊。</span><span class="sxs-lookup"><span data-stu-id="dc408-142">Enables or disables audio on the Surface device.</span></span>                                                                                                                                     | <span data-ttu-id="dc408-143">**已啟用**、已停用</span><span class="sxs-lookup"><span data-stu-id="dc408-143">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="dc408-144">microSD</span><span class="sxs-lookup"><span data-stu-id="dc408-144">microSD</span></span>        | <span data-ttu-id="dc408-145">啟用或停用 Surface 裝置上的 microSD 插槽。</span><span class="sxs-lookup"><span data-stu-id="dc408-145">Enables or disables the microSD slot on the Surface device.</span></span>                                                                                                                          | <span data-ttu-id="dc408-146">**已啟用**、已停用</span><span class="sxs-lookup"><span data-stu-id="dc408-146">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="dc408-147">WiFi</span><span class="sxs-lookup"><span data-stu-id="dc408-147">WiFi</span></span>           | <span data-ttu-id="dc408-148">啟用或停用 Surface 裝置內建的 Wi-Fi 收發機。</span><span class="sxs-lookup"><span data-stu-id="dc408-148">Enables or disables the built-in Wi-Fi transceiver in the Surface device.</span></span> <span data-ttu-id="dc408-149">此設定也會停用藍牙。</span><span class="sxs-lookup"><span data-stu-id="dc408-149">This also disables Bluetooth.</span></span>                                                                              | <span data-ttu-id="dc408-150">**已啟用**、已停用</span><span class="sxs-lookup"><span data-stu-id="dc408-150">**Enabled**, Disabled</span></span>                       |
| <span data-ttu-id="dc408-151">藍牙</span><span class="sxs-lookup"><span data-stu-id="dc408-151">Bluetooth</span></span>      | <span data-ttu-id="dc408-152">啟用或停用 Surface 裝置內建的藍牙收發機。</span><span class="sxs-lookup"><span data-stu-id="dc408-152">Enables or disables the built-in Bluetooth transceiver in the Surface device.</span></span>                                                                                                        | <span data-ttu-id="dc408-153">**已啟用**、已停用</span><span class="sxs-lookup"><span data-stu-id="dc408-153">**Enabled**, Disabled</span></span>                       |

 

## <span data-ttu-id="dc408-154">自動化其他安全性設定</span><span class="sxs-lookup"><span data-stu-id="dc408-154">Automate additional security settings</span></span>


<span data-ttu-id="dc408-155">身為具備系統管理員權限的 IT 專業人員，您可以利用能在 Microsoft 下載中心取得的 [Surface Pro 3 韌體工具 (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038)，來自動化設定 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="dc408-155">As an IT professional with administrative privileges, you can automate the configuration of UEFI settings by leveraging [Surface Pro 3 Firmware Tools (476 KB)](https://go.microsoft.com/fwlink/p/?LinkID=618038) available from the Microsoft Download Center.</span></span> <span data-ttu-id="dc408-156">這些工具會安裝可從任何自訂的應用程式或指令碼呼叫的 .NET 組件。</span><span class="sxs-lookup"><span data-stu-id="dc408-156">These tools install a .NET assembly that can be called from any custom application or script.</span></span>

**<span data-ttu-id="dc408-157">先決條件</span><span class="sxs-lookup"><span data-stu-id="dc408-157">Prerequisites</span></span>**

-   <span data-ttu-id="dc408-158">以下範例指令碼是利用前述的延伸模組，因此假設正受到管理的裝置已安裝該工具。</span><span class="sxs-lookup"><span data-stu-id="dc408-158">The sample scripts below leverage the previously mentioned extension and therefore assume that the tool has been installed on the device being managed.</span></span>
-   <span data-ttu-id="dc408-159">必須具有系統管理權限才能執行指令碼。</span><span class="sxs-lookup"><span data-stu-id="dc408-159">The scripts must be run with administrative privilege.</span></span>
-   <span data-ttu-id="dc408-160">如果範例指令碼未經數位簽署，您必須先呼叫 Windows PowerShell 命令 [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) 才能執行範例指令碼。</span><span class="sxs-lookup"><span data-stu-id="dc408-160">The Windows PowerShell command [**Set-ExecutionPolicy Unrestricted**](https://technet.microsoft.com/library/ee176961.aspx) must be called prior to running sample scripts if they are not digitally signed.</span></span>

**<span data-ttu-id="dc408-161">範例指令碼</span><span class="sxs-lookup"><span data-stu-id="dc408-161">Sample scripts</span></span>**

><span data-ttu-id="dc408-162">**注意**:&nbsp;&nbsp;以下範例指令碼中所使用的 UEFI 密碼會以純文字呈現。</span><span class="sxs-lookup"><span data-stu-id="dc408-162">**Note**:&nbsp;&nbsp;The UEFI password used in the sample scripts below is presented in clear text.</span></span> <span data-ttu-id="dc408-163">我們強烈建議您將指令碼儲存在受保護的位置，並於受控制的環境中執行。</span><span class="sxs-lookup"><span data-stu-id="dc408-163">We strongly recommend saving the scripts in a protected location and running them in a controlled environment.</span></span>


<span data-ttu-id="dc408-164">顯示所有可設定的選項：</span><span class="sxs-lookup"><span data-stu-id="dc408-164">Show all configurable options:</span></span>

```
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

<span data-ttu-id="dc408-165">設定或變更 UEFI 密碼：</span><span class="sxs-lookup"><span data-stu-id="dc408-165">Set or change UEFI password:</span></span>

```
# Load the extension 
[System.Reflection.Assembly]::Load("SurfaceUefiManager, Version=1.0.5483.22783, Culture=neutral, PublicKeyToken=20606f4b5276c705")  
 
# Must supply UEFI administrator Password if set 
# If it is not currently set this is ignored 
[Microsoft.Surface.FirmwareOption]::Unlock("1234") 
 
$Password = [Microsoft.Surface.FirmwareOption]::Find("Password") 
 
# Set New value to 12345 
$Password.ProposedValue = "12345"
```

<span data-ttu-id="dc408-166">查看所建議之變更的狀態：</span><span class="sxs-lookup"><span data-stu-id="dc408-166">Check status of proposed changes:</span></span>

```
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

<span data-ttu-id="dc408-167">將 UEFI 還原為預設值：</span><span class="sxs-lookup"><span data-stu-id="dc408-167">Revert UEFI to default values:</span></span>

```
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

<span data-ttu-id="dc408-168">狀態碼解讀</span><span class="sxs-lookup"><span data-stu-id="dc408-168">Status code interpretation</span></span>

-   <span data-ttu-id="dc408-169">00 - 建議的更新已成功設定</span><span class="sxs-lookup"><span data-stu-id="dc408-169">00 - The proposed update was a success</span></span>
-   <span data-ttu-id="dc408-170">02 - 其中一個建議值為無效值</span><span class="sxs-lookup"><span data-stu-id="dc408-170">02 - One of the proposed values had an invalid value</span></span>
-   <span data-ttu-id="dc408-171">03 - 無法辨識其中一組建議值</span><span class="sxs-lookup"><span data-stu-id="dc408-171">03 - There was a proposed value set that was not recognized</span></span>
-   <span data-ttu-id="dc408-172">0F - 解除鎖定密碼與目前設定的密碼不符</span><span class="sxs-lookup"><span data-stu-id="dc408-172">0F - The unlock password did not match currently set password</span></span>

 

 





