---
title: 使用 SEMM 保護Surface Hub管理 2S
description: 深入瞭解使用 SEMM 保護 Surface Hub 2S。
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
ms.openlocfilehash: b22bfc39c07facb84ca57438ec16038492f85d15
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911038"
---
# <a name="secure-and-manage-surface-hub-2s-with-semm-and-uefi"></a>使用 SEMM 和 UEFI 保護及管理 Surface Hub 2S

在 Surface Hub 2S 中新增功能，您可以使用 SEMM 來管理裝置中的 UEFI 設定。
使用 Microsoft Surface UEFI Configurator 控制下列元件：

- 有線 LAN
- 相機
- 藍牙
- Wi-Fi
- 佔用感應器

使用 Microsoft Surface UEFI 設定器開啟或關閉下列 UEFI 設定：

- 開機

    - 適用於 PXE 開機 的 IPv6
    - 替代開機
    - 開機順序鎖定
    - USB 開機
- UEFI 首頁

    - 裝置
    - 開機
    - 日期/時間

## <a name="create-uefi-configuration-image"></a>建立 UEFI 組組圖像

與其他 Surface 裝置不同，您無法使用 MSI 檔案或 Win PE 影像將這些設定Surface Hub 2S。 您必須建立 USB 圖像，以載入至裝置。 若要建立 Surface Hub 2S UEFI 組組圖像，請從 Microsoft 下載中心的 Surface [Tools](https://www.microsoft.com/download/details.aspx?id=46703)頁面下載並安裝最新版本的 Microsoft Surface UEFI Configurationator。 有關使用 UEFI 和 SEMM 的資訊，請參閱[Microsoft Surface Enterprise管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。

## <a name="to-configure-uefi-on-surface-hub-2s"></a>若要在 2S Surface Hub UEFI

1. 啟動 UEFI Configurationator，並選取第一個畫面上的配置 **套件**。<br><br>
![* 啟動 UEFI Configurationator，然後選擇組組套件*。](images/sh2-uefi1.png) <br> <br>
2. 若要將憑證新加到您的套件中，您必須有以 .pfx 檔案格式使用私密金鑰的有效憑證，以簽署及保護套件。 選取 **+憑證保護。** <br>
![* 選取 + 憑證保護 *。](images/sh2-uefi2.png) <br><br>
3. 輸入憑證的私密金鑰密碼。<br>
![* 輸入憑證的私密金鑰密碼 *。](images/sh2-uefi3.png) <br><br>
4. 在導入私密金鑰之後，繼續建立套件。<br>
![* 繼續建立套件 *。](images/sh2-uefi4.png) <br><br>
5. 選擇**中樞**Surface Hub **2S**做為 UEFI 組組套件的目標。<br>
![* 選擇中樞Surface Hub 2S 做為 UEFI 組組套件 *的目標。](images/sh2-uefi5.png) <br><br>
6. 選擇您想要在 2S 上啟用或停用的元件Surface Hub設定。<br>
![* 選擇您想要啟用或停用的元件和設定 *。](images/sh2-uefi6.png) <br><br>
7. 使用 USB 選項匯出檔案。<br>
![* 使用 USB 選項匯出檔案 *。](images/sh2-uefi8.png) <br><br>
8. 插入並選擇要用於此套件的 USB 磁碟機。 USB 磁碟機會格式化，而您也會失去任何您擁有的資訊。<br>
![* 插入並選擇套件的 USB 磁碟機 *。](images/sh2-uefi9.png) <br><br>
9. 成功建立套件後，Configurator 會顯示憑證指紋的最後兩個字元。 當您將這些字元導入到 2S 的組Surface Hub字元。<br>
![* 成功組組套件 *。](images/sh2-uefi10.png) <br>

## <a name="to-boot-into-uefi"></a>若要啟動至 UEFI

關閉 2S Surface Hub 2S。 按住向上 **音量** 按鈕，然後按 **Power** 按鈕。 持續按住向上音量按鈕，直到 UEFI 功能表出現。
