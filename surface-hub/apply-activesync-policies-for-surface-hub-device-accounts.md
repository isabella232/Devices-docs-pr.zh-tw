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
ms.openlocfilehash: 7ead08e49d3eee2d616ac9fcf06b85dd82e136dc
ms.sourcegitcommit: 4ec96ff1cd563d055fa0689a63f136acf2794a2e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "11474730"
---
# <a name="applying-activesync-policies-to-device-accounts-surface-hub"></a><span data-ttu-id="8fe4d-105">將 ActiveSync 原則套用到裝置帳戶 (Surface Hub)</span><span class="sxs-lookup"><span data-stu-id="8fe4d-105">Applying ActiveSync policies to device accounts (Surface Hub)</span></span>


<span data-ttu-id="8fe4d-106">使用 Active Directory 裝置帳戶的 Surface Hub (以網域 **\使用者** 名稱格式) 和內部部署 Exchange 服務在中樞上部署，因此可以使用 ActiveSync 同步處理郵件和日曆。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-106">Surface Hubs using Active Directory device accounts (provisioned on the Hub in **domain\username** format) and on-premises Exchange services make use of ActiveSync to sync mail and calendar.</span></span> <span data-ttu-id="8fe4d-107">這讓使用者能夠從 Surface Hub 加入和啟動排程的會議，並讓他們能夠透過電子郵件傳送他們在會議期間製作的任何白板。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-107">This allows people to join and start scheduled meetings from the Surface Hub, and allows them to email any whiteboards they have made during their meeting.</span></span>

<span data-ttu-id="8fe4d-108">為了讓這些功能運作，您必須以下列方式設定適用於組織的 ActiveSync 原則：</span><span class="sxs-lookup"><span data-stu-id="8fe4d-108">For these features to work, the ActiveSync policies for your organization must be configured as follows:</span></span>

-   <span data-ttu-id="8fe4d-109">不能有任何會封鎖同步處理 Surface Hub 裝置帳戶所使用之資源信箱的全域原則。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-109">There can't be any global policies that block synchronization of the resource mailbox that's being used by the Surface Hub’s device account.</span></span> <span data-ttu-id="8fe4d-110">如果有這類封鎖政策，您必須將 Surface Hub 新增為允許的裝置。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-110">If there is such a blocking policy, you need to add the Surface Hub as an allowed device.</span></span>
-   <span data-ttu-id="8fe4d-111">您必須設定行動裝置信箱原則，將 **PasswordEnabled** 設定設為 False。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-111">You must set a mobile device mailbox policy where the **PasswordEnabled** setting is set to False.</span></span> <span data-ttu-id="8fe4d-112">其他的行動裝置信箱原則設定均與 Surface Hub 不相容。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-112">Other mobile device mailbox policy settings are not compatible with the Surface Hub.</span></span>

## <a name="allowing-the-deviceid"></a><span data-ttu-id="8fe4d-113">允許 DeviceID</span><span class="sxs-lookup"><span data-stu-id="8fe4d-113">Allowing the DeviceID</span></span>

<span data-ttu-id="8fe4d-114">您的組織可能有一個全域原則，以防止同步處理 Surface Hub 上佈建的裝置帳戶。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-114">Your organization may have a global policy that prevents syncing of device accounts provisioned on Surface Hubs.</span></span> <span data-ttu-id="8fe4d-115">若要設定這個屬性，請參閱 [允許適用於 ActiveSync 的裝置識別碼](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync)。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-115">To configure this property, see [Allowing device IDs for ActiveSync](appendix-a-powershell-scripts-for-surface-hub.md#allowing-device-ids-for-activesync).</span></span>

## <a name="setting-passwordenabled"></a><span data-ttu-id="8fe4d-116">設定 PasswordEnabled</span><span class="sxs-lookup"><span data-stu-id="8fe4d-116">Setting PasswordEnabled</span></span>

<span data-ttu-id="8fe4d-117">裝置帳戶必須具有 ActiveSync 原則，並將 **PasswordEnabled** 屬性設為 False 或 0。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-117">The device account must have an ActiveSync policy where the **PasswordEnabled** attribute is set to False or 0.</span></span> <span data-ttu-id="8fe4d-118">若要設定這個屬性，請參閱 [建立與 Surface Hub 相容的 Microsoft Exchange ActiveSync 原則](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy)。</span><span class="sxs-lookup"><span data-stu-id="8fe4d-118">To configure this property, see [Creating a Surface Hub-compatible Microsoft Exchange ActiveSync policy](appendix-a-powershell-scripts-for-surface-hub.md#create-compatible-as-policy).</span></span>

 

 





