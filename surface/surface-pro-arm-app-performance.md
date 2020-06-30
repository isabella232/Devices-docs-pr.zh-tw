---
title: Surface Pro X 應用程式相容性
description: 本文提供 Surface Pro X ARM 電腦的簡介 app 相容性資訊。
ms.prod: w10
ms.localizationpriority: medium
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/03/2019
ms.reviewer: jessko
manager: laurawi
ms.audience: itpro
ms.openlocfilehash: c236bf066d22cae80f4c0df39cc04450ad57a419
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831516"
---
# <span data-ttu-id="f7d38-103">Surface Pro X 應用程式相容性</span><span class="sxs-lookup"><span data-stu-id="f7d38-103">Surface Pro X app compatibility</span></span>

<span data-ttu-id="f7d38-104">應用程式在 ARM 的 Windows 10 電腦（例如 Surface Pro X）上會以不同的方式執行。限制包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="f7d38-104">Applications run differently on ARM-based Windows 10 PCs such as Surface Pro X. Limitations include the following:</span></span>

- <span data-ttu-id="f7d38-105">**硬體、遊戲和應用程式的驅動程式只有專為 Windows 10 ARM 電腦所設計時才能運作**。</span><span class="sxs-lookup"><span data-stu-id="f7d38-105">**Drivers for hardware, games and apps will only work if they're designed for a Windows 10 ARM-based PC**.</span></span> <span data-ttu-id="f7d38-106">如需詳細資訊，請諮詢硬體製造商或開發驅動程式的組織。</span><span class="sxs-lookup"><span data-stu-id="f7d38-106">For more info, check with the hardware manufacturer or the organization that developed the driver.</span></span> <span data-ttu-id="f7d38-107">驅動程式是與硬體裝置通訊的軟體程式，通常用於防毒軟體與反惡意程式碼、列印或 PDF 軟體、輔助技術、CD 和 DVD 公用程式，以及虛擬化軟體。</span><span class="sxs-lookup"><span data-stu-id="f7d38-107">Drivers are software programs that communicate with hardware devices—they're commonly used for antivirus and antimalware software, printing or PDF software, assistive technologies, CD and DVD utilities, and virtualization software.</span></span> <span data-ttu-id="f7d38-108">如果驅動程式無法運作，依賴它的應用程式或硬體將無法運作（至少不是完全）。</span><span class="sxs-lookup"><span data-stu-id="f7d38-108">If a driver doesn’t work, the app or hardware that relies on it won’t work either (at least not fully).</span></span> <span data-ttu-id="f7d38-109">只有在 Windows 10 中內建群組件所依賴的驅動程式，或硬體開發人員已為裝置發行 ARM64 驅動程式時，才能使用週邊設備和裝置。</span><span class="sxs-lookup"><span data-stu-id="f7d38-109">Peripherals and devices only work if the drivers they depend on are built into Windows 10, or if the hardware developer has released ARM64 drivers for the device.</span></span>
- <span data-ttu-id="f7d38-110">**無法使用64位（x64）應用程式**。</span><span class="sxs-lookup"><span data-stu-id="f7d38-110">**64-bit (x64) apps won’t work**.</span></span> <span data-ttu-id="f7d38-111">您需要64位（ARM64）應用程式、32位（ARM32）應用程式，或32位（x86）應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d38-111">You'll need 64-bit (ARM64) apps, 32-bit (ARM32) apps, or 32-bit (x86) apps.</span></span> <span data-ttu-id="f7d38-112">您通常可以找到32位（x86）的應用程式版本，但某些 app 開發人員只提供64位（x64）應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d38-112">You can usually find 32-bit (x86) versions of apps, but some app developers only offer 64-bit (x64) apps.</span></span>
- <span data-ttu-id="f7d38-113">**有些遊戲無法運作**。</span><span class="sxs-lookup"><span data-stu-id="f7d38-113">**Certain games won’t work**.</span></span> <span data-ttu-id="f7d38-114">如果遊戲和應用程式使用的 OpenGL 版本大於1.1，或它們所依賴的是不是針對 Windows 10 ARM 電腦的「防型」驅動程式，則無法使用遊戲和 app。</span><span class="sxs-lookup"><span data-stu-id="f7d38-114">Games and apps won't work if they use a version of OpenGL greater than 1.1, or if they rely on "anti-cheat" drivers that haven't been made for Windows 10 ARM-based PCs.</span></span> <span data-ttu-id="f7d38-115">請與您的遊戲發行者確認遊戲是否可正常運作。</span><span class="sxs-lookup"><span data-stu-id="f7d38-115">Check with your game publisher to see if a game will work.</span></span>
- <span data-ttu-id="f7d38-116">**自訂 Windows 體驗的 app 可能會有問題**。</span><span class="sxs-lookup"><span data-stu-id="f7d38-116">**Apps that customize the Windows experience might have problems**.</span></span> <span data-ttu-id="f7d38-117">這包括一些輸入法編輯器（Ime）、輔助技術及雲端儲存應用程式。</span><span class="sxs-lookup"><span data-stu-id="f7d38-117">This includes some input method editors (IMEs), assistive technologies, and cloud storage apps.</span></span> <span data-ttu-id="f7d38-118">開發應用程式的組織會決定其應用程式是否可在 Windows 10 ARM 電腦上運作。</span><span class="sxs-lookup"><span data-stu-id="f7d38-118">The organization that develops the app determines whether their app will work on a Windows 10 ARM-based PC.</span></span>
- <span data-ttu-id="f7d38-119">**無法安裝某些協力廠商防毒軟體**。</span><span class="sxs-lookup"><span data-stu-id="f7d38-119">**Some third-party antivirus software can’t be installed**.</span></span> <span data-ttu-id="f7d38-120">您無法在 Windows 10 ARM 的電腦上安裝某些協力廠商的防毒軟體。</span><span class="sxs-lookup"><span data-stu-id="f7d38-120">You won't be able to install some third-party antivirus software on a Windows 10 ARM-based PC.</span></span> <span data-ttu-id="f7d38-121">不過，Windows 安全性將協助您保護 Windows 10 裝置支援的存留期。</span><span class="sxs-lookup"><span data-stu-id="f7d38-121">However, Windows Security will help keep you safe for the supported lifetime of your Windows 10 device.</span></span>
- <span data-ttu-id="f7d38-122">**Windows 傳真及掃描**功能無法使用。</span><span class="sxs-lookup"><span data-stu-id="f7d38-122">**Windows Fax and Scan isn’t available**.</span></span> <span data-ttu-id="f7d38-123">此功能無法在 Windows 10 ARM 電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="f7d38-123">This feature isn’t available on a Windows 10 ARM-based PC.</span></span>

<span data-ttu-id="f7d38-124">如需應用程式相容性的詳細資訊，請參閱[Windows 10 ARM 電腦常見問題（FAQ](https://support.microsoft.com/en-us/help/4521606) ）</span><span class="sxs-lookup"><span data-stu-id="f7d38-124">For more information about app compatibility, refer to [Windows 10 ARM-based PCs FAQ](https://support.microsoft.com/en-us/help/4521606)</span></span>
