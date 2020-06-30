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
# <span data-ttu-id="99820-104">從 SEMM 取消 Surface 裝置的註冊</span><span class="sxs-lookup"><span data-stu-id="99820-104">Unenroll Surface devices from SEMM</span></span>

<span data-ttu-id="99820-105">當 Surface 裝置註冊在 Surface Enterprise 管理模式（SEMM）中時，會將憑證儲存在該裝置的固件中。</span><span class="sxs-lookup"><span data-stu-id="99820-105">When a Surface device is enrolled in Surface Enterprise Management Mode (SEMM), a certificate is stored in the firmware of that device.</span></span> <span data-ttu-id="99820-106">該憑證和 SEMM 中的註冊，在裝置註冊 SEMM 時，可防止對 Surface UEFI 設定或選項進行任何未經授權的變更。</span><span class="sxs-lookup"><span data-stu-id="99820-106">The presence of that certificate and the enrollment in SEMM prevent any unauthorized changes to Surface UEFI settings or options while the device is enrolled in SEMM.</span></span> <span data-ttu-id="99820-107">若要將 Surface UEFI 設定的控制權還原給使用者，Surface 裝置必須從 SEMM 中 unenrolled，程式有時會將它描述為 reset 或 recovery。</span><span class="sxs-lookup"><span data-stu-id="99820-107">To restore control of Surface UEFI settings to the user, the Surface device must be unenrolled from SEMM, a process sometimes described as reset or recovery.</span></span> <span data-ttu-id="99820-108">您可以使用兩種方法將裝置從 SEMM 取消註冊，即 Surface UEFI 重設套件與復原要求。</span><span class="sxs-lookup"><span data-stu-id="99820-108">There are two methods you can use to unenroll a device from SEMM—a Surface UEFI reset package and a Recovery Request.</span></span>

>[!WARNING]
><span data-ttu-id="99820-109">若要從 SEMM 取消註冊裝置並還原 Surface UEFI 設定的使用者控制權，您必須擁有用來在 SEMM 中註冊裝置的 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="99820-109">To unenroll a device from SEMM and restore user control of Surface UEFI settings, you must have the SEMM certificate that was used to enroll the device in SEMM.</span></span> <span data-ttu-id="99820-110">如果此憑證遭到遺失或損毀，就無法取消註冊 SEMM。</span><span class="sxs-lookup"><span data-stu-id="99820-110">If this certificate becomes lost or corrupted, it is not possible to unenroll from SEMM.</span></span> <span data-ttu-id="99820-111">據此備份及保護您的 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="99820-111">Back up and protect your SEMM certificate accordingly.</span></span>

<span data-ttu-id="99820-112">如需 SEMM 的詳細資訊，請參閱[Microsoft Surface Enterprise 管理模式](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)。</span><span class="sxs-lookup"><span data-stu-id="99820-112">For more information about SEMM, see [Microsoft Surface Enterprise Management Mode](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode).</span></span>

## <span data-ttu-id="99820-113">從 SEMM 取消註冊 Surface 裝置與 Surface UEFI 重設套件</span><span class="sxs-lookup"><span data-stu-id="99820-113">Unenroll a Surface device from SEMM with a Surface UEFI reset package</span></span>

<span data-ttu-id="99820-114">Surface UEFI 重設套件是您用來從 SEMM 取消註冊 Surface 裝置的主要方法。</span><span class="sxs-lookup"><span data-stu-id="99820-114">The Surface UEFI reset package is the primary method you use to unenroll a Surface device from SEMM.</span></span> <span data-ttu-id="99820-115">就像 Surface UEFI 設定套件一樣，reset 套件是在裝置上配置 SEMM 的 Windows Installer （.msi）檔案。</span><span class="sxs-lookup"><span data-stu-id="99820-115">Like a Surface UEFI configuration package, the reset package is a Windows Installer (.msi) file that configures SEMM on the device.</span></span> <span data-ttu-id="99820-116">與設定套件不同的是，重設套件會將 Surface 裝置上的 Surface UEFI 設定重設為預設設定、移除 SEMM 憑證，以及將裝置從 SEMM 取消註冊。</span><span class="sxs-lookup"><span data-stu-id="99820-116">Unlike the configuration package, the reset package will reset the Surface UEFI configuration on a Surface device to its default settings, remove the SEMM certificate, and unenroll the device from SEMM.</span></span>

