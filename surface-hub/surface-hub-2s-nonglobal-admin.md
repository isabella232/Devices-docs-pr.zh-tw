---
title: 在 Surface Hub 2S 上設定非全域系統管理員帳戶
description: 本文說明如何設定非全域系統管理員帳戶來管理 Surface Hub 2S。
keywords: Surface Hub 2S
ms.prod: surface-hub
ms.sitesec: library
author: greg-lindsay
ms.author: greglin
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 12/07/2020
ms.localizationpriority: Medium
appliesto:
- Surface Hub 2S 2020 Update
ms.openlocfilehash: e16e4f8bd4b2b253233fa9790987287cf17966c7
ms.sourcegitcommit: 7e1b351024e33926901ddbdc562ba12aea0b4196
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/03/2021
ms.locfileid: "11385171"
---
# <a name="configure-non-global-admin-accounts-on-surface-hub-2s"></a>在 Surface Hub 2S 上設定非全域系統管理員帳戶

當您將 Surface Hub 2S 加入 Azure AD 網域時，您可以設定非全域系統管理員帳戶，以限制 Surface Hub 2S 上的設定應用程式管理許可權。 這可讓您只將 Surface Hub 2S 的系統管理員許可權範圍範圍，並防止整個 Azure AD 網域可能不需要的系統管理員存取權。 開始之前，請確定 Surface Hub 2S 已加入 Azure AD。 如果沒有，您必須重設 Surface Hub 2S，並完成第一次開箱即用 (OOBE) 安裝程式，加入宣告 Azure AD 的選項。

## <a name="summary"></a>摘要 

建立非全域系統管理員帳戶的過程涉及下列步驟： 

1. 在 Microsoft Intune 中，建立一個安全性群組，其中包含指定管理 Surface Hub 2S 的系統管理員。
2. 使用 PowerShell 取得 Azure AD 群組 SID。
3. 建立包含 Azure AD 群組 SID 的 XML 檔案。
4. 建立一個安全性群組，其中包含由非全域系統管理員安全性群組管理的 Surface Hub 2S 裝置。
5. 建立自訂群組設定檔，以鎖定包含 Surface Hub 2S 裝置的安全性群組。 


## <a name="create-azure-ad-security-groups"></a>建立 Azure AD 安全性群組

首先建立包含系統管理員帳戶的安全性群組。 然後為 Surface Hub 裝置建立另一個安全性群組。  

### <a name="create-security-group-for-admin-accounts"></a>為系統管理員帳戶建立安全性群組

1. 透過[Microsoft 端點](https://go.microsoft.com/fwlink/?linkid=2109431)管理員系統管理中心進入 Intune，選取群組新群組>群組類型下****  >  ** **，選取**安全性。** 
2. 輸入組名 ，例如 **Surface Hub Local Admins，** 然後選取建立 **。** 

     ![為中樞系統管理員建立安全性群組](images/sh-create-sec-group.png)

3. 開啟群組，選取**成員**，然後選擇新增成員，**** 以在 Surface Hub 2S 上輸入要指定為非全域系統管理員的系統管理員帳戶。 若要深入瞭解在 Intune 中建立群組，請參閱新增  [群組以整理使用者和裝置](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。

### <a name="create-security-group-for-surface-hub-2s-devices"></a>為 Surface Hub 2S 裝置建立安全性群組

1. 重複上述程式，為中樞裝置建立個別的安全性群組;例如 **Surface Hub 裝置**。 

     ![為中樞裝置建立安全性群組](images/sh-create-sec-group-devices.png) 

## <a name="obtain-azure-ad-group-sid-using-powershell"></a>使用 PowerShell 取得 Azure AD 群組 SID

1. 以提升的帳戶許可權啟動 PowerShell (**以** 系統管理員) 並確保您的系統已設置為執行 PowerShell 腳本。 若要深入瞭解，請參閱關於 [執行策略](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。 
2. [安裝 Azure PowerShell 模組](https://docs.microsoft.com/powershell/azure/install-az-ps)。
3. 請登錄您的 Azure AD 租使用者。

    ```powershell
    Connect-AzureAD
    ```

4. 當您已進入租使用者時，請執行下列命令小程式。 它會提示您「請輸入 Azure AD 群組的物件識別碼」。

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. 在 Intune 中，選取您先前所建立群組，然後複製物件識別碼，如下圖所示。 

     ![複製安全性群組的物件識別碼](images/sh-objectid.png)

6. 執行下列命令小程式以取得安全性群組之 SID：

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. 將物件識別碼貼到 PowerShell 命令小程式，按 **Enter，** 然後將 **Azure AD 群組 SID** 複製到文字編輯器中。 

## <a name="create-xml-file-containing-azure-ad-group-sid"></a>建立包含 Azure AD 群組 SID 的 XML 檔案

1. 將下列內容複寫到文字編輯器中： 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. 將預留位置 SID (S-1-12-1) 取代為 Azure **AD Group SID，** 然後將檔案另存為 XML;例如 **，aad-local-admin.xml。** 

## <a name="create-custom-configuration-profile"></a>建立自訂群組設定檔

1. 在端點管理員中，選取**裝置**  >  **組組設定檔**  >  **建立設定檔**。 
2. 在平臺下 **選取 Windows 10 及更新版本。** 在設定檔下，選取 **自訂**，然後選取建立 **。**
3. 新增名稱和描述，然後選取下 **一步。**
4. 在**設定設定**  >  **OMA-URI**設定**** 下，選取新增。
5. 在新增列窗格中新增名稱，在     **OMA-URI**下新增下列字串： 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. 在資料類型下，選取 **字串 XML** 並流覽以開啟您于上一個步驟中建立 XML 檔案。 

     ![上傳本地系統管理員 xml 設定檔](images/sh-local-admin-config.png)

7. 按一下 [儲存]****。
8. 按一下 **[選取群組以包含**及選擇您先前在**Surface Hub**裝置[上 (](#create-security-group-for-surface-hub-2s-devices)的安全) 。 按 **\[下一步\]**。
9. 在可適用性規則下，依需要新增規則。 否則，請選取下**一步****，然後選取**建立。

若要深入瞭解使用 OMA-URI 字串的自訂群組設定設定檔，請參閱在 Intune 中為 [Windows 10 裝置使用自訂設定](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。


## <a name="non-global-admins-managing-surface-hub-2s"></a>管理 Surface Hub 2S 的非全域系統管理員

Surface **Hub Local Admins** Security 群組的成員現在可以在 Surface Hub 2S 上，以登錄設定應用程式並管理設定。
