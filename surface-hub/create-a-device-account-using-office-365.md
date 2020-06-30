---
title: 使用 UI 建立裝置帳戶 (Surface Hub)
description: 如果您習慣使用圖形化使用者介面，您可以使用 Office 365 UI 或 Exchange 系統管理中心，來為 Microsoft Surface Hub 建立裝置帳戶。
ms.assetid: D11BCDC4-DABA-4B9A-9ECB-58E02CC8218C
ms.reviewer: ''
manager: laurawi
keywords: 建立裝置帳戶、Office 365 UI、Exchange 系統管理中心、Microsoft 365 系統管理中心、商務用 Skype、行動裝置信箱原則
ms.prod: surface-hub
ms.sitesec: library
author: dansimp
ms.author: dansimp
ms.topic: article
ms.date: 05/04/2018
ms.localizationpriority: medium
ms.openlocfilehash: e1f82f084103d4eef942e812c5e4f0e8bf425def
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10832098"
---
# 使用 UI 建立裝置帳戶 (Surface Hub)


如果您習慣使用圖形化使用者介面，您可以使用 [Office 365 UI](#create-device-acct-o365) 或 [Exchange 系統管理中心](#create-device-acct-eac)，來為 Microsoft Surface Hub 建立裝置帳戶。

## <a href="" id="create-device-acct-o365"></a>使用 Office 365 建立裝置帳戶


1.  [在 Microsoft 365 系統管理中心建立帳戶](#create-device-acct-o365-admin-ctr)。
2.  [從 Microsoft Exchange 系統管理員中心建立行動裝置信箱 (ActiveSync) 原則](#create-device-acct-o365-mbx-policy)。
3.  [使用 Windows PowerShell 完成裝置帳戶的建立](#create-device-acct-o365-complete-acct)。
4.  [使用 PowerShell 設定帳戶的 Exchange 屬性](#create-device-acct-o365-configure-exch-prop)。
5.  [使用商務用 Skype 啟用帳戶](#create-device-acct-o365-skype-for-business)。

### <a href="" id="create-device-acct-o365-admin-ctr"></a>在系統管理中心建立帳戶

1.  透過造訪登入 Office 365https://portal.office.com
2.  為您的 Office 365 租用戶提供系統管理員認證。 這會將您帶到您的 Microsoft 365 系統管理中心。

    ![Microsoft 365 系統管理中心。](images/setupdeviceaccto365-02.png)

3. 在系統管理中心中，流覽至左面板中的 [**資源**]，然後按一下 [**會議室] & 裝置**]。

    ![系統管理中心的會議室 & 裝置] 選項](images/room-equipment.png)

4. 按一下 **\[新增\]** 以建立新的會議室帳戶。 輸入帳戶的顯示名稱和電子郵件地址，然後按一下 **\[新增\]**。

    ![[建立新的會議室帳戶] 視窗](images/room-add.png)

5. 在 [作用中使用者] 清單中選取您剛建立的會議室帳戶。 在右面板中，可以看到帳戶屬性和數個選用動作。 因為無法從 Surface Hub 登入流程中變更密碼，請按一下 **\[重設密碼\]** 變更密碼，然後取消選取 **\[讓這個使用者在第一次登入時變更其密碼\]**。

6. 在 **\[指派的授權\]** 區段中，按一下 **\[編輯\]**，然後按一下適當授權旁邊的下拉箭頭以展開詳細資料。 選取使用者位置，並切換開啟授權清單中的**\[商務用 Skype Online (方案 2)\]**，然後按一下 **\[儲存\]**。 授權會隨您的組織而改變 (例如，您可能有方案 2 或方案 3)。

### <a href="" id="create-device-acct-o365-mbx-policy"></a>從 Exchange 系統管理員中心建立行動裝置信箱 (ActiveSync) 原則

1.  在系統管理中心的左面板中，按一下 [系統**管理**]，然後按一下 [ **Exchange**]。

    ![[系統管理中心]，顯示 exchange 作用中的使用者。](images/setupdeviceaccto365-08.png)

2.  這將會在您的瀏覽器上開啟另一個索引標籤，並將您帶至 Exchange 系統管理中心，您可以在此處為 Surface Hub 建立並設定信箱設定。

    ![Exchange 系統管理中心。](images/setupdeviceaccto365-09.png)

3.  若要建立行動裝置信箱原則，請按一下左面板的 **\[行動\]**，然後按一下 **\[行動裝置信箱原則\]**。 Surface Hub 要求帳戶包含不需要密碼的行動裝置信箱原則，因此，如果您的現有原則已經符合此需求，就可以將該原則套用到帳戶。 否則，使用下列步驟來建立僅限用於 Surface Hub 裝置帳戶的新原則。

    ![Exchange 系統管理員中心 - 建立行動裝置信箱原則。](images/setupdeviceaccto365-10.png)

4.  若要建立新的 Surface Hub 行動裝置信箱原則，按一下原則清單上方控制項的 **+** 按鈕來新增原則。 針對名稱，請提供一個可以協助您區分此原則與其他裝置帳戶的名稱 (例如，*SurfaceHubDeviceMobilePolicy*)。 請確定原則不需要針對指派的目標裝置使用密碼，因此請確定 **\[需要密碼\]** 保持未核取，然後按一下 **\[儲存\]**。

    ![顯示新行動裝置原則的影像。](images/setupdeviceaccto365-11.png)

5.  建立新的行動裝置信箱原則之後，請回到 **\[Exchange 系統管理中心\]**，您將會看到列出的新原則。

    ![Exchange 系統管理中心內新行動裝置信箱原則的影像。](images/setupdeviceaccto365-12.png)



### <a href="" id="create-device-acct-o365-complete-acct"></a>使用 Windows PowerShell 完成裝置帳戶的建立

從現在開始，您需要使用 PowerShell 來設定一些組態，以完成帳戶建立程序。

若要執行這些 PowerShell 指令碼所使用的 Cmdlet，必須針對 PowerShell 系統管理主控台安裝下列項目：

-   [適用于 IT 專業人員的 Microsoft Online Services 登入小幫手 RTW](https://www.microsoft.com/download/details.aspx?id=41950)
-   [適用於 Windows PowerShell 的 Windows Azure Active Directory 模組](https://www.microsoft.com/web/handlers/webpi.ashx/getinstaller/WindowsAzurePowershellGet.3f.3f.3fnew.appids)
-   [商務用 Skype Online，Windows PowerShell 模組](https://www.microsoft.com/download/details.aspx?id=39366)

在 Powershell 中安裝下列模組
``` syntax
    install-module AzureAD
    Install-module MsOnline
```

### 連線到線上服務

1.  以系統管理員身分執行 Windows PowerShell。

    ![顯示如何啟動 Windows PowerShell 並以系統管理員身分執行的影像。](images/setupdeviceaccto365-17.png)

2.  建立認證物件，然後建立新的工作階段以連線到商務用 Skype Online，並提供全域租用戶系統管理員帳戶，然後按一下 **\[確定\]**。

    ![Windows PowerShell 認證要求的影像。](images/setupdeviceaccto365-18.png)

3.  若要連線到 Microsoft Online Services，請執行：

    ``` syntax
    Connect-MsolService -Credential $Cred
    ```

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-19.png)

4.  現在若要連線到商務用 Skype Online 服務，請執行：

    ``` syntax
    $sfbsession = New-CsOnlineSession -Credential $cred
    ```

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-20.png)

5.  最後，若要連線到 Exchange Online 服務，請執行：

    ``` syntax
    $exchangeSession = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri "https://outlook.office365.com/powershell-liveid/" -Credential $cred -Authentication "Basic" –AllowRedirection
    ```

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-21.png)

6.  現在您必須匯入剛才建立的商務用 Skype Online 工作階段和 Exchange Online 工作階段，這將會匯入 Exchange 和 Skype 命令，讓您可以在本機使用它們。

    ``` syntax
    Import-PSSession $exchangesession -AllowClobber -WarningAction SilentlyContinue
    Import-PSSession $sfbsession -AllowClobber -WarningAction SilentlyContinue
    ```

    請注意，這可能需要一段時間才能完成。

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-22.png)

7.  一旦連線到線上服務之後，您需要執行更多 Cmdlet，以便將此帳戶設定為 Surface Hub 裝置帳戶。

### <a href="" id="create-device-acct-o365-configure-exch-prop"></a>使用 PowerShell 設定帳戶的 Exchange 屬性

您現在已連線到線上服務，您可以完成設定裝置帳戶。 您將使用裝置帳戶電子郵件地址來執行下列動作：

-   將信箱類型從一般變更為會議室。
-   設定密碼並啟用會議室信箱帳戶
-   變更各種 Exchange 屬性
-   將使用者帳戶密碼設定為永久有效。

1.  您需要輸入帳戶的電子郵件地址，然後使用該值來建立變數：

    ```powershell
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    若要儲存值，請從信箱取得它：

    ```powershell
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    列印值：

    ```powershell
    $strEmail
    ```

    您將會看到正確的電子郵件地址。

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-23.png)

2. 執行下列 Cmdlet：

    ```powershell
    Set-CASMailbox $strEmail  -ActiveSyncMailboxPolicy "SurfaceHubDeviceMobilePolicy"
    ```

4.  您可以在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。 您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)一節中看到需要設定哪些屬性。

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

    ![顯示 PowerShell Cmdlet 的影像。](images/setupdeviceaccto365-26.png)

5.  如果您決定要讓密碼永久有效，也可以使用 PowerShell Cmdlet 來設定。 如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。

    ``` syntax
    Set-MsolUser -UserPrincipalName $strEmail -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-o365-skype-for-business"></a>使用商務用 Skype 啟用帳戶

使用商務用 Skype 啟用裝置帳戶。

為了啟用商務用 Skype，您的環境需要符合下列先決條件：

-   您必須在 O365 方案中有商務用 Skype Online 獨立方案2或更高版本。 方案必須支援會議功能。
-   如果您需要使用企業語音（PSTN 電話）使用 Surface Hub 的電話服務提供者，您需要商務用 Skype Online 獨立方案3。
-   您的租用戶使用者必須擁有 Exchange 信箱。
-   您的 Surface Hub 帳戶需要商務用 Skype Online 獨立方案2或商務用 Skype Online 獨立方案3授權，但不需要 Exchange Online 授權。

1.  一開始先從電腦建立遠端 PowerShell 工作階段。

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2.  若要針對商務用 Skype Server 啟用您的 Surface Hub 帳戶，請執行下列 Cmdlet：

    ```PowerShell
    Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
    ```

    如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet，從現有的商務用 Skype 使用者取得值：

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```

## <a href="" id="create-device-acct-eac"></a>使用 Exchange 系統管理訊息中心建立裝置帳戶

>[!NOTE]
>只有當您從內部部署的 Active Directory 進行同步處理時，才能使用這個方法。

您可以使用 Exchange 系統管理中心來建立裝置帳戶：

1.  [使用 Exchange 系統管理中心建立帳戶和信箱](#create-device-acct-exch-admin-ctr)。
2.  [從 Exchange 系統管理中心建立行動裝置信箱原則](#create-device-acct-exch-mbx-policy)。
3.  [使用 PowerShell 設定帳戶](#create-device-acct-exch-powershell-conf)。
4.  [使用商務用 Skype 啟用帳戶](#create-device-acct-exch-skype-for-business)。

### <a href="" id="create-device-acct-exch-admin-ctr"></a>使用 Exchange 系統管理中心建立帳戶和信箱

1.  使用 Exchange 系統管理員認證，登入您的 Exchange 系統管理中心。
2.  當您處於 Exchange 系統管理中心 (EAC) 時，請瀏覽到左面板中的 **\[收件者\]**。

    ![顯示 Exchange 系統管理中心內信箱的影像。](images/setupdeviceacctexch-01.png)

3.  在信箱清單上方的控制項上，選擇 **+** 以建立一個新信箱，然後提供 **「顯示名稱」**、**「名稱」** 和 **「使用者登入名稱」**，然後按一下 **\[儲存\]**。

    ![顯示建立新信箱的影像。](images/setupdeviceacctexch-02.png)

### <a href="" id="create-device-acct-exch-mbx-policy"></a>從 Exchange 系統管理中心建立行動裝置信箱原則

>[!NOTE]
>如果您想要建立並指派原則給您所建立的帳戶，且使用 Exchange 2010，請在使用 EMC （Exchange 管理主控台）時查詢原則建立與原則指派的相關資訊。

 

1.  移至 Exchange 系統管理中心。

    ![顯示 Exchange 系統管理中心的影像。](images/setupdeviceacctexch-03.png)

2.  若要建立行動裝置信箱原則，請按一下左面板的 **\[行動\]**，然後按一下 **\[行動裝置信箱原則\]**。 Surface Hub 要求帳戶包含不需要密碼的行動裝置信箱原則，因此，如果您的現有原則已經符合此需求，就可以將該原則套用到帳戶。 否則，使用下列步驟來建立僅限用於 Surface Hub 裝置帳戶的新原則。

    ![使用 Exchange 系統管理中心建立行動裝置信箱原則的影像。](images/setupdeviceacctexch-05.png)

3.  若要建立新的行動裝置帳戶信箱原則，按一下原則清單上方控制項的 **+** 按鈕來新增原則。 針對名稱，請提供一個可以協助您區分此原則與其他裝置帳戶的名稱 (例如，*SurfaceHubDeviceMobilePolicy*)。 原則不得受到密碼保護，因此請確定 **\[需要密碼\]** 保持未核取，然後按一下 **\[儲存\]**。

    ![顯示新的行動裝置信箱原則的影像。](images/setupdeviceacctexch-06.png)

4.  建立新的行動裝置信箱原則之後，請回到 Exchange 系統管理中心，您將會看到列出的新原則。

    ![顯示 Exchange 系統管理訊息中心內新行動裝置信箱原則的影像。](images/setupdeviceacctexch-07.png)

5.  若要在不使用 PowerShell 的情況下套用 ActiveSync 原則，您可以執行下列動作：

    -   在 EAC 中，按一下 **\[收件者\]** &gt; **\[信箱\]**，然後選取信箱。

        ![顯示 Exchange 系統管理中心的影像。](images/setupdeviceacctexch-08.png)

    -   在 **[詳細資料]** 窗格中，捲動至 **[電話和語音功能]**，然後按一下 **[檢視詳細資料]** 以顯示 **[行動裝置詳細資料]** 畫面。

        ![顯示信箱詳細資料的影像。](images/setupdeviceacctexch-09.png)

    -   隨即顯示目前指派的行動裝置信箱原則。 若要變更行動裝置信箱原則，可按一下 **[瀏覽]**。

        ![顯示目前指派的行動裝置信箱原則的影像。](images/setupdeviceacctexch-10.png)

    -   從清單中選擇適當的行動裝置信箱原則，然後依序按一下** [確定]** 和 **[儲存]**。

        ![顯示行動裝置信箱原則清單的影像。](images/setupdeviceacctexch-11.png)

### <a href="" id="create-device-acct-exch-powershell-conf"></a>使用 PowerShell 設定帳戶

您現在已連線到線上服務，您可以完成設定裝置帳戶。 您將使用裝置帳戶電子郵件地址來執行下列動作：

-   將信箱類型從一般變更為會議室。
-   變更各種 Exchange 屬性
-   將使用者帳戶密碼設定為永久有效。

1.  您需要輸入帳戶的電子郵件地址，然後使用該值來建立變數：

    ``` syntax
    $mailbox = (Get-Mailbox <your device account’s alias>)
    ```

    若要儲存值，請從信箱取得它：

    ``` syntax
    $strEmail = $mailbox.WindowsEmailAddress
    ```

    執行下列動作來列印值：

    ``` syntax
    $strEmail
    ```

    您將會看到正確的電子郵件地址。

2.  您需要將帳戶轉換成會議室信箱，請執行下列動作：

    ``` syntax
    Set-Mailbox $strEmail -Type Room
    ```

3.  為了讓裝置帳戶可在 Surface Hub 上進行驗證，您需要啟用會議室信箱帳戶並設定密碼，如此一來裝置便能使用帳戶，利用 ActiveSync 來取得會議資訊並登入商務用 Skype。

    ``` syntax
    Set-Mailbox $strEmail -RoomMailboxPassword (ConvertTo-SecureString  -String "<your password>" -AsPlainText -Force) -EnableRoomMailboxAccount $true
    ```

4.  您可以在裝置帳戶上設定各種不同的 Exchange 屬性來改善會議體驗。 您可以在 [Exchange 屬性](exchange-properties-for-surface-hub-device-accounts.md)一節中看到需要設定哪些屬性。

    ``` syntax
    Set-CalendarProcessing -Identity $strEmail -AutomateProcessing AutoAccept -AddOrganizerToSubject $false –AllowConflicts   $false –DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
    Set-CalendarProcessing -Identity $strEmail -AddAdditionalResponse $true -AdditionalResponse "This is a Surface Hub room!"
    ```

5.  現在我們必須在 AD 中設定一些屬性。 若要這樣做，您需要帳戶別名 (這會在 UPN 中成為 “@” 之前的一部分)。

    ``` syntax
    $strAlias = “<your device account’s alias>”
    ```

6.  使用者必須在其可向 Surface Hub 進行驗證之前，於 AD 中加以啟用。 執行：

    ``` syntax
    Set-ADUser $strAlias -Enabled $True
    ```

7.  如果您決定要讓密碼永久有效，也可以使用 PowerShell Cmdlet 來設定。 如需詳細資訊，請參閱[密碼管理](password-management-for-surface-hub-device-accounts.md)。

    ``` syntax
    Set-ADUser $strAlias -PasswordNeverExpires $True
    ```

### <a href="" id="create-device-acct-exch-skype-for-business"></a>使用商務用 Skype 啟用帳戶

使用商務用 Skype 啟用裝置帳戶。

為了啟用商務用 Skype，您的環境需要符合下列先決條件：

-   您必須在 O365 方案中有商務用 Skype Online 獨立方案2或更高版本。 方案必須支援會議功能。
-   如果您需要使用企業語音（PSTN 電話）使用 Surface Hub 的電話服務提供者，您需要商務用 Skype Online 獨立方案3。
-   您的租用戶使用者必須擁有 Exchange 信箱。
-   您的 Surface Hub 帳戶需要商務用 Skype Online 獨立方案2或商務用 Skype Online 獨立方案3授權，但不需要 Exchange Online 授權。

1.  一開始先從電腦建立遠端 PowerShell 工作階段。

    ```PowerShell
    Import-Module SkypeOnlineConnector
    $cssess=New-CsOnlineSession -Credential $cred
    Import-PSSession $cssess -AllowClobber
    ```

2. 檢索 Surface Hub 帳戶註冊機構池

如果您不確定要針對環境中的 `RegistrarPool` 參數使用哪一個值，您可以使用下列 Cmdlet，從現有的商務用 Skype 使用者取得值：

    ```PowerShell
    Get-CsOnlineUser -Identity ‘alice@contoso.microsoft.com’| fl *registrarpool*
    ```
    
3. 若要針對商務用 Skype Server 啟用您的 Surface Hub 帳戶，請執行下列 Cmdlet：

   ```PowerShell
   Enable-CsMeetingRoom -Identity $strEmail -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    





