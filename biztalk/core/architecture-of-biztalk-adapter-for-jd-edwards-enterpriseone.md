---
title: 体系结构的 BizTalk Adapter for 博士 Edwards EnterpriseOne |Microsoft 文档
description: 在设计时和在 BizTalk 博士 Edwards EnterpriseOne 适配器中的运行的时在设计时和运行的时和出站事件描述的入站的服务
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
ms.openlocfilehash: b495ee9a34cf464bd5cc11caed53c5df54948a49
ms.sourcegitcommit: dd7c54feab783ae2f8fe75873363fe9ffc77cd66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2017
ms.locfileid: "24013756"
---
# <a name="architecture-of-biztalk-adapter-for-jd-edwards-enterpriseone"></a><span data-ttu-id="8889f-103">JD Edwards EnterpriseOne 的  BizTalk 适配器的体系结构</span><span class="sxs-lookup"><span data-stu-id="8889f-103">Architecture of BizTalk Adapter for JD Edwards EnterpriseOne</span></span>
<span data-ttu-id="8889f-104">JD Edwards EnterpriseOne 的 Microsoft BizTalk 适配器提供对 JD Edwards EnterpriseOne 业务功能的访问。</span><span class="sxs-lookup"><span data-stu-id="8889f-104">Microsoft BizTalk Adapter for JD Edwards EnterpriseOne provides access to JD Edwards EnterpriseOne business functions.</span></span> <span data-ttu-id="8889f-105">JD Edwards EnterpriseOne 使用称为 JDENet 的专用消息体系结构在客户端和服务器计算机之间进行通信。</span><span class="sxs-lookup"><span data-stu-id="8889f-105">JD Edwards EnterpriseOne communicates between client and server machines using a proprietary messaging architecture called JDENet.</span></span> <span data-ttu-id="8889f-106">JDENet 由 Connector.jar 和 Kernel.jar JAR 文件中找到的博士 Edwards EnterpriseOne 连接器类实现。</span><span class="sxs-lookup"><span data-stu-id="8889f-106">JDENet is implemented by the JD Edwards EnterpriseOne connector classes found in the JAR files, Connector.jar and Kernel.jar.</span></span> <span data-ttu-id="8889f-107">使用 TCP/IP 作为传输协议，使用默认端口的 6009 或 6010 实现通信。</span><span class="sxs-lookup"><span data-stu-id="8889f-107">Communication is implemented using TCP/IP as a transport protocol, with a default port of 6009 or 6010.</span></span> <span data-ttu-id="8889f-108">此值设置有关位置的说明，请参阅[将项目添加到 BizTalk 管理](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md)。</span><span class="sxs-lookup"><span data-stu-id="8889f-108">For a description of where this value is set, see [Add the artifacts to BizTalk Administration](../core/adding-biztalk-adapter-for-jd-edwards-oneworld.md).</span></span>  
  
 <span data-ttu-id="8889f-109">下图显示 JD Edwards EnterpriseOne 的 BizTalk 适配器的架构。</span><span class="sxs-lookup"><span data-stu-id="8889f-109">The following figure shows the architecture for BizTalk Adapter for JD Edwards EnterpriseOne.</span></span>  
  
 ![](../core/media/jd-enterpriseone-arch.gif "JD_EnterpriseOne_arch")  
  
## <a name="inbound-services-at-design-time"></a><span data-ttu-id="8889f-110">设计时的入站服务</span><span class="sxs-lookup"><span data-stu-id="8889f-110">Inbound Services at Design Time</span></span>  
  
-   <span data-ttu-id="8889f-111">在设计时，您将创建一个端口，选择一个适配器，并提供用于连接到目标 JD Edwards EnterpriseOne 服务器的凭据信息。</span><span class="sxs-lookup"><span data-stu-id="8889f-111">At design time, you create a port, select an adapter, and provide credential information to connect to the target JD Edwards EnterpriseOne server.</span></span> <span data-ttu-id="8889f-112">Visual Studio 开发环境调用适配器框架，以请求此端口的设计时信息。</span><span class="sxs-lookup"><span data-stu-id="8889f-112">The Visual Studio development environment calls the adapter framework to request design-time information for this port.</span></span> <span data-ttu-id="8889f-113">适配器使用此端口的 Browsingagent。</span><span class="sxs-lookup"><span data-stu-id="8889f-113">The adapter uses the Browsingagent for this port.</span></span>  
  
