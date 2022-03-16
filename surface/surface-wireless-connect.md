---
title: 最佳化 Surface 裝置的 Wi-Fi 連線能力
description: 本主題說明建議Wi-Fi，以確保 Surface 裝置在塞塞的網路環境和行動情境中保持連接。
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
author: coveminer
ms.audience: itpro
ms.localizationpriority: medium
ms.author: greglin
ms.topic: article
ms.reviewer: tokatz
manager: laurawi
ms.date: 11/30/2021
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 2f0aaaff212475887c3cf446709947d4e960c353
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449306"
---
# <a name="optimize-wi-fi-connectivity-on-surface-devices"></a>最佳化 Surface 裝置上的 Wi-Fi 連線能力

為了與全天的電池使用時間保持聯繫，Surface 裝置會採用無線連接設定，以平衡性能和省電。 在最嚴苛的行動能力工作負載之外，使用者可以維持足夠的無線網路連接，而不必修改預設網路介面卡或相關設定。 此頁面會強調使用 Surface 裝置在行動裝置情況下的重要無線連接考慮。

## <a name="prerequisites"></a>必要條件

本檔假設您已成功部署支援 802.11n (Wi-Fi 4) 或更新版本，遵循主要設備廠商的最佳作法建議。

## <a name="configuring-access-points-for-optimal-roaming-capabilities"></a>為優化漫遊功能而建立存取點

假設您正在管理由許多不同類型的用戶端裝置所存取的無線網路。 在這種情況下，建議您在無線局域網中的存取點 (AP) 上啟用特定通訊協定，如使用 [802.11k、802.11v 和 802.11r](/windows-hardware/drivers/network/fast-roaming-with-802-11k--802-11v--and-802-11r)快速漫遊中所述。 Surface 裝置可以利用下列無線通訊協定：

- **802.11r。** 「**快速 BSS 轉場」** 會減少裝置在裝置四處移動時存取另一個 AP 之前所需的框架數目，以加速連接至新的無線存取點。 在自 2019 年發行的新一代 Surface 裝置中，使用者可能會存取其裝置上的漫遊攻擊性設定。 雖然不建議修改預設設定，但使用者應該瞭解這項功能，並瞭解特定設定如何影響他們保持連接的能力。
- **802.11k。** **「鄰近報告」** 會為裝置提供鄰近存取點目前狀況的資訊。 它可協助 Surface 裝置使用訊號強度外的準則來選擇最佳的 AP，例如 AP 使用率。

特定 Surface 裝置也可以使用 802.11v「BSS 轉場管理框架」，其功能與 802.11k 類似，可提供附近候選 AP 的資訊。 這些包括 Surface Pro 8、Surface Pro 7+、Surface Laptop Studio、Surface Go 3、Surface Go 2、Surface Go、Surface Pro 7、Surface Pro X 和 Surface Laptop 3。

## <a name="managing-user-settings"></a>管理使用者設定

您可以透過設計良好的網路，在所有存取點支援 802.11r 和 802.11k，達到最佳的漫遊功能。 與管理個別裝置上的使用者設定相比，建議的方法是確保您的網路經過適當設定，為使用者提供最佳的無線體驗。

### <a name="recommended-user-settings-and-best-practices"></a>建議的使用者設定和最佳做法

在某些情況下，修改 Surface 裝置內建的進一步網路介面卡設定可能會促進更可靠的連接。 不過，請記住，由於存取點問題、網路設計瑕疵或環境網站問題，無法連到無線資源通常較為頻繁。

> [!TIP]
> 您按住手機或 Surface Go Surface Pro也會影響訊號強度。 如果您遇到頻寬遺失的問題，請檢查您並未按住顯示畫面頂端 ，因為Wi-Fi的收音器所在的位置。 雖然按住顯示器頂端不會封鎖無線訊號，但可以觸發裝置驅動程式來啟動降低連線性變更。

### <a name="keep-default-auto-setting-for-dual-bandwidth-capability"></a>保留雙頻寬功能的預設自動設定

在大多數 Surface 裝置上，您可以將用戶端網路介面卡設定為只連接到超過 5 GbHz (GHz) 的無線 AP、僅連接超過 2.4 GHz，或讓作業系統選擇最佳選項 (預設自動設定) 。

**若要存取網路介面卡設定，請前往：**

- **開始**  > ** **  >  控制台**網路和共用中心**  > **您的Wi-Fi配接器**  > **性能**  > **配置**  > **進位**。

![* wifi-band 設定*。](images/wifi-band.png) <br>

