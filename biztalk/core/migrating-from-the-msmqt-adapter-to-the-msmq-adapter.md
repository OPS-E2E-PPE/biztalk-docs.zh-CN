---
title: 从 MSMQT 适配器迁移到 MSMQ 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 12/07/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97126f70-0be5-4a2f-bcba-173fd932b6de
caps.latest.revision: 30
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 345247a39a3226d3e51b7c73f12be177adf01a3d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65324832"
---
# <a name="migrate-from-the-msmqt-adapter-to-the-msmq-adapter"></a>从 MSMQT 适配器迁移到 MSMQ 适配器
本主题讨论点需要注意的有关端到端按序送达、 事务一致性、 高可用性和可伸缩性迁移之前从 BizTalk 消息队列 (MSMQT) 适配器的消息队列 (MSMQ) 适配器的解决方案。 对于本主题按序送达，事务一致性、 高可用性和可伸缩性定义，如下所示：  
  
-   **按序的送达。** 保证消息发送出 BizTalk Server 接收时的顺序相同。  
  
-   **事务一致性。** 正在处理的消息不能保证而丢失或重复由于硬件、 软件或网络故障。  
  
-   **高可用性。** 保证服务用于处理消息始终可供处理。  
  
-   **可伸缩性。** 若要提高现有消息处理能力的功能。  
  
## <a name="end-to-end-ordered-delivery"></a>端到端按序送达  
 MSMQT 适配器可确保端到端按序的送达消息。 这意味着，如果 MSMQ 应用程序将消息 1、 2 和 3 发送到接收位置绑定到 MSMQT 适配器，则这些消息发送到业务流程或发送端口在 BizTalk Server 中的相同顺序：1, 2, 3. 此功能的一种用法可能包括股票市场交易，必须提交并按相同顺序接收时的执行。  
  
 MSMQT 的端到端按序送达需要多个组件协同工作。 以下一系列事件阐释了如何做到这一点与 MSMQT 适配器：  
  
1. 远程计算机上的 MSMQ API 按顺序接收消息 1、 2 和 3，并将其推送到相同的顺序中的事务的本地队列：1, 2, 3.  
  
2. 在远程计算机上的 MSMQ 客户端将消息从队列，并将其发送到 MSMQT 队列按顺序：1, 2, 3.  
  
3. MSMQT 适配器接收的消息按顺序 1，2，3，并将其传递到 BizTalk MessageAgent 组件的相同顺序：1, 2, 3.  
  
4. BizTalk MessageAgent 组件确保消息都发送到 MessageBox 中顺序：1, 2, 3.  
  
5. MessageBox 将消息路由，并确保其路由到同一实例的业务流程或发送端口，确保它们都已传递到此实例的相同顺序：1, 2, 3.  
  
   在 BizTalk Server 2004 中，MSMQT 是唯一的适配器能够确保端对端按序送达。 所有其他集成的 BizTalk 适配器可能可以更改与消息在步骤 3 至 5 上面列出的顺序。 大多数其他集成适配器完成通过使用组件，称为作为终结点管理器中，这是本质上是多线程，因此将不保留顺序的步骤 3。 使用"串行处理"功能保留步骤 3 中，为使 BizTalk Server 2004 MSMQ 适配器，但然后要求 MessageAgent 保留下来，因此可能被路由到业务流程或发送端口无序的消息的顺序。  
  
   **端到端使用 MSMQ 适配器按序送达**  
  
   若要实现端到端使用 MSMQ 适配器按序送达，请执行以下步骤：  
  
6. 启用**按序送达**属性的接收订阅业务流程的端口或发送端口。 在 BizTalk Server 中，接收业务流程中的端口和发送端口都具有**按序送达**配置选项。 如果启用此选项，然后业务流程接收端口或发送端口将要求 MessageBox，以向其提交到 MessageBox 的相同顺序传送消息。  
  
7. 设置**按序处理**绑定到 MSMQ 适配器的接收位置属性`True`。 在 BizTalk Server 接收位置使用 MSMQ 传输可以将配置为使用按序处理这样，如果启用，可以确保消息将发送到 MessageBox 中相同的顺序接收。  
  
