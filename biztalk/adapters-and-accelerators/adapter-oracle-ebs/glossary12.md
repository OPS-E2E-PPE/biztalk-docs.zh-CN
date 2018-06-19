---
title: BizTalk 中的 Oracle E-business Suite 适配器的术语表 |Microsoft 文档
description: 常见术语和定义为 Oracle EBS 适配器 BizTalk 适配器包 (BAP) 中
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 328b0ed2-58e2-45d5-8322-a72179ad5c8b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56f51dd1cc8897d5593a382ec4600a07d8f1e50e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22218637"
---
# <a name="glossary"></a><span data-ttu-id="d68d5-103">词汇表</span><span class="sxs-lookup"><span data-stu-id="d68d5-103">Glossary</span></span>
<span data-ttu-id="d68d5-104">中使用以下术语和定义[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d68d5-104">The following terms and definitions are used in [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)].</span></span>  
  
## <a name="a"></a><span data-ttu-id="d68d5-105">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="d68d5-105">A</span></span>  
  
<span data-ttu-id="d68d5-106">**适配器**</span><span class="sxs-lookup"><span data-stu-id="d68d5-106">**adapter**</span></span>  
<span data-ttu-id="d68d5-107">应用程序 （例如，业务线系统） 之间的基于 WCF 的组件，可帮助 exchange 消息和 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="d68d5-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="d68d5-108">适配器由执行接收操作和发送操作的设计时组件和运行时组件组成。</span><span class="sxs-lookup"><span data-stu-id="d68d5-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="d68d5-109">**适配器客户端**</span><span class="sxs-lookup"><span data-stu-id="d68d5-109">**adapter client**</span></span>  
<span data-ttu-id="d68d5-110">应用程序与通过适配器的业务线 (LOB) 系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="d68d5-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>  
  
## <a name="b"></a><span data-ttu-id="d68d5-111">B</span><span class="sxs-lookup"><span data-stu-id="d68d5-111">B</span></span>  
  
<span data-ttu-id="d68d5-112">**绑定**</span><span class="sxs-lookup"><span data-stu-id="d68d5-112">**binding**</span></span>  
<span data-ttu-id="d68d5-113">链接软件组件和层的过程。</span><span class="sxs-lookup"><span data-stu-id="d68d5-113">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="d68d5-114">安装网络组件时，会建立组件间的绑定关系和依存关系。</span><span class="sxs-lookup"><span data-stu-id="d68d5-114">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="d68d5-115">绑定可使组件之间互相通信。</span><span class="sxs-lookup"><span data-stu-id="d68d5-115">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="d68d5-116">在 BizTalk Server 中，指的是与业务流程适配器无关的终结点（端口或角色链接）和特定于物理适配器的终结点（发送/接收端口或参与方）之间已建立的映射。</span><span class="sxs-lookup"><span data-stu-id="d68d5-116">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="d68d5-117">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="d68d5-117">**BizTalk Server**</span></span>  
<span data-ttu-id="d68d5-118">连接不同的软件。</span><span class="sxs-lookup"><span data-stu-id="d68d5-118">Connects diverse software.</span></span> <span data-ttu-id="d68d5-119">BizTalk Server，可创建和修改过程逻辑，它使用该软件。</span><span class="sxs-lookup"><span data-stu-id="d68d5-119">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="d68d5-120">使用 BizTalk Server，信息工作者还可以监视正在运行的进程、与贸易合作伙伴进行交互，以及执行其他面向企业的任务。</span><span class="sxs-lookup"><span data-stu-id="d68d5-120">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>
  
## <a name="c"></a><span data-ttu-id="d68d5-121">C</span><span class="sxs-lookup"><span data-stu-id="d68d5-121">C</span></span>  
  
<span data-ttu-id="d68d5-122">**通道**</span><span class="sxs-lookup"><span data-stu-id="d68d5-122">**channel**</span></span>  
<span data-ttu-id="d68d5-123">绑定元素的具体实现。</span><span class="sxs-lookup"><span data-stu-id="d68d5-123">A concrete implementation of a binding element.</span></span> <span data-ttu-id="d68d5-124">绑定表示配置，而通道是与该配置相关联的实现。</span><span class="sxs-lookup"><span data-stu-id="d68d5-124">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="d68d5-125">因此，没有与每个绑定元素关联的通道。</span><span class="sxs-lookup"><span data-stu-id="d68d5-125">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="d68d5-126">通道堆叠在一起以形成绑定的具体实现： 通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="d68d5-126">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="d68d5-127">**连接 URI**</span><span class="sxs-lookup"><span data-stu-id="d68d5-127">**connection URI**</span></span>  
<span data-ttu-id="d68d5-128">一个字符串，标识分布式环境中的资源。</span><span class="sxs-lookup"><span data-stu-id="d68d5-128">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="d68d5-129">适配器使用的连接统一资源标识符 (URI)，包含与 LOB 系统建立连接所需的信息。</span><span class="sxs-lookup"><span data-stu-id="d68d5-129">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="d68d5-130">**协定**</span><span class="sxs-lookup"><span data-stu-id="d68d5-130">**contract**</span></span>  
<span data-ttu-id="d68d5-131">指定的集合和访问服务提供的操作所必需的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="d68d5-131">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>  
  
## <a name="d"></a><span data-ttu-id="d68d5-132">D</span><span class="sxs-lookup"><span data-stu-id="d68d5-132">D</span></span>  
  
<span data-ttu-id="d68d5-133">**数据操作语言 (DML)**</span><span class="sxs-lookup"><span data-stu-id="d68d5-133">**data manipulation language (DML)**</span></span>  
<span data-ttu-id="d68d5-134">用于检索和操作数据的 SQL 语句的子集。</span><span class="sxs-lookup"><span data-stu-id="d68d5-134">The subset of SQL statements that is used to retrieve and manipulate data.</span></span> <span data-ttu-id="d68d5-135">DML 语句通常以 SELECT、 INSERT、 UPDATE 或 DELETE 开头。</span><span class="sxs-lookup"><span data-stu-id="d68d5-135">DML statements typically start with SELECT, INSERT, UPDATE, or DELETE.</span></span>

<span data-ttu-id="d68d5-136">**设计时体验**</span><span class="sxs-lookup"><span data-stu-id="d68d5-136">**design-time experience**</span></span>  
<span data-ttu-id="d68d5-137">过程和开发人员在设计时; 期间执行的操作例如，使用使用适配器服务 BizTalk 项目外接程序检索消息架构。</span><span class="sxs-lookup"><span data-stu-id="d68d5-137">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span>  
  
## <a name="e"></a><span data-ttu-id="d68d5-138">E</span><span class="sxs-lookup"><span data-stu-id="d68d5-138">E</span></span>  
  
<span data-ttu-id="d68d5-139">**终结点地址**</span><span class="sxs-lookup"><span data-stu-id="d68d5-139">**endpoint address**</span></span>  
<span data-ttu-id="d68d5-140">标识 Windows Communication Foundation (WCF) 服务终结点的位置的网络地址。</span><span class="sxs-lookup"><span data-stu-id="d68d5-140">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="d68d5-141">对于适配器，终结点地址表示为统一资源标识符 (URI)，包含位置及连接参数的连接。</span><span class="sxs-lookup"><span data-stu-id="d68d5-141">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="d68d5-142">适配器可以使用这些建立与基础的业务线 (LOB) 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="d68d5-142">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="d68d5-143">**企业单一登录系统 (SSO)**</span><span class="sxs-lookup"><span data-stu-id="d68d5-143">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="d68d5-144">由 SSO 数据库、主密钥服务器以及一个或多个企业单一登录 (SSO) 服务器组成。</span><span class="sxs-lookup"><span data-stu-id="d68d5-144">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="d68d5-145">这些服务器在 Windows 凭据和非 Windows 凭据之间建立映射，在 SSO 数据库中查找凭据并管理 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="d68d5-145">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="d68d5-146">SSO 数据库还用作配置存储，以保存适配器的自定义配置数据。</span><span class="sxs-lookup"><span data-stu-id="d68d5-146">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="d68d5-147">**可扩展标记语言**</span><span class="sxs-lookup"><span data-stu-id="d68d5-147">**Extensible Markup Language**</span></span>  
<span data-ttu-id="d68d5-148">标记语言，专门用于描述数据。</span><span class="sxs-lookup"><span data-stu-id="d68d5-148">A markup language designed to describe data.</span></span> <span data-ttu-id="d68d5-149">XML 标记不是预定义。</span><span class="sxs-lookup"><span data-stu-id="d68d5-149">XML tags are not predefined.</span></span>  
  
## <a name="g"></a><span data-ttu-id="d68d5-150">G</span><span class="sxs-lookup"><span data-stu-id="d68d5-150">G</span></span>  
  
<span data-ttu-id="d68d5-151">**全局程序集缓存 (GAC)**</span><span class="sxs-lookup"><span data-stu-id="d68d5-151">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="d68d5-152">计算机范围内的代码缓存，用于存储专为由计算机上的许多应用程序共享而安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="d68d5-152">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="d68d5-153">在全局程序集缓存中部署的应用程序必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="d68d5-153">Applications deployed in the global assembly cache must have a strong name.</span></span>  
  

## <a name="i"></a><span data-ttu-id="d68d5-154">I</span><span class="sxs-lookup"><span data-stu-id="d68d5-154">I</span></span>  
  
<span data-ttu-id="d68d5-155">**入站的操作**</span><span class="sxs-lookup"><span data-stu-id="d68d5-155">**inbound operation**</span></span>  
<span data-ttu-id="d68d5-156">是由在适配器上的业务线 (LOB) 系统调用的操作。</span><span class="sxs-lookup"><span data-stu-id="d68d5-156">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>  
  
## <a name="m"></a><span data-ttu-id="d68d5-157">M</span><span class="sxs-lookup"><span data-stu-id="d68d5-157">M</span></span>  
  
<span data-ttu-id="d68d5-158">**元数据**</span><span class="sxs-lookup"><span data-stu-id="d68d5-158">**metadata**</span></span>  
<span data-ttu-id="d68d5-159">在 WCF 中，是指由服务公开的协定的说明。</span><span class="sxs-lookup"><span data-stu-id="d68d5-159">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="d68d5-160">这被称为服务说明和表示 WSDL 文档中。</span><span class="sxs-lookup"><span data-stu-id="d68d5-160">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="d68d5-161">适配器公开的元数据描述的 （接口） 它可以对基础的 LOB 系统执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d68d5-161">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying LOB system.</span></span>

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="d68d5-162">用于构建 BizTalk 适配器使用开放标准，基于 Web 服务规范。</span><span class="sxs-lookup"><span data-stu-id="d68d5-162">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="o"></a><span data-ttu-id="d68d5-163">O</span><span class="sxs-lookup"><span data-stu-id="d68d5-163">O</span></span>  
  
<span data-ttu-id="d68d5-164">**单向**</span><span class="sxs-lookup"><span data-stu-id="d68d5-164">**one-way**</span></span>  
<span data-ttu-id="d68d5-165">发件人发送一条消息，但没有响应的消息交换模式 (MEP) 返回的接收方。</span><span class="sxs-lookup"><span data-stu-id="d68d5-165">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="d68d5-166">在 BizTalk Server 中 Mep 统称为通信模式。</span><span class="sxs-lookup"><span data-stu-id="d68d5-166">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="d68d5-167">**出站操作**</span><span class="sxs-lookup"><span data-stu-id="d68d5-167">**outbound operation**</span></span>  
<span data-ttu-id="d68d5-168">由业务线系统 (LOB) 上的适配器调用操作。</span><span class="sxs-lookup"><span data-stu-id="d68d5-168">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>
  
<span data-ttu-id="d68d5-169">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="d68d5-169">**output.cs**</span></span>  
<span data-ttu-id="d68d5-170">ServiceModel 元数据实用工具 (svcutil.exe) 创建的默认输出文件。</span><span class="sxs-lookup"><span data-stu-id="d68d5-170">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span>  
  
## <a name="p"></a><span data-ttu-id="d68d5-171">P</span><span class="sxs-lookup"><span data-stu-id="d68d5-171">P</span></span>  
  
<span data-ttu-id="d68d5-172">**轮询**</span><span class="sxs-lookup"><span data-stu-id="d68d5-172">**polling**</span></span>  
<span data-ttu-id="d68d5-173">设备驱动程序使用来了解从多个设备它们是否包含数据传输一种技术。</span><span class="sxs-lookup"><span data-stu-id="d68d5-173">A technique that device drivers use to find out from multiple devices whether they contain data to transmit.</span></span> <span data-ttu-id="d68d5-174">设备是轮询一次一个地。</span><span class="sxs-lookup"><span data-stu-id="d68d5-174">The devices are polled one at a time.</span></span>

<span data-ttu-id="d68d5-175">**代理**</span><span class="sxs-lookup"><span data-stu-id="d68d5-175">**proxy**</span></span>  
<span data-ttu-id="d68d5-176">在 WCF 中，引用托管代码实现的对象，由服务公开的服务协定。</span><span class="sxs-lookup"><span data-stu-id="d68d5-176">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="d68d5-177">WCF 服务模型取决于此类代理使用。</span><span class="sxs-lookup"><span data-stu-id="d68d5-177">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="d68d5-178">在 WCF 服务模型中，服务协定表示为.NET 接口。</span><span class="sxs-lookup"><span data-stu-id="d68d5-178">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>
  
## <a name="r"></a><span data-ttu-id="d68d5-179">R</span><span class="sxs-lookup"><span data-stu-id="d68d5-179">R</span></span>  
  
<span data-ttu-id="d68d5-180">**请求-响应**</span><span class="sxs-lookup"><span data-stu-id="d68d5-180">**request-response**</span></span>  
<span data-ttu-id="d68d5-181">消息交换模式 (MEP) 发件人发送请求消息，并需要从接收方的响应消息。</span><span class="sxs-lookup"><span data-stu-id="d68d5-181">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="d68d5-182">在 BizTalk Server 中 Mep 统称为通信模式。</span><span class="sxs-lookup"><span data-stu-id="d68d5-182">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="d68d5-183">具体取决于消息传送技术和请求消息 （入站或出站） 的方向，此模式也称为请求-答复或请求作出响应。</span><span class="sxs-lookup"><span data-stu-id="d68d5-183">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="d68d5-184">**运行时体验**</span><span class="sxs-lookup"><span data-stu-id="d68d5-184">**run-time experience**</span></span>  
<span data-ttu-id="d68d5-185">过程和在运行时期间或部署解决方案; 由开发人员执行的操作例如，从 BizTalk Server 管理控制台中创建物理端口绑定。</span><span class="sxs-lookup"><span data-stu-id="d68d5-185">Procedures and operations performed by a developer during run time or when deploying a solution; for example, creating a physical port binding from the BizTalk Server Administration console.</span></span>  
  
## <a name="s"></a><span data-ttu-id="d68d5-186">S</span><span class="sxs-lookup"><span data-stu-id="d68d5-186">S</span></span>  
  
<span data-ttu-id="d68d5-187">**架构**</span><span class="sxs-lookup"><span data-stu-id="d68d5-187">**schema**</span></span>  
<span data-ttu-id="d68d5-188">消息的结构。</span><span class="sxs-lookup"><span data-stu-id="d68d5-188">The structure for a message.</span></span> <span data-ttu-id="d68d5-189">架构可以包含多个子。</span><span class="sxs-lookup"><span data-stu-id="d68d5-189">A schema can contain multiple subschema.</span></span>

<span data-ttu-id="d68d5-190">**ServiceModel 元数据实用工具 (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="d68d5-190">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="d68d5-191">WCF 包含一个命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="d68d5-191">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="d68d5-192">它用于从适配器之类的 WCF 服务公开的服务说明 （元数据） 创建服务模型代理代码。</span><span class="sxs-lookup"><span data-stu-id="d68d5-192">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="d68d5-193">对于出站操作，该工具可创建 WCF 客户端类和帮助程序代码;对于入站操作，该工具创建 WCF 服务协定和帮助程序代码。</span><span class="sxs-lookup"><span data-stu-id="d68d5-193">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="d68d5-194">**SOAP （简单对象访问协议）**</span><span class="sxs-lookup"><span data-stu-id="d68d5-194">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="d68d5-195">用于交换结构化和分散和分布式环境中的类型信息的简单、 基于 XML 的协议。</span><span class="sxs-lookup"><span data-stu-id="d68d5-195">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="d68d5-196">WCF 基于的客户端和服务调用操作并返回结果之间的 SOAP 消息交换。</span><span class="sxs-lookup"><span data-stu-id="d68d5-196">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="d68d5-197">**SOAP 消息**</span><span class="sxs-lookup"><span data-stu-id="d68d5-197">**SOAP message**</span></span>  
<span data-ttu-id="d68d5-198">格式正确的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="d68d5-198">A well-formed XML document.</span></span> <span data-ttu-id="d68d5-199">此消息应使用 SOAP 信封和 SOAP 编码命名空间，并且应包含可选的 XML 声明，声明后跟 SOAP 信封（根元素）。此消息由可选的 SOAP 标头和 SOAP 消息正文组成。</span><span class="sxs-lookup"><span data-stu-id="d68d5-199">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="d68d5-200">**SQL Server Integration Services (SSIS)** 用于导入、 导出，并将来自不同数据源的数据转换组件。</span><span class="sxs-lookup"><span data-stu-id="d68d5-200">**SQL Server Integration Services (SSIS)** A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="d68d5-201">以前称为数据转换服务 (DTS)。</span><span class="sxs-lookup"><span data-stu-id="d68d5-201">Previously called data transformation service (DTS).</span></span>

<span data-ttu-id="d68d5-202">**强类型化数据**</span><span class="sxs-lookup"><span data-stu-id="d68d5-202">**strongly-typed data**</span></span>  
<span data-ttu-id="d68d5-203">数据集或绑定到的基础对象类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="d68d5-203">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="d68d5-204">强类型 XML 数据集中的每一行被组成类型化，名为基础的对象类型的字段对应的元素。</span><span class="sxs-lookup"><span data-stu-id="d68d5-204">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span>
  
## <a name="w"></a><span data-ttu-id="d68d5-205">W</span><span class="sxs-lookup"><span data-stu-id="d68d5-205">W</span></span>  
  
<span data-ttu-id="d68d5-206">**WCF 通道模型**</span><span class="sxs-lookup"><span data-stu-id="d68d5-206">**WCF channel model**</span></span>  
<span data-ttu-id="d68d5-207">一个依赖于多个接口和其他类型的编程模型。</span><span class="sxs-lookup"><span data-stu-id="d68d5-207">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="d68d5-208">通道提供用于发送和接收消息的低级编程模型。</span><span class="sxs-lookup"><span data-stu-id="d68d5-208">Channels provide a low-level programming model for sending and receiving messages.</span></span>

<span data-ttu-id="d68d5-209">**WCF 客户端**</span><span class="sxs-lookup"><span data-stu-id="d68d5-209">**WCF client**</span></span>  
<span data-ttu-id="d68d5-210">一个客户端应用程序构造，用于将服务操作作为方法公开。</span><span class="sxs-lookup"><span data-stu-id="d68d5-210">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="d68d5-211">可用于添加适配器服务引用 Visual Studio 插件或 ServiceModel 元数据实用工具从适配器公开的元数据生成 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="d68d5-211">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="d68d5-212">**WCF 服务协定**</span><span class="sxs-lookup"><span data-stu-id="d68d5-212">**WCF service contract**</span></span>  
<span data-ttu-id="d68d5-213">托管代码表示形式的服务协定。</span><span class="sxs-lookup"><span data-stu-id="d68d5-213">A managed-code representation of the service contract.</span></span> <span data-ttu-id="d68d5-214">它之所以表示为接口中的类和方法属性来定义服务、 操作、 消息和用于与服务通信的数据协定。</span><span class="sxs-lookup"><span data-stu-id="d68d5-214">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="d68d5-215">你可以使用 ServiceModel 元数据实用工具工具或添加适配器服务引用 Visual Studio 插件从适配器公开的元数据生成 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="d68d5-215">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="d68d5-216">实现 WCF 服务约定以接收从 LOB 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="d68d5-216">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="d68d5-217">**WCF 服务模型**</span><span class="sxs-lookup"><span data-stu-id="d68d5-217">**WCF service model**</span></span>  
<span data-ttu-id="d68d5-218">在其中一项服务会表示为托管的代码对象的一种 WCF 编程模型。</span><span class="sxs-lookup"><span data-stu-id="d68d5-218">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="d68d5-219">由服务公开的操作表示为具有强类型数据的方法。</span><span class="sxs-lookup"><span data-stu-id="d68d5-219">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="d68d5-220">**弱类型化数据**</span><span class="sxs-lookup"><span data-stu-id="d68d5-220">**weakly-typed data**</span></span>  
<span data-ttu-id="d68d5-221">数据集或未绑定到的基础对象类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="d68d5-221">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="d68d5-222">弱类型 XML 数据集中的每个行组成的一般顺序特性描述的名称和每个元素的类型的列集合。</span><span class="sxs-lookup"><span data-stu-id="d68d5-222">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="d68d5-223">**Web 服务**</span><span class="sxs-lookup"><span data-stu-id="d68d5-223">**Web services**</span></span>  
<span data-ttu-id="d68d5-224">提供数据和向其他应用程序的服务的应用程序逻辑的单位。</span><span class="sxs-lookup"><span data-stu-id="d68d5-224">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="d68d5-225">应用程序使用标准 Web 协议和数据格式（如 HTTP、XML 和 SOAP）访问 XML Web Services，并与每个 XML Web Services 如何实现无关。</span><span class="sxs-lookup"><span data-stu-id="d68d5-225">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="d68d5-226">XML Web Services 结合了基于组件的开发和 Web 两者的优点，同时还是 Microsoft .NET 编程模型的基础。</span><span class="sxs-lookup"><span data-stu-id="d68d5-226">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="d68d5-227">**Web 服务描述语言 (WSDL)**</span><span class="sxs-lookup"><span data-stu-id="d68d5-227">**Web Services Description Language (WSDL)**</span></span>  
<span data-ttu-id="d68d5-228">一种基于 XML 的语言，它描述作为一组操作的终结点的服务，在消息上。</span><span class="sxs-lookup"><span data-stu-id="d68d5-228">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="d68d5-229">WSDL 文档描述服务协定、 操作协定、 消息协定和数据协定，客户端必须使用以便与该服务。</span><span class="sxs-lookup"><span data-stu-id="d68d5-229">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="d68d5-230">**Windows Communication Foundation (WCF)** Microsoft 面向服务的通信基础结构。</span><span class="sxs-lookup"><span data-stu-id="d68d5-230">**Windows Communication Foundation (WCF)** A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="d68d5-231">该框架本质上是提供客户端与服务编程模型和编程模型的消息交换更精细的控制通道。</span><span class="sxs-lookup"><span data-stu-id="d68d5-231">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>
  
## <a name="x"></a><span data-ttu-id="d68d5-232">X</span><span class="sxs-lookup"><span data-stu-id="d68d5-232">X</span></span>  
  
<span data-ttu-id="d68d5-233">**XML 架构定义语言 (XSD)** 架构语言。</span><span class="sxs-lookup"><span data-stu-id="d68d5-233">**XML Schema definition language (XSD)** A schema language.</span></span> <span data-ttu-id="d68d5-234">XML 架构定义元素、 属性和数据类型符合万维网联合会 (W3C) XML 架构第 1 部分： 结构建议的 XML 架构定义语言。</span><span class="sxs-lookup"><span data-stu-id="d68d5-234">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="d68d5-235">“W3C XML 架构第 2 部分：数据类型建议”是针对定义 XML 架构中使用的数据类型的建议。</span><span class="sxs-lookup"><span data-stu-id="d68d5-235">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="d68d5-236">使用 XML 架构定义语言可以定义 XML 消息的结构和数据类型。</span><span class="sxs-lookup"><span data-stu-id="d68d5-236">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>