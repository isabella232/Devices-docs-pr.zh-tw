---
title: 建立和測試裝置帳戶 (Surface Hub)
description: 本主題介紹如何建立和測試 Microsoft Surface Hub 用來與 Microsoft Exchange 和 Skype 通訊的裝置帳戶。
ms.assetid: C8605B5F-2178-4C3A-B4E0-CE32C70ECF67
ms.reviewer: rikot
manager: laurawi
keywords: 建立和測試裝置帳戶, 裝置帳戶, Surface Hub 與 Microsoft Exchange, Surface Hub 與 Skype
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 03/06/2018
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 20ec9b3a81ad511bcb7880de6b53025fbac0a561
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831897"
---
# 建立和測試裝置帳戶 (Surface Hub)


本主題介紹如何建立和測試 Microsoft Surface Hub 用來與 Microsoft Exchange 和 Skype 通訊的裝置帳戶。

**「裝置帳戶」** 是 Surface Hub 用來執行下列動作的 Exchange 資源帳戶：

-   顯示會議行事曆
-   加入小組或商務用 Skype 通話
-   傳送電子郵件 (例如以電子郵件寄送會議的白板內容)

當裝置帳戶已佈建到 Surface Hub 之後，人員便可以利用和邀請會議室相同的方式，將此帳戶新增到會議邀請。 

## 設定概觀

下表說明建立裝置帳戶的主要步驟和設定決策。 
 
| 步驟 | 說明                     |  用途                             |
|------|---------------------------------|--------------------------------------|
| sr-1    | 建立已啟用登入功能的 Exchange 資源信箱 (Exchange 2013 或更新版本，或是 Exchange Online) | 此資源信箱允許裝置維護會議行事曆、接收會議要求，以及傳送郵件。 它必須已啟用登入功能以佈建到 Surface Hub。 |
| pplx-2    | 設定信箱屬性 | 信箱必須設定為正確屬性，以在 Surface Hub 上提供最佳的會議體驗。 如需信箱屬性的詳細資訊，請參閱[信箱屬性](exchange-properties-for-surface-hub-device-accounts.md)。 |
| 3    | 將相容的行動裝置信箱原則套用到信箱 | Surface Hub 是使用行動裝置管理 (MDM) 來管理，而不是透過行動裝置信箱原則。 為了相容性，裝置帳戶必須具有已將 **PasswordEnabled** 設定設為 False 的行動裝置信箱原則。 否則，Surface Hub 將無法同步處理郵件和行事曆資訊。 |
| 4    | 為信箱啟用商務用 Skype (Lync Server 2013 或更新版本，或商務用 Skype Online) | 必須啟用商務用 Skype，才能使用各種不同的會議功能，例如，視訊通話、IM 和螢幕畫面分享。  |
| 500    | (選擇性) 將 ActiveSync 裝置 ID 納入允許清單 | 您的組織可能有一個全域原則，以防止裝置帳戶同步處理郵件和行事曆資訊。 如果是，您必須允許您 Surface Hub 的 ActiveSync 裝置識別碼。 |
| 6    | (選擇性) 停用密碼到期 | 為了簡化管理作業，您可以將裝置帳戶的密碼到期關閉，並允許 Surface Hub 自動循環裝置帳戶密碼。 如需密碼管理的詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。  |

## 詳細設定步驟 

建議您使用遠端 PowerShell 來設定裝置帳戶。 有可協助建立並驗證裝置帳戶的 PowerShell 指令碼可供使用。如需 PowerShell 指令碼和指示的詳細資訊，請參閱[附錄 A：PowerShell](appendix-a-powershell-scripts-for-surface-hub.md)。 

如需使用 PowerShell 佈建裝置帳戶的詳細步驟，請根據您的組織部署選擇表格中的選項。 

| 組織部署             |  說明                  |
|---------------------------------|--------------------------------------|
| [線上部署 (Office 365)](online-deployment-surface-hub-device-accounts.md) | 您組織的環境完全部署在 Office 365 上。 |
| [內部部署 (單一樹系)](on-premises-deployment-surface-hub-device-accounts.md) | 您的組織擁有其所控制的伺服器，並在單一樹系環境將它用來裝載 Active Directory、Exchange 及商務用 Skype (或 Lync)。 |
| [內部部署 (多重樹系)](on-premises-deployment-surface-hub-multi-forest.md) | 您的組織擁有其所控制的伺服器，並在多重樹系環境將它用來裝載 Active Directory、Exchange 及商務用 Skype (或 Lync)。 |
| [混合式部署](hybrid-deployment-surface-hub-device-accounts.md) | 您的組織擁有混合的服務，其中部分是透過內部部署裝載，部分是透過 Office 365 線上裝載。 |
| [線上或混合式部署，使用 Skype 混合語音環境](skype-hybrid-voice.md) | 您的組織在雲端中有商務用 Skype 主集區與 Exchange 伺服器，並使用透過公用交換電話網路 (PSTN) 連線的商務用 Skype 2015 或 Cloud Connector 版的內部部署集區。 |


如果您想要使用圖形化的使用者介面 (UI)，一部分的步驟可以不使用 PowerShell，而改為使用 UI 來完成。 如需詳細資訊，請參閱[使用 UI 建立裝置帳戶](create-a-device-account-using-office-365.md)。

## 帳戶驗證與測試

有兩種可用方法，您可以用來驗證和測試 Surface Hub 裝置帳戶：[帳戶驗證指令碼](appendix-a-powershell-scripts-for-surface-hub.md#acct-verification-ps-scripts)和 [Surface Hub 硬體診斷應用程式](https://www.microsoft.com/store/apps/9nblggh51f2g)。 帳戶驗證指令碼將會從桌面使用 PowerShell 來驗證先前建立的裝置帳戶。 Surface Hub 硬體診斷應用程式已安裝在 Surface Hub 上，並且會提供有關登入及通訊失敗的詳細意見反應。 兩者都是要測試新建立裝置帳戶的實用工具，您應該用來確保最佳的帳戶可用性。

 

 

 





