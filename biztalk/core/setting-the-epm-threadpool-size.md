---
title: EPM 线程池大小设置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9e170e76-5151-4306-9473-5b68e815219a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54afa88b51876d0ee56f548f263be1b00c37967a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271133"
---
# <a name="setting-the-epm-threadpool-size"></a><span data-ttu-id="c32a1-102">设置 EPM 线程池大小</span><span class="sxs-lookup"><span data-stu-id="c32a1-102">Setting the EPM Threadpool Size</span></span>
<span data-ttu-id="c32a1-103">本主题说明如何设置为终结点管理器 (EPM) 的线程池大小。</span><span class="sxs-lookup"><span data-stu-id="c32a1-103">This topic explains how to set the threadpool size for the End Point Manager (EPM).</span></span>  
  
 <span data-ttu-id="c32a1-104">上**高级**选项卡中**主机属性**对话框中，没有名为的属性**每个 CPU 线程的最大数量的消息传递引擎**。</span><span class="sxs-lookup"><span data-stu-id="c32a1-104">On the **Advanced** tab in the **Host Properties** dialog box, there is a property called **Maximum number of messaging engine threads per CPU**.</span></span> <span data-ttu-id="c32a1-105">有关访问此对话框中的说明，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。</span><span class="sxs-lookup"><span data-stu-id="c32a1-105">For instructions about accessing this dialog box, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span> <span data-ttu-id="c32a1-106">使用此属性来控制的消息传递引擎用于处理消息的进程线程池的大小。</span><span class="sxs-lookup"><span data-stu-id="c32a1-106">Use this property to control the size of the pool of process threads that the messaging engine uses to process messages.</span></span> <span data-ttu-id="c32a1-107">默认值为此属性为 20，这意味着消息引擎将为每个服务器上的 CPU 使用不能超过 20 个线程。</span><span class="sxs-lookup"><span data-stu-id="c32a1-107">The default value for this property is 20, meaning that the messaging engine will use no more than 20 threads for each CPU on the server.</span></span>  
  
 <span data-ttu-id="c32a1-108">由于消息批处理池中的每个线程处理，调整的值**每个 CPU 线程的最大数量的消息传递引擎**可以通过更改服务器上的资源使用率的 dynamics 影响性能。</span><span class="sxs-lookup"><span data-stu-id="c32a1-108">Since batches of messages are processed by each thread in the pool, adjusting the value of **Maximum number of messaging engine threads per CPU** can affect performance by changing the dynamics of resource utilization on the server.</span></span> <span data-ttu-id="c32a1-109">有关线程池的工作原理的详细信息，请参阅[使用 BizTalk Messaging Engine](../core/using-the-biztalk-messaging-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="c32a1-109">For more information about how the threadpool works, see [Using the BizTalk Messaging Engine](../core/using-the-biztalk-messaging-engine.md).</span></span>  
  
 <span data-ttu-id="c32a1-110">测试表明，在其中 CPU 或 SQL Server 过度使用的情况下，减少的值**每个 CPU 线程的最大数量的消息传递引擎**可能会导致吞吐量净的性能收益。</span><span class="sxs-lookup"><span data-stu-id="c32a1-110">Testing has shown that in cases where the CPU or the SQL Server is over utilized, decreasing the value of **Maximum number of messaging engine threads per CPU** can result in a net gain in throughput.</span></span> <span data-ttu-id="c32a1-111">例如，在其中 MessageBox 数据库服务器表现出 CPU 的情况下利用率高于 90%或 SQL 锁等待时间将提升超过 500-1000 毫秒，减少池中的线程数会减少对 SQL 进行的所有连接服务器，这会导致消息处理更高效。</span><span class="sxs-lookup"><span data-stu-id="c32a1-111">For example, in cases where the MessageBox database server exhibits CPU utilization above 90% or the SQL lock wait times are elevated above 500-1000 milliseconds, reducing the number of threads in the pool will reduce the overall number connections being made to SQL Server, which results in more efficient message processing.</span></span> <span data-ttu-id="c32a1-112">在某些情况下，将设置最大线程池大小的值低 2 可能会导致显著提高吞吐量提升。</span><span class="sxs-lookup"><span data-stu-id="c32a1-112">In some cases, setting the maximum thread pool size to a value as low as 2 can result in measurable throughput gain.</span></span>  
  
## <a name="recommendation"></a><span data-ttu-id="c32a1-113">建议</span><span class="sxs-lookup"><span data-stu-id="c32a1-113">Recommendation</span></span>  
 <span data-ttu-id="c32a1-114">在优化的 BizTalk Server 安装，建议你精细优化为设置的值**每个 CPU 线程的最大数量的消息传递引擎**。</span><span class="sxs-lookup"><span data-stu-id="c32a1-114">When optimizing a BizTalk Server installation, it is recommended that you fine tune the value you set for **Maximum number of messaging engine threads per CPU**.</span></span>  <span data-ttu-id="c32a1-115">尝试减少 MessageBox 数据库服务器的使用率，请考虑减小此属性的值。</span><span class="sxs-lookup"><span data-stu-id="c32a1-115">When you try to reduce the utilization of the MessageBox database server, consider reducing the value of this property.</span></span>  
  
 <span data-ttu-id="c32a1-116">当 BizTalk server 或 MessageBox 数据库服务器不高利用率，并应用额外的负载不会导致更高的吞吐量时，请尝试增加的值**每个 CPU 线程的最大数量的消息传递引擎**若要利用使用不足的资源。</span><span class="sxs-lookup"><span data-stu-id="c32a1-116">When the BizTalk server or the MessageBox database server is not highly utilized, and applying additional load does not result in additional throughput, try increasing the value of **Maximum number of messaging engine threads per CPU** to take advantage of underutilized resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c32a1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c32a1-117">See Also</span></span>  
 <span data-ttu-id="c32a1-118">[如何创建新的主机](../core/how-to-create-a-new-host.md) </span><span class="sxs-lookup"><span data-stu-id="c32a1-118">[How to Create a New Host](../core/how-to-create-a-new-host.md) </span></span>  
 [<span data-ttu-id="c32a1-119">使用 BizTalk 消息传送引擎</span><span class="sxs-lookup"><span data-stu-id="c32a1-119">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)