<span data-ttu-id="99820-117">[重設套件] 專為個別 Surface 裝置建立。</span><span class="sxs-lookup"><span data-stu-id="99820-117">Reset packages are created specifically for an individual Surface device.</span></span> <span data-ttu-id="99820-118">若要開始建立重設套件的程式，您需要要取消封裝之裝置的序列值，以及用來註冊裝置的 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="99820-118">To begin the process of creating a reset package, you will need the serial number of the device you want to unenroll, as well as the SEMM certificate used to enroll the device.</span></span> <span data-ttu-id="99820-119">您可以在 Surface UEFI 的 [**電腦資訊**] 頁面上找到 surface 裝置的序列值，如圖1所示。</span><span class="sxs-lookup"><span data-stu-id="99820-119">You can find the serial number of your Surface device on the **PC information** page of Surface UEFI, as shown in Figure 1.</span></span> <span data-ttu-id="99820-120">即使 Surface UEFI 受密碼保護且輸入不正確的密碼，此頁面也會顯示。</span><span class="sxs-lookup"><span data-stu-id="99820-120">This page is displayed even if Surface UEFI is password protected and the incorrect password is entered.</span></span>

![顯示 Surface 裝置的序列值](images/surface-semm-unenroll-fig1.png "Serial number of Surface device is displayed")

*<span data-ttu-id="99820-122">圖 1。</span><span class="sxs-lookup"><span data-stu-id="99820-122">Figure 1.</span></span> <span data-ttu-id="99820-123">Surface 裝置的序列值會顯示在 [Surface UEFI 電腦資訊] 頁面上</span><span class="sxs-lookup"><span data-stu-id="99820-123">The serial number of the Surface device is displayed on the Surface UEFI PC information page</span></span>*

>[!NOTE]
><span data-ttu-id="99820-124">若要引導至 Surface UEFI，請在裝置關閉時同步選取**大容量**和**電源**。</span><span class="sxs-lookup"><span data-stu-id="99820-124">To boot to Surface UEFI, press **Volume Up** and **Power** simultaneously while the device is off.</span></span> <span data-ttu-id="99820-125">一直按住**音量**，直到顯示表面標誌為止，且裝置開始啟動。</span><span class="sxs-lookup"><span data-stu-id="99820-125">Hold **Volume Up** until the Surface logo is displayed and the device begins to boot.</span></span>

<span data-ttu-id="99820-126">若要建立 Surface UEFI 重設套件，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="99820-126">To create a Surface UEFI reset package, follow these steps:</span></span>

1. <span data-ttu-id="99820-127">從 [開始] 功能表開啟 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="99820-127">Open Microsoft Surface UEFI Configurator from the Start menu.</span></span>
2. <span data-ttu-id="99820-128">按一下 **\[開始\]**。</span><span class="sxs-lookup"><span data-stu-id="99820-128">Click **Start**.</span></span>
3. <span data-ttu-id="99820-129">按一下 [**重設套件**]，如圖2所示。</span><span class="sxs-lookup"><span data-stu-id="99820-129">Click **Reset Package**, as shown in Figure 2.</span></span>

   ![選取 [重設套件]，建立從 SEMM 取消註冊 Surface 裝置的套件](images/surface-semm-unenroll-fig2.png "Select Reset Package to create a package to unenroll Surface device from SEMM")

   *<span data-ttu-id="99820-131">圖 2.</span><span class="sxs-lookup"><span data-stu-id="99820-131">Figure 2.</span></span> <span data-ttu-id="99820-132">按一下 [重設套件]，以建立從 SEMM 取消註冊 Surface 裝置的套件</span><span class="sxs-lookup"><span data-stu-id="99820-132">Click Reset Package to create a package to unenroll a Surface device from SEMM</span></span>*

4. <span data-ttu-id="99820-133">按一下 [**憑證保護**]，以使用私密金鑰（.pfx）新增您的 SEMM 憑證檔案，如圖3所示。</span><span class="sxs-lookup"><span data-stu-id="99820-133">Click **Certificate Protection** to add your SEMM certificate file with private key (.pfx), as shown in Figure 3.</span></span> <span data-ttu-id="99820-134">流覽到您憑證檔案的位置，選取檔案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="99820-134">Browse to the location of your certificate file, select the file, and then click **OK**.</span></span>

   ![將 SEMM 憑證新增至 Surface UEFI 重設套件](images/surface-semm-unenroll-fig3.png "Add the SEMM certificate to Surface UEFI reset package")

   *<span data-ttu-id="99820-136">圖 3.</span><span class="sxs-lookup"><span data-stu-id="99820-136">Figure 3.</span></span> <span data-ttu-id="99820-137">將 SEMM 憑證新增至 Surface UEFI 重設套件</span><span class="sxs-lookup"><span data-stu-id="99820-137">Add the SEMM certificate to a Surface UEFI reset package</span></span>*