-   <span data-ttu-id="8889f-114">在设计时，BizTalk Server 通过调用适配器来请求信息。</span><span class="sxs-lookup"><span data-stu-id="8889f-114">At design time, BizTalk Server requests information by making calls to the adapter.</span></span>  
  
-   <span data-ttu-id="8889f-115">Browsingagent 将请求转换为本机 JD Edwards EnterpriseOne 代码，并通过 ThinNet API 连接（在 Connector.jar 和 Kernel.jar 中建立）将请求传输到 JD Edwards EnterpriseOne。</span><span class="sxs-lookup"><span data-stu-id="8889f-115">The Browsingagent converts the request into native JD Edwards EnterpriseOne code and transmits the requests to JD Edwards EnterpriseOne through the ThinNet API connection (established in Connector.jar and Kernel.jar).</span></span>  
  
-   <span data-ttu-id="8889f-116">首先返回 JD Edwards EnterpriseOne 中的模块的列表，并将其传输到填充适配器向导的 Visual Studio 开发环境。</span><span class="sxs-lookup"><span data-stu-id="8889f-116">A list of Modules in JD Edwards EnterpriseOne is initially returned and transported to the Visual Studio development environment, where it populates the Adapter Wizard.</span></span>  
  
-   <span data-ttu-id="8889f-117">您可以通过先显示库名称，然后显示模块名称来扩展层次结构。</span><span class="sxs-lookup"><span data-stu-id="8889f-117">You can expand the hierarchy by displaying the library name and then the module name.</span></span>  
  
-   <span data-ttu-id="8889f-118">选择特定模块时，您将看到模块中所有功能的架构。</span><span class="sxs-lookup"><span data-stu-id="8889f-118">When you select a specific module, you see schemas for all functions within the module.</span></span> <span data-ttu-id="8889f-119">适配器从 JD Edwards EnterpriseOne 获取所需信息，browsingagent 创建架构。</span><span class="sxs-lookup"><span data-stu-id="8889f-119">The adapter gets the required information from JD Edwards EnterpriseOne, and the browsingagent creates the schemas.</span></span>  
  
-   <span data-ttu-id="8889f-120">架构添加到 BizTalk Server 项目业务流程。</span><span class="sxs-lookup"><span data-stu-id="8889f-120">The schemas are added to the BizTalk Server project orchestration.</span></span>  
  
## <a name="inbound-services-at-run-time"></a><span data-ttu-id="8889f-121">运行时的入站服务</span><span class="sxs-lookup"><span data-stu-id="8889f-121">Inbound Services at Run Time</span></span>  
  
-   <span data-ttu-id="8889f-122">BizTalk Server 调用适配器以在特定端口上发送消息。</span><span class="sxs-lookup"><span data-stu-id="8889f-122">BizTalk Server calls the adapter to send a message on a specific port.</span></span>  
  
-   <span data-ttu-id="8889f-123">运行时代理将 XML 转换为本机 JDE 代码。</span><span class="sxs-lookup"><span data-stu-id="8889f-123">The run-time agent converts the XML into native JDE code.</span></span>  
  
-   <span data-ttu-id="8889f-124">运行时代理通过 ThinNet 将请求提交到发送端口的传输属性中指定的 JD Edwards EnterpriseOne 系统。</span><span class="sxs-lookup"><span data-stu-id="8889f-124">The run-time agent submits the request through the ThinNet to the JD Edwards EnterpriseOne system specified in the transport properties of the send port.</span></span>  
  
-   <span data-ttu-id="8889f-125">在 JD Edwards EnterpriseOne 系统上执行主业务功能，然后生成一个响应文档，指示成功或失败以及业务功能返回的数据参数。</span><span class="sxs-lookup"><span data-stu-id="8889f-125">The Master Business Function is executed on the JD Edwards EnterpriseOne system, which then generates a response document indicating success or failure as well as data parameters returned by the business function.</span></span>  
  
-   <span data-ttu-id="8889f-126">发送到 JD Edwards EnterpriseOne 的消息是一种单消息、单回复结构。</span><span class="sxs-lookup"><span data-stu-id="8889f-126">The message sent to JD Edwards EnterpriseOne is a single message, single reply architecture.</span></span> <span data-ttu-id="8889f-127">不能同时处理多个消息。</span><span class="sxs-lookup"><span data-stu-id="8889f-127">Multiple messages cannot be processed at the same time.</span></span>  
  
