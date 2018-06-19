---
title: BizTalk 适配器附带 Host Integration Server |Microsoft 文档
description: 概述用于承载应用程序、 主机文件、 DB2 和 WebSphere MQ BizTalk 适配器附带他
author: MandiOhlinger
manager: anneta
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.author: mandia
ms.openlocfilehash: 26f2bf48c9a1268aace041776ff3895c8f3b3aa5
ms.sourcegitcommit: 75d35f6f230f0846c29a4b146c6d5b074e60b13c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/11/2017
ms.locfileid: "22645177"
---
# <a name="biztalk-adapters-for-host-systems"></a><span data-ttu-id="8e76b-103">主机系统的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="8e76b-103">BizTalk adapters for host systems</span></span>


## <a name="biztalk-adapter-for-host-applications"></a><span data-ttu-id="8e76b-104">用于承载应用程序的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="8e76b-104">BizTalk Adapter for Host Applications</span></span>

<span data-ttu-id="8e76b-105">Microsoft BizTalk 适配器的主机应用程序旨在用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="8e76b-105">The Microsoft BizTalk Adapter for Host Applications is designed for BizTalk Server.</span></span> <span data-ttu-id="8e76b-106">它基于技术中 Microsoft 事务系统集成商 (TI) Windows-Initiated 处理，从而实现到现有 IBM 大型机 zSeries （CICS 和即时消息） 或的中端 iSeries (RPG) 的服务器程序的有效客户端访问。</span><span class="sxs-lookup"><span data-stu-id="8e76b-106">It is based on technology in Microsoft Transaction Integrator (TI) for Windows-Initiated Processing, which enables efficient client access to existing IBM mainframe zSeries (CICS and IMS) or midrange iSeries (RPG) server programs.</span></span> 

<span data-ttu-id="8e76b-107">与 Visual Studio 和 BizTalk Server 解决方案，使 IT 开发人员可以定义客户端代理时追求高生产力和创建 XSD 架构集成 TI 设计工具。</span><span class="sxs-lookup"><span data-stu-id="8e76b-107">The TI design tools are integrated with Visual Studio and BizTalk Server solutions, enabling IT developers to be highly productive when defining the client proxy and creating the XSD schema.</span></span> <span data-ttu-id="8e76b-108">BizTalk Server administrators、 Microsoft 管理控制台 (MMC) 管理单元中，现有的 TI Manager 得到了增强以改进可支持性和支持的所需的远程 BizTalk Server 解决方案部署方案功能。</span><span class="sxs-lookup"><span data-stu-id="8e76b-108">For BizTalk Server administrators, the existing TI Manager, Microsoft Management Console (MMC) snap-in, has been enhanced to improve supportability and support the required remote BizTalk Server solution deployment scenarios.</span></span>

<span data-ttu-id="8e76b-109">请参阅[用于承载应用程序的 BizTalk Adapter](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="8e76b-109">See [BizTalk Adapter for Host Applications](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx).</span></span> 

## <a name="biztalk-adapter-for-host-files"></a><span data-ttu-id="8e76b-110">BizTalk 适配器的主机文件</span><span class="sxs-lookup"><span data-stu-id="8e76b-110">BizTalk Adapter for Host Files</span></span>
<span data-ttu-id="8e76b-111">Microsoft BizTalk 适配器的主机文件是高级的数据适配器，使 IT 部门能够访问并将集成存储在主机文件系统，包括主 zSeries 框架 VSAM 数据集和的中端 iSeries 物理文件中的信息。</span><span class="sxs-lookup"><span data-stu-id="8e76b-111">The Microsoft BizTalk Adapter for Host Files is an advanced data adapter that enables IT organizations to access and integrate information stored in host file systems, including mainframe zSeries VSAM datasets and midrange iSeries physical files.</span></span> 

<span data-ttu-id="8e76b-112">BizTalk Server 解决方案中使用的 visual Studio 设计工具用于定义元数据的代码图的主机程序描述文件中，它用于 BizTalk 适配器然后导出为 XSD。</span><span class="sxs-lookup"><span data-stu-id="8e76b-112">Visual Studio design tools are used within a BizTalk Server solution to define a metadata map of the host program-described files, which is then exported as XSD for use with the BizTalk adapter.</span></span> <span data-ttu-id="8e76b-113">向导集成到 BizTalk Server 管理工具的配置，并允许 IT 专业人员可以定义动态发送端口和静态并要求响应接收端口，基于一组简化的 SQL 命令 （SELECT、 INSERT、 更新、 删除).</span><span class="sxs-lookup"><span data-stu-id="8e76b-113">The configuration wizards are integrated into the BizTalk Server administration tools, allowing IT professionals to define dynamic send ports and static and solicit response receive ports, based on a simplified set of SQL commands (SELECT, INSERT, UPDATE, DELETE).</span></span> 

<span data-ttu-id="8e76b-114">此 BizTalk 适配器基于映射到非关系主机数据集和成员的 SQL 的主机文件的 Microsoft.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="8e76b-114">This BizTalk adapter is based on the Microsoft .NET Framework Data Provider for Host Files that maps SQL to non-relational host datasets and members.</span></span> <span data-ttu-id="8e76b-115">这简化非程序员可以读取和写入文件数据源的主机。</span><span class="sxs-lookup"><span data-stu-id="8e76b-115">This makes it easier for non-programmers to read and write host file data sources.</span></span>

