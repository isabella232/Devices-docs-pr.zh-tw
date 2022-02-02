---
title: 適用於 Surface 裝置的電源喚醒
ms.author: greglin
author: mccoybot
audience: ITPro
search.appverid:
- SPO160
- MET150
ms.custom:
- CI 121602
ms.reviewer: hachidan
description: 說明如何啟用和停用 Surface 裝置 Power 上的喚醒。
keywords: 更新、部署、驅動程式、wol、wake-on-lan
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
manager: laurawi
ms.audience: itpro
ms.date: 12/08/2021
ms.openlocfilehash: e8e4ddbd559fc6aea2d04e61208b911ebef3ec22
ms.sourcegitcommit: e7d95d583429169eb65aae9034eab2347b1f04a0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/02/2022
ms.locfileid: "12338396"
---
# <a name="wake-on-power-for-surface-devices"></a>適用於 Surface 裝置的電源喚醒

Surface 裝置可在您離開桌面時關閉電源，或設定為睡眠模式以節省電池使用時間。 若要改善這些裝置可管理性，Power 喚醒可讓相容的 Surface 裝置在重新連接電源時自動啟動。 若要設定 Power 喚醒，您可以使用 Surface Enterprise管理模式 (SEMM) Surface UEFI 設定器或 UEFI Manager。

下列裝置提供 Power 喚醒功能：

- Surface Pro只 (8 個商業 SKUS) 
- Surface Pro 7+ (商務 SKUs) 
- Surface Pro X (所有 SKUs) 
- Surface Pro 7 (所有 SKUs) 
- Surface Go 3 (商務 SKUs) 
- Surface Laptop Studio (只供應商業 SKUs) 
- Surface Book 3 (所有 SKUs) 
- Surface Laptop只 (4 個商業 SKUS) 
- Surface Laptop 3 (SKUs) 
- Surface Laptop前往 (所有 SKUs) 


>[!TIP]
> 商業 SKUs (或 Surface 商務版) Windows 10 專業版/Enterprise 或 Windows 11 專業版/Enterprise;消費者 SKUs Windows 10/Windows 11 家用版。 若要深入瞭解，請參閱 [查看系統資訊](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00)。 

## <a name="overview-and-prerequisites"></a>概觀與先決條件

Surface UEFI 設定器可讓您將個別的 UEFI 設定儲存在 Windows 安裝程式.msi套件中，以發佈至目標裝置。 

> [!NOTE]
> 本文假設您知道如何使用 SEMM。 詳細資訊請參閱[SURFACE Enterprise管理模式 (SEMM) ](surface-enterprise-management-mode.md)檔。

## <a name="to-enable-wake-on-power"></a>若要啟用 Power 喚醒

1.  下載最新版本 [的 Surface UEFI Configurator](https://www.microsoft.com/download/confirmation.aspx?id=46703)。
2.  以系統管理員的名號登錄 Surface 裝置、開啟 **Surface UEFI 配置**器、選取 **Surface Devices**，然後選取下一 **步**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-1.png" alt-text="選取 Surface Devices，然後選取下一步。":::
3.  選取**開始**，然後在組**組套件****下選取建立**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-2.png" alt-text="選取建立組組套件。":::
4.  選取 **憑證保護**，然後新增您的憑證 .pfx 檔案。 
5. 輸入您的密碼 **，選取下**一步 **，並在適當**時新增密碼保護，然後選取下 **一步**。
6.  在選擇 **您想要的目標 Surface** 類型頁面上，選取您的目標裝置。 例如，選取 Surface Pro **7**。
7.  在進 **一步功能** 頁面上，選取 **Power 喚醒**，將功能設定為 **On**，然後選取下 **一步**。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-3.png" alt-text="選取在 Power 上喚醒，然後設定為 On。"::: 
8.  在成功**頁面上****，選取結束**。

    > [!NOTE]
    > 如果這是您第一次為裝置提供設定，系統會提示您同時提供憑證指紋的最後兩個字元。 
9.  儲存.msi套件。 

## <a name="apply-the-msi-package"></a>套用 MSI 套件 

您可以使用軟體發佈工具 ，例如軟體發佈工具，將 MSI 套件套用至Microsoft Endpoint Configuration Manager。 此套裝程式含將套件安裝在您本地電腦上的步驟。 

1.  在提升的命令提示符中，輸入.msi的完整路徑，以執行.msi套件。 

    ```
    C:\SEMM\wake-on-power.msi 
    ```

2.  在 [ **警告」** 對話方塊中，選取 **[確定** 或停用 BitLocker， 適當的話。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-4.png" alt-text="請選取確定或停用 BitLocker 。":::
3.  在歡迎頁面上 **，選取下** 一步以執行套件並套用新設定 UEFI 設定。

    :::image type="content" source="images/wake-on-power-for-surface/wake-on-power-for-surface-5.png" alt-text="在歡迎頁面，選取下一步。":::
4.  重新啟動您的裝置。 

現在已針對 Power 喚醒進行配置。 若要測試設定，請關閉裝置、中斷電源連接，然後重新連接電源。 裝置應該會自動啟動。 

## <a name="references"></a>參考

詳細資訊，請參閱下列文章。 

- [Surface 企業管理模式](surface-enterprise-management-mode.md)
- [在 Surface 裝置上的 LAN 喚醒](wake-on-lan-for-surface-devices.md)

仍需要協助？ 前往[Microsoft Community](https://answers.microsoft.com/)。