-   <span data-ttu-id="8889f-128">响应文档通过 ThinNet 发回，转换为 XML，然后传输回 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="8889f-128">The response document is sent back through ThinNet, converted to XML, and transmitted back to BizTalk Server.</span></span>  
  
## <a name="outbound-events-at-design-time"></a><span data-ttu-id="8889f-129">设计时的出站事件</span><span class="sxs-lookup"><span data-stu-id="8889f-129">Outbound Events at Design Time</span></span>  
  
-   <span data-ttu-id="8889f-130">事件元数据的系统创建不可用。</span><span class="sxs-lookup"><span data-stu-id="8889f-130">No systematic creation of event metadata is available.</span></span>  
  
-   <span data-ttu-id="8889f-131">必须为 Visual Studio 提供事件文档的传真，以便生成架构并与目标命名空间一起合并到项目中。</span><span class="sxs-lookup"><span data-stu-id="8889f-131">A facsimile of the event document must be supplied to Visual Studio so that a schema can be generated and incorporated into the project along with the target namespace.</span></span>  
  
## <a name="outbound-events-at-run-time"></a><span data-ttu-id="8889f-132">运行时的出站事件</span><span class="sxs-lookup"><span data-stu-id="8889f-132">Outbound Events at Run Time</span></span>  
  
-   <span data-ttu-id="8889f-133">在 JD Edwards EnterpriseOne 服务器中建立文件传输机制，以便将事件完成触发的结果 XML 文档传输到该计算机的目标目录。</span><span class="sxs-lookup"><span data-stu-id="8889f-133">A file transport mechanism is established in the JD Edwards EnterpriseOne server to transport the resulting XML document, triggered by the event completion, to the target directory on that computer.</span></span>  
  
-   <span data-ttu-id="8889f-134">BizTalk Server 计算机已将驱动器映射到 EnterpriseOne 服务器上的目录。</span><span class="sxs-lookup"><span data-stu-id="8889f-134">The BizTalk Server computer has a mapped drive to the directory on the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="8889f-135">已经为映射的驱动器配置了接收端口传输属性。</span><span class="sxs-lookup"><span data-stu-id="8889f-135">The receive port transport properties are configured for the mapped drive.</span></span> <span data-ttu-id="8889f-136">该接收端口接收 EnterpriseOne 服务器发布到目录的消息。</span><span class="sxs-lookup"><span data-stu-id="8889f-136">The receive port receives messages, which are posted to a directory by the EnterpriseOne server.</span></span>  
  
-   <span data-ttu-id="8889f-137">目标命名空间标识确保路由到已配置的接收端口的消息正确。</span><span class="sxs-lookup"><span data-stu-id="8889f-137">The target namespace identification ensures that the correct messages are routed to the configured receive port</span></span>  
  
-   <span data-ttu-id="8889f-138">接收端口提交 BizTalk Server 中的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="8889f-138">The receive port submits the XML document in BizTalk Server.</span></span>  
  
## <a name="more-good-stuff"></a><span data-ttu-id="8889f-139">更多有用内容</span><span class="sxs-lookup"><span data-stu-id="8889f-139">More good stuff</span></span>
[<span data-ttu-id="8889f-140">用于 JD Edwards EnterpriseOne 的 BizTalk 适配器中的安全性</span><span class="sxs-lookup"><span data-stu-id="8889f-140">Security in BizTalk Adapter for JD Edwards EnterpriseOne</span></span>](../core/security-in-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="8889f-141">创建应用程序项目</span><span class="sxs-lookup"><span data-stu-id="8889f-141">Create the application artifacts</span></span>](../core/developing-applications2.md)  
[<span data-ttu-id="8889f-142">导入博士 Edwards EnterpriseOne 应用</span><span class="sxs-lookup"><span data-stu-id="8889f-142">Import your JD Edwards EnterpriseOne app</span></span>](../core/deploying-biztalk-adapter-for-jd-edwards-enterpriseone.md)  
[<span data-ttu-id="8889f-143">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="8889f-143">Use BizTalk Server Exception Handling</span></span>](../core/using-biztalk-server-exception-handling3.md)  
[<span data-ttu-id="8889f-144">故障排除</span><span class="sxs-lookup"><span data-stu-id="8889f-144">Troubleshoot</span></span>](../core/troubleshooting-jd-edwards-enterpriseone.md)  
