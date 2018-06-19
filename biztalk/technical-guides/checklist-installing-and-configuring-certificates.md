---
title: 清单： 安装和配置证书 |Microsoft 文档
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
ms.openlocfilehash: 5e675a60967b5ee34c40f1711f256aff76362d2a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22300493"
---
# <a name="checklist-installing-and-configuring-certificates"></a>清单： 安装和配置证书
本主题介绍在将与 BizTalk Server 使用的证书设置所涉及的步骤。  
  
|步骤|参考|  
|-----------|---------------|  
|评估你的证书要求，并且到与您有关您与证书的相互职责的贸易合作伙伴协议。|中的"评估和计划你使用的证书"部分[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|如果你将使用的私钥，从证书颁发机构 (CA) 请求用于数字签名的私钥-公钥密钥对，并将公钥发送到贸易合作伙伴。<br /><br /> 如果你将使用的公钥，有你贸易合作伙伴请求 CA 中的数字签名的私钥-公钥密钥对，并将公钥发送给你。|[如何为 BizTalk Server 中安装证书](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)|  
|私有或公共密钥安装到适当的证书存储中，并且具有你执行相同操作的贸易合作伙伴。|-   [如何为 BizTalk Server 中安装证书](~/technical-guides/how-to-install-certificates-for-biztalk-server.md)<br />-"安装证书"部分[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|如果使用的 MIME/SMIME 消息的证书，配置 BizTalk Server 以使用证书。|-   [为 MIME 或 SMIME 消息配置证书](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)<br />-"的 MIME/SMIME 配置 BizTalk Server 使用证书"部分中[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|（可选）如果使用具有适配器的证书，配置为使用证书的适配器。|-   [使用适配器配置证书](~/technical-guides/configuring-certificates-with-adapters.md)<br />-"配置 BizTalk 适配器使用证书"部分[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
|（可选）如果使用证书来执行参与方解析，配置该参与方将使用的证书。|[如何为参与方解析配置证书](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)|  
|（可选）如果从一个 BizTalk 组证书导出到另一个中，将证书添加到 BizTalk 应用程序;导出到.msi 文件; 应用程序然后，然后将应用程序导入不同的 BizTalk 组。|-   [如何为参与方解析配置证书](~/technical-guides/how-to-configure-certificates-for-party-resolution.md)<br />-   [如何导出为.msi 文件的应用程序](~/technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-   [如何从.msi 文件导入应用程序](~/technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"导出证书从一个 BizTalk 组到另一个"一节的[管理证书的最佳实践](~/technical-guides/best-practices-for-managing-certificates2.md)|  
  
## <a name="see-also"></a>另请参阅  
 [管理证书的最佳做法](~/technical-guides/best-practices-for-managing-certificates2.md)   
 [BizTalk Server 中的证书的已知的问题](~/technical-guides/known-issues-with-certificates-in-biztalk-server.md)