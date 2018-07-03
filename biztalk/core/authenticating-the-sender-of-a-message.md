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
ms.openlocfilehash: 52b0e69a2799bf5b119093e4ac82773014e979b1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019083"
---
# <a name="authenticating-the-sender-of-a-message"></a>对消息的发件人进行身份验证
Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用不同的机制来验证参与方和流程的真实性。 此外，您可以指定流程是否向 BizTalk Server 通知消息的原始发件人，也可指定 BizTalk Server 是否将参与方识别为合作伙伴。  
  
 下图显示了 BizTalk Server 中可用于对消息的发件人进行验证和授权的安全功能。  
  
 ![安全消息的安全功能](../core/media/ebiz-plan-secoverview.gif "ebiz_plan_secoverview")  
BizTalk Server 用于对消息的发件人进行验证和授权的安全功能  
  
 可用于对消息的发件人进行验证的功能包括：  
  
- **数字签名验证。** 如果消息带有数字签名，则 BizTalk Server 会使用该签名验证发件人的身份。 有关如何配置数字签名验证的详细信息，请参阅[如何配置为接收签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。  
  
- **参与方解析。** MessageBox 数据库中的所有消息（无论是从 BizTalk Server 内部还是外部发起）都包含一个参与方 ID (PID)，它是通过数字证书或 Windows 帐户与 PID 之间的映射来确定的。 有关如何配置参与方解析组件的详细信息，请参阅[使用证书进行参与方解析](../core/using-certificates-for-party-resolution.md)。  
  
- **所需的身份验证。** 如果接收端口无法确定消息的发件人，则 BizTalk 主机可以将该消息作为“来宾”消息接受，或者完全忽略该消息。 使用此功能可以使来自未知参与方的消息不被处理或存储在跟踪数据库中，因此能够防止您的系统遭到拒绝服务攻击。 有关接收端口的身份验证选项的详细信息，请参阅[如何配置接收端口的身份验证选项](../core/how-to-configure-authentication-options-for-a-receive-port.md)。  
  
- **受信任验证。** 如果 MessageBox 数据库接收到来自未标识为受信任验证的主机的消息，则 MessageBox 数据库将用来宾 ID 覆盖 PID，用运行该主机实例的服务帐户覆盖 SSID。 BizTalk Server 将主机标识为受信任验证来表明受信任主机排队到 MessageBox 数据库的消息的发件人是一个实体而不是受信任主机本身。 受信任验证的主要目的在于使管道能够解析出 PID，然后将该 PID 传递给授权和出站参与方解析中使用的服务，以及将发件人的 Windows 安全 ID (SSID) 传输到业务流程操作授权中使用的服务。 有关受信任验证主机的详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。 有关如何使用 BizTalk Server 业务流程与参与方解析结合使用的详细信息，请参阅[PartyResolution （BizTalk Server 示例）](../core/partyresolution-biztalk-server-sample.md)。  
  
  根据是否需要知道是谁向您发送了此消息（即消息的原始发件人），或者消息的收件人或查看人，可以使用图中显示的部分或所有功能。  
  
  如果对于合作伙伴来说，有必要了解消息确实来自您处并且在传输过程中其他任何人都无法阅读这些消息，则应考虑采用以下技术来确保只有指定的收件人和收件人应用程序才能够接收这些消息：  
  
- 在出站消息中使用数字签名，以便您的合作伙伴能够验证您就是消息的发件人。  
  
- 对出站消息进行加密，以确保在传输消息时未经授权的参与方无法查看该消息。  
  
  如果有必要确定向您公司发送消息的发件人，并确定在消息发送过程中其他任何人都未阅读该消息，则应考虑采用以下技术来确保只有指定的收件人和收件人应用程序才能够接收这些消息：  
  
- 请确保 BizTalk Server 只接受带有数字签名的消息，以便了解是谁发送的消息。  
  
- 请确保向您的合作伙伴发送公钥证书，该证书用于对发送给 BizTalk Server 的消息进行加密。 通过使用加密，可以确保在传输消息时未经授权的参与方无法查看该消息。  
  
- 在接收端口中使用“要求验证”属性以确保消息来自已知参与方。  
  
  多个主机对消息进行处理后，可能弄不清楚消息的原始发件人是谁。 在必须知道的标识的原始发件人，例如，授予访问权限来发送或接收消息时的情况下[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供了一种安全机制来验证传播通过多个主机的原始发件人标识对下游主机基于该标识访问权限。 在 BizTalk Server 中，这种安全机制称为流程受信任验证。 有关详细信息，请参阅[身份验证的消息之间进程](../core/authentication-of-messages-between-processes.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [入站消息认证](../core/inbound-message-authentication.md)  
  
-   [进程间的消息验证](../core/authentication-of-messages-between-processes.md)  
  
-   [出站消息保护](../core/outbound-message-protection.md)