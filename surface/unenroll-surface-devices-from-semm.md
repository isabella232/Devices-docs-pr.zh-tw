---
title: '從 SEMM 和 Surface (取消) '
description: 瞭解如何使用 Surface UEFI 重設套件或修復要求選項，從 SEMM 取消註冊裝置。
keywords: surface 企業管理
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
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: 4942dd5ab187b7350e5093d8d189ad52536ef5bd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448556"
---
# <a name="unenroll-surface-devices-from-semm"></a>從 SEMM 取消 Surface 裝置的註冊

當 Surface 裝置在 Surface Enterprise管理模式 (SEMM) 註冊時，憑證會儲存在該裝置的固件中。 當裝置在 SEMM 中註冊時，該憑證的目前狀態和 SEMM 中的註冊可防止對 Surface UEFI 設定或選項進行未經授權的變更。 若要將 Surface UEFI 設定控制權還原給使用者，Surface 裝置必須從 SEMM 取消註冊，此程式有時稱為重設或復原。 您可以使用兩種方法從 SEMM 取消註冊裝置：Surface UEFI 重設套件和修復要求。

>[!WARNING]
>若要從 SEMM 取消註冊裝置，並還原使用者對 Surface UEFI 設定的控制，您必須擁有用於註冊 SEMM 中的裝置之 SEMM 憑證。 如果此憑證遺失或損壞，則無法從 SEMM 取消註冊。 請備份並保護您的 SEMM 憑證。

