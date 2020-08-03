---
title: 如何啟用表面電源喚醒
ms.author: v-todmc
author: mccoybot
ms.date: 7/30/2020
audience: ITPro
search.appverid:
- SPO160
- MET150
appliesto:
- Surface Book 3
- Surface Pro 7
- Surface Laptop 3
- Surface Pro X
ms.custom:
- CI 121602
ms.reviewer: johnk@cadencepreferred.com
description: 說明如何啟用和停用適用于 Surface 裝置的喚醒功能。
keywords: 更新、部署、驅動程式、wol、局域網喚醒
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: 271831651280299a40c4e7a7480fa86e29bd1cf5
ms.sourcegitcommit: f875a45961ff5f3c04006afc8690b5e5965e4d80
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/31/2020
ms.locfileid: "10903003"
---
# 在 Surface 裝置上喚醒電源

您可以在離開辦公桌時關閉 Surface 裝置，或將它設為睡眠模式，以節省電池。 若要改善這些裝置的可管理性，請先喚醒電源啟用相容的 Surface 裝置，以便在重新電源開啟時自動啟動。 設定 [在 Power 喚醒] 需要使用 Surface Enterprise 管理模式（SEMM），不論是透過 Surface UEFI 配置或 UEFI 管理員。

[電源開啟] 是下列裝置上可用的功能：

- Surface Book 3
- Surface Pro 7
- Surface 膝上型電腦3
- Surface Pro X 

## 概述與先決條件

您可以使用 Surface UEFI 配置單元來設定個別的 UEFI 設定，這些設定是儲存在 Windows 安裝程式的 .msi 套件中，以發佈至目標裝置。 

> [!NOTE]
> 本文假設您熟悉如何使用 SEMM。 如需詳細資訊，請參閱[Surface Enterprise 管理模式（SEMM）](surface-enterprise-management-mode.md)檔。

## 啟用喚醒功能

1.  下載最新版本的[SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。
2.  以系統管理員身分登入您的 Surface 裝置，然後開啟**SURFACE UEFI 配置**器，選取 [ **surface 裝置**]，然後選取 **[下一步]**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
3.  選取 [**開始**]，然後在 [設定**套件**] 底下選取 [**建立**]。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="選取 [建立配置套件]。":::
4.  選取 [**憑證保護**]，然後新增您的憑證 .pfx 檔案。 輸入密碼之後，請選取 **[下一步]**。 視需要新增**密碼保護**，然後選取 **[下一步]**。
5.  在 [**選擇您要設定目標的表面類型**] 頁面上，視需要選取您的目標裝置。 例如， **Surface Pro 7**。
6.  在 [**高級功能**] 頁面上，選取 [**電源喚醒**]，並設定為 [**開啟**]。 選取 **\[下一步\]**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="選取 [電源開啟後喚醒] 並設定為 [開啟]。"::: 
7.  在 [**成功**] 頁面上，選取 [**結束**]。 如果這是您第一次為裝置提供設定，系統會提示您提供憑證指紋的最後兩個字元。 
8.  儲存 .msi 套件。 

## 套用 MSI 套件 

您可以使用軟體發佈工具（例如 Microsoft 端點設定管理員），將 MSI 套件套用到您網路上的裝置。 此套裝程式含在本機電腦上安裝套件的步驟。 

1.  開啟提升許可權的命令提示字元，然後輸入 .msi 檔案的完整路徑，以執行 .msi 封裝。 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  在 [**警告**] 對話方塊中，選取 **[確定] 或 [** 視需要停用 Bitlocker]。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="視需要選取 [確定] 或 [停用 Bitlocker]。":::
3.  在 [歡迎] 頁面上，選取 **[下一步]** 以執行套件，並套用新設定的 UEFI 設定。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="在 [歡迎] 頁面中，選取 [下一步]。":::
4.  重新開機您的裝置。 

[電源開啟] 現已設定。 若要測試設定，請關閉您的裝置，中斷電源連接，然後重新連接電源。 裝置將會自動啟動。 

## 詳細資訊

如需詳細資訊，請參閱下列文章。 

- [Surface 企業管理模式](surface-enterprise-management-mode.md)
- [在 Surface 裝置上喚醒局域網](wake-on-lan-for-surface-devices.md)

仍需要協助？ 移至[Microsoft 社區](https://answers.microsoft.com/)。