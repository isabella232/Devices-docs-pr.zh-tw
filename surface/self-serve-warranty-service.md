---
title: Surface 自助保固與服務
description: Microsoft 365商務客戶可能有資格使用 Microsoft 系統管理中心的 Beta Surface 自我服務保固和服務節點來建立及管理服務訂單。
ms.prod: w10
ms.mktglfcycl: support
ms.localizationpriority: medium
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.date: 06/07/2021
ms.reviewer: louannh
manager: laurawi
audience: itpro
ms.openlocfilehash: a6021a58c85ac6ee4c039959dcde9bab632ea1bb
ms.sourcegitcommit: 267e12897efd9d11f8c7303eaf780632741cfe77
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/22/2021
ms.locfileid: "11614060"
---
# <a name="surface-self-serve-warranty-and-service"></a>Surface 自助保固與服務

Microsoft 365商務客戶可能有資格使用 Microsoft 365 系統管理 中心中的 Surface 自助保固和服務節點來建立及管理服務訂單。 這項新功能以 Beta 版計畫提供，可讓全域系統管理員指定許可權給負責支援保固和服務索賠的公司內部人員，包括：

- Upload需要服務的裝置，輸入序號。
- 新增多個出貨位址。
- 為一或多個裝置建立單一服務訂單，並輸入封面。
- 查看即時服務訂單狀態。
- 若裝置有Exchange保固或進Exchange，則以大量方式出貨和接收進貨。

## <a name="join-beta-program"></a>加入 Beta 計畫

請與您的 Microsoft 客戶成功客戶管理員或客戶成功管理員聯繫，以深入瞭解體驗以及如何參與 Beta 計畫。

## <a name="role-based-permissions"></a>角色型許可權

Surface Self-Serve保固與服務Microsoft 365全域系統管理員可以指派角色給使用者，以授予不同的許可權，以建立及管理服務訂單。

當新的Microsoft 365新使用者新加入 Beta 計畫時，下列系統管理員角色會獲得其他許可權：

| 角色                  | 權限                                                                                                                         |
| --------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| 全域系統管理員          | 查看維修要求<br>建立/管理維修要求<br>新增/編輯/刪除出貨 (位址) <br>建立/管理使用者及其角色 |
| 服務支援系統管理員 | 查看維修要求<br>建立/管理維修要求                                                                               |
| 帳單系統管理員         | 查看維修要求<br>建立/管理維修要求<br>新增/編輯/刪除出貨位址 (es)                                         |

有關使用者和許可權的資訊，請參閱 Microsoft [系統管理中心概觀](/microsoft-365/admin/admin-overview/about-the-admin-center)。

## <a name="create-and-manage-a-service-order"></a>建立及管理服務訂單

