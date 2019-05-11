---
title: 优化 MQSeries 适配器性能 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1a46455c-a8d2-4427-99bb-4e3c6dbd9566
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ba12a46e17c8c521afef62e7c0ad5a9f51afe35
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291427"
---
# <a name="optimizing-mqseries-adapter-performance"></a><span data-ttu-id="a0266-102">优化 MQSeries 适配器性能</span><span class="sxs-lookup"><span data-stu-id="a0266-102">Optimizing MQSeries Adapter Performance</span></span>
<span data-ttu-id="a0266-103">使用以下设置时，可以增加性能配置 MQSeries 适配器。</span><span class="sxs-lookup"><span data-stu-id="a0266-103">Configure the MQSeries adapter by using the following settings when possible to increase performance.</span></span>  
  
## <a name="adjust-the-value-for-the-mqseries-receive-adapter-polling-threads"></a><span data-ttu-id="a0266-104">将值调整为 MQSeries 接收适配器轮询线程</span><span class="sxs-lookup"><span data-stu-id="a0266-104">Adjust the value for the MQSeries receive adapter polling threads</span></span>  
 <span data-ttu-id="a0266-105">增加为指定的值**线程**中**MQSeries 传输属性**时配置 MQSeries 适配器接收位置。</span><span class="sxs-lookup"><span data-stu-id="a0266-105">Increase the value specified for **Threads** in the **MQSeries Transport Properties** when configuring MQSeries adapter receive locations.</span></span> <span data-ttu-id="a0266-106">增加此属性的默认值为 2 从 5 的值将极大地缩短从该处可以接收消息使用 MQSeries 适配器的速率。</span><span class="sxs-lookup"><span data-stu-id="a0266-106">Increasing this property from the default value of 2 to a value of 5 will significantly improve the rate at which messages can be received using the MQSeries adapter.</span></span>  
  
## <a name="disable-transaction-support-on-mqseries-receive-locations-where-not-required"></a><span data-ttu-id="a0266-107">禁用事务支持，在 MQSeries 接收位置在不需要</span><span class="sxs-lookup"><span data-stu-id="a0266-107">Disable transaction support on MQSeries receive locations where not required</span></span>  
 <span data-ttu-id="a0266-108">MQSeries 适配器的事务支持会产生很大的开销。</span><span class="sxs-lookup"><span data-stu-id="a0266-108">MQSeries adapter transaction support incurs significant overhead.</span></span> <span data-ttu-id="a0266-109">如果事务支持不是一项业务要求，设置**支持事务**中的值**MQSeries 传输属性**对话框中的默认值从**是**到**否**。</span><span class="sxs-lookup"><span data-stu-id="a0266-109">If transaction support is not a business requirement, set the **Transaction Supported** value in the **MQSeries Transport Properties** dialog box from the default value of **Yes** to **No**.</span></span>  
  
## <a name="disable-ordered-delivery-of-messages-on-the-mqseries-adapter-when-not-required"></a><span data-ttu-id="a0266-110">禁用 MQSeries 适配器时不是必需的适配器上的消息按序的的送达</span><span class="sxs-lookup"><span data-stu-id="a0266-110">Disable Ordered delivery of messages on the MQSeries Adapter when not required</span></span>  
 <span data-ttu-id="a0266-111">启用此属性将强制执行按序的送达消息，因为从接收或发送到 MQSeries 队列，但会影响性能。</span><span class="sxs-lookup"><span data-stu-id="a0266-111">Enabling this property will enforce ordered delivery of messages as they are received from or sent to the MQSeries queue but will affect performance.</span></span> <span data-ttu-id="a0266-112">启用按序的送达后，消息传送的运行时将使用一个线程从给定的 MQSeries 队列接收消息。</span><span class="sxs-lookup"><span data-stu-id="a0266-112">When ordered delivery is enabled, the messaging runtime will use a single thread to receive messages from a given MQSeries queue.</span></span> <span data-ttu-id="a0266-113">如果按序送达消息不是一项业务要求，则执行更改的默认值**Ordered**属性中的**MQSeries 传输属性**对话框中为其设置为**否排序**。</span><span class="sxs-lookup"><span data-stu-id="a0266-113">If ordered delivery of messages is not a business requirement, then do not change the default value of **Ordered** property in the **MQSeries Transport Properties** dialog box which is set as **No Ordering**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0266-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="a0266-114">See Also</span></span>  
 [<span data-ttu-id="a0266-115">优化 BizTalk Server 性能</span><span class="sxs-lookup"><span data-stu-id="a0266-115">Optimizing BizTalk Server Performance</span></span>](../technical-guides/optimizing-biztalk-server-performance.md)