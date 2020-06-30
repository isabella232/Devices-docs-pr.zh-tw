---
title: 在 Surface 裝置上喚醒局域網（Surface）
description: 瞭解您可以如何使用 LAN 喚醒來遠端喚醒裝置，以執行管理或維護工作，或自動啟用管理解決方案，即使裝置已斷電也一樣。
keywords: 更新、部署、驅動程式、wol、局域網喚醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: scottmca
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 760ba75ea7b36238d6de722d38e44a3854073112
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831502"
---
# 適用於 Surface 裝置的網路喚醒

執行 Windows 10 （版本1607（又稱為 Windows 10 年度更新版）或更新版本的 surface 裝置，並使用 Surface 乙太網卡連線至有線網路，就能從連線的待機（WOL）喚醒。 有了 WOL，您就可以遠端喚醒裝置來執行管理或維護工作，或自動啟用管理解決方案（例如 Microsoft 端點建構管理員）。 例如，您可以將應用程式部署到與 Surface Dock 或 Surface Pro 3 插接站固定的 Surface 裝置，方法是在夜間辦公室是空的情況下，使用 Microsoft 端點組態管理員。

>[!NOTE]
>Surface 裝置必須連線到交流電源，且處於連線的待機（睡眠）以支援 WOL。 在休眠或關閉的裝置中無法進行 WOL。

## 支援的裝置

WOL 支援下列裝置：

* Surface 乙太網卡
* 從 USB 到乙太網路和 USB 配接器的 Surface
* Surface 擴充座
* Surface Pro 3 的 surface 插接站
* Surface 3
* Surface Pro 3
* Surface Pro 4
* Surface Pro （第5代）
* 使用 LTE Advanced 的 Surface Pro （第5代）
* Surface Book
* Surface 膝上型電腦（第1代）
* Surface Pro 6
* Surface Book 2
* Surface Laptop 2
* Surface Go
* 配備 LTE Advanced 的 Surface Go
* Surface Studio 2 （請參閱以下的 Surface Studio 2 指示）
* Surface Pro 7
* Surface 膝上型電腦3

## WOL 驅動程式

若要在 Surface 裝置上啟用 WOL 支援，必須有 Surface 乙太網配接器的特定驅動程式。 此驅動程式不包含在 Surface 裝置的標準驅動程式和固件套件中，您必須另行下載並安裝。 您可以從 Microsoft 下載中心的 [[表面工具](https://www.microsoft.com/download/details.aspx?id=46703)] 頁面下載 surface WOL 驅動程式（SurfaceWOL.msi）。

您可以在 Surface 裝置上執行這個 Microsoft Windows Installer （.msi）檔案來安裝 Surface WOL 驅動程式，也可以使用應用程式部署方案（例如 Microsoft 端點設定管理員）將它發佈到 Surface 裝置。 若要在部署期間包含 Surface WOL 驅動程式，您可以在部署期間將 .msi 檔案安裝為應用程式。 您也可以解壓縮 Surface WOL 驅動程式檔案，將它們包含在部署程式中。 例如，您可以將它們包含在您的 Microsoft 部署工具箱（MDT）部署共用中。 您可以在[使用 Microsoft 部署工具組將 Windows 10 部署到 Surface 裝置](https://technet.microsoft.com/itpro/surface/deploy-windows-10-to-surface-devices-with-mdt)中，深入瞭解使用 MDT 的 surface 部署。

> [!NOTE]
> 在安裝 SurfaceWOL.msi 期間，下列登錄機碼會設定為1的值，這可讓您輕鬆識別已安裝 WOL 驅動程式的系統。 如果您選擇在部署期間單獨提取並安裝這些驅動程式，則不會設定此登錄機碼，且必須手動設定或使用腳本進行設定。
> 
> **HKLM\SYSTEM\CurrentControlSet\Control\Power AllowSystemRequiredPowerRequests** 

若要解壓縮 SurfaceWOL.msi 的內容，請使用 MSIExec 系統管理安裝選項（**/a**），如下列範例所示，將內容解壓縮至 [C:\WOL\] 資料夾：

   `msiexec /a surfacewol.msi targetdir=C:\WOL /qn`

## Surface Studio 2 指示

若要在 Surface Studio 2 上啟用 WOL，您必須使用下列程式

1. 建立下列登錄機碼：

   ```console
   ; Set CONNECTIVITYINSTANDBY to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power\PowerSettings\F15576E8-98B7-4186-B944-EAFA664402D9]
   "Attributes"=dword:00000001
   ; Set EnforceDisconnectedStandby to 0 and AllowSystemRequiredPowerRequests to 1:
   [HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Power]
   "EnforceDisconnectedStandby"=dword:00000000
   "AllowSystemRequiredPowerRequests"=dword:00000001
   ```

2. 執行下列命令

    ```powercfg /SETACVALUEINDEX SCHEME_BALANCED SUB_NONE CONNECTIVITYINSTANDBY 1```

## 使用 Surface WOL

Surface WOL 驅動程式會符合 WOL 標準，讓裝置是由稱為幻資料包的特殊網路通訊 woken。 幻數資料包包含6個位元組的255（或十六進位中的 FF），後接目的電腦之 MAC 位址的16個重複專案。 您可以在[維琪百科](https://wikipedia.org/wiki/Wake-on-LAN#Magic_packet)上進一步瞭解幻資料包和 WOL 標準。

>[!NOTE]
>若要使用 WOL 傳送幻資料包並喚醒裝置，您必須知道目標裝置和乙太網路介面卡的 MAC 位址。 因為幻資料包不使用 IP 網路通訊協定，所以無法使用裝置的 IP 位址或 DNS 名稱。

許多管理解決方案（例如建構管理員）提供 WOL 的內建支援。 還有許多解決方案，包括 Microsoft Store app、PowerShell 模組、協力廠商應用程式，以及可讓您傳送幻資料包來喚醒裝置的協力廠商管理解決方案。 例如，您可以使用 TechNet [腳本中心] 的 [[局域網喚醒] PowerShell 模組](https://gallery.technet.microsoft.com/scriptcenter/Wake-On-Lan-815424c4)。 

>[!NOTE]
>在裝置與幻資料包 woken 之後，如果應用程式不積極地在系統上預防睡眠，或 AllowSystemRequiredPowerRequests 登錄機碼沒有設定為1，裝置就會回到睡眠狀態，這可讓應用程式防止睡眠。 如需此登錄機碼的詳細資訊，請參閱本文的 [ [WOL 驅動程式](#wol-driver)] 區段。
