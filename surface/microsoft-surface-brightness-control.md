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
# Surface 亮度控制

在銷售點或其他「永不開啟」的展臺案例中部署 Surface 裝置時，您可以使用新的 Surface 亮度控制項 app 來優化電源管理。

可供使用[Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)下載。
表面亮度控制項的設計目的是為了協助減少熱量負載並降低部署表面裝置的整體碳足跡大小。
如果您打算從 [下載] 頁面只取得此工具，請在 [可用] 清單中選取檔案**Surface_Brightness_Control_v1.16.137.0.msi** 。
在不使用時，工具會自動將螢幕調暗，且包含下列設定選項：

- 變暗顯示前的不活動期。

- 當灰色時的亮度等級。

- 使用時的最大亮度等級。

**執行表面亮度控制：**

- 在目標裝置上安裝 surfacebrightnesscontrol.msi，表面亮度控制將會立即開始運作。

## 配置 Surface 亮度控制項

您可以透過 Windows Registry 調整預設值。 如需有關使用 Windows 登錄的詳細資訊，請參閱[註冊檔](https://docs.microsoft.com/windows/desktop/sysinfo/registry)。

1.  從命令提示字元執行 regedit，以開啟 Windows 登錄編輯程式。
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\WOW6432Node\Microsoft\Surface\Surface 亮度控制 \ 
    
    如果您執行的是舊版 Surface 亮度控制，請改為執行下列命令：
    
      - Computer\HKEY\ _LOCAL \ _MACHINE \SOFTWARE\Microsoft\Surface\Surface 亮度控制 \


| 註冊表設定 | 資料| 描述  
|-----------|------------|---------------
| 已啟用亮度控制  |  預設值：01  <br> 選項：01，00 <br> 類型： REG_BINARY |  此設定可讓您開啟或關閉表面亮度控制。 若要停用 Surface 亮度控制，請將值設定為00。 如果您未設定此設定，就會開啟 [Surface 亮度] 控制項。 |
| 已啟用電源上的亮度控制| 預設值：01 <br> 選項：01，00 <br> 類型： REG_BINARY | 此設定可讓您在裝置與電源直接連線時，關閉表面亮度控制。 若要在電源電源開啟時停用表面亮度控制，請將值設定為00。 如果您未設定此設定，就會開啟 [Surface 亮度] 控制項。 |
| 亮度暗淡   | 預設值：20  <br>選項：0-100% 的螢幕亮度範圍 <br> 資料類型：正整數 <br> 類型： REG_DWORD | 此設定可讓您在不活動期間管理亮度範圍。 如果您未設定此設定，亮度等級將會下降為30秒無啟用時間之後的全部亮度的20%。 |
全亮度   | 預設：100  <br>選項：0-100% 的螢幕亮度範圍 <br> 資料類型：正整數 <br> 類型： REG_DWORD  | 此設定可讓您管理裝置的最大亮度範圍。 如果您未設定此設定，最大亮度範圍為100%。|  
| 閒置逾時| 預設值：30秒 <br>選項：任何數位值  <br>資料類型： Integer  <br> 類型： REG_DWORD | 此設定可讓您管理裝置變暗前的非活動期。 如果您未設定此設定，非活動超時為30秒。|
| 已啟用遙測 | 預設值：01 <br>選項：01，00 <br> 類型： REG_BINARY  | 此設定可讓您管理 app 使用方式資訊的共用，以改善軟體並提供更佳的使用者體驗。 若要停用遙測，請將值設定為00。 如果您未設定此設定，則會依照[Microsoft 隱私權聲明](https://privacy.microsoft.com/privacystatement)與 microsoft 共用遙測資訊。 |

## 變更與更新

### 版本1.16.137<br>
*發行日期：2019年10月22日*<br>
這個版本的 Surface 亮度控制項會新增支援：針對 x86 重新編譯，新增 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3的支援。 

### 版本1.12.239。0
*發行日期：2019年4月26日*<br>
此版本的 Surface 亮度控制項可為下列專案新增支援：
- 觸控延遲修正程式。


## 相關主題

- [電池限制設定](battery-limit.md)
