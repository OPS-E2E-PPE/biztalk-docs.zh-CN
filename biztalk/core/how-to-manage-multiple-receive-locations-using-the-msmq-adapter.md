---
title: "如何管理多个接收位置使用 MSMQ 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, receive locations
- MSMQ adapters, threads
- receive locations, multiple
- threads
- receive locations, MSMQ adapters
- receive locations, threads
- configuring [MSMQ adapters], receive locations
ms.assetid: 5b2ee043-bcc9-443b-84b0-df7f487159eb
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72438551d2ecab09b918808d43e7d7de6d600677
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a><span data-ttu-id="45d81-102">如何使用 MSMQ 适配器管理多个接收位置</span><span class="sxs-lookup"><span data-stu-id="45d81-102">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>
<span data-ttu-id="45d81-103">为了提高性能，MSMQ 适配器提供了多线程功能。</span><span class="sxs-lookup"><span data-stu-id="45d81-103">To increase performance, the MSMQ adapter is multithreaded.</span></span> <span data-ttu-id="45d81-104">如果您具有许多接收位置，则可能会没有足够的线程用于所有接收位置。</span><span class="sxs-lookup"><span data-stu-id="45d81-104">If you have many receive locations, there may not be enough threads available for all the receive locations.</span></span> <span data-ttu-id="45d81-105">这会妨碍某些接收位置对消息的提取。</span><span class="sxs-lookup"><span data-stu-id="45d81-105">This prevents some of the receive locations from picking up messages.</span></span> <span data-ttu-id="45d81-106">解决这一问题有以下三种方法：</span><span class="sxs-lookup"><span data-stu-id="45d81-106">There are three ways to solve this problem:</span></span>  
  
-   <span data-ttu-id="45d81-107">向您的计算机添加多个 BizTalk 主机，并将各接收位置划分给这些主机。</span><span class="sxs-lookup"><span data-stu-id="45d81-107">Add BizTalk Hosts to your computer and divide the receive locations among the hosts.</span></span> <span data-ttu-id="45d81-108">添加主机可为接收位置提供更多线程。</span><span class="sxs-lookup"><span data-stu-id="45d81-108">Adding hosts makes more threads available for the receive locations.</span></span>  
  
-   <span data-ttu-id="45d81-109">设置**串行处理**属性`True`上每个接收位置。</span><span class="sxs-lookup"><span data-stu-id="45d81-109">Set the **Serial Processing** property to `True` on each receive location.</span></span> <span data-ttu-id="45d81-110">将属性设置为`True`将分配给每个线程单个接收位置。</span><span class="sxs-lookup"><span data-stu-id="45d81-110">Setting the property to `True` assigns a single thread to each receive location.</span></span> <span data-ttu-id="45d81-111">这样池中可用的线程就会增多。</span><span class="sxs-lookup"><span data-stu-id="45d81-111">This leaves more threads available in the pool.</span></span> <span data-ttu-id="45d81-112">不过，这也可能会导致性能降低。</span><span class="sxs-lookup"><span data-stu-id="45d81-112">However, this may also cause a decrease in performance.</span></span>  
  
-   <span data-ttu-id="45d81-113">修改注册表以增加 MSMQ 适配器接收处理程序的主机可使用的线程数。</span><span class="sxs-lookup"><span data-stu-id="45d81-113">Modify the registry to increase the number of threads that are available to the host for the MSMQ adapter receive handler.</span></span> <span data-ttu-id="45d81-114">有关详细信息请参阅**修改主机的 CLR 承载线程值**部分[配置参数会影响适配器性能](../core/configuration-parameters-that-affect-adapter-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="45d81-114">For more information see the **Modify the CLR Hosting thread values for the host** section of [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45d81-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45d81-115">See Also</span></span>  
 [<span data-ttu-id="45d81-116">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="45d81-116">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)