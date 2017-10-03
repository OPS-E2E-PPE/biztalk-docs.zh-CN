---
title: "使用连接到 Oracle 数据库适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- connection string
- uniform resource identifier
- Oracle database, connecting to
- URI
- connection URI
ms.assetid: 5d5598e5-aba0-4c73-8e97-9156475b93c4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01b04a615d0b0b8cd83b9ed7516cd096b2c85a54
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="connect-to-oracle-database-using-the-adapter"></a><span data-ttu-id="6b122-102">使用连接到 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="6b122-102">Connect to Oracle Database using the adapter</span></span>
<span data-ttu-id="6b122-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] ODP.NET 11.1.0.7 用于连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="6b122-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] uses ODP.NET 11.1.0.7 to connect to the Oracle database.</span></span> <span data-ttu-id="6b122-104">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]要求适配器客户端提供连接字符串，调用统一资源标识符 (URI)，以连接到 Oracle 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="6b122-104">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] requires adapter clients to provide a connection string, called the connection Uniform Resource Identifier (URI), to connect to the Oracle database.</span></span> <span data-ttu-id="6b122-105">在内部，[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将 URI 映射到一个数据库连接字符串以连接到 Oracle 数据库。</span><span class="sxs-lookup"><span data-stu-id="6b122-105">Internally, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] maps the URI to a database connection string to connect to the Oracle database.</span></span> <span data-ttu-id="6b122-106">通过连接 URI 适配器客户端可以指定要连接到外部系统的连接参数。</span><span class="sxs-lookup"><span data-stu-id="6b122-106">With a connection URI, adapter clients can specify connection parameters to connect to an external system.</span></span>  
  
 <span data-ttu-id="6b122-107">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]允许适配器客户端连接到 Oracle 数据库在以下两种方法：</span><span class="sxs-lookup"><span data-stu-id="6b122-107">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] enables adapter clients to connect to the Oracle database in the following two ways:</span></span>  
  
-   <span data-ttu-id="6b122-108">**使用 tnsnames.ora**： 连接适配器客户端提供的 URI 包含仅在 tnsnames.ora 文件中指定的 net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="6b122-108">**Using tnsnames.ora**: The connection URI provided by the adapter client contains only the net service name specified in the tnsnames.ora file.</span></span> <span data-ttu-id="6b122-109">适配器从 tnsnames.ora 文件中的 net 服务名称条目提取如服务器名称、 服务名称和端口号的连接参数。</span><span class="sxs-lookup"><span data-stu-id="6b122-109">The adapter extracts the connection parameters such as server name, service name, and port number from the net service name entry in the tnsnames.ora file.</span></span> <span data-ttu-id="6b122-110">若要使用此方法，必须配置运行 Oracle 客户端的计算机为 tnsnames.ora 文件中包括 Oracle 数据库的 net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="6b122-110">To use this approach, the computer running the Oracle client must be configured to include the net service name for the Oracle database in the tnsnames.ora file.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6b122-111">由于 Oracle 客户端存在的限制， **DataSourceName**中的参数 （net 服务名称）[配置 Oracle 数据库适配器的连接 URI](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md)不能包含超过 39 个字符，如果你在事务中执行操作。</span><span class="sxs-lookup"><span data-stu-id="6b122-111">Due to an Oracle Client limitation, the **DataSourceName** parameter (net service name) in the [Configure the connection URI for the Oracle Database adapter](../../adapters-and-accelerators/adapter-oracle-database/configure-the-connection-uri-for-the-oracle-database-adapter.md) cannot contain more than 39 characters if you are performing operations in a transaction.</span></span> <span data-ttu-id="6b122-112">因此，请确保为指定的值**DataSourceName**参数是否小于或等于 39 个字符如果你将在事务中执行操作。</span><span class="sxs-lookup"><span data-stu-id="6b122-112">Therefore, make sure that the value specified for the **DataSourceName** parameter is less than or equal to 39 characters if you will be performing operations in a transaction.</span></span>  
  
