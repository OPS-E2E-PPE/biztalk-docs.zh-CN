---
title: BizTalk Server 安全功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- authentication
- security, authentication
- security, BizTalk Server
- security, security features
- BizTalk Server, security features
ms.assetid: db356439-1898-4c09-86de-458a9bd21b18
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 45d541138d566eb6791385cdb23413187d2e68ba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971126"
---
# <a name="biztalk-server-security-features"></a>BizTalk Server 安全功能
通过使用财务服务应用程序和集成解决方案的开发[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]都[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]由本机保护的应用程序和是否[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全功能。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 应用程序通常由构成的消息传送功能 (消息处理、 转换、 路由) 和工作流自动化 （业务流程自动化、 业务规则和逻辑求值）。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 提供常规消息传送和工作流自动化安全性。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] 提供特定于保护最终用户消息项、 修复、 批准和提交的其他安全功能。 有关详细信息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]-特定的安全，请参阅[A4SWIFT 安全功能，用于消息修复和新提交](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 被针对在其消息和文档，以及与其交互，处理组件均基于 XML 和 Web 服务的消息传送事件模型 （以 MessageBox 数据库和发布程序-订阅设计模式为中心）技术。 若要保护的信息、 参与者和进程组成任何系统的完整性，下面的基本要求指导安全机制：  
  
- **保护隐私的系统元素。** 保护隐私的通信中一打开的计算和网络环境的加密函数。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 支持的加密通过公钥基础结构 (PKI)、 安全多用途 Internet 邮件扩展 (S/MIME) 和安全套接字层 (SSL) 通信。 若要进行身份验证和增强保护隐私的消息，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]广泛使用的数字证书 （键）。  
  
   PKI 是解决升级安全交换密钥、 过程和颁发机构进行身份验证密钥，以及针对这些目的部署的算法的层次结构的方法的 Internet 协议的组。  
  
   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 使用 S/MIME 协议发送和接收多个步骤，多方的进程中，数据加密标准 (DES)、 3DES 和 RC2 加密算法支持的消息进行加密和解密。 Web 客户端和 Web 服务器之间的加密的点对点通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 SSL 协议。  
  
- **进行身份验证信息、 参与者和进程。** 进行身份验证信息、 参与者和流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]依赖于签名证书时，[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证和扩展的实现[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]中的身份验证[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]称为企业单一单一登录 (SSO)。 签名证书是数字证书 （或密钥），用于标识消息传送 exchange 中对每个其他的两个参与方。 签名证书还确定是否消息已在传输过程中篡改。  
  
   [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 可以使用存储的公钥进行解码传入消息进行数字签名，并且可以使用私钥生成的出站消息进行签名。 SSO 是[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]扩展[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证允许的参与方和参与多个步骤的消息事件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]进程自身进行身份验证，在任何不带步骤在过程中，在过程中，任何资源需要多个登录。  
  
- **授权资源使用情况。** 授权是分配和管理系统的资源的使用权限。 在主[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]授权机制[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]角色，[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证，并且 MessageBox 数据库。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 将所有传入和传出消息在其 MessageBox 数据库中，存储之前将它们发送到业务流程和业务流程将消息发送到发送管道。 访问权限[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]数据库和资源分配给管理员、 用户、 和主机帐户使用[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]角色。  
  
  [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全体系结构基于一组可靠的机制，实现在整个[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用各种方法旨在提高安全性。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]合并的安全机制的组件都将发送和接收适配器、 管道、 MessageBox 数据库、 业务流程和消息安全上下文属性。  
  
  这些组件使用所需的身份验证管道、 多个逻辑主机和它们"受信任验证"的属性，并发布和订阅/接收授权方法来部署的安全机制。 多方面的安全体系结构的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供大量选项帮助，设计和执行的详细信息安全的金融服务消息传送和工作流自动化应用程序。