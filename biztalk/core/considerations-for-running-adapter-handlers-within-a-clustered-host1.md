---
title: 运行中群集 Host1 的适配器处理程序的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 2016-03-17
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- high availability
- receive adapters, clustering
- clustering, POP3 adapters
- FTP adapters, clustering
- clustering, receive adapters
- NLB system
- MSMQ send handler
- MSMQ receive handler
- clustering, FTP adapters
- handlers [adapters], best practices
- hosts, clustering
- MSMQ adapters
- clustering, MSMQ adapters
- adapters, best practices
- adapters, handlers
- POP3 adapters, clustering
- MSMQ adapters, clustering
- clustering
ms.assetid: ee66663c-4f4d-4515-9df1-aacf4fc72be4
caps.latest.revision: 27
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6ac819e5255a423427e0e8c10235f73ab1ced5f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390388"
---
# <a name="considerations-for-running-adapter-handlers-within-a-clustered-host"></a><span data-ttu-id="2ae45-102">运行在群集主机内的适配器处理程序的注意事项</span><span class="sxs-lookup"><span data-stu-id="2ae45-102">Considerations for Running Adapter Handlers within a Clustered Host</span></span>
<span data-ttu-id="2ae45-103">BizTalk 主机群集支持，可用于为以下集成的 BizTalk 适配器提供高可用性： FTP 适配器、 SFTP 适配器、 MSMQ 适配器和 POP3 适配器。</span><span class="sxs-lookup"><span data-stu-id="2ae45-103">BizTalk host cluster support is available to provide high availability for the following integrated BizTalk adapters: the FTP adapter, the SFTP adapter, the MSMQ adapter, and the POP3 adapter.</span></span> <span data-ttu-id="2ae45-104">主机群集支持还提供，以便运行为目的的按序送达的适配器的单个实例的高可用性。</span><span class="sxs-lookup"><span data-stu-id="2ae45-104">Host cluster support is also provided so that there is high availability for running a single instance of an adapter for purposes of ordered delivery.</span></span>  
  
 <span data-ttu-id="2ae45-105">所有 BizTalk 适配器处理程序可以在群集主机中运行，但没有任何好处除群集主机中运行适配器处理程序，如下所述。</span><span class="sxs-lookup"><span data-stu-id="2ae45-105">All of the BizTalk adapter handlers  can be run in a clustered host but there is no benefit derived for running adapter handlers in a clustered host except as described below.</span></span> <span data-ttu-id="2ae45-106">如果您的处理要求不包括任何下面描述的方案，则应在群集主机中不运行适配器处理程序。</span><span class="sxs-lookup"><span data-stu-id="2ae45-106">If your processing requirements do not include any of the scenarios described below, then you should not run adapter handlers in a clustered host.</span></span>  
  
## <a name="running-the-ftp-or-sftp-adapter-receive-handler-within-a-clustered-biztalk-host"></a><span data-ttu-id="2ae45-107">运行 FTP 或 SFTP 适配器接收处理程序在群集 BizTalk 主机内</span><span class="sxs-lookup"><span data-stu-id="2ae45-107">Running the FTP or SFTP adapter receive handler within a clustered BizTalk host</span></span>  
 <span data-ttu-id="2ae45-108">对于大多数集成的适配器，高可用性可以通过创建多个适配器处理程序在 BizTalk 上运行的 BizTalk server 的主机实例上不同[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]BizTalk 组内的服务器。</span><span class="sxs-lookup"><span data-stu-id="2ae45-108">For most of the BizTalk Server integrated adapters, high availability can be achieved by creating multiple adapter handlers to run on BizTalk host instances on different [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] servers within a BizTalk group.</span></span> <span data-ttu-id="2ae45-109">FTP 或 SFTP 适配器接收处理程序不应但是，将配置为同时在多个 BizTalk 主机实例中运行。</span><span class="sxs-lookup"><span data-stu-id="2ae45-109">FTP or SFTP adapter receive handlers should not, however, be configured to run in multiple BizTalk host instances simultaneously.</span></span> <span data-ttu-id="2ae45-110">提出此建议是因为 FTP 或 SFTP 接收适配器使用 FTP 或 SFTP 协议从目标系统检索文件。</span><span class="sxs-lookup"><span data-stu-id="2ae45-110">This recommendation is made because the FTP or SFTP receive adapter uses the FTP or SFTP protocol to retrieve files from the target system.</span></span> <span data-ttu-id="2ae45-111">FTP 或 SFTP 协议不会锁定文件，以确保不会同时检索同一文件的多个副本正在运行的多个实例的 FTP 或 SFTP 接收适配器时。</span><span class="sxs-lookup"><span data-stu-id="2ae45-111">The FTP or SFTP protocol does not lock files to ensure that multiple copies of the same file are not retrieved simultaneously when running multiple instances of the FTP or SFTP receive adapter.</span></span>  
  
 <span data-ttu-id="2ae45-112">若要确保高可用性为 FTP 或 SFTP 接收适配器，应配置 FTP 或 SFTP 接收适配器已群集的 BizTalk 主机实例中运行。</span><span class="sxs-lookup"><span data-stu-id="2ae45-112">To provide high availability for the FTP or SFTP receive adapter, you should configure the FTP or SFTP receive adapter to run in a BizTalk host instance that has been clustered.</span></span>  
  
