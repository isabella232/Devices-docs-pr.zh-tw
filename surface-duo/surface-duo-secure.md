---
title: Surface Duo 安全性概觀
description: 本文強調 Surface Duo 如何在行動裝置上透過 Android OS 和 Microsoft 工程版 UEFI 提供企業級安全性。
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 677839038d8990aa7cb88800dabd51ace565e472
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449156"
---
# <a name="surface-duo-security-overview"></a>Surface Duo 安全性概觀

Surface Duo 的每一層都有內建保護，具有深度整合的硬體、固件和軟體，可保護您的裝置、身分及資料。 Surface Duo 是 Android 10 裝置，在作業系統層級和 Google 服務層使用 Android 安全性功能。 Android 作業系統利用傳統的作業系統安全性控制項來保護使用者資料和系統資源、保護裝置完整性，防範惡意程式碼，並提供應用程式隔離。 此外，Google 提供分層在作業系統上方的各種服務，與 Android OS 安全性結合時，可協助持續保護 Android 使用者。

- **自訂工程 UEFI。** Android 裝置中 Surface Duo 的獨特功能是 Microsoft 自訂設計的統一可擴展 (UEFI) ，可完全控制固件元件。 Microsoft 在Enterprise撰寫或審查每一行的固件程式碼，為 Surface Duo 提供高等級的安全性，讓 Microsoft 能直接且敏捷地回應潛在的固件威脅，並降低供應鏈安全性風險。
- **已驗證啟動。** 從硬體層級開始，從登錄開始，驗證啟動會盡力確保執行的代碼僅來自信任的來源。 它會建立完整的信任鏈 ，從受硬體保護的根信任目錄到開機載入程式、開機磁碟分割和其他已驗證的分區。 當 Surface Duo 啟動時，每個階段會先驗證下一階段的完整性與真實性，再進行交還執行。
- **App 分隔。** 應用程式沙箱功能會隔離並保護 Android 應用程式，防止惡意應用程式存取私人資訊。 強制且一直使用加密和金鑰處理功能可協助保護傳輸中和靜態的資料 ，即使裝置落入錯誤之手也一樣。 加密受到 Keystore 金鑰的保護，金鑰會儲存在容器內，因此較難從裝置中解壓縮。
- **Google Play 保護。** 在軟體層上，Surface Duo 使用 Google Play 保護威脅偵測功能，可掃描所有應用程式，包括來自 Google Play 的公用應用程式、由 Microsoft 和電信公司更新的系統應用程式，以及側載應用程式。
- **Microsoft Defender ATP。** 現在，從 Intune 管理的 Android 裝置可以使用適用于視窗 10 的企業級防毒軟體和惡意程式碼保護軟體。 若要深入瞭解，請參閱 [Android 版 Microsoft Defender ATP](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-android)。

## <a name="mobile-device-management-security"></a>行動裝置管理安全性

Surface Duo 在公司環境中使用 Enterprise 行動管理 (EMM) 解決方案，提供一組一致的保護工具、技術和最佳做法，可根據您的組織與合規性需求量身打造。 各種管理 API 為 IT 部門提供工具，協助防止資料外泄，並在各種情況下強制執行合規性。 多設定檔支援與裝置管理選項可讓工作與個人資料分開，協助確保公司資料安全。

MDM 安全性建立在一組擴充的組組設定技術上，可讓使用者在外保持生產力，同時保護重要的公司知識產權。 這包括應用程式保護政策、裝置限制政策，以及相關技術，可根據您的環境達成特定目標 ，無論是提供餐廳外賣訂單、管理牙科診所的 IT 服務或處理機密的國安資訊。

例如，您可以要求使用者輸入 6 位數的 Alphanumeric pin，以及雙因素驗證，以強化裝置驗證。 您可能會想要限制使用者可以註冊的裝置，協助您遵守授許可權制，或避免授與「越權」電話或其他不受支援裝置類型的存取權。 Intune 和其他 EMM 允許組織根據需求管理裝置。

## <a name="app-protection-policies"></a>應用程式保護政策

