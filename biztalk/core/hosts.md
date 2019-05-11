---
title: 主机 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9785e734579c88a790f2a07a292fef476be5d6d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387523"
---
# <a name="hosts"></a><span data-ttu-id="2f398-102">主机</span><span class="sxs-lookup"><span data-stu-id="2f398-102">Hosts</span></span>
<span data-ttu-id="2f398-103">BizTalk 主机对象表示的零个或多个运行时进程在其中部署服务、 管道和其他项目的逻辑组。</span><span class="sxs-lookup"><span data-stu-id="2f398-103">The BizTalk Host object represents a logical set of zero or more runtime processes in which you can deploy services, pipelines, and other artifacts.</span></span> <span data-ttu-id="2f398-104">该主机对象还表示已部署的项以物理方式运行的运行时实例 （零个或多个） 的集合。</span><span class="sxs-lookup"><span data-stu-id="2f398-104">The Host object also represents a collection of runtime instances (zero or more) where the deployed items physically run.</span></span>  
  
 <span data-ttu-id="2f398-105">创建主机 （逻辑容器） 后，您可以向主机添加物理 BizTalk server （主机实例）。</span><span class="sxs-lookup"><span data-stu-id="2f398-105">After you create a host (a logical container), you can add physical BizTalk servers (host instances) to the host.</span></span> <span data-ttu-id="2f398-106">不能超过一次到同一主机中添加 BizTalk server。</span><span class="sxs-lookup"><span data-stu-id="2f398-106">You cannot add a BizTalk server to the same host more than once.</span></span> <span data-ttu-id="2f398-107">单个主机实例可以添加到多个主机。</span><span class="sxs-lookup"><span data-stu-id="2f398-107">A single host instance can be added to multiple hosts.</span></span>  
  
 <span data-ttu-id="2f398-108">项 — 如适配器处理程序、 接收位置 （包括管道） 和业务流程，包含在 BizTalk 主机可以执行以下功能：</span><span class="sxs-lookup"><span data-stu-id="2f398-108">Items—such as adapter handlers, receive locations (including pipelines), and orchestrations—contained in BizTalk hosts can perform the following functions:</span></span>  
  
- <span data-ttu-id="2f398-109">**接收**。</span><span class="sxs-lookup"><span data-stu-id="2f398-109">**Receiving**.</span></span> <span data-ttu-id="2f398-110">这些项后选取在接收位置对其进行初始处理的消息。</span><span class="sxs-lookup"><span data-stu-id="2f398-110">These items do the initial processing of messages after they are picked up in a receive location.</span></span> <span data-ttu-id="2f398-111">当主机包含接收项时，如接收位置或管道，它充当安全边界，并在主机内的管道中出现消息解码和解密。</span><span class="sxs-lookup"><span data-stu-id="2f398-111">When a host contains a receiving item, such as a receive location or pipeline, it acts as a security boundary, and the message decoding and decrypting occurs in a pipeline within the host.</span></span>  
  
- <span data-ttu-id="2f398-112">**发送**。</span><span class="sxs-lookup"><span data-stu-id="2f398-112">**Sending**.</span></span> <span data-ttu-id="2f398-113">这些项对其进行最终处理消息之前发送到发送端口发送。</span><span class="sxs-lookup"><span data-stu-id="2f398-113">These items do the final processing of messages before they are sent out to the send port.</span></span> <span data-ttu-id="2f398-114">当主机包含发送项，例如发送端口或管道中，主机将充当安全边界，而且消息的签名和加密发生在主机中的管道中。</span><span class="sxs-lookup"><span data-stu-id="2f398-114">When a host contains a sending item, such as a send port or pipeline, the host acts as a security boundary, and the message signing and encryption occurs in a pipeline within the host.</span></span>  
  
