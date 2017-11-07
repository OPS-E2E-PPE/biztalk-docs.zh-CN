---
title: "TIBCO 企业消息服务适配器功能 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ede748ce-3f28-4942-b2bd-e38e5f1b0f54
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ce63950ea9fca42969a7d8574fec76f438ed5f8f
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
---
# <a name="tibco-ems-adapter-features"></a>TIBCO EMS 适配器功能
用于 TIBCO Enterprise Message Service (EMS) 的 Microsoft BizTalk 适配器使您能够通过使用 BizTalk Server 和 TIBCO SDK 来发布和订阅由 TIBCO EMS 管理的队列和主题。 适配器将以快速、简便和可靠的方式集成 TIBCO EMS 消息。 它将在 TIBCO EMS 服务器和 Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 之间交换 XML 数据格式，以提供一个高度整合并且可靠的应用程序基础结构。 它提供了传输和接收适配器集成操作，可使用 XML 架构提供端到端业务流程管理。  
  
## <a name="data-validation"></a>数据验证  
 用于 TIBCO EMS 的 BizTalk 适配器作为一个高度集中的本地适配器，与 BizTalk Server 主机一起运行，并在配置时验证端口配置。 它将尽可能多地对数据进行验证，例如，有效名称、有效编号和有效范围。 它不会尝试进行连接。 因此，存在一个运行时调用（在这些情况下会记录错误）之前，将不会对主机、端口目标、用户和密码进行验证。  
  
## <a name="message-delivery"></a>消息送达  
 用于 TIBCO EMS 的 BizTalk 适配器将保证消息的一次性传递。 未达到 EMS 的邮件将在挂起时被标记为可重试。 可能会出现某些异常，例如，当执行期间存在一个有效的端口配置的时候。  
  
 适配器接受文本 EMS 消息类型。  适配器的转到 EMS，消息支持事务和事务支持受[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
> [!NOTE]
>  用于 TIBCO EMS 的 BizTalk 适配器和 EMS 服务器之间的连接不安全。 它不受提供的 TIBCO EMS SDK 所支持。  
  
 适配器支持所有标准的 JMS 属性和 EMS 扩展名。 这些属性放在可用于业务流程的 BizTalk 消息上下文中。  
  
## <a name="general-adapter-features"></a>常规适配器功能  
 用于 TIBCO EMS 的 BizTalk 适配器提供了一种手段，在 TIBCO EMS 系统和 BizTalk Server 之间交换实时企业数据。 适配器允许 XML 应用程序和 TIBCO EMS 之间的交互。 它为使用 TIBCO EMS 处理的入站和出站启用了 XML 应用程序。  
  
 适配器通过使用以下端口接受 XML 消息，以使 BizTalk Server 应用程序与 TIBCO EMS 进行通信：  
  
-   传输适配器，使用静态单向发送端口将消息发送到 TIBCO EMS。  
  
-   接收适配器，使用静态单向接收端口从 TIBCO EMS 接收消息。  
  
### <a name="transmit-adapter-architecture-send--static-one-way"></a>传输适配器体系结构： 发送 – 静态单向  
 在单向发送方案中，将对发送端口进行配置以便将消息发送到队列/主题。 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器会将请求转发到指定队列/主题上的 TIBCO EMS 服务器。 适配器使用 TIBCO EMS 通信协议将消息发送到 TIBCO EMS 系统。 TIBCO EMS 系统接收请求并执行业务逻辑。 若要呼叫 TIBCO EMS, 您必须为适配器提供配置信息以访问 TIBCO EMS 服务器。  
  
 下图显示了适配器的单向发送操作。  
  
 ![](../core/media/tibcoems-architecture-send.gif "TIBCOEMS_architecture_send")  
  
### <a name="receive-adapter-architecture-receive--static-one-way"></a>收到适配器体系结构： 接收 – 静态单向  
 在单向接收方案中，将对接收位置进行配置以接收 EMS 队列/主题上的信息。 用于 TIBCO EMS 的 BizTalk 适配器将侦听指定队列/主题上的消息，并将接收的消息提交到 BizTalk Server。  
  
 下图显示了适配器的单向接收操作。  
  
 ![](../core/media/tibcoems-architecture-receive.gif "TIBCOEMS_architecture_receive")  
  
## <a name="see-also"></a>另请参阅  
 [开发应用程序](../core/developing-applications5.md)   
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)