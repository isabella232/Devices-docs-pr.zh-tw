---
title: '使用 Surface Enterprise 管理模式的安全 Surface Dock 2 埠 (SEMM) '
description: 這份檔在連線至相容的 Surface 裝置（包括 Surface Book 3、Surface 膝上型電腦3和 Surface Pro 7）時，提供設定 Surface Dock 2 的 UEFI 埠設定的指導方針。
ms.assetid: 2808a8be-e2d4-4cb6-bd53-9d10c0d3e1d6
ms.reviewer: ''
manager: laurawi
keywords: 疑難排解常見問題, 設定問題
ms.prod: w10
ms.mktglfcycl: support
ms.sitesec: library
ms.pagetype: surfacehub
author: v-miegge
ms.author: jesko
ms.topic: article
ms.date: 06/08/2020
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: 641d023b59426582130dcfb7e0d86c6f3af456e8
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114691"
---
# <span data-ttu-id="a98f7-104">使用 Surface Enterprise 管理模式的安全 Surface Dock 2 埠 (SEMM) </span><span class="sxs-lookup"><span data-stu-id="a98f7-104">Secure Surface Dock 2 ports with Surface Enterprise Management Mode (SEMM)</span></span>

## <span data-ttu-id="a98f7-105">簡介</span><span class="sxs-lookup"><span data-stu-id="a98f7-105">Introduction</span></span>

<span data-ttu-id="a98f7-106"> (SEMM) 的 Surface Enterprise 管理模式可讓 IT 管理員在 Windows 安裝程式配置套件 ( 中設定 UEFI 設定，以保護及管理 Surface Dock 2 埠。在企業環境中，) 將 MSI 檔案部署至相容的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="a98f7-106">Surface Enterprise Management Mode (SEMM) enables IT admins to secure and manage Surface Dock 2 ports by configuring UEFI settings in a Windows installer configuration package (.MSI file) deployed to compatible Surface devices across a corporate environment.</span></span>

### <span data-ttu-id="a98f7-107">支援的裝置</span><span class="sxs-lookup"><span data-stu-id="a98f7-107">Supported devices</span></span>

<span data-ttu-id="a98f7-108">使用 SEMM 的管理 Surface Dock 2 可供連接至 Surface Book 3、Surface 膝上型電腦3、Surface 膝上型電腦前往、Surface Pro 7 及 Surface Pro X。這些相容的 Surface 裝置通常稱為 **主機裝置**。</span><span class="sxs-lookup"><span data-stu-id="a98f7-108">Managing Surface Dock 2 with SEMM is available for docks connected to Surface Book 3, Surface Laptop 3, Surface Laptop Go, Surface Pro 7, and Surface Pro X. These compatible Surface devices are commonly referred to as **host devices**.</span></span> <span data-ttu-id="a98f7-109">根據主機裝置是否 **經過驗證** 或未 **驗證**，將套件套用到主機裝置。</span><span class="sxs-lookup"><span data-stu-id="a98f7-109">A package is applied to host devices based on if a host device is **authenticated** or **unauthenticated**.</span></span> <span data-ttu-id="a98f7-110">設定的設定會駐留在主機裝置上的 UEFI 層中，讓您（IT 系統管理員）管理 Surface Dock 2，就像相機中的任何其他內建外設一樣。</span><span class="sxs-lookup"><span data-stu-id="a98f7-110">Configured settings reside in the UEFI layer on host devices enabling you — the IT admin — to manage Surface Dock 2 just like any other built-in peripheral such as the camera.</span></span>

>[!NOTE]
><span data-ttu-id="a98f7-111">只有當 Dock 連接至下列其中一個相容的裝置時，才能管理 Surface Dock 2 埠： Surface Book 3、Surface 膝上型電腦3和 Surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="a98f7-111">You can manage Surface Dock 2 ports only when the dock is connected to one of the following compatible devices:  Surface Book 3, Surface Laptop 3, and Surface Pro 7.</span></span> <span data-ttu-id="a98f7-112">任何沒有收到 UEFI 驗證原則設定的裝置，本身就是未獲驗證的裝置。</span><span class="sxs-lookup"><span data-stu-id="a98f7-112">Any device that doesn't receive the UEFI Authenticated policy settings is inherently an unauthenticated device.</span></span>

### <span data-ttu-id="a98f7-113">案例</span><span class="sxs-lookup"><span data-stu-id="a98f7-113">Scenarios</span></span>

