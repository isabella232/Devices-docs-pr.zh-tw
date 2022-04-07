---
title: Surface Laptop SE 概觀
description: 本文提供教育用Surface Laptop SE概觀。
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
ms.openlocfilehash: 2d16d63dda53bbfffbf5d7d9cb080c4e595217a5
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472582"
---
# <a name="surface-laptop-se-overview"></a>Surface Laptop SE 概觀

Surface Laptop SE提供受控裝置體驗，可簡化學生以經濟實惠的成本學習。 它會執行Windows 11 SE雲端優先作業系統，並[預載入廣泛使用的應用程式](#pre-installed-apps)，例如 Microsoft Teams、Word、PowerPoint、Excel、OneNote、Edge、Minecraft: Education Edition、Flipgrid、 和更多。 

:::image type="content" source="images/surface-laptop-se.png" alt-text="顯示Windows 11 SE [開始] 功能表的Surface Laptop SE":::<br>
*圖 1。 顯示Windows 11 SE [開始] 功能表的Surface Laptop SE*

Surface Laptop SE支援學生和授課者所需的大部分應用程式，包括漸進式Web Apps (PWA) 、通用 Windows 平臺應用程式 (UWP) ，以及一[組策劃的 Win32 & Microsoft Store 應用程式](#install-optional-apps)。 不同于其他 Surface 裝置，Surface Laptop SE防止使用者安裝自己的應用程式。 相反地，IT 系統管理員或技術主管會使用 Microsoft 端點管理員 來管理Surface Laptop SE裝置，其中包括[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)、[Microsoft Intune教育](https://www.microsoft.com/education/intune)版，以及新的[Surface Management 入口網站](surface-management-portal.md)。 

> [!NOTE]
> 本文適用于為學校使用者部署和管理裝置的 IT 系統管理員和教育人員。 如需一般資訊或排序，[請參閱 Surface Laptop SE 適用于學生的 Laptop](https://www.microsoft.com/surface/business/surface-laptop-se)。

## <a name="simplified-deployment-management--security"></a>簡化部署、管理&安全性

- 使用 Windows Autopilot 完成新裝置的低觸控部署、快速套用原則及安裝應用程式。 Windows Autopilot 提供現成可用的低觸控部署和映射處理，其中已預先安裝和預先設定許多應用程式和原則。 IT 可以輕鬆地調整裝置設定，包括韌體設定，並安裝學生需要的應用程式，讓一切準備好在裝置上第一次開機時就緒。
- 部署裝置之後，Microsoft Intune在整個學年提供簡化的遠端系統管理，讓 IT 能夠管理應用程式、控制安全性和隱私權，以及產生合規性報告。
- 當膝上型電腦關閉時，請使用 lid-lock 鎖定作業系統，並使用整合式的 Nano Nano 安全性位置™來控制實體存取。
- 新設計的非公開轉軸、材質底座，以及周遭移出邊框的螢幕周圍，提供額外的持久性，以更符合學生使用的需求和需求。
- Intune和 DFCI 支援韌體層的安全裝置更新和管理。 IT 系統管理員可以控制硬體元素，例如麥克風、USB 埠、相機和藍牙，以及移除週邊設備的電源。 唯一的可掃描 Surface 封裝可讓您輕鬆識別裝置，而裝置識別碼會在重新註冊時維持不變。

### <a name="surface-management-portal"></a>Surface 管理入口網站

當您為雲端管理註冊Surface Laptop SE，且使用者第一次登入時，來自這些 Surface 裝置的資訊會自動流入[Surface 管理入口網站](surface-management-portal.md)，為您提供一個適用于 Surface 特定裝置系統管理活動的單一窗格。 您可以深入瞭解裝置合規性、支援活動和保固涵蓋範圍。 快速查看每個裝置的狀態、哪些裝置仍在保固或即將到期，以及作用中支援要求的狀態。

:::image type="content" source="images/surface-management-portal-laptop-se.png" alt-text="顯示Surface Laptop SE保固涵蓋範圍的 Surface 管理入口網站":::
*圖 2. 顯示Surface Laptop SE保固涵蓋範圍的 Surface 管理入口網站*

## <a name="common-admin-scenarios"></a>常見的系統管理員案例

| 案例                                                            | 描述                                                                                                                                                                                                                                                                                                                          | 深入了解                                                                                                                                                                                                                                                                                                                                                                                                       |
| ------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 使用 Windows Autopilot 遠端設定Surface Laptop SE裝置 | Windows Autopilot 提供現成可用的低觸控部署和映射處理，並預先安裝和預先設定許多應用程式和原則。 IT 可以輕鬆地調整裝置設定，包括韌體設定，並安裝學生需要的應用程式，讓一切準備好在裝置上第一次開機時就緒。                 |[使用 Windows Autopilot 設定教育用Intune裝置](/intune-education/windows-autopilot-setup)<br><br>[如何註冊我的裝置？](/intune-education/how-should-i-enroll-devices)                                                                                                                                                  |
| 透過教育用Intune部署更新                             | IT 系統管理員可以使用Microsoft Intune來推送作業系統和應用程式更新，以在整個學校Surface Laptop SE裝置。 如有必要，他們可以停用相機或個別裝置上的藍牙等硬體元素，或在學生遇到技術問題時重設特定裝置。 |[管理執行Windows 11 SE的裝置](/intune-education/windows-11-se-overview)<br><br>[Microsoft 教育版文件與資源](/microsoft-365/education/)<br><br>[開始教育用Intune](/microsoft-365/education/deploy/intune-for-education)<br><br>[使用 Intune 教育版管理群組、應用程式及設定](/microsoft-365/education/deploy/use-intune-for-education) |
| 視需要取代裝置                                           | 如果學生破解螢幕或損壞裝置，IT 系統管理員可以快速部署備用裝置，將學生的雲端身分識別傳輸至新裝置。                                                                                                  |[Intune教育版中的遠端裝置動作](/intune-education/edu-device-remote-actions)                                                                                                                                                                                                                                                                                   |
| 透過 Intune 部署新的應用程式                                          | 如果教師要求新的應用程式，IT 系統管理員可以使用 Intune 從遠端將它安裝在所有學生裝置上。                                                                                                                                                                                                                            |[為所有使用者安裝應用程式](/microsoft-365/education/deploy/use-intune-for-education#install-apps-for-all-users)                                                                                                                                                                                                                                                              |
| 透過 Intune 重設裝置                                            | 當學生在學年結束時開啟其Surface Laptop SE裝置時，IT 系統管理員可以使用Intune重設下一個班級的裝置，在下一個學年的開頭需要這些裝置。                                                                                                           |[使用 Autopilot 重設以Intune教育版重新設定裝置](/intune-education/autopilot-reset)                                                                                                                                                                                                                                                                      |

## <a name="pre-installed-apps"></a>預先安裝的應用程式

Surface LaptopSE隨附下列預先安裝的應用程式：  

- Microsoft Excel
- Flipgrid
- Groove 音樂
- 地圖
- Microsoft Edge
- Microsoft 新聞
- Microsoft Teams
- Microsoft To Do
- Microsoft Whiteboard
- Minecraft Education Edition
- 記事本
- Microsoft Office
- OneDrive
- OneNote
- Outlook 網頁版
- 小畫家
- 相片
- PowerPoint
- 剪下工具
- 自黏便
- Surface 應用程式
- Surface Diagnostic Toolkit
- 提示
- 語音錄音機
- 天氣
- 猜字

## <a name="install-optional-apps"></a>安裝選擇性應用程式

IT 系統管理員可以透過 Intune 安裝[其他應用程式](/education/windows/windows-11-se-overview#available-apps)，例如 Chrome 或 Zoom。 請注意，沒有適用于Surface Laptop SE的應用程式市集。 請參閱下列指示以完成應用程式部署： 

- [應用程式部署](/intune-education/windows-11-se-overview#app-deployment)


## <a name="repairability"></a>可修復性

Surface Laptop SE Surface Laptop SE旨在讓技術熟練的技術人員能夠快速取代核心元件，在本機服務裝置：

- 顯示模組  
- 鍵盤&貯體
- 演講者& Wi-Fi模組
- 電池
- 腳

學校可以依照 Microsoft 提供的「Surface Laptop SE 服務指南」，使用授權服務提供者或其專屬技術熟練的技術人員，在現場修復裝置。[《Surface Service 指南》](https://www.microsoft.com/download/100440)提供。

若要深入瞭解，請參閱：

- [Surface Laptop SE修復影片](https://youtu.be/fVjjSqfp75g)
- [Surface 裝置的最佳支援解決方案](support-solutions-surface.md)

## <a name="surface-laptop-se-tech-specs"></a>Surface Laptop SE技術規格

| 功能                     | 描述                                                                                                                                                                                               |
| --------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **尺寸**              | - 11.17" x 7.6" x 0.70" (283.70 mm x 193.05 mm x 17.85 mm)                                                                                                                                                 |
| ** ** <sup> 儲存體1</sup>     | - 上線時，內嵌多媒體卡片 (eMMC) 64GB 或 128GB                                                                                                                                                 |
| **顯示**                 | - 畫面：11.6 吋 TFT Liquid Liquid Display Module<br>- 顯示解析度：1366 x 768 (135 PPI) <br>- 外觀比例：16：9<br>- 對比比率：800：1 (一般) <br>- 亮度：220 nits<br>- 無蓋玻璃 |
| **電池**                 | - 35 Wh () ，33.9Wh (分鐘) <br>- 16 小時的電池使用時間 <sup> 2</sup>                                                                                                                                              |
| **記憶體**                  | - 4GB 或 8GB DDR4 (2400 MHz min)                                                                                                                                                                           |
| **CPU / 圖形**          | - Intel® Celeron® 處理器 N4020 / Intel® UHD 圖形 600<br>- Intel® Celeron® 處理器 N4120 / Intel® UHD 圖形 600                                                                                |
| **連線**             | - 1 x USB-A<br>- 1 x USB-C<br>- 1 x 桶類型 DC 連接器<br>- 1 x 3.5 公釐耳機/Mic Jack                                                                                                           |
| **安全性**                | - 所有設定的韌體 TPM (商業) <br>- Nano 安全性鎖定位置                                                                                                                        |
| **相機、視訊、&音訊** | - 最多 720p 30fps 視訊的 1MP 前端相機<br>- 2W 身歷聲喇叭<br>- 單一數位麥克風                                                                                              |
| **軟體**                | - Windows 11 SE<br>- Microsoft 365教育版 <sup> 3</sup>                                                                                                                                                         |
| **無線**                | - Wi-Fi：802.11ac (2x2) <br>- 藍牙 Wireless 5.0 LE                                                                                                                                                    |
| **感應器**                 | - 1 x Hall 效果感應器                                                                                                                                                                                  |
| **外部**                | - 大小寫：所有未繪製的材質<br>- 色彩：嶺色<br>- 實體按鈕：鍵盤上的電源和磁片區<br>- 轉軸：135 度開啟角度                                                          |
| **粗細**                  | - 2.45 lb. (1，111.3 g)                                                                                                                                                                                     |
| **鍵盤和追蹤板**   | - 標準Windows鍵盤 11.6 吋沒有背光<br>- 標準無浮精確度追蹤板                                                                                                      |
| **熱**                | - 被動冷卻                                                                                                                                                                                        |
| **電源**            | - 內建、45W 與 DC 桶充電器                                                                                                                                                                      |
| **包裝盒內容**              | - Surface 裝置<br>- 電源供應器<br>- 快速入門手冊<br>- 安全性和保固檔                                                                                                              |
| **保修** <sup>4</sup>    | - 一年有限的硬體保固                                                                                                                                                                      |

## <a name="references"></a>參考

1. 系統軟體和更新會使用大量的儲存空間。 可用的儲存體可能會根據系統軟體、更新和應用程式使用量而有所變更。 1 GB = 10 億個位元組。 1 TB = 1，000 GB。 如需詳細資訊，請參閱[Surface 儲存體](https://support.microsoft.com/help/4023513/surface-surface-storage?)。
2. 電池使用時間會根據使用量、網路和功能設定、訊號強度、設定和其他因素而大幅不同。 如需詳細資訊，請參閱 [Surface 電池測試和預估效能](https://support.microsoft.com/surface/surface-battery-testing-and-estimated-performance-f038487c-a6c8-407d-b0b0-5737ac5e8397) 。
3. 需要符合資格的Microsoft 365或Office 365授權;個別銷售。 [比較Microsoft 365教育計畫](https://aka.ms/EDU-Plan-Comparison)。
4. Microsoft 的有限擔保除了您的消費者法律權利之外。


## <a name="learn-more"></a>深入了解

- [排序Surface Laptop SE](https://www.microsoft.com/surface/business/surface-laptop-se)
- [教育Surface Laptop SE簡介](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/introducing-surface-laptop-se-for-education/ba-p/1721767)
- [Windows 11 SE 教育版](/education/windows/windows-11-se-overview)
- [管理執行Windows 11 SE的裝置](/intune-education/windows-11-se-overview)
- [使用 Windows Autopilot 設定教育用Intune裝置](/intune-education/windows-autopilot-setup)
- [Microsoft 教育版文件與資源](/microsoft-365/education/)
- [Outlook 網頁版](https://www.microsoft.com/microsoft-365/outlook/web-email-login-for-outlook?)
- [教育用的專用硬體&軟體解決方案](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/a-purpose-built-hardware-amp-software-solution-for-education/ba-p/1419013)