---
title: Host Integration Server 中包含的 BizTalk 适配器 |Microsoft Docs
description: 他包含的主机应用程序、 主机文件、 DB2 和 WebSphere MQ 的 BizTalk 适配器概述
author: MandiOhlinger
manager: anneta
ms.date: 10/10/2017
ms.prod: biztalk-server
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.author: mandia
ms.openlocfilehash: 138e49965520505c2f45203836af7172dfd56612
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401538"
---
# <a name="biztalk-adapters-for-host-systems"></a><span data-ttu-id="577ae-103">主机系统的的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="577ae-103">BizTalk adapters for host systems</span></span>


## <a name="biztalk-adapter-for-host-applications"></a><span data-ttu-id="577ae-104">主机应用程序的的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="577ae-104">BizTalk Adapter for Host Applications</span></span>

<span data-ttu-id="577ae-105">用于主机应用程序的 Microsoft BizTalk 适配器用于 BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="577ae-105">The Microsoft BizTalk Adapter for Host Applications is designed for BizTalk Server.</span></span> <span data-ttu-id="577ae-106">它是 Windows-Initiated 处理命令，从而使对现有 IBM 大型机 zSeries （CICS 和 IMS） 或中型机 iSeries (RPG) 服务器程序高效的客户端访问基于技术中 Microsoft 事务集成器 (TI)。</span><span class="sxs-lookup"><span data-stu-id="577ae-106">It is based on technology in Microsoft Transaction Integrator (TI) for Windows-Initiated Processing, which enables efficient client access to existing IBM mainframe zSeries (CICS and IMS) or midrange iSeries (RPG) server programs.</span></span> 

<span data-ttu-id="577ae-107">TI 设计工具集成使用 Visual Studio 和 BizTalk Server 解决方案，使 IT 开发人员能够定义客户端代理时追求高生产力和创建 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="577ae-107">The TI design tools are integrated with Visual Studio and BizTalk Server solutions, enabling IT developers to be highly productive when defining the client proxy and creating the XSD schema.</span></span> <span data-ttu-id="577ae-108">对于 BizTalk Server 管理员，现有的 TI 管理器，Microsoft 管理控制台 (MMC) 管理单元中，已增强，提高可支持性和支持所需的远程 BizTalk Server 解决方案部署方案。</span><span class="sxs-lookup"><span data-stu-id="577ae-108">For BizTalk Server administrators, the existing TI Manager, Microsoft Management Console (MMC) snap-in, has been enhanced to improve supportability and support the required remote BizTalk Server solution deployment scenarios.</span></span>