## <a name="running-msmq-adapter-handlers-within-a-clustered-biztalk-host"></a><span data-ttu-id="2ae45-113">在群集 BizTalk 主机内运行 MSMQ 适配器处理程序</span><span class="sxs-lookup"><span data-stu-id="2ae45-113">Running MSMQ adapter handlers within a clustered BizTalk host</span></span>  
 <span data-ttu-id="2ae45-114">若要确保 MSMQ 适配器的高可用性并确保消息由 MSMQ 适配器发送或接收的事务一致性，应执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2ae45-114">To ensure high availability for the MSMQ adapter and to ensure transactional consistency for messages sent or received by the MSMQ adapter, you should do the following:</span></span>  
  
1. <span data-ttu-id="2ae45-115">在 Windows 群集组中的群集资源配置消息队列 (MSMQ) 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机。</span><span class="sxs-lookup"><span data-stu-id="2ae45-115">Configure Message Queuing (MSMQ) as a clustered resource in a Windows cluster group on your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] computers.</span></span>  
  
2. <span data-ttu-id="2ae45-116">将群集的 MSMQ 服务添加到的资源依赖关系列表中，为群集的 BizTalk 主机。</span><span class="sxs-lookup"><span data-stu-id="2ae45-116">Add the clustered MSMQ service to the list of Resource dependencies for the clustered BizTalk host.</span></span> <span data-ttu-id="2ae45-117">这可确保在群集的 BizTalk 主机始终开始之后发生故障转移群集的 MSMQ 服务。</span><span class="sxs-lookup"><span data-stu-id="2ae45-117">This ensures that the clustered BizTalk host always starts after the clustered MSMQ service in failover scenarios.</span></span>  
  
3. <span data-ttu-id="2ae45-118">配置 MSMQ 适配器发送和接收处理程序已配置为群集 MSMQ 资源所在的群集组中的群集资源的 BizTalk 主机实例中。</span><span class="sxs-lookup"><span data-stu-id="2ae45-118">Configure the MSMQ adapter send and receive handlers in a BizTalk host instance that has been configured as a cluster resource in the same cluster group as the clustered MSMQ resource.</span></span>  
  
   <span data-ttu-id="2ae45-119">由于以下原因建议使用以下步骤：</span><span class="sxs-lookup"><span data-stu-id="2ae45-119">These steps are recommended for the following reasons:</span></span>  
  
   <span data-ttu-id="2ae45-120">**MSMQ 适配器接收处理程序**– MSMQ 4.0 (Windows Server 2008) 之前的 MSMQ 版本不支持远程事务性读取，支持仅本地事务读取。</span><span class="sxs-lookup"><span data-stu-id="2ae45-120">**MSMQ adapter receive handler** – MSMQ versions prior to MSMQ 4.0 (Windows Server 2008) do not support remote transactional reads; only local transactional reads are supported.</span></span> <span data-ttu-id="2ae45-121">在这种情况下，MSMQ 适配器接收处理程序必须是本地群集的消息队列服务，以完成本地事务读取使用 MSMQ 适配器的主机实例中运行。</span><span class="sxs-lookup"><span data-stu-id="2ae45-121">In this case, the MSMQ adapter receive handler must run in a host instance that is local to the clustered Message Queuing service to complete local transactional reads with the MSMQ adapter.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2ae45-122">MSMQ 适配器接收处理程序要求在接收处理程序主机实例运行的同一台计算机上正在运行消息队列服务的本地非群集实例。</span><span class="sxs-lookup"><span data-stu-id="2ae45-122">The MSMQ adapter receive handler requires that a local non-clustered instance of the Message Queuing service is running on the same computer that the receive handler host instance is running on.</span></span>  
  
 <span data-ttu-id="2ae45-123">**MSMQ 适配器发送处理程序**-若要确保所做的 MSMQ 适配器，使用 MSMQ 适配器发送处理程序的传出队列的事务发送的一致性，以便如果 MSMQ 服务的传出队列失败则可能应具备高可用性已恢复。</span><span class="sxs-lookup"><span data-stu-id="2ae45-123">**MSMQ adapter send handler** - To ensure the consistency of transactional sends made by the MSMQ adapter, the outgoing queue used by the MSMQ adapter send handler should be highly available so that if the MSMQ service for the outgoing queue fails it can be resumed.</span></span> <span data-ttu-id="2ae45-124">在群集组中配置群集的消息 Queuingresource 和 MSMQ 适配器处理程序将确保使用 MSMQ 适配器发送处理程序的传出队列具有高可用性。</span><span class="sxs-lookup"><span data-stu-id="2ae45-124">Configuring a clustered Message Queuingresource and the MSMQ adapter handlers in a cluster group will ensure that the outgoing queue used by the MSMQ adapter send handler will be highly available.</span></span> <span data-ttu-id="2ae45-125">在的消息队列服务失败，这将降低消息丢失的可能性。</span><span class="sxs-lookup"><span data-stu-id="2ae45-125">This will mitigate the possibility of message loss in the event that the Message Queuing service fails.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2ae45-126">MSMQ 接收位置是否**仅**接收来自远程 MSMQ 服务器上的 MSMQ 队列，则可以通过运行 MSMQ 实现高可用性 BizTalk 组中接收多个 BizTalk 计算机上的主机。</span><span class="sxs-lookup"><span data-stu-id="2ae45-126">If the MSMQ receive location is **only** receiving from MSMQ queues on a remote MSMQ server, then high availability can be achieved by running the MSMQ receive host on multiple BizTalk computers in the BizTalk group.</span></span>  <span data-ttu-id="2ae45-127">若要为 MSMQ 提供高可用性，必须确保远程 MSMQ 服务器正在使用中 Windows 故障转移群集。</span><span class="sxs-lookup"><span data-stu-id="2ae45-127">To provide high availability for MSMQ, you must ensure the remote MSMQ server is using failover clustering in Windows.</span></span>  <span data-ttu-id="2ae45-128">如果使用的事务性队列，必须运行远程 MSMQ 服务器 MSMQ 4.0 (Windows Server 2008) 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="2ae45-128">If using transactional queues, the remote MSMQ server must be running MSMQ 4.0 (Windows Server 2008) or above.</span></span>  
  
