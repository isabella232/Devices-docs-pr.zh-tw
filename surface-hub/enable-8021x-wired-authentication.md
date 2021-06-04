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
ms.openlocfilehash: 119f879d74ccda5d53da27d842413346a50693f1
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831853"
---
# 啟用 802.1x 有線驗證

[2017 年 11 月 14 日的 Windows 10 更新](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (組建 15063.726) 已在 Surface Hub 裝置上啟用 802.1x 有線驗證 MDM 原則。 此功能可讓組織使用 [IEEE 802.1x 驗證通訊協定](http://www.ieee802.org/1/pages/802.1x-2010.html)強制執行標準化有線網路驗證。 這已透過 MDM 提供給使用 WLAN 設定檔的有線驗證。 本主題說明如何設定 Surface Hub 使用有線驗證。 

在 Surface Hub 上強制執行和啟用 802.1x 有線驗證可以透過 MDM [OMA-URI 定義](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings)來完成。 

主要要進行得設定是 **LanProfile** 原則。 取決於所選取的驗證方法，可能需要其他原則，可能是 **EapUserData** 原則或透過 MDM 原則新增使用者或電腦憑證 (例如 [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) 用於使用者/裝置憑證，或 [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) 用於裝置憑證)。 

##  <a name="lanprofile-policy-element"></a>LanProfile 原則項目

若要設定 Surface Hub 來使用其中一個支援的 802.1x 驗證方法，請使用下列 OMA-URI。 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

這個 OMA-URI 節點採用 XML 文字字串做為參數。 提供做為參數的 XML 必須遵守[有線區域網路設定檔架構](https://msdn.microsoft.com/library/cc233002.aspx)，包含 [802.1X 架構](https://msdn.microsoft.com/library/cc233003.aspx)中的項目。 

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

##  <a name="eapuserdata-policy-element"></a>EapUserData 原則項目

如果您選取的驗證方法需要使用者名稱和密碼，而不是憑證，您可以使用 **EapUserData** 項目來指定裝置認證以用來向網路進行驗證。 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

這個 OMA-URI 節點採用 XML 文字字串做為參數。 提供做為參數的 XML 必須遵守 [PEAP MS-CHAPv2 使用者屬性範例](https://msdn.microsoft.com/library/windows/desktop/bb891979)。 在此範例中，您需要將所有 *test* 和 *ias-domain* 例項更換為您的資訊。



##  <a name="adding-certificates"></a>新增憑證

如果您選取的驗證方法是以憑證為基礎，您將需要[建立置備套件](provisioning-packages-for-surface-hub.md)、[使用 MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)，或從 [設定] （[**設定**  >  **更新與安全性**憑證]）匯入憑證，  >  **Certificates**以將這些憑證部署到適當的憑證存放區中的 Surface Hub 裝置。 新增憑證時，每個 PFX 都只能包含一個憑證 (PFX 無法有多個憑證)。