5. <span data-ttu-id="99820-138">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="99820-138">Click **Next**.</span></span>
6. <span data-ttu-id="99820-139">輸入您要從 SEMM 取消封裝之裝置的序列值（如圖4所示），然後按一下 [**建立**] 以產生 Surface UEFI 重設套件。</span><span class="sxs-lookup"><span data-stu-id="99820-139">Type the serial number of the device you want to unenroll from SEMM (as shown in Figure 4), and then click **Build** to generate the Surface UEFI reset package.</span></span>

   ![使用序列值（Surface 裝置）建立 Surface UEFI 重設套件](images/surface-semm-unenroll-fig4.png "Create a Surface UEFI reset package with serial number of Surface device")

   *<span data-ttu-id="99820-141">圖 4.</span><span class="sxs-lookup"><span data-stu-id="99820-141">Figure 4.</span></span> <span data-ttu-id="99820-142">使用 Surface 裝置的序列值來建立 Surface UEFI 重設套件</span><span class="sxs-lookup"><span data-stu-id="99820-142">Use the serial number of your Surface device to create a Surface UEFI reset package</span></span>*

7. <span data-ttu-id="99820-143">在 [**另存**新檔] 對話方塊中，指定 Surface UEFI 重設套件的名稱，流覽至您要儲存檔案的位置，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="99820-143">In the **Save As** dialog box, specify a name for the Surface UEFI reset package, browse to the location where you would like to save the file, and then click **Save**.</span></span>
8. <span data-ttu-id="99820-144">套件產生完成後，就會顯示**成功**的頁面。</span><span class="sxs-lookup"><span data-stu-id="99820-144">When the package generation has completed, the **Successful** page is displayed.</span></span> <span data-ttu-id="99820-145">按一下 [**結束**] 以完成套件建立，然後關閉 MICROSOFT Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="99820-145">Click **End** to complete package creation and close Microsoft Surface UEFI Configurator.</span></span>

<span data-ttu-id="99820-146">在 Surface 裝置上執行 Surface UEFI 重新設定套件的 Windows Installer （.msi）檔案，以從 SEMM 取消裝置的註冊。</span><span class="sxs-lookup"><span data-stu-id="99820-146">Run the Surface UEFI reset package Windows Installer (.msi) file on the Surface device to unenroll the device from SEMM.</span></span> <span data-ttu-id="99820-147">重設套件需要重新開機才能執行取消註冊作業。</span><span class="sxs-lookup"><span data-stu-id="99820-147">The reset package will require a reboot to perform the unenroll operation.</span></span> <span data-ttu-id="99820-148">裝置 unenrolled 之後，您可以確保 [**程式和功能**] （如圖5所示）中的 [ **Microsoft Surface Configuration 套件**專案] 不再出現，以驗證成功的移除。</span><span class="sxs-lookup"><span data-stu-id="99820-148">After the device has been unenrolled, you can verify the successful removal by ensuring that the **Microsoft Surface Configuration Package** item in **Programs and Features** (shown in Figure 5) is no longer present.</span></span>

![顯示裝置已在 SEMM 中註冊的畫面](images/surface-semm-unenroll-fig5.png "Screen that shows device is enrolled in SEMM")

*<span data-ttu-id="99820-150">圖 5.</span><span class="sxs-lookup"><span data-stu-id="99820-150">Figure 5.</span></span> <span data-ttu-id="99820-151">[程式和功能] 中的 [Microsoft Surface Configuration 套件] 專案出現的狀態表示裝置已註冊 SEMM</span><span class="sxs-lookup"><span data-stu-id="99820-151">The presence of the Microsoft Surface Configuration Package item in Programs and Features indicates that the device is enrolled in SEMM</span></span>*

## <span data-ttu-id="99820-152">從 SEMM 取消註冊 Surface 裝置與恢復要求</span><span class="sxs-lookup"><span data-stu-id="99820-152">Unenroll a Surface device from SEMM with a Recovery Request</span></span>

