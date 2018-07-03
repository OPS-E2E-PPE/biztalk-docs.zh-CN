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
ms.openlocfilehash: 52798c5f34c1f436d5c55954f61c6e18fcb2a398
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013014"
---
# <a name="ordered-delivery-of-messages"></a>按序送达消息
按序送达消息可以确保按给定顺序发布到 MessageBox 数据库的消息能够以发布到 MessageBox 的相同顺序送达每个匹配的订户。  
  
## <a name="configuring-ordered-message-delivery"></a>配置按序消息送达  
 可以在以下位置配置按序消息送达：  
  
-   **接收**业务流程中的形状  
  
-   发送端口  
  
## <a name="ordered-delivery-with-existing-transports"></a>使用现有传输实现按序送达  
 某些传输的基础协议（例如，FILE 和 HTTP）与按序送达的概念不一致。 但是，即使对于此类传输，如果将绑定到传输的端口标记为按序送达，BizTalk Server 也会通过确保在当前消息成功发送之后再获取下一个出站消息来强制实现按序送达。 若要达到此目的，BizTalk Server 会将每个消息放在单个批中传递给传输的适配器，并等到适配器已从 MessageBox 中成功删除消息之后，再通过另一个批将下一条消息传递给适配器。  
  
### <a name="ordered-delivery-for-custom-adapters"></a>自定义适配器的按序送达  
 对于自定义接收适配器，有一些特殊注意事项。 如果你正在编写支持在接收时按序送达的自定义适配器，则该适配器应执行以下操作：  
  
- 在提交一批消息之后, 您的自定义接收适配器应等待**BatchComplete**从 BizTalk Server 提交下一批之前的回调。 有关更多详细信息，请参阅[Batch-Supported 接收适配器的接口](../core/interfaces-for-a-batch-supported-receive-adapter.md)。  
  
- 如果消息在管道中失败，则应挂起该消息，最好作为不可恢复的消息。 使用**BTS。SuspendAsNonResumable**消息上下文属性中的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来适当地标记消息。  
  
> [!NOTE]
>  如果随后恢复了挂起的消息，则可能会打乱消息顺序。 如果不想出现此行为，请将失败消息作为不可恢复消息挂起。  
  
 构建自定义适配器的详细信息，请参阅[开发自定义适配器](../core/developing-custom-adapters.md)。  
  
## <a name="conditions-for-end-to-end-ordered-message-processing"></a>端到端按序消息处理的条件  
 为提供端对端的按序送达功能，必须满足以下条件：  
  
- 接收消息的适配器必须保持消息提交给 BizTalk Server 时的顺序。 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，这样的适配器的示例包括 MSMQ 和 MQSeries。 此外，HTTP 或 SOAP 适配器也可以用来按序提交消息，但在该情况下，HTTP 或 SOAP 客户端需要通过每次提交一条消息来强制实现顺序提交。  
  
- 您必须订阅这些消息与发送端口都**按序送达**选项设置为`True`。  
  
- 如果业务流程来的处理消息，只能运行一个业务流程实例应使用，该业务流程应配置为使用顺序保护，并**按序送达**属性业务流程的接收端口应设置为`True`。  
  
## <a name="restrictions"></a>限制  
 在以下情况下不支持按序送达消息：  
  
- 动态发送端口中[!INCLUDE[bts2013r2_md](../includes/bts2013r2-md.md)]和以前的版本

- 动态发送端口中[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]（和任何更高版本） 的适配器类型**不**支持静态发送端口按序送达
  
- 备份传输  

  
## <a name="interactions"></a>交互  
 为发送端口配置按序送达后，应注意以下与 BizTalk Server 中的其他配置行为的交互：  
  
-   对于同一发送端口上的“当前消息失败后停止发送随后的消息”设置：  
  
    -   **如果为 false。** 仅挂起失败消息（不可恢复），将继续处理随后的所有消息。 这样可以保留未失败消息的顺序，但在序列中会存在中断的情况。 例如，如果收到订单 101、102 和 103，并且订单 102 被挂起，则订单 101 和 103 将继续按序处理。  
  
    -   **为 true。** 如果对任何消息的处理失败，都将挂起发送端口实例。 这会导致按序排列的消息集中随后的所有消息都被挂起。 通过防止在送达失败消息之前送达随后的消息，这样可以保留消息顺序。  
  
-   如果要求响应发送端口的“当前消息失败后停止发送随后的消息”属性设置为 `true`，并且为响应的接收管道的拆装阶段配置了可恢复的交换处理，那么，如果在拆装响应的过程中存在可恢复的错误，则发送端口不会停止发送消息（即实例不会挂起）。  
  
-   在删除按序发送端口之前，请确保没有与其关联的实例。 如果存在关联的实例，则应在删除发送端口之前先终止这些实例。  
  
## <a name="ordered-delivery-to-file-transport"></a>按序送达到文件传输  
 消息将按顺序到达文件适配器。 文件适配器可能将消息附加到单个文件中或编写一个文件序列，其结果如下：  
  
-   如果将消息数据附加到单个文件中，则各个消息将按序附加。 使用 FILE 适配器的发送端口的“按序送达”选项只有在发送传输以附加模式工作时才有意义。  
  
-   如果将消息写入各个文件中，则顺序将反映在文件名中，即按序命名。 在这种情况下，对于由适配器编写的文件，与时间信息（例如，文件创建时间或修改时间）相关的文件系统属性不必反映消息的到达顺序。  
  
## <a name="performance-impact-of-ordered-delivery"></a>按序送达对性能的影响  
 为了实现按序送达，BizTalk Server 必须对消息路径各个点上按序分布的消息的处理进行序列化。 这对扩展技术（例如，使用多个主机实例实现对消息的并行处理）非常有效。 在使用按序送达时，甚至配置为在多个主机实例上运行的端口也只运行在单个主机实例上，以确保按序送达。 但在此情况下仍然能保持高可用性，因为如果正在处理按序送达消息的主机实例发生故障，将会在另一个可用主机实例上重新处理失败消息。  
  
 启用按序送达时，默认值**重试间隔**为 5 分钟。 为了改进性能，请将“重试间隔”设置为最小值，即 1 分钟。 **重试间隔**属性可接受值为零 (0)，但零 (0) 无效。 **重试计数**也可以进行调整到所需的重试次数。 例如，如果你知道应在不到 1 分钟之内处理请求且发送端口目标始终可以访问，则应将这两个值都设置为 1。  
  
 若要更改重试值，请转到[如何配置传输高级选项的发送端口](http://go.microsoft.com/fwlink/p/?LinkID=267697)。  
  
 有关“按序送达”的详细信息，请参阅以下资源：  
  
 [BizTalk： 端到端按序消息处理选项](http://social.technet.microsoft.com/wiki/contents/articles/12887.biztalk-end-to-end-ordered-message-processing-options.aspx)  
  
 [BizTalk： 按序的送达](http://social.technet.microsoft.com/wiki/contents/articles/6681.biztalk-ordered-delivery.aspx)  
  
## <a name="see-also"></a>请参阅  
 [按序送达消息使用 MSMQ 适配器](../core/ordered-delivery-of-messages-with-the-msmq-adapter.md)   
 [使用 MQSeries 适配器按序送达消息](../core/ordered-delivery-of-messages-with-the-mqseries-adapter.md)