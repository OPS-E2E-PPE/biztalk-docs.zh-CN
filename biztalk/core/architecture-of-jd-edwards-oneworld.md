---
title: JD Edwards OneWorld 的体系结构 |Microsoft Docs
description: 在设计时和运行的时和出站事件在设计时和运行的时在 BizTalk 中的 JD Edwards OneWorld 适配器中描述的入站的服务
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9200a090-a587-4b60-9447-d281580f2078
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e98b7196077d0754ef067d01a51b49b96dc8f9e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65358990"
---
# <a name="architecture-of-jd-edwards-oneworld"></a><span data-ttu-id="6c1d2-103">JD Edwards OneWorld 的体系结构</span><span class="sxs-lookup"><span data-stu-id="6c1d2-103">Architecture of JD Edwards OneWorld</span></span>
<span data-ttu-id="6c1d2-104">用于 JD Edwards OneWorld 的 Microsoft BizTalk 适配器提供了对 JD Edwards OneWorld 业务功能的访问。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-104">Microsoft BizTalk Adapter for JD Edwards OneWorld provides access to JD Edwards OneWorld business functions.</span></span> <span data-ttu-id="6c1d2-105">JD Edwards OneWorld 使用消息传递体系结构称为 JDENet 的专用的客户端和服务器计算机之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-105">JD Edwards OneWorld communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="6c1d2-106">JDENet 由 JAR 文件，Connector.jar 和 Kernel.jar 中找到的 JD Edwards OneWorld 连接器类实现。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-106">JDENet is implemented by the JD Edwards OneWorld connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="6c1d2-107">使用 TCP/IP 作为传输协议，默认端口为 6009 或 6010 实现通信。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-107">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="6c1d2-108">此值设置的位置的说明，请参阅[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-108">For a description of where this value is set, see [Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span></span>  
  
 <span data-ttu-id="6c1d2-109">**用于 JD Edwards OneWorld 的 BizTalk 适配器的体系结构**</span><span class="sxs-lookup"><span data-stu-id="6c1d2-109">**Architecture for BizTalk Adapter for JD Edwards OneWorld**</span></span>  
  
 <span data-ttu-id="6c1d2-110">![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")</span><span class="sxs-lookup"><span data-stu-id="6c1d2-110">![](../core/media/jdedadapter-01-architecture.gif "JDEdAdapter_01_Architecture")</span></span>  
  
 <span data-ttu-id="6c1d2-111">对 JD Edwards OneWorld 业务函数的调用需要两条消息：</span><span class="sxs-lookup"><span data-stu-id="6c1d2-111">Calls to JD Edwards OneWorld business functions require two messages:</span></span>  
  
-   <span data-ttu-id="6c1d2-112">第一条消息息响应处理业务功能的服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-112">The first message responds with the location of the server that processes the business function.</span></span> <span data-ttu-id="6c1d2-113">这通过一系列名为的表中执行查找来实现*对象配置映射 (OCM)*。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-113">This is accomplished by performing a lookup in a set of tables called *object configuration mapping (OCM)*.</span></span>  
  
-   <span data-ttu-id="6c1d2-114">第二条消息将发送包含要传递到相应的服务器，到或从 JD Edwards OneWorld 的参数的格式的消息缓冲区，并等待回复。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-114">The second message sends a formatted message buffer containing the arguments to pass to or from JD Edwards OneWorld to the appropriate server, and waits for a reply.</span></span> <span data-ttu-id="6c1d2-115">对缓冲区进行格式化的基础类型定义根据C++结构。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-115">The buffers are formatted according to the typedefs of the underlying C++ structs.</span></span>  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="6c1d2-116">在设计时的入站服务</span><span class="sxs-lookup"><span data-stu-id="6c1d2-116">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="6c1d2-117">在设计时，创建你的端口、 选择适配器，并提供凭据信息连接到目标 JD Edwards OneWorld 服务器。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-117">At design time, you create your port, select the adapter, and provide credential information to connect to the target JD Edwards OneWorld server.</span></span> <span data-ttu-id="6c1d2-118">在 Visual Studio 开发环境调用适配器框架，以请求为此端口的设计时信息。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-118">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="6c1d2-119">用于 JD Edwards OneWorld 的 BizTalk 适配器使用此端口的 Browsingagent。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-119">BizTalk Adapter for JD Edwards OneWorld uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="6c1d2-120">在设计时，BizTalk Server 通过调用适配器来请求信息。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-120">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="6c1d2-121">Browsingagent 将请求转换为本机 JD Edwards OneWorld 代码，然后将请求传输到 JD Edwards OneWorld 通过 ThinNet API 连接 （连接器和 Kernel.jar 中建立）。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-121">The Browsingagent converts the request into native JD Edwards OneWorld code and then transmits the requests to JD Edwards OneWorld through the ThinNet API connection (established in the Connector and Kernel.jars).</span></span>  
  
-   <span data-ttu-id="6c1d2-122">通过 BTSREL 安装安装自定义业务函数： 它公开了主业务功能。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-122">A custom business function is installed through the BTSREL installation: it exposes the master business functions.</span></span>  
  
-   <span data-ttu-id="6c1d2-123">最初返回 JD Edwards OneWorld 中的模块的列表并将其传输到 Visual Studio 中，填充适配器向导。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-123">A list of modules in JD Edwards OneWorld is initially returned and transported to Visual Studio, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="6c1d2-124">您可以展开层次结构显示库名称和模块名称。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-124">You can expand the hierarchy to display the library name and module name.</span></span>  
  
-   <span data-ttu-id="6c1d2-125">选择特定模块时，可以看到该模块中的所有函数的架构。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-125">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="6c1d2-126">适配器从 JD Edwards OneWorld 获取所需的信息，browsingagent 创建架构。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-126">The adapter obtains the required information from JD Edwards OneWorld, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="6c1d2-127">架构将添加到 BizTalk Server 项目业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-127">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="6c1d2-128">在运行时的入站服务</span><span class="sxs-lookup"><span data-stu-id="6c1d2-128">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="6c1d2-129">BizTalk Server 调用用于 JD Edwards OneWorld 特定端口上发送消息的 BizTalk 适配器。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-129">BizTalk Server calls the BizTalk Adapter for JD Edwards OneWorld to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="6c1d2-130">运行时代理将 XML 转换为本机 JD Edwards 代码。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-130">The run-time agent converts the XML into native JD Edwards code.</span></span>  
  
-   <span data-ttu-id="6c1d2-131">运行时代理通过 ThinNet 到发送端口的传输属性中指定的 JD Edwards 企业系统将请求提交。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-131">The run-time agent submits the request through the ThinNet to the JD Edwards enterprise system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="6c1d2-132">在 JD Edwards 系统上，然后生成一个，该值指示成功或失败，以及数据的响应文档执行主业务函数返回的业务函数的参数。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-132">The master business function is executed on the JD Edwards system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="6c1d2-133">发送到 JD Edwards OneWorld 的消息是单消息、 单回复结构。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-133">The message sent to JD Edwards OneWorld is a single message, single reply architecture.</span></span> <span data-ttu-id="6c1d2-134">不能同时处理多条消息。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-134">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="6c1d2-135">响应文档通过 ThinNet 发回，转换为 XML，并传输回 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-135">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="6c1d2-136">在设计时的出站事件</span><span class="sxs-lookup"><span data-stu-id="6c1d2-136">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="6c1d2-137">提供的事件元数据系统创建。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-137">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="6c1d2-138">必须为 Visual Studio 提供事件文档的传真，以便可以生成一个架构，并将其合并到一个项目，以及目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-138">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="6c1d2-139">在运行时的出站事件</span><span class="sxs-lookup"><span data-stu-id="6c1d2-139">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="6c1d2-140">要传输生成的 XML 文档中，触发的事件完成时，到该服务器上的目标目录的 JD Edwards 企业服务器中建立文件传输机制。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-140">A file transport mechanism is established in the JD Edwards enterprise server to transport the resulting XML document, triggered by the event completion, to the target directory on that server.</span></span>  
  
-   <span data-ttu-id="6c1d2-141">BizTalk Server 计算机具有企业服务器上的目录映射的驱动器。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-141">The BizTalk Server computer has a mapped drive to the directory on the enterprise server.</span></span>  
  
-   <span data-ttu-id="6c1d2-142">接收端口传输属性配置为映射的驱动器。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-142">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="6c1d2-143">接收端口接收企业服务器发布到目录的消息。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-143">The receive port receives messages posted to directory by the enterprise server.</span></span>  
  
-   <span data-ttu-id="6c1d2-144">目标命名空间标识确保将正确的消息路由到配置的接收端口。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-144">The target namespace identification ensures that the correct messages are routed to the configured receive port.</span></span>  
  
-   <span data-ttu-id="6c1d2-145">接收端口将提交到 BizTalk Server 的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="6c1d2-145">The receive port submits the XML document to BizTalk Server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c1d2-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c1d2-146">See Also</span></span>  
 <span data-ttu-id="6c1d2-147">[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span><span class="sxs-lookup"><span data-stu-id="6c1d2-147">[Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md) </span></span>  
 [<span data-ttu-id="6c1d2-148">规划和体系结构</span><span class="sxs-lookup"><span data-stu-id="6c1d2-148">Planning and Architecture</span></span>](../core/planning-and-architecture17.md)