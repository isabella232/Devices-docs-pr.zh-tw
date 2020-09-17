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
# <span data-ttu-id="081eb-104">Microsoft Surface 部署加速器</span><span class="sxs-lookup"><span data-stu-id="081eb-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="081eb-105">Microsoft Surface 部署加速器 (SDA) 使用免費的 Microsoft 部署工具，自動建立和設定 Microsoft 建議的部署體驗。</span><span class="sxs-lookup"><span data-stu-id="081eb-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="081eb-106">在2020年4月重新設計，可在公司環境中簡化並自動部署表面影像，SDA 工具可讓您建立「工廠狀」 Windows 影像，您可以根據組織的需求自訂。</span><span class="sxs-lookup"><span data-stu-id="081eb-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="081eb-107">「開放來源」、「腳本驅動」 SDA 工具利用 windows 10 (ADK) 的 Windows 評量和部署套件，方便您在測試或生產環境中建立 Windows 影像 () WIM。</span><span class="sxs-lookup"><span data-stu-id="081eb-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="081eb-108">如果未安裝最新的 ADK，則會在執行 SDA 工具時下載並安裝它。</span><span class="sxs-lookup"><span data-stu-id="081eb-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="081eb-109">產生的影像會緊密符合裸機復原 (BMR) 影像的設定，沒有任何預先安裝的應用程式（例如 Microsoft Office 或 Surface UWP 應用程式）。</span><span class="sxs-lookup"><span data-stu-id="081eb-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

## <span data-ttu-id="081eb-110">需求</span><span class="sxs-lookup"><span data-stu-id="081eb-110">Requirements</span></span>

