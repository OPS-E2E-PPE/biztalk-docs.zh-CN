---
title: 使用失败消息路由 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.ops.tsroutingfailure
ms.assetid: d081934c-600e-44ce-8ba4-fb646d494589
caps.latest.revision: 33
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5c3f4fa3b978775c9f2c8fa91467b88cc74eae8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976566"
---
# <a name="using-failed-message-routing"></a>使用失败消息路由
使用错误处理功能，设计者可以指定对消息传送失败进行自动处理，以此作为将失败消息放在挂起队列中的传统（现在是默认）行为的替换选择。 此自动处理方式会将错误消息路由到任何订阅路由目标（例如发送端口或业务流程）。 错误消息是原始消息的克隆，其中以前升级的所有属性将降级，与特定消息传送失败相关的所选属性将升级到消息上下文。  
  
> [!WARNING]
>  失败消息包含原始消息的副本。 如果原始消息包含敏感信息，则应当设计手动和自动失败消息处理，以避免意外泄漏这些信息。  
  
## <a name="what-does-failed-message-routing-consist-of"></a>失败消息路由由哪些部分组成？  
 启用失败消息路由后，BizTalk Server 不会挂起消息，而是路由消息。 可以在接收端口和发送端口上都启用失败消息路由，其结果如下：  
  
- 如果在接收端口上启用失败消息路由，并且消息在接收管道或路由中失败，则会生成失败消息。 在拆装阶段中或拆装阶段之前出现错误的情况下，错误消息是原始交换的克隆。  
  
- 如果在发送端口上启用失败消息路由，并且消息在发送管道中失败，则会生成失败消息。  
  
  生成失败消息时，BizTalk Server 会在发布失败消息之前将与错误报告相关的消息上下文属性升级，并将常规消息上下文属性降级。 未启用失败的消息时，与默认行为相比较：失败的邮件都将挂起。  
  
## <a name="what-kinds-of-messaging-failures-trigger-an-error-message"></a>有哪些种类的消息失败会触发错误消息？  
 如果启用了对失败消息的路由，则在适配器处理、管道处理、映射或消息路由过程中所发生的任何故障都将导致错误消息。 如果从接收端口接收或向发送端口发送业务流程时出现了消息传送错误，则生成的错误消息将与业务流程所绑定的消息端口关联。  
  
## <a name="subscribing-to-an-error-message"></a>订阅错误消息  
 错误消息将传送到已订阅接收它们的业务流程或发送端口。 通常，订阅基于出现消息传送错误的端口（发送端口或接收端口）的名称来选择错误消息。 订阅还可能对升级到错误消息上下文的其他属性（例如， **InboundTransportLocation** 或 **FailureCode**）进行筛选。  
  
## <a name="error-message-specification"></a>错误消息规范  
 错误消息是原始失败消息的克隆，其中以前升级的所有属性将降级，一组特定于错误的属性将升级到消息上下文。 以前升级的属性降级是为了避免非有意地将其传送给未指定接收错误消息的订户。 发布错误消息以分发给订户（业务流程、发送端口和发送端口组）。  
  
 升级到的所有这些都包含在下一条错误消息上下文属性**ErrorReport** BizTalk Server 中的命名空间。 这些属性包括：  
  
|属性名称|数据类型|已升级|Description|  
|-------------------|---------------|--------------|-----------------|  
|FailureCode|System.String|是|错误代码。 十六进制值，在 BizTalk Server 管理控制台中报告该值。|  
|FailureCategory|System.Int32|是|不使用此属性。 未定义其值。|  
|Description|System.String|“否”|错误说明。 与写入应用程序事件日志中的内容相同的诊断文本，提供有关此消息传送失败的信息。|  
|MessageType|System.String|是|失败消息的消息类型，如果消息类型不确定则为空。<br /><br /> BizTalk Server 使用消息类型将消息与其 XML 架构相关联。 消息类型通过连接架构命名空间和架构根节点形成： http://mynamespace#rootnode。 **注意：** 消息失败之前确定其消息类型不具有此属性设置。|  
|ReceivePortName|System.String|如果失败发生在入站处理期间（在接收端口中），则为“已升级” 。<br /><br /> 如果在发生端口发生失败，则为“未升级” 。|发生失败的接收端口的名称。|  
|InboundTransportLocation|System.String|如果失败发生在入站处理期间（在接收端口中），则为“已升级” 。<br /><br /> 如果在发生端口发生失败，则为“未升级” 。|发生失败的接收位置的 URI。|  
|SendPortName|System.String|如果失败发生在出站处理期间（在发送端口中），则为“已升级” 。<br /><br /> 如果失败发生在接收端口中，则为“未升级” 。|发生失败的发送端口的名称。|  
|OutboundTransportLocation|System.String|如果失败发生在出站处理期间（在发送端口中），则为“已升级” 。<br /><br /> 如果失败发生在接收端口中，则为“未升级” 。|发生失败的发送位置的 URI。|  
|ErrorType|System.String|是|指示错误包含的消息的类型。 此属性始终包含值 **FailedMessage**，表示错误包含原始的失败消息。|  
|RoutingFailureReportID|System.String|是|存在路由故障时，此属性提供 BizTalk Server 生成的路由故障报告的 ID。 路由故障报告是由 BizTalk Server 生成和挂起的特殊消息。 此消息没有正文，但它具有失败消息的上下文。 使用此 ID，错误处理业务流程或发送端口可以查询 MessageBox 数据库并处理路由故障报告。 例如，业务流程在获取失败消息之后可能要终止路由故障报告。|  
  
