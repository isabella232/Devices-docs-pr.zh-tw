---
title: Surface 與 Microsoft 端點建構管理員的考慮
description: 使用 Configuration Manager 管理和部署 Surface 裝置與任何其他電腦基本相同;本文將說明可能需要額外考慮的案例。
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
ms.openlocfilehash: 4fa62d227deb0b0b07fa0fbc6552ea5b04c1b87b
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831307"
---
# Surface 與 Microsoft 端點建構管理員的考慮

從根本上來說，使用 Microsoft 端點設定管理員來管理和部署 Surface 裝置，與管理和部署任何其他電腦相同。 就像任何其他電腦一樣，部署到 Surface 裝置包括匯入驅動程式、匯入 Windows 影像、準備部署工作序列，然後將任務序列部署到集合。 部署之後，Surface 裝置就像任何其他 Windows 用戶端一樣;若要發佈 app、設定及原則，您可以使用與任何其他裝置相同的程式。

您可以在[Microsoft 端點設定管理員的檔](https://docs.microsoft.com/sccm/index)中，找到有關如何使用 Configuration Manager 來部署和管理裝置的詳細資訊。

雖然表面裝置的部署與管理基本是與任何其他電腦相同，但在某些情況下，可能需要其他考慮或步驟。 本文提供這些案例的描述與指導方針。 本文中所述的解決方案也適用于其他裝置和製造商。

> [!NOTE]
> 若要管理 Surface 裝置，建議您使用 Microsoft 端點 Configuration Manager 的目前分支。

##  <a name="updating-surface-device-drivers-and-firmware"></a>更新 Surface 裝置驅動程式和固件

對於透過 Windows Update 接收更新的裝置，表面元件的驅動程式（甚至是固件更新）會自動套用為 Windows 更新程式的一部分。 針對有受管理更新的裝置（例如那些透過 Windows Server Update Services （WSUS）或 Configuration Manager 更新的裝置），請參閱[管理 Surface 驅動程式和固件更新](https://docs.microsoft.com/surface/manage-surface-driver-and-firmware-updates/)。

> [!NOTE]
> Surface 裝置驅動程式和固件已使用 SHA-256 簽署，這不是 Windows Server 2008 R2 本身所支援的。 在 Windows Server 2008 R2 上執行 Configuration Manager 環境時，有一個因應措施。 如需詳細資訊，請參閱[無法將驅動程式匯入 Microsoft 端點建構管理員（KB3025419）](https://support.microsoft.com/kb/3025419)。

##  <a name="surface-ethernet-adapters-and-configuration-manager-deployment"></a>Surface 乙太網卡與 Configuration Manager 部署

Configuration Manager 在部署期間用來識別裝置的預設機制是媒體存取控制（MAC）位址。 因為 MAC 位址是與乙太網路控制器相關聯，所以在多個裝置之間共用的乙太網路介面卡會使 Configuration Manager 僅將每個裝置識別為單一裝置。 這可能會導致 Windows Configuration Manager 部署無法套用至預期的裝置。

若要確保使用相同乙太網卡的 Surface 裝置在部署期間被識別為唯一的裝置，您可以指示 Configuration Manager 使用其他方法來識別裝置。 這個其他方法可能是無線網路介面卡的 MAC 位址，或是系統通用唯一識別碼（系統 UUID）。 您可以指定 Configuration Manager 使用其他身分識別方法，並使用下列選項：

* 針對 Surface 乙太網路介面卡的 MAC 位址新增排除，這會強制 Configuration Manager 忽略 System UUID 的 MAC 位址，如在[SMicrosoft 端點設定管理員 OSD 博客文章中重複使用相同的 NIC 進行多個 PXE 啟動的部署](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/)所述。

* 根據系統 UUID，在[Microsoft 端點 Configuration MANAGER OSD 博客文章中重複使用相同 NIC 進行多個 PXE 啟動的部署](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2015/08/27/reusing-the-same-nic-for-multiple-pxe-initiated-deployments-in-system-center-configuration-manger-osd/)中所述的裝置。

* 您可以使用腳本，透過其無線配接器的 MAC 位址來識別新部署的 Surface 裝置，如如何在[多個 SCCM OSD 博客文章中使用相同的外部乙太網路介面卡](https://blogs.technet.microsoft.com/askpfeplat/2014/07/27/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm-osd/)一文中所述。

在使用 Configuration Manager 進行部署期間，Surface 乙太網卡的另一個考慮是乙太網路控制器的驅動程式。 從 Windows 10 版本1511開始，在 Windows 中預設會包含 Surface 乙太網卡的驅動程式。 如果組織想要部署最新版本的 Windows 10 並使用最新版本的 WinPE，請使用 Surface 乙太網卡，不需要其他動作。

在 Windows 10 版1511（包括 Windows 10 RTM 和 Windows 8.1）之前的 Windows 版本中，您可能仍需要安裝 Surface 乙太網路介面卡驅動程式，並將該驅動程式包含在 WinPE 啟動媒體中。 在 Windows 10 中包含該驅動程式後，就不能再從 Microsoft 下載中心下載該驅動程式。 若要下載 Surface 乙太網路介面卡驅動程式，請從詢問核心小組博客的[Surface 乙太網路驅動程式](https://blogs.technet.microsoft.com/askcore/2016/08/18/surface-ethernet-drivers/)博客文章中所述，從 Microsoft 更新目錄下載它。

##  <a name="deploy-surface-app-with-configuration-manager"></a>使用 Configuration Manager 部署 Surface 應用程式

在 Microsoft Store for Business 發行中，Surface app 已不再以驅動程式和固件下載的形式提供。 想要將 Surface 應用程式部署到受管理的 Surface 裝置或在部署期間使用建構管理員的組織，必須透過商務用 Microsoft Store 取得 Surface app，然後再使用 PowerShell 部署 Surface 應用程式。 您可以在 TechNet 文件庫中，找到部署 Surface 應用程式的 PowerShell 命令、下載 Surface 應用程式的指示，以及 microsoft store for [business 文章中](https://technet.microsoft.com/itpro/surface/deploy-surface-app-with-windows-store-for-business)的 microsoft Store for business 中的必要架構。

##  <a name="use-prestaged-media-with-surface-clients"></a>將預留媒體與 Surface 用戶端搭配使用

如果您的組織使用預置媒體，在部署之前將部署資源預先載入到電腦上，則 Surface 裝置的性質是 UEFI 裝置，可能需要您採取其他步驟。 具體來說，原生 UEFI 環境需要您在系統的啟動磁片上建立多個分區。 如果您與[預留媒體的相關檔](https://technet.microsoft.com/library/79465d90-4831-4872-96c2-2062d80f5583?f=255&MSPPError=-2147217396#BKMK_CreatePrestagedMedia)一起追蹤，則指示僅提供單一分區啟動磁片，因此在套用至 Surface 裝置時將會失敗。

將預置媒體套用至 UEFI 裝置（例如 Surface 裝置）的指示，可以在 Microsoft 端點 Configuration Manager 博客文章中的 [[如何在多分區磁片上套用任務順序預留媒體] 或 [Uefi 電腦] 中](https://blogs.technet.microsoft.com/system_center_configuration_manager_operating_system_deployment_support_blog/2014/04/02/how-to-apply-task-sequence-prestaged-media-on-multi-partitioned-disks-for-bios-or-uefi-pcs-in-system-center-configuration-manager/)找到。

##  <a name="licensing-conflicts-with-oem-activation-3.0"></a>授權與 OEM 啟用3.0 的衝突

Surface 裝置會預先安裝已授權的 Windows 版本。 例如，Surface Pro 4 是預先預先安裝了 Windows 10 專業版。 此預先安裝的 Windows 版本的授權金鑰是內嵌在裝置的固件中，OEM 啟用3.0 （OA 3.0）。 當您在配備 OA 3.0 金鑰的裝置上執行 Windows 安裝媒體時，Windows 安裝程式會自動讀取授權金鑰，並使用它來安裝及啟用 Windows。 在大部分的情況下，這會簡化 Windows 的重新安裝，因為使用者不需要尋找或輸入授權金鑰。

當您使用 Windows Enterprise 重新鏡像裝置時，這個內嵌的授權金鑰不會導致衝突。 這是因為 Windows Enterprise 的安裝媒體已設定為只安裝 Windows 版企業版，因此與內嵌在系統固件中的授權金鑰不相容。 如果未指定產品金鑰（例如，您想要使用金鑰管理服務（KMS）或 Active Directory 啟用）來啟動產品金鑰，請使用一般的大量授權金鑰（GVLK），直到 Windows 由這些技術啟用為止。

不過，如果組織想要使用與固件內嵌金鑰相容的 Windows 版本，可能會發生問題。 例如，想要在最初隨附 Windows 10 家用版的 Surface 3 裝置上安裝 Windows 10 專業版的組織可能會在安裝期間自動讀取家用版金鑰而非專業版時遇到困難。 若要避免這種衝突，您可以使用 Ei 或 Pid.txt 檔案，明確指示 Windows 安裝程式提示輸入產品金鑰，或者您可以在部署工作序列中輸入特定產品金鑰。 如需詳細資訊，請參閱[Windows 安裝程式版本配置和產品識別碼](https://technet.microsoft.com/library/hh824952.aspx)檔案。 如果您沒有特定金鑰，您可以使用 Windows 的預設產品金鑰，您可以在裝置合作夥伴中心的[自訂和部署 Windows 10 作業系統](https://dpcenter.microsoft.com/en/Windows/Build/cp-Windows-10-build)中找到此功能。

##  <a name="apply-an-asset-tag-during-deployment"></a>在部署期間套用資產標記

Surface Studio、Surface Book、Surface Pro 4、Surface Pro 3 和 Surface 3 裝置都支援在 UEFI 中使用資產標記的應用程式。 即使作業系統失敗，也可以使用此資產標記來識別 UEFI 的裝置，也可以從作業系統中查詢。 若要深入瞭解 Surface 資產標記函式，請參閱[Surface Pro 3 博客文章的資產圖章工具](https://blogs.technet.microsoft.com/askcore/2014/10/20/asset-tag-tool-for-surface-pro-3/)。

若要在 Configuration Manager 部署工作序列期間使用[Surface 資產標記 CLI 公用程式](https://www.microsoft.com/download/details.aspx?id=44076)套用資產標記，請使用在[Configuration manager 任務序列文章中設定 surface 資產標記](https://blogs.technet.microsoft.com/jchalfant/set-surface-pro-3-asset-tag-during-a-configuration-manager-task-sequence/)中的腳本和指示。

##  <a name="configure-push-button-reset"></a>設定推播按鈕重設

當您將 Windows 部署到 Surface 裝置時，系統會預設設定 Windows 的按鈕重設功能，以將系統還原回尚未設定環境的狀態。 使用 reset 函數時，系統會捨棄任何已安裝的應用程式和設定。 雖然在某些情況下，將系統還原為不含應用程式和設定的狀態是有益的，但在專業環境中，這會有效地將系統呈現給最終使用者使用。

不過，您可以設定推播按鈕，將系統設定還原為可供最終使用者使用的狀態。 遵循[部署推播按鈕重設功能](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/deploy-push-button-reset-features)中所述的程式，來自訂裝置的按鈕重設體驗。
