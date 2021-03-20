---
title: Surface Hub 2S 第一次設定
description: 瞭解如何完成 Surface Hub 2S 第一次設定。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 03/03/2019
ms.localizationpriority: Medium
ms.openlocfilehash: 9cbce8bf0cc9c729af4cd052167fef016197274f
ms.sourcegitcommit: 8b35cdee6c638359403697711ee53d07cca6ee51
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/20/2021
ms.locfileid: "11442191"
---
# <a name="first-time-setup-for-surface-hub-2s"></a>Surface Hub 2S 第一次設定

當您第一次啟動 Surface Hub 2S 時，裝置會自動進入第一次設定模式，以引導您完成帳戶設定和相關設定。

## <a name="configuring-surface-hub-2s-account"></a>正在配置 Surface Hub 2S 帳戶

1. **設定您的地區設定。** 輸入地區、語言、鍵盤配置和時區資訊。 選取 **\[下一步\]**。

   ![* 設定您的地區設定 *](images/sh2-run1.png)

1. **連接到無線網路。** 選擇您偏好的無線網路，然後選取下 **一步。**

   - 如果使用乙太網路纜線連接，則不會顯示此選項。

   - 您無法在將登錄要求重新導向到提供者 (入口網站或) 中，連接到無線網路。

3. **輸入裝置帳戶資訊。** 針對 **內部部署和** 混合式環境使用網域\user，以及適用于線上 example.com 使用者 **\@example.com** 使用者。 選取 **下一步。**

   ![* 輸入裝置帳戶資訊 *](images/sh2-run2.png)

1. **輸入其他資訊。** 如果要求，請提供您的 Exchange 伺服器位址，然後選取下 **一步。**

   ![* 輸入詳細資訊;例如 Exchange 伺服器名稱*](images/sh2-run3.png)

1. **為此裝置命名。** 輸入您裝置的名稱，或根據帳戶的顯示名稱和使用者原則名稱 [UPN] 使用建議的名稱。 **選取 下一個**。

   - Surface **Hub** 2S 左下角會顯示好用名稱，且在專案到裝置時會顯示。

   - 裝置 **名稱** 會識別與 Active Directory 或 Azure Active Directory 有關系，以及使用 Intune 註冊裝置時，裝置。

   ![* 命名此裝置*](images/sh2-run4.png)
 

## <a name="configuring-device-admin-accounts"></a>正在配置裝置系統管理員帳戶

您只能在第一次設定期間設定裝置系統管理員。 詳細資訊，請參閱 Surface [Hub 2S 裝置關聯。](https://docs.microsoft.com/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)

在此裝置 **視窗** 的安裝程式系統管理員中，選取下列其中一個選項：Active Directory Domain Services、Azure Active Directory 或 Local admin。

![* 此裝置設定系統管理員 *](images/sh2-run5.png)

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. 輸入具有將裝置加入 Active Directory 之許可權之使用者的認證。

    ![* 使用網域加入設定系統管理員 *](images/sh2-run6.png)

2. 選取包含允許成員登入 Surface Hub 2S 上的設定 App 的 Active Directory 安全性群組。

   ![* 輸入安全性群組 *](images/sh2-run7.png)

1. 選取 **完成**。 裝置會重新啟動。

### <a name="azure-active-directory"></a>Azure Active Directory

選擇將裝置與 Azure Active Directory 聯屬時，裝置會立即重新開機並顯示下列頁面。

![* 如果貴組織使用 Microsoft 的 Office 365 或其他商務服務，我們會向貴組織註冊此裝置*](images/sh2-run8.png)

1. 選取 **\[下一步\]**。

1. 輸入具有 Intune 方案 **1** 或更大的帳戶的電子郵件地址或 UPN，然後選取下 **一步。**

   ![* 輸入公司或學校帳戶*](images/sh2-run9.png)

1. 如果重新導向，請使用貴組織的登入頁面進行驗證，並提供額外的登入資訊 。如果有要求，請提供其他登入資訊。 裝置會重新啟動。

## <a name="local-administrator-account"></a>本地系統管理員帳戶

- 輸入您的當地系統管理員的使用者名稱和密碼。裝置將會重新開機。

  ![* 設定系統管理員帳戶*](images/sh2-run10.png)
 
## <a name="using-provisioning-packages"></a>使用資源調配套件

如果您在啟動 Surface Hub 2S 時，將包含部署套件的 USB 拇指磁碟機插入其中一個 USB 埠，裝置會顯示下列頁面。

1. 輸入要求設定，然後選取 **設定**。

   ![* 輸入地區設定以設定套件*](images/sh2-run11.png)

   ![* 從可移除媒體提供此裝置*](images/sh2-run12.png)

2. 選擇您喜歡的部署套件。

   ![* 選擇要使用的部署套件*](images/sh2-run13.png)

3. 如果您建立了多個裝置 CSV 檔案，您就能選擇裝置組組。 詳細資訊，請參閱建立 [Surface Hub 2S 的部署套件](https://docs.microsoft.com/surface-hub/surface-hub-2s-deploy#provisioning-multiple-devices-csv-file)。

   ![* 從組組檔案中選取裝置帳戶和好用名稱*](images/sh2-run14.png)

4. 按照指示完成第一次設定。
