---
title: 入站消息身份验证 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, authenticating
- processing, inbound messages
- messages, inbound
- processing, security
- security, messages
- inbound messages
ms.assetid: 34c06283-667d-4498-8544-dea6e87f276f
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49ada514c771f4e6dbf0abad3f23cab54721299d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22258061"
---
# <a name="inbound-message-authentication"></a>入站的消息身份验证
为了验证消息发件人的身份，BizTalk Server 可以使用证书信息或 Windows 集成安全性对消息的发件人进行验证。 下图显示了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中可用于验证入站消息的安全功能。  
  
 ![安全功能进行身份验证的入站的消息](../core/media/ebiz-plan-secoverview-auth-inbound.gif "ebiz_plan_secoverview_auth_inbound")  
BizTalk Server 用于验证入站消息的安全功能。  
  
 BizTalk Server 收到加密的签名消息时，它会执行以下步骤以确保识别出发送消息的参与方。  
  
1.  当消息到达 BizTalk Server 接收位置时，接收处理程序会试图获取来自发送流程的发件人 Windows 安全 ID (SSID)。 签名消息通过监听程序的验证后，接收位置会将该 SSID 往下游传递。 如果通过 BizTalk 消息队列或 HTTP 适配器等可获取客户端证书信息，则 BizTalk Server 接收位置可获取该证书信息，然后沿着接收管道传递该证书消息以用于参与方解析。 如果接收处理程序无法获取 SSID，则此字段留空。  
  
     接收处理程序将消息发送到接收管道，在接收管道中将会解密消息、验证数字签名，如果该接收管道含有参与方解析组件，还会进行参与方解析。 如果发件人对传入消息使用了签名证书，则 MIME/SMIME 解码器组件会覆盖从适配器获取的任何证书信息。  
  
2.  如果发件人对消息进行了加密，则 MIME/SMIME 解码器会从主机实例服务帐户的个人证书存储中检索解密证书，然后使用私钥对消息进行解密。  
  
     如果发件人对消息进行了签名，则 MIME/SMIME 解码器会验证该数字签名，它先验证负载哈希以确定签名是否被篡改，然后从证书存储中检索证书来验证该签名。 如果消息本身就包含签名人的公钥，则 MIME/SMIME 解码器不会从证书存储中检索证书，而使用消息中提供的公钥。  
  
3.  通常管道中的最后一个处理步骤是参与方解析。 使用 BizTalk 浏览器或 BizTalk Server 管理控制台，可以创建参与方、将参与方映射到签名证书或创建参与方别名。 在 BizTalk 浏览器中定义的所有参与方都有一个唯一的参与方标识符 (PID)。 BizTalk Server 获取该 PID，然后将它放在消息上下文中。 BizTalk 使用以下方法之一获取 PID：  
  
    1.  当发件人对消息进行了签名或者接收处理程序无法获取客户端证书，并且您选择了使用证书来解析参与方的选项时，BizTalk 会使用相应的签名或客户端证书来查找 PID。 开始接收参与方的消息之前，必须在属性中配置参与方及其证书。 有关详细信息如何配置当事方，请参阅[使用证书的参与方解析](../core/using-certificates-for-party-resolution.md)。  
  
    2.  当发件人没有对消息使用签名证书，并且您选择了使用发件人的安全 ID (SSID) 来解析参与方的选项时，参与方解析组件会使用 SSID 来查找 PID。 开始接收参与方的消息之前，必须将参与方配置为使用 SSID 作为别名。 有关方解析组件的详细信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。  
  
        > [!NOTE]
        >  BizTalk Server 定义参与方的别名时，使用的是帐户名而不是实际的 Windows SID。  
  
    3.  如果无法解析参与方，则管道会将 PID 设为“来宾”。  
  
4.  当接收端口标记为“要求验证”，并且 BizTalk Server 获取了有效 PID 并将其解析为已知参与方时，消息会被排入 MessageBox 数据库的队列。 当 SSID 为空或者 PID 是来宾 ID 时，BizTalk Server 将丢弃消息或者将消息发送到挂起的队列中（具体情况取决于“要求验证”属性的配置）。 使用“要求验证”属性可以尽量减小从未知参与方接收大量消息的负面影响。 接收端口的身份验证选项有关的详细信息，请参阅[如何将身份验证选项配置为接收端口](../core/how-to-configure-authentication-options-for-a-receive-port.md)。  
  
## <a name="see-also"></a>另请参阅  
 [进程之间的消息的身份验证](../core/authentication-of-messages-between-processes.md)   
 [出站消息保护](../core/outbound-message-protection.md)   
 [对一条消息的发送方进行身份验证](../core/authenticating-the-sender-of-a-message.md)   
 [授权一条消息的接收方](../core/authorizing-the-receiver-of-a-message.md)   
 [如何将 BizTalk Server 配置为接收注册消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)