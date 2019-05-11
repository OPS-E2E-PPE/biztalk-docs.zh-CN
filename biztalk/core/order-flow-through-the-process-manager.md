---
title: 排序流通过进程管理器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, processing
- processing, processing logic
ms.assetid: e2b51eff-44b5-440f-a7d1-0872543e5f27
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c272f8b9aaf179a7d9db395a1ad1e884567c3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262903"
---
# <a name="order-flow-through-the-process-manager"></a>通过进程管理器的订单流
本部分介绍了如何 Southridge Video 订购流程管理器**OrderManager**业务流程、 进程订单。 本部分将跟踪新订单在业务流程。 部分还讨论了如何在业务流程处理对订单的更新。  
  
> [!NOTE]
>  业务流程管理器解决方案包含只有一个进程管理器，但它编写，以便它可以使用多个管理器的类型。  
  
 **OrderManager**业务流程协调实现业务流程要处理订单的从属业务流程。 **OrderManager**发送订单在两个阶段，结合使用，验证订单、 将信息发送到设备组，将订单发送到订单系统通过远程处理组件和更新的订单历史记录。 可以添加、 删除或修改这些阶段，而无需更改**OrderManager**。  
  
> [!NOTE]
>  由于大小和范围**OrderManager**业务流程中，你可能想要阅读此部分在 Microsoft Visual Studio 中打开该业务流程。  
  
## <a name="order-manager-structure"></a>订单管理器结构  
 **OrderManager**以激活该业务流程接收形状的业务流程开始。 下图显示了的一般结构**OrderManager**业务流程。  
  
 ![阻止关系图的订单管理器](../core/media/ordermanagerblockdiagram.gif "OrderManagerBlockDiagram")  
  
 第一个接收形状将通向两个主要分支。 一个分支，适合用于处理新订单。 左的分支，处理订单取消。 由于它接受用户输入，因此很可能**OrderManager**已经完成订单后接收到订单取消。 这种情况左侧主要分支所要处理。 通过设置用于终止处理标志以及向事件日志中添加一条警告，分支处理单个的取消。 业务流程将处理正在右侧分支内处理订单时到达的订单取消。  
  
 订单处理分支执行某种初始化，然后进入两个嵌套的循环。 外部循环对订单处理中的每个阶段运行一次。 内部循环运行的同时，处理阶段。 订单管理器还侦听内部循环中的顺序可能更新。 循环终止后，订单管理器将发送一条完成消息。  
  
 订单处理阶段使用动态、 自相关端口要发送回**OrderManager**业务流程。 这简化了的相关性**OrderManager**与阶段实例，因为它不需要使用相关集。 有关自相关端口的详细信息，请参阅[端口绑定](../core/port-bindings.md)。  
  
## <a name="receiving-orders"></a>接收订单  
 **OrderManager**接收从订单消息**OrderBroker**业务流程通过**FromBrokerPort**端口。 此端口直接绑定到 MessageBox 数据库。 业务流程具有两个**接收**形状连接到端口： 一个用于新订单，一个用于更新订单。  
  
 **OrderManger**确定哪些消息根据筛选器表达式的过程。 筛选器表达式中的消息状态字段和订单管理器类型字段中，测试的值**OrderMgrType**。 如果状态字段等于已接受，并**OrderMgrType**是 CABLEORDER，顺序是新的专门为此进程管理器。  
  
 新的订单将激活业务流程的新实例。 **OrderManager**接下来将检查请求的类型**决策**形状。 如果类型为 Terminate，业务流程将执行左侧分支，并终止订单。 否则，业务流程将继续进行处理订单。 请注意，这包括侦听与此特定订单相关的后续消息。  
  
