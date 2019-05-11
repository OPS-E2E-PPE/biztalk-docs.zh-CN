---
title: 进程间的消息身份验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PID
- security, warnings
- processing, messages
- processing, security
- messages, processing
- security, messages
- MessageBox database, authenticating
- SSID
- authenticating, warnings
ms.assetid: fa746ee3-fc22-4e63-a5cc-8bc0cbeb536b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0491946d3e8398fa56914b9f9ff4aaa89edb9228
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358766"
---
# <a name="authentication-of-messages-between-processes"></a>进程间的消息身份验证
下图显示了 BizTalk Server，可用于不同的 BizTalk 主机之间验证消息中的安全功能。  
  
 ![验证消息的安全功能](../core/media/ebiz-plan-secoverview-auth-process.gif "ebiz_plan_secoverview_auth_process")  
BizTalk Server 的安全功能使用进程之间验证消息。  
  
 BizTalk Server 接收消息、 解密和验证消息，并具有有效的参与方 ID (PID) 和证书确定该消息的发件人后，MessageBox 数据库就可以以验证订阅该消息匹配，并发送此到其他主机进行进一步处理的消息。  
  
 当消息从一个进程流到另一个，它通常是需要将消息的原始发件人的标识传递给授权、 参与方解析和发件人相关的业务逻辑的下游进程。 但是，若要传递此信息而无需某种类型的安全措施或信任机制在所有主机将极大地增加需验证所有用户对象和代码 (例如，业务流程、 适配器、 管道组件和 functoid) 是可信任.  
  
 若要提供区分用户对象和代码的信任级别的方法，BizTalk Server 作为主机的一个属性提供身份验证信任。 MessageBox 数据库从尚未设置为受信任验证主机收到一条消息，MessageBox 数据库将用来宾 ID 覆盖 PID，并使用作为运行主机实例的服务帐户覆盖 SSID。 在主机标记为受信任的身份验证，BizTalk 允许该主机指定任何发件人 SID (SSID) 和消息在排队进入 MessageBox 数据库参与方 ID (PID)。  
  
 通过指定哪些主机可信，哪些不能，可以定义用户对象和代码可信或不受信任的安全边界。 也就是说，用户对象和代码部署到已设置为身份验证受信任的主机需要用户对象和代码部署到未设置为受信任验证主机比更值得信任。 有关如何配置受信任的验证主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。  
  
 在 MessageBox 数据库接收一条消息，BizTalk Server 将采取以下步骤以强制实施将消息发送到 MessageBox 数据库的主机实例的受信任验证：  
  
1.  MessageBox 数据库首先确定发送该消息的主机是否已设置为检查 SSID 受信任的主机的主机实例服务帐户的受信任验证。  
  
2.  如果主机的是将消息发送到 MessageBox 数据库是受信任验证，MessageBox 数据库将保留在"按原样，"的消息上下文的 SSID 和 PID 除非它们为空。 如果 SSID 为空，MessageBox 数据库使用填充它调用的过程中，也称为主机 SID (HSID）) 的 SID。 如果 PID 为空，将其设为来宾 id。  
  
3.  如果使用 HSID 和 PID 填充发送到 MessageBox 数据库邮件尚未设置为受信任，验证 SSID 的主机而不考虑是否已填充这些字段已设置为 Guest。  
  
> [!IMPORTANT]
>  如果你想要知道的 SSID 和 PID 的消息的原始发件人的下游进程，则必须设置为受信任验证传递的消息的所有主机。 此外，在情况下如上时接收到消息，将其随后用于构造在业务流程中的出站消息，接收的 SSID 和 PID 的入站的消息必须显式添加为属性才能继续传递这些出站消息标识。  
  
> [!IMPORTANT]
>  如果配置为受信任验证运行管道的主机，BizTalk Server 会认为该管道是受信任的环境。 因此，它是非常重要的是受信任验证主机正在运行的 BizTalk 管道中包含任何自定义组件也是受信任验证。  
  
> [!NOTE]
>  受信任验证主机和不受信任验证主机，不能使用相同的服务帐户。  
  
## <a name="see-also"></a>请参阅  
 [入站的消息身份验证](../core/inbound-message-authentication.md)   
 [出站消息保护](../core/outbound-message-protection.md)   
 [对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md)   
 [向消息收件人授权](../core/authorizing-the-receiver-of-a-message.md)