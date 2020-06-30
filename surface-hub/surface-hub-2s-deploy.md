---
title: 建立 Surface Hub 2S 的佈建套件
description: 此頁面說明如何使用預配套件和其他工具來部署 Surface Hub 2。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 8f91b751a10977d80210d10ac1b48a93d9ba0f6f
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832186"
---
# 建立 Surface Hub 2S 的佈建套件

您可以使用 Windows 配置設計工具（WCD）建立預配套件，以自動化 Surface Hub 2 的部署程式。 使用預配套件來新增憑證、設定 proxy、設定裝置管理員和裝置帳戶。 您也可以使用置備套件和設定檔，以單一的 USB 拇指磁片磁碟機來部署多個 Surface Hub。

### 安裝 Windows 設定設計工具

從 windows 10 版 Windows 評估與部署套件（ADK）安裝 Windows 配置設計工具。 下載並安裝[適用于 Windows 10 版本1703的 ADK](https://go.microsoft.com/fwlink/p/?LinkId=845542)。 如需詳細資訊，請參閱[下載並安裝 WINDOWS ADK](https://docs.microsoft.com/windows-hardware/get-started/adk-install)。

### 新增憑證

您可以將憑證授權單位憑證匯入到 Surface Hub 2 秒。
若要將憑證新增至 Surface Hub 2，您需要將每個憑證複本為 x.509 格式。 您無法匯入 .crt、.pfx 或其他容器格式。 必須將憑證匯入 Windows 配置設計工具，並依階層排列：

 ![新增憑證](images/sh2-wcd.png)

### 在 OOBE 期間設定 proxy

在 Windows [組態工具設計工具] 中，移至 [設定 proxy 設定] 索引標籤，然後輸入適當的設定，如下所示。

 ![設定 Proxy 設定](images/sh2-proxy.png) 

> [!NOTE]
> 設定 [proxy 設定] 時，如果您想要使用安裝程式腳本或 proxy 伺服器，請關閉 [**自動偵測設定**]。 您可以使用安裝程式腳本*或*proxy 伺服器，而不是兩者。

### 含 Azure Active Directory 的關聯 Surface Hub 中樞

您可以使用置備套件，將 Surface Hub 2 與 Azure Active Directory 封裝在一起：如 Azure Active Directory 全域系統管理員，您可以使用大量的 Windows 裝置，將大量的新 Windows 裝置加入 Azure Active Directory 和 Intune，並使用大量的權杖。

若要建立大量權杖，請為它指定一個易記的名稱、設定到期日（最多30天），並使用您的系統管理員認證來取得權杖，如下所示：

 ![設定裝置管理員](images/sh2-token.png) <br><br>
 ![設定裝置管理員](images/sh2-token2.png) <br><br>
 ![設定裝置管理員](images/sh2-token3.png) <br><br>

### 預配多個裝置（.csv 檔案）

除了預配套件之外，您還可以使用 Surface Hub 設定檔，讓您更輕鬆地設定裝置。 Surface Hub 設定檔包含適用于無線投影的裝置帳戶和易記名稱清單。 在第一次執行期間，您會看到從設定檔選擇裝置帳戶和易記名稱的選項。

### 建立 Surface Hub 設定檔

1. 使用 Microsoft Excel 或其他 CSV 編輯器，建立名為： **SurfaceHubConfiguration.csv**的 CSV 檔案
2. 以這個格式輸入裝置帳戶和易記名稱的清單：

```
<DeviceAccountName>,<DeviceAccountPassword>,<FriendlyName>
```

3. 將檔案儲存到您複製 PPKG 檔案的 USB 拇指磁片磁碟機根目錄。

    ![設定檔範例](images/sh2-config-file.png)
