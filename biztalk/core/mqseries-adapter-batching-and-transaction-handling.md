---
title: "MQSeries 适配器批处理和事务处理 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- transactions, MQSeries adapters
- MQSeries adapters, transactions
- MQSeries adapters, IBM WebSphere MQ queues
- MQSeries adapters, batching
- batching, MQSeries adapters
ms.assetid: 2e43fca9-acbd-4fd3-8df3-5f7398553830
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ffcdec02c464b9398acbece35657e0c3d1dc4432
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="mqseries-adapter-batching-and-transaction-handling"></a><span data-ttu-id="0e869-102">MQSeries 适配器批处理和事务处理</span><span class="sxs-lookup"><span data-stu-id="0e869-102">MQSeries Adapter Batching and Transaction Handling</span></span>
<span data-ttu-id="0e869-103">MQSeries 适配器只在未接收所有数据的情况下才停止事务。</span><span class="sxs-lookup"><span data-stu-id="0e869-103">The MQSeries adapter stops a transaction only if it does not receive all the data.</span></span> <span data-ttu-id="0e869-104">适配器事务的边界是适配器终结点（MQSeries 服务器上的 MQSeries 队列）和 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="0e869-104">The boundaries of a transaction for the adapter are the adapter endpoint (MQSeries queue on the MQSeries Server) and the MessageBox database.</span></span>  
  
 <span data-ttu-id="0e869-105">如果 BizTalk 应用程序使消息无效，则适配器会将该消息移至挂起队列中。</span><span class="sxs-lookup"><span data-stu-id="0e869-105">If the BizTalk application invalidates a message, the adapter moves the message to the suspended queue.</span></span> <span data-ttu-id="0e869-106">不过，由于适配器仍将其视为有效事务（该适配器接收了所有数据），因此适配器将提交事务。</span><span class="sxs-lookup"><span data-stu-id="0e869-106">However, because it is still a valid transaction from the point of view of the adapter (the adapter received all the data), the adapter commits the transaction.</span></span>  
  
 <span data-ttu-id="0e869-107">对适配器进行配置时，可以通过设置属性来控制批处理和事务处理。</span><span class="sxs-lookup"><span data-stu-id="0e869-107">You can control batching and transaction handling by setting properties when configuring the adapter.</span></span> <span data-ttu-id="0e869-108">有关详细信息，请参阅[配置 MQSeries 适配器](../core/configuring-the-mqseries-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="0e869-108">For more information, see [Configuring the MQSeries Adapter](../core/configuring-the-mqseries-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e869-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e869-109">See Also</span></span>  
 [<span data-ttu-id="0e869-110">MQSeries 适配器属性</span><span class="sxs-lookup"><span data-stu-id="0e869-110">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)