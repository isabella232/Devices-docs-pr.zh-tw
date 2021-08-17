---
title: Surface 和 Microsoft Endpoint Configuration Manager
description: 使用 Configuration Manager 管理及部署 Surface 裝置，基本上與任何其他電腦相同;本文將說明可能需要額外考慮的情境。
keywords: 管理、部署、更新、驅動程式、固件
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.date: 08/12/2021
ms.openlocfilehash: 66fb57afaa3e218a79ac31d36562bae567a3d301
ms.sourcegitcommit: 2776af08eb63c0a23950c476256e5019f83effd8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/17/2021
ms.locfileid: "11902632"
---
# <a name="considerations-for-surface-and-microsoft-endpoint-configuration-manager"></a>Surface 和 Microsoft Endpoint Configuration Manager

基本上，使用 Microsoft Endpoint Configuration Manager 管理及部署 Surface 裝置與管理及部署任何其他電腦相同。 與任何其他電腦一樣，Surface 裝置部署包括輸入驅動程式、Windows圖像、準備部署工作順序，然後將工作順序部署到集合。 部署之後，Surface 裝置會與其他用戶端Windows一樣;若要發佈應用程式、設定和策略，請使用與任何其他裝置相同的程式。

若要深入瞭解，請參閱Microsoft Endpoint Configuration Manager[檔](/mem/configmgr/)。

雖然 Surface 裝置部署和管理與其他電腦基本類似，但如本文所述，某些案例可能需要執行額外的 IT 工作。 

> [!TIP]
> 使用[Surface 裝置Microsoft Endpoint Configuration Manager](/mem/configmgr/core/servers/manage/updates)分支管理 Surface 裝置。

## <a name="update-surface-device-drivers-and-firmware"></a>更新 Surface 裝置驅動程式和固件

若要使用 Configuration Manager 或 WSUS Windows Server Update Services (部署更新裝置驅動程式和) ，請參閱管理[Surface 驅動程式和固件更新](manage-surface-driver-and-firmware-updates.md)。

## <a name="surface-ethernet-adapters-and-configuration-manager-deployment"></a>Surface 乙太網路介面卡和 Configuration Manager 部署

Configuration Manager 在部署期間用來識別裝置的預設機制是 MAC (存取控制) 裝置。 由於 MAC 位址與乙太網路控制器相關聯，因此在多個裝置之間共用的乙太網路介面卡會導致 Configuration Manager 將每個裝置識別為單一裝置，導致部署失敗。 

