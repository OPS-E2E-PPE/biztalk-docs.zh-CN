---
title: 消息 |Microsoft Docs
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
ms.openlocfilehash: e28c7296023cc9dec30dfede9c31f2de78e89dbd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394521"
---
# <a name="messages"></a>消息
Enterprise Message Service (EMS) 消息，如 JMS 消息，包含三个独立的部分： 标头、 属性和正文。 标头是唯一必需的 EMS 消息部分。 本主题介绍适用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器中处理消息如何。  
  
> [!NOTE]
>  若要设置或检索标头字段 （例如，设置消息优先级或相关 ID） 或从业务流程的消息属性，必须添加对的引用**Microsoft.BizTalk.Adapters.TIBCOEMSProperties.dll**中你使用解决方案资源管理器的项目。  
  
## <a name="message-header"></a>消息标头  
 消息标头包含一系列包含值的预定义字段。 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器知道它可以和不能设置标头中。 如果您尝试设置只读的值，适配器将重定向，或在属性中设置此值{}部分。  
  
### <a name="header-example"></a>标头示例  
 在以下示例中，注意**属性 = {目标 = {字符串： 队列 [第 2 季度]}}**。 `Properties` 是包含一个字符串，一个属性，该字符串的内容是**第 2 季度**。 这有无与 Destination 部分; 操作它包含的字符串值的设置，可能需要任何其他位置，因此适配器将其保留在本部分中。  
  
 `ReplyTo`属性可以设置在业务流程中，以告诉最终使用者发送响应的位置。 EMS 设置`Destination`属性从 TIBCOEMS 接收消息。 此第二个属性是在业务流程中接收来自 TIBCOEMS 的消息以只读的不能在业务流程中进行编辑。  
  
 例如，业务流程不能将消息调度并将业务流程中动态目标设置。 由消息传输到的端口设置的目标值。  
  
 如果你想要将消息调度到不同的队列，则必须创建每个队列的发送端口。 然后，业务流程可以决定要将消息分配的端口。  
  
 在以下消息示例中，目标 =`{Queue[Q1]}`是只读的。 服务器接收消息时由 TIBCOEMS 设置此值。 值为目标，第 1 季度，来自传输属性。  
  
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
  
 标头包含一系列包含值，则适配器将提升为 BizTalk Server 消息上下文，以便在业务流程中使用的预定义字段。 升级的属性是在定义上与 JMS 规范和 TIBCO Enterprise Message Service 扩展定义的标准标头属性相同的。 除了两个的所有属性都是从 EMS 接收到业务流程可：`Destination`和`ReplyTo`描述不能正确映射以便在单个属性作为业务流程中使用的目标。  
  
 用于 TIBCO EMS 的 BizTalk 适配器将 TIBCOEMS 属性映射为字符串类型，并使用目标字符串表示形式。 这看起来像`StaticQueue[queuename]`或`StatisTopic[topicname]`。 业务流程可以设置的值为`ReplyTo`，并使用有效的目标对象的标头中的适配器替换它。  
  
 适配器提供了描述可由业务流程的所有 TIBCO EMS 标头属性的架构和引用程序集。 若要筛选传入消息，或将添加到传出消息，可以使用这些属性。 管理业务流程筛选器的规则不同于 EMS 服务器的消息选择器。 例如，业务流程可以根据筛选`TibcoEMS.ReplyTo`或`TibcoEMS.Destination`属性，但在 JMS 规范来对此相同属性的消息选择器中不支持。  
  
 当业务流程定义了这些属性时，它们包含在 JMS 消息的标头属性。 或者，当收到 EMS 消息时，这些标头属性复制到 BizTalk Server 消息上下文。  
  
 当一个属性匹配的端口配置时，对消息属性的值优先上端口的配置。 例如，如果在端口中的优先级设置为 4，但消息的优先级设置为 9 的业务流程逻辑中，接收消息的 TIBCO EMS 为具有优先级为 9。  
  