8. 设置**事务性**绑定到 MSMQ 适配器的接收位置属性`True`。  
  
9. 确保所有 MSMQ 队列是受监视的 MSMQ 都接收位置标记为"事务性"。 此属性必须在队列上设置，以确保按序的送达消息。  
  
> [!NOTE]
>  按序的送达保证仅当 MSMQ 队列或队列是受监视的 BizTalk 接收位置是 / 由只有一台计算机提供服务。 这可以提供可伸缩性，遇到的问题，如下所述。  
  
## <a name="transaction-usage-when-processing-messages-with-the-msmqt-adapter-vs-the-msmq-adapter"></a>当使用 MSMQ 适配器与 MSMQT 适配器处理消息时使用的事务  
 事务使用方面是 MSMQT 和 MSMQ 适配器如何处理消息的主要区别。  
  
 使用 MSMQT 适配器时，在单个事务下处理从网络接收消息和处理与 BizTalk Server 的过程。 使用 MSMQT 适配器时，该发件人生成的 ACK 消息将是一种指示消息已收到并已由 BizTalk Server 成功处理。  
  
 使用 MSMQ 适配器时，将其与 BizTalk Server 中的网络和处理从接收一条消息的进程处理两个单独的事务，一个用于从网络接收，一个用于处理与 BizTalk Server。 使用 MSMQ 适配器，发件人为生成的 ACK 消息时，仅表示消息已成功接收来自网络，该消息已成功处理的 BizTalk Server 不。 从网络接收消息并将其保存到本地 MSMQ 队列之后，无论是否安装了 BizTalk Server 时，发件人从 Microsoft 消息队列服务器接收确认。 消息已保存到 MSMQ 队列之后，BizTalk MSMQ 适配器提取该消息、 处理它，并将其发布到 MessageBox。 如果此过程失败，消息是发送到 BizTalk 挂起队列或保留在本地 MSMQ 队列 （当使用事务处理），并且发件人具有不会指示消息在 BizTalk Server 中的处理失败。  
  
 如果您的体系结构需要被 BizTalk Server 成功处理消息时收到 Ack，则必须如果从 MSMQT 适配器迁移到 MSMQ 适配器添加应用程序级别的 Ack。 您需要更新你的业务流程和发送应用程序以实现应用程序级别的 Ack。  
  
## <a name="high-availability-transactional-in-order"></a>高可用性 （事务性，按顺序）  
 若要为 MSMQT 适配器提供高可用性可以向接收主机添加多台计算机，并为容错配置网络负载平衡 (NLB) 或在可以群集默认的 BizTalk 主机。 如果您使用 NLB，在运行 MSMQT 适配器，如果一台服务器出现故障的其他服务器处理的负载。 如果群集主机上运行 MSMQT 适配器处理程序，如果一个主机节点出现故障，群集软件将故障转移到另一个节点的群集主机。 使用 MSMQ 适配器时，NLB 将无法工作如果需要事务性处理，而无数据丢失因为 MSMQ 适配器使用本地 MSMQ 队列的中间存储。 在此方案中，如果消息已传送到本地 MSMQ 队列，但不是消耗了 MSMQ 适配器，消息将丢失如果计算机出现故障。  
  
 若要使用 MSMQ 适配器提供高可用性和事务一致性，应执行以下操作：  
  
1. 将 Microsoft 消息队列 (MSMQ) 配置为在 BizTalk server 上的 Windows Server 群集组中的群集资源。  
  
2. 配置 MSMQ 适配器接收处理程序已配置为群集 MSMQ 资源所在的群集组中的群集资源的 BizTalk 主机实例中。  
  
3. 配置 BizTalk 主机实例的群集资源，使它保持群集 MSMQ 资源上的依赖项。  
  
   若要实现这种体系结构的按序的送达，请按照前述"端到端使用 MSMQ 适配器按序送达。"的步骤  
  