<span data-ttu-id="99820-153">在某些情況下，Surface UEFI 重設套件可能不是將 Surface 裝置從 SEMM 取消註冊的可行選項（例如，Windows 無法使用的位置）。</span><span class="sxs-lookup"><span data-stu-id="99820-153">In some scenarios, a Surface UEFI reset package may not be a viable option to unenroll a Surface device from SEMM (for example, where Windows has become unusable).</span></span> <span data-ttu-id="99820-154">在這些案例中，您可以使用從 Surface UEFI 中產生的復原要求，取消註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="99820-154">In these scenarios you can unenroll the device by using a Recovery Request generated from within Surface UEFI.</span></span> <span data-ttu-id="99820-155">即使在您沒有 Surface UEFI 密碼的裝置上，也可以啟動復原要求處理常式。</span><span class="sxs-lookup"><span data-stu-id="99820-155">The Recovery Request process can be initiated even on devices where you do not have the Surface UEFI password.</span></span>

<span data-ttu-id="99820-156">復原要求程式是從 Surface 裝置上的 Surface UEFI，在另一部電腦上以 Microsoft Surface UEFI 配置器核准，然後在 Surface UEFI 中完成。</span><span class="sxs-lookup"><span data-stu-id="99820-156">The Recovery Request process is initiated from Surface UEFI on the Surface device, approved with Microsoft Surface UEFI Configurator on another computer, and then completed in Surface UEFI.</span></span> <span data-ttu-id="99820-157">與 [重設套件] 一樣，使用 Microsoft Surface UEFI 配置器核准復原要求，需要存取用來註冊 Surface 裝置的 SEMM 憑證。</span><span class="sxs-lookup"><span data-stu-id="99820-157">Like the reset package, approving a Recovery Request with Microsoft Surface UEFI Configurator requires access to the SEMM certificate that was used to enroll the Surface device.</span></span>

<span data-ttu-id="99820-158">若要啟動復原要求，請依照下列步驟執行：</span><span class="sxs-lookup"><span data-stu-id="99820-158">To initiate a Recovery Request, follow these steps:</span></span>

1. <span data-ttu-id="99820-159">引導要從 SEMM unenrolled 到 Surface UEFI 的 Surface 裝置。</span><span class="sxs-lookup"><span data-stu-id="99820-159">Boot the Surface device that is to be unenrolled from SEMM to Surface UEFI.</span></span>
2. <span data-ttu-id="99820-160">如果系統提示您執行此動作，請輸入 Surface UEFI 密碼。</span><span class="sxs-lookup"><span data-stu-id="99820-160">Type the Surface UEFI password if you are prompted to do so.</span></span>
3. <span data-ttu-id="99820-161">按一下 [**企業管理**] 頁面，如圖6所示。</span><span class="sxs-lookup"><span data-stu-id="99820-161">Click the **Enterprise management** page, as shown in Figure 6.</span></span>

   ![企業管理頁面](images/surface-semm-unenroll-fig6.png "Enterprise Management page")

   *<span data-ttu-id="99820-163">圖 6.</span><span class="sxs-lookup"><span data-stu-id="99820-163">Figure 6.</span></span> <span data-ttu-id="99820-164">[企業管理] 頁面會顯示在已註冊 SEMM 之裝置上的 Surface UEFI 中</span><span class="sxs-lookup"><span data-stu-id="99820-164">The Enterprise management page is displayed in Surface UEFI on devices enrolled in SEMM</span></span>*

4. <span data-ttu-id="99820-165">按一下或按 [**開始**使用]。</span><span class="sxs-lookup"><span data-stu-id="99820-165">Click or press **Get Started**.</span></span>
5. <span data-ttu-id="99820-166">按一下或按 **[下一步]** 以開始 [恢復要求] 程式。</span><span class="sxs-lookup"><span data-stu-id="99820-166">Click or press **Next** to begin the Recovery Request process.</span></span>
   >[!NOTE]
   ><span data-ttu-id="99820-167">復原要求在建立之後就會過期兩個小時。</span><span class="sxs-lookup"><span data-stu-id="99820-167">A Recovery Request expires two hours after it is created.</span></span> <span data-ttu-id="99820-168">如果在這段時間內沒有完成復原要求，您就必須重新開機復原要求程式。</span><span class="sxs-lookup"><span data-stu-id="99820-168">If a Recovery Request is not completed in this time, you will have to restart the Recovery Request process.</span></span>
