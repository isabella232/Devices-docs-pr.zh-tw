---
title: Surface Duo 管理概觀
description: 本文重點說明在商業環境中管理 Surface 雙核的選項。
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/23/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 19ef3f5d20b22997aa339a462a34b84da27fb922
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326141"
---
# Surface Duo 管理概觀

商業客戶可以使用任何一種企業行動裝置管理 (EMM) 解決方案來管理 Surface 雙核處理器技術，每個方案都提供一致的一組雲端、裝置管理功能，無論是管理員工或公司擁有的裝置。

您可以透過使用整合式主機的 [MICROSOFT EMM](https://androidenterprisepartners.withgoogle.com/provider/#!/75) 來管理雙核管理雙核--Microsoft 端點管理員-以及 microsoft Intune 等可擴展元件。 或者，您也可以在 Google 的 Android 生態系統中使用任何 EMM 提供者。 在某些情況下，協力廠商 EMM 解決方案會提供額外的支援，以符合可能會因您的環境而有所説明的特定案例。

 若要比較 EMM 解決方案，請參閱 [Android 企業版解決方案目錄](https://androidenterprisepartners.withgoogle.com/emm/)。
使用 Intune 的端點管理員，您可以使用最新的行動裝置管理原則以及較舊的技術（例如 Exchange ActiveSync）來管理雙核。 如果您已使用 Exchange ActiveSync 設定來管理行動裝置，您可以使用電子郵件裝置-設定設定檔，將這些設定套用到使用 Intune 的雙核裝置。  如需詳細資訊，請參閱 [使用 Intune 將電子郵件設定新增至裝置](https://docs.microsoft.com/mem/intune/configuration/email-settings-configure)。

在 Intune 中管理裝置的主要方式，設定檔提供預設設定，您可以自訂這些設定，以符合貴組織的需求。 

## 管理個人擁有的 Surface 雙核裝置
| 解決方案                                          | 功能                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        | 深入了解                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 不含裝置註冊的 App 保護原則 | 可讓您在應用程式中管理及保護貴組織的資料。<br>部署應用程式保護原則，即精簡管理解決方案，不需要裝置註冊。<br>您現在可以使用應用程式保護原則（包括 Adobe Acrobat、[立即服務] 和 [縮放] 等 Microsoft Office 和協力廠商應用程式）來管理數量不斷增加的應用程式。 如需完整清單，請參閱 [Microsoft Intune 受保護的 app](https://docs.microsoft.com/mem/intune/apps/apps-supported-intune-apps)。 | - [App 保護原則概述](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)<br>- [Microsoft Intune 中的 Android 應用程式保護原則設定](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)。<br>- [使用 Intune App 換行工具為 app 保護原則準備 Android 應用](https://docs.microsoft.com/mem/intune/developer/app-wrapper-prepare-android)程式。 |
| Android 企業版工作設定檔                   | 針對 BYOD 部署，工作設定檔會針對工作 app 與資料提供獨立的空間，讓組織完全控制其資料、應用程式及安全性原則，而不限制使用者使用其裝置進行個人 app 與資料。                                                                                                                                                                                                                                                  | - [針對 Surface 雙核設定 Android 企業版工作設定檔](surface-duo-config-work-profile.md)。                                                                                                                                                                                                                                                                                                               |


## 管理公司擁有的 Surface 雙核裝置

| 解決方案                                  | 說明                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     | 深入了解                                                                                                                                                                                                                                                                                                      |
| ----------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 含工作設定檔的公司擁有的裝置 | 針對想要在公司擁有的單一使用者裝置上，針對他們提供的工作提供個人用途的組織。 它的設計目的是讓組織比使用工作設定檔進行管理更精確，但不想要使用完整的裝置管理或專用裝置管理完全鎖定裝置。<br>受 Android 作業系統隔離的工作和個人檔案 app 資料，但與 Android 企業版工作設定檔不同，因為提供管理員更多裝置層級控制。<br>IT 管理員可以在工作設定檔中查看、控制及設定公司帳戶、應用程式及資料，而最終使用者保證系統管理員無法看到個人設定檔中的資料和應用程式。 | - [Intune 宣佈使用工作設定檔的 Android 企業公司擁有的公用預覽版](https://techcommunity.microsoft.com/t5/intune-customer-success/intune-announcing-public-preview-for-android-enterprise/ba-p/1524325)                                                                    |
| Android 企業完全管理          | 針對與單一使用者相關聯的公司擁有的裝置，提供全面的裝置和 app 管理功能，且專供使用且不供個人使用。<br> <br>完整的裝置管理可提供對裝置資料和安全性的完全控制，以及對 Android 全套 app 管理功能的存取權。 例如：<br><br>-您可以設定裝置上的最小密碼需求<br>-遠端擦除並鎖定裝置<br>-將預設回應設定為應用程式許可權要求。<br>-使用 Microsoft 啟動器自訂最終使用者體驗<br><br>您也可以完全控制裝置上的應用程式，包括遠端安裝及移除應用程式的功能。                                 | - [設定 Android 企業完整管理裝置的 Intune 登記](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-enroll)。 |
| 專用裝置管理               | 此企業部署案例針對部署到特定使用案例的裝置，例如物流、運輸和工廠地面。 將它用於已鎖定的體驗，您需要將使用限制在一或兩個 app 中，並禁止使用者變更任何設定。                                                                                                                                                                                                                                                                                                                                                                                                                                                           | - [設定 Android 企業專用裝置的 Intune 登記](https://docs.microsoft.com/mem/intune/enrollment/android-kiosk-enroll)                                                                                                                                                               |

 
## 深入了解
- [Ignite 會話：使用企業中的 Surface 雙核部署、管理及啟用生產力](https://youtu.be/DOsBMNFmdfw)
- [使用 Microsoft Intune 管理裝置](https://docs.microsoft.com/mem/intune/remote-actions/device-management)
- [Intune 部署規劃、設計及實施指南](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide)
- [使用 Intune 註冊 Android 裝置](https://docs.microsoft.com/mem/intune/enrollment/android-enroll)
