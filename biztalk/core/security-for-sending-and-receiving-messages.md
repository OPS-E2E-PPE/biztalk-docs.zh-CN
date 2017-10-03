---
title: "用于发送和接收消息的安全 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1328eb98cbf94b85cda16eda431da197c6d0126
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="security-for-sending-and-receiving-messages"></a>发送和接收消息过程中的安全性
下图显示了 BizTalk Server 接收、处理消息以及将消息发送到另一个应用程序或合作伙伴时，对消息执行的操作。  
  
 ![安全消息的安全功能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
消息生存期中使用的安全功能  
  
1.  适配器的接收位置接收消息。 根据协议的具体情况，适配器在协议级别对发件人进行验证，以标识表示消息发件人的 Windows 用户帐户。  
  
2.  然后适配器将消息传递到管道，如果在适配器中还没有执行消息级别的验证，则此时在管道中执行该验证。  
  
    1.  在解码阶段，管道将对消息进行解密，然后使用消息附带的证书或者本地计算机的“其他人”证书存储中配置的证书，来验证签名的有效性。 管道对签名进行验证后，解码组件将对证书链进行验证，直至到达受信任根证书颁发机构 (CA)。 如果将管道配置为对 S/MIME 消息进行解码，并且发件人使用 S/MIME 对消息进行了加密，则 MIME/SMIME 解码器将验证消息的签名，然后使用证书识别发件人。 有关如何使用 MIME/SMIME 解码器管道组件的详细信息，请参阅[实现消息安全](../core/implementing-message-security.md)。  
  
    2.  在参与方解析阶段，BizTalk Server 将使用从协议级别验证获取的证书信息和发件人安全 ID (SSID) 来确定消息的发件人是否是系统中已知的参与方。 发件人 SSID 是由适配器验证的用户限定名。 例如， 如果 BizTalk Server 通过 HTTP 适配器使用 Windows 验证接收消息，则发件人 SSID 为“域\用户名”格式。 BizTalk Server 将方 ID (PID) 分配给消息，这是识别方，当事方 ID 或来宾 id。 有关如何使用方解析组件的详细信息，请参阅[使用证书的参与方解析](../core/using-certificates-for-party-resolution.md)。  
  
    3.  如果将接收端口配置为要求验证发件人是系统中的已知参与方，而 BizTalk Server 找不到消息发件人的 PID，则 BizTalk Server 会根据接收端口的配置丢弃或挂起该消息。 BizTalk Server 提供此功能来规避拒绝服务攻击的威胁。 接收端口的身份验证选项有关的详细信息，请参阅[如何将身份验证选项配置为接收端口](../core/how-to-configure-authentication-options-for-a-receive-port.md)。  
  
3.  管道对消息进行验证后，会将该消息发送到 MessageBox 数据库。  
  
    1.  如果排队的主机（运行管道的主机）未标识为受信任验证主机，则 MessageBox 数据库将用来宾 ID 覆盖 PID，用运行排队主机实例的服务帐户覆盖 SSID。 有关身份验证信任的主机的详细信息，请参阅[身份验证的消息之间进程](../core/authentication-of-messages-between-processes.md)。 有关如何配置身份验证信任的主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
    2.  如果运行管道的主机标记为受信任验证，则 MessageBox 数据库信任该 PID 和 SSID，并将此信息留在消息的上下文中，以便下游流程能使用此信息对消息的原始发件人进行验证和/或授权。  
  
    3.  如果 BizTalk Server 需要接收授权，则 MessageBox 数据库将验证订阅消息的主机有接收该消息的授权。 有关详细信息收到授权，请参阅[授权一条消息的接收方](../core/authorizing-the-receiver-of-a-message.md)。  
  
4.  BizTalk Server 对消息进行处理后，出站管道将在编码阶段对消息进行加密和/或数字签名。  
  
## <a name="see-also"></a>另请参阅  
 [实现消息安全性](../core/implementing-message-security.md)   
 [规划消息安全](../core/planning-message-security.md)