6. <span data-ttu-id="99820-169">從 [**選擇 SEMM 重設金鑰**] 頁面上顯示的憑證清單中選取 [ **SEMM Certificate** ] （如圖7所示），然後按一下或按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="99820-169">Select **SEMM Certificate** from the list of certificates displayed on the **Choose a SEMM reset key** page (shown in Figure 7), and then click or press **Next**.</span></span>

   ![針對您的 [恢復] 要求選取 [SEMM 憑證]](images/surface-semm-unenroll-fig7.png "Select SEMM certificate for your Recovery Request")

   *<span data-ttu-id="99820-171">圖 7.</span><span class="sxs-lookup"><span data-stu-id="99820-171">Figure 7.</span></span> <span data-ttu-id="99820-172">針對您的 [恢復] 要求選擇 [SEMM 憑證] （重設要求）</span><span class="sxs-lookup"><span data-stu-id="99820-172">Choose SEMM Certificate for your Recovery Request (Reset Request)</span></span>*

7. <span data-ttu-id="99820-173">在 [**輸入 SEMM 重設驗證碼**] 頁面上，您可以按一下 [ **QR 代碼**] 或 [**文字**] 按鈕，以顯示您的復原要求（重設要求），如圖8所示，或**Usb**按鈕，將您的復原要求（重設要求）儲存為檔案至 USB 磁片磁碟機，如圖9所示。</span><span class="sxs-lookup"><span data-stu-id="99820-173">On the **Enter SEMM reset verification code** page you can click the **QR Code** or **Text** buttons to display your Recovery Request (Reset Request) as shown in Figure 8, or the **USB** button to save your Recovery Request (Reset Request) as a file to a USB drive, as shown in Figure 9.</span></span>

   ![將復原要求顯示為 QR 代碼](images/surface-semm-unenroll-fig8.png "Recovery Request displayed as a QR Code")

   *<span data-ttu-id="99820-175">圖 8.</span><span class="sxs-lookup"><span data-stu-id="99820-175">Figure 8.</span></span> <span data-ttu-id="99820-176">顯示為 QR 程式碼的恢復要求（重設要求）</span><span class="sxs-lookup"><span data-stu-id="99820-176">A Recovery Request (Reset Request) displayed as a QR Code</span></span>*

   ![將恢復要求儲存至 USB 磁片磁碟機](images/surface-semm-unenroll-fig9.png "Save a recovery request to a USB drive")

   *<span data-ttu-id="99820-178">圖 9.</span><span class="sxs-lookup"><span data-stu-id="99820-178">Figure 9.</span></span> <span data-ttu-id="99820-179">將恢復要求（重設要求）儲存至 USB 磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="99820-179">Save a Recovery Request (Reset Request) to a USB drive</span></span>*

   * <span data-ttu-id="99820-180">若要使用 QR 代碼復原要求（Reset 要求），請使用行動裝置上的 QR 閱讀程式 app 來朗讀程式碼。</span><span class="sxs-lookup"><span data-stu-id="99820-180">To use a QR Code Recovery Request (Reset Request), use a QR reader app on a mobile device to read the code.</span></span> <span data-ttu-id="99820-181">QR 閱讀程式 app 會將 QR 代碼轉譯為一個字母數位字串。</span><span class="sxs-lookup"><span data-stu-id="99820-181">The QR reader app will translate the QR code into an alphanumeric string.</span></span> <span data-ttu-id="99820-182">然後，您可以透過電子郵件或訊息將字串傳送給系統管理員，以使用 Microsoft Surface UEFI 配置器產生重設驗證碼。</span><span class="sxs-lookup"><span data-stu-id="99820-182">You can then email or message that string to the administrator that will produce the reset verification code with Microsoft Surface UEFI Configurator.</span></span>
   * <span data-ttu-id="99820-183">若要使用儲存至 USB 磁片磁碟機的復原要求（重設要求）做為檔案，請使用 USB 磁片磁碟機將檔案傳輸到 Microsoft Surface UEFI 設定檔將用來產生重設驗證碼的電腦。</span><span class="sxs-lookup"><span data-stu-id="99820-183">To use a Recovery Request (Reset Request) saved to a USB drive as a file, use the USB drive to transfer the file to the computer where Microsoft Surface UEFI Configurator will be used to produce the Reset Verification Code.</span></span> <span data-ttu-id="99820-184">您也可以從另一個裝置上的 USB 磁片磁碟機複製該檔案，以透過網路傳送或轉移郵件。</span><span class="sxs-lookup"><span data-stu-id="99820-184">The file can also be copied from the USB drive on another device to be emailed or transferred over the network.</span></span>
   * <span data-ttu-id="99820-185">若要使用 [恢復] 要求（Reset 要求）做為文字，只要直接在 Microsoft Surface UEFI 配置器中輸入文字即可。</span><span class="sxs-lookup"><span data-stu-id="99820-185">To use the Recovery Request (Reset Request) as text, simply type the text directly into Microsoft Surface UEFI Configurator.</span></span>

