---
title: 批处理消息的发送处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d9115ec-13bc-41a8-8928-57b168c95af4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7854151b0b32165d2ec3db83a90516898cf8d8e6
ms.sourcegitcommit: 53b16fe6c1b1707ecf233dbd05f780653eb19419
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "50753133"
---
# <a name="batching-messages-for-send-processing"></a>为发送处理批处理消息
## <a name="send-adapter-batch-management"></a>发送适配器批的管理  
 在发送端使用事务时，由 BizTalk Server 创建的用于发送到目标系统的相同事务在成功发送后，将用于删除相应消息。 如果其中有任何步骤失败，则事务将结束，在这种情况下将中止删除操作，数据仍保留在 BizTalk Server 中，而不在目标系统中。 这可以防止消息重复。 只有异步发送适配器才支持事务。 不应该将事务与同步发送适配器一起使用。  
  
 但是适配器不能只结束事务，它还必须能够正确处理给出的消息状态。 具体而言，适配器应调用的方法**重新提交**， **MoveToNextTransport**，并**MoveToSuspendQ**适当地根据重试计数和是否可备份传输。  
  
 务必要放置**删除**并**SubmitResponse**一起使用同一个事务的批中的操作。 失败将通过结束事务来进行处理，以来确保数据仅向外部系统提交一次。 但仍想要重新提交或调用**MoveToNextTransport**在 BizTalk Server 上的消息。 为此，对于这些类型的操作，请使用单独的普通批（非事务批）。  
  
 下图显示了如何为响应消息使用单独的批。  
  
 ![为响应消息使用单独的批](../core/media/eawp-separatebatch.gif "EAWP_SeparateBatch")  
  
## <a name="sorting-the-send-side-transactional-batches-by-endpoint"></a>按终结点对发送端事务批进行分类  
 由 BizTalk Server 发送到适配器的消息批可以跨多个发送端口（或终结点）。 因为适配器通常需要有一个终结点的事务，适配器必须对根据发送端口的消息进行排序 (**SPName**或**OutboundTransportLocation**)。 通过执行此操作，适配器可以创建仅跨越特定发送端口的事务。  
  
 例如，当 FTP 发送适配器接收一个来自 BizTalk Server 的消息批时，它得到的是一个混合的消息批，这些消息来自所有当前活动的 FTP 发送端口。 发生这种情况的原因是 API 是基于单一的接口，这意味着只能加载单个 FTP 适配器，而不能每个发送端口都加载一个。  
  
 适配器必须首先将 BizTalk Server 传来的消息批分类为单独的批，即每个终结点一个批次。 然后它可以轮流处理每个终结点，并可以构造每个终结点的删除批。 SDK 示例代码中的 BaseAdapter 可重用泛型类以同样的方式运行。  
  
## <a name="sorting-for-dynamic-send"></a>为动态发送分类  
 只要 BizTalk Server 业务流程在消息头和 URL 本身中提供足够的配置详细信息，它就可以将消息发送到尚未配置的端口。 因此 BizTalk Server 必须能够识别 URL 协议。  
  
 将消息分类时，应该谨慎建立定义终结点的内容。 这在动态发送的情况下更是如此。 如果只是用 URI 定义终结点，问题就简单了。 但是，在 FTP 会话中，FTP 服务器可能使用用户名登录详细信息来定义真正的终结点。 在这种情况下，如果适配器以不同的帐户登录，则它可能会被连接到不同的目录。  
  
 在某些情况下，真正的终结点不知道运行企业单一登录 (SSO) 命令之前**validateandredeemticket，以**。  
  
 对于 MQSeries，是否决定使用事务是可配置的。 在确定远程 COM+ 对象的结构和用途后，最好将事务性终结点看作是与非事务性终结点完全不同的终结点。  
  
 总而言之，将消息分类到其单个终结点批中有时是一项非常重要的任务，可能会涉及到一些额外步骤，如考虑上下文值，甚至是考虑 SSO 的调用结果。  
  
## <a name="sorting-for-static-send"></a>为静态发送分类  
 如果终结点是静态配置的终结点，则在消息上下文中有一个叫作静态端口 ID (SPID) 的唯一 GUID。 此值可用于对终结点进行分类。 以下代码可用于检索该 GUID：  
  
```  
string spid = (string)message.Context.Read("SPID", "http://schemas.microsoft.com/BizTalk/2003/system-properties");  
```  
  
 当考虑由基于 XML 架构定义 (XSD) 的配置框架引起的问题时，这是很有帮助的。 在此框架中，有一个可能是终结点键一部分的属性隐藏在单个上下文属性的 XML 中。 如果在该上下文中有 SPID，就可以使用它作为将批分类的一种方法。 否则就是在执行动态发送，需要构造一个用来将批分类的备用键。  
  
 下图显示了如何按终结点对消息进行分类。  
  
 ![对消息的终结点进行排序](../core/media/eawp-sortbatch.gif "EAWP_SortBatch")  
  
 请注意，消息的重试次数与批的成功与否无关。 在发送端，消息批可能会由于批中的几个消息失败而失败。 适配器必须决定如何处理它接收到的每个消息。 在批失败的情况下，可以假定每个消息都被重新提交了。 但是，如果失败批中的所有消息都重新提交了，则对于成功的消息，重试次数（由 BizTalk Server 引擎维护）也将不正确地递增，这是因为这些成功的消息恰好与失败的消息在同一批中。 在这种情况下，适配器可以重新形成出站批，并针对外部系统重试成功的消息。
