---
title: Surface 亮度控制
description: 本主題描述如何使用 Surface 亮度控制項 app 來管理銷售點和 kiosk 案例中的顯示亮度。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 197ed9fe1abc880779ad6bb0f85d2970086395f6
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831630"
---
# <span data-ttu-id="3736b-103">Surface 亮度控制</span><span class="sxs-lookup"><span data-stu-id="3736b-103">Surface Brightness Control</span></span>

<span data-ttu-id="3736b-104">在銷售點或其他「永不開啟」的展臺案例中部署 Surface 裝置時，您可以使用新的 Surface 亮度控制項 app 來優化電源管理。</span><span class="sxs-lookup"><span data-stu-id="3736b-104">When deploying Surface devices in point of sale or other “always-on” kiosk scenarios, you can optimize power management using the new Surface Brightness Control app.</span></span>

<span data-ttu-id="3736b-105">可供使用[Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)下載。</span><span class="sxs-lookup"><span data-stu-id="3736b-105">Available for download with [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
<span data-ttu-id="3736b-106">表面亮度控制項的設計目的是為了協助減少熱量負載並降低部署表面裝置的整體碳足跡大小。</span><span class="sxs-lookup"><span data-stu-id="3736b-106">Surface Brightness Control is designed to help reduce thermal load and lower the overall carbon footprint for deployed Surface devices.</span></span>
<span data-ttu-id="3736b-107">如果您打算從 [下載] 頁面只取得此工具，請在 [可用] 清單中選取檔案**Surface_Brightness_Control_v1.16.137.0.msi** 。</span><span class="sxs-lookup"><span data-stu-id="3736b-107">If you plan to get only this tool from the download page, select the file **Surface_Brightness_Control_v1.16.137.0.msi** in the available list.</span></span>
<span data-ttu-id="3736b-108">在不使用時，工具會自動將螢幕調暗，且包含下列設定選項：</span><span class="sxs-lookup"><span data-stu-id="3736b-108">The tool automatically dims the screen when not in use and includes the following configuration options:</span></span>

- <span data-ttu-id="3736b-109">變暗顯示前的不活動期。</span><span class="sxs-lookup"><span data-stu-id="3736b-109">Period of inactivity before dimming the display.</span></span>

- <span data-ttu-id="3736b-110">當灰色時的亮度等級。</span><span class="sxs-lookup"><span data-stu-id="3736b-110">Brightness level when dimmed.</span></span>

- <span data-ttu-id="3736b-111">使用時的最大亮度等級。</span><span class="sxs-lookup"><span data-stu-id="3736b-111">Maximum brightness level when in use.</span></span>

**<span data-ttu-id="3736b-112">執行表面亮度控制：</span><span class="sxs-lookup"><span data-stu-id="3736b-112">To run Surface Brightness Control:</span></span>**

- <span data-ttu-id="3736b-113">在目標裝置上安裝 surfacebrightnesscontrol.msi，表面亮度控制將會立即開始運作。</span><span class="sxs-lookup"><span data-stu-id="3736b-113">Install surfacebrightnesscontrol.msi on the target device and Surface Brightness Control will begin working immediately.</span></span>

## <span data-ttu-id="3736b-114">配置 Surface 亮度控制項</span><span class="sxs-lookup"><span data-stu-id="3736b-114">Configuring Surface Brightness Control</span></span>

<span data-ttu-id="3736b-115">您可以透過 Windows Registry 調整預設值。</span><span class="sxs-lookup"><span data-stu-id="3736b-115">You can adjust the default values via the Windows Registry.</span></span> <span data-ttu-id="3736b-116">如需有關使用 Windows 登錄的詳細資訊，請參閱[註冊檔](https://docs.microsoft.com/windows/desktop/sysinfo/registry)。</span><span class="sxs-lookup"><span data-stu-id="3736b-116">For more information about using the Windows Registry, refer to the [Registry documentation](https://docs.microsoft.com/windows/desktop/sysinfo/registry).</span></span>

1.  <span data-ttu-id="3736b-117">從命令提示字元執行 regedit，以開啟 Windows 登錄編輯程式。</span><span class="sxs-lookup"><span data-stu-id="3736b-117">Run regedit from a command prompt to open the Windows Registry Editor.</span></span>
    
      - <span data-ttu-id="3736b-118">Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface 亮度控制 </span><span class="sxs-lookup"><span data-stu-id="3736b-118">Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface Brightness Control</span></span>\ 
    
    <span data-ttu-id="3736b-119">如果您執行的是舊版 Surface 亮度控制，請改為執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="3736b-119">If you're running an older version of Surface Brightness control, run the following command instead:</span></span>
    
      - <span data-ttu-id="3736b-120">Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\Microsoft\Surface\Surface 亮度控制 </span><span class="sxs-lookup"><span data-stu-id="3736b-120">Computer\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\Surface Brightness Control</span></span>\


| <span data-ttu-id="3736b-121">註冊表設定</span><span class="sxs-lookup"><span data-stu-id="3736b-121">Registry Setting</span></span> | <span data-ttu-id="3736b-122">資料</span><span class="sxs-lookup"><span data-stu-id="3736b-122">Data</span></span>| <span data-ttu-id="3736b-123">描述</span><span class="sxs-lookup"><span data-stu-id="3736b-123">Description</span></span>  
|-----------|------------|---------------
| <span data-ttu-id="3736b-124">已啟用亮度控制</span><span class="sxs-lookup"><span data-stu-id="3736b-124">Brightness Control Enabled</span></span>  |  <span data-ttu-id="3736b-125">預設值：01</span><span class="sxs-lookup"><span data-stu-id="3736b-125">Default: 01</span></span>  <br> <span data-ttu-id="3736b-126">選項：01，00</span><span class="sxs-lookup"><span data-stu-id="3736b-126">Option: 01, 00</span></span> <br> <span data-ttu-id="3736b-127">類型： REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="3736b-127">Type: REG_BINARY</span></span> |  <span data-ttu-id="3736b-128">此設定可讓您開啟或關閉表面亮度控制。</span><span class="sxs-lookup"><span data-stu-id="3736b-128">This setting allows you to turn Surface Brightness Control on or off.</span></span> <span data-ttu-id="3736b-129">若要停用 Surface 亮度控制，請將值設定為00。</span><span class="sxs-lookup"><span data-stu-id="3736b-129">To disable Surface Brightness Control, set the value to 00.</span></span> <span data-ttu-id="3736b-130">如果您未設定此設定，就會開啟 [Surface 亮度] 控制項。</span><span class="sxs-lookup"><span data-stu-id="3736b-130">If you do not configure this setting, Surface Brightness Control is on.</span></span> |
| <span data-ttu-id="3736b-131">已啟用電源上的亮度控制</span><span class="sxs-lookup"><span data-stu-id="3736b-131">Brightness Control On Power Enabled</span></span>| <span data-ttu-id="3736b-132">預設值：01</span><span class="sxs-lookup"><span data-stu-id="3736b-132">Default: 01</span></span> <br> <span data-ttu-id="3736b-133">選項：01，00</span><span class="sxs-lookup"><span data-stu-id="3736b-133">Options: 01, 00</span></span> <br> <span data-ttu-id="3736b-134">類型： REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="3736b-134">Type: REG_BINARY</span></span> | <span data-ttu-id="3736b-135">此設定可讓您在裝置與電源直接連線時，關閉表面亮度控制。</span><span class="sxs-lookup"><span data-stu-id="3736b-135">This setting allows you to turn off Surface Brightness Control when the device is directly connected to power.</span></span> <span data-ttu-id="3736b-136">若要在電源電源開啟時停用表面亮度控制，請將值設定為00。</span><span class="sxs-lookup"><span data-stu-id="3736b-136">To disable Surface Brightness Control when power is plugged in, set the value to 00.</span></span> <span data-ttu-id="3736b-137">如果您未設定此設定，就會開啟 [Surface 亮度] 控制項。</span><span class="sxs-lookup"><span data-stu-id="3736b-137">If you do not configure this setting, Surface Brightness Control is on.</span></span> |
| <span data-ttu-id="3736b-138">亮度暗淡</span><span class="sxs-lookup"><span data-stu-id="3736b-138">Dimmed Brightness</span></span>   | <span data-ttu-id="3736b-139">預設值：20</span><span class="sxs-lookup"><span data-stu-id="3736b-139">Default: 20</span></span>  <br><span data-ttu-id="3736b-140">選項：0-100% 的螢幕亮度範圍</span><span class="sxs-lookup"><span data-stu-id="3736b-140">Option: Range of 0-100 percent of screen brightness</span></span> <br> <span data-ttu-id="3736b-141">資料類型：正整數</span><span class="sxs-lookup"><span data-stu-id="3736b-141">Data Type: Positive integer</span></span> <br> <span data-ttu-id="3736b-142">類型： REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="3736b-142">Type: REG_DWORD</span></span> | <span data-ttu-id="3736b-143">此設定可讓您在不活動期間管理亮度範圍。</span><span class="sxs-lookup"><span data-stu-id="3736b-143">This setting allows you to manage brightness range during periods of inactivity.</span></span> <span data-ttu-id="3736b-144">如果您未設定此設定，亮度等級將會下降為30秒無啟用時間之後的全部亮度的20%。</span><span class="sxs-lookup"><span data-stu-id="3736b-144">If you do not configure this setting, the brightness level will drop to 20 percent of full brightness after 30 seconds of inactivity.</span></span> |
<span data-ttu-id="3736b-145">全亮度</span><span class="sxs-lookup"><span data-stu-id="3736b-145">Full Brightness</span></span>   | <span data-ttu-id="3736b-146">預設：100</span><span class="sxs-lookup"><span data-stu-id="3736b-146">Default: 100</span></span>  <br><span data-ttu-id="3736b-147">選項：0-100% 的螢幕亮度範圍</span><span class="sxs-lookup"><span data-stu-id="3736b-147">Option: Range of 0-100 percent of screen brightness</span></span> <br> <span data-ttu-id="3736b-148">資料類型：正整數</span><span class="sxs-lookup"><span data-stu-id="3736b-148">Data Type: Positive integer</span></span> <br> <span data-ttu-id="3736b-149">類型： REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="3736b-149">Type: REG_DWORD</span></span>  | <span data-ttu-id="3736b-150">此設定可讓您管理裝置的最大亮度範圍。</span><span class="sxs-lookup"><span data-stu-id="3736b-150">This setting allows you to manage the maximum brightness range for the device.</span></span> <span data-ttu-id="3736b-151">如果您未設定此設定，最大亮度範圍為100%。</span><span class="sxs-lookup"><span data-stu-id="3736b-151">If you do not configure this setting, the maximum brightness range is 100 percent.</span></span>|  
| <span data-ttu-id="3736b-152">閒置逾時</span><span class="sxs-lookup"><span data-stu-id="3736b-152">Inactivity Timeout</span></span>| <span data-ttu-id="3736b-153">預設值：30秒</span><span class="sxs-lookup"><span data-stu-id="3736b-153">Default: 30 seconds</span></span> <br><span data-ttu-id="3736b-154">選項：任何數位值</span><span class="sxs-lookup"><span data-stu-id="3736b-154">Option: Any numeric value</span></span>  <br><span data-ttu-id="3736b-155">資料類型： Integer</span><span class="sxs-lookup"><span data-stu-id="3736b-155">Data Type: Integer</span></span>  <br> <span data-ttu-id="3736b-156">類型： REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="3736b-156">Type: REG_DWORD</span></span> | <span data-ttu-id="3736b-157">此設定可讓您管理裝置變暗前的非活動期。</span><span class="sxs-lookup"><span data-stu-id="3736b-157">This setting allows you to manage the period of inactivity before dimming the device.</span></span> <span data-ttu-id="3736b-158">如果您未設定此設定，非活動超時為30秒。</span><span class="sxs-lookup"><span data-stu-id="3736b-158">If you do not configure this setting, the inactivity timeout is 30 seconds.</span></span>|
| <span data-ttu-id="3736b-159">已啟用遙測</span><span class="sxs-lookup"><span data-stu-id="3736b-159">Telemetry  Enabled</span></span> | <span data-ttu-id="3736b-160">預設值：01</span><span class="sxs-lookup"><span data-stu-id="3736b-160">Default: 01</span></span> <br><span data-ttu-id="3736b-161">選項：01，00</span><span class="sxs-lookup"><span data-stu-id="3736b-161">Option: 01, 00</span></span> <br> <span data-ttu-id="3736b-162">類型： REG_BINARY</span><span class="sxs-lookup"><span data-stu-id="3736b-162">Type: REG_BINARY</span></span>  | <span data-ttu-id="3736b-163">此設定可讓您管理 app 使用方式資訊的共用，以改善軟體並提供更佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="3736b-163">This setting allows you to manage the sharing of app usage information to improve software and provide better user experience.</span></span> <span data-ttu-id="3736b-164">若要停用遙測，請將值設定為00。</span><span class="sxs-lookup"><span data-stu-id="3736b-164">To disable telemetry, set the value to 00.</span></span> <span data-ttu-id="3736b-165">如果您未設定此設定，則會依照[Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)與 microsoft 共用遙測資訊。</span><span class="sxs-lookup"><span data-stu-id="3736b-165">If you do not configure this setting, telemetry information is shared with Microsoft in accordance with the [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement).</span></span> |

## <span data-ttu-id="3736b-166">變更與更新</span><span class="sxs-lookup"><span data-stu-id="3736b-166">Changes and updates</span></span>

### <span data-ttu-id="3736b-167">版本1.16.137</span><span class="sxs-lookup"><span data-stu-id="3736b-167">Version 1.16.137</span></span><br>
*<span data-ttu-id="3736b-168">發行日期：2019年10月22日</span><span class="sxs-lookup"><span data-stu-id="3736b-168">Release Date: 22 October 2019</span></span>*<br>
<span data-ttu-id="3736b-169">這個版本的 Surface 亮度控制項會新增支援：針對 x86 重新編譯，新增 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3的支援。</span><span class="sxs-lookup"><span data-stu-id="3736b-169">This version of Surface Brightness Control adds support for the following: -Recompiled for x86, adding support for Surface Pro 7, Surface Pro X, and Surface Laptop 3.</span></span> 

### <span data-ttu-id="3736b-170">版本1.12.239。0</span><span class="sxs-lookup"><span data-stu-id="3736b-170">Version 1.12.239.0</span></span>
*<span data-ttu-id="3736b-171">發行日期：2019年4月26日</span><span class="sxs-lookup"><span data-stu-id="3736b-171">Release Date: 26 April 2019</span></span>*<br>
<span data-ttu-id="3736b-172">此版本的 Surface 亮度控制項可為下列專案新增支援：</span><span class="sxs-lookup"><span data-stu-id="3736b-172">This version of Surface Brightness Control adds support for the following:</span></span>
- <span data-ttu-id="3736b-173">觸控延遲修正程式。</span><span class="sxs-lookup"><span data-stu-id="3736b-173">Touch delay fixes.</span></span>


## <span data-ttu-id="3736b-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="3736b-174">Related topics</span></span>

- [<span data-ttu-id="3736b-175">電池限制設定</span><span class="sxs-lookup"><span data-stu-id="3736b-175">Battery limit setting</span></span>](battery-limit.md)