## <a name="initialization-for-new-orders"></a>初始化新的订单  
 之后**OrderManager**业务流程接收初始消息，并开始主右侧分支，它将获取从其配置信息**SSOConfigStore**。 这是通过单一对象中定义**实用程序**程序集。 配置值是该对象的属性。 对象管理的配置值类似于面向服务的体系结构解决方案的本地缓存。 有关单一对象的详细信息，请参阅[业务流程管理解决方案中有效使用 SSO](../core/using-sso-efficiently-in-the-business-process-management-solution.md)。  
  
 像面向服务的解决方案，业务流程管理解决方案使用机密存储，因为存在每次安装 BizTalk，SSO 将缓存配置信息，以便值随时可用，并且它可以保护数据库连接字符串和密码等信息。 对于所有这些原因，密钥存储区将是一个好的配置信息，即使上单一登录不用于管理指向后端应用程序的连接。  
  
> [!NOTE]
>  业务流程检索开始处理前的配置信息。 这可确保该业务流程使用相同的配置，如果它是冻结和更高版本，解除冻结。 有关冻结的详细信息，请参阅[业务流程冻结和解除冻结](../core/orchestration-dehydration-and-rehydration.md)。  
  
 订单管理器使用的配置数据中的某个值：**即 TotalStages**，订单处理过程中的各个阶段的总数。 该管理器将此值分配给本地变量**numStages**。 它还将设置连接到外部循环中，两个变量**阶段**并**停止**。 **阶段**表示的当前阶段，它是外部循环; 的计数器**停止**停止值。  
  
 最后，该管理器设置**orderStatus**变量已启动并进入的外部处理循环。  
  
## <a name="new-order-processing-loops"></a>新的顺序处理循环  
 外部循环的值长时间运行**阶段**变量小于的值**numStages**变量。 外部循环驱动每个阶段的处理。 内部循环运行，只要仍在处理一个阶段。 它还会侦听对订单可能发生的更改。  
  
### <a name="outer-loop"></a>外部循环  
 业务流程首先会对外部循环将接收到的消息 (**NewOrderMgrMsg**) 给一个变量**OrderMgrMsg**。 它然后将阶段和状态复制到消息的路由部分。 业务流程还将为地址的消息中设置的寄信人地址**StageCompletionPort**:  
  
```  
OrderMgrMsg.RoutingPart.OrderMgrReturnAddress =   
       StageCompletionPort(Microsoft.XLANGs.BaseTypes.Address);  
```  
  
 该业务流程将发送到订单**StagePort**，要求-响应端口。 该业务流程将等待来自阶段的确认订单处理已开始。 阶段发送**OrderAck**消息启动处理订单时。  
  
> [!NOTE]
>  **OrderAck**消息是由.NET 类而不是架构定义解决方案中的多个之一。 有关使用.NET 类来定义消息的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
 业务流程收到确认，它将分配到阶段**currentStage**变量并进入内部循环。  
  
### <a name="inner-loop"></a>内部循环  
 内部循环将一直运行，只要**currentStage**变量等于**阶段**变量; 也就是说，只要正在处理的当前阶段。 循环的正文**侦听**具有三个形状**接收**形状。 在业务流程，最左侧的形状**订单请求**，是下一节中所述的顺序更新机制的一部分。  
  
 当一个订单处理阶段完成，它将消息发送到**StageCompletion**端口**OrderManager**业务流程。 如果由于错误而突然终止阶段，则会发送**TerminatedMessage**。 在这种情况下， **OrderManager**将引发异常。 最外面的异常处理程序捕获异常并将发送到的错误消息**OperatorPort**。  
  
 如果阶段发送**OrderMgrMsg**，则**OrderManager**增量**阶段**变量。 如果有多个阶段 （阶段小于或等于到 numStages），业务流程设置订单状态**OrderMgrMsg**到 STAGE_n_COMPLETED 其中 n 是当前阶段的数字。 如果没有多个阶段，它将订单状态设置为 ' 已完成并退出这两个循环。  
  
