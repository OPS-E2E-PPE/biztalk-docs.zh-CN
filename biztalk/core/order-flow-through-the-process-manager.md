---
title: "顺序流通过进程管理器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: e2b51eff-44b5-440f-a7d1-0872543e5f27
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8556bce43ba4a951d0045d22f76d4bd222fcd8f2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="order-flow-through-the-process-manager"></a>顺序流通过进程管理器
本部分介绍如何南广视频订购过程管理器， **OrderManager**业务流程、 进程订单。 本部分将跟踪一份新订单在业务流程中的处理过程。 本部分还讨论了业务流程如何处理对订单的更新。  
  
> [!NOTE]
>  业务流程管理器解决方案只包含一个流程管理器，尽管该解决方案已编写为可以使用多种类型的管理器。  
  
 **OrderManager** orchestration 协调实现业务流程来处理顺序的从属业务流程。 **OrderManager**发送的顺序通过两个阶段，结合使用，验证订单、 将信息发送到设备组、 将顺序发送到通过远程处理组件订单系统和更新的订单历史记录。 你可以添加、 删除或修改这些阶段，而无需更改**OrderManager**。  
  
> [!NOTE]
>  由于的大小和作用域**OrderManager**业务流程，你可能想要阅读此部分与 Microsoft Visual Studio 中打开业务流程。  
  
## <a name="order-manager-structure"></a>顺序 Manager 结构  
 **OrderManager** orchestration 开头激活业务流程的接收形状。 下图显示的一般结构**OrderManager**业务流程。  
  
 ![阻止关系图的顺序管理器](../core/media/ordermanagerblockdiagram.gif "OrderManagerBlockDiagram")  
  
 第一个接收形状将通向两个主要分支。 一个分支（右侧的分支）用于处理新订单。 而左侧的分支则处理订单取消。 它接受用户输入，因为它有可能**OrderManager**已完成订单后接收的顺序取消。 这就是左侧主要分支所要处理的情况。 该分支通过设置用于终止处理操作的标志以及向事件日志添加警告，来处理单个取消。 业务流程将处理正在右侧分支内处理订单时到达的订单取消。  
  
 订单处理分支执行某种初始化操作，然后进入两个嵌套的循环。 外部循环对订单处理中的每个阶段都会运行一次。 而内部循环则在阶段正进行时运行。 订单管理器还将侦听内部循环中对订单的可能更新。 循环终止之后，订单管理器将发送完成消息。  
  
 订单处理阶段使用动态、 自助关联的端口进行通信回**OrderManager**业务流程。 这简化了相关的**OrderManager**与阶段实例，因为它不需要使用相关集。 有关自相关端口的详细信息，请参阅[端口绑定](../core/port-bindings.md)。  
  
## <a name="receiving-orders"></a>接收订单  
 **OrderManager**接收订单消息从**OrderBroker**通过 orchestration **FromBrokerPort**端口。 此端口是直接绑定到 MessageBox 数据库。 业务流程具有两个**接收**形状连接到端口： 一个用于新订单，另一个用于更新订单。  
  
 **OrderManger**确定哪些消息根据筛选器表达式的过程。 筛选表达式消息状态字段和顺序管理器类型字段中，在测试值**OrderMgrType**。 如果状态字段值等于已接受，和**OrderMgrType**是 CABLEORDER，顺序是新的和计划用于此进程管理器。  
  
 新订单将激活新的业务流程实例。 **OrderManager**下一步检查的类型中的请求**决策**形状。 如果该类型为“终止”，则业务流程将执行左侧分支，并终止订单。 否则，业务流程将继续处理该订单。 请注意，这包括侦听与此特定订单相关的随后的消息。  
  
## <a name="initialization-for-new-orders"></a>初始化的新订单  
 后**OrderManager** orchestration 接收初始消息，并开始主右侧分支时，它获取其配置信息**SSOConfigStore**。 这是通过单一实例对象中定义**实用工具**程序集。 配置值都是该对象的属性。 对象管理的配置值类似于面向服务的体系结构解决方案的本地缓存。 有关单一实例对象的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。  
  
 面向服务的解决方案，业务流程管理解决方案使用密钥存储，因为它是每次安装 BizTalk 时，存在类似 SSO 缓存的配置信息，以便值尚不可用，并且它可以保护数据库连接字符串和密码等信息。 对于所有这些原因，机密存储将是一个好的配置信息，即使上单一登录没有用于管理连接到后端应用程序。  
  
