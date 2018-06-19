---
title: 已知问题的 SOAP 适配器 |Microsoft 文档
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
ms.openlocfilehash: 671510c6901fc399580ab73018e67eadc86f7212
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262845"
---
# <a name="known-issues-with-the-soap-adapter"></a><span data-ttu-id="6aa6a-102">SOAP 适配器的已知问题</span><span class="sxs-lookup"><span data-stu-id="6aa6a-102">Known Issues with the SOAP Adapter</span></span>
<span data-ttu-id="6aa6a-103">本部分包含可帮助你避免出现错误的信息。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-103">This section contains information that may help you avoid errors.</span></span>  
  
## <a name="known-issues"></a><span data-ttu-id="6aa6a-104">已知问题</span><span class="sxs-lookup"><span data-stu-id="6aa6a-104">Known Issues</span></span>  
  
#### <a name="the-soap-adapter-experiences-poor-performance-or-generates-errors-under-load"></a><span data-ttu-id="6aa6a-105">SOAP 适配器在负载下性能降低或生成错误</span><span class="sxs-lookup"><span data-stu-id="6aa6a-105">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6aa6a-106">问题</span><span class="sxs-lookup"><span data-stu-id="6aa6a-106">Problem</span></span>  
 <span data-ttu-id="6aa6a-107">SOAP 适配器在负载下性能降低或生成错误</span><span class="sxs-lookup"><span data-stu-id="6aa6a-107">The SOAP Adapter experiences poor performance or generates errors under load</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6aa6a-108">原因</span><span class="sxs-lookup"><span data-stu-id="6aa6a-108">Cause</span></span>  
 <span data-ttu-id="6aa6a-109">发生这一问题的原因是 SOAP 适配器的默认配置选项或影响 SOAP 适配器的依存关系组件的默认配置选项未针对负载下的性能进行优化。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-109">This problem occurs because the default configuration options for the SOAP adapter or for dependency components that affect the SOAP adapter are not tuned for performance under load.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6aa6a-110">解决方法</span><span class="sxs-lookup"><span data-stu-id="6aa6a-110">Resolution</span></span>  
 <span data-ttu-id="6aa6a-111">若要解决此问题，请修改 SOAP 适配器或主题中所述的依赖项组件的配置选项[配置参数会影响适配器性能](../core/configuration-parameters-that-affect-adapter-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-111">To resolve this problem modify the configuration options for the SOAP adapter or for the dependency components described in the topic [Configuration Parameters that Affect Adapter Performance](../core/configuration-parameters-that-affect-adapter-performance.md).</span></span>  
  
#### <a name="the-mimesmime-encoder-and-decoder-pipeline-components-cannot-encode-and-decode-data-processed-by-the-soap-adapter"></a><span data-ttu-id="6aa6a-112">MIME/SMIME 编码器和解码器管道组件无法对 SOAP 适配器处理的数据进行编码和解码</span><span class="sxs-lookup"><span data-stu-id="6aa6a-112">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6aa6a-113">问题</span><span class="sxs-lookup"><span data-stu-id="6aa6a-113">Problem</span></span>  
 <span data-ttu-id="6aa6a-114">MIME/SMIME 编码器和解码器管道组件无法对 SOAP 适配器处理的数据进行编码和解码</span><span class="sxs-lookup"><span data-stu-id="6aa6a-114">The MIME/SMIME encoder and decoder pipeline components cannot encode and decode data processed by the SOAP adapter</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6aa6a-115">原因</span><span class="sxs-lookup"><span data-stu-id="6aa6a-115">Cause</span></span>  
 <span data-ttu-id="6aa6a-116">发生这一问题的原因是 SOAP 适配器在流程的适配器阶段组装和拆装 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-116">This problem occurs because the SOAP adapter assembles and disassembles the SOAP messages in the adapter stage of the process.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6aa6a-117">解决方法</span><span class="sxs-lookup"><span data-stu-id="6aa6a-117">Resolution</span></span>  
 <span data-ttu-id="6aa6a-118">若要解决此问题，请使用安全套接字层 (SSL) 保障通信的安全，以便对 SOAP 适配器处理的信息进行编码。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-118">To resolve this problem, Use Secure Sockets Layer (SSL) to secure communications to encode messages processed by the SOAP adapter.</span></span> <span data-ttu-id="6aa6a-119">在发送端，使用**客户端证书指纹**来实现此目的的 SOAP 适配器属性页中的属性。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-119">On the send side, use the **Client Certificate Thumbprint** property in the SOAP adapter properties page to achieve this.</span></span> <span data-ttu-id="6aa6a-120">在接收端，必须为 SSL 安全通信配置 BizTalk Web Services 的宿主虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-120">On the receive side, you must configure the virtual directory that hosts the BizTalk Web Service for SSL secure communications.</span></span>  
  
#### <a name="the-default-appdomain-hosting-the-soap-adapter-gets-unloaded-causing-the-host-process-to-hang"></a><span data-ttu-id="6aa6a-121">承载 SOAP 适配器的默认 AppDomain 被卸载，导致主机进程挂起</span><span class="sxs-lookup"><span data-stu-id="6aa6a-121">The default AppDomain hosting the SOAP adapter gets unloaded causing the host process to hang</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6aa6a-122">问题</span><span class="sxs-lookup"><span data-stu-id="6aa6a-122">Problem</span></span>  
 <span data-ttu-id="6aa6a-123">承载 SOAP 适配器的进程挂起，导致进程中的所有其他 Web Services 挂起。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-123">The process hosting the SOAP adapter hangs, causing all other Web services in the process to hang.</span></span> <span data-ttu-id="6aa6a-124">这可能导致以下错误：</span><span class="sxs-lookup"><span data-stu-id="6aa6a-124">This may result in the following error:</span></span>  
  
 <span data-ttu-id="6aa6a-125">执行 response(send) 管道失败:"未知"的源:"未知"接收端口:: TwoWayLatencyLoopBack_RxPort"URI:"/ TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx"原因： 尝试访问已卸载的 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-125">There was a failure executing the response(send) pipeline: "Unknown " Source: "Unknown " Receive Port: TwoWayLatencyLoopBack_RxPort" URI: "/TwoWayLatencyRxSOAP/TwoWayLatencyWS.asmx" Reason: Attempted to access an unloaded AppDomain.</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6aa6a-126">原因</span><span class="sxs-lookup"><span data-stu-id="6aa6a-126">Cause</span></span>  
 <span data-ttu-id="6aa6a-127">SOAP 适配器在 IIS 进程空间中运行。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-127">The SOAP adapter runs in the IIS process space.</span></span> <span data-ttu-id="6aa6a-128">如果 IIS AppPool 中存在一个以上的 Web Services，则每个 Web Services 最后会具有自己的 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-128">If more than one Web service exists in the IIS AppPool, then every Web service ends up having its own AppDomain.</span></span>  
  
 <span data-ttu-id="6aa6a-129">默认情况下可以在第一个 AppDomain 中中创建所有消息传递引擎对象 （即。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-129">By default all messaging engine objects are created in the first AppDomain (that is,.</span></span> <span data-ttu-id="6aa6a-130">与第一个 Web 服务相对应的 AppDomain 确定)。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-130">the AppDomain corresponding to the first Web service).</span></span> <span data-ttu-id="6aa6a-131">如果第一个 Web Services 出于任何原因在很长的一段时间内是不活动的，IIS 将卸载第一个 AppDomain。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-131">If the first Web service is inactive for an extended period of time for any reason, IIS unloads the first AppDomain.</span></span> <span data-ttu-id="6aa6a-132">出现这样的情况时，承载进程中的所有服务都不能使用。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-132">When this happens, all services in the hosting process become unusable.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6aa6a-133">解决方法</span><span class="sxs-lookup"><span data-stu-id="6aa6a-133">Resolution</span></span>  
 <span data-ttu-id="6aa6a-134">若要防止卸载 AppDomain，请执行以下过程：</span><span class="sxs-lookup"><span data-stu-id="6aa6a-134">To prevent the AppDomain from being unloaded, follow the procedure below:</span></span>  
  
