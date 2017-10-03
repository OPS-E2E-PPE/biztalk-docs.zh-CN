---
title: "从 MSMQT 适配器迁移到 MSMQ 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 2015-12-07
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance, MSMQT adapters
- scaling, MSMQT adapters
- reliability, MSMQT adapters
- MSMQT adapters, transactional consistency
- migrating, MSMQT adapters
- MSMQT adapters, ordered delivery
- MSMQT adapters, migrating to MSMQ adapters
- MSMQT adapters, scaling
- MSMQT adapters, reliability
- MSMQ adapters, migrating MSMQT adapters
- high availability, MSMQT adapters
- MSMQT adapters, performance
- MSMQT adapters, availability
ms.assetid: 97126f70-0be5-4a2f-bcba-173fd932b6de
caps.latest.revision: "30"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b1fce448788a8c6c5721403dbb7e4e58609a31a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="migrating-from-the-msmqt-adapter-to-the-msmq-adapter"></a>从 MSMQT 适配器迁移到 MSMQ 适配器
本主题讨论在将解决方案从 BizTalk 消息队列 (MSMQT) 适配器迁移到消息队列 (MSMQ) 适配器之前，在端对端按序送达、事务一致性、高可用性以及可伸缩性等方面的注意事项。 在本主题中，按序送达、事务一致性、高可用性以及可伸缩性的定义如下：  
  
-   **有序的传递。** 确保消息按照接收时的顺序从 BizTalk Server 发出。  
  
-   **事务一致性。** 确保消息在处理过程中不会由于硬件、软件或网络故障而丢失或重复。  
  
-   **高可用性。** 确保用于处理消息的服务随时可用于执行处理任务。  
  
-   **可伸缩性。** 可提高现有消息处理能力的功能。  
  
## <a name="end-to-end-ordered-delivery"></a>端到端的传递顺序  
 MSMQT 适配器可确保消息的端对端按序送达。 这意味着，如果一个 MSMQ 应用程序将 1、 2 和 3 的消息发送到绑定到 MSMQT 适配器接收位置，然后这些消息传递到业务流程或发送端口 BizTalk Server 中的相同顺序： 1、 2、 3。 此功能的一项应用可能包括股票市场交易，这些交易必须以与接收它们的顺序相同的顺序提交和执行。  
  
 MSMQT 的端对端按序送达需要将多个组件协同使用。 以下一系列事件阐释了 MSMQT 适配器是如何实现此功能的：  
  
1.  MSMQ API 远程计算机上按顺序接收消息 1、 2 和 3，并将它们推送至事务的本地队列中的相同顺序： 1、 2、 3。  
  
2.  在远程计算机上的 MSMQ 客户端将从队列的消息，并将其发送到 MSMQT 队列按顺序： 1、 2、 3。  
  
3.  MSMQT 适配器接收的消息按顺序 1，2，3，并将其传递到相同的顺序中的 BizTalk MessageAgent 组件： 1、 2、 3。  
  
4.  BizTalk MessageAgent 组件可确保消息将发送到按顺序 MessageBox: 1、 2、 3。  
  
5.  MessageBox 将消息路由，并确保它们路由到同一实例的业务流程或发送端口，如果它们传递到此实例的相同顺序： 1、 2、 3。  
  
 在[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]，MSMQT 是端到，从而保证的支持的唯一适配器有序传送的结束。 集成的其他所有 BizTalk 适配器都可能会在上面所列的步骤 3 到 5 中更改消息的顺序。 集成的其他大多数适配器都通过使用称为“端点管理器”的组件来完成步骤 3，该组件本身为多线程组件，因此不会保留顺序。 [!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)] 的 MSMQ 适配器可使用“串行处理”功能保留步骤 3 中的顺序，但是随后它并不会要求 MessageAgent 保留传输顺序，因此消息在路由到业务流程或发送端口时顺序可能会被打乱。  
  
 **端到端与 MSMQ 适配器的传递顺序**  
  
 若要实现端到端的传递顺序与 MSMQ 适配器，请按照下列步骤：  
  
1.  启用**按序送达**属性接收端口用于订阅的业务流程或发送端口。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]在业务流程中接收端口和发送端口都具有**按序送达**配置选项。 如果启用了此选项，则业务流程接收端口或发送端口将要求 MessageBox 按照消息的提交顺序向其传送消息。  
  