## <a name="high-availability-nontransactional-not-in-order"></a>高可用性 （非事务性，不按顺序）  
 如果需要高可用性，但不是需要事务性处理，您可以使用 MSMQ 适配器实现此目的通过实现 NLB 并正在运行的实例的主机配置有 MSMQ 发送和接收 NLB 后的多个 BizTalk 服务器上的处理程序。 当使用 MSMQ 实现 NLB 时你应遵循最佳做法，如 Microsoft 知识库文章中所述[899611:消息队列如何函数通过网络负载平衡 (NLB)](https://support.microsoft.com/help/899611/how-message-queuing-can-function-over-network-load-balancing-nlb)。 在此方案中，如果 BizTalk 服务器出现故障时，将恢复中的主机实例运行的 BizTalk server 将不可用之前的 BizTalk server 的消息。 此配置提供高可用性，因为如果其中一台 BizTalk 服务器不可用，NLB 会将请求路由到其他 BizTalk 服务器。  
  
## <a name="scalability-nontransactional-not-in-order"></a>可伸缩性 （事务性，不按顺序）  
 为实现高可用性 （非事务性） 准则并添加其他主机实例，即可实现可伸缩性。 此体系结构提供了快速送达以及可伸缩性，但不提供按序的送达。  
  
## <a name="scalability-transactional-not-in-order"></a>可伸缩性 （事务性，不按顺序）  
 对于送达的事务性消息不按序送达的情况下，可以使用 MSMQ 和 Windows 群集组合使用 NLB。 此体系结构需要两个独立 Windows 群集环境中的步骤"高可用性 （事务性，按顺序）"下为每个 Windows 群集上配置至少两个群集组。 随后即可实现 NLB 群集组之间的负载分配。 由于 Windows NLB 不支持 Windows 群集上运行，这种情况下需要使用硬件 NLB 解决方案。 下图对此结构进行了说明：  
  
 ![群集组之间的负载平衡](../core/media/scaleclusteredmsmqwithnlb.gif "ScaleClusteredMSMQwithNLB")  
  
> [!NOTE]
>  此体系结构不提供按序的送达。  
  
## <a name="scalability-transactional-in-order"></a>可伸缩性 （事务性，按顺序）  
 扩展提供高可用性、 事务一致性以及按序的送达的体系结构是使用 MSMQ 3.0 时，会出现问题或更早版本不支持远程事务性读取，除非由于 BizTalk Server 计算机和远程 MSMQ 服务器都运行 MSMQ 4.0。 使用 MSMQ 3.0 或更早版本时，必须使用多个本地 MSMQ 队列实现向外扩展。 此外，在此方案中，如果连接到 NLB 的 MSMQ 会话的 TCP/IP 连接中断，它可能被 NLB 随后还原到其他计算机，这会导致无序送达。  
  
 这一限制的一种解决方法是手动加载平衡消息传递目标队列分配到不同的计算机。 你可以使这通过将特定的 BizTalk 主机实例到特定的 MSMQ 队列。 因此，例如，如果从特定的贸易合作伙伴接收大量的文档，创建单独的主机，并为该贸易合作伙伴接收特定的 BizTalk server 上的队列。  
  
 如果可能，请在远程计算机上运行 MSMQ 4.0，需要远程事务性读取和负载平衡时。  
  
## <a name="summary"></a>总结  
 下表总结了你可用来实现特定功能的体系结构。  
  
|**功能**|**NLB 和群集都不**|**NLB**|**Cluster**|**NLB 和群集**|  
|-----------------------|---------------------------------|-------------|-----------------|-------------------------|  
|端到端按序送达|是|否|是|可能的通过手动配置|  
|事务一致性|否 （消息可能已丢失或重复如果出现服务故障）|否|是|是|  
|高度可用|否|是|是|是|  
|可缩放|否|是|否|是|  
  
## <a name="see-also"></a>请参阅  
 [使用 Windows Server 群集为 BizTalk Server 主机 2 提供高可用性](../core/use-windows-cluster-to-provide-high-availability-for-biztalk-hosts.md)