---
title: '使用 Microsoft 端點設定管理員來管理含 SEMM (Surface 的裝置) '
description: 瞭解如何使用端點建構管理員來管理 Microsoft Surface Enterprise 管理模式 (SEMM) 。
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
ms.date: 10/13/2020
ms.openlocfilehash: bfd10df3bb7a7dd031c1719d4191ffc46418c4e3
ms.sourcegitcommit: 30c1eb469610dfd2ad9169c154ca07e565240fdb
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/14/2020
ms.locfileid: "11117849"
---
# 搭配 SEMM 使用 Microsoft Endpoint Configuration Manager 管理裝置

「Microsoft Surface Enterprise 管理」模式 (SEMM Surface UEFI 裝置的) 功能，可讓系統管理員管理並協助保護 Surface UEFI 設定的配置。 對於大多陣列織而言，這個程式是透過使用 Microsoft Surface UEFI 設定檔工具建立 Windows Installer ( .msi) 套件來完成。 接著，這些套件會執行或部署至用戶端 Surface 裝置，以在 SEMM 中註冊裝置，並更新 Surface UEFI 設定設定。

對於有 Microsoft 端點設定管理員的組織，您可以使用 Microsoft Surface UEFI 配置處理常式 .msi 程式來部署及管理 SEMM。 Microsoft Surface UEFI 管理員是一種羽量級安裝程式，可讓您在裝置上提供 SEMM 管理所需的元件。 透過在受管理的用戶端上安裝這些元件與 Microsoft Surface UEFI 管理器，SEMM 可以由 Configuration Manager 使用 PowerShell 腳本管理，並部署為應用程式。 在這個程式中，SEMM 管理是在 Configuration Manager 中執行，因此不需要外部 Microsoft Surface UEFI 組態工具。

> [!Note]
> 雖然本文所述的程式可能適用于舊版的 Endpoint Configuration Manager 或其他協力廠商管理解決方案，但只有端點設定管理員的目前分支支援使用 Microsoft Surface UEFI 管理員和 PowerShell 的 SEMM 管理。

#### 必要條件

開始本文所述的程式之前，請先熟悉下列技術與工具：

