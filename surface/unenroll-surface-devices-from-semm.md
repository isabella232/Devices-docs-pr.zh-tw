---
title: 從 SEMM （Surface）中取消註冊的 Surface 裝置
description: 瞭解如何使用 Surface UEFI 重設套件或 [恢復要求] 選項，從 SEMM 取消註冊裝置。
keywords: surface enterprise 管理
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices, security
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.openlocfilehash: aa24ff1ac8a93ebc8078490c5e0c8fa34c940a25
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831276"
---
# 從 SEMM 取消 Surface 裝置的註冊

當 Surface 裝置註冊在 Surface Enterprise 管理模式（SEMM）中時，會將憑證儲存在該裝置的固件中。 該憑證和 SEMM 中的註冊，在裝置註冊 SEMM 時，可防止對 Surface UEFI 設定或選項進行任何未經授權的變更。 若要將 Surface UEFI 設定的控制權還原給使用者，Surface 裝置必須從 SEMM 中 unenrolled，程式有時會將它描述為 reset 或 recovery。 您可以使用兩種方法將裝置從 SEMM 取消註冊，即 Surface UEFI 重設套件與復原要求。

>[!WARNING]
>若要從 SEMM 取消註冊裝置並還原 Surface UEFI 設定的使用者控制權，您必須擁有用來在 SEMM 中註冊裝置的 SEMM 憑證。 如果此憑證遭到遺失或損毀，就無法取消註冊 SEMM。 據此備份及保護您的 SEMM 憑證。

