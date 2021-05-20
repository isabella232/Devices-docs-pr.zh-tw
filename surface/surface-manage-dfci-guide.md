---
title: Surface UEFI 設定的 Intune 管理
description: 本文將說明如何在 Microsoft Intune 中設定 DFCI 環境，以及管理目標 Surface 裝置的固件設定。
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 04/13/2021
ms.reviewer: jesko
manager: laurawi
ms.audience: itpro
appliesto:
- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop Go
- Surface Laptop 4
ms.openlocfilehash: b74aeab45dd2354550f0dff712af5b37b853111c
ms.sourcegitcommit: a4f8d271b1372321c3b45fc5a7a29703976964a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2021
ms.locfileid: "11576513"
---
# <a name="intune-management-of-surface-uefi-settings"></a>Surface UEFI 設定的 Intune 管理

## <a name="introduction"></a>簡介

從雲端管理裝置的能力大幅簡化了整個生命週期的 IT 部署和部署。 Surface UEFI 管理 (DFCI) 內建的[DFCI](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)Microsoft Intune 設定檔，將新式管理堆疊延伸至 UEFI 硬體層級。 DFCI 支援零接觸式設定、消除BIOS 密碼、提供安全性設定控制，包括開機選項和內建的周邊設備，以及為日後進一步的安全性案例打下基礎。 有關常見問題的解答，請參閱 [Ignite 2019：宣佈從 Intune](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333)遠端系統管理 Surface UEFI 設定。

### <a name="background"></a>背景

如同執行Windows 10，Surface 裝置會仰賴儲存在 SoC 中的程式碼，讓 CPU 能夠與硬碟、顯示裝置、USB 埠及其他裝置進行介面。 儲存在此唯讀記憶體中的程式 (ROM) 稱為 (，而儲存在動態媒體中的程式稱為軟體) 。

與現今市Windows 10的其他裝置不同，Surface 提供 IT 系統管理員透過豐富的 UEFI 設定設定集來設定及管理固件的能力。 這會在軟體型策略管理上提供一層硬體控制，透過行動裝置管理或 MDM (、Configuration Manager 或組) 策略來執行。 例如，將裝置部署在具有敏感性資訊的高度安全區域的組織，可以移除硬體層級的功能，以防止相機使用。 從裝置角度而言，透過固件設定關閉相機相當於實際移除相機。 比較新增的在固件層級管理的安全性，只仰賴作業系統軟體設定。 例如，如果您透過網域Windows設定停用音訊服務，則當地系統管理員仍可重新啟用服務。

### <a name="dfci-versus-semm"></a>DFCI 與 SEMM