* [Surface UEFI](https://technet.microsoft.com/itpro/surface/manage-surface-uefi-settings)
* [Surface 企業管理模式 (SEMM)](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode)
* [PowerShell 腳本](https://technet.microsoft.com/scriptcenter/dd742419)
* [System Center Configuration Manager 應用程式部署](https://docs.microsoft.com/sccm/apps/deploy-use/deploy-applications)
* 憑證管理

> [!Note]
> 您也需要使用您想要用來保護 SEMM 的憑證的存取權。 如需此憑證需求的詳細資訊，請參閱 [Surface Enterprise 管理模式憑證需求](https://technet.microsoft.com/itpro/surface/surface-enterprise-management-mode#surface-enterprise-management-mode-certificate-requirements)。
> 
> 必須將此憑證存放在安全的位置並正確備份，這一點非常重要。 如果此憑證遺失或無法使用，就無法重設 Surface UEFI、變更 managed Surface UEFI 設定，或從已註冊的 Surface 裝置移除 SEMM。

#### 下載 Microsoft Surface UEFI 管理員

使用 Configuration Manager 的 SEMM 管理需要在每個用戶端 Surface 裝置上安裝 Microsoft Surface UEFI 管理器。 您可以從 Microsoft 下載中心的 [ [表面工具](https://www.microsoft.com/download/details.aspx?id=46703) ] 頁面上，下載 MICROSOFT Surface UEFI 管理員 ( # A0) 。

#### 下載 Configuration Manager 的 SEMM 腳本

在用戶端 Surface 裝置上安裝 Microsoft Surface UEFI 管理員之後，就會使用 PowerShell 腳本來部署和管理 SEMM。 您可以從下載中心下載 [SEMM 管理腳本](https://www.microsoft.com/download/details.aspx?id=46703) 的範例。

## 部署 Microsoft Surface UEFI 管理員

部署 Microsoft Surface UEFI 管理員是一個典型的應用程式部署。 Microsoft Surface UEFI 管理員安裝程式檔案是標準的 Windows 安裝程式檔案，您可以使用 [標準安靜選項](https://msdn.microsoft.com/library/windows/desktop/aa367988)進行安裝。

安裝 Microsoft Surface UEFI Manager 的命令如下所示。

`msiexec /i "SurfaceUEFIManagerSetup.msi" /q`

卸載 Microsoft Surface UEFI Manager 的命令如下所示。

`msiexec /x {541DA890-1AEB-446D-B3FD-D5B3BB18F9AF} /q`

若要建立新的應用程式，並將它部署到包含 Surface 裝置的集合，請執行下列步驟：

1. 從 [ **開始** ] 畫面或 [ **開始** ] 功能表開啟 Configuration Manager 主控台。
2. 選取視窗左下角的 [ **軟體庫** ]。
3. 展開軟體庫的 [ **應用程式管理** ] 節點，然後選取 [ **應用程式**]。
4. 在視窗頂端的 [**常用] 索引**標籤底下，選取 [**建立應用程式**] 按鈕。 這會啟動 [建立應用程式] 嚮導。
5. [建立應用程式] 嚮導會顯示一系列步驟：

   * **[一般** ]：預設會選取 [ **自動偵測此應用程式的安裝檔案相關資訊** ] 選項。 在 [ **Type** ] （類型）欄位中，預設也會選取 [ **Windows 安裝程式] ( .msi 檔案) ** 。 選取 **[流覽]** 以流覽至 [ **SurfaceUEFIManagerSetup.msi**]，然後選取 **[下一步**]。
   
      > [!Note]
      > SurfaceUEFIManagerSetup.msi 的位置必須位於網路共用位置，且位於不含其他檔案的資料夾中。 無法使用本機檔案位置。

   * 匯**入資訊**-[建立應用程式] 嚮導會分析 .msi 檔案並讀取**應用程式名稱**和**產品代碼**。 SurfaceUEFIManagerSetup.msi 應該線上條 **內容**檔案下以唯一的檔案的形式列出，如圖1所示。 選取 **[下一步]** 繼續。

      ![來自 Surface UEFI 管理員設定的資訊會自動進行分析](images/config-mgr-semm-fig1.png "Information from Surface UEFI Manager setup is automatically parsed")

      *圖 1。 來自 Microsoft Surface UEFI 管理員設定的資訊會自動進行分析*

   * **一般資訊** –您可以修改應用程式的名稱，以及有關發行者與版本的資訊，或在此頁面上新增批註。 Microsoft Surface UEFI Manager 的 [安裝] 命令會顯示在 [安裝程式] 欄位中。 安裝系統的預設安裝行為將允許 Microsoft Surface UEFI 管理員安裝 SEMM 的必要元件，即使使用者沒有登入 Surface 裝置也一樣。 選取 **[下一步]** 繼續。
   * **摘要** ：在 [匯 **入資訊** ] 步驟中分析的資訊，以及您在 [ **一般資訊** ] 步驟中選取的資訊會顯示在此頁面上。 選取 **[下一步]** ，確認您的選擇並建立應用程式。
   * **進度** –當應用程式匯入並新增至軟體文件庫時，會顯示進度列和狀態。
   * **完成** –當應用程式建立處理常式完成時，就會顯示成功建立應用程式的確認。 選取 [ **關閉** ] 以完成 [建立應用程式] 嚮導。

在 Configuration Manager 中建立應用程式後，您可以將它發佈到您的發佈點，並將它部署到集合（包括 Surface 裝置）。 這個應用程式不會在 Surface 裝置上安裝或啟用 SEMM。 它只會提供使用 PowerShell 腳本啟用 SEMM 所需的元件。

如果您不想要在不是使用 SEMM 管理的裝置上安裝 Microsoft Surface UEFI 管理器元件，您可以將 Microsoft Surface UEFI 管理員設定為 SEMM Configuration Manager 腳本的相依性。 此案例將在本文稍後的 [ [部署 SEMM Configuration Manager 腳本](#deploy-semm-configuration-manager-scripts) ] 區段中講述。

## 建立或修改 SEMM Configuration Manager 腳本

在裝置上安裝所需的元件之後，在 SEMM 中註冊裝置並設定 Surface UEFI 的程式是使用 PowerShell 腳本完成，並以 Configuration Manager 的形式部署為腳本應用程式。 您可以修改這些腳本，以符合貴組織與環境的需求。 例如，您可以針對不同部門或角色中的受管理 Surface 裝置建立多個設定。 您可以從本文開頭的 [ [先決條件](#prerequisites) ] 區段中的連結，下載 SEMM 與 Configuration Manager 腳本的範例。

您必須有兩個主要的腳本，才能使用 Configuration Manager 執行 SEMM 部署：

* **ConfigureSEMM.ps1** –使用此腳本來為 surface 裝置建立配置套件，以使用您想要的 surface UEFI 設定，將指定的設定套用至 Surface 裝置、在 SEMM 中註冊裝置，以及設定用來識別 SEMM 中裝置註冊的登錄機碼。
* **ResetSEMM.ps1** –使用此腳本在 surface 裝置上重設 SEMM，這會從 SEMM 中 unenrolls 它，並移除對 surface UEFI 設定的控制。

範例腳本包含如何設定 Surface UEFI 設定，以及如何控制這些設定許可權的範例。 您可以將這些設定修改為安全 Surface UEFI，並根據您的環境需求設定 Surface UEFI 設定。 本文的下列各節將說明 ConfigureSEMM.ps1 腳本，並探索您需要對腳本所做的修改，以符合您的需求。

> [!NOTE]
> SEMM Configuration Manager 腳本和匯出的 SEMM 憑證檔案 ( .pfx) 應該放在與其他檔案不在同一個資料夾中，才能新增至 Configuration Manager。

### 指定憑證及套件名稱

您需要修改的腳本第一個區域是指定及載入 SEMM 憑證的部分，也會指出 SurfaceUEFIManager 版本，以及 SEMM configuration 套件的名稱，以及 SEMM 重設套件。 認證名稱和 SurfaceUEFIManager 版本是在 ConfigureSEMM.ps1 腳本中的第56至73行上指定。

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

將 **$certName**變數的**FabrikamSEMMSample**值，以 SEMM 憑證檔案的名稱取代到行58。 此腳本會在您的腳本所在的資料夾中，建立一個 (命名的 Config) 的工作目錄，然後將證書檔案複製到此工作目錄。

您也會在 Config 目錄中建立擁有者封裝及重設套件，並保留由腳本產生的 Surface UEFI 設定和許可權的配置。

在 line 73 上，將 **$password** 變數的值（從 **1234** ）取代為憑證檔案的密碼。 如果不需要密碼，請刪除 **1234** 文字。

> [!Note]
> 您必須在 SEMM 中註冊裝置，才能使用憑證指紋的最後兩個字元。 此腳本會將這些數字顯示給使用者，讓使用者或技術人員在系統重新開機前記錄這些數位，以在 SEMM 中註冊裝置。 此腳本會使用下列程式碼（在150-155 行中找到）來完成這項作業。

```powershell
150 # Device owners will need the last two characters of the thumbprint to accept SEMM ownership.
151 # For convenience we get the thumbprint here and present to the user.
152 $pw = ConvertTo-SecureString $password -AsPlainText -Force
153 $certPrint = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2
154 $certPrint.Import($privateOwnerKey, $pw, [System.Security.Cryptography.X509Certificates.X509KeyStorageFlags]::DefaultKeySet)
155 Write-Host "Thumbprint =" $certPrint.Thumbprint
```

您可以在 CertMgr 中開啟 .pfx 檔案，讓擁有證書檔案存取權的管理員 ( .pfx) 可隨時讀取指紋。 若要使用 CertMgr 查看指紋，請遵循此程式：

1. 以滑鼠右鍵按一下 .pfx 檔案，然後選取 [ **開啟**]。
2. 展開 [功能窗格] 中的資料夾。
3. 選取 [ **憑證**]。
4. 在主要窗格中，以滑鼠右鍵按一下您的憑證，然後選取 [ **開啟**]。
5. 選取 [ **詳細資料** ] 索引標籤。
6. [**全部**] 或 [**僅限屬性**] 必須在 [**顯示**] 下拉式功能表中選取。
7. 選取欄位 **指紋**。

> [!NOTE]
> 您也必須在 ResetSEMM.ps1 腳本的此區段中輸入 SEMM 憑證名稱和密碼，才能讓 Configuration Manager 從裝置中移除 SEMM 與卸載動作。

### 設定許可權

您將在其中指定 Surface UEFI 配置的腳本第一個區域是 [ **設定許可權** ] 區域。 這個區域會從範例腳本中的第210列開始，並以批註 **# 設定許可權** ，並繼續到第247列。 下列程式碼片段首先將許可權設定為所有 Surface UEFI 設定，以便僅供 SEMM 修改，然後新增明確許可權，以允許本機使用者修改 Surface UEFI 密碼、TPM 以及前臺和後置相機。

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

每個 **$uefiV 2** 變數都透過設定名稱或識別碼來識別 Surface UEFI 設定，然後將許可權設定為下列其中一個值：

* **$ownerOnly** –修改此設定的許可權僅獲授與 SEMM。
* **$ownerAndLocalUser** –修改此設定的許可權會被授與本機使用者引導至 Surface UEFI，以及 SEMM。

您可以在本文的 [ [設定名稱和識別碼](#settings-names-and-ids) ] 區段中，找到有關 Surface UEFI 可用之設定名稱和識別碼的資訊。

### 進行設定

您將在其中指定 Surface UEFI 配置的腳本第二個區域是 ConfigureSEMM.ps1 腳本的 [設定 **設定** ] 區域，它會設定是否已啟用或停用每個設定。 範例腳本包含將所有設定設為預設值的指示。 然後，腳本會提供針對 PXE 啟動停用 IPv6 的明確指示，並讓 Surface UEFI 管理員密碼保持不變。 您可以在範例腳本中，從第291至 line 335 的 **# 設定設定** 批註開始，找到這個區域。 區域如下所示。

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

就像在腳本的 [ **設定許可權** ] 區段中設定的許可權，每個 Surface UEFI 設定的設定都是透過定義 **$uefiV 2** 變數來執行。 針對定義 **$uefiV 2** 變數的每個線條，Surface UEFI 設定是透過設定名稱或識別碼來加以識別，且已設定的值會設定為 [ **啟用** ] 或 [ **已停用**]。

如果您不想要變更 Surface UEFI 設定的設定，例如，以確保將所有 Surface UEFI 設定重設為預設值的動作無法清除 Surface UEFI 系統管理員密碼，您可以使用 **ClearConfiguredValue ( # B1 ** 來強制變更此設定。 在範例腳本中，在 line 323 上使用此選項，以避免清除 Surface UEFI 系統管理員密碼，在範例腳本中以其設定識別碼（ **501**）加以識別。

您可以在本文稍後的 [ [設定名稱和識別碼](#settings-names-and-ids) ] 區段中，找到有關 Surface UEFI 可用設定名稱和識別碼的資訊。

### [設定] 登錄機碼

若要識別 Configuration Manager 的已註冊系統，ConfigureSEMM.ps1 腳本會寫入登錄機碼，以用於識別已註冊的系統（即已使用 SEMM 設定腳本安裝）。 您可以在下列位置找到這些金鑰。

`HKLM\SOFTWARE\Microsoft\Surface\SEMM`

下列程式碼片段（在380-477 行中找到）是用來撰寫這些登錄機碼。

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

### 設定名稱和識別碼

若要設定 Surface uefi 設定或 Surface UEFI 設定的許可權，您必須透過其設定名稱或設定識別碼來參照每一個設定。 針對 Surface UEFI 的每個新更新，可能會新增新設定。 若要取得 Surface 裝置上可用設定的完整清單，以及設定名稱和設定識別碼，就是在[IT 下載的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中使用 ShowSettingsOptions.ps1 腳本 SEMM_Powershell.zip 

執行 ShowSettingsOptions.ps1 的電腦必須安裝 Microsoft Surface UEFI 管理員，但腳本不需要 Surface 裝置。

若要查看裝置最新的設定名稱和識別碼，最好的方法是使用 ConfigureSEMM.ps1 腳本，或 <device name> 從 [IT 下載的 Surface 工具](https://www.microsoft.com/download/details.aspx?id=46703)中的 SEMM_Powershell.zip 中 ConfigureSEMM。

您可以在 ConfigureSEMM.ps1 腳本中查看所有裝置的名稱和識別碼。

您可以在 ConfigureSEMM-ps1 腳本中看到設定特定裝置的名稱和識別碼 <device name> 。 

## 部署 SEMM Configuration Manager 腳本

準備好要在用戶端裝置上設定及啟用 SEMM 的腳本之後，下一步就是在 Configuration Manager 中將這些腳本新增為應用程式。 在您開啟 Configuration Manager 前，請確定下列檔案位於不含其他檔案的共用資料夾中：

* ConfigureSEMM.ps1
* ResetSEMM.ps1
* 您的 SEMM 憑證 (例如 SEMMCertificate .pfx) 

SEMM Configuration Manager 腳本將會新增至 Configuration Manager，做為腳本應用程式。 使用 ConfigureSEMM.ps1 安裝 SEMM 的命令如下所示。

`Powershell.exe -file ".\ConfigureSEMM.ps1"`

使用 ResetSEMM.ps1 卸載 SEMM 的命令如下所示。

`Powershell.exe -file ".\ResetSEMM.ps1"`

若要將 SEMM Configuration Manager 腳本新增至 Configuration Manager 做為應用程式，請使用下列程式：

1. 從本文先前的 [部署 Microsoft SURFACE UEFI 管理員](#deploy-microsoft-surface-uefi-manager) 區段中，使用步驟1到步驟5啟動 [建立應用程式] 嚮導。

2. 依下列步驟繼續執行 [建立應用程式] 嚮導：

   - **一般** –選取 [ **手動指定應用程式資訊**]，然後選取 **[下一步]**。

   - **一般資訊** –輸入應用程式 (的名稱，例如 SEMM) 及您想要的任何其他資訊（例如，此頁面上的 publisher、版本或批註）。 選取 **[下一步]** 繼續。

   - [**應用程式目錄**] –此頁面上的欄位可以保留其預設值。 選取 **\[下一步\]**。

   - **部署類型** –選取 [ **新增** ] 以啟動 [建立部署類型] 嚮導。

   - 依照 [建立部署類型] 嚮導中的步驟進行，如下所示：

     * **一般**-從 [**類型**] 下拉式功能表選取 [**腳本安裝程式**]。 [ **手動指定部署類型資訊** ] 選項會自動選取。 選取 **[下一步]** 繼續。
     * **一般資訊** -在 (輸入部署類型的名稱，例如 SEMM [設定腳本]) ，然後選取 **[下一步]** 以繼續。
     * **內容**–選取 [**內容位置**] 欄位旁的 **[流覽]** ，然後選取您的 SEMM Configuration Manager 腳本所在的資料夾。 在 [ **安裝程式** ] 欄位中，輸入本文前文所述的 [安裝命令](#deploy-semm-configuration-manager-scripts) 。 在 [ **卸載程式** ] 欄位中，輸入您在本文先前所見到的 [卸載命令](#deploy-semm-configuration-manager-scripts) (圖 2) 所示。 選取 **[下一步]** ，移至下一個頁面。
    
     ![將 SEMM Configuration Manager 腳本設定為安裝與卸載命令](images/config-mgr-semm-fig2.png "Set the SEMM Configuration Manager scripts as the install and uninstall commands")

     *圖 2. 將 SEMM Configuration Manager 腳本設定為安裝與卸載命令*

     * **偵測方法** –選取 **add 子句** 以新增 SEMM Configuration Manager 腳本登錄金鑰偵測規則。 隨即會顯示 [ **偵測規則** ] 視窗，如圖3所示。 使用下列設定：

       - 從 [**設定類型**] 下拉式功能表中選取 [**註冊表**]。
       - 從 [**配置單元**] 下拉式功能表中選取 [ **HKEY_LOCAL_MACHINE** ]。
       - 在 [索引**鍵**] 欄位中輸入**SOFTWARE\Microsoft\Surface\SEMM** 。
       - 在 [**值**] 欄位中輸入**CertName** 。
       - 從 [**資料類型**] 下拉式功能表中選取 [**字串**]。
       - 選取 [ **此登錄設定必須符合下列規則，才能指出此應用程式的目前狀態** ] 按鈕。
       - 在 [ **值** ] 欄位中，輸入您在腳本的 [行 58] 中輸入的憑證名稱。
       - 選取 **[確定]** 以關閉 [ **偵測規則** ] 視窗。

     ![使用登錄機碼來識別註冊 SEMM 的裝置](images/config-mgr-semm-fig3.png "Use a registry key to identify devices enrolled in SEMM")
     
     *圖 3. 使用登錄機碼來識別註冊 SEMM 的裝置*

     * 選取 **[下一步]** ，繼續進行下一個頁面。
     
     * **使用者體驗**-從 [**安裝行為**] 下拉式功能表選取 [**安裝系統**]。 如果您想讓使用者錄製並輸入證書指紋本身，請將登錄需求只設定為 **在使用者登入時才**設定。 如果您想要讓系統管理員為使用者輸入指紋，且使用者不需要看到指紋，請從 [**登錄需求**] 下拉式功能表選取使用者是否已**登入**。

     * **需求** -ConfigureSEMM.ps1 腳本會在嘗試啟用 SEMM 前，自動確認裝置是 Surface 裝置。 不過，如果您想要將此腳本應用程式部署到集合，而不是使用 SEMM 管理的裝置，您可以在這裡新增需求，以確保此應用程式只會在 Surface 裝置或您想要使用 SEMM 管理的裝置上執行。 選取 **[下一步]** 繼續。
     
     * 相依性–選取 [**新增** **]** 以開啟 [**新增**相依性] 視窗。

       * 選取 [ **新增** ] 以開啟 [ **指定所需的應用程式** ] 視窗。

          - 在 [相依性 **群組名稱** ] (欄位中輸入 SEMM 相依性的名稱，例如， *SEMM 元件*) 。

          - 從**可用應用程式**及 MSI 部署類型清單中選取 [ **Microsoft Surface UEFI 管理員**]，然後選取 **[確定**] 以關閉 [**指定所需的應用程式**] 視窗。
          
         *   如果您想要在裝置上使用 Configuration Manager 腳本啟用 SEMM，請將 [ **自動安裝** ] 核取方塊保持為已選取。 選取 **[確定** ] 以關閉 [ **新增** 相依性] 視窗。

     * 選取 **[下一步]** 繼續。
     
     * **摘要** -您在整個 [建立部署類型] 嚮導中輸入的資訊會顯示在此頁面上。 選取 **[下一步]** 以確認您的選擇。
     
     * **進度** –將在此頁面上顯示 SEMM 腳本應用程式的進度列和狀態作為部署類型。
     
     * **完成** –在處理常式完成時，會顯示部署類型建立的確認。 選取 [ **關閉** ] 以完成 [建立部署類型] 嚮導。

   - **摘要** ：您在整個 [建立應用程式] 嚮導中輸入的資訊都會顯示。 選取 **[下一步]** 來建立應用程式。

   - **進度** –在此頁面上顯示應用程式新增至軟體文件庫的進度列和狀態。

   - **完成** –當應用程式建立處理常式完成時，就會顯示成功建立應用程式的確認。 選取 [ **關閉** ] 以完成 [建立應用程式] 嚮導。

在 Configuration Manager 的軟體庫中提供腳本應用程式之後，您就可以使用您準備好到裝置或集合的腳本來發佈及部署 SEMM。 如果您已將 Microsoft Surface UEFI 系統管理員元件設定為將自動安裝的相依性，您可以在單一步驟中部署 SEMM。 如果您沒有將元件設定為相依性，您必須先將其安裝在您想要管理的裝置上，才能啟用 SEMM。

當您使用此腳本應用程式及最終使用者可見的設定部署 SEMM 時，PowerShell 腳本將會啟動，並由 PowerShell 視窗顯示憑證的指紋。 您可以讓使用者記錄這個指紋，並在裝置重新開機後，在 Surface UEFI 出現提示時輸入它。

或者，您可以將應用程式安裝設定為自動重新開機，並以不可見的使用者的安裝。 在這種情況下，系統會在重新開機時，在每個裝置上輸入指紋。 任何擁有憑證檔案存取權的技術人員，都可以透過 CertMgr 查看憑證來讀取指紋。 使用 CertMgr 查看指紋的指示是在本文的 [ [建立或修改 SEMM Configuration Manager 腳本](#create-or-modify-the-semm-configuration-manager-scripts) ] 區段中。

從使用 Configuration Manager 部署的裝置中移除 SEMM，就像透過 Configuration Manager 卸載應用程式一樣簡單。 這個動作會啟動 ResetSEMM.ps1 腳本，並使用與 SEMM 部署期間使用相同的憑證檔案正確 unenrolls 裝置。

> [!NOTE]
> Microsoft Surface 建議您只有在您需要取消註冊裝置時，才能建立 [重設套件]。 這些重設套件通常只適用于一個裝置，且由其序列值識別。 不過，您可以針對使用此憑證註冊的任何裝置，建立可使用的通用重設套件。
> 
> 我們強烈建議您在 SEMM 中使用您用來註冊裝置的憑證，謹慎保護您的通用重設套件。 請記住，就像證書本身一樣，此通用重設套件可以用來從 SEMM 取消您組織的任何 Surface 裝置。
> 
> 當您安裝重設套件時， (LSV) 最低支援的值會重設為1的值。 您可以使用現有的配置套件重新註冊裝置。 在取得擁有權之前，裝置會提示您輸入憑證指紋。
> 
> 基於這個原因，SEMM 中的裝置 reenrollment 會要求在該裝置上建立並安裝新套件。 因為此動作是新的註冊，而裝置上已註冊的裝置設定不會變更，所以在取得擁有權之前，裝置會提示您輸入憑證指紋。
