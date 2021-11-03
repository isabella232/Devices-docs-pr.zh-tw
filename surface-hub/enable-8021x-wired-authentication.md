---
title: 啟用 802.1x 有線驗證
description: Surface Hub 裝置上已啟用 802.1x 有線驗證 MDM 原則。
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 11/15/2017
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.openlocfilehash: dcb2799accfcbccb41e44e09f0df3fd1ac6eb57e
ms.sourcegitcommit: 94e11386d7034c6bc5fe753f7bebf61a9c815509
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/02/2021
ms.locfileid: "12154038"
---
# <a name="enable-8021x-wired-authentication"></a>啟用 802.1x 有線驗證

[2017 年 11 月 14](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954)日更新至 Windows 10 (在 Surface Hub 裝置上啟用 802.1x 有線驗證 MDM) 15063.726。 此功能可讓組織使用 [IEEE 802.1x 驗證通訊協定](http://www.ieee802.org/1/pages/802.1x-2010.html)強制執行標準化有線網路驗證。 這項功能已經可用於透過 MDM 使用 [無線局域網卡設定檔進行](/mem/intune/configuration/wi-fi-settings-import-windows-8-1) 無線驗證。 本主題說明如何設定 Surface Hub 使用有線驗證。 

在 Surface Hub 上強制執行和啟用 802.1x 有線驗證可以透過 MDM [OMA-URI 定義](/mem/intune/configuration/custom-settings-windows-10)來完成。 

主要要進行得設定是 **LanProfile** 原則。 取決於所選取的驗證方法，可能需要其他原則，可能是 **EapUserData** 原則或透過 MDM 原則新增使用者或電腦憑證 (例如 [ClientCertificateInstall](/windows/client-management/mdm/clientcertificateinstall-csp) 用於使用者/裝置憑證，或 [RootCATrustedCertificates](/windows/client-management/mdm/rootcacertificates-csp) 用於裝置憑證)。 

## <a name="lanprofile-policy-element"></a>LanProfile 原則項目

若要設定 Surface Hub 來使用其中一個支援的 802.1x 驗證方法，請使用下列 OMA-URI。 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

這個 OMA-URI 節點採用 XML 文字字串做為參數。 提供做為參數的 XML 必須遵守[有線區域網路設定檔架構](/openspecs/windows_protocols/ms-gpwl/c88a926a-087b-405f-9a76-effaf7277bf3)，包含 [802.1X 架構](/openspecs/windows_protocols/ms-gpwl/71f2eda6-d018-4ba3-ad37-32c98b926ebb)中的項目。 

在大部分案例中，系統管理員或使用者可以使用下列 NETSH 命令，從已在 802.1X 網路上設定的現有電腦匯出 LanProfile XML。 

```
netsh lan export profile folder=.
```

執行此命令將會提供下列輸出，並在目前目錄放置名為 **Ethernet.xml** 的檔案。 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <a name="eapuserdata-policy-element"></a>EapUserData 原則項目

如果您選取的驗證方法需要使用者名稱和密碼，而不是憑證，您可以使用 **EapUserData** 項目來指定裝置認證以用來向網路進行驗證。 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

這個 OMA-URI 節點採用 XML 文字字串做為參數。 提供做為參數的 XML 必須遵守 [PEAP MS-CHAPv2 使用者屬性範例](/windows/win32/eaphost/peap-ms-chapv2-user-properties)。 在此範例中，您需要將所有 *test* 和 *ias-domain* 例項更換為您的資訊。



## <a name="adding-certificates"></a>新增憑證

如果您選取的驗證方法是以憑證為基礎，您必須建立一個設定[](provisioning-packages-for-surface-hub.md)套件、使用[MDM，](/windows/client-management/mdm/clientcertificateinstall-csp)或從設定 (**設定 更新**和安全性憑證) 將這些憑證部署到適當的憑證存放區中的  >  ****  >  ** **Surface Hub 裝置。 新增憑證時，每個 PFX 都只能包含一個憑證 (PFX 無法有多個憑證)。

