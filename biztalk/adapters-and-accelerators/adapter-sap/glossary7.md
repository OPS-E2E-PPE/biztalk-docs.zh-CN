---
title: 为 mySAP 适配器在 BizTalk 中的术语表 |Microsoft Docs
description: 常见术语和定义 mySAP 适配器的 BizTalk 适配器包 (BAP) 中使用
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 87db79be-e242-40fa-9897-8915e6fb5cae
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 15d2c077fefc89e779e0ea12b121a8c8bcba8024
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373351"
---
# <a name="glossary"></a><span data-ttu-id="42ad1-103">词汇表</span><span class="sxs-lookup"><span data-stu-id="42ad1-103">Glossary</span></span>
<span data-ttu-id="42ad1-104">中使用以下术语和定义[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="42ad1-104">The following terms and definitions are used in [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)].</span></span>  
  
## <a name="a"></a><span data-ttu-id="42ad1-105">A</span><span class="sxs-lookup"><span data-stu-id="42ad1-105">A</span></span>  
  
<span data-ttu-id="42ad1-106">**adapter**</span><span class="sxs-lookup"><span data-stu-id="42ad1-106">**adapter**</span></span>  
<span data-ttu-id="42ad1-107">基于 WCF 的组件，可帮助 exchange 应用程序 （例如，业务线系统） 之间的消息和 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="42ad1-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="42ad1-108">适配器由设计时组件和接收和发送操作的运行时组件组成。</span><span class="sxs-lookup"><span data-stu-id="42ad1-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="42ad1-109">**适配器客户端**</span><span class="sxs-lookup"><span data-stu-id="42ad1-109">**adapter client**</span></span>  
<span data-ttu-id="42ad1-110">应用程序与通过适配器的业务线 (LOB) 系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="42ad1-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>

<span data-ttu-id="42ad1-111">**高级的业务应用程序编程 (ABAP)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-111">**Advanced Business Application Programming (ABAP)**</span></span>  
<span data-ttu-id="42ad1-112">SAP 编程语言。</span><span class="sxs-lookup"><span data-stu-id="42ad1-112">The SAP programming language.</span></span>  
  
## <a name="b"></a><span data-ttu-id="42ad1-113">B</span><span class="sxs-lookup"><span data-stu-id="42ad1-113">B</span></span>  
  
<span data-ttu-id="42ad1-114">**Bapi （业务应用程序编程接口）**</span><span class="sxs-lookup"><span data-stu-id="42ad1-114">**BAPIs (Business Application Programming Interfaces)**</span></span>  
<span data-ttu-id="42ad1-115">公开的 SAP 系统交换业务 SAP 和其他系统之间的标准接口。</span><span class="sxs-lookup"><span data-stu-id="42ad1-115">Standard interfaces exposed by the SAP system to exchange business between SAP and other systems.</span></span> <span data-ttu-id="42ad1-116">Bapi 用于集成不同的组件，通过本地网络或 Internet 上彼此连接。</span><span class="sxs-lookup"><span data-stu-id="42ad1-116">BAPIs are used to integrate different components, which are connected to each other over a local network or on the Internet.</span></span>

<span data-ttu-id="42ad1-117">**binding**</span><span class="sxs-lookup"><span data-stu-id="42ad1-117">**binding**</span></span>  
<span data-ttu-id="42ad1-118">通过哪种软件组件和层链接在一起的过程。</span><span class="sxs-lookup"><span data-stu-id="42ad1-118">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="42ad1-119">安装网络组件时，建立绑定关系和依赖项的组件。</span><span class="sxs-lookup"><span data-stu-id="42ad1-119">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="42ad1-120">绑定允许组件彼此通信。</span><span class="sxs-lookup"><span data-stu-id="42ad1-120">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="42ad1-121">在 BizTalk Server 中，业务流程适配器无关的终结点 （端口或角色链接） 和物理特定于适配器的终结点 （发送/接收端口或参与方） 之间已建立的映射。</span><span class="sxs-lookup"><span data-stu-id="42ad1-121">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="42ad1-122">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="42ad1-122">**BizTalk Server**</span></span>  
<span data-ttu-id="42ad1-123">连接不同的软件。</span><span class="sxs-lookup"><span data-stu-id="42ad1-123">Connects diverse software.</span></span> <span data-ttu-id="42ad1-124">BizTalk Server，可创建和修改使用该软件的流程逻辑。</span><span class="sxs-lookup"><span data-stu-id="42ad1-124">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="42ad1-125">BizTalk Server 还可以监视正在运行的进程、 与贸易合作伙伴进行交互以及执行其他面向企业的任务的信息工作者。</span><span class="sxs-lookup"><span data-stu-id="42ad1-125">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>

