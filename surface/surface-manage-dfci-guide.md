---
title: Surface UEFI 設定的 Intune 管理
description: 本文說明如何在 Microsoft Intune 中設定 DFCI 環境，以及如何管理目標 Surface 裝置的固件設定。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 10/09/2020
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
ms.openlocfilehash: e984741a8367935eab18351815c5f00d9f8a72b7
ms.sourcegitcommit: efc38524f81238e0c36371f462eb57123e46d09b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/15/2020
ms.locfileid: "11228544"
---
# Surface UEFI 設定的 Intune 管理

## 簡介

從雲端管理裝置的能力在整個生命週期中大大簡化 IT 部署與資源調配。 使用 Device 固件配置介面 (DFCI 在 [Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)內建的) 設定檔，Surface UEFI 管理會將新式管理堆疊延伸到 UEFI 硬體層級。 DFCI 支援零觸控配，消除 BIOS 密碼，提供安全性設定（包括啟動選項和內建週邊設備）的控制權，並針對未來的高級安全性案例奠定基礎。 如需常見問題的解答，請參閱 [Ignite 2019：宣佈從 Intune 遠端系統管理 SURFACE UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)。

### 背景

就像任何執行 Windows 10 的電腦一樣，Surface 裝置都依賴儲存在 SoC 中的程式碼，讓 CPU 能夠與硬碟進行介面、顯示裝置、USB 埠及其他裝置。 儲存在這個唯讀記憶體 (ROM) 中的程式稱為固件 (，而儲存在動態媒體中的程式稱為軟體) 。

與目前市場上提供的其他 Windows 10 裝置相比，Surface 提供 IT 管理員能夠透過一組豐富的 UEFI 設定設定來設定及管理固件。 這會在軟體基礎上提供一層硬體控制，因為它是透過行動裝置管理 (MDM) 原則、Configuration Manager 或群組原則來實現。 例如，在高度安全的區域中部署含機密資訊的裝置，可以移除硬體層級的功能，以避免相機的使用。 從裝置的角度來看，透過固件設定將攝像頭關閉，相當於實際移除相機。 比較在固件層級管理所增加的安全性，只依賴作業系統軟體設定。 例如，如果您透過網域環境中的原則設定停用 Windows 音訊服務，本機管理員仍可重新啟用服務。

### DFCI 與 SEMM

先前，管理固件所需的註冊裝置在 Surface Enterprise 管理模式中 (SEMM) 與持續進行手動 IT 密集型任務的額外負荷。 例如，SEMM 需要 IT 員工以實際方式存取每個電腦，以在證書管理程式中輸入兩位數的 pin。 雖然 SEMM 對於嚴格內部部署環境中的組織而言是一個不錯的解決方案，但其複雜性和 IT 密集型需求都能讓使用成本變得非常昂貴。

 使用 Microsoft Intune 中的整合 UEFI 固件管理功能，可簡化並更輕鬆地使用在單一主控台中進行提供、安全性和精簡更新的新功能，讓您可以更輕鬆地使用鎖定硬體的功能，現在已與 [Microsoft 端點管理員](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)進行整合。 下圖顯示直接在裝置上 (left) 中查看，以及在端點管理員主控台中查看 (右側) 的 UEFI 設定。

![在裝置上顯示的 UEFI 設定 (left) ，而在端點管理員主控台中則 (右側) ](images/uefidfci.png)

Crucially、DFCI 啟用零觸控管理，不需要 IT 系統管理員手動互動。 DFCI 是透過 Windows Autopilot 使用 Intune 中的裝置設定檔功能來部署。 裝置設定檔可讓您新增並設定設定，然後將這些設定部署至在組織內註冊管理的裝置。 裝置收到裝置設定檔之後，就會自動套用這些功能與設定。 常見裝置設定檔的範例包括電子郵件、裝置限制、VPN、Wi-fi 和管理範本。 DFCI 只是一個額外的裝置設定檔，可讓您從雲端管理 UEFI 配置設定，而不必維護內部部署基礎結構。  

## 支援的裝置

下列裝置支援 DFCI：

- Surface Pro 7
- Surface Pro X
- Surface 膝上型電腦3
- Surface Book 3
- Surface 膝上型電腦前往

> [!NOTE]
> Surface Pro X 不支援內建相機、音訊和 Wi-fi/藍牙的 DFCI 設定管理。

## 必要條件

