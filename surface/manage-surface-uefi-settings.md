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
ms.reviewer: hachidan
manager: laurawi
ms.date: 04/13/2021
ms.openlocfilehash: 1ba8da50472927ff106b7243d89c15995844b191
ms.sourcegitcommit: 21fcd329a7b0c82c69e2a65c423d47c5b23b4e7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/13/2021
ms.locfileid: "11883020"
---
# <a name="manage-surface-uefi-settings"></a>管理 Surface UEFI 設定

 Surface PC 裝置的設計目的是使用 Microsoft 專為這些裝置 (UEFI) 統一可擴展的固件介面。 Surface UEFI 設定提供啟用或停用內建裝置和元件、保護 UEFI 設定不受變更，以及調整 Surface 裝置開機設定的能力。

## <a name="supported-products"></a>支援的產品

下列支援 UEFI 管理：

- Surface Pro 4，Surface Pro (第 5 代) 、Surface Pro 6、Surface Pro 7、Surface Pro 7+、Surface Pro X
- Surface Laptop (第 1 代) ，Surface Laptop 2，Surface Laptop 3，Surface Laptop，Surface Laptop 4
- Surface Studio (第 1 代) ，Surface Studio 2
- Surface Book，Surface Book 2，Surface Book 3
- Surface Go， Surface Go 2[ <sup> 1 </sup> ](#references)

## <a name="support-for-cloud-based-management"></a>支援雲端管理

有了裝置 (DFCI) 設定檔內建的 Microsoft Intune (現在可在公用預覽) 中使用，Surface UEFI 管理可將新式管理堆疊延伸到 UEFI 硬體層級。 DFCI 支援零接觸式設定、消除BIOS 密碼、提供安全性設定控制，包括開機選項和內建的周邊設備，以及為日後進一步的安全性案例打下基礎。 DFCI 目前適用于 Surface Pro 7+、Surface Laptop、Surface Book 3、Surface Laptop 3、Surface Pro 7 和 Surface Pro X。 詳情請參閱[Surface UEFI 設定 Intune 管理](surface-manage-dfci-guide.md)。

## <a name="open-surface-uefi-menu"></a>開啟 Surface UEFI 功能表

若要在系統啟動期間調整 UEFI 設定：

1. 關閉 Surface 並等候約 10 秒，確定已關閉。
2. 按住放大 **音量** 按鈕，並同步選取並放開 **Power 按鈕。**
3. 當 Microsoft 或 Surface 標誌出現在您的螢幕上時，請**** 繼續按住放大按鈕，直到 UEFI 畫面出現。

## <a name="uefi-pc-information-page"></a>UEFI 電腦資訊頁面

電腦資訊頁面包含 Surface 裝置的詳細資訊：

- **模型**– 您的 Surface 裝置模型會顯示在這裡，例如第 2 或 Surface Book 7 Surface Pro顯示。 裝置的確切組態並不會顯示 (例如處理器、磁碟大小或記憶體大小)。
- **UUID** – 這個通用唯一識別碼是裝置特定的號碼，用來在部署或管理期間識別裝置。

- **序號** – 此號碼是用來識別這個特定的 Surface 裝置，以進行資產標記和支援案例。
- **資產標記**– 資產標記是使用[資產標記工具](assettag.md)指派至 Surface 裝置。

您也能找到 Surface 裝置韌體的詳細資訊。 Surface 裝置擁有數個內部元件，每個元件都會執行不同版本的韌體。 下列裝置的個別韌體版本都會顯示於 \[電腦資訊\] 頁面上 \(如圖 1 所示\)：****

- 系統 UEFI

- SAM 控制器

- Intel 管理引擎

- 系統內嵌控制器

- 觸控韌體

:::image type="content" alt-text="系統資訊和固件版本資訊。" source="images/manage-surface-uefi-figure-1.png":::

*圖 1. 系統資訊和韌體版本資訊*

您可以在裝置的 [Surface 更新記錄](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中找到 Surface 裝置最新韌體版本的最新資訊。

## <a name="uefi-security-page"></a>UEFI 安全性頁面

:::image type="content" alt-text="設定 Surface UEFI 安全性設定。" source="images/manage-surface-uefi-fig4.png":::

*圖 2. 設定 Surface UEFI 安全性設定*

安全性頁面可讓您設定密碼以保護 UEFI 設定。 此密碼必須在將 Surface 裝置開機至 UEFI 時輸入。 密碼可以包含下列字元 (如圖 3 所示) ：

- 大寫字母：A-Z

- 小寫字母：a-z

- 數字：1-0

- 特殊字元：！@#$%^&* () ？<>{} []-_=+|.，;：''

密碼必須至少為 6 個字元，並會區分大小寫。

![新增密碼以保護 Surface UEFI 設定](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*圖 3. 新增密碼以保護 Surface UEFI 設定*

您也可以在 \[安全性\] 頁面上變更 Surface 裝置的安全開機設定。 安全開機技術能防止未經授權的啟動碼將您的 Surface 裝置開機，這將能針對 Bookit 和 Rootkit 類型的惡意程式碼感染提供保護。 您可以停用安全開機以允許 Surface 裝置使用第三方作業系統或可開機媒體進行開機。 您也可以設定安全啟動以使用協力廠商憑證，如圖 4 所示。 於 TechNet Library 深入了解[安全開機](https://msdn.microsoft.com/windows/hardware/commercialize/manufacture/desktop/secure-boot-overview)。

![設定安全開機](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*圖 4. 設定安全開機*

視您的裝置不同，您也可以查看 TPM 是否已啟用或停用。 如果您沒看到啟用**TPM**設定，請在 Windows 中開啟 tpm.msc 以檢查狀態，如圖 5 所示。 TPM 是用來以 BitLocker 為您裝置的資料驗證加密。 若要深入瞭解，請參閱 [BitLocker 概觀](/windows/security/information-protection/bitlocker/bitlocker-overview)。

![TPM 主機](images/manage-surface-uefi-fig5-a.png "TPM console")

*圖 5. TPM 主機*

## <a name="uefi-menu-devices"></a>UEFI 功能表：裝置

裝置頁面可讓您啟用或停用特定裝置和元件，包括：

- 固定 USB 埠

- MicroSD 或 SD 記憶卡插槽

- 後方攝影機

- 前方攝影機

- 紅外線 (IR) 相機

- Wi-Fi 和藍牙

- 內建音訊 (擴音器和麥克風)

每個裝置都列出一個滑杆按鈕，您可以移至啟用**** (或關閉) 或關閉**** () 位置，如圖 6 所示。

:::image type="content" alt-text="啟用及停用特定裝置。" source="images/manage-surface-uefi-fig5a.png":::

*圖 6. 啟用或停用特定裝置*

## <a name="uefi-menu-boot-configuration"></a>UEFI 功能表：啟動組式

啟動組組頁面可讓您變更啟動裝置的順序，以及啟用或停用下列裝置啟動：

- Windows 開機管理程式

- USB 儲存裝置

- PXE 網路

- 內部儲存裝置

您可以立即從特定的裝置開機，或是使用觸控螢幕在該裝置於清單中的項目上向左撥動。 您也可以在 Surface 裝置電源關閉的情況下，立即開機至 USB 裝置或 USB 乙太網路介面卡，方法是同時按下 \[降低音量\] 按鈕和 \[電源\] 按鈕。********

若要讓指定的啟動順序生效，您必須將啟用替代啟動順序**** 選項設定為**On**，如圖 7 所示。

:::image type="content" alt-text="設定 Surface 裝置開機順序。" source="images/manage-surface-uefi-fig6.png":::

*圖 7. 設定 Surface 裝置的開機順序*

您也可以透過 \[針對 PXE 網路開機啟用 IPv6\] 選項，針對 PXE 開啟或關閉 IPv6 支援，例如使用 PXE 執行 Windows 部署，而 PXE 伺服器僅針對 IPv4 進行設定的情況。****  

## <a name="uefi-menu-management"></a>UEFI 功能表：管理

管理頁面可讓您管理零觸控 UEFI 管理和其他功能在合格裝置上的使用，包括 Surface Pro 7、Surface Pro X 和 Surface Laptop 3。  

:::image type="content" alt-text="管理零觸控 UEFI 管理和其他功能的存取權。" source="images/manage-surface-uefi-fig7a.png":::

*圖 8. 管理零觸控 UEFI 管理和其他功能的存取權*

零觸控 UEFI 管理可讓您在 Intune 中使用稱為 DFCI (裝置設定檔，以遠端系統管理 UEFI) 設定。 如果您沒有設定此設定，使用 DFCI 管理合格裝置的能力會設定為 **Ready**。 若要防止 DFCI，請選取 **退出宣告**。

> [!NOTE]
> UEFI 管理設定頁面及 DFCI 的使用目前適用于 Surface Pro 7+、Surface Laptop Go、Surface Book 3、Surface Laptop 4、Surface Laptop 3、Surface Pro 7 和 Surface Pro X。若要深入瞭解，請參閱[Surface UEFI 設定 Intune 管理](surface-manage-dfci-guide.md)。

## <a name="uefi-menu-exit"></a>UEFI 功能表：離開

使用離開**頁面上**的立即重新開機按鈕****，以退出 UEFI 設定，如圖 9 所示。

:::image type="content" alt-text="離開 Surface UEFI 並重新啟動裝置。" source="images/manage-surface-uefi-fig7.png":::

*圖 9. 按一下 \[立即重新啟動\] 以結束 Surface UEFI 並重新啟動裝置*

## <a name="surface-uefi-boot-screens"></a>Surface UEFI 開機畫面

當您使用 Windows Update 或手動安裝更新 Surface 裝置韌體時，更新不會立即套用到裝置，而是在下一個重新開機循環期間套用。 您可以在管理及部署 Surface 驅動程式和固件更新中，進一步瞭解 Surface 固件 [更新程式](manage-surface-driver-and-firmware-updates.md)。 畫面上會顯示韌體更新進度，進度列會以不同的色彩來表示每個元件的韌體。 每個元件的進度列會顯示在圖 9 到 18 中。

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

![具有淺綠色進度條的 Surface KIP 固件](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*圖 15. Surface KIP 固件更新會顯示淺綠色進度列*

![具有粉紅色進度條的 Surface ISH 固件](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*圖 16 Surface ISH 的固件更新會顯示淺粉紅色的進度列*

![具有灰色進度列的 Surface 軌跡板固件](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*圖 17. Surface Trackpad 的固件更新會顯示粉紅色的進度列*

![具有淺灰色進度條的 Surface TCON 固件](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*圖 18. Surface TCON 固件更新會顯示淺灰色進度列*

![具有淺紫色進度條的 Surface TPM 固件](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*圖 19. Surface TPM 的固件更新會顯示紫色的進度列*

>[!NOTE]
>系統會顯示另一則警告訊息，指出安全啟動已停用，如圖 19 所示。

![表示安全開機已停用的 Surface 開機畫面](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*圖 20. 表示 Surface UEFI 設定中安全開機已停用的 Surface 開機畫面*

## <a name="references"></a>參考

1. Surface Go 和 Surface Go 2 使用協力廠商 UEFI，且不支援 DFCI。

## <a name="related-topics"></a>相關主題

- [Surface UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)

- [Surface 企業管理模式](surface-enterprise-management-mode.md)
