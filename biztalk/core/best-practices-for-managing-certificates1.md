---
title: 用于管理 Certificates1 最佳做法 |Microsoft Docs
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
ms.openlocfilehash: b9aaf8c42b2b0d96e44323af6ee4a0e164a3f46c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004198"
---
# <a name="best-practices-for-managing-certificates"></a>管理证书的最佳实践
本部分提供了在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 环境中管理证书的最佳做法。  
  
- **进行威胁模型分析您的环境**  
  
   对您的环境进行威胁模型分析可以确定签名证书和加密证书是否有助于缓解安全威胁。  
  
- **创建与合作伙伴的公钥证书计划**  
  
   与合作伙伴制定发送和接收公钥证书的计划。 如果您不准备使用签名证书进行参与方解析，则公共证书可以附加到消息上，在此情况下，您无需事先在系统中复制证书。  
  
- **在设置的时间间隔下载证书吊销列表**  
  
   以固定的时间间隔从证书颁发机构 (CA) 下载证书吊销列表 (CRL)。 建议每周进行一次。 对于 BizTalk Server 所加入的域，如果有 CA 存在，则将自动下载 CRL。  
  
- **指导原则与合作伙伴建立提交公钥的**  
  
   在与合作伙伴达成的服务级别协议 (SLA) 中，建立提交公钥的准则以及在他们的证书即将过期或要吊销证书时通知您。  
  
- **验证签名证书**  
  
   确保根据证书吊销列表来验证签名证书。 有关如何验证签名证书的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
- **避免拒绝服务攻击的数字签名**  
  
   确定在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 无法验证数字签名时可以对消息执行哪种操作。 设置**身份验证**接收端口上的属性将有助于防止拒绝服务攻击。  
  
  > [!NOTE]
  >  **身份验证-删除消息**并**身份验证-保留消息**接收端口上的标志需要正确配置参与方解析管道组件和参与方是在 BizTalk Server 中定义。 有关配置参与方解析管道组件的详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。  
  
- **创建单独的加密和未加密消息接收位置**  
  
   如果计划从某些合作伙伴接收 MIME 加密的消息而从其他合作伙伴接收未加密的消息，请在不同主机上为加密消息和未加密消息创建单独的接收位置。 要得到仅 MIME 加密的消息，请配置**允许非 MIME 消息**解码 MIME/SMIME 管道组件中的选项**否**。  
  
- **管理证书与合作伙伴**  
  
   将证书管理作为您的合作伙伴管理实践的一部分。 在 BizTalk Server 环境中添加或删除参与方时，建议您添加或删除与该合作伙伴相关联的各个证书。  
  
- **删除主机实例前删除证书**  
  
   在从 BizTalk Server 中删除主机实例前，先删除运行该主机实例的帐户的个人存储中的证书。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)