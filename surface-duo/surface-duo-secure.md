---
title: Surface Duo 安全性概觀
description: 本文重點說明 Surface 雙核如何透過 Android OS 和 Microsoft 工程的 UEFI，在行動裝置上提供企業級的安全性。
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
ms.openlocfilehash: 91eb893dbdc6dae93cf402a602b64a83309388e8
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326138"
---
# Surface Duo 安全性概觀

Surface 雙核在每一層中都有以較緊密的硬體、固件和軟體內建的保護，以確保您的裝置、身分識別及資料安全。 作為 Android 10 裝置，Surface 雙核使用 OS 層級和 Google services 層版的 Android 安全性功能。 Android OS 利用傳統的作業系統安全性控制來保護使用者資料和系統資源、保護裝置完整性，防範惡意程式碼，並提供應用程式隔離。 此外，Google 在作業系統上方提供了許多服務，在與 Android OS 安全性結合時，協助您持續保護 Android 使用者。

- **自訂設計的 UEFI。** 在 Android 裝置中，不同于 Surface 雙核，是 Microsoft 的自訂設計的整合可延伸韌體介面 (UEFI) ，可讓您完全控制固件元件。 Microsoft 透過在房屋中撰寫或審查每一行固件程式碼，提供企業級的安全性到 Surface 雙核，讓 Microsoft 能夠直接回應並 agilely 潛在的固件威脅，並緩解提供鏈安全性風險。
- **已驗證引導。** 從登入的硬體層級開始，驗證引導會努力確保執行的程式碼只來自受信任的來源。 它會建立完整的信任鏈，從受硬體保護的根信任到載入程式、開機磁碟分割及其他經過驗證的分區。 當 Surface 雙核啟動時，每個階段都會在提交執行之前驗證下一個階段的完整性與真實性。
- **App 分隔。** 應用程式沙箱會隔離並保護 Android 應用程式，防止惡意 app 存取私人資訊。 強制性、永不加密及金鑰處理可協助保護傳輸中和存放的資料，即使裝置落入錯誤的手中也一樣。 使用金鑰庫金鑰來保護加密，該金鑰會將加密金鑰儲存在容器中，讓它更難從裝置解壓縮。
- **Google Play 保護。** 在軟體層級，Surface 雙核使用 Google Play 保護威脅偵測，這會掃描所有應用程式，包括 Google Play 中的公用應用程式、Microsoft 和電信公司更新的系統 app，以及側載應用程式。
- **Microsoft Defender ATP。** Windows 10 版企業的防毒軟體和惡意程式碼保護軟體現已可供從 Intune 管理的 Android 裝置使用。 若要深入瞭解，請參閱 [Android 版 Microsoft DEFENDER ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-atp-android)。 


## 行動裝置管理安全性

在公司環境中使用企業行動裝置管理 (EMM) 方案來保護 Surface 雙核，提供一致的一組保護工具、技術和最佳做法，您可以根據您的組織和規範需求進行量身定制。 多種管理 Api 為 IT 部門提供工具，協助防止資料洩露，並在各種情況下強制執行合規性。 多重設定檔支援和裝置管理選項可讓公司和個人資料保持安全，協助保證公司資料的安全。

MDM 安全性是以一組不斷擴大的配置技術為基礎，可讓使用者在功能上保持生產力，同時也能保護重要的公司知識產權。 這包括 app 保護原則、裝置限制原則，以及旨在讓您根據您的環境來符合特定目標的相關技術，無論您的企業是由提供餐館 takeout 訂單、針對牙科辦公室管理 IT 服務，還是處理機密的國內安全性資訊。 

例如，您可能想要加強裝置驗證，方法是要求使用者輸入6位數的字母數位 pin 以及雙因素驗證。  您可能會想要限制使用者可以註冊的裝置，以協助確保您遵守授許可權制，或避免將存取權授予「已越獄」手機或其他不受支援的裝置類型。
Intune 和其他 Emm 為組織提供根據其需求管理裝置的靈活性。

## App 保護原則

App 保護原則 (應用程式) 是一些規則，可確保組織的資料在受管理的應用程式中保持安全或包含。 原則可以是當使用者嘗試存取或移動「企業」資料，或當使用者位於應用程式內時，禁止或監視的一組動作時所強制執行的規則。 受管理的 app 是已套用 app 保護原則且可由 Intune 管理的 app。