<span data-ttu-id="42ad1-126">**业务对象**</span><span class="sxs-lookup"><span data-stu-id="42ad1-126">**business object**</span></span>  
<span data-ttu-id="42ad1-127">封装的 SAP 数据和一个面向对象的模型中的进程。</span><span class="sxs-lookup"><span data-stu-id="42ad1-127">Encapsulates SAP data and processes in an object-oriented model.</span></span> <span data-ttu-id="42ad1-128">外部客户端调用的方法调用的业务对象应用程序接口 (Bapi) 对对象进行操作 （和其基础 SAP 项目）。</span><span class="sxs-lookup"><span data-stu-id="42ad1-128">External clients invoke methods called business object application interfaces (BAPIs) to act on the object (and its underlying SAP artifacts).</span></span> <span data-ttu-id="42ad1-129">默认情况下，SAP 适配器不公开给使用方应用程序的业务对象。</span><span class="sxs-lookup"><span data-stu-id="42ad1-129">By default, the SAP adapter does not expose business objects to consuming applications.</span></span> <span data-ttu-id="42ad1-130">业务对象只是可用于客户端操作。</span><span class="sxs-lookup"><span data-stu-id="42ad1-130">Business objects are only available for client operations.</span></span>

<span data-ttu-id="42ad1-131">**业务对象储存库 (BOR)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-131">**Business Object Repository (BOR)**</span></span>  
<span data-ttu-id="42ad1-132">包含所有的 SAP 业务对象类型和 SAP 接口类型，以及其组件 （如方法和属性） 驻留在 SAP R/3 系统。</span><span class="sxs-lookup"><span data-stu-id="42ad1-132">Contains all of the SAP business object types and SAP interface types, as well as their components (such as methods and attributes), resident on the SAP R/3 system.</span></span>  
  
## <a name="c"></a><span data-ttu-id="42ad1-133">C</span><span class="sxs-lookup"><span data-stu-id="42ad1-133">C</span></span>  
  
<span data-ttu-id="42ad1-134">**channel**</span><span class="sxs-lookup"><span data-stu-id="42ad1-134">**channel**</span></span>  
<span data-ttu-id="42ad1-135">绑定元素的具体实现。</span><span class="sxs-lookup"><span data-stu-id="42ad1-135">A concrete implementation of a binding element.</span></span> <span data-ttu-id="42ad1-136">绑定表示配置，而通道为与该配置关联的实现。</span><span class="sxs-lookup"><span data-stu-id="42ad1-136">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="42ad1-137">因此，没有与每个绑定元素关联的通道。</span><span class="sxs-lookup"><span data-stu-id="42ad1-137">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="42ad1-138">通道堆叠在一起以形成绑定的具体实现： 通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="42ad1-138">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="42ad1-139">**代码页**实质上是矩阵的码位。</span><span class="sxs-lookup"><span data-stu-id="42ad1-139">**code page** Essentially a matrix of code points.</span></span> <span data-ttu-id="42ad1-140">在数据库中，包括字符，所有数据都存储为字节序列。</span><span class="sxs-lookup"><span data-stu-id="42ad1-140">All data in the database, including characters, is stored as byte sequences.</span></span> <span data-ttu-id="42ad1-141">字符数据的代码页是字节序列和一个字符之间的映射。</span><span class="sxs-lookup"><span data-stu-id="42ad1-141">For character data, a code page is the mapping between a byte sequence and a character.</span></span>

