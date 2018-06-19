---
title: 向外扩展发送主机 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- hosts, sending
- FTP adapters, high availability
- EDI adapters, high availability
- hosts, high availability
- hosts, availability
- Windows SharePoint Services adapters, high availability
- scaling, hosts
- hosts, clustering
- scaling, adapters
- high availability, hosts
- clustering, hosts
- MSMQ adapters, high availability
- hosts, planning
- hosts, scaling
- adapters, scaling
ms.assetid: a3d79e0b-8c1e-471c-88e2-623600dfd81a
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 50659e267731caafe4bad6dabe89944cb16c0c98
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007742"
---
# <a name="scaled-out-sending-hosts"></a><span data-ttu-id="2dccc-102">扩展的发送主机</span><span class="sxs-lookup"><span data-stu-id="2dccc-102">Scaled-Out Sending Hosts</span></span>
<span data-ttu-id="2dccc-103">向外扩展的发送主机可确保中的发送功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高度可用。</span><span class="sxs-lookup"><span data-stu-id="2dccc-103">A scaled-out sending host makes sure that the sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is highly available.</span></span> <span data-ttu-id="2dccc-104">如果向发送消息的主机添加多台计算机，您就可以运行多个发送主机实例以实现冗余和高可用性。</span><span class="sxs-lookup"><span data-stu-id="2dccc-104">If you add multiple computers to a host for sending messages, you can run multiple sending host instances for redundancy and high availability.</span></span>  
  
 <span data-ttu-id="2dccc-105">下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发送主机通过在两台计算机正在运行的发送主机的实例提供高可用性的部署。</span><span class="sxs-lookup"><span data-stu-id="2dccc-105">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability for the sending host by having two computers that are running instances of the sending host.</span></span> <span data-ttu-id="2dccc-106">请注意，此图中的接收主机和处理主机并不高度可用。</span><span class="sxs-lookup"><span data-stu-id="2dccc-106">Note that in this figure the receiving and processing hosts are not highly available.</span></span>  
  
 <span data-ttu-id="2dccc-107">![缩放 &#45; 出发送主机](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span><span class="sxs-lookup"><span data-stu-id="2dccc-107">![Scaled&#45;Out Sending Host](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span></span>  
  
## <a name="high-availability-for-sending-hosts"></a><span data-ttu-id="2dccc-108">发送主机的高可用性</span><span class="sxs-lookup"><span data-stu-id="2dccc-108">High Availability for Sending Hosts</span></span>  
 <span data-ttu-id="2dccc-109">发送功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]类似于处理在这些活动都不需要任何主机和数据之间的关联的意义上的功能。</span><span class="sxs-lookup"><span data-stu-id="2dccc-109">Sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is similar to processing functionality in the sense that neither of these activities requires any association between host and data.</span></span> <span data-ttu-id="2dccc-110">正如任何处理主机实例可从 MessageBox 数据库中检索消息并处理这些消息一样，任何发送主机实例也可以从 MessageBox 数据库中检索消息并发送这些消息。</span><span class="sxs-lookup"><span data-stu-id="2dccc-110">Just as any processing host instance can retrieve messages from the MessageBox database and process them, any sending host instance can retrieve messages from the MessageBox database and send them.</span></span> <span data-ttu-id="2dccc-111">因此，若要确保发送主机的高可用性，则需要使用确保处理主机的高可用性的相同方法。</span><span class="sxs-lookup"><span data-stu-id="2dccc-111">Therefore, providing high availability for the sending hosts means that you use the same techniques as for providing high availability for the processing hosts.</span></span>  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a><span data-ttu-id="2dccc-112">扩展 BizTalk Server 发送适配器</span><span class="sxs-lookup"><span data-stu-id="2dccc-112">Scaling the BizTalk Server Send Adapters</span></span>  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a><span data-ttu-id="2dccc-113">MSMQ 发送适配器的高可用性</span><span class="sxs-lookup"><span data-stu-id="2dccc-113">High Availability for the MSMQ Send Adapter</span></span>  
 <span data-ttu-id="2dccc-114">为确保 MSMQ 发送适配器的高可用性，您应群集 MSMQ 服务、群集与群集的 MSMQ 服务位于同一组中的 BizTalk 主机，并将 MSMQ 发送处理程序配置为在此群集的 BizTalk 主机中运行。</span><span class="sxs-lookup"><span data-stu-id="2dccc-114">To provide high availability for the MSMQ send adapter you should cluster the MSMQ service, cluster a BizTalk host in the same group as the clustered MSMQ service, and configure the MSMQ send handler to run in this clustered BizTalk host.</span></span> <span data-ttu-id="2dccc-115">您应完成以上操作以确保 MSMQ 适配器启动的事务发送的一致性。</span><span class="sxs-lookup"><span data-stu-id="2dccc-115">This should be done to ensure the consistency of transactional sends initiated by the MSMQ adapter.</span></span> <span data-ttu-id="2dccc-116">有关详细信息请参阅[在群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。</span><span class="sxs-lookup"><span data-stu-id="2dccc-116">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a><span data-ttu-id="2dccc-117">Windows SharePoint Services 发送适配器的高可用性</span><span class="sxs-lookup"><span data-stu-id="2dccc-117">High Availability for the Windows SharePoint Services Send Adapter</span></span>  
 <span data-ttu-id="2dccc-118">为确保 Windows SharePoint Services 发送适配器的高可用性，请向发送主机添加多台计算机，并且每台主机计算机上的发送端口需要引用同一个文档库。</span><span class="sxs-lookup"><span data-stu-id="2dccc-118">To provide high availability for the Windows SharePoint Services send adapter, add multiple computers to the send host with the send port on each host computer referencing the same document library.</span></span> <span data-ttu-id="2dccc-119">Windows SharePoint Services 适配器通过调入 SharePoint 计算机上安装 BizTalk 的 Windows SharePoint Services web 服务将消息发送到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="2dccc-119">The Windows SharePoint Services adapter sends messages to SharePoint by calling into the Windows SharePoint Services web service installed by BizTalk on the SharePoint machine.</span></span> <span data-ttu-id="2dccc-120">BizTalk Server 提供高可用性 SharePoint 通过让多个消息推送到相同的 SharePoint NLB 安装所指向的 HTTP URL 的主机实例运行相同的发送端口发送适配器。</span><span class="sxs-lookup"><span data-stu-id="2dccc-120">BizTalk Server provides high availability for the SharePoint send adapter by letting you run the same send ports on multiple host instances that push messages to the same HTTP URL pointing to a SharePoint NLB installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dccc-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2dccc-121">See Also</span></span>  
 <span data-ttu-id="2dccc-122">[为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="2dccc-122">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="2dccc-123">在群集主机内运行适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="2dccc-123">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)