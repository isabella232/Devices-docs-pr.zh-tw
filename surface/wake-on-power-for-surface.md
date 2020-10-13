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
- Surface Laptop Go
ms.custom:
- CI 121602
ms.reviewer: hachidan
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
ms.openlocfilehash: dee2a2962cf6b70a1bf11cf597b4d41f4b5568e4
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114571"
---
# 適用於 Surface 裝置的電源喚醒

當您不在辦公室時，可以關閉 Surface 裝置，或設定為睡眠模式，以節省電池使用時間。 若要改善這些裝置的可管理性，當電源電源開啟時，可讓相容的 Surface 裝置自動啟動。 若要設定喚醒功能，您可以使用 Surface Enterprise 管理模式 (SEMM) 透過 Surface UEFI 配置器或 UEFI 管理員來進行。

在下列裝置上可使用 [喚醒電源] 功能：

- Surface Book 3
- Surface Pro 7
- Surface 膝上型電腦3
- Surface 膝上型電腦前往
- Surface Pro X 


## 概述與先決條件

Surface UEFI 設定檔可讓您將個別的 UEFI 設定儲存在 Windows 安裝程式的 .msi 套件中，以發佈至目標裝置。 

> [!NOTE]
> 本文假設您知道如何使用 SEMM。 如需詳細資訊，請參閱 [ (SEMM) 檔的 Surface Enterprise 管理模式 ](surface-enterprise-management-mode.md) 。

## 啟用喚醒功能

1.  下載最新版本的 [SURFACE UEFI 配置](https://www.microsoft.com/download/confirmation.aspx?id=46703)器。
2.  以系統管理員身分登入您的 Surface 裝置，然後開啟 [ **SURFACE UEFI 配置**單元]，選取 [ **surface 裝置**]，然後選取 **[下一步]**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
3.  選取 [**開始**]，然後選取 [設定**套件**] 下的 [**建立**]。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
4.  選取 [ **憑證保護**]，然後新增您的憑證 .pfx 檔案。 
5. 輸入您的密碼，選取 **[下一步]**，視需要新增 **密碼保護**，然後選取 **[下一步]**。
6.  在 [ **選擇您要設定目標的表面類型** ] 頁面上，視需要選取您的目標裝置。 例如，選取 [ **Surface Pro 7**]。
7.  在 [ **高級功能** ] 頁面上，選取 [ **電源喚醒**]，將功能設定為 [ **開啟**]，然後選取 **[下一步]**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。"::: 
8.  在 [ **成功** ] 頁面上，選取 [ **結束**]。

    > [!NOTE]
    > 如果這是您第一次將設定提供給您的裝置，系統會提示您同時提供憑證指紋的最後兩個字元。 
9.  儲存 .msi 套件。 

## 套用 MSI 套件 

您可以使用軟體發佈工具（例如 Microsoft 端點設定管理員），將 MSI 套件套用到整個網路的裝置。 此套裝程式含在您的本機電腦上安裝套件的步驟。 

1.  在提升許可權的命令提示字元中，輸入 .msi 檔案的完整路徑，以執行 .msi 封裝。 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  在 [ **警告** ] 對話方塊中，視需要選取 **[確定] 或 [** 停用 BitLocker]。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
3.  在 [歡迎] 頁面上，選取 **[下一步]** 以執行套件，並套用新設定的 UEFI 設定。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="選取 [Surface 裝置]，然後選取 [下一步]。":::
4.  重新開機您的裝置。 

[電源開啟] 現已設定。 若要測試設定，請關閉您的裝置，中斷電源連接，然後重新連接電源。 裝置應該會自動啟動。 

## 參考

如需詳細資訊，請參閱下列文章。 

- [Surface 企業管理模式](surface-enterprise-management-mode.md)
- [在 Surface 裝置上喚醒局域網](wake-on-lan-for-surface-devices.md)

仍需要協助？ 移至 [Microsoft 社區](https://answers.microsoft.com/)。