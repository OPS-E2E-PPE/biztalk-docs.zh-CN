---
title: 发送和接收消息的安全性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, receiving
- messages, sending
- messages, processing
- security, messages
- security, message processing
- messages, security
ms.assetid: 9bcd01e4-245a-4f4c-b65c-89d7cd3d1b68
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0dfaf4b02c674995c2e60c694d439281d6d632ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280431"
---
# <a name="security-for-sending-and-receiving-messages"></a>发送和接收消息的安全性
下图显示了当 BizTalk Server 接收、 处理它，并将其发送到另一个应用程序或合作伙伴，一条消息会发生什么情况。  
  
 ![安全消息的安全功能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
一条消息的整个生存期中使用的安全功能  
  
1.  该适配器的接收位置接收的消息。 根据协议，该适配器在协议级别身份验证的发件人标识表示消息的发件人的 Windows 用户帐户。  
  
2.  适配器然后将消息传递到管道，其中消息级别进行身份验证，如果不出现在适配器中。  
  
    1.  在解码阶段中，管道对消息进行解密，证书附加到消息，或从一台本地计算机其他人证书存储中配置验证签名的有效性。 管道对签名进行验证后，解码组件将验证由受信任的根证书颁发机构 (CA) 的证书链。 如果配置管道以 S/MIME 消息解码和发件人使用 S/MIME 消息进行了加密，则 MIME/SMIME 解码器签名验证的消息，并使用证书进行标识发件人。 有关如何使用 MIME/SMIME 解码器管道组件的详细信息，请参阅[实施消息安全性](../core/implementing-message-security.md)。  
  
    2.  在参与方解析阶段中，BizTalk Server 使用的证书信息和发件人安全 ID (SSID) 获取从协议级别身份验证来确定消息的发件人是否是系统中已知的参与方。 发件人 SSID 是用户的由适配器身份验证的限定的名称。 有关示例。 如果 BizTalk Server 接收的消息通过 HTTP 适配器使用 Windows 身份验证，则发件人 SSID 是域 \ 用户名。 BizTalk Server 将参与方 ID (PID) 分配给消息，这是已知的参与方的参与方 ID 或来宾 id。 有关如何使用参与方解析组件的详细信息，请参阅[使用证书进行参与方解析](../core/using-certificates-for-party-resolution.md)。  
  
    3.  如果配置的接收端口以要求发件人进行身份验证的已知参与方在系统中，并且 BizTalk Server 不能查找 PID 发送方的消息，则 BizTalk Server 将删除或挂起该消息根据的配置 接收端口。 BizTalk Server 提供此功能来规避拒绝服务攻击。 有关接收端口的身份验证选项的详细信息，请参阅[如何配置接收端口的身份验证选项](../core/how-to-configure-authentication-options-for-a-receive-port.md)。  
  
3.  管道对消息进行身份验证后，它会将消息发送到 MessageBox 数据库中。  
  
    1.  如果未作为身份验证的受信任主机标识排入队列主机 （正在其运行该管道），MessageBox 数据库将使用来宾 ID 和与作为运行排队主机实例服务帐户的 SSID 覆盖 PID。 有关受信任验证主机的详细信息，请参阅[身份验证的消息之间进程](../core/authentication-of-messages-between-processes.md)。 有关如何配置受信任的验证主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
    2.  如果在其运行管道的主机标记为受信任的身份验证，MessageBox 数据库信任该 PID 和 SSID，并保持消息的上下文中的此信息，以便下游进程可以使用此信息进行身份验证和/或授权消息原始发件的人。  
  
    3.  如果 BizTalk Server 需要接收授权，MessageBox 数据库将验证订阅该消息的主机能够接收它的授权。 有关详细信息接收授权，请参阅[向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md)。  
  
4.  BizTalk Server 处理消息后，出站管道了加密和/或数字对消息进行签名将在编码阶段。  
  
## <a name="see-also"></a>请参阅  
 [实现消息安全性](../core/implementing-message-security.md)   
 [规划消息安全性](../core/planning-message-security.md)