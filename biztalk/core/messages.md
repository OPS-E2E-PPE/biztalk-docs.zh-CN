---
title: 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, headers
- messages, acknowledgements
- messages, persisting
- messages
- examples, message headers
- properties
- message headers
- EMS messages
ms.assetid: 65bb3431-7186-4d4c-b004-932cdf070e73
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f7313e93029ca75d345aa4e9603699c50399230
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22266685"
---
# <a name="messages"></a>消息
某个企业消息服务 (EMS) 消息，如 JMS 消息包含三个独立的部分： 标头、 属性和正文。 标头是 EMS 消息中唯一必需的部分。 本主题介绍如何在用于在 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器中处理消息。  
  
> [!NOTE]
>  若要设置或检索一个标头字段 （例如，设置消息优先级或相关 ID） 或从业务流程的消息属性，必须添加对引用**Microsoft.BizTalk.Adapters.TIBCOEMSProperties.dll**中你使用解决方案资源管理器的项目。  
  
## <a name="message-header"></a>消息标头  
 消息标头包括一系列包含值的预定义字段。 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器了解它在标头中可以设置和不可设置的内容。 如果您尝试设置一个只读值，该适配器将在 Properties{} 部分中重定向或设置此值。  
  
### <a name="header-example"></a>标头示例  
 在下面的示例，请注意，**属性 = {目标 = {字符串： 队列 [季 2 季]}}**。 `Properties`是一个属性，包含一个字符串，字符串的内容是**季 2 季**。 这与 Destination 部分无任何关系；该属性包含的所设置的字符串值无法转向其他任何位置，因此适配器将其保留在此部分中的此位置。  
  
 `ReplyTo`属性可以设置在业务流程，以便告知最终的使用者发送响应的位置。 EMS 设置`Destination`属性时从 TIBCOEMS 收到的消息。 业务流程中的上述第二个属性是只读的，用于接收来自 TIBCOEMS 的消息，该属性不能在业务流程中进行编辑。  
  
 例如，业务流程无法在业务流程内部调度消息和动态设置目标。 Destination 的值是由消息传输的目标端口设置的。  
  
 如果要将消息调度到不同队列，必须为每个队列创建发送端口。 然后，业务流程可确定应向哪些端口分配消息。  
  
 在下面的消息示例，目标 =`{Queue[Q1]}`是只读的。 此值是在服务器收到消息时由 TIBCOEMS 设置的。 Destination 的值 Q1 来自于“传输属性”。  
  
#### <a name="example"></a>示例  
  
```  
TextMessage={   
    Header={ MessageID={ID:EMS-SERVER.824437A58B11C75F4:1}   
    Destination={Queue[Q1]}   
  
        ' This is READONLY. It gets set by the server when the  
        ' message is received by the server (EMS). It is set in the  
        ' Transport Properties when you specify that you want to  
        ' listen for messages on Q1.  
    ReplyTo={}   
    DeliveryMode={Persistent}   
    Redelivered={False}   
    CorrelationID={}   
    MsgType={}   
    Timestamp={12/1/2005 11:59:01 PM}   
    Expiration={0}   
    Priority={1} }   
    Properties={ Destination={String:Queue[Q2]} }   
  
        ' This is a property that contains a string, and the   
        ' contents of the string is Q2. This has nothing to do with  
        ' the Destination section above – it is just another   
        ' property that is set.   
        ' This is in the schema. The adapter knows what it can and   
        ' cannot set in an EMS header. The values that the adapter   
        ' cannot set are put in the Properties section.   
    text={<?xml version="1.0" encoding="utf-16"?>  
    <ns0:Employees xmlns:ns0="http://BizTalk_Server_Project1.Employee">  
        <Emp Id="Id_0">  
            Name>Name_0</Name>  
        </Emp>  
    </ns0:Employees>  
    }  
```  
  
 标头包含一系列包含值的预定义字段，适配器将这些字段升级为 BizTalk Server 消息上下文，以便在业务流程中使用。 升级后的属性在定义上与 JMS 规范和 TIBCO Enterprise Message Service 扩展定义的标准标头属性相同。 除了两个的所有属性都均可用于业务流程从 EMS 接收到：`Destination`和`ReplyTo`描述不能在单个属性作为业务流程中使用正确映射的目标。  
  
 用于 TIBCO EMS 的 BizTalk 适配器将 TIBCOEMS 属性映射为字符串类型，并使用 Destination 的字符串表示形式， 这看起来像`StaticQueue[queuename]`或`StatisTopic[topicname]`。 业务流程可以设置的值`ReplyTo`，并将该适配器替换它的标头中的有效目标对象。  
  
 适配器提供了一个描述业务流程可使用的所有 TIBCO EMS 标头属性的架构和引用程序集。 这些属性可用于筛选传入消息，也可用于添加到传出消息。 控制业务流程筛选器的规则不同于 EMS 服务器的消息选择器规则。 例如，业务流程可以筛选在`TibcoEMS.ReplyTo`或`TibcoEMS.Destination`属性，但没有 JMS 规范来对此属性的消息选择器中不支持。  
  
 当业务流程定义这些属性时，这些属性将包含在 JMS 消息的标头属性中。 或者在接收 EMS 消息时，这些标头属性将复制到 BizTalk Server 消息上下文中。  
  
 如果某一属性与端口配置匹配，则消息的此属性值将优先于端口配置中的相应值。 例如，如果在端口中将优先级设置为 4，但在业务流程的逻辑中将消息的优先级设置为 9，那么该消息的优先级则为 9，并且将被发送到 TIBCO EMS。  
  
