---
title: Microsoft Surface 部署加速器 (Surface)
description: Microsoft Surface 部署加速器為組織提供快速且簡易的部署機制來為 Surface 裝置重新安裝映像。
ms.assetid: E7991E90-4AAE-44B6-8822-58BFDE3EADE4
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
keywords: 部署, 安裝, 工具
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.date: 5/08/2020
ms.openlocfilehash: 3ede7311289dc4bc720735c0142ff3a46fbb69e7
ms.sourcegitcommit: 582c5a79881c58c4f1aa66cfcab46db966ca9f24
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/16/2020
ms.locfileid: "11016554"
---
# Microsoft Surface 部署加速器

Microsoft Surface 部署加速器 (SDA) 使用免費的 Microsoft 部署工具，自動建立和設定 Microsoft 建議的部署體驗。

在2020年4月重新設計，可在公司環境中簡化並自動部署表面影像，SDA 工具可讓您建立「工廠狀」 Windows 影像，您可以根據組織的需求自訂。

「開放來源」、「腳本驅動」 SDA 工具利用 windows 10 (ADK) 的 Windows 評量和部署套件，方便您在測試或生產環境中建立 Windows 影像 () WIM。 如果未安裝最新的 ADK，則會在執行 SDA 工具時下載並安裝它。

產生的影像會緊密符合裸機復原 (BMR) 影像的設定，沒有任何預先安裝的應用程式（例如 Microsoft Office 或 Surface UWP 應用程式）。

## 需求

1. USB 拇指磁片磁碟機大小至少 16 GB。 USB 磁片磁碟機將會設定格式。
2. Windows 10 專業版或 Windows 10 企業版的 .iso 檔案。 媒體建立工具可用於下載 Windows 10 並建立 .iso 檔案。 如需詳細資訊，請參閱 [下載 Windows 10](https://www.microsoft.com/software-download/windows10)。
3. 在執行 Windows 10 版本2004或更新版本的裝置上使用網際網路存取。

如需詳細的需求清單，請參閱讀我檔案的 [ [先決條件](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) ] 區段。

## 如何執行 SDA

**若要執行 SDA：**

1. 移至 GitHub 上的 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 。 
2. 請參閱 [自述](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) 檔。
3. 在 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 頁面上，按一下 [程式 **代碼** ] 按鈕，然後選取 [ **下載 ZIP** ]，將檔案儲存在本機的電腦上。
4. 以滑鼠右鍵按一下 .zip 檔案，然後按一下 [ **屬性**]。
5. 選取 [ **一般** ] 索引標籤上的 [ **解除封鎖** ] 核取方塊，然後按一下 **[確定]**。
6. 將 .zip 檔案解壓縮至硬碟上的某個位置 (ex： C:\SDA) ]。
7. 開啟提升許可權的 Windows PowerShell 提示，並將目前會話的 ExecutionPolicy 設定為 [不受限制]。

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. 執行 SDA 腳本，為您的環境指定參數。 您可以使用此腳本來建立影像，以在各種不同的 Surface 裝置上安裝 Windows 10。 如需支援裝置的完整清單，請參閱 SDA 讀我檔案中的 [裝置參數說明](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) 。 

    例如，下列命令會建立可啟動的 USB 磁片磁碟機，以用於 [在 Surface Hub 2 上安裝 Windows 10](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os)：

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    [範例腳本] 輸出如下所示。

   ![執行 Surface 部署加速器工具](images/sda1.png)

    此腳本將需要大約45分鐘的時間才能執行，但可能需要較長的時間，視可用的 CPU 和磁片資源而定。 

    在建立 Windows 影像之後，腳本會要求您插入並確認您的 USB 磁片磁碟機盤符。 然後 USB 磁片磁碟機將會格式化、設定為可引導，以及複製的檔案，以啟用 Surface 裝置的自訂 Windows 10 影像。

9. 將 USB 磁片磁碟機插入您要安裝 Windows 10 的裝置，然後重新開機以開始安裝 Windows 10。 在 BIOS 中必須啟用 USB 啟動，這可能會要求您暫時停用 [安全啟動]。

> [!IMPORTANT]
> 從 USB 磁片磁碟機啟動後，就會立即開始安裝 Windows 10。 在插入 USB 並重新啟動之前，請確定您的裝置已準備好。 

## 相關連結

 - [在 GitHub 上發佈的開啟來源映射部署工具](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [下載並安裝 Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
