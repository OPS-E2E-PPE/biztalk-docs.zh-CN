---
title: 用于在 BizTalk 中的 Oracle 数据库的 BizTalk 适配器的术语表 |Microsoft Docs
description: 常见术语和定义使用的 BizTalk 适配器包 (BAP) 中的 Oracle 数据库适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d386cd36-d8e4-4e5e-806e-0d02e042344f
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2a89bfcfcf387ed6451f795a9e5f83c174eca74
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65376523"
---
# <a name="glossary"></a><span data-ttu-id="ab36c-103">词汇表</span><span class="sxs-lookup"><span data-stu-id="ab36c-103">Glossary</span></span>
<span data-ttu-id="ab36c-104">中使用以下术语和定义[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ab36c-104">The following terms and definitions are used in [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)].</span></span>    
  
## <a name="a"></a><span data-ttu-id="ab36c-105">A</span><span class="sxs-lookup"><span data-stu-id="ab36c-105">A</span></span>  
  
<span data-ttu-id="ab36c-106">**adapter**</span><span class="sxs-lookup"><span data-stu-id="ab36c-106">**adapter**</span></span>  
<span data-ttu-id="ab36c-107">基于 WCF 的组件，可帮助 exchange 应用程序 （例如，业务线系统） 之间的消息和 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="ab36c-107">A WCF-based component that helps exchange messages between applications (for example, a line-of-business system) and BizTalk Server.</span></span> <span data-ttu-id="ab36c-108">适配器由设计时组件和接收和发送操作的运行时组件组成。</span><span class="sxs-lookup"><span data-stu-id="ab36c-108">The adapter consists of design-time components and run-time components for receive and send operations.</span></span>

<span data-ttu-id="ab36c-109">**适配器客户端**</span><span class="sxs-lookup"><span data-stu-id="ab36c-109">**adapter client**</span></span>  
<span data-ttu-id="ab36c-110">应用程序与通过适配器的业务线 (LOB) 系统进行交互。</span><span class="sxs-lookup"><span data-stu-id="ab36c-110">An application that interacts with a line-of-business (LOB) system through the adapter.</span></span>  
  
## <a name="b"></a><span data-ttu-id="ab36c-111">B</span><span class="sxs-lookup"><span data-stu-id="ab36c-111">B</span></span>  
  
<span data-ttu-id="ab36c-112">**BFILE**</span><span class="sxs-lookup"><span data-stu-id="ab36c-112">**BFILE**</span></span>  
<span data-ttu-id="ab36c-113">Oracle 数据类型，可以访问二进制文件存储在文件系统外部的 Oracle 数据库中的 Lob。</span><span class="sxs-lookup"><span data-stu-id="ab36c-113">An Oracle data type that enables access to binary file LOBs that are stored in file systems external to the Oracle database.</span></span> <span data-ttu-id="ab36c-114">一个 BFILE 列存储 BFILE 定位符，它表示的目录名称和包含服务器文件系统上的数据的文件名称。</span><span class="sxs-lookup"><span data-stu-id="ab36c-114">A BFILE column stores a BFILE locator, which represents the directory name and file name that contains the data on the server file system.</span></span>

<span data-ttu-id="ab36c-115">**二进制大型对象**</span><span class="sxs-lookup"><span data-stu-id="ab36c-115">**binary large object**</span></span>  
1.  <span data-ttu-id="ab36c-116">一个大型的数据，如位图，特征是大型字段值、 不可预测的表的大小，并为不从应用程序的角度来看定型数据的数据。</span><span class="sxs-lookup"><span data-stu-id="ab36c-116">A large piece of data, such as a bitmap, characterized by large field values, an unpredictable table size, and data that is formless from the perspective of an application.</span></span>
2.  <span data-ttu-id="ab36c-117">指定包含有关的数据块的信息的 BLOB 结构关键字。</span><span class="sxs-lookup"><span data-stu-id="ab36c-117">A keyword that designates the BLOB structure that contains information about a block of data.</span></span>

<span data-ttu-id="ab36c-118">**binding**</span><span class="sxs-lookup"><span data-stu-id="ab36c-118">**binding**</span></span>  
<span data-ttu-id="ab36c-119">通过哪种软件组件和层链接在一起的过程。</span><span class="sxs-lookup"><span data-stu-id="ab36c-119">A process by which software components and layers are linked together.</span></span> <span data-ttu-id="ab36c-120">安装网络组件时，建立绑定关系和依赖项的组件。</span><span class="sxs-lookup"><span data-stu-id="ab36c-120">When a network component is installed, the binding relationships and dependencies for the components are established.</span></span> <span data-ttu-id="ab36c-121">绑定允许组件彼此通信。</span><span class="sxs-lookup"><span data-stu-id="ab36c-121">Binding allows components to communicate with each other.</span></span> <span data-ttu-id="ab36c-122">在 BizTalk Server 中，业务流程适配器无关的终结点 （端口或角色链接） 和物理特定于适配器的终结点 （发送/接收端口或参与方） 之间已建立的映射。</span><span class="sxs-lookup"><span data-stu-id="ab36c-122">In BizTalk Server, an established mapping between an orchestration adapter-agnostic endpoint (port or role link) and physical adapter-specific endpoints (send/receive ports or party).</span></span>

<span data-ttu-id="ab36c-123">**BizTalk Server**</span><span class="sxs-lookup"><span data-stu-id="ab36c-123">**BizTalk Server**</span></span>  
<span data-ttu-id="ab36c-124">连接不同的软件。</span><span class="sxs-lookup"><span data-stu-id="ab36c-124">Connects diverse software.</span></span> <span data-ttu-id="ab36c-125">BizTalk Server，可创建和修改使用该软件的流程逻辑。</span><span class="sxs-lookup"><span data-stu-id="ab36c-125">BizTalk Server enables you to create and modify process logic that uses that software.</span></span> <span data-ttu-id="ab36c-126">BizTalk Server 还可以监视正在运行的进程、 与贸易合作伙伴进行交互以及执行其他面向企业的任务的信息工作者。</span><span class="sxs-lookup"><span data-stu-id="ab36c-126">BizTalk Server also enables information workers to monitor running processes, interact with trading partners, and perform other business-oriented tasks.</span></span>
  
## <a name="c"></a><span data-ttu-id="ab36c-127">C</span><span class="sxs-lookup"><span data-stu-id="ab36c-127">C</span></span>  
  
<span data-ttu-id="ab36c-128">**channel**</span><span class="sxs-lookup"><span data-stu-id="ab36c-128">**channel**</span></span>  
<span data-ttu-id="ab36c-129">绑定元素的具体实现。</span><span class="sxs-lookup"><span data-stu-id="ab36c-129">A concrete implementation of a binding element.</span></span> <span data-ttu-id="ab36c-130">绑定表示配置，而通道为与该配置关联的实现。</span><span class="sxs-lookup"><span data-stu-id="ab36c-130">The binding represents the configuration, and the channel is the implementation associated with that configuration.</span></span> <span data-ttu-id="ab36c-131">因此，没有与每个绑定元素关联的通道。</span><span class="sxs-lookup"><span data-stu-id="ab36c-131">Therefore, there is a channel associated with each binding element.</span></span> <span data-ttu-id="ab36c-132">通道堆叠在一起以形成绑定的具体实现： 通道堆栈。</span><span class="sxs-lookup"><span data-stu-id="ab36c-132">Channels stack on top of each other to create the concrete implementation of the binding: the channel stack.</span></span>

<span data-ttu-id="ab36c-133">**连接 URI**</span><span class="sxs-lookup"><span data-stu-id="ab36c-133">**connection URI**</span></span>  
<span data-ttu-id="ab36c-134">标识分布式环境中的资源的字符串。</span><span class="sxs-lookup"><span data-stu-id="ab36c-134">A string that identifies a resource in a distributed environment.</span></span> <span data-ttu-id="ab36c-135">适配器使用统一资源标识符 (URI)，其中包含与 LOB 系统建立连接所需的信息的连接。</span><span class="sxs-lookup"><span data-stu-id="ab36c-135">Adapters use a connection Uniform Resource Identifier (URI) that contains the information necessary to establish a connection with the LOB system.</span></span>

<span data-ttu-id="ab36c-136">**contract**</span><span class="sxs-lookup"><span data-stu-id="ab36c-136">**contract**</span></span>  
<span data-ttu-id="ab36c-137">指定的集合和访问服务提供的操作所需的消息的结构。</span><span class="sxs-lookup"><span data-stu-id="ab36c-137">Specifies the collection and structure of messages required to access the operations offered by the service.</span></span>  
  
## <a name="d"></a><span data-ttu-id="ab36c-138">D</span><span class="sxs-lookup"><span data-stu-id="ab36c-138">D</span></span>  
  
<span data-ttu-id="ab36c-139">**数据操作语言 (DML)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-139">**data manipulation language (DML)**</span></span>  
<span data-ttu-id="ab36c-140">用于检索和操作数据的 SQL 语句的子集。</span><span class="sxs-lookup"><span data-stu-id="ab36c-140">The subset of SQL statements that is used to retrieve and manipulate data.</span></span> <span data-ttu-id="ab36c-141">DML 语句通常开始于 SELECT、 INSERT、 UPDATE 或 DELETE。</span><span class="sxs-lookup"><span data-stu-id="ab36c-141">DML statements typically start with SELECT, INSERT, UPDATE, or DELETE.</span></span>

<span data-ttu-id="ab36c-142">**设计时体验**</span><span class="sxs-lookup"><span data-stu-id="ab36c-142">**design-time experience**</span></span>  
<span data-ttu-id="ab36c-143">过程和开发人员在设计时期间执行的操作例如，使用使用适配器服务的 BizTalk 项目添加中检索消息架构。</span><span class="sxs-lookup"><span data-stu-id="ab36c-143">Procedures and operations that a developer performs during design time; for example, using the Consume Adapter Service BizTalk Project Add-in to retrieve message schemas.</span></span>  
  
## <a name="e"></a><span data-ttu-id="ab36c-144">E</span><span class="sxs-lookup"><span data-stu-id="ab36c-144">E</span></span>  
  
<span data-ttu-id="ab36c-145">**终结点地址**</span><span class="sxs-lookup"><span data-stu-id="ab36c-145">**endpoint address**</span></span>  
<span data-ttu-id="ab36c-146">网络地址标识 Windows Communication Foundation (WCF) 服务终结点的位置。</span><span class="sxs-lookup"><span data-stu-id="ab36c-146">A network address that identifies the location of a Windows Communication Foundation (WCF) service endpoint.</span></span> <span data-ttu-id="ab36c-147">为适配器，终结点地址表示为统一资源标识符 (URI)，其中包含位置和连接参数的连接。</span><span class="sxs-lookup"><span data-stu-id="ab36c-147">For an adapter, the endpoint address is expressed as a connection Uniform Resource Identifier (URI) that contains location and connection parameters.</span></span> <span data-ttu-id="ab36c-148">适配器可以使用这些来建立与基础业务 (LOB) 系统的连接。</span><span class="sxs-lookup"><span data-stu-id="ab36c-148">The adapter can use these to establish a connection to the underlying line-of-business (LOB) system.</span></span>

<span data-ttu-id="ab36c-149">**企业单一登录系统 (SSO)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-149">**Enterprise Single Sign-on system (SSO)**</span></span>  
<span data-ttu-id="ab36c-150">SSO 数据库、 主密钥服务器和一个或多个企业单一登录 (SSO) 服务器。</span><span class="sxs-lookup"><span data-stu-id="ab36c-150">An SSO database, a master secret server, and one or more Enterprise Single Sign-On (SSO) servers.</span></span> <span data-ttu-id="ab36c-151">这些服务器的 Windows 和非 Windows 凭据之间进行映射，查找在 SSO 数据库中，凭据用于管理 SSO 系统。</span><span class="sxs-lookup"><span data-stu-id="ab36c-151">These servers do the mapping between the Windows and non-Windows credentials, look up the credentials in the SSO database, and are used for administering the SSO system.</span></span> <span data-ttu-id="ab36c-152">SSO 数据库还用作为配置存储来保存适配器的自定义配置数据。</span><span class="sxs-lookup"><span data-stu-id="ab36c-152">The SSO database is also used as a configuration store to hold custom configuration data for adapters.</span></span>

<span data-ttu-id="ab36c-153">**可扩展标记语言 (XML)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-153">**Extensible Markup Language (XML)**</span></span>  
<span data-ttu-id="ab36c-154">标记语言，专门用于描述数据。</span><span class="sxs-lookup"><span data-stu-id="ab36c-154">A markup language designed to describe data.</span></span> <span data-ttu-id="ab36c-155">未预定义的 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="ab36c-155">XML tags are not predefined.</span></span>  
  
## <a name="g"></a><span data-ttu-id="ab36c-156">G</span><span class="sxs-lookup"><span data-stu-id="ab36c-156">G</span></span>  
  
<span data-ttu-id="ab36c-157">**全局程序集缓存 (GAC)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-157">**global assembly cache (GAC)**</span></span>  
<span data-ttu-id="ab36c-158">计算机范围内的代码缓存，用于存储专为由计算机上的许多应用程序共享而安装的程序集。</span><span class="sxs-lookup"><span data-stu-id="ab36c-158">A machine-wide code cache that stores assemblies specifically installed to be shared by many applications on the computer.</span></span> <span data-ttu-id="ab36c-159">应用程序部署到全局程序集缓存中必须具有强名称。</span><span class="sxs-lookup"><span data-stu-id="ab36c-159">Applications deployed in the global assembly cache must have a strong name.</span></span>
  
## <a name="i"></a><span data-ttu-id="ab36c-160">I</span><span class="sxs-lookup"><span data-stu-id="ab36c-160">I</span></span>  
  
<span data-ttu-id="ab36c-161">**入站的操作**</span><span class="sxs-lookup"><span data-stu-id="ab36c-161">**inbound operation**</span></span>  
<span data-ttu-id="ab36c-162">调用的业务 (LOB) 系统的适配器上的操作。</span><span class="sxs-lookup"><span data-stu-id="ab36c-162">An operation that is invoked by a line-of-business (LOB) system on the adapter.</span></span>  
  
## <a name="l"></a><span data-ttu-id="ab36c-163">L</span><span class="sxs-lookup"><span data-stu-id="ab36c-163">L</span></span>  
  
<span data-ttu-id="ab36c-164">**本地命名方法**</span><span class="sxs-lookup"><span data-stu-id="ab36c-164">**local naming method**</span></span>  
<span data-ttu-id="ab36c-165">Oracle 命名 Oracle 数据库适配器所支持的方法。</span><span class="sxs-lookup"><span data-stu-id="ab36c-165">The Oracle naming method that is supported by the Oracle Database adapter.</span></span> <span data-ttu-id="ab36c-166">在此命名方法中，对 Oracle 客户端将网络服务名称解析为本地 tnsnames.ora 文件中的条目。</span><span class="sxs-lookup"><span data-stu-id="ab36c-166">In this naming method, the Oracle client resolves the net service name to an entry in the local tnsnames.ora file.</span></span>  
  
## <a name="m"></a><span data-ttu-id="ab36c-167">M</span><span class="sxs-lookup"><span data-stu-id="ab36c-167">M</span></span>  
  
<span data-ttu-id="ab36c-168">**metadata**</span><span class="sxs-lookup"><span data-stu-id="ab36c-168">**metadata**</span></span>  
<span data-ttu-id="ab36c-169">在 WCF 中，是指由服务公开的协定说明。</span><span class="sxs-lookup"><span data-stu-id="ab36c-169">In WCF, refers to a description of the contract exposed by a service.</span></span> <span data-ttu-id="ab36c-170">这称为服务说明和表示 WSDL 文档中。</span><span class="sxs-lookup"><span data-stu-id="ab36c-170">This is known as the service description and is expressed in a WSDL document.</span></span> <span data-ttu-id="ab36c-171">由适配器公开的元数据描述的 （接口） 它可以对基础 LOB 系统执行的操作。</span><span class="sxs-lookup"><span data-stu-id="ab36c-171">The metadata exposed by an adapter describes the (interface to) the operations that it can perform on the underlying LOB system.</span></span>

**[!INCLUDE[afproductnamelong](../../includes/afproductnamelong-md.md)]**  
<span data-ttu-id="ab36c-172">生成 BizTalk 适配器使用基于 Web 服务的开放标准规范。</span><span class="sxs-lookup"><span data-stu-id="ab36c-172">The specifications for building BizTalk adapters using open standards based on Web services.</span></span>  
  
## <a name="n"></a><span data-ttu-id="ab36c-173">N</span><span class="sxs-lookup"><span data-stu-id="ab36c-173">N</span></span>  
  
<span data-ttu-id="ab36c-174">**命名方法**</span><span class="sxs-lookup"><span data-stu-id="ab36c-174">**naming method**</span></span>  
<span data-ttu-id="ab36c-175">Oracle 命名方法确定如何对 Oracle 客户端获取 Oracle 数据库服务 （实例） 的连接信息。</span><span class="sxs-lookup"><span data-stu-id="ab36c-175">Oracle naming methods determine how the Oracle client obtains connection information for an Oracle database service (instance).</span></span> <span data-ttu-id="ab36c-176">可以配置 Oracle 客户端通过使用 Oracle 网络配置助手使用特定的命名方法。</span><span class="sxs-lookup"><span data-stu-id="ab36c-176">You can configure the Oracle client to use specific naming methods by using the Oracle Net Configuration Assistant.</span></span> <span data-ttu-id="ab36c-177">Oracle 数据库适配器支持本地命名方法。</span><span class="sxs-lookup"><span data-stu-id="ab36c-177">The Oracle Database adapter supports the Local Naming method.</span></span>

<span data-ttu-id="ab36c-178">**网络服务名称**</span><span class="sxs-lookup"><span data-stu-id="ab36c-178">**net service name**</span></span>  
<span data-ttu-id="ab36c-179">Oracle 客户端用于获取连接信息的 Oracle 数据库别名。</span><span class="sxs-lookup"><span data-stu-id="ab36c-179">An alias used by the Oracle client to obtain connection information for the Oracle database.</span></span> <span data-ttu-id="ab36c-180">作为一个连接 URI 中的连接属性提供网络服务名称。</span><span class="sxs-lookup"><span data-stu-id="ab36c-180">You supply a net service name as one of the connection properties in the connection URI.</span></span>  
  
## <a name="o"></a><span data-ttu-id="ab36c-181">O</span><span class="sxs-lookup"><span data-stu-id="ab36c-181">O</span></span>  
  
<span data-ttu-id="ab36c-182">**one-way**</span><span class="sxs-lookup"><span data-stu-id="ab36c-182">**one-way**</span></span>  
<span data-ttu-id="ab36c-183">接收方会返回在其中发送方发送一条消息，但无响应的消息交换模式 (MEP)。</span><span class="sxs-lookup"><span data-stu-id="ab36c-183">A message exchange pattern (MEP) in which the sender sends a message, but no response is returned by the receiver.</span></span> <span data-ttu-id="ab36c-184">在 BizTalk Server 中，Mep 统称为通信模式。</span><span class="sxs-lookup"><span data-stu-id="ab36c-184">In BizTalk Server, MEPs are referred to as communication patterns.</span></span>

<span data-ttu-id="ab36c-185">**出站操作**</span><span class="sxs-lookup"><span data-stu-id="ab36c-185">**outbound operation**</span></span>  
<span data-ttu-id="ab36c-186">由业务线系统 (LOB) 适配器调用操作。</span><span class="sxs-lookup"><span data-stu-id="ab36c-186">An operation that is invoked by the adapter on the line-of-business system (LOB).</span></span>

<span data-ttu-id="ab36c-187">**output.cs**</span><span class="sxs-lookup"><span data-stu-id="ab36c-187">**output.cs**</span></span>  
<span data-ttu-id="ab36c-188">ServiceModel 元数据实用工具 (svcutil.exe) 工具创建的默认输出文件。</span><span class="sxs-lookup"><span data-stu-id="ab36c-188">The default output file created by the ServiceModel Metadata Utility tool (svcutil.exe).</span></span>  
  
## <a name="p"></a><span data-ttu-id="ab36c-189">P</span><span class="sxs-lookup"><span data-stu-id="ab36c-189">P</span></span>  
  
<span data-ttu-id="ab36c-190">**polling**</span><span class="sxs-lookup"><span data-stu-id="ab36c-190">**polling**</span></span>  
<span data-ttu-id="ab36c-191">设备驱动程序用于找出从多个设备它们是否包含要传输的数据的一种方法。</span><span class="sxs-lookup"><span data-stu-id="ab36c-191">A technique that device drivers use to find out from multiple devices whether they contain data to transmit.</span></span> <span data-ttu-id="ab36c-192">设备是轮询一次一个。</span><span class="sxs-lookup"><span data-stu-id="ab36c-192">The devices are polled one at a time.</span></span>

<span data-ttu-id="ab36c-193">**proxy**</span><span class="sxs-lookup"><span data-stu-id="ab36c-193">**proxy**</span></span>  
<span data-ttu-id="ab36c-194">在 WCF 中，是指用于实现服务协定由服务公开的托管代码对象。</span><span class="sxs-lookup"><span data-stu-id="ab36c-194">In WCF, refers to a managed-code object that implements the service contract exposed by a service.</span></span> <span data-ttu-id="ab36c-195">WCF 服务模型基于此类代理使用。</span><span class="sxs-lookup"><span data-stu-id="ab36c-195">The WCF service model is based on the use of such proxies.</span></span> <span data-ttu-id="ab36c-196">在 WCF 服务模型中，服务协定表示为.NET 接口。</span><span class="sxs-lookup"><span data-stu-id="ab36c-196">In the WCF service model, the service contract is expressed as a .NET interface.</span></span>
  
## <a name="r"></a><span data-ttu-id="ab36c-197">R</span><span class="sxs-lookup"><span data-stu-id="ab36c-197">R</span></span>  
  
<span data-ttu-id="ab36c-198">**REF CURSOR**</span><span class="sxs-lookup"><span data-stu-id="ab36c-198">**REF CURSOR**</span></span>  
<span data-ttu-id="ab36c-199">Oracle PL/SQL 数据类型，对结果集的 Oracle 数据库中表示的指针。</span><span class="sxs-lookup"><span data-stu-id="ab36c-199">An Oracle PL/SQL data type that represents a pointer to a result set in the Oracle database.</span></span> <span data-ttu-id="ab36c-200">REF CURSOR 类型支持输入和输出数据的流式处理，适合用于传输大量数据传入和传出 PL/SQL 代码块。</span><span class="sxs-lookup"><span data-stu-id="ab36c-200">A REF CURSOR type enables input and output streaming of data, and is ideal for transferring large amounts of data to and from a PL/SQL code block.</span></span>

<span data-ttu-id="ab36c-201">**request-response**</span><span class="sxs-lookup"><span data-stu-id="ab36c-201">**request-response**</span></span>  
<span data-ttu-id="ab36c-202">消息交换模式 (MEP) 发件人发送请求消息，并期望来自接收方的响应消息。</span><span class="sxs-lookup"><span data-stu-id="ab36c-202">A message exchange pattern (MEP) in which the sender sends a request message and expects a response message from the receiver.</span></span> <span data-ttu-id="ab36c-203">在 BizTalk Server 中，Mep 统称为通信模式。</span><span class="sxs-lookup"><span data-stu-id="ab36c-203">In BizTalk Server, MEPs are referred to as communication patterns.</span></span> <span data-ttu-id="ab36c-204">具体取决于消息传送技术和方向 （入站或出站） 的请求消息，此模式也称为请求-答复或要求响应。</span><span class="sxs-lookup"><span data-stu-id="ab36c-204">Depending on the messaging technology and the direction of the request message (inbound or outbound), this pattern is also called request-reply or solicit-response.</span></span>

<span data-ttu-id="ab36c-205">**运行时体验**</span><span class="sxs-lookup"><span data-stu-id="ab36c-205">**run-time experience**</span></span>  
<span data-ttu-id="ab36c-206">过程和在运行时期间或部署解决方案; 由开发人员执行的操作例如，从 BizTalk Server 管理控制台中创建物理端口绑定。</span><span class="sxs-lookup"><span data-stu-id="ab36c-206">Procedures and operations performed by a developer during run time or when deploying a solution; for example, creating a physical port binding from the BizTalk Server Administration console.</span></span>  
  
## <a name="s"></a><span data-ttu-id="ab36c-207">S</span><span class="sxs-lookup"><span data-stu-id="ab36c-207">S</span></span>  
  
<span data-ttu-id="ab36c-208">**schema**</span><span class="sxs-lookup"><span data-stu-id="ab36c-208">**schema**</span></span>  
<span data-ttu-id="ab36c-209">一条消息的结构。</span><span class="sxs-lookup"><span data-stu-id="ab36c-209">The structure for a message.</span></span> <span data-ttu-id="ab36c-210">架构可以包含多个子架构。</span><span class="sxs-lookup"><span data-stu-id="ab36c-210">A schema can contain multiple subschema.</span></span>

<span data-ttu-id="ab36c-211">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-211">**ServiceModel Metadata Utility Tool (svcutil.exe)**</span></span>  
<span data-ttu-id="ab36c-212">WCF 附带一个命令行实用工具。</span><span class="sxs-lookup"><span data-stu-id="ab36c-212">A command-line utility that is included with WCF.</span></span> <span data-ttu-id="ab36c-213">它用于从由适配器之类的 WCF 服务公开的服务说明 （元数据） 创建服务模型代理代码。</span><span class="sxs-lookup"><span data-stu-id="ab36c-213">It is used to create service model proxy code from the service description (metadata) that is exposed by a WCF service such as an adapter.</span></span> <span data-ttu-id="ab36c-214">对于出站操作，该工具将创建一个 WCF 客户端类和帮助器代码;对于入站操作，该工具创建 WCF 服务协定和帮助程序代码。</span><span class="sxs-lookup"><span data-stu-id="ab36c-214">For outbound operations, the tool creates a WCF client class and helper code; for inbound operations, the tool creates a WCF service contract and helper code.</span></span>

<span data-ttu-id="ab36c-215">**SOAP （简单对象访问协议）**</span><span class="sxs-lookup"><span data-stu-id="ab36c-215">**SOAP (Simple Object Access Protocol)**</span></span>  
<span data-ttu-id="ab36c-216">用于交换结构化和分散、 分布式环境中的类型信息的简单、 基于 XML 的协议。</span><span class="sxs-lookup"><span data-stu-id="ab36c-216">A simple, XML-based protocol for exchanging structured and type information in decentralized, distributed environments.</span></span> <span data-ttu-id="ab36c-217">WCF 基于客户端与服务调用操作并返回结果的 SOAP 消息的交换。</span><span class="sxs-lookup"><span data-stu-id="ab36c-217">WCF is based on the exchange of SOAP messages between clients and services to invoke operations and return results.</span></span>

<span data-ttu-id="ab36c-218">**SOAP 消息**</span><span class="sxs-lookup"><span data-stu-id="ab36c-218">**SOAP message**</span></span>  
<span data-ttu-id="ab36c-219">格式正确的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="ab36c-219">A well-formed XML document.</span></span> <span data-ttu-id="ab36c-220">它应使用的 SOAP 信封和 SOAP 编码命名空间并包含可选的 XML 声明后, 跟 SOAP 信封 （根元素），其中一个可选的 SOAP 标头和 SOAP 消息正文组成。</span><span class="sxs-lookup"><span data-stu-id="ab36c-220">It should use the SOAP envelope and SOAP encoding namespaces and include an optional XML declaration, followed by a SOAP envelope (the root element), which is made up of an optional SOAP header and a SOAP message body.</span></span>

<span data-ttu-id="ab36c-221">**SQL Server Integration Services (SSIS)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-221">**SQL Server Integration Services (SSIS)**</span></span>  
<span data-ttu-id="ab36c-222">使用导入、 导出和转换来自不同数据源的数据的组件。</span><span class="sxs-lookup"><span data-stu-id="ab36c-222">A component that is used to import, export, and transform data from different data sources.</span></span> <span data-ttu-id="ab36c-223">以前调用过数据转换服务 (DTS)。</span><span class="sxs-lookup"><span data-stu-id="ab36c-223">Previously called data transformation service (DTS).</span></span>

<span data-ttu-id="ab36c-224">**强类型化数据**</span><span class="sxs-lookup"><span data-stu-id="ab36c-224">**strongly-typed data**</span></span>  
<span data-ttu-id="ab36c-225">数据集或绑定到基础对象类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="ab36c-225">A data set or result set that is bound to an underlying object type.</span></span> <span data-ttu-id="ab36c-226">强类型化的 XML 数据集中的每一行被组成类型化的名为对应于基础对象类型的字段的元素。</span><span class="sxs-lookup"><span data-stu-id="ab36c-226">Each row in a strongly-typed XML data set is composed of typed, named elements that correspond to fields of the underlying object type.</span></span>  
 
## <a name="w"></a><span data-ttu-id="ab36c-227">W</span><span class="sxs-lookup"><span data-stu-id="ab36c-227">W</span></span>  
<span data-ttu-id="ab36c-228">**WCF 通道模型**</span><span class="sxs-lookup"><span data-stu-id="ab36c-228">**WCF channel model**</span></span>  
<span data-ttu-id="ab36c-229">依赖于多个接口和其他类型的编程模型。</span><span class="sxs-lookup"><span data-stu-id="ab36c-229">A programming model that relies on several interfaces and other types.</span></span> <span data-ttu-id="ab36c-230">通道提供用于发送和接收消息的低级编程模型。</span><span class="sxs-lookup"><span data-stu-id="ab36c-230">Channels provide a low-level programming model for sending and receiving messages.</span></span>

<span data-ttu-id="ab36c-231">**WCF 客户端**</span><span class="sxs-lookup"><span data-stu-id="ab36c-231">**WCF client**</span></span>  
<span data-ttu-id="ab36c-232">一种服务操作作为方法公开的客户端应用程序构造。</span><span class="sxs-lookup"><span data-stu-id="ab36c-232">A client-application construct that exposes the service operations as methods.</span></span> <span data-ttu-id="ab36c-233">可以使用添加适配器服务参考 Visual Studio 插件或 ServiceModel Metadata Utility Tool 从由适配器公开的元数据生成 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="ab36c-233">You can use the Add Adapter Service Reference Visual Studio Plug-in or the ServiceModel Metadata Utility Tool to generate a WCF client class from the metadata exposed by an adapter.</span></span>

<span data-ttu-id="ab36c-234">**WCF 服务约定**</span><span class="sxs-lookup"><span data-stu-id="ab36c-234">**WCF service contract**</span></span>  
<span data-ttu-id="ab36c-235">服务协定的托管代码表示形式。</span><span class="sxs-lookup"><span data-stu-id="ab36c-235">A managed-code representation of the service contract.</span></span> <span data-ttu-id="ab36c-236">它将表示为一个接口的类和方法中经过属性化来定义服务、 操作、 消息和数据协定，用来与服务通信。</span><span class="sxs-lookup"><span data-stu-id="ab36c-236">It is expressed as an interface in which classes and methods are attributed to define the service, operation, message, and data contracts used to communicate with a service.</span></span> <span data-ttu-id="ab36c-237">可以使用 ServiceModel 元数据实用工具工具或添加适配器服务参考 Visual Studio 插件以从由适配器公开的元数据生成 WCF 服务约定。</span><span class="sxs-lookup"><span data-stu-id="ab36c-237">You can use the ServiceModel Metadata Utility tool or the Add Adapter Service Reference Visual Studio Plug-in to generate a WCF service contract from the metadata exposed by an adapter.</span></span> <span data-ttu-id="ab36c-238">实现 WCF 服务约定以接收从 LOB 系统的操作。</span><span class="sxs-lookup"><span data-stu-id="ab36c-238">You implement the WCF service contract to receive operations from an LOB system.</span></span>

<span data-ttu-id="ab36c-239">**WCF 服务模型**</span><span class="sxs-lookup"><span data-stu-id="ab36c-239">**WCF service model**</span></span>  
<span data-ttu-id="ab36c-240">WCF 编程模型在其中一项服务表示为托管的代码对象。</span><span class="sxs-lookup"><span data-stu-id="ab36c-240">A WCF programming model in which a service is represented as a managed code object.</span></span> <span data-ttu-id="ab36c-241">由服务公开的操作表示为具有强类型化数据的方法。</span><span class="sxs-lookup"><span data-stu-id="ab36c-241">The operations exposed by the service are represented as methods with strongly-typed data.</span></span>

<span data-ttu-id="ab36c-242">**弱类型数据**</span><span class="sxs-lookup"><span data-stu-id="ab36c-242">**weakly-typed data**</span></span>  
<span data-ttu-id="ab36c-243">数据集或未绑定到基础对象类型的结果集。</span><span class="sxs-lookup"><span data-stu-id="ab36c-243">A data set or result set that is not bound to an underlying object type.</span></span> <span data-ttu-id="ab36c-244">在弱类型 XML 数据集中每个行组成的一般列中的属性描述的名称和类型的每个元素的集合。</span><span class="sxs-lookup"><span data-stu-id="ab36c-244">Each row in a weakly-typed XML data set is composed of a collection of generic columns in which attributes describe the name and type of each element.</span></span>

<span data-ttu-id="ab36c-245">**Web 服务**</span><span class="sxs-lookup"><span data-stu-id="ab36c-245">**Web services**</span></span>  
<span data-ttu-id="ab36c-246">提供数据和服务添加到其他应用程序的应用程序逻辑的单位。</span><span class="sxs-lookup"><span data-stu-id="ab36c-246">A unit of application logic providing data and services to other applications.</span></span> <span data-ttu-id="ab36c-247">应用程序访问 XML Web services 使用标准 Web 协议和数据格式如 HTTP、 XML 和 SOAP，独立于每个 XML Web 服务的实现方式。</span><span class="sxs-lookup"><span data-stu-id="ab36c-247">Applications access XML Web services using standard Web protocols and data formats such as HTTP, XML, and SOAP, independent of how each XML Web service is implemented.</span></span> <span data-ttu-id="ab36c-248">XML Web services 结合了基于组件的开发的最佳方面和 Web，和是 Microsoft.NET 编程模型的基石。</span><span class="sxs-lookup"><span data-stu-id="ab36c-248">XML Web services combine the best aspects of component-based development and the Web, and are a cornerstone of the Microsoft .NET programming model.</span></span>

<span data-ttu-id="ab36c-249">**Web 服务描述语言 (WSDL)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-249">**Web Services Description Language (WSDL)**</span></span>  
<span data-ttu-id="ab36c-250">一种基于 XML 的语言，它描述为一组操作的终结点对消息的服务。</span><span class="sxs-lookup"><span data-stu-id="ab36c-250">An XML-based language that describes a service as a set of endpoints that operate on messages.</span></span> <span data-ttu-id="ab36c-251">WSDL 文档描述服务协定、 操作约定、 消息协定和客户端必须使用的数据协定与服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="ab36c-251">The WSDL document describes the service contract, operation contracts, message contracts, and data contracts that a client must use to interface with the service.</span></span>

<span data-ttu-id="ab36c-252">**Windows Communication Foundation (WCF)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-252">**Windows Communication Foundation (WCF)**</span></span>  
<span data-ttu-id="ab36c-253">Microsoft 面向服务的通信基础结构。</span><span class="sxs-lookup"><span data-stu-id="ab36c-253">A Microsoft service-oriented communication infrastructure.</span></span> <span data-ttu-id="ab36c-254">该框架本质上是提供客户端与服务编程模型和编程模型，用于消息交换的更精细的控制通道。</span><span class="sxs-lookup"><span data-stu-id="ab36c-254">The framework inherently provides clients with a service programming model and a channel programming model for finer control of message exchanges.</span></span>

<span data-ttu-id="ab36c-255">**WS-元数据交换 (MEX) 终结点**</span><span class="sxs-lookup"><span data-stu-id="ab36c-255">**WS-Metadata Exchange (MEX) endpoint**</span></span>  
<span data-ttu-id="ab36c-256">实现 WCF 服务，如适配器公开的终结点**IMetadataExchange**接口。</span><span class="sxs-lookup"><span data-stu-id="ab36c-256">An endpoint exposed by a WCF service, such as an adapter, that implements the **IMetadataExchange** interface.</span></span> <span data-ttu-id="ab36c-257">WS-元数据交换终结点可以用于检索服务说明 (WSDL) 公开目标系统上的适配器的操作。</span><span class="sxs-lookup"><span data-stu-id="ab36c-257">A WS-Metadata Exchange endpoint can be used to retrieve a service description (WSDL) for operations exposed by an adapter on the target system.</span></span>
  
## <a name="x"></a><span data-ttu-id="ab36c-258">X</span><span class="sxs-lookup"><span data-stu-id="ab36c-258">X</span></span>  
  
<span data-ttu-id="ab36c-259">**XML 架构定义语言 (XSD)**</span><span class="sxs-lookup"><span data-stu-id="ab36c-259">**XML Schema definition language (XSD)**</span></span>  
<span data-ttu-id="ab36c-260">一种架构语言。</span><span class="sxs-lookup"><span data-stu-id="ab36c-260">A schema language.</span></span> <span data-ttu-id="ab36c-261">XML 架构定义元素、 属性和数据类型符合 World Wide Web 联合会 (W3C) XML 架构第 1 部分：XML 架构定义语言的结构建议。</span><span class="sxs-lookup"><span data-stu-id="ab36c-261">An XML Schema defines the elements, attributes, and data types that comply with the World Wide Web Consortium (W3C) XML Schema Part 1: Structures Recommendation for the XML Schema Definition Language.</span></span> <span data-ttu-id="ab36c-262">W3C XML 架构第 2 部分：Datatypes Recommendation 是用于在 XML 架构中定义所使用的数据类型的建议。</span><span class="sxs-lookup"><span data-stu-id="ab36c-262">The W3C XML Schema Part 2: Datatypes Recommendation is the recommendation for defining data types that are used in XML schemas.</span></span> <span data-ttu-id="ab36c-263">XML 架构定义语言，可定义 XML 消息的结构和数据类型。</span><span class="sxs-lookup"><span data-stu-id="ab36c-263">The XML Schema definition language enables you to define the structure and data types for XML messages.</span></span>