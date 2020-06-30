---
title: 儲存您的 BitLocker 金鑰 (Surface Hub)
description: 每部 Microsoft Surface Hub 都是使用 BitLocker 磁碟機加密軟體自動設定。 Microsoft 強烈建議您務必備份您的 BitLocker 修復金鑰。
ms.assetid: E11E4AB6-B13E-4ACA-BCE1-4EDC9987E4F2
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, BitLocker, BitLocker 修復金鑰
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 07/08/2019
ms.localizationpriority: medium
ms.openlocfilehash: 73efa418fa80ef90a643d4fb4c457280ab982b38
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831958"
---
# 儲存您的 BitLocker 金鑰 (Surface Hub)


每部 Microsoft Surface Hub 都是使用 BitLocker 磁碟機加密軟體自動設定。 Microsoft 強烈建議您務必備份您的 BitLocker 修復金鑰。

有數種方式可用來管理 Surface Hub 上的 BitLocker 金鑰。

1.  如果您已將 Surface Hub 加入網域，裝置將會在網域中備份金鑰，並將它儲存在電腦物件。

    如果您在將裝置加入網域之後找不到 BitLocker 金鑰，很可能是您的 Active Directory 結構描述不支援 BitLocker 金鑰備份。 如果您不想變更結構描述，您可以移至 [設定]，然後遵循使用本機系統管理員帳戶的程序 (稍後將在此清單中加以詳述)，藉以儲存 BitLocker 金鑰。

2.  如果您已將 Surface Hub 加入 Azure Active Directory (Azure AD)，BitLocker 金鑰將會儲存於用來加入裝置的帳戶下方。

3.  如果您使用的是本機系統管理員帳戶來管理裝置，您可以移至 [**設定**] 應用程式，然後流覽到 [**更新 & 安全性**復原] 來儲存 BitLocker 金鑰 &gt; ** **。 插入 USB 磁碟機，然後選取選項來儲存 BitLocker 金鑰。 金鑰將會儲存到 USB 磁碟機上的文字檔。


## 相關主題

[管理 Microsoft Surface Hub](manage-surface-hub.md)

[Microsoft Surface Hub 系統管理員指南](surface-hub-administrators-guide.md)

 

 