<span data-ttu-id="42ad1-142">**连接 URI**</span><span class="sxs-lookup"><span data-stu-id="42ad1-142">**connection URI**</span></span>  
<span data-ttu-id="42ad1-143">标识分布式环境中的资源的字符串。</span><span class="sxs-lookup"><span data-stu-id="42ad1-143">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="42ad1-144">适配器使用统一资源标识符 (URI)，其中包含与 LOB 系统建立连接所需的信息的连接。</span><span class="sxs-lookup"><span data-stu-id="42ad1-144">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="42ad1-145">**contract**</span><span class="sxs-lookup"><span data-stu-id="42ad1-145">**contract**</span></span>  
<span data-ttu-id="42ad1-146">指定的集合和访问服务提供的操作所需的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="42ad1-146">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>
  
####  <a name="D"></a> <span data-ttu-id="42ad1-147">D</span><span class="sxs-lookup"><span data-stu-id="42ad1-147">D</span></span>  
  
<span data-ttu-id="42ad1-148">**设计时体验**</span><span class="sxs-lookup"><span data-stu-id="42ad1-148">**design-time experience**</span></span>  
<span data-ttu-id="42ad1-149">过程和开发人员在设计时期间执行的操作例如，使用使用适配器服务的 BizTalk 项目添加中检索消息架构。</span><span class="sxs-lookup"><span data-stu-id="42ad1-149">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span>  
  
## <a name="e"></a><span data-ttu-id="42ad1-150">E</span><span class="sxs-lookup"><span data-stu-id="42ad1-150">E</span></span>  
<span data-ttu-id="42ad1-151">**终结点地址**</span><span class="sxs-lookup"><span data-stu-id="42ad1-151">**endpoint address**</span></span>  
<span data-ttu-id="42ad1-152">网络地址标识 Windows Communication Foundation (WCF) 服务终结点的位置。</span><span class="sxs-lookup"><span data-stu-id="42ad1-152">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="42ad1-153">为适配器，终结点地址表示为统一资源标识符 (URI)，其中包含位置和连接参数的连接。</span><span class="sxs-lookup"><span data-stu-id="42ad1-153">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="42ad1-154">适配器可以使用这些来建立与基础业务 (LOB) 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="42ad1-154">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="42ad1-155">**企业单一登录系统 (SSO)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-155">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="42ad1-156">SSO 数据库、 主密钥服务器和一个或多个企业单一登录 (SSO) 服务器。</span><span class="sxs-lookup"><span data-stu-id="42ad1-156">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="42ad1-157">这些服务器的 Windows 和非 Windows 凭据之间进行映射，查找在 SSO 数据库中，凭据用于管理 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="42ad1-157">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="42ad1-158">SSO 数据库还用作为配置存储来保存适配器的自定义配置数据。</span><span class="sxs-lookup"><span data-stu-id="42ad1-158">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="42ad1-159">**可扩展标记语言 (XML)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-159">**Extensible Markup Language (XML)**</span></span>  
<span data-ttu-id="42ad1-160">标记语言，专门用于描述数据。</span><span class="sxs-lookup"><span data-stu-id="42ad1-160">A markup language designed to describe data.</span></span> <span data-ttu-id="42ad1-161">未预定义的 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="42ad1-161">XML tags are not predefined.</span></span>  
  
## <a name="f"></a><span data-ttu-id="42ad1-162">F</span><span class="sxs-lookup"><span data-stu-id="42ad1-162">F</span></span>  
  