如需 SEMM 的詳細資訊，請參閱[Microsoft Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

##  <a name="unenroll-a-surface-device-from-semm-with-a-surface-uefi-reset-package"></a>從 SEMM 取消註冊 Surface 裝置與 Surface UEFI 重設套件

Surface UEFI 重設套件是您用來從 SEMM 取消註冊 Surface 裝置的主要方法。 就像 Surface UEFI 設定套件一樣，reset 套件是在裝置上配置 SEMM 的 Windows Installer （.msi）檔案。 與設定套件不同的是，重設套件會將 Surface 裝置上的 Surface UEFI 設定重設為預設設定、移除 SEMM 憑證，以及將裝置從 SEMM 取消註冊。

[重設套件] 專為個別 Surface 裝置建立。 若要開始建立重設套件的程式，您需要要取消封裝之裝置的序列值，以及用來註冊裝置的 SEMM 憑證。 您可以在 Surface UEFI 的 [**電腦資訊**] 頁面上找到 surface 裝置的序列值，如圖1所示。 即使 Surface UEFI 受密碼保護且輸入不正確的密碼，此頁面也會顯示。

![顯示 Surface 裝置的序列值](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*圖 1。 Surface 裝置的序列值會顯示在 [Surface UEFI 電腦資訊] 頁面上*

>[!NOTE]
>若要引導至 Surface UEFI，請在裝置關閉時同步選取**大容量**和**電源**。 一直按住**音量**，直到顯示表面標誌為止，且裝置開始啟動。

若要建立 Surface UEFI 重設套件，請遵循下列步驟：

1. 從 [開始] 功能表開啟 Microsoft Surface UEFI 配置器。
2. 按一下 **\[開始\]**。
3. 按一下 [**重設套件**]，如圖2所示。

   ![選取 [重設套件]，建立從 SEMM 取消註冊 Surface 裝置的套件](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *圖 2. 按一下 [重設套件]，以建立從 SEMM 取消註冊 Surface 裝置的套件*

4. 按一下 [**憑證保護**]，以使用私密金鑰（.pfx）新增您的 SEMM 憑證檔案，如圖3所示。 流覽到您憑證檔案的位置，選取檔案，然後按一下 **[確定]**。

   ![將 SEMM 憑證新增至 Surface UEFI 重設套件](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *圖 3. 將 SEMM 憑證新增至 Surface UEFI 重設套件*

5. 按 **\[下一步\]**。
6. 輸入您要從 SEMM 取消封裝之裝置的序列值（如圖4所示），然後按一下 [**建立**] 以產生 Surface UEFI 重設套件。

   ![使用序列值（Surface 裝置）建立 Surface UEFI 重設套件](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *圖 4. 使用 Surface 裝置的序列值來建立 Surface UEFI 重設套件*

7. 在 [**另存**新檔] 對話方塊中，指定 Surface UEFI 重設套件的名稱，流覽至您要儲存檔案的位置，然後按一下 [**儲存**]。
8. 套件產生完成後，就會顯示**成功**的頁面。 按一下 [**結束**] 以完成套件建立，然後關閉 MICROSOFT Surface UEFI 配置器。

在 Surface 裝置上執行 Surface UEFI 重新設定套件的 Windows Installer （.msi）檔案，以從 SEMM 取消裝置的註冊。 重設套件需要重新開機才能執行取消註冊作業。 裝置 unenrolled 之後，您可以確保 [**程式和功能**] （如圖5所示）中的 [ **Microsoft Surface Configuration 套件**專案] 不再出現，以驗證成功的移除。

![顯示裝置已在 SEMM 中註冊的畫面](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*圖 5. [程式和功能] 中的 [Microsoft Surface Configuration 套件] 專案出現的狀態表示裝置已註冊 SEMM*

##  <a name="unenroll-a-surface-device-from-semm-with-a-recovery-request"></a>從 SEMM 取消註冊 Surface 裝置與恢復要求

在某些情況下，Surface UEFI 重設套件可能不是將 Surface 裝置從 SEMM 取消註冊的可行選項（例如，Windows 無法使用的位置）。 在這些案例中，您可以使用從 Surface UEFI 中產生的復原要求，取消註冊裝置。 即使在您沒有 Surface UEFI 密碼的裝置上，也可以啟動復原要求處理常式。

復原要求程式是從 Surface 裝置上的 Surface UEFI，在另一部電腦上以 Microsoft Surface UEFI 配置器核准，然後在 Surface UEFI 中完成。 與 [重設套件] 一樣，使用 Microsoft Surface UEFI 配置器核准復原要求，需要存取用來註冊 Surface 裝置的 SEMM 憑證。

若要啟動復原要求，請依照下列步驟執行：

1. 引導要從 SEMM unenrolled 到 Surface UEFI 的 Surface 裝置。
2. 如果系統提示您執行此動作，請輸入 Surface UEFI 密碼。
3. 按一下 [**企業管理**] 頁面，如圖6所示。

   ![企業管理頁面](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *圖 6. [企業管理] 頁面會顯示在已註冊 SEMM 之裝置上的 Surface UEFI 中*

4. 按一下或按 [**開始**使用]。
5. 按一下或按 **[下一步]** 以開始 [恢復要求] 程式。
   >[!NOTE]
   >復原要求在建立之後就會過期兩個小時。 如果在這段時間內沒有完成復原要求，您就必須重新開機復原要求程式。
6. 從 [**選擇 SEMM 重設金鑰**] 頁面上顯示的憑證清單中選取 [ **SEMM Certificate** ] （如圖7所示），然後按一下或按 **[下一步]**。

   ![針對您的 [恢復] 要求選取 [SEMM 憑證]](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *圖 7. 針對您的 [恢復] 要求選擇 [SEMM 憑證] （重設要求）*

7. 在 [**輸入 SEMM 重設驗證碼**] 頁面上，您可以按一下 [ **QR 代碼**] 或 [**文字**] 按鈕，以顯示您的復原要求（重設要求），如圖8所示，或**Usb**按鈕，將您的復原要求（重設要求）儲存為檔案至 USB 磁片磁碟機，如圖9所示。

   ![將復原要求顯示為 QR 代碼](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *圖 8. 顯示為 QR 程式碼的恢復要求（重設要求）*

   ![將恢復要求儲存至 USB 磁片磁碟機](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *圖 9. 將恢復要求（重設要求）儲存至 USB 磁片磁碟機*

   * 若要使用 QR 代碼復原要求（Reset 要求），請使用行動裝置上的 QR 閱讀程式 app 來朗讀程式碼。 QR 閱讀程式 app 會將 QR 代碼轉譯為一個字母數位字串。 然後，您可以透過電子郵件或訊息將字串傳送給系統管理員，以使用 Microsoft Surface UEFI 配置器產生重設驗證碼。
   * 若要使用儲存至 USB 磁片磁碟機的復原要求（重設要求）做為檔案，請使用 USB 磁片磁碟機將檔案傳輸到 Microsoft Surface UEFI 設定檔將用來產生重設驗證碼的電腦。 您也可以從另一個裝置上的 USB 磁片磁碟機複製該檔案，以透過網路傳送或轉移郵件。
   * 若要使用 [恢復] 要求（Reset 要求）做為文字，只要直接在 Microsoft Surface UEFI 配置器中輸入文字即可。

8. 從另一部電腦的 [開始] 功能表開啟 Microsoft Surface UEFI 配置器。
    >[!NOTE]
    >Microsoft Surface UEFI 配置單元必須在能夠驗證 SEMM 憑證之憑證鏈的環境中執行。
9. 按一下 **\[開始\]**。
10. 按一下 [**恢復要求**]，如圖10所示。

    ![核准恢復要求的開始程式](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *圖 10. 按一下 [恢復要求] 以開始核准復原要求*

11. 按一下 [**憑證保護**] 以使用 SEMM 憑證驗證恢復要求。
12. 流覽並選取您的 SEMM 憑證檔案，然後按一下 **[確定]**。
13. 當系統提示您輸入證書密碼（如圖11所示）時，請輸入並確認憑證檔案的密碼，然後按一下 **[確定]**。

    ![輸入 SEMM 憑證的密碼](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *圖 11. 輸入 SEMM 憑證的密碼*

14. 按 **\[下一步\]**。
15. 輸入 [復原要求（重設要求）]，然後按一下 [**產生**] 來建立重設驗證碼（如圖12所示）。

    ![輸入恢復要求](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *圖 12. 輸入恢復要求（重設要求）*

    * 如果您在 Surface 裝置上以文字的方式顯示覆原要求（重設要求），請使用鍵盤在提供的欄位中輸入復原要求（重設要求）。
    * 如果您將復原要求（Reset 要求）顯示為 QR 程式碼，然後使用訊息或電子郵件應用程式，將程式碼傳送到具有 Microsoft Surface UEFI 配置器的電腦，請將程式碼複製並貼到所提供的欄位中。
    * 如果您已將復原要求（重設要求）儲存為檔案至 USB 磁片磁碟機，請按一下 [匯**入**] 按鈕，流覽並選取 [恢復要求] （重設要求）檔案，然後按一下 **[確定]**。

16. [重設驗證碼] 會顯示在 Microsoft Surface UEFI 配置單元中，如圖13所示。

    ![顯示重設驗證碼](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *圖 13. 顯示在 Microsoft Surface UEFI 配置單元中的 reset 驗證碼*

    * 按一下 [**共用**] 按鈕，透過電子郵件傳送重設驗證碼。

17. 在 Surface 裝置上提供的欄位中輸入重設驗證碼（如圖8所示），然後按一下或按下 [**驗證**] 來重設裝置，然後從 SEMM 取消註冊裝置。
18. 按一下或按下 SEMM 的 [**重****啟**]，以完成 SEMM 中的取消註冊，如圖14所示。

    ![從 SEMM 成功取消註冊的範例](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *圖 14. 成功從 SEMM 取消註冊*

19. 按一下 Microsoft Surface UEFI 配置單元中的 [**結束**]，以完成恢復要求（Reset 要求）處理常式，然後關閉 MICROSOFT Surface UEFI 配置器。


