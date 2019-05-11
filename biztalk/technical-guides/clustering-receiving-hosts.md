---
title: 接收主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93544f39-836f-4a4f-9587-230bfa3a9d4e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a50a23fa3c3d5a5469d82f42e7b467524c2a1f81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277251"
---
# <a name="clustering-receiving-hosts"></a><span data-ttu-id="060f6-102">接收主机</span><span class="sxs-lookup"><span data-stu-id="060f6-102">Clustering Receiving Hosts</span></span>
<span data-ttu-id="060f6-103">BizTalk Server 提供了功能，可将 BizTalk 主机配置中的群集资源[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集组。</span><span class="sxs-lookup"><span data-stu-id="060f6-103">BizTalk Server provides functionality that allows you to configure a BizTalk Host as a clustered resource within a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster group.</span></span> <span data-ttu-id="060f6-104">若要支持集成 BizTalk 的高可用性的接收适配器不应运行多个主机实例中同时，例如 FTP 接收处理程序，或在某些情况下，POP3 接收处理程序提供主机群集支持。</span><span class="sxs-lookup"><span data-stu-id="060f6-104">Host cluster support is provided to support high availability for integrated BizTalk receive adapters that should not be run in multiple host instances simultaneously, such as the FTP receive handler or, under certain circumstances, the POP3 receive handler.</span></span> <span data-ttu-id="060f6-105">主机群集支持还可确保由需要 MSMQ 服务已群集化的方案中的 MSMQ 适配器发送或接收消息的事务一致性。</span><span class="sxs-lookup"><span data-stu-id="060f6-105">Host cluster support is also provided to ensure transactional consistency for messages sent or received by the MSMQ adapter in scenarios that require that the MSMQ service is clustered.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="060f6-106">仅随 BizTalk Server Enterprise Edition 提供了主机群集。</span><span class="sxs-lookup"><span data-stu-id="060f6-106">Host clustering is available only with BizTalk Server Enterprise Edition.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="060f6-107">在可以群集 BizTalk 主机之前，必须配置至少两个[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为成员的 BizTalk 组中计算机[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集。</span><span class="sxs-lookup"><span data-stu-id="060f6-107">Before you can cluster a BizTalk Host you must have configured at least two [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers in a BizTalk group as members of a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster.</span></span> <span data-ttu-id="060f6-108">有关配置详细信息[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]群集，请参阅[Windows Server 2008 聚类分析文档、 白皮书、 网络广播、 组](http://go.microsoft.com/fwlink/?LinkId=156818)(<http://go.microsoft.com/fwlink/?LinkId=156818>)。</span><span class="sxs-lookup"><span data-stu-id="060f6-108">For more information about configuring a [!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)] cluster, see [Windows Server 2008 Clustering Documents, Whitepapers, Webcasts, Groups](http://go.microsoft.com/fwlink/?LinkId=156818) (<http://go.microsoft.com/fwlink/?LinkId=156818>).</span></span>  
  
 <span data-ttu-id="060f6-109">BizTalk 主机群集支持，可用于为五个集成的 BizTalk 适配器提供高可用性： FTP 适配器、 MSMQ 适配器、 POP3 适配器、 SQL 适配器和 SAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="060f6-109">BizTalk Host cluster support is available to provide high availability for five of the integrated BizTalk adapters: the FTP adapter, the MSMQ adapter, the POP3 adapter, the SQL adapter, and the SAP adapter.</span></span> <span data-ttu-id="060f6-110">主机群集支持还提供，以便运行为目的的按序送达的适配器的单个实例的高可用性。</span><span class="sxs-lookup"><span data-stu-id="060f6-110">Host cluster support is also provided so that there is high availability for running a single instance of an adapter for purposes of ordered delivery.</span></span>  
  
 <span data-ttu-id="060f6-111">所有 BizTalk 适配器处理程序可以运行在群集主机，但从群集主机中除下面所述运行适配器处理程序并无好处。</span><span class="sxs-lookup"><span data-stu-id="060f6-111">All of the BizTalk adapter handlers can be run in a clustered host, but there is no benefit from running adapter handlers in a clustered host except as described below.</span></span> <span data-ttu-id="060f6-112">如果您的处理要求包括任何以下部分中所述的方案，则应在群集主机中运行适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="060f6-112">If your processing requirements include any of the scenarios described in the section below, then you should run adapter handlers in a clustered host.</span></span> <span data-ttu-id="060f6-113">有关设置的详细步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]群集，请参阅[通过使用 Windows Server 2008 故障转移群集或 Windows Server 2003 服务器群集的 BizTalk Server 中改进容错能力](http://go.microsoft.com/fwlink/?LinkId=156819)(<http://go.microsoft.com/fwlink/?LinkId=156819>)。</span><span class="sxs-lookup"><span data-stu-id="060f6-113">For detailed steps of setting up [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] clusters, see [Improving Fault Tolerance in BizTalk Server by Using a Windows Server 2008 Failover Cluster or Windows Server 2003 Server Cluster](http://go.microsoft.com/fwlink/?LinkId=156819) (<http://go.microsoft.com/fwlink/?LinkId=156819>).</span></span>  
  
## <a name="scenarios-for-running-adapter-handlers-in-clustered-hosts"></a><span data-ttu-id="060f6-114">有关在群集主机中运行适配器处理程序的方案</span><span class="sxs-lookup"><span data-stu-id="060f6-114">Scenarios for Running Adapter Handlers in Clustered Hosts</span></span>  
 <span data-ttu-id="060f6-115">如果您的处理要求包括任何下面列出的方案，则应在群集主机中运行适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="060f6-115">If your processing requirements include any of the scenarios listed below, then you should run adapter handlers in a clustered host.</span></span>  
  
- <span data-ttu-id="060f6-116">运行 FTP 适配器接收处理程序在群集 BizTalk 主机内</span><span class="sxs-lookup"><span data-stu-id="060f6-116">Running the FTP adapter receive handler within a clustered BizTalk host</span></span>  
  
- <span data-ttu-id="060f6-117">在群集 BizTalk 主机内运行 MSMQ 适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="060f6-117">Running MSMQ adapter handlers within a clustered BizTalk host</span></span>  
  
- <span data-ttu-id="060f6-118">运行 POP3 适配器接收处理程序在群集 BizTalk 主机内</span><span class="sxs-lookup"><span data-stu-id="060f6-118">Running the POP3 adapter receive handler within a clustered BizTalk host</span></span>  
  
- <span data-ttu-id="060f6-119">运行支持群集的 BizTalk 主机使用按序送达的接收适配器</span><span class="sxs-lookup"><span data-stu-id="060f6-119">Running a receive adapter that supports ordered delivery with a clustered BizTalk host</span></span>  
  
  <span data-ttu-id="060f6-120">有关这些方案的详细信息，请参阅[群集主机内运行适配器处理程序的注意事项](http://go.microsoft.com/fwlink/?LinkId=151284)(http://go.microsoft.com/fwlink/?LinkId=151284)。</span><span class="sxs-lookup"><span data-stu-id="060f6-120">For more information about these scenarios, see [Considerations for Running Adapter Handlers within a Clustered Host](http://go.microsoft.com/fwlink/?LinkId=151284) (http://go.microsoft.com/fwlink/?LinkId=151284).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="060f6-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="060f6-121">See Also</span></span>  
 <span data-ttu-id="060f6-122">[向外扩展接收主机](../technical-guides/scaling-out-receiving-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="060f6-122">[Scaling Out Receiving Hosts](../technical-guides/scaling-out-receiving-hosts.md) </span></span>  
 <span data-ttu-id="060f6-123">[横向扩展处理主机](../technical-guides/scaling-out-processing-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="060f6-123">[Scaling Out Processing Hosts](../technical-guides/scaling-out-processing-hosts.md) </span></span>  
 [<span data-ttu-id="060f6-124">横向扩展发送主机</span><span class="sxs-lookup"><span data-stu-id="060f6-124">Scaling Out Sending Hosts</span></span>](../technical-guides/scaling-out-sending-hosts.md)