<span data-ttu-id="8e76b-116">请参阅[用于主机文件的 BizTalk Adapter](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="8e76b-116">See [BizTalk Adapter for Host Files](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx).</span></span>

## <a name="biztalk-adapter-for-db2"></a><span data-ttu-id="8e76b-117">用于 DB2 的 BizTalk Adapter</span><span class="sxs-lookup"><span data-stu-id="8e76b-117">BizTalk Adapter for DB2</span></span>
<span data-ttu-id="8e76b-118">Microsoft BizTalk Adapter for DB2 是使 IT 专业人员访问计算平台时，IBM 大型机 zSeries 中端 iSeries (DB2/400)，并还 IBM DB2 的远程主机上的 IBM DB2 数据库服务器中存储的重要数据的关系数据库适配器通用数据库 (UDB) 在打开的平台上。</span><span class="sxs-lookup"><span data-stu-id="8e76b-118">The Microsoft BizTalk Adapter for DB2 is a relational database adapter that enables IT professionals to access vital data stored in IBM DB2 database servers on remote host computing platforms, IBM mainframe zSeries and midrange iSeries (DB2/400), and also IBM DB2 Universal Database (UDB) on open platforms.</span></span> 

<span data-ttu-id="8e76b-119">使用标准的 SQL 命令和内置于 BizTalk Server 管理工具配置向导，IT 专业人员可以创建用于读取和写入到 DB2 数据库编程对任何需要的解决方案。</span><span class="sxs-lookup"><span data-stu-id="8e76b-119">Using standard SQL commands and a configuration wizard built into BizTalk Server administration tools, IT professionals can create solutions that read and write to DB2 without any need for database programming.</span></span> <span data-ttu-id="8e76b-120">将基于 DB2 的 Microsoft.NET Framework 数据提供程序、 支持广泛的功能，包括动态发送端口和静态和请求作出响应的 DB2 适配器接收端口。</span><span class="sxs-lookup"><span data-stu-id="8e76b-120">The DB2 adapter, which is based on the Microsoft .NET Framework Data Provider for DB2, supports a broad range of functions, including dynamic send ports, and static and solicit response receive ports.</span></span>

<span data-ttu-id="8e76b-121">请参阅[用于 DB2 的 BizTalk Adapter](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="8e76b-121">See [BizTalk Adapter for DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx).</span></span>

## <a name="biztalk-adapter-for-websphere-mq"></a><span data-ttu-id="8e76b-122">适用于 WebSphere MQ 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="8e76b-122">BizTalk Adapter for WebSphere MQ</span></span>
<span data-ttu-id="8e76b-123">（基于客户端） 的 WebSphere MQ Microsoft BizTalk 适配器使用 IBM WebSphere MQ 客户端 （基本客户端） 和 IBM WebSphere MQ 扩展事务客户端 （扩展客户端） Api 与远程 MQSeries 队列管理器进行通信。</span><span class="sxs-lookup"><span data-stu-id="8e76b-123">The Microsoft BizTalk Adapter for WebSphere MQ (Client-Based) uses IBM WebSphere MQ Client (Base-Client) and IBM WebSphere MQ Extended Transactional Client (Extended-Client) APIs to communicate with remote MQSeries Queue Managers.</span></span> <span data-ttu-id="8e76b-124">适配器支持 BizTalk Server 直接与 MQSeries 队列管理器部署在非 Windows 操作系统，而无需部署和管理 WebSphere MQ 用于 Windows 的服务器，能够有效地与交换消息的业务通信在企业范围内的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8e76b-124">The adapter enables BizTalk Server to communicate directly with MQSeries Queue Managers deployed on non-Windows operating systems, without needing to deploy and manage WebSphere MQ Server for Windows, to efficiently exchange messages with line-of-business applications across the enterprise.</span></span> 

<span data-ttu-id="8e76b-125">对基本客户端使用时，适配器提供了非事务性消息处理保证消息的传递。</span><span class="sxs-lookup"><span data-stu-id="8e76b-125">When used with the Base-Client, the adapter provides non-transactional message processing, guaranteeing only the delivery of messages.</span></span> <span data-ttu-id="8e76b-126">它负责接收端上的应用程序，以处理任何重复的消息。</span><span class="sxs-lookup"><span data-stu-id="8e76b-126">It is the responsibility of the application on the receiving end to handle any duplicate messages.</span></span> <span data-ttu-id="8e76b-127">对扩展客户端使用时，适配器提供事务性消息处理，以保证一次和-仅-一次传递消息。</span><span class="sxs-lookup"><span data-stu-id="8e76b-127">When used with the Extended-Client, the adapter provides transactional message processing to guarantee once-and-only-once delivery of messages.</span></span>

<span data-ttu-id="8e76b-128">请参阅[WebSphere MQ 的 BizTalk Adapter](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="8e76b-128">See [BizTalk Adapter for WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx).</span></span>