<span data-ttu-id="a98f7-114">針對登入公司主機裝置的授權人員，限制 Surface Dock 2，提供另一個層級的資料保護。</span><span class="sxs-lookup"><span data-stu-id="a98f7-114">Restricting Surface Dock 2 to authorized persons signed into a corporate host device provides another layer of data protection.</span></span> <span data-ttu-id="a98f7-115">鎖定 Surface Dock 2 的功能對於高度安全的環境中的特定客戶而言是非常重要的，他們想要在固定性的安全通訊協定中保持遵守，同時又能提供 Dock 的功能和生產力好處。</span><span class="sxs-lookup"><span data-stu-id="a98f7-115">This ability to lock down Surface Dock 2 is critical for specific customers in highly secure environments who want the functionality and productivity benefits of the dock while maintaining compliance with strict security protocols.</span></span> <span data-ttu-id="a98f7-116">我們預計在開啟的辦公室和共用空間中使用的 SEMM，特別適合出於安全考慮而想要鎖定 USB 埠的客戶。</span><span class="sxs-lookup"><span data-stu-id="a98f7-116">We anticipate SEMM used with Surface Dock 2 will be particularly useful in open offices and shared spaces especially for customers who want to lock USB ports for security reasons.</span></span> <span data-ttu-id="a98f7-117">如需視頻示範，請查看 [Surface Dock 2 的 SEMM](https://youtu.be/VLV19ISvq_s)。</span><span class="sxs-lookup"><span data-stu-id="a98f7-117">For a video demo, check out [SEMM for Surface Dock 2](https://youtu.be/VLV19ISvq_s).</span></span>

## <span data-ttu-id="a98f7-118">設定及部署 Surface Dock 2 的 UEFI 設定</span><span class="sxs-lookup"><span data-stu-id="a98f7-118">Configuring and deploying UEFI settings for Surface Dock 2</span></span>

<span data-ttu-id="a98f7-119">本節提供下列工作的逐步指導方針：</span><span class="sxs-lookup"><span data-stu-id="a98f7-119">This section provides step-by-step guidance for the following tasks:</span></span>

1. <span data-ttu-id="a98f7-120">安裝 [**SURFACE UEFI 配置**](https://www.microsoft.com/download/details.aspx?id=46703)器。</span><span class="sxs-lookup"><span data-stu-id="a98f7-120">Install [**Surface UEFI Configurator**](https://www.microsoft.com/download/details.aspx?id=46703).</span></span>
1. <span data-ttu-id="a98f7-121">建立或取得公開金鑰憑證。</span><span class="sxs-lookup"><span data-stu-id="a98f7-121">Create or obtain public key certificates.</span></span>
1. <span data-ttu-id="a98f7-122">建立。MSI 配置套件。</span><span class="sxs-lookup"><span data-stu-id="a98f7-122">Create an .MSI configuration package.</span></span>
   1. <span data-ttu-id="a98f7-123">新增您的憑證。</span><span class="sxs-lookup"><span data-stu-id="a98f7-123">Add your certificates.</span></span>
   1. <span data-ttu-id="a98f7-124">輸入 Surface Dock 2 裝置的16位數 RN 號碼。</span><span class="sxs-lookup"><span data-stu-id="a98f7-124">Enter the 16-digit RN number for your Surface Dock 2 devices.</span></span>
   1. <span data-ttu-id="a98f7-125">設定 UEFI 設定。</span><span class="sxs-lookup"><span data-stu-id="a98f7-125">Configure UEFI settings.</span></span>
1. <span data-ttu-id="a98f7-126">建立配置套件，並將其套用至目標 Surface 裝置 (Surface Book 3、Surface 膝上型電腦3或 Surface Pro 7。 ) </span><span class="sxs-lookup"><span data-stu-id="a98f7-126">Build and apply the configuration package to targeted Surface devices (Surface Book 3, Surface Laptop 3, or Surface Pro 7.)</span></span>

>[!NOTE]
><span data-ttu-id="a98f7-127">\*\* (RN) 的亂數字\*\*是唯一的16位十六進位代碼識別碼，在工廠提供，並在 dock 的下方以小型類型列印。</span><span class="sxs-lookup"><span data-stu-id="a98f7-127">The **Random Number (RN)** is a unique 16-digit hex code identifier which is provisioned at the factory, and printed in small type on the underside of the dock.</span></span> <span data-ttu-id="a98f7-128">RN 不同于大多數的序列值，因為它無法以電子方式讀取。</span><span class="sxs-lookup"><span data-stu-id="a98f7-128">The RN differs from most serial numbers in that it can't be read electronically.</span></span> <span data-ttu-id="a98f7-129">這可確保擁有權的證據，主要是透過在實際存取裝置時讀取 RN 來建立。</span><span class="sxs-lookup"><span data-stu-id="a98f7-129">This ensures proof of ownership is primarily established only by reading the RN when physically accessing the device.</span></span> <span data-ttu-id="a98f7-130">您也可以在購買交易期間取得 RN，並將其記錄在 Microsoft 庫存系統中。</span><span class="sxs-lookup"><span data-stu-id="a98f7-130">The RN may also be obtained during the purchase transaction and is recorded in Microsoft inventory systems.</span></span>

### <span data-ttu-id="a98f7-131">安裝 SEMM 和 Surface UEFI 配置器</span><span class="sxs-lookup"><span data-stu-id="a98f7-131">Install SEMM and Surface UEFI Configurator</span></span>

<span data-ttu-id="a98f7-132">透過執行 **SurfaceUEFI_Configurator_v2.71.139.0.msi**來安裝 SEMM。</span><span class="sxs-lookup"><span data-stu-id="a98f7-132">Install SEMM by running **SurfaceUEFI_Configurator_v2.71.139.0.msi**.</span></span> <span data-ttu-id="a98f7-133">這是獨立的安裝程式，包含您建立並散佈 Surface Dock 2 的設定套件所需的一切。</span><span class="sxs-lookup"><span data-stu-id="a98f7-133">This is a standalone installer and contains everything you need to create and distribute configuration packages for Surface Dock 2.</span></span>

- <span data-ttu-id="a98f7-134">從[表面工具](https://www.microsoft.com/en-us/download/details.aspx?id=46703)下載**SURFACE UEFI 配置**檔。</span><span class="sxs-lookup"><span data-stu-id="a98f7-134">Download **Surface UEFI Configurator** from [Surface Tools for IT](https://www.microsoft.com/en-us/download/details.aspx?id=46703).</span></span>

## <span data-ttu-id="a98f7-135">建立公開金鑰憑證</span><span class="sxs-lookup"><span data-stu-id="a98f7-135">Create public key certificates</span></span>

<span data-ttu-id="a98f7-136">本節提供建立週邊用來管理 Surface Dock 2 埠所需的憑證的規範。</span><span class="sxs-lookup"><span data-stu-id="a98f7-136">This section provides specifications for creating the certificates needed to manage ports for Surface Dock 2.</span></span>

### <span data-ttu-id="a98f7-137">必要條件</span><span class="sxs-lookup"><span data-stu-id="a98f7-137">Prerequisites</span></span>

<span data-ttu-id="a98f7-138">本文假設您是從協力廠商提供者取得憑證，或您已經有 PKI 認證服務的專業知識，並知道如何建立您自己的憑證。</span><span class="sxs-lookup"><span data-stu-id="a98f7-138">This article assumes that you either obtain certificates from a third-party provider or you already have expertise in PKI certificate services and know how to create your own.</span></span>  <span data-ttu-id="a98f7-139">您應該熟悉並遵循建立憑證的一般建議，如 [ [Surface Enterprise 管理] 模式 (SEMM) ](https://docs.microsoft.com/surface/surface-enterprise-management-mode) 檔中所述，但有一個例外狀況。</span><span class="sxs-lookup"><span data-stu-id="a98f7-139">You should be familiar with and follow the general recommendations for creating certificates as described in [Surface Enterprise Management Mode (SEMM)](https://docs.microsoft.com/surface/surface-enterprise-management-mode) documentation, with one exception.</span></span> <span data-ttu-id="a98f7-140">此頁面上所述的憑證需要在 **Dock 憑證授權單位**的到期期限為30年，且 **主機驗證憑證**為20年。</span><span class="sxs-lookup"><span data-stu-id="a98f7-140">The certificates documented on this page require expiration terms of 30 years for the **Dock Certificate Authority**, and 20 years for the **Host Authentication Certificate**.</span></span>

<span data-ttu-id="a98f7-141">如需詳細資訊，請參閱 [憑證服務架構](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) 檔，並在 microsoft 新聞中查看 [windows server 2019](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)中適當的章節，或是從 Microsoft 按下取得的 [Windows Server 2008 PKI 與證書安全性](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) 。</span><span class="sxs-lookup"><span data-stu-id="a98f7-141">For more information, see [Certificate Services Architecture](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture) documentation and review the appropriate chapters in [Windows Server 2019 Inside Out](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277), or [Windows Server 2008 PKI and Certificate Security](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788) available from Microsoft Press.</span></span>

### <span data-ttu-id="a98f7-142">根目錄與主機憑證需求</span><span class="sxs-lookup"><span data-stu-id="a98f7-142">Root and host certificate requirements</span></span>

<span data-ttu-id="a98f7-143">在建立設定套件之前，您必須準備公用金鑰憑證，以驗證 Surface Dock 2 的擁有權，並在裝置週期期間協助擁有任何後續變更。</span><span class="sxs-lookup"><span data-stu-id="a98f7-143">Prior to creating the configuration package, you need to prepare public key certificates that authenticate ownership of Surface Dock 2 and facilitate any subsequent changes in ownership during the device lifecycle.</span></span> <span data-ttu-id="a98f7-144">主機和置備憑證需要輸入 EKU Id，否則稱為「 \*\*用戶端驗證」增強型金鑰用法 (EKU) 物件識別碼 (oid) \*\*。</span><span class="sxs-lookup"><span data-stu-id="a98f7-144">The host and provisioning certificates require entering EKU IDs otherwise known as **Client Authentication Enhanced Key Usage (EKU) object identifiers (OIDs)**.</span></span>

<span data-ttu-id="a98f7-145">[資料表 1] 和 [資料表 2] 中列出所需的 EKU 值。</span><span class="sxs-lookup"><span data-stu-id="a98f7-145">The required EKU values are listed in Table 1 and Table 2.</span></span>

#### <span data-ttu-id="a98f7-146">表 1.</span><span class="sxs-lookup"><span data-stu-id="a98f7-146">Table 1.</span></span> <span data-ttu-id="a98f7-147">根目錄與 Dock 證書需求</span><span class="sxs-lookup"><span data-stu-id="a98f7-147">Root and Dock Certificate requirements</span></span>

|<span data-ttu-id="a98f7-148">憑證</span><span class="sxs-lookup"><span data-stu-id="a98f7-148">Certificate</span></span>|<span data-ttu-id="a98f7-149">演算法</span><span class="sxs-lookup"><span data-stu-id="a98f7-149">Algorithm</span></span>|<span data-ttu-id="a98f7-150">說明</span><span class="sxs-lookup"><span data-stu-id="a98f7-150">Description</span></span>|<span data-ttu-id="a98f7-151">到期</span><span class="sxs-lookup"><span data-stu-id="a98f7-151">Expiration</span></span>|<span data-ttu-id="a98f7-152">EKU OID</span><span class="sxs-lookup"><span data-stu-id="a98f7-152">EKU OID</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="a98f7-153">根憑證授權單位</span><span class="sxs-lookup"><span data-stu-id="a98f7-153">Root Certificate Authority</span></span>|<span data-ttu-id="a98f7-154">ECDSA_P384</span><span class="sxs-lookup"><span data-stu-id="a98f7-154">ECDSA_P384</span></span>|<span data-ttu-id="a98f7-155">-具有384位質數橢圓曲線數位簽章演算法 (ECDSA) 的根憑證</span><span class="sxs-lookup"><span data-stu-id="a98f7-155">- Root certificate with 384-bit prime elliptic curve digital signature algorithm (ECDSA)</span></span><br><span data-ttu-id="a98f7-156">-SHA 256 金鑰用法：</span><span class="sxs-lookup"><span data-stu-id="a98f7-156">- SHA 256 Key Usage:</span></span><br><span data-ttu-id="a98f7-157">CERT_DIGITAL_SIGNATURE_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="a98f7-157">CERT_DIGITAL_SIGNATURE_KEY_USAGE</span></span><br><span data-ttu-id="a98f7-158">-CERT_KEY_CERT_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="a98f7-158">- CERT_KEY_CERT_SIGN_KEY_USAGE</span></span><br><span data-ttu-id="a98f7-159">CERT_CRL_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="a98f7-159">CERT_CRL_SIGN_KEY_USAGE</span></span>|<span data-ttu-id="a98f7-160">30年</span><span class="sxs-lookup"><span data-stu-id="a98f7-160">30 years</span></span>|<span data-ttu-id="a98f7-161">無</span><span class="sxs-lookup"><span data-stu-id="a98f7-161">N/A</span></span>
|<span data-ttu-id="a98f7-162">Dock 憑證授權單位</span><span class="sxs-lookup"><span data-stu-id="a98f7-162">Dock Certificate Authority</span></span>|<span data-ttu-id="a98f7-163">ECC P256 曲線</span><span class="sxs-lookup"><span data-stu-id="a98f7-163">ECC P256 curve</span></span>|<span data-ttu-id="a98f7-164">具有256位橢圓曲線密碼的主機憑證 (ECC) </span><span class="sxs-lookup"><span data-stu-id="a98f7-164">- Host certificate with 256-bit elliptic-curve cryptography (ECC)</span></span><br><span data-ttu-id="a98f7-165">-SHA 256 金鑰用法：</span><span class="sxs-lookup"><span data-stu-id="a98f7-165">- SHA 256 Key Usage:</span></span><br><span data-ttu-id="a98f7-166">CERT_KEY_CERT_SIGN_KEY_USAGE</span><span class="sxs-lookup"><span data-stu-id="a98f7-166">CERT_KEY_CERT_SIGN_KEY_USAGE</span></span><br><span data-ttu-id="a98f7-167">-路徑長度限制 = 0</span><span class="sxs-lookup"><span data-stu-id="a98f7-167">- Path Length Constraint = 0</span></span>|<span data-ttu-id="a98f7-168">20年</span><span class="sxs-lookup"><span data-stu-id="a98f7-168">20 years</span></span>|<span data-ttu-id="a98f7-169">1.3.6.1.4.1.311.76.9.21.2</span><span class="sxs-lookup"><span data-stu-id="a98f7-169">1.3.6.1.4.1.311.76.9.21.2</span></span><br><span data-ttu-id="a98f7-170">1.3.6.1.4.1.311.76.9.21.3</span><span class="sxs-lookup"><span data-stu-id="a98f7-170">1.3.6.1.4.1.311.76.9.21.3</span></span>|

   >[!NOTE]
   ><span data-ttu-id="a98f7-171">Dock CA 必須匯出為. p7b 檔案。</span><span class="sxs-lookup"><span data-stu-id="a98f7-171">The dock CA must be exported as a .p7b file.</span></span>

### <span data-ttu-id="a98f7-172">提供管理憑證需求</span><span class="sxs-lookup"><span data-stu-id="a98f7-172">Provisioning Administration Certificate requirements</span></span>

<span data-ttu-id="a98f7-173">每個主機裝置都必須擁有 [doc] CA 和兩個憑證，如資料表2所示。</span><span class="sxs-lookup"><span data-stu-id="a98f7-173">Each host device must have the doc CA and two certificates as shown in Table 2.</span></span>

#### <span data-ttu-id="a98f7-174">表 2.</span><span class="sxs-lookup"><span data-stu-id="a98f7-174">Table 2.</span></span> <span data-ttu-id="a98f7-175">提供管理憑證需求</span><span class="sxs-lookup"><span data-stu-id="a98f7-175">Provisioning administration certificate requirements</span></span>

|<span data-ttu-id="a98f7-176">憑證</span><span class="sxs-lookup"><span data-stu-id="a98f7-176">Certificate</span></span>|<span data-ttu-id="a98f7-177">演算法</span><span class="sxs-lookup"><span data-stu-id="a98f7-177">Algorithm</span></span>|<span data-ttu-id="a98f7-178">說明</span><span class="sxs-lookup"><span data-stu-id="a98f7-178">Description</span></span>|<span data-ttu-id="a98f7-179">EKU OID</span><span class="sxs-lookup"><span data-stu-id="a98f7-179">EKU OID</span></span>|
|---|---|---|---|
|<span data-ttu-id="a98f7-180">主機驗證憑證</span><span class="sxs-lookup"><span data-stu-id="a98f7-180">Host authentication certificate</span></span>|<span data-ttu-id="a98f7-181">ECC P256</span><span class="sxs-lookup"><span data-stu-id="a98f7-181">ECC P256</span></span><br><span data-ttu-id="a98f7-182">SHA 256</span><span class="sxs-lookup"><span data-stu-id="a98f7-182">SHA 256</span></span>|<span data-ttu-id="a98f7-183">證明主機裝置的身分識別。</span><span class="sxs-lookup"><span data-stu-id="a98f7-183">Proves the identity of the host device.</span></span>|<span data-ttu-id="a98f7-184">1.3.6.1.4.1.311.76.9.21.2</span><span class="sxs-lookup"><span data-stu-id="a98f7-184">1.3.6.1.4.1.311.76.9.21.2</span></span>|
|<span data-ttu-id="a98f7-185">提供管理憑證</span><span class="sxs-lookup"><span data-stu-id="a98f7-185">Provisioning administration certificate</span></span>|<span data-ttu-id="a98f7-186">ECC P256</span><span class="sxs-lookup"><span data-stu-id="a98f7-186">ECC P256</span></span><br><span data-ttu-id="a98f7-187">SHA256</span><span class="sxs-lookup"><span data-stu-id="a98f7-187">SHA256</span></span>|<span data-ttu-id="a98f7-188">可讓您更換目前安裝在 dock 上的 CA，以變更 dock 擁有權和/或原則設定。</span><span class="sxs-lookup"><span data-stu-id="a98f7-188">Enables you to change dock ownership and/or policy settings by allowing you to replace the CA that's currently installed on the dock.</span></span>|<span data-ttu-id="a98f7-189">1.3.6.1.4.1.311.76.9.21.3</span><span class="sxs-lookup"><span data-stu-id="a98f7-189">1.3.6.1.4.1.311.76.9.21.3</span></span><br><span data-ttu-id="a98f7-190">1.3.6.1.4.1.311.76.9.21.4</span><span class="sxs-lookup"><span data-stu-id="a98f7-190">1.3.6.1.4.1.311.76.9.21.4</span></span>|

   >[!NOTE]
   ><span data-ttu-id="a98f7-191">主機驗證與預配憑證必須匯出為 .pfx 檔案。</span><span class="sxs-lookup"><span data-stu-id="a98f7-191">The host authentication and provisioning certificates must be exported as .pfx files.</span></span>

### <span data-ttu-id="a98f7-192">建立配置套件</span><span class="sxs-lookup"><span data-stu-id="a98f7-192">Create configuration package</span></span>

<span data-ttu-id="a98f7-193">取得或建立憑證之後，您就可以開始建立將套用至目標 Surface 裝置的 MSI 配置套件。</span><span class="sxs-lookup"><span data-stu-id="a98f7-193">When you have obtained or created the certificates, you’re ready to build the MSI configuration package that will be applied to target Surface devices.</span></span>

1. <span data-ttu-id="a98f7-194">執行 Surface **UEFI 配置**器。</span><span class="sxs-lookup"><span data-stu-id="a98f7-194">Run Surface **UEFI Configurator**.</span></span>

   ![執行 Surface UEFI 配置器](images/secure-surface-dock-ports-semm-1.png)

1. <span data-ttu-id="a98f7-196">選取 [ **介面固定**]。</span><span class="sxs-lookup"><span data-stu-id="a98f7-196">Select **Surface Dock**.</span></span>

   ![選取介面停靠](images/secure-surface-dock-ports-semm-2.png)

1. <span data-ttu-id="a98f7-198">在 [憑證] 頁面上，輸入適當的 **憑證**。</span><span class="sxs-lookup"><span data-stu-id="a98f7-198">On the certificate page, enter the appropriate **certificates**.</span></span>

   ![輸入適當的憑證](images/secure-surface-dock-ports-semm-3.png)

1. <span data-ttu-id="a98f7-200">在清單中新增適當的固定 RNs。</span><span class="sxs-lookup"><span data-stu-id="a98f7-200">Add appropriate dock RNs to the list.</span></span>

   >[!NOTE]
   ><span data-ttu-id="a98f7-201">為多個 Surface Dock 2 裝置建立配置套件時，不是手動輸入每個 RN，而是使用包含 RNs 清單的 .csv 檔案。</span><span class="sxs-lookup"><span data-stu-id="a98f7-201">When creating a configuration package for multiple Surface Dock 2 devices, instead of entering each RN manually, you can use a .csv file that contains a list of RNs.</span></span>

1. <span data-ttu-id="a98f7-202">指定 USB 資料、乙太網路和音訊埠的原則設定。</span><span class="sxs-lookup"><span data-stu-id="a98f7-202">Specify your policy settings for USB data, Ethernet, and Audio ports.</span></span> <span data-ttu-id="a98f7-203">UEFI 配置器可讓您為經過驗證的使用者設定策略設定， (驗證原則) 與未經驗證的使用者 (未驗證的原則) 。</span><span class="sxs-lookup"><span data-stu-id="a98f7-203">UEFI Configurator lets you configure policy settings for authenticated users (Authenticated Policy) and unauthenticated users (Unauthenticated Policy).</span></span> <span data-ttu-id="a98f7-204">下圖顯示針對經過驗證的使用者開啟埠存取，並針對未授權的使用者關閉該功能。</span><span class="sxs-lookup"><span data-stu-id="a98f7-204">The following figure shows port access turned on for authenticated users and turned off for unauthenticated users.</span></span>

   ![選擇您要啟動或停用的元件。](images/secure-surface-dock-ports-semm-4.png)

   - <span data-ttu-id="a98f7-206">已驗證使用者參照已安裝適當證書的 Surface 裝置，如中所述。您已套用至目標裝置的 MSI 配置套件。</span><span class="sxs-lookup"><span data-stu-id="a98f7-206">Authenticated user refers to a Surface Device that has the appropriate certificates installed, as configured in the .MSI configuration package that you applied to target devices.</span></span> <span data-ttu-id="a98f7-207">它適用于登入裝置的任何由使用者驗證的使用者。</span><span class="sxs-lookup"><span data-stu-id="a98f7-207">It applies to any user authenticated user who signs into the device.</span></span> 
   - <span data-ttu-id="a98f7-208">未驗證的使用者會參照任何其他裝置。</span><span class="sxs-lookup"><span data-stu-id="a98f7-208">Unauthenticated user refers to any other device.</span></span>
   - <span data-ttu-id="a98f7-209">選取 [ **重設** ]，建立特殊的「重設」套件，該套件將移除任何先前已接受的固定配置套件。</span><span class="sxs-lookup"><span data-stu-id="a98f7-209">Select **Reset** to create a special “Reset” package that will remove any previous configuration package that the dock had accepted.</span></span>

1. <span data-ttu-id="a98f7-210">選取 [ **建立** ] 以建立指定的套件。</span><span class="sxs-lookup"><span data-stu-id="a98f7-210">Select **Build** to create the package as specified.</span></span>

### <span data-ttu-id="a98f7-211">將 configuration 套件套用至 Surface Dock 2</span><span class="sxs-lookup"><span data-stu-id="a98f7-211">Apply the configuration package to a Surface Dock 2</span></span>

1. <span data-ttu-id="a98f7-212">讓 Surface UEFI 設定檔產生的 MSI 檔案，並將它安裝在 Surface 主機裝置上。</span><span class="sxs-lookup"><span data-stu-id="a98f7-212">Take the MSI file that the Surface UEFI Configurator generated and install it on a Surface host device.</span></span> <span data-ttu-id="a98f7-213">相容的主機裝置為 Surface Book 3、Surface 膝上型3或 Surface Pro 7。</span><span class="sxs-lookup"><span data-stu-id="a98f7-213">Compatible host devices are Surface Book 3, Surface Laptop 3, or Surface Pro 7.</span></span>
1. <span data-ttu-id="a98f7-214">將主機裝置連接至 Surface Dock 2。</span><span class="sxs-lookup"><span data-stu-id="a98f7-214">Connect the host device to the Surface Dock 2.</span></span> <span data-ttu-id="a98f7-215">當您連線時，就會套用 dock UEFI 原則設定。</span><span class="sxs-lookup"><span data-stu-id="a98f7-215">When you connect the dock UEFI policy settings are applied.</span></span>

## <span data-ttu-id="a98f7-216">使用 Surface App 驗證受管理的狀態</span><span class="sxs-lookup"><span data-stu-id="a98f7-216">Verify managed state using the Surface App</span></span>

<span data-ttu-id="a98f7-217">一旦您套用了設定套件，您就可以直接從 Surface App 驗證 dock 的產生原則狀態（依預設在所有 Surface 裝置上安裝）。</span><span class="sxs-lookup"><span data-stu-id="a98f7-217">Once you have applied the configuration package, you can quickly verify the resultant policy state of the dock directly from the Surface App, installed by default on all Surface devices.</span></span> <span data-ttu-id="a98f7-218">如果表面 App 不存在於裝置上，您可以從 Microsoft 網上商店下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="a98f7-218">If Surface App isn't present on the device, you can download and install it from the Microsoft Store.</span></span>

### <span data-ttu-id="a98f7-219">測試案例</span><span class="sxs-lookup"><span data-stu-id="a98f7-219">Test scenario</span></span>

<span data-ttu-id="a98f7-220">目標：將原則設定設定為僅允許經過驗證的使用者存取埠。</span><span class="sxs-lookup"><span data-stu-id="a98f7-220">Objective: Configure policy settings to allow port access by authenticated users only.</span></span>

1. <span data-ttu-id="a98f7-221">針對經過驗證的使用者開啟所有埠，然後將其關閉以進行未授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="a98f7-221">Turn on all ports for authenticated users and turn them off for unauthenticated users.</span></span>

   ![為經過驗證的使用者啟用埠](images/secure-surface-dock-ports-semm-4.png)

1. <span data-ttu-id="a98f7-223">將 [設定套件] 套用到您的目標裝置，然後連接 Surface Dock 2。</span><span class="sxs-lookup"><span data-stu-id="a98f7-223">Apply the configuration package to your target device and then connect Surface Dock 2.</span></span>

1. <span data-ttu-id="a98f7-224">開啟 [ **surface] App** ，然後選取 [ **表面停靠** ] 來查看 surface dock 的結果原則狀態。</span><span class="sxs-lookup"><span data-stu-id="a98f7-224">Open **Surface App** and select **Surface Dock** to view the resultant policy state of your Surface Dock.</span></span> <span data-ttu-id="a98f7-225">如果已套用原則設定，Surface App 就會指出埠可供使用。</span><span class="sxs-lookup"><span data-stu-id="a98f7-225">If the policy settings are applied, Surface App will indicate that ports are available.</span></span>

   ![Surface app 顯示所有埠都可供經過驗證的使用者使用](images/secure-surface-dock-ports-semm-5.png)

1. <span data-ttu-id="a98f7-227">現在，您必須驗證原則設定是否已成功關閉所有埠（未經授權的使用者）。</span><span class="sxs-lookup"><span data-stu-id="a98f7-227">Now you need to verify that the policy settings have successfully turned off all ports for unauthenticated users.</span></span> <span data-ttu-id="a98f7-228">將表面停靠2連接至未受管理的裝置，亦即，在您所建立之設定套件的管理範圍之外的任何 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="a98f7-228">Connect Surface Dock 2 to an unmanaged device, i.e., any Surface device outside the scope of management for the configuration package you created.</span></span>

1. <span data-ttu-id="a98f7-229">開啟 [ **surface] App** ，然後選取 [ **介面固定**]。</span><span class="sxs-lookup"><span data-stu-id="a98f7-229">Open **Surface App** and select **Surface Dock**.</span></span> <span data-ttu-id="a98f7-230">產生的原則狀態將會指出埠已關閉。</span><span class="sxs-lookup"><span data-stu-id="a98f7-230">The resultant policy state will indicate ports are turned off.</span></span>

   ![<span data-ttu-id="a98f7-231">顯示未授權使用者的埠關閉的 Surface 應用程式</span><span class="sxs-lookup"><span data-stu-id="a98f7-231">Surface app showing ports turned off for unauthenticated users</span></span> ](images/secure-surface-dock-ports-semm-6.png)

>[!NOTE]
><span data-ttu-id="a98f7-232">如果您想要保留裝置的擁有權，但允許所有使用者都能使用 [完全存取]，您可以建立新的套件，讓所有人都能開啟。</span><span class="sxs-lookup"><span data-stu-id="a98f7-232">If you want to keep ownership of the device, but allow all users full access, you can make a new package with everything turned on.</span></span> <span data-ttu-id="a98f7-233">如果您想要完全移除裝置的限制及擁有權， (讓它處於未受管理的) ，請選取 [在 Surface UEFI 設定檔中 **重設** ]，以建立要套用至目標裝置的套件。</span><span class="sxs-lookup"><span data-stu-id="a98f7-233">If you wish to completely remove the restrictions and ownership of the device (make it unmanaged), select **Reset** in Surface UEFI Configurator to create a package to apply to target devices.</span></span>

<span data-ttu-id="a98f7-234">！.</span><span class="sxs-lookup"><span data-stu-id="a98f7-234">Congratulations.</span></span> <span data-ttu-id="a98f7-235">您已在目標主機裝置上成功管理 Surface Dock 2 埠。</span><span class="sxs-lookup"><span data-stu-id="a98f7-235">You have successfully managed Surface Dock 2 ports on targeted host devices.</span></span>

## <span data-ttu-id="a98f7-236">深入了解</span><span class="sxs-lookup"><span data-stu-id="a98f7-236">Learn more</span></span>

- [<span data-ttu-id="a98f7-237"> (SEMM) 檔的 Surface Enterprise 管理模式</span><span class="sxs-lookup"><span data-stu-id="a98f7-237">Surface Enterprise Management Mode (SEMM) documentation</span></span>](https://docs.microsoft.com/surface/surface-enterprise-management-mode)
- [<span data-ttu-id="a98f7-238">憑證服務架構</span><span class="sxs-lookup"><span data-stu-id="a98f7-238">Certificate Services Architecture</span></span>](https://docs.microsoft.com/windows/win32/seccrypto/certificate-services-architecture)
- [<span data-ttu-id="a98f7-239">Windows Server 2019 內</span><span class="sxs-lookup"><span data-stu-id="a98f7-239">Windows Server 2019 Inside Out</span></span>](https://www.microsoftpressstore.com/store/windows-server-2019-inside-out-9780135492277)
- [<span data-ttu-id="a98f7-240">Windows Server 2008 PKI 與證書安全性</span><span class="sxs-lookup"><span data-stu-id="a98f7-240">Windows Server 2008 PKI and Certificate Security</span></span>](https://www.microsoftpressstore.com/store/windows-server-2008-pki-and-certificate-security-9780735640788)
