---
title: 按序送达消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- backing up, message order
- file transport, message order
- Messaging Engine, transports
- messages, performance
- dynamic send ports, message order
- BTS.SuspendAsNonResumable message context property
- performance, message order
- Messaging Engine, performance
- Messaging Engine, message order
- MessageBox database, message order
- messages, sorting
- backing up, backup transports
- adapters, custom receive adapters
- adapters, messages
- customizing, receive adapters
ms.assetid: 39e0bba6-81f5-4ae0-af92-837b225bc801
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6068d3d4e84389022a07d315b808b7005b95a88c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262596"
---
# <a name="ordered-delivery-of-messages"></a>按序送达消息
按序的消息传递可确保发布到 MessageBox 数据库中给定订单的消息将传送到每个匹配的订户所在的相同顺序仍依照其发布到 messagebox。  
  
## <a name="configuring-ordered-message-delivery"></a>配置按序送达的消息  
 可以在以下位置配置按序送达的消息：  
  
-   **接收**业务流程中的形状  
  
-   发送端口  
  
## <a name="ordered-delivery-with-existing-transports"></a>按序送达使用现有传输实现  
 某些传输，如文件和 HTTP 的基础的协议不一致的按序送达的概念。 但是，即使使用此类传输，如果该端口绑定到传输标记为按序送达，则 BizTalk Server 通过确保传输不会直到成功发送当前一获取下一个出站消息来强制执行按序的送达. 若要实现此目的，BizTalk Server 每个将消息传递到传输的适配器在单个批次并等待直到该适配器已成功删除该消息从 messagebox 中另一个批处理中的下一条消息，交付到适配器之前。  
  
### <a name="ordered-delivery-for-custom-adapters"></a>自定义适配器按序送达  
 为自定义接收适配器，有一些特殊注意事项。 如果你正在编写的自定义适配器支持在按序送达接收，适配器应执行以下操作：  
  
- 在提交一批消息之后, 您的自定义接收适配器应等待**BatchComplete**从 BizTalk Server 提交下一批之前的回调。 有关更多详细信息，请参阅[Batch-Supported 接收适配器的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)。  
  
- 如果消息在管道中失败，则应挂起，最好作为不可恢复。 使用**BTS。SuspendAsNonResumable**消息上下文属性中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来适当地标记消息。  
  
> [!NOTE]
>  如果以后恢复挂起的消息，消息顺序可能会中断。 如果不希望此行为，挂起失败的消息作为不可恢复。  
  
 构建自定义适配器的详细信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。  
  
## <a name="conditions-for-end-to-end-ordered-message-processing"></a>条件的端到端按序消息处理  
 若要提供端到端按序的送达必须满足以下条件:  
  
- 必须与适配器提交给 BizTalk Server 时保留消息的顺序接收消息。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，这样的适配器的示例包括 MSMQ 和 MQSeries。 此外，可以使用 HTTP 或 SOAP 适配器提交消息的顺序，但在这种情况下 HTTP 或 SOAP 客户端需要通过一次提交一个消息来强制实现顺序。  
  
- 您必须订阅这些消息与发送端口都**按序送达**选项设置为`True`。  
  
- 如果业务流程来的处理消息，只能运行一个业务流程实例应使用，该业务流程应配置为使用顺序保护，并**按序送达**属性业务流程的接收端口应设置为`True`。  
  
## <a name="restrictions"></a>限制  
 以下不支持按序的送达消息：  
  
- 动态发送端口中[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]和以前的版本

- 动态发送端口中[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]（和任何更高版本） 的适配器类型**不**支持静态发送端口按序送达
  
- 备份传输  

  
## <a name="interactions"></a>交互  
 为发送端口配置按序的送达后，应注意与 BizTalk Server 中的其他配置行为之间的以下交互：  
  
-   用于上相同的"停止发送随后的消息在当前消息失败时"设置发送端口：  
  
    -   **如果为 false。** 失败的消息已挂起 （作为不可恢复），所有后续消息继续处理。 这会保留未失败消息的顺序，但可能会导致序列中的空白。 例如，如果收到订单 101、 102 和 103，并且订单 102 被挂起，则订单 101 和 103 将继续按顺序处理。  
  
    -   **为 true。** 如果任何消息处理失败，则挂起发送端口实例。 这会导致消息被挂起的有序集的所有后续消息。 这通过防止在送达失败的消息传递之前的后续消息保留消息顺序。  
  
-   如果要求响应发送端口具有"停止发送随后的消息在当前消息失败时"属性设置为`true`，以及是否可恢复交换处理配置的接收管道的拆装阶段的响应，然后发送端口不会停止发送消息 （即实例不会挂起） 如果在拆装响应可恢复的错误。  
  
-   之前删除按序发送端口，请确保有与之关联的实例。 如果有关联的实例，应删除发送端口之前终止它们。  
  
## <a name="ordered-delivery-to-file-transport"></a>按序送达文件传输  
 消息按顺序到达文件适配器。 文件适配器可能会将消息附加到单个文件，或写出一系列文件，其结果如下：  
  
-   如果消息数据附加到单个文件，则各个消息将按序附加。 使用文件适配器的发送端口上的按序的送达选项仅在发送传输以附加模式工作时才有意义  
  
-   如果消息将写入到单个文件中，顺序将反映在文件名称，即按序命名。 在这种情况下，对于由适配器编写的文件，与编年表 （例如，文件创建时间或修改时间） 相关的文件系统属性不一定反映消息的到达顺序。  
  
## <a name="performance-impact-of-ordered-delivery"></a>按序送达对性能的影响  
 若要实现按序的送达，BizTalk Server 必须序列化消息路径各个点的有序消息的处理。 此扩展适用于横向扩展技术，例如，消息的并行处理多个主机实例使用。 在使用按序的送达，甚至端口配置为运行在多个主机实例上运行仅在单个主机实例以确保按序的送达。 但是，在此情况下，可用性组仍将保留因为正在处理的主机实例失败按序送达消息中的另一个可用的主机实例上的失败消息重新处理的结果。  
  
 启用按序送达时，默认值**重试间隔**为 5 分钟。 若要提高性能，设置为最低值，该值为 1 分钟重试间隔。 **重试间隔**属性可接受值为零 (0)，但零 (0) 无效。 **重试计数**也可以进行调整到所需的重试次数。 例如，如果您知道请求应处理在 < 1 分钟和发送端口目标始终是可访问，将这两个值设置为 1。  
  
 若要更改重试值，请转到[如何配置传输高级选项的发送端口](http://go.microsoft.com/fwlink/p/?LinkID=267697)。  
  
 有关按序送达的其他信息，请参阅以下：  
  
 [BizTalk:端到端按序消息处理选项](http://social.technet.microsoft.com/wiki/contents/articles/12887.biztalk-end-to-end-ordered-message-processing-options.aspx)  
  
 [BizTalk:按序的送达](http://social.technet.microsoft.com/wiki/contents/articles/6681.biztalk-ordered-delivery.aspx)  
  
## <a name="see-also"></a>请参阅  
 [按序送达消息使用 MSMQ 适配器](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md)   
 [使用 MQSeries 适配器按序送达消息](../core/ordered-delivery-of-messages-with-the-mqseries-adapter.md)