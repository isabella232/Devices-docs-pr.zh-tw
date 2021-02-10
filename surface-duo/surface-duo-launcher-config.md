---
title: 針對 Surface 雙核設定 Microsoft 啟動器
description: 本文將摘要說明如何針對商業環境中的受管理的裝置設定 Microsoft 啟動器。
ms.technology: windows
ms.prod: surface
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 8/12/2020
ms.reviewer: karand
manager: laurawi
ms.audience: itpro
audience: ITPro
ms.localizationpriority: medium
appliesto:
- Surface Duo
ms.openlocfilehash: 1254f28ce65894c8d43d89188f22ed161cd72098
ms.sourcegitcommit: 37e0994e2b8ae62b0352b016b698edcc7ca500fb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/10/2021
ms.locfileid: "11326281"
---
# <span data-ttu-id="2c70e-103">針對 Surface 雙核設定 Microsoft 啟動器</span><span class="sxs-lookup"><span data-stu-id="2c70e-103">Configure Microsoft Launcher for Surface Duo</span></span>

<span data-ttu-id="2c70e-104">Surface 雙核處理器技術支援企業版 Microsoft 啟動器（適用于企業），可讓使用者自行個人化手機、保持井然有序，並在行動裝置和其電腦之間嚴密地同步處理其行事曆、工作、記事及其他資訊。</span><span class="sxs-lookup"><span data-stu-id="2c70e-104">Surface Duo supports Microsoft Launcher for enterprise, an Android application that lets users personalize their phone, stay organized on the go, and seamlessly sync their Calendar, Task, Notes and more between mobile devices and their PCs.</span></span> <span data-ttu-id="2c70e-105">事實上，Surface 雙核啟動器是一個雙螢幕自訂版本的 Microsoft 啟動器，您可以調整它以定義貴組織的完整管理裝置上的最佳體驗，以及允許使用者在這些公司裝置上個人化他們的體驗。</span><span class="sxs-lookup"><span data-stu-id="2c70e-105">In fact, the Surface Duo launcher is a two-screen customized version of  Microsoft Launcher that you can adjust to define the preferred experiences on the fully managed devices for your organization as well as allow users some options to personalize their experiences on these corporate devices.</span></span> <span data-ttu-id="2c70e-106">例如，您可以選取要將哪些 app 釘選到主畫面、部署品牌牆紙，或隱藏搜尋列，同時允許使用者啟用搜尋列（如果需要的話）。</span><span class="sxs-lookup"><span data-stu-id="2c70e-106">For example, you can select which apps you want pinned to the home screen, deploy a branded wallpaper, or hide a search bar while allowing users to enable the Search bar if desired.</span></span>

## <span data-ttu-id="2c70e-107">Microsoft 啟動器設定</span><span class="sxs-lookup"><span data-stu-id="2c70e-107">Microsoft Launcher settings</span></span>

<span data-ttu-id="2c70e-108">Microsoft 啟動器包含下列設定，可自訂最終使用者體驗：</span><span class="sxs-lookup"><span data-stu-id="2c70e-108">Microsoft Launcher includes the following settings to customize the end user experience:</span></span>


- <span data-ttu-id="2c70e-109">允許使用者變更的主畫面 App 順序</span><span class="sxs-lookup"><span data-stu-id="2c70e-109">Home Screen App Order User Change Allowed</span></span>
- <span data-ttu-id="2c70e-110">設定格線大小</span><span class="sxs-lookup"><span data-stu-id="2c70e-110">Set Grid Size</span></span>
- <span data-ttu-id="2c70e-111">設定 Device 壁紙</span><span class="sxs-lookup"><span data-stu-id="2c70e-111">Set Device Wallpaper</span></span>
- <span data-ttu-id="2c70e-112">已允許設定 Device 壁紙使用者變更</span><span class="sxs-lookup"><span data-stu-id="2c70e-112">Set Device Wallpaper User Change Allowed</span></span>
- <span data-ttu-id="2c70e-113">啟用供給</span><span class="sxs-lookup"><span data-stu-id="2c70e-113">Feed Enable</span></span>
- <span data-ttu-id="2c70e-114">啟用 [允許使用者變更] 的摘要</span><span class="sxs-lookup"><span data-stu-id="2c70e-114">Feed Enable User Change Allowed</span></span>
- <span data-ttu-id="2c70e-115">搜尋列位置</span><span class="sxs-lookup"><span data-stu-id="2c70e-115">Search Bar Placement</span></span>
- <span data-ttu-id="2c70e-116">允許搜尋欄位置使用者變更</span><span class="sxs-lookup"><span data-stu-id="2c70e-116">Search Bar Placement User Change Allowed</span></span>
- <span data-ttu-id="2c70e-117">Dock 模式</span><span class="sxs-lookup"><span data-stu-id="2c70e-117">Dock Mode</span></span>
- <span data-ttu-id="2c70e-118">允許使用者變更的 Dock 模式</span><span class="sxs-lookup"><span data-stu-id="2c70e-118">Dock Mode User Change Allowed</span></span>

<span data-ttu-id="2c70e-119">如需每個設定的完整詳細資料，請參閱 [使用 Intune 設定適用于 Android Enterprise 的 Microsoft 啟動器](https://docs.microsoft.com/mem/intune/apps/configure-microsoft-launcher)。</span><span class="sxs-lookup"><span data-stu-id="2c70e-119">For full details of each setting, refer to [Configure Microsoft Launcher for Android Enterprise with Intune](https://docs.microsoft.com/mem/intune/apps/configure-microsoft-launcher).</span></span>

<span data-ttu-id="2c70e-120">如需逐步部署指示，請參閱 [如何使用 Intune 在 Android 企業完整管理的裝置上設定 Microsoft 啟動器](https://techcommunity.microsoft.com/t5/intune-customer-success/how-to-setup-microsoft-launcher-on-android-enterprise-fully/ba-p/1482134)。</span><span class="sxs-lookup"><span data-stu-id="2c70e-120">For step by step deployment instructions, refer to [How to Setup Microsoft Launcher on Android Enterprise Fully Managed Devices with Intune](https://techcommunity.microsoft.com/t5/intune-customer-success/how-to-setup-microsoft-launcher-on-android-enterprise-fully/ba-p/1482134).</span></span>
