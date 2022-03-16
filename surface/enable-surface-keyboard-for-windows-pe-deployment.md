---
title: 如何在 MDT 部署期間Surface Laptop鍵盤
description: 當您使用 MDT 將 Windows 10 Surface 膝上型電腦部署時，您需要將鍵盤驅動程式輸入到 Windows 環境中使用。
keywords: windows 10 surface， 自動化， 自訂， mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: carlol
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
ms.date: 01/05/2022
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
- Surface Laptop 4
- Surface Laptop Studio
- Surface Pro 8
- Windows 10
- Windows 11
ms.openlocfilehash: 8707d022ae5e3d3f34c59fab88328b5720896898
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449186"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>如何在 MDT 部署期間Surface Laptop鍵盤

本文說明使用 Microsoft Deployment Toolkit (MDT) 。 您也可以將這項資訊用於其他部署方法。 在大部分類型的 Surface 裝置上，鍵盤應在 Lite Touch 安裝期間使用 (LTI) 。 不過，Surface Laptop一些額外的驅動程式才能啟用鍵盤。 針對 Surface Laptop (第 1 代) 和 Surface Laptop 2 個裝置，您必須準備資料夾結構和選取設定檔，讓您指定鍵盤驅動程式，以在 LTI 的 Windows 預先安裝環境 (Windows PE) 階段使用。 有關此資料夾結構的資訊，請參閱使用[MDT 部署Windows 10圖像：步驟 5：準備驅動程式存放庫](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。

> [!TIP]
> 在同一個 Windows PE 啟動實例中使用 Surface Laptop 2 和 Surface Laptop 3 的鍵盤驅動程式時，如果鍵盤或觸控板在 WINDOWS PE 中無法工作，您可能需要手動重設Windows：
>
> - 按住 Power 按鈕 30 秒。 如果您連接到電源裝置 (PSU) ，請按住 Power 按鈕，直到您看到 PSU 電源線結尾的燈短暫關閉，然後再重新開啟。

> [!IMPORTANT]
> 如果您要將 Windows 10 映射部署到預先安裝 S 模式 Windows 10 的 Surface Laptop，請參閱 KB [4032347，將 Windows](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)部署到在 S 模式中預先安裝 Windows 10 的 Surface 裝置時的問題。

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>新增鍵盤驅動程式至選取設定檔

1. 從適當的Surface Laptop .msi下載最新的檔案：
    - [Surface Laptop (驅動程式和) 第一代](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 個驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 與 Intel 處理器驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 與 Intel 處理器驅動程式和固件](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 使用AMD 處理器驅動程式和固件](https://www.microsoft.com/download/102923)
    - [Surface Laptop Studio 驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 個驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=103503)

2. 將檔案內容解壓縮Surface Laptop .msi資料夾，您可以輕鬆地找到 (例如 c：\surface_laptop_drivers) 。 若要解壓縮內容，請開啟提升的 Command Prompt 視窗，然後從下列範例執行命令：

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. 開啟部署工作臺並展開 **部署共用** 節點和部署共用，然後流覽至 **WindowsPEX64** 資料夾。
4. 以滑鼠右鍵按一下 **WindowsPEX64** 資料夾，然後選取 **[導入驅動程式**。
5. 請遵循導入驅動程式精靈中的指示，將驅動程式資料夾導入 WindowsPEX64 資料夾。

 > [!NOTE]
 > 檢查已下載.msi套件，以決定格式和目錄結構。  目錄結構會從 SurfacePlatformInstaller (.msi 檔案) 或 SurfaceUpdate (.msi) 視 .msi 檔案發行時間開始。

## <a name="import-drivers-for-surface-devices"></a>導入 Surface 裝置驅動程式

請根據您的裝置Surface Laptop資料夾。  

| 裝置                                | 匯出資料夾                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | 其他資訊                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Surface Laptop Studio                 | Heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol | 不適用 |
| Surface Pro 8                         | Heci<br>ialpss2_gpio2_tgl<br>ialpss2_i2c_tgl<br>ialpss2_spi_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>msux64w10<br>netwtw08<br>surfacebattery<br>surfacehidminidriver<br>surfaceintegrationdriver<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>tbthostcontroller<br>tbthostcontrollerhacomponent<br> |不適用 |
| Surface Laptop 4 與 Intel 處理器 | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          |不適用                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 4 個使用AMD 處理器   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>APP<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDLylyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>Surface Surface SurfacePanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient |不適用                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| Surface Laptop 3 與 Intel 處理器 | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | 在 PE 中，輸入下列資料夾將啟用完整的鍵盤、軌跡板和觸控功能：<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>晶片組<br>集中LPSS<br>斯達克Northpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| Surface Laptop 2                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | 針對以.msi SurfaceUpdate"開頭的較新檔案，請使用：<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                                    |
| Surface Laptop (第一代)               | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | 針對以.msi SurfaceUpdate"開頭的較新檔案，請使用：<br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                |

  > [!TIP]
  > 檢查已下載.msi套件，以決定格式和目錄結構。  目錄結構會從 SurfacePlatformInstaller (.msi 檔案) 或 SurfaceUpdate (.msi) 視 .msi 發行時間開始。

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>驗證已輸入的驅動程式&設定WINDOWS PE 屬性

1. 請確認 WindowsPEX64 資料夾現在包含已輸入的驅動程式，如下圖所示：

   ![顯示部署工作臺 WindowsPEX64 資料夾中新導入驅動程式的影像。](./images/surface-laptop-keyboard-2.png)
1. 設定使用 WindowsPEX64 資料夾的選取設定檔，如下圖所示：

   ![顯示已選取為選取設定檔一部分的 WindowsPEX64 資料夾的影像。](./images/surface-laptop-keyboard-3.png)
1. 將 MDT Windows的 PE 屬性設定為使用新的選取設定檔，如下所示：
    - 針對 **平臺，** 選取 **x64**。
    - 針對 **選取設定檔**，選取新的設定檔。
    - 選取 **包含選取設定檔的所有驅動程式**。

    ![顯示 MDT 部署Windows的 PE 屬性的影像。](./images/surface-laptop-keyboard-4.png)
4. 使用選取設定檔或**DriverGroup001**變數，Surface Laptop其餘的驅動程式。
    - 如果Surface Laptop (第 1 代) ，**模型會Surface Laptop**。 其餘的 Surface Laptop驅動程式應該位於 \MDT 部署共用\開箱驅動程式\Windows10\X64\Surface Laptop 資料夾中，如下圖所示。
    - 對於 Surface Laptop 2，模型為 Surface Laptop **2**。 其餘的Surface Laptop應該位於 \MDT 部署共用\開箱驅動程式\Windows10\X64\Surface Laptop資料夾中。
    - 對於Surface Laptop 3 處理器的 3，型號為 Surface Laptop 3。 其餘的 Surface Laptop驅動程式位於 \MDT 部署共用\開箱即用驅動程式\Windows10\X64\Surface Laptop 3 資料夾中。

    ![顯示部署工作Surface Laptop (中第一代) 驅動程式Surface Laptop圖像。](./images/surface-laptop-keyboard-5.png)

將 MDT 部署共用設定為使用新的選取設定檔和相關設定之後，請繼續部署程式，如使用[MDT 部署 Windows 10](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)影像中所述：步驟 6：建立部署工作順序。