1.  <span data-ttu-id="6aa6a-135">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server** ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-135">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk Server** and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="6aa6a-136">在**BizTalk Server 管理控制台**，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后单击**主机**。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-136">In **BizTalk Server Administration Console**, Expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Platform Settings**, and then click **Hosts**.</span></span>  
  
3.  <span data-ttu-id="6aa6a-137">从主机列表中，右键单击所需的主机，并依次**设置**。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-137">From the list of Hosts, right-click the required host, and then click **Settings**.</span></span>  
  
4.  <span data-ttu-id="6aa6a-138">在**BizTalk 设置仪表板**，检查**独立的适配器的默认应用程序域**下**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-138">In the **BizTalk Settings Dashboard**, check **Default application domain for isolated adapter** under **General** tab.</span></span>  
  
 <span data-ttu-id="6aa6a-139">执行此操作后，BizTalk 消息引擎对象在默认的 AppDomain 中创建，而不是在自己的 AppDomain 中创建。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-139">When you do this, the BizTalk Messaging Engine objects are created in the default AppDomain instead of in their own AppDomains.</span></span> <span data-ttu-id="6aa6a-140">因为默认的 AppDomain 永不被卸载，就不会再出现这样的问题了。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-140">Because the default AppDomain is never unloaded, the problem no longer occurs.</span></span>  
  
