---
title: 使用 SOAP 适配器的已知问题 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a3229d73-170d-42b7-bab9-12ae5f2d0fa7
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4b0d27f01efee12e32d201a1a0f7ab9e686088cc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65329022"
---
# <a name="known-issues-with-the-soap-adapter"></a><span data-ttu-id="54c44-102">SOAP 适配器的已知的问题</span><span class="sxs-lookup"><span data-stu-id="54c44-102">Known Issues with the SOAP Adapter</span></span>
<span data-ttu-id="54c44-103">本部分包含可能帮助您避免错误的信息。</span><span class="sxs-lookup"><span data-stu-id="54c44-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="54c44-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="54c44-104">Known Issues</span></span>  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a><span data-ttu-id="54c44-105">SOAP 适配器性能降低或生成负载下的错误</span><span class="sxs-lookup"><span data-stu-id="54c44-105">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="54c44-106">问题</span><span class="sxs-lookup"><span data-stu-id="54c44-106">Problem</span></span>  
 <span data-ttu-id="54c44-107">SOAP 适配器性能降低或生成负载下的错误</span><span class="sxs-lookup"><span data-stu-id="54c44-107">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="54c44-108">原因</span><span class="sxs-lookup"><span data-stu-id="54c44-108">Cause</span></span>  
 <span data-ttu-id="54c44-109">由于 SOAP 适配器或影响 SOAP 适配器的依存关系组件的默认配置选项不进行优化，在负载下的性能，将发生此问题。</span><span class="sxs-lookup"><span data-stu-id="54c44-109">This problem occurs because the default configuration options for the SOAP adapter or for dependency components that affect the SOAP adapter are not tuned for performance under load.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="54c44-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="54c44-110">Resolution</span></span>  
 <span data-ttu-id="54c44-111">若要解决此问题，请修改 SOAP 适配器或依存关系组件的主题中所述的配置选项[配置参数会影响适配器性能的](../core/configuration-parameters-that-affect-adapter-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="54c44-111">To resolve this problem modify the configuration options for the SOAP adapter or for the dependency components described in the topic [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a><span data-ttu-id="54c44-112">MIME/SMIME 编码器和解码器管道组件不能进行编码和解码通过 SOAP 适配器处理的数据</span><span class="sxs-lookup"><span data-stu-id="54c44-112">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="54c44-113">问题</span><span class="sxs-lookup"><span data-stu-id="54c44-113">Problem</span></span>  
 <span data-ttu-id="54c44-114">MIME/SMIME 编码器和解码器管道组件不能进行编码和解码通过 SOAP 适配器处理的数据</span><span class="sxs-lookup"><span data-stu-id="54c44-114">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="54c44-115">原因</span><span class="sxs-lookup"><span data-stu-id="54c44-115">Cause</span></span>  
 <span data-ttu-id="54c44-116">由于 SOAP 适配器组装和拆装 SOAP 消息的适配器阶段的过程，将发生此问题。</span><span class="sxs-lookup"><span data-stu-id="54c44-116">This problem occurs because the SOAP adapter assembles and disassembles the SOAP messages in the adapter stage of the process.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="54c44-117">解决方法</span><span class="sxs-lookup"><span data-stu-id="54c44-117">Resolution</span></span>  
 <span data-ttu-id="54c44-118">若要解决此问题，请使用安全套接字层 (SSL) 来保护通信的 SOAP 适配器处理的消息进行编码。</span><span class="sxs-lookup"><span data-stu-id="54c44-118">To resolve this problem, Use Secure Sockets Layer (SSL) to secure communications to encode messages processed by the SOAP adapter.</span></span> <span data-ttu-id="54c44-119">在发送端，使用**客户端证书指纹**来实现此目的的 SOAP 适配器属性页中的属性。</span><span class="sxs-lookup"><span data-stu-id="54c44-119">On the send side, use the **Client Certificate Thumbprint** property in the SOAP adapter properties page to achieve this.</span></span> <span data-ttu-id="54c44-120">在接收端，必须配置虚拟目录用于承载 BizTalk Web 服务的 SSL 安全通信。</span><span class="sxs-lookup"><span data-stu-id="54c44-120">On the receive side, you must configure the virtual directory that hosts the BizTalk Web Service for SSL secure communications.</span></span>  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a><span data-ttu-id="54c44-121">默认值承载 SOAP 适配器的 AppDomain 被卸载，导致主机进程挂起</span><span class="sxs-lookup"><span data-stu-id="54c44-121">The default AppDomain hosting the SOAP adapter gets unloaded causing the host process to hang</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="54c44-122">问题</span><span class="sxs-lookup"><span data-stu-id="54c44-122">Problem</span></span>  
 <span data-ttu-id="54c44-123">承载 SOAP 适配器的进程挂起，所有其他 Web 服务导致的挂起的过程。</span><span class="sxs-lookup"><span data-stu-id="54c44-123">The process hosting the SOAP adapter hangs, causing all other Web services in the process to hang.</span></span> <span data-ttu-id="54c44-124">这可能会导致以下错误：</span><span class="sxs-lookup"><span data-stu-id="54c44-124">This may result in the following error:</span></span>  
  
 <span data-ttu-id="54c44-125">执行响应 （发送） 管道时出错："未知"源："未知"接收端口：TwoWayLatencyLoopBack_RxPort" URI: "/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx" Reason:尝试访问已卸载的 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="54c44-125">There was a failure executing the response(send) pipeline: "Unknown " Source: "Unknown " Receive Port: TwoWayLatencyLoopBack_RxPort" URI: "/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx" Reason: Attempted to access an unloaded AppDomain.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="54c44-126">原因</span><span class="sxs-lookup"><span data-stu-id="54c44-126">Cause</span></span>  
 <span data-ttu-id="54c44-127">SOAP 适配器在 IIS 进程空间中运行。</span><span class="sxs-lookup"><span data-stu-id="54c44-127">The SOAP adapter runs in the IIS process space.</span></span> <span data-ttu-id="54c44-128">如果 IIS AppPool 中存在多个 Web 服务，每个 Web 服务最后会具有其自身的 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="54c44-128">If more than one Web service exists in the IIS AppPool, then every Web service ends up having its own AppDomain.</span></span>  
  
 <span data-ttu-id="54c44-129">所有消息引擎对象在第一个 AppDomain 中默认情况下的创建 （即。</span><span class="sxs-lookup"><span data-stu-id="54c44-129">By default all messaging engine objects are created in the first AppDomain (that is,.</span></span> <span data-ttu-id="54c44-130">与第一个 Web 服务相对应的 AppDomain 确定)。</span><span class="sxs-lookup"><span data-stu-id="54c44-130">the AppDomain corresponding to the first Web service).</span></span> <span data-ttu-id="54c44-131">如果第一个 Web 服务的时间出于任何原因长时间处于非活动状态，IIS 将卸载第一个 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="54c44-131">If the first Web service is inactive for an extended period of time for any reason, IIS unloads the first AppDomain.</span></span> <span data-ttu-id="54c44-132">在此情况下，宿主进程中的所有服务都变为不可用。</span><span class="sxs-lookup"><span data-stu-id="54c44-132">When this happens, all services in the hosting process become unusable.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="54c44-133">解决方法</span><span class="sxs-lookup"><span data-stu-id="54c44-133">Resolution</span></span>  
 <span data-ttu-id="54c44-134">若要防止 AppDomain 被卸载，请执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="54c44-134">To prevent the AppDomain from being unloaded, follow the procedure below:</span></span>  
  
1. <span data-ttu-id="54c44-135">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk Server** ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="54c44-135">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server** and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="54c44-136">在中**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="54c44-136">In **BizTalk Server Administration Console**, Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Hosts**.</span></span>  
  
3. <span data-ttu-id="54c44-137">从主机列表中，右键单击所需的主机，然后依次**设置**。</span><span class="sxs-lookup"><span data-stu-id="54c44-137">From the list of Hosts, right-click the required host, and then click **Settings**.</span></span>  
  
4. <span data-ttu-id="54c44-138">在中**BizTalk 设置仪表板**，检查**独立适配器的默认应用程序域**下**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="54c44-138">In the **BizTalk Settings Dashboard**, check **Default application domain for isolated adapter** under **General** tab.</span></span>  
  
   <span data-ttu-id="54c44-139">当执行此操作时，默认值而不是在自己的 Appdomain 的 AppDomain 中创建 BizTalk 消息引擎对象。</span><span class="sxs-lookup"><span data-stu-id="54c44-139">When you do this, the BizTalk Messaging Engine objects are created in the default AppDomain instead of in their own AppDomains.</span></span> <span data-ttu-id="54c44-140">因为永远不会卸载默认 AppDomain 时，不会再出现问题。</span><span class="sxs-lookup"><span data-stu-id="54c44-140">Because the default AppDomain is never unloaded, the problem no longer occurs.</span></span>  
  
#### <a name="the-soap-adapter-fails-to-register"></a><span data-ttu-id="54c44-141">SOAP 适配器无法注册</span><span class="sxs-lookup"><span data-stu-id="54c44-141">The SOAP Adapter fails to register</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="54c44-142">问题</span><span class="sxs-lookup"><span data-stu-id="54c44-142">Problem</span></span>  
 <span data-ttu-id="54c44-143">BizTalk Server 尝试注册 SOAP （或 HTTP） 适配器时，可能出现以下错误。</span><span class="sxs-lookup"><span data-stu-id="54c44-143">The following error may occur when BizTalk Server attempts to register the SOAP (or HTTP) adapter.</span></span>  
  
 <span data-ttu-id="54c44-144">"消息引擎无法注册适配器"SOAP"。</span><span class="sxs-lookup"><span data-stu-id="54c44-144">"The Messaging Engine failed to register an adapter "SOAP".</span></span> <span data-ttu-id="54c44-145">详细信息："注册同一进程内的多个适配器类型不受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="54c44-145">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span> <span data-ttu-id="54c44-146">例如 HTTP 和 SOAP 接收适配器不能同时存在同一进程中"。</span><span class="sxs-lookup"><span data-stu-id="54c44-146">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
 <span data-ttu-id="54c44-147">或</span><span class="sxs-lookup"><span data-stu-id="54c44-147">Or</span></span>  
  
 <span data-ttu-id="54c44-148">"消息引擎无法注册适配器"HTTP"。</span><span class="sxs-lookup"><span data-stu-id="54c44-148">"The Messaging Engine failed to register an adapter "HTTP".</span></span> <span data-ttu-id="54c44-149">详细信息："注册同一进程内的多个适配器类型不受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="54c44-149">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span>  <span data-ttu-id="54c44-150">例如 HTTP 和 SOAP 接收适配器不能同时存在同一进程中"。</span><span class="sxs-lookup"><span data-stu-id="54c44-150">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="54c44-151">原因</span><span class="sxs-lookup"><span data-stu-id="54c44-151">Cause</span></span>  
 <span data-ttu-id="54c44-152">运行时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]上[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]/ IIS 6.x，SOAP 和 HTTP 适配器不能执行在同一进程空间或应用程序池中。</span><span class="sxs-lookup"><span data-stu-id="54c44-152">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] / IIS 6.x, the SOAP and HTTP adapters cannot execute in the same process space or application pool.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="54c44-153">解决方法</span><span class="sxs-lookup"><span data-stu-id="54c44-153">Resolution</span></span>  
 <span data-ttu-id="54c44-154">如果安装需要相同的 Web 服务器上使用 SOAP 和 HTTP 适配器则必须为每个适配器创建单独的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="54c44-154">If an installation requires using both the SOAP and HTTP adapters on the same Web server then separate application pools must be created for each adapter.</span></span>  <span data-ttu-id="54c44-155">创建后，每个适配器的虚拟目录每个分配给不同的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="54c44-155">Once created, the virtual directories for each adapter are each assigned to a different application pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="54c44-156">出现此问题不在 Windows XP 以来在这些操作系统下运行在 IIS 下的不同进程空间中的 SOAP 和 HTTP 适配器 5.x。</span><span class="sxs-lookup"><span data-stu-id="54c44-156">This problem does not occur under Windows XP since under these operating systems, the SOAP and HTTP adapter run in different process spaces under IIS 5.x.</span></span>  <span data-ttu-id="54c44-157">SOAP 适配器作为 ASP.Net 应用程序在 aspnet_wp.exe 进程中运行。</span><span class="sxs-lookup"><span data-stu-id="54c44-157">The SOAP adapter runs as an ASP.Net application in the aspnet_wp.exe process.</span></span>  <span data-ttu-id="54c44-158">HTTP 适配器运行在 dllhost.exe 的专用的进程空间中。</span><span class="sxs-lookup"><span data-stu-id="54c44-158">The HTTP adapter runs in the dedicated process space of dllhost.exe.</span></span>  <span data-ttu-id="54c44-159">因此这两种适配器都允许用户同时运行同一 Web 服务器上彼此隔离。</span><span class="sxs-lookup"><span data-stu-id="54c44-159">Therefore both adapters are isolated from each other allowing them to run on the same Web server concurrently.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54c44-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="54c44-160">See Also</span></span>  
 [<span data-ttu-id="54c44-161">SOAP 适配器故障排除</span><span class="sxs-lookup"><span data-stu-id="54c44-161">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)