## <a name="running-the-pop3-adapter-receive-handler-within-a-clustered-biztalk-host"></a><span data-ttu-id="2ae45-129">运行 POP3 适配器接收处理程序在群集 BizTalk 主机内</span><span class="sxs-lookup"><span data-stu-id="2ae45-129">Running the POP3 adapter receive handler within a clustered BizTalk host</span></span>  
 <span data-ttu-id="2ae45-130">POP3 适配器接收处理程序不需要将配置为群集的 BizTalk 主机中运行，除非适配器从中进行读取的 POP3 服务器允许对同一邮箱进行多个并发连接。</span><span class="sxs-lookup"><span data-stu-id="2ae45-130">The POP3 adapter receive handler does not need to be configured to run in a clustered BizTalk host unless the POP3 server that the adapter is reading from allows multiple concurrent connections to be made to the same mailbox.</span></span> <span data-ttu-id="2ae45-131">如果 POP3 适配器连接到的 POP3 服务器允许对其邮箱，多个并发连接，则我们建议您确保高可用性通过配置单个 POP3 适配器的 POP3 适配器接收处理程序为 BizTalk 主机中运行已群集的实例。</span><span class="sxs-lookup"><span data-stu-id="2ae45-131">If the POP3 server that the POP3 adapter is connected to permits multiple concurrent connections to its mailboxes, then we recommend that you ensure high availability for the POP3 adapter by configuring a single POP3 adapter receive handler to run in a BizTalk host instance that has been clustered.</span></span> <span data-ttu-id="2ae45-132">提出此建议以确保不会同时检索同一电子邮件的多个副本正在运行的多个实例的 POP3 接收适配器时。</span><span class="sxs-lookup"><span data-stu-id="2ae45-132">This recommendation is made to ensure that multiple copies of the same e-mail message are not retrieved simultaneously when running multiple instances of the POP3 receive adapter.</span></span>  
  
## <a name="running-a-receive-adapter-that-supports-ordered-delivery-with-a-clustered-biztalk-host"></a><span data-ttu-id="2ae45-133">运行支持群集的 BizTalk 主机使用按序送达的接收适配器</span><span class="sxs-lookup"><span data-stu-id="2ae45-133">Running a receive adapter that supports ordered delivery with a clustered BizTalk host</span></span>  
 <span data-ttu-id="2ae45-134">MSMQ 和 MQSeries 集成的适配器能够将文档提交给[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收的顺序。</span><span class="sxs-lookup"><span data-stu-id="2ae45-134">The MSMQ and MQSeries integrated adapters provide the ability to submit documents to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] in the order that they were received.</span></span> <span data-ttu-id="2ae45-135">正确实现此功能需要单个实例的这些接收适配器在任何给定时间运行。</span><span class="sxs-lookup"><span data-stu-id="2ae45-135">Correct implementation of this functionality requires that only a single instance of these receive adapters be running at any given time.</span></span> <span data-ttu-id="2ae45-136">若要为这些适配器的单个实例提供高可用性，应将它们配置为在群集 BizTalk 主机实例中运行。</span><span class="sxs-lookup"><span data-stu-id="2ae45-136">To provide high availability for a single instance of these adapters, they should be configured to run in a clustered BizTalk host instance.</span></span>