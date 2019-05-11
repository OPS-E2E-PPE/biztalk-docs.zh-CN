---
title: 用于 JD Edwards EnterpriseOne 的 BizTalk 适配器的体系结构 |Microsoft Docs
description: 在设计时和运行的时和出站事件在设计时和运行的时在 BizTalk 中的 JD Edwards EnterpriseOne 适配器中描述的入站的服务
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0441c5d2-6a46-45b6-8ab5-0bdac3590f56
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dc7992262731532f2c9df6b29896f48f5f74e5d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65359365"
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="2d10d-103">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器的体系结构</span><span class="sxs-lookup"><span data-stu-id="2d10d-103">Architecture of BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="2d10d-104">用于 JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器提供了对 JD Edwards EnterpriseOne 业务功能的访问。</span><span class="sxs-lookup"><span data-stu-id="2d10d-104">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="2d10d-105">JD Edwards EnterpriseOne 使用消息传递体系结构称为 JDENet 的专用的客户端和服务器计算机之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="2d10d-105">JD Edwards EnterpriseOne communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="2d10d-106">JDENet 由 JAR 文件，Connector.jar 和 Kernel.jar 中找到的 JD Edwards EnterpriseOne 连接器类实现。</span><span class="sxs-lookup"><span data-stu-id="2d10d-106">JDENet is implemented by the JD Edwards EnterpriseOne connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="2d10d-107">使用 TCP/IP 作为传输协议，默认端口为 6009 或 6010 实现通信。</span><span class="sxs-lookup"><span data-stu-id="2d10d-107">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="2d10d-108">此值设置的位置的说明，请参阅[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)。</span><span class="sxs-lookup"><span data-stu-id="2d10d-108">For a description of where this value is set, see [Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span></span>  
  
 <span data-ttu-id="2d10d-109">下图显示有关用于 JD Edwards EnterpriseOne 的 BizTalk 适配器体系结构。</span><span class="sxs-lookup"><span data-stu-id="2d10d-109">The following figure shows the architecture for BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
 <span data-ttu-id="2d10d-110">![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")</span><span class="sxs-lookup"><span data-stu-id="2d10d-110">![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")</span></span>  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="2d10d-111">在设计时的入站服务</span><span class="sxs-lookup"><span data-stu-id="2d10d-111">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="2d10d-112">在设计时创建的端口、 选择一个适配器，并提供凭据信息连接到目标 JD Edwards EnterpriseOne 服务器。</span><span class="sxs-lookup"><span data-stu-id="2d10d-112">At design time, you create a port, select an adapter, and provide credential information to connect to the target JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="2d10d-113">在 Visual Studio 开发环境调用适配器框架，以请求为此端口的设计时信息。</span><span class="sxs-lookup"><span data-stu-id="2d10d-113">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="2d10d-114">适配器使用此端口的 Browsingagent。</span><span class="sxs-lookup"><span data-stu-id="2d10d-114">The adapter uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="2d10d-115">在设计时，BizTalk Server 通过调用适配器来请求信息。</span><span class="sxs-lookup"><span data-stu-id="2d10d-115">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="2d10d-116">Browsingagent 将请求转换为本机 JD Edwards EnterpriseOne 代码，并将请求传输到 JD Edwards EnterpriseOne 通过 ThinNet API 连接 （在 Connector.jar 和 Kernel.jar 中建立）。</span><span class="sxs-lookup"><span data-stu-id="2d10d-116">The Browsingagent converts the request into native JD Edwards EnterpriseOne code and transmits the requests to JD Edwards EnterpriseOne through the ThinNet API connection (established in Connector.jar and Kernel.jar).</span></span>  
  
-   <span data-ttu-id="2d10d-117">最初返回 JD Edwards EnterpriseOne 中的模块的列表并将其传输到 Visual Studio 开发环境，其中它将填充适配器向导。</span><span class="sxs-lookup"><span data-stu-id="2d10d-117">A list of Modules in JD Edwards EnterpriseOne is initially returned and transported to the Visual Studio development environment, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="2d10d-118">通过显示库名称，然后选择模块名称，可以展开层次结构。</span><span class="sxs-lookup"><span data-stu-id="2d10d-118">You can expand the hierarchy by displaying the library name and then the module name.</span></span>  
  
-   <span data-ttu-id="2d10d-119">选择特定模块时，可以看到该模块中的所有函数的架构。</span><span class="sxs-lookup"><span data-stu-id="2d10d-119">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="2d10d-120">适配器从 JD Edwards EnterpriseOne 获取所需的信息，browsingagent 创建架构。</span><span class="sxs-lookup"><span data-stu-id="2d10d-120">The adapter gets the required information from JD Edwards EnterpriseOne, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="2d10d-121">架构将添加到 BizTalk Server 项目业务流程。</span><span class="sxs-lookup"><span data-stu-id="2d10d-121">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="2d10d-122">在运行时的入站服务</span><span class="sxs-lookup"><span data-stu-id="2d10d-122">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="2d10d-123">BizTalk Server 调用适配器的特定端口上发送消息。</span><span class="sxs-lookup"><span data-stu-id="2d10d-123">BizTalk Server calls the adapter to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="2d10d-124">运行时代理将 XML 转换为本机 JDE 代码。</span><span class="sxs-lookup"><span data-stu-id="2d10d-124">The run-time agent converts the XML into native JDE code.</span></span>  
  
-   <span data-ttu-id="2d10d-125">运行时代理通过 ThinNet 到发送端口的传输属性中指定的 JD Edwards EnterpriseOne 系统将请求提交。</span><span class="sxs-lookup"><span data-stu-id="2d10d-125">The run-time agent submits the request through the ThinNet to the JD Edwards EnterpriseOne system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="2d10d-126">JD Edwards EnterpriseOne 系统，然后生成一个，该值指示成功或失败，以及数据的响应文档上执行主业务功能返回的业务函数的参数。</span><span class="sxs-lookup"><span data-stu-id="2d10d-126">The Master Business Function is executed on the JD Edwards EnterpriseOne system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="2d10d-127">发送到 JD Edwards EnterpriseOne 的消息是单消息、 单回复结构。</span><span class="sxs-lookup"><span data-stu-id="2d10d-127">The message sent to JD Edwards EnterpriseOne is a single message, single reply architecture.</span></span> <span data-ttu-id="2d10d-128">不能同时处理多条消息。</span><span class="sxs-lookup"><span data-stu-id="2d10d-128">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="2d10d-129">响应文档通过 ThinNet 发回，转换为 XML，并传输回 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="2d10d-129">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="2d10d-130">在设计时的出站事件</span><span class="sxs-lookup"><span data-stu-id="2d10d-130">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="2d10d-131">提供的事件元数据系统创建。</span><span class="sxs-lookup"><span data-stu-id="2d10d-131">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="2d10d-132">必须为 Visual Studio 提供事件文档的传真，以便可以生成一个架构，并将其合并到一个项目，以及目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="2d10d-132">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="2d10d-133">在运行时的出站事件</span><span class="sxs-lookup"><span data-stu-id="2d10d-133">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="2d10d-134">要传输生成的 XML 文档中，触发的事件完成时，到该计算机上的目标目录的 JD Edwards EnterpriseOne 服务器中建立文件传输机制。</span><span class="sxs-lookup"><span data-stu-id="2d10d-134">A file transport mechanism is established in the JD Edwards EnterpriseOne server to transport the resulting XML document, triggered by the event completion, to the target directory on that computer.</span></span>  
  
-   <span data-ttu-id="2d10d-135">BizTalk Server 计算机已经 EnterpriseOne 服务器上的目录映射的驱动器。</span><span class="sxs-lookup"><span data-stu-id="2d10d-135">The BizTalk Server computer has a mapped drive to the directory on the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="2d10d-136">接收端口传输属性配置为映射的驱动器。</span><span class="sxs-lookup"><span data-stu-id="2d10d-136">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="2d10d-137">接收端口接收 EnterpriseOne 服务器发布到目录的消息。</span><span class="sxs-lookup"><span data-stu-id="2d10d-137">The receive port receives messages, which are posted to a directory by the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="2d10d-138">目标命名空间标识确保将正确的消息路由到配置的接收端口</span><span class="sxs-lookup"><span data-stu-id="2d10d-138">The target namespace identification ensures that the correct messages are routed to the configured receive port</span></span>  
  
-   <span data-ttu-id="2d10d-139">接收端口提交 BizTalk Server 中的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="2d10d-139">The receive port submits the XML document in BizTalk Server.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="2d10d-140">更多有用资料</span><span class="sxs-lookup"><span data-stu-id="2d10d-140">More good stuff</span></span>
[<span data-ttu-id="2d10d-141">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="2d10d-141">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="2d10d-142">创建应用程序项目</span><span class="sxs-lookup"><span data-stu-id="2d10d-142">Create the application artifacts</span></span>](../core/developing-applications2.md)  
[<span data-ttu-id="2d10d-143">导入 JD Edwards EnterpriseOne 应用程序</span><span class="sxs-lookup"><span data-stu-id="2d10d-143">Import your JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="2d10d-144">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="2d10d-144">Use BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)  
[<span data-ttu-id="2d10d-145">故障排除</span><span class="sxs-lookup"><span data-stu-id="2d10d-145">Troubleshoot</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)  
