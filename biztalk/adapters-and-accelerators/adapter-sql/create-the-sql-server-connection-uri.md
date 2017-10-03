---
title: "创建 SQL Server 连接 URI |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 688e2215-a4d8-4f55-a37c-7d91c3de080f
caps.latest.revision: "24"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f31b6d6919924d3bb4bb1ac6c817c3f3b3d77dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="create-the-sql-server-connection-uri"></a><span data-ttu-id="ac4cc-102">创建 SQL Server 连接 URI</span><span class="sxs-lookup"><span data-stu-id="ac4cc-102">Create the SQL Server connection URI</span></span>
<span data-ttu-id="ac4cc-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]连接 URI 包含适配器用于建立与 SQL Server 数据库的连接的属性。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] connection URI contains properties that the adapter uses to establish a connection to the SQL Server database.</span></span> <span data-ttu-id="ac4cc-104">本主题提供有关 SQL Server 连接 URI 的信息，并提供指向其他主题的说明如何在不同的编程方案中指定一个 URI。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-104">This topic provides information about the SQL Server connection URI, and provides links to other topics that explain how to specify a URI in different programming scenarios.</span></span>  
  
##  <span data-ttu-id="ac4cc-105"><a name="FailoverPartner"></a>SQL 适配器的连接 URI</span><span class="sxs-lookup"><span data-stu-id="ac4cc-105"><a name="FailoverPartner"></a> The Connection URI for the SQL Adapter</span></span>  
 <span data-ttu-id="ac4cc-106">典型的终结点地址 URI 在 WCF 中表示为： `scheme://hostinfoparams?query_string`，其中：</span><span class="sxs-lookup"><span data-stu-id="ac4cc-106">A typical endpoint address URI in WCF is represented as: `scheme://hostinfoparams?query_string`, where:</span></span>  
  
-   <span data-ttu-id="ac4cc-107">方案是方案名称。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-107">scheme is the scheme name.</span></span>  
  
-   <span data-ttu-id="ac4cc-108">hostinfoparams 是建立与主机; 的连接所需的信息例如，服务器名称。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-108">hostinfoparams is information required to establish the connection to the host; for example, a server name.</span></span>  
  
-   <span data-ttu-id="ac4cc-109">query_string 是可选的由问号 （？） 分隔的参数名称 / 值集合。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-109">query_string is an optional name-value collection of parameters delimited by a question mark (?).</span></span>  
  
 <span data-ttu-id="ac4cc-110">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]连接 URI 遵循此基本格式和实现，如下所示：</span><span class="sxs-lookup"><span data-stu-id="ac4cc-110">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] connection URI adheres to this basic format and is implemented as follows:</span></span>  
  
```  
  
mssql://[Server_Name[:Portno]]/[Database_Instance_Name]/[Database_Name]?FailoverPartner=[Partner_Server_Name]&InboundId=[Inbound_ID]  
```  
  
 <span data-ttu-id="ac4cc-111">其中，`mssql`是 SQL Server 连接 URI 的方案。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-111">where, `mssql` is the scheme for the SQL Server connection URI.</span></span>  
  
 <span data-ttu-id="ac4cc-112">下表介绍了连接 URI 中包含的属性。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-112">The following table explains the properties contained in the connection URI.</span></span>  
  
