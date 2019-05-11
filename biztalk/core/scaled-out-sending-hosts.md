---
title: 向外扩展发送主机 |Microsoft Docs
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
ms.openlocfilehash: 80fcc73aa4d0f2d65a097bd47d06fc75305abdc3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65309068"
---
# <a name="scaled-out-sending-hosts"></a><span data-ttu-id="b1efe-102">向外扩展发送主机</span><span class="sxs-lookup"><span data-stu-id="b1efe-102">Scaled-Out Sending Hosts</span></span>
<span data-ttu-id="b1efe-103">向外扩展发送主机可确保的发送功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]高度可用。</span><span class="sxs-lookup"><span data-stu-id="b1efe-103">A scaled-out sending host makes sure that the sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is highly available.</span></span> <span data-ttu-id="b1efe-104">如果用于发送消息，可以向主机添加多台计算机，可以运行多个发送主机实例以实现冗余和高可用性。</span><span class="sxs-lookup"><span data-stu-id="b1efe-104">If you add multiple computers to a host for sending messages, you can run multiple sending host instances for redundancy and high availability.</span></span>  
  
 <span data-ttu-id="b1efe-105">下图显示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]通过在两台计算机上运行的发送主机实例以确保发送主机提供高可用性的部署。</span><span class="sxs-lookup"><span data-stu-id="b1efe-105">The following figure shows a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment that provides high availability for the sending host by having two computers that are running instances of the sending host.</span></span> <span data-ttu-id="b1efe-106">请注意，在此图中的接收和处理主机并不高度可用。</span><span class="sxs-lookup"><span data-stu-id="b1efe-106">Note that in this figure the receiving and processing hosts are not highly available.</span></span>  
  
 <span data-ttu-id="b1efe-107">![缩放&#45;扩展发送主机](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span><span class="sxs-lookup"><span data-stu-id="b1efe-107">![Scaled&#45;Out Sending Host](../core/media/tdi-ha-scalesend.gif "TDI_HA_ScaleSend")</span></span>  
  
## <a name="high-availability-for-sending-hosts"></a><span data-ttu-id="b1efe-108">发送主机的高可用性</span><span class="sxs-lookup"><span data-stu-id="b1efe-108">High Availability for Sending Hosts</span></span>  
 <span data-ttu-id="b1efe-109">发送功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]类似于处理意义上说，这些活动都不需要主机和数据之间的关联中的功能。</span><span class="sxs-lookup"><span data-stu-id="b1efe-109">Sending functionality in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is similar to processing functionality in the sense that neither of these activities requires any association between host and data.</span></span> <span data-ttu-id="b1efe-110">正如任何处理主机实例可以从 MessageBox 数据库中检索消息和处理它们，任何发送主机实例可以从 MessageBox 数据库中检索消息并将其发送。</span><span class="sxs-lookup"><span data-stu-id="b1efe-110">Just as any processing host instance can retrieve messages from the MessageBox database and process them, any sending host instance can retrieve messages from the MessageBox database and send them.</span></span> <span data-ttu-id="b1efe-111">因此，发送主机提供高可用性意味着使用确保处理主机高度可用的相同方法。</span><span class="sxs-lookup"><span data-stu-id="b1efe-111">Therefore, providing high availability for the sending hosts means that you use the same techniques as for providing high availability for the processing hosts.</span></span>  
  
## <a name="scaling-the-biztalk-server-send-adapters"></a><span data-ttu-id="b1efe-112">扩展 BizTalk Server 发送适配器</span><span class="sxs-lookup"><span data-stu-id="b1efe-112">Scaling the BizTalk Server Send Adapters</span></span>  
  
### <a name="high-availability-for-the-msmq-send-adapter"></a><span data-ttu-id="b1efe-113">发送适配器在 msmq 的高可用性</span><span class="sxs-lookup"><span data-stu-id="b1efe-113">High Availability for the MSMQ Send Adapter</span></span>  
 <span data-ttu-id="b1efe-114">MSMQ 发送适配器应群集 MSMQ 服务、 群集与群集的 MSMQ 服务位于同一组中的 BizTalk 主机和配置为提供高可用性 MSMQ 发送处理程序在此群集的 BizTalk 主机中运行。</span><span class="sxs-lookup"><span data-stu-id="b1efe-114">To provide high availability for the MSMQ send adapter you should cluster the MSMQ service, cluster a BizTalk host in the same group as the clustered MSMQ service, and configure the MSMQ send handler to run in this clustered BizTalk host.</span></span> <span data-ttu-id="b1efe-115">这应进行以确保 MSMQ 适配器启动的事务发送的一致性。</span><span class="sxs-lookup"><span data-stu-id="b1efe-115">This should be done to ensure the consistency of transactional sends initiated by the MSMQ adapter.</span></span> <span data-ttu-id="b1efe-116">有关详细信息请参阅[群集主机内运行适配器处理程序的注意事项](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)。</span><span class="sxs-lookup"><span data-stu-id="b1efe-116">For more information see [Considerations for Running Adapter Handlers within a Clustered Host](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md).</span></span>  
  
### <a name="high-availability-for-the-windows-sharepoint-services-send-adapter"></a><span data-ttu-id="b1efe-117">发送适配器的 Windows SharePoint Services 的高可用性</span><span class="sxs-lookup"><span data-stu-id="b1efe-117">High Availability for the Windows SharePoint Services Send Adapter</span></span>  
 <span data-ttu-id="b1efe-118">若要为 Windows SharePoint Services 发送适配器提供高可用性，请向引用相同的文档库的每台主机计算机上的发送端口与发送主机添加多台计算机。</span><span class="sxs-lookup"><span data-stu-id="b1efe-118">To provide high availability for the Windows SharePoint Services send adapter, add multiple computers to the send host with the send port on each host computer referencing the same document library.</span></span> <span data-ttu-id="b1efe-119">Windows SharePoint Services 适配器通过调入 SharePoint 计算机上安装 BizTalk 的 Windows SharePoint Services web 服务将消息发送到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="b1efe-119">The Windows SharePoint Services adapter sends messages to SharePoint by calling into the Windows SharePoint Services web service installed by BizTalk on the SharePoint machine.</span></span> <span data-ttu-id="b1efe-120">有关 SharePoint 允许将消息推送到同一 HTTP URL 指向 SharePoint NLB 安装的多个主机实例运行同一个发送端口的发送适配器，BizTalk Server 提供高可用性。</span><span class="sxs-lookup"><span data-stu-id="b1efe-120">BizTalk Server provides high availability for the SharePoint send adapter by letting you run the same send ports on multiple host instances that push messages to the same HTTP URL pointing to a SharePoint NLB installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1efe-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="b1efe-121">See Also</span></span>  
 <span data-ttu-id="b1efe-122">[为 BizTalk 主机提供高可用性](../core/providing-high-availability-for-biztalk-hosts.md) </span><span class="sxs-lookup"><span data-stu-id="b1efe-122">[Providing High Availability for BizTalk Hosts](../core/providing-high-availability-for-biztalk-hosts.md) </span></span>  
 [<span data-ttu-id="b1efe-123">在群集主机内运行适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="b1efe-123">Considerations for Running Adapter Handlers within a Clustered Host</span></span>](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)