#### <a name="the-soap-adapter-fails-to-register"></a><span data-ttu-id="6aa6a-141">SOAP 适配器无法注册</span><span class="sxs-lookup"><span data-stu-id="6aa6a-141">The SOAP Adapter fails to register</span></span>  
  
##### <a name="problem"></a><span data-ttu-id="6aa6a-142">问题</span><span class="sxs-lookup"><span data-stu-id="6aa6a-142">Problem</span></span>  
 <span data-ttu-id="6aa6a-143">BizTalk Server 尝试注册 SOAP（或 HTTP）适配器时，可能出现以下错误。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-143">The following error may occur when BizTalk Server attempts to register the SOAP (or HTTP) adapter.</span></span>  
  
 <span data-ttu-id="6aa6a-144">“The Messaging Engine failed to register an adapter SOAP”（消息引擎无法注册适配器 SOAP。）</span><span class="sxs-lookup"><span data-stu-id="6aa6a-144">"The Messaging Engine failed to register an adapter "SOAP".</span></span> <span data-ttu-id="6aa6a-145">详细信息:"注册相同的进程内的多个适配器类型不是受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-145">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span> <span data-ttu-id="6aa6a-146">“For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process.”（例如，HTTP 和 SOAP 接收适配器不能在同一个进程中共存。）</span><span class="sxs-lookup"><span data-stu-id="6aa6a-146">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
 <span data-ttu-id="6aa6a-147">或</span><span class="sxs-lookup"><span data-stu-id="6aa6a-147">Or</span></span>  
  
 <span data-ttu-id="6aa6a-148">“The Messaging Engine failed to register an adapter HTTP”（消息引擎无法注册适配器 HTTP。）</span><span class="sxs-lookup"><span data-stu-id="6aa6a-148">"The Messaging Engine failed to register an adapter "HTTP".</span></span> <span data-ttu-id="6aa6a-149">详细信息:"注册相同的进程内的多个适配器类型不是受支持的方案。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-149">Details: "Registering multiple adapter types within the same process is not a supported scenario.</span></span>  <span data-ttu-id="6aa6a-150">“For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process.”（例如，HTTP 和 SOAP 接收适配器不能在同一个进程中共存。）</span><span class="sxs-lookup"><span data-stu-id="6aa6a-150">For e.g. HTTP and SOAP receive adapters cannot co-exist in the same process".</span></span>  
  
##### <a name="cause"></a><span data-ttu-id="6aa6a-151">原因</span><span class="sxs-lookup"><span data-stu-id="6aa6a-151">Cause</span></span>  
 <span data-ttu-id="6aa6a-152">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] / IIS 6.x 上运行 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 时，SOAP 和 HTTP 适配器不能在同一个进程空间或应用程序池中执行。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-152">When running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] / IIS 6.x, the SOAP and HTTP adapters cannot execute in the same process space or application pool.</span></span>  
  
##### <a name="resolution"></a><span data-ttu-id="6aa6a-153">解决方法</span><span class="sxs-lookup"><span data-stu-id="6aa6a-153">Resolution</span></span>  
 <span data-ttu-id="6aa6a-154">如果安装需要在一个 Web 服务器上同时使用 SOAP 和 HTTP 适配器，则必须为每个适配器创建单独的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-154">If an installation requires using both the SOAP and HTTP adapters on the same Web server then separate application pools must be created for each adapter.</span></span>  <span data-ttu-id="6aa6a-155">创建后，每个适配器的虚拟目录被分别分配给不同的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-155">Once created, the virtual directories for each adapter are each assigned to a different application pool.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6aa6a-156">在 Windows XP 下不会出现此问题，因为在这些操作系统下，SOAP 和 HTTP 适配器运行在 IIS 5.x 下的不同进程空间中。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-156">This problem does not occur under Windows XP since under these operating systems, the SOAP and HTTP adapter run in different process spaces under IIS 5.x.</span></span>  <span data-ttu-id="6aa6a-157">SOAP 适配器作为 ASP.Net 应用程序运行在 aspnet_wp.exe 进程中。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-157">The SOAP adapter runs as an ASP.Net application in the aspnet_wp.exe process.</span></span>  <span data-ttu-id="6aa6a-158">HTTP 适配器运行在 dllhost.exe 的专用进程空间中。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-158">The HTTP adapter runs in the dedicated process space of dllhost.exe.</span></span>  <span data-ttu-id="6aa6a-159">因此，这两个适配器是相互隔离的，可以同时在一个 Web 服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="6aa6a-159">Therefore both adapters are isolated from each other allowing them to run on the same Web server concurrently.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa6a-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6aa6a-160">See Also</span></span>  
 [<span data-ttu-id="6aa6a-161">故障排除 SOAP 适配器</span><span class="sxs-lookup"><span data-stu-id="6aa6a-161">Troubleshooting the SOAP Adapter</span></span>](../core/troubleshooting-the-soap-adapter.md)