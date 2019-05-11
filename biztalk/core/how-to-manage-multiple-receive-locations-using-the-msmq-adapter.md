---
title: 如何管理多个接收位置使用 MSMQ 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3b46ab60e3e5073c7c487ffb530dbc0407b0444f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384709"
---
# <a name="how-to-manage-multiple-receive-locations-using-the-msmq-adapter"></a><span data-ttu-id="eb747-102">如何管理多个接收位置使用 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="eb747-102">How to Manage Multiple Receive Locations Using the MSMQ Adapter</span></span>
<span data-ttu-id="eb747-103">若要提高性能，MSMQ 适配器是多线程。</span><span class="sxs-lookup"><span data-stu-id="eb747-103">To increase performance, the MSMQ adapter is multithreaded.</span></span> <span data-ttu-id="eb747-104">如果有多个接收位置，可能不有足够的线程可用于所有接收位置。</span><span class="sxs-lookup"><span data-stu-id="eb747-104">If you have many receive locations, there may not be enough threads available for all the receive locations.</span></span> <span data-ttu-id="eb747-105">这会妨碍某些接收位置提取消息。</span><span class="sxs-lookup"><span data-stu-id="eb747-105">This prevents some of the receive locations from picking up messages.</span></span> <span data-ttu-id="eb747-106">有三种方法来解决此问题：</span><span class="sxs-lookup"><span data-stu-id="eb747-106">There are three ways to solve this problem:</span></span>  
  
-   <span data-ttu-id="eb747-107">添加到您的计算机的 BizTalk 主机，并划分的主机之间的接收位置。</span><span class="sxs-lookup"><span data-stu-id="eb747-107">Add BizTalk Hosts to your computer and divide the receive locations among the hosts.</span></span> <span data-ttu-id="eb747-108">添加主机使更多的线程可用于接收位置。</span><span class="sxs-lookup"><span data-stu-id="eb747-108">Adding hosts makes more threads available for the receive locations.</span></span>  
  
-   <span data-ttu-id="eb747-109">设置**串行处理**属性设置为`True`上每个接收位置。</span><span class="sxs-lookup"><span data-stu-id="eb747-109">Set the **Serial Processing** property to `True` on each receive location.</span></span> <span data-ttu-id="eb747-110">将属性设置为`True`分配到每个线程的单个接收位置。</span><span class="sxs-lookup"><span data-stu-id="eb747-110">Setting the property to `True` assigns a single thread to each receive location.</span></span> <span data-ttu-id="eb747-111">这将使更多可用的线程池中。</span><span class="sxs-lookup"><span data-stu-id="eb747-111">This leaves more threads available in the pool.</span></span> <span data-ttu-id="eb747-112">但是，这可能还会导致性能降低。</span><span class="sxs-lookup"><span data-stu-id="eb747-112">However, this may also cause a decrease in performance.</span></span>  
  
-   <span data-ttu-id="eb747-113">修改注册表以增加 MSMQ 适配器接收处理程序是可用于该主机的线程数。</span><span class="sxs-lookup"><span data-stu-id="eb747-113">Modify the registry to increase the number of threads that are available to the host for the MSMQ adapter receive handler.</span></span> <span data-ttu-id="eb747-114">有关详细信息请参阅**修改主机的 CLR 宿主线程值**一部分[配置参数会影响适配器性能的](../core/configuration-parameters-that-affect-adapter-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="eb747-114">For more information see the **Modify the CLR Hosting thread values for the host** section of [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb747-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb747-115">See Also</span></span>  
 [<span data-ttu-id="eb747-116">配置 MSMQ 适配器</span><span class="sxs-lookup"><span data-stu-id="eb747-116">Configuring the MSMQ Adapter</span></span>](../core/configuring-the-msmq-adapter.md)