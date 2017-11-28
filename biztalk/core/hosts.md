---
title: "主机 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host instances, servers
- hosts, isolated
- host instances, relationships
- hosts, in-process hosts
- servers, hosts
- hosts, host instances
- hosts, relationships
- In-Process BizTalk Host groups
- hosts, about hosts
- hosts, untrusted
- host instances, hosts
- hosts, servers
- hosts
- servers, host instances
- Isolated Host Users group
- hosts, trusted
ms.assetid: d96537e0-e679-407a-8870-34a663acfed9
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a1c61995bca06203208c057762db7f737afd6eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="hosts"></a><span data-ttu-id="24fd5-102">主机</span><span class="sxs-lookup"><span data-stu-id="24fd5-102">Hosts</span></span>
<span data-ttu-id="24fd5-103">BizTalk 主机对象表示在其中部署服务、管道和其他项目的零个或多个运行时进程的逻辑组。</span><span class="sxs-lookup"><span data-stu-id="24fd5-103">The BizTalk Host object represents a logical set of zero or more runtime processes in which you can deploy services, pipelines, and other artifacts.</span></span> <span data-ttu-id="24fd5-104">主机对象还表示运行时实例（零个或多个）的集合，是运行部署项的物理位置。</span><span class="sxs-lookup"><span data-stu-id="24fd5-104">The Host object also represents a collection of runtime instances (zero or more) where the deployed items physically run.</span></span>  
  
 <span data-ttu-id="24fd5-105">在创建主机（逻辑容器）后，您可以向主机添加物理 BizTalk Server（主机实例）。</span><span class="sxs-lookup"><span data-stu-id="24fd5-105">After you create a host (a logical container), you can add physical BizTalk servers (host instances) to the host.</span></span> <span data-ttu-id="24fd5-106">不能向同一主机多次添加 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="24fd5-106">You cannot add a BizTalk server to the same host more than once.</span></span> <span data-ttu-id="24fd5-107">可将单个主机实例添加到多个主机上。</span><span class="sxs-lookup"><span data-stu-id="24fd5-107">A single host instance can be added to multiple hosts.</span></span>  
  
 <span data-ttu-id="24fd5-108">项-适配器处理程序，如接收位置 （包括管道） 和业务流程-BizTalk 中包含的主机可以执行以下功能：</span><span class="sxs-lookup"><span data-stu-id="24fd5-108">Items—such as adapter handlers, receive locations (including pipelines), and orchestrations—contained in BizTalk hosts can perform the following functions:</span></span>  
  
-   <span data-ttu-id="24fd5-109">**接收**。</span><span class="sxs-lookup"><span data-stu-id="24fd5-109">**Receiving**.</span></span> <span data-ttu-id="24fd5-110">在接收位置中提取消息后，这些项对其进行初始处理。</span><span class="sxs-lookup"><span data-stu-id="24fd5-110">These items do the initial processing of messages after they are picked up in a receive location.</span></span> <span data-ttu-id="24fd5-111">当主机包含接收项（例如接收位置或管道）时，该主机将充当安全边界，而且消息的解码和解密都将发生在主机内的管道中。</span><span class="sxs-lookup"><span data-stu-id="24fd5-111">When a host contains a receiving item, such as a receive location or pipeline, it acts as a security boundary, and the message decoding and decrypting occurs in a pipeline within the host.</span></span>  
  
-   <span data-ttu-id="24fd5-112">**发送**。</span><span class="sxs-lookup"><span data-stu-id="24fd5-112">**Sending**.</span></span> <span data-ttu-id="24fd5-113">在将消息发送给发送端口前，这些项对其进行最终处理。</span><span class="sxs-lookup"><span data-stu-id="24fd5-113">These items do the final processing of messages before they are sent out to the send port.</span></span> <span data-ttu-id="24fd5-114">当主机包含发送项（例如发送端口或管道）时，该主机将充当安全边界，而且消息的签名和加密都将发生在主机内的管道中。</span><span class="sxs-lookup"><span data-stu-id="24fd5-114">When a host contains a sending item, such as a send port or pipeline, the host acts as a security boundary, and the message signing and encryption occurs in a pipeline within the host.</span></span>  
  
