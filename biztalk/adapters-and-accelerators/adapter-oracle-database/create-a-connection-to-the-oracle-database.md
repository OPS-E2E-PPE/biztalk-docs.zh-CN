---
title: 创建与 Oracle 数据库的连接 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, connecting to the Oracle Database
ms.assetid: 95f7905a-abad-4841-85c4-62cf0cc1e044
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c79af51280879e1cf6c72053a42822cd24fae68e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988454"
---
# <a name="create-a-connection-to-the-oracle-database"></a><span data-ttu-id="bbf2f-102">创建与 Oracle 数据库的连接</span><span class="sxs-lookup"><span data-stu-id="bbf2f-102">Create a connection to the Oracle Database</span></span>
<span data-ttu-id="bbf2f-103">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]是[!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)]自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-103">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] is a [!INCLUDE[firstref_btsWinCommFoundation](../../includes/firstref-btswincommfoundation-md.md)] custom binding.</span></span> <span data-ttu-id="bbf2f-104">在这种情况下，它支持到 Oracle 数据库通过 WCF 终结点地址的通信。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-104">As such, it enables communication to an Oracle database through a WCF endpoint address.</span></span> <span data-ttu-id="bbf2f-105">在 WCF 中，终结点地址通常表示为统一资源标识符 (URI)，用于标识该服务的网络位置。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-105">In WCF, the endpoint address is typically expressed as a Uniform Resource Identifier (URI), which identifies the network location of the service.</span></span> <span data-ttu-id="bbf2f-106">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]表达此位置作为一个连接 URI，其中包含属性的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]用于建立与 Oracle 数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-106">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] expresses this location as a connection URI, which contains properties that the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] uses to establish a connection to the Oracle database.</span></span>  
  
 <span data-ttu-id="bbf2f-107">必须指定连接 URI 时您：</span><span class="sxs-lookup"><span data-stu-id="bbf2f-107">You must specify a connection URI when you:</span></span>  
  
- <span data-ttu-id="bbf2f-108">创建通道工厂或通道侦听器使用[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]通道模型或创建使用 WCF 客户端或服务主机时[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-108">Create a channel factory or a channel listener using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] channel model or when you create a WCF client or service host using the [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model.</span></span>  
  
- <span data-ttu-id="bbf2f-109">创建中的一个物理端口绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-109">Create a physical port binding in a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="bbf2f-110">使用[!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)]生成 WCF 客户端类或 WCF 服务接口[!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)]服务模型解决方案。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-110">Use the [!INCLUDE[addadapterservreflong](../../includes/addadapterservreflong-md.md)] to generate a WCF client class or WCF service interface for a [!INCLUDE[nextref_btsWinCommFoundation](../../includes/nextref-btswincommfoundation-md.md)] service model solution.</span></span>  
  
- <span data-ttu-id="bbf2f-111">使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]来检索从消息架构[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]解决方案。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-111">Use the [!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)] to retrieve message schemas from the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] for a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] solution.</span></span>  
  
- <span data-ttu-id="bbf2f-112">使用 ServiceModel 元数据实用工具工具 (svcutil.exe) 生成 WCF 客户端类或 WCF 服务模型解决方案的 WCF 服务接口。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-112">Use the ServiceModel Metadata Utility tool (svcutil.exe) to generate a WCF client class or WCF service interface for a WCF service model solution.</span></span>  
  
  <span data-ttu-id="bbf2f-113">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持建立与 Oracle 数据库的连接的两种方法：</span><span class="sxs-lookup"><span data-stu-id="bbf2f-113">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports two ways of establishing a connection to the Oracle database:</span></span>  
  
