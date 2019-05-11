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
ms.openlocfilehash: b01936259f9259335f43b39ed19b741b20bf25b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358213"
---
# <a name="best-practices-for-managing-certificates"></a>管理证书的最佳实践
本部分提供有关在中管理证书的最佳做法在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。  
  
- **进行威胁模型分析您的环境**  
  
   进行威胁模型分析 (TMA) 的你的环境以确定是否签名或加密的证书将帮助您缓解安全威胁。  
  
- **创建与合作伙伴的公钥证书计划**  
  
   创建用于发送和接收公钥证书与合作伙伴计划。 如果不使用签名证书进行参与方解析，公共证书可以附加到消息中，在这种情况下不需要证书的副本在系统中事先。  
  
- **在设置的时间间隔下载证书吊销列表**  
  
   在设置的时间间隔下载证书吊销列表 (CRL) 从证书颁发机构 (CA)。 我们建议执行此操作每周一次。 如果没有为 BizTalk server 已加入的域的 CA，将会自动下载 Crl。  
  
- **指导原则与合作伙伴建立提交公钥的**  
  
   过程与您的合作伙伴的服务级别协议 (SLA) 中，建立提交公钥，通知你证书即将过期，并吊销证书时通知您的准则。  
  
- **验证签名证书**  
  
   请确保验证签名证书对证书吊销列表。 有关如何验证签名证书的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。  
  
- **避免拒绝服务攻击的数字签名**  
  
   确定您想如何处理消息时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]无法验证数字签名。 设置**身份验证**接收端口上的属性将有助于防止拒绝服务攻击。  
  
  > [!NOTE]
  >  **身份验证-删除消息**并**身份验证-保留消息**接收端口上的标志需要正确配置参与方解析管道组件和参与方是在 BizTalk Server 中定义。 有关配置参与方解析管道组件的详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。  
  
- **创建单独的加密和未加密消息接收位置**  
  
   如果你计划从某些合作伙伴和未加密的消息从其他合作伙伴接收 MIME 加密的消息，请创建单独的加密和未加密消息的不同主机中的接收位置。 要得到仅 MIME 加密的消息，请配置**允许非 MIME 消息**解码 MIME/SMIME 管道组件中的选项**否**。  
  
- **管理证书与合作伙伴**  
  
   使证书管理属于您的合作伙伴管理实践。 当添加或删除参与方从 BizTalk Server 环境时，我们建议您添加或删除与该合作伙伴相关联的证书。  
  
- **删除主机实例前删除证书**  
  
   从 BizTalk server 中删除主机实例之前, 在其下运行的主机实例的帐户的个人存储中删除的证书。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk Server 安全性](../core/managing-biztalk-server-security.md)   
 [管理 Windows 组和用户帐户的最佳做法](../core/best-practices-for-managing-windows-groups-and-user-accounts.md)