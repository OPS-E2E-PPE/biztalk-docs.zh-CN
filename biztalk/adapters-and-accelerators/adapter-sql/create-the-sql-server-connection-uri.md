---
title: 创建 SQL Server 连接 URI |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 688e2215-a4d8-4f55-a37c-7d91c3de080f
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c58812b9fc3404b9922cf05c84717f3c95e05435
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007574"
---
# <a name="create-the-sql-server-connection-uri"></a><span data-ttu-id="7627a-102">创建 SQL Server 连接 URI</span><span class="sxs-lookup"><span data-stu-id="7627a-102">Create the SQL Server connection URI</span></span>
<span data-ttu-id="7627a-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]连接 URI 包含适配器用来建立与 SQL Server 数据库的连接属性。</span><span class="sxs-lookup"><span data-stu-id="7627a-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] connection URI contains properties that the adapter uses to establish a connection to the SQL Server database.</span></span> <span data-ttu-id="7627a-104">本主题介绍 SQL Server 连接 URI，并提供指向其他主题的解释如何在不同的编程方案中指定一个 URI。</span><span class="sxs-lookup"><span data-stu-id="7627a-104">This topic provides information about the SQL Server connection URI, and provides links to other topics that explain how to specify a URI in different programming scenarios.</span></span>  
  
##  <a name="FailoverPartner"></a> <span data-ttu-id="7627a-105">SQL 适配器的连接 URI</span><span class="sxs-lookup"><span data-stu-id="7627a-105">The Connection URI for the SQL Adapter</span></span>  
 <span data-ttu-id="7627a-106">典型的终结点地址 URI 在 WCF 中表示为： `scheme://hostinfoparams?query_string`，其中：</span><span class="sxs-lookup"><span data-stu-id="7627a-106">A typical endpoint address URI in WCF is represented as: `scheme://hostinfoparams?query_string`, where:</span></span>  
  
- <span data-ttu-id="7627a-107">方案为方案名称。</span><span class="sxs-lookup"><span data-stu-id="7627a-107">scheme is the scheme name.</span></span>  
  
- <span data-ttu-id="7627a-108">hostinfoparams 是建立与主机; 的连接所需的信息例如，服务器名称。</span><span class="sxs-lookup"><span data-stu-id="7627a-108">hostinfoparams is information required to establish the connection to the host; for example, a server name.</span></span>  
  
- <span data-ttu-id="7627a-109">query_string 是由问号 （？） 分隔的参数的可选名称值集合。</span><span class="sxs-lookup"><span data-stu-id="7627a-109">query_string is an optional name-value collection of parameters delimited by a question mark (?).</span></span>  
  
  <span data-ttu-id="7627a-110">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]连接 URI 遵循此基本格式和实现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7627a-110">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] connection URI adheres to this basic format and is implemented as follows:</span></span>  
  
```  
  
mssql://[Server_Name[:Portno]]/[Database_Instance_Name]/[Database_Name]?FailoverPartner=[Partner_Server_Name]&InboundId=[Inbound_ID]  
```  
  
 <span data-ttu-id="7627a-111">其中，`mssql`是 SQL Server 连接 URI 的方案。</span><span class="sxs-lookup"><span data-stu-id="7627a-111">where, `mssql` is the scheme for the SQL Server connection URI.</span></span>  
  
 <span data-ttu-id="7627a-112">下表介绍了连接 URI 中包含的属性。</span><span class="sxs-lookup"><span data-stu-id="7627a-112">The following table explains the properties contained in the connection URI.</span></span>  
  
