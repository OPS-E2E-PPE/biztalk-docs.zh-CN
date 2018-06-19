---
title: 连接到 SQL Server 使用适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 727d73e6-fb84-48ce-ae72-5de70dcae8b8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c9b837aa4e0bc0a815434307b10d249dccf54d70
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222133"
---
# <a name="connect-to-sql-server-using-the-adapter"></a><span data-ttu-id="32824-102">连接到 SQL Server 使用适配器</span><span class="sxs-lookup"><span data-stu-id="32824-102">Connect to SQL Server using the adapter</span></span>
<span data-ttu-id="32824-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI)，以连接到 SQL Server 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="32824-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] requires adapter clients to provide a connection string, called the connection Uniform Resource Identifier (URI), to connect to the SQL Server database.</span></span> <span data-ttu-id="32824-104">在内部，[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]将 URI 映射到一个数据库连接字符串以连接到 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="32824-104">Internally, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] maps the URI to a database connection string to connect to the SQL Server database.</span></span> <span data-ttu-id="32824-105">通过连接 URI 适配器客户端可以指定要连接到外部系统的连接参数。</span><span class="sxs-lookup"><span data-stu-id="32824-105">With a connection URI, adapter clients can specify connection parameters to connect to an external system.</span></span> <span data-ttu-id="32824-106">有关连接 URI 的详细信息，请参阅[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)。</span><span class="sxs-lookup"><span data-stu-id="32824-106">For more information about the connection URI, see [Create the SQL Server Connection URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md).</span></span>  
  
 <span data-ttu-id="32824-107">在连接 URI，主 SQL Server 数据库不可用时要连接到的备用计算机上，还可以指定故障转移 SQL Server 数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="32824-107">In the connection URI, you can also specify the name of a failover SQL Server database on a standby computer to connect to if the primary SQL Server database is not available.</span></span> <span data-ttu-id="32824-108">故障转移 SQL Server 数据库必须是主 SQL Server 数据库的镜像。</span><span class="sxs-lookup"><span data-stu-id="32824-108">The failover SQL Server database must be a mirror of the primary SQL Server database.</span></span> <span data-ttu-id="32824-109">使用可选参数，FailoverPartner，连接 URI 中的指定故障转移 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="32824-109">The failover SQL Server database is specified using an optional parameter, FailoverPartner, in the connection URI.</span></span> <span data-ttu-id="32824-110">提供故障转移 SQL Server 数据库可确保高可用性和数据冗余。</span><span class="sxs-lookup"><span data-stu-id="32824-110">Providing a failover SQL Server database ensures high availability and data redundancy.</span></span> <span data-ttu-id="32824-111">有关与 SQL Server 的高可用性的详细信息，请参阅[SQL Server 中的数据库镜像](https://msdn.microsoft.com/library/5h52hef8.aspx)。</span><span class="sxs-lookup"><span data-stu-id="32824-111">For more information about high availability with respect to SQL Server, see [Database Mirroring in SQL Server](https://msdn.microsoft.com/library/5h52hef8.aspx).</span></span>
  
 <span data-ttu-id="32824-112">请确保您遵守安全指导原则建立与 SQL Server 数据库的连接时。</span><span class="sxs-lookup"><span data-stu-id="32824-112">Make sure you comply with the security guidelines when establishing a connection with the SQL Server database.</span></span> <span data-ttu-id="32824-113">有关安全指导原则的详细信息，请参阅[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="32824-113">For more information about security guidelines, see [Secure your SQL applications](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32824-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32824-114">See Also</span></span>  
 <span data-ttu-id="32824-115">[用于 SQL Server 的 BizTalk Adapter 的概述](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="32824-115">[Overview of BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md) </span></span>  
 [<span data-ttu-id="32824-116">创建与 SQL Server 的连接</span><span class="sxs-lookup"><span data-stu-id="32824-116">Create a Connection to SQL Server</span></span>](../../adapters-and-accelerators/adapter-sql/create-a-connection-to-sql-server.md)