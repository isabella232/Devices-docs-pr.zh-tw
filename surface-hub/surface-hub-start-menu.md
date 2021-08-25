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
ms.openlocfilehash: ff08b8ab6e59af77761fb365980af261c47030a9
ms.sourcegitcommit: 09a47921ec2e565a92ba2baa61e181d218706ad9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/24/2021
ms.locfileid: "11921822"
---
# <a name="configure-surface-hub-start-menu"></a>設定 Surface Hub 的 [開始] 功能表

[Windows 10 的 2018 年 1 月 17 日更新](https://support.microsoft.com/help/4057144) (組建 15063.877) 可在 Surface Hub 裝置上啟用自訂的 [開始] 功能表。 您可以使用行動裝置管理 (MDM) 來套用自訂的 [開始] 功能表配置。

當您將自訂的 [開始] 功能表配置套用至 Surface Hub 時，使用者無法從開始畫面釘選、取消釘選，或解除安裝應用程式。 

## <a name="how-to-apply-a-customized-start-menu-to-surface-hub"></a>如何將自訂的 [開始] 功能表套用至 Surface Hub

自訂的 [開始] 功能表是在開始畫面配置 XML 檔案中定義。 您有兩個建立開始畫面配置 XML 檔案的選項：

- 編輯[預設 Surface Hub 開始畫面 XML](#default)

    - 或 -

- 在電腦上設定想要的 [開始] 功能表 (僅釘選 Surface Hub 上提供的應用程式)，然後[匯出配置](/windows/configuration/customize-and-export-start-layout#export-the-start-layout)。

>[!TIP]
>若要新增有 Web 連結的磚到電腦的 [開始] 功能表，請移至 Microsoft Edge 中的連結、選取右上角的 `...`，然後選取 **\[將此頁面釘選到開始畫面\]**。 如需連結如何顯示在 XML 中的範例，請參閱[包含 Microsoft Edge 連結的 \[開始\] 配置](#edge)。

若要編輯預設 XML 或匯出的配置，請熟悉一下[開始畫面配置 XML](/windows/configuration/start-layout-xml-desktop)。 有幾個[電腦與 Surface Hub 之間的開始畫面配置差異](#differences)

您在開始畫面配置 XML 中定義 [開始] 功能表之後，[建立 MDM 原則以套用配置。](/windows/configuration/customize-windows-10-start-screens-by-using-mobile-device-management#a-href-idbkmk-domaingpodeploymentacreate-a-policy-for-your-customized-start-layout)

<span id="differences" />

## <a name="differences-between-surface-hub-and-desktop-start-menu"></a>Surface Hub 與電腦 [開始] 功能表之間的差異

Surface Hub 與 Windows 10 電腦的 [開始] 功能表自訂之間有一些主要差異：

- 您無法在開始版面配置 XML 中使用**[DesktopApplication，](/windows/configuration/start-layout-xml-desktop#startdesktopapplicationtile)** 因為 Windows不支援 (Win32) 桌面應用程式Surface Hub。
- 您無法使用開始畫面配置 XML 來設定 Surface Hub 的工作列或歡迎畫面。  
- 開始版面配置策略應該只指派給裝置，而不是使用者。
- 在策略中使用的 OMA-URI 設定為 `./Device/Vendor/MSFT/Policy/Config/Start/StartLayout`
- Surface Hub 最多支援 6 欄 (6 個 1x1 磚)，但即使 Surface Hub 只會將磚顯示在第 0-5 欄 (而非第 6 和 7 欄)，您還是**必須**定義 `GroupCellWidth=8`。
- Surface Hub 最多支援 6 列 (6 個 1 x 1 磚)
- `SecondaryTile`，這會用於連結，並在 Microsoft Edge 中開啟連結。


<span id="default" />

## <a name="example-default-surface-hub-start-layout"></a>範例：預設 Surface Hub 開始畫面配置

```xml
<LayoutModificationTemplate Version="1" xmlns="http://schemas.microsoft.com/Start/2014/LayoutModification">
  <LayoutOptions StartTileGroupCellWidth="8" />
  <DefaultLayoutOverride>
    <StartLayoutCollection>
      <defaultlayout:StartLayout GroupCellWidth="8" xmlns:defaultlayout="http://schemas.microsoft.com/Start/2014/FullDefaultLayout">
        <start:Group Name="" xmlns:start="http://schemas.microsoft.com/Start/2014/StartLayout">
        <start:DesktopApplicationTile
            DesktopApplicationID="MSEdge"
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

## <a name="example-start-layout-that-includes-a-microsoft-edge-link"></a>範例：包含 Microsoft Edge 連結的開始畫面配置

此範例顯示網站的連結和 .pdf 檔案的連結。 次要磚Microsoft Edge 150 x 150 圖元圖示。

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
          <start:DesktopApplicationTile
              DesktopApplicationID="MSEdge"
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
>預設值為淺;除非您將值變更為深色，否則不需要在 XML 中 `ForegroundText` `ForegroundText` 納入。
