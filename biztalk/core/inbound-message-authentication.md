---
title: 入站消息身份验证 |Microsoft Docs
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
ms.openlocfilehash: d3b9a7812b7466145a0861112948633dae8442a0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65332102"
---
# <a name="inbound-message-authentication"></a>入站的消息身份验证
BizTalk Server 能够进行身份验证 （通过证书信息或 Windows 集成的安全性） 的消息的发送方验证消息的发件人的身份。 下图显示了中的安全功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可用于验证入站的消息。  
  
 ![入站的消息进行身份验证的安全功能](../core/media/ebiz-plan-secoverview-auth-inbound.gif "ebiz_plan_secoverview_auth_inbound")  
BizTalk Server 的安全功能使用入站的消息进行身份验证。  
  
 当 BizTalk Server 接收加密和签名消息时，需要以下步骤以确保发送方被识别。  
  
1.  当消息到达 BizTalk Server 接收位置时，接收处理程序将尝试获取来自发送流程的发件人 Windows 安全 ID (SSID)。 接收位置将该 ssid 往下游传递，以支持其中侦听器具有已通过身份验证已签名的消息的情况。 如果客户端证书可获得的信息 （例如通过 BizTalk 消息队列或 HTTP 适配器），BizTalk Server 接收位置可以获取该证书的信息并将其传递进行更高版本上在接收管道中的参与方解析. 如果接收处理程序无法获取 SSID，此字段留空。  
  
     接收处理程序将消息发送到接收管道，其中对消息进行解密、 数字签名进行验证，并参与方解析管道是否参与方解析组件，则会发生。 如果发件人对传入消息使用签名证书，则 MIME/SMIME 解码器组件将覆盖从适配器获取的任何证书信息。  
  
2.  如果发件人加密消息，则 MIME/SMIME 解码器从主机实例服务帐户的个人证书存储中检索的解密证书，并使用私钥对消息进行解密。  
  
     如果发件人对消息进行了签名，则 MIME/SMIME 解码器进行身份验证的数字签名验证篡改、，然后从证书存储检索证书的签名来验证签名的有效负载哈希值。 如果签名者的公钥是消息本身，则 MIME/SMIME 解码器不会从证书存储检索证书，但使用消息中提供的公共密钥。  
  
3.  通常情况下，管道中的最后一个处理步骤是参与方解析。 使用 BizTalk 浏览器或 BizTalk Server 管理控制台中，可以创建参与方、 将参与方映射到一个签名证书，或创建参与方别名。 在 BizTalk 浏览器中定义的所有参与方具有唯一的参与方标识符 (PID)。 BizTalk Server 获取该 PID，并将其放在消息上下文中。 BizTalk 通过以下方法之一获取 PID:  
  
    1.  如果发件人签名消息，或者如果接收处理程序无法获取客户端证书，并选择选项以使用证书解析参与方，BizTalk 会使用相应的签名或查找到的客户端证书PID。 在开始接收消息之前，必须配置与证书作为属性的参与方。 有关详细信息配置参与方，请参阅[使用证书进行参与方解析](../core/using-certificates-for-party-resolution.md)。  
  
    2.  如果发件人未在消息中，使用签名证书，选择选项使用发件人的安全 ID (SSID) 来解析参与方的参与方解析组件会使用 SSID 来查找 PID。 必须配置为使用 SSID 作为别名之前开始接收消息, 的参与方。 有关参与方解析组件的详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。  
  
        > [!NOTE]
        >  定义参与方别名时，BizTalk Server 使用的帐户名而不是实际的 Windows SID。  
  
    3.  如果无法解析的参与方，管道会将 PID 设置为来宾。  
  
4.  如果接收端口标记为必需的身份验证，并 BizTalk Server 获取了有效 PID 并将其解析的已知参与方时，将该消息会然后排队到 MessageBox 数据库。 如果 SSID 为空或者 PID 是来宾 ID，BizTalk Server 将丢弃该消息，或将其发送到挂起队列 （具体取决于你的配置所需的身份验证属性）。 作为一种方法从未知参与方接收大量消息的负面影响降至最低，可以使用所需的身份验证属性。 有关接收端口的身份验证选项的详细信息，请参阅[如何配置接收端口的身份验证选项](../core/how-to-configure-authentication-options-for-a-receive-port.md)。  
  
## <a name="see-also"></a>请参阅  
 [进程间的消息身份验证](../core/authentication-of-messages-between-processes.md)   
 [出站消息保护](../core/outbound-message-protection.md)   
 [对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md)   
 [向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md)   
 [如何配置 BizTalk Server 以便接收签名消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)   
 [BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md)