<span data-ttu-id="42ad1-163">**函数模块**</span><span class="sxs-lookup"><span data-stu-id="42ad1-163">**function modules**</span></span>  
<span data-ttu-id="42ad1-164">SAP 系统中定义为 ABAP 程序的过程。</span><span class="sxs-lookup"><span data-stu-id="42ad1-164">Procedures defined in an SAP system as ABAP programs.</span></span> <span data-ttu-id="42ad1-165">这些是包含函数模块的逻辑分组的函数组的一部分。</span><span class="sxs-lookup"><span data-stu-id="42ad1-165">These are part of function groups that contain a logical grouping of function modules.</span></span> <span data-ttu-id="42ad1-166">函数模块使 SAP 客户端可以重用和封装全局函数。</span><span class="sxs-lookup"><span data-stu-id="42ad1-166">Function modules enable SAP clients to reuse and encapsulate global functions.</span></span>
  
## <a name="g"></a><span data-ttu-id="42ad1-167">G</span><span class="sxs-lookup"><span data-stu-id="42ad1-167">G</span></span>  
  
<span data-ttu-id="42ad1-168">**全局程序集缓存 (GAC)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-168">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="42ad1-169">计算机范围内的代码缓存，用于存储专为由计算机上的许多应用程序共享而安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="42ad1-169">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="42ad1-170">应用程序部署到全局程序集缓存中必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="42ad1-170">Applications deployed in the global assembly cache must have a strong name.</span></span>
  
## <a name="i"></a><span data-ttu-id="42ad1-171">I</span><span class="sxs-lookup"><span data-stu-id="42ad1-171">I</span></span>  
  
<span data-ttu-id="42ad1-172">**入站的操作**</span><span class="sxs-lookup"><span data-stu-id="42ad1-172">**inbound operation**</span></span>  
<span data-ttu-id="42ad1-173">调用的业务 (LOB) 系统的适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="42ad1-173">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>
  
<span data-ttu-id="42ad1-174">**中间文档 (IDOC)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-174">**intermediate document (IDOC)**</span></span>  
<span data-ttu-id="42ad1-175">用于 R/3、 R/2 和非 SAP 系统之间交换数据的结构化的文档。</span><span class="sxs-lookup"><span data-stu-id="42ad1-175">A structured document that is used to exchange data between R/3, R/2 and non-SAP systems.</span></span>  
  
## <a name="m"></a><span data-ttu-id="42ad1-176">M</span><span class="sxs-lookup"><span data-stu-id="42ad1-176">M</span></span>  
  
<span data-ttu-id="42ad1-177">**metadata**</span><span class="sxs-lookup"><span data-stu-id="42ad1-177">**metadata**</span></span>  
<span data-ttu-id="42ad1-178">在 WCF 中，是指由服务公开的协定说明。</span><span class="sxs-lookup"><span data-stu-id="42ad1-178">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="42ad1-179">这称为服务说明和表示 WSDL 文档中。</span><span class="sxs-lookup"><span data-stu-id="42ad1-179">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="42ad1-180">由适配器公开的元数据描述的 （接口） 它可以在基础业务 (LOB) 系统执行的操作。</span><span class="sxs-lookup"><span data-stu-id="42ad1-180">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying line-of-business (LOB) system.</span></span>

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="42ad1-181">生成 BizTalk 适配器使用基于 Web 服务的开放标准规范。</span><span class="sxs-lookup"><span data-stu-id="42ad1-181">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="o"></a><span data-ttu-id="42ad1-182">O</span><span class="sxs-lookup"><span data-stu-id="42ad1-182">O</span></span>  
  
<span data-ttu-id="42ad1-183">**one-way**</span><span class="sxs-lookup"><span data-stu-id="42ad1-183">**one-way**</span></span>  
<span data-ttu-id="42ad1-184">接收方会返回在其中发送方发送一条消息，但无响应的消息交换模式 (MEP)。</span><span class="sxs-lookup"><span data-stu-id="42ad1-184">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="42ad1-185">在 BizTalk Server 中，Mep 统称为通信模式。</span><span class="sxs-lookup"><span data-stu-id="42ad1-185">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="42ad1-186">**出站操作**</span><span class="sxs-lookup"><span data-stu-id="42ad1-186">**outbound operation**</span></span>  
<span data-ttu-id="42ad1-187">由业务线系统 (LOB) 适配器调用操作。</span><span class="sxs-lookup"><span data-stu-id="42ad1-187">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>
  