- <span data-ttu-id="bbf2f-114">**使用 tnsnames.ora**。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-114">**Using tnsnames.ora**.</span></span> <span data-ttu-id="bbf2f-115">在此方法中，连接由适配器客户端提供的 URI 包含 tnsnames.ora 文件中指定的网络服务名称。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-115">In this approach, the connection URI provided by the adapter client contains only the net service name specified in the tnsnames.ora file.</span></span> <span data-ttu-id="bbf2f-116">适配器提取连接参数，如服务器名称、 服务名称、 端口号，从该文件中的 net 服务名称条目等。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-116">The adapter extracts the connection parameters such as server name, service name, port no, etc. from the net service name entry in the file.</span></span> <span data-ttu-id="bbf2f-117">若要使用此方法，运行 Oracle 客户端的计算机必须配置为在 tnsnames.ora 文件中包含的 Oracle 数据库的 net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-117">To use this approach, the computer running the Oracle client must be configured to include the net service name for the Oracle database in the tnsnames.ora file.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="bbf2f-118">由于 Oracle 客户端限制， **DataSourceName**中的参数 （net 服务名称）[创建 Oracle 数据库连接 URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)不能包含超过 39 个字符，如果您正在执行在事务中的操作。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-118">Due to an Oracle Client limitation, the **DataSourceName** parameter (net service name) in the [Create the Oracle Database connection URI](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md) cannot contain more than 39 characters if you are performing operations in a transaction.</span></span> <span data-ttu-id="bbf2f-119">因此，请确保为指定的值**DataSourceName**参数是小于或等于 39 个字符如果您将在事务中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-119">Therefore, make sure that the value specified for the **DataSourceName** parameter is less than or equal to 39 characters if you will be performing operations in a transaction.</span></span>  
  
- <span data-ttu-id="bbf2f-120">**而无需使用 tnsnames.ora**。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-120">**Without using tnsnames.ora**.</span></span> <span data-ttu-id="bbf2f-121">在此方法时，适配器客户端指定直接在连接 URI 中的连接参数。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-121">In this approach, the adapter clients specify the connection parameters directly in the connection URI.</span></span> <span data-ttu-id="bbf2f-122">这不需要网络服务名称必须包含在客户端计算机上的 tnsnames.ora 文件中。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-122">This does not require the net service name to be present in the tnsnames.ora file on the client computer.</span></span> <span data-ttu-id="bbf2f-123">这种方法甚至不需要在客户端计算机上显示的 tnsname.ora 文件。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-123">This approach does not even require the tnsname.ora file to be present on the client computer.</span></span>  
  
  > [!IMPORTANT]
  >  <span data-ttu-id="bbf2f-124">如果你在事务中执行操作，则不支持这种模式的连接。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-124">This mode of connectivity is not supported if you are performing operations in a transaction.</span></span> <span data-ttu-id="bbf2f-125">这是由于 Oracle 客户端的限制。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-125">This is due to a limitation of Oracle Client.</span></span>  
  
  <span data-ttu-id="bbf2f-126">在本部分中的主题介绍如何建立之间的连接[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]和，它可以提供与 Oracle 数据库：</span><span class="sxs-lookup"><span data-stu-id="bbf2f-126">The topics in this section describe how to establish a connection between the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] and the Oracle database by providing you with:</span></span>  
  
- <span data-ttu-id="bbf2f-127">有关配置 Oracle 客户端的信息。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-127">Information about configuring the Oracle client.</span></span>  
  
- <span data-ttu-id="bbf2f-128">有关连接属性和 Oracle 连接 URI 的结构信息。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-128">Information about the connection properties and the structure of the Oracle connection URI.</span></span>  
  
- <span data-ttu-id="bbf2f-129">演示如何通过使用建立的连接的主题的链接[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-129">Links to topics that show how to establish a connection by using the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
- <span data-ttu-id="bbf2f-130">有关连接到 Oracle 数据库使用 Windows 身份验证的信息。</span><span class="sxs-lookup"><span data-stu-id="bbf2f-130">Information about connecting to the Oracle database using Windows Authentication.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbf2f-131">本节内容</span><span class="sxs-lookup"><span data-stu-id="bbf2f-131">In This Section</span></span>  
  
-   [<span data-ttu-id="bbf2f-132">配置 Oracle 数据库适配器的 Oracle 客户端</span><span class="sxs-lookup"><span data-stu-id="bbf2f-132">Configure the Oracle Client for the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/configure-the-oracle-client-for-the-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="bbf2f-133">创建 Oracle 数据库连接 URI</span><span class="sxs-lookup"><span data-stu-id="bbf2f-133">Create the Oracle Database connection URI</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-the-oracle-database-connection-uri.md)  
  
-   [<span data-ttu-id="bbf2f-134">连接到 Oracle 数据库使用 Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="bbf2f-134">Connect to the Oracle Database Using Windows Authentication</span></span>](../../adapters-and-accelerators/adapter-oracle-database/connect-to-the-oracle-database-using-windows-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="bbf2f-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="bbf2f-135">See Also</span></span>  
[<span data-ttu-id="bbf2f-136">开发 Oracle 数据库应用程序</span><span class="sxs-lookup"><span data-stu-id="bbf2f-136">Develop your Oracle Database applications</span></span>](../../adapters-and-accelerators/adapter-oracle-database/develop-your-oracle-database-applications.md)