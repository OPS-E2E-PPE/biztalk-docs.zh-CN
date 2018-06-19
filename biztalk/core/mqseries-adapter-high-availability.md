---
title: MQSeries 适配器高可用性 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- performance, MQSeries adapters
- MQSeries adapters, availability
- MQSeries adapters, performance
- high availability, MQSeries adapters
ms.assetid: 4339b10b-b35d-47c0-b78a-c60207e06c8e
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21c0b6486e49cb2ccddfab37271a94a4ba7a6948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263229"
---
# <a name="mqseries-adapter-high-availability"></a><span data-ttu-id="b3816-102">MQSeries 适配器高可用性</span><span class="sxs-lookup"><span data-stu-id="b3816-102">MQSeries Adapter High Availability</span></span>
<span data-ttu-id="b3816-103">在使用适配器时，可通过以下方式提高其可用性：</span><span class="sxs-lookup"><span data-stu-id="b3816-103">You can improve availability in the following ways when you use the adapter:</span></span>  
  
-   <span data-ttu-id="b3816-104">设置的容错的宿主环境[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b3816-104">Set up a fault-tolerant hosting environment for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="b3816-105">对 IBM WebSphere MQ 使用 Windows 群集。</span><span class="sxs-lookup"><span data-stu-id="b3816-105">Use Windows Clustering with IBM WebSphere MQ.</span></span>  
  
 <span data-ttu-id="b3816-106">有关容错和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[示例 BizTalk 服务器体系结构](../core/sample-biztalk-server-architectures.md)和[规划你的平台，用于容错](../core/planning-your-platform-for-fault-tolerance.md)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="b3816-106">For information about fault tolerance and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md) and [Planning Your Platform for Fault Tolerance](../core/planning-your-platform-for-fault-tolerance.md) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
 <span data-ttu-id="b3816-107">为确保 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries 适配器能够与远程安装的 MQSAgent 组件进行通信，请确保在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和安装了 IBM WebSphere MQ 的服务器上已启用了网络 COM+ 访问。</span><span class="sxs-lookup"><span data-stu-id="b3816-107">To ensure that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries Adapter is able to communicate with a remote installation of the MQSAgent component, ensure that you have enabled network COM+ access on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]and server where IBM WebSphere MQ is installed.</span></span> <span data-ttu-id="b3816-108">有关启用网络 COM + 访问的详细信息，请参阅 Microsoft 知识库文章编号 817065，"如何启用 Windows Server 2003 中的网络 COM + 访问"在可用[http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580)。</span><span class="sxs-lookup"><span data-stu-id="b3816-108">For more information about enabling network COM+ access, see Microsoft Knowledge Base article number 817065, " How to enable network COM+ access in Windows Server 2003," available at [http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580).</span></span>  
  
 <span data-ttu-id="b3816-109">没有无需群集 MQSAgent (MQSAgent2) COM + 应用程序，用于为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries 适配器。</span><span class="sxs-lookup"><span data-stu-id="b3816-109">There is no requirement to cluster the MQSAgent (MQSAgent2) COM+ application that is used with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries adapter.</span></span> <span data-ttu-id="b3816-110">为确保此组件的高可用性，请在每个群集节点安装该组件。</span><span class="sxs-lookup"><span data-stu-id="b3816-110">To provide high availability for this component, install the component on each cluster node.</span></span> <span data-ttu-id="b3816-111">如果该 COM+ 应用程序停止运行，则下一次从客户端中进行调用时将启动该程序。</span><span class="sxs-lookup"><span data-stu-id="b3816-111">If the COM+ application stops, the next call from the client will start it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3816-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3816-112">See Also</span></span>  
 [<span data-ttu-id="b3816-113">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="b3816-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)