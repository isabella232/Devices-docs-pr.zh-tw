---
title: 適用於 Windows Autopilot 的 Surface 註冊支援
description: 本文將說明將 Autopilot 註冊要求提交給 Microsoft 支援服務的需求。
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 77881fae189af1ad3773f5fad192a28746e2d983
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449416"
---
# <a name="surface-registration-support-for-windows-autopilot"></a>適用於 Windows Autopilot 的 Surface 註冊支援

Microsoft 支援服務現在提供註冊適用于自動Windows部署之 Surface 裝置的簡化程式。 從 2020 年 9 月開始，客戶和 Microsoft 雲端解決方案提供者 (CSP) 向 Microsoft 支援服務提交要求，以註冊 Surface 裝置。 此頁面概述下列支援的 Autopilot 註冊案例需求：
 
- **Surface Device Autopilot 註冊**。 提交將 Surface 裝置註冊到 Autopilot Windows要求。
- **Surface Device 硬體雜湊要求。** 向 Microsoft 支援服務提交要求，提供客戶或 CSP 可透過 microsoft 合作夥伴中心自行註冊Microsoft Intune硬體雜湊。
- **Surface Device Autopilot Deregistration。** 提交從 Autopilot Windows刪除裝置的要求，通常是在裝置生命週期結束的情況下使用。

請參閱下表，瞭解在提交註冊要求至 Microsoft 支援服務之前，您需要收集的資訊詳細資料。 有關所有 Surface 裝置的正式系統模型名稱，請參閱 [Surface System SKU 參考](surface-system-sku-reference.md)。
 
**表 1. Autopilot 註冊要求所需的資訊**
 

| 必要的資訊                   | 描述                                                                                                                                                                                                                                                                                    | Autopilot 註冊 | 硬體雜湊要求 | 自動駕駛儀<br>登出 |
| -------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------- | --------------------- | --------------------------- |
| **Azure Active Directory租使用者識別碼**   | 您的Azure Active Directory識別碼是 GUID (全域唯一) 識別碼，與貴組織名稱或網域不同。<br> <br>若要在這裡找到您的租使用者識別碼，請在這裡找到 Azure 入口 [網站](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)。 | 是                      | 否                     | 是                           |
| **Azure Active Directory功能變數名稱** | 您的頂層功能變數名稱;例如，contoso.com。                                                                                                                                                                                                                                          | 是                      | 否                     | 是                           |
| **擁有證明**                 | 以 PDF 格式上傳原始的銷售帳單或發票，以驗證擁有憑證。 不接受螢幕擷取畫面。<br> <br>銷售單或發票必須包含下列專案：<br>裝置序號。<br>公司名稱。                                                           | 是                      | 是                     | 是                           |
| **裝置序號**              | Upload Excel CSV 格式的檔案，每一個裝置序號會以新行顯示。                                                                                                                                                                                                                  | 是                      | 是                     | 是                           |

 

## <a name="submit-support-requests"></a>提交支援要求

  [![Get Autopilot 註冊支援 Surface。](images/autopilot-reg-support-surface.png)](https://prod.support.services.microsoft.com/supportrequestform/0d8bf192-cab7-6d39-143d-5a17840b9f5f)
 
 
 
## <a name="learn-more"></a>深入了解

- [Windows Autopilot 與 Surface 裝置](windows-autopilot-and-surface-devices.md)
- [使用 Windows Autopilot 在 Intune 中註冊 Windows 裝置](/mem/autopilot/enrollment-autopilot)
- [Windows Autopilot 概觀](/mem/autopilot/windows-autopilot)
- [Surface 系統 SKU 參考](surface-system-sku-reference.md)

 
 
 

