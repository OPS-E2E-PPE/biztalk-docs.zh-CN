---
title: MQSeries 适配器的高可用性 |Microsoft Docs
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
ms.openlocfilehash: 96fb7eb3ef5d126656d3cc456206ae56feba4c23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65323758"
---
# <a name="mqseries-adapter-high-availability"></a><span data-ttu-id="34fb4-102">MQSeries 适配器的高可用性</span><span class="sxs-lookup"><span data-stu-id="34fb4-102">MQSeries Adapter High Availability</span></span>
<span data-ttu-id="34fb4-103">使用适配器时，可以按以下方式提高可用性：</span><span class="sxs-lookup"><span data-stu-id="34fb4-103">You can improve availability in the following ways when you use the adapter:</span></span>  
  
- <span data-ttu-id="34fb4-104">设置容错宿主环境[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="34fb4-104">Set up a fault-tolerant hosting environment for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
- <span data-ttu-id="34fb4-105">使用 Windows 群集对 IBM WebSphere MQ。</span><span class="sxs-lookup"><span data-stu-id="34fb4-105">Use Windows Clustering with IBM WebSphere MQ.</span></span>  
  
  <span data-ttu-id="34fb4-106">有关容错能力的信息和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[示例 BizTalk Server 体系结构](../core/sample-biztalk-server-architectures.md)并[规划你平台容错](../core/planning-your-platform-for-fault-tolerance.md)中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助。</span><span class="sxs-lookup"><span data-stu-id="34fb4-106">For information about fault tolerance and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], see [Sample BizTalk Server Architectures](../core/sample-biztalk-server-architectures.md) and [Planning Your Platform for Fault Tolerance](../core/planning-your-platform-for-fault-tolerance.md) in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help.</span></span>  
  
  <span data-ttu-id="34fb4-107">若要确保[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries 适配器是能够与远程安装的 MQSAgent 组件进行通信，请确保在启用了网络 COM + 访问[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和安装了 IBM WebSphere MQ 的服务器。</span><span class="sxs-lookup"><span data-stu-id="34fb4-107">To ensure that the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries Adapter is able to communicate with a remote installation of the MQSAgent component, ensure that you have enabled network COM+ access on the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]and server where IBM WebSphere MQ is installed.</span></span> <span data-ttu-id="34fb4-108">有关启用网络 COM + 访问的详细信息，请参阅 Microsoft 知识库文章编号为 817065 的"如何在 Windows Server 2003 中，启用网络 COM + 访问"网址[ http://go.microsoft.com/fwlink/?LinkId=196580 ](http://go.microsoft.com/fwlink/?LinkId=196580)。</span><span class="sxs-lookup"><span data-stu-id="34fb4-108">For more information about enabling network COM+ access, see Microsoft Knowledge Base article number 817065, " How to enable network COM+ access in Windows Server 2003," available at [http://go.microsoft.com/fwlink/?LinkId=196580](http://go.microsoft.com/fwlink/?LinkId=196580).</span></span>  
  
  <span data-ttu-id="34fb4-109">没有不需要群集的 MQSAgent (MQSAgent2) COM + 应用程序与一起使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]MQSeries 适配器。</span><span class="sxs-lookup"><span data-stu-id="34fb4-109">There is no requirement to cluster the MQSAgent (MQSAgent2) COM+ application that is used with the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] MQSeries adapter.</span></span> <span data-ttu-id="34fb4-110">若要为此组件提供高可用性，请在每个群集节点上安装组件。</span><span class="sxs-lookup"><span data-stu-id="34fb4-110">To provide high availability for this component, install the component on each cluster node.</span></span> <span data-ttu-id="34fb4-111">如果 COM + 应用程序停止时，从客户端的下一个调用将启动它。</span><span class="sxs-lookup"><span data-stu-id="34fb4-111">If the COM+ application stops, the next call from the client will start it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34fb4-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="34fb4-112">See Also</span></span>  
 [<span data-ttu-id="34fb4-113">使用 MQSeries 适配器</span><span class="sxs-lookup"><span data-stu-id="34fb4-113">Using the MQSeries Adapter</span></span>](../core/using-the-mqseries-adapter.md)