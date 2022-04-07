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
ms.date: 04/01/2022
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: e38fb3ae8a25fddfcb64985a64b41d4d2e084178
ms.sourcegitcommit: b922aaf7287bdfb99f848aad455b2b4001b8f5be
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2022
ms.locfileid: "12472652"
---
# <a name="manage-surface-uefi-settings"></a>管理 Surface UEFI 設定

 Surface PC 裝置的設計目的是利用 Microsoft 專為這些裝置設計的唯一整合可延伸韌體介面 (UEFI) 。 Surface UEFI 設定可讓您啟用或停用內建裝置和元件、防止變更 UEFI 設定，以及調整 Surface 裝置開機設定。

## <a name="supported-products"></a>支援的產品

下列專案支援 UEFI 管理：

- Surface Pro 4、Surface Pro (第 5 代) 、Surface Pro 6、Surface Pro 7、Surface Pro 7+ (商業 SKU 僅) ，僅) Surface Pro 8 個 (商業 SKU，Surface Pro X
- Surface Laptop (第 1 代) 、Surface Laptop 2、Surface Laptop 3 (Intel 處理器僅) 、Surface Laptop Go、Surface Laptop僅) 4 個 (商業 SKU，Surface Laptop SE
- Surface Studio (第 1 代) ，Surface Studio 2
- Surface Book (所有世代) 
- Surface Laptop Studio 僅 (商業 SKU) 
- Surface Go、Surface Go [21 <sup> </sup> ](#references)、Surface Go 3 (僅限商業 SKU) 

>[!TIP]
> 商業 SKU (也稱為Surface 商務版) 執行Windows 10 專業版/Enterprise或Windows 11 專業版/Enterprise;取用者 SKU 執行Windows 10/Windows 11 家用版。 在 UEFI 中，商業 SKU 是唯一具有 [ [裝置] 頁面](#uefi-devices-page) 和管理 [頁面](#uefi-management-page)功能的模型。 若要深入瞭解， [請參閱檢視您的系統資訊](https://support.microsoft.com/windows/view-your-system-info-a965a8f2-0773-1d65-472a-1e747c9ebe00)。 


## <a name="support-for-cloud-based-management"></a>支援雲端式管理

使用裝置韌體組態介面 (內建在Microsoft Intune (內的 DFCI) 設定檔現在可在公開預覽) 中使用，Surface UEFI 管理會將新式管理堆疊向下延伸至 UEFI 硬體層級。 DFCI 支援零觸控布建、消除 BIOS 密碼、提供安全性設定的控制 ，包括開機選項和內建周邊，並為未來的進階安全性案例打下基礎。 DFCI 目前適用于 Surface Laptop SE、Surface Laptop Studio、Surface Pro 8、Surface Go 3、Surface Laptop 4、Surface Laptop Go、Surface Book 3、Surface Laptop 3、Surface Pro 7+、Surface Pro 7 和 Surface Pro X。如需詳細資訊，請參閱[surface UEFI 設定的Intune管理](surface-manage-dfci-guide.md)。

## <a name="open-surface-uefi-menu"></a>開啟 Surface UEFI 功能表

若要在系統啟動期間調整 UEFI 設定：

1. 關閉 Surface 並等候約 10 秒，以確定已關閉。
2. 按住 [向上音 **量]** 按鈕，同步選取並放開 **電源按鈕。**
3. 當 Microsoft 或 Surface 標誌出現在您的畫面上時，請繼續按住 [向上卷 **] 按鈕，** 直到 UEFI 畫面出現為止。

## <a name="uefi-pc-information-page"></a>UEFI 電腦資訊頁面

電腦資訊頁面包含 Surface 裝置的詳細資訊：

- **模型**– Surface 裝置的型號會顯示在這裡，例如Surface Book 2 或Surface Pro 7。 您的裝置的確切設定不會顯示 (例如處理器、磁片大小或記憶體大小) 。
- **UUID** – 這個通用唯一識別碼是裝置特定的號碼，用來在部署或管理期間識別裝置。

- **序號** – 此數目可識別資產標記和支援案例的這個特定 Surface 裝置。
- **資產標記**– 資產標記是使用[資產標記工具](assettag.md)指派至 Surface 裝置。

您也能找到 Surface 裝置韌體的詳細資訊。 Surface 裝置擁有數個內部元件，每個元件都會執行不同版本的韌體。 下列裝置的個別韌體版本都會顯示於 \[電腦資訊\] 頁面上 \(如圖 1 所示\)：****

- 系統 UEFI

- SAM 控制器

- Intel 管理引擎

- 系統內嵌控制器

- 觸控韌體

:::image type="content" alt-text="系統資訊和韌體版本資訊。" source="images/manage-surface-uefi-figure-1.png":::

*圖 1. 系統資訊和韌體版本資訊*

您可以在裝置的 [Surface 更新記錄](https://www.microsoft.com/surface/support/install-update-activate/surface-update-history)中找到 Surface 裝置最新韌體版本的最新資訊。

## <a name="uefi-security-page"></a>UEFI 安全性頁面

:::image type="content" alt-text="設定 Surface UEFI 安全性設定。" source="images/manage-surface-uefi-fig4.png":::

*圖 2. 設定 Surface UEFI 安全性設定*

[安全性] 頁面可讓您設定密碼來保護 UEFI 設定。 此密碼必須在將 Surface 裝置開機至 UEFI 時輸入。 密碼可以包含下列字元 (如圖 3) 所示：

- 大寫字母：A-Z

- 小寫字母：a-z

- 數字：1-0

- 特殊字元：！@#$%^&* () ？<>{} []-_=+|.，;：''"

密碼必須至少為六個字元，而且會區分大小寫。

![新增密碼以保護 Surface UEFI 設定。](images/manage-surface-uefi-fig2.png "Add a password to protect Surface UEFI settings")

*圖 3. 新增密碼以保護 Surface UEFI 設定*

在 [安全性] 頁面上，您也可以變更 Surface 裝置上安全開機的設定。 安全開機技術能防止未經授權的啟動碼將您的 Surface 裝置開機，這將能針對 Bookit 和 Rootkit 類型的惡意程式碼感染提供保護。 您可以停用安全開機以允許 Surface 裝置使用第三方作業系統或可開機媒體進行開機。 您也可以設定安全開機以使用協力廠商憑證，如圖 4 所示。 若要深入瞭解，請參閱 [安全開機](/windows-hardware/design/device-experiences/oem-secure-boot)。

![設定安全開機。](images/manage-surface-uefi-fig3.png "Configure Secure Boot")

*圖 4. 設定安全開機*

視您的裝置而定，您也可以查看 TPM 是否已啟用或停用。 如果您沒有看到 **[啟用 TPM**] 設定，請在 Windows 中開啟 tpm.msc 以檢查狀態，如圖 5 所示。 TPM 可用來使用 BitLocker 驗證裝置資料的加密。 若要深入瞭解，請參閱 [BitLocker 概觀](/windows/security/information-protection/bitlocker/bitlocker-overview)。

![TPM 主控台。](images/manage-surface-uefi-fig5-a.png "TPM console")

*圖 5. TPM 主控台*

## <a name="uefi-devices-page"></a>UEFI 裝置頁面

[裝置] 頁面可讓您在合格裝置上啟用或停用特定元件，包括Surface Pro 8、Surface Go 3、Surface Laptop Studio、Surface Pro 7+、Surface Pro 7、Surface Pro X、Surface Laptop 4、Surface Laptop 3、Surface Laptop SE 和 Surface Book 3。 元件包含下列各項：

- 停駐 USB 埠

- MicroSD 或 SD 記憶卡插槽

- 後方攝影機

- 前方攝影機

- 紅外線 (IR) 相機

- Wi-Fi 和藍牙

- 內建音訊 (擴音器和麥克風)

每個裝置都會列出一個滑杆按鈕，您可以 **移至 [** 啟用 (]) 或 **[關閉** ] (停用) 位置，如圖 6 所示。

:::image type="content" alt-text="啟用和停用特定裝置。" source="images/manage-surface-uefi-fig5a.png":::

*圖 6. 啟用或停用特定裝置*

## <a name="uefi-boot-configuration-page"></a>UEFI 開機設定頁面

[開機設定] 頁面可讓您變更開機裝置的順序，以及啟用或停用下列裝置的開機：

- Windows 開機管理程式

- USB 儲存裝置

- PXE 網路

- 內部儲存裝置

您可以立即從特定裝置開機，或使用觸控式螢幕向左撥動清單中的裝置專案。 您也可以在 Surface 裝置電源關閉的情況下，立即開機至 USB 裝置或 USB 乙太網路介面卡，方法是同時按下 \[降低音量\] 按鈕和 \[電源\] 按鈕。********

若要讓指定的開機順序生效，您必須將 [ **啟用替代開機順序** ] 選項設定為 [ **開**啟]，如圖 7 所示。

:::image type="content" alt-text="設定 Surface 裝置的開機順序。" source="images/manage-surface-uefi-fig6.png":::

*圖 7. 設定 Surface 裝置的開機順序*

您也可以使用 [**啟用 IPv6 for PXE 網路開機**] 選項來開啟和關閉 PXE 的 IPv6 支援，例如，使用 PXE 執行Windows部署時，其中的 PXE 伺服器僅針對 IPv4 進行設定。  

## <a name="uefi-management-page"></a>UEFI 管理頁面

[管理] 頁面可讓您管理在合格裝置上使用零觸控 UEFI 管理和其他功能，包括Surface Pro 8、Surface Go 3、Surface Laptop Studio、Surface Pro 7+、Surface Pro 7、Surface Pro X、Surface Laptop 4、Surface Laptop 3、Surface Laptop SE 和 Surface Book 3。 

:::image type="content" alt-text="管理零觸控 UEFI 管理和其他功能的存取權。" source="images/manage-surface-uefi-fig7a.png":::

*圖 8. 管理對零觸控 UEFI 管理和其他功能的存取*

零觸控 UEFI 管理可讓您使用名為裝置韌體設定介面 (DFCI) Intune內的裝置設定檔，從遠端系統管理 UEFI 設定。 如果您未設定此設定，使用 DFCI 管理合格裝置的能力會設定為 [ **就緒]**。 若要防止 DFCI，請選取 **[退出]**。

> [!NOTE]
> UEFI 管理設定頁面和 DFCI 的使用目前適用于 Surface Laptop SE、Surface Laptop Studio、Surface Pro 8、Surface Go 3、Surface Laptop 4、Surface Laptop Go、Surface Book 3、Surface Laptop 3、Surface Pro 7+、Surface Pro 7 和 Surface Pro X。 若要深入瞭解，[請參閱Intune Surface UEFI 設定的管理](surface-manage-dfci-guide.md)。

## <a name="uefi-exit-page"></a>UEFI 結束頁面

使用 [**結束**] 頁面上的 [**立即重新開機**] 按鈕結束 UEFI 設定，如圖 9 所示。

:::image type="content" alt-text="結束 Surface UEFI 並重新啟動裝置。" source="images/manage-surface-uefi-fig7.png":::

*圖 9. 按一下 \[立即重新啟動\] 以結束 Surface UEFI 並重新啟動裝置*

## <a name="surface-uefi-boot-screens"></a>Surface UEFI 開機畫面

當您使用Windows Update或手動安裝更新 Surface 裝置韌體時，更新不會立即套用至裝置，而是在下一次重新開機週期期間套用。 您可以在管理和 [部署 Surface 驅動程式和韌體更新](manage-surface-driver-and-firmware-updates.md)中深入瞭解 Surface 韌體更新程式。 韌體更新進度會顯示在具有不同色彩進度列的畫面上，以指出每個元件的韌體。 每個元件的進度列都會顯示在圖 9 到 18 中。

![使用藍色進度列更新 Surface UEFI 韌體。](images/manage-surface-uefi-fig8.png "Surface UEFI firmware update with blue progress bar")

*圖 10. Surface UEFI 韌體更新會顯示藍色進度列*

![具有綠色進度列的系統內嵌控制器韌體。](images/manage-surface-uefi-fig9.png "System Embedded Controller firmware with green progress bar")

*圖 11. 系統內嵌控制器韌體更新會顯示綠色進度列*

![SAM 控制器韌體以橙色進度列更新。](images/manage-surface-uefi-fig10.png "SAM Controller firmware update with orange progress bar")

*圖 12. SAM 控制器韌體更新會顯示橘色進度列*

![具有紅色進度列的 Intel Management Engine 韌體。](images/manage-surface-uefi-fig11.png "Intel Management Engine firmware with red progress bar")

*圖 13. Intel Management Engine 韌體更新會顯示紅色進度列*

![具有灰色進度列的 Surface 觸控韌體。](images/manage-surface-uefi-fig12.png "Surface touch firmware with gray progress bar")

*圖 14. Surface 觸控韌體更新會顯示灰色進度列*

![具有淺綠色進度列的 Surface KIP 韌體。](images/manage-surface-uefi-fig13.png "Surface touch firmware with light green progress bar")

*圖 15. Surface KIP 韌體更新會顯示淺綠色進度列*

![具有粉紅色進度列的 Surface ISH 韌體。](images/manage-surface-uefi-fig14.png "Surface ISH firmware with pink progress bar")

*圖 16 Surface ISH 韌體更新會顯示淺粉色進度列*

![具有灰色進度列的 Surface Trackpad 韌體。](images/manage-surface-uefi-fig15.png "Surface Trackpad firmware with gray progress bar")

*圖 17. Surface Trackpad 韌體更新會顯示粉紅色進度列*

![具有淺灰色進度列的 Surface TCON 韌體。](images/manage-surface-uefi-fig16.png "Surface TCON firmware with light gray progress bar")

*圖 18. Surface TCON 韌體更新會顯示淺灰色進度列*

![具有淺紫色進度列的 Surface TPM 韌體。](images/manage-surface-uefi-fig17.png "Surface TPM firmware with purple progress bar")

*圖 19. Surface TPM 韌體更新會顯示紫色進度列*

>[!NOTE]
>另一則表示已停用安全開機的警告訊息隨即顯示，如圖 19 所示。

![表示已停用安全開機的 Surface 開機畫面。](images/manage-surface-uefi-fig18.png "Surface boot screen that indicates Secure Boot has been disabled")

*圖 20. 表示 Surface UEFI 設定中安全開機已停用的 Surface 開機畫面*

## <a name="references"></a>參考

1. Surface Go 和 Surface Go 2 使用協力廠商 UEFI，不支援 DFCI。 DFCI 目前適用于 Surface Laptop SE、Surface Laptop Studio、Surface Pro 8、Surface Go 3、Surface Laptop 4、Surface Laptop Go、Surface Book 3、Surface Laptop 3、Surface Pro 7+、Surface Pro 7 和 Surface Pro X。

## <a name="related-topics"></a>相關主題

- [Surface UEFI 設定的 Intune 管理](surface-manage-dfci-guide.md)

- [Surface 企業管理模式](surface-enterprise-management-mode.md)