<span data-ttu-id="42ad1-188">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="42ad1-188">**output.cs**</span></span>  
<span data-ttu-id="42ad1-189">ServiceModel 元数据实用工具 (svcutil.exe) 工具创建的默认输出文件。</span><span class="sxs-lookup"><span data-stu-id="42ad1-189">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span>  
  
## <a name="p"></a><span data-ttu-id="42ad1-190">P</span><span class="sxs-lookup"><span data-stu-id="42ad1-190">P</span></span>  
  
<span data-ttu-id="42ad1-191">**polling**</span><span class="sxs-lookup"><span data-stu-id="42ad1-191">**polling**</span></span>  
<span data-ttu-id="42ad1-192">设备驱动程序用于找出从多个设备它们是否包含要传输的数据的一种方法。</span><span class="sxs-lookup"><span data-stu-id="42ad1-192">A technique that device drivers use to find out from multiple devices whether they contain data to transmit.</span></span> <span data-ttu-id="42ad1-193">设备是轮询一次一个。</span><span class="sxs-lookup"><span data-stu-id="42ad1-193">The devices are polled one at a time.</span></span>

<span data-ttu-id="42ad1-194">**程序 ID**</span><span class="sxs-lookup"><span data-stu-id="42ad1-194">**program ID**</span></span>  
<span data-ttu-id="42ad1-195">若要在配置网关发送 RFC 的唯一通道。</span><span class="sxs-lookup"><span data-stu-id="42ad1-195">Unique channel to send an RFC in the configured gateway.</span></span> <span data-ttu-id="42ad1-196">程序 ID 或主机名和 SAP 网关服务，提供程序 id 必须匹配 （通过 RfcAccept) 注册参数。</span><span class="sxs-lookup"><span data-stu-id="42ad1-196">The program ID or host name and the SAP gateway service, provided for the program ID, must match the registration parameters (via RfcAccept).</span></span>

<span data-ttu-id="42ad1-197">**proxy**</span><span class="sxs-lookup"><span data-stu-id="42ad1-197">**proxy**</span></span>  
<span data-ttu-id="42ad1-198">在 WCF 中，是指用于实现服务协定由服务公开的托管代码对象。</span><span class="sxs-lookup"><span data-stu-id="42ad1-198">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="42ad1-199">WCF 服务模型基于此类代理使用。</span><span class="sxs-lookup"><span data-stu-id="42ad1-199">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="42ad1-200">在 WCF 服务模型中，服务协定表示为.NET 接口。</span><span class="sxs-lookup"><span data-stu-id="42ad1-200">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>
  
## <a name="r"></a><span data-ttu-id="42ad1-201">R</span><span class="sxs-lookup"><span data-stu-id="42ad1-201">R</span></span>  
  
<span data-ttu-id="42ad1-202">**远程函数调用 (RFC)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-202">**Remote Function Call (RFC)**</span></span>  
<span data-ttu-id="42ad1-203">用于客户端和服务器之间交换数据的过程。</span><span class="sxs-lookup"><span data-stu-id="42ad1-203">A procedure for data exchange between a client and server.</span></span> <span data-ttu-id="42ad1-204">通常，客户端调用服务器程序，并通过 TCP/IP 连接，则服务器返回结果。</span><span class="sxs-lookup"><span data-stu-id="42ad1-204">Typically the client calls a server program, and the server returns the results via a TCP/IP connection.</span></span>
  