## <a name="order-updates"></a>订单更新  
 **OrderManager**侦听在内部处理循环中的订单更新业务流程。 请注意，**接收**调整该为此，使用**OrderRequest**，还使用**FromBrokerPort**。 第二个接收形状在循环中，与相关集结合使用的同一端口上使用形成通用 BizTalk Server 模式，保护模式。 使用保护模式以确保业务流程的同一个实例处理与某一特定操作相关联的第一个和后续消息。  
  
 当订单管理器收到连接到订单的第一个消息时，它将初始化两个相关集。 第一种**OrderCorrelation**，使用客户 ID (**CustID**) 和订单 ID (**OrderID**)。 订单管理器与订单处理阶段共享此相关。 第二个相关是保护相关**OrderConvoyCorrelation**，它使用订单状态 (**状态**) 除了客户 ID 和订单 id。 **OrderRequestReceive**形状使用**OrderConvoyCorrelation**作为沿用相关集。 设置相关集这种方式可确保按特定顺序处理的订单管理器实例收到的任何更改。  
  
> [!NOTE]
>  回想一下，相关集是一组消息属性用于确定消息属于给定业务流程的实例。 有关详细信息，请参阅[业务流程中使用相关性](../core/using-correlations-in-orchestrations.md)。  
  
 当**OrderManager**接收后续消息的订单，它首先测试的请求的类型。 如果请求类型为 TERMINATE，决策形状将执行终止分支。 否则，业务流程测试要查看它是否是更新的新消息。 更新消息具有更高版本的序列号 (**SeqNum**) 比原始请求。 如果新消息的序列号更高，业务流程将启动订单处理新消息。 如果原始和更新消息具有相同或较低的序列号，则存在序列错误。 序列号相等，如果它是一个重复的订单，并标记为重复错误。  
  
 有关详细信息**SeqNum**，请参阅[键消息和字段](../core/key-messages-and-fields.md)。  
  
## <a name="final-steps"></a>最后的步骤  
 退出循环之后, 的订单管理器将回复地址分配给动态端口**CSRCompletionPort**。 该管理器，然后构造完成状态消息、 将它发送，然后测试是否存在错误。 如果出现错误，业务流程将执行终止形状;否则，它只是结束。  
  
## <a name="coordinating-with-the-stages"></a>阶段与协作  
 这两个**OrderBroker**业务流程和第二个处理阶段业务流程 (**CableOrder2**) 在历史记录数据库中生成条目。 CableOrder2 业务流程都会更新输入的历史记录信息**OrderBroker**业务流程。 为了确保有要更新，请在数据库中的条目**OrderBroker**上用于访问数据库的端口使用送达通知。  
  
 配置地图**OrderBroker**将历史记录数据库的端口发送到包含两个端口的发送端口组 — 一个用于测试配置端口 (**测试-HISTORYINSERT-SP**)，另一个用于常规配置 (**HISTORYINSERT-SP**)。 如果将这两个端口都在组中的保持活动，该解决方案在这两个端口上发送消息。 因此，请求两个送达通知，但仅处理其中一个。  
  
 若要避免这种情况下，取消登记测试端口 (**测试-HISTORYINSERT-SP**)，或停止应用程序的测试版本。 有关送达通知的详细信息，请参阅[使用确认](../core/using-acknowledgments.md)。  
  
## <a name="errors-and-routing-repaired-messagesdesign-choices"></a>错误和路由修复消息 — 设计方案  
 异常处理程序业务流程和业务流程使用订单处理阶段使用一个错误处理业务流程 (**ErrorHandlerOrch**) 路由错误修复的订单。 设计，假设有一个部门或组将在所需格式修复订单。 已修复的顺序不重新提交 orderbroker 业务流程通过 (**OrderBroker**)。 而是将规范化的订单被修复以其规范化格式。 当前解决方案的设计具有错误消息路由回原始订单的源的处理程序业务流程。 修复的订单，但是，必须将路由到错误处理程序业务流程上的 MSMQ 端口。 （测试版本的解决方案使用一个文件夹。）然后，错误处理程序将修复后的消息返回到调用业务流程。  
  
 此解决方案使用这种设计，因为 orderbroker 会进行重要验证和规范化订单消息。 反过来，需要修复的订单消息也是采用规范化格式。 保持消息的规范化的形式可避免无需解决的消息的已提交和规范化形式之间的差异。  
  
## <a name="see-also"></a>请参阅  
 [进程管理器逻辑](../core/process-manager-logic.md)   
 [主要消息和字段](../core/key-messages-and-fields.md)