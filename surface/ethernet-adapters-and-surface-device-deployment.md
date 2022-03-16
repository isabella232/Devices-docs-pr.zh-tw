---
title: 乙太網路卡與 Surface 部署 (Surface)
description: 本文章提供的指導方針與解答可協助您執行 Surface 裝置的網路部署。
ms.assetid: 5273C59E-6039-4E50-96B3-426BB38A64C0
ms.reviewer: ''
manager: laurawi
keywords: ethernet, deploy, removable, network, connectivity, boot, firmware, device, adapter, PXE boot, USB, 乙太網路, 部署, 卸除式, 網路, 連線能力, 開機, 韌體, 裝置, 介面卡, PXE 開機
ms.localizationpriority: medium
ms.prod: w10
ms.mktglfcycl: deploy
ms.pagetype: surface, devices
ms.sitesec: library
author: coveminer
ms.author: greglin
ms.topic: article
ms.audience: itpro
appliesto:
- Windows 10
- Windows 11
ms.openlocfilehash: ec73d437d2784ffbceb350f38507524e761df8dd
ms.sourcegitcommit: beb2f9db90b19b74da6cdee8717cc0888f3b1d70
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/16/2022
ms.locfileid: "12448476"
---
# <a name="ethernet-adapters-and-surface-deployment"></a>乙太網路卡與 Surface 部署

本文將說明如何執行最新 Surface 裝置的網路部署，包括 Surface Pro 3 及更新版本。

Surface 裝置的網路部署可能會對系統管理員造成一些特殊的挑戰。 因為缺少原生的有線乙太網路卡，系統管理員必須透過卸除式乙太網路卡來提供連線。

## <a name="select-an-ethernet-adapter-for-surface-devices"></a>選取適用於 Surface 裝置的乙太網路卡

您必須使用有線網路介面卡，才可以解決如何開機到部署環境，或您的部署解決方案要如何辨識裝置的問題。

