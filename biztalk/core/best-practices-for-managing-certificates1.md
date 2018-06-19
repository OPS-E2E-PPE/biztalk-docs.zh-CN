---
title: 用于管理 Certificates1 最佳实践 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- best practices, certificates
- certificates, security
- security, certificates
- certificates, best practices
- best practices, security
- security, best practices
ms.assetid: cd182df4-0fcd-409c-9221-89f92e069f07
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e72d87530e5d080bd98ed55c2d29ca9554430375
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232085"
---
# <a name="best-practices-for-managing-certificates"></a>管理证书的最佳实践
本部分提供了在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中管理证书的最佳做法。  
  
-   **执行你环境的威胁模型分析**  
  
     对您的环境进行威胁模型分析可以确定签名证书和加密证书是否有助于缓解安全威胁。  
  
-   **创建与合作伙伴公钥证书的计划**  
  
     与合作伙伴制定发送和接收公钥证书的计划。 如果您不准备使用签名证书进行参与方解析，则公共证书可以附加到消息上，在此情况下，您无需事先在系统中复制证书。  
  
-   **在设置的时间间隔中下载证书吊销列表**  
  
     以固定的时间间隔从证书颁发机构 (CA) 下载证书吊销列表 (CRL)。 建议每周进行一次。 对于 BizTalk Server 所加入的域，如果有 CA 存在，则将自动下载 CRL。  
  
-   **用于提交公钥与合作伙伴建立准则**  
  
     在与合作伙伴达成的服务级别协议 (SLA) 中，建立提交公钥的准则以及在他们的证书即将过期或要吊销证书时通知您。  
  
-   **验证签名证书**  
  
     确保根据证书吊销列表来验证签名证书。 有关如何验证签名的证书的详细信息，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
-   **避免拒绝服务攻击的数字签名**  
  
     确定在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法验证数字签名时可以对消息执行哪种操作。 设置**身份验证**接收端口上的属性将有助于防止拒绝服务攻击。  
  
    > [!NOTE]
    >  **身份验证-放置消息**和**身份验证-保留消息**接收端口上的标志需要参与方解析管道组件配置正确，并且双方是在 BizTalk Server 中定义。 有关配置参与方解析管道组件的详细信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。  
  
-   **创建单独的加密和未加密消息接收位置**  
  
     如果计划从某些合作伙伴接收 MIME 加密的消息而从其他合作伙伴接收未加密的消息，请在不同主机上为加密消息和未加密消息创建单独的接收位置。 当希望仅 MIME 加密的消息时，配置**允许非组成的 MIME 消息**为解码 MIME/SMIME 管道组件中的选项**否**。  
  
-   **与合作伙伴管理证书**  
  
     将证书管理作为您的合作伙伴管理实践的一部分。 在 BizTalk Server 环境中添加或删除参与方时，建议您添加或删除与该合作伙伴相关联的各个证书。  
  
-   **在删除的主机实例之前删除证书**  
  
     在从 BizTalk Server 中删除主机实例前，先删除运行该主机实例的帐户的个人存储中的证书。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)