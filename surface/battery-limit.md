---
title: '電池限制設定 (表面) '
description: 電池計量限制是一種 UEFI 設定，可變更 Surface 裝置電池的充電速度，並可能延長其壽命。
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.reviewer: jesko
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
manager: laurawi
audience: itpro
ms.date: 1/15/2021
ms.openlocfilehash: 8ce1dcfc621a547aca9ca1db322f3ed2ce082728
ms.sourcegitcommit: 1b86286bd13b13749ddbf454ae78d9a24fec44ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/15/2021
ms.locfileid: "11271140"
---
# 電池限制設定

[電池限制] 選項是 [UEFI] 設定，可變更 Surface 裝置電池的充電方式，並可能延長其壽命。 在裝置持續連接電源的情況下（例如，裝置已整合至 kiosk 解決方案）時，建議使用此設定。  

## 電池計量限制的運作方式

將裝置設定為電池限制會變更用來為裝置電池充電的通訊協定。 啟用電池計量限制後，電池計量將限制在其最大容量的50%。 Windows 中報告的費用層級會反映此限制。 因此，它會顯示電池計量已計費至50%，且不會超出此限制。 如果您在裝置超過50% 時啟用電池限制，電池圖示會顯示裝置已插入但正在放電，直到裝置達到其最大充電容量的50%。  

## 支援的裝置

電池限制 UEFI 設定會內置於最新的 Surface 裝置中，包括 Surface Pro 7 +、Surface Pro 7 及 Surface 膝上型電腦3。 較舊的裝置需要 [SURFACE UEFI 固件更新](manage-surface-driver-and-firmware-updates.md)，可透過 Windows update 或透過 [Surface 支援網站](https://support.microsoft.com/help/4023482/surface-download-drivers-and-firmware-for-surface)上的 MSI 驅動程式和固件套件進行。 針對每個支援的裝置所需的特定 Surface UEFI 版本，核取 [ [啟用 [電池限制]：必須插入長時間的 surface 裝置](https://support.microsoft.com/help/4464941) 。 

## 在 Surface UEFI 中啟用電池計量限制 (Surface Pro 4 及更新版本) 

您可以在開啟裝置) 時，透過啟動至 Surface UEFI (**電源 + Vol** ，來設定 Surface Uefi 電池限制設定。 選擇 [ **啟動**設定]，然後在 [ **高級選項**] 底下，將 [ **啟用電池限制模式]** 切換為 [ **開啟**]。  

![電池限制高級選項](images/enable-bl.png) 

## 在表面移至表面的 [移至 2] 啟用電量限制
您可以在開啟裝置) 時，透過啟動至 Surface UEFI (**電源 + Vol** 來設定表面電量限制設定。 選擇 [ **啟動**設定]，然後在 [ **展臺模式]** 下，將滑杆向右移動以將電池限制設定為 [ **已啟用**]。  

![在 Surface 中轉時的 Kiosk 模式電池計量限制](images/go-batterylimit.png) 

## 在 Surface UEFI 中啟用電池限制 (Surface Pro 3) 

您可以在開啟裝置) 時，透過啟動至 Surface UEFI (**電源 + Vol** ，來設定 Surface Uefi 電池限制設定。 選擇 [ **展臺模式]**，選取 [ **電量限制**]，然後選擇 [ **啟用**]。

![[高級] 選項的螢幕擷取畫面](images/enable-bl-sp3.png) 

![進階選項](images/enable-bl-sp3-2.png) 

## 使用 [Surface Enterprise 管理] 模式 (SEMM) 或 Surface Pro 3 固件 PowerShell 腳本啟用電池限制

您也可以透過下列方法，使用表面 UEFI 電池限制：

- Surface Pro 4 及更新版本 
    - [Microsoft Surface UEFI 配置器](https://docs.microsoft.com/surface/surface-enterprise-management-mode)  
    - Surface UEFI 管理員 Powershell 腳本在[IT 下載的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中 ( # A0) 
- Surface Pro 3 
    - [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)

### 使用 Microsoft Surface UEFI 配置器

若要設定電池限制模式，請在 SEMM (Surface Pro 4 及更新) 版本的 [**高級設定**] 設定頁面上，設定 [ **Kiosk 覆蓋**] 設定。

![[高級] 設定的螢幕擷取畫面](images/semm-bl.png)

### 使用 Surface UEFI 管理器 PowerShell 腳本

電池限制功能是透過下列設定加以控制：  

`407 = Battery Profile`

**描述**：電池使用模式的活動管理配置

**預設值**：  `0` 

將此設定為 `1` 以啟用電量限制。

### 使用 Surface Pro 3 固件工具

電池限制功能是透過下列設定加以控制：  

**名稱**： BatteryLimitEnable

**描述**： BatteryLimit

**目前值**：  `0` 

**預設值**： `0`

**建議值**： `0` 

將此設定為 `1` 以啟用電量限制。

>[!NOTE]
>若要設定此設定，您必須使用 [SP3_Firmware_Powershell_Scripts.zip](https://www.microsoft.com/download/details.aspx?id=46703)。 