8. <span data-ttu-id="99820-186">從另一部電腦的 [開始] 功能表開啟 Microsoft Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="99820-186">Open Microsoft Surface UEFI Configurator from the Start menu on another computer.</span></span>
    >[!NOTE]
    ><span data-ttu-id="99820-187">Microsoft Surface UEFI 配置單元必須在能夠驗證 SEMM 憑證之憑證鏈的環境中執行。</span><span class="sxs-lookup"><span data-stu-id="99820-187">Microsoft Surface UEFI Configurator must run in an environment that is able to authenticate the certificate chain for the SEMM certificate.</span></span>
9. <span data-ttu-id="99820-188">按一下 **\[開始\]**。</span><span class="sxs-lookup"><span data-stu-id="99820-188">Click **Start**.</span></span>
10. <span data-ttu-id="99820-189">按一下 [**恢復要求**]，如圖10所示。</span><span class="sxs-lookup"><span data-stu-id="99820-189">Click **Recovery Request**, as shown in Figure 10.</span></span>

    ![核准恢復要求的開始程式](images/surface-semm-unenroll-fig10.png "Start process to approve a Recovery Request")

    *<span data-ttu-id="99820-191">圖 10.</span><span class="sxs-lookup"><span data-stu-id="99820-191">Figure 10.</span></span> <span data-ttu-id="99820-192">按一下 [恢復要求] 以開始核准復原要求</span><span class="sxs-lookup"><span data-stu-id="99820-192">Click Recovery Request to begin the process to approve a Recovery Request</span></span>*

11. <span data-ttu-id="99820-193">按一下 [**憑證保護**] 以使用 SEMM 憑證驗證恢復要求。</span><span class="sxs-lookup"><span data-stu-id="99820-193">Click **Certificate Protection** to authenticate the Recovery Request with the SEMM certificate.</span></span>
12. <span data-ttu-id="99820-194">流覽並選取您的 SEMM 憑證檔案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="99820-194">Browse to and select your SEMM certificate file, and then click **OK**.</span></span>
13. <span data-ttu-id="99820-195">當系統提示您輸入證書密碼（如圖11所示）時，請輸入並確認憑證檔案的密碼，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="99820-195">When you are prompted to enter the certificate password as shown in Figure 11, type and confirm the password for the certificate file, and then click **OK**.</span></span>

    ![輸入 SEMM 憑證的密碼](images/surface-semm-unenroll-fig11.png "Type password for SEMM certificate")

    *<span data-ttu-id="99820-197">圖 11.</span><span class="sxs-lookup"><span data-stu-id="99820-197">Figure 11.</span></span> <span data-ttu-id="99820-198">輸入 SEMM 憑證的密碼</span><span class="sxs-lookup"><span data-stu-id="99820-198">Type the password for the SEMM certificate</span></span>*