有關 SEMM 的資訊，請參閱[Microsoft Surface Enterprise管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。

## <a name="unenroll-a-surface-device-from-semm-with-a-surface-uefi-reset-package"></a>使用 Surface UEFI 重設套件從 SEMM 取消註冊 Surface 裝置

Surface UEFI 重設套件是從 SEMM 取消註冊 Surface 裝置的主要方法。 如同 Surface UEFI 設定套件，重設套件是Windows安裝程式 (.msi) 設定裝置上 SEMM 的檔案。 與組組套件不同，重設套件會將 Surface 裝置上的 Surface UEFI 設定重設為預設設定、移除 SEMM 憑證，以及從 SEMM 取消註冊裝置。

重設套件是專為個別 Surface 裝置所建立。 若要開始建立重設套件程式，您需要要取消註冊的裝置序號，以及註冊裝置所使用的 SEMM 憑證。 您可以在 Surface UEFI 的 PC 資訊頁面上找到 Surface 裝置的**** 序號，如圖 1 所示。 即使 Surface UEFI 受密碼保護且輸入的密碼不正確，此頁面也會顯示。

![系統會顯示 Surface 裝置序號。](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*圖 1。 Surface 裝置序列值會顯示在 Surface UEFI 電腦資訊頁面上*

>[!NOTE]
>若要啟動至 Surface UEFI，在裝置關閉時同時**** 按**音量**增加和電源。 將 **音量保持為最高** ，直到 Surface 標誌顯示且裝置開始啟動。

若要建立 Surface UEFI 重設套件，請遵循下列步驟：

1. 從應用程式開啟 Microsoft Surface UEFI [開始] 功能表。
2. 按一下 **\[開始\]**。
3. 按一下 **[重設套件**，如圖 2 所示。

   ![選取重設套件以建立套件，以從 SEMM 取消註冊 Surface 裝置。](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *圖 2. 按一下 [重設套件以建立套件以從 SEMM 取消註冊 Surface 裝置*

4. 按一下 **[憑證保護** > 以使用私密金鑰 (.pfx) 新增 SEMM 憑證檔案，如圖 3 所示。 流覽至憑證檔案的位置，選取該檔案，然後按一下 [ **確定**。

   ![將 SEMM 憑證新增到 Surface UEFI 重設套件。](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *圖 3. 將 SEMM 憑證新增到 Surface UEFI 重設套件*

5. 按 **\[下一步\]**。
6. 輸入您想要從 SEMM (取消註冊的裝置序號，如圖 4) 所示，然後按一下 [建立以產生 Surface UEFI 重設套件。** **

   ![使用 Surface 裝置序號建立 Surface UEFI 重設套件。](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *圖 4. 使用 Surface 裝置序號建立 Surface UEFI 重設套件*

7. 在 [ **另** 存新案> 對話方塊中，指定 Surface UEFI 重設套件的名稱，流覽至要儲存檔案的位置，然後按一下 [ **儲存**。
8. 當套件產生完成時 **，會顯示成功** 頁面。 按一下 **[結束** 以完成套件建立並關閉 Microsoft Surface UEFI Configurator。

在 Surface 裝置上Windows安裝程式 (.msi) Surface UEFI 重設套件，以從 SEMM 取消註冊裝置。 重設套件需要重新開機才能執行取消註冊作業。 取消註冊裝置之後，您可以確認不再顯示圖) 5 (中的**Microsoft Surface 組配置套件****專案，以**驗證移除是否成功。

![顯示裝置已註冊 SEMM 的畫面。](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*圖 5. 程式和功能中的 Microsoft Surface 組組套件專案顯示裝置已註冊于 SEMM*

## <a name="unenroll-a-surface-device-from-semm-with-a-recovery-request"></a>使用修復要求從 SEMM 取消註冊 Surface 裝置

在某些情況下，Surface UEFI 重設套件可能無法從 SEMM (取消啟用 Surface 裝置，例如，Windows已無法使用) 。 在這些情況下，您可以使用從 Surface UEFI 中產生的修復要求來取消註冊裝置。 即使您沒有 Surface UEFI 密碼的裝置，也可以啟動修復要求程式。

修復要求程式是由 Surface 裝置上的 Surface UEFI 啟動，已由另一部電腦的 Microsoft Surface UEFI 組員核准，然後在 Surface UEFI 中完成。 與重設套件一樣，核准 Microsoft Surface UEFI 設定器的修復要求時，必須存取用於註冊 Surface 裝置之 SEMM 憑證。

若要啟動修復要求，請遵循下列步驟：

1. 啟動要從 SEMM 取消註冊到 Surface UEFI 的 Surface 裝置。
2. 如果系統提示您這麼做，請輸入 Surface UEFI 密碼。
3. 按一下 [**Enterprise管理**頁面，如圖 6 所示。

   ![Enterprise管理頁面。](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *圖 6. 系統Enterprise管理頁面會顯示在註冊于 SEMM 的裝置上的 Surface UEFI 中*

4. 按一下或按**入門**。
5. 按一下或按 **[下一** 步， 以開始修復要求程式。
   >[!NOTE]
   >修復要求會在建立後的兩小時到期。 如果此時尚未完成修復要求，您必須重新啟動修復要求程式。
6. 從 **[選擇 SEMM** 重設金鑰 (中顯示的憑證清單中選取 [ **SEMM** 憑證) ，然後按一下或按 [下一 **步**。

   ![針對您的修復要求選取 SEMM 憑證。](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *圖 7. 針對您的復原要求選擇 SEMM 憑證 (重設要求) *

7. 在 [輸入**SEMM**重設驗證碼> 頁面上，您可以按一下**QR**碼**** 或文字按鈕，以顯示覆原要求 (重設要求) 如圖 8 所示，或 USB 按鈕將修復要求 (重設要求****) 儲存為檔案至 USB 磁碟機，如圖 9 所示。

   ![以 QR 程式碼顯示覆原要求。](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *圖 8. 復原要求 (重設) 顯示為 QR 程式碼*

   ![將修復要求儲存到 USB 磁碟機。](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *圖 9. 將復原要求儲存 (重設) USB 磁碟機*

   * 若要使用 QR 程式碼修復 (重設) ，請使用行動裝置上的 QR 閱讀程式應用程式來讀取程式碼。 QR 閱讀程式應用程式會將 QR 程式碼轉換成數位字串。 接著，您可以以電子郵件或訊息將字串電子郵件或訊息給系統管理員，以 Microsoft Surface UEFI 設定器產生重設驗證碼。
   * 若要使用儲存至 USB 磁碟機 (重設要求) 的復原要求) ，請使用 USB 磁碟機將檔案傳輸至 Microsoft Surface UEFI 設定器用來產生重設驗證碼的電腦。 檔案也可以從另一個裝置上的 USB 磁碟機複製，以以電子郵件傳送或網路傳輸。
   * 若要使用復原要求 (重設) 文字，只要直接在 Microsoft Surface UEFI 設定器中輸入文字。

8. 在另一部電腦上從 [開始] 功能表開啟 Microsoft Surface UEFI Configurator。
    >[!NOTE]
    >Microsoft Surface UEFI Configurator 必須在能夠驗證 SEMM 憑證的憑證鏈的環境中執行。
9. 按一下 **\[開始\]**。
10. 按一下 **[復原要求**，如圖 10 所示。

    ![啟動程式以核准修復要求。](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *圖 10. 按一下 [復原要求以開始核准復原要求程式*

11. 按一下 **[憑證保護** > 以使用 SEMM 憑證驗證修復要求。
12. 流覽至並選取您的 SEMM 憑證檔案，然後按一下 [ **確定**。
13. 當系統提示您輸入憑證密碼時，如圖 11 所示，輸入並確認憑證檔案的密碼，然後按一下 [ **確定**。

    ![輸入 SEMM 憑證的密碼。](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *圖 11. 輸入 SEMM 憑證的密碼*

14. 按 **\[下一步\]**。
15. 輸入 [復原 (重設) ，然後按一下 [產生 (以建立重設驗證**** 碼，如圖 12) 。

    ![輸入復原要求。](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *圖 12. 輸入復原要求 (重設) *

    * 如果您在 Surface 裝置上 (重設要求) 文字，請使用鍵盤在提供的欄位中輸入復原要求 (重設) 要求。
    * 如果您將修復要求 (重設要求) 顯示為 QR 程式碼，然後使用訊息或電子郵件應用程式將程式碼傳送至具有 Microsoft Surface UEFI 設定器的電腦，請將程式碼複製並貼到提供的欄位中。
    * 如果您將 [復原要求 (重設要求) 儲存為 USB 磁碟機的檔案，請按一下 [輸入> 按鈕，流覽至並**** 選取 [復原要求 (重設要求) 檔案，然後按一下 [**確定**。

16. 重設驗證碼會顯示在 Microsoft Surface UEFI 設定器中，如圖 13 所示。

    ![顯示重設驗證碼。](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *圖 13. Microsoft Surface UEFI 設定器中顯示的重設驗證碼*

    * 按一下 [ **共用** > 按鈕，以電子郵件傳送重設驗證碼。

17. 在 Surface 裝置上提供的欄位中輸入重設驗證碼 (如圖 8) 所示，然後按一下或按 **[** 驗證以重設裝置，然後從 SEMM 取消註冊裝置。
18. 按一下或按**SEMM**重設**** 成功頁面上的 [立即重新開機，以完成 SEMM 的取消註冊，如圖 14 所示。

    ![從 SEMM 成功取消註冊的範例顯示。](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *圖 14. 從 SEMM 成功取消註冊*

19. 按一下 **[** 結束于 Microsoft Surface UEFI 設定器中完成復原要求 (重設) 程式並關閉 Microsoft Surface UEFI 設定器。