2.  设置**排序处理**属性绑定到 MSMQ 适配器接收位置`True`。 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 接收位置使用 MSMQ 传输可以配置为使用排序处理，如果启用，可以确保消息被发送到它们已接收的相同顺序 MessageBox。  
  
3.  设置**事务**属性绑定到 MSMQ 适配器接收位置`True`。  
  
4.  确保将 MSMQ 接收位置监视的所有 MSMQ 队列标记为“事务性”。 必须对队列设置此属性以确保消息的按序送达。  
  
> [!NOTE]
>  只有当 BizTalk 接收位置监视的 MSMQ 队列仅由一台计算机提供支持时，才可确保按序送达。 这可能会在可伸缩性方面产生问题，在下文中将对此进行说明。  
  
## <a name="transaction-usage-when-processing-messages-with-the-msmqt-adapter-vs-the-msmq-adapter"></a>使用 MSMQT 适配器处理消息与使用 MSMQ 适配器处理消息时的事务使用比较  
 在事务使用方面，MSMQT 和 MSMQ 适配器在处理消息的方式上有重要差异。  
  
 在使用 MSMQT 适配器时，从网络接收消息并使用 BizTalk Server 对其进行处理的过程是在单个事务中进行处理的。 在使用 MSMQT 适配器时，为发件人生成的 ACK 消息表示消息已被接收并已被 BizTalk Server 成功处理。  
  
 在使用 MSMQ 适配器时，从网络接收消息并使用 BizTalk Server 对其进行处理的过程在两个单独的事务中进行处理，一个负责从网络接收消息，而另一个负责使用 BizTalk Server 对消息进行处理。 在使用 MSMQ 适配器时，为发件人生成的 ACK 消息仅表示消息已被成功地从网络接收，并不表示该消息已被 BizTalk Server 成功处理。 当从网络接收消息并将该消息保存到本地 MSMQ 队列之后，无论是否安装了 BizTalk Server，发件人都会从 Microsoft 消息队列服务器接收到一个 ACK。 在将消息保存到 MSMQ 队列之后，BizTalk MSMQ 适配器将提取该消息，并对其进行处理，然后将其发布到 MessageBox。 如果此过程失败，消息将发送到 BizTalk 挂起队列或保留在本地 MSMQ 队列（当使用事务性处理）中，并且发件人不会收到该消息在 BizTalk Server 中处理失败的提示。  
  
 从 MSMQT 适配器迁移到 MSMQ 适配器时，如果您的结构要求您在 BizTalk Server 成功处理消息之后收到 ACK，则必须添加应用程序级别的 ACK。 您需要更新您的业务流程和发送应用程序以实现应用程序级别的 ACK。  
  
## <a name="high-availability-transactional-in-order"></a>高可用性（事务性，按顺序）  
 若要为 MSMQT 适配器提供高可用性你可以将多台计算机添加到接收主机和网络负载平衡 (NLB) 配置容错或可以群集默认 BizTalk 主机。 如果在运行 MSMQT 适配器时使用 NLB，当一台服务器出现故障时，其他服务器将处理负载。 如果在群集主机中运行 MSMQT 适配器处理程序，当一个主机节点出现故障时，群集软件将把该群集主机切换到其他节点。 在使用 MSMQ 适配器时，由于 MSMQ 适配器使用本地 MSMQ 队列用于中间存储，因此，如果需要没有数据损失的事务性处理，NLB 将无法工作。 在这种情况下，如果消息已送达本地 MSMQ 队列，但尚未被 MSMQ 适配器使用，则当计算机出现故障时该消息将丢失。  
  
 若要与 MSMQ 适配器提供高可用性和事务一致性，应执行以下操作：  
  
1.  在 BizTalk 服务器上，将 Microsoft 消息队列 (MSMQ) 配置为 Windows Server 群集组中的群集资源。  
  
2.  在已配置为群集 MSMQ 资源所在群集组中的群集资源的 BizTalk 主机实例中，配置 MSMQ 适配器接收处理程序。  
  
