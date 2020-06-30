---
title: 如何在 MDT 部署期間啟用 Surface 膝上型電腦鍵盤
description: 當您使用 MDT 將 Windows 10 部署到 Surface 膝上型電腦時，您必須匯入鍵盤驅動程式，才能在 Windows PE 環境中使用。
keywords: windows 10 surface、自動化、自訂、mdt
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface
ms.sitesec: library
author: Teresa-Motiv
ms.author: v-tea
ms.topic: article
ms.reviewer: scottmca
ms.localizationpriority: medium
ms.audience: itpro
manager: jarrettr
appliesto:
- Surface Laptop (1st Gen)
- Surface Laptop 2
- Surface Laptop 3
ms.openlocfilehash: 5d4e4b46c109d9fe24fe75151c9eb1e0a8b702c0
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831303"
---
# 如何在 MDT 部署期間啟用 Surface 膝上型電腦鍵盤

本文討論使用 Microsoft 部署工具套件（MDT）的部署方法。 您也可以將此資訊套用到其他部署方法。 在大多數類型的 Surface 裝置上，鍵盤應該在精簡的觸控安裝（LTI）期間運作。 不過，Surface 膝上型電腦需要一些其他驅動程式，才能啟用鍵盤。 針對 Surface 膝上型電腦（1 Gen）和 Surface 膝上型電腦2裝置，您必須準備可讓您指定鍵盤驅動程式的資料夾結構和選取設定檔，以便在 LTI 的 Windows 預先安裝環境（Windows PE）階段使用。 如需此資料夾結構的詳細資訊，請參閱[使用 MDT 部署 Windows 10 影像：步驟5：準備驅動程式儲存庫](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt?redirectedfrom=MSDN#step-5-prepare-the-drivers-repository)。

> [!NOTE]
> 由於驅動程式衝突，目前不支援在相同的 Windows PE 啟動實例中新增 Surface 膝上型電腦2和 Surface 膝上型電腦3的鍵盤驅動程式。請改為使用個別的實例。

> [!IMPORTANT]
> 如果您要將 Windows 10 影像部署到已預先安裝 Windows 10 的 Surface 膝上型電腦，請參閱 KB [4032347：在 s 模式中，將 windows 部署到已預先安裝 windows 10 的 surface 裝置時會發生問題](https://support.microsoft.com/help/4032347/surface-preinstall-windows10-s-mode-issues)。

若要將鍵盤驅動程式新增至選取設定檔，請遵循下列步驟：

1. 從適當的位置下載最新的 Surface 膝上型電腦 MSI 檔案：
    - [Surface 膝上型電腦（第1代）驅動程式和固件](https://www.microsoft.com/download/details.aspx?id=55489)
    - [Surface 膝上型電腦2驅動程式與固件](https://www.microsoft.com/download/details.aspx?id=57515)
    - [含英特爾處理器驅動程式和固件的 Surface 膝上型電腦3](https://www.microsoft.com/download/details.aspx?id=100429)

2. 將 Surface 膝上型電腦 MSI 檔案的內容解壓至您可以輕鬆找到的資料夾（例如，c：\ surface_laptop_drivers）。 若要解壓縮內容，請開啟提升許可權的命令提示字元視窗，然後執行下列範例中的命令：

   ```cmd
   Msiexec.exe /a SurfaceLaptop_Win10_15063_1703008_1.msi targetdir=c:\surface_laptop_drivers /qn
   ```

3. 開啟部署工作臺，然後展開 [**部署共用**] 節點和您的部署共用，然後流覽至 [ **WindowsPEX64** ] 資料夾。

   ![在部署工作臺中顯示 WindowsPEX64 資料夾位置的影像](./images/surface-laptop-keyboard-1.png)

4. 以滑鼠右鍵按一下 [ **WindowsPEX64** ] 資料夾，然後選取 [匯**入驅動程式**]。
5. 依照 [匯入驅動程式] 嚮導中的指示，將驅動程式資料夾匯入 [WindowsPEX64] 資料夾。  

> [!NOTE]
>  檢查已下載的 MSI 套件，以判斷格式和目錄結構。  目錄結構會從 SurfacePlatformInstaller （較舊的 MSI 檔案）或 SurfaceUpdate （較新的 MSI 檔案）開始，視 MSI 的發行時間而定。 

若要支援 Surface 膝上型電腦（第1代），請匯入下列資料夾：

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\SurfaceHidMiniDriver
- SurfaceUpdate\SurfaceSerialHubDriver
- SurfaceUpdate\Itouch

若要支援 Surface 膝上型電腦2，請匯入下列資料夾：

 - SurfacePlatformInstaller\Drivers\System\GPIO
 - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
 - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
 - SurfacePlatformInstaller\Drivers\System\I2C
 - SurfacePlatformInstaller\Drivers\System\SPI
 - SurfacePlatformInstaller\Drivers\System\UART
 - SurfacePlatformInstaller\Drivers\System\PreciseTouch

或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：

- SurfaceUpdate\SerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\Itouch

 
若要支援含英特爾處理器的 Surface 膝上型電腦3，請匯入下列資料夾：

- SurfaceUpdate\IclSerialIOGPIO
- SurfaceUpdate\IclSerialIOI2C
- SurfaceUpdate\IclSerialIOSPI
- SurfaceUpdate\IclSerialIOUART
- SurfaceUpdate\SurfaceHidMini
- SurfaceUpdate\SurfaceSerialHub
- SurfaceUpdate\SurfaceHotPlug
- SurfaceUpdate\Itouch

匯入下列資料夾將在 Surface 膝上型電腦3的 PE 中啟用完整的鍵盤、軌跡板和觸控功能。

- IclSerialIOGPIO
- IclSerialIOI2C
- IclSerialIOSPI
- IclSerialIOUART
- itouch
- IclChipset
- IclChipsetLPSS
- IclChipsetNorthpeak
- ManagementEngine
- SurfaceAcpiNotify
- SurfaceBattery
- SurfaceDockIntegration
- SurfaceHidMini
- SurfaceHotPlug
- SurfaceIntegration
- SurfaceSerialHub
- SurfaceService
- SurfaceStorageFwUpdate


    > [!NOTE]
    >  檢查已下載的 MSI 套件，以判斷格式和目錄結構。  目錄結構會從 SurfacePlatformInstaller （較舊的 MSI 檔案）或 SurfaceUpdate （較新的 MSI 檔案）開始，視 MSI 的發行時間而定。 

    若要支援 Surface 膝上型電腦（第1代），請匯入下列資料夾：

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHidMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\SurfaceHidMiniDriver
    - SurfaceUpdate\SurfaceSerialHubDriver
    - SurfaceUpdate\Itouch

    若要支援 Surface 膝上型電腦2，請匯入下列資料夾：

     - SurfacePlatformInstaller\Drivers\System\GPIO
     - SurfacePlatformInstaller\Drivers\System\SurfaceHIDMiniDriver
     - SurfacePlatformInstaller\Drivers\System\SurfaceSerialHubDriver
     - SurfacePlatformInstaller\Drivers\System\I2C
     - SurfacePlatformInstaller\Drivers\System\SPI
     - SurfacePlatformInstaller\Drivers\System\UART
     - SurfacePlatformInstaller\Drivers\System\PreciseTouch

    或者，對於以 "SurfaceUpdate" 開頭的較新的 MSI 檔案，請使用：

    - SurfaceUpdate\SerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\Itouch

    若要支援含英特爾處理器的 Surface 膝上型電腦3，請匯入下列資料夾：

    - SurfaceUpdate\IclSerialIOGPIO
    - SurfaceUpdate\IclSerialIOI2C
    - SurfaceUpdate\IclSerialIOSPI
    - SurfaceUpdate\IclSerialIOUART
    - SurfaceUpdate\SurfaceHidMini
    - SurfaceUpdate\SurfaceSerialHub
    - SurfaceUpdate\SurfaceHotPlug
    - SurfaceUpdate\Itouch

    > [!NOTE]
    > 針對含英特爾處理器的 Surface 膝上型電腦3，模型為 Surface 膝上型電腦3。 剩餘的 Surface 膝上型電腦驅動程式位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦 3] 資料夾中。

6. 確認 WindowsPEX64 資料夾現在包含已匯入的驅動程式。 該資料夾應如下所示：  

   ![在部署工作臺的 [WindowsPEX64] 資料夾中顯示新匯入驅動程式的影像](./images/surface-laptop-keyboard-2.png)

7. 設定使用 WindowsPEX64 資料夾的選取設定檔。 選取設定檔應如下所示：  

   ![顯示選取為選取設定檔一部分之 WindowsPEX64 資料夾的影像](./images/surface-laptop-keyboard-3.png)

8. 將 MDT 部署共用的 Windows PE 屬性設定為使用新的選取設定檔，如下所示：  

   - 針對 [**平臺**]，選取 [ **x64**]。
   - 針對 [**選取設定檔**]，選取新的設定檔。
   - 選取 **[包含選取設定檔中的所有驅動程式**]。
   
   ![顯示 MDT 部署共用的 Windows PE 屬性的圖像](./images/surface-laptop-keyboard-4.png)

9. 使用選取設定檔或**DriverGroup001**變數，確認您已設定剩餘的 Surface 膝上型電腦驅動程式。  
   - 針對 Surface 膝上型電腦（1 Gen），模型是**Surface 膝上型電腦**。 剩餘的 Surface 膝上型電腦驅動程式應該位於 \MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦資料夾中，如以下清單所示。
   - 如果是 Surface 膝上型電腦2，則模型為**Surface 膝上型電腦 2**。 剩餘的 Surface 膝上型電腦驅動程式應該位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型 2] 資料夾中。 
   - 針對含英特爾處理器的 Surface 膝上型電腦3，模型為 Surface 膝上型電腦3。 剩餘的 Surface 膝上型電腦驅動程式位於 [\MDT 部署 Share\Out-of-Box Drivers\Windows10\X64\Surface 膝上型電腦 3] 資料夾中。

   ![在部署工作臺的 [Surface 膝上型電腦] 資料夾中顯示一般 Surface 膝上型電腦（第1代）驅動程式的影像](./images/surface-laptop-keyboard-5.png)

將 MDT 部署共用設定為使用新的選取設定檔和相關設定之後，請按照[使用 MDT 部署 Windows 10 映射](https://docs.microsoft.com/windows/deployment/deploy-windows-mdt/deploy-a-windows-10-image-using-mdt#step-6-create-the-deployment-task-sequence)中的說明，繼續進行部署程式：建立部署任務序列。
