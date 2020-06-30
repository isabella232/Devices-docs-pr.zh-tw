---
title: 管理 Surface UEFI 設定
description: 使用 Surface UEFI 設定以啟用或停用裝置或元件、設定安全性設定，以及調整 Surface 裝置開機設定。
keywords: firmware, security, features, configure, hardware, 韌體、安全性、功能、設定、硬體
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: devices, surface
author: coveminer
ms.author: greglin
ms.topic: article
ms.reviewer: ''
manager: laurawi
ms.openlocfilehash: ce857260c3f4b42ae560a7dba51d47d0e20233bd
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831654"
---
# 管理 Surface UEFI 設定

所有目前及未來的 Surface 裝置代都使用專為這些裝置設計的獨特的整合可延伸韌體介面（UEFI）。 Surface UEFI 設定能讓您啟用或停用內建的裝置和元件、保護 UEFI 設定不被變更，以及調整 Surface 裝置的啟動設定。 

## 支援雲端管理

在內置於 Microsoft Intune 中的裝置固件配置介面（DFCI）設定檔（現已在公用預覽中提供），Surface UEFI 管理會將新式管理堆疊延伸到 UEFI 硬體層級。 DFCI 支援零觸控配，消除 BIOS 密碼，提供安全性設定（包括啟動選項和內建週邊設備）的控制權，並針對未來的高級安全性案例奠定基礎。 DFCI 目前可供 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3使用。 如需詳細資訊，請參閱[SURFACE UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)。

## 開啟 Surface UEFI 功能表

在系統啟動期間調整 UEFI 設定：

1. 關閉表面並等候大約10秒鐘，以確定它已關閉。
2. 按住**音量調高**按鈕，同步選取電源按鈕，然後放開 [**電源] 按鈕。**
3. 當您的螢幕上出現 Microsoft 或 Surface 標誌時，請繼續按住**音量**按鈕，直到出現 [UEFI] 畫面。

## [UEFI 電腦資訊] 頁面

[電腦資訊] 頁面包含 Surface 裝置的詳細資訊： 

- **模型**-您的 surface 裝置模型將會顯示在這裡，例如 surface Book 2 或 surface Pro 7。 裝置的確切組態並不會顯示 (例如處理器、磁碟大小或記憶體大小)。 
- **UUID** – 這個通用唯一識別碼是裝置特定的號碼，用來在部署或管理期間識別裝置。 

