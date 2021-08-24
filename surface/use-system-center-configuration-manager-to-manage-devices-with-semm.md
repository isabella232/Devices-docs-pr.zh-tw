---
title: 搭配 SEMM 使用 Microsoft Endpoint Configuration Manager 以管理裝置
description: 瞭解如何使用端點組Enterprise管理模式管理 microsoft Surface (SEMM) 管理模式。
keywords: 註冊、更新、腳本、設定
ms.prod: w10
ms.mktglfcycl: manage
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: hachidan
manager: laurawi
ms.localizationpriority: medium
ms.audience: itpro
ms.date: 10/28/2020
ms.openlocfilehash: 3a70f08ded5ad19b8bc2dc8a7e4fe6d85d972c43
ms.sourcegitcommit: d6ac31a94b6630f04cf3469d5dcf8b66e46c7412
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11911618"
---
# <a name="use-microsoft-endpoint-configuration-manager-to-manage-devices-with-semm"></a>搭配 SEMM 使用 Microsoft Endpoint Configuration Manager 以管理裝置

Microsoft Surface Enterprise管理模式 (SEMM) Surface UEFI 裝置的功能，可讓系統管理員管理及協助保護 Surface UEFI 設定設定。 對大部分組織來說 Windows，此程式是使用 Microsoft Surface UEFI (.msi) 工具建立安裝程式套件以完成。 這些套件接著會執行或部署到用戶端 Surface 裝置，以在 SEMM 中註冊裝置，並更新 Surface UEFI 設定設定。

對於有Microsoft Endpoint Configuration Manager的組織，使用 Microsoft Surface UEFI 組.msi程式來部署和管理 SEMM。 Microsoft Surface UEFI Manager 是一種輕量型安裝程式，可在裝置上提供 SEMM 管理所需的元件。 使用 Microsoft Surface UEFI Manager 在受管理的用戶端上安裝這些程式集，SEMM 就可以由 Configuration Manager 使用 PowerShell 腳本進行管理，並部署為應用程式。 此程式在 Configuration Manager 中執行 SEMM 管理，這樣就不需要外部 Microsoft Surface UEFI Configurationator 工具。

> [!Note]
> 雖然本文所述程式可能與較舊版本的端點組組管理員或其他協力廠商管理解決方案一起使用，但 Microsoft Surface UEFI Manager 和 PowerShell 的 SEMM 管理僅受端點群組原則管理員目前分支的支援。

#### <a name="prerequisites"></a>必要條件

在開始本文所述的程式之前，請熟悉下列技術和工具：

* [Surface UEFI](manage-surface-uefi-settings.md)
* [Surface 企業管理模式 (SEMM)](surface-enterprise-management-mode.md)
* [PowerShell 腳本](/powershell)
* [使用 Configuration Manager 部署應用程式](/mem/configmgr/apps/deploy-use/deploy-applications)


