---
title: "博士 Edwards OneWorld 的体系结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: architecture
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1daee7d44152817da1ac536dd98cbaf898e2ac7c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="architecture-of-jd-edwards-oneworld"></a><span data-ttu-id="81b92-102">JD Edwards OneWorld 的体系结构</span><span class="sxs-lookup"><span data-stu-id="81b92-102">Architecture of JD Edwards OneWorld</span></span>
<span data-ttu-id="81b92-103">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供了对 JD Edwards OneWorld 业务功能的访问。</span><span class="sxs-lookup"><span data-stu-id="81b92-103">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="81b92-104">JD Edwards OneWorld 使用名为 JDENet 的专用消息体系结构在客户端和服务器计算机之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="81b92-104">JD Edwards OneWorld communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="81b92-105">JDENet 由 Connector.jar 和 Kernel.jar JAR 文件中找到的博士 Edwards OneWorld 连接器类实现。</span><span class="sxs-lookup"><span data-stu-id="81b92-105">JDENet is implemented by the JD Edwards OneWorld connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="81b92-106">使用 TCP/IP 作为传输协议，使用默认端口的 6009 或 6010 实现通信。</span><span class="sxs-lookup"><span data-stu-id="81b92-106">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="81b92-107">此值设置有关位置的说明，请参阅[如何设置博士 Edwards OneWorld 传输属性](../core/how-to-set-jd-edwards-oneworld-transport-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="81b92-107">For a description of where this value is set, see [How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md).</span></span>  
  
 <span data-ttu-id="81b92-108">**用于博士 Edwards OneWorld 的 BizTalk Adapter 的体系结构**</span><span class="sxs-lookup"><span data-stu-id="81b92-108">**Architecture for BizTalk Adapter for JD Edwards OneWorld**</span></span>  
  
 ![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")  
  
 <span data-ttu-id="81b92-109">对 JD Edwards OneWorld 业务功能的调用需要两条消息：</span><span class="sxs-lookup"><span data-stu-id="81b92-109">Calls to JD Edwards OneWorld business functions require two messages:</span></span>  
  
-   <span data-ttu-id="81b92-110">第一条消息息响应处理业务功能的服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="81b92-110">The first message responds with the location of the server that processes the business function.</span></span> <span data-ttu-id="81b92-111">这通过一组表调用中执行查找实现*对象配置映射 (OCM)*。</span><span class="sxs-lookup"><span data-stu-id="81b92-111">This is accomplished by performing a lookup in a set of tables called *object configuration mapping (OCM)*.</span></span>  
  
-   <span data-ttu-id="81b92-112">第二条消息发送格式化的消息缓冲区，其中包含要传递的参数或从 JD Edwards OneWorld 传递到相应服务器的参数，然后等待回复。</span><span class="sxs-lookup"><span data-stu-id="81b92-112">The second message sends a formatted message buffer containing the arguments to pass to or from JD Edwards OneWorld to the appropriate server, and waits for a reply.</span></span> <span data-ttu-id="81b92-113">根据基础 C++ 结构的 typedef 对缓冲区进行格式化。</span><span class="sxs-lookup"><span data-stu-id="81b92-113">The buffers are formatted according to the typedefs of the underlying C++ structs.</span></span>  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="81b92-114">设计时的入站服务</span><span class="sxs-lookup"><span data-stu-id="81b92-114">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="81b92-115">在设计时，您创建端口、选择适配器并提供凭据信息以连接到目标 JD Edwards OneWorld 服务器。</span><span class="sxs-lookup"><span data-stu-id="81b92-115">At design time, you create your port, select the adapter, and provide credential information to connect to the target JD Edwards OneWorld server.</span></span> <span data-ttu-id="81b92-116">Visual Studio 开发环境调用适配器框架，以请求此端口的设计时信息。</span><span class="sxs-lookup"><span data-stu-id="81b92-116">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="81b92-117">用于 JD Edwards OneWorld 的 BizTalk 适配器使用此端口的 Browsingagent。</span><span class="sxs-lookup"><span data-stu-id="81b92-117">BizTalk Adapter for JD Edwards OneWorld uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="81b92-118">在设计时，BizTalk Server 通过调用适配器来请求信息。</span><span class="sxs-lookup"><span data-stu-id="81b92-118">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="81b92-119">Browsingagent 将请求转换成本地 JD Edwards OneWorld 代码，然后通过 ThinNet API 连接（在连接器和 Kernel.jar 中建立）将请求传输给 JD Edwards OneWorld。</span><span class="sxs-lookup"><span data-stu-id="81b92-119">The Browsingagent converts the request into native JD Edwards OneWorld code and then transmits the requests to JD Edwards OneWorld through the ThinNet API connection (established in the Connector and Kernel.jars).</span></span>  
  
-   <span data-ttu-id="81b92-120">通过 BTSREL 安装安装自定义业务函数： 它公开的主业务功能。</span><span class="sxs-lookup"><span data-stu-id="81b92-120">A custom business function is installed through the BTSREL installation: it exposes the master business functions.</span></span>  
  
-   <span data-ttu-id="81b92-121">最初返回 JD Edwards OneWorld 的模块列表，并将其传输到 Visual Studio，填充适配器向导。</span><span class="sxs-lookup"><span data-stu-id="81b92-121">A list of modules in JD Edwards OneWorld is initially returned and transported to Visual Studio, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="81b92-122">您可以展开层次结构显示库名称和模块名称。</span><span class="sxs-lookup"><span data-stu-id="81b92-122">You can expand the hierarchy to display the library name and module name.</span></span>  
  
-   <span data-ttu-id="81b92-123">选择特定模块时，您将看到模块中所有功能的架构。</span><span class="sxs-lookup"><span data-stu-id="81b92-123">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="81b92-124">适配器从 JD Edwards OneWorld 获取所需的信息，而 browsingagent 创建架构。</span><span class="sxs-lookup"><span data-stu-id="81b92-124">The adapter obtains the required information from JD Edwards OneWorld, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="81b92-125">架构添加到 BizTalk Server 项目业务流程。</span><span class="sxs-lookup"><span data-stu-id="81b92-125">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="81b92-126">运行时的入站服务</span><span class="sxs-lookup"><span data-stu-id="81b92-126">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="81b92-127">BizTalk Server 在特定端口上调用用于 JD Edwards OneWorld 的 BizTalk 适配器来发送消息。</span><span class="sxs-lookup"><span data-stu-id="81b92-127">BizTalk Server calls the BizTalk Adapter for JD Edwards OneWorld to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="81b92-128">运行代理将 XML 转换为本地 JD Edwards 代码。</span><span class="sxs-lookup"><span data-stu-id="81b92-128">The run-time agent converts the XML into native JD Edwards code.</span></span>  
  
-   <span data-ttu-id="81b92-129">运行时代理通过 ThinNet 将请求提交给在发送端口的传输属性中指定的 JD Edwards 企业系统。</span><span class="sxs-lookup"><span data-stu-id="81b92-129">The run-time agent submits the request through the ThinNet to the JD Edwards enterprise system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="81b92-130">主业务功能在 JD Edwards 系统上执行，随后生成一个表示成功或失败的响应文档及业务功能返回的数据参数。</span><span class="sxs-lookup"><span data-stu-id="81b92-130">The master business function is executed on the JD Edwards system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="81b92-131">发送到 JD Edwards OneWorld 的消息是一种单消息、单回复结构。</span><span class="sxs-lookup"><span data-stu-id="81b92-131">The message sent to JD Edwards OneWorld is a single message, single reply architecture.</span></span> <span data-ttu-id="81b92-132">不能同时处理多个消息。</span><span class="sxs-lookup"><span data-stu-id="81b92-132">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="81b92-133">响应文档通过 ThinNet 发回，转换为 XML，然后传输回 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="81b92-133">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="81b92-134">设计时的出站事件</span><span class="sxs-lookup"><span data-stu-id="81b92-134">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="81b92-135">事件元数据的系统创建不可用。</span><span class="sxs-lookup"><span data-stu-id="81b92-135">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="81b92-136">必须为 Visual Studio 提供事件文档的传真，以便生成架构并与目标命名空间一起合并到项目中。</span><span class="sxs-lookup"><span data-stu-id="81b92-136">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="81b92-137">运行时的出站事件</span><span class="sxs-lookup"><span data-stu-id="81b92-137">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="81b92-138">在 JD Edwards 企业服务器中建立文件传输机制，以将事件完成触发的 XML 结果文档传输到该服务器的目标目录。</span><span class="sxs-lookup"><span data-stu-id="81b92-138">A file transport mechanism is established in the JD Edwards enterprise server to transport the resulting XML document, triggered by the event completion, to the target directory on that server.</span></span>  
  
-   <span data-ttu-id="81b92-139">BizTalk Server 计算机拥有一个到企业服务器上目录的映射驱动器。</span><span class="sxs-lookup"><span data-stu-id="81b92-139">The BizTalk Server computer has a mapped drive to the directory on the enterprise server.</span></span>  
  
-   <span data-ttu-id="81b92-140">已经为映射的驱动器配置了接收端口传输属性。</span><span class="sxs-lookup"><span data-stu-id="81b92-140">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="81b92-141">接收端口接收企业服务器发布到目录的消息。</span><span class="sxs-lookup"><span data-stu-id="81b92-141">The receive port receives messages posted to directory by the enterprise server.</span></span>  
  
-   <span data-ttu-id="81b92-142">目标名称空间标识确保将正确的消息路由到配置的接收端口。</span><span class="sxs-lookup"><span data-stu-id="81b92-142">The target namespace identification ensures that the correct messages are routed to the configured receive port.</span></span>  
  
-   <span data-ttu-id="81b92-143">接收端口将 XML 文档提交到 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="81b92-143">The receive port submits the XML document to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81b92-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81b92-144">See Also</span></span>  
 <span data-ttu-id="81b92-145">[如何设置博士 Edwards OneWorld 传输属性](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span><span class="sxs-lookup"><span data-stu-id="81b92-145">[How to Set JD Edwards OneWorld Transport Properties](../core/how-to-set-jd-edwards-oneworld-transport-properties.md) </span></span>  
 [<span data-ttu-id="81b92-146">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="81b92-146">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)