<span data-ttu-id="577ae-109">请参阅[托管应用程序的 BizTalk 适配器](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="577ae-109">See [BizTalk Adapter for Host Applications](https://msdn.microsoft.com/library/dn148497(BTS.80).aspx).</span></span> 

## <a name="biztalk-adapter-for-host-files"></a><span data-ttu-id="577ae-110">主机文件的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="577ae-110">BizTalk Adapter for Host Files</span></span>
<span data-ttu-id="577ae-111">用于主机文件的 Microsoft BizTalk 适配器是支持 IT 部门能够访问并将信息存储在主机文件系统，包括大型机 zSeries VSAM 数据集和中型机 iSeries 物理文件中集成的高级的数据适配器。</span><span class="sxs-lookup"><span data-stu-id="577ae-111">The Microsoft BizTalk Adapter for Host Files is an advanced data adapter that enables IT organizations to access and integrate information stored in host file systems, including mainframe zSeries VSAM datasets and midrange iSeries physical files.</span></span> 

<span data-ttu-id="577ae-112">BizTalk Server 解决方案中使用的 visual Studio 设计工具用于定义主机程序描述文件，然后将导出为 XSD 的 BizTalk 适配器一起使用的元数据映射。</span><span class="sxs-lookup"><span data-stu-id="577ae-112">Visual Studio design tools are used within a BizTalk Server solution to define a metadata map of the host program-described files, which is then exported as XSD for use with the BizTalk adapter.</span></span> <span data-ttu-id="577ae-113">配置向导集成到 BizTalk Server 管理工具，允许 IT 专业人员定义的动态发送端口和静态和要求响应接收端口，基于一组简化的 SQL 命令 (SELECT、 INSERT、 UPDATE、 DELETE).</span><span class="sxs-lookup"><span data-stu-id="577ae-113">The configuration wizards are integrated into the BizTalk Server administration tools, allowing IT professionals to define dynamic send ports and static and solicit response receive ports, based on a simplified set of SQL commands (SELECT, INSERT, UPDATE, DELETE).</span></span> 

<span data-ttu-id="577ae-114">此 BizTalk 适配器基于 SQL 映射到主机的非关系数据集和成员的主机文件的 Microsoft.NET Framework 数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="577ae-114">This BizTalk adapter is based on the Microsoft .NET Framework Data Provider for Host Files that maps SQL to non-relational host datasets and members.</span></span> <span data-ttu-id="577ae-115">这使得更易于非编程人员读取和写入文件数据源的主机。</span><span class="sxs-lookup"><span data-stu-id="577ae-115">This makes it easier for non-programmers to read and write host file data sources.</span></span>

<span data-ttu-id="577ae-116">请参阅[主机文件的 BizTalk 适配器](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="577ae-116">See [BizTalk Adapter for Host Files](https://msdn.microsoft.com/library/dn150042(BTS.80).aspx).</span></span>

## <a name="biztalk-adapter-for-db2"></a><span data-ttu-id="577ae-117">用于 DB2 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="577ae-117">BizTalk Adapter for DB2</span></span>
<span data-ttu-id="577ae-118">用于 DB2 的 Microsoft BizTalk 适配器是使 IT 专业人员能够访问存储在远程计算平台、 IBM 大型机 zSeries 和中型机 iSeries (DB2/400)，以及 IBM DB2 的主机上的 IBM DB2 数据库服务器中的重要数据的关系数据库适配器通用数据库 (UDB) 在开放平台上。</span><span class="sxs-lookup"><span data-stu-id="577ae-118">The Microsoft BizTalk Adapter for DB2 is a relational database adapter that enables IT professionals to access vital data stored in IBM DB2 database servers on remote host computing platforms, IBM mainframe zSeries and midrange iSeries (DB2/400), and also IBM DB2 Universal Database (UDB) on open platforms.</span></span> 

<span data-ttu-id="577ae-119">使用标准 SQL 命令以及 BizTalk Server 管理工具中内置的配置向导，IT 专业人员可以创建的读取和写入 DB2 而无需进行数据库编程解决方案。</span><span class="sxs-lookup"><span data-stu-id="577ae-119">Using standard SQL commands and a configuration wizard built into BizTalk Server administration tools, IT professionals can create solutions that read and write to DB2 without any need for database programming.</span></span> <span data-ttu-id="577ae-120">DB2 适配器，也不能基于 DB2 的 Microsoft.NET Framework 数据提供程序、 支持范围广泛的功能，包括动态发送端口和静态要求响应接收端口。</span><span class="sxs-lookup"><span data-stu-id="577ae-120">The DB2 adapter, which is based on the Microsoft .NET Framework Data Provider for DB2, supports a broad range of functions, including dynamic send ports, and static and solicit response receive ports.</span></span>

<span data-ttu-id="577ae-121">请参阅[用于 DB2 的 BizTalk 适配器](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="577ae-121">See [BizTalk Adapter for DB2](https://msdn.microsoft.com/library/dn150160(BTS.80).aspx).</span></span>

## <a name="biztalk-adapter-for-websphere-mq"></a><span data-ttu-id="577ae-122">适用于 WebSphere MQ 的 BizTalk 适配器</span><span class="sxs-lookup"><span data-stu-id="577ae-122">BizTalk Adapter for WebSphere MQ</span></span>
<span data-ttu-id="577ae-123">用于 WebSphere MQ （基于客户端） 的 Microsoft BizTalk 适配器使用 IBM WebSphere MQ 客户端 （基本客户端） 和 IBM WebSphere MQ 扩展事务客户端 （扩展客户端） Api 来与远程 MQSeries 队列管理器进行通信。</span><span class="sxs-lookup"><span data-stu-id="577ae-123">The Microsoft BizTalk Adapter for WebSphere MQ (Client-Based) uses IBM WebSphere MQ Client (Base-Client) and IBM WebSphere MQ Extended Transactional Client (Extended-Client) APIs to communicate with remote MQSeries Queue Managers.</span></span> <span data-ttu-id="577ae-124">该适配器，BizTalk Server 可直接与 MQSeries 队列管理器部署在非 Windows 操作系统，而无需部署和管理 WebSphere MQ 服务器的 Windows，若要有效地与交换消息的业务通信企业范围内的应用程序。</span><span class="sxs-lookup"><span data-stu-id="577ae-124">The adapter enables BizTalk Server to communicate directly with MQSeries Queue Managers deployed on non-Windows operating systems, without needing to deploy and manage WebSphere MQ Server for Windows, to efficiently exchange messages with line-of-business applications across the enterprise.</span></span> 

<span data-ttu-id="577ae-125">当用于基本客户端，适配器提供了非事务性消息处理保证消息的发送。</span><span class="sxs-lookup"><span data-stu-id="577ae-125">When used with the Base-Client, the adapter provides non-transactional message processing, guaranteeing only the delivery of messages.</span></span> <span data-ttu-id="577ae-126">它负责在接收端上的应用程序以处理任何重复消息。</span><span class="sxs-lookup"><span data-stu-id="577ae-126">It is the responsibility of the application on the receiving end to handle any duplicate messages.</span></span> <span data-ttu-id="577ae-127">当用于扩展客户端，适配器提供了事务性消息处理，以保证一次-和-仅限-传递消息一次。</span><span class="sxs-lookup"><span data-stu-id="577ae-127">When used with the Extended-Client, the adapter provides transactional message processing to guarantee once-and-only-once delivery of messages.</span></span>

<span data-ttu-id="577ae-128">请参阅[适用于 WebSphere MQ 的 BizTalk 适配器](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx)。</span><span class="sxs-lookup"><span data-stu-id="577ae-128">See [BizTalk Adapter for WebSphere MQ](https://msdn.microsoft.com/library/dn191830(BTS.80).aspx).</span></span>