|<span data-ttu-id="ac4cc-113">连接 URI 属性</span><span class="sxs-lookup"><span data-stu-id="ac4cc-113">Connection URI Property</span></span>|<span data-ttu-id="ac4cc-114">类别</span><span class="sxs-lookup"><span data-stu-id="ac4cc-114">Category</span></span>|<span data-ttu-id="ac4cc-115">Description</span><span class="sxs-lookup"><span data-stu-id="ac4cc-115">Description</span></span>|  
|-----------------------------|--------------|-----------------|  
|<span data-ttu-id="ac4cc-116">[SERVER_NAME]</span><span class="sxs-lookup"><span data-stu-id="ac4cc-116">[SERVER_NAME]</span></span>|<span data-ttu-id="ac4cc-117">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="ac4cc-117">hostinfoparams</span></span>|<span data-ttu-id="ac4cc-118">在其上安装 SQL Server 的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-118">Name of the server on which SQL Server is installed.</span></span> <span data-ttu-id="ac4cc-119">如果未指定一个值，该适配器假定为"localhost"的服务器名称，并建立与本地服务器上的 SQL Server 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-119">If you do not specify a value, the adapter assumes the server name as “localhost” and establishes a connection with the SQL Server database on the local server.</span></span>|  
|<span data-ttu-id="ac4cc-120">[PORTNO]</span><span class="sxs-lookup"><span data-stu-id="ac4cc-120">[PORTNO]</span></span>|<span data-ttu-id="ac4cc-121">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="ac4cc-121">hostinfoparams</span></span>|<span data-ttu-id="ac4cc-122">建立连接的端口号。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-122">The port number where the connection is established.</span></span> <span data-ttu-id="ac4cc-123">如果未指定一个值，该适配器将连接通过默认端口。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-123">If you do not specify a value, the adapter connects through the default port.</span></span>|  
|<span data-ttu-id="ac4cc-124">[DATABASE_INSTANCE_NAME]</span><span class="sxs-lookup"><span data-stu-id="ac4cc-124">[DATABASE_INSTANCE_NAME]</span></span>|<span data-ttu-id="ac4cc-125">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="ac4cc-125">hostinfoparams</span></span>|<span data-ttu-id="ac4cc-126">要连接到的 SQL Server 实例的名称。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-126">Name of the SQL Server instance to connect to.</span></span> <span data-ttu-id="ac4cc-127">如果未指定一个值，该适配器将连接到默认数据库实例。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-127">If you do not specify a value, the adapter connects to the default database instance.</span></span>|  
|<span data-ttu-id="ac4cc-128">[DATABASE_NAME]</span><span class="sxs-lookup"><span data-stu-id="ac4cc-128">[DATABASE_NAME]</span></span>|<span data-ttu-id="ac4cc-129">hostinfoparams</span><span class="sxs-lookup"><span data-stu-id="ac4cc-129">hostinfoparams</span></span>|<span data-ttu-id="ac4cc-130">要连接到的数据库的名称。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-130">Name of the database to connect to.</span></span> <span data-ttu-id="ac4cc-131">如果未指定一个值，该适配器将连接到的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-131">If you do not specify a value, the adapter connects to the default database.</span></span>|  
|<span data-ttu-id="ac4cc-132">[PARTNER_SERVER_NAME]</span><span class="sxs-lookup"><span data-stu-id="ac4cc-132">[PARTNER_SERVER_NAME]</span></span>|<span data-ttu-id="ac4cc-133">query_string</span><span class="sxs-lookup"><span data-stu-id="ac4cc-133">query_string</span></span>|<span data-ttu-id="ac4cc-134">要连接到如果主 SQL Server 数据库的故障转移 SQL Server 数据库的名称不可用。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-134">Name of the failover SQL Server database to connect to if the primary SQL Server database is not available.</span></span> <span data-ttu-id="ac4cc-135">有关与 SQL Server 的高可用性的详细信息，请参阅[SQL Server 中的数据库镜像](https://msdn.microsoft.com/library/5h52hef8.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-135">For more information about high availability with respect to SQL Server, see [Database Mirroring in SQL Server](https://msdn.microsoft.com/library/5h52hef8.aspx).</span></span>|  
|<span data-ttu-id="ac4cc-136">[INBOUND_ID]</span><span class="sxs-lookup"><span data-stu-id="ac4cc-136">[INBOUND_ID]</span></span>|<span data-ttu-id="ac4cc-137">query_string</span><span class="sxs-lookup"><span data-stu-id="ac4cc-137">query_string</span></span>|<span data-ttu-id="ac4cc-138">你将添加到连接 URI，以使其唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-138">An identifier that you add to the connection URI to make it unique.</span></span> <span data-ttu-id="ac4cc-139">如果你想要生成的元数据，必须提供此连接参数**TypedPolling**入站操作。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-139">You must provide this connection parameter if you want to generate metadata for the **TypedPolling** inbound operation.</span></span> <span data-ttu-id="ac4cc-140">此外，在 BizTalk 应用程序中，如果你有多个接收位置轮询同一数据库中，入站的 ID 进行连接 URI 唯一的从而支持适配器客户端接收来自上不同的同一数据库的轮询消息接收位置。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-140">Also, in a BizTalk application, if you have multiple receive locations polling the same database, the inbound ID makes the connection URI unique, thereby enabling adapter clients to receive polling messages from the same database on different receive locations.</span></span> <span data-ttu-id="ac4cc-141">有关详细信息，请参阅[接收轮询消息跨多个接收端口从 SQL 使用 BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-141">For more information, see [Receive Polling Messages Across Multiple Receive Ports from SQL using BizTalk Server](../../adapters-and-accelerators/adapter-sql/receive-polling-messages-across-multiple-receive-ports-from-sql-using-biztalk.md).</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="ac4cc-142">有关这些连接字符串属性的详细信息，请参阅[SqlConnection.ConnectionString 属性](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx)。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-142">For more information about these connection string properties, see [SqlConnection.ConnectionString Property](https://msdn.microsoft.com/library/system.data.sqlclient.sqlconnection.connectionstring.aspx).</span></span>
  
## <a name="sql-server-credentials-and-the-connection-uri"></a><span data-ttu-id="ac4cc-143">SQL Server 凭据和连接 URI</span><span class="sxs-lookup"><span data-stu-id="ac4cc-143">SQL Server Credentials and the Connection URI</span></span>  
 <span data-ttu-id="ac4cc-144">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持连接 URI 中指定的凭据。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-144">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support specifying credentials in the connection URI.</span></span> <span data-ttu-id="ac4cc-145">有关在使用的应用程序中指定凭据的详细信息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-145">For more information about specifying credentials in your applications that use the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], see [Secure your SQL applications](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md).</span></span>  
  
