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
# <span data-ttu-id="3440e-103">Surface 資產圖章工具</span><span class="sxs-lookup"><span data-stu-id="3440e-103">Surface Asset Tag Tool</span></span>

<span data-ttu-id="3440e-104">[Surface 資產標記] 是命令列介面（CLI）公用程式，可讓您查看、指派及修改 Surface 裝置的指派資產標記值。</span><span class="sxs-lookup"><span data-stu-id="3440e-104">Surface Asset Tag is a command line interface (CLI) utility that allows you to view, assign, and modify an assigned asset tag value for Surface devices.</span></span> <span data-ttu-id="3440e-105">它適用于 Surface Pro 3 和所有較新的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="3440e-105">It works on Surface Pro 3 and all newer Surface devices.</span></span>

## <span data-ttu-id="3440e-106">系統需求</span><span class="sxs-lookup"><span data-stu-id="3440e-106">System requirements</span></span>

- <span data-ttu-id="3440e-107">Surface Pro 3 或更新版本</span><span class="sxs-lookup"><span data-stu-id="3440e-107">Surface Pro 3 or later</span></span>

- <span data-ttu-id="3440e-108">UEFI 固件版本3.9.150.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="3440e-108">UEFI firmware version 3.9.150.0 or later</span></span>

## <span data-ttu-id="3440e-109">使用 Surface 資產標記</span><span class="sxs-lookup"><span data-stu-id="3440e-109">Using Surface Asset Tag</span></span> 

<span data-ttu-id="3440e-110">執行表面資產標記：</span><span class="sxs-lookup"><span data-stu-id="3440e-110">To run Surface Asset Tag:</span></span>