> [!NOTE]
>  业务流程在开始处理前将检索配置信息。 这可确保业务流程在冻结并随后解冻后，仍然使用同一配置。 有关冻结的详细信息，请参阅[Orchestration 冻结和 Rehydration](../core/orchestration-dehydration-and-rehydration.md)。  
  
 顺序管理器使用从配置数据的一个值： **TotalStages**，处理过程的顺序中的各个阶段的总数。 管理器将此值分配给局部变量， **numStages**。 它还将设置连接到外部循环中，两个多个变量**阶段**和**停止**。 **阶段**表示的当前阶段，它是外部循环; 的计数器**停止**停止值。  
  
 最后，该管理器设置**orderStatus**变量已启动并进入外部处理循环。  
  
## <a name="new-order-processing-loops"></a>新的顺序处理循环  
 外部循环的值作为长时间运行**阶段**变量小于的值**numStages**变量。 外部循环驱动器的每个阶段的处理。 内部循环运行处理程序，但前提是仍在处理某一阶段。 它还会侦听顺序可能发生的更改。  
  
### <a name="outer-loop"></a>外部循环  
 业务流程首先外部循环分配收到的消息 (**NewOrderMgrMsg**) 给一个变量， **OrderMgrMsg**。 然后，它将阶段和状态复制到消息的路由部分。 业务流程还设置寄信人地址的地址将邮件中**StageCompletionPort**:  
  
```  
OrderMgrMsg.RoutingPart.OrderMgrReturnAddress =   
       StageCompletionPort(Microsoft.XLANGs.BaseTypes.Address);  
```  
  
 然后，业务流程将发送到的顺序**StagePort**，请求-响应端口。 随后，业务流程将等待来自已启动订单处理的阶段的确认。 阶段发送**OrderAck**消息启动处理订单时。  
  
> [!NOTE]
>  **OrderAck**消息是由.NET 类，而不是架构解决方案中的多个之一。 有关使用.NET 类来定义消息的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
 当业务流程收到确认时，它将分配到阶段**currentStage**变量，并输入内部循环。  
  
### <a name="inner-loop"></a>内部循环  
 内部循环将一直运行长达**currentStage**变量等于**阶段**变量; 即，只要正在处理的当前阶段。 循环的正文是**侦听**有三个形状**接收**形状。 业务流程中的最左侧形状**顺序请求**，是在下一部分中所述的顺序更新机制的一部分。  
  
 当一个订单处理阶段完成的情况下，它将消息发送到**StageCompletion**端口**OrderManager**业务流程。 如果由于错误突然终止阶段，则将发送**TerminatedMessage**。 在这种情况下， **OrderManager**引发异常。 最外面的异常处理程序捕捉异常并将发送到错误消息**OperatorPort**。  
  
 如果阶段发送**OrderMgrMsg**、 **OrderManager**增量**阶段**变量。 如果有多个阶段 （阶段小于或等于到 numStages），业务流程设置订单状态**OrderMgrMsg**到 STAGE_n_COMPLETED 其中 n 是数的当前阶段。 如果没有其他阶段，则业务流程将订单状态设置为 COMPLETED，并退出这两个循环。  
  
