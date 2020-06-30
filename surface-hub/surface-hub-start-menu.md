---
title: 設定 Surface Hub 的 [開始] 功能表
description: 使用 MDM 來自訂 Surface Hub 的 [開始] 功能表。
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
ms.topic: article
ms.date: 08/15/2018
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: c5b6a083d543649eab899d2fea36327d08f8bc29
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831253"
---
# <span data-ttu-id="95e29-103">設定 Surface Hub 的 [開始] 功能表</span><span class="sxs-lookup"><span data-stu-id="95e29-103">Configure Surface Hub Start menu</span></span>

<span data-ttu-id="95e29-104">[Windows 10 的 2018 年 1 月 17 日更新](https://support.microsoft.com/help/4057144) (組建 15063.877) 可在 Surface Hub 裝置上啟用自訂的 [開始] 功能表。</span><span class="sxs-lookup"><span data-stu-id="95e29-104">The [January 17, 2018 update to Windows 10](https://support.microsoft.com/help/4057144) (build 15063.877) enables customized Start menus on Surface Hub devices.</span></span> <span data-ttu-id="95e29-105">您可以使用行動裝置管理 (MDM) 來套用自訂的 [開始] 功能表配置。</span><span class="sxs-lookup"><span data-stu-id="95e29-105">You apply the customized Start menu layout using mobile device management (MDM).</span></span>

<span data-ttu-id="95e29-106">當您將自訂的 [開始] 功能表配置套用至 Surface Hub 時，使用者無法從開始畫面釘選、取消釘選，或解除安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="95e29-106">When you apply a customized Start menu layout to Surface Hub, users cannot pin, unpin, or uninstall apps from Start.</span></span> 

## <span data-ttu-id="95e29-107">如何將自訂的 [開始] 功能表套用至 Surface Hub</span><span class="sxs-lookup"><span data-stu-id="95e29-107">How to apply a customized Start menu to Surface Hub</span></span>

<span data-ttu-id="95e29-108">自訂的 [開始] 功能表是在開始畫面配置 XML 檔案中定義。</span><span class="sxs-lookup"><span data-stu-id="95e29-108">The customized Start menu is defined in a Start layout XML file.</span></span> <span data-ttu-id="95e29-109">您有兩個建立開始畫面配置 XML 檔案的選項：</span><span class="sxs-lookup"><span data-stu-id="95e29-109">You have two options for creating your Start layout XML file:</span></span>

- <span data-ttu-id="95e29-110">編輯[預設 Surface Hub 開始畫面 XML](#default)</span><span class="sxs-lookup"><span data-stu-id="95e29-110">Edit the [default Surface Hub Start XML](#default)</span></span>

    <span data-ttu-id="95e29-111">- 或 -</span><span class="sxs-lookup"><span data-stu-id="95e29-111">-or-</span></span>

- <span data-ttu-id="95e29-112">在電腦上設定想要的 [開始] 功能表 (僅釘選 Surface Hub 上提供的應用程式)，然後[匯出配置](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout)。</span><span class="sxs-lookup"><span data-stu-id="95e29-112">Configure the desired Start menu on a desktop (pinning only apps that are available on Surface Hub), and then [export the layout](https://docs.microsoft.com/windows/configuration/customize-and-export-start-layout#export-the-start-layout).</span></span>

>[!TIP]
><span data-ttu-id="95e29-113">若要新增有 Web 連結的磚到電腦的 [開始] 功能表，請移至 Microsoft Edge 中的連結、選取右上角的 `...`，然後選取 **\[將此頁面釘選到開始畫面\]**。</span><span class="sxs-lookup"><span data-stu-id="95e29-113">To add a tile with a web link to your desktop start menu, go to the link in Microsoft Edge, select `...` in the top right corner, and select **Pin this page to Start**.</span></span> <span data-ttu-id="95e29-114">如需連結如何顯示在 XML 中的範例，請參閱[包含 Microsoft Edge 連結的 \[開始\] 配置](#edge)。</span><span class="sxs-lookup"><span data-stu-id="95e29-114">See [a Start layout that includes a Microsoft Edge link](#edge) for an example of how links will appear in the XML.</span></span>

<span data-ttu-id="95e29-115">若要編輯預設 XML 或匯出的配置，請熟悉一下[開始畫面配置 XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop)。</span><span class="sxs-lookup"><span data-stu-id="95e29-115">To edit the default XML or the exported layout, familiarize yourself with the [Start layout XML](https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop).</span></span> <span data-ttu-id="95e29-116">有幾個[電腦與 Surface Hub 之間的開始畫面配置差異](#differences)</span><span class="sxs-lookup"><span data-stu-id="95e29-116">There are a few [differences between Start layout on a deskop and a Surface Hub.](#differences)</span></span>

<span data-ttu-id="95e29-117">您在開始畫面配置 XML 中定義 [開始] 功能表之後，[建立 MDM 原則以套用配置。](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span><span class="sxs-lookup"><span data-stu-id="95e29-117">When you have your Start menu defined in a Start layout XML, [create an MDM policy to apply the layout.](https://docs.microsoft.com/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)</span></span>

<span id="differences" />
## <span data-ttu-id="95e29-118">Surface Hub 與電腦 [開始] 功能表之間的差異</span><span class="sxs-lookup"><span data-stu-id="95e29-118">Differences between Surface Hub and desktop Start menu</span></span>

<span data-ttu-id="95e29-119">Surface Hub 與 Windows 10 電腦的 [開始] 功能表自訂之間有一些主要差異：</span><span class="sxs-lookup"><span data-stu-id="95e29-119">There are a few key differences between Start menu customization for Surface Hub and a Windows 10 desktop:</span></span>

- <span data-ttu-id="95e29-120">您無法使用**DesktopApplicationTile** （ https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) 在您的開始版面配置 XML 中，因為 Surface Hub 不支援 Windows 桌面應用程式（Win32）。</span><span class="sxs-lookup"><span data-stu-id="95e29-120">You cannot use **DesktopApplicationTile** (https://docs.microsoft.com/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile) in your Start layout XML because Windows desktop applications (Win32) are not supported on Surface Hub.</span></span>
- <span data-ttu-id="95e29-121">您無法使用開始畫面配置 XML 來設定 Surface Hub 的工作列或歡迎畫面。</span><span class="sxs-lookup"><span data-stu-id="95e29-121">You cannot use the Start layout XML to configure the taskbar or the Welcome screen for Surface Hub.</span></span>  
- <span data-ttu-id="95e29-122">Surface Hub 最多支援 6 欄 (6 個 1x1 磚)，但即使 Surface Hub 只會將磚顯示在第 0-5 欄 (而非第 6 和 7 欄)，您還是**必須**定義 `GroupCellWidth=8`。</span><span class="sxs-lookup"><span data-stu-id="95e29-122">Surface Hub supports a maximum of 6 columns (6 1x1 tiles), however, you **must** define `GroupCellWidth=8` even though Surface Hub will only display tiles in columns 0-5, not columns 6 and 7.</span></span>
- <span data-ttu-id="95e29-123">Surface Hub 最多支援 6 列 (6 個 1 x 1 磚)</span><span class="sxs-lookup"><span data-stu-id="95e29-123">Surface Hub supports a maximum 6 rows (6 1x1 tiles)</span></span>
- `SecondaryTile`<span data-ttu-id="95e29-124">，這會用於連結，並在 Microsoft Edge 中開啟連結。</span><span class="sxs-lookup"><span data-stu-id="95e29-124">, which is used for links, will open the link in Microsoft Edge.</span></span>


<span id="default" />
## <span data-ttu-id="95e29-125">範例：預設 Surface Hub 開始畫面配置</span><span class="sxs-lookup"><span data-stu-id="95e29-125">Example: Default Surface Hub Start layout</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
            Size="2x2"
            Row="0"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Getstarted_8wekyb3d8bbwe!App"
            Size="4x2"
            Row="0"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
            Size="2x2"
            Row="2"
            Column="0"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
            Size="2x2"
            Row="2"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
            Size="2x2"
            Row="2"
            Column="4"/>
        <start:Tile
            AppUserModelID="c5e2524a-ea46-4f67-841f-6a9465d9d515_cw5n1h2txyewy!App"
            Size="2x2"
            Row="4"
            Column="0"/>
        <start:Tile
            AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
            Size="2x2"
            Row="4"
            Column="2"/>
        <start:Tile
            AppUserModelID="Microsoft.MicrosoftPowerBIForWindows_8wekyb3d8bbwe!Microsoft.MicrosoftPowerBIForWindows"
            Size="2x2"
            Row="4"
            Column="4"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

<span id="edge" />
## <span data-ttu-id="95e29-126">範例：包含 Microsoft Edge 連結的開始畫面配置</span><span class="sxs-lookup"><span data-stu-id="95e29-126">Example: Start layout that includes a Microsoft Edge link</span></span>

<span data-ttu-id="95e29-127">此範例顯示網站的連結和 .pdf 檔案的連結。</span><span class="sxs-lookup"><span data-stu-id="95e29-127">This example shows a link to a website and a link to a .pdf file.</span></span> <span data-ttu-id="95e29-128">Microsoft Edge 的次要磚使用 150 x 150 圖元圖示。</span><span class="sxs-lookup"><span data-stu-id="95e29-128">The secondary tile for Microsoft Edge uses a 150 x 150 pixel icon.</span></span>

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
    <start:Tile
              AppUserModelID="Microsoft.Office.PowerPoint_8wekyb3d8bbwe!Microsoft.pptim"
              Size="2x2"
              Row="0"
              Column="0"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Word_8wekyb3d8bbwe!Microsoft.Word"
              Size="2x2"
              Row="0"
              Column="2"/>
          <start:Tile
              AppUserModelID="Microsoft.Office.Excel_8wekyb3d8bbwe!Microsoft.Excel"
              Size="2x2"
              Row="0"
              Column="4"/>
    <start:Tile
              AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
              Size="2x2"
              Row="2"
              Column="0"/>
    <start:Tile
              AppUserModelID="microsoft.microsoftskydrive_8wekyb3d8bbwe!App"
              Size="2x2" 
             Row="2"
             Column="2"/>   
  <start:SecondaryTile
            AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
           TileID="2678823080"
           DisplayName="Bing"
           Arguments="https://www.bing.com/"
           Square150x150LogoUri="ms-appx:///"
           Wide310x150LogoUri="ms-appx:///"
           ShowNameOnSquare150x150Logo="true"
           ShowNameOnWide310x150Logo="false"
           BackgroundColor="#ffe9e7e7"
           ForegroundText="dark"
           Size="2x2"
           Column="4"
           Row="2"  />
    <start:Tile
              AppUserModelID="Microsoft.Windows.Photos_8wekyb3d8bbwe!App"
              Size="2x2"
              Row="4"
              Column="0"/>
    <start:SecondaryTile
             AppUserModelID="Microsoft.MicrosoftEdge_8wekyb3d8bbwe!MicrosoftEdge"
             TileID="6153963000"
             DisplayName="cstrtqbiology.pdf"
             Arguments="-contentTile -formatVersion 0x00000003 -pinnedTimeLow 0x45b7376e -pinnedTimeHigh 0x01d2356c -securityFlags 0x00000000 -tileType 0x00000000 -url 0x0000003a https://www.ada.gov/regs2010/2010ADAStandards/Guidance_2010ADAStandards.pdf"
             Square150x150LogoUri="ms-appx:///Assets/MicrosoftEdgeSquare150x150.png"
             Wide310x150LogoUri="ms-appx:///" 
             ShowNameOnSquare150x150Logo="true"
             ShowNameOnWide310x150Logo="false"
             BackgroundColor="#ff4e4248"
             Size="4x2" 
             Row="4"
             Column="2"/>
        </start:Group>
      </defaultlayout:StartLayout>
    </StartLayoutCollection>
  </DefaultLayoutOverride>
</LayoutModificationTemplate>
```

>[!NOTE]
><span data-ttu-id="95e29-129">預設值 `ForegroundText` 為 light; 除非您將值變更為深色，否則您不需要包含 `ForegroundText` 在 XML 中。</span><span class="sxs-lookup"><span data-stu-id="95e29-129">The default value for `ForegroundText` is light; you don't need to include `ForegroundText` in your XML unless you're changing the value to dark.</span></span>