### <a name="property-descriptions"></a>属性说明  
 下表说明了用于 TIBCO Enterprise Message Service 的 BizTalk 适配器如何使用每个属性。  
  
|Name|类型|Description|  
|----------|----------|-----------------|  
|TibcoEMS.MessageID|string|发送调用向每个消息分配一个唯一 ID，并将其记录在标头中。<br /><br /> 所有消息 ID 的值均以包含三个字符的前缀 ID 开头（鉴于此原因而保留此前缀 ID）。<br /><br /> 只读。 更改此值不会对消息产生影响。|  
|TibcoEMS.Timestamp|long|发送调用在标头中记录 UTC 时间戳。 该属性指示服务器接受消息的大致时间。<br /><br /> 该值是自 1970 年 1 月 1 日之后的时间（以毫秒为单位）。<br /><br /> 只读。 更改此值不会对消息产生影响。|  
|TibcoEMS.Redelivered|boolean|服务器设置标头以指示某一消息是否与先前已传送的消息重复：<br /><br /> -false-服务器尚未以前尝试将此消息传递给使用者。<br />-true-它是可能的但不是保证，服务器以前已尝试将此消息传递给使用者，但使用者未返回及时确认。<br /><br /> 只读。 更改此值不会对消息产生影响。|  
|TibcoEMS.Destination|string|发送调用在此标头中记录消息的目标（队列或主题）。 其格式已从目标形式改为字符串形式。 之前已对此格式进行了介绍。<br /><br /> 只读。 更改此值不会对消息产生影响。|  
|TibcoEMS.DeliveryMode|string|有两个可能值： 持久和非持久。 默认值为 PERSISTENT 模式。<br /><br /> 适配器在确认将消息发送到 BizTalk Server 之前将一直等待 EMS 服务器的确认。 此标头属性和端口配置项控制 EMS 向适配器发送此确认的时间，并控制消息传输的可靠性。<br /><br /> 使用 PERSISTENT 传送模式—在 EMS 服务器中成功持久化消息之前，EMS 服务器将一直等待。 此操作可保证消息已到达队列。 使用 PERSISTENT 模式传送时，请考虑以下各项：<br /><br /> 消息越大，则 BizTalk Server 用来确认该消息是否已发送的时间就越长。<br /><br /> 使用 NON-PERSISTENT 模式—EMS 服务器先返回确认，然后再对消息进行持久化处理。 如果 EMS 服务器出现故障，则消息可能已丢失，而 BizTalk Server 认为已成功发送该消息。|  
|TibcoEMS.Expiration|long|消息在过期之前的生存时间长度。 如果设置为 0，消息则不会过期。<br /><br /> 消息生存时间以毫秒为单位指定。|  
|TibcoEMS.Priority|int|使用 0 至 9 之间的某个数字级别将消息优先级定义为正常或加急。 数字越大，表示的优先级越高。|  
|TibcoEMS.CorrolationID|string|可用于链接消息，例如将响应消息链接到请求消息。<br /><br /> 这通常是相同的值`EMS.JMSMessageID`。 这通常用于连同`EMS.JMSReplyTo`属性。|  
|TibcoEMS.ReplyTo|string|应接收消息答复的目标。 格式等同于`EMS.JMSDestination`和也端口的配置。|  
|TibcoEMS.Type|string|未描述消息类型（文本、字节、字符串…）。<br /><br /> 某些 JMS 提供程序使用消息存储库来存储消息类型定义。 客户端程序可在此字段中存储一个值，以便引用存储库中的定义。 EMS 支持但不使用此标头。<br /><br /> JMS 规范没有定义标准的消息定义存储库，也没有定义消息类型定义的命名策略。<br /><br /> 某些提供程序需要每个应用程序消息的消息类型定义。 为保证与此种提供程序兼容，即使客户端应用程序不使用此标头，客户端程序也可以对此标头进行设置。<br /><br /> 为保证可移植性，客户端可使用符号值（而非文本值）设置此标头，并将其配置为与提供程序的存储库匹配。|  
  