### <a name="property-descriptions"></a>属性说明  
 下表介绍 TIBCO Enterprise Message Service 的方式的 BizTalk 适配器使用的每个属性。  
  
|“属性”|类型|Description|  
|----------|----------|-----------------|  
|TibcoEMS.MessageID|string|发送调用向每个消息分配一个唯一 ID 并将其记录在标头中。<br /><br /> 所有消息 ID 的值都开头的三字符前缀 ID （可用于此目的）。<br /><br /> 只读。 更改的值不会影响该消息。|  
|TibcoEMS.Timestamp|long|标头中发送调用记录 UTC 时间戳。 这指示服务器接受消息的大致时间。<br /><br /> 自 1970 年 1 月 1 日起的值是以毫秒为单位<br /><br /> 只读。 更改的值不会影响该消息。|  
|TibcoEMS.Redelivered|boolean|服务器设置标头以指示消息是否可能重复先前已送达的消息：<br /><br /> -false — 服务器具有先前未尝试向使用者传送此消息。<br />-true-它是可能的但不是保证，服务器以前已尝试将此消息传递给使用者，但使用者未及时返回确认。<br /><br /> 只读。 更改的值不会影响该消息。|  
|TibcoEMS.Destination|string|此标头中发送调用记录消息的目标 （队列或主题）。 格式为改编从目标为字符串。 前面所述的格式。<br /><br /> 只读。 更改的值不会影响该消息。|  
|TibcoEMS.DeliveryMode|string|具有两个可能值：持久性和非永久。 默认值为 PERSISTENT 模式。<br /><br /> 适配器在等待之前确认将消息发送到 BizTalk Server 确认从 EMS 服务器。 此标头属性和端口配置项控制 EMS 向适配器发送此确认和控制消息传输的可靠性所需的时间。<br /><br /> 使用 PERSISTENT 传送模式 — EMS 服务器等待，直到该消息已成功保存在 EMS 服务器。 此操作可保证消息已到达队列中。 使用 PERSISTENT 模式传送时，考虑以下方面：<br /><br /> 较大的消息的时间越长，需要为 BizTalk Server 以便发送确认该消息。<br /><br /> 使用 NON-PERSISTENT 模式 — EMS 服务器先返回确认，保存该消息。 如果 EMS 服务器出现故障时，它被视为成功发送的 BizTalk Server 中可能会丢失的消息。|  
|TibcoEMS.Expiration|long|该消息将存放在过期之前的时间长度。 如果设置为 0，消息不会过期。<br /><br /> 生存时间以毫秒为单位指定。|  
|TibcoEMS.Priority|ssNoversion|使用的某个数字级别为 0 到 9，消息优先级定义为正常或加急。 数字越大，表示优先级越高。|  
|TibcoEMS.CorrolationID|string|可用于链接消息，例如将响应消息链接到请求消息。<br /><br /> 这通常是相同的值`EMS.JMSMessageID`。 这通常在一起使用`EMS.JMSReplyTo`属性。|  
|TibcoEMS.ReplyTo|string|消息答复应发送到目标。 格式等同于`EMS.JMSDestination`和也端口的配置。|  
|TibcoEMS.Type|string|不描述消息类型 （文本、 字节、 字符串...）。<br /><br /> 某些 JMS 提供程序使用的消息存储库来存储消息类型定义。 客户端程序可以在此字段以引用存储库中的定义中存储一个值。 EMS 支持此标头，但不使用它。<br /><br /> JMS 规范没有定义标准的消息定义存储库，也没有定义消息类型定义的命名策略。<br /><br /> 某些提供程序需要为每个应用程序消息的消息类型定义。 若要保证与此类提供程序的兼容性，客户端程序可以设置此标头，即使客户端应用程序不使用它。<br /><br /> 若要确保可移植性，客户端可以设置符号值 （而不是文本），此标头并将它们配置为匹配提供程序的存储库。|  
  