|<span data-ttu-id="7627a-113">连接 URI 属性</span><span class="sxs-lookup"><span data-stu-id="7627a-113">Connection URI Property</span></span>|<span data-ttu-id="7627a-114">类别</span><span class="sxs-lookup"><span data-stu-id="7627a-114">Category</span></span>|<span data-ttu-id="7627a-115">Description</span><span class="sxs-lookup"><span data-stu-id="7627a-115">Description</span></span>|  
|-----------------------------|--------------|-----------------|  
|<span data-ttu-id="7627a-116">[SERVER_NAME]</span><span class="sxs-lookup"><span data-stu-id="7627a-116">[SERVER_NAME]</span></span>|<span data-ttu-id="7627a-117">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="7627a-117">hostinfoparams</span></span>|<span data-ttu-id="7627a-118">在其安装 SQL Server 的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="7627a-118">Name of the server on which SQL Server is installed.</span></span> <span data-ttu-id="7627a-119">如果不指定一个值，适配器将假定为"localhost"的服务器名称，并建立与本地服务器上的 SQL Server 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="7627a-119">If you do not specify a value, the adapter assumes the server name as “localhost” and establishes a connection with the SQL Server database on the local server.</span></span>|  
|<span data-ttu-id="7627a-120">[PORTNO]</span><span class="sxs-lookup"><span data-stu-id="7627a-120">[PORTNO]</span></span>|<span data-ttu-id="7627a-121">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="7627a-121">hostinfoparams</span></span>|<span data-ttu-id="7627a-122">建立连接的端口号。</span><span class="sxs-lookup"><span data-stu-id="7627a-122">The port number where the connection is established.</span></span> <span data-ttu-id="7627a-123">如果不指定一个值，适配器将连接通过默认端口。</span><span class="sxs-lookup"><span data-stu-id="7627a-123">If you do not specify a value, the adapter connects through the default port.</span></span>|  
|<span data-ttu-id="7627a-124">[DATABASE_INSTANCE_NAME]</span><span class="sxs-lookup"><span data-stu-id="7627a-124">[DATABASE_INSTANCE_NAME]</span></span>|<span data-ttu-id="7627a-125">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="7627a-125">hostinfoparams</span></span>|<span data-ttu-id="7627a-126">要连接到的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="7627a-126">Name of the SQL Server instance to connect to.</span></span> <span data-ttu-id="7627a-127">如果不指定一个值，该适配器连接到默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="7627a-127">If you do not specify a value, the adapter connects to the default database instance.</span></span>|  
|<span data-ttu-id="7627a-128">[DATABASE_NAME]</span><span class="sxs-lookup"><span data-stu-id="7627a-128">[DATABASE_NAME]</span></span>|<span data-ttu-id="7627a-129">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="7627a-129">hostinfoparams</span></span>|<span data-ttu-id="7627a-130">要连接到的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="7627a-130">Name of the database to connect to.</span></span> <span data-ttu-id="7627a-131">如果不指定一个值，该适配器连接到的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="7627a-131">If you do not specify a value, the adapter connects to the default database.</span></span>|  
|<span data-ttu-id="7627a-132">[PARTNER_SERVER_NAME]</span><span class="sxs-lookup"><span data-stu-id="7627a-132">[PARTNER_SERVER_NAME]</span></span>|<span data-ttu-id="7627a-133">query_string</span><span class="sxs-lookup"><span data-stu-id="7627a-133">query_string</span></span>|<span data-ttu-id="7627a-134">若要连接到主 SQL Server 数据库的故障转移 SQL Server 数据库的名称不可用。</span><span class="sxs-lookup"><span data-stu-id="7627a-134">Name of the failover SQL Server database to connect to if the primary SQL Server database is not available.</span></span> <span data-ttu-id="7627a-135">有关高可用性的 SQL Server 方面的详细信息，请参阅[SQL Server 中的数据库镜像](https://msdn.microsoft.com/library/5h52hef8.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7627a-135">For more information about high availability with respect to SQL Server, see [Database Mirroring in SQL Server](https://msdn.microsoft.com/library/5h52hef8.aspx).</span></span>|  
|<span data-ttu-id="7627a-136">[INBOUND_ID]</span><span class="sxs-lookup"><span data-stu-id="7627a-136">[INBOUND_ID]</span></span>|<span data-ttu-id="7627a-137">query_string</span><span class="sxs-lookup"><span data-stu-id="7627a-137">query_string</span></span>|<span data-ttu-id="7627a-138">您将添加到连接 URI，使其成为唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="7627a-138">An identifier that you add to the connection URI to make it unique.</span></span> <span data-ttu-id="7627a-139">如果你想要生成的元数据，必须提供此连接参数**TypedPolling**的入站操作。</span><span class="sxs-lookup"><span data-stu-id="7627a-139">You must provide this connection parameter if you want to generate metadata for the **TypedPolling** inbound operation.</span></span> <span data-ttu-id="7627a-140">此外，在 BizTalk 应用程序中，如果有多个接收位置轮询同一数据库，入站的 ID 进行连接 URI 唯一的从而使适配器客户端可以接收来自同一个数据库上不同的轮询消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="7627a-140">Also, in a BizTalk application, if you have multiple receive locations polling the same database, the inbound ID makes the connection URI unique, thereby enabling adapter clients to receive polling messages from the same database on different receive locations.</span></span> <span data-ttu-id="7627a-141">有关详细信息，请参阅[接收轮询消息跨多个接收端口从使用 BizTalk Server 的 SQL](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="7627a-141">For more information, see [Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="7627a-142">有关这些连接字符串属性的详细信息，请参阅[SqlConnection.ConnectionString 属性](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7627a-142">For more information about these connection string properties, see [SqlConnection.ConnectionString Property](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx).</span></span>
  
## <a name="sql-server-credentials-and-the-connection-uri"></a><span data-ttu-id="7627a-143">SQL Server 凭据和连接 URI</span><span class="sxs-lookup"><span data-stu-id="7627a-143">SQL Server Credentials and the Connection URI</span></span>  
 <span data-ttu-id="7627a-144">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持在连接 URI 中指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="7627a-144">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support specifying credentials in the connection URI.</span></span> <span data-ttu-id="7627a-145">详细了解在使用的应用程序中指定凭据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="7627a-145">For more information about specifying credentials in your applications that use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Secure your SQL applications](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).</span></span>  
  
## <a name="using-special-characters-in-the-connection-uri"></a><span data-ttu-id="7627a-146">在连接 URI 中使用特殊字符</span><span class="sxs-lookup"><span data-stu-id="7627a-146">Using Special Characters in the Connection URI</span></span>  
 <span data-ttu-id="7627a-147">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持指定连接 URI，其中含有特殊字符的任何参数值。</span><span class="sxs-lookup"><span data-stu-id="7627a-147">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support specifying a connection URI that has special characters for any of the parameter values.</span></span> <span data-ttu-id="7627a-148">如果连接参数值包含特殊字符，请确保执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="7627a-148">If the connection parameter values contain special characters, make sure you do one of the following:</span></span>  
  
- <span data-ttu-id="7627a-149">如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，则必须指定其作为-处于**URI 属性**选项卡上，即，而无需使用任何转义符。</span><span class="sxs-lookup"><span data-stu-id="7627a-149">If you are specifying the URI in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] using [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="7627a-150">如果指定的 URI 中直接**配置 URI**字段和连接参数包含特殊字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="7627a-150">If you specify the URI directly in the **Configure a URI** field and the connection parameters contain special characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
   <span data-ttu-id="7627a-151">例如，如果连接 URI 的名称的参数`sql server`，则必须指定其作为`sql%20server`。</span><span class="sxs-lookup"><span data-stu-id="7627a-151">For example, if the connection URI has a parameter with name `sql server`, you must specify it as `sql%20server`.</span></span>  
  
- <span data-ttu-id="7627a-152">如果创建一个发送时指定的 URI 或接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中和连接参数包含特殊字符，则必须指定连接参数使用正确的转义字符。</span><span class="sxs-lookup"><span data-stu-id="7627a-152">If you are specifying the URI while creating a send or receive port in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, and the connection parameters contain special characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
## <a name="using-the-connection-uri-to-connect-to-the-sql-server-database"></a><span data-ttu-id="7627a-153">使用的连接 URI 连接到 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="7627a-153">Using the Connection URI to Connect to the SQL Server Database</span></span>  
 <span data-ttu-id="7627a-154">下面是示例连接 URI 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7627a-154">The following is a sample connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
```  
mssql://sql_server/sql_server_instance//  
```  
  
 <span data-ttu-id="7627a-155">在上述示例中，"sql_server"是计算机的"sql server 实例"是计算机的要连接到的数据库实例的名称而在其安装 SQL Server 的名称。</span><span class="sxs-lookup"><span data-stu-id="7627a-155">In the preceding example, “sql_server” is the name of the computer on which SQL Server is installed whereas “sql_server_instance” is the name of the database instance to connect to.</span></span> <span data-ttu-id="7627a-156">由于不指定任何数据库名称，因此适配器将连接到的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="7627a-156">Because no database name is specified, the adapter will connect to the default database.</span></span>  
  
 <span data-ttu-id="7627a-157">以下是一个连接 URI 相同的计算机安装 SQL Server 数据库的示例[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7627a-157">The following is an example of a connection URI where the SQL Server database is installed on the same computer as the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="7627a-158">在此示例中，该适配器连接到数据库"my_database"本地计算机上的"sql server 实例"数据库实例。</span><span class="sxs-lookup"><span data-stu-id="7627a-158">In this example, the adapter connects to the database “my_database” for the “sql_server_instance” database instance on the local computer.</span></span>  
  
```  
mssql://localhost/sql_server_instance/my_database/  
```  
  
 <span data-ttu-id="7627a-159">在此示例中，适配器连接到本地计算机上运行的默认实例的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="7627a-159">In this example, the adapter connects to the default database for the default instance running on the local computer.</span></span>  
  
```  
mssql://localhost///  
```  
  
 <span data-ttu-id="7627a-160">有关如何指定连接到 SQL Server 数据库的信息时您：</span><span class="sxs-lookup"><span data-stu-id="7627a-160">For information about how to specify a connection to the SQL Server database when you:</span></span>  
  
- <span data-ttu-id="7627a-161">使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到 SQL Server 在 Visual Studio 中使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7627a-161">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], see [Connect to SQL Server in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="7627a-162">配置发送端口或接收端口 （位置） 中的 BizTalk Server 解决方案，请参阅[手动配置与 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7627a-162">Configure a send port or receive port (location) in a BizTalk Server solution, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span>
  
- <span data-ttu-id="7627a-163">编程解决方案中使用 WCF 通道模型，请参阅[创建一个通道，使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7627a-163">Use the WCF channel model in a programming solution, see [Create a channel using the SQL adapter](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md).</span></span>  
  
- <span data-ttu-id="7627a-164">编程解决方案中使用 WCF 服务模型，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7627a-164">Use the WCF service model in a programming solution, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7627a-165">请参阅</span><span class="sxs-lookup"><span data-stu-id="7627a-165">See Also</span></span>  
[<span data-ttu-id="7627a-166">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="7627a-166">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)