---
title: 使用 Intune 將應用程式部署到 Surface Hub 2S
description: 瞭解您可以如何使用 Intune 將 app 部署到 Surface Hub 2。
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
ms.openlocfilehash: 51e54a5b2881519f2fc361675253c9e50bad0864
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831570"
---
# 使用 Intune 將應用程式部署到 Surface Hub 2S

您可以安裝其他 app 來符合您團隊或組織的需求。

##  <a name="developer-guidelines"></a>開發人員指導方針

- Surface Hub 僅能執行[通用 Windows 平台 (UWP) 應用程式](https://msdn.microsoft.com/windows/uwp/get-started/whats-a-uwp)。 使用 [Desktop App Converter](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-run-desktop-app-converter) 建立的應用程式將無法在 Surface Hub 上執行。
- 應用程式必須以[通用裝置系列](https://msdn.microsoft.com/library/windows/apps/dn894631)或 Windows 小組裝置系列為目標。
- Surface Hub 只支援來自[Microsoft Store For Business](https://businessstore.microsoft.com/store)的[離線授權 app](https://docs.microsoft.com/microsoft-store/distribute-offline-apps) 。
- 根據預設，應用程式必須經過市集簽署才能安裝。 在測試和開發期間，您也可以選擇將裝置切換到開發人員模式來執行開發人員簽署的 UWP app。
- 在開發並提交應用程式至 Microsoft Store 時，請設定裝置系列可用性與組織授權選項，以確保 app 可在 Surface Hub 上執行。
- 您需要系統管理員認證，才能在 Surface Hub 上安裝應用程式。 為在會議室和其他共用空間中使用而設計，Surface Hub 可防止一般使用者存取 Microsoft Store 來下載及安裝應用程式。

##  <a name="deployment-guidelines"></a>部署指導方針

您可以使用 Intune 將通用 Windows 平臺（UWP） app 部署至 Surface Hub 2-2，緩動 app 部署到裝置。

1. 若要部署應用程式，請為您的組織啟用 MDM。 在 Intune 入口網站中，選取 [ **Intune** ] 做為您的 MDM 頒發機構（建議）。 <br>

    ![選擇 MDM 頒發機構](images/sh2-set-intune5.png)

2. 在 Intune 中啟用商務用 Microsoft 網上商店。 開啟 Intune，選取 [**用戶端應用程式**  >  **Microsoft 網上商店]。** <br>

    ![啟用商務用商店](images/sh2-deploy-apps-sync.png)

3. 在 Intune 中開啟 [**商務用 Microsoft Store** ]，然後選取 [**設定**  >  **散佈**  >  **管理工具**]。 選擇 [ **Microsoft Intune** ] 做為您的管理工具。 <br>

    ![新增 Intune 作為您的管理工具](images/sh2-set-intune8.png)

4. 在 [商務用 Microsoft 網上商店] 中，選取 [**設定**  >  **車間**  >  **購物經驗**]，然後選取 [**顯示離線應用程式**]。 離線應用程式指的是可以同步處理到 Intune 並集中部署到裝置的 app。
5. 啟用離線購物之後，您可以為可同步處理到 Intune 並部署為裝置授權的 app 取得離線授權。
6. 在**Intune**  >  **用戶端 app**  >  **Microsoft Store for Business**中，選取 [**同步**處理]。
7. 在 [用戶端應用程式] 頁面上，于 [應用程式] 清單中搜尋應用程式。 將應用程式指派給想要的裝置群組或群組。 選取 [**作業**  >  **新增] 群組**。 <br>

![* 將 app 指派給群組 *](images/sh2-assign-group.png) <br>

8. 在 [作業類型] 底下，選擇 [**必要**]。 <br>

![* 將 app 指派給群組 *](images/sh2-add-group.png) <br>

9. 針對選取的群組，選擇 [**裝置授權**]，然後選取 **[確定]** 並儲存作業。 <br>
 
![* 將 app 指派給群組 *](images/sh2-apps-assign.png)
