---
title: 初次執行程式 (Surface Hub)
description: 「初次執行」一詞是指當您第一次開啟 Microsoft Surface Hub 的電源時即將逐步執行的一系列步驟，而其意味著與「全新體驗」(OOBE) 相同的動作。 本節將帶領您逐步完成此程序。
ms.assetid: 07C9E84C-1245-4511-B3B3-75939AD57C49
ms.reviewer: ''
manager: laurawi
keywords: 第一次執行, Surface Hub, 全新體驗, OOBE
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 10/27/2020
ms.localizationpriority: medium
ms.openlocfilehash: e070c28d13cd8466bff47022f4508fdb8aa06331
ms.sourcegitcommit: 19d2a78242777590bd09af3ac6552c07b032e0a1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/27/2020
ms.locfileid: "11142912"
---
# 初次執行程式 (Surface Hub)


「初次執行」一詞是指當您第一次開啟 Microsoft Surface Hub 的電源時將逐步執行的一系列步驟，而其意味著與「全新體驗」(OOBE) 相同的動作。 本節將帶領您逐步完成此程序。

現在，您應該已經完成所有先前的步驟：

-   [針對 Surface Hub 準備您的環境](prepare-your-environment-for-surface-hub.md)
-   [實際安裝 Surface Hub 裝置](physically-install-your-surface-hub-device.md)，以及
-   [設定工作表](setup-worksheet-surface-hub.md)

假設符合上述情況，則初次執行應該是簡單且快速的。
一般的程序會執行六個步驟：

