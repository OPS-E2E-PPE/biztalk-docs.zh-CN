---
title: 开发 SQL 应用程序使用 WCF 服务模型 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3ecfd6f-9144-4e41-a4b8-0c768a6ac254
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 645b783ad23d79b4f6be177f6d38287e62abab1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223205"
---
# <a name="develop-sql-applications-using-the-wcf-service-model"></a><span data-ttu-id="1d867-102">开发 SQL 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="1d867-102">Develop SQL applications using the WCF Service model</span></span>
[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]<span data-ttu-id="1d867-103">提供作为编程模型的 WCF 通道的替代方法调用 WCF 服务模型编程模型。</span><span class="sxs-lookup"><span data-stu-id="1d867-103"> provides a programming model called the WCF service model, as an alternative to the WCF channel programming model.</span></span>  
  
 <span data-ttu-id="1d867-104">WCF 服务模型使用熟悉的.NET 范例来隐藏通过通道交换 SOAP 消息的复杂性。</span><span class="sxs-lookup"><span data-stu-id="1d867-104">The WCF service model uses familiar .NET paradigms to hide the complexities of exchanging SOAP messages over a channel.</span></span> <span data-ttu-id="1d867-105">服务模型完成这种简化读取到内存的整个的 SOAP 消息，然后将信息复制到.NET 数据结构。</span><span class="sxs-lookup"><span data-stu-id="1d867-105">The service model accomplishes this simplification by reading the entire SOAP message into memory before copying the information into .NET data structures.</span></span> <span data-ttu-id="1d867-106">加载到内存长消息，但是，可能不可行对于某些应用程序。</span><span class="sxs-lookup"><span data-stu-id="1d867-106">Loading long messages into memory, however, may not be practical for some applications.</span></span> <span data-ttu-id="1d867-107">在这些情况下，开发人员应使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="1d867-107">In these cases, developers should use the WCF channel model.</span></span> <span data-ttu-id="1d867-108">有关使用 WCF 通道模型的详细信息，请参阅[开发 SQL 应用程序使用 WCF 通道模型](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="1d867-108">For more information about using the WCF channel model, see [Develop SQL applications using the WCF Channel Model](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-channel-model.md).</span></span>  
  
 <span data-ttu-id="1d867-109">在最低级别，[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]提供了 WCF 通道模型，在其中客户端调用服务上的操作通过在客户端和服务终结点之间建立信道交换 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="1d867-109">At the lowest level, [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] presents the WCF channel model, in which clients invoke operations on a service by exchanging SOAP messages over a channel established between client and service endpoints.</span></span> <span data-ttu-id="1d867-110">WCF 通道模型公开数据类型和方法，您可以直接对 WCF 通道体系结构进行操作。</span><span class="sxs-lookup"><span data-stu-id="1d867-110">The WCF channel model exposes data types and methods that enable you to operate directly on the WCF channel architecture.</span></span> <span data-ttu-id="1d867-111">WCF 通道模型为您提供通过你创建的 SOAP 消息的内容和方式这两个应用程序的直接控制和[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]使用它们。</span><span class="sxs-lookup"><span data-stu-id="1d867-111">The WCF channel model provides you with direct control over the contents of the SOAP messages you create and over the way both your application and the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] consume them.</span></span> <span data-ttu-id="1d867-112">但是，创建格式正确的 SOAP 消息在通道上发送和验证返回的答复消息可以是详细、 更严格的任务。</span><span class="sxs-lookup"><span data-stu-id="1d867-112">However, creating well-formed SOAP messages to send over a channel and validating the reply messages returned can be a detailed and exacting task.</span></span>  
  
 <span data-ttu-id="1d867-113">WCF 服务模型使用代理类来调用针对目标服务的操作或从客户端接收操作。</span><span class="sxs-lookup"><span data-stu-id="1d867-113">The WCF service model uses proxy classes to invoke operations on a target service or to receive operations from a client.</span></span> <span data-ttu-id="1d867-114">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开 SQL Server 数据库作为 WCF 服务可以在其调用操作。</span><span class="sxs-lookup"><span data-stu-id="1d867-114">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes the SQL Server database as a WCF service on which you can invoke operations.</span></span>  
  
-   <span data-ttu-id="1d867-115">用于调用操作将针对目标服务的代理类调用 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="1d867-115">The proxy class that is used to invoke operations on a target service is called a WCF client class.</span></span> <span data-ttu-id="1d867-116">此类模型作为使用强类型参数的.NET 方法由服务公开的操作。</span><span class="sxs-lookup"><span data-stu-id="1d867-116">This class models the operations exposed by a service as .NET methods with strongly-typed parameters.</span></span> <span data-ttu-id="1d867-117">通过使用 WCF 服务模型，你可以调用公开的运算[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]为 WCF 客户端上的.NET 方法。</span><span class="sxs-lookup"><span data-stu-id="1d867-117">By using the WCF service model, you can invoke the operations exposed by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] as .NET methods on the WCF client.</span></span> <span data-ttu-id="1d867-118">有关 WCF 客户端的详细信息，请参阅[WCF 客户端概述](https://msdn.microsoft.com/library/ms735103.aspx)。</span><span class="sxs-lookup"><span data-stu-id="1d867-118">For more information about WCF clients, see [WCF Client Overview](https://msdn.microsoft.com/library/ms735103.aspx).</span></span>
  
 <span data-ttu-id="1d867-119">可以使用以下工具之一生成 WCF 客户端类和关联的服务元数据中的帮助器代码，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]公开：</span><span class="sxs-lookup"><span data-stu-id="1d867-119">You can use either of the following tools to generate a WCF client class and associated helper code from the service metadata that the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] exposes:</span></span>  
  