- **序號** – 此號碼是用來識別這個特定的 Surface 裝置，以進行資產標記和支援案例。
- **資產標記**– 資產標記是使用[資產標記工具](https://docs.microsoft.com/surface/assettag)指派至 Surface 裝置。 

您也能找到 Surface 裝置韌體的詳細資訊。 Surface 裝置擁有數個內部元件，每個元件都會執行不同版本的韌體。 下列裝置的個別韌體版本都會顯示於 \[電腦資訊\] 頁面上 \(如圖 1 所示\)：**** 

- 系統 UEFI 

- SAM 控制器 

- Intel 管理引擎 

- 系統內嵌控制器 

- 觸控韌體 

![系統資訊和韌體版本資訊](images/manage-surface-uefi-figure-1.png "System information and firmware version information")

*圖 1. 系統資訊和韌體版本資訊*

您可以在裝置的 [Surface 更新記錄](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中找到 Surface 裝置最新韌體版本的最新資訊。 

## UEFI 安全性頁面 

![設定 Surface UEFI 安全性設定](images/manage-surface-uefi-fig4.png "Configure Surface UEFI security settings")

*圖 2. 設定 Surface UEFI 安全性設定*

[安全性] 頁面可讓您設定密碼來保護 UEFI 設定。 此密碼必須在將 Surface 裝置開機至 UEFI 時輸入。 密碼可以包含下列字元（如圖3所示）： 

- 大寫字母：A-Z 

- 小寫字母：a-z 

- 數字：1-0 

- 特殊字元：！ @ # $% ^& * （）？ <>{} []-_ = + |.，;： "" " 

密碼必須至少為 6 個字元，並會區分大小寫。 

![新增密碼以保護 Surface UEFI 設定](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*圖 3. 新增密碼以保護 Surface UEFI 設定*

您也可以在 \[安全性\] 頁面上變更 Surface 裝置的安全開機設定。 安全開機技術能防止未經授權的啟動碼將您的 Surface 裝置開機，這將能針對 Bookit 和 Rootkit 類型的惡意程式碼感染提供保護。 您可以停用安全開機以允許 Surface 裝置使用第三方作業系統或可開機媒體進行開機。 您也可以設定 [安全啟動]，與協力廠商憑證搭配使用，如圖4所示。 於 TechNet Library 深入了解[安全開機](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)。

![設定安全開機](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*圖 4. 設定安全開機*

視您的裝置而定，您可能也可以查看您的 TPM 是已啟用或停用。 如果您沒有看到 [**啟用 TPM** ] 設定，請在 Windows 中開啟 [services.msc] 來檢查狀態，如圖5所示。 TPM 是用來以 BitLocker 為您裝置的資料驗證加密。 若要深入瞭解，請參閱[BitLocker 簡介](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)。 

![TPM 主控台](images/manage-surface-uefi-fig5-a.png "TPM console")

*圖 5. TPM 主控台*


## UEFI 功能表：裝置 

[裝置] 頁面可讓您啟用或停用特定裝置和元件，包括：

- 擴充座和 USB 連接埠 

- MicroSD 或 SD 記憶卡插槽 

- 後方攝影機 

- 前方攝影機 

- 紅外線 (IR) 相機 

- Wi-Fi 和藍牙 

- 內建音訊 (擴音器和麥克風) 

列出的每個裝置都有一個滑杆按鈕，您可以將它移至 [**開啟**] （啟用）或 [**關閉**] （停用）位置，如圖6所示。 

![啟用或停用特定裝置](images/manage-surface-uefi-fig5a.png "Enable and disable specific devices")

*圖 6. 啟用或停用特定裝置*

## UEFI 功能表：啟動設定 

[啟動設定] 頁面可讓您變更啟動裝置的順序，以及啟用或停用啟動下列裝置： 

- Windows 開機管理程式 

- USB 儲存裝置 

- PXE 網路 

- 內部儲存裝置 

您可以立即從特定的裝置開機，或是使用觸控螢幕在該裝置於清單中的項目上向左撥動。 您也可以在 Surface 裝置電源關閉的情況下，立即開機至 USB 裝置或 USB 乙太網路介面卡，方法是同時按下 \[降低音量\] 按鈕和 \[電源\] 按鈕。******** 

若要讓指定的引導順序生效，您必須將 [**啟用備用啟動順序**] 選項設定為 [**開啟**]，如圖7所示。 

![設定 Surface 裝置的開機順序](images/manage-surface-uefi-fig6.png "Configure the boot order for your Surface device")

*圖 7. 設定 Surface 裝置的開機順序* 

您也可以透過 \[針對 PXE 網路開機啟用 IPv6\] 選項，針對 PXE 開啟或關閉 IPv6 支援，例如使用 PXE 執行 Windows 部署，而 PXE 伺服器僅針對 IPv4 進行設定的情況。****  

## UEFI 功能表：管理
[管理] 頁面可讓您管理在合格的裝置上使用零觸控 UEFI 管理和其他功能，包括 Surface Pro 7、Surface Pro X 及 Surface 膝上型電腦3。  

![管理零觸控 UEFI 管理的存取權和其他功能 ](images/manage-surface-uefi-fig7a.png "Manage access to Zero Touch UEFI Management and other features")
 *圖8。管理零觸控 UEFI 管理和其他功能的存取權* 


零觸控 UEFI 管理可讓您在名為 Device 固件配置介面（DFCI）的 Intune 中使用裝置設定檔來遠端系統管理 UEFI 設定。 如果您未設定此設定，管理具有 DFCI 的合格裝置的功能會設定為 [**就緒**]。 若要防止 DFCI，**請選取 [退出宣告]**。 

> [!NOTE]
> 只有 Surface Pro 7、Surface Pro X 和 Surface 膝上型電腦3提供 [UEFI 管理設定] 頁面和使用 DFCI。  

如需詳細資訊，請參閱[SURFACE UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)。

## UEFI 功能表：結束 

使用 [結束 **] 頁面上的 [** **立即重新開機**] 按鈕，即可結束 UEFI 設定，如圖9所示。 

![結束 Surface UEFI 並重新啟動裝置](images/manage-surface-uefi-fig7.png "Exit Surface UEFI and restart the device")

*圖 9. 按一下 \[立即重新啟動\] 以結束 Surface UEFI 並重新啟動裝置*

## Surface UEFI 開機畫面

當您使用 Windows Update 或手動安裝更新 Surface 裝置韌體時，更新不會立即套用到裝置，而是在下一個重新開機循環期間套用。 您可以在[管理 Surface 的驅動程式和韌體更新](https://docs.microsoft.com/surface/manage-surface-pro-3-firmware-updates)中深入了解 Surface 韌體更新過程。 畫面上會顯示韌體更新進度，進度列會以不同的色彩來表示每個元件的韌體。 每個元件的進度列都會顯示在 [圖 9] 到 [18] 中。

![Surface UEFI 韌體更新與藍色進度列](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*圖 10. Surface UEFI 韌體更新會顯示藍色進度列*

![系統內嵌控制器韌體與綠色進度列](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*圖 11. 系統內嵌控制器韌體更新會顯示綠色進度列*

![SAM 控制器韌體更新與橘色進度列](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*圖 12. SAM 控制器韌體更新會顯示橘色進度列*

![Intel Management Engine 韌體與紅色進度列](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*圖 13. Intel Management Engine 韌體更新會顯示紅色進度列*

![Surface 觸控韌體與灰色進度列](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*圖 14. Surface 觸控韌體更新會顯示灰色進度列*

![表面 KIP 固件為淺綠色的進度列](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*圖 15. Surface KIP 固件更新會顯示淺綠色的進度列*

![表面 ISH 固件與粉紅色的進度列](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*圖 16 Surface ISH 固件更新顯示淺粉紅色的進度列*

![具有灰色進度列的 Surface 軌跡板固件](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*圖 17. Surface 軌跡板固件更新顯示粉紅色的進度列*

![含淺灰色進度列的 Surface TCON 固件](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*圖 18. Surface TCON 固件更新會顯示淺灰色進度列*


![含淺紫色進度列的 Surface TPM 固件](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*圖 19. Surface TPM 固件更新顯示紫色進度列*


>[!NOTE]
>隨即會顯示另一個指示安全啟動已停用的警告訊息，如圖19所示。

![表示安全開機已停用的 Surface 開機畫面](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*圖 20. 表示 Surface UEFI 設定中安全開機已停用的 Surface 開機畫面*

## 相關主題

- [Surface UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)

-  [Surface 企業管理模式](surface-enterprise-management-mode.md)
