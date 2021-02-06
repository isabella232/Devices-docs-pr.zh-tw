---
title: 將 ActiveSync 原則套用到裝置帳戶 (Surface Hub)
description: Microsoft Surface Hub 的裝置帳戶會使用 ActiveSync 來同步處理電子郵件和行事曆。 這讓使用者能夠從 Surface Hub 加入和啟動排程的會議，並讓他們能夠透過電子郵件傳送他們在會議期間製作的任何白板。
ms.assetid: FAABBA74-3088-4275-B58E-EC1070F4D110
ms.reviewer: ''
manager: laurawi
keywords: Surface Hub, ActiveSync 原則
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 06/20/2019
ms.localizationpriority: medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: 4db5066c62f4e0e324a5cc3ddad027e00a2e18c9
ms.sourcegitcommit: 7809222a51eb184f07d6b3ffbdd04a6272b247f9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314406"
---
# 將 ActiveSync 原則套用到裝置帳戶 (Surface Hub)


所有版本的 Microsoft Surface Hub 中的裝置帳戶都使用 ActiveSync 來同步處理郵件和行事曆。 這讓使用者能夠從 Surface Hub 加入和啟動排程的會議，並讓他們能夠透過電子郵件傳送他們在會議期間製作的任何白板。

為了讓這些功能運作，您必須以下列方式設定適用於組織的 ActiveSync 原則：

-   不能有任何會封鎖同步處理 Surface Hub 裝置帳戶所使用之資源信箱的全域原則。 如果有這樣的封鎖原則，您需要將 Surface Hub 新增為允許的裝置。
-   您必須設定行動裝置信箱原則，將 **PasswordEnabled** 設定設為 False。 其他的行動裝置信箱原則設定均與 Surface Hub 不相容。

## 允許 DeviceID

您的組織可能有一個全域原則，以防止同步處理 Surface Hub 上佈建的裝置帳戶。 若要設定這個屬性，請參閱 [允許適用於 ActiveSync 的裝置識別碼](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync)。

## 設定 PasswordEnabled

裝置帳戶必須具有 ActiveSync 原則，並將 **PasswordEnabled** 屬性設為 False 或 0。 若要設定這個屬性，請參閱 [建立與 Surface Hub 相容的 Microsoft Exchange ActiveSync 原則](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy)。

 

 





