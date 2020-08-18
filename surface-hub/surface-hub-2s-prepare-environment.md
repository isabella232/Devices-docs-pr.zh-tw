---
title: 針對 Surface Hub 2S 準備您的環境
description: 瞭解您需要採取哪些做法來準備您的環境以進行 Surface Hub 的2秒。
keywords: 使用逗號分隔值
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 11/21/2019
ms.localizationpriority: Medium
ms.openlocfilehash: dddab2adce1bec9ff722a3324b9c4b1be609ae89
ms.sourcegitcommit: ac34f0ec1a9df74ea688bf0da2a51fadf5139a41
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/18/2020
ms.locfileid: "10934843"
---
# 針對 Surface Hub 2S 準備您的環境

## Office 365 就緒

如果您使用的是 Exchange Online、商務用 Skype Online、Microsoft 團隊或 Microsoft 白板，且想要在 Intune 中管理 Surface Hub 2，請先查看 [端點的 Office 365 需求](https://docs.microsoft.com/office365/enterprise/office-365-endpoints)。

Office 365 端點可透過防火牆直接傳送所有受信任的 Office 365 網路要求，以繞過所有其他的資料包層級檢查或處理，協助優化您的網路。 此功能可減少延遲及您的周邊容量需求。

Microsoft 會定期使用新功能和功能更新 Office 365 服務，這可能會改變所需的埠、Url 和 IP 位址。 若要評估、設定及掌握最新變更，請訂閱 [Office 365 IP 位址和 URL Web 服務](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)。

## 裝置附屬

使用裝置附屬關係來管理使用者對 Surface Hub 2 上的 [設定] app 的存取權。
在 Surface Hub 2) 上執行的 Windows 10 小組作業系統 (，只有獲授權的使用者才能使用 [設定] app 來調整設定。 由於選擇 [隸屬關係] 可能會影響功能可用性，請適當地規劃，以確保使用者可以依預期存取功能。

> [!NOTE]
> 您只能在 (OOBE) 安裝程式的初始全新體驗期間設定裝置附屬。 如果您需要重設裝置附屬關係，您必須重複 OOBE 設定。

## 無隸屬關係

沒有任何隸屬關係，就像是在擁有各個 Surface Hub 2 的不同本機系統管理員帳戶的工作組中都有 Surface Hub 2。 如果您選擇 [無附屬]，您必須在本機將 [BitLocker 金鑰儲存至 USB 拇指磁片磁碟機](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-key-management-faq)。 您仍然可以使用 Intune 註冊裝置;不過，只有本機管理員才能使用在 OOBE 期間設定的帳號憑證來存取 [設定] 應用程式。 您可以從 [設定] app 變更系統管理員帳戶密碼。

## Active Directory Domain Services

如果您使用內部部署的 Active Directory 網域服務來建立 Surface Hub 2 的關聯，您必須使用網域上的安全性群組來管理 [設定] app 的存取權。 這有助於確保所有安全群組成員都有權變更 Surface Hub 2 的設定。 另請注意下列事項：

- 當 Surface Hub 2 擁有您的內部部署 Active Directory 網域服務的子公司時，可將 BitLocker 金鑰儲存在 Active Directory 架構中。 如需詳細資訊，請參閱 [準備貴組織以進行 BitLocker：規劃與原則](https://docs.microsoft.com/windows/security/information-protection/bitlocker/prepare-your-organization-for-bitlocker-planning-and-policies)。 
- 貴組織的根信任 Ca 會推送至 Surface Hub 2 中的相同容器，這表示您不需要使用置備套件匯入它們。
- 您仍可在 Intune 中註冊裝置，以集中管理 Surface Hub 2 的設定。

## Azure Active Directory

當您選擇將 Surface Hub 2 與 Azure Active Directory (Azure AD) 結合時，全域系統管理員安全性群組中的任何使用者都可以在 Surface Hub 2 的 [設定] 應用程式中登入。 目前，不能委派其他群組登入 Surface Hub 2 上的 [設定] 應用程式。

如果您為組織啟用 Intune 自動登記，Surface Hub 秒將會自動使用 Intune 註冊自己。 裝置的 BitLocker 金鑰會自動儲存在 Azure AD 中。 當 affiliating Surface Hub 2 和 Azure AD 時，單一登入和輕鬆驗證將無法運作。
