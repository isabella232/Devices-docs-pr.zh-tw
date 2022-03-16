---
title: Surface Laptop SE 概觀
description: 本文提供教育Surface Laptop SE概觀。
ms.prod: w11
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 01/11/2022
ms.reviewer: hachidan
manager: laurawi
audience: itpro
appliesto:
- Windows 11
ms.openlocfilehash: a99c3241eea0099b90de9c64ff840306aa98e58d
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448317"
---
# <a name="surface-laptop-se-overview"></a>Surface Laptop SE 概觀

Surface Laptop SE提供受管理的裝置體驗，以經濟實惠的成本簡化學生的學習。 它Windows 11 SE雲端式作業系統，並預載入廣泛使用的應用程式，例如[](#pre-installed-apps) Microsoft Teams、Word、PowerPoint、Excel、OneNote、Edge、Minecraft: Education Edition、Flipgrid，以及更多。 

:::image type="content" source="images/surface-laptop-se.png" alt-text="Surface Laptop SE顯示Windows 11 SE [開始] 功能表":::<br>
*圖 1。 Surface Laptop SE顯示Windows 11 SE [開始] 功能表*

Surface Laptop SE支援學生和教育工作者所需的大部分應用程式，包括漸進式 Web App (PWAs) 、通用 Windows 平臺應用程式 (UWP) ，以及一組由[Win32 & Microsoft Store](#install-optional-apps)應用程式。 與其他 Surface 裝置不同，Surface Laptop SE防止使用者安裝自己的 App。 相反地，IT 系統管理員或技術Surface Laptop SE使用 Microsoft 端點管理員 管理裝置，包括 Microsoft Intune、Microsoft Intune 教育用和新的[Surface 管理入口網站](surface-management-portal.md)。[ ](/mem/intune/fundamentals/what-is-intune) [ ](https://www.microsoft.com/education/intune) 

> [!NOTE]
> 本文適用于部署及管理學校使用者的裝置之 IT 系統管理員和教育人員。 若要瞭解一般資訊或訂購，請參閱[Surface Laptop SE超薄型膝上型電腦](https://www.microsoft.com/surface/business/surface-laptop-se)。

## <a name="simplified-deployment-management--security"></a>簡化部署、管理&安全性

- 使用 Autopilot、快速套用原則Windows安裝應用程式，完成新裝置低觸式部署。 Windows Autopilot 提供開箱即用、低觸控式部署和影像，並預先安裝及預配置許多應用程式與政策。 IT 可以輕鬆地調整裝置設定 ，包括固件設定，並安裝學生所需的應用程式，以便學生第一次在裝置上電源時一切就緒。
- 部署裝置後，Microsoft Intune整個學年度提供簡化的遠端系統管理，讓 IT 能夠管理應用程式、控制安全性與隱私權，以及產生合規性報告。
- 當膝上型電腦關閉時，使用蓋鎖定鎖定作業系統，以及使用整合的 Kensington Nano Security Slot 控制實體存取™。
- 新設計的無外接式轉軸、塑膠底板，以及外接到表圈的螢幕周圍塑膠邊框，可提供額外的耐久度，以更符合學生使用的需求和需求。
- Intune 和 DFCI 支援安全裝置更新及管理至固件層。 IT 系統管理員可以控制硬體元素，例如麥克風、USB 埠、相機和藍牙，並移除對周邊設備的電源。 獨一無二的可掃描 Surface 封裝可讓您輕鬆識別裝置，當需要重新註冊時，裝置識別碼號碼會保持不變。

### <a name="surface-management-portal"></a>Surface 管理入口網站

當您註冊雲端管理Surface Laptop SE使用者第一次登入時，這些 Surface 裝置的資訊會自動進入[Surface 管理入口](surface-management-portal.md)網站，為您提供適用于 Surface 特定裝置系統管理員活動的單一窗格。 您可以深入瞭解裝置合規性、支援活動和保固範圍。 快速查看每個裝置的狀態、哪些裝置仍在保固或即將到期，以及使用中支援要求的狀態。

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="Surface Management Portal 顯示保固保固保Surface Laptop SE":::
*圖 2. Surface Management Portal 顯示保固保固保Surface Laptop SE*

## <a name="common-admin-scenarios"></a>常見的系統管理案例

| 案例                                                            | 描述                                                                                                                                                                                                                                                                                                                          | 深入了解                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 使用自動Surface Laptop SE遠端設定Windows裝置 | Windows Autopilot 提供開箱即用、低觸控式部署和影像，並預先安裝及預配置許多應用程式與政策。 IT 可以輕鬆地調整裝置設定 ，包括固件設定，並安裝學生所需的應用程式，以便學生第一次在裝置上電源時一切就緒。                 |[使用 Autopilot 設定教育用 Intune Windows裝置](/intune-education/windows-autopilot-setup)<br><br>[我要如何註冊我的裝置？](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| 透過 Intune 教育用部署更新                             | IT 系統管理員可以使用 Microsoft Intune，在一年四Surface Laptop SE將作業系統與應用程式更新推送到整個學校的裝置。 如有需要，他們可以停用硬體元素，例如相機或藍牙裝置上的裝置，或在學生遇到技術問題時重設特定裝置。 |[管理正在Windows 11 SE](/intune-education/windows-11-se-overview)<br><br>[Microsoft 教育版文件與資源](/microsoft-365/education/)<br><br>[開始使用 Intune 教育用](/microsoft-365/education/deploy/intune-for-education)<br><br>[使用 Intune 教育版管理群組、應用程式及設定](/microsoft-365/education/deploy/use-intune-for-education) |
| 根據需要取代裝置                                           | 如果學生畫面損毀或裝置損毀，IT 系統管理員可以快速部署備用裝置，將學生的雲端身分標識轉移到新裝置。                                                                                                  |[Intune 教育用中的遠端裝置動作](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| 透過 Intune 部署新應用程式                                          | 如果教師要求新的 App，IT 系統管理員可以使用 Intune 在所有學生裝置上遠端安裝。                                                                                                                                                                                                                            |[為所有使用者安裝應用程式](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| 透過 Intune 重設裝置                                            | 當學生於Surface Laptop SE結束時開啟他們的 Surface Laptop SE 裝置時，IT 系統管理員可以使用 Intune 來重設下一個班級的裝置，這些裝置將在下一個學年度開始時需要這些裝置。                                                                                                           |[使用 Autopilot Reset 使用 Intune 教育用重新設定裝置](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>預先安裝的應用程式

Surface LaptopSE隨附下列預先安裝的應用程式：  

- Microsoft Excel
- Flipgrid
- Groove音樂
- 地圖
- Microsoft Edge
- Microsoft 新聞
- Microsoft Teams
- Microsoft To Do
- Microsoft Whiteboard
- Minecraft教育版
- 記事本
- Microsoft Office
- OneDrive
- OneNote
- Outlook 網頁版
- 小畫家
- 相片
- PowerPoint
- 吸食工具
- 自黏便箋
- Surface 應用程式
- Surface Diagnostic Toolkit
- 提示
- 語音錄音機
- 天氣
- 猜字

## <a name="install-optional-apps"></a>安裝選擇性應用程式

IT 系統管理員可以透過 Intune [安裝其他應用程式](/education/windows/windows-11-se-overview#available-apps) ，例如 Chrome 或縮放。 請注意，系統沒有適用于 Surface Laptop SE 的應用程式Surface Laptop SE。 請參閱下列指示以完成應用程式部署： 

- [應用程式部署](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>可修復性

Surface Laptop SE Surface Laptop SE是專為技術精湛的技術人員所設計，可快速取代核心元件，以在當地維修裝置：

- 顯示模組  
- 鍵盤&桶
- 演講者& Wi-Fi模組
- 電池
- 腳

學校可以使用授權服務提供者或他們自己的技術人員，按照 Microsoft 提供的「Surface Laptop SE指南」，在現場修復裝置，並可從[Surface 服務](https://www.microsoft.com/download/100440)指南中提供。

若要深入瞭解，請參閱：

- [Surface Laptop SE修復影片](https://youtu.be/fVjjSqfp75g)
- [Surface 裝置的最佳支援解決方案](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop SE技術規格

| 功能                     | 描述                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **尺寸**              | - 11.17" x 7.6" x 0.70" (283.70 mm x 193.05 mm x 17.85 mm)                                                                                                                                                 |
| ** ** <sup> 儲存體1</sup>     | - 在 64 GB 或 128 GB (內嵌多媒體卡) 內嵌多媒體卡                                                                                                                                                 |
| **顯示**                 | - 螢幕：11.6" TFT 液體水晶顯示模組<br>- 顯示解析度：1366 x 768 (135 PPI) <br>- 長寬比：16：9<br>- 對比比：800：1 (一般) <br>- 亮度：220 nits<br>- 無蓋玻璃 |
| **電池**                 | - 35Wh (標) ，33.9Wh (分鐘) <br>- 16 小時的電池使用時間 <sup> 2</sup>                                                                                                                                              |
| **記憶體**                  | - 4 GB 或 8 GB 的DDR4 (2400 MHz 分鐘)                                                                                                                                                                           |
| **CPU / 圖形**          | - Intel® Celeron® 處理器 N4020 / Intel® UHD 圖形 600<br>- Intel® Celeron® 處理器 N4120 / Intel® UHD 圖形 600                                                                                |
| **連線**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x 筒式 DC 連接器<br>- 1 x 3.5 mm Headphone/麥克風插孔                                                                                                           |
| **安全性**                | - 商業用軟體的所有 (TPM) <br>- Nano Security Lock 插槽                                                                                                                        |
| **相機、視&音訊** | - 1MP 前置相機，最多 720p 30fps 影片<br>- 2W 立體喇叭<br>- 單數位麥克風                                                                                              |
| **軟體**                | - Windows 11 SE<br>- Microsoft 365教育 <sup> 版 3</sup>                                                                                                                                                         |
| **無線**                | - Wi-Fi：802.11ac (2x2) <br>- 藍牙無線 5.0 LE                                                                                                                                                    |
| **感應器**                 | - 1 x Hall-effect 感應器                                                                                                                                                                                  |
| **外部**                | - 大小寫：所有未配對的塑膠內體<br>- 色彩：冰河<br>- 實體按鈕：鍵盤上的電源和音量<br>- 轉軸：135 度開啟角度                                                          |
| **粗細**                  | - 2.45 磅 (1，111.3 克)                                                                                                                                                                                     |
| **鍵盤和軌跡板**   | - 不含Windows 11.6" 的標準鍵盤<br>- 標準無浮動精准軌跡板                                                                                                      |
| **熱處理**                | - 被動式冷淡                                                                                                                                                                                        |
| **電源**            | - 內箱式 45W，具有 DC 筒式充電器                                                                                                                                                                      |
| **包裝盒內容**              | - Surface 裝置<br>- 電源<br>- 快速入門手冊<br>- 安全與保固檔                                                                                                              |
| **保修** <sup>4</sup>    | - 一年有限硬體保固                                                                                                                                                                      |

## <a name="references"></a>參考

1. 系統軟體和更新會佔用大量的儲存空間。 可用的儲存空間可能會根據系統軟體、更新和應用程式使用量而變更。 1 GB = 10 億位元組。 1 TB = 1，000 GB。 請參閱[Surface 儲存體](https://support.microsoft.com/help/4023513/surface-surface-storage?)以進一步查看詳細資料。
2. 電池使用時間會因使用量、網路和功能設定、訊號強度、設定及其他因素而大幅改變。 請參閱 [Surface 電池測試和預估的電池使用](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) 效果，以瞭解詳細資料。
3. 需要符合資格Microsoft 365或Office 365授權;需另行購買。 [比較Microsoft 365方案](https://aka.ms/EDU-Plan-Comparison)。
4. Microsoft 的有限擔保是消費者法律權利之外。


## <a name="learn-more"></a>深入了解

- [訂購Surface Laptop SE](https://www.microsoft.com/surface/business/surface-laptop-se)
- [教育Surface Laptop SE介紹](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows 11 SE 教育版](/education/windows/windows-11-se-overview)
- [管理正在Windows 11 SE](/intune-education/windows-11-se-overview)
- [使用 Autopilot 設定教育用 Intune Windows裝置](/intune-education/windows-autopilot-setup)
- [Microsoft 教育版文件與資源](/microsoft-365/education/)
- [Outlook 網頁版](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