1. <span data-ttu-id="081eb-111">USB 拇指磁片磁碟機大小至少 16 GB。</span><span class="sxs-lookup"><span data-stu-id="081eb-111">A USB thumb drive at least 16 GB in size.</span></span> <span data-ttu-id="081eb-112">USB 磁片磁碟機將會設定格式。</span><span class="sxs-lookup"><span data-stu-id="081eb-112">The USB drive will be formatted.</span></span>
2. <span data-ttu-id="081eb-113">Windows 10 專業版或 Windows 10 企業版的 .iso 檔案。</span><span class="sxs-lookup"><span data-stu-id="081eb-113">An .iso file with Windows 10 Pro or Windows 10 Enterprise.</span></span> <span data-ttu-id="081eb-114">媒體建立工具可用於下載 Windows 10 並建立 .iso 檔案。</span><span class="sxs-lookup"><span data-stu-id="081eb-114">The media creation tool can be used to download Windows 10 and create an .iso file.</span></span> <span data-ttu-id="081eb-115">如需詳細資訊，請參閱 [下載 Windows 10](https://www.microsoft.com/software-download/windows10)。</span><span class="sxs-lookup"><span data-stu-id="081eb-115">For more information, see [Download Windows 10](https://www.microsoft.com/software-download/windows10).</span></span>
3. <span data-ttu-id="081eb-116">在執行 Windows 10 版本2004或更新版本的裝置上使用網際網路存取。</span><span class="sxs-lookup"><span data-stu-id="081eb-116">A device running Windows 10, version 2004 or later with Internet access.</span></span>

<span data-ttu-id="081eb-117">如需詳細的需求清單，請參閱讀我檔案的 [ [先決條件](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) ] 區段。</span><span class="sxs-lookup"><span data-stu-id="081eb-117">See the [Prerequisites](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#prerequisites) section of the README document for a detailed list of requirements.</span></span>

## <span data-ttu-id="081eb-118">如何執行 SDA</span><span class="sxs-lookup"><span data-stu-id="081eb-118">How to run the SDA</span></span>

**<span data-ttu-id="081eb-119">若要執行 SDA：</span><span class="sxs-lookup"><span data-stu-id="081eb-119">To run SDA:</span></span>**

1. <span data-ttu-id="081eb-120">移至 GitHub 上的 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 。</span><span class="sxs-lookup"><span data-stu-id="081eb-120">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="081eb-121">請參閱 [自述](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) 檔。</span><span class="sxs-lookup"><span data-stu-id="081eb-121">Review the [README](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md) documentation.</span></span>
3. <span data-ttu-id="081eb-122">在 [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 頁面上，按一下 [程式 **代碼** ] 按鈕，然後選取 [ **下載 ZIP** ]，將檔案儲存在本機的電腦上。</span><span class="sxs-lookup"><span data-stu-id="081eb-122">On the [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) page, click the **Code** button and then select **Download ZIP** to save the files locally on your computer.</span></span>
4. <span data-ttu-id="081eb-123">以滑鼠右鍵按一下 .zip 檔案，然後按一下 [ **屬性**]。</span><span class="sxs-lookup"><span data-stu-id="081eb-123">Right-click the .zip file and then click **Properties**.</span></span>
5. <span data-ttu-id="081eb-124">選取 [ **一般** ] 索引標籤上的 [ **解除封鎖** ] 核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="081eb-124">On the **General** tab, select the **Unblock** checkbox and then click **OK**.</span></span>
6. <span data-ttu-id="081eb-125">將 .zip 檔案解壓縮至硬碟上的某個位置 (ex： C:\SDA) ]。</span><span class="sxs-lookup"><span data-stu-id="081eb-125">Extract the .zip file to a location on your hard drive (ex: C:\SDA).</span></span>
7. <span data-ttu-id="081eb-126">開啟提升許可權的 Windows PowerShell 提示，並將目前會話的 ExecutionPolicy 設定為 [不受限制]。</span><span class="sxs-lookup"><span data-stu-id="081eb-126">Open an elevated Windows PowerShell prompt and set ExecutionPolicy for the current session to Unrestricted.</span></span>

    ```powershell
    Set-ExecutionPolicy -Scope Process -ExecutionPolicy Unrestricted -Force
    ```
8. <span data-ttu-id="081eb-127">執行 SDA 腳本，為您的環境指定參數。</span><span class="sxs-lookup"><span data-stu-id="081eb-127">Run the SDA script specifying parameters for your environment.</span></span> <span data-ttu-id="081eb-128">您可以使用此腳本來建立影像，以在各種不同的 Surface 裝置上安裝 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="081eb-128">The script can be used to create images to install Windows 10 on a variety of Surface devices.</span></span> <span data-ttu-id="081eb-129">如需支援裝置的完整清單，請參閱 SDA 讀我檔案中的 [裝置參數說明](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) 。</span><span class="sxs-lookup"><span data-stu-id="081eb-129">For a full list of supported devices, see the [Device parameter description](https://github.com/microsoft/SurfaceDeploymentAccelerator/blob/master/README.md#full-parameter-documentation) in the SDA README article.</span></span> 

    <span data-ttu-id="081eb-130">例如，下列命令會建立可啟動的 USB 磁片磁碟機，以用於 [在 Surface Hub 2 上安裝 Windows 10](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os)：</span><span class="sxs-lookup"><span data-stu-id="081eb-130">For example, the following command will create a bootable USB drive that can be used to [install Windows 10 on Surface Hub 2](https://docs.microsoft.com/surface-hub/surface-hub-2s-migrate-os):</span></span>

    ```powershell
    .\CreateSurfaceWindowsImage.ps1 -ISO C:\SDA\enterprise_client.iso -OSSKU Enterprise -DestinationFolder C:\Output -Device SurfaceHub2 -CreateUSB $True
    ```
    <span data-ttu-id="081eb-131">[範例腳本] 輸出如下所示。</span><span class="sxs-lookup"><span data-stu-id="081eb-131">Sample script output is below.</span></span>

   ![執行 Surface 部署加速器工具](images/sda1.png)

    <span data-ttu-id="081eb-133">此腳本將需要大約45分鐘的時間才能執行，但可能需要較長的時間，視可用的 CPU 和磁片資源而定。</span><span class="sxs-lookup"><span data-stu-id="081eb-133">The script will require about 45 minutes to run, but could take longer depending on available CPU and disk resources.</span></span> 

    <span data-ttu-id="081eb-134">在建立 Windows 影像之後，腳本會要求您插入並確認您的 USB 磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="081eb-134">After creating a Windows image, the script will ask you to insert and confirm the drive letter of your USB drive.</span></span> <span data-ttu-id="081eb-135">然後 USB 磁片磁碟機將會格式化、設定為可引導，以及複製的檔案，以啟用 Surface 裝置的自訂 Windows 10 影像。</span><span class="sxs-lookup"><span data-stu-id="081eb-135">The USB drive will then be formatted, configured as bootable, and files copied to enable installation of the custom Windows 10 image for Surface devices.</span></span>

9. <span data-ttu-id="081eb-136">將 USB 磁片磁碟機插入您要安裝 Windows 10 的裝置，然後重新開機以開始安裝 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="081eb-136">Insert the USB drive into the device where you want to install Windows 10 and reboot to begin installing Windows 10.</span></span> <span data-ttu-id="081eb-137">在 BIOS 中必須啟用 USB 啟動，這可能會要求您暫時停用 [安全啟動]。</span><span class="sxs-lookup"><span data-stu-id="081eb-137">USB boot must be enabled in BIOS, which can require that you temporarily disable Secure Boot.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="081eb-138">從 USB 磁片磁碟機啟動後，就會立即開始安裝 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="081eb-138">Booting from the USB drive will immediately begin installing Windows 10.</span></span> <span data-ttu-id="081eb-139">在插入 USB 並重新啟動之前，請確定您的裝置已準備好。</span><span class="sxs-lookup"><span data-stu-id="081eb-139">Ensure that your device is ready before inserting the USB and restarting.</span></span> 

## <span data-ttu-id="081eb-140">相關連結</span><span class="sxs-lookup"><span data-stu-id="081eb-140">Related links</span></span>

 - [<span data-ttu-id="081eb-141">在 GitHub 上發佈的開啟來源映射部署工具</span><span class="sxs-lookup"><span data-stu-id="081eb-141">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)
 - [<span data-ttu-id="081eb-142">下載並安裝 Windows ADK</span><span class="sxs-lookup"><span data-stu-id="081eb-142">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
