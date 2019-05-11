---
title: 设置 EPM 线程池的大小 |Microsoft Docs
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
ms.openlocfilehash: 0eeb755b7fbee5939510e9e3fae0bb8868f91611
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393236"
---
# <a name="setting-the-epm-threadpool-size"></a><span data-ttu-id="d218b-102">设置 EPM 线程池的大小</span><span class="sxs-lookup"><span data-stu-id="d218b-102">Setting the EPM Threadpool Size</span></span>
<span data-ttu-id="d218b-103">本主题说明如何设置为终结点管理器 (EPM) 的线程池大小。</span><span class="sxs-lookup"><span data-stu-id="d218b-103">This topic explains how to set the threadpool size for the End Point Manager (EPM).</span></span>  
  
 <span data-ttu-id="d218b-104">上**高级**选项卡**主机属性**对话框中，还有一个名为属性**每 CPU 的最大数量的消息引擎线程**。</span><span class="sxs-lookup"><span data-stu-id="d218b-104">On the **Advanced** tab in the **Host Properties** dialog box, there is a property called **Maximum number of messaging engine threads per CPU**.</span></span> <span data-ttu-id="d218b-105">有关访问此对话框中的说明，请参阅[如何创建新的主机](../core/how-to-create-a-new-host.md)。</span><span class="sxs-lookup"><span data-stu-id="d218b-105">For instructions about accessing this dialog box, see [How to Create a New Host](../core/how-to-create-a-new-host.md).</span></span> <span data-ttu-id="d218b-106">使用此属性来控制消息引擎使用来处理消息的进程线程池的大小。</span><span class="sxs-lookup"><span data-stu-id="d218b-106">Use this property to control the size of the pool of process threads that the messaging engine uses to process messages.</span></span> <span data-ttu-id="d218b-107">默认值为 20，这意味着消息引擎将为每个 CPU 的服务器上使用不超过 20 个线程。</span><span class="sxs-lookup"><span data-stu-id="d218b-107">The default value for this property is 20, meaning that the messaging engine will use no more than 20 threads for each CPU on the server.</span></span>  
  
 <span data-ttu-id="d218b-108">由于消息批通过在池中每个线程处理，因此调整的值**每 CPU 的最大数量的消息引擎线程**可以通过更改在服务器上的资源利用率的动态会影响性能。</span><span class="sxs-lookup"><span data-stu-id="d218b-108">Since batches of messages are processed by each thread in the pool, adjusting the value of **Maximum number of messaging engine threads per CPU** can affect performance by changing the dynamics of resource utilization on the server.</span></span> <span data-ttu-id="d218b-109">有关线程池的工作原理的详细信息，请参阅[使用 BizTalk 消息引擎](../core/using-the-biztalk-messaging-engine.md)。</span><span class="sxs-lookup"><span data-stu-id="d218b-109">For more information about how the threadpool works, see [Using the BizTalk Messaging Engine](../core/using-the-biztalk-messaging-engine.md).</span></span>  
  
 <span data-ttu-id="d218b-110">测试表明，在其中 CPU 或 SQL Server 过度的情况下，减小值的**每 CPU 的最大数量的消息引擎线程**可能会导致吞吐量的净增加。</span><span class="sxs-lookup"><span data-stu-id="d218b-110">Testing has shown that in cases where the CPU or the SQL Server is over utilized, decreasing the value of **Maximum number of messaging engine threads per CPU** can result in a net gain in throughput.</span></span> <span data-ttu-id="d218b-111">例如，在其中 MessageBox 数据库服务器表现出 CPU 的情况下利用率高于 90%或 SQL 锁等待时间提升超过 500-1000 毫秒，减少池中的线程数将减少对 SQL 进行的所有连接服务器，这会导致更有效的消息处理。</span><span class="sxs-lookup"><span data-stu-id="d218b-111">For example, in cases where the MessageBox database server exhibits CPU utilization above 90% or the SQL lock wait times are elevated above 500-1000 milliseconds, reducing the number of threads in the pool will reduce the overall number connections being made to SQL Server, which results in more efficient message processing.</span></span> <span data-ttu-id="d218b-112">在某些情况下，将最大线程池大小设置为值低 2 可能会导致可测量吞吐量提升。</span><span class="sxs-lookup"><span data-stu-id="d218b-112">In some cases, setting the maximum thread pool size to a value as low as 2 can result in measurable throughput gain.</span></span>  
  
## <a name="recommendation"></a><span data-ttu-id="d218b-113">建议</span><span class="sxs-lookup"><span data-stu-id="d218b-113">Recommendation</span></span>  
 <span data-ttu-id="d218b-114">在优化时 BizTalk Server 安装，建议您调整为设置的值**每 CPU 的最大数量的消息引擎线程**。</span><span class="sxs-lookup"><span data-stu-id="d218b-114">When optimizing a BizTalk Server installation, it is recommended that you fine tune the value you set for **Maximum number of messaging engine threads per CPU**.</span></span>  <span data-ttu-id="d218b-115">当您尝试减少 MessageBox 数据库服务器的使用率时，请考虑减少此属性的值。</span><span class="sxs-lookup"><span data-stu-id="d218b-115">When you try to reduce the utilization of the MessageBox database server, consider reducing the value of this property.</span></span>  
  
 <span data-ttu-id="d218b-116">当 BizTalk server 或 MessageBox 数据库服务器的利用率不高，并应用其他负载不会导致更高的吞吐量时，请尝试增加的值**每 CPU 的最大数量的消息引擎线程**若要充分利用未充分利用资源。</span><span class="sxs-lookup"><span data-stu-id="d218b-116">When the BizTalk server or the MessageBox database server is not highly utilized, and applying additional load does not result in additional throughput, try increasing the value of **Maximum number of messaging engine threads per CPU** to take advantage of underutilized resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d218b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="d218b-117">See Also</span></span>  
 <span data-ttu-id="d218b-118">[如何创建新的主机](../core/how-to-create-a-new-host.md) </span><span class="sxs-lookup"><span data-stu-id="d218b-118">[How to Create a New Host](../core/how-to-create-a-new-host.md) </span></span>  
 [<span data-ttu-id="d218b-119">使用 BizTalk 消息引擎</span><span class="sxs-lookup"><span data-stu-id="d218b-119">Using the BizTalk Messaging Engine</span></span>](../core/using-the-biztalk-messaging-engine.md)