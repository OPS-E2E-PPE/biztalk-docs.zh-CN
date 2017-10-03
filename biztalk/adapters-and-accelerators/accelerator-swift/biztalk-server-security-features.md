---
title: "BizTalk Server 安全功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication
- security, authentication
- security, BizTalk Server
- security, security features
- BizTalk Server, security features
ms.assetid: db356439-1898-4c09-86de-458a9bd21b18
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58f87bab3118f824843167a7be97d831cecc0b7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="biztalk-server-security-features"></a>BizTalk Server 安全功能
通过使用财务服务应用程序和集成解决方案开发[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]是[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]由本机保护的应用程序和是否[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全功能。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]应用程序通常由构成的消息传送功能 (消息处理转换，路由) 和工作流自动化 （业务流程自动化、 业务规则和逻辑求值）。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供常规消息传递和工作流自动化安全。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]提供了特定于保护最终用户消息项、 修复、 批准和提交的其他安全功能。 有关详细信息[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]-特定的安全，请参阅[A4SWIFT 消息修复和新提交的安全功能](../../adapters-and-accelerators/accelerator-swift/a4swift-security-features-for-message-repair-and-new-submission.md)。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]在于，围绕在其中的消息和文档，以及它们，与之交互的处理组件基于 XML 和 Web 服务消息传送事件模型 （以 MessageBox 数据库和发布服务器订阅服务器设计模式为中心） 设计技术。 为了帮助保护信息、 参与者和进程组成任何系统的完整性，下面的基本要求，请指导安全机制：  
  
-   **保护的系统组件的隐私。** 保护在打开的计算的通信的隐私和网络环境是加密的功能。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]支持的加密通过公钥基础结构 (PKI)、 安全多用途 Internet 邮件扩展 (S/MIME) 和安全套接字层 (SSL) 通信。 进行身份验证并增强保护消息的隐私[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]广为使用数字证书 （键）。  
  
     PKI 是授权的的解决方法可提高安全交换密钥、 过程和层次结构的密钥，以及针对这些目的部署的算法进行身份验证的 Internet 协议集。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 S/MIME 协议加密和解密消息发送和接收具有数据加密标准 (DES)、 3DES 和 RC2 加密算法支持多个步骤，多方的进程。 为 Web 客户端和 Web 服务器之间的加密的点到点通信[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用 SSL 协议。  
  
-   **身份验证信息、 参与者和进程。** 进行身份验证信息、 参与者和进程，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]依赖于签名证书，[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证，并扩展的实现[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]中的身份验证[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]称为企业单一登录 (SSO)。 签名证书是数字的证书 （或密钥），它们可标识在消息交换中彼此的两个参与方。 签名证书还确定是否消息已在传输过程中篡改。  
  
     [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以使用存储的公钥进行解码数字签名的传入消息，并且可以使用私钥进行签名它生成的出站消息。 SSO 是[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]扩展[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]允许方并参与多步骤的消息事件的身份验证[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]进程自身进行身份验证，在任何不步骤在过程中，在过程中，任何资源需要多个登录。  
  
-   **授权资源使用情况。** 授权是分配和对系统的资源的使用权限管理。 主[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]授权机制[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]角色，[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]身份验证，并且 MessageBox 数据库。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]为业务流程过程和业务流程将消息发送到发送管道发送它们之前在 MessageBox 其数据库中，存储所有传入和传出消息。 访问[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]数据库和资源分配给管理员、 用户，以及主机帐户使用[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]角色。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]安全体系结构基于一组可靠的实现在整个的机制[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]使用各种方法旨在提高安全性。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]合并的安全机制的组件都将发送和接收适配器、 管道、 MessageBox 数据库、 业务流程，以及消息安全上下文属性。  
  
 这些组件使用所需的身份验证管道、 多个逻辑主机和其"受信任身份验证"属性和发布和订阅/接收授权方法部署的安全机制。 此多方面的安全体系结构[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]提供许多选项用于帮助设计并执行更多安全的金融服务消息传递和工作流自动化应用程序。