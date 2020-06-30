---
title: 使用 Microsoft Store for Business 或 Microsoft Store for 教育版（Surface）部署 Surface app
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
ms.openlocfilehash: e25e146de49110dca1fea797f9630d9fa2d953e3
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831405"
---
# 使用 Microsoft Store for Business 和教育版部署 Surface app

**適用於**

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

使用 Windows Update 的客戶通常會接收 Surface app 作為自動更新的一部分。 但是，如果您的組織準備將影像部署至 Surface 裝置，您可能會想要在您的影像和部署程式中包含 Surface 應用程式（先前稱為 Surface 中樞），而不需要每個獨立裝置的使用者從 Microsoft 網上商店或您的 Microsoft 網上商店下載並安裝應用程式。 

> [!NOTE]
> 本文不適用於 Surface Pro X。如需詳細資訊，請參閱[部署、管理及維護 Surface Pro X](surface-pro-arm-app-management.md)

## Surface app 概覽

您可以從[Microsoft 網上商店](https://www.microsoft.com/store/apps/Surface/9WZDNCRFJB8P)免費下載 Surface app。 使用者可以從 Microsoft 網上商店下載並安裝它，但如果您的組織使用的是商務用 Microsoft Store，您將需要將它新增到您的商店庫存，並可能包含 app 做為您的 Windows 部署程式。 本文將討論這些程式。 如需 Microsoft 網上商店的詳細資訊，請參閱 Windows 技術中心的[Microsoft 商務用商店](https://docs.microsoft.com/microsoft-store/)。 

## 將 Surface 應用程式新增至 Microsoft Store for Business 帳戶 

在使用者可以從公司的 Microsoft 網上商店帳戶安裝或部署應用程式之前，必須先將所需的應用程式提供給企業的使用者並獲得授權。 

1. 如果您尚未這麼做，請建立[商務用 Microsoft Store 帳戶](https://www.microsoft.com/business-store)。 

2. 登入入口網站。 

3. 啟用離線授權：按一下 [**管理]->[儲存設定**]，然後選取 [將**離線授權的 app 顯示給在市集中購物的人員**] 核取方塊，如圖1所示。 如需 Microsoft Store for Business 應用程式授權模型的詳細資訊，請參閱[商務用 Microsoft store 中的 app 與教育](https://docs.microsoft.com/microsoft-store/)版。<br/> <br/>
   ![[顯示離線授權應用程式] 核取方塊](images/deploysurfapp-figure1-enablingapps.png "Show offline licenses apps checkbox")<br/>
   *圖 1。 啟用 app 供離線使用*

4. 若要將 Surface app 新增至您的 Microsoft Store for Business 帳戶，請遵循此程式：
    * 按一下 [**車間**] 功能表。
    * 在 [搜尋] 方塊中，輸入 [ **Surface app**]，然後按一下 [搜尋] 圖示。
    * 在搜尋結果中呈現 Surface 應用程式後，請按一下 app 的圖示。
    * 您會看到選項（選取 [**線上**] 或 [**離線**]），如圖2所示。<br/><br/>
    
    ![選取離線授權模式，並將應用程式新增至您的庫存](images/deploysurfapp-fig2-selectingofflinelicense.png "Select the Offline licensing mode and add the app to your inventory")
    
    *圖 2. 選取離線授權模式，並將應用程式新增至您的庫存*
    
    * 按一下 [**離線**]，選取 [離線授權模式]。
    * 按一下 **[取得應用程式**]，將 app 新增至您的商務用 Microsoft 市集中庫存。 如圖3所示，您會看到一個對話方塊，提示您確認離線應用程式可以使用管理工具部署，或從其私人商店中的公司庫存頁面下載。
    
    ![離線授權應用程式確認視窗](images/deploysurfapp-fig3-acknowledge.png "Offline-licensed app acknowledgement window")
    
    *圖 3. 離線授權應用程式確認*
    * 按一下 \[確定\] ****。

## 從 Microsoft Store for Business 帳戶下載 Surface 應用程式
在離線模式中，將 app 新增至商務用 Microsoft Store 帳戶之後，您就可以將 app 作為 .Appxbundle 下載並新增到部署共用中。
1. 登入 Microsoft 網上商店企業版帳戶 https://businessstore.microsoft.com 。
2. 按一下 [**管理]->應用程式 & 軟體**。 隨即會顯示您公司所有 app 的清單，包括您在 [新增 Surface 應用程式] 中新增的 Surface app 至本文的 [[商務用 Microsoft Store 帳戶](#add-surface-app-to-a-microsoft-store-for-business-account)] 區段。
3. 在 [**動作**] 底下，按一下省略號（**...**），然後按一下 [**下載以供離線使用**] 進行 Surface app。
4. 從選取的應用程式可用的選項中，選取 [所需的**平臺**與**體系結構**選項]，如圖4所示。

    ![在 .Appxbundle 套件中的範例](images/deploysurfapp-fig4-downloadappxbundle.png "Example of the AppxBundle package")

    *圖 4. 下載應用程式的 .Appxbundle 套件*
5. 按一下 [**下載**]。 將會下載 .Appxbundle 套件。 請確認您記下已下載檔案的路徑，因為您稍後會需要本文中的內容。
6. 按一下 [**編碼授權**] 或 [未**編碼的授權**] 選項。 使用 [編碼授權] 選項搭配 Microsoft 端點設定管理員之類的管理工具，或者當您使用 Windows 配置設計工具建立配套件時。 如果您使用部署影像服務與管理（DISM），或是根據影像（包括 Microsoft 部署工具箱（MDT））部署解決方案，請選取 [未編碼的授權] 選項。
7. 按一下 [**產生**]，以產生並下載 app 的授權。 請確認您記下授權檔案的路徑，因為您稍後會需要本文中的內容。

>[!NOTE]
>當您下載 app 供離線使用時（例如 Surface app），您可能會注意到頁面底部的 [**必要的框架**] 中有一個區段。 您的目的電腦必須已安裝應用程式的框架才能執行，因此您可能需要針對您的體系結構（x86 或 x64）所需的每一個架構重複下載程式，並將它們包含在本文稍後所述的 Windows 部署中。

圖5顯示 Surface app 所需的框架。

![Surface app 所需的框架](images/deploysurfapp-fig5-requiredframework.png "Required frameworks for the Surface app")

*圖 5. Surface app 所需的框架*

>[!NOTE]
>Surface app 與必要框架的版本號碼會隨著 app 更新而變更。 在 Microsoft Store for Business 中查看最新版本的 Surface 應用程式和每個架構。 使用 Microsoft Store for Business 所提供的 Surface app 和建議架構版本。 使用過時的框架或不正確的版本，可能會導致錯誤或應用程式當機。

若要下載 Surface app 所需的架構，請遵循下列步驟：
1. 按一下 [VCLibs] 下的 [**下載**] 按鈕， **0_x64__8wekyb3d8bbwe 14.0.23816**]。 這會下載 VCLibs. 140.00 _ 14.0.23816 0_x64__8wekyb3d8bbwe。Appx 檔案移至您指定的資料夾。
2. 按一下 [ **0_x64__8wekyb3d8bbwe 1.1.23406**] 底下的 [**下載**] 按鈕。 這會將 0_x64__8wekyb3d8bbwe .Appx 檔案下載到您指定的資料夾中（1.1.23406）。

>[!NOTE]
>表面裝置只需要每個架構的64位（x64）版本。 Surface 裝置是原始的64位 UEFI 裝置，且與需要32位架構的32位（x86）版本不相容。 

## 使用 PowerShell 在您的電腦上安裝 Surface 應用程式
下列程式會將 Surface 應用程式置備到您的電腦，並將它提供給電腦之後所建立的任何使用者帳戶。
1. 若要使用本文所述的 [[如何從 Microsoft Store For Business 帳戶下載 surface app](#download-surface-app-from-a-microsoft-store-for-business-account) ] 區段所述的程式，請下載 Surface app .appxbundle 和授權檔案。 
2. 開始已提升權限的 PowerShell 工作階段。

    >[!NOTE]
    >如果您不是以系統管理員身分執行 PowerShell，會話就不會有安裝 app 所需的許可權。
    
3. 在提升權限的 PowerShell 工作階段中，複製和貼上下列命令︰
    ```
    Add-AppxProvisionedPackage –Online –PackagePath <DownloadPath>\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath <DownloadPath>\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

    其中 `<DownloadPath>` 是您從 Microsoft Store For Business 帳戶下載 .appxbundle 和授權檔案的資料夾。

    例如，如果您將檔案下載到 C：\Temp，您執行的命令就是：
    ````
    Add-AppxProvisionedPackage –Online –PackagePath c:\Temp\ Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle –LicensePath c:\Temp\ Microsoft.SurfaceHub_8wekyb3d8bbwe_a53ef8ab-9dbd-dec1-46c5-7b664d4dd003.xml
    ```

4. The Surface app will now be available on your current Windows computer. 

Before the Surface app is functional on the computer where it has been provisioned, you must also provision the frameworks described earlier in this article. To provision these frameworks, use the following procedure in the elevated PowerShell session you used to provision the Surface app.

5. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.VCLibs.140.00_14.0.23816.0_x64__8wekyb3d8bbwe.Appx
   ```
6. In the elevated PowerShell session, copy and paste the following command:
   ```
   Add-AppxProvisionedPackage –Online –SkipLicense –PackagePath <DownloadPath>\Microsoft.NET.Native.Runtime.1.1_1.1.23406.0_x64__8wekyb3d8bbwe.Appx
   ```

## Install Surface app with MDT
The following procedure uses MDT to automate installation of the Surface app at the time of deployment. The application is provisioned automatically by MDT during deployment and thus you can use this process with existing images. This is the recommended process to deploy the Surface app as part of a Windows deployment to Surface devices because it does not reduce the cross platform compatibility of the Windows image.
1. Using the procedure described [earlier in this article](#download-surface-app-from-a-microsoft-store-for-business-account), download the Surface app AppxBundle and license file. 
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page of the New Application Wizard, specify the default **Working Directory** and for the **Command** specify the file name of the AppxBundle, as follows:

   * Command:
     ```
     Microsoft.SurfaceHub_10.0.342.0_neutral_~_8wekyb3d8bbwe.AppxBundle
     ```
   * Working Directory: %DEPLOYROOT%\Applications\SurfaceApp

For the Surface app to function on the target computer, it will also require the frameworks described earlier in this article. Use the following procedure to import the frameworks required for the Surface app into MDT and to configure them as dependencies.
1. Using the procedure described earlier in this article, download the framework files. Store each framework in a separate folder.
2. Using the New Application Wizard in the MDT Deployment Workbench, import the downloaded files as a new **Application with source files**.
3. On the **Command Details** page, type the file name of each application you downloaded in the **Command** field and the default Working Directory.

To configure the frameworks as dependencies of the Surface app, use this process:
1. Open the properties of the Surface app in the MDT Deployment Workbench.
2. Click the **Dependencies** tab, and then click **Add**.
3. Select the check box for each framework using the name you provided in the New Application Wizard.

After import, the Surface app will be available for selection in the **Applications** step of the Windows Deployment Wizard. You can also install the application automatically by specifying the application in the deployment task sequence by following this process:
1. Open your deployment task sequence in the MDT Deployment Workbench.
2. Add a new **Install Application** task in the **State Restore** section of deployment.
3. Select **Install a single application** and specify the **Surface App** as the **Application to be installed**.

For more information about including apps into your Windows deployments, see [Deploy Windows 10 with the Microsoft Deployment Toolkit](https://technet.microsoft.com/itpro/windows/deploy/deploy-windows-10-with-the-microsoft-deployment-toolkit).