-   <span data-ttu-id="6b122-113">**而无需使用 tnsnames.ora**： 连接 URI 的适配器客户端提供包含如服务器名称、 服务名称和端口号的连接参数。</span><span class="sxs-lookup"><span data-stu-id="6b122-113">**Without using tnsnames.ora**: The connection URI provided by the adapter clients contains the connection parameters such as server name, service name, and port number.</span></span> <span data-ttu-id="6b122-114">在这种情况下，在 tnsnames.ora 文件中或实际 tnsnames.ora 文件本身，net 服务名称不必存在于客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="6b122-114">In this case, the net service name in the tnsnames.ora file, or the actual tnsnames.ora file itself, does not need to be present on the client computer.</span></span> <span data-ttu-id="6b122-115">如果有大量的用户连接到 Oracle 数据库中您的组织，并添加/更新服务器不会导致手动添加/更新每个客户端计算机上的 tnsnames.ora 文件中的连接详细信息，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="6b122-115">This is helpful when you have a large number of users connecting to the Oracle database in your organization, and adding/updating servers does not lead to manually adding/updating the connection details in the tnsnames.ora file on every client computer.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="6b122-116">如果你在事务中执行操作，则不支持这种模式的连接。</span><span class="sxs-lookup"><span data-stu-id="6b122-116">This mode of connectivity is not supported if you are performing operations in a transaction.</span></span> <span data-ttu-id="6b122-117">这是因为 Oracle 客户端的限制。</span><span class="sxs-lookup"><span data-stu-id="6b122-117">This is due to a limitation of Oracle Client.</span></span>  
  
 <span data-ttu-id="6b122-118">有关连接到 Oracle 数据库的详细信息，请参阅[创建与 Oracle 数据库的连接](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="6b122-118">For more information about connecting to the Oracle database, see [Create a connection to the Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md).</span></span>  
  
 <span data-ttu-id="6b122-119">请确保您遵守安全指导原则建立与 Oracle 数据库的连接时。</span><span class="sxs-lookup"><span data-stu-id="6b122-119">Make sure you comply with the security guidelines when establishing a connection with the Oracle database.</span></span> <span data-ttu-id="6b122-120">有关安全指导原则的详细信息，请参阅[保护 Oracle 数据库应用程序](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="6b122-120">For more information about security guidelines, see [Secure your Oracle Database applications](../../adapters-and-accelerators/adapter-oracle-database/secure-your-oracle-database-applications.md).</span></span>  
  
## <a name="windows-authentication"></a><span data-ttu-id="6b122-121">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="6b122-121">Windows Authentication</span></span>  
 <span data-ttu-id="6b122-122">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]连接到 Oracle 数据库时，支持 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="6b122-122">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports Windows Authentication while connecting to the Oracle database.</span></span> <span data-ttu-id="6b122-123">使用 Windows 身份验证适配器客户端可以确定用户的标识基于的 Windows 登录凭据，而且可以利用 Windows 环境的内置安全性。</span><span class="sxs-lookup"><span data-stu-id="6b122-123">With Windows Authentication, the adapter clients can determine a user’s identity based on Windows logon credentials, and can leverage the built-in security of the Windows environment.</span></span> <span data-ttu-id="6b122-124">有关使用 Windows 身份验证连接到 Oracle 数据库的信息，请参阅[连接到 Oracle 数据库使用 Windows 身份验证](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)。</span><span class="sxs-lookup"><span data-stu-id="6b122-124">For information about connecting to the Oracle database by using Windows Authentication, see [Connect to the Oracle Database Using Windows Authentication](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b122-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6b122-125">See Also</span></span>  
 [<span data-ttu-id="6b122-126">用于 Oracle 数据库的 BizTalk Adapter 的概述</span><span class="sxs-lookup"><span data-stu-id="6b122-126">Overview of BizTalk Adapter for Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/overview-of-biztalk-adapter-for-oracle-database.md)