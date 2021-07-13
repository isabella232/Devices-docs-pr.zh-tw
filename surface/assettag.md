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
# <a name="surface-asset-tag-tool"></a><span data-ttu-id="41d29-103">Surface 資產圖章工具</span><span class="sxs-lookup"><span data-stu-id="41d29-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="41d29-104">Surface Asset Tag 是 CLI (工具) 介面，可讓您查看、指派及修改 Surface 裝置指派的資產標記值。</span><span class="sxs-lookup"><span data-stu-id="41d29-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="41d29-105">它適用于 Surface Pro 3 及所有較新的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="41d29-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="41d29-106">系統需求</span><span class="sxs-lookup"><span data-stu-id="41d29-106">System requirements</span></span>

- <span data-ttu-id="41d29-107">Surface Pro 3 或更高版本</span><span class="sxs-lookup"><span data-stu-id="41d29-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="41d29-108">UEFI 固件版本 3.9.150.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="41d29-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <a name="using-surface-asset-tag"></a><span data-ttu-id="41d29-109">使用 Surface 資產標記</span><span class="sxs-lookup"><span data-stu-id="41d29-109">Using Surface Asset Tag</span></span>

<span data-ttu-id="41d29-110">若要執行 Surface 資產標記：</span><span class="sxs-lookup"><span data-stu-id="41d29-110">To run Surface Asset Tag:</span></span>

1. <span data-ttu-id="41d29-111">在 Surface 裝置上，從[Microsoft](https://www.microsoft.com/download/details.aspx?id=46703)下載中心Tag.zipSurface **Asset** Tag.zip，解壓縮 zip 檔案，然後將 AssetTag.exe 儲存到想要的資料夾 (在此範例中，C：\\assets) 。</span><span class="sxs-lookup"><span data-stu-id="41d29-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download  Center](https://www.microsoft.com/download/details.aspx?id=46703),  extract the zip file, and save AssetTag.exe in desired folder (in  this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="41d29-112">針對 Surface Pro X，請使用 ZIP**檔案AssetTag_x86**名為 AssetTag_x86的應用程式。</span><span class="sxs-lookup"><span data-stu-id="41d29-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span>

2. <span data-ttu-id="41d29-113">以系統管理員角色開啟命令主控台，然後AssetTag.exe輸入工具的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="41d29-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3. <span data-ttu-id="41d29-114">重新開機 Surface。</span><span class="sxs-lookup"><span data-stu-id="41d29-114">Restart Surface.</span></span>

    > [!NOTE]
    > <span data-ttu-id="41d29-115">設定資產標記之後，需要第二次重新開機，才能在 WMI 中顯示。</span><span class="sxs-lookup"><span data-stu-id="41d29-115">After setting the asset tag, a second reboot is required before it appears in WMI.</span></span>

### <a name="asset-tag-tool-commands"></a><span data-ttu-id="41d29-116">資產圖章工具命令</span><span class="sxs-lookup"><span data-stu-id="41d29-116">Asset Tag tool commands</span></span>

<span data-ttu-id="41d29-117">在下列範例中，AssetTag.exe C：\assets (本機電腦上儲存) 。</span><span class="sxs-lookup"><span data-stu-id="41d29-117">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span>

<span data-ttu-id="41d29-118">若要取得建議的資產標記，請執行**AssetTag -g：**</span><span class="sxs-lookup"><span data-stu-id="41d29-118">To get the proposed asset tag, run **AssetTag -g**:</span></span>

```console
C:\assets\AssetTag.exe -g
```

<span data-ttu-id="41d29-119">若要清除建議的資產標記，請執行 **AssetTag -s**：</span><span class="sxs-lookup"><span data-stu-id="41d29-119">To clear the proposed asset tag, run **AssetTag -s**:</span></span>

```console
C:\assets\AssetTag.exe -s
```

<span data-ttu-id="41d29-120">若要設定建議的資產標記，請執行**AssetTag -s testassettag12：**</span><span class="sxs-lookup"><span data-stu-id="41d29-120">To set the proposed asset tag, run **AssetTag -s testassettag12**:</span></span>

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="41d29-121">資產標記值必須包含 1 到 36 個字元。</span><span class="sxs-lookup"><span data-stu-id="41d29-121">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="41d29-122">有效的字元包括 A-Z、a-z、0-9、期間 (.) 及連字號 (-) 。</span><span class="sxs-lookup"><span data-stu-id="41d29-122">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>

## <a name="managing-asset-tags"></a><span data-ttu-id="41d29-123">管理資產標記</span><span class="sxs-lookup"><span data-stu-id="41d29-123">Managing asset tags</span></span>

<span data-ttu-id="41d29-124">您可以在裝置資訊 (控制台> **修復**>進啟動> UEFI 設定中>現有資產標記 。) </span><span class="sxs-lookup"><span data-stu-id="41d29-124">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="41d29-125">下圖顯示在 Surface Go 上執行資產圖章工具的結果。</span><span class="sxs-lookup"><span data-stu-id="41d29-125">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![在 Surface Go 上執行 Surface 資產圖章工具的結果。](images/assettag-fig1.png)

> **<span data-ttu-id="41d29-127&quot;>圖 1。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;41d29-127&quot;>Figure 1.</span></span>** <span data-ttu-id=&quot;41d29-128&quot;>在 Surface Go 上執行 Surface 資產圖章工具的結果</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;41d29-128&quot;>Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id=&quot;41d29-129&quot;>或者，您也可以使用 WMI 查詢裝置上現有的資產標記：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;41d29-129&quot;>Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id=&quot;41d29-130&quot;> (Get-WmiObject -query &quot;從 Win32_SystemEnclosure 選取\ *") </span><span class="sxs-lookup"><span data-stu-id="41d29-130">(Get-WmiObject -query "Select \* from Win32_SystemEnclosure")</span></span>

### <a name="example"></a><span data-ttu-id="41d29-131">範例</span><span class="sxs-lookup"><span data-stu-id="41d29-131">Example</span></span>

```console
C:\Windows\System32> (Get-WmiObject -query "Select * from Win32_SystemEnclosure")
```
  
### <a name="using-powershell"></a><span data-ttu-id="41d29-132">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="41d29-132">Using PowerShell</span></span>

<span data-ttu-id="41d29-133">您可以使用下列腳本來取得建議的值，並解譯任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="41d29-133">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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