若要確保使用相同乙太網路介面卡的 Surface 裝置在部署期間被識別為唯一裝置，您可以指示 Configuration Manager 使用另一種方法識別裝置。 您可以指定 Configuration Manager 使用其他識別方法，如管理重複硬體識別碼所[記載：](/mem/configmgr/core/clients/manage/manage-clients#manage-duplicate-hardware-identifiers)

- 新增 Surface 乙太網路介面卡的 MAC 位址排除，強制 Configuration Manager 忽略系統 UUID 偏好設定中的 MAC 位址。

- 使用腳本，以無線介面卡的 MAC 位址識別新部署的 Surface 裝置。

### <a name="surface-ethernet-driver"></a>Surface 乙太網路磁碟機

自 2016 起，Surface 乙太網路介面卡的驅動程式預設已包含在 Windows 且不需要其他 IT 組組。 驅動程式包含在 Windows 10中，因此無法再從 Microsoft 下載中心下載。  (如果您需要部署較舊版本的 Windows 10 專業版，可以從[Microsoft](https://www.catalog.update.microsoft.com/Search.aspx?q=surface%20ethernet%20drivers)更新目錄下載最新的驅動程式) 。

## <a name="deploy-surface-app-with-configuration-manager"></a>使用 Configuration Manager 部署 Surface 應用程式

隨著版本商務用 Microsoft Store，Surface App 將不再提供驅動程式和固件下載。 將 Surface App 部署到受管理的 Surface 裝置或透過 Configuration Manager 進行部署期間，組織必須先透過 商務用 Microsoft Store 取得 Surface 應用程式。 若要深入瞭解，請參閱使用[商務用 Microsoft Store 部署 Surface 商務用 Microsoft Store。](deploy-surface-app-with-windows-store-for-business.md)

## <a name="use-prestaged-media-with-surface-clients"></a>在 Surface 用戶端使用預先暫存的媒體

如果貴組織在使用 Configuration Manager 進行部署之前，使用預先暫存的媒體將部署資源載入至電腦，則 Surface 裝置的性質是 UEFI 裝置，可能需要您採取其他步驟。 具體來說，原生 UEFI 環境要求您在系統的啟動磁片上建立多個分區。 如果您遵循預暫存媒體的檔[](/mem/configmgr/osd/deploy-use/create-prestaged-media)，指示只會提供單一分區啟動磁片，因此套用至 Surface 裝置時將會失敗。

在系統部落格文章的多重分區磁片中，如何將任務順序預先暫存媒體適用于BIOS 或 UEFI 電腦，可找到將預先暫存媒體適用于 [UEFI](https://techcommunity.microsoft.com/t5/configuration-manager-archive/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned/ba-p/392239) 裝置 ，例如 Surface 裝置的指示。

## <a name="licensing-conflicts-with-oem-activation-30"></a>授權與 OEM 啟用 3.0 衝突

Surface 裝置會預先安裝授權Windows。 此預先安裝 Windows 授權金鑰會內嵌于具有 OEM 啟用[3.0](/windows-hardware/manufacture/desktop/oem-activation-3) (OA 3.0) 的裝置) 。 當您在Windows OA 3.0 金鑰的裝置上執行安裝媒體時，Windows安裝程式會自動讀取授權金鑰，並使用它來安裝並Windows。 在大多數情況下，這可簡化Windows，因為使用者不需要尋找或輸入授權金鑰。

當您使用應用程式重新製作裝置Windows Enterprise，此內嵌授權金鑰不會造成衝突。 這是因為適用于 Windows Enterprise 的安裝媒體已Enterprise版本 Windows 因此與系統固件中內嵌的授權金鑰不相容。 如果未指定產品金鑰 (例如，當您打算使用金鑰管理服務 [KMS] 或 Active Directory 型啟用) 啟用時，一般大量授權金鑰 (GVLK) 會一直使用，直到 Windows 由其中一項技術啟用。

不過，當組織想要使用與Windows內嵌金鑰相容的版本時，可能會出現問題。 例如，想要在原本隨 Windows 10 家用版 一起出貨的裝置上安裝 Windows 10 專業版 的組織，當 Windows 安裝程式在安裝期間自動讀取家用版金鑰，並安裝為 Windows 10 家用版 而非 Windows 10 專業版 時，可能會遇到困難。 若要避免此衝突，請使用 Ei.cfg 或 Pid.txt 檔案明確指示 Windows 設定提示產品金鑰，或在部署工作順序中輸入特定產品金鑰。 詳細資訊請參閱設定Windows[版設定與產品識別碼檔案](/windows-hardware/manufacture/desktop/windows-setup-edition-configuration-and-product-id-files--eicfg-and-pidtxt)。 如果您沒有特定金鑰，您可以使用預設的產品金鑰Windows。 若要詳細資訊，請參閱部署[Windows 10。](/windows/deployment/deploy)

## <a name="apply-an-asset-tag-during-deployment"></a>在部署期間使用資產標記

使用 [Surface Asset 圖章工具](assettag.md)，即使作業系統失敗，您也可以從 UEFI 識別裝置。 若要深入瞭解使用 Configuration Manager 管理資產，請參閱 Configuration [Manager 中的資產智慧簡介](/mem/configmgr/core/clients/manage/asset-intelligence/introduction-to-asset-intelligence)。

## <a name="configure-push-button-reset"></a>設定按鈕重設

當您將 Windows部署到 Surface 裝置時，Windows 的按鈕重設功能預設會設定為將系統還原回尚未設定環境的狀態。 使用重設函數時，系統會捨棄任何已安裝的應用程式和設定。 雖然在某些情況下，將系統還原為沒有應用程式和設定的狀態可能相當有利，但若在專業環境中，這會使系統無法讓使用者使用。

不過，您可以設定按鈕重設，將系統設定還原為可供使用者使用的狀態。 請遵循部署按鈕重設功能中概述 [的流程](/windows-hardware/manufacture/desktop/deploy-push-button-reset-features) ，為裝置自訂按鈕重設體驗。
