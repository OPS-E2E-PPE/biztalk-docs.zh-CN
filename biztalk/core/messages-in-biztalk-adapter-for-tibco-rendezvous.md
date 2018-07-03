---
title: TIBCO Rendezvous 适配器中的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 12699550-22e7-4a11-a024-2302570970af
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d916b51e57d05fade93c4efc32eb4f6d544f2c94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005078"
---
# <a name="messages-in-biztalk-adapter-for-tibco-rendezvous"></a>TIBCO Rendezvous 的 BizTalk 适配器中的消息
用于 TIBCO Rendezvous 的 BizTalk 适配器提供了 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和 TIBCO Rendezvous 之间的双向连接。 此适配器同时使用 TIBCO Rendezvous API 和 BizTalk 适配器框架 API 来提供紧密集成。  
  
## <a name="about-tibco-rendezvous"></a>有关 TIBCO Rendezvous  
 TIBCO Rendezvous 是为企业应用程序集成 (EAI) 提供消息总线的程序。 TIBCO 在 C、C++、Java、Visual Basic 中提供了消息传送 API，并为 Microsoft .NET Framework 提供了用于接收 Microsoft Office Excel 工作表及其他所选应用程序上的数据馈送的消息传送 API。 有关详细信息，请参阅[TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)。  
  
## <a name="message-passing"></a>消息传递  
 消息传递的基本概念相当简单：  
  
- 消息具有单个主题，其中包含用句点分隔的元素。 尽管消息最终可能会被广播到其他后台程序，但它也会被发送到单个的 Rendezvous 后台程序。  
  
- 侦听器会向后台程序宣布其感兴趣的主题（带有基本通配符）。 如果两个后台程序相互连接，或者它们实际上是同一个后台程序，则会将拥有匹配主题的消息传递到该侦听程序。  
  
  可以使用可能的“容错/可靠”或“已认证”选项，根据需要将重要的“企业”功能分层部署到此后台程序，所有操作均通过潜在的基本消息实现。  
  
  消息本身可看作是键入的名称-值字段或数字-值字段（消息中的两个标识机制可以混合，并且可以与某些限制混合使用）。 消息本身可包含子消息，子消息中还可以包含子消息。  
  
  主题名称由圆点字符（句点）分隔的一个或多个元素组成。 这些元素实现一个主题名称层次结构，反映信息在应用程序系统中的结构。 以下字符串是有效主题名称的示例：  
  
- 运行。主页  
  
- RUN.for.Elected_Office  
  
  用于 TIBCO Rendezvous 的 BizTalk 适配器使用 TIBCO Rendezvous SDK 来将消息发布到 TIBCO Rendezvous 主题，并注册 TIBCO Rendezvous 事件。 与 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 相关的类在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 计算机中托管。 将启动单独的进程（运行时代理）并用作 Rendezvous 程序，.NET Framework 远程调用用于在这两者之间交换消息。  
  
- 信息级别、警告级别和错误级别的消息将被发送到 Windows 事件日志。  
  
- 包括调试级别消息在内的所有级别的消息都将被发送到 Windows 跟踪日志。  
  
## <a name="transmitter"></a>发送器  
 用于 TIBCO Rendezvous 的 BizTalk 适配器会对每个发送端口启动一个运行时代理。 TIBCO Rendezvous .net Framework API 只允许在全局范围内设置字符编码。 因此，其中一个端口配置选项是代码页数。 通过为每个代码页启动不同的进程，适配器可以为全球化提供更好的支持。  
  
## <a name="receiver"></a>接收方  
 用于 TIBCO Rendezvous 的 BizTalk 适配器会对每个接收位置启动一个运行时代理。  
  
## <a name="transactions"></a>中的  
 TIBCO Rendezvous 产品不是事务性的。 需要一个单独的产品，即 TIBCO Rendezvous TX。 用于 TIBCO Rendezvous 的 BizTalk 适配器不支持此版本中的事务。  
  
## <a name="security"></a>Security  
 TIBCO Rendezvous 仅支持 TIBCO Rendezvous 程序与后台程序之间的身份验证。 它不会执行授权或加密。 需要一个单独的产品，即 TIBCO Rendezvous DataSecurity。  
  
## <a name="see-also"></a>请参阅  
 [TIBCO Rendezvous 概念](../core/tibco-rendezvous-concepts.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-rendezvous.md)