---
title: 系統管理員群組管理 (Surface Hub)
description: 您可以在裝置上開啟 \[設定\] 應用程式，個別設定每一個 Microsoft Surface Hub。
ms.assetid: FA67209E-B355-4333-B903-482C4A3BDCCE
ms.reviewer: ''
manager: laurawi
keywords: 系統管理員群組管理, \[設定\] 應用程式, 設定 Surface Hub
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/27/2017
ms.localizationpriority: medium
ms.openlocfilehash: 716e409bf988e7178ec45e21165aad070d027eee
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831898"
---
# 系統管理員群組管理 (Surface Hub)


在個別裝置上使用 \[設定\] 應用程式，可各自設定其上的 Surface Hub。 為防止未經授權的使用者變更設定，\[設定\] 應用程式要求您必須提供系統管理員認證才能開啟應用程式。


## 系統管理員群組管理

您可以使用下列三種方式的其中一種來設定裝置的系統管理員帳戶：

-   建立本機系統管理員帳戶
-   將裝置加入 Active Directory (AD) 網域
-   Azure Active Directory (Azure AD) 加入裝置


### 建立本機系統管理員帳戶

若要建立本機系統管理員，請[在初次執行期間選擇使用本機系統管理員](first-run-program-surface-hub.md#use-a-local-admin)。 這將在 Surface Hub 上使用您選擇的使用者名稱與密碼，來建立單一本機系統管理員帳戶。 使用這些認證來開啟 \[設定\] 應用程式。

請注意，所有目錄服務都不會備份本機系統管理員帳戶資訊。 如果裝置沒有 Active Directory (AD) 或 Azure Active Directory (Azure AD) 的存取權，建議您只選擇本機系統管理員。 如果您決定變更本機系統管理員的密碼，可以在 \[設定\] 中變更。 不過，如果您想要將使用本機系統管理員變更為使用來自您網域或 Azure AD 租用戶的群組，則您需要[重設裝置](device-reset-surface-hub.md)，然後再次進行初次程式。

### 將裝置加入 Active Directory (AD) 網域

您可以將 Surface Hub 加入您的 AD 網域，以允許來自指定安全性群組的使用者進行設定。 在初次執行時，請選擇使用 [Active Directory Domain Services](first-run-program-surface-hub.md#use-active-directory-domain-services)。 您將需要提供能夠加入您選擇之網域的認證，以及現有安全性群組的名稱。 所有屬於該安全性群組成員的使用者都可以輸入他們的認證，並將 \[設定\] 解除鎖定。

#### 當您將 Surface Hub 加入網域時會發生什麼事？
Surface Hub 會透過加入網域來：
- 將系統管理員權限授與 AD 中指定安全性群組的成員。
- 透過將裝置的 BitLocker 修復金鑰儲存在 AD 中的電腦物件底下來備份它。 請參閱[儲存您的 BitLocker 金鑰](save-bitlocker-key-surface-hub.md)來取得詳細資料。
- 透過網域控制站同步處理系統時鐘以進行加密通訊

Surface Hub 不支援從網域控制站套用群組原則或憑證。

> [!NOTE]
> 如果您的 Surface Hub 失去網域的信任 (例如，如果您在 Surface Hub 加入網域之後，將它從網域移除)，您將無法在裝置中進行驗證並開啟 \[設定\]。 如果您決定移除 Surface Hub 與您網域的信任關係，請先[重設裝置](device-reset-surface-hub.md)。


### Azure Active Directory (Azure AD) 加入裝置

您可以將 Surface Hub 加入 Azure AD，以允許來自您 Azure AD 租用戶的 IT 專業人員進行設定。 在初次執行時，請選擇使用 [Microsoft Azure Active Directory](first-run-program-surface-hub.md#use-microsoft-azure-active-directory)。 您需要提供能夠加入您選擇之 Azure AD 租用戶的認證。 成功加入 Azure AD 之後，適當的人員將會在裝置上獲得系統管理員權限。

根據預設，所有的**全域系統管理員**都會在加入 Azure AD 的 Surface Hub 上獲得系統管理員權限。 透過 **Azure AD Premium** 或 **Enterprise Mobility Suite (EMS)**，您將可以新增額外的系統管理員：
1.  在 [Azure 傳統入口網站](https://manage.windowsazure.com/)中，按一下 **Active Directory**，然後按一下您組織目錄的名稱。
2.  在 **\[設定\]** 頁面上，於 **\[裝置\]**  >  **\[加入 Azure AD 之裝置的其他系統管理員\]** 底下，按一下 **\[已選取\]**。
3.  按一下 **\[新增\]**，然後選取您想要在 Surface Hub 和其他加入 Azure AD 的裝置上新增為系統管理員的使用者。
4.  當您完成之後，請按一下核取記號以儲存變更。

#### 當您將 Surface Hub 加入 Azure AD 時會發生什麼事？
Surface Hub 會透過加入 Azure AD 來：
- 將系統管理員權限授與 Azure AD 租用戶中適當的使用者。
- 透過將裝置的 BitLocker 修復金鑰儲存在用來將裝置加入 Azure AD 的帳戶底下來備份它。 請參閱[儲存您的 BitLocker 金鑰](save-bitlocker-key-surface-hub.md)來取得詳細資料。

### 透過 Azure Active Directory join 自動登記

Surface Hub 現在支援透過將裝置加入 Azure Active Directory 來自動註冊 Intune。 

如需詳細資訊，請參閱[啟用 Windows 10 自動註冊](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)。

### 我應該選擇哪一個？

如果您的組織使用 AD 或 Azure AD，我們建議您選擇加入網域或加入 Azure AD (主要是基於安全性考量)。 使用者將能夠使用自己的認證進行驗證並解除鎖定 \[設定\]，而且可以移入或移出與您的網域相關聯的安全性群組。

| 選項                                            | 需求                            | 哪些認證可以用於存取 \[設定\] 應用程式？  |
|---------------------------------------------------|-----------------------------------------|-------|
| 建立本機系統管理員帳戶                      | 無                                    | 於初次執行時指定的使用者名稱和密碼 |
| 加入 Active Directory (AD) 網域              | 您的組織使用 AD               | 來自您網域中指定安全性群組的任何 AD 使用者 |
| Azure Active Directory (Azure AD) 加入裝置 | 您的組織使用 Azure AD Basic   | 僅限全域系統管理員 |
| &nbsp;                                            | 您的組織使用 Azure AD Premium 或 Enterprise Mobility Suite (EMS) | 全域系統管理員及額外的系統管理員 |


