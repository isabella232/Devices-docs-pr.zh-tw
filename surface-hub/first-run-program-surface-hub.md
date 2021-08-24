---
title: 第一次設定Surface Hub
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
ms.openlocfilehash: 95b3e9dceab3304da627807cf28a9e37a5af10d4
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911448"
---
# <a name="first-time-setup-for-surface-hub"></a>第一次設定Surface Hub

當您第一次Surface Hub時，裝置會自動進入第一次設定模式，以引導您完成帳戶設定和相關設定。

> [!TIP]
> 您可以使用資源調配套件自動化整個設定程式，[](#use-provisioning-packages)以確保跨多個 Surface Hub 的一致體驗。

## <a name="get-started"></a>入門

1. 根據預設，Cortana會引導您完成此程式。 若要關閉Cortana，請選取麥克風圖示。

    :::image type="content" source="images/hub-setup-cortana.png" alt-text="Cortana可引導您完成此程式。":::

2. **選取您的地區。** 確認自動偵測到的區域，然後選取 **是**。

    :::image type="content" source="images/hub-setup-region.png" alt-text="選取您的地區。":::

3. **確認鍵盤配置。** 選取 **是**。

    :::image type="content" source="images/hub-setup-keyboard.png" alt-text="確認鍵盤配置。":::

4. 若要新增第二個鍵盤，請選取 新增 **版面配置**。 否則 **，請選取**跳過 。

    :::image type="content" source="images/hub-setup-2keyboard.png" alt-text="新增第二個鍵盤。":::

5. **連線網路。** 如果您已經連接乙太網路纜線，Surface Hub自動連接到您的網路。 或者，您也可以連接到無線網路。 **注意：** 您無法在將登錄要求重新導向到提供者網站 (或) 入口網站中的無線網路。 選取 **[下一步]**。

    :::image type="content" source="images/hub-setup-network.png" alt-text="連線網路。":::

6. **接受Windows 10授權合約。** 選取 **接受**。

    :::image type="content" source="images/hub-setup-license.png" alt-text="接受Windows 10授權合約。":::

7. **使用 UPN 位址** 或下層網域 (user@contoso.com) CONTOSO\user (輸入裝置帳戶) 。 使用符合您環境的格式，然後輸入密碼。

    :::image type="content" source="images/hub-setup-device-account.png" alt-text="輸入裝置帳戶資訊。":::

| 環境                                              | 裝置帳戶所需的格式 |
| -------------------------------------------------------- | ---------------------------------- |
| 裝置帳戶僅線上託管                     | username@contoso.com               |
| 裝置帳戶僅託管于內部部署                | CONTOSO\user                       |
| 裝置帳戶是線上和內部部署 (混合式)  | CONTOSO\user                       |

>[!NOTE]
>雖然您可以略過設定裝置帳戶，但裝置不會完全整合到您的基礎結構中。 如果您現在略過設定的步驟，可以稍後使用 \[設定\] 應用程式來加以新增。

8. **輸入您的密碼，** 然後選取下 **一步。**

9. Surface Hub自動偵測Exchange步驟中輸入之網域的伺服器和 SIP 位址資訊。 或者，如果需要，請提供您的Exchange伺服器位址，然後選取下**一步**。

    :::image type="content" source="images/hub-setup-exchange.png" alt-text="Exchange伺服器和 SIP 位址。":::

10. **為此裝置命名。** 輸入您的裝置名稱或使用建議的名稱。 **選取 下一個**。

    :::image type="content" source="images/hub-setup-name.png" alt-text="為此裝置命名。":::

- 2S **Surface Hub**左下角會顯示好用名稱，且在專案到裝置時會顯示。
- 當**與**Active Directory 或 Azure Active Directory關聯，以及使用 Intune 註冊裝置時，裝置名稱會識別裝置。

>[!NOTE]
>如果您想要啟用[基礎結構上的 Miracast](miracast-over-infrastructure.md)，需要透過 DNS 找到的裝置名稱。 達到此目的的方法不是透過動態 DNS 讓您的 Surface Hub 自動登錄，就是以手動方式建立 Surface Hub 裝置名稱的 A 或 AAAA 記錄。

### <a name="configure-device-admin-accounts"></a>設定裝置系統管理員帳戶

您只能在第一次設定期間設定裝置系統管理員。 如需詳細資訊，請參閱：

- [Surface Hub 2S 裝置關聯](/surface-hub/prepare-your-environment-for-surface-hub#device-affiliation)
- [系統管理員群組管理](admin-group-management-for-surface-hub.md)

1. **選擇系統管理帳戶類型。** 選取下列其中一個選項：Active Directory 網域服務、Azure Active Directory或本地系統管理員。

    :::image type="content" source="images/hub-setup-join.png" alt-text="選擇系統管理帳戶類型。":::

### <a name="active-directory-domain-services"></a>Active Directory Domain Services

1. 如果您想要在內部部署Surface Hub，您可以將 Hub 與**Active Directory 網域服務**關聯。  輸入具有將裝置加入 Active Directory 之許可權之使用者的認證。
2. 選取 Active Directory 安全性群組，其中包含允許在 設定 2S 上Surface Hub應用程式的成員。
3. 選取 **完成**。 裝置會重新啟動。

### <a name="microsoft-azure-active-directory"></a>Microsoft Azure Active Directory

1. 如果您想要使用 Surface Hub MDM 提供者管理雲端Microsoft Intune，請選取**Microsoft Azure Active Directory。**
2. 選取下一步，然後使用公司或學校帳戶來登錄。 如果重新導向，請使用貴組織的登錄頁面進行驗證，並提供額外的認證 。如果要求的話。 否則，請輸入您的密碼，然後選取下 **一步。**

    :::image type="content" source="images/hub-setup-signin.png" alt-text="使用公司或學校帳戶來登錄。":::

>[!NOTE]
>若要設定哪些人可以使用 設定 App 管理 Surface Hub，請確保您的租使用者已啟用自動 Intune 註冊，然後再將裝置加入 Azure AD。 然後，Intune 策略可用於在 Surface Hub [上](surface-hub-2s-nonglobal-admin.md) 設定非全域系統管理員。

### <a name="local-administrator-account"></a>本地系統管理員帳戶

- 輸入您的當地系統管理員的使用者名稱和值得記住的密碼。 (如果您忘記當地系統管理員密碼，則需要復原裝置並重複安裝程式。) [](surface-hub-2s-recover-reset.md)  

    :::image type="content" source="images/hub-setup-local-admin.png" alt-text="輸入當地系統管理員帳戶的令人難以忘懷的密碼。":::

### <a name="choose-privacy-settings-for-your-device"></a>選擇您裝置的隱私設定

- 從可用的隱私權設定中選取，然後選取接受 **。**

    :::image type="content" source="images/hub-setup-privacy.png" alt-text="選擇隱私權設定。":::

### <a name="use-provisioning-packages"></a>使用佈建套件

您可以自訂第一次設定選項，讓您確保跨多個 Surface Hub 的一致體驗。

1. 首先，請查看建立資源配置套件中的 [檔](provisioning-packages-for-surface-hub.md) ，然後將部署套件儲存到 USB 拇指磁碟機。
2. 開始設定程式之前，請將 USB 拇指磁碟機插入其中一個 USB 埠。
3. 當系統提示時，請選擇您喜歡使用的部署套件。
4. 如果您建立了多個裝置 CSV 檔案，您就能選擇裝置組組。
5. 按照指示完成第一次設定。
