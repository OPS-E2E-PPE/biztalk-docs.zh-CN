---
title: BizTalk Server 中的安全功能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, security
- Master Secret server, security
- security, Master Secret server
- security, runtime
- security, data
- deploying, security
- security, configuring
- runtime, security
- security, security features
- security, messages
- security, access control
- security, about security
- access control
- security, deploying
- data, security
- messages, security
ms.assetid: 5ab15023-fa71-439e-b3aa-420fe28806fa
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d1473ef87ccab6d035799f37a44b341e58a27a04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65279951"
---
# <a name="security-features-in-biztalk-server"></a>BizTalk Server 中安全功能
Microsoft® BizTalk® Server 提供了用于发送和接收的文档在 intranet 中或通过 Internet 的标准网关。 由于发往和来自 BizTalk Server 的消息的可能的业务关键特性，务必要考虑措施，以帮助安全，这些消息和它们同时包含因为它们是在传输中和时 BizTalk Server 进程和存储的信息它们。 本部分提供有关 BizTalk Server 安全功能，以及如何使用它们来帮助保护你的数据和环境的信息。  
  
 BizTalk Server 使用以下措施来保护入站和出站消息，来帮助保护的运行时和配置信息，并帮助安全地与其他应用程序和系统集成：  
  
 **消息安全**  
  
- 对消息的发件人进行身份验证。 BizTalk Server 能够进行身份验证 （通过证书信息或 Windows 集成的安全性） 的消息的发送方验证消息的发件人的身份。 有关详细信息，请参阅[入站消息身份验证](../core/inbound-message-authentication.md)。  
  
- 授权的消息的接收方。 BizTalk Server 接收消息后，BizTalk Server 可以确定哪些进程和用户有权接收消息。 有关详细信息，请参阅[向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md)。  
  
  **运行时和配置安全**  
  
- **访问控制和保护数据。** BizTalk Server 使用访问控制以确保 BizTalk Server 进程有适当的限制和控制访问的业务关键信息。 换而言之，BizTalk Server 确保用户和帐户具有的最低用户权限可以启用它们来执行其任务。 有关详细信息，请参阅[访问控制和数据安全性](../core/access-control-and-data-security.md)。  
  
  **集成的安全性**  
  
- 企业单一登录。 BizTalk Server 使用企业单一登录 (SSO) 以确保它对适配器，发送和接收位置的敏感配置信息进行加密要求，从而帮助确保 BizTalk Server 将存储和传输中的此信息安全的方式。 有关详细信息，请参阅[使用 SSO](../core/using-sso.md)。  
  
## <a name="see-also"></a>请参阅  
 [为 BizTalk Server 设计系统体系结构](../core/designing-the-system-architectures-for-biztalk-server.md)   
 [实现企业单一登录](../core/implementing-enterprise-single-sign-on.md)   
 [规划消息安全性](../core/planning-message-security.md)   
 [访问控制和数据安全性](../core/access-control-and-data-security.md)   
