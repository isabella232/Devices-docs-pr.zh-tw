---
title: 針對 Surface 雙核設定 Android 企業版工作設定檔
description: 本文說明如何在 Surface 雙核上設定工作設定檔。
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
ms.openlocfilehash: 393844a4e4f0f06f16d11d1313ec9aacfa109d57
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326139"
---
# 針對 Surface 雙核設定 Android 企業版工作設定檔

針對 BYOD 部署，工作設定檔會針對工作 app 與資料提供獨立的空間，讓組織完全控制其資料、應用程式及安全性原則，而不會防止員工將其裝置用於個人 app 和資料。

### 設定 Android 企業版工作設定檔

使用工作設定檔管理使用者擁有的 Android 裝置上的公司資料和應用程式。 根據預設，會啟用個人擁有的工作設定檔裝置，且不需要進一步的管理員設定。  

**若要啟用企業工作設定檔：**

- 在端點管理器中，選取 [**裝置**  >  **android**  >  **android 登記**]，然後選取 [**含工作設定檔的個人裝置**]。
<br><br>
 ![啟用企業作業設定檔](images/enroll-start.png)

 
**使用 Android 企業版工作設定檔登入 Surface 雙核**

1. 從 Google Play 商店安裝公司入口網站應用程式，並使用您的 Microsoft 公司或學校帳戶登入。<br><br>
![登入 Surface 雙核](images/duo-wp-1.png)
 
2. 在 [存取設定] 頁面上，選取 [ **開始**]。<br><br>
![首先](images/duo-wp-2.png)

3. 查看 [隱私權] 頁面上的資訊，然後選取 [ **繼續**]。<br><br>
 ![繼續](images/duo-wp-3.png)
<br><br>
 ![選取 [繼續]](images/duo-wp-4.png)
 
4. 當工作設定檔設定完成時，請選取 [ **繼續** ] 以啟動並註冊裝置。<br><br>
 ![選取 [繼續] 以啟動並註冊裝置](images/duo-wp-5.png)

5. 選取 **\[繼續\]**。<br><br>
 ![再次選取 [繼續]](images/duo-wp-6.png)

6. 當您啟動工作設定檔後，請選取 [ **繼續** ] 以更新裝置設定。 在這個範例中，工作設定檔會套用 MDM 設定，以要求較強的6位數的字母數位密碼。 <br><br>

     ![[數位元] 密碼範例](images/duo-wp-7.png)<br><br>
7. 選取 [ **解決** ] 以輸入所需的驗證，然後選取 [ **繼續** ] 以完成工作設定檔設定。 <br><br>
     ![選取 [繼續] 以完成設定](images/duo-wp-8.png)<br><br>
     ![完成設定](images/duo-wp-9.png)<br><br>

## 深入了解

- [設定 Android 企業作業設定檔的登記](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-enroll)

