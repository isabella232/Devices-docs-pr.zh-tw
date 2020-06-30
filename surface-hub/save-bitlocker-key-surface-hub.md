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
# <span data-ttu-id="3603d-105">儲存您的 BitLocker 金鑰 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="3603d-105">Save your BitLocker key (Surface Hub)</span></span>


<span data-ttu-id="3603d-106">每部 Microsoft Surface Hub 都是使用 BitLocker 磁碟機加密軟體自動設定。</span><span class="sxs-lookup"><span data-stu-id="3603d-106">Every Microsoft Surface Hub is automatically set up with BitLocker drive encryption software.</span></span> <span data-ttu-id="3603d-107">Microsoft 強烈建議您務必備份您的 BitLocker 修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="3603d-107">Microsoft strongly recommends that you make sure you back up your BitLocker recovery keys.</span></span>

<span data-ttu-id="3603d-108">有數種方式可用來管理 Surface Hub 上的 BitLocker 金鑰。</span><span class="sxs-lookup"><span data-stu-id="3603d-108">There are several ways to manage your BitLocker key on the Surface Hub.</span></span>

1.  <span data-ttu-id="3603d-109">如果您已將 Surface Hub 加入網域，裝置將會在網域中備份金鑰，並將它儲存在電腦物件。</span><span class="sxs-lookup"><span data-stu-id="3603d-109">If you’ve joined the Surface Hub to a domain, the device will back up the key on the domain and store it under the computer object.</span></span>

    <span data-ttu-id="3603d-110">如果您在將裝置加入網域之後找不到 BitLocker 金鑰，很可能是您的 Active Directory 結構描述不支援 BitLocker 金鑰備份。</span><span class="sxs-lookup"><span data-stu-id="3603d-110">If you can’t find the BitLocker key after joining the device to a domain, it’s likely that your Active Directory schema doesn’t support BitLocker key backup.</span></span> <span data-ttu-id="3603d-111">如果您不想變更結構描述，您可以移至 [設定]，然後遵循使用本機系統管理員帳戶的程序 (稍後將在此清單中加以詳述)，藉以儲存 BitLocker 金鑰。</span><span class="sxs-lookup"><span data-stu-id="3603d-111">If you don’t want to change the schema, you can save the BitLocker key by going to Settings and following the procedure for using a local admin account, which is detailed later in this list.</span></span>

2.  <span data-ttu-id="3603d-112">如果您已將 Surface Hub 加入 Azure Active Directory (Azure AD)，BitLocker 金鑰將會儲存於用來加入裝置的帳戶下方。</span><span class="sxs-lookup"><span data-stu-id="3603d-112">If you’ve joined the Surface Hub to Azure Active Directory (Azure AD), the BitLocker key will be stored under the account that was used to join the device.</span></span>

3.  <span data-ttu-id="3603d-113">如果您使用的是本機系統管理員帳戶來管理裝置，您可以移至 [**設定**] 應用程式，然後流覽到 [**更新 & 安全性**復原] 來儲存 BitLocker 金鑰 &gt; \*\* \*\*。</span><span class="sxs-lookup"><span data-stu-id="3603d-113">If you’re using a local admin account to manage the device, you can save the BitLocker key by going to the **Settings** app and navigating to **Update & security** &gt; **Recovery**.</span></span> <span data-ttu-id="3603d-114">插入 USB 磁碟機，然後選取選項來儲存 BitLocker 金鑰。</span><span class="sxs-lookup"><span data-stu-id="3603d-114">Insert a USB drive and select the option to save the BitLocker key.</span></span> <span data-ttu-id="3603d-115">金鑰將會儲存到 USB 磁碟機上的文字檔。</span><span class="sxs-lookup"><span data-stu-id="3603d-115">The key will be saved to a text file on the USB drive.</span></span>


## <span data-ttu-id="3603d-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="3603d-116">Related topics</span></span>

[<span data-ttu-id="3603d-117">管理 Microsoft Surface Hub</span><span class="sxs-lookup"><span data-stu-id="3603d-117">Manage Microsoft Surface Hub</span></span>](manage-surface-hub.md)

[<span data-ttu-id="3603d-118">Microsoft Surface Hub 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="3603d-118">Microsoft Surface Hub administrator's guide</span></span>](surface-hub-administrators-guide.md)

 

 





