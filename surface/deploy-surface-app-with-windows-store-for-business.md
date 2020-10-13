---
title: 使用 Microsoft Store for Business 或 Microsoft Store for 教育 (Surface) 部署 Surface app
description: 瞭解如何使用 Microsoft Store for Business 或 Microsoft Store for 教育，以及使用 PowerShell 和 MDT 安裝 Surface app 來新增和下載 Surface app。
keywords: surface app、app、部署、自訂
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, store
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.localizationpriority: medium
ms.audience: itpro
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: 811feff1f0643ab0ba5d624c5f7d561ba5b0cd4d
ms.sourcegitcommit: c1efb75e8524193bdc0a5f7496dc23a92ac665c8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2020
ms.locfileid: "11114711"
---
# 使用 Microsoft Store for Business 和教育版部署 Surface app

**適用於**

- Surface 膝上型電腦前往
- Surface Pro 7
- Surface 膝上型電腦3
- Surface Pro 6
- Surface Laptop 2
- Surface Go
- 使用 LTE 的 Surface
- Surface Book 2
- 配備 LTE Advanced 的 Surface Pro (型號 1807)
- Surface Pro (型號 1796)
- Surface 膝上型電腦
- Surface Studio
- Surface Studio 2
- Surface Book
- Surface Pro 4
- Surface 3 LTE
- Surface 3
- Surface Pro 3


Surface app 是一個可讓您控制許多 Surface 特定設定和選項的輕型 Microsoft Store 應用程式，包括： 

* 啟用或停用 Surface 裝置上的 Windows 鍵 

* 調整 Surface 手寫筆的敏感度 

* 自訂 Surface 手寫筆按鈕動作 

* 啟用或停用 Surface 音訊增強功能 

* 快速存取您裝置的支援檔與資訊

使用 Windows Update 的客戶通常會接收 Surface app 作為自動更新的一部分。 但如果您的組織準備將影像部署至 Surface 裝置，您可能會想要在您的影像和部署程式中包含 surface 應用程式 (先前稱為 Surface Hub) ，而不需要每個人裝置的使用者從 Microsoft 網上商店或您的 Microsoft 網上商店下載並安裝應用程式。 

> [!NOTE]
> 本文不適用於 Surface Pro X。如需詳細資訊，請參閱 [部署、管理及維護 Surface Pro X](surface-pro-arm-app-management.md)

## Surface app 概覽