## <a name="properties"></a>属性  
 集成器可定义一组属性，以便升级为 BizTalk Server 消息上下文，然后可将这些属性添加到 JMS 消息的属性部分。 创建架构时，集成器将负责定义属性的类型。 如果在消息选择器中使用此属性的值，那么根据此属性的类型，某些操作是有效的。 例如，如果消息选择器**myMessageProperty > 5**是使用，该属性必须定义为整数值，并适配器将值放入一个整数值形式的消息。 对于要升级的属性，属性名称必须以 EMSX 开头， 此外，其名称不能与预定义属性的名称相同。  
  
 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器提供了一个架构和程序集，用于声明此部分中显示的特定 EMS 和 JMS 属性。 可扩充此架构和程序集，以包含任何遗漏项。 在消息上下文中引用的所有 EMSX 属性都将放置到 EMS 消息的消息属性部分中。 有关详细信息，请参阅 TIBCO EMS 用户指南。  
  
## <a name="body"></a>正文  
 EMS 支持枚举 JMS 规范中的所有消息： 文本、 字节、 流、 地图中和对象。 用于 TIBCO EMS 的 BizTalk 适配器仅支持文本消息类型。  
  
 JMS 并未要求文本类型的消息应包含 XML 格式的正文。 适配器不处理消息; 的正文它提供给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收到。  因此，消息提交到 BizTalk 适配器可能不始终解析为 XML 数据中。  
  
## <a name="persistent-messages"></a>持久性消息  
 消息可持久保留在 EMS 服务器中，以保证对订户进行一次性传送；但是，这可能会严重影响适配器的性能。 发送消息时，EMS 会将此消息存储在本地存储区，然后再向适配器确认已收到此消息。 您可以在业务流程中针对每条消息设置此属性，也可以针对端口处理的所有消息设置此属性。  
  
 从接收方面而言，如果适配器未订阅到主题，则可能丢失消息。 对于发布为主题的消息，如果没有任何订阅，EMS 将不会持久保留这些消息。 适配器需要即使当前没有订阅也仍会接收消息发布的机制；但是，此机制与使用持久性消息一样，会对 EMS 性能产生重大影响，因此此机制并非总是必需的。  
  
> [!NOTE]
>  从 EMS 角度而言，存在一个接收机制，实际上此接收机制并不是所需的，因此并未实现。 此问题仅与主题相关；并不影响队列。 主题通常用于特定于时间的数据，如股票行情。 如果股票价格丢失，如您所知，稍后将再次发布价格。  
  
 鉴于以上原因，端口配置允许您在 EMS 服务器上启用或禁用消息持久化功能。  
  
## <a name="message-acknowledgement"></a>消息确认  
 将消息正确调度到 BizTalk Server 时，用于 TIBCO Enterprise Message Service 的 BizTalk 适配器将始终确认已收到此消息。 这表示 EMS 将向适配器重新发送未经确认的消息。 适配器无法控制 EMS 重新发送消息的次数，这是因为这是目标自身的配置；但是，适配器可控制是否向 MessageBox 发送消息。 EMS 服务器控制向队列发送失败消息的最大次数。  
  
 对于将被重新传送的消息，EMS 服务器设置`JMSRedelivered`属性设置为 True、 增量`JMSXDeliveryCount`。 业务流程可使用上述两个属性值。 在未在 EMS 服务器中传送消息的情况下，您不能将此消息移动到 EMS 的未传送队列中。 否则将更改消息属性。  
  
 如果消息达到其配置的最大重新传送计数，EMS 服务器将确定是否应删除此消息，或将其放置到 $sys.undelivered 队列中。 EMS 服务器所做的决策基于`JMS_TIBCO_PRESERVE_UNDELIVERED`属性; 如果为 True，消息将发送到未传递队列，或它已被删除。 在发送消息之前，您可以在业务流程中设置此属性。 传送之后则无法更改此消息属性。 消息成功发送到 EMS 时，BizTalk Server 将对此消息进行确认。 如果发送到 EMS 失败，消息将挂起并标记为可重试。  
  
## <a name="see-also"></a>另请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)