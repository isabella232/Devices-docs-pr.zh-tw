---
title: 在 Surface Hub 2 秒設定非全域管理員帳戶
description: 本文說明如何設定非全域管理員帳戶來管理 Surface Hub 2 秒。
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
ms.openlocfilehash: 647a7bf53e5ca8dc52ddec21ec8393cc574ee95a
ms.sourcegitcommit: 16cc2e8d9dfc5d6e061e0b5b6ddfcf35547643f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2020
ms.locfileid: "11196792"
---
# 在 Surface Hub 2 秒設定非全域管理員帳戶

當您將 Surface Hub 秒數連接至 Azure AD 網域時，您可以設定非全域管理員帳戶，限制在 Surface Hub 2 的設定應用程式管理許可權。 這可讓您只對 Surface Hub 2 的作用域管理員許可權，並防止可能不需要的管理員存取整個 Azure AD 網域。 開始之前，請確定您的 Surface Hub 秒已連接至 Azure AD。 如果不是，您將需要重設 Surface Hub 2，並完成第一次、現成的 (OOBE) 安裝程式，加入宣告 Azure AD 的選項。

## 摘要 

建立非全域系統管理員帳戶的套裝程式含下列步驟： 

1. 在 Microsoft Intune 中，建立包含指定要管理 Surface Hub 2 秒的管理員的安全性群組。
2. 使用 PowerShell 取得 Azure AD 群組 SID。
3. 建立包含 Azure AD 群組 SID 的 XML 檔案。
4. 建立包含由非全域系統管理員安全性群組管理的 Surface Hub 2 裝置的安全性群組。
5. 建立針對內含 Surface Hub 2 裝置之安全性群組的自訂設定檔。 


## 建立 Azure AD 安全性群組

首先，建立包含管理員帳戶的安全性群組。 然後為 Surface Hub 裝置建立另一個安全性群組。  

### 建立管理員帳戶的安全性群組

1. 透過[Microsoft 端點管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)登入 Intune，選取 [**群組**  >  **新群組**] >，然後在 [群組類型] 底下，選取 [**安全性]。** 
2. 輸入組名（例如 **Surface Hub 本機管理員** ），然後選取 [ **建立]。** 

     ![建立中樞管理員的安全性群組](images/sh-create-sec-group.png)

3. 開啟 [群組]，選取 [ **成員**]，然後選擇 [ **新增成員** ]，輸入您想要指定為「Surface Hub」的非全域管理員的系統管理員帳戶。 若要深入瞭解如何在 Intune 中建立群組，請參閱  [新增群組以組織使用者和裝置](https://docs.microsoft.com/mem/intune/fundamentals/groups-add)。

### 建立 Surface Hub 2 裝置的安全性群組

1. 重複上述程式來為中樞裝置建立個別的安全性群組;例如， **Surface Hub 裝置**。 

     ![建立中樞裝置的安全性群組](images/sh-create-sec-group-devices.png) 

## 使用 PowerShell 取得 Azure AD 群組 SID

1. 使用提升的帳戶許可權啟動 PowerShell， (**以系統管理員身分執行**) ，並確保您的系統已設定為執行 PowerShell 腳本。 若要深入瞭解，請參閱 [關於執行原則](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies?)。 
2. [安裝 Azure PowerShell 模組](https://docs.microsoft.com/powershell/azure/install-az-ps)。
3. 登入您的 Azure AD 租使用者。

    ```powershell
    Connect-AzureAD
    ```

4. 當您登入您的租使用者時，請執行下列 commandlet。 它會提示您 [請輸入您的 Azure AD 群組的物件識別碼]。

    ```powershell
    function Convert-ObjectIdToSid
    {    param([String] $ObjectId)   
         $d=[UInt32[]]::new(4);[Buffer]::BlockCopy([Guid]::Parse($ObjectId).ToByteArray(),0,$d,0,16);"S-1-12-1-$d".Replace(' ','-')
         
    }
    ```

5. 在 Intune 中，選取您先前建立的群組，然後複製物件識別碼，如下圖所示。 

     ![複製安全性群組的物件識別碼](images/sh-objectid.png)

6. 執行下列 commandlet 來取得安全性群組的 SID：

    ```powershell
    $AADGroup = Read-Host "Please type the Object ID of your Azure AD Group"
    $Result = Convert-ObjectIdToSid $AADGroup
    Write-Host "Your Azure Ad Group SID is" -ForegroundColor Yellow $Result
    ```
    
7. 將物件識別碼貼到 PowerShell commandlet 中，按 **enter**，然後將 **AZURE AD 群組 SID** 複製到文字編輯器。 

## 建立包含 Azure AD 群組 SID 的 XML 檔

1. 將下列內容複寫到文字編輯器中： 

    ```xml
      <groupmembership>   
      <accessgroup desc = "Administrators">        
      <member name = "Administrator" />        
      <member name = "S-1-12-1-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX-XXXXXXXXXX" />  
      </accessgroup>
      </groupmembership>
      ```

2. 使用您的 **AZURE AD 群組 SID** 來取代以 S-1-12-1) 開頭的預留位置 (SID，然後將檔案儲存為 XML;例如， **aad-local-admin.xml**。 

## 建立自訂設定檔

1. 在端點管理員中，選取 [**裝置**設定配置  >  **檔**]  >  **建立設定檔**。 
2. 在 [平臺] 底下，選取 [ **Windows 10 及更新版本]。** 選取 [設定檔] 底下的 [ **自訂**]，然後選取 [ **建立]。**
3. 新增名稱和描述，然後選取 **[下一步]。**
4. 在 [**設定設定**  >  **OMA-URI 設定**] 底下，選取 [**新增**]。
5. 在 [Add Row] （新增列）窗格中，新增名稱，然後在 [     **OMA URI**] 底下，新增下列字串： 

    ```OMA-URI
    ./Device/Vendor/MSFT/Policy/Config/RestrictedGroups/ConfigureGroupMembership
    ```
6. 在 [資料類型] 底下，選取 [ **字串 XML** ]，然後流覽以開啟您在上一個步驟中建立的 XML 檔案。 

     ![上傳本機系統管理 xml 設定檔](images/sh-local-admin-config.png)

7. 按一下 **[儲存]**。
8. 按一下 [ **選取要包含的群組** ]，然後選擇 [您先前建立的安全性群組](#create-security-group-for-surface-hub-2s-devices) (**Surface Hub 裝置**) 。 按 **\[下一步\]**。
9. 如有需要，請在 [適用性規則] 底下新增規則。 否則，選取 **[下一步]** ，然後選取 [ **建立**]。

若要深入瞭解使用 OMA-URI 字串自訂設定檔的詳細資訊，請參閱 [在 Intune 中使用適用于 Windows 10 裝置的自訂設定](https://docs.microsoft.com/mem/intune/configuration/custom-settings-windows-10)。


## 非全域管理員管理 Surface Hub 的2秒

**Surface hub 「本機管理員**」安全性群組的成員現在可以登入 surface hub 2 的 [設定] 應用程式，然後管理 [設定]。