3.  为 BizTalk 主机实例配置群集资源以便其维护对群集 MSMQ 资源的依存关系。  
  
 若要实现此体系结构使用的有序的传递，请按照下"端到端的传递顺序与 MSMQ 适配器。"前面提供的步骤  
  
## <a name="high-availability-nontransactional-not-in-order"></a>高可用性（非事务性，不按顺序）  
 如果需要高可用性，但不需要事务性处理，则可以通过实现 NLB 并在 NLB 后的多个 BizTalk 服务器上运行配置有 MSMQ 发送和接收处理程序的主机实例，使用 MSMQ 适配器实现此目的。 实现与 MSMQ NLB 时你应遵循最佳做法，如 Microsoft 知识库文章 899611 中, 所述"如何消息队列客户端可通过网络负载平衡 (NLB)"在可用[http://go.microsoft.com/fwlink/?LinkId = 57510](http://go.microsoft.com/fwlink/?LinkId=57510)。 在这种情况下，如果一台 BizTalk 服务器出现故障，在该 BizTalk 服务器恢复之前，在该 BizTalk 服务器上的主机实例中运行的消息将不可用。 由于当一台 BizTalk 服务器不可用时，NLB 会将请求路由至其他 BizTalk 服务器，因此该配置可提供高可用性。  
  
## <a name="scalability-nontransactional-not-in-order"></a>可伸缩性（非事务性，不按顺序）  
 通过遵循高可用性（非事务性）准则并添加其他主机实例，可以实现可伸缩性。 此结构提供了快速送达以及可伸缩性，但是不提供按序送达。  
  
## <a name="scalability-transactional-not-in-order"></a>可伸缩性（事务性，不按顺序）  
 对于非按序送达的事务性消息送达，可以将使用 MSMQ 的 NLB 与 Windows 群集组合使用。 此结构要求您按照“高可用性（事务性，按顺序）”中的步骤，在两个单独的 Windows 群集环境中为每个 Windows 群集至少配置两个群集组。 随后即可实现 NLB 以在群集组之间分布负载。 由于 Windows NLB 不支持在 Windows 群集上运行，在这种情况下，需要使用硬件 NLB 解决方案。 下图对此结构进行了说明：  
  
 ![负载平衡群集组之间](../core/media/scaleclusteredmsmqwithnlb.gif "ScaleClusteredMSMQwithNLB")  
  
> [!NOTE]
>  此结构不提供按序送达。  
  
## <a name="scalability-transactional-in-order"></a>可伸缩性（事务性，按顺序）  
 使用 MSMQ 3.0 或早期版本时，因为不支持远程事务性读取，所以对提供高可用性、事务一致性以及按序送达的结构进行扩展将会有问题（除非 BizTalk Server 计算机和远程 MSMQ 服务器都运行 MSMQ 4.0）。 当使用 MSMQ 3.0 或早期版本时，必须使用多个本地 MSMQ 队列才能进行扩展。 而且，在这种情况下，如果用于与 NLB 进行 MSMQ 会话的 TCP/IP 连接中断，该连接可被 NLB 随后还原到另一台计算机上，这会导致送达顺序紊乱。  
  
 针对此限制的一种可能的解决办法是：通过将目标队列分配到不同的计算机手动进行消息送达的负载平衡。 通过尝试将特定的 BizTalk 主机实例分配给特定的 MSMQ 队列可实现此目的。 因此，例如，如果从特定的贸易合作伙伴接收大量文档，请在特定的 BizTalk 服务器上为该贸易合作伙伴创建单独的主机和接收队列。  
  
 如果可能，请在要求远程事务性读取和负载平衡时在远程计算机上运行 MSMQ 4.0。  
  
## <a name="summary"></a>摘要  
 下表概括列出了可用来实现特定功能的结构：  
  
|**功能**|**NLB 和群集都不**|**NLB**|**Cluster**|**NLB 和群集**|  
|-----------------------|---------------------------------|-------------|-----------------|-------------------------|  
|端对端按序送达|是|“否”|是|可通过手动配置实现|  
|事务一致性|否（如果出现服务故障，消息可能会丢失或重复）|是|是|是|  
|高度可用|是|是|是|是|  
|可伸缩|是|是|“否”|是|  
  
## <a name="see-also"></a>另请参阅  
 [Windows Server 群集用于 BizTalk Server Hosts2 为提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)