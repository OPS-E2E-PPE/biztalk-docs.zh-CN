---
title: 授权一条消息的接收方 |Microsoft 文档
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
ms.openlocfilehash: 7317cd9c54568edd2c49df026790ee7a1e70fb2e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230741"
---
# <a name="authorizing-the-receiver-of-a-message"></a>授权一条消息的接收方
使用 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 可以对授权接收消息的流程和参与方进行限制。  
  
 下图显示了 BizTalk Server 中可用于向消息的收件人进行授权的安全功能。  
  
 ![授权消息接收方的安全功能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")  
BizTalk Server 用于对消息的收件人进行授权的安全功能。  
  
 可以使用以下安全机制来建立有权接收您发送的消息的人员：  
  
-   **解密。** 请确保将发送给 BizTalk Server 的消息具有的公钥证书用于加密消息它们向 BizTalk Server 发送方。 BizTalk Server 使用私钥证书对消息进行解密。  
  
-   **收到授权。** 可以使用此方法来控制 BizTalk Server 环境中的哪些主机能接收给定消息。  
  
-   **加密。** 通过让 BizTalk 使用来自给定参与方的公钥证书对消息进行加密，可确保只有目标参与方才能读取该消息。  
  
## <a name="receive-authorization"></a>接收授权  
 接收授权是可用于控制哪些主机能接收（订阅）给定消息的方法。 BizTalk Server 使用的证书信息，如对消息的订阅属性以匹配谓词： MessageBox 数据库将标记为具有该消息解密证书的主机所需身份验证的消息仅路由。 要说明该流程，请考虑以下情况：  
  
-   **未加密的消息路由：** 时 BizTalk Server 接收一条消息，发送方未进行加密，关于 BizTalk 将消息的路由没有解密限制。 有或者没有配置接收授权证书的主机都可以接收该消息。  
  
-   **路由加密的消息：** 当加密的消息到达时，接收管道必须包含解密消息解码组件。 当 BizTalk Server 路由解密后的消息时，BizTalk 会将用于解密该消息的证书指纹作为 MessageBox 数据库订阅机制中的证据，并且只有配置了该证书的主机才能接收该消息。  
  
 如果要使用接收授权，必须提供要向其授权接收消息的主机的属性中的解密证书指纹。 有关详细信息收到授权，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="see-also"></a>另请参阅  
 [入站的消息身份验证](../core/inbound-message-authentication.md)   
 [进程之间的消息的身份验证](../core/authentication-of-messages-between-processes.md)   
 [出站消息保护](../core/outbound-message-protection.md)   
 [对一条消息的发送方进行身份验证](../core/authenticating-the-sender-of-a-message.md)   
 [规划消息安全](../core/planning-message-security.md)