App 保護原則 (APP) 是可確保組織資料保持安全或包含在受管理應用程式中的規則。 原則可以是當使用者嘗試存取或移動「公司」資料時所強制執行的規則，或是當使用者在 App 內時禁止或監視的一組動作。 受管理應用程式是一種應用程式，其應用程式保護原則已適用于它，而且可以由 Intune 管理。

應用程式保護政策允許您管理及保護貴組織在應用程式中的資料。 許多生產力應用程式 ，例如 Microsoft Office應用程式，都可以由 Intune MAM 管理。 請參閱可公開Microsoft Intune[應用程式](/mem/intune/apps/apps-supported-intune-apps)的正式清單。

## <a name="security-considerations-for-managing-surface-duo"></a>管理 Surface Duo 的安全性考慮

行動裝置管理解決方案中可用的策略設定數量日增，可讓組織調整保護等級，以滿足其特定需求。 為了協助組織排定 Surface Duo (或其他 Android 裝置) 的安全性設定優先順序，Intune 已推出其[Android Enterprise](/mem/intune/enrollment/android-configuration-framework)安全性組組架構，組織成多個不同的設定案例，提供工作設定檔和完全管理案例的指引。

| 安全性層級                                                                                                       | 已鎖定目標                                                                                                                                                                      | 摘要                                                                                                                                                                                     | 設定資訊                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 工作設定檔基本安全性 - 第 1 層                                                                                | 可存取公司或學校資料的個人裝置。                                                                                                                             | 介紹密碼需求、分隔工作與個人資料，並驗證 Android 裝置認證。                                                                               | [工作設定檔層級 1 設定](/mem/intune/enrollment/android-work-profile-security-settings) |
| 工作設定檔高安全性 - 第 3 層<br> (由於架構慣例，這是第 1.) 層以上的下一層) <br>  | 獨一無二的高風險使用者或群組所使用的裝置。 例如，處理高度機密資料的使用者在未經授權的情況下，會造成大量材料遺失。 | 推出行動威脅防護或 Microsoft Defender ATP，將 Android 的最低版本設定為 8.0，制定更強大的密碼原則，進一步限制工作和個人分隔。 | [工作設定檔層級 3 設定](/mem/intune/enrollment/android-work-profile-security-settings#work-profile-high-security)                                                                                         |
| 完全管理的基本安全性 -第 1 層                                                                                | 企業裝置的最低安全性組組，適用于存取公司或學校資料的大多數行動使用者。                                                          | 引入密碼需求、將 Android 版本的最低版本設定為 8.0，以及制定特定裝置限制。                                                                          | [完全管理的層級 1 設定](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-basic-security)                                                                                     |
| 完全管理的增強安全性等級 2                                                                              | 使用者存取機密或機密資訊的裝置。                                                                                                                | 制定更強大的密碼政策，並停用使用者/帳戶功能。                                                                                                                   | [完全管理第 2 層設定](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-enhanced-security)                                                                                   |
| 完全管理的高安全性等級 3                                                                                  | 獨一無二的高風險使用者或群組所使用的裝置。 例如，處理高度機密資料的使用者在未經授權的情況下，會造成大量材料遺失。 | 將 Android 的最低版本提高為 10.0、引進行動威脅防護或 Microsoft Defender ATP，以及強制執行其他裝置限制。                                     | [完全管理的層級 3 設定](/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-high-security)                                                                                      |

 與任何架構一樣，可能需要根據組織的需求調整對應層級內的設定，因為安全性必須評估威脅環境、風險偏好，以及可用性的影響。

## <a name="learn-more"></a>深入了解

- [Android 企業版安全性設定架構](/mem/intune/enrollment/android-configuration-framework)
- [應用程式保護政策概觀](/mem/intune/apps/app-protection-policy)
- [Android 應用程式保護政策設定Microsoft Intune](/mem/intune/apps/app-protection-policy-settings-android)
- [設定註冊限制](/mem/intune/enrollment/enrollment-restrictions-set)
- [Android Enterprise安全性白皮書](https://static.googleusercontent.com/media/www.android.com/en//static/2016/pdfs/enterprise/Android_Enterprise_Security_White_Paper_2019.pdf)
