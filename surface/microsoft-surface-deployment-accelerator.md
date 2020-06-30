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
# Microsoft Surface 部署加速器

Microsoft Surface 部署加速器（SDA）可使用免費的 Microsoft 部署工具，自動建立和設定 Microsoft 建議的部署體驗。

在2020年4月重新設計，可在公司環境中簡化並自動部署表面影像，SDA 工具可讓您建立「工廠狀」 Windows 影像，您可以根據組織的需求自訂。

開放原始碼、腳本驅動的 SDA 工具利用 windows 10 的 Windows 評量與部署套件（ADK），方便您在測試或生產環境中建立 Windows 映像（WIM）。 如果未安裝最新的 ADK，則會在執行 SDA 工具時下載並安裝它。

產生的影像會與裸機復原（BMR）影像的設定緊密地相符，沒有任何預先安裝的應用程式（例如 Microsoft Office 或 Surface UWP 應用程式）。

**若要執行 SDA：**

1. 移至 GitHub 上的[SurfaceDeploymentAccelerator](https://github.com/microsoft/SurfaceDeploymentAccelerator) 。 
2. 選取 [**複製] 或 [下載**並查看讀我檔案]。
3. 使用適用于您環境的適當變數編輯腳本（如讀我檔案中所述），並在您的測試環境中執行它之前進行檢查。 

   ![執行 Surface 部署加速器工具](images/surface-deployment-accelerator.png)

## 相關連結

 - [在 GitHub 上發佈的開啟來源映射部署工具](https://techcommunity.microsoft.com/t5/surface-it-pro-blog/open-source-image-deployment-tool-released-on-github/ba-p/1314115)

 - [下載並安裝 Windows ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)