14. <span data-ttu-id="99820-199">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="99820-199">Click **Next**.</span></span>
15. <span data-ttu-id="99820-200">輸入 [復原要求（重設要求）]，然後按一下 [**產生**] 來建立重設驗證碼（如圖12所示）。</span><span class="sxs-lookup"><span data-stu-id="99820-200">Enter the Recovery Request (Reset Request), and then click **Generate** to create a reset verification code (as shown in Figure 12).</span></span>

    ![輸入恢復要求](images/surface-semm-unenroll-fig12.png "Enter the recovery request")

    *<span data-ttu-id="99820-202">圖 12.</span><span class="sxs-lookup"><span data-stu-id="99820-202">Figure 12.</span></span> <span data-ttu-id="99820-203">輸入恢復要求（重設要求）</span><span class="sxs-lookup"><span data-stu-id="99820-203">Enter the Recovery Request (Reset Request)</span></span>*

    * <span data-ttu-id="99820-204">如果您在 Surface 裝置上以文字的方式顯示覆原要求（重設要求），請使用鍵盤在提供的欄位中輸入復原要求（重設要求）。</span><span class="sxs-lookup"><span data-stu-id="99820-204">If you displayed the Recovery Request (Reset Request) as text on the Surface device being reset, use the keyboard to type the Recovery Request (Reset Request)  in the provided field.</span></span>
    * <span data-ttu-id="99820-205">如果您將復原要求（Reset 要求）顯示為 QR 程式碼，然後使用訊息或電子郵件應用程式，將程式碼傳送到具有 Microsoft Surface UEFI 配置器的電腦，請將程式碼複製並貼到所提供的欄位中。</span><span class="sxs-lookup"><span data-stu-id="99820-205">If you displayed the Recovery Request (Reset Request) as a QR Code and then used a messaging or email application to send the code to the computer with Microsoft Surface UEFI Configurator, copy and paste the code into the provided field.</span></span>
    * <span data-ttu-id="99820-206">如果您已將復原要求（重設要求）儲存為檔案至 USB 磁片磁碟機，請按一下 [匯**入**] 按鈕，流覽並選取 [恢復要求] （重設要求）檔案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="99820-206">If you saved the Recovery Request (Reset Request) as a file to a USB drive, click the **Import** button, browse to and select the Recovery Request (Reset Request) file, and then click **OK**.</span></span>

16. <span data-ttu-id="99820-207">[重設驗證碼] 會顯示在 Microsoft Surface UEFI 配置單元中，如圖13所示。</span><span class="sxs-lookup"><span data-stu-id="99820-207">The reset verification code is displayed in Microsoft Surface UEFI Configurator, as shown in Figure 13.</span></span>

    ![顯示重設驗證碼](images/surface-semm-unenroll-fig13.png "Display of the reset verification code")

    *<span data-ttu-id="99820-209">圖 13.</span><span class="sxs-lookup"><span data-stu-id="99820-209">Figure 13.</span></span> <span data-ttu-id="99820-210">顯示在 Microsoft Surface UEFI 配置單元中的 reset 驗證碼</span><span class="sxs-lookup"><span data-stu-id="99820-210">The reset verification code displayed in Microsoft Surface UEFI Configurator</span></span>*

    * <span data-ttu-id="99820-211">按一下 [**共用**] 按鈕，透過電子郵件傳送重設驗證碼。</span><span class="sxs-lookup"><span data-stu-id="99820-211">Click the **Share** button to send the reset verification code by email.</span></span>

17. <span data-ttu-id="99820-212">在 Surface 裝置上提供的欄位中輸入重設驗證碼（如圖8所示），然後按一下或按下 [**驗證**] 來重設裝置，然後從 SEMM 取消註冊裝置。</span><span class="sxs-lookup"><span data-stu-id="99820-212">Enter the reset verification code in the provided field on the Surface device (shown in Figure 8), and then click or press **Verify** to reset the device and unenroll the device from SEMM.</span></span>
18. <span data-ttu-id="99820-213">按一下或按下 SEMM 的 [**重\*\*\*\*啟**]，以完成 SEMM 中的取消註冊，如圖14所示。</span><span class="sxs-lookup"><span data-stu-id="99820-213">Click or press **Restart now** on the **SEMM reset successful** page to complete the unenrollment from SEMM, as shown in Figure 14.</span></span>

    ![從 SEMM 成功取消註冊的範例](images/surface-semm-unenroll-fig14.png "Example display of successful unenrollment from SEMM")

    *<span data-ttu-id="99820-215">圖 14.</span><span class="sxs-lookup"><span data-stu-id="99820-215">Figure 14.</span></span> <span data-ttu-id="99820-216">成功從 SEMM 取消註冊</span><span class="sxs-lookup"><span data-stu-id="99820-216">Successful unenrollment from SEMM</span></span>*

19. <span data-ttu-id="99820-217">按一下 Microsoft Surface UEFI 配置單元中的 [**結束**]，以完成恢復要求（Reset 要求）處理常式，然後關閉 MICROSOFT Surface UEFI 配置器。</span><span class="sxs-lookup"><span data-stu-id="99820-217">Click **End** in Microsoft Surface UEFI Configurator to complete the Recovery Request (Reset Request) process and close Microsoft Surface UEFI Configurator.</span></span>