1.  <span data-ttu-id="3440e-111">在 Surface 裝置上，從[Microsoft 下載中心](https://www.microsoft.com/download/details.aspx?id=46703)下載**表面資產 Tag.zip** ，解壓縮 zip 檔案，然後將 AssetTag.exe 儲存在所需的資料夾中（在此範例中為 C:\\assets）。</span><span class="sxs-lookup"><span data-stu-id="3440e-111">On the Surface device, download **Surface Asset Tag.zip** from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=46703), extract the zip file, and save AssetTag.exe in desired folder (in this example, C:\\assets).</span></span>

    > [!NOTE]
    > <span data-ttu-id="3440e-112">針對 Surface Pro X，請在 ZIP 檔案中使用名為**AssetTag_x86**的應用程式。</span><span class="sxs-lookup"><span data-stu-id="3440e-112">For Surface Pro X, use the application named **AssetTag_x86**  in the ZIP file.</span></span> 

2.  <span data-ttu-id="3440e-113">以系統管理員身分開啟命令主控台，然後執行 AssetTag.exe，輸入工具的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="3440e-113">Open a command console as an Administrator and run AssetTag.exe, entering the full path to the tool.</span></span>

3.  <span data-ttu-id="3440e-114">重新開機表面。</span><span class="sxs-lookup"><span data-stu-id="3440e-114">Restart Surface.</span></span>

### <span data-ttu-id="3440e-115">資產圖章工具命令</span><span class="sxs-lookup"><span data-stu-id="3440e-115">Asset Tag tool commands</span></span>   
<span data-ttu-id="3440e-116">在下列範例中，AssetTag.exe 會儲存在本機電腦上的目錄中（C:\assets）。</span><span class="sxs-lookup"><span data-stu-id="3440e-116">In the following examples, AssetTag.exe is saved in a directory on a local machine (C:\assets).</span></span> 

<span data-ttu-id="3440e-117">若要取得建議的資產標記，請執行 AssetTag-g。</span><span class="sxs-lookup"><span data-stu-id="3440e-117">To get the proposed asset tag, run AssetTag -g.</span></span>

**<span data-ttu-id="3440e-118">範例</span><span class="sxs-lookup"><span data-stu-id="3440e-118">Example</span></span>**

   ```
 C:\assets\AssetTag.exe -g
  ```
 
 <span data-ttu-id="3440e-119">若要清除建議的資產標記，請執行 AssetTag-s。</span><span class="sxs-lookup"><span data-stu-id="3440e-119">To clear the proposed asset tag, run AssetTag -s.</span></span>
 
 **<span data-ttu-id="3440e-120">範例</span><span class="sxs-lookup"><span data-stu-id="3440e-120">Example</span></span>**
 
   ```
C:\assets\AssetTag.exe -s
  ```
<span data-ttu-id="3440e-121">若要設定建議的資產標記，請執行 AssetTag-s testassettag12。</span><span class="sxs-lookup"><span data-stu-id="3440e-121">To set the proposed asset tag, run AssetTag -s testassettag12.</span></span>

**<span data-ttu-id="3440e-122">範例</span><span class="sxs-lookup"><span data-stu-id="3440e-122">Example</span></span>**

```
C:\assets\AssetTag.exe -s testassettag12
```

>[!NOTE]
><span data-ttu-id="3440e-123">資產標記值必須包含1到36個字元。</span><span class="sxs-lookup"><span data-stu-id="3440e-123">The asset tag value must contain between 1 and 36 characters.</span></span> <span data-ttu-id="3440e-124">有效的字元包括 A-z、a-z、0-9、句點（.）及連字號（-）。</span><span class="sxs-lookup"><span data-stu-id="3440e-124">Valid characters include A-Z, a-z, 0-9, period (.) and hyphen (-).</span></span>


## <span data-ttu-id="3440e-125">管理資產標記</span><span class="sxs-lookup"><span data-stu-id="3440e-125">Managing asset tags</span></span>

<span data-ttu-id="3440e-126">您可以在 [裝置資訊] 下的 [UEFI 設定] （[**控制台] > > [高級 > 啟動**] 中，[立即重新開機]），查看現有資產標記。</span><span class="sxs-lookup"><span data-stu-id="3440e-126">You can view the existing asset tag in the UEFI settings under Device Information (**Control Panel > Recovery > Advanced Startup > Restart now**.)</span></span>

<span data-ttu-id="3440e-127">下圖顯示在表面上執行資產圖章工具的結果。</span><span class="sxs-lookup"><span data-stu-id="3440e-127">The figure below shows the results of running the Asset Tag Tool on Surface Go.</span></span>

![<span data-ttu-id="3440e-128">表面上執行的表面資產圖章工具的結果。</span><span class="sxs-lookup"><span data-stu-id="3440e-128">Results of running Surface Asset Tag tool on Surface Go.</span></span>
](images/assettag-fig1.png)

> **<span data-ttu-id="3440e-129">圖 1。</span><span class="sxs-lookup"><span data-stu-id="3440e-129">Figure 1.</span></span>** <span data-ttu-id="3440e-130">表面上執行的表面資產圖章工具結果</span><span class="sxs-lookup"><span data-stu-id="3440e-130">Results of running Surface Asset Tag tool on Surface Go</span></span>

<span data-ttu-id="3440e-131">或者，您可以使用 WMI 來查詢裝置上的現有資產標記：</span><span class="sxs-lookup"><span data-stu-id="3440e-131">Alternately, you can use WMI to query the existing asset tag on a device:</span></span>

<span data-ttu-id="3440e-132">（WmiObject-query "從 Win32_SystemEnclosure 選取 \*）</span><span class="sxs-lookup"><span data-stu-id="3440e-132">(Get-WmiObject -query “Select \* from Win32_SystemEnclosure”)</span></span>

**<span data-ttu-id="3440e-133">範例</span><span class="sxs-lookup"><span data-stu-id="3440e-133">Example</span></span>**

   ```
C:\Windows\System32> (Get-WmiObject -query “Select * from Win32_SystemEnclosure”)
  ```
  
### <span data-ttu-id="3440e-134">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="3440e-134">Using PowerShell</span></span>

<span data-ttu-id="3440e-135">您可以使用下列腳本來取得建議值並解釋任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="3440e-135">You can use the script below as a way of getting the proposed value and interpreting any errors.</span></span>

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