-   <span data-ttu-id="1d867-120">**ServiceModel 元数据实用工具 (svcutil.exe)**，其中附带了 WCF。</span><span class="sxs-lookup"><span data-stu-id="1d867-120">**The ServiceModel Metadata Utility Tool (svcutil.exe)**, which ships with WCF.</span></span>  
  
-   <span data-ttu-id="1d867-121">**[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]** ，其中附带[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]并与集成[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]设计体验。</span><span class="sxs-lookup"><span data-stu-id="1d867-121">**The [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]**, which ships with [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and is integrated with the [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] design experience.</span></span> <span data-ttu-id="1d867-122">此工具提供的标准的 Microsoft Windows 界面提供功能强大的浏览和搜索适配器公开的操作的功能。</span><span class="sxs-lookup"><span data-stu-id="1d867-122">This tool presents a standard Microsoft Windows interface that provides powerful browsing and searching capabilities on operations that the adapter exposes.</span></span> <span data-ttu-id="1d867-123">有关如何生成一个 WCF 客户端应用程序的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="1d867-123">For more information about how to generate a WCF client application, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
     <span data-ttu-id="1d867-124">本部分中的主题包含信息、 过程和示例来帮助你创建并使用 WCF 服务模型来开发应用程序使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1d867-124">The topics in this section contain information, procedures, and examples to help you create and use the WCF service model to develop applications by using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1d867-125">本节内容</span><span class="sxs-lookup"><span data-stu-id="1d867-125">In This Section</span></span>  
  
-   [<span data-ttu-id="1d867-126">与 SQL 适配器的 WCF 服务模型概述</span><span class="sxs-lookup"><span data-stu-id="1d867-126">Overview of the WCF service model with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/overview-of-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="1d867-127">元数据和 WCF 服务模型与 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="1d867-127">Metadata and the WCF Service Model with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/metadata-and-the-wcf-service-model-with-the-sql-adapter.md)  
  
-   [<span data-ttu-id="1d867-128">为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定</span><span class="sxs-lookup"><span data-stu-id="1d867-128">Generate a WCF Client or WCF Service Contract for SQL Server Artifacts</span></span>](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)  
  
-   [<span data-ttu-id="1d867-129">为该 SQL 适配器配置客户端绑定</span><span class="sxs-lookup"><span data-stu-id="1d867-129">Configure a Client Binding for the SQL Adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)  
  
-   [<span data-ttu-id="1d867-130">插入、 更新、 删除或选择接口表和视图使用 WCF 服务模型的操作</span><span class="sxs-lookup"><span data-stu-id="1d867-130">Insert, update, delete, or select operations on interface tables and views using the WCF service model</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/insert-update-delete-select-on-interface-tables-and-views-with-a-wcf-service.md)  
  
-   [<span data-ttu-id="1d867-131">在上运行操作表和视图使用 SQL 使用 WCF 服务模型中的大型数据类型</span><span class="sxs-lookup"><span data-stu-id="1d867-131">Run Operations on Tables and Views with Large Data Types in SQL using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/read-or-update-tables-and-views-with-large-data-types-in-sql-with-a-wcf-service.md)  
  
-   [<span data-ttu-id="1d867-132">调用中使用 WCF 服务模型的 SQL 存储过程</span><span class="sxs-lookup"><span data-stu-id="1d867-132">Invoke Stored Procedures in SQL using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-stored-procedures-in-sql-using-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="1d867-133">使用 WCF 服务模型调用 SQL Server 中的标量函数</span><span class="sxs-lookup"><span data-stu-id="1d867-133">Invoke Scalar Functions in SQL Server by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-scalar-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="1d867-134">使用 WCF 服务模型调用 SQL Server 中的表值函数</span><span class="sxs-lookup"><span data-stu-id="1d867-134">Invoke Table-Valued Functions in SQL Server by Using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/invoke-table-valued-functions-in-sql-server-by-using-the-wcf-service-model.md)  
  
-   [<span data-ttu-id="1d867-135">ExecuteReader、 ExecuteScalar 或 ExecuteNonQuery SQL 使用 WCF 服务模型中的操作</span><span class="sxs-lookup"><span data-stu-id="1d867-135">ExecuteReader, ExecuteScalar, or ExecuteNonQuery operations in SQL using WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/executereader-executescalar-executenonquery-in-sql-using-wcf-service-model.md)  
  
-   [<span data-ttu-id="1d867-136">使用 WCF 服务模型的 SQL 适配器的轮询 SQL Server</span><span class="sxs-lookup"><span data-stu-id="1d867-136">Poll SQL Server using the SQL Adapter with WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/poll-sql-server-using-the-sql-adapter-with-wcf-service-model.md)  
  
-   [<span data-ttu-id="1d867-137">从使用 WCF 服务模型的 SQL 接收查询通知</span><span class="sxs-lookup"><span data-stu-id="1d867-137">Receive Query Notifications from SQL using the WCF Service Model</span></span>](../../adapters-and-accelerators/adapter-sql/receive-query-notifications-from-sql-using-the-wcf-service-model.md)  
  
## <a name="see-also"></a><span data-ttu-id="1d867-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d867-138">See Also</span></span>  
[<span data-ttu-id="1d867-139">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="1d867-139">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)