之前，管理固件時，需要將裝置註冊到 Surface Enterprise管理模式 (SEMM) ，而需要持續進行大量手動 IT 工作。 例如，SEMM 要求 IT 員工以實體方式存取每部電腦，才能在憑證管理程式過程中輸入兩位數的圖釘。 雖然 SEMM 仍然是嚴格內部部署環境中組織的良好解決方案，但其複雜度和 IT 需求高，因此使用成本高。

 有了 Microsoft Intune 中整合的 UEFI 固件管理功能，鎖定硬體的功能變得簡單且更容易與新功能一起使用，以在單一主機中進行部署、安全性和簡化更新，現在統一為[Microsoft 端點管理員。](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 下圖顯示直接在裝置上的 UEFI 設定 (左) ，端點管理員主控台 (右) 。

![裝置上顯示的 UEFI 設定 (左) ，端點管理員主控台 (右) ](images/uefidfci.png)

最重要的是，DFCI 可啟用零觸控管理，而不需要 IT 系統管理員手動互動。 使用 Intune 中的裝置設定檔功能，Windows Autopilot 部署 DFCI。 裝置設定檔可讓您新增和設定設定，然後部署至您組織中註冊管理中的裝置。 一旦裝置收到裝置設定檔，就會自動應用功能和設定。 常見的裝置設定檔範例包括電子郵件、裝置限制、VPN、Wi-Fi 及系統管理範本。 DFCI 只是額外的裝置設定檔，可讓您從雲端管理 UEFI 設定設定，而不需要維護內部部署基礎結構。  

## <a name="supported-devices"></a>支援的裝置

下列裝置支援 DFCI：

- Surface Pro 7+
- Surface Pro 7
- Surface Pro X
- Surface Laptop 3
- Surface Book 3
- Surface Laptop去
- Surface Laptop 4

> [!NOTE]
> Surface ProX 不支援內建相機、音訊和 Wi-Fi/藍牙。

## <a name="prerequisites"></a>必要條件

- 裝置必須由合作夥伴或 OEM Windows[的 CSP](https://partner.microsoft.com/membership/cloud-solution-provider) Microsoft 雲端解決方案提供者 (在 Autopilot) 註冊。

- 在針對 Surface 配置 DFCI 之前，您應該先熟悉 Microsoft Intune 和[](https://docs.microsoft.com/intune/)Azure Active Directory (Azure [](https://docs.microsoft.com/azure/active-directory/) AD) 。

## <a name="before-you-begin"></a>開始之前

將目標 Surface 裝置新增到 Azure AD 安全性群組。 有關建立及管理安全性群組的資訊，請參閱 [Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows#create-your-azure-ad-security-groups)。

## <a name="configure-dfci-management-for-surface-devices"></a>設定 Surface 裝置 DFCI 管理

DFCI 環境需要設定包含設定和 Autopilot 設定檔的 DFCI 設定檔，以將設定適用于已註冊的裝置。 此外，建議使用註冊狀態設定檔，以確保使用者第一次啟動裝置時，在 OOBE 設定期間將設定向下推入。 本指南說明如何設定 DFCI 環境，以及管理目標 Surface 裝置之 UEFI 設定設定。

## <a name="create-dfci-profile"></a>建立 DFCI 設定檔

設定 DFCI 策略設定之前，先建立 DFCI 設定檔，並將其指派給包含您目標裝置之 Azure AD 安全性群組。

1. 請于您的租使用者 devicemanagement.microsoft.com。
2. 在系統管理Microsoft 端點管理員中，選取 >**設定檔**的裝置>建立設定檔並輸入名稱;例如 **，DFCI 群組原則。**
3. 選取**Windows 10及稍後**的平臺類型。
4. 在配置檔案類型下拉式清單中，選取 **裝置固件設定介面** 以開啟包含所有可用策略設定之 DFCI 邊欄選項卡。 有關 DFCI 設定的資訊，請參閱此頁面的表格 1 或 [Intune 檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。 您可以在初始設定程式或稍後編輯 DFCI 設定檔時設定 DFCI 設定。

    ![建立 DFCI 設定檔](images/df1.png)

5. 按一下 **[確定** ，然後選取 **[建立**> 。
6. 選取 **作業** ，在選取 **群組下選取** 包含您目標裝置之 Azure AD 安全性群組，如下圖所示。 按一下 [儲存]****。

    ![指派安全性群組](images/df2a.png)

## <a name="create-autopilot-profile"></a>建立 Autopilot 設定檔

1. 在 端點管理員的 devicemanagement.microsoft.com，選取 **> Windows的裝置**，然後向下卷起至**部署設定檔**。
2. 選取 **建立設定檔** 並輸入名稱;例如，我的 **Autopilot 設定檔**，然後選取 下 **一步**。
3. 選取下列設定：

    - 部署模式： **使用者導向**。
    - 加入類型：已加入**Azure AD。**

4. 將其餘的預設設定維持不變， **然後選取下**一步，如下圖所示。

    ![建立 Autopilot 設定檔](images/df3b.png)

5. 在 [作業」 頁面上，選擇 **[選取要** 包含的群組，然後按一下您的 Azure AD 安全性群組。 選取 **[下一步]**。
6. 接受摘要， **然後選取建立**。 Autopilot 設定檔現在已建立並指派給群組。

## <a name="configure-enrollment-status-page"></a>設定註冊狀態頁面

若要在使用者登錄前，確保裝置在 OOBE 期間適用 DFCI 設定，您必須設定註冊狀態。

若要詳細資訊，請參閱 [設定註冊狀態頁面](https://docs.microsoft.com/intune/enrollment/windows-enrollment-status)。


## <a name="configure-dfci-settings-on-surface-devices"></a>在 Surface 裝置上設定 DFCI 設定

DFCI 包含一組簡化的 UEFI 設定策略，可鎖定硬體層級的裝置，提供額外的安全性等級。 DFCI 是設計用來與軟體層級的行動裝置管理設定一起使用。 請注意，DFCI 設定只會影響 Surface 裝置內建的硬體元件，不會延伸到 USB 網路網路等附加的周邊。  (不過，您可以使用 Intune 中的裝置限制政策，在軟體層級關閉附加) 。

您可以設定 DFCI 策略設定，從 端點管理員編輯 DFCI 設定檔，如下圖所示。 

- 在 端點管理員的 devicemanagement.microsoft.com 中，選取 > Windows >**設定檔> DFCI 設定檔名稱">屬性**> 設定。

    ![設定 DFCI 設定](images/dfciconfig.png)

### <a name="block-user-access-to-uefi-settings"></a>封鎖使用者對 UEFI 設定的存取權限

對於許多客戶來說，封鎖使用者變更 UEFI 設定的能力至關重要，也是使用 DFCI 的主要理由。 如表格 1 所列，此設定會透過設定允許 **本地使用者變更 UEFI 設定進行管理**。 如果您沒有編輯或設定此設定，則當地使用者將可以變更 Intune 未管理的任何 UEFI 設定。 因此，強烈建議您停用允許 **本地使用者變更 UEFI 設定。**
其餘的 DFCI 設定可讓使用者關閉原本可供使用者使用的功能。 例如，如果您需要保護高度安全區域中的敏感性資訊，您可以停用相機，如果您不希望使用者從 USB 磁片磁碟機啟動，您也可以停用此功能。

### <a name="table-1-dfci-scenarios"></a>表 1. DFCI 案例

| 裝置管理目標                        | 組組步驟                                                                           |
| --------------------------------------------- | --------------------------------------------------------------------------------------------- |
| 封鎖當地使用者變更 UEFI 設定 | 在 **安全性功能>允許本地使用者變更 UEFI 設定**，選取 **無**。              |
| 停用相機                               | 在 **內建硬體>相機**下，選取 已 **停用**。                                       |
| 停用麥克風和喇叭              | 在 **內建硬體>麥克風和喇叭**下，選取 已 **停用**。                      |
| 停用無線 (藍牙、Wi-Fi)              | 在**內建硬體>無線 (藍牙、Wi-Fi**等...) ，選取 已**停用**。                   |
| 停用從外部媒體啟動 (USB、SD)     | 在 **內建硬體>啟動選項> USB、SD ** (從外部媒體啟動) ，選取 已 **停用**。 |

> [!CAUTION]
> 停用**無線 (藍牙 Wi-Fi) **設定只能用於有有線乙太網路連接的裝置。
 
> [!NOTE]
>  Intune 中的 DFCI 包含兩個目前不適用於 Surface 裝置設定： (1) CPU 和 IO 虛擬化，以及 (2) 從網路介面卡停用開機。
 
Intune 提供範圍標記以委派系統管理許可權和適用規則來管理裝置類型。 有關策略管理支援的詳細資訊，以及所有 DFCI 設定的完整詳細資料，請參閱Microsoft Intune[檔](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)。

## <a name="register-devices-in-autopilot"></a>在 Autopilot 中註冊裝置

如上所述，DFCI 僅適用于轉銷商或轉銷商在 Windows Autopilot 註冊的裝置，且僅支援 Surface Pro 7+、Surface Laptop Go、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。 基於安全性考慮，您無法將裝置「自我布供」到 Autopilot。 若要深入瞭解，請參閱適用于[Autopilot](surface-autopilot-registration-support.md)Windows Surface 註冊支援 。 

## <a name="manually-sync-autopilot-devices"></a>手動同步處理自動駕駛裝置

雖然 Intune 原則設定通常幾乎會立即採用，但設定在目標裝置上生效之前，可能會延遲 10 分鐘。 在少數情況下，最多可能會延遲 8 小時。 若要確保設定儘快適用， (例如測試案例) ，您可以手動同步處理目標裝置。

- 在 端點管理員的 devicemanagement.microsoft.com，請前往 > 裝置註冊> Windows自動> Windows裝置，然後選取**同步** **。**

 若要詳細資訊，請參閱手動[同步Windows同步處理您的裝置](https://docs.microsoft.com/intune-user-help/sync-your-device-manually-windows)。

> [!NOTE]
> 當直接在 UEFI 中調整設定時，您必須確保裝置完全重新開機至標準Windows登入。

## <a name="verifying-uefi-settings-on-dfci-managed-devices"></a>驗證 DFCI 管理的裝置上的 UEFI 設定

在測試環境中，您可以在 Surface UEFI 介面中驗證設定。

1. 開啟 Surface UEFI，這涉及同時按 **音量 +** 和 **Power** 按鈕。
2. 選取 **裝置**。 如下圖所示，UEFI 功能表會反映設定。

    ![Surface UEFI](images/df3.png)

    請注意如何：

      - 設定會以灰色顯示，因為允許 **本地使用者變更 UEFI 設定** 設為無。
      - 音訊已設為關閉， **因為麥克風和喇** 叭設定為 **已停用**。

## <a name="removing-dfci-policy-settings"></a>移除 DFCI 策略設定

當您建立 DFCI 設定檔時，所有設定都會在設定檔管理範圍內的所有裝置上維持有效。 您只要直接編輯 DFCI 設定檔，才能移除 DFCI 策略設定。

如果原始 DFCI 設定檔已刪除，您可以建立新設定檔，然後編輯設定來移除策略設定。

## <a name="removing-dfci-management"></a>移除 DFCI 管理

**若要移除 DFCI 管理，將裝置返回出廠新狀態：**

1. 從 Intune 淘汰裝置：
    1. 在 端點管理員的 devicemanagement.microsoft.com，選擇 >**所有裝置 。** 選取您想要淘汰的裝置，然後選擇淘汰 **/抹掉。** 若要深入瞭解，請參閱使用 [抹除、](https://docs.microsoft.com/intune/remote-actions/devices-wipe)淘汰或手動取消註冊裝置來移除裝置。 
2. 從 Intune 刪除 Autopilot 註冊：
    1.  選擇**裝置註冊> Windows註冊>裝置**。
    2. 在 Windows Autopilot 裝置下，選擇您想要刪除的裝置，**然後選擇刪除**。
3. 連線 Surface 品牌乙太網路介面卡將裝置連接到有線網際網路。 重新開機裝置並開啟 UEFI 功能表 (按住放大按鈕，同時按並放開電源按鈕) 。
4. 選取 **管理>從>重新設定** ，然後選擇 **退出宣告。**

若要使用 Intune 持續管理裝置，但不需要 DFCI 管理，請自行將裝置註冊至 Autopilot，然後註冊至 Intune。 DFCI 不會用於自我註冊的裝置。

## <a name="learn-more"></a>深入了解
- [Ignite 2019：宣佈從 Intune 遠端系統管理 Surface UEFI 設定](https://techcommunity.microsoft.com/t5/Surface-IT-Pro-Blog/Ignite-2019-Announcing-remote-management-of-Surface-UEFI/ba-p/978333) 
[Windows Autopilot](https://www.microsoft.com/microsoft-365/windows/windows-autopilot)
- [Windows Autopilot 與 Surface 裝置](windows-autopilot-and-surface-devices.md) 
- [在 Windows 裝置上使用 DFCI 設定檔Microsoft Intune](https://docs.microsoft.com/intune/configuration/device-firmware-configuration-interface-windows)