## <a name="order-updates"></a>订单更新  
 **OrderManager** orchestration 侦听的内部处理循环内的订单更新。 请注意，**接收**调整该为此，使用**OrderRequest**，还使用**FromBrokerPort**。 如果在循环中同一端口上使用第二个接收形状，并将其与相关集进行组合，则会形成通用 BizTalk Server 模式：保护模式。 使用保护模式可确保同一业务流程实例处理与特定操作连接的第一条及其后续消息。  
  
 在订单管理器收到连接到订单的第一条消息后，它将初始化两个相关集。 首先， **OrderCorrelation**，使用客户 ID (**CustID**) 和订单 ID (**OrderID**)。 订单管理器与订单处理阶段共享此相关。 第二个相关是队列相关**OrderConvoyCorrelation**，它使用订单状态 (**状态**) 除了客户 ID 和订单 id。 **OrderRequestReceive**调整使用**OrderConvoyCorrelation**作为以下相关设置。 按此方式设置相关集可确保处理特定订单的订单管理器实例能够接收任何更改。  
  
> [!NOTE]
>  请回忆一下，相关集是用于确定消息是否属于给定业务流程实例的消息属性的分组。 有关详细信息，请参阅[在业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。  
  
 当**OrderManager**接收后续消息的订单时，它首先测试的请求的类型。 如果请求类型为 TERMINATE，则决策形状将执行终止分支。 否则，业务流程将测试新消息，以查看它是否是更新消息。 更新消息具有更高版本的序列号 (**SeqNum**) 与原始请求。 如果新消息的序列号更高，则业务流程将对新消息启动订单处理。 如果原始消息和更新消息具有相同或更低的序列号，则说明存在序列错误。 如果序列号相等，则更新消息为重复订单，并将标记为重复错误。  
  
 有关详细信息**SeqNum**，请参阅[密钥消息和字段](../core/key-messages-and-fields.md)。  
  
## <a name="final-steps"></a>最后的步骤  
 退出循环之后, 的顺序管理器将的答复地址分配给了动态端口**CSRCompletionPort**。 然后，管理器将构造完成状态消息，并发送该消息，然后测试是否存在错误。 若有错误，则业务流程将执行终止形状；否则，将正常结束。  
  
## <a name="coordinating-with-the-stages"></a>与阶段协作  
 这两个**OrderBroker**业务流程和第二个处理阶段业务流程 (**CableOrder2**) 历史记录数据库中创建条目。 CableOrder2 业务流程更新输入的历史记录信息**OrderBroker**业务流程。 为了确保在要更新的数据库中没有条目**OrderBroker**使用它的数据库使用的端口上传递通知。  
  
 配置映射**OrderBroker**将历史记录数据库的端口发送到包含两个端口的发送端口组-一个用于测试配置端口 (**HistoryInsert 测试 SP**)，一个用于常规配置 (**HistoryInsert SP**)。 如果将该组中的两个端口都保持活动状态，则解决方案将同时向这两个端口发送消息。 因而，该解决方案将请求两个送达通知，但仅处理其中一个通知。  
  
 若要避免这种情况下，取消登记测试端口 (**HistoryInsert 测试 SP**)，或停止应用程序的测试版本。 有关传递通知的详细信息，请参阅[使用确认](../core/using-acknowledgments.md)。  
  
## <a name="errors-and-routing-repaired-messagesdesign-choices"></a>错误和路由修复消息 — 设计选择  
 异常处理程序业务流程和业务流程由订单处理阶段使用一个错误处理业务流程 (**ErrorHandlerOrch**) 路由修复错误订单。 在设计中，假设有一个部门或组需要以所需格式修复订单。 不通过顺序 broker 业务流程已重新提交的修复后的顺序 (**OrderBroker**)。 而是将规范化的订单以其规范化格式进行修复。 当前设计的解决方案具有处理程序业务流程，该业务流程可以将错误消息路由回原始订单的源。 但是，修复的订单必须路由到错误处理程序业务流程上的 MSMQ 端口。 （解决方案的测试版本使用文件夹。）然后，错误处理程序将修复的消息返回到发起调用的业务流程。  
  
 此解决方案之所以使用该设计是因为 OrderBroker 会对订单消息进行重要验证和规范化。 从而，需要修复的订单消息也会采用规范化格式。 如果保持消息的规范化格式，则无需处理消息的已提交格式与规范化格式之间的差异问题。  
  
## <a name="see-also"></a>另请参阅  
 [过程管理器逻辑](../core/process-manager-logic.md)   
 [关键信息和字段](../core/key-messages-and-fields.md)