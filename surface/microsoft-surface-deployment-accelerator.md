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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 0ececf7a21b4870c4fb6db2403d9a5e34a67fdba
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449466"
---
# <a name="microsoft-surface-deployment-accelerator"></a>Microsoft Surface 部署加速器

Microsoft Surface 部署 (SDA) 使用免費的 Microsoft 部署工具，自動化 Microsoft 建議的部署體驗的建立和組組。

SDA 工具于 2020 年 4 月重新設計，以簡化及自動化在公司環境中部署 Surface 影像，可讓您建立「類似工廠」的 Windows 影像，以便根據組織需求進行自訂。

以腳本為導向的開放來源 SDA 工具可運用 Windows 評估與部署套件 (ADK) Windows 10，方便在測試或生產環境中建立 Windows 影像 (WIM) 。 如果尚未安裝最新的 ADK，它會在執行 SDA 工具時下載並安裝。

產生的影像與 BMR (BMR) 的組配置非常符合，而沒有任何預先安裝的應用程式 ，例如 Microsoft Office 或 Surface UWP 應用程式。

## <a name="requirements"></a>需求

1. 大小至少為 16 GB 的 USB 拇指磁碟機。 USB 磁碟機會格式化。
2. 包含 Windows 10/11 Pro 或 Windows 10/11 Enterprise。 媒體建立工具可用來下載或Windows 10 Windows 11建立 .iso 檔案。 詳細資訊，請參閱下載[Windows 10](https://www.microsoft.com/software-download/windows10)。
3. 使用網際網路存取Windows 10版本 2004 或更新版本之裝置。

請參閱 [自述](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) 檔的先決條件一節，瞭解詳細的需求清單。

## <a name="how-to-run-the-sda"></a>如何執行 SDA

**若要執行 SDA：**

1. 請前往[SurfaceDeploymentAccelerator GitHub](https://github.com/microsoft/SurfaceDeploymentAccelerator)。 
2. 請閱 [閱讀我檔案](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) 。
3. 在[SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator)頁面上，按一下 [程式**** 代碼> 按鈕，然後選取 [下載**ZIP**以將檔案儲存在您電腦上。
4. 以滑鼠右鍵按一下.zip，然後按一下 [ **內容**。
5. 在 [ **一般」** 選項卡上，選取 **[解除封鎖** > 核取方塊，然後按一下 **[確定**。
6. 將.zip解壓縮到硬碟上的位置，例如：C：\SDA (：C：\SDA) 。
7. 開啟提升Windows PowerShell提示，將目前會話的執行策略設定為無限制。

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. 執行 SDA 腳本，為環境指定參數。 腳本可用來建立影像，以Windows 10或Windows 11 Surface 裝置上安裝。 有關支援裝置的完整清單，請參閱 SDA 自述 [文章中的裝置](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) 參數描述。 

    例如，下列命令會建立可啟動的 USB 磁碟機，可用於在[Windows 10 2 Surface Hub安裝](/surface-hub/surface-hub-2s-migrate-os)：

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    範例腳本輸出如下。

   ![執行 Surface 部署快速鍵工具。](images/sda1.png)

    腳本大約需要 45 分鐘才能執行，但可能需要較長的時間，視可用的 CPU 和磁片資源而不同。 

    建立圖像Windows之後，腳本會要求您插入並確認 USB 磁碟機的磁碟機號。 接著，USB 磁碟機會格式化、已配置為可啟動，並複製檔案以啟用安裝 Surface 裝置Windows 10或Windows 11圖像。

9. 將 USB 磁碟機插入您想要安裝或Windows 10，Windows 11重新開機以開始安裝。 必須在BIOS 中啟用 USB 啟動，這可能需要您暫時停用安全啟動。

> [!IMPORTANT]
> 從 USB 磁碟機啟動會立即開始安裝作業系統。 在插入 USB 並重新啟動之前，請確保您的裝置已準備就緒。 

## <a name="related-links"></a>相關連結

 - [開放來源圖像部署工具于 GitHub](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [下載並安裝 Windows ADK](/windows-hardware/get-started/adk-install)
