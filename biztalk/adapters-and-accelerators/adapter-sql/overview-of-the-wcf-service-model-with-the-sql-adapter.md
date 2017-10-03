---
title: "与 SQL 适配器的 WCF 服务模型概述 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7641bcc7-3845-4914-9b1b-cb86b998ea6d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3afbf1822945f0a47b09a93b3ac3cc2f8ac8653d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="overview-of-the-wcf-service-model-with-the-sql-adapter"></a><span data-ttu-id="800ae-102">与 SQL 适配器的 WCF 服务模型概述</span><span class="sxs-lookup"><span data-stu-id="800ae-102">Overview of the WCF service model with the SQL adapter</span></span>
<span data-ttu-id="800ae-103">[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]公开作为 WCF 服务的 SQL Server 操作。</span><span class="sxs-lookup"><span data-stu-id="800ae-103">The [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] exposes a SQL Server operation as a WCF service.</span></span> <span data-ttu-id="800ae-104">若要对 SQL Server 项目，例如来调用存储的过程中，执行操作你调用上的适配器，后者，反过来，执行 SQL Server 上的操作的操作。</span><span class="sxs-lookup"><span data-stu-id="800ae-104">To perform operations on SQL Server artifacts, for example to invoke a stored procedure, you invoke an operation on the adapter, which, in turn, performs the operation on the SQL Server.</span></span> <span data-ttu-id="800ae-105">你的代码因此充当客户端提供的适配器的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="800ae-105">Your code therefore acts as a client to the WCF service presented by the adapter.</span></span>  
  
 <span data-ttu-id="800ae-106">在[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]服务模型，为.NET 接口，表示客户端和服务之间存在的服务协定和操作表示为此接口上的方法。</span><span class="sxs-lookup"><span data-stu-id="800ae-106">In the [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] service model, the service contract that exists between a client and a service is represented as a .NET interface, and operations are represented as methods on this interface.</span></span> <span data-ttu-id="800ae-107">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]并 WCF 提供使你能够从适配器公开的元数据生成目标操作此接口的工具。</span><span class="sxs-lookup"><span data-stu-id="800ae-107">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] and WCF provide tools that enable you to generate this interface for targeted operations from the metadata that the adapter exposes.</span></span> <span data-ttu-id="800ae-108">这些工具还创建一个可用于调用服务接口中公开的操作的 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="800ae-108">These tools also create a WCF client class that can be used to invoke the operations exposed in the service interface.</span></span> <span data-ttu-id="800ae-109">客户端应用程序可以调用 WCF 客户端类，以调用在适配器上的操作的方法。</span><span class="sxs-lookup"><span data-stu-id="800ae-109">A client application can call the methods of the WCF client class to invoke operations on the adapter.</span></span> <span data-ttu-id="800ae-110">若要实现服务以接收从入站的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，实现接口的入站操作生成。</span><span class="sxs-lookup"><span data-stu-id="800ae-110">To implement a service to receive inbound operations from the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you implement the interface generated for the inbound operations.</span></span>  
  
 <span data-ttu-id="800ae-111">以下部分介绍如何使用 WCF 服务模型来调用操作与 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="800ae-111">The following section explains how to use the WCF service model to invoke operations with a WCF client.</span></span>  
  
## <a name="invoking-operations-on-the-sql-server-with-a-wcf-client"></a><span data-ttu-id="800ae-112">调用 SQL Server 使用 WCF 客户端上的操作</span><span class="sxs-lookup"><span data-stu-id="800ae-112">Invoking Operations on the SQL Server with a WCF Client</span></span>  
 <span data-ttu-id="800ae-113">以使用 WCF 服务模型上调用操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，你必须首先生成的目标操作一个 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="800ae-113">To use the WCF service model to invoke operations on the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must first generate a WCF client class for the target operations.</span></span> <span data-ttu-id="800ae-114">然后，你可以创建 WCF 客户端，此类的实例并调用其方法来执行这些操作的 SQL Server 系统上。</span><span class="sxs-lookup"><span data-stu-id="800ae-114">You can then create an instance of this class, a WCF client, and call its methods to perform these operations on the SQL Server system.</span></span> <span data-ttu-id="800ae-115">本部分提供了一个典型的.NET 适配器客户端应用程序如下所示的概述。</span><span class="sxs-lookup"><span data-stu-id="800ae-115">This section provides an outline of how a typical .NET adapter client application looks like.</span></span> <span data-ttu-id="800ae-116">特定主题中提供了有关如何执行不同的操作使用该适配器的 SQL Server 数据库的详细的说明。</span><span class="sxs-lookup"><span data-stu-id="800ae-116">Detailed explanations on how to perform different operations on the SQL Server database using the adapter are provided in specific topics.</span></span>  
  
#### <a name="to-invoke-operations-on-the-sql-adapter"></a><span data-ttu-id="800ae-117">若要调用的 SQL 适配器上的操作</span><span class="sxs-lookup"><span data-stu-id="800ae-117">To invoke operations on the SQL adapter</span></span>  
  
