---
title: 在 Surface Hub 上設定非全域系統管理員帳戶
description: 本文說明如何設定非全域系統管理員帳戶來管理Surface Hub和Surface Hub 2S。
keywords: Surface Hub、Surface Hub v1、Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 02/15/2022
ms.localizationpriority: Medium
appliesto:
- Surface Hub
- Surface Hub 2S
ms.openlocfilehash: be6a6c75155b3c45ae9dda9dd2726033411100c4
ms.sourcegitcommit: e1d7782c2d205da9d1eb6b7aad0333350f2cb5a8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/29/2022
ms.locfileid: "12497688"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>在 Surface Hub 上設定非全域系統管理員帳戶

Windows 10 團隊版 2020 Update 新增了設定非全域系統管理員帳戶的支援，以限制已加入Azure AD網域之裝置上 Surface Hub設定應用程式的管理許可權。 這可讓您僅限限Surface Hub的系統管理員許可權，並防止整個Azure AD網域中潛在的垃圾系統管理員存取。 開始之前，請確定您的Surface Hub已加入Azure AD並Intune自動註冊。 否則，您必須重設Surface Hub，並完成 OOBE) 安裝程式 (第一次、現成可用的設定程式，並加入宣告Azure AD的選項。

Windows 10 團隊版 2020 Update 2 新增[LocalUsersAndGroups 設定服務提供者](/windows/client-management/mdm/policy-csp-localusersandgroups)的支援。 這會取代 [RestrictedGroups CSP，該 CSP](/windows/client-management/mdm/policy-csp-restrictedgroups)仍可供使用，但不再建議使用，如下所述。

## <a name="summary"></a>摘要

建立非全域系統管理員帳戶的程式牽涉到下列步驟：

1. 在Microsoft Intune中，建立一個安全性群組，其中包含指定來管理Surface Hub的系統管理員。
2. 使用 PowerShell 取得Azure AD群組 SID。
3. 建立包含群組 SID Azure AD XML 檔案。
4. 建立安全性群組，其中包含非全域管理員安全性群組將管理的Surface Hub裝置。 
5. 建立以包含您Surface Hub裝置的安全性群組為目標的自訂群組態設定檔。

## <a name="create-azure-ad-security-groups"></a>建立Azure AD安全性群組

首先，建立包含系統管理員帳戶的安全性群組。 然後為Surface Hub裝置建立另一個安全性群組。  

### <a name="create-security-group-for-admin-accounts"></a>建立系統管理員帳戶的安全性群組

1. 透過 Microsoft 端點管理員[系統管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)登入Intune，選取 [**群組**  >  ][**新增群組**>]，然後在 [群組類型] 底下，選取 [**安全性]。**
2. 輸入組名 --例如 **，Surface Hub本機系統管理員**]，然後選取 [**建立]。**

     ![建立中樞系統管理員的安全性群組。](images/sh-create-sec-group.png)

3. 開啟群組，選取 **[成員**]，然後選擇 [**新增成員**] 以輸入您想要在 Surface Hub 上指定為非全域系統管理員的系統管理員帳戶。 若要深入瞭解如何在Intune中建立群組，請參閱[新增群組以組織使用者和裝置](/mem/intune/fundamentals/groups-add)。

### <a name="create-security-group-for-surface-hub-devices"></a>建立Surface Hub裝置的安全性群組

1. 重複上述程式，為中樞裝置建立個別的安全性群組;例如，**Surface Hub裝置**。

     ![建立中樞裝置的安全性群組。](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>使用 PowerShell 取得Azure AD群組 SID

1. 使用提高的帳戶許可權啟動 PowerShell (以系統 **管理員** 身分) 執行，並確保您的系統已設定為執行 PowerShell 腳本。 若要深入瞭解，請參閱 [關於執行原則](/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。
2. [安裝Azure PowerShell模組](/powershell/azure/install-az-ps)。
3. 登入您的Azure AD租使用者。

    ```powershell
    Connect-AzureAD
    ```

4. 當您登入租使用者時，請執行下列 Commandlet。 它會提示您「請輸入Azure AD群組的物件識別碼」。

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. 在Intune中，選取您稍早建立的群組並複製 [物件識別碼]，如下圖所示。

     ![複製安全性群組的物件識別碼。](images/sh-objectid.png)

6. 執行下列 Commandlet 以取得安全性群組的 SID：

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. 將 [物件識別碼] 貼到 PowerShell 命令列中，按**Enter**鍵，然後將**Azure AD群組 SID**複製到文字編輯器中。

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>建立包含群組 SID Azure AD XML 檔案

1. 將下列內容複寫到文字編輯器中：

    ```xml
    <GroupConfiguration>
    <accessgroup desc = "S-1-5-32-544">
        <group action = "U" />
        <add member = "AzureAD\bob@contoso.com"/>
        <add member = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX"/>
    </accessgroup>
    </GroupConfiguration>
    ```
2. 將開頭為 S-1-12-1) 的預留位置 SID (取代為**Azure AD群組 SID**，然後將檔案儲存為 XML;例如 **，aad-local-admin.xml**。

      > [!NOTE]
      > 雖然應該透過其 SID 指定群組，但如果您想要直接新增 Azure 使用者，請以下列格式指定其使用者主體名稱 (UPN) ： `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>建立自訂群組態設定檔

1. 在 [端點管理員] 中，選取 [**裝置**  >  ][**設定設定檔**  >  **][建立設定檔]**。
2. 在 [平臺] 底下 **，選取 [Windows 10及更新版本]。** 在 [設定檔] 底下，選取 [**範本][**  >  **自訂**  >  **][建立]。**
3. 新增名稱和描述，然後選取 [ **下一步]。**
4. 在 [**組態設定**  >  **][OMA-URI] 設定**中，選取 [**新增]**。
5. 在 [新增資料列] 窗格中，新增名稱，並在     **[OMA-URI]** 底下新增下列字串：

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

   > [!NOTE]
   > **RestrictedGroups/ConfigureGroupMembership**原則設定也可讓您設定成員 (使用者或AAD群組) Windows 10本機群組。 不過，它只允許以新成員完整取代現有的群組。 您無法選擇性地新增或移除成員。  在 Windows 10 團隊版 2020 Update 2 中提供，建議使用**LocalUsersandGroups**原則設定，而不是 RestrictedGroups 原則設定。 不支援將這兩個原則設定套用至Surface Hub，而且可能會產生無法預期的結果。

6. 在 [資料類型] 下，選取 **[字串 XML** ]，然後流覽以開啟您在上一個步驟中建立的 XML 檔案。

     ![上傳本機系統管理員 xml 組態檔。](images/sh-local-admin-config.png)

7. 按一下 [儲存]****。
8. 按一下 **[選取群組] 以包含**[並選擇您稍早](#create-security-group-for-surface-hub-devices) (**Surface Hub裝置**) 建立的安全性群組。 按 **\[下一步\]**。
9. 在 [適用性規則] 下方，視需要新增規則。 否則，請選取 **[下一步** ]，然後選取 [ **建立]**。

若要深入瞭解使用 OMA-URI 字串的自訂群組態設定檔，請參閱[在Intune中使用Windows 10裝置的自訂設定](/mem/intune/configuration/custom-settings-windows-10)。

## <a name="non-global-admins-managing-surface-hub"></a>管理Surface Hub的非全域系統管理員

**Surface Hub本**機系統管理員安全性群組的成員現在可以在Surface Hub上登入設定應用程式，並管理設定。

> [!IMPORTANT]
> 除非全域系統管理員也是這個新安全性群組) 的成員，否則 (會移除全域系統管理員對設定應用程式的預設存取權。
