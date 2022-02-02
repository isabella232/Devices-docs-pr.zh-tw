---
title: Surface 亮度控制
description: 本主題說明如何使用 Surface 亮度控制應用程式管理銷售點和資訊站案例的顯示亮度。
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
ms.openlocfilehash: 660a96a8825002c6d52d067dac77894bb0c0b7a9
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12337826"
---
# <a name="surface-brightness-control"></a>Surface 亮度控制

在銷售點或其他「永遠在」資訊站情境中部署 Surface 裝置時，您可以使用 Surface 亮度控制應用程式優化電源管理。 Surface 亮度控制是專為協助降低熱負荷，並降低已部署 Surface 裝置的整體排減量所設計。 工具會在不使用時自動將螢幕變暗，並包含下列組式選項：

- 將顯示器變暗之前，處於非活動狀態期間。
- 變暗時，亮度等級。
- 使用時的最大亮度等級。

從適用于 IT 的 [Surface Tools 下載 Surface 亮度控制](https://www.microsoft.com/download/details.aspx?id=46703)。 選取可用 **Surface_Brightness_Control_v1.16.137.0.msi** 中的檔案。

## <a name="supported-devices"></a>支援的裝置

- Surface Pro 3 及更高版本
- Surface Pro X (代) 
- Surface 3
- Surface Book (代) 
- Surface Laptop工作室
- Surface Studio (代) 
- Surface Laptop (代) 
- Surface Laptop Go
- Surface Go (代) 


## <a name="run-surface-brightness-control"></a>執行 Surface 亮度控制

- 在 **Surface_Brightness_Control_v1.16.137.0.msi** 裝置上安裝亮度控制，Surface 亮度控制將會立即開始工作。

## <a name="configure-surface-brightness-control"></a>設定 Surface 亮度控制

您可以透過註冊表來調整Windows值。 若要進一Windows註冊表，請參閱[註冊表檔](/windows/desktop/sysinfo/registry)。

1. 從**命令提示符執行 regedit**，以開啟 Windows編輯器。
2. 流覽至電腦\HKEY\_LOCAL\_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Surface\Surface 亮度控制。
3. 如下表所述，調整登錄機碼值。

> [!TIP]
> 如果您正使用舊版的 Surface 亮度控制項，請流覽至：電腦\HKEY\_LOCAL\_MACHINE\SOFTWARE\Microsoft\Surface\SurfaceBrightnessControl\

| 註冊表設定 | 資料| 描述  
|-----------|------------|---------------
| BrightnessControlEnabled  |  預設值：01  <br> 選項：01，00 <br> 類型：REG_BINARY |  此設定可讓您開啟或關閉 Surface 亮度控制。 若要停用 Surface 亮度控制，請設定為 00。 如果您沒有設定此設定，Surface 亮度控制即為啟用。 |
| BrightnessControlOnPowerEnabled| 預設值：01 <br> 選項：01，00 <br> 類型：REG_BINARY | 這項設定可讓您在裝置直接連接到電源時關閉 Surface 亮度控制。 若要在電源接通時停用 Surface 亮度控制，請設定值為 00。 如果您沒有設定此設定，Surface 亮度控制即為啟用。 |
| 灰暗的亮度   | 預設值：20  <br>選項：0-100% 的螢幕亮度範圍 <br> 資料類型：正整數 <br> 類型：REG_DWORD | 此設定可讓您在閒置期間管理亮度範圍。 如果您沒有設定此設定，在閒置 30 秒之後，亮度等級會降為完整亮度的 20%。 |
FullBrightness   | 預設值：100  <br>選項：0-100% 的螢幕亮度範圍 <br> 資料類型：正整數 <br> 類型：REG_DWORD  | 此設定可讓您管理裝置的最大亮度範圍。 如果您沒有設定此設定，最大亮度範圍為 100%。|  
| 非活動Timeout| 預設值：30 秒 <br>選項：任何數值  <br>資料類型：整數  <br> 類型：REG_DWORD | 此設定可讓您在將裝置變暗之前，管理非活動期間。 如果您沒有設定此設定，則非活動超時為 30 秒。|
| 遙測Enabled | 預設值：01 <br>選項：01，00 <br> 類型：REG_BINARY  | 此設定可讓您管理應用程式使用方式資訊的共用，以改善軟體，並提供更佳的使用者體驗。 若要停用遙測，請設定為 00。 如果您沒有設定此設定，遙測資訊會根據 Microsoft 隱私權聲明與 [Microsoft 共用](https://privacy.microsoft.com/privacystatement)。 |

## <a name="changes-and-updates"></a>變更與更新

### <a name="version-116137br"></a>版本 1.16.137<br>

*發行日期：2019 年 10 月 22 日*<br>
此版本的 Surface 亮度控制新增下列支援：-重新編譯 x86，新增 Surface Pro 7、Surface Pro X 和 Surface Laptop 3 的支援。

### <a name="version-1122390"></a>版本 1.12.239.0

*發行日期：2019 年 4 月 26 日*<br>
此版本的 Surface 亮度控制新增下列支援：

- 觸控延遲修正。

## <a name="related-topics"></a>相關主題

- [電池限制設定](battery-limit.md)
