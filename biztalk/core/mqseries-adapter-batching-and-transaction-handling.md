---
title: MQSeries 适配器批处理和事务处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IBM WebSphere MQ queues
- transactions, MQSeries adapters
- MQSeries adapters, transactions
- MQSeries adapters, IBM WebSphere MQ queues
- MQSeries adapters, batching
- batching, MQSeries adapters
ms.assetid: 2e43fca9-acbd-4fd3-8df3-5f7398553830
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 466201e88b55cd17300deaae3d1b1258e82a2c2c
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531204"
---
# <a name="mqseries-adapter-batching-and-transaction-handling"></a><span data-ttu-id="88ab3-102">MQSeries 适配器批处理和事务处理</span><span class="sxs-lookup"><span data-stu-id="88ab3-102">MQSeries Adapter Batching and Transaction Handling</span></span>
<span data-ttu-id="88ab3-103">它不会接收所有数据，MQSeries 适配器就会停止事务。</span><span class="sxs-lookup"><span data-stu-id="88ab3-103">The MQSeries adapter stops a transaction only if it does not receive all the data.</span></span> <span data-ttu-id="88ab3-104">适配器事务的边界是适配器终结点 （MQSeries 服务器上的 MQSeries 队列） 和 MessageBox 数据库。</span><span class="sxs-lookup"><span data-stu-id="88ab3-104">The boundaries of a transaction for the adapter are the adapter endpoint (MQSeries queue on the MQSeries Server) and the MessageBox database.</span></span>  
  
 <span data-ttu-id="88ab3-105">如果 BizTalk 应用程序使消息无效，则适配器将消息移至挂起队列。</span><span class="sxs-lookup"><span data-stu-id="88ab3-105">If the BizTalk application invalidates a message, the adapter moves the message to the suspended queue.</span></span> <span data-ttu-id="88ab3-106">但是，因为它仍是有效的事务从角度来看 （该适配器接收的所有数据） 的适配器，适配器将提交事务。</span><span class="sxs-lookup"><span data-stu-id="88ab3-106">However, because it is still a valid transaction from the point of view of the adapter (the adapter received all the data), the adapter commits the transaction.</span></span>  
  
 <span data-ttu-id="88ab3-107">您可以控制批处理和事务处理通过配置适配器时设置属性。</span><span class="sxs-lookup"><span data-stu-id="88ab3-107">You can control batching and transaction handling by setting properties when configuring the adapter.</span></span> <span data-ttu-id="88ab3-108">有关详细信息，请参阅[配置 MQSeries 适配器](../core/configuring-the-mqseries-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="88ab3-108">For more information, see [Configuring the MQSeries Adapter](../core/configuring-the-mqseries-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88ab3-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="88ab3-109">See Also</span></span>  
 [<span data-ttu-id="88ab3-110">MQSeries 适配器属性</span><span class="sxs-lookup"><span data-stu-id="88ab3-110">MQSeries Adapter Properties</span></span>](../core/mqseries-adapter-properties.md)