---
title: 向消息收件人授权 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, messages
- messages, receive authorization
- receive authorization
- messages, security
ms.assetid: c0cdb3ef-ee8e-40a1-9362-13cd26495951
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 612aa7cfca75e34248a094113258fc3c261ef14e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997230"
---
# <a name="authorizing-the-receiver-of-a-message"></a>向消息收件人授权
使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以对授权接收消息的流程和参与方进行限制。  
  
 下图显示了 BizTalk Server 中可用于向消息的收件人进行授权的安全功能。  
  
 ![向消息收件人授权的安全功能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")  
BizTalk Server 用于对消息的收件人进行授权的安全功能。  
  
 可以使用以下安全机制来建立有权接收您发送的消息的人员：  
  
-   **解密。** 请确保发送到 BizTalk Server 消息具有的公钥证书用于加密消息他们将发送到 BizTalk Server 参与方。 BizTalk Server 使用私钥证书对消息进行解密。  
  
-   **接收授权。** 可以使用此方法来控制 BizTalk Server 环境中的哪些主机能接收给定消息。  
  
-   **加密。** 通过让 BizTalk 使用来自给定参与方的公钥证书对消息进行加密，可确保只有目标参与方才能读取该消息。  
  
## <a name="receive-authorization"></a>接收授权  
 接收授权是可用于控制哪些主机能接收（订阅）给定消息的方法。 BizTalk Server 使用的证书信息，如订阅属性，以匹配消息谓词： MessageBox 数据库仅将标记为具有该消息的解密证书的主机，为所需身份验证的消息路由。 要说明该流程，请考虑以下情况：  
  
- **路由未加密的消息：** 时 BizTalk Server 收到一条消息，发送方未进行加密时，没有任何解密限制 BizTalk 如何路由消息。 有或者没有配置接收授权证书的主机都可以接收该消息。  
  
- **路由加密的消息：** 时收到加密的消息，接收管道必须含有对消息进行解密的解码组件。 当 BizTalk Server 路由解密后的消息时，BizTalk 会将用于解密该消息的证书指纹作为 MessageBox 数据库订阅机制中的证据，并且只有配置了该证书的主机才能接收该消息。  
  
  如果要使用接收授权，必须提供要向其授权接收消息的主机的属性中的解密证书指纹。 有关详细信息接收授权，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [入站的消息身份验证](../core/inbound-message-authentication.md)   
 [进程间的消息身份验证](../core/authentication-of-messages-between-processes.md)   
 [出站消息保护](../core/outbound-message-protection.md)   
 [对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md)   
 [规划消息安全性](../core/planning-message-security.md)