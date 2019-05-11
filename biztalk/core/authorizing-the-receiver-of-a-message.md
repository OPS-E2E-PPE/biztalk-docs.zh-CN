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
ms.openlocfilehash: 3ca2b0b6474421bc474cf30ae8c8817bc5f8e10d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358753"
---
# <a name="authorizing-the-receiver-of-a-message"></a>向消息收件人授权
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使您能够限制流程和授权接收消息的参与方。  
  
 下图显示了 BizTalk Server 中可使用一条消息的收件人进行授权的安全功能。  
  
 ![向消息收件人授权的安全功能](../core/media/ebiz-plan-secoverview-authz.gif "ebiz_plan_secoverview_authz")  
BizTalk Server 的安全功能使用消息的收件人进行授权。  
  
 可以使用以下安全机制来建立哪些人拥有权限 （授权） 以接收您发送的消息：  
  
-   **解密。** 请确保发送到 BizTalk Server 消息具有的公钥证书用于加密消息他们将发送到 BizTalk Server 参与方。 BizTalk Server 使用私钥证书对消息进行解密。  
  
-   **接收授权。** 可以使用此方法来控制在 BizTalk Server 环境中的哪些主机能接收给定的消息。  
  
-   **加密。** 通过使用来自给定参与方的公钥证书时 BizTalk 对消息进行加密，可以确保只有预期的参与方是能够读取该消息。  
  
## <a name="receive-authorization"></a>接收授权  
 接收授权是方法，可以使用来控制哪些主机能接收 （订阅） 给定的消息。 BizTalk Server 使用的证书信息，如订阅属性，以匹配消息谓词： MessageBox 数据库仅将标记为具有该消息的解密证书的主机，为所需身份验证的消息路由。 若要说明该过程，请考虑以下方案：  
  
- **路由未加密的消息：** 在 BizTalk Server 接收一条消息，发送方未进行加密，没有任何解密限制 BizTalk 如何路由消息。 使用的主机和主机，而无需接收授权配置的证书可以接收该消息。  
  
- **路由加密的消息：** 当加密的消息到达时，接收管道必须含有对消息进行解密的解码组件。 当 BizTalk Server 将消息路由后被解密，只有配置了该证书的主机接收和 BizTalk 使用用来作为证据在 MessageBox 数据库订阅机制中，对消息进行解密的证书指纹消息。  
  
  如果想要使用接收授权，则必须提供你想要授权接收消息的主机的属性中的解密证书的指纹。 有关详细信息接收授权，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
## <a name="see-also"></a>请参阅  
 [入站的消息身份验证](../core/inbound-message-authentication.md)   
 [进程间的消息身份验证](../core/authentication-of-messages-between-processes.md)   
 [出站消息保护](../core/outbound-message-protection.md)   
 [对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md)   
 [规划消息安全性](../core/planning-message-security.md)