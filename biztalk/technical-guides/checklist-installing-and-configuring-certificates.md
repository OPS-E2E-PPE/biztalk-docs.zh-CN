---
title: 清单：安装和配置证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76a8f8f6-8d79-4caf-8fba-8cbcb251d461
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c7851d0b688d21bfc8bda28afa78149a1c3904f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295311"
---
# <a name="checklist-installing-and-configuring-certificates"></a>清单：安装和配置证书
本主题介绍设置与 BizTalk Server 使用的证书中所涉及的步骤。  
  
|步骤|参考|  
|-----------|---------------|  
|评估您的证书要求，并与您根据证书的相互责任有关贸易合作伙伴达成共识为。|中的"评估和规划你使用的证书"部分[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|如果使用的私钥，证书颁发机构 (CA) 请求用于数字签名的私钥 / 公钥对，并将公钥发送到您的贸易合作伙伴。<br /><br /> 如果使用的公钥，具有你的贸易合作伙伴请求用于从 CA 中，数字签名的私钥 / 公钥对，并将公钥发送给您。|[如何为 BizTalk Server 安装证书](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)|  
|安装到适当的证书存储中，专用或公用密钥并将执行相同操作您的贸易合作伙伴。|-   [如何为 BizTalk Server 安装证书](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)<br />-"安装证书"部分中的[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|如果使用证书的 MIME/SMIME 消息时，配置 BizTalk Server 以便使用该证书。|-   [为 MIME 或 SMIME 消息配置证书](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)<br />-在"配置使用证书的 BizTalk Server 以便 MIME/SMIME"部分[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|（可选）如果使用具有适配器的证书，将适配器配置为使用该证书。|-   [使用适配器配置证书](~/technical-guides/configuring-certificates-with-adapters.md)<br />-"配置使用证书的 BizTalk 适配器"部分中的[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|（可选）如果使用证书来执行参与方解析，配置要使用的证书的参与方。|[如何为参与方解析配置证书](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)|  
|（可选）如果证书从一个 BizTalk 组导出到另一个，将证书添加到 BizTalk 应用程序;导出到.msi 文件; 应用程序然后将该应用程序导入其他 BizTalk 组。|-   [如何为参与方解析配置证书](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)<br />-   [如何导出到.msi 文件的应用程序](~/technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [如何从某一.msi 文件导入应用程序](~/technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"导出证书从一个 BizTalk 组到另一个"部分中的[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
  
## <a name="see-also"></a>请参阅  
 [管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)   
 [BizTalk Server 中证书的已知问题](~/technical-guides/known-issues-with-certificates-in-biztalk-server.md)