<span data-ttu-id="42ad1-205">**request-response**</span><span class="sxs-lookup"><span data-stu-id="42ad1-205">**request-response**</span></span>  
<span data-ttu-id="42ad1-206">消息交换模式 (MEP) 发件人发送请求消息，并期望来自接收方的响应消息。</span><span class="sxs-lookup"><span data-stu-id="42ad1-206">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="42ad1-207">在 BizTalk Server 中，Mep 统称为通信模式。</span><span class="sxs-lookup"><span data-stu-id="42ad1-207">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="42ad1-208">具体取决于消息传送技术和方向 （入站或出站） 的请求消息，此模式也称为请求-答复或要求响应。</span><span class="sxs-lookup"><span data-stu-id="42ad1-208">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="42ad1-209">**运行时体验**</span><span class="sxs-lookup"><span data-stu-id="42ad1-209">**run-time experience**</span></span>  
<span data-ttu-id="42ad1-210">过程和在运行时期间或部署解决方案; 由开发人员执行的操作例如，从 BizTalk Server 管理控制台中创建物理端口绑定。</span><span class="sxs-lookup"><span data-stu-id="42ad1-210">Procedures and operations performed by a developer during run time or when deploying a solution; For example, creating a physical port binding from the BizTalk Server Administration console.</span></span>
  
## <a name="s"></a><span data-ttu-id="42ad1-211">S</span><span class="sxs-lookup"><span data-stu-id="42ad1-211">S</span></span>  
  
<span data-ttu-id="42ad1-212">**schema**</span><span class="sxs-lookup"><span data-stu-id="42ad1-212">**schema**</span></span>  
<span data-ttu-id="42ad1-213">一条消息的结构。</span><span class="sxs-lookup"><span data-stu-id="42ad1-213">The structure for a message.</span></span> <span data-ttu-id="42ad1-214">架构可以包含多个子架构。</span><span class="sxs-lookup"><span data-stu-id="42ad1-214">A schema can contain multiple subschema.</span></span>
  
<span data-ttu-id="42ad1-215">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-215">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="42ad1-216">WCF 附带一个命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="42ad1-216">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="42ad1-217">它用于从由适配器之类的 WCF 服务公开的服务说明 （元数据） 创建服务模型代理代码。</span><span class="sxs-lookup"><span data-stu-id="42ad1-217">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="42ad1-218">对于出站操作，该工具将创建一个 WCF 客户端类和帮助器代码;对于入站操作，该工具创建 WCF 服务协定和帮助程序代码。</span><span class="sxs-lookup"><span data-stu-id="42ad1-218">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="42ad1-219">**SOAP （简单对象访问协议）**</span><span class="sxs-lookup"><span data-stu-id="42ad1-219">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="42ad1-220">用于交换结构化和分散、 分布式环境中的类型信息的简单、 基于 XML 的协议。</span><span class="sxs-lookup"><span data-stu-id="42ad1-220">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="42ad1-221">WCF 基于客户端与服务调用操作并返回结果的 SOAP 消息的交换。</span><span class="sxs-lookup"><span data-stu-id="42ad1-221">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="42ad1-222">**SOAP 消息**</span><span class="sxs-lookup"><span data-stu-id="42ad1-222">**SOAP message**</span></span>  
<span data-ttu-id="42ad1-223">格式正确的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="42ad1-223">A well-formed XML document.</span></span> <span data-ttu-id="42ad1-224">它应使用的 SOAP 信封和 SOAP 编码命名空间并包含可选的 XML 声明后, 跟 SOAP 信封 （根元素），其中一个可选的 SOAP 标头和 SOAP 消息正文组成。</span><span class="sxs-lookup"><span data-stu-id="42ad1-224">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="42ad1-225">**SQL Server Integration Services (SSIS)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-225">**SQL Server Integration Services (SSIS)**</span></span>  
<span data-ttu-id="42ad1-226">使用导入、 导出和转换来自不同数据源的数据的组件。</span><span class="sxs-lookup"><span data-stu-id="42ad1-226">A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="42ad1-227">以前调用过数据转换服务 (DTS)。</span><span class="sxs-lookup"><span data-stu-id="42ad1-227">Previously called data transformation service (DTS).</span></span>
  