- 裝置必須由 [Microsoft 雲端解決方案提供者](https://partner.microsoft.com/membership/cloud-solution-provider) 在 Windows Autopilot 中註冊， (CSP) 夥伴或 OEM 分發伺服器。

- 在設定 Surface 的 DFCI 之前，您應該熟悉  [Microsoft Intune](https://docs.microsoft.com/intune/) 中的 Autopilot 設定需求以及 [azure Active DIRECTORY](https://docs.microsoft.com/azure/active-directory/) (azure AD) 。

## 開始之前

將您的目標 Surface 裝置新增至 Azure AD 安全性群組。 如需有關建立及管理安全性群組的詳細資訊，請參閱 [Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。

## 設定 Surface 裝置的 DFCI 管理

DFCI 環境需要設定包含設定的 DFCI 設定檔，以及將設定套用到已註冊裝置的 Autopilot 設定檔。 建議使用註冊狀態設定檔，以確保在使用者第一次啟動裝置時，在 OOBE 設定期間將設定推向下。 本指南說明如何設定 DFCI 環境，以及如何管理目標 Surface 裝置的 UEFI 配置設定。

## 建立 DFCI 設定檔

在設定 DFCI 原則設定之前，請先建立 DFCI 設定檔，然後將它指派給包含您目標裝置的 Azure AD 安全性群組。

1. 在 devicemanagement.microsoft.com 登入您的租使用者。
2. 在 Microsoft 端點管理員系統管理中心，選取 [ **裝置] > 配置設定檔] > [建立配置** 檔]，然後輸入名稱;例如， **DFCI [配置原則]。**
3. 針對 [平臺類型] 選取 [ **Windows 10 及更新版本** ]。
4. 在 [配置檔案類型] 下拉式清單中，選取 [ **裝置固件配置介面** ] 來開啟包含所有可用原則設定的 DFCI blade。 如需 DFCI 設定的詳細資訊，請參閱此頁面上的資料表1或 [Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。 您可以在初始安裝程式期間設定 DFCI 設定，或在稍後編輯 DFCI 設定檔。

    ![建立 DFCI 設定檔](images/df1.png)

5. 按一下 **[確定]** ，然後選取 [ **建立**]。
6. 選取 [ **作業** ]，然後在 [ **選取要包含的群組** ] 底下，選取包含您目標裝置的 Azure AD 安全性群組，如下圖所示。 按一下 **[儲存]**。

    ![指派安全性群組](images/df2a.png)

## 建立 Autopilot 設定檔

1. 在 devicemanagement.microsoft.com 的端點管理員中，選取 [ **裝置] > Windows 註冊** ，然後向下滾動至 [ **部署設定檔**]。
2. 選取 [ **建立設定檔** ]，然後輸入名稱;例如， **我的 Autopilot 設定檔**，然後選取 **[下一步]**。
3. 選取下列設定：

    - 部署模式： **使用者導向**。
    - 加入類型： Azure **AD 已加入**。

4. 將剩餘的預設設定保持不變，然後選取 **[下一步]**，如下圖所示。

    ![建立 Autopilot 設定檔](images/df3b.png)

5. 在 [作業] 頁面上，選擇 [ **選取要包含的群組** ]，然後按一下您的 Azure AD 安全性群組。 選取 **\[下一步\]**。
6. 接受摘要，然後選取 [ **建立**]。 Autopilot 設定檔隨即會建立並指派給群組。

## [設定註冊狀態] 頁面

為了確保裝置在使用者登入時在 OOBE 期間套用 DFCI 設定，您必須設定註冊狀態。

如需詳細資訊，請參閱 [設定 [註冊狀態] 頁面](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。


## 在 Surface 裝置上設定 DFCI 設定

DFCI 包含一組經過簡化的 UEFI 配置原則，可在硬體層級鎖定裝置，提供額外的安全性。 DFCI 的設計目的是與軟體層級的行動裝置管理設定搭配使用。 請注意，[DFCI 設定] 只會影響已內建到 Surface 裝置的硬體元件，且不會延伸到連接的外設（例如 USB 網路攝影機）。  (不過，您可以在 Intune 中使用裝置限制原則，關閉軟體層級) 的已連接外設的存取權。

您可以從端點管理員編輯 DFCI 設定檔，以設定 DFCI 原則設定，如下圖所示。 

- 在 devicemanagement.microsoft.com 的 [端點管理員] 中，選取 **[裝置] > Windows > 設定設定檔 > 「DFCI profile name」 > 屬性 > 設定**。

    ![設定 DFCI 設定](images/dfciconfig.png)

### 封鎖使用者對 UEFI 設定的存取權

對於許多客戶而言，封鎖使用者變更 UEFI 設定的能力至關重要，且主要是使用 DFCI 的理由。 如資料表1所列，這是透過設定 [ **允許本機使用者變更 UEFI 設定**] 來管理。 如果您沒有編輯或設定此設定，本機使用者將能夠變更任何不由 Intune 管理的 UEFI 設定。 因此，強烈建議您停用 [ **允許本機使用者變更 UEFI 設定]。**
其餘的 [DFCI] 設定可讓您關閉其他使用者可以使用的功能。 例如，如果您需要在高度安全的區域中保護機密資訊，您可以停用相機，如果不想讓使用者從 USB 磁片磁碟機啟動，您也可以停用。

### 表 1. DFCI 案例

| 裝置管理目標                        | 設定步驟                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 封鎖本機使用者變更 UEFI 設定 | 在 [ **安全性功能] 底下 > [允許本機使用者變更 UEFI 設定**] 底下，選取 [ **無**]。              |
| 停用相機                               | 在 [ **內置於硬體 > 相機**] 底下，選取 [ **停用**]。                                       |
| 停用麥克風和喇叭              | 在 [ **內置於硬體 > 麥克風和喇叭**] 底下，選取 [ **停用**]。                      |
| 停用無線電 (藍牙、Wi-fi)              | 在 [ **內置硬體 > 無線功能] 底下 (藍牙、wi-fi 等 ... ) **，請選取 [ **停用**]。                   |
| 停用從外部媒體啟動 (USB、SD)     | 在 [ **內置於硬體 > 啟動選項] 底下 > 從外部媒體 (USB、SD) **，請選取 [ **停用**]。 |

> [!CAUTION]
> **停用無線電 (藍牙、wi-fi) **設定，只應該在具備有線乙太網連線的裝置上使用。
 
> [!NOTE]
>  Intune 中的 DFCI 包含兩個目前不適用於 Surface 裝置的設定： (1) CPU 和 IO 虛擬化， (2) 停用網路介面卡的啟動。
 
Intune 提供作用中標籤來委派管理權利和適用性規則來管理裝置類型。 如需有關原則管理支援的詳細資訊，以及所有 DFCI 設定的完整詳細資訊，請參閱 [Microsoft Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。

## 在 Autopilot 中註冊裝置

如上述所述，DFCI 只能套用在由您的轉銷商或分銷商在 Windows Autopilot 中註冊的裝置上，而且目前僅支援（在 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3）。 基於安全性的考慮，您無法將裝置「自行提供」 Autopilot。

## 手動同步處理 Autopilot 裝置

雖然 Intune 原則設定通常會立即套用，但在目標裝置上設定會生效，可能會有10分鐘的延遲。 在極少數情況下，可能會延遲長達8小時。 若要盡可能儘快套用設定，請 (例如在測試案例) 中，您可以手動同步處理目標裝置。

- 在 devicemanagement.microsoft.com 的 [端點管理員] 中，移至 [裝置] **> 裝置註冊 > windows 註冊 > Windows Autopilot 裝置** ，然後選取 [ **同步**處理]。

 如需詳細資訊，請參閱 [手動同步處理您的 Windows 裝置](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。

> [!NOTE]
> 在 UEFI 中直接調整設定時，您必須確保裝置完全重新開機至標準的 Windows 登入。

## 在 DFCI 管理的裝置上驗證 UEFI 設定

在測試環境中，您可以驗證 Surface UEFI 介面中的設定。

1. [開啟 Surface UEFI]，其中包括同步選取 [ **音量 +** ] 和 [ **電源** ] 按鈕。
2. 選取 [ **裝置**]。 UEFI 功能表會反映已設定的設定，如下圖所示。

    ![Surface UEFI](images/df3.png)

    注意做法：

      - 這些設定會呈現灰色，因為 [ **允許本機使用者變更 UEFI] 設定** 為 [無]。
      - 因為 **麥克風和喇叭** 設定為 [ **停用**]，所以音訊已設定為 [關閉]。

## 移除 DFCI 原則設定

當您建立 DFCI 設定檔時，所有設定的設定都會在設定檔的管理範圍內的所有裝置上保持生效。 您只能透過直接編輯 DFCI 設定檔來移除 DFCI 原則設定。

如果原始的 DFCI 設定檔已遭刪除，您可以建立新的設定檔，然後視需要編輯設定，以移除原則設定。

## 移除 DFCI 管理

**若要移除 DFCI 管理，並將裝置傳回工廠新狀態：**

1. 從 Intune 停用裝置：
    1. 在 devicemanagement.microsoft.com 的 [端點管理員] 中，選擇 [ **群組 > 所有裝置**]。 選取您要撤出的裝置，然後選擇 [ **停用/清除]。** 若要深入瞭解，請參閱 [使用 [擦除]、[停用] 或 [手動 unenrolling 裝置] 來移除裝置](https://docs.microsoft.com/intune/remote-actions/devices-wipe)。 
2. 從 Intune 刪除 Autopilot 註冊：
    1.  選擇 [ **裝置註冊] > Windows 註冊 > 裝置**]。
    2. 在 [Windows Autopilot 裝置] 下，選擇您要刪除的裝置，然後選擇 [ **刪除**]。
3. 使用 Surface 品牌乙太網卡將裝置連線至有線網際網路。 重新開機裝置，然後開啟 [UEFI] 功能表 (按住音量按鈕，同步選取並放開電源按鈕) 。
4. 選取 [ **管理] > 設定 [從網路 >** 重新整理]，然後選擇 [ **退出]。**

若要繼續使用 Intune 管理裝置，但不 DFCI 管理，請自行註冊裝置以 Autopilot 並將它註冊至 Intune。 DFCI 將不會套用到自行註冊的裝置。

## 深入了解
- [Ignite 2019：宣佈從 Intune 進行 SURFACE UEFI 設定的遠端系統管理](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 與 Surface 裝置](windows-autopilot-and-surface-devices.md) 
- [在 Microsoft Intune 中使用 Windows 裝置上的 DFCI 設定檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