## <a name="using-special-characters-in-the-connection-uri"></a><span data-ttu-id="ac4cc-146">在连接 URI 中使用特殊字符</span><span class="sxs-lookup"><span data-stu-id="ac4cc-146">Using Special Characters in the Connection URI</span></span>  
 <span data-ttu-id="ac4cc-147">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]不支持指定的连接具有任何参数值的特殊字符的 URI。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-147">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not support specifying a connection URI that has special characters for any of the parameter values.</span></span> <span data-ttu-id="ac4cc-148">连接参数值包含特殊字符，请确保执行下列任一操作：</span><span class="sxs-lookup"><span data-stu-id="ac4cc-148">If the connection parameter values contain special characters, make sure you do one of the following:</span></span>  
  
-   <span data-ttu-id="ac4cc-149">如果在指定的 URI 中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，你必须指定它们作为-处于**URI 属性**选项卡上，即，而无需使用任何转义字符。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-149">If you are specifying the URI in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] using [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], you must specify them as-is in the **URI Properties** tab, that is, without using any escape characters.</span></span> <span data-ttu-id="ac4cc-150">如果你指定直接在 URI**配置 URI**字段和连接参数包含特殊字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-150">If you specify the URI directly in the **Configure a URI** field and the connection parameters contain special characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
     <span data-ttu-id="ac4cc-151">例如，如果连接 URI 具有名称的参数`sql server`，你必须指定其作为`sql%20server`。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-151">For example, if the connection URI has a parameter with name `sql server`, you must specify it as `sql%20server`.</span></span>  
  
