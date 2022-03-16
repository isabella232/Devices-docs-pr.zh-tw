---
title: 在 Surface Hub 上設定非全域系統管理員帳戶
description: 本文將說明如何設定非全域系統管理員帳戶來管理 Surface Hub 2S Surface Hub帳戶。
keywords: Surface Hub，Surface Hub v1，Surface Hub 2S
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
ms.openlocfilehash: 429a7c84605167aa5129999f516c18d17ee30e65
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12449296"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub"></a>在 Surface Hub 上設定非全域系統管理員帳戶

Windows 10 團隊版 2020 Update 新增了針對在加入 Azure AD 網域的 Surface Hub 裝置上，將管理 設定 應用程式的許可權限制為非全域系統管理員帳戶的支援。 這可讓您只將系統管理員許可權範圍Surface Hub，並防止整個網域的系統管理員Azure AD存取。 開始之前，請確定您的Surface Hub已Azure AD和 Intune 自動註冊。 如果沒有，您必須重設 Surface Hub 並完成第一次即用即用 (OOBE) 安裝程式，加入宣告 Azure AD。

Windows 10 團隊版 2020 Update 2 新增[LocalUsersAndGroups 組組服務提供者的支援](/windows/client-management/mdm/policy-csp-localusersandgroups)。 這會取代 [RestrictedGroups CSP](/windows/client-management/mdm/policy-csp-restrictedgroups)#A0 此為可用，但不再建議使用#A1，如下所述。

## <a name="summary"></a>摘要

建立非全域系統管理員帳戶的過程涉及下列步驟：

1. 在 Microsoft Intune中，建立一個安全性群組，其中包含指定管理Surface Hub。
2. 使用 powerShell Azure AD組 SID。
3. 建立包含群組 SID Azure AD XML 檔案。
4. 建立包含非全域系統管理員安全Surface Hub管理之所有裝置的安全性組。 
5. 建立自訂的組組設定檔，以包含您裝置Surface Hub組。

## <a name="create-azure-ad-security-groups"></a>建立Azure AD組

首先，建立包含系統管理員帳戶的安全性組。 然後為裝置建立另一個Surface Hub組。  

### <a name="create-security-group-for-admin-accounts"></a>為系統管理員帳戶建立安全性群組

1. 透過系統管理中心[Microsoft 端點管理員](https://go.microsoft.com/fwlink/?linkid=2109431)Intune，選取**GroupsNew**  >  **Group >**，然後選取在群組類型下，選取安全性 **。**
2. 輸入組名 ，例如，Surface Hub**管理員**，然後選取建立 **。**

     ![為中樞系統管理員建立安全性群組。](images/sh-create-sec-group.png)

3. 開啟群組 **，選取成員**，然後選擇新增成員****，以在 Surface Hub 中輸入要指定為非全域系統管理員的系統管理員Surface Hub。 若要深入瞭解在 Intune 中建立群組，請參閱  [新增群組以組織使用者和裝置](/mem/intune/fundamentals/groups-add)。

### <a name="create-security-group-for-surface-hub-devices"></a>為裝置建立Surface Hub組

1. 重複上一個程式，為中樞裝置建立另一個安全性群組;例如，Surface Hub**裝置**。

     ![建立中樞裝置的安全性群組。](images/sh-create-sec-group-devices.png)

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>使用 powerShell Azure AD組 SID

1. 使用提升的帳戶許可權啟動 PowerShell (**以** 系統管理員) ，並確保您的系統已配置為執行 PowerShell 腳本。 若要深入瞭解，請參閱關於 [執行政策](/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。
2. [安裝Azure PowerShell模組](/powershell/azure/install-az-ps)。
3. 請Azure AD租使用者。

    ```powershell
    Connect-AzureAD
    ```

4. 當您已登錄租使用者時，請執行下列命令。 它會提示您「請輸入您群組Azure AD識別碼」。

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
      
    }
    ```

5. 在 Intune 中，選取您先前建立群組並複製物件識別碼，如下圖所示。

     ![複製安全性群組的物件識別碼。](images/sh-objectid.png)

6. 執行下列命令小命令以取得安全性群組的 SID：

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```

7. 將物件識別碼貼到 PowerShell 命令let中，按**Enter**，然後將 Azure AD **SID 複製到**文字編輯器中。

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>建立包含群組 SID Azure AD XML 檔案

1. 將下列專案複製到文字編輯器：

    ```xml
    <GroupConfiguration>
    <accessgroup desc = "S-1-5-32-544">
        <group action = "U" />
        <add member = "AzureAD\bob@contoso.com"/>
        <add member = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX"/>
    </accessgroup>
    </GroupConfiguration>
    ```
2. 將預留位置 SID (S-1-12-1) 取代為**Azure AD Group SID**，然後將檔案儲存**為**XML;例如，aad-local-admin.xml。

      > [!NOTE]
      > 雖然應該透過其 SID 指定群組，但如果您想要直接新增 Azure 使用者，請以此格式指定其使用者主體名稱 (UPNs) UPNs： `<member name = "AzureAD\user@contoso.com" />`

## <a name="create-custom-configuration-profile"></a>建立自訂群組組設定檔

1. 在 端點管理員中，選取**DevicesConfiguration**  >  **設定檔**  >  **建立設定檔**。
2. 在平臺下選取**Windows 10及稍後。** 在設定檔下， **選取自訂**，然後選取建立 **。**
3. 新增名稱和描述，然後選取下 **一步。**
4. 在**設定設定**  >  **OMA-URI 設定****，選取新增**。
5. 在新增列窗格中，新增名稱，在     **OMA-URI**下，新增下列字串：

    ```OMA-URI
     ./Device/Vendor/MSFT/Policy/Config/LocalUsersAndGroups/Configure
    ```

> [!NOTE]
> **RestrictedGroups/ConfigureGroupMembership**策略設定也可讓您將成員 (或AAD群組) 到Windows 10群組。 不過，它只允許以新成員完全取代現有的群組。 您無法選擇性地新增或移除成員。  2020 Windows 10 團隊版 2 提供，建議您使用**LocalUsers 和Groups**策略設定，而不是限制群組原則設定。 將兩個原則設定Surface Hub不支援，並可能導致無法預測的結果。

6. 在資料類型下，選取 **字串 XML** 並流覽以開啟您于上一個步驟中建立之 XML 檔案。

     ![上傳本地系統管理員 xml 設定檔。](images/sh-local-admin-config.png)

7. 按一下 [儲存]****。
8. 按一下 **[選取群組以包含**及選擇[](#create-security-group-for-surface-hub-devices)您先前在 (Surface Hub**中**) 。 按 **\[下一步\]**。
9. 在適用規則下，依需要新增規則。 否則，請選取 **下一** 步，然後選取 **建立**。

若要深入瞭解使用 OMA-URI 字串的自訂設定設定檔，[請參閱在 Intune Windows 10裝置使用自訂設定](/mem/intune/configuration/custom-settings-windows-10)。

## <a name="non-global-admins-managing-surface-hub"></a>管理帳戶的非全域系統管理員Surface Hub

現在，**Surface Hub系統管理員**安全性群組的成員就可以在 設定 上Surface Hub並管理設定。

> [!IMPORTANT]
> 全域系統管理員對應用程式的預設設定會 (，除非他們也是這個新安全性群組) 。
