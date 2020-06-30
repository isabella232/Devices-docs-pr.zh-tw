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
ms.openlocfilehash: 32d8fded8c325766f7ab6bbc750ba7fe13e01d70
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831222"
---
# <span data-ttu-id="bec7c-104">Microsoft Surface 部署加速器</span><span class="sxs-lookup"><span data-stu-id="bec7c-104">Microsoft Surface Deployment Accelerator</span></span>

<span data-ttu-id="bec7c-105">Microsoft Surface 部署加速器（SDA）可使用免費的 Microsoft 部署工具，自動建立和設定 Microsoft 建議的部署體驗。</span><span class="sxs-lookup"><span data-stu-id="bec7c-105">Microsoft Surface Deployment Accelerator (SDA) automates the creation and configuration of a Microsoft recommended deployment experience by using free Microsoft deployment tools.</span></span>

<span data-ttu-id="bec7c-106">在2020年4月重新設計，可在公司環境中簡化並自動部署表面影像，SDA 工具可讓您建立「工廠狀」 Windows 影像，您可以根據組織的需求自訂。</span><span class="sxs-lookup"><span data-stu-id="bec7c-106">Redesigned in April 2020 to simplify and automate deployment of Surface images in a corporate environment, the SDA tool allows you to build a “factory-like” Windows image that you can customize to your organizational requirements.</span></span>

<span data-ttu-id="bec7c-107">開放原始碼、腳本驅動的 SDA 工具利用 windows 10 的 Windows 評量與部署套件（ADK），方便您在測試或生產環境中建立 Windows 映像（WIM）。</span><span class="sxs-lookup"><span data-stu-id="bec7c-107">The open source, script-driven SDA tool leverages the Windows Assessment and Deployment Kit (ADK) for Windows 10, facilitating the creation of Windows images (WIM) in test or production environments.</span></span> <span data-ttu-id="bec7c-108">如果未安裝最新的 ADK，則會在執行 SDA 工具時下載並安裝它。</span><span class="sxs-lookup"><span data-stu-id="bec7c-108">If the latest ADK is not already installed, it will be downloaded and installed when running the SDA tool.</span></span>

<span data-ttu-id="bec7c-109">產生的影像會與裸機復原（BMR）影像的設定緊密地相符，沒有任何預先安裝的應用程式（例如 Microsoft Office 或 Surface UWP 應用程式）。</span><span class="sxs-lookup"><span data-stu-id="bec7c-109">The resulting image closely matches the configuration of Bare Metal Recovery (BMR) images, without any pre-installed applications such as Microsoft Office or the Surface UWP application.</span></span>

**<span data-ttu-id="bec7c-110">若要執行 SDA：</span><span class="sxs-lookup"><span data-stu-id="bec7c-110">To run SDA:</span></span>**

1. <span data-ttu-id="bec7c-111">移至 GitHub 上的[SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 。</span><span class="sxs-lookup"><span data-stu-id="bec7c-111">Go to [SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) on GitHub.</span></span> 
2. <span data-ttu-id="bec7c-112">選取 [**複製] 或 [下載**並查看讀我檔案]。</span><span class="sxs-lookup"><span data-stu-id="bec7c-112">Select **Clone or Download** and review the Readme file.</span></span>
3. <span data-ttu-id="bec7c-113">使用適用于您環境的適當變數編輯腳本（如讀我檔案中所述），並在您的測試環境中執行它之前進行檢查。</span><span class="sxs-lookup"><span data-stu-id="bec7c-113">Edit the script with the appropriate variables for your environment, as documented in the Readme, and review before running it in your test environment.</span></span> 

   ![執行 Surface 部署加速器工具](images/surface-deployment-accelerator.png)

## <span data-ttu-id="bec7c-115">相關連結</span><span class="sxs-lookup"><span data-stu-id="bec7c-115">Related links</span></span>

 - [<span data-ttu-id="bec7c-116">在 GitHub 上發佈的開啟來源映射部署工具</span><span class="sxs-lookup"><span data-stu-id="bec7c-116">Open source image deployment tool released on GitHub</span></span>](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [<span data-ttu-id="bec7c-117">下載並安裝 Windows ADK</span><span class="sxs-lookup"><span data-stu-id="bec7c-117">Download and install the Windows ADK</span></span>](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