## <a name="handling-error-messages"></a>处理错误消息  
 错误处理由其筛选器与已升级到错误消息的消息上下文的属性匹配的业务流程或发送端口订阅指定。  
  
## <a name="security-implications"></a>安全含义  
 将与原始消息关联的标识（它的初始标识或它的最后标识，由接收管道的解析参与方阶段确定）分配给错误消息。  
  
 限制消息只能传送给授权的订阅端口和业务流程的安全机制也应用于错误消息。  
  
 对于订阅错误消息但未使用适当的解密证书进行配置的发送端口，不会收到在接收管道（原始消息通过其进入 BizTalk Server）解密阶段之内或之前基于消息传送失败产生的错误消息。 而失败消息将放置在挂起队列中。  
  
## <a name="adapter-messaging-failure"></a>适配器消息传送失败  
 如果适配器挂起消息，则会发布错误消息。 如果消息未挂起，则不会生成错误消息。  
  
## <a name="transactional-receive-pipelines"></a>事务性接收管道  
 如果事务性接收管道引发异常（指定事务应被中止），则事务将中止，并发布错误消息。  
  
 如果事务性接收管道显式挂起消息（指定 MessageDestination = SuspendQueue），则允许当前事务继续（并且可能被提交，除非随后的阶段指定将其中止），并且发布所生成的错误消息。  
  
## <a name="solicit-response-send-ports"></a>要求响应发送端口  
 如果从业务流程发送请求消息，而请求消息传输失败或其响应在入站处理时失败，则不管是否已经路由失败消息，业务流程都将获得异常。  
  
 在将要求响应发送端口连接到请求响应接收端口的情况下，不管是否已经路由失败消息，接收端口都将获得响应消息（如果传输成功）或 NACK（如果传输失败）。  
  
## <a name="one-way-send-ports"></a>单向发送端口  
 如果从业务流程通过配置送达通知的发送端口发送消息，则不管是否已经路由了错误消息，业务流程都将收到送达通知。 换句话说，即使端口在处理期间遇到消息传送失败，发送端口也将为业务流程生成送达通知。 通知会确认到端口的送达，但不会确保通过端口成功进行处理。  
  
## <a name="resuming-suspended-messages"></a>恢复挂起消息  
 大多数入站处理（即从接收适配器（包括）到发布到 MessageBox（不包括）的处理）失败并且其失败未处理的消息将会作为可恢复消息挂起。 例外情况是来自双向接收端口的请求消息将作为不可恢复消息挂起。  
  
 消息通常以其原始形式（管道处理之前的形式）挂起，但以下两种消息除外：  
  
-   **由管道组件挂起的消息。** BizTalk 服务器以将其提供给失败管道组件时的相同形式挂起此类消息。 恢复消息时，从同一管道的开始位置执行管道处理。 这意味着，对于在出现原始失败的阶段以前的管道阶段中的管道组件，它们必须准备以不同于原始形式（处理该消息的形式）的形式处理“相同”消息。  
  
-   **来自可恢复的消息的交换拆装随后路由失败。** BizTalk 服务器以其被发布时的相同形式挂起此类消息。 这是在管道执行 **之后** 消息所具有的形式。 消息恢复后，会跳过管道处理，直接发布到 MessageBox 数据库。  
  
## <a name="scenarios-leading-to-suspended-non-resumable-messages"></a>导致消息挂起（不可恢复）的情况  
 通常，挂起的消息是可恢复的，不过在某些情况下，也会导致不可恢复的消息：  
  
-   在允许在发生故障后仍继续的“按序送达”发送端口中，如果管道、映射或传输发生故障的情况下。  
  
-   在“按序送达”接收端口中，如果适配器配置为发生故障时以不可恢复的方式挂起消息的情况下。 例如，如果 MSMQ 适配器的“失败时”设置设为“已挂起(不可恢复)”或者 MQSeries 适配器启用了“挂起且不可恢复”，则失败的消息将作为不可恢复的消息被挂起。  
  
-   在双向接收端口中，如果管道、映射或传输中的响应消息失败的情况下。  
  
-   在双向接收端口中，如果管道、映射或传输中的接收消息失败的情况下。 不同的适配器可能有不同的行为。 例如，默认情况下 HTTP 适配器不会将消息挂起，但可以配置为将消息挂起。  
  
## <a name="see-also"></a>请参阅  
 [错误处理](../core/error-handling.md)   
 [使用确认](../core/using-acknowledgments.md)   
 [消息按序送达](../core/ordered-delivery-of-messages.md)