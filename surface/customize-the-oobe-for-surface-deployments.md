---
title: 自訂 Surface 部署的 OOBE (Surface)
description: 本文會逐步引導您為組織中的終端使用者自訂 Surface 全新體驗的流程。
ms.assetid: F6910315-9FA9-4297-8FA8-2C284A4B1D87
ms.reviewer: ''
manager: laurawi
keywords: deploy, customize, automate, network, Pen, pair, boot, 部署, 自訂, 自動化, 網路, 手寫筆, 配對, 開機
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
ms.openlocfilehash: f704541a2d862550250794308df6201c38b09e15
ms.sourcegitcommit: 6d531906c36da51cb4032a220d70182e686114a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2021
ms.locfileid: "11721263"
---
# <a name="customize-the-oobe-for-surface-deployments"></a>自訂 Surface 部署的 OOBE

本文將說明為貴組織的使用者自訂 Surface 即用即用體驗。

自訂所部署之電腦的使用者初次啟動體驗 (全新體驗，或簡稱為 OOBE) 是 Windows 部署中的常見做法。

>[!TIP]
>OOBE 也經常用於描述 Windows 設定期間顯示使用者體驗的階段或設定階段。 如需設定之 OOBE 階段的詳細資訊，請參閱[設定階段的運作方式](/windows-hardware/manufacture/desktop/how-configuration-passes-work)。

某些情況下，您可能希望提供完整的自動部署，以確保部署完成時，使用者不需進行任何互動即可使用電腦。 而在其他情況下，您可能希望保留體驗中的關鍵部分，讓使用者執行必要的動作，或在重要的選項之間進行選取。 對於部署 Surface 裝置的系統管理員，這兩種情況各自有需要克服的挑戰。

> [!NOTE]
> 本文不適用於 X Surface Pro。詳細資訊，請參閱部署[、管理](surface-pro-arm-app-management.md)及維護 X Surface Pro

本文提供部署時可能需要額外步驟之案例的摘要。 其中也提供確保任何新部署的 Surface 能達到預期之體驗的必要資訊。 本文的適用對象為熟悉部署程序及回應檔案和[建立 Windows 10 參照映像](https://technet.microsoft.com/itpro/windows/deploy/create-a-windows-10-reference-image)等概念的系統管理員。

>[!NOTE]
>雖然 OOBE 階段的設定仍在執行為自動化部署解決方案的一部分，例如 Microsoft 部署工具組[ (MDT) ](/mem/configmgr/mdt)或 Microsoft Endpoint Configuration Manager 作業系統部署 ([OSD) ，](/mem/configmgr/osd/)但系統是由部署精靈和工作順序所提供的設定自動執行。

## <a name="scenario-1-wireless-networking-in-oobe-with-mdt-2013"></a>案例 1：使用 MDT 2013 執行 OOBE 時的無線網路功能

當 OOBE 執行期間有無線網路介面卡存在時，會顯示 \[加入無線網路\] 頁面，並提示使用者連線至無線網路。**** 部署技術 (包含 MDT 2013) 不會自動隱藏此頁面，因此即使已將部署設定為完全自動化仍會顯示此頁面。

為了確保自動部署不會因為此頁面而停止，必須在回應檔案 **HideWirelessSetupInOOBE** 中設定額外的設定來隱藏此頁面。 您可以在[自動 Windows 設定參考](/windows-hardware/customize/desktop/unattend/microsoft-windows-shell-setup-oobe-hidewirelesssetupinoobe)中找到關於 **HideWirelessSetupInOOBE** 設定的其他資訊。

## <a name="scenario-2-surface-pen-pairing-in-oobe"></a>案例 2：在 OOBE 中配對 Surface 手寫筆

當您首次將 Surface Pro 3、Surface Pro 4、Surface Book 或 Surface Studio 從套件中取出並啟動時，原廠映像的初次執行體驗會包含一個提示，要求您將隨附的 Surface 手寫筆與裝置配對。 只有裝置出廠時隨附的原廠映象會提供此提示，其他用於部署的映像則不會，例如從「大量授權服務中心」下載的 Windows 企業版安裝媒體。 因為在此體驗之外配對藍牙 Surface 手寫筆需要進入「控制台」或「電腦設定」並手動配對藍牙裝置，因此您可能想要讓使用者或技術人員使用此提示來進行配對作業。

若要在 OOBE 中提供原廠 Surface 手寫筆配對體驗，您必須從原廠 Surface 映像複製四個檔案到參考映像。 您可以在擷取參考映像之前，將這些檔案複製到參考環境，或者您可於稍後使用「部署映像服務與管理」(DISM) 掛接映像時再將它們加入。 四個必要的檔案是︰

- %windir%\\system32\\oobe\\info\\default\\1033\\oobe.xml
- %windir%\\system32\\oobe\\info\\default\\1033\\PenPairing\_en-US.png
- %windir%\\system32\\oobe\\info\\default\\1033\\PenError\_en-US.png
- %windir%\\system32\\oobe\\info\\default\\1033\\PenSuccess\_en-US.png

>[!NOTE]
>您應該從與要部署的 Surface 裝置相同型號的原廠映像複製這些檔案。 例如，您應該使用 Surface Pro 7 中的檔案來部署到 Surface Pro 7，而使用 Surface Book 2 的檔案來部署 Surface Book 2，但您不應該使用 Surface Pro 7 中的檔案來部署 Surface Book 或 Surface Pro 6。

[部署 Surface Pro 3 手寫筆和 OneNote 的祕訣](https://blogs.technet.microsoft.com/askcore/2014/07/15/deploying-surface-pro-3-pen-and-onenote-tips/)中有提供將這些必要檔案加入映像的逐步說明。 這篇部落格文章也包含確保已安裝 Surface 手寫筆快速筆記體驗 (使用者只要按一下就能將筆記傳送至 OneNote) 之必要更新的祕訣。
