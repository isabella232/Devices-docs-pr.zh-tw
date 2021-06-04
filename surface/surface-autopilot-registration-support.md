---
title: 適用於 Windows Autopilot 的 Surface 註冊支援
description: 本文說明提交 Autopilot 註冊要求至 Microsoft 支援的需求。
ms.prod: w10
ms.mktglfcycl: manage
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 9/14/2020
ms.reviewer: brrecord
manager: laurawi
audience: itpro
ms.openlocfilehash: b31cacad5a744dcb29fc3dd2822c656d528fcd40
ms.sourcegitcommit: 25b8d880c6438f94b008f47b4fecc3aa4c473e85
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/28/2021
ms.locfileid: "11304836"
---
# 適用於 Windows Autopilot 的 Surface 註冊支援

您現在可以在 Microsoft 支援中取得為 Windows Autopilot 部署註冊 Surface 裝置的簡化程式。 從2020年9月起，客戶與 Microsoft 雲端解決方案供應商 (Csp) 可以透過提交要求到 Microsoft 支援來註冊 Surface 裝置。 此頁面概述下列支援的 Autopilot 註冊案例的需求：
 
- **Surface Device Autopilot 註冊**。 提交要求以在 Windows Autopilot 中註冊 Surface 裝置。
- **Surface 裝置硬體雜湊要求。** 提交 Microsoft 支援的要求，為您提供客戶或 Csp 可用來透過 Microsoft Intune 或 Microsoft 合作夥伴中心自行註冊裝置的硬體雜湊值。
- **[Surface 裝置] Autopilot [取消註冊]。** 提交從 Windows Autopilot 刪除裝置的要求，通常用於裝置的生命週期結束案例。

請參閱下表，瞭解在將註冊要求提交至 Microsoft 支援之前所需收集的資訊的詳細資訊。 如需所有 Surface 裝置的正式系統模型名稱，請參閱 [Surface SYSTEM SKU 參考](surface-system-sku-reference.md)。
 
**表 1. Autopilot 註冊要求所需的資訊**
 

| 必要資訊                   | 說明                                                                                                                                                                                                                                                                                    | Autopilot 註冊 | 硬體雜湊要求 | Autopilot<br>登出 |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory 租使用者識別碼**   | 您的 Azure Active Directory 租使用者識別碼是與您的組織名稱或網域不同 (GUID) 的全域唯一識別碼。<br> <br>若要尋找您的租使用者識別碼，請在 [這裡](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)登入 Azure 入口網站。 | 是                      | 否                     | 是                           |
| **Azure Active Directory 網功能變數名稱稱** | 您最上層的功能變數名稱;例如，contoso.com。                                                                                                                                                                                                                                          | 是                      | 否                     | 是                           |
| **擁有權憑證**                 | 以 PDF 格式上傳原始的銷售帳單或發票，以驗證擁有權。 螢幕擷取畫面不接受。<br> <br>[帳單] 或 [發票] 必須包括下列各項：<br>裝置序列值。<br>[公司名稱]。                                                           | 是                      | 是                     | 是                           |
| **裝置序列值**              | 以 CSV 格式上傳 Excel 檔案，並在新的一行中使用每個裝置的序列值。                                                                                                                                                                                                                  | 是                      | 是                     | 是                           |

 

##  <a name="submit-support-requests"></a>提交支援要求

  [![Get Autopilot 註冊支援 Surface](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
##  <a name="learn-more"></a>深入了解

- [Windows Autopilot 與 Surface 裝置](windows-autopilot-and-surface-devices.md)
- [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot)
- [Windows Autopilot 概觀](https://docs.microsoft.com/mem/autopilot/windows-autopilot)
- [Surface 系統 SKU 參考](surface-system-sku-reference.md)

 
 
 