1. 請前往 Microsoft 365 系統管理 中心 [https://admin.microsoft.com](https://go.microsoft.com/fwlink/p/?linkid=2024339) ，然後以適當的系統管理員許可權進行登錄。 若要深入瞭解，請參閱[神秘中擁有系統管理員許可權嗎？](/microsoft-365/business-video/admin-center-overview#who-has-admin-permissions-in-my-business)
2. 前往支援****  >  **Surface 裝置維修，然後**選取**建立維修要求**。  (如果您沒看到這個修復選項，表示您沒有存取此頁面的許可權。) 

    > [!div class="mx-imgBorder"]
    > ![開始自助維修要求](images/self-serve-fig1.png)

3. 您可以為一或多個裝置建立維修要求。 選取一**次提交 1**個裝置****，或選取提交多個裝置，.csv檔案上傳多個序列值，然後選取下一**步**。

    > [!NOTE]
    > **適用于多個裝置：**
    >
    > - 從系統管理中心頁面下載範例 CSV 範本，新增所需資訊，並將其儲存到您的本地磁片磁碟機。
    > - 選取**Upload CSV**檔案做為大量專案，選取.csv儲存到您本地磁片磁碟機的檔案，然後選取開啟 **。**
    > - 您的裝置序號將會上傳。 選取 **下** 一步以繼續建立修復。

4. 在 **出貨取代至**下，選取一個出貨位址。 或選取  **新增位址**。

    > [!NOTE]
    >
    > - 許可權允許特定系統管理員新增出貨位址。 如果您有許可權，>您可以新增位址。 輸入必要的資訊，  **然後選取**儲存 。
    > - 表單會自動驗證位址資訊，如果當地郵政系統無法識別位址，可能會更正您進行變更。 電子郵件地址是用來傳送修復要求的通知和通訊。

    > [!div class="mx-imgBorder"]
    > ![
      新增地址
    ](images/self-serve-fig2a.png)

5. 在文字區塊中輸入裝置序號以新增裝置。 若要深入瞭解，請參閱 [裝置序號](https://support.microsoft.com/help/4036293/surface-find-the-serial-number-on-surface)。 如果序號有效，將會顯示影像和產品資訊，包括保固日期和型號。 如果 **資訊正確** ，請選取新增裝置。

    > [!div class="mx-imgBorder"]
    > ![新增裝置](images/self-serve-fig2.png)

6. 重複步驟 1-2，將多個 (最多 20) 要求。
7. 從下拉式功能表中，選取最能描述問題的問題類型，然後選取下 **一步。**

    > [!div class="mx-imgBorder"]
    > ![選取問題類別](images/self-serve-fig3.png)

8. 檢查您的訂單。 如果有任何不正確的資訊，請選擇 **返回** 以修正錯誤。
9. 接受條件條款。
10. 如果要求摘要正確，請選取 **提交您的要求**。

    > [!div class="mx-imgBorder"]
    > ![提交自助維修要求](images/self-serve-fig4.png)

當首頁顯示時，您可以在摘要清單中查看您的服務要求，並收到確認電子郵件。

## <a name="frequently-asked-questions"></a>常見問題集

### <a name="why-am-i-getting-error-code-400-generic-client-service-error-401-unauthorized-service-error-or-error-403-forbidden-service-error"></a>為什麼我收到錯誤碼 400「一般用戶端服務錯誤」、401「未經授權的服務錯誤」或錯誤 403「禁止服務錯誤」？

帳戶可能Microsoft 365問題，或使用者沒有存取內容的許可權。 請到您的全域系統管理員Microsoft 365以取得協助。

### <a name="when-i-enter-my-shipping-address-and-i-get-an-error-message-that-no-shipping-offers-are-available"></a>當我輸入我的出貨位址時，我收到錯誤訊息，指出沒有可用的出貨優惠？

Surface Self-Serve保固與服務 Beta 版目前的可用性有限。 只有在位址位於下列其中一個國家/地區時，才能提供優惠：

奧地利、荷蘭、比利時、保加利亞、克羅埃西亞、賽普勒斯、捷克共和國、丹麥、愛沙尼亞、芬蘭、法國、德國、希臘、匈牙利、愛爾蘭、義大利、科威特、拉脫維亞、立陶宛、盧森堡、馬爾他、荷蘭、安達文、波蘭、葡萄牙、羅馬尼亞、斯洛伐克、斯洛維尼亞、南非、西班牙、瑞典及英國 (不含愛爾蘭) 。

### <a name="where-can-i-see-orders-that-i-have-placed-through-the-microsoft-365-portal"></a>我可以在哪裡查看透過網站入口網站Microsoft 365訂單？

前往 Microsoft 365 系統管理中心[- 服務要求](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/support/devicerepairs)，然後使用您的 Microsoft 365 認證進行登錄。

透過 Microsoft 客戶支援建立的訂單將不會顯示在 Self-Serve和服務管理模組中。

### <a name="why-am-i-unable-to-add-edit-or-delete-a-shipping-address"></a>為什麼我無法新增、編輯或刪除出貨位址？

只有您的全域或帳單系統管理員才能新增、編輯或刪除出貨位址Microsoft 365。請聯繫他們以取得協助。  

### <a name="how-can-i-contact-microsoft-support-for-the-surface-self-serve-warranty-and-service-beta"></a>如何與 Microsoft 支援服務聯繫，以Self-Serve保固與服務 Beta 版？

您可以透過 Microsoft 系統管理中心的 Surface 支援模組直接與支援人員聯繫。

1. 使用您的認證來Microsoft 365 Microsoft 系統管理中心。
2. 選取**支援**  >  **Surface 裝置修復>需要協助嗎？** 並描述問題。
3. 如果結果沒有説明，請選取連絡人 **支援**，然後輸入問題的描述。 確認您的連絡人號碼和電子郵件地址，選取您偏好的連絡人方法，然後選取 **連絡人給我**。