1.  [[嗨，您好] 頁面](#first-page)
2.  [[為您進行設定] 頁面](#set-up-for-you)
3.  [[裝置帳戶] 頁面](#device-account)
4.  [[請為此裝置命名] 頁面](#name-this-device)
5.  [[設定此裝置的系統管理員] 頁面](#setup-admins)
6.  [更新 Surface Hub](#update-surface-hub)

這些小節中的每一節也會包含當某些情況不同時您可能要採取的路徑相關資訊。 例如，大部分的 Surface Hub 將使用有線網路連線，但其中有一些將改用無線來設定。 詳細資料將會在適當時機加以說明。

>[!NOTE]
>注意：開始之前，您應該使用 Surface Hub 隨附的另一個鍵盤進行安裝和準備。 如需詳細資訊，請參閱＜Surface Hub 設定指南＞。

 

## <a href="" id="first-page"></a>[嗨，您好] 頁面


這是您第一次開啟 Surface Hub 的電源時所看見的第一個畫面。 您可以在此處為裝置輸入當地語系化資訊。

>[!NOTE]
>這也是您開始部署佈建套件選用程序的地方。 如果您正在執行此動作，請參閱[建立佈建套件](provisioning-packages-for-certificates-surface-hub.md)。

 選擇語言，便會顯示初始設定選項。

![顯示 ICD 選項檢查清單的影像](images/setuplocale.png)

### 詳細資料

如果顯示的預設值正確，則您可以按 **\[下一步\]** 繼續。 否則，您需要在適當的方塊中輸入資料。

-   **國家/地區：** 選取將使用 Surface Hub 的國家或地區。
-   **應用程式語言：** 應用程式與功能將使用此語言和語言格式來顯示。
-   **鍵盤配置：** 針對將與裝置搭配使用的螢幕小鍵盤和實體鍵盤，選取鍵盤配置。
-   **時區：** 選擇將使用 Surface Hub 的時區。

### 發生什麼事？

>[!NOTE]
> 只要輸入了本頁面的設定後，除非重設裝置，否則無法回到此畫面 (請參閱 [裝置重設](device-reset-surface-hub.md))。 繼續之前，請確定已進行適當設定。

 

接受設定時，裝置將檢查有線網路連線。 如果連線良好，即會顯示 [[為您進行設定] 頁面](#set-up-for-you)。 如果有線連線發生問題，裝置將顯示 [[網路設定] 頁面](#network-setup)。

如果找不到有線連線，則裝置將嘗試設定無線連線，並顯示 [[網路設定] 頁面](#network-setup)。

## <a href="" id="network-setup"></a>[網路設定] 頁面


如果您的裝置未偵測到可用來連線到網路或網際網路的有線連線，您將會看到這個頁面。 您可以在此處連線到無線網路，或略過建立網路連線的步驟。

![顯示網路設定頁面的影像。](images/setupnetworksetup-1.png)

### 詳細資料

只有在裝置無法偵測到有線網路時，才會顯示這個畫面。 如果您看到這個畫面，您會有三個選擇：

-   您可以選取其中一個顯示的無線網路。 如果網路受到保護，系統會將您引導至登入頁面。 如需詳細資訊，請參閱 [無線網路設定](#wireless) 。
-   按一下 **\[略過此步驟\]**，以略過連線到網路的步驟。 系統會將您引導至 [\[為您進行設定\] 頁面](#set-up-for-you)。
    >[!NOTE]
    >注意：如果您略過此步驟，裝置將不具備網路連線，而您的 Surface Hub 上將不會有任何需要網路連線的功能運作，包括系統更新以及電子郵件和行事曆的同步處理功能。 您可以稍後使用 [設定] (查看 [無線網路管理](wireless-network-management-for-surface-hub.md)) 來連線至無線網路。

     

-   您可以在看到這個畫面時插入網路線。 裝置將會偵測到它，並在螢幕上新增 **[下一步]**。 按一下 **[下一步]**，繼續進行有線連線。

### 發生什麼事？

如果裝置在啟動時具備有線連線，而且可以建立網路或網際網路連線時，則此頁面將會不顯示。 如果您想要將裝置連線到無線連線，請確定未在初次執行時插入任何乙太網路纜線，其會將您帶到這個畫面。 不論您是否選擇立即設定，都可以 [使用 [設定]](wireless-network-management-for-surface-hub.md) ，稍後設定不同的連線。

如果您想要從這個頁面連線到受保護的無線網路，可按一下您選擇的網路，然後提供連線所需的資訊 (密碼或帳戶認證)。 請參閱 [無線網路設定](#wireless)。

## <a href="" id="wireless"></a>無線網路設定


當您選取了受保護的無線網路時，將會顯示這個頁面。

![顯示無線網路設定頁面的影像。](images/setupnetworksetup-3.png)

### 詳細資料

-   **使用者名稱：** 輸入所選取無線網路的使用者名稱。
-   **密碼：** 這是網路的密碼。

### 發生什麼事？

裝置將嘗試連線到指定的網路。 如果成功，系統會將您引導至 [[為您進行設定] 頁面](#set-up-for-you)。

## <a href="" id="proxy"></a>網路 Proxy 設定


當裝置偵測到連線能力有限的有線連線時，將會顯示這個頁面。 您有三個選項：

-   您可以選擇要使用的無線網路，而不是有限的有線連線。
-   您可以選取 **\[略過此步驟\]** 來略過連線到網路的步驟。 系統會將您引導至 [\[為您進行設定\] 頁面](#set-up-for-you)。
    **注意**：如果您略過此步驟，裝置將不具備網路連線，而您的 Surface Hub 上將不會有任何需要網路連線的功能運作，包括電子郵件和行事曆的同步處理等功能。 您可以稍後使用 [設定] (查看 [無線網路管理](wireless-network-management-for-surface-hub.md)) 來連線至無線網路。

     

-   您可以選取 **[輸入 Proxy 設定]**，讓您能夠指定使用網路 Proxy 的方式。 系統會將您引導至下一個畫面。

    ![顯示網路 Proxy 頁面的影像。](images/setupnetworksetup-2.png)

    如果您在上一個畫面中，按一下** \[輸入 Proxy 設定\]**，您將會看見這個畫面。

    ![顯示 Proxy 伺服器設定詳細資料的影像。](images/setupnetworksetup-4.png)

### 詳細資料

為了進行網路連線，您需要填入指令碼名稱，或 Proxy 伺服器和連接埠資訊。

-   **Proxy 指令碼：** 提供 Proxy 指令碼的位址。
-   **Proxy 伺服器和連接埠：** 您可以提供 Proxy 伺服器位址和連接埠。

### 發生什麼事？

當您按 **\[下一步\] **時，裝置將嘗試連線到 Proxy 伺服器。 如果成功，系統會將您引導至 [[為您進行設定] 頁面](#set-up-for-you)。

您可以選取 **\[略過此步驟\]** 來略過連線到網路的步驟。 系統會將您引導至 [\[為您進行設定\] 頁面](#set-up-for-you)。

>[!NOTE]
>注意：如果您略過此步驟，裝置將不具備網路連線，而您的 Surface Hub 上將不會有任何需要網路連線的功能運作，包括電子郵件和行事曆的同步處理等功能。 您可以稍後使用 [設定] (查看 [無線網路管理](wireless-network-management-for-surface-hub.md)) 來連線至無線網路。

 

## <a href="" id="set-up-for-you"></a>[為您進行設定] 頁面


這個畫面僅提供資訊，並顯示預設已啟用哪些建議的設定。

![顯示為您進行設定頁面的影像。](images/setupsetupforyou.png)

### 詳細資料

您應該閱讀這個畫面，並注意預設已啟用哪些服務。 所有的這些變更都可視需要使用 \[設定\]應用程式來變更，但您應該留意這樣做所產生的後果。 如需詳細資訊，請參閱 [Surface Hub 簡介](intro-to-surface-hub.md) 。

一旦您完成檢閱設定之後，可按 **\[下一步\]** 來開始。

### 發生什麼事？

頁面上顯示的設定已經完成，而且在初次執行完成之後便無法變更。

## <a href="" id="device-account"></a>[裝置帳戶] 頁面


在此頁面上，Surface Hub 將要求提供您先前設定的裝置帳戶認證。 (請參閱[建立和測試裝置帳戶](create-and-test-a-device-account-surface-hub.md))。Surface Hub 將嘗試探索帳戶的各種屬性，而且如果不成功，可能會在其他頁面上要求更多資訊。

>[!NOTE]
>注意：本節並未涵蓋在初次執行期間發生的特定錯誤。 如需錯誤的詳細資訊，請參閱[對 Surface Hub 進行疑難排解](troubleshoot-surface-hub.md)。


![顯示 \[輸入裝置帳戶資訊\] 頁面的影像。](images/setupdeviceacct.png)

### 詳細資料

使用 **「使用者主體名稱」**(UPN) 或 **「網域\\使用者名稱」** 做為第一個項目欄位中的帳戶識別碼。 使用符合您環境的格式，然後輸入密碼。


|                      環境                      | 裝置帳戶所需的格式 |
|-------------------------------------------------------|------------------------------------|
|         僅限線上裝載裝置帳戶。         |        username@domain.com         |
|        僅限內部部署裝載裝置帳戶。         |          DOMAIN\username           |
| 線上與內部部署裝載裝置帳戶 (混合式)。 |          DOMAIN\username           |

按一下 **\[略過設定裝置帳戶\]** 以略過設定裝置帳戶的步驟。 不過，如果您未設定裝置帳戶，裝置將不會完全整合到您的基礎結構。 例如，使用者將無法：

-   在歡迎畫面上看到會議行事曆
-   從歡迎畫面啟動會議
-   從 OneNote 透過電子郵件傳送白板
-   使用商務用 Skype 進行會議

如果您現在略過設定的步驟，可以稍後使用 \[設定\] 應用程式來加以新增。

如果您按一下** \[略過設定裝置帳戶\]**，裝置將顯示一個對話方塊，說明如果裝置沒有裝置帳戶，將會發生什麼事。 如果您選擇 **\[是，跳過此程序\]**，系統即會將您送到 [\[請為此裝置命名\] 頁面](#name-this-device)。

![顯示訊息的圖像，以確認您要略過建立裝置帳戶。](images/setupskipdeviceacct.png)

### 發生什麼事？

裝置將使用裝置帳戶的 UPN 或網域\\使用者名稱與密碼，來執行下列動作：

-   檢查帳戶是否存在於 Active Directory (AD) 或 Azure Active Directory (Azure AD) 中：

    -   如果輸入 UPN：裝置將會在 Azure AD 中尋找帳戶。
    -   如果輸入網域\\使用者名稱：裝置將會在 AD 中尋找帳戶。
-   查詢適用於帳戶信箱的 Microsoft Exchange Server。
-   查詢適用於帳戶的工作階段初始通訊協定 (SIP) 位址。
-   提取帳戶的顯示名稱和別名屬性。

## <a href="" id="exchange-server"></a>Exchange Server 頁面


只有在發生問題時，才會顯示這個頁面。 通常，這表示在 Active Directory (AD) 或 Azure Active Directory (Azure AD) 中找到您提供的裝置帳戶，但未探索到適用於帳戶的 Exchange Server。

![顯示 Exchange 伺服器頁面的影像。](images/setupexchangeserver-01.png)

### 詳細資料

輸入裝載裝置帳戶信箱的 Exchange Server 名稱。

按一下 **\[略過設定 Exchange 服務\]** 以略過此步驟。 如果您這麼做，使用者將無法：

-   在歡迎畫面上看到會議行事曆。
-   從歡迎畫面啟動會議。
-   從 OneNote 透過電子郵件傳送白板。

如需設定相依性的詳細資訊，請參閱 [Surface Hub 的簡介](intro-to-surface-hub.md) 。

您可以使用 [設定] 應用程式，稍後啟用裝置帳戶的 Exchange 服務。

如果您按一下 **\[略過設定 Exchange 服務\]**，裝置將顯示一個對話方塊，說明將會發生什麼事。 如果您選擇 **\[是，跳過此程序\]**，將不會設定 Exchange 服務。

![顯示當您略過設定 Exchange 服務時所顯示確認訊息的影像。](images/setupexchangeserver-02.png)

### 發生什麼事？

Surface Hub 將嘗試在 Exchange Server 上驗證您在此處輸入的裝置帳戶。 如果 Exchange Server 可以連線並加以驗證，則初次執行將會繼續。

如果您選擇略過設定 Exchange 服務，Surface Hub 就會停止尋找 Exchange Server，並且不會啟用任何 Exchange 服務 (電子郵件和行事曆)。

## <a href="" id="exchange-policies"></a>Exchange 原則頁面


這個頁面的顯示時機如下：

-   裝置帳戶正在使用已將 PasswordEnabled 原則設為 1 的 Exchange Active Sync (EAS) 原則。
-   沒有與 Exchange 的連線。
-   Exchange 傳回表示發生錯誤的狀態碼。 (例如：已將帳戶佈建至太多裝置)。
-   Surface Hub 不支援 Exchange 支援的通訊協定。
-   Exchange 傳回不正確的 XML。

![顯示 Exchange 原則頁面的影像。](images/setupexchangepolicies.png)

### 詳細資料

這個頁面僅用於提供資訊，因此不需要任何輸入。 不過，您必須選擇下列其中一個選項以繼續：往前跳過，或重試造成錯誤的驗證。 決定哪一個是最佳選項之前，請參閱下列 **發生什麼事？** 一節。 您或許能夠在按一下其中一個選項之前，在他處修正此問題。

-   **請按一下這裡以繼續使用不受支援的原則**：按一下這裡以繼續進行初次執行。 Surface Hub 將無法使用 Exchange 服務或同步處理。
-   **重試**：再次檢查 Exchange Server 上的原則。

### 發生什麼事？

Surface Hub 會檢查裝置帳戶的 EAS 原則是否已將 PasswordEnabled 原則設為 0 (False)。 如果沒有，就無法同步處理郵件和行事曆，而 Surface Hub 不能使用任何 Exchange 服務。 您可以使用電腦的 Exchange 管理工具，來檢查裝置帳戶是否已將 PasswordEnabled 原則設為 0。 如果沒有，您可以重新設定帳戶，然後按一下此處的 **\[重試\]**。

如果原則已經正確設定，請檢查您的裝置是否已正確連線到網路或網際網路，並且可以連線到您的 Exchange Server，因為如果 Surface Hub 無法連線到 Exchange Server，也會顯示這個頁面。

無法連線到 Exchange 的另一個可能原因是憑證式驗證。 您可能會因為憑證問題而看見這個頁面。 注意：如果裝置顯示 0x80072F0D 或 0X800C0019 的錯誤碼，則需要憑證。 因為佈建是在初次執行程序的第一頁完成，所以您必須按一下 **\[請按一下這裡以繼續使用不受支援的原則\] **來停用 Exchange 服務，然後透過 \[設定\] 應用程式安裝正確的憑證。

如果您選擇略過這個檢查，Surface Hub 就會停止尋找 Exchange Server 和驗證 EAS 原則，而且將不會啟用任何 Exchange 服務。 如需設定相依性的詳細資訊，請參閱 [Surface Hub 的簡介](intro-to-surface-hub.md) 。

## <a href="" id="name-this-device"></a>[請為此裝置命名] 頁面


這個頁面會要求您提供兩個用於識別 Surface Hub 的名稱。

![顯示 \[請為此裝置命名\] 頁面的影像](images/setupnamedevice.png)

### 詳細資料

如果顯示的預設值正確，則您可以按 **\[下一步\]** 開始。 否則，在下列一或兩個文字方塊中輸入資料。

-   **易記名稱：** 這是當使用者想要以無線方式連線到 Surface Hub 時所看見的名稱。
-   **裝置名稱：** 可設定為畫面上所述的任何唯一名稱。

只要這兩個名稱長度符合長度需求，而且未使用受限制的字元，按 **\[下一步\]** 就會引導您進入下一個頁面 [設定此裝置的系統管理員](#setup-admins)。

### 發生什麼事？

Surface Hub 需要兩個適用於裝置的名稱，其預設值如下：

-   **易記名稱：** 裝置帳戶顯示名稱的預設值
-   **裝置名稱：** 裝置帳戶別名的預設值

儘管您稍後可以變更這其中一個名稱，但請記住：

-   易記名稱應該是可辨識且不同的，讓使用者在嘗試進行無線連線時，可以從多個 Surface Hub 中區分出某一個 Surface Hub。
-   如果您決定將裝置加入網域，則裝置名稱不能與帳戶的 Active Directory 網域中任何其他裝置的名稱相同。 如果裝置的名稱與另一個已加入網域的裝置相同，則該裝置就無法加入網域。

>[!NOTE]
>如果您想要啟用[基礎結構上的 Miracast](miracast-over-infrastructure.md)，需要透過 DNS 找到的裝置名稱。 達到此目的的方法不是透過動態 DNS 讓您的 Surface Hub 自動登錄，就是以手動方式建立 Surface Hub 裝置名稱的 A 或 AAAA 記錄。

## <a href="" id="setup-admins"></a>[設定此裝置的系統管理員] 頁面


在這個頁面上，您將會從數個選項選擇您想要如何將系統管理員帳戶設定為在本機管理裝置的方式。

由於每個 Surface Hub 都能讓任意數目已通過驗證的員工使用，因此，會鎖定設定，讓他們無法在工作階段之間進行變更。 只有系統管理員可以設定裝置上的設定，而且在這個頁面上，您將選擇哪種類型的系統管理員具備該權限。

>[!NOTE]
>注意：這個頁面的用途主要是判斷可從裝置 UI 設定裝置的使用者；也就是，可實際瀏覽裝置、登入、開啟 \[設定\] 應用程式，以及對 \[設定\] 進行變更的使用者。

 

![顯示 \[設定此裝置的系統管理員\] 頁面的影像。](images/setupsetupadmins.png)

### 詳細資料

選擇下列其中一個可用的選項：

-   **使用 Microsoft Azure Active Directory**
-   **使用 Active Directory 網域服務**
-   **使用本機系統管理員**

### 發生什麼事？

這是當您選擇某一個選項時所發生的情況。

-   **使用 Microsoft Azure Active Directory**

    按一下這個選項，可讓您將裝置加入 Azure AD。 當您按 **\[下一步\]** 時，裝置將重新啟動以套用某些設定，系統接著會將您引導至 [ [使用 Microsoft Azure Active Directory](#use-microsoft-azure) ] 頁面，並要求輸入可讓您加入 Azure AD 的認證。 已加入組織的 Azure 全域管理員角色的成員，就可以使用 [設定] 應用程式。 將允許哪些特定人員，會取決於您的 Azure AD 訂用帳戶，以及您針對 Azure AD 組織進行設定的方式。
    
    > [!IMPORTANT]
    > 將裝置加入 Azure AD 之後，系統管理員會新增至 Azure Device Administrator 角色，將無法使用 [設定] 應用程式。
    >
    > 如果您在初次執行設定期間將 Surface Hub 加入 Azure AD，Office 應用程式的單一登入 (SSO) 將無法正常運作。 使用者必須單獨登入每個 Office 應用程式。

-   **使用 Active Directory Domain Services**

    按一下此選項，以將裝置加入 AD。 當您按 **\[下一步\]** 時，系統會將您引導至 [ [使用 Active Directory 網域服務](#use-active-directory) ] 頁面，並要求輸入可讓您加入指定網域的認證。 加入之後，您可以從已加入的網域中挑選安全性群組，而來自該安全性群組的使用者就能使用 [設定] 應用程式。

-   **使用本機系統管理員**

    這位系統管理員將不受任何目錄服務支援，因此我們建議您只有在裝置無法存取 Azure AD 或 AD 時選擇此選項。 一旦您在 \[[使用本機系統管理員](#use-a-local-admin)\] 頁面中建立系統管理員的使用者名稱和密碼之後，就需要在每次開啟 \[設定\] 應用程式時重新輸入這些相同的認證。

    注意：本機系統管理員必須能夠實際存取 Surface Hub 才能登入。

>[!NOTE]
>注意：在您完成這個程序之後，除非您重設裝置，否則將無法變更裝置的系統管理員選項。

 

### <a href="" id="use-microsoft-azure"></a>使用 Microsoft Azure Active Directory

如果您決定將 Surface Hub 加入 Azure Active Directory (Azure AD)，您將會看到 **\[接下來將會\]** 頁面。 閱讀該頁面，然後按 **\[下一步\]** 移至 **\[讓您登入\]** 頁面。

加入 Azure AD 有兩個主要優點：

1.  有一些組織的員工將能以系統管理員身分存取裝置，而且能夠啟動 [設定]應用程式並設定裝置。 擁有系統管理員權限的使用者將定義於您的 Azure AD 訂用帳戶中。

2.  如果您的 Azure AD 連線到行動裝置管理 (MDM) 解決方案，裝置將會利用該 MDM 解決方案來註冊，因此您可以套用原則和設定。

    ![顯示當您將 Surface Hub 加入 Azure Active Directory 時的訊息影像。](images/setupjoiningazuread-1.png)

### 詳細資料

以下為必要輸入：

-   **使用者的 UPN：** 可加入 Azure AD 的帳戶的使用者主體名稱 (UPN)。
-   **密碼：** 您用來加入 Azure AD 的帳戶密碼。

![顯示帳戶登入資訊的影像。](images/setupjoiningazuread-2.png)

如果您進行到此階段但尚未具備任何適用於 Azure AD 帳戶的有效認證，裝置將可讓您藉由建立本機系統管理員帳戶來繼續進行。 按一下 **\[改用本機帳戶設定 Windows\]**。

![顯示 \[設定系統管理員帳戶\] 頁面的影像。](images/setupjoiningazuread-3.png)

### 發生什麼事？

一旦您輸入有效的 Azure AD 帳戶認證之後，裝置就會試著加入相關聯的 Azure AD 組織。 如果成功，裝置接著會將該組織中的員工佈建為裝置上的本機系統管理員。 如果您已針對它設定 Azure AD 租用戶，則裝置也會註冊到 MDM。

### <a href="" id="use-active-directory"></a>使用 Active Directory 網域服務

這個頁面將要求提供認證以加入網域，如此一來，Surface Hub 就能以裝置的系統管理員身分佈建安全性群組。

將裝置加入網域之後，必須從您加入的網域中指定安全性群組。 這個安全性群組將佈建為 Surface Hub 上的系統管理員，而任何來自安全性群組的人員都能輸入其網域認證來存取 \[設定\]。

![顯示 \[使用「網域加入」設定系統管理員\] 頁面的影像。](images/setupdomainjoin.png)

### 詳細資料

以下為必要輸入：

-   **網域：** 這是您想要加入之網域的完整網域名稱 (FQDN)。 來自這個網域的安全性群組可以用來管理裝置。
-   **使用者名稱：** 具備足夠權限加入指定網域的帳戶使用者名稱。 
-   **密碼：** 帳戶的密碼。

驗證認證之後，系統會要求您輸入安全性群組名稱。 此為必要輸入。

![顯示 \[輸入安全性群組\] 頁面的影像。](images/setupsecuritygroup-1.png)

### 發生什麼事？

Surface Hub 將使用提供的網域、來自 [[使用 Active Directory 網域服務] 頁面](#use-active-directory) 的帳戶認證，以及來自 [ [請為此裝置命名](#name-this-device) ] 頁面的裝置名稱，嘗試加入網域。 如果加入成功，初次執行將會繼續，並要求安全性群組。 如果加入失敗，初次執行即會中止，並要求您變更所提供的資訊。

如果加入成功，您將看到 **\[輸入安全性群組\]** 頁面。 當您按一下這個頁面中的 **\[選取\]** 按鈕時，裝置將會在您的網域上搜尋指定的安全性群組。 如果找到，即會驗證該群組。 按一下 **\[完成\]** 以完成初次執行程序。

>[!NOTE]
>注意：如果您將 Surface Hub 加入網域，則您需要進行重設才能取消加入裝置。

 

### 使用本機系統管理員

如果您決定不使用 Azure Active Directory (Azure AD) 或 Active Directory (AD) 來管理 Surface Hub，您需要建立本機系統管理員帳戶。

![顯示為本機系統管理員設定系統管理員帳戶的影像。](images/setuplocaladmin.png)

### 詳細資料

以下為必要輸入：

-   **使用者名稱：** 這是將針對這個 Surface Hub 建立的本機系統管理員帳戶的使用者名稱。
-   **密碼：** 這是裝置帳戶的密碼。
-   **重新輸入密碼：** 確認密碼與前一個方塊相同。

### 發生什麼事？

這個頁面將嘗試使用您在此處輸入的認證來建立新的系統管理員帳戶。 如果成功，將結束初次執行。 如果失敗，將要求您提供不同的認證。

## <a href="" id="update-surface-hub"></a>更新 Surface Hub


>[!IMPORTANT]
>重要：進行更新之前，請確定您會閱讀[儲存您的 BitLocker 金鑰](save-bitlocker-key-surface-hub.md)，以確定您擁有金鑰的備份。

 

若要取得最新的功能與修正程式，您應該在完成所有先前的初次執行步驟之後，立即更新 Surface Hub。

1.  請確定裝置有權存取 Windows 補救伺服器。 
2.  開啟 \[設定\]，依序按一下 **\[更新與安全性\]**、**\[Windows Update\]** 及 **\[檢查更新\]**。
3.  如果有可用的更新，即會加以下載。 下載完成之後，按一下 **\[立即更新\]** 按鈕以安裝更新。
4.  安裝更新之後，請依照螢幕上的提示執行。 您可能需要重新啟動裝置。

 

 





