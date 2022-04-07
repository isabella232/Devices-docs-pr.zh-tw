---
title: 第一次設定 Surface Hub
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
ms.date: 08/17/2021
ms.localizationpriority: medium
ms.openlocfilehash: 551867ccbb041fe292d9ec60f38bb89acfbc764e
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472443"
---
# <a name="first-time-setup-for-surface-hub"></a>第一次設定 Surface Hub

當您第一次開始Surface Hub時，裝置會自動進入第一次安裝模式，以引導您完成帳戶設定和相關設定。

> [!TIP]
> 您可以使用布建 [套](#use-provisioning-packages) 件將整個安裝程式自動化，以確保跨多個 Surface Hub 的一致體驗。

## <a name="get-started"></a>開始使用

1. 根據預設，Cortana會引導您完成此程式。 若要關閉Cortana協助，請選取麥克風圖示。

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana可引導您完成此程式。":::

2. **選取您的地區。** 確認自動偵測到的區域，然後選取 [ **是]**。

    :::image type="content" source="images/hub-setup-region.png" alt-text="選取您的地區。":::

3. **確認鍵盤配置。** 選 **取 [是]**。

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="確認鍵盤配置。":::

4. 若要新增第二個鍵盤，請選取 **[新增配置]**。 否則，請選取 **[略過]**。

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="新增第二個鍵盤。":::

5. **連線至網路。** 如果您已經連接乙太網路纜線，Surface Hub會自動連線到您的網路。 或者，您可以連線到無線網路。 **注意：** 您無法連線到熱點中的無線網路， (將登入要求重新導向至提供者網站的入口網站) 。 選取 **[下一步]**。

    :::image type="content" source="images/hub-setup-network.png" alt-text="連線至網路。":::

6. **接受Windows 10授權合約。** 選取 **[接受]**。

    :::image type="content" source="images/hub-setup-license.png" alt-text="接受Windows 10授權合約。":::

7. 使用 UPN 位址 (user@contoso.com) 或下層網域位址輸入**裝置帳戶資訊** (CONTOSO\user) 。 使用符合您環境的格式，並輸入密碼。

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="輸入裝置帳戶資訊。":::

| 環境                                              | 裝置帳戶所需的格式 |
| -------------------------------------------------------- | ---------------------------------- |
| 裝置帳戶僅在線上託管                     | username@contoso.com               |
| 裝置帳戶僅裝載于內部部署                | CONTOSO\user                       |
| 裝置帳戶裝載于線上和內部部署 (混合式)  | CONTOSO\user                       |

>[!NOTE]
>雖然您可以略過設定裝置帳戶，但裝置將不會完全整合到您的基礎結構中。 如果您現在略過設定的步驟，可以稍後使用 \[設定\] 應用程式來加以新增。

8. **輸入您的密碼** ，然後選取 [ **下一步]。**

9. Surface Hub會自動從上一個步驟中輸入的網域偵測Exchange伺服器和 SIP 位址資訊。 或者，視需要提供您的Exchange伺服器位址，然後選取 [**下一步]**。

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange伺服器和 SIP 位址。":::

10. **將此裝置命名為 。** 輸入裝置的名稱，或使用建議的名稱。 **選取 [下一步]**。

    :::image type="content" source="images/hub-setup-name.png" alt-text="將此裝置命名為 。":::

- [**易記名稱**] 會顯示在 Surface Hub 2S 的左下角，並在投影到裝置時顯示。
- **[裝置名稱**] 會在與 Active Directory 或 Azure Active Directory 相關聯時，以及使用 Intune 註冊裝置時識別裝置。

>[!IMPORTANT]
>如果您打算將Surface Hub與 Active Directory 產生關聯，則裝置名稱必須符合[AD 中電腦名稱稱的標準需求](/troubleshoot/windows-server/identity/naming-conventions-for-computer-domain-site-ou#computer-names)，否則安裝程式將會失敗。

>[!NOTE]
>如果您想要啟用[基礎結構上的 Miracast](miracast-over-infrastructure.md)，需要透過 DNS 找到的裝置名稱。 達到此目的的方法不是透過動態 DNS 讓您的 Surface Hub 自動登錄，就是以手動方式建立 Surface Hub 裝置名稱的 A 或 AAAA 記錄。

### <a name="configure-device-admin-accounts"></a>設定裝置系統管理員帳戶

您只能在第一次安裝期間設定裝置系統管理員。 如需詳細資訊，請參閱：

- [Surface Hub 2S 裝置關係](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [系統管理員群組管理](admin-group-management-for-surface-hub.md)

1. **選擇系統管理員帳戶的類型。** 選取下列其中一個選項：Active Directory 網域服務、Azure Active Directory或本機系統管理員。

    :::image type="content" source="images/hub-setup-join.png" alt-text="選擇系統管理員帳戶的類型。":::

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. 如果您想要在內部部署環境中使用Surface Hub，**您可以透過 Active Directory 網域服務**來建立中樞。  輸入有權將裝置加入 Active Directory 之使用者的認證。
2. 選取 Active Directory 安全性群組，其中包含可在 Surface Hub 2S 上登入設定應用程式的成員。
3. 選 **取 [完成]**。 裝置會重新啟動。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. 如果您想要使用 Microsoft Intune 或 MDM 提供者從雲端管理Surface Hub，請選**取 [Microsoft Azure Active Directory]**。
2. 選取 [下一步]，然後使用公司或學校帳戶登入。 如果重新導向，請使用組織的登入頁面進行驗證，並在要求時提供其他認證。 否則，請輸入您的密碼，然後選取 **[下一步]。**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="使用公司或學校帳戶登入。":::

>[!NOTE]
>若要設定誰可以使用設定應用程式來管理 Surface Hub，請先確定您的租使用者已啟用自動Intune註冊，再將裝置加入Azure AD。 然後，Intune原則可用來設定 Surface Hub 上的[非全域系統管理員](surface-hub-2s-nonglobal-admin.md)。

### <a name="local-administrator-account"></a>本機系統管理員帳戶

- 為您的本機系統管理員輸入使用者名稱和易記密碼。 (如果您忘記本機系統管理員密碼，您必須 [復原您的裝置](surface-hub-2s-recover-reset.md) 並重複安裝程式。)   

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="輸入本機系統管理員帳戶的易記密碼。":::

### <a name="choose-privacy-settings-for-your-device"></a>選擇裝置的隱私權設定

- 從可用的隱私權設定中選取，然後選取 [ **接受]。**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="選擇隱私權設定。":::

### <a name="use-provisioning-packages"></a>使用佈建套件

您可以自訂第一次安裝選項，讓您可以確保跨多個 Surface Hub 的一致體驗。

1. 若要開始，請檢閱 [建立布建套件](provisioning-packages-for-surface-hub.md) 中的檔，並將布建套件儲存至 USB Thumb 磁片磁碟機。
2. 當您在上述安裝步驟中看到 [授權合約] 頁面 (步驟 6 時，請將 USB Thumb 磁片磁碟機插入其中一個 USB 埠) 。
3. 出現提示時，選擇您想要使用的布建套件。
4. 如果您建立了多個裝置 CSV 檔案，您將能夠選擇裝置組態。
5. 依照指示完成第一次安裝程式。
