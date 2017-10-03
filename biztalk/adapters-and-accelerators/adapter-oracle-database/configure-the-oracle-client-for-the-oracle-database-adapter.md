---
title: "配置 Oracle 数据库适配器 Oracle 客户端 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- net service name
- tnsnames.ora
- configuring, the Oracle client
- connect descriptor
- Oracle client, configuring
- Oracle Net Configuration Assistant
- Oracle Net Configuration Assistant, using the
ms.assetid: 2d4c0f20-b3a6-453f-a9b3-65fd5a38c020
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 209d5603a9f8ff8c09185093efb976afb6432d65
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-oracle-client-for-the-oracle-database-adapter"></a><span data-ttu-id="c708b-102">配置 Oracle 数据库适配器 Oracle 客户端</span><span class="sxs-lookup"><span data-stu-id="c708b-102">Configure the Oracle Client for the Oracle Database adapter</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="c708b-103">本主题是仅当使用 tnsnames.ora 来连接到 Oracle 数据库相关。</span><span class="sxs-lookup"><span data-stu-id="c708b-103">This topic is relevant only if you are using tnsnames.ora to connect to the Oracle database.</span></span>  
  
 <span data-ttu-id="c708b-104">[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]连接到 Oracle 数据库中，通过在计算机上安装 Oracle 客户端。</span><span class="sxs-lookup"><span data-stu-id="c708b-104">The [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] connects to the Oracle database through the Oracle client installed on your computer.</span></span> <span data-ttu-id="c708b-105">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]将 net 服务名称传递到 Oracle 客户端建立与 Oracle 数据库的连接的连接 URI 中指定。</span><span class="sxs-lookup"><span data-stu-id="c708b-105">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] passes the net service name that you specify in the connection URI to the Oracle client to establish a connection to the Oracle database.</span></span> <span data-ttu-id="c708b-106">网络服务名称是 Oracle 客户端用于获取目标 Oracle 数据库服务的连接信息的别名。</span><span class="sxs-lookup"><span data-stu-id="c708b-106">The net service name is an alias that the Oracle client uses to acquire connection information for the target Oracle database service.</span></span>  
  
 <span data-ttu-id="c708b-107">Net 服务名称根据命名方法，它配置为使用 Oracle 客户端解析。</span><span class="sxs-lookup"><span data-stu-id="c708b-107">The Oracle client resolves the net service name according to the naming method that it is configured to use.</span></span> <span data-ttu-id="c708b-108">用于 Oracle Net Configuration Assistant 配置 Oracle 客户端使用的命名方法。</span><span class="sxs-lookup"><span data-stu-id="c708b-108">You use the Oracle Net Configuration Assistant to configure the naming methods to be used by the Oracle client.</span></span> <span data-ttu-id="c708b-109">[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]支持用于连接到 Oracle 数据库的本地命名方法。</span><span class="sxs-lookup"><span data-stu-id="c708b-109">The [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] supports the Local Naming method for connecting to the Oracle database.</span></span> <span data-ttu-id="c708b-110">此方法使用本地文件，tnsnames.ora，若要解决的 net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="c708b-110">This method uses a local file, tnsnames.ora, to resolve the net service name.</span></span>  
  
 <span data-ttu-id="c708b-111">使用 net 服务名称连接包含 Oracle 客户端需要建立与特定的 Oracle 数据库服务 （实例） 的连接的信息的描述符 tnsnames.ora 文件相关联。</span><span class="sxs-lookup"><span data-stu-id="c708b-111">The tnsnames.ora file associates net service names with connect descriptors that contain the information the Oracle client needs to establish a connection to a specific Oracle database service (instance).</span></span> <span data-ttu-id="c708b-112">下面是从 tnsnames.ora 示例条目。</span><span class="sxs-lookup"><span data-stu-id="c708b-112">The following is a sample entry from tnsnames.ora.</span></span>  
  
```  
ADAPTER =  
  (DESCRIPTION =  
    (ADDRESS_LIST =  
      (ADDRESS = (PROTOCOL = TCP)(HOST = yourOracleServer)(PORT = 1521))  
    )  
    (CONNECT_DATA =  
      (SERVICE_NAME = yourOracleDatabaseServiceName)  
    )  
  )  
```  
  
 <span data-ttu-id="c708b-113">在此示例条目，适配器是网络服务名称。</span><span class="sxs-lookup"><span data-stu-id="c708b-113">In this sample entry, ADAPTER is the net service name.</span></span> <span data-ttu-id="c708b-114">连接描述符指定地址信息和与适配器关联的 Oracle 数据库服务的服务名称。</span><span class="sxs-lookup"><span data-stu-id="c708b-114">The connect descriptor specifies address information and the service name of the Oracle database service associated with ADAPTER.</span></span> <span data-ttu-id="c708b-115">你可以使用 Oracle Net Configuration Assistant 创建和配置 tnsnames.ora net 服务名称。</span><span class="sxs-lookup"><span data-stu-id="c708b-115">You can use the Oracle Net Configuration Assistant to create and configure net service names in tnsnames.ora.</span></span> <span data-ttu-id="c708b-116">配置网络服务名称后，可以指定它在连接中的 URI，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="c708b-116">After you have configured the net service name, you can specify it in a connection URI as in the following example.</span></span>  
  
```  
oracledb://ADAPTER  
```  
  
 <span data-ttu-id="c708b-117">有关使用 Oracle Net Configuration Assistant 以及 tnsnames.ora 的详细信息，请参阅 Oracle 数据库 Net 服务管理员的指南。</span><span class="sxs-lookup"><span data-stu-id="c708b-117">For more information about using the Oracle Net Configuration Assistant and about tnsnames.ora, see the Oracle Database Net Services Administrator's Guide.</span></span> <span data-ttu-id="c708b-118">用于特定安装，请查阅你的数据库管理员，了解配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="c708b-118">Consult your database administrator about configuration details for your specific installation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c708b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c708b-119">See Also</span></span>  
[<span data-ttu-id="c708b-120">创建与 Oracle 数据库的连接</span><span class="sxs-lookup"><span data-stu-id="c708b-120">Create a connection to the Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/create-a-connection-to-the-oracle-database.md)