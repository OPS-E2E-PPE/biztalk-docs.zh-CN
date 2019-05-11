---
title: 对消息的发件人进行身份验证 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- parties, authenticating
- authenticating, authentication required
- messages, authenticating
- security, authenticating
- digital signatures, authenticating
- security, messages
- MessageBox database, authenticating
- authenticating, authentication trust
- messages, message flow
- authenticating, security
- authenticating, party resolution
- authenticating, digital signatures
- authenticating, messages
ms.assetid: 813a2fb9-0346-4129-9cc5-1713f72a491e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6e0f5a4cb539581102fdc599130fdf82819b425d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358775"
---
# <a name="authenticating-the-sender-of-a-message"></a>对消息的发件人进行身份验证
Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用不同的机制来验证参与方是用户身份，或流程的真实性进行。 此外，您可以指定是否过程可以将中继到 BizTalk Server 消息的原始发件人是，谁和 BizTalk Server 是否识别为合作伙伴的参与方。  
  
 下图显示了可用于进行身份验证和授权的一条消息发件人的 BizTalk Server 中的安全功能。  
  
 ![安全消息的安全功能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
BizTalk Server 用于进行身份验证和授权的发送消息的安全功能  
  
 使您能够进行身份验证消息的发件人的功能包括：  
  
- **数字签名验证。** 如果消息具有数字签名，BizTalk Server 将使用它来验证发件人的身份。 有关如何配置数字签名验证的详细信息，请参阅[如何配置为接收签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。  
  
- **参与方解析。** 插入到 MessageBox 数据库中，是否内部还是外部 BizTalk Server 中，发起的所有消息都执行参与方 ID (PID) 通过数字签名功能的映射或 Windows 帐户与 PID 确定的。 有关如何配置参与方解析组件的详细信息，请参阅[使用证书进行参与方解析](../core/using-certificates-for-party-resolution.md)。  
  
- **所需的身份验证。** 如果接收端口不能以确定消息的发件人，可以接受它作为"来宾"消息，或完全忽略该 BizTalk 主机。 此功能，可保护你的系统免受拒绝服务攻击，如来自未知参与方的消息不会处理或存储在跟踪数据库中。 有关接收端口的身份验证选项的详细信息，请参阅[如何配置接收端口的身份验证选项](../core/how-to-configure-authentication-options-for-a-receive-port.md)。  
  
- **受信任验证。** 如果 MessageBox 数据库接收来自未标识为受信任验证主机的一条消息，MessageBox 数据库将用来宾 ID，并使用作为运行主机实例的服务帐户的 SSID 覆盖 PID。 BizTalk Server 将主机标识为受信任验证来指示，受信任的主机排队到 MessageBox 数据库的消息的发件人是一个实体而不受信任主机本身。 受信任验证的主要目的是将管道解析出 PID，并将传递到使用 PID 服务以用于授权和出站参与方解析，并沿启用发件人 Windows 安全 ID (SSID) 传输为使用在业务流程操作授权中使用的服务。 有关受信任验证主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。 有关如何使用 BizTalk Server 业务流程与参与方解析结合使用的详细信息，请参阅[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。  
  
  根据您是否需要知道谁向您发送此消息，消息或接收方或你的消息，查看器的原始发件人可以使用部分或全部在图中所示的功能。  
  
  如果对于合作伙伴了解消息确实来自您和，任何其他人都可以读取它们而在传输过程中重要，应考虑使用以下方法来帮助确保只有指定的收件人和收件人应用程序接收的消息：  
  
- 对于出站消息使用数字签名，以便你的合作伙伴可以验证您的消息的发件人。  
  
- 对出站消息，可帮助确保在传输过程中时，未授权的方无法查看该消息进行加密。  
  
  如果务必要确定谁将消息发送你的公司和任何其他人都读取它在传输过程中时，应考虑使用以下方法来帮助确保只有指定的收件人和收件人应用程序接收的消息：  
  
- 请确保 BizTalk Server 仅接受的消息的数字签名，以便您知道谁发送的消息。  
  
- 请确保将你的合作伙伴发送公钥证书以加密消息他们将发送到 BizTalk Server。 通过使用加密，可以帮助确保在传输过程中时，未授权的方无法查看该消息。  
  
- 使用身份验证所需属性中以确保消息的接收端口是来自已知参与方。  
  
  多个主机处理该消息后，可能不会清除消息的原始发件人是谁。 在必须知道的标识的原始发件人，例如，授予访问权限来发送或接收消息时的情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供了一种安全机制来验证传播通过多个主机的原始发件人标识对下游主机基于该标识访问权限。 在 BizTalk Server 中，这将调用进程身份验证信任。 有关详细信息，请参阅[身份验证的消息之间进程](../core/authentication-of-messages-between-processes.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [入站消息认证](../core/inbound-message-authentication.md)  
  
-   [进程间的消息验证](../core/authentication-of-messages-between-processes.md)  
  
-   [出站消息保护](../core/outbound-message-protection.md)