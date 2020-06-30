---
title: 第一次安裝 Surface Hub 2 秒
description: 瞭解如何在第一次安裝 Surface Hub 2 秒時完成。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 07/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 47a393944c1b524931a6ac56962cc2cd60786007
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831789"
---
# 第一次安裝 Surface Hub 2 秒

當您第一次啟動 Surface Hub 2 秒時，裝置會自動進入 [第一次設定] 模式，引導您透過帳戶設定和相關設定。

## 設定 Surface Hub 2 秒帳戶

1. **設定您的地區設定。** 輸入地區、語言、鍵盤配置和時區資訊。 選取 **\[下一步\]**。

   ![* 設定您的地區設定 *](images/sh2-run1.png) <br>
1. **連線至無線網路。** 選擇您慣用的無線網路，然後選取 **[下一步]。**

- 如果使用乙太網纜線連線，則不會顯示此選項。
- 您無法在作用中將登入要求重新導向至提供者網站的熱點（固定入口網站）中連線至無線網路。

3. **輸入 [裝置帳戶資訊]。** 將 [ **domain\user** ] 用於內部部署和混合式環境，以及適用于線上環境的**使用者 \ @example .com** 。 選取 **[下一步]。**

   ![* 輸入裝置帳戶資訊 *](images/sh2-run2.png) <br>
1. **輸入其他資訊。** 如有需要，請提供您的 Exchange 伺服器位址，然後選取 **[下一步]。**

    ![* 輸入其他資訊;例如，Exchange 伺服器名稱 *](images/sh2-run3.png) <br>

1. **為此裝置命名。** 輸入您裝置的名稱，或使用根據您帳戶的顯示名稱和使用者主要名稱 [UPN] 所建議的名稱。 **選取 [下一步]**。

- **易記名稱**會顯示在 Surface Hub 2 的左下角，且會在投影到裝置時顯示。

- **裝置名稱**會識別附屬於 Active Directory 或 Azure Active directory 的裝置，以及在使用 Intune 註冊裝置時。

  ![* 將此裝置命名 *](images/sh2-run4.png) <br>
 
## 設定裝置系統管理員帳戶

您只能在第一次設定期間設定裝置管理員。 如需詳細資訊，請參閱[Surface Hub 2 的裝置從屬關係](https://docs.microsoft.com/surface-hub/surface-hub-2s-prepare-environment#device-affiliation)。

 在 [**針對此裝置設定管理員**] 視窗中，選取下列其中一個選項： Active Directory 網域服務、Azure Active Directory 或本機系統管理員。

   ![* 針對此裝置的設定管理員 *](images/sh2-run5.png) <br>

### Active Directory Domain Services

1. 輸入有許可權將裝置加入 Active Directory 的使用者認證。

    ![* 使用網域加入的設定管理員 *](images/sh2-run6.png) <br>

2. 選取包含允許登入 Surface Hub 2 的 [設定] 應用程式之成員的 Active Directory 安全性群組。

    ![* 輸入安全性群組 *](images/sh2-run7.png) <br>
1. 選取 **[完成]**。 裝置將會重新開機。

### Azure Active Directory

當您選擇將您的裝置與 Azure Active Directory 關聯時，裝置會立即重新開機並顯示下列頁面。 選取 **\[下一步\]**。

![* 如果您的組織使用的是 Microsoft Office 365 或其他商務服務，我們會將此裝置與您的組織 enrolll *](images/sh2-run8.png) <br>

1. 輸入**使用 Intune 方案 1**或更高版本的帳戶的電子郵件地址或 UPN，然後選取 **[下一步]。**

    ![* 輸入公司或學校帳戶 *](images/sh2-run9.png) <br>

2. 如果已重新導向，請使用貴組織的登入頁面進行驗證，並視需要提供額外的登入資訊。 裝置將會重新開機。

## 本機系統管理員帳戶

- 輸入您的本機系統管理員的使用者名稱和密碼。裝置將會重新開機。

     ![* 設定管理員帳戶 *](images/sh2-run10.png) <br>
 
## 使用預配套件

如果您在啟動 Surface Hub 2 秒後，在其中一個 USB 埠中插入一個含預配套件的 USB 拇指磁片磁碟機，則裝置會顯示下列頁面。

1. 輸入要求的設定，然後選取 [**設定**]。

    ![* 輸入套件的 [地區設定] *](images/sh2-run11.png) <br>

    ![* 從卸除式媒體提供此裝置 *](images/sh2-run12.png) <br>
2. 選擇您想要使用的預配套件。

   ![* 選擇要使用的 [配套件] *](images/sh2-run13.png) <br>

3. 如果您建立了多個裝置 CSV 檔案，您就可以選擇裝置設定。 如需詳細資訊，請參閱[建立 Surface Hub 2 的預配套件](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file)。


    ![* 從您的設定檔中選取裝置帳戶和易記名稱 *](images/sh2-run14.png) <br>

4. 依照指示完成第一次設定。
