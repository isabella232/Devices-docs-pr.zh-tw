---
title: 如何在 MDT 部署期間啟用Surface Laptop鍵盤
description: 當您使用 MDT 將Windows 10部署到 Surface 膝上型電腦時，您需要匯入鍵盤驅動程式以在 Windows PE 環境中使用。
keywords: windows 10 surface， automate， customize， mdt， 自動化， 自訂， mdt
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
ms.openlocfilehash: d207d0843e23f68713597c12a529ab5574fa695e
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497916"
---
# <a name="how-to-enable-the-surface-laptop-keyboard-during-mdt-deployment"></a>如何在 MDT 部署期間啟用Surface Laptop鍵盤

本文說明使用 Microsoft Deployment Toolkit (MDT) 的部署方法。 您也可以將此資訊套用至其他部署方法。 在大部分類型的 Surface 裝置上，鍵盤應該會在 Lite Touch 安裝 (LTI) 期間運作。 不過，Surface Laptop需要一些額外的驅動程式才能啟用鍵盤。 針對 Surface Laptop (第 1 代) 和Surface Laptop 2 裝置，您必須準備資料夾結構和選取設定檔，讓您指定要在 LTI 的 PE) 階段Windows預先安裝環境 (Windows期間使用的鍵盤驅動程式。 如需此資料夾結構的詳細資訊，請[參閱使用 MDT 部署Windows 10映射：步驟 5：準備驅動程式存放庫](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。

> [!TIP]
> 在相同的 Windows PE 開機實例中使用Surface Laptop 2 和 Surface Laptop 3 的鍵盤驅動程式時，如果鍵盤或觸控板無法在 Windows PE 中運作，您可能需要手動重設韌體：
>
> - 按住電源按鈕 30 秒。 如果您連線到 PSU)  (電源供應器單位，請按住 [電源] 按鈕，直到您看到 PSU 線條結尾的光線短暫關閉，然後再重新開啟。

> [!IMPORTANT]
> 如果您要將Windows 10映射部署至已預先安裝 S 模式Windows 10的Surface Laptop，請參閱 KB [4032347、在 S 模式中預先安裝Windows 10將Windows部署至 Surface 裝置時發生問題](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)。

## <a name="add-keyboard-drivers-to-the-selection-profile"></a>將鍵盤驅動程式新增至選取設定檔

1. 從適當的位置下載最新的Surface Laptop .msi檔：
    - [Surface Laptop (第 1 代) 驅動程式和韌體](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface Laptop 2 驅動程式和韌體](https://www.microsoft.com/download/details.aspx?id=57515)
    - [Surface Laptop 3 搭配 Intel 處理器驅動程式和韌體](https://www.microsoft.com/download/details.aspx?id=100429)
    - [Surface Laptop 4 搭配 Intel 處理器驅動程式和韌體](https://www.microsoft.com/download/102924)
    - [Surface Laptop 4 與 AMD 處理器驅動程式和韌體](https://www.microsoft.com/download/102923)
    - [Surface Laptop Studio 驅動程式和韌體](https://www.microsoft.com/download/details.aspx?id=103505)
    - [Surface Pro 8 驅動程式和韌體](https://www.microsoft.com/download/details.aspx?id=103503)

2. 將Surface Laptop .msi檔案的內容解壓縮到您可以輕鬆找到 (的資料夾，例如 c：\surface_laptop_drivers) 。 若要擷取內容，請開啟提升許可權的命令提示字元視窗，然後從下列範例執行命令：

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. 開啟 [部署工作臺]，然後展開 [ **部署共用** ] 節點和您的部署共用，然後流覽至 **[WindowsPEX64** ] 資料夾。
4. 以滑鼠右鍵按一下 **WindowsPEX64** 資料夾，然後選取 [ **匯入驅動程式]**。
5. 請遵循匯入驅動程式精靈中的指示，將驅動程式資料夾匯入 WindowsPEX64 資料夾。

 > [!NOTE]
 > 檢查下載的.msi套件，以判斷格式和目錄結構。  目錄結構的開頭是 SurfacePlatformInstaller (舊.msi檔案) 或 SurfaceUpdate (較新的.msi檔案) 視.msi檔案的發行時間而定。

## <a name="import-drivers-for-surface-devices"></a>匯入 Surface 裝置的驅動程式

根據您的Surface Laptop裝置，匯入下列資料夾。

| 裝置                                    | 匯入資料夾                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | 其他資訊                                                                                                                                                                                                                                                                                                                                                                                                                            |
| ----------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Surface Laptop Studio**                 | heci<br>ialpss2_gpio2_tgl<br>ialpss2_uart2_tgl<br>intelthcbase<br>surfacehidminidriver<br>surfacehotplug<br>surfaceintegrationdriver<br>surfacepenwirelesschargerhotkey<br>surfacesarmanager<br>surfaceserialhubdriver<br>surfacestoragefwupdateenum<br>surfacestoragefwupdatekbg40zns256gpackage<br>surfacewakeontouchcontrol                                                                                                                                                                                                                                                 | 不適用                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Pro 8**                         | intelthcbase<br>ManagementEngine<br>surfaceacpiplatformextension<br>SurfaceBattery<br>SurfaceCoverClick<br>SurfaceEthernetAdapter<br>SurfaceHidMini<br>SurfaceHotPlug<br>surfaceintegrationdriver<br>SurfaceSar<br>SurfaceSerialHub<br>surfacetimealarmacpifilter<br>surfacetypecoverv7fprude<br>SurfaceUcmUcsiHidClient<br>surfacevirtualfunctionenum<br>tbtslimhostcontroller<br>TglChipset<br>TglSerial                                                                                                                                                                     | 不適用                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 搭配 Intel 處理器** | TglSerial<br>IntelPreciseTouch<br>SurfaceEthernetAdapter<br>SurfaceBattery<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceSerialHub<br>SurfaceTconDriver<br>surfacetimealarmacpifilter<br>surfacevirtualfunctionenum<br>TglChipset<br>ManagementEngine                                                                                                                                                                                                                                                                                                                          | 不適用                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 4 與 AMD 處理器**   | U0361415<br>AMDfendr<br>AMDGpio2<br>AMDI2c<br>AMDLpcFilterDriverAMDMicroPEP<br>AMDPsp<br>AMDSmf<br>AMDSpi<br>AMDUart<br>SurfaceEthernetAdapter<br>SMBUS<br>SurfaceBattery<br>SurfaceButton<br>SurfaceDigitizerHidSpiExtnPackage<br>SurfaceHIDFriendlyNames<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceOemPanel<br>SurfacePowerMeter<br>SurfacePowerTrackerCore<br>SurfaceSerialHub<br>SurfaceSMFClient<br>SurfaceSmfDisplayClient<br>SurfaceSystemManagementFramework<br>SurfaceTconDriver<br>SurfaceThermalPolicy<br>Surfacetimealarmacpifilter<br>SurfaceUcmUcsiHidClient | 不適用                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| **Surface Laptop 3 搭配 Intel 處理器** | SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SerialIOI2C<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\SurfaceHotPlug<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                                                                                                                   | 匯入下列資料夾將會在 PE 中啟用完整的鍵盤、追蹤板和觸控功能：<br><br>SerialIOGPIO<br>SerialIOI2C<br>SerialIOSPI<br>SerialIOUART<br>itouch<br>晶片組<br>晶片組LPSS<br>ChipsetNorthpeak<br>ManagementEngine<br>SurfaceAcpiNotify<br>SurfaceBattery<br>SurfaceDockIntegration<br>SurfaceHidMini<br>SurfaceHotPlug<br>SurfaceIntegration<br>SurfaceSerialHub<br>SurfaceService<br>SurfaceStorageFwUpdat |
| **Surface Laptop 2**                      | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\I2C<br>SurfacePlatformInstaller\Drivers\System\SPI<br>SurfacePlatformInstaller\Drivers\System\UART<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                           | 針對開頭為 「SurfaceUpdate」 的較新.msi檔案，請使用：<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\serialioi2c<br>SurfaceUpdate\SerialIOSPI<br>SurfaceUpdate\SerialIOUART<br>SurfaceUpdate\SurfaceHidMini<br>SurfaceUpdate\SurfaceSerialHub<br>SurfaceUpdate\Itouch                                                                                                                                                               |
| **Surface Laptop (第 1 代) **              | SurfacePlatformInstaller\Drivers\System\GPIO<br>SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver<br>SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver<br>SurfacePlatformInstaller\Drivers\System\PreciseTouch                                                                                                                                                                                                                                                                                                                                         | 對於以 **「SurfaceUpdate」** 開頭的較新.msi檔案，請使用：<br><br>SurfaceUpdate\SerialIOGPIO<br>SurfaceUpdate\SurfaceHidMiniDriver<br>SurfaceUpdate\SurfaceSerialHubDriver<br>SurfaceUpdate\Itouch                                                                                                                                                                                                                                       |

  > [!TIP]
  > 檢查下載的.msi套件，以判斷格式和目錄結構。  目錄結構的開頭是 SurfacePlatformInstaller (舊.msi檔案) 或 SurfaceUpdate (更新.msi檔案) 視發行.msi的時間而定。

## <a name="verify-imported-drivers--configure-windows-pe-properties"></a>確認匯入的驅動程式&設定Windows PE 屬性

1. 確認 WindowsPEX64 資料夾現在包含匯入的驅動程式，如下圖所示：

   ![顯示部署 Workbench 之 WindowsPEX64 資料夾中新匯入驅動程式的影像。](./images/surface-laptop-keyboard-2.png)
1. 設定使用 WindowsPEX64 資料夾的選取設定檔，如下圖所示：

   ![顯示選取的 WindowsPEX64 資料夾做為選取設定檔一部分的影像。](./images/surface-laptop-keyboard-3.png)
1. 將 MDT 部署共用的 Windows PE 屬性設定為使用新的選取設定檔，如下所示：
    - 針對 **[平臺**]，選取 **[x64]**。
    - 針對 **[選取設定檔**]，選取新的設定檔。
    - **從選取設定檔中選取 [包含所有驅動程式]**。

    ![顯示 MDT 部署共用Windows PE 屬性的影像。](./images/surface-laptop-keyboard-4.png)
4. 使用選取設定檔或**DriverGroup001**變數，確認您已設定其餘的Surface Laptop驅動程式。
    - 針對 Surface Laptop (第 1 代) ，模型會**Surface Laptop**。 其餘的Surface Laptop驅動程式應該位於 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 資料夾中，如下圖所示。
    - 針對 Surface Laptop 2，模型**Surface Laptop 2**。 其餘Surface Laptop驅動程式應位於 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 2 資料夾中。
    - 若Surface Laptop 3 搭配 Intel 處理器，則模型Surface Laptop 3。 其餘Surface Laptop驅動程式位於 \MDT Deployment Share\Out-of-Box Drivers\Windows10\X64\Surface Laptop 3 資料夾中。

    ![顯示 Deployment Workbench Surface Laptop 資料夾中一般Surface Laptop (第 1 代) 驅動程式的影像。](./images/surface-laptop-keyboard-5.png)

將 MDT 部署共用設定為使用新的選取設定檔和相關設定之後，請繼續執行部署程式，如[使用 MDT 部署Windows 10映射：步驟 6：建立部署工作順序](/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)中所述。
