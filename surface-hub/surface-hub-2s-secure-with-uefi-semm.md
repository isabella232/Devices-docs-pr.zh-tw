---
title: 使用 SEMM 來保護及管理 Surface Hub 的2秒
description: 深入瞭解使用 SEMM 保護 Surface Hub 的詳細資料。
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
ms.openlocfilehash: 03ce1dfa48ade8aade545c63818ca5ae8947e6b7
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831442"
---
# 使用 SEMM 和 UEFI 保護及管理 Surface Hub 2S

在 Surface Hub 2 的新功能中，您可以使用 SEMM 來管理裝置的 UEFI 設定。
使用 Microsoft Surface UEFI 配置器來控制下列元件：

- 有線 LAN
- 相機
- 藍牙
- Wi-Fi
- 佔用感應器

使用 Microsoft Surface UEFI 配置器來開啟或關閉下列 UEFI 設定：

- 開機

    - 適用於 PXE 開機 的 IPv6
    - 替代開機
    - 開機順序鎖定
    - USB 開機
- UEFI 首頁

    - 裝置
    - 開機
    - 日期/時間

##  <a name="create-uefi-configuration-image"></a>建立 UEFI 配置圖像

與其他 Surface 裝置不同，您無法使用 MSI 檔案或 Win PE 映射，在 Surface Hub 2 秒上套用這些設定。 相反地，您需要建立要載入到裝置的 USB 影像。 若要建立 Surface Hub 2 的 UEFI 設定影像，請從 Microsoft 下載中心的 [ [Surface Tools for IT](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面下載並安裝最新版本的 MICROSOFT Surface UEFI 設定檔。 如需有關使用 UEFI 與 SEMM 的詳細資訊，請參閱[Microsoft Surface Enterprise 管理模式](https://docs.microsoft.com/surface/surface-enterprise-management-mode)。

##  <a name="to-configure-uefi-on-surface-hub-2s"></a>在 Surface Hub 2 秒上設定 UEFI

1. 啟動 UEFI 配置器，然後在第一個畫面上，選擇 [設定**套件**]。<br><br>
![* 啟動 UEFI 配置器並選擇 [設定套件] *](images/sh2-uefi1.png) <br> <br>
2. 若要將憑證新增到您的套件，您必須有有效的憑證，且私密金鑰是 .pfx 檔案格式，才能簽署及保護套件。 選取 [ **+ 憑證保護]。** <br>
![* 選取 + 憑證保護 *](images/sh2-uefi2.png) <br><br>
3. 輸入證書的私密金鑰密碼。<br>
![* 輸入證書的私人金鑰密碼 *](images/sh2-uefi3.png) <br><br>
4. 匯入私人金鑰之後，繼續建立套件。<br>
![* 繼續建立套件 *](images/sh2-uefi4.png) <br><br>
5. 選擇 [**中樞**] 和 [ **Surface hub** 2] 作為 UEFI 配置套件的目標。<br>
![* 選擇 [中樞] 和 [Surface Hub 2] 作為 UEFI 配置套件的目標 *](images/sh2-uefi5.png) <br><br>
6. 選擇您想要在 Surface Hub 2 秒啟動或停用的元件和設定。<br>
![* 選擇您想要啟動或停用的元件和設定 *](images/sh2-uefi6.png) <br><br>
7. 使用 USB 選項匯出檔案。<br>
![* 使用 USB 選項匯出檔案 *](images/sh2-uefi8.png) <br><br>
8. 插入並選擇您想要用於此套件的 USB 磁片磁碟機。 USB 磁片磁碟機將會格式化，而且您會遺失任何您在其上的資訊。<br>
![* 插入並選擇您套件的 USB 磁片磁碟機 *](images/sh2-uefi9.png) <br><br>
9. 成功建立套件後，配置器就會顯示憑證指紋的最後兩個字元。 當您匯入到 [Surface Hub 2] 的配置時，您需要這些字元。<br>
![* 套件的成功設定 *](images/sh2-uefi10.png) <br>

##  <a name="to-boot-into-uefi"></a>若要引導至 UEFI

關閉 Surface Hub 秒。 按住**音量**按鈕，然後按下 [**電源**] 按鈕。 一直按住音量按鈕，直到 UEFI 功能表出現為止。