<span data-ttu-id="42ad1-228">**强类型化数据**</span><span class="sxs-lookup"><span data-stu-id="42ad1-228">**strongly-typed data**</span></span>  
<span data-ttu-id="42ad1-229">数据集或绑定到基础对象类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="42ad1-229">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="42ad1-230">强类型化的 XML 数据集中的每一行被组成类型化的名为对应于基础对象类型的字段的元素。</span><span class="sxs-lookup"><span data-stu-id="42ad1-230">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span>

  
## <a name="t"></a><span data-ttu-id="42ad1-231">T</span><span class="sxs-lookup"><span data-stu-id="42ad1-231">T</span></span>  
  
<span data-ttu-id="42ad1-232">**事务 ID (TID)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-232">**transaction ID (TID)**</span></span>  
<span data-ttu-id="42ad1-233">SAP 相关联的工作 (LUW) 的每个逻辑单元的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="42ad1-233">A globally-unique identifier that SAP associates with each logical unit of work (LUW).</span></span>  
  
 
## <a name="w"></a><span data-ttu-id="42ad1-234">W</span><span class="sxs-lookup"><span data-stu-id="42ad1-234">W</span></span>  
  
<span data-ttu-id="42ad1-235">**WCF 通道模型**</span><span class="sxs-lookup"><span data-stu-id="42ad1-235">**WCF channel model**</span></span>  
<span data-ttu-id="42ad1-236">依赖于多个接口和其他类型的编程模型。</span><span class="sxs-lookup"><span data-stu-id="42ad1-236">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="42ad1-237">通道提供用于发送和接收消息的低级编程模型。</span><span class="sxs-lookup"><span data-stu-id="42ad1-237">Channels provide a low-level programming model for sending and receiving messages.</span></span>
  
<span data-ttu-id="42ad1-238">**WCF 客户端**</span><span class="sxs-lookup"><span data-stu-id="42ad1-238">**WCF client**</span></span>  
<span data-ttu-id="42ad1-239">一种服务操作作为方法公开的客户端应用程序构造。</span><span class="sxs-lookup"><span data-stu-id="42ad1-239">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="42ad1-240">可以使用添加适配器服务参考 Visual Studio 插件或 ServiceModel Metadata Utility Tool 从由适配器公开的元数据生成 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="42ad1-240">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="42ad1-241">**WCF 服务约定**</span><span class="sxs-lookup"><span data-stu-id="42ad1-241">**WCF service contract**</span></span>  
<span data-ttu-id="42ad1-242">服务协定的托管代码表示形式。</span><span class="sxs-lookup"><span data-stu-id="42ad1-242">A managed-code representation of the service contract.</span></span> <span data-ttu-id="42ad1-243">它将表示为一个接口的类和方法中经过属性化来定义服务、 操作、 消息和数据协定，用来与服务通信。</span><span class="sxs-lookup"><span data-stu-id="42ad1-243">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="42ad1-244">可以使用 ServiceModel 元数据实用工具工具或添加适配器服务参考 Visual Studio 插件以从由适配器公开的元数据生成 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="42ad1-244">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="42ad1-245">实现 WCF 服务约定以接收从 LOB 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="42ad1-245">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="42ad1-246">**WCF 服务模型**</span><span class="sxs-lookup"><span data-stu-id="42ad1-246">**WCF service model**</span></span>  
<span data-ttu-id="42ad1-247">WCF 编程模型在其中一项服务表示为托管的代码对象。</span><span class="sxs-lookup"><span data-stu-id="42ad1-247">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="42ad1-248">由服务公开的操作表示为具有强类型化数据的方法。</span><span class="sxs-lookup"><span data-stu-id="42ad1-248">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="42ad1-249">**弱类型数据**</span><span class="sxs-lookup"><span data-stu-id="42ad1-249">**weakly-typed data**</span></span>  
<span data-ttu-id="42ad1-250">数据集或未绑定到基础对象类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="42ad1-250">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="42ad1-251">在弱类型 XML 数据集中每个行组成的一般列中的属性描述的名称和类型的每个元素的集合。</span><span class="sxs-lookup"><span data-stu-id="42ad1-251">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="42ad1-252">**Web 服务**</span><span class="sxs-lookup"><span data-stu-id="42ad1-252">**Web services**</span></span>  
<span data-ttu-id="42ad1-253">提供数据和服务添加到其他应用程序的应用程序逻辑的单位。</span><span class="sxs-lookup"><span data-stu-id="42ad1-253">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="42ad1-254">应用程序访问 XML Web services 使用标准 Web 协议和数据格式如 HTTP、 XML 和 SOAP，独立于每个 XML Web 服务的实现方式。</span><span class="sxs-lookup"><span data-stu-id="42ad1-254">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="42ad1-255">XML Web services 结合了基于组件的开发的最佳方面和 Web，和是 Microsoft.NET 编程模型的基石。</span><span class="sxs-lookup"><span data-stu-id="42ad1-255">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="42ad1-256">**Web 服务描述语言 (WSDL)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-256">**Web Services Description Language (WSDL)**</span></span>  
<span data-ttu-id="42ad1-257">一种基于 XML 的语言，它描述为一组操作的终结点对消息的服务。</span><span class="sxs-lookup"><span data-stu-id="42ad1-257">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="42ad1-258">WSDL 文档描述服务协定、 操作约定、 消息协定和客户端必须使用的数据协定与服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="42ad1-258">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="42ad1-259">**Windows Communication Framework (WCF)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-259">**Windows Communication Framework (WCF)**</span></span>  
<span data-ttu-id="42ad1-260">Microsoft 面向服务的通信基础结构。</span><span class="sxs-lookup"><span data-stu-id="42ad1-260">A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="42ad1-261">该框架本质上是提供客户端与服务编程模型和编程模型，用于消息交换的更精细的控制通道。</span><span class="sxs-lookup"><span data-stu-id="42ad1-261">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>