-   <span data-ttu-id="24fd5-115">**处理**。</span><span class="sxs-lookup"><span data-stu-id="24fd5-115">**Processing**.</span></span> <span data-ttu-id="24fd5-116">这些项将根据业务流程中的指令来处理消息。</span><span class="sxs-lookup"><span data-stu-id="24fd5-116">These items process messages based on the instructions in an orchestration.</span></span>  
  
 <span data-ttu-id="24fd5-117">一个 BizTalk 主机可以包含接收、发送和处理消息的项。</span><span class="sxs-lookup"><span data-stu-id="24fd5-117">One BizTalk Host can contain items that receive, send, and process messages.</span></span> <span data-ttu-id="24fd5-118">建议为每个功能创建不同的主机，以创建安全边界，从而有助于管理。</span><span class="sxs-lookup"><span data-stu-id="24fd5-118">It is recommended that you create different hosts for each function to create security boundaries and facilitate management.</span></span> <span data-ttu-id="24fd5-119">特别是，建议对于处理操作和接收/发送分别使用不同的主机，并且分隔可信任项和不可信任项。</span><span class="sxs-lookup"><span data-stu-id="24fd5-119">In particular, it is recommended that you use different hosts for processing and for receive/send, and that you separate trusted and non-trusted items.</span></span>  
  
 <span data-ttu-id="24fd5-120">下图显示了服务器、主机和主机实例之间的关系：</span><span class="sxs-lookup"><span data-stu-id="24fd5-120">The following figure shows the relationship between servers, hosts, and host instances.</span></span>  
  
 <span data-ttu-id="24fd5-121">![主机、 主机实例和服务器关系](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span><span class="sxs-lookup"><span data-stu-id="24fd5-121">![Hosts, host instances, and server relationships](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span></span>  
<span data-ttu-id="24fd5-122">主机、 主机实例和服务器之间的关系</span><span class="sxs-lookup"><span data-stu-id="24fd5-122">Relationship between hosts, host instances, and servers</span></span>  
  
 <span data-ttu-id="24fd5-123">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="24fd5-123">For more information about Host Instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
 <span data-ttu-id="24fd5-124">根据物理配置和承载适配器的类型，有两种类型的主机：进程内主机和独立主机。</span><span class="sxs-lookup"><span data-stu-id="24fd5-124">Based on the physical configuration and type of adapter hosted, there are two types of hosts: in-process hosts and isolated hosts.</span></span>  
  
## <a name="in-process-hosts"></a><span data-ttu-id="24fd5-125">进程内主机</span><span class="sxs-lookup"><span data-stu-id="24fd5-125">In-process Hosts</span></span>  
 <span data-ttu-id="24fd5-126">进程内主机表示管理员使用 Windows 管理规范 (WMI) 和 BizTalk 管理控制台创建、删除和完全控制的服务实例。</span><span class="sxs-lookup"><span data-stu-id="24fd5-126">In-process hosts represent service instances that an administrator creates, deletes, and fully controls with Windows Management Instrumentation (WMI) and the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="24fd5-127">进程内主机具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="24fd5-127">In-process hosts have the following characteristics:</span></span>  
  
-   <span data-ttu-id="24fd5-128">可以将任何业务流程登记到进程内主机中。</span><span class="sxs-lookup"><span data-stu-id="24fd5-128">You can enlist any orchestration into an in-process host.</span></span>  
  
-   <span data-ttu-id="24fd5-129">进程内主机可以作为任何发送处理程序的宿主。</span><span class="sxs-lookup"><span data-stu-id="24fd5-129">An in-process host can host any send handler.</span></span>  
  
-   <span data-ttu-id="24fd5-130">进程内主机可以作为除 SOAP 和 HTTP 以外的任何接收处理程序的宿主：</span><span class="sxs-lookup"><span data-stu-id="24fd5-130">An in-process host can host any of the receive handlers except for SOAP and HTTP:</span></span>  
  
    -   <span data-ttu-id="24fd5-131">FILE</span><span class="sxs-lookup"><span data-stu-id="24fd5-131">FILE</span></span>  
  
    -   <span data-ttu-id="24fd5-132">FTP</span><span class="sxs-lookup"><span data-stu-id="24fd5-132">FTP</span></span>  
  
    -   <span data-ttu-id="24fd5-133">MQSeries</span><span class="sxs-lookup"><span data-stu-id="24fd5-133">MQSeries</span></span>  
  
    -   <span data-ttu-id="24fd5-134">MSMQ</span><span class="sxs-lookup"><span data-stu-id="24fd5-134">MSMQ</span></span>  
  
    -   <span data-ttu-id="24fd5-135">POP3</span><span class="sxs-lookup"><span data-stu-id="24fd5-135">POP3</span></span>  
  
    -   <span data-ttu-id="24fd5-136">SQL</span><span class="sxs-lookup"><span data-stu-id="24fd5-136">SQL</span></span>  
  
    -   <span data-ttu-id="24fd5-137">Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="24fd5-137">Windows SharePoint Services</span></span>  
  
-   <span data-ttu-id="24fd5-138">在中创建第一个进程内主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署**默认主机**并且不能删除它。</span><span class="sxs-lookup"><span data-stu-id="24fd5-138">The first in-process host you create in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment is the **default host** and you cannot delete it.</span></span> <span data-ttu-id="24fd5-139">BizTalk 消息队列适配器将默认主机用于静态处理程序配置。</span><span class="sxs-lookup"><span data-stu-id="24fd5-139">The BizTalk Message Queuing adapter uses the default host for static handler configuration.</span></span> <span data-ttu-id="24fd5-140">添加适配器会自动创建默认主机的接收和发送端口。</span><span class="sxs-lookup"><span data-stu-id="24fd5-140">Adding an adapter automatically creates receive and send ports for the default host.</span></span>  
  
## <a name="isolated-hosts"></a><span data-ttu-id="24fd5-141">独立主机</span><span class="sxs-lookup"><span data-stu-id="24fd5-141">Isolated Hosts</span></span>  
 <span data-ttu-id="24fd5-142">独立主机表示解决方案开发人员以编程的方式创建、删除和控制的服务实例。</span><span class="sxs-lookup"><span data-stu-id="24fd5-142">Isolated hosts represent service instances that a solutions developer programmatically creates, deletes, and controls.</span></span> <span data-ttu-id="24fd5-143">管理员使用 WMI 和 BizTalk 管理控制台来配置这些主机（例如，配置主机服务帐户和受信任验证）。</span><span class="sxs-lookup"><span data-stu-id="24fd5-143">An administrator uses WMI and the BizTalk Administration Console to configure these hosts (for example, to configure the host service account and authentication trust).</span></span>  
  
 <span data-ttu-id="24fd5-144">独立主机主要作为必须运行于常规 BizTalk Server 运行时进程之外的适配器的宿主。</span><span class="sxs-lookup"><span data-stu-id="24fd5-144">Isolated hosts primarily host adapters that must run outside of the normal BizTalk Server runtime process.</span></span> <span data-ttu-id="24fd5-145">例如，使用独立主机作为外部进程（如 ISAPI 扩展和 ASP.NET）适配器的宿主。</span><span class="sxs-lookup"><span data-stu-id="24fd5-145">For example, you use isolated hosts to host adapters for external processes such as ISAPI extensions and ASP.NET.</span></span>  
  
 <span data-ttu-id="24fd5-146">独立主机具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="24fd5-146">Isolated hosts have the following characteristics:</span></span>  
  
-   <span data-ttu-id="24fd5-147">您不能将业务流程登记到独立主机中。</span><span class="sxs-lookup"><span data-stu-id="24fd5-147">You cannot enlist orchestrations into an isolated host.</span></span>  
  
-   <span data-ttu-id="24fd5-148">独立主机不能作为发送处理程序的宿主。</span><span class="sxs-lookup"><span data-stu-id="24fd5-148">An isolated host cannot host send handlers.</span></span>  
  
-   <span data-ttu-id="24fd5-149">独立主机仅能作为与 HTTP/S 和 SOAP 适配器（独立类型适配器）相关联的接收处理程序的宿主。</span><span class="sxs-lookup"><span data-stu-id="24fd5-149">An isolated host can host only the receive handlers associated with HTTP/S and SOAP adapters (the isolated-type adapters).</span></span>  
  
-   <span data-ttu-id="24fd5-150">独立主机不能作为跟踪的宿主。</span><span class="sxs-lookup"><span data-stu-id="24fd5-150">An isolated host cannot host tracking.</span></span>  
  
-   <span data-ttu-id="24fd5-151">独立主机不能为默认主机。</span><span class="sxs-lookup"><span data-stu-id="24fd5-151">An isolated host cannot be the default host.</span></span>  
  
-   <span data-ttu-id="24fd5-152">隔离主机的状态始终是**状态不可用**。</span><span class="sxs-lookup"><span data-stu-id="24fd5-152">The status of an isolated host is always **Status Unavailable**.</span></span> <span data-ttu-id="24fd5-153">BizTalk Server 不访问外部进程的状态信息。</span><span class="sxs-lookup"><span data-stu-id="24fd5-153">BizTalk Server does not access the status information for external processes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24fd5-154">只要主机实例共享相同的安全配置（受信任验证），它们就可以共享相同的服务帐户。</span><span class="sxs-lookup"><span data-stu-id="24fd5-154">Host instances can share the same service account as long as they share the same security configuration (authentication trust).</span></span>  
  
## <a name="trusted-and-untrusted-hosts"></a><span data-ttu-id="24fd5-155">可信任主机和不可信任主机</span><span class="sxs-lookup"><span data-stu-id="24fd5-155">Trusted and Untrusted Hosts</span></span>  
 <span data-ttu-id="24fd5-156">BizTalk Server 将主机标识为受信任验证来表明受信任主机排队到 MessageBox 数据库的消息的发件人是一个实体而不是受信任主机本身。</span><span class="sxs-lookup"><span data-stu-id="24fd5-156">BizTalk Server enables hosts identified as authentication trusted to indicate that the sender of a message that the trusted host is queuing to the MessageBox database is an entity other than the trusted host itself.</span></span> <span data-ttu-id="24fd5-157">受信任验证的主要用途是将管道解析为产品 ID (PID)，并将该 PID 传递到需要该 ID 的服务，以用于授权和出站参与方解析，以及将发件人 Windows 安全 ID (SSID) 传输到需要该 ID 的服务，以用于业务流程操作授权。</span><span class="sxs-lookup"><span data-stu-id="24fd5-157">The primary purposes of authentication trust are to enable pipelines to resolve to a Product ID (PID) and pass that PID along to consuming services for use in authorization and outbound party resolution, and to enable the transmission of the sender Windows Security ID (SSID) along to consuming services for use in orchestration action authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24fd5-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24fd5-158">See Also</span></span>  
 <span data-ttu-id="24fd5-159">[主机实例](../core/host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="24fd5-159">[Host Instances](../core/host-instances.md) </span></span>  
 [<span data-ttu-id="24fd5-160">管理 BizTalk 主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="24fd5-160">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)  
 [<span data-ttu-id="24fd5-161">实体</span><span class="sxs-lookup"><span data-stu-id="24fd5-161">Entities</span></span>](../core/entities.md)