## <a name="properties"></a>属性  
 系统集成商可以定义一组属性，以便升级到 BizTalk Server 消息上下文之后该, 属性添加到 JMS 消息的属性部分。 系统集成商负责创建架构定义的属性类型时。 如果在消息选择器中使用此属性的值，则某些操作是根据属性类型有效。 例如，如果消息选择器**myMessageProperty > 5**是使用，必须将属性定义为整数值，并且适配器可将值放置在消息中作为一个整数值。 对于要升级的属性，属性名称必须以 EMSX 开头。 它们还不能与预定义的属性相同的名称。  
  
 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器提供的架构和程序集，该声明可以出现在本部分中的特定于 EMS 和 JMS 属性。 这些可以扩充以包含任何遗漏项。 在消息上下文中引用的所有 EMSX 属性都将都置于 EMS 消息的消息属性部分。 有关详细信息，请参阅 TIBCO EMS 用户指南。  
  
## <a name="body"></a>正文  
 EMS 支持 JMS 规范中枚举的所有消息： 文本、 字节、 流、 映射和对象。 用于 TIBCO EMS 的 BizTalk 适配器仅支持文本消息类型。  
  
 JMS 并未要求文本类型的消息包含 XML 格式的正文。 适配器不会处理消息; 的正文提供给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收。  因此，由适配器提交到 BizTalk 消息可能并非始终会解析为 XML 数据。  
  
## <a name="persistent-messages"></a>持久性消息  
 消息可以保留在 EMS 服务器以保证一次性传送到订阅服务器;但是，这可以对适配器的性能产生重大影响。 当发送消息时，EMS 将消息在本地存储中存储确认接收到适配器消息之前。 可以将此属性设置在每个消息的基础业务流程中或端口处理的所有消息。  
  
 从接收方面而言，该适配器可能丢失消息时未订阅到主题。 不保存 ems 的消息发布到主题时没有任何订阅。 适配器需要一种机制来接收消息发布即使当前没有订阅;但是，如使用持久性消息时，这对 EMS 性能产生重大影响，并且它并不总是必需。  
  
> [!NOTE]
>  没有一种机制接收从 EMS 角度来看，但未实现，也不真正需要。 这是问题仅与主题;队列不受影响。 本主题是通常用于特定于时间的数据--股票报价，例如。 如果股票价格丢失，您知道它将在稍后发布。  
  
 出于这些原因，端口配置允许您启用或禁用消息持久化 EMS 服务器上。  
  
## <a name="message-acknowledgement"></a>消息确认  
 用于 TIBCO Enterprise Message Service 的 BizTalk 适配器始终确认已收到的消息时该消息正确调度到 BizTalk Server。 这意味着未确认的消息是从 EMS 重新发送到适配器。 适配器无法控制 ems 发送消息，因为这是目标自身; 的配置的次数但是，如果将消息发送到 MessageBox 或不可以控制适配器。 EMS 服务器控制最多的失败的消息发送到队列的次数。  
  
 对于重新传送的消息，EMS 服务器设置`JMSRedelivered`属性设置为 True 并增加`JMSXDeliveryCount`。 这两个属性值可供业务流程。 无法将消息移动到 EMS 的未传送队列，却不能那里实现。 执行此操作将更改消息属性。  
  
 当消息到达其已配置的最大重新传送计数时，EMS 服务器将确定是否应删除或放入 $sys.undelivered 队列消息。 EMS 服务器使基于决策`JMS_TIBCO_PRESERVE_UNDELIVERED`属性; 如果为 True，消息将转至未传送队列，或将其删除。 可以在业务流程中发送消息之前设置此属性。 传送之后无法更改消息属性。 它们都成功后，将向 BizTalk Server 确认发送到 EMS 的消息。 如果没有到 EMS 失败发送主题，它们已挂起并标记为可重试。  
  
## <a name="see-also"></a>请参阅  
 [入门](../core/getting-started-with-biztalk-adapter-for-tibco-enterprise-message-service.md)