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
ms.openlocfilehash: 4b0cfd9cadab33d82ae3d0acaa83e007229c6fb8
ms.sourcegitcommit: 109d1d7608ac4667564fa5369e8722e569b8ea36
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/27/2020
ms.locfileid: "10831301"
---
# 乙太網路卡與 Surface 部署


本文提供指引與解答，協助您執行網路部署至 Surface 裝置，包括 Surface Pro 3 及更新版本。

Surface 裝置的網路部署可能會對系統管理員造成一些特殊的挑戰。 因為缺少原生的有線乙太網路卡，系統管理員必須透過卸除式乙太網路卡來提供連線。

##  <a name="select-an-ethernet-adapter-for-surface-devices"></a>選取適用於 Surface 裝置的乙太網路卡


您必須使用有線網路介面卡，才可以解決如何開機到部署環境，或您的部署解決方案要如何辨識裝置的問題。

選擇乙太網路卡的主要考量，是該網路卡會如何從網路將您的 Surface 裝置開機。 如果您是使用 Windows 部署服務（WDS）預暫存用戶端，或如果您使用的是 Microsoft 端點設定管理員，您可能也想要考慮將可移除的乙太網路介面卡專用於特定的 Surface 裝置，或在多個裝置之間共用。 如需有關共用配接器之潛在衝突的詳細資訊，請參閱本文稍後的[使用可移動乙太網卡管理 MAC 位址](#manage-mac-addresses)。

只有使用乙太網路卡或 Microsoft 的擴充座時，才支援從網路開機 (PXE 開機)。 若要從網路開機，乙太網路卡或擴充座中的晶片必須能在 Surface 裝置的韌體中被偵測並設定為開機裝置。 Microsoft 乙太網路卡 (例如 Surface 乙太網路卡和 [Surface 擴充座](https://www.microsoft.com/surface/accessories/surface-dock)) 是使用與 Surface 韌體相容的晶片。

下列乙太網路裝置支援 Surface 裝置的網路開機：

-   從 USB 到乙太網路和 USB 3.0 配接器的 Surface

-   Surface USB 3.0 至千兆乙太網卡

-   Surface 擴充座

-   Surface 3 擴充座

-   Surface Pro 3 擴充座

-   適用於 Surface Pro 和 Surface Pro 2 的擴充座

協力廠商乙太網路卡也支援網路部署，雖然它們不支援 PXE 開機。 若要使用協力廠商乙太網路卡，您必須將驅動程式載入至部署開機映像，且您必須從不同的儲存裝置 (例如 USB 隨身碟) 啟動該開機映像。

##  <a name="boot-surface-devices-from-the-network"></a>從網路將 Surface 裝置開機

若要從網路或連接的 USB 隨身碟開機，您必須指示 Surface 裝置從其他開機裝置開機。 您可以在系統韌體中變更開機順序，以排定 USB 開機裝置的優先順序，或指示它在開機程序期間從其他的開機裝置開機。

若要讓 Surface 裝置從其他開機裝置開機，請依照下列步驟執行：

1.  確定 Surface 裝置電源已經關閉。
2.  長按**降低音量**按鈕。
3.  按下並放開**電源**按鈕。
4.  當系統開始從 USB 隨身碟或乙太網路卡開機之後，放開**降低音量**按鈕。

>[!NOTE]
>除了乙太網路卡，鍵盤也必須連接到 Surface 裝置，以進入預先安裝環境和瀏覽部署精靈。

 
針對 Windows 10，1511 版本與更新版本 (包括適用於 Windows 10，1511 版本的 Windows 評定及部署套件 (Windows ADK) )，預設會有 Microsoft Surface 乙太網路卡的驅動程式。 如果您正在使用使用 Windows 預先安裝環境 (WinPE) 的部署解決方案 (例如 Microsoft Deployment Toolkit)，並且透過 PXE 從網路開機，請確定您的部署解決方案使用最新版本的 Windows ADK。

## <a href="" id="manage-mac-addresses"></a>管理卸除式乙太網路卡的 MAC 位址

系統管理員透過網路執行 Windows 部署的另一項考量，是當您使用相同的乙太網路卡部署到多部電腦時要如何識別電腦。 部署技術常用的識別碼是媒體存取控制 (MAC) 位址，該位址會與每個乙太網路卡關聯。 不過，當使用相同的乙太網路卡來部署到多部電腦時，您無法使用會偵測 MAC 位址的部署技術，因為在不同的電腦上使用卸除式介面卡時會無法區隔 MAC 位址。

避免 MAC 位址衝突最簡單的解決方案，是為每個 Surface 裝置提供專用的卸除式乙太網路介面卡。 對於經常使用乙太網路卡或其他擴充座功能的許多案例而言，這個方法很實際。 不過，並非所有的案例都需要使用擴充座的其他連線，或支援有線網路。

另一個在共用介面卡時避免衝突的可能解決方案，是使用 [Microsoft Deployment Toolkit (MDT)](https://technet.microsoft.com/windows/dn475741) 來執行 Surface 裝置的部署。 MDT 不會使用 MAC 位址來識別個別電腦，因此不受限於此限制。 不過，MDT 會使用 Windows 部署服務來提供 PXE 開機功能，並受限於和前置階段用戶端有關的限制，本節稍後會說明。

當您使用共用的介面卡來部署時，針對受影響之部署技術的解決方案是使用另一種方法來識別唯一系統。 對於 Configuration Manager 和 WDS 而言，兩者皆可能受此問題影響，解決方案是使用電腦製造商內嵌於電腦韌體中的系統通用唯一識別元 (系統 UUID)。 對於 Surface 裝置，您可以在電腦韌體中的 \[裝置資訊\] 底下看到此項目。****

若要存取 Surface 裝置的韌體，請依照下列步驟執行：

1.  確定 Surface 裝置電源已經關閉。
2.  長按**增強音量**按鈕。
3.  按下並放開**電源**按鈕。
4.  裝置開始開機之後，放開**增強音量**按鈕。

當使用 WDS 部署時，只有在部署伺服器設為僅回應已知的前置階段用戶端時，才會使用 MAC 位址識別電腦。 當預先設置用戶端時，系統管理員會在 Active Directory 中建立電腦帳戶，並根據 MAC 位址或系統 UUID 定義該電腦。 若要避免共用乙太網路卡造成識別衝突，您應該使用[系統 UUID 來定義前置階段用戶端](https://technet.microsoft.com/library/cc742034)。 或者，您可以設定 WDS 來回應不需要由 MAC 位址或系統 UUID 定義的未知用戶端，方法是選取 \[Windows 部署伺服器屬性\] 中 [\[PXE 回應\] 索引標籤](https://technet.microsoft.com/library/cc732360)上的 \[回應所有用戶端電腦 (已知及未知)\] 選項。************

使用 Configuration Manager 共用乙太網路卡的衝突可能性會更高。 WDS 只有在設定為使用 MAC 位址來定義個別系統時才會這麼做，而 Configuration Manager 則無論是執行部署到新電腦或未知電腦，皆會使用 MAC 位址來定義個別的系統。 這會導致裝置設定錯誤，或甚至導致無法透過共用乙太網路卡部署多個系統。 此情況有幾種可能的解決方案，詳細說明[如何在多個 SCCM OSD 中使用相同的外部乙太網卡](https://techcommunity.microsoft.com/t5/core-infrastructure-and-security/how-to-use-the-same-external-ethernet-adapter-for-multiple-sccm/ba-p/257374)，這是核心基礎結構和安全性博客的博客文章。

 

 