<span data-ttu-id="42ad1-262">**WS-元数据交换 (MEX) 终结点**</span><span class="sxs-lookup"><span data-stu-id="42ad1-262">**WS-Metadata Exchange (MEX) endpoint**</span></span>  
<span data-ttu-id="42ad1-263">实现 WCF 服务，如适配器公开的终结点**IMetadataExchange**接口。</span><span class="sxs-lookup"><span data-stu-id="42ad1-263">An endpoint exposed by a WCF service, such as an adapter, that implements the **IMetadataExchange** interface.</span></span> <span data-ttu-id="42ad1-264">WS-元数据交换终结点可以用于检索服务说明 (WSDL) 公开目标系统上的适配器的操作。</span><span class="sxs-lookup"><span data-stu-id="42ad1-264">A WS-Metadata Exchange endpoint can be used to retrieve a service description (WSDL) for operations exposed by an adapter on the target system.</span></span>  
  
## <a name="x"></a><span data-ttu-id="42ad1-265">X</span><span class="sxs-lookup"><span data-stu-id="42ad1-265">X</span></span>  
  
<span data-ttu-id="42ad1-266">**XML 架构定义语言 (XSD)**</span><span class="sxs-lookup"><span data-stu-id="42ad1-266">**XML Schema definition language (XSD)**</span></span>  
<span data-ttu-id="42ad1-267">一种架构语言。</span><span class="sxs-lookup"><span data-stu-id="42ad1-267">A schema language.</span></span> <span data-ttu-id="42ad1-268">XML 架构定义元素、 属性和数据类型符合 World Wide Web 联合会 (W3C) XML 架构第 1 部分：XML 架构定义语言的结构建议。</span><span class="sxs-lookup"><span data-stu-id="42ad1-268">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="42ad1-269">W3C XML 架构第 2 部分：Datatypes Recommendation 是用于在 XML 架构中定义所使用的数据类型的建议。</span><span class="sxs-lookup"><span data-stu-id="42ad1-269">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="42ad1-270">XML 架构定义语言，可定义 XML 消息的结构和数据类型。</span><span class="sxs-lookup"><span data-stu-id="42ad1-270">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>