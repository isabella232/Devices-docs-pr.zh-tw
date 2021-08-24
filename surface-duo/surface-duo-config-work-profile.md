---
title: 針對 Surface Duo 設定 Android 企業版工作設定檔
description: 本文將說明如何在 Surface Duo 上設定工作設定檔。
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/25/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 380c5fc625983119a516f5d0e2294af70e0dbd29
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911198"
---
# <a name="configure-android-enterprise-work-profile-for-surface-duo"></a>針對 Surface Duo 設定 Android 企業版工作設定檔

針對 BYOD 部署，工作設定檔為工作應用程式和資料提供 Duo 上的個別空間，讓組織能夠完全控制其資料、應用程式和安全性原則，而不會禁止員工將裝置用於個人應用程式和資料。

### <a name="set-up-android-enterprise-work-profile"></a>設定 Android Enterprise工作設定檔

使用公司設定檔在使用者擁有的 Android 裝置上管理公司資料與應用程式。 根據預設，個人擁有的工作設定檔裝置會啟用註冊，而且不需要進一步系統管理員組組。  

**若要啟用Enterprise設定檔：**

- 在 端點管理員中，選取**裝置**  >  **Android**  >  **註冊**，然後選取具有工作**設定檔的個人裝置**。
<br><br>
 ![啟用Enterprise設定檔。](images/enroll-start.png)

 
**使用 Android 和工作設定檔Enterprise Surface Duo**

1. 從 Google Play 公司入口網站安裝應用程式，然後使用 Microsoft 公司或學校帳戶進行登錄。<br><br>
![請登錄 Surface Duo。](images/duo-wp-1.png)
 
2. 在 Access 安裝程式頁面上， **選取**開始 。<br><br>
![開始。](images/duo-wp-2.png)

3. 查看隱私權頁面上的資訊， **然後選取**繼續 。<br><br>
 ![繼續。](images/duo-wp-3.png)
<br><br>
 ![選取繼續。](images/duo-wp-4.png)
 
4. 工作設定檔設定完成後， **選取繼續啟用** 並註冊裝置。<br><br>
 ![選取 繼續啟用並註冊裝置。](images/duo-wp-5.png)

5. 選取 **\[繼續\]**。<br><br>
 ![再次選取繼續。](images/duo-wp-6.png)

6. 當您啟用工作設定檔時，請 **選取繼續更新** 裝置設定。 在此範例中，工作設定檔會採用 MDM 設定，要求使用較強的 6 位數數位密碼。 <br><br>

     ![範例數位密碼。](images/duo-wp-7.png)<br><br>
7. 選取 **解決** 以輸入必要的驗證， **然後選取** 繼續完成工作設定檔設定。 <br><br>
     ![選取繼續完成設定。](images/duo-wp-8.png)<br><br>
     ![完成設定。](images/duo-wp-9.png)<br><br>

## <a name="learn-more"></a>深入了解

- [設定 Android Enterprise工作設定檔裝置](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