> [!Note]
> 您也需要存取要用於保護 SEMM 的憑證。 有關此憑證需求的詳細資訊，請參閱 Surface [Enterprise管理模式憑證需求](surface-enterprise-management-mode.md#surface-enterprise-management-mode-certificate-requirements)。
> 
> 此憑證必須存放在安全的位置並妥善備份。這非常重要。 如果此憑證遺失或無法使用，則無法重設 Surface UEFI、變更受管理的 Surface UEFI 設定，或從註冊的 Surface 裝置移除 SEMM。

#### <a name="download-microsoft-surface-uefi-manager"></a>下載 Microsoft Surface UEFI Manager

使用 Configuration Manager 管理 SEMM 需要在每個用戶端 Surface 裝置上安裝 Microsoft Surface UEFI Manager。 您可以下載 Microsoft Surface UEFI Manager (SurfaceUEFIManager.msi) [Microsoft](https://www.microsoft.com/download/details.aspx?id=46703) 下載中心的 IT 版 Surface 工具頁面。

#### <a name="download-semm-scripts-for-configuration-manager"></a>下載 Configuration Manager 的 SEMM 腳本

在用戶端 Surface 裝置上安裝 Microsoft Surface UEFI Manager 之後，SEMM 就可以使用 PowerShell 腳本進行部署和管理。 從 IT 用 Surface Tools 下載SEMM_PowerShell.zip取得 [SEMM](https://www.microsoft.com/download/details.aspx?id=46703) 管理腳本範例。

## <a name="deploy-microsoft-surface-uefi-manager"></a>部署 Microsoft Surface UEFI Manager

Microsoft Surface UEFI Manager 的部署是典型的應用程式部署。 Microsoft Surface UEFI Manager 安裝程式檔案是一Windows安裝程式檔案，您可以使用標準靜音選項[安裝](https://msdn.microsoft.com/library/windows/desktop/aa367988)。

安裝 Microsoft Surface UEFI Manager 的命令如下所示。

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

卸載 Microsoft Surface UEFI Manager 的命令如下所示。

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

若要建立新應用程式，並部署到包含 Surface 裝置的集合，請執行下列步驟：

1. 從開始畫面或**開始**功能表開啟 Configuration Manager **Console。**
2. 選取 **視窗左** 下角的軟體庫。
3. 展開 **軟體庫** 的應用程式管理節點， **然後選取**應用程式 。
4. 選取視窗 **頂端** 的 **首頁選項卡下的** 建立應用程式按鈕。 這會啟動建立應用程式精靈。
5. 建立應用程式精靈會提供一系列步驟：

   * **一** 般 – 預設 **會選取的自動** 偵測來自安裝檔案之此應用程式的資訊選項。 在 "**類型"** 欄位中 **，Windows安裝程式 (.msi檔案) **預設也會選取。 選取 **流覽** 以流覽至 ** 並選取 **SurfaceUEFIManagerSetup.msi，然後選取 下 **一步**。
   
      > [!Note]
      > 檔案SurfaceUEFIManagerSetup.msi位於網路共用上，並位於不包含其他檔案的資料夾。 無法使用本地檔案位置。

   * **輸入資訊**- 建立應用程式精靈會剖析.msi檔案，並讀取**應用程式名稱和****產品代碼**。 SurfaceUEFIManagerSetup.msi應列為內容檔案行下的唯一 **檔案，如圖**1 所示。 選取 **下一** 步以繼續。

      ![系統會自動剖析 Surface UEFI Manager 設定的資訊。](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *圖 1。 系統會自動剖析 Microsoft Surface UEFI Manager 設定的資訊*

   * **一般** 資訊 – 您可以修改應用程式的名稱，以及發行者與版本的資訊，或在此頁面上新增批註。 Microsoft Surface UEFI Manager 的安裝命令會顯示在安裝程式欄位中。 系統安裝的預設安裝行為會允許 Microsoft Surface UEFI Manager 安裝 SEMM 所需的程式集，即使使用者未登入 Surface 裝置。 選取 **下一** 步以繼續。
   * **Summary** – The information that was parsed in the **Import Information** step and your selections from the **General Information** step is displayed on this page. 選取 **下** 一步以確認您的選取專案，然後建立應用程式。
   * **進度** – 當應用程式已導入並新到軟體文件庫時，會顯示進度列和狀態。
   * **完成** – 應用程式建立程式完成時，會顯示成功建立應用程式的確認。 選取 **關閉** 以完成建立應用程式精靈。

在 Configuration Manager 中建立應用程式之後，您可以將它發佈至您的通訊點，並將其部署到包括 Surface 裝置在內的集合。 此應用程式不會在 Surface 裝置上安裝或啟用 SEMM。 它只會提供使用 PowerShell 腳本啟用 SEMM 所需的程式集。

如果您不想在無法使用 SEMM 管理的裝置上安裝 Microsoft Surface UEFI Manager 程式集，您可以將 Microsoft Surface UEFI Manager 設定為 SEMM Configuration Manager 腳本的相依性。 本文稍後的部署 [SEMM Configuration Manager 腳本](#deploy-semm-configuration-manager-scripts) 一節將涵蓋此案例。

## <a name="create-or-modify-the-semm-configuration-manager-scripts"></a>建立或修改 SEMM Configuration Manager 腳本

在裝置上安裝必要的程式集之後，在 SEMM 中註冊裝置並配置 Surface UEFI 的程式會使用 PowerShell 腳本完成，並部署為使用 Configuration Manager 的腳本應用程式。 您可以修改這些腳本，以配合貴組織及環境的需求。 例如，您可以為不同部門或角色的受管理的 Surface 裝置建立多個組組。 You can download samples of the scripts for SEMM and Configuration Manager from the link in the [Prerequisites](#prerequisites) section at the beginning of this article.

您需要兩個主要腳本，才能使用 Configuration Manager 執行 SEMM 部署：

* **ConfigureSEMM.ps1** – 使用此腳本為 Surface 裝置建立設定套件，並設定您想要的 Surface UEFI 設定，以將指定的設定套用至 Surface 裝置、在 SEMM 中註冊裝置，以及設定用來識別 SEMM 中裝置註冊的登錄機碼。
* **ResetSEMM.ps1** – 使用此腳本在 Surface 裝置上重設 SEMM，這會從 SEMM 取消註冊，並移除對 Surface UEFI 設定的控制。

範例腳本包含如何設定 Surface UEFI 設定，以及如何控制這些設定許可權的範例。 您可以修改這些設定來保護 Surface UEFI，並依您的環境需求設定 Surface UEFI 設定。 本文的下列各節說明ConfigureSEMM.ps1腳本，並探索您需要對腳本所做的修改，以配合您的需求。

> [!NOTE]
> SEMM Configuration Manager 腳本和匯出的 SEMM 憑證檔案 (.pfx) 應放在沒有其他檔案的同一個資料夾中，再新加入 Configuration Manager。

### <a name="specify-certificate-and-package-names"></a>指定憑證和套件名稱

您需要修改之腳本的第一個區域是指定並載入 SEMM 憑證的部分，同時也指出 SurfaceUEFIManager 版本，以及 SEMM 設定套件和 SEMM 重設套件的名稱。 憑證名稱和 SurfaceUEFIManager 版本會于腳本的行 56 到 73 中ConfigureSEMM.ps1指定。

  ```powershell
  56    $WorkingDirPath = split-path -parent $MyInvocation.MyCommand.Definition
  57    $packageRoot = "$WorkingDirPath\Config"
  58    $certName = "FabrikamSEMMSample.pfx"
  59  $DllVersion = "2.26.136.0"
  60
  61  $certNameOnly = [System.IO.Path]::GetFileNameWithoutExtension($certName)
  62  $ProvisioningPackage = $certNameOnly + "ProvisioningPackage.pkg"
  63  $ResetPackage = $certNameOnly + "ResetPackage.pkg"
  64
  65    if (-not (Test-Path $packageRoot))  { New-Item -ItemType Directory -Force -Path $packageRoot }
  66    Copy-Item "$WorkingDirPath\$certName" $packageRoot
  67    
  68    $privateOwnerKey = Join-Path -Path $packageRoot -ChildPath $certName
  69    $ownerPackageName = Join-Path -Path $packageRoot -ChildPath $ProvisioningPackage
  70    $resetPackageName = Join-Path -Path $packageRoot -ChildPath $ResetPackage
  71    
  72    # If your PFX file requires a password then it can be set here, otherwise use a blank string.
  73    $password = "1234" 
  ```

以第 58 行的 SEMM 憑證**檔案名**取代 $certName 變數的**FabrikamSEMMSample.pfx**值。 腳本將在腳本所在的資料夾中 (名為 Config) 的工作目錄，然後將憑證檔案複製到此工作目錄。

擁有者套件和重設套件也會在 Config 目錄中建立，並保留 Surface UEFI 設定和腳本產生的許可權設定。

在行 73 中，取代****$password變數的值，從**1234**到憑證檔案的密碼。 如果不需要密碼，請刪除 **1234** 文字。

> [!Note]
> 註冊 SEMM 中的裝置時，需要憑證指紋的最後兩個字元。 此腳本會向使用者顯示這些數位，讓使用者或技術人員在系統重新開機以在 SEMM 中註冊裝置之前，先記錄這些數位。 腳本使用第 150-155 行找到的下列程式碼來達成此目的。

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

具有憑證檔案 (.pfx) 的系統管理員隨時都可以在 CertMgr 中開啟 .pfx 檔案來讀取指紋。 若要使用 CertMgr 來查看指紋，請遵循下列程式：

1. 以滑鼠右鍵按一下 .pfx 檔案，然後選取 [ **開啟**。
2. 展開流覽窗格中的資料夾。
3. 選取 **憑證**。
4. 以滑鼠右鍵按一下主窗格中的憑證，然後選取 [ **開啟**。
5. Select the **Details** tab.
6. **在**顯示**下拉式功能表**中，必須選取所有或**** 僅屬性。
7. 選取拇 **指列印欄位**。

> [!NOTE]
> SEMM 憑證名稱和密碼也必須在 ResetSEMM.ps1 腳本的本節中輸入，才能讓 Configuration Manager 使用卸載動作從裝置移除 SEMM。

### <a name="configure-permissions"></a>設定許可權

您指定 Surface UEFI 設定之腳本的第一個區域是設定 **許可權** 區域。 此區域從範例腳本的第 210 行開始，並包含批註 **#設定** 許可權，並繼續到第 247 行。 下列程式碼片段會先設定所有 Surface UEFI 設定的許可權，以便僅由 SEMM 修改，然後新增明確許可權，讓當地使用者修改 Surface UEFI 密碼、TPM 以及前置和後方相機。

```powershell
210 # Configure Permissions
211 foreach ($uefiV2 IN $surfaceDevices.Values) {
212 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
213 Write-Host "Configuring permissions"
214 Write-Host $Device.Model
215 Write-Host "======================="
216
217 # Here we define which "identities" will be allowed to modify which settings
218 #   PermissionSignerOwner = The primary SEMM enterprise owner identity
219 #   PermissionLocal = The user when booting to the UEFI pre-boot GUI
220 #   PermissionSignerUser, PermissionSignerUser1, PermissionSignerUser2 =
221 #     Additional user identities created so that the signer owner
222 #     can delegate permission control for some settings.
223 $ownerOnly = [Microsoft.Surface.IUefiSetting]::PermissionSignerOwner
224 $ownerAndLocalUser = ([Microsoft.Surface.IUefiSetting]::PermissionSignerOwner -bor [Microsoft.Surface.IUefiSetting]::PermissionLocal)
225 
226 # Make all permissions owner only by default
227 foreach ($setting IN $uefiV2.Settings.Values) {
228 $setting.ConfiguredPermissionFlags = $ownerOnly
229 }
230 
231 # Allow the local user to change their own password
232 $uefiV2.SettingsById[501].ConfiguredPermissionFlags = $ownerAndLocalUser
233
234 Write-Host ""
235  
236 # Create a unique package name based on family and LSV.
237 # We will choose a name that can be parsed by later scripts.
238 $packageName = $uefiV2.SurfaceUefiFamily + "^Permissions^" + $lsv + ".pkg"
239 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
240 
241 # Build and sign the Permission package then save it to a file.
242 $permissionPackageStream =  $uefiV2.BuildAndSignPermissionPackage($privateOwnerKey, $password, "", $null, $lsv)
243 $permissionPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
244 $permissionPackageStream.CopyTo($permissionPackage)
245 $permissionPackage.Close()
246 }
247 }
```

每個 **$uefiV 2** 變數會設定名稱或識別碼來識別 Surface UEFI 設定，然後將許可權設定為下列其中一個值：

* **$ownerOnly** – 僅將修改此設定的許可權授予 SEMM。
* **$ownerAndLocalUser** – 將修改此設定的許可權授予將本地使用者引導至 Surface UEFI，以及 SEMM。

You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section of this article.

### <a name="configure-settings"></a>進行設定

您指定 Surface UEFI 設定之腳本的第二個區域是 ConfigureSEMM.ps1**** 腳本的設定 設定 區域，可設定每個設定是否已啟用或停用。 範例腳本包含將所有設定設為預設值的指示。 腳本接著會提供明確指示，以停用 PXE Boot 的 IPv6，並維持 Surface UEFI 系統管理員密碼不變。 您可以在範例腳本的第 291 行**設定**第 335 行 #C1 開始尋找此區域。 該區域會顯示如下。

```powershell
291 # Configure Settings
292 foreach ($uefiV2 IN $surfaceDevices.Values) {
293 if ($uefiV2.SurfaceUefiFamily -eq $Device.Model) {
294 Write-Host "Configuring settings"
295 Write-Host $Device.Model
296 Write-Host "===================="
297
298 # In this demo, we will start by setting every setting to the default factory setting.
299 # You may want to start by doing this in your scripts
300 # so that every setting gets set to a known state.
301 foreach ($setting IN $uefiV2.Settings.Values) {
302 $setting.ConfiguredValue = $setting.DefaultValue
303 }
304 
305 $EnabledValue = "Enabled"
306 $DisabledValue = "Disabled"
307
308 # If you want to set something to a different value from the default,
309 # here are examples of how to accomplish this.
310 # This disables IPv6 PXE boot by name:
311 $uefiV2.Settings["IPv6 for PXE Boot"].ConfiguredValue = $DisabledValue
312
313 # This disables IPv6 PXE Boot by ID:
314 $uefiV2.SettingsById[400].ConfiguredValue = $DisabledValue
315
316 Write-Host ""
317
318 # If you want to leave the setting unmodified, set it to $null
319 # PowerShell has issues setting things to $null so ClearConfiguredValue()
320 # is supplied to do this explicitly.
321 # Here is an example of leaving the UEFI administrator password as-is,
322 # even after we initially set it to factory default above.
323 $uefiV2.SettingsById[501].ClearConfiguredValue()
324 
325 # Create a unique package name based on family and LSV.
326 # We will choose a name that can be parsed by later scripts.
327 $packageName = $uefiV2.SurfaceUefiFamily + "^Settings^" + $lsv + ".pkg"
328 $fullPackageName = Join-Path -Path $packageRoot -ChildPath $packageName
329 
330 # Build and sign the Settings package then save it to a file.
331 $settingsPackageStream =  $uefiV2.BuildAndSignSecuredSettingsPackage($privateOwnerKey, $password, "", $null, $lsv)
332 $settingsPackage = New-Object System.IO.Filestream($fullPackageName, [System.IO.FileMode]::CreateNew, [System.IO.FileAccess]::Write)
333 $settingsPackageStream.CopyTo($settingsPackage)
334 $settingsPackage.Close()
335 }
```

就像腳本的設定許可權區段**** 所設定的許可權一樣，每個 Surface UEFI 設定都是定義 $uefiV 2 變數**來**執行。 針對定義 $uefiV 2 變數的每 **一行** ，會設定名稱或識別碼來識別 Surface UEFI 設定，且設定的值設為 **啟用** 或 **停用**。

如果您不想變更 Surface UEFI 設定設定，例如為了確保 Surface UEFI 系統管理員密碼不會因為將所有 Surface UEFI 設定重設為預設值的動作而清除，您可以使用 **ClearConfiguredValue () ** 來強制執行此設定不會變更。 在範例腳本中，這會用於第 323 行，以防止清除在範例腳本中以其設定識別碼 **501**識別的 Surface UEFI 系統管理員密碼。

You can find information about the available settings names and IDs for Surface UEFI in the [Settings Names and IDs](#settings-names-and-ids) section later in this article.

### <a name="settings-registry-key"></a>設定登錄機碼

若要識別 Configuration Manager 的註冊系統，ConfigureSEMM.ps1腳本會撰寫登錄機碼，用來識別已註冊的系統已與 SEMM 組組腳本一起安裝。 您可以在下列位置找到這些按鍵。

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

下列程式碼片段位於第 380-477 行，用來撰寫這些登錄機碼。

```powershell
380 # For Endpoint Configuration Manager or other management solutions that wish to know what version is applied, tattoo the LSV and current DateTime (in UTC) to the registry:
381 $UTCDate = (Get-Date).ToUniversalTime().ToString()
382 $certIssuer = $certPrint.Issuer
383 $certSubject = $certPrint.Subject
384 
385 $SurfaceRegKey = "HKLM:\SOFTWARE\Microsoft\Surface\SEMM"
386 New-RegKey $SurfaceRegKey
387 $LSVRegValue = Get-ItemProperty $SurfaceRegKey LSV -ErrorAction SilentlyContinue
388 $DateTimeRegValue = Get-ItemProperty $SurfaceRegKey LastConfiguredUTC -ErrorAction SilentlyContinue
389 $OwnershipSessionIdRegValue = Get-ItemProperty $SurfaceRegKey OwnershipSessionId -ErrorAction SilentlyContinue
390 $PermissionSessionIdRegValue = Get-ItemProperty $SurfaceRegKey PermissionSessionId -ErrorAction SilentlyContinue
391 $SettingsSessionIdRegValue = Get-ItemProperty $SurfaceRegKey SettingsSessionId -ErrorAction SilentlyContinue
392 $IsResetRegValue = Get-ItemProperty $SurfaceRegKey IsReset -ErrorAction SilentlyContinue
393 $certUsedRegValue = Get-ItemProperty $SurfaceRegKey CertName -ErrorAction SilentlyContinue
394 $certIssuerRegValue = Get-ItemProperty $SurfaceRegKey CertIssuer -ErrorAction SilentlyContinue
395 $certSubjectRegValue = Get-ItemProperty $SurfaceRegKey CertSubject -ErrorAction SilentlyContinue
396 
397 
398 If ($LSVRegValue -eq $null)
399 {
400     New-ItemProperty -Path $SurfaceRegKey -Name LSV -PropertyType DWORD -Value $lsv | Out-Null
401 }
402 Else
403 {
404     Set-ItemProperty -Path $SurfaceRegKey -Name LSV -Value $lsv
405 }
406 
407 If ($DateTimeRegValue -eq $null)
408 {
409     New-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -PropertyType String -Value $UTCDate | Out-Null
410 }
411 Else
412 {
413     Set-ItemProperty -Path $SurfaceRegKey -Name LastConfiguredUTC -Value $UTCDate
414 }
415 
416 If ($OwnershipSessionIdRegValue -eq $null)
417 {
418     New-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -PropertyType String -Value $ownerSessionIdValue | Out-Null
419 }
420 Else
421 {
422     Set-ItemProperty -Path $SurfaceRegKey -Name OwnershipSessionId -Value $ownerSessionIdValue
423 }
424 
425 If ($PermissionSessionIdRegValue -eq $null)
426 {
427     New-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -PropertyType String -Value $permissionSessionIdValue | Out-Null
428 }
429 Else
430 {
431     Set-ItemProperty -Path $SurfaceRegKey -Name PermissionSessionId -Value $permissionSessionIdValue
432 }
433 
434 If ($SettingsSessionIdRegValue -eq $null)
435 {
436     New-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -PropertyType String -Value $settingsSessionIdValue | Out-Null
437 }
438 Else
439 {
440     Set-ItemProperty -Path $SurfaceRegKey -Name SettingsSessionId -Value $settingsSessionIdValue
441 }
442 
443 If ($IsResetRegValue -eq $null)
444 {
445     New-ItemProperty -Path $SurfaceRegKey -Name IsReset -PropertyType DWORD -Value 0 | Out-Null
446 }
447 Else
448 {
449     Set-ItemProperty -Path $SurfaceRegKey -Name IsReset -Value 0
450 }
451 
452 If ($certUsedRegValue -eq $null)
453 {
454     New-ItemProperty -Path $SurfaceRegKey -Name CertName -PropertyType String -Value $certName | Out-Null
455 }
456 Else
457 {
458     Set-ItemProperty -Path $SurfaceRegKey -Name CertName -Value $certName
459 }
460 
461 If ($certIssuerRegValue -eq $null)
462 {
463     New-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -PropertyType String -Value $certIssuer | Out-Null
464 }
465 Else
466 {
467     Set-ItemProperty -Path $SurfaceRegKey -Name CertIssuer -Value $certIssuer
468 }
469 
470 If ($certSubjectRegValue -eq $null)
471 {
472     New-ItemProperty -Path $SurfaceRegKey -Name CertSubject -PropertyType String -Value $certSubject | Out-Null
473 }
474 Else
475 {
476     Set-ItemProperty -Path $SurfaceRegKey -Name CertSubject -Value $certSubject
477 }
```

### <a name="settings-names-and-ids"></a>設定名稱和 ID

若要設定 Surface UEFI 設定或 Surface UEFI 設定的許可權，您必須參照每個設定的名稱或設定識別碼。 隨著 Surface UEFI 的每個新更新，可能會新增新的設定。 在 ShowSettingsOptions.ps1 工具 (執行SEMM_Powershell.zip腳本) [提供](https://www.microsoft.com/download/details.aspx?id=46703) 可用設定的詳細資訊。 執行ShowSettingsOptions.ps1的電腦必須安裝 Microsoft Surface UEFI Manager，但腳本不需要 Surface 裝置。


## <a name="deploy-semm-configuration-manager-scripts"></a>部署 SEMM Configuration Manager 腳本

腳本準備好在用戶端裝置上設定及啟用 SEMM 之後，下一個步驟是在 Configuration Manager 中新增這些腳本做為應用程式。 開啟 Configuration Manager 之前，請確保下列檔案在不包含其他檔案的共用資料夾中：

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* 您的 SEMM 憑證 (例如 SEMMCertificate.pfx) 

SEMM Configuration Manager 腳本會新增到 Configuration Manager 做為腳本應用程式。 安裝 SEMM 的命令ConfigureSEMM.ps1如下所示。

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

使用命令卸載 SEMM 的命令ResetSEMM.ps1如下所示。

`Powershell.exe -file ".\ResetSEMM.ps1"`

若要將 SEMM Configuration Manager 腳本新增為應用程式至 Configuration Manager，請使用下列程式：

1. 從本文稍早的部署 [Microsoft Surface UEFI Manager](#deploy-microsoft-surface-uefi-manager) 一節中，使用步驟 1 到步驟 5 啟動建立應用程式精靈。

2. 繼續執行建立應用程式精靈，如下所示：

   - **一** 般 – 選取 **手動指定應用程式資訊**，然後選取下 **一步**。

   - **一般** 資訊 ： 在此頁面上輸入應用程式名稱 (例如 SEMM) ，以及任何其他您想要的資訊，例如發行者、版本或批註。 選取 **下一** 步以繼續。

   - **應用程式目錄** - 此頁面上的欄位可以留有預設值。 選取 **[下一步]**。

   - **部署類型** – 選取 **新增** 以啟動建立部署類型精靈。

   - 繼續完成建立部署類型精靈的步驟，如下所示：

     * **一**般 – 從**輸入**下拉式功能表選取腳本安裝程式。 **** 系統 **會自動選取手動指定部署類型** 資訊選項。 選取 **下一** 步以繼續。
     * **一般資訊** - 輸入部署類型的名稱 (例如 SEMM 組) 腳本，然後選取下一 **步以繼續** 。
     * **內容**–**選取內容**位置**** 欄位旁的流覽，然後選取 SEMM Configuration Manager 腳本所在的資料夾。 在安裝程式 **欄位中** ，輸入 [本文稍早](#deploy-semm-configuration-manager-scripts) 找到的安裝命令。 在卸載**程式**欄位中，輸入本文稍[](#deploy-semm-configuration-manager-scripts)早找到的卸載命令， (圖 2) 。 選取 **下** 一頁以移至下一頁。
    
     ![將 SEMM Configuration Manager 腳本設定為安裝和卸載命令。](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *圖 2. 將 SEMM Configuration Manager 腳本設定為安裝和卸載命令*

     * **偵測方法** ： **選取 Add 子句** 以新增 SEMM Configuration Manager 腳本登錄機碼偵測規則。 系統 **會顯示偵測規則** 視窗，如圖 3 所示。 使用下列設定：

       - 從**設定類型**下拉式功能表選取**** 註冊表。
       - 從 **HKEY_LOCAL_MACHINE** 下拉式 **功能表中** 選取選項。
       - 在 Key 欄位中輸入**SOFTWARE\Microsoft\Surface\SEMM。** ****
       - 在**值欄位中輸入 CertName。** ****
       - 從 **資料類型** 下拉式功能表 **選取** 字串。
       - 選取此 **註冊表設定必須符合下列規則，以表示此應用程式按鈕的** 顯示狀態。
       - 在值欄位的腳本第 58 行輸入您輸入的 **憑證** 名稱。
       - 選取 **確定** 以關閉 **偵測規則** 視窗。

     ![使用登錄機碼來識別在 SEMM 中註冊的裝置。](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *圖 3. 使用登錄機碼識別在 SEMM 中註冊的裝置*

     * 選取 **下** 一頁，繼續下一頁。
     
     * **使用者體驗** – 從安裝 **行為下拉式功能表** 選取 **系統安裝** 。 如果您希望使用者自行錄製並輸入憑證指紋，請保留登入需求設為只有在**使用者登入時。** 如果您希望系統管理員輸入使用者的指紋，而使用者不需要看到指紋，請從登入需求下拉式功能表選取是否要登入使用者。 **** ****

     * **需求** – ConfigureSEMM.ps1腳本會在嘗試啟用 SEMM 之前，自動驗證裝置是 Surface 裝置。 不過，如果您打算將此腳本應用程式部署至包含要使用 SEMM 管理之裝置外之裝置的集合，您可以在這裡新增需求，以確保此應用程式只會在想要使用 SEMM 管理的 Surface 裝置或裝置上執行。 選取 **下一** 步以繼續。
     
     * **相依性** – **選取新增** 以開啟 **新增相依性** 視窗。

       * 選取 **新增** 以開啟 **指定所需的應用程式** 視窗。

          - 在相依性組名欄位中輸入 SEMM**** 相依性的名稱 (例如*SEMM 程式集*) 。

          - 從可用應用程式和 MSI 部署類型清單中選取**** Microsoft **Surface UEFI Manager，** 然後**** 選取確定以關閉**指定所需應用程式**視窗。
          
         *   如果您想要 **在** 裝置上自動安裝 Microsoft Surface UEFI Manager，請保持選取自動安裝核取方塊，當您嘗試使用 Configuration Manager 腳本啟用 SEMM。 選取 **確定** 以關閉 **新增相依性** 視窗。

     * 選取 **下一** 步以繼續。
     
     * **摘要** ： 您在整個建立部署類型精靈中輸入的資訊會顯示在此頁面上。 選取 **下一** 步以確認您的選取專案。
     
     * **進度** - 新增 SEMM 腳本應用程式的部署類型時的進度列和狀態會顯示在此頁面上。
     
     * **完成** – 完成程式時，系統會顯示部署類型建立確認。 選取 **關閉** 以完成建立部署類型精靈。

   - **摘要** ： 顯示您在整個建立應用程式精靈中輸入的資訊。 選取 **下一** 步以建立應用程式。

   - **進度** ： 應用程式新加入軟體庫時的進度列和狀態會顯示在此頁面上。

   - **完成** – 應用程式建立程式完成時，會顯示成功建立應用程式的確認。 選取 **關閉** 以完成建立應用程式精靈。

在 Configuration Manager 的軟體文件庫中提供腳本應用程式之後，您可以使用準備至裝置或集合的腳本發佈及部署 SEMM。 如果您已經將 Microsoft Surface UEFI Manager 程式集配置為會自動安裝的相依性，您可以在單一步驟中部署 SEMM。 如果您尚未將程式集配置為相依性，這些程式集必須安裝在您打算管理的裝置上，才能啟用 SEMM。

當您使用此腳本應用程式部署 SEMM，以及使用者可見的組塊時，PowerShell 腳本將會啟動，而憑證的指紋會顯示在 PowerShell 視窗。 您可以讓使用者錄製此指紋，在裝置重新開機後，當 Surface UEFI 提示時輸入。

或者，您可以將應用程式安裝設定為自動重新開機，並讓使用者以隱形方式安裝。 在此情境中，技術人員在重新開機時，必須在每個裝置上輸入指紋。 任何能夠存取憑證檔案的技術人員都可以使用 CertMgr 檢視憑證來讀取指紋。 使用 CertMgr 檢視指紋的指示，請參閱本文的建立或修改 [SEMM Configuration Manager 腳本](#create-or-modify-the-semm-configuration-manager-scripts) 一節。

使用這些腳本從使用 Configuration Manager 部署的裝置移除 SEMM，就像使用 Configuration Manager 卸載應用程式一樣簡單。 此動作會啟動ResetSEMM.ps1腳本，並使用 SEMM 部署期間所使用的相同憑證檔案來正確取消註冊裝置。

> [!NOTE]
> Microsoft Surface 建議您只在需要取消註冊裝置時，才能建立重設套件。 這些重設套件通常僅適用于一個裝置，其序號會識別。 不過，您可以建立通用重設套件，適用于使用此憑證在 SEMM 註冊的任何裝置。
> 
> 我們強烈建議您謹慎保護通用重設套件，就像您在 SEMM 中註冊裝置所使用的憑證一樣。 請記住，就像憑證本身一樣，這個通用重設套件可以用來從 SEMM 取消註冊貴組織的任何 Surface 裝置。
> 
> 當您安裝重設套件時，LSV (的最低) 值會重設為 1。 您可以使用現有的組組套件重新註冊裝置。 裝置在取得擁有權之前，會提示您輸入憑證指紋。
> 
> 基於這個原因，在 SEMM 中重新註冊裝置時，需要在此裝置上建立並安裝新套件。 由於此動作是新的註冊，而非已在 SEMM 中註冊的裝置上的組組變更，因此裝置在取得擁有權之前，會提示您輸入憑證指紋。