-   <span data-ttu-id="ac4cc-152">如果你创建一个发送时指定的 URI，或接收中的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，和连接参数包含特殊字符，则必须指定连接参数使用适当的转义字符。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-152">If you are specifying the URI while creating a send or receive port in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, and the connection parameters contain special characters, you must specify the connection parameters using proper escape characters.</span></span>  
  
## <a name="using-the-connection-uri-to-connect-to-the-sql-server-database"></a><span data-ttu-id="ac4cc-153">连接 URI 用于连接到 SQL Server 数据库</span><span class="sxs-lookup"><span data-stu-id="ac4cc-153">Using the Connection URI to Connect to the SQL Server Database</span></span>  
 <span data-ttu-id="ac4cc-154">下面是示例连接 URI 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-154">The following is a sample connection URI for the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
```  
mssql://sql_server/sql_server_instance//  
```  
  
 <span data-ttu-id="ac4cc-155">在前面的示例中，"sql_server"是计算机的"sql server 实例"是计算机的要连接到的数据库实例的名称而在其安装 SQL Server 的名称。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-155">In the preceding example, “sql_server” is the name of the computer on which SQL Server is installed whereas “sql_server_instance” is the name of the database instance to connect to.</span></span> <span data-ttu-id="ac4cc-156">由于未不指定任何数据库名称，该适配器将连接到的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-156">Because no database name is specified, the adapter will connect to the default database.</span></span>  
  
 <span data-ttu-id="ac4cc-157">以下是一个连接 URI，将 SQL Server 数据库安装在同一台计算机的示例[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-157">The following is an example of a connection URI where the SQL Server database is installed on the same computer as the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="ac4cc-158">在此示例中，适配器连接到数据库"my_database"本地计算机上的"sql server 实例"数据库实例。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-158">In this example, the adapter connects to the database “my_database” for the “sql_server_instance” database instance on the local computer.</span></span>  
  
```  
mssql://localhost/sql_server_instance/my_database/  
```  
  
 <span data-ttu-id="ac4cc-159">在此示例中，适配器用来连接到本地计算机上运行的默认实例的默认数据库。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-159">In this example, the adapter connects to the default database for the default instance running on the local computer.</span></span>  
  
```  
mssql://localhost///  
```  
  
 <span data-ttu-id="ac4cc-160">有关如何指定与 SQL Server 的连接信息数据库时你：</span><span class="sxs-lookup"><span data-stu-id="ac4cc-160">For information about how to specify a connection to the SQL Server database when you:</span></span>  
  
-   <span data-ttu-id="ac4cc-161">使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]，请参阅[连接到使用 SQL 适配器的 Visual Studio 中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-161">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] or the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)], see [Connect to SQL Server in Visual Studio using the SQL adapter](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-sql-adapter.md).</span></span>  
  
-   <span data-ttu-id="ac4cc-162">配置发送端口或接收 BizTalk Server 解决方案中的端口 （位置），请参阅[手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-162">Configure a send port or receive port (location) in a BizTalk Server solution, see [Manually configure a physical port binding to the SQL adapter](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md).</span></span>
  
-   <span data-ttu-id="ac4cc-163">使用编程解决方案中的 WCF 通道模型，请参阅[创建一个通道，使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-163">Use the WCF channel model in a programming solution, see [Create a channel using the SQL adapter](../../adapters-and-accelerators/adapter-sql/create-a-channel-using-the-sql-adapter.md).</span></span>  
  
-   <span data-ttu-id="ac4cc-164">使用 WCF 服务模型编程解决方案中，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="ac4cc-164">Use the WCF service model in a programming solution, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac4cc-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ac4cc-165">See Also</span></span>  
[<span data-ttu-id="ac4cc-166">开发 SQL 应用程序</span><span class="sxs-lookup"><span data-stu-id="ac4cc-166">Develop your SQL applications</span></span>](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)