您可以從 [Microsoft 網上商店](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)免費下載 Surface app。 使用者可以從 Microsoft 網上商店下載並安裝它，但如果您的組織使用的是商務用 Microsoft Store，您將需要將它新增到您的商店庫存，並可能包含 app 做為您的 Windows 部署程式。 本文將討論這些程式。 如需 Microsoft 網上商店的詳細資訊，請參閱 Windows 技術中心的 [Microsoft 商務用商店](https://docs.microsoft.com/microsoft-store/) 。 

## 將 Surface 應用程式新增至 Microsoft Store for Business 帳戶 

在使用者可以從公司的 Microsoft Store for Business 帳戶安裝或部署應用程式之前，必須先將所需的應用程式 (s) 提供給企業的使用者，然後授權給他們。 

1. 如果您尚未這麼做，請建立 [商務用 Microsoft Store 帳戶](https://www.microsoft.com/business-store)。 

2. 登入入口網站。 

3. 啟用離線授權：按一下 [ **管理]->[儲存設定**]，然後選取 [將 **離線授權的 app 顯示給在市集中購物的人員** ] 核取方塊，如圖1所示。 如需 Microsoft Store for Business 應用程式授權模型的詳細資訊，請參閱 [商務用 Microsoft store 中的 app 與教育](https://docs.microsoft.com/microsoft-store/)版。

   > [!div class="mx-imgBorder"]
   > ![[顯示離線授權應用程式] 核取方塊](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *圖 1。 啟用 app 供離線使用*

4. 若要將 Surface app 新增至您的 Microsoft Store for Business 帳戶，請遵循此程式：

    * 按一下 [ **車間** ] 功能表。
    
    * 在 [搜尋] 方塊中，輸入 [ **Surface app**]，然後按一下 [搜尋] 圖示。
    
    * 在搜尋結果中呈現 Surface 應用程式後，請按一下 app 的圖示。
    
    * 您會看到一個選項 (選取 [ **線上** ] 或 [ **離線** ]) ，如圖2所示。
    
      > [!div class="mx-imgBorder"]
      > ![選取離線授權模式，並將應用程式新增至您的庫存](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")   
      *圖 2. 選取離線授權模式，並將應用程式新增至您的庫存*
    
    * 按一下 [ **離線** ]，選取 [離線授權模式]。
    
    * 按一下 **[取得應用程式** ]，將 app 新增至您的商務用 Microsoft 市集中庫存。 如圖3所示，您會看到一個對話方塊，提示您確認離線應用程式可以使用管理工具部署，或從其私人商店中的公司庫存頁面下載。
    
      > [!div class="mx-imgBorder"]
      > ![離線授權的 app 確認視窗： ](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
       *圖3。離線授權應用程式確認*
      
    * 按一下**確定**。

## 從 Microsoft Store for Business 帳戶下載 Surface 應用程式
在離線模式中，將 app 新增至商務用 Microsoft Store 帳戶之後，您就可以將 app 作為 .Appxbundle 下載並新增到部署共用中。

1. 登入 Microsoft 網上商店企業版帳戶 https://businessstore.microsoft.com 。

2. 按一下 [ **管理]->應用程式 & 軟體**。 隨即會顯示您公司所有 app 的清單，包括您在 [新增 Surface 應用程式] 中新增的 Surface app 至本文的 [ [商務用 Microsoft Store 帳戶](#add-surface-app-to-a-microsoft-store-for-business-account) ] 區段。

3. 在 [ **動作**] 底下，按一下省略號 (**...**) ，然後按一下 Surface app 的 [ **離線使用** ]。

4. 從選取的應用程式可用的選項中，選取 [所需的 **平臺** 與 **體系結構** 選項]，如圖4所示。

    > [!div class="mx-imgBorder"]
    > ![在 .Appxbundle 套件中的範例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")<br/>
    *圖 4. 下載應用程式的 .Appxbundle 套件*
    
5. 按一下 [ **下載**]。 將會下載 .Appxbundle 套件。 請確認您記下已下載檔案的路徑，因為您稍後會需要本文中的內容。

6. 按一下 [ **編碼授權** ] 或 [未 **編碼的授權** ] 選項。 使用 [編碼授權] 選項搭配 Microsoft 端點設定管理員之類的管理工具，或者當您使用 Windows 配置設計工具建立配套件時。 如果您使用部署映射服務與管理 (DISM) 或以影像為基礎的部署解決方案（包括 Microsoft 部署工具套件 (MDT) ），請選取 [未加上授權] 選項。

7. 按一下 [ **產生** ]，以產生並下載 app 的授權。 請確認您記下授權檔案的路徑，因為您稍後會需要本文中的內容。

>[!NOTE]
>當您下載 app 供離線使用時（例如 Surface app），您可能會注意到頁面底部的 [ **必要的框架**] 中有一個區段。 您的目的電腦必須已安裝應用程式的框架才能執行，因此您可能需要針對架構的每一個所需架構， (x86 或 x64) 中重複下載程式，也可以將它們包含在本文稍後討論的 Windows 部署中。

圖5顯示 Surface app 所需的框架。

> [!div class="mx-imgBorder"]
> ![Surface app 所需的框架](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")<br/>
*圖 5. Surface app 所需的框架*

>[!NOTE]
>Surface app 與必要框架的版本號碼會隨著 app 更新而變更。 在 Microsoft Store for Business 中查看最新版本的 Surface 應用程式和每個架構。 使用 Microsoft Store for Business 所提供的 Surface app 和建議架構版本。 使用過時的框架或不正確的版本，可能會導致錯誤或應用程式當機。

若要下載 Surface app 所需的架構，請遵循下列步驟：

1. 按一下 [VCLibs] 底下的 [ **下載** ] 按鈕 **140.00 _14. 0 23816 _x64__8wekyb3d8bbwe**。 這會下載 VCLibs 140.00 _14. 0 23816 _x64__8wekyb3d8bbwe。Appx 檔案移至您指定的資料夾。

2. 按一下 [23406] 底下的 [ **下載** ] 按鈕 **1.1 版. 1. 0 _x64__8wekyb3d8bbwe**。 這會將 23406 _x64__8wekyb3d8bbwe .Appx 檔案下載到您指定的資料夾中（& 1.）。

>[!NOTE]
>在 Surface 裝置上，只需要每個架構的64位 (x64) 版本。 Surface 裝置是原生64位 UEFI 裝置，且與32位 (x86) 版本的 Windows （需要32位架構）不相容。 

## 使用 PowerShell 在您的電腦上安裝 Surface 應用程式
下列程式會將 Surface 應用程式置備到您的電腦，並將它提供給電腦之後所建立的任何使用者帳戶。

1. 若要使用本文所述的 [ [如何從 Microsoft Store For Business 帳戶下載 surface app](#download-surface-app-from-a-microsoft-store-for-business-account) ] 區段所述的程式，請下載 Surface app .appxbundle 和授權檔案。 

2. 開始已提升權限的 PowerShell 工作階段。

    >[!NOTE]
    >如果您不是以系統管理員身分執行 PowerShell，會話就不會有安裝 app 所需的許可權。
    
3. 在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰

    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    其中 `<DownloadPath>` 是您從 Microsoft Store For Business 帳戶下載 .appxbundle 和授權檔案的資料夾。

    例如，如果您將檔案下載到 C：\Temp，您執行的命令就是：
    
    ```powershell
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. 現在可在您目前的 Windows 電腦上使用 Surface app。 

   您也必須先提供本文先前所述的架構，才能讓 Surface app 在已設定的電腦上正常運作。 若要設定這些架構，請在您用來置備 Surface 應用程式的提升 PowerShell 會話中使用下列程式。

5. 在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
   
6. 在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰

   ```powershell
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## 使用 MDT 安裝 Surface 應用程式
下列程式會使用 MDT，在部署時自動安裝 Surface app。 應用程式會由 MDT 在部署期間自動佈建，因此您可以利用這個程序搭配現有映像。 此程式是將 Surface app 部署為 Windows 部署至 Surface 裝置的建議程式，因為它不會降低 Windows 影像的跨平臺相容性。

1. 使用 [本文先前](#download-surface-app-from-a-microsoft-store-for-business-account)所述的程式，下載 Surface app .appxbundle 和授權檔案。 

2. 使用 MDT 部署工作臺中的 [新增應用程式] 嚮導，將下載的檔案匯入為含有來源檔案的新 **應用程式**。

3. 在 [新增應用程式] 嚮導的 [ **命令詳細資料** ] 頁面上，指定預設的 **工作目錄** ，然後針對 **命令** 指定您的 .appxbundle 檔案名，如下所示：

   * 命令
   
     ```console
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
     
   * 工作目錄：%DEPLOYROOT%\Applications\SurfaceApp

為了讓 Surface 應用程式在目的電腦上正常運作，您也需要本文前面所述的框架。 使用下列程式將 Surface app 所需的框架匯入到 MDT，並將其設定為相依性。

1. 使用本文先前所述的程式下載架構檔案。 將每個架構儲存在另一個資料夾中。

2. 使用 MDT 部署工作臺中的 [新增應用程式] 嚮導，將下載的檔案匯入為含有來源檔案的新 **應用程式**。

3. 在 [ **命令詳細資料** ] 頁面上，輸入您在 **命令** 欄位中下載的每個應用程式的檔案名和預設的工作目錄。

若要將框架設定為 Surface app 的相依性，請使用此程式：

1. 在 MDT 部署工作臺中開啟 Surface 應用程式的屬性。

2. 按一下 [ **依賴性** ] 索引標籤，然後按一下 [ **新增**]。

3. 使用您在新的應用程式精靈中所提供的名稱，選取每個架構的核取方塊。

匯入之後，就可以在 Windows 部署嚮導的 [ **應用程式** ] 步驟中選取 Surface app。 您也可以依照下列程序，在部署工作順序中指定應用程式來自動安裝應用程式：

1. 在 MDT Deployment Workbench 中開啟部署工作順序。

2. 在部署的 [State Restore]**** (狀態還原) 區段中新增新的 [Install Application]**** (安裝應用程式) 工作。

3. 選取 [ **安裝單一應用程式** ]，然後指定 **Surface App** 作為 **要安裝的應用程式**。

如需將 app 納入 Windows 部署的詳細資訊，請參閱 [使用 Microsoft 部署工具組部署 Windows 10](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit)。
