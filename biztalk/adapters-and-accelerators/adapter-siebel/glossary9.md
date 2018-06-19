---
title: 在 BizTalk Siebel 电子商务应用程序的 BizTalk Adapter 术语表 |Microsoft 文档
description: 常见术语和定义使用 BizTalk 适配器包 (BAP) 中的 Siebel 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 75c74760-53b6-45c3-bacc-bb7ab4fb5b4b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 54cb0b66bc7cb4b7477160ab2673ec06165ee6c0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22224677"
---
# <a name="terms-and-definitions-for-the-siebel-adapter"></a><span data-ttu-id="8204d-103">术语和定义为 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="8204d-103">Terms and definitions for the Siebel adapter</span></span>
<span data-ttu-id="8204d-104">中使用以下术语和定义[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8204d-104">The following terms and definitions are used in [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)].</span></span>  
  
 
## <a name="a"></a><span data-ttu-id="8204d-105">仅当辅助副本配置为使用手动故障转移模式，并且至少一个辅助副本当前与主要副本同步时，</span><span class="sxs-lookup"><span data-stu-id="8204d-105">A</span></span>  

<span data-ttu-id="8204d-106">**适配器**</span><span class="sxs-lookup"><span data-stu-id="8204d-106">**adapter**</span></span>  
<span data-ttu-id="8204d-107">应用程序 （例如，业务线系统） 之间的基于 WCF 的组件，可帮助 exchange 消息和 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="8204d-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="8204d-108">适配器由执行接收操作和发送操作的设计时组件和运行时组件组成。</span><span class="sxs-lookup"><span data-stu-id="8204d-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="8204d-109">**适配器客户端**</span><span class="sxs-lookup"><span data-stu-id="8204d-109">**adapter client**</span></span>  
<span data-ttu-id="8204d-110">应用程序与通过适配器的业务线 (LOB) 系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="8204d-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>  

  
## <a name="b"></a><span data-ttu-id="8204d-111">B</span><span class="sxs-lookup"><span data-stu-id="8204d-111">B</span></span>
  
<span data-ttu-id="8204d-112">**绑定**</span><span class="sxs-lookup"><span data-stu-id="8204d-112">**binding**</span></span>  
<span data-ttu-id="8204d-113">链接软件组件和层的过程。</span><span class="sxs-lookup"><span data-stu-id="8204d-113">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="8204d-114">安装网络组件时，会建立组件间的绑定关系和依存关系。</span><span class="sxs-lookup"><span data-stu-id="8204d-114">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="8204d-115">绑定可使组件之间互相通信。</span><span class="sxs-lookup"><span data-stu-id="8204d-115">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="8204d-116">在 BizTalk Server 中，指的是与业务流程适配器无关的终结点（端口或角色链接）和特定于物理适配器的终结点（发送/接收端口或参与方）之间已建立的映射。</span><span class="sxs-lookup"><span data-stu-id="8204d-116">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="8204d-117">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="8204d-117">**BizTalk Server**</span></span>  
<span data-ttu-id="8204d-118">连接不同的软件。</span><span class="sxs-lookup"><span data-stu-id="8204d-118">Connects diverse software.</span></span> <span data-ttu-id="8204d-119">BizTalk Server，可创建和修改过程逻辑，它使用该软件。</span><span class="sxs-lookup"><span data-stu-id="8204d-119">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="8204d-120">使用 BizTalk Server，信息工作者还可以监视正在运行的进程、与贸易合作伙伴进行交互，以及执行其他面向企业的任务。</span><span class="sxs-lookup"><span data-stu-id="8204d-120">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>

 
## <a name="c"></a><span data-ttu-id="8204d-121">C</span><span class="sxs-lookup"><span data-stu-id="8204d-121">C</span></span>
  
<span data-ttu-id="8204d-122">**通道**</span><span class="sxs-lookup"><span data-stu-id="8204d-122">**channel**</span></span>  
<span data-ttu-id="8204d-123">绑定元素的具体实现。</span><span class="sxs-lookup"><span data-stu-id="8204d-123">A concrete implementation of a binding element.</span></span> <span data-ttu-id="8204d-124">绑定表示配置，而通道是与该配置相关联的实现。</span><span class="sxs-lookup"><span data-stu-id="8204d-124">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="8204d-125">因此，没有与每个绑定元素关联的通道。</span><span class="sxs-lookup"><span data-stu-id="8204d-125">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="8204d-126">通道堆叠在一起以形成绑定的具体实现： 通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="8204d-126">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="8204d-127">**连接 URI**</span><span class="sxs-lookup"><span data-stu-id="8204d-127">**connection URI**</span></span>  
<span data-ttu-id="8204d-128">一个字符串，标识分布式环境中的资源。</span><span class="sxs-lookup"><span data-stu-id="8204d-128">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="8204d-129">适配器使用的连接统一资源标识符 (URI)，包含与 LOB 系统建立连接所需的信息。</span><span class="sxs-lookup"><span data-stu-id="8204d-129">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="8204d-130">**协定**</span><span class="sxs-lookup"><span data-stu-id="8204d-130">**contract**</span></span>  
<span data-ttu-id="8204d-131">指定的集合和访问服务提供的操作所必需的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="8204d-131">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>  
  
## <a name="d"></a><span data-ttu-id="8204d-132">D</span><span class="sxs-lookup"><span data-stu-id="8204d-132">D</span></span>
  
<span data-ttu-id="8204d-133">**设计时体验**</span><span class="sxs-lookup"><span data-stu-id="8204d-133">**design-time experience**</span></span>  
<span data-ttu-id="8204d-134">过程和开发人员在设计时; 期间执行的操作例如，使用使用适配器服务 BizTalk 项目外接程序检索消息架构。</span><span class="sxs-lookup"><span data-stu-id="8204d-134">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span> 

 
## <a name="e"></a><span data-ttu-id="8204d-135">E</span><span class="sxs-lookup"><span data-stu-id="8204d-135">E</span></span> 
  
<span data-ttu-id="8204d-136">**终结点地址**</span><span class="sxs-lookup"><span data-stu-id="8204d-136">**endpoint address**</span></span>  
<span data-ttu-id="8204d-137">标识 Windows Communication Foundation (WCF) 服务终结点的位置的网络地址。</span><span class="sxs-lookup"><span data-stu-id="8204d-137">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="8204d-138">对于适配器，终结点地址表示为统一资源标识符 (URI)，包含位置及连接参数的连接。</span><span class="sxs-lookup"><span data-stu-id="8204d-138">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="8204d-139">适配器可以使用这些建立与基础的业务线 (LOB) 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="8204d-139">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="8204d-140">**企业单一登录系统 (SSO)**</span><span class="sxs-lookup"><span data-stu-id="8204d-140">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="8204d-141">由 SSO 数据库、主密钥服务器以及一个或多个企业单一登录 (SSO) 服务器组成。</span><span class="sxs-lookup"><span data-stu-id="8204d-141">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="8204d-142">这些服务器在 Windows 凭据和非 Windows 凭据之间建立映射，在 SSO 数据库中查找凭据并管理 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="8204d-142">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="8204d-143">SSO 数据库还用作配置存储，以保存适配器的自定义配置数据。</span><span class="sxs-lookup"><span data-stu-id="8204d-143">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="8204d-144">**可扩展标记语言 (XML)**</span><span class="sxs-lookup"><span data-stu-id="8204d-144">**Extensible Markup Language (XML)**</span></span>  
<span data-ttu-id="8204d-145">标记语言，专门用于描述数据。</span><span class="sxs-lookup"><span data-stu-id="8204d-145">A markup language designed to describe data.</span></span> <span data-ttu-id="8204d-146">XML 标记不是预定义。</span><span class="sxs-lookup"><span data-stu-id="8204d-146">XML tags are not predefined.</span></span>  
 
 
## <a name="g"></a><span data-ttu-id="8204d-147">G</span><span class="sxs-lookup"><span data-stu-id="8204d-147">G</span></span>
  
<span data-ttu-id="8204d-148">**全局程序集缓存 (GAC)**</span><span class="sxs-lookup"><span data-stu-id="8204d-148">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="8204d-149">计算机范围内的代码缓存，用于存储专为由计算机上的许多应用程序共享而安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="8204d-149">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="8204d-150">在全局程序集缓存中部署的应用程序必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="8204d-150">Applications deployed in the global assembly cache must have a strong name.</span></span>
  
 
## <a name="i"></a><span data-ttu-id="8204d-151">I</span><span class="sxs-lookup"><span data-stu-id="8204d-151">I</span></span>
  
<span data-ttu-id="8204d-152">**入站的操作**</span><span class="sxs-lookup"><span data-stu-id="8204d-152">**inbound operation**</span></span>  
<span data-ttu-id="8204d-153">是由在适配器上的业务线 (LOB) 系统调用的操作。</span><span class="sxs-lookup"><span data-stu-id="8204d-153">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>  
  
## <a name="m"></a><span data-ttu-id="8204d-154">M</span><span class="sxs-lookup"><span data-stu-id="8204d-154">M</span></span>
  
<span data-ttu-id="8204d-155">**元数据**</span><span class="sxs-lookup"><span data-stu-id="8204d-155">**metadata**</span></span>  
<span data-ttu-id="8204d-156">在 WCF 中，是指由服务公开的协定的说明。</span><span class="sxs-lookup"><span data-stu-id="8204d-156">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="8204d-157">这被称为服务说明和表示 WSDL 文档中。</span><span class="sxs-lookup"><span data-stu-id="8204d-157">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="8204d-158">适配器公开的元数据描述的 （接口） 它可以对基础的 LOB 系统执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8204d-158">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying LOB system.</span></span> <span data-ttu-id="8204d-159">诸如位置、时间、消息大小等信息和/或异常信息。</span><span class="sxs-lookup"><span data-stu-id="8204d-159">Information, such as location, time, message size, and/or exception information.</span></span>


**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="8204d-160">用于构建 BizTalk 适配器使用开放标准，基于 Web 服务规范。</span><span class="sxs-lookup"><span data-stu-id="8204d-160">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="o"></a><span data-ttu-id="8204d-161">O</span><span class="sxs-lookup"><span data-stu-id="8204d-161">O</span></span>
  
<span data-ttu-id="8204d-162">**单向**</span><span class="sxs-lookup"><span data-stu-id="8204d-162">**one-way**</span></span>  
<span data-ttu-id="8204d-163">发件人发送一条消息，但没有响应的消息交换模式 (MEP) 返回的接收方。</span><span class="sxs-lookup"><span data-stu-id="8204d-163">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="8204d-164">在 BizTalk Server 中 Mep 统称为通信模式。</span><span class="sxs-lookup"><span data-stu-id="8204d-164">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="8204d-165">**出站操作**</span><span class="sxs-lookup"><span data-stu-id="8204d-165">**outbound operation**</span></span>  
<span data-ttu-id="8204d-166">由业务线系统 (LOB) 上的适配器调用操作。</span><span class="sxs-lookup"><span data-stu-id="8204d-166">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>

<span data-ttu-id="8204d-167">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="8204d-167">**output.cs**</span></span>  
<span data-ttu-id="8204d-168">ServiceModel 元数据实用工具 (svcutil.exe) 创建的默认输出文件。</span><span class="sxs-lookup"><span data-stu-id="8204d-168">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span>  
 
## <a name="p"></a><span data-ttu-id="8204d-169">P</span><span class="sxs-lookup"><span data-stu-id="8204d-169">P</span></span>
  
<span data-ttu-id="8204d-170">**选择列表**</span><span class="sxs-lookup"><span data-stu-id="8204d-170">**picklist**</span></span>  
<span data-ttu-id="8204d-171">其值通常限制为一组值 （像是枚举） 之一的业务组件中的字段。</span><span class="sxs-lookup"><span data-stu-id="8204d-171">A field in a business component whose value is typically constrained to one of a set of values (akin to enumeration).</span></span>

<span data-ttu-id="8204d-172">**代理**</span><span class="sxs-lookup"><span data-stu-id="8204d-172">**proxy**</span></span>  
<span data-ttu-id="8204d-173">在 WCF 中，引用托管代码实现的对象，由服务公开的服务协定。</span><span class="sxs-lookup"><span data-stu-id="8204d-173">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="8204d-174">WCF 服务模型取决于此类代理使用。</span><span class="sxs-lookup"><span data-stu-id="8204d-174">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="8204d-175">在 WCF 服务模型中，服务协定表示为.NET 接口。</span><span class="sxs-lookup"><span data-stu-id="8204d-175">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>
  
## <a name="r"></a><span data-ttu-id="8204d-176">R</span><span class="sxs-lookup"><span data-stu-id="8204d-176">R</span></span>
  
<span data-ttu-id="8204d-177">**请求-响应**</span><span class="sxs-lookup"><span data-stu-id="8204d-177">**request-response**</span></span>  
<span data-ttu-id="8204d-178">消息交换模式 (MEP) 发件人发送请求消息，并需要从接收方的响应消息。</span><span class="sxs-lookup"><span data-stu-id="8204d-178">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="8204d-179">在 BizTalk Server 中 Mep 统称为通信模式。</span><span class="sxs-lookup"><span data-stu-id="8204d-179">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="8204d-180">具体取决于消息传送技术和请求消息 （入站或出站） 的方向，此模式也称为请求-答复或请求作出响应。</span><span class="sxs-lookup"><span data-stu-id="8204d-180">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="8204d-181">**运行时体验**</span><span class="sxs-lookup"><span data-stu-id="8204d-181">**run-time experience**</span></span>  
<span data-ttu-id="8204d-182">过程和在运行时期间或部署解决方案; 由开发人员执行的操作例如，从 BizTalk Server 管理控制台中创建物理端口绑定。</span><span class="sxs-lookup"><span data-stu-id="8204d-182">Procedures and operations performed by a developer during run time or when deploying a solution; for example, creating a physical port binding from the BizTalk Server Administration console.</span></span>  


## <a name="s"></a><span data-ttu-id="8204d-183">S</span><span class="sxs-lookup"><span data-stu-id="8204d-183">S</span></span>
  
<span data-ttu-id="8204d-184">**架构**</span><span class="sxs-lookup"><span data-stu-id="8204d-184">**schema**</span></span>  
<span data-ttu-id="8204d-185">消息的结构。</span><span class="sxs-lookup"><span data-stu-id="8204d-185">The structure for a message.</span></span> <span data-ttu-id="8204d-186">架构可以包含多个子。</span><span class="sxs-lookup"><span data-stu-id="8204d-186">A schema can contain multiple subschema.</span></span>

<span data-ttu-id="8204d-187">**ServiceModel 元数据实用工具 (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="8204d-187">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="8204d-188">WCF 包含一个命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="8204d-188">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="8204d-189">它用于从适配器之类的 WCF 服务公开的服务说明 （元数据） 创建服务模型代理代码。</span><span class="sxs-lookup"><span data-stu-id="8204d-189">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="8204d-190">对于出站操作，该工具可创建 WCF 客户端类和帮助程序代码;对于入站操作，该工具创建 WCF 服务协定和帮助程序代码。</span><span class="sxs-lookup"><span data-stu-id="8204d-190">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="8204d-191">**Siebel 在业务组件**</span><span class="sxs-lookup"><span data-stu-id="8204d-191">**Siebel business component**</span></span>  
<span data-ttu-id="8204d-192">关联逻辑上相关列从一个或多个表到单个结构。</span><span class="sxs-lookup"><span data-stu-id="8204d-192">Associates logically related columns from one or more tables into a single structure.</span></span>

<span data-ttu-id="8204d-193">**Siebel 业务对象**</span><span class="sxs-lookup"><span data-stu-id="8204d-193">**Siebel business object**</span></span>  
<span data-ttu-id="8204d-194">表示业务组件的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="8204d-194">Represents a logical grouping of business components.</span></span>
  
<span data-ttu-id="8204d-195">**Siebel 业务服务**</span><span class="sxs-lookup"><span data-stu-id="8204d-195">**Siebel business service**</span></span>  
<span data-ttu-id="8204d-196">业务服务方法或可以在 Siebel 系统中直接调用的函数的集合。</span><span class="sxs-lookup"><span data-stu-id="8204d-196">A collection of business service methods or functions that can be directly invoked in the Siebel system.</span></span>
  
<span data-ttu-id="8204d-197">**Siebel COM 数据控件库**</span><span class="sxs-lookup"><span data-stu-id="8204d-197">**Siebel COM Data Control library**</span></span>  
<span data-ttu-id="8204d-198">包含启用外部客户端，如在 Siebel 适配器连接并与 Siebel 应用程序对象管理器通信 Siebel 服务器上的接口。</span><span class="sxs-lookup"><span data-stu-id="8204d-198">Contains interfaces that enable an external client like the Siebel adapter to connect and communicate with a Siebel Application Object Manager on a Siebel server.</span></span>

<span data-ttu-id="8204d-199">**SOAP （简单对象访问协议）**</span><span class="sxs-lookup"><span data-stu-id="8204d-199">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="8204d-200">用于交换结构化和分散和分布式环境中的类型信息的简单、 基于 XML 的协议。</span><span class="sxs-lookup"><span data-stu-id="8204d-200">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="8204d-201">WCF 基于的客户端和服务调用操作并返回结果之间的 SOAP 消息交换。</span><span class="sxs-lookup"><span data-stu-id="8204d-201">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="8204d-202">**SOAP 消息**</span><span class="sxs-lookup"><span data-stu-id="8204d-202">**SOAP message**</span></span>  
<span data-ttu-id="8204d-203">格式正确的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="8204d-203">A well-formed XML document.</span></span> <span data-ttu-id="8204d-204">此消息应使用 SOAP 信封和 SOAP 编码命名空间，并且应包含可选的 XML 声明，声明后跟 SOAP 信封（根元素）。此消息由可选的 SOAP 标头和 SOAP 消息正文组成。</span><span class="sxs-lookup"><span data-stu-id="8204d-204">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="8204d-205">**SQL Server Integration Services (SSIS)**</span><span class="sxs-lookup"><span data-stu-id="8204d-205">**SQL Server Integration Services (SSIS)**</span></span>  
<span data-ttu-id="8204d-206">用于导入、 导出，并将来自不同数据源的数据转换组件。</span><span class="sxs-lookup"><span data-stu-id="8204d-206">A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="8204d-207">以前称为数据转换服务 (DTS)。</span><span class="sxs-lookup"><span data-stu-id="8204d-207">Previously called data transformation service (DTS).</span></span>

<span data-ttu-id="8204d-208">**强类型化数据**</span><span class="sxs-lookup"><span data-stu-id="8204d-208">**strongly-typed data**</span></span>  
<span data-ttu-id="8204d-209">数据集或绑定到的基础对象类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="8204d-209">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="8204d-210">强类型 XML 数据集中的每一行被组成类型化，名为基础的对象类型的字段对应的元素。</span><span class="sxs-lookup"><span data-stu-id="8204d-210">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span>  
  
## <a name="w"></a><span data-ttu-id="8204d-211">W</span><span class="sxs-lookup"><span data-stu-id="8204d-211">W</span></span>
  
<span data-ttu-id="8204d-212">**WCF 通道模型**</span><span class="sxs-lookup"><span data-stu-id="8204d-212">**WCF channel model**</span></span>  
<span data-ttu-id="8204d-213">一个依赖于多个接口和其他类型的编程模型。</span><span class="sxs-lookup"><span data-stu-id="8204d-213">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="8204d-214">通道提供用于发送和接收消息的低级编程模型。</span><span class="sxs-lookup"><span data-stu-id="8204d-214">Channels provide a low-level programming model for sending and receiving messages.</span></span>
  
<span data-ttu-id="8204d-215">**WCF 客户端**</span><span class="sxs-lookup"><span data-stu-id="8204d-215">**WCF client**</span></span>  
<span data-ttu-id="8204d-216">一个客户端应用程序构造，用于将服务操作作为方法公开。</span><span class="sxs-lookup"><span data-stu-id="8204d-216">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="8204d-217">可用于添加适配器服务引用 Visual Studio 插件或 ServiceModel 元数据实用工具从适配器公开的元数据生成 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="8204d-217">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="8204d-218">**WCF 服务协定**</span><span class="sxs-lookup"><span data-stu-id="8204d-218">**WCF service contract**</span></span>  
<span data-ttu-id="8204d-219">托管代码表示形式的服务协定。</span><span class="sxs-lookup"><span data-stu-id="8204d-219">A managed-code representation of the service contract.</span></span> <span data-ttu-id="8204d-220">它之所以表示为接口中的类和方法属性来定义服务、 操作、 消息和用于与服务通信的数据协定。</span><span class="sxs-lookup"><span data-stu-id="8204d-220">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="8204d-221">你可以使用 ServiceModel 元数据实用工具工具或添加适配器服务引用 Visual Studio 插件从适配器公开的元数据生成 WCF 服务协定。</span><span class="sxs-lookup"><span data-stu-id="8204d-221">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="8204d-222">实现 WCF 服务约定以接收从 LOB 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="8204d-222">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="8204d-223">**WCF 服务模型**</span><span class="sxs-lookup"><span data-stu-id="8204d-223">**WCF service model**</span></span>  
<span data-ttu-id="8204d-224">在其中一项服务会表示为托管的代码对象的一种 WCF 编程模型。</span><span class="sxs-lookup"><span data-stu-id="8204d-224">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="8204d-225">由服务公开的操作表示为具有强类型数据的方法。</span><span class="sxs-lookup"><span data-stu-id="8204d-225">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="8204d-226">**弱类型化数据**</span><span class="sxs-lookup"><span data-stu-id="8204d-226">**weakly-typed data**</span></span>  
<span data-ttu-id="8204d-227">数据集或未绑定到的基础对象类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="8204d-227">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="8204d-228">弱类型 XML 数据集中的每个行组成的一般顺序特性描述的名称和每个元素的类型的列集合。</span><span class="sxs-lookup"><span data-stu-id="8204d-228">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="8204d-229">**web 服务**</span><span class="sxs-lookup"><span data-stu-id="8204d-229">**web services**</span></span>  
<span data-ttu-id="8204d-230">提供数据和向其他应用程序的服务的应用程序逻辑的单位。</span><span class="sxs-lookup"><span data-stu-id="8204d-230">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="8204d-231">应用程序使用标准 Web 协议和数据格式（如 HTTP、XML 和 SOAP）访问 XML Web Services，并与每个 XML Web Services 如何实现无关。</span><span class="sxs-lookup"><span data-stu-id="8204d-231">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="8204d-232">XML Web Services 结合了基于组件的开发和 Web 两者的优点，同时还是 Microsoft .NET 编程模型的基础。</span><span class="sxs-lookup"><span data-stu-id="8204d-232">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="8204d-233">**Web 服务描述语言**</span><span class="sxs-lookup"><span data-stu-id="8204d-233">**Web Services Description Language**</span></span>  
<span data-ttu-id="8204d-234">一种基于 XML 的语言，它描述作为一组操作的终结点的服务，在消息上。</span><span class="sxs-lookup"><span data-stu-id="8204d-234">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="8204d-235">WSDL 文档描述服务协定、 操作协定、 消息协定和数据协定，客户端必须使用以便与该服务。</span><span class="sxs-lookup"><span data-stu-id="8204d-235">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="8204d-236">**Windows Communication Foundation (WCF)**</span><span class="sxs-lookup"><span data-stu-id="8204d-236">**Windows Communication Foundation (WCF)**</span></span>  
<span data-ttu-id="8204d-237">Microsoft 面向服务的通信基础结构。</span><span class="sxs-lookup"><span data-stu-id="8204d-237">A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="8204d-238">该框架本质上是提供客户端与服务编程模型和编程模型的消息交换更精细的控制通道。</span><span class="sxs-lookup"><span data-stu-id="8204d-238">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>

<span data-ttu-id="8204d-239">**WS 元数据交换 (MEX) 终结点**</span><span class="sxs-lookup"><span data-stu-id="8204d-239">**WS-Metadata Exchange (MEX) endpoint**</span></span>  
<span data-ttu-id="8204d-240">实现 WCF 服务，例如适配器，公开的终结点**IMetadataExchange**接口。</span><span class="sxs-lookup"><span data-stu-id="8204d-240">An endpoint exposed by a WCF service, such as an adapter, that implements the **IMetadataExchange** interface.</span></span> <span data-ttu-id="8204d-241">WS 元数据交换终结点可以用于检索服务说明 (WSDL) 公开的目标系统上的适配器操作。 |</span><span class="sxs-lookup"><span data-stu-id="8204d-241">A WS-Metadata Exchange endpoint can be used to retrieve a service description (WSDL) for operations exposed by an adapter on the target system.|</span></span>  
  
## <a name="x"></a><span data-ttu-id="8204d-242">X</span><span class="sxs-lookup"><span data-stu-id="8204d-242">X</span></span>
<span data-ttu-id="8204d-243">**XML 架构定义语言 (XSD)**</span><span class="sxs-lookup"><span data-stu-id="8204d-243">**XML Schema definition language (XSD)**</span></span>  
<span data-ttu-id="8204d-244">一种架构语言。</span><span class="sxs-lookup"><span data-stu-id="8204d-244">A schema language.</span></span> <span data-ttu-id="8204d-245">XML 架构定义元素、 属性和数据类型符合万维网联合会 (W3C) XML 架构第 1 部分： 结构建议的 XML 架构定义语言。</span><span class="sxs-lookup"><span data-stu-id="8204d-245">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="8204d-246">“W3C XML 架构第 2 部分：数据类型建议”是针对定义 XML 架构中使用的数据类型的建议。</span><span class="sxs-lookup"><span data-stu-id="8204d-246">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="8204d-247">使用 XML 架构定义语言可以定义 XML 消息的结构和数据类型。</span><span class="sxs-lookup"><span data-stu-id="8204d-247">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>