1.  <span data-ttu-id="800ae-118">生成 WCF 客户端类和帮助程序代码。</span><span class="sxs-lookup"><span data-stu-id="800ae-118">Generate a WCF client class and helper code.</span></span> <span data-ttu-id="800ae-119">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]针对你想要的 SQL Server 数据库项目生成 WCF 客户端类。</span><span class="sxs-lookup"><span data-stu-id="800ae-119">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]to generate a WCF client class targeted at the SQL Server database artifacts with which you want to work.</span></span> <span data-ttu-id="800ae-120">有关如何生成 WCF 客户端的详细信息，请参阅[为 SQL Server 项目生成 WCF 客户端或 WCF 服务协定](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md)。</span><span class="sxs-lookup"><span data-stu-id="800ae-120">For more information about how to generate a WCF client, see [Generate a WCF Client or WCF Service Contract for SQL Server Artifacts](../../adapters-and-accelerators/adapter-sql/generate-a-wcf-client-or-wcf-service-contract-for-sql-server-artifacts.md).</span></span>  
  
2.  <span data-ttu-id="800ae-121">创建 WCF 客户端实例和配置 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="800ae-121">Create a WCF client instance and configure the WCF client.</span></span> <span data-ttu-id="800ae-122">配置 WCF 客户端涉及到指定的绑定和客户端将使用的终结点地址 （连接 URI）。</span><span class="sxs-lookup"><span data-stu-id="800ae-122">Configuring the WCF client involves specifying the binding and endpoint address (connection URI) that the client will use.</span></span> <span data-ttu-id="800ae-123">可以在代码中以强制方式或配置中以声明方式执行此操作。</span><span class="sxs-lookup"><span data-stu-id="800ae-123">You can do this either imperatively in code or declaratively in configuration.</span></span> <span data-ttu-id="800ae-124">下面的代码创建一个 WCF 客户端针对**选择**操作**员工**SQL Server 数据库中的表。</span><span class="sxs-lookup"><span data-stu-id="800ae-124">The following code creates a WCF client that targets the **Select** operation on the **Employee** table in a SQL Server database.</span></span> <span data-ttu-id="800ae-125">它还将设置 SQL Server 数据库的凭据。</span><span class="sxs-lookup"><span data-stu-id="800ae-125">It also sets the credentials for the SQL Server database.</span></span> <span data-ttu-id="800ae-126">WCF 客户端从配置初始化。</span><span class="sxs-lookup"><span data-stu-id="800ae-126">The WCF client is initialized from configuration.</span></span>  
  
    ```  
    TableOp_dbo_EmployeeClient client = new TableOp_dbo_EmployeeClient("SqlAdapterBinding_TableOp_dbo_Employee"); //picking the binding and address from the app.config  
  
    client.ClientCredentials.UserName.UserName = "myuser";  
    client.ClientCredentials.UserName.Password = "mypassword";  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="800ae-127">可以在代码中指定的客户端绑定和终结点地址，也可以将其声明 app.config 配置文件中。</span><span class="sxs-lookup"><span data-stu-id="800ae-127">You can either specify the client binding and endpoint address in the code or declare it in the app.config configuration file.</span></span> <span data-ttu-id="800ae-128">前面的代码段使用后者。</span><span class="sxs-lookup"><span data-stu-id="800ae-128">The preceding code snippet uses the latter.</span></span> <span data-ttu-id="800ae-129">有关如何使用任一方法的详细信息，请参阅[为 SQL 适配器配置客户端绑定](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="800ae-129">For more information on how to use either approaches, see [Configure a Client Binding for the SQL Adapter](../../adapters-and-accelerators/adapter-sql/configure-a-client-binding-for-the-sql-adapter.md).</span></span>  
  
3.  <span data-ttu-id="800ae-130">打开 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="800ae-130">Open the WCF client.</span></span>  
  
    ```  
    client.Open();  
    ```  
  
4.  <span data-ttu-id="800ae-131">调用在上一步中创建 WCF 客户端以执行 SQL server 数据库上的选择操作的方法。</span><span class="sxs-lookup"><span data-stu-id="800ae-131">Invoke methods on the WCF client created in preceding step to perform a Select operation on the SQL server database.</span></span> <span data-ttu-id="800ae-132">下面的代码调用 WCF 客户端以调用在对 SQL Server 数据库表的 SELECT 语句的选择方法。</span><span class="sxs-lookup"><span data-stu-id="800ae-132">The following code invokes the Select method of the WCF client to invoke the SELECT statement on a SQL Server database table.</span></span>  
  
    ```  
    client.Select("*", "where [Name] = ‘John Smith’");  
    ```  
  
5.  <span data-ttu-id="800ae-133">关闭 WCF 客户端。</span><span class="sxs-lookup"><span data-stu-id="800ae-133">Close the WCF client.</span></span>  
  
    ```  
    client.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="800ae-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="800ae-134">See Also</span></span>  
[<span data-ttu-id="800ae-135">开发 SQL 应用程序使用 WCF 服务模型</span><span class="sxs-lookup"><span data-stu-id="800ae-135">Develop SQL applications using the WCF Service model</span></span>](../../adapters-and-accelerators/adapter-sql/develop-sql-applications-using-the-wcf-service-model.md)