App 保護原則可讓您在應用程式中管理及保護貴組織的資料。 許多生產力應用程式（例如 Microsoft Office 應用程式）都可以由 Intune MAM 來管理。 請參閱可供公用使用的 [Microsoft Intune 受保護 app](https://docs.microsoft.com/mem/intune/apps/apps-supported-intune-apps) 正式清單。

## 管理 Surface 雙核的安全性考慮

行動裝置管理解決方案中提供的原則設定數量增加，讓組織能夠調整保護層級，以符合其特定需求。 為了協助組織為 Surface 雙核 (或任何其他 Android 裝置的安全性設定設定優先順序) ，Intune 已引進其 [Android 企業安全性配置架構](https://docs.microsoft.com/mem/intune/enrollment/android-configuration-framework) ，這些架構分為幾個不同的配置案例，提供工作設定檔和完全管理案例的指導方針。
 

| 安全性層級                                                                                                       | 目標物件                                                                                                                                                                      | 摘要                                                                                                                                                                                     | 設定資訊                                                                                                                                                                                                                                     |
| -------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 工作設定檔基本安全性-等級1                                                                                | 可存取公司或學校資料的個人裝置。                                                                                                                             | 引入密碼需求、將工作與個人資料分開，以及驗證 Android 裝置認證。                                                                               | [工作設定檔層級1設定](https://microsoft.sharepoint.com/teams/EpsilonAdminGuide/Shared%20Documents/General/•%09https:/docs.microsoft.com/mem/intune/enrollment/android-work-profile-security-settings#work-profile-basic-security) |
| 工作設定檔高安全性-層級3<br> (由於架構慣例，這是等級1上方的下一層級。 ) <br> ** | 使用者或群組所使用的裝置，這些裝置是唯一高的風險。 例如，在未經授權披露的情況下，處理高度敏感性資料的使用者可能會造成實質性的素材遺失。 | 介紹行動威脅防護或 Microsoft Defender ATP、將最小 Android 版本設為8.0、enacts 加強密碼原則，以及進一步限制工作與個人區隔。 | [工作設定檔層級3設定](https://docs.microsoft.com/mem/intune/enrollment/android-work-profile-security-settings#work-profile-high-security)                                                                                         |
| 完全管理的基本安全性-等級1                                                                                | 企業裝置的最低安全性設定，適用于大多數行動使用者存取公司或學校資料。                                                          | 引入密碼需求、將最低 Android 版本設定為8.0，並 enacts 特定裝置限制。                                                                          | [完全管理的第1層級設定](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-basic-security)                                                                                     |
| 全面管理的增強型安全層級2                                                                              | 使用者存取機密或機密資訊的裝置。                                                                                                                | Enacts 較強的密碼原則並停用使用者/帳戶功能。                                                                                                                   | [完全管理的層級 2 settngs](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-enhanced-security)                                                                                   |
| 完全管理的高安全性層級3                                                                                  | 使用者或群組所使用的裝置，這些裝置是唯一高的風險。 例如，在未經授權披露的情況下，處理高度敏感性資料的使用者可能會造成實質性的素材遺失。 | 將最低版本的 Android 版增加至10.0、引入行動威脅防護或 Microsoft Defender ATP，並強制執行額外的裝置限制。                                     | [完全管理的層級3設定](https://docs.microsoft.com/mem/intune/enrollment/android-fully-managed-security-settings#fully-managed-high-security)                                                                                      |
 
就像任何架構一樣，可能需要根據組織的需求來調整相對層中的設定，因為安全性必須評估威脅環境、風險 appetite 及可用性的影響。
 
 
**深入了解**


- [Android 企業安全性配置架構](https://docs.microsoft.com/mem/intune/enrollment/android-configuration-framework)
- [App 保護原則概述](https://docs.microsoft.com/mem/intune/apps/app-protection-policy)
- [Microsoft Intune 中的 Android 應用程式保護原則設定](https://docs.microsoft.com/mem/intune/apps/app-protection-policy-settings-android)
- [設定註冊限制](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set)
- [Android 企業安全性白皮書](https://static.googleusercontent.com/media/www.android.com/en//static/2016/pdfs/enterprise/Android_Enterprise_Security_White_Paper_2019.pdf)
 