- <span data-ttu-id="2f398-115">**处理**。</span><span class="sxs-lookup"><span data-stu-id="2f398-115">**Processing**.</span></span> <span data-ttu-id="2f398-116">这些项来处理基于业务流程中的说明进行操作的消息。</span><span class="sxs-lookup"><span data-stu-id="2f398-116">These items process messages based on the instructions in an orchestration.</span></span>  
  
  <span data-ttu-id="2f398-117">一个 BizTalk 主机可以包含接收、 发送和处理消息的项。</span><span class="sxs-lookup"><span data-stu-id="2f398-117">One BizTalk Host can contain items that receive, send, and process messages.</span></span> <span data-ttu-id="2f398-118">建议创建不同的主机，为每个函数来创建安全边界，从而有助于管理。</span><span class="sxs-lookup"><span data-stu-id="2f398-118">It is recommended that you create different hosts for each function to create security boundaries and facilitate management.</span></span> <span data-ttu-id="2f398-119">具体而言，建议使用不同的主机，对于处理操作和接收/发送，并且分隔可信任项和不受信任项。</span><span class="sxs-lookup"><span data-stu-id="2f398-119">In particular, it is recommended that you use different hosts for processing and for receive/send, and that you separate trusted and non-trusted items.</span></span>  
  
  <span data-ttu-id="2f398-120">下图显示了服务器、 主机和主机实例之间的关系。</span><span class="sxs-lookup"><span data-stu-id="2f398-120">The following figure shows the relationship between servers, hosts, and host instances.</span></span>  
  
  <span data-ttu-id="2f398-121">![主机、 主机实例和服务器之间的关系](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span><span class="sxs-lookup"><span data-stu-id="2f398-121">![Hosts, host instances, and server relationships](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")</span></span>  
  <span data-ttu-id="2f398-122">主机、 主机实例和服务器之间的关系</span><span class="sxs-lookup"><span data-stu-id="2f398-122">Relationship between hosts, host instances, and servers</span></span>  
  
  <span data-ttu-id="2f398-123">有关主机实例的详细信息，请参阅[主机实例](../core/host-instances.md)。</span><span class="sxs-lookup"><span data-stu-id="2f398-123">For more information about Host Instances, see [Host Instances](../core/host-instances.md).</span></span>  
  
  <span data-ttu-id="2f398-124">根据物理配置和托管的适配器类型，有两种类型的主机： 进程内主机和独立主机。</span><span class="sxs-lookup"><span data-stu-id="2f398-124">Based on the physical configuration and type of adapter hosted, there are two types of hosts: in-process hosts and isolated hosts.</span></span>  
  
## <a name="in-process-hosts"></a><span data-ttu-id="2f398-125">进程内主机</span><span class="sxs-lookup"><span data-stu-id="2f398-125">In-process Hosts</span></span>  
 <span data-ttu-id="2f398-126">进程内主机表示管理员身份创建、 删除和完全控制使用 Windows Management Instrumentation (WMI) 和 BizTalk 管理控制台中的服务实例。</span><span class="sxs-lookup"><span data-stu-id="2f398-126">In-process hosts represent service instances that an administrator creates, deletes, and fully controls with Windows Management Instrumentation (WMI) and the BizTalk Administration Console.</span></span>  
  
 <span data-ttu-id="2f398-127">进程内主机具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="2f398-127">In-process hosts have the following characteristics:</span></span>  
  
- <span data-ttu-id="2f398-128">您可以登记到进程内主机的任何业务流程。</span><span class="sxs-lookup"><span data-stu-id="2f398-128">You can enlist any orchestration into an in-process host.</span></span>  
  
- <span data-ttu-id="2f398-129">进程内主机可以承载任何发送处理程序。</span><span class="sxs-lookup"><span data-stu-id="2f398-129">An in-process host can host any send handler.</span></span>  
  
- <span data-ttu-id="2f398-130">进程内主机可以承载任何除 SOAP 和 HTTP 的接收处理程序：</span><span class="sxs-lookup"><span data-stu-id="2f398-130">An in-process host can host any of the receive handlers except for SOAP and HTTP:</span></span>  
  
  -   <span data-ttu-id="2f398-131">FILE</span><span class="sxs-lookup"><span data-stu-id="2f398-131">FILE</span></span>  
  
  -   <span data-ttu-id="2f398-132">FTP</span><span class="sxs-lookup"><span data-stu-id="2f398-132">FTP</span></span>  
  
  -   <span data-ttu-id="2f398-133">MQSeries</span><span class="sxs-lookup"><span data-stu-id="2f398-133">MQSeries</span></span>  
  
  -   <span data-ttu-id="2f398-134">MSMQ</span><span class="sxs-lookup"><span data-stu-id="2f398-134">MSMQ</span></span>  
  
  -   <span data-ttu-id="2f398-135">POP3</span><span class="sxs-lookup"><span data-stu-id="2f398-135">POP3</span></span>  
  
  -   <span data-ttu-id="2f398-136">SQL</span><span class="sxs-lookup"><span data-stu-id="2f398-136">SQL</span></span>  
  
  -   <span data-ttu-id="2f398-137">Windows SharePoint Services</span><span class="sxs-lookup"><span data-stu-id="2f398-137">Windows SharePoint Services</span></span>  
  
- <span data-ttu-id="2f398-138">在创建的第一个进程内主机[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署**默认主机**并不能将其删除。</span><span class="sxs-lookup"><span data-stu-id="2f398-138">The first in-process host you create in a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] deployment is the **default host** and you cannot delete it.</span></span> <span data-ttu-id="2f398-139">BizTalk 消息队列适配器将默认主机用于静态处理程序配置。</span><span class="sxs-lookup"><span data-stu-id="2f398-139">The BizTalk Message Queuing adapter uses the default host for static handler configuration.</span></span> <span data-ttu-id="2f398-140">添加适配器会自动创建接收和发送端口的默认主机。</span><span class="sxs-lookup"><span data-stu-id="2f398-140">Adding an adapter automatically creates receive and send ports for the default host.</span></span>  
  
## <a name="isolated-hosts"></a><span data-ttu-id="2f398-141">独立主机</span><span class="sxs-lookup"><span data-stu-id="2f398-141">Isolated Hosts</span></span>  
 <span data-ttu-id="2f398-142">独立主机表示解决方案开发人员以编程方式创建、 删除和控制的服务实例。</span><span class="sxs-lookup"><span data-stu-id="2f398-142">Isolated hosts represent service instances that a solutions developer programmatically creates, deletes, and controls.</span></span> <span data-ttu-id="2f398-143">管理员使用 WMI 和 BizTalk 管理控制台来配置这些主机 （例如，若要配置主机服务帐户和身份验证信任）。</span><span class="sxs-lookup"><span data-stu-id="2f398-143">An administrator uses WMI and the BizTalk Administration Console to configure these hosts (for example, to configure the host service account and authentication trust).</span></span>  
  
 <span data-ttu-id="2f398-144">独立主机主要主机必须运行正常的 BizTalk Server 运行时进程外部的适配器。</span><span class="sxs-lookup"><span data-stu-id="2f398-144">Isolated hosts primarily host adapters that must run outside of the normal BizTalk Server runtime process.</span></span> <span data-ttu-id="2f398-145">例如，对于外部进程，如 ISAPI 扩展和 ASP.NET 使用到的主机适配器的独立主机。</span><span class="sxs-lookup"><span data-stu-id="2f398-145">For example, you use isolated hosts to host adapters for external processes such as ISAPI extensions and ASP.NET.</span></span>  
  
 <span data-ttu-id="2f398-146">独立主机具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="2f398-146">Isolated hosts have the following characteristics:</span></span>  
  
-   <span data-ttu-id="2f398-147">无法登记到独立主机的业务流程。</span><span class="sxs-lookup"><span data-stu-id="2f398-147">You cannot enlist orchestrations into an isolated host.</span></span>  
  
-   <span data-ttu-id="2f398-148">独立主机不能作为发送处理程序的宿主。</span><span class="sxs-lookup"><span data-stu-id="2f398-148">An isolated host cannot host send handlers.</span></span>  
  
-   <span data-ttu-id="2f398-149">独立主机可作为仅与 HTTP/S 和 SOAP 适配器 （独立类型适配器） 相关联的接收处理程序的宿主。</span><span class="sxs-lookup"><span data-stu-id="2f398-149">An isolated host can host only the receive handlers associated with HTTP/S and SOAP adapters (the isolated-type adapters).</span></span>  
  
-   <span data-ttu-id="2f398-150">独立主机不能作为跟踪的宿主。</span><span class="sxs-lookup"><span data-stu-id="2f398-150">An isolated host cannot host tracking.</span></span>  
  
-   <span data-ttu-id="2f398-151">独立主机不能为默认主机。</span><span class="sxs-lookup"><span data-stu-id="2f398-151">An isolated host cannot be the default host.</span></span>  
  
-   <span data-ttu-id="2f398-152">独立主机的状态始终是**不可用状态**。</span><span class="sxs-lookup"><span data-stu-id="2f398-152">The status of an isolated host is always **Status Unavailable**.</span></span> <span data-ttu-id="2f398-153">BizTalk Server 不访问外部进程的状态信息。</span><span class="sxs-lookup"><span data-stu-id="2f398-153">BizTalk Server does not access the status information for external processes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2f398-154">主机实例可以共享相同的服务帐户，只要它们共享相同的安全配置 （受信任验证）。</span><span class="sxs-lookup"><span data-stu-id="2f398-154">Host instances can share the same service account as long as they share the same security configuration (authentication trust).</span></span>  
  
## <a name="trusted-and-untrusted-hosts"></a><span data-ttu-id="2f398-155">受信任和不受信任主机</span><span class="sxs-lookup"><span data-stu-id="2f398-155">Trusted and Untrusted Hosts</span></span>  
 <span data-ttu-id="2f398-156">BizTalk Server 将主机标识为受信任验证来指示，受信任的主机排队到 MessageBox 数据库的消息的发件人是一个实体而不受信任主机本身。</span><span class="sxs-lookup"><span data-stu-id="2f398-156">BizTalk Server enables hosts identified as authentication trusted to indicate that the sender of a message that the trusted host is queuing to the MessageBox database is an entity other than the trusted host itself.</span></span> <span data-ttu-id="2f398-157">受信任验证的主要目的是将管道解析为产品 ID (PID) 并将传递到使用 PID 服务用于授权和出站参与方解析和发件人 Windows 安全 ID 的传输(SSID) 一起使用以便在业务流程操作授权中使用的服务。</span><span class="sxs-lookup"><span data-stu-id="2f398-157">The primary purposes of authentication trust are to enable pipelines to resolve to a Product ID (PID) and pass that PID along to consuming services for use in authorization and outbound party resolution, and to enable the transmission of the sender Windows Security ID (SSID) along to consuming services for use in orchestration action authorization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f398-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="2f398-158">See Also</span></span>  
 <span data-ttu-id="2f398-159">[主机实例](../core/host-instances.md) </span><span class="sxs-lookup"><span data-stu-id="2f398-159">[Host Instances](../core/host-instances.md) </span></span>  
 [<span data-ttu-id="2f398-160">管理 BizTalk 主机和主机实例</span><span class="sxs-lookup"><span data-stu-id="2f398-160">Managing BizTalk Hosts and Host Instances</span></span>](../core/managing-biztalk-hosts-and-host-instances.md)  
 [<span data-ttu-id="2f398-161">实体</span><span class="sxs-lookup"><span data-stu-id="2f398-161">Entities</span></span>](../core/entities.md)