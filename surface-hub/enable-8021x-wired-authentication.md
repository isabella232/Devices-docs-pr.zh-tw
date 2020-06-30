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
# <span data-ttu-id="0b00c-103">啟用 802.1x 有線驗證</span><span class="sxs-lookup"><span data-stu-id="0b00c-103">Enable 802.1x wired authentication</span></span>

<span data-ttu-id="0b00c-104">[2017 年 11 月 14 日的 Windows 10 更新](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (組建 15063.726) 已在 Surface Hub 裝置上啟用 802.1x 有線驗證 MDM 原則。</span><span class="sxs-lookup"><span data-stu-id="0b00c-104">The [November 14, 2017 update to Windows 10](https://support.microsoft.com/help/4048954/windows-10-update-kb4048954) (build 15063.726) enables 802.1x wired authentication MDM policies on Surface Hub devices.</span></span> <span data-ttu-id="0b00c-105">此功能可讓組織使用 [IEEE 802.1x 驗證通訊協定](http://www.ieee802.org/1/pages/802.1x-2010.html)強制執行標準化有線網路驗證。</span><span class="sxs-lookup"><span data-stu-id="0b00c-105">The feature allows organizations to enforce standardized wired network authentication using the [IEEE 802.1x authentication protocol](http://www.ieee802.org/1/pages/802.1x-2010.html).</span></span> <span data-ttu-id="0b00c-106">這已透過 MDM 提供給使用 WLAN 設定檔的有線驗證。</span><span class="sxs-lookup"><span data-stu-id="0b00c-106">This is already available for wireless authentication using WLAN profiles via MDM.</span></span> <span data-ttu-id="0b00c-107">本主題說明如何設定 Surface Hub 使用有線驗證。</span><span class="sxs-lookup"><span data-stu-id="0b00c-107">This topic explains how to  configure a Surface Hub for use with wired authentication.</span></span> 

<span data-ttu-id="0b00c-108">在 Surface Hub 上強制執行和啟用 802.1x 有線驗證可以透過 MDM [OMA-URI 定義](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings)來完成。</span><span class="sxs-lookup"><span data-stu-id="0b00c-108">Enforcement and enablement of 802.1x wired authentication on Surface Hub can be done through MDM [OMA-URI definition](https://docs.microsoft.com/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune#oma-uri-settings).</span></span> 

<span data-ttu-id="0b00c-109">主要要進行得設定是 **LanProfile** 原則。</span><span class="sxs-lookup"><span data-stu-id="0b00c-109">The primary configuration to set is the **LanProfile** policy.</span></span> <span data-ttu-id="0b00c-110">取決於所選取的驗證方法，可能需要其他原則，可能是 **EapUserData** 原則或透過 MDM 原則新增使用者或電腦憑證 (例如 [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) 用於使用者/裝置憑證，或 [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) 用於裝置憑證)。</span><span class="sxs-lookup"><span data-stu-id="0b00c-110">Depending on the authentication method selected, other policies may be required, either the **EapUserData** policy or through MDM policies for adding user or machine certificates (such as [ClientCertificateInstall](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp) for user/device certificates or [RootCATrustedCertificates](https://docs.microsoft.com/windows/client-management/mdm/rootcacertificates-csp) for device certificates).</span></span> 

## <span data-ttu-id="0b00c-111">LanProfile 原則項目</span><span class="sxs-lookup"><span data-stu-id="0b00c-111">LanProfile policy element</span></span>

<span data-ttu-id="0b00c-112">若要設定 Surface Hub 來使用其中一個支援的 802.1x 驗證方法，請使用下列 OMA-URI。</span><span class="sxs-lookup"><span data-stu-id="0b00c-112">To configure Surface Hub to use one of the supported 802.1x authentication methods, utilize the following OMA-URI.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/LanProfile
```

<span data-ttu-id="0b00c-113">這個 OMA-URI 節點採用 XML 文字字串做為參數。</span><span class="sxs-lookup"><span data-stu-id="0b00c-113">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="0b00c-114">提供做為參數的 XML 必須遵守[有線區域網路設定檔架構](https://msdn.microsoft.com/library/cc233002.aspx)，包含 [802.1X 架構](https://msdn.microsoft.com/library/cc233003.aspx)中的項目。</span><span class="sxs-lookup"><span data-stu-id="0b00c-114">The XML provided as a parameter should conform to the [Wired LAN Profile Schema](https://msdn.microsoft.com/library/cc233002.aspx) including elements from the [802.1X schema](https://msdn.microsoft.com/library/cc233003.aspx).</span></span> 

<span data-ttu-id="0b00c-115">在大部分案例中，系統管理員或使用者可以使用下列 NETSH 命令，從已在 802.1X 網路上設定的現有電腦匯出 LanProfile XML。</span><span class="sxs-lookup"><span data-stu-id="0b00c-115">In most instances, an administrator or user can export the LanProfile XML from an existing PC that is already configured on the network for 802.1X using this following NETSH command.</span></span> 

```
netsh lan export profile folder=.
```

<span data-ttu-id="0b00c-116">執行此命令將會提供下列輸出，並在目前目錄放置名為 **Ethernet.xml** 的檔案。</span><span class="sxs-lookup"><span data-stu-id="0b00c-116">Running this command will give the following output and place a file titled **Ethernet.xml** in the current directory.</span></span> 

```
Interface: Ethernet
Profile File Name: .\Ethernet.xml
1 profile(s) were exported successfully.
```

## <span data-ttu-id="0b00c-117">EapUserData 原則項目</span><span class="sxs-lookup"><span data-stu-id="0b00c-117">EapUserData policy element</span></span>

<span data-ttu-id="0b00c-118">如果您選取的驗證方法需要使用者名稱和密碼，而不是憑證，您可以使用 **EapUserData** 項目來指定裝置認證以用來向網路進行驗證。</span><span class="sxs-lookup"><span data-stu-id="0b00c-118">If your selected authentication method requires a username and password as opposed to a certificate, you can use the **EapUserData** element to specify credentials for the device to use to authenticate to the network.</span></span> 

```
./Vendor/MSFT/SurfaceHub/Dot3/EapUserData 
```

<span data-ttu-id="0b00c-119">這個 OMA-URI 節點採用 XML 文字字串做為參數。</span><span class="sxs-lookup"><span data-stu-id="0b00c-119">This OMA-URI node takes a text string of XML as a parameter.</span></span> <span data-ttu-id="0b00c-120">提供做為參數的 XML 必須遵守 [PEAP MS-CHAPv2 使用者屬性範例](https://msdn.microsoft.com/library/windows/desktop/bb891979)。</span><span class="sxs-lookup"><span data-stu-id="0b00c-120">The XML provided as a parameter should conform to the [PEAP MS-CHAPv2 User Properties example](https://msdn.microsoft.com/library/windows/desktop/bb891979).</span></span> <span data-ttu-id="0b00c-121">在此範例中，您需要將所有 *test* 和 *ias-domain* 例項更換為您的資訊。</span><span class="sxs-lookup"><span data-stu-id="0b00c-121">In the example, you will need to replace all instances of *test* and *ias-domain* with your information.</span></span>



## <span data-ttu-id="0b00c-122">新增憑證</span><span class="sxs-lookup"><span data-stu-id="0b00c-122">Adding certificates</span></span>

<span data-ttu-id="0b00c-123">如果您選取的驗證方法是以憑證為基礎，您將需要[建立置備套件](provisioning-packages-for-surface-hub.md)、[使用 MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp)，或從 [設定] （[**設定**  >  **更新與安全性**憑證]）匯入憑證，  >  **Certificates**以將這些憑證部署到適當的憑證存放區中的 Surface Hub 裝置。</span><span class="sxs-lookup"><span data-stu-id="0b00c-123">If your selected authentication method is certificate-based, you will need to [create a provisioning package](provisioning-packages-for-surface-hub.md), [utilize MDM](https://docs.microsoft.com/windows/client-management/mdm/clientcertificateinstall-csp), or import a certificate from settings (**Settings** > **Update and Security** > **Certificates**) to deploy those certificates to your Surface Hub device in the appropriate Certificate Store.</span></span> <span data-ttu-id="0b00c-124">新增憑證時，每個 PFX 都只能包含一個憑證 (PFX 無法有多個憑證)。</span><span class="sxs-lookup"><span data-stu-id="0b00c-124">When adding certificates, each PFX must contain only one certificate (a PFX cannot have multiple certificates).</span></span>