選取乙太網路介面卡時，主要考慮的是介面卡如何從網路啟動 Surface 裝置。 假設您在部署服務中Windows部署 (WDS) 或Microsoft Endpoint Configuration Manager。 在這種情況下，您可能也想要考慮可移除的乙太網路介面卡是否專屬於特定的 Surface 裝置，或在多個裝置之間共用。 有關共用配接器的潛在衝突詳細資訊，請參閱本文稍後使用可移除[](#manage-mac-addresses)的乙太網路介面卡管理 MAC 位址。

只有在使用 Microsoft 的乙太網 (或固定基座) 才能從網路啟動 PXE 啟動。 必須偵測乙太網路介面卡或基座中的組線，並將其配置為 Surface 裝置之固件中的啟動裝置。 Microsoft 乙太網路介面卡 ，例如 Surface 乙太網路介面卡和 [Surface Dock](https://www.microsoft.com/surface/accessories/surface-dock)，會使用與 Surface 固件相容的機組。

下列乙太網路裝置支援 Surface 裝置的網路開機：

- Surface USB-C 到乙太網路和 USB 3.0 介面卡
- Surface USB 3.0 到 Gigabit 乙太網路介面卡
- Microsoft USB-C 旅遊樞紐
- Surface 擴充座
- Surface Dock 2
- Surface 3 的固定座
- 適用于 3 的固定Surface Pro座 
- 適用於 Surface Pro 和 Surface Pro 2 的擴充座

協力廠商乙太網路卡也支援網路部署，雖然它們不支援 PXE 開機。 若要使用協力廠商乙太網路介面卡，您必須將驅動程式載入至部署啟動映射，而且您必須從另一個儲存裝置啟動該啟動映射，例如 USB 記憶棒。

## <a name="boot-surface-devices-from-the-network"></a>從網路將 Surface 裝置開機

若要從網路或連接的 USB 隨身碟開機，您必須指示 Surface 裝置從其他開機裝置開機。 您可以在系統固件中變更啟動順序，以排定 USB 啟動裝置優先順序，或在啟動程式期間從替代啟動裝置啟動。

**若要從替代啟動裝置啟動：**

1. 確定 Surface 裝置電源已經關閉。
2. 長按**降低音量**按鈕。
3. 按下並放開**電源**按鈕。
4. 當系統開始從 USB 隨身碟或乙太網路卡開機之後，放開**降低音量**按鈕。

>[!NOTE]
>除了乙太網路卡，鍵盤也必須連接到 Surface 裝置，以進入預先安裝環境和瀏覽部署精靈。

針對 Windows 10，1511 版本與更新版本 (包括適用於 Windows 10，1511 版本的 Windows 評定及部署套件 (Windows ADK) )，預設會有 Microsoft Surface 乙太網路卡的驅動程式。 如果您使用的是使用 Windows 預先安裝環境 (WinPE) 的部署解決方案 ，例如 Microsoft 部署工具組，並使用 PXE 從網路啟動，請確保您的部署解決方案使用最新版本的 Windows ADK。

## <a name="manage-mac-addresses-with-removable-ethernet-adapters"></a><a href="" id="manage-mac-addresses"></a>管理卸除式乙太網路卡的 MAC 位址

系統管理員在網路中執行Windows的另一個考慮，是識別使用同一個乙太網路介面卡部署到多部電腦時的電腦。 部署技術常用的識別碼是每個乙太網路介面卡 (MAC) 位址。 不過，當您使用相同的乙太網路介面卡部署到多部電腦時，您無法使用可檢查 MAC 位址的部署技術，因為在不同電腦上使用時，無法區分可移除介面卡的 MAC 位址。

避免 MAC 位址衝突最簡單的解決方案，是為每個 Surface 裝置提供專用的卸除式乙太網路介面卡。 對於經常使用乙太網路卡或其他擴充座功能的許多案例而言，這個方法很實際。 不過，並非所有的案例都需要使用擴充座的其他連線，或支援有線網路。

另一個在共用介面卡時避免衝突的可能解決方案，是使用 [Microsoft Deployment Toolkit (MDT)](/mem/configmgr/mdt) 來執行 Surface 裝置的部署。 MDT 不會使用 MAC 位址來識別個別電腦，因此不受限於此限制。 不過，MDT 確實Windows部署服務來提供 PXE 啟動功能，並受限於階段前用戶端的限制，如本節稍後所述。

當您使用共用的介面卡來部署時，針對受影響之部署技術的解決方案是使用另一種方法來識別唯一系統。 針對 Configuration Manager 和 WDS ，這兩者均會受到此問題影響，解決方案是使用電腦製造商內嵌于電腦 (System UUID) System Unique 識別碼) 。 對於 Surface 裝置，您可以在電腦韌體中的 \[裝置資訊\] 底下看到此項目。****

**若要存取 Surface 裝置之固件：**

1. 確定 Surface 裝置電源已經關閉。
2. 長按**增強音量**按鈕。
3. 按下並放開**電源**按鈕。
4. 機器開始啟動之後，放開音量 **增加** 按鈕。

當使用 WDS 部署時，只有在部署伺服器設為僅回應已知的前置階段用戶端時，才會使用 MAC 位址識別電腦。 當預先設置用戶端時，系統管理員會在 Active Directory 中建立電腦帳戶，並根據 MAC 位址或系統 UUID 定義該電腦。 若要避免共用乙太網路卡造成識別衝突，您應該使用[系統 UUID 來定義前置階段用戶端](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/cc742034(v=ws.11))。 

或者，您可以設定 WDS 以回應不需要 MAC 位址或 System UUID 定義之未知用戶端。 在部署**伺服器屬性** (的[ **PX** ](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc732360(v=ws.11)) **Windows** E 回應) 選取所有用戶端電腦的回復選項。

使用 Configuration Manager 共用乙太網路卡的衝突可能性會更高。 當 WDS 只使用 MAC 位址來定義個別系統時，Configuration Manager 每當部署到新的或未知的電腦時，都會使用 MAC 位址來定義不同的系統。 這會導致裝置設定錯誤，或甚至導致無法透過共用乙太網路卡部署多個系統。 如何在多個 [SCCM OSD](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374)中使用同一個外部乙太網路介面卡，詳細說明幾種可能的解決方案。
