---
title: 在 Surface 裝置上啟用 PEAP、EAP-FAST 和 Cisco LEAP (Surface)
description: 了解如何讓 Surface 裝置支援 PEAP、EAP-FAST 和 Cisco LEAP 通訊協定。
ms.assetid: A281EFA3-1552-467D-8A21-EB151E58856D
ms.reviewer: ''
manager: laurawi
keywords: network, wireless, device, deploy, authentication, protocol, 網路, 無線, 裝置, 部署, 驗證, 通訊協定
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.openlocfilehash: 3cb8af88e0aab78d5c1aa7f30c983d1da81216c0
ms.sourcegitcommit: ad08299d14810db746514f01d977a81fc5a3961e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/29/2021
ms.locfileid: "11708744"
---
# <a name="enable-peap-eap-fast-and-cisco-leap-on-surface-devices"></a>在 Surface 裝置上啟用 PEAP、EAP-FAST 和 Cisco LEAP

了解如何讓 Surface 裝置支援 PEAP、EAP-FAST 和 Cisco LEAP 通訊協定。

如果您的企業中使用 PEAP、EAP-FAST 或 Cisco LEAP，您可能已經知道 Surface 裝置並不支援這三種無線驗證通訊協定。 有些使用者可能在嘗試連線到無線網路時發現，有些則可能是在無法存取網路內部資源 (例如檔案共用和內部網站) 時發現。 如需詳細資訊，請參閱[可延伸的驗證通訊協定](/previous-versions/windows/it-pro/windows-xp/bb457039(v=technet.10)?)。

您可以從 USB 或檔案共用執行小型的 MSI 套件來新增對各通訊協定的支援。 針對想要在 Surface 裝置上啟用 EAP 支援的組織，MSI 套件格式支援許多管理和部署工具的部署，例如 Microsoft 部署工具組 (MDT) Microsoft Endpoint Configuration Manager。

## <a name="download-peap-eap-fast-or-cisco-leap-installation-files"></a><a href="" id="download-peap--eap-fast--or-cisco-leap-installation-files--"></a>下載 PEAP、EAP-FAST 或 Cisco LEAP 安裝檔

您可以從 Microsoft 下載中心下載單一的 zip 壓縮檔，其中的 MSI 安裝檔適用於 PEAP、EAP-FAST 或 Cisco LEAP。 若要下載此檔案，請移至 Microsoft 下載中心的[適用於 IT 專業人員的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)頁面，按一下**下載**，然後選取 **Cisco EAP-Supplicant Installer.zip** 檔案。

## <a name="deploy-peap-eap-fast-or-cisco-leap-with-mdt"></a>使用 MDT 部署 PEAP、EAP-FAST 或 Cisco LEAP

如果您的組織中已經針對 Surface 裝置執行 Windows 部署，您就可以快速且輕鬆地將各通訊協定的安裝檔加入部署共用，並於部署期間設定自動安裝。 您甚至可以設定工作順序，使用相同程序來更新先前部署的 Surface 裝置以支援這些通訊協定。

若要在新部署的 Surface 裝置上啟用對 PEAP、EAP-FAST 或 Cisco LEAP 的支援，請按照下列步驟：

1. 下載各通訊協定的安裝檔並解壓縮至位於易存取位置的個別資料夾。

2. 開啟 MDT Deployment Workbench 並展開部署共用至 **\[Applications\] (應用程式)** 資料夾。

3. 從 **\[Action\] (動作)** 窗格選取 **\[New Application\] (新增應用程式)**。

4. 選擇 **\[Application with source files\] (應用程式與來源檔案)** 以將 MSI 檔案複製到部署共用。

5. 選取在步驟 1 時為所需通訊協定建立的資料夾。

6. 為部署共用中將儲存安裝檔的資料夾命名。

7. 指定命令列來部署應用程式：

    - PEAP 使用 **EAP-PEAP.msi /qn /norestart**。

    - LEAP 使用 **EAP-LEAP.msi /qn /norestart**。

    - EAP-FAST 使用 **EAP-FAST.msi /qn /norestart**。

8. 使用預設選項來完成 New Application Wizard (新增應用程式精靈)。

9. 針對各個所需的通訊協定重複步驟 3 至步驟 8。

執行這些步驟將三個 MSI 套件以應用程式的方式匯入 MDT 之後，將可以從 Windows Deployment Wizard (Windows 部署精靈) 的 \[Applications\] (應用程式) 頁面選取它們。 雖然在某些簡單的部署情況下，技術人員只需要在部署時選取每個套件即可，但不建議這麼做。 此做法可能會造成技術人員嘗試將這些套件套用至 Surface 裝置以外的其他電腦，或因人為錯誤而在沒有支援 EAP 的情況下部署 Surface 裝置。

若要在「安裝應用程式」頁面隱藏這些應用程式，請選取各應用程式的 **[在部署精靈中隱藏此應用程式]** 核取方塊。 隱藏應用程式之後，它們就不會在部署期間顯示為選用的應用程式。 若要透過您的 Surface 部署工作順序部署它們，就必須透過工作順序中的個別步驟明確定義它們來加以安裝。

若要明確指定通訊協定，請按照下列步驟執行：

1. 從 MDT Deployment Workbench 開啟 Surface 部署工作順序內容。

2. 在 **\[Task Sequence\] (工作順序)** 索引標籤中，選取 **\[State Restore\] (狀態還原)** 底下的 **\[Install Applications\] (安裝應用程式)**。 通常可以在應用程式安裝前和應用程式安裝後 Windows Update 步驟之間找到。

3. 使用 **\[Add\] (新增)** 按鈕來從 **\[General\] (一般)** 類別建立新的 **\[Install Application\] (安裝應用程式)** 步驟。

4. 在步驟 **\[Properties\] (內容)** 索引標籤中選取 **\[Install a single application\] (安裝單一應用程式)**。

5. 從清單中選取所需的 EAP 通訊協定。

6. 針對各個所需的通訊協定重複步驟 2 至步驟 5。

## <a name="deploy-peap-eap-fast-or-cisco-leap-with-configuration-manager"></a>使用 Configuration Manager 部署 PEAP、EAP-FAST 或 Cisco LEAP

對於使用 Configuration Manager 管理 Surface 裝置的組織而言，部署 PEAP、EAP-FAST 或 Cisco LEAP 甚至更為容易。 只要將每個 MSI 檔案以應用程式的方式從 Software Library 匯入，並對 Surface 裝置集合設定部署即可。

若要瞭解如何使用 Configuration Manager 部署應用程式，請參閱使用 Configuration Manager 建立及部署 [應用程式](/mem/configmgr/apps/get-started/create-and-deploy-an-application.md)。