請記住，2.4 GHz 比 5 GHz 有一些優點：它更進一步且更容易穿透牆面或其他實心物件。 除非您有明確的使用案例可以連接到 5 GHz，否則建議您將 Band 設定保留為預設狀態，以避免可能的不良後果。 例如：

- 許多位於旅館、咖啡店和機場的熱點仍然只能使用 2.4 GHz，如果 Band 設為 5 GHz，則有效地封鎖裝置存取。
- 由於Miracast顯示連接需要在 2.4 GHz 通道上完成初始握手，因此裝置無法僅以 5 GHz 進行連接。

> [!NOTE]
> 根據預設，Surface 裝置會偏好使用 5 GHz 連接 。如果可用。 不過，Surface 會先尋找 2.4 GHz 連接，以在低電池狀態中維持電力。

您也可以根據環境需要切換頻帶設定。 例如，居住在具有多個 Wi-Fi 熱點的高層住宅大樓的使用者 ，在消費者裝置全部透過 2.4 GHz 廣播的情況下，將 Surface 裝置設定為僅以 5 GHz 連接，然後視需要還原為自動，可能會帶來好處。

### <a name="roaming-aggressiveness-settings-on-surface-devices-with-intel-adapters"></a>使用 Intel 介面卡在 Surface 裝置上漫遊攻擊性設定

使用者可能會想要選取一個訊號強度閾值，當訊號在漫遊攻擊性降低時，提示裝置 (新的) 。 根據預設，如果訊號強度低於 72 **% (，** 具有 Intel 介面卡的 Surface 裝置會嘗試漫遊到新的) 。 如本頁稍早所述，組織也可以跨多個網路存取點執行專為使用者打造的無線通訊協定，以促進漫遊塞塞網路環境。

在高度塞塞的辦公室或**** 住宅環境中增加漫遊攻擊性可能會改善高度塞塞的辦公室或居住環境中的連線性，但當超出這些環境時，可能會導致連接品質降低。

除非您在特定的行動情境中遇到連接問題，例如執行環境網站檢查，同時在會議期間維護語音和視音訊連接，否則請保持預設狀態中的漫遊攻擊性設定。 如果您沒注意到有任何改進，請還原為預設的中態。 請注意，如果您增加漫遊攻擊性，也會加速電池電力消耗。

**若要在 Surface 上啟用漫遊攻擊性：**

1. 前往**StartDevice** ** **  >  Manager。
2. 在 **[網路介面卡Wi-Fi**中，選取 [ **Intel Wi-Fi 6** ，然後以滑鼠右鍵按一下 **[屬性**。
3. 選取進 **一頁** 的定位停駐點。
4. 選取 **漫遊攻擊性** ，然後從下拉式功能表選擇您的偏好值。

![* 漫遊攻擊性設定-Intel *。](images/wifi-roaming-int.png) <br>

### <a name="roaming-aggressiveness-settings-on-surface-go-and-surface-pro-x"></a>Surface Go 和 x 上的漫遊攻擊Surface Pro設定

使用 Surface Go 的前線工作人員可能會想要選取一個訊號強度閾值，當訊號強度降低或漫遊攻擊性降低時，提示裝置 (新的) 。 根據預設，如果訊號強度低於 50 **% (，** Surface 裝置會嘗試漫遊到新的) 。 請注意，每當您增加漫遊攻擊性時，就會加速電池電力消耗。

除非您在特定的行動情境中遇到連接問題，例如執行環境網站檢查，同時在會議期間維護語音和視音訊連接，否則請保持預設狀態中的漫遊攻擊性設定。 如果您沒注意到有任何改善，會還原為預設的中 **態** 。

**若要在 Surface Go 上啟用漫遊攻擊性：**

1. 請前往**控制台>**  >  **和 InternetNetwork**  >  **與共享中心開始作業。**
2. 在 **連結下**，選取 **Wi-Fi** ，然後選擇屬性 **。**
3. 選取 **Microsoft Networks 的用戶端** ， **然後選取設定**
4. 選取**進**  >  **位攻擊性**，然後從下拉式功能表選擇您的偏好值。

![* 漫遊攻擊性設定-QualComm *。](images/wifi-roaming.png) <br>

## <a name="conclusion"></a>總結

Surface 裝置在設計時採用預設設定，以在保持電池使用時間需求時，平衡最佳的無線連線性。 為 Surface 裝置啟用可靠連接最有效的方法，就是透過設計良好的網路，支援 802.11r 和 802.11k。 使用者可以調整網路介面卡設定或漫遊攻擊性，但只應因應特定環境因素而調整，如果沒有任何明顯改